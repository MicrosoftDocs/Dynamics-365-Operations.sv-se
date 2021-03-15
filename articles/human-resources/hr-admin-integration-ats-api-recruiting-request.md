---
title: Rekryteringsbegäran
description: Detta ämne beskriver entiteten Rekryteringsbegäran för Dynamics 365 Human Resources.
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
ms.openlocfilehash: 572ee0755e331d19b41442e3614effb92db95a92
ms.sourcegitcommit: 33b5c8bc4f9461e290513aa22de1ec1fba3b0742
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/05/2021
ms.locfileid: "5125435"
---
# <a name="recruiting-request"></a>Rekryteringsbegäran

Detta ämne beskriver entiteten Rekryteringsbegäran för Dynamics 365 Human Resources.

Fysiskt namn: mshr_hcmrecruitingrequestentity

### <a name="description"></a>beskrivning

Beskriver en rekryteringsbegäran för ett jobb.

### <a name="json-representation"></a>JSON-representation

```json
{
    "mshr_recruitingrequestid": "String",
    "mshr_hiringmanagerpersonnelnumber": "String",
    "mshr_recruiterpartynumber": "String",
    "mshr_status": Int,
    "mshr_description": "String",
    "mshr_recruitingrequestlocationid": "String",
    "mshr_comments": "String",
    "mshr_jobid": "String",
    "mshr_titleid": "String",
    "mshr_jobfunctionid": "String",
    "mshr_defaultfulltimeequivalency": Decimal,
    "mshr_regulatoryjobcategory": Int,
    "mshr_jobtypeid": "String",
    "mshr_exemptstatus": Int,
    "mshr_estimatedstartdate": "Date",
    "mshr_externaldescription": "String",
    "mshr_compensationlevelid": "String",
    "mshr_compensationlowthreshold": Decimal,
    "mshr_compensationcontrolpoint": Decimal,
    "mshr_compensationhighthreshold": Decimal,
    "mshr_dataareaid": "String",
    "_mshr_dataareaid_id_value": "Guid",
    "_mshr_fk_hiringmanager_id_value": "Guid",
    "_mshr_fk_recruiter_id_value": "Guid",
    "_mshr_fk_job_id_value": "Guid",
    "_mshr_fk_title_id_value": "Guid",
    "_mshr_fk_jobtype_id_value": "Guid",
    "_mshr_fk_compensationlevel_id_value": "Guid",
    "mshr_hcmrecruitingrequestentityid": "Guid",
    "_mshr_fk_recruitingrequestlocation_id_value": “Guid”
}
```

### <a name="properties"></a>Egenskaper

