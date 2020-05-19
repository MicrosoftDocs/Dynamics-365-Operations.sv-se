---
title: Koder för påfyllnadssteg
description: Det här ämnet innehåller en översikt över koder för påfyllnadssteg och hur de används.
author: josaw1
manager: tfehr
ms.date: 09/06/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 251e9982451c888424589e0f0d6fce48aab42df1
ms.sourcegitcommit: 68092ed283bfbb7b6f611cce1b62c791f9b6a208
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/30/2020
ms.locfileid: "3323587"
---
# <a name="wave-step-codes"></a><span data-ttu-id="072a5-103">Koder för påfyllnadssteg</span><span class="sxs-lookup"><span data-stu-id="072a5-103">Wave step codes</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="072a5-104">Koder för påfyllnadssteg är koder som användarna kan ställa in och använda för att länka specifika förekomster av påfyllnadsmetoder till en motsvarande mall.</span><span class="sxs-lookup"><span data-stu-id="072a5-104">Wave step codes are codes that users can set up and use to link specific instances of wave methods to a corresponding template.</span></span> <span data-ttu-id="072a5-105">Mallarna innehåller mallar för påfyllning, skapande av behållare, etikettutskrift, lastuppbyggnad och sortering.</span><span class="sxs-lookup"><span data-stu-id="072a5-105">The templates include templates for replenishment, containerization, label printing, load building, and sorting.</span></span>

<span data-ttu-id="072a5-106">När koder för påfyllnadssteg inte används måste användarna ange fritext för att referera till en specifik mall från förekomst av påfyllnadsmetod.</span><span class="sxs-lookup"><span data-stu-id="072a5-106">When wave step codes aren't used, users must enter free text to reference a specific template from the wave method instance.</span></span> <span data-ttu-id="072a5-107">Fritext är benägen att bli fel, eftersom användare måste se till att påfyllnadsstegets text de lägger till för en specifik påfyllnadsstegmetoden i en vågmall exakt matchar påfyllnadsstegtexten i målmallen.</span><span class="sxs-lookup"><span data-stu-id="072a5-107">Free text is prone to errors because users must make sure that the wave step text that they add for a specific wave step method in a wave template exactly matches the wave step text in the target template.</span></span>

<span data-ttu-id="072a5-108">Påfyllnadskoderna för en viss typ av påfyllnadsstegtyp ställs in på en separat sida.</span><span class="sxs-lookup"><span data-stu-id="072a5-108">Wave step codes for a specific wave step type are set up on a separate page.</span></span> <span data-ttu-id="072a5-109">För varje instans av påfyllnadsstegmetod i en påfyllnadsmall som kräver en kod för påfyllnadssteg, måste koden för påfyllnadssteg väljas i en nedrullningsbar lista.</span><span class="sxs-lookup"><span data-stu-id="072a5-109">For every wave step method instance in a wave template that requires a wave step code, the wave step code must be selected in a drop-down list.</span></span> <span data-ttu-id="072a5-110">Markeringen i en nedrullningsbar lista ersätter text som är fritext och minskar risken och konsekvenserna av det mänskliga felet.</span><span class="sxs-lookup"><span data-stu-id="072a5-110">Selection in a drop-down list replaces free text entry and helps reduce the risk and impact of human error.</span></span> <span data-ttu-id="072a5-111">Inställningskoder används för att koppla en påfyllnadsstegmetod i en påfyllnadsmall till en målmall för metoden.</span><span class="sxs-lookup"><span data-stu-id="072a5-111">Setup codes are used to link a wave step method in a wave template to a target template for the method.</span></span>

> [!NOTE]
> <span data-ttu-id="072a5-112">Användning av funktionen för koder för påfyllnadssteg är valfri.</span><span class="sxs-lookup"><span data-stu-id="072a5-112">Use of the wave step codes feature is optional.</span></span> <span data-ttu-id="072a5-113">Det är aktiverat för hela organisationen för alla juridiska personer.</span><span class="sxs-lookup"><span data-stu-id="072a5-113">It is enabled organization-wide for all legal entities.</span></span>

