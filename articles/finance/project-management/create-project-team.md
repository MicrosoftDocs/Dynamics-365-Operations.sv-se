---
title: Skapa ett projektteam
description: Denna artikel innehåller information om hur du skapar och hanterar projektteam.
author: Yowelle
manager: AnnBe
ms.date: 09/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProjProjectsListPage
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 82022
ms.assetid: bd2fb375-84c6-428a-8e54-f0f719045898
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 834a6c0a4fcc32a955c1feddf0a6cbbb1f16b869
ms.sourcegitcommit: 241ada0945c72d769eaa70ae35aedbb6a3233fdf
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/02/2020
ms.locfileid: "3760664"
---
# <a name="create-a-project-team"></a><span data-ttu-id="1d0e8-103">Skapa ett projektteam</span><span class="sxs-lookup"><span data-stu-id="1d0e8-103">Create a project team</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="1d0e8-104">Om du vill använda de roller som redan har ställts in i ett projekt, måste en projektledare associera rollerna med projektet.</span><span class="sxs-lookup"><span data-stu-id="1d0e8-104">To use the roles that were previously set up in a project, a project manager must associate the roles with the project.</span></span> <span data-ttu-id="1d0e8-105">Flera roller kan tilldelas för ett projekt.</span><span class="sxs-lookup"><span data-stu-id="1d0e8-105">Multiple roles can be assigned for a project.</span></span> <span data-ttu-id="1d0e8-106">I syfte att undvika förvirring märks dessa roller automatiskt under reservation.</span><span class="sxs-lookup"><span data-stu-id="1d0e8-106">To prevent confusion, these roles are automatically labeled during reservation.</span></span> <span data-ttu-id="1d0e8-107">Om till exempel projektledaren kräver tre programingenjörer, genereras automatiskt tre roller för programingenjör som har etiketterna **programingenjör 1**, **programingenjör 2** och **programingenjör 3**.</span><span class="sxs-lookup"><span data-stu-id="1d0e8-107">For example, if the project manager requires three software engineers, three Software engineer roles that have **software engineer 1**, **software engineer 2**, and **software engineer 3** as their labels are automatically generated.</span></span> <span data-ttu-id="1d0e8-108">Om rollen tidigare fått egenskaper, används de som ett filter för sökningar efter en resurs.</span><span class="sxs-lookup"><span data-stu-id="1d0e8-108">If role characteristics were previously set for the role, they are applied as a filter during searches for a resource.</span></span> <span data-ttu-id="1d0e8-109">Ytterligare egenskaper kan läggas till som krävs för att begränsa sökningen.</span><span class="sxs-lookup"><span data-stu-id="1d0e8-109">Additional characteristics can be added as required to further refine the search.</span></span>

<span data-ttu-id="1d0e8-110">Visningsinställningar kan också anpassas för att ge en bättre vy av resurstillgänglighet.</span><span class="sxs-lookup"><span data-stu-id="1d0e8-110">View settings can also be customized to give a better view of resource availability.</span></span> <span data-ttu-id="1d0e8-111">Det finns alternativ för att visa tim, dag, vecka, månad, kvartalsvis och årlig tillgänglighet.</span><span class="sxs-lookup"><span data-stu-id="1d0e8-111">There are options to show hourly, daily, weekly, monthly, quarterly, and annual availability.</span></span> <span data-ttu-id="1d0e8-112">Det finns även alternativ för att visa återstående och tillgänglig kapacitet för resurser.</span><span class="sxs-lookup"><span data-stu-id="1d0e8-112">There is also an option to show available and remaining capacity on resources.</span></span> <span data-ttu-id="1d0e8-113">Det här alternativet är användbart för tidsadministration, när du vill beräkna tillgänglig tid för aktiviteter eller resurstillgänglighet.</span><span class="sxs-lookup"><span data-stu-id="1d0e8-113">This option is useful for time management, when you're estimating available time for activities or resource availability.</span></span>

