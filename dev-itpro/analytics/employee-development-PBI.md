---
title: "Utveckling av medarbetare Power BI-innehåll"
description: "Det här avsnittet beskriver Power BI-innehåll för medarbetarutveckling. Det förklarar hur du öppnar rapporter, och ger information om den datamodell och de enheter som användes för att skapa innehållet."
author: jcart1106
manager: AnnBe
ms.date: 05/24/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User, IT Pro
ms.search.scope: Operations, UnifiedOperations, Talent, Core
ms.search.region: Global
ms.author: JCart
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.translationtype: Human Translation
ms.sourcegitcommit: 869151f2486b7a481e4694cfb6992d0ee2cfc008
ms.openlocfilehash: d25f3be5821a02ea618a2356878bf2904765a6f7
ms.contentlocale: sv-se
ms.lasthandoff: 06/13/2017

---

# Utveckling av medarbetare Power BI-innehåll
<a id="employee-development-power-bi-content" class="xliff"></a>

[!include[banner](../includes/banner.md)]

Det här avsnittet beskriver Power BI-innehåll för **medarbetarutveckling**. Det förklarar hur du öppnar rapporter, och ger information om den datamodell och de enheter som användes för att skapa innehållet.

## Åtkomst till Power BI-innehåll
<a id="accessing-the-power-bi-content" class="xliff"></a>

Om du använder Microsoft Dynamics 365 for Operations version 1611 eller Finance and Operations, Enterprise edition juli 2017 uppdatering hittar du Power BI-innehållspaket för **medarbetarutveckling** i Microsoft Dynamics Lifecycle Services (LCS). Mer information om hur du laddar ned innehållspaket och ansluter det till dina data finns i [Power BI-innehåll i LCS från Microsoft och dina partner](power-bi-content-microsoft-partners.md).

## Rapporter som ingår i Power BI-innehållet
<a id="reports-that-are-included-in-the-power-bi-content" class="xliff"></a>
Rapporter som ingår i Power BI-innehållspaketet **Medarbetarutveckling** har både diagram och tabeller med ytterligare information. Följande register beskriver rapporterna.

| Rapport                        | Innehåll |
|-------------------------------|----------|
| Översikt över medarbetarutveckling | Sammanfattning av andra rapporter |
| Analys över medarbetarens kompetenser       | Typer av medarbetarens kompetenser och medarbetarens kompetenser efter typ |
| Analys över medarbetarens kompetensnivå | Medarbetarens kompetensnivåer per avdelning, medarbetare per kompentensnivå och kompetenstyp och lägsta och högsta nivåerna per kompetens |
| Kompetensprofil                 | Kompetensprofil för vald medarbetare. |
| Kompetensanalys                | Kompetens efter typ och värdering |
| Resultatvärderingsanalys   | Medarbetare per lägsta och högsta värdering per jobb, medarbetarvärderingar per avdelning, medarbetare per värdering och beafattningstyp och högsta och lägsta värdering per befattning  |
| Medarbetarresultatanalys | Medarbetarvärdering för vald värdering av chef |

Diagrammen och rutorna i samtliga dessa rapporter kan filtreras och fästas på instrumentpanelen. Mer information om hur du filtrerar och fäster i Power BI finns i [Skapa och konfigurera en intrumentpanel](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-4-2-create-configure-dashboards).

