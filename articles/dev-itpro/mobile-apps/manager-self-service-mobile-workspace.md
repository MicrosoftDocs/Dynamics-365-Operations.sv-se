---
title: Mobil arbetsyta för mitt team
description: Detta avsnitt innehåller information om den mobila arbetsytan för mitt team, som låter chefer se sina underställda och utökad personal. Användare kan också skicka beröm till enskilda personer i sin rapporteringskedja.
author: ShielaSogge
manager: AnnBe
ms.date: 12/01/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: sericks
ms.search.scope: Operations, Talent
ms.search.region: Global
ms.author: shielas
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.openlocfilehash: fccbedea611228cc57531c89406f72a6664153c7
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2019
ms.locfileid: "346926"
---
# <a name="my-team-mobile-workspace"></a><span data-ttu-id="d190a-104">Mobil arbetsyta för mitt team</span><span class="sxs-lookup"><span data-stu-id="d190a-104">My team mobile workspace</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="d190a-105">Det här avsnittet innehåller information om den mobila arbetsytan **Mitt team**.</span><span class="sxs-lookup"><span data-stu-id="d190a-105">This topic provides information about the **My team** mobile workspace.</span></span> <span data-ttu-id="d190a-106">Den här arbetsytan låter chefer visa sina underställda och utökade personal.</span><span class="sxs-lookup"><span data-stu-id="d190a-106">This workspace lets managers view their direct reports and extended staff.</span></span> <span data-ttu-id="d190a-107">De kan också skicka beröm till enskilda personer i sin rapporteringskedja.</span><span class="sxs-lookup"><span data-stu-id="d190a-107">They can also send praise to individuals in their reporting chain.</span></span>

<span data-ttu-id="d190a-108">Denna mobila arbetsyta är avsedd att användas med mobilappen Microsoft Dynamics 365 for Unified Operations Mobile.</span><span class="sxs-lookup"><span data-stu-id="d190a-108">This mobile workspace is intended to be used with the Microsoft Dynamics 365 for Unified Operations mobile app.</span></span>

## <a name="overview"></a><span data-ttu-id="d190a-109">Översikt</span><span class="sxs-lookup"><span data-stu-id="d190a-109">Overview</span></span> 
<span data-ttu-id="d190a-110">Den mobila arbetsytan **Mitt team** låter cheferna utföra följande uppgifter:</span><span class="sxs-lookup"><span data-stu-id="d190a-110">The **My team** mobile workspace lets managers perform these tasks:</span></span>

