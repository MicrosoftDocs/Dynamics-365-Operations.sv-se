---
title: Plats för rekryteringsbegäran
description: Detta ämne beskriver platsentiteten Rekryteringsbegäran för Dynamics 365 Human Resources.
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
ms.openlocfilehash: f22926292690cb23d9d19cf3887a005b71d44c8d
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5789670"
---
# <a name="recruiting-request-location"></a>Plats för rekryteringsbegäran

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Detta ämne beskriver platsentiteten Rekryteringsbegäran för Dynamics 365 Human Resources.

Fysiskt namn: mshr_hcmrecruitingrequestlocationentity

### <a name="description"></a>beskrivning

Listan med platser som definieras som platser där rekryterade medarbetare ska arbeta vid anställning. Dessa är platser som skapas över flera olika juridiska personer.

### <a name="json-representation"></a>JSON-representation

```
{
    "mshr_recruitingrequestlocationid": "String",
    "mshr_locationid": "String",
    "mshr_description": "String",
    "mshr_countryregionid": "String",
    "mshr_zipcode": "String",
    "mshr_street": "String",
    "mshr_city": "String",
    "mshr_state": "String",
    "mshr_county": "String",
    "mshr_telephone": "String",
    "mshr_email": "String",
    "mshr_internetaddress": "String",
    "_mshr_dataareaid_id_value": "Guid",
    "mshr_dataareaid": "String",
    "_mshr_fk_countryregion_id_value": "Guid",
    "mshr_hcmrecruitingrequestlocationentityid": "Guid"
}
```

### <a name="properties"></a>Egenskaper

| Egenskap<br>**Fysiskt namn**<br>**_Typ_** | Använd | beskrivning |
| --- | --- | --- |
| **Plats-id**<br>mshr_locationid<br>*Sträng* | Skriv en gång<br>Obligatoriskt | Systemgenererad, unik och användarläsbar identifierare för rekryteringsplatsen. |
| **Plats för rekryteringsbegäran**<br>mshr_recruitingrequestlocationid<br>*Sträng* | Skriv en gång<br>Obligatoriskt | Användardefinierad, unik identifierare för rekryteringsplatsen. |
| **Entitets-ID för plats för rekryteringsbegäran**<br>mshr_hcmrecruitingrequestlocationentityid<br>*GUID* | Skrivskydd<br>Obligatoriskt | Systemgenererad, unik identifierare för platsposten för rekryteringsbegäran. |
| **Beskrivning**<br>mshr_description<br>*Sträng* | Skrivskydd<br>Obligatoriskt | Beskrivning av platsen. |
| **ID för land/region**<br>mshr_countryregionid<br>*Sträng* | Skrivskydd<br>Valfritt | Anger det land eller den region som kandidaten är medborgare i. |
| **ID-värde för land/region**<br>_mshr_fk_countriregion_id_value<br>*GUID* | Skrivskydd<br>Valfritt<br>Sekundärnyckel: mshr_logisticaddresscountryregionentityid tillhörande mshr_logisticsaddresscountryregionentity | Systemgenererad, unik identifierare för adressens land/region. |
| **Postnummer**<br>mshr_zipcode<br>*Sträng* | Skrivskydd<br>Valfritt | Postnummer/postkod. |
| **Gata**<br>mshr_street<br>*Sträng* | Skrivskydd<br>Valfritt | Gatuadress. |
| **Ort**<br>mshr_city<br>*Sträng* | Skrivskydd<br>Valfritt | Ort. |
| **Delstat**<br>mshr_state<br>*Sträng* | Skrivskydd<br>Valfritt | Delstat eller region. |
| **Region**<br>mshr_county<br>*Sträng* | Skrivskydd<br>Valfritt | Region. |
| **Telefon**<br>mshr_telephone<br>*Sträng* | Skrivskydd<br>Valfritt | Telefonnummer till platsen. |
| **E-postmeddelande**<br>mshr_email<br>*Sträng* | Skrivskydd<br>Valfritt | E-postadress. |
| **Internet-adress**<br>mshr_internetaddress<br>*Sträng* | Skrivskydd<br>Valfritt | URL för platsens webbplats. |
| **ID för dataområde**<br>mshr_dataareaid<br>*Sträng* | Skrivskydd<br>Valfritt | Anger den juridiska personen (företaget). |
| **ID-värde för dataområde**<br>_mshr_dataareaid_id_value<br>*GUID* | Skrivskydd<br>Valfritt<br>Sekundärnyckel: entiteten cdm_companyid cdm_company | Systemgenererat GUID-värde som identifierar den juridiska personen (företaget). |

## <a name="see-also"></a>Se även

[Introduktion av API för integrering av system för sökandespårning](hr-admin-integration-ats-api-introduction.md)<br>
[Exempelfråga för rekryteringsbegäran](hr-admin-integration-ats-api-recruiting-request-example-query.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]