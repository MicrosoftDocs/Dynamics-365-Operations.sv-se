---
title: Ställ in olika dimensioner för förpackning och lagring
description: I det här avsnittet visas hur du anger vilken process (förpackning, lagring eller kapslad förpackning) som varje dimension används för.
author: mirzaab
manager: tfehr
ms.date: 01/28/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSPhysDimUOM
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2021-01-28
ms.dyn365.ops.version: Release 10.0.17
ms.openlocfilehash: 004d9b4522335b481b640ef0fe35f4db66e3c9f5
ms.sourcegitcommit: b7a7a14f8650913f6797ae1c4a82ad8adfe415fd
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/28/2021
ms.locfileid: "5078310"
---
# <a name="set-different-dimensions-for-packing-and-storage"></a><span data-ttu-id="a8776-103">Ställ in olika dimensioner för förpackning och lagring</span><span class="sxs-lookup"><span data-stu-id="a8776-103">Set different dimensions for packing and storage</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="a8776-104">Vissa artiklar packas eller lagras på ett sådant sätt att du kan behöva spåra fysiska dimensioner olika för vart och ett av flera olika processer.</span><span class="sxs-lookup"><span data-stu-id="a8776-104">Some items are packed or stored in such a way that you may need to track physical dimensions differently for each of several different processes.</span></span> <span data-ttu-id="a8776-105">Funktionen *Dimensioner för förpackningsprodukt* gör att du kan ställa in en eller flera typer av dimensioner för varje produkt.</span><span class="sxs-lookup"><span data-stu-id="a8776-105">The *Packaging product dimensions* feature lets you set up one or several types of dimensions for each product.</span></span> <span data-ttu-id="a8776-106">Varje dimensionstyp tillhandahåller en uppsättning fysiska mått (vikt, bredd, djup och höjd) och använder den process där de fysiska mätningsvärdena gäller.</span><span class="sxs-lookup"><span data-stu-id="a8776-106">Each dimension type provides a set of physical measurements (weight, width, depth, and height), and establishes the process where those physical measurement values apply.</span></span> <span data-ttu-id="a8776-107">När den här funktionen är aktiverad har ditt system stöd för följande typer av dimensioner:</span><span class="sxs-lookup"><span data-stu-id="a8776-107">When this feature is enabled, your system will support the following types of dimensions:</span></span>

- <span data-ttu-id="a8776-108">*Lagring* - Lagringsdimensioner används tillsammans med platsvolym för att bestämma hur många av varje artikel som kan lagras på olika lagerställen.</span><span class="sxs-lookup"><span data-stu-id="a8776-108">*Storage* - Storage dimensions are used along with location volumetrics to determine how many of each item can be stored in various warehouse locations.</span></span>
- <span data-ttu-id="a8776-109">*Förpackning* - Förpackningsdimensioner används under skapande av behållare och manuell förpackningsprocess för att bestämma hur många av varje artikel som kommer att passa i olika behållartyper.</span><span class="sxs-lookup"><span data-stu-id="a8776-109">*Packing* - Packing dimensions are used during containerization and the manual packing process to determine how many of each item will fit in various container types.</span></span>
- <span data-ttu-id="a8776-110">*Kapslad förpackning* - Kapslade förpackningsdimensioner används när förpackningsprocessen innehåller flera nivåer.</span><span class="sxs-lookup"><span data-stu-id="a8776-110">*Nested packing* - Nested packing dimensions are used when the packing process contains multiple levels.</span></span>

<span data-ttu-id="a8776-111">*Lagringsdimensioner* stöds även om funktionen *Förpackningsproduktdimensioner* inte är aktiverad.</span><span class="sxs-lookup"><span data-stu-id="a8776-111">*Storage* dimensions are supported even when the *Packaging product dimensions* feature isn't enabled.</span></span> <span data-ttu-id="a8776-112">Du ställer in dessa med hjälp av sidan **Fysisk dimension** i Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="a8776-112">You set these up using the **Physical dimension** page in Supply Chain Management.</span></span> <span data-ttu-id="a8776-113">Dessa dimensioner används av alla processer där förpacknings- och kapslade förpackningsdimensioner inte anges.</span><span class="sxs-lookup"><span data-stu-id="a8776-113">These dimensions are used by all processes where the packing and nested packing dimensions aren't specified.</span></span>

