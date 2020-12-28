---
title: Tilldela uppgiftslistor till butiker eller medarbetare
description: I det här avsnittet beskrivs hur du tilldelar en uppgiftslista till butiker eller medarbetare i Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
manager: annbe
ms.date: 02/10/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.search.industry: ''
ms.author: gmohanv
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Release 10.0.9
ms.openlocfilehash: 82cec9861b759037f40315fb2e6f36002a0ac059
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "4415898"
---
# <a name="assign-task-lists-to-stores-or-employees"></a><span data-ttu-id="d3f91-103">Tilldela uppgiftslistor till butiker eller medarbetare</span><span class="sxs-lookup"><span data-stu-id="d3f91-103">Assign task lists to stores or employees</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="d3f91-104">I det här avsnittet beskrivs hur du tilldelar en uppgiftslista till butiker eller medarbetare i Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="d3f91-104">This topic describes how to assign task lists to stores or employees in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="d3f91-105">Översikt</span><span class="sxs-lookup"><span data-stu-id="d3f91-105">Overview</span></span>

<span data-ttu-id="d3f91-106">Med uppgiftshantering i Dynamics 365 Commerce kan du tilldela en uppgiftslista till flera butiker eller medarbetare, eller till en kombination av butiker och medarbetare.</span><span class="sxs-lookup"><span data-stu-id="d3f91-106">Task management in Dynamics 365 Commerce lets you assign a task list to multiple stores or employees, or to a combination of stores and employees.</span></span> <span data-ttu-id="d3f91-107">En regional chef för 20 butiker kan till exempel vilja tilldela uppgiftslistan **förberedelse av semestertider** till alla 20 butiker.</span><span class="sxs-lookup"><span data-stu-id="d3f91-107">For example, a regional manager for 20 stores might want to assign the **Holiday season preparation** task list to all 20 stores.</span></span>

## <a name="start-the-task-list-assignment-process"></a><span data-ttu-id="d3f91-108">Starta listan för aktivitetstilldelningar</span><span class="sxs-lookup"><span data-stu-id="d3f91-108">Start the task list assignment process</span></span>

<span data-ttu-id="d3f91-109">Om du vill börja tilldela en uppgiftslista följer du stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="d3f91-109">To start the process of assigning a task list, follow these steps.</span></span>

1. <span data-ttu-id="d3f91-110">Gå till **Retail och Commerce \> Uppgiftshantering \> Administration av uppgiftshantering**.</span><span class="sxs-lookup"><span data-stu-id="d3f91-110">Go to **Retail and Commerce \> Task management \> Task management administration**.</span></span>
1. <span data-ttu-id="d3f91-111">Markera uppgiftslistan som du vill tilldela.</span><span class="sxs-lookup"><span data-stu-id="d3f91-111">Select the task list to assign.</span></span>
1. <span data-ttu-id="d3f91-112">Select **Starta process**.</span><span class="sxs-lookup"><span data-stu-id="d3f91-112">Select **Start process**.</span></span>
1. <span data-ttu-id="d3f91-113">I dialogrutan **Starta process** på fliken **Allmänt** i fältet **Processnamn** anger du ett namn (t.ex. **Butiker i östra regionen**).</span><span class="sxs-lookup"><span data-stu-id="d3f91-113">In the **Start process** dialog box, on the **General** tab, in the **Process name** field, enter a name (for example, **East region stores**).</span></span>
1. <span data-ttu-id="d3f91-114">Ange ett datum i fältet **Måldatum**.</span><span class="sxs-lookup"><span data-stu-id="d3f91-114">In the **Target date** field, specify a date.</span></span>
1. <span data-ttu-id="d3f91-115">Om du vill tilldela en uppgiftslista till butiker, på fliken **butiker** använder du filtret **Organisationshierarki** för att hitta och välja butikerna.</span><span class="sxs-lookup"><span data-stu-id="d3f91-115">To assign the task list to stores, on the **Stores** tab, use the **Organization hierarchy** filter to find and select the stores.</span></span>

    <span data-ttu-id="d3f91-116">Om du vill tilldela uppgiftslistan till medarbetare, går du till fliken **arbetare** och väljer medarbetarna.</span><span class="sxs-lookup"><span data-stu-id="d3f91-116">To assign the task list to employees, on the **Workers** tab, find and select the employees.</span></span>

