---
title: Sent val respekteras inte när produktionsorder återställs via ett batchjobb
description: När du använder ett återkommande batchjobb för att återställa statusen för en produktionsorder respekteras inte sena val.
author: johanhoffmann
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: ProdTableListPage
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: e53198f427f4060421a4f0078277682c43db1320
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026909"
---
# <a name="late-selection-isnt-respected-when-production-orders-are-reset-via-a-batch-job"></a>Sent val respekteras inte när produktionsorder återställs via ett batchjobb

KB-nummer: 4614634

## <a name="symptoms"></a>Symtom

När du använder ett återkommande batchjobb för att återställa statusen för en produktionsorder respekteras inte sena val.

## <a name="resolution"></a>Upplösning

Den aktuella designen stöder inte användning av sena val för processen *Återställ status*.
