---
title: "Power BI-innehåll för personalmätningar"
description: "Det här avsnittet beskriver Power BI-innehåll för personalmätningar. Det förklarar hur du öppnar rapporter, och ger information om den datamodell och de enheter som användes för att skapa innehållet."
author: jcart1106
manager: AnnBe
ms.date: 06/16/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Operations, UnifiedOperations, Talent, Core
ms.custom: 264084
ms.assetid: 8e700583-3a7d-4f5f-9ac8-58c4feed1a02
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2016-11-30T00:00:00.000Z
ms.dyn365.ops.version: Version 1611
ms.translationtype: Human Translation
ms.sourcegitcommit: 869151f2486b7a481e4694cfb6992d0ee2cfc008
ms.openlocfilehash: 1f732a53eee17317417058b92706a9228d783cb5
ms.contentlocale: sv-se
ms.lasthandoff: 06/13/2017

---

# <a name="workforce-metrics-power-bi-content"></a>Power BI-innehåll för personalmätningar

[!include[banner](../includes/banner.md)]

Det här avsnittet beskriver **Microsoft Power BI-innehåll för personalmätningar**. Det förklarar hur du öppnar Power BI-rapporter, och ger information om den datamodell och de enheter som användes för att skapa innehållet.

## <a name="accessing-the-power-bi-content"></a>Åtkomst till Power BI-innehåll
Power BI-innehåll för **Personalmätningar** visas i arbetsytan **Personalhantering** om du använder någon av följande produkter:

- Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition, juli 2017 uppdatering
- Microsoft Dynamics 365 for Talent

## <a name="metrics-that-are-included-in-the-power-bi-content"></a>Mått som ingår i Power BI-innehållet
Följande tabell visar mätningar som är tillgängliga i varje rapport.

| Rapport                                           | Mätvärden                                                                                                                                                                                                            |
|--------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Personmätningar                                   | Sammanfattning av andra rapporter                                                                                                                           |
| Personalstyrka analys företag, avdelning, plats | Personalstyrka per företag, personalstyrka per avdelning, personalstyrka per plats och totala personalstyrkan                                                                                                                           |
| Personalstyrka analys, jobb, steg, chef            | Personalstyrka per jobb, personalstyrka per steg, personalstyrka per chef och totala personalstyrkan                                                                                                                                      |
| Personalstyrkan trendanalys                         | Personalstyrkan detta år jämfört med förra året per företag och rullande personalstyrka under de senaste 12 månaderna                                                                                                                        |
| FTE-analyser                                     | Totalt motsvarande heltid, totalt tilldelad heltid, heltid per avdelning, heltid de senaste 12 månaderna och heltid efter jobb |
| Personalens befolkning                           | Personalstyrka per ålder och kön, personalstyrka per etniskt ursprung, personalstyrka per veteranstatus, personalstyrka per civilstånd, antal heltidsstudenter, genomsnittlig anställningstid, genomsnittlig ålder, förhållandet mellan kvinnliga och manliga medarbetare och språk som talas av personalen |
| Befattningsanalys                                | Lediga befattningar per avdelning, öppna till fulla befattningar, aktiva till inaktiva befattningar och befattningar per avdelning                                                                                                   |
| Avgångsanalys                               | Avgång i år jämfört med förra året, avgång, medarbetare som slutar efter ålder och kön, genomsnittlig anställningstid för medarbetare som slutar, medarbetare som slutar denna månad och medarbetare som slutar efter orsak                                                                   |
| Personer efter avdelning                             | Anställda med ett anställningsnummer per avdelning, befattning och tilldelningens start-och slutdatum                                                                                                                       |
| Tjänsteålderanalys                               | Genomsnittligt anställningstid, genomsnittliga tjänsteår per företag och tjänsteålderslista                                                                                                                                                              |
| Medarbetarnas jubileumsdagar                           | Jubileumsdagar denna månad, jubileumsdagar nästa månad, anställda efter tjänsteår, och jubileumsdagar, tjänsteår per avdelning                                                                                                                                                                    |
| Medarbetarnas födelsedagar                               | Månadens födelsedagar, födelsedagar nästa månad, medarbetarnas födelsedagar, och födelsedagar per månad och avdelning                                                                                                                                                                    |
| Massanställningsprojekt                               | Totalt antal massanställningsprojekt, massanställningsprojekt efter status, massanställningsprojekt efter avdelning och ägare, massanställningsprojekt efter jobb och massanställningsprojekt                                                                                                                                                                    |

Diagrammen och rutorna i samtliga dessa rapporter kan filtreras och fästas på instrumentpanelen. Mer information om hur du filtrerar och fäster i Power BI finns i [Skapa och konfigurera en instrumentpanel](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-4-2-create-configure-dashboards).

## <a name="extending-the-power-bi-content"></a>Utöka Power BI-innehåll
Genom att använda innehållspaket som är tillgängliga i Microsoft Dynamics Lifecycle Services (LCS) kan du ge bra analyser till människor som inte är inloggade i Finance and Operations. Du kan ändra dessa innehållspaket så att de innehåller andra rapporter och modeller och publicera innehållspaket till din Power BI.com-innehavare för analys.

Du hittar Power BI-innehåll för **Personalmätningar** i biblioteket för gemensamma tillgångar i LCS. Mer information om hur du laddar ned innehållspaket och använder det i din organisation finns i [Power BI-innehåll i LCS från Microsoft och dina partner](power-bi-content-microsoft-partners.md). Om du vill se en demonstration som visar hur du implementerar Power BI-innehållet, se [Power BI-innehåll från Microsoft och dina samarbetspartners i Dynamics Lifecycle Services](https://mix.office.com/watch/9puyb1b2xs1w) Office mix.

Hämta Power BI-innehåll för **Personalmätningar** som kan tillämpas på den version av Microsoft Dynamics 365 som du använder.

>[!NOTE]
>.pbix-filerna i Lifecycle Services gäller endast Finance and Operations.

## <a name="understanding-the-data-model-and-entities"></a>Förstå datamodellen och enheterna
Följande tabell visar enheterna som innehållet baserades på.

| Enhet                   | Innehåll                                                                            | Relationer med andra entiteter |
|--------------------------|-------------------------------------------------------------------------------------|-----------------------------------|
| Kalenderförskjutning          | Kalenderförskjutningar till uppdela rapporter                                                   | Tidigare befattningstilldelning, befattningsutveckling, uppsagd medarbetare |
| Företag                  | Företag att filtrera rapporter efter                                                      | Aktuell medarbetare, uppsagd, medarbetare, medarbetarutveckling |
| Aktuell befattning         | Befattningar per innevarande datum, heltid, lediga positioner och lediga till tillsatta befattningar | Jobb, befattning |
| Aktuell medarbetare         | Arbetare per aktuellt datum, ålder och antal anställda                                  | Företag, geografisk plats, medarbetarens namn, rapporter till, förskjutningskalender, datum, medarbetarens titel, demografi, jobb, anställning, befattning |
| Datum                     | Dagar, veckor, månader och år.                                                      | Tidigare befattningstilldelning, befattningsutveckling, uppsagd medarbetare, medarbetarutveckling |
| Demografi             | Födelsedatum, kön, etniskt ursprung och civilstånd                            | Aktuell medarbetare, uppsagd, medarbetare, medarbetarutveckling |
| Anställning               | Startdatum, slutdatum och övergångsdatum                                           | Aktuell medarbetare, uppsagd, medarbetare, medarbetarutveckling |
| Geografisk plats      | Stad, region, postnummer och delstat eller region                                    | Aktuell medarbetare, uppsagd, medarbetare, medarbetarutveckling |
| Jobb                      | Funktion, typ och rubrik                                                           | Aktuell befattning, aktuell medarbetare |
| Tidigare befattningstilldelning | Orsak för tilldelningen, startdatum, slutdatum och jobb                                    | Kalenderförskjutning, datum, jobb, befattning |
| Befattning                 | Avdelning, FTE, befattning, befattningstyp och titel                                 | Aktuell befattning, aktuell medarbetare |
| Befattningsutveckling           | Positioner över tid, FTE och jobb                                                   | Kalenderförskjutning, datum, jobb, befattning |
| Rapporterar till               | Förnamn, efternamn och fullständiga namn                                                | Aktuell medarbetare, uppsagd, medarbetare, medarbetarutveckling |
| Uppsagda medarbetare      | Avslutade arbetare, uppsägningsdatum, titel, befattning och jobb                      | Företag, geografisk plats, medarbetarens namn, rapporter till, förskjutningskalender, datum, medarbetarens titel, demografi, anställning, jobb, befattning |
| Namn på medarbetare            | Förnamn, efternamn och fullständiga namn                                                | Aktuell arbetare, uppsagd medarbetare, medarbetarutveckling |
| Medarbetartitel           | Titel och tjänsteålder                                                            | Aktuell medarbetare, uppsagd, medarbetare, medarbetarutveckling |
| Medarbetarutveckling           | Arbetare över tid, antal anställda, företag och befattning                                 | Företag, geografisk plats, medarbetarens namn, rapporter till, förskjutningskalender, datum, medarbetarens titel, demografi, anställning, jobb |
| Massanställningsprojekt        | Antal massanställningsprojekt, projektägare och projektstatus                     | Företag, massanställningsrad |
| Massanställningsrad           | Avdelning, anställningstyp och befattning                                           | Datum, jobb, massanställningsprojekt |

Dessa enheter används för att skapa beräknade mått i datamodellen. Beräknade åtgärder används sedan för att beräkna huvudindikatorerna för prestanda (KPI) samt de rapporter som används i Power BI-innehållspaketet. Om du vill inkludera ytterligare beräkningar i rapporterna och instrumentpanelerna kan du ladda ned och ändra filen .pbix från LCS. Filen är den standarddatamodell som använts för att skapa Power BI-innehållspaketet. När du är klar med ändringarna kan du skapa ett innehållspaket för organisationen samt en instrumentpanel som innehåller den information som du har lagt till.

