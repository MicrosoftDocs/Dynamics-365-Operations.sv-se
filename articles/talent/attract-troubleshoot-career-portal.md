---
title: Attract-användare kan inte söka jobb från karriärportalen
description: I det här avsnittet beskrivs felsökning av problem där Attract-användare inte kan söka jobb från karriärportalen.
author: andreabichsel
manager: AnnBe
ms.date: 09/23/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-09-23
ms.dyn365.ops.version: Platform update 24
ms.openlocfilehash: e1d72bef6d8bbe15e27326f66341915ba44a09b4
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "4462556"
---
# <a name="attract-users-cant-apply-for-jobs-from-career-portal"></a><span data-ttu-id="1a3eb-103">Attract-användare kan inte söka jobb från karriärportalen</span><span class="sxs-lookup"><span data-stu-id="1a3eb-103">Attract users can't apply for jobs from career portal</span></span>

[!include [banner](includes/banner.md)]

## <a name="issue"></a><span data-ttu-id="1a3eb-104">Utleverans</span><span class="sxs-lookup"><span data-stu-id="1a3eb-104">Issue</span></span>

<span data-ttu-id="1a3eb-105">Attract-användare kan inte söka jobb från karriärportalen.</span><span class="sxs-lookup"><span data-stu-id="1a3eb-105">Attract users can't apply for jobs from the career portal.</span></span> <span data-ttu-id="1a3eb-106">När de försöker att söka ett jobb som har skapats i Dynamics 365 Talent: Attract läser webbläsaren in sidan kontinuerligt och utför inte åtgärden.</span><span class="sxs-lookup"><span data-stu-id="1a3eb-106">When they try to apply for a job that was created in Dynamics 365 Talent: Attract, the browser loads the page continuously and doesn't complete the action.</span></span>

## <a name="cause"></a><span data-ttu-id="1a3eb-107">Orsak</span><span class="sxs-lookup"><span data-stu-id="1a3eb-107">Cause</span></span>

<span data-ttu-id="1a3eb-108">Det här problemet uppstår när talangrelationsgruppen inte har användarrollen Talang.</span><span class="sxs-lookup"><span data-stu-id="1a3eb-108">This problem occurs when the Talent Relationship Team doesn't have the Talent user role.</span></span>

## <a name="resolution"></a><span data-ttu-id="1a3eb-109">Upplösning</span><span class="sxs-lookup"><span data-stu-id="1a3eb-109">Resolution</span></span>

<span data-ttu-id="1a3eb-110">Tilldela användarrollen Talang till talangrelationsgruppen.</span><span class="sxs-lookup"><span data-stu-id="1a3eb-110">Assign the Talent user role to the Talent Relationship Team.</span></span>

1. <span data-ttu-id="1a3eb-111">Logga in till [Power Platform administrationscentret](https://admin.powerplatform.microsoft.com) med någon av följande administratörsuppgifter:</span><span class="sxs-lookup"><span data-stu-id="1a3eb-111">Sign in to the [Power Platform admin center](https://admin.powerplatform.microsoft.com) with any of the following admin credentials:</span></span>

   - <span data-ttu-id="1a3eb-112">Dynamics 365-administratör</span><span class="sxs-lookup"><span data-stu-id="1a3eb-112">Dynamics 365 admin</span></span>
   - <span data-ttu-id="1a3eb-113">Global administratör</span><span class="sxs-lookup"><span data-stu-id="1a3eb-113">Global admin</span></span>
   - <span data-ttu-id="1a3eb-114">Power Platform-administratör</span><span class="sxs-lookup"><span data-stu-id="1a3eb-114">Power Platform admin</span></span>

2. <span data-ttu-id="1a3eb-115">I navigeringsfönstret väljer du **Miljöer** och sedan den miljö där användarrollen Talang ska tilldelas talangrelationsgruppen.</span><span class="sxs-lookup"><span data-stu-id="1a3eb-115">In the navigation pane, select **Environments**, and then select the environment in which to assign the Talent user role to the Talent Relationship Team.</span></span>

   ![Välj miljö](./media/attract-troubleshoot-career-portal-select-environment.png)

3. <span data-ttu-id="1a3eb-117">I fönstret **Miljöer** väljer du **miljöns URL** och loggar in på miljöns administratörsportal (till exempel https:<orgname>.crm.dynamics.com).</span><span class="sxs-lookup"><span data-stu-id="1a3eb-117">In the **Environments** pane, select the **Environment URL** and sign in to the environment's admin portal (for example, https:<orgname>.crm.dynamics.com).</span></span>

4. <span data-ttu-id="1a3eb-118">Välj **Inställningar** väljer du **System** och sedan **Säkerhet**.</span><span class="sxs-lookup"><span data-stu-id="1a3eb-118">Select **Settings**, select **System**, and then select **Security**.</span></span>

   ![Navigera till Säkerhet](./media/attract-troubleshoot-career-portal-security.png)

5. <span data-ttu-id="1a3eb-120">Välj **Team**.</span><span class="sxs-lookup"><span data-stu-id="1a3eb-120">Select **Teams**.</span></span>

   ![Välj Team](./media/attract-troubleshoot-career-portal-security-teams.png)

6. <span data-ttu-id="1a3eb-122">Sök efter **Talangrelationsgrupp** i sökrutan och välj sedan teamet från sökresultaten.</span><span class="sxs-lookup"><span data-stu-id="1a3eb-122">Search for **Talent Relationship Team** in the search box, and then select the team from the search results.</span></span>

7. <span data-ttu-id="1a3eb-123">Välj **HANTERA ROLLER** från menyfliken.</span><span class="sxs-lookup"><span data-stu-id="1a3eb-123">Select **MANAGE ROLES** from the ribbon.</span></span>

8. <span data-ttu-id="1a3eb-124">I dialogrutan **Hantera teamroller** väljer du **Talanganvändare** från listan över tillgängliga roller och väljer sedan **OK** för att tillämpa rollen.</span><span class="sxs-lookup"><span data-stu-id="1a3eb-124">In the **Manage Team Roles** dialog, select **Talent user** from the list of available roles, and then select **OK** to apply the role.</span></span>

   ![Tillämpa roll](./media/attract-troubleshoot-career-portal-apply-role.png)

9. <span data-ttu-id="1a3eb-126">Testa ändringarna:</span><span class="sxs-lookup"><span data-stu-id="1a3eb-126">Test your changes:</span></span>

   1. <span data-ttu-id="1a3eb-127">Logga in på karriärportalen från ett nytt webbläsarfönster.</span><span class="sxs-lookup"><span data-stu-id="1a3eb-127">Sign in to the career portal from a new browser window.</span></span>
   2. <span data-ttu-id="1a3eb-128">Sök jobbet från karriärportalen.</span><span class="sxs-lookup"><span data-stu-id="1a3eb-128">Apply for the job from the career portal.</span></span> 