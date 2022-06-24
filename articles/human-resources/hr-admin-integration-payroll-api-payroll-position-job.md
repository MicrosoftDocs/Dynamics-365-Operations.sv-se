---
title: Lönebefattningsjobb
description: Detta ämne tillhandahåller information och en exempelfrågeställning för entiteten för lönebefattningsjobb i Dynamics 365 Human Resources.
author: jcart
ms.date: 04/07/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2021-04-07
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: fa347f4b99adc7c29d69daf62ad2bbfc14726a19
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8864095"
---
# <a name="payroll-position-job"></a>Lönebefattningsjobb


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Detta ämne beskriver löneentiteten för befattning för Dynamics 365 Human Resources.

### <a name="description"></a>Beskrivning

Denna entitet tillhandahåller relationen mellan befattningen och ett jobb för en given fast kompensationsplan.

Fysiskt namn: mshr_payrollpositionjobentity.

## <a name="properties"></a>Egenskaper

| Egenskap</br>**Fysiskt namn**</br>**_Typ_** | Använd | Beskrivning |
| --- | --- | --- |
| **Befattnings-ID**</br>mshr_positionid</br>*Sträng* | Skrivskydd | Befattningens ID. |
| **Giltig från**</br>mshr_validto</br>*Datum Tid Offset* | Skrivskydd | Datumet från vilket befattningen och jobbrelationen gäller. |
| **Giltig till**</br>mshr_validto</br>*Datum Tid Offset* | Skrivskydd | Datumet till och med vilket befattningen och jobbrelationen gäller. |
| **Jobb-ID**</br>mshr_jobid</br>*Sträng* | Skrivskydd | Jobbets ID. |
| **Primärt fält**</br>mshr_primaryfield</br>*Sträng* | Systemgenererad | Primärt fält. |
| **Entitets-ID för lönebefattningsjobb**</br>mshr_payrollpositionjobentityid</br>*Guid* | Systemgenererat. | Ett systemgenererat globalt unikt ID (GUID) som identifierar jobbet unikt. |

## <a name="relations"></a>Relationer

| Egenskapsvärde | Relaterad entitet | Navigeringsegenskap | Samlingstyp |
| --- | --- | --- | --- |
| _mshr_fk_fixedcompplan_id_value | mshr_payrollfixedcompensationplanentity | mshr_FK_FixedCompPlan_id | mshr_FK_PayrollFixedCompensationPlanEntity_Job |
| _mshr_fk_jobdetail_id_value | mshr_hcmjobdetailentity | mshr_FK_JobDetail_id | Inte tillämpligt |
| _mshr_fk_payroll_id_value | mshr_payrollpositionentity | mshr_FK_Payroll_id | mshr_FK_PayrollPositionEntity_Job |

## <a name="example-query"></a>Exempelfrågeställning

**Begäran**

```http
GET [Organizaton URI]/api/data/v9.1/mshr_payrollpositionjobentities?$filter=mshr_positionid eq '000276'
```

**Svar**

```json
{
    "mshr_positionid": "000276",
    "mshr_validfrom": "2016-07-06T18:11:33Z",
    "mshr_validto": "2154-12-31T23:59:59Z",
    "mshr_jobid": "Accountant",
    "mshr_primaryfield": "000276 | Accountant | 7/6/2016 06:11:33 pm",
    "_mshr_fk_jobdetail_id_value": "00000b8d-0000-0000-b0ff-004105000000",
    "_mshr_fk_fixedcompplan_id_value": "0000058a-0000-0000-d5ff-004105000000",
    "_mshr_fk_payroll_id_value": "00000427-0000-0000-df00-014105000000",
    "mshr_payrollpositionjobentityid": "00000906-0000-0000-df00-014105000000"
}
```

## <a name="see-also"></a>Se även

[Introduktion till API för löneintegrering](hr-admin-integration-payroll-api-introduction.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
