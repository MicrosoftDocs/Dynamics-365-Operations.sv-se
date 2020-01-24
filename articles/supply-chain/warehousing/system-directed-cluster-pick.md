---
title: Systemdirigerad klusterplockning
description: Det här avsnittet innehåller en översikt över systemstyrd klusterplockning i Microsoft Dynamics 365 Supply Chain Management.
author: Mirzaab
manager: AnnBe
ms.date: 12/10/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Supply Chain Management
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2019-12-31
ms.dyn365.ops.version: 10.0.1
ms.openlocfilehash: c3b23a5d3b77bae89e4845bdff4ab20f95c46497
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/20/2019
ms.locfileid: "2917866"
---
# <a name="system-directed-cluster-picking"></a><span data-ttu-id="81e83-103">Systemdirigerad klusterplockning</span><span class="sxs-lookup"><span data-stu-id="81e83-103">System-directed cluster picking</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="81e83-104">Klusterplockning är en del plockningsprocess som låter dig plocka artiklar för flera order samtidigt genom att klustra dem i plockningskluster.</span><span class="sxs-lookup"><span data-stu-id="81e83-104">Cluster picking is a piece picking process that lets you pick items for multiple orders at the same time by clustering them into pick clusters.</span></span> <span data-ttu-id="81e83-105">Du måste sedan besöka plockplatsen bara en gång.</span><span class="sxs-lookup"><span data-stu-id="81e83-105">You then have to visit the pick location only one time.</span></span> <span data-ttu-id="81e83-106">Den här funktionen används vanligtvis med små orderplockning eller kvantiteter som är mindre än antalet fall.</span><span class="sxs-lookup"><span data-stu-id="81e83-106">Typically, this functionality is used with small order picking or quantities that are less than case quantities.</span></span>

<span data-ttu-id="81e83-107">När Systemstyrd klusterplockning har ställts in kan du klusterplocka arbetshuvuden baserat på ett systemgenererat kluster.</span><span class="sxs-lookup"><span data-stu-id="81e83-107">When system-directed cluster picking is set up, you can cluster-pick work headers, based on a system-generated cluster.</span></span> <span data-ttu-id="81e83-108">Systemet klusterplockar order upp till antalet befattningar som anges i klusterprofilen.</span><span class="sxs-lookup"><span data-stu-id="81e83-108">The system cluster-picks orders up to the number of positions that is specified in the cluster profile.</span></span> <span data-ttu-id="81e83-109">Därför kan du plocka flera order samtidigt utan att manuellt skapa ett kluster.</span><span class="sxs-lookup"><span data-stu-id="81e83-109">Therefore, you can pick multiple orders at the same time without having to manually create a cluster.</span></span>

<span data-ttu-id="81e83-110">Systemstyrd klusterplockning erbjuder ett alternativ till manuell klusteruppbyggnad, där en klusterprofil används för att skapa ett kluster.</span><span class="sxs-lookup"><span data-stu-id="81e83-110">System-directed cluster picking offers an alternative to manual cluster building, where a cluster profile is used to create a cluster.</span></span> <span data-ttu-id="81e83-111">Flera installationsrelaterade rader måste definieras i klusterprofilen innan de används:</span><span class="sxs-lookup"><span data-stu-id="81e83-111">Several setup-related lines must be defined in the cluster profile before it's used:</span></span>

- <span data-ttu-id="81e83-112">**Antal positioner** motsvarar antalet order som ska placeras i ett kluster.</span><span class="sxs-lookup"><span data-stu-id="81e83-112">**Number of positions** corresponds to the number of orders that will be put on a cluster.</span></span> <span data-ttu-id="81e83-113">Därför motsvarar antalet last.</span><span class="sxs-lookup"><span data-stu-id="81e83-113">Therefore, it corresponds to the number of totes.</span></span>
- <span data-ttu-id="81e83-114">**Bryt kluster** avgör när klustret ska brytas.</span><span class="sxs-lookup"><span data-stu-id="81e83-114">**Break cluster** determines when the cluster should be broken.</span></span>
- <span data-ttu-id="81e83-115">**Generera kluster-ID** styr om kluster-ID kommer att genereras av systemet eller anges av användaren.</span><span class="sxs-lookup"><span data-stu-id="81e83-115">**Generate cluster ID** controls whether the cluster ID will be generated by the system or entered by the user.</span></span>
- <span data-ttu-id="81e83-116">**Sortera verifieringstyp** avgör om positionsverifiering krävs.</span><span class="sxs-lookup"><span data-stu-id="81e83-116">**Sort verification type** determines whether position verification is required.</span></span>

