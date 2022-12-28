---
title: Personkontroller
description: I denna artikel beskrivs kontrollentiteten Person för Dynamics 365 Human Resources.
author: jaredha
ms.date: 12/05/2022
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
ms.openlocfilehash: 3c316e0381f4d407ed7c4c39b5949717b71477bd
ms.sourcegitcommit: 0c927fcb3afd34d870391f05b5393a4673d916e5
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/08/2022
ms.locfileid: "9831901"
---
# <a name="person-screening"></a>Personkontroller


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

I denna artikel beskrivs kontrollentiteten Person för Dynamics 365 Human Resources.

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
    "_mshr_fk_screeningtype_id_value": "Guid",
    "mshr_primaryfield": "String",
    "_mshr_fk_person_id_value": "Guid",
    "mshr_hcmpersonscreeningentityid": "Guid",
    "mshr_completeddate": "Date"
}
```

## <a name="properties"></a>Egenskaper

| Egenskap<br>**Fysiskt namn**<br>**_Typ_** | Använd | beskrivning |
| --- | --- | --- |
| **Anteckningar**<br>mshr_note<br>*Sträng* | Skrivskydd<br>Valfritt | Anteckningar att användas av anställande chefer och rekryterare. |
| **Krävs senast**<br>mshr_requiredby<br>*Datum/tid* | Skrivskydd<br>Valfritt | Det datum då gallringen måste ha genomförts. |
| **Status**<br>mshr_status<br>*alternativuppsättningen mshr_hcmcompletionstatus*|Skrivskydd<br>Obligatoriskt | Anger kandidatens status för gallring. |
| **Partnummer**<br>mshr_partynumber<br>*Sträng* | Skrivskydd<br>Obligatoriskt | Det partnummer (personnummer) som är kopplat till kandidaten. |
| **ID för gallringstyp**<br>mshr_screeningtypeid<br>*Sträng* | Skrivskydd<br>Obligatoriskt<br>Sekundärnyckel: Gallringstyp | Identifieraren för den gallringstyp som angetts i Personal. |
| **ID-värde för gallringstyp**<br>_mshr_fk_screeningtype_id_value<br>*GUID* | Skrivskydd<br>Obligatoriskt<br>Sekundärnyckel: mshr_hcmscreeningtypeentityid för mshr_hcmscreeningtypeentity | Systemgenererad identifierare för gallringstypposten i den associerade entiteten. |
| **Primärt fält**<br>mshr_primaryfield<br>*Sträng* |  Skrivskydd<br>Obligatoriskt | Fält som används som identifierare för entitetsposten. |
| **Värde för personligt ID**<br>_mshr_fk_person_id_value<br>*GUID* | Skrivskydd<br>Obligatoriskt<br>Sekundärnyckel: mshr_dirpersonentityid för mshr_dirpersonentity | Den systemgenererade, unika identifieraren för entitetsposten för parten (personen). |
| **Entitets-ID för persongallring**<br>mshr_hcmpersonscreeningentityid<br>*GUID* | Skrivskydd<br>Obligatoriskt<br>Systemgenererad| Unik, primär identifierare för posten för persongallring. |
| **Slutfört den**<br>mshr_completeddate<br>*Datum/tid* | Skrivskydd<br>Valfritt | Det datum då gallringningen slutfördes. |


## <a name="see-also"></a>Se även

[Introduktion av API för integrering av system för sökandespårning](hr-admin-integration-ats-api-introduction.md)<br>
[Exempelfråga för kandidat att anställa](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
