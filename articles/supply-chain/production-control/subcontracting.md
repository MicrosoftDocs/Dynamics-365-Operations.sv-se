---
title: Legotillverkning
description: "I det här avsnittet hjälper dig att skapa en genomgång av den legotillverkning i produktionen i Microsoft Dynamics 365 for Finance and Operations."
author: christophernread
manager: AnnBe
ms.date: 09/28/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: 
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2018-09-30
ms.dyn365.ops.version: 
ms.translationtype: HT
ms.sourcegitcommit: ade3f4ad9878c9e885afc5034334e41897512871
ms.openlocfilehash: 55b516f928eadea9b7ddbb1192db79f3ab7fa204
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2018

---

# <a name="subcontracting"></a><span data-ttu-id="804d9-103">Legotillverkning</span><span class="sxs-lookup"><span data-stu-id="804d9-103">Subcontracting</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="804d9-104">I det här avsnittet hjälper dig att skapa en genomgång av den legotillverkning i produktionen i Microsoft Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="804d9-104">This topic will help you build a walkthrough of subcontracting in manufacturing in Microsoft Dynamics 365 for Finance and Operations.</span></span> <span data-ttu-id="804d9-105">Den första delen av det här avsnittet beskriver inställningen av data.</span><span class="sxs-lookup"><span data-stu-id="804d9-105">The first part of this topic describes the setup of the data.</span></span> <span data-ttu-id="804d9-106">Den andra delen tar dig igenom stegen i genomgången.</span><span class="sxs-lookup"><span data-stu-id="804d9-106">The second part takes you through the steps in the walkthrough.</span></span>

## <a name="target-audience"></a><span data-ttu-id="804d9-107">Målgrupp</span><span class="sxs-lookup"><span data-stu-id="804d9-107">Target audience</span></span>

<span data-ttu-id="804d9-108">I det här avsnittet får du lära dig hur du ställer in den legotillverkning i produktionen.</span><span class="sxs-lookup"><span data-stu-id="804d9-108">In this topic, you will learn how to set up subcontracting in manufacturing.</span></span> <span data-ttu-id="804d9-109">Du kommer att använda befintliga data i den juridiska personen HQUS för att göra grundinställningen av ett flöde för legotillverkningsaktiviteten.</span><span class="sxs-lookup"><span data-stu-id="804d9-109">You will use existing data in the HQUS legal entity to do the basic setup of a subcontracting activity flow.</span></span> <span data-ttu-id="804d9-110">Demodata hos den juridiska personen HQUS inkluderar inställningsparametrar som har blivit förinställda för att ge stöd till stegen i genomgången.</span><span class="sxs-lookup"><span data-stu-id="804d9-110">The demo data in the HQUS legal entity includes setup parameters that have been preset to support the steps in the walkthrough.</span></span> <span data-ttu-id="804d9-111">Trots att genomgången behandlar viktiga sårbarheter och utmaningar för olika roller kan den kompletteras av systemadministratören.</span><span class="sxs-lookup"><span data-stu-id="804d9-111">Even though the walkthrough addresses key pain points and challenges for various roles, it can be completed by the system admin.</span></span>

## <a name="demo-scenario"></a><span data-ttu-id="804d9-112">Demonstrationsscenario</span><span class="sxs-lookup"><span data-stu-id="804d9-112">Demo scenario</span></span>

<span data-ttu-id="804d9-113">Avancerade högtalare tillverkas i den juridiska personen HQUS.</span><span class="sxs-lookup"><span data-stu-id="804d9-113">In the HQUS legal entity, high-end speakers are manufactured.</span></span> <span data-ttu-id="804d9-114">Under tillverkningsprocessen går högtalare igenom följande tre åtgärder.</span><span class="sxs-lookup"><span data-stu-id="804d9-114">During the manufacturing process, speakers go through the following three operations.</span></span>

- <span data-ttu-id="804d9-115">**Förmontering** - Högtalarkabinetten monteras.</span><span class="sxs-lookup"><span data-stu-id="804d9-115">**Pre-assembly** – The speaker cabinet is assembled.</span></span> <span data-ttu-id="804d9-116">Materialet för kabinetten plockas på lagerstället för material innan operationen startas.</span><span class="sxs-lookup"><span data-stu-id="804d9-116">The material for the cabinet is picked in the material warehouse before the operation is started.</span></span>
- <span data-ttu-id="804d9-117">**Beläggning** – När högtalarkabinetten har monterats måste den beläggas.</span><span class="sxs-lookup"><span data-stu-id="804d9-117">**Coating** – After the speaker cabinet has been assembled, it must be coated.</span></span> <span data-ttu-id="804d9-118">Åtgärden slutförs av en leverantör (underleverantör).</span><span class="sxs-lookup"><span data-stu-id="804d9-118">This operation is completed by a vendor (subcontractor).</span></span> <span data-ttu-id="804d9-119">Den förmonterade högtalarkabinetten levereras till underleverantören för beläggning tillsammans med två material.</span><span class="sxs-lookup"><span data-stu-id="804d9-119">The pre-assembled speaker cabinet is shipped to the coating subcontractor together with two materials.</span></span>
- <span data-ttu-id="804d9-120">**Ytbehandling** – När den förmonterade högtalarkabinetten är belagd av underleverantören returneras den till den juridiska personen HQUS så att slutmonteringen av högtalaren kan slutföras.</span><span class="sxs-lookup"><span data-stu-id="804d9-120">**Finish** – After the pre-assembled speaker cabinet has been coated by the subcontractor, it's returned to the HQUS legal entity so that final assembly of the speaker can be completed.</span></span>

<span data-ttu-id="804d9-121">Följande bild visar de tre operationerna och materialet som de använder.</span><span class="sxs-lookup"><span data-stu-id="804d9-121">The following illustration shows the three operations and the materials that they consume.</span></span>

![Operationerna förmontering, beläggning, ytbehandling och materialet som de förbrukar](./media/subcontract01_operations-materials.png)

