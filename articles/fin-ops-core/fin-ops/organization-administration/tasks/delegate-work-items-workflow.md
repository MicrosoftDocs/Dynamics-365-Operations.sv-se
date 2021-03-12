---
title: Delegera arbetsuppgifter i ett arbetsflöde
description: Om du kommer att vara borta från kontoret under en tid eller av annat skäl inte kommer att kunna arbeta med en arbetsuppgift, kan du delegera eller omfördela dina arbetsuppgifter till andra användare.
author: ChrisGarty
manager: AnnBe
ms.date: 07/07/2020
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysUserSetup, WorkflowDelegationUserListLookup
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.author: cgarty
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 48d8fd06217d318fa8208e11ffa5624f6be25be1
ms.sourcegitcommit: b112925c389a460a98c3401cc2c67df7091b066f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/19/2020
ms.locfileid: "4796716"
---
# <a name="delegate-work-items-in-a-workflow"></a><span data-ttu-id="fd9d2-103">Delegera arbetsuppgifter i ett arbetsflöde</span><span class="sxs-lookup"><span data-stu-id="fd9d2-103">Delegate work items in a workflow</span></span>

[!include [banner](../../includes/banner.md)]

## <a name="manually-delegate-a-work-item"></a><span data-ttu-id="fd9d2-104">Manuellt delegera en arbetsuppgift</span><span class="sxs-lookup"><span data-stu-id="fd9d2-104">Manually delegate a work item</span></span>

<span data-ttu-id="fd9d2-105">Om du vill delegera en enskild arbetsuppgift, välj alternativet **Delegera** i menyn **Arbetsflöde** och ange sedan användaren som ska delegeras till tillsammans med en kommentar.</span><span class="sxs-lookup"><span data-stu-id="fd9d2-105">To delegate an individual work item, select the **Delegate** option in the **Workflow** menu and then enter the user to be delegated to along with a comment.</span></span> <span data-ttu-id="fd9d2-106">Detta tilldelar om arbetsuppgift till användaren så att de kan slutföra den.</span><span class="sxs-lookup"><span data-stu-id="fd9d2-106">This will reassign the work item to that user so they can complete it.</span></span>

## <a name="manually-delegate-multiple-work-items"></a><span data-ttu-id="fd9d2-107">Delegera flera arbetsuppgifter manuellt</span><span class="sxs-lookup"><span data-stu-id="fd9d2-107">Manually delegate multiple work items</span></span>