<span data-ttu-id="81e83-117">Ett nytt menyalternativ för mobila enheter används för systemstyrd klusterplockning.</span><span class="sxs-lookup"><span data-stu-id="81e83-117">A new mobile device menu item is used for system-directed cluster picking.</span></span> <span data-ttu-id="81e83-118">Klusterprofil-ID måste anges för alternativet **dirigerad av**.</span><span class="sxs-lookup"><span data-stu-id="81e83-118">The cluster profile ID must be specified for the **Directed by** option.</span></span> <span data-ttu-id="81e83-119">Dessutom kan den systeminriktade frågeordningen gruppera order, baserat på företagsspecifika kriterier.</span><span class="sxs-lookup"><span data-stu-id="81e83-119">Additionally, the system-directed query order can group orders, based on company-specific criteria.</span></span> <span data-ttu-id="81e83-120">Därför kan du ytterligare optimera tilldelningen av arbetsorder genom att ange anpassade sorteringskriterier på den systeminriktade frågeordningen.</span><span class="sxs-lookup"><span data-stu-id="81e83-120">Therefore, you can further optimize the assignment of work orders by specifying customized sorting criteria on the system-directed query order.</span></span>

<span data-ttu-id="81e83-121">När systemstyrd klusterplockning görs, visas lagerarbetare med ett kluster där plockorder har förtilldelats till klusterbefattningar.</span><span class="sxs-lookup"><span data-stu-id="81e83-121">When system-directed cluster picking is done, warehouse workers are presented with a cluster where picking orders have been preassigned to cluster positions.</span></span> <span data-ttu-id="81e83-122">Därför kan arbetstagarna börja plocka en artikel för flera arbetsorder genom att besöka plockplatsen bara en gång.</span><span class="sxs-lookup"><span data-stu-id="81e83-122">Therefore, workers can start to pick an item for multiple work orders by visiting the pick location only one time.</span></span> <span data-ttu-id="81e83-123">Plockningsprocessen för systemstyrd klusterplockning är densamma som processen för användarstyrd klusterplockning.</span><span class="sxs-lookup"><span data-stu-id="81e83-123">The picking process for system-directed cluster picking is the same as the process for user-directed cluster picking.</span></span>

## <a name="set-up-system-directed-cluster-picking"></a><span data-ttu-id="81e83-124">Ställ in systemdirigerad klusterplockning</span><span class="sxs-lookup"><span data-stu-id="81e83-124">Set up system-directed cluster picking</span></span>

### <a name="create-cluster-profiles"></a><span data-ttu-id="81e83-125">Skapa klusterprofiler</span><span class="sxs-lookup"><span data-stu-id="81e83-125">Create cluster profiles</span></span>

<span data-ttu-id="81e83-126">Klusterprofiler styr hur systemet skapar varje kluster.</span><span class="sxs-lookup"><span data-stu-id="81e83-126">Cluster profiles control how the system creates each cluster.</span></span> <span data-ttu-id="81e83-127">Om det krävs olika kluster bör en annan klusterprofil skapas för varje menyalternativ för mobila enheter.</span><span class="sxs-lookup"><span data-stu-id="81e83-127">If different clusters are required, a different cluster profile should be created for each mobile device menu item.</span></span>

