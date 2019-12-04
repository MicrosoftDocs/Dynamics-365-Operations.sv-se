---
title: Tilldela användare till säkerhetsroller
description: Om du vill komma åt Finance and Operations-appar måste användarna ha tilldelats säkerhetsroller.
author: ChrisGarty
manager: AnnBe
ms.date: 11/14/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysSecRolesEditUsers, SysSecAssignmentQueryLookup, SysQueryForm, SysSecRoleExcludeUsers
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: cgarty
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e4f4ef4535de9e371829c2d86d4fdc1400510c7b
ms.sourcegitcommit: 6aa74f66f1abd3a7977050a5339b0b17e62ff053
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/15/2019
ms.locfileid: "2808006"
---
# <a name="assign-users-to-security-roles"></a><span data-ttu-id="cc2b5-103">Tilldela användare till säkerhetsroller</span><span class="sxs-lookup"><span data-stu-id="cc2b5-103">Assign users to security roles</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="cc2b5-104">För att kunna använda något annat än vanliga funktioner måste användarna tilldelas till säkerhetsroller.</span><span class="sxs-lookup"><span data-stu-id="cc2b5-104">To use anything other than common capabilities, users must be assigned to security roles.</span></span> <span data-ttu-id="cc2b5-105">I den här proceduren förklaras hur systemadministratörer kan tilldela användarna roller automatiskt, baserat på affärsdata.</span><span class="sxs-lookup"><span data-stu-id="cc2b5-105">This procedure explains how system administrators can automatically assign users to roles, based on business data.</span></span> 

## <a name="automatically-assign-users-to-roles"></a><span data-ttu-id="cc2b5-106">Tilldela användare automatiskt till roller</span><span class="sxs-lookup"><span data-stu-id="cc2b5-106">Automatically assign users to roles</span></span>
1. <span data-ttu-id="cc2b5-107">Gå till **Navigeringsfönster > Moduler > Systemadministration > Säkerhet > Tilldela användare till roller**.</span><span class="sxs-lookup"><span data-stu-id="cc2b5-107">Go to **Navigation pane > Modules > System administration > Security > Assign users to roles**.</span></span>
2. <span data-ttu-id="cc2b5-108">Välj "Redovisningsansvarig" i trädet.</span><span class="sxs-lookup"><span data-stu-id="cc2b5-108">In the tree, select 'Accounting supervisor'.</span></span> <span data-ttu-id="cc2b5-109">Välj den roll som du vill använda till att konfigurera regeln.</span><span class="sxs-lookup"><span data-stu-id="cc2b5-109">Select the role that you want to configure the rule for.</span></span> <span data-ttu-id="cc2b5-110">Välj Redovisningsansvarig i det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="cc2b5-110">In this example, select Accounting supervisor.</span></span> 
3. <span data-ttu-id="cc2b5-111">Klicka på **Lägg till regel** för att öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="cc2b5-111">Click **Add rule** to open the drop dialog.</span></span>
4. <span data-ttu-id="cc2b5-112">Sök efter och markera önskad post från listan **Välj en frågan**.</span><span class="sxs-lookup"><span data-stu-id="cc2b5-112">In the **Select a query**list, find and select the desired record.</span></span> <span data-ttu-id="cc2b5-113">Välj frågan som ska användas till den här regeln.</span><span class="sxs-lookup"><span data-stu-id="cc2b5-113">Select the query to use for this rule.</span></span>  
5. <span data-ttu-id="cc2b5-114">Klicka på länken på den valda raden i listan **Namn på medlemskapsregel**.</span><span class="sxs-lookup"><span data-stu-id="cc2b5-114">In the **Membership rule name** list, click the link in the selected row.</span></span>
6. <span data-ttu-id="cc2b5-115">Klicka på **Redigera fråga**.</span><span class="sxs-lookup"><span data-stu-id="cc2b5-115">Click **Edit query**.</span></span> <span data-ttu-id="cc2b5-116">Redigera frågan, om det behövs.</span><span class="sxs-lookup"><span data-stu-id="cc2b5-116">Edit the query, as needed.</span></span>  
7. <span data-ttu-id="cc2b5-117">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="cc2b5-117">Click **OK**.</span></span>
8. <span data-ttu-id="cc2b5-118">Klicka på **Kör automatisk rolltilldelning**.</span><span class="sxs-lookup"><span data-stu-id="cc2b5-118">Click **Run automatic role assignment**.</span></span>
9. <span data-ttu-id="cc2b5-119">Gå till **Navigeringsfönstret > Moduler > Systemadministration > Användare > Användare** (helst på en separat flik i webbläsaren).</span><span class="sxs-lookup"><span data-stu-id="cc2b5-119">Go to **Navigation pane > Modules > System administration > Users > Users** (ideally in a separate browser tab).</span></span>
10. <span data-ttu-id="cc2b5-120">Granska roller tilldelade olika användare för att bekräfta att rolltilldelningsfrågan var korrekt.</span><span class="sxs-lookup"><span data-stu-id="cc2b5-120">Review the roles assigned to various users to confirm that the role assignment query was correct.</span></span> <span data-ttu-id="cc2b5-121">Justera och kör om om det behövs.</span><span class="sxs-lookup"><span data-stu-id="cc2b5-121">Adjust and re-run if needed.</span></span>

