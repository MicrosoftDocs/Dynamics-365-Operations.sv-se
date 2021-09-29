---
title: Vad är nytt eller ändrat i mobilappen Warehouse Management
description: Det här ämnet visar en lista med nya och ändrade funktioner för varje frisläppt version av mobilappen Warehouse Management för Microsoft Dynamics 365 Supply Chain Management.
author: MarkusFogelberg
ms.date: 09/09/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mafoge
ms.search.validFrom: 2021-06-07
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: ac3ea6a088b2086054eb692cd0688b269dafca51
ms.sourcegitcommit: e7eeca05d738e9e46d6185d1ba349836ebafc1a4
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/09/2021
ms.locfileid: "7485632"
---
# <a name="whats-new-or-changed-in-the-warehouse-management-mobile-app"></a>Vad är nytt eller ändrat i mobilappen Warehouse Management

[!include [banner](../includes/banner.md)]

Detta ämne listar nya funktioner, korrigeringar, förbättringar och kända problem för varje släppt version av mobilappen Warehouse Management för Microsoft Dynamics 365 Supply Chain Management.

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
- Korrigerade ett problem som genererade följande felmeddelande på vissa enheter: "Det går inte att hitta någon lämplig vy för den angivna storleken."
- Korrigerade ett problem där läget för helskärm inte alltid fungerar när tangentbordet på skärmen används.
- Korrigerade ett problem där sidsepandet inte fungerade på Windows-enheter.
- Åtgärdade olika problem som gjorde att systemet inte svarade har lösts.

## <a name="version-2070"></a>Version 2.0.7.0

### <a name="new-features-fixes-and-improvements-in-version-2070"></a>Nya funktioner, korrigeringar och förbättringar i version 2.0.7.0

- Har lagt till ett avsnitt på sidan **Om** där den senast släppta versionen av appen kontrolleras.
- Gör det enklare att snärta och svepa mellan sidor.
- Ändrade ikonen för knappen stigande/fallande i arbetslistan.
- Minskade marginalerna på kortet **Information** för mer plats för information.
- Tillämpat olika prestandaförbättringar för att minska problemet med att appen blir långsammare med tiden.
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
