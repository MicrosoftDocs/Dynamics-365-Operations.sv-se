---
title: "Ställ in säkerhet för kostnadsredovisningsanalys för Power BI"
description: "Det här avsnittet beskriver hur du kan sprida säkerhet för åtkomstnivå i kostnadsredovisning till säkerhet för radnivå i Microsoft Power BI. Dessa funktioner hjälper till att säkerställa att användare bara ser Power BI-data som de har beviljats åtkomst till."
author: YuyuScheller
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Operations, UnifiedOperations
ms.custom: 270294
ms.assetid: 3a7ba8b0-ac57-4159-9cd8-4308f6021f36
ms.search.region: Global
ms.author: yuyus
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 04f8cb1a6375be9371bca2af7e4044392ce7322b
ms.openlocfilehash: 12fd8e11211b701304f9f4a68ff31f3b42e3e8ee
ms.contentlocale: sv-se
ms.lasthandoff: 08/02/2017

---

# <a name="set-up-security-for-the-cost-accounting-analysis-power-bi-content"></a><span data-ttu-id="b8785-104">Ställ in säkerhet för kostnadsredovisningsanalys för Power BI</span><span class="sxs-lookup"><span data-stu-id="b8785-104">Set up security for the Cost accounting analysis Power BI content</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="b8785-105">Det här avsnittet beskriver hur du kan sprida säkerhet för åtkomstnivå i kostnadsredovisning till säkerhet för radnivå i Microsoft Power BI.</span><span class="sxs-lookup"><span data-stu-id="b8785-105">This topic explains how you can propagate the access-level security in Cost accounting to row-level security in Microsoft Power BI.</span></span> <span data-ttu-id="b8785-106">Dessa funktioner hjälper till att säkerställa att användare bara ser Power BI-data som de har beviljats åtkomst till.</span><span class="sxs-lookup"><span data-stu-id="b8785-106">This functionality helps guarantee that users see only Power BI data that they are granted access to.</span></span>

<a name="overview"></a><span data-ttu-id="b8785-107">Översikt</span><span class="sxs-lookup"><span data-stu-id="b8785-107">Overview</span></span>
--------

<span data-ttu-id="b8785-108">**Kostnadsredovisningsanalys** Microsoft Power BI-innehållet använder Power BI säkerhet på radnivå för att begränsa en användares åtkomst.</span><span class="sxs-lookup"><span data-stu-id="b8785-108">The **Cost accounting analysis** Microsoft Power BI content uses Power BI row-level security to limit a user's access.</span></span> <span data-ttu-id="b8785-109">Säkerheten baseras på den organisationshierarki på åtkomstnivå som har ställts in i parametrar för kostnadsredovisning.</span><span class="sxs-lookup"><span data-stu-id="b8785-109">Security is based on the access-level organizational hierarchy that is set up in the Cost accounting parameters.</span></span> <span data-ttu-id="b8785-110">Mer information om **Kostnadsredovisningsanalys** för Power BI-innehåll finns i [Kostnadsredovisningsanalys för Power BI-innehåll](cost-accounting-analysis-content-pack.md).</span><span class="sxs-lookup"><span data-stu-id="b8785-110">For more information about the **Cost accounting analysis** Power BI content, see [Cost accounting analysis Power BI content](cost-accounting-analysis-content-pack.md).</span></span>

## <a name="setup"></a><span data-ttu-id="b8785-111">Inställningar</span><span class="sxs-lookup"><span data-stu-id="b8785-111">Setup</span></span>
<span data-ttu-id="b8785-112">Om du vill sprida säkerhet på åtkomstnivå till Power BI måste Power BI-innehållet följa dessa steg.</span><span class="sxs-lookup"><span data-stu-id="b8785-112">To propagate access-level security to Power BI, the owner of the Power BI content must follow these steps.</span></span> <span data-ttu-id="b8785-113">**Obs!** Användare som publicerar **Kostnadsredovisningsanalys** för Power BI-innehåll blir automatiskt ägare.</span><span class="sxs-lookup"><span data-stu-id="b8785-113">**Note:** The user who publishes the **Cost accounting analysis** Power BI content automatically becomes the owner.</span></span> <span data-ttu-id="b8785-114">Endast en ägare kan ställa in säkerhet i Power BI.</span><span class="sxs-lookup"><span data-stu-id="b8785-114">Only an owner can set up security in Power BI.</span></span> <span data-ttu-id="b8785-115">Dessutom, tills ägaren lägger till andra användare i PowerBI.com kan ingen förutom ägaren se några data i **Kostnadsredovisningsanalys** för Power BI-innehåll.</span><span class="sxs-lookup"><span data-stu-id="b8785-115">Additionally, until an owner adds other users on PowerBI.com, no one except the owner can see any data in the **Cost accounting analysis** Power BI content.</span></span>

