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
ms.openlocfilehash: 05e9d6441cf99dce3f4663b9d5ba57e2b386e8c2f3060f75550270083f3b98b3
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6741463"
---
# <a name="payroll-position"></a>Lönebefattning

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Detta ämne beskriver löneentiteten för befattningar i Dynamics 365 Human Resources.

Fysiskt namn: mshr_payrollpositionentity.

### <a name="description"></a>beskrivning

Denna entitet tillhandahåller befattningsrelaterad information för en given medarbetare.

Fysiskt namn: 

## <a name="properties"></a>Egenskaper

| Egenskap<br>**Fysiskt namn**<br>**_Typ_** | Använd | beskrivning |
| --- | --- | --- |
| **Ordinarie timmar per år**<br>annualregularhours<br>*Decimal* | Skrivskydd<br>Obligatoriskt | Årligt antal regelbundna timmar som definierats för befattningen.  |
| **Entitets-ID för information om löneposition**<br>payrollpositiondetailsentityid<br>*Guid* | Obligatoriskt<br>Systemgenererat. | Ett systemgenererat GUID-värde som unikt identifierar positionen.  |
| **Primärt fält**<br>mshr_primaryfield<br>*Sträng* | Obligatoriskt<br>Systemgenererad |  |
| **ID-värde för befattningsjobb**<br>_mshr_fk_positionjob_id_value<br>*GUID* | Skrivskydd<br>Obligatoriskt<br>Sekundärnyckel:mshr_PayrollPositionJobEntity för mshr_payrollpositionjobentity |ID för det jobb som är kopplat till befattningen.|
| **ID-värde för fast kompensationsplan**<br>_mshr_fk_fixedcompplan_id_value<br>*GUID* | Skrivskydd<br>Obligatoriskt<br>Sekundärnyckel: mshr_FixedCompPlan_id för mshr_payrollfixedcompensationplanentity  | ID för den fasta kompensationsplan som är kopplad till befattningen. |
| **ID för lönecykel**<br>mshr_primaryfield<br>*Sträng* | Skrivskydd<br>Obligatoriskt | Lönecykeln som definieras för befattningen. |
| **Betalas av den juridiska personen**<br>paidbylegalentity<br>*Sträng* | Skrivskydd<br>Obligatoriskt | Den juridiska person som definieras för den befattning som ansvarar för utfärdande av betalning. |
| **Befattnings-ID**<br>mshr_positionid<br>*Sträng* | Skrivskydd<br>Obligatoriskt | Befattningens ID. |
| **Giltig till**<br>validto<br>*Datum Tid Offset* | Skrivskydd<br>Obligatoriskt |Det datum befattningsinformationen gäller från.  |
| **Giltig från**<br>validfrom<br>*Datum Tid Offset* | Skrivskydd<br>Obligatoriskt |Det datum befattningsinformationen gäller till.  |

## <a name="example-query"></a>Exempelfrågeställning

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

## <a name="see-also"></a>Se även

[Introduktion till API för löneintegrering](hr-admin-integration-payroll-api-introduction.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
