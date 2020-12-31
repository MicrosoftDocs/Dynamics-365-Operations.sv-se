---
title: ER Skapa en formatkonfiguration (november 2016)
description: Det här avsnittet förklarar hur en användare i rollen Systemadministratör eller Utvecklare för elektronisk rapportering kan skapa en formatkonfiguration för elektronisk rapportering (ER).
author: NickSelin
manager: AnnBe
ms.date: 08/02/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, ERSolutionCreateDropDialog, EROperationDesigner, ERComponentTypeDropDialog
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e4cd3960594ab37ca867792c655cfd28dc332fa9
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/05/2020
ms.locfileid: "4684773"
---
# <a name="er-create-a-format-configuration-november-2016"></a><span data-ttu-id="9fe9f-103">ER Skapa en formatkonfiguration (november 2016)</span><span class="sxs-lookup"><span data-stu-id="9fe9f-103">ER Create a format configuration (November 2016)</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="9fe9f-104">Det här avsnittet förklarar hur en användare i rollen Systemadministratör eller Utvecklare för elektronisk rapportering kan skapa en formatkonfiguration för elektronisk rapportering (ER).</span><span class="sxs-lookup"><span data-stu-id="9fe9f-104">This topic explains how a user in the System Administrator or Electronic Reporting Developer role can create a format configuration for Electronic reporting (ER).</span></span> <span data-ttu-id="9fe9f-105">Den här formatkonfiguration definierar formatet för elektroniska dokument som används för att bearbeta betalningar.</span><span class="sxs-lookup"><span data-stu-id="9fe9f-105">This format configuration will define the format of electronic documents that are used for processing payments.</span></span> <span data-ttu-id="9fe9f-106">I det här exemplet ska du skapa en konfigurering för exempelföretaget, Litware, Inc. För att slutföra dessa steg måste du först avsluta stegen i proceduren "Mappa modellen till utvalda datakällor".</span><span class="sxs-lookup"><span data-stu-id="9fe9f-106">In this example, you will create a format configuration for sample company, Litware, Inc. To complete these steps, you must first complete the steps in the "Map model to selected datasources" procedure.</span></span>


## <a name="create-a-new-format-configuration"></a><span data-ttu-id="9fe9f-107">Skapa en ny formatkonfiguration</span><span class="sxs-lookup"><span data-stu-id="9fe9f-107">Create a new format configuration</span></span>
1. <span data-ttu-id="9fe9f-108">Gå till **Organisationsadministration > Arbetsytor > Elektronisk rapportering**.</span><span class="sxs-lookup"><span data-stu-id="9fe9f-108">Go to **Organization administration > Workspaces > Electronic reporting**.</span></span>
2. <span data-ttu-id="9fe9f-109">Klicka på **Rapporteringskonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="9fe9f-109">Click **Reporting configurations**.</span></span>
3. <span data-ttu-id="9fe9f-110">I trädet väljer du **Betalningar (förenklad modell)**.</span><span class="sxs-lookup"><span data-stu-id="9fe9f-110">In the tree, select **Payments (simplified model)**.</span></span>
4. <span data-ttu-id="9fe9f-111">Klicka på **Skapa konfiguration** om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="9fe9f-111">Click **Create configuration** to open the drop dialog.</span></span>

 > [!NOTE]
 > <span data-ttu-id="9fe9f-112">Om du inte ser **Skapa konfiguration** måste du aktivera designläge på sidan **Elektronisk rapportering parametrar**.</span><span class="sxs-lookup"><span data-stu-id="9fe9f-112">If you don't see **Create configuration**, you must enable design mode on the **Electronic reporting parameters** page.</span></span> 
 
