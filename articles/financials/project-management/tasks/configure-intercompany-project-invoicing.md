--- 
title: Konfigurera koncernintern projektfakturering
description: "Den här proceduren visar hur du ställer in projektfakturering mellan två företag i din organisation."
author: KimANelson
manager: AnnBe
ms.date: 8/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: VendTable, InterCompanyTradingRelationSetupVendor, SysDataAreaSelectLookup, ProjParameters, ProjPosting, ProjTransferPrice
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Service industries
ms.author: knelson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 32d71167fdad65cb1dec37671999a497759ca484
ms.openlocfilehash: 33b36e032bdecb13718e6eb8cd7a203f9a7b85f6
ms.contentlocale: sv-se
ms.lasthandoff: 09/11/2018

---
# <a name="configure-intercompany-project-invoicing"></a><span data-ttu-id="86e2e-103">Konfigurera koncernintern projektfakturering</span><span class="sxs-lookup"><span data-stu-id="86e2e-103">Configure intercompany project invoicing</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="86e2e-104">Den här proceduren visar hur du ställer in projektfakturering mellan två företag i din organisation.</span><span class="sxs-lookup"><span data-stu-id="86e2e-104">This procedure shows how to set up project invoicing between two companies in your organization.</span></span> <span data-ttu-id="86e2e-105">I den här uppgiften används datauppsättningen USSI.</span><span class="sxs-lookup"><span data-stu-id="86e2e-105">This task uses the USSI data set.</span></span>

