---
title: Resultat för lagerställe Power BI-innehåll
description: Det här avsnittet beskriver vad som ingår i Power BI-innehållet för lagerställets prestanda. Det förklarar hur du öppnar Power BI-rapporter, och ger information om den datamodell och de enheter som används för att skapa innehållet.
author: Mirzaab
manager: AnnBe
ms.date: 12/18/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: WHSWarehousePerformancePowerBI
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 272953
ms.assetid: 4e4d4323-78cf-4ffa-8d5a-05e856c33db6
ms.search.region: Global
ms.author: mirzaab
ms.dyn365.ops.version: Version 1611
ms.search.validFrom: 2016-11-30
ms.openlocfilehash: 99966a67fa1fd91fc54e7100f8e2e41b87f6a406
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/15/2019
ms.locfileid: "1551146"
---
# <a name="warehouse-performance-power-bi-content"></a>Resultat för lagerställe Power BI-innehåll

[!include [banner](../includes/banner.md)]

Det här avsnittet beskriver vad som ingår i Power BI-innehållet för **lagerställets prestanda**. Det förklarar hur du öppnar Power BI-rapporter, och ger information om den datamodell och de enheter som används för att skapa innehållet.

## <a name="overview"></a>Översikt

Microsoft Power BI-innehåll för **Lagerställets prestanda** skapades så att chefer för lagerställen och verksamhetschefer kan övervaka viktiga inkommande, utgående och lagermått. Den använder lagerstyrning, produkt och andra transaktionsdata från ditt system och ger både en aggregerad vy över lagerställets prestanda och en uppdelning för leverantörer, produktgrupper och produkter samt plats och lagerställen.

Lagerställechefer kan använda Power BI-innehåll för **lagerställets prestanda** för att mäta följande tre områden:

- **Inkommande prestanda** – mät hur bra en leverantör presterar mot kundens krav (d.v.s. mät leveransresultat) och mät artikelinförselprestanda så att du kan identifiera problem kopplade till medarbetare eller artiklar under en period. Det är viktigt att du känner till om leverantörer levererar i tid, tidigare eller senare, så att du kan bestämma hur leverantörsprestanda påverkar övergripande artikelinförselprestanda. En leverantör som levererar utanför överrenskommet datum kan lägga extra tryck på lagerstället på grund av oväntat arbete och kan öka den genomsnittliga tiden för artikelinförsel.
- **Leveransprestanda** – mät om distributionslagret levereras i sin helhet och i tid till kunder (d.v.s. mät utgående transport- och leveransprestanda), så att du kan identifiera eventuella problem som rör produkter, platser eller lagerställen eller särskilda kunder. Om du tycker att du får sen leverans till specifika områden eller städer kan du behöva ägna mer uppmärksamhet åt transport eller kontohantering.
- **Platslagerprecision** – lagerprecision är en viktigt intern Business Intelligence för lagerställe (BI). Det är mycket viktigt att du avgör hur exakt du i allmänhet räknar. Det är dock också viktigt att fastställa hur exakt du artiklarna lagras på rätt plats och att markera avvikelsedata så att du kan hitta bättre befattningar för artiklar eller initiera totala positioner om ett visst objekt. (För närvarande levereras nya artikelbaserade cykliska funktioner som en snabbkorrigering). Om du använder Power BI-innehållet för att avgöra korrekt lagerbehållningsdata per lagerställe kan du även identifiera stöld i dina butiker. Du kan bestämma om några platser har lagerbehållningskvantiteter som avviker från företagets resursplaneringsdata (ERP). Dessa platser kan vara för stora eller omöjligt att räkna. Alternativt kan bland annat fysisk placering vara dålig, så att det är svårt att synkronisera en enstaka objekttyp med behållningsdata.

## <a name="accessing-the-power-bi-content-pack"></a>Åtkomst till Power BI-innehållspaketet
**Lagerprestanda** Power BI-innehåll visas på sidan **Lagerprestanda** (**Lagerhantering** \> **Förfrågningar och rapporter** \> **Analys av lagerprestanda** \> **Lagerprestanda**).

