---
title: Kandidat att anställa
description: Detta ämne beskriver entiteten Kandidat att anställa för Dynamics 365 Human Resources.
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
ms.openlocfilehash: eb16f9f46e3f5c58854ec06c3b89ec72dd7bae00
ms.sourcegitcommit: 33b5c8bc4f9461e290513aa22de1ec1fba3b0742
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/05/2021
ms.locfileid: "5125747"
---
# <a name="candidate-to-hire"></a>Kandidat att anställa

Detta ämne beskriver entiteten Kandidat att anställa för Dynamics 365 Human Resources.

Fysiskt namn: mshr_hcmcandidatetohireentity

## <a name="description"></a>beskrivning

Denna entitet tillhandahåller kandidatinformation som används för att skapa en medarbetare i Dynamics 365 Human Resources. Den används för att läsa alla kandidatposter och skapa interna och externa poster för kandidaten, så att du kan skapa personlig information om den nya kandidaten.

När du skapar en post för extern kandidat som ska bli en ny personpost i systemet, får du inte ange ett partnummer (person) när du bokför en ny kandidatpost. Entitetsposten för ny person skapas med den nya kandidatposten.

När du skapar en intern post för en kandidat (en kandidat till befattningen som redan har en medarbetarpost i företaget) ska du definiera partnumret för posten som redan finns för person för mshr_partynumber-egenskapen i kandidatposten i stället för att definiera personlig information (t.ex. namn, kön eller födelsedatum) som kan användas för att skapa en ny personpost.

## <a name="json-representation"></a>JSON-representation

```json
        {
            "mshr_candidateid": "String",
            "mshr_partynumber": "String",
            "mshr_partytype": "String",
            "mshr_recruitingrequestid": "String",
            "mshr_positionid": "String",
            "mshr_firstname": "String",
            "mshr_middlename": "String",
            "mshr_lastnameprefix": "String",
            "mshr_lastname": "String",
            "mshr_gender": Int,
            "mshr_birthdate": "Date",
            "mshr_citizenshipcountrycode": "String",
            "mshr_veteranstatusid": "String",
            "mshr_isdisabledveteran": Int,
            "mshr_availabilitydate": "Date",
            "mshr_iswillingtorelocate": Int,
            "mshr_comments": "String",
            "mshr_applicantintegrationresult": Int,
            "mshr_donothirereasoncodeid": "String",
            "mshr_dataareaid": "String",
            "_mshr_dataareaid_id_value": "Guid",
            "_mshr_fk_person_id_value": "Guid",
            "_mshr_fk_recruitingrequest_id_value": "Guid",
            "_mshr_fk_position_id_value": "Guid",
            "mshr_hcmcandidatetohireentityid": "Guid",
            "_mshr_fk_veteranstatus_id_value": "Guid",
            "_mshr_fk_reasoncode_id_value": "Guid",
            "mshr_militaryserviceenddate": "Guid",
            "mshr_militaryservicestartdate": "Guid"
        }
```

## <a name="properties"></a>Egenskaper

