---
title: Kluster för artikelinförsel
description: Kluster för artikelinförsel erbjuder ett sätt att välja flera ID-nummer samtidigt och sedan ta dem till artikelinförsel på olika platser. De kan vara mycket användbara för butiker, där ID-nummer vanligtvis inte är fullständiga lastpallar med lager.
author: Mirzaab
manager: tfehr
ms.date: 10/19/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-10-19
ms.dyn365.ops.version: Release 10.0.7
ms.openlocfilehash: 297792e90b3d2da0d738f5cbaa14779bc17ea3c8
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "4996208"
---
# <a name="putaway-clusters"></a><span data-ttu-id="8cb61-104">Kluster för artikelinförsel</span><span class="sxs-lookup"><span data-stu-id="8cb61-104">Putaway clusters</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="8cb61-105">Kluster för artikelinförsel erbjuder ett sätt att välja flera ID-nummer samtidigt och sedan ta dem till artikelinförsel på olika platser.</span><span class="sxs-lookup"><span data-stu-id="8cb61-105">Putaway clusters offer a way to pick multiple license plates at the same time and then take them for putaway in different locations.</span></span> <span data-ttu-id="8cb61-106">Den här processen kalla ofta en *slinga*.</span><span class="sxs-lookup"><span data-stu-id="8cb61-106">This process is often referred to as a *milk run*.</span></span> <span data-ttu-id="8cb61-107">Kluster för artikelinförsel kan vara mycket användbara för butiker, där ID-nummer vanligtvis inte är fullständiga lastpallar med lager.</span><span class="sxs-lookup"><span data-stu-id="8cb61-107">Putaway clusters can be very useful for retail businesses, where license plates typically aren't full pallets of inventory.</span></span> 

## <a name="turn-on-the-cluster-putaway-feature"></a><span data-ttu-id="8cb61-108">Aktivera funktionen för kluster för artikelinförsel</span><span class="sxs-lookup"><span data-stu-id="8cb61-108">Turn on the cluster putaway feature</span></span>

<span data-ttu-id="8cb61-109">Innan du kan använda den här funktionen den aktiveras i ditt system.</span><span class="sxs-lookup"><span data-stu-id="8cb61-109">Before you can use this feature, it must be turned on in your system.</span></span> <span data-ttu-id="8cb61-110">Administratörer kan använda arbetsytan [funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) för att kontrollera funktionens status och aktivera den om det behövs.</span><span class="sxs-lookup"><span data-stu-id="8cb61-110">Admins can use the [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) workspace to check the status of the feature and turn it on if it's required.</span></span> <span data-ttu-id="8cb61-111">Funktionen visas på följande sätt:</span><span class="sxs-lookup"><span data-stu-id="8cb61-111">There, the feature is listed in the following way:</span></span>

- <span data-ttu-id="8cb61-112">**Modul:** *Lagerstyrning*</span><span class="sxs-lookup"><span data-stu-id="8cb61-112">**Module:** *Warehouse management*</span></span>
- <span data-ttu-id="8cb61-113">**Funktionens namn:** *Funktion för kluster för artikelinförsel*</span><span class="sxs-lookup"><span data-stu-id="8cb61-113">**Feature name:** *Cluster putaway feature*</span></span>

## <a name="setup-for-the-example-scenario"></a><span data-ttu-id="8cb61-114">Ställ in exempelscenario</span><span class="sxs-lookup"><span data-stu-id="8cb61-114">Setup for the example scenario</span></span>

### <a name="cluster-profiles"></a><span data-ttu-id="8cb61-115">Klusterprofiler</span><span class="sxs-lookup"><span data-stu-id="8cb61-115">Cluster profiles</span></span>

<span data-ttu-id="8cb61-116">Profilen kluster för artikelinförsel avgör var ett objekt ska placeras, baserat på platsen som objektet har tilldelats vid tiden för inleverans.</span><span class="sxs-lookup"><span data-stu-id="8cb61-116">The putaway cluster profile determines where an item will go, based on the location that is assigned to the item at the time of receipt.</span></span> <span data-ttu-id="8cb61-117">Om det krävs olika kluster bör ett annat kluster för artikelinförsel skapas, en för varje menyalternativ för mobila enheter.</span><span class="sxs-lookup"><span data-stu-id="8cb61-117">If different clusters are required, different putaway clusters should be created, one for each mobile device menu item.</span></span>

1. <span data-ttu-id="8cb61-118">Gå till **lagerstyrning \> inställningar \> mobiltelefon \> klusterprofiler**.</span><span class="sxs-lookup"><span data-stu-id="8cb61-118">Go to **Warehouse management \> Setup \> Mobile device \> Cluster profiles**.</span></span>
1. <span data-ttu-id="8cb61-119">Klicka på **Ny** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="8cb61-119">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="8cb61-120">I vyn **Rubrik** anger du följande värden:</span><span class="sxs-lookup"><span data-stu-id="8cb61-120">In the **Header** view, set the following values:</span></span>

    - <span data-ttu-id="8cb61-121">**Profil-ID för kluster för artikelinförsel:** *Kluster för artikelinförsel*</span><span class="sxs-lookup"><span data-stu-id="8cb61-121">**Putaway cluster profile ID:** *Cluster putaway*</span></span>
    - <span data-ttu-id="8cb61-122">**Profil-ID-namn för kluster för artikelinförsel:** *Kluster för artikelinförsel*</span><span class="sxs-lookup"><span data-stu-id="8cb61-122">**Putaway cluster profile ID Name:** *Cluster putaway*</span></span>
    - <span data-ttu-id="8cb61-123">**Klustertyp:** *artikelinförsel*</span><span class="sxs-lookup"><span data-stu-id="8cb61-123">**Cluster type:** *Putaway*</span></span>
    - <span data-ttu-id="8cb61-124">**Löpnummer:** Acceptera standardvärdet.</span><span class="sxs-lookup"><span data-stu-id="8cb61-124">**Sequence number:** Accept the default value.</span></span>