## <a name="setup"></a><span data-ttu-id="804d9-123">Konfigurera</span><span class="sxs-lookup"><span data-stu-id="804d9-123">Setup</span></span>

<span data-ttu-id="804d9-124">Innan du påbörjar genomgången måste du ställa in data.</span><span class="sxs-lookup"><span data-stu-id="804d9-124">Before you start the walkthrough, you must set up the data.</span></span>

### <a name="set-up-the-finished-product"></a><span data-ttu-id="804d9-125">Ställ in den färdiga produkten</span><span class="sxs-lookup"><span data-stu-id="804d9-125">Set up the finished product</span></span>

<span data-ttu-id="804d9-126">Den här proceduren hjälper dig genom inställningarna för frisläppt produkt D8100, ”Belagd kabinett”.</span><span class="sxs-lookup"><span data-stu-id="804d9-126">This procedure takes you through the setup of released product D8100, "Coated Cabinet."</span></span>

1. <span data-ttu-id="804d9-127">Välj **produktinformationshantering \> produkter \> frisläppta produkter** för att öppna sidan **Information om frisläppt produkt**.</span><span class="sxs-lookup"><span data-stu-id="804d9-127">Select **Product information management \> Products \> Released products** to open the **Released product details** page.</span></span>
2. <span data-ttu-id="804d9-128">I snabbfilterfältet anger du **D8100** för att söka efter befintlig frisläppt produkt.</span><span class="sxs-lookup"><span data-stu-id="804d9-128">In the quick filter field, enter **D8100** to find the existing released product.</span></span>

    ![Filtrering för frisläppt produkt D8100 på informationssidan för frisläppt produkt](./media/subcontract02_filtering-released-products.png)

3. <span data-ttu-id="804d9-130">I åtgärdsfönstret, på fliken **tekniker**, välj **flöde** för att öppna sidan **flöde**.</span><span class="sxs-lookup"><span data-stu-id="804d9-130">On the Action Pane, on the **Engineer** tab, select **Route** to open the **Route** page.</span></span>

    <span data-ttu-id="804d9-131">Sidan **Flöde** visar de åtta flödesversioner för frisläppt produkt D8100.</span><span class="sxs-lookup"><span data-stu-id="804d9-131">The **Route** page shows the eight route versions for released product D8100.</span></span> <span data-ttu-id="804d9-132">Åtta flödesversioner ska delas upp mellan fyra flöden på site 1 och 5.</span><span class="sxs-lookup"><span data-stu-id="804d9-132">The eight route versions are divided among four routes on site 1 and site 5.</span></span> <span data-ttu-id="804d9-133">Flöde 000400 används för kostnadsredovisning, flöde 00041 används när beläggningsoperationen är en intern operation, och flöde 00042 används när beläggningsoperationen är en extern operation.</span><span class="sxs-lookup"><span data-stu-id="804d9-133">Route 000400 is used for costing, route 00041 is used when the Coating operation is an internal operation, and route 00042 is used when the Coating operation is an external operation.</span></span>

    ![Åtta flödesversioner på sidan Flöde](./media/subcontract03_route-page.png)

4. <span data-ttu-id="804d9-135">I det övre fönstret i rutnätet **versioner**, välj flödesversion **00042** för site **5**.</span><span class="sxs-lookup"><span data-stu-id="804d9-135">In the upper pane, in the **Versions** grid, select route version **00042** for site **5**.</span></span>
5. <span data-ttu-id="804d9-136">I det nedre fönstret på fliken **översikt**, välj operation **20** (**Cbnt CtSc**) i rutnätet.</span><span class="sxs-lookup"><span data-stu-id="804d9-136">In the lower pane, on the **Overview** tab, select operation **20** (**Cbnt CtSc**) in the grid.</span></span>

    ![Operation 20 flödesversionen 00042 för site 5 markerad](./media/subcontract04_route-version-operation.png)

6. <span data-ttu-id="804d9-138">Välj fliken **Allmänt**.</span><span class="sxs-lookup"><span data-stu-id="804d9-138">Select the **General** tab.</span></span>

    <span data-ttu-id="804d9-139">Lägg märke till att fältet **flödestyp** har tilldelats **leverantör**.</span><span class="sxs-lookup"><span data-stu-id="804d9-139">Notice that the field **Route type** field is set to **Vendor**.</span></span> <span data-ttu-id="804d9-140">Detta värde anger att operation 20 (Cbnt CtSc) är en legotillverkningsoperation.</span><span class="sxs-lookup"><span data-stu-id="804d9-140">This value indicates that operation 20 (Cbnt CtSc) is a subcontracted operation.</span></span>

    ![Fältet Flödestyp anges till Leverantör på fliken Allmänt](./media/subcontract05_general-tab.png)

7. <span data-ttu-id="804d9-142">Välj fliken **Resurskrav**.</span><span class="sxs-lookup"><span data-stu-id="804d9-142">Select the **Resource requirements** tab.</span></span>

    <span data-ttu-id="804d9-143">Funktioner används för att hitta en tillämplig resurs vid produktionsplaneringen.</span><span class="sxs-lookup"><span data-stu-id="804d9-143">Capabilities will be used to find an applicable resource during production scheduling.</span></span> <span data-ttu-id="804d9-144">Observera att för operation 20 (Cbnt CtSc) krävs en resurs som har två funktioner **beläggning** och **belagd kabinett**.</span><span class="sxs-lookup"><span data-stu-id="804d9-144">For operation 20 (Cbnt CtSc), notice that a resource that has two capabilities, **Coating** and **Coated cabinets**, is required.</span></span>

    ![Kapacitet för beläggning och belagda kabinett på fliken resursbehov](./media/subcontract06_resource-requirements-tab.png)

