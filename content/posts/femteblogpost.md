---
title: "Undervisning 5 – AI-drevne applikationer og LLM API"
date: 2026-04-24
draft: false
summary: "Kort om hvad en AI-drevet applikation er, og hvordan man bygger en med et LLM API"
---

I denne undervisning arbejdede vi med **AI-drevne applikationer** og hvordan man integrerer en **LLM via API** i sin egen software.

## Hvad er en AI-drevet applikation?

En AI-drevet applikation er en app, hvor AI er en **central del af funktionaliteten**.

Fx:
- tager input fra brugeren  
- analyserer det med en model  
- returnerer et svar eller en vurdering  

Et eksempel var en app, der **vurderer en opgave ud fra en rubric**.

## Hvad skal der til?

For at bygge det skal man bruge:

- **Frontend** → brugerinterface  
- **Backend** → håndterer logik og API-kald  
- **LLM API** → selve AI’en  
- **Dataflow** → hvordan data bevæger sig frem og tilbage  

Man bruger altså AI som en **ekstern service**.

## Hvordan fungerer det?

1. Bruger sender input  
2. Backend sender request til LLM  
3. Man bruger:
   - system prompt  
   - user prompt  
4. Modellen returnerer svar  
5. Svaret bruges i appen  

## Vigtige ting

- **Promptstruktur** → påvirker resultatet meget  
- **Struktureret output** (fx JSON) → nemmere at bruge i kode  
- **Fejlhåndtering** → API kan fejle eller give mærkelige svar  
- **Async kode** → API-kald tager tid  

## Dagens opgave

Byg en mini-app der:
- bruger et LLM API  
- vurderer en opgave  
- har frontend eller REST client  
- dokumenterer løsningen  

## Mine tanker

Det her føles mere som “rigtig” udvikling med AI.  
Man bruger ikke bare en chatbot, men bygger en app hvor AI er en del af systemet.

AI gør ikke arbejdet for dig – men ændrer måden man arbejder på.