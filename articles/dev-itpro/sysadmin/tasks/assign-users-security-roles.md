---
title: Tilldela användare till säkerhetsroller
description: För att öppna Microsoft Microsoft Dynamics 365 for Finance and Operations måste användaren tilldelas säkerhetsroller.
author: maertenm
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysSecRolesEditUsers, SysSecAssignmentQueryLookup, SysQueryForm, SysSecRoleExcludeUsers
audience: Application User
ms.reviewer: margoc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: maertenm
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 55cb085bb5170aa4894a2240a12f6ca451b922fb
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2019
ms.locfileid: "349962"
---
# <a name="assign-users-to-security-roles"></a><span data-ttu-id="1c2a3-103">Tilldela användare till säkerhetsroller</span><span class="sxs-lookup"><span data-stu-id="1c2a3-103">Assign users to security roles</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="1c2a3-104">För att öppna Microsoft Microsoft Dynamics 365 for Finance and Operations måste användaren tilldelas säkerhetsroller.</span><span class="sxs-lookup"><span data-stu-id="1c2a3-104">To access Microsoft Dynamics 365 for Finance and Operations, Enterprise edition, users must be assigned to security roles.</span></span> <span data-ttu-id="1c2a3-105">I den här proceduren förklaras hur systemadministratörer kan tilldela användarna roller automatiskt, baserat på affärsdata.</span><span class="sxs-lookup"><span data-stu-id="1c2a3-105">This procedure explains how system administrators can assign users to roles automatically, based on business data.</span></span> <span data-ttu-id="1c2a3-106">Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF.</span><span class="sxs-lookup"><span data-stu-id="1c2a3-106">The demo data company used to create this procedure is USMF.</span></span>


## <a name="automatically-assign-users-to-roles"></a><span data-ttu-id="1c2a3-107">Tilldela användare automatiskt till roller</span><span class="sxs-lookup"><span data-stu-id="1c2a3-107">Automatically assign users to roles</span></span>
1. <span data-ttu-id="1c2a3-108">Gå till systemadministrationen > Säkerhet > Tilldela användare till roller.</span><span class="sxs-lookup"><span data-stu-id="1c2a3-108">Go to System administration > Security > Assign users to roles.</span></span>
2. <span data-ttu-id="1c2a3-109">Välj "Redovisningsansvarig" i trädet.</span><span class="sxs-lookup"><span data-stu-id="1c2a3-109">In the tree, select 'Accounting supervisor'.</span></span>
    * <span data-ttu-id="1c2a3-110">Välj den roll som du vill använda till att konfigurera regeln.</span><span class="sxs-lookup"><span data-stu-id="1c2a3-110">Select the role that you want to configure the rule for.</span></span> <span data-ttu-id="1c2a3-111">Välj Redovisningsansvarig i det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="1c2a3-111">In this example, select Accounting supervisor.</span></span>  
3. <span data-ttu-id="1c2a3-112">Klicka på Lägg till regel för att öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="1c2a3-112">Click Add rule to open the drop dialog.</span></span>
4. <span data-ttu-id="1c2a3-113">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="1c2a3-113">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="1c2a3-114">Välj frågan som ska användas till den här regeln.</span><span class="sxs-lookup"><span data-stu-id="1c2a3-114">Select the query to use for this rule.</span></span>  
5. <span data-ttu-id="1c2a3-115">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="1c2a3-115">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="1c2a3-116">Klicka på Redigera fråga.</span><span class="sxs-lookup"><span data-stu-id="1c2a3-116">Click Edit query.</span></span>
    * <span data-ttu-id="1c2a3-117">Redigera frågan, om det behövs.</span><span class="sxs-lookup"><span data-stu-id="1c2a3-117">Edit the query, as needed.</span></span>  
7. <span data-ttu-id="1c2a3-118">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="1c2a3-118">Click OK.</span></span>

## <a name="exclude-users-from-automatic-role-assignment"></a><span data-ttu-id="1c2a3-119">Exkludera användare från automatisk rolltilldelning</span><span class="sxs-lookup"><span data-stu-id="1c2a3-119">Exclude users from automatic role assignment</span></span>
1. <span data-ttu-id="1c2a3-120">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="1c2a3-120">Close the page.</span></span>
2. <span data-ttu-id="1c2a3-121">Gå till systemadministrationen > Säkerhet > Tilldela användare till roller.</span><span class="sxs-lookup"><span data-stu-id="1c2a3-121">Go to System administration > Security > Assign users to roles.</span></span>
3. <span data-ttu-id="1c2a3-122">Välj "Redovisningsansvarig" i trädet.</span><span class="sxs-lookup"><span data-stu-id="1c2a3-122">In the tree, select 'Accounting supervisor'.</span></span>
    * <span data-ttu-id="1c2a3-123">Välj en roll.</span><span class="sxs-lookup"><span data-stu-id="1c2a3-123">Select a role.</span></span> <span data-ttu-id="1c2a3-124">Välj Redovisningsansvarig för det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="1c2a3-124">For this example, select Accounting supervisor.</span></span>  
4. <span data-ttu-id="1c2a3-125">Klicka på Tilldela/exkludera användare manuellt.</span><span class="sxs-lookup"><span data-stu-id="1c2a3-125">Click Manually assign / exclude users.</span></span>
5. <span data-ttu-id="1c2a3-126">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="1c2a3-126">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="1c2a3-127">Välj en användare.</span><span class="sxs-lookup"><span data-stu-id="1c2a3-127">Select a user.</span></span>  
6. <span data-ttu-id="1c2a3-128">Klicka på Exkludera från roll.</span><span class="sxs-lookup"><span data-stu-id="1c2a3-128">Click Exclude from role.</span></span>
    * <span data-ttu-id="1c2a3-129">Klicka på Exkludera från roll om du vill exkludera den valda användaren från rollen.</span><span class="sxs-lookup"><span data-stu-id="1c2a3-129">Click Exclude from role to exclude the selected users from the role.</span></span> <span data-ttu-id="1c2a3-130">Markera de användare som du vill ta bort exkluderingar för och klicka sedan på Återställ status om du vill ta bort exkluderingar.</span><span class="sxs-lookup"><span data-stu-id="1c2a3-130">To remove exclusions, select the users that you want to remove exclusions for, and then click Reset status.</span></span> <span data-ttu-id="1c2a3-131">När du raderar en exkludering genom att återställa användarens status, kommer användarens roll att tilldelas igen automatiskt.</span><span class="sxs-lookup"><span data-stu-id="1c2a3-131">When you remove an exclusion by resetting the user’s status, the user’s role is again assigned automatically.</span></span> <span data-ttu-id="1c2a3-132">Men användaren tilldelas inte omedelbart rollen eller exkluderas från rollen när du återställer statusen.</span><span class="sxs-lookup"><span data-stu-id="1c2a3-132">However, the user is not immediately assigned to the role or excluded from the role when you reset the status.</span></span> <span data-ttu-id="1c2a3-133">Istället tilldelas användaren antingen rollen eller tas bort från rollen nästa gång som reglerna för automatisk rolltilldelning körs.</span><span class="sxs-lookup"><span data-stu-id="1c2a3-133">Instead, the user is either assigned to the role or removed from the role the next time that the rules for automatic role assignment are run.</span></span>  

