--- 
title: "Ställ in ett menyalternativ för mobil enhet för att slutföra arbetet i en inköpsorder"
description: "I den här proceduren visas hur du ställer in ett menyalternativet för mobila enheter."
author: BibiSp
manager: AnnBe
ms.date: 08/25/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: bis
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 37010003ad638e068ed7650532da29c6dbc033cb
ms.contentlocale: sv-se
ms.lasthandoff: 04/13/2018

---
# <a name="set-up-a-mobile-device-menu-item-for-completing-work-in-a-purchase-order"></a><span data-ttu-id="ee6c4-103">Ställ in ett menyalternativ för mobil enhet för att slutföra arbetet i en inköpsorder</span><span class="sxs-lookup"><span data-stu-id="ee6c4-103">Set up a mobile device menu item for completing work in a purchase order</span></span>

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="ee6c4-104">I den här proceduren visas hur du ställer in ett menyalternativet för mobila enheter.</span><span class="sxs-lookup"><span data-stu-id="ee6c4-104">This procedure shows how to set up a Mobile device menu item.</span></span> <span data-ttu-id="ee6c4-105">I det här exemplet används menyalternativet för att utföra arbete av typen Inköpsorder.</span><span class="sxs-lookup"><span data-stu-id="ee6c4-105">In this example, the menu item is used for performing work of type Purchase order.</span></span> <span data-ttu-id="ee6c4-106">Arbetsklassen som associeras med menyalternativet bestämmer vilket arbete som är giltigt.</span><span class="sxs-lookup"><span data-stu-id="ee6c4-106">The work class that’s associated with the menu item determines which work is valid.</span></span> <span data-ttu-id="ee6c4-107">Du kan använda den här guiden i demonstrationsföretaget USMF.</span><span class="sxs-lookup"><span data-stu-id="ee6c4-107">You can use this guide in demo data company USMF.</span></span> <span data-ttu-id="ee6c4-108">Vanligtvis utförs den här proceduren av en lagerchef.</span><span class="sxs-lookup"><span data-stu-id="ee6c4-108">This procedure is typically carried out by a warehouse manager.</span></span>


## <a name="create-a-mobile-device-menu-item"></a><span data-ttu-id="ee6c4-109">Skapa ett menykommando för mobila enheter</span><span class="sxs-lookup"><span data-stu-id="ee6c4-109">Create a mobile device menu item</span></span>
1. <span data-ttu-id="ee6c4-110">Gå till Menyalternativ på mobil enhet.</span><span class="sxs-lookup"><span data-stu-id="ee6c4-110">Go to Mobile device menu items.</span></span>
2. <span data-ttu-id="ee6c4-111">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="ee6c4-111">Click New.</span></span>
3. <span data-ttu-id="ee6c4-112">Skriv ett värde i fältet Menyalternativ.</span><span class="sxs-lookup"><span data-stu-id="ee6c4-112">In the Menu item name field, type a value.</span></span>
    * <span data-ttu-id="ee6c4-113">Ange ett unikt värde.</span><span class="sxs-lookup"><span data-stu-id="ee6c4-113">Enter a unique value.</span></span> <span data-ttu-id="ee6c4-114">Du kan exempelvis skriva POMove.</span><span class="sxs-lookup"><span data-stu-id="ee6c4-114">For example, you could type POMove.</span></span> <span data-ttu-id="ee6c4-115">Kom ihåg värdet, du behöver det senare.</span><span class="sxs-lookup"><span data-stu-id="ee6c4-115">Remember the value, you'll need it later.</span></span>  
4. <span data-ttu-id="ee6c4-116">Ange ett värde i fältet Titel.</span><span class="sxs-lookup"><span data-stu-id="ee6c4-116">In the Title field, type a value.</span></span>
    * <span data-ttu-id="ee6c4-117">Detta är den rubrik som visas för användaren på den mobila enheten.</span><span class="sxs-lookup"><span data-stu-id="ee6c4-117">This is the title which will be displayed on the mobile device.</span></span> <span data-ttu-id="ee6c4-118">Du kan exempelvis skriva PO Move.</span><span class="sxs-lookup"><span data-stu-id="ee6c4-118">For example, you could type PO Move.</span></span>  
