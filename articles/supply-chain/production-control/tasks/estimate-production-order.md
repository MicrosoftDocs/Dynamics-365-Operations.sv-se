---
title: Uppskatta en produktionsorder
description: Du kan köra den här proceduren med demonstrationsdataföretaget USMF eller använda dina egna data.
author: johanhoffmann
manager: AnnBe
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f1e99d7c84171e4affe59fb896a7e93c2a328740
ms.sourcegitcommit: fcb27d6a46cd544feef34f6ec7607bdd46b0c12b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/18/2020
ms.locfileid: "3146777"
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
