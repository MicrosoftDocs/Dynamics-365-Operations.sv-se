---
title: Lönefrekvens för kompensation
description: Detta ämne tillhandahåller information och en exempelfrågeställning för entiteten Lönefrekvens för kompensation i Dynamics 365 Human Resources.
author: marcelbf
ms.date: 09/01/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: marcelbf
ms.search.validFrom: 2021-09-01
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 9afe27776797b2355a32226bbd7fa514b5c5d962
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8894626"
---
# <a name="compensation-pay-frequency"></a>Lönefrekvens för kompensation


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Detta ämne beskriver entiteten för Lönefrekvens för kompensation i Dynamics 365 Human Resources.

Fysiskt namn: mshr_hcmpayrateconversionentity.

### <a name="description"></a>Beskrivning

Den här enheten ger information om lönesatskonverteringen för en given kompensationslönefrekvens.

## <a name="properties"></a>Egenskaper

| Egenskap</br>**Fysiskt namn**</br>**_Typ_** | Använd | Beskrivning |
| --- | --- | --- |
| **Konvertering av årlig lönesats**</br>mshr_annualconversionfactor</br>*Decimal* | Skrivskydd | Den årliga konverteringsfaktorn för betalningsfrekvensen. |
| **Beskrivning**</br>mshr_description</br>*Sträng* | Skrivskydd | En beskrivning av konverteringsfaktorn. |
| **Konvertering av timlönesats**</br>mshr_hourlyconversionfactor</br>*Decimal* | Skrivskydd | Timkonverteringsfaktorn för betalningsfrekvensen. |
| **Konvertering av månadslönesats**</br>mshr_monthlyconversionfactor</br>*Decimal* | Skrivskydd | Den månatliga konverteringsfaktorn för betalningsfrekvensen. |
| **Lönesatskonvertering**</br>mshr_payrateconversion</br>*Sträng* | Skrivskydd | En unik sträng för att identifiera konverteringsfrekvensen. |
| **Period**</br>mshr_period</br>*periodalternativuppsättning* | Skrivskydd | Huvudperioden för den givna lönesatskonverteringen. |
| **Konvertering av veckolönesats**</br>mshr_weeklyconversionfactor</br>*Decimal* | Skrivskydd | Veckokonverteringsfaktorn för betalningsfrekvensen. |
| **ID för dataområde**</br>mshr_dataareaid</br>*Sträng* | Skrivskydd | Den juridiska personen (företaget). |
| **Lönefrekvens för kompensation, entitets-ID**</br>mshr_dirpersonnamehistoricalentityid</br>*GUID* | Systemgenererad | Ett systemgenererat globalt unikt ID (GUID) som identifierar posten unikt. |

## <a name="example-query-for-payroll-employee"></a>Exempelfrågeställning för lönemedarbetare

**Begäran**

```http
GET [Organizaton URI]/api/data/v9.1/mshr_hcmpayrateconversionentities?$filter=mshr_payrateconversion eq 'Annual' and mshr_dataareaid eq 'usmf'
```

**Svar**

```json
{
    "mshr_annualconversionfactor": 1,
    "mshr_description": "Annual",
    "mshr_hourlyconversionfactor": 0.0004807692,
    "mshr_monthlyconversionfactor": 0.0833333333,
    "mshr_payrateconversion": "Annual",
    "mshr_period": 200000000,
    "mshr_weeklyconversionfactor": 0.0192307692,
    "mshr_dataareaid": "usmf",
    "mshr_hcmpayrateconversionentityid": "0000056e-0000-0000-b027-fef003000000",
    "_mshr_dataareaid_id_value": null
}
```

## <a name="see-also"></a>Se även

[Introduktion till API för löneintegrering](hr-admin-integration-payroll-api-introduction.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
