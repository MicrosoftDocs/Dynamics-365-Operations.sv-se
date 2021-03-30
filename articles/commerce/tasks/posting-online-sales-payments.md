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
ms.search.region: Global
ms.search.industry: Retail
ms.author: jashanno
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e24c2be8a1b0da3c34919fdb44aa744f8e7fc87c
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5215422"
---
# <a name="posting-of-online-sales-and-payments"></a><span data-ttu-id="ca0f8-103">Bokföring av försäljningar och betalningar online</span><span class="sxs-lookup"><span data-stu-id="ca0f8-103">Posting of online sales and payments</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="ca0f8-104">Den här proceduren går igenom hur du kör ett återkommande batchjobb om du vill skapa försäljningsorder och betalningar för onlinebutikstransaktioner.</span><span class="sxs-lookup"><span data-stu-id="ca0f8-104">This procedure walks through configuring and running a recurrent batch job to create sales orders and payments for online store transactions.</span></span>

<span data-ttu-id="ca0f8-105">Att bokföra både försäljning och betalningar online är en process i två steg.</span><span class="sxs-lookup"><span data-stu-id="ca0f8-105">Posting online sales and payments is a two-stage process.</span></span>

- <span data-ttu-id="ca0f8-106">Dra in transaktionsdata för onlinehandel i huvudkontor.</span><span class="sxs-lookup"><span data-stu-id="ca0f8-106">Pulling the online commerce transaction data in HQ.</span></span>
- <span data-ttu-id="ca0f8-107">Synkronisera order för att skapa försäljningsorder i huvudkontor.</span><span class="sxs-lookup"><span data-stu-id="ca0f8-107">Synchronizing orders to create sales orders in HQ.</span></span>

<span data-ttu-id="ca0f8-108">Du kan dra in transaktionsdata online manuellt genom att köra P-jobbet eller genom att skapa ett återkommande batchjobb.</span><span class="sxs-lookup"><span data-stu-id="ca0f8-108">Pulling the online transaction data can be done either by manually running the P-job or by creating a recurrent batch job.</span></span>

### <a name="manually-running-the-p-job"></a><span data-ttu-id="ca0f8-109">Köra P-jobbet manuellt</span><span class="sxs-lookup"><span data-stu-id="ca0f8-109">Manually running the P-job</span></span>

1. <span data-ttu-id="ca0f8-110">Gå till alla arbetsytor > Butik och handel-IT.</span><span class="sxs-lookup"><span data-stu-id="ca0f8-110">Go to All workspaces > Retail and Commerce IT.</span></span>
2. <span data-ttu-id="ca0f8-111">Klicka på Distributionsschema.</span><span class="sxs-lookup"><span data-stu-id="ca0f8-111">Click Distribution schedule.</span></span>
3. <span data-ttu-id="ca0f8-112">Välj P-0001.</span><span class="sxs-lookup"><span data-stu-id="ca0f8-112">Select P-0001.</span></span>
4. <span data-ttu-id="ca0f8-113">Justera kanaldatabasgrupper om det behövs.</span><span class="sxs-lookup"><span data-stu-id="ca0f8-113">Adjust channel database groups, if required.</span></span>
5. <span data-ttu-id="ca0f8-114">Klicka på Kör nu.</span><span class="sxs-lookup"><span data-stu-id="ca0f8-114">Click Run now.</span></span>
6. <span data-ttu-id="ca0f8-115">Klicka på Ja.</span><span class="sxs-lookup"><span data-stu-id="ca0f8-115">Click Yes.</span></span>

### <a name="scheduling-a-recurring-p-job"></a><span data-ttu-id="ca0f8-116">Schemalägga ett återkommande P-jobb</span><span class="sxs-lookup"><span data-stu-id="ca0f8-116">Scheduling a recurring P-job</span></span>

