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
ms.openlocfilehash: 73ebc45ee83516f573c3f73ef8106da9ae44c590c05d8dbd08520bc5ef19e49a
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6714220"
---
# <a name="reversal-of-reporting-as-finished-creates-an-unexpected-open-transaction"></a>En återföring av rapportering som färdig skapar en oväntat öppen transaktion

KB-nummer: 4612469

## <a name="symptoms"></a>Symtom

Om du återför rapportering som färdig som har markering skapar systemet en öppen transaktion där den återförda kvantiteten har samma lagerdimensioner som den återförda transaktionen.

## <a name="resolution"></a>Upplösning

När du återför en rapportera som färdig-åtgärd initieras lagerdimensionen från produktionsjournalen. Därför hämtar det batchnumret. På grund av markering ärver försäljningsordertransaktionerna batchnumret.

Dimensionen kan återställas när rapportering som färdigt bokförs.
