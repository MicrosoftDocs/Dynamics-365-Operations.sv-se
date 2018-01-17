---
title: "Power BI-innehåll med förmåner"
description: "Det här avsnittet beskriver Power BI-innehåll för förmåner. Det beskriver hur du får åtkomst till de rapporter som är inkluderade, samt ger dig information om den datamodell och de enheter som användes för att skapa innehållet."
author: jcart1106
manager: AnnBe
ms.date: 12/19/2017
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
ms.sourcegitcommit: cb43245afe578341251b140383a3b03ba2abd962
ms.openlocfilehash: 2c8570984e44499d8cc5d45ab38da43f461c61e9
ms.contentlocale: sv-se
ms.lasthandoff: 12/19/2017

---

# <a name="benefits-power-bi-content"></a>Power BI-innehåll med förmåner

[!include[banner](../includes/banner.md)]

Det här avsnittet beskriver Microsoft Power BI-innehåll för **Förmåner**. Det beskriver hur du får åtkomst till de rapporter som är inkluderade, samt ger dig information om den datamodell och de enheter som användes för att skapa innehållet.

## <a name="accessing-the-power-bi-content"></a>Åtkomst till Power BI-innehåll
Power BI-innehåll för **Förmåner** visas i arbetsytan **Förmånshantering** om du använder någon av följande produkter:

- Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition
- Microsoft Dynamics 365 for Talent

## <a name="reports-that-are-included-in-the-power-bi-content"></a>Rapporter som ingår i Power BI-innehållet
Rapporter som ingår i  Power BI-innehållspaketet **Förmåner** har både diagram och tabeller med ytterligare information. Följande register beskriver rapporterna.

| Rapport                       | Innehåll                                                                                       |
|------------------------------|------------------------------------------------------------------------------------------------|
| Översikt över förmånsanmälan  | De mesta och minst anmälda planerna, anmäland per medarbetargrupp och valda förmånsplanalternativ |
| Anställningsförmåner            | Anmälan till medarbetare efter valt förmån                                                        |
                                                                                             
Diagrammen och rutorna i samtliga dessa rapporter kan filtreras och fästas på instrumentpanelen. Mer information om hur du filtrerar och fäster i Power BI finns i [Skapa och konfigurera en intrumentpanel](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-4-2-create-configure-dashboards).


## <a name="understanding-the-data-model-and-entities"></a>Förstå datamodellen och enheterna
Följande data används för att fylla i rapporterna i Power-Bi-innehållet för **Förmåner**. Denna tabell visar enheterna som innehållet baserades på.

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