1. <span data-ttu-id="ca0f8-117">Gå till alla arbetsytor > Butik och handel-IT.</span><span class="sxs-lookup"><span data-stu-id="ca0f8-117">Go to All workspaces > Retail and Commerce IT.</span></span>
2. <span data-ttu-id="ca0f8-118">Klicka på Distributionsschema.</span><span class="sxs-lookup"><span data-stu-id="ca0f8-118">Click Distribution schedule.</span></span>
3. <span data-ttu-id="ca0f8-119">Välj P-0001.</span><span class="sxs-lookup"><span data-stu-id="ca0f8-119">Select P-0001.</span></span>
4. <span data-ttu-id="ca0f8-120">Klicka på Skapa batchjobb.</span><span class="sxs-lookup"><span data-stu-id="ca0f8-120">Click Create batch job.</span></span>
5. <span data-ttu-id="ca0f8-121">Klicka på Kör i bakgrunden.</span><span class="sxs-lookup"><span data-stu-id="ca0f8-121">Click Run in the background.</span></span>
5. <span data-ttu-id="ca0f8-122">Aktivera Batchbearbetning.</span><span class="sxs-lookup"><span data-stu-id="ca0f8-122">Enable Batch processing.</span></span>
6. <span data-ttu-id="ca0f8-123">Klicka på Upprepning.</span><span class="sxs-lookup"><span data-stu-id="ca0f8-123">Click Recurrence..</span></span>
7. <span data-ttu-id="ca0f8-124">Välj alternativet Slutdatum saknas.</span><span class="sxs-lookup"><span data-stu-id="ca0f8-124">Select the No end date option.</span></span>
8. <span data-ttu-id="ca0f8-125">I fältet Antal anger du intervall mellan körningarna i minuter.</span><span class="sxs-lookup"><span data-stu-id="ca0f8-125">In the Count field, enter interval between the runs in minutes.</span></span> <span data-ttu-id="ca0f8-126">Detta är vanligtvis 5-10.</span><span class="sxs-lookup"><span data-stu-id="ca0f8-126">Typically this would be 5-10.</span></span>
9. <span data-ttu-id="ca0f8-127">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="ca0f8-127">Click OK.</span></span>
10. <span data-ttu-id="ca0f8-128">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="ca0f8-128">Click OK.</span></span>

<span data-ttu-id="ca0f8-129">Order kan synkroniseras antingen genom att köra "Synkronisera order"-jobbet manuellt eller genom att skapa ett återkommande batchjobb.</span><span class="sxs-lookup"><span data-stu-id="ca0f8-129">Orders can be synchronized either by manually running the "Synchronize orders"-job or by creating a recurring batch job.</span></span>

### <a name="manually-running-order-synchronization"></a><span data-ttu-id="ca0f8-130">Köra ordersynkronisering manuellt</span><span class="sxs-lookup"><span data-stu-id="ca0f8-130">Manually running order synchronization</span></span> 

<span data-ttu-id="ca0f8-131">Följ dessa steg om du vill köra "Synkronisera order"-jobb manuellt en gång.</span><span class="sxs-lookup"><span data-stu-id="ca0f8-131">Follow these steps to manually run "Synchronize orders" job once.</span></span>

1. <span data-ttu-id="ca0f8-132">Gå till alla arbetsytor > butiksekonomi.</span><span class="sxs-lookup"><span data-stu-id="ca0f8-132">Go to All workspaces > Store financials.</span></span>
2. <span data-ttu-id="ca0f8-133">Klicka på Synkronisera order.</span><span class="sxs-lookup"><span data-stu-id="ca0f8-133">Click Synchronize orders.</span></span>
3. <span data-ttu-id="ca0f8-134">Välj Butiker efter region i fältet Organisationshierarki.</span><span class="sxs-lookup"><span data-stu-id="ca0f8-134">In the Organization hierarchy field, select 'Stores by Region'.</span></span>
    * <span data-ttu-id="ca0f8-135">Välj antingen en specifik onlinebutik eller välj en nod om du vill skapa batchjobbet för en grupp av butiker.</span><span class="sxs-lookup"><span data-stu-id="ca0f8-135">Select either a specific online store, or select a node if you want to create the batch job for a group of stores.</span></span>  
    * <span data-ttu-id="ca0f8-136">Klicka på pilen om du vill lägga till ditt val.</span><span class="sxs-lookup"><span data-stu-id="ca0f8-136">Click the arrow to add your selection.</span></span>  
