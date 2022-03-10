---
title: Personfärdighet
description: Detta ämne beskriver entiteten för Personfärdighet för Dynamics 365 Human Resources.
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
ms.openlocfilehash: c37001c82be34e802835515db86f7ab29e6735bf
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/31/2022
ms.locfileid: "8066278"
---
# <a name="person-skill"></a>Personfärdighet


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Detta ämne beskriver entiteten för Personfärdighet för Dynamics 365 Human Resources.

Fysiskt namn: mshr_hcmpersonskillentity

## <a name="description"></a>beskrivning

Denna entitet beskriver färdigheterna hos en kandidat.

## <a name="json-representation"></a>JSON-representation

```json
{
    "mshr_certifier": "String",
    "mshr_partynumber": "String",
    "mshr_levelid": "String",
    "mshr_ratinglevelexaminer": "String",
    "mshr_skillid": "String",
    "mshr_ratingid": "String",
    "mshr_leveltype": Int,
    "mshr_yearsofexperience": Decimal,
    "mshr_verified": Int,
    "mshr_leveldate": "Date",
    "mshr_primaryfield": "String",
    "_mshr_fk_certifier_id_value": "Guid",
    "_mshr_fk_person_id_value": "Guid",
    "_mshr_fk_ratinglevel_id_value": "Guid",
    "_mshr_fk_ratinglevelexaminer_id_value": "Guid",
    "_mshr_fk_skill_id_value": "Guid",
    "mshr_hcmpersonskillentityid": "Guid"
}
```

## <a name="properties"></a>Egenskaper

| Egenskap<br>**Fysiskt namn**<br>**_Typ_** | Använd | beskrivning |
| --- | --- | --- |
| **Entitets-ID för personfärdighet**<br>mshr_hcmpersonskillentityid<br>*GUID* | Skrivskydd<br>Obligatoriskt | Systemgenererad, unik identifierare för entitetsposten. |
| **Partnummer**<br>mshr_partynumber<br>*Sträng* | Skrivskydd<br>Obligatoriskt |   ID för den associerade partens (personens) post. |
| **Värde för personligt ID**<br>_mshr_fk_person_id_value<br>*GUID* | Skrivskydd<br>Obligatoriskt<br>Sekundärnyckel: mshr_dirpersonentityid för mshr_dirpersonentity | Den systemgenererade, unika identifieraren för entitetsposten för parten (personen). |
| **Certifierare**<br>mshr_certifier<br>*Sträng* | Skrivskydd<br>Valfritt | Personalnumret för den medarbetare som certifierade denna färdighet. |
| **ID-värde för certifierare**<br>_mshr_fk_certifier_id_value<br>*GUID* | Skrivskydd<br>Valfritt<br>Sekundärnyckel: mshr_hcmworkerentityid för mshr_hcmworkerentity | Systemgenererad unik identifierare för arbetarposten för den medarbetare som certifierade färdigheten. |
| **Färdighets-ID**<br>mshr_skillid<br>*Sträng* | Skrivskydd<br>Obligatoriskt | Identifieraren för den färdighet som angetts i Personal. |
| **Värde för färdighets-ID**<br>_mshr_fk_skill_id_value<br>*GUID* | Skrivskydd<br>Obligatoriskt<br>Sekundärnyckel: mshr_hcmskillentityid tillhörande mshr_hcmskillentity | Den systemgenererade, unika identifieraren för vald färdighet. |
| **Erfarenhetsår**<br>mshr_yearsofexperience<br>*Decimal* | Skrivskydd<br>Valfritt | Det antal års erfarenhet som kandidaten har av denna denna färdighet. |
| **Bedömnings-ID**<br>mshr_ratingid<br>*Sträng* | Skrivskydd<br>Obligatoriskt | Bedömningsskaletypen. För denna entitet är värdet **Kompetenser**. |
| **Nivåtyp**<br>mshr_leveltype<br>*alternativuppsättningen mshr_hrmskillleveltype* | Skrivskydd<br>Obligatoriskt | En typkategorisering för den nivå som tilldelats färdigheten. |
| **Nivå-ID**<br>mshr_levelid<br>*Sträng* | Skrivskydd<br>Obligatoriskt | ID:t för bedömningsnivån som kandidaten har för denna färdighet. |
| **ID-värde för bedömningsnivå**<br>_mshr_fk_ratinglevel_id_value<br>*GUID* | Skrivskydd<br>Obligatoriskt<br>Sekundärnyckel: mshr_hcmratinglevelentityid tillhörande mshr_hcmratinglevelentity | Den systemgenererade, unika identifieraren för bedömningsnivån. |
| **Nivådatum**<br>mshr_leveldate<br>*Datum/tid* | Skrivskydd<br>Obligatoriskt | Det datum då kandidaten klassades i färdigheten. |
| **Granskare för bedömningsnivå**<br>mshr_ratinglevelexaminer<br>*Sträng* | Skrivskydd<br>Valfritt | Personalnumret för den medarbetare som bedömt kandidaten. |
| **ID-värde för bedömningsgranskare**<br>_mshr_fk_ratinglevelexaminer_id_value<br>*GUID* | Skrivskydd<br>Valfritt<br>Sekundärnyckel: mshr_hcmworkerentityid för mshr_hcmworkerentity | Den systemgenererade identifieraren för den medarbetare som undersökte kandidatens färdighetsnivå. |
| **Bekräftat**<br>mshr_verified<br>*alternativuppsättningen mshr_noyes* | Skrivskydd<br>Obligatoriskt | Indikerar huruvida den bedömda färdigheten har verifierats. |
| **Primärt fält**<br>mshr_primaryfield<br>*Sträng* | Skrivskydd<br>Obligatoriskt | Fält som används som identifierare för entitetsposten. Kombination av partnummer, nivåtyp, färdighets-ID och nivådatum. |

## <a name="see-also"></a>Se även

[Introduktion av API för integrering av system för sökandespårning](hr-admin-integration-ats-api-introduction.md)<br>
[Exempelfråga för kandidat att anställa](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
