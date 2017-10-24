--- 
title: "Skapa en formatkonfiguration för elektronisk rapportering (ER)"
description: "I följande steg förklaras hur en användare i rollen Systemadministratör eller Utvecklare för elektronisk rapportering kan skapa en formatkonfiguration för elektronisk rapportering (ER)."
author: NickSelin
manager: AnnBe
ms.date: 01/16/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 04817d1f1851e43679995641e8b0ff99edaa83ad
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---
# <a name="create-a-format-configuration-for-electronic-reporting-er"></a><span data-ttu-id="44822-103">Skapa en formatkonfiguration för elektronisk rapportering (ER)</span><span class="sxs-lookup"><span data-stu-id="44822-103">Create a format configuration for electronic reporting (ER)</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="44822-104">I följande steg förklaras hur en användare i rollen Systemadministratör eller Utvecklare för elektronisk rapportering kan skapa en formatkonfiguration för elektronisk rapportering (ER).</span><span class="sxs-lookup"><span data-stu-id="44822-104">The following steps explain how a user in the System Administrator or Electronic Reporting Developer role can create a format configuration for Electronic reporting (ER).</span></span> <span data-ttu-id="44822-105">Den här formatkonfiguration definierar formatet för elektroniska dokument som används för att bearbeta betalningar.</span><span class="sxs-lookup"><span data-stu-id="44822-105">This format configuration will define the format of electronic documents that are used for processing payments.</span></span> <span data-ttu-id="44822-106">I det här exemplet ska du skapa en konfigurering för exempelföretaget, Litware, Inc. För att slutföra dessa steg måste du först avsluta stegen i proceduren "Mappa modellen till utvalda datakällor".</span><span class="sxs-lookup"><span data-stu-id="44822-106">In this example, you will create a format configuration for sample company, Litware, Inc. To complete these steps, you must first complete the steps in the “Map model to selected datasources” procedure.</span></span>


## <a name="create-a-new-format-configuration"></a><span data-ttu-id="44822-107">Skapa en ny formatkonfiguration</span><span class="sxs-lookup"><span data-stu-id="44822-107">Create a new format configuration</span></span>
1. <span data-ttu-id="44822-108">Gå till Organisationsadministration > Arbetsytor > Elektronisk rapportering.</span><span class="sxs-lookup"><span data-stu-id="44822-108">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="44822-109">Klicka på Reporting configurations.</span><span class="sxs-lookup"><span data-stu-id="44822-109">Click Reporting configurations.</span></span>
3. <span data-ttu-id="44822-110">Välj "Betalningar (förenklad modell)" i trädet.</span><span class="sxs-lookup"><span data-stu-id="44822-110">In the tree, select 'Payments (simplified model)'.</span></span>
4. <span data-ttu-id="44822-111">Klicka på Skapa konfiguration om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="44822-111">Click Create configuration to open the drop dialog.</span></span>
5. <span data-ttu-id="44822-112">Ange "Format som baseras på datamodellen PaymentModel" i fältet Ny.</span><span class="sxs-lookup"><span data-stu-id="44822-112">In the New field, enter 'Format based on data model PaymentModel'.</span></span>
6. <span data-ttu-id="44822-113">Skriv "BACS (fiktivt UK) i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="44822-113">In the Name field, type 'BACS (UK fictitious)'.</span></span>
    * <span data-ttu-id="44822-114">BACS (fiktivt UK)</span><span class="sxs-lookup"><span data-stu-id="44822-114">BACS (UK fictitious)</span></span>  
