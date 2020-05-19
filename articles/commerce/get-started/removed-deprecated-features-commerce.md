---
title: Borttagna och utfasade funktioner i Dynamics 365 Commerce
description: I det här avsnittet beskrivs funktioner som har tagits bort, eller har planerats för borttagning från Dynamics 365 Commerce.
author: josaw
manager: AnnBe
ms.date: 05/04/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2020-04-30
ms.dyn365.ops.version: Platform update 33
ms.openlocfilehash: c47c5430a8f5d67e13c95db609a95d5ad66933ae
ms.sourcegitcommit: a8b6cd799eddaf5be9aec9ea3c2b55e2c3231652
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/05/2020
ms.locfileid: "3335286"
---
# <a name="removed-or-deprecated-features-in-dynamics-365-commerce"></a><span data-ttu-id="18fdf-103">Borttagna och utfasade funktioner i Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="18fdf-103">Removed or deprecated features in Dynamics 365 Commerce</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="18fdf-104">I det här avsnittet beskrivs funktioner som har tagits bort, eller har planerats för borttagning från Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="18fdf-104">This topic describes features that have been removed, or that are planned for removal from Dynamics 365 Commerce.</span></span>

- <span data-ttu-id="18fdf-105">En *borttagen* funktion är inte längre tillgänglig i produkten.</span><span class="sxs-lookup"><span data-stu-id="18fdf-105">A *removed* feature is no longer available in the product.</span></span>
- <span data-ttu-id="18fdf-106">En *borttagen* funktion är inte i aktiv utveckling och kan tas bort i en kommande uppdatering.</span><span class="sxs-lookup"><span data-stu-id="18fdf-106">A *deprecated* feature is not in active development and may be removed in a future update.</span></span>

<span data-ttu-id="18fdf-107">Den här listan är avsedd att hjälpa dig att ta hänsyn till dessa borttagna och inaktuella funktioner för din planerings skull.</span><span class="sxs-lookup"><span data-stu-id="18fdf-107">This list is intended to help you consider these removals and deprecations for your own planning.</span></span> 

