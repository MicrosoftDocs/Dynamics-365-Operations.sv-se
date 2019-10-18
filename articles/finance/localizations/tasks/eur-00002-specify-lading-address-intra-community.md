---
title: EUR-00002 Ange en fraktadress för en inomeuropeisk transaktion
description: I den här proceduren visas hur du anger en fraktadress för en transaktion för inomeuropeisk handel.
author: v-oloski
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchTable, PurchCreateOrder, InventItemIdLookupPurchase, TransportationDocument, LogisticsPostalAddress, SysLookupMultiSelectGrid,  VendEditInvoice, VendEditInvoiceDefaultQuantityForLinesDropDialog, Intrastat, SysQueryForm
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Austria, Belgium, Czech Republic, Denmark, Estonia, Finland, France, Germany, Hungary, Ireland, Italy, Latvia, Lithuania, Netherlands, Poland, Spain, Sweden, United Kingdom
ms.author: v-oloski
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 6eea2a905a59842b6f39c5b1e1c78ae6801b28e0
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/27/2019
ms.locfileid: "2175081"
---
# <a name="eur-00002-specifying-a-lading-address-for-an-intra-community-transaction"></a><span data-ttu-id="09b99-103">EUR-00002 Ange en fraktadress för en inomeuropeisk transaktion</span><span class="sxs-lookup"><span data-stu-id="09b99-103">EUR-00002 Specifying a lading address for an intra-community transaction</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="09b99-104">I den här proceduren visas hur du anger en fraktadress för en transaktion för inomeuropeisk handel.</span><span class="sxs-lookup"><span data-stu-id="09b99-104">This procedure shows how to specify a lading address for an intra-community trade transaction.</span></span> <span data-ttu-id="09b99-105">Till exempel: Ett företag i Tyskland beställer artiklar från en leverantör med tysk företagsadress.</span><span class="sxs-lookup"><span data-stu-id="09b99-105">For example, a Germany company orders items from a vendor with a German business address.</span></span> <span data-ttu-id="09b99-106">Denna leverantör har ett lager i Italien och skickar artiklarna därifrån.</span><span class="sxs-lookup"><span data-stu-id="09b99-106">This vendor has a warehouse in Italy and ships the items from there.</span></span> <span data-ttu-id="09b99-107">Denna leverans måste visas i Intrastat.</span><span class="sxs-lookup"><span data-stu-id="09b99-107">This delivery must be reported in the Intrastat.</span></span> <span data-ttu-id="09b99-108">Samma förfarande gäller för kundreturer.</span><span class="sxs-lookup"><span data-stu-id="09b99-108">The same behavior is valid for customer returns.</span></span>
<span data-ttu-id="09b99-109">Den här proceduren gäller för alla europeiska länder/regioner.</span><span class="sxs-lookup"><span data-stu-id="09b99-109">This procedure applies to all European countries/regions.</span></span> <span data-ttu-id="09b99-110">Uppgiften skapades med hjälp av demonstrationsdataföretaget DEMF, med primär adress i Tyskland.</span><span class="sxs-lookup"><span data-stu-id="09b99-110">The task was created using the demo data company DEMF with a primary address in Germany.</span></span> <span data-ttu-id="09b99-111">Innan du kan slutföra proceduren måste du konfigurera Intrastat-rapporteringen.</span><span class="sxs-lookup"><span data-stu-id="09b99-111">Before you can complete this procedure, you must configure Intrastat reporting.</span></span> <span data-ttu-id="09b99-112">Proceduren är avsedd för kamrerer.</span><span class="sxs-lookup"><span data-stu-id="09b99-112">This procedure is intended for accountants.</span></span> <span data-ttu-id="09b99-113">Denna procedur är avsedd för en funktion som lades till i Dynamics 365 for Operations version 1611.</span><span class="sxs-lookup"><span data-stu-id="09b99-113">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>

1. <span data-ttu-id="09b99-114">Gå till leverantörsskulder > inköpsorder > Alla inköpsorder.</span><span class="sxs-lookup"><span data-stu-id="09b99-114">Go to Accounts payable > Purchase orders > All purchase orders.</span></span>
2. <span data-ttu-id="09b99-115">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="09b99-115">Click New.</span></span>
3. <span data-ttu-id="09b99-116">Ange eller välj ett värde</span><span class="sxs-lookup"><span data-stu-id="09b99-116">Enter or select a value</span></span>
    * <span data-ttu-id="09b99-117">Välj till exempel DE-001.</span><span class="sxs-lookup"><span data-stu-id="09b99-117">For example, select DE-001.</span></span> <span data-ttu-id="09b99-118">Denna leverantör har en tysk företagsadress.</span><span class="sxs-lookup"><span data-stu-id="09b99-118">This vendor has a German business address.</span></span>  
