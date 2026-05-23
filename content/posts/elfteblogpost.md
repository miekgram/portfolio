---
title: Projekt process og fremdrift del 2
categories: ["project, sparring"]
tags: ["Project"]
date: 2026-05-22
draft: false
featureimage: ""
authors:
  - rikke
---

# Fremgang i projektet

Denne post vedrører fremgangen i projektets udvikling og hvordan det går. 

## Videre arbejde

Vores næste skridt var: 
- Github repo - Som jeg satte op da det projekt vi besluttede at gå videre med var på hendes pc.
- Afvente svar fra kunden, hvor vi har fået nogle enkelte svar, men de vil sende skabeloner på tirsdag den 26. maj.
- AI integrationen af en LLM. 

Vi havde endvidere lavet en liste med ting vi umiddelbart kunne se der manglede. Dog vil vi i dag fokusere på LLM-integrationen og lave en foreløbigt prompt til LLM'en.


### AI integration
*Hvad skal den kunne*
- Den skal kunne læse PDF dokumenter
- Den skal kunne aflæse og udtrække konkrete informationer fra dokumentet, og opdele det i mapper
    - Brudepars navn, dato, kuvertantal, menu-valg, drikkelse, blomster, tillæg, overnatning 
- Indsætte DE KORREKTE informationer fra dokumenter i de rigtige felter.
    - Brudepars navn, dato, kuvertantal, menu-valg, drikkelse, blomster, tillæg, overnatning 
- Oprette relevante frister vedrørende manglende udførte opgaver
    - Og opdatere udfra oplysninger fra dokumenter
    - Bestilling af lager, opstilling, ansatte
- Oprette relevante frister vedrørende manglende oplysninger fra brudeparret
    - Endeligt kuvertantal, allergener, overnatning, bordplan
- Påminde om forekommende frister  

*Hvilken LLM bruger vi*
Vi har tænkt os at benytte OpenAIs API

*Vi skal give den et eksempel på et tilbud/kontrakt*
Dette har vi fået chatgpt til at lave, da vi endnu ikke har modtaget noget fra EG.

## Dagens arbejde
1. Git repo
Vi startede med at lave repo, og få rikke som collaborator.

2. AI kan læse dokumenter og udtrække oplysninger og indsætte de korrekte oplysninger
Dernæst udarbejdede vi den liste ovenfor, som vi sendte til hver vores kodeagent, med prompten: 
"Vi skal nu have integreret en LLM som kan nedenstående punkter, vil du hjælpe med at lave integrationen, opsætningen og prompten til den LLM. Husk at det skal være nemt at danne sig et overblik over opsætningen i programmet. Lav gerne et markdown fil med hvordan og hvorledes det er gjort. Jeg skal også bruge en gitignore fil til min ENV, da ENV'en ikke skal med i github, og du må heller ikke kigge i env filen. "

Jeg bruger Cursor, samt plan-mode, så jeg ved hvad den tænker at udføre. Den stilte to gode spørgsmål, nemlig om AI'en skal indsætte værdien uanset hvad eller om der skal et menneske indover. Vi valgte semi-trusting og gøre det med 90 % certainty. Derudover spurgte den om hvordan fristerne skulle fungere, kun i applikationen eller påbegynde arbejde til e-mail påmindelser, vi valgte at gå kun i applikationen. 

jeg bruger Codex.

Vi havde begge problemer ved iteration af vores prompt med API'en, men mit problem var et simpel .env problem, og rikkes var læsningen. Endnu en gang vandt Codex over claude/cursor. Selvom at codex tog lidt længere tid. Cursors resultat var at den ikke kunne finde oplysningerne i dokumentet, på trods af det skulle være letlæseligt i rikkes kontrakteksempel.

Ved mit er der dog nogle mangler i form af design og oplysninger dukker op to gange.

Da rikket fik cursor til at tilrette oplysningerne, så kunne den godt finde oplysningerne i dokumentet.

Vi valgte at gå med Rikkes resultat for denne del af opgaven.
Vi merged det ind i main, og jeg lavede en ny branch

3. Oprette relevante frister
Prompt til frister:
"Nu skal vi rigtigt have det sjovt. Vi skal nemlig sørge for at ved oprettelse af et bryllup, samt uploading af nye dokumenter, at de rigtige frister bliver oprettet og tilrettet. Såsom at når vi uploader en kontrakt eller andet dokumentation, at fristerne bliver tilrettet. Endvidere skal de ansvarlige også have mulighed for at tilrette disse frister. Frister skal også automatisk opdateres hvis informationen de vedrører bliver opdateret. Giver det mening eller har du spørgsmål?

Frister vi VED vi skal have med:
Allergener: 30 dage før bryllupsdatoen
Booking af overnatning: 15. februar
Bordplan: 5 dage før bryllupets afholdelse
Køb af inventar: To uger inden bryllup
Er depositum betalt: to uger efter tilbud er afsendt
Er tjenere tilføjet bryllup: 30 dage før
"