> [!NOTE]
> <span data-ttu-id="18fdf-108">Detaljerad information om objekt i Finance and Operations-appar hittas i [Tekniska referensrapporter](https://mbs.microsoft.com/customersource/northamerica/AX/downloads/reports/axtechrefrep).</span><span class="sxs-lookup"><span data-stu-id="18fdf-108">Detailed information about objects in Finance and Operations apps can be found in the [Technical reference reports](https://mbs.microsoft.com/customersource/northamerica/AX/downloads/reports/axtechrefrep).</span></span> <span data-ttu-id="18fdf-109">Du kan jämföra olika versioner av rapporterna för mer information om objekt som har ändrats eller tagits bort i varje version av Finance and Operations-appar.</span><span class="sxs-lookup"><span data-stu-id="18fdf-109">You can compare the different versions of these reports to learn about objects that have changed or been removed in each version of Finance and Operations apps.</span></span>

## <a name="features-removed-or-deprecated-in-the-commerce-10010-release"></a><span data-ttu-id="18fdf-110">Borttagna eller föråldrade funktioner i Commerce version 10.0.10</span><span class="sxs-lookup"><span data-stu-id="18fdf-110">Features removed or deprecated in the Commerce 10.0.10 release</span></span>
### <a name="pos-operation-803---picking-and-receiving"></a><span data-ttu-id="18fdf-111">Kassaåtgärd 803 – Plockning och mottagning</span><span class="sxs-lookup"><span data-stu-id="18fdf-111">POS operation 803 - Picking and receiving</span></span>
|   |  |
|------------|--------------------|
| <span data-ttu-id="18fdf-112">**Orsak till inaktuell/borttagning**</span><span class="sxs-lookup"><span data-stu-id="18fdf-112">**Reason for deprecation/removal**</span></span> | <span data-ttu-id="18fdf-113">Plocknings- och mottagningsåtgärder föråldras på grund av att ny åtgärd har omdesignats.</span><span class="sxs-lookup"><span data-stu-id="18fdf-113">Picking and receiving operations is being deprecated due to new operation redesign.</span></span> |
| <span data-ttu-id="18fdf-114">**Ersatt av en annan funktion?**</span><span class="sxs-lookup"><span data-stu-id="18fdf-114">**Replaced by another feature?**</span></span>   | <span data-ttu-id="18fdf-115">Ja.</span><span class="sxs-lookup"><span data-stu-id="18fdf-115">Yes.</span></span> <span data-ttu-id="18fdf-116">Den ersätts av två nya kassaåtgärder: inkommande åtgärd (804) och utgående åtgärd (805).</span><span class="sxs-lookup"><span data-stu-id="18fdf-116">It is replaced by two new POS operations: inbound operation (804) and outbound operation (805).</span></span>|
| <span data-ttu-id="18fdf-117">**Produktområden som påverkas**</span><span class="sxs-lookup"><span data-stu-id="18fdf-117">**Product areas affected**</span></span>         | <span data-ttu-id="18fdf-118">Program för kassa (POS)</span><span class="sxs-lookup"><span data-stu-id="18fdf-118">Point of sale (POS) application</span></span> |
| <span data-ttu-id="18fdf-119">**Distribueringsalternativ**</span><span class="sxs-lookup"><span data-stu-id="18fdf-119">**Deployment option**</span></span>              | <span data-ttu-id="18fdf-120">Allt</span><span class="sxs-lookup"><span data-stu-id="18fdf-120">All</span></span> |
| <span data-ttu-id="18fdf-121">**Status**</span><span class="sxs-lookup"><span data-stu-id="18fdf-121">**Status**</span></span>                         | <span data-ttu-id="18fdf-122">Inaktuell: Från version 10.0.10 kommer åtgärden för plockning och mottagning inte längre att erhålla funktionsuppdateringar.</span><span class="sxs-lookup"><span data-stu-id="18fdf-122">Deprecated: As of release 10.0.10, the picking and receiving operation will no longer receive any new feature updates.</span></span> <span data-ttu-id="18fdf-123">Endast viktiga felkorrigeringar kommer att utföras för den här åtgärden i framtida versioner.</span><span class="sxs-lookup"><span data-stu-id="18fdf-123">Only critical bug fixes will be done for this operation in future releases.</span></span> <span data-ttu-id="18fdf-124">Alla kunder uppmuntras att flytta till de nya [Inkommande åtgärderna](https://docs.microsoft.com/dynamics365/commerce/pos-inbound-inventory-operation) och [Utgående åtgärderna](https://docs.microsoft.com/dynamics365/commerce/pos-outbound-inventory-operation) som fortsätter att ingå i vår långsiktiga produktplan.</span><span class="sxs-lookup"><span data-stu-id="18fdf-124">All customers are encouraged to move to the new [Inbound operations](https://docs.microsoft.com/dynamics365/commerce/pos-inbound-inventory-operation) and [Outbound operations](https://docs.microsoft.com/dynamics365/commerce/pos-outbound-inventory-operation), which will continue to be part of our long-term product roadmap.</span></span> |


## <a name="features-removed-or-deprecated-in-the-commerce-1007-release"></a><span data-ttu-id="18fdf-125">Borttagna eller föråldrade funktioner i Commerce version 10.0.7</span><span class="sxs-lookup"><span data-stu-id="18fdf-125">Features removed or deprecated in the Commerce 10.0.7 release</span></span>
### <a name="commerce-getproductavailabilities-and-getavailableinventorynearby-apis"></a><span data-ttu-id="18fdf-126">Commerce GetProductAvailabilities och GetAvailableInventoryNearby API:er</span><span class="sxs-lookup"><span data-stu-id="18fdf-126">Commerce GetProductAvailabilities and GetAvailableInventoryNearby API's</span></span>
|   |  |
|------------|--------------------|
| <span data-ttu-id="18fdf-127">**Orsak till inaktuell/borttagning**</span><span class="sxs-lookup"><span data-stu-id="18fdf-127">**Reason for deprecation/removal**</span></span> | <span data-ttu-id="18fdf-128">Nya optimerade API:er har skapats för att ersätta GetProductAvailabilities och GetAvailableInventoryNearby API:er.</span><span class="sxs-lookup"><span data-stu-id="18fdf-128">New optimized APIs have been created to replace the GetProductAvailabilities and GetAvailableInventoryNearby APIs.</span></span> |
| <span data-ttu-id="18fdf-129">**Ersatt av en annan funktion?**</span><span class="sxs-lookup"><span data-stu-id="18fdf-129">**Replaced by another feature?**</span></span>   | <span data-ttu-id="18fdf-130">Ja: Det ersätts med GetEstimatedAvailability och GetEstimatedProductWarehouseAvailability API:er.</span><span class="sxs-lookup"><span data-stu-id="18fdf-130">Yes: It is replaced by GetEstimatedAvailabilty and GetEstimatedProductWarehouseAvailability APIs.</span></span> |
| <span data-ttu-id="18fdf-131">**Produktområden som påverkas**</span><span class="sxs-lookup"><span data-stu-id="18fdf-131">**Product areas affected**</span></span>         | <span data-ttu-id="18fdf-132">e-handelsprogram SDK</span><span class="sxs-lookup"><span data-stu-id="18fdf-132">e-Commerce application SDK</span></span> |
| <span data-ttu-id="18fdf-133">**Distribueringsalternativ**</span><span class="sxs-lookup"><span data-stu-id="18fdf-133">**Deployment option**</span></span>              | <span data-ttu-id="18fdf-134">Allt</span><span class="sxs-lookup"><span data-stu-id="18fdf-134">All</span></span> |
| <span data-ttu-id="18fdf-135">**Status**</span><span class="sxs-lookup"><span data-stu-id="18fdf-135">**Status**</span></span>                         | <span data-ttu-id="18fdf-136">Inaktuell: Från version 10.0.7 kommer du inte längre att kunna göra tekniska investeringar för GetProductAvailabilities och GetAvailableInventoryNearby.</span><span class="sxs-lookup"><span data-stu-id="18fdf-136">Deprecated: As of release 10.0.7, there will no longer be engineering investments made for GetProductAvailabilities and GetAvailableInventoryNearby.</span></span> <span data-ttu-id="18fdf-137">Organisationer som använder dessa API:er i sina e-handelsdistributioner bör konvertera till nya GetEstimatedAvailability och GetEstimatedProductWarehouseAvailability API:er och aktivera [optimerade beräkningsfunktionen för produkttillgänglighet](https://docs.microsoft.com/dynamics365/commerce/calculated-inventory-retail-channels).</span><span class="sxs-lookup"><span data-stu-id="18fdf-137">Organizations that use these APIs in their e-Commerce deployments should convert to the new GetEstimatedAvailabilty and GetEstimatedProductWarehouseAvailability APIs and enable the [Optimized product availability calculation feature](https://docs.microsoft.com/dynamics365/commerce/calculated-inventory-retail-channels).</span></span>  |

## <a name="previous-announcements-about-removed-or-deprecated-features"></a><span data-ttu-id="18fdf-138">Tidigare meddelanden om borttagna eller inaktuella funktioner</span><span class="sxs-lookup"><span data-stu-id="18fdf-138">Previous announcements about removed or deprecated features</span></span>
<span data-ttu-id="18fdf-139">Om du vill veta mer om funktioner som har tagits bort eller ersatts i tidigare versioner, se [borttagna eller inaktuella funktioner i tidigare versioner](../../fin-ops-core/dev-itpro/migration-upgrade/deprecated-features.md?toc=/dynamics365/commerce/toc.json).</span><span class="sxs-lookup"><span data-stu-id="18fdf-139">To learn more about features that have been removed or deprecated in previous releases, see [Removed or deprecated features in previous releases](../../fin-ops-core/dev-itpro/migration-upgrade/deprecated-features.md?toc=/dynamics365/commerce/toc.json).</span></span>
