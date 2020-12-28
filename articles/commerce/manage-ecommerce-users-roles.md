---
title: Hantera näthandelsanvändare och roller
description: I det här avsnittet beskrivs hur du ger användarna åtkomst till redigeringsmiljön för din Microsoft Dynamics 365 Commerce-webbplats.
author: bicyclingfool
manager: AnnBe
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: stuharg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 9a1f9abae20d0f2e71790a3b27337338dc042b52
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "4415720"
---
# <a name="manage-e-commerce-users-and-roles"></a><span data-ttu-id="b7f3c-103">Hantera näthandelsanvändare och roller</span><span class="sxs-lookup"><span data-stu-id="b7f3c-103">Manage e-Commerce users and roles</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="b7f3c-104">I det här avsnittet beskrivs hur du ger användarna åtkomst till redigeringsmiljön för din Microsoft Dynamics 365 Commerce-webbplats.</span><span class="sxs-lookup"><span data-stu-id="b7f3c-104">This topic explains how to grant users access to the authoring environment for your Microsoft Dynamics 365 Commerce site.</span></span>

<span data-ttu-id="b7f3c-105">Om du vill kontrollera användaråtkomst och bevilja användare behörighet att utföra särskilda uppgifter, använder du säkerhetsgrupper för webbplatsens redigeringsmiljö som du skapar i Microsoft Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="b7f3c-105">To help control user access and grant users permission to perform specific tasks, the site authoring environment uses security groups that you create in Microsoft Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="b7f3c-106">Du tilldelar först en ny eller befintlig säkerhetsgrupp från Azure AD till varje roll i redigeringsmiljön.</span><span class="sxs-lookup"><span data-stu-id="b7f3c-106">You first assign a new or existing security group from Azure AD to each role in the authoring environment.</span></span> <span data-ttu-id="b7f3c-107">Du kan sedan bevilja eller återkalla behörigheter för enskilda användare genom att antingen lägga till dessa användare i en lämplig säkerhetsgrupp eller ta bort dem från en säkerhetsgrupp.</span><span class="sxs-lookup"><span data-stu-id="b7f3c-107">You then grant or revoke permissions for individual users by either adding those users to an appropriate security group or removing them from a security group.</span></span>

## <a name="overview-of-roles-in-the-authoring-environment"></a><span data-ttu-id="b7f3c-108">Översikt över roller i redigeringsmiljön</span><span class="sxs-lookup"><span data-stu-id="b7f3c-108">Overview of roles in the authoring environment</span></span>

<span data-ttu-id="b7f3c-109">Dynamics 365 for Commerce redigeringsmiljön stöder följande roller.</span><span class="sxs-lookup"><span data-stu-id="b7f3c-109">The Dynamics 365 for Commerce authoring environment supports the following roles.</span></span>

| <span data-ttu-id="b7f3c-110">Roll</span><span class="sxs-lookup"><span data-stu-id="b7f3c-110">Role</span></span>                 | <span data-ttu-id="b7f3c-111">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="b7f3c-111">Description</span></span> |
|----------------------|-------------|
| <span data-ttu-id="b7f3c-112">Systemadministratör</span><span class="sxs-lookup"><span data-stu-id="b7f3c-112">System Administrator</span></span> | <span data-ttu-id="b7f3c-113">Användare med den här rollen har alla behörigheter för alla verktyg och för alla omdömen och recensioner.</span><span class="sxs-lookup"><span data-stu-id="b7f3c-113">Users who have this role have all privileges for all tools, and for all ratings and reviews.</span></span> <span data-ttu-id="b7f3c-114">De kan också skapa webbplatser.</span><span class="sxs-lookup"><span data-stu-id="b7f3c-114">They can also create sites.</span></span> |
| <span data-ttu-id="b7f3c-115">Administratör</span><span class="sxs-lookup"><span data-stu-id="b7f3c-115">Administrator</span></span>   | <span data-ttu-id="b7f3c-116">Användare med den här rollen har alla behörigheter för alla verktyg och RnR i en given webbplatsstruktur.</span><span class="sxs-lookup"><span data-stu-id="b7f3c-116">Users who have this role have all privileges for all tools and RnR in a given site structure.</span></span> |
| <span data-ttu-id="b7f3c-117">Webbtillverkare</span><span class="sxs-lookup"><span data-stu-id="b7f3c-117">Web Producer</span></span>         | <span data-ttu-id="b7f3c-118">Användare med den här rollen kan skapa sidor, fragment och mallar, ladda upp och hantera tillgångar och utöka produkter och kategorier.</span><span class="sxs-lookup"><span data-stu-id="b7f3c-118">Users who have this role can create pages, fragments and templates, upload and manage assets, and enrich products and categories.</span></span> |
| <span data-ttu-id="b7f3c-119">Läsare</span><span class="sxs-lookup"><span data-stu-id="b7f3c-119">Reader</span></span>               | <span data-ttu-id="b7f3c-120">Användare med denna roll kan visa sidor, mallar, resurser, fragment, layouter och inställningar, men de kan inte göra ändringar.</span><span class="sxs-lookup"><span data-stu-id="b7f3c-120">Users who have this role can view pages, templates, assets, fragments, layouts and settings, but may not make changes.</span></span> |
| <span data-ttu-id="b7f3c-121">RnR moderator</span><span class="sxs-lookup"><span data-stu-id="b7f3c-121">RnR Moderator</span></span>        | <span data-ttu-id="b7f3c-122">Användare med denna roll kan moderera produktrecensioner.</span><span class="sxs-lookup"><span data-stu-id="b7f3c-122">Users who have this role can moderate product reviews.</span></span> |

