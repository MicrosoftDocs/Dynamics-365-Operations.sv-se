---
title: "Mobil arbetsyta för fakturagodkännanden"
description: "Det här avsnittet innehåller information om den mobila arbetsytan för fakturagodkännanden. Denna arbetsyta tillhandahåller en lista med fakturor som har tilldelats till dig via arbetsflödet för leverantörsfakturahuvud."
author: abruer
manager: AnnBe
ms.date: 06/16/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: af673f076f684500b6ca84d04c01f7f773d65cd6
ms.contentlocale: sv-se
ms.lasthandoff: 11/03/2017

---

# <a name="invoice-approvals-mobile-workspace"></a><span data-ttu-id="a202f-104">Mobil arbetsyta för fakturagodkännanden</span><span class="sxs-lookup"><span data-stu-id="a202f-104">Invoice approvals mobile workspace</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="a202f-105">Detta avsnitt tillhandahåller innehåller information om den mobila arbetsytan för **fakturagodkännanden**.</span><span class="sxs-lookup"><span data-stu-id="a202f-105">This topic provides information about the **Invoice approvals** mobile workspace.</span></span> <span data-ttu-id="a202f-106">Denna arbetsyta tillhandahåller en lista med fakturor som har tilldelats till dig via arbetsflödet för leverantörsfakturahuvud.</span><span class="sxs-lookup"><span data-stu-id="a202f-106">This workspace provides a list of invoices that have been assigned to you through the vendor invoice header workflow process.</span></span> 

<span data-ttu-id="a202f-107">Denna mobila arbetsyta är avsedd att användas med mobilappen Microsoft Dynamics 365 for Unified Operations.</span><span class="sxs-lookup"><span data-stu-id="a202f-107">This mobile workspace is intended to be used with the Microsoft Dynamics 365 for Unified Operations mobile app.</span></span>

## <a name="overview"></a><span data-ttu-id="a202f-108">Översikt</span><span class="sxs-lookup"><span data-stu-id="a202f-108">Overview</span></span>

<span data-ttu-id="a202f-109">Den mobila arbetsytan **Faktureringsgodkännanden** låter ansvariga och chefer inom leverantörsreskontra visa fakturor som har tilldelats till dem som ett led i arbetsflödet för leverantörsfakturahuvud.</span><span class="sxs-lookup"><span data-stu-id="a202f-109">The **Invoice approvals** mobile workspace lets Accounts payable clerks and managers view invoices that have been assigned to them as part of the vendor invoice header workflow process.</span></span> <span data-ttu-id="a202f-110">Du kan visa faktureringsinformationen - och till och med rad- och distributionsinformationen - för att hjälpa dig att fatta välinformerade godkännandebeslut.</span><span class="sxs-lookup"><span data-stu-id="a202f-110">You can view the invoice information, and even the line and distribution details, to help you make informed approval decisions.</span></span> <span data-ttu-id="a202f-111">Från arbetsytan kan vidta du åtgärder för att flytta faktura genom arbetsflödesprocessen.</span><span class="sxs-lookup"><span data-stu-id="a202f-111">From the workspace, you can take action to move the invoice through the workflow process.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="a202f-112">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="a202f-112">Prerequisites</span></span>

