---
title: Faktoravskrivning
description: Den här artikeln ger en översikt över faktoravskrivningsmetoden.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetDepreciationProfile
audience: Application User
ms.reviewer: roschlom
ms.custom: 13831
ms.assetid: 2b6c4fe4-02ff-4191-bcad-32f1f34c15f2
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 87cca8b3472f572cd1c4ba3d894269f7ba0f248a
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5241084"
---
# <a name="factor-depreciation"></a>Faktoravskrivning

[!include [banner](../includes/banner.md)]

Den här artikeln ger en översikt över faktoravskrivningsmetoden.

Faktorer är de procentsatser som används till att skriva av tillgångar. När du ställer in en avskrivningsprofil för anläggningstillgångar och väljer värdet **Faktor** i fältet **Metod** på sidan för **Avskrivningsprofiler** kan du ställa in progressiv, digressiv eller linjär avskrivning:

-   I progressiv avskrivning ökar avskrivningsbeloppet för varje avskrivningsperiod.
-   I digressiv avskrivning, minskar avskrivningsbeloppet per period med tiden.
-   I linjär avskrivning är avskrivningen densamma för varje period.

Reglerna och exemplen nedan anger hur du kan ställa in faktorer för varje avskrivningstyp. 

> [!NOTE] 
> När du väljer **Faktor** i fältet **Metod** kommer fälten **Faktor** och **Intervall** att visas.

## <a name="progressive-depreciation"></a>Progressiv avskrivning
Värdet i fältet **Faktor** är mer än **50**.

### <a name="example"></a>Exempel

Anskaffningspriset är 100 000, faktorn är 70, livslängden är 10 år och avskrivningen börjar den 1 januari. Avskrivningsbeloppen och bokförda nettovärdesbelopp visas endast för de första sex åren av livslängden.

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

Anskaffningspriset är 100 000, faktorn är 20, livslängden är 10 år och avskrivningen börjar den 1 januari. Avskrivningsbeloppen och bokförda nettovärdesbelopp visas endast för de första sex åren av livslängden.

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





[!INCLUDE[footer-include](../../includes/footer-banner.md)]