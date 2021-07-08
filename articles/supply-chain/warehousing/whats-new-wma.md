---
title: Vad är nytt eller ändrat i mobilappen Warehouse Management
description: Det här ämnet visar en lista med nya och ändrade funktioner för varje frisläppt version av mobilappen Warehouse Management för Microsoft Dynamics 365 Supply Chain Management.
author: ivanv-microsoft
ms.date: 06/07/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: ivanv
ms.search.validFrom: 2021-06-07
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: 61124728942c0b8162de9f687ae752773c47d07e
ms.sourcegitcommit: 4cbd83e21a78459e4711a2dedba0f5a7acc3c841
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/15/2021
ms.locfileid: "6261800"
---
# <a name="whats-new-or-changed-in-the-warehouse-management-mobile-app"></a>Vad är nytt eller ändrat i mobilappen Warehouse Management

[!include [banner](../includes/banner.md)]

Detta ämne listar nya funktioner, korrigeringar, förbättringar och kända problem för varje släppt version av mobilappen Warehouse Management för Microsoft Dynamics 365 Supply Chain Management.

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
