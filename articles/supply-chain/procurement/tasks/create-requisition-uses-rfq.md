---
title: Skapa en rekvisition som använder en anbudsförfrågan
description: Den här handboken visar hur du lägger till pris- och leverantörsinformation till en inköpsrekvisition från en anbudsförfråganprocess.
author: mkirknel
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchReqTableListPage, PurchReqCreate, PurchReqTable, PurchReqLineRelatedDocuments, EcoResCategorySingleLookup, PurchReqWorkflowDropDialog, WorkflowSubmitDialog, WorkflowStatus, WorkflowWorkItemActionDialog, WorkflowUserListLookup, PurchReqCopyRFQ, SysDataAreaSelectLookup, PurchRFQCaseTable, PurchRFQEditLines, PurchRFQReplyTable, UnitOfMeasureLookup
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 8a9418b526f992008086f10ce78e95cb682bc164
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2019
ms.locfileid: "344994"
---
# <a name="create-a-requisition-that-uses-an-rfq"></a><span data-ttu-id="22192-103">Skapa en rekvisition som använder en anbudsförfrågan</span><span class="sxs-lookup"><span data-stu-id="22192-103">Create a requisition that uses an RFQ</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="22192-104">Den här handboken visar hur du lägger till pris- och leverantörsinformation till en inköpsrekvisition från en anbudsförfråganprocess.</span><span class="sxs-lookup"><span data-stu-id="22192-104">This guide shows how to add price and vendor information to a purchase requisition from an RFQ process.</span></span> <span data-ttu-id="22192-105">De exempel som visas i den här handboken kan användas i demoföretaget USMF och du måste vara inloggad som administratör för att utföra alla steg.</span><span class="sxs-lookup"><span data-stu-id="22192-105">The example shown in this guide can be used in the USMF demo data company, and you must be logged in as an Admin to complete all the steps.</span></span> <span data-ttu-id="22192-106">Uppgifterna i den här handboken utförs normalt av anskaffningsproffs.</span><span class="sxs-lookup"><span data-stu-id="22192-106">The tasks in this guide would typically be done by procurement professionals.</span></span>


## <a name="create-a-requisition"></a><span data-ttu-id="22192-107">Skapaen rekvisition</span><span class="sxs-lookup"><span data-stu-id="22192-107">Create a requisition</span></span>
1. <span data-ttu-id="22192-108">Gå till Anskaffning och källa > Inköpsrekvisitioner > Inköpsrekvisitioner som har förberetts av mig.</span><span class="sxs-lookup"><span data-stu-id="22192-108">Go to Procurement and sourcing > Purchase requisitions > Purchase requisitions prepared by me.</span></span>
2. <span data-ttu-id="22192-109">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="22192-109">Click New.</span></span>
3. <span data-ttu-id="22192-110">Skriv ett värde i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="22192-110">In the Name field, type a value.</span></span>
4. <span data-ttu-id="22192-111">Ange ett datum i fältet Begärt datum.</span><span class="sxs-lookup"><span data-stu-id="22192-111">In the Requested date field, enter a date.</span></span>
5. <span data-ttu-id="22192-112">Ange ett datum i fältet Redovisningsdatum.</span><span class="sxs-lookup"><span data-stu-id="22192-112">In the Accounting date field, enter a date.</span></span>
6. <span data-ttu-id="22192-113">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="22192-113">Click OK.</span></span>
7. <span data-ttu-id="22192-114">Ange eller välj ett värde i fältet Orsak.</span><span class="sxs-lookup"><span data-stu-id="22192-114">In the Reason field, enter or select a value.</span></span>
8. <span data-ttu-id="22192-115">Klicka på Lägg till rad.</span><span class="sxs-lookup"><span data-stu-id="22192-115">Click Add line.</span></span>
9. <span data-ttu-id="22192-116">I fältet Anskaffningkategori väljer du kategori i trädet och klickar på OK.</span><span class="sxs-lookup"><span data-stu-id="22192-116">In the Procurement category field, select a category in the tree, and then click OK.</span></span>
10. <span data-ttu-id="22192-117">Skriv ett värde i fältet Produktnamn.</span><span class="sxs-lookup"><span data-stu-id="22192-117">In the Product name field, type a value.</span></span>
11. <span data-ttu-id="22192-118">Ange ett tal i fältet Kvantitet.</span><span class="sxs-lookup"><span data-stu-id="22192-118">In the Quantity field, enter a number.</span></span>
12. <span data-ttu-id="22192-119">Ange eller välj ett värde i fältet Enhet.</span><span class="sxs-lookup"><span data-stu-id="22192-119">In the Unit field, enter or select a value.</span></span>
13. <span data-ttu-id="22192-120">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="22192-120">Click Save.</span></span>
14. <span data-ttu-id="22192-121">Klicka på Arbetsflöde för att öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="22192-121">Click Workflow to open the drop dialog.</span></span>
15. <span data-ttu-id="22192-122">Klicka på Skicka.</span><span class="sxs-lookup"><span data-stu-id="22192-122">Click Submit.</span></span>
16. <span data-ttu-id="22192-123">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="22192-123">Close the page.</span></span>
17. <span data-ttu-id="22192-124">Klicka på Skicka.</span><span class="sxs-lookup"><span data-stu-id="22192-124">Click Submit.</span></span>

