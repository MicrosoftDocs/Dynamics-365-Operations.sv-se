---
title: Arbetspolicyer
description: Det här avsnittet innehåller information om hur du ställer in arbetspolicyer.
author: perlynne
manager: tfehr
ms.date: 07/31/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSWorkPolicy
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-07-31
ms.dyn365.ops.version: Release 10.0.13
ms.openlocfilehash: 530abffb4c80a2d2f0e58e0c5a34294f7cba0b1a
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "4998463"
---
# <a name="work-policies"></a><span data-ttu-id="10eb4-103">Arbetspolicyer</span><span class="sxs-lookup"><span data-stu-id="10eb4-103">Work policies</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="10eb4-104">I det här avsnittet beskrivs hur du ställer in systemet och lagerställeappen så att de stöder arbetspolicyer.</span><span class="sxs-lookup"><span data-stu-id="10eb4-104">This topic explains how to set up the system and the warehouse app so that they support work policies.</span></span> <span data-ttu-id="10eb4-105">Du kan använda den här funktionen för att snabbt registrera lager utan att skapa inlagringsarbete när du tar emot inköps- eller överföringsorder, eller när du avslutar tillverkningsprocesser.</span><span class="sxs-lookup"><span data-stu-id="10eb4-105">You can use this functionality to quickly register inventory without creating putaway work when you receive purchase or transfer orders, or when you complete manufacturing processes.</span></span> <span data-ttu-id="10eb4-106">Det här avsnittet innehåller allmän information.</span><span class="sxs-lookup"><span data-stu-id="10eb4-106">This topic provides general information.</span></span> <span data-ttu-id="10eb4-107">Detaljerad information som är relaterad till det mottagna ID-numret finns i [Inleverans av ID-nummer som erhålls via lagerställeappen](warehousing-mobile-device-app-license-plate-receiving.md).</span><span class="sxs-lookup"><span data-stu-id="10eb4-107">For detailed information that is related to license plate receiving, see [License plate receiving via the warehouse app](warehousing-mobile-device-app-license-plate-receiving.md).</span></span>

<span data-ttu-id="10eb4-108">En arbetspolicy styr om lagerarbete ska skapas när en tillverkad artikel rapporteras som färdig eller när varor tas emot med hjälp av lagerställeapp.</span><span class="sxs-lookup"><span data-stu-id="10eb4-108">A work policy controls whether warehouse work is created when a manufactured item is reported as finished, or when goods are received by using the warehouse app.</span></span> <span data-ttu-id="10eb4-109">Du ställer in varje arbetspolicy genom att definiera villkoren där den gäller: arbetsordertyper och processer, lagerstället och (valfritt) produkterna.</span><span class="sxs-lookup"><span data-stu-id="10eb4-109">You set up each work policy by defining the conditions where it applies: the work order types and processes, the inventory location, and (optionally) the products.</span></span> <span data-ttu-id="10eb4-110">En inköpsorder för produkt *A0001* måste tas emot på plats *RECV* i lagerstället *24*.</span><span class="sxs-lookup"><span data-stu-id="10eb4-110">For example, a purchase order for product *A0001* must be received in location *RECV* in warehouse *24*.</span></span> <span data-ttu-id="10eb4-111">Senare förbrukas produkten i en annan process vid platsen *RECV*.</span><span class="sxs-lookup"><span data-stu-id="10eb4-111">Later, the product is consumed in another process at location *RECV*.</span></span> <span data-ttu-id="10eb4-112">I det här fallet kan du ställa in en arbetspolicy för att förhindra att inlagringsarbete skapas när en arbetare rapporterar produkt *A0001* som inlevererad på plats *RECV*.</span><span class="sxs-lookup"><span data-stu-id="10eb4-112">In this case, you can set up a work policy to prevent putaway work from being created when a worker reports product *A0001* as received in location *RECV*.</span></span>

> [!NOTE]
> - <span data-ttu-id="10eb4-113">Om en arbetspolicy ska vara aktiv måste du definiera minst en plats för den på snabbfliken **lagerplatser** på sidan **Arbetspolicyer**.</span><span class="sxs-lookup"><span data-stu-id="10eb4-113">For a work policy to be active, you must define at least one location for it on the **Inventory locations** FastTab of the **Work policies** page.</span></span> 
> - <span data-ttu-id="10eb4-114">Du kan inte ange samma plats för flera arbetspolicyer.</span><span class="sxs-lookup"><span data-stu-id="10eb4-114">You can't specify the same location for multiple work policies.</span></span>
> - <span data-ttu-id="10eb4-115">Alternativet **Skriv ut etikett** för menyalternativ för mobila enheter kommer inte att skriva ut en ID-nummeretikett om inte ett arbete skapas.</span><span class="sxs-lookup"><span data-stu-id="10eb4-115">The **Print label** option for mobile device menu items won't print a license plate label unless work was created.</span></span>

## <a name="activate-the-features-in-your-system"></a><span data-ttu-id="10eb4-116">Aktivera funktionerna i systemet</span><span class="sxs-lookup"><span data-stu-id="10eb4-116">Activate the features in your system</span></span>

<span data-ttu-id="10eb4-117">Om du vill göra alla funktioner som beskrivs i det här avsnittet tillgängliga i systemet aktiverar du följande två funktioner i [funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md):</span><span class="sxs-lookup"><span data-stu-id="10eb4-117">To make all the functionality that is described in this topic available in your system, turn on the following two features in [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md):</span></span>

- <span data-ttu-id="10eb4-118">Förbättrad mottagning av registreringsskylt</span><span class="sxs-lookup"><span data-stu-id="10eb4-118">License plate receiving enhancements</span></span>
- <span data-ttu-id="10eb4-119">Arbetspolicyförbättringar för inkommande arbete</span><span class="sxs-lookup"><span data-stu-id="10eb4-119">Work policy enhancements for inbound work</span></span>

## <a name="the-work-policies-page"></a><span data-ttu-id="10eb4-120">Sidan arbetspolicyer</span><span class="sxs-lookup"><span data-stu-id="10eb4-120">The Work policies page</span></span>

<span data-ttu-id="10eb4-121">Om du vill ställa in arbetspolicyer går du till **Hantering av distributionslager \> inställningar \> arbete \> arbetspolicyer**.</span><span class="sxs-lookup"><span data-stu-id="10eb4-121">To set up work policies, go to **Warehouse management \> Setup \> Work \> Work policies**.</span></span> <span data-ttu-id="10eb4-122">Ställ sedan in fälten enligt beskrivningen i följande underavsnitt på varje snabbflik.</span><span class="sxs-lookup"><span data-stu-id="10eb4-122">Then, on each FastTab, set the fields as described in the following subsections.</span></span>

### <a name="the-work-order-types-fasttab"></a><span data-ttu-id="10eb4-123">Snabbfliken arbetsordertyper</span><span class="sxs-lookup"><span data-stu-id="10eb4-123">The Work order types FastTab</span></span>

<span data-ttu-id="10eb4-124">På snabbfliken **arbetsordertyper** kan du lägga till alla arbetsordertyper och relaterade arbetsprocesser som arbetspolicyn gäller för.</span><span class="sxs-lookup"><span data-stu-id="10eb4-124">On the **Work order types** FastTab, add all the work order types, and the related work processes, that the work policy applies to.</span></span> <span data-ttu-id="10eb4-125">Följande arbetsordertyper och relaterade arbetsprocesser stöds för arbetspolicyer.</span><span class="sxs-lookup"><span data-stu-id="10eb4-125">The following work order types and related work processes are supported for work policies.</span></span>

