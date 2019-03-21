---
title: Nyheter och ändringar i Dynamics 365 for Talent (5 mars 2019)
description: Det här ämnet beskriver nya eller ändrade funktioner i Microsoft Dynamics 365 for Talent.
author: Darinkramer
manager: AnnBe
ms.date: 03/05/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2019-03-05
ms.dyn365.ops.version: Talent
ms.openlocfilehash: e6b490a696dc0a00c47e56f57373f330d0e53dde
ms.sourcegitcommit: 479b8cda7e411830bf1f579fab3692c980dcf850
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/08/2019
ms.locfileid: "783013"
---
# <a name="whats-new-or-changed-in-dynamics-365-for-talent-march-5-2019"></a><span data-ttu-id="3c75b-103">Nyheter och ändringar i Dynamics 365 for Talent (5 mars 2019)</span><span class="sxs-lookup"><span data-stu-id="3c75b-103">What's new or changed in Dynamics 365 for Talent (March 5, 2019)</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="3c75b-104">Det här ämnet beskriver nya eller ändrade funktioner i Talent.</span><span class="sxs-lookup"><span data-stu-id="3c75b-104">This topic describes features that are either new or changed in Talent</span></span>

## <a name="changes-in-attract"></a><span data-ttu-id="3c75b-105">Ändringar i Attract</span><span class="sxs-lookup"><span data-stu-id="3c75b-105">Changes in Attract</span></span>

### <a name="extending-option-sets-in-attract"></a><span data-ttu-id="3c75b-106">Utökade alternativuppsättningar i Attract</span><span class="sxs-lookup"><span data-stu-id="3c75b-106">Extending option sets in Attract</span></span>

<span data-ttu-id="3c75b-107">I Attract finns flera fält som består av alternativuppsättningar i Common Data Service (CDS).</span><span class="sxs-lookup"><span data-stu-id="3c75b-107">In Attract, there are multiple fields that are option sets within the Common Data Service (CDS).</span></span> <span data-ttu-id="3c75b-108">Nya funktioner har införts för att utöka alternativuppsättningar, från och med orsaksfältet **Avvisning**, fältet **Anställningstyp** och fältet **tjänsteåldertyp**.</span><span class="sxs-lookup"><span data-stu-id="3c75b-108">New capabilities have been introduced to extend the option sets, beginning with the **Rejection** reason field, **Employment type** field, and **Seniority type** field.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3c75b-109">Jobbpublicering till LinkedIn-funktionen kräver användning av fälten **Anställningstyp** och **Tjänsteåldertyp** på sidan **Projektdetaljer**.</span><span class="sxs-lookup"><span data-stu-id="3c75b-109">The job posting to LinkedIn functionality requires the use of the **Employment type** and **Seniority type** fields on the **Job details** page.</span></span> <span data-ttu-id="3c75b-110">Standardvärden i dessa fält stöds av LinkedIn och visas när jobbet har publicerats.</span><span class="sxs-lookup"><span data-stu-id="3c75b-110">The default values in these fields are supported by LinkedIn and are displayed when the job is posted.</span></span> <span data-ttu-id="3c75b-111">Om du publicerar jobb på LinkedIn och du ändrar befintliga alternativuppsättningsvärden i fälten, kommer jobbet fortfarande publiceras och LinkedIn visar inte de anpassade värdena för **Anställningstyp** och **Tjänsteåldertyp**.</span><span class="sxs-lookup"><span data-stu-id="3c75b-111">If you are posting jobs to LinkedIn and you modify the existing option set values for these fields, the job will still post, but LinkedIn will not display the custom **Employment type** and **Seniority type** values.</span></span>

## <a name="changes-in-onboarding"></a><span data-ttu-id="3c75b-112">Ändringar i Onboard</span><span class="sxs-lookup"><span data-stu-id="3c75b-112">Changes in Onboarding</span></span>

