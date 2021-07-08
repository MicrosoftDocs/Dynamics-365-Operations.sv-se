---
title: Påfyllnadsmetoder och kvantitetsändring
description: Det här ämnet innehåller information om påfyllnadsmetoder i Planeringsoptimering. Det förklarar också hur flera orderkvantitet för en produkt påverkar resultatet.
author: crytt
ms.date: 6/1/2021
ms.topic: article
ms.search.form: ReqGroup, ReqItemTable, InventItemOrderSetup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2021-06-01
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d5e0e671e624de2646a47647ef08d3567599b884
ms.sourcegitcommit: 4cbd83e21a78459e4711a2dedba0f5a7acc3c841
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/15/2021
ms.locfileid: "6261706"
---
# <a name="replenishment-methods-and-quantity-modification"></a><span data-ttu-id="71788-104">Påfyllnadsmetoder och kvantitetsändring</span><span class="sxs-lookup"><span data-stu-id="71788-104">Replenishment methods and quantity modification</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="71788-105">Det här ämnet innehåller information om påfyllnadsmetoder i Planeringsoptimering.</span><span class="sxs-lookup"><span data-stu-id="71788-105">This topic provides information about replenishment methods in Planning Optimization.</span></span> <span data-ttu-id="71788-106">Det förklarar också hur flera orderkvantitet för en produkt påverkar resultatet.</span><span class="sxs-lookup"><span data-stu-id="71788-106">It also explains how the multiple order quantity for a product affects the result.</span></span>

<span data-ttu-id="71788-107">Påfyllnadsmetoder kallas också för disponeringsmetoder och partistorleksmetoder.</span><span class="sxs-lookup"><span data-stu-id="71788-107">Replenishment methods are also known as coverage methods and lot-sizing methods.</span></span>

## <a name="coverage-codes"></a><span data-ttu-id="71788-108">Täckningskoder</span><span class="sxs-lookup"><span data-stu-id="71788-108">Coverage codes</span></span>

<span data-ttu-id="71788-109">Planeringsoptimering kan konfigureras till att använda olika återanskaffningsmetoder.</span><span class="sxs-lookup"><span data-stu-id="71788-109">Planning Optimization can be configured to use different replenishment methods.</span></span> <span data-ttu-id="71788-110">Påfyllnadsmetoderna är de tekniker som systemet använder för att beräkna behoven för en produkt.</span><span class="sxs-lookup"><span data-stu-id="71788-110">The replenishment methods are the techniques that the system uses to calculate requirements for a product.</span></span> <span data-ttu-id="71788-111">Påfyllnadsmetoder definieras per disponeringskoder som du kan ställa in för disponeringsgruppen eller produkten.</span><span class="sxs-lookup"><span data-stu-id="71788-111">Replenishment methods are defined by coverage codes that you can set up on either the coverage group or the product.</span></span>

<span data-ttu-id="71788-112">Följande disponeringskoder kan användas vid planeringsoptimering:</span><span class="sxs-lookup"><span data-stu-id="71788-112">The following coverage codes can be used in Planning Optimization:</span></span>

- <span data-ttu-id="71788-113">**Period** - den påfyllnadsmetod som kombinerar hela efter frågan för en period till en order för produkt.</span><span class="sxs-lookup"><span data-stu-id="71788-113">**Period** – The replenishment method combines all the demand for a period into one order for the product.</span></span> <span data-ttu-id="71788-114">Ordern planeras under den första dagen i perioden och dess kvantitet uppfyller nettokraven under den fastställda perioden.</span><span class="sxs-lookup"><span data-stu-id="71788-114">The order will be planned for the first day of the period, and its quantity will fulfill the net requirements during the established period.</span></span> <span data-ttu-id="71788-115">Perioden inleds med det första efter frågan av produkten och täcker den definierade tiden i tid.</span><span class="sxs-lookup"><span data-stu-id="71788-115">The period starts with the first demand of the product and covers the defined length of time.</span></span> <span data-ttu-id="71788-116">Nästa period kommer att inledas med nästa behov av produkten.</span><span class="sxs-lookup"><span data-stu-id="71788-116">The next period will start with the next requirements of the product.</span></span> <span data-ttu-id="71788-117">Disponeringskod *Period* används ofta för icke-förutsägbar inventering, säsongspåverkade produkter eller högkostnadsprodukter.</span><span class="sxs-lookup"><span data-stu-id="71788-117">The *Period* coverage code is often used for non-predictable inventory draw, season-influenced products, or high-cost products.</span></span> <span data-ttu-id="71788-118">Illustrationen nedan visar ett exempel.</span><span class="sxs-lookup"><span data-stu-id="71788-118">The following illustration shows an example.</span></span>

    <span data-ttu-id="71788-119">![Exempel på användning av period disponeringskod](./media/coverage-code-period.png "Exempel på användning av period disponeringskod")</span><span class="sxs-lookup"><span data-stu-id="71788-119">![Example of Period coverage code use](./media/coverage-code-period.png "Example of Period coverage code use")</span></span>

