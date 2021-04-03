---
title: ER Skapa en formatkonfiguration (november 2016)
description: I det här avsnittet beskrivs hur du skapar en formatkonfiguration för elektronisk rapportering (ER).
author: NickSelin
manager: AnnBe
ms.date: 08/02/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, ERSolutionCreateDropDialog, EROperationDesigner, ERComponentTypeDropDialog
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 8cb86c1486223e982f8cbddc8eadaaf1c8ced4f8
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/09/2021
ms.locfileid: "5565200"
---
# <a name="er-create-a-format-configuration-november-2016"></a><span data-ttu-id="f308b-103">ER Skapa en formatkonfiguration (november 2016)</span><span class="sxs-lookup"><span data-stu-id="f308b-103">ER Create a format configuration (November 2016)</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="f308b-104">Det här avsnittet förklarar hur en användare i rollen Systemadministratör eller Utvecklare för elektronisk rapportering kan skapa en formatkonfiguration för elektronisk rapportering (ER).</span><span class="sxs-lookup"><span data-stu-id="f308b-104">This topic explains how a user in the System Administrator or Electronic Reporting Developer role can create a format configuration for Electronic reporting (ER).</span></span> <span data-ttu-id="f308b-105">Den här formatkonfiguration definierar formatet för elektroniska dokument som används för att bearbeta betalningar.</span><span class="sxs-lookup"><span data-stu-id="f308b-105">This format configuration will define the format of electronic documents that are used for processing payments.</span></span> <span data-ttu-id="f308b-106">I det här exemplet ska du skapa en konfigurering för exempelföretaget, Litware, Inc. För att slutföra dessa steg måste du först avsluta stegen i proceduren "Mappa modellen till utvalda datakällor".</span><span class="sxs-lookup"><span data-stu-id="f308b-106">In this example, you will create a format configuration for sample company, Litware, Inc. To complete these steps, you must first complete the steps in the "Map model to selected datasources" procedure.</span></span>


## <a name="create-a-new-format-configuration"></a><span data-ttu-id="f308b-107">Skapa en ny formatkonfiguration</span><span class="sxs-lookup"><span data-stu-id="f308b-107">Create a new format configuration</span></span>
1. <span data-ttu-id="f308b-108">Gå till **Organisationsadministration > Arbetsytor > Elektronisk rapportering**.</span><span class="sxs-lookup"><span data-stu-id="f308b-108">Go to **Organization administration > Workspaces > Electronic reporting**.</span></span>
2. <span data-ttu-id="f308b-109">Klicka på **Rapporteringskonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="f308b-109">Click **Reporting configurations**.</span></span>
3. <span data-ttu-id="f308b-110">I trädet väljer du **Betalningar (förenklad modell)**.</span><span class="sxs-lookup"><span data-stu-id="f308b-110">In the tree, select **Payments (simplified model)**.</span></span>
4. <span data-ttu-id="f308b-111">Klicka på **Skapa konfiguration** om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="f308b-111">Click **Create configuration** to open the drop dialog.</span></span>

 > [!NOTE]
 > <span data-ttu-id="f308b-112">Om du inte ser **Skapa konfiguration** måste du aktivera designläge på sidan **Elektronisk rapportering parametrar**.</span><span class="sxs-lookup"><span data-stu-id="f308b-112">If you don't see **Create configuration**, you must enable design mode on the **Electronic reporting parameters** page.</span></span> 
 
5. <span data-ttu-id="f308b-113">I fältet **Nytt** anger du **Format som baseras på datamodellen PaymentModel**.</span><span class="sxs-lookup"><span data-stu-id="f308b-113">In the **New** field, enter **Format based on data model PaymentModel**.</span></span>
6. <span data-ttu-id="f308b-114">I fältet **Namn**, ange **BACS (fiktivt UK)**.</span><span class="sxs-lookup"><span data-stu-id="f308b-114">In the **Name** field, type **BACS (UK fictitious)**.</span></span>
7. <span data-ttu-id="f308b-115">I fältet **Beskrivning** ange **BACS-leverantörsbetalningsformat (fiktivt UK)**.</span><span class="sxs-lookup"><span data-stu-id="f308b-115">In the **Description** field, type **BACS vendor payment format (UK fictitious)**.</span></span>
    * <span data-ttu-id="f308b-116">Den aktiva konfigurationsleverantören anges automatiskt här.</span><span class="sxs-lookup"><span data-stu-id="f308b-116">The active configuration provider is automatically entered here.</span></span> <span data-ttu-id="f308b-117">Den här leverantören kommer att kunna underhålla konfigurationen.</span><span class="sxs-lookup"><span data-stu-id="f308b-117">This provider will be able to maintain this configuration.</span></span> <span data-ttu-id="f308b-118">Andra leverantörer kan använda den här konfigurationen, men de kan inte underhålla den.</span><span class="sxs-lookup"><span data-stu-id="f308b-118">Other providers can use this configuration, but will not be able to maintain it.</span></span>  
    * <span data-ttu-id="f308b-119">Ett visst format för elektroniska dokument kan definieras.</span><span class="sxs-lookup"><span data-stu-id="f308b-119">A particular format of electronic document can be defined.</span></span> <span data-ttu-id="f308b-120">Lämna det här fältet tomt om du vill välja ett format vid körning.</span><span class="sxs-lookup"><span data-stu-id="f308b-120">Leave this field blank if you want to select a format at run-time.</span></span>  
