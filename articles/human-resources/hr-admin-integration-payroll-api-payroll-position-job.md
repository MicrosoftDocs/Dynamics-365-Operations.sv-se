---
title: Lönebefattningsjobb
description: Detta ämne tillhandahåller information och en exempelfrågeställning för entiteten för lönebefattningsjobb i Dynamics 365 Human Resources.
author: jcart
manager: tfehr
ms.date: 04/07/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2021-04-07
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 72f3109f5bea36a390b04b7165fc3831d777b640
ms.sourcegitcommit: d18d9cdb175c9d42eafbed66352c24b2aa94258b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/13/2021
ms.locfileid: "5882080"
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