## Förstå datamodellen och enheterna
<a id="understanding-the-data-model-and-entities" class="xliff"></a>
| Enhet                   | Innehåll                                                                                                   | Relationer med andra entiteter |
|--------------------------|------------------------------------------------------------------------------------------------------------|-----------------------------------|
| Kalenderförskjutning          | Kalenderförskjutningar till uppdela rapporter                                                                          | Tidigare befattningstilldelning, befattningsutveckling, uppsagd medarbetare 
| Företag                  | Företag att filtrera rapporter efter                                                                             | Aktuell medarbetare, uppsagd, medarbetare, medarbetarutveckling |
| Aktuell befattning         | Befattningar per innevarande datum, heltidslön (FTE) öppna positioner och öppna till fulla befattningar | Jobb, befattning |
| Aktuell medarbetare         | Arbetare per aktuellt datum, ålder och antal anställda                                                         | Företag, geografisk plats, medarbetarens namn, rapporter till, förskjutningskalender, datum, medarbetarens titel, demografi, jobb, anställning, befattning |
| Datum                     | Dagar, veckor, månader och år.                                                                             | Tidigare befattningstilldelning, befattningsutveckling, uppsagd medarbetare, medarbetarutveckling |
| Demografi             | Födelsedatum, kön, etniskt ursprung och civilstånd                                                   | Aktuell medarbetare, uppsagd, medarbetare, medarbetarutveckling |
| Anställning               | Startdatum, slutdatum och övergångsdatum                                                                  | Aktuell medarbetare, uppsagd, medarbetare, medarbetarutveckling |
| Geografisk plats      | Stad, region, postnummer och delstat eller region                                                           | Aktuell medarbetare, uppsagd, medarbetare, medarbetarutveckling |
| Jobb                      | Funktion, typ och rubrik                                                                                  | Aktuell befattning, aktuell medarbetare |
| Tidigare befattningstilldelning | Orsak för tilldelningen, startdatum, slutdatum och jobb                                                           | Kalenderförskjutning, datum, jobb, befattning |
| Befattning                 | Avdelning, FTE, befattning, befattningstyp och titel                                                        | Aktuell befattning, aktuell medarbetare |
| Befattningsutveckling           | Positioner över tid, FTE och jobb                                                                          | Kalenderförskjutning, datum, jobb, befattning |
| Rapporterar till               | Förnamn, efternamn och fullständiga namn                                                                       | Aktuell medarbetare, uppsagd, medarbetare, medarbetarutveckling |
| Uppsagda medarbetare      | Avslutade arbetare, uppsägningsdatum, titel, befattning och jobb                                             | Företag, geografisk plats, medarbetarens namn, rapporter till, förskjutningskalender, datum, medarbetarens titel, demografi, anställning, jobb, befattning |
| Namn på medarbetare            | Förnamn, efternamn och fullständiga namn                                                                       | Aktuell arbetare, uppsagd medarbetare, medarbetarutveckling |
| Medarbetartitel           | Titel och tjänsteålder                                                                                   | Aktuell medarbetare, uppsagd, medarbetare, medarbetarutveckling |
| Medarbetarutveckling           | Arbetare över tid, antal anställda, företag och befattning                                                        | Företag, geografisk plats, medarbetarens namn, rapporter till, förskjutningskalender, datum, medarbetarens titel, demografi, anställning, jobb |
| Jobb                      | Funktion, typ och rubrik                                                                                      | Aktuell medarbetare, aktuell befattning, medarbetarutveckling, prioriterade kompetenser för jobbet, tidigare befattningstilldelning, avslutade medarbetare |
| Prioriterad kompetens för jobbet      | Prioritet, värdering, kompetens och kompetensnivå                                                                 | Jobb |
| Analys över medarbetarens kompetenser  | Certifierad, nivå, nivådatum och kompetens                                                                    | Medarbetarens namn, kompetens |  
| Resultat              | Värdering, beskrivning och bedömningsmodellen                                                                      | Aktuell medarbetare, aktuell befattning, medarbetarutveckling, prioriterade kompetenser för jobbet, tidigare befattningstilldelning, avslutade medarbetare |
|  Kompetens                   | Färdighet, färdighetstyp och värdering                                                                              | Analys över medarbetarens kompetenser, prioriterad kompetens för jobbet |                                                                                                                        

Dessa enheter används för att skapa beräknade mått i datamodellen. Beräknade åtgärder används sedan för att beräkna huvudindikatorerna för prestanda (KPI) samt de rapporter som används i Power BI-innehållspaketet. Om du vill inkludera ytterligare beräkningar i rapporterna och instrumentpanelerna kan du ladda ned och ändra filen .pbix från LCS. Filen är den standarddatamodell som använts för att skapa Power BI-innehållspaketet. När du är klar med ändringarna kan du skapa ett innehållspaket för organisationen samt en instrumentpanel som innehåller den information som du har lagt till.