<span data-ttu-id="fd9d2-108">Flera arbetsuppgifter kan delegeras till varandra från sidan **Arbetsuppgifter som tilldelats till mig**.</span><span class="sxs-lookup"><span data-stu-id="fd9d2-108">Multiple work items can be delegated together from the **Work items assigned to me** page.</span></span> <span data-ttu-id="fd9d2-109">Följande arbetsflödestyper är berättigade för massdelegering: arbetsflöde för godkännande av inköpsavtal, arbetsflöde för inköpsorder, granskning av inköpsrekvisition och arbetsflöde för leverantör.</span><span class="sxs-lookup"><span data-stu-id="fd9d2-109">The following workflow types are eligible for mass delegation: Purchase agreement approval workflow, Purchase order workflow, Purchase requisition review, and Vendor invoice workflow.</span></span> <span data-ttu-id="fd9d2-110">Funktionen **Delegera flera arbetsuppgifter** är inaktiverad som standard och kan aktiveras i **Arbetsytor > Funktionshantering**.</span><span class="sxs-lookup"><span data-stu-id="fd9d2-110">The **Delegate multiple work items** feature is disabled by default and can be enabled in **Workspaces > Feature management**.</span></span> <span data-ttu-id="fd9d2-111">Kontakta systemadministratören om du vill ha hjälp med att aktivera den här funktionen.</span><span class="sxs-lookup"><span data-stu-id="fd9d2-111">Contact your system administrator for help with enabling this feature.</span></span>
1.  <span data-ttu-id="fd9d2-112">Gå till **Gemensamt > Gemensamt > Arbetsuppgifter > Arbetsuppgifter som tilldelats till mig**.</span><span class="sxs-lookup"><span data-stu-id="fd9d2-112">Go to **Common > Common > Work items > Work items assigned to me**.</span></span>
2.  <span data-ttu-id="fd9d2-113">Välj de arbetsuppgifter som ska delegeras.</span><span class="sxs-lookup"><span data-stu-id="fd9d2-113">Select the work items that will be delegated.</span></span>
3.  <span data-ttu-id="fd9d2-114">Klicka på menyn **Delegera arbetsuppgifter**.</span><span class="sxs-lookup"><span data-stu-id="fd9d2-114">Click the **Delegate work items** menu.</span></span>
4.  <span data-ttu-id="fd9d2-115">I fältet **användare** markera den användare som du vill delegera arbetsuppgifterna till.</span><span class="sxs-lookup"><span data-stu-id="fd9d2-115">In the **User** field, select the user to delegate the work items to.</span></span>
5.  <span data-ttu-id="fd9d2-116">Ange en kommentar som förklarar varför du delegerar arbetsuppgifterna i fältet **Kommentar**.</span><span class="sxs-lookup"><span data-stu-id="fd9d2-116">In the **Comment** field, enter a comment that explains why you're delegating the work items.</span></span>
6.  <span data-ttu-id="fd9d2-117">Klicka på knappen **Delegera arbetsuppgifter** om du vill slutföra delegeringen av arbetsuppgiften.</span><span class="sxs-lookup"><span data-stu-id="fd9d2-117">Click the **Delegate work items** button to complete the work item delegation.</span></span>

## <a name="automatically-delegate-work-items"></a><span data-ttu-id="fd9d2-118">Delegera arbetsuppgiften automatiskt</span><span class="sxs-lookup"><span data-stu-id="fd9d2-118">Automatically delegate work items</span></span>

<span data-ttu-id="fd9d2-119">Om du tänker vara borta från kontoret eller annars inte kan åtgärda arbetsuppgifter för en viss tidsperiod, kan du automatiskt delegera nya arbetsuppgifter till andra användare på sidan **Användaralternativ**.</span><span class="sxs-lookup"><span data-stu-id="fd9d2-119">If you plan to be out of the office or otherwise unavailable to act on work items for a period of time, you can automatically delegate new work items to other users using the **User options** page.</span></span>

### <a name="set-up-automatic-delegation"></a><span data-ttu-id="fd9d2-120">Ställa in automatisk delegering</span><span class="sxs-lookup"><span data-stu-id="fd9d2-120">Set up automatic delegation</span></span>
1. <span data-ttu-id="fd9d2-121">Gå till **Allmänt > Inställningar > Användaralternativ**.</span><span class="sxs-lookup"><span data-stu-id="fd9d2-121">Go to **Common > Setup > User options**.</span></span>
2. <span data-ttu-id="fd9d2-122">Klicka på **Arbetsflöde**. Kontrollera att avsnittet Delegering är expanderat.</span><span class="sxs-lookup"><span data-stu-id="fd9d2-122">Click the **Workflow** tab. Make sure the Delegation section is expanded.</span></span> <span data-ttu-id="fd9d2-123">Om du vill konfigurera systemet för att automatiskt delegera dina arbetsuppgifter till andra användare, måste du skapa delegeringsregler som anger när vissa typer av arbetsuppgifter delegeras.</span><span class="sxs-lookup"><span data-stu-id="fd9d2-123">To configure the system to automatically delegate your work items to other users, you must create delegation rules, which specify when certain types of work items are delegated.</span></span> <span data-ttu-id="fd9d2-124">Följ dessa steg för att skapa en ny delegeringsregel.</span><span class="sxs-lookup"><span data-stu-id="fd9d2-124">Follow these steps to create a delegation rule.</span></span>  
3. <span data-ttu-id="fd9d2-125">Klicka på **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="fd9d2-125">Click **Add**.</span></span>
4. <span data-ttu-id="fd9d2-126">Markera ett alternativ i fältet **Omfattning**:</span><span class="sxs-lookup"><span data-stu-id="fd9d2-126">In the **Scope** field, select an option:</span></span>
    - <span data-ttu-id="fd9d2-127">Alla – Delegera alla arbetsuppgifter som har tilldelats dig.</span><span class="sxs-lookup"><span data-stu-id="fd9d2-127">All – Delegate all work items that are assigned to you.</span></span>
    - <span data-ttu-id="fd9d2-128">Modul – Delegera enbart de arbetsuppgifter som är relaterade till en specifik arbetsflödestyp.</span><span class="sxs-lookup"><span data-stu-id="fd9d2-128">Module – Delegate only the work items that are related to a specific type of workflow.</span></span> <span data-ttu-id="fd9d2-129">Om du väljer det här alternativet måste du välja typ av arbetsflöde i fältet **Namn**.</span><span class="sxs-lookup"><span data-stu-id="fd9d2-129">If you select this option, you must select the type of workflow in the **Name** field.</span></span>
    - <span data-ttu-id="fd9d2-130">Arbetsflöde – Delegera enbart de arbetsuppgifter som är relaterade till en specifik typ av arbetsflöde.</span><span class="sxs-lookup"><span data-stu-id="fd9d2-130">Workflow – Delegate only the work items that are related to a specific workflow.</span></span> <span data-ttu-id="fd9d2-131">Om du väljer det här alternativet måste du välja typen av arbetsflöde i fältet **Namn**.</span><span class="sxs-lookup"><span data-stu-id="fd9d2-131">If you select this option, you must select the workflow in the **Name** field.</span></span>  
5. <span data-ttu-id="fd9d2-132">I fältet **Namn**:</span><span class="sxs-lookup"><span data-stu-id="fd9d2-132">In the **Name** field:</span></span>
    - <span data-ttu-id="fd9d2-133">För omfattningen **Modul** välj målmodul.</span><span class="sxs-lookup"><span data-stu-id="fd9d2-133">For **Module** scope, select the target module.</span></span>
    - <span data-ttu-id="fd9d2-134">För omfattningen **Arbetsflöde** välj målarbetsflöde.</span><span class="sxs-lookup"><span data-stu-id="fd9d2-134">For **Workflow** scope, select the target workflow.</span></span>
6. <span data-ttu-id="fd9d2-135">Markera den användare som du vill delegera arbetsuppgifterna till i fältet **Delegera**.</span><span class="sxs-lookup"><span data-stu-id="fd9d2-135">In the **Delegate** field, select the user to delegate the work items to.</span></span> <span data-ttu-id="fd9d2-136">Använd fälten **Startdatum/-tid** och **Slutdatum/-tid** när du vill att arbetsuppgifterna ska delegeras automatiskt.</span><span class="sxs-lookup"><span data-stu-id="fd9d2-136">Use the **Start date/time** and **End date/time** fields to specify when you want the work items to be automatically delegated.</span></span>  
7. <span data-ttu-id="fd9d2-137">Ange datum och tid i fältet **Startdatum/-tid**.</span><span class="sxs-lookup"><span data-stu-id="fd9d2-137">In the **Start date/time** field, enter a date and time.</span></span>
8. <span data-ttu-id="fd9d2-138">Ange datum och tid i fältet **Slutdatum/-tid**.</span><span class="sxs-lookup"><span data-stu-id="fd9d2-138">In the **End date/time** field, enter a date and time.</span></span>
9. <span data-ttu-id="fd9d2-139">Aktivera delegeringsregeln genom att markera kryssrutan **Aktiverad**.</span><span class="sxs-lookup"><span data-stu-id="fd9d2-139">Select the **Enabled** check box to activate the delegation rule.</span></span> 
10. <span data-ttu-id="fd9d2-140">Ange en kommentar som förklarar varför du delegerar arbetsuppgifterna i fältet **Kommentar**.</span><span class="sxs-lookup"><span data-stu-id="fd9d2-140">In the **Comment** field, enter a comment that explains why you're delegating the work items.</span></span>
