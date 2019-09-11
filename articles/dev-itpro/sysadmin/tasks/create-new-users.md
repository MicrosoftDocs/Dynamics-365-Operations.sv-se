---
title: Skapa nya användare
description: Användare är interna medarbetare i organisationen, eller externa kunder och leverantörer, som behöver åtkomst till systemet för att utföra sitt arbete.
author: maertenm
manager: AnnBe
ms.date: 07/01/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysUserManagement, SysDataAreaSelectLookup, SysSecUserAddRoles, SysUserMSODSUserImport
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: maertenm
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a542ece226750330262e0c44427e5654fa4f6369
ms.sourcegitcommit: cbcf344b3b552acca56c3e27606eac7f2f124afe
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/22/2019
ms.locfileid: "1916494"
---
# <a name="create-new-users"></a><span data-ttu-id="4790e-103">Skapa nya användare</span><span class="sxs-lookup"><span data-stu-id="4790e-103">Create new users</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="4790e-104">Användare är interna medarbetare i organisationen, eller externa kunder och leverantörer, som behöver åtkomst till systemet för att utföra sitt arbete.</span><span class="sxs-lookup"><span data-stu-id="4790e-104">Users are internal employees of your organization, or external customers and vendors, who require access to the system to perform their jobs.</span></span> <span data-ttu-id="4790e-105">Systemadministratörer kan slutföra den här proceduren för att lägga till användare i systemet.</span><span class="sxs-lookup"><span data-stu-id="4790e-105">System administrators can complete this procedure to add users to the system.</span></span> <span data-ttu-id="4790e-106">Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF.</span><span class="sxs-lookup"><span data-stu-id="4790e-106">The demo data company used to create this procedure is USMF.</span></span> 


## <a name="add-a-new-user"></a><span data-ttu-id="4790e-107">Lägg till ny användare</span><span class="sxs-lookup"><span data-stu-id="4790e-107">Add a new user</span></span>
1. <span data-ttu-id="4790e-108">Gå till **Navigeringsfönster > Moduler > Systemadministration > Användare > Användare**.</span><span class="sxs-lookup"><span data-stu-id="4790e-108">Go to **Navigation pane > Modules > System administration > Users > Users**.</span></span>
2. <span data-ttu-id="4790e-109">Klicka på **Nytt** i **Åtgärdsfönstret**.</span><span class="sxs-lookup"><span data-stu-id="4790e-109">On the **Action pane**, click **New**.</span></span>
3. <span data-ttu-id="4790e-110">Skriv ett värde i fältet **Användar-id**.</span><span class="sxs-lookup"><span data-stu-id="4790e-110">In the **User ID** field, type a value.</span></span> <span data-ttu-id="4790e-111">Ange en unik identifierare för användaren.</span><span class="sxs-lookup"><span data-stu-id="4790e-111">Enter a unique identifier for the user.</span></span> <span data-ttu-id="4790e-112">Ett användar-id krävs.</span><span class="sxs-lookup"><span data-stu-id="4790e-112">A user ID is required.</span></span>  
4. <span data-ttu-id="4790e-113">Skriv ett värde i fältet **Användarnamn.**</span><span class="sxs-lookup"><span data-stu-id="4790e-113">In the **User name** field, type a value.</span></span> <span data-ttu-id="4790e-114">Ange användarens namn.</span><span class="sxs-lookup"><span data-stu-id="4790e-114">Enter the user's name.</span></span>  
5. <span data-ttu-id="4790e-115">Skriv ett värde i fältet **Domän**.</span><span class="sxs-lookup"><span data-stu-id="4790e-115">In the **Domain** field, type a value.</span></span> <span data-ttu-id="4790e-116">Ange användarens domän.</span><span class="sxs-lookup"><span data-stu-id="4790e-116">Enter the user's domain.</span></span>  
6. <span data-ttu-id="4790e-117">Ange ett värde i fältet **Alias**.</span><span class="sxs-lookup"><span data-stu-id="4790e-117">In the **Alias** field, type a value.</span></span> <span data-ttu-id="4790e-118">Ange användarens alias.</span><span class="sxs-lookup"><span data-stu-id="4790e-118">Enter the user's alias.</span></span>  
7. <span data-ttu-id="4790e-119">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet **Företag**.</span><span class="sxs-lookup"><span data-stu-id="4790e-119">In the **Company** field, click the drop-down button to open the lookup.</span></span>
8. <span data-ttu-id="4790e-120">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="4790e-120">In the list, find and select the desired record.</span></span> 
9. <span data-ttu-id="4790e-121">I avsnittet **Användarens roller** klicka på **Tilldela roller**.</span><span class="sxs-lookup"><span data-stu-id="4790e-121">In the **User's roles** section, click **Assign roles**.</span></span>
10. <span data-ttu-id="4790e-122">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="4790e-122">In the list, find and select the desired record.</span></span>
11. <span data-ttu-id="4790e-123">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="4790e-123">Click **OK**.</span></span>
12. <span data-ttu-id="4790e-124">Klicka på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="4790e-124">Click **Save**.</span></span>

## <a name="import-users"></a><span data-ttu-id="4790e-125">Importera användare</span><span class="sxs-lookup"><span data-stu-id="4790e-125">Import users</span></span>
1. <span data-ttu-id="4790e-126">Klicka på **Importera användare** i **åtgärdsfönstret**.</span><span class="sxs-lookup"><span data-stu-id="4790e-126">On the **Action pane**, click **Import users**.</span></span>
2. <span data-ttu-id="4790e-127">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="4790e-127">In the list, mark the selected row.</span></span>
3. <span data-ttu-id="4790e-128">Klicka på **Importera användare**.</span><span class="sxs-lookup"><span data-stu-id="4790e-128">Click **Import users**.</span></span>
4. <span data-ttu-id="4790e-129">Klicka på **Stäng**.</span><span class="sxs-lookup"><span data-stu-id="4790e-129">Click **Close**.</span></span>

