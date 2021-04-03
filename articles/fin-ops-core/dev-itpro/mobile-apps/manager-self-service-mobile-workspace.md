---
title: Mobil arbetsyta för mitt team
description: Detta avsnitt innehåller information om den mobila arbetsytan för mitt team, som låter chefer se sina underställda och utökad personal.
author: ShielaSogge
manager: AnnBe
ms.date: 12/01/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.author: shielas
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.openlocfilehash: 5dc2f8b5195fb5210ca6399cbf744f210671f475
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/09/2021
ms.locfileid: "5570102"
---
# <a name="my-team-mobile-workspace"></a><span data-ttu-id="18f0c-103">Mobil arbetsyta för mitt team</span><span class="sxs-lookup"><span data-stu-id="18f0c-103">My team mobile workspace</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="18f0c-104">Det här avsnittet innehåller information om den mobila arbetsytan **Mitt team**.</span><span class="sxs-lookup"><span data-stu-id="18f0c-104">This topic provides information about the **My team** mobile workspace.</span></span> <span data-ttu-id="18f0c-105">Den här arbetsytan låter chefer visa sina underställda och utökade personal.</span><span class="sxs-lookup"><span data-stu-id="18f0c-105">This workspace lets managers view their direct reports and extended staff.</span></span> <span data-ttu-id="18f0c-106">De kan också skicka beröm till enskilda personer i sin rapporteringskedja.</span><span class="sxs-lookup"><span data-stu-id="18f0c-106">They can also send praise to individuals in their reporting chain.</span></span>

<span data-ttu-id="18f0c-107">Denna mobila arbetsyta är avsedd att användas med mobilappen Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="18f0c-107">This mobile workspace is intended to be used with the Finance and Operations mobile app.</span></span>

## <a name="overview"></a><span data-ttu-id="18f0c-108">Översikt</span><span class="sxs-lookup"><span data-stu-id="18f0c-108">Overview</span></span> 
<span data-ttu-id="18f0c-109">Den mobila arbetsytan **Mitt team** låter cheferna utföra följande uppgifter:</span><span class="sxs-lookup"><span data-stu-id="18f0c-109">The **My team** mobile workspace lets managers perform these tasks:</span></span>

