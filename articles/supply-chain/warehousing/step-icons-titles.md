---
title: Tilldela stegikoner och titlar för mobilappen för Warehouse Management
description: I det här avsnittet beskrivs hur du tilldelar stegikoner och titlar för nya eller anpassade uppgiftsflöden för mobilappen för Warehouse Management.
author: MarkusFogelberg
ms.date: 05/17/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mafoge
ms.search.validFrom: 2021-05-17
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 9523492d766669e6c38579fba7b5ddd6b3d282fc
ms.sourcegitcommit: c53de2c09b9296b41653e739178edf29f79e0679
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/17/2021
ms.locfileid: "6049374"
---
# <a name="assign-step-icons-and-titles-for-the-warehouse-management-mobile-app"></a><span data-ttu-id="fa554-103">Tilldela stegikoner och titlar för mobilappen för Warehouse Management</span><span class="sxs-lookup"><span data-stu-id="fa554-103">Assign step icons and titles for the Warehouse Management mobile app</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="fa554-104">I det här avsnittet beskrivs hur du tilldelar stegikoner och titlar för nya eller anpassade uppgiftsflöden för mobilappen för Warehouse Management.</span><span class="sxs-lookup"><span data-stu-id="fa554-104">This topic describes how to assign step icons and step titles for new or customized task flows for the Warehouse Management mobile app.</span></span>

<span data-ttu-id="fa554-105">Följande illustrationer visar hur stegikoner och titlar visas i mobilappen för Warehouse Management.</span><span class="sxs-lookup"><span data-stu-id="fa554-105">The following illustrations shows how step icons and titles appear in the Warehouse Management mobile app.</span></span>

<span data-ttu-id="fa554-106">![Exempel på en stegikon och en stegrubrik i mobilappen för Warehouse Management](media/step-icon-example.png "Exempel på en stegikon och en stegrubrik i mobilappen för Warehouse Management")</span><span class="sxs-lookup"><span data-stu-id="fa554-106">![Example of a step icon and a step title in the Warehouse Management mobile app](media/step-icon-example.png "Example of a step icon and a step title in the Warehouse Management mobile app")</span></span>

## <a name="turn-on-this-feature-in-your-system"></a><span data-ttu-id="fa554-107">Aktivera funktionen i systemet</span><span class="sxs-lookup"><span data-stu-id="fa554-107">Turn on this feature in your system</span></span>

<span data-ttu-id="fa554-108">Innan du kan använda den här funktionen den aktiveras i ditt system.</span><span class="sxs-lookup"><span data-stu-id="fa554-108">Before you can use this feature, it must be turned on in your system.</span></span> <span data-ttu-id="fa554-109">Administratörer kan använda inställningarna [funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) för att kontrollera funktionens status och aktivera den.</span><span class="sxs-lookup"><span data-stu-id="fa554-109">Admins can use the [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) settings to check the status of the feature and turn it on.</span></span> <span data-ttu-id="fa554-110">I arbetsytan **utgiftshantering** anges den här funktionen på följande sätt:</span><span class="sxs-lookup"><span data-stu-id="fa554-110">In the **Feature management** workspace, the feature is listed in the following way:</span></span>

- <span data-ttu-id="fa554-111">**Modul:** *Lagerstyrning*</span><span class="sxs-lookup"><span data-stu-id="fa554-111">**Module:** *Warehouse management*</span></span>
- <span data-ttu-id="fa554-112">**Funktionsnamn:** *användarinställningar, ikoner och stegrubriker för den nya distributionslagerappen*</span><span class="sxs-lookup"><span data-stu-id="fa554-112">**Feature name:** *User settings, icons, and step titles for the new warehouse app*</span></span>

## <a name="standard-step-ids-classes-and-icons"></a><span data-ttu-id="fa554-113">Standardstegs-ID, klasser och ikoner</span><span class="sxs-lookup"><span data-stu-id="fa554-113">Standard step IDs, classes, and icons</span></span>

<span data-ttu-id="fa554-114">Varje steg i ett uppgiftsflöde identifieras med ett steg-ID och varje steg-ID har en motsvarande stegklass.</span><span class="sxs-lookup"><span data-stu-id="fa554-114">Each step in a task flow is identified by a step ID, and each step ID has a corresponding step class.</span></span> <span data-ttu-id="fa554-115">Stegikonen och rubriken anges i varje stegklass.</span><span class="sxs-lookup"><span data-stu-id="fa554-115">The step icon and title are specified in each step class.</span></span>

### <a name="step-ids-and-step-classes"></a><a name="step-ids-classes"></a><span data-ttu-id="fa554-116">Steg-ID och stegklasser</span><span class="sxs-lookup"><span data-stu-id="fa554-116">Step IDs and step classes</span></span>

<span data-ttu-id="fa554-117">I följande register visas alla steg-ID som för närvarande är tillgängliga, och det är motsvarande stegklass.</span><span class="sxs-lookup"><span data-stu-id="fa554-117">The following table lists every step ID that is currently available, and its corresponding step class.</span></span> <span data-ttu-id="fa554-118">Kontrollnamnet för det primära indatafältet används som steg-ID.</span><span class="sxs-lookup"><span data-stu-id="fa554-118">The control name of the primary input field is used as the step ID.</span></span>

