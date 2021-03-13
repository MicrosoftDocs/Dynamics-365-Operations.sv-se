---
title: Befattning för rekryteringsbegäran
description: Detta ämne beskriver positionsentiteten Rekryteringsbegäran för Dynamics 365 Human Resources.
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
ms.openlocfilehash: 01d73d390f72343c7498ccbb99838d38be45a19e
ms.sourcegitcommit: 33b5c8bc4f9461e290513aa22de1ec1fba3b0742
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/05/2021
ms.locfileid: "5126036"
---
# <a name="recruiting-request-position"></a>Befattning för rekryteringsbegäran

Detta ämne beskriver positionsentiteten Rekryteringsbegäran för Dynamics 365 Human Resources.

Fysiskt namn: mshr_hcmrecruitingrequestpositionentity

### <a name="description"></a>beskrivning

Beskriver befattningen eller befattningarna som ska fyllas i för en rekryteringsbegäran. Det är valfritt att lägga till en befattning i rekryteringsbegäran. Egenskaperna för befattningen är skrivskyddade, detta eftersom befattningsegenskaperna inte bör vara olika på rekryteringsbegäran jämfört med i huvudposten för befattningen. Om egenskaperna behöver ändras bör det göras på huvudposten för befattningen innan befattningen läggs till i rekryteringsbegäran.

### <a name="json-representation"></a>JSON-representation
```json
{
    "mshr_recruitingrequestid": "String",
    "mshr_positionid": "String",
    "mshr_description": "String",
    "mshr_positiontypeid": "String",
    "mshr_status": Int,
    "mshr_departmentnumber": "String",
    "mshr_reportstopositionid": "String",
    "mshr_reportstopersonnelnumber": "String",
    "mshr_financialdimension": "String",
    "mshr_dataareaid": "String",
    "_mshr_dataareaid_id_value": "Guid",
    "mshr_primaryfield": "String",
    "_mshr_fk_recruitingrequest_id_value": "Guid",
    "_mshr_fk_position_id_value": "Guid",
    "_mshr_fk_positiontype_id_value": "Guid",
    "_mshr_fk_department_id_value": "Guid",
    "_mshr_fk_reportstoposition_id_value": "Guid",
    "_mshr_fk_reportstoworker_id_value": "Guid",
    "mshr_hcmrecruitingrequestpositionentityid": "Guid"
}
```

### <a name="properties"></a>Egenskaper