1.  <span data-ttu-id="b8785-116">Publicera definitionsfilen till Power BI.</span><span class="sxs-lookup"><span data-stu-id="b8785-116">Publish the definition file to Power BI.</span></span>
2.  <span data-ttu-id="b8785-117">Logga in på PowerBI.com.</span><span class="sxs-lookup"><span data-stu-id="b8785-117">Sign in to PowerBI.com.</span></span>
3.  <span data-ttu-id="b8785-118">Hitta datamängden för **Kostnadsredovisningsanalys** för Power BI content.</span><span class="sxs-lookup"><span data-stu-id="b8785-118">Find the dataset for the **Cost accounting analysis** Power BI content.</span></span>
4.  <span data-ttu-id="b8785-119">Öppna säkerhetssidan.</span><span class="sxs-lookup"><span data-stu-id="b8785-119">Open the security page.</span></span> 

    ![Öppna säkerhetssidan](./media/CA-picture-1.png)

5.  <span data-ttu-id="b8785-121">Rollen **Kostnadsobjektcontroller** har redan skapats.</span><span class="sxs-lookup"><span data-stu-id="b8785-121">The **Cost object controller** role is already created.</span></span> <span data-ttu-id="b8785-122">Lägg till andra medlemmar som ingår i organisationshierarkin på åtkomstnivå för kostnadsredovisning.</span><span class="sxs-lookup"><span data-stu-id="b8785-122">Add other members who are part of the Cost accounting access-level organizational hierarchy.</span></span> 

    ![Lägga till medlemmar](./media/CA-picture-2.png)

<span data-ttu-id="b8785-124">Användare som läggs till i rollen **Kostnadsobjektcontroller** kommer endast att se de data som de får tillstånd att se enligt definitionen i organisationshierarkin på åtkomstnivå för kostnadsredovisning.</span><span class="sxs-lookup"><span data-stu-id="b8785-124">Users who are added to the **Cost object controller** role will see only the data that they are allowed to see, according to the definition in the Cost accounting access-level organizational hierarchy.</span></span> <span data-ttu-id="b8785-125">**Obs!** Säkerhet på radnivå som gäller paneler och rapporter i Microsoft Dynamics 365 for Finance and Operations som är inbäddade från Power BI.</span><span class="sxs-lookup"><span data-stu-id="b8785-125">**Note:** Row-level security applies to tiles and reports in Microsoft Dynamics 365 for Finance and Operations that are embedded from Power BI.</span></span>

