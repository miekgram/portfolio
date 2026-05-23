---
title: Projektbeskrivelse
categories: ["project, sparring"]
tags: ["Project"]
date: 2026-05-11
draft: false
featureimage: ""
authors:
  - rikke/Mie
---

# Projektets beskrivelse V1:

**Projektets arbejdstitel: Ny-samlet platform for bryllup/organisering \+ reminder**

**Problem:**  
*Hvilket konkret problem løser vi?*  
Vi har til sinde at løse problemet med overskuelighed, overblik og informationsdeling. På nuværende tidspunkt skal J manuelt skrive oplysninger ind fra forskellige steder, og holde dette opdateret alle steder. Det er vores mål at sammensætte en applikation der har det store overblik som kan samarbejde med eksterne programmer, såsom deres mailsystem og i fremtiden e-conomic. Eventuelt inkorporerer en drag and drop løsning, hvor AI’en læser informationerne fra enten en e-mail eller en kontrakt og placerer oplysningerne korrekt i de forskellige mapper. 

Endvidere vil vi lave et reminder-system, som påminder i appen om opkommende frister og manglende oplysninger. 

**Bruger:**  
*Hvem er den primære bruger?*  
De primære brugere er J og Brian, men også andre ansatte såsom tjenere og kokke. 

**Nuværende proces:**  
*Hvordan foregår det i dag?*  
I dag foregår det ved at J modtager en henvendelse fra en mulig kunde (herefter brudeparret), via e-mail, ved svar, tager han en skabelon manuelt (copy paste) fra word, og udfylder med de oplysninger han har, eventuelt går han via e-conomics for at lave en tilbudsliste, og indsætter dette, samt vedhæfter han de generelle betingelser til brudeparret. Når der er en kontrakt på plads, opretter han en ny trello ved hjælp af copy paste af en skabelon og manuel udfyldning. Her bruger J meget tid på at udfylde oplysningerne, der bliver brugt farvekodning for at se hvad der er gjort og ikke gjort. Der kan endvidere opstå problemer ved sommerhus booking, da dette bliver glemt, fordi det ligger i et andet trello. J er eneste punkt for kunden, hvilket det skal forblive, men processen bag må gerne gå fremad, og lige nu er det afhængigt af ham. Der er endvidere frister for oplysninger, som først kommer senere ind, men de frister har J vist i hovedet. 

Email → word → e-conomic → tilbud → kontrakt → trello 

**Foreslået løsning:**  
*Hvad bygger vi?*

- Standalone program med oversigt over alle bryllupper i form af noget lignende et bullet board. Med oversigt over opgaver og frister, farvekodet.   
- Reminder System  
- Samlet information der automatisk opdaterer forskellige steder

Vores løsning er en prototype, som ikke har løsninger til alle problemerne, men blot det minimale til at vise kunden (EG). Vi vil bygge et stand alone program som kan tage de oplysninger J får fra brudeparret, og fordele dem til de korrekte oplysninger og arbejdsopgaver, samt lave et overblik system der er mere brugervenligt end trello i forhold til fordeling af oplysninger og oversigt. Vi vil endvidere inkorporere et reminder-system, som kan sortere ud fra manglende oplysninger, og hvornår disse senest skal indhentes og hvilke opgaver der mangler at blive løst til en frist.  \- Dette skal både give overskud og mere klarhed og bedre navigation i systemet.

**AI-funktion:**  
*Hvad bruger vi AI til?*  
Vi vil benytte AI i programmet til at fordele de informationer som enten brudeparret eller J kommer med. Derudover vil vi også bruge det til reminder-systemet, så dette sker automatisk, eventuelt med et forslag til fremgang af løsningen til fristens opgave.

**MVP:**  
*Hvad er den mindste version, vi kan demonstrere?*

- Som minimum en frontend \- hvor vi senere kan koble mere funktionalitet på  
- En AI som kan modtage oplysninger og placere dem i den rigtige mappe