| <span data-ttu-id="10eb4-126">Typ av arbetsorder</span><span class="sxs-lookup"><span data-stu-id="10eb4-126">Work order type</span></span> | <span data-ttu-id="10eb4-127">Arbetsprocess</span><span class="sxs-lookup"><span data-stu-id="10eb4-127">Work process</span></span> |
|---|---|
| <span data-ttu-id="10eb4-128">Råmaterialhämtning</span><span class="sxs-lookup"><span data-stu-id="10eb4-128">Raw material picking</span></span>| <span data-ttu-id="10eb4-129">Alla relaterade processer</span><span class="sxs-lookup"><span data-stu-id="10eb4-129">All related processes</span></span> |
| <span data-ttu-id="10eb4-130">Plats för samprodukt och biprodukt</span><span class="sxs-lookup"><span data-stu-id="10eb4-130">Co-product and by-product put away</span></span> | <span data-ttu-id="10eb4-131">Alla relaterade processer</span><span class="sxs-lookup"><span data-stu-id="10eb4-131">All related processes</span></span> |
| <span data-ttu-id="10eb4-132">Plats för slutförda varor</span><span class="sxs-lookup"><span data-stu-id="10eb4-132">Finished goods putaway</span></span> | <span data-ttu-id="10eb4-133">Alla relaterade processer</span><span class="sxs-lookup"><span data-stu-id="10eb4-133">All related processes</span></span> |
| <span data-ttu-id="10eb4-134">Överföringsinleverans</span><span class="sxs-lookup"><span data-stu-id="10eb4-134">Transfer receipt</span></span> | <span data-ttu-id="10eb4-135">Plats och mottagning av registreringsskylt</span><span class="sxs-lookup"><span data-stu-id="10eb4-135">License plate receiving (and putaway)</span></span> |
| <span data-ttu-id="10eb4-136">Inköpsorder</span><span class="sxs-lookup"><span data-stu-id="10eb4-136">Purchase orders</span></span> | <ul><li><span data-ttu-id="10eb4-137">Plats och mottagning av registreringsskylt</span><span class="sxs-lookup"><span data-stu-id="10eb4-137">License plate receiving (and putaway)</span></span></li><li><span data-ttu-id="10eb4-138">Mottagande och inleverans av lastartikel</span><span class="sxs-lookup"><span data-stu-id="10eb4-138">Load item receiving (and putaway)</span></span></li><li><span data-ttu-id="10eb4-139">Inköpsorderrad har inlevererats och inlagrats</span><span class="sxs-lookup"><span data-stu-id="10eb4-139">Purchase order line receiving (and putaway)</span></span></li><li><span data-ttu-id="10eb4-140">Inleverans och inlagring av inköpsorderartikel</span><span class="sxs-lookup"><span data-stu-id="10eb4-140">Purchase order item receiving (and putaway)</span></span></li></ul> |

<span data-ttu-id="10eb4-141">Om du vill ställa in en arbetspolicy så att den gäller för flera arbetsprocesser av samma arbetsordertyp, lägger du till en separat rad för varje arbetsprocess i rutnätet.</span><span class="sxs-lookup"><span data-stu-id="10eb4-141">To set up a work policy so that it applies to several work processes of the same work order type, add a separate line for each work process to the grid.</span></span>

<span data-ttu-id="10eb4-142">För varje rad i rutnätet anger du fältet **Metod för att skapa arbete** till ett av följande värden:</span><span class="sxs-lookup"><span data-stu-id="10eb4-142">For each line in the grid, set the **Work creation method** field to one of the following values:</span></span>

- <span data-ttu-id="10eb4-143">**Aldrig** – Arbetspolicyn förhindrar att arbetsuppgifter på lagerstället skapas för vald arbetsordertyp och relaterade arbetsprocesser.</span><span class="sxs-lookup"><span data-stu-id="10eb4-143">**Never** – The work policy will prevent warehouse work from being created for the selected work order type and related work process.</span></span>
- <span data-ttu-id="10eb4-144">**Direktutleverans** – Arbetspolicyn kommer att skapa direktutleverans med hjälp av den policy du väljer i fältet **Direktleveranspolicynamn**.</span><span class="sxs-lookup"><span data-stu-id="10eb4-144">**Cross docking** – The work policy will create cross-docking work by using the policy that you select in the **Cross docking policy name** field.</span></span>

### <a name="the-inventory-locations-fasttab"></a><span data-ttu-id="10eb4-145">Snabbfliken lagerplatser</span><span class="sxs-lookup"><span data-stu-id="10eb4-145">The Inventory locations FastTab</span></span>

<span data-ttu-id="10eb4-146">På snabbfliken **lagerplatser** lägger du till alla platser där den här arbetspolicyn ska användas.</span><span class="sxs-lookup"><span data-stu-id="10eb4-146">On the **Inventory locations** FastTab, add all the locations where this work policy should be applied.</span></span> <span data-ttu-id="10eb4-147">Om ingen plats finns associerad med en arbetspolicy, gäller inte arbetspolicyn för några processer.</span><span class="sxs-lookup"><span data-stu-id="10eb4-147">If no location is associated with a work policy, the work policy won't be applied to any process.</span></span>

<span data-ttu-id="10eb4-148">Du kan inte ange samma plats för flera arbetspolicyer.</span><span class="sxs-lookup"><span data-stu-id="10eb4-148">You can't specify the same location for multiple work policies.</span></span>

<span data-ttu-id="10eb4-149">Det går att använda ett lagerställe som är tilldelat till en platsprofil även om **Använd spårning av ID-nummer** inte är aktiverad.</span><span class="sxs-lookup"><span data-stu-id="10eb4-149">You can use a warehouse location that is assigned to a location profile where the **Use license plate tracking** option is turned off.</span></span> <span data-ttu-id="10eb4-150">I det här fallet registrerar arbetare direkt lagerbehållningen.</span><span class="sxs-lookup"><span data-stu-id="10eb4-150">In this case, workers will directly register the on-hand inventory.</span></span>

### <a name="the-products-fasttab"></a><span data-ttu-id="10eb4-151">Snabbfliken produkter</span><span class="sxs-lookup"><span data-stu-id="10eb4-151">The Products FastTab</span></span>

<span data-ttu-id="10eb4-152">På fliken **produkter** ställer du in fältet **produktval** så att du kan kontrollera vilka produkter policyn ska gälla för:</span><span class="sxs-lookup"><span data-stu-id="10eb4-152">On the **Products** tab, set the **Product selection** field to control which products the policy should apply to:</span></span>

- <span data-ttu-id="10eb4-153">**Alla** – policyn ska gälla för alla produkter.</span><span class="sxs-lookup"><span data-stu-id="10eb4-153">**All** – The policy should apply to all products.</span></span>
- <span data-ttu-id="10eb4-154">**Markerad** – policyn ska bara gälla för produkter som visas i rutnätet.</span><span class="sxs-lookup"><span data-stu-id="10eb4-154">**Selected** – The policy should apply only to products that are listed in the grid.</span></span> <span data-ttu-id="10eb4-155">Använd verktygsfältet på snabbfliken **produkter** om du vill lägga till produkter i rutnätet eller ta bort dem från rutnätet.</span><span class="sxs-lookup"><span data-stu-id="10eb4-155">Use the toolbar on the **Products** FastTab to add products to the grid or remove them from the grid.</span></span>

## <a name="default-and-custom-to-locations"></a><span data-ttu-id="10eb4-156">Standard och anpassade till platser</span><span class="sxs-lookup"><span data-stu-id="10eb4-156">Default and custom "to" locations</span></span>

