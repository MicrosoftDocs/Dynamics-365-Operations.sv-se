---
title: Exempelfrågeställning för kandidat att anställa
description: Detta ämne utgör en exempelfrågeställning för entiteten för Kandidat att anställa i Dynamics 365 Human Resources.
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
ms.openlocfilehash: 2dd744665d4f0b6c64f4ee45a01c237081018514
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8848355"
---
# <a name="example-query-for-candidate-to-hire"></a>Exempelfrågeställning för kandidat att anställa


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Detta ämne utgör en exempelfrågeställning för entiteten för Kandidat att anställa i Dynamics 365 Human Resources.

Detta ämne innehåller ett exempel som demonstrerar hur du kan använda *djupgående infogningar* för att skapa alla detaljer för en ny kandidatpost i en enskild API-åtgärd. Mer information om djupgående infogningar finns i [Skapa relaterade entitetsposter i en och samma åtgärd](/powerapps/developer/data-platform/webapi/create-entity-web-api#create-related-entity-records-in-one-operation).

Entiteten **mshr_hcmcandidatetohireentity** är unik på grund av sin relation till entiteten **mshr_dirpersonentity**. Många av egenskaperna i **mshr_hcmcandidatetohireentity** (till exempel **mshr_firstname**, **mshr_lastname** och **mshr_birthdate**) hämtas från posten **mshr_dirpersonentity**. Om du bokför en ny kandidatpost i **mshr_hcmcandidatetohireentity** utan att använda djupgående infogningar kan du definiera värden för dessa egenskaper direkt i posten **mshr_hcmcandidatetohireentity**. Den associerade posten **mshr_dirpersonentity** skapas automatiskt med de definierade värdena för egenskaperna. Du kan sedan skapa alla andra relaterade entitetsposter (till exempel färdigheter eller utbildning) som separata API-anrop.

Om du vill använda djupinfogningar för att skapa alla relaterade entiteter i en och samma åtgärd måste egenskaperna som är specifika för entiteten **mshr_dirpersonentity** definieras på åtgärdens kapslade nivå.

Detta exempel visar hur du kan skapa en kandidatpost, associerad personpost och personens färdigheter och utbildning på tre kapslade nivåer med hjälp av djupgående infogning i en enskild API-åtgärd.

> [!NOTE]
> Exemplet inkluderar inte alla egenskaper för respektive API-entitet. Den är förenklad i demonstrationssyfte.

**Begäran**

```http

POST [Organization URI]/api/data/v9.1/mshr_hcmcandidatetohireentities
Content-Type: application/json; charset=utf-8
OData-MaxVersion: 4.0
OData-Version: 4.0
Accept: application/json

{
    "mshr_dataareaid": "usmf",
    "mshr_recruitingrequestid": "USMF-000141",
    "mshr_positionid": "000601",
    "mshr_iswillingtorelocate": 200000000,
    "mshr_availabilitydate": "2021-03-18",
    "mshr_comments": "Evelyn's experience is exactly what we need for this position.",
    "mshr_FK_Person_id":
        {
            "mshr_firstname": "Evelyn",
            "mshr_lastname": "Chambers",
            "mshr_namesequencedisplayas": "FirstMiddleLast",
            "mshr_FK_HcmPersonSkillEntity_Person":
            [
                {
                    "mshr_skillid": "CustFocus",
                    "mshr_ratingid": "Skills",
                    "mshr_levelid": "4",
                    "mshr_ratinglevelexaminer": "",
                    "mshr_leveltype": 200000000,
                    "mshr_yearsofexperience": 0,
                    "mshr_verified": 200000000,
                    "mshr_leveldate": "2013-01-01T00:00:00Z"
                },
                {
                    "mshr_skillid": "CashFlow",
                    "mshr_ratingid": "Skills",
                    "mshr_levelid": "4",
                    "mshr_ratinglevelexaminer": "",
                    "mshr_leveltype": 200000000,
                    "mshr_yearsofexperience": 0,
                    "mshr_verified": 200000000,
                    "mshr_leveldate": "2013-01-01T00:00:00Z"
                }
            ],
            "mshr_FK_HcmPersonEducationEntity_Person": [
                {
                    "mshr_creditbasis": 200000000,
                    "mshr_enddate": "2021-02-22T00:00:00Z",
                    "mshr_educationlevelid": "Bachelor",
                    "mshr_creditsearned": 0,
                    "mshr_startdate": "2017-02-21T00:00:00Z",
                    "mshr_creditscompleted": 0,
                    "mshr_educationinstitutionid": "Cottonwood Univ",
                    "mshr_educationdisciplineid": "Business Mgmt",
                    "mshr_durationunit": 200000000
                }              
            ]
        }
}
```

**Svar**

```http

HTTP/1/1 204 No Content
OData-Version: 4.0
OData-EntityId: [Organization URI]/api/data/v9.1/mshr_hcmcandidatetohireentities(00000d2d-0000-0000-7317-005001000000)

```

## <a name="see-also"></a>Se även

[Introduktion av API för integrering av system för sökandespårning](hr-admin-integration-ats-api-introduction.md)<br>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