1. <span data-ttu-id="81e83-128">Gå till **lagerstyrning \> inställningar \> mobiltelefon \> klusterprofiler**.</span><span class="sxs-lookup"><span data-stu-id="81e83-128">Go to **Warehouse management \> Setup \> Mobile device \> Cluster profiles**.</span></span>
2. <span data-ttu-id="81e83-129">Välj **Ny**.</span><span class="sxs-lookup"><span data-stu-id="81e83-129">Select **New**.</span></span>
3. <span data-ttu-id="81e83-130">I fältet **Klusterprofil-ID** ange **2 position**.</span><span class="sxs-lookup"><span data-stu-id="81e83-130">In the **Cluster profile ID** field, enter **2 Position**.</span></span>
4. <span data-ttu-id="81e83-131">Skriv **2 position** i fältet **Namn**.</span><span class="sxs-lookup"><span data-stu-id="81e83-131">In the **Name** field, enter **2 Position**.</span></span>
5. <span data-ttu-id="81e83-132">På snabbfliken **Allmänt** ange följande fält:</span><span class="sxs-lookup"><span data-stu-id="81e83-132">On the **General** FastTab, set the following fields:</span></span>

    - <span data-ttu-id="81e83-133">**Generera kluster-ID** : Ange det här alternativet **Ja**.</span><span class="sxs-lookup"><span data-stu-id="81e83-133">**Generate cluster ID:** Set this option to **Yes**.</span></span> <span data-ttu-id="81e83-134">Det här alternativet avgör om kluster-ID skapas automatiskt av systemet eller om användaren ska skapa den i början av plockning.</span><span class="sxs-lookup"><span data-stu-id="81e83-134">This option determines whether the cluster ID is automatically created by the system, or whether the user will create it at the start of picking.</span></span>
    - <span data-ttu-id="81e83-135">**Aktivera positioner:** ange det här alternativet till **Ja**.</span><span class="sxs-lookup"><span data-stu-id="81e83-135">**Activate positions:** Set this option to **Yes**.</span></span> <span data-ttu-id="81e83-136">Det här alternativet avgör om positionsnamnen genereras automatiskt baserat på inställningen av positionsnamn.</span><span class="sxs-lookup"><span data-stu-id="81e83-136">This option determines whether the position names are automatically generated based on the position name setup.</span></span> <span data-ttu-id="81e83-137">Om den här alternativet är inställt på **Nej** används registreringsskylt-ID för positionen.</span><span class="sxs-lookup"><span data-stu-id="81e83-137">If this option is set to **No**, the license plate ID for the position is used.</span></span>
    - <span data-ttu-id="81e83-138">**Antal positioner:** Ange **2**.</span><span class="sxs-lookup"><span data-stu-id="81e83-138">**Number of positions:** Enter **2**.</span></span> <span data-ttu-id="81e83-139">Det här fältet bestämmer det maximala antalet positioner som klustret kan ha (det vill, det maximala antalet rutor, laster och så vidare).</span><span class="sxs-lookup"><span data-stu-id="81e83-139">This field determines the maximum number of positions that the cluster can have (that is, the maximum number of boxes, totes, and so on).</span></span>
    - <span data-ttu-id="81e83-140">**Positionsnamn:** Välj **numeriskt**, så att befattningar namnges med hjälp av kontinuerliga tal.</span><span class="sxs-lookup"><span data-stu-id="81e83-140">**Position name:** Select **Numeric**, so that positions are named by using continuous numbers.</span></span> <span data-ttu-id="81e83-141">Om du väljer **alfabetiskt** namnges positionerna i alfabetisk ordning.</span><span class="sxs-lookup"><span data-stu-id="81e83-141">If you select **Alphabetical**, the positions are named in alphabetical order.</span></span>
    - <span data-ttu-id="81e83-142">**Bryt kluster på:** Välj **placera**.</span><span class="sxs-lookup"><span data-stu-id="81e83-142">**Break cluster at:** Select **Put**.</span></span> <span data-ttu-id="81e83-143">Det här fältet avgör när klustret bryts.</span><span class="sxs-lookup"><span data-stu-id="81e83-143">This field determines when the cluster is broken.</span></span>
    - <span data-ttu-id="81e83-144">**Sortera verifieringstyp:** Välj **positionsskanning**.</span><span class="sxs-lookup"><span data-stu-id="81e83-144">**Sort verification type:** Select **Position scan**.</span></span> <span data-ttu-id="81e83-145">Det här fältet bestämmer om sätta i position-steget verifieras.</span><span class="sxs-lookup"><span data-stu-id="81e83-145">This field determines whether the put-to-position step is verified.</span></span>