**Afgrænsning:**  
*Hvad bygger vi ikke?*  
På baggrund af tidsmangel vil vi til start ikke inkorporere E-conomic API, eller et mail system derinde fra.  
Endvidere vil vi heller ikke tilføje mulighed for oversigt af booking for sommerhuse, på nuværende tidspunkt. Men dette vil være oplagt, så virksomheden kan slippe for trello, men muligvis havde et system der taler sammen, så de slipper for "forhåndsbookinger" der aldrig bliver opdateret.

**Kundespørgsmål:**  
*Hvilke svar mangler vi?*  
Vi kunne godt bruge nogle skabeloner for de forskellige steps, såsom tilbuddet, e-conomics liste, trello skabelonen og eksempel på kontrakt, eventuelt også en tillægskontrakt.

Det kunne også være yderst hjælpsomt med en tidslinje over de forskellige oplysninger og kontakt, f.eks.

- 9 måneder inden: første kontakt med par og angivelse af tilbud  
- uge efter dette: kontrakt underskrevet  
- samme dag, trello oprettes og depositum betaling modtages  
- 5 måneder inden: flere oplysninger modtages  
- 1 måned inden: endelig optælling af gæster?  
- 1 uge inden: bordplan

Til slut kunne vi også have behov for en oversigt af deres farvekoder, så vi kan genbruge disse farver.

**Antagelser:**  
*Hvad antager vi indtil videre?*  
Da vi på nuværende tidspunkt ikke har skabeloner eller kontrakt eksempler, laver vi en  informationsliste med antagelser af oplysninger de typisk bruger. Vi bruger endvidere farver og opgaver ud fra hvad vi antager de har.  
**Techstack:**  
*Frontend:*  
React

*Backend:*   
Java  
JavaLin  
Docker

*Database:*  
PostgreSQL

*Andet:*  
Trello  
Mail

**Næste tre opgaver:**  
1\. Færdiggøre beskrivelsen.  
2\. Lave en “tegning” over hvordan systemerne snakker sammen.  
3\. Formulerer en prompt til kodeagent. 

# ChatGPT prompt

## Den information vi gav chatGPT så den kunne lave en prompt

Vi skal have en prompt til codex og cursor, vi kan give en kode agent ud fra dette, kan du så lave prompten:

Vi skal lave et webbaseret program sammen. Det her er vores techstack, det kan være vi mangler noget, men det her vil vi gerne bruge:  
React, Java, JavaLin, Docker, PostgreSQL.   
Vi har denne projekt beskrivelse:  
Problem vi vil løse: Vi har til sinde at løse problemet med overskuelighed, overblik og informationsdeling. På nuværende tidspunkt skal J manuelt skrive oplysninger ind fra forskellige steder, og holde dette opdateret alle steder.. Eventuelt inkorporerer en drag and drop løsning, hvor AI’en læser informationerne fra enten en e-mail eller en kontrakt og placerer oplysningerne korrekt i de forskellige mapper. 

Endvidere vil vi lave et reminder-system, som påminder i appen om opkommende frister og manglende oplysninger. 

Dette er den nuværende proces som vi selvfølgelig gerne vil automatisere:   
I dag foregår det ved at J modtager en henvendelse fra en mulig kunde (herefter brudeparret), via e-mail, ved svar, tager han en skabelon manuelt (copy paste) fra word, og udfylder med de oplysninger han har, eventuelt går han via e-conomics for at lave en tilbudsliste, og indsætter dette, samt vedhæfter han de generelle betingelser til brudeparret. Når der er en kontrakt på plads, opretter han en ny trello ved hjælp af copy paste af en skabelon og manuel udfyldning. Her bruger J meget tid på at udfylde oplysningerne, der bliver brugt farvekodning for at se hvad der er gjort og ikke gjort. Der kan endvidere opstå problemer ved sommerhus booking, da dette bliver glemt, fordi det ligger i et andet trello. J er eneste punkt for kunden, hvilket det skal forblive, men processen bag må gerne gå fremad, og lige nu er det afhængigt af ham. Der er endvidere frister for oplysninger, som først kommer senere ind, men de frister har J vist i hovedet. 

Det her er hvad vi konkret foreslår: 