8. <span data-ttu-id="f308b-121">I fältet **Definition av datamodell** ange eller välj ett värde.</span><span class="sxs-lookup"><span data-stu-id="f308b-121">In the **Data model definition** field, enter or select a value.</span></span>
9. <span data-ttu-id="f308b-122">Klicka på **Skapa konfiguration**.</span><span class="sxs-lookup"><span data-stu-id="f308b-122">Click **Create configuration**.</span></span> <span data-ttu-id="f308b-123">En ny konfiguration har skapats.</span><span class="sxs-lookup"><span data-stu-id="f308b-123">A new configuration has been created.</span></span> <span data-ttu-id="f308b-124">Utkastversionen kan användas för att lagra designformatet för att hantera elektroniska dokument.</span><span class="sxs-lookup"><span data-stu-id="f308b-124">The draft version can be used to store the design format for managing electronic documents.</span></span>  

## <a name="design-the-format-of-an-electronic-document"></a><span data-ttu-id="f308b-125">Designa formatet för ett elektroniskt dokument</span><span class="sxs-lookup"><span data-stu-id="f308b-125">Design the format of an electronic document</span></span>
1. <span data-ttu-id="f308b-126">Klicka på **Designer**.</span><span class="sxs-lookup"><span data-stu-id="f308b-126">Click **Designer**.</span></span>
2. <span data-ttu-id="f308b-127">Klicka på **Lägg till rot** för att öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="f308b-127">Click **Add root** to open the drop dialog.</span></span>
3. <span data-ttu-id="f308b-128">I trädet, välj **Allmänt\Fil**.</span><span class="sxs-lookup"><span data-stu-id="f308b-128">In the tree, select **Common\File**.</span></span>
4. <span data-ttu-id="f308b-129">I fältet **Namn** ange **Xml**.</span><span class="sxs-lookup"><span data-stu-id="f308b-129">In the **Name** field, type **Xml**.</span></span>
5. <span data-ttu-id="f308b-130">I fältet **Kodning** ange **UTF-8**.</span><span class="sxs-lookup"><span data-stu-id="f308b-130">In the **Encoding** field, type **UTF-8**.</span></span>
6. <span data-ttu-id="f308b-131">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="f308b-131">Click **OK**.</span></span>
7. <span data-ttu-id="f308b-132">Klicka på **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="f308b-132">Click **Add**.</span></span>
8. <span data-ttu-id="f308b-133">I trädet, välj **XML\Element**.</span><span class="sxs-lookup"><span data-stu-id="f308b-133">In the tree, select **XML\Element**.</span></span>
9. <span data-ttu-id="f308b-134">I fältet **Namn** ange **Meddelande**.</span><span class="sxs-lookup"><span data-stu-id="f308b-134">In the **Name** field, type **Message**.</span></span>
10. <span data-ttu-id="f308b-135">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="f308b-135">Click **OK**.</span></span>
11. <span data-ttu-id="f308b-136">I fältet träd ange **Xml\Message**.</span><span class="sxs-lookup"><span data-stu-id="f308b-136">In the tree, select **Xml\Message**.</span></span>
12. <span data-ttu-id="f308b-137">Klicka på **Lägg till element**.</span><span class="sxs-lookup"><span data-stu-id="f308b-137">Click **Add Element**.</span></span>
13. <span data-ttu-id="f308b-138">I fältet **Namn** ange **ProcessingDate**.</span><span class="sxs-lookup"><span data-stu-id="f308b-138">In the **Name** field, type **ProcessingDate**.</span></span>
14. <span data-ttu-id="f308b-139">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="f308b-139">Click **OK**.</span></span>
15. <span data-ttu-id="f308b-140">Klicka på **Lägg till element**.</span><span class="sxs-lookup"><span data-stu-id="f308b-140">Click **Add Element**.</span></span>
16. <span data-ttu-id="f308b-141">I fältet Namne ange **MessageId**.</span><span class="sxs-lookup"><span data-stu-id="f308b-141">In the Name field, type **MessageId**.</span></span>
17. <span data-ttu-id="f308b-142">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="f308b-142">Click **OK**.</span></span>
18. <span data-ttu-id="f308b-143">Klicka på **Lägg till element**.</span><span class="sxs-lookup"><span data-stu-id="f308b-143">Click **Add Element**.</span></span>
19. <span data-ttu-id="f308b-144">I fältet **Namn** ange **Betalningar**.</span><span class="sxs-lookup"><span data-stu-id="f308b-144">In the **Name** field, type **Payments**.</span></span>
20. <span data-ttu-id="f308b-145">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="f308b-145">Click **OK**.</span></span>
21. <span data-ttu-id="f308b-146">I trädet, välj **Xml\Message\Payments**.</span><span class="sxs-lookup"><span data-stu-id="f308b-146">In the tree, select **Xml\Message\Payments**.</span></span>
22. <span data-ttu-id="f308b-147">Klicka på **Lägg till element**.</span><span class="sxs-lookup"><span data-stu-id="f308b-147">Click **Add Element**.</span></span>
23. <span data-ttu-id="f308b-148">I fältet **Namn** ange **Artikel**.</span><span class="sxs-lookup"><span data-stu-id="f308b-148">In the **Name** field, type **Item**.</span></span>
24. <span data-ttu-id="f308b-149">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="f308b-149">Click **OK**.</span></span>
25. <span data-ttu-id="f308b-150">I trädet välj **Xml\Message\Payments\Item**.</span><span class="sxs-lookup"><span data-stu-id="f308b-150">In the tree, select **Xml\Message\Payments\Item**.</span></span>
26. <span data-ttu-id="f308b-151">Klicka på **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="f308b-151">Click **Add**.</span></span>
27. <span data-ttu-id="f308b-152">I trädet välj **XML\Attribute**.</span><span class="sxs-lookup"><span data-stu-id="f308b-152">In the tree, select **XML\Attribute**.</span></span>
28. <span data-ttu-id="f308b-153">I fältet Namn, ange **Id**.</span><span class="sxs-lookup"><span data-stu-id="f308b-153">In the Name field, type **Id**.</span></span>
29. <span data-ttu-id="f308b-154">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="f308b-154">Click **OK**.</span></span>
30. <span data-ttu-id="f308b-155">Klicka på **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="f308b-155">Click **Add**.</span></span>
31. <span data-ttu-id="f308b-156">I trädet, välj **XML\Element**.</span><span class="sxs-lookup"><span data-stu-id="f308b-156">In the tree, select **XML\Element**.</span></span>
32. <span data-ttu-id="f308b-157">I fältet Namn, ange **Leverantör**.</span><span class="sxs-lookup"><span data-stu-id="f308b-157">In the Name field, type **Vendor**.</span></span>
33. <span data-ttu-id="f308b-158">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="f308b-158">Click **OK**.</span></span>
34. <span data-ttu-id="f308b-159">I trädet välj **Xml\Message\Payments\Item\Vendor**.</span><span class="sxs-lookup"><span data-stu-id="f308b-159">In the tree, select **Xml\Message\Payments\Item\Vendor**.</span></span>
35. <span data-ttu-id="f308b-160">Klicka på **Lägg till element**.</span><span class="sxs-lookup"><span data-stu-id="f308b-160">Click **Add Element**.</span></span>
36. <span data-ttu-id="f308b-161">I fältet Namn, ange **Namn**.</span><span class="sxs-lookup"><span data-stu-id="f308b-161">In the Name field, type **Name**.</span></span>
37. <span data-ttu-id="f308b-162">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="f308b-162">Click **OK**.</span></span>
38. <span data-ttu-id="f308b-163">Klicka på **Lägg till element**.</span><span class="sxs-lookup"><span data-stu-id="f308b-163">Click **Add Element**.</span></span>
39. <span data-ttu-id="f308b-164">I fältet **Namn** ange **Bank**.</span><span class="sxs-lookup"><span data-stu-id="f308b-164">In the **Name** field, type **Bank**.</span></span>
40. <span data-ttu-id="f308b-165">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="f308b-165">Click **OK**.</span></span>
41. <span data-ttu-id="f308b-166">I trädet ange **Xml\Message\Payments\Item\Vendor\Bank**.</span><span class="sxs-lookup"><span data-stu-id="f308b-166">In the tree, select **Xml\Message\Payments\Item\Vendor\Bank**.</span></span>
42. <span data-ttu-id="f308b-167">Klicka på **Lägg till element**.</span><span class="sxs-lookup"><span data-stu-id="f308b-167">Click **Add Element**.</span></span>
43. <span data-ttu-id="f308b-168">I fältet **Namn** ange **RoutingNumber**.</span><span class="sxs-lookup"><span data-stu-id="f308b-168">In the **Name** field, type **RoutingNumber**.</span></span>
44. <span data-ttu-id="f308b-169">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="f308b-169">Click **OK**.</span></span>
45. <span data-ttu-id="f308b-170">Klicka på **Lägg till element**.</span><span class="sxs-lookup"><span data-stu-id="f308b-170">Click **Add Element**.</span></span>
46. <span data-ttu-id="f308b-171">I fältet **Namn** ange **AccountNumber**.</span><span class="sxs-lookup"><span data-stu-id="f308b-171">In the **Name** field, type **AccountNumber**.</span></span>
47. <span data-ttu-id="f308b-172">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="f308b-172">Click **OK**.</span></span>
48. <span data-ttu-id="f308b-173">I trädet välj **Xml\Message\Payments\Item\Vendor**.</span><span class="sxs-lookup"><span data-stu-id="f308b-173">In the tree, select **Xml\Message\Payments\Item\Vendor**.</span></span>
49. <span data-ttu-id="f308b-174">Klicka på **Kopiera**.</span><span class="sxs-lookup"><span data-stu-id="f308b-174">Click **Copy**.</span></span>
50. <span data-ttu-id="f308b-175">I trädet välj **Xml\Message\Payments\Item**.</span><span class="sxs-lookup"><span data-stu-id="f308b-175">In the tree, select **Xml\Message\Payments\Item**.</span></span>
51. <span data-ttu-id="f308b-176">Klicka på **Klistra in**.</span><span class="sxs-lookup"><span data-stu-id="f308b-176">Click **Paste**.</span></span>
52. <span data-ttu-id="f308b-177">I fältet **Namn** ange **Betalare**.</span><span class="sxs-lookup"><span data-stu-id="f308b-177">In the **Name** field, type **Payer**.</span></span>
53. <span data-ttu-id="f308b-178">I trädet välj **Xml\Message\Payments\Item**.</span><span class="sxs-lookup"><span data-stu-id="f308b-178">In the tree, select **Xml\Message\Payments\Item**.</span></span>
54. <span data-ttu-id="f308b-179">Klicka på **Lägg till element**.</span><span class="sxs-lookup"><span data-stu-id="f308b-179">Click **Add Element**.</span></span>
55. <span data-ttu-id="f308b-180">I fältet **Namn** ange **Valuta**.</span><span class="sxs-lookup"><span data-stu-id="f308b-180">In the **Name** field, type **Currency**.</span></span>
56. <span data-ttu-id="f308b-181">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="f308b-181">Click **OK**.</span></span>
57. <span data-ttu-id="f308b-182">Klicka på **Lägg till element**.</span><span class="sxs-lookup"><span data-stu-id="f308b-182">Click **Add Element**.</span></span>
58. <span data-ttu-id="f308b-183">I fältet **Namn** ange **Beskrivning**.</span><span class="sxs-lookup"><span data-stu-id="f308b-183">In the **Name** field, type **Description**.</span></span>
59. <span data-ttu-id="f308b-184">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="f308b-184">Click **OK**.</span></span>
60. <span data-ttu-id="f308b-185">Klicka på **Lägg till element**.</span><span class="sxs-lookup"><span data-stu-id="f308b-185">Click **Add Element**.</span></span>
61. <span data-ttu-id="f308b-186">I fältet Nman ange **TransDate**.</span><span class="sxs-lookup"><span data-stu-id="f308b-186">In the Name field, type **TransDate**.</span></span>
62. <span data-ttu-id="f308b-187">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="f308b-187">Click **OK**.</span></span>
63. <span data-ttu-id="f308b-188">Klicka på **Lägg till element**.</span><span class="sxs-lookup"><span data-stu-id="f308b-188">Click **Add Element**.</span></span>
64. <span data-ttu-id="f308b-189">I fältet Namn ange **Belopp**.</span><span class="sxs-lookup"><span data-stu-id="f308b-189">In the Name field, type **Amount**.</span></span>
65. <span data-ttu-id="f308b-190">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="f308b-190">Click **OK**.</span></span>

