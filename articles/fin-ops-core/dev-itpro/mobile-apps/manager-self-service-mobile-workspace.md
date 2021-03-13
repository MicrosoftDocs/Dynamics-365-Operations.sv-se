---
title: Mobil arbetsyta för mitt team
description: Detta avsnitt innehåller information om den mobila arbetsytan för mitt team, som låter chefer se sina underställda och utökad personal.
author: ShielaSogge
manager: AnnBe
ms.date: 12/01/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.author: shielas
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.openlocfilehash: 79678c42545a07054af00cd408e04e9d1a42caed
ms.sourcegitcommit: f8bac7ca2803913fd236adbc3806259a17a110f4
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/06/2021
ms.locfileid: "5127555"
---
# <a name="my-team-mobile-workspace"></a><span data-ttu-id="0f5ee-103">Mobil arbetsyta för mitt team</span><span class="sxs-lookup"><span data-stu-id="0f5ee-103">My team mobile workspace</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="0f5ee-104">Det här avsnittet innehåller information om den mobila arbetsytan **Mitt team**.</span><span class="sxs-lookup"><span data-stu-id="0f5ee-104">This topic provides information about the **My team** mobile workspace.</span></span> <span data-ttu-id="0f5ee-105">Den här arbetsytan låter chefer visa sina underställda och utökade personal.</span><span class="sxs-lookup"><span data-stu-id="0f5ee-105">This workspace lets managers view their direct reports and extended staff.</span></span> <span data-ttu-id="0f5ee-106">De kan också skicka beröm till enskilda personer i sin rapporteringskedja.</span><span class="sxs-lookup"><span data-stu-id="0f5ee-106">They can also send praise to individuals in their reporting chain.</span></span>

<span data-ttu-id="0f5ee-107">Denna mobila arbetsyta är avsedd att användas med mobilappen Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="0f5ee-107">This mobile workspace is intended to be used with the Finance and Operations mobile app.</span></span>

## <a name="overview"></a><span data-ttu-id="0f5ee-108">Översikt</span><span class="sxs-lookup"><span data-stu-id="0f5ee-108">Overview</span></span> 
<span data-ttu-id="0f5ee-109">Den mobila arbetsytan **Mitt team** låter cheferna utföra följande uppgifter:</span><span class="sxs-lookup"><span data-stu-id="0f5ee-109">The **My team** mobile workspace lets managers perform these tasks:</span></span>

