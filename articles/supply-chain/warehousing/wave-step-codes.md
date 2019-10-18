---
title: Koder för påfyllnadssteg
description: Det här ämnet innehåller en översikt över koder för påfyllnadssteg och hur de används.
author: josaw1
manager: AnnBe
ms.date: 09/06/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 0f89c6098db9e2e3a9aa4ee3666e4b9ae608f054
ms.sourcegitcommit: d8f1135cdbc2deca70bc4b2805a0519253c9a31f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/06/2019
ms.locfileid: "1992367"
---
# <a name="wave-step-codes"></a><span data-ttu-id="173c7-103">Koder för påfyllnadssteg</span><span class="sxs-lookup"><span data-stu-id="173c7-103">Wave step codes</span></span>

[!include [banner](../includes/preview-banner.md)]
[!include [banner](../includes/banner.md)]

## <a name="about-wave-step-codes"></a><span data-ttu-id="173c7-104">Om koder för påfyllnadssteg</span><span class="sxs-lookup"><span data-stu-id="173c7-104">About wave step codes</span></span>

<span data-ttu-id="173c7-105">Koder för påfyllnadssteg är koder som användarna kan ställa in och använda för att länka specifika förekomster av påfyllnadsmetoder till en motsvarande mall.</span><span class="sxs-lookup"><span data-stu-id="173c7-105">Wave step codes are codes that users can set up and use to link specific instances of wave methods to a corresponding template.</span></span> <span data-ttu-id="173c7-106">Mallarna innehåller mallar för påfyllning, skapande av behållare, etikettutskrift, lastuppbyggnad och sortering.</span><span class="sxs-lookup"><span data-stu-id="173c7-106">The templates include templates for replenishment, containerization, label printing, load building, and sorting.</span></span>

<span data-ttu-id="173c7-107">När koder för påfyllnadssteg inte används måste användarna ange fritext för att referera till en specifik mall från förekomst av påfyllnadsmetod.</span><span class="sxs-lookup"><span data-stu-id="173c7-107">When wave step codes aren't used, users must enter free text to reference a specific template from the wave method instance.</span></span> <span data-ttu-id="173c7-108">Fritext är benägen att bli fel, eftersom användare måste se till att påfyllnadsstegets text de lägger till för en specifik påfyllnadsstegmetoden i en vågmall exakt matchar påfyllnadsstegtexten i målmallen.</span><span class="sxs-lookup"><span data-stu-id="173c7-108">Free text is prone to error, because users must make sure that the wave step text that they add for a specific wave step method in a wave template exactly matches the wave step text in the target template.</span></span>

<span data-ttu-id="173c7-109">Påfyllnadskoderna för en viss typ av påfyllnadsstegtyp ställs in på en separat sida.</span><span class="sxs-lookup"><span data-stu-id="173c7-109">Wave step codes for a specific wave step type are set up on a separate page.</span></span> <span data-ttu-id="173c7-110">För varje instans av påfyllnadsstegmetod i en påfyllnadsmall som kräver en kod för påfyllnadssteg, måste koden för påfyllnadssteg väljas i en nedrullningsbar lista.</span><span class="sxs-lookup"><span data-stu-id="173c7-110">For every wave step method instance in a wave template that requires a wave step code, the wave step code must be selected in a drop-down list.</span></span> <span data-ttu-id="173c7-111">Markeringen i en nedrullningsbar lista ersätter text som är fritext och minskar risken och konsekvenserna av det mänskliga felet.</span><span class="sxs-lookup"><span data-stu-id="173c7-111">Selection in a drop-down list replaces free text entry and helps reduce the risk and impact of human error.</span></span> <span data-ttu-id="173c7-112">Inställningskoder används för att koppla en påfyllnadsstegmetod i en påfyllnadsmall till en målmall för metoden.</span><span class="sxs-lookup"><span data-stu-id="173c7-112">Setup codes are used to link a wave step method in a wave template to a target template for the method.</span></span>

