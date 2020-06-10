# Frontendprojekt: HAMSTERWARS
**Ditt projekt är att bygga en frontend till webbplatsen HAMSTERWARS.**
Webplatsen är en spinoff på [Kittenwar](http://www.kittenwar.com), en hemsida där matcher mellan två bilder slumpas fram och publiken röstar på den de finner gulligast. Poäng ska räknas, listor ska sammanställas.

Detta är en fortsättning på [API-projektet som du gjorde tidigare i kursen](https://github.com/johankivi/hamsterwars).


## Relevanta mål

**Kunskaper**
- JavaScript-ramverket React
- Pakethantering med NPM

**Färdigheter**
- Skapa användarvänliga webbapplikationer där innehållet ändras dynamiskt (Single
Page Applications)
- Hantera paket med NPM vid utveckling av webbappplikationer

**Kompetenser**
- Skapa och vidareutveckla Single-Page Applikationer
- Kunna välja och motivera val av ramverk och teknologier utifrån webbapplikationens omfattning och funktionalitet

## Bedömning
**Godkänt**
- Utvecklar en single page app med React.js
- Skapar användarvänliga webbapplikationer
- Väljer och motiverar val av ramverk och teknologier utifrån webbapplikationens omfattning och
funktionalitet

**Väl Godkänt**
- Utvecklar *med säkerhet* en single page app med React.js
- Skapar *med säkerhet* användarvänliga webbapplikationer

---

## Tekniker
- Node.js
- React och react-router
- Ditt API-projekt

## Inlämning
- Ditt projekt ska inkomma senast **tors 18/6 kl 16**.
- Du lämnar in en *textfil* via ITHSdistans.se ( ironic framework ).
- Textfilen ska innehålla:
    - URL till ditt GitHub-repository
    - URL till din publicerade app
    - Eventuella kommentarer
- Kom ihåg att göra ditt repository *public* så läraren kan se det
- Kom ihåg att *testa* appen när du har laddat upp den, innan du lämnar in

---

## App spec
- Appen ska använda React och react-router.
- Gränssnittet ska vara användarvänligt.
- Du ska använda datamodeller och endpoints från API-projektet.


Tips: [Figma](https://www.figma.com/) är ett populärt verktyg för att göra skisser på gränssnitt.

|Route|Vad ska visas|
---|---
|`/`|Startsida
|`/battle`|Rösta på slumpade hamstrar
|`/battle/:id1/:id2`|En specifik matchup
|`/matchup/:id1/:id2`|Resultatet av en match
|`/stats`|Statistik
|`/upload`|Ladda upp en ny hamsterbild


### Startsida
Här ska du presentera idén med appen. Startsidan ska vara det första man ser när man laddar appen. Därifrån kan man gå till *battle*, *statistik* eller *uppladdning*.

**Tips**: använd navigeringslänkar i `<header>`.

### Battle
Två hamstrar ställs mot varandra. Bara en kan vinna. Om det finns parametrar i URL ska de användas, annars två slumpade hamstrar (se routes ovan). Användaren röstar genom att klicka på den bild man tycker bäst om. När man röstat ska resultatet visas.

### Resultat (matchup)
Visa resultatet av en match mellan två hamstrar. Man vill se så mycket information som möjligt om vinnaren - åtminstone bild och namn.

### Statistik
Visa statistik om matcher och tävlande hamstrar.
- totala antalet matcher
- top 5 hamstrar som vunnit mest
- top 5 hamstrar som förlorat mest

### Ladda upp ny hamster
Här ska det finnas ett formulär för att fylla i all information om en tävlande hamster som databasen behöver. All information ska *valideras* så att den är *informativ och användarvänlig*. Man behöver inte kunna ladda upp en riktig bild i grundversionen.

---

### Level ups
Förslag på förbättringar (i ungefärlig svårighetsordning) som du kan göra för att lära dig mer!

#### Wowfaktor
Använd CSS-animeringar för att förhöja användarupplevelsen! (Man kan använda `<audio`-elementet för att spela upp ljud.)

#### API-nyckel
Appen använder en API-nyckel för alla requests.

#### Hamsterkatalog
Bläddra igenom alla hamstrar som finns i databasen.

#### Rättvisare slumpning
Välj bland de hamstrar som haft minst antal matcher, när appen ska slumpa fram hamstrar.

#### Ladda upp bild
Formuläret för att lägga till ny hamster ska kunna ladda upp riktiga bilder.

#### Chuck Norris level
Hamster-VM!! Välj ut 8 hamstrar som tävlar 2-3 gånger mot varandra. De 4 som vunnit flest gånger går vidare till semifinal. Vinnarna möter sedan varandra i finalen. (Man kan fortsätta med gruppspel, eller förenkla och bara köra semifinal + final.)

---

## Getting started
Ett förslag på hur man kan lägga upp projektet:

1. gör en skiss - Figma, HTML + CSS
2. lägg in skissen i en React-komponent (bara JSX)
3. använd *props* för att skicka (påhittad) data till komponenterna
4. lägg till *state* och *events*
5. lägg till riktig data - skicka GET och POST *reqests* till API:et

Sedan får man upprepa detta för alla olika vyer, tills appen är klar. Försök att jobba mot en **MVP** (minimum viable product) och vänta till senare i projektet med att ta in sådant som inte är lika viktigt. Försök också att jobba med en *feature* i taget. Testa gärna appen på dina klasskamrater flera gånger under projektet. Feedback kan vara oerhört värdefull.


## Publicering / deploy
*Den här guiden förutsätter att du antingen har laddat upp databasen med Firebase/Firestore och kan anropa den från Express-servern. Du behöver inte göra något för att databasen ska fungera.*

**1.** Börja med att skapa ett nytt projekt. Vi använder frontend-projektet som bas eftersom create-react-app automatiskt skapar ett nytt repository med bra inställningar.
```bash
npx create-react-app ditt-app-namn
```
---
**2.** Nu ska du kopiera in ditt API-projekt i frontend-projektet. Skapa en mapp med namnet `server/` och lägg backend-filerna där. *Obs! Flytta över det som finns i* `server/package.json` *till* `./package.json`. (Om du glömmer detta så kommer server-mappen att få en pil på sig på GitHub och inte gå att klicka på.)
Så här kan din mappstruktur se ut:
```text
|- .git/
|- .gitignore
|- package.json
|- Procfile              <-- skapa den här, se steg 6
|- src/                  <-- här hamnar React-appen
|- build/                <-- skapas när du bygger frontend-appen med "npm run build"
|- server/               <-- skapa den här!
    |- package.json      <-- ta bort  (flytta innehållet till andra package.json)
    |- .git/             <-- ta bort
    |- .gitignore        <-- ta bort
    |- server.js
    |- ...
```

Resten av guiden förutsätter att filen som du startar servern med heter `server.js`.

---
**3a.** Heroku bestämmer vilken port som Express ska använda. Uppdatera `server.js` så att den använder rätt port.
```javascript
// Använd en variabel till portnumret
const port = 2048;   // FEL
const port = process.env.PORT || 2048;   // RÄTT

// Använd static middleware för att serva de byggda frontend-app-filerna
// Det kan se annorlunda ut om man använder express-router
server.use(express.static(__dirname + '/../build'));

// Glöm inte att starta servern med rätt portnummer
// Man kan se allt som skrivs ut med console.log från Heroku webbsidan
server.listen(serverPort, () => console.log('Server is listening on port ' + serverPort));

```
---
**3b.** För att det inte ska bli konflikter mellan routing i frontend och backend, kan du ändra alla backend-routes så att de börjar med `/api`:
```text
/hamsters --> /api/hamsters
/hamsters/:id --> /api/hamsters/:id
osv.
```

---
**4.** Lägg till och committa backend-filerna till ditt lokala repo.

---
**5.** Skapa ett nytt repository på GitHub för hela projektet. När du skapat ett repo visar GitHub vad man ska skriva *i terminalen* för att koppla ihop ditt repo på GitHub med ditt lokala repo. Det bör se ut så här:
```bash
git remote add origin https://github.com/ditt-användarnamn/ditt-repo.git
git push -u origin master
```
Ladda om sidan på GitHub för att kontrollera att filerna har laddats upp.

---
**6.** Nu ska vi förbereda repot så att Heroku vet hur det ska göra för att bygga och publicera appen. (*build och deploy*) Skapa en fil med namnet `Procfile` (stort P, ingen filändelse, inte ens .txt) i projektets root med följande innehåll:
```text
release: npm run build
web: node server/server.js
```

Detta betyder att när Heroku ska publicera en ny **release** av appen, så ska den börja med att bygga frontend-appen. (Heroku kör automatiskt `npm install` innan den kör `npm run build`.) Detta kommer att skapa filer i mappen `build/`.

När releasen är byggd kommer Heroku att starta **web** appen genom att köra filen `server/server.js`.

---
**7.** Skapa ett konto på [Heroku](https://heroku.com/). Klicka på `New -> Create new app`.

---
**8.** Koppla ihop Heroku med GitHub. Skriv in namnet på ditt GitHub-repo. Slå på *Automatic deploy from master*. Från och med nu, varje gång du pushar en ny version till GitHub, så kommer Heroku att *bygga och publicera* den. Avsluta med att klicka på *Deploy branch* för att publicera direkt.

Klicka på `Open app` för att testköra. Håll tummarna!

---
**9.** Express-servern servar både frontend och backend. När du skickar GET/POST request med AJAX så är det till samma webbserver. Men man vill ibland använda olika URL till *development* och *production*. Enklaste sättet att lösa detta är att lägga till en *proxy* i package.json. Den används bara när man kör `npm run start` lokalt.

Lägg till en rad med ordet `proxy` och URL till din lokala webbserver, efter `scripts`:
```json
"scripts": {
  "start": "react-scripts start",
  "build": "react-scripts build",
  "test": "react-scripts test",
  "eject": "react-scripts eject"
},
"proxy": "http://localhost:1234",   <- lägg till den här
```

Alternativ lösning: create-react-app skapar en variabel, vars värde beror på om vi använt `npm run start` (utvecklingsversionen) eller `npm run build` (production). Du kan bli tvungen att lägga till stöd för CORS i servern.
```javascript
let baseUrl;
if( process.env.NODE_ENV === 'production' ) {
	// Vi behöver inte ange HTTP eftersom AJAX stannar kvar på samma server
	baseUrl = '/api';
}
else {  // 'development'
	// Använd portnumret från din serverfil, steg 3a
	baseUrl = 'http://localhost:1234/api';
}
const response = await fetch(baseUrl + '/hamsters');
const allTheHamsters = await response.json();
```