- <span data-ttu-id="71788-120">**Krav** - I påfyllnadsmetod i vilken systemet skapar en planerad inköps-, överförings- eller produktionsorder per behov för artikeln.</span><span class="sxs-lookup"><span data-stu-id="71788-120">**Requirement** – In the replenishment method, the system creates a planned purchase, transfer, or production order per requirement for the product.</span></span> <span data-ttu-id="71788-121">Denna metod används för höga produkter som har återkommande efterfrågan.</span><span class="sxs-lookup"><span data-stu-id="71788-121">This method is used for expensive products that have intermittent demand.</span></span> <span data-ttu-id="71788-122">Disponeringskod *Krav* används ofta för konfigurerbara produkter eller scenarier som måste beställas.</span><span class="sxs-lookup"><span data-stu-id="71788-122">The *Requirement* coverage code is often used for configurable products or make-to-order scenarios.</span></span> <span data-ttu-id="71788-123">Illustrationen nedan visar ett exempel.</span><span class="sxs-lookup"><span data-stu-id="71788-123">The following illustration shows an example.</span></span>

    <span data-ttu-id="71788-124">![Exempel på användning av krav disponeringskod](./media/coverage-code-requirement.png "Exempel på användning av krav disponeringskod")</span><span class="sxs-lookup"><span data-stu-id="71788-124">![Example of Requirement coverage code use](./media/coverage-code-requirement.png "Example of Requirement coverage code use")</span></span>

- <span data-ttu-id="71788-125">**Min./Max.**</span><span class="sxs-lookup"><span data-stu-id="71788-125">**Min./Max.**</span></span> <span data-ttu-id="71788-126">– Påfyllnadsmetoden baseras på lagernivån.</span><span class="sxs-lookup"><span data-stu-id="71788-126">– The replenishment method is based on the inventory level.</span></span> <span data-ttu-id="71788-127">Den definierar påfyllnaden av lagret upp till en specifik nivå när den prognosterade lagerbehållningsnivån är under ett specifikt tröskelvärde.</span><span class="sxs-lookup"><span data-stu-id="71788-127">It defines the replenishment of inventory up to a specific level when the predicted on-hand level is below a specific threshold.</span></span> <span data-ttu-id="71788-128">Kvantiteten för påfyllnaden är differensen mellan den högsta nivån och den förutsagda behållningsnivån.</span><span class="sxs-lookup"><span data-stu-id="71788-128">The replenishment quantity will be the difference between the maximum level and the predicted on-hand level.</span></span> <span data-ttu-id="71788-129">*Minsta/högsta.*</span><span class="sxs-lookup"><span data-stu-id="71788-129">The *Min./Max.*</span></span> <span data-ttu-id="71788-130">disponeringskod används ofta för förutsägbar inventering, höga kostnader eller billigaste produkter.</span><span class="sxs-lookup"><span data-stu-id="71788-130">coverage code is often used for predictable inventory draw, high runners, or less expensive products.</span></span> <span data-ttu-id="71788-131">Illustrationen nedan visar ett exempel.</span><span class="sxs-lookup"><span data-stu-id="71788-131">The following illustration shows an example.</span></span>

    <span data-ttu-id="71788-132">![Exempel på användning av min/max disponeringskod](./media/coverage-code-min-max.png "Exempel på användning av min/max disponeringskod")</span><span class="sxs-lookup"><span data-stu-id="71788-132">![Example of Min./Max. coverage code use](./media/coverage-code-min-max.png "Example of Min./Max. coverage code use")</span></span>

