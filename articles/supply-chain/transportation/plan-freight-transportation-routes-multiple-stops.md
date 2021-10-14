---
title: Planera frakttransportvägar med flera stopp
description: Den här artikeln ger en beskrivning av de olika elementen som du använder för att planera transportrutter i Dynamics 365 Supply Chain Management.
author: Henrikan
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: TMSHubMaster, TMSLoadBuildTemplates, TMSRateRouteWorkbench, TMSRouteGuide, TMSRoutePlan, TMSRouteWorkbench, WHSLoadTemplate, TMSRouteSchedule, TMSRouteRateDetail
audience: Application User
ms.reviewer: kamaybac
ms.custom: 90013
ms.assetid: 50d6f58c-f1c8-4321-9e83-8445cec57a85
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: eff1efd7530c410b392646e39325b58cbd8bcf78
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/29/2021
ms.locfileid: "7571243"
---
# <a name="plan-freight-transportation-routes-with-multiple-stops"></a>Planera frakttransportvägar med flera stopp

[!include [banner](../includes/banner.md)]

Den här artikeln ger en beskrivning av de olika elementen som du använder för att planera transportrutter i Dynamics 365 Supply Chain Management.

Du kan använda färdplaner och ruttguider för komplexa transportvägar som har flera stopp. Om samma rutt ska användas regelbundet kan du ställa in en tidsplanerad rutt.

## <a name="route-plans"></a>Flödesplaner
En färdplan väg innehåller ruttsegment som ger information om stoppen som besöks på vägen och om de transportföretag som används för varje segment. Du måste definiera stoppen utmed rutten som nav. Ett nav kan vara en leverantör, ett lagerställe, en kund eller bara en omlastningsplats där du byter transportföretag. Du kan definiera "punkttariffer" för olika avgifter för varje segment. Nedan följer några exempel:

-   Avgifter för resor till angivna segment
-   Avgifter för hämtning av varorna
-   Avgifter för att avlämning av varorna

Varje färdplan måste associeras med en ruttguide.

## <a name="route-guides"></a>Flödesguider
En ruttguide definierar villkoren för matchning av en last med en specifik färdplan. Du kan till exempel ange ett ursprungsnav och ett målnav, begränsningar för containervolym eller vikt och transportföretag, -tjänst eller -grupp. Ruttguider finns på sidan **Workbench för tariff/rutt** där laster kan matchas till rutter manuellt eller automatiskt. Om ruttguiden gäller för en tidsplanerad rutt finns den även på sidan tillgängligt på sidan **Workbench för lastuppbyggnad**.

## <a name="scheduled-routes"></a>Tidsplanerade rutter
En tidsplanerad rutt är en fördefinierad färdplan som har en tidsplan för leveransdatumen. Tidsplanerade rutter och ej tidsplanerade rutter skiljer sig åt på så sätt att laster tilldelas till dem. Om du tilldelar en ej tidsplanerad rutt med hjälp av sidan Workbench för tariff/rutt valideras endast lasten och ruttguiden. Om du tilldelar en tidsplanerad rutt tas det även hänsyn till datum och adresser från order och nav och datumet på färdplanen. Du behöver inte använda sidan Workbench för tariff/rutt för att tilldela laster manuellt till en tidsplanerad rutt. Använd i stället sidan Workbench för lastuppbyggnad för att föreslå att laster byggs på basis av kundadresser och leveransdatum från försäljningsorder för en viss tidsplanerad rutt. För tidsplanerade rutter kommer färdplanen att ha fasta ursprungs- och destinationshubbar. Vanligtvis kommer transportföretaget och -tjänsten att vara samma för alla segment, men de kan variera. Destinationsnav skapas med hjälp av postnumren till de kunder som besöks utmed rutten. Flera tidsplanerade rutter kan definieras för en färdplanen. Färdplanen måste kopplas till en ruttguide. För tidsplanerade rutter behöver planen dock endast kopplas till en ruttguide. Den tidsplanerad rutten används bara för att skapa faktiska rutter på sidan **Tidsplanerad rutt**. Du kan använda standardlastmallen när du föreslår laster på sidan Workbench för lastuppbyggnad.

## <a name="load-building-workbench"></a>Workbench för lastuppbyggnad
Sidan Workbench för lastuppbyggnad använder kundadresser och leveransdatum från försäljningsorder och tidsplanerade rutter som är tillgängliga för att föreslå en last. Som standard anges värdena från rutten i workbenchen. Du kan dock välja ett "från"-datum som är tidigare än "från"-datumet för rutten. När en last föreslås kontrolleras leveransadressen och leveransdatumet för alla öppna försäljningsorder. Om postnumret till leveransadressen matchar postnumret för en hubb i färdplanen och om leveransdatumet infaller inom det intervall som valts i kriterierna, föreslås försäljningsordern för lasten. Kapaciteten för lastmallen beaktas också. Endast en last föreslås åt gången. Om du har en försäljningsorder som inte ingår kan du behöva använda en annan lastmall (till exempel en lastmall för en större lastbil eller container) eller planera en extra leverans.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]