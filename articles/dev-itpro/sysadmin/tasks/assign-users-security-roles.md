---
title: Tilldela användare till säkerhetsroller
description: För att öppna Microsoft Microsoft Dynamics 365 for Finance and Operations måste användaren tilldelas säkerhetsroller.
author: maertenm
manager: AnnBe
ms.date: 06/21/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysSecRolesEditUsers, SysSecAssignmentQueryLookup, SysQueryForm, SysSecRoleExcludeUsers
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: maertenm
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 4c0afd0f5754e59307a82af9c9700b36c31edcc4
ms.sourcegitcommit: 16bfa0fd08feec1647829630401ce62ce2ffa1a4
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/02/2019
ms.locfileid: "1851369"
---
# <a name="assign-users-to-security-roles"></a><span data-ttu-id="c8060-103">Tilldela användare till säkerhetsroller</span><span class="sxs-lookup"><span data-stu-id="c8060-103">Assign users to security roles</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="c8060-104">För att öppna Microsoft Microsoft Dynamics 365 for Finance and Operations måste användaren tilldelas säkerhetsroller.</span><span class="sxs-lookup"><span data-stu-id="c8060-104">To access Microsoft Dynamics 365 for Finance and Operations, Enterprise edition, users must be assigned to security roles.</span></span> <span data-ttu-id="c8060-105">I den här proceduren förklaras hur systemadministratörer kan tilldela användarna roller automatiskt, baserat på affärsdata.</span><span class="sxs-lookup"><span data-stu-id="c8060-105">This procedure explains how system administrators can assign users to roles automatically, based on business data.</span></span> <span data-ttu-id="c8060-106">Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF.</span><span class="sxs-lookup"><span data-stu-id="c8060-106">The demo data company used to create this procedure is USMF.</span></span>


## <a name="automatically-assign-users-to-roles"></a><span data-ttu-id="c8060-107">Tilldela användare automatiskt till roller</span><span class="sxs-lookup"><span data-stu-id="c8060-107">Automatically assign users to roles</span></span>
1. <span data-ttu-id="c8060-108">Gå till **Navigeringsfönster > Moduler > Systemadministration > Säkerhet > Tilldela användare till roller**.</span><span class="sxs-lookup"><span data-stu-id="c8060-108">Go to **Navigation pane > Modules > System administration > Security > Assign users to roles**.</span></span>
2. <span data-ttu-id="c8060-109">Välj "Redovisningsansvarig" i trädet.</span><span class="sxs-lookup"><span data-stu-id="c8060-109">In the tree, select 'Accounting supervisor'.</span></span> <span data-ttu-id="c8060-110">Välj den roll som du vill använda till att konfigurera regeln.</span><span class="sxs-lookup"><span data-stu-id="c8060-110">Select the role that you want to configure the rule for.</span></span> <span data-ttu-id="c8060-111">Välj Redovisningsansvarig i det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="c8060-111">In this example, select Accounting supervisor.</span></span> 
3. <span data-ttu-id="c8060-112">Klicka på **Lägg till regel** för att öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="c8060-112">Click **Add rule** to open the drop dialog.</span></span>
4. <span data-ttu-id="c8060-113">Sök efter och markera önskad post från listan **Välj en frågan**.</span><span class="sxs-lookup"><span data-stu-id="c8060-113">In the **Select a query**list, find and select the desired record.</span></span> <span data-ttu-id="c8060-114">Välj frågan som ska användas till den här regeln.</span><span class="sxs-lookup"><span data-stu-id="c8060-114">Select the query to use for this rule.</span></span>  
5. <span data-ttu-id="c8060-115">Klicka på länken på den valda raden i listan **Namn på medlemskapsregel**.</span><span class="sxs-lookup"><span data-stu-id="c8060-115">In the **Membership rule name** list, click the link in the selected row.</span></span>
6. <span data-ttu-id="c8060-116">Klicka på **Redigera fråga**.</span><span class="sxs-lookup"><span data-stu-id="c8060-116">Click **Edit query**.</span></span> <span data-ttu-id="c8060-117">Redigera frågan, om det behövs.</span><span class="sxs-lookup"><span data-stu-id="c8060-117">Edit the query, as needed.</span></span>  
7. <span data-ttu-id="c8060-118">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="c8060-118">Click **OK**.</span></span>

