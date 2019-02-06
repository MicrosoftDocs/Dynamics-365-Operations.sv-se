--- 
title: ER Skapa en formatkonfiguration (november 2016)
description: "I följande steg förklaras hur en användare i rollen Systemadministratör eller Utvecklare för elektronisk rapportering kan skapa en formatkonfiguration för elektronisk rapportering (ER)."
author: NickSelin
manager: AnnBe
ms.date: 11/27/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ERWorkspace, ERSolutionTable, ERSolutionCreateDropDialog, EROperationDesigner, ERComponentTypeDropDialog
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f004451a260b5be6c15c3975cd9e63ba9c1a7a2e
ms.openlocfilehash: 6fa5023a29c95ab9f10d8aacd51edc1a06c3c152
ms.contentlocale: sv-se
ms.lasthandoff: 02/06/2019

---
# <a name="er-create-a-format-configuration-november-2016"></a><span data-ttu-id="ae56d-103">ER Skapa en formatkonfiguration (november 2016)</span><span class="sxs-lookup"><span data-stu-id="ae56d-103">ER Create a format configuration (November 2016)</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="ae56d-104">I följande steg förklaras hur en användare i rollen Systemadministratör eller Utvecklare för elektronisk rapportering kan skapa en formatkonfiguration för elektronisk rapportering (ER).</span><span class="sxs-lookup"><span data-stu-id="ae56d-104">The following steps explain how a user in the System Administrator or Electronic Reporting Developer role can create a format configuration for Electronic reporting (ER).</span></span> <span data-ttu-id="ae56d-105">Den här formatkonfiguration definierar formatet för elektroniska dokument som används för att bearbeta betalningar.</span><span class="sxs-lookup"><span data-stu-id="ae56d-105">This format configuration will define the format of electronic documents that are used for processing payments.</span></span> <span data-ttu-id="ae56d-106">I det här exemplet ska du skapa en konfigurering för exempelföretaget, Litware, Inc. För att slutföra dessa steg måste du först avsluta stegen i proceduren "Mappa modellen till utvalda datakällor".</span><span class="sxs-lookup"><span data-stu-id="ae56d-106">In this example, you will create a format configuration for sample company, Litware, Inc. To complete these steps, you must first complete the steps in the “Map model to selected datasources” procedure.</span></span>


## <a name="create-a-new-format-configuration"></a><span data-ttu-id="ae56d-107">Skapa en ny formatkonfiguration</span><span class="sxs-lookup"><span data-stu-id="ae56d-107">Create a new format configuration</span></span>
1. <span data-ttu-id="ae56d-108">Gå till **Organisationsadministration > Arbetsytor > Elektronisk rapportering**.</span><span class="sxs-lookup"><span data-stu-id="ae56d-108">Go to **Organization administration > Workspaces > Electronic reporting**.</span></span>
2. <span data-ttu-id="ae56d-109">Klicka på **Rapporteringskonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="ae56d-109">Click **Reporting configurations**.</span></span>
3. <span data-ttu-id="ae56d-110">I trädet väljer du **Betalningar (förenklad modell)**.</span><span class="sxs-lookup"><span data-stu-id="ae56d-110">In the tree, select **Payments (simplified model)**.</span></span>
4. <span data-ttu-id="ae56d-111">Klicka på **Skapa konfiguration** om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="ae56d-111">Click **Create configuration** to open the drop dialog.</span></span>

 > [!NOTE]
 > <span data-ttu-id="ae56d-112">Om du inte ser **Skapa konfiguration** måste du aktivera designläge på sidan **Elektronisk rapportering parametrar**.</span><span class="sxs-lookup"><span data-stu-id="ae56d-112">If you don't see **Create configuration**, you must enable design mode on the **Electronic reporting parameters** page.</span></span> 
 