5. <span data-ttu-id="9fe9f-113">I fältet **Nytt** anger du **Format som baseras på datamodellen PaymentModel**.</span><span class="sxs-lookup"><span data-stu-id="9fe9f-113">In the **New** field, enter **Format based on data model PaymentModel**.</span></span>
6. <span data-ttu-id="9fe9f-114">I fältet **Namn**, ange **BACS (fiktivt UK)**.</span><span class="sxs-lookup"><span data-stu-id="9fe9f-114">In the **Name** field, type **BACS (UK fictitious)**.</span></span>
7. <span data-ttu-id="9fe9f-115">I fältet **Beskrivning** ange **BACS-leverantörsbetalningsformat (fiktivt UK)**.</span><span class="sxs-lookup"><span data-stu-id="9fe9f-115">In the **Description** field, type **BACS vendor payment format (UK fictitious)**.</span></span>
    * <span data-ttu-id="9fe9f-116">Den aktiva konfigurationsleverantören anges automatiskt här.</span><span class="sxs-lookup"><span data-stu-id="9fe9f-116">The active configuration provider is automatically entered here.</span></span> <span data-ttu-id="9fe9f-117">Den här leverantören kommer att kunna underhålla konfigurationen.</span><span class="sxs-lookup"><span data-stu-id="9fe9f-117">This provider will be able to maintain this configuration.</span></span> <span data-ttu-id="9fe9f-118">Andra leverantörer kan använda den här konfigurationen, men de kan inte underhålla den.</span><span class="sxs-lookup"><span data-stu-id="9fe9f-118">Other providers can use this configuration, but will not be able to maintain it.</span></span>  
    * <span data-ttu-id="9fe9f-119">Ett visst format för elektroniska dokument kan definieras.</span><span class="sxs-lookup"><span data-stu-id="9fe9f-119">A particular format of electronic document can be defined.</span></span> <span data-ttu-id="9fe9f-120">Lämna det här fältet tomt om du vill välja ett format vid körning.</span><span class="sxs-lookup"><span data-stu-id="9fe9f-120">Leave this field blank if you want to select a format at run-time.</span></span>  
8. <span data-ttu-id="9fe9f-121">I fältet **Definition av datamodell** ange eller välj ett värde.</span><span class="sxs-lookup"><span data-stu-id="9fe9f-121">In the **Data model definition** field, enter or select a value.</span></span>
9. <span data-ttu-id="9fe9f-122">Klicka på **Skapa konfiguration**.</span><span class="sxs-lookup"><span data-stu-id="9fe9f-122">Click **Create configuration**.</span></span> <span data-ttu-id="9fe9f-123">En ny konfiguration har skapats.</span><span class="sxs-lookup"><span data-stu-id="9fe9f-123">A new configuration has been created.</span></span> <span data-ttu-id="9fe9f-124">Utkastversionen kan användas för att lagra designformatet för att hantera elektroniska dokument.</span><span class="sxs-lookup"><span data-stu-id="9fe9f-124">The draft version can be used to store the design format for managing electronic documents.</span></span>  

