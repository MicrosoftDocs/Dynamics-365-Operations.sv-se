---
title: Generera och granska lönelisteentiteter
description: Detta ämne beskriver hur du genererar och granskar löneenheter.
author: andreabichsel
manager: tfehr
ms.date: 04/07/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2021-04-07
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: c6e043498d4e36e38575a16c6475a5edfef51fc6
ms.sourcegitcommit: d18d9cdb175c9d42eafbed66352c24b2aa94258b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/13/2021
ms.locfileid: "5882079"
---
# <a name="generate-payroll-entities"></a><span data-ttu-id="2fbb0-103">Generera lönelisteentiteter</span><span class="sxs-lookup"><span data-stu-id="2fbb0-103">Generate payroll entities</span></span>

<span data-ttu-id="2fbb0-104">Använd denna OData-funktion för att generera de entiteter som behövs för löneintegrering.</span><span class="sxs-lookup"><span data-stu-id="2fbb0-104">Use this OData function to generate the entities needed for payroll integration.</span></span> <span data-ttu-id="2fbb0-105">Om några ändringar görs i dessa entiteter i Personal, t.ex. att lägga till anpassade fält, kan denna funktion anropas igen för att uppdatera metadatan för respektive entitet.</span><span class="sxs-lookup"><span data-stu-id="2fbb0-105">If any changes are made to these entities in Human Resources, such as adding custom fields, this function can be called again to refresh the metadata of each entity.</span></span> <span data-ttu-id="2fbb0-106">Svaret innehåller ett åtgärds-ID som du kan övervaka så att du vet när genereringen har slutförts.</span><span class="sxs-lookup"><span data-stu-id="2fbb0-106">The response contains an operation ID that you can monitor so you know when the generation process has completed.</span></span>

<span data-ttu-id="2fbb0-107">**Begäran**</span><span class="sxs-lookup"><span data-stu-id="2fbb0-107">**Request**</span></span>

```http
GET [Organizaton URI]/api/data/v9.1/RefreshHumanResourcesVirtualEntities
```

<span data-ttu-id="2fbb0-108">**brödtext**</span><span class="sxs-lookup"><span data-stu-id="2fbb0-108">**body**</span></span>

```json
{
    "PhysicalNames" : ["PayrollEmployeeEntity", "HcmWorkerBaseEntity", "PayrollPositionEntity", "PayrollPositionJobEntity", "PayrollWorkerAddressEntity", "HcmJobDetailEntity", "HcmCompFixedPlanTableEntity", "PayrollFixedCompensationPlanEntity", "HcmEmploymentDetailEntity"]
}
```

<span data-ttu-id="2fbb0-109">**Svar**</span><span class="sxs-lookup"><span data-stu-id="2fbb0-109">**Response**</span></span>

```json
{
    "AsyncOperationId": "8b98d338-f939-4c86-9a91-80b76b6ab2ea"
}
```

## <a name="review-payroll-entities"></a><span data-ttu-id="2fbb0-110">Granska löneentiteter</span><span class="sxs-lookup"><span data-stu-id="2fbb0-110">Review payroll entities</span></span>

<span data-ttu-id="2fbb0-111">Använd detta API om du vill hämta en lista över de entiteter som har skapats och är klara för användning.</span><span class="sxs-lookup"><span data-stu-id="2fbb0-111">Use this API to retrieve a list of the entities that have been successfully generated and are ready for use.</span></span>

<span data-ttu-id="2fbb0-112">**Begäran**</span><span class="sxs-lookup"><span data-stu-id="2fbb0-112">**Request**</span></span>

```http
GET [Organizaton URI]/api/data/v9.1/mshr_hrvirtualentitycatalogs?$filter=mshr_hasbeengenerated eq true
```

<span data-ttu-id="2fbb0-113">**Svar**</span><span class="sxs-lookup"><span data-stu-id="2fbb0-113">**Response**</span></span>

```json
{
      "value": [
        {
            "mshr_physicalname": "PayrollWorkerAddressEntity",
            "mshr_hasbeengenerated": true,
            "mshr_hrvirtualentitycatalogid": "00000603-0000-0000-1c00-005001000000",
            "mshr_refresh": null
        },
        {
            "mshr_physicalname": "HcmJobDetailEntity",
            "mshr_hasbeengenerated": true,
            "mshr_hrvirtualentitycatalogid": "00000603-0000-0000-6400-005001000000",
            "mshr_refresh": null
        },
        {
            "mshr_physicalname": "HcmCompFixedPlanTableEntity",
            "mshr_hasbeengenerated": true,
            "mshr_hrvirtualentitycatalogid": "00000603-0000-0000-6b00-005001000000",
            "mshr_refresh": null
        },
        {
            "mshr_physicalname": "PayrollEmployeeEntity",
            "mshr_hasbeengenerated": true,
            "mshr_hrvirtualentitycatalogid": "00000603-0000-0000-6d00-005001000000",
            "mshr_refresh": null
        },
        {
            "mshr_physicalname": "HcmEmploymentDetailEntity",
            "mshr_hasbeengenerated": true,
            "mshr_hrvirtualentitycatalogid": "00000603-0000-0000-7e00-005001000000",
            "mshr_refresh": null
        },
        {
            "mshr_physicalname": "PayrollFixedCompensationPlanEntity",
            "mshr_hasbeengenerated": true,
            "mshr_hrvirtualentitycatalogid": "00000603-0000-0000-9300-005001000000",
            "mshr_refresh": null
        },
        {
            "mshr_physicalname": "HcmWorkerBaseEntity",
            "mshr_hasbeengenerated": true,
            "mshr_hrvirtualentitycatalogid": "00000603-0000-0000-c000-005001000000",
            "mshr_refresh": null
        },
        {
            "mshr_physicalname": "PayrollPositionJobEntity",
            "mshr_hasbeengenerated": true,
            "mshr_hrvirtualentitycatalogid": "00000603-0000-0000-e700-005001000000",
            "mshr_refresh": null
        }
    ]
}
```

[!INCLUDE[footer-include](../includes/footer-banner.md)]