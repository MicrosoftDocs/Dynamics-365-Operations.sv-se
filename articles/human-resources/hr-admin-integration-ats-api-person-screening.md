---
title: Personkontroller
description: I detta ämne beskrivs kontrollentiteten Person för Dynamics 365 Human Resources.
author: jaredha
ms.date: 02/05/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2021-02-05
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 241b9888624d95bf37a82b6e9b807509818387d2d4f4e5eac67bd67afdaed735
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6782789"
---
# <a name="person-screening"></a>Personkontroller

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

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