<span data-ttu-id="a8776-114">Dimensionerna *förpackning* och *kapslad förpackning* ställs in på sidan **Fysiska produktdimensioner** som läggs till när du aktiverar funktionen för *förpackningsproduktdimensioner*.</span><span class="sxs-lookup"><span data-stu-id="a8776-114">*Packing* and *nested packing* dimensions are set up using the **Physical product dimensions** page, which is added when you enable the *Packaging product dimensions* feature.</span></span>
<span data-ttu-id="a8776-115">Det här avsnittet innehåller ett scenario som illustrerar hur den här funktionen används.</span><span class="sxs-lookup"><span data-stu-id="a8776-115">This topic provides a scenario that illustrates how to use this feature.</span></span>

## <a name="turn-on-the-packaging-product-dimensions-feature"></a><span data-ttu-id="a8776-116">Aktivera funktionen för förpackningsproduktdimensioner</span><span class="sxs-lookup"><span data-stu-id="a8776-116">Turn on the packaging product dimensions feature</span></span>

<span data-ttu-id="a8776-117">Innan du kan använda den här funktionen den aktiveras i ditt system.</span><span class="sxs-lookup"><span data-stu-id="a8776-117">Before you can use this feature, it must be turned on in your system.</span></span> <span data-ttu-id="a8776-118">Administratörer kan använda arbetsytan [funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) för att kontrollera funktionens status och aktivera den om det behövs.</span><span class="sxs-lookup"><span data-stu-id="a8776-118">Admins can use the [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) workspace to check the status of the feature and turn it on if it's required.</span></span> <span data-ttu-id="a8776-119">Funktionen visas på följande sätt:</span><span class="sxs-lookup"><span data-stu-id="a8776-119">There, the feature is listed in the following way:</span></span>

- <span data-ttu-id="a8776-120">**Modul:** *Lagerstyrning*</span><span class="sxs-lookup"><span data-stu-id="a8776-120">**Module:** *Warehouse management*</span></span>
- <span data-ttu-id="a8776-121">**Funktionens namn:** *förpackningsproduktdimensioner*</span><span class="sxs-lookup"><span data-stu-id="a8776-121">**Feature name:** *Packaging product dimensions*</span></span>

## <a name="example-scenario"></a><span data-ttu-id="a8776-122">Exempelscenario</span><span class="sxs-lookup"><span data-stu-id="a8776-122">Example scenario</span></span>

### <a name="set-up-the-scenario"></a><span data-ttu-id="a8776-123">Ställ in scenario</span><span class="sxs-lookup"><span data-stu-id="a8776-123">Set up the scenario</span></span>

<span data-ttu-id="a8776-124">Innan du kan köra exempelscenariot måste du förbereda systemet på det sätt som beskrivs i det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="a8776-124">Before you can run the example scenario, you must prepare your system as described in this section.</span></span>

#### <a name="enable-demo-data"></a><span data-ttu-id="a8776-125">Aktivera demonstrationsdata</span><span class="sxs-lookup"><span data-stu-id="a8776-125">Enable demo data</span></span>

<span data-ttu-id="a8776-126">Om du vill arbeta genom detta scenario med hjälp av de demoposter och värden som anges här måste du använda ett system där standard [demodata](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) har installerats.</span><span class="sxs-lookup"><span data-stu-id="a8776-126">To work through this scenario using the demo records and values that are specified here, you must be on a system where the standard [demo data](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) is installed.</span></span> <span data-ttu-id="a8776-127">Dessutom måste du välja den *USMF* juridiska personen innan du börjar.</span><span class="sxs-lookup"><span data-stu-id="a8776-127">Additionally, you must select the *USMF* legal entity before you begin.</span></span>

#### <a name="add-a-new-physical-dimension-to-a-product"></a><span data-ttu-id="a8776-128">Lägga till en ny fysisk dimension i en produkt</span><span class="sxs-lookup"><span data-stu-id="a8776-128">Add a new physical dimension to a product</span></span>

<span data-ttu-id="a8776-129">Lägg till en ny fysisk dimension för en produkt genom att göra följande:</span><span class="sxs-lookup"><span data-stu-id="a8776-129">Add a new physical dimension for a product by doing the following:</span></span>

