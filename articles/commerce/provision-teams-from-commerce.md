---
title: Provision Microsoft Teams från Dynamics 365 Commerce
description: I det här avsnittet beskrivs hur du etablerar Microsoft Teams med hjälp av organisationsdata från Dynamics 365 Commerce.
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
ms.openlocfilehash: 96382c072e03506294d72899072a358091bda8ab
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5842750"
---
# <a name="provision-microsoft-teams-from-dynamics-365-commerce"></a><span data-ttu-id="64a83-103">Provision Microsoft Teams från Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="64a83-103">Provision Microsoft Teams from Dynamics 365 Commerce</span></span>

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

<span data-ttu-id="64a83-104">I det här avsnittet beskrivs hur du etablerar Microsoft Teams med hjälp av organisationsdata från Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="64a83-104">This topic describes how to provision Microsoft Teams by using organizational data from Dynamics 365 Commerce.</span></span>

<span data-ttu-id="64a83-105">Dynamics 365 Commerce erbjuder ett enkelt sätt att tillhandahålla Teams om du ännu inte har ställt in team för dina detaljhandelsbutiker där.</span><span class="sxs-lookup"><span data-stu-id="64a83-105">Dynamics 365 Commerce offers an easy way to provision Teams if you haven't yet set up teams for your retail stores there.</span></span> <span data-ttu-id="64a83-106">Genom att dra nytta av väldefinierad information från Commerce som du vill använda i Teams kan du hjälpa butiksanställda att komma igång i Teams.</span><span class="sxs-lookup"><span data-stu-id="64a83-106">By taking advantage of well-defined information from Commerce that you want to use in Teams, you can help your store employees get started in Teams.</span></span> <span data-ttu-id="64a83-107">Den här informationen omfattar organisationshierarkin, butiksnamn, medarbetarinformation Azure Active Directory och (Azure AD) konton.</span><span class="sxs-lookup"><span data-stu-id="64a83-107">This information includes the organizational hierarchy, store names, employee information, and Azure Active Directory (Azure AD) accounts.</span></span> 

<span data-ttu-id="64a83-108">Processen för reservering av Teams har två huvudsteg:</span><span class="sxs-lookup"><span data-stu-id="64a83-108">The process of provisioning Teams has two main steps:</span></span>

1. <span data-ttu-id="64a83-109">I Teams skapar du ett team för varje butik och lägger till butiksarbetare som medlemmar i rätt team.</span><span class="sxs-lookup"><span data-stu-id="64a83-109">In Teams, create a team for each retail store, and add store workers as members of the appropriate team.</span></span> <span data-ttu-id="64a83-110">Om en anställd är associerad med mer än en butik kommer teammedlemskapet att återspegla detta faktum.</span><span class="sxs-lookup"><span data-stu-id="64a83-110">If an employee is associated with more than one retail store, team membership will reflect that fact.</span></span> <span data-ttu-id="64a83-111">Ett kommunikationsteam med regionala chefer som medlemmar skapas för att publicera uppgifter från Teams.</span><span class="sxs-lookup"><span data-stu-id="64a83-111">A communications team that includes regional managers as members will be created to help publish tasks from Teams.</span></span>
1. <span data-ttu-id="64a83-112">Överför organisationshierarkin från Commerce till Teams.</span><span class="sxs-lookup"><span data-stu-id="64a83-112">Upload your organizational hierarchy from Commerce to Teams.</span></span>

## <a name="provision-teams-in-commerce-headquarters"></a><span data-ttu-id="64a83-113">Provision Teams i Commerce-administration</span><span class="sxs-lookup"><span data-stu-id="64a83-113">Provision Teams in Commerce headquarters</span></span>

<span data-ttu-id="64a83-114">Innan du provision Microsoft Teams måste du utföra följande uppgifter:</span><span class="sxs-lookup"><span data-stu-id="64a83-114">Before you provision Microsoft Teams, complete these tasks:</span></span>

