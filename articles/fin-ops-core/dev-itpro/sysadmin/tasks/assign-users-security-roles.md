---
title: Tilldela användare till säkerhetsroller
description: Om du vill komma åt Finance and Operations-appar måste användarna ha tilldelats säkerhetsroller.
author: ChrisGarty
manager: AnnBe
ms.date: 09/16/2019
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
ms.openlocfilehash: a4daecc1acd589cd1656402244e5325382a407e7
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/27/2019
ms.locfileid: "2180977"
---
# <a name="assign-users-to-security-roles"></a><span data-ttu-id="01065-103">Tilldela användare till säkerhetsroller</span><span class="sxs-lookup"><span data-stu-id="01065-103">Assign users to security roles</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="01065-104">För att kunna använda något annat än vanliga funktioner måste användarna tilldelas till säkerhetsroller.</span><span class="sxs-lookup"><span data-stu-id="01065-104">To use anything other than common capabilities, users must be assigned to security roles.</span></span> <span data-ttu-id="01065-105">I den här proceduren förklaras hur systemadministratörer kan tilldela användarna roller automatiskt, baserat på affärsdata.</span><span class="sxs-lookup"><span data-stu-id="01065-105">This procedure explains how system administrators can automatically assign users to roles, based on business data.</span></span> 

## <a name="automatically-assign-users-to-roles"></a><span data-ttu-id="01065-106">Tilldela användare automatiskt till roller</span><span class="sxs-lookup"><span data-stu-id="01065-106">Automatically assign users to roles</span></span>
1. <span data-ttu-id="01065-107">Gå till **Navigeringsfönster > Moduler > Systemadministration > Säkerhet > Tilldela användare till roller**.</span><span class="sxs-lookup"><span data-stu-id="01065-107">Go to **Navigation pane > Modules > System administration > Security > Assign users to roles**.</span></span>
2. <span data-ttu-id="01065-108">Välj "Redovisningsansvarig" i trädet.</span><span class="sxs-lookup"><span data-stu-id="01065-108">In the tree, select 'Accounting supervisor'.</span></span> <span data-ttu-id="01065-109">Välj den roll som du vill använda till att konfigurera regeln.</span><span class="sxs-lookup"><span data-stu-id="01065-109">Select the role that you want to configure the rule for.</span></span> <span data-ttu-id="01065-110">Välj Redovisningsansvarig i det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="01065-110">In this example, select Accounting supervisor.</span></span> 
3. <span data-ttu-id="01065-111">Klicka på **Lägg till regel** för att öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="01065-111">Click **Add rule** to open the drop dialog.</span></span>
4. <span data-ttu-id="01065-112">Sök efter och markera önskad post från listan **Välj en frågan**.</span><span class="sxs-lookup"><span data-stu-id="01065-112">In the **Select a query**list, find and select the desired record.</span></span> <span data-ttu-id="01065-113">Välj frågan som ska användas till den här regeln.</span><span class="sxs-lookup"><span data-stu-id="01065-113">Select the query to use for this rule.</span></span>  
5. <span data-ttu-id="01065-114">Klicka på länken på den valda raden i listan **Namn på medlemskapsregel**.</span><span class="sxs-lookup"><span data-stu-id="01065-114">In the **Membership rule name** list, click the link in the selected row.</span></span>
6. <span data-ttu-id="01065-115">Klicka på **Redigera fråga**.</span><span class="sxs-lookup"><span data-stu-id="01065-115">Click **Edit query**.</span></span> <span data-ttu-id="01065-116">Redigera frågan, om det behövs.</span><span class="sxs-lookup"><span data-stu-id="01065-116">Edit the query, as needed.</span></span>  
7. <span data-ttu-id="01065-117">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="01065-117">Click **OK**.</span></span>

## <a name="exclude-users-from-automatic-role-assignment"></a><span data-ttu-id="01065-118">Exkludera användare från automatisk rolltilldelning</span><span class="sxs-lookup"><span data-stu-id="01065-118">Exclude users from automatic role assignment</span></span>
1. <span data-ttu-id="01065-119">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="01065-119">Close the page.</span></span>
2. <span data-ttu-id="01065-120">Gå till **Navigeringsfönster > Moduler > Systemadministration > Säkerhet > Tilldela användare till roller**.</span><span class="sxs-lookup"><span data-stu-id="01065-120">Go to **Navigation pane > Modules > System administration > Security > Assign users to roles**.</span></span>
3. <span data-ttu-id="01065-121">Välj "Redovisningsansvarig" i trädet.</span><span class="sxs-lookup"><span data-stu-id="01065-121">In the tree, select 'Accounting supervisor'.</span></span> <span data-ttu-id="01065-122">Välj en roll.</span><span class="sxs-lookup"><span data-stu-id="01065-122">Select a role.</span></span> <span data-ttu-id="01065-123">Välj Redovisningsansvarig för det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="01065-123">For this example, select Accounting supervisor.</span></span>  
4. <span data-ttu-id="01065-124">I menyn **Användare som är tilldelade till rollen**, välj **Tilldela/exkludera användare manuellt**.</span><span class="sxs-lookup"><span data-stu-id="01065-124">In the **Users assigned to role** menu, select **Manually assign / exclude users**.</span></span>
5. <span data-ttu-id="01065-125">Markera den markerade raden på listan **Tilldela användare till eller exkludera användare från roll**.</span><span class="sxs-lookup"><span data-stu-id="01065-125">In the **Assign users to or exclude users from role** list, mark the selected row.</span></span> <span data-ttu-id="01065-126">Välj en användare.</span><span class="sxs-lookup"><span data-stu-id="01065-126">Select a user.</span></span>  
6. <span data-ttu-id="01065-127">På **Åtgärdsfönstret**, välj **Exkludera från roll**.</span><span class="sxs-lookup"><span data-stu-id="01065-127">On the **Action pane**, select **Exclude from role**.</span></span>
    
    <span data-ttu-id="01065-128">Klicka på **Exkludera från roll** om du vill exkludera den valda användaren från rollen.</span><span class="sxs-lookup"><span data-stu-id="01065-128">Click **Exclude from role** to exclude the selected users from the role.</span></span> <span data-ttu-id="01065-129">Markera de användare som du vill ta bort exkluderingar för och klicka sedan på **Återställ status** om du vill ta bort exkluderingar.</span><span class="sxs-lookup"><span data-stu-id="01065-129">To remove exclusions, select the users that you want to remove exclusions for, and then click **Reset status**.</span></span> <span data-ttu-id="01065-130">När du raderar en exkludering genom att återställa användarens status, kommer användarens roll att tilldelas igen automatiskt.</span><span class="sxs-lookup"><span data-stu-id="01065-130">When you remove an exclusion by resetting the user’s status, the user’s role is again assigned automatically.</span></span> <span data-ttu-id="01065-131">Men användaren tilldelas inte omedelbart rollen eller exkluderas från rollen när du återställer statusen.</span><span class="sxs-lookup"><span data-stu-id="01065-131">However, the user is not immediately assigned to the role or excluded from the role when you reset the status.</span></span> <span data-ttu-id="01065-132">Istället tilldelas användaren antingen rollen eller tas bort från rollen nästa gång som reglerna för automatisk rolltilldelning körs.</span><span class="sxs-lookup"><span data-stu-id="01065-132">Instead, the user is either assigned to the role or removed from the role the next time that the rules for automatic role assignment are run.</span></span>  