8. <span data-ttu-id="804d9-146">Välj **tillämpliga resurser** för att öppna dialogrutan **tillämpliga resurser**.</span><span class="sxs-lookup"><span data-stu-id="804d9-146">Select **Applicable resources** to open the **Applicable resources** dialog box.</span></span>

    <span data-ttu-id="804d9-147">Tre resurser hittas som matchar operationens resursbehov.</span><span class="sxs-lookup"><span data-stu-id="804d9-147">Three resources are found that match the resource requirements for the operation.</span></span> <span data-ttu-id="804d9-148">Lägg märke till att 8851 och 8852 är av typen **leverantör**.</span><span class="sxs-lookup"><span data-stu-id="804d9-148">Notice that resources 8851 and 8852 are of the **Vendor** type.</span></span>

    ![Tre tillämpliga resurser i dialogrutan tillämpliga resurser.](./media/subcontract07_applicable-resources-dialog.png)

9. <span data-ttu-id="804d9-150">Välj **OK** för att stänga dialogrutan **tillämpliga resurser** och återgå till sidan **flöde**.</span><span class="sxs-lookup"><span data-stu-id="804d9-150">Select **OK** to close the **Applicable resources** dialog box and return to the **Route** page.</span></span>
10. <span data-ttu-id="804d9-151">Stäng sidan **flöde** om du vill återgå till sidan **Information om frisläppt produkt**.</span><span class="sxs-lookup"><span data-stu-id="804d9-151">Close the **Route** page to return to the **Released product details** page.</span></span>

    ![Sidan Information om frisläppt produkt](./media/subcontract08_released-product-details-page.png)

11. <span data-ttu-id="804d9-153">I åtgärdsfönstret, på fliken **tekniker**, välj **strukturlisteversioner** för att öppna sidan **strukturlisteversioner**.</span><span class="sxs-lookup"><span data-stu-id="804d9-153">On the Action Pane, on the **Engineer** tab, select **BOM versions** to open the **BOM versions** page.</span></span>

    <span data-ttu-id="804d9-154">Sidan **strukturlisteversioner** visar fyra strukturlisteversioner för frisläppt produkt D8100.</span><span class="sxs-lookup"><span data-stu-id="804d9-154">The **BOM versions** page shows the four bill of materials (BOM) versions for released product D8100.</span></span> <span data-ttu-id="804d9-155">Strukturlistan 000040 används för kostnadsredovisning och planering, strukturlistan 000041 används om operationen beläggning görs inom företaget, strukturlistan och 000042 och 000043 används om beläggningsoperationen gäller legotillverkning.</span><span class="sxs-lookup"><span data-stu-id="804d9-155">BOM 000040 is used for costing and planning, BOM 000041 is used if the Coating operation is done in-house, and BOMs 000042 and 000043 are used if the Coating operation is subcontracted.</span></span>

    <span data-ttu-id="804d9-156">Observera att artikel S8050 är en produkt av artikeltypen **Tjänst**.</span><span class="sxs-lookup"><span data-stu-id="804d9-156">Notice that item S8050 is a product of the **Service** item type.</span></span> <span data-ttu-id="804d9-157">Den här artikeln representerar legotillverkning.</span><span class="sxs-lookup"><span data-stu-id="804d9-157">This item represents the subcontracted work.</span></span>

    ![Fyra strukturlisteversioner på sidan strukturlisteversioner](./media/subcontract09_bom-versions-page.png)

12. <span data-ttu-id="804d9-159">På snabbfliken **strukturlisterader**, välj **redigera** för att öppna dialogrutan **Redigera strukturlisterad**.</span><span class="sxs-lookup"><span data-stu-id="804d9-159">On the **Bill of materials lines** FastTab, select **Edit** to open the **Edit BOM line** dialog box.</span></span>

    <span data-ttu-id="804d9-160">När en produktionsorder har skapats och uppskattats för frisläppt produkt D8100, genereras en inköpsorder automatiskt för artikel S8050.</span><span class="sxs-lookup"><span data-stu-id="804d9-160">When a production order is created and estimated for released product D8100, a purchase order will be automatically generated for item S8050.</span></span> <span data-ttu-id="804d9-161">Denna inköpsorder ska kopplas till produktionsordern.</span><span class="sxs-lookup"><span data-stu-id="804d9-161">This purchase order will be linked to the production order.</span></span> <span data-ttu-id="804d9-162">För att inköpsorder ska skapas automatiskt måste fältet **Radtyp** ställas in på **leverantör**, och du måste välja leverantörskontot för underleverantören.</span><span class="sxs-lookup"><span data-stu-id="804d9-162">For purchase orders to be automatically generated, the **Line type** field must be set to **Vendor**, and the vendor account for the subcontractor must be selected.</span></span> <span data-ttu-id="804d9-163">I det här fallet är leverantörskontot US-801.</span><span class="sxs-lookup"><span data-stu-id="804d9-163">In this case, the vendor account is US-801.</span></span>

    <span data-ttu-id="804d9-164">Observera att strukturlisteraden är ansluten till beläggningsoperationen genom operationsnummer (i vårt exempel 20).</span><span class="sxs-lookup"><span data-stu-id="804d9-164">Notice that the BOM line is connected to the Coating operation through the operation number (in this case, 20).</span></span>

    ![Redigera dialogrutan Strukturlista](./media/subcontract10_edit-bom-line-dialog.png)

### <a name="create-a-password-for-warehouse-workers"></a><span data-ttu-id="804d9-166">Skapa ett lösenord för lagerarbetare</span><span class="sxs-lookup"><span data-stu-id="804d9-166">Create a password for warehouse workers</span></span>

<span data-ttu-id="804d9-167">Du måste definiera ett lösenord för lagerarbetare som använder den bärbara enheten.</span><span class="sxs-lookup"><span data-stu-id="804d9-167">You must define a password for the warehouse workers who use the hand-held device.</span></span>

1. <span data-ttu-id="804d9-168">Välj **lagerstyrning \> inställningar \> arbetare** för att öppna sidan **Arbetsanvändare**.</span><span class="sxs-lookup"><span data-stu-id="804d9-168">Select **Warehouse management \> Setup \> Worker** to open the **Work users** page.</span></span>
2. <span data-ttu-id="804d9-169">På snabbfliken **användare**, markerar du raden för användaren **51**.</span><span class="sxs-lookup"><span data-stu-id="804d9-169">On the **Users** FastTab, select the row for user **51**.</span></span>

    ![Sidan arbetsanvändare](./media/subcontract11_work-users-page.png)