1. <span data-ttu-id="a8776-130">Gå till **Produktinformationshantering \> Produkter \> Frisläppta produkter**.</span><span class="sxs-lookup"><span data-stu-id="a8776-130">Go to **Product information management \> Products \> Released products**.</span></span>
1. <span data-ttu-id="a8776-131">Välj produkten med **artikelnummer** *A0001*.</span><span class="sxs-lookup"><span data-stu-id="a8776-131">Select the product with **Item number** *A0001*.</span></span>
1. <span data-ttu-id="a8776-132">I åtgärdsfönstret, öppna fliken **Hantera lager**, i gruppen **Lagerställe**, väljer du **Fysiska produktdimensioner**.</span><span class="sxs-lookup"><span data-stu-id="a8776-132">On the Action Pane, open the **Manage inventory** tab and, from the **Warehouse** group, select **Physical product dimensions**.</span></span>
1. <span data-ttu-id="a8776-133">Sidan **Fysiska produktdimensioner** öppnas.</span><span class="sxs-lookup"><span data-stu-id="a8776-133">The **Physical product dimensions** page opens.</span></span> <span data-ttu-id="a8776-134">I åtgärdsfönstret, välj **Ny** för att lägga till en ny dimension i rutnätet med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="a8776-134">On the Action Pane, select **New** to add a new dimension to the grid with the following settings:</span></span>
    - <span data-ttu-id="a8776-135">**Fysisk dimensionstyp** - *förpackning*</span><span class="sxs-lookup"><span data-stu-id="a8776-135">**Physical dimension type** - *Packing*</span></span>
    - <span data-ttu-id="a8776-136">**Fysiska enheter** - *st*</span><span class="sxs-lookup"><span data-stu-id="a8776-136">**Physical unit** - *pcs*</span></span>
    - <span data-ttu-id="a8776-137">**Vikt** - *4*</span><span class="sxs-lookup"><span data-stu-id="a8776-137">**Weight** - *4*</span></span>
    - <span data-ttu-id="a8776-138">**Viktenhet** - *kg*</span><span class="sxs-lookup"><span data-stu-id="a8776-138">**Weight unit** - *kg*</span></span>
    - <span data-ttu-id="a8776-139">**Djup** - *3*</span><span class="sxs-lookup"><span data-stu-id="a8776-139">**Depth** - *3*</span></span>
    - <span data-ttu-id="a8776-140">**Höjd** - *4*</span><span class="sxs-lookup"><span data-stu-id="a8776-140">**Height** - *4*</span></span>
    - <span data-ttu-id="a8776-141">**Bredd** - *3*</span><span class="sxs-lookup"><span data-stu-id="a8776-141">**Width** - *3*</span></span>
    - <span data-ttu-id="a8776-142">**Längd** - *cm*</span><span class="sxs-lookup"><span data-stu-id="a8776-142">**Length** - *cm*</span></span>
    - <span data-ttu-id="a8776-143">**Volymenhet** - *cm3*</span><span class="sxs-lookup"><span data-stu-id="a8776-143">**Volume unit** - *cm3*</span></span>

<span data-ttu-id="a8776-144">Fältet **Volym** beräknas automatiskt baserat på inställningarna **djup**, **höjd** och **bredd**.</span><span class="sxs-lookup"><span data-stu-id="a8776-144">The **Volume** field is automatically calculated based on your **Depth**, **Height**, and **Width** settings.</span></span>

#### <a name="create-a-new-container-type"></a><span data-ttu-id="a8776-145">Skapa en ny behållartyp</span><span class="sxs-lookup"><span data-stu-id="a8776-145">Create a new container type</span></span>

<span data-ttu-id="a8776-146">Gå till **Lagerstyrning \> Inställningar \> Behållare \> Behållartyper** och skapa en ny post med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="a8776-146">Go to **Warehouse management \> Setup \> Containers \> Container types** and create a new record with the following settings:</span></span>

- <span data-ttu-id="a8776-147">**Behållartyp** - *liten kartong*</span><span class="sxs-lookup"><span data-stu-id="a8776-147">**Container type code** - *Short Box*</span></span>
- <span data-ttu-id="a8776-148">**Beskrivning** - *liten kartong*</span><span class="sxs-lookup"><span data-stu-id="a8776-148">**Description** - *Short Box*</span></span>
- <span data-ttu-id="a8776-149">**Högsta nettovikt** - *50*</span><span class="sxs-lookup"><span data-stu-id="a8776-149">**Maximum net weight** - *50*</span></span>
- <span data-ttu-id="a8776-150">**Volym** - *144*</span><span class="sxs-lookup"><span data-stu-id="a8776-150">**Volume** - *144*</span></span>
- <span data-ttu-id="a8776-151">**Längd** - *6*</span><span class="sxs-lookup"><span data-stu-id="a8776-151">**Length** - *6*</span></span>
- <span data-ttu-id="a8776-152">**Bredd** - *6*</span><span class="sxs-lookup"><span data-stu-id="a8776-152">**Width** - *6*</span></span>
- <span data-ttu-id="a8776-153">**Höjd** - *4*</span><span class="sxs-lookup"><span data-stu-id="a8776-153">**Height** - *4*</span></span>

#### <a name="create-a-container-group"></a><span data-ttu-id="a8776-154">Skapa en behållargrupp</span><span class="sxs-lookup"><span data-stu-id="a8776-154">Create a container group</span></span>