- Standalone program med oversigt over alle bryllupper i form af noget lignende et bullet board. Med oversigt over opgaver og frister, farvekodet.   
- Reminder System  
- Samlet information der automatisk opdaterer forskellige steder

Vi vil bygge et stand alone program som kan tage de oplysninger J får fra brudeparret, og fordele dem til de korrekte oplysninger og arbejdsopgaver, samt lave et overblik system der er mere brugervenligt end trello i forhold til fordeling af oplysninger og oversigt. Vi vil endvidere inkorporere et reminder-system, som kan sortere ud fra manglende oplysninger, og hvornår disse senest skal indhentes og hvilke opgaver der mangler at blive løst til en frist.  \- Dette skal både give overskud og mere klarhed og bedre navigation i systemet.

Vi vil på nuværende tidspunkt ikke inkorporerere noget med e-conomics, men det skal være en mulighed senere.

vi vil i vores projekt gerne have AI ind over. vores tanke er at AI skal kunne læse kontrakter og ud fra oplysninger opdele information i “mapper” ude i siden at vores hjemmeside/applikation så man som admin nemt at danne sig et overblik i stedet for at man skal ind og læse hele kontrakten igennem for fx. bare at finde antal gæster eller hvilken velkomstdrink der skal være og den skal kunne sammenligne datoer med almene frister og dermed give besked når der er en frist der er opkommende.