## <a name="metrics-that-are-included-in-the-power-bi-content"></a>Mätvärden som ingår i Power BI-innehållet
Power BI-innehållet för **Prestanda för lagerställe** innehåller ofta en rapport. Denna rapport består av en uppsättning mått som visualiseras som diagram, brickor och tabeller. Följande register ger en översikt över de visuella effekterna i Power BI-innehållet **Prestanda för lagerställe**.

| Rapportsida                 | Diagram                                   | beskrivning |
|-----------------------------|------------------------------------------|-------------|
| Inkommande prestanda         | Totala artikelinförslar                          | Antalet rader för artikelinförsel som bearbetas under en viss tidsperiod. |
| Inkommande prestanda         | Genomsnittlig tid för artikelinförsel                    | Genomsnittlig tid i timmar för alla artikelinförselrader för inköpsorder som har bearbetats från registrering av artiklar tills den senaste införseln bearbetas. |
| Inkommande prestanda         | Mottagen tidigare                           | Antal inköpsorderrader som tas emot tidigt. |
| Inkommande prestanda         | Mottagen i tid                         | Antal inköpsorderrader som tas emot i tid. |
| Inkommande prestanda         | Sent mottagen                            | Antal inköpsorderrader som tas emot sent. |
| Inkommande prestanda         | I tid av leverantör                        | En vy av hur många procent av inköpsorderrader som har inlevererats från en leverantör eller leverantörsgrupp tidigt, i tid och sent. |
| Inkommande prestanda         | Docka till genomsnittligt lagerartikelinförsel (timmar) | Genomsnittlig docka till lagerartikelinförsel tid i timmar över tiden. |
| Inkommande prestanda         | Medelvärde artikelinförsel av arbetare               | Genomsnittlig tid, i timmar, som en arbetare tar på sig för artikelinförsel krävs för inköpsorderrader. |
| Inkommande prestanda         | Medelvärde lagerartikelinförseltid per leverantör          | Genomsnittlig lagerartikelinförseltid i timmar av leverantör eller leverantörsgrupp. |
| Inkommande prestanda         | Medelvärde lagerartikelinförseltid per produkt         | Genomsnittlig lagerartikelinförseltid i timmar av artikel eller artikelgrupp. |
| Platslagerprecision | Totalt antal                              | Antalet rader för inventeringsarbete som bearbetas under en viss period. |
| Platslagerprecision | Avvikelsefrekvensen                         | Totala avvikelsefrekvensen i procent av alla rader som inventerats för en given period. |
| Platslagerprecision | Räkna utan avvikelse                | Antalet totala rader för inventeringarbete som har bearbetats, antalet rader som bearbetas utan någon avvikelse. |
| Platslagerprecision | Artiklar räknade över tid                  | Procent av artiklar som räknas med och utan avvikelser över tiden. |
| Platslagerprecision | Artikelkvantitetavvikelsen är större än % | En tabellvy över inventeringsrader vars avvikelser överskrider en viss mängd. Tabellen innehåller information om lagerställen, artiklar, genomsnittlig avvikelse, totalt antal rader för inventeringsarbete som räknas, antalet inventeringsrader som har avvikelser för platsen, genomsnittlig kvantitet som räknas, förväntad total kvantitet som ska räknas och faktisk artikelkvantitet som räknas. |
| Platslagerprecision | Artikel som räknas av arbetare                     | Arbetares räkneprestanda. Resultatet uttrycks som en procentandel av rader för inventeringarbete som inte har avvikelser. |
| Platslagerprecision | Objekt antal per site/lager           | Beräkningsresultat av antalet bearbetade rader för inventeringsarbete på plats eller lagerställe som har eller inte har avvikelser. |
| Platslagerprecision | Avvikelsefrekvens per produkt              | Avvikelsefrekvensen för inventeringsprestanda. Priset uttrycks som en procentandel av bearbetade rader för inventeringsarbete per artikel eller artikelgrupp. |
| Leveransprestanda        | Levererade rader                            | Antalet rader för leverans som levererats under en viss period. |
| Leveransprestanda        | Årlig                                    | Procentandel av rader för leverans som levereras tidigt. |
| Leveransprestanda        | I tid                                  | Procentandel av rader för leverans som levereras i tid. |
| Leveransprestanda        | Sent                                     | Procentandel av rader för leverans som levereras sent. |
| Leveransprestanda        | Leverans över tid                      | Procentandelen av rader för leverans som levereras i tid, tidigt eller sent under en viss period. En trendlinje visar trenden för rader som levereras i tid. |
| Leveransprestanda        | Sent leverans efter ort                     | En kartvisualisering över städer och områden som påverkas av försenade leveranser. |
| Leveransprestanda        | Leverans efter produkt                       | Den procentandel som levererades tidigt, i tid eller sent per artikel eller artikelgrupp. |
| Leveransprestanda        | Levererade av kunder                      | Den procentandel som levererades tidigt, i tid eller sent per kund eller kundgrupp. |
| Leveransprestanda        | Levererat per site/lagerställe              | Den procentandel som levererades tidigt, i tid eller sent per site eller lagerställe. |