7. <span data-ttu-id="44822-115">Skriv "BACS-leverantörsbetalningsformat (fiktivt UK)" i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="44822-115">In the Description field, type 'BACS vendor payment format (UK fictitious)'.</span></span>
    * <span data-ttu-id="44822-116">BACS-leverantörsbetalningsformat (fiktivt UK)</span><span class="sxs-lookup"><span data-stu-id="44822-116">BACS vendor payment format (UK fictitious)</span></span>  
    * <span data-ttu-id="44822-117">Den aktiva konfigurationsleverantören anges automatiskt här.</span><span class="sxs-lookup"><span data-stu-id="44822-117">The active configuration provider is automatically entered here.</span></span> <span data-ttu-id="44822-118">Den här leverantören kommer att kunna underhålla konfigurationen.</span><span class="sxs-lookup"><span data-stu-id="44822-118">This provider will be able to maintain this configuration.</span></span> <span data-ttu-id="44822-119">Andra leverantörer kan använda den här konfigurationen, men de kan inte underhålla den.</span><span class="sxs-lookup"><span data-stu-id="44822-119">Other providers can use this configuration, but will not be able to maintain it.</span></span>  
    * <span data-ttu-id="44822-120">Ett visst format för elektroniska dokument kan definieras.</span><span class="sxs-lookup"><span data-stu-id="44822-120">A particular format of electronic document can be defined.</span></span> <span data-ttu-id="44822-121">Lämna det här fältet tomt om du vill välja ett format vid körning.</span><span class="sxs-lookup"><span data-stu-id="44822-121">Leave this field blank if you want to select a format at run-time.</span></span>  
8. <span data-ttu-id="44822-122">Ange eller välj ett värde i fältet Data model definition.</span><span class="sxs-lookup"><span data-stu-id="44822-122">In the Data model definition field, enter or select a value.</span></span>
9. <span data-ttu-id="44822-123">Klicka på Skapa konfiguration.</span><span class="sxs-lookup"><span data-stu-id="44822-123">Click Create configuration.</span></span>
    * <span data-ttu-id="44822-124">En ny konfiguration har skapats.</span><span class="sxs-lookup"><span data-stu-id="44822-124">A new configuration has been created.</span></span> <span data-ttu-id="44822-125">Utkastversionen kan användas för att lagra designformatet för att hantera elektroniska dokument.</span><span class="sxs-lookup"><span data-stu-id="44822-125">The draft version can be used to store the design format for managing electronic documents.</span></span>  

## <a name="design-format-of-electronic-document"></a><span data-ttu-id="44822-126">Designa format för elektroniskt dokument</span><span class="sxs-lookup"><span data-stu-id="44822-126">Design format of electronic document</span></span>
1. <span data-ttu-id="44822-127">Klicka på Designer.</span><span class="sxs-lookup"><span data-stu-id="44822-127">Click Designer.</span></span>
2. <span data-ttu-id="44822-128">Klicka på Lägg till rot för att öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="44822-128">Click Add root to open the drop dialog.</span></span>
3. <span data-ttu-id="44822-129">Välj "Allmänt\Fil" i trädet.</span><span class="sxs-lookup"><span data-stu-id="44822-129">In the tree, select 'Common\File'.</span></span>
4. <span data-ttu-id="44822-130">Skriv "Xml" i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="44822-130">In the Name field, type 'Xml'.</span></span>
    * <span data-ttu-id="44822-131">Xml</span><span class="sxs-lookup"><span data-stu-id="44822-131">Xml</span></span>  
5. <span data-ttu-id="44822-132">Skriv "UTF 8" i fältet Kodning.</span><span class="sxs-lookup"><span data-stu-id="44822-132">In the Encoding field, type 'UTF-8'.</span></span>
    * <span data-ttu-id="44822-133">UTF-8</span><span class="sxs-lookup"><span data-stu-id="44822-133">UTF-8</span></span>  
6. <span data-ttu-id="44822-134">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="44822-134">Click OK.</span></span>
7. <span data-ttu-id="44822-135">Klicka på Lägg till för att öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="44822-135">Click Add to open the drop dialog.</span></span>
8. <span data-ttu-id="44822-136">Välj "XML\Element" i trädet.</span><span class="sxs-lookup"><span data-stu-id="44822-136">In the tree, select 'XML\Element'.</span></span>
9. <span data-ttu-id="44822-137">Skriv "Meddelande" i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="44822-137">In the Name field, type 'Message'.</span></span>
    * <span data-ttu-id="44822-138">Meddelande</span><span class="sxs-lookup"><span data-stu-id="44822-138">Message</span></span>  
