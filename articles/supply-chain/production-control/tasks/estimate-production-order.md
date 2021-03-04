---
title: Uppskatta en produktionsorder
description: Du kan köra den här proceduren med demonstrationsdataföretaget USMF eller använda dina egna data.
author: johanhoffmann
manager: tfehr
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5bbb541a09809c1f1bfada42094d840a2f6e7764
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "4437366"
---
# <a name="estimate-a-production-order"></a>Uppskatta en produktionsorder

[!include [banner](../../includes/banner.md)]

Du kan köra den här proceduren med demonstrationsdataföretaget USMF eller använda dina egna data. I båda fall måste du ha en öppen produktionsorder som har statusen Skapad. Detta är den andra proceduren av sju som förklarar produktionsorderns livscykel.


## <a name="estimate-a-production-order"></a>Uppskatta en produktionsorder
1. Gå till Produktionskontroll > Produktionsorder > Alla produktionsorder.
2. Markera en order som har statusen Skapad i rutnätet.
3. Klicka på Produktionsorder i åtgärdsfönstret.
4. Klicka på Uppskattning.
    * I det här steget beräknas de uppskattade kostnaderna för en enskild produktionsorder.   
5. Klicka på OK.

## <a name="view-the-calculation-details"></a>Visa beräkningsuppgifterna
1. Klicka på Hantera kostnader i åtgärdsfönstret.
2. Klicka på Visa beräkningsuppgifter.
    * Den här sidan visar kostnadsuppdelningen. Du kan till exempel visa den totala självkostnaden per enhet för den färdiga produkten på den första raden. De efterföljande raderna innehåller kostnader i enlighet med strukturlistan, produktionsflödet och de indirekta kostnaderna.  


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]