| Egenskap<br>**Fysiskt namn**<br>**_Typ_** | Använd | beskrivning |
| --- | --- | --- |
| **ID för rekryteringsbegäran**<br>mshr_recruitingrequestid<br>*Sträng* | Skrivskydd<br>Obligatoriskt<br>Systemgenererad | En användarläsbar, unik identifierare för den begäran som visas i personalansökningen. Nummerserie. |
| **Entitets-ID för rekryteringsbegäran**<br>mshr_hcmrecruitingrequestentityid<br>*GUID* | Skrivskydd<br>Obligatoriskt<br>Systemgenererad | Ett systemgenererat GUID-värde som unikt identifierar rekryteringsbegäran. |
| **ID för dataområde**<br>mshr_dataareaid<br>*Sträng* | Skrivskydd<br>Valfritt<br> | Anger den juridiska personen (företaget) för rekryteringsbegäran. |
| **ID-värde för dataområde**<br>_mshr_dataareaid_id_value<br>*GUID*<br> | Skrivskydd<br>Valfritt<br>Sekundärnyckel: entiteten cdm_companyid cdm_company | Systemgenererat GUID-värde som identifierar den juridiska personen (företaget) för rekryteringsbegäran. |
| **Anställningsnummer för anställande chef**<br>mshr_hiringmanagerpersonnelnumber<br>*Sträng* | Skrivskydd<br>Valfritt | Personalnumret för den anställningsansvarig som är kopplad till denna rekryteringsbegäran. |
| **ID-värde för anställande chef**<br>_mshr_fk_hiringmanager_id_value<br>*GUID* | Skrivskydd<br>Valfritt<br>Sekundärnyckel: mshr_hcmworkerbaseentityid tillhörande entiteten mshr_hcmworkerbaseentity | Systemgenererat GUID-värde för att identifiera chefen som är associerad med rekryteringsbegäran. |
| **Partnummer för rekryterare**<br>mshr_recruiterpartynumber<br>*Sträng* | Skrivskydd<br>Valfritt | Personnummert (partnummer) för den rekryterare som valts för begäran. |
| **ID-värde för rekryterare**<br>_mshr_fk_recruiter_id_value<br>*GUID* | Skrivskydd<br>Valfritt<br>Sekundärnyckel: mshr_dirpersonentityid tillhörande entiteten mshr_dirpersonentity | Systemgenererat GUID-värde för att identifiera den rekryterare som är associerad med rekryteringsbegäran. |
| **Status**<br>mshr_status<br>Alternativuppsättningen *RekryteringRequestStatus* | Skrivskydd<br>Obligatoriskt<br> | Visar statusen för rekryteringsbegäran. |
| **Beskrivning**<br>mshr_description<br>*Sträng* | Skrivskydd<br>Obligatoriskt | Beskriver begäran. |
| **Plats-ID för rekryteringsbegäran**<br>mshr_recruitingrequestlocationid<br>*Sträng* | Skrivskydd<br>Valfritt | Det användarläsbara unika ID:t för jobbplatsen som hör till denna begäran. |
| **ID-värde för rekryteringsplats**<br>_mshr_fk_recruitinglocation_id_value<br>*GUID* | Skrivskydd<br>Valfritt<br>Sekundärnyckel: entiteten mshr_hcmrecruitingrequestlocationentityid of mshr_hcmrecruitingrequestlocationentity | Systemgenererat GUID-värde för att identifiera den plats för rekryteringsbegäran som valts för begäran. |
| **Kommentarer**<br>mshr_comments<br>*Sträng* | Skrivskydd<br>Valfritt | Kommentarer om begäran (att användas av anställande chefer och rekryterare). |
| **Jobb-ID**<br>mshr_jobid<br>*Sträng* | Skriv en gång<br>Obligatoriskt |   Det användarläsbara unika ID:t för jobbet som delas av samtliga befattningar associerade med denna begäran. |
| **ID-värde för jobb**<br>_mshr_fk_job_id_value<br>*GUID* | Skrivskydd<br>Obligatoriskt<br>Sekundärnyckel: mshr_hcmjobentityid för entiteten mshr_hcmjobentity | Det systemgenererade, unika ID:t för jobbet som delas av samtliga befattningar associerade med rekryterandebegäran. |
| **Titel-ID**<br>mshr_titleid<br>*Sträng* | Skrivskydd<br>Obligatoriskt | Det användarläsbara unika ID:t för jobbtiteln som hör till denna begäran. |
| **Värde för titel-ID**<br>_mshr_fk_title_id_value<br>*GUID* | Skrivskydd<br>Obligatoriskt<br>Sekundärnyckel: mshr_hcmtitleid tillhörande entiteten mshr_hcmtitleentity | Den systemgenererade, unika identifieraren för titeln på det jobb som valts för rekryteringsbegäran. |
| **Jobbfunktions-ID**<br>mshr_jobfunctionid<br>*Sträng* | Skrivskydd<br>Obligatoriskt<br>Sekundärnyckel: mshr_jobfunctionid tillhörande entiteten mshr_hcmjobfunctionentity | Det användarläsbara unika ID:t för jobbfunktionen som hör till denna begäran. |
| **Heltidslön**<br>mshr_defaultfulltimeequivalency<br>*Dubbel* | Skrivskydd<br>Obligatoriskt | Det heltidsmotsvarande värdet för jobbet, där 1,0 representerar en heltidsmedarbetare. |
| **Jobbkategori enligt regelverk**<br>mshr_regulatoryjobcategory<br>Alternativuppsättningen *RegulatoryJobCategory* | Skrivskydd<br>Valfritt | EEO-jobbkategorin för den jobbfunktion som valts för jobbet. Giltiga värden som ingår i alternativuppsättningen HcmRegulatoryJobCatetory (mshr_hcmregulatoryjobcategory). |
| **Jobbets typ-ID**<br>mshr_jobtypeid<br>*Sträng* | Skrivskydd<br>Valfritt | Den typ av jobb som är kopplad till befattningen. Jobbtyperna är användardefinierade värden som är tillgängliga i entiteten mshr_hcmjobtypeentity. |
| **ID-värde för jobbtyp**<br>_mshr_fk_jobtype_id_value<br>*GUID* | Skrivskydd<br>Valfritt<br>Sekundärnyckel: mshr_hcmjobtypeentityid tillhörande entiteten mshr_hcmjobtypenentity | Den systemgenererade, unika identifieraren för den jobbtyp som associeras med jobbet för rekryterandebegäran. |
| **Befrielsestatus**<br>mshr_exemptstatus<br>Alternativuppsättningen *JobExemptStatus* | Skrivskydd<br>Valfritt | Status för FLSA-undantaget som baseras på jobbtypen. |
| **Uppskattat startdatum**<br>mshr_estimatedstartdate<br>*Datum* | Skrivskydd<br>Obligatoriskt | Det uppskattade datum då en kandidat skulle påbörja arbetet. |
| **Extern beskrivning**<br>mshr_externaldescription<br>*Sträng* | Skrivskydd<br>Valfritt | En beskrivning av jobbet/befattningen riktad till kandidaten. | Låg kompensationströskel<br>mshr_compensationlowthreshold<br>*Dubbel* | Skrivskydd<br>Valfritt | Nedre begränsning för kompensationsnivån. |
| **Kontrollpunkt för kompensation**<br>mshr_compensationcontrolpoint<br>*Dubbel* | Skrivskydd<br>Valfritt | Kontrollpunkt för kompensationsnivån. |
| **Hög kompensationströskel**<br>mshr_compensationhighthreshold<br>*Dubbel* | Skrivskydd<br>Valfritt | Övre begränsning för kompensationsnivån. |
| **Kompensationsnivå**<br>mshr_compensationlevelid<br>*Sträng* | Skrivskydd<br>Valfritt | Kompensationsnivån för jobbet. Ett jobb kan konfigurera med flera kompensationsnivåer. Detta attribut anger den valda jobbkompensationsnivån för denna begäran. |
| **Kompensations-ID för jobb**<br>_mshr_fk_jobcompensation_id_value<br>*GUID* | Skrivskydd<br>Valfritt<br>Sekundärnyckel: Foreign key: mshr_hcmjobcompensationentityid tillhörande entiteten mshr_hcmjobcompensationentity | Systemgenererad, unik identifierare för den kompensationsnivå som associeras med jobbet för rekryterandebegäran. |

## <a name="see-also"></a>Se även

[Introduktion av API för integrering av system för sökandespårning](hr-admin-integration-ats-api-introduction.md)<br>
[Exempelfråga för rekryteringsbegäran](hr-admin-integration-ats-api-recruiting-request-example-query.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]