---
title: Interna tillgångar för service
description: I det här avsnittet beskrivs hur du kan använda Microsoft Dynamics 365 Field Service för att serva både kundtillgångar och interna tillgångar.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-01-27
ms.openlocfilehash: d931811e9fbea3c10f83b048a3c3fbeda5396d39
ms.sourcegitcommit: 48c39c0c0949fe48b3536d9d2d0e451d561ff5c6
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/09/2020
ms.locfileid: "3112523"
---
# <a name="in-house-assets-for-servicing"></a><span data-ttu-id="4eaf8-103">Interna tillgångar för service</span><span class="sxs-lookup"><span data-stu-id="4eaf8-103">In-house assets for servicing</span></span>

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

<span data-ttu-id="4eaf8-104">Microsoft Dynamics 365 Field Service har utformats för att betjäna kundtillgångar.</span><span class="sxs-lookup"><span data-stu-id="4eaf8-104">Microsoft Dynamics 365 Field Service is designed to service customer assets.</span></span> <span data-ttu-id="4eaf8-105">Tillgångshantering för Dynamics 365 Supply Chain Management har utformats för att upprätthålla anläggningstillgångar.</span><span class="sxs-lookup"><span data-stu-id="4eaf8-105">Asset management for Dynamics 365 Supply Chain Management is designed to maintain in-house assets.</span></span> <span data-ttu-id="4eaf8-106">Genom att integrera dessa två appar kan du använda Field Service för att betjäna både kundtillgångar och interna tillgångar.</span><span class="sxs-lookup"><span data-stu-id="4eaf8-106">Integration of these two apps lets you use Field Service to service both customer assets and in-house assets.</span></span> <span data-ttu-id="4eaf8-107">Du kan också klassificera tillgångarna, baserat på en funktionell plats eller hierarki och spåra underhållet på en detaljerad nivå.</span><span class="sxs-lookup"><span data-stu-id="4eaf8-107">You can also classify the assets, based on functional location or hierarchy, and track the servicing at a detailed level.</span></span>

