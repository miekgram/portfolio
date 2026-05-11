---
title: "Undervisning 9 – Projektstart"
date: 2026-05-11
draft: false
summary: "Projektstart, projektbeskrivelse og første systemskitse til vores AI-drevne applikation."
---

I denne undervisning gik vi i gang med vores projekt. Efter en kort snak i klassen satte jeg mig sammen med min makker Rikke, og vi begyndte at konkretisere vores idé ud fra casen med **Engestofte Gods**.

Dagens output var en **projektbeskrivelse** og en **systemskitse**, hvor vi skulle beskrive problemet, brugeren, løsningen og hvordan systemet kunne bygges.

## Projektidé

Vores arbejdstitel blev:

**Ny samlet platform for bryllup/organisering + reminder**

Problemet vi vil arbejde med, handler om overblik, informationsdeling og manuelle processer. I dag skal Johan selv flytte informationer mellem mails, dokumenter, e-conomic og Trello. Det tager tid, og der kan nemt opstå fejl eller manglende opdateringer.

Vores idé er derfor at bygge et standalone program, som kan samle information om bryllupper ét sted og gøre det nemmere at holde styr på opgaver, deadlines og manglende oplysninger.

## Vores foreslåede løsning

Vi vil lave en prototype på en app, som giver et samlet overblik over bryllupper og de vigtigste informationer.

Appen skal blandt andet kunne vise:

- kommende bryllupper  
- opgaver og frister  
- manglende oplysninger  
- dokumenter og noter  
- reminders i systemet  

Derudover vil vi gerne gøre systemet klar til AI, så man senere kan uploade dokumenter eller mails, hvorefter AI kan læse informationerne og placere dem de rigtige steder.

## AI-funktion

AI skal bruges til at hjælpe med at fordele informationer automatisk. For eksempel kunne AI læse en kontrakt eller en mail og finde oplysninger som dato, antal gæster, navne, aftaler og deadlines.

Til en start bygger vi dog kun en MVP, hvor AI-funktionen er tænkt ind i strukturen, men ikke nødvendigvis fuldt implementeret.

## Systemskitse

Vi lavede også en skitse over, hvordan systemerne kunne tale sammen.

I midten har vi vores egen app, **EG Admin**, som skal fungere som det centrale system. Den skal kunne forbindes med mailsystem, Trello API og på sigt e-conomic. Derudover skal appen indeholde et reminder-system og AI-mappeoverblik.

![Systemskitse](/images/systemskitse-eg-admin.svg)

## Hvad vi byggede

Vi begyndte også at formulere en prompt til vores kodeagent. Prompten beskrev blandt andet vores tech stack:

- React til frontend  
- Java med Javalin til backend  
- PostgreSQL som database  
- Docker og Docker Compose  
- mulighed for senere OpenAI API-integration  

Vi fik projektet op at køre og fik lavet en fin startside, som vi fremadrettet skal bygge videre på.

![Startside for EG Admin](/images/eg-admin-startside.svg)

## Hvad jeg lærte

- en projektidé bliver mere konkret, når man skriver problem, bruger og MVP ned  
- det er vigtigt at afgrænse projektet, så det ikke bliver for stort  
- en systemskitse hjælper med at forstå, hvilke dele der skal tale sammen  
- en god prompt til en kodeagent kræver mange konkrete detaljer  

## Resultat

Vi endte dagen med en klarere projektbeskrivelse, en første systemskitse og en fungerende start på vores applikation. Det gav et godt fundament for det videre arbejde med projektet.
