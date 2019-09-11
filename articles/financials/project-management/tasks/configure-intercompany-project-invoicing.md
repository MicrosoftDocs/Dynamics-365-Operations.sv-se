---
title: Konfigurera koncernintern projektfakturering
description: Det här avsnittet visar hur du ställer in projektfakturering mellan två företag i din organisation.
author: KimANelson
manager: AnnBe
ms.date: 07/29/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendTable, InterCompanyTradingRelationSetupVendor, SysDataAreaSelectLookup, ProjParameters, ProjPosting, ProjTransferPrice
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Service industries
ms.author: knelson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: c89b17c09a4f145b5a4ca9cdd127b4e635447d4b
ms.sourcegitcommit: a368682f9cf3897347d155f1a2d4b33e555cc2c4
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/08/2019
ms.locfileid: "1867329"
---
# <a name="configure-intercompany-project-invoicing"></a><span data-ttu-id="db64d-103">Konfigurera koncernintern projektfakturering</span><span class="sxs-lookup"><span data-stu-id="db64d-103">Configure intercompany project invoicing</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="db64d-104">Det här avsnittet visar hur du ställer in projektfakturering mellan två företag i din organisation.</span><span class="sxs-lookup"><span data-stu-id="db64d-104">This topic shows how to set up project invoicing between two companies in your organization.</span></span> <span data-ttu-id="db64d-105">I den här uppgiften används datauppsättningen USSI.</span><span class="sxs-lookup"><span data-stu-id="db64d-105">This task uses the USSI data set.</span></span>

