---
title: Rensningjobbet för försäljningsuppdateringshistorik misslyckas eller har prestandaproblem
description: Batchjobbet för rensning av försäljningshistorik kan misslyckas eller ta mycket lång tid om det finns stora mängder försäljningsuppdateringsdata.
author: myvakalo
ms.date: 10/05/2021
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: myvakalo
ms.search.validFrom: 2021-09-29
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 124fb90ecafd4f4cccbd8a8bb443694c95365732
ms.sourcegitcommit: 197e6ddee84522fd587c6e4ee4f9089101e301c2
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/13/2022
ms.locfileid: "8570356"
---
# <a name="sales-update-history-cleanup-job-fails-or-has-performance-issues"></a>Rensningjobbet för försäljningsuppdateringshistorik misslyckas eller har prestandaproblem

## <a name="symptoms"></a>Symtom

Batchjobbet för **Rensning av försäljningsuppdateringshistorik** misslyckas eller har prestandaproblem.  

## <a name="cause"></a>Orsak

Detta kan inträffa när ditt system omfattar ett stort antal försäljningsuppdateringar, vilket kan leda till en stor mängd försäljningsuppdateringsdata. Rensningsjobbet försöker rensa alla dessa data i en enda transaktion. Detta innebär att jobbet kan ta mycket lång tid att köra eller till och med misslyckas.

## <a name="resolution"></a>Lösning

En ny version av batchjobbet **Rensning av försäljningsuppdateringshistorik** finns för Supply Chain Management version 10.0.19 och högre. Den här funktionen är inte aktiverad som standard. Mer information om hur funktionen fungerar och hur du aktiverar den i funktionshanteringen finns i [Schemalägga datarensning i försäljningshistorik](../../sales-marketing/sales-update-history-cleanup-performance-improvements.md).

