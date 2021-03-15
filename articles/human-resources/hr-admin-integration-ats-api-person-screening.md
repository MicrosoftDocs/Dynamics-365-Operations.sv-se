---
title: Personkontroller
description: I detta ämne beskrivs kontrollentiteten Person för Dynamics 365 Human Resources.
author: jaredha
manager: tfehr
ms.date: 02/05/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2021-02-05
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: d76bb57d85ee16f4faa0bb9cfec77047feb7df5f
ms.sourcegitcommit: 33b5c8bc4f9461e290513aa22de1ec1fba3b0742
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/05/2021
ms.locfileid: "5125387"
---
# <a name="person-screening"></a>Personkontroller

I detta ämne beskrivs kontrollentiteten Person för Dynamics 365 Human Resources.

Fysiskt namn: mshr_hcmpersonscreeningentity

## <a name="description"></a>beskrivning

Denna entitet beskriver gallringningar som en kandidat har klarat eller måste klara för anställning.

## <a name="json-representation"></a>JSON-representation

```json
{
    "mshr_note": "String",
    "mshr_requiredby": "Date",
    "mshr_status": Int,
    "mshr_partynumber": "String",
    "mshr_screeningtypeid": "String",
    "mshr_primaryfield": "String",
    "_mshr_fk_person_id_value": "Guid",
    "mshr_hcmpersonscreeningentityid": "Guid",
    "mshr_completeddate": "Date"
}
```

## <a name="properties"></a>Egenskaper

| Egenskap<br>**Fysiskt namn**<br>**_Typ_** | Använd | beskrivning |
| --- | --- | --- |
| **Entitets-ID för persongallring**<br>mshr_hcmpersonscreeningentityid<br>*GUID* | Skrivskydd<br>Obligatoriskt<br>Systemgenererad | Unik, primär identifierare för posten för persongallring. |
| **Partnummer**<br>mshr_partynumber<br>*Sträng* | Skrivskydd<br>Obligatoriskt | Det partnummer (personnummer) som är kopplat till kandidaten. |
| **Värde för personligt ID**<br>_mshr_fk_person_id_value<br>*GUID* | Skrivskydd<br>Obligatoriskt<br>Sekundärnyckel: mshr_dirpersonentityid för mshr_dirpersonentity | Den systemgenererade, unika identifieraren för entitetsposten för parten (personen). |
| **ID för gallringstyp**<br>mshr_screeningtypeid<br>*Sträng* | Skrivskydd<br>Obligatoriskt<br>Sekundärnyckel: Gallringstyp | Identifieraren för den gallringstyp som angetts i Personal. |
| **ID-värde för gallringstyp**<br>_mshr_fk_screeningtype_id_value<br>*GUID* | Skrivskydd<br>Obligatoriskt<br>Sekundärnyckel: mshr_hcmscreeningtypeentityid för mshr_hcmscreeningtypeentity | Systemgenererad identifierare för gallringstypposten i den associerade entiteten. |
| **Krävs senast**<br>mshr_requiredby<br>*Datum/tid* | Skrivskydd<br>Valfritt | Det datum då gallringen måste ha genomförts. |
| **Status**<br>mshr_status<br>*alternativuppsättningen mshr_hcmcompletionstatus*<br>Skrivskydd<br>Obligatoriskt | Anger kandidatens status för gallring. |
| **Slutfört den**<br>mshr_completeddate<br>*Datum/tid* | Skrivskydd<br>Valfritt | Det datum då gallringningen slutfördes. |
| **Anteckningar**<br>mshr_note<br>*Sträng* | Skrivskydd<br>Valfritt | Anteckningar att användas av anställande chefer och rekryterare. |

## <a name="see-also"></a>Se även

[Introduktion av API för integrering av system för sökandespårning](hr-admin-integration-ats-api-introduction.md)<br>
[Exempelfråga för kandidat att anställa](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]