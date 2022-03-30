---
title: Vad är nytt eller ändrat i mobilappen Warehouse Management
description: Det här ämnet visar en lista med nya och ändrade funktioner för varje frisläppt version av mobilappen Warehouse Management för Microsoft Dynamics 365 Supply Chain Management.
author: Mirzaab
ms.date: 03/11/2022
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2021-06-07
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: c4731c5f0b0a1553deb53753d82d29a34e5525df
ms.sourcegitcommit: 399d0d3f8e2ebb81b6b9d640365ebe182690bab2
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/15/2022
ms.locfileid: "8418650"
---
# <a name="whats-new-or-changed-in-the-warehouse-management-mobile-app"></a>Vad är nytt eller ändrat i mobilappen Warehouse Management

[!include [banner](../includes/banner.md)]

Detta ämne listar nya funktioner, korrigeringar, förbättringar och kända problem för varje släppt version av mobilappen Warehouse Management för Microsoft Dynamics 365 Supply Chain Management.

## <a name="version-20190"></a>Version 2.0.19.0

I den här versionen ingår följande nya funktioner, korrigeringar och förbättringar:

- Förbättrade det allmänna flödet för dataförfrågan.
- Förbättrade darrningsproblemet på sidorna **Arbetslista** och **Artikelförfrågan**.
- Sänkt batteriförbrukning.
- Tog bort gränsen för antalet fält för arbetskort.
- Justerade höjden på arbetskort så att alla har samma storlek, oavsett antal fält i varje.
- Åtgärdade ett problem där blanksteg i streckkoder rensades.
- Lade till inställningen **Knappstil**, som gör att du kan växla mellan att visa skjutreglaget och visa knappar på alla typer av enheter.
- Åtgärdade olika problem som fick appen att krascha.
- Ange fokus automatiskt på den första textrutan på anpassade sidor.
- Hjälpmedelsförbättringar relaterade till ljusstyrka, kontrast, berättande och platshållartexter som saknas.

## <a name="version-20170"></a>Version 2.0.17.0

I den här versionen ingår följande nya funktioner, korrigeringar och förbättringar:

- Åtgärdade ett problem där streckkoder skannades felaktigt.
- Åtgärdade ett GS1-skanningsproblem för skannern.
- Åtgärdade GS1-skanningsproblemet för streckkodsskannern på Zebra-enheter.
- Förbättrade flödet för omvägsförfrågan så att valet av ett kort under en omväg nu medför en återgång till huvudflödet.
- Lade till stöd för ett allmänt dataförfrågningsflöde.
- Lade till ett meddelande om ändringar av nätverkets anslutningsstatus för användarna.
- Anpassa lagringsbehörigheter till sekretesspolicyn för lagring i Android 10.
- För flöden som behöver det inkluderar kvantitetsförloppsrutan nu en position där användare skickar ett tomt numeriskt värde.
- Åtgärdade problem med kvantitetsförloppsorientering.
- Åtgärdade ett problem där kvantitetsförloppet kunde hoppa till fel värde.
- Åtgärdade ett problem där inmatning till den primära sidan gick förlorad när den fylls i från detaljsidan.
- Åtgärdade ett problem där platshållartexten behandlades som det inledningsvis valda värdet i urvalslistor.
- Knappen "Skicka" på bekräftelsesteg aktiveras nu automatiskt om det finns förvalda värden.
- Åtgärdade detaljkortet så att så många rader som möjligt för textfält med flera rader visas.
- Åtgärdade höjden på knapparna "Skicka" och "Fler åtgärder", så nu tar de mindre plats på skärmen.
- Lade till rubriker på saknade vallistor.
- Åtgärdade ett problem där bakåtknappen inte fungerade.
- Lade till flera korrigeringar och förbättringar för tangentbordsnavigering, bland annat på följande sidor:
  - Användarinloggning
  - Välj anslutning
  - Redigera anslutning
- Fast rullning när du använder tangentbordsnavigering.
- Förbättrad åtkomst, inklusive följande förbättringar:
  - Fast färgsynbarhet och kontrast.
  - Förhindrad förlust av tangentbordsfokus när popup-sidor stängs.
  - Lade till felmeddelanden i berättandet.
  - Ökade storleken på platshållarvärdena i stegbanderollen.