6. <span data-ttu-id="81e83-146">På snabbfliken **klustersortering** kan du definiera sorteringskriterier genom att skapa en ny rad och ange följande fält:</span><span class="sxs-lookup"><span data-stu-id="81e83-146">On the **Cluster sorting** FastTab, you can define sorting criteria by creating a new line and setting the following fields:</span></span>

    - <span data-ttu-id="81e83-147">**Sekvensnummer:** det här fältet bestämmer sekvensen som systemet sorterar efter.</span><span class="sxs-lookup"><span data-stu-id="81e83-147">**Sequence number:** This field determines the sequence that the system sorts by.</span></span> <span data-ttu-id="81e83-148">Ett värde anges automatiskt, men du kan ändra det som du behöver.</span><span class="sxs-lookup"><span data-stu-id="81e83-148">A value is entered automatically, but you can change it as you require.</span></span>
    - <span data-ttu-id="81e83-149">**Fältnamn:** välj **WMSLocationId**.</span><span class="sxs-lookup"><span data-stu-id="81e83-149">**Field name:** Select **WMSLocationId**.</span></span> <span data-ttu-id="81e83-150">Det här fältet bestämmer det fält som raden använder för sorteringskriterier.</span><span class="sxs-lookup"><span data-stu-id="81e83-150">This field determines the field that the line uses for sorting criteria.</span></span>
    - <span data-ttu-id="81e83-151">**Sortering:** Välj **stigande**.</span><span class="sxs-lookup"><span data-stu-id="81e83-151">**Sorting:** Select **Ascending**.</span></span> <span data-ttu-id="81e83-152">Det här fältet anger om sorteringen görs i stigande eller fallande ordning.</span><span class="sxs-lookup"><span data-stu-id="81e83-152">This field defines whether the sorting is done in ascending or descending order.</span></span>

### <a name="create-a-mobile-device-menu-item"></a><span data-ttu-id="81e83-153">Skapa ett menykommando för mobila enheter</span><span class="sxs-lookup"><span data-stu-id="81e83-153">Create a mobile device menu item</span></span>

<span data-ttu-id="81e83-154">Gör så här om du vill skapa ett nytt menyalternativ för mobila enheter för systemstyrd klusterplockning och länka klusterprofil-ID till menyalternativet mobil enhet.</span><span class="sxs-lookup"><span data-stu-id="81e83-154">To create a new mobile device menu item for system-directed cluster picking and link the cluster profile ID to the mobile device menu item, follow these steps.</span></span>

1. <span data-ttu-id="81e83-155">Gå till **Lagerstyrning \> Inställningar \> Mobil enhet \> Menyalternativ på mobil enhet**.</span><span class="sxs-lookup"><span data-stu-id="81e83-155">Go to **Warehouse management \> Setup \> Mobile device \> Mobile device menu items**.</span></span>
2. <span data-ttu-id="81e83-156">Välj **Ny**.</span><span class="sxs-lookup"><span data-stu-id="81e83-156">Select **New**.</span></span>
3. <span data-ttu-id="81e83-157">I fältet **menyalternativnamn** anger du ett **SD-kluster**.</span><span class="sxs-lookup"><span data-stu-id="81e83-157">In the **Menu item name** field, enter **SD Cluster**.</span></span>
4. <span data-ttu-id="81e83-158">I fältet **Titel** ange **SD-kluster**.</span><span class="sxs-lookup"><span data-stu-id="81e83-158">In the **Title** field, enter **SD Cluster**.</span></span>
5. <span data-ttu-id="81e83-159">Välj **Arbete** i fältet **Läge**.</span><span class="sxs-lookup"><span data-stu-id="81e83-159">In the **Mode** field, select **Work**.</span></span>
6. <span data-ttu-id="81e83-160">Ange alternativet **Använd befintligt arbete** till **Ja**.</span><span class="sxs-lookup"><span data-stu-id="81e83-160">Set the **Use existing work** option to **Yes**.</span></span>
7. <span data-ttu-id="81e83-161">På snabbfliken **Allmänt** ange följande fält:</span><span class="sxs-lookup"><span data-stu-id="81e83-161">On the **General** FastTab, set the following fields:</span></span>

    - <span data-ttu-id="81e83-162">**Dirigerad av:** Välj **Systemdirigerad**.</span><span class="sxs-lookup"><span data-stu-id="81e83-162">**Directed by:** Select **System directed**.</span></span>
    - <span data-ttu-id="81e83-163">**Generera registreringsskylt** : Ange det här alternativet **Ja**.</span><span class="sxs-lookup"><span data-stu-id="81e83-163">**Generate license plate:** Set this option to **Yes**.</span></span>
    - <span data-ttu-id="81e83-164">**Klusterprofil-ID:** Välj **2 position**.</span><span class="sxs-lookup"><span data-stu-id="81e83-164">**Cluster profile ID:** Select **2 Position**.</span></span>

