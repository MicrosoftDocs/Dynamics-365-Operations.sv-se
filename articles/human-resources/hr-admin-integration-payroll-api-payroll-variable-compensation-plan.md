---
title: Löneplan för variabel kompensation
description: Detta ämne tillhandahåller information och en exempelfrågeställning för lönelisteentiteten för fast kompensationsplan i Dynamics 365 Human Resources.
author: twheeloc
ms.date: 06/15/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2021-06-15
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 5c6190084c3f1ce15d6a4ab8f13843a5da801dd3
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8868142"
---
# <a name="payroll-variable-compensation-plan"></a>Löneplan för variabel kompensation


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Detta ämne beskriver lönelisteentiteten för variabel kompensationsplan i Dynamics 365 Human Resources.

### <a name="description"></a>beskrivning

Denna entitet tillhandahåller den variabla kompensationsplan som tilldelats för en viss befattning för en medarbetare.

Fysiskt namn: mshr_payrollvariablecompensationawardentity.

## <a name="properties"></a>Egenskaper

| Egenskap</br>**Fysiskt namn**</br>**_Typ_** | Använd | beskrivning |
| --- | --- | --- |
| **Personalnummer**</br>mshr_personnelnumber</br>*Sträng* | Skrivskydd | Medarbetarens unika personalnummer.  |
| **Ersättningsdatum**</br>mshr_awarddate</br>*Datum Tid Offset* | Skrivskydd | Datum för tilldelningen. |
| **Belöningstyp**</br>mshr_awardtype</br>*[Alternativuppsättningen mshr_HrmCompVarAwardEmplType](hr-admin-integration-payroll-api-award-type.md)* | Skrivskydd | Den kompensationstyp som definierats för den valda variabla kompensationsplanen. |
| **Valuta**</br>mshr_unitcurrencycode</br>*Sträng* | Skrivskydd |Den valuta som har definierats för den variabla kompensationsplanen.   |
| **Plan-ID för fast kompensation**</br>mshr_fixedplanid</br>*Sträng* | Skrivskydd | Den fasta kompensationsplan som ligger till grund för beräkningen av kompensationen. |
| **Enhetsvärde**</br>mshr_awardamount</br>*Decimal* | Skrivskydd | Värdet för enheten |
| **Processtyp**</br>mshr_processtype</br>*[Alternativuppsättningen mshr_hrmCompProcessType](hr-admin-integration-payroll-api-process-type.md)* | Skrivskydd | Processtypen. |
| **Typ av variabel kompensationsplan**</br>Sträng</br>*mshr_typeid* | Skrivskydd | Typ av variabel kompensationsplan. |
| **ID för typ av variabel kompensationsplan**</br>Sträng</br>*mshr_planid* | Skrivskydd | ID för variabel kompensationsplan. |
| **Antal enheter**</br>Decimal</br>*mshr_numberofunits* | Skrivskydd | Antalet enheter av kompensationen. |
| **Primärt fält**</br>mshr_primaryfield</br>*GUID* | Skrivskydd</br>Systemgenererat. | |
| **Löneplansentitet för variabel kompensation**</br>mshr_payrollvariablecompensationawardentityid</br>*GUID* | Systemgenererad | Ett systemgenererat GUID-värde som ger kompensationsplanen ett unikt ID. |

## <a name="relations"></a>Relationer 

|Egenskapsvärde | Relaterad entitet | Navigeringsegenskap | Samlingstyp |
| --- | --- | --- | --- |
| _mshr_fk_employee_id_value | [mshr_payrollemployeeentity](hr-admin-integration-payroll-api-payroll-employee.md) | mshr_FK_Employee_id | mshr_FK_PayrollEmployeeEntity_VariableCompAward |
| _mshr_fk_fixedcomp_id_value | [mshr_payrollfixedcompensationplanentity](hr-admin-integration-payroll-api-payroll-fixed-compensation-plan.md) | mshr_FK_FixedComp_id | mshr_FK_PayrollFixedCompensationPlanEntity_VariableCompAward |

## <a name="example-query"></a>Exempelfrågeställning

**Begäran**

```http
GET [Organizaton URI]/api/data/v9.1/mshr_payrollvariablecompensationawardentities?$filter=mshr_personnelnumber eq '000046'
```

**Svar**

```json
{
    "mshr_personnelnumber": "000046",
    "mshr_awarddate": "2015-01-15T00:00:00Z",
    "mshr_awardtype": 200000000,
    "mshr_unitcurrencycode": "USD",
    "mshr_fixedplanid": "",
    "mshr_unitvalue": 1,
    "mshr_processtype": 200000003,
    "mshr_typeid": "Bonus",
    "mshr_planid": "MgBonus",
    "mshr_numberofunits": 1500,
    "mshr_primaryfield": "000046 | MgBonus | Bonus | 1/15/2015",
    "_mshr_fk_employee_id_value": "00000666-0000-0000-daff-004105000000",
    "mshr_payrollvariablecompensationawardentityid": "000001a4-0000-0000-0d00-005001000000",
    "_mshr_fk_fixedcomp_id_value": null
}
```

## <a name="see-also"></a>Se även

[Introduktion till API för löneintegrering](hr-admin-integration-payroll-api-introduction.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
