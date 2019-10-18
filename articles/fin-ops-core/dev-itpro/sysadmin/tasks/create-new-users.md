---
title: Skapa nya användare
description: Användare är interna medarbetare i organisationen, eller externa kunder och leverantörer, som behöver åtkomst till systemet för att utföra sitt arbete.
author: maertenm
manager: AnnBe
ms.date: 08/30/2019
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
ms.openlocfilehash: 4a5635f96132b2e52227b569e7e480fa55e82d61
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/27/2019
ms.locfileid: "2180954"
---
# <a name="create-new-users"></a><span data-ttu-id="97e87-103">Skapa nya användare</span><span class="sxs-lookup"><span data-stu-id="97e87-103">Create new users</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]
[!include [banner](../../includes/preview-banner.md)]

<span data-ttu-id="97e87-104">Användare är interna medarbetare i organisationen, eller externa kunder och leverantörer, som behöver åtkomst till systemet för att utföra sitt arbete.</span><span class="sxs-lookup"><span data-stu-id="97e87-104">Users are internal employees of your organization, or external customers and vendors, who require access to the system to do their jobs.</span></span>

## <a name="associate-a-user-with-a-license-new-license-types-only"></a><span data-ttu-id="97e87-105">Associera en användare med en licens (endast nya licenstyper)</span><span class="sxs-lookup"><span data-stu-id="97e87-105">Associate a user with a license (new license types only)</span></span>
<span data-ttu-id="97e87-106">För kunder som finns på en av de nya licenstyperna som lades till i oktober 2019, måste användarna associeras med en licens.</span><span class="sxs-lookup"><span data-stu-id="97e87-106">For customers who are on one of the new license types that were added in October 2019, users must be associated with a license.</span></span> <span data-ttu-id="97e87-107">Användare som associeras med en licens läggs automatiskt till som systemanvändare som inte har några roller första gången de loggar in.</span><span class="sxs-lookup"><span data-stu-id="97e87-107">Users who are associated with a license are automatically added as system users who have no roles the first time that they sign in.</span></span> <span data-ttu-id="97e87-108">Användare som inte är kopplade till någon licens får ett varningsmeddelande.</span><span class="sxs-lookup"><span data-stu-id="97e87-108">Users who aren't associated with a licence receive a warning message.</span></span>

<span data-ttu-id="97e87-109">Systemadministratörer kan [tilldela licenser till användare](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?view=o365-worldwide) i [Microsoft 365 administrationscenter](https://docs.microsoft.com/office365/admin/admin-overview/about-the-admin-center?view=o365-worldwide)</span><span class="sxs-lookup"><span data-stu-id="97e87-109">System admins can [assign licenses to users](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?view=o365-worldwide) in the [Microsoft 365 admin center](https://docs.microsoft.com/office365/admin/admin-overview/about-the-admin-center?view=o365-worldwide).</span></span>

## <a name="add-a-new-user"></a><span data-ttu-id="97e87-110">Lägg till ny användare</span><span class="sxs-lookup"><span data-stu-id="97e87-110">Add a new user</span></span>
1. <span data-ttu-id="97e87-111">Gå till **Systemadministration \> Användare \> Användare**.</span><span class="sxs-lookup"><span data-stu-id="97e87-111">Go to **System administration \> Users \> Users**.</span></span>
2. <span data-ttu-id="97e87-112">Klicka på **Ny** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="97e87-112">On the Action Pane, select **New**.</span></span>
3. <span data-ttu-id="97e87-113">I fältet **Användar-ID** anger du en unik identifierare för användaren.</span><span class="sxs-lookup"><span data-stu-id="97e87-113">In the **User ID** field, enter a unique identifier for the user.</span></span> <span data-ttu-id="97e87-114">Ett användar-id krävs.</span><span class="sxs-lookup"><span data-stu-id="97e87-114">A user ID is required.</span></span>  
4. <span data-ttu-id="97e87-115">Ange användarens namn fältet **Användarnamn**.</span><span class="sxs-lookup"><span data-stu-id="97e87-115">In the **User name** field, enter the user's name.</span></span>  
5. <span data-ttu-id="97e87-116">Ange användarens domän i fältet **Domän**.</span><span class="sxs-lookup"><span data-stu-id="97e87-116">In the **Domain** field, enter the user's domain.</span></span>  
6. <span data-ttu-id="97e87-117">Ange användarens alias i fältet **alias**.</span><span class="sxs-lookup"><span data-stu-id="97e87-117">In the **Alias** field, enter the user's alias.</span></span>  
7. <span data-ttu-id="97e87-118">Välj önskat företag i fältet **Företag**.</span><span class="sxs-lookup"><span data-stu-id="97e87-118">In the **Company** field, select the desired company.</span></span> 
8. <span data-ttu-id="97e87-119">På snabbfliken **användarens roller** väljer du **tilldela roller** för att [tilldela användare till säkerhetsroller](assign-users-security-roles.md)</span><span class="sxs-lookup"><span data-stu-id="97e87-119">On the **User's roles** FastTab, select **Assign roles** to [assign users to security roles](assign-users-security-roles.md)</span></span>
9. <span data-ttu-id="97e87-120">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="97e87-120">Select **OK**.</span></span>
10. <span data-ttu-id="97e87-121">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="97e87-121">Select **Save**.</span></span>

## <a name="import-users"></a><span data-ttu-id="97e87-122">Importera användare</span><span class="sxs-lookup"><span data-stu-id="97e87-122">Import users</span></span>
1. <span data-ttu-id="97e87-123">Välj **Importera användare** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="97e87-123">On the Action Pane, select **Import users**.</span></span>
2. <span data-ttu-id="97e87-124">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="97e87-124">In the list, mark the selected row.</span></span>
3. <span data-ttu-id="97e87-125">Välj **Importera användare**.</span><span class="sxs-lookup"><span data-stu-id="97e87-125">Select **Import users**.</span></span>
4. <span data-ttu-id="97e87-126">Välj **Nära**.</span><span class="sxs-lookup"><span data-stu-id="97e87-126">Select **Close**.</span></span>

