---
title: "Gör manuella justeringar på baslinjeprognosen"
description: "Denna artikel beskriver hur du kan göra manuella justeringar till en baslinje prognos och visa information om prognosen."
author: YuyuScheller
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ReqDemPlanForecastViewer
audience: Application User
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 72704
ms.assetid: e7c5d44e-07bc-40b1-a4b3-8ba46483ef9e
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 869151f2486b7a481e4694cfb6992d0ee2cfc008
ms.openlocfilehash: 0b3b56aa838888461a6d27c6612e405a3cf59414
ms.contentlocale: sv-se
ms.lasthandoff: 06/13/2017


---

# Gör manuella justeringar på baslinjeprognosen
<a id="make-manual-adjustments-to-the-baseline-forecast" class="xliff"></a>

[!include[banner](../includes/banner.md)]


Denna artikel beskriver hur du kan göra manuella justeringar till en baslinje prognos och visa information om prognosen. 

Innan du gör manuella justeringar, det är viktigt att du förstår några begrepp på olika sidor.

## Raster på det justerade behovet prognos sida
<a id="grid-on-the-adjusted-demand-forecast-page" class="xliff"></a>
Det **justerade behovet prognos** sidan innehåller ett rutnät som har följande struktur:

-   Den första kolumnen visar element, fördelningsnycklar, företag och så vidare, att prognosen har genererats för. Undertiteln på sidan ger en beskrivning av den aktuella prognosen mått som visas i rutnätet. Om undertexten på sidan exempelvis är **Företag / Plats / Allokeringsnyckel för artikel** och en av radrubrikerna i rutnätet är **USMF / 1 / D\_Alloc**, visar den raden prognosen för företaget USMF, plats 1 , samt artikelallokeringsnyckeln **D\_Alloc**.
-   Följande kolumnerna representerar prognos hinkar att prognosen har genererats för. Varje kolumnrubrik är den första dagen av den prognostiserade kostnadsslag som visas.
-   Värdena i cellerna utgör prognosen för ett objekt, objekt fördelningsnyckel, och så vidare, för att särskilda prognostiserade hink.

## Prognosaggregering och deaggregering
<a id="forecast-aggregation-and-deaggregation" class="xliff"></a>
Undertiteln på sidan visar prognossummeringen. 

Till exempel, om undertexten på sidan **Företag / Ort / fördelningsnyckel / artikelnummer / Färg / Storlek / Konfiguration / Stil**, det finns ingen prognos aggregering och prognosen visas på objektet och dess dimensioner. För att ändra aggregering, använd **ändra prognosen mått** sida som du kan öppna från programmenyn. 

För att ändra prognosen, klicka på någon av de celler som är tillgängliga, och den justerade prognosen. Den redigerade cell omedelbart blir fet för att indikera att prognosen att det visar inte prognosen att behovsprognoser service skapats, men har justerats manuellt. 

Om du ändrar aggregering för att göra sidan mer aggregerade data, kan du använda **efterfrågan prognosrader** sidan för att se de enskilda prognosrader som sminkar den aggregerade prognosen. 

Exempelvis du har genererat den prognos på artikelnivå, men du vet att efterfrågan på denna punkt kommer att öka mellan alla platser på grund av en kampanj eller annan liknande händelse. I detta fall kan du ange den aggregering till **företag / Post fördelningsnyckel / Objekt** på **ändra prognosen mått** sida. Du kan justera den globala prognos för posten över alla orter i **Justerat behov prognos** raster. För att se effekten av din förändring på alla orter, öppna **efterfrågan prognosrader** sida. På den här sidan kommer du att se en rad för posten för varje ort, den justerade prognosen och den ursprungliga prognosen. 

När justeringen av den prognosticerade kvantiteten görs på aggregerad nivå, använder systemet viktad tilldelning för att distribuera förändringen bland de rader som skapar sammansättningen. 

Du kan också göra manuella justeringar på **efterfrågan prognosrader** sida, genom att modifiera antingen den **totala kvantitet** värde eller **kvantitet** celler i de-aggregering raster.

## Visa detaljer för prognos
<a id="viewing-details-of-the-forecast" class="xliff"></a>
Du kan öppna **Demand forecast sidan detaljer för** att se mer information om prognosen. 

**Efterfrågan sidan Detaljer** visar följande information i grafisk och i tabellform format:

-   Det historiska behovet att prognosen prognosen är baserad på.
-   Den aktuella prognosen som används av huvudplanering.
-   Den nya efterfrågan prognostiserade värden och de belopp de har justerats manuellt.
-   Konfidensintervallet för prognostiserade värden.
-   Den prognosmodell som använts för att generera prognos. Om du tittar på aggregerade data, du skar ser en förteckning av alla de metoder som användes för samtliga aggregerade tidsserier.
-   Den inre modellen noggrannhet (MAPE). För mer information om prognosprecision, se [övervakning prognosprecision](monitor-forecast-accuracy.md).

**Anteckningar:**

-   De konfidensintervall som visas i **Prognosdelen** av sidan representerar skillnaden mellan konfidensintervall övre gräns och konfidensintervallet undre gräns. För att se värdena för de övre och nedre gränserna, hovra över diagrammet i den **historiska efterfrågan och prognos grafiskt** .
-   Om du använder tjänsten Microsoft Azure Machine Learning för Finance and Operations-efterfrågeprognoser, kan du ange vilken förtroendenivå som den genererade prognosen ska ha. Ett konfidensintervall består av ett antal värden som fungerar som goda prognoser för efterfrågan. En 95-procentig konfidensnivå procenttal indikerar att det finns en 5-procentig risk att efterfrågan faller utanför konfidensintervallet.

Du kan också göra manuella justeringar av prognosen på **efterfrågan sidan detaljer** genom att ändra värdena i **prognosen** raden i **prognos** .

Se även
<a id="see-also" class="xliff"></a>
--------

[Övervaka prognosprecisionen](monitor-forecast-accuracy.md)

[Generera en statistisk baslinjeprognos](generate-statistical-baseline-forecast.md)