Udseende: Vi vil gerne have at hjemmesiden bruger farverne fra [https://www.engestofte.com/](https://www.engestofte.com/), den skal endvidere også fungere på mobilskærme. Der skal være et dashboard med alle bryllupper i kronologisk rækkefølge. Hvor der skal være for hvert bryllup være dato, brudeparrets navne, opgaver med farvekoder (ikke uddybende beskrivelser bare farvekoder for dem der har uløste opgaver) og frister med samme farvekoder. Endvidere skal man kunne trykke på det enkelte bryllup og komme ind på en page med deres oplysninger, hvor der i venstre side er en “pillar” med titlerne “kontrakter”, oplysninger, opgaver, frister, ansatte etc. Hvor der under hver page er underside med de forskellige ting til deres respektive titler.  
Man skal kunne drag and droppe tillægskontrakter eller nye oplysninger under hvert bryllup som så bliver automatisk fordelt i brylluppet. 

Man skal endvidere kunne oprette et nyt bryllup og drag and droppe oplysninger/pdf’er med tilbud og/eller kontrakt.   

det skal være en brugervenlig side og den skal være nem og overskuelig at navigere i.

## Den prompt vi fik tilbage

Du er en senior full-stack kodeagent. Byg et webbaseret standalone program til administration af bryllupper for Engestofte.

Tech stack:  
\- Frontend: React  
\- Backend: Java med Javalin  
\- Database: PostgreSQL  
\- Deployment/dev: Docker og Docker Compose  
\- AI-funktionalitet skal designes modulært, så den kan kobles på dokumentanalyse senere  
\- OpenAI API

Projektets formål:  
Systemet skal erstatte en manuel proces, hvor J i dag modtager kundehenvendelser, udfylder skabeloner, opretter Trello-kort, holder styr på frister og manuelt flytter information mellem forskellige steder. Programmet skal give overblik, automatisere informationsdeling og gøre det nemt at se manglende oplysninger, opgaver og deadlines.

Kernefunktioner:  
1\. Dashboard  
\- Vis alle bryllupper i kronologisk rækkefølge.  
\- Hvert bryllupskort skal vise:  
  \- Bryllupsdato  
  \- Brudeparrets navne  
  \- Status på opgaver via farvekoder  
  \- Status på frister via farvekoder  
\- Dashboardet skal være overskueligt og responsivt, også på mobil.

2\. Bryllupsdetaljeside  
Når man klikker på et bryllup, skal man komme til en detaljeret side.  
Venstre side skal have en sidebar/pillar med sektioner:  
\- Kontrakter  
\- Oplysninger  
\- Opgaver  
\- Frister  
\- Ansatte  
\- Dokumenter/noter

Hver sektion skal have sin egen underside/visning.

3\. Oprettelse af nyt bryllup  
\- Admin skal kunne oprette et nyt bryllup manuelt.  
\- Admin skal kunne drag-and-droppe PDF’er, tilbud, kontrakter eller andre dokumenter ved oprettelse.  
\- Dokumenterne skal gemmes og knyttes til brylluppet.

4\. Drag and drop på eksisterende bryllup  
\- På et eksisterende bryllup skal admin kunne uploade/drag-and-droppe tillægskontrakter eller nye oplysninger.  
\- Systemet skal være forberedt på, at AI senere kan læse dokumentet og fordele information til de rigtige felter/mapper.

5\. Reminder-system  
\- Systemet skal kunne vise kommende frister.  
\- Systemet skal kunne vise manglende oplysninger.  
\- Frister og opgaver skal have farvekoder:  
  \- Grøn: afsluttet/alt ok  
  \- Gul: nærmer sig deadline  
  \- Rød: mangler/overskredet deadline  
\- Reminders skal vises inde i appen.

6\. AI-design  
Implementér ikke nødvendigvis fuld AI-integration med ekstern API endnu, men lav arkitekturen klar til det.  
Der skal være en service/klasse til dokumentanalyse, fx \`AiDocumentAnalyzerService\`, som senere kan:  
\- Læse kontrakter  
\- Ekstrahere information som:  
  \- Antal gæster  
  \- Dato  
  \- Brudeparrets navne  
  \- Velkomstdrink  
  \- Praktiske aftaler  
  \- Frister  
  \- Manglende oplysninger  
\- Placere information i de rigtige sektioner på bryllupssiden.  
Lav gerne mock-funktionalitet, hvor uploadede dokumenter simulerer udtræk af data.

7\. Datamodel  
Lav PostgreSQL-tabeller/entities for minimum:  
\- weddings  
\- couples  
\- tasks  
\- deadlines  
\- documents  
\- extracted\_information  
\- employees  
\- wedding\_employees

8\. Backend  
Byg REST API med Java og Javalin.  
Endpoints skal som minimum understøtte:  
\- CRUD for bryllupper  
\- CRUD for opgaver  
\- CRUD for frister  
\- Upload af dokumenter  
\- Hent dokumenter for et bryllup  
\- Mock AI-analyse af uploadet dokument  
\- Hent dashboard-data samlet

9\. Frontend  
Byg React-app med:  
\- Dashboard  
\- Bryllupsdetaljeside  
\- Sidebar navigation  
\- Upload/drag-and-drop komponent  
\- Formular til nyt bryllup  
\- Opgave- og fristvisning  
\- Farvekodede statusindikatorer  
\- Responsivt design

10\. Design  
Brug farver og visuel stil inspireret af https://www.engestofte.com/  
Designet skal være:  
\- Elegant  
\- Roligt  
\- Brugervenligt  
\- Overskueligt  
\- Mobilvenligt  
\- Let at navigere i

11\. Docker  
Lav Docker Compose setup med:  
\- Frontend  
\- Backend  
\- PostgreSQL database

12\. Kvalitet  
Skriv kode som er:  
\- Modulær  
\- Let at udvide  
\- Tydeligt navngivet  
\- Kommenteret hvor det giver mening  
\- Klar til senere integration med e-conomics, men e-conomics skal ikke implementeres nu

Start med at oprette projektstrukturen, database schema/migrations, backend API og frontend sider. Prioritér en fungerende MVP frem for perfekt styling.

## Prompt resultat:

I forhold til mangler til Rikkes prøvede jeg at ændre nogle af tingene, men jeg er vist ikke klar nok i sproget, fordi oplysninger bliver stadig ikke pæne.

*Vi fortsætter med Mies prompt resultat.*  
**Ting der skal ordnes:**

- github repo  
- database på PGadmin  
- Vi skal have sat nogle faste datoer for frister.  
  - Når man laver et nyt bryllup oprettes der ikke frister. Vi skal lave en liste af frister/opgaver som automatisk skal oprettes. J skal kunne administrere denne “skabelon”... Tidslinje  
- AI skal sættes op \- så den automatisk kan læse dokumenter  
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
