Back to [[FJSx23]]
### What is it?
GraphQL is a query language for APIs that allows clients to request exactly the data they need, no more and no less. It offers flexibility compared to traditional REST APIs by enabling clients to define the structure of the response. Clients can ask for multiple resources in a single request, reducing the need for multiple API calls. It’s widely used for optimizing data-fetching in complex applications, especially in modern web and mobile apps, and helps in improving performance by avoiding over-fetching or under-fetching of data.

Installation:
`npm i @apollo/server graphql`

Two dependencies, one for the apollo server and the other for parsing and executing algorithms.
### Defining the GraphQL Schema

Schemas are a collection of type definitions that define the "shape" of queries that are executed against your data.

```typescript
export const typeDefinitions = `#graphql

type Book {
	title: String
	author: String
}

type Author {
	id: ID!
	name: String
	age: Int
}

type Query {
	books: [Book]
}
`
```

### Initializing Apollo Server

```typescript
import { ApolloServer } from '@apollo/server';
import { startStandaloneServer } from '@apollo/server/standalone';

import { typeDefinitions } from "./graphql/schema.js";

const server = new ApolloServer({
  typeDefinitions,
  resolvers,
});

startStandaloneServer(server, {
  listen: { port: 4000 },
}).then(({ url }) => {
  console.log(`Server ready at: ${url}`);
});
```