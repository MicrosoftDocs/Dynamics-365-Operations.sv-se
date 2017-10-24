--- 
title: "Utfärda ett EU-mottagningskvitto"
description: "Den här proceduren beskriver hur du aktiverar ett EU-mottagningskvitto genom att konfigurera ett kundkonto som ska använda mottagningskvitton och genom att utfärda ett certifikat."
author: mrolecki
manager: AnnBe
ms.date: 02/26/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations
ms.search.region: Austria, Belgium, Czech Republic, Denmark, Estonia, Finland, France, Germany, Hungary, Ireland, Italy, Latvia, Lithuania, Netherlands, Poland, Spain, Sweden, United Kingdom
ms.author: mrolecki
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: ff00ff0df3835ee2cbf21219ad6f07bfeba6e7ac
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---
# <a name="issue-an-eu-entry-certificate"></a><span data-ttu-id="c641b-103">Utfärda ett EU-mottagningskvitto</span><span class="sxs-lookup"><span data-stu-id="c641b-103">Issue an EU entry certificate</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="c641b-104">Den här proceduren beskriver hur du aktiverar ett EU-mottagningskvitto genom att konfigurera ett kundkonto som ska använda mottagningskvitton och genom att utfärda ett certifikat.</span><span class="sxs-lookup"><span data-stu-id="c641b-104">This procedure walks you through enabling an EU entry certificate, configuring a customer account to use entry certificates and issue a certificate.</span></span> <span data-ttu-id="c641b-105">Proceduren har skapats med demodataföretaget DEMF.</span><span class="sxs-lookup"><span data-stu-id="c641b-105">This procedure was created using the demo data company DEMF.</span></span>


## <a name="enable-entry-certificate-management"></a><span data-ttu-id="c641b-106">Aktivera hantering av mottagningskvitton</span><span class="sxs-lookup"><span data-stu-id="c641b-106">Enable entry certificate management</span></span>
1. <span data-ttu-id="c641b-107">Gå till Kundreskontra > Inställningar > Parametrar för kundreskontra.</span><span class="sxs-lookup"><span data-stu-id="c641b-107">Go to Accounts receivable > Setup > Accounts receivable parameters.</span></span>
2. <span data-ttu-id="c641b-108">Klicka på fliken Leveranser.</span><span class="sxs-lookup"><span data-stu-id="c641b-108">Click the Shipments tab.</span></span>
3. <span data-ttu-id="c641b-109">Expandera avsnittet Mottagningskvitto.</span><span class="sxs-lookup"><span data-stu-id="c641b-109">Expand the Entry certificate section.</span></span>
4. <span data-ttu-id="c641b-110">Välj Ja i fältet Aktivera hantering av mottagningskvitton.</span><span class="sxs-lookup"><span data-stu-id="c641b-110">Select Yes in the Enable entry certificate management field.</span></span>
5. <span data-ttu-id="c641b-111">Välj Ja i fältet Aktivera utfärdande av mottagningskvitton.</span><span class="sxs-lookup"><span data-stu-id="c641b-111">Select Yes in the Enable entry certificate issuing field.</span></span>
6. <span data-ttu-id="c641b-112">Klicka på fliken Nummersekvenser.</span><span class="sxs-lookup"><span data-stu-id="c641b-112">Click the Number sequences tab.</span></span>
7. <span data-ttu-id="c641b-113">Leta upp och välj mottagningskvittoraden i listan.</span><span class="sxs-lookup"><span data-stu-id="c641b-113">In the list, find and select Entry certificate row.</span></span>
8. <span data-ttu-id="c641b-114">I fältet Nummersekvenskod anger du eller väljer ett värde.</span><span class="sxs-lookup"><span data-stu-id="c641b-114">In the Number sequence code field, enter or select a value.</span></span>

