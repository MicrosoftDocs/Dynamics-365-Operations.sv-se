---
title: Utbildning för rekryteringsbegäran
description: Detta ämne beskriver utbildningsentiteten Rekryteringsbegäran för Dynamics 365 Human Resources.
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
ms.openlocfilehash: 9fe1a99debac3dc784ba82b711143337d4077be0
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/31/2022
ms.locfileid: "8067136"
---
# <a name="recruiting-request-education"></a>Utbildning för rekryteringsbegäran


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Detta ämne beskriver utbildningsentiteten Rekryteringsbegäran för Dynamics 365 Human Resources.

Fysiskt namn: mshr_hcmrecruitingrequesteducationentity

### <a name="description"></a>beskrivning

Beskriver utbildningskraven för en RecruitingRequest.

### <a name="json-representation"></a>JSON-representation

```json
{
    "mshr_recruitingrequestid": "String",
    "mshr_educationdisciplineid": "String",
    "mshr_educationdisciplinedescription": "String",
    "mshr_educationlevelid": "String",
    "mshr_educationleveldescription": "String",
    "mshr_dataareaid": "String",
    "_mshr_dataareaid_id_value": "Guid",
    "mshr_primaryfield": "String",
    "_mshr_fk_recruitingrequest_id_value": "Guid",
    "_mshr_fk_educationdiscipline_id_value": "Guid",
    "_mshr_fk_educationlevel_id_value": "Guid",
    "mshr_hcmrecruitingrequesteducationentityid": "Guid"
}
```

### <a name="properties"></a>Egenskaper

| Egenskap<br>**Fysiskt namn**<br>**_Typ_** | Använd | beskrivning |
| --- | --- | --- |
| **Entitets-ID för utbildning för rekryteringsbegäran**<br>mshr_hcmrecruitingrequesteducationentityid<br>*GUID* | Skrivskydd<br>Obligatoriskt | Systemgenererad, unik identifierare för utbildningsposten för rekryteringsbegäran. |
| **ID för rekryteringsbegäran**<br>mshr_recruitingrequestid<br>*Sträng* | Skriv en gång<br>Obligatoriskt | Den användarläsbara unika identifieraren för relaterad rekryteringsbegäran. |
| **ID-värde för rekryteringsbegäran**<br>_mshr_fk_recruitingrequest_id_value<br>*GUID* | Skrivskydd<br>Obligatoriskt<br>Sekundärnyckel: mshr_hcmrecruitingrequestentityid för mshr_hcmrecruitingrequestentity | Systemgenererad, unik identifierare för relaterad rekryteringsbegäran. |
| **ID för utbildningsnivå**<br>mshr_educationlevelid<br>*Sträng* | Skriv en gång<br>Obligatoriskt | Nivå för erforderlig utbildningsnivå. |
| **ID-värde för utbildningsnivå**<br>_mshr_fk_educationlevel_id_value<br>*GUID* | Skrivskydd<br>Obligatoriskt<br>Sekundärnyckel: mshr_hcmratinglevelentityid tillhörande mshr_hcmratinglevelentity | Systemgenererad, unik identifierare för den utbildningsnivå som krävs. |
| **Beskrivning av utbildningsnivå**<br>mshr_educationleveldescription<br>*Sträng* | Skrivskydd<br>Obligatoriskt | Beskrivning av den nivå som krävs för färdigheten. |
| **ID för utbildningsdisciplin**<br>mshr_educationdisciplinedescription<br>*Sträng* | Skriv en gång<br>Obligatoriskt | Utbildningsområdet. |
| **ID-värde för utbildningsdisciplin**<br>_mshr_fk_educationdiscipline_id_value<br>*GUID* | Skrivskydd<br>Obligatoriskt<br>Sekundärnyckel: mshr_hcmeducationdegreeentityid tillhörande mshr_hcmeducationdegreeentity | Systemgenererad, unik identifierare för utbildningsområdet. |
| **Beskrivning av utbildningsområdet**<br>mshr_educationdisciplinedescription<br>Sträng | Skrivskydd<br>Obligatoriskt | Beskrivning av utbildningsområdet. |
| **ID för dataområde**<br>mshr_dataareaid<br>*Sträng* | Skrivskydd<br>Valfritt | Anger den juridiska personen (företaget).|
| **ID-värde för dataområde**<br>_mshr_dataareaid_id_value<br>*GUID* | Skrivskydd<br>Valfritt<br>Sekundärnyckel: entiteten cdm_companyid cdm_company | Systemgenererat GUID-värde som identifierar den juridiska personen (företaget). |
| **Primärt fält**<br>mshr_primaryfield<br>*Sträng* | Skrivskydd<br>Obligatoriskt | Sammanslagning av värdet för rekryteringsbegäran, ID för utbildningsnivå samt ID för utbildningsområde är en annan metod för att identifiera posten unikt. |

## <a name="see-also"></a>Se även

[Introduktion av API för integrering av system för sökandespårning](hr-admin-integration-ats-api-introduction.md)<br>
[Exempelfråga för rekryteringsbegäran](hr-admin-integration-ats-api-recruiting-request-example-query.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