1. <span data-ttu-id="d3f91-117">Starta processen genom att välja **OK**.</span><span class="sxs-lookup"><span data-stu-id="d3f91-117">Select **OK** to start the process.</span></span> <span data-ttu-id="d3f91-118">Uppgiftslistan tilldelas till de valda butikerna eller medarbetarna.</span><span class="sxs-lookup"><span data-stu-id="d3f91-118">The tasks list is assigned to the selected stores or employees.</span></span>

<span data-ttu-id="d3f91-119">I bilden nedan visas ett exempel på hur du hittar och väljer butiker i dialogrutan **Starta process**.</span><span class="sxs-lookup"><span data-stu-id="d3f91-119">The following illustration shows an example of how to find and select stores in the **Start process** dialog box.</span></span>

![Söka efter och välja butiker i dialogrutan starta process](media/HQ-Assign-Tasks-Lists.png)

## <a name="assign-task-lists-on-a-recurring-basis"></a><span data-ttu-id="d3f91-121">Tilldela uppgiftslistor regelbundet</span><span class="sxs-lookup"><span data-stu-id="d3f91-121">Assign task lists on a recurring basis</span></span>

<span data-ttu-id="d3f91-122">Återförsäljare har ibland återkommande uppgifter, t.ex. "Checklista för stängning torsdag" eller "Checklista för första dagen i månaden".</span><span class="sxs-lookup"><span data-stu-id="d3f91-122">Retailer sometimes have recurrent tasks, such as "Thursday closure checklist" or "First day of the month checklist."</span></span> <span data-ttu-id="d3f91-123">De kan därför vilja tilldela aktivitetslistan på en återkommande basis.</span><span class="sxs-lookup"><span data-stu-id="d3f91-123">Therefore, they might want to assign the task list on a recurring basis.</span></span>

1. <span data-ttu-id="d3f91-124">Gå till **Retail och Commerce \> Uppgiftshantering \> Administration av uppgiftshantering**.</span><span class="sxs-lookup"><span data-stu-id="d3f91-124">Go to **Retail and Commerce \> Task management \> Task management administration**.</span></span>
1. <span data-ttu-id="d3f91-125">Markera uppgiftslistan som du vill tilldela.</span><span class="sxs-lookup"><span data-stu-id="d3f91-125">Select the task list to assign.</span></span>
1. <span data-ttu-id="d3f91-126">Select **Starta process**.</span><span class="sxs-lookup"><span data-stu-id="d3f91-126">Select **Start process**.</span></span>
1. <span data-ttu-id="d3f91-127">I dialogrutan **Starta process** på fliken **Allmänt** i fältet **Processnamn** anger du ett namn.</span><span class="sxs-lookup"><span data-stu-id="d3f91-127">In the **Start process** dialog box, on the **General** tab, in the **Process name** field, enter a name.</span></span>
1. <span data-ttu-id="d3f91-128">Ge alternativet **Upprepning** värdet **Ja**.</span><span class="sxs-lookup"><span data-stu-id="d3f91-128">Set the **Recurrence** option to **Yes**.</span></span>
1. <span data-ttu-id="d3f91-129">I fältet **Återkommande förskjutning av måldatum i dagar** anger du antal dagar.</span><span class="sxs-lookup"><span data-stu-id="d3f91-129">In the **Recurrence target date offset in days** field, enter a number of days.</span></span> <span data-ttu-id="d3f91-130">Om du till exempel anger **4** är måldatumet det återkommande datumet plus fyra dagar.</span><span class="sxs-lookup"><span data-stu-id="d3f91-130">For example, if you enter **4**, the target date is the recurrence date plus four days.</span></span>
1. <span data-ttu-id="d3f91-131">På fliken **kör i bakgrunden** väljer du **återkommande**.</span><span class="sxs-lookup"><span data-stu-id="d3f91-131">On the **Run in the background** tab, select **Recurrence**.</span></span>
1. <span data-ttu-id="d3f91-132">I dialogrutan **Definiera återkommande** anger du frekvenskriterier och väljer sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="d3f91-132">In the **Define recurrence** dialog box, enter the frequency criteria, and then select **OK**.</span></span>

<span data-ttu-id="d3f91-133">I bilden nedan visas ett exempel på hur du anger frekvenskriterier i dialogrutan **definiera återkommande**.</span><span class="sxs-lookup"><span data-stu-id="d3f91-133">The following illustration shows an example of how to enter frequency criteria in the **Define recurrence** dialog box.</span></span>