1. <span data-ttu-id="86e2e-106">Gå till leverantörsreskontra > Leverantörer > Alla leverantörer.</span><span class="sxs-lookup"><span data-stu-id="86e2e-106">Go to Accounts payable > Vendors > All vendors.</span></span>
2. <span data-ttu-id="86e2e-107">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="86e2e-107">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="86e2e-108">Klicka på Allmänt i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="86e2e-108">On the Action Pane, click General.</span></span>
4. <span data-ttu-id="86e2e-109">Klicka på Koncernintern.</span><span class="sxs-lookup"><span data-stu-id="86e2e-109">Click Intercompany.</span></span>
5. <span data-ttu-id="86e2e-110">Ange Aktiv som Ja för att aktivera koncernintern handel.</span><span class="sxs-lookup"><span data-stu-id="86e2e-110">Set Active to Yes to enable intercompany trading.</span></span>
6. <span data-ttu-id="86e2e-111">Ange eller välj ett värde i fältet för Kundföretag.</span><span class="sxs-lookup"><span data-stu-id="86e2e-111">In the Customer company field, enter or select a value.</span></span>
7. <span data-ttu-id="86e2e-112">Ange eller välj ett värde i fältet Mitt konto.</span><span class="sxs-lookup"><span data-stu-id="86e2e-112">In the My account field, enter or select a value.</span></span>
8. <span data-ttu-id="86e2e-113">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="86e2e-113">Click Save.</span></span>
9. <span data-ttu-id="86e2e-114">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="86e2e-114">Close the page.</span></span>
10. <span data-ttu-id="86e2e-115">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="86e2e-115">Close the page.</span></span>
11. <span data-ttu-id="86e2e-116">Gå till Projektledning och redovisning > Inställningar > Parametrar för projekthantering och redovisning.</span><span class="sxs-lookup"><span data-stu-id="86e2e-116">Go to Project management and accounting > Setup > Project management and accounting parameters.</span></span>
12. <span data-ttu-id="86e2e-117">Klicka på fliken Koncernintern.</span><span class="sxs-lookup"><span data-stu-id="86e2e-117">Click the Intercompany tab.</span></span>
13. <span data-ttu-id="86e2e-118">Flytta reglaget till Ja för att aktivera koncernintern resursplanering och tidrapporter.</span><span class="sxs-lookup"><span data-stu-id="86e2e-118">Move the slider to Yes to enable intercompany resource scheduling and timesheets.</span></span>
14. <span data-ttu-id="86e2e-119">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="86e2e-119">In the list, mark the selected row.</span></span>
15. <span data-ttu-id="86e2e-120">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="86e2e-120">Click New.</span></span>
16. <span data-ttu-id="86e2e-121">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="86e2e-121">In the list, mark the selected row.</span></span>
17. <span data-ttu-id="86e2e-122">Ange eller välj ett värde i fältet Lånande juridisk person.</span><span class="sxs-lookup"><span data-stu-id="86e2e-122">In the Borrowing legal entity field, enter or select a value.</span></span>
18. <span data-ttu-id="86e2e-123">Välj kryssrutan Upplupen intäkt.</span><span class="sxs-lookup"><span data-stu-id="86e2e-123">Select the Accrue revenue check box.</span></span>
19. <span data-ttu-id="86e2e-124">Ange eller välj ett värde i fältet Standardkategori för tidrapport.</span><span class="sxs-lookup"><span data-stu-id="86e2e-124">In the Default timesheet category field, enter or select a value.</span></span>
20. <span data-ttu-id="86e2e-125">Ange eller välj ett värde i fältet Standardkategori för utgift.</span><span class="sxs-lookup"><span data-stu-id="86e2e-125">In the Default expense category field, enter or select a value.</span></span>
21. <span data-ttu-id="86e2e-126">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="86e2e-126">Click Save.</span></span>
22. <span data-ttu-id="86e2e-127">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="86e2e-127">Close the page.</span></span>
23. <span data-ttu-id="86e2e-128">Gå till Projekthantering och redovisning > Inställningar > Bokföra > Inställning av redovisningsbokföring.</span><span class="sxs-lookup"><span data-stu-id="86e2e-128">Go to Project management and accounting > Setup > Posting > Ledger posting setup.</span></span>
24. <span data-ttu-id="86e2e-129">Välj ett alternativ i fältet Huvudbokskontotyp.</span><span class="sxs-lookup"><span data-stu-id="86e2e-129">In the Ledger account types field, select an option.</span></span>
25. <span data-ttu-id="86e2e-130">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="86e2e-130">Click New.</span></span>
26. <span data-ttu-id="86e2e-131">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="86e2e-131">In the list, mark the selected row.</span></span>
27. <span data-ttu-id="86e2e-132">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="86e2e-132">In the list, mark the selected row.</span></span>
28. <span data-ttu-id="86e2e-133">Ange önskade värden i fältet Huvudkonto.</span><span class="sxs-lookup"><span data-stu-id="86e2e-133">In the Main account field, specify the desired values.</span></span>
29. <span data-ttu-id="86e2e-134">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="86e2e-134">Click Save.</span></span>
30. <span data-ttu-id="86e2e-135">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="86e2e-135">Close the page.</span></span>
31. <span data-ttu-id="86e2e-136">Gå till Projekthantering och redovisning > Inställningar > Priser > Överföringspris.</span><span class="sxs-lookup"><span data-stu-id="86e2e-136">Go to Project management and accounting > Setup > Prices > Transfer price.</span></span>
32. <span data-ttu-id="86e2e-137">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="86e2e-137">Click New.</span></span>
33. <span data-ttu-id="86e2e-138">Ange ett datum i fältet Giltighetsdatum.</span><span class="sxs-lookup"><span data-stu-id="86e2e-138">In the Effective date field, enter a date.</span></span>
34. <span data-ttu-id="86e2e-139">Ange eller välj ett värde i fältet Lånande juridisk person.</span><span class="sxs-lookup"><span data-stu-id="86e2e-139">In the Borrowing legal entity field, enter or select a value.</span></span>
35. <span data-ttu-id="86e2e-140">Välj ett alternativ i fältet Modell för överföringspris.</span><span class="sxs-lookup"><span data-stu-id="86e2e-140">In the Transfer price model field, select an option.</span></span>
36. <span data-ttu-id="86e2e-141">Ange ett nummer i fältet Pris.</span><span class="sxs-lookup"><span data-stu-id="86e2e-141">In the Pricing field, enter a number.</span></span>
37. <span data-ttu-id="86e2e-142">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="86e2e-142">Click Save.</span></span>


