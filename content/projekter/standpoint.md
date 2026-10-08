---
title: "Standpoint – en samlet platform til Susan Gram"
weight: 20
summary: "En platform til Susan Gram, der samler hjemmeside, ansøgninger og administration. Bygget med React, .NET og Supabase og stadig under udvikling."
cardTitle: Standpoint
cardDescription: "En samlet platform til Susan Gram med hjemmeside, ansøgninger og administration. Målet er at give hende ejerskab over sin digitale løsning og gøre hverdagen lettere."
category: "Fullstack-udvikling"
technologies: [React, ".NET 10", Supabase, Azure]
website: "https://jolly-glacier-0e7d98d03.6.azurestaticapps.net/kontakt"
previewBrand: standpoint
previewSubtitle: "Overblik & nye muligheder"
previewLabel: "FRA IDÉ TIL PLATFORM"
previewHeading: "Mere nærvær. Bedre overblik."
previewAction: "Tag det næste skridt ↗"
previewCaption: "Website & administration · Under udvikling"
previewStyle: standpoint
showDate: false
showAuthor: false
showReadingTime: false
showWordCount: false
showPagination: false
---

Jeg arbejder på **Standpoint til Susan Gram**: en samlet platform, der skal erstatte hendes nuværende Simplero-løsning. Målet er at give hende ejerskab over sin digitale løsning og samle hjemmeside, ansøgninger, kalender og mails, så hun kan bruge mere tid på menneskerne og mindre tid på administration.

### Sådan er den bygget

Frontend er bygget med **React 18, JavaScript, Vite og React Router**. Jeg bruger egen CSS med mosgrønne, gyldne og lyse nuancer for at skabe et roligt og sammenhængende udtryk. Den offentlige hjemmeside og admin-panelet ligger i samme applikation, som er deployet på **Azure Static Web Apps**.

**Supabase** håndterer PostgreSQL-databasen og login via magic links. Admin-panelet giver overblik over ansøgninger og en kalender, hvor arrangementer kan oprettes og redigeres. Adgangen til data styres med regler i databasen, så administrationen er begrænset til godkendte brugere.

Backend er bygget separat i **ASP.NET Core / .NET 10** og integrerer med Supabase og **Resend** til mails om ansøgningsstatus og kalenderændringer. Opdelingen giver plads til senere at tilføje betaling og mere komplekse arbejdsgange. Frontend og backend ligger i hver sit repository, og ændringer føres ind via pull requests til `main`.

### Hvor langt er projektet?

Hjemmesiden og den første version af admin-panelet er bygget, og ansøgninger, kalender og login er koblet til Supabase. Mailservicen er implementeret, men udsendelse i produktion afventer domæneverifikation, og deployment af backend mangler stadig. Betaling med Stripe og kursuslevering er planlagt til senere.

Det spændende ved projektet er at forbinde en brugervenlig hjemmeside med de arbejdsgange, der ligger bag. Jeg arbejder både med den visuelle oplevelse og med at få data, adgang og automatisering til at hænge sammen.

[Besøg Standpoint →](https://jolly-glacier-0e7d98d03.6.azurestaticapps.net/kontakt)