3. <span data-ttu-id="804d9-171">Välj **Återställ lösenord**.</span><span class="sxs-lookup"><span data-stu-id="804d9-171">Select **Reset password**.</span></span>
4. <span data-ttu-id="804d9-172">I fältet **Lösenord** och **Bekräfta lösenord** ange **1**.</span><span class="sxs-lookup"><span data-stu-id="804d9-172">In the **Password** and **Confirm password** fields, enter **1**.</span></span>
5. <span data-ttu-id="804d9-173">Välj **Ange lösenord**.</span><span class="sxs-lookup"><span data-stu-id="804d9-173">Select **Set password**.</span></span>

## <a name="step-by-step-walkthrough"></a><span data-ttu-id="804d9-174">Stegvis genomgång</span><span class="sxs-lookup"><span data-stu-id="804d9-174">Step-by-step walkthrough</span></span>

<span data-ttu-id="804d9-175">**Scenario och bakgrund**</span><span class="sxs-lookup"><span data-stu-id="804d9-175">**Scenario and background**</span></span>

<span data-ttu-id="804d9-176">En produktionsorder på 10 enheter skapas för produkten D8100, ”belagd kabinett”.</span><span class="sxs-lookup"><span data-stu-id="804d9-176">A production order of 10 pieces is created for product D8100, "Coated Cabinet."</span></span> <span data-ttu-id="804d9-177">Beläggning av kabinetter är en legotillverkningsoperation som utförs av leverantör US-801 Perfect Coating Solutions.</span><span class="sxs-lookup"><span data-stu-id="804d9-177">The coating of the cabinets is a sub-contracted operation that is done at vendor US-801, Perfect Coating Solutions.</span></span> <span data-ttu-id="804d9-178">Tillverkningsordern består av tre operationer.</span><span class="sxs-lookup"><span data-stu-id="804d9-178">The production order consists of three operations.</span></span> <span data-ttu-id="804d9-179">I den första operationen sammansätts kabinetten i förväg som en intern operation.</span><span class="sxs-lookup"><span data-stu-id="804d9-179">In the first operation, the cabinet is pre-assembled as an in-house operation.</span></span> <span data-ttu-id="804d9-180">Materialet för förmonteringen har frisläppts för plockning i råmateriallagret.</span><span class="sxs-lookup"><span data-stu-id="804d9-180">The material for the pre-assembly is released for picking in the raw material warehouse.</span></span> <span data-ttu-id="804d9-181">När förmonteringen har slutförts skickas den förmonterade kabinetten till Perfect Coating Solutions tillsammans med två material som krävs för beläggningsoperationen.</span><span class="sxs-lookup"><span data-stu-id="804d9-181">After the pre-assembly is completed, the pre-assembled cabinet is sent to Perfect Coating Solutions together with two materials that are required for the Coating operation.</span></span> <span data-ttu-id="804d9-182">När den belagda kabinetten tas emot från säljaren går den igenom en slutlig montering på plats innan den rapporteras som färdig.</span><span class="sxs-lookup"><span data-stu-id="804d9-182">When the coated cabinet is received back from the vendor, it goes through a final in-house assembly operation before it's reported as finished.</span></span>

1. <span data-ttu-id="804d9-183">Välj **produktionskontroll \> produktionsorder \> alla produktionsorder** för att öppna sidan **alla produktionsorder**.</span><span class="sxs-lookup"><span data-stu-id="804d9-183">Select **Production control \> Production orders \> All production orders** to open the **All production orders** page.</span></span>
2. <span data-ttu-id="804d9-184">I åtgärdsfönstret, välj **ny produktionsorder** för att öppna dialogrutan **skapa produktionsorder**.</span><span class="sxs-lookup"><span data-stu-id="804d9-184">On the Action Pane, select **New production order** to open the **Create production order** dialog box.</span></span>

    ![Dialogrutan Skapa produktionsorder](./media/subcontract12_create-production-order-dialog.png)

3. <span data-ttu-id="804d9-186">I fältet **Artikelnummer**, välj **D8100**.</span><span class="sxs-lookup"><span data-stu-id="804d9-186">In the **Item number** field, select **D8100**.</span></span>
4. <span data-ttu-id="804d9-187">När du har valt artikelnumret visas fälten för inventeringsdimensionerna.</span><span class="sxs-lookup"><span data-stu-id="804d9-187">After you select the item number, fields for the inventory dimensions appear.</span></span> <span data-ttu-id="804d9-188">I fältet **Färg**, välj **Chrome**.</span><span class="sxs-lookup"><span data-stu-id="804d9-188">In the **Color** field, select **Chrome**.</span></span>

    <span data-ttu-id="804d9-189">Ett meddelande visas som frågar om du vill infoga aktiva versioner för strukturlista och flöde.</span><span class="sxs-lookup"><span data-stu-id="804d9-189">A message box appears that asks whether the active versions for the BOM and route should be inserted.</span></span>

    ![Meddelanderuta](./media/subcontract13_message-box.png)

5. <span data-ttu-id="804d9-191">Välj **Ja**.</span><span class="sxs-lookup"><span data-stu-id="804d9-191">Select **Yes**.</span></span> 

    <span data-ttu-id="804d9-192">I dialogrutan **skapa produktionsorder** väljs de aktiva versionerna av strukturlistan och flödet för produkten D8100 automatiskt i fälten **Strukturlistenummer** och **Flödesnummer**.</span><span class="sxs-lookup"><span data-stu-id="804d9-192">In the **Create production order** dialog box, the active versions of the BOM and route for product D8100 are automatically selected in the **BOM number** and **Route number** fields, respectively.</span></span> <span data-ttu-id="804d9-193">I det här fallet väljs strukturlista **000040** och **000040**.</span><span class="sxs-lookup"><span data-stu-id="804d9-193">In this case, BOM **000040** and route **000040** are selected.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="804d9-194">För både strukturlista och flöde används version 000040 för kostnadsberäkning och planering.</span><span class="sxs-lookup"><span data-stu-id="804d9-194">For both the BOM and the route, version 000040 is used for costing and planning.</span></span>

