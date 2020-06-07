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

### Ladda upp ny hamsterbild
Här ska det finnas ett formulär för att fylla i all information om en tävlande hamster som databasen behöver. All information ska *valideras* så att den är *informativ och användarvänlig*. Man behöver inte ladda upp en riktig bild i grundversionen.

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
Formuläret för att lägga till ny hamster ska ... riktig bild...

#### Chuck Norris level
Hamster-VM!! Välj ut 8 hamstrar som tävlar 2-3 gånger mot varandra. De 4 som vunnit flest gånger går vidare till semifinal. Vinnarna möter sedan varandra i finalen. (Man kan fortsätta med gruppspel, eller förenkla och bara köra semifinal + final.)

---

## Getting started / publicering / deploy
*Den här guiden förutsätter att du har laddat upp databasen med Firebase/Firestore och kan anropa den från Express-servern.*

1. Börja med att skapa ett nytt projekt:
```bash
npx create-react-app ditt-app-namn
```
2. Nu ska ditt lokala repo kombineras med ditt API-projekt. Skapa en mapp med namnet `server/` *inuti* frontend-projektet. Kopiera ditt API-projekt till server-mappen. (Flytta över det som finns i `server/package.json` till `package.json`.)

3. Skapa ett nytt repository på GitHub och koppla ihop det med ditt lokala repo.

3. Lägg till ett start-script i package.json så Heroku vet hur den ska starta din server:
```javascript
"scripts": {
    "start": "node server/server.js"
}
```
3. En Heroku-app kan inte använda alla portar. Uppdatera `server.js` så att Heroku kan ge appen rätt port:
```javascript
const port = 2048;   // FEL
const port = process.env.PORT || 2048;   // RÄTT
```
4. Heroku är en molntjänst som vi kan använda gratis för att publicera (*deploy*) små Node-appar på nätet. Man kan publicera via ett Command Line Interface eller via GitHub. Vi använder GitHub. Gå till [Heroku.com](https://heroku.com) och skapa ett konto med hjälp av GitHub.

5. Gå till https://dashboard.heroku.com/apps och välj menyn New - Create New App. Hitta på ett namn på appen, t.ex. "Hamsterwars123". (Det måste vara unikt.) Välj "Europe" som region och klicka på "Create app".

6. I rutan som heter "Deployment method" väljer du "Connect to GitHub". Skriv in namnet på ditt GitHub-repo, klicka på "Search" och "Connect".

7. Klicka på "Deploy branch" för att publicera innehållet i master-branchen till din Heroku-domän. Kryssa i "Automatic deploys from master" om du vill att det ska göras automatiskt varje gång du committar till master. (rekommenderas)

8. Nu kan du klicka på "Open App" för att testköra din app. Men än så länge är bara API:et publicerat...

9. Fortsättning följer...


Så här kan din mappstruktur se ut:
```text
|- .git/
|- .gitignore
|- package.json
|- src/
|- build/         <-- skapas när du bygger frontend-appen
|- server/
    |- package.json      <-- ta bort  (ska bara finnas i roten)
    |- .git/             <-- ta bort
    |- .gitignore        <-- ta bort
    |- server.js
    |- modules/          <-- organiserade API-projektet
```