| Egenskap<br>**Fysiskt namn**<br>**_Typ_** | Använd | beskrivning |
| --- | --- | --- |
| **Entitets-ID för rekryteringsbegäran**<br>mshr_hcmrecruitingrequestpositionentityid<br>*GUID* | Skrivskydd<br>Obligatoriskt |    Systemgenererad identifierare för posten för rekryteringsbegäran. |
| **ID för rekryteringsbegäran**<br>mshr_recruitingrequestid<br>*Sträng* | Skriv en gång<br>Obligatoriskt | Den användarläsbara unika identifieraren för rekryteringsbegäran. |
| **ID-värde för rekryteringsbegäran**<br>_mshr_fk_recruitingrequest_id_value<br>*GUID* | Skrivskydd<br>Obligatoriskt<br>Sekundärnyckel: mshr_hcmrecruitingrequestentityid för entiteten mshr_hcmrecruitingrequestentity | Systemgenererad identifierare för den rekryteringsbegäran till vilken befattningen har tilldelats. |
| **Befattnings-ID**<br>mshr_positionid<br>*Sträng* | Skriv en gång<br>Obligatoriskt | Den användarläsbara unika identifieraren för befattningen. |
| **ID-värde för befattning**<br>_mshr_fk_position_id_value<br>*GUID* | Skrivskydd<br>Obligatoriskt<br>Sekundärnyckel: entiteten mshr_hcmpositionv2entityid för mshr_hcmpositionv2entity | Systemgenererad identifierare för befattningen. |
| **Beskrivning**<br>mshr_description<br>*Sträng* | Skrivskydd<br>Obligatoriskt | Befattningsbeskrivningen. |
| **ID för befattningstyp**<br>mshr_positiontypeid<br>*Sträng* | Skrivskydd<br>Valfritt | Den användarläsbara unika identifieraren för befattningens positionstyp. |
| **ID-värde för befattningstyp**<br>_mshr_fk_positiontype_id_value<br>*GUID* | Skrivskydd<br>Valfritt<br>Sekundärnyckel: mshr_hcmpositiontypeentityid för entiteten mshr_hcmpositiontypeentity | En systemgenererad, unik identifierare för befattningens positionstyp. |
| **Status**<br>mshr_status<br>Alternativuppsättningen *RecruitingRequestPositionStatus* | Skrivskydd<br>Obligatoriskt | Befattningsstatusen för rekryteringsbegäran. |
| **Avdelningsnummer**<br>mshr_departmentnumber<br>*Sträng* | Skrivskydd<br>Valfritt<br> | Befattningens avdelningsnummer. |
| **ID-värde för avdelning**<br>_mshr_fk_department_id_value<br>*GUID* | Skrivskydd<br>Valfritt<br>Sekundärnyckel: mshr_omdepartmententityid tillhörande entiteten mshr_omdepartmententity | Systemgenererad, unik identifierare för befattningens avdelningstyp. |
| **Befattnings-ID för rapportering**<br>mshr_reportstopositionid<br>*Sträng* | Skrivskydd<br>Obligatoriskt | Användarläsbart ID för den befattning till vilken den rekryterade befattningen rapporterar i organisationshierarkin. |
| **ID-värde för befattning för rapportering**<br>_mshr_fk_reportstoposition_id_value<br>*GUID* | Skrivskydd<br>Obligatoriskt<br>Sekundärnyckel: entiteten mshr_hcmpositionv2entityid för mshr_hcmpositionv2entity | Det systemgenererade ID:t för befattningen som den rekryterade befattningen rapporterar till. |
| **Rapporterar till personalnummer**<br>mshr_reportstopersonnelnumber<br>*Sträng* | Skrivskydd<br>Obligatoriskt | Arbetar-ID för den medarbetare som den anställda kandidaten rapporterar till. |
| **ID-värde för Rapporterar till medarbetare**<br>_mshr_fk_reportstoworker_id_value<br>*GUID* | Skrivskydd<br>Obligatoriskt<br>Sekundärnyckel: mshr_hcmworkerbaseentityid tillhörande entiteten mshr_hcmworkerbaseentity | Systemgenererat ID för den medarbetare som den anställda kandidaten rapporterar till. |
| **Ekonomisk dimension**<br>mshr_financialdimension<br>*Sträng* | Skrivskydd<br>Valfritt | Den ekonomiska dimension (till exempel kostnadsställe) som tilldelats befattningen. Den ekonomiska dimensionen tilldelas för respektive befattning per juridisk person. Kostnadsställen som definieras i dimensioner kan nås via entiteten mshr_dimattributeomcostcenterentity. |
| **ID för dataområde**<br>mshr_dataareaid<br>*Sträng* | Skrivskydd<br>Valfritt | Anger den juridiska personen (företaget) för befattningen i rekryteringsbegäran. |
| **ID-värde för dataområde**<br>_mshr_dataareaid_id_value<br>*GUID* | Skrivskydd<br>Valfritt<br>Sekundärnyckel: entiteten cdm_companyid cdm_company | Systemgenererat GUID-värde som identifierar den juridiska personen (företaget) för befattningen i rekryteringsbegäran. |
| **Primärt fält**<br>mshr_primaryfield<br>*Sträng* | Skrivskydd<br>Obligatoriskt | Sammanslagning av värdet för rekryteringsbegäran och positions-ID som en annan metod för att identifiera posten unikt. |

## <a name="see-also"></a>Se även

[Introduktion av API för integrering av system för sökandespårning](hr-admin-integration-ats-api-introduction.md)<br>
[Exempelfråga för rekryteringsbegäran](hr-admin-integration-ats-api-recruiting-request-example-query.md)