> [!NOTE]
> <span data-ttu-id="173c7-113">Användningen av koder för påfyllnadssteg är valfri och upptagning är per juridisk person.</span><span class="sxs-lookup"><span data-stu-id="173c7-113">Use of the wave step codes feature is optional, and uptake is per legal entity.</span></span> <span data-ttu-id="173c7-114">Om en viss juridisk person använder funktionen uppgraderas därför alla befintliga koder för påfyllnadssteg i den juridiska personen till den nya strukturen.</span><span class="sxs-lookup"><span data-stu-id="173c7-114">Therefore, if a specific legal entity uses the feature, all existing wave step codes in that legal entity are upgraded to the new structure.</span></span>

## <a name="setup-demo"></a><span data-ttu-id="173c7-115">Demonstration av installation</span><span class="sxs-lookup"><span data-stu-id="173c7-115">Setup demo</span></span> 

<span data-ttu-id="173c7-116">För den här demonstrationen måste demonstrationsdata vara installerade och du måste använda **USMF**-demodataföretaget.</span><span class="sxs-lookup"><span data-stu-id="173c7-116">For this demo, demo data must be installed, and you must use the **USMF** demo data company.</span></span>

### <a name="enable-wave-step-codes"></a><span data-ttu-id="173c7-117">Aktivera koder för påfyllnadssteg</span><span class="sxs-lookup"><span data-stu-id="173c7-117">Enable wave step codes</span></span>

<span data-ttu-id="173c7-118">Följ de här stegen för att aktivera funktionen för koder för påfyllnadssteg.</span><span class="sxs-lookup"><span data-stu-id="173c7-118">Follow these steps to turn on the wave step codes feature.</span></span>

1. <span data-ttu-id="173c7-119">Gå till **Lagerstyrning \> Inställningar \> Parametrar för lagerstyrning**.</span><span class="sxs-lookup"><span data-stu-id="173c7-119">Go to **Warehouse management \> Setup \> Warehouse management parameters**.</span></span>
2. <span data-ttu-id="173c7-120">På fliken **Allmän** på snabbfliken **Påfyllnadsbearbetning**, ange alternativet **Aktivera koder för påfyllnadssteg** som **Ja**.</span><span class="sxs-lookup"><span data-stu-id="173c7-120">On the **General** tab, on the **Wave processing** FastTab, set the **Enable wave step codes** option to **Yes**.</span></span>

<span data-ttu-id="173c7-121">Alla befintliga fritexter för påfyllnadssteg uppgraderas till den nya strukturen.</span><span class="sxs-lookup"><span data-stu-id="173c7-121">All existing wave step free texts are upgraded to the new structure.</span></span> <span data-ttu-id="173c7-122">När den här uppgraderingen har slutförts för en juridisk person är alternativet **Aktivera koder för påfyllnadssteg** inte längre tillgängligt på sidan **Parametrar för lagerstyrning**.</span><span class="sxs-lookup"><span data-stu-id="173c7-122">After this upgrade is completed for a legal entity, the **Enable wave step codes** option is no longer available on the **Warehouse management parameters** page.</span></span>

<span data-ttu-id="173c7-123">Valideringar görs under uppgraderingen och om uppgraderingen misslyckas visas ett felmeddelande.</span><span class="sxs-lookup"><span data-stu-id="173c7-123">Validations are done during the upgrade, and if the upgrade fails, you receive an error message.</span></span> <span data-ttu-id="173c7-124">En uppgradering kan misslyckas på grund av följande konflikter:</span><span class="sxs-lookup"><span data-stu-id="173c7-124">An upgrade might fail because of the following conflicts:</span></span>

- <span data-ttu-id="173c7-125">Dubbla fritexter för påfyllnadssteg finns.</span><span class="sxs-lookup"><span data-stu-id="173c7-125">Duplicate wave step free texts exist.</span></span>
- <span data-ttu-id="173c7-126">Anpassningar finns.</span><span class="sxs-lookup"><span data-stu-id="173c7-126">Customizations exist.</span></span>
- <span data-ttu-id="173c7-127">En fritext för påfyllnadssteg som hör till en instans för påfyllnadsstegmetod matchar inte den förväntade malltypen.</span><span class="sxs-lookup"><span data-stu-id="173c7-127">A wave step free text that is associated with a wave step method instance doesn't match the expected template type.</span></span>

