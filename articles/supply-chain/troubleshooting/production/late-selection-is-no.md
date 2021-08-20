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
ms.openlocfilehash: 8800ec411ddd7ae73c5ac159592620a07b50c1e87938f823274ec24062c9a71a
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6741966"
---
# <a name="late-selection-isnt-respected-when-production-orders-are-reset-via-a-batch-job"></a>Sent val respekteras inte när produktionsorder återställs via ett batchjobb

KB-nummer: 4614634

## <a name="symptoms"></a>Symtom

När du använder ett återkommande batchjobb för att återställa statusen för en produktionsorder respekteras inte sena val.

## <a name="resolution"></a>Upplösning

Den aktuella designen stöder inte användning av sena val för processen *Återställ status*.
