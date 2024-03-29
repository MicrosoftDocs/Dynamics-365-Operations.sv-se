---
title: Personlig yrkeserfarenhet
description: Detta ämne beskriver entiteten för personlig yrkeserfarenhet för Dynamics 365 Human Resources.
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
ms.openlocfilehash: d306213e4c647ecd4be98598cba92376aba0d5bb
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8856437"
---
# <a name="person-professional-experience"></a>Personlig yrkeserfarenhet


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Detta ämne beskriver entiteten för personlig yrkeserfarenhet för Dynamics 365 Human Resources.

Fysiskt namn: mshr_hcmpersonprofessionalexperienceentity

## <a name="description"></a>beskrivning

Denna entitet beskriver yrkeserfarenhet eller arbetshistorik för en kandidat.

## <a name="json-representation"></a>JSON-representation

```json
{
    "mshr_partynumber": "String",
    "mshr_employerposition": "String",
    "mshr_startdate": "Date",
    "mshr_allowcontactemployer": Int,
    "mshr_employerlocation": "String",
    "mshr_employername": "String",
    "mshr_enddate": "Date",
    "mshr_note": "String",
    "mshr_phone": "String",
    "mshr_url": "String",
    "mshr_primaryfield": "String",
    "_mshr_fk_person_id_value": "Guid",
    "mshr_hcmpersonprofessionalexperienceentityid": "Guid"
}
```

## <a name="properties"></a>Egenskaper

| Egenskap<br>**Fysiskt namn**<br>**_Typ_** | Använd | beskrivning |
| --- | --- | --- |
| **Entitets-ID för personlig yrkeserfarenhet**<br>mshr_hcmpersonprofessionalexperienceentityid<br>*GUID* | Skrivskydd<br>Obligatoriskt | Systemgenererad, unik identifierare för entitetsposten. |
| **Partnummer**<br>mshr_partynumber<br>*Sträng* | Skrivskydd<br>Obligatoriskt | Unik identifierare för personens post för kandidaten. |
| **Värde för personligt ID**<br>_mshr_fk_person_id_value<br>*GUID* | Skrivskydd<br>Obligatoriskt<br>Sekundärnyckel: mshr_dirpersonentityid för mshr_dirpersonentity | Systemgenererad, unik identifierare för entitetsposten för person. |
| **Arbetsgivarens befattning**<br>mshr_employerposition<br>*Sträng* | Skrivskydd<br>Obligatoriskt | Befattningstitel för kandidaten när han eller hon är under anställning. |
| **Namn på arbetsgivare**<br>mshr_employername<br>*Sträng* | Skrivskydd<br>Obligatoriskt | Namnet på arbetsgivaren. |
| **Arbetsgivarens plats**<br>mshr_employerlocation<br>*Sträng* | Skrivskydd<br>Valfritt | Arbetsgivarens plats. Maxlängd = 60. Inget specifikt format har definierats eller krävs. |
| **Telefon**<br>mshr_phone<br>*Sträng* | Skrivskydd<br>Valfritt | Arbetsgivarens telefonnummer. |
| **URL**<br>mshr_url<br>*Sträng* | Skrivskydd<br>Valfritt | Webbadressen (URL) till arbetsgivarens webbplats. |
| **Startdatum**<br>mshr_startdate<br>*Datum/tid* | Skrivskydd<br>Obligatoriskt | Startdatumet för kandidatens anställning. |
| **Slutdatum**<br>mshr_enddate<br>*Datum/tid* | Skrivskydd<br>Valfritt | Slutdatumet för kandidatens anställning, eller null om kandidaten fortfarande är anställd här. |
| **Tillåt kontakt med arbetsgivare**<br>mshr_allowcontactemployer<br>*Alternativuppsättningen mshr_hrmblankyesno* | Skrivskydd<br>Valfritt | Anger om kandidaten tillåter att den föregående arbetsgivaren kontaktas. |
| **Anteckningar**<br>mshr_note<br>*Sträng* | Skrivskydd<br>Valfritt | Anteckningar att användas av rekryterare eller anställande chef. |
| **Primärt fält**<br>mshr_primaryfield<br>*Sträng* | Skrivskydd<br>Obligatoriskt | Fält som används som primär identifierare för entitetsposten. Kombination av partnummer, startdatum, arbetsgivarens befattning och arbetsgivarens namn. |

## <a name="see-also"></a>Se även

[Introduktion av API för integrering av system för sökandespårning](hr-admin-integration-ats-api-introduction.md)<br>
[Exempelfråga för kandidat att anställa](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