5. <span data-ttu-id="ae56d-113">I fältet **Nytt** anger du **Format som baseras på datamodellen PaymentModel**.</span><span class="sxs-lookup"><span data-stu-id="ae56d-113">In the **New** field, enter **Format based on data model PaymentModel**.</span></span>
6. <span data-ttu-id="ae56d-114">I fältet **Namn**, ange **BACS (fiktivt UK)**.</span><span class="sxs-lookup"><span data-stu-id="ae56d-114">In the **Name** field, type **BACS (UK fictitious)**.</span></span>
7. <span data-ttu-id="ae56d-115">I fältet **Beskrivning** ange **BACS-leverantörsbetalningsformat (fiktivt UK)**.</span><span class="sxs-lookup"><span data-stu-id="ae56d-115">In the **Description** field, type **BACS vendor payment format (UK fictitious)**.</span></span>
    * <span data-ttu-id="ae56d-116">Den aktiva konfigurationsleverantören anges automatiskt här.</span><span class="sxs-lookup"><span data-stu-id="ae56d-116">The active configuration provider is automatically entered here.</span></span> <span data-ttu-id="ae56d-117">Den här leverantören kommer att kunna underhålla konfigurationen.</span><span class="sxs-lookup"><span data-stu-id="ae56d-117">This provider will be able to maintain this configuration.</span></span> <span data-ttu-id="ae56d-118">Andra leverantörer kan använda den här konfigurationen, men de kan inte underhålla den.</span><span class="sxs-lookup"><span data-stu-id="ae56d-118">Other providers can use this configuration, but will not be able to maintain it.</span></span>  
    * <span data-ttu-id="ae56d-119">Ett visst format för elektroniska dokument kan definieras.</span><span class="sxs-lookup"><span data-stu-id="ae56d-119">A particular format of electronic document can be defined.</span></span> <span data-ttu-id="ae56d-120">Lämna det här fältet tomt om du vill välja ett format vid körning.</span><span class="sxs-lookup"><span data-stu-id="ae56d-120">Leave this field blank if you want to select a format at run-time.</span></span>  
8. <span data-ttu-id="ae56d-121">I fältet **Definition av datamodell** ange eller välj ett värde.</span><span class="sxs-lookup"><span data-stu-id="ae56d-121">In the **Data model definition** field, enter or select a value.</span></span>
9. <span data-ttu-id="ae56d-122">Klicka på **Skapa konfiguration**.</span><span class="sxs-lookup"><span data-stu-id="ae56d-122">Click **Create configuration**.</span></span> <span data-ttu-id="ae56d-123">En ny konfiguration har skapats.</span><span class="sxs-lookup"><span data-stu-id="ae56d-123">A new configuration has been created.</span></span> <span data-ttu-id="ae56d-124">Utkastversionen kan användas för att lagra designformatet för att hantera elektroniska dokument.</span><span class="sxs-lookup"><span data-stu-id="ae56d-124">The draft version can be used to store the design format for managing electronic documents.</span></span>  

 > [!NOTE]
 > <span data-ttu-id="ae56d-125">Om du inte ser **Skapa konfiguration** måste du aktivera designläge på sidan **Elektronisk rapportering parametrar**.</span><span class="sxs-lookup"><span data-stu-id="ae56d-125">If you don't see **Create configuration**, you must enable design mode on the **Electronic reporting parameters** page.</span></span>