6. <span data-ttu-id="804d9-195">I fltet **Site**, välj **5**.</span><span class="sxs-lookup"><span data-stu-id="804d9-195">In the **Site** field, select **5**.</span></span>
7. <span data-ttu-id="804d9-196">I fältet **Lagerställe**, välj **51**.</span><span class="sxs-lookup"><span data-stu-id="804d9-196">In the **Warehouse** field, select **51**.</span></span>
8. <span data-ttu-id="804d9-197">I **Strukturlistenummer** och **Flödesnummer**, ändra värdet som valdes automatiskt till **000042**.</span><span class="sxs-lookup"><span data-stu-id="804d9-197">In the **BOM number** and **Route number** fields, change the value that was automatically selected to **000042**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="804d9-198">För både strukturlistan och flödet används version 000042 för att underleverera beläggningen av kabinetten till leverantör US-801.</span><span class="sxs-lookup"><span data-stu-id="804d9-198">For both the BOM and the route, version 000042 is used to subcontract the coating of the cabinet to vendor US-801.</span></span>

    ![Värdena som anges i dialogrutan Skapa produktionsorder](./media/subcontract14_create-production-order-dialog-set.png)

9. <span data-ttu-id="804d9-200">Välj **Skapa** för att skapa produktionsordern och återgå till sidan **alla produktionsorder**.</span><span class="sxs-lookup"><span data-stu-id="804d9-200">Select **Create** to create the production order and return to the **All production orders** page.</span></span>

    ![Ny produktionsorder på sidan Alla produktionsorder](./media/subcontract15_new-production-order.png)

10. <span data-ttu-id="804d9-202">I åtgärdsfönstret, på fliken **produktionsorder**, välj **Beräkna** för att öppna dialogrutan **Beräkna**.</span><span class="sxs-lookup"><span data-stu-id="804d9-202">On the Action Pane, on the **Production order** tab, select **Estimate** to open the **Estimate** dialog box.</span></span>

    ![Dialogrutan Beräkna](./media/subcontract16_estimate-dialog.png)

11. <span data-ttu-id="804d9-204">Välj **OK** för att bekräfta beräkningen och återgå till sidan **alla produktionsorder**.</span><span class="sxs-lookup"><span data-stu-id="804d9-204">Select **OK** to confirm the estimate and return to the **All production orders** page.</span></span>

    > [!NOTE]
    > <span data-ttu-id="804d9-205">När produktionsorder beräknas genereras inköpsorder S8050 för leverantör US-801.</span><span class="sxs-lookup"><span data-stu-id="804d9-205">When the production order is estimated, the purchase order for service item S8050 is generated for vendor US-801.</span></span>

12. <span data-ttu-id="804d9-206">I åtgärdsfönstret, på fliken **tillverkningsorder** väljer du **Strukturlista** för att öppna sidan **Strukturlista** där du kan visa strukturlisterader för tillverkningsordern.</span><span class="sxs-lookup"><span data-stu-id="804d9-206">On the Action Pane, on the **Production order** tab, select **BOM** to open the **BOM** page, where you can view the BOM lines for the production order.</span></span>

    <span data-ttu-id="804d9-207">För serviceartikel S8050 märker du att det finns en hänvisning till inköpsordern som genererades när produktionsordern beräknades.</span><span class="sxs-lookup"><span data-stu-id="804d9-207">For service item S8050, notice that there is a reference to the purchase order that was generated when the production order was estimated.</span></span>

    ![Produktionsorders strukturrader på sidan Strukturlista](./media/subcontract17_production-order-bom-lines.png)

13. <span data-ttu-id="804d9-209">Stäng sidan **Strukturlista** om du vill återgå till sidan **alla produktionsorder**.</span><span class="sxs-lookup"><span data-stu-id="804d9-209">Close the **BOM** page to return to the **All production orders** page.</span></span>
14. <span data-ttu-id="804d9-210">I åtgärdsfönstret, på fliken **Tidsplan**, välj **Tidsplanera jobb** för att öppna dialogrutan **Finplanering**.</span><span class="sxs-lookup"><span data-stu-id="804d9-210">On the Action Pane, on the **Schedule** tab, select **Schedule jobs** to open the **Job scheduling** dialog box.</span></span>
15. <span data-ttu-id="804d9-211">Ange följande värden.</span><span class="sxs-lookup"><span data-stu-id="804d9-211">Specify the following values:</span></span>

    - <span data-ttu-id="804d9-212">I fältet **Planeringsriktning**, välj **Framåt från imorgon**.</span><span class="sxs-lookup"><span data-stu-id="804d9-212">In the **Scheduling direction** field, select **Forward from tomorrow**.</span></span>
    - <span data-ttu-id="804d9-213">Ange alternativet **begränsad kapacitet** till **Ja**.</span><span class="sxs-lookup"><span data-stu-id="804d9-213">Set the **Finite capacity** option to **Yes**.</span></span>

    ![Dialogrutan Finplanera](./media/subcontract18_job-scheduling-dialog.png)

16. <span data-ttu-id="804d9-215">Välj **OK** för att stänga dialogrutan **finplanering** och återgå till sidan **alla produktionsorder**.</span><span class="sxs-lookup"><span data-stu-id="804d9-215">Select **OK** to close the **Job scheduling** dialog box and return to the **All production orders** page.</span></span>
17. <span data-ttu-id="804d9-216">I åtgärdsfönstret, på fliken **Tidsplan**, välj **Gantt** för att öppna sidan **Gantt-schema - Resursvy**.</span><span class="sxs-lookup"><span data-stu-id="804d9-216">On the Action Pane, on the **Schedule** tab, select **Gantt** to open the **Gantt chart - Resource view** page.</span></span>

    <span data-ttu-id="804d9-217">Gantt-schemat ger en visuell översikt av hur produktionsjobben tidplaneras på resurser.</span><span class="sxs-lookup"><span data-stu-id="804d9-217">The Gantt chart provides a visual overview of how the production jobs are scheduled on the resources.</span></span> <span data-ttu-id="804d9-218">Observera att den externa beläggningsoperationen består av tre jobb: ett processjobb, ett transportjobb och ett kötidjobb.</span><span class="sxs-lookup"><span data-stu-id="804d9-218">Notice that the external Coating operation consists of three jobs: a process job, a transport job, and a queue time job.</span></span>

    ![Gantt-schema i Gantt-schemat - Sida för resursvy](./media/subcontract19_gantt-chart.png)

