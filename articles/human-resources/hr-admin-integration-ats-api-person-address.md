---
title: Privat adress
description: Detta ämne beskriver entiteten för privat adress för Dynamics 365 Human Resources.
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
ms.openlocfilehash: 9911362ff8260860864cfe24f0b60f59adb77186
ms.sourcegitcommit: 33b5c8bc4f9461e290513aa22de1ec1fba3b0742
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/05/2021
ms.locfileid: "5125892"
---
# <a name="person-address"></a>Privat adress

Detta ämne beskriver entiteten för privat adress för Dynamics 365 Human Resources.

Fysiskt namn: mshr_hcmpersonaddressentities

## <a name="description"></a>beskrivning

Denna entitet innehåller en lista över postadresser för kandidatposter.

## <a name="json-representation"></a>JSON-representation

```json
{
    "mshr_partynumber": "String",
    "mshr_locationid": "String",
    "mshr_description": "String",
    "mshr_roles": "String",
    "mshr_countryregionid": "String",
    "mshr_zipcode": "String",
    "mshr_street": "String",
    "mshr_city": "String",
    "mshr_state": "String",
    "mshr_county": "String",
    "mshr_isprimary": Int,
    "mshr_isprivate": Int,
    "mshr_primaryfield": "String",
    "_mshr_fk_person_id_value": "Guid",
    "_mshr_fk_countryregion_id_value": "Guid",
    "mshr_hcmpersonaddressentityid": "Guid"
}
```

## <a name="properties"></a>Egenskaper

| Egenskap<br>**Fysiskt namn**<br>**_Typ_** | Använd | beskrivning |
| --- | --- | --- |
| **Entitets-ID för privat adress**<br>mshr_hcmpersonaddressentityid<br>*Sträng* | Skrivskydd<br>Obligatoriskt | Systemgenererad, unik identifierare för entitetsposten. |
| **Partnummer**<br>mshr_partynumber<br>*Sträng* | Skrivskydd<br>Obligatoriskt | ID för den associerade partens (personens) post. |
| **Värde för personligt ID**<br>_mshr_fk_person_id_value<br>*GUID* | Skrivskydd<br>Obligatoriskt<br>Sekundärnyckel: mshr_dirpersonentityid för mshr_dirpersonentity | Den systemgenererade, unika identifieraren för entitetsposten för parten (personen). |
| **Plats-id**<br>mshr_locationid<br>*Sträng* | Skrivskydd<br>Obligatoriskt | Plats-ID för adressposten. Konfigurera i entiteten mshr_logisticspostaladdresslocationcdsentity. |
| **Beskrivning**<br>mshr_description<br>*Sträng* | Skrivskydd<br>Obligatoriskt | En beskrivning av kandidatens adress. |
| **Roller**<br>mshr_roles<br>*Sträng* | Skrivskydd<br>Obligatoriskt | Rollerna som tilldelats den här adressen. Mer än en roll kan tilldelas. Varje enskild roll bör avgränsas med ett semikolon. Giltiga värden som ingår i entiteten mshr_logisticslocationroleentity. |
| **Gata**<br>mshr_street<br>*Sträng* | Skrivskydd<br>Valfritt | Gatunummer. |
| **Ort**<br>mshr_city<br>*Sträng* | Skrivskydd<br>Valfritt | Orten där adressen finns. Ställ in i entiteten mshr_logisticsaddresscityentity. |
| **Delstat**<br>mshr_state<br>*Sträng* | Skrivskydd<br>Valfritt | Delstaten där adressen finns. Ställ in i entiteten mshr_logisticsaddressstateentity. |
| **Region**<br>mshr_county<br>*Sträng* | Skrivskydd<br>Valfritt | Regionen där adressen finns. Ställ in i entiteten mshr_logisticsaddresscountyentity. |
| **Postnummer**<br>mshr_zipcode<br>*Sträng* | Skrivskydd<br>Valfritt | Postnummer för adressen. Ställ in i entiteten mshr_logisticsaddresspostalcodeentity. |
| **ID för land/region**<br>mshr_countryregionid<br>*Sträng* | Skrivskydd<br>Valfritt | Land eller region där adressen finns. |
| **ID-värde för land/region**<br>_mshr_fk_countriregion_id_value<br>*GUID* | Skrivskydd<br>Valfritt<br>Sekundärnyckel: mshr_logisticaddresscountryregionentityid tillhörande mshr_logisticsaddresscountryregionentity | Systemgenererad, unik identifierare för adressens land/region. |
| **Är primär**<br>mshr_isprimary<br>*alternativuppsättningen mshr_noyes* | Skrivskydd<br>Obligatoriskt | Anger huruvida den här adressen är den primära adressen för personen med den definierade rollen. |
| **Är privat**<br>mshr_isprivate<br>*alternativuppsättningen mshr_noyes* | Skrivskydd<br>Obligatoriskt | Anger om den här adressen är en privat adress för personen. |
| **Primärt fält**<br>mshr_primaryfield<br>*Sträng* | Skrivskydd<br>Obligatoriskt | Fält som används som primär identifierare för entitetsposten. Kombination av partnummer och plats-ID. |

## <a name="see-also"></a>Se även

[Introduktion av API för integrering av system för sökandespårning](hr-admin-integration-ats-api-introduction.md)<br>
[Exempelfråga för kandidat att anställa](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)

