---
title: Persondientifieringsnummer
description: Detta ämne beskriver entiteten för persondientifieringsnummer för Dynamics 365 Human Resources.
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
ms.openlocfilehash: 223f7537dfb5f87e590e74888228ce703a3454d7e33fbd31b6b9a6915884fa4a
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6748115"
---
# <a name="person-identification-number"></a>Persondientifieringsnummer

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Detta ämne beskriver entiteten för persondientifieringsnummer för Dynamics 365 Human Resources.

Fysiskt namn: mshr_hcmpersonidentificationnumberentity

## <a name="description"></a>beskrivning

Denna entitet beskriver kandidatens identifieringsnummer. Det gör det möjligt för API-kunden att skriva ID-nummer, exempelvis socialförsäkrings-/personnummer eller passnummer, till sökandeposten. Identifieringsnummer visas på medarbetarposten, men inte på sökandeposten. Ett integrationsprogram kan skriva värden till Personal-databasen, men värdena syns inte i Personal förrän kandidatens medarbetarpost har skapats.

## <a name="json-representation"></a>JSON-representation

```json
{
    "mshr_entrytype": "String",
    "mshr_description": "String",
    "mshr_expirationdate": "Datetime",
    "mshr_isprimary": Int,
    "mshr_identificationnumber": "String",
    "mshr_partynumber": "String",
    "mshr_identificationtypeid": "String",
    "mshr_issuingagencyid": "String",
    "mshr_primaryfield": "String",
    "_mshr_fk_person_id_value": "Guid",
    "_mshr_fk_issuingagency_id_value": "Guid",
    "_mshr_fk_identificationtype_id_value": "Guid",
    "mshr_hcmpersonidentificationnumberentityid": "Guid",
    "mshr_issueddate": "Datetime"
}
```

## <a name="properties"></a>Egenskaper

| Egenskap<br>**Fysiskt namn**<br>**_Typ_** | Använd | beskrivning |
| --- | --- | --- |
| **Entitetsvärde för Personidentifieringsnummer**<br>mshr_hcmpersonidentificationnumberentityid<br>*GUID* | Skrivskydd<br>Obligatoriskt<br>Systemgenererad | Unik primär identifierare för nummerposten för personidentifiering. |
| **Inmatningstyp**<br>mshr_entrytype<br>*Sträng* | Skrivskydd<br>Valfritt | Frivärde som referens till inmatningstypen för identifieringsnumret. |
| **Beskrivning**<br>mshr_description<br>*Sträng* | Skrivskydd<br>Valfritt | Beskrivningen av ID-numret. |
| **Utgångsdatum**<br>mshr_expirationdate<br>*Datum/tid* | Skrivskydd<br>Valfritt | Det datum då identifieringsnumret eller det kopplade dokumentet upphör att gälla. |
| **Är primär**<br>mshr_isprimary<br>*alternativuppsättningen mshr_noyes* | Skrivskydd<br>Valfritt | Anger huruvida identifieringsnumret är den primära posten för personen för den här identifieringstypen. |
| **ID-nummer**<br>mshr_identificationnumber<br>*Sträng* | Skrivskydd<br>Obligatoriskt | ID-numret. |
| **Partnummer**<br>mshr_partynumber<br>*Sträng* | Skrivskydd<br>Obligatoriskt | Identifieraren för parten (personen) som äger indentifieringsnumret. |
| **Värde för personligt ID**<br>_mshr_fk_person_id_value<br>*GUID* | Skrivskydd<br>Obligatoriskt<br>Sekundärnyckel: mshr_dirpersonentityid tillhörande entiteten mshr_dirpersonentity | Den unika identifieraren för parten (personen). |
| **ID för identifieringstyp**<br>mshr_identificationtypeid<br>*Sträng* | Skrivskydd<br>Obligatoriskt | Identifieringsnumrets typ. |
| **ID-värde för identifieringstyp**<br>_mshr_fk_identificationtype_id_value<br>*GUID* | Skrivskydd<br>Obligatoriskt<br>Sekundärnyckel: mshr_hcmidentificationtypeentityid tillhörande entiteten mshr_hcmidentificationtypeentity | Systemgenererad, unik identifierare för identifieringstypen. |
| **ID för utfärdande organ**<br>mshr_issuingagencyid<br>*Sträng* | Skrivskydd<br>Valfritt | Det organ eller den organisation som utfärdar identifieringsnumret. |
| **ID-värde för utfärdande organ**<br>_mshr_fk_issuingagency_id_value<br>*GUID* | Skrivskydd<br>Valfritt<br>Sekundärnyckel: mshr_hcmissuingagencyentityid tillhörande entiteten mshr_hcmissuingagencyentity | Systemgenererad, unik identifierare för det organ som utfärdar identifieringsnumret. |
| **Primärt fält**<br>mshr_primaryfield<br>*Sträng* | Skrivskydd<br>Obligatoriskt | Fält som används som identifierare för entitetsposten. Kombination av partnummer, identifieringstyps-ID och identifieringsnummer. |
| **Utfärdandedatum**<br>mshr_issuedate<br>*Datum* | Skrivskydd<br>Valfritt | Det datum då identifieringsnumret utfärdades. |

## <a name="see-also"></a>Se även

[Introduktion av API för integrering av system för sökandespårning](hr-admin-integration-ats-api-introduction.md)<br>
[Exempelfråga för kandidat att anställa](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]