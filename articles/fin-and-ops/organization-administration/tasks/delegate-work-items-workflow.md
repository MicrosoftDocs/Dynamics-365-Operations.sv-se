--- 
title: "Delegera arbetsuppgifter i ett arbetsflöde"
description: "Om du kommer att vara borta från kontoret under en tid eller av annat skäl inte kommer att kunna arbeta med en arbetsuppgift, kan du delegera eller omfördela dina arbetsuppgifter till andra användare."
author: jasongre
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SysUserSetup, WorkflowDelegationUserListLookup
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: abd59b96a2e5dceb2492c2db2c617485b332fbd3
ms.openlocfilehash: f85a1318822ceaf829134bf2eb3581e350d5bea4
ms.contentlocale: sv-se
ms.lasthandoff: 09/13/2018

---
# <a name="delegate-work-items-in-a-workflow"></a><span data-ttu-id="4e95a-103">Delegera arbetsuppgifter i ett arbetsflöde</span><span class="sxs-lookup"><span data-stu-id="4e95a-103">Delegate work items in a workflow</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="4e95a-104">Om du kommer att vara borta från kontoret under en tid eller av annat skäl inte kommer att kunna arbeta med en arbetsuppgift, kan du delegera eller omfördela dina arbetsuppgifter till andra användare.</span><span class="sxs-lookup"><span data-stu-id="4e95a-104">If you plan to be out of the office or otherwise unavailable to act on work items, you can delegate, or reassign, your work items to other users.</span></span> <span data-ttu-id="4e95a-105">Med den här proceduren kan du konfigurera systemet att automatiskt delegera dina arbetsuppgifter till en annan användare.</span><span class="sxs-lookup"><span data-stu-id="4e95a-105">This procedure helps you configure the system to automatically delegate your work items to another user.</span></span>



<span data-ttu-id="4e95a-106">Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF.</span><span class="sxs-lookup"><span data-stu-id="4e95a-106">The demo data company used to create this procedure is USMF.</span></span>


## <a name="set-up-automatic-delegation"></a><span data-ttu-id="4e95a-107">Ställa in automatisk delegering</span><span class="sxs-lookup"><span data-stu-id="4e95a-107">Set up automatic delegation</span></span>
1. <span data-ttu-id="4e95a-108">Gå till Allmänt > Inställningar > Användaralternativ.</span><span class="sxs-lookup"><span data-stu-id="4e95a-108">Go to Common > Setup > User options.</span></span>
2. <span data-ttu-id="4e95a-109">Klicka på fliken Arbetsflöde.</span><span class="sxs-lookup"><span data-stu-id="4e95a-109">Click the Workflow tab.</span></span>
    * <span data-ttu-id="4e95a-110">Kontrollera att avsnittet för Delegering expanderas.</span><span class="sxs-lookup"><span data-stu-id="4e95a-110">Make sure the Delegation section is expanded.</span></span>    <span data-ttu-id="4e95a-111">Om du vill konfigurera systemet för att automatiskt delegera dina arbetsuppgifter till andra användare, måste du skapa delegeringsregler som anger när vissa typer av arbetsuppgifter delegeras.</span><span class="sxs-lookup"><span data-stu-id="4e95a-111">To configure the system to automatically delegate your work items to other users, you must create delegation rules, which specify when certain types of work items are delegated.</span></span> <span data-ttu-id="4e95a-112">Följ dessa steg för att skapa en ny delegeringsregel.</span><span class="sxs-lookup"><span data-stu-id="4e95a-112">Follow these steps to create a delegation rule.</span></span>  
3. <span data-ttu-id="4e95a-113">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="4e95a-113">Click Add.</span></span>
4. <span data-ttu-id="4e95a-114">Markera ett alternativ i fältet Omfattning.</span><span class="sxs-lookup"><span data-stu-id="4e95a-114">In the Scope field, select an option.</span></span>
    * <span data-ttu-id="4e95a-115">Alla – Delegera alla arbetsuppgifter som har tilldelats dig.</span><span class="sxs-lookup"><span data-stu-id="4e95a-115">All – Delegate all work items that are assigned to you.</span></span>    <span data-ttu-id="4e95a-116">Modul – Delegera enbart de arbetsuppgifter som är relaterade till en specifik arbetsflödestyp.</span><span class="sxs-lookup"><span data-stu-id="4e95a-116">Module – Delegate only the work items that are related to a specific type of workflow.</span></span> <span data-ttu-id="4e95a-117">Om du väljer det här alternativet måste du välja typ av arbetsflöde i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="4e95a-117">If you select this option, you must select the type of workflow in the Name field.</span></span>    <span data-ttu-id="4e95a-118">Arbetsflöde – Delegera enbart de arbetsuppgifter som är relaterade till en specifik typ av arbetsflöde.</span><span class="sxs-lookup"><span data-stu-id="4e95a-118">Workflow – Delegate only the work items that are related to a specific workflow.</span></span> <span data-ttu-id="4e95a-119">Om du väljer det här alternativet måste du välja typen av arbetsflöde i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="4e95a-119">If you select this option, you must select the workflow in the Name field.</span></span>  
5. <span data-ttu-id="4e95a-120">Markera den användare som du vill delegera arbetsuppgifterna till i fältet Delegera.</span><span class="sxs-lookup"><span data-stu-id="4e95a-120">In the Delegate field, select the user to delegate the work items to.</span></span>
    * <span data-ttu-id="4e95a-121">Använd fälten Startdatum/-tid och Slutdatum/-tid när du vill att arbetsuppgifterna ska delegeras automatiskt.</span><span class="sxs-lookup"><span data-stu-id="4e95a-121">Use the Start date/time and End date/time fields to specify when you want the work items to be automatically delegated.</span></span>  
6. <span data-ttu-id="4e95a-122">Ange datum och tid i fältet Startdatum/-tid.</span><span class="sxs-lookup"><span data-stu-id="4e95a-122">In the Start date/time field, enter a date and time.</span></span>
7. <span data-ttu-id="4e95a-123">Ange datum och tid i fältet Slutdatum/-tid.</span><span class="sxs-lookup"><span data-stu-id="4e95a-123">In the End date/time field, enter a date and time.</span></span>
8. <span data-ttu-id="4e95a-124">Aktivera delegeringsregeln genom att markera kryssrutan Aktiverad.</span><span class="sxs-lookup"><span data-stu-id="4e95a-124">Select the Enabled check box to activate the delegation rule.</span></span>
    * <span data-ttu-id="4e95a-125">Om du har valt Modul som Omfattning måste du välja modulen i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="4e95a-125">If you selected Module as the Scope, then you must select the module in the Name field.</span></span>    <span data-ttu-id="4e95a-126">Om du har valt Arbetsflöde som Omfattning måste du välja specifikt arbetsflöde att delegera i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="4e95a-126">If you selected Workflow as the Scope, then you must select the specific workflow to delegate in the Name field.</span></span>  
9. <span data-ttu-id="4e95a-127">Ange en kommentar som förklarar varför du delegerar arbetsuppgifterna i fältet Kommentar.</span><span class="sxs-lookup"><span data-stu-id="4e95a-127">In the Comment field, enter a comment that explains why you are delegating the work items.</span></span>


