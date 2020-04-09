---
title: Bokföring av försäljningar och betalningar online
description: Den här proceduren går igenom hur du kör ett återkommande batchjobb om du vill skapa försäljningsorder och betalningar för onlinebutikstransaktioner.
author: psimolin
manager: AnnBe
ms.date: 08/06/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: RetailChannelOperationsWorkspace, RetailOperatingUnitPicker, SysRecurrence
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: jashanno
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e3bac0cab764436a618fa570901c84ab720dbc86
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/18/2020
ms.locfileid: "3140794"
---
# <a name="posting-of-online-sales-and-payments"></a><span data-ttu-id="6c599-103">Bokföring av försäljningar och betalningar online</span><span class="sxs-lookup"><span data-stu-id="6c599-103">Posting of online sales and payments</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="6c599-104">Den här proceduren går igenom hur du kör ett återkommande batchjobb om du vill skapa försäljningsorder och betalningar för onlinebutikstransaktioner.</span><span class="sxs-lookup"><span data-stu-id="6c599-104">This procedure walks through configuring and running a recurrent batch job to create sales orders and payments for online store transactions.</span></span>

<span data-ttu-id="6c599-105">Att bokföra både försäljning och betalningar online är en process i två steg.</span><span class="sxs-lookup"><span data-stu-id="6c599-105">Posting online sales and payments is a two-stage process.</span></span>

- <span data-ttu-id="6c599-106">Dra in transaktionsdata för onlinehandel i huvudkontor.</span><span class="sxs-lookup"><span data-stu-id="6c599-106">Pulling the online commerce transaction data in HQ.</span></span>
- <span data-ttu-id="6c599-107">Synkronisera order för att skapa försäljningsorder i huvudkontor.</span><span class="sxs-lookup"><span data-stu-id="6c599-107">Synchronizing orders to create sales orders in HQ.</span></span>

<span data-ttu-id="6c599-108">Du kan dra in transaktionsdata online manuellt genom att köra P-jobbet eller genom att skapa ett återkommande batchjobb.</span><span class="sxs-lookup"><span data-stu-id="6c599-108">Pulling the online transaction data can be done either by manually running the P-job or by creating a recurrent batch job.</span></span>

### <a name="manually-running-the-p-job"></a><span data-ttu-id="6c599-109">Köra P-jobbet manuellt</span><span class="sxs-lookup"><span data-stu-id="6c599-109">Manually running the P-job</span></span>

1. <span data-ttu-id="6c599-110">Gå till alla arbetsytor > Butik och handel-IT.</span><span class="sxs-lookup"><span data-stu-id="6c599-110">Go to All workspaces > Retail and Commerce IT.</span></span>
2. <span data-ttu-id="6c599-111">Klicka på Distributionsschema.</span><span class="sxs-lookup"><span data-stu-id="6c599-111">Click Distribution schedule.</span></span>
3. <span data-ttu-id="6c599-112">Välj P-0001.</span><span class="sxs-lookup"><span data-stu-id="6c599-112">Select P-0001.</span></span>
4. <span data-ttu-id="6c599-113">Justera kanaldatabasgrupper om det behövs.</span><span class="sxs-lookup"><span data-stu-id="6c599-113">Adjust channel database groups, if required.</span></span>
5. <span data-ttu-id="6c599-114">Klicka på Kör nu.</span><span class="sxs-lookup"><span data-stu-id="6c599-114">Click Run now.</span></span>
6. <span data-ttu-id="6c599-115">Klicka på Ja.</span><span class="sxs-lookup"><span data-stu-id="6c599-115">Click Yes.</span></span>

### <a name="scheduling-a-recurring-p-job"></a><span data-ttu-id="6c599-116">Schemalägga ett återkommande P-jobb</span><span class="sxs-lookup"><span data-stu-id="6c599-116">Scheduling a recurring P-job</span></span>

1. <span data-ttu-id="6c599-117">Gå till alla arbetsytor > Butik och handel-IT.</span><span class="sxs-lookup"><span data-stu-id="6c599-117">Go to All workspaces > Retail and Commerce IT.</span></span>
2. <span data-ttu-id="6c599-118">Klicka på Distributionsschema.</span><span class="sxs-lookup"><span data-stu-id="6c599-118">Click Distribution schedule.</span></span>
3. <span data-ttu-id="6c599-119">Välj P-0001.</span><span class="sxs-lookup"><span data-stu-id="6c599-119">Select P-0001.</span></span>
4. <span data-ttu-id="6c599-120">Klicka på Skapa batchjobb.</span><span class="sxs-lookup"><span data-stu-id="6c599-120">Click Create batch job.</span></span>
5. <span data-ttu-id="6c599-121">Klicka på Kör i bakgrunden.</span><span class="sxs-lookup"><span data-stu-id="6c599-121">Click Run in the background.</span></span>
5. <span data-ttu-id="6c599-122">Aktivera Batchbearbetning.</span><span class="sxs-lookup"><span data-stu-id="6c599-122">Enable Batch processing.</span></span>
6. <span data-ttu-id="6c599-123">Klicka på Upprepning.</span><span class="sxs-lookup"><span data-stu-id="6c599-123">Click Recurrence..</span></span>
7. <span data-ttu-id="6c599-124">Välj alternativet Slutdatum saknas.</span><span class="sxs-lookup"><span data-stu-id="6c599-124">Select the No end date option.</span></span>
8. <span data-ttu-id="6c599-125">I fältet Antal anger du intervall mellan körningarna i minuter.</span><span class="sxs-lookup"><span data-stu-id="6c599-125">In the Count field, enter interval between the runs in minutes.</span></span> <span data-ttu-id="6c599-126">Detta är vanligtvis 5-10.</span><span class="sxs-lookup"><span data-stu-id="6c599-126">Typically this would be 5-10.</span></span>
9. <span data-ttu-id="6c599-127">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="6c599-127">Click OK.</span></span>
10. <span data-ttu-id="6c599-128">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="6c599-128">Click OK.</span></span>