<span data-ttu-id="fa554-119">För ett exempel som visar hur dessa steg-ID och klasser används, se implementeringen av metoden `WHSMobileAppStepInfoBuilder.stepId()` i avsnittet [Exempel: Tilldela stegikoner och titlar för ett anpassat flöde](#example) senare i det här ämnet.</span><span class="sxs-lookup"><span data-stu-id="fa554-119">For an example that shows how these step IDs and classes are used, see the implementation of the `WHSMobileAppStepInfoBuilder.stepId()` method in the [Example: Assign step icons and titles for a custom flow](#example) section later in this topic.</span></span>

| <span data-ttu-id="fa554-120">Steg-ID</span><span class="sxs-lookup"><span data-stu-id="fa554-120">Step ID</span></span> | <span data-ttu-id="fa554-121">Stegklass</span><span class="sxs-lookup"><span data-stu-id="fa554-121">Step Class</span></span> |
|-|-|
| <span data-ttu-id="fa554-122">BatchDisposition</span><span class="sxs-lookup"><span data-stu-id="fa554-122">BatchDisposition</span></span> | <span data-ttu-id="fa554-123">WHSMobileAppStepBatchDisposition</span><span class="sxs-lookup"><span data-stu-id="fa554-123">WHSMobileAppStepBatchDisposition</span></span> |
| <span data-ttu-id="fa554-124">Transportföretag</span><span class="sxs-lookup"><span data-stu-id="fa554-124">Carrier</span></span> | <span data-ttu-id="fa554-125">WHSMobileAppStepCarrier</span><span class="sxs-lookup"><span data-stu-id="fa554-125">WHSMobileAppStepCarrier</span></span> |
| <span data-ttu-id="fa554-126">CatchWeight</span><span class="sxs-lookup"><span data-stu-id="fa554-126">CatchWeight</span></span> | <span data-ttu-id="fa554-127">WHSMobileAppStepCatchWeight</span><span class="sxs-lookup"><span data-stu-id="fa554-127">WHSMobileAppStepCatchWeight</span></span> |
| <span data-ttu-id="fa554-128">CatchWeightQtyOutboundWeight</span><span class="sxs-lookup"><span data-stu-id="fa554-128">CatchWeightQtyOutboundWeight</span></span> | <span data-ttu-id="fa554-129">WHSMobileAppStepCatchWeight</span><span class="sxs-lookup"><span data-stu-id="fa554-129">WHSMobileAppStepCatchWeight</span></span> |
| <span data-ttu-id="fa554-130">CatchWeightTag</span><span class="sxs-lookup"><span data-stu-id="fa554-130">CatchWeightTag</span></span> | <span data-ttu-id="fa554-131">WHSMobileAppStepCatchWeightTag</span><span class="sxs-lookup"><span data-stu-id="fa554-131">WHSMobileAppStepCatchWeightTag</span></span> |
| <span data-ttu-id="fa554-132">CatchWeightTagWeight</span><span class="sxs-lookup"><span data-stu-id="fa554-132">CatchWeightTagWeight</span></span> | <span data-ttu-id="fa554-133">WHSMobileAppStepCatchWeightTagWeight</span><span class="sxs-lookup"><span data-stu-id="fa554-133">WHSMobileAppStepCatchWeightTagWeight</span></span> |
| <span data-ttu-id="fa554-134">ChangeWarehouseSuccess</span><span class="sxs-lookup"><span data-stu-id="fa554-134">ChangeWarehouseSuccess</span></span> | <span data-ttu-id="fa554-135">WHSMobileAppStepChangeWarehouseSuccess</span><span class="sxs-lookup"><span data-stu-id="fa554-135">WHSMobileAppStepChangeWarehouseSuccess</span></span> |
| <span data-ttu-id="fa554-136">CheckDigit</span><span class="sxs-lookup"><span data-stu-id="fa554-136">CheckDigit</span></span> | <span data-ttu-id="fa554-137">WHSMobileAppStepCheckDigit</span><span class="sxs-lookup"><span data-stu-id="fa554-137">WHSMobileAppStepCheckDigit</span></span> |
| <span data-ttu-id="fa554-138">ClusterId</span><span class="sxs-lookup"><span data-stu-id="fa554-138">ClusterId</span></span> | <span data-ttu-id="fa554-139">WHSMobileAppStepClusterId</span><span class="sxs-lookup"><span data-stu-id="fa554-139">WHSMobileAppStepClusterId</span></span> |
| <span data-ttu-id="fa554-140">ClusterPickQtyVerification</span><span class="sxs-lookup"><span data-stu-id="fa554-140">ClusterPickQtyVerification</span></span> | <span data-ttu-id="fa554-141">WHSMobileAppStepQtyVerification</span><span class="sxs-lookup"><span data-stu-id="fa554-141">WHSMobileAppStepQtyVerification</span></span> |
| <span data-ttu-id="fa554-142">ClusterPosition</span><span class="sxs-lookup"><span data-stu-id="fa554-142">ClusterPosition</span></span> | <span data-ttu-id="fa554-143">WHSMobileAppStepClusterPosition</span><span class="sxs-lookup"><span data-stu-id="fa554-143">WHSMobileAppStepClusterPosition</span></span> |
| <span data-ttu-id="fa554-144">ConfigId</span><span class="sxs-lookup"><span data-stu-id="fa554-144">ConfigId</span></span> | <span data-ttu-id="fa554-145">WHSMobileAppStepConfigId</span><span class="sxs-lookup"><span data-stu-id="fa554-145">WHSMobileAppStepConfigId</span></span> |
| <span data-ttu-id="fa554-146">Bekräftelse</span><span class="sxs-lookup"><span data-stu-id="fa554-146">Confirmation</span></span> | <span data-ttu-id="fa554-147">WHSMobileAppStepConfirmation</span><span class="sxs-lookup"><span data-stu-id="fa554-147">WHSMobileAppStepConfirmation</span></span> |
| <span data-ttu-id="fa554-148">ConsolidateFromLicensePlateId</span><span class="sxs-lookup"><span data-stu-id="fa554-148">ConsolidateFromLicensePlateId</span></span> | <span data-ttu-id="fa554-149">WHSMobileAppStepConsolidateFromLicensePlateId</span><span class="sxs-lookup"><span data-stu-id="fa554-149">WHSMobileAppStepConsolidateFromLicensePlateId</span></span> |
| <span data-ttu-id="fa554-150">ConsolidateLPConfirmation</span><span class="sxs-lookup"><span data-stu-id="fa554-150">ConsolidateLPConfirmation</span></span> | <span data-ttu-id="fa554-151">WHSMobileAppStepConsolidateLPConfirmation</span><span class="sxs-lookup"><span data-stu-id="fa554-151">WHSMobileAppStepConsolidateLPConfirmation</span></span> |
| <span data-ttu-id="fa554-152">ConsolidateToLicensePlateId</span><span class="sxs-lookup"><span data-stu-id="fa554-152">ConsolidateToLicensePlateId</span></span> | <span data-ttu-id="fa554-153">WHSMobileAppStepConsolidateToLicensePlateId</span><span class="sxs-lookup"><span data-stu-id="fa554-153">WHSMobileAppStepConsolidateToLicensePlateId</span></span> |
| <span data-ttu-id="fa554-154">ContainerType</span><span class="sxs-lookup"><span data-stu-id="fa554-154">ContainerType</span></span> | <span data-ttu-id="fa554-155">WHSMobileAppStepContainerType</span><span class="sxs-lookup"><span data-stu-id="fa554-155">WHSMobileAppStepContainerType</span></span> |
| <span data-ttu-id="fa554-156">CountingReasonCode</span><span class="sxs-lookup"><span data-stu-id="fa554-156">CountingReasonCode</span></span> | <span data-ttu-id="fa554-157">WHSMobileAppStepCountingReasonCode</span><span class="sxs-lookup"><span data-stu-id="fa554-157">WHSMobileAppStepCountingReasonCode</span></span> |
| <span data-ttu-id="fa554-158">CycleCountingAddLPOrFinish</span><span class="sxs-lookup"><span data-stu-id="fa554-158">CycleCountingAddLPOrFinish</span></span> | <span data-ttu-id="fa554-159">WHSMobileAppStepCycleCountingAddLPOrFinish</span><span class="sxs-lookup"><span data-stu-id="fa554-159">WHSMobileAppStepCycleCountingAddLPOrFinish</span></span> |
| <span data-ttu-id="fa554-160">CycleCountQty1</span><span class="sxs-lookup"><span data-stu-id="fa554-160">CycleCountQty1</span></span> | <span data-ttu-id="fa554-161">WHSMobileAppStepCycleCountQty</span><span class="sxs-lookup"><span data-stu-id="fa554-161">WHSMobileAppStepCycleCountQty</span></span> |
| <span data-ttu-id="fa554-162">CycleCountQty2</span><span class="sxs-lookup"><span data-stu-id="fa554-162">CycleCountQty2</span></span> | <span data-ttu-id="fa554-163">WHSMobileAppStepCycleCountQty</span><span class="sxs-lookup"><span data-stu-id="fa554-163">WHSMobileAppStepCycleCountQty</span></span> |
| <span data-ttu-id="fa554-164">CycleCountQty3</span><span class="sxs-lookup"><span data-stu-id="fa554-164">CycleCountQty3</span></span> | <span data-ttu-id="fa554-165">WHSMobileAppStepCycleCountQty</span><span class="sxs-lookup"><span data-stu-id="fa554-165">WHSMobileAppStepCycleCountQty</span></span> |
| <span data-ttu-id="fa554-166">CycleCountQty4</span><span class="sxs-lookup"><span data-stu-id="fa554-166">CycleCountQty4</span></span> | <span data-ttu-id="fa554-167">WHSMobileAppStepCycleCountQty</span><span class="sxs-lookup"><span data-stu-id="fa554-167">WHSMobileAppStepCycleCountQty</span></span> |
| <span data-ttu-id="fa554-168">Disposition</span><span class="sxs-lookup"><span data-stu-id="fa554-168">Disposition</span></span> | <span data-ttu-id="fa554-169">WHSMobileAppStepDisposition</span><span class="sxs-lookup"><span data-stu-id="fa554-169">WHSMobileAppStepDisposition</span></span> |
| <span data-ttu-id="fa554-170">DriverCheckInConfirmation</span><span class="sxs-lookup"><span data-stu-id="fa554-170">DriverCheckInConfirmation</span></span> | <span data-ttu-id="fa554-171">WHSMobileAppStepDriverCheckInConfirmation</span><span class="sxs-lookup"><span data-stu-id="fa554-171">WHSMobileAppStepDriverCheckInConfirmation</span></span> |
| <span data-ttu-id="fa554-172">DriverCheckInId</span><span class="sxs-lookup"><span data-stu-id="fa554-172">DriverCheckInId</span></span> | <span data-ttu-id="fa554-173">WHSMobileAppStepDriverCheckInId</span><span class="sxs-lookup"><span data-stu-id="fa554-173">WHSMobileAppStepDriverCheckInId</span></span> |
| <span data-ttu-id="fa554-174">DriverCheckOutConfirmation</span><span class="sxs-lookup"><span data-stu-id="fa554-174">DriverCheckOutConfirmation</span></span> | <span data-ttu-id="fa554-175">WHSMobileAppStepDriverCheckOutConfirmation</span><span class="sxs-lookup"><span data-stu-id="fa554-175">WHSMobileAppStepDriverCheckOutConfirmation</span></span> |
| <span data-ttu-id="fa554-176">DriverCheckOutId</span><span class="sxs-lookup"><span data-stu-id="fa554-176">DriverCheckOutId</span></span> | <span data-ttu-id="fa554-177">WHSMobileAppStepDriverCheckOutId</span><span class="sxs-lookup"><span data-stu-id="fa554-177">WHSMobileAppStepDriverCheckOutId</span></span> |
| <span data-ttu-id="fa554-178">ExpDate</span><span class="sxs-lookup"><span data-stu-id="fa554-178">ExpDate</span></span> | <span data-ttu-id="fa554-179">WHSMobileAppStepExpDate</span><span class="sxs-lookup"><span data-stu-id="fa554-179">WHSMobileAppStepExpDate</span></span> |
| <span data-ttu-id="fa554-180">FromBatchDisposition</span><span class="sxs-lookup"><span data-stu-id="fa554-180">FromBatchDisposition</span></span> | <span data-ttu-id="fa554-181">WHSMobileAppStepFromBatchDisposition</span><span class="sxs-lookup"><span data-stu-id="fa554-181">WHSMobileAppStepFromBatchDisposition</span></span> |
| <span data-ttu-id="fa554-182">FromInventoryStatus</span><span class="sxs-lookup"><span data-stu-id="fa554-182">FromInventoryStatus</span></span> | <span data-ttu-id="fa554-183">WHSMobileAppStepInventoryStatusFrom</span><span class="sxs-lookup"><span data-stu-id="fa554-183">WHSMobileAppStepInventoryStatusFrom</span></span> |
| <span data-ttu-id="fa554-184">FullQty</span><span class="sxs-lookup"><span data-stu-id="fa554-184">FullQty</span></span> | <span data-ttu-id="fa554-185">WHSMobileAppStepFullQty</span><span class="sxs-lookup"><span data-stu-id="fa554-185">WHSMobileAppStepFullQty</span></span> |
| <span data-ttu-id="fa554-186">InboundPut</span><span class="sxs-lookup"><span data-stu-id="fa554-186">InboundPut</span></span> | <span data-ttu-id="fa554-187">WHSMobileAppStepInboundPut</span><span class="sxs-lookup"><span data-stu-id="fa554-187">WHSMobileAppStepInboundPut</span></span> |
| <span data-ttu-id="fa554-188">InventBatchId</span><span class="sxs-lookup"><span data-stu-id="fa554-188">InventBatchId</span></span> | <span data-ttu-id="fa554-189">WHSMobileAppStepBatch</span><span class="sxs-lookup"><span data-stu-id="fa554-189">WHSMobileAppStepBatch</span></span> |
| <span data-ttu-id="fa554-190">InventColorId</span><span class="sxs-lookup"><span data-stu-id="fa554-190">InventColorId</span></span> | <span data-ttu-id="fa554-191">WHSMobileAppStepInventColorId</span><span class="sxs-lookup"><span data-stu-id="fa554-191">WHSMobileAppStepInventColorId</span></span> |
| <span data-ttu-id="fa554-192">InventLocation</span><span class="sxs-lookup"><span data-stu-id="fa554-192">InventLocation</span></span> | <span data-ttu-id="fa554-193">WHSMobileAppStepInventLocation</span><span class="sxs-lookup"><span data-stu-id="fa554-193">WHSMobileAppStepInventLocation</span></span> |
| <span data-ttu-id="fa554-194">InventLocationId</span><span class="sxs-lookup"><span data-stu-id="fa554-194">InventLocationId</span></span> | <span data-ttu-id="fa554-195">WHSMobileAppStepWarehouse</span><span class="sxs-lookup"><span data-stu-id="fa554-195">WHSMobileAppStepWarehouse</span></span> |
| <span data-ttu-id="fa554-196">InventSerialId</span><span class="sxs-lookup"><span data-stu-id="fa554-196">InventSerialId</span></span> | <span data-ttu-id="fa554-197">WHSMobileAppStepInventSerialId</span><span class="sxs-lookup"><span data-stu-id="fa554-197">WHSMobileAppStepInventSerialId</span></span> |
| <span data-ttu-id="fa554-198">InventSizeId</span><span class="sxs-lookup"><span data-stu-id="fa554-198">InventSizeId</span></span> | <span data-ttu-id="fa554-199">WHSMobileAppStepInventSizeId</span><span class="sxs-lookup"><span data-stu-id="fa554-199">WHSMobileAppStepInventSizeId</span></span> |
| <span data-ttu-id="fa554-200">InventStatusId</span><span class="sxs-lookup"><span data-stu-id="fa554-200">InventStatusId</span></span> | <span data-ttu-id="fa554-201">WHSMobileAppStepInventStatus</span><span class="sxs-lookup"><span data-stu-id="fa554-201">WHSMobileAppStepInventStatus</span></span> |
| <span data-ttu-id="fa554-202">InventStyleId</span><span class="sxs-lookup"><span data-stu-id="fa554-202">InventStyleId</span></span> | <span data-ttu-id="fa554-203">WHSMobileAppStepInventStyleId</span><span class="sxs-lookup"><span data-stu-id="fa554-203">WHSMobileAppStepInventStyleId</span></span> |
| <span data-ttu-id="fa554-204">InventVersionId</span><span class="sxs-lookup"><span data-stu-id="fa554-204">InventVersionId</span></span> | <span data-ttu-id="fa554-205">WHSMobileAppStepInventVersionId</span><span class="sxs-lookup"><span data-stu-id="fa554-205">WHSMobileAppStepInventVersionId</span></span> |
| <span data-ttu-id="fa554-206">ItemId</span><span class="sxs-lookup"><span data-stu-id="fa554-206">ItemId</span></span> | <span data-ttu-id="fa554-207">WHSMobileAppStepItem</span><span class="sxs-lookup"><span data-stu-id="fa554-207">WHSMobileAppStepItem</span></span> |
| <span data-ttu-id="fa554-208">ITMContainerID</span><span class="sxs-lookup"><span data-stu-id="fa554-208">ITMContainerID</span></span> | <span data-ttu-id="fa554-209">ITMMobileAppStepContainerId</span><span class="sxs-lookup"><span data-stu-id="fa554-209">ITMMobileAppStepContainerId</span></span> |
| <span data-ttu-id="fa554-210">ITMShipmentID</span><span class="sxs-lookup"><span data-stu-id="fa554-210">ITMShipmentID</span></span> | <span data-ttu-id="fa554-211">ITMMobileAppStepShipmentId</span><span class="sxs-lookup"><span data-stu-id="fa554-211">ITMMobileAppStepShipmentId</span></span> |
| <span data-ttu-id="fa554-212">KanbanCardId</span><span class="sxs-lookup"><span data-stu-id="fa554-212">KanbanCardId</span></span> | <span data-ttu-id="fa554-213">WHSMobileAppStepKanbanCard</span><span class="sxs-lookup"><span data-stu-id="fa554-213">WHSMobileAppStepKanbanCard</span></span> |
| <span data-ttu-id="fa554-214">KanbanCardToEmpty</span><span class="sxs-lookup"><span data-stu-id="fa554-214">KanbanCardToEmpty</span></span> | <span data-ttu-id="fa554-215">WHSMobileAppStepKanbanCardToEmpty</span><span class="sxs-lookup"><span data-stu-id="fa554-215">WHSMobileAppStepKanbanCardToEmpty</span></span> |
| <span data-ttu-id="fa554-216">KanbanOrCardId</span><span class="sxs-lookup"><span data-stu-id="fa554-216">KanbanOrCardId</span></span> | <span data-ttu-id="fa554-217">WHSMobileAppStepKanbanCard</span><span class="sxs-lookup"><span data-stu-id="fa554-217">WHSMobileAppStepKanbanCard</span></span> |
| <span data-ttu-id="fa554-218">LicensePlateId</span><span class="sxs-lookup"><span data-stu-id="fa554-218">LicensePlateId</span></span> | <span data-ttu-id="fa554-219">WHSMobileAppStepLicensePlate</span><span class="sxs-lookup"><span data-stu-id="fa554-219">WHSMobileAppStepLicensePlate</span></span> |
| <span data-ttu-id="fa554-220">LoadId</span><span class="sxs-lookup"><span data-stu-id="fa554-220">LoadId</span></span> | <span data-ttu-id="fa554-221">WHSMobileAppStepLoadId</span><span class="sxs-lookup"><span data-stu-id="fa554-221">WHSMobileAppStepLoadId</span></span> |
| <span data-ttu-id="fa554-222">LocationLicensePlatePosition</span><span class="sxs-lookup"><span data-stu-id="fa554-222">LocationLicensePlatePosition</span></span> | <span data-ttu-id="fa554-223">WHSMobileAppStepLocationLicensePlatePosition</span><span class="sxs-lookup"><span data-stu-id="fa554-223">WHSMobileAppStepLocationLicensePlatePosition</span></span> |
| <span data-ttu-id="fa554-224">LocOrLP</span><span class="sxs-lookup"><span data-stu-id="fa554-224">LocOrLP</span></span> | <span data-ttu-id="fa554-225">WHSMobileAppStepLocOrLP</span><span class="sxs-lookup"><span data-stu-id="fa554-225">WHSMobileAppStepLocOrLP</span></span> |
| <span data-ttu-id="fa554-226">LocOrLP_From</span><span class="sxs-lookup"><span data-stu-id="fa554-226">LocOrLP_From</span></span> | <span data-ttu-id="fa554-227">WHSMobileAppStepLocOrLPFrom</span><span class="sxs-lookup"><span data-stu-id="fa554-227">WHSMobileAppStepLocOrLPFrom</span></span> |
| <span data-ttu-id="fa554-228">LocOrLP_To</span><span class="sxs-lookup"><span data-stu-id="fa554-228">LocOrLP_To</span></span> | <span data-ttu-id="fa554-229">WHSMobileAppStepLocOrLPTo</span><span class="sxs-lookup"><span data-stu-id="fa554-229">WHSMobileAppStepLocOrLPTo</span></span> |
| <span data-ttu-id="fa554-230">LocOrLPCheck</span><span class="sxs-lookup"><span data-stu-id="fa554-230">LocOrLPCheck</span></span> | <span data-ttu-id="fa554-231">WHSMobileAppStepLocOrLPCheck</span><span class="sxs-lookup"><span data-stu-id="fa554-231">WHSMobileAppStepLocOrLPCheck</span></span> |
| <span data-ttu-id="fa554-232">LocVerification</span><span class="sxs-lookup"><span data-stu-id="fa554-232">LocVerification</span></span> | <span data-ttu-id="fa554-233">WHSMobileAppStepLocVerification</span><span class="sxs-lookup"><span data-stu-id="fa554-233">WHSMobileAppStepLocVerification</span></span> |
| <span data-ttu-id="fa554-234">LPAdjustIn</span><span class="sxs-lookup"><span data-stu-id="fa554-234">LPAdjustIn</span></span> | <span data-ttu-id="fa554-235">WHSMobileAppStepLPAdjustIn</span><span class="sxs-lookup"><span data-stu-id="fa554-235">WHSMobileAppStepLPAdjustIn</span></span> |
| <span data-ttu-id="fa554-236">LPBreakChildLP</span><span class="sxs-lookup"><span data-stu-id="fa554-236">LPBreakChildLP</span></span> | <span data-ttu-id="fa554-237">WHSMobileAppStepLPBreakChildLP</span><span class="sxs-lookup"><span data-stu-id="fa554-237">WHSMobileAppStepLPBreakChildLP</span></span> |
| <span data-ttu-id="fa554-238">LPBreakParentLP</span><span class="sxs-lookup"><span data-stu-id="fa554-238">LPBreakParentLP</span></span> | <span data-ttu-id="fa554-239">WHSMobileAppStepLPBreakParentLP</span><span class="sxs-lookup"><span data-stu-id="fa554-239">WHSMobileAppStepLPBreakParentLP</span></span> |
| <span data-ttu-id="fa554-240">LPBuildChildLP</span><span class="sxs-lookup"><span data-stu-id="fa554-240">LPBuildChildLP</span></span> | <span data-ttu-id="fa554-241">WHSMobileAppStepLPBuildChildLP</span><span class="sxs-lookup"><span data-stu-id="fa554-241">WHSMobileAppStepLPBuildChildLP</span></span> |
| <span data-ttu-id="fa554-242">LPBuildParentLP</span><span class="sxs-lookup"><span data-stu-id="fa554-242">LPBuildParentLP</span></span> | <span data-ttu-id="fa554-243">WHSMobileAppStepLPBuildParentLP</span><span class="sxs-lookup"><span data-stu-id="fa554-243">WHSMobileAppStepLPBuildParentLP</span></span> |
| <span data-ttu-id="fa554-244">LPVerification</span><span class="sxs-lookup"><span data-stu-id="fa554-244">LPVerification</span></span> | <span data-ttu-id="fa554-245">WHSMobileAppStepLPVerification</span><span class="sxs-lookup"><span data-stu-id="fa554-245">WHSMobileAppStepLPVerification</span></span> |
| <span data-ttu-id="fa554-246">MergeContainerId</span><span class="sxs-lookup"><span data-stu-id="fa554-246">MergeContainerId</span></span> | <span data-ttu-id="fa554-247">WHSMobileAppStepMergeContainerId</span><span class="sxs-lookup"><span data-stu-id="fa554-247">WHSMobileAppStepMergeContainerId</span></span> |
| <span data-ttu-id="fa554-248">MixedLPLineNum</span><span class="sxs-lookup"><span data-stu-id="fa554-248">MixedLPLineNum</span></span> | <span data-ttu-id="fa554-249">WHSMobileAppStepMixedLPLineNum</span><span class="sxs-lookup"><span data-stu-id="fa554-249">WHSMobileAppStepMixedLPLineNum</span></span> |
| <span data-ttu-id="fa554-250">MobileDeviceQueueMessageCollectionIdentifierId</span><span class="sxs-lookup"><span data-stu-id="fa554-250">MobileDeviceQueueMessageCollectionIdentifierId</span></span> | <span data-ttu-id="fa554-251">WHSMobileAppStepSelectOrder</span><span class="sxs-lookup"><span data-stu-id="fa554-251">WHSMobileAppStepSelectOrder</span></span> |
| <span data-ttu-id="fa554-252">MovementConfirmCancel</span><span class="sxs-lookup"><span data-stu-id="fa554-252">MovementConfirmCancel</span></span> | <span data-ttu-id="fa554-253">WHSMobileAppStepMovementConfirmCancel</span><span class="sxs-lookup"><span data-stu-id="fa554-253">WHSMobileAppStepMovementConfirmCancel</span></span> |
| <span data-ttu-id="fa554-254">NewCaptureWeight</span><span class="sxs-lookup"><span data-stu-id="fa554-254">NewCaptureWeight</span></span> | <span data-ttu-id="fa554-255">WHSMobileAppStepCatchWeight</span><span class="sxs-lookup"><span data-stu-id="fa554-255">WHSMobileAppStepCatchWeight</span></span> |
| <span data-ttu-id="fa554-256">NewQty</span><span class="sxs-lookup"><span data-stu-id="fa554-256">NewQty</span></span> | <span data-ttu-id="fa554-257">WHSMobileAppStepNewQty</span><span class="sxs-lookup"><span data-stu-id="fa554-257">WHSMobileAppStepNewQty</span></span> |
| <span data-ttu-id="fa554-258">OutboundCatchWeightTag</span><span class="sxs-lookup"><span data-stu-id="fa554-258">OutboundCatchWeightTag</span></span> | <span data-ttu-id="fa554-259">WHSMobileAppStepCatchWeightTag</span><span class="sxs-lookup"><span data-stu-id="fa554-259">WHSMobileAppStepCatchWeightTag</span></span> |
| <span data-ttu-id="fa554-260">OutboundPut</span><span class="sxs-lookup"><span data-stu-id="fa554-260">OutboundPut</span></span> | <span data-ttu-id="fa554-261">WHSMobileAppStepOutboundPut</span><span class="sxs-lookup"><span data-stu-id="fa554-261">WHSMobileAppStepOutboundPut</span></span> |
| <span data-ttu-id="fa554-262">OutboundWeight</span><span class="sxs-lookup"><span data-stu-id="fa554-262">OutboundWeight</span></span> | <span data-ttu-id="fa554-263">WHSMobileAppStepCatchWeight</span><span class="sxs-lookup"><span data-stu-id="fa554-263">WHSMobileAppStepCatchWeight</span></span> |
| <span data-ttu-id="fa554-264">OverridePutNewLocation</span><span class="sxs-lookup"><span data-stu-id="fa554-264">OverridePutNewLocation</span></span> | <span data-ttu-id="fa554-265">WHSMobileAppStepOverridePutNewLocation</span><span class="sxs-lookup"><span data-stu-id="fa554-265">WHSMobileAppStepOverridePutNewLocation</span></span> |
| <span data-ttu-id="fa554-266">PieceByPieceConfirmation</span><span class="sxs-lookup"><span data-stu-id="fa554-266">PieceByPieceConfirmation</span></span> | <span data-ttu-id="fa554-267">WHSMobileAppStepQtyVerification</span><span class="sxs-lookup"><span data-stu-id="fa554-267">WHSMobileAppStepQtyVerification</span></span> |
| <span data-ttu-id="fa554-268">POLineNum</span><span class="sxs-lookup"><span data-stu-id="fa554-268">POLineNum</span></span> | <span data-ttu-id="fa554-269">WHSMobileAppStepPOLineNum</span><span class="sxs-lookup"><span data-stu-id="fa554-269">WHSMobileAppStepPOLineNum</span></span> |
| <span data-ttu-id="fa554-270">PONum</span><span class="sxs-lookup"><span data-stu-id="fa554-270">PONum</span></span> | <span data-ttu-id="fa554-271">WHSMobileAppStepPONum</span><span class="sxs-lookup"><span data-stu-id="fa554-271">WHSMobileAppStepPONum</span></span> |
| <span data-ttu-id="fa554-272">PositionFull</span><span class="sxs-lookup"><span data-stu-id="fa554-272">PositionFull</span></span> | <span data-ttu-id="fa554-273">WHSMobileAppStepPositionFull</span><span class="sxs-lookup"><span data-stu-id="fa554-273">WHSMobileAppStepPositionFull</span></span> |
| <span data-ttu-id="fa554-274">PositionFullQty</span><span class="sxs-lookup"><span data-stu-id="fa554-274">PositionFullQty</span></span> | <span data-ttu-id="fa554-275">WHSMobileAppStepPositionFullQty</span><span class="sxs-lookup"><span data-stu-id="fa554-275">WHSMobileAppStepPositionFullQty</span></span> |
| <span data-ttu-id="fa554-276">Potens</span><span class="sxs-lookup"><span data-stu-id="fa554-276">Potency</span></span> | <span data-ttu-id="fa554-277">WHSMobileAppStepPotency</span><span class="sxs-lookup"><span data-stu-id="fa554-277">WHSMobileAppStepPotency</span></span> |
| <span data-ttu-id="fa554-278">PrinterName</span><span class="sxs-lookup"><span data-stu-id="fa554-278">PrinterName</span></span> | <span data-ttu-id="fa554-279">WHSMobileAppStepPrinterName</span><span class="sxs-lookup"><span data-stu-id="fa554-279">WHSMobileAppStepPrinterName</span></span> |
| <span data-ttu-id="fa554-280">ProdId</span><span class="sxs-lookup"><span data-stu-id="fa554-280">ProdId</span></span> | <span data-ttu-id="fa554-281">WHSMobileAppStepProdId</span><span class="sxs-lookup"><span data-stu-id="fa554-281">WHSMobileAppStepProdId</span></span> |
| <span data-ttu-id="fa554-282">ProdLastPalletConfirmation</span><span class="sxs-lookup"><span data-stu-id="fa554-282">ProdLastPalletConfirmation</span></span> | <span data-ttu-id="fa554-283">WHSMobileAppStepProdLastPalletConfirmation</span><span class="sxs-lookup"><span data-stu-id="fa554-283">WHSMobileAppStepProdLastPalletConfirmation</span></span> |
| <span data-ttu-id="fa554-284">ProductConfirmation</span><span class="sxs-lookup"><span data-stu-id="fa554-284">ProductConfirmation</span></span> | <span data-ttu-id="fa554-285">WHSMobileAppStepProductConfirmation</span><span class="sxs-lookup"><span data-stu-id="fa554-285">WHSMobileAppStepProductConfirmation</span></span> |
| <span data-ttu-id="fa554-286">ProductionScrapConfirmation</span><span class="sxs-lookup"><span data-stu-id="fa554-286">ProductionScrapConfirmation</span></span> | <span data-ttu-id="fa554-287">WHSMobileAppStepProductionScrapConfirmation</span><span class="sxs-lookup"><span data-stu-id="fa554-287">WHSMobileAppStepProductionScrapConfirmation</span></span> |
| <span data-ttu-id="fa554-288">Placera</span><span class="sxs-lookup"><span data-stu-id="fa554-288">Put</span></span> | <span data-ttu-id="fa554-289">WHSMobileAppStepPut</span><span class="sxs-lookup"><span data-stu-id="fa554-289">WHSMobileAppStepPut</span></span> |
| <span data-ttu-id="fa554-290">PutawayClusterId</span><span class="sxs-lookup"><span data-stu-id="fa554-290">PutawayClusterId</span></span> | <span data-ttu-id="fa554-291">WHSMobileAppStepPutawayClusterId</span><span class="sxs-lookup"><span data-stu-id="fa554-291">WHSMobileAppStepPutawayClusterId</span></span> |
| <span data-ttu-id="fa554-292">Kvantitet</span><span class="sxs-lookup"><span data-stu-id="fa554-292">Qty</span></span> | <span data-ttu-id="fa554-293">WHSMobileAppStepQty</span><span class="sxs-lookup"><span data-stu-id="fa554-293">WHSMobileAppStepQty</span></span> |
| <span data-ttu-id="fa554-294">QtyAdjust</span><span class="sxs-lookup"><span data-stu-id="fa554-294">QtyAdjust</span></span> | <span data-ttu-id="fa554-295">WHSMobileAppStepQtyAdjust</span><span class="sxs-lookup"><span data-stu-id="fa554-295">WHSMobileAppStepQtyAdjust</span></span> |
| <span data-ttu-id="fa554-296">QtyShort</span><span class="sxs-lookup"><span data-stu-id="fa554-296">QtyShort</span></span> | <span data-ttu-id="fa554-297">WHSMobileAppStepQtyShort</span><span class="sxs-lookup"><span data-stu-id="fa554-297">WHSMobileAppStepQtyShort</span></span> |
| <span data-ttu-id="fa554-298">QtyToConsume</span><span class="sxs-lookup"><span data-stu-id="fa554-298">QtyToConsume</span></span> | <span data-ttu-id="fa554-299">WHSMobileAppStepQtyToConsume</span><span class="sxs-lookup"><span data-stu-id="fa554-299">WHSMobileAppStepQtyToConsume</span></span> |
| <span data-ttu-id="fa554-300">QtyToPick</span><span class="sxs-lookup"><span data-stu-id="fa554-300">QtyToPick</span></span> | <span data-ttu-id="fa554-301">WHSMobileAppStepQtyToPick</span><span class="sxs-lookup"><span data-stu-id="fa554-301">WHSMobileAppStepQtyToPick</span></span> |
| <span data-ttu-id="fa554-302">QtyToPut</span><span class="sxs-lookup"><span data-stu-id="fa554-302">QtyToPut</span></span> | <span data-ttu-id="fa554-303">WHSMobileAppStepQtyToPut</span><span class="sxs-lookup"><span data-stu-id="fa554-303">WHSMobileAppStepQtyToPut</span></span> |
| <span data-ttu-id="fa554-304">QtyToScrap</span><span class="sxs-lookup"><span data-stu-id="fa554-304">QtyToScrap</span></span> | <span data-ttu-id="fa554-305">WHSMobileAppStepQtyToScrap</span><span class="sxs-lookup"><span data-stu-id="fa554-305">WHSMobileAppStepQtyToScrap</span></span> |
| <span data-ttu-id="fa554-306">QtyVerification</span><span class="sxs-lookup"><span data-stu-id="fa554-306">QtyVerification</span></span> | <span data-ttu-id="fa554-307">WHSMobileAppStepQtyVerification</span><span class="sxs-lookup"><span data-stu-id="fa554-307">WHSMobileAppStepQtyVerification</span></span> |
| <span data-ttu-id="fa554-308">QtyWithScanningLimit</span><span class="sxs-lookup"><span data-stu-id="fa554-308">QtyWithScanningLimit</span></span> | <span data-ttu-id="fa554-309">WHSMobileAppStepQtyAdjust</span><span class="sxs-lookup"><span data-stu-id="fa554-309">WHSMobileAppStepQtyAdjust</span></span> |
| <span data-ttu-id="fa554-310">ReasonString</span><span class="sxs-lookup"><span data-stu-id="fa554-310">ReasonString</span></span> | <span data-ttu-id="fa554-311">WHSMobileAppStepReasonString</span><span class="sxs-lookup"><span data-stu-id="fa554-311">WHSMobileAppStepReasonString</span></span> |
| <span data-ttu-id="fa554-312">RecvLocationId</span><span class="sxs-lookup"><span data-stu-id="fa554-312">RecvLocationId</span></span> | <span data-ttu-id="fa554-313">WHSMobileAppStepRecvLocationId</span><span class="sxs-lookup"><span data-stu-id="fa554-313">WHSMobileAppStepRecvLocationId</span></span> |
| <span data-ttu-id="fa554-314">RemoveContainerId</span><span class="sxs-lookup"><span data-stu-id="fa554-314">RemoveContainerId</span></span> | <span data-ttu-id="fa554-315">WHSMobileAppStepRemoveContainerId</span><span class="sxs-lookup"><span data-stu-id="fa554-315">WHSMobileAppStepRemoveContainerId</span></span> |
| <span data-ttu-id="fa554-316">ReprintLabelConfirmation</span><span class="sxs-lookup"><span data-stu-id="fa554-316">ReprintLabelConfirmation</span></span> | <span data-ttu-id="fa554-317">WHSMobileAppStepReprintLabelConfirmation</span><span class="sxs-lookup"><span data-stu-id="fa554-317">WHSMobileAppStepReprintLabelConfirmation</span></span> |
| <span data-ttu-id="fa554-318">RMANum</span><span class="sxs-lookup"><span data-stu-id="fa554-318">RMANum</span></span> | <span data-ttu-id="fa554-319">WHSMobileAppStepRMANum</span><span class="sxs-lookup"><span data-stu-id="fa554-319">WHSMobileAppStepRMANum</span></span> |
| <span data-ttu-id="fa554-320">ShortPickReason</span><span class="sxs-lookup"><span data-stu-id="fa554-320">ShortPickReason</span></span> | <span data-ttu-id="fa554-321">WHSMobileAppStepShortPickReason</span><span class="sxs-lookup"><span data-stu-id="fa554-321">WHSMobileAppStepShortPickReason</span></span> |
| <span data-ttu-id="fa554-322">SortConOrLP</span><span class="sxs-lookup"><span data-stu-id="fa554-322">SortConOrLP</span></span> | <span data-ttu-id="fa554-323">WHSMobileAppStepSortConOrLP</span><span class="sxs-lookup"><span data-stu-id="fa554-323">WHSMobileAppStepSortConOrLP</span></span> |
| <span data-ttu-id="fa554-324">SortLicensePlateId</span><span class="sxs-lookup"><span data-stu-id="fa554-324">SortLicensePlateId</span></span> | <span data-ttu-id="fa554-325">WHSMobileAppStepSortLicensePlateId</span><span class="sxs-lookup"><span data-stu-id="fa554-325">WHSMobileAppStepSortLicensePlateId</span></span> |
| <span data-ttu-id="fa554-326">SortPositionId</span><span class="sxs-lookup"><span data-stu-id="fa554-326">SortPositionId</span></span> | <span data-ttu-id="fa554-327">WHSMobileAppStepSortPositionId</span><span class="sxs-lookup"><span data-stu-id="fa554-327">WHSMobileAppStepSortPositionId</span></span> |
| <span data-ttu-id="fa554-328">SortVerification</span><span class="sxs-lookup"><span data-stu-id="fa554-328">SortVerification</span></span> | <span data-ttu-id="fa554-329">WHSMobileAppStepSortVerification</span><span class="sxs-lookup"><span data-stu-id="fa554-329">WHSMobileAppStepSortVerification</span></span> |
| <span data-ttu-id="fa554-330">StartLocationId</span><span class="sxs-lookup"><span data-stu-id="fa554-330">StartLocationId</span></span> | <span data-ttu-id="fa554-331">WHSMobileAppStepStartLocationId</span><span class="sxs-lookup"><span data-stu-id="fa554-331">WHSMobileAppStepStartLocationId</span></span> |
| <span data-ttu-id="fa554-332">StartProdOrderConfirmation</span><span class="sxs-lookup"><span data-stu-id="fa554-332">StartProdOrderConfirmation</span></span> | <span data-ttu-id="fa554-333">WHSMobileAppStepStartProdOrderConfirmation</span><span class="sxs-lookup"><span data-stu-id="fa554-333">WHSMobileAppStepStartProdOrderConfirmation</span></span> |
| <span data-ttu-id="fa554-334">TargetLicensePlateId</span><span class="sxs-lookup"><span data-stu-id="fa554-334">TargetLicensePlateId</span></span> | <span data-ttu-id="fa554-335">WHSMobileAppStepTargetLicensePlateId</span><span class="sxs-lookup"><span data-stu-id="fa554-335">WHSMobileAppStepTargetLicensePlateId</span></span> |
| <span data-ttu-id="fa554-336">TOLineNum</span><span class="sxs-lookup"><span data-stu-id="fa554-336">TOLineNum</span></span> | <span data-ttu-id="fa554-337">WHSMobileAppStepTOLineNum</span><span class="sxs-lookup"><span data-stu-id="fa554-337">WHSMobileAppStepTOLineNum</span></span> |
| <span data-ttu-id="fa554-338">ToLocation</span><span class="sxs-lookup"><span data-stu-id="fa554-338">ToLocation</span></span> | <span data-ttu-id="fa554-339">WHSMobileAppStepToLocation</span><span class="sxs-lookup"><span data-stu-id="fa554-339">WHSMobileAppStepToLocation</span></span> |
| <span data-ttu-id="fa554-340">TONum</span><span class="sxs-lookup"><span data-stu-id="fa554-340">TONum</span></span> | <span data-ttu-id="fa554-341">WHSMobileAppStepTONum</span><span class="sxs-lookup"><span data-stu-id="fa554-341">WHSMobileAppStepTONum</span></span> |
| <span data-ttu-id="fa554-342">ToWarehouse</span><span class="sxs-lookup"><span data-stu-id="fa554-342">ToWarehouse</span></span> | <span data-ttu-id="fa554-343">WHSMobileAppStepWarehouseTo</span><span class="sxs-lookup"><span data-stu-id="fa554-343">WHSMobileAppStepWarehouseTo</span></span> |
| <span data-ttu-id="fa554-344">TransportLoadId</span><span class="sxs-lookup"><span data-stu-id="fa554-344">TransportLoadId</span></span> | <span data-ttu-id="fa554-345">WHSMobileAppStepTransportLoadId</span><span class="sxs-lookup"><span data-stu-id="fa554-345">WHSMobileAppStepTransportLoadId</span></span> |
| <span data-ttu-id="fa554-346">WaveLabelId</span><span class="sxs-lookup"><span data-stu-id="fa554-346">WaveLabelId</span></span> | <span data-ttu-id="fa554-347">WHSMobileAppStepWaveLabelId</span><span class="sxs-lookup"><span data-stu-id="fa554-347">WHSMobileAppStepWaveLabelId</span></span> |
| <span data-ttu-id="fa554-348">WaveLblQty</span><span class="sxs-lookup"><span data-stu-id="fa554-348">WaveLblQty</span></span> | <span data-ttu-id="fa554-349">WHSMobileAppStepWaveLblQty</span><span class="sxs-lookup"><span data-stu-id="fa554-349">WHSMobileAppStepWaveLblQty</span></span> |
| <span data-ttu-id="fa554-350">Vikt</span><span class="sxs-lookup"><span data-stu-id="fa554-350">Weight</span></span> | <span data-ttu-id="fa554-351">WHSMobileAppStepWeight</span><span class="sxs-lookup"><span data-stu-id="fa554-351">WHSMobileAppStepWeight</span></span> |
| <span data-ttu-id="fa554-352">WeightToConsume</span><span class="sxs-lookup"><span data-stu-id="fa554-352">WeightToConsume</span></span> | <span data-ttu-id="fa554-353">WHSMobileAppStepWeightToConsume</span><span class="sxs-lookup"><span data-stu-id="fa554-353">WHSMobileAppStepWeightToConsume</span></span> |
| <span data-ttu-id="fa554-354">WHSAdjustmentType</span><span class="sxs-lookup"><span data-stu-id="fa554-354">WHSAdjustmentType</span></span> | <span data-ttu-id="fa554-355">WHSMobileAppStepWHSAdjustmentType</span><span class="sxs-lookup"><span data-stu-id="fa554-355">WHSMobileAppStepWHSAdjustmentType</span></span> |
| <span data-ttu-id="fa554-356">WHSReceivingException</span><span class="sxs-lookup"><span data-stu-id="fa554-356">WHSReceivingException</span></span> | <span data-ttu-id="fa554-357">WHSMobileAppStepWHSReceivingException</span><span class="sxs-lookup"><span data-stu-id="fa554-357">WHSMobileAppStepWHSReceivingException</span></span> |
| <span data-ttu-id="fa554-358">WHSWorkException</span><span class="sxs-lookup"><span data-stu-id="fa554-358">WHSWorkException</span></span> | <span data-ttu-id="fa554-359">WHSMobileAppStepWHSWorkException</span><span class="sxs-lookup"><span data-stu-id="fa554-359">WHSMobileAppStepWHSWorkException</span></span> |
| <span data-ttu-id="fa554-360">WHSWorkLicensePlateId</span><span class="sxs-lookup"><span data-stu-id="fa554-360">WHSWorkLicensePlateId</span></span> | <span data-ttu-id="fa554-361">WHSMobileAppStepWorkLicensePlateId</span><span class="sxs-lookup"><span data-stu-id="fa554-361">WHSMobileAppStepWorkLicensePlateId</span></span> |
| <span data-ttu-id="fa554-362">WMSLocationId</span><span class="sxs-lookup"><span data-stu-id="fa554-362">WMSLocationId</span></span> | <span data-ttu-id="fa554-363">WHSMobileAppStepLocation</span><span class="sxs-lookup"><span data-stu-id="fa554-363">WHSMobileAppStepLocation</span></span> |
| <span data-ttu-id="fa554-364">WorkId</span><span class="sxs-lookup"><span data-stu-id="fa554-364">WorkId</span></span> | <span data-ttu-id="fa554-365">WHSMobileAppStepWorkId</span><span class="sxs-lookup"><span data-stu-id="fa554-365">WHSMobileAppStepWorkId</span></span> |
| <span data-ttu-id="fa554-366">WorkIdToCancel</span><span class="sxs-lookup"><span data-stu-id="fa554-366">WorkIdToCancel</span></span> | <span data-ttu-id="fa554-367">WHSMobileAppStepWorkIdToCancel</span><span class="sxs-lookup"><span data-stu-id="fa554-367">WHSMobileAppStepWorkIdToCancel</span></span> |
| <span data-ttu-id="fa554-368">WorkLPIdPutawayCluster</span><span class="sxs-lookup"><span data-stu-id="fa554-368">WorkLPIdPutawayCluster</span></span> | <span data-ttu-id="fa554-369">WHSMobileAppStepWorkLPIdPutawayCluster</span><span class="sxs-lookup"><span data-stu-id="fa554-369">WHSMobileAppStepWorkLPIdPutawayCluster</span></span> |
| <span data-ttu-id="fa554-370">WorkPoolId</span><span class="sxs-lookup"><span data-stu-id="fa554-370">WorkPoolId</span></span> | <span data-ttu-id="fa554-371">WHSMobileAppStepWorkPoolId</span><span class="sxs-lookup"><span data-stu-id="fa554-371">WHSMobileAppStepWorkPoolId</span></span> |
| <span data-ttu-id="fa554-372">ZoneId</span><span class="sxs-lookup"><span data-stu-id="fa554-372">ZoneId</span></span> | <span data-ttu-id="fa554-373">WHSMobileAppStepZoneId</span><span class="sxs-lookup"><span data-stu-id="fa554-373">WHSMobileAppStepZoneId</span></span> |

### <a name="available-step-icons"></a><a name="step-icons"></a><span data-ttu-id="fa554-374">Tillgängliga stegikoner</span><span class="sxs-lookup"><span data-stu-id="fa554-374">Available step icons</span></span>

<span data-ttu-id="fa554-375">Systemet innehåller en samling standardstegsikoner som du också kan använda för dina anpassade steg.</span><span class="sxs-lookup"><span data-stu-id="fa554-375">The system includes a collection of standard step icons that you can also use for your custom steps.</span></span> <span data-ttu-id="fa554-376">Det går inte att föra över anpassade stegikoner.</span><span class="sxs-lookup"><span data-stu-id="fa554-376">You can't currently upload custom step icons.</span></span> <span data-ttu-id="fa554-377">Därför måste du alltid välja en av standardstegikonerna.</span><span class="sxs-lookup"><span data-stu-id="fa554-377">Therefore, you must always select one of the standard step icons.</span></span>

<span data-ttu-id="fa554-378">I följande tabell visas alla standardstegsikoner som för närvarande är tillgängliga, samt dess namn.</span><span class="sxs-lookup"><span data-stu-id="fa554-378">The following table shows every standard step icon that is currently available, and its name.</span></span>

<table>
<tbody>
<tr>
<td><img src="media/step-icons-about.png" alt="About step icon" title="Om stegikon"><br><span data-ttu-id="fa554-380">Om</span><span class="sxs-lookup"><span data-stu-id="fa554-380">About</span></span></td>
<td><img src="media/step-icons-add-lp.png" alt="Add license plate or item step icon" title="Lägg till licens- eller artikelstegsikon"><br><span data-ttu-id="fa554-382">AddLpOrItem</span><span class="sxs-lookup"><span data-stu-id="fa554-382">AddLpOrItem</span></span></td>
<td><img src="media/step-icons-batch-disposition.png" alt="Batch disposition step icon" title="Stegikon för batchdisposition"><br><span data-ttu-id="fa554-384">BatchDisposition</span><span class="sxs-lookup"><span data-stu-id="fa554-384">BatchDisposition</span></span></td>
<td><img src="media/step-icons-carrier.png" alt="Carrier step icon" title="Stegikonen transportföretag"><br><span data-ttu-id="fa554-386">Transportföretag</span><span class="sxs-lookup"><span data-stu-id="fa554-386">Carrier</span></span></td>
</tr>
<tr>
<td><img src="media/step-icons-cw-tag.png" alt="Catch weight tag step icon" title="Stegikonen tagg för faktisk/nominell vikt"><br><span data-ttu-id="fa554-388">CatchWeightTag</span><span class="sxs-lookup"><span data-stu-id="fa554-388">CatchWeightTag</span></span></td>
<td><img src="media/step-icons-cw-tag-weight.png" alt="Catch weight tag weight step icon" title="Stegikonen för vikt tagg för faktisk/nominell vikt"><br><span data-ttu-id="fa554-390">CatchWeightTagWeight</span><span class="sxs-lookup"><span data-stu-id="fa554-390">CatchWeightTagWeight</span></span></td>
<td><img src="media/step-icons-check-digit.png" alt="Check digit step icon" title="Stegikonen kontrollsiffra"><br><span data-ttu-id="fa554-392">CheckDigit</span><span class="sxs-lookup"><span data-stu-id="fa554-392">CheckDigit</span></span></td>
<td><img src="media/step-icons-check-in-out.png" alt="Check in or out ID step icon" title="Stegikonen checka in eller checka ut ID"><br><span data-ttu-id="fa554-394">CheckInOutId</span><span class="sxs-lookup"><span data-stu-id="fa554-394">CheckInOutId</span></span></td>
</tr>
<tr>
<td><img src="media/step-icons-child-lp.png" alt="Child license plate step icon" title="Stegikonen för underordnat ID-nummer"><br><span data-ttu-id="fa554-396">ChildLP</span><span class="sxs-lookup"><span data-stu-id="fa554-396">ChildLP</span></span></td>
<td><img src="media/step-icons-cluster-id.png" alt="Cluster ID step icon" title="Stegikon för kluster-ID"><br><span data-ttu-id="fa554-398">ClusterId</span><span class="sxs-lookup"><span data-stu-id="fa554-398">ClusterId</span></span></td>
<td><img src="media/step-icons-cluster-position.png" alt="Cluster position step icon" title="Stegikon för klusterposition"><br><span data-ttu-id="fa554-400">ClusterPosition</span><span class="sxs-lookup"><span data-stu-id="fa554-400">ClusterPosition</span></span></td>
<td><img src="media/step-icons-config-id.png" alt="Config ID step icon" title="Stegikon för konfig-ID"><br><span data-ttu-id="fa554-402">ConfigId</span><span class="sxs-lookup"><span data-stu-id="fa554-402">ConfigId</span></span></td>
</tr>
<tr>
<td><img src="media/step-icons-configured-field.png" alt="Configured field step icon" title="Stegikonen konfiguration av fält"><br><span data-ttu-id="fa554-404">ConfiguredField</span><span class="sxs-lookup"><span data-stu-id="fa554-404">ConfiguredField</span></span></td>
<td><img src="media/step-icons-con-lp.png" alt="Con or LP step icon" title="Stegikonen Con eller LP"><br><span data-ttu-id="fa554-406">ConOrLP</span><span class="sxs-lookup"><span data-stu-id="fa554-406">ConOrLP</span></span></td>
<td><img src="media/step-icons-consolidate-from-LP.png" alt="Consolidate from license plate ID step icon" title="Konsolidering från licens- eller ID-stegikonen"><br><span data-ttu-id="fa554-408">ConsolidateFromLicensePlateID</span><span class="sxs-lookup"><span data-stu-id="fa554-408">ConsolidateFromLicensePlateID</span></span></td>
<td><img src="media/step-icons-consolidate-to-LP.png" alt="Consolidate to license plate ID step icon" title="Konsolidering till licens- eller ID-stegikonen"><br><span data-ttu-id="fa554-410">ConsolidateToLicensePlateID</span><span class="sxs-lookup"><span data-stu-id="fa554-410">ConsolidateToLicensePlateID</span></span></td>
</tr>
<tr>
<td><img src="media/step-icons-container-type.png" alt="Container type step icon" title="Stegikon för behållartyp"><br><span data-ttu-id="fa554-412">ContainerType</span><span class="sxs-lookup"><span data-stu-id="fa554-412">ContainerType</span></span></td>
<td><img src="media/step-icons-counting.png" alt="Counting step icon" title="Stegikonen inventering"><br><span data-ttu-id="fa554-414">Inventering</span><span class="sxs-lookup"><span data-stu-id="fa554-414">Counting</span></span></td>
<td><img src="media/step-icons-counting-reason.png" alt="Counting reason code step icon" title="Stegikon för inventeringsorsakskoder"><br><span data-ttu-id="fa554-416">CountingReasonCode</span><span class="sxs-lookup"><span data-stu-id="fa554-416">CountingReasonCode</span></span></td>
<td><img src="media/step-icons-country-origin.png" alt="Country of origin code step icon" title="Stegikon för kod för ursprungsland"><br><span data-ttu-id="fa554-418">CountryOfOrigin</span><span class="sxs-lookup"><span data-stu-id="fa554-418">CountryOfOrigin</span></span></td>
</tr>
<tr>
<td><img src="media/step-icons-disposition.png" alt="Disposition step icon" title="Stegikon för disposition"><br><span data-ttu-id="fa554-420">Disposition</span><span class="sxs-lookup"><span data-stu-id="fa554-420">Disposition</span></span></td>
<td><img src="media/step-icons-done.png" alt="Done step icon" title="Stegikonen klart"><br><span data-ttu-id="fa554-422">Klart</span><span class="sxs-lookup"><span data-stu-id="fa554-422">Done</span></span></td>
<td><img src="media/step-icons-driver-check-in-confirmation.png" alt="Driver check in confirmation step icon" title="Stegikon för incheckning förare i bekräftelsesteg"><br><span data-ttu-id="fa554-424">DriverCheckInConfirmation</span><span class="sxs-lookup"><span data-stu-id="fa554-424">DriverCheckInConfirmation</span></span></td>
<td><img src="media/step-icons-driver-check-in-id.png" alt="Driver check in ID step icon" title="Stegikonen inchecknings-ID förare"><br><span data-ttu-id="fa554-426">DriverCheckInId</span><span class="sxs-lookup"><span data-stu-id="fa554-426">DriverCheckInId</span></span></td>
</tr>
<tr>
<td><img src="media/step-icons-driver-check-out-id.png" alt="Driver check out ID step icon" title="Stegikonen utchecknings-ID förare"><br><span data-ttu-id="fa554-428">DriverCheckOutId</span><span class="sxs-lookup"><span data-stu-id="fa554-428">DriverCheckOutId</span></span></td>
<td><img src="media/step-icons-exp-date.png" alt="Expiration date step icon" title="Stegikonen Utgångsdatum"><br><span data-ttu-id="fa554-430">ExpDate</span><span class="sxs-lookup"><span data-stu-id="fa554-430">ExpDate</span></span></td>
<td><img src="media/step-icons-field.png" alt="Field step icon" title="Stegikonen fält"><br><span data-ttu-id="fa554-432">Fält</span><span class="sxs-lookup"><span data-stu-id="fa554-432">Field</span></span></td>
<td><img src="media/step-icons-from-batch.png" alt="From batch disposition step icon" title="Stegikon från batchdisposition"><br><span data-ttu-id="fa554-434">FromBatchDisposition</span><span class="sxs-lookup"><span data-stu-id="fa554-434">FromBatchDisposition</span></span></td>
</tr>
<tr>
<td><img src="media/step-icons-from-inventory-status.png" alt="From inventory status step icon" title="Stegikonen lagerstatus"><br><span data-ttu-id="fa554-436">FromInventoryStatus</span><span class="sxs-lookup"><span data-stu-id="fa554-436">FromInventoryStatus</span></span></td>
<td><img src="media/step-icons-id-attribute.png" alt="ID attribute step icon" title="Stegikon för ID-attribut"><br><span data-ttu-id="fa554-438">IdAttribute</span><span class="sxs-lookup"><span data-stu-id="fa554-438">IdAttribute</span></span></td>
<td><img src="media/step-icons-invent-batch-id.png" alt="Inventory batch ID step icon" title="Stegikon för batch-ID för lager"><br><span data-ttu-id="fa554-440">InventBatchID</span><span class="sxs-lookup"><span data-stu-id="fa554-440">InventBatchID</span></span></td>
<td><img src="media/step-icons-invent-color-id.png" alt="Inventory color ID step icon" title="Stegikon för färg-ID för lager"><br><span data-ttu-id="fa554-442">InventColorID</span><span class="sxs-lookup"><span data-stu-id="fa554-442">InventColorID</span></span></td>
</tr>
<tr>
<td><img src="media/step-icons-invent-location.png" alt="Inventory location step icon" title="Stegikon för lagerplats"><br><span data-ttu-id="fa554-444">InventLocation</span><span class="sxs-lookup"><span data-stu-id="fa554-444">InventLocation</span></span></td>
<td><img src="media/step-icons-invent-serial-id.png" alt="Inventory serial ID step icon" title="Stegikon för seriell-ID för lager"><br><span data-ttu-id="fa554-446">InventSerialID</span><span class="sxs-lookup"><span data-stu-id="fa554-446">InventSerialID</span></span></td>
<td><img src="media/step-icons-invent-size-id.png" alt="Inventory size ID step icon" title="Stegikon för storleks-ID för lager"><br><span data-ttu-id="fa554-448">InventSizeID</span><span class="sxs-lookup"><span data-stu-id="fa554-448">InventSizeID</span></span></td>
<td><img src="media/step-icons-invent-status-id.png" alt="Inventory status ID step icon" title="Stegikonen lagerstatus-ID"><br><span data-ttu-id="fa554-450">InventStatusID</span><span class="sxs-lookup"><span data-stu-id="fa554-450">InventStatusID</span></span></td>
</tr>
<tr>
<td><img src="media/step-icons-invent-style-id.png" alt="Inventory style ID step icon" title="Stegikon för storleks-ID för lager"><br><span data-ttu-id="fa554-452">InventStyleID</span><span class="sxs-lookup"><span data-stu-id="fa554-452">InventStyleID</span></span></td>
<td><img src="media/step-icons-invent-version-id.png" alt="Inventory version ID step icon" title="Stegikonen lagerversions-ID"><br><span data-ttu-id="fa554-454">InventVersionID</span><span class="sxs-lookup"><span data-stu-id="fa554-454">InventVersionID</span></span></td>
<td><img src="media/step-icons-item-id.png" alt="Item ID step icon" title="Stegikon för objekt-ID"><br><span data-ttu-id="fa554-456">ItemID</span><span class="sxs-lookup"><span data-stu-id="fa554-456">ItemID</span></span></td>
<td><img src="media/step-icons-itm-contianer-id.png" alt="ITM container ID step icon" title="Stegikon för ITM behållar-ID"><br><span data-ttu-id="fa554-458">ITMContainerID</span><span class="sxs-lookup"><span data-stu-id="fa554-458">ITMContainerID</span></span></td>
</tr>
<tr>
<td><img src="media/step-icons-itm-shipment-id.png" alt="ITM shipment ID step icon" title="Stegikon för ITM försändelse-ID"><br><span data-ttu-id="fa554-460">ITMShipmentID</span><span class="sxs-lookup"><span data-stu-id="fa554-460">ITMShipmentID</span></span></td>
<td><img src="media/step-icons-kanban-card-id.png" alt="Kanban card ID step icon" title="Stegikon för Kanban-kort-ID"><br><span data-ttu-id="fa554-462">KanbanCardID</span><span class="sxs-lookup"><span data-stu-id="fa554-462">KanbanCardID</span></span></td>
<td><img src="media/step-icons-kanban-or-card-id.png" alt="Kanban or card ID step icon" title="Stegikon för Kanban eller kort-ID"><br><span data-ttu-id="fa554-464">KanbanOrCardID</span><span class="sxs-lookup"><span data-stu-id="fa554-464">KanbanOrCardID</span></span></td>
<td><img src="media/step-icons-license-plate-id.png" alt="License plate ID step icon" title="Stegikonen för ID-nummer"><br><span data-ttu-id="fa554-466">LicensePlateID</span><span class="sxs-lookup"><span data-stu-id="fa554-466">LicensePlateID</span></span></td>
</tr>
<tr>
<td><img src="media/step-icons-load-id.png" alt="Load ID step icon" title="Stegikon för last-ID"><br><span data-ttu-id="fa554-468">LoadId</span><span class="sxs-lookup"><span data-stu-id="fa554-468">LoadId</span></span></td>
<td><img src="media/step-icons-location-lp-pos.png" alt="Location license plate position step icon" title="Stegikon för position-ID-nummer"><br><span data-ttu-id="fa554-470">LocationLicensePlatePosition</span><span class="sxs-lookup"><span data-stu-id="fa554-470">LocationLicensePlatePosition</span></span></td>
<td><img src="media/step-icons-location-or-lp.png" alt="Location or license plate step icon" title="Stegikon för plats- eller ID-nummer"><br><span data-ttu-id="fa554-472">LocOrLP</span><span class="sxs-lookup"><span data-stu-id="fa554-472">LocOrLP</span></span></td>
<td><img src="media/step-icons-location-or-lp-check.png" alt="Location or license plate check step icon" title="Stegikon för kontroll av plats- eller ID-nummer"><br><span data-ttu-id="fa554-474">LocOrLPCheck</span><span class="sxs-lookup"><span data-stu-id="fa554-474">LocOrLPCheck</span></span></td>
</tr>
<tr>
<td><img src="media/step-icons-location-or-lp-from.png" alt="Location or license plate from step icon" title="Stegikon från plats- eller ID-nummer"><br><span data-ttu-id="fa554-476">LocOrLPFrom</span><span class="sxs-lookup"><span data-stu-id="fa554-476">LocOrLPFrom</span></span></td>
<td><img src="media/step-icons-location-or-lp-to.png" alt="Location or license plate to step icon" title="Stegikon till plats- eller ID-nummer"><br><span data-ttu-id="fa554-478">LocOrLPTo</span><span class="sxs-lookup"><span data-stu-id="fa554-478">LocOrLPTo</span></span></td>
<td><img src="media/step-icons-long-process-complete.png" alt="Long process completed step icon" title="Stegikon för långt process slutförd"><br><span data-ttu-id="fa554-480">LongProcessCompleted</span><span class="sxs-lookup"><span data-stu-id="fa554-480">LongProcessCompleted</span></span></td>
<td><img src="media/step-icons-lp-break-parent.png" alt="LP break parent LP step icon" title="Stegikon för LP-paus överordnad LP"><br><span data-ttu-id="fa554-482">LPBreakParentLP</span><span class="sxs-lookup"><span data-stu-id="fa554-482">LPBreakParentLP</span></span></td>
</tr>
<tr>
<td><img src="media/step-icons-merge-container.png" alt="Merge container ID step icon" title="Stegikon för sammanslå behållar-ID"><br><span data-ttu-id="fa554-484">MergeContainerId</span><span class="sxs-lookup"><span data-stu-id="fa554-484">MergeContainerId</span></span></td>
<td><img src="media/step-icons-mixed-lp-line.png" alt="Mixed license plate line number step icon" title="Stegikon för blandat ID-radnummer"><br><span data-ttu-id="fa554-486">MixedLPLineNum</span><span class="sxs-lookup"><span data-stu-id="fa554-486">MixedLPLineNum</span></span></td>
<td><img src="media/step-icons-outbound-weight.png" alt="Outbound weight step icon" title="Stegikon för utgående vikt"><br><span data-ttu-id="fa554-488">OutboundWeight</span><span class="sxs-lookup"><span data-stu-id="fa554-488">OutboundWeight</span></span></td>
<td><img src="media/step-icons-owner.png" alt="Owner step icon" title="Stegikon för ägare"><br><span data-ttu-id="fa554-490">Ägare</span><span class="sxs-lookup"><span data-stu-id="fa554-490">Owner</span></span></td>
</tr>
<tr>
<td><img src="media/step-icons-parent-lp.png" alt="Parent license plate step icon" title="Stegikon för överordnat ID-nummer"><br><span data-ttu-id="fa554-492">ParentLP</span><span class="sxs-lookup"><span data-stu-id="fa554-492">ParentLP</span></span></td>
<td><img src="media/step-icons-please-confirm.png" alt="Please confirm step icon" title="Stegikonen bekräfta"><br><span data-ttu-id="fa554-494">Bekräfta gärna</span><span class="sxs-lookup"><span data-stu-id="fa554-494">PleaseConfirm</span></span></td>
<td><img src="media/step-icons-po-line-num.png" alt="Purchase order line number step icon" title="Stegikonen inköpsorderradnummer"><br><span data-ttu-id="fa554-496">POLineNum</span><span class="sxs-lookup"><span data-stu-id="fa554-496">POLineNum</span></span></td>
<td><img src="media/step-icons-po-num.png" alt="Purchase order number step icon" title="Stegikonen inköpsordernummer"><br><span data-ttu-id="fa554-498">PONum</span><span class="sxs-lookup"><span data-stu-id="fa554-498">PONum</span></span></td>
</tr>
<tr>
<td><img src="media/step-icons-position-full.png" alt="Position full step icon" title="Stegikon för position full"><br><span data-ttu-id="fa554-500">PositionFull</span><span class="sxs-lookup"><span data-stu-id="fa554-500">PositionFull</span></span></td>
<td><img src="media/step-icons-potency.png" alt="Potency step icon" title="Stegikon för potens"><br><span data-ttu-id="fa554-502">Potens</span><span class="sxs-lookup"><span data-stu-id="fa554-502">Potency</span></span></td>
<td><img src="media/step-icons-printer-name.png" alt="Printer name step icon" title="Stegikon för skrivarnamn"><br><span data-ttu-id="fa554-504">PrinterName</span><span class="sxs-lookup"><span data-stu-id="fa554-504">PrinterName</span></span></td>
<td><img src="media/step-icons-prod-id.png" alt="Prod ID step icon" title="Stegikon för prod-ID"><br><span data-ttu-id="fa554-506">ProdId</span><span class="sxs-lookup"><span data-stu-id="fa554-506">ProdId</span></span></td>
</tr>
<tr>
<td><img src="media/step-icons-product-confirm.png" alt="Product confirmation step icon" title="Stegikon för produktbekräftelse"><br><span data-ttu-id="fa554-508">ProductConfirmation</span><span class="sxs-lookup"><span data-stu-id="fa554-508">ProductConfirmation</span></span></td>
<td><img src="media/step-icons-put.png" alt="Put step icon" title="Stegikon för placera"><br><span data-ttu-id="fa554-510">Placera</span><span class="sxs-lookup"><span data-stu-id="fa554-510">Put</span></span></td>
<td><img src="media/step-icons-putaway-cluster-id.png" alt="Putaway cluster ID step icon" title="Stegikon för kluster för artikelinförsel"><br><span data-ttu-id="fa554-512">PutawayClusterId</span><span class="sxs-lookup"><span data-stu-id="fa554-512">PutawayClusterId</span></span></td>
<td><img src="media/step-icons-qty.png" alt="Quantity step icon" title="Stegikonen kvantitet"><br><span data-ttu-id="fa554-514">Kvantitet</span><span class="sxs-lookup"><span data-stu-id="fa554-514">Qty</span></span></td>
</tr>
<tr>
<td><img src="media/step-icons-qty-adjust-in.png" alt="Quantity adjust in step icon" title="Stegikonen kvantitetsjustering"><br><span data-ttu-id="fa554-516">QtyAdjustIn</span><span class="sxs-lookup"><span data-stu-id="fa554-516">QtyAdjustIn</span></span></td>
<td><img src="media/step-icons-qty-short.png" alt="Quantity short step icon" title="Stegikonen kvantitet kort"><br><span data-ttu-id="fa554-518">QtyShort</span><span class="sxs-lookup"><span data-stu-id="fa554-518">QtyShort</span></span></td>
<td><img src="media/step-icons-qty-to-consume.png" alt="Quantity to consume step icon" title="Stegikon för kvantitet som ska förbrukas"><br><span data-ttu-id="fa554-520">QtyToConsume</span><span class="sxs-lookup"><span data-stu-id="fa554-520">QtyToConsume</span></span></td>
<td><img src="media/step-icons-qty-to-put.png" alt="Quantity to put step icon" title="Stegikon för kvantitet som ska placeras"><br><span data-ttu-id="fa554-522">QtyToPut</span><span class="sxs-lookup"><span data-stu-id="fa554-522">QtyToPut</span></span></td>
</tr>
<tr>
<td><img src="media/step-icons-qty-to-scrap.png" alt="Quantity to scrap step icon" title="Stegikon för kvantitet som ska kasseras"><br><span data-ttu-id="fa554-524">QtyToScrap</span><span class="sxs-lookup"><span data-stu-id="fa554-524">QtyToScrap</span></span></td>
<td><img src="media/step-icons-qty-confirmation.png" alt="Quantity confirmation step icon" title="Stegikon för kvantitetsbekräftelse"><br><span data-ttu-id="fa554-526">QuantityConfirmation</span><span class="sxs-lookup"><span data-stu-id="fa554-526">QuantityConfirmation</span></span></td>
<td><img src="media/step-icons-raf-end-job.png" alt="Report as finished end job step icon" title="Stegikon för rapportera som färdigt"><br><span data-ttu-id="fa554-528">RAFEndJob</span><span class="sxs-lookup"><span data-stu-id="fa554-528">RAFEndJob</span></span></td>
<td><img src="media/step-icons-recv-loc-id.png" alt="Receive location ID step icon" title="Stegikon för ta emot plats-ID"><br><span data-ttu-id="fa554-530">RecvLocationID</span><span class="sxs-lookup"><span data-stu-id="fa554-530">RecvLocationID</span></span></td>
</tr>
<tr>
<td><img src="media/step-icons-remove-container-id.png" alt="Remove container ID step icon" title="Stegikon för ta bort behållar-ID"><br><span data-ttu-id="fa554-532">RemoveContainerID</span><span class="sxs-lookup"><span data-stu-id="fa554-532">RemoveContainerID</span></span></td>
<td><img src="media/step-icons-rma-no.png" alt="RMA number step icon" title="Stegikon RMA-nummer"><br><span data-ttu-id="fa554-534">RMANum</span><span class="sxs-lookup"><span data-stu-id="fa554-534">RMANum</span></span></td>
<td><img src="media/step-icons-select-order.png" alt="Select order step icon" title="Välj orderstegsikon"><br><span data-ttu-id="fa554-536">SelectOrder</span><span class="sxs-lookup"><span data-stu-id="fa554-536">SelectOrder</span></span></td>
<td><img src="media/step-icons-short-pick-reason.png" alt="Short pick reason step icon" title="Stegikon för orsak till kort plockning"><br><span data-ttu-id="fa554-538">ShortPickReason</span><span class="sxs-lookup"><span data-stu-id="fa554-538">ShortPickReason</span></span></td>
</tr>
<tr>
<td><img src="media/step-icons-sort-position-id.png" alt="Sort position ID step icon" title="Stegikon för sorteringsposition"><br><span data-ttu-id="fa554-540">SortPositionId</span><span class="sxs-lookup"><span data-stu-id="fa554-540">SortPositionId</span></span></td>
<td><img src="media/step-icons-target-lp-id.png" alt="Target license plate ID step icon" title="Stegikonen för målnummer-ID"><br><span data-ttu-id="fa554-542">TargetLicensePlateId</span><span class="sxs-lookup"><span data-stu-id="fa554-542">TargetLicensePlateId</span></span></td>
<td><img src="media/step-icons-to-line-no.png" alt="To line number step icon" title="Stegikon för radnummer"><br><span data-ttu-id="fa554-544">ToLineNum</span><span class="sxs-lookup"><span data-stu-id="fa554-544">ToLineNum</span></span></td>
<td><img src="media/step-icons-to-location.png" alt="To location step icon" title="Stegikon för till plats"><br><span data-ttu-id="fa554-546">ToLocation</span><span class="sxs-lookup"><span data-stu-id="fa554-546">ToLocation</span></span></td>
</tr>
<tr>
<td><img src="media/step-icons-to-number.png" alt="To number step icon" title="Stegikon för till nummer"><br><span data-ttu-id="fa554-548">ToNum</span><span class="sxs-lookup"><span data-stu-id="fa554-548">ToNum</span></span></td>
<td><img src="media/step-icons-to-warehouse.png" alt="To warehouse step icon" title="Stegikon för till lagerställe"><br><span data-ttu-id="fa554-550">ToWarehouse</span><span class="sxs-lookup"><span data-stu-id="fa554-550">ToWarehouse</span></span></td>
<td><img src="media/step-icons-tranport-load-id.png" alt="Transport load ID step icon" title="Stegikon för transportlast-ID"><br><span data-ttu-id="fa554-552">TransportLoadId</span><span class="sxs-lookup"><span data-stu-id="fa554-552">TransportLoadId</span></span></td>
<td><img src="media/step-icons-vendor-batch-id.png" alt="Vendor batch ID step icon" title="Stegikon för leverantörs-ID för lager"><br><span data-ttu-id="fa554-554">VendBatchId</span><span class="sxs-lookup"><span data-stu-id="fa554-554">VendBatchId</span></span></td>
</tr>
<tr>
<td><img src="media/step-icons-wave-label-id.png" alt="Wave label ID step icon" title="Stegikon för påfyllnadsetikett-ID"><br><span data-ttu-id="fa554-556">WaveLabelId</span><span class="sxs-lookup"><span data-stu-id="fa554-556">WaveLabelId</span></span></td>
<td><img src="media/step-icons-wave-label-qty.png" alt="Wave label quantity step icon" title="Stegikon för påfyllnadsetikett kvantitet"><br><span data-ttu-id="fa554-558">WaveLblQty</span><span class="sxs-lookup"><span data-stu-id="fa554-558">WaveLblQty</span></span></td>
<td><img src="media/step-icons-weight.png" alt="Weight step icon" title="Stegikon för vikt"><br><span data-ttu-id="fa554-560">Vikt</span><span class="sxs-lookup"><span data-stu-id="fa554-560">Weight</span></span></td>
<td><img src="media/step-icons-weight-to-consume.png" alt="Weight to consume step icon" title="Stegikon för vikt som ska förbrukas"><br><span data-ttu-id="fa554-562">WeightToConsume</span><span class="sxs-lookup"><span data-stu-id="fa554-562">WeightToConsume</span></span></td>
</tr>
<tr>
<td><img src="media/step-icons-whs-adjustment-type.png" alt="WHS adjustment type step icon" title="Stegikon för WHS-justeringstyp"><br><span data-ttu-id="fa554-564">WHSAdjustmentType</span><span class="sxs-lookup"><span data-stu-id="fa554-564">WHSAdjustmentType</span></span></td>
<td><img src="media/step-icons-whs-receiving-exception.png" alt="WHS receiving exception step icon" title="Stegikon för WHS-mottagningsundantag"><br><span data-ttu-id="fa554-566">WHSReceivingException</span><span class="sxs-lookup"><span data-stu-id="fa554-566">WHSReceivingException</span></span></td>
<td><img src="media/step-icons-wms-location-id.png" alt="WMS location ID step icon" title="Stegikon för WMS-plats-ID"><br><span data-ttu-id="fa554-568">WMSLocationID</span><span class="sxs-lookup"><span data-stu-id="fa554-568">WMSLocationID</span></span></td>
<td><img src="media/step-icons-work-id.png" alt="Work ID step icon" title="Stegikon för arbets-ID"><br><span data-ttu-id="fa554-570">WorkId</span><span class="sxs-lookup"><span data-stu-id="fa554-570">WorkId</span></span></td>
</tr>
<tr>
<td><img src="media/step-icons-work-id-to-cancel.png" alt="Work ID to cancel step icon" title="Stegikon för arbets-ID för att avbryta"><br><span data-ttu-id="fa554-572">WorkIdToCancel</span><span class="sxs-lookup"><span data-stu-id="fa554-572">WorkIdToCancel</span></span></td>
<td><img src="media/step-icons-work-lp-id.png" alt="Work license plate ID step icon" title="Stegikon för arbets-ID-nummer"><br><span data-ttu-id="fa554-574">WorkLicensePlateId</span><span class="sxs-lookup"><span data-stu-id="fa554-574">WorkLicensePlateId</span></span></td>
<td><img src="media/step-icons-work-lp-putaway-cluster.png" alt="Work license plate ID putaway cluster step icon" title="Stegikon för arbets-ID-nummer för kluster för artikelinförsel"><br><span data-ttu-id="fa554-576">WorkLPIDPutawayCluster</span><span class="sxs-lookup"><span data-stu-id="fa554-576">WorkLPIDPutawayCluster</span></span></td>
<td><img src="media/step-icons-work-pool-id.png" alt="Work pool ID step icon" title="Stegikon för arbetspool-ID"><br><span data-ttu-id="fa554-578">WorkPoolID</span><span class="sxs-lookup"><span data-stu-id="fa554-578">WorkPoolID</span></span></td>
</tr>
<tr>
<td><img src="media/step-icons-zone-pool-id.png" alt="Zone ID step icon" title="Stegikon för zon-ID"><br><span data-ttu-id="fa554-580">ZoneID</span><span class="sxs-lookup"><span data-stu-id="fa554-580">ZoneID</span></span></td>
<td></td>
<td></td>
<td></td>
</tr>
</tbody>
</table>

## <a name="example-assign-step-icons-and-titles-for-a-custom-flow"></a><a name="example"></a><span data-ttu-id="fa554-581">Exempel: Tilldela stegikoner och titlar för ett anpassat flöde</span><span class="sxs-lookup"><span data-stu-id="fa554-581">Example: Assign step icons and titles for a custom flow</span></span>

<span data-ttu-id="fa554-582">I det här exemplet förklaras hur du ställer in stegikoner och titlar för ett anpassat uppgiftsflöde.</span><span class="sxs-lookup"><span data-stu-id="fa554-582">This example explains how to set up step icons and titles for a custom task flow.</span></span> <span data-ttu-id="fa554-583">Scenariot bygger på ett exempel på ett anpassat uppgiftsflöde som visas och mer ingående i följande bloggpost: [Anpassa mobilappen för lagerhantering](https://cloudblogs.microsoft.com/dynamics365/it/2017/07/06/customizing-the-warehousing-mobile-app).</span><span class="sxs-lookup"><span data-stu-id="fa554-583">The scenario is built on an example of a custom task flow that is presented and explored in more detail in the following blog post: [Customizing the Warehousing Mobile App](https://cloudblogs.microsoft.com/dynamics365/it/2017/07/06/customizing-the-warehousing-mobile-app).</span></span> <span data-ttu-id="fa554-584">Uppgiftsflödet fungerar på följande sätt:</span><span class="sxs-lookup"><span data-stu-id="fa554-584">The task flow works in the following way:</span></span>

1. <span data-ttu-id="fa554-585">I programmet visas en sida där arbetaren måste ange ett behållar-ID (till exempel genom att skanna en streckkod).</span><span class="sxs-lookup"><span data-stu-id="fa554-585">The app shows a page that prompts the worker to provide a container ID (for example, by scanning a bar code).</span></span>
1. <span data-ttu-id="fa554-586">Om behållar-ID:t är giltigt öppnar programmet en ny sida där arbetaren uppmanas att ange vikten.</span><span class="sxs-lookup"><span data-stu-id="fa554-586">If the container ID is valid, the app opens a new page that prompts the worker for the weight.</span></span> <span data-ttu-id="fa554-587">(Om behållar-ID:t är ogiltigt, returneras arbetaren till första sidan.)</span><span class="sxs-lookup"><span data-stu-id="fa554-587">(If the container ID isn't valid, the worker is returned to the first page.)</span></span>
1. <span data-ttu-id="fa554-588">När arbetaren anger en giltig vikt lagrar systemet vikten och returnerar arbetaren till första sidan.</span><span class="sxs-lookup"><span data-stu-id="fa554-588">When the worker enters a valid weight, the system stores the weight and returns the worker to the first page.</span></span>

<span data-ttu-id="fa554-589">Illustrationen nedan visar detta uppgiftsflöde.</span><span class="sxs-lookup"><span data-stu-id="fa554-589">The following illustration shows this task flow.</span></span>

<span data-ttu-id="fa554-590">![Uppgiftsflödesdiagram](media/step-icons-example-task-flow.png "Uppgiftsflödesdiagram")</span><span class="sxs-lookup"><span data-stu-id="fa554-590">![Task flow diagram](media/step-icons-example-task-flow.png "Task flow diagram")</span></span>

### <a name="create-a-step-class-for-the-container-input-page"></a><span data-ttu-id="fa554-591">Skapa en stegklass för inmatningssidan för behållare</span><span class="sxs-lookup"><span data-stu-id="fa554-591">Create a step class for the container input page</span></span>

<span data-ttu-id="fa554-592">På inmatningssidan för behållare kan arbetaren skanna eller ange ett behållar-ID.</span><span class="sxs-lookup"><span data-stu-id="fa554-592">The container input page lets the worker scan or enter a container ID.</span></span>

<span data-ttu-id="fa554-593">![Inmatningssida för behållare](media/step-icons-example-container-input.png "Inmatningssida för behållare")</span><span class="sxs-lookup"><span data-stu-id="fa554-593">![Container input page](media/step-icons-example-container-input.png "Container input page")</span></span>

<span data-ttu-id="fa554-594">På behållarens inmatningssida är kontrollnamnet för inmatningsfältet `ContainerId`.</span><span class="sxs-lookup"><span data-stu-id="fa554-594">On the container input page, the control name of the input field is `ContainerId`.</span></span> <span data-ttu-id="fa554-595">Eftersom det här kontrollnamnet inte finns i [listan med steg-ID](#step-ids-classes), hittar du inte ett befintligt steg som baseras på det.</span><span class="sxs-lookup"><span data-stu-id="fa554-595">Because this control name isn't in the [list of step IDs](#step-ids-classes), you won't find an existing step that is based on it.</span></span> <span data-ttu-id="fa554-596">Därför måste du skapa en stegklass som representerar steget.</span><span class="sxs-lookup"><span data-stu-id="fa554-596">Therefore, you must create a step class that represents the step.</span></span> <span data-ttu-id="fa554-597">Här är ett exempel:</span><span class="sxs-lookup"><span data-stu-id="fa554-597">Here is an example.</span></span>

```xpp
[WHSMobileAppStepId('ContainerId')]
final internal class WHSMobileAppStepContainerId extends WHSMobileAppStep
{
    private const WHSMobileAppStepIcon PopulationIcon = 'InventBatchID';
    private const WHSMobileAppStepTitle InputNotFilledTitle = "@WAX:WHSMobileAppStepContainerID_InputNotFilled"; //Scan a container
    protected void initValues()
    {
        defaultStepIcon = PopulationIcon;
        defaultStepTitle = InputNotFilledTitle;
    }
}
```

<span data-ttu-id="fa554-598">Identifieraren för stegikonen lagras i `defaultStepIcon` klassmedlemmen och stegtiteln lagras i  `defaultStepTitle` klassmedlemmen.</span><span class="sxs-lookup"><span data-stu-id="fa554-598">The identifier of the step icon is stored in the `defaultStepIcon` class member, and the step title is stored in the `defaultStepTitle` class member.</span></span>

<span data-ttu-id="fa554-599">Om du vill tilldela en stegikon ställer du in `defaultStepIcon` till ett av de ikon_ID som anges i avsnittet [Tillgängliga stegikoner](#step-icons) tidigare i det här ämnet.</span><span class="sxs-lookup"><span data-stu-id="fa554-599">To assign a step icon, set `defaultStepIcon` to one of the icon IDs that are listed in the [Available step icons](#step-icons) section earlier in this topic.</span></span>

### <a name="use-a-standard-or-custom-step-icon-and-title-for-the-weight-input"></a><span data-ttu-id="fa554-600">Använd en standard- eller anpassad stegikon och rubrik för viktinmatning</span><span class="sxs-lookup"><span data-stu-id="fa554-600">Use a standard or custom step icon and title for the weight input</span></span>

<span data-ttu-id="fa554-601">På indatasidan för vikt kan arbetaren ange en vikt.</span><span class="sxs-lookup"><span data-stu-id="fa554-601">The weight input page lets the worker enter a weight.</span></span>

<span data-ttu-id="fa554-602">![Viktinmatningssida](media/step-icons-example-weight-input.png "Viktinmatningssida")</span><span class="sxs-lookup"><span data-stu-id="fa554-602">![Weight input page](media/step-icons-example-weight-input.png "Weight input page")</span></span>

<span data-ttu-id="fa554-603">På viktinmatningssidan är kontrollnamnet för inmatningsfältet `Weight`, som finns i [listan med steg-ID](#step-ids-classes).</span><span class="sxs-lookup"><span data-stu-id="fa554-603">On the weight input page, the control name of the input field is `Weight`, which is in the [list of step IDs](#step-ids-classes).</span></span> <span data-ttu-id="fa554-604">Därför, om stegikonen och titeln som definieras i `WHSMobileAppStepWeight` klass är acceptabelt för dig, du behöver inte ändra någonting för detta steg.</span><span class="sxs-lookup"><span data-stu-id="fa554-604">Therefore, if the step icon and title that are defined in the `WHSMobileAppStepWeight` class are acceptable to you, you don't have to change anything for this step.</span></span>

<span data-ttu-id="fa554-605">Om du föredrar att använda en annan ikon eller rubrik för det här steget kan du dock åsidosätta metoden `stepId()` eller metoden `stepInfo()` skaparklass.</span><span class="sxs-lookup"><span data-stu-id="fa554-605">However, if you prefer to use a different icon or title for this step, you can override either the `stepId()` method or the `stepInfo()` method in the builder class.</span></span> <span data-ttu-id="fa554-606">Varje uppgiftsflöde har ett eget steginfoskapare.</span><span class="sxs-lookup"><span data-stu-id="fa554-606">Each task flow has its own step info builder.</span></span>

#### <a name="override-the-stepid-method"></a><span data-ttu-id="fa554-607">Åsidosätt metoden stepId()</span><span class="sxs-lookup"><span data-stu-id="fa554-607">Override the stepId() method</span></span>

<span data-ttu-id="fa554-608">Följande exempel visar ett sätt att ändra en skaparklass genom att åsidosätta `stepId()` metoden.</span><span class="sxs-lookup"><span data-stu-id="fa554-608">The following example shows one way that you can modify a builder class by overriding the `stepId()` method.</span></span>

```xpp
[WHSWorkExecuteMode(WHSWorkExecuteMode:: WeighContainer)]
public class WHSMobileAppStepInfoBuilderWeighContainer extends WHSMobileAppStepInfoBuilder
{
    protected WHSMobileAppStepId stepId()
    {
        WHSMobileAppStepId stepIdLocal = super();
        if (stepIdLocal == 'Weight')
        {
            return 'NewWeight';
        }
        return stepIdLocal;
    }
}
```

<span data-ttu-id="fa554-609">Du skapar sedan en stegklass för `NewWeight` steget.</span><span class="sxs-lookup"><span data-stu-id="fa554-609">You then create a step class for the `NewWeight` step.</span></span> <span data-ttu-id="fa554-610">Koden bör likna koden för `ContainerId` exempel som tidigare visades i det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="fa554-610">The code should resemble the code for the `ContainerId` example that was shown earlier in this topic.</span></span>

#### <a name="override-the-stepinfo-method"></a><span data-ttu-id="fa554-611">Åsidosätt metoden stepInfo()</span><span class="sxs-lookup"><span data-stu-id="fa554-611">Override the stepInfo() method</span></span>

<span data-ttu-id="fa554-612">Följande exempel visar ett sätt att ändra en skaparklass genom att åsidosätta `stepInfo()` metoden.</span><span class="sxs-lookup"><span data-stu-id="fa554-612">The following example shows one way that you can modify a builder class by overriding the `stepInfo()` method.</span></span>

```xpp
[WHSWorkExecuteMode(WHSWorkExecuteMode:: WeighContainer)]
public class WHSMobileAppStepInfoBuilderWeighContainer extends WHSMobileAppStepInfoBuilder
{
    protected WHSMobileAppStepInfo stepInfo()
    {
        if (stepId != 'Weight')
        {
            return super();
        }
        WHSMobileAppStepInfo stepInfo = WHSMobileAppStepInfo::construct();
        stepInfo.parmStepIcon('NewIcon');
        stepInfo.parmStepTitle('NewTitle');
        return stepInfo;
    }
}
```

<span data-ttu-id="fa554-613">Sedan skapar du ett `WHSMobileAppStepInfo` objekt och ställer in ikonen och/eller rubriken direkt.</span><span class="sxs-lookup"><span data-stu-id="fa554-613">You then construct a `WHSMobileAppStepInfo` object, and set the icon and/or title directly.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="fa554-614">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="fa554-614">Additional resources</span></span>

- [<span data-ttu-id="fa554-615">Installera och ansluta mobilappen för distributionslagerhantering</span><span class="sxs-lookup"><span data-stu-id="fa554-615">Install and connect the Warehouse Management mobile app</span></span>](install-configure-warehouse-management-app.md)
- [<span data-ttu-id="fa554-616">Användarinställningar för mobil enhet</span><span class="sxs-lookup"><span data-stu-id="fa554-616">Mobile device user settings</span></span>](mobile-device-user-settings.md)