1. <span data-ttu-id="8cb61-125">Välj **Spara** om du vill göra krävda fälten på fliken **Allmänt** tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="8cb61-125">Select **Save** to make the required fields on the **General** FastTab available.</span></span>
1. <span data-ttu-id="8cb61-126">Ange följande värden på snabbfliken **Allmänt**:</span><span class="sxs-lookup"><span data-stu-id="8cb61-126">On the **General** FastTab, set the following values:</span></span>

    - <span data-ttu-id="8cb61-127">**Tidsgränsen för klustertilldelning:** *Vid inleverans*</span><span class="sxs-lookup"><span data-stu-id="8cb61-127">**Cluster assignment timing:** *At receipt*</span></span>

        <span data-ttu-id="8cb61-128">I det här fältet definieras om kluster för artikelinförsel ska tilldelas direkt när lagret tas emot, eller om det ska sorteras senare.</span><span class="sxs-lookup"><span data-stu-id="8cb61-128">This field defines whether the putaway cluster should be assigned immediately when the inventory is received, or whether it should be sorted later.</span></span>

    - <span data-ttu-id="8cb61-129">**Regel för klustertilldelning:** *manuell*</span><span class="sxs-lookup"><span data-stu-id="8cb61-129">**Cluster assignment rule:** *Manual*</span></span>

        <span data-ttu-id="8cb61-130">Fältet definierar om klustertilldelningen ska bestämmas automatiskt av systemet eller manuellt av användaren.</span><span class="sxs-lookup"><span data-stu-id="8cb61-130">This field defines whether the cluster assignment should be determined automatically by the system or manually by the user.</span></span>

    - <span data-ttu-id="8cb61-131">**Direktivkod:** Lämna det här fältet tomt.</span><span class="sxs-lookup"><span data-stu-id="8cb61-131">**Directive code:** Leave this field blank.</span></span>
    - <span data-ttu-id="8cb61-132">**Lokalisera kluster för artikelinförsel:** *Inleverans*</span><span class="sxs-lookup"><span data-stu-id="8cb61-132">**Putaway cluster locate:** *Receipt*</span></span>

        <span data-ttu-id="8cb61-133">Följande värden finns:</span><span class="sxs-lookup"><span data-stu-id="8cb61-133">The following values are available:</span></span>

        - <span data-ttu-id="8cb61-134">**Inleverans** – En plats hittades omedelbart under inleveransen.</span><span class="sxs-lookup"><span data-stu-id="8cb61-134">**Receipt** – A location is found immediately during receipt.</span></span>
        - <span data-ttu-id="8cb61-135">**Klusterstängning** – En plats hittades när klustret är stängt.</span><span class="sxs-lookup"><span data-stu-id="8cb61-135">**Cluster close** – A location is found when the cluster is closed.</span></span>
        - <span data-ttu-id="8cb61-136">**Användarriktad** – en plats hittas när ID-numret plockas från klustret för artikelinförsel.</span><span class="sxs-lookup"><span data-stu-id="8cb61-136">**User directed** – A location is found when the license plate is picked from the cluster for putaway.</span></span> <span data-ttu-id="8cb61-137">I det här fallet anges ingen plats när artikelinförselarbete skapas.</span><span class="sxs-lookup"><span data-stu-id="8cb61-137">In this case, no location is specified when the putaway work is created.</span></span> <span data-ttu-id="8cb61-138">Under själva artikelinförseln måste användaren söka igenom ID-numret eller arbets-ID för att initiera steget.</span><span class="sxs-lookup"><span data-stu-id="8cb61-138">During the putaway itself, the user must scan the license plate or work ID to initiate the put step.</span></span> <span data-ttu-id="8cb61-139">Systemet söker sedan efter platsen igen och talar om för användaren var den plockade kvantiteten ska placeras.</span><span class="sxs-lookup"><span data-stu-id="8cb61-139">The system then finds the put location again and tells the user where to put the picked quantity.</span></span>

    - <span data-ttu-id="8cb61-140">**Kluster för artikelinförsel:** *Nej*</span><span class="sxs-lookup"><span data-stu-id="8cb61-140">**Putaway cluster per user:** *No*</span></span>

        <span data-ttu-id="8cb61-141">I det här fältet anges om varje kluster måste vara unikt för varje användare när kluster tilldelas automatiskt.</span><span class="sxs-lookup"><span data-stu-id="8cb61-141">This field defines whether each cluster should be unique per user when clusters are automatically assigned.</span></span> <span data-ttu-id="8cb61-142">Den är bara tillgänglig när fältet **Klustertilldelningsregel** anges till *automatisk*.</span><span class="sxs-lookup"><span data-stu-id="8cb61-142">It's available only when the **Cluster assignment rule** field is set to *Automatic*.</span></span>

    - <span data-ttu-id="8cb61-143">**Enhetsbegränsning:** lämna det här fältet tomt.</span><span class="sxs-lookup"><span data-stu-id="8cb61-143">**Unit restriction:** Leave this field blank.</span></span>

        <span data-ttu-id="8cb61-144">I det här fältet definieras den enhet som måste inlevereras för att profilen ska gälla.</span><span class="sxs-lookup"><span data-stu-id="8cb61-144">This field defines the unit that must be received for the profile to be valid.</span></span> <span data-ttu-id="8cb61-145">Om den lämnas tom är alla enheter giltiga.</span><span class="sxs-lookup"><span data-stu-id="8cb61-145">If it's left blank, all units are valid.</span></span>

    - <span data-ttu-id="8cb61-146">**Arbetsenhetsavbrott:** *individuell*</span><span class="sxs-lookup"><span data-stu-id="8cb61-146">**Work unit break:** *Individual*</span></span>

        <span data-ttu-id="8cb61-147">I det här fältet anges om alla lager ska konsolideras (med hjälp av kluster-ID och ID-nummer) till ett ID-nummer när ett kluster stängs och om det ska föras in som en enskild ID-nummer eller separat på ID-numren som togs emot.</span><span class="sxs-lookup"><span data-stu-id="8cb61-147">This field defines whether all inventory should be consolidated (by using the cluster ID and the license plate) onto one license plate when a cluster is closed, and whether it should be put away as a single license plate or separately on the license plates that were received.</span></span> <span data-ttu-id="8cb61-148">Det här fältet är inte tillgängligt om fältet **Lokalisera kluster för artikelinförsel** anges till *Inleverans*.</span><span class="sxs-lookup"><span data-stu-id="8cb61-148">This field is unavailable when the **Putaway cluster locate** field is set to *Receipt*.</span></span>

    - <span data-ttu-id="8cb61-149">**Kluster finns kvar som överordnat ID-nummer:** *Nej*</span><span class="sxs-lookup"><span data-stu-id="8cb61-149">**Cluster persists as Parent License Plate:** *No*</span></span>

        <span data-ttu-id="8cb61-150">Om det här alternativet är inställt på *Ja*, när inlagringssteget är slutfört blir kluster-ID ett överordnat ID-nummer och alla artiklar på kluster-ID kommer att länkas till det överordnade ID-numret.</span><span class="sxs-lookup"><span data-stu-id="8cb61-150">If this option is set to *Yes*, when the put step is completed, the cluster ID will become a parent license plate, and all items on the cluster ID will be linked to that parent license plate.</span></span>

