---
title: Skapa nya användare
description: Användare är interna medarbetare i organisationen, eller externa kunder och leverantörer, som behöver åtkomst till systemet för att utföra sitt arbete.
author: maertenm
manager: AnnBe
ms.date: 02/06/2020
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
ms.openlocfilehash: 9db4b6d355d6499bce6c550b2fbe76b82cf69fd4
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/18/2020
ms.locfileid: "3143591"
---
# <a name="create-new-users"></a><span data-ttu-id="018a5-103">Skapa nya användare</span><span class="sxs-lookup"><span data-stu-id="018a5-103">Create new users</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="018a5-104">Användare är interna medarbetare i organisationen, eller externa kunder och leverantörer, som behöver åtkomst till systemet för att utföra sitt arbete.</span><span class="sxs-lookup"><span data-stu-id="018a5-104">Users are internal employees of your organization, or external customers and vendors, who require access to the system to do their jobs.</span></span>

## <a name="associate-a-user-with-a-license-new-license-types-only"></a><span data-ttu-id="018a5-105">Associera en användare med en licens (endast nya licenstyper)</span><span class="sxs-lookup"><span data-stu-id="018a5-105">Associate a user with a license (new license types only)</span></span>
<span data-ttu-id="018a5-106">För kunder som finns på en av de nya licenstyperna som lades till i oktober 2019, måste användarna associeras med en licens.</span><span class="sxs-lookup"><span data-stu-id="018a5-106">For customers who are on one of the new license types that were added in October 2019, users must be associated with a license.</span></span> <span data-ttu-id="018a5-107">Användare som associeras med en licens läggs automatiskt till som systemanvändare som inte har några roller första gången de loggar in.</span><span class="sxs-lookup"><span data-stu-id="018a5-107">Users who are associated with a license are automatically added as system users who have no roles the first time that they sign in.</span></span>

<span data-ttu-id="018a5-108">Systemadministratörer kan [tilldela licenser till användare](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?view=o365-worldwide) i [Microsoft 365 administrationscenter](https://docs.microsoft.com/office365/admin/admin-overview/about-the-admin-center?view=o365-worldwide)</span><span class="sxs-lookup"><span data-stu-id="018a5-108">System admins can [assign licenses to users](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?view=o365-worldwide) in the [Microsoft 365 admin center](https://docs.microsoft.com/office365/admin/admin-overview/about-the-admin-center?view=o365-worldwide).</span></span>

## <a name="associate-an-external-user-with-a-license-new-license-types-only"></a><span data-ttu-id="018a5-109">Associera en extern användare med en licens (endast nya licenstyper)</span><span class="sxs-lookup"><span data-stu-id="018a5-109">Associate an external user with a license (new license types only)</span></span>
<span data-ttu-id="018a5-110">Användare som är externa till innehavaren som miljön distribuerades till måste representeras i värdbaserade klientkatalogen (Azure Active Directory (Azure AD)) så att de kan tilldelas licenser.</span><span class="sxs-lookup"><span data-stu-id="018a5-110">Users external to the tenant that the environment was deployed into need to be represented in the host tenant directory (Azure Active Directory (Azure AD)) so that they can be assigned licenses.</span></span> <span data-ttu-id="018a5-111">Dessa externa användare ska läggas till i innehavaren av Azure AD som gästanvändare och sedan tilldelas de lämpliga licenserna.</span><span class="sxs-lookup"><span data-stu-id="018a5-111">Those external users should be added to the tenant in Azure AD as guest users and then assigned the appropriate licenses.</span></span> <span data-ttu-id="018a5-112">Mer information finns i [lägga till Azure Active Directory B2B samarbetsanvändare i Azure-portalen](https://docs.microsoft.com/azure/active-directory/b2b/add-users-administrator).</span><span class="sxs-lookup"><span data-stu-id="018a5-112">For more information, see [Add Azure Active Directory B2B collaboration users in the Azure portal](https://docs.microsoft.com/azure/active-directory/b2b/add-users-administrator).</span></span>

## <a name="add-a-new-user"></a><span data-ttu-id="018a5-113">Lägg till ny användare</span><span class="sxs-lookup"><span data-stu-id="018a5-113">Add a new user</span></span>
1. <span data-ttu-id="018a5-114">Gå till **Systemadministration \> Användare \> Användare**.</span><span class="sxs-lookup"><span data-stu-id="018a5-114">Go to **System administration \> Users \> Users**.</span></span>
2. <span data-ttu-id="018a5-115">Klicka på **Ny** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="018a5-115">On the Action Pane, select **New**.</span></span>
3. <span data-ttu-id="018a5-116">I fältet **Användar-ID** anger du en unik identifierare för användaren.</span><span class="sxs-lookup"><span data-stu-id="018a5-116">In the **User ID** field, enter a unique identifier for the user.</span></span> <span data-ttu-id="018a5-117">Ett användar-id krävs.</span><span class="sxs-lookup"><span data-stu-id="018a5-117">A user ID is required.</span></span>  
4. <span data-ttu-id="018a5-118">Ange användarens namn fältet **Användarnamn**.</span><span class="sxs-lookup"><span data-stu-id="018a5-118">In the **User name** field, enter the user's name.</span></span>  
5. <span data-ttu-id="018a5-119">Ange användarens domän i fältet **Domän**.</span><span class="sxs-lookup"><span data-stu-id="018a5-119">In the **Domain** field, enter the user's domain.</span></span>  
6. <span data-ttu-id="018a5-120">Ange användarens alias i fältet **alias**.</span><span class="sxs-lookup"><span data-stu-id="018a5-120">In the **Alias** field, enter the user's alias.</span></span>  
7. <span data-ttu-id="018a5-121">Välj önskat företag i fältet **Företag**.</span><span class="sxs-lookup"><span data-stu-id="018a5-121">In the **Company** field, select the desired company.</span></span> 
8. <span data-ttu-id="018a5-122">På snabbfliken **användarens roller** välj **tilldela roller** tilldela användare till säkerhetsroller.</span><span class="sxs-lookup"><span data-stu-id="018a5-122">On the **User's roles** FastTab, select **Assign roles** to assign users to security roles.</span></span> <span data-ttu-id="018a5-123">För mer information, se [Tilldela användare till säkerhetsroller](assign-users-security-roles.md).</span><span class="sxs-lookup"><span data-stu-id="018a5-123">For more information, see [Assign users to security roles](assign-users-security-roles.md).</span></span>
9. <span data-ttu-id="018a5-124">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="018a5-124">Select **OK**.</span></span>
10. <span data-ttu-id="018a5-125">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="018a5-125">Select **Save**.</span></span>

## <a name="import-users"></a><span data-ttu-id="018a5-126">Importera användare</span><span class="sxs-lookup"><span data-stu-id="018a5-126">Import users</span></span>
1. <span data-ttu-id="018a5-127">Välj **Importera användare** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="018a5-127">On the Action Pane, select **Import users**.</span></span>
2. <span data-ttu-id="018a5-128">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="018a5-128">In the list, mark the selected row.</span></span>
3. <span data-ttu-id="018a5-129">Välj **Importera användare**.</span><span class="sxs-lookup"><span data-stu-id="018a5-129">Select **Import users**.</span></span>
4. <span data-ttu-id="018a5-130">Välj **Nära**.</span><span class="sxs-lookup"><span data-stu-id="018a5-130">Select **Close**.</span></span>