10. <span data-ttu-id="44822-139">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="44822-139">Click OK.</span></span>
11. <span data-ttu-id="44822-140">Välj "Xml\Message" i trädet.</span><span class="sxs-lookup"><span data-stu-id="44822-140">In the tree, select 'Xml\Message'.</span></span>
12. <span data-ttu-id="44822-141">Klicka på Add Element.</span><span class="sxs-lookup"><span data-stu-id="44822-141">Click Add Element.</span></span>
13. <span data-ttu-id="44822-142">Skriv "ProcessingDate" i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="44822-142">In the Name field, type 'ProcessingDate'.</span></span>
    * <span data-ttu-id="44822-143">ProcessingDate</span><span class="sxs-lookup"><span data-stu-id="44822-143">ProcessingDate</span></span>  
14. <span data-ttu-id="44822-144">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="44822-144">Click OK.</span></span>
15. <span data-ttu-id="44822-145">Klicka på Add Element.</span><span class="sxs-lookup"><span data-stu-id="44822-145">Click Add Element.</span></span>
16. <span data-ttu-id="44822-146">Skriv "MessageId'" i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="44822-146">In the Name field, type 'MessageId'.</span></span>
    * <span data-ttu-id="44822-147">MessageId</span><span class="sxs-lookup"><span data-stu-id="44822-147">MessageId</span></span>  
17. <span data-ttu-id="44822-148">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="44822-148">Click OK.</span></span>
18. <span data-ttu-id="44822-149">Klicka på Add Element.</span><span class="sxs-lookup"><span data-stu-id="44822-149">Click Add Element.</span></span>
19. <span data-ttu-id="44822-150">Skriv "Betalningar" i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="44822-150">In the Name field, type 'Payments'.</span></span>
    * <span data-ttu-id="44822-151">Betalningar</span><span class="sxs-lookup"><span data-stu-id="44822-151">Payments</span></span>  
20. <span data-ttu-id="44822-152">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="44822-152">Click OK.</span></span>
21. <span data-ttu-id="44822-153">Välj "Xml\Message\Payments" i trädet.</span><span class="sxs-lookup"><span data-stu-id="44822-153">In the tree, select 'Xml\Message\Payments'.</span></span>
22. <span data-ttu-id="44822-154">Klicka på Add Element.</span><span class="sxs-lookup"><span data-stu-id="44822-154">Click Add Element.</span></span>
23. <span data-ttu-id="44822-155">Skriv "Artikel" i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="44822-155">In the Name field, type 'Item'.</span></span>
    * <span data-ttu-id="44822-156">Artikel</span><span class="sxs-lookup"><span data-stu-id="44822-156">Item</span></span>  
24. <span data-ttu-id="44822-157">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="44822-157">Click OK.</span></span>
25. <span data-ttu-id="44822-158">Välj "Xml\Message\Payments\Item" i trädet.</span><span class="sxs-lookup"><span data-stu-id="44822-158">In the tree, select 'Xml\Message\Payments\Item'.</span></span>
26. <span data-ttu-id="44822-159">Klicka på Lägg till för att öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="44822-159">Click Add to open the drop dialog.</span></span>
27. <span data-ttu-id="44822-160">Välj "XML\Attribut" i trädet.</span><span class="sxs-lookup"><span data-stu-id="44822-160">In the tree, select 'XML\Attribute'.</span></span>
28. <span data-ttu-id="44822-161">Skriv "Id" i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="44822-161">In the Name field, type 'Id'.</span></span>
    * <span data-ttu-id="44822-162">ID</span><span class="sxs-lookup"><span data-stu-id="44822-162">Id</span></span>  
