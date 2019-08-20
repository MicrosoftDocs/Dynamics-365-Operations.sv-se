---
title: Skapa nya användare
description: Användare är interna medarbetare i organisationen, eller externa kunder och leverantörer, som behöver åtkomst till systemet för att utföra sitt arbete.
author: maertenm
manager: AnnBe
ms.date: 08/29/2018
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
ms.openlocfilehash: 89e492ef5030dd28020094152259b615010aa676
ms.sourcegitcommit: 16bfa0fd08feec1647829630401ce62ce2ffa1a4
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/02/2019
ms.locfileid: "1851321"
---
# <a name="create-new-users"></a><span data-ttu-id="5f567-103">Skapa nya användare</span><span class="sxs-lookup"><span data-stu-id="5f567-103">Create new users</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="5f567-104">Användare är interna medarbetare i organisationen, eller externa kunder och leverantörer, som behöver åtkomst till systemet för att utföra sitt arbete.</span><span class="sxs-lookup"><span data-stu-id="5f567-104">Users are internal employees of your organization, or external customers and vendors, who require access to the system to perform their jobs.</span></span> <span data-ttu-id="5f567-105">Systemadministratörer kan slutföra den här proceduren för att lägga till användare i systemet.</span><span class="sxs-lookup"><span data-stu-id="5f567-105">System administrators can complete this procedure to add users to the system.</span></span> <span data-ttu-id="5f567-106">Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF.</span><span class="sxs-lookup"><span data-stu-id="5f567-106">The demo data company used to create this procedure is USMF.</span></span> 


## <a name="add-a-new-user"></a><span data-ttu-id="5f567-107">Lägg till ny användare</span><span class="sxs-lookup"><span data-stu-id="5f567-107">Add a new user</span></span>
1. <span data-ttu-id="5f567-108">Gå till Systemadministration > Användare > Användare.</span><span class="sxs-lookup"><span data-stu-id="5f567-108">Go to System administration > Users > Users.</span></span>
2. <span data-ttu-id="5f567-109">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="5f567-109">Click New.</span></span>
3. <span data-ttu-id="5f567-110">Skriv ett värde i fältet Användar-id.</span><span class="sxs-lookup"><span data-stu-id="5f567-110">In the User ID field, type a value.</span></span>
    * <span data-ttu-id="5f567-111">Ange en unik identifierare för användaren.</span><span class="sxs-lookup"><span data-stu-id="5f567-111">Enter a unique identifier for the user.</span></span> <span data-ttu-id="5f567-112">Ett användar-id krävs.</span><span class="sxs-lookup"><span data-stu-id="5f567-112">A user ID is required.</span></span>  
4. <span data-ttu-id="5f567-113">Skriv ett värde i fältet Användarnamn.</span><span class="sxs-lookup"><span data-stu-id="5f567-113">In the User name field, type a value.</span></span>
    * <span data-ttu-id="5f567-114">Ange användarens namn.</span><span class="sxs-lookup"><span data-stu-id="5f567-114">Enter the user's name.</span></span>  
5. <span data-ttu-id="5f567-115">Skriv ett värde i fältet Domän.</span><span class="sxs-lookup"><span data-stu-id="5f567-115">In the Domain field, type a value.</span></span>
    * <span data-ttu-id="5f567-116">Ange användarens domän.</span><span class="sxs-lookup"><span data-stu-id="5f567-116">Enter the user's domain.</span></span>  
6. <span data-ttu-id="5f567-117">Ange ett värde i fältet Alias.</span><span class="sxs-lookup"><span data-stu-id="5f567-117">In the Alias field, type a value.</span></span>
    * <span data-ttu-id="5f567-118">Ange användarens alias.</span><span class="sxs-lookup"><span data-stu-id="5f567-118">Enter the user's alias.</span></span>  
7. <span data-ttu-id="5f567-119">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Företag.</span><span class="sxs-lookup"><span data-stu-id="5f567-119">In the Company field, click the drop-down button to open the lookup.</span></span>
8. <span data-ttu-id="5f567-120">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="5f567-120">In the list, find and select the desired record.</span></span>
9. <span data-ttu-id="5f567-121">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="5f567-121">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="5f567-122">Välj användarens företag</span><span class="sxs-lookup"><span data-stu-id="5f567-122">Select the user's company</span></span>  
10. <span data-ttu-id="5f567-123">Klicka på Tilldela roller.</span><span class="sxs-lookup"><span data-stu-id="5f567-123">Click Assign roles.</span></span>
11. <span data-ttu-id="5f567-124">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="5f567-124">In the list, find and select the desired record.</span></span>
12. <span data-ttu-id="5f567-125">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="5f567-125">Click OK.</span></span>
13. <span data-ttu-id="5f567-126">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="5f567-126">Click Save.</span></span>

## <a name="import-users"></a><span data-ttu-id="5f567-127">Importera användare</span><span class="sxs-lookup"><span data-stu-id="5f567-127">Import users</span></span>
1. <span data-ttu-id="5f567-128">Klicka på Importera användare.</span><span class="sxs-lookup"><span data-stu-id="5f567-128">Click Import users.</span></span>
2. <span data-ttu-id="5f567-129">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="5f567-129">In the list, mark the selected row.</span></span>
3. <span data-ttu-id="5f567-130">Klicka på Importera användare.</span><span class="sxs-lookup"><span data-stu-id="5f567-130">Click Import users.</span></span>
4. <span data-ttu-id="5f567-131">Klicka på Stäng.</span><span class="sxs-lookup"><span data-stu-id="5f567-131">Click Close.</span></span>

