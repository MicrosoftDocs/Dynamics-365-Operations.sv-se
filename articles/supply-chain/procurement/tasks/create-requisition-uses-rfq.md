---
title: Skapa en rekvisition som använder en anbudsförfrågan
description: I det här avsnittet visas hur du lägger till pris- och leverantörsinformation till en inköpsrekvisition från en anbudsförfråganprocess.
author: RichardLuan
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchReqTableListPage, PurchReqCreate, PurchReqTable, PurchReqLineRelatedDocuments, EcoResCategorySingleLookup, PurchReqWorkflowDropDialog, WorkflowSubmitDialog, WorkflowStatus, WorkflowWorkItemActionDialog, WorkflowUserListLookup, PurchReqCopyRFQ, SysDataAreaSelectLookup, PurchRFQCaseTable, PurchRFQEditLines, PurchRFQReplyTable, UnitOfMeasureLookup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 05ff98b5fd95fa345d344e54d9116c73434e5de5
ms.sourcegitcommit: deac22ba5377a912d93fe408c5ae875706378c2d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/16/2021
ms.locfileid: "5018906"
---
# <a name="create-a-requisition-that-uses-an-rfq"></a><span data-ttu-id="8d7cb-103">Skapa en rekvisition som använder en anbudsförfrågan</span><span class="sxs-lookup"><span data-stu-id="8d7cb-103">Create a requisition that uses an RFQ</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="8d7cb-104">I det här avsnittet visas hur du lägger till pris- och leverantörsinformation till en inköpsrekvisition från en anbudsförfråganprocess.</span><span class="sxs-lookup"><span data-stu-id="8d7cb-104">This topic explains how to add price and vendor information to a purchase requisition from an RFQ process.</span></span> <span data-ttu-id="8d7cb-105">De exempel som visas i den här handboken kan användas i demoföretaget USMF och du måste vara inloggad som administratör för att utföra alla steg.</span><span class="sxs-lookup"><span data-stu-id="8d7cb-105">The example shown in this guide can be used in the USMF demo data company, and you must be logged in as an Admin to complete all the steps.</span></span> <span data-ttu-id="8d7cb-106">Uppgifterna i den här handboken utförs normalt av anskaffningsproffs.</span><span class="sxs-lookup"><span data-stu-id="8d7cb-106">The tasks in this guide would typically be done by procurement professionals.</span></span>


## <a name="create-a-requisition"></a><span data-ttu-id="8d7cb-107">Skapaen rekvisition</span><span class="sxs-lookup"><span data-stu-id="8d7cb-107">Create a requisition</span></span>
1. <span data-ttu-id="8d7cb-108">I navigeringsfönstret, gå till **Moduler > Anskaffning och källa > Inköpsrekvisitioner > Inköpsrekvisitioner som har förberetts av mig**.</span><span class="sxs-lookup"><span data-stu-id="8d7cb-108">In the navigation pane, go to **Modules > Procurement and sourcing > Purchase requisitions > Purchase requisitions prepared by me**.</span></span>
2. <span data-ttu-id="8d7cb-109">Välj **Ny**.</span><span class="sxs-lookup"><span data-stu-id="8d7cb-109">Select **New**.</span></span>
3. <span data-ttu-id="8d7cb-110">Skriv ett värde i fältet **Namn**.</span><span class="sxs-lookup"><span data-stu-id="8d7cb-110">In the **Name** field, type a value.</span></span>
4. <span data-ttu-id="8d7cb-111">Ange ett datum i fältet **Begärt datum**.</span><span class="sxs-lookup"><span data-stu-id="8d7cb-111">In the **Requested date** field, enter a date.</span></span>
5. <span data-ttu-id="8d7cb-112">Ange ett datum i fältet **Redovisningsdatum**.</span><span class="sxs-lookup"><span data-stu-id="8d7cb-112">In the **Accounting date** field, enter a date.</span></span>
6. <span data-ttu-id="8d7cb-113">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="8d7cb-113">Select **OK**.</span></span>
7. <span data-ttu-id="8d7cb-114">Ange eller välj ett värde i fältet **Orsak**.</span><span class="sxs-lookup"><span data-stu-id="8d7cb-114">In the **Reason** field, enter or select a value.</span></span>
8. <span data-ttu-id="8d7cb-115">Välj **Markera rad**.</span><span class="sxs-lookup"><span data-stu-id="8d7cb-115">Select **Add line**.</span></span>
9. <span data-ttu-id="8d7cb-116">I fältet **Anskaffningskategori** väljer du en kategori i trädet och väljer **OK**.</span><span class="sxs-lookup"><span data-stu-id="8d7cb-116">In the **Procurement category** field, select a category in the tree, and then select **OK**.</span></span>
10. <span data-ttu-id="8d7cb-117">Skriv ett värde i fältet **Produktnamn**.</span><span class="sxs-lookup"><span data-stu-id="8d7cb-117">In the **Product name** field, type a value.</span></span>
11. <span data-ttu-id="8d7cb-118">Ange ett nummer i fältet **Kvantitet**.</span><span class="sxs-lookup"><span data-stu-id="8d7cb-118">In the **Quantity** field, enter a number.</span></span>
12. <span data-ttu-id="8d7cb-119">Ange eller välj ett värde i fältet **Enhet**.</span><span class="sxs-lookup"><span data-stu-id="8d7cb-119">In the **Unit** field, enter or select a value.</span></span>
13. <span data-ttu-id="8d7cb-120">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="8d7cb-120">Select **Save**.</span></span>
14. <span data-ttu-id="8d7cb-121">Klicka på **Arbetsflöde** för att öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="8d7cb-121">Select **Workflow** to open the drop dialog.</span></span>
15. <span data-ttu-id="8d7cb-122">Välj **skicka**.</span><span class="sxs-lookup"><span data-stu-id="8d7cb-122">Select **Submit**.</span></span>
16. <span data-ttu-id="8d7cb-123">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="8d7cb-123">Close the page.</span></span>
17. <span data-ttu-id="8d7cb-124">Välj **skicka**.</span><span class="sxs-lookup"><span data-stu-id="8d7cb-124">Select **Submit**.</span></span>