- Åtgärdade exemplet på den anpassade äldre sidan i demoläge.

## <a name="version-20150"></a>Version 2.0.15.0

I den här versionen ingår följande nya funktioner, korrigeringar och förbättringar:

- Förbättrad prestanda genom korrigering av ett problem med minnesproblem.
- Åtgärdade ett problem där vissa fältvärden inte uppdaterades korrekt när de markerades på detaljsidan.

## <a name="version-20140"></a>Version 2.0.14.0

I den här versionen ingår följande nya funktioner, korrigeringar och förbättringar:

- Åtgärdade ett problem som inaktiverade knappen Skicka.

## <a name="version-20130"></a>Version 2.0.13.0

I den här versionen ingår följande nya funktioner, korrigeringar och förbättringar:

- Förbättrad bläddring mellan sidor med smidigare animering.
- Fasta ologiska svar på sveprörelser och enstaka skärmfrysningar.
- Förbättrad kombination av mörklägestext och bakgrundsfärg för bättre läsbarhet.
- Åtgärdade ett problem där viss text kan bli mycket liten när du ändra storlek på appfönstret.
- Åtgärdade ett problem som kan göra att programmet kraschar när streckkoder skannas.
- Har lagt till möjligheten att ersätta ett skjutreglage med en knapp.
- Åtgärdade ett problem som kan göra att programmet visar felmeddelandet, "AADSTS7000215: Ogiltig klienthemlighet anges."
- Har fast tipsanimeringen som visar hur du stänger en sida med ett svepa nedåt-gest.
- Lade till möjligheten att stänga en sida med hjälp av en snärt nedåt.
- Har åtgärdat ett problem där listruterubriker inte visas på sidan **Användarinställningar**.
- Åtgärdade ett lokaliseringsproblem där programmet inte identifierar ett komma (,) som en decimalavgränsare.
- Förbättrad tillgänglighet.
- Har fast navigeringen på sidan **Ny anslutning** för att ge förbättrad åtkomst.
- Har åtgärdat ett problem där det mjuka tangentbordet (på skärmen) inte visas när du väljer ett inmatningsfält.
- Fast ett problem som kan kraschar programmet om användarna snabbt ändrar storlek på dess fönster.
- Fast en fråga där en snabbtangent ibland tolkas som ett långt tryck.
- Har åtgärdat ett problem där applayouten kan bli skadad på grund av fältanpassningar som gjorts i Supply Chain Management.
- Fast ett problem där artikelplatserna inte visas korrekt.
- Har åtgärdat ett problem vid kort plockning av produktvariantarbetsflödet.
- Den onödiga valideringen av fält som innehåller förinställda standardvärden har tagits bort.
- Förbättrad prestanda.
- En ny inställning har lagts till där användarna kan välja hur fält filtreras och beställs på kortsidan.

## <a name="version-20110"></a>Version 2.0.11.0

I den här versionen ingår följande nya funktioner, korrigeringar och förbättringar:

- Stöd för uppsagda fält har lagts till.
- Stöd för tangentbordsnavigering för maskinvara.
- Förbättrad tillgänglighet.
- Kort med förbättrad detalj.
- Förbättrade omvägar för menyalternativsteg.
- Mindre förbättringar av användargränssnitt.
- Åtgärdade ett problem som kunde göra att programmet kraschar när streckkoder skannades.
- Åtgärdade olika problem som gjorde att systemet inte svarade har lösts.

## <a name="version-20100"></a>Version 2.0.10.0

I den här versionen ingår följande nya funktioner, korrigeringar och förbättringar:

- Lade till animering när du sveper genom listor och sidor.
- Text som nu radbryts korrekt på anslutningsfelsidan.
- Kombinationsrutor utan standardvärden visas nu korrekt.
- Informationen i underrubriksområdet visas nu bara på den fullständiga detaljsidan.
- Tomma inmatningsfält visas inte längre på detaljkortet.
- Bekräftelsevärden dupliceras inte längre på informationskortet.
- Åtgärdade olika problem som gjorde att systemet inte svarade har lösts.