## <a name="reassign-a-workflow-task"></a><span data-ttu-id="22192-125">Tilldela om en arbetsflödesuppgift</span><span class="sxs-lookup"><span data-stu-id="22192-125">Reassign a workflow task</span></span>
    * <span data-ttu-id="22192-126">Nästa uppgift är att skapa en anbudsförfrågan för att få bud från leverantörer för produkten.</span><span class="sxs-lookup"><span data-stu-id="22192-126">The next task is to create an RFQ to get bids from vendors for the product.</span></span> <span data-ttu-id="22192-127">I USMF-demonstrationdata ställs rekvisitionarbetsflödet in med en regel så att om en leverantör inte är markerad, eller om priset per enhet är 0 för en rad, tilldelas en uppgift till en särskild arbetare för att skapa en anbudsförfrågan.</span><span class="sxs-lookup"><span data-stu-id="22192-127">In USMF demo data, the requisition workflow is set up with a rule so that if a vendor is not selected, or the unit price is 0 for a line, a task is assigned to a specific worker to create an RFQ.</span></span> <span data-ttu-id="22192-128">Om du vill fortsätta med den här guiden måste du tilldela om den uppgiften igen till en annan användare (dig själv).</span><span class="sxs-lookup"><span data-stu-id="22192-128">To continue with this guide, you need to re-assign that task to another user (yourself).</span></span> <span data-ttu-id="22192-129">Du kan bara göra detta om du är inloggad som administratör.</span><span class="sxs-lookup"><span data-stu-id="22192-129">You can only do this if you are logged in as an Admin.</span></span>  
1. <span data-ttu-id="22192-130">Klicka på Arbetsflöde för att öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="22192-130">Click Workflow to open the drop dialog.</span></span>
2. <span data-ttu-id="22192-131">Klicka på Visa historik.</span><span class="sxs-lookup"><span data-stu-id="22192-131">Click View history.</span></span>
3. <span data-ttu-id="22192-132">Uppdatera sidan.</span><span class="sxs-lookup"><span data-stu-id="22192-132">Refresh the page.</span></span>
4. <span data-ttu-id="22192-133">Expandera avsnittet Spårningsuppgifter.</span><span class="sxs-lookup"><span data-stu-id="22192-133">Expand the Tracking details section.</span></span>
5. <span data-ttu-id="22192-134">Välj ”raden som startar med ”Arbetsflödet för rad aktiverat på” i trädet.</span><span class="sxs-lookup"><span data-stu-id="22192-134">In the tree, select 'the line that starts with “Line workflow activated on”'.</span></span>
6. <span data-ttu-id="22192-135">Klicka på Visa information om arbetsflöde.</span><span class="sxs-lookup"><span data-stu-id="22192-135">Click View workflow details.</span></span>
7. <span data-ttu-id="22192-136">Expandera avsnittet Arbetsuppgifter.</span><span class="sxs-lookup"><span data-stu-id="22192-136">Expand the Work items section.</span></span>
8. <span data-ttu-id="22192-137">Klicka på Tilldela om.</span><span class="sxs-lookup"><span data-stu-id="22192-137">Click Reassign.</span></span>
9. <span data-ttu-id="22192-138">Välj Administraör i fältet Användare.</span><span class="sxs-lookup"><span data-stu-id="22192-138">In the User field, select Admin.</span></span>
10. <span data-ttu-id="22192-139">Klicka på Tilldela om.</span><span class="sxs-lookup"><span data-stu-id="22192-139">Click Reassign.</span></span>
11. <span data-ttu-id="22192-140">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="22192-140">Close the page.</span></span>
12. <span data-ttu-id="22192-141">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="22192-141">Close the page.</span></span>