## <a name="reassign-a-workflow-task"></a><span data-ttu-id="8d7cb-125">Tilldela om en arbetsflödesuppgift</span><span class="sxs-lookup"><span data-stu-id="8d7cb-125">Reassign a workflow task</span></span>
<span data-ttu-id="8d7cb-126">Nästa uppgift är att skapa en anbudsförfrågan för att få bud från leverantörer för produkten.</span><span class="sxs-lookup"><span data-stu-id="8d7cb-126">The next task is to create an RFQ to get bids from vendors for the product.</span></span> <span data-ttu-id="8d7cb-127">I USMF-demonstrationdata ställs rekvisitionarbetsflödet in med en regel så att om en leverantör inte är markerad, eller om priset per enhet är 0 för en rad, tilldelas en uppgift till en särskild arbetare för att skapa en anbudsförfrågan.</span><span class="sxs-lookup"><span data-stu-id="8d7cb-127">In USMF demo data, the requisition workflow is set up with a rule so that if a vendor is not selected, or the unit price is 0 for a line, a task is assigned to a specific worker to create an RFQ.</span></span> <span data-ttu-id="8d7cb-128">Om du vill fortsätta med den här guiden måste du tilldela om den uppgiften igen till en annan användare (dig själv).</span><span class="sxs-lookup"><span data-stu-id="8d7cb-128">To continue with this guide, you need to re-assign that task to another user (yourself).</span></span> <span data-ttu-id="8d7cb-129">Du kan bara göra detta om du är inloggad som administratör.</span><span class="sxs-lookup"><span data-stu-id="8d7cb-129">You can only do this if you are logged in as an Admin.</span></span>  