## <a name="design-the-format-of-an-electronic-document"></a><span data-ttu-id="9fe9f-125">Designa formatet för ett elektroniskt dokument</span><span class="sxs-lookup"><span data-stu-id="9fe9f-125">Design the format of an electronic document</span></span>
1. <span data-ttu-id="9fe9f-126">Klicka på **Designer**.</span><span class="sxs-lookup"><span data-stu-id="9fe9f-126">Click **Designer**.</span></span>
2. <span data-ttu-id="9fe9f-127">Klicka på **Lägg till rot** för att öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="9fe9f-127">Click **Add root** to open the drop dialog.</span></span>
3. <span data-ttu-id="9fe9f-128">I trädet, välj **Allmänt\Fil**.</span><span class="sxs-lookup"><span data-stu-id="9fe9f-128">In the tree, select **Common\File**.</span></span>
4. <span data-ttu-id="9fe9f-129">I fältet **Namn** ange **Xml**.</span><span class="sxs-lookup"><span data-stu-id="9fe9f-129">In the **Name** field, type **Xml**.</span></span>
5. <span data-ttu-id="9fe9f-130">I fältet **Kodning** ange **UTF-8**.</span><span class="sxs-lookup"><span data-stu-id="9fe9f-130">In the **Encoding** field, type **UTF-8**.</span></span>
6. <span data-ttu-id="9fe9f-131">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="9fe9f-131">Click **OK**.</span></span>
7. <span data-ttu-id="9fe9f-132">Klicka på **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="9fe9f-132">Click **Add**.</span></span>
8. <span data-ttu-id="9fe9f-133">I trädet, välj **XML\Element**.</span><span class="sxs-lookup"><span data-stu-id="9fe9f-133">In the tree, select **XML\Element**.</span></span>
9. <span data-ttu-id="9fe9f-134">I fältet **Namn** ange **Meddelande**.</span><span class="sxs-lookup"><span data-stu-id="9fe9f-134">In the **Name** field, type **Message**.</span></span>
10. <span data-ttu-id="9fe9f-135">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="9fe9f-135">Click **OK**.</span></span>
11. <span data-ttu-id="9fe9f-136">I fältet träd ange **Xml\Message**.</span><span class="sxs-lookup"><span data-stu-id="9fe9f-136">In the tree, select **Xml\Message**.</span></span>
12. <span data-ttu-id="9fe9f-137">Klicka på **Lägg till element**.</span><span class="sxs-lookup"><span data-stu-id="9fe9f-137">Click **Add Element**.</span></span>
13. <span data-ttu-id="9fe9f-138">I fältet **Namn** ange **ProcessingDate**.</span><span class="sxs-lookup"><span data-stu-id="9fe9f-138">In the **Name** field, type **ProcessingDate**.</span></span>
14. <span data-ttu-id="9fe9f-139">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="9fe9f-139">Click **OK**.</span></span>
15. <span data-ttu-id="9fe9f-140">Klicka på **Lägg till element**.</span><span class="sxs-lookup"><span data-stu-id="9fe9f-140">Click **Add Element**.</span></span>
16. <span data-ttu-id="9fe9f-141">I fältet Namne ange **MessageId**.</span><span class="sxs-lookup"><span data-stu-id="9fe9f-141">In the Name field, type **MessageId**.</span></span>
17. <span data-ttu-id="9fe9f-142">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="9fe9f-142">Click **OK**.</span></span>
18. <span data-ttu-id="9fe9f-143">Klicka på **Lägg till element**.</span><span class="sxs-lookup"><span data-stu-id="9fe9f-143">Click **Add Element**.</span></span>
19. <span data-ttu-id="9fe9f-144">I fältet **Namn** ange **Betalningar**.</span><span class="sxs-lookup"><span data-stu-id="9fe9f-144">In the **Name** field, type **Payments**.</span></span>
20. <span data-ttu-id="9fe9f-145">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="9fe9f-145">Click **OK**.</span></span>
21. <span data-ttu-id="9fe9f-146">I trädet, välj **Xml\Message\Payments**.</span><span class="sxs-lookup"><span data-stu-id="9fe9f-146">In the tree, select **Xml\Message\Payments**.</span></span>
22. <span data-ttu-id="9fe9f-147">Klicka på **Lägg till element**.</span><span class="sxs-lookup"><span data-stu-id="9fe9f-147">Click **Add Element**.</span></span>
23. <span data-ttu-id="9fe9f-148">I fältet **Namn** ange **Artikel**.</span><span class="sxs-lookup"><span data-stu-id="9fe9f-148">In the **Name** field, type **Item**.</span></span>
24. <span data-ttu-id="9fe9f-149">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="9fe9f-149">Click **OK**.</span></span>
25. <span data-ttu-id="9fe9f-150">I trädet välj **Xml\Message\Payments\Item**.</span><span class="sxs-lookup"><span data-stu-id="9fe9f-150">In the tree, select **Xml\Message\Payments\Item**.</span></span>
26. <span data-ttu-id="9fe9f-151">Klicka på **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="9fe9f-151">Click **Add**.</span></span>
27. <span data-ttu-id="9fe9f-152">I trädet välj **XML\Attribute**.</span><span class="sxs-lookup"><span data-stu-id="9fe9f-152">In the tree, select **XML\Attribute**.</span></span>
28. <span data-ttu-id="9fe9f-153">I fältet Namn, ange **Id**.</span><span class="sxs-lookup"><span data-stu-id="9fe9f-153">In the Name field, type **Id**.</span></span>
29. <span data-ttu-id="9fe9f-154">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="9fe9f-154">Click **OK**.</span></span>
30. <span data-ttu-id="9fe9f-155">Klicka på **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="9fe9f-155">Click **Add**.</span></span>
31. <span data-ttu-id="9fe9f-156">I trädet, välj **XML\Element**.</span><span class="sxs-lookup"><span data-stu-id="9fe9f-156">In the tree, select **XML\Element**.</span></span>
32. <span data-ttu-id="9fe9f-157">I fältet Namn, ange **Leverantör**.</span><span class="sxs-lookup"><span data-stu-id="9fe9f-157">In the Name field, type **Vendor**.</span></span>
33. <span data-ttu-id="9fe9f-158">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="9fe9f-158">Click **OK**.</span></span>
34. <span data-ttu-id="9fe9f-159">I trädet välj **Xml\Message\Payments\Item\Vendor**.</span><span class="sxs-lookup"><span data-stu-id="9fe9f-159">In the tree, select **Xml\Message\Payments\Item\Vendor**.</span></span>
35. <span data-ttu-id="9fe9f-160">Klicka på **Lägg till element**.</span><span class="sxs-lookup"><span data-stu-id="9fe9f-160">Click **Add Element**.</span></span>
36. <span data-ttu-id="9fe9f-161">I fältet Namn, ange **Namn**.</span><span class="sxs-lookup"><span data-stu-id="9fe9f-161">In the Name field, type **Name**.</span></span>
37. <span data-ttu-id="9fe9f-162">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="9fe9f-162">Click **OK**.</span></span>
38. <span data-ttu-id="9fe9f-163">Klicka på **Lägg till element**.</span><span class="sxs-lookup"><span data-stu-id="9fe9f-163">Click **Add Element**.</span></span>
39. <span data-ttu-id="9fe9f-164">I fältet **Namn** ange **Bank**.</span><span class="sxs-lookup"><span data-stu-id="9fe9f-164">In the **Name** field, type **Bank**.</span></span>
40. <span data-ttu-id="9fe9f-165">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="9fe9f-165">Click **OK**.</span></span>
41. <span data-ttu-id="9fe9f-166">I trädet ange **Xml\Message\Payments\Item\Vendor\Bank**.</span><span class="sxs-lookup"><span data-stu-id="9fe9f-166">In the tree, select **Xml\Message\Payments\Item\Vendor\Bank**.</span></span>
42. <span data-ttu-id="9fe9f-167">Klicka på **Lägg till element**.</span><span class="sxs-lookup"><span data-stu-id="9fe9f-167">Click **Add Element**.</span></span>
43. <span data-ttu-id="9fe9f-168">I fältet **Namn** ange **RoutingNumber**.</span><span class="sxs-lookup"><span data-stu-id="9fe9f-168">In the **Name** field, type **RoutingNumber**.</span></span>
44. <span data-ttu-id="9fe9f-169">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="9fe9f-169">Click **OK**.</span></span>
45. <span data-ttu-id="9fe9f-170">Klicka på **Lägg till element**.</span><span class="sxs-lookup"><span data-stu-id="9fe9f-170">Click **Add Element**.</span></span>
46. <span data-ttu-id="9fe9f-171">I fältet **Namn** ange **AccountNumber**.</span><span class="sxs-lookup"><span data-stu-id="9fe9f-171">In the **Name** field, type **AccountNumber**.</span></span>
47. <span data-ttu-id="9fe9f-172">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="9fe9f-172">Click **OK**.</span></span>
48. <span data-ttu-id="9fe9f-173">I trädet välj **Xml\Message\Payments\Item\Vendor**.</span><span class="sxs-lookup"><span data-stu-id="9fe9f-173">In the tree, select **Xml\Message\Payments\Item\Vendor**.</span></span>
49. <span data-ttu-id="9fe9f-174">Klicka på **Kopiera**.</span><span class="sxs-lookup"><span data-stu-id="9fe9f-174">Click **Copy**.</span></span>
50. <span data-ttu-id="9fe9f-175">I trädet välj **Xml\Message\Payments\Item**.</span><span class="sxs-lookup"><span data-stu-id="9fe9f-175">In the tree, select **Xml\Message\Payments\Item**.</span></span>
51. <span data-ttu-id="9fe9f-176">Klicka på **Klistra in**.</span><span class="sxs-lookup"><span data-stu-id="9fe9f-176">Click **Paste**.</span></span>
52. <span data-ttu-id="9fe9f-177">I fältet **Namn** ange **Betalare**.</span><span class="sxs-lookup"><span data-stu-id="9fe9f-177">In the **Name** field, type **Payer**.</span></span>
53. <span data-ttu-id="9fe9f-178">I trädet välj **Xml\Message\Payments\Item**.</span><span class="sxs-lookup"><span data-stu-id="9fe9f-178">In the tree, select **Xml\Message\Payments\Item**.</span></span>
54. <span data-ttu-id="9fe9f-179">Klicka på **Lägg till element**.</span><span class="sxs-lookup"><span data-stu-id="9fe9f-179">Click **Add Element**.</span></span>
55. <span data-ttu-id="9fe9f-180">I fältet **Namn** ange **Valuta**.</span><span class="sxs-lookup"><span data-stu-id="9fe9f-180">In the **Name** field, type **Currency**.</span></span>
56. <span data-ttu-id="9fe9f-181">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="9fe9f-181">Click **OK**.</span></span>
57. <span data-ttu-id="9fe9f-182">Klicka på **Lägg till element**.</span><span class="sxs-lookup"><span data-stu-id="9fe9f-182">Click **Add Element**.</span></span>
58. <span data-ttu-id="9fe9f-183">I fältet **Namn** ange **Beskrivning**.</span><span class="sxs-lookup"><span data-stu-id="9fe9f-183">In the **Name** field, type **Description**.</span></span>
59. <span data-ttu-id="9fe9f-184">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="9fe9f-184">Click **OK**.</span></span>
60. <span data-ttu-id="9fe9f-185">Klicka på **Lägg till element**.</span><span class="sxs-lookup"><span data-stu-id="9fe9f-185">Click **Add Element**.</span></span>
61. <span data-ttu-id="9fe9f-186">I fältet Nman ange **TransDate**.</span><span class="sxs-lookup"><span data-stu-id="9fe9f-186">In the Name field, type **TransDate**.</span></span>
62. <span data-ttu-id="9fe9f-187">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="9fe9f-187">Click **OK**.</span></span>
63. <span data-ttu-id="9fe9f-188">Klicka på **Lägg till element**.</span><span class="sxs-lookup"><span data-stu-id="9fe9f-188">Click **Add Element**.</span></span>
64. <span data-ttu-id="9fe9f-189">I fältet Namn ange **Belopp**.</span><span class="sxs-lookup"><span data-stu-id="9fe9f-189">In the Name field, type **Amount**.</span></span>
65. <span data-ttu-id="9fe9f-190">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="9fe9f-190">Click **OK**.</span></span>