29. <span data-ttu-id="44822-163">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="44822-163">Click OK.</span></span>
30. <span data-ttu-id="44822-164">Klicka på Lägg till för att öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="44822-164">Click Add to open the drop dialog.</span></span>
31. <span data-ttu-id="44822-165">Välj "XML\Element" i trädet.</span><span class="sxs-lookup"><span data-stu-id="44822-165">In the tree, select 'XML\Element'.</span></span>
32. <span data-ttu-id="44822-166">Skriv "Leverantör" i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="44822-166">In the Name field, type 'Vendor'.</span></span>
    * <span data-ttu-id="44822-167">Leverantör</span><span class="sxs-lookup"><span data-stu-id="44822-167">Vendor</span></span>  
33. <span data-ttu-id="44822-168">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="44822-168">Click OK.</span></span>
34. <span data-ttu-id="44822-169">Välj "Xml\Message\Payments\Item\Vendor" i trädet.</span><span class="sxs-lookup"><span data-stu-id="44822-169">In the tree, select 'Xml\Message\Payments\Item\Vendor'.</span></span>
35. <span data-ttu-id="44822-170">Klicka på Add Element.</span><span class="sxs-lookup"><span data-stu-id="44822-170">Click Add Element.</span></span>
36. <span data-ttu-id="44822-171">Skriv "Namn" i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="44822-171">In the Name field, type 'Name'.</span></span>
    * <span data-ttu-id="44822-172">Namn</span><span class="sxs-lookup"><span data-stu-id="44822-172">Name</span></span>  
37. <span data-ttu-id="44822-173">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="44822-173">Click OK.</span></span>
38. <span data-ttu-id="44822-174">Klicka på Add Element.</span><span class="sxs-lookup"><span data-stu-id="44822-174">Click Add Element.</span></span>
39. <span data-ttu-id="44822-175">Skriv "Bank" i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="44822-175">In the Name field, type 'Bank'.</span></span>
    * <span data-ttu-id="44822-176">Bank</span><span class="sxs-lookup"><span data-stu-id="44822-176">Bank</span></span>  
40. <span data-ttu-id="44822-177">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="44822-177">Click OK.</span></span>
41. <span data-ttu-id="44822-178">Välj "Xml\Message\Payments\Item\Vendor\Bank" i trädet.</span><span class="sxs-lookup"><span data-stu-id="44822-178">In the tree, select 'Xml\Message\Payments\Item\Vendor\Bank'.</span></span>
42. <span data-ttu-id="44822-179">Klicka på Add Element.</span><span class="sxs-lookup"><span data-stu-id="44822-179">Click Add Element.</span></span>
43. <span data-ttu-id="44822-180">Skriv "RoutingNumber" i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="44822-180">In the Name field, type 'RoutingNumber'.</span></span>
    * <span data-ttu-id="44822-181">RoutingNumber</span><span class="sxs-lookup"><span data-stu-id="44822-181">RoutingNumber</span></span>  
44. <span data-ttu-id="44822-182">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="44822-182">Click OK.</span></span>
45. <span data-ttu-id="44822-183">Klicka på Add Element.</span><span class="sxs-lookup"><span data-stu-id="44822-183">Click Add Element.</span></span>
46. <span data-ttu-id="44822-184">Skriv "AccountNumber" i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="44822-184">In the Name field, type 'AccountNumber'.</span></span>
    * <span data-ttu-id="44822-185">Kontonummer</span><span class="sxs-lookup"><span data-stu-id="44822-185">AccountNumber</span></span>  