- <span data-ttu-id="64a83-115">Bekräfta att alla regionchefer har kommunikationschefer.</span><span class="sxs-lookup"><span data-stu-id="64a83-115">Confirm that all regional managers have been made communications managers.</span></span>
- <span data-ttu-id="64a83-116">Bekräfta att Azure-kontot för alla butikschefer och den anställda har associerats med chefens eller arbetarens arbetarpost i Commerce-administration.</span><span class="sxs-lookup"><span data-stu-id="64a83-116">Confirm that the Azure account of every store manager and worker has been associated with that manager's or worker's worker record in Commerce headquarters.</span></span>

<span data-ttu-id="64a83-117">Följ de här stegen om du vill etablera Teams i Commerce-administration.</span><span class="sxs-lookup"><span data-stu-id="64a83-117">To provision Teams in Commerce headquarters, follow these steps.</span></span>

1. <span data-ttu-id="64a83-118">Öppna **Retail och Commerce \> Kanalinställningar \> Microsoft Teams integrationskonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="64a83-118">Go to **Retail and Commerce \> Channel setup \> Microsoft Teams Integration Configuration**.</span></span>
1. <span data-ttu-id="64a83-119">Klicka på **Provision Teams** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="64a83-119">On the Action Pane, select **Provision teams**.</span></span> <span data-ttu-id="64a83-120">Ett batchjobb som kallas **Teams Provision** skapas.</span><span class="sxs-lookup"><span data-stu-id="64a83-120">A batch job that is named **Teams provision** is created.</span></span>
1. <span data-ttu-id="64a83-121">Gå till **Systemadministration \> Förfrågningar \> Batch-jobb** och hitta det senaste jobbet som har beskrivningen **Teams-etablering**.</span><span class="sxs-lookup"><span data-stu-id="64a83-121">Go to **System administration \> Inquiries \> Batch jobs**, and find the most recent job that has the description **Teams provision**.</span></span> <span data-ttu-id="64a83-122">Vänta tills körningen är klar för det här jobbet.</span><span class="sxs-lookup"><span data-stu-id="64a83-122">Wait until this job has finished running.</span></span>

> [!TIP]
> <span data-ttu-id="64a83-123">Om ingen av dina regionchefer, butikschefer och butiksarbetare har associerats med en Teams-licens kan du få följande felmeddelande: "Det gick inte att hämta tillämpliga SKU-kategorier för användaren."</span><span class="sxs-lookup"><span data-stu-id="64a83-123">If none of your regional managers, store managers, and store workers have been associated with a Teams license, you might receive the following error message: "Failed to retrieve appliable Sku categories for the user."</span></span> <span data-ttu-id="64a83-124">Välj för att rätta till problemet **Synkronisera team och medlemmar** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="64a83-124">To correct the issue, select **Sync teams and members** on the Action Pane.</span></span>

<!-- ![Dynamics 365 Commerce - Teams integration configuration](media/D365-Commerce-Microsoft-Teams-Configuration_with_disclaimer.png)-->

## <a name="validate-teams-provisioning-in-the-teams-admin-center"></a><span data-ttu-id="64a83-125">Validera Teams-etablering i administratörscentret för Teams</span><span class="sxs-lookup"><span data-stu-id="64a83-125">Validate Teams provisioning in the Teams admin center</span></span>

<span data-ttu-id="64a83-126">Om du validera Microsoft Teams etablering i Microsoft Teams administrationscentret gör du på följande sätt.</span><span class="sxs-lookup"><span data-stu-id="64a83-126">To validate Microsoft Teams provisioning in the Microsoft Teams admin center, follow these steps.</span></span>
    
1. <span data-ttu-id="64a83-127">Gå till [Teams administratörscenter](https://admin.teams.microsoft.com/) och logga in som administratör för din e-handelsklient.</span><span class="sxs-lookup"><span data-stu-id="64a83-127">Go to the [Teams admin center](https://admin.teams.microsoft.com/), and sign in as the administrator of your e-commerce tenant.</span></span>
1. <span data-ttu-id="64a83-128">I det vänstra navigeringsfönstret väljer du **Teams** för att öppna och sedan **Hantera team**.</span><span class="sxs-lookup"><span data-stu-id="64a83-128">In the left navigation pane, select **Teams** to expand it, and then select **Manage teams**.</span></span>
1. <span data-ttu-id="64a83-129">Bekräfta att ett team har skapats för varje Commerce butik.</span><span class="sxs-lookup"><span data-stu-id="64a83-129">Confirm that one team has been created for each Commerce retail store.</span></span>
1. <span data-ttu-id="64a83-130">Markera ett team och bekräfta att butiksarbetare har lagts till som medlemmar i gruppen.</span><span class="sxs-lookup"><span data-stu-id="64a83-130">Select a team, and confirm that store workers have been added to it as members.</span></span>
1. <span data-ttu-id="64a83-131">I vänstra navigeringsfönstret, välj **Användare** och bekräfta att alla butiksanställda i alla butiker har lagts till som användare.</span><span class="sxs-lookup"><span data-stu-id="64a83-131">In the left navigation pane, select **Users**, and confirm that all store employees in all stores have been added as users.</span></span>

<span data-ttu-id="64a83-132">I följande illustration visas ett exempel på sidan **Hantera team** i Teams administratörscenter.</span><span class="sxs-lookup"><span data-stu-id="64a83-132">The following illustration shows an example of the **Manage teams** page in the Teams admin center.</span></span>

![Exempel på sidan Hantera team i administrationscentret för Teams](media/Teams-FLW-Admin-Teams.png)

## <a name="upload-a-commerce-organizational-hierarchy-to-teams"></a><span data-ttu-id="64a83-134">Överför en Commerce organisationshierarki till Teams</span><span class="sxs-lookup"><span data-stu-id="64a83-134">Upload a Commerce organizational hierarchy to Teams</span></span>
    
<span data-ttu-id="64a83-135">Commerce organisationshierarki kan användas för Microsoft Teams för att publicera uppgifter i alla eller valda butiker som använder samma hierarkistruktur.</span><span class="sxs-lookup"><span data-stu-id="64a83-135">The Commerce organizational hierarchy can be used in Microsoft Teams to publish tasks to all or selected stores that use the same hierarchy structure.</span></span>

<span data-ttu-id="64a83-136">Så här överför du en Commerce organisationshierarki till Teams.</span><span class="sxs-lookup"><span data-stu-id="64a83-136">To upload a Commerce organizational hierarchy to Teams, follow these steps.</span></span>
    
1. <span data-ttu-id="64a83-137">I Commerce-administration, gå till **Retail och Commerce \> Kanalinställning \> Microsoft Teams integrationskonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="64a83-137">In Commerce headquarters, go to **Retail and Commerce \> Channel setup \> Microsoft Teams Integration Configuration**.</span></span>
1. <span data-ttu-id="64a83-138">Välj **Hämta målhierarki** och välj sedan **Retail Stores by Region** om du vill hämta filen med kommaavgränsade värden (CSV) i organisationshierarkin.</span><span class="sxs-lookup"><span data-stu-id="64a83-138">Select **Download targeting hierarchy**, and then select **Retail Stores by Region** to download a comma-separated values (CSV) file of the organizational hierarchy.</span></span>
1. <span data-ttu-id="64a83-139">Installera modulen Microsoft TeamsPowerShell genom att följa stegen i [Installera Microsoft Teams PowerShell](https://docs.microsoft.com/microsoftteams/teams-powershell-install).</span><span class="sxs-lookup"><span data-stu-id="64a83-139">Install the Microsoft Teams PowerShell module by following the steps in [Install Microsoft Teams PowerShell](https://docs.microsoft.com/microsoftteams/teams-powershell-install).</span></span>
1. <span data-ttu-id="64a83-140">När du uppmanas i Teams PowerShell-fönster, logga in med administratörskontot för din Azure AD klientorganisation.</span><span class="sxs-lookup"><span data-stu-id="64a83-140">When you're prompted in the Teams PowerShell window, sign in by using the administrator account for your Azure AD tenant.</span></span>
1. <span data-ttu-id="64a83-141">Följ stegen i [Ställ in din teaminriktningshierarki](https://docs.microsoft.com/microsoftteams/set-up-your-team-hierarchy) om du vill överföra CSV-filen för målhierarkin.</span><span class="sxs-lookup"><span data-stu-id="64a83-141">Follow the steps in [Set up your team targeting hierarchy](https://docs.microsoft.com/microsoftteams/set-up-your-team-hierarchy) to upload the CSV file for the targeting hierarchy.</span></span>

## <a name="verify-that-the-organizational-hierarchy-was-uploaded-to-teams"></a><span data-ttu-id="64a83-142">Kontrollera att organisationshierarkin har överförts till Teams</span><span class="sxs-lookup"><span data-stu-id="64a83-142">Verify that the organizational hierarchy was uploaded to Teams</span></span>

<span data-ttu-id="64a83-143">Kontrollera att organisationshierarkin har överförts till Microsoft Teams med följande steg.</span><span class="sxs-lookup"><span data-stu-id="64a83-143">To verify that the organizational hierarchy was uploaded to Microsoft Teams, follow these steps.</span></span>

1. <span data-ttu-id="64a83-144">Logga in i Teams som kommunikationschef.</span><span class="sxs-lookup"><span data-stu-id="64a83-144">Sign in to Teams as a communications manager.</span></span>
1. <span data-ttu-id="64a83-145">I det navigeringsfönstret, välj **Uppgifter av Planner**.</span><span class="sxs-lookup"><span data-stu-id="64a83-145">In the left navigation pane, select **Tasks by Planner**.</span></span>
1. <span data-ttu-id="64a83-146">På fliken **Publicerade listor** skapar du en ny lista som har en dummy-uppgift.</span><span class="sxs-lookup"><span data-stu-id="64a83-146">On the **Published lists** tab, create a new list that has a dummy task.</span></span>
1. <span data-ttu-id="64a83-147">Markera **Publicera**.</span><span class="sxs-lookup"><span data-stu-id="64a83-147">Select **Publish**.</span></span> <span data-ttu-id="64a83-148">Organisationshierarkin bör visas i dialogrutan **Välj vem som ska publicera till** som visas i exemplet i illustrationen nedan.</span><span class="sxs-lookup"><span data-stu-id="64a83-148">The organizational hierarchy should appear in the **Select who to publish to** dialog box, as shown in the example in the following illustration.</span></span>

![Exempel på en organisationshierarki i dialogrutan Välj vem som ska publicera till](media/Microsoft-teams-verify-org-hierarchy.png)

## <a name="additional-resources"></a><span data-ttu-id="64a83-150">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="64a83-150">Additional resources</span></span>

[<span data-ttu-id="64a83-151">Dynamics 365 Commerce och Microsoft Teams-integrering, översikt</span><span class="sxs-lookup"><span data-stu-id="64a83-151">Dynamics 365 Commerce and Microsoft Teams integration overview</span></span>](commerce-teams-integration.md)

[<span data-ttu-id="64a83-152">Aktivera Dynamics 365 Commerce och Microsoft Teams-integration</span><span class="sxs-lookup"><span data-stu-id="64a83-152">Enable Dynamics 365 Commerce and Microsoft Teams integration</span></span>](enable-teams-integration.md)

[<span data-ttu-id="64a83-153">Synkronisera uppgiftshantering mellan Microsoft Teams och Dynamics 365 Commerce POS</span><span class="sxs-lookup"><span data-stu-id="64a83-153">Synchronize task management between Microsoft Teams and Dynamics 365 Commerce POS</span></span>](synchronize-tasks-teams-pos.md)

[<span data-ttu-id="64a83-154">Hantera användarroller i Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="64a83-154">Manage user roles in Microsoft Teams</span></span>](manage-user-roles-teams.md)

[<span data-ttu-id="64a83-155">Mappa butiker och team om det finns befintliga team i Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="64a83-155">Map stores and teams if there are pre-existing teams in Microsoft Teams</span></span>](map-stores-existing-teams.md)

[<span data-ttu-id="64a83-156">Vanliga frågor och svar om Dynamics 365 Commerce och Microsoft Teams-integration</span><span class="sxs-lookup"><span data-stu-id="64a83-156">Dynamics 365 Commerce and Microsoft Teams integration FAQ</span></span>](teams-integration-faq.md)