<span data-ttu-id="1d0e8-114">Projektledaren kan välja en roll på sidan och sedan, om det finns en tillgänglig resurs som passar behovet, välja att reservera en resurs för att fylla rollen.</span><span class="sxs-lookup"><span data-stu-id="1d0e8-114">The project manager can select a role on the page and then, if there is an available resource that fits the requirement, select to reserve a resource to fill the role.</span></span> <span data-ttu-id="1d0e8-115">Observera att resurserna inte måste reserveras vid denna tidpunkt i planeringsfasen.</span><span class="sxs-lookup"><span data-stu-id="1d0e8-115">Note that the resources don't have to be reserved at this point in the planning stage.</span></span> <span data-ttu-id="1d0e8-116">När du skapar en struktur kan du ersätta roller med bemannade resurser för projektet.</span><span class="sxs-lookup"><span data-stu-id="1d0e8-116">When you create a WBS, you can replace roles with staffed resources for the project.</span></span> <span data-ttu-id="1d0e8-117">Om roller ersättas med bemannade resurser i strukturen uppdaterar inställningen av resursen automatiskt projektteamslistan och tidsplaneringen.</span><span class="sxs-lookup"><span data-stu-id="1d0e8-117">If roles are replaced with staffed resources in the WBS, the resource setup automatically updates the project team listing and scheduling.</span></span>

<span data-ttu-id="1d0e8-118">[![Projektteam som innehåller både roller och faktiska resurser](./media/projectresourcing03-1024x368.jpg)](./media/projectresourcing03.jpg)</span><span class="sxs-lookup"><span data-stu-id="1d0e8-118">[![Project team listing that includes both roles and actual resources](./media/projectresourcing03-1024x368.jpg)](./media/projectresourcing03.jpg)</span></span> 

<span data-ttu-id="1d0e8-119">Projektchefen har olika alternativ för att boka resurser för ett projekt, till exempel **Resterande kapacitet**, **Total kapacitet**, **Kapacitet i procent** och **Ange timmar**.</span><span class="sxs-lookup"><span data-stu-id="1d0e8-119">The project manager has various options for booking a resource for a project, such as **Remaining capacity**, **Full capacity**, **Capacity percentage**, and **Specify hours**.</span></span> <span data-ttu-id="1d0e8-120">Dessa bokningsalternativ kan annulleras när som helst om resurstilldelningen ändras.</span><span class="sxs-lookup"><span data-stu-id="1d0e8-120">These booking options can be canceled at any time if resource assignments change.</span></span> <span data-ttu-id="1d0e8-121">Två typer av bokningar stöds:</span><span class="sxs-lookup"><span data-stu-id="1d0e8-121">Two types of booking are supported:</span></span>

- <span data-ttu-id="1d0e8-122">**Fast bokning** – Resursreservationen godkändes och bekräftades för att arbeta på engagemanget under den angivna varaktigheten.</span><span class="sxs-lookup"><span data-stu-id="1d0e8-122">**Hard Book** – The resource reservation was approved and confirmed to work on the engagement for the specified duration.</span></span>
- <span data-ttu-id="1d0e8-123">**Preliminär bokning** – Resursreservationerna godkändes preliminärt för att arbeta på engagemanget för den angivna varaktigheten.</span><span class="sxs-lookup"><span data-stu-id="1d0e8-123">**Soft book** – The resource reservations was tentatively set to work on the engagement for the specified duration.</span></span>

<span data-ttu-id="1d0e8-124">Följande procedur förklarar hur du skapar ett projektteam.</span><span class="sxs-lookup"><span data-stu-id="1d0e8-124">The following procedure explains how to create a project team.</span></span>

## <a name="create-a-project-team"></a><span data-ttu-id="1d0e8-125">Skapa ett projektteam</span><span class="sxs-lookup"><span data-stu-id="1d0e8-125">Create a project team</span></span>