8. <span data-ttu-id="81e83-165">På snabbfliken **arbetsklasser** ställer du in den giltiga arbetsklassen för den här mobila enhetens menyalternativ genom att ange följande fält:</span><span class="sxs-lookup"><span data-stu-id="81e83-165">On the **Work classes** FastTab, set up the valid work class for this mobile device menu item by setting the following fields:</span></span>

    - <span data-ttu-id="81e83-166">**Arbetsklass-ID**: kontrollera att **försäljning** har angetts.</span><span class="sxs-lookup"><span data-stu-id="81e83-166">**Work class ID:** Make sure that **Sales** is entered.</span></span>
    - <span data-ttu-id="81e83-167">**Typ av arbetsorder**: kontrollera att **försäljningsorder** har angetts.</span><span class="sxs-lookup"><span data-stu-id="81e83-167">**Work order type:** Make sure that **Sales orders** is entered.</span></span>

9. <span data-ttu-id="81e83-168">Gör så här om du vill ange en ny systemstyrd arbetssekvensfråga:</span><span class="sxs-lookup"><span data-stu-id="81e83-168">Follow these steps to specify a new system-directed work sequence query:</span></span>

    1. <span data-ttu-id="81e83-169">Välj **Ny**.</span><span class="sxs-lookup"><span data-stu-id="81e83-169">Select **New**.</span></span>
    2. <span data-ttu-id="81e83-170">I fältet **Sekvensnummer**, ange **1**.</span><span class="sxs-lookup"><span data-stu-id="81e83-170">In the **Sequence number** field, enter **1**.</span></span>
    3. <span data-ttu-id="81e83-171">I fältet **Beskrivning** väljer du **Arbetsprioritet – arbets-ID**.</span><span class="sxs-lookup"><span data-stu-id="81e83-171">In the **Description** field, select **Work priority – Work ID**.</span></span>

10. <span data-ttu-id="81e83-172">Välj på menyn **redigera fråga**.</span><span class="sxs-lookup"><span data-stu-id="81e83-172">On the menu, select **Edit query**.</span></span>
11. <span data-ttu-id="81e83-173">Ange något av följande fält på fliken **Sortering**:</span><span class="sxs-lookup"><span data-stu-id="81e83-173">On the **Sorting** tab, set the following fields:</span></span>

    - <span data-ttu-id="81e83-174">**Register:** Välj **Arbete**.</span><span class="sxs-lookup"><span data-stu-id="81e83-174">**Table:** Select **Work**.</span></span>
    - <span data-ttu-id="81e83-175">**Härlett register:** Välj **Arbete**.</span><span class="sxs-lookup"><span data-stu-id="81e83-175">**Derived table:** Select **Work**.</span></span>
    - <span data-ttu-id="81e83-176">**Fält:** Välj **arbetsprioritet**.</span><span class="sxs-lookup"><span data-stu-id="81e83-176">**Field:** Select **Work priority**.</span></span>
    - <span data-ttu-id="81e83-177">**Sökriktningarna:** Välj **Stigande**.</span><span class="sxs-lookup"><span data-stu-id="81e83-177">**Search direction:** Select **Ascending**.</span></span>
    - <span data-ttu-id="81e83-178">**Register:** Välj **Arbete**.</span><span class="sxs-lookup"><span data-stu-id="81e83-178">**Table:** Select **Work**.</span></span>
    - <span data-ttu-id="81e83-179">**Härlett register:** Välj **Arbete**.</span><span class="sxs-lookup"><span data-stu-id="81e83-179">**Derived table:** Select **Work**.</span></span>
    - <span data-ttu-id="81e83-180">**Fält:** Välj **arbets-ID**.</span><span class="sxs-lookup"><span data-stu-id="81e83-180">**Field:** Select **Work ID**.</span></span>
    - <span data-ttu-id="81e83-181">**Sökriktningarna:** Välj **Stigande**.</span><span class="sxs-lookup"><span data-stu-id="81e83-181">**Search direction:** Select **Ascending**.</span></span>

