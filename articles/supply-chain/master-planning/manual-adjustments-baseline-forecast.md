---
title: Gör manuella justeringar på baslinjeprognosen
description: Denna artikel beskriver hur du kan utföra manuella justeringar på en baslinjeprognos och visa information om prognosen.
author: t-benebo
ms.date: 01/07/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqDemPlanForecastViewer
audience: Application User
ms.reviewer: kamaybac
ms.custom: 72704
ms.assetid: e7c5d44e-07bc-40b1-a4b3-8ba46483ef9e
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: benebotg
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b3b2cc172e551096492f2aebfd8b81eb3f9c471b
ms.sourcegitcommit: 491ab9ae2b6ed991b4eb0317e396fef542d3a21b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/03/2022
ms.locfileid: "9741268"
---
# <a name="make-manual-adjustments-to-the-baseline-forecast"></a>Gör manuella justeringar på baslinjeprognosen

[!include [banner](../includes/banner.md)]

Denna artikel beskriver hur du kan utföra manuella justeringar på en baslinjeprognos och visa information om prognosen. 

Innan du gör manuella justeringar, det är viktigt att du förstår några begrepp på olika sidor.

## <a name="grid-on-the-adjusted-demand-forecast-page"></a>Raster på det justerade behovet prognos sida
Det **justerade behovet prognos** sidan innehåller ett rutnät som har följande struktur:

-   Den första kolumnen visar element, fördelningsnycklar, företag och så vidare, att prognosen har genererats för. Undertiteln på sidan ger en beskrivning av den aktuella prognosen mått som visas i rutnätet. Om undertexten på sidan exempelvis är **Företag / Plats / Allokeringsnyckel för artikel** och en av radrubrikerna i rutnätet är **USMF / 1 / D\_Alloc**, visar den raden prognosen för företaget USMF, plats 1 , samt artikelallokeringsnyckeln **D\_Alloc**.
-   Följande kolumnerna representerar prognos hinkar att prognosen har genererats för. Varje kolumnrubrik är den första dagen av den prognostiserade kostnadsslag som visas.
-   Värdena i cellerna utgör prognosen för ett objekt, objekt fördelningsnyckel, och så vidare, för att särskilda prognostiserade hink.

## <a name="forecast-aggregation-and-de-aggregation"></a>Prognossummeringen och aggregering
Undertiteln på sidan visar prognossummeringen. 

Till exempel, om undertexten på sidan **Företag / Ort / fördelningsnyckel / artikelnummer / Färg / Storlek / Konfiguration / Stil**, det finns ingen prognos aggregering och prognosen visas på objektet och dess dimensioner. För att ändra aggregering, använd **ändra prognosen mått** sida som du kan öppna från programmenyn. 

För att ändra prognosen, klicka på någon av de celler som är tillgängliga, och den justerade prognosen. Den redigerade cell omedelbart blir fet för att indikera att prognosen att det visar inte prognosen att behovsprognoser service skapats, men har justerats manuellt. 

Om du ändrar aggregering för att göra sidan mer aggregerade data, kan du använda **efterfrågan prognosrader** sidan för att se de enskilda prognosrader som sminkar den aggregerade prognosen. 

Exempelvis du har genererat den prognos på artikelnivå, men du vet att efterfrågan på denna punkt kommer att öka mellan alla platser på grund av en kampanj eller annan liknande händelse. I detta fall kan du ange den aggregering till **företag / Post fördelningsnyckel / Objekt** på **ändra prognosen mått** sida. Du kan justera den globala prognos för posten över alla orter i **Justerat behov prognos** raster. För att se effekten av din förändring på alla orter, öppna **efterfrågan prognosrader** sida. På den här sidan kommer du att se en rad för posten för varje ort, den justerade prognosen och den ursprungliga prognosen. 

När justeringen av den prognosticerade kvantiteten görs på aggregerad nivå, använder systemet viktad tilldelning för att distribuera förändringen bland de rader som skapar sammansättningen. 

Du kan också göra manuella justeringar på **efterfrågan prognosrader** sida, genom att modifiera antingen den **totala kvantitet** värde eller **kvantitet** celler i de-aggregering raster.

## <a name="viewing-details-of-the-forecast"></a>Visa detaljer för prognos
Du kan öppna **Demand forecast sidan detaljer för** att se mer information om prognosen. 

**Efterfrågan sidan Detaljer** visar följande information i grafisk och i tabellform format:

-   Det historiska behovet att prognosen prognosen är baserad på.
-   Den aktuella prognosen som används av huvudplanering.
-   Den nya efterfrågan prognostiserade värden och de belopp de har justerats manuellt.
-   Konfidensintervallet för prognostiserade värden.
-   Den prognosmodell som använts för att generera prognos. Om du tittar på aggregerade data, du skar ser en förteckning av alla de metoder som användes för samtliga aggregerade tidsserier.
-   Den inre modellen noggrannhet (MAPE). För mer information om prognosprecision, se [Övervaka prognosprecision](monitor-forecast-accuracy.md).

**Anteckningar:**

- Funktionen *Val av prognosmodell på detaljer för efterfrågeprognos* lägger till inställningar på sidan **Detaljer för efterfrågeprognos** som låter dig välja vilka prognosmodeller som ska inkluderas. Från och med version 10.0.21 av Supply Chain Management är denna funktion aktiverad som standard. Från och med version 10.0.25 av Supply Chain Management är denna funktion obligatorisk och kan inte inaktiveras. Om du kör en version som är äldre än 10.0.25 kan administratörer aktivera eller inaktivera den här funktionen genom att söka efter funktionen *Prognosmodellval på Detaljer för efterfrågeprognos* i arbetsytan [funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).
- De konfidensintervall som visas i **Prognosdelen** av sidan representerar skillnaden mellan konfidensintervall övre gräns och konfidensintervallet undre gräns. För att se värdena för de övre och nedre gränserna, hovra över diagrammet i den **historiska efterfrågan och prognos grafiskt** .
- Om du använder Microsoft Azure Machine Learning-efterfrågeprognoser, kan du ange vilken förtroendenivå som den genererade prognosen ska ha. Ett konfidensintervall består av ett antal värden som fungerar som goda prognoser för efterfrågan. En 95-procentig konfidensnivå procenttal indikerar att det finns en 5-procentig risk att efterfrågan faller utanför konfidensintervallet.

Du kan också göra manuella justeringar av prognosen på **efterfrågan sidan detaljer** genom att ändra värdena i **prognosen** raden i **prognos** .

## <a name="additional-resources"></a>Ytterligare resurser

- [Övervaka prognosens exakthet](monitor-forecast-accuracy.md)
- [Generera en statistisk baslinjeprognos](generate-statistical-baseline-forecast.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]