18. <span data-ttu-id="804d9-220">Stäng sidan **Gantt.schema - Resursvy** om du vill återgå till sidan **alla produktionsorder**.</span><span class="sxs-lookup"><span data-stu-id="804d9-220">Close the **Gantt chart - Resource view** page to return to the **All production orders** page.</span></span>
19. <span data-ttu-id="804d9-221">I åtgärdsfönstret, på fliken **produktionsorder**, välj **Frisläpp** för att öppna dialogrutan **Frisläpp**.</span><span class="sxs-lookup"><span data-stu-id="804d9-221">On the Action Pane, on the **Production order** tab, select **Release** to open the **Release** dialog box.</span></span>

    ![Dialogrutan Frisläpp](./media/subcontract20_release-dialog.png)

20. <span data-ttu-id="804d9-223">Välj **OK** för att stänga dialogrutan **Frisläpp**.</span><span class="sxs-lookup"><span data-stu-id="804d9-223">Select **OK** to close the **Release** dialog box.</span></span>
21. <span data-ttu-id="804d9-224">Välj **produktionskontroll \> periodiska uppgifter \> frisläpp till lagerställe \> Automatisk frisläppning av strukturliste- och receptrader** för att öppna dialogrutan **Automatisk frisläppning av strukturliste- och receptrader**.</span><span class="sxs-lookup"><span data-stu-id="804d9-224">Select **Production control \> Periodic tasks \> Release to warehouse \> Automatic release of BOM and formula lines** to open the **Automatic release of BOM and formula lines** dialog box.</span></span>

    ![Dialogrutan Automatisk frisläppning av strukturliste- och receptrader](./media/subcontract21_auto-release-bom-formula-lines-dialog.png)

22. <span data-ttu-id="804d9-226">Välj **OK** för att köra automatiskt frisläppning av strukturliste- och receptradjobb.</span><span class="sxs-lookup"><span data-stu-id="804d9-226">Select **OK** to run the Automatic release of BOM and formula lines job.</span></span>

    <span data-ttu-id="804d9-227">Det här jobbet frisläpper plockningsarbete av råmaterial till lagret.</span><span class="sxs-lookup"><span data-stu-id="804d9-227">This job releases pick work for raw materials to the warehouse.</span></span>

23. <span data-ttu-id="804d9-228">Välj **produktionskontroll \> produktionsorder \> alla produktionsorder** för att öppna sidan **alla produktionsorder**.</span><span class="sxs-lookup"><span data-stu-id="804d9-228">Select **Production control \> Production orders \> All production orders** to open the **All production orders** page.</span></span>
24. <span data-ttu-id="804d9-229">Använd fältet för snabbfilter för att välja den tillverkningsorder som du har arbetat med.</span><span class="sxs-lookup"><span data-stu-id="804d9-229">Use the quick filter field to select the production order that you've been working on.</span></span>
25. <span data-ttu-id="804d9-230">I åtgärdsfönstret, på fliken **Lagerställe**, välj **Information om arbete** för att öppna sidan **Arbete**.</span><span class="sxs-lookup"><span data-stu-id="804d9-230">On the Action Pane, on the **Warehouse** tab, select **Work details** to open the **Work** page.</span></span>

    <span data-ttu-id="804d9-231">Observera att sidan visar två uppsättningar arbete för råmaterialplockning.</span><span class="sxs-lookup"><span data-stu-id="804d9-231">Notice that the page shows two sets of work for raw material picking.</span></span> <span data-ttu-id="804d9-232">Första arbetet är för material M8100 och M8101.</span><span class="sxs-lookup"><span data-stu-id="804d9-232">The first work is for materials M8100 and M8101.</span></span> <span data-ttu-id="804d9-233">Dessa material som förbrukas av operation 10.</span><span class="sxs-lookup"><span data-stu-id="804d9-233">These materials are consumed by operation 10.</span></span> <span data-ttu-id="804d9-234">Det andra arbetet är för material M8202 och M8250.</span><span class="sxs-lookup"><span data-stu-id="804d9-234">The second work is for materials M8202 and M8250.</span></span> <span data-ttu-id="804d9-235">Dessa material förbrukas av operation 20, d.v.s. legotillverkningsoperationen.</span><span class="sxs-lookup"><span data-stu-id="804d9-235">These materials are consumed by operation 20, which is the subcontracted operation.</span></span>

    ![Två uppsättningar arbete för råmaterialplockning på sidan Arbete.](./media/subcontract22_work-page.png)

26. <span data-ttu-id="804d9-237">Starta lagerställeappen för att bearbeta lagerställearbetet för operation 10.</span><span class="sxs-lookup"><span data-stu-id="804d9-237">Start the warehouse app to process the warehouse work for operation 10.</span></span>

    <!-- TBD – screen shots for processing pick work for the materials. -->

