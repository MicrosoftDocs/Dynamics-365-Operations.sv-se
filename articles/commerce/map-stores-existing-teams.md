---
title: Mappa butiker och team om det finns befintliga team i Microsoft Teams
description: Detta ämne beskriver hur man kan kartlägga butiker och motsvarande team i Dynamics 365 Commerce-administration om din organisation redan har skapat team i Microsoft Teams före Commerce-integration.
author: gvrmohanreddy
ms.date: 03/31/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2021-01-15
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: ccc2cbf11e405facf310d93e5458cfe12a43146d
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/11/2021
ms.locfileid: "6020229"
---
# <a name="map-stores-and-teams-if-there-are-pre-existing-teams-in-microsoft-teams"></a><span data-ttu-id="89430-103">Mappa butiker och team om det finns befintliga team i Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="89430-103">Map stores and teams if there are pre-existing teams in Microsoft Teams</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="89430-104">Detta ämne beskriver hur man kan kartlägga butiker och motsvarande team i Dynamics 365 Commerce-administration om din organisation redan har skapat team i Microsoft Teams före Commerce-integration.</span><span class="sxs-lookup"><span data-stu-id="89430-104">This topic covers how to map stores and corresponding teams in Dynamics 365 Commerce headquarters if your organization has already created teams in Microsoft Teams before Commerce integration.</span></span>

<span data-ttu-id="89430-105">Din organisation kanske har team skapade för några eller alla av butikerna innan de kan integrera Dynamics 365 Commerce och Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="89430-105">Your organization may have teams created for some or all of your stores before integrating Dynamics 365 Commerce and Microsoft Teams.</span></span> <span data-ttu-id="89430-106">Om detta är fallet ska du skapa uppgiftssynkronisering mellan Commerce POS och Microsoft Teams måste du ange mappningen av butiker och motsvarande team i Commerce-administration.</span><span class="sxs-lookup"><span data-stu-id="89430-106">If this is the case, to establish task synchronization between Commerce POS and Microsoft Teams you must provide the mapping of stores and corresponding team in Commerce headquarters.</span></span>

## <a name="map-stores-and-corresponding-teams-in-commerce-headquarters"></a><span data-ttu-id="89430-107">Mappa butiker och motsvarande team i Commerce-administration</span><span class="sxs-lookup"><span data-stu-id="89430-107">Map stores and corresponding teams in Commerce headquarters</span></span> 

<span data-ttu-id="89430-108">Mappa butiker och motsvarande team i Commerce-administration, följer dessa steg.</span><span class="sxs-lookup"><span data-stu-id="89430-108">To map stores and corresponding teams in Commerce headquarters, follow these steps.</span></span>

1. <span data-ttu-id="89430-109">Gå till **Systemadministration \> Arbetsyta \> Datahantering**.</span><span class="sxs-lookup"><span data-stu-id="89430-109">Go to **System Administration \> Workspace \> Data management**.</span></span>
1. <span data-ttu-id="89430-110">Välj **Exportera**.</span><span class="sxs-lookup"><span data-stu-id="89430-110">Select **Export**.</span></span> 
1. <span data-ttu-id="89430-111">Klicka på **Ny** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="89430-111">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="89430-112">Under **Gruppnamn** anger du "Exportera Teams-mappning".</span><span class="sxs-lookup"><span data-stu-id="89430-112">Under **Group name**, enter "Export Teams mapping".</span></span>
1. <span data-ttu-id="89430-113">På snabbfliken **Vald entiteter**, välj **Lägg till entitet**.</span><span class="sxs-lookup"><span data-stu-id="89430-113">On the **Selected entities** FastTab, select **Add entity**.</span></span> <span data-ttu-id="89430-114">Dialogrutan **Lägg till enhet** visas.</span><span class="sxs-lookup"><span data-stu-id="89430-114">The **Add entity** dialog box appears.</span></span>  
1. <span data-ttu-id="89430-115">I listrutan **Entitetsnamn**, välj **Teams-mappning mellan källa och team**.</span><span class="sxs-lookup"><span data-stu-id="89430-115">In the **Entity name** drop-down list, select **Teams mapping between source and team**.</span></span>
1. <span data-ttu-id="89430-116">I listrutan **Måldataformat**, välj **CSV**.</span><span class="sxs-lookup"><span data-stu-id="89430-116">In the **Target data format** drop-down list, select **CSV**.</span></span>
1. <span data-ttu-id="89430-117">Välj **Lägg till** och sedan **Stäng**.</span><span class="sxs-lookup"><span data-stu-id="89430-117">Select **Add**, and then select **Close**.</span></span>
1. <span data-ttu-id="89430-118">Längst upp till vänster under åtgärdsfönstret, välj **Exportera nu**.</span><span class="sxs-lookup"><span data-stu-id="89430-118">On the top left under the Action Pane, select **Export now**.</span></span>
1. <span data-ttu-id="89430-119">Under **Bearbetningsstatus för entitet**, välj **Hämta fil**.</span><span class="sxs-lookup"><span data-stu-id="89430-119">Under **Entity processing status**, select **Download file**.</span></span>
1. <span data-ttu-id="89430-120">I den exporterade CSV-filen, ange värden för **SOURCETYPE**, **SOURCEID** och **TEAMID** enligt följande:</span><span class="sxs-lookup"><span data-stu-id="89430-120">In the exported CSV file, enter values for **SOURCETYPE**, **SOURCEID**, and **TEAMID** as follows:</span></span>
    - <span data-ttu-id="89430-121">För **SOURCETYPE**, ange "RetailStore".</span><span class="sxs-lookup"><span data-stu-id="89430-121">For **SOURCETYPE**, enter "RetailStore".</span></span> 
    - <span data-ttu-id="89430-122">För **SOURCEID**, ange butiksnumret (till exempel "000135" för San Francisco-butiken).</span><span class="sxs-lookup"><span data-stu-id="89430-122">For **SOURCEID**, enter the store number (for example, "000135" for the San Francisco store).</span></span> <span data-ttu-id="89430-123">Du hittar butiksnummer på **Butik och handel \> Kanaler \> Butiker**.</span><span class="sxs-lookup"><span data-stu-id="89430-123">You can find store numbers at **Retail and Commerce \> Channels \> Stores**.</span></span>
    - <span data-ttu-id="89430-124">För **TEAMID** anger du motsvarande team-ID från Microsoft Teams (till exempel "5f8bc92b-6aa8-451e-85d1-3949c01ddc6c").</span><span class="sxs-lookup"><span data-stu-id="89430-124">For **TEAMID**, enter the corresponding team ID from Microsoft Teams (for example, "5f8bc92b-6aa8-451e-85d1-3949c01ddc6c").</span></span> <span data-ttu-id="89430-125">Du hittar ID-information på [admin.teams.microsoft.com](https://admin.teams.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="89430-125">You can find team ID information at [admin.teams.microsoft.com](https://admin.teams.microsoft.com).</span></span>
1. <span data-ttu-id="89430-126">Spara CSV-filen på den lokala datorn.</span><span class="sxs-lookup"><span data-stu-id="89430-126">Save the CSV file to your local machine.</span></span>
1. <span data-ttu-id="89430-127">Gå till **Systemadministration \> Arbetsyta \> Datahantering** och välj sedan **Importera**.</span><span class="sxs-lookup"><span data-stu-id="89430-127">Go to **System Administration \> Workspace \> Data management**, and then select **Import**.</span></span>
1. <span data-ttu-id="89430-128">På snabbfliken **Vald entiteter**, välj **Lägg till fil**.</span><span class="sxs-lookup"><span data-stu-id="89430-128">On the **Selected entities** FastTab, select **Add file**.</span></span> <span data-ttu-id="89430-129">Dialogrutan **Lägg till fil** visas.</span><span class="sxs-lookup"><span data-stu-id="89430-129">The **Add file** dialog box appears.</span></span>
1. <span data-ttu-id="89430-130">I listrutan **Entitetsnamn**, välj **Teams-mappning mellan källa och team**.</span><span class="sxs-lookup"><span data-stu-id="89430-130">In the **Entity name** drop-down list, select **Teams mapping between source and team**.</span></span>
1. <span data-ttu-id="89430-131">I listrutan **Källdataformat**, välj **CSV**.</span><span class="sxs-lookup"><span data-stu-id="89430-131">In the **Source data format** drop-down list, select **CSV**.</span></span>
1. <span data-ttu-id="89430-132">Välj **Ladda upp och lägg till**, välj den CSV-fil du sparade tidigare och välj sedan **Öppna**.</span><span class="sxs-lookup"><span data-stu-id="89430-132">Select **Upload and add**, select the CSV file that you saved previously, and then select **Open**.</span></span>
1. <span data-ttu-id="89430-133">I dialogrutan **Lägg till**, välj **Stäng**.</span><span class="sxs-lookup"><span data-stu-id="89430-133">In the **Add file** dialog box, select **Close**.</span></span>
1. <span data-ttu-id="89430-134">I åtgärdsrutan väljer du **Spara** och välj sedan **Import**.</span><span class="sxs-lookup"><span data-stu-id="89430-134">On the Action Pane, select **Save** , and then select **Import**.</span></span>

<span data-ttu-id="89430-135">Följande exempelbild visar **Exportera Teams-mappning** gruppen i Commerce med **Lägg till enhet** och de exporterade CSV-filrubrikerna markerade.</span><span class="sxs-lookup"><span data-stu-id="89430-135">The following example image shows the **Export teams mapping** group in Commerce with **Add entity** elements and the exported CSV file headers highlighted.</span></span>

![Exportera Teams-mappning gruppen i Commerce med Lägg till enhet och de exporterade CSV-filrubrikerna markerade.](media/d365-commerce-data-mgmt-export-entity.png)

> [!NOTE]
> <span data-ttu-id="89430-137">När du har slutfört föregående steg följer du stegen i [Synkronisera uppgiftshantering mellan Microsoft Teams och kassa](synchronize-tasks-teams-pos.md) för synkronisera för uppgiftshantering.</span><span class="sxs-lookup"><span data-stu-id="89430-137">After you complete the preceeding steps, follow the steps in [Synchronize task management between Microsoft Teams and POS](synchronize-tasks-teams-pos.md) to synchronize task management.</span></span> 

## <a name="additional-resources"></a><span data-ttu-id="89430-138">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="89430-138">Additional resources</span></span>

[<span data-ttu-id="89430-139">Dynamics 365 Commerce och Microsoft Teams-integrering, översikt</span><span class="sxs-lookup"><span data-stu-id="89430-139">Dynamics 365 Commerce and Microsoft Teams integration overview</span></span>](commerce-teams-integration.md)

[<span data-ttu-id="89430-140">Aktivera Dynamics 365 Commerce och Microsoft Teams-integration</span><span class="sxs-lookup"><span data-stu-id="89430-140">Enable Dynamics 365 Commerce and Microsoft Teams integration</span></span>](enable-teams-integration.md)

[<span data-ttu-id="89430-141">Provision Microsoft Teams från Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="89430-141">Provision Microsoft Teams from Dynamics 365 Commerce</span></span>](provision-teams-from-commerce.md)

[<span data-ttu-id="89430-142">Synkronisera uppgiftshantering mellan Microsoft Teams och Dynamics 365 Commerce POS</span><span class="sxs-lookup"><span data-stu-id="89430-142">Synchronize task management between Microsoft Teams and Dynamics 365 Commerce POS</span></span>](synchronize-tasks-teams-pos.md)

[<span data-ttu-id="89430-143">Hantera användarroller i Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="89430-143">Manage user roles in Microsoft Teams</span></span>](manage-user-roles-teams.md)

[<span data-ttu-id="89430-144">Vanliga frågeställningar och svar om Dynamics 365 Commerce och Microsoft Teams-integration</span><span class="sxs-lookup"><span data-stu-id="89430-144">Dynamics 365 Commerce and Microsoft Teams integration FAQ</span></span>](teams-integration-faq.md)