4. <span data-ttu-id="09b99-119">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="09b99-119">Click OK.</span></span>
5. <span data-ttu-id="09b99-120">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="09b99-120">In the list, mark the selected row.</span></span>
6. <span data-ttu-id="09b99-121">Ange eller välj värdet D0001 i fältet Item number.</span><span class="sxs-lookup"><span data-stu-id="09b99-121">In the Item number field, enter or select a value D0001.</span></span>
7. <span data-ttu-id="09b99-122">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="09b99-122">Click Save.</span></span>
8. <span data-ttu-id="09b99-123">Klicka på Ta emot i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="09b99-123">On the Action Pane, click Receive.</span></span>
9. <span data-ttu-id="09b99-124">Klicka på Transportation details.</span><span class="sxs-lookup"><span data-stu-id="09b99-124">Click Transportation details.</span></span>
10. <span data-ttu-id="09b99-125">I fältet Loading date and time anger du datum och tid.</span><span class="sxs-lookup"><span data-stu-id="09b99-125">In the Loading date and time field, enter a date and time.</span></span>
11. <span data-ttu-id="09b99-126">Klicka på Add address.</span><span class="sxs-lookup"><span data-stu-id="09b99-126">Click Add address.</span></span>
12. <span data-ttu-id="09b99-127">Klicka på New och skapa den nya adressen med syftet Lading.</span><span class="sxs-lookup"><span data-stu-id="09b99-127">Click New and create new address with purpose Lading.</span></span>
13. <span data-ttu-id="09b99-128">Ange "Italian" i fältet Name or description.</span><span class="sxs-lookup"><span data-stu-id="09b99-128">In the Name or description field, type 'Italian'.</span></span>
14. <span data-ttu-id="09b99-129">Välj Lading som värde.</span><span class="sxs-lookup"><span data-stu-id="09b99-129">Select Lading as the value.</span></span>
    * <span data-ttu-id="09b99-130">Observera att adress-syftet måste vara Lading.</span><span class="sxs-lookup"><span data-stu-id="09b99-130">Note that that address purpose must be Lading.</span></span>  
15. <span data-ttu-id="09b99-131">Ange eller välj värdet ITA i fältet Country/region.</span><span class="sxs-lookup"><span data-stu-id="09b99-131">In the Country/region field, enter or select a value ITA.</span></span>
16. <span data-ttu-id="09b99-132">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="09b99-132">Click Save.</span></span>
17. <span data-ttu-id="09b99-133">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="09b99-133">Close the page.</span></span>
18. <span data-ttu-id="09b99-134">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="09b99-134">Click Save.</span></span>
    * <span data-ttu-id="09b99-135">Kontrollera att fraktadressen är korrekt.</span><span class="sxs-lookup"><span data-stu-id="09b99-135">Verify that the lading address is correct.</span></span>  
19. <span data-ttu-id="09b99-136">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="09b99-136">Close the page.</span></span>
20. <span data-ttu-id="09b99-137">Klicka på Inköp i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="09b99-137">On the Action Pane, click Purchase.</span></span>
21. <span data-ttu-id="09b99-138">Klicka på Bekräfta.</span><span class="sxs-lookup"><span data-stu-id="09b99-138">Click Confirm.</span></span>
22. <span data-ttu-id="09b99-139">Klicka på Faktura i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="09b99-139">On the Action Pane, click Invoice.</span></span>
23. <span data-ttu-id="09b99-140">Klicka på Faktura.</span><span class="sxs-lookup"><span data-stu-id="09b99-140">Click Invoice.</span></span>
24. <span data-ttu-id="09b99-141">Ange ett värde i fältet Antal.</span><span class="sxs-lookup"><span data-stu-id="09b99-141">In the Number field, type a value.</span></span>
25. <span data-ttu-id="09b99-142">Ange ett datum i fältet Fakturadatum.</span><span class="sxs-lookup"><span data-stu-id="09b99-142">In the Invoice date field, enter a date.</span></span>
26. <span data-ttu-id="09b99-143">Klicka på Default from: Product receipt quantity för att öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="09b99-143">Click Default from: Product receipt quantity to open the drop dialog.</span></span>
27. <span data-ttu-id="09b99-144">I fältet Default quantity for lines väljer du "Ordered quantity".</span><span class="sxs-lookup"><span data-stu-id="09b99-144">In the Default quantity for lines field, select 'Ordered quantity'.</span></span>
28. <span data-ttu-id="09b99-145">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="09b99-145">Click OK.</span></span>
29. <span data-ttu-id="09b99-146">Klicka på Transportation details.</span><span class="sxs-lookup"><span data-stu-id="09b99-146">Click Transportation details.</span></span>
    * <span data-ttu-id="09b99-147">Kontrollera att varorna skeppades från Italien.</span><span class="sxs-lookup"><span data-stu-id="09b99-147">Verify that goods were shipped from Italy.</span></span> <span data-ttu-id="09b99-148">Vid behov kan du redigera fraktformationen.</span><span class="sxs-lookup"><span data-stu-id="09b99-148">If necessary, you can edit the lading details.</span></span>  
30. <span data-ttu-id="09b99-149">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="09b99-149">Close the page.</span></span>
31. <span data-ttu-id="09b99-150">Klicka på Bokför.</span><span class="sxs-lookup"><span data-stu-id="09b99-150">Click Post.</span></span>
32. <span data-ttu-id="09b99-151">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="09b99-151">Close the page.</span></span>
33. <span data-ttu-id="09b99-152">Gå till Moms > Deklarationer > Utländsk handel > Intrastat.</span><span class="sxs-lookup"><span data-stu-id="09b99-152">Go to Tax > Declarations > Foreign trade > Intrastat.</span></span>
34. <span data-ttu-id="09b99-153">Klicka på Överför.</span><span class="sxs-lookup"><span data-stu-id="09b99-153">Click Transfer.</span></span>
35. <span data-ttu-id="09b99-154">Välj Yes i fältet Vendor invoice.</span><span class="sxs-lookup"><span data-stu-id="09b99-154">Select Yes in the Vendor invoice field.</span></span>
36. <span data-ttu-id="09b99-155">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="09b99-155">Click OK.</span></span>
37. <span data-ttu-id="09b99-156">Klicka på fliken Allmänt.</span><span class="sxs-lookup"><span data-stu-id="09b99-156">Click the General tab.</span></span>
    * <span data-ttu-id="09b99-157">Sök efter en nyligen skapad rad och kontrollera att avsändaren skickade varorna från Italien.</span><span class="sxs-lookup"><span data-stu-id="09b99-157">Find a newly created line and verify that the sender shipped the goods from Italy.</span></span>  