1. <span data-ttu-id="8cb61-151">På snabbfliken **klustersortering** kan du definiera sorteringskriterier för artikelinförsel.</span><span class="sxs-lookup"><span data-stu-id="8cb61-151">On the **Cluster sorting** FastTab, you can define putaway sorting criteria.</span></span> <span data-ttu-id="8cb61-152">Välj **Ny** på verktygsfältet för att lägga till en andra rad och ställa sedan in följande värden för den:</span><span class="sxs-lookup"><span data-stu-id="8cb61-152">Select **New** on the toolbar to add a line, and then set the following values:</span></span>

    - <span data-ttu-id="8cb61-153">**Löpnummer:** Acceptera standardvärdet.</span><span class="sxs-lookup"><span data-stu-id="8cb61-153">**Sequence number:** Accept the default value.</span></span>
    - <span data-ttu-id="8cb61-154">**Fältnamn:** *WMSLocationId*</span><span class="sxs-lookup"><span data-stu-id="8cb61-154">**Field name:** *WMSLocationId*</span></span>

        <span data-ttu-id="8cb61-155">Det här fältet definierar det fält som den här raden ska använda som ett sorteringskriterium.</span><span class="sxs-lookup"><span data-stu-id="8cb61-155">This field defines the field that this line should use as a sorting criterion.</span></span>

    - <span data-ttu-id="8cb61-156">**Sortera:** *stigande*</span><span class="sxs-lookup"><span data-stu-id="8cb61-156">**Sorting:** *Ascending*</span></span>

        <span data-ttu-id="8cb61-157">Det här fältet anger om sorteringen görs i stigande eller fallande ordning.</span><span class="sxs-lookup"><span data-stu-id="8cb61-157">This field defines whether sorting should be done in ascending or descending order.</span></span>

1. <span data-ttu-id="8cb61-158">På snabbfliken **Arbetsmallar för kluster** välj **Ny** på verktygsfältet för att lägga till en rad och anger sedan följande värden:</span><span class="sxs-lookup"><span data-stu-id="8cb61-158">On the **Cluster work template** FastTab, select **New** on the toolbar to add a line, and then set the following values:</span></span>

    - <span data-ttu-id="8cb61-159">**Arbetsordertyp:** *inköpsorder*</span><span class="sxs-lookup"><span data-stu-id="8cb61-159">**Work order type:** *Purchase orders*</span></span>
    - <span data-ttu-id="8cb61-160">**Arbetsmallen:** *61 PO direkt*</span><span class="sxs-lookup"><span data-stu-id="8cb61-160">**Work template:** *61 PO Direct*</span></span>

1. <span data-ttu-id="8cb61-161">I åtgärdsrutan väljer du **Spara** och välj sedan **Redigera fråga**.</span><span class="sxs-lookup"><span data-stu-id="8cb61-161">On the Action Pane, select **Save**, and then select **Edit query**.</span></span>
1. <span data-ttu-id="8cb61-162">I dialogrutan **kluster för artikelinförsel** på fliken **Intervall**, välj **Lägg till** om du vill lägga till en andra rad i frågan.</span><span class="sxs-lookup"><span data-stu-id="8cb61-162">In the **Cluster putaway** dialog box, on the **Range** tab, select **Add** to add a second line to the query.</span></span> <span data-ttu-id="8cb61-163">Uppdatera sedan raderna som visas i följande tabell.</span><span class="sxs-lookup"><span data-stu-id="8cb61-163">Then update the query lines as shown in the following table.</span></span>

    | <span data-ttu-id="8cb61-164">Register</span><span class="sxs-lookup"><span data-stu-id="8cb61-164">Table</span></span> | <span data-ttu-id="8cb61-165">Härlett register</span><span class="sxs-lookup"><span data-stu-id="8cb61-165">Derived table</span></span> | <span data-ttu-id="8cb61-166">Fält</span><span class="sxs-lookup"><span data-stu-id="8cb61-166">Field</span></span> | <span data-ttu-id="8cb61-167">Villkor</span><span class="sxs-lookup"><span data-stu-id="8cb61-167">Criteria</span></span> |
    |---|---|---|---|
    | <span data-ttu-id="8cb61-168">Arbete</span><span class="sxs-lookup"><span data-stu-id="8cb61-168">Work</span></span> | <span data-ttu-id="8cb61-169">Arbete</span><span class="sxs-lookup"><span data-stu-id="8cb61-169">Work</span></span> | <span data-ttu-id="8cb61-170">Lagerställe</span><span class="sxs-lookup"><span data-stu-id="8cb61-170">Warehouse</span></span> | <span data-ttu-id="8cb61-171">*61*</span><span class="sxs-lookup"><span data-stu-id="8cb61-171">*61*</span></span> |
    | <span data-ttu-id="8cb61-172">Arbete</span><span class="sxs-lookup"><span data-stu-id="8cb61-172">Work</span></span> | <span data-ttu-id="8cb61-173">Arbete</span><span class="sxs-lookup"><span data-stu-id="8cb61-173">Work</span></span> | <span data-ttu-id="8cb61-174">Arbets-ID</span><span class="sxs-lookup"><span data-stu-id="8cb61-174">Work ID</span></span> | <span data-ttu-id="8cb61-175">Lämna det här fältet tomt.</span><span class="sxs-lookup"><span data-stu-id="8cb61-175">Leave this field blank.</span></span> |