- <span data-ttu-id="71788-133">**Manuell** - Påfyllnadsmetoden för partistorlek där systemet inte föreslår inköps-, överförings- eller tillverkningsorder för produkten.</span><span class="sxs-lookup"><span data-stu-id="71788-133">**Manual** – In the replenishment method, the system doesn't suggest purchase, transfer, or production orders for the product.</span></span> <span data-ttu-id="71788-134">I stället ansvarar planeraren för produkten för att skapa de order som krävs för påfyllnaden av produkten.</span><span class="sxs-lookup"><span data-stu-id="71788-134">Instead, the planner for the product is responsible for creating the required orders for the replenishment of the product.</span></span> <span data-ttu-id="71788-135">*Manuell* disponeringskod används ofta för produkter som systemgenererade planerade order inte är önskade för.</span><span class="sxs-lookup"><span data-stu-id="71788-135">The *Manual* coverage code is often used for products that system-generated planned orders aren't wanted for.</span></span>

## <a name="impact-of-the-order-quantity-from-default-order-settings"></a><span data-ttu-id="71788-136">Inverkan från standardorderinställningarna för orderkvantiteten</span><span class="sxs-lookup"><span data-stu-id="71788-136">Impact of the order quantity from default order settings</span></span>

<span data-ttu-id="71788-137">På sidan **inställning för standardorder** för en frisläppt produkt kan du ange följande kvantitetsinställningar på snabbflikarna **Inköpsorder**, **Lager** och **Försäljningsorder**.</span><span class="sxs-lookup"><span data-stu-id="71788-137">On the **Default order setting** page for a released product, you can specify each of following quantity settings on the **Purchase order**, **Inventory**, and **Sales order** FastTabs.</span></span> <span data-ttu-id="71788-138">(Snabbfliken **Lager** används för både överföringsorder och tillverkningsorder.)</span><span class="sxs-lookup"><span data-stu-id="71788-138">(The **Inventory** FastTab is used for both transfer orders and production orders.)</span></span>

- <span data-ttu-id="71788-139">**Flera** – Planerade order kommer att vara en multipel av den här kvantiteten.</span><span class="sxs-lookup"><span data-stu-id="71788-139">**Multiple** – Planned orders will be a multiple of this quantity.</span></span>

    <span data-ttu-id="71788-140">Till exempel om fältet **Flera** anges till *5*, kan en order vara för kvantiteten 5, 10, 15, 20 och så vidare.</span><span class="sxs-lookup"><span data-stu-id="71788-140">For example, if the **Multiple** field is set to *5*, an order can be for a quantity of 5, 10, 15, 20, and so on.</span></span>

- <span data-ttu-id="71788-141">**Minsta orderkvantitet** – Planerade order understiger inte det angivna värdet.</span><span class="sxs-lookup"><span data-stu-id="71788-141">**Min. order quantity** – Planned orders won't be less than the specified value.</span></span>

    <span data-ttu-id="71788-142">Om till exempel fältet **Minsta orderkvantitet** är inställt på *10*, skapas en planerad order med kvantiteten 10, även om det bara krävs fyra för att uppfylla efterfrågan.</span><span class="sxs-lookup"><span data-stu-id="71788-142">For example, if the **Min. order quantity** field is set to *10*, a planned order for a quantity of 10 will be created, even if only four are required to fulfill the demand.</span></span>

- <span data-ttu-id="71788-143">**Högsta orderkvantitet** – Planerade order överstiger inte det angivna värdet.</span><span class="sxs-lookup"><span data-stu-id="71788-143">**Max. order quantity** – Planned orders won't exceed the specified value.</span></span> <span data-ttu-id="71788-144">Om efterfrågan är större än värdet **Maximal orderkvantitet** skapas flera planerade order för att täcka den.</span><span class="sxs-lookup"><span data-stu-id="71788-144">If the demand is more than the **Max. order quantity** value, multiple planned orders will be created to cover it.</span></span>

    <span data-ttu-id="71788-145">Om till exempel fältet **Max. orderkvantitet** är inställt på *100* och efterfrågan är 450, skapas fyra planerade order för kvantiteten 100 och en planerad order för kvantiteten 50.</span><span class="sxs-lookup"><span data-stu-id="71788-145">For example, if the **Max. order quantity** field is set to *100*, and the demand is 450, four planned orders for a quantity of 100 and one planned order for a quantity of 50 will be created.</span></span>

## <a name="examples-of-replenishment-that-use-the-minmax-coverage-code"></a><span data-ttu-id="71788-146">Exempel på påfyllnad där min./max används.</span><span class="sxs-lookup"><span data-stu-id="71788-146">Examples of replenishment that use the Min./Max.</span></span> <span data-ttu-id="71788-147">disponeringskod</span><span class="sxs-lookup"><span data-stu-id="71788-147">coverage code</span></span>

