---
title: Skapa en kanban-regel för fast kvantitet för tillverkning
description: Den här proceduren fokuserar på inställningarna som krävs för att skapa en fast kanban-regel för tillverkning som utlöser omvandlingsaktiviteter, i en arbetsgrupp, i en resurssnål miljö.
author: ChristianRytt
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KanbanRules, LeanProductionFlowActivityLookup, InventItemIdLookupSimple, UnitOfMeasureLookup, KanbanCreate
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: af912ecfb07a7af2f299e354243ba0d80c063a9e
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "4981316"
---
# <a name="create-a-fixed-quantity-kanban-rule-for-manufacturing"></a><span data-ttu-id="224a7-103">Skapa en kanban-regel för fast kvantitet för tillverkning</span><span class="sxs-lookup"><span data-stu-id="224a7-103">Create a fixed quantity kanban rule for manufacturing</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="224a7-104">Den här proceduren fokuserar på inställningarna som krävs för att skapa en fast kanban-regel för tillverkning som utlöser omvandlingsaktiviteter, i en arbetsgrupp, i en resurssnål miljö.</span><span class="sxs-lookup"><span data-stu-id="224a7-104">This procedure focuses on the setup needed to create a fixed manufacturing kanban rule for triggering transforming activities, at a work cell, in a lean environment.</span></span> <span data-ttu-id="224a7-105">Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF.</span><span class="sxs-lookup"><span data-stu-id="224a7-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="224a7-106">Den här proceduren är avsedd för processingenjören eller värdeströmansvarig när de förbereder tillverkningen av en ny eller ändrad produkt.</span><span class="sxs-lookup"><span data-stu-id="224a7-106">This procedure is intended for the Process Engineer or the Value Stream Manager, as they prepare production of a new or modified product.</span></span>


## <a name="create-new-kanban-rule"></a><span data-ttu-id="224a7-107">Skapa en ny kanban-regel</span><span class="sxs-lookup"><span data-stu-id="224a7-107">Create new kanban rule</span></span>
1. <span data-ttu-id="224a7-108">Gå till Kanban-regler.</span><span class="sxs-lookup"><span data-stu-id="224a7-108">Go to Kanban rules.</span></span>
2. <span data-ttu-id="224a7-109">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="224a7-109">Click New.</span></span>
    * <span data-ttu-id="224a7-110">Observera att standardtypen för strategin Tillverkning och återanskaffning är Fast.</span><span class="sxs-lookup"><span data-stu-id="224a7-110">Notice that the default Type is Manufacturing and Replenishment strategy is Fixed.</span></span> <span data-ttu-id="224a7-111">Du behöver inte ändra dessa parametrar.</span><span class="sxs-lookup"><span data-stu-id="224a7-111">You do not have to change these parameters.</span></span>  
3. <span data-ttu-id="224a7-112">Ange eller välj ett värde i fältet Första planaktivitet.</span><span class="sxs-lookup"><span data-stu-id="224a7-112">In the First plan activity field, enter or select a value.</span></span>
    * <span data-ttu-id="224a7-113">Detta är den aktivitet som ska utföras för kanban som baseras på den här kanban-regeln.</span><span class="sxs-lookup"><span data-stu-id="224a7-113">This is the activity that will be performed for kanbans created based on this kanban rule.</span></span>  <span data-ttu-id="224a7-114">Välj ”SpeakerTestAndPackaging”.</span><span class="sxs-lookup"><span data-stu-id="224a7-114">Select 'SpeakerTestAndPackaging'.</span></span>  
4. <span data-ttu-id="224a7-115">Expandera avsnittet Detaljer.</span><span class="sxs-lookup"><span data-stu-id="224a7-115">Expand the Details section.</span></span>
5. <span data-ttu-id="224a7-116">Ange eller välj ett värde i fältet Produkt.</span><span class="sxs-lookup"><span data-stu-id="224a7-116">In the Product field, enter or select a value.</span></span>
    * <span data-ttu-id="224a7-117">Välj L0050.</span><span class="sxs-lookup"><span data-stu-id="224a7-117">Select L0050.</span></span>  
6. <span data-ttu-id="224a7-118">Ange eller välj ett värde i fältet Måttenhet.</span><span class="sxs-lookup"><span data-stu-id="224a7-118">In the Unit of measure field, enter or select a value.</span></span>
    * <span data-ttu-id="224a7-119">Välj minuter.</span><span class="sxs-lookup"><span data-stu-id="224a7-119">Select minutes.</span></span>  
7. <span data-ttu-id="224a7-120">Ange ett värde i fältet Produktionstid.</span><span class="sxs-lookup"><span data-stu-id="224a7-120">In the Lead time field, enter a number.</span></span>
    * <span data-ttu-id="224a7-121">Ange 5.</span><span class="sxs-lookup"><span data-stu-id="224a7-121">Enter 5.</span></span>  

## <a name="set-quantities"></a><span data-ttu-id="224a7-122">Ställ in kvantiteter</span><span class="sxs-lookup"><span data-stu-id="224a7-122">Set quantities</span></span>
1. <span data-ttu-id="224a7-123">Expandera avsnittet Kvantiteter.</span><span class="sxs-lookup"><span data-stu-id="224a7-123">Expand the Quantities section.</span></span>
2. <span data-ttu-id="224a7-124">Ange standardkvantiteten till "10".</span><span class="sxs-lookup"><span data-stu-id="224a7-124">Set Default quantity to '10'.</span></span>
    * <span data-ttu-id="224a7-125">Detta är kvantiteten som ska överföras för varje kanban.</span><span class="sxs-lookup"><span data-stu-id="224a7-125">This is the quantity that will be transferred for each kanban.</span></span>  
3. <span data-ttu-id="224a7-126">Markera kryssrutan Produktkvantitetsavvikelse.</span><span class="sxs-lookup"><span data-stu-id="224a7-126">Select the Product quantity variance check box.</span></span>
    * <span data-ttu-id="224a7-127">Med detta kan vald kanban slutföras med en avvikelse från standardkvantiteten.</span><span class="sxs-lookup"><span data-stu-id="224a7-127">With this, selected kanbans can be completed with a variance from the default quantity.</span></span>  <span data-ttu-id="224a7-128">Ange båda avvikelserna till 2 om du vill tillåta att kanban slutförs med en kvantitet från 8 till 12.</span><span class="sxs-lookup"><span data-stu-id="224a7-128">To allow kanbans to be completed with a quantity from 8 to 12, set both variances to 2.</span></span>  
4. <span data-ttu-id="224a7-129">Ange Avvikelse nedan till "2 ".</span><span class="sxs-lookup"><span data-stu-id="224a7-129">Set Variance below to '2'.</span></span>
    * <span data-ttu-id="224a7-130">Detta tillåter att den slutförs ned till 10 - 2 = 8</span><span class="sxs-lookup"><span data-stu-id="224a7-130">This will allow completing down to 10 - 2 = 8</span></span>  
5. <span data-ttu-id="224a7-131">Ange Avvikelse ovan till "2 ".</span><span class="sxs-lookup"><span data-stu-id="224a7-131">Set Variance above to '2'.</span></span>
    * <span data-ttu-id="224a7-132">Detta tillåter att den slutförs upp till 10 + 2 = 12</span><span class="sxs-lookup"><span data-stu-id="224a7-132">This will allow completing up to 10 + 2 = 12</span></span>  
6. <span data-ttu-id="224a7-133">Ange ett nummer i fältet Fast kanban-kvantitet.</span><span class="sxs-lookup"><span data-stu-id="224a7-133">In the Fixed kanban quantity field, enter a number.</span></span>
    * <span data-ttu-id="224a7-134">Detta är antalet kanban som ska vara aktiva.</span><span class="sxs-lookup"><span data-stu-id="224a7-134">This is the amount of kanbans that should be active.</span></span> <span data-ttu-id="224a7-135">I det här fallet 5 kanbans som bearbetar 10 var.</span><span class="sxs-lookup"><span data-stu-id="224a7-135">In this case, 5 kanbans processing 10 each.</span></span>  
7. <span data-ttu-id="224a7-136">Ange "2" i fältet Notifieringsgränsminimum.</span><span class="sxs-lookup"><span data-stu-id="224a7-136">In the Alert boundary minimum field, enter '2'.</span></span>
    * <span data-ttu-id="224a7-137">Används för att hålla reda på den minsta mängd fullständiga kanbans som ska finnas på destinationen.</span><span class="sxs-lookup"><span data-stu-id="224a7-137">Used to keep track of the minimum amount of full kanbans that should be at the destination.</span></span> <span data-ttu-id="224a7-138">Detta används till exempel i översikten över kanban-kvantitet.</span><span class="sxs-lookup"><span data-stu-id="224a7-138">For example, this is used on the kanban quantity overview.</span></span>  
8. <span data-ttu-id="224a7-139">Ange "4" i fältet Notifieringsgränsmaximum.</span><span class="sxs-lookup"><span data-stu-id="224a7-139">In the Alert boundary maximum field, enter '4'.</span></span>
    * <span data-ttu-id="224a7-140">Används för att hålla reda på den största mängd fullständiga kanbans som ska finnas på destinationen.</span><span class="sxs-lookup"><span data-stu-id="224a7-140">Used to keep track of the maximum amount of full kanbans that should be at the destination.</span></span> <span data-ttu-id="224a7-141">Detta används till exempel i översikten över kanban-kvantitet.</span><span class="sxs-lookup"><span data-stu-id="224a7-141">For example, this is used on the kanban quantity overview.</span></span>  
9. <span data-ttu-id="224a7-142">Ange "1" i fältet Automatisk planeringskvantitet.</span><span class="sxs-lookup"><span data-stu-id="224a7-142">In the Automatic planning quantity field, enter '1'.</span></span>
    * <span data-ttu-id="224a7-143">När du anger detta till 1 innebär det att varje kanban planeras automatiskt.</span><span class="sxs-lookup"><span data-stu-id="224a7-143">Setting this to 1 means that every kanban will be automatically planned.</span></span>   <span data-ttu-id="224a7-144">Om du anger 3 planeras inte kanbans förrän 3 tomma kanbans är redo för planering.</span><span class="sxs-lookup"><span data-stu-id="224a7-144">If we entered 3, the kanbans would not be planned until 3 empty kanbans are ready for planning.</span></span> <span data-ttu-id="224a7-145">Detta kan användas för att gruppera arbete och undvika för många inställningar.</span><span class="sxs-lookup"><span data-stu-id="224a7-145">This is useful for grouping work and avoiding too much setup.</span></span>  

## <a name="create-kanbans"></a><span data-ttu-id="224a7-146">Skapa kanbans</span><span class="sxs-lookup"><span data-stu-id="224a7-146">Create Kanbans</span></span>
1. <span data-ttu-id="224a7-147">Expandera avsnittet Kanbans.</span><span class="sxs-lookup"><span data-stu-id="224a7-147">Expand the Kanbans section.</span></span>
2. <span data-ttu-id="224a7-148">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="224a7-148">Click Save.</span></span>
    * <span data-ttu-id="224a7-149">Kanban-regeln måste sparas innan kanbans kan skapas.</span><span class="sxs-lookup"><span data-stu-id="224a7-149">The kanban rule needs to be saved before kanbans can be created.</span></span>  
3. <span data-ttu-id="224a7-150">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="224a7-150">Click Add.</span></span>
    * <span data-ttu-id="224a7-151">Lägg märke till att det inte finns några aktiva kanbans, därför är det föreslagna antalet nya kanban 5.</span><span class="sxs-lookup"><span data-stu-id="224a7-151">Note that there are no active kanbans, due to this the suggested 'Number of new kanbans' are 5.</span></span> <span data-ttu-id="224a7-152">Detta är lika med den fasta kanban-kvantiteten.</span><span class="sxs-lookup"><span data-stu-id="224a7-152">This is equal to the 'Fixed kanban quantity'.</span></span>  
4. <span data-ttu-id="224a7-153">Klicka på Skapa.</span><span class="sxs-lookup"><span data-stu-id="224a7-153">Click Create.</span></span>
    * <span data-ttu-id="224a7-154">Detta skapar 5 kanbans.</span><span class="sxs-lookup"><span data-stu-id="224a7-154">This will create 5 kanbans.</span></span>  
    * <span data-ttu-id="224a7-155">Observera att 5 kanbans, för 10 vardera, skapades för den här kanban-regeln för tillverkning.</span><span class="sxs-lookup"><span data-stu-id="224a7-155">Note that 5 kanbans, for 10 each, was created for this manufacturing kanban rule.</span></span> <span data-ttu-id="224a7-156">Detta är det sista steget i den här proceduren.</span><span class="sxs-lookup"><span data-stu-id="224a7-156">This is the last step in this procedure.</span></span>  