![Ange frekvenskriterier i dialogrutan Definiera återkommande](media/HQ-Assign-Tasks-Lists-Recurrently.png)

## <a name="track-task-list-status"></a><span data-ttu-id="d3f91-135">Status för spåra uppgiftslista</span><span class="sxs-lookup"><span data-stu-id="d3f91-135">Track task list status</span></span>

<span data-ttu-id="d3f91-136">Om du är en regional chef eller butikschef kanske du vill spåra status för uppgiftslistor som har tilldelats flera butiker eller medarbetare.</span><span class="sxs-lookup"><span data-stu-id="d3f91-136">If you're a regional manager or store manager, you might want to track the status of task lists that have been assigned to multiple stores or employees.</span></span> <span data-ttu-id="d3f91-137">Du kan sedan följa upp med butiker eller arbetare som inte slutfört sina tilldelade uppgifter i tid.</span><span class="sxs-lookup"><span data-stu-id="d3f91-137">You can then follow up with stores or workers that didn't complete their assigned tasks on time.</span></span> <span data-ttu-id="d3f91-138">Med Commerce backoffice kan du visa status för uppgiftslistor, tilldela om uppgifter eller ändra status för en uppgift.</span><span class="sxs-lookup"><span data-stu-id="d3f91-138">Commerce back office lets you view the status of task lists, reassign tasks, or change the status of a task.</span></span>

<span data-ttu-id="d3f91-139">Följ stegen nedan om du vill spåra uppgiftslistans status för alla uppgifter.</span><span class="sxs-lookup"><span data-stu-id="d3f91-139">To track the task list status for all tasks, follow these steps.</span></span>

1. <span data-ttu-id="d3f91-140">Gå till **Retail och Commerce \> Uppgiftshantering \> Processer för uppgiftshantering**.</span><span class="sxs-lookup"><span data-stu-id="d3f91-140">Go to **Retail and Commerce \> Task management \> Task management processes**.</span></span>
1. <span data-ttu-id="d3f91-141">Välj fliken **alla uppgiftslistor** om du vill visa status för alla uppgiftslistor som har tilldelats olika butiker.</span><span class="sxs-lookup"><span data-stu-id="d3f91-141">Select the **All task lists** tab to view the status of all task lists that are assigned to various stores.</span></span>

<span data-ttu-id="d3f91-142">Följ dessa steg för att spåra uppgiftslistans status för alla uppgifter som tilldelats dig.</span><span class="sxs-lookup"><span data-stu-id="d3f91-142">To track the task list status for all tasks that are assigned to you, follow these steps.</span></span>

1. <span data-ttu-id="d3f91-143">Gå till **Retail och Commerce \> Uppgiftshantering \> Processer för uppgiftshantering**.</span><span class="sxs-lookup"><span data-stu-id="d3f91-143">Go to **Retail and Commerce \> Task management \> Task management processes**.</span></span>
1. <span data-ttu-id="d3f91-144">Välj fliken **mina uppgifter** eller **aktiviteter** om du vill visa eller uppdatera status för de uppgifter som har tilldelats dig.</span><span class="sxs-lookup"><span data-stu-id="d3f91-144">Select the **My tasks** or **All tasks** tab to view or update the status of tasks that are assigned to you.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="d3f91-145">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="d3f91-145">Additional resources</span></span>

[<span data-ttu-id="d3f91-146">Översikt över uppgiftshantering</span><span class="sxs-lookup"><span data-stu-id="d3f91-146">Task management overview</span></span>](task-mgmt-overview.md)

[<span data-ttu-id="d3f91-147">Konfigurera uppgiftshantering</span><span class="sxs-lookup"><span data-stu-id="d3f91-147">Configure task management</span></span>](task-mgmt-configure.md)

[<span data-ttu-id="d3f91-148">Skapa uppgiftslistor och lägga till uppgifter</span><span class="sxs-lookup"><span data-stu-id="d3f91-148">Create task lists and add tasks</span></span>](task-mgmt-create-lists.md)

[<span data-ttu-id="d3f91-149">Uppgiftshantering i kassan</span><span class="sxs-lookup"><span data-stu-id="d3f91-149">Task management in POS</span></span>](task-mgmt-POS.md)