1. <span data-ttu-id="1d0e8-126">På listsidan **Alla projekt**, markera ett projekt och markera sedan **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="1d0e8-126">On the **All projects** list page, select a project, and then select **Edit**.</span></span>
2. <span data-ttu-id="1d0e8-127">På fliken **Projektteam och tidsplanering**, i fältet **Schemalagt slutdatum**, ange schemastartdatumet plus en månad.</span><span class="sxs-lookup"><span data-stu-id="1d0e8-127">On the **Project team and scheduling** tab, in the **Schedule end date** field, enter the schedule start date plus one month.</span></span> <span data-ttu-id="1d0e8-128">Om till exempel schemastartdatumet är 24 juni 2017 (24/06/2017), ange **24/07/2017**.</span><span class="sxs-lookup"><span data-stu-id="1d0e8-128">For example, if the schedule start date is June 24, 2017 (24/06/2017), enter **24/07/2017**.</span></span>
3. <span data-ttu-id="1d0e8-129">Markera **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="1d0e8-129">Select **Add**.</span></span>
4. <span data-ttu-id="1d0e8-130">I **Lägg till roller i projektet**-fönstret, i **Roll**-fältet, välj **Senior projektledare**.</span><span class="sxs-lookup"><span data-stu-id="1d0e8-130">In the **Add roles to the project** pane, in the **Role** field, select **Senior Project Manager**.</span></span>
5. <span data-ttu-id="1d0e8-131">Markera **Erforderliga kompetenser**.</span><span class="sxs-lookup"><span data-stu-id="1d0e8-131">Select **Required competencies**.</span></span>
6. <span data-ttu-id="1d0e8-132">På **Välj egenskaper**-sidan markeras de egenskaper som du tidigare angett för rollen senior projektledare som standard.</span><span class="sxs-lookup"><span data-stu-id="1d0e8-132">On the **Choose characteristics** page, the characteristics that you previously set for the Senior project manager role are selected by default.</span></span> <span data-ttu-id="1d0e8-133">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="1d0e8-133">Select **OK**.</span></span>
7. <span data-ttu-id="1d0e8-134">På **Lägg till roller i projektet**-sidan i **Antal resurser**-fältet, ange **1**.</span><span class="sxs-lookup"><span data-stu-id="1d0e8-134">On the **Add roles to project** page, in the **Number of resources** field, enter **1**.</span></span>
8. <span data-ttu-id="1d0e8-135">I **Resurs**-fältet visar sökningen alla resurser som har begärt kompetenserna.</span><span class="sxs-lookup"><span data-stu-id="1d0e8-135">In the **Resource** field, the lookup shows all resources that have the required competencies.</span></span> <span data-ttu-id="1d0e8-136">Markera **Daniel Goldschmidt** och markera sedan **Skapa**.</span><span class="sxs-lookup"><span data-stu-id="1d0e8-136">Select **Daniel Goldschmidt**, and then select **Create**.</span></span>
9. <span data-ttu-id="1d0e8-137">På sidan **Projekt** markerar du **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="1d0e8-137">On the **Project** page, select **Add**.</span></span>
10. <span data-ttu-id="1d0e8-138">I **Lägg till roller i projektet**-fönstret, i **Roll**-fältet, välj **Teammedlem**.</span><span class="sxs-lookup"><span data-stu-id="1d0e8-138">In the **Add roles to the project** pane, in the **Role** field, select **Team member**.</span></span> <span data-ttu-id="1d0e8-139">I fältet **Antal resurser**, ange **5**.</span><span class="sxs-lookup"><span data-stu-id="1d0e8-139">In the **Number of resources** field, enter **5**.</span></span>
11. <span data-ttu-id="1d0e8-140">Markera **Skapa**.</span><span class="sxs-lookup"><span data-stu-id="1d0e8-140">Select **Create**.</span></span>
12. <span data-ttu-id="1d0e8-141">På sidan **Projekt** markerar du **Uppfyll resurs**.</span><span class="sxs-lookup"><span data-stu-id="1d0e8-141">On the **Projects** page, select **Fulfill resource**.</span></span>

## <a name="monitor-project-teams"></a><span data-ttu-id="1d0e8-142">Övervaka projektteam</span><span class="sxs-lookup"><span data-stu-id="1d0e8-142">Monitor project teams</span></span>
1. <span data-ttu-id="1d0e8-143">På sidan **Alla projekt**, markera länken **Projekt-ID** för projektet **XYZ-uppgradering fas 2**.</span><span class="sxs-lookup"><span data-stu-id="1d0e8-143">On the **All projects** page, select the **Project ID** link for the **XYZ Upgrade Phase 2** project.</span></span>
2. <span data-ttu-id="1d0e8-144">På snabbfliken **Projektteam och tidsplanering**, verifiera att de listade projektresurserna är korrekta.</span><span class="sxs-lookup"><span data-stu-id="1d0e8-144">On the **Project team and scheduling** FastTab, verify that the project resources that are listed are correct.</span></span>