1. <span data-ttu-id="8cb61-176">Välj **OK** om du vill spara frågan och stänga dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="8cb61-176">Select **OK** to save the query and close the dialog box.</span></span>
1. <span data-ttu-id="8cb61-177">Välj **Spara** i åtgärdsfönstret och stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="8cb61-177">On the Action Pane, select **Save**, and close the page.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8cb61-178">Fält i klusterprofilen som är nedtonade när **Genera kluster-ID** anges till *Ja* är inte tillgängligt och kommer inte att beaktas när den här funktionen används.</span><span class="sxs-lookup"><span data-stu-id="8cb61-178">Fields in the cluster profile that appear dimmed when **Generate cluster ID** is set to *Yes* are unavailable and won't be considered when this feature is used.</span></span>

### <a name="mobile-device-menu-items"></a><span data-ttu-id="8cb61-179">Menyalternativ på mobil enhet</span><span class="sxs-lookup"><span data-stu-id="8cb61-179">Mobile device menu items</span></span>

<span data-ttu-id="8cb61-180">Det finns två nya menyartiklar för mobila enheter för den här funktionen.</span><span class="sxs-lookup"><span data-stu-id="8cb61-180">Two new mobile device menu items are available for this feature.</span></span> <span data-ttu-id="8cb61-181">Menyalternativet **Inleverera och sortera kluster** används för att inleverera lager i ett kluster för artikelinförsel vid mottagning.</span><span class="sxs-lookup"><span data-stu-id="8cb61-181">The **Receive and sort cluster** menu item is used to sort the received inventory into a putaway cluster upon receipt.</span></span> <span data-ttu-id="8cb61-182">Menyartikeln **kluster för artikelinförsel** används för att placera klustret efter att det har tilldelats.</span><span class="sxs-lookup"><span data-stu-id="8cb61-182">The **Cluster putaway** menu item is used to put the cluster away after it has been assigned.</span></span>

#### <a name="receive-and-sort-cluster"></a><span data-ttu-id="8cb61-183">Ta emot och sortera kluster</span><span class="sxs-lookup"><span data-stu-id="8cb61-183">Receive and sort cluster</span></span>

<span data-ttu-id="8cb61-184">Skapa ett nytt menyalternativ för mobil enhet för mottagning av lager och sortering i ett kluster.</span><span class="sxs-lookup"><span data-stu-id="8cb61-184">Create a new mobile device menu item for receiving inventory and sorting into a cluster.</span></span> <span data-ttu-id="8cb61-185">Det här menyalternativet skapar inkommande arbete efter att lagret mottagits, vilket anger att det mottagande menyobjektet ska användas för kluster för artikelinförsel.</span><span class="sxs-lookup"><span data-stu-id="8cb61-185">This menu item will create inbound work after inventory is received, which indicates that the receiving menu item will be used for putaway clusters.</span></span>

> [!NOTE]
> <span data-ttu-id="8cb61-186">Menyalternativet **ta emot och sortera kluster** kan användas med följande menyalternativ för mottagning:</span><span class="sxs-lookup"><span data-stu-id="8cb61-186">The **Receive and sort cluster** menu item can be used with the following receiving menu items:</span></span>
>
> - <span data-ttu-id="8cb61-187">Inleverans av inköpsorderrad</span><span class="sxs-lookup"><span data-stu-id="8cb61-187">Purchase order line receiving</span></span>
> - <span data-ttu-id="8cb61-188">Inleverans av inköpsorderartikel</span><span class="sxs-lookup"><span data-stu-id="8cb61-188">Purchase order item receiving</span></span>
> - <span data-ttu-id="8cb61-189">Mottagande av lastartikel</span><span class="sxs-lookup"><span data-stu-id="8cb61-189">Load item receiving</span></span>

1. <span data-ttu-id="8cb61-190">Gå till **Lagerstyrning \> Inställningar \> Mobil enhet \> Menyalternativ på mobil enhet**.</span><span class="sxs-lookup"><span data-stu-id="8cb61-190">Go to **Warehouse management \> Setup \> Mobile device \> Mobile device menu items**.</span></span>
1. <span data-ttu-id="8cb61-191">Klicka på **Ny** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="8cb61-191">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="8cb61-192">I vyn **Rubrik** anger du följande värden:</span><span class="sxs-lookup"><span data-stu-id="8cb61-192">In the **Header** view, set the following values:</span></span>

    - <span data-ttu-id="8cb61-193">**Menyalternativnamn:** *ta emot och sortera kluster*</span><span class="sxs-lookup"><span data-stu-id="8cb61-193">**Menu item name:** *Receive and sort cluster*</span></span>
    - <span data-ttu-id="8cb61-194">**Titel:** *Ta emot och sortera kluster*</span><span class="sxs-lookup"><span data-stu-id="8cb61-194">**Title:** *Receive and sort cluster*</span></span>
    - <span data-ttu-id="8cb61-195">**Läge:** *arbete*</span><span class="sxs-lookup"><span data-stu-id="8cb61-195">**Mode:** *Work*</span></span>
    - <span data-ttu-id="8cb61-196">**Använd befintligt arbete:** *Nej*</span><span class="sxs-lookup"><span data-stu-id="8cb61-196">**Use existing work:** *No*</span></span>

1. <span data-ttu-id="8cb61-197">Ange följande värden på snabbfliken **Allmänt**:</span><span class="sxs-lookup"><span data-stu-id="8cb61-197">On the **General** FastTab, set the following values:</span></span>

    - <span data-ttu-id="8cb61-198">**Arbetsskapandeprocess:** *Inköpsorderpost har inlevererats*</span><span class="sxs-lookup"><span data-stu-id="8cb61-198">**Work creation process:** *Purchase order item receiving*</span></span>
    - <span data-ttu-id="8cb61-199">**Generera ID-nummer:** *Ja*</span><span class="sxs-lookup"><span data-stu-id="8cb61-199">**Generate license plate:** *Yes*</span></span>
    - <span data-ttu-id="8cb61-200">**Tilldela kluster för artikelinförsel:** *Ja*</span><span class="sxs-lookup"><span data-stu-id="8cb61-200">**Assign putaway cluster:** *Yes*</span></span>

        > [!NOTE]
        > <span data-ttu-id="8cb61-201">Alternativet **Tilldela kluster för artikelinförsel** är bara tillgängligt för aktiviteten skapa ett steg i *Arbetsskapandeprocess* för mottagning.</span><span class="sxs-lookup"><span data-stu-id="8cb61-201">The **Assign putaway cluster** option is available only for the one-step *Work creation process* activity for receiving.</span></span>

    <span data-ttu-id="8cb61-202">Acceptera standardvärden för kvarvarande fält.</span><span class="sxs-lookup"><span data-stu-id="8cb61-202">Accept the default values for the remaining fields.</span></span>