- <span data-ttu-id="0f5ee-110">Visa en lista över chefens underställda.</span><span class="sxs-lookup"><span data-stu-id="0f5ee-110">View a list of the manager’s direct reports.</span></span>
- <span data-ttu-id="0f5ee-111">Visa en lista över chefens utökade rapporteringsteam.</span><span class="sxs-lookup"><span data-stu-id="0f5ee-111">View a list of the manager’s extended reporting team.</span></span>
- <span data-ttu-id="0f5ee-112">Visa detaljerad information för varje medlem i teamet, till exempel födelsedatum, datum för tjänsteålder, antal tjänsteår, samt information om kompensation och resultat.</span><span class="sxs-lookup"><span data-stu-id="0f5ee-112">View detailed information for each team member, such as birth date, seniority date, years of service, and compensation and performance information.</span></span>
- <span data-ttu-id="0f5ee-113">Skicka beröm till en person i chefens utökade rapporteringsteam.</span><span class="sxs-lookup"><span data-stu-id="0f5ee-113">Send praise to any individual in the manager’s extended reporting team.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="0f5ee-114">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="0f5ee-114">Prerequisites</span></span>
<span data-ttu-id="0f5ee-115">Följande förutsättningar måste vara uppfyllda innan du kan använda den här mobila arbetsytan.</span><span class="sxs-lookup"><span data-stu-id="0f5ee-115">Before you can use this mobile workspace, the following prerequisites must be met.</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="0f5ee-116">Förutsättning</span><span class="sxs-lookup"><span data-stu-id="0f5ee-116">Prerequisite</span></span></th>
<th><span data-ttu-id="0f5ee-117">Roll</span><span class="sxs-lookup"><span data-stu-id="0f5ee-117">Role</span></span></th>
<th><span data-ttu-id="0f5ee-118">beskrivning</span><span class="sxs-lookup"><span data-stu-id="0f5ee-118">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="0f5ee-119">Någon av följande produkter måste distribueras i organisationen:</span><span class="sxs-lookup"><span data-stu-id="0f5ee-119">One of the following products must be deployed in your organization:</span></span>
<ul><li><span data-ttu-id="0f5ee-120">En Finance and Operations-app</span><span class="sxs-lookup"><span data-stu-id="0f5ee-120">A Finance and Operations app</span></span></li>
<li><span data-ttu-id="0f5ee-121">Microsoft Dynamics 365 Human Resources</span><span class="sxs-lookup"><span data-stu-id="0f5ee-121">Microsoft Dynamics 365 Human Resources</span></span></li>
</ul>
</td>
<td><span data-ttu-id="0f5ee-122">Systemadministratör</span><span class="sxs-lookup"><span data-stu-id="0f5ee-122">System administrator</span></span></td>
<td><span data-ttu-id="0f5ee-123">Om du inte &#39;redan har en Finance and Operations-app i din organisation, se <a href="../deployment/deploy-demo-environment.md">Distribuera en demomiljö</a>.</span><span class="sxs-lookup"><span data-stu-id="0f5ee-123">If you don&#39;t already have a Finance and Operations app deployed in your organization, see <a href="../deployment/deploy-demo-environment.md">Deploy a demo environment</a>.</span></span> <span data-ttu-id="0f5ee-124">Om du inte redan använder Personal i din organisation kan systemadministratören komma åt en utvärderingsversion från <a href="https://dynamics.microsoft.com/human-resources/overview/">webbsidan Personal</a>.</span><span class="sxs-lookup"><span data-stu-id="0f5ee-124">If you don&#39;t already have Human Resources deployed in your organization, the system administrator can access a trial version from the <a href="https://dynamics.microsoft.com/human-resources/overview/">Human Resources webpage</a>.</span></span>
</td>
</tr>
<tr class="even">
<td><span data-ttu-id="0f5ee-125">Den mobila arbetsytan <strong>Mitt team</strong> måste publiceras.</span><span class="sxs-lookup"><span data-stu-id="0f5ee-125">The <strong>My team</strong> mobile workspace must be published.</span></span></td>
<td><span data-ttu-id="0f5ee-126">Systemadministratör</span><span class="sxs-lookup"><span data-stu-id="0f5ee-126">System administrator</span></span></td>
<td><span data-ttu-id="0f5ee-127">Se <a href="publish-mobile-workspace.md">Publicera en mobil arbetsyta</a>.</span><span class="sxs-lookup"><span data-stu-id="0f5ee-127">See <a href="publish-mobile-workspace.md">Publish a mobile workspace</a>.</span></span></td>
</tr>
</tbody>
</table>

## <a name="download-and-install-the-mobile-app"></a><span data-ttu-id="0f5ee-128">Hämta och installera mobilappen</span><span class="sxs-lookup"><span data-stu-id="0f5ee-128">Download and install the mobile app</span></span>

<span data-ttu-id="0f5ee-129">Hämta och installera mobilappen Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="0f5ee-129">Download and install the Finance and Operations mobile app:</span></span>