47. <span data-ttu-id="44822-186">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="44822-186">Click OK.</span></span>
48. <span data-ttu-id="44822-187">Välj "Xml\Message\Payments\Item\Vendor" i trädet.</span><span class="sxs-lookup"><span data-stu-id="44822-187">In the tree, select 'Xml\Message\Payments\Item\Vendor'.</span></span>
49. <span data-ttu-id="44822-188">Klicka på Kopiera.</span><span class="sxs-lookup"><span data-stu-id="44822-188">Click Copy.</span></span>
50. <span data-ttu-id="44822-189">Välj "Xml\Message\Payments\Item" i trädet.</span><span class="sxs-lookup"><span data-stu-id="44822-189">In the tree, select 'Xml\Message\Payments\Item'.</span></span>
51. <span data-ttu-id="44822-190">Klicka på Paste.</span><span class="sxs-lookup"><span data-stu-id="44822-190">Click Paste.</span></span>
52. <span data-ttu-id="44822-191">Skriv "Betalare" i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="44822-191">In the Name field, type 'Payer'.</span></span>
    * <span data-ttu-id="44822-192">Betalare</span><span class="sxs-lookup"><span data-stu-id="44822-192">Payer</span></span>  
53. <span data-ttu-id="44822-193">Välj "Xml\Message\Payments\Item" i trädet.</span><span class="sxs-lookup"><span data-stu-id="44822-193">In the tree, select 'Xml\Message\Payments\Item'.</span></span>
54. <span data-ttu-id="44822-194">Klicka på Add Element.</span><span class="sxs-lookup"><span data-stu-id="44822-194">Click Add Element.</span></span>
55. <span data-ttu-id="44822-195">Skriv "Valuta" i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="44822-195">In the Name field, type 'Currency'.</span></span>
    * <span data-ttu-id="44822-196">Valuta</span><span class="sxs-lookup"><span data-stu-id="44822-196">Currency</span></span>  
56. <span data-ttu-id="44822-197">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="44822-197">Click OK.</span></span>
57. <span data-ttu-id="44822-198">Klicka på Add Element.</span><span class="sxs-lookup"><span data-stu-id="44822-198">Click Add Element.</span></span>
58. <span data-ttu-id="44822-199">Skriv "Beskrivning" i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="44822-199">In the Name field, type 'Description'.</span></span>
    * <span data-ttu-id="44822-200">beskrivning</span><span class="sxs-lookup"><span data-stu-id="44822-200">Description</span></span>  
59. <span data-ttu-id="44822-201">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="44822-201">Click OK.</span></span>
60. <span data-ttu-id="44822-202">Klicka på Add Element.</span><span class="sxs-lookup"><span data-stu-id="44822-202">Click Add Element.</span></span>
61. <span data-ttu-id="44822-203">Skriv "TransDate" i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="44822-203">In the Name field, type 'TransDate'.</span></span>
    * <span data-ttu-id="44822-204">TransDatum</span><span class="sxs-lookup"><span data-stu-id="44822-204">TransDate</span></span>  
62. <span data-ttu-id="44822-205">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="44822-205">Click OK.</span></span>
63. <span data-ttu-id="44822-206">Klicka på Add Element.</span><span class="sxs-lookup"><span data-stu-id="44822-206">Click Add Element.</span></span>
64. <span data-ttu-id="44822-207">Skriv "Belopp" i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="44822-207">In the Name field, type 'Amount'.</span></span>
    * <span data-ttu-id="44822-208">Tid</span><span class="sxs-lookup"><span data-stu-id="44822-208">Amount</span></span>  
65. <span data-ttu-id="44822-209">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="44822-209">Click OK.</span></span>