<span data-ttu-id="81e83-182">Systemet sorterar nu arbets-ID:n i klustret, först efter arbetsprioritet och sedan efter arbets-ID.</span><span class="sxs-lookup"><span data-stu-id="81e83-182">The system will now sort work IDs in the cluster, first by work priority and then by work ID.</span></span>

### <a name="set-up-a-mobile-device-menu"></a><span data-ttu-id="81e83-183">Ställ in mobil enhet för lagerställe</span><span class="sxs-lookup"><span data-stu-id="81e83-183">Set up a mobile device menu</span></span>

1. <span data-ttu-id="81e83-184">Gå till **Lagerstyrning \> Inställningar \> Mobil enhet \> Meny på mobil enhet**.</span><span class="sxs-lookup"><span data-stu-id="81e83-184">Go to **Warehouse management \> Setup \> Mobile device \> Mobile device menu**.</span></span>
2. <span data-ttu-id="81e83-185">Lägg till menyalternativet som du nyss skapade i önskad meny.</span><span class="sxs-lookup"><span data-stu-id="81e83-185">Add the menu item that you just created to the desired menu.</span></span>

## <a name="example"></a><span data-ttu-id="81e83-186">Exempel</span><span class="sxs-lookup"><span data-stu-id="81e83-186">Example</span></span>

### <a name="create-picking-work"></a><span data-ttu-id="81e83-187">Skapa plockarbete</span><span class="sxs-lookup"><span data-stu-id="81e83-187">Create picking work</span></span>

<span data-ttu-id="81e83-188">Innan du kan ställa in systemstyrd klusterplockning måste du skapa vissa kvalificerade utgående arbete.</span><span class="sxs-lookup"><span data-stu-id="81e83-188">Before you can set up system-directed cluster picking, you must create some eligible outbound work.</span></span> <span data-ttu-id="81e83-189">Den klusterprofil som du skapade tidigare anger två klusterpositioner.</span><span class="sxs-lookup"><span data-stu-id="81e83-189">The cluster profile that you created earlier specifies two cluster positions.</span></span> <span data-ttu-id="81e83-190">Därför måste du skapa minst två arbets-ID.</span><span class="sxs-lookup"><span data-stu-id="81e83-190">Therefore, you must create at least two work IDs.</span></span>

