---
title: Kompensationsplan med fast lön
description: Detta ämne tillhandahåller information och en exempelfrågeställning för lönelistaentiteten för fast kompensationsplan i Dynamics 365 Human Resources.
author: jcart
ms.date: 08/25/2021
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
ms.openlocfilehash: 14829f18fb5e3adde83e265cd6e70b60e1ff03ac
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/31/2022
ms.locfileid: "8069106"
---
# <a name="payroll-fixed-compensation-plan"></a>Kompensationsplan med fast lön


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Detta ämne beskriver lönelisteentiteten för fast kompensationsplan i Dynamics 365 Human Resources.

### <a name="description"></a>beskrivning

Denna entitet tillhandahåller den fasta kompensationsplan som tilldelats för en viss befattning för en medarbetare.

Fysiskt namn: mshr_payrollfixedcompensationplanentity.

## <a name="properties"></a>Egenskaper

| Egenskap</br>**Fysiskt namn**</br>**_Typ_** | Använd | beskrivning |
| --- | --- | --- |
| **Plan-ID**</br>mshr_planid</br>*Sträng* | Skrivskydd | Anger kompensationsplanen.  |
| **Personalnummer**</br>mshr_personnelnumber</br>*Sträng* | Skrivskydd | Medarbetarens unika personalnummer. |
| **Lönesats**</br>mshr_payrate</br>*Decimal* | Skrivskydd | Lönesats som definieras i den fasta kompensationsplanen. |
| **Befattnings-ID**</br>mshr_positionid</br>*Sträng* | Skrivskydd | Positions-ID som är kopplat till medarbetaren samt registrering för fast kompensationsplan. |
| **Giltig från**</br>mshr_validfrom</br>*Datum Tid Offset* |  Skrivskydd | Det datum då medarbetarens fasta kompensation börjar gälla.  |
| **Giltig till**</br>mshr_validto</br>*Datum Tid Offset* | Skrivskydd | Det datum då medarbetarens fasta kompensation slutar gälla. |
| **Lönefrekvens**</br>mshr_payfrequency</br>*Sträng* | Skrivskydd | ID för [kompensationslönefrekvensen](hr-admin-integration-payroll-api-compensation-pay-frequency.md) för den angivna lönesatsen. |
| **Valuta**</br>mshr_currency</br>*Sträng* | Skrivskydd | Den valuta som har definierats för den fasta kompensationsplanen. |
| **Lönelisteentiteten för fast kompensation**</br>mshr_payrollfixedcompensationplanentityid</br>*GUID* | Systemgenererad | Ett systemgenererat GUID-värde som ger kompensationsplanen ett unikt ID. |

## <a name="relations"></a>Relationer

|Egenskapsvärde | Relaterad entitet | Navigeringsegenskap | Samlingstyp |
| --- | --- | --- | --- |
| _mshr_fk_employee_id_value | [mshr_payrollemployeeentity](hr-admin-integration-payroll-api-payroll-employee.md) | mshr_FK_Employee_id | mshr_FK_PayrollEmployeeEntity_FixedCompPlan |
| _mshr_fk_job_id_value | [mshr_payrollpositionjobentity](hr-admin-integration-payroll-api-payroll-position-job.md) | mshr_FK_Job_id | mshr_FK_PayrollPositionJobEntity_FixedCompPlan |
| _mshr_fk_payrollposition_id_value | [mshr_payrollpositionentity](hr-admin-integration-payroll-api-payroll-position.md) | mshr_FK_PayrollPosition_id | mshr_FK_PayrollPositionEntity_FixedCompPlan |
| _mshr_fk_plan_id_value | mshr_hcmcompfixedplantableentity | mshr_FK_Plan_id | - |
| _mshr_fk_variablecompaward_id_value | [mshr_payrollvariablecompensationawardentity](hr-admin-integration-payroll-api-payroll-variable-compensation-plan.md) | mshr_FK_VariableCompAward_id | mshr_FK_PayrollVariableCompensationAwardEntity_FixedComp |

## <a name="example-query"></a>Exempelfrågeställning

**Begäran**

```http
GET [Organizaton URI]/api/data/v9.1/mshr_payrollfixedcompensationplanentities?$filter=mshr_personnelnumber eq @personnelnumber and mshr_validfrom le @asofdate and mshr_validto ge @asofdate&@personnelnumber='000041'&@asofdate=2021-04-01
```

**Svar**

```json
{
    "mshr_planid": "GradeC",
    "mshr_personnelnumber": "000041",
    "mshr_payrate": 75200,
    "mshr_positionid": "000276",
    "mshr_validfrom": "2011-04-05T00:00:00Z",
    "mshr_validto": "2154-12-31T00:00:00Z",
    "mshr_payfrequency": "Annual",
    "mshr_currency": "USD",
    "_mshr_fk_employee_id_value": "00000d3c-0000-0000-d5ff-004105000000",
    "_mshr_fk_plan_id_value": "0000070c-0000-0000-b328-fef003000000",
    "_mshr_fk_job_id_value": "00010094-0000-0000-df00-014105000000",
    "mshr_payrollfixedcompensationplanentityid": "0000029f-0000-0000-d5ff-004105000000",
    "_mshr_fk_payroll_id_value": null
}
```

## <a name="see-also"></a>Se även

[Introduktion till API för löneintegrering](hr-admin-integration-payroll-api-introduction.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