1. <span data-ttu-id="8cb61-203">Klicka på **Spara** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="8cb61-203">On the Action Pane, select **Save**.</span></span>

#### <a name="cluster-putaway"></a><span data-ttu-id="8cb61-204">Klusterplats</span><span class="sxs-lookup"><span data-stu-id="8cb61-204">Cluster putaway</span></span>

<span data-ttu-id="8cb61-205">Skapa ett nytt menyalternativ för mobila enheter för att sätta klustret i en annan plats efter att det har tilldelats.</span><span class="sxs-lookup"><span data-stu-id="8cb61-205">Create a new mobile device menu item for putting the cluster away after it has been assigned.</span></span>

1. <span data-ttu-id="8cb61-206">Gå till **Lagerstyrning \> Inställningar \> Mobil enhet \> Menyalternativ på mobil enhet**.</span><span class="sxs-lookup"><span data-stu-id="8cb61-206">Go to **Warehouse management \> Setup \> Mobile device \> Mobile device menu items**.</span></span>
1. <span data-ttu-id="8cb61-207">Klicka på **Ny** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="8cb61-207">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="8cb61-208">I vyn **Rubrik** anger du följande värden:</span><span class="sxs-lookup"><span data-stu-id="8cb61-208">In the **Header** view, set the following values:</span></span>

    - <span data-ttu-id="8cb61-209">**Menyalternativnamn:** *kluster för artikelinförsel*</span><span class="sxs-lookup"><span data-stu-id="8cb61-209">**Menu item name:** *Cluster putaway*</span></span>
    - <span data-ttu-id="8cb61-210">**Titel:** *kluster för artikelinförsel*</span><span class="sxs-lookup"><span data-stu-id="8cb61-210">**Title:** *Cluster putaway*</span></span>
    - <span data-ttu-id="8cb61-211">**Läge:** *arbete*</span><span class="sxs-lookup"><span data-stu-id="8cb61-211">**Mode:** *Work*</span></span>
    - <span data-ttu-id="8cb61-212">**Använd befintligt arbete:** *Ja*</span><span class="sxs-lookup"><span data-stu-id="8cb61-212">**Use existing work:** *Yes*</span></span>

1. <span data-ttu-id="8cb61-213">På snabbfliken **Allmänt** ska fältet **Dirigerad av** bör ställas in på *kluster för artikelinförsel*.</span><span class="sxs-lookup"><span data-stu-id="8cb61-213">On the **General** FastTab, set the **Directed by** field to *Cluster putaway*.</span></span> <span data-ttu-id="8cb61-214">Acceptera standardvärden för kvarvarande fält.</span><span class="sxs-lookup"><span data-stu-id="8cb61-214">Accept the default values for the remaining fields.</span></span>
1. <span data-ttu-id="8cb61-215">På snabbfliken **Arbetsklasser** ställer du in den giltiga arbetsklassen för denna menyartikel för mobila enheter:</span><span class="sxs-lookup"><span data-stu-id="8cb61-215">On the **Work classes** FastTab, set up the valid work class for this mobile device menu item:</span></span>

    - <span data-ttu-id="8cb61-216">**Arbetsklass-ID:** *Inköp*</span><span class="sxs-lookup"><span data-stu-id="8cb61-216">**Work class ID:** *Purchase*</span></span>
    - <span data-ttu-id="8cb61-217">**Arbetsordertyp:** *inköpsorder*</span><span class="sxs-lookup"><span data-stu-id="8cb61-217">**Work order type:** *Purchase orders*</span></span>

1. <span data-ttu-id="8cb61-218">Klicka på **Spara** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="8cb61-218">On the Action Pane, select **Save**.</span></span>

### <a name="mobile-device-menu"></a><span data-ttu-id="8cb61-219">Meny på mobil enhet</span><span class="sxs-lookup"><span data-stu-id="8cb61-219">Mobile device menu</span></span>

<span data-ttu-id="8cb61-220">Lägg till de menyalternativ som du just har skapat på inkommande menyn för mobilappen.</span><span class="sxs-lookup"><span data-stu-id="8cb61-220">Add the menu items that you just created to the inbound menu of the mobile app.</span></span>

1. <span data-ttu-id="8cb61-221">Gå till **Lagerstyrning \> Inställningar \> Mobil enhet \> Meny på mobil enhet**.</span><span class="sxs-lookup"><span data-stu-id="8cb61-221">Go to **Warehouse management \> Setup \> Mobile device \> Mobile device menu**.</span></span>
1. <span data-ttu-id="8cb61-222">I åtgärdsfönstret väljer du **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="8cb61-222">On the Action Pane, select **Edit**.</span></span>
1. <span data-ttu-id="8cb61-223">I menylistan, välj **Inkommande**.</span><span class="sxs-lookup"><span data-stu-id="8cb61-223">In the menu list, select **Inbound**.</span></span>
1. <span data-ttu-id="8cb61-224">I listan **Tillgängliga menyer och menyartiklar** hittar du och väljer menyalternativet **Ta emot och sortera kluster**.</span><span class="sxs-lookup"><span data-stu-id="8cb61-224">In the **Available menus and menu items** list, find and select **Receive and sort cluster**.</span></span>
1. <span data-ttu-id="8cb61-225">Klicka på högerpilen för att flytta det valda menyalternativet till listan **Menystruktur**.</span><span class="sxs-lookup"><span data-stu-id="8cb61-225">Select the right arrow button to move the selected menu item to the **Menu structure** list.</span></span>
1. <span data-ttu-id="8cb61-226">Använd uppilen eller nedpilen om du vill flytta menyalternativet till önskad plats på menyn.</span><span class="sxs-lookup"><span data-stu-id="8cb61-226">Use the up arrow or down arrow button to move the menu item into the desired position in the menu.</span></span>
1. <span data-ttu-id="8cb61-227">Klicka på **Spara** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="8cb61-227">On the Action Pane, select **Save**.</span></span>
1. <span data-ttu-id="8cb61-228">Upprepa steg 4 till och med 7 om du vill lägga till resterande menyartiklar.</span><span class="sxs-lookup"><span data-stu-id="8cb61-228">Repeat steps 4 through 7 to add the remaining menu items:</span></span>

    - <span data-ttu-id="8cb61-229">Tilldela kluster</span><span class="sxs-lookup"><span data-stu-id="8cb61-229">Assign cluster</span></span>
    - <span data-ttu-id="8cb61-230">Klusterplats</span><span class="sxs-lookup"><span data-stu-id="8cb61-230">Cluster putaway</span></span>