1. <span data-ttu-id="81e83-191">Gå till **Försäljning och marknadsföring \> Försäljningsorder \> Alla försäljningsorder**.</span><span class="sxs-lookup"><span data-stu-id="81e83-191">Go to **Sales and Marketing \> Sales orders \> All sales orders**.</span></span>
2. <span data-ttu-id="81e83-192">Skapa en försäljningsorder genom att välja **Ny**.</span><span class="sxs-lookup"><span data-stu-id="81e83-192">Select **New** to create a sales order.</span></span>
3. <span data-ttu-id="81e83-193">Markera en kund i fältet **Kundkonto**.</span><span class="sxs-lookup"><span data-stu-id="81e83-193">In the **Customer account** field, select any customer.</span></span>
4. <span data-ttu-id="81e83-194">På snabbfliken **Allmänt** i fältet **Lagerställe**, välj lagerställe **62**.</span><span class="sxs-lookup"><span data-stu-id="81e83-194">On the **General** FastTab, in the **Warehouse** field, select warehouse **62**.</span></span>
5. <span data-ttu-id="81e83-195">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="81e83-195">Select **OK**.</span></span>
6. <span data-ttu-id="81e83-196">På snabbfliken **Försäljningsorderrader** välj **Lägg till rad**.</span><span class="sxs-lookup"><span data-stu-id="81e83-196">On the **Sales order lines** FastTab, select **Add line**.</span></span>
7. <span data-ttu-id="81e83-197">I fältet **Artikelnummer**, välj **A0001**.</span><span class="sxs-lookup"><span data-stu-id="81e83-197">In the **Item number** field, select **A0001**.</span></span>
8. <span data-ttu-id="81e83-198">I fältet **Kvantitet**, ange **1**.</span><span class="sxs-lookup"><span data-stu-id="81e83-198">In the **Quantity** field, enter **1**.</span></span>
9. <span data-ttu-id="81e83-199">Välj **Lägg till rad** för att lägga till en andra rad.</span><span class="sxs-lookup"><span data-stu-id="81e83-199">Select **Add line** to add a second line.</span></span>
10. <span data-ttu-id="81e83-200">I fältet **Artikelnummer**, välj **A0002**.</span><span class="sxs-lookup"><span data-stu-id="81e83-200">In the **Item number** field, select **A0002**.</span></span>
11. <span data-ttu-id="81e83-201">I fältet **Kvantitet**, ange **3**.</span><span class="sxs-lookup"><span data-stu-id="81e83-201">In the **Quantity** field, enter **3**.</span></span>
12. <span data-ttu-id="81e83-202">Upprepa sedan steg 2 till och med 6.</span><span class="sxs-lookup"><span data-stu-id="81e83-202">Repeat steps 2 through 6.</span></span>
13. <span data-ttu-id="81e83-203">I fältet **Artikelnummer**, välj **A0001**.</span><span class="sxs-lookup"><span data-stu-id="81e83-203">In the **Item number** field, select **A0001**.</span></span>
14. <span data-ttu-id="81e83-204">I fältet **Kvantitet**, ange **4**.</span><span class="sxs-lookup"><span data-stu-id="81e83-204">In the **Quantity** field, enter **4**.</span></span>
15. <span data-ttu-id="81e83-205">Välj **Lägg till rad** för att lägga till en andra rad.</span><span class="sxs-lookup"><span data-stu-id="81e83-205">Select **Add line** to add a second line.</span></span>
16. <span data-ttu-id="81e83-206">I fältet **Artikelnummer**, välj **A0002**.</span><span class="sxs-lookup"><span data-stu-id="81e83-206">In the **Item number** field, select **A0002**.</span></span>
17. <span data-ttu-id="81e83-207">I fältet **Kvantitet**, ange **2**.</span><span class="sxs-lookup"><span data-stu-id="81e83-207">In the **Quantity** field, enter **2**.</span></span>

<span data-ttu-id="81e83-208">Reservera lagret och släpp det till lagerställe.</span><span class="sxs-lookup"><span data-stu-id="81e83-208">Reserve the inventory, and release it to the warehouse.</span></span> <span data-ttu-id="81e83-209">Två olika arbets-ID skapas.</span><span class="sxs-lookup"><span data-stu-id="81e83-209">Two different work IDs are created.</span></span> <span data-ttu-id="81e83-210">Varje arbets-ID har två plockningsrader.</span><span class="sxs-lookup"><span data-stu-id="81e83-210">Each work ID has two pick lines.</span></span>

### <a name="run-the-mobile-device-flow"></a><span data-ttu-id="81e83-211">Kör det mobila enhetsflödet</span><span class="sxs-lookup"><span data-stu-id="81e83-211">Run the mobile device flow</span></span>