## <a name="understanding-the-data-model-and-calculations"></a>Förstå datamodellen och beräkningar
Följande data används för att fylla i rapportsidorna Power BI-innehållet **Lagerställeprestanda**. Informationen visas som sammansatta mått som mellanlagras i Enhetslagring. Enhetslagring är en Microsoft SQL Server-databas som är optimerad för analys. Mer information finns i [Översikt för Power BI-integrering med enhetsarkiv](power-bi-integration-entity-store.md).

Följande sammanlagda huvudmått används till grund för innehållet:

| Rapportsida                 | Diagram                                   | Register                                | Beskrivning av beräkning |
|-----------------------------|------------------------------------------|---------------------------------------|--------------------------|
| Inkommande prestanda         | Totala artikelinförslar                          | WHSWorkLine                           | Antalet arbets rader där arbetstypen är **lägga**. |
| Inkommande prestanda         | Genomsnittlig tid för artikelinförsel                    | WHSWorkLine                           | Summan av arbetsrader maxtid dividerat med antalet arbetsrader maxtid, där arbetsrader maxtid är största skillnaden mellan arbetet skapades datum och avslutade datum. |
| Inkommande prestanda         | Mottagen tidigare                           | WHSWorkLine                           | Antalet arbetsrader där datumet för skapat arbete är tidigare än leveransdatumet som används. Om bekräftat datum för leveransen inte har angetts, kan du använda standardleveransdatum. |
| Inkommande prestanda         | Mottagen i tid                         | WHSWorkLine                           | Antalet arbetsrader där datumet för skapat arbete är lika med leveransdatumet som används. Om bekräftat datum för leveransen inte har angetts, kan du använda standardleveransdatum. |
| Inkommande prestanda         | Sent mottagen                            | WHSWorkLine                           | Antalet arbetsrader där datumet för skapat arbete är senare än leveransdatumet som används. Om bekräftat datum för leveransen inte har angetts, kan du använda standardleveransdatum. |
| Inkommande prestanda         | I tid av leverantör                        | WHSWorkLine                           | Inlevererade tidigt, Inlevererade i tid och Inlevererade sent (se beskrivningarna tidigare i den här tabellen). |
| Inkommande prestanda         | Docka till genomsnittligt lagerartikelinförsel (timmar)   | WHSWorkLine                           | Genomsnittstid för artikelinförsel (se beskrivningen tidigare i den här tabellen). |
| Inkommande prestanda         | Medelvärde artikelinförsel av arbetare               | WHSWorkLine                           | Genomsnittstid för artikelinförsel (se beskrivningen tidigare i den här tabellen). |
| Inkommande prestanda         | Medelvärde lagerartikelinförseltid per leverantör          | WHSWorkLine                           | Genomsnittstid för artikelinförsel (se beskrivningen tidigare i den här tabellen). |
| Inkommande prestanda         | Medelvärde lagerartikelinförseltid per produkt         | WHSWorkLine                           | Genomsnittstid för artikelinförsel (se beskrivningen tidigare i den här tabellen). |
| Platslagerprecision | Totalt antal                              | WHSWorkLineCycleCount                 | Rullande inventeringar där den absoluta avvikelsekvantiteten är lika med eller större än 0 (noll). |
| Platslagerprecision | Avvikelsefrekvensen                         | WHSWorkLineCycleCount                 | Rullande inventeringar som har avvikelser, delat med det totala antalet. En rullande inventering anses ha avvikelser om absoluta avvikelsekvantiteten är större än 0 (noll). |
| Platslagerprecision | Räkna utan avvikelse                | WHSWorkLineCycleCount                 | Rullande inventeringar där den absoluta avvikelsekvantiteten är mer än 0 (noll). |
| Platslagerprecision | Räkna med avvikelse                   | WHSWorkLineCycleCount                 | Rullande inventeringar där den absoluta avvikelsekvantiteten är lika med 0 (noll). |
| Platslagerprecision | Artiklar räknade över tid                  | WHSWorkLineCycleCount                 | Inventering utan avvikelsen och Inventering med avvikelse (se beskrivningarna tidigare i den här tabellen). |
| Platslagerprecision | Artikelkvantitetavvikelsen är större än % | WHSWorkLineCycleCount                 | Genomsnittlig avvikelse är den absoluta avvikelsekvantiteten dividerat med den förväntade kvantiteten när den absoluta avvikelsekvantiteten är större än 0 (noll). Genomsnittlig avvikelsekvantitet är den genomsnittliga absoluta avvikelsekvantiteten när den absoluta avvikelsekvantiteten är större än 0 (noll). Inventering med avvikelser, Total inventering, Förväntad kvantitet och Inventerad kvantitet där hela kvantiteten är grupperad efter artikel och plats (se beskrivningarna tidigare i den här tabellen). |
| Platslagerprecision | Artikel som räknas av arbetare                     | WHSWorkLineCycleCount                 | Inventering utan avvikelsen och Inventering med avvikelse (se beskrivningarna tidigare i den här tabellen). |
| Platslagerprecision | Objekt antal per site/lager           | WHSWorkLineCycleCount                 | Inventering utan avvikelsen och Inventering med avvikelse (se beskrivningarna tidigare i den här tabellen). |
| Platslagerprecision | Avvikelsefrekvens per produkt              | WHSWorkLineCycleCount                 | Avvikelsefrekvens (se beskrivningen tidigare i den här tabellen). |
| Leveransprestanda        | Levererade rader                            | SalesLine               | Inventeringen av rader där försäljningsrader levereras. |
| Leveransprestanda        | Årlig                                    | CustPackingSlipOnTimeStatus           | Försäljningsrader där leveransdatum är **1 (tidigare)**. Tidig innebär att leveransdatumet för följesedeln är tidigare än det bekräftade leveransdatumet för försäljningsraden. Om det bekräftade leveransdatumet inte anges, använd det begärda leveransdatumet. |
| Leveransprestanda        | I tid                                  | CustPackingSlipOnTimeStatus           | Försäljningsrader där leveransdatum är **2 (i tid)**. I tid innebär att leveransdatumet för följesedeln är lika med det bekräftade leveransdatumet för försäljningsraden. Om det bekräftade leveransdatumet inte anges, använd det begärda leveransdatumet. |
| Leveransprestanda        | Sent                                     | CustPackingSlipOnTimeStatus           | Försäljningsrader där leveransdatum är **3 (sent)**. Sent innebär att leveransdatumet för följesedeln är senare än det bekräftade leveransdatumet för försäljningsraden. Om det bekräftade leveransdatumet inte anges, använd det begärda leveransdatumet. |
| Leveransprestanda        | Leverans över tid                      | SalesLine CustPackingSlipOnTimeStatus | En order som helt levereras, där hela kvantiteten för försäljningsraden har levererats plus tidig, i tid och sen (se beskrivningarna tidigare i den här tabellen). |
| Leveransprestanda        | Sent leverans efter ort                     | CustPackingSlipOnTimeStatus           | Sen (se beskrivningen tidigare i den här tabellen). |
| Leveransprestanda        | Leverans efter produkt                       | CustPackingSlipOnTimeStatus           | Tidig, I tid och Sen (se beskrivningarna tidigare i den här tabellen). |
| Leveransprestanda        | Levererade av kunder                      | CustPackingSlipOnTimeStatus           | Tidig, I tid och Sen (se beskrivningarna tidigare i den här tabellen). |
| Leveransprestanda        | Levererat per site/lagerställe              | CustPackingSlipOnTimeStatus           | Tidig, I tid och Sen (se beskrivningarna tidigare i den här tabellen). |