<span data-ttu-id="a8776-155">Gå till **Lagerstyrning \> Inställningar \> Behållare \> Behållargrupper** och skapa en ny post med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="a8776-155">Go to **Warehouse management \> Setup \> Containers \> Container groups** and create a new record with the following settings:</span></span>

- <span data-ttu-id="a8776-156">**Behållargrupp-ID** - *liten kartong*</span><span class="sxs-lookup"><span data-stu-id="a8776-156">**Container group ID** - *Short Box*</span></span>
- <span data-ttu-id="a8776-157">**Beskrivning** - *liten kartong*</span><span class="sxs-lookup"><span data-stu-id="a8776-157">**Description** - *Short Box*</span></span>

<span data-ttu-id="a8776-158">Lägg till en ny rad i avsnittet **Information**.</span><span class="sxs-lookup"><span data-stu-id="a8776-158">Add a new line to the **Details** section.</span></span> <span data-ttu-id="a8776-159">Ange att **behållartypen** är *liten kartong*.</span><span class="sxs-lookup"><span data-stu-id="a8776-159">Set the **Container type** to *Short Box*.</span></span>

#### <a name="set-up-a-container-build-template"></a><span data-ttu-id="a8776-160">Ställa in en behållarversionsmall</span><span class="sxs-lookup"><span data-stu-id="a8776-160">Set up a container build template</span></span>

<span data-ttu-id="a8776-161">Gå till **Lagerstyrning \> Inställningar \> Behållare \> Mall för skapande av behållare** och välj **Kartonger**.</span><span class="sxs-lookup"><span data-stu-id="a8776-161">Go to **Warehouse management \> Setup \> Containers \> Container build templates** and select **Boxes**.</span></span> <span data-ttu-id="a8776-162">Ändra **behållargrupp-ID** till *liten kartong*.</span><span class="sxs-lookup"><span data-stu-id="a8776-162">Change the **Container group ID** to *Short Box*.</span></span>

### <a name="run-the-scenario"></a><span data-ttu-id="a8776-163">Kör scenariot</span><span class="sxs-lookup"><span data-stu-id="a8776-163">Run the scenario</span></span>

<span data-ttu-id="a8776-164">När du har förberett systemet enligt beskrivningen i det föregående avsnittet är du redo att köra scenariot enligt beskrivningen i nästa avsnitt.</span><span class="sxs-lookup"><span data-stu-id="a8776-164">After you have prepared your system as described in the previous section, you are ready to run the scenario as described in the next section.</span></span>

#### <a name="create-a-sales-order-and-create-a-shipment"></a><span data-ttu-id="a8776-165">Skapa en försäljningsorder och skapa en försändelse</span><span class="sxs-lookup"><span data-stu-id="a8776-165">Create a sales order and create a shipment</span></span>

<span data-ttu-id="a8776-166">I denna process skapar du en försändelse baserad på artikelns *förpackningsdimensioner*, för vilken höjden är mindre än 3.</span><span class="sxs-lookup"><span data-stu-id="a8776-166">In this process you will create a shipment based on the item *packing* dimensions, for which the height is less than 3.</span></span>

1. <span data-ttu-id="a8776-167">Gå till **Försäljning och marknadsföring \> Försäljningsorder \> Alla försäljningsorder**.</span><span class="sxs-lookup"><span data-stu-id="a8776-167">Go to **Sales and marketing \> Sales orders \> All sales orders**.</span></span>
1. <span data-ttu-id="a8776-168">Klicka på **Ny** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="a8776-168">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="a8776-169">I dialogrutan **Skapa försäljningsorder** ställ in följande värden:</span><span class="sxs-lookup"><span data-stu-id="a8776-169">In the **Create sales order** dialog box, set the following values:</span></span>

    - <span data-ttu-id="a8776-170">**Kundkonto:** *US-001*</span><span class="sxs-lookup"><span data-stu-id="a8776-170">**Customer account:** *US-001*</span></span>
    - <span data-ttu-id="a8776-171">**Lagerställe:** *63*</span><span class="sxs-lookup"><span data-stu-id="a8776-171">**Warehouse:** *63*</span></span>

1. <span data-ttu-id="a8776-172">Välj **OK** för att skapa den försäljningsordern och stänga dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="a8776-172">Select **OK** to create the sales order and close the dialog box.</span></span>
1. <span data-ttu-id="a8776-173">Den nya försäljningsordern öppnas.</span><span class="sxs-lookup"><span data-stu-id="a8776-173">The new sales order is opened.</span></span> <span data-ttu-id="a8776-174">Detta bör innehålla en ny tom rad i rutnätet på snabbfliken **försäljningsorderrader**.</span><span class="sxs-lookup"><span data-stu-id="a8776-174">It should include a new, empty line in the grid on the **Sales order lines** FastTab.</span></span> <span data-ttu-id="a8776-175">Ställ in följande värden på denna rad:</span><span class="sxs-lookup"><span data-stu-id="a8776-175">On this line, set the following values:</span></span>

    - <span data-ttu-id="a8776-176">**Artikelnummer:** *A0001*</span><span class="sxs-lookup"><span data-stu-id="a8776-176">**Item number:** *A0001*</span></span>
    - <span data-ttu-id="a8776-177">**Kvantitet:** *5*</span><span class="sxs-lookup"><span data-stu-id="a8776-177">**Quantity:** *5*</span></span>

1. <span data-ttu-id="a8776-178">På snabbfliken **Försäljningsorderrader** välj **Lager \> Reservation**.</span><span class="sxs-lookup"><span data-stu-id="a8776-178">On the **Sales order lines** FastTab, select **Inventory \> Reservation**.</span></span>
1. <span data-ttu-id="a8776-179">På sidan **Reservation** i åtgärdsfönstret, välj **Reservera parti** för att reservera lager.</span><span class="sxs-lookup"><span data-stu-id="a8776-179">On the **Reservation** page, on the Action Pane, select **Reserve lot** to reserve the inventory.</span></span>
1. <span data-ttu-id="a8776-180">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="a8776-180">Close the page.</span></span>
1. <span data-ttu-id="a8776-181">I åtgärdsfönstret öppna fliken **Lagerställe** och välj **Släpp till lagerställe** för att skapa arbete för lagerstället.</span><span class="sxs-lookup"><span data-stu-id="a8776-181">On the Action Pane, open the **Warehouse** tab and select **Release to warehouse** to create work for the warehouse.</span></span>
1. <span data-ttu-id="a8776-182">På snabbfliken **försäljningsorderrad** välj **Lagerställe \> Leveransdetaljer**.</span><span class="sxs-lookup"><span data-stu-id="a8776-182">On the **Sales order lines** FastTab, select **Warehouse \> Shipment details**.</span></span>
1. <span data-ttu-id="a8776-183">Öppna fliken arbetsflöde i åtgärdsfönstret **Transport** och välj **Visa behållare**.</span><span class="sxs-lookup"><span data-stu-id="a8776-183">On the Action Pane, open the **Transportation** tab and select **View containers**.</span></span> <span data-ttu-id="a8776-184">Bekräfta att artikeln har förpackats i de två behållarna *liten kartong*.</span><span class="sxs-lookup"><span data-stu-id="a8776-184">Confirm that the item was containerized into the two *Short Box* containers.</span></span>

#### <a name="place-an-item-into-storage"></a><span data-ttu-id="a8776-185">Förvara artikel</span><span class="sxs-lookup"><span data-stu-id="a8776-185">Place an item into storage</span></span>

1. <span data-ttu-id="a8776-186">Öppna den mobila enheten, logga in på lagerställe 63 och gå till **Lager \> Justera i**.</span><span class="sxs-lookup"><span data-stu-id="a8776-186">Open the mobile device, sign in to warehouse 63 and go to **Inventory \> Adjust In**.</span></span>
1. <span data-ttu-id="a8776-187">Ange **Loc** = *SHORT-01*.</span><span class="sxs-lookup"><span data-stu-id="a8776-187">Enter **Loc** = *SHORT-01*.</span></span> <span data-ttu-id="a8776-188">Gör ett nytt ID-nummer med **artikel** = *A0001* och **kvantitet** = *1 st*.</span><span class="sxs-lookup"><span data-stu-id="a8776-188">Make a new license plate with **Item** = *A0001* and **Quantity** = *1 pcs*.</span></span>
1. <span data-ttu-id="a8776-189">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="a8776-189">Select **OK**.</span></span> <span data-ttu-id="a8776-190">Du får felmeddelandet "Plats SHORT-01 misslyckades eftersom artikel A0001 inte får plats i platsens angivna dimensioner."</span><span class="sxs-lookup"><span data-stu-id="a8776-190">You will receive the error "Location SHORT-01 failed because item A0001 does not fit in location's specified dimensions."</span></span> <span data-ttu-id="a8776-191">Det beror på att produktens *lagringstypdimensioner* är större än de dimensioner som anges i platsprofilen.</span><span class="sxs-lookup"><span data-stu-id="a8776-191">This is because the *Storage* type dimensions of the product are larger than the dimensions specified on the location profile.</span></span>