4. <span data-ttu-id="ca0f8-137">Klicka på fliken Kör i bakgrunden ...</span><span class="sxs-lookup"><span data-stu-id="ca0f8-137">Click the Run in the background tab.</span></span>
5. <span data-ttu-id="ca0f8-138">Inaktivera Batchbearbetning</span><span class="sxs-lookup"><span data-stu-id="ca0f8-138">Disable Batch processing</span></span>
6. <span data-ttu-id="ca0f8-139">Klicka på Upprepning.</span><span class="sxs-lookup"><span data-stu-id="ca0f8-139">Click Recurrence.</span></span>
7. <span data-ttu-id="ca0f8-140">Välja alternativet Sluta efter</span><span class="sxs-lookup"><span data-stu-id="ca0f8-140">Select End After option</span></span>
8. <span data-ttu-id="ca0f8-141">Ange 1 i fältet Sluta efter.</span><span class="sxs-lookup"><span data-stu-id="ca0f8-141">In the End After field, enter 1.</span></span>
9. <span data-ttu-id="ca0f8-142">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="ca0f8-142">Click OK.</span></span>
10. <span data-ttu-id="ca0f8-143">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="ca0f8-143">Click OK.</span></span>

### <a name="scheduling-recurring-order-synchronization"></a><span data-ttu-id="ca0f8-144">Tidsplanera synkronisering av återkommande order</span><span class="sxs-lookup"><span data-stu-id="ca0f8-144">Scheduling recurring order synchronization</span></span>

<span data-ttu-id="ca0f8-145">Den här proceduren går igenom hur du kör ett återkommande batchjobb om du vill skapa försäljningsorder och betalningar för onlinebutikstransaktioner.</span><span class="sxs-lookup"><span data-stu-id="ca0f8-145">This procedure walks through configuring and running a recurrent batch job to create sales orders and payments for online store transactions.</span></span> <span data-ttu-id="ca0f8-146">I proceduren används demonstrationsföretaget USRT.</span><span class="sxs-lookup"><span data-stu-id="ca0f8-146">This procedure uses the USRT company in demo data.</span></span>

1. <span data-ttu-id="ca0f8-147">Gå till alla arbetsytor > butiksekonomi.</span><span class="sxs-lookup"><span data-stu-id="ca0f8-147">Go to All workspaces > Store financials.</span></span>
2. <span data-ttu-id="ca0f8-148">Klicka på Synkronisera order.</span><span class="sxs-lookup"><span data-stu-id="ca0f8-148">Click Synchronize orders.</span></span>
3. <span data-ttu-id="ca0f8-149">Välj Butiker efter region i fältet Organisationshierarki.</span><span class="sxs-lookup"><span data-stu-id="ca0f8-149">In the Organization hierarchy field, select 'Stores by Region'.</span></span>
    * <span data-ttu-id="ca0f8-150">Välj antingen en specifik onlinebutik eller välj en nod om du vill skapa batchjobbet för en grupp av butiker.</span><span class="sxs-lookup"><span data-stu-id="ca0f8-150">Select either a specific online store, or select a node if you want to create the batch job for a group of stores.</span></span>  
    * <span data-ttu-id="ca0f8-151">Klicka på pilen om du vill lägga till ditt val.</span><span class="sxs-lookup"><span data-stu-id="ca0f8-151">Click the arrow to add your selection.</span></span>  