<span data-ttu-id="173c7-128">När du har löst alla konflikter som har identifierats under valideringen kan du köra uppgraderingsprocessen igen.</span><span class="sxs-lookup"><span data-stu-id="173c7-128">After you've resolved any conflicts that are identified during the validations, you can rerun the upgrade process.</span></span>

<span data-ttu-id="173c7-129">När uppgraderingen lyckas blir sidan **koder för påfyllnadssteg** (**Lagerstyrning \> Inställning \> Påfyllnad \> Koder för påfyllnadssteg**) tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="173c7-129">When the upgrade succeeds, the **Wave step codes** page (**Warehouse management \> Setup \> Waves \> Wave step codes**) becomes available.</span></span> <span data-ttu-id="173c7-130">På den här sidan visas de koder för påfyllnadssteg som uppgraderades när funktionen koder för påfyllnadssteg aktiverades.</span><span class="sxs-lookup"><span data-stu-id="173c7-130">This page lists the wave step codes that were upgraded when the wave step codes feature was turned on.</span></span>

### <a name="create-new-wave-step-codes"></a><span data-ttu-id="173c7-131">Skapa nya koder för påfyllnadssteg</span><span class="sxs-lookup"><span data-stu-id="173c7-131">Create new wave step codes</span></span>

<span data-ttu-id="173c7-132">Du kan använda sidan the **Koder för påfyllnadssteg** för att skapa och ta bort koder för påfyllnadssteg.</span><span class="sxs-lookup"><span data-stu-id="173c7-132">You can use the **Wave step codes** page to create and delete wave step codes.</span></span>

<span data-ttu-id="173c7-133">Varje ny kod för påfyllnadssteg och dess associerade ID måste vara unika för alla typer av påfyllnadssteg ch de måste definieras för en viss typ av påfyllnadssteg.</span><span class="sxs-lookup"><span data-stu-id="173c7-133">Every new wave step code and its associated ID must be unique across all wave step types, and they must be defined for a specific wave step type.</span></span>

### <a name="apply-wave-step-codes"></a><span data-ttu-id="173c7-134">Tillämpa koder för påfyllnadssteg</span><span class="sxs-lookup"><span data-stu-id="173c7-134">Apply wave step codes</span></span>

<span data-ttu-id="173c7-135">När du har definierat lämpliga koder för påfyllnadssteg kan de tillämpas på påfyllnadsprocessmetoderna.</span><span class="sxs-lookup"><span data-stu-id="173c7-135">After you've defined the appropriate wave step codes, they can be applied to the wave process methods.</span></span>

<span data-ttu-id="173c7-136">Om du vill använda koder för påfyllnadssteg går du till rätt målmall.</span><span class="sxs-lookup"><span data-stu-id="173c7-136">To apply wave step codes, go to the appropriate target template.</span></span> <span data-ttu-id="173c7-137">Nedan visas de målmallar som koder för påfyllnadssteg är avsedda att peka på:</span><span class="sxs-lookup"><span data-stu-id="173c7-137">Here are the target templates that the wave step codes are designated to point to:</span></span>

- <span data-ttu-id="173c7-138">**Mallar för lagerpåfyllnad:** Lagerstyrning \> Inställningar \> Lagerpåfyllnad \> Mallar för lagerpåfyllnad</span><span class="sxs-lookup"><span data-stu-id="173c7-138">**Replenishment templates:** Warehouse management \> Setup \> Replenishment \> Replenishment templates</span></span>
- <span data-ttu-id="173c7-139">**Lastuppbyggnadsmallar:** Lagerstyrning \> Inställningar \> Last \> Lastuppbyggnadsmallar</span><span class="sxs-lookup"><span data-stu-id="173c7-139">**Load build templates:** Warehouse management \> Setup \> Load \> Load build templates</span></span>
- <span data-ttu-id="173c7-140">**Sortera mallar:** Lagerstyrning \> Inställningar \> Förpackning \> Utgående sorteringsmallar</span><span class="sxs-lookup"><span data-stu-id="173c7-140">**Sort templates:** Warehouse management \> Setup \> Packing \> Outbound sorting templates</span></span>
- <span data-ttu-id="173c7-141">**Mallar för skapande av behållare:** Lagerstyrning \> Inställningar \> Behållare \> Mall för skapande av behållare.</span><span class="sxs-lookup"><span data-stu-id="173c7-141">**Containerization templates:** Warehouse management \> Setup \> Containers \> Container build templates</span></span>
- <span data-ttu-id="173c7-142">**Mallar för etikettutskrift:** Lagerstyrning \> Inställningar \> Dokumentflöde \> Mallar för påfyllnadsetikett</span><span class="sxs-lookup"><span data-stu-id="173c7-142">**Label printing templates:** Warehouse management \> Setup \> Document routing \> Wave label templates</span></span>

<span data-ttu-id="173c7-143">Mallarna i den här listan tillämpas när de refereras från en påfyllnadsprocessmetod som är vald i en påfyllnadsmall.</span><span class="sxs-lookup"><span data-stu-id="173c7-143">The templates in this list are applied when they are referenced from a wave process method that is selected in a wave template.</span></span> <span data-ttu-id="173c7-144">När påfyllnadsstegkoden i en påfyllnadsprocessmetod i en påfyllnadsmall matchar påfyllnadsstegkoden i en av malltyperna används mallen.</span><span class="sxs-lookup"><span data-stu-id="173c7-144">When the wave step code on a wave process method in a wave template matches the wave step code in one of the templates types, the template is applied.</span></span>

### <a name="sample-scenario"></a><span data-ttu-id="173c7-145">Exempelscenario</span><span class="sxs-lookup"><span data-stu-id="173c7-145">Sample scenario</span></span>

<span data-ttu-id="173c7-146">Följande procedur garanterar att den påfyllnadsmall som du har skapat kommer att användas för påfyllnadsmallen.</span><span class="sxs-lookup"><span data-stu-id="173c7-146">The following procedure helps guarantee that the replenishment template that you created will be applied for the wave template.</span></span>

1. <span data-ttu-id="173c7-147">Gå till **Lagerstyrning \> Inställningar \> Påfyllnad \> Koder för påfyllnadssteg** och skapa en kod för påfyllnadssteg för typen **Lagerpåfyllnad**.</span><span class="sxs-lookup"><span data-stu-id="173c7-147">Go to **Warehouse management \> Setup \> Waves \> Wave step codes**, and create a wave step code for the **Replenishment** type.</span></span>
2. <span data-ttu-id="173c7-148">Gå till **Lagerstyrning \> Inställningar \> Lagerpåfyllnad \> Mallar för lagerpåfyllnad** och skapa en mall för lagerpåfyllnad.</span><span class="sxs-lookup"><span data-stu-id="173c7-148">Go to **Warehouse management \> Setup \> Replenishment \> Replenishment templates**, and create a replenishment template.</span></span>
3. <span data-ttu-id="173c7-149">I mallen för lagerpåfyllnad väljer du koden för påfyllningssteg som du skapade för typen **Lagerpåfyllnad**.</span><span class="sxs-lookup"><span data-stu-id="173c7-149">In the replenishment template, select the wave step code that you created for the **Replenishment** type.</span></span>
4. <span data-ttu-id="173c7-150">Gå till **Lagerstyrning \> Inställningar \> Påfyllnader \> Påfyllnadsmallar** och välj den våg som du tänker använda.</span><span class="sxs-lookup"><span data-stu-id="173c7-150">Go to **Warehouse management \> Setup \> Waves \> Wave templates**, and select the wave template that you intend to use.</span></span>
5. <span data-ttu-id="173c7-151">I mallen, på snabbfliken **Metoder**, välj metoden **Lagerpåfyllnad**.</span><span class="sxs-lookup"><span data-stu-id="173c7-151">In the template, on the **Methods** FastTab, select the **Replenishment** method.</span></span>
6. <span data-ttu-id="173c7-152">I fältet **Kod för påfyllnadssteg**, välj koden för påfyllningssteg som du valde i lagerpåfyllnadsmallen.</span><span class="sxs-lookup"><span data-stu-id="173c7-152">In the **Wave step code** field, select the wave step code that you selected in the replenishment template.</span></span>
