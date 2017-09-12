--- 
title: "Tilldela användare till säkerhetsroller"
description: "Om du vill komma åt Microsoft Dynamics 365 for Finance and Operations, Enterprise edition, måste användarna ha tilldelats säkerhetsroller."
author: maertenm
manager: AnnBe
ms.date: 06/07/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: sericks
ms.search.scope: Operations
ms.search.region: Global
ms.author: maertenm
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 551048af26f46d334c562d1968963aed262a5e03
ms.contentlocale: sv-se
ms.lasthandoff: 08/29/2017

---
# <a name="assign-users-to-security-roles"></a><span data-ttu-id="3a1d2-103">Tilldela användare till säkerhetsroller</span><span class="sxs-lookup"><span data-stu-id="3a1d2-103">Assign users to security roles</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="3a1d2-104">Om du vill komma åt Microsoft Dynamics 365 for Finance and Operations, Enterprise edition, måste användarna ha tilldelats säkerhetsroller.</span><span class="sxs-lookup"><span data-stu-id="3a1d2-104">To access Microsoft Dynamics 365 for Finance and Operations, Enterprise edition, users must be assigned to security roles.</span></span> <span data-ttu-id="3a1d2-105">I den här proceduren förklaras hur systemadministratörer kan tilldela användarna roller automatiskt, baserat på affärsdata.</span><span class="sxs-lookup"><span data-stu-id="3a1d2-105">This procedure explains how system administrators can assign users to roles automatically, based on business data.</span></span> <span data-ttu-id="3a1d2-106">Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF.</span><span class="sxs-lookup"><span data-stu-id="3a1d2-106">The demo data company used to create this procedure is USMF.</span></span>


## <a name="automatically-assign-users-to-roles"></a><span data-ttu-id="3a1d2-107">Tilldela användare automatiskt till roller</span><span class="sxs-lookup"><span data-stu-id="3a1d2-107">Automatically assign users to roles</span></span>
1. <span data-ttu-id="3a1d2-108">Gå till systemadministrationen > Säkerhet > Tilldela användare till roller.</span><span class="sxs-lookup"><span data-stu-id="3a1d2-108">Go to System administration > Security > Assign users to roles.</span></span>
2. <span data-ttu-id="3a1d2-109">Välj "Redovisningsansvarig" i trädet.</span><span class="sxs-lookup"><span data-stu-id="3a1d2-109">In the tree, select 'Accounting supervisor'.</span></span>
    * <span data-ttu-id="3a1d2-110">Välj den roll som du vill använda till att konfigurera regeln.</span><span class="sxs-lookup"><span data-stu-id="3a1d2-110">Select the role that you want to configure the rule for.</span></span> <span data-ttu-id="3a1d2-111">Välj Redovisningsansvarig i det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="3a1d2-111">In this example, select Accounting supervisor.</span></span>  
3. <span data-ttu-id="3a1d2-112">Klicka på Lägg till regel för att öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="3a1d2-112">Click Add rule to open the drop dialog.</span></span>
4. <span data-ttu-id="3a1d2-113">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="3a1d2-113">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="3a1d2-114">Välj frågan som ska användas till den här regeln.</span><span class="sxs-lookup"><span data-stu-id="3a1d2-114">Select the query to use for this rule.</span></span>  
5. <span data-ttu-id="3a1d2-115">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="3a1d2-115">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="3a1d2-116">Klicka på Redigera fråga.</span><span class="sxs-lookup"><span data-stu-id="3a1d2-116">Click Edit query.</span></span>
    * <span data-ttu-id="3a1d2-117">Redigera frågan, om det behövs.</span><span class="sxs-lookup"><span data-stu-id="3a1d2-117">Edit the query, as needed.</span></span>  
7. <span data-ttu-id="3a1d2-118">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="3a1d2-118">Click OK.</span></span>

## <a name="exclude-users-from-automatic-role-assignment"></a><span data-ttu-id="3a1d2-119">Exkludera användare från automatisk rolltilldelning</span><span class="sxs-lookup"><span data-stu-id="3a1d2-119">Exclude users from automatic role assignment</span></span>
1. <span data-ttu-id="3a1d2-120">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="3a1d2-120">Close the page.</span></span>
2. <span data-ttu-id="3a1d2-121">Gå till systemadministrationen > Säkerhet > Tilldela användare till roller.</span><span class="sxs-lookup"><span data-stu-id="3a1d2-121">Go to System administration > Security > Assign users to roles.</span></span>
3. <span data-ttu-id="3a1d2-122">Välj "Redovisningsansvarig" i trädet.</span><span class="sxs-lookup"><span data-stu-id="3a1d2-122">In the tree, select 'Accounting supervisor'.</span></span>
    * <span data-ttu-id="3a1d2-123">Välj en roll.</span><span class="sxs-lookup"><span data-stu-id="3a1d2-123">Select a role.</span></span> <span data-ttu-id="3a1d2-124">Välj Redovisningsansvarig för det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="3a1d2-124">For this example, select Accounting supervisor.</span></span>  
4. <span data-ttu-id="3a1d2-125">Klicka på Tilldela/exkludera användare manuellt.</span><span class="sxs-lookup"><span data-stu-id="3a1d2-125">Click Manually assign / exclude users.</span></span>
5. <span data-ttu-id="3a1d2-126">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="3a1d2-126">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="3a1d2-127">Välj en användare.</span><span class="sxs-lookup"><span data-stu-id="3a1d2-127">Select a user.</span></span>  
6. <span data-ttu-id="3a1d2-128">Klicka på Exkludera från roll.</span><span class="sxs-lookup"><span data-stu-id="3a1d2-128">Click Exclude from role.</span></span>
    * <span data-ttu-id="3a1d2-129">Klicka på Exkludera från roll om du vill exkludera den valda användaren från rollen.</span><span class="sxs-lookup"><span data-stu-id="3a1d2-129">Click Exclude from role to exclude the selected users from the role.</span></span> <span data-ttu-id="3a1d2-130">Markera de användare som du vill ta bort exkluderingar för och klicka sedan på Återställ status om du vill ta bort exkluderingar.</span><span class="sxs-lookup"><span data-stu-id="3a1d2-130">To remove exclusions, select the users that you want to remove exclusions for, and then click Reset status.</span></span> <span data-ttu-id="3a1d2-131">När du raderar en exkludering genom att återställa användarens status, kommer användarens roll att tilldelas igen automatiskt.</span><span class="sxs-lookup"><span data-stu-id="3a1d2-131">When you remove an exclusion by resetting the user’s status, the user’s role is again assigned automatically.</span></span> <span data-ttu-id="3a1d2-132">Men användaren tilldelas inte omedelbart rollen eller exkluderas från rollen när du återställer statusen.</span><span class="sxs-lookup"><span data-stu-id="3a1d2-132">However, the user is not immediately assigned to the role or excluded from the role when you reset the status.</span></span> <span data-ttu-id="3a1d2-133">Istället tilldelas användaren antingen rollen eller tas bort från rollen nästa gång som reglerna för automatisk rolltilldelning körs.</span><span class="sxs-lookup"><span data-stu-id="3a1d2-133">Instead, the user is either assigned to the role or removed from the role the next time that the rules for automatic role assignment are run.</span></span>  