<span data-ttu-id="71788-148">Om du inte anger ett värde i fältet **Flera** för en produkt på sidan **inställning för standardorder**, och om du använder *Min./Max.*</span><span class="sxs-lookup"><span data-stu-id="71788-148">If you don't specify a value in the **Multiple** field for a product on the **Default order setting** page, and if you're using the *Min./Max.*</span></span> <span data-ttu-id="71788-149">påfyllnadsmetod kommer Planeringsoptimering fylla på lagret till en specifik nivå när den prognostiserade lagerbehållningsnivån är under ett specifikt tröskelvärde.</span><span class="sxs-lookup"><span data-stu-id="71788-149">replenishment method, Planning Optimization will replenish the inventory up to a specific level when the predicted on-hand level is below a specific threshold.</span></span>

<span data-ttu-id="71788-150">Om du definierar en multipelkvantitet för en produkt måste du ange *Min./Max.*</span><span class="sxs-lookup"><span data-stu-id="71788-150">If you define a multiple quantity for a product, the *Min./Max.*</span></span> <span data-ttu-id="71788-151">påfyllnadsmetoden ändrar dess beteende och tar hänsyn till värdet **flera**.</span><span class="sxs-lookup"><span data-stu-id="71788-151">replenishment method changes its behavior and considers the **Multiple** value.</span></span>

<span data-ttu-id="71788-152">Med andra ord fyller Planeringsoptimering fortfarande på lagret upp till den definierade maximinivån när den förutsagda behållningsnivån är mindre än den definierade miniminivån.</span><span class="sxs-lookup"><span data-stu-id="71788-152">In other words, Planning Optimization will still replenish the inventory up to the defined maximum level when the predicted on-hand level is less than the defined minimum level.</span></span> <span data-ttu-id="71788-153">Påfyllnadskvantiteten måste dock vara en multipel av värdet **Flera**.</span><span class="sxs-lookup"><span data-stu-id="71788-153">However, the replenishment quantity must be a multiple of the **Multiple** value.</span></span>

<span data-ttu-id="71788-154">Om påfyllnadskvantiteten (skillnaden mellan maximinivån och den sagda lagerhållningsnivån) inte är en multipel av den definierade multipelkvantiteten, använder Planeringsoptimering det första möjliga värdet som, tillsammans med förutsagd behållningsnivå, kommer att vara under maximinivån.</span><span class="sxs-lookup"><span data-stu-id="71788-154">If the replenishment quantity (the difference between the maximum level and the predicted on-hand level) isn't a multiple of the defined multiple quantity, Planning Optimization uses the first possible value that, together with predicted on-hand level, will be below the maximum level.</span></span> <span data-ttu-id="71788-155">Om summan är mindre än miniminivån använder Planeringsoptimering det första värdet som, tillsammans med förväntad behållning, ligger över maximinivån.</span><span class="sxs-lookup"><span data-stu-id="71788-155">If the sum is less than the minimum level, Planning Optimization uses the first value that, together with predicted on-hand, will be above the maximum level.</span></span>

<span data-ttu-id="71788-156">Följande delgrupper innehåller några exempel som visar hur multipeln av orderkvantiteten för en produkt påverkar resultatet av *Min./Max.*</span><span class="sxs-lookup"><span data-stu-id="71788-156">The following subsections provide some examples that show how the multiple order quantity for a product affects the result of the *Min./Max.*</span></span> <span data-ttu-id="71788-157">lagerpåfyllnadsmetod.</span><span class="sxs-lookup"><span data-stu-id="71788-157">replenishment method.</span></span>

### <a name="example-1"></a><span data-ttu-id="71788-158">Exempel 1</span><span class="sxs-lookup"><span data-stu-id="71788-158">Example 1</span></span>

<span data-ttu-id="71788-159">En produkt har följande konfiguration:</span><span class="sxs-lookup"><span data-stu-id="71788-159">A product has the following configuration:</span></span>

- <span data-ttu-id="71788-160">**Disponeringskod:** *Min./Max.*</span><span class="sxs-lookup"><span data-stu-id="71788-160">**Coverage code:** *Min./Max.*</span></span>
- <span data-ttu-id="71788-161">**Minimum:** *15*</span><span class="sxs-lookup"><span data-stu-id="71788-161">**Minimum:** *15*</span></span>
- <span data-ttu-id="71788-162">**Maximum:** *22*</span><span class="sxs-lookup"><span data-stu-id="71788-162">**Maximum:** *22*</span></span>
- <span data-ttu-id="71788-163">**Flera:** *0*</span><span class="sxs-lookup"><span data-stu-id="71788-163">**Multiple:** *0*</span></span>

