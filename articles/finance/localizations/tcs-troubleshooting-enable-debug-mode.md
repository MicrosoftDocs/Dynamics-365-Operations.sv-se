---
title: Aktivera felsökningsläge i momsberäkningstjänst
description: I den här artikeln beskrivs hur du aktiverar felsökningsläget i tjänsten momsberäkning för att undersöka problem.
author: hangwan
ms.date: 03/25/2022
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: TaxIntegrationTaxServiceParameters
audience: Application User
ms.reviewer: ''
ms.search.region: Global
ms.author: hangwan
ms.search.validFrom: 03/23/2022
ms.dyn365.ops.version: Version 10.0.21
ms.openlocfilehash: 2bb381939ebe32cb51caf730cdd441557d83a4c0
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8887802"
---
# <a name="enable-debug-mode-in-the-tax-calculation-service"></a>Aktivera felsökningsläge i momsberäkningstjänst

[!include [banner](../includes/banner.md)]

I den här artikeln beskrivs hur du aktiverar felsökningsläget i tjänsten Momsberäkning för att undersöka problem.

1. Lägg till **&debug=vs%2CconfirmExit&** till URL:en för Application Object Server (AOS) och uppdatera sedan sidan.
2. När du väljer **Moms** för att beräkna momsen öppnas en textfil med namnet **TaxServiceTroubleshootingLog.txt**. Filen **TaxServiceTroubleshootingLog.txt** innehåller **TaxableDocument** och beräkningsparametern. De här resultaten returneras från momstjänsten och undantagsinformation för felsökning.

## <a name="sample"></a>Exempel

```json
===============================Tax service calculation input JSON:=====================================
{
    "TaxableDocument": {
    "Header": [
        {
        "Lines": [
            {
            "Transaction Line ID": "5816,68719677391",
            ...
            }
        ],
        "Transaction Header ID": "2022,68719506302",
        ...
        }
    ]
    },
    "Parameter": {
    "ContinueOnErrors": true,
    ...
    },
    "Adjustment": {
    "Lines": {}
    }
}
===========================Tax service calculation result JSON:=================================
{
    "taxDocument": {
    "Header": [
        {
        "Lines": [
            {
            "Tax Codes": {
                ...
            }
        ],
        "Measures": {
            "List Code": "EUTrade"
        },
        "Tax Registration ID": null,
        "Transaction Header ID": "2022,68719506302",
        "Errors": null
        }
    ]
    },
    "solutionId": "b51e0025-cbbe-4d37-bf0b-90d7be4f214d|1",
    "isPartialSuccess": false
}
=============================CorrelationId:==============================
"21f3a8a1-ee9a-477b-b44e-b8ec79e74d16"
```

[!INCLUDE[footer-include](../../includes/footer-banner.md)]