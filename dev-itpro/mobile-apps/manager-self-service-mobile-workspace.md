---
title: "Mobil arbetsyta för mitt team"
description: "Detta avsnitt innehåller information om den mobila arbetsytan för mitt team, som låter mmanagers visa deras underställda och utökade personal. Användare kan också skicka beröm till enskilda personer i sin rapporteringskedja."
author: ShielaSogge
manager: AnnBe
ms.date: 06/16/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: sericks
ms.search.scope: Talent, Operations, UnifiedOperations
ms.search.region: Global
ms.author: shielas
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.translationtype: Human Translation
ms.sourcegitcommit: 08c38aada355583c5a6872f75b57db95d9b81786
ms.openlocfilehash: 0bfbc07130e908a1326cd01522038fc90bb3465f
ms.contentlocale: sv-se
ms.lasthandoff: 07/18/2017

---

# <a name="my-team-mobile-workspace"></a><span data-ttu-id="95877-104">Mobil arbetsyta för mitt team</span><span class="sxs-lookup"><span data-stu-id="95877-104">My team mobile workspace</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="95877-105">Det här avsnittet innehåller information om den mobila arbetsytan **Mitt team**.</span><span class="sxs-lookup"><span data-stu-id="95877-105">This topic provides information about the **My team** mobile workspace.</span></span> <span data-ttu-id="95877-106">Den här arbetsytan låter chefer visa sina underställda och utökade personal.</span><span class="sxs-lookup"><span data-stu-id="95877-106">This workspace lets managers view their direct reports and extended staff.</span></span> <span data-ttu-id="95877-107">De kan också skicka beröm till enskilda personer i sin rapporteringskedja.</span><span class="sxs-lookup"><span data-stu-id="95877-107">They can also send praise to individuals in their reporting chain.</span></span>

<span data-ttu-id="95877-108">Denna mobila arbetsyta är avsedd att användas med mobilappen Microsoft Dynamics 365 for Unified Operations.</span><span class="sxs-lookup"><span data-stu-id="95877-108">This mobile workspace is intended to be used with the Microsoft Dynamics 365 for Unified Operations mobile app.</span></span>

## <a name="overview"></a><span data-ttu-id="95877-109">Översikt</span><span class="sxs-lookup"><span data-stu-id="95877-109">Overview</span></span> 
<span data-ttu-id="95877-110">Den mobila arbetsytan **Mitt team** låter cheferna utföra följande uppgifter:</span><span class="sxs-lookup"><span data-stu-id="95877-110">The **My team** mobile workspace lets managers perform these tasks:</span></span>