## <a name="exclude-users-from-automatic-role-assignment"></a><span data-ttu-id="c8060-119">Exkludera användare från automatisk rolltilldelning</span><span class="sxs-lookup"><span data-stu-id="c8060-119">Exclude users from automatic role assignment</span></span>
1. <span data-ttu-id="c8060-120">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="c8060-120">Close the page.</span></span>
2. <span data-ttu-id="c8060-121">Gå till **Navigeringsfönster > Moduler > Systemadministration > Säkerhet > Tilldela användare till roller**.</span><span class="sxs-lookup"><span data-stu-id="c8060-121">Go to **Navigation pane > Modules > System administration > Security > Assign users to roles**.</span></span>
3. <span data-ttu-id="c8060-122">Välj "Redovisningsansvarig" i trädet.</span><span class="sxs-lookup"><span data-stu-id="c8060-122">In the tree, select 'Accounting supervisor'.</span></span> <span data-ttu-id="c8060-123">Välj en roll.</span><span class="sxs-lookup"><span data-stu-id="c8060-123">Select a role.</span></span> <span data-ttu-id="c8060-124">Välj Redovisningsansvarig för det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="c8060-124">For this example, select Accounting supervisor.</span></span>  
4. <span data-ttu-id="c8060-125">I menyn **Användare som är tilldelade till rollen**, välj **Tilldela/exkludera användare manuellt**.</span><span class="sxs-lookup"><span data-stu-id="c8060-125">In the **Users assigned to role** menu, select **Manually assign / exclude users**.</span></span>
5. <span data-ttu-id="c8060-126">Markera den markerade raden på listan **Tilldela användare till eller exkludera användare från roll**.</span><span class="sxs-lookup"><span data-stu-id="c8060-126">In the **Assign users to or exclude users from role** list, mark the selected row.</span></span> <span data-ttu-id="c8060-127">Välj en användare.</span><span class="sxs-lookup"><span data-stu-id="c8060-127">Select a user.</span></span>  
6. <span data-ttu-id="c8060-128">På **Åtgärdsfönstret**, välj **Exkludera från roll**.</span><span class="sxs-lookup"><span data-stu-id="c8060-128">On the **Action pane**, select **Exclude from role**.</span></span>
    
    <span data-ttu-id="c8060-129">Klicka på **Exkludera från roll** om du vill exkludera den valda användaren från rollen.</span><span class="sxs-lookup"><span data-stu-id="c8060-129">Click **Exclude from role** to exclude the selected users from the role.</span></span> <span data-ttu-id="c8060-130">Markera de användare som du vill ta bort exkluderingar för och klicka sedan på **Återställ status** om du vill ta bort exkluderingar.</span><span class="sxs-lookup"><span data-stu-id="c8060-130">To remove exclusions, select the users that you want to remove exclusions for, and then click **Reset status**.</span></span> <span data-ttu-id="c8060-131">När du raderar en exkludering genom att återställa användarens status, kommer användarens roll att tilldelas igen automatiskt.</span><span class="sxs-lookup"><span data-stu-id="c8060-131">When you remove an exclusion by resetting the user’s status, the user’s role is again assigned automatically.</span></span> <span data-ttu-id="c8060-132">Men användaren tilldelas inte omedelbart rollen eller exkluderas från rollen när du återställer statusen.</span><span class="sxs-lookup"><span data-stu-id="c8060-132">However, the user is not immediately assigned to the role or excluded from the role when you reset the status.</span></span> <span data-ttu-id="c8060-133">Istället tilldelas användaren antingen rollen eller tas bort från rollen nästa gång som reglerna för automatisk rolltilldelning körs.</span><span class="sxs-lookup"><span data-stu-id="c8060-133">Instead, the user is either assigned to the role or removed from the role the next time that the rules for automatic role assignment are run.</span></span>  
