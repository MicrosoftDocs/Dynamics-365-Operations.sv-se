---
title: Bedömningsnivå
description: Detta ämne beskriver entiteten Bedömningsnivå för Dynamics 365 Human Resources.
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
ms.openlocfilehash: dcd366632456c186eca9682d79a0c8690772e8bc
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8893886"
---
# <a name="rating-level"></a>Bedömningsnivå


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Detta ämne beskriver entiteten Bedömningsnivå för Dynamics 365 Human Resources.

Fysiskt namn: mshr_hcmratinglevelentity

## <a name="description"></a>beskrivning

Denna entitet tillhandahåller tillgängliga bedömningsnivåer för färdigheter. Bedömningsnivåerna gäller för alla juridiska personer.

## <a name="json-representation"></a>JSON-representation

```json
{
    "mshr_description": "String",
    "mshr_factor": Int,
    "mshr_note": "String",
    "mshr_ratinglevelid": "String",
    "mshr_ratingmodelid": "String",
    "mshr_primaryfield": "String",
    "_mshr_fk_ratingmodelentity_id_value": "Guid",
    "mshr_hcmratinglevelentityid": "Guid"
}
```

## <a name="properties"></a>Egenskaper

| Egenskap<br>**Fysiskt namn**<br>**_Typ_** | Använd | beskrivning |
| --- | --- | --- |
| **Entitets-ID för bedömningsnivå**<br>mshr_hcmratinglevelentityid<br>*GUID* | Skrivskydd<br>Obligatoriskt<br>Systemgenererad | Systemgenererad, unik identifierare för nivån. |
| **ID för bedömningsnivå**<br>mshr_ratinglevelid<br>*Sträng* | Skrivskydd<br>Obligatoriskt | Användarläsbar, unik identifierare för nivån. |
| **ID för bedömningsmodell**<br>mshr_ratingmodelid<br>*Sträng* | Skrivskydd<br>Obligatoriskt | Bedömningsmodellen som bedömningsnivån tillhör. |
| **Entitets-ID för bedömningsmodell**<br>_mshr_fk_ratingmodelentity_id_value<br>*GUID* | Skrivskydd<br>Obligatoriskt<br>Sekundärnyckel: mshr_hcmratingmodelentityid för mshr_hcmratingmodelentity | Den systemgenererade identifieraren för den bedömningsmodell som bedömningsnivån tillhör. |
| **Beskrivning**<br>mshr_description<br>*Sträng* | Skrivskydd<br>Obligatoriskt | Beskrivningen av bedömningsnivån. |
| **Faktor**<br>mshr_factor<br>*Heltal* | Skrivskydd<br>Obligatoriskt | Faktorn för bedömningsnivån. När du jämför artiklar med olika bedömningsnivåer används faktorn till att normalisera poängen. Värdet måste vara ett heltal mellan 0 och 9. |
| **Obs!**<br>mshr_note<br>*Sträng* | Skrivskydd<br>Valfritt | Eventuella anteckningar som är kopplade till bedömningsnivån. |
| **Primärt fält**<br>mshr_primaryfield<br>*Sträng* | Skrivskydd<br>Obligatoriskt | Fält som används som identifierare för entitetsposten. Kombination av bedömningsnivå-ID och bedömningsmodell-ID. |

## <a name="see-also"></a>Se även

[Introduktion av API för integrering av system för sökandespårning](hr-admin-integration-ats-api-introduction.md)<br>
[Exempelfråga för kandidat att anställa](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
