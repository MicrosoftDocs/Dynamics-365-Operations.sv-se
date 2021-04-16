---
title: Färdigheten Rekryteringsbegäran
description: Detta ämne beskriver färdighetsentiteten Rekryteringsbegäran för Dynamics 365 Human Resources.
author: jaredha
ms.date: 02/05/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2021-02-05
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 9e464ced904eb4358ba5d4e1c6c2c36089bfa0d8
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5801321"
---
# <a name="recruiting-request-skill"></a>Färdigheten Rekryteringsbegäran

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Detta ämne beskriver färdighetsentiteten Rekryteringsbegäran för Dynamics 365 Human Resources.

Fysiskt namn: mshr_hcmrecruitingrequestskillentity

### <a name="description"></a>beskrivning

Beskriver färdighetskraven för en RecruitingRequest.

### <a name="json-representation"></a>JSON-representation

```json
{
    "mshr_recruitingrequestid": "String",
    "mshr_skillid": "String",
    "mshr_skilldescription": "String",
    "mshr_ratinglevelid": "String",
    "mshr_ratingmodelid": "String",
    "mshr_ratingleveldescription": "String",
    "mshr_dataareaid": "String",
    "_mshr_dataareaid_id_value": "Guid",
    "mshr_primaryfield": "String",
    "_mshr_fk_recruitingrequest_id_value": "Guid",
    "_mshr_fk_skill_id_value": "Guid",
    "_mshr_fk_ratinglevel_id_value": "Guid",
    "_mshr_fk_ratingmodel_id_value": "Guid",
    "mshr_hcmrecruitingrequestskillentityid": "Guid"
}
```

### <a name="properties"></a>Egenskaper

| Egenskap<br>**Fysiskt namn**<br>**_Typ_** | Använd | beskrivning |
| --- | --- | --- |
| **Entitets-ID för rekryteringsbegäran**<br>mshr_hcmrecruitingrequestskillentityid<br>*GUID* | Skrivskydd<br>Obligatoriskt | Systemgenererad, unik identifierare för posten **Färdigheten Rekryteringsbegäran**. |
| **ID för rekryteringsbegäran**<br>mshr_recruitingrequestid<br>*Sträng* | Skriv en gång<br>Obligatoriskt | Den användarläsbara unika identifieraren för associerad rekryteringsbegäran. |
| **ID-värde för rekryteringsbegäran**<br>_mshr_fk_recruitingrequest_id_value<br>*GUID* | Skrivskydd<br>Obligatoriskt<br> Sekundärnyckel: mshr_hcmrecruitingrequestentityid för entiteten mshr_hcmrecruitingrequestentity | Systemgenererad, unik identifierare för associerad rekryteringsbegäran. |
| **Färdighets-ID**<br>mshr_skillid<br>*Sträng*<br> | Skriv en gång<br>Obligatoriskt | Den användarläsbara, unika identifieraren för erfordrad färdighet. |
| **Värde för färdighets-ID**<br>_mshr_fk_skill_id_value<br>*GUID* | Skrivskydd<br>Obligatoriskt<br>Sekundärnyckel: mshr_hcmskillentityid tillhörande entiteten mshr_hcmskillentity | Systemgenererad, unik identifierare för erfordrad färdighet. |
| **ID för bedömningsnivå**<br>mshr_ratinglevelid<br>*Sträng* | Skriv en gång<br>Valfritt | Det värde på färdighetsnivån som krävs för jobbet, baserat på den bedömningsmodell som färdigheten är tilldelad. |
| **ID-värde för bedömningsnivå**<br>_mshr_fk_ratinglevel_id_value<br>*GUID* | Skrivskydd<br>Valfritt<br>Sekundärnyckel: mshr_hcmratinglevelentityid tillhörande entiteten mshr_hcmratinglevelentity | Systemgenererad, unik identifierare för nivån. |
| **Färdighetsbeskrivning**<br>mshr_skilldescription<br>*Sträng* | Skrivskydd<br>Obligatoriskt | Färdighetsbeskrivningen. |
| **Beskrivning av bedömningsnivå**<br>mshr_ratingleveldescription<br>*Sträng* | Skrivskydd<br>Valfritt | Beskrivningen av den valda färdighetsnivån. |
| **ID för dataområde**<br>mshr_dataareaid<br>*Sträng* | Skrivskydd<br>Valfritt | Anger den juridiska personen (företaget). |
| **ID-värde för dataområde**<br>_mshr_dataareaid_id_value<br>*GUID* | Skrivskydd<br>Valfritt<br>Sekundärnyckel: entiteten cdm_companyid cdm_company | Systemgenererat GUID-värde som identifierar den juridiska personen (företaget). |
| **Primärt fält**<br>mshr_primaryfield<br>*Sträng* | Skrivskydd<br>Obligatoriskt | Sammanslagning av värdet för rekryteringsbegäran och färdighets-ID som en annan metod för att identifiera posten unikt. |
| **ID för bedömningsmodell**<br>mshr_ratingmodelid<br>*Sträng* | Skrivskydd<br>Obligatoriskt | Bedömningsmodellen som används för att gradera färdigheten. |
| **ID-värde för bedömningsmodell**<br>_mshr_fk_hcmratingmodel_id_value<br>*GUID* | Skrivskydd<br>Obligatoriskt<br>Sekundärnyckel: mshr_hcmratingmodelentityid för entiteten mshr_hcmratingmodelentity | Systemgenererad, unik identifierare för bedömningsmodellen som används för att betygssätta färdigheten. |

## <a name="see-also"></a>Se även

[Introduktion av API för integrering av system för sökandespårning](hr-admin-integration-ats-api-introduction.md)<br>
[Exempelfråga för rekryteringsbegäran](hr-admin-integration-ats-api-recruiting-request-example-query.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]