4. <span data-ttu-id="ca0f8-152">Klicka på fliken Kör i bakgrunden ...</span><span class="sxs-lookup"><span data-stu-id="ca0f8-152">Click the Run in the background tab.</span></span>
5. <span data-ttu-id="ca0f8-153">Aktivera Batchbearbetning</span><span class="sxs-lookup"><span data-stu-id="ca0f8-153">Enable Batch processing</span></span>
6. <span data-ttu-id="ca0f8-154">Klicka på Upprepning.</span><span class="sxs-lookup"><span data-stu-id="ca0f8-154">Click Recurrence.</span></span>
7. <span data-ttu-id="ca0f8-155">Välj alternativet Slutdatum saknas.</span><span class="sxs-lookup"><span data-stu-id="ca0f8-155">Select the No end date option.</span></span>
8. <span data-ttu-id="ca0f8-156">I fältet Antal anger du intervall mellan körningarna i minuter.</span><span class="sxs-lookup"><span data-stu-id="ca0f8-156">In the Count field, enter interval between the runs in minutes.</span></span> <span data-ttu-id="ca0f8-157">Detta är vanligtvis 2-20</span><span class="sxs-lookup"><span data-stu-id="ca0f8-157">Typically this would be 2-20</span></span>
9. <span data-ttu-id="ca0f8-158">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="ca0f8-158">Click OK.</span></span>
10. <span data-ttu-id="ca0f8-159">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="ca0f8-159">Click OK.</span></span>

## <a name="data-entities-involved-in-the-process"></a><span data-ttu-id="ca0f8-160">Dataenheter som är inblandade i processen</span><span class="sxs-lookup"><span data-stu-id="ca0f8-160">Data entities involved in the process</span></span>

- <span data-ttu-id="ca0f8-161">RetailTransactionTable</span><span class="sxs-lookup"><span data-stu-id="ca0f8-161">RetailTransactionTable</span></span>
- <span data-ttu-id="ca0f8-162">RetailTransactionAddressTrans</span><span class="sxs-lookup"><span data-stu-id="ca0f8-162">RetailTransactionAddressTrans</span></span>
- <span data-ttu-id="ca0f8-163">RetailTransactionInfocodeTrans</span><span class="sxs-lookup"><span data-stu-id="ca0f8-163">RetailTransactionInfocodeTrans</span></span>
- <span data-ttu-id="ca0f8-164">RetailTransactionTaxTrans</span><span class="sxs-lookup"><span data-stu-id="ca0f8-164">RetailTransactionTaxTrans</span></span>
- <span data-ttu-id="ca0f8-165">RetailTransactionSalesTrans</span><span class="sxs-lookup"><span data-stu-id="ca0f8-165">RetailTransactionSalesTrans</span></span>
- <span data-ttu-id="ca0f8-166">RetailTransactionTaxMeasure</span><span class="sxs-lookup"><span data-stu-id="ca0f8-166">RetailTransactionTaxMeasure</span></span>
- <span data-ttu-id="ca0f8-167">RetailTransactionDiscountTrans</span><span class="sxs-lookup"><span data-stu-id="ca0f8-167">RetailTransactionDiscountTrans</span></span>
- <span data-ttu-id="ca0f8-168">RetailTransactionTaxTransGTE</span><span class="sxs-lookup"><span data-stu-id="ca0f8-168">RetailTransactionTaxTransGTE</span></span>
- <span data-ttu-id="ca0f8-169">RetailTransactionMarkupTrans</span><span class="sxs-lookup"><span data-stu-id="ca0f8-169">RetailTransactionMarkupTrans</span></span>
- <span data-ttu-id="ca0f8-170">RetailTransactionPaymentTrans</span><span class="sxs-lookup"><span data-stu-id="ca0f8-170">RetailTransactionPaymentTrans</span></span>
- <span data-ttu-id="ca0f8-171">RetailTransactionAttributeTrans</span><span class="sxs-lookup"><span data-stu-id="ca0f8-171">RetailTransactionAttributeTrans</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]