5. <span data-ttu-id="ee6c4-119">Välj Arbete i fältet Läge.</span><span class="sxs-lookup"><span data-stu-id="ee6c4-119">In the Mode field, select 'Work'.</span></span>
6. <span data-ttu-id="ee6c4-120">Välj Ja i fältet Använd befintligt arbete.</span><span class="sxs-lookup"><span data-stu-id="ee6c4-120">Select Yes in the Use existing work field.</span></span>
    * <span data-ttu-id="ee6c4-121">Menyobjektet för den här mobila enheten används för att utföra befintligt arbete.</span><span class="sxs-lookup"><span data-stu-id="ee6c4-121">This mobile device menu item is used to perform existing work.</span></span> <span data-ttu-id="ee6c4-122">Du måste därför ange värdet Ja.</span><span class="sxs-lookup"><span data-stu-id="ee6c4-122">Therefore you must set this value to Yes.</span></span>  
    * <span data-ttu-id="ee6c4-123">Statusfältet Visa lagerstatus avgör om lagerstatusen för lagerbehållningen visas för lagerarbetare på den mobila enheten.</span><span class="sxs-lookup"><span data-stu-id="ee6c4-123">The Display inventory status field determines whether the inventory status of the on-hand inventory will be displayed to the warehouse worker on the mobile device.</span></span>  
7. <span data-ttu-id="ee6c4-124">Välj Systemgruppering i fältet Dirigerad av.</span><span class="sxs-lookup"><span data-stu-id="ee6c4-124">In the Directed by field, select 'System grouping'.</span></span>
    * <span data-ttu-id="ee6c4-125">När du väljer något i fältet Dirigerad av visas ytterligare fält avsnittet Allmänt på den här sidan.</span><span class="sxs-lookup"><span data-stu-id="ee6c4-125">When you select something in the Directed by field, additional fields appear in the General section on this page.</span></span> <span data-ttu-id="ee6c4-126">Fälten som visas beror på vad du har valt.</span><span class="sxs-lookup"><span data-stu-id="ee6c4-126">The fields that appear depend on what you selected.</span></span> <span data-ttu-id="ee6c4-127">När du väljer Systemgruppering läggs två nya fält till.</span><span class="sxs-lookup"><span data-stu-id="ee6c4-127">When you select System grouping, two new fields are added.</span></span> <span data-ttu-id="ee6c4-128">Dessa beskrivs nedan.</span><span class="sxs-lookup"><span data-stu-id="ee6c4-128">These are explained below.</span></span>  
8. <span data-ttu-id="ee6c4-129">Välj "WorkPoolID" i fältet Fält för systemgruppering.</span><span class="sxs-lookup"><span data-stu-id="ee6c4-129">In the System grouping field, select 'WorkPoolId'.</span></span>
    * <span data-ttu-id="ee6c4-130">När lagerarbetare öppnar den här menyartikeln uppmanas de att skanna ett arbetspool-ID.</span><span class="sxs-lookup"><span data-stu-id="ee6c4-130">When warehouse workers open this menu item, they’ll be asked to scan a Work pool ID.</span></span> <span data-ttu-id="ee6c4-131">Alla arbetsorder med detta arbetspool-ID och öppna arbetsorderrader med en av arbetsklasserna som läggs till i det här menyalternativet kommer att skickas till användaren.</span><span class="sxs-lookup"><span data-stu-id="ee6c4-131">All work orders with this Work pool ID and open work order lines with one of the work classes added to this menu item will be pushed to the user.</span></span>  
9. <span data-ttu-id="ee6c4-132">Skriv ett värde i fältet Etikett för systemgruppering.</span><span class="sxs-lookup"><span data-stu-id="ee6c4-132">In the System grouping label field, type a value.</span></span>
    * <span data-ttu-id="ee6c4-133">Den här är texten som visas för användaren på den mobila enheten</span><span class="sxs-lookup"><span data-stu-id="ee6c4-133">This is the text displayed to the user on the mobile device.</span></span> <span data-ttu-id="ee6c4-134">Du kan exempelvis skriva Arbetspool.</span><span class="sxs-lookup"><span data-stu-id="ee6c4-134">For example, you could type Work pool.</span></span>  