Den her prompt kører jeg direkte i agent-mode. Cursor blev færdigt først, og havde gjordt det umiddelbart ret tilfredsstillende, vi skulle dog ændre teksten på fristerne da de virkede tvetydige såsom: "Bordplan modtaget", til "Er bordplan modtaget?". Derudover kørte jeg en prompt mere med at ændre udseendet på dashboardet, da frister der er langt fra tidsfristen (1. uge) ikke dukker op: "kan vi gøre så de frister der ikke er overskredet eller længere væk end 7 dage ikke kommer op på dashboardet?"

Det virker!

Så har vi lavet AI-integrationen med aflæsning af dokumenter og frister. Dog skal vi have testet om tillægskontrakter med ændringer til f.eks. menu-en virker.



## TO-DO liste
- Vi har ikke opsat en database på PGadmin, og vi skal også finde ud af hvilke oplysninger vi har brug for at gemme deri  
- Vi skal have sat nogle faste datoer for frister.  
  - Når man laver et nyt bryllup oprettes der ikke frister. Vi skal lave en liste af frister/opgaver som automatisk skal oprettes. J skal kunne administrere denne “skabelon”... Tidslinje    
- Oplysninger skal udspecificeres \- Faste oplysninger fra tilbud skal indsættes/forventes ud fra skabeloner  
- Opgaver og frister fra dashboard skal linke direkte til opgaver/frister  
- Opgaver og frister skal kunne tildeles Brian/J både automatisk og manuelt.  
- Login funktion  
- User dashboard og admin dashboard  
- Sikre mobile version  
- Skal man kunne oprette menu ud fra tidligere muligheder?  
- Tests  
- sikre at nyere informationer er vigtigere \- ie. tillægskontrakter  
- kalender funktion  
- man skal kunne ændre oplysninger igen fx antal gæster osv.  
- den sætter ikke ansatte på og den skal selv kunne lave frister ud fra datoerne i stedet for man skal ind og oprette en frist.
- mobile version og deployment
- Standard pakkevalg for mad, drikkelse etc.'
- Vi skal kunne ændre valg af mad, drikkelse etc. direkte inde i programmet

### Prioritering og de næste skridt (erfaringer)

Vi skal benytte os af J og MMs skabeloner, som vi har modtaget i dag, men i første iteration benyttede vi bare vores egen.

Vi skal kunne ændre oplysninger f.eks. menu-valg, blomster etc. DEM ALLE SAMMEN. - Hvis disse ændres, skal eventuelle tilkoblede frister ændres.

Vi skal kunne ændre frister og opgaver, samt have en "fuldførte" "kolonne" nedenunder de manglende
- Frister og opgaver skal kunne tilkobles informationer. 

Vi skal kunne fjerne dokumenter og bryllupper

---

## Opsummering

Projektet går fremad, og vi har i dag fået lavet rigtig meget på ret kort tid. Vi har igen sammenholdt vores kodeagenters resultater og er blevet enige om hvis vi tog. Endvidere var det fedt at få AI-integrationen op at køre, eftersom det er det helt store ved dette valgfag. Der mangler nogle tweaks og tests, især efter vi har modtaget dokumenter fra J og MM.

## ekstra

da vi lavede .ignore og .env har vi brugt sammen oplysninger men hver vores openAI api key 


## Møde

- Vi havde idag 9:30 møde med lise og mette hvor vi fik mulighed for at stille spørgsmål angående deres problemstillinger 

Der blev snakket lidt om julemarked - lager - admin 

Vores del vi arbejder med er admin 

Vi startede med at høre Lise angående julemarked og jeg syntes jeg fik lov at mærke hvad min uddannelse har lært mig, man fik straks ideer til hvordan man kunne løse flere af hendes problemer via kode 

Vi fik snakket lidt om admin siden man umiddelbart i forhold til vores projekt var der ikke noget nyt vi som sådan skulle forholde os til  - så vi har tænkt os at fortsætte med det vi havde planlagt. - derudover stod Johan for mange af de svar vi skulle have og han var desværre ikke til stede 

Vores AI projekt/side vi laver til dem er endeligt også en erstatning for deres trello - så det er et større projekt der skal snakke sammen med flere teknologier - så jeg tvivler på vi når i mål med at implementere alt det vi ville til semester afslutning - men vi starter og så ser vi ellers hvor langt vi når. 


## MCP 

Vi snakkede derefter om MCP 
 
- MCP står for Model Context Protocol. Det er en åben standard skabt af virksomheden Anthropic, som gør det muligt for AI-modeller at snakke direkte med dine interne systemer, databaser og værktøjer

Det er en slags REST protokol - man skal kunne tilgå en server et eller andet sted 

Kodeagenter kan interagere med andre platforme 
 Uden MCP kender AI promoten men med mcp via port nummer eller ip kan den connecte med server for ekstra context og actions 

Serveren retunere strukturet data fx vi json som kodeagenten kan læse 

Man kan forbinde ting på sin lokale computer 

*** Hvordan gør man ? *** 

Der blev givet et Figma eksempel med det

Vi laver en MCP server i intelij og laver en jar fil 