## <a name="updating-security"></a><span data-ttu-id="b8785-126">Uppdatera säkerhet</span><span class="sxs-lookup"><span data-stu-id="b8785-126">Updating security</span></span>
<span data-ttu-id="b8785-127">Om uppdateringar görs av säkerhet på åtkomstnivå i kostnadsredovisningen och du vill att Power BI ska återspegla dessa uppdateringarna, måste du uppdatera enhetsbutiken **Kostnadsredovisningsanalys** för Power BI-innehåll.</span><span class="sxs-lookup"><span data-stu-id="b8785-127">If updates are made to access-level security in Cost accounting, and you want Power BI to reflect those updates, you must update the entity store for the **Cost accounting analysis** Power BI content.</span></span> <span data-ttu-id="b8785-128">När du har slutfört uppdateringen av enhetsbutiken från Finance and Operations måste du uppdatera artefakterna på PowerBI.com.</span><span class="sxs-lookup"><span data-stu-id="b8785-128">After you complete the entity store update from Finance and Operations, you must update the artifacts on PowerBI.com.</span></span> <span data-ttu-id="b8785-129">Mer information om hur du gör en uppdatering av enhetsbutik finns [Uppdatera enhetsbutik](power-bi-integration-entity-store.md#update-entity-store).</span><span class="sxs-lookup"><span data-stu-id="b8785-129">For more information about how to do an entity store update, see [Update entity store](power-bi-integration-entity-store.md#update-entity-store).</span></span> <span data-ttu-id="b8785-130">Ägaren av **Kostnadsredovisningsanalys** för Power BI-innehåll måste också göra en uppdatering av enhetsbutiken om nya användare beviljas åtkomst till organisationshierarkin.</span><span class="sxs-lookup"><span data-stu-id="b8785-130">The owner of the **Cost accounting analysis** Power BI content must also do an entity store update if new users are granted access to the organizational hierarchy.</span></span> <span data-ttu-id="b8785-131">Dessutom måste ägaren lägga till nya användare till rollen **Kostnadsobjektcontroller** i PowerBI.com, så att säkerhet på radnivå tillämpas för dem.</span><span class="sxs-lookup"><span data-stu-id="b8785-131">Additionally, the owner must add the new users to the **Cost object controller** role on PowerBI.com, so that row-level security is applied for them.</span></span>

## <a name="disabling-security"></a><span data-ttu-id="b8785-132">Inaktivera säkerhet</span><span class="sxs-lookup"><span data-stu-id="b8785-132">Disabling security</span></span>
<span data-ttu-id="b8785-133">Vi utgår från att din organisation vill begränsa dataåtkomst.</span><span class="sxs-lookup"><span data-stu-id="b8785-133">We assume that your organization wants to restrict data access.</span></span> <span data-ttu-id="b8785-134">Om säkerhetsparametrarna av någon anledning är inaktiverade när du kör kostnadsredovisning måste ägaren istället lägga till rollen **Kostnadsredovisare** i Power BI.</span><span class="sxs-lookup"><span data-stu-id="b8785-134">If, for some reason, the security parameters are disabled when you run Cost accounting, the owner must add users to the **Cost accountant** role in Power BI instead.</span></span> <span data-ttu-id="b8785-135">Om du ändrar säkerhet från ett aktiverat tillstånd till inaktiverat är det en bra idé att ta bort användare från rolleb **Kostnadsobjektcontroller**.</span><span class="sxs-lookup"><span data-stu-id="b8785-135">If you change security from an enabled state to a disabled state, it’s a good idea to remove users from the **Cost object controller** role.</span></span> <span data-ttu-id="b8785-136">Och tvärtom när du aktiverar säkerhet igen.</span><span class="sxs-lookup"><span data-stu-id="b8785-136">And vice versa if you re-enable security.</span></span> <span data-ttu-id="b8785-137">Användare kan tillhöra båda rollerna.</span><span class="sxs-lookup"><span data-stu-id="b8785-137">Users can belong to both roles.</span></span> <span data-ttu-id="b8785-138">Gemensam åtkomst är unionen av båda rollerna.</span><span class="sxs-lookup"><span data-stu-id="b8785-138">Joint access is the union of both roles.</span></span> <span data-ttu-id="b8785-139">I fallet **Kostnadsredovisningsanalys** för Power BI-innehåll får användare som har gemensam åtkomst obegränsad dataåtkomst.</span><span class="sxs-lookup"><span data-stu-id="b8785-139">In the case of the **Cost accounting analysis** Power BI content, users who have joint access have unrestricted data access.</span></span> <span data-ttu-id="b8785-140">Om målet är att använda begränsad åtkomst får användarna endast tilldelas rollen **Kostnadsobjektcontroller**.</span><span class="sxs-lookup"><span data-stu-id="b8785-140">If your goal is to apply restricted access, users must be assigned only to the **Cost object controller** role.</span></span> <span data-ttu-id="b8785-141">Dessa säkerhetsuppdateringar på radnivå börjar gälla omedelbart.</span><span class="sxs-lookup"><span data-stu-id="b8785-141">These row-level security updates take effect immediately.</span></span> <span data-ttu-id="b8785-142">Berörda användare bör uppdatera sina webbläsare.</span><span class="sxs-lookup"><span data-stu-id="b8785-142">Affected users should refresh their browsers.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="b8785-143">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="b8785-143">Additional resources</span></span>
<span data-ttu-id="b8785-144">Mer information om säkerhet för Power BI på radnivå finns i [Hantera säkerheten av din modell i Power BI](https://powerbi.microsoft.com/en-us/documentation/powerbi-admin-rls/#manage-security-on-your-model).</span><span class="sxs-lookup"><span data-stu-id="b8785-144">To learn more about Power BI row-level security, see [Manage security on your model in Power BI](https://powerbi.microsoft.com/en-us/documentation/powerbi-admin-rls/#manage-security-on-your-model).</span></span>