## <a name="example-scenario"></a><span data-ttu-id="8cb61-231">Exempelscenario</span><span class="sxs-lookup"><span data-stu-id="8cb61-231">Example scenario</span></span>

<span data-ttu-id="8cb61-232">Det här scenariot simulerar bearbetning av kluster för artikelinförsel.</span><span class="sxs-lookup"><span data-stu-id="8cb61-232">This scenario simulates putaway cluster processing.</span></span>

### <a name="create-a-purchase-order"></a><span data-ttu-id="8cb61-233">Skapa en inköpsorder</span><span class="sxs-lookup"><span data-stu-id="8cb61-233">Create a purchase order</span></span>

1. <span data-ttu-id="8cb61-234">Gå till **Leverantörsreskontra \> Inköpsorder \> Alla inköpsorder**.</span><span class="sxs-lookup"><span data-stu-id="8cb61-234">Go to **Accounts payable \> Purchase orders \> All purchase orders**.</span></span>
1. <span data-ttu-id="8cb61-235">Klicka på **Ny** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="8cb61-235">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="8cb61-236">I dialogrutan **Skapa inköpsorder** ställ in följande värden:</span><span class="sxs-lookup"><span data-stu-id="8cb61-236">In the **Create purchase order** dialog box, set the following values:</span></span>

    - <span data-ttu-id="8cb61-237">**Leverantörskonto:** *1001*</span><span class="sxs-lookup"><span data-stu-id="8cb61-237">**Vendor account:** *1001*</span></span>
    - <span data-ttu-id="8cb61-238">**Lagerställe:** *61*</span><span class="sxs-lookup"><span data-stu-id="8cb61-238">**Warehouse:** *61*</span></span>

1. <span data-ttu-id="8cb61-239">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="8cb61-239">Select **OK**.</span></span>

    <span data-ttu-id="8cb61-240">Sidan **Alla försäljningsorder** visas.</span><span class="sxs-lookup"><span data-stu-id="8cb61-240">The **All purchase orders** page appears.</span></span>

1. <span data-ttu-id="8cb61-241">På sidan **Alla inköpsorder** på snabbfliken **Inköpsorderrader** använder du knappen **Lägg till rad** för att lägga till följande rader:</span><span class="sxs-lookup"><span data-stu-id="8cb61-241">On the **All purchase orders** page, on the **Purchase order lines** FastTab, use the **Add line** button to add the following lines:</span></span>

    - <span data-ttu-id="8cb61-242">Inköpsorderrad 1:</span><span class="sxs-lookup"><span data-stu-id="8cb61-242">Purchase order line 1:</span></span>

        - <span data-ttu-id="8cb61-243">**Artikelnummer:** *A0001*</span><span class="sxs-lookup"><span data-stu-id="8cb61-243">**Item number:** *A0001*</span></span>
        - <span data-ttu-id="8cb61-244">**Kvantitet:** *10*</span><span class="sxs-lookup"><span data-stu-id="8cb61-244">**Quantity:** *10*</span></span>

    - <span data-ttu-id="8cb61-245">Inköpsorderrad 2:</span><span class="sxs-lookup"><span data-stu-id="8cb61-245">Purchase order line 2:</span></span>

        - <span data-ttu-id="8cb61-246">**Artikelnummer:** *A0002*</span><span class="sxs-lookup"><span data-stu-id="8cb61-246">**Item number:** *A0002*</span></span>
        - <span data-ttu-id="8cb61-247">**Kvantitet:** *20*</span><span class="sxs-lookup"><span data-stu-id="8cb61-247">**Quantity:** *20*</span></span>

    - <span data-ttu-id="8cb61-248">Inköpsorderrad 3:</span><span class="sxs-lookup"><span data-stu-id="8cb61-248">Purchase order line 3:</span></span>

        - <span data-ttu-id="8cb61-249">**Artikelnummer:** *M9215*</span><span class="sxs-lookup"><span data-stu-id="8cb61-249">**Item number:** *M9215*</span></span>
        - <span data-ttu-id="8cb61-250">**Kvantitet:** *30*</span><span class="sxs-lookup"><span data-stu-id="8cb61-250">**Quantity:** *30*</span></span>

1. <span data-ttu-id="8cb61-251">Klicka på **Spara** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="8cb61-251">On the Action Pane, select **Save**.</span></span>
1. <span data-ttu-id="8cb61-252">Anteckna inköpsordernumret.</span><span class="sxs-lookup"><span data-stu-id="8cb61-252">Make a note of the purchase order number.</span></span>

### <a name="receive-inventory-and-put-it-away-from-the-mobile-device"></a><span data-ttu-id="8cb61-253">Ta emot lager och placera det utanför den mobila enheten</span><span class="sxs-lookup"><span data-stu-id="8cb61-253">Receive inventory and put it away from the mobile device</span></span>

#### <a name="receive-and-sort-the-inventory-into-a-cluster"></a><span data-ttu-id="8cb61-254">Ta emot och sortera lagret i ett kluster</span><span class="sxs-lookup"><span data-stu-id="8cb61-254">Receive and sort the inventory into a cluster</span></span>

