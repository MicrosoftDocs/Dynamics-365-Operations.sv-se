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
ms.openlocfilehash: 62b9caf94f1c9aa8bb5758e62565fe57dfdd245a
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/18/2021
ms.locfileid: "6055038"
---
# <a name="payroll-position-job"></a>Lönebefattningsjobb

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Detta ämne tillhandahåller information och en exempelfrågeställning för entiteten för lönebefattningsrelation i Dynamics 365 Human Resources.

## <a name="properties"></a>Egenskaper

| Egenskap<br>**Fysiskt namn**<br>**_Typ_** | Använd | beskrivning |
| --- | --- | --- |
| **Jobb-ID**<br>mshr_jobid<br>*Sträng* | Skrivskyddat<br>Obligatoriskt |Jobbets ID. |
| **Giltig från**<br>mshr_validto<br>*Datum Tid Offset* | Skrivskydd <br>Obligatoriskt | Datum från vilket befattningen och jobbrelationen gäller. |
| **Giltig till**<br>mshr_validto<br>*Datum Tid Offset* | Skrivskydd <br>Obligatoriskt | Datum till och med vilket befattningen och jobbrelationen gäller.  |
| **Befattnings-ID**<br>mshr_positionid<br>*Sträng* | Skrivskydd<br>Obligatoriskt | Befattningens ID. |
| **Primärt fält**<br>mshr_primaryfield<br>*Sträng* | Obligatoriskt<br>Systemgenererad |  |
| **ID-värde för befattningsjobb**<br>_mshr_fk_positionjob_id_value<br>*GUID* | Skrivskydd<br>Obligatoriskt<br>Sekundärnyckel:mshr_PayrollPositionJobEntity för mshr_payrollpositionjobentity |ID för det jobb som är kopplat till befattningen.|
| **ID-värde för fast kompensationsplan**<br>_mshr_fk_fixedcompplan_id_value<br>*GUID* | Skrivskydd<br>Obligatoriskt<br>Sekundärnyckel: mshr_FixedCompPlan_id för mshr_payrollfixedcompensationplanentity  | ID för den fasta kompensationsplan som är kopplad till befattningen. |
| **Entitets-ID för lönebefattningsjobb**<br>mshr_payrollpositionjobentityid<br>*Guid* | Obligatoriskt<br>Systemgenererat. | Ett systemgenererat GUID-värde som unikt identifierar jobbet.  |

