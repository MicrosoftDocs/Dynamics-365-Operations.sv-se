---
title: En återföring av rapportering som färdig skapar en oväntat öppen transaktion
description: Återföring av rapportering som färdig som har markering skapar en öppen transaktion där den återförda kvantiteten har samma lagerdimensioner som den återförda transaktionen.
author: niwang
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: ProdTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: ea9044a9008e766c7fc92f98e27cfb91076f5b44
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026927"
---
# <a name="reversal-of-reporting-as-finished-creates-an-unexpected-open-transaction"></a>En återföring av rapportering som färdig skapar en oväntat öppen transaktion

KB-nummer: 4612469

## <a name="symptoms"></a>Symtom

Om du återför rapportering som färdig som har markering skapar systemet en öppen transaktion där den återförda kvantiteten har samma lagerdimensioner som den återförda transaktionen.

## <a name="resolution"></a>Upplösning

När du återför en rapportera som färdig-åtgärd initieras lagerdimensionen från produktionsjournalen. Därför hämtar det batchnumret. På grund av markering ärver försäljningsordertransaktionerna batchnumret.

Dimensionen kan återställas när rapportering som färdigt bokförs.