1. <span data-ttu-id="8cb61-255">Logga in på lagerställeappen som en användare som är konfigurerad för lagerstället *61*.</span><span class="sxs-lookup"><span data-stu-id="8cb61-255">Sign in to the warehouse app as a user who is set up for warehouse *61*.</span></span>
1. <span data-ttu-id="8cb61-256">I huvudmenyn, välj **ingående**.</span><span class="sxs-lookup"><span data-stu-id="8cb61-256">On the main menu, select **Inbound**.</span></span>
1. <span data-ttu-id="8cb61-257">I menyn **Ingående** välj **Ta emot och sortera kluster**.</span><span class="sxs-lookup"><span data-stu-id="8cb61-257">On the **Inbound** menu, select **Receive and sort cluster**.</span></span>
1. <span data-ttu-id="8cb61-258">I fältet **Ponum** anger du inköpsordernummer.</span><span class="sxs-lookup"><span data-stu-id="8cb61-258">In the **Ponum** field, enter the purchase order number.</span></span>
1. <span data-ttu-id="8cb61-259">Välj **OK** (bockmarkeringsknappen).</span><span class="sxs-lookup"><span data-stu-id="8cb61-259">Select **OK** (the check mark button).</span></span>
1. <span data-ttu-id="8cb61-260">Markera fältet **Artikel** ange artikelnummer *A0001* och välj sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="8cb61-260">Select the **Item** field, enter item number *A0001*, and then select **OK**.</span></span>
1. <span data-ttu-id="8cb61-261">Markera fältet **Kvt** ange *10* med hjälp av det numeriska tangentbordet och sedan bockmarkeringsknappen.</span><span class="sxs-lookup"><span data-stu-id="8cb61-261">Select the **Qty** field, enter *10* by using the number pad, and then select the check mark button.</span></span>
1. <span data-ttu-id="8cb61-262">På sidan **Kvt** välj **OK** (bockmarkeringsknappen) för att bekräfta kvantiteten som du har angett.</span><span class="sxs-lookup"><span data-stu-id="8cb61-262">On the **Qty** task page, select **OK** (the check mark button) to confirm the quantity that you entered.</span></span>
1. <span data-ttu-id="8cb61-263">På sidan **artikel** välj **OK** för att bekräfta att artikeln *A0001* har registrerats.</span><span class="sxs-lookup"><span data-stu-id="8cb61-263">On the **Item** task page, select **OK** to confirm that item *A0001* was entered.</span></span>
1. <span data-ttu-id="8cb61-264">Markera fältet **kluster-ID** och ange ett ID för klustret som du ska skapa.</span><span class="sxs-lookup"><span data-stu-id="8cb61-264">Select the **Cluster ID** field, and enter a value to assign an ID for the cluster that you're creating.</span></span>

    <span data-ttu-id="8cb61-265">Det ID som du anger här kommer att användas när de två återstående artiklarna på inköpsordern inlevereras.</span><span class="sxs-lookup"><span data-stu-id="8cb61-265">The ID that you enter here will be used when the two remaining items on the purchase order are received.</span></span>

1. <span data-ttu-id="8cb61-266">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="8cb61-266">Select **OK**.</span></span>

    <span data-ttu-id="8cb61-267">Uppgiftssidan **Ponum** visas och visar meddelandet "Arbetet slutfört".</span><span class="sxs-lookup"><span data-stu-id="8cb61-267">The **Ponum** task page appears and shows a "Work completed" message.</span></span>

    <span data-ttu-id="8cb61-268">Artikeln *A0001* har nu tagits emot på platsen *RECV* och tilldelats det kluster-ID som du angav i steg 10.</span><span class="sxs-lookup"><span data-stu-id="8cb61-268">Item *A0001* has now been received into the *RECV* location and assigned to the cluster ID that you entered in step 10.</span></span>

1. <span data-ttu-id="8cb61-269">Upprepa steg 4 till 11 om du vill ta emot de återstående två artiklarna från inköpsordern och tilldela dem till kluster-ID:</span><span class="sxs-lookup"><span data-stu-id="8cb61-269">Repeat steps 4 through 11 to receive the remaining two items from the purchase order and assign them to the cluster ID:</span></span>

    - <span data-ttu-id="8cb61-270">En kvantitet på *20* för artikel *A0002*</span><span class="sxs-lookup"><span data-stu-id="8cb61-270">A quantity of *20* for item *A0002*</span></span>
    - <span data-ttu-id="8cb61-271">En kvantitet på *30* för artikel *M9215*</span><span class="sxs-lookup"><span data-stu-id="8cb61-271">A quantity of *30* for item *M9215*</span></span>

#### <a name="close-the-cluster"></a><span data-ttu-id="8cb61-272">Stäng klustret</span><span class="sxs-lookup"><span data-stu-id="8cb61-272">Close the cluster</span></span>

<span data-ttu-id="8cb61-273">Klustret måste vara stängt innan artiklarna i klustret kan föras in.</span><span class="sxs-lookup"><span data-stu-id="8cb61-273">Before the items in the cluster can be put away, the cluster must be closed.</span></span>