## <a name="version-2090"></a>Version 2.0.9.0

Denna version korrigerar ett problem där programmet kan sluta svara om användarna rullar uppåt från överst i en lista.

## <a name="version-2080"></a>Version 2.0.8.0

I den här versionen ingår följande nya funktioner, korrigeringar och förbättringar:

- Lade till stöd för den [steginstruktionsfunktionen](mobile-app-titles-instructions.md) som lagts till i version 10.0.21 av Supply Chain Management.
- Lade till tipsanimering för att visa användare att de kan stänga överlägg genom att svepa nedåt.
- Lade till stöd för funktionstangenter i åtgärdslistor och menyer. Användare kan hålla ned valfri funktionstangent i tre sekunder när de vill visa en lista över tillgängliga kommandon.
- Åtgärdade ett problem som genererade följande felmeddelande på vissa enheter: "Det går inte att hitta någon lämplig vy för den angivna storleken."
- Åtgärdade ett problem där läget för helskärm inte alltid fungerar när tangentbordet på skärmen används.
- Åtgärdade ett problem där sidsepandet inte fungerade på Windows-enheter.
- Åtgärdade olika problem som gjorde att systemet inte svarade har lösts.

## <a name="version-2070"></a>Version 2.0.7.0

### <a name="new-features-fixes-and-improvements-in-version-2070"></a>Nya funktioner, korrigeringar och förbättringar i version 2.0.7.0

- Har lagt till ett avsnitt på sidan **Om** där den senast släppta versionen av appen kontrolleras.
- Gör det enklare att snärta och svepa mellan sidor.
- Ändrade ikonen för knappen stigande/fallande i arbetslistan.
- Minskade marginalerna på kortet **Information** för mer plats för information.
- Tillämpade olika prestandaförbättringar för att minska problemet med att appen blir långsammare med tiden.
- Om det finns fler kontroller än de som får plats på skärmen leder det till sidindelning och kontrollen rullar inte längre på samma sätt som sidan.
- Prioritera att visa det senast skannade värdet före att visa uppgiftens rubrik, så om de överlappar uppgiftsrubrikn kortas den av.
- Åtgärdade olika problem som gjorde att systemet inte svarade har lösts.
- Text på olika ställen skärs inte längre av på vissa språk.
- Appen körs nu som standard i helskärmsläge.
- Åtgärdade ett problem som medförde att skanningar ignorerades på huvudsidan för vissa enheter.

### <a name="known-issues-in-version-2070"></a>Kända problem i version 2.0.7.0

- På vissa enheter visas följande felmeddelande när du startar appen eller påbörjar en uppgift: "Det går inte att hitta någon lämplig vy för den angivna storleken." Om det här felmeddelandet visas på någon av dina enheter måste du nedgradera mobilappen Warehouse Management till version 2.0.6.0 på den enheten och vänta med uppgradering tills nästa version av appen släpps.

## <a name="version-2060"></a>Version 2.0.6.0

### <a name="new-features-fixes-and-improvements-in-version-2060"></a>Nya funktioner, korrigeringar och förbättringar i version 2.0.6.0

I den här versionen ingår följande nya funktioner, korrigeringar och förbättringar:

- I demoläget visas nu alla etiketter på enhetens språk.
- Det är mindre sannolikt att du får följande felmeddelande: "Det går inte att hitta någon lämplig vy för den angivna storleken."
- Minimihöjden för arbetskort har ökat (i fall där tre eller färre fält har konfigurerats för att visas i arbetslistan).
- Marginalerna (tona ut) har förbättrats längst ner på detaljkorten.
- Ogiltiga symboler i XML-filer som utbyts med servern hanteras nu. (Tecken som inte kan skrivas ut hanteras nu för respit så att programmet inte längre slutar svara.)
- HTTP-fel (som "fel 503") när en serverbegäran skickas hanteras nu utan fel.
- Medan ett fel visas visas inte längre alternativlistan automatiskt för kombinationsrutakontroller.
- Programmet slutar inte längre svara på grund av den visningsorientering som har valts i användarinställningarna.
- Produktbilder visas nu i självbetjäningsmiljöer. (Den här ändringen gäller endast för lågupplösningsversioner. Filhanteringstjänsten har inte stöd för bilder av full storlek i självbetjäningmiljöer.)
- Ett problem som involverar korta plockningar med nollkvantitet har lösts.
- Programmet slutar inte längre att svara när ett detaljkort visar flera identiska fält.