## <a name="design-the-format-of-an-electronic-document"></a><span data-ttu-id="ae56d-126">Designa formatet för ett elektroniskt dokument</span><span class="sxs-lookup"><span data-stu-id="ae56d-126">Design the format of an electronic document</span></span>
1. <span data-ttu-id="ae56d-127">Klicka på **Designer**.</span><span class="sxs-lookup"><span data-stu-id="ae56d-127">Click **Designer**.</span></span>
2. <span data-ttu-id="ae56d-128">Klicka på **Lägg till rot** för att öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="ae56d-128">Click **Add root** to open the drop dialog.</span></span>
3. <span data-ttu-id="ae56d-129">I trädet, välj **Allmänt\Fil**.</span><span class="sxs-lookup"><span data-stu-id="ae56d-129">In the tree, select **Common\File**.</span></span>
4. <span data-ttu-id="ae56d-130">I fältet **Namn** ange **Xml**.</span><span class="sxs-lookup"><span data-stu-id="ae56d-130">In the **Name** field, type **Xml**.</span></span>
5. <span data-ttu-id="ae56d-131">I fältet **Kodning** ange **UTF-8**.</span><span class="sxs-lookup"><span data-stu-id="ae56d-131">In the **Encoding** field, type **UTF-8**.</span></span>
6. <span data-ttu-id="ae56d-132">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="ae56d-132">Click **OK**.</span></span>
7. <span data-ttu-id="ae56d-133">Klicka på **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="ae56d-133">Click **Add**.</span></span>
8. <span data-ttu-id="ae56d-134">I trädet, välj **XML\Element**.</span><span class="sxs-lookup"><span data-stu-id="ae56d-134">In the tree, select **XML\Element**.</span></span>
9. <span data-ttu-id="ae56d-135">I fältet **Namn** ange **Meddelande**.</span><span class="sxs-lookup"><span data-stu-id="ae56d-135">In the **Name** field, type **Message**.</span></span>
10. <span data-ttu-id="ae56d-136">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="ae56d-136">Click **OK**.</span></span>
11. <span data-ttu-id="ae56d-137">I fältet träd ange **Xml\Message**.</span><span class="sxs-lookup"><span data-stu-id="ae56d-137">In the tree, select **Xml\Message**.</span></span>
12. <span data-ttu-id="ae56d-138">Klicka på **Lägg till element**.</span><span class="sxs-lookup"><span data-stu-id="ae56d-138">Click **Add Element**.</span></span>
13. <span data-ttu-id="ae56d-139">I fältet **Namn** ange **ProcessingDate**.</span><span class="sxs-lookup"><span data-stu-id="ae56d-139">In the **Name** field, type **ProcessingDate**.</span></span>
14. <span data-ttu-id="ae56d-140">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="ae56d-140">Click **OK**.</span></span>
15. <span data-ttu-id="ae56d-141">Klicka på **Lägg till element**.</span><span class="sxs-lookup"><span data-stu-id="ae56d-141">Click **Add Element**.</span></span>
16. <span data-ttu-id="ae56d-142">I fältet Namne ange **MessageId**.</span><span class="sxs-lookup"><span data-stu-id="ae56d-142">In the Name field, type **MessageId**.</span></span>
17. <span data-ttu-id="ae56d-143">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="ae56d-143">Click **OK**.</span></span>
18. <span data-ttu-id="ae56d-144">Klicka på **Lägg till element**.</span><span class="sxs-lookup"><span data-stu-id="ae56d-144">Click **Add Element**.</span></span>
19. <span data-ttu-id="ae56d-145">I fältet **Namn** ange **Betalningar**.</span><span class="sxs-lookup"><span data-stu-id="ae56d-145">In the **Name** field, type **Payments**.</span></span>
20. <span data-ttu-id="ae56d-146">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="ae56d-146">Click **OK**.</span></span>
21. <span data-ttu-id="ae56d-147">I trädet, välj **Xml\Message\Payments**.</span><span class="sxs-lookup"><span data-stu-id="ae56d-147">In the tree, select **Xml\Message\Payments**.</span></span>
22. <span data-ttu-id="ae56d-148">Klicka på **Lägg till element**.</span><span class="sxs-lookup"><span data-stu-id="ae56d-148">Click **Add Element**.</span></span>
23. <span data-ttu-id="ae56d-149">I fältet **Namn** ange **Artikel**.</span><span class="sxs-lookup"><span data-stu-id="ae56d-149">In the **Name** field, type **Item**.</span></span>
24. <span data-ttu-id="ae56d-150">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="ae56d-150">Click **OK**.</span></span>
25. <span data-ttu-id="ae56d-151">I trädet välj **Xml\Message\Payments\Item**.</span><span class="sxs-lookup"><span data-stu-id="ae56d-151">In the tree, select **Xml\Message\Payments\Item**.</span></span>
26. <span data-ttu-id="ae56d-152">Klicka på **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="ae56d-152">Click **Add**.</span></span>
27. <span data-ttu-id="ae56d-153">I trädet välj **XML\Attribute**.</span><span class="sxs-lookup"><span data-stu-id="ae56d-153">In the tree, select **XML\Attribute**.</span></span>
28. <span data-ttu-id="ae56d-154">I fältet Namn, ange **Id**.</span><span class="sxs-lookup"><span data-stu-id="ae56d-154">In the Name field, type **Id**.</span></span>
29. <span data-ttu-id="ae56d-155">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="ae56d-155">Click **OK**.</span></span>
30. <span data-ttu-id="ae56d-156">Klicka på **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="ae56d-156">Click **Add**.</span></span>
31. <span data-ttu-id="ae56d-157">I trädet, välj **XML\Element**.</span><span class="sxs-lookup"><span data-stu-id="ae56d-157">In the tree, select **XML\Element**.</span></span>
32. <span data-ttu-id="ae56d-158">I fältet Namn, ange **Leverantör**.</span><span class="sxs-lookup"><span data-stu-id="ae56d-158">In the Name field, type **Vendor**.</span></span>
33. <span data-ttu-id="ae56d-159">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="ae56d-159">Click **OK**.</span></span>
34. <span data-ttu-id="ae56d-160">I trädet välj **Xml\Message\Payments\Item\Vendor**.</span><span class="sxs-lookup"><span data-stu-id="ae56d-160">In the tree, select **Xml\Message\Payments\Item\Vendor**.</span></span>
35. <span data-ttu-id="ae56d-161">Klicka på **Lägg till element**.</span><span class="sxs-lookup"><span data-stu-id="ae56d-161">Click **Add Element**.</span></span>
36. <span data-ttu-id="ae56d-162">I fältet Namn, ange **Namn**.</span><span class="sxs-lookup"><span data-stu-id="ae56d-162">In the Name field, type **Name**.</span></span>
37. <span data-ttu-id="ae56d-163">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="ae56d-163">Click **OK**.</span></span>
38. <span data-ttu-id="ae56d-164">Klicka på **Lägg till element**.</span><span class="sxs-lookup"><span data-stu-id="ae56d-164">Click **Add Element**.</span></span>
39. <span data-ttu-id="ae56d-165">I fältet **Namn** ange **Bank**.</span><span class="sxs-lookup"><span data-stu-id="ae56d-165">In the **Name** field, type **Bank**.</span></span>
40. <span data-ttu-id="ae56d-166">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="ae56d-166">Click **OK**.</span></span>
41. <span data-ttu-id="ae56d-167">I trädet ange **Xml\Message\Payments\Item\Vendor\Bank**.</span><span class="sxs-lookup"><span data-stu-id="ae56d-167">In the tree, select **Xml\Message\Payments\Item\Vendor\Bank**.</span></span>
42. <span data-ttu-id="ae56d-168">Klicka på **Lägg till element**.</span><span class="sxs-lookup"><span data-stu-id="ae56d-168">Click **Add Element**.</span></span>
43. <span data-ttu-id="ae56d-169">I fältet **Namn** ange **RoutingNumber**.</span><span class="sxs-lookup"><span data-stu-id="ae56d-169">In the **Name** field, type **RoutingNumber**.</span></span>
44. <span data-ttu-id="ae56d-170">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="ae56d-170">Click **OK**.</span></span>
45. <span data-ttu-id="ae56d-171">Klicka på **Lägg till element**.</span><span class="sxs-lookup"><span data-stu-id="ae56d-171">Click **Add Element**.</span></span>
46. <span data-ttu-id="ae56d-172">I fältet **Namn** ange **AccountNumber**.</span><span class="sxs-lookup"><span data-stu-id="ae56d-172">In the **Name** field, type **AccountNumber**.</span></span>
47. <span data-ttu-id="ae56d-173">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="ae56d-173">Click **OK**.</span></span>
48. <span data-ttu-id="ae56d-174">I trädet välj **Xml\Message\Payments\Item\Vendor**.</span><span class="sxs-lookup"><span data-stu-id="ae56d-174">In the tree, select **Xml\Message\Payments\Item\Vendor**.</span></span>
49. <span data-ttu-id="ae56d-175">Klicka på **Kopiera**.</span><span class="sxs-lookup"><span data-stu-id="ae56d-175">Click **Copy**.</span></span>
50. <span data-ttu-id="ae56d-176">I trädet välj **Xml\Message\Payments\Item**.</span><span class="sxs-lookup"><span data-stu-id="ae56d-176">In the tree, select **Xml\Message\Payments\Item**.</span></span>
51. <span data-ttu-id="ae56d-177">Klicka på **Klistra in**.</span><span class="sxs-lookup"><span data-stu-id="ae56d-177">Click **Paste**.</span></span>
52. <span data-ttu-id="ae56d-178">I fältet **Namn** ange **Betalare**.</span><span class="sxs-lookup"><span data-stu-id="ae56d-178">In the **Name** field, type **Payer**.</span></span>
53. <span data-ttu-id="ae56d-179">I trädet välj **Xml\Message\Payments\Item**.</span><span class="sxs-lookup"><span data-stu-id="ae56d-179">In the tree, select **Xml\Message\Payments\Item**.</span></span>
54. <span data-ttu-id="ae56d-180">Klicka på **Lägg till element**.</span><span class="sxs-lookup"><span data-stu-id="ae56d-180">Click **Add Element**.</span></span>
55. <span data-ttu-id="ae56d-181">I fältet **Namn** ange **Valuta**.</span><span class="sxs-lookup"><span data-stu-id="ae56d-181">In the **Name** field, type **Currency**.</span></span>
56. <span data-ttu-id="ae56d-182">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="ae56d-182">Click **OK**.</span></span>
57. <span data-ttu-id="ae56d-183">Klicka på **Lägg till element**.</span><span class="sxs-lookup"><span data-stu-id="ae56d-183">Click **Add Element**.</span></span>
58. <span data-ttu-id="ae56d-184">I fältet **Namn** ange **Beskrivning**.</span><span class="sxs-lookup"><span data-stu-id="ae56d-184">In the **Name** field, type **Description**.</span></span>
59. <span data-ttu-id="ae56d-185">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="ae56d-185">Click **OK**.</span></span>
60. <span data-ttu-id="ae56d-186">Klicka på **Lägg till element**.</span><span class="sxs-lookup"><span data-stu-id="ae56d-186">Click **Add Element**.</span></span>
61. <span data-ttu-id="ae56d-187">I fältet Nman ange **TransDate**.</span><span class="sxs-lookup"><span data-stu-id="ae56d-187">In the Name field, type **TransDate**.</span></span>
62. <span data-ttu-id="ae56d-188">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="ae56d-188">Click **OK**.</span></span>
63. <span data-ttu-id="ae56d-189">Klicka på **Lägg till element**.</span><span class="sxs-lookup"><span data-stu-id="ae56d-189">Click **Add Element**.</span></span>
64. <span data-ttu-id="ae56d-190">I fältet Namn ange **Belopp**.</span><span class="sxs-lookup"><span data-stu-id="ae56d-190">In the Name field, type **Amount**.</span></span>
65. <span data-ttu-id="ae56d-191">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="ae56d-191">Click **OK**.</span></span>

