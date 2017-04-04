---
title: Faktoravskrivning
description: "Den här artikeln ger en översikt över faktoravskrivningsmetoden."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: AssetDepreciationProfile
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 13831
ms.assetid: 2b6c4fe4-02ff-4191-bcad-32f1f34c15f2
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: b41901d573e977a89fcd1a7c1ebf7185e162c654
ms.openlocfilehash: d57c1811bfed466b7707214b85bc1fcecabbce2b
ms.lasthandoff: 03/31/2017


---

# <a name="factor-depreciation"></a>Faktoravskrivning

Den här artikeln ger en översikt över faktoravskrivningsmetoden.

Faktorer är de procentsatser som används till att skriva av tillgångar. När du ställer in en avskrivningsprofil för anläggningstillgångar och väljer värdet **Faktor** i fältet **Metod** på sidan för **Avskrivningsprofiler** kan du ställa in progressiv, digressiv eller linjär avskrivning:

-   I progressiv avskrivning ökar avskrivningsbeloppet för varje avskrivningsperiod.
-   I digressiv avskrivning, minskar avskrivningsbeloppet per period med tiden.
-   I linjär avskrivning är avskrivningen densamma för varje period.

Reglerna och exemplen nedan anger hur du kan ställa in faktorer för varje avskrivningstyp. 

> [!NOTE] 
> När du väljer **faktor** i den **metod** fältet den **faktor** fält och **intervallet** visas.

## <a name="progressive-depreciation"></a>Progressiv avskrivning
Värdet i fältet **Faktor** är mer än **50**.

### <a name="example"></a>Exempel

Anskaffningspris är 100 000, faktorn är 70, livslängden är 10 år och avskrivningen börjar den 1 januari. Avskrivningsbeloppen och bokfört nettovärde belopp visas endast för de första sex året av livslängden.

| År | Period      | Avskrivningsbelopp | Bokfört nettovärdebelopp |
|------|-------------|---------------------|-----------------------|
| 1    | 31 december | 307,69              | 99 692,31             |
| 2    | 31 december | 1 447,21            | 98 245,10             |
| 3    | 31 december | 3 104,50            | 95 140,60             |
| 4    | 31 december | 5 150,21            | 89 990,39             |
| 5    | 31 december | 7 522,95            | 82 467,44             |
| 6    | 31 december | 10 184,06           | 72 283,38             |

## <a name="digressive-depreciation"></a>Digressiv avskrivning
Värdet i fältet **Faktor** är mindre än **50**.

### <a name="example"></a>Exempel

Anskaffningspris är 100 000, faktorn är 20, livslängden är 10 år och avskrivningen börjar den 1 januari. Avskrivningsbeloppen och bokfört nettovärde belopp visas endast för de första sex året av livslängden.

| År | Period      | Avskrivningsbelopp | Bokfört nettovärdebelopp |
|------|-------------|---------------------|-----------------------|
| 1    | 31 december | 56 080,43           | 43 919,57             |
| 2    | 31 december | 10 665,70           | 33 253,87             |
| 3    | 31 december | 7 156,22            | 26 097,65             |
| 4    | 31 december | 5 538,06            | 20 559,59             |
| 5    | 31 december | 4 579,89            | 15 979,70             |
| 6    | 31 december | 3 937,36            | 12 042,34             |

## <a name="straight-line-depreciation"></a>Linjär avskrivning
Värdet i fältet **Faktor** är lika med **50**. I detta fall är avskrivningen densamma för varje period och du bör beakta följderna av värdena som du har angett i andra fält, enligt beskrivningen i [Linjär avskrivning av tjänstelivstid](straight-line-service-life-depreciation.md).