### <a name="known-issues-in-version-2060"></a>Kända problem i version 2.0.6.0

Följande kända problem finns i den här versionen:

- Appen (särskilt arbetslistan) blir slut med tiden.
- **Windows-version:** När USB används för skanning i Windows, orsakar inkonsekventa resultat att skannade symboler blandas ihop.

## <a name="version-2050"></a>Version 2.0.5.0

I den här versionen ingår följande nya funktioner, korrigeringar och förbättringar:

- Klienthemligheten är inte längre dold i anslutningsinställningarna.
- Du kan nu länge trycka på en text för att se den helt.
- Felmeddelandet när lagringsbehörigheter saknas har förbättrats.
- Nya kontrollsekvenser har lagts till för vissa flöden.
- Knappen Skicka blir inte längre fel tillgänglig på grund av fönsterstorleken.
- Skjutreglagen kan nu fortsätta på mindre skärmar när större knappstorlekar används.
- Den fyra knappen är inte längre avklippt.
- Tangentbordet har nu stöd för knappen Radera.
- Ett problem med ett problem som kan uppstå när du använder tangentbordet har lösts in.
- Olika problem med demodata har åtgärdats.
- Ett problem som påverkas av numeriska fält på detaljsidan har åtgärdats.
- Ibland försvinner inte längre skärmtangentbordet på vissa enheter.
- Olika användargränssnitt (UI) har åtgärdats, till exempel så att det påverkade bakgrundsfärgen och positionering.
- Användargränssnittet för ryska har förbättrats.
- Olika problem som gör att systemet inte svarar har lösts.
- Ett problem som gick att öppna kalkylatorn på nytt har lösts.
- **Android version:** Ett problem som orsakade Android 4.4 att sluta svara vid start har åtgärdats.
- **Android version:** minimiskalning har reducerats till 50 procent.

## <a name="version-2040"></a>Version 2.0.4.0

Version 2.0.4.0 var den första allmänt tillgängliga versionen av mobilappen Warehouse Management.

### <a name="new-features-fixes-and-improvements-in-version-2040"></a>Nya funktioner, korrigeringar och förbättringar i version 2.0.4.0

Denna version introducerar följande nya funktioner, korrigeringar och förbättringar som inte är tillgängliga i förhandsgranskningsversionen:

- Om ett detaljkort innehåller två etiketter med identiska data är en av etiketterna dold.
- Specialtecken visas nu som standard och alternativet för att dölja dem tas bort från användarinställningarna.
- Inaktiverade skicka-knappar visas nu som inte tillgängliga im-visning.
- En ändring av ordningslogiken för kontroller ser till att skalningen blir smidigare mellan enheter. Det är därför mindre nödvändigt att justera skalningen av teckensnitt eller knappar.
- Standardfärgtemat har ändrats till *Mörk*.
- Ikonen som saknas för den inaktiverade skicka-knappen har lagts till i tittat.
- Time-out-undantag tar dig nu till anslutningssidan istället för att visa ett radfel.
- Om det inte finns någon åtgärd att skicka (till exempel **OK**, **Ja**, **Acceptera**, **Klar** eller **Avslutad**), inaktiveras knappen Skicka.
- Appens stabilitet har förbättrats.
- Det finns en korrigering för säkerhetsrisk [CVE-2021-26701](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2021-26701).
- **Windows-version:** Ett problem i Windows, där menyerna inte var svarande efter det att fönstret ändrades, har åtgärdats.

### <a name="known-issue-in-version-2040"></a>Kända problem i version 2.0.4.0

Följande kända problem finns i den här versionen:

- Den här versionen har problem med enheter som använder Android 4.4. Du kan få problem när du använder programmet i den här Android versionen.