## <a name="prepare-format-components-for-mapping-to-data-model-elements"></a><span data-ttu-id="ae56d-192">Förbered formatkomponenter för att mappa till datamodellelement</span><span class="sxs-lookup"><span data-stu-id="ae56d-192">Prepare format components for mapping to data model elements</span></span>
1. <span data-ttu-id="ae56d-193">I trädet ange **Xml\Message\ProcessingDate**.</span><span class="sxs-lookup"><span data-stu-id="ae56d-193">In the tree, select **Xml\Message\ProcessingDate**.</span></span>
2. <span data-ttu-id="ae56d-194">Klicka på **Lägg till** för att öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="ae56d-194">Click **Add** to open the drop dialog.</span></span>
3. <span data-ttu-id="ae56d-195">I trädet välj **Text\DateTime**.</span><span class="sxs-lookup"><span data-stu-id="ae56d-195">In the tree, select **Text\DateTime**.</span></span>
4. <span data-ttu-id="ae56d-196">I fältet **Format** ange **åååå-MM-dd**.</span><span class="sxs-lookup"><span data-stu-id="ae56d-196">In the **Format** field, type **yyyy-MM-dd**.</span></span>
5. <span data-ttu-id="ae56d-197">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="ae56d-197">Click **OK**.</span></span>
6. <span data-ttu-id="ae56d-198">I trädet ange **Xml\Message\Payments\Item\TransDate**.</span><span class="sxs-lookup"><span data-stu-id="ae56d-198">In the tree, select **Xml\Message\Payments\Item\TransDate**.</span></span>
7. <span data-ttu-id="ae56d-199">Klicka på **Lägg till DateTime**.</span><span class="sxs-lookup"><span data-stu-id="ae56d-199">Click **Add DateTime**.</span></span>
8. <span data-ttu-id="ae56d-200">I fältet **Format** ange **åååå-MM-dd**.</span><span class="sxs-lookup"><span data-stu-id="ae56d-200">In the **Format** field, type **yyyy-MM-dd**.</span></span>
9. <span data-ttu-id="ae56d-201">I fältet **DateTime** ange **Datum**.</span><span class="sxs-lookup"><span data-stu-id="ae56d-201">In the **DateTime** type field, select **Date**.</span></span>
10. <span data-ttu-id="ae56d-202">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="ae56d-202">Click **OK**.</span></span>
11. <span data-ttu-id="ae56d-203">I trädet ange **Xml\Message\MessageId**.</span><span class="sxs-lookup"><span data-stu-id="ae56d-203">In the tree, select **Xml\Message\MessageId**.</span></span>
12. <span data-ttu-id="ae56d-204">Klicka på **Lägg till** för att öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="ae56d-204">Click **Add** to open the drop dialog.</span></span>
13. <span data-ttu-id="ae56d-205">I trädet ange **Text\String**.</span><span class="sxs-lookup"><span data-stu-id="ae56d-205">In the tree, select **Text\String**.</span></span>
14. <span data-ttu-id="ae56d-206">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="ae56d-206">Click **OK**.</span></span>
15. <span data-ttu-id="ae56d-207">I trädet ange **Xml\Message\Payments\Item\Vendor\Name**.</span><span class="sxs-lookup"><span data-stu-id="ae56d-207">In the tree, select **Xml\Message\Payments\Item\Vendor\Name**.</span></span>
16. <span data-ttu-id="ae56d-208">Klicka på **Lägg till sträng**.</span><span class="sxs-lookup"><span data-stu-id="ae56d-208">Click **Add String**.</span></span>
17. <span data-ttu-id="ae56d-209">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="ae56d-209">Click **OK**.</span></span>
18. <span data-ttu-id="ae56d-210">I trädet välj **Xml\Message\Payments\Item\Vendor\Bank\RoutingNumber**.</span><span class="sxs-lookup"><span data-stu-id="ae56d-210">In the tree, select **Xml\Message\Payments\Item\Vendor\Bank\RoutingNumber**.</span></span>
19. <span data-ttu-id="ae56d-211">Klicka på **Lägg till sträng**.</span><span class="sxs-lookup"><span data-stu-id="ae56d-211">Click **Add String**.</span></span>
20. <span data-ttu-id="ae56d-212">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="ae56d-212">Click **OK**.</span></span>
21. <span data-ttu-id="ae56d-213">I trädet välj **Xml\Message\Payments\Item\Vendor\Bank\AccountNumber**.</span><span class="sxs-lookup"><span data-stu-id="ae56d-213">In the tree, select **Xml\Message\Payments\Item\Vendor\Bank\AccountNumber**.</span></span>
22. <span data-ttu-id="ae56d-214">Klicka på **Lägg till sträng**.</span><span class="sxs-lookup"><span data-stu-id="ae56d-214">Click **Add String**.</span></span>
23. <span data-ttu-id="ae56d-215">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="ae56d-215">Click **OK**.</span></span>
24. <span data-ttu-id="ae56d-216">I trädet välj **Xml\Message\Payments\Item\Payer\Name**.</span><span class="sxs-lookup"><span data-stu-id="ae56d-216">In the tree, select **Xml\Message\Payments\Item\Payer\Name**.</span></span>
25. <span data-ttu-id="ae56d-217">Klicka på **Lägg till sträng**.</span><span class="sxs-lookup"><span data-stu-id="ae56d-217">Click **Add String**.</span></span>
26. <span data-ttu-id="ae56d-218">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="ae56d-218">Click **OK**.</span></span>
27. <span data-ttu-id="ae56d-219">I trädet välj **Xml\Message\Payments\Item\Payer\Bank\RoutingNumber**.</span><span class="sxs-lookup"><span data-stu-id="ae56d-219">In the tree, select **Xml\Message\Payments\Item\Payer\Bank\RoutingNumber**.</span></span>
28. <span data-ttu-id="ae56d-220">Klicka på **Lägg till sträng**.</span><span class="sxs-lookup"><span data-stu-id="ae56d-220">Click **Add String**.</span></span>
29. <span data-ttu-id="ae56d-221">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="ae56d-221">Click **OK**.</span></span>
30. <span data-ttu-id="ae56d-222">I trädet välj **Xml\Message\Payments\Item\Payer\Bank\AccountNumber**.</span><span class="sxs-lookup"><span data-stu-id="ae56d-222">In the tree, select **Xml\Message\Payments\Item\Payer\Bank\AccountNumber**.</span></span>
31. <span data-ttu-id="ae56d-223">Klicka på **Lägg till sträng**.</span><span class="sxs-lookup"><span data-stu-id="ae56d-223">Click **Add String**.</span></span>
32. <span data-ttu-id="ae56d-224">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="ae56d-224">Click **OK**.</span></span>
33. <span data-ttu-id="ae56d-225">I trädet välj **Xml\Message\Payments\Item\Currency**.</span><span class="sxs-lookup"><span data-stu-id="ae56d-225">In the tree, select **Xml\Message\Payments\Item\Currency**.</span></span>
34. <span data-ttu-id="ae56d-226">Klicka på **Lägg till sträng**.</span><span class="sxs-lookup"><span data-stu-id="ae56d-226">Click **Add String**.</span></span>
35. <span data-ttu-id="ae56d-227">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="ae56d-227">Click **OK**.</span></span>
36. <span data-ttu-id="ae56d-228">I trädet välj **Xml\Message\Payments\Item\Description**.</span><span class="sxs-lookup"><span data-stu-id="ae56d-228">In the tree, select **Xml\Message\Payments\Item\Description**.</span></span>
37. <span data-ttu-id="ae56d-229">Klicka på **Lägg till sträng**.</span><span class="sxs-lookup"><span data-stu-id="ae56d-229">Click **Add String**.</span></span>
38. <span data-ttu-id="ae56d-230">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="ae56d-230">Click **OK**.</span></span>
39. <span data-ttu-id="ae56d-231">I trädet välj **Xml\Message\Payments\Item\Amount**.</span><span class="sxs-lookup"><span data-stu-id="ae56d-231">In the tree, select **Xml\Message\Payments\Item\Amount**.</span></span>
40. <span data-ttu-id="ae56d-232">Klicka på **Lägg till sträng**.</span><span class="sxs-lookup"><span data-stu-id="ae56d-232">Click **Add String**.</span></span>
41. <span data-ttu-id="ae56d-233">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="ae56d-233">Click **OK**.</span></span>
42. <span data-ttu-id="ae56d-234">Klicka på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="ae56d-234">Click **Save**.</span></span>
43. <span data-ttu-id="ae56d-235">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="ae56d-235">Close the page.</span></span>