## <a name="setup-demo"></a><span data-ttu-id="072a5-114">Demonstration av installation</span><span class="sxs-lookup"><span data-stu-id="072a5-114">Setup demo</span></span> 

<span data-ttu-id="072a5-115">För den här demonstrationen måste demonstrationsdata vara installerade och du måste använda **USMF**-demodataföretaget.</span><span class="sxs-lookup"><span data-stu-id="072a5-115">For this demo, demo data must be installed, and you must use the **USMF** demo data company.</span></span>

### <a name="enable-wave-step-codes"></a><span data-ttu-id="072a5-116">Aktivera koder för påfyllnadssteg</span><span class="sxs-lookup"><span data-stu-id="072a5-116">Enable wave step codes</span></span>

<span data-ttu-id="072a5-117">Följ de här stegen för att aktivera funktionen för koder för påfyllnadssteg.</span><span class="sxs-lookup"><span data-stu-id="072a5-117">Follow these steps to turn on the wave step codes feature.</span></span>

1. <span data-ttu-id="072a5-118">Gå till **Funktionshantering**.</span><span class="sxs-lookup"><span data-stu-id="072a5-118">Go to **Feature Management**.</span></span>
2. <span data-ttu-id="072a5-119">Välj om du vill aktivera funktionen som kallas **organisationsomfattande kod för påfyllnadssteg**.</span><span class="sxs-lookup"><span data-stu-id="072a5-119">Select to enable the feature called **Organization-wide Wave Step Code**.</span></span>

<span data-ttu-id="072a5-120">Alla befintliga fritexter för påfyllnadssteg i alla juridiska personer uppgraderas till den nya strukturen.</span><span class="sxs-lookup"><span data-stu-id="072a5-120">All existing wave step free texts in all legal entities are upgraded to the new structure.</span></span> <span data-ttu-id="072a5-121">När uppgraderingen har slutförts för alla juridiska personer är funktionen aktiverad.</span><span class="sxs-lookup"><span data-stu-id="072a5-121">After this upgrade is completed for all legal entities, then the feature is enabled.</span></span> <span data-ttu-id="072a5-122">Om funktionen inte kan aktiveras för en eller flera juridiska personer, är funktionen inte aktiverad för alla juridiska personer.</span><span class="sxs-lookup"><span data-stu-id="072a5-122">If the feature cannot be enabled for one or more legal entities, then the feature is not enabled for any legal entities.</span></span>

<span data-ttu-id="072a5-123">Under inställningar görs valideringar under datauppgraderingen.</span><span class="sxs-lookup"><span data-stu-id="072a5-123">During the enablement, validations are done during the data upgrade.</span></span> <span data-ttu-id="072a5-124">Om uppgraderingen misslyckas visas ett felmeddelande.</span><span class="sxs-lookup"><span data-stu-id="072a5-124">If the upgrade fails, you receive an error message.</span></span> <span data-ttu-id="072a5-125">En uppgradering kan misslyckas på grund av följande konflikter:</span><span class="sxs-lookup"><span data-stu-id="072a5-125">An upgrade might fail because of the following conflicts:</span></span>

- <span data-ttu-id="072a5-126">Dubbla fritexter för påfyllnadssteg finns.</span><span class="sxs-lookup"><span data-stu-id="072a5-126">Duplicate wave step free texts exist.</span></span>
- <span data-ttu-id="072a5-127">Anpassningar finns.</span><span class="sxs-lookup"><span data-stu-id="072a5-127">Customizations exist.</span></span>
- <span data-ttu-id="072a5-128">En fritext för påfyllnadssteg som hör till en instans för påfyllnadsstegmetod matchar inte den förväntade malltypen.</span><span class="sxs-lookup"><span data-stu-id="072a5-128">A wave step free text that is associated with a wave step method instance doesn't match the expected template type.</span></span>

<span data-ttu-id="072a5-129">När du har löst alla konflikter som har identifierats under valideringen kan du köra försök igen för att aktivera funktionen.</span><span class="sxs-lookup"><span data-stu-id="072a5-129">After you've resolved any conflicts that are identified during the validations, you can retry to enable the feature.</span></span>