## <a name="create-an-rfq"></a><span data-ttu-id="22192-142">Skapa en anbudsförfrågan</span><span class="sxs-lookup"><span data-stu-id="22192-142">Create an RFQ</span></span>
1. <span data-ttu-id="22192-143">Uppdatera sidan.</span><span class="sxs-lookup"><span data-stu-id="22192-143">Refresh the page.</span></span>
2. <span data-ttu-id="22192-144">Klicka på Anbudsförfrågan.</span><span class="sxs-lookup"><span data-stu-id="22192-144">Click Request for quotation.</span></span>
3. <span data-ttu-id="22192-145">Välj USMF i fältet Juridisk person för inköp.</span><span class="sxs-lookup"><span data-stu-id="22192-145">In the Buying legal entity field, select USMF.</span></span>
    * <span data-ttu-id="22192-146">Du måste välja samma juridiska person som finns på rekvisitionraden.</span><span class="sxs-lookup"><span data-stu-id="22192-146">You must select the same legal entity that’s on the requisition line.</span></span>  
4. <span data-ttu-id="22192-147">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="22192-147">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="22192-148">Om du har flera rader i din inköpsrekvisition, markerar du alla rader som du vill lägga till i anbudsförfrågan.</span><span class="sxs-lookup"><span data-stu-id="22192-148">If you had multiple lines on your purchase requisition, select all the lines that you want to add to the RFQ.</span></span>  
5. <span data-ttu-id="22192-149">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="22192-149">Click OK.</span></span>
6. <span data-ttu-id="22192-150">Uppdatera sidan.</span><span class="sxs-lookup"><span data-stu-id="22192-150">Refresh the page.</span></span>
7. <span data-ttu-id="22192-151">Öppna faktaboxen och expandera sedan avsnittet Relaterade dokument.</span><span class="sxs-lookup"><span data-stu-id="22192-151">Open the FactBox and then expand the Related documents section.</span></span>
    * <span data-ttu-id="22192-152">Du kanske redan har faktaboxen öppen.</span><span class="sxs-lookup"><span data-stu-id="22192-152">You may already have the FactBox open.</span></span> <span data-ttu-id="22192-153">Sök efter ikonen med en pil till höger om växlingsknapparna rader/rubrik.</span><span class="sxs-lookup"><span data-stu-id="22192-153">Look for the icon with an arrow on it, to the right of the Lines/Header toggle buttons.</span></span> <span data-ttu-id="22192-154">Om pilen pekar till höger är faktaboxen redan öppen.</span><span class="sxs-lookup"><span data-stu-id="22192-154">If the arrow is pointing to the right, the FactBox is already open.</span></span> <span data-ttu-id="22192-155">Om pilen pekar åt vänster klickar du på den för att öppna faktaboxen.</span><span class="sxs-lookup"><span data-stu-id="22192-155">If the arrow points to the left, click it to open the FactBox.</span></span>  
