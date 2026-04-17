---
title: "Undervisning 2 – RAG"
date: 2026-04-13
draft: false
summary: "Introduktion til Retrieval Augmented Generation og egen chatbot"
---



I denne undervisning arbejdede vi med noget der hedder **RAG (Retrieval Augmented Generation)**.

## Hvad er RAG?

RAG står for Retrieval-Augmented Generation og er en metode inden for kunstig intelligens, der kombinerer informationssøgning med tekstgenerering. Formålet med RAG er at gøre AI-modeller mere præcise og opdaterede ved at lade dem hente relevant information fra eksterne kilder, før de genererer et svar.
I stedet for kun at basere sig på den viden, modellen er trænet på, kan en RAG-model slå op i eksempelvis dokumenter, databaser eller interne vidensbaser. Det betyder, at svarene bliver mere faktabaserede og relevante i forhold til brugerens spørgsmål.
RAG består typisk af tre hoveddele:
- Indeksering (Indexing)
Før systemet kan bruges, bliver dokumenter delt op i mindre dele og gemt på en måde, så de hurtigt kan søges i. Disse dele kaldes chunks. Hver chunk bliver omdannet til en såkaldt embedding, som gør det muligt for systemet at sammenligne og finde relevant indhold.
- Retrieval (Søgning)
Når brugeren stiller et spørgsmål, bliver spørgsmålet også omdannet til en embedding. Systemet søger derefter efter de chunks, der minder mest om spørgsmålet, og vælger de mest relevante tekststykker.
- Generation (Generering)
De fundne chunks sendes til en sprogmodel, som bruger informationen til at formulere et svar. På den måde bliver svaret baseret på konkrete kilder i stedet for kun modellens træning.
En vigtig del af RAG er brugen af chunks. Da dokumenter ofte er lange, bliver de opdelt i mindre tekststykker for at gøre søgningen mere præcis og effektiv. Hvis man arbejdede med hele dokumenter, ville systemet have sværere ved at finde præcis den relevante information. Chunks gør det derfor muligt at hente små, målrettede dele af teksten, som passer direkte til brugerens spørgsmål.
Ofte arbejder man også med overlap mellem chunks, så vigtig information ikke går tabt i opdelingen.
Sammenfattende kan man sige, at RAG gør AI-systemer bedre ved først at finde relevant information og derefter bruge den til at generere mere præcise og troværdige svar.

---

## Hvordan virker det?

Vi lærte, at RAG fungerer sådan:

1. Man lægger sine dokumenter ind  
2. De bliver lavet om til **embeddings** (tal som AI kan forstå)  
3. Når man stiller et spørgsmål:
   - systemet finder relevante tekststykker  
   - og sender dem med til AI'en  
4. AI’en svarer ud fra både sin viden og de fundne data  

---

## Praktisk arbejde (Diffy)

Vi arbejdede i **Diffy**, hvor vi byggede vores egen chatbot.

- https://cloud.dify.ai/app/edabd953-ac4f-4231-815f-6eeee6689e10/configuration


Her kunne vi:
- uploade vores egne data  
- teste hvordan chatbotten svarede  
- justere og forbedre svarene  

Det var interessant at se, hvordan svarene blev bedre, når vi gav den relevant data.

hertil forsøgte vi med studieordningen.
---

## Hvornår giver RAG mening?

Vi snakkede om, hvornår RAG er en god idé:

Godt når:
- man har egne dokumenter  
- man vil have præcise svar  
- man arbejder med specifik viden  

Mindre godt når:
- man bare stiller generelle spørgsmål  
- man ikke har noget data at koble på  

---

## Mini-projekt

Opgaven var at lave en simpel chatbot baseret på vores eget materiale.

Formålet var:
- at forstå hvordan RAG fungerer i praksis  
- at eksperimentere med AI og data  
- at bygge noget selv  

---

## Det har jeg lært

- hvad RAG er  
- hvordan AI kan bruge egne data  
- hvad embeddings er  
- hvordan man kan bygge en chatbot  

---

## Mine tanker

Jeg synes det var spændende at arbejde med AI på den her måde.  
Det var fedt at kunne bruge sine egne data og se, hvordan det påvirker svarene.

Det var lidt teknisk, men også meget relevant i forhold til fremtidig teknologi.

---