<span data-ttu-id="072a5-130">När funktionen har aktiverats, kommer sidan **koder för påfyllnadssteg** (**Lagerstyrning \> Inställning \> Påfyllnad \> Koder för påfyllnadssteg**) tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="072a5-130">When the feature has been enabled, the **Wave step codes** page (**Warehouse management \> Setup \> Waves \> Wave step codes**) becomes available.</span></span> <span data-ttu-id="072a5-131">På den här sidan visas de koder för påfyllnadssteg som uppgraderades när funktionen organisationsomfattande kod för påfyllnadssteg aktiverades.</span><span class="sxs-lookup"><span data-stu-id="072a5-131">This page lists the wave step codes that were upgraded when the Organization-wide Wave Step Code feature was enabled.</span></span>

### <a name="create-new-wave-step-codes"></a><span data-ttu-id="072a5-132">Skapa nya koder för påfyllnadssteg</span><span class="sxs-lookup"><span data-stu-id="072a5-132">Create new wave step codes</span></span>

<span data-ttu-id="072a5-133">Du kan använda sidan the **Koder för påfyllnadssteg** för att skapa och ta bort koder för påfyllnadssteg.</span><span class="sxs-lookup"><span data-stu-id="072a5-133">You can use the **Wave step codes** page to create and delete wave step codes.</span></span>

<span data-ttu-id="072a5-134">Varje ny kod för påfyllnadssteg och dess associerade ID måste vara unika för alla typer av påfyllnadssteg ch de måste definieras för en viss typ av påfyllnadssteg.</span><span class="sxs-lookup"><span data-stu-id="072a5-134">Every new wave step code and its associated ID must be unique across all wave step types, and they must be defined for a specific wave step type.</span></span>

### <a name="apply-wave-step-codes"></a><span data-ttu-id="072a5-135">Tillämpa koder för påfyllnadssteg</span><span class="sxs-lookup"><span data-stu-id="072a5-135">Apply wave step codes</span></span>

<span data-ttu-id="072a5-136">När du har definierat lämpliga koder för påfyllnadssteg kan de tillämpas på påfyllnadsprocessmetoderna.</span><span class="sxs-lookup"><span data-stu-id="072a5-136">After you've defined the appropriate wave step codes, they can be applied to the wave process methods.</span></span>

<span data-ttu-id="072a5-137">Om du vill använda koder för påfyllnadssteg går du till rätt målmall.</span><span class="sxs-lookup"><span data-stu-id="072a5-137">To apply wave step codes, go to the appropriate target template.</span></span> <span data-ttu-id="072a5-138">Nedan visas de målmallar som koder för påfyllnadssteg är avsedda att peka på:</span><span class="sxs-lookup"><span data-stu-id="072a5-138">Here are the target templates that the wave step codes are designated to point to:</span></span>

- <span data-ttu-id="072a5-139">**Mallar för lagerpåfyllnad:** Lagerstyrning \> Inställningar \> Lagerpåfyllnad \> Mallar för lagerpåfyllnad</span><span class="sxs-lookup"><span data-stu-id="072a5-139">**Replenishment templates:** Warehouse management \> Setup \> Replenishment \> Replenishment templates</span></span>
- <span data-ttu-id="072a5-140">**Lastuppbyggnadsmallar:** Lagerstyrning \> Inställningar \> Last \> Lastuppbyggnadsmallar</span><span class="sxs-lookup"><span data-stu-id="072a5-140">**Load build templates:** Warehouse management \> Setup \> Load \> Load build templates</span></span>
- <span data-ttu-id="072a5-141">**Sortera mallar:** Lagerstyrning \> Inställningar \> Förpackning \> Utgående sorteringsmallar</span><span class="sxs-lookup"><span data-stu-id="072a5-141">**Sort templates:** Warehouse management \> Setup \> Packing \> Outbound sorting templates</span></span>
- <span data-ttu-id="072a5-142">**Mallar för skapande av behållare:** Lagerstyrning \> Inställningar \> Behållare \> Mall för skapande av behållare.</span><span class="sxs-lookup"><span data-stu-id="072a5-142">**Containerization templates:** Warehouse management \> Setup \> Containers \> Container build templates</span></span>
- <span data-ttu-id="072a5-143">**Mallar för etikettutskrift:** Lagerstyrning \> Inställningar \> Dokumentflöde \> Mallar för påfyllnadsetikett</span><span class="sxs-lookup"><span data-stu-id="072a5-143">**Label printing templates:** Warehouse management \> Setup \> Document routing \> Wave label templates</span></span>