<span data-ttu-id="a202f-113">Följande förutsättningar måste vara uppfyllda innan du kan använda den här mobila arbetsytan.</span><span class="sxs-lookup"><span data-stu-id="a202f-113">Before you can use this mobile workspace, the following prerequisites must be met.</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="a202f-114">Förutsättning</span><span class="sxs-lookup"><span data-stu-id="a202f-114">Prerequisite</span></span></th>
<th><span data-ttu-id="a202f-115">Roll</span><span class="sxs-lookup"><span data-stu-id="a202f-115">Role</span></span></th>
<th><span data-ttu-id="a202f-116">beskrivning</span><span class="sxs-lookup"><span data-stu-id="a202f-116">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="a202f-117">Microsoft Dynamics 365 for Finance and Operations, Enterprise edition (juli 2017) måste implementeras i din organisation.</span><span class="sxs-lookup"><span data-stu-id="a202f-117">Microsoft Dynamics 365 for Finance and Operations, Enterprise edition (July 2017) must be deployed in your organization.</span></span></td>
<td><span data-ttu-id="a202f-118">Systemadministratör</span><span class="sxs-lookup"><span data-stu-id="a202f-118">System administrator</span></span></td>
<td><span data-ttu-id="a202f-119">Se <a href="../deployment/deploy-demo-environment.md">Distribuera en demonstrationsmiljö</a>.</span><span class="sxs-lookup"><span data-stu-id="a202f-119">See <a href="../deployment/deploy-demo-environment.md">Deploy a demo environment</a>.</span></span>
</td>
</tr>
<tr class="even">
<td><span data-ttu-id="a202f-120">Den mobila arbetsytan <strong>Fakturagodkännanden</strong> måste publiceras.</span><span class="sxs-lookup"><span data-stu-id="a202f-120">The <strong>Invoice approvals</strong> mobile workspace must be published.</span></span></td>
<td><span data-ttu-id="a202f-121">Systemadministratör</span><span class="sxs-lookup"><span data-stu-id="a202f-121">System administrator</span></span></td>
<td><span data-ttu-id="a202f-122">Se <a href="publish-mobile-workspace.md">Publicera en mobil arbetsyta</a>.</span><span class="sxs-lookup"><span data-stu-id="a202f-122">See <a href="publish-mobile-workspace.md">Publish a mobile workspace</a>.</span></span></td>
</tr>
</tbody>
</table>

## <a name="download-and-install-the-mobile-app"></a><span data-ttu-id="a202f-123">Hämta och installera mobilappen</span><span class="sxs-lookup"><span data-stu-id="a202f-123">Download and install the mobile app</span></span>

<span data-ttu-id="a202f-124">Hämta och installera mobilappen Dynamics 365 for Unified Operations:</span><span class="sxs-lookup"><span data-stu-id="a202f-124">Download and install the Dynamics 365 for Unified Operations mobile app:</span></span>