| Egenskap<br>**Fysiskt namn**<br>**_Typ_** | Använd | beskrivning |
| --- | --- | --- |
| **Entitets-ID för Kandidat att anställa**<br>mshr_hcmcandidatetohireentityid<br>GUID | Skrivskydd<br>Obligatoriskt<br>Systemgenererad | En systemgenererad unik identifierare för entitetsposten. |
| **Kandidat-ID**<br>mshr_candidateid<br>Sträng | Skrivskydd<br>Obligatoriskt<br>Systemgenererad | En unik identifierare för entiteten. |
| **Partnummer**<br>mshr_partynumber<br>Sträng | Skrivskydd<br>Obligatoriskt | Partnumret (personnumret) för kandidatens personpost. |
| **Värde för personligt ID**<br>_mshr_fk_person_id_value<br>GUID | Skrivskydd<br>Obligatoriskt<br>Sekundärnyckel: mshr_dirpersonentityid för mshr_direpersonentity | Den systemgenererade, unika identifieraren för partens (personens) post för kandidaten. |
| **Parttyp**<br>mshr_partytype<br>alternativuppsättningen mshr_dirpartytype | Skrivskydd<br>Obligatoriskt | Partstypen för posten, enligt vad som angetts i alternativuppsättningen mshr_dirpartytype. För denna entitet är typen alltid "Person". |
| **ID för rekryteringsbegäran**<br>mshr_recruitingrequestid<br>Sträng | Skriv en gång<br>Valfritt | Referenser till den rekryteringsbegäran som denna kandidat uppfyller. |
| **ID-värde för rekryteringsbegäran**<br>_mshr_fk_recruitingrequest_id_value<br>GUID | Skrivskydd<br>Valfritt<br>Sekundärnyckel: mshr_hcmrecruitingrequestentityid för mshr_hcmrecruitingrequestentity | Den systemgenererade, unika identifieraren för den rekryteringsbegäran som kandidaten uppfyller. |
| **Befattnings-ID**<br>mshr_positionid<br>Sträng | Skrivskydd<br>Valfritt | ID för befattningen som kandidaten behandlas för. |
| **ID-värde för befattning**<br>_mshr_fk_position_if_value<br>GUID | Skrivskydd<br>Valfritt<br>Sekundärnyckel: mshr_hcmpositionv2entityid för mshr_hcmpositionv2entity | Systemgenererad identifierare för den befattning som kandidaten övervägs för. |
| **Förnamn**<br>mshr_firstname<br>Sträng | Skrivskydd<br>Obligatoriskt | Kandidatens förnamn. |
| **Mellannamn**<br>mshr_middlename<br>Sträng | Skrivskydd<br>Valfritt | Sökandes mellannamn. |
| **Prefix för efternamn**<br>mshr_lastnameprefix<br>Sträng | Skrivskydd<br>Valfritt | Prefix för sökandes efternamn. |
| **Efternamn**<br>mshr_lastname<br>Sträng | Skrivskydd<br>Valfritt | Kandidatens efternamn. |
| **Kön**<br>mshr_gender<br>alternativuppsättningen mshr_hcmpersongender | Skrivskydd<br>Valfritt | Kandidatens kön. |
| **Födelsedatum**<br>mshr_birthdate<br>DatumTid | Skrivskydd<br>Valfritt | Kandidatens födelsedatum. |
| **Landskod för medborgarskap**<br>mshr_citizenshipcountrycode<br>Sträng | Skrivskydd<br>Valfritt | Anger det land som kandidaten är medborgare i. Giltiga landskoder finns i mshr_logisticaddresscountryregionentity. |
| **ID för veteranstatus**<br>mshr_veteranstatusid<br>Sträng | Skrivskydd<br>Valfritt | Visar veteranstatusen för kandidaten. |
| **ID-värde för veteranstatus**<br>_mshr_fk_veteranstatus_id_value<br>GUID | Skrivskydd<br>Valfritt<br>Sekundärnyckel: mshr_hcmveteranstatusentityid för mshr_hcmveteranstatusentity | Systemgenererad unik identifierare för entitetsposten för veteranstatus. |
| **Startdatum för militärtjänstgöring**<br>mshr_militaryservicestartdate<br>DatumTid | Skrivskydd<br>Valfritt | Startdatumet för kandidatens militärtjänst. |
| **Slutdatum för militärtjänstgöring**<br>mshr_militaryserviceenddate<br>DatumTid | Skrivskydd<br>Valfritt | Slutdatumet för kandidatens militärtjänst. |
| **Är veteran med funktionshinder**<br>mshr_isdisabledveteran<br>alternativuppsättningen mshr_noyes | Skrivskydd<br>Valfritt | Anger om kandidaten innehar status som veteran med handikapp. |
| **Tillgänglighetsdatum**<br>mshr_availabilitydate<br>DatumTid | Skrivskydd<br>Valfritt | Det tidigaste datum då kandidaten skulle vara tillgänglig för att arbeta. |
| **Är villig att flytta**<br>mshr_iswillingtorelocate<br>alternativuppsättningen mshr_noyes | Skrivskydd<br>Valfritt | Anger om kandidaten är villig att flytta för befattningens skull. |
| **Kommentarer**<br>mshr_comments<br>Sträng | Skrivskydd<br>Valfritt | Kommentarer som ska användas av rekryteraren eller anställande chef. |
| **Resultat för ansökningsintegrering**<br>mshr_applcantintegrationresult<br>alternativuppsättningen mshr_applicantintegrationresult | Skrivskydd<br>Obligatoriskt | Status för kandidaten i anställningsprocessen relaterad till integreringen. |
| **Orsakskod-ID för Anställ inte**<br>mshr_donothirereasoncodeid<br>Sträng | Skrivskydd<br>Valfritt | En orsakskod kan också anges när statusen (resultat av ansökningsintegrering) är inställd på "Ej anställd". |
| **ID-värde för orsakskod**<br>_mshr_fk_reasoncode_id_value<br>GUID | Skrivskydd<br>Valfritt<br>Sekundärnyckel: mshr_hcmreasoncodeentityid tillhörande entiteten mshr_hcmreasoncodeentity | Systemgenererad unik identifierare för orsakskoden **Anställ inte**. |
| **ID för dataområde**<br>mshr_dataareaid<br>Sträng | Skrivskydd<br>Valfritt |  Anger den juridiska personen (företaget). |
| **ID-värde för dataområde**<br>_mshr_dataareaid_id_value<br>GUID | Skrivskydd<br>Valfritt<br>Sekundärnyckel: entiteten cdm_companyid cdm_company | Systemgenererat GUID-värde som identifierar den juridiska personen (företaget). |

## <a name="see-also"></a>Se även

[Introduktion av API för integrering av system för sökandespårning](hr-admin-integration-ats-api-introduction.md)<br>
[Exempelfråga för kandidat att anställa](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]