<span data-ttu-id="4eaf8-108">Mer information finns i [integrera Dynamics 365 Field Service och Supply Chain Management](https://docs.microsoft.com/dynamics365/field-service/supply-chain-field-service-integration).</span><span class="sxs-lookup"><span data-stu-id="4eaf8-108">For more information, see [Integrate Dynamics 365 Field Service and Supply Chain Management](https://docs.microsoft.com/dynamics365/field-service/supply-chain-field-service-integration).</span></span>

## <a name="templates"></a><span data-ttu-id="4eaf8-109">Mallar</span><span class="sxs-lookup"><span data-stu-id="4eaf8-109">Templates</span></span>

<span data-ttu-id="4eaf8-110">Interna tillgångar inkluderar en samling entitetsmappningar som fungerar tillsammans under kunddatainteraktion, som visas i följande tabell.</span><span class="sxs-lookup"><span data-stu-id="4eaf8-110">In-house-assets include a collection of core entity maps that work together during data interaction, as shown in the following table.</span></span>

| <span data-ttu-id="4eaf8-111">Finance and Operations-appar</span><span class="sxs-lookup"><span data-stu-id="4eaf8-111">Finance and Operations apps</span></span> | <span data-ttu-id="4eaf8-112">Modellstyrda appar i Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="4eaf8-112">Model-driven apps in Dynamics 365</span></span> | <span data-ttu-id="4eaf8-113">beskrivning</span><span class="sxs-lookup"><span data-stu-id="4eaf8-113">Description</span></span> |
|-----------------------------|-----------------------------------|-------------|
| <span data-ttu-id="4eaf8-114">Tillgångshantering för livscykelmodeller av tillgångar</span><span class="sxs-lookup"><span data-stu-id="4eaf8-114">Asset management asset lifecycle models</span></span> | <span data-ttu-id="4eaf8-115">msdyn\_assetlifecyclemodels</span><span class="sxs-lookup"><span data-stu-id="4eaf8-115">msdyn\_assetlifecyclemodels</span></span> | |
| <span data-ttu-id="4eaf8-116">Tillgångshantering för livscykeltillstånd av tillgångar</span><span class="sxs-lookup"><span data-stu-id="4eaf8-116">Asset management asset lifecycle states</span></span> | <span data-ttu-id="4eaf8-117">msdyn\_assetlifecyclestates</span><span class="sxs-lookup"><span data-stu-id="4eaf8-117">msdyn\_assetlifecyclestates</span></span> | |
| <span data-ttu-id="4eaf8-118">Tillgångar för hantering av tillgångar</span><span class="sxs-lookup"><span data-stu-id="4eaf8-118">Asset management assets</span></span> | <span data-ttu-id="4eaf8-119">msdyn\_customerassets</span><span class="sxs-lookup"><span data-stu-id="4eaf8-119">msdyn\_customerassets</span></span> | |
| <span data-ttu-id="4eaf8-120">Tillgångstyper för hantering av tillgångar</span><span class="sxs-lookup"><span data-stu-id="4eaf8-120">Asset management asset types</span></span> | <span data-ttu-id="4eaf8-121">msdyn\_customerassetcategories</span><span class="sxs-lookup"><span data-stu-id="4eaf8-121">msdyn\_customerassetcategories</span></span> | |
| <span data-ttu-id="4eaf8-122">Livscykelmodeller för funktionsplatsens tillgångshantering</span><span class="sxs-lookup"><span data-stu-id="4eaf8-122">Asset management functional location lifecycle models</span></span> | <span data-ttu-id="4eaf8-123">msdyn\_functionallocationlifecyclemodels</span><span class="sxs-lookup"><span data-stu-id="4eaf8-123">msdyn\_functionallocationlifecyclemodels</span></span> | |
| <span data-ttu-id="4eaf8-124">Livscykeltillstånd för funktionsplatsens tillgångshantering</span><span class="sxs-lookup"><span data-stu-id="4eaf8-124">Asset management functional location lifecycle states</span></span> | <span data-ttu-id="4eaf8-125">msdyn\_functionallocationlifecyclestates</span><span class="sxs-lookup"><span data-stu-id="4eaf8-125">msdyn\_functionallocationlifecyclestates</span></span> | |
| <span data-ttu-id="4eaf8-126">Funktionsplatser för tillgångshantering</span><span class="sxs-lookup"><span data-stu-id="4eaf8-126">Asset management functional locations</span></span> | <span data-ttu-id="4eaf8-127">msdyn\_functionallocations</span><span class="sxs-lookup"><span data-stu-id="4eaf8-127">msdyn\_functionallocations</span></span> | |
| <span data-ttu-id="4eaf8-128">Funktionsplatstyper för tillgångshantering</span><span class="sxs-lookup"><span data-stu-id="4eaf8-128">Asset management functional location types</span></span> | <span data-ttu-id="4eaf8-129">msdyn\_functionallocationtypes</span><span class="sxs-lookup"><span data-stu-id="4eaf8-129">msdyn\_functionallocationtypes</span></span> | |
| <span data-ttu-id="4eaf8-130">Tillverkare för tillgångshantering</span><span class="sxs-lookup"><span data-stu-id="4eaf8-130">Asset management manufacturers</span></span> | <span data-ttu-id="4eaf8-131">msdyn\_manufacturers</span><span class="sxs-lookup"><span data-stu-id="4eaf8-131">msdyn\_manufacturers</span></span> | |
| <span data-ttu-id="4eaf8-132">Tillgångshanteringsmodeller</span><span class="sxs-lookup"><span data-stu-id="4eaf8-132">Asset management models</span></span> | <span data-ttu-id="4eaf8-133">msdyn\_models</span><span class="sxs-lookup"><span data-stu-id="4eaf8-133">msdyn\_models</span></span> | |
| <span data-ttu-id="4eaf8-134">Garanti över tillgångshantering</span><span class="sxs-lookup"><span data-stu-id="4eaf8-134">Asset management warranty</span></span> | <span data-ttu-id="4eaf8-135">msdyn\_warranties</span><span class="sxs-lookup"><span data-stu-id="4eaf8-135">msdyn\_warranties</span></span> | |

[!include [symbols](../../includes/dual-write-symbols.md)]

[!include [lifecycle models](includes/AssetManagementAssetLifecycleModels-msdyn-assetlifecyclemodels.md)]

[!include [lifecycle states](includes/AssetManagementAssetLifecycleStates-msdyn-assetlifecyclestates.md)]

[!include [assets](includes/AssetManagementAssets-msdyn-customerassets.md)]

[!include [asset types](includes/AssetManagementAssetTypes-msdyn-customerassetcategories.md)]

[!include [functional location lifecycle models](includes/AssetManagementFunctionalLocationLifecycleModels-msdyn-functionallocationlifecyclemodels.md)]

[!include [functional location lifecycle states](includes/AssetManagementFunctionalLocationLifecycleStates-msdyn-functionallocationlifecyclestates.md)]

[!include [functional locations](includes/AssetManagementFunctionalLocations-msdyn-functionallocations.md)]

[!include [functional location types](includes/AssetManagementFunctionalLocationTypes-msdyn-functionallocationtypes.md)]

[!include [manufacturers](includes/AssetManagementManufacturers-msdyn-manufacturers.md)]

[!include [models](includes/AssetManagementModels-msdyn-models.md)]

[!include [warranty](includes/AssetManagementWarranty-msdyn-warranties.md)]