-   [<span data-ttu-id="a202f-125">För Android-telefoner</span><span class="sxs-lookup"><span data-stu-id="a202f-125">For Android phones</span></span>](https://go.microsoft.com/fwlink/?linkid=850662)
-   [<span data-ttu-id="a202f-126">För iPhones</span><span class="sxs-lookup"><span data-stu-id="a202f-126">For iPhones</span></span>](https://go.microsoft.com/fwlink/?linkid=850663)

## <a name="sign-in-to-the-mobile-app"></a><span data-ttu-id="a202f-127">Logga in på mobilappen</span><span class="sxs-lookup"><span data-stu-id="a202f-127">Sign in to the mobile app</span></span>

1.  <span data-ttu-id="a202f-128">Starta appen i din mobila enhet.</span><span class="sxs-lookup"><span data-stu-id="a202f-128">Start the app on your mobile device.</span></span>
2.  <span data-ttu-id="a202f-129">Ange din webbadress för Microsoft Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="a202f-129">Enter your Microsoft Dynamics 365 URL.</span></span>
3.  <span data-ttu-id="a202f-130">Första gången du loggar in uppmanas du ange användarnamn och lösenord.</span><span class="sxs-lookup"><span data-stu-id="a202f-130">The first time that you sign in, you're prompted for your user name and password.</span></span> <span data-ttu-id="a202f-131">Ange dina autentiseringsuppgifter.</span><span class="sxs-lookup"><span data-stu-id="a202f-131">Enter your credentials.</span></span>
4.  <span data-ttu-id="a202f-132">När du loggar in visas tillgängliga arbetsytor för ditt företag.</span><span class="sxs-lookup"><span data-stu-id="a202f-132">After you sign in, the available workspaces for your company are shown.</span></span> <span data-ttu-id="a202f-133">Observera att om systemadministratören publicerar en ny arbetsyta senare kan du dra om du vill uppdatera listan över mobila arbetsytor.</span><span class="sxs-lookup"><span data-stu-id="a202f-133">Note that if your system administrator publishes a new workspace later, you will have to refresh the list of mobile workspaces.</span></span>

    <span data-ttu-id="a202f-134">[![Dra för att uppdatera](./media/pull-to-refresh-list-of-workspaces-183x300.png)](./media/pull-to-refresh-list-of-workspaces.png)</span><span class="sxs-lookup"><span data-stu-id="a202f-134">[![Pull to refresh](./media/pull-to-refresh-list-of-workspaces-183x300.png)](./media/pull-to-refresh-list-of-workspaces.png)</span></span>

## <a name="approve-invoices-by-using-the-invoice-approvals-mobile-workspace"></a><span data-ttu-id="a202f-135">Godkänn fakturor genom att använda den mobila arbetsytan för fakturagodkännanden</span><span class="sxs-lookup"><span data-stu-id="a202f-135">Approve invoices by using the Invoice approvals mobile workspace</span></span>
1.  <span data-ttu-id="a202f-136">På din mobila enhet väljer du arbetsytan **Fakturagodkännanden**.</span><span class="sxs-lookup"><span data-stu-id="a202f-136">On your mobile device, select the **Invoice approvals** workspace.</span></span>
2.  <span data-ttu-id="a202f-137">Välj den faktura som har tilldelats dig av arbetsflödet för leverantörsfakturahuvud.</span><span class="sxs-lookup"><span data-stu-id="a202f-137">Select the invoice that has been assigned to you by the vendor invoice header workflow process.</span></span>
3.  <span data-ttu-id="a202f-138">På sidan **Fakturainformation** granskar du informationen i fakturahuvudet, till exempel leverantör och datum.</span><span class="sxs-lookup"><span data-stu-id="a202f-138">On the **Invoice details** page, review the invoice header information, such as the vendor and date information.</span></span>
4.  <span data-ttu-id="a202f-139">Markera en rad på fakturan för att visa mer detaljerad information om den i vyn **Information om fakturarader**.</span><span class="sxs-lookup"><span data-stu-id="a202f-139">Select a line on the invoice to view more detailed information about it in the **Invoice line details** view.</span></span>
5.  <span data-ttu-id="a202f-140">I vyn **Information om fakturarader** väljer du **Fördelningar** för att visa radfördelningarna.</span><span class="sxs-lookup"><span data-stu-id="a202f-140">In the **Invoice line details** view, select **Distributions** to show the line distributions.</span></span> <span data-ttu-id="a202f-141">Här kan du visa redovisningen för fakturaraden.</span><span class="sxs-lookup"><span data-stu-id="a202f-141">Here, you can view the accounting for the invoice line.</span></span> <span data-ttu-id="a202f-142">Den information som visas inkluderar ekonomiska dimensioner och huvudkontot.</span><span class="sxs-lookup"><span data-stu-id="a202f-142">The information that is shown includes the financial dimensions and the main account.</span></span>
6.  <span data-ttu-id="a202f-143">På sidan **Fakturainformation** väljer du **Fördelningar** för att visa alla fördelningar.</span><span class="sxs-lookup"><span data-stu-id="a202f-143">On the **Invoice details** page, select **Distributions** to show all distributions.</span></span> <span data-ttu-id="a202f-144">Här kan du visa redovisningen för hela fakturan.</span><span class="sxs-lookup"><span data-stu-id="a202f-144">Here, you can view the accounting for the whole invoice.</span></span> <span data-ttu-id="a202f-145">Den information som visas inkluderar ekonomiska dimensioner och huvudkonton.</span><span class="sxs-lookup"><span data-stu-id="a202f-145">The information that is shown includes the financial dimensions and the main accounts.</span></span> 
7.  <span data-ttu-id="a202f-146">Välj **Bilagor** för att visa noteringar eller filer som är kopplade till fakturan.</span><span class="sxs-lookup"><span data-stu-id="a202f-146">Select **Attachments** to view any notes or files that are attached to the invoice.</span></span>
8.  <span data-ttu-id="a202f-147">På sidan **Fakturainformation** väljer du lämplig arbetsflödesåtgärd för att slutföra din granskningsprocess.</span><span class="sxs-lookup"><span data-stu-id="a202f-147">On the **Invoice details** page, select the appropriate workflow action to complete your review process.</span></span>
9.  <span data-ttu-id="a202f-148">Välj **Klar**.</span><span class="sxs-lookup"><span data-stu-id="a202f-148">Select **Done**.</span></span>

