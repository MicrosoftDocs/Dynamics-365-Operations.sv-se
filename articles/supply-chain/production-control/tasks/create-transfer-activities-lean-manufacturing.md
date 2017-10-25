--- 
title: "Skapa överföringsaktiviteter för lean manufacturing"
description: "Skapa en överföringsaktivitet för lean manufacturing."
author: cvocph
manager: AnnBe
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: conradv
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: 010ac08fa96ead49b6ecbbe083e59fb96427e29e
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---
# <a name="create-transfer-activities-for-lean-manufacturing"></a><span data-ttu-id="f927c-103">Skapa överföringsaktiviteter för lean manufacturing</span><span class="sxs-lookup"><span data-stu-id="f927c-103">Create transfer activities for lean manufacturing</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="f927c-104">Skapa en överföringsaktivitet för lean manufacturing.</span><span class="sxs-lookup"><span data-stu-id="f927c-104">Create a transfer activity for lean manufacturing.</span></span> 

<span data-ttu-id="f927c-105">Förutsättningar:</span><span class="sxs-lookup"><span data-stu-id="f927c-105">Prerequisites:</span></span> 

1. <span data-ttu-id="f927c-106">Ett produktionsflöde och en version som inte är aktiv måste skapas.</span><span class="sxs-lookup"><span data-stu-id="f927c-106">A production flow and version that is not active must be created.</span></span>

2. <span data-ttu-id="f927c-107">Från- och till-lagerställe och -platser måste skapas.</span><span class="sxs-lookup"><span data-stu-id="f927c-107">The from and to warehouse and locations must be created.</span></span> <span data-ttu-id="f927c-108">Den påfyllande eller påfyllda arbetsgruppen bör skapas (valfritt).</span><span class="sxs-lookup"><span data-stu-id="f927c-108">Optionally, the replenishing or the replenished work cell should be created.</span></span>


## <a name="find-the-production-flow-version"></a><span data-ttu-id="f927c-109">Hitta produktionsflödesversionen</span><span class="sxs-lookup"><span data-stu-id="f927c-109">Find the production flow version</span></span>
1. <span data-ttu-id="f927c-110">Gå till Produktionskontroll > Inställningar > Lean-produktionsflöde > Produktionsflöden.</span><span class="sxs-lookup"><span data-stu-id="f927c-110">Go to Production control > Setup > Lean production flow > Production flows.</span></span>
2. <span data-ttu-id="f927c-111">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="f927c-111">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="f927c-112">Observera att produktionsflödet måste ha en version med utkaststatus.</span><span class="sxs-lookup"><span data-stu-id="f927c-112">Note that the production flow must have a version in draft status.</span></span>  
3. <span data-ttu-id="f927c-113">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="f927c-113">In the list, click the link in the selected row.</span></span>

## <a name="create-a-new-activity"></a><span data-ttu-id="f927c-114">Skapa en ny aktivitet</span><span class="sxs-lookup"><span data-stu-id="f927c-114">Create a new activity</span></span>
1. <span data-ttu-id="f927c-115">Klicka på Aktiviteter.</span><span class="sxs-lookup"><span data-stu-id="f927c-115">Click Activities.</span></span>
    * <span data-ttu-id="f927c-116">Kontrollera att det valda produktionsflödet har en version i utkast och välj den version.</span><span class="sxs-lookup"><span data-stu-id="f927c-116">Ensure that the selected production flow has a version in draft and select that version.</span></span>  
2. <span data-ttu-id="f927c-117">Klicka på Skapa en ny planaktivitet.</span><span class="sxs-lookup"><span data-stu-id="f927c-117">Click Create new plan activity.</span></span>
3. <span data-ttu-id="f927c-118">Klicka på Nästa.</span><span class="sxs-lookup"><span data-stu-id="f927c-118">Click Next.</span></span>
4. <span data-ttu-id="f927c-119">Skriv ett värde i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="f927c-119">In the Name field, type a value.</span></span>
5. <span data-ttu-id="f927c-120">I fältet Aktivitetstyp väljer du Överföring.</span><span class="sxs-lookup"><span data-stu-id="f927c-120">In the Activity type field, select 'Transfer'.</span></span>
6. <span data-ttu-id="f927c-121">Ange ett nummer i fältet Processkvantitet.</span><span class="sxs-lookup"><span data-stu-id="f927c-121">In the Process quantity field, enter a number.</span></span>
7. <span data-ttu-id="f927c-122">Klicka på Nästa.</span><span class="sxs-lookup"><span data-stu-id="f927c-122">Click Next.</span></span>

