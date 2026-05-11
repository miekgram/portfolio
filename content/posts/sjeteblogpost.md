---
title: "Undervisning 6 – Implementering af LLM API"
date: 2026-04-27
draft: false
summary: "Fra idé til fungerende AI-app: implementering af rubric, prompts og LLM API i praksis"
---

I denne undervisning arbejdede vi med at **implementere en AI-drevet applikation i praksis**.  
Fokus var ikke længere kun design – men at få en **samlet løsning til at fungere end-to-end**.

## Hvad gik dagen ud på?

Vi byggede videre på arbejdet fra gang 05, hvor vi havde designet:

- rubric til vurdering  
- prompts (system + user)  
- struktur for løsningen  

I dag handlede det om at **omsætte det til kode**, så man faktisk står med en applikation, der virker.

Målet var at lave en app hvor:

- en bruger uploader en praktikrapport  
- rapporten sendes til en LLM via API  
- modellen vurderer den ud fra en rubric  
- og returnerer et struktureret svar  

## Hvad jeg konkret lavede

Jeg byggede en mini-applikation med:

- **Java backend** → håndterer API-kald og logik  
- **React frontend** → gør det nemt at indsætte en rapport og se resultatet  
- **OpenAI API** → selve vurderingen  

Derudover arbejdede jeg med:

- at lave en **systemprompt** med rubric  
- at lave **userprompts** til vurdering  
- at strukturere output (markdown)  
- at gemme resultater i `/output`  

![Praktikrapport vurdering med OpenAI API](/images/praktikrapport-vurdering-openai-api.svg)

Jeg satte også:

- **.env til lokal udvikling** (API key)  
- **GitHub Secrets** til sikker håndtering i CI  

## Hvordan det fungerer (bagved)

Selvom det virker simpelt i frontend, sker der flere ting bagved:

### 1. Bruger → Frontend
Brugeren indsætter eller uploader en rapport i React-appen.

### 2. Frontend → Backend
Frontend sender rapporten til backend via et API endpoint (fx `/evaluate`).

### 3. Backend → LLM (OpenAI API)
Backend:

- henter **systemprompten** (med rubric)
- indsætter rapporten i **userprompten**
- sender en request til OpenAI API

Requesten indeholder typisk:

- system prompt → styrer hvordan modellen skal tænke  
- user prompt → selve opgaven  
- model → fx GPT  

### 4. LLM → Backend
Modellen returnerer et svar (ofte tekst eller struktureret output).

Backend:

- parser svaret  
- evt. tjekker for fejl  
- sender det videre til frontend  

### 5. Backend → Frontend
Frontend modtager vurderingen og viser den (fx som markdown).

## Dataflow (kort fortalt)

Det er altså en kæde, hvor AI’en er en **ekstern service**, som backend taler med.

## Hvad var vigtigt i dag

Fokus var ikke perfektion, men at få tingene til at hænge sammen:

- API-kald virker  
- prompts giver brugbare svar  
- output kan bruges i appen  

Derudover arbejdede vi meget med:

- **debugging** → hvorfor virker det ikke?  
- **iteration på prompts** → små ændringer = store forskelle  
- **fejlhåndtering** → hvad hvis API fejler?  
- **test på rigtige eksempler**  

## Hvad jeg lærte

Det vigtigste jeg tog med var:

- hvordan man går fra **idé → fungerende system**  
- hvor vigtigt **promptdesign** er for output  
- hvordan AI indgår som en **del af en arkitektur**, ikke bare en chatbot  

Det her føles klart som mere “rigtig udvikling”, fordi:

- man bygger noget, der faktisk kan bruges  
- man skal få flere dele til at spille sammen  
- og AI er kun én del af hele systemet  

## Resultat

Jeg endte med en første version af en **LLM-drevet vurderingsapp**, hvor:

- rubric, prompts og API er integreret  
- en rapport kan vurderes automatisk  
- output vises struktureret  

Der er stadig ting, der kan forbedres – men systemet virker, og det er det vigtigste første skridt.