27. <span data-ttu-id="804d9-238">Välj **produktionskontroll \> produktionsorder \> alla produktionsorder** för att öppna sidan **alla produktionsorder**.</span><span class="sxs-lookup"><span data-stu-id="804d9-238">Select **Production control \> Production orders \> All production orders** to open the **All production orders** page.</span></span>
28. <span data-ttu-id="804d9-239">Använd fältet för snabbfilter för att välja den tillverkningsorder som du har arbetat med.</span><span class="sxs-lookup"><span data-stu-id="804d9-239">Use the quick filter field to select the production order that you've been working on.</span></span>
29. <span data-ttu-id="804d9-240">I åtgärdsfönstret, på fliken **produktionsorder**, välj **Starta** för att öppna dialogrutan **Starta**.</span><span class="sxs-lookup"><span data-stu-id="804d9-240">On the Action Pane, on the **Production order** tab, select **Start** to open the **Start** dialog box.</span></span>
30. <span data-ttu-id="804d9-241">På fliken **Allmänt**, fyll i följande värden:</span><span class="sxs-lookup"><span data-stu-id="804d9-241">On the **General** tab, specify the following values:</span></span>

    - <span data-ttu-id="804d9-242">I fältet **Från oper.nr.**</span><span class="sxs-lookup"><span data-stu-id="804d9-242">In the **From Oper. No.**</span></span> <span data-ttu-id="804d9-243">välj **10**.</span><span class="sxs-lookup"><span data-stu-id="804d9-243">field, select **10**.</span></span>
    - <span data-ttu-id="804d9-244">I fältet **Till oper.nr.**</span><span class="sxs-lookup"><span data-stu-id="804d9-244">In the **To Oper. No.**</span></span> <span data-ttu-id="804d9-245">välj **10**.</span><span class="sxs-lookup"><span data-stu-id="804d9-245">field, select **10**.</span></span>

    ![Värden som har angetts på fliken Allmänt](./media/subcontract23_start-dialog.png)

31. <span data-ttu-id="804d9-247">Välj **OK** för att stänga dialogrutan **Starta** och återgå till sidan **alla produktionsorder**.</span><span class="sxs-lookup"><span data-stu-id="804d9-247">Select **OK** to close the **Start** dialog box and return to the **All production orders** page.</span></span>

    <span data-ttu-id="804d9-248">Observera att statusen för produktionsordern nu är **startad**.</span><span class="sxs-lookup"><span data-stu-id="804d9-248">Notice that the status of the production order is now **Started**.</span></span> <span data-ttu-id="804d9-249">Materialen för en operation 10 förbrukas av en automatisk bokföring av plocklistejournalen.</span><span class="sxs-lookup"><span data-stu-id="804d9-249">The materials for operation 10 are consumed by an automatic posting of the picking list journal.</span></span> <span data-ttu-id="804d9-250">Tidsförbrukning för operationen 10 redovisas enligt en automatisk bokföring av en flödeskortjournal.</span><span class="sxs-lookup"><span data-stu-id="804d9-250">Time consumption for operation 10 is accounted for by an automatic posting of a route card journal.</span></span>

32. <span data-ttu-id="804d9-251">Starta lagerställeappen för att bearbeta lagerställearbetet för operation 20.</span><span class="sxs-lookup"><span data-stu-id="804d9-251">Start the warehouse app to process the warehouse work for operation 20.</span></span>

    <!-- TBD – screen shots for processing pick work for the materials. -->

33. <span data-ttu-id="804d9-252">I åtgärdsfönstret, på fliken **produktionsorder**, välj **Starta** för att öppna dialogrutan **Starta**.</span><span class="sxs-lookup"><span data-stu-id="804d9-252">On the Action Pane, on the **Production order** tab, select **Start** to open the **Start** dialog box.</span></span>
34. <span data-ttu-id="804d9-253">På fliken **Allmänt**, fyll i följande värden:</span><span class="sxs-lookup"><span data-stu-id="804d9-253">On the **General** tab, specify the following values:</span></span>

    - <span data-ttu-id="804d9-254">I fältet **Från oper.nr.**</span><span class="sxs-lookup"><span data-stu-id="804d9-254">In the **From Oper. No.**</span></span> <span data-ttu-id="804d9-255">fält, välj **20**.</span><span class="sxs-lookup"><span data-stu-id="804d9-255">field, select **20**.</span></span>
    - <span data-ttu-id="804d9-256">I fältet **Till oper.nr.**</span><span class="sxs-lookup"><span data-stu-id="804d9-256">In the **To Oper. No.**</span></span> <span data-ttu-id="804d9-257">fält, välj **20**.</span><span class="sxs-lookup"><span data-stu-id="804d9-257">field, select **20**.</span></span>
    - <span data-ttu-id="804d9-258">I fältet **Kvantitet**, ange **10**.</span><span class="sxs-lookup"><span data-stu-id="804d9-258">In the **Quantity** field, enter **10**.</span></span>
    - <span data-ttu-id="804d9-259">Ange alternativet **Bokför plocklista nu** till **Nej**.</span><span class="sxs-lookup"><span data-stu-id="804d9-259">Set the **Post picking list now** option to **No**.</span></span>

    ![Värden som har angetts på fliken Allmänt](./media/subcontract24_general-tab.png)

35. <span data-ttu-id="804d9-261">Välj **OK** för att stänga dialogrutan **Starta** och återgå till sidan **alla produktionsorder**.</span><span class="sxs-lookup"><span data-stu-id="804d9-261">Select **OK** to close the **Start** dialog box and return to the **All production orders** page.</span></span>

    <span data-ttu-id="804d9-262">En plocklista har skapats för material som används för beläggningsoperationen och för serviceartikeln.</span><span class="sxs-lookup"><span data-stu-id="804d9-262">A picking list is created for the materials that are used for the Coating operation, and for the service item.</span></span> <span data-ttu-id="804d9-263">Serviceartikeln motsvarar kostnaden för legotillverkningsoperationen.</span><span class="sxs-lookup"><span data-stu-id="804d9-263">The service item represents the cost of the subcontracted operation.</span></span>

36. <span data-ttu-id="804d9-264">I åtgärdsfönstret, på fliken **Visa**, välj **Plocklista** för att öppna sidan **Plocklista**.</span><span class="sxs-lookup"><span data-stu-id="804d9-264">On the Action Pane, on the **View** tab, select **Picking list** to open the **Picking list** page.</span></span>
37. <span data-ttu-id="804d9-265">Välj plocklistan som inte har bokförts och markera journalnumret för att visa journalraderna.</span><span class="sxs-lookup"><span data-stu-id="804d9-265">Select the picking list that isn't posted, and then select the journal number to view the journal lines.</span></span>

    ![Journalrader på sidan Plocklista](./media/subcontract25_picking-list.png)

