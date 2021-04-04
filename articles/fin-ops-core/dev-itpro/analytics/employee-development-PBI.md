---
title: Power BI-innehåll för medarbetarutveckling
description: Det här avsnittet beskriver Power BI-innehåll för medarbetarutveckling.
author: jcart1106
manager: AnnBe
ms.date: 12/19/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.openlocfilehash: 1091357f1d86bac17c860a41daaa2577035163ca
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/09/2021
ms.locfileid: "5569673"
---
# <a name="employee-development-power-bi-content"></a>Power BI-innehåll för medarbetarutveckling

[!include [banner](../includes/banner.md)]

Det här avsnittet beskriver **medarbetarutveckling** Microsoft Power BI-innehåll.

## <a name="reports-that-are-included-in-the-power-bi-content"></a>Rapporter som ingår i Power BI-innehållet
Rapporter som ingår i **Medarbetarutveckling** Power BI har både diagram och tabeller med ytterligare information. Följande register beskriver rapporterna.

| Rapport                        | Innehåll |
|-------------------------------|----------|
| Översikt över medarbetarutveckling | Sammanfattning av andra rapporter |
| Analys över medarbetarens kompetenser       | Typer av medarbetarens kompetenser och medarbetarens kompetenser efter typ |
| Analys över medarbetarens kompetensnivå | Medarbetarens kompetensnivåer per avdelning, medarbetare per kompentensnivå och kompetenstyp och lägsta och högsta nivåerna per kompetens |
| Kompetensprofil                 | Kompetensprofil för vald medarbetare. |
| Kompetensanalys                | Kompetens efter typ och värdering |
| Resultatvärderingsanalys   | Medarbetare per lägsta och högsta värdering per jobb, medarbetarvärderingar per avdelning, medarbetare per värdering och beafattningstyp och högsta och lägsta värdering per befattning |
| Medarbetarresultatanalys | Medarbetarvärdering för vald värdering av chef |

Diagrammen och rutorna i samtliga dessa rapporter kan filtreras och fästas på instrumentpanelen. Mer information om hur du filtrerar och fäster i Power BI, se [Skapa och konfigurera en instrumentpanel](https://powerbi.microsoft.com/guided-learning/powerbi-learning-4-2-create-configure-dashboards).

## <a name="understanding-the-data-model-and-entities"></a>Förstå datamodellen och enheterna

| Enhet                   | Innehåll                                                                                                   | Relationer med andra entiteter |
|--------------------------|------------------------------------------------------------------------------------------------------------|-----------------------------------|
| Kalenderförskjutning          | Kalenderförskjutningar till uppdela rapporter                                                                          | Tidigare befattningstilldelning, befattningsutveckling, uppsagd medarbetare |
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
| Jobb                      | Funktion, typ och rubrik                                                                                  | Aktuell medarbetare, aktuell befattning, medarbetarutveckling, prioriterade kompetenser för jobbet, tidigare befattningstilldelning, avslutade medarbetare |
| Prioriterad kompetens för jobbet      | Prioritet, värdering, kompetens och kompetensnivå                                                                 | Jobb |
| Analys över medarbetarens kompetenser  | Certifierad, nivå, nivådatum och kompetens                                                                    | Medarbetarens namn, kompetens |
| Resultat              | Värdering, beskrivning och bedömningsmodellen                                                                      | Aktuell medarbetare, aktuell befattning, medarbetarutveckling, prioriterade kompetenser för jobbet, tidigare befattningstilldelning, avslutade medarbetare |
| Kompetens                    | Färdighet, färdighetstyp och värdering                                                                              | Analys över medarbetarens kompetenser, prioriterad kompetens för jobbet |


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]