- <span data-ttu-id="95877-111">Visa en lista över chefens underställda.</span><span class="sxs-lookup"><span data-stu-id="95877-111">View a list of the manager’s direct reports.</span></span>
- <span data-ttu-id="95877-112">Visa en lista över chefens utökade rapporteringsteam.</span><span class="sxs-lookup"><span data-stu-id="95877-112">View a list of the manager’s extended reporting team.</span></span>
- <span data-ttu-id="95877-113">Visa detaljerad information för varje medlem i teamet, till exempel födelsedatum, datum för tjänsteålder, antal tjänsteår, samt information om kompensation och resultat.</span><span class="sxs-lookup"><span data-stu-id="95877-113">View detailed information for each team member, such as birth date, seniority date, years of service, and compensation and performance information.</span></span>
- <span data-ttu-id="95877-114">Skicka beröm till en person i chefens utökade rapporteringsteam.</span><span class="sxs-lookup"><span data-stu-id="95877-114">Send praise to any individual in the manager’s extended reporting team.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="95877-115">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="95877-115">Prerequisites</span></span>
<span data-ttu-id="95877-116">Följande förutsättningar måste vara uppfyllda innan du kan använda den här mobila arbetsytan.</span><span class="sxs-lookup"><span data-stu-id="95877-116">Before you can use this mobile workspace, the following prerequisites must be met.</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="95877-117">Förutsättning</span><span class="sxs-lookup"><span data-stu-id="95877-117">Prerequisite</span></span></th>
<th><span data-ttu-id="95877-118">Roll</span><span class="sxs-lookup"><span data-stu-id="95877-118">Role</span></span></th>
<th><span data-ttu-id="95877-119">beskrivning</span><span class="sxs-lookup"><span data-stu-id="95877-119">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="95877-120">Någon av följande produkter måste distribueras i organisationen:</span><span class="sxs-lookup"><span data-stu-id="95877-120">One of the following products must be deployed in your organization:</span></span>
<ul><li><span data-ttu-id="95877-121">Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition, juli 2017 uppdatering</span><span class="sxs-lookup"><span data-stu-id="95877-121">Microsoft Dynamics 365 for Finance and Operations, Enterprise edition July 2017 update</span></span></li>
<li><span data-ttu-id="95877-122">Microsoft Dynamics 365 for Talent</span><span class="sxs-lookup"><span data-stu-id="95877-122">Microsoft Dynamics 365 for Talent</span></span></li>
</ul>
</td>
<td><span data-ttu-id="95877-123">Systemadministratör</span><span class="sxs-lookup"><span data-stu-id="95877-123">System administrator</span></span></td>
<td><span data-ttu-id="95877-124">Om du inte redan använder Finance and Operations i din organisation, se <a href="../deployment/deploy-demo-environment.md">Distribuera en demomiljö</a>.</span><span class="sxs-lookup"><span data-stu-id="95877-124">If you don't already have Finance and Operations deployed in your organization, see <a href="../deployment/deploy-demo-environment.md">Deploy a demo environment</a>.</span></span> <span data-ttu-id="95877-125">Om du inte redan använder Talent i din organisation kan systemadministratören komma åt en utvärderingsversion från webbsidan <a href="https://www.microsoft.com/en-us/dynamics365/talent">Talent-användare</a>.</span><span class="sxs-lookup"><span data-stu-id="95877-125">If you don't already have Talent deployed in your organization, the system administrator can access a trial version from the <a href="https://www.microsoft.com/en-us/dynamics365/talent">Talent webpage</a>.</span></span>
</td>
</tr>
<tr class="even">
<td><span data-ttu-id="95877-126">Den mobila arbetsytan <strong>Mitt team</strong> måste publiceras.</span><span class="sxs-lookup"><span data-stu-id="95877-126">The <strong>My team</strong> mobile workspace must be published.</span></span></td>
<td><span data-ttu-id="95877-127">Systemadministratör</span><span class="sxs-lookup"><span data-stu-id="95877-127">System administrator</span></span></td>
<td><span data-ttu-id="95877-128">Se <a href="/dynamics365/unified-operations/dev-itpro/mobile-apps/publish-mobile-workspace">Publicera en mobil arbetsyta</a>.</span><span class="sxs-lookup"><span data-stu-id="95877-128">See <a href="/dynamics365/unified-operations/dev-itpro/mobile-apps/publish-mobile-workspace">Publish a mobile workspace</a>.</span></span></td>
</tr>
</tbody>
</table>

## <a name="download-and-install-the-mobile-app"></a><span data-ttu-id="95877-129">Hämta och installera mobilappen</span><span class="sxs-lookup"><span data-stu-id="95877-129">Download and install the mobile app</span></span>

<span data-ttu-id="95877-130">Hämta och installera mobilappen Dynamics 365 for Unified Operations:</span><span class="sxs-lookup"><span data-stu-id="95877-130">Download and install the Dynamics 365 for Unified Operations mobile app:</span></span>

