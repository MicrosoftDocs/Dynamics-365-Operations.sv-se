---
title: Kompensation Power BI-innehåll
description: Det här avsnittet beskriver kompensation Power BI-innehållet. Här förklaras hur du kommer åt rapporterna och ger information om den använda datamodellen.
author: jcart1106
manager: AnnBe
ms.date: 12/19/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: HcmCompensationWorkspace
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.openlocfilehash: b625ea7dcbb6bd8b80cbcdcc544c59b9839fc19d
ms.sourcegitcommit: 5192cfaedfd861faea63d8954d7bcc500608a225
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/30/2021
ms.locfileid: "5093066"
---
# <a name="compensation-power-bi-content"></a>Kompensation Power BI-innehåll

[!include [banner](../includes/banner.md)]

Det här avsnittet beskriver **Kompensation** Microsoft Power BI-innehållet. Det förklarar hur du öppnar rapporter, och ger information om den datamodell och de enheter som användes för att skapa innehållet.

## <a name="accessing-the-power-bi-content"></a>Komma åt Power BI-innehåll
Innehåll för **kompensation** Power BI visas i arbetsytan **kompensationshantering** om du använder någon av följande produkter:

- Finance and Operations-appar
- Microsoft Dynamics 365 Human Resources

## <a name="reports-that-are-included-in-the-power-bi-content"></a>Rapporter som ingår i Power BI-innehållet
Rapporter som ingår i **Kompensation** Power BI-innehållet har både diagram och tabeller med ytterligare information. Följande register beskriver rapporterna.

| Rapport                     | Innehåll |
|----------------------------|----------|
| Översikt över kompensation      | Sammanfattning av andra rapporter |
| Kompensationsanalys      | Timlön och avlönade anställda per företag, totala anställda per kompensationsplan, manliga och kvinnliga anställda per kompensationsplan och medarbetarkompensation per avdelning |
| Befattningsutbetalningsanalys      | Högsta och lägsta timlön och löneutbetalning, befattning med högsta och lägsta lön och heltids- och deltidsbefattning |
| Kompensationsplananalys | Anmälan till medarbetare efter valt förmån |

Diagrammen och rutorna i samtliga dessa rapporter kan filtreras och fästas på instrumentpanelen. Mer information om hur du filtrerar och fäster i Power BI, se [Skapa och konfigurera en instrumentpanel](https://powerbi.microsoft.com/guided-learning/powerbi-learning-4-2-create-configure-dashboards).

## <a name="understanding-the-data-model-and-entities"></a>Förstå datamodellen och enheterna
Följande data används för att fylla i rapporterna i **Kompensation** Power BI-innehållet. Denna tabell visar enheterna som innehållet baserades på.

| Enhet                   | Innehåll                                                                                                   | Relationer med andra entiteter |
|--------------------------|------------------------------------------------------------------------------------------------------------|-----------------------------------|
| Kalenderförskjutning          | Kalenderförskjutningar till uppdela rapporter                                                                          | Tidigare befattningstilldelning, befattningsutveckling, uppsagd medarbetare |
| Företag                  | Företag att filtrera rapporter efter                                                                             | Aktuell kompensation, aktuell medarbetare, uppsagd medarbetare, medarbetarutveckling |
| Kompensation             | Lönesatsen och frekvens över tiden                                                                           | Aktuell kompensation, aktuell medarbetare, uppsagd medarbetare, medarbetarutveckling |
| Aktuell kompensation     | Lönesatsen och frekvens per aktuellt datum                                                              | Företag, kompensation, demografi, jobb, befattning |
| Aktuell befattning         | Befattningar per innevarande datum, heltidslön (FTE) öppna positioner och öppna till fulla befattningar | Jobb, befattning |
| Aktuell medarbetare         | Arbetare per aktuellt datum, ålder och antal anställda                                                         | Företag, kompensation, geografisk plats, medarbetarens namn, rapporter till, medarbetarens titel, demografi, jobb, anställning, befattning, förmåner |
| Datum                     | Dagar, veckor, månader och år.                                                                             | Tidigare befattningstilldelning, befattningsutveckling, uppsagd medarbetare, medarbetarutveckling |
| Demografi             | Födelsedatum, kön, etniskt ursprung och civilstånd                                                   | Aktuell medarbetare, uppsagd, medarbetare, medarbetarutveckling |
| Anställning               | Startdatum, slutdatum och övergångsdatum                                                                  | Aktuell medarbetare, uppsagd, medarbetare, medarbetarutveckling |
| Geografisk plats      | Stad, region, postnummer och delstat eller region                                                           | Aktuell medarbetare, uppsagd, medarbetare, medarbetarutveckling |
| Jobb                      | Funktion, typ och rubrik                                                                                  | Aktuell befattning, aktuell medarbetare |
| Tidigare befattningstilldelning | Orsak för tilldelningen, startdatum, slutdatum och jobb                                                           | Kalenderförskjutning, datum, jobb, befattning |
| Befattning                 | Avdelning, FTE, befattning, befattningstyp och titel                                                        | Aktuell befattning, aktuell medarbetare |
| Befattningsutveckling           | Positioner över tid, FTE och jobb                                                                          | Kalenderförskjutning, datum, jobb, befattning |
| Rapporterar till               | Förnamn, efternamn och fullständiga namn                                                                       | Aktuell arbetare, uppsagd medarbetare, medarbetarutveckling |
| Uppsagda medarbetare      | Uppsagda medarbetare, uppsägningsdatum, titel, befattning och jobb                                           | Företag, kompensation, geografisk plats, medarbetarens namn, rapporter till, förskjutningskalender, datum, medarbetarens titel, demografi, anställning, jobb, befattning, förmåner |
| Förmåner                 | Giltighetsdatum, förmånsalternativ, förmånsplanen och förmånstyp                                             | Aktuellt namn, uppsagd medarbetare, medarbetarutveckling |
| Namn på medarbetare            | Förnamn, efternamn och fullständiga namn                                                                       | Aktuell medarbetare, uppsagd, medarbetare, medarbetarutveckling |
| Medarbetartitel           | Titel och tjänsteålder                                                                                   | Aktuell medarbetare, uppsagd, medarbetare, medarbetarutveckling |
| Medarbetarutveckling           | Arbetare över tid, antal anställda, företag och befattning                                                        | Företag, kompensation, geografisk plats, medarbetarens namn, rapporter till, förskjutningskalender, datum, medarbetarens titel, demografi, anställning, jobb, förmåner |
