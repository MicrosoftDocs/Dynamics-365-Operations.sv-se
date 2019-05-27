---
title: Delegera arbetsuppgifter i ett arbetsflöde
description: Om du kommer att vara borta från kontoret under en tid eller av annat skäl inte kommer att kunna arbeta med en arbetsuppgift, kan du delegera eller omfördela dina arbetsuppgifter till andra användare.
author: jasongre
manager: AnnBe
ms.date: 04/09/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysUserSetup, WorkflowDelegationUserListLookup
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: feace647d7acef6abf86b13fcb8019c622c55ff6
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/07/2019
ms.locfileid: "1509465"
---
# <a name="delegate-work-items-in-a-workflow"></a><span data-ttu-id="e3316-103">Delegera arbetsuppgifter i ett arbetsflöde</span><span class="sxs-lookup"><span data-stu-id="e3316-103">Delegate work items in a workflow</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

## <a name="manually-delegate-a-work-item"></a><span data-ttu-id="e3316-104">Manuellt delegera en arbetsuppgift</span><span class="sxs-lookup"><span data-stu-id="e3316-104">Manually delegate a work item</span></span>

<span data-ttu-id="e3316-105">Om du vill delegera en enskild arbetsuppgift, välj alternativet **Delegera** i menyn **Arbetsflöde** och ange sedan användaren som ska delegeras till tillsammans med en kommentar.</span><span class="sxs-lookup"><span data-stu-id="e3316-105">To delegate an individual work item, select the **Delegate** option in the **Workflow** menu and then enter the user to be delegated to along with a comment.</span></span> <span data-ttu-id="e3316-106">Detta tilldelar om arbetsuppgift till användaren så att de kan slutföra den.</span><span class="sxs-lookup"><span data-stu-id="e3316-106">This will reassign the work item to that user so they can complete it.</span></span>

## <a name="automatically-delegate-work-items"></a><span data-ttu-id="e3316-107">Delegera arbetsuppgiften automatiskt</span><span class="sxs-lookup"><span data-stu-id="e3316-107">Automatically delegate work items</span></span>

<span data-ttu-id="e3316-108">Om du tänker vara borta från kontoret eller annars inte kan åtgärda arbetsuppgifter för en viss tidsperiod, kan du automatiskt delegera nya arbetsuppgifter till andra användare på sidan **Användaralternativ**.</span><span class="sxs-lookup"><span data-stu-id="e3316-108">If you plan to be out of the office or otherwise unavailable to act on work items for a period of time, you can automatically delegate new work items to other users using the **User options** page.</span></span>

### <a name="set-up-automatic-delegation"></a><span data-ttu-id="e3316-109">Ställa in automatisk delegering</span><span class="sxs-lookup"><span data-stu-id="e3316-109">Set up automatic delegation</span></span>
1. <span data-ttu-id="e3316-110">Gå till Allmänt > Inställningar > Användaralternativ.</span><span class="sxs-lookup"><span data-stu-id="e3316-110">Go to Common > Setup > User options.</span></span>
2. <span data-ttu-id="e3316-111">Klicka på fliken Arbetsflöde.</span><span class="sxs-lookup"><span data-stu-id="e3316-111">Click the Workflow tab.</span></span>
    * <span data-ttu-id="e3316-112">Kontrollera att avsnittet för Delegering expanderas.</span><span class="sxs-lookup"><span data-stu-id="e3316-112">Make sure the Delegation section is expanded.</span></span>    <span data-ttu-id="e3316-113">Om du vill konfigurera systemet för att automatiskt delegera dina arbetsuppgifter till andra användare, måste du skapa delegeringsregler som anger när vissa typer av arbetsuppgifter delegeras.</span><span class="sxs-lookup"><span data-stu-id="e3316-113">To configure the system to automatically delegate your work items to other users, you must create delegation rules, which specify when certain types of work items are delegated.</span></span> <span data-ttu-id="e3316-114">Följ dessa steg för att skapa en ny delegeringsregel.</span><span class="sxs-lookup"><span data-stu-id="e3316-114">Follow these steps to create a delegation rule.</span></span>  
