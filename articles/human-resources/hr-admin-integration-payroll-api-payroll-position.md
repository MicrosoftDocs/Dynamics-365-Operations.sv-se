---
title: Löneuppgifter för Positioner
description: Detta ämne tillhandahåller information och en exempelfrågeställning för entiteten för löneuppgifter för positioner i Dynamics 365 Human Resources.
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
ms.openlocfilehash: 8918044dbf84e79015dc3bca904f204123a37db8
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/18/2021
ms.locfileid: "6056790"
---
# <a name="payroll-position"></a>Lönebefattning

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Detta ämne tillhandahåller information och en exempelfrågeställning för entiteten för löneuppgifter för positioner i Dynamics 365 Human Resources.

## <a name="properties"></a>Egenskaper

| Egenskap<br>**Fysiskt namn**<br>**_Typ_** | Använd | beskrivning |
| --- | --- | --- |
| **Ordinarie timmar per år**<br>annualregularhours<br>*Decimal* | Skrivskydd<br>Obligatoriskt | Årligt antal regelbundna timmar som definierats för befattningen.  |
| **Entitets-ID för information om löneposition**<br>payrollpositiondetailsentityid<br>*Guid* | Obligatoriskt<br>Systemgenererat. | Ett systemgenererat GUID-värde som unikt identifierar positionen.  |
| **Primärt fält**<br>mshr_primaryfield<br>*Sträng* | Obligatoriskt<br>Systemgenererad |  |
| **ID-värde för befattningsjobb**<br>_mshr_fk_positionjob_id_value<br>*GUID* | Skrivskydd<br>Obligatoriskt<br>Sekundärnyckel:mshr_PayrollPositionJobEntity för mshr_payrollpositionjobentity |ID för det jobb som är kopplat till befattningen.|
| **ID-värde för fast kompensationsplan**<br>_mshr_fk_fixedcompplan_id_value<br>*GUID* | Skrivskydd<br>Obligatoriskt<br>Sekundärnyckel: mshr_FixedCompPlan_id för mshr_payrollfixedcompensationplanentity  | ID för den fasta kompensationsplan som är kopplad till befattningen. |
| **ID för lönecykel**<br>mshr_primaryfield<br>*Sträng* | Skrivskydd<br>Obligatoriskt | Lönecykeln som definieras för befattningen. |
| **Betalas av den juridiska personen**<br>paidbylegalentity<br>*Sträng* | Skrivskydd<br>Obligatoriskt | Den juridiska person som definieras i befattningen som ansvarar för utfärdande av betalning. |
| **Befattnings-ID**<br>mshr_positionid<br>*Sträng* | Skrivskydd<br>Obligatoriskt | Befattningens ID. |
| **Giltig till**<br>validto<br>*Datum Tid Offset* | Skrivskydd<br>Obligatoriskt |Det datum befattningsinformationen gäller från.  |
| **Giltig från**<br>validfrom<br>*Datum Tid Offset* | Skrivskydd<br>Obligatoriskt |Det datum befattningsinformationen gäller till.  |

**Fråga**

**Begäran**

```http
GET [Organizaton URI]/api/data/v9.1/mshr_payrollpositionentities?$filter=mshr_positionid eq @positionid and mshr_validfrom le @asofdate and mshr_validto ge @asofdate&@positionid='000276'&@asofdate=2021-04-01
```

**Svar**

```json
{
            "mshr_positionid": "000276",
            "mshr_paycycleid": "w",
            "mshr_annualregularhours": 3000,
            "mshr_paidbylegalentity": "USMF",
            "mshr_validfrom": "2021-03-14T00:00:00Z",
            "mshr_validto": "2154-12-31T00:00:00Z",
            "mshr_primaryfield": "000276 | 3/14/2021",
            "_mshr_fk_job_id_value": "00010094-0000-0000-df00-014105000000",
            "_mshr_fk_fixedcompplan_id_value": "0000029f-0000-0000-d5ff-004105000000",
            "mshr_payrollpositionentityid": "00010097-0000-0000-df00-014105000000"
}
```
