---
title: Ställ in en arbetsmall för inköpsorder
description: I det här avsnittet beskrivs hur du ställer in en enkel arbetsmall som ska användas när mottagna artiklar inlagras.
author: ShylaThompson
manager: tfehr
ms.date: 08/08/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSWorkTemplateTable, SysQueryForm
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e9acf6db9138a009527c6662f1cbb7e5fedc8778
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "4976873"
---
# <a name="set-up-a-work-template-for-purchase-orders"></a><span data-ttu-id="15e3c-103">Ställ in en arbetsmall för inköpsorder</span><span class="sxs-lookup"><span data-stu-id="15e3c-103">Set up a work template for purchase orders</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="15e3c-104">I det här avsnittet beskrivs hur du ställer in en enkel arbetsmall som ska användas när mottagna artiklar inlagras.</span><span class="sxs-lookup"><span data-stu-id="15e3c-104">This topic describes how to set up a simple work template to be used when putting away received items.</span></span> <span data-ttu-id="15e3c-105">Arbetsmallar bestämmer instruktionsuppsättning som visas för lagerställearbetaren på en mobil enhet när artiklar flyttas från inleveransområdet.</span><span class="sxs-lookup"><span data-stu-id="15e3c-105">Work templates determine the set of instructions presented to the warehouse worker on a mobile device when moving items from the receiving area.</span></span> <span data-ttu-id="15e3c-106">Du kan använda den här proceduren med uppgifterna i demonstrationsföretaget USMF.</span><span class="sxs-lookup"><span data-stu-id="15e3c-106">You can use this procedure with the data mentioned in demo data company USMF.</span></span> <span data-ttu-id="15e3c-107">Innan du startar guiden skapar du ett arbetspool-id.</span><span class="sxs-lookup"><span data-stu-id="15e3c-107">Before you start this guide, create a work pool ID.</span></span> <span data-ttu-id="15e3c-108">I det här exemplet används arbetspool-id:t Inkommande.</span><span class="sxs-lookup"><span data-stu-id="15e3c-108">In this example, a work pool ID called in Inbound is used.</span></span> <span data-ttu-id="15e3c-109">Den här proceduren är avsedd för lagerchefen.</span><span class="sxs-lookup"><span data-stu-id="15e3c-109">This procedure is intended for the warehouse manager.</span></span>

1. <span data-ttu-id="15e3c-110">I navigeringsfönstret, gå till **Moduler > Lagerstyrning > Inställningar > Arbete > Arbetsmallar**.</span><span class="sxs-lookup"><span data-stu-id="15e3c-110">In the navigation pane, go to **Modules > Warehouse management > Setup > Work > Work templates**.</span></span>
2. <span data-ttu-id="15e3c-111">Välj **Inköpsorder** i fältet **Typ av arbetsorder**.</span><span class="sxs-lookup"><span data-stu-id="15e3c-111">In the **Work order type** field, select **Purchase orders**.</span></span>