38. <span data-ttu-id="804d9-267">I åtgärdsfönstret, välj **Skriv ut** \> **Rapport över plocklista** för att öppna dialogrutan **Rapport över plocklista**.</span><span class="sxs-lookup"><span data-stu-id="804d9-267">On the Action Pane, select **Print** \> **Picking list report** to open the **Picking list report** dialog box.</span></span>
39. <span data-ttu-id="804d9-268">Ange alternativet **Använd layouten för följesedelsnoteringen** till **Ja**.</span><span class="sxs-lookup"><span data-stu-id="804d9-268">Set the **Use delivery note layout** option to **Yes**.</span></span>

    ![Dialogrutan Plocklista - rapport](./media/subcontract26_picking-list-report-dialog.png)

40. <span data-ttu-id="804d9-270">Välj **OK** för att generera rapporten **Plocklista**.</span><span class="sxs-lookup"><span data-stu-id="804d9-270">Select **OK** to generate a **Picking list** report.</span></span>

    <span data-ttu-id="804d9-271">I det här fallet skrivs en leverantörens följesedelsnotering ut för produktionens plocklistejournal.</span><span class="sxs-lookup"><span data-stu-id="804d9-271">In this case, a vendor delivery note is printed from the production picking list journal.</span></span> <span data-ttu-id="804d9-272">Följesedeln anger det material som levereras till leverantören som ska utföra beläggningsoperationen.</span><span class="sxs-lookup"><span data-stu-id="804d9-272">The delivery note specifies the materials that are shipped to the vendor who will do the Coating operation.</span></span>

    ![Plocklista - rapport](./media/subcontract27_picking-list-report.png)

41. <span data-ttu-id="804d9-274">Stäng rapporten **plocklista** för att återgå till sidan **plocklista**.</span><span class="sxs-lookup"><span data-stu-id="804d9-274">Close the **Picking list** report to return to the **Picking list** page.</span></span>
42. <span data-ttu-id="804d9-275">I åtgärdsfönstret, välj **Bokför** för att öppna dialogrutan **bokför journal**.</span><span class="sxs-lookup"><span data-stu-id="804d9-275">On the Action Pane, select **Post** to open the **Post journal** dialog box.</span></span>

    ![Dialogrutan Bokför journal](./media/subcontract28_post-journal-dialog.png)

43. <span data-ttu-id="804d9-277">Välj **OK** för att stänga dialogrutan **Bokför journal**.</span><span class="sxs-lookup"><span data-stu-id="804d9-277">Select **OK** to close the **Post journal** dialog box.</span></span>
44. <span data-ttu-id="804d9-278">Öppna inköpsordern.</span><span class="sxs-lookup"><span data-stu-id="804d9-278">Open the purchase order.</span></span>

    ![Inköpsordersida](./media/subcontract29_purchase-order-page.png)

45. <span data-ttu-id="804d9-280">I åtgärdsfönstret, på fliken **Inköp**, välj **Bekräfta**.</span><span class="sxs-lookup"><span data-stu-id="804d9-280">On the Action Pane, on the **Purchase** tab, select **Confirm**.</span></span>
46. <span data-ttu-id="804d9-281">Välj **Bokför** för att öppna dialogrutan **Bokför journal**.</span><span class="sxs-lookup"><span data-stu-id="804d9-281">Select **Post** to open the **Post journal** dialog box.</span></span>
47. <span data-ttu-id="804d9-282">Välj **OK** för att stänga dialogrutan **Bokför journal** och återgå till sidan **Inköpsorder**.</span><span class="sxs-lookup"><span data-stu-id="804d9-282">Select **OK** to close the **Post journal** dialog box and return to the **Purchase order** page.</span></span>
48. <span data-ttu-id="804d9-283">Ändra enhetspriset från **33** till **40**.</span><span class="sxs-lookup"><span data-stu-id="804d9-283">Change the unit price from **33** to **40**.</span></span>

    ![Enhetspris ändras på sidan inköpsorder](./media/subcontract30_unit-price.png)

49. <span data-ttu-id="804d9-285">Bekräfta inköpsordern igen.</span><span class="sxs-lookup"><span data-stu-id="804d9-285">Confirm the purchase order again.</span></span>
50. <span data-ttu-id="804d9-286">Produktinleverans.</span><span class="sxs-lookup"><span data-stu-id="804d9-286">Product receipt.</span></span>

    ![Dialogrutan Bokför produktinleverans](./media/subcontract31_posting-product-receipt-dialog.png)

51. <span data-ttu-id="804d9-288">Inköpsfaktura.</span><span class="sxs-lookup"><span data-stu-id="804d9-288">Purchase invoice.</span></span>
52. <span data-ttu-id="804d9-289">Uppdatera matchningsstatus.</span><span class="sxs-lookup"><span data-stu-id="804d9-289">Update the match status.</span></span>

    ![Sidan Leverantörsfaktura](./media/subcontract32_vendor-invoice-page.png)

53. <span data-ttu-id="804d9-291">Rapportera som färdig.</span><span class="sxs-lookup"><span data-stu-id="804d9-291">Report as finished.</span></span>

    ![Dialogrutan Rapportera som färdigt](./media/subcontract33_report-as-finished-dialog.png)

54. <span data-ttu-id="804d9-293">Slut.</span><span class="sxs-lookup"><span data-stu-id="804d9-293">End.</span></span>

    ![Dialogrutan Slut](./media/subcontract34_end-dialog.png)

55. <span data-ttu-id="804d9-295">Kostnadsjämförelse.</span><span class="sxs-lookup"><span data-stu-id="804d9-295">Cost comparison.</span></span>

    ![Kostnadsjämförelsediagram](./media/subcontract35_cost-comparison-charts.png)

<span data-ttu-id="804d9-297">Inställning saknas i data.</span><span class="sxs-lookup"><span data-stu-id="804d9-297">Missing setup in data.</span></span>

