Back to [[FJSx23]]
### The Dashboard
I denna uppgift ska du bygga en personlig dashboard som användaren kan ha som startsida i sin webbläsare. Denna dashboard kommer både ha delar som användaren kan anpassa själv samt information som hämtas från API:er.

![Dashboard](https://qlok.notion.site/image/https%3A%2F%2Fprod-files-secure.s3.us-west-2.amazonaws.com%2F76ff052e-5519-4c95-9c8a-d50fbda370ef%2F36136f2a-752b-4269-9100-a3f1a20f2dbf%2FDesktop_-_2.png?table=block&id=34cb9fd1-b095-45d3-88d3-342c4dfea306&spaceId=76ff052e-5519-4c95-9c8a-d50fbda370ef&width=2000&userId=&cache=v2)

##### Övergripande Krav
- [x] Endast ren HTML, CSS och JavaScript är tillåten.
- [x] Dashboarden ska spara inställningar mellan reloads (LocalStorage).
- [x] Designen måste inte följa den mockup som finns i denna uppgiften men försök gärna efterlikna den för att också öva på CSS.
##### Funktionalitet
![Dashboard Legend](https://qlok.notion.site/image/https%3A%2F%2Fprod-files-secure.s3.us-west-2.amazonaws.com%2F76ff052e-5519-4c95-9c8a-d50fbda370ef%2Ffc850c6d-28f0-474b-8b75-c34dff6fc0ed%2FDesktop_-_3.png?table=block&id=995f1d99-1a34-4566-916b-8a96057af3f4&spaceId=76ff052e-5519-4c95-9c8a-d50fbda370ef&width=2000&userId=&cache=v2)
1.  [x] Här ska klockslag och datum synas och klockan ska ändras när tiden ändras utan att sidan laddas om.
2.  [x] Rubriken på sidan ska användaren kunna ändra genom att klicka på den. När användaren klickat på rubriken blir den redigerbar och ändringarna sparas direkt.
3.  [x] Denna del innehåller länkar som användaren sparat. Användaren kan ta bort länkar (3a) samt lägga till nya (3b). När användaren lägger till nya länkar ska användaren fylla i länken samt en rubrik som denna vill ska synas i dashboarden.
	- [x] **Extra: Hämta länkens favicon och visa som bild i dashboarden.**
4.  [x] Här ska vädret i närtid visas. Denna behöver inte se ut exakt som i skissen men det ska vara data som hämtas från något öppet API. För att avgöra vilken stad vädret ska visas för ska browserns geolocation-api användas.
	- [x] **Extra: Gör så att användaren kan anpassa orten som visas.**
5.  [x] Denna del får du fritt bestämma vad den ska innehålla. Det ska dock vara data från ett externt API och exempelvis kan det vara senaste nyheterna eller aktiekurser.
6.  [x] I den här delen ska användaren kunna skriva snabba anteckningar. Tänk en stor textarea bara där det som skrivs sparas hela tiden. Det ska inte finnas flera olika anteckningar utan bara just en yta.
7.  [x] När användaren klickar på denna knapp ska en randomiserad bild från Unsplash API hämtas och läggas in som bakgrund på dashboarden.
	- [x] **Extra: Låt användaren fylla i ett sökord som används för att hitta en randomiserad bild så att det blir inom ett tema som användaren önskar.**
##### VG-Kriterium
- [x] I din readme-fil på github ska du ha med ett resonemang kring din kod. I denna ska du nyanserat resonera kring styrkor och brister i ditt genomförandet, alltså i den kod du utvecklat. VG-nivån bedöms genom kvalitén på koden i kombination med din förmåga att se just styrkor och brister i den. Detta betyder att om din kod har allt för låg kvalité räcker det inte med resonemang kring det för att rädda upp, men det betyder också att ingen kod behöver vara helt perfekt men det är bra att du själv kan peka på de brister du då ser.