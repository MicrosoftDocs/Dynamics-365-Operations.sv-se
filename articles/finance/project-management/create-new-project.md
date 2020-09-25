---
title: Skapa ett nytt projekt
description: Denna artikel innehåller information om hur du skapar och ett nytt projekt.
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
ms.openlocfilehash: c8c52b8c1c86ea2f6e03cf439ba5930f1006ab4f
ms.sourcegitcommit: 241ada0945c72d769eaa70ae35aedbb6a3233fdf
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/02/2020
ms.locfileid: "3760663"
---
# <a name="create-a-new-project"></a><span data-ttu-id="8cc19-103">Skapa ett nytt projekt</span><span class="sxs-lookup"><span data-stu-id="8cc19-103">Create a new project</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="8cc19-104">Gör på följande sätt om du vill skapa ett nytt projekt.</span><span class="sxs-lookup"><span data-stu-id="8cc19-104">Complete the following steps to create a new project.</span></span>

1. <span data-ttu-id="8cc19-105">På sidan **Projekthantering** markerar du **Nytt projekt** och anger sedan följande värden:</span><span class="sxs-lookup"><span data-stu-id="8cc19-105">On the **Project management** page, select **New project**, and enter the following values:</span></span>

    - <span data-ttu-id="8cc19-106">**Projekttyp:** tid och material</span><span class="sxs-lookup"><span data-stu-id="8cc19-106">**Project type:** Time and material</span></span>
    - <span data-ttu-id="8cc19-107">**Projektnamn:** XYZ uppgraderingsfas 2</span><span class="sxs-lookup"><span data-stu-id="8cc19-107">**Project name:** XYZ Upgrade Phase 2</span></span>
    - <span data-ttu-id="8cc19-108">**Projektgrupp:** TM\_WIP</span><span class="sxs-lookup"><span data-stu-id="8cc19-108">**Project group:** TM\_WIP</span></span>
    - <span data-ttu-id="8cc19-109">**Projektkontrakt-ID:** 00000002</span><span class="sxs-lookup"><span data-stu-id="8cc19-109">**Project contract ID:** 00000002</span></span>

2. <span data-ttu-id="8cc19-110">Markera **Skapa projekt**.</span><span class="sxs-lookup"><span data-stu-id="8cc19-110">Select **Create project**.</span></span>

## <a name="assign-a-resource-to-a-project"></a><span data-ttu-id="8cc19-111">Tilldela en resurs till ett projekt</span><span class="sxs-lookup"><span data-stu-id="8cc19-111">Assign a resource to a project</span></span>

1. <span data-ttu-id="8cc19-112">På sidan **Arbetare**, på listan **Arbetare**, markerar du posten för den medarbetare som du tidigare angett kompetenser för, och öppnar sedan arbetarposten.</span><span class="sxs-lookup"><span data-stu-id="8cc19-112">On the **Workers** page, in the **Workers** list, select the record for the worker that you previously set up competencies for, and open the worker record.</span></span>
2. <span data-ttu-id="8cc19-113">I Åtgärdsfönstret, på fliken **Projekt**, i gruppen **Inställningar**, markerar du **Tilldela projekt**.</span><span class="sxs-lookup"><span data-stu-id="8cc19-113">On the Action Pane, on the **Project** tab, in the **Setup** group, select **Assign projects**.</span></span>
3. <span data-ttu-id="8cc19-114">På sidan **Projekttilldelningar för resursvalidering**, på fliken **Projekt**, i fältet **Lägg till projektet bland valda projekt**, filtrera projektet **XYZ-uppgradering fas 2**.</span><span class="sxs-lookup"><span data-stu-id="8cc19-114">On the **Resource validation project assignments** page, on the **Projects** tab, in the **Add the project to selected projects** field, filter on the **XYZ Upgrade Phase 2** project.</span></span>
4. <span data-ttu-id="8cc19-115">I fönstret **Återstående projekt**, markera ett projekt och markera sedan pilknappen för att lägga till det i fönstret **Valda projekt**.</span><span class="sxs-lookup"><span data-stu-id="8cc19-115">In the **Remaining projects** pane, select a project, and then select the arrow button to add it to the **Selected projects** pane.</span></span>

<span data-ttu-id="8cc19-116">Du kan vid behov också tilldela kategorier för en resurs.</span><span class="sxs-lookup"><span data-stu-id="8cc19-116">You can also assign categories for a resource as you require.</span></span> <span data-ttu-id="8cc19-117">Kategoritypen är antingen **Kostnad** eller **Intäkt**.</span><span class="sxs-lookup"><span data-stu-id="8cc19-117">The category type is either **Cost** or **Revenue**.</span></span> <span data-ttu-id="8cc19-118">Kategoritypen bestäms av din organisation.</span><span class="sxs-lookup"><span data-stu-id="8cc19-118">The category type is determined by your organization.</span></span> <span data-ttu-id="8cc19-119">Om det inte finns några tilldelade kategorier för en resurs, slår Finance upp standardkategorin på timpriser för kostnader och intäkter.</span><span class="sxs-lookup"><span data-stu-id="8cc19-119">If no categories are assigned for a resource, Finance looks up the default category on hour prices for cost and revenue.</span></span>

## <a name="set-up-project-resource-and-role-characteristics"></a><span data-ttu-id="8cc19-120">Ställ in projektresurs och rollegenskaper</span><span class="sxs-lookup"><span data-stu-id="8cc19-120">Set up project resource and role characteristics</span></span>

<span data-ttu-id="8cc19-121">En projektledare kan använda projektresurshanteringsfunktionen för att skapa roller som krävs för projektet.</span><span class="sxs-lookup"><span data-stu-id="8cc19-121">A project manager can use the project resourcing functionality to create the roles that are required for the project.</span></span> <span data-ttu-id="8cc19-122">Roller kan användas om bekräftade resurser fortfarande är okända när resurser reserveras.</span><span class="sxs-lookup"><span data-stu-id="8cc19-122">Roles can be used if confirmed resources are still unknown when resources are being reserved.</span></span> <span data-ttu-id="8cc19-123">Roller kan tillfälligt reserveras som planerade resurser, så att du kan fortsätta projektplanläggningsfaserna.</span><span class="sxs-lookup"><span data-stu-id="8cc19-123">Roles can be temporarily reserved as planned resources, so that you can continue the project planning stages.</span></span>

<span data-ttu-id="8cc19-124">[![Exempel på en roll](./media/projectresourcing05.jpg)](./media/projectresourcing05.jpg)</span><span class="sxs-lookup"><span data-stu-id="8cc19-124">[![Example of a role](./media/projectresourcing05.jpg)](./media/projectresourcing05.jpg)</span></span> 

<span data-ttu-id="8cc19-125">**Scenario:** Contoso anlitades för att slutföra ett tids- och materialprojekt som har ett godkänt projektramverk.</span><span class="sxs-lookup"><span data-stu-id="8cc19-125">**Scenario:** Contoso was hired to complete a Time and material project that has an approved project charter.</span></span> <span data-ttu-id="8cc19-126">Juniorprojektledaren avslutar fortfarande omfånget för projektet.</span><span class="sxs-lookup"><span data-stu-id="8cc19-126">The junior project manager is still completing the scope of the project.</span></span> <span data-ttu-id="8cc19-127">Den resursansvarige identifierar för närvarande specifika resurser som ska reserveras för arbete på det nya projektet.</span><span class="sxs-lookup"><span data-stu-id="8cc19-127">The resource manager is currently identifying specific resources that will be reserved to work on the new project.</span></span> <span data-ttu-id="8cc19-128">På grund av projektets vitala natur har projektets sponsor begärt rollen som ledande projektchef som en av sina roller.</span><span class="sxs-lookup"><span data-stu-id="8cc19-128">Because of the critical nature of the project, the project sponsor requested Senior project manager as one of the roles.</span></span> <span data-ttu-id="8cc19-129">Resursansvarig måste anskaffa den nya resursen och definiera rollen i systemet om biträdande projektledare behöver resursinformationen i samband med projektplaneringen.</span><span class="sxs-lookup"><span data-stu-id="8cc19-129">The resource manager must acquire the new resource and define the role in the system in case the junior project manager requires the resource information during project planning.</span></span>

<span data-ttu-id="8cc19-130">Följande steg visar hur resursansvarig kan ställa in rollen Seniorprojektledare och associera resursegenskaper med den.</span><span class="sxs-lookup"><span data-stu-id="8cc19-130">The following steps show how the resource manager can set up the Senior project manager role and associate resource characteristics with it.</span></span> <span data-ttu-id="8cc19-131">Senare rollen kan användas för att söka efter tillgängliga resurser som matchar de nödvändiga resurskompetenserna.</span><span class="sxs-lookup"><span data-stu-id="8cc19-131">Later, the role can be used to search for available resources that match the required resource competencies.</span></span>

1. <span data-ttu-id="8cc19-132">På sidan **Konfigurera roller** markerar du **Nytt** och anger sedan följande värden:</span><span class="sxs-lookup"><span data-stu-id="8cc19-132">On the **Setup roles** page, select **New**, and enter the following values:</span></span>

    - <span data-ttu-id="8cc19-133">**Roll ID:** Senior projektledare</span><span class="sxs-lookup"><span data-stu-id="8cc19-133">**Role ID:** Senior Project Manager</span></span>
    - <span data-ttu-id="8cc19-134">**Beskrivning:** Senior projektledare</span><span class="sxs-lookup"><span data-stu-id="8cc19-134">**Description:** Senior Project Manager</span></span>

2. <span data-ttu-id="8cc19-135">Markera **Skapa**.</span><span class="sxs-lookup"><span data-stu-id="8cc19-135">Select **Create**.</span></span>
3. <span data-ttu-id="8cc19-136">Markera rollen **Senior Project Manager** och markera sedan **Konfigurera egenskaper**.</span><span class="sxs-lookup"><span data-stu-id="8cc19-136">Select the **Senior Project Manager** role, and then select **Configure characteristics**.</span></span>
4. <span data-ttu-id="8cc19-137">I fältet **Egenskapstyp**, välj **Kompetens**.</span><span class="sxs-lookup"><span data-stu-id="8cc19-137">In the **Characteristics type** field, select **Skill**.</span></span>
5. <span data-ttu-id="8cc19-138">I fältet **Tillgängliga egenskaper** anger du den kompetens som du söker efter.</span><span class="sxs-lookup"><span data-stu-id="8cc19-138">In the **Available characteristics** field, enter the skill to search for.</span></span>
6. <span data-ttu-id="8cc19-139">I fältet **Egenskapstyp**, välj **Certifikat**.</span><span class="sxs-lookup"><span data-stu-id="8cc19-139">In the **Characteristic type** field, select **Certificate**.</span></span>
7. <span data-ttu-id="8cc19-140">I fältet **Tillgängliga egenskaper**, ange den certifikattyp som du söker efter.</span><span class="sxs-lookup"><span data-stu-id="8cc19-140">In the **Available characteristics** field, enter the certificate type to search for.</span></span>

## <a name="assign-a-project-resource-to-a-project"></a><span data-ttu-id="8cc19-141">Tilldela en projektresurs till ett projekt</span><span class="sxs-lookup"><span data-stu-id="8cc19-141">Assign a project resource to a project</span></span>

1. <span data-ttu-id="8cc19-142">På sidan **Alla projekt** markerar du projektet **XYZ-uppgradering fas 2**.</span><span class="sxs-lookup"><span data-stu-id="8cc19-142">On the **All projects** page, select the **XYZ Upgrade Phase 2** project.</span></span>
2. <span data-ttu-id="8cc19-143">På fliken **Projektteam och tidsplanering** markerar du **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="8cc19-143">On the **Project team and scheduling** tab, select **Add**.</span></span>
3. <span data-ttu-id="8cc19-144">I fältet **Roll**, välj **Teammedlem**.</span><span class="sxs-lookup"><span data-stu-id="8cc19-144">In the **Role** field, select **Team member**.</span></span>
4. <span data-ttu-id="8cc19-145">Markera **Boka via kalender**.</span><span class="sxs-lookup"><span data-stu-id="8cc19-145">Select **Book from calendar**.</span></span>
5. <span data-ttu-id="8cc19-146">På sidan **Resurstillgänglighet** markerar du **Visa inställningar**.</span><span class="sxs-lookup"><span data-stu-id="8cc19-146">On the **Resource availability** page, select **View settings**.</span></span>
6. <span data-ttu-id="8cc19-147">På sidan **Justera visningsinställningar**, ange följande värden:</span><span class="sxs-lookup"><span data-stu-id="8cc19-147">On the **Adjust view settings** page, enter the following values:</span></span>

    - <span data-ttu-id="8cc19-148">**Vy för format för datumintervall:** Dag</span><span class="sxs-lookup"><span data-stu-id="8cc19-148">**Format for date range view:** Day</span></span>
    - <span data-ttu-id="8cc19-149">**Visa beskrivningar av tillgänglighet:** Ja</span><span class="sxs-lookup"><span data-stu-id="8cc19-149">**Display availability descriptions:** Yes</span></span>
    - <span data-ttu-id="8cc19-150">**Visa resterande kapacitet:** Ja</span><span class="sxs-lookup"><span data-stu-id="8cc19-150">**Display remaining capacity:** Yes</span></span>

7. <span data-ttu-id="8cc19-151">Välj en resurs i listan över resurser.</span><span class="sxs-lookup"><span data-stu-id="8cc19-151">In the list of resources, select a resource.</span></span>
8. <span data-ttu-id="8cc19-152">Markera **Fast bokning** och **Full kapacitet**.</span><span class="sxs-lookup"><span data-stu-id="8cc19-152">Select **Hard book** and **Full capacity**.</span></span>

## <a name="assign-a-resource-to-a-default-role"></a><span data-ttu-id="8cc19-153">Tilldela en resurs till en standardroll</span><span class="sxs-lookup"><span data-stu-id="8cc19-153">Assign a resource to a default role</span></span>

<span data-ttu-id="8cc19-154">Om du vill hjälpa projektledare eller resursansvariga kan du ytterligare fördjupa dig i resurserna som kan reserveras för ett projekt.</span><span class="sxs-lookup"><span data-stu-id="8cc19-154">To help project or resource managers can drill down further on the resources that can be reserved for a project.</span></span> <span data-ttu-id="8cc19-155">Du kan associera en standardroll med en befintlig resurs eller en nyligen anskaffad resurs.</span><span class="sxs-lookup"><span data-stu-id="8cc19-155">You can associate a default role with an existing resource or a newly acquired resource.</span></span> <span data-ttu-id="8cc19-156">Exempelvis när Daniel anställdes hade han erfarenhet och sakkunskap som passade för rollen Affärsanalytiker.</span><span class="sxs-lookup"><span data-stu-id="8cc19-156">For example, when Daniel was hired, he had the experience and skills to fill the Business analyst role.</span></span> <span data-ttu-id="8cc19-157">Resursansvarige tilldelade den här rollen som Daniels standardroll.</span><span class="sxs-lookup"><span data-stu-id="8cc19-157">The resource manager assigned this role as Daniel's default role.</span></span> <span data-ttu-id="8cc19-158">Därefter lade resursansvarige till Daniel i en pool med affärsanalytiker som är tillgängliga för arbete i projekt.</span><span class="sxs-lookup"><span data-stu-id="8cc19-158">Therefore, the resource manager added Daniel to a pool of business analysts who are available to work on projects.</span></span>

<span data-ttu-id="8cc19-159">Under resursreserveringen kan projektledare filtrera rollresurserna som är tillgängliga för arbete i projekt.</span><span class="sxs-lookup"><span data-stu-id="8cc19-159">During resource reservation, project managers can filter the role resources that are available to work on projects.</span></span> <span data-ttu-id="8cc19-160">De kan använda den här informationen som ett villkor när de använder beslutsanalys för flera kriterier under resursuppfyllelse.</span><span class="sxs-lookup"><span data-stu-id="8cc19-160">They can use this information as one criterion when they perform multi-criteria decision analysis during resource fulfillment.</span></span> <span data-ttu-id="8cc19-161">De kan också lägga till andra resursegenskaper till filtret om du vill söka efter resurser som har specifika färdigheter, utbildning och erfarenheter för ett visst projekt.</span><span class="sxs-lookup"><span data-stu-id="8cc19-161">They can also add other resource characteristics to the filter to search for resources that have specific skills, education, and experience for a given project.</span></span>

<span data-ttu-id="8cc19-162">**Scenario:** Ett godkänt projekt har startat och den seniora projektledarrollen reserverades som en planerad resurs under projektplanläggningsfasen.</span><span class="sxs-lookup"><span data-stu-id="8cc19-162">**Scenario:** An approved project has started, and the Senior project manager role was reserved as a planned resource during the project planning stage.</span></span> <span data-ttu-id="8cc19-163">Resurschefen har nu fått en resurs för att uppfylla den seniora rollen som projektledare.</span><span class="sxs-lookup"><span data-stu-id="8cc19-163">The resource manager has now acquired a resource to fulfill the Senior project manager role.</span></span>

1. <span data-ttu-id="8cc19-164">På sidan **Resurslista** markerar du **Daniel Goldschmidt**.</span><span class="sxs-lookup"><span data-stu-id="8cc19-164">On the **Resources list** page, select **Daniel Goldschmidt**.</span></span>
2. <span data-ttu-id="8cc19-165">På sidan **Resursroll** markerar du **Nytt** och anger sedan följande värden:</span><span class="sxs-lookup"><span data-stu-id="8cc19-165">On the **Resource role** page, select **New**, and enter the following values:</span></span>

    - <span data-ttu-id="8cc19-166">**Giltighet:** Ange aktuellt datum.</span><span class="sxs-lookup"><span data-stu-id="8cc19-166">**Effective:** Enter the current date.</span></span>
    - <span data-ttu-id="8cc19-167">**Utgår:** Ange **Aldrig**.</span><span class="sxs-lookup"><span data-stu-id="8cc19-167">**Expiration:** Enter **Never**.</span></span>
    - <span data-ttu-id="8cc19-168">**Roll:** Ange **Senior Project Manager**.</span><span class="sxs-lookup"><span data-stu-id="8cc19-168">**Role:** Enter **Senior Project Manager**.</span></span>

3. <span data-ttu-id="8cc19-169">Markera **Spara** och stäng sedan sidan.</span><span class="sxs-lookup"><span data-stu-id="8cc19-169">Select **Save**, and then close the page.</span></span>
4. <span data-ttu-id="8cc19-170">På fliken **Kompetenser**, lägg till färdigheten **ProjectMgmt** och **PMP**.</span><span class="sxs-lookup"><span data-stu-id="8cc19-170">On the **Competencies** tab, add the **ProjectMgmt** skill and the **PMP** certificate.</span></span>
