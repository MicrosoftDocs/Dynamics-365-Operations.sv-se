---
title: Personlig utbildning
description: Detta ämne beskriver enheten för personlig utbildning för Dynamics 365 Human Resources.
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
ms.openlocfilehash: b3f3c5a94d7deedd70af0d031c15ecf631dce4d7
ms.sourcegitcommit: 33b5c8bc4f9461e290513aa22de1ec1fba3b0742
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/05/2021
ms.locfileid: "5125339"
---
# <a name="person-education"></a>Personlig utbildning

Detta ämne beskriver enheten för personlig utbildning för Dynamics 365 Human Resources.


Fysiskt namn: mshr_hcmpersoneducationentity

## <a name="description"></a>beskrivning

Denna entitet innehåller utbildningshistoriken för den person som är kandidat. Utbildningen är kopplad till personposten som gör att utbildningen kan kopplas till andra roller som skapats för personen förutom kandidatposten (medarbetare, entreprenör och så vidare).

## <a name="json-representation"></a>JSON-representation

```json
{
    "mshr_creditbasis": Int,
    "mshr_creditscompleted": Decimal,
    "mshr_creditsearned": Decimal,
    "mshr_creditsneeded": Decimal,
    "mshr_description": "String",
    "mshr_duration": Decimal,
    "mshr_durationunit": Int,
    "mshr_educationdisciplineid": "String",
    "mshr_educationinstitutionid": "String",
    "mshr_educationlevelid": "String",
    "mshr_enddate": "Date",
    "mshr_gradepointaverage": Decimal,
    "mshr_gradescale": "String",
    "mshr_notes": "String",
    "mshr_secondaryemphasis": "String",
    "mshr_startdate": "Date",
    "mshr_partynumber": "String",
    "mshr_primaryfield": "String",
    "_mshr_fk_educationdiscipline_id_value": "Guid",
    "_mshr_fk_person_id_value": "Guid",
    "_mshr_fk_educationinstitution_id_value": "Guid",
    "_mshr_fk_educationlevel_id_value": "Guid",
    "mshr_hcmpersoneducationentityid": "Guid"
}
```

## <a name="properties"></a>Egenskaper

| Egenskap<br>**Fysiskt namn**<br>**_Typ_** | Använd | beskrivning |
| --- | --- | --- |
| **Entitets-ID för personlig utbildning**<br>mshr_hcmpersoneducationentityid<br>*GUID* | Skrivskydd<br>Obligatoriskt | Systemgenererad, unik identifierare för entitetsposten för personlig utbildning. |
| **Partnummer**<br>mshr_partynumber<br>*Sträng* | Skrivskydd<br>Obligatoriskt | Den unika identifieraren för partens (personens) post för kandidaten. |
| **Värde för personligt ID**<br>_mshr_fk_person_id_value<br>*GUID* | Skrivskydd<br>Obligatoriskt<br>Sekundärnyckel: mshr_dirpersonentityid för mshr_dirpersonentity | Systemgenererad, unik identifierare för kandidatens personpost. |
| **Kreditbas**<br>mshr_creditbasis<br>*alternativuppsättningen mshr_hcmeducationcreditbasis* | Skrivskydd<br>Valfritt | Kreditbasen för utbildningen. |
| **Slutförda poäng**<br>mshr_creditscompleted<br>*Decimal* | Skrivskydd<br>Valfritt | Det antal akademiska poäng som har slutförts för utbildningen. |
| **Intjänade poäng**<br>mshr_creditsearned<br>*Decimal* | Skrivskydd<br>Valfritt | Det antal poäng som har intjänats för utbildningsposten för en pågående examen. |
| **Erforderliga poäng**<br>mshr_creditsneeded<br>*Decimal* | Skrivskydd<br>Valfritt | Det antal poäng som krävs för en pågående examen. |
| **Beskrivning**<br>mshr_description<br>*Sträng* | Skrivskydd<br>Valfritt | En beskrivning av kandidatens examen. |
| **ID för utbildningsnivå**<br>mshr_educationlevelid<br>*Sträng* | Skrivskydd<br>Valfritt | ID för utbildningsnivån. | 
| **ID-värdet för utbildningsnivån**<br>_mshr_fk_educationlevel_id_value<br>*GUID* | Skrivskydd<br>Valfritt<br>Sekundärnyckel: mshr_hcmeducationdegreeentityid tillhörande entiteten mshr_hcmeducationdegreeentity | Systemgenererad identifierare för posten för utbildningsexamen. Denna identifierare ger de examina- och utbildningsnivåer som definierats för organisationen. |
| **ID för utbildningsdisciplin**<br>mshr_educationdisciplineid<br>*Sträng* | Skrivskydd<br>Obligatoriskt<br>Sekundärnyckel: EducationDiscipline | ID för utbildningsdisciplinen. |
| **ID-värde för utbildningsdisciplin**<br>_mshr_fk_educationdiscipline_id_value<br>*GUID* | Skrivskydd<br>Obligatoriskt<br>Sekundärnyckel: mshr_hcmeducationdegreeentityid tillhörande mshr_hcmeducationdegreeentity | Den systemgenererade, unika identifieraren för utbildningspostens utbildningsdisciplin. |
| **Sekundär tonvikt**<br>mshr_secondaryemphasis<br>*Sträng* | Skrivskydd<br>Valfritt | Den intjänade examens sekundära tonvikt. |
| **ID för utbildningsinstitution**<br>mshr_educationinstitutionid<br>*Sträng* | Skrivskydd<br>Valfritt | ID för besökt utbildningsinstitution. |
| **ID-värde för utbildningsinstitution**<br>_mshr_fk_educationinstitution_id_value<br>*GUID* | Skrivskydd<br>Valfritt<br>Sekundärnyckel: mshr_hcmeducationinstitutionentityid tillhörande mshr_hcmeducationinstitutionentity | Systemgenererad identifierare för utbildningsinstitutionen. |
| **Startdatum**<br>mshr_startdate<br>*Datum/tid* | Skrivskydd<br>Valfritt | Startdatum för utbildningen för den intjänade examen. |
| **Slutdatum**<br>mshr_enddate<br>*Datum/tid* | Skrivskydd<br>Obligatoriskt | Det datum då meriten utfärdades. |
| **Tidslängd**<br>mshr_duration<br>*Decimal* | Skrivskydd<br>Valfritt | Tidslängden för utbildningsposten. |
| **Enhet för tidslängd**<br>mshr_durationunit<br>*alternativuppsättningen mshr_periodunit* | Skrivskydd<br>Valfritt | Den tidsenhet som är kopplad till utbildningspostens varaktighet. |
| **Medelbetyg**<br>mshr_gradepointaverage<br>*Decimal* | Skrivskydd<br>Valfritt | Uppnått poänggenomsnitt för examen. |
| **Betygskala**<br>mshr_gradescale<br>*Sträng* | Skrivskydd<br>Valfritt | Den skala som har använts för betygsgenomsnittet. |
| **Anteckningar**<br>mshr_notes<br>*Sträng* | Skrivskydd<br>Valfritt | Anteckningar att användas av rekryterare eller anställande chef. |
| **Primärt fält**<br>mshr_primaryfield<br>*Sträng* | Skrivskydd<br>Obligatoriskt | Fält som används som ytterligare primär identifierare för entitetsposten. Kombination av partnummer, ID för utbildningsdisciplin, Id för utbildningsinstitution och utbildningsnivå-ID. |

## <a name="see-also"></a>Se även

[Introduktion av API för integrering av system för sökandespårning](hr-admin-integration-ats-api-introduction.md)<br>
[Exempelfråga för kandidat att anställa](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]