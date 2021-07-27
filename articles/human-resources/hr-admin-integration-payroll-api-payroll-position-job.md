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
ms.openlocfilehash: 842c459acd8b5e1a8b6074243b3afa18dc6a13c5
ms.sourcegitcommit: 89bb2a7f402deed32998eddc1e56e75250e3d15e
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/29/2021
ms.locfileid: "6314247"
---
# <a name="payroll-position-job"></a>Lönebefattningsjobb

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Detta ämne beskriver löneentiteten för befattning för Dynamics 365 Human Resources.

### <a name="description"></a>beskrivning

Denna entitet tillhandahåller relationen mellan befattningen och ett jobb för en given fast kompensationsplan.

Fysiskt namn: mshr_payrollpositionjobentity.

## <a name="properties"></a>Egenskaper

| Egenskap<br>**Fysiskt namn**<br>**_Typ_** | Använd | beskrivning |
| --- | --- | --- |
| **Jobb-ID**<br>mshr_jobid<br>*Sträng* | Skrivskydd<br>Obligatoriskt |Jobbets ID. |
| **Giltig från**<br>mshr_validto<br>*Datum Tid Offset* | Skrivskydd <br>Obligatoriskt | Datum från vilket befattningen och jobbrelationen gäller. |
| **Giltig till**<br>mshr_validto<br>*Datum Tid Offset* | Skrivskydd <br>Obligatoriskt | Datum till och med vilket befattningen och jobbrelationen gäller.  |
| **Befattnings-ID**<br>mshr_positionid<br>*Sträng* | Skrivskydd<br>Obligatoriskt | Befattningens ID. |
| **Primärt fält**<br>mshr_primaryfield<br>*Sträng* | Obligatoriskt<br>Systemgenererad |  |
| **ID-värde för befattningsjobb**<br>_mshr_fk_positionjob_id_value<br>*GUID* | Skrivskydd<br>Obligatoriskt<br>Sekundärnyckel:mshr_PayrollPositionJobEntity för mshr_payrollpositionjobentity |ID för det jobb som är kopplat till befattningen.|
| **ID-värde för fast kompensationsplan**<br>_mshr_fk_fixedcompplan_id_value<br>*GUID* | Skrivskydd<br>Obligatoriskt<br>Sekundärnyckel: mshr_FixedCompPlan_id för mshr_payrollfixedcompensationplanentity  | ID för den fasta kompensationsplan som är kopplad till befattningen. |
| **Entitets-ID för lönebefattningsjobb**<br>mshr_payrollpositionjobentityid<br>*Guid* | Obligatoriskt<br>Systemgenererat. | Ett systemgenererat GUID-värde som unikt identifierar jobbet.  |

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