10. <span data-ttu-id="ee6c4-135">Välj Ja i fältet Åsidosätt registreringsskylt under placering.</span><span class="sxs-lookup"><span data-stu-id="ee6c4-135">Select Yes in the Override license plate during put field.</span></span>
    * <span data-ttu-id="ee6c4-136">Det här alternativet kan lagerarbetare använda för att åsidosätta målregistreringsskylten när artiklar placeras på en registreringsskyltsstyrd plats.</span><span class="sxs-lookup"><span data-stu-id="ee6c4-136">This option allows warehouse workers to override the target license plate when items are put down on a license plate controlled location.</span></span>  
11. <span data-ttu-id="ee6c4-137">Välj Ja i fältet Grupplats.</span><span class="sxs-lookup"><span data-stu-id="ee6c4-137">Select Yes in the Group put away field.</span></span>
    * <span data-ttu-id="ee6c4-138">Om alla inleveransrader på arbetsordern delar samma plats får användaren en kombinerad placeringsinstruktion för alla rader.</span><span class="sxs-lookup"><span data-stu-id="ee6c4-138">If all the Put lines on the work order share the same location, the user will receive one combined Put instruction for all lines.</span></span>  
    * <span data-ttu-id="ee6c4-139">ID för granskningsmall: med hjälp av en arbetsgranskningsmall kan du ange hur arbetsprocessen för ett menyalternativ ska avbrytas så att en annan åtgärd kan utföras.</span><span class="sxs-lookup"><span data-stu-id="ee6c4-139">Audit template ID: A work audit template allows you to specify that the work process for a menu item should be interrupted so that another operation can be performed.</span></span> <span data-ttu-id="ee6c4-140">Om till exempel det här menyalternativet är till för inkommande arbete kan granskningsmallen kräva att arbetstagaren kontrollerar temperaturen.</span><span class="sxs-lookup"><span data-stu-id="ee6c4-140">For example, if this menu item is for inbound work, the audit template might require that the worker checks the temperature.</span></span> <span data-ttu-id="ee6c4-141">Den punkt som processen avbryts vid anges på revisionsmallen och kan vara, till exempel, när jobbet har påbörjats eller avslutats, eller när dess status ändras.</span><span class="sxs-lookup"><span data-stu-id="ee6c4-141">The point at which the process is interrupted is specified on the audit template and can be, for example, when work is started or completed, or when its status changes.</span></span>  
12. <span data-ttu-id="ee6c4-142">Expandera arbetsklassavsnittet.</span><span class="sxs-lookup"><span data-stu-id="ee6c4-142">Expand the Work classes section.</span></span>
13. <span data-ttu-id="ee6c4-143">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="ee6c4-143">Click New.</span></span>
14. <span data-ttu-id="ee6c4-144">Skriv "Inköp" i fältet Arbetsklass-ID.</span><span class="sxs-lookup"><span data-stu-id="ee6c4-144">In the Work class ID field, type 'Purchase'.</span></span>
    * <span data-ttu-id="ee6c4-145">Arbetspoolen begränsar det arbete menyalternativet kan användas för.</span><span class="sxs-lookup"><span data-stu-id="ee6c4-145">The work pool restricts the work that the menu item can be used for.</span></span> <span data-ttu-id="ee6c4-146">I det här fallet kommer den att användas för öppna orderrader som har inköpsarbetsklass-ID.</span><span class="sxs-lookup"><span data-stu-id="ee6c4-146">In this case it will be used for open work order lines that have the Purchase work class ID.</span></span>  
15. <span data-ttu-id="ee6c4-147">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="ee6c4-147">Click Save.</span></span>

