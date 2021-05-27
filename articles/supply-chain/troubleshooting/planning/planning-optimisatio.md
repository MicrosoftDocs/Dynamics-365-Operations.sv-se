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
ms.openlocfilehash: 826496c2de956ff949dd79ab8aa643053719bf75
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026921"
---
# <a name="planned-purchase-order-is-created-when-a-purchase-exists-within-negative-days"></a>Planerad inköpsorder skapas när det finns ett inköp inom negativa dagar

KB-nummer: 4614298

## <a name="symptoms"></a>Symtom

Om disponeringskoden är *Min/max* skapas en planerad inköpsorder med planeringsoptimering när det finns ett inköp inom negativa dagar.

## <a name="resolution"></a>Upplösning

Planeringsoptimering har inte stöd för negativa dagar. Det garanterar alltid att planerade order inte schemaläggs inom produktionstiden i förhållande till det aktuella datumet. Inköpsstiden är till exempel 10 dagar och en inköpsorder förväntas komma in åtta dagar från idag. I det här fallet används inköpsordern som tillgång för efterfrågan som är fem dagar från idag.

Därför rekommenderar vi att du justerar dina produktionstider för att täcka alla (eller nästan alla) av dina scenarier.
