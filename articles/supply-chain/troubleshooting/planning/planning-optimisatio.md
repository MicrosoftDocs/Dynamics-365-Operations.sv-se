---
title: Planerad inköpsorder skapas när det finns ett inköp inom negativa dagar
description: Om disponeringskoden är Min/max skapas en planerad inköpsorder med planeringsoptimering när det finns ett inköp inom negativa dagar.
author: ChristianRytt
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: ReqTransPo,MpsIntegrationParameters
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: ilebedev
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 94d569684a0bfa2398e98147b9b85531954f8d56748894034a048fa627230ef0
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6775517"
---
# <a name="planned-purchase-order-is-created-when-a-purchase-exists-within-negative-days"></a>Planerad inköpsorder skapas när det finns ett inköp inom negativa dagar

KB-nummer: 4614298

## <a name="symptoms"></a>Symtom

Om disponeringskoden är *Min/max* skapas en planerad inköpsorder med planeringsoptimering när det finns ett inköp inom negativa dagar.

## <a name="resolution"></a>Upplösning

Planeringsoptimering har inte stöd för negativa dagar. Det garanterar alltid att planerade order inte schemaläggs inom produktionstiden i förhållande till det aktuella datumet. Inköpsstiden är till exempel 10 dagar och en inköpsorder förväntas komma in åtta dagar från idag. I det här fallet används inköpsordern som tillgång för efterfrågan som är fem dagar från idag.

Därför rekommenderar vi att du justerar dina produktionstider för att täcka alla (eller nästan alla) av dina scenarier.
