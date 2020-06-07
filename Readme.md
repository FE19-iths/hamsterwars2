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
    - URL till ditt publicerade API (kan behövas för testning)
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

Allmänna principer:
- Använd navigeringslänkar i `<header>`


### Startsida
Här ska du presentera idén med appen.

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
Här ska det finnas ett formulär för att fylla i all information om en tävlande hamster som databasen behöver. All information ska *valideras* så att den är *informativ och användarvänlig*.

---

### Level ups

#### Rättvisare slumpning
Välj bland de hamstrar som haft minst antal matcher, när appen ska slumpa fram hamstrar.

#### Hamsterkatalog
Bläddra igenom alla hamstrar som finns i databasen.

#### Wowfaktor
Använd CSS-animeringar och ljudeffekter för att förhöja användarupplevelsen!

#### Chuck Norris level
Hamster-VM!! Välj ut 8 hamstrar som tävlar 2-3 gånger mot varandra. De 4 som vunnit flest gånger går vidare till semifinal. Vinnarna möter sedan varandra i finalen. (Man kan fortsätta med gruppspel, eller förenkla och bara köra semifinal + final.)

---

## Getting started
Börja med att skapa ett nytt projekt:
```
npx create-react-app ditt-app-namn
```
Det rekommenderas att du har koden i två olika projekt.
