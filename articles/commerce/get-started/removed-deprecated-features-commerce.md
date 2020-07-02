---
title: Borttagna och utfasade funktioner i Dynamics 365 Commerce
description: I det här avsnittet beskrivs funktioner som har tagits bort, eller har planerats för borttagning från Dynamics 365 Commerce.
author: josaw
manager: AnnBe
ms.date: 06/10/2020
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
ms.openlocfilehash: 64241ef1c25359c7b3b305c4e8f2b24de7e8f5e4
ms.sourcegitcommit: cf709f1421a0bf66ecea493088ecb4eb08004187
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/12/2020
ms.locfileid: "3443928"
---
# <a name="removed-or-deprecated-features-in-dynamics-365-commerce"></a><span data-ttu-id="e0ec0-103">Borttagna och utfasade funktioner i Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="e0ec0-103">Removed or deprecated features in Dynamics 365 Commerce</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="e0ec0-104">I det här avsnittet beskrivs funktioner som har tagits bort, eller har planerats för borttagning från Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="e0ec0-104">This topic describes features that have been removed, or that are planned for removal from Dynamics 365 Commerce.</span></span>

- <span data-ttu-id="e0ec0-105">En *borttagen* funktion är inte längre tillgänglig i produkten.</span><span class="sxs-lookup"><span data-stu-id="e0ec0-105">A *removed* feature is no longer available in the product.</span></span>
- <span data-ttu-id="e0ec0-106">En *borttagen* funktion är inte i aktiv utveckling och kan tas bort i en kommande uppdatering.</span><span class="sxs-lookup"><span data-stu-id="e0ec0-106">A *deprecated* feature is not in active development and may be removed in a future update.</span></span>

<span data-ttu-id="e0ec0-107">Den här listan är avsedd att hjälpa dig att ta hänsyn till dessa borttagna och inaktuella funktioner för din planerings skull.</span><span class="sxs-lookup"><span data-stu-id="e0ec0-107">This list is intended to help you consider these removals and deprecations for your own planning.</span></span> 

