---
title: "Mobil arbetsyta för projekttidangivelse"
description: "Det här avsnittet innehåller information om Mobil arbetsyta för projekttidangivelse. Den här arbetsytan låter användarna ange och spara tid för ett projekt genom att använda sin mobilenhet."
author: KimANelson
manager: AnnBe
ms.date: 12/01/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 272101
ms.assetid: 4505f021-b9bb-4b87-be24-6bf0bd88ee60
ms.search.region: Global
ms.search.industry: Service industries
ms.author: knelson
ms.dyn365.ops.intro: Version 1611
ms.search.validFrom: 2016-11-30
ms.translationtype: HT
ms.sourcegitcommit: 6e64337f19600b18320550d91c134949c33af7b0
ms.openlocfilehash: c04ffccdcbf104b1d5db30a41116663fcedd4e1d
ms.contentlocale: sv-se
ms.lasthandoff: 12/01/2017

---

# <a name="project-time-entry-mobile-workspace"></a><span data-ttu-id="61c48-104">Mobil arbetsyta för projekttidangivelse</span><span class="sxs-lookup"><span data-stu-id="61c48-104">Project time entry mobile workspace</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="61c48-105">Det här avsnittet innehåller information om den mobila arbetsytan **Projekttidsangivelse**.</span><span class="sxs-lookup"><span data-stu-id="61c48-105">This topic provides information about the **Project time entry** mobile workspace.</span></span> <span data-ttu-id="61c48-106">Den här arbetsytan låter användarna ange och spara tid för ett projekt genom att använda sin mobilenhet.</span><span class="sxs-lookup"><span data-stu-id="61c48-106">This workspace lets users enter and save time against a project by using their mobile device.</span></span>

<span data-ttu-id="61c48-107">Denna mobila arbetsyta är avsedd att användas med mobilappen Microsoft Dynamics 365 for Unified Operations.</span><span class="sxs-lookup"><span data-stu-id="61c48-107">This mobile workspace is intended to be used with the Microsoft Dynamics 365 for Unified Operations mobile app.</span></span> 

## <a name="overview"></a><span data-ttu-id="61c48-108">Översikt</span><span class="sxs-lookup"><span data-stu-id="61c48-108">Overview</span></span>
<span data-ttu-id="61c48-109">Som ett led i sitt dagliga arbete är projektresurser ofta på plats eller på resande fot.</span><span class="sxs-lookup"><span data-stu-id="61c48-109">As part of their daily work, project resources are often on-site or traveling.</span></span> <span data-ttu-id="61c48-110">Arbetsytan för **projekttidangivelse** låter användarna mata in sin fakturerbara tid eller ej fakturerbara tid mot ett projekt på den mobila enheten efter eget val.</span><span class="sxs-lookup"><span data-stu-id="61c48-110">The **Project time entry** mobile workspace lets users enter their billable or non-billable time against a project on the mobile device of their choice.</span></span> <span data-ttu-id="61c48-111">Därför registrerar projektresurser tidangivelse när som helst och var som helst.</span><span class="sxs-lookup"><span data-stu-id="61c48-111">Therefore, project resources can record time entries anytime and anywhere.</span></span> <span data-ttu-id="61c48-112">De kan också visa tidangivelse som redan har registrerats.</span><span class="sxs-lookup"><span data-stu-id="61c48-112">They can also view time entries that have already been recorded.</span></span> 

<span data-ttu-id="61c48-113">I den mobila arbetsytan **Projekttidsangivelse** kan användarna utföra följande uppgifter:</span><span class="sxs-lookup"><span data-stu-id="61c48-113">Specifically, in the **Project time entry** mobile workspace, users can perform these tasks:</span></span>

