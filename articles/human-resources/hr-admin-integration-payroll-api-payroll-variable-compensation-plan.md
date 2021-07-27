---
title: Löneplan för variabel kompensation
description: Detta ämne tillhandahåller information och en exempelfrågeställning för lönelisteentiteten för fast kompensationsplan i Dynamics 365 Human Resources.
author: marcelbf
ms.date: 06/15/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: marcelbf
ms.search.validFrom: 2021-06-15
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 5dc096c08ed808f577c8cdc96ca84000a0b80679
ms.sourcegitcommit: 89bb2a7f402deed32998eddc1e56e75250e3d15e
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/29/2021
ms.locfileid: "6314491"
---
# <a name="payroll-variable-compensation-plan"></a>Löneplan för variabel kompensation

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Detta ämne beskriver lönelisteentiteten för variabel kompensationsplan i Dynamics 365 Human Resources.

### <a name="description"></a>beskrivning

Denna entitet tillhandahåller den variabla kompensationsplan som tilldelats för en viss befattning för en medarbetare.

Fysiskt namn: mshr_payrollvariablecompensationawardentity.

## <a name="properties"></a>Egenskaper

| Egenskap</br>**Fysiskt namn**</br>**_Typ_** | Använd | beskrivning |
| --- | --- | --- |
| **Personalnummer**</br>mshr_personnelnumber</br>*Sträng* | Skrivskydd</br>Obligatoriskt |Medarbetarens unika personalnummer.  |
| **Ersättningsdatum**</br>mshr_awarddate</br>*Datum Tid Offset* | Skrivskydd</br>Obligatoriskt | Datum för tilldelningen. |
| **Belöningstyp**</br>mshr_awardtype</br>*[Alternativuppsättningen mshr_HrmCompVarAwardEmplType](hr-admin-integration-payroll-api-award-type.md)* | Skrivskydd</br>Obligatoriskt | Den kompensationstyp som definierats för den valda variabla kompensationsplanen. |
| **Valuta**</br>mshr_unitcurrencycode</br>*Sträng* | Skrivskydd </br>Obligatoriskt |Den valuta som har definierats för den variabla kompensationsplanen.   |
| **Plan-ID för fast kompensation**</br>mshr_fixedplanid</br>*Sträng* | Skrivskydd | Den fasta kompensationsplan som ligger till grund för beräkningen av kompensationen. |
| **Enhetsvärde**</br>mshr_awardamount</br>*Decimal* | Skrivskydd | Värdet för enheten |
| **Processtyp**</br>mshr_processtype</br>*[Alternativuppsättningen mshr_hrmCompProcessType](hr-admin-integration-payroll-api-process-type.md)* | Skrivskydd | Processtypen. |
| **Typ av variabel kompensationsplan**</br>Sträng</br>*mshr_typeid* | Skrivskydd | Typ av variabel kompensationsplan. |
| **ID för typ av variabel kompensationsplan**</br>Sträng</br>*mshr_planid* | Skrivskydd | ID för variabel kompensationsplan. |
| **Primärt fält**</br>mshr_primaryfield</br>*GUID* | Skrivskydd</br>Systemgenererat. | |
| **Medarbetarens ID**</br>mshr_fk_employee_id_value</br>*GUID* | Skrivskydd</br>Obligatoriskt</br>Sekundärnyckel: mshr_Employee_id för entiteten mshr_payrollemployeeentity  | Medarbetarens ID. |
| **Löneplansentitet för variabel kompensation**</br>mshr_payrollvariablecompensationawardentityid</br>*GUID* | Obligatoriskt</br>Systemgenererad | Ett systemgenererat GUID-värde som ger kompensationsplanen ett unikt ID. |


## <a name="example-query"></a>Exempelfrågeställning

**Begäran**

```http
GET [Organizaton URI]/api/data/v9.1/mshr_payrollvariablecompensationawardentities?$filter=mshr_personnelnumber eq '000001'
```

**Svar**

```json
{
    "mshr_personnelnumber": "000001",
    "mshr_awarddate": "2015-01-15T00:00:00Z",
    "mshr_awardtype": 200000000,
    "mshr_unitcurrencycode": "USD",
    "mshr_fixedplanid": "",
    "mshr_awardamount": 1,
    "mshr_processtype": 200000003,
    "mshr_typeid": "Bonus",
    "mshr_planid": "MgBonus",
    "mshr_primaryfield": "000001 | MgBonus | Bonus | 1/15/2015",
    "_mshr_fk_employee_id_value": "00000655-0000-0000-adff-004105000000",
    "mshr_payrollvariablecompensationawardentityid": "000001a1-0000-0000-adff-004105000000",
    "_mshr_fk_fixedcomp_id_value": null
}
```

## <a name="see-also"></a>Se även

[Introduktion till API för löneintegrering](hr-admin-integration-payroll-api-introduction.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
