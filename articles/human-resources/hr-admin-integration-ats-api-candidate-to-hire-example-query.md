---
title: Exempelfråga för kandidat att anställa
description: Detta ämne utgör en exempelfråga för entiteten för Kandidat att anställa i Dynamics 365 Human Resources.
author: jaredha
ms.date: 02/05/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2021-02-05
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: ea6fc745ffb5892a32196394cb28cb5e646b7639
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5795079"
---
# <a name="example-query-for-candidate-to-hire"></a><span data-ttu-id="ded66-103">Exempelfråga för kandidat att anställa</span><span class="sxs-lookup"><span data-stu-id="ded66-103">Example query for Candidate to hire</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="ded66-104">Detta ämne utgör en exempelfråga för entiteten för Kandidat att anställa i Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="ded66-104">This topic provides an example query for the Candidate to hire entity in Dynamics 365 Human Resources.</span></span>

<span data-ttu-id="ded66-105">Detta ämne innehåller ett exempel som demonstrerar hur du kan använda *djupgående infogningar* för att skapa alla detaljer för en ny kandidatpost i en enskild API-åtgärd.</span><span class="sxs-lookup"><span data-stu-id="ded66-105">This topic provides an example demonstrating how you can use *deep inserts* to create all the detail of a new candidate record in a single API operation.</span></span> <span data-ttu-id="ded66-106">Mer information om djupgående infogningar finns i [Skapa relaterade entitetsposter i en och samma åtgärd](https://docs.microsoft.com/powerapps/developer/data-platform/webapi/create-entity-web-api#create-related-entity-records-in-one-operation).</span><span class="sxs-lookup"><span data-stu-id="ded66-106">For more information about deep inserts, see [Create related entity records in one operation](https://docs.microsoft.com/powerapps/developer/data-platform/webapi/create-entity-web-api#create-related-entity-records-in-one-operation).</span></span>

<span data-ttu-id="ded66-107">Entiteten **mshr_hcmcandidatetohireentity** är unik på grund av sin relation till entiteten **mshr_dirpersonentity**.</span><span class="sxs-lookup"><span data-stu-id="ded66-107">The **mshr_hcmcandidatetohireentity** entity is unique because of its relationship to the **mshr_dirpersonentity** entity.</span></span> <span data-ttu-id="ded66-108">Många av egenskaperna i **mshr_hcmcandidatetohireentity** (till exempel **mshr_firstname**, **mshr_lastname** och **mshr_birthdate**) hämtas från posten **mshr_dirpersonentity**.</span><span class="sxs-lookup"><span data-stu-id="ded66-108">Many of the properties on the **mshr_hcmcandidatetohireentity** (for example, **mshr_firstname**, **mshr_lastname**, and **mshr_birthdate**) are derived from the **mshr_dirpersonentity** record.</span></span> <span data-ttu-id="ded66-109">Om du bokför en ny kandidatpost i **mshr_hcmcandidatetohireentity** utan att använda djupgående infogningar kan du definiera värden för dessa egenskaper direkt i posten **mshr_hcmcandidatetohireentity**.</span><span class="sxs-lookup"><span data-stu-id="ded66-109">If you post a new candidate record to **mshr_hcmcandidatetohireentity** without using deep inserts, you can define values for these properties directly on the **mshr_hcmcandidatetohireentity** record.</span></span> <span data-ttu-id="ded66-110">Den associerade posten **mshr_dirpersonentity** skapas automatiskt med de definierade värdena för egenskaperna.</span><span class="sxs-lookup"><span data-stu-id="ded66-110">The associated **mshr_dirpersonentity** record is created implicitly with the defined values for the properties.</span></span> <span data-ttu-id="ded66-111">Du kan sedan skapa alla andra relaterade entitetsposter (till exempel färdigheter eller utbildning) som separata API-anrop.</span><span class="sxs-lookup"><span data-stu-id="ded66-111">You can then create any other related entity records (such as skills or education) as separate API calls.</span></span>

<span data-ttu-id="ded66-112">Om du vill använda djupinfogningar för att skapa alla relaterade entiteter i en och samma åtgärd måste egenskaperna som är specifika för entiteten **mshr_dirpersonentity** definieras på åtgärdens kapslade nivå.</span><span class="sxs-lookup"><span data-stu-id="ded66-112">If, however, you want to use deep inserts to create all related entities in one operation, the properties specific to the **mshr_dirpersonentity** entity must be defined on that nested level of the operation.</span></span>

<span data-ttu-id="ded66-113">Detta exempel visar hur du kan skapa en kandidatpost, associerad personpost och personens färdigheter och utbildning på tre kapslade nivåer med hjälp av djupgående infogning i en enskild API-åtgärd.</span><span class="sxs-lookup"><span data-stu-id="ded66-113">This example shows how you can create a candidate record, the associated person record, and the person's skills and education in three nested levels using deep inserts in a single API operation.</span></span>

> [!NOTE]
> <span data-ttu-id="ded66-114">Exemplet inkluderar inte alla egenskaper för respektive API-entitet.</span><span class="sxs-lookup"><span data-stu-id="ded66-114">The example does not include all properties of each of the API entities.</span></span> <span data-ttu-id="ded66-115">Den är förenklad i demonstrationssyfte.</span><span class="sxs-lookup"><span data-stu-id="ded66-115">It is simplified for demonstration purposes.</span></span>

<span data-ttu-id="ded66-116">**Begäran**</span><span class="sxs-lookup"><span data-stu-id="ded66-116">**Request**</span></span>

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

<span data-ttu-id="ded66-117">**Svar**</span><span class="sxs-lookup"><span data-stu-id="ded66-117">**Response**</span></span>

```http

HTTP/1/1 204 No Content
OData-Version: 4.0
OData-EntityId: [Organization URI]/api/data/v9.1/mshr_hcmcandidatetohireentities(00000d2d-0000-0000-7317-005001000000)

```

## <a name="see-also"></a><span data-ttu-id="ded66-118">Se även</span><span class="sxs-lookup"><span data-stu-id="ded66-118">See also</span></span>

[<span data-ttu-id="ded66-119">Introduktion av API för integrering av system för sökandespårning</span><span class="sxs-lookup"><span data-stu-id="ded66-119">Applicant Tracking System integration API introduction</span></span>](hr-admin-integration-ats-api-introduction.md)<br>


[!INCLUDE[footer-include](../includes/footer-banner.md)]