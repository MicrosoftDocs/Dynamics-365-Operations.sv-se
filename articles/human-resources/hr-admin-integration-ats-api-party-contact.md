---
title: Partkontakt
description: Detta ämne beskriver entiteten Partkontakt för Dynamics 365 Human Resources.
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
ms.openlocfilehash: b37910f10c0d89e2659aa0bfbdc601c3592f896c
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/18/2021
ms.locfileid: "6053813"
---
# <a name="party-contact"></a>Partkontakt

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Detta ämne beskriver entiteten Partkontakt för Dynamics 365 Human Resources.

Fysiskt namn: mshr_dirpartycontactentities

## <a name="description"></a>beskrivning

Denna entitet beskriver kandidatens kontaktinformation, bland annat telefonnummer, e-postadress och sociala mediakonton.

## <a name="json-representation"></a>JSON-representation

```json
{
    "mshr_partynumber": "String",
    "mshr_locationid": "String",
    "mshr_description": "String",
    "mshr_type": Int,
    "mshr_countryregioncode": "String",
    "mshr_locator": "String",
    "mshr_locatorextension": "String",
    "mshr_purpose": "String",
    "mshr_ismobilephone": Int,
    "mshr_isinstantmessage": Int,
    "mshr_isprimary": Int,
    "mshr_isprivate": Int,
    "mshr_primaryfield": "String",
    "_mshr_fk_person_id_value": "String",
    "mshr_dirpartycontactentityid": "String"
}
```

## <a name="properties"></a>Egenskaper

| Egenskap<br>**Fysiskt namn**<br>**_Typ_** | Använd | beskrivning |
| --- | --- | --- |
| **Entitets-ID för partkontakt**<br>mshr_dirpartycontactentityid<br>*Sträng* | Skrivskydd<br>Obligatoriskt | Systemgenererad, unik identifierare för entitetsposten. |
| **Partnummer**<br>mshr_partynumber<br>*Sträng* | Skrivskydd<br>Obligatoriskt | ID för den associerade partens (personens) post. |
| **Värde för personligt ID**<br>_mshr_fk_person_id_value<br>*GUID* | Skrivskydd<br>Obligatoriskt<br>Sekundärnyckel: mshr_dirpersonentityid för mshr_dirpersonentity | Den systemgenererade, unika identifieraren för entitetsposten för parten (personen). |
| **Plats-id**<br>mshr_locationid<br>*Sträng* | Skrivskydd<br>Obligatoriskt | Plats-ID för adressposten. Konfigurera i entiteten mshr_logisticspostaladdresslocationcdsentity. |
| **Beskrivning**<br>mshr_description<br>*Sträng* | Skrivskydd<br>Obligatoriskt | Beskrivning av kontaktinformationen. |
| **Typ**<br>mshr_type<br>*Alternativuppsättningen mshr_logisticselectronicaddressmethodtype* | Skrivskydd<br>Obligatoriskt | Kontaktinformationstypen. |
| **Lands-/regionkod**<br>mshr_countryregioncode<br>*Sträng* | Skrivskydd<br>Valfritt | Land eller region där adressen finns. |
| **Lokaliserare**<br>mshr_locator<br>*Sträng* | Skrivskydd<br>Valfritt | Kontaktinformationen. Om typen till exempel är **E-postadress** så innehåller detta fält kandidatens e-postadress. |
| **Tillägg för lokaliserare**<br>mshr_locatorextension<br>*Sträng* | Skrivskydd<br>Valfritt | Tillägget för lokaliseraren. Om typen till exempel är **Telefon** innehåller egenskaper telefonnummertillägget. |
| **Är mobil**<br>mshr_ismobile<br>*alternativuppsättningen mshr_noyes* | Skrivskydd<br>Obligatoriskt | Anger huruvida telefonnumret är ett mobilnummer. |
| **Är snabbmeddelande**<br>mshr_isinstantmessage<br>*alternativuppsättningen mshr_noyes* | Skrivskydd<br>Obligatoriskt | Anger huruvida telefonen är aktiverad för snabbmeddelanden. |
| **Är primär**<br>mshr_isprimary<br>*alternativuppsättningen mshr_noyes* | Skrivskydd<br>Obligatoriskt | Avgör den primära kontakten för kontakttypen. Det får bara finnas en primär post per kontakttyp. |
| **Är privat**<br>mshr_isprivate<br>*alternativuppsättningen mshr_noyes* | Skrivskydd<br>Obligatoriskt | Anger om den här adressen är en privat adress för personen. |
| **Syfte**<br>mshr_purpose<br>*Sträng* | Skrivskydd<br>Valfritt | Kontaktinformationens syfte/roll. |
| **Primärt fält**<br>mshr_primaryfield<br>*Sträng* | Skrivskydd<br>Obligatoriskt | Fält som används som primär identifierare för entitetsposten. Kombination av partnummer, typ, beskrivning och lokaliserare. |

## <a name="see-also"></a>Se även

[Introduktion av API för integrering av system för sökandespårning](hr-admin-integration-ats-api-introduction.md)<br>
[Exempelfråga för kandidat att anställa](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]