1. <span data-ttu-id="8cb61-274">I Supply Chain Management, gå till **Lagerhantering \> Arbete \> Utgående \> Arbetskluster**.</span><span class="sxs-lookup"><span data-stu-id="8cb61-274">In Supply Chain Management, go to **Warehouse management \> Work \> Outbound \> Work clusters**.</span></span>
1. <span data-ttu-id="8cb61-275">På sidan **Arbetskluster** i avsnittet **Arbetskluster**, sök fältet **Kluster-ID** för det kluster-ID som du angav tidigare.</span><span class="sxs-lookup"><span data-stu-id="8cb61-275">On the **Work clusters** page, in the **Work cluster** section, search the **Cluster ID** field for the cluster ID that you entered earlier.</span></span>
1. <span data-ttu-id="8cb61-276">Om klustret inte visas kan det redan ha stängts.</span><span class="sxs-lookup"><span data-stu-id="8cb61-276">If the cluster isn't shown, it might already have been closed.</span></span> <span data-ttu-id="8cb61-277">Om du vill ta reda på om klustret har stängts markerar du kryssrutan **Visa stängt arbete** och söker efter det kluster-ID som du angav tidigare.</span><span class="sxs-lookup"><span data-stu-id="8cb61-277">To determine whether the cluster was closed, select the **Show closed work** check box, and search for the cluster ID that you entered earlier.</span></span> <span data-ttu-id="8cb61-278">Gör sedan något av följande:</span><span class="sxs-lookup"><span data-stu-id="8cb61-278">Then follow one of these steps:</span></span>

    - <span data-ttu-id="8cb61-279">Om klustret har stängts hoppar du över de återstående stegen för den här proceduren och går vidare till nästa procedur, [placera klustret](#put-the-cluster-away).</span><span class="sxs-lookup"><span data-stu-id="8cb61-279">If the cluster has been closed, skip the remaining steps of this procedure, and move on to the next procedure, [Put the cluster away](#put-the-cluster-away).</span></span>
    - <span data-ttu-id="8cb61-280">Om klustret inte har stängts följer du de återstående stegen i den här proceduren för att stänga klustret manuellt.</span><span class="sxs-lookup"><span data-stu-id="8cb61-280">If the cluster hasn't been closed, follow the remaining steps of this procedure to manually close the cluster.</span></span> <span data-ttu-id="8cb61-281">Gå sedan vidare till nästa procedur.</span><span class="sxs-lookup"><span data-stu-id="8cb61-281">Then move on to the next procedure.</span></span>

1. <span data-ttu-id="8cb61-282">I avsnittet **Arbetskluster** väljer du det kluster-ID som du angav tidigare.</span><span class="sxs-lookup"><span data-stu-id="8cb61-282">In the **Work cluster** section, select the cluster ID that you entered earlier.</span></span>
1. <span data-ttu-id="8cb61-283">Klicka på **Stäng kluster** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="8cb61-283">On the Action Pane, select **Close cluster**.</span></span>

    <span data-ttu-id="8cb61-284">När klustret har stängts visas det inte längre i avsnittet **Arbetskluster** (om inte kryssrutan **Visa stängt arbete** är markerad).</span><span class="sxs-lookup"><span data-stu-id="8cb61-284">After the cluster has been closed, it's no longer shown in the **Work cluster** section (unless the **Show closed work** check box is selected).</span></span>

#### <a name="put-the-cluster-away"></a><span data-ttu-id="8cb61-285">Placera klustret</span><span class="sxs-lookup"><span data-stu-id="8cb61-285">Put the cluster away</span></span>

1. <span data-ttu-id="8cb61-286">Logga in på lagerställeappen som en användare som är konfigurerad för lagerstället *61*.</span><span class="sxs-lookup"><span data-stu-id="8cb61-286">Sign in to the warehouse app as a user who is set up for warehouse *61*.</span></span>
1. <span data-ttu-id="8cb61-287">I huvudmenyn, välj **ingående**.</span><span class="sxs-lookup"><span data-stu-id="8cb61-287">On the main menu, select **Inbound**.</span></span>
1. <span data-ttu-id="8cb61-288">I menyn **ingående** välj **kluster för artikelinförsel**.</span><span class="sxs-lookup"><span data-stu-id="8cb61-288">On the **Inbound** menu, select **Cluster putaway**.</span></span>
1. <span data-ttu-id="8cb61-289">Välj **kluster-ID** och ange det kluster-ID som du angav tidigare för det stängda klustret.</span><span class="sxs-lookup"><span data-stu-id="8cb61-289">Select **Cluster ID**, and enter the cluster ID that you entered earlier for the closed cluster.</span></span>
1. <span data-ttu-id="8cb61-290">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="8cb61-290">Select **OK**.</span></span>

    <span data-ttu-id="8cb61-291">Sidan **kluster för artikelinförsel: plocka** visas.</span><span class="sxs-lookup"><span data-stu-id="8cb61-291">The **Cluster putaway: Pick** page appears.</span></span> <span data-ttu-id="8cb61-292">Det visar kluster-ID, plockplatsen, artiklarna (värdet *Flera* visas) och den totala kvantiteten i klustret som måste plockas.</span><span class="sxs-lookup"><span data-stu-id="8cb61-292">It shows the cluster ID, the picking location, the items (the value *Multiple* will be shown), and the total quantity in the cluster that must be picked.</span></span>

1. <span data-ttu-id="8cb61-293">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="8cb61-293">Select **OK**.</span></span>

    <span data-ttu-id="8cb61-294">Sidan **kluster för artikelinförsel: placera** visas.</span><span class="sxs-lookup"><span data-stu-id="8cb61-294">The **Cluster putaway: Put** page appears.</span></span> <span data-ttu-id="8cb61-295">Instruktionerna för **Placera** identifierar kluster-ID, plats, artiklar, total kvantitet och ID-nummer för de artiklar som har tagits emot i klustret.</span><span class="sxs-lookup"><span data-stu-id="8cb61-295">The **Put** instructions identify the cluster ID, the put location, the items, the total quantity, and the license plate IDs for the items that have been received on the cluster.</span></span>

    <span data-ttu-id="8cb61-296">Du har standardalternativen för att åsidosätta eller godkänna det här steget.</span><span class="sxs-lookup"><span data-stu-id="8cb61-296">You have the standard options to override or pass this step.</span></span>

    <span data-ttu-id="8cb61-297">![Kluster för artikelinförsel: sidan placera](media/Cluster_putaway-Put.png "Kluster för artikelinförsel: sidan placera")</span><span class="sxs-lookup"><span data-stu-id="8cb61-297">![Cluster putaway: Put page](media/Cluster_putaway-Put.png "Cluster putaway: Put page")</span></span>

1. <span data-ttu-id="8cb61-298">Välj **OK** för att bekräfta placering av kluster.</span><span class="sxs-lookup"><span data-stu-id="8cb61-298">Select **OK** to confirm the putaway of the cluster.</span></span>

    <span data-ttu-id="8cb61-299">Du får ett meddelande att "klustret är slutfört".</span><span class="sxs-lookup"><span data-stu-id="8cb61-299">A "Cluster completed" message is shown.</span></span>

## <a name="notes-and-tips"></a><span data-ttu-id="8cb61-300">Anteckningar och tips</span><span class="sxs-lookup"><span data-stu-id="8cb61-300">Notes and tips</span></span>

<span data-ttu-id="8cb61-301">För fall där kluster-ID blir det överordnade ID-numret för en kapslad lastpall, anges automatiskt placeringspositionen när kluster-ID skannas.</span><span class="sxs-lookup"><span data-stu-id="8cb61-301">For cases where the cluster ID becomes the parent license plate for a nested pallet, the put position is automatically given when the cluster ID is scanned.</span></span> <span data-ttu-id="8cb61-302">Inget ytterligare ID-nummer måste skannas, även om ID-numren generation är inställd på manuell.</span><span class="sxs-lookup"><span data-stu-id="8cb61-302">No further license plate must be scanned, even if license plate generation is set to manual.</span></span>