1. <span data-ttu-id="8d7cb-130">Klicka på **Arbetsflöde** för att öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="8d7cb-130">Select **Workflow** to open the drop dialog.</span></span>
2. <span data-ttu-id="8d7cb-131">Välj **Visa historik**.</span><span class="sxs-lookup"><span data-stu-id="8d7cb-131">Select **View history**.</span></span>
3. <span data-ttu-id="8d7cb-132">Uppdatera sidan.</span><span class="sxs-lookup"><span data-stu-id="8d7cb-132">Refresh the page.</span></span>
4. <span data-ttu-id="8d7cb-133">Expandera avsnittet **Spårningsuppgifter**.</span><span class="sxs-lookup"><span data-stu-id="8d7cb-133">Expand the **Tracking details** section.</span></span>
5. <span data-ttu-id="8d7cb-134">Välj raden som startar med ”Arbetsflödet för rad aktiverat på” i trädet.</span><span class="sxs-lookup"><span data-stu-id="8d7cb-134">In the tree, select the line that starts with "Line workflow activated on".</span></span>
6. <span data-ttu-id="8d7cb-135">Välj **Visa information om arbetsflöde**.</span><span class="sxs-lookup"><span data-stu-id="8d7cb-135">Select **View workflow details**.</span></span>
7. <span data-ttu-id="8d7cb-136">Expandera avsnittet **Arbetsuppgifter**.</span><span class="sxs-lookup"><span data-stu-id="8d7cb-136">Expand the **Work items** section.</span></span>
8. <span data-ttu-id="8d7cb-137">Välj **Tilldela om**.</span><span class="sxs-lookup"><span data-stu-id="8d7cb-137">Select **Reassign**.</span></span>
9. <span data-ttu-id="8d7cb-138">Välj **Administratör** i fältet **Användare**.</span><span class="sxs-lookup"><span data-stu-id="8d7cb-138">In the **User** field, select **Admin**.</span></span>
10. <span data-ttu-id="8d7cb-139">Välj **Tilldela om**.</span><span class="sxs-lookup"><span data-stu-id="8d7cb-139">Select **Reassign**.</span></span>
11. <span data-ttu-id="8d7cb-140">Stäng de två sidorna.</span><span class="sxs-lookup"><span data-stu-id="8d7cb-140">Close the two pages.</span></span>

## <a name="create-an-rfq"></a><span data-ttu-id="8d7cb-141">Skapa en anbudsförfrågan</span><span class="sxs-lookup"><span data-stu-id="8d7cb-141">Create an RFQ</span></span>

1. <span data-ttu-id="8d7cb-142">Uppdatera sidan.</span><span class="sxs-lookup"><span data-stu-id="8d7cb-142">Refresh the page.</span></span>
2. <span data-ttu-id="8d7cb-143">Välj **Anbudsförfrågan**.</span><span class="sxs-lookup"><span data-stu-id="8d7cb-143">Select **Request for quotation**.</span></span>
3. <span data-ttu-id="8d7cb-144">I fältet **Juridisk person för inköp** väljer du **USMF**.</span><span class="sxs-lookup"><span data-stu-id="8d7cb-144">In the **Buying legal entity** field, select **USMF**.</span></span> <span data-ttu-id="8d7cb-145">Du måste välja samma juridiska person som finns på rekvisitionraden.</span><span class="sxs-lookup"><span data-stu-id="8d7cb-145">You must select the same legal entity that's on the requisition line.</span></span>  
4. <span data-ttu-id="8d7cb-146">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="8d7cb-146">In the list, mark the selected row.</span></span> <span data-ttu-id="8d7cb-147">Om du har flera rader i din inköpsrekvisition, markerar du alla rader som du vill lägga till i anbudsförfrågan.</span><span class="sxs-lookup"><span data-stu-id="8d7cb-147">If you had multiple lines on your purchase requisition, select all the lines that you want to add to the RFQ.</span></span>  
5. <span data-ttu-id="8d7cb-148">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="8d7cb-148">Select **OK**.</span></span>
6. <span data-ttu-id="8d7cb-149">Uppdatera sidan.</span><span class="sxs-lookup"><span data-stu-id="8d7cb-149">Refresh the page.</span></span>
7. <span data-ttu-id="8d7cb-150">Öppna faktaboxen och expandera sedan avsnittet **Relaterade dokument**.</span><span class="sxs-lookup"><span data-stu-id="8d7cb-150">Ensure that the FactBox is open, then expand the **Related documents** section.</span></span>
8. <span data-ttu-id="8d7cb-151">Välj länken i fältet **Anbudsförfrågan** för att öppna anbudsförfrågan som just har skapats.</span><span class="sxs-lookup"><span data-stu-id="8d7cb-151">Select the link in the **Request for quotation** field to open the RFQ that was just created.</span></span>
9. <span data-ttu-id="8d7cb-152">Välj **Sidhuvud**.</span><span class="sxs-lookup"><span data-stu-id="8d7cb-152">Select **Header**.</span></span>
10. <span data-ttu-id="8d7cb-153">Markera **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="8d7cb-153">Select **Add**.</span></span>
11. <span data-ttu-id="8d7cb-154">I **leverantörskonto** fält, ange eller välj ett värde.</span><span class="sxs-lookup"><span data-stu-id="8d7cb-154">In the **Vendor account** field, enter or select a value.</span></span>
12. <span data-ttu-id="8d7cb-155">Markera **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="8d7cb-155">Select **Add**.</span></span>
13. <span data-ttu-id="8d7cb-156">I **leverantörskonto** fält, ange eller välj ett värde.</span><span class="sxs-lookup"><span data-stu-id="8d7cb-156">In the **Vendor account** field, enter or select a value.</span></span>
14. <span data-ttu-id="8d7cb-157">Välj **Skicka**.</span><span class="sxs-lookup"><span data-stu-id="8d7cb-157">Select **Send**.</span></span>
15. <span data-ttu-id="8d7cb-158">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="8d7cb-158">Select **OK**.</span></span>
16. <span data-ttu-id="8d7cb-159">Välj **Ange svar**.</span><span class="sxs-lookup"><span data-stu-id="8d7cb-159">Select **Enter reply**.</span></span>
17. <span data-ttu-id="8d7cb-160">Klicka på **Svar** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="8d7cb-160">On the Action Pane, select **Reply**.</span></span>
18. <span data-ttu-id="8d7cb-161">Välj **Kopiera data till svar**.</span><span class="sxs-lookup"><span data-stu-id="8d7cb-161">Select **Copy data to reply**.</span></span> <span data-ttu-id="8d7cb-162">Då kopieras data, till exempel kvantitet och datum, från anbudsförfrågan till svaret.</span><span class="sxs-lookup"><span data-stu-id="8d7cb-162">This copies data, such as the quantity and dates, from the RFQ to the reply.</span></span>  
19. <span data-ttu-id="8d7cb-163">Ange ett tal i fältet **Enhetspris**.</span><span class="sxs-lookup"><span data-stu-id="8d7cb-163">In the **Unit price** field, enter a number.</span></span> <span data-ttu-id="8d7cb-164">Detta är priset som du har tagit emot från leverantören.</span><span class="sxs-lookup"><span data-stu-id="8d7cb-164">This is the price that you've received from the vendor.</span></span> <span data-ttu-id="8d7cb-165">Du kanske också vill ange ytterligare information från leverantören.</span><span class="sxs-lookup"><span data-stu-id="8d7cb-165">You might also want to enter additional information from the vendor.</span></span>  
20. <span data-ttu-id="8d7cb-166">Välj **Godkänn**.</span><span class="sxs-lookup"><span data-stu-id="8d7cb-166">Select **Accept**.</span></span>
21. <span data-ttu-id="8d7cb-167">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="8d7cb-167">Select **OK**.</span></span>