> [!NOTE]
> <span data-ttu-id="10eb4-157">Om du vill göra funktionen som beskrivs i det här avsnittet tillgänglig i ditt system, måste du aktivera funktionerna *Förbättringar av inleverans av ID-nummer* och *Förbättringar av arbetspolicy för inkommande arbete* i [funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).</span><span class="sxs-lookup"><span data-stu-id="10eb4-157">To make the functionality that is described in this section available in your system, you must turn on the *License plate receiving enhancements* and *Work policy enhancements for inbound work* features in [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).</span></span>

<span data-ttu-id="10eb4-158">Tidigare har systemet endast tagit emot den standardplats som har definierats för varje lagerställe.</span><span class="sxs-lookup"><span data-stu-id="10eb4-158">Previously, the system supported receiving only at the default location that is defined for each warehouse.</span></span> <span data-ttu-id="10eb4-159">Menyalternativen för mobila enheter som använder följande processer för arbetsskapande har nu alternativet **Använd standarddata**.</span><span class="sxs-lookup"><span data-stu-id="10eb4-159">However, mobile device menu items that use the following work creation processes now provide the **Use default data** option.</span></span> <span data-ttu-id="10eb4-160">Med det här alternativet kan du tilldela en anpassad "till"-plats till ett eller flera menyalternativ.</span><span class="sxs-lookup"><span data-stu-id="10eb4-160">This option lets you assign a custom "to" location to one or more menu items.</span></span> <span data-ttu-id="10eb4-161">(Det här alternativet är redan tillgängligt för andra typer av menyalternativ.)</span><span class="sxs-lookup"><span data-stu-id="10eb4-161">(This option was already available for some other types of menu items.)</span></span>

- <span data-ttu-id="10eb4-162">Plats och mottagning av registreringsskylt</span><span class="sxs-lookup"><span data-stu-id="10eb4-162">License plate receiving (and putaway)</span></span>
- <span data-ttu-id="10eb4-163">Mottagande och inleverans av lastartikel</span><span class="sxs-lookup"><span data-stu-id="10eb4-163">Load item receiving (and putaway)</span></span>
- <span data-ttu-id="10eb4-164">Inköpsorderrad har inlevererats och inlagrats</span><span class="sxs-lookup"><span data-stu-id="10eb4-164">Purchase order line receiving (and putaway)</span></span>
- <span data-ttu-id="10eb4-165">Inleverans och inlagring av inköpsorderartikel</span><span class="sxs-lookup"><span data-stu-id="10eb4-165">Purchase order item receiving (and putaway)</span></span>

<span data-ttu-id="10eb4-166">Inställningen **Till plats** för ett menyalternativ åsidosätter standard mottagningsplatsen för lagerstället, för alla order som bearbetas med hjälp av det menyalternativet.</span><span class="sxs-lookup"><span data-stu-id="10eb4-166">The **To location** setting for a menu item overrides the default receiving location for the warehouse, for all orders that are processed by using that menu item.</span></span>

<span data-ttu-id="10eb4-167">Gör så här om du vill konfigurera ett menyalternativ för mobila enheter för att stödja mottagning på en vald plats:</span><span class="sxs-lookup"><span data-stu-id="10eb4-167">To set up a mobile device menu item to support receiving at a custom location, follow these steps.</span></span>

1. <span data-ttu-id="10eb4-168">Gå till **Lagerstyrning \> Inställningar \> Mobil enhet \> Menyalternativ på mobil enhet**.</span><span class="sxs-lookup"><span data-stu-id="10eb4-168">Go to **Warehouse management \> Setup \> Mobile device \> Mobile device menu items**.</span></span>
1. <span data-ttu-id="10eb4-169">Välj eller skapa ett menyalternativ som använder en av arbetsprocesserna som listas tidigare i det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="10eb4-169">Select or create a menu item that uses one of the work creation processes that are listed earlier in this section.</span></span>
1. <span data-ttu-id="10eb4-170">På snabbfliken **allmänt** anger du alternativet **Använd standarddata** till **Ja**.</span><span class="sxs-lookup"><span data-stu-id="10eb4-170">On the **General** FastTab, set the **Use default data** option to **Yes**.</span></span>
1. <span data-ttu-id="10eb4-171">I åtgärdsfönstret, välj **Standarddata**.</span><span class="sxs-lookup"><span data-stu-id="10eb4-171">On the Action Pane, select **Default data**.</span></span>
1. <span data-ttu-id="10eb4-172">Ange följande värden på sidan **Standarddata**:</span><span class="sxs-lookup"><span data-stu-id="10eb4-172">On the **Default data** page, set the following values:</span></span>

    - <span data-ttu-id="10eb4-173">**Standarddatafält:** Ange det här fältet till *till plats*.</span><span class="sxs-lookup"><span data-stu-id="10eb4-173">**Default data field:** Set this field to *To location*.</span></span>
    - <span data-ttu-id="10eb4-174">**Lagerställe:** Välj det lagerställe vid destinationen som ska användas för menyartikeln.</span><span class="sxs-lookup"><span data-stu-id="10eb4-174">**Warehouse:** Select the destination warehouse to use with this menu item.</span></span>
    - <span data-ttu-id="10eb4-175">**Plats:** i det här fältet visas en lista över de plats-ID:n som är tillgängliga för det valda lagerstället.</span><span class="sxs-lookup"><span data-stu-id="10eb4-175">**Location:** This field lists all the location IDs that are available for the selected warehouse.</span></span> <span data-ttu-id="10eb4-176">Inställningen av det här fältet har dock ingen effekt.</span><span class="sxs-lookup"><span data-stu-id="10eb4-176">However, the setting of this field doesn't actually have any effect.</span></span> <span data-ttu-id="10eb4-177">Därför kan du lämna det tomt.</span><span class="sxs-lookup"><span data-stu-id="10eb4-177">Therefore, you can leave it blank.</span></span> <span data-ttu-id="10eb4-178">Du kan dock använda listan för att bekräfta det ID som du måste ange i fältet **Hårdkodat värde**.</span><span class="sxs-lookup"><span data-stu-id="10eb4-178">Nevertheless, you can use the list to confirm the ID that you must enter in the **Hardcoded value** field.</span></span>
    - <span data-ttu-id="10eb4-179">**Hårdkodat värde:** Ange plats-ID för mottagningsplatsen som gäller för det här menyalternativet.</span><span class="sxs-lookup"><span data-stu-id="10eb4-179">**Hardcoded value:** Enter the location ID for the receiving location that applies to this menu item.</span></span>

> [!TIP]
> <span data-ttu-id="10eb4-180">En arbetspolicy kan bara användas om alla mottagande platser anges i de relevanta inställningarna för arbetspolicy.</span><span class="sxs-lookup"><span data-stu-id="10eb4-180">A work policy can be applied only if all the receiving locations are listed in the relevant work policy setup.</span></span> <span data-ttu-id="10eb4-181">Detta krav gäller oavsett om du använder standardplatsen för lagermottagning eller en anpassad "till"-plats.</span><span class="sxs-lookup"><span data-stu-id="10eb4-181">This requirement applies regardless of whether you're using the default warehouse receiving location or a custom "to" location.</span></span>

## <a name="example-scenario-warehouse-receiving"></a><span data-ttu-id="10eb4-182">Exempelscenario: inleverans av lager</span><span class="sxs-lookup"><span data-stu-id="10eb4-182">Example scenario: Warehouse receiving</span></span>