## <a name="set-up-a-customer"></a><span data-ttu-id="c641b-115">Ställ in en kund</span><span class="sxs-lookup"><span data-stu-id="c641b-115">Set up a customer</span></span>
1. <span data-ttu-id="c641b-116">Gå till Leverantörsreskontra > Kunder > Alla kunder.</span><span class="sxs-lookup"><span data-stu-id="c641b-116">Go to Accounts receivable > Customers > All customers.</span></span>
2. <span data-ttu-id="c641b-117">Använd snabbfiltret för att söka efter poster.</span><span class="sxs-lookup"><span data-stu-id="c641b-117">Use the Quick Filter to find records.</span></span> <span data-ttu-id="c641b-118">Filtrera till exempel efter fältet Konto med värdet "DE-015".</span><span class="sxs-lookup"><span data-stu-id="c641b-118">For example, filter on the Account field with a value of 'DE-015'.</span></span>
3. <span data-ttu-id="c641b-119">Öppna information om kundkontot.</span><span class="sxs-lookup"><span data-stu-id="c641b-119">Open customer account details.</span></span>
4. <span data-ttu-id="c641b-120">Klicka på Redigera.</span><span class="sxs-lookup"><span data-stu-id="c641b-120">Click Edit.</span></span>
5. <span data-ttu-id="c641b-121">Expandera faktura- och leveransavsnittet.</span><span class="sxs-lookup"><span data-stu-id="c641b-121">Expand the Invoice and delivery section.</span></span>
6. <span data-ttu-id="c641b-122">Välj Ja i fältet Mottagningskvitto krävs.</span><span class="sxs-lookup"><span data-stu-id="c641b-122">Select Yes in the Entry certificate required field.</span></span>
7. <span data-ttu-id="c641b-123">Välj Ja i fältet Utfärda mottagningskvitto.</span><span class="sxs-lookup"><span data-stu-id="c641b-123">Select Yes in the Issue entry certificate field.</span></span>
8. <span data-ttu-id="c641b-124">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="c641b-124">Click Save.</span></span>

## <a name="create-an-eu-entry-certificate-automatically"></a><span data-ttu-id="c641b-125">Skapa ett EU-mottagningskvitto automatiskt</span><span class="sxs-lookup"><span data-stu-id="c641b-125">Create an EU entry certificate automatically</span></span>
1. <span data-ttu-id="c641b-126">Gå till Leverantörsreskontra > Order > Alla försäljningsorder.</span><span class="sxs-lookup"><span data-stu-id="c641b-126">Go to Accounts receivable > Orders > All sales orders.</span></span>
2. <span data-ttu-id="c641b-127">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="c641b-127">Click New.</span></span>
3. <span data-ttu-id="c641b-128">I fältet Kundkonto, ange eller välj ett värde.</span><span class="sxs-lookup"><span data-stu-id="c641b-128">In the Customer account field, enter or select a value.</span></span>
4. <span data-ttu-id="c641b-129">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="c641b-129">Click OK.</span></span>
5. <span data-ttu-id="c641b-130">Ange eller välj ett värde i fältet Artikelnummer.</span><span class="sxs-lookup"><span data-stu-id="c641b-130">In the Item number field, enter or select a value.</span></span>
6. <span data-ttu-id="c641b-131">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="c641b-131">Click Save.</span></span>
7. <span data-ttu-id="c641b-132">Klicka på Plocka och packa i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="c641b-132">On the Action Pane, click Pick and pack.</span></span>
8. <span data-ttu-id="c641b-133">Klicka på Bokför följesedel.</span><span class="sxs-lookup"><span data-stu-id="c641b-133">Click Post packing slip.</span></span>
9. <span data-ttu-id="c641b-134">Expandera avsnittet Parametrar.</span><span class="sxs-lookup"><span data-stu-id="c641b-134">Expand the Parameters section.</span></span>
10. <span data-ttu-id="c641b-135">Välj Alla i fältet Kvantitet.</span><span class="sxs-lookup"><span data-stu-id="c641b-135">In the Quantity field, select 'All'.</span></span>
11. <span data-ttu-id="c641b-136">Avmarkera kryssrutan Utfärda mottagningskvitto.</span><span class="sxs-lookup"><span data-stu-id="c641b-136">Clear the Issue entry certificate check box.</span></span>
    * <span data-ttu-id="c641b-137">Ett mottagningskvitto kan utfärdas under bokföringen av följesedeln eller under orderfaktureringen.</span><span class="sxs-lookup"><span data-stu-id="c641b-137">An entry certificate can be issued during packing slip posting or during order invoicing.</span></span> <span data-ttu-id="c641b-138">Lämna kryssrutan Utfärda mottagningskvitto avmarkerad om du vill utfärda det senare.</span><span class="sxs-lookup"><span data-stu-id="c641b-138">Leave the Issue entry certificate checkbox unchecked to issue it later.</span></span>  