> [!NOTE]
> <span data-ttu-id="e0ec0-108">Detaljerad information om objekt i Finance and Operations-appar hittas i [Tekniska referensrapporter](https://mbs.microsoft.com/customersource/northamerica/AX/downloads/reports/axtechrefrep).</span><span class="sxs-lookup"><span data-stu-id="e0ec0-108">Detailed information about objects in Finance and Operations apps can be found in the [Technical reference reports](https://mbs.microsoft.com/customersource/northamerica/AX/downloads/reports/axtechrefrep).</span></span> <span data-ttu-id="e0ec0-109">Du kan jämföra olika versioner av rapporterna för mer information om objekt som har ändrats eller tagits bort i varje version av Finance and Operations-appar.</span><span class="sxs-lookup"><span data-stu-id="e0ec0-109">You can compare the different versions of these reports to learn about objects that have changed or been removed in each version of Finance and Operations apps.</span></span>

## <a name="features-removed-or-deprecated-in-the-commerce-10011-release"></a><span data-ttu-id="e0ec0-110">Borttagna eller föråldrade funktioner i Commerce version 10.0.11</span><span class="sxs-lookup"><span data-stu-id="e0ec0-110">Features removed or deprecated in the Commerce 10.0.11 release</span></span>
### <a name="data-action-hooks"></a><span data-ttu-id="e0ec0-111">Dataåtgärdshookar</span><span class="sxs-lookup"><span data-stu-id="e0ec0-111">Data action hooks</span></span>
|   |  |
|------------|--------------------|
| <span data-ttu-id="e0ec0-112">**Orsak till inaktuell/borttagning**</span><span class="sxs-lookup"><span data-stu-id="e0ec0-112">**Reason for deprecation/removal**</span></span> | <span data-ttu-id="e0ec0-113">Funktionen dataåtgärdshookar har föråldrats på grund av prestandaproblem.</span><span class="sxs-lookup"><span data-stu-id="e0ec0-113">The data action hooks feature has been deprecated due to performance issues.</span></span> |
| <span data-ttu-id="e0ec0-114">**Ersatt av en annan funktion?**</span><span class="sxs-lookup"><span data-stu-id="e0ec0-114">**Replaced by another feature?**</span></span>   | <span data-ttu-id="e0ec0-115">Du rekommenderas att istället använda [dataåtgärdsåsidosättningar](../e-commerce-extensibility/data-action-overrides.md) för att ändra affärslogiken i dataåtgärdsskiktet.</span><span class="sxs-lookup"><span data-stu-id="e0ec0-115">It is recommended to instead use [data action overrides](../e-commerce-extensibility/data-action-overrides.md) to modify business logic in the data action layer.</span></span>|
| <span data-ttu-id="e0ec0-116">**Produktområden som påverkas**</span><span class="sxs-lookup"><span data-stu-id="e0ec0-116">**Product areas affected**</span></span>         | <span data-ttu-id="e0ec0-117">Dataåtgärder för utbyggbarhet för e-handel</span><span class="sxs-lookup"><span data-stu-id="e0ec0-117">E-Commerce extensibility data actions</span></span> |
| <span data-ttu-id="e0ec0-118">**Distribueringsalternativ**</span><span class="sxs-lookup"><span data-stu-id="e0ec0-118">**Deployment option**</span></span>              | <span data-ttu-id="e0ec0-119">Allt</span><span class="sxs-lookup"><span data-stu-id="e0ec0-119">All</span></span> |
| <span data-ttu-id="e0ec0-120">**Status**</span><span class="sxs-lookup"><span data-stu-id="e0ec0-120">**Status**</span></span>                         | <span data-ttu-id="e0ec0-121">Inaktuell: Från version 10.0.11</span><span class="sxs-lookup"><span data-stu-id="e0ec0-121">Deprecated: As of release 10.0.11</span></span> |

## <a name="features-removed-or-deprecated-in-the-commerce-10010-release"></a><span data-ttu-id="e0ec0-122">Borttagna eller föråldrade funktioner i Commerce version 10.0.10</span><span class="sxs-lookup"><span data-stu-id="e0ec0-122">Features removed or deprecated in the Commerce 10.0.10 release</span></span>
### <a name="pos-operation-803---picking-and-receiving"></a><span data-ttu-id="e0ec0-123">Kassaåtgärd 803 – Plockning och mottagning</span><span class="sxs-lookup"><span data-stu-id="e0ec0-123">POS operation 803 - Picking and receiving</span></span>
|   |  |
|------------|--------------------|
| <span data-ttu-id="e0ec0-124">**Orsak till inaktuell/borttagning**</span><span class="sxs-lookup"><span data-stu-id="e0ec0-124">**Reason for deprecation/removal**</span></span> | <span data-ttu-id="e0ec0-125">Plocknings- och mottagningsåtgärder föråldras på grund av att ny åtgärd har omdesignats.</span><span class="sxs-lookup"><span data-stu-id="e0ec0-125">Picking and receiving operations is being deprecated due to new operation redesign.</span></span> |
| <span data-ttu-id="e0ec0-126">**Ersatt av en annan funktion?**</span><span class="sxs-lookup"><span data-stu-id="e0ec0-126">**Replaced by another feature?**</span></span>   | <span data-ttu-id="e0ec0-127">Ja.</span><span class="sxs-lookup"><span data-stu-id="e0ec0-127">Yes.</span></span> <span data-ttu-id="e0ec0-128">Den ersätts av två nya kassaåtgärder: inkommande åtgärd (804) och utgående åtgärd (805).</span><span class="sxs-lookup"><span data-stu-id="e0ec0-128">It is replaced by two new POS operations: inbound operation (804) and outbound operation (805).</span></span>|
| <span data-ttu-id="e0ec0-129">**Produktområden som påverkas**</span><span class="sxs-lookup"><span data-stu-id="e0ec0-129">**Product areas affected**</span></span>         | <span data-ttu-id="e0ec0-130">Program för kassa (POS)</span><span class="sxs-lookup"><span data-stu-id="e0ec0-130">Point of sale (POS) application</span></span> |
| <span data-ttu-id="e0ec0-131">**Distribueringsalternativ**</span><span class="sxs-lookup"><span data-stu-id="e0ec0-131">**Deployment option**</span></span>              | <span data-ttu-id="e0ec0-132">Allt</span><span class="sxs-lookup"><span data-stu-id="e0ec0-132">All</span></span> |
| <span data-ttu-id="e0ec0-133">**Status**</span><span class="sxs-lookup"><span data-stu-id="e0ec0-133">**Status**</span></span>                         | <span data-ttu-id="e0ec0-134">Inaktuell: Från version 10.0.10 kommer åtgärden för plockning och mottagning inte längre att erhålla funktionsuppdateringar.</span><span class="sxs-lookup"><span data-stu-id="e0ec0-134">Deprecated: As of release 10.0.10, the picking and receiving operation will no longer receive any new feature updates.</span></span> <span data-ttu-id="e0ec0-135">Endast viktiga felkorrigeringar kommer att utföras för den här åtgärden i framtida versioner.</span><span class="sxs-lookup"><span data-stu-id="e0ec0-135">Only critical bug fixes will be done for this operation in future releases.</span></span> <span data-ttu-id="e0ec0-136">Alla kunder uppmuntras att flytta till de nya [Inkommande åtgärderna](https://docs.microsoft.com/dynamics365/commerce/pos-inbound-inventory-operation) och [Utgående åtgärderna](https://docs.microsoft.com/dynamics365/commerce/pos-outbound-inventory-operation) som fortsätter att ingå i vår långsiktiga produktplan.</span><span class="sxs-lookup"><span data-stu-id="e0ec0-136">All customers are encouraged to move to the new [Inbound operations](https://docs.microsoft.com/dynamics365/commerce/pos-inbound-inventory-operation) and [Outbound operations](https://docs.microsoft.com/dynamics365/commerce/pos-outbound-inventory-operation), which will continue to be part of our long-term product roadmap.</span></span> |


## <a name="features-removed-or-deprecated-in-the-commerce-1007-release"></a><span data-ttu-id="e0ec0-137">Borttagna eller föråldrade funktioner i Commerce version 10.0.7</span><span class="sxs-lookup"><span data-stu-id="e0ec0-137">Features removed or deprecated in the Commerce 10.0.7 release</span></span>
### <a name="commerce-getproductavailabilities-and-getavailableinventorynearby-apis"></a><span data-ttu-id="e0ec0-138">Commerce GetProductAvailabilities och GetAvailableInventoryNearby API:er</span><span class="sxs-lookup"><span data-stu-id="e0ec0-138">Commerce GetProductAvailabilities and GetAvailableInventoryNearby API's</span></span>
|   |  |
|------------|--------------------|
| <span data-ttu-id="e0ec0-139">**Orsak till inaktuell/borttagning**</span><span class="sxs-lookup"><span data-stu-id="e0ec0-139">**Reason for deprecation/removal**</span></span> | <span data-ttu-id="e0ec0-140">Nya optimerade API:er har skapats för att ersätta GetProductAvailabilities och GetAvailableInventoryNearby API:er.</span><span class="sxs-lookup"><span data-stu-id="e0ec0-140">New optimized APIs have been created to replace the GetProductAvailabilities and GetAvailableInventoryNearby APIs.</span></span> |
| <span data-ttu-id="e0ec0-141">**Ersatt av en annan funktion?**</span><span class="sxs-lookup"><span data-stu-id="e0ec0-141">**Replaced by another feature?**</span></span>   | <span data-ttu-id="e0ec0-142">Ja: Det ersätts med GetEstimatedAvailability och GetEstimatedProductWarehouseAvailability API:er.</span><span class="sxs-lookup"><span data-stu-id="e0ec0-142">Yes: It is replaced by GetEstimatedAvailabilty and GetEstimatedProductWarehouseAvailability APIs.</span></span> |
| <span data-ttu-id="e0ec0-143">**Produktområden som påverkas**</span><span class="sxs-lookup"><span data-stu-id="e0ec0-143">**Product areas affected**</span></span>         | <span data-ttu-id="e0ec0-144">e-handelsprogram SDK</span><span class="sxs-lookup"><span data-stu-id="e0ec0-144">e-Commerce application SDK</span></span> |
| <span data-ttu-id="e0ec0-145">**Distribueringsalternativ**</span><span class="sxs-lookup"><span data-stu-id="e0ec0-145">**Deployment option**</span></span>              | <span data-ttu-id="e0ec0-146">Allt</span><span class="sxs-lookup"><span data-stu-id="e0ec0-146">All</span></span> |
| <span data-ttu-id="e0ec0-147">**Status**</span><span class="sxs-lookup"><span data-stu-id="e0ec0-147">**Status**</span></span>                         | <span data-ttu-id="e0ec0-148">Inaktuell: Från version 10.0.7 kommer du inte längre att kunna göra tekniska investeringar för GetProductAvailabilities och GetAvailableInventoryNearby.</span><span class="sxs-lookup"><span data-stu-id="e0ec0-148">Deprecated: As of release 10.0.7, there will no longer be engineering investments made for GetProductAvailabilities and GetAvailableInventoryNearby.</span></span> <span data-ttu-id="e0ec0-149">Organisationer som använder dessa API:er i sina e-handelsdistributioner bör konvertera till nya GetEstimatedAvailability och GetEstimatedProductWarehouseAvailability API:er och aktivera [optimerade beräkningsfunktionen för produkttillgänglighet](https://docs.microsoft.com/dynamics365/commerce/calculated-inventory-retail-channels).</span><span class="sxs-lookup"><span data-stu-id="e0ec0-149">Organizations that use these APIs in their e-Commerce deployments should convert to the new GetEstimatedAvailabilty and GetEstimatedProductWarehouseAvailability APIs and enable the [Optimized product availability calculation feature](https://docs.microsoft.com/dynamics365/commerce/calculated-inventory-retail-channels).</span></span>  |

## <a name="previous-announcements-about-removed-or-deprecated-features"></a><span data-ttu-id="e0ec0-150">Tidigare meddelanden om borttagna eller inaktuella funktioner</span><span class="sxs-lookup"><span data-stu-id="e0ec0-150">Previous announcements about removed or deprecated features</span></span>
<span data-ttu-id="e0ec0-151">Om du vill veta mer om funktioner som har tagits bort eller ersatts i tidigare versioner, se [borttagna eller inaktuella funktioner i tidigare versioner](../../fin-ops-core/dev-itpro/migration-upgrade/deprecated-features.md?toc=/dynamics365/commerce/toc.json).</span><span class="sxs-lookup"><span data-stu-id="e0ec0-151">To learn more about features that have been removed or deprecated in previous releases, see [Removed or deprecated features in previous releases](../../fin-ops-core/dev-itpro/migration-upgrade/deprecated-features.md?toc=/dynamics365/commerce/toc.json).</span></span>