## <a name="verify-that-vendor-and-price-have-been-transferred-to-the-requisition"></a><span data-ttu-id="8d7cb-168">Kontrollera att leverantören och priset har överförts till rekvisitionen</span><span class="sxs-lookup"><span data-stu-id="8d7cb-168">Verify that vendor and price have been transferred to the requisition</span></span>
1. <span data-ttu-id="8d7cb-169">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="8d7cb-169">Close the page.</span></span>
2. <span data-ttu-id="8d7cb-170">Markera **rader**</span><span class="sxs-lookup"><span data-stu-id="8d7cb-170">Select **Lines**.</span></span>
3. <span data-ttu-id="8d7cb-171">Välj **Relaterad information**.</span><span class="sxs-lookup"><span data-stu-id="8d7cb-171">Select **Related information**.</span></span>
4. <span data-ttu-id="8d7cb-172">Välj **Inköpsrekvisition**.</span><span class="sxs-lookup"><span data-stu-id="8d7cb-172">Select **Purchase requisition**.</span></span>
5. <span data-ttu-id="8d7cb-173">Markera raden som har överförts till anbudsförfrågan.</span><span class="sxs-lookup"><span data-stu-id="8d7cb-173">Select the line that was transferred to the RFQ.</span></span> <span data-ttu-id="8d7cb-174">Kontrollera att priset och leverantören har kopierats till rekvisitionen.</span><span class="sxs-lookup"><span data-stu-id="8d7cb-174">Verify that the price and vendor have been copied to the requisition.</span></span>  
6. <span data-ttu-id="8d7cb-175">Klicka på **Arbetsflöde** för att öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="8d7cb-175">Select **Workflow** to open the drop dialog.</span></span>
7. <span data-ttu-id="8d7cb-176">Välj Slutför.</span><span class="sxs-lookup"><span data-stu-id="8d7cb-176">Select Complete.</span></span>
8. <span data-ttu-id="8d7cb-177">Välj sidan.</span><span class="sxs-lookup"><span data-stu-id="8d7cb-177">Select the page.</span></span>
9. <span data-ttu-id="8d7cb-178">Välj Slutför.</span><span class="sxs-lookup"><span data-stu-id="8d7cb-178">Select Complete.</span></span>