8. <span data-ttu-id="22192-156">Klicka på länken i fältet Anbudsförfrågan för att öppna anbudsförfrågan som just har skapats.</span><span class="sxs-lookup"><span data-stu-id="22192-156">Click the link in the Request for quotation field to open the RFQ that was just created.</span></span>
9. <span data-ttu-id="22192-157">Klicka på Rubrik.</span><span class="sxs-lookup"><span data-stu-id="22192-157">Click Header.</span></span>
10. <span data-ttu-id="22192-158">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="22192-158">Click Add.</span></span>
11. <span data-ttu-id="22192-159">Ange eller välj ett värde i fältet Leverantörskonto.</span><span class="sxs-lookup"><span data-stu-id="22192-159">In the Vendor account field, enter or select a value.</span></span>
12. <span data-ttu-id="22192-160">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="22192-160">Click Add.</span></span>
13. <span data-ttu-id="22192-161">Ange eller välj ett värde i fältet Leverantörskonto.</span><span class="sxs-lookup"><span data-stu-id="22192-161">In the Vendor account field, enter or select a value.</span></span>
14. <span data-ttu-id="22192-162">Klicka på Skicka.</span><span class="sxs-lookup"><span data-stu-id="22192-162">Click Send.</span></span>
15. <span data-ttu-id="22192-163">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="22192-163">Click OK.</span></span>
16. <span data-ttu-id="22192-164">Klicka på Ange svar.</span><span class="sxs-lookup"><span data-stu-id="22192-164">Click Enter reply.</span></span>
17. <span data-ttu-id="22192-165">Klicka på Svar i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="22192-165">On the Action Pane, click Reply.</span></span>
18. <span data-ttu-id="22192-166">Klicka på Kopiera data för att svara.</span><span class="sxs-lookup"><span data-stu-id="22192-166">Click Copy data to reply.</span></span>
    * <span data-ttu-id="22192-167">Då kopieras data, till exempel kvantitet och datum, från anbudsförfrågan till svaret.</span><span class="sxs-lookup"><span data-stu-id="22192-167">This copies data, such as the quantity and dates, from the RFQ to the reply .</span></span>  
19. <span data-ttu-id="22192-168">Ange ett tal i fältet Enhetspris.</span><span class="sxs-lookup"><span data-stu-id="22192-168">In the Unit price field, enter a number.</span></span>
    * <span data-ttu-id="22192-169">Detta är priset som du har tagit emot från leverantören.</span><span class="sxs-lookup"><span data-stu-id="22192-169">This is the price that you’ve received from the vendor.</span></span> <span data-ttu-id="22192-170">Du kanske också vill ange ytterligare information från leverantören.</span><span class="sxs-lookup"><span data-stu-id="22192-170">You might also want to enter additional information from the vendor.</span></span>  
20. <span data-ttu-id="22192-171">Klicka på Godkänn.</span><span class="sxs-lookup"><span data-stu-id="22192-171">Click Accept.</span></span>
21. <span data-ttu-id="22192-172">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="22192-172">Click OK.</span></span>

## <a name="verify-that-vendor-and-price-have-been-transferred-to-the-requisition"></a><span data-ttu-id="22192-173">Kontrollera att leverantören och priset har överförts till rekvisitionen</span><span class="sxs-lookup"><span data-stu-id="22192-173">Verify that vendor and price have been transferred to the requisition</span></span>
1. <span data-ttu-id="22192-174">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="22192-174">Close the page.</span></span>
2. <span data-ttu-id="22192-175">Klicka på Rader.</span><span class="sxs-lookup"><span data-stu-id="22192-175">Click Lines.</span></span>
3. <span data-ttu-id="22192-176">Klicka på Relaterad information.</span><span class="sxs-lookup"><span data-stu-id="22192-176">Click Related information.</span></span>
4. <span data-ttu-id="22192-177">Klicka på Inköpsrekvisition.</span><span class="sxs-lookup"><span data-stu-id="22192-177">Click Purchase requisition.</span></span>
5. <span data-ttu-id="22192-178">Markera raden som har överförts till anbudsförfrågan.</span><span class="sxs-lookup"><span data-stu-id="22192-178">Select the line that was transferred to the RFQ.</span></span>
    * <span data-ttu-id="22192-179">Kontrollera att priset och leverantören har kopierats till rekvisitionen.</span><span class="sxs-lookup"><span data-stu-id="22192-179">Verify that the price and vendor have been copied to the requisition.</span></span>  
6. <span data-ttu-id="22192-180">Klicka på Arbetsflöde för att öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="22192-180">Click Workflow to open the drop dialog.</span></span>
7. <span data-ttu-id="22192-181">Klicka på Slutför.</span><span class="sxs-lookup"><span data-stu-id="22192-181">Click Complete.</span></span>
8. <span data-ttu-id="22192-182">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="22192-182">Close the page.</span></span>
9. <span data-ttu-id="22192-183">Klicka på Slutför.</span><span class="sxs-lookup"><span data-stu-id="22192-183">Click Complete.</span></span>