<span data-ttu-id="6c599-129">Order kan synkroniseras antingen genom att köra "Synkronisera order"-jobbet manuellt eller genom att skapa ett återkommande batchjobb.</span><span class="sxs-lookup"><span data-stu-id="6c599-129">Orders can be synchronized either by manually running the "Synchronize orders"-job or by creating a recurring batch job.</span></span>

### <a name="manually-running-order-synchronization"></a><span data-ttu-id="6c599-130">Köra ordersynkronisering manuellt</span><span class="sxs-lookup"><span data-stu-id="6c599-130">Manually running order synchronization</span></span> 

<span data-ttu-id="6c599-131">Följ dessa steg om du vill köra "Synkronisera order"-jobb manuellt en gång.</span><span class="sxs-lookup"><span data-stu-id="6c599-131">Follow these steps to manually run "Synchronize orders" job once.</span></span>

1. <span data-ttu-id="6c599-132">Gå till alla arbetsytor > butiksekonomi.</span><span class="sxs-lookup"><span data-stu-id="6c599-132">Go to All workspaces > Store financials.</span></span>
2. <span data-ttu-id="6c599-133">Klicka på Synkronisera order.</span><span class="sxs-lookup"><span data-stu-id="6c599-133">Click Synchronize orders.</span></span>
3. <span data-ttu-id="6c599-134">Välj Butiker efter region i fältet Organisationshierarki.</span><span class="sxs-lookup"><span data-stu-id="6c599-134">In the Organization hierarchy field, select 'Stores by Region'.</span></span>
    * <span data-ttu-id="6c599-135">Välj antingen en specifik onlinebutik eller välj en nod om du vill skapa batchjobbet för en grupp av butiker.</span><span class="sxs-lookup"><span data-stu-id="6c599-135">Select either a specific online store, or select a node if you want to create the batch job for a group of stores.</span></span>  
    * <span data-ttu-id="6c599-136">Klicka på pilen om du vill lägga till ditt val.</span><span class="sxs-lookup"><span data-stu-id="6c599-136">Click the arrow to add your selection.</span></span>  
4. <span data-ttu-id="6c599-137">Klicka på fliken Kör i bakgrunden ...</span><span class="sxs-lookup"><span data-stu-id="6c599-137">Click the Run in the background tab.</span></span>
5. <span data-ttu-id="6c599-138">Inaktivera Batchbearbetning</span><span class="sxs-lookup"><span data-stu-id="6c599-138">Disable Batch processing</span></span>
6. <span data-ttu-id="6c599-139">Klicka på Upprepning.</span><span class="sxs-lookup"><span data-stu-id="6c599-139">Click Recurrence.</span></span>
7. <span data-ttu-id="6c599-140">Välja alternativet Sluta efter</span><span class="sxs-lookup"><span data-stu-id="6c599-140">Select End After option</span></span>
8. <span data-ttu-id="6c599-141">Ange 1 i fältet Sluta efter.</span><span class="sxs-lookup"><span data-stu-id="6c599-141">In the End After field, enter 1.</span></span>
9. <span data-ttu-id="6c599-142">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="6c599-142">Click OK.</span></span>
10. <span data-ttu-id="6c599-143">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="6c599-143">Click OK.</span></span>

### <a name="scheduling-recurring-order-synchronization"></a><span data-ttu-id="6c599-144">Tidsplanera synkronisering av återkommande order</span><span class="sxs-lookup"><span data-stu-id="6c599-144">Scheduling recurring order synchronization</span></span>

<span data-ttu-id="6c599-145">Den här proceduren går igenom hur du kör ett återkommande batchjobb om du vill skapa försäljningsorder och betalningar för onlinebutikstransaktioner.</span><span class="sxs-lookup"><span data-stu-id="6c599-145">This procedure walks through configuring and running a recurrent batch job to create sales orders and payments for online store transactions.</span></span> <span data-ttu-id="6c599-146">I proceduren används demonstrationsföretaget USRT.</span><span class="sxs-lookup"><span data-stu-id="6c599-146">This procedure uses the USRT company in demo data.</span></span>