## <a name="prepare-format-components-for-mapping-to-data-model-elements"></a><span data-ttu-id="44822-210">Förbered formatkomponenter för att mappa till datamodellelement</span><span class="sxs-lookup"><span data-stu-id="44822-210">Prepare format components for mapping to data model elements</span></span>
1. <span data-ttu-id="44822-211">Välj "Xml\Message\ProcessingDate" i trädet.</span><span class="sxs-lookup"><span data-stu-id="44822-211">In the tree, select 'Xml\Message\ProcessingDate'.</span></span>
2. <span data-ttu-id="44822-212">Klicka på Lägg till för att öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="44822-212">Click Add to open the drop dialog.</span></span>
3. <span data-ttu-id="44822-213">Välj "Text\DateTime" i trädet.</span><span class="sxs-lookup"><span data-stu-id="44822-213">In the tree, select 'Text\DateTime'.</span></span>
4. <span data-ttu-id="44822-214">Skriv "åååå-MM-dd" i fältet Format.</span><span class="sxs-lookup"><span data-stu-id="44822-214">In the Format field, type 'yyyy-MM-dd'.</span></span>
    * <span data-ttu-id="44822-215">åååå/mm/dd</span><span class="sxs-lookup"><span data-stu-id="44822-215">yyyy-MM-dd</span></span>  
5. <span data-ttu-id="44822-216">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="44822-216">Click OK.</span></span>
6. <span data-ttu-id="44822-217">Välj "Xml\Message\Payments\Item\TransDate" i trädet.</span><span class="sxs-lookup"><span data-stu-id="44822-217">In the tree, select 'Xml\Message\Payments\Item\TransDate'.</span></span>
7. <span data-ttu-id="44822-218">Klicka på Lägg till DateTime.</span><span class="sxs-lookup"><span data-stu-id="44822-218">Click Add DateTime.</span></span>
8. <span data-ttu-id="44822-219">Skriv "åååå-MM-dd" i fältet Format.</span><span class="sxs-lookup"><span data-stu-id="44822-219">In the Format field, type 'yyyy-MM-dd'.</span></span>
    * <span data-ttu-id="44822-220">åååå/mm/dd</span><span class="sxs-lookup"><span data-stu-id="44822-220">yyyy-MM-dd</span></span>  
