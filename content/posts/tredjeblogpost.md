---
title: "Undervisning 3 – Automatisk sync mellem portfolio og Dify"
date: 2026-04-20
draft: false
summary: "Automatisering af portfolio så Dify-chatbotten automatisk opdateres via Java, sitemap, Jina Reader og Dify API"
---

I denne undervisning arbejdede vi videre med vores portfolio, men denne gang med fokus på **automatisering**.

Målet var at lave en løsning, hvor vores **Dify-chatbot** automatisk bliver opdateret med nyt indhold fra vores portfolio, hver gang vi kører vores Java-program. På den måde slipper vi for manuelt at uploade sider én efter én, og chatbotten kan hele tiden arbejde med det nyeste indhold.

---

## Overblik over systemet

![System arkitektur](/images/diagram1.png)

Systemet fungerer sådan her:

- Java henter alle links fra `sitemap.xml`
- hver side bliver sendt til **Jina Reader**
- siden bliver konverteret til **Markdown**
- Markdown bliver sendt videre til **Dify Knowledge Base**
- Dify bruger derefter indholdet sammen med **LLM og embeddings**

Det betyder, at hele flowet fra website til chatbot bliver automatiseret.

---

## Det vi lavede

Vi lavede et Java-program, som kan:

- læse alle sider fra vores portfolio
- hente indholdet automatisk via sitemap
- konvertere siderne til Markdown
- oprette eller opdatere dokumenter i Dify
- synkronisere eksisterende indhold automatisk

Det gør, at chatbotten altid er opdateret med vores nyeste portfolio-indhold, uden at vi skal gøre det manuelt.

---

## Fokus på automatisering

Det vigtigste i denne opgave var ikke bare at hente data, men at få systemet til at arbejde **automatisk**.

Programmet finder selv:

- hvilket dataset der skal bruges i Dify
- hvilke sider der findes i vores sitemap
- hvilke dokumenter der allerede ligger i Dify
- om et dokument skal **oprettes** eller **opdateres**

På den måde bliver løsningen mere robust og mere brugbar i praksis.

---

## Eksempel på main-klassen

Main-klassen er det sted, hvor programmet starter. Her bliver miljøvariabler læst ind, og selve synkroniseringen bliver sat i gang.

```java
package app;

public class Main {
    public static void main(String[] args) throws Exception {
        String sitemapUrl = args.length > 0 ? args[0] : System.getenv("SITEMAP_URL");
        String difyApiKey = System.getenv("DIFY_API_KEY");

        if (sitemapUrl == null || difyApiKey == null) {
            System.err.println("""
                Mangler konfiguration. Sæt følgende:
                  export DIFY_API_KEY=din-nøgle
                  java -jar sitemap-to-dify.jar https://dit-website.dk/sitemap.xml
                """);
            System.exit(1);
        }

        new SitemapToDify(difyApiKey).runSync(sitemapUrl);
    }
}
```
---

## Mine tanker

Jeg syntes, det har været lidt svært og nyt det her med at prompte AI til den kode, man gerne vil have. Man skal lige tænke sig en ekstra gang om, hvad det egentlig er, man vil have – man skal have tungen lige i munden.

Det tog også to forsøg for mig. Min første prompt var ikke så fyldestgørende, men efterfølgende, da jeg fik uddybet den, spyttede AI noget kode ud, hvor man egentlig bare skulle indsætte de to klasser og køre det.

Jeg synes, det er meget interessant, hvor hurtigt det kan gå, og hvor hurtigt man kan få stablet noget kode på benene, som faktisk virker. Men det kan også være lidt farligt, fordi man hurtigt kan indsætte noget kode, som virker, uden rigtig at have kigget på det eller forstået, hvorfor det virker.

Så selvom det er et rigtig godt redskab, er det vigtigt, at man stadig har sine kritiske briller på.


