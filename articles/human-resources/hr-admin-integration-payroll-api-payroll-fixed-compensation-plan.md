---
title: Kompensationsplan med fast lön
description: Detta ämne tillhandahåller information och en exempelfrågeställning för lönelistaentiteten för fast kompensationsplan i Dynamics 365 Human Resources.
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
ms.openlocfilehash: f1e5345d9f27106bdf3a3a60cb0480a9b072e340c01236e4d48c5e2ae592ddbd
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6738401"
---
# <a name="payroll-fixed-compensation-plan"></a>Kompensationsplan med fast lön

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Detta ämne beskriver lönelisteentiteten för fast kompensationsplan i Dynamics 365 Human Resources.

### <a name="description"></a>beskrivning

Denna entitet tillhandahåller den fasta kompensationsplan som tilldelats för en viss befattning för en medarbetare.

Fysiskt namn: mshr_payrollfixedcompensationplanentity.

## <a name="properties"></a>Egenskaper

| Egenskap<br>**Fysiskt namn**<br>**_Typ_** | Använd | beskrivning |
| --- | --- | --- |
| **Medarbetarens ID**<br>mshr_fk_employee_id_value<br>*GUID* | Skrivskydd<br>Obligatoriskt<br>Sekundärnyckel: mshr_Employee_id för entiteten mshr_payrollemployeeentity  | Medarbetarens ID |
| **Lönesats**<br>mshr_payrate<br>*Decimal* | Skrivskydd<br>Obligatoriskt | Lönesats som definieras i den fasta kompensationsplanen. |
| **Plan-ID**<br>mshr_planid<br>*Sträng* | Skrivskydd<br>Obligatoriskt |Anger kompensationsplanen.  |
| **Giltig från**<br>mshr_validfrom<br>*Datum Tid Offset* |  Skrivskydd<br>Obligatoriskt |Det datum då medarbetarens fasta kompensation börjar gälla.  |
| **Lönelisteentiteten för fast kompensation**<br>mshr_payrollfixedcompensationplanentityid<br>*GUID* | Obligatoriskt<br>Systemgenererad | Ett systemgenererat GUID-värde som ger kompensationsplanen ett unikt ID. |
| **Lönefrekvens**<br>mshr_payfrequency<br>*Sträng* | Skrivskydd<br>Obligatoriskt |Den frekvens som medarbetaren ska betalas.  |
| **Giltig till**<br>mshr_validto<br>*Datum Tid Offset* | Skrivskydd <br>Obligatoriskt | Det datum då medarbetarens fasta kompensation slutar gälla. |
| **Befattnings-ID**<br>mshr_positionid<br>*Sträng* | Skrivskydd <br>Obligatoriskt | Positions-ID som är kopplat till medarbetaren samt registrering för fast kompensationsplan. |
| **Valuta**<br>mshr_currency<br>*Sträng* | Skrivskydd <br>Obligatoriskt |Den valuta som har definierats för den fasta kompensationsplanen   |
| **Personalnummer**<br>mshr_personnelnumber<br>*Sträng* | Skrivskydd<br>Obligatoriskt |Medarbetarens unika personalnummer.  |

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