<span data-ttu-id="71788-164">Det finns 10 stycken i lagerbehållning och det finns ingen annan efterfrågan eller leverans.</span><span class="sxs-lookup"><span data-stu-id="71788-164">There are 10 pieces of on-hand inventory for the product, and there is no other demand or supply.</span></span>

<span data-ttu-id="71788-165">När huvudplaneringen körs skapas en planerad order på 12 enheter för att fylla på lagret till maximikvantiteten.</span><span class="sxs-lookup"><span data-stu-id="71788-165">When master planning runs, a planned order for 12 pieces is created to replenish inventory to the maximum quantity.</span></span>

### <a name="example-2"></a><span data-ttu-id="71788-166">Exempel 2</span><span class="sxs-lookup"><span data-stu-id="71788-166">Example 2</span></span>

<span data-ttu-id="71788-167">En produkt har följande konfiguration:</span><span class="sxs-lookup"><span data-stu-id="71788-167">A product has the following configuration:</span></span>

- <span data-ttu-id="71788-168">**Disponeringskod:** *Min./Max.*</span><span class="sxs-lookup"><span data-stu-id="71788-168">**Coverage code:** *Min./Max.*</span></span>
- <span data-ttu-id="71788-169">**Minimum:** *15*</span><span class="sxs-lookup"><span data-stu-id="71788-169">**Minimum:** *15*</span></span>
- <span data-ttu-id="71788-170">**Maximum:** *22*</span><span class="sxs-lookup"><span data-stu-id="71788-170">**Maximum:** *22*</span></span>
- <span data-ttu-id="71788-171">**Flera:** *5*</span><span class="sxs-lookup"><span data-stu-id="71788-171">**Multiple:** *5*</span></span>

<span data-ttu-id="71788-172">Det finns 10 stycken i lagerbehållning och det finns ingen annan efterfrågan eller leverans.</span><span class="sxs-lookup"><span data-stu-id="71788-172">There are 10 pieces of on-hand inventory for the product, and there is no other demand or supply.</span></span>

<span data-ttu-id="71788-173">När huvudplaneringen körs skapas en planerad order på tio enheter (eftersom 15 påfyllnadsdelar plus 10 lagerdelar överskrider maximikvantiteten).</span><span class="sxs-lookup"><span data-stu-id="71788-173">When master planning runs, a planned order for 10 pieces is created (because 15 pieces of replenishment plus 10 pieces of on-hand inventory will exceed the maximum quantity).</span></span>

### <a name="example-3"></a><span data-ttu-id="71788-174">Exempel 3</span><span class="sxs-lookup"><span data-stu-id="71788-174">Example 3</span></span>

<span data-ttu-id="71788-175">En produkt har följande konfiguration:</span><span class="sxs-lookup"><span data-stu-id="71788-175">A product has the following configuration:</span></span>

- <span data-ttu-id="71788-176">**Disponeringskod:** *Min./Max.*</span><span class="sxs-lookup"><span data-stu-id="71788-176">**Coverage code:** *Min./Max.*</span></span>
- <span data-ttu-id="71788-177">**Minimum:** *21*</span><span class="sxs-lookup"><span data-stu-id="71788-177">**Minimum:** *21*</span></span>
- <span data-ttu-id="71788-178">**Maximum:** *24*</span><span class="sxs-lookup"><span data-stu-id="71788-178">**Maximum:** *24*</span></span>
- <span data-ttu-id="71788-179">**Flera:** *5*</span><span class="sxs-lookup"><span data-stu-id="71788-179">**Multiple:** *5*</span></span>

<span data-ttu-id="71788-180">Det finns 10 stycken i lagerbehållning och det finns ingen annan efterfrågan eller leverans.</span><span class="sxs-lookup"><span data-stu-id="71788-180">There are 10 pieces of on-hand inventory for the product, and there is no other demand or supply.</span></span>

<span data-ttu-id="71788-181">När huvudplaneringen körs skapas en planerad order på tio enheter (eftersom 10 påfyllnadsdelar plus 15 lagerdelar är mindre än minimikvantiteten).</span><span class="sxs-lookup"><span data-stu-id="71788-181">When master planning runs, the planned order for 15 pieces is created (because 10 pieces of replenishment plus 10 pieces of on-hand inventory will be less than the minimum quantity).</span></span>

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
