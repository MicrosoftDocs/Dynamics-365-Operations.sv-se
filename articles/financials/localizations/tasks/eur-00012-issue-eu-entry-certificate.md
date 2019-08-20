---
title: EUR-00012 Utfärda ett EU-mottagningskvitto
description: Den här proceduren beskriver hur du aktiverar ett EU-mottagningskvitto genom att konfigurera ett kundkonto som ska använda mottagningskvitton och genom att utfärda ett certifikat.
author: mrolecki
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustParameters, CustTable, SalesTableListPage, SalesCreateOrder, SalesTable, SalesEditLines,  CustInvoiceJournal, CustEntryCertificateJour_W, SrsReportViewerForm
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Austria, Belgium, Czech Republic, Denmark, Estonia, Finland, France, Germany, Hungary, Ireland, Italy, Latvia, Lithuania, Netherlands, Poland, Spain, Sweden, United Kingdom
ms.author: mrolecki
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 735331fd399ba9501031084e236b88c0e11bb179
ms.sourcegitcommit: 16bfa0fd08feec1647829630401ce62ce2ffa1a4
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/02/2019
ms.locfileid: "1848853"
---
# <a name="eur-00012-issue-an-eu-entry-certificate"></a><span data-ttu-id="4e31d-103">EUR-00012 Utfärda ett EU-mottagningskvitto</span><span class="sxs-lookup"><span data-stu-id="4e31d-103">EUR-00012 Issue an EU entry certificate</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="4e31d-104">Den här proceduren beskriver hur du aktiverar ett EU-mottagningskvitto genom att konfigurera ett kundkonto som ska använda mottagningskvitton och genom att utfärda ett certifikat.</span><span class="sxs-lookup"><span data-stu-id="4e31d-104">This procedure walks you through enabling an EU entry certificate, configuring a customer account to use entry certificates and issue a certificate.</span></span> <span data-ttu-id="4e31d-105">Proceduren har skapats med demodataföretaget DEMF.</span><span class="sxs-lookup"><span data-stu-id="4e31d-105">This procedure was created using the demo data company DEMF.</span></span>


## <a name="enable-entry-certificate-management"></a><span data-ttu-id="4e31d-106">Aktivera hantering av mottagningskvitton</span><span class="sxs-lookup"><span data-stu-id="4e31d-106">Enable entry certificate management</span></span>
1. <span data-ttu-id="4e31d-107">Gå till Kundreskontra > Inställningar > Parametrar för kundreskontra.</span><span class="sxs-lookup"><span data-stu-id="4e31d-107">Go to Accounts receivable > Setup > Accounts receivable parameters.</span></span>
2. <span data-ttu-id="4e31d-108">Klicka på fliken Leveranser.</span><span class="sxs-lookup"><span data-stu-id="4e31d-108">Click the Shipments tab.</span></span>
3. <span data-ttu-id="4e31d-109">Expandera avsnittet Mottagningskvitto.</span><span class="sxs-lookup"><span data-stu-id="4e31d-109">Expand the Entry certificate section.</span></span>
4. <span data-ttu-id="4e31d-110">Välj Ja i fältet Aktivera hantering av mottagningskvitton.</span><span class="sxs-lookup"><span data-stu-id="4e31d-110">Select Yes in the Enable entry certificate management field.</span></span>
5. <span data-ttu-id="4e31d-111">Välj Ja i fältet Aktivera utfärdande av mottagningskvitton.</span><span class="sxs-lookup"><span data-stu-id="4e31d-111">Select Yes in the Enable entry certificate issuing field.</span></span>
6. <span data-ttu-id="4e31d-112">Klicka på fliken Nummersekvenser.</span><span class="sxs-lookup"><span data-stu-id="4e31d-112">Click the Number sequences tab.</span></span>
7. <span data-ttu-id="4e31d-113">Leta upp och välj mottagningskvittoraden i listan.</span><span class="sxs-lookup"><span data-stu-id="4e31d-113">In the list, find and select Entry certificate row.</span></span>
8. <span data-ttu-id="4e31d-114">I fältet Nummersekvenskod anger du eller väljer ett värde.</span><span class="sxs-lookup"><span data-stu-id="4e31d-114">In the Number sequence code field, enter or select a value.</span></span>

## <a name="set-up-a-customer"></a><span data-ttu-id="4e31d-115">Ställ in en kund</span><span class="sxs-lookup"><span data-stu-id="4e31d-115">Set up a customer</span></span>
1. <span data-ttu-id="4e31d-116">Gå till Leverantörsreskontra > Kunder > Alla kunder.</span><span class="sxs-lookup"><span data-stu-id="4e31d-116">Go to Accounts receivable > Customers > All customers.</span></span>
2. <span data-ttu-id="4e31d-117">Använd snabbfiltret för att söka efter poster.</span><span class="sxs-lookup"><span data-stu-id="4e31d-117">Use the Quick Filter to find records.</span></span> <span data-ttu-id="4e31d-118">Filtrera till exempel efter fältet Konto med värdet "DE-015".</span><span class="sxs-lookup"><span data-stu-id="4e31d-118">For example, filter on the Account field with a value of 'DE-015'.</span></span>
3. <span data-ttu-id="4e31d-119">Öppna information om kundkontot.</span><span class="sxs-lookup"><span data-stu-id="4e31d-119">Open customer account details.</span></span>
4. <span data-ttu-id="4e31d-120">Klicka på Redigera.</span><span class="sxs-lookup"><span data-stu-id="4e31d-120">Click Edit.</span></span>
5. <span data-ttu-id="4e31d-121">Expandera faktura- och leveransavsnittet.</span><span class="sxs-lookup"><span data-stu-id="4e31d-121">Expand the Invoice and delivery section.</span></span>
6. <span data-ttu-id="4e31d-122">Välj Ja i fältet Mottagningskvitto krävs.</span><span class="sxs-lookup"><span data-stu-id="4e31d-122">Select Yes in the Entry certificate required field.</span></span>
7. <span data-ttu-id="4e31d-123">Välj Ja i fältet Utfärda mottagningskvitto.</span><span class="sxs-lookup"><span data-stu-id="4e31d-123">Select Yes in the Issue entry certificate field.</span></span>
8. <span data-ttu-id="4e31d-124">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="4e31d-124">Click Save.</span></span>

## <a name="create-an-eu-entry-certificate-automatically"></a><span data-ttu-id="4e31d-125">Skapa ett EU-mottagningskvitto automatiskt</span><span class="sxs-lookup"><span data-stu-id="4e31d-125">Create an EU entry certificate automatically</span></span>
1. <span data-ttu-id="4e31d-126">Gå till Leverantörsreskontra > Order > Alla försäljningsorder.</span><span class="sxs-lookup"><span data-stu-id="4e31d-126">Go to Accounts receivable > Orders > All sales orders.</span></span>
2. <span data-ttu-id="4e31d-127">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="4e31d-127">Click New.</span></span>
3. <span data-ttu-id="4e31d-128">I fältet Kundkonto, ange eller välj ett värde.</span><span class="sxs-lookup"><span data-stu-id="4e31d-128">In the Customer account field, enter or select a value.</span></span>
4. <span data-ttu-id="4e31d-129">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="4e31d-129">Click OK.</span></span>
5. <span data-ttu-id="4e31d-130">Ange eller välj ett värde i fältet Artikelnummer.</span><span class="sxs-lookup"><span data-stu-id="4e31d-130">In the Item number field, enter or select a value.</span></span>
6. <span data-ttu-id="4e31d-131">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="4e31d-131">Click Save.</span></span>
7. <span data-ttu-id="4e31d-132">Klicka på Plocka och packa i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="4e31d-132">On the Action Pane, click Pick and pack.</span></span>
8. <span data-ttu-id="4e31d-133">Klicka på Bokför följesedel.</span><span class="sxs-lookup"><span data-stu-id="4e31d-133">Click Post packing slip.</span></span>
9. <span data-ttu-id="4e31d-134">Expandera avsnittet Parametrar.</span><span class="sxs-lookup"><span data-stu-id="4e31d-134">Expand the Parameters section.</span></span>
10. <span data-ttu-id="4e31d-135">Välj Alla i fältet Kvantitet.</span><span class="sxs-lookup"><span data-stu-id="4e31d-135">In the Quantity field, select 'All'.</span></span>
11. <span data-ttu-id="4e31d-136">Avmarkera kryssrutan Utfärda mottagningskvitto.</span><span class="sxs-lookup"><span data-stu-id="4e31d-136">Clear the Issue entry certificate check box.</span></span>
    * <span data-ttu-id="4e31d-137">Ett mottagningskvitto kan utfärdas under bokföringen av följesedeln eller under orderfaktureringen.</span><span class="sxs-lookup"><span data-stu-id="4e31d-137">An entry certificate can be issued during packing slip posting or during order invoicing.</span></span> <span data-ttu-id="4e31d-138">Lämna kryssrutan Utfärda mottagningskvitto avmarkerad om du vill utfärda det senare.</span><span class="sxs-lookup"><span data-stu-id="4e31d-138">Leave the Issue entry certificate checkbox unchecked to issue it later.</span></span>  
12. <span data-ttu-id="4e31d-139">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="4e31d-139">Click OK.</span></span>
13. <span data-ttu-id="4e31d-140">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="4e31d-140">Click OK.</span></span>
14. <span data-ttu-id="4e31d-141">Klicka på Faktura i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="4e31d-141">On the Action Pane, click Invoice.</span></span>
15. <span data-ttu-id="4e31d-142">Klicka på Faktura.</span><span class="sxs-lookup"><span data-stu-id="4e31d-142">Click Invoice.</span></span>
    * <span data-ttu-id="4e31d-143">Kontrollera att kryssrutorna Mottagningskvitto krävs och Utfärda mottagningskvitto i avsnittet Översikt är markerade.</span><span class="sxs-lookup"><span data-stu-id="4e31d-143">Verify that the Entry certificate required and Issue entry certificate checkboxes in the Overview section are marked.</span></span>  <span data-ttu-id="4e31d-144">Du kan också markera kryssrutan Skriv ut mottagningskvitto om du vill tillåta att kvittot skrivs ut.</span><span class="sxs-lookup"><span data-stu-id="4e31d-144">You can also select the Print entry certificate check box to allow printing of the certificate.</span></span>  
16. <span data-ttu-id="4e31d-145">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="4e31d-145">Click OK.</span></span>
17. <span data-ttu-id="4e31d-146">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="4e31d-146">Click OK.</span></span>
18. <span data-ttu-id="4e31d-147">Klicka på Faktura i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="4e31d-147">On the Action Pane, click Invoice.</span></span>
19. <span data-ttu-id="4e31d-148">Klicka på Faktura.</span><span class="sxs-lookup"><span data-stu-id="4e31d-148">Click Invoice.</span></span>
20. <span data-ttu-id="4e31d-149">Klicka på Faktura i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="4e31d-149">On the Action Pane, click Invoice.</span></span>
21. <span data-ttu-id="4e31d-150">Klicka på Visa utfärdade mottagningskvitton.</span><span class="sxs-lookup"><span data-stu-id="4e31d-150">Click View issued entry certificates.</span></span>
22. <span data-ttu-id="4e31d-151">Klicka på Skriv ut.</span><span class="sxs-lookup"><span data-stu-id="4e31d-151">Click Print.</span></span>
23. <span data-ttu-id="4e31d-152">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="4e31d-152">Close the page.</span></span>
24. <span data-ttu-id="4e31d-153">Klicka på Ändra status.</span><span class="sxs-lookup"><span data-stu-id="4e31d-153">Click Change status.</span></span>
25. <span data-ttu-id="4e31d-154">Välj ett alternativ i fältet Ny status.</span><span class="sxs-lookup"><span data-stu-id="4e31d-154">In the New status field, select an option.</span></span>
26. <span data-ttu-id="4e31d-155">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="4e31d-155">Click OK.</span></span>
27. <span data-ttu-id="4e31d-156">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="4e31d-156">Close the page.</span></span>

## <a name="create-an-eu-entry-certificate-manually"></a><span data-ttu-id="4e31d-157">Skapa ett EU-mottagningskvitto manuellt</span><span class="sxs-lookup"><span data-stu-id="4e31d-157">Create an EU entry certificate manually</span></span>
1. <span data-ttu-id="4e31d-158">Klicka på Faktura i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="4e31d-158">On the Action Pane, click Invoice.</span></span>
2. <span data-ttu-id="4e31d-159">Klicka på Skapa mottagningskvitto.</span><span class="sxs-lookup"><span data-stu-id="4e31d-159">Click Create entry certificate.</span></span>
3. <span data-ttu-id="4e31d-160">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="4e31d-160">Click OK.</span></span>
4. <span data-ttu-id="4e31d-161">Klicka på Faktura i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="4e31d-161">On the Action Pane, click Invoice.</span></span>
5. <span data-ttu-id="4e31d-162">Klicka på Visa utfärdade mottagningskvitton.</span><span class="sxs-lookup"><span data-stu-id="4e31d-162">Click View issued entry certificates.</span></span>