-   [<span data-ttu-id="0f5ee-130">För Android-telefoner</span><span class="sxs-lookup"><span data-stu-id="0f5ee-130">For Android phones</span></span>](https://go.microsoft.com/fwlink/?linkid=850662)
-   [<span data-ttu-id="0f5ee-131">För iPhones</span><span class="sxs-lookup"><span data-stu-id="0f5ee-131">For iPhones</span></span>](https://go.microsoft.com/fwlink/?linkid=850663)

## <a name="sign-in-to-the-mobile-app"></a><span data-ttu-id="0f5ee-132">Logga in på mobilappen</span><span class="sxs-lookup"><span data-stu-id="0f5ee-132">Sign in to the mobile app</span></span>
1.  <span data-ttu-id="0f5ee-133">Starta appen i din mobila enhet.</span><span class="sxs-lookup"><span data-stu-id="0f5ee-133">Start the app on your mobile device.</span></span>
2.  <span data-ttu-id="0f5ee-134">Ange din Microsoft Dynamics 365 URL.</span><span class="sxs-lookup"><span data-stu-id="0f5ee-134">Enter your Microsoft Dynamics 365 URL.</span></span>
3.  <span data-ttu-id="0f5ee-135">Första gången du loggar in uppmanas du ange användarnamn och lösenord.</span><span class="sxs-lookup"><span data-stu-id="0f5ee-135">The first time that you sign in, you're prompted for your user name and password.</span></span> <span data-ttu-id="0f5ee-136">Ange dina autentiseringsuppgifter.</span><span class="sxs-lookup"><span data-stu-id="0f5ee-136">Enter your credentials.</span></span>
4.  <span data-ttu-id="0f5ee-137">När du loggar in visas tillgängliga arbetsytor för ditt företag.</span><span class="sxs-lookup"><span data-stu-id="0f5ee-137">After you sign in, the available workspaces for your company are shown.</span></span> <span data-ttu-id="0f5ee-138">Observera att om systemadministratören publicerar en ny arbetsyta senare kan du dra om du vill uppdatera listan över mobila arbetsytor.</span><span class="sxs-lookup"><span data-stu-id="0f5ee-138">Note that if your system administrator publishes a new workspace later, you will have to refresh the list of mobile workspaces.</span></span>

<span data-ttu-id="0f5ee-139">[![Dra för att uppdatera](./media/pull-to-refresh-list-of-workspaces-183x300.png)](./media/pull-to-refresh-list-of-workspaces.png)</span><span class="sxs-lookup"><span data-stu-id="0f5ee-139">[![Pull to refresh](./media/pull-to-refresh-list-of-workspaces-183x300.png)](./media/pull-to-refresh-list-of-workspaces.png)</span></span>

## <a name="view-team-members-by-using-the-my-team-mobile-workspace"></a><span data-ttu-id="0f5ee-140">Visa team-medlemmar via arbetsytan för Mitt team</span><span class="sxs-lookup"><span data-stu-id="0f5ee-140">View team members by using the My team mobile workspace</span></span>
1.  <span data-ttu-id="0f5ee-141">I mobilappen väljer du arbetsytan **Mitt team**.</span><span class="sxs-lookup"><span data-stu-id="0f5ee-141">In the mobile app, select the **My team** workspace.</span></span> <span data-ttu-id="0f5ee-142">En lista över team-medlemmar visas.</span><span class="sxs-lookup"><span data-stu-id="0f5ee-142">A list of team members is shown.</span></span> <span data-ttu-id="0f5ee-143">Listan visar också varje enskild teammedlems titel, samt alla eventuella underställda som medlemmen har.</span><span class="sxs-lookup"><span data-stu-id="0f5ee-143">The list also shows each team member's title, and any direct reports that the member has.</span></span>
2.  <span data-ttu-id="0f5ee-144">Välj en teammedlem</span><span class="sxs-lookup"><span data-stu-id="0f5ee-144">Select a team member.</span></span> <span data-ttu-id="0f5ee-145">Sidan **Sammanfattning för teammedlem** visas.</span><span class="sxs-lookup"><span data-stu-id="0f5ee-145">The **Team member summary** page appears.</span></span> <span data-ttu-id="0f5ee-146">Informationen på denna sida innehåller teammedlemmarnas födelsedatum, tjänsteålder, antal tjänsteår, år i den aktuella befattningen samt kompensationsinformation.</span><span class="sxs-lookup"><span data-stu-id="0f5ee-146">The information on this page includes the team member's birth date, seniority date, years of service, years in the current position, and compensation information.</span></span>

## <a name="view-extended-team-members-by-using-the-my-team-mobile-workspace"></a><span data-ttu-id="0f5ee-147">Visa utökade teammedlemmar via arbetsytan för Mitt team</span><span class="sxs-lookup"><span data-stu-id="0f5ee-147">View extended team members by using the My team mobile workspace</span></span>
1.  <span data-ttu-id="0f5ee-148">I mobilappen väljer du arbetsytan **Mitt team**.</span><span class="sxs-lookup"><span data-stu-id="0f5ee-148">In the mobile app, select the **My team** workspace.</span></span> <span data-ttu-id="0f5ee-149">En lista över team-medlemmar visas.</span><span class="sxs-lookup"><span data-stu-id="0f5ee-149">A list of team members is shown.</span></span> <span data-ttu-id="0f5ee-150">Listan visar också varje enskild teammedlems titel, samt alla eventuella underställda som medlemmen har.</span><span class="sxs-lookup"><span data-stu-id="0f5ee-150">The list also shows each team member's title, and any direct reports that the member has.</span></span>
1.  <span data-ttu-id="0f5ee-151">Välj länken **Underställda**.</span><span class="sxs-lookup"><span data-stu-id="0f5ee-151">Select the **Direct reports** link.</span></span> <span data-ttu-id="0f5ee-152">En lista över ditt utökade team visas.</span><span class="sxs-lookup"><span data-stu-id="0f5ee-152">A list of your extended team is shown.</span></span>
1.  <span data-ttu-id="0f5ee-153">Välj en teammedlem</span><span class="sxs-lookup"><span data-stu-id="0f5ee-153">Select a team member.</span></span> <span data-ttu-id="0f5ee-154">Sidan **Sammanfattning för teammedlem** visas.</span><span class="sxs-lookup"><span data-stu-id="0f5ee-154">The **Team member summary** page appears.</span></span> <span data-ttu-id="0f5ee-155">Informationen på denna sida innehåller teammedlemmarnas födelsedatum, tjänsteålder, antal tjänsteår, år i den aktuella befattningen samt kompensationsinformation.</span><span class="sxs-lookup"><span data-stu-id="0f5ee-155">The information on this page includes the team member's birth date, seniority date, years of service, years in the current position, and compensation information.</span></span>

## <a name="send-praise-about-team-members-by-using-the-my-team-mobile-workspace"></a><span data-ttu-id="0f5ee-156">Skicka beröm om teammedlemmar via arbetsytan för Mitt team</span><span class="sxs-lookup"><span data-stu-id="0f5ee-156">Send praise about team members by using the My team mobile workspace</span></span>
1.  <span data-ttu-id="0f5ee-157">I mobilappen väljer du arbetsytan **Mitt team**.</span><span class="sxs-lookup"><span data-stu-id="0f5ee-157">In the mobile app, select the **My team** workspace.</span></span> <span data-ttu-id="0f5ee-158">En lista över team-medlemmar visas.</span><span class="sxs-lookup"><span data-stu-id="0f5ee-158">A list of team members is shown.</span></span> <span data-ttu-id="0f5ee-159">Listan visar också varje enskild teammedlems titel, samt alla eventuella underställda som medlemmen har.</span><span class="sxs-lookup"><span data-stu-id="0f5ee-159">The list also shows each team member's title, and any direct reports that the member has.</span></span>
1.  <span data-ttu-id="0f5ee-160">Välj en teammedlem</span><span class="sxs-lookup"><span data-stu-id="0f5ee-160">Select a team member.</span></span> <span data-ttu-id="0f5ee-161">Sidan **Sammanfattning för teammedlem** visas.</span><span class="sxs-lookup"><span data-stu-id="0f5ee-161">The **Team member summary** page appears.</span></span>
1.  <span data-ttu-id="0f5ee-162">Välj **Skicka beröm**.</span><span class="sxs-lookup"><span data-stu-id="0f5ee-162">Select **Send praise**.</span></span> 
1. <span data-ttu-id="0f5ee-163">Ange den berömtext som du vill skicka.</span><span class="sxs-lookup"><span data-stu-id="0f5ee-163">Enter the text of the praise that you want to send.</span></span> 
1. <span data-ttu-id="0f5ee-164">Välj **Klar**.</span><span class="sxs-lookup"><span data-stu-id="0f5ee-164">Select **Done**.</span></span>
