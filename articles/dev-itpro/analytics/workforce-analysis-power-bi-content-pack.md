---
title: "Power BI-innehåll för personalmätningar"
description: "Det här avsnittet beskriver Power BI-innehåll för personalmätningar. Det förklarar hur du öppnar rapporter, och ger information om den datamodell och de enheter som användes för att skapa innehållet."
author: jcart1106
manager: AnnBe
ms.date: 12/19/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: HcmWorkforceWorkspace
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations, Talent
ms.custom: 264084
ms.assetid: 8e700583-3a7d-4f5f-9ac8-58c4feed1a02
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: cb43245afe578341251b140383a3b03ba2abd962
ms.openlocfilehash: 8ff4eb80eeb47a72fc1ac91ddc4bdfccebc4c0c6
ms.contentlocale: sv-se
ms.lasthandoff: 12/19/2017

---

# <a name="workforce-metrics-power-bi-content"></a>Power BI-innehåll för personalmätningar

[!include[banner](../includes/banner.md)]

Det här avsnittet beskriver **Microsoft Power BI-innehåll för personalmätningar**. Det förklarar hur du öppnar Power BI-rapporter, och ger information om den datamodell och de enheter som användes för att skapa innehållet.

## <a name="accessing-the-power-bi-content"></a>Åtkomst till Power BI-innehåll
Power BI-innehåll för **Personalmätningar** visas i arbetsytan **Personalhantering** om du använder någon av följande produkter:

- Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition 
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