<span data-ttu-id="10eb4-183">Alla produkter som tas emot av processen *Inleverans och inlagring av inköpsorderartikel* måste registreras på platsen *FL-001* och de måste vara tillgängliga i lagerstället *24*.</span><span class="sxs-lookup"><span data-stu-id="10eb4-183">All products that are received by the *Purchase order item receiving (and putaway)* process must be registered in location *FL-001*, and they must be available in warehouse *24*.</span></span> <span data-ttu-id="10eb4-184">Arbete ska dock inte skapas.</span><span class="sxs-lookup"><span data-stu-id="10eb4-184">However, work should not be created.</span></span> <span data-ttu-id="10eb4-185">Produkter som tas emot av någon annan process (dvs. genom att använda andra menyartiklar för mobila enheter) registreras på standardplatsen för inleverans av lager (*RECV*) och arbete ska skapas som vanligt.</span><span class="sxs-lookup"><span data-stu-id="10eb4-185">Products that are received by any other process (that is, by using other mobile device menu items) should be registered at the default warehouse receiving location (*RECV*), and work should be created as usual.</span></span> <span data-ttu-id="10eb4-186">(Det här scenariot visar inte standardinställningarna för mottagning.)</span><span class="sxs-lookup"><span data-stu-id="10eb4-186">(This scenario doesn't show the default receiving setup.)</span></span>

<span data-ttu-id="10eb4-187">Det här scenariot kräver följande element:</span><span class="sxs-lookup"><span data-stu-id="10eb4-187">This scenario requires the following elements:</span></span>

- <span data-ttu-id="10eb4-188">En arbetspolicy för processen *Inleverans och inlagring av inköpsorderartikel* på platsen *FL-001* för alla produkter</span><span class="sxs-lookup"><span data-stu-id="10eb4-188">A work policy for the *Purchase order item receiving (and putaway)* process in location *FL-001*, for all products</span></span>
- <span data-ttu-id="10eb4-189">En menyartikel på en mobil enhet som har standarddata och som anger fältet **Till plats** till *FL-001*</span><span class="sxs-lookup"><span data-stu-id="10eb4-189">A mobile device menu item that has default data, and that sets the **To location** field to *FL-001*</span></span>

### <a name="prerequisites"></a><span data-ttu-id="10eb4-190">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="10eb4-190">Prerequisites</span></span>

<span data-ttu-id="10eb4-191">Om du vill göra funktionen som beskrivs i det här scenariot tillgänglig i ditt system, måste du aktivera funktionerna *Förbättringar av inleverans av ID-nummer* och *Förbättringar av arbetspolicy för inkommande arbete* i [funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).</span><span class="sxs-lookup"><span data-stu-id="10eb4-191">To make the functionality that is described in this scenario available in your system, you must turn on the *License plate receiving enhancements* and *Work policy enhancements for inbound work* features in [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).</span></span>

<span data-ttu-id="10eb4-192">Den här scenariot använder sig av standard demodata.</span><span class="sxs-lookup"><span data-stu-id="10eb4-192">This scenario uses the standard demo data.</span></span> <span data-ttu-id="10eb4-193">Därför, om du vill arbeta igenom scenariot genom att använda värdena som ges här måste du arbeta på ett system där demodata är installerat.</span><span class="sxs-lookup"><span data-stu-id="10eb4-193">Therefore, if you want to work through it by using the values that are provided here, you must work on a system where demo data is installed.</span></span> <span data-ttu-id="10eb4-194">Dessutom måste du välja den **USMF** juridiska personen.</span><span class="sxs-lookup"><span data-stu-id="10eb4-194">Additionally, you must select the **USMF** legal entity.</span></span>

### <a name="set-up-a-work-policy"></a><span data-ttu-id="10eb4-195">Konfigurera en arbetspolicy</span><span class="sxs-lookup"><span data-stu-id="10eb4-195">Set up a work policy</span></span>

1. <span data-ttu-id="10eb4-196">Gå till **Lagerstyrning \> Inställningar \> Arbete \> Arbetspolicyer**.</span><span class="sxs-lookup"><span data-stu-id="10eb4-196">Go to **Warehouse management \> Setup \> Work \> Work policies**.</span></span>
1. <span data-ttu-id="10eb4-197">Välj **Ny**.</span><span class="sxs-lookup"><span data-stu-id="10eb4-197">Select **New**.</span></span>
1. <span data-ttu-id="10eb4-198">I fältet the **Arbetspolicynamn** anger du *Ingen inköpspost för inlagringsarbete*.</span><span class="sxs-lookup"><span data-stu-id="10eb4-198">In the **Work policy name** field, enter *No purchase item putaway work*.</span></span>
1. <span data-ttu-id="10eb4-199">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="10eb4-199">Select **Save**.</span></span>
1. <span data-ttu-id="10eb4-200">På snabbfliken **Arbetsordertyper** väljer du **Lägg till** om du vill lägga till en rad i rutnätet och sedan ange följande värden för den nya raden:</span><span class="sxs-lookup"><span data-stu-id="10eb4-200">On the **Work order types** FastTab, select **Add** to add a row to the grid, and then set the following values for the new row:</span></span>

    - <span data-ttu-id="10eb4-201">**Arbetsordertyp:** *inköpsorder*</span><span class="sxs-lookup"><span data-stu-id="10eb4-201">**Work order type:** *Purchase orders*</span></span>
    - <span data-ttu-id="10eb4-202">**Arbetsprocess:** *Inköpsorderpost har inlevererats och inlagrats*</span><span class="sxs-lookup"><span data-stu-id="10eb4-202">**Work process:** *Purchase order item receiving (and putaway)*</span></span>
    - <span data-ttu-id="10eb4-203">**Arbetsskapande metod:** *aldrig*</span><span class="sxs-lookup"><span data-stu-id="10eb4-203">**Work creation method:** *Never*</span></span>
    - <span data-ttu-id="10eb4-204">**Direktleveranspolicynamn:** Lämna det här fältet tomt.</span><span class="sxs-lookup"><span data-stu-id="10eb4-204">**Cross docking policy name:** Leave this field blank.</span></span>

1. <span data-ttu-id="10eb4-205">På snabbfliken **Lagerplatser** väljer du **Lägg till** om du vill lägga till en rad i rutnätet och sedan ange följande värden för den nya raden:</span><span class="sxs-lookup"><span data-stu-id="10eb4-205">On the **Inventory locations** FastTab, select **Add** to add a row to the grid, and then set the following values for the new row:</span></span>

    - <span data-ttu-id="10eb4-206">**Lagerställe:** *24*</span><span class="sxs-lookup"><span data-stu-id="10eb4-206">**Warehouse:** *24*</span></span>
    - <span data-ttu-id="10eb4-207">**Plats:** *FL-001*</span><span class="sxs-lookup"><span data-stu-id="10eb4-207">**Location:** *FL-001*</span></span>

1. <span data-ttu-id="10eb4-208">På snabbfliken **produkter** ställer du in fältet **produktval** till *alla*.</span><span class="sxs-lookup"><span data-stu-id="10eb4-208">On the **Products** FastTab, set the **Product selection** field to *All*.</span></span>
1. <span data-ttu-id="10eb4-209">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="10eb4-209">Select **Save**.</span></span>

### <a name="set-up-a-mobile-device-menu-item-to-change-the-receiving-location"></a><span data-ttu-id="10eb4-210">Ställ in ett menyalternativ för mobila enheter för att ändra mottagningsplats</span><span class="sxs-lookup"><span data-stu-id="10eb4-210">Set up a mobile device menu item to change the receiving location</span></span>

1. <span data-ttu-id="10eb4-211">Gå till **Lagerstyrning \> Inställningar \> Mobil enhet \> Menyalternativ på mobil enhet**.</span><span class="sxs-lookup"><span data-stu-id="10eb4-211">Go to **Warehouse management \> Setup \> Mobile device \> Mobile device menu items**.</span></span>
1. <span data-ttu-id="10eb4-212">I vänster ruta, välj befintligt menyalternativ **inleverans av inköp**.</span><span class="sxs-lookup"><span data-stu-id="10eb4-212">In the left pane, select the existing **Purchase receive** menu item.</span></span>
1. <span data-ttu-id="10eb4-213">På snabbfliken **allmänt** anger du alternativet **Använd standarddata** till *Ja*.</span><span class="sxs-lookup"><span data-stu-id="10eb4-213">On the **General** FastTab, set the **Use default data** option to *Yes*.</span></span>
1. <span data-ttu-id="10eb4-214">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="10eb4-214">Select **Save**.</span></span>
1. <span data-ttu-id="10eb4-215">I åtgärdsfönstret, välj **Standarddata**.</span><span class="sxs-lookup"><span data-stu-id="10eb4-215">On the Action Pane, select **Default data**.</span></span>
1. <span data-ttu-id="10eb4-216">På sidan **Standarddata** i åtgärdsfönstret väljer du **Ny** om du vill lägga till en rad i rutnätet och sedan ange följande värden för den nya raden:</span><span class="sxs-lookup"><span data-stu-id="10eb4-216">On the **Default data** page, on the Action Pane, select **New** to add a row to the grid, and then set the following values for the new row:</span></span>

    - <span data-ttu-id="10eb4-217">**Standarddatafält:** *till plats*</span><span class="sxs-lookup"><span data-stu-id="10eb4-217">**Default data field:** *To location*</span></span>
    - <span data-ttu-id="10eb4-218">**Lagerställe:** *24*</span><span class="sxs-lookup"><span data-stu-id="10eb4-218">**Warehouse:** *24*</span></span>
    - <span data-ttu-id="10eb4-219">**Plats:** lämna det här fältet tomt.</span><span class="sxs-lookup"><span data-stu-id="10eb4-219">**Location:** Leave this field blank.</span></span>
    - <span data-ttu-id="10eb4-220">**Hårdkodat värde:** *FL-001*</span><span class="sxs-lookup"><span data-stu-id="10eb4-220">**Hardcoded value:** *FL-001*</span></span>

1. <span data-ttu-id="10eb4-221">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="10eb4-221">Select **Save**.</span></span>

### <a name="receive-a-purchase-order-without-creating-work"></a><span data-ttu-id="10eb4-222">Ta emot en inköpsorder utan att skapa arbete</span><span class="sxs-lookup"><span data-stu-id="10eb4-222">Receive a purchase order without creating work</span></span>

<span data-ttu-id="10eb4-223">Exemplet i det här avsnittet visar hur du tar emot en inköpsorderartikel, men utan att skapa arbete på en plats som skiljer sig från den standardplats för inleverans som har ställts in för lagerstället.</span><span class="sxs-lookup"><span data-stu-id="10eb4-223">The example in this section shows how to receive a purchase order item, but without creating work, at a location that differs from the default receiving location that is set up for the warehouse.</span></span> <span data-ttu-id="10eb4-224">I det här exemplet används arbetspolicyn och objektet i den mobila enheten som du skapade tidigare i det här scenariot.</span><span class="sxs-lookup"><span data-stu-id="10eb4-224">This example uses the work policy and mobile device item that you created earlier in this scenario.</span></span>

#### <a name="create-a-purchase-order"></a><span data-ttu-id="10eb4-225">Skapa en inköpsorder</span><span class="sxs-lookup"><span data-stu-id="10eb4-225">Create a purchase order</span></span>

1. <span data-ttu-id="10eb4-226">Gå till **Anskaffning och källa \> Inköpsorder \> Alla inköpsorder**.</span><span class="sxs-lookup"><span data-stu-id="10eb4-226">Go to **Procurement and sourcing \> Purchase orders \> All purchase orders**.</span></span>
1. <span data-ttu-id="10eb4-227">Välj **Ny**.</span><span class="sxs-lookup"><span data-stu-id="10eb4-227">Select **New**.</span></span>
1. <span data-ttu-id="10eb4-228">I dialogrutan **Skapa inköpsorder** ställ in följande värden:</span><span class="sxs-lookup"><span data-stu-id="10eb4-228">In the **Create purchase order** dialog box, set the following values:</span></span>

    - <span data-ttu-id="10eb4-229">**Leverantörskonto:** *US-101*</span><span class="sxs-lookup"><span data-stu-id="10eb4-229">**Vendor account:** *US-101*</span></span>
    - <span data-ttu-id="10eb4-230">**Plats:** *2*</span><span class="sxs-lookup"><span data-stu-id="10eb4-230">**Site:** *2*</span></span>
    - <span data-ttu-id="10eb4-231">**Lagerställe:** *24*</span><span class="sxs-lookup"><span data-stu-id="10eb4-231">**Warehouse:** *24*</span></span>

1. <span data-ttu-id="10eb4-232">Välj **OK** för att stänga dialogrutan och öppna den nya inköpsordern.</span><span class="sxs-lookup"><span data-stu-id="10eb4-232">Select **OK** to close the dialog box and open the new purchase order.</span></span>
1. <span data-ttu-id="10eb4-233">På snabbfliken **inköpsorderrader** anger du följande värden för den tomma raden:</span><span class="sxs-lookup"><span data-stu-id="10eb4-233">On the **Purchase order lines** FastTab, set the following values for the empty row:</span></span>

    - <span data-ttu-id="10eb4-234">**Artikelnummer:** *A0001*</span><span class="sxs-lookup"><span data-stu-id="10eb4-234">**Item number:** *A0001*</span></span>
    - <span data-ttu-id="10eb4-235">**Kvantitet:** *1*</span><span class="sxs-lookup"><span data-stu-id="10eb4-235">**Quantity:** *1*</span></span>

1. <span data-ttu-id="10eb4-236">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="10eb4-236">Select **Save**.</span></span>
1. <span data-ttu-id="10eb4-237">Anteckna inköpsordernumret.</span><span class="sxs-lookup"><span data-stu-id="10eb4-237">Make a note of the purchase order number.</span></span>

#### <a name="receive-a-purchase-order"></a><span data-ttu-id="10eb4-238">Få en inköpsorder</span><span class="sxs-lookup"><span data-stu-id="10eb4-238">Receive a purchase order</span></span>

1. <span data-ttu-id="10eb4-239">På den mobila enheten logga in på lagerställe *24* med hjälp av *24* som användar-ID och *1* som lösenord.</span><span class="sxs-lookup"><span data-stu-id="10eb4-239">On the mobile device, sign in to warehouse *24* by using *24* as the user ID and *1* as the password.</span></span>
1. <span data-ttu-id="10eb4-240">Välj **Ankommande**.</span><span class="sxs-lookup"><span data-stu-id="10eb4-240">Select **Inbound**.</span></span>
1. <span data-ttu-id="10eb4-241">Välj **inköpsmottagare**.</span><span class="sxs-lookup"><span data-stu-id="10eb4-241">Select **Purchase receive**.</span></span> <span data-ttu-id="10eb4-242">Fältet **Plats** fältet ska ställas in på *FL-001*.</span><span class="sxs-lookup"><span data-stu-id="10eb4-242">The **Location** field should be set to *FL-001*.</span></span>
1. <span data-ttu-id="10eb4-243">Ange inköpsordernumret för inköpsordern som du skapade i den föregående proceduren.</span><span class="sxs-lookup"><span data-stu-id="10eb4-243">Enter the purchase order number for the purchase order that you created in the previous procedure.</span></span>
1. <span data-ttu-id="10eb4-244">I fältet **artikelnummer** ange *A0001*.</span><span class="sxs-lookup"><span data-stu-id="10eb4-244">In the **Item number** field, enter *A0001*.</span></span>
1. <span data-ttu-id="10eb4-245">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="10eb4-245">Select **OK**.</span></span>
1. <span data-ttu-id="10eb4-246">I fältet **Kvantitet**, ange *1*.</span><span class="sxs-lookup"><span data-stu-id="10eb4-246">In the **Quantity** field, enter *1*.</span></span>
1. <span data-ttu-id="10eb4-247">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="10eb4-247">Select **OK**.</span></span>

<span data-ttu-id="10eb4-248">Inköpsordern tas nu emot, men inget arbete associeras med den.</span><span class="sxs-lookup"><span data-stu-id="10eb4-248">The purchase order is now received, but no work is associated with it.</span></span> <span data-ttu-id="10eb4-249">Lagerbehållningen har uppdaterats och kvantiteten *1* av artikel *A0001* finns nu tillgänglig på platsen *FL-001*.</span><span class="sxs-lookup"><span data-stu-id="10eb4-249">The on-hand inventory has been updated, and a quantity of *1* of item *A0001* is now available at location *FL-001*.</span></span>

## <a name="example-scenario-manufacturing"></a><span data-ttu-id="10eb4-250">Exempelscenario: tillverkning</span><span class="sxs-lookup"><span data-stu-id="10eb4-250">Example scenario: Manufacturing</span></span>

<span data-ttu-id="10eb4-251">I följande exempel finns det två produktionsorder *PRD-001* och *PRD-002*.</span><span class="sxs-lookup"><span data-stu-id="10eb4-251">In the following example, there are two production orders, *PRD-001* and *PRD-002*.</span></span> <span data-ttu-id="10eb4-252">Produktionsorder *PRD-001* har en åtgärd med namnet *Sammansättning*, där produkten *SC1* rapporterats som färdig till plats *001*.</span><span class="sxs-lookup"><span data-stu-id="10eb4-252">Production order *PRD-001* has an operation that is named *Assembly*, where product *SC1* is being reported as finished to location *001*.</span></span> <span data-ttu-id="10eb4-253">Produktionsorder *PRD-002* har en åtgärd med namnet *Målar* och förbrukar produkten *SC1* från platsen *001*.</span><span class="sxs-lookup"><span data-stu-id="10eb4-253">Production order *PRD-002* has an operation that is named *Painting* and consumes product *SC1* from location *001*.</span></span> <span data-ttu-id="10eb4-254">Produktionsorder *PRD-002* förbrukar även råmaterial *RM1* från platsen *001*.</span><span class="sxs-lookup"><span data-stu-id="10eb4-254">Production order *PRD-002* also consumes raw material *RM1* from location *001*.</span></span> <span data-ttu-id="10eb4-255">Råmaterial *RM1* lagras på lagerställeplats och *BULK-001* plockas till platsen *001* av lagerställets arbetsuppgift för plockning av råmaterial.</span><span class="sxs-lookup"><span data-stu-id="10eb4-255">Raw material *RM1* is stored in warehouse location *BULK-001* and will be picked to location *001* by warehouse work for raw material picking.</span></span> <span data-ttu-id="10eb4-256">Plockningsarbetet skapas när produktion *PRD-002* frisläpps.</span><span class="sxs-lookup"><span data-stu-id="10eb4-256">The picking work is generated when production *PRD-002* is released.</span></span>

<span data-ttu-id="10eb4-257">[![Policyer för distributionslagerarbete](./media/warehouse-work-policies.png)](./media/warehouse-work-policies.png)</span><span class="sxs-lookup"><span data-stu-id="10eb4-257">[![Warehouse work policies](./media/warehouse-work-policies.png)](./media/warehouse-work-policies.png)</span></span>

<span data-ttu-id="10eb4-258">När du planerar att konfigurera en arbetspolicy för detta scenario på lagerstället, bör du beakta följande punkter:</span><span class="sxs-lookup"><span data-stu-id="10eb4-258">When you're planning to configure a warehouse work policy for this scenario, you should consider the following points:</span></span>

- <span data-ttu-id="10eb4-259">Arbetsuppgifter för förvaring av färdiga varor på lagerställen krävs inte när du rapporterar produkten *SC1* som färdig från produktionsorder *PRD-001* till platsen *001*.</span><span class="sxs-lookup"><span data-stu-id="10eb4-259">Warehouse work for putaway of finished goods isn't required when you report product *SC1* as finished from production order *PRD-001* to location *001*.</span></span> <span data-ttu-id="10eb4-260">Detta eftersom åtgärden *Målar* för produktionsorder *PRD-002* förbrukar produkten *SC1* på samma plats.</span><span class="sxs-lookup"><span data-stu-id="10eb4-260">The reason is that the *Painting* operation for production order *PRD-002* consumes product *SC1* at the same location.</span></span>
- <span data-ttu-id="10eb4-261">Lagerställearbete för plockning av råmaterial krävs för att flytta råmaterialet *RM1* från lagerplats *BULK-001* till plats *001*.</span><span class="sxs-lookup"><span data-stu-id="10eb4-261">Warehouse work for raw material picking is required to move raw material *RM1* from warehouse location *BULK-001* to location *001*.</span></span>

<span data-ttu-id="10eb4-262">Här följer ett exempel på en arbetspolicy som du kan ställa in, baserat på dessa överväganden:</span><span class="sxs-lookup"><span data-stu-id="10eb4-262">Here is an example of a work policy that you can set up, based on these considerations:</span></span>

- <span data-ttu-id="10eb4-263">**Namn på arbetspolicy:** *inget inlagringsarbete*</span><span class="sxs-lookup"><span data-stu-id="10eb4-263">**Work policy name:** *No putaway work*</span></span>
- <span data-ttu-id="10eb4-264">**Arbetsordertyper:** *Plats för slutförda varor* och *Plats för samprodukt och biprodukt*</span><span class="sxs-lookup"><span data-stu-id="10eb4-264">**Work order types:** *Finished goods put away* and *Co-product and by-product put away*</span></span>
- <span data-ttu-id="10eb4-265">**Lagerställen:** lagerställe *51* och plats *001*</span><span class="sxs-lookup"><span data-stu-id="10eb4-265">**Inventory locations:** Warehouse *51* and location *001*</span></span>
- <span data-ttu-id="10eb4-266">**Produkter:** *SC1*</span><span class="sxs-lookup"><span data-stu-id="10eb4-266">**Products:** *SC1*</span></span>

<span data-ttu-id="10eb4-267">Följande exempelscenario ger steg-för-steg-instruktioner om hur du ställer in arbetspolicyn för lagerstället för detta scenario.</span><span class="sxs-lookup"><span data-stu-id="10eb4-267">The following example scenario provides step-by-step instructions for setting up the warehouse work policy for this scenario.</span></span>

## <a name="example-scenario-report-as-finished-to-a-location-that-isnt-license-platecontrolled"></a><span data-ttu-id="10eb4-268">Exempelscenario: Rapportera en produktionsorder som slutförd till en plats som inte kontrolleras via registreringsskylt</span><span class="sxs-lookup"><span data-stu-id="10eb4-268">Example scenario: Report as finished to a location that isn't license plate–controlled</span></span>

<span data-ttu-id="10eb4-269">Detta scenario visar ett exempel som visar hur du rapporterar en produktionsorder som slutförd till en plats som inte kontrolleras via registreringsskylt.</span><span class="sxs-lookup"><span data-stu-id="10eb4-269">This scenario shows an example where a production order is reported as finished to a location that isn't license plate–controlled.</span></span>

<span data-ttu-id="10eb4-270">Den här scenariot använder sig av standard demodata.</span><span class="sxs-lookup"><span data-stu-id="10eb4-270">This scenario uses the standard demo data.</span></span> <span data-ttu-id="10eb4-271">Därför, om du vill arbeta igenom scenariot genom att använda värdena som ges här måste du arbeta på ett system där demodata är installerat.</span><span class="sxs-lookup"><span data-stu-id="10eb4-271">Therefore, if you want to work through it by using the values that are provided here, you must work on a system where demo data is installed.</span></span> <span data-ttu-id="10eb4-272">Dessutom måste du välja den **USMF** juridiska personen.</span><span class="sxs-lookup"><span data-stu-id="10eb4-272">Additionally, you must select the **USMF** legal entity.</span></span>

### <a name="set-up-a-warehouse-work-policy"></a><span data-ttu-id="10eb4-273">Konfigurera en policy för lagerarbete</span><span class="sxs-lookup"><span data-stu-id="10eb4-273">Set up a warehouse work policy</span></span>

<span data-ttu-id="10eb4-274">Lagerställeprocesser inkluderar inte alltid lagerarbete.</span><span class="sxs-lookup"><span data-stu-id="10eb4-274">Warehouse processes don't always include warehouse work.</span></span> <span data-ttu-id="10eb4-275">Genom att definiera en arbetspolicy kan du förhindra skapande av arbete för råmaterialhämtning och inlagring av färdiga varor för en uppsättning av produkter på specifika platser.</span><span class="sxs-lookup"><span data-stu-id="10eb4-275">By defining a work policy, you can prevent the creation of work for raw material picking and putaway of finished goods for a set of products at specific locations.</span></span>

1. <span data-ttu-id="10eb4-276">Gå till **Lagerstyrning \> Inställningar \> Arbete \> Arbetspolicyer**.</span><span class="sxs-lookup"><span data-stu-id="10eb4-276">Go to **Warehouse management \> Setup \> Work \> Work policies**.</span></span>
1. <span data-ttu-id="10eb4-277">Välj **Ny**.</span><span class="sxs-lookup"><span data-stu-id="10eb4-277">Select **New**.</span></span>
1. <span data-ttu-id="10eb4-278">I fältet **Arbetspolicynamn** anger du *Inget inlagringsarbete*.</span><span class="sxs-lookup"><span data-stu-id="10eb4-278">In the **Work policy name** field, enter *No putaway work*.</span></span>
1. <span data-ttu-id="10eb4-279">Klicka på **Spara** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="10eb4-279">On the Action Pane, select **Save**.</span></span>
1. <span data-ttu-id="10eb4-280">På snabbfliken **Arbetsordertyper** väljer du **Lägg till** om du vill lägga till en rad i rutnätet och sedan ange följande värden för den nya raden:</span><span class="sxs-lookup"><span data-stu-id="10eb4-280">On the **Work order types** FastTab, select **Add** to add a row to the grid, and then set the following values for the new row:</span></span>

    - <span data-ttu-id="10eb4-281">**Arbetsordertyp:** *Plats för slutförda varor*</span><span class="sxs-lookup"><span data-stu-id="10eb4-281">**Work order type:** *Finished goods put away*</span></span>
    - <span data-ttu-id="10eb4-282">**Arbetsprocess:** *Alla relaterade arbetsprocesser*</span><span class="sxs-lookup"><span data-stu-id="10eb4-282">**Work process:** *All related work processes*</span></span>
    - <span data-ttu-id="10eb4-283">**Arbetsskapande metod:** *aldrig*</span><span class="sxs-lookup"><span data-stu-id="10eb4-283">**Work creation method:** *Never*</span></span>
    - <span data-ttu-id="10eb4-284">**Direktleveranspolicynamn:** Lämna det här fältet tomt.</span><span class="sxs-lookup"><span data-stu-id="10eb4-284">**Cross docking policy name:** Leave this field blank.</span></span>

1. <span data-ttu-id="10eb4-285">Välj **Lägg till** igen om du vill lägga till en rad i rutnätet och sedan ange följande värden för den nya raden:</span><span class="sxs-lookup"><span data-stu-id="10eb4-285">Select **Add** again to add a second row to the grid, and then set the following values for the new row:</span></span>

    - <span data-ttu-id="10eb4-286">**Arbetsordertyp:** *Plats för samprodukt och biprodukt*</span><span class="sxs-lookup"><span data-stu-id="10eb4-286">**Work order type:** *Co-product and by-product put away*</span></span>
    - <span data-ttu-id="10eb4-287">**Arbetsprocess:** *Alla relaterade arbetsprocesser*</span><span class="sxs-lookup"><span data-stu-id="10eb4-287">**Work process:** *All related work processes*</span></span>
    - <span data-ttu-id="10eb4-288">**Arbetsskapande metod:** *aldrig*</span><span class="sxs-lookup"><span data-stu-id="10eb4-288">**Work creation method:** *Never*</span></span>
    - <span data-ttu-id="10eb4-289">**Direktleveranspolicynamn:** Lämna det här fältet tomt.</span><span class="sxs-lookup"><span data-stu-id="10eb4-289">**Cross docking policy name:** Leave this field blank.</span></span>

1. <span data-ttu-id="10eb4-290">På snabbfliken **Lagerplatser** väljer du **Lägg till** om du vill lägga till en rad i rutnätet och sedan ange följande värden för den nya raden:</span><span class="sxs-lookup"><span data-stu-id="10eb4-290">On the **Inventory locations** FastTab, select **Add** to add a row to the grid, and then set the following values for the new row:</span></span>

    - <span data-ttu-id="10eb4-291">**Lagerställe:** *51*</span><span class="sxs-lookup"><span data-stu-id="10eb4-291">**Warehouse:** *51*</span></span>
    - <span data-ttu-id="10eb4-292">**Plats:** *001*</span><span class="sxs-lookup"><span data-stu-id="10eb4-292">**Location:** *001*</span></span>

1. <span data-ttu-id="10eb4-293">På snabbfliken **produkter** ställer du in fältet **produktval** till *valda*.</span><span class="sxs-lookup"><span data-stu-id="10eb4-293">On the **Products** FastTab, set the **Product selection** field to *Selected*.</span></span>
1. <span data-ttu-id="10eb4-294">På snabbfliken **produkter**, välj **Lägg till** om du vill lägga till rutnätet.</span><span class="sxs-lookup"><span data-stu-id="10eb4-294">On the **Products** FastTab, select **Add** to add a row to the grid.</span></span>
1. <span data-ttu-id="10eb4-295">I nya rader, ange fältet **Artikelnummer** till *L0101*.</span><span class="sxs-lookup"><span data-stu-id="10eb4-295">In the new row, set the **Item number** field to *L0101*.</span></span>
1. <span data-ttu-id="10eb4-296">Klicka på **Spara** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="10eb4-296">On the Action Pane, select **Save**.</span></span>

### <a name="set-up-an-output-location"></a><span data-ttu-id="10eb4-297">Ställ in en utleveransplats</span><span class="sxs-lookup"><span data-stu-id="10eb4-297">Set up an output location</span></span>

1. <span data-ttu-id="10eb4-298">Gå till **Organisationsadministration \> Resurser \> Resursgrupper**.</span><span class="sxs-lookup"><span data-stu-id="10eb4-298">Go to **Organization administration \> Resources \> Resource groups**.</span></span>
1. <span data-ttu-id="10eb4-299">I det vänstra fönstret, välj resursgrupp **5102**.</span><span class="sxs-lookup"><span data-stu-id="10eb4-299">In the left pane, select resource group **5102**.</span></span>
1. <span data-ttu-id="10eb4-300">Ange följande värden på snabbfliken **Allmänt**:</span><span class="sxs-lookup"><span data-stu-id="10eb4-300">On the **General** FastTab, set the following values:</span></span>

    - <span data-ttu-id="10eb4-301">**Utleveranslagerställe:** *51*</span><span class="sxs-lookup"><span data-stu-id="10eb4-301">**Output warehouse:** *51*</span></span>
    - <span data-ttu-id="10eb4-302">**Utleveransplats:** *001*</span><span class="sxs-lookup"><span data-stu-id="10eb4-302">**Output location:** *001*</span></span>

1. <span data-ttu-id="10eb4-303">Klicka på **Spara** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="10eb4-303">On the Action Pane, select **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="10eb4-304">Plats *001* är en ej ID-nummerstyrd plats.</span><span class="sxs-lookup"><span data-stu-id="10eb4-304">Location *001* isn't a license plate–controlled location.</span></span> <span data-ttu-id="10eb4-305">Du kan ställa in en utgående plats som inte är ID-nummerstyrd utleveransplats bara om en lämplig arbetspolicy finns för platsen.</span><span class="sxs-lookup"><span data-stu-id="10eb4-305">You can set up an output location that isn't license plate–controlled only if an applicable work policy exists for the location.</span></span>

### <a name="create-a-production-order-and-report-it-as-finished"></a><span data-ttu-id="10eb4-306">Skapa en produktionsorder och rapportera den som färdig.</span><span class="sxs-lookup"><span data-stu-id="10eb4-306">Create a production order and report it as finished</span></span>

1. <span data-ttu-id="10eb4-307">Gå till **Produktionskontroll \> Produktionsorder \> Alla produktionsorder**.</span><span class="sxs-lookup"><span data-stu-id="10eb4-307">Go to **Production control \> Production orders \> All production orders**.</span></span>
1. <span data-ttu-id="10eb4-308">Välj **Ny produktionsorder** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="10eb4-308">On the Action Pane, select **New production order**.</span></span>
1. <span data-ttu-id="10eb4-309">I dialogrutan **Skapa produktionsorder** ange fältet **Artikelnummer** till *L0101*.</span><span class="sxs-lookup"><span data-stu-id="10eb4-309">In the **Create production order** dialog box, set the **Item number** field to *L0101*.</span></span>
1. <span data-ttu-id="10eb4-310">Välj **Skapa** för att skapa den försäljningsordern och stänga dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="10eb4-310">Select **Create** to create the order and close the dialog box.</span></span>

    <span data-ttu-id="10eb4-311">En ny tillverkningsorder läggs till i rutnätet på sidan **Alla produktionsorder**.</span><span class="sxs-lookup"><span data-stu-id="10eb4-311">A new production order is added to the grid on the **All production orders** page.</span></span>

    <span data-ttu-id="10eb4-312">Behåll den nya produktionsordern vald.</span><span class="sxs-lookup"><span data-stu-id="10eb4-312">Keep the new production order selected.</span></span>

1. <span data-ttu-id="10eb4-313">I Åtgärdsfönstret, på fliken **Produktionsorder**, i gruppen **Process**, markerar du **Uppskatta**.</span><span class="sxs-lookup"><span data-stu-id="10eb4-313">On the Action Pane, on the **Production order** tab, in the **Process** group, select **Estimate**.</span></span>
1. <span data-ttu-id="10eb4-314">I dialogrutan **uppskattningen** läs uppskattningen och välj sedan **OK** för att stänga dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="10eb4-314">In the **Estimate** dialog box, read the estimate, and then select **OK** to close the dialog box.</span></span>
1. <span data-ttu-id="10eb4-315">I Åtgärdsfönstret, på fliken **Produktionsorder**, i gruppen **Process**, markerar du **Start**.</span><span class="sxs-lookup"><span data-stu-id="10eb4-315">On the Action Pane, on the **Production order** tab, in the **Process** group, select **Start**.</span></span>
1. <span data-ttu-id="10eb4-316">I dialogrutan **Start** på fliken **Allmänt** anger du fältet **automatisk strukturlisteförbrukning** till *Aldrig*.</span><span class="sxs-lookup"><span data-stu-id="10eb4-316">In the **Start** dialog box, on the **General** tab, set the **Automatic BOM consumption** field to *Never*.</span></span>
1. <span data-ttu-id="10eb4-317">Välj **OK** om du vill spara inställningarna och stänga dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="10eb4-317">Select **OK** to save your setting and close the dialog box.</span></span>
1. <span data-ttu-id="10eb4-318">I Åtgärdsfönstret, på fliken **Produktionsorder**, i gruppen **Process**, markerar du **Rapportera som slutförd**.</span><span class="sxs-lookup"><span data-stu-id="10eb4-318">On the Action Pane, on the **Production order** tab, in the **Process** group, select **Report as finished**.</span></span>
1. <span data-ttu-id="10eb4-319">I dialogrutan **Rapportera som slutförd** på fliken **Allmänt** anger du alternativet **Acceptera fel** till *Ja*.</span><span class="sxs-lookup"><span data-stu-id="10eb4-319">In the **Report as finished** dialog box, on the **General** tab, set the **Accept error** option to *Yes*.</span></span>
1. <span data-ttu-id="10eb4-320">Välj **OK** om du vill spara inställningarna och stänga dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="10eb4-320">Select **OK** to save your setting and close the dialog box.</span></span>
1. <span data-ttu-id="10eb4-321">I åtgärdsfönstret, på fliken **Lagerställe**, i gruppen **Allmänt**, väljer du **Arbetsdetaljer**.</span><span class="sxs-lookup"><span data-stu-id="10eb4-321">On the Action Pane, on the **Warehouse** tab, in the **General** group, select **Work details**.</span></span>

<span data-ttu-id="10eb4-322">När tillverkningsordern rapporterades som färdig, genererades inget arbete för plats.</span><span class="sxs-lookup"><span data-stu-id="10eb4-322">When the production order is reported as finished, no work is generated for putaway.</span></span> <span data-ttu-id="10eb4-323">Detta beteende inträffar, eftersom en arbetspolicy definieras som hindrar arbete från att genereras när produkten *L0101* rapporterats som färdig till plats *001*.</span><span class="sxs-lookup"><span data-stu-id="10eb4-323">This behavior occurs because a work policy is defined that prevents work from being generated when product *L0101* is reported as finished to location *001*.</span></span>

## <a name="more-information"></a><span data-ttu-id="10eb4-324">Mer information</span><span class="sxs-lookup"><span data-stu-id="10eb4-324">More information</span></span>

<span data-ttu-id="10eb4-325">Mer information om menyartiklar för mobila enheter finns i [ställa in mobila enheter för lagerarbete](configure-mobile-devices-warehouse.md).</span><span class="sxs-lookup"><span data-stu-id="10eb4-325">For more information about mobile device menu items, see [Set up mobile devices for warehouse work](configure-mobile-devices-warehouse.md).</span></span>

<span data-ttu-id="10eb4-326">Detaljerad information om det mottagna ID-numret och arbetspolicyer finns i [Inleverans av ID-nummer som erhålls via lagerställeappen](warehousing-mobile-device-app-license-plate-receiving.md).</span><span class="sxs-lookup"><span data-stu-id="10eb4-326">For more information about license plate receiving and work policies, see [License plate receiving via the warehouse app](warehousing-mobile-device-app-license-plate-receiving.md).</span></span>

<span data-ttu-id="10eb4-327">Mer information om inkommande belastningshantering finns i [Lagerhantering av inkommande laster för inköpsorder](inbound-load-handling.md).</span><span class="sxs-lookup"><span data-stu-id="10eb4-327">For more information about inbound load management, see [Warehouse handling of inbound loads for purchase orders](inbound-load-handling.md).</span></span>