## <a name="set-up-work-confirmation"></a><span data-ttu-id="ee6c4-148">Ställ in arbetsbekräftelse</span><span class="sxs-lookup"><span data-stu-id="ee6c4-148">Set up work confirmation</span></span>
1. <span data-ttu-id="ee6c4-149">Klicka på Inställning av arbetsbekräftelse.</span><span class="sxs-lookup"><span data-stu-id="ee6c4-149">Click Work confirmation setup.</span></span>
2. <span data-ttu-id="ee6c4-150">Välj Välj i fältet Arbetstyp.</span><span class="sxs-lookup"><span data-stu-id="ee6c4-150">In the Work type field, select 'Pick'.</span></span>
3. <span data-ttu-id="ee6c4-151">Markera kryssrutan Bekräfta automatiskt.</span><span class="sxs-lookup"><span data-stu-id="ee6c4-151">Select the Auto confirm check box.</span></span>
    * <span data-ttu-id="ee6c4-152">Arbetsinstruktionen med arbetstypen Plockning kommer att bekräftas automatiskt.</span><span class="sxs-lookup"><span data-stu-id="ee6c4-152">The work instruction with work type Pick will be auto-confirmed.</span></span> <span data-ttu-id="ee6c4-153">Denna instruktion visas inte för användaren.</span><span class="sxs-lookup"><span data-stu-id="ee6c4-153">This instruction will not be presented to the user.</span></span>  
4. <span data-ttu-id="ee6c4-154">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="ee6c4-154">Click New.</span></span>
5. <span data-ttu-id="ee6c4-155">Välj Placera i fältet Arbetstyp.</span><span class="sxs-lookup"><span data-stu-id="ee6c4-155">In the Work type field, select 'Put'.</span></span>
6. <span data-ttu-id="ee6c4-156">Markera kryssrutan Platsbekräftelse.</span><span class="sxs-lookup"><span data-stu-id="ee6c4-156">Select the Location confirmation check box.</span></span>
    * <span data-ttu-id="ee6c4-157">Lagerarbetaren kommer att uppmanas att utföra en bekräftelsescanning av platsen när artikeln införs.</span><span class="sxs-lookup"><span data-stu-id="ee6c4-157">The warehouse worker will be asked to perform a confirmation scan of the location, when the item is put down.</span></span>  
7. <span data-ttu-id="ee6c4-158">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="ee6c4-158">Click Save.</span></span>
8. <span data-ttu-id="ee6c4-159">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="ee6c4-159">Close the page.</span></span>
9. <span data-ttu-id="ee6c4-160">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="ee6c4-160">Close the page.</span></span>

## <a name="add-the-menu-item-to-a-mobile-device-menu"></a><span data-ttu-id="ee6c4-161">Lägg till menykommandot på en meny för mobila enheter</span><span class="sxs-lookup"><span data-stu-id="ee6c4-161">Add the menu item to a mobile device menu</span></span>
1. <span data-ttu-id="ee6c4-162">Gå till Meny på mobil enhet.</span><span class="sxs-lookup"><span data-stu-id="ee6c4-162">Go to Mobile device menu.</span></span>
2. <span data-ttu-id="ee6c4-163">Klicka på Redigera.</span><span class="sxs-lookup"><span data-stu-id="ee6c4-163">Click Edit.</span></span>
3. <span data-ttu-id="ee6c4-164">Använd snabbfiltret för att söka efter poster.</span><span class="sxs-lookup"><span data-stu-id="ee6c4-164">Use the Quick Filter to find records.</span></span> <span data-ttu-id="ee6c4-165">Filtrera till exempel i fältet Namn med värdet inkommande.</span><span class="sxs-lookup"><span data-stu-id="ee6c4-165">For example, filter on the Name field with a value of 'inbound'.</span></span>
    * <span data-ttu-id="ee6c4-166">Du vill söka efter på menyn som du använder för inkommande menyalternativ.</span><span class="sxs-lookup"><span data-stu-id="ee6c4-166">You want to find the menu you use for inbound menu items.</span></span> <span data-ttu-id="ee6c4-167">I USMF kallas detta Inkommande.</span><span class="sxs-lookup"><span data-stu-id="ee6c4-167">In USMF this is called Inbound.</span></span>  
4. <span data-ttu-id="ee6c4-168">Välj ett värde i trädet.</span><span class="sxs-lookup"><span data-stu-id="ee6c4-168">In the tree, select 'a value'.</span></span>
5. <span data-ttu-id="ee6c4-169">Klicka på pilen som pekar åt höger.</span><span class="sxs-lookup"><span data-stu-id="ee6c4-169">Click on the arrow that points to the right.</span></span>
6. <span data-ttu-id="ee6c4-170">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="ee6c4-170">Click Save.</span></span>
7. <span data-ttu-id="ee6c4-171">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="ee6c4-171">Close the page.</span></span>