## <a name="prepare-format-components-for-mapping-to-data-model-elements"></a><span data-ttu-id="f308b-191">Förbered formatkomponenter för att mappa till datamodellelement</span><span class="sxs-lookup"><span data-stu-id="f308b-191">Prepare format components for mapping to data model elements</span></span>
1. <span data-ttu-id="f308b-192">I trädet ange **Xml\Message\ProcessingDate**.</span><span class="sxs-lookup"><span data-stu-id="f308b-192">In the tree, select **Xml\Message\ProcessingDate**.</span></span>
2. <span data-ttu-id="f308b-193">Klicka på **Lägg till** för att öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="f308b-193">Click **Add** to open the drop dialog.</span></span>
3. <span data-ttu-id="f308b-194">I trädet välj **Text\DateTime**.</span><span class="sxs-lookup"><span data-stu-id="f308b-194">In the tree, select **Text\DateTime**.</span></span>
4. <span data-ttu-id="f308b-195">I fältet **Format** ange **åååå-MM-dd**.</span><span class="sxs-lookup"><span data-stu-id="f308b-195">In the **Format** field, type **yyyy-MM-dd**.</span></span>
5. <span data-ttu-id="f308b-196">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="f308b-196">Click **OK**.</span></span>
6. <span data-ttu-id="f308b-197">I trädet ange **Xml\Message\Payments\Item\TransDate**.</span><span class="sxs-lookup"><span data-stu-id="f308b-197">In the tree, select **Xml\Message\Payments\Item\TransDate**.</span></span>
7. <span data-ttu-id="f308b-198">Klicka på **Lägg till DateTime**.</span><span class="sxs-lookup"><span data-stu-id="f308b-198">Click **Add DateTime**.</span></span>
8. <span data-ttu-id="f308b-199">I fältet **Format** ange **åååå-MM-dd**.</span><span class="sxs-lookup"><span data-stu-id="f308b-199">In the **Format** field, type **yyyy-MM-dd**.</span></span>
9. <span data-ttu-id="f308b-200">I fältet **DateTime** ange **Datum**.</span><span class="sxs-lookup"><span data-stu-id="f308b-200">In the **DateTime** type field, select **Date**.</span></span>
10. <span data-ttu-id="f308b-201">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="f308b-201">Click **OK**.</span></span>
11. <span data-ttu-id="f308b-202">I trädet ange **Xml\Message\MessageId**.</span><span class="sxs-lookup"><span data-stu-id="f308b-202">In the tree, select **Xml\Message\MessageId**.</span></span>
12. <span data-ttu-id="f308b-203">Klicka på **Lägg till** för att öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="f308b-203">Click **Add** to open the drop dialog.</span></span>
13. <span data-ttu-id="f308b-204">I trädet ange **Text\String**.</span><span class="sxs-lookup"><span data-stu-id="f308b-204">In the tree, select **Text\String**.</span></span>
14. <span data-ttu-id="f308b-205">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="f308b-205">Click **OK**.</span></span>
15. <span data-ttu-id="f308b-206">I trädet ange **Xml\Message\Payments\Item\Vendor\Name**.</span><span class="sxs-lookup"><span data-stu-id="f308b-206">In the tree, select **Xml\Message\Payments\Item\Vendor\Name**.</span></span>
16. <span data-ttu-id="f308b-207">Klicka på **Lägg till sträng**.</span><span class="sxs-lookup"><span data-stu-id="f308b-207">Click **Add String**.</span></span>
17. <span data-ttu-id="f308b-208">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="f308b-208">Click **OK**.</span></span>
18. <span data-ttu-id="f308b-209">I trädet välj **Xml\Message\Payments\Item\Vendor\Bank\RoutingNumber**.</span><span class="sxs-lookup"><span data-stu-id="f308b-209">In the tree, select **Xml\Message\Payments\Item\Vendor\Bank\RoutingNumber**.</span></span>
19. <span data-ttu-id="f308b-210">Klicka på **Lägg till sträng**.</span><span class="sxs-lookup"><span data-stu-id="f308b-210">Click **Add String**.</span></span>
20. <span data-ttu-id="f308b-211">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="f308b-211">Click **OK**.</span></span>
21. <span data-ttu-id="f308b-212">I trädet välj **Xml\Message\Payments\Item\Vendor\Bank\AccountNumber**.</span><span class="sxs-lookup"><span data-stu-id="f308b-212">In the tree, select **Xml\Message\Payments\Item\Vendor\Bank\AccountNumber**.</span></span>
22. <span data-ttu-id="f308b-213">Klicka på **Lägg till sträng**.</span><span class="sxs-lookup"><span data-stu-id="f308b-213">Click **Add String**.</span></span>
23. <span data-ttu-id="f308b-214">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="f308b-214">Click **OK**.</span></span>
24. <span data-ttu-id="f308b-215">I trädet välj **Xml\Message\Payments\Item\Payer\Name**.</span><span class="sxs-lookup"><span data-stu-id="f308b-215">In the tree, select **Xml\Message\Payments\Item\Payer\Name**.</span></span>
25. <span data-ttu-id="f308b-216">Klicka på **Lägg till sträng**.</span><span class="sxs-lookup"><span data-stu-id="f308b-216">Click **Add String**.</span></span>
26. <span data-ttu-id="f308b-217">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="f308b-217">Click **OK**.</span></span>
27. <span data-ttu-id="f308b-218">I trädet välj **Xml\Message\Payments\Item\Payer\Bank\RoutingNumber**.</span><span class="sxs-lookup"><span data-stu-id="f308b-218">In the tree, select **Xml\Message\Payments\Item\Payer\Bank\RoutingNumber**.</span></span>
28. <span data-ttu-id="f308b-219">Klicka på **Lägg till sträng**.</span><span class="sxs-lookup"><span data-stu-id="f308b-219">Click **Add String**.</span></span>
29. <span data-ttu-id="f308b-220">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="f308b-220">Click **OK**.</span></span>
30. <span data-ttu-id="f308b-221">I trädet välj **Xml\Message\Payments\Item\Payer\Bank\AccountNumber**.</span><span class="sxs-lookup"><span data-stu-id="f308b-221">In the tree, select **Xml\Message\Payments\Item\Payer\Bank\AccountNumber**.</span></span>
31. <span data-ttu-id="f308b-222">Klicka på **Lägg till sträng**.</span><span class="sxs-lookup"><span data-stu-id="f308b-222">Click **Add String**.</span></span>
32. <span data-ttu-id="f308b-223">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="f308b-223">Click **OK**.</span></span>
33. <span data-ttu-id="f308b-224">I trädet välj **Xml\Message\Payments\Item\Currency**.</span><span class="sxs-lookup"><span data-stu-id="f308b-224">In the tree, select **Xml\Message\Payments\Item\Currency**.</span></span>
34. <span data-ttu-id="f308b-225">Klicka på **Lägg till sträng**.</span><span class="sxs-lookup"><span data-stu-id="f308b-225">Click **Add String**.</span></span>
35. <span data-ttu-id="f308b-226">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="f308b-226">Click **OK**.</span></span>
36. <span data-ttu-id="f308b-227">I trädet välj **Xml\Message\Payments\Item\Description**.</span><span class="sxs-lookup"><span data-stu-id="f308b-227">In the tree, select **Xml\Message\Payments\Item\Description**.</span></span>
37. <span data-ttu-id="f308b-228">Klicka på **Lägg till sträng**.</span><span class="sxs-lookup"><span data-stu-id="f308b-228">Click **Add String**.</span></span>
38. <span data-ttu-id="f308b-229">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="f308b-229">Click **OK**.</span></span>
39. <span data-ttu-id="f308b-230">I trädet välj **Xml\Message\Payments\Item\Amount**.</span><span class="sxs-lookup"><span data-stu-id="f308b-230">In the tree, select **Xml\Message\Payments\Item\Amount**.</span></span>
40. <span data-ttu-id="f308b-231">Klicka på **Lägg till sträng**.</span><span class="sxs-lookup"><span data-stu-id="f308b-231">Click **Add String**.</span></span>
41. <span data-ttu-id="f308b-232">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="f308b-232">Click **OK**.</span></span>
42. <span data-ttu-id="f308b-233">Klicka på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="f308b-233">Click **Save**.</span></span>
43. <span data-ttu-id="f308b-234">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="f308b-234">Close the page.</span></span>



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]