## <a name="select-the-work-cells"></a><span data-ttu-id="f927c-123">Välj arbetsgrupperna</span><span class="sxs-lookup"><span data-stu-id="f927c-123">Select the Work cells</span></span>
1. <span data-ttu-id="f927c-124">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Fyller på.</span><span class="sxs-lookup"><span data-stu-id="f927c-124">In the Replenishing field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="f927c-125">Välj en arbetsgrupp om du vill använda utleveransplatsen för arbetsgruppen som "från"-platsen i överföringsaktiviteten.</span><span class="sxs-lookup"><span data-stu-id="f927c-125">To use the work cell output location as the from location in the transfer activity, select a work cell.</span></span> <span data-ttu-id="f927c-126">Detsamma kan göras med den påfyllda arbetsgruppen, som anger destinationsplatsen för överföringsaktiviteten.</span><span class="sxs-lookup"><span data-stu-id="f927c-126">The same can be done with the replenished work cell, which sets the target location of the transfer activity.</span></span>  
2. <span data-ttu-id="f927c-127">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="f927c-127">In the list, click the link in the selected row.</span></span>

## <a name="define-the-inventory-updates"></a><span data-ttu-id="f927c-128">Definiera lageruppdateringarna</span><span class="sxs-lookup"><span data-stu-id="f927c-128">Define the inventory updates</span></span>
1. <span data-ttu-id="f927c-129">Välj ett alternativ i fältet Produkttyp.</span><span class="sxs-lookup"><span data-stu-id="f927c-129">In the Product type field, select an option.</span></span>
    * <span data-ttu-id="f927c-130">Observera att en överföring inte ändrar typen av produkt.</span><span class="sxs-lookup"><span data-stu-id="f927c-130">Note that a transfer does not change the type of product.</span></span> <span data-ttu-id="f927c-131">Du kan överföra färdiga produkter eller halvfärdiga produkter (överföring mellan två aktiviteter av ett produktionsflöde och eventuellt ett kanban-flöde).</span><span class="sxs-lookup"><span data-stu-id="f927c-131">You can transfer finished products or semi-finished products (transfer between two activities of a production flow and possibly a kanban flow).</span></span>     <span data-ttu-id="f927c-132">När du överför färdiga produkter kan du välja om du plockar eller tar emot resultat i en lagertransaktion.</span><span class="sxs-lookup"><span data-stu-id="f927c-132">When transferring finished products, you can select if picking or receiving results in an inventory transaction.</span></span>  

## <a name="define-the-transfer-locations"></a><span data-ttu-id="f927c-133">Definiera överföringsplatserna</span><span class="sxs-lookup"><span data-stu-id="f927c-133">Define the transfer locations</span></span>
1. <span data-ttu-id="f927c-134">Klicka på Nästa.</span><span class="sxs-lookup"><span data-stu-id="f927c-134">Click Next.</span></span>
2. <span data-ttu-id="f927c-135">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Lagerställe.</span><span class="sxs-lookup"><span data-stu-id="f927c-135">In the Warehouse field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="f927c-136">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="f927c-136">In the list, find and select the desired record.</span></span>
4. <span data-ttu-id="f927c-137">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="f927c-137">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="f927c-138">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Plats.</span><span class="sxs-lookup"><span data-stu-id="f927c-138">In the Location field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="f927c-139">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="f927c-139">In the list, click the link in the selected row.</span></span>
7. <span data-ttu-id="f927c-140">Välj Speditör” i fältet Fraktad av.</span><span class="sxs-lookup"><span data-stu-id="f927c-140">In the Freighted by field, select 'Shipper'.</span></span>
    * <span data-ttu-id="f927c-141">Alternativen inkluderar: Speditör – organisationen som driver speditionslagret, Mottagare – organisationen som driver inleveranslagret, Transportföretag: – en tredjepartsleverantör.</span><span class="sxs-lookup"><span data-stu-id="f927c-141">Options include: Shipper - the organization operating the shipping warehouse, Recipient -  the organization operating the receiving warehouse, Carrier - a third party vendor.</span></span> <span data-ttu-id="f927c-142">Om organisationen är en leverantör kräver överföringsaktiviteten ett legotillverkningsavtal.</span><span class="sxs-lookup"><span data-stu-id="f927c-142">If the operating organization is a vendor, the transfer activity requires a subcontracting agreement.</span></span>  
