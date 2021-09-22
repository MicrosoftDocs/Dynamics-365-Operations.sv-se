---
title: Inköpsavtalets maximala gräns gäller inte för en inköpsrekvisition
description: Inköpsavtalets maximala gräns gäller inte för en inköpsrekvisition
author: kamaybac
ms.date: 05/31/2021
ms.topic: troubleshooting
ms.search.form: PurchTable, PurchTablePart, PurchRFQTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yanansong
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: c19d40dce65acbe80d4572bfc4e925aa87ea4f02
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477610"
---
# <a name="the-purchase-agreement-maximum-limit-isnt-effective-on-a-purchase-requisition"></a>Inköpsavtalets maximala gräns gäller inte för en inköpsrekvisition

## <a name="symptoms"></a>Symtom

När en inköpsrekvisition är kopplad till ett inköpsavtal gäller inte den maximala gränsen från inköpsavtalet på inköpsrekvisitionen. Standard prisinformationen anges korrekt, men mer än den högsta gränsen från inköpsavtalet kan beställas i inköpsrekvisitionen.

## <a name="resolution"></a>Lösning

Detta är ett förväntat beteende. Eftersom rekvisitioner inte alltid godkänns ska en kvantitet eller ett belopp inte reserveras i inköpsavtalet. Därför kommer du inte att uppfylla den högsta gränsen från inköpsavtalet.
