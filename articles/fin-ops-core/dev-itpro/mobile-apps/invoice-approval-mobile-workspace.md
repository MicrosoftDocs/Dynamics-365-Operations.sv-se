---
title: Mobil arbetsyta för fakturagodkännanden
description: Det här avsnittet innehåller information om den mobila arbetsytan för fakturagodkännanden.
author: abruer
manager: AnnBe
ms.date: 12/01/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.openlocfilehash: 1a7aa1a03791b8ccb7050389097d1272f5930a49
ms.sourcegitcommit: f8bac7ca2803913fd236adbc3806259a17a110f4
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/06/2021
ms.locfileid: "5127579"
---
# <a name="invoice-approvals-mobile-workspace"></a><span data-ttu-id="4093b-103">Mobil arbetsyta för fakturagodkännanden</span><span class="sxs-lookup"><span data-stu-id="4093b-103">Invoice approvals mobile workspace</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="4093b-104">Detta avsnitt tillhandahåller innehåller information om den mobila arbetsytan för **fakturagodkännanden**.</span><span class="sxs-lookup"><span data-stu-id="4093b-104">This topic provides information about the **Invoice approvals** mobile workspace.</span></span> <span data-ttu-id="4093b-105">Denna arbetsyta tillhandahåller en lista med fakturor som har tilldelats till dig via arbetsflödet för leverantörsfakturahuvud.</span><span class="sxs-lookup"><span data-stu-id="4093b-105">This workspace provides a list of invoices that have been assigned to you through the vendor invoice header workflow process.</span></span> 

<span data-ttu-id="4093b-106">Denna mobila arbetsyta är avsedd att användas med mobilappen Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="4093b-106">This mobile workspace is intended to be used with the Finance and Operations mobile app.</span></span>

## <a name="overview"></a><span data-ttu-id="4093b-107">Översikt</span><span class="sxs-lookup"><span data-stu-id="4093b-107">Overview</span></span>

<span data-ttu-id="4093b-108">Den mobila arbetsytan **Faktureringsgodkännanden** låter ansvariga och chefer inom leverantörsreskontra visa fakturor som har tilldelats till dem som ett led i arbetsflödet för leverantörsfakturahuvud.</span><span class="sxs-lookup"><span data-stu-id="4093b-108">The **Invoice approvals** mobile workspace lets Accounts payable clerks and managers view invoices that have been assigned to them as part of the vendor invoice header workflow process.</span></span> <span data-ttu-id="4093b-109">Du kan visa faktureringsinformationen - och till och med rad- och distributionsinformationen - för att hjälpa dig att fatta välinformerade godkännandebeslut.</span><span class="sxs-lookup"><span data-stu-id="4093b-109">You can view the invoice information, and even the line and distribution details, to help you make informed approval decisions.</span></span> <span data-ttu-id="4093b-110">Från arbetsytan kan vidta du åtgärder för att flytta faktura genom arbetsflödesprocessen.</span><span class="sxs-lookup"><span data-stu-id="4093b-110">From the workspace, you can take action to move the invoice through the workflow process.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="4093b-111">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="4093b-111">Prerequisites</span></span>

<span data-ttu-id="4093b-112">Följande förutsättningar måste vara uppfyllda innan du kan använda den här mobila arbetsytan.</span><span class="sxs-lookup"><span data-stu-id="4093b-112">Before you can use this mobile workspace, the following prerequisites must be met.</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="4093b-113">Förutsättning</span><span class="sxs-lookup"><span data-stu-id="4093b-113">Prerequisite</span></span></th>
<th><span data-ttu-id="4093b-114">Roll</span><span class="sxs-lookup"><span data-stu-id="4093b-114">Role</span></span></th>
<th><span data-ttu-id="4093b-115">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="4093b-115">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="4093b-116">Microsoft Dynamics 365 Finance måste distribueras i organisationen.</span><span class="sxs-lookup"><span data-stu-id="4093b-116">Microsoft Dynamics 365 Finance must be deployed in your organization.</span></span></td>
<td><span data-ttu-id="4093b-117">Systemadministratör</span><span class="sxs-lookup"><span data-stu-id="4093b-117">System administrator</span></span></td>
<td><span data-ttu-id="4093b-118">Se <a href="../deployment/deploy-demo-environment.md">Distribuera en demonstrationsmiljö</a>.</span><span class="sxs-lookup"><span data-stu-id="4093b-118">See <a href="../deployment/deploy-demo-environment.md">Deploy a demo environment</a>.</span></span>
</td>
</tr>
<tr class="even">
<td><span data-ttu-id="4093b-119">Den mobila arbetsytan <strong>Fakturagodkännanden</strong> måste publiceras.</span><span class="sxs-lookup"><span data-stu-id="4093b-119">The <strong>Invoice approvals</strong> mobile workspace must be published.</span></span></td>
<td><span data-ttu-id="4093b-120">Systemadministratör</span><span class="sxs-lookup"><span data-stu-id="4093b-120">System administrator</span></span></td>
<td><span data-ttu-id="4093b-121">Se <a href="publish-mobile-workspace.md">Publicera en mobil arbetsyta</a>.</span><span class="sxs-lookup"><span data-stu-id="4093b-121">See <a href="publish-mobile-workspace.md">Publish a mobile workspace</a>.</span></span></td>
</tr>
</tbody>
</table>

## <a name="download-and-install-the-mobile-app"></a><span data-ttu-id="4093b-122">Hämta och installera mobilappen</span><span class="sxs-lookup"><span data-stu-id="4093b-122">Download and install the mobile app</span></span>

<span data-ttu-id="4093b-123">Hämta och installera mobilappen Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="4093b-123">Download and install the Finance and Operations mobile app:</span></span>

-   [<span data-ttu-id="4093b-124">För Android-telefoner</span><span class="sxs-lookup"><span data-stu-id="4093b-124">For Android phones</span></span>](https://go.microsoft.com/fwlink/?linkid=850662)
-   [<span data-ttu-id="4093b-125">För iPhones</span><span class="sxs-lookup"><span data-stu-id="4093b-125">For iPhones</span></span>](https://go.microsoft.com/fwlink/?linkid=850663)

## <a name="sign-in-to-the-mobile-app"></a><span data-ttu-id="4093b-126">Logga in på mobilappen</span><span class="sxs-lookup"><span data-stu-id="4093b-126">Sign in to the mobile app</span></span>

1.  <span data-ttu-id="4093b-127">Starta appen i din mobila enhet.</span><span class="sxs-lookup"><span data-stu-id="4093b-127">Start the app on your mobile device.</span></span>
2.  <span data-ttu-id="4093b-128">Ange din Microsoft Dynamics 365 URL.</span><span class="sxs-lookup"><span data-stu-id="4093b-128">Enter your Microsoft Dynamics 365 URL.</span></span>
3.  <span data-ttu-id="4093b-129">Första gången du loggar in uppmanas du ange användarnamn och lösenord.</span><span class="sxs-lookup"><span data-stu-id="4093b-129">The first time that you sign in, you're prompted for your user name and password.</span></span> <span data-ttu-id="4093b-130">Ange dina autentiseringsuppgifter.</span><span class="sxs-lookup"><span data-stu-id="4093b-130">Enter your credentials.</span></span>
4.  <span data-ttu-id="4093b-131">När du loggar in visas tillgängliga arbetsytor för ditt företag.</span><span class="sxs-lookup"><span data-stu-id="4093b-131">After you sign in, the available workspaces for your company are shown.</span></span> <span data-ttu-id="4093b-132">Observera att om systemadministratören publicerar en ny arbetsyta senare kan du dra om du vill uppdatera listan över mobila arbetsytor.</span><span class="sxs-lookup"><span data-stu-id="4093b-132">Note that if your system administrator publishes a new workspace later, you will have to refresh the list of mobile workspaces.</span></span>

    <span data-ttu-id="4093b-133">[![Dra för att uppdatera](./media/pull-to-refresh-list-of-workspaces-183x300.png)](./media/pull-to-refresh-list-of-workspaces.png)</span><span class="sxs-lookup"><span data-stu-id="4093b-133">[![Pull to refresh](./media/pull-to-refresh-list-of-workspaces-183x300.png)](./media/pull-to-refresh-list-of-workspaces.png)</span></span>

## <a name="approve-invoices-by-using-the-invoice-approvals-mobile-workspace"></a><span data-ttu-id="4093b-134">Godkänn fakturor genom att använda den mobila arbetsytan för fakturagodkännanden</span><span class="sxs-lookup"><span data-stu-id="4093b-134">Approve invoices by using the Invoice approvals mobile workspace</span></span>
1.  <span data-ttu-id="4093b-135">På din mobila enhet väljer du arbetsytan **Fakturagodkännanden**.</span><span class="sxs-lookup"><span data-stu-id="4093b-135">On your mobile device, select the **Invoice approvals** workspace.</span></span>
2.  <span data-ttu-id="4093b-136">Välj den faktura som har tilldelats dig av arbetsflödet för leverantörsfakturahuvud.</span><span class="sxs-lookup"><span data-stu-id="4093b-136">Select the invoice that has been assigned to you by the vendor invoice header workflow process.</span></span>
3.  <span data-ttu-id="4093b-137">På sidan **Fakturainformation** granskar du informationen i fakturahuvudet, till exempel leverantör och datum.</span><span class="sxs-lookup"><span data-stu-id="4093b-137">On the **Invoice details** page, review the invoice header information, such as the vendor and date information.</span></span>
4.  <span data-ttu-id="4093b-138">Markera en rad på fakturan för att visa mer detaljerad information om den i vyn **Information om fakturarader**.</span><span class="sxs-lookup"><span data-stu-id="4093b-138">Select a line on the invoice to view more detailed information about it in the **Invoice line details** view.</span></span>
5.  <span data-ttu-id="4093b-139">I vyn **Information om fakturarader** väljer du **Fördelningar** för att visa radfördelningarna.</span><span class="sxs-lookup"><span data-stu-id="4093b-139">In the **Invoice line details** view, select **Distributions** to show the line distributions.</span></span> <span data-ttu-id="4093b-140">Här kan du visa redovisningen för fakturaraden.</span><span class="sxs-lookup"><span data-stu-id="4093b-140">Here, you can view the accounting for the invoice line.</span></span> <span data-ttu-id="4093b-141">Den information som visas inkluderar ekonomiska dimensioner och huvudkontot.</span><span class="sxs-lookup"><span data-stu-id="4093b-141">The information that is shown includes the financial dimensions and the main account.</span></span>
6.  <span data-ttu-id="4093b-142">På sidan **Fakturainformation** väljer du **Fördelningar** för att visa alla fördelningar.</span><span class="sxs-lookup"><span data-stu-id="4093b-142">On the **Invoice details** page, select **Distributions** to show all distributions.</span></span> <span data-ttu-id="4093b-143">Här kan du visa redovisningen för hela fakturan.</span><span class="sxs-lookup"><span data-stu-id="4093b-143">Here, you can view the accounting for the whole invoice.</span></span> <span data-ttu-id="4093b-144">Den information som visas inkluderar ekonomiska dimensioner och huvudkonton.</span><span class="sxs-lookup"><span data-stu-id="4093b-144">The information that is shown includes the financial dimensions and the main accounts.</span></span> 
7.  <span data-ttu-id="4093b-145">Välj **Bilagor** för att visa noteringar eller filer som är kopplade till fakturan.</span><span class="sxs-lookup"><span data-stu-id="4093b-145">Select **Attachments** to view any notes or files that are attached to the invoice.</span></span>
8.  <span data-ttu-id="4093b-146">På sidan **Fakturainformation** väljer du lämplig arbetsflödesåtgärd för att slutföra din granskningsprocess.</span><span class="sxs-lookup"><span data-stu-id="4093b-146">On the **Invoice details** page, select the appropriate workflow action to complete your review process.</span></span>
9.  <span data-ttu-id="4093b-147">Välj **Klar**.</span><span class="sxs-lookup"><span data-stu-id="4093b-147">Select **Done**.</span></span>