8. <span data-ttu-id="f927c-143">Klicka på Nästa.</span><span class="sxs-lookup"><span data-stu-id="f927c-143">Click Next.</span></span>

## <a name="define-the-activity-times"></a><span data-ttu-id="f927c-144">Definiera aktivitetstiderna</span><span class="sxs-lookup"><span data-stu-id="f927c-144">Define the activity times</span></span>
1. <span data-ttu-id="f927c-145">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="f927c-145">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="f927c-146">Definitionen av en körning krävs.</span><span class="sxs-lookup"><span data-stu-id="f927c-146">The definition of a Runtime is required.</span></span> <span data-ttu-id="f927c-147">Körningen används för att beräkna kostnaden och genomflödetiderna för kanban-jobben.</span><span class="sxs-lookup"><span data-stu-id="f927c-147">The Runtime is used to calculate cost and the throughput times of the kanban jobs.</span></span> <span data-ttu-id="f927c-148">Körningar används inte för att beräkna kapacitetsbeläggning och förbrukning, vilket beräknas med cykeltider, som hämtas från uppgiften för produktionsflödesversion.</span><span class="sxs-lookup"><span data-stu-id="f927c-148">Runtimes are not used to calculate capacity load and consumption, which is calculated by cycle time, derived from the production flow version task.</span></span>  
2. <span data-ttu-id="f927c-149">Ange ett värde i fältet Tid.</span><span class="sxs-lookup"><span data-stu-id="f927c-149">In the Time field, enter a number.</span></span>
3. <span data-ttu-id="f927c-150">Skriv ett värde i fältet Enhet.</span><span class="sxs-lookup"><span data-stu-id="f927c-150">In the Unit field, type a value.</span></span>
4. <span data-ttu-id="f927c-151">Välj tidsenhet.</span><span class="sxs-lookup"><span data-stu-id="f927c-151">Select the Time unit.</span></span>
5. <span data-ttu-id="f927c-152">Ange ett värde i fältet Per kvantitet.</span><span class="sxs-lookup"><span data-stu-id="f927c-152">In the Per quantity field, enter a number.</span></span>
6. <span data-ttu-id="f927c-153">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="f927c-153">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="f927c-154">Kötider är valfria.</span><span class="sxs-lookup"><span data-stu-id="f927c-154">Queue times are optional.</span></span>  
7. <span data-ttu-id="f927c-155">Ange ett värde i fältet Tid.</span><span class="sxs-lookup"><span data-stu-id="f927c-155">In the Time field, enter a number.</span></span>
8. <span data-ttu-id="f927c-156">Skriv ett värde i fältet Enhet.</span><span class="sxs-lookup"><span data-stu-id="f927c-156">In the Unit field, type a value.</span></span>
9. <span data-ttu-id="f927c-157">Välj tidsenhet.</span><span class="sxs-lookup"><span data-stu-id="f927c-157">Select the Time unit.</span></span>
10. <span data-ttu-id="f927c-158">Ange ett värde i fältet Per kvantitet.</span><span class="sxs-lookup"><span data-stu-id="f927c-158">In the Per quantity field, enter a number.</span></span>
11. <span data-ttu-id="f927c-159">Klicka på Nästa.</span><span class="sxs-lookup"><span data-stu-id="f927c-159">Click Next.</span></span>
12. <span data-ttu-id="f927c-160">Klicka på Avsluta.</span><span class="sxs-lookup"><span data-stu-id="f927c-160">Click Finish.</span></span>
13. <span data-ttu-id="f927c-161">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="f927c-161">Close the page.</span></span>