9. <span data-ttu-id="44822-221">Välj "Datum" i fältet DateTime-typ</span><span class="sxs-lookup"><span data-stu-id="44822-221">In the DateTime type field, select 'Date'.</span></span>
10. <span data-ttu-id="44822-222">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="44822-222">Click OK.</span></span>
11. <span data-ttu-id="44822-223">Välj "Xml\Message\MessageId" i trädet.</span><span class="sxs-lookup"><span data-stu-id="44822-223">In the tree, select 'Xml\Message\MessageId'.</span></span>
12. <span data-ttu-id="44822-224">Klicka på Lägg till för att öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="44822-224">Click Add to open the drop dialog.</span></span>
13. <span data-ttu-id="44822-225">Välj "Text\Sträng" i trädet.</span><span class="sxs-lookup"><span data-stu-id="44822-225">In the tree, select 'Text\String'.</span></span>
14. <span data-ttu-id="44822-226">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="44822-226">Click OK.</span></span>
15. <span data-ttu-id="44822-227">Välj "Xml\Message\Payments\Item\Vendor\Name" i trädet.</span><span class="sxs-lookup"><span data-stu-id="44822-227">In the tree, select 'Xml\Message\Payments\Item\Vendor\Name'.</span></span>
16. <span data-ttu-id="44822-228">Klicka på Add string.</span><span class="sxs-lookup"><span data-stu-id="44822-228">Click Add String.</span></span>
17. <span data-ttu-id="44822-229">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="44822-229">Click OK.</span></span>
18. <span data-ttu-id="44822-230">Välj "Xml\Message\Payments\Item\Vendor\Bank\RoutingNumber" i trädet.</span><span class="sxs-lookup"><span data-stu-id="44822-230">In the tree, select 'Xml\Message\Payments\Item\Vendor\Bank\RoutingNumber'.</span></span>
19. <span data-ttu-id="44822-231">Klicka på Add string.</span><span class="sxs-lookup"><span data-stu-id="44822-231">Click Add String.</span></span>
20. <span data-ttu-id="44822-232">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="44822-232">Click OK.</span></span>
21. <span data-ttu-id="44822-233">Välj "Xml\Message\Payments\Item\Vendor\Bank\AccountNumber" i trädet.</span><span class="sxs-lookup"><span data-stu-id="44822-233">In the tree, select 'Xml\Message\Payments\Item\Vendor\Bank\AccountNumber'.</span></span>
22. <span data-ttu-id="44822-234">Klicka på Add string.</span><span class="sxs-lookup"><span data-stu-id="44822-234">Click Add String.</span></span>
23. <span data-ttu-id="44822-235">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="44822-235">Click OK.</span></span>
24. <span data-ttu-id="44822-236">Välj "Xml\Message\Payments\Item\Payer\Name" i trädet.</span><span class="sxs-lookup"><span data-stu-id="44822-236">In the tree, select 'Xml\Message\Payments\Item\Payer\Name'.</span></span>
25. <span data-ttu-id="44822-237">Klicka på Add string.</span><span class="sxs-lookup"><span data-stu-id="44822-237">Click Add String.</span></span>
26. <span data-ttu-id="44822-238">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="44822-238">Click OK.</span></span>
27. <span data-ttu-id="44822-239">Välj "Xml\Message\Payments\Item\Payer\Bank\RoutingNumber" i trädet.</span><span class="sxs-lookup"><span data-stu-id="44822-239">In the tree, select 'Xml\Message\Payments\Item\Payer\Bank\RoutingNumber'.</span></span>
28. <span data-ttu-id="44822-240">Klicka på Add string.</span><span class="sxs-lookup"><span data-stu-id="44822-240">Click Add String.</span></span>
29. <span data-ttu-id="44822-241">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="44822-241">Click OK.</span></span>
30. <span data-ttu-id="44822-242">I trädet väljer du "Xml\Message\Payments\Item\Payer\Bank\AccountNumber".</span><span class="sxs-lookup"><span data-stu-id="44822-242">In the tree, select 'Xml\Message\Payments\Item\Payer\Bank\AccountNumber'.</span></span>
31. <span data-ttu-id="44822-243">Klicka på Add string.</span><span class="sxs-lookup"><span data-stu-id="44822-243">Click Add String.</span></span>
32. <span data-ttu-id="44822-244">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="44822-244">Click OK.</span></span>
33. <span data-ttu-id="44822-245">I trädet väljer du "Xml\Message\Payments\Item\Currency".</span><span class="sxs-lookup"><span data-stu-id="44822-245">In the tree, select 'Xml\Message\Payments\Item\Currency'.</span></span>
34. <span data-ttu-id="44822-246">Klicka på Add string.</span><span class="sxs-lookup"><span data-stu-id="44822-246">Click Add String.</span></span>
35. <span data-ttu-id="44822-247">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="44822-247">Click OK.</span></span>
36. <span data-ttu-id="44822-248">I trädet väljer du "Xml\Message\Payments\Item\Description".</span><span class="sxs-lookup"><span data-stu-id="44822-248">In the tree, select 'Xml\Message\Payments\Item\Description'.</span></span>
37. <span data-ttu-id="44822-249">Klicka på Add string.</span><span class="sxs-lookup"><span data-stu-id="44822-249">Click Add String.</span></span>
38. <span data-ttu-id="44822-250">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="44822-250">Click OK.</span></span>
39. <span data-ttu-id="44822-251">I trädet väljer du "Xml\Message\Payments\Item\Amount".</span><span class="sxs-lookup"><span data-stu-id="44822-251">In the tree, select 'Xml\Message\Payments\Item\Amount'.</span></span>
40. <span data-ttu-id="44822-252">Klicka på Add string.</span><span class="sxs-lookup"><span data-stu-id="44822-252">Click Add String.</span></span>
41. <span data-ttu-id="44822-253">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="44822-253">Click OK.</span></span>
42. <span data-ttu-id="44822-254">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="44822-254">Click Save.</span></span>
43. <span data-ttu-id="44822-255">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="44822-255">Close the page.</span></span>