1. <span data-ttu-id="db64d-106">I navigeringsfönstret, gå till **Moduler > Leverantörsreskontra > Leverantörer > Alla leverantörer**.</span><span class="sxs-lookup"><span data-stu-id="db64d-106">In the navigation pane, go to **Modules > Accounts payable > Vendors > All vendors**.</span></span>
2. <span data-ttu-id="db64d-107">Sök efter och markera önskad post i listan **Alla leverantörer**.</span><span class="sxs-lookup"><span data-stu-id="db64d-107">In the **All vendors** list, find and select the desired record.</span></span>
3. <span data-ttu-id="db64d-108">Välj **Allmänt** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="db64d-108">On the Action Pane, select **General**.</span></span>
4. <span data-ttu-id="db64d-109">Välj **Koncernintern**.</span><span class="sxs-lookup"><span data-stu-id="db64d-109">Select **Intercompany**.</span></span>
5. <span data-ttu-id="db64d-110">Ange **Aktiv** som **Ja** för att aktivera koncernintern handel.</span><span class="sxs-lookup"><span data-stu-id="db64d-110">Set **Active** to **Yes** to enable intercompany trading.</span></span>
6. <span data-ttu-id="db64d-111">Ange eller välj ett värde i fältet **Kundföretag**.</span><span class="sxs-lookup"><span data-stu-id="db64d-111">In the **Customer company** field, enter or select a value.</span></span>
7. <span data-ttu-id="db64d-112">Ange eller välj ett värde i fältet **Mitt konto**.</span><span class="sxs-lookup"><span data-stu-id="db64d-112">In the **My account** field, enter or select a value.</span></span>
8. <span data-ttu-id="db64d-113">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="db64d-113">Select **Save**.</span></span>
9. <span data-ttu-id="db64d-114">Stäng sidorna om du vill gå tillbaka till startsidan.</span><span class="sxs-lookup"><span data-stu-id="db64d-114">Close the pages to return to the home page.</span></span>
10. <span data-ttu-id="db64d-115">I navigeringsfönstret, gå till **Moduler > Projekthantering och redovisning > Inställningar > Parametrar för projekthantering och redovisning**.</span><span class="sxs-lookup"><span data-stu-id="db64d-115">In the navigation pane, go to **Modules > Project management and accounting > Setup > Project management and accounting parameters**.</span></span>
11. <span data-ttu-id="db64d-116">Välj fliken **Koncernintern**.</span><span class="sxs-lookup"><span data-stu-id="db64d-116">Select the **Intercompany** tab.</span></span>
12. <span data-ttu-id="db64d-117">Flytta reglaget till **Ja** för att aktivera koncernintern resursplanering och tidrapporter.</span><span class="sxs-lookup"><span data-stu-id="db64d-117">Move the slider to **Yes** to enable intercompany resource scheduling and timesheets.</span></span>
13. <span data-ttu-id="db64d-118">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="db64d-118">In the list, mark the selected row.</span></span>
14. <span data-ttu-id="db64d-119">Välj **Ny**.</span><span class="sxs-lookup"><span data-stu-id="db64d-119">Select **New**.</span></span>
15. <span data-ttu-id="db64d-120">Ange eller välj ett värde i fältet **Lånande juridisk person**.</span><span class="sxs-lookup"><span data-stu-id="db64d-120">In the **Borrowing legal entity** field, enter or select a value.</span></span>
16. <span data-ttu-id="db64d-121">Välj kryssrutan **Upplupen intäkt**.</span><span class="sxs-lookup"><span data-stu-id="db64d-121">Select the **Accrue revenue** check box.</span></span>
17. <span data-ttu-id="db64d-122">Ange eller välj ett värde i fältet **Standardkategori för tidrapport**.</span><span class="sxs-lookup"><span data-stu-id="db64d-122">In the **Default timesheet category** field, enter or select a value.</span></span>
18. <span data-ttu-id="db64d-123">Ange eller välj ett värde i fältet **Standardkategori för utgift**.</span><span class="sxs-lookup"><span data-stu-id="db64d-123">In the **Default expense category** field, enter or select a value.</span></span>
19. <span data-ttu-id="db64d-124">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="db64d-124">Select **Save**.</span></span>
20. <span data-ttu-id="db64d-125">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="db64d-125">Close the page.</span></span>
21. <span data-ttu-id="db64d-126">I navigeringsfönstret, gå till **Moduler > Projekthantering och redovisning > Inställningar > Bokföring > Inställning av redovisningsbokföring**.</span><span class="sxs-lookup"><span data-stu-id="db64d-126">In the navigation pane, go to **Modules > Project management and accounting > Setup > Posting > Ledger posting setup**.</span></span>
22. <span data-ttu-id="db64d-127">Välj ett alternativ i fältet **Huvudbokskontotyper**.</span><span class="sxs-lookup"><span data-stu-id="db64d-127">In the **Ledger account types** field, select an option.</span></span>
23. <span data-ttu-id="db64d-128">Välj **Ny**.</span><span class="sxs-lookup"><span data-stu-id="db64d-128">Select **New**.</span></span>
24. <span data-ttu-id="db64d-129">Ange önskade värden i fältet **Huvudkonto** för den nya raden.</span><span class="sxs-lookup"><span data-stu-id="db64d-129">In the **Main account** field of the new row, specify the desired values.</span></span>
25. <span data-ttu-id="db64d-130">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="db64d-130">Select **Save**.</span></span>
26. <span data-ttu-id="db64d-131">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="db64d-131">Close the page.</span></span>
27. <span data-ttu-id="db64d-132">I navigeringsfönstret, gå till **Moduler > Projekthantering och redovisning > Inställningar > Priser > Internpris**.</span><span class="sxs-lookup"><span data-stu-id="db64d-132">In the navigation pane, go to **Modules > Project management and accounting > Setup > Prices > Transfer price**.</span></span>
28. <span data-ttu-id="db64d-133">Välj **Ny**.</span><span class="sxs-lookup"><span data-stu-id="db64d-133">Select **New**.</span></span>
29. <span data-ttu-id="db64d-134">Ange ett datum i fältet **Giltighetsdatum**.</span><span class="sxs-lookup"><span data-stu-id="db64d-134">In the **Effective date** field, enter a date.</span></span>
30. <span data-ttu-id="db64d-135">Ange eller välj ett värde i fältet **Lånande juridisk person**.</span><span class="sxs-lookup"><span data-stu-id="db64d-135">In the **Borrowing legal entity** field, enter or select a value.</span></span>
31. <span data-ttu-id="db64d-136">Välj ett alternativ i fältet **Modell för överföringspris**.</span><span class="sxs-lookup"><span data-stu-id="db64d-136">In the **Transfer price model** field, select an option.</span></span>
32. <span data-ttu-id="db64d-137">Ange ett nummer i fältet **Pris**.</span><span class="sxs-lookup"><span data-stu-id="db64d-137">In the **Pricing** field, enter a number.</span></span>
33. <span data-ttu-id="db64d-138">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="db64d-138">Select **Save**.</span></span>