1. <span data-ttu-id="6c599-147">Gå till alla arbetsytor > butiksekonomi.</span><span class="sxs-lookup"><span data-stu-id="6c599-147">Go to All workspaces > Store financials.</span></span>
2. <span data-ttu-id="6c599-148">Klicka på Synkronisera order.</span><span class="sxs-lookup"><span data-stu-id="6c599-148">Click Synchronize orders.</span></span>
3. <span data-ttu-id="6c599-149">Välj Butiker efter region i fältet Organisationshierarki.</span><span class="sxs-lookup"><span data-stu-id="6c599-149">In the Organization hierarchy field, select 'Stores by Region'.</span></span>
    * <span data-ttu-id="6c599-150">Välj antingen en specifik onlinebutik eller välj en nod om du vill skapa batchjobbet för en grupp av butiker.</span><span class="sxs-lookup"><span data-stu-id="6c599-150">Select either a specific online store, or select a node if you want to create the batch job for a group of stores.</span></span>  
    * <span data-ttu-id="6c599-151">Klicka på pilen om du vill lägga till ditt val.</span><span class="sxs-lookup"><span data-stu-id="6c599-151">Click the arrow to add your selection.</span></span>  
4. <span data-ttu-id="6c599-152">Klicka på fliken Kör i bakgrunden ...</span><span class="sxs-lookup"><span data-stu-id="6c599-152">Click the Run in the background tab.</span></span>
5. <span data-ttu-id="6c599-153">Aktivera Batchbearbetning</span><span class="sxs-lookup"><span data-stu-id="6c599-153">Enable Batch processing</span></span>
6. <span data-ttu-id="6c599-154">Klicka på Upprepning.</span><span class="sxs-lookup"><span data-stu-id="6c599-154">Click Recurrence.</span></span>
7. <span data-ttu-id="6c599-155">Välj alternativet Slutdatum saknas.</span><span class="sxs-lookup"><span data-stu-id="6c599-155">Select the No end date option.</span></span>
8. <span data-ttu-id="6c599-156">I fältet Antal anger du intervall mellan körningarna i minuter.</span><span class="sxs-lookup"><span data-stu-id="6c599-156">In the Count field, enter interval between the runs in minutes.</span></span> <span data-ttu-id="6c599-157">Detta är vanligtvis 2-20</span><span class="sxs-lookup"><span data-stu-id="6c599-157">Typically this would be 2-20</span></span>
9. <span data-ttu-id="6c599-158">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="6c599-158">Click OK.</span></span>
10. <span data-ttu-id="6c599-159">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="6c599-159">Click OK.</span></span>

## <a name="data-entities-involved-in-the-process"></a><span data-ttu-id="6c599-160">Dataenheter som är inblandade i processen</span><span class="sxs-lookup"><span data-stu-id="6c599-160">Data entities involved in the process</span></span>

- <span data-ttu-id="6c599-161">RetailTransactionTable</span><span class="sxs-lookup"><span data-stu-id="6c599-161">RetailTransactionTable</span></span>
- <span data-ttu-id="6c599-162">RetailTransactionAddressTrans</span><span class="sxs-lookup"><span data-stu-id="6c599-162">RetailTransactionAddressTrans</span></span>
- <span data-ttu-id="6c599-163">RetailTransactionInfocodeTrans</span><span class="sxs-lookup"><span data-stu-id="6c599-163">RetailTransactionInfocodeTrans</span></span>
- <span data-ttu-id="6c599-164">RetailTransactionTaxTrans</span><span class="sxs-lookup"><span data-stu-id="6c599-164">RetailTransactionTaxTrans</span></span>
- <span data-ttu-id="6c599-165">RetailTransactionSalesTrans</span><span class="sxs-lookup"><span data-stu-id="6c599-165">RetailTransactionSalesTrans</span></span>
- <span data-ttu-id="6c599-166">RetailTransactionTaxMeasure</span><span class="sxs-lookup"><span data-stu-id="6c599-166">RetailTransactionTaxMeasure</span></span>
- <span data-ttu-id="6c599-167">RetailTransactionDiscountTrans</span><span class="sxs-lookup"><span data-stu-id="6c599-167">RetailTransactionDiscountTrans</span></span>
- <span data-ttu-id="6c599-168">RetailTransactionTaxTransGTE</span><span class="sxs-lookup"><span data-stu-id="6c599-168">RetailTransactionTaxTransGTE</span></span>
- <span data-ttu-id="6c599-169">RetailTransactionMarkupTrans</span><span class="sxs-lookup"><span data-stu-id="6c599-169">RetailTransactionMarkupTrans</span></span>
- <span data-ttu-id="6c599-170">RetailTransactionPaymentTrans</span><span class="sxs-lookup"><span data-stu-id="6c599-170">RetailTransactionPaymentTrans</span></span>
- <span data-ttu-id="6c599-171">RetailTransactionAttributeTrans</span><span class="sxs-lookup"><span data-stu-id="6c599-171">RetailTransactionAttributeTrans</span></span>