-   [<span data-ttu-id="95877-131">För Android-telefoner</span><span class="sxs-lookup"><span data-stu-id="95877-131">For Android phones</span></span>](https://go.microsoft.com/fwlink/?linkid=850662)
-   [<span data-ttu-id="95877-132">För iPhones</span><span class="sxs-lookup"><span data-stu-id="95877-132">For iPhones</span></span>](https://go.microsoft.com/fwlink/?linkid=850663)

## <a name="sign-in-to-the-mobile-app"></a><span data-ttu-id="95877-133">Logga in på mobilappen</span><span class="sxs-lookup"><span data-stu-id="95877-133">Sign in to the mobile app</span></span>
1.  <span data-ttu-id="95877-134">Starta appen i din mobila enhet.</span><span class="sxs-lookup"><span data-stu-id="95877-134">Start the app on your mobile device.</span></span>
2.  <span data-ttu-id="95877-135">Ange din webbadress för Microsoft Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="95877-135">Enter your Microsoft Dynamics 365 URL.</span></span>
3.  <span data-ttu-id="95877-136">Första gången du loggar in uppmanas du ange användarnamn och lösenord.</span><span class="sxs-lookup"><span data-stu-id="95877-136">The first time that you sign in, you're prompted for your user name and password.</span></span> <span data-ttu-id="95877-137">Ange dina autentiseringsuppgifter.</span><span class="sxs-lookup"><span data-stu-id="95877-137">Enter your credentials.</span></span>
4.  <span data-ttu-id="95877-138">När du loggar in visas tillgängliga arbetsytor för ditt företag.</span><span class="sxs-lookup"><span data-stu-id="95877-138">After you sign in, the available workspaces for your company are shown.</span></span> <span data-ttu-id="95877-139">Observera att om systemadministratören publicerar en ny arbetsyta senare kan du dra om du vill uppdatera listan över mobila arbetsytor.</span><span class="sxs-lookup"><span data-stu-id="95877-139">Note that if your system administrator publishes a new workspace later, you will have to refresh the list of mobile workspaces.</span></span>

<span data-ttu-id="95877-140">[![Dra för att uppdatera](./media/pull-to-refresh-list-of-workspaces-183x300.png)](./media/pull-to-refresh-list-of-workspaces.png)</span><span class="sxs-lookup"><span data-stu-id="95877-140">[![Pull to refresh](./media/pull-to-refresh-list-of-workspaces-183x300.png)](./media/pull-to-refresh-list-of-workspaces.png)</span></span>

## <a name="view-team-members-by-using-the-my-team-mobile-workspace"></a><span data-ttu-id="95877-141">Visa team-medlemmar via arbetsytan för Mitt team</span><span class="sxs-lookup"><span data-stu-id="95877-141">View team members by using the My team mobile workspace</span></span>
1.  <span data-ttu-id="95877-142">I mobilappen väljer du arbetsytan **Mitt team**.</span><span class="sxs-lookup"><span data-stu-id="95877-142">In the mobile app, select the **My team** workspace.</span></span> <span data-ttu-id="95877-143">En lista över team-medlemmar visas.</span><span class="sxs-lookup"><span data-stu-id="95877-143">A list of team members is shown.</span></span> <span data-ttu-id="95877-144">Listan visar också varje enskild team-medlems titel, samt alla eventuella underställda som han eller hon har.</span><span class="sxs-lookup"><span data-stu-id="95877-144">The list also shows each team member's title, and any direct reports that he or she has.</span></span>
2.  <span data-ttu-id="95877-145">Välj en teammedlem</span><span class="sxs-lookup"><span data-stu-id="95877-145">Select a team member.</span></span> <span data-ttu-id="95877-146">Sidan **Sammanfattning för teammedlem** visas.</span><span class="sxs-lookup"><span data-stu-id="95877-146">The **Team member summary** page appears.</span></span> <span data-ttu-id="95877-147">Informationen på denna sida innehåller teammedlemmarnas födelsedatum, tjänsteålder, antal tjänsteår, år i aktuell befattning samt kompensationsinformation.</span><span class="sxs-lookup"><span data-stu-id="95877-147">The information on this page includes the team member's birth date, seniority date, years of service, years in his or her current position, and compensation information.</span></span>

## <a name="view-extended-team-members-by-using-the-my-team-mobile-workspace"></a><span data-ttu-id="95877-148">Visa utökade teammedlemmar via arbetsytan för Mitt team</span><span class="sxs-lookup"><span data-stu-id="95877-148">View extended team members by using the My team mobile workspace</span></span>
1.  <span data-ttu-id="95877-149">I mobilappen väljer du arbetsytan **Mitt team**.</span><span class="sxs-lookup"><span data-stu-id="95877-149">In the mobile app, select the **My team** workspace.</span></span> <span data-ttu-id="95877-150">En lista över team-medlemmar visas.</span><span class="sxs-lookup"><span data-stu-id="95877-150">A list of team members is shown.</span></span> <span data-ttu-id="95877-151">Listan visar också varje enskild team-medlems titel, samt alla eventuella underställda som han eller hon har.</span><span class="sxs-lookup"><span data-stu-id="95877-151">The list also shows each team member's title, and any direct reports that he or she has.</span></span>
1.  <span data-ttu-id="95877-152">Välj länken **Underställda**.</span><span class="sxs-lookup"><span data-stu-id="95877-152">Select the **Direct reports** link.</span></span> <span data-ttu-id="95877-153">En lista över ditt utökade team visas.</span><span class="sxs-lookup"><span data-stu-id="95877-153">A list of your extended team is shown.</span></span>
1.  <span data-ttu-id="95877-154">Välj en teammedlem</span><span class="sxs-lookup"><span data-stu-id="95877-154">Select a team member.</span></span> <span data-ttu-id="95877-155">Sidan **Sammanfattning för teammedlem** visas.</span><span class="sxs-lookup"><span data-stu-id="95877-155">The **Team member summary** page appears.</span></span> <span data-ttu-id="95877-156">Informationen på denna sida innehåller teammedlemmarnas födelsedatum, tjänsteålder, antal tjänsteår, år i aktuell befattning samt kompensationsinformation.</span><span class="sxs-lookup"><span data-stu-id="95877-156">The information on this page includes the team member's birth date, seniority date, years of service, years in his or her current position, and compensation information.</span></span>

## <a name="send-praise-about-team-members-by-using-the-my-team-mobile-workspace"></a><span data-ttu-id="95877-157">Skicka beröm om teammedlemmar via arbetsytan för Mitt team</span><span class="sxs-lookup"><span data-stu-id="95877-157">Send praise about team members by using the My team mobile workspace</span></span>
1.  <span data-ttu-id="95877-158">I mobilappen väljer du arbetsytan **Mitt team**.</span><span class="sxs-lookup"><span data-stu-id="95877-158">In the mobile app, select the **My team** workspace.</span></span> <span data-ttu-id="95877-159">En lista över team-medlemmar visas.</span><span class="sxs-lookup"><span data-stu-id="95877-159">A list of team members is shown.</span></span> <span data-ttu-id="95877-160">Listan visar också varje enskild team-medlems titel, samt alla eventuella underställda som han eller hon har.</span><span class="sxs-lookup"><span data-stu-id="95877-160">The list also shows each team member's title, and any direct reports that he or she has.</span></span>
1.  <span data-ttu-id="95877-161">Välj en teammedlem</span><span class="sxs-lookup"><span data-stu-id="95877-161">Select a team member.</span></span> <span data-ttu-id="95877-162">Sidan **Sammanfattning för teammedlem** visas.</span><span class="sxs-lookup"><span data-stu-id="95877-162">The **Team member summary** page appears.</span></span>
1.  <span data-ttu-id="95877-163">Välj **Skicka beröm**.</span><span class="sxs-lookup"><span data-stu-id="95877-163">Select **Send praise**.</span></span> 
1. <span data-ttu-id="95877-164">Ange den berömtext som du vill skicka.</span><span class="sxs-lookup"><span data-stu-id="95877-164">Enter the text of the praise that you want to send.</span></span> 
1. <span data-ttu-id="95877-165">Välj **Klar**.</span><span class="sxs-lookup"><span data-stu-id="95877-165">Select **Done**.</span></span>

