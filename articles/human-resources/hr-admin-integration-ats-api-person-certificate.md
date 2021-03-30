---
title: Personcertifikat
description: I detta ämne beskrivs entiteten Personcertifikat för Dynamics 365 Human Resources.
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
ms.openlocfilehash: fa4582dc00341a647f1ea43ed16d9dce8bfcf688
ms.sourcegitcommit: 33b5c8bc4f9461e290513aa22de1ec1fba3b0742
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/05/2021
ms.locfileid: "5125363"
---
# <a name="person-certificate"></a>Personcertifikat

I detta ämne beskrivs entiteten Personcertifikat för Dynamics 365 Human Resources.

Fysiskt namn: mshr_hcmpersoncertificateentity

## <a name="description"></a>beskrivning

Denna entitet beskriver yrkescertifikaten för en kandidat.

## <a name="json-representation"></a>JSON-representation

```json
{
    "mshr_certificatetypeid": "String",
    "mshr_startdate": "Date",
    "mshr_enddate": "Date",
    "mshr_notes": "String",
    "mshr_partynumber": "String",
    "mshr_primaryfield": "String",
    "_mshr_fk_certificatetype_id_value": "Guid",
    "_mshr_fk_person_id_value": "Guid",
    "mshr_hcmpersoncertificateentityid": "Guid"
}
```

## <a name="properties"></a>Egenskaper

| Egenskap<br>**Fysiskt namn**<br>**_Typ_** | Använd | beskrivning |
| --- | --- | --- |
| **Entitets-ID för personcertifikat**<br>mshr_hcmpersoncertificateentityid<br>*GUID* | Skrivskydd<br>Obligatoriskt | Systemgenererad, unik identifierare för entitetsposten för personcertifikat. |
| **Partnummer**<br>mshr_partynumber<br>*Sträng* | Skrivskydd<br>Obligatoriskt | Part-/person-ID för kandidaten. |
| **Värde för personligt ID**<br>_mshr_fk_person_id_value<br>*GUID* | Skrivskydd<br>Obligatoriskt<br>Sekundärnyckel: mshr_dirpersonentityid för mshr_dirpersonentity | Den systemgenererade, unika identifieraren för entitetsposten för parten (personen). |
| **ID för certifikattyp**<br>mshr_certificatetypeid<br>*Sträng* | Skrivskydd<br>Obligatoriskt |  Identifieraren för den certifikattyp som angetts i Personal. |
| **ID-värde för certifikattyp**<br>_mshr_fk_certificatetype_id_value<br>*GUID* | Skrivskydd<br>Obligatoriskt<br>Sekundärnyckel mshr_hcmcertificatetypeentityid för mshr_hcmcertificatetypeentity | Systemgenererad, unik identifierare för certifikattypen i den associerade entiteten. |
| **Startdatum**<br>mshr_startdate<br>*Datum/tid* | Skrivskydd<br>Obligatoriskt | Det datum då certifikatet utfärdades. |
| **Slutdatum**<br>mshr_enddate<br>*Datum/tid* | Skrivskydd<br>Valfritt | Det datum då certifikatet löper ut. |
| **Anteckningar**<br>mshr_notes<br>*Sträng* | Skrivskydd<br>Valfritt | Anteckningar att användas av anställande chefer och rekryterare. |
| **Primärt fält**<br>mshr_primaryfield<br>*Sträng* | Skrivskydd<br>Obligatoriskt |  Fält som används som identifierare för entitetsposten. Kombination av partnummer, ID för certifikattyp samt startdatum. |

## <a name="see-also"></a>Se även

[Introduktion av API för integrering av system för sökandespårning](hr-admin-integration-ats-api-introduction.md)<br>
[Exempelfråga för kandidat att anställa](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]