## <a name="create-a-work-template-header"></a><span data-ttu-id="15e3c-112">Skapa ett arbetsmallshuvud</span><span class="sxs-lookup"><span data-stu-id="15e3c-112">Create a work template header</span></span>
1. <span data-ttu-id="15e3c-113">Välj **Ny**.</span><span class="sxs-lookup"><span data-stu-id="15e3c-113">Select **New**.</span></span>
2. <span data-ttu-id="15e3c-114">Ange ett nummer i fältet **Sekvensnummer**.</span><span class="sxs-lookup"><span data-stu-id="15e3c-114">In the **Sequence number** field, enter a number.</span></span> <span data-ttu-id="15e3c-115">I den här sekvensen utvärderas arbetsmallen.</span><span class="sxs-lookup"><span data-stu-id="15e3c-115">This is the sequence in which the work templates are evaluated.</span></span> <span data-ttu-id="15e3c-116">Du kan ändra sekvensen vid behov.</span><span class="sxs-lookup"><span data-stu-id="15e3c-116">You can modify the sequence, if needed.</span></span>  
3. <span data-ttu-id="15e3c-117">Skriv ett värde i fältet **Arbetsmall.**</span><span class="sxs-lookup"><span data-stu-id="15e3c-117">In the **Work template** field, type a value.</span></span> <span data-ttu-id="15e3c-118">Detta är den unika identifieraren för mallen.</span><span class="sxs-lookup"><span data-stu-id="15e3c-118">This is the unique identifier for this template.</span></span>  
4. <span data-ttu-id="15e3c-119">Skriv ett värde i fältet **Beskrivning av arbetsmall.**</span><span class="sxs-lookup"><span data-stu-id="15e3c-119">In the **Work template description** field, type a value.</span></span>
    - <span data-ttu-id="15e3c-120">Alternativet **Giltig** markeras inte förrän du har fyllt i all information som krävs av mallen och valt **Spara**.</span><span class="sxs-lookup"><span data-stu-id="15e3c-120">The **Valid** option will not be checked until you've completed all the information that's needed by the template and have then selected **Save**.</span></span>  
    - <span data-ttu-id="15e3c-121">En arbetsorder av typen **Inköpsorder** kan inte bearbetas automatiskt, så lämna alternativet **Bearbeta automatiskt** med värdet **Nej**.</span><span class="sxs-lookup"><span data-stu-id="15e3c-121">A work order of type **Purchase order** cannot be automatically processed, so leave the **Automatically process** option set to **No**.</span></span>  
5. <span data-ttu-id="15e3c-122">Skriv ett värde i fältet **ID för arbetspool.**</span><span class="sxs-lookup"><span data-stu-id="15e3c-122">In the **Work pool ID** field, type a value.</span></span> <span data-ttu-id="15e3c-123">Id:n för arbetspooler gör att du kan strukturera arbetsuppgifter i grupper.</span><span class="sxs-lookup"><span data-stu-id="15e3c-123">Work pool IDs allow you to organize work into groups.</span></span> <span data-ttu-id="15e3c-124">Det värde som du som anges här är det förvalda värdet för alla arbetsuppgifter som skapas med den här mallen.</span><span class="sxs-lookup"><span data-stu-id="15e3c-124">The value that you set here will be the default value for any work that's created using this template.</span></span>  
6. <span data-ttu-id="15e3c-125">Ange `1` i fältet **Arbetsprioritet**.</span><span class="sxs-lookup"><span data-stu-id="15e3c-125">In the **Work priority** field, enter `1`.</span></span> <span data-ttu-id="15e3c-126">Detta indikerar värdet för arbetsuppgiften och värdet du anger här är standardinställningen för alla arbetsuppgifter som skapas med hjälp av den här mallen.</span><span class="sxs-lookup"><span data-stu-id="15e3c-126">This indicates the importance of the work, and the value that you set here will be the default for any work created using this template.</span></span>  
7. <span data-ttu-id="15e3c-127">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="15e3c-127">Select **Save**.</span></span> <span data-ttu-id="15e3c-128">Du måste spara arbetsmallhuvudet för att knappen **Redigera fråga** ska bli tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="15e3c-128">You must save the work template header before the **Edit Query** button becomes available.</span></span>  

## <a name="set-up-the-query-for-the-work-template"></a><span data-ttu-id="15e3c-129">Ställa in frågan för arbetsmallen</span><span class="sxs-lookup"><span data-stu-id="15e3c-129">Set up the query for the work template</span></span>
1. <span data-ttu-id="15e3c-130">Välj **Redigera fråga**.</span><span class="sxs-lookup"><span data-stu-id="15e3c-130">Select **Edit query**.</span></span> <span data-ttu-id="15e3c-131">Vi anger en begränsning som innebär att mallen bara kan användas på ett specifikt lagerställe.</span><span class="sxs-lookup"><span data-stu-id="15e3c-131">We'll set a limitation that the template can only be used within a specific warehouse.</span></span>  
2. <span data-ttu-id="15e3c-132">Markera **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="15e3c-132">Select **Add**.</span></span>
3. <span data-ttu-id="15e3c-133">I fältet **Fält** för den nya raden, ange `warehouse`.</span><span class="sxs-lookup"><span data-stu-id="15e3c-133">In the **Field** field of the new row, type `warehouse`.</span></span>
4. <span data-ttu-id="15e3c-134">I fältet **Kriterier** skriver du ett värde.</span><span class="sxs-lookup"><span data-stu-id="15e3c-134">In the **Criteria** field, type a value.</span></span>
5. <span data-ttu-id="15e3c-135">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="15e3c-135">Select **OK**.</span></span>
6. <span data-ttu-id="15e3c-136">Välj **Ja**.</span><span class="sxs-lookup"><span data-stu-id="15e3c-136">Select **Yes**.</span></span>

## <a name="set-work-template-details"></a><span data-ttu-id="15e3c-137">Ställa in arbetsmallinformation</span><span class="sxs-lookup"><span data-stu-id="15e3c-137">Set work template details</span></span>
1. <span data-ttu-id="15e3c-138">Välj **Ny**.</span><span class="sxs-lookup"><span data-stu-id="15e3c-138">Select **New**.</span></span>
2. <span data-ttu-id="15e3c-139">I fältet **Arbetstyp**, välj **Välj**.</span><span class="sxs-lookup"><span data-stu-id="15e3c-139">In the **Work type** field, select **Pick**.</span></span>
3. <span data-ttu-id="15e3c-140">I fältet **Arbetsklass-ID**, skriv `purchase`.</span><span class="sxs-lookup"><span data-stu-id="15e3c-140">In the **Work class ID** field, type `purchase`.</span></span> <span data-ttu-id="15e3c-141">Arbetsklassen att du som anges här är standardinställningen i alla arbetsrader av typen Välj som skapas med den här mallen.</span><span class="sxs-lookup"><span data-stu-id="15e3c-141">The work class that you set here will be the default on all work lines of type Pick that are created using this template.</span></span> <span data-ttu-id="15e3c-142">Arbetsklassen kan inte ersättas av arbetsorderraderna.</span><span class="sxs-lookup"><span data-stu-id="15e3c-142">The work class cannot be overridden from the work order lines.</span></span> <span data-ttu-id="15e3c-143">Arbetsklasser används för att begränsa och/eller styra typen arbetsorderrader som en lagerställemedarbetare kan behandla på en mobil enhet.</span><span class="sxs-lookup"><span data-stu-id="15e3c-143">Work classes are used to direct and/or limit the type of work order lines a warehouse worker can process on a mobile device.</span></span>  
4. <span data-ttu-id="15e3c-144">Välj **Ny**.</span><span class="sxs-lookup"><span data-stu-id="15e3c-144">Select **New**.</span></span>
5. <span data-ttu-id="15e3c-145">Välj **Placera** i fältet **Arbetstyp**.</span><span class="sxs-lookup"><span data-stu-id="15e3c-145">In the **Work type** field, select **Put**.</span></span>
6. <span data-ttu-id="15e3c-146">Ange ett värde i fältet **Arbetsklass-ID**.</span><span class="sxs-lookup"><span data-stu-id="15e3c-146">In the **Work class ID** field, type a value.</span></span> <span data-ttu-id="15e3c-147">Instruktionerna för plock och plats är en uppsättning.</span><span class="sxs-lookup"><span data-stu-id="15e3c-147">The pick and put instructions are a set.</span></span> <span data-ttu-id="15e3c-148">Varje plock/platsuppsättning måste ha samma arbetsklass.</span><span class="sxs-lookup"><span data-stu-id="15e3c-148">Each pick/put set must have the same work class.</span></span> <span data-ttu-id="15e3c-149">Använda samma arbetsklass som du gjorde i plockinstruktionen.</span><span class="sxs-lookup"><span data-stu-id="15e3c-149">Use the same work class that you provided for the pick instruction.</span></span>  
7. <span data-ttu-id="15e3c-150">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="15e3c-150">Select **Save**.</span></span> <span data-ttu-id="15e3c-151">Observera att kryssrutan **Giltig** nu är markerad.</span><span class="sxs-lookup"><span data-stu-id="15e3c-151">Note that the **Valid** checkbox is now checked.</span></span>  