12. <span data-ttu-id="c641b-139">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="c641b-139">Click OK.</span></span>
13. <span data-ttu-id="c641b-140">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="c641b-140">Click OK.</span></span>
14. <span data-ttu-id="c641b-141">Klicka på Faktura i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="c641b-141">On the Action Pane, click Invoice.</span></span>
15. <span data-ttu-id="c641b-142">Klicka på Faktura.</span><span class="sxs-lookup"><span data-stu-id="c641b-142">Click Invoice.</span></span>
    * <span data-ttu-id="c641b-143">Kontrollera att kryssrutorna Mottagningskvitto krävs och Utfärda mottagningskvitto i avsnittet Översikt är markerade.</span><span class="sxs-lookup"><span data-stu-id="c641b-143">Verify that the Entry certificate required and Issue entry certificate checkboxes in the Overview section are marked.</span></span>  <span data-ttu-id="c641b-144">Du kan också markera kryssrutan Skriv ut mottagningskvitto om du vill tillåta att kvittot skrivs ut.</span><span class="sxs-lookup"><span data-stu-id="c641b-144">You can also select the Print entry certificate check box to allow printing of the certificate.</span></span>  
16. <span data-ttu-id="c641b-145">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="c641b-145">Click OK.</span></span>
17. <span data-ttu-id="c641b-146">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="c641b-146">Click OK.</span></span>
18. <span data-ttu-id="c641b-147">Klicka på Faktura i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="c641b-147">On the Action Pane, click Invoice.</span></span>
19. <span data-ttu-id="c641b-148">Klicka på Faktura.</span><span class="sxs-lookup"><span data-stu-id="c641b-148">Click Invoice.</span></span>
20. <span data-ttu-id="c641b-149">Klicka på Faktura i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="c641b-149">On the Action Pane, click Invoice.</span></span>
21. <span data-ttu-id="c641b-150">Klicka på Visa utfärdade mottagningskvitton.</span><span class="sxs-lookup"><span data-stu-id="c641b-150">Click View issued entry certificates.</span></span>
22. <span data-ttu-id="c641b-151">Klicka på Skriv ut.</span><span class="sxs-lookup"><span data-stu-id="c641b-151">Click Print.</span></span>
23. <span data-ttu-id="c641b-152">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="c641b-152">Close the page.</span></span>
24. <span data-ttu-id="c641b-153">Klicka på Ändra status.</span><span class="sxs-lookup"><span data-stu-id="c641b-153">Click Change status.</span></span>
25. <span data-ttu-id="c641b-154">Välj ett alternativ i fältet Ny status.</span><span class="sxs-lookup"><span data-stu-id="c641b-154">In the New status field, select an option.</span></span>
26. <span data-ttu-id="c641b-155">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="c641b-155">Click OK.</span></span>
27. <span data-ttu-id="c641b-156">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="c641b-156">Close the page.</span></span>

## <a name="create-an-eu-entry-certificate-manually"></a><span data-ttu-id="c641b-157">Skapa ett EU-mottagningskvitto manuellt</span><span class="sxs-lookup"><span data-stu-id="c641b-157">Create an EU entry certificate manually</span></span>
1. <span data-ttu-id="c641b-158">Klicka på Faktura i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="c641b-158">On the Action Pane, click Invoice.</span></span>
2. <span data-ttu-id="c641b-159">Klicka på Skapa mottagningskvitto.</span><span class="sxs-lookup"><span data-stu-id="c641b-159">Click Create entry certificate.</span></span>
3. <span data-ttu-id="c641b-160">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="c641b-160">Click OK.</span></span>
4. <span data-ttu-id="c641b-161">Klicka på Faktura i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="c641b-161">On the Action Pane, click Invoice.</span></span>
5. <span data-ttu-id="c641b-162">Klicka på Visa utfärdade mottagningskvitton.</span><span class="sxs-lookup"><span data-stu-id="c641b-162">Click View issued entry certificates.</span></span>