## <a name="exclude-users-from-automatic-role-assignment"></a><span data-ttu-id="cc2b5-122">Exkludera användare från automatisk rolltilldelning</span><span class="sxs-lookup"><span data-stu-id="cc2b5-122">Exclude users from automatic role assignment</span></span>
1. <span data-ttu-id="cc2b5-123">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="cc2b5-123">Close the page.</span></span>
2. <span data-ttu-id="cc2b5-124">Gå till **Navigeringsfönster > Moduler > Systemadministration > Säkerhet > Tilldela användare till roller**.</span><span class="sxs-lookup"><span data-stu-id="cc2b5-124">Go to **Navigation pane > Modules > System administration > Security > Assign users to roles**.</span></span>
3. <span data-ttu-id="cc2b5-125">Välj "Redovisningsansvarig" i trädet.</span><span class="sxs-lookup"><span data-stu-id="cc2b5-125">In the tree, select 'Accounting supervisor'.</span></span> <span data-ttu-id="cc2b5-126">Välj en roll.</span><span class="sxs-lookup"><span data-stu-id="cc2b5-126">Select a role.</span></span> <span data-ttu-id="cc2b5-127">Välj Redovisningsansvarig för det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="cc2b5-127">For this example, select Accounting supervisor.</span></span>  
4. <span data-ttu-id="cc2b5-128">I menyn **Användare som är tilldelade till rollen**, välj **Tilldela/exkludera användare manuellt**.</span><span class="sxs-lookup"><span data-stu-id="cc2b5-128">In the **Users assigned to role** menu, select **Manually assign / exclude users**.</span></span>
5. <span data-ttu-id="cc2b5-129">Markera den markerade raden på listan **Tilldela användare till eller exkludera användare från roll**.</span><span class="sxs-lookup"><span data-stu-id="cc2b5-129">In the **Assign users to or exclude users from role** list, mark the selected row.</span></span> <span data-ttu-id="cc2b5-130">Välj en användare.</span><span class="sxs-lookup"><span data-stu-id="cc2b5-130">Select a user.</span></span>  
6. <span data-ttu-id="cc2b5-131">På **Åtgärdsfönstret**, välj **Exkludera från roll**.</span><span class="sxs-lookup"><span data-stu-id="cc2b5-131">On the **Action pane**, select **Exclude from role**.</span></span>
    
    <span data-ttu-id="cc2b5-132">Klicka på **Exkludera från roll** om du vill exkludera den valda användaren från rollen.</span><span class="sxs-lookup"><span data-stu-id="cc2b5-132">Click **Exclude from role** to exclude the selected users from the role.</span></span> <span data-ttu-id="cc2b5-133">Markera de användare som du vill ta bort exkluderingar för och klicka sedan på **Återställ status** om du vill ta bort exkluderingar.</span><span class="sxs-lookup"><span data-stu-id="cc2b5-133">To remove exclusions, select the users that you want to remove exclusions for, and then click **Reset status**.</span></span> <span data-ttu-id="cc2b5-134">När du raderar en exkludering genom att återställa användarens status, kommer användarens roll att tilldelas igen automatiskt.</span><span class="sxs-lookup"><span data-stu-id="cc2b5-134">When you remove an exclusion by resetting the user’s status, the user’s role is again assigned automatically.</span></span> <span data-ttu-id="cc2b5-135">Men användaren tilldelas inte omedelbart rollen eller exkluderas från rollen när du återställer statusen.</span><span class="sxs-lookup"><span data-stu-id="cc2b5-135">However, the user is not immediately assigned to the role or excluded from the role when you reset the status.</span></span> <span data-ttu-id="cc2b5-136">Istället tilldelas användaren antingen rollen eller tas bort från rollen nästa gång som reglerna för automatisk rolltilldelning körs.</span><span class="sxs-lookup"><span data-stu-id="cc2b5-136">Instead, the user is either assigned to the role or removed from the role the next time that the rules for automatic role assignment are run.</span></span>  
