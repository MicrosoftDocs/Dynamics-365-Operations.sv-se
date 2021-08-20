---
title: Kompensation Power BI-innehåll
description: Det här avsnittet beskriver kompensation Power BI-innehållet. Här förklaras hur du kommer åt rapporterna och ger information om den använda datamodellen.
author: jcart1106
ms.date: 12/19/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HcmCompensationWorkspace
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.openlocfilehash: 549111dab1b6d3b66567801ae787a680a04b18e20e286e1a59d1ab388bf2a4f7
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6763606"
---
# <a name="compensation-power-bi-content"></a>Kompensation Power BI-innehåll

[!include [banner](../includes/banner.md)]

Det här avsnittet beskriver **kompensation** Microsoft Power BI-innehållet. Det förklarar hur du öppnar rapporter, och ger information om den datamodell och de enheter som användes för att skapa innehållet.

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


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]