### <a name="private-preview-for-onboard-teams"></a><span data-ttu-id="3c75b-113">Privat förhandsgranskning för Onboard-team</span><span class="sxs-lookup"><span data-stu-id="3c75b-113">Private preview for Onboard teams</span></span>
<span data-ttu-id="3c75b-114">Nu kan du enkelt dela och samarbeta på mallar i hela organisationen.</span><span class="sxs-lookup"><span data-stu-id="3c75b-114">You can now easily share and collaborate on templates across your entire organization.</span></span> <span data-ttu-id="3c75b-115">Mer information finns i [dela regelverk inom företaget med Onboard-teams](https://docs.microsoft.com/en-us/business-applications-release-notes/April19/dynamics365-talent/onboard/share-best-practices-teams).</span><span class="sxs-lookup"><span data-stu-id="3c75b-115">For more information, see [Share best practices across your organization using Onboard Teams](https://docs.microsoft.com/en-us/business-applications-release-notes/April19/dynamics365-talent/onboard/share-best-practices-teams).</span></span>

### <a name="private-preview-for-assignee-placeholders"></a><span data-ttu-id="3c75b-116">Privat förhandsgranskning för tilldelade platshållare</span><span class="sxs-lookup"><span data-stu-id="3c75b-116">Private preview for assignee placeholders</span></span>
<span data-ttu-id="3c75b-117">Du kan utöka dina mallar genom att tilldela aktiviteter till roller i stället för individer.</span><span class="sxs-lookup"><span data-stu-id="3c75b-117">You can enrich your templates by assigning activities to roles instead of individuals.</span></span> <span data-ttu-id="3c75b-118">Roller tilldelas sedan individer när guiden skapas.</span><span class="sxs-lookup"><span data-stu-id="3c75b-118">Roles are then assigned to individuals at the time of guide creation.</span></span> <span data-ttu-id="3c75b-119">Mer information finns i [Förenkla guideadministration genom att tilldela aktiviteter till roller](https://docs.microsoft.com/en-us/business-applications-release-notes/April19/dynamics365-talent/onboard/assign-activities-roles).</span><span class="sxs-lookup"><span data-stu-id="3c75b-119">For more information, see [Streamline guide administration by assigning activities to roles](https://docs.microsoft.com/en-us/business-applications-release-notes/April19/dynamics365-talent/onboard/assign-activities-roles).</span></span>

## <a name="changes-in-core-hr"></a><span data-ttu-id="3c75b-120">Ändringar i Core HR</span><span class="sxs-lookup"><span data-stu-id="3c75b-120">Changes in Core HR</span></span>
<span data-ttu-id="3c75b-121">**Skapa 8.1.2178**</span><span class="sxs-lookup"><span data-stu-id="3c75b-121">**Build 8.1.2178**</span></span>

### <a name="configure-workflow-to-auto-approve-or-follow-workflow-when-an-hr-or-line-manager-submits-or-updates-time-off-requests"></a><span data-ttu-id="3c75b-122">Konfigurera arbetsflödet till att automatiskt godkänna eller följa arbetsflöde när en personal- eller linjechef skickar eller uppdaterar begäran om ledighet</span><span class="sxs-lookup"><span data-stu-id="3c75b-122">Configure workflow to auto-approve or follow workflow when an HR or line manager submits or updates time off requests</span></span>
<span data-ttu-id="3c75b-123">Nya arbetsflödesvillkor har lagts till för att tillåta att begäran om ledighet godkänns automatiskt om den lämnas in av en anställds chef eller av HR.</span><span class="sxs-lookup"><span data-stu-id="3c75b-123">New workflow conditions have been added to allow for leave requests to be automatically approved if submitted by an employee’s manager or by HR.</span></span> <span data-ttu-id="3c75b-124">Ett sätt att åstadkomma detta automatiska godkännande i ett arbetsflöde är att aktivera en automatisk åtgärd för arbetsflödesgodkännande.</span><span class="sxs-lookup"><span data-stu-id="3c75b-124">One way to achieve this auto-approval on a workflow is to enable an automatic action on the workflow approval.</span></span>

<span data-ttu-id="3c75b-125">Villkoret som har lagts till inkluderar:</span><span class="sxs-lookup"><span data-stu-id="3c75b-125">The conditions that have been added include:</span></span>

- <span data-ttu-id="3c75b-126">Inskickad av - används för att utvärdera systemanvändar-ID för den användare som skickade förfrågan till arbetsflödet.</span><span class="sxs-lookup"><span data-stu-id="3c75b-126">Submitted by - Used to evaluate the system user ID of the user who submitted the request to workflow.</span></span>
- <span data-ttu-id="3c75b-127">Skickad på uppdrag av - används för att utvärdera om ledighetsbegäran skickades på uppdrag av arbetaren som är kopplat till begäran.</span><span class="sxs-lookup"><span data-stu-id="3c75b-127">Submitted on behalf of - Used to evaluate if the leave request was submitted on behalf of the worker associated to the request.</span></span>
- <span data-ttu-id="3c75b-128">Skickad av personal - används för att utvärdera om systemanvändaren som skickade begäran till arbetsflödet är i en personalroll.</span><span class="sxs-lookup"><span data-stu-id="3c75b-128">Submitted by human resources - Used to evaluate if the system user who submitted the request to workflow is in a Human Resources role.</span></span>
- <span data-ttu-id="3c75b-129">Skickad av chef – används för att utvärdera om användaren som skickade begäran om ledighet till arbetsflödet är en radhierarkichef för arbetaren som är kopplad till begäran.</span><span class="sxs-lookup"><span data-stu-id="3c75b-129">Submitted by manager - Used to evaluate if the user who submitted the leave request to workflow is a line hierarchy manager of the worker associated to the request.</span></span>

### <a name="enable-employee-fixed-compensation-for-future-position-assignments"></a><span data-ttu-id="3c75b-130">Aktivera medarbetarens fasta kompensation för framtida befattningstilldelningar</span><span class="sxs-lookup"><span data-stu-id="3c75b-130">Enable employee fixed compensation for future position assignments</span></span>
<span data-ttu-id="3c75b-131">Detta gäller för medarbetare som ansluter sig till en organisation med startdatum i framtiden.</span><span class="sxs-lookup"><span data-stu-id="3c75b-131">It is typical for employees to join an organization with a future start date.</span></span> <span data-ttu-id="3c75b-132">Denna ändring tillåter definition av fast kompensation för anställda med framtida befattningstilldelningar.</span><span class="sxs-lookup"><span data-stu-id="3c75b-132">This change enables defining fixed compensation for employees with future position assignments.</span></span>

### <a name="position-payroll-fields-are-blank-when-editing-the-position"></a><span data-ttu-id="3c75b-133">Fälten för löneposition är tomma när du redigerar befattningen</span><span class="sxs-lookup"><span data-stu-id="3c75b-133">Position Payroll fields are blank when editing the position</span></span>
<span data-ttu-id="3c75b-134">Med denna ändring, när du begär ändringar i befintliga befattningar, kommer lönefälten nu anges till de aktuella värdena.</span><span class="sxs-lookup"><span data-stu-id="3c75b-134">With this change, when requesting changes to existing positions, the payroll fields will now default to the current values.</span></span>

### <a name="other-miscellaneous-bug-fixes"></a><span data-ttu-id="3c75b-135">Diverse andra felkorrigeringar</span><span class="sxs-lookup"><span data-stu-id="3c75b-135">Other miscellaneous bug fixes</span></span>
<span data-ttu-id="3c75b-136">Den här versionen innehåller andra mindre felkorrigeringar.</span><span class="sxs-lookup"><span data-stu-id="3c75b-136">Other minor bug fixes are included with this release.</span></span>

### <a name="upgrade-to-cds-for-apps"></a><span data-ttu-id="3c75b-137">Uppgradera till CDS för appar</span><span class="sxs-lookup"><span data-stu-id="3c75b-137">Upgrade to CDS for Apps</span></span>
<span data-ttu-id="3c75b-138">Tidsgränser för uppgradering till CDS för appar närmar sig snabbt.</span><span class="sxs-lookup"><span data-stu-id="3c75b-138">Deadlines to upgrade to CDS for Apps are quickly approaching.</span></span> <span data-ttu-id="3c75b-139">Logga in på PowerApps administrationscenter för att avgöra om databasen måste uppgraderas.</span><span class="sxs-lookup"><span data-stu-id="3c75b-139">Sign in to the PowerApps Admin center to determine if your database needs to be upgraded.</span></span> <span data-ttu-id="3c75b-140">Mer information om deadlines och nödvändiga instruktioner för uppgradering finns i [uppgraderar till Common Data Service för appar](https://docs.microsoft.com/en-us/common-data-service/upgradecds/introduction-upgrade-cds).</span><span class="sxs-lookup"><span data-stu-id="3c75b-140">For more information about deadlines and necessary steps to upgrade, see [Upgrade to Common Data Service for Apps](https://docs.microsoft.com/en-us/common-data-service/upgradecds/introduction-upgrade-cds).</span></span>

## <a name="coming-soon"></a><span data-ttu-id="3c75b-141">Kommer snart</span><span class="sxs-lookup"><span data-stu-id="3c75b-141">Coming soon</span></span>

###  <a name="advanced-compensation-security-fixed-and-variable"></a><span data-ttu-id="3c75b-142">Avancerad kompensationssäkerhet (fasta och rörliga)</span><span class="sxs-lookup"><span data-stu-id="3c75b-142">Advanced compensation security (fixed and variable)</span></span>
<span data-ttu-id="3c75b-143">I många organisationer kan kompensations- och förmånsansvariga bara komma åt vissa kompensationsposter, t.ex. poster för chefer eller regionsbaserade anställda.</span><span class="sxs-lookup"><span data-stu-id="3c75b-143">In many organizations, compensation and benefits managers can only access certain compensation records, such as records for executives or regional-based employees.</span></span> <span data-ttu-id="3c75b-144">Med den här ändringen kan du hantera och underhålla kompensationsplaner för olika medarbetare i organisationen.</span><span class="sxs-lookup"><span data-stu-id="3c75b-144">With this change, you can manage and maintain the compensation plans for different employee populations in the organization.</span></span> <span data-ttu-id="3c75b-145">Fasta och variabla planer kan tilldelas säkerhetsroller som bestämmer åtkomsten till planer och medarbetardata relaterade till planerna, till exempel lön eller bonusposter.</span><span class="sxs-lookup"><span data-stu-id="3c75b-145">Fixed and variable plans can be assigned security roles, which will determine the access to the plans and the employee data related to the plans, such as salary or bonus records.</span></span> <span data-ttu-id="3c75b-146">Endast roller med viss åtkomst ska kunna bearbeta kompensation för dessa anställda.</span><span class="sxs-lookup"><span data-stu-id="3c75b-146">Only the roles with the given access will be able to process compensation for those employees.</span></span>

###  <a name="platform-update-24"></a><span data-ttu-id="3c75b-147">Plattform update 24</span><span class="sxs-lookup"><span data-stu-id="3c75b-147">Platform update 24</span></span>
<span data-ttu-id="3c75b-148">Ytterligare information om plattformsuppdatering 24 finns i [Nyheter eller ändringar i Finance and Operations plattformsuppdatering 24 (mars 2019)](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/get-started/whats-new-platform-update-24).</span><span class="sxs-lookup"><span data-stu-id="3c75b-148">For additional details about Platform update 24, see [What's new or changed in Finance and Operations platform update 24 (March 2019)](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/get-started/whats-new-platform-update-24).</span></span>