- <span data-ttu-id="18f0c-110">Visa en lista över chefens underställda.</span><span class="sxs-lookup"><span data-stu-id="18f0c-110">View a list of the manager’s direct reports.</span></span>
- <span data-ttu-id="18f0c-111">Visa en lista över chefens utökade rapporteringsteam.</span><span class="sxs-lookup"><span data-stu-id="18f0c-111">View a list of the manager’s extended reporting team.</span></span>
- <span data-ttu-id="18f0c-112">Visa detaljerad information för varje medlem i teamet, till exempel födelsedatum, datum för tjänsteålder, antal tjänsteår, samt information om kompensation och resultat.</span><span class="sxs-lookup"><span data-stu-id="18f0c-112">View detailed information for each team member, such as birth date, seniority date, years of service, and compensation and performance information.</span></span>
- <span data-ttu-id="18f0c-113">Skicka beröm till en person i chefens utökade rapporteringsteam.</span><span class="sxs-lookup"><span data-stu-id="18f0c-113">Send praise to any individual in the manager’s extended reporting team.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="18f0c-114">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="18f0c-114">Prerequisites</span></span>
<span data-ttu-id="18f0c-115">Följande förutsättningar måste vara uppfyllda innan du kan använda den här mobila arbetsytan.</span><span class="sxs-lookup"><span data-stu-id="18f0c-115">Before you can use this mobile workspace, the following prerequisites must be met.</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="18f0c-116">Förutsättning</span><span class="sxs-lookup"><span data-stu-id="18f0c-116">Prerequisite</span></span></th>
<th><span data-ttu-id="18f0c-117">Roll</span><span class="sxs-lookup"><span data-stu-id="18f0c-117">Role</span></span></th>
<th><span data-ttu-id="18f0c-118">beskrivning</span><span class="sxs-lookup"><span data-stu-id="18f0c-118">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="18f0c-119">Någon av följande produkter måste distribueras i organisationen:</span><span class="sxs-lookup"><span data-stu-id="18f0c-119">One of the following products must be deployed in your organization:</span></span>
<ul><li><span data-ttu-id="18f0c-120">En Finance and Operations-app</span><span class="sxs-lookup"><span data-stu-id="18f0c-120">A Finance and Operations app</span></span></li>
<li><span data-ttu-id="18f0c-121">Microsoft Dynamics 365 Human Resources</span><span class="sxs-lookup"><span data-stu-id="18f0c-121">Microsoft Dynamics 365 Human Resources</span></span></li>
</ul>
</td>
<td><span data-ttu-id="18f0c-122">Systemadministratör</span><span class="sxs-lookup"><span data-stu-id="18f0c-122">System administrator</span></span></td>
<td><span data-ttu-id="18f0c-123">Om du inte &#39;redan har en Finance and Operations-app i din organisation, se <a href="../deployment/deploy-demo-environment.md">Distribuera en demomiljö</a>.</span><span class="sxs-lookup"><span data-stu-id="18f0c-123">If you don&#39;t already have a Finance and Operations app deployed in your organization, see <a href="../deployment/deploy-demo-environment.md">Deploy a demo environment</a>.</span></span> <span data-ttu-id="18f0c-124">Om du inte redan använder Personal i din organisation kan systemadministratören komma åt en utvärderingsversion från <a href="https://dynamics.microsoft.com/human-resources/overview/">webbsidan Personal</a>.</span><span class="sxs-lookup"><span data-stu-id="18f0c-124">If you don&#39;t already have Human Resources deployed in your organization, the system administrator can access a trial version from the <a href="https://dynamics.microsoft.com/human-resources/overview/">Human Resources webpage</a>.</span></span>
</td>
</tr>
<tr class="even">
<td><span data-ttu-id="18f0c-125">Den mobila arbetsytan <strong>Mitt team</strong> måste publiceras.</span><span class="sxs-lookup"><span data-stu-id="18f0c-125">The <strong>My team</strong> mobile workspace must be published.</span></span></td>
<td><span data-ttu-id="18f0c-126">Systemadministratör</span><span class="sxs-lookup"><span data-stu-id="18f0c-126">System administrator</span></span></td>
<td><span data-ttu-id="18f0c-127">Se <a href="publish-mobile-workspace.md">Publicera en mobil arbetsyta</a>.</span><span class="sxs-lookup"><span data-stu-id="18f0c-127">See <a href="publish-mobile-workspace.md">Publish a mobile workspace</a>.</span></span></td>
</tr>
</tbody>
</table>

## <a name="download-and-install-the-mobile-app"></a><span data-ttu-id="18f0c-128">Hämta och installera mobilappen</span><span class="sxs-lookup"><span data-stu-id="18f0c-128">Download and install the mobile app</span></span>

<span data-ttu-id="18f0c-129">Hämta och installera mobilappen Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="18f0c-129">Download and install the Finance and Operations mobile app:</span></span>