1. <span data-ttu-id="81e83-212">På den mobila enheten väljer du den meny som innehåller menyalternativet ny mobil enhet.</span><span class="sxs-lookup"><span data-stu-id="81e83-212">On the mobile device, select the menu that includes the new mobile device menu item.</span></span>
2. <span data-ttu-id="81e83-213">Välj menyalternativet **SD-kluster** och initiera plockningen.</span><span class="sxs-lookup"><span data-stu-id="81e83-213">Select the **SD Cluster** menu item, and initiate the pick.</span></span> <span data-ttu-id="81e83-214">Ett kluster skapas och de två arbets-ID:n som du skapade tidigare är kopplade till den.</span><span class="sxs-lookup"><span data-stu-id="81e83-214">A cluster is created, and the two work IDs that you created earlier are attached to it.</span></span> <span data-ttu-id="81e83-215">Om du har skapat fler än två arbets-ID:n läggs bara de första två till i klustret.</span><span class="sxs-lookup"><span data-stu-id="81e83-215">If you created more than two work IDs, only the first two are added to the cluster.</span></span> <span data-ttu-id="81e83-216">Observera att arbets-ID:n läggs till i klustret i stigande ordning, som du angav i frågeinstallationen.</span><span class="sxs-lookup"><span data-stu-id="81e83-216">Notice that the work IDs are added to the cluster in ascending order, as you specified in the query setup.</span></span>

    > [!NOTE]
    > <span data-ttu-id="81e83-217">Det nya klustret skapas automatiskt endast om tillräckligt med ytterligare arbets-ID har skapats tidigare.</span><span class="sxs-lookup"><span data-stu-id="81e83-217">The new cluster is automatically created only if enough additional work IDs were previously created.</span></span> <span data-ttu-id="81e83-218">I annat fall visas följande meddelande: "det går inte att hitta tillräckligt med arbete för klustret."</span><span class="sxs-lookup"><span data-stu-id="81e83-218">Otherwise, the following message is shown: "Not enough work can be found for cluster."</span></span>

    <span data-ttu-id="81e83-219">När du har valt menyn visas den första plockskärmen.</span><span class="sxs-lookup"><span data-stu-id="81e83-219">After you select the menu, the first pick screen appears.</span></span> <span data-ttu-id="81e83-220">Systemet sammanställer alla matchande plockningsrader från de två arbets-ID:n och dirigerar dig att besöka plockplatsen en gång, så att du kan tillfredsställa båda ordrarna genom att använda en plockning.</span><span class="sxs-lookup"><span data-stu-id="81e83-220">The system aggregates all matching pick lines from the two work IDs and directs you to visit the pick location one time, so that you can satisfy both orders by using one pick.</span></span> <span data-ttu-id="81e83-221">Den här processen görs på samma sätt som process för användarstyrd klusterplockning.</span><span class="sxs-lookup"><span data-stu-id="81e83-221">This process is done in the same way as process for user-directed cluster picking.</span></span>

3. <span data-ttu-id="81e83-222">Bekräfta den första plockningen.</span><span class="sxs-lookup"><span data-stu-id="81e83-222">Confirm the first pick.</span></span> <span data-ttu-id="81e83-223">Du måste sedan ange positionsnamnet för att bekräfta att artiklarna har satts till rätt position.</span><span class="sxs-lookup"><span data-stu-id="81e83-223">You must then enter the position name to confirm that the items were put to the correct position.</span></span>
4. <span data-ttu-id="81e83-224">Upprepa den här processen tills alla objekt har plockats och satts till rätt position.</span><span class="sxs-lookup"><span data-stu-id="81e83-224">Repeat this process until all items have been picked and put to the correct position.</span></span>
5. <span data-ttu-id="81e83-225">Det sista steget på den mobila enheten är att placera klustret till den sista platsen.</span><span class="sxs-lookup"><span data-stu-id="81e83-225">The last step on the mobile device is to put the cluster to the final location.</span></span> <span data-ttu-id="81e83-226">När den här placeringsoperationen bekräftas stängs klustret och bryts, baserat på det värde som du anger för fältet **Bryt kluster vid** i klusterprofilen.</span><span class="sxs-lookup"><span data-stu-id="81e83-226">When this put operation is confirmed, the cluster is closed and broken, based on the value that you set for the **Break cluster at** field in the cluster profile.</span></span> <span data-ttu-id="81e83-227">Arbets-ID:n är också stängda.</span><span class="sxs-lookup"><span data-stu-id="81e83-227">Work IDs are also closed.</span></span>
6. <span data-ttu-id="81e83-228">Ett meddelande om att "klustret har slutförts" visas på den mobila enheten.</span><span class="sxs-lookup"><span data-stu-id="81e83-228">A "Cluster complete" message is shown on the mobile device.</span></span>