## <a name="prepare-format-components-for-mapping-to-data-model-elements"></a><span data-ttu-id="9fe9f-191">Förbered formatkomponenter för att mappa till datamodellelement</span><span class="sxs-lookup"><span data-stu-id="9fe9f-191">Prepare format components for mapping to data model elements</span></span>
1. <span data-ttu-id="9fe9f-192">I trädet ange **Xml\Message\ProcessingDate**.</span><span class="sxs-lookup"><span data-stu-id="9fe9f-192">In the tree, select **Xml\Message\ProcessingDate**.</span></span>
2. <span data-ttu-id="9fe9f-193">Klicka på **Lägg till** för att öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="9fe9f-193">Click **Add** to open the drop dialog.</span></span>
3. <span data-ttu-id="9fe9f-194">I trädet välj **Text\DateTime**.</span><span class="sxs-lookup"><span data-stu-id="9fe9f-194">In the tree, select **Text\DateTime**.</span></span>
4. <span data-ttu-id="9fe9f-195">I fältet **Format** ange **åååå-MM-dd**.</span><span class="sxs-lookup"><span data-stu-id="9fe9f-195">In the **Format** field, type **yyyy-MM-dd**.</span></span>
5. <span data-ttu-id="9fe9f-196">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="9fe9f-196">Click **OK**.</span></span>
6. <span data-ttu-id="9fe9f-197">I trädet ange **Xml\Message\Payments\Item\TransDate**.</span><span class="sxs-lookup"><span data-stu-id="9fe9f-197">In the tree, select **Xml\Message\Payments\Item\TransDate**.</span></span>
7. <span data-ttu-id="9fe9f-198">Klicka på **Lägg till DateTime**.</span><span class="sxs-lookup"><span data-stu-id="9fe9f-198">Click **Add DateTime**.</span></span>
8. <span data-ttu-id="9fe9f-199">I fältet **Format** ange **åååå-MM-dd**.</span><span class="sxs-lookup"><span data-stu-id="9fe9f-199">In the **Format** field, type **yyyy-MM-dd**.</span></span>
9. <span data-ttu-id="9fe9f-200">I fältet **DateTime** ange **Datum**.</span><span class="sxs-lookup"><span data-stu-id="9fe9f-200">In the **DateTime** type field, select **Date**.</span></span>
10. <span data-ttu-id="9fe9f-201">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="9fe9f-201">Click **OK**.</span></span>
11. <span data-ttu-id="9fe9f-202">I trädet ange **Xml\Message\MessageId**.</span><span class="sxs-lookup"><span data-stu-id="9fe9f-202">In the tree, select **Xml\Message\MessageId**.</span></span>
12. <span data-ttu-id="9fe9f-203">Klicka på **Lägg till** för att öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="9fe9f-203">Click **Add** to open the drop dialog.</span></span>
13. <span data-ttu-id="9fe9f-204">I trädet ange **Text\String**.</span><span class="sxs-lookup"><span data-stu-id="9fe9f-204">In the tree, select **Text\String**.</span></span>
14. <span data-ttu-id="9fe9f-205">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="9fe9f-205">Click **OK**.</span></span>
15. <span data-ttu-id="9fe9f-206">I trädet ange **Xml\Message\Payments\Item\Vendor\Name**.</span><span class="sxs-lookup"><span data-stu-id="9fe9f-206">In the tree, select **Xml\Message\Payments\Item\Vendor\Name**.</span></span>
16. <span data-ttu-id="9fe9f-207">Klicka på **Lägg till sträng**.</span><span class="sxs-lookup"><span data-stu-id="9fe9f-207">Click **Add String**.</span></span>
17. <span data-ttu-id="9fe9f-208">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="9fe9f-208">Click **OK**.</span></span>
18. <span data-ttu-id="9fe9f-209">I trädet välj **Xml\Message\Payments\Item\Vendor\Bank\RoutingNumber**.</span><span class="sxs-lookup"><span data-stu-id="9fe9f-209">In the tree, select **Xml\Message\Payments\Item\Vendor\Bank\RoutingNumber**.</span></span>
19. <span data-ttu-id="9fe9f-210">Klicka på **Lägg till sträng**.</span><span class="sxs-lookup"><span data-stu-id="9fe9f-210">Click **Add String**.</span></span>
20. <span data-ttu-id="9fe9f-211">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="9fe9f-211">Click **OK**.</span></span>
21. <span data-ttu-id="9fe9f-212">I trädet välj **Xml\Message\Payments\Item\Vendor\Bank\AccountNumber**.</span><span class="sxs-lookup"><span data-stu-id="9fe9f-212">In the tree, select **Xml\Message\Payments\Item\Vendor\Bank\AccountNumber**.</span></span>
22. <span data-ttu-id="9fe9f-213">Klicka på **Lägg till sträng**.</span><span class="sxs-lookup"><span data-stu-id="9fe9f-213">Click **Add String**.</span></span>
23. <span data-ttu-id="9fe9f-214">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="9fe9f-214">Click **OK**.</span></span>
24. <span data-ttu-id="9fe9f-215">I trädet välj **Xml\Message\Payments\Item\Payer\Name**.</span><span class="sxs-lookup"><span data-stu-id="9fe9f-215">In the tree, select **Xml\Message\Payments\Item\Payer\Name**.</span></span>
25. <span data-ttu-id="9fe9f-216">Klicka på **Lägg till sträng**.</span><span class="sxs-lookup"><span data-stu-id="9fe9f-216">Click **Add String**.</span></span>
26. <span data-ttu-id="9fe9f-217">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="9fe9f-217">Click **OK**.</span></span>
27. <span data-ttu-id="9fe9f-218">I trädet välj **Xml\Message\Payments\Item\Payer\Bank\RoutingNumber**.</span><span class="sxs-lookup"><span data-stu-id="9fe9f-218">In the tree, select **Xml\Message\Payments\Item\Payer\Bank\RoutingNumber**.</span></span>
28. <span data-ttu-id="9fe9f-219">Klicka på **Lägg till sträng**.</span><span class="sxs-lookup"><span data-stu-id="9fe9f-219">Click **Add String**.</span></span>
29. <span data-ttu-id="9fe9f-220">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="9fe9f-220">Click **OK**.</span></span>
30. <span data-ttu-id="9fe9f-221">I trädet välj **Xml\Message\Payments\Item\Payer\Bank\AccountNumber**.</span><span class="sxs-lookup"><span data-stu-id="9fe9f-221">In the tree, select **Xml\Message\Payments\Item\Payer\Bank\AccountNumber**.</span></span>
31. <span data-ttu-id="9fe9f-222">Klicka på **Lägg till sträng**.</span><span class="sxs-lookup"><span data-stu-id="9fe9f-222">Click **Add String**.</span></span>
32. <span data-ttu-id="9fe9f-223">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="9fe9f-223">Click **OK**.</span></span>
33. <span data-ttu-id="9fe9f-224">I trädet välj **Xml\Message\Payments\Item\Currency**.</span><span class="sxs-lookup"><span data-stu-id="9fe9f-224">In the tree, select **Xml\Message\Payments\Item\Currency**.</span></span>
34. <span data-ttu-id="9fe9f-225">Klicka på **Lägg till sträng**.</span><span class="sxs-lookup"><span data-stu-id="9fe9f-225">Click **Add String**.</span></span>
35. <span data-ttu-id="9fe9f-226">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="9fe9f-226">Click **OK**.</span></span>
36. <span data-ttu-id="9fe9f-227">I trädet välj **Xml\Message\Payments\Item\Description**.</span><span class="sxs-lookup"><span data-stu-id="9fe9f-227">In the tree, select **Xml\Message\Payments\Item\Description**.</span></span>
37. <span data-ttu-id="9fe9f-228">Klicka på **Lägg till sträng**.</span><span class="sxs-lookup"><span data-stu-id="9fe9f-228">Click **Add String**.</span></span>
38. <span data-ttu-id="9fe9f-229">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="9fe9f-229">Click **OK**.</span></span>
39. <span data-ttu-id="9fe9f-230">I trädet välj **Xml\Message\Payments\Item\Amount**.</span><span class="sxs-lookup"><span data-stu-id="9fe9f-230">In the tree, select **Xml\Message\Payments\Item\Amount**.</span></span>
40. <span data-ttu-id="9fe9f-231">Klicka på **Lägg till sträng**.</span><span class="sxs-lookup"><span data-stu-id="9fe9f-231">Click **Add String**.</span></span>
41. <span data-ttu-id="9fe9f-232">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="9fe9f-232">Click **OK**.</span></span>
42. <span data-ttu-id="9fe9f-233">Klicka på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="9fe9f-233">Click **Save**.</span></span>
43. <span data-ttu-id="9fe9f-234">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="9fe9f-234">Close the page.</span></span>