-   [<span data-ttu-id="18f0c-130">För Android-telefoner</span><span class="sxs-lookup"><span data-stu-id="18f0c-130">For Android phones</span></span>](https://go.microsoft.com/fwlink/?linkid=850662)
-   [<span data-ttu-id="18f0c-131">För iPhones</span><span class="sxs-lookup"><span data-stu-id="18f0c-131">For iPhones</span></span>](https://go.microsoft.com/fwlink/?linkid=850663)

## <a name="sign-in-to-the-mobile-app"></a><span data-ttu-id="18f0c-132">Logga in på mobilappen</span><span class="sxs-lookup"><span data-stu-id="18f0c-132">Sign in to the mobile app</span></span>
1.  <span data-ttu-id="18f0c-133">Starta appen i din mobila enhet.</span><span class="sxs-lookup"><span data-stu-id="18f0c-133">Start the app on your mobile device.</span></span>
2.  <span data-ttu-id="18f0c-134">Ange din Microsoft Dynamics 365 URL.</span><span class="sxs-lookup"><span data-stu-id="18f0c-134">Enter your Microsoft Dynamics 365 URL.</span></span>
3.  <span data-ttu-id="18f0c-135">Första gången du loggar in uppmanas du ange användarnamn och lösenord.</span><span class="sxs-lookup"><span data-stu-id="18f0c-135">The first time that you sign in, you're prompted for your user name and password.</span></span> <span data-ttu-id="18f0c-136">Ange dina autentiseringsuppgifter.</span><span class="sxs-lookup"><span data-stu-id="18f0c-136">Enter your credentials.</span></span>
4.  <span data-ttu-id="18f0c-137">När du loggar in visas tillgängliga arbetsytor för ditt företag.</span><span class="sxs-lookup"><span data-stu-id="18f0c-137">After you sign in, the available workspaces for your company are shown.</span></span> <span data-ttu-id="18f0c-138">Observera att om systemadministratören publicerar en ny arbetsyta senare kan du dra om du vill uppdatera listan över mobila arbetsytor.</span><span class="sxs-lookup"><span data-stu-id="18f0c-138">Note that if your system administrator publishes a new workspace later, you will have to refresh the list of mobile workspaces.</span></span>

<span data-ttu-id="18f0c-139">[![Dra för att uppdatera](./media/pull-to-refresh-list-of-workspaces-183x300.png)](./media/pull-to-refresh-list-of-workspaces.png)</span><span class="sxs-lookup"><span data-stu-id="18f0c-139">[![Pull to refresh](./media/pull-to-refresh-list-of-workspaces-183x300.png)](./media/pull-to-refresh-list-of-workspaces.png)</span></span>

## <a name="view-team-members-by-using-the-my-team-mobile-workspace"></a><span data-ttu-id="18f0c-140">Visa team-medlemmar via arbetsytan för Mitt team</span><span class="sxs-lookup"><span data-stu-id="18f0c-140">View team members by using the My team mobile workspace</span></span>
1.  <span data-ttu-id="18f0c-141">I mobilappen väljer du arbetsytan **Mitt team**.</span><span class="sxs-lookup"><span data-stu-id="18f0c-141">In the mobile app, select the **My team** workspace.</span></span> <span data-ttu-id="18f0c-142">En lista över team-medlemmar visas.</span><span class="sxs-lookup"><span data-stu-id="18f0c-142">A list of team members is shown.</span></span> <span data-ttu-id="18f0c-143">Listan visar också varje enskild teammedlems titel, samt alla eventuella underställda som medlemmen har.</span><span class="sxs-lookup"><span data-stu-id="18f0c-143">The list also shows each team member's title, and any direct reports that the member has.</span></span>
2.  <span data-ttu-id="18f0c-144">Välj en teammedlem</span><span class="sxs-lookup"><span data-stu-id="18f0c-144">Select a team member.</span></span> <span data-ttu-id="18f0c-145">Sidan **Sammanfattning för teammedlem** visas.</span><span class="sxs-lookup"><span data-stu-id="18f0c-145">The **Team member summary** page appears.</span></span> <span data-ttu-id="18f0c-146">Informationen på denna sida innehåller teammedlemmarnas födelsedatum, tjänsteålder, antal tjänsteår, år i den aktuella befattningen samt kompensationsinformation.</span><span class="sxs-lookup"><span data-stu-id="18f0c-146">The information on this page includes the team member's birth date, seniority date, years of service, years in the current position, and compensation information.</span></span>

## <a name="view-extended-team-members-by-using-the-my-team-mobile-workspace"></a><span data-ttu-id="18f0c-147">Visa utökade teammedlemmar via arbetsytan för Mitt team</span><span class="sxs-lookup"><span data-stu-id="18f0c-147">View extended team members by using the My team mobile workspace</span></span>
1.  <span data-ttu-id="18f0c-148">I mobilappen väljer du arbetsytan **Mitt team**.</span><span class="sxs-lookup"><span data-stu-id="18f0c-148">In the mobile app, select the **My team** workspace.</span></span> <span data-ttu-id="18f0c-149">En lista över team-medlemmar visas.</span><span class="sxs-lookup"><span data-stu-id="18f0c-149">A list of team members is shown.</span></span> <span data-ttu-id="18f0c-150">Listan visar också varje enskild teammedlems titel, samt alla eventuella underställda som medlemmen har.</span><span class="sxs-lookup"><span data-stu-id="18f0c-150">The list also shows each team member's title, and any direct reports that the member has.</span></span>
1.  <span data-ttu-id="18f0c-151">Välj länken **Underställda**.</span><span class="sxs-lookup"><span data-stu-id="18f0c-151">Select the **Direct reports** link.</span></span> <span data-ttu-id="18f0c-152">En lista över ditt utökade team visas.</span><span class="sxs-lookup"><span data-stu-id="18f0c-152">A list of your extended team is shown.</span></span>
1.  <span data-ttu-id="18f0c-153">Välj en teammedlem</span><span class="sxs-lookup"><span data-stu-id="18f0c-153">Select a team member.</span></span> <span data-ttu-id="18f0c-154">Sidan **Sammanfattning för teammedlem** visas.</span><span class="sxs-lookup"><span data-stu-id="18f0c-154">The **Team member summary** page appears.</span></span> <span data-ttu-id="18f0c-155">Informationen på denna sida innehåller teammedlemmarnas födelsedatum, tjänsteålder, antal tjänsteår, år i den aktuella befattningen samt kompensationsinformation.</span><span class="sxs-lookup"><span data-stu-id="18f0c-155">The information on this page includes the team member's birth date, seniority date, years of service, years in the current position, and compensation information.</span></span>

## <a name="send-praise-about-team-members-by-using-the-my-team-mobile-workspace"></a><span data-ttu-id="18f0c-156">Skicka beröm om teammedlemmar via arbetsytan för Mitt team</span><span class="sxs-lookup"><span data-stu-id="18f0c-156">Send praise about team members by using the My team mobile workspace</span></span>
1.  <span data-ttu-id="18f0c-157">I mobilappen väljer du arbetsytan **Mitt team**.</span><span class="sxs-lookup"><span data-stu-id="18f0c-157">In the mobile app, select the **My team** workspace.</span></span> <span data-ttu-id="18f0c-158">En lista över team-medlemmar visas.</span><span class="sxs-lookup"><span data-stu-id="18f0c-158">A list of team members is shown.</span></span> <span data-ttu-id="18f0c-159">Listan visar också varje enskild teammedlems titel, samt alla eventuella underställda som medlemmen har.</span><span class="sxs-lookup"><span data-stu-id="18f0c-159">The list also shows each team member's title, and any direct reports that the member has.</span></span>
1.  <span data-ttu-id="18f0c-160">Välj en teammedlem</span><span class="sxs-lookup"><span data-stu-id="18f0c-160">Select a team member.</span></span> <span data-ttu-id="18f0c-161">Sidan **Sammanfattning för teammedlem** visas.</span><span class="sxs-lookup"><span data-stu-id="18f0c-161">The **Team member summary** page appears.</span></span>
1.  <span data-ttu-id="18f0c-162">Välj **Skicka beröm**.</span><span class="sxs-lookup"><span data-stu-id="18f0c-162">Select **Send praise**.</span></span> 
1. <span data-ttu-id="18f0c-163">Ange den berömtext som du vill skicka.</span><span class="sxs-lookup"><span data-stu-id="18f0c-163">Enter the text of the praise that you want to send.</span></span> 
1. <span data-ttu-id="18f0c-164">Välj **Klar**.</span><span class="sxs-lookup"><span data-stu-id="18f0c-164">Select **Done**.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]