-   <span data-ttu-id="61c48-114">Ange antalet timmar som du ägnar till en specifik uppgift för alla valda datum.</span><span class="sxs-lookup"><span data-stu-id="61c48-114">For any selected date, enter the number of hours that you spent on a specific task.</span></span>
-   <span data-ttu-id="61c48-115">Sök efter projektnamn eller kund och hitta projektet du vill registrera tid för.</span><span class="sxs-lookup"><span data-stu-id="61c48-115">Search by project name or customer to find the project to enter time for.</span></span>
-   <span data-ttu-id="61c48-116">Ange kategori och aktivitet under den tid som du ägnar.</span><span class="sxs-lookup"><span data-stu-id="61c48-116">Specify the category and activity for the time that you spent.</span></span>
-   <span data-ttu-id="61c48-117">Ange hur mycket tid som är fakturerbar tid eller ej fakturerbart för projektet.</span><span class="sxs-lookup"><span data-stu-id="61c48-117">Record the time as billable or non-billable for the project.</span></span>
-   <span data-ttu-id="61c48-118">Ange eventuella interna eller externa kommentarer.</span><span class="sxs-lookup"><span data-stu-id="61c48-118">Optionally enter any external or internal comments.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="61c48-119">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="61c48-119">Prerequisites</span></span>
<span data-ttu-id="61c48-120">Kraven varierar baserat på versionen av Microsoft Dynamics 365 som har distribuerats i organisationen.</span><span class="sxs-lookup"><span data-stu-id="61c48-120">The prerequisites differ, based on the version of Microsoft Dynamics 365 that has been deployed for your organization.</span></span>

### <a name="prerequisites-if-you-use-microsoft-dynamics-365-for-finance-and-operations-enterprise-edition"></a><span data-ttu-id="61c48-121">Förutsättningar om du använder Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="61c48-121">Prerequisites if you use Microsoft Dynamics 365 for Finance and Operations, Enterprise edition</span></span>
<span data-ttu-id="61c48-122">Om Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition används inom din organisation måste systemadministratören publicera den mobila arbetsytan **Projekttidsangivelse**.</span><span class="sxs-lookup"><span data-stu-id="61c48-122">If Microsoft Dynamics 365 for Finance and Operations, Enterprise edition has been deployed for your organization, the system administrator must publish the **Project time entry** mobile workspace.</span></span> <span data-ttu-id="61c48-123">Instruktioner finns i [Publicera en mobil arbetsyta](../../dev-itpro/mobile-apps/publish-mobile-workspace.md).</span><span class="sxs-lookup"><span data-stu-id="61c48-123">For instructions, see [Publish a mobile workspace](../../dev-itpro/mobile-apps/publish-mobile-workspace.md).</span></span>

### <a name="prerequisites-if-you-use-microsoft-dynamics-365-for-operations-version-1611-with-platform-update-3-or-later"></a><span data-ttu-id="61c48-124">Krav om du använder Microsoft Dynamics 365 for Operations version 1611 med plattformsuppdatering 3 eller senare</span><span class="sxs-lookup"><span data-stu-id="61c48-124">Prerequisites if you use Microsoft Dynamics 365 for Operations version 1611 with platform update 3 or later</span></span>
<span data-ttu-id="61c48-125">Om Microsoft Dynamics 365 for Operations version 1611 med plattformsuppdatering 3 eller senare har använts i organisationen måste systemadministratören uppfylla följande krav.</span><span class="sxs-lookup"><span data-stu-id="61c48-125">If Microsoft Dynamics 365 for Operations version 1611 with platform update 3 or later has been deployed for your organization, the system administrator must complete the following prerequisites.</span></span> 

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="61c48-126">Förutsättning</span><span class="sxs-lookup"><span data-stu-id="61c48-126">Prerequisite</span></span></th>
<th><span data-ttu-id="61c48-127">Roll</span><span class="sxs-lookup"><span data-stu-id="61c48-127">Role</span></span></th>
<th><span data-ttu-id="61c48-128">beskrivning</span><span class="sxs-lookup"><span data-stu-id="61c48-128">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">

<td><span data-ttu-id="61c48-129">Implementera KB 4018050.</span><span class="sxs-lookup"><span data-stu-id="61c48-129">Implement KB 4018050.</span></span></td>
<td><span data-ttu-id="61c48-130">Systemadministratör</span><span class="sxs-lookup"><span data-stu-id="61c48-130">System administrator</span></span></td>
<td><span data-ttu-id="61c48-131">KB 4018050 är X ++ uppdatering eller snabbkorrigering av metadata som innehåller den mobila arbetsytan för <strong>projekttidangivelse</strong>.</span><span class="sxs-lookup"><span data-stu-id="61c48-131">KB 4018050 is an X++ update or metadata hotfix that contains the <strong>Project time entry</strong> mobile workspace.</span></span> <span data-ttu-id="61c48-132">Om du vill implementera KB 4018050 måste systemadministratören göra följande.</span><span class="sxs-lookup"><span data-stu-id="61c48-132">To implement KB 4018050, your system administrator must follow these steps.</span></span>
<ol>
<li><span data-ttu-id="61c48-133"><a href="../../dev-itpro/migration-upgrade/download-hotfix-lcs.md">Hämta snabbkorrigering av metadata från Microsoft Dynamics AX Lifecycle Services(LCS)</a>.</span><span class="sxs-lookup"><span data-stu-id="61c48-133"><a href="../../dev-itpro/migration-upgrade/download-hotfix-lcs.md">Download the metadata hotfix from Microsoft Dynamics Lifecycle Services (LCS)</a>.</span></span></li>
<li><span data-ttu-id="61c48-134"><a href="../../dev-itpro/migration-upgrade/install-metadata-hotfix-package.md">Snabbkorrigering av metadata</a>.</span><span class="sxs-lookup"><span data-stu-id="61c48-134"><a href="../../dev-itpro/migration-upgrade/install-metadata-hotfix-package.md">Install the metadata hotfix</a>.</span></span></li>
<li><span data-ttu-id="61c48-135"><a href="../../dev-itpro/deployment/create-apply-deployable-package.md">Skapa ett driftfärdigt paket</a> som innehåller modellerna <strong>ApplicationSuite</strong> och <strong>ProjectMobile</strong> och överför sedan det driftfärdiga paketet till LCS.</span><span class="sxs-lookup"><span data-stu-id="61c48-135"><a href="../../dev-itpro/deployment/create-apply-deployable-package.md">Create a deployable package</a> that contains the <strong>ApplicationSuite</strong> and <strong>ProjectMobile</strong> models, and then upload the deployable package to LCS.</span></span></li>
<li><span data-ttu-id="61c48-136"><a href="../../dev-itpro/deployment/apply-deployable-package-system.md">Tillämpa ett distribuerbart paket</a></span><span class="sxs-lookup"><span data-stu-id="61c48-136"><a href="../../dev-itpro/deployment/apply-deployable-package-system.md">Apply the deployable package</a>.</span></span></li>

</ol></td>
</tr>
<tr class="even">
<td><span data-ttu-id="61c48-137">Publicera den mobila arbetsytan <strong>Projekttidsangivelse</strong>.</span><span class="sxs-lookup"><span data-stu-id="61c48-137">Publish the <strong>Project time entry</strong> mobile workspace.</span></span></td>
<td><span data-ttu-id="61c48-138">Systemadministratör</span><span class="sxs-lookup"><span data-stu-id="61c48-138">System administrator</span></span></td>
<td><span data-ttu-id="61c48-139">Se <a href="../../dev-itpro/mobile-apps/publish-mobile-workspace.md">Publicera en mobil arbetsyta</a>.</span><span class="sxs-lookup"><span data-stu-id="61c48-139">See <a href="../../dev-itpro/mobile-apps/publish-mobile-workspace.md">Publish a mobile workspace</a>.</span></span></td>
</tr>
</tbody>
</table>

## <a name="download-and-install-the-mobile-app"></a><span data-ttu-id="61c48-140">Hämta och installera mobilappen</span><span class="sxs-lookup"><span data-stu-id="61c48-140">Download and install the mobile app</span></span>

<span data-ttu-id="61c48-141">Hämta och installera mobilappen Dynamics 365 for Unified Operations:</span><span class="sxs-lookup"><span data-stu-id="61c48-141">Download and install the Dynamics 365 for Unified Operations mobile app:</span></span>

-   [<span data-ttu-id="61c48-142">För Android-telefoner</span><span class="sxs-lookup"><span data-stu-id="61c48-142">For Android phones</span></span>](https://go.microsoft.com/fwlink/?linkid=850662)
-   [<span data-ttu-id="61c48-143">För iPhones</span><span class="sxs-lookup"><span data-stu-id="61c48-143">For iPhones</span></span>](https://go.microsoft.com/fwlink/?linkid=850663)

## <a name="sign-in-to-the-mobile-app"></a><span data-ttu-id="61c48-144">Logga in på mobilappen</span><span class="sxs-lookup"><span data-stu-id="61c48-144">Sign in to the mobile app</span></span>
1.  <span data-ttu-id="61c48-145">Starta appen i din mobila enhet.</span><span class="sxs-lookup"><span data-stu-id="61c48-145">Start the app on your mobile device.</span></span>
2.  <span data-ttu-id="61c48-146">Ange din webbadress för Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="61c48-146">Enter your Dynamics 365 URL.</span></span>
3.  <span data-ttu-id="61c48-147">Första gången du loggar in uppmanas du ange användarnamn och lösenord.</span><span class="sxs-lookup"><span data-stu-id="61c48-147">The first time that you sign in, you're prompted for your user name and password.</span></span> <span data-ttu-id="61c48-148">Ange dina autentiseringsuppgifter.</span><span class="sxs-lookup"><span data-stu-id="61c48-148">Enter your credentials.</span></span>
4.  <span data-ttu-id="61c48-149">När du loggar in visas tillgängliga arbetsytor för ditt företag.</span><span class="sxs-lookup"><span data-stu-id="61c48-149">After you sign in, the available workspaces for your company are shown.</span></span> <span data-ttu-id="61c48-150">Observera att om systemadministratören publicerar en ny arbetsyta senare kan du dra om du vill uppdatera listan över mobila arbetsytor.</span><span class="sxs-lookup"><span data-stu-id="61c48-150">Note that if your system administrator publishes a new workspace later, you will have to refresh the list of mobile workspaces.</span></span>

<span data-ttu-id="61c48-151">[![Dra för att uppdatera](./media/pull-to-refresh-list-of-workspaces-183x300.png)](./media/pull-to-refresh-list-of-workspaces.png)</span><span class="sxs-lookup"><span data-stu-id="61c48-151">[![Pull to refresh](./media/pull-to-refresh-list-of-workspaces-183x300.png)](./media/pull-to-refresh-list-of-workspaces.png)</span></span>

## <a name="enter-time-by-using-the-project-time-entry-mobile-workspace"></a><span data-ttu-id="61c48-152">Ange tid genom att använda mobila arbetsytan för projekttidangivelse</span><span class="sxs-lookup"><span data-stu-id="61c48-152">Enter time by using the Project time entry mobile workspace</span></span>
1.  <span data-ttu-id="61c48-153">På din mobila enhet väljer du arbetsytan **projekttidangivelse**.</span><span class="sxs-lookup"><span data-stu-id="61c48-153">On your mobile device, select the **Project time entry** workspace.</span></span>
2.  <span data-ttu-id="61c48-154">Välj **tidangivelse**.</span><span class="sxs-lookup"><span data-stu-id="61c48-154">Select **Time entry**.</span></span> <span data-ttu-id="61c48-155">Du kan se kalenderdatum för den aktuella veckan.</span><span class="sxs-lookup"><span data-stu-id="61c48-155">The calendar dates for the current week are shown.</span></span>
3.  <span data-ttu-id="61c48-156">Välj för ett valt datum **åtgärder** &gt; **ny post**.</span><span class="sxs-lookup"><span data-stu-id="61c48-156">For a selected date, select **Actions** &gt; **New entry**.</span></span>
4.  <span data-ttu-id="61c48-157">Ange antalet timmar att registrera.</span><span class="sxs-lookup"><span data-stu-id="61c48-157">Enter the number of hours to record.</span></span>
5.  <span data-ttu-id="61c48-158">Välj nästa projekt för nästa tidsangivelse.</span><span class="sxs-lookup"><span data-stu-id="61c48-158">Select the project for the time entry.</span></span> <span data-ttu-id="61c48-159">En lista visar de projekt som laddas in i din app för användning offline.</span><span class="sxs-lookup"><span data-stu-id="61c48-159">A list shows the projects that are loaded into your app for offline use.</span></span> <span data-ttu-id="61c48-160">50 objekt laddas som standard, men en utvecklare kan ändra detta antal.</span><span class="sxs-lookup"><span data-stu-id="61c48-160">By default, 50 items are loaded, but a developer can change this number.</span></span> <span data-ttu-id="61c48-161">För information, se [Mobil plattform](../../dev-itpro/mobile-apps/platform/mobile-platform-home-page.md).</span><span class="sxs-lookup"><span data-stu-id="61c48-161">For more information, see [Mobile platform](../../dev-itpro/mobile-apps/platform/mobile-platform-home-page.md).</span></span>
6.  <span data-ttu-id="61c48-162">Om projektet inte finns i listan, välj **Sök**.</span><span class="sxs-lookup"><span data-stu-id="61c48-162">If your project isn't in the list, select **Search**.</span></span> <span data-ttu-id="61c48-163">Sök efter namn eller gå till sök efter projektnamn eller kund.</span><span class="sxs-lookup"><span data-stu-id="61c48-163">Search by name, or switch to search by project name or customer.</span></span>
7.  <span data-ttu-id="61c48-164">Markera en kategori.</span><span class="sxs-lookup"><span data-stu-id="61c48-164">Select a category.</span></span> <span data-ttu-id="61c48-165">En lista visar de kategorier som laddas in i din app för användning offline.</span><span class="sxs-lookup"><span data-stu-id="61c48-165">A list shows the categories that are loaded into your app for offline use.</span></span> <span data-ttu-id="61c48-166">50 objekt laddas som standard, men en utvecklare kan ändra detta antal.</span><span class="sxs-lookup"><span data-stu-id="61c48-166">By default, 50 items are loaded, but a developer can change this number.</span></span> <span data-ttu-id="61c48-167">För information, se [Mobil plattform](../../dev-itpro/mobile-apps/platform/mobile-platform-home-page.md).</span><span class="sxs-lookup"><span data-stu-id="61c48-167">For more information, see [Mobile platform](../../dev-itpro/mobile-apps/platform/mobile-platform-home-page.md).</span></span>
8.  <span data-ttu-id="61c48-168">Om kategorin inte finns i listan, välj **Sök**.</span><span class="sxs-lookup"><span data-stu-id="61c48-168">If your category isn't in the list, select **Search**.</span></span> <span data-ttu-id="61c48-169">Sök efter kategori eller växla om du vill söka efter kategorinamnet.</span><span class="sxs-lookup"><span data-stu-id="61c48-169">Search by category, or switch to search by category name.</span></span>
9.  <span data-ttu-id="61c48-170">Välj en aktivitet.</span><span class="sxs-lookup"><span data-stu-id="61c48-170">Select an activity.</span></span> <span data-ttu-id="61c48-171">En lista visar de aktiviteter som laddas in i din app för användning offline.</span><span class="sxs-lookup"><span data-stu-id="61c48-171">A list shows the activities that are loaded into your app for offline use.</span></span> <span data-ttu-id="61c48-172">50 objekt laddas som standard, men en utvecklare kan ändra detta antal.</span><span class="sxs-lookup"><span data-stu-id="61c48-172">By default, 50 items are loaded, but a developer can change this number.</span></span> <span data-ttu-id="61c48-173">För information, se [Mobil plattform](../../dev-itpro/mobile-apps/platform/mobile-platform-home-page.md).</span><span class="sxs-lookup"><span data-stu-id="61c48-173">For more information, see [Mobile platform](../../dev-itpro/mobile-apps/platform/mobile-platform-home-page.md).</span></span>
10. <span data-ttu-id="61c48-174">Om aktiviteten inte finns i listan, välj **Sök**.</span><span class="sxs-lookup"><span data-stu-id="61c48-174">If your activity isn't in the list, select **Search**.</span></span> <span data-ttu-id="61c48-175">Sök efter aktivitetsnummer eller växla till att söka efter funktion.</span><span class="sxs-lookup"><span data-stu-id="61c48-175">Search by activity number, or switch to search by purpose.</span></span>

11. <span data-ttu-id="61c48-176">Välj radegenskapen.</span><span class="sxs-lookup"><span data-stu-id="61c48-176">Select the line property.</span></span>
12. <span data-ttu-id="61c48-177">Tillval: Ange eventuella interna och externa kommentarer.</span><span class="sxs-lookup"><span data-stu-id="61c48-177">Optional: Enter any external and internal comments.</span></span>
13. <span data-ttu-id="61c48-178">Välj **Klar**.</span><span class="sxs-lookup"><span data-stu-id="61c48-178">Select **Done**.</span></span>