## <a name="system-administrator-role"></a><span data-ttu-id="b7f3c-123">Systemadministratörroll</span><span class="sxs-lookup"><span data-stu-id="b7f3c-123">System Administrator role</span></span>

<span data-ttu-id="b7f3c-124">När du etablerar Dynamics 365 Commerce i Microsoft Dynamics Lifecycle Services (LCS)-miljön uppmanas du att ange en säkerhetsgrupp för rollen **Systemadministratör**.</span><span class="sxs-lookup"><span data-stu-id="b7f3c-124">When you provision Dynamics 365 Commerce in the Microsoft Dynamics Lifecycle Services (LCS) environment, you're asked to provide a security group for the **System Administrator** role.</span></span> <span data-ttu-id="b7f3c-125">Den här rollen används sedan automatiskt på alla webbplatser som du skapar i den miljö som du konfigurerar.</span><span class="sxs-lookup"><span data-stu-id="b7f3c-125">This role is then automatically applied to all sites that you create in the environment that you're configuring.</span></span> <span data-ttu-id="b7f3c-126">Säkerhetsgruppen för den här rollen kan bara uppdateras i LCS.</span><span class="sxs-lookup"><span data-stu-id="b7f3c-126">The security group for this role can be updated only in LCS.</span></span> <span data-ttu-id="b7f3c-127">På sidan **webbplatsadministration** för alla webbplatser visas den som skrivskyddad och endast i informationssyfte.</span><span class="sxs-lookup"><span data-stu-id="b7f3c-127">On the **Site Administration** page for all sites, it appears as read-only and is for informational purposes only.</span></span>

## <a name="administrator-role"></a><span data-ttu-id="b7f3c-128">Administratörsrollen</span><span class="sxs-lookup"><span data-stu-id="b7f3c-128">Administrator role</span></span>

<span data-ttu-id="b7f3c-129">När du skapar en ny webbplats i Commerce uppmanas du att ange en säkerhetsgrupp för rollen **administratör**.</span><span class="sxs-lookup"><span data-stu-id="b7f3c-129">When you create a new site in Commerce, you're asked to provide a security group for the **Administrator** role.</span></span> <span data-ttu-id="b7f3c-130">Se tabellen tidigare i det här avsnittet för en översikt över de behörigheter som den här rollen beviljar.</span><span class="sxs-lookup"><span data-stu-id="b7f3c-130">See the table earlier in this topic for an overview of the permissions that this role grants.</span></span>

## <a name="add-or-update-security-groups"></a><span data-ttu-id="b7f3c-131">Lägg till eller uppdatera säkerhetsgrupper</span><span class="sxs-lookup"><span data-stu-id="b7f3c-131">Add or update security groups</span></span>

<span data-ttu-id="b7f3c-132">När webbplatsen har skapats kan bara användare som finns i de säkerhetsgrupper som är kopplade till rollerna **systemadministratör** och **administratör** få tillgång till redigeringsmiljön för den webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="b7f3c-132">After your site is created, only users who are in the security groups that are associated with the **System Administrator** and **Administrator** roles can access the authoring environment for that site.</span></span> <span data-ttu-id="b7f3c-133">Om du vill tilldela användare till rollerna **Webbtillverkare**, **RnR moderator** och **Läsare** måste du tilldela säkerhetsgrupper till dessa roller.</span><span class="sxs-lookup"><span data-stu-id="b7f3c-133">To assign users to the **Web Producer**, **RnR Moderator**, and **Reader** roles, you must assign security groups to those roles.</span></span> <span data-ttu-id="b7f3c-134">Om du vill lägga till en säkerhetsgrupp till en roll, eller uppdatera en säkerhetsgrupp som för närvarande är tilldelad till en roll, följer du stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="b7f3c-134">To add a security group to a role, or to update a security group that is currently assigned to a role, follow these steps.</span></span>

1. <span data-ttu-id="b7f3c-135">Gå till den webbplats som ska uppdateras.</span><span class="sxs-lookup"><span data-stu-id="b7f3c-135">Go to the site that you want to update.</span></span>
1. <span data-ttu-id="b7f3c-136">I **webbplatshantering**, öppna sidan **säkerhet**.</span><span class="sxs-lookup"><span data-stu-id="b7f3c-136">In **Site management**, open the **Security** page.</span></span>
1. <span data-ttu-id="b7f3c-137">Välj den roll du vill ändra.</span><span class="sxs-lookup"><span data-stu-id="b7f3c-137">Select the role to modify.</span></span>
1. <span data-ttu-id="b7f3c-138">Lägg till säkerhetsgrupper i roller eller ta bort säkerhetsgrupper från roller.</span><span class="sxs-lookup"><span data-stu-id="b7f3c-138">Add security groups to roles, or remove security groups from roles.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="b7f3c-139">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="b7f3c-139">Additional resources</span></span>

[<span data-ttu-id="b7f3c-140">Lägga till skriptkod på webbsidor för att stödja telemetri</span><span class="sxs-lookup"><span data-stu-id="b7f3c-140">Add script code to site pages to support telemetry</span></span>](add-telemetry.md)

[<span data-ttu-id="b7f3c-141">Språkinformation för sökmotoroptimering (SEO) för din webbplats</span><span class="sxs-lookup"><span data-stu-id="b7f3c-141">Search engine optimization (SEO) considerations for your site</span></span>](search-engine-optimization-considerations.md)

[<span data-ttu-id="b7f3c-142">Hantera säkerhetspolicy för innehåll (CSP)</span><span class="sxs-lookup"><span data-stu-id="b7f3c-142">Manage Content Security Policy (CSP)</span></span>](manage-csp.md)