- <span data-ttu-id="d190a-111">Visa en lista över chefens underställda.</span><span class="sxs-lookup"><span data-stu-id="d190a-111">View a list of the manager’s direct reports.</span></span>
- <span data-ttu-id="d190a-112">Visa en lista över chefens utökade rapporteringsteam.</span><span class="sxs-lookup"><span data-stu-id="d190a-112">View a list of the manager’s extended reporting team.</span></span>
- <span data-ttu-id="d190a-113">Visa detaljerad information för varje medlem i teamet, till exempel födelsedatum, datum för tjänsteålder, antal tjänsteår, samt information om kompensation och resultat.</span><span class="sxs-lookup"><span data-stu-id="d190a-113">View detailed information for each team member, such as birth date, seniority date, years of service, and compensation and performance information.</span></span>
- <span data-ttu-id="d190a-114">Skicka beröm till en person i chefens utökade rapporteringsteam.</span><span class="sxs-lookup"><span data-stu-id="d190a-114">Send praise to any individual in the manager’s extended reporting team.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="d190a-115">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="d190a-115">Prerequisites</span></span>
<span data-ttu-id="d190a-116">Följande förutsättningar måste vara uppfyllda innan du kan använda den här mobila arbetsytan.</span><span class="sxs-lookup"><span data-stu-id="d190a-116">Before you can use this mobile workspace, the following prerequisites must be met.</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="d190a-117">Förutsättning</span><span class="sxs-lookup"><span data-stu-id="d190a-117">Prerequisite</span></span></th>
<th><span data-ttu-id="d190a-118">Roll</span><span class="sxs-lookup"><span data-stu-id="d190a-118">Role</span></span></th>
<th><span data-ttu-id="d190a-119">beskrivning</span><span class="sxs-lookup"><span data-stu-id="d190a-119">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="d190a-120">Någon av följande produkter måste distribueras i organisationen:</span><span class="sxs-lookup"><span data-stu-id="d190a-120">One of the following products must be deployed in your organization:</span></span>
<ul><li><span data-ttu-id="d190a-121">Microsoft Dynamics 365 for Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="d190a-121">Microsoft Dynamics 365 for Finance and Operations</span></span></li>
<li><span data-ttu-id="d190a-122">Microsoft Dynamics 365 for Talent</span><span class="sxs-lookup"><span data-stu-id="d190a-122">Microsoft Dynamics 365 for Talent</span></span></li>
</ul>
</td>
<td><span data-ttu-id="d190a-123">Systemadministratör</span><span class="sxs-lookup"><span data-stu-id="d190a-123">System administrator</span></span></td>
<td><span data-ttu-id="d190a-124">Om du inte redan använder Finance and Operations i din organisation, se <a href="../deployment/deploy-demo-environment.md"> Distribuera en demomiljö</a>.</span><span class="sxs-lookup"><span data-stu-id="d190a-124">If you don&#39;t already have Finance and Operations deployed in your organization, see <a href="../deployment/deploy-demo-environment.md">Deploy a demo environment</a>.</span></span> <span data-ttu-id="d190a-125">Om du inte redan använder Talent i din organisation kan systemadministratören komma åt en utvärderingsversion från <a href="https://www.microsoft.com/en-us/dynamics365/talent">webbsidan Talent</a>.</span><span class="sxs-lookup"><span data-stu-id="d190a-125">If you don&#39;t already have Talent deployed in your organization, the system administrator can access a trial version from the <a href="https://www.microsoft.com/en-us/dynamics365/talent">Talent webpage</a>.</span></span>
</td>
</tr>
<tr class="even">
<td><span data-ttu-id="d190a-126">Den mobila arbetsytan <strong>Mitt team</strong> måste publiceras.</span><span class="sxs-lookup"><span data-stu-id="d190a-126">The <strong>My team</strong> mobile workspace must be published.</span></span></td>
<td><span data-ttu-id="d190a-127">Systemadministratör</span><span class="sxs-lookup"><span data-stu-id="d190a-127">System administrator</span></span></td>
<td><span data-ttu-id="d190a-128">Se <a href="publish-mobile-workspace.md">Publicera en mobil arbetsyta</a>.</span><span class="sxs-lookup"><span data-stu-id="d190a-128">See <a href="publish-mobile-workspace.md">Publish a mobile workspace</a>.</span></span></td>
</tr>
</tbody>
</table>

## <a name="download-and-install-the-mobile-app"></a><span data-ttu-id="d190a-129">Hämta och installera mobilappen</span><span class="sxs-lookup"><span data-stu-id="d190a-129">Download and install the mobile app</span></span>

<span data-ttu-id="d190a-130">Hämta och installera mobilappen Dynamics 365 for Unified Operations:</span><span class="sxs-lookup"><span data-stu-id="d190a-130">Download and install the Dynamics 365 for Unified Operations mobile app:</span></span>