3. <span data-ttu-id="e3316-115">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="e3316-115">Click Add.</span></span>
4. <span data-ttu-id="e3316-116">Markera ett alternativ i fältet Omfattning.</span><span class="sxs-lookup"><span data-stu-id="e3316-116">In the Scope field, select an option.</span></span>
    * <span data-ttu-id="e3316-117">Alla – Delegera alla arbetsuppgifter som har tilldelats dig.</span><span class="sxs-lookup"><span data-stu-id="e3316-117">All – Delegate all work items that are assigned to you.</span></span>    <span data-ttu-id="e3316-118">Modul – Delegera enbart de arbetsuppgifter som är relaterade till en specifik arbetsflödestyp.</span><span class="sxs-lookup"><span data-stu-id="e3316-118">Module – Delegate only the work items that are related to a specific type of workflow.</span></span> <span data-ttu-id="e3316-119">Om du väljer det här alternativet måste du välja typ av arbetsflöde i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="e3316-119">If you select this option, you must select the type of workflow in the Name field.</span></span>    <span data-ttu-id="e3316-120">Arbetsflöde – Delegera enbart de arbetsuppgifter som är relaterade till en specifik typ av arbetsflöde.</span><span class="sxs-lookup"><span data-stu-id="e3316-120">Workflow – Delegate only the work items that are related to a specific workflow.</span></span> <span data-ttu-id="e3316-121">Om du väljer det här alternativet måste du välja typen av arbetsflöde i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="e3316-121">If you select this option, you must select the workflow in the Name field.</span></span>  
5. <span data-ttu-id="e3316-122">Markera den användare som du vill delegera arbetsuppgifterna till i fältet Delegera.</span><span class="sxs-lookup"><span data-stu-id="e3316-122">In the Delegate field, select the user to delegate the work items to.</span></span>
    * <span data-ttu-id="e3316-123">Använd fälten Startdatum/-tid och Slutdatum/-tid när du vill att arbetsuppgifterna ska delegeras automatiskt.</span><span class="sxs-lookup"><span data-stu-id="e3316-123">Use the Start date/time and End date/time fields to specify when you want the work items to be automatically delegated.</span></span>  
6. <span data-ttu-id="e3316-124">Ange datum och tid i fältet Startdatum/-tid.</span><span class="sxs-lookup"><span data-stu-id="e3316-124">In the Start date/time field, enter a date and time.</span></span>
7. <span data-ttu-id="e3316-125">Ange datum och tid i fältet Slutdatum/-tid.</span><span class="sxs-lookup"><span data-stu-id="e3316-125">In the End date/time field, enter a date and time.</span></span>
8. <span data-ttu-id="e3316-126">Aktivera delegeringsregeln genom att markera kryssrutan Aktiverad.</span><span class="sxs-lookup"><span data-stu-id="e3316-126">Select the Enabled check box to activate the delegation rule.</span></span>
    * <span data-ttu-id="e3316-127">Om du har valt Modul som Omfattning måste du välja modulen i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="e3316-127">If you selected Module as the Scope, then you must select the module in the Name field.</span></span>    <span data-ttu-id="e3316-128">Om du har valt Arbetsflöde som Omfattning måste du välja specifikt arbetsflöde att delegera i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="e3316-128">If you selected Workflow as the Scope, then you must select the specific workflow to delegate in the Name field.</span></span>  
9. <span data-ttu-id="e3316-129">Ange en kommentar som förklarar varför du delegerar arbetsuppgifterna i fältet Kommentar.</span><span class="sxs-lookup"><span data-stu-id="e3316-129">In the Comment field, enter a comment that explains why you are delegating the work items.</span></span>