<span data-ttu-id="072a5-144">Mallarna i den här listan tillämpas när de refereras från en påfyllnadsprocessmetod som är vald i en påfyllnadsmall.</span><span class="sxs-lookup"><span data-stu-id="072a5-144">The templates in this list are applied when they are referenced from a wave process method that is selected in a wave template.</span></span> <span data-ttu-id="072a5-145">När påfyllnadsstegkoden i en påfyllnadsprocessmetod i en påfyllnadsmall matchar påfyllnadsstegkoden i en av malltyperna används mallen.</span><span class="sxs-lookup"><span data-stu-id="072a5-145">When the wave step code on a wave process method in a wave template matches the wave step code in one of the templates types, the template is applied.</span></span>

### <a name="sample-scenario"></a><span data-ttu-id="072a5-146">Exempelscenario</span><span class="sxs-lookup"><span data-stu-id="072a5-146">Sample scenario</span></span>

<span data-ttu-id="072a5-147">Följande procedur garanterar att den påfyllnadsmall som du har skapat kommer att användas för påfyllnadsmallen.</span><span class="sxs-lookup"><span data-stu-id="072a5-147">The following procedure helps guarantee that the replenishment template that you created will be applied for the wave template.</span></span>

1. <span data-ttu-id="072a5-148">Gå till **Lagerstyrning \> Inställningar \> Påfyllnad \> Koder för påfyllnadssteg** och skapa en kod för påfyllnadssteg för typen **Lagerpåfyllnad**.</span><span class="sxs-lookup"><span data-stu-id="072a5-148">Go to **Warehouse management \> Setup \> Waves \> Wave step codes**, and create a wave step code for the **Replenishment** type.</span></span>
2. <span data-ttu-id="072a5-149">Gå till **Lagerstyrning \> Inställningar \> Lagerpåfyllnad \> Mallar för lagerpåfyllnad** och skapa en mall för lagerpåfyllnad.</span><span class="sxs-lookup"><span data-stu-id="072a5-149">Go to **Warehouse management \> Setup \> Replenishment \> Replenishment templates**, and create a replenishment template.</span></span>
3. <span data-ttu-id="072a5-150">I mallen för lagerpåfyllnad väljer du koden för påfyllningssteg som du skapade för typen **Lagerpåfyllnad**.</span><span class="sxs-lookup"><span data-stu-id="072a5-150">In the replenishment template, select the wave step code that you created for the **Replenishment** type.</span></span>
4. <span data-ttu-id="072a5-151">Gå till **Lagerstyrning \> Inställningar \> Påfyllnader \> Påfyllnadsmallar** och välj den våg som du tänker använda.</span><span class="sxs-lookup"><span data-stu-id="072a5-151">Go to **Warehouse management \> Setup \> Waves \> Wave templates**, and select the wave template that you intend to use.</span></span>
5. <span data-ttu-id="072a5-152">I mallen, på snabbfliken **Metoder**, välj metoden **Lagerpåfyllnad**.</span><span class="sxs-lookup"><span data-stu-id="072a5-152">In the template, on the **Methods** FastTab, select the **Replenishment** method.</span></span>
6. <span data-ttu-id="072a5-153">I fältet **Kod för påfyllnadssteg**, välj koden för påfyllningssteg som du valde i lagerpåfyllnadsmallen.</span><span class="sxs-lookup"><span data-stu-id="072a5-153">In the **Wave step code** field, select the wave step code that you selected in the replenishment template.</span></span>

<span data-ttu-id="072a5-154">Du utför dessa steg för varje juridisk person.</span><span class="sxs-lookup"><span data-stu-id="072a5-154">You perform these steps for each legal entity.</span></span>