-   [<span data-ttu-id="d190a-131">För Android-telefoner</span><span class="sxs-lookup"><span data-stu-id="d190a-131">For Android phones</span></span>](https://go.microsoft.com/fwlink/?linkid=850662)
-   [<span data-ttu-id="d190a-132">För iPhones</span><span class="sxs-lookup"><span data-stu-id="d190a-132">For iPhones</span></span>](https://go.microsoft.com/fwlink/?linkid=850663)

## <a name="sign-in-to-the-mobile-app"></a><span data-ttu-id="d190a-133">Logga in på mobilappen</span><span class="sxs-lookup"><span data-stu-id="d190a-133">Sign in to the mobile app</span></span>
1.  <span data-ttu-id="d190a-134">Starta appen i din mobila enhet.</span><span class="sxs-lookup"><span data-stu-id="d190a-134">Start the app on your mobile device.</span></span>
2.  <span data-ttu-id="d190a-135">Ange din Microsoft Dynamics 365 URL.</span><span class="sxs-lookup"><span data-stu-id="d190a-135">Enter your Microsoft Dynamics 365 URL.</span></span>
3.  <span data-ttu-id="d190a-136">Första gången du loggar in uppmanas du ange användarnamn och lösenord.</span><span class="sxs-lookup"><span data-stu-id="d190a-136">The first time that you sign in, you're prompted for your user name and password.</span></span> <span data-ttu-id="d190a-137">Ange dina autentiseringsuppgifter.</span><span class="sxs-lookup"><span data-stu-id="d190a-137">Enter your credentials.</span></span>
4.  <span data-ttu-id="d190a-138">När du loggar in visas tillgängliga arbetsytor för ditt företag.</span><span class="sxs-lookup"><span data-stu-id="d190a-138">After you sign in, the available workspaces for your company are shown.</span></span> <span data-ttu-id="d190a-139">Observera att om systemadministratören publicerar en ny arbetsyta senare kan du dra om du vill uppdatera listan över mobila arbetsytor.</span><span class="sxs-lookup"><span data-stu-id="d190a-139">Note that if your system administrator publishes a new workspace later, you will have to refresh the list of mobile workspaces.</span></span>

<span data-ttu-id="d190a-140">[![Dra för att uppdatera](./media/pull-to-refresh-list-of-workspaces-183x300.png)](./media/pull-to-refresh-list-of-workspaces.png)</span><span class="sxs-lookup"><span data-stu-id="d190a-140">[![Pull to refresh](./media/pull-to-refresh-list-of-workspaces-183x300.png)](./media/pull-to-refresh-list-of-workspaces.png)</span></span>

## <a name="view-team-members-by-using-the-my-team-mobile-workspace"></a><span data-ttu-id="d190a-141">Visa team-medlemmar via arbetsytan för Mitt team</span><span class="sxs-lookup"><span data-stu-id="d190a-141">View team members by using the My team mobile workspace</span></span>
1.  <span data-ttu-id="d190a-142">I mobilappen väljer du arbetsytan **Mitt team**.</span><span class="sxs-lookup"><span data-stu-id="d190a-142">In the mobile app, select the **My team** workspace.</span></span> <span data-ttu-id="d190a-143">En lista över team-medlemmar visas.</span><span class="sxs-lookup"><span data-stu-id="d190a-143">A list of team members is shown.</span></span> <span data-ttu-id="d190a-144">Listan visar också varje enskild team-medlems titel, samt alla eventuella underställda som han eller hon har.</span><span class="sxs-lookup"><span data-stu-id="d190a-144">The list also shows each team member's title, and any direct reports that he or she has.</span></span>
2.  <span data-ttu-id="d190a-145">Välj en teammedlem</span><span class="sxs-lookup"><span data-stu-id="d190a-145">Select a team member.</span></span> <span data-ttu-id="d190a-146">Sidan **Sammanfattning för teammedlem** visas.</span><span class="sxs-lookup"><span data-stu-id="d190a-146">The **Team member summary** page appears.</span></span> <span data-ttu-id="d190a-147">Informationen på denna sida innehåller teammedlemmarnas födelsedatum, tjänsteålder, antal tjänsteår, år i aktuell befattning samt kompensationsinformation.</span><span class="sxs-lookup"><span data-stu-id="d190a-147">The information on this page includes the team member's birth date, seniority date, years of service, years in his or her current position, and compensation information.</span></span>

## <a name="view-extended-team-members-by-using-the-my-team-mobile-workspace"></a><span data-ttu-id="d190a-148">Visa utökade teammedlemmar via arbetsytan för Mitt team</span><span class="sxs-lookup"><span data-stu-id="d190a-148">View extended team members by using the My team mobile workspace</span></span>
1.  <span data-ttu-id="d190a-149">I mobilappen väljer du arbetsytan **Mitt team**.</span><span class="sxs-lookup"><span data-stu-id="d190a-149">In the mobile app, select the **My team** workspace.</span></span> <span data-ttu-id="d190a-150">En lista över team-medlemmar visas.</span><span class="sxs-lookup"><span data-stu-id="d190a-150">A list of team members is shown.</span></span> <span data-ttu-id="d190a-151">Listan visar också varje enskild team-medlems titel, samt alla eventuella underställda som han eller hon har.</span><span class="sxs-lookup"><span data-stu-id="d190a-151">The list also shows each team member's title, and any direct reports that he or she has.</span></span>
1.  <span data-ttu-id="d190a-152">Välj länken **Underställda**.</span><span class="sxs-lookup"><span data-stu-id="d190a-152">Select the **Direct reports** link.</span></span> <span data-ttu-id="d190a-153">En lista över ditt utökade team visas.</span><span class="sxs-lookup"><span data-stu-id="d190a-153">A list of your extended team is shown.</span></span>
1.  <span data-ttu-id="d190a-154">Välj en teammedlem</span><span class="sxs-lookup"><span data-stu-id="d190a-154">Select a team member.</span></span> <span data-ttu-id="d190a-155">Sidan **Sammanfattning för teammedlem** visas.</span><span class="sxs-lookup"><span data-stu-id="d190a-155">The **Team member summary** page appears.</span></span> <span data-ttu-id="d190a-156">Informationen på denna sida innehåller teammedlemmarnas födelsedatum, tjänsteålder, antal tjänsteår, år i aktuell befattning samt kompensationsinformation.</span><span class="sxs-lookup"><span data-stu-id="d190a-156">The information on this page includes the team member's birth date, seniority date, years of service, years in his or her current position, and compensation information.</span></span>

## <a name="send-praise-about-team-members-by-using-the-my-team-mobile-workspace"></a><span data-ttu-id="d190a-157">Skicka beröm om teammedlemmar via arbetsytan för Mitt team</span><span class="sxs-lookup"><span data-stu-id="d190a-157">Send praise about team members by using the My team mobile workspace</span></span>
1.  <span data-ttu-id="d190a-158">I mobilappen väljer du arbetsytan **Mitt team**.</span><span class="sxs-lookup"><span data-stu-id="d190a-158">In the mobile app, select the **My team** workspace.</span></span> <span data-ttu-id="d190a-159">En lista över team-medlemmar visas.</span><span class="sxs-lookup"><span data-stu-id="d190a-159">A list of team members is shown.</span></span> <span data-ttu-id="d190a-160">Listan visar också varje enskild team-medlems titel, samt alla eventuella underställda som han eller hon har.</span><span class="sxs-lookup"><span data-stu-id="d190a-160">The list also shows each team member's title, and any direct reports that he or she has.</span></span>
1.  <span data-ttu-id="d190a-161">Välj en teammedlem</span><span class="sxs-lookup"><span data-stu-id="d190a-161">Select a team member.</span></span> <span data-ttu-id="d190a-162">Sidan **Sammanfattning för teammedlem** visas.</span><span class="sxs-lookup"><span data-stu-id="d190a-162">The **Team member summary** page appears.</span></span>
1.  <span data-ttu-id="d190a-163">Välj **Skicka beröm**.</span><span class="sxs-lookup"><span data-stu-id="d190a-163">Select **Send praise**.</span></span> 
1. <span data-ttu-id="d190a-164">Ange den berömtext som du vill skicka.</span><span class="sxs-lookup"><span data-stu-id="d190a-164">Enter the text of the praise that you want to send.</span></span> 
1. <span data-ttu-id="d190a-165">Välj **Klar**.</span><span class="sxs-lookup"><span data-stu-id="d190a-165">Select **Done**.</span></span>
