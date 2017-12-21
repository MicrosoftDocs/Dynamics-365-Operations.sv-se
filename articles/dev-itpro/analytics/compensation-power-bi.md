---
title: "Power BI-innehållspaket för kompensationer"
description: "Det här avsnittet beskriver Power BI-innehåll för kompensationer. Det förklarar hur du öppnar rapporter, och ger information om den datamodell och de enheter som användes för att skapa innehållet."
author: jcart1106
manager: AnnBe
ms.date: 12/01/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Operations, Talent, Core
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 6e64337f19600b18320550d91c134949c33af7b0
ms.openlocfilehash: 7143a2750d284080609c884ce15bc2b2e8943394
ms.contentlocale: sv-se
ms.lasthandoff: 12/01/2017

---

# <a name="compensation-power-bi-content"></a>Power BI-innehållspaket för kompensationer

[!include[banner](../includes/banner.md)]

Det här avsnittet beskriver Microsoft Power BI-innehåll för **Kompensation**. Det förklarar hur du öppnar rapporter, och ger information om den datamodell och de enheter som användes för att skapa innehållet.

## <a name="accessing-the-power-bi-content"></a>Åtkomst till Power BI-innehåll
Power BI-innehåll för **kompensation** visas i arbetsytan **kompensationshantering** om du använder någon av följande produkter:

- Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition
- Microsoft Dynamics 365 for Talent

## <a name="reports-that-are-included-in-the-power-bi-content"></a>Rapporter som ingår i Power BI-innehållet
Rapporter som ingår i  Power BI-innehållspaketet **Kompensation** har både diagram och tabeller med ytterligare information. Följande register beskriver rapporterna.

| Rapport                     | Innehåll |
|----------------------------|----------|
| Översikt över kompensation      | Sammanfattning av andra rapporter |
| Kompensationsanalys      | Timlön och avlönade anställda per företag, totala anställda per kompensationsplan, manliga och kvinnliga anställda per kompensationsplan och medarbetarkompensation per avdelning |
| Befattningsutbetalningsanalys      | Högsta och lägsta timlön och löneutbetalning, befattning med högsta och lägsta lön och heltids- och deltidsbefattning |
| Kompensationsplananalys | Anmälan till medarbetare efter valt förmån |

Diagrammen och rutorna i samtliga dessa rapporter kan filtreras och fästas på instrumentpanelen. Mer information om hur du filtrerar och fäster i Power BI finns i [Skapa och konfigurera en intrumentpanel](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-4-2-create-configure-dashboards).

## <a name="extending-the-power-bi-content"></a>Utöka Power BI-innehåll
Om du använder Microsoft Dynamics 365 for Operations version 1611 eller Finance and Operations, Enterprise edition (juli-uppdateringen 2017) hittar du Power BI-innehållet **Kompensation** i biblioteket för delade tillgångar i LCS. Mer information om hur du laddar ned innehållspaket och använder det i din organisation finns i [Power BI-innehåll i LCS från Microsoft och dina partner](power-bi-content-microsoft-partners.md). Om du vill se en demonstration som visar hur du implementerar Power BI-innehållet, se [Power BI-innehåll från Microsoft och dina samarbetspartners i Dynamics Lifecycle Services](https://mix.office.com/watch/9puyb1b2xs1w) Office mix.

Hämta Power BI-innehållet för **Kompensation** som avser versionen av Microsoft Dynamics 365 som du använder.

>[!NOTE]
>.pbix-filerna i Lifecycle Services gäller endast Finance and Operations.

## <a name="understanding-the-data-model-and-entities"></a>Förstå datamodellen och enheterna
Följande data används för att fylla i rapporterna i Power-Bi-innehållet för **Kompensation**. Denna tabell visar enheterna som innehållet baserades på.

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
| Uppsagda medarbetare      | Uppsagda medarbetare, uppsägningsdatum, titel, befattning och jobb                                             | Företag, kompensation, geografisk plats, medarbetarens namn, rapporter till, förskjutningskalender, datum, medarbetarens titel, demografi, anställning, jobb, befattning, förmåner |
| Förmåner                 | Giltighetsdatum, förmånsalternativ, förmånsplanen och förmånstyp                                             | Aktuellt namn, uppsagd medarbetare, medarbetarutveckling |
| Namn på medarbetare            | Förnamn, efternamn och fullständiga namn                                                                       | Aktuell medarbetare, uppsagd, medarbetare, medarbetarutveckling |
| Medarbetartitel           | Titel och tjänsteålder                                                                                   | Aktuell medarbetare, uppsagd, medarbetare, medarbetarutveckling |
| Medarbetarutveckling           | Arbetare över tid, antal anställda, företag och befattning                                                        | Företag, kompensation, geografisk plats, medarbetarens namn, rapporter till, förskjutningskalender, datum, medarbetarens titel, demografi, anställning, jobb, förmåner |

Dessa enheter används för att skapa beräknade mått i datamodellen. Beräknade åtgärder används sedan för att beräkna huvudindikatorerna för prestanda (KPI) samt de rapporter som används i innehåll. Om du vill inkludera ytterligare beräkningar i rapporterna och instrumentpanelerna kan du ladda ned och ändra filen .pbix från LCS. Filen är den standarddatamodell som använts för att skapa innehållet. När du är klar med ändringarna kan du skapa ett innehållspaket för organisationen samt en instrumentpanel som innehåller den information som du har lagt till.

