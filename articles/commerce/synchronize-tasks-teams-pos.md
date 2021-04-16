---
title: Synkronisera uppgiftshantering mellan Microsoft Teams och Dynamics 365 Commerce POS
description: I det här avsnittet beskrivs hur du synkroniserar uppgiftshantering mellan Microsoft Teams och Dynamics 365 Commerce kassa (POS).
author: gvrmohanreddy
manager: annbe
ms.date: 03/31/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2021-01-15
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: ca0cb32ac3ee508ddcd5346a895fb9904fa92517
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5842748"
---
# <a name="synchronize-task-management-between-microsoft-teams-and-dynamics-365-commerce-pos"></a><span data-ttu-id="88fd5-103">Synkronisera uppgiftshantering mellan Microsoft Teams och Dynamics 365 Commerce POS</span><span class="sxs-lookup"><span data-stu-id="88fd5-103">Synchronize task management between Microsoft Teams and Dynamics 365 Commerce POS</span></span>

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

<span data-ttu-id="88fd5-104">I det här avsnittet beskrivs hur du synkroniserar uppgiftshantering mellan Microsoft Teams och Dynamics 365 Commerce kassa (POS).</span><span class="sxs-lookup"><span data-stu-id="88fd5-104">This topic describes how to synchronize task management between Microsoft Teams and Dynamics 365 Commerce point of sale (POS).</span></span>

<span data-ttu-id="88fd5-105">Ett av huvudsyftena med Teams-integration är att aktivera synkronisering av uppgiftshantering mellan kassaprogrammet och Teams.</span><span class="sxs-lookup"><span data-stu-id="88fd5-105">One of the main purposes of Teams integration is to enable the synchronization of task management between the POS application and Teams.</span></span> <span data-ttu-id="88fd5-106">På det här sättet kan butiksanställda använda antingen kassaprogrammet eller Teams för att hantera uppgifter och behöver inte byta program.</span><span class="sxs-lookup"><span data-stu-id="88fd5-106">In this way, store employees can use either the POS application or Teams to manage tasks, and don't have to switch applications.</span></span>

<span data-ttu-id="88fd5-107">Eftersom Planner används som databas för uppgifter i Teams måste det finnas en länk mellan Teams och Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="88fd5-107">Because Planner is used as a repository for tasks in Teams, there must be a link between Teams and Dynamics 365 Commerce.</span></span> <span data-ttu-id="88fd5-108">Den här länken upprättas genom att ett specifikt plan-ID för ett givet butikteam används.</span><span class="sxs-lookup"><span data-stu-id="88fd5-108">This link is established by using a specific plan ID for a given store team.</span></span>

<span data-ttu-id="88fd5-109">Följande procedurer visar hur du ställer in synkronisering av uppgiftshantering mellan kassa- och Teams-programmen.</span><span class="sxs-lookup"><span data-stu-id="88fd5-109">The following procedures show how to set up task management synchronization between the POS and Teams applications.</span></span>

## <a name="publish-a-test-task-list-in-teams"></a><span data-ttu-id="88fd5-110">Publicera en testuppgiftslista i Teams</span><span class="sxs-lookup"><span data-stu-id="88fd5-110">Publish a test task list in Teams</span></span>

<span data-ttu-id="88fd5-111">I följande procedur förutsätts det att dina butiksgrupper använder Microsoft Teams uppgiftshanteringsintegrering med Commerce för första gången.</span><span class="sxs-lookup"><span data-stu-id="88fd5-111">The following procedure assumes that your store teams are using Microsoft Teams task management integration with Commerce for the first time.</span></span>

<span data-ttu-id="88fd5-112">Publicera en testuppgiftslista i Teams genom att följa dessa steg.</span><span class="sxs-lookup"><span data-stu-id="88fd5-112">To publish a test task list in Teams, follow these steps.</span></span>

1. <span data-ttu-id="88fd5-113">Logga in i Teams som kommunikationschef.</span><span class="sxs-lookup"><span data-stu-id="88fd5-113">Sign in to Teams as a communications manager.</span></span> <span data-ttu-id="88fd5-114">Kommunikationschefer är vanligtvis användare med rollen **Regionchef** i Commerce.</span><span class="sxs-lookup"><span data-stu-id="88fd5-114">Typically, communications managers are users who have the **Regional manager** role in Commerce.</span></span>
1. <span data-ttu-id="88fd5-115">I det navigeringsfönstret, välj **Uppgifter av Planner**.</span><span class="sxs-lookup"><span data-stu-id="88fd5-115">In the left navigation pane, select **Tasks by Planner**.</span></span>
1. <span data-ttu-id="88fd5-116">På fliken **Publicerade listor**, välj **Ny lista** längst ned till vänster och namnge den nya listan **Testuppgiftslista**.</span><span class="sxs-lookup"><span data-stu-id="88fd5-116">On the **Published lists** tab, select **New list** in the lower left, and name the new list **Test task list**.</span></span>
1. <span data-ttu-id="88fd5-117">Markera **Skapa**.</span><span class="sxs-lookup"><span data-stu-id="88fd5-117">Select **Create**.</span></span> <span data-ttu-id="88fd5-118">Den nya listan visas under **Utkast**.</span><span class="sxs-lookup"><span data-stu-id="88fd5-118">The new list appears under **Drafts**.</span></span>
1. <span data-ttu-id="88fd5-119">Under **Uppgiftsrubrik**, ge den första uppgiften rubriken **Testa Teams-integration**.</span><span class="sxs-lookup"><span data-stu-id="88fd5-119">Under **Task title**, give the first task the title **Testing Teams integration**.</span></span> <span data-ttu-id="88fd5-120">Välj sedan **Retur**.</span><span class="sxs-lookup"><span data-stu-id="88fd5-120">Then select **Enter**.</span></span>
1. <span data-ttu-id="88fd5-121">I listan **Utkast**, välj uppgiftslistan.</span><span class="sxs-lookup"><span data-stu-id="88fd5-121">In the **Drafts** list, select the task list.</span></span> <span data-ttu-id="88fd5-122">Välj  **Publicera**  i det övre högra hörnet.</span><span class="sxs-lookup"><span data-stu-id="88fd5-122">Then select **Publish** in the upper-right corner.</span></span>
1. <span data-ttu-id="88fd5-123">I dialogrutan **Välj som ska publiceras till**, välj de team som ska få testuppgiftslistan.</span><span class="sxs-lookup"><span data-stu-id="88fd5-123">In the **Select who to publish to** dialog box, select the teams that should receive the test task list.</span></span>
1. <span data-ttu-id="88fd5-124">Välj **Nästa** om du vill granska publiceringsplanen.</span><span class="sxs-lookup"><span data-stu-id="88fd5-124">Select **Next** to review your publication plan.</span></span> <span data-ttu-id="88fd5-125">Om du måste göra ändringar väljer du  **Bakåt**.</span><span class="sxs-lookup"><span data-stu-id="88fd5-125">If you must make changes, select **Back**.</span></span> 
1. <span data-ttu-id="88fd5-126">Välj **Bekräfta om du vill fortsätta** och välj **Publicera**.</span><span class="sxs-lookup"><span data-stu-id="88fd5-126">Select **Confirm to proceed**, and then select **Publish**.</span></span>
1. <span data-ttu-id="88fd5-127">När publiceringen är klar visas ett meddelande överst på fliken **Publicerade listor** om huruvida uppgiftslistan kunde levereras.</span><span class="sxs-lookup"><span data-stu-id="88fd5-127">After publishing is completed, a message at the top of the **Published lists** tab indicates whether your task list was successfully delivered.</span></span>

<span data-ttu-id="88fd5-128">Mer information finns i [Publicera uppgiftslistor om du vill skapa och spåra arbete i organisationen](https://support.microsoft.com/office/publish-task-lists-to-create-and-track-work-in-your-organization-095409b3-f5af-40aa-9f9e-339b54e705df).</span><span class="sxs-lookup"><span data-stu-id="88fd5-128">For more information, see [Publish task lists to create and track work in your organization](https://support.microsoft.com/office/publish-task-lists-to-create-and-track-work-in-your-organization-095409b3-f5af-40aa-9f9e-339b54e705df).</span></span>

## <a name="link-pos-and-teams-for-task-management"></a><span data-ttu-id="88fd5-129">Koppla kassa och Teams för uppgiftshantering</span><span class="sxs-lookup"><span data-stu-id="88fd5-129">Link POS and Teams for task management</span></span>

<span data-ttu-id="88fd5-130">Om du vill koppla kassa och Microsoft Teams-program för uppgiftshantering i Commerce-administration följer du dessa steg.</span><span class="sxs-lookup"><span data-stu-id="88fd5-130">To link the POS and Microsoft Teams applications for task management in Commerce headquarters, follow these steps.</span></span>

1. <span data-ttu-id="88fd5-131">Gå till **Retail och Commerce \> Uppgiftshantering \> Uppgifter integration med Microsoft Teams**.</span><span class="sxs-lookup"><span data-stu-id="88fd5-131">Go to **Retail and Commerce \> Task management \> Tasks integration with Microsoft Teams**.</span></span>
1. <span data-ttu-id="88fd5-132">I åtgärdsfönstret väljer du **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="88fd5-132">On the Action Pane, select **Edit**.</span></span>
1. <span data-ttu-id="88fd5-133">Ange alternativet **Aktivera integration av uppgiftshantering** till **Ja**.</span><span class="sxs-lookup"><span data-stu-id="88fd5-133">Set the **Enable Task Management Integration** option to **Yes**.</span></span>
1. <span data-ttu-id="88fd5-134">Klicka på **Spara** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="88fd5-134">On the Action Pane, select **Save**.</span></span>
1. <span data-ttu-id="88fd5-135">Klicka på **Uppgiftskonfiguration** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="88fd5-135">On the Action Pane, select **Setup task management**.</span></span> <span data-ttu-id="88fd5-136">Du bör få ett meddelande som anger att ett batchjobb som heter **Teams-etablering** skapas.</span><span class="sxs-lookup"><span data-stu-id="88fd5-136">You should receive a notification that indicates that a batch job that is named **Teams provision** is being created.</span></span>
1. <span data-ttu-id="88fd5-137">Gå till **Systemadministration \> Förfrågningar \> Batch-jobb** och hitta det senaste jobbet som har beskrivningen **Teams-etablering**.</span><span class="sxs-lookup"><span data-stu-id="88fd5-137">Go to **System administration \> Inquiries \> Batch jobs**, and find the most recent job that has the description **Teams provision**.</span></span> <span data-ttu-id="88fd5-138">Vänta tills körningen är klar för det här jobbet.</span><span class="sxs-lookup"><span data-stu-id="88fd5-138">Wait until this job has finished running.</span></span>
1. <span data-ttu-id="88fd5-139">Kör **CDX job 1070** för att publicera plan-ID och lagra referenser till Retail Server.</span><span class="sxs-lookup"><span data-stu-id="88fd5-139">Run the **CDX job 1070** to publish the plan ID and store references to Retail Server.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="88fd5-140">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="88fd5-140">Additional resources</span></span>

[<span data-ttu-id="88fd5-141">Dynamics 365 Commerce och Microsoft Teams-integrering, översikt</span><span class="sxs-lookup"><span data-stu-id="88fd5-141">Dynamics 365 Commerce and Microsoft Teams integration overview</span></span>](commerce-teams-integration.md)

[<span data-ttu-id="88fd5-142">Aktivera Dynamics 365 Commerce och Microsoft Teams-integration</span><span class="sxs-lookup"><span data-stu-id="88fd5-142">Enable Dynamics 365 Commerce and Microsoft Teams integration</span></span>](enable-teams-integration.md)

[<span data-ttu-id="88fd5-143">Provision Microsoft Teams från Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="88fd5-143">Provision Microsoft Teams from Dynamics 365 Commerce</span></span>](provision-teams-from-commerce.md)

[<span data-ttu-id="88fd5-144">Hantera användarroller i Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="88fd5-144">Manage user roles in Microsoft Teams</span></span>](manage-user-roles-teams.md)

[<span data-ttu-id="88fd5-145">Mappa butiker och team om det finns befintliga team i Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="88fd5-145">Map stores and teams if there are pre-existing teams in Microsoft Teams</span></span>](map-stores-existing-teams.md)

[<span data-ttu-id="88fd5-146">Vanliga frågor och svar om Dynamics 365 Commerce och Microsoft Teams-integration</span><span class="sxs-lookup"><span data-stu-id="88fd5-146">Dynamics 365 Commerce and Microsoft Teams integration FAQ</span></span>](teams-integration-faq.md)
