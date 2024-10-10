Back to [[FJSx23]] / [[Express]]
### What is it?
Passport.js is an authentication middleware for express that supports multiple authentication strategies such as local (username/password) and third-party OAuth providers (Google, Facebook, etc.). It integrates with Express and works well with [session](session) to handle user authentication, storing user data in the session for persistent logins.

Installation:
`npm install passport`
##### Initializing passport:

```javascript
import passport from "passport";

...

app.use(passport.initialize());
app.use(passport.session());    <- //if used with session
```

##### The authentication function, initialization of Strategy:
Usually, for separation of concerns and to keep code cleaner, the function which will be called on the route that will authenticate users, will be placed in a separate strategy file. Local and other OAuth2 authentication strategies will be placed and handled in separate files. Each strategy will be its own dependency and must be installed separately. See available strategies at [passportjs.org](https://www.passportjs.org/packages/)

Inside `./strategies/localStrategy.ts`:
```javascript
import passport from "passport";
import { Strategy as LocalStrategy } from "passport-local";

passport.use(new LocalStrategy({ usernameField: email }, (email, password, done) => {
	try {
        const user = await prisma.user.findUnique({
          where: {
            email: email,
          },
        });

        if (!user) return done(null, false, { message: "Incorrect email." });

        const isMatch = await bcrypt.compare(password, user.password);
        
        if (!isMatch) return done(null, false, { message: "Incorrect password." });

        return done(null, user);
      } catch (err) {
	      return done(err);
      }
}))
```

Inside `./authenticationRoutes.ts`:
```javascript
authRoutes.post("/api/authenticate", passport.authenticate("local"), (req, res) => {
	res.status(200).json({ message: "Auth successful", user: req.user });
})
```

- `new Strategy(options?, callback)` the options are optional, you can tell passport the name of the field where your usename will come from, in this case its email, because we want the email to be the username in our local strategy.
- `done(error, user?, options?)` we call the done function and attach the user object when we deem the user to have passed all checks for authentication. Passport will then attach the user to the `request` object. Immediately after this, the `serializeUser()` function will be called that will serialize the user, which means assign the user a session id, a cookie with said session id and attach his session id to the `req.session.passport.user object.
##### The roles of `serializeUser()` and `deserializeUser()`:

- `serializeUser()` role is to insert the unique user identifier into session @ `req.session.passport.user` after `passport.authenticate()` has been called and successfully authenticated a user. It will (in the background) create a session id, attach it to a cookie for the client and keep track of that session id in the `req.session` object. 
- `deserializeUser()` role is to check if the users session cookie/sessionID is still valid on each subsequent request, after the user has been authenticated and serialized. IF the cookie session id and the session id inside `req.session` match, the `done()` function will attach the entire user object into `req.user` indicating that the user is still logged in, and has a valid ongoing session.

```javascript
passport.serializeUser(function(user, done) {
    done(null, user.id);
});              │
                 │ 
                 │
                 └─────────────────┬──→ saved to session
                                   │    req.session.passport.user = {id: '..'}
                                   │
                                   ↓           
passport.deserializeUser(function(id, done) {
                   ┌───────────────┘
                   │
                   ↓ 
    User.findById(id, function(err, user) {
        done(err, user);
    });            └──────────────→ user object attaches to the request as req.user   
});
```



