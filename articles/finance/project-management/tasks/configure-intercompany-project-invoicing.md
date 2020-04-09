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
ms.openlocfilehash: 31dbae2d37aefe1841fe85cb6caf185c78596e55
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/18/2020
ms.locfileid: "3144289"
---
# <a name="configure-intercompany-project-invoicing"></a><span data-ttu-id="3c2d3-103">Konfigurera koncernintern projektfakturering</span><span class="sxs-lookup"><span data-stu-id="3c2d3-103">Configure intercompany project invoicing</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="3c2d3-104">Det här avsnittet visar hur du ställer in projektfakturering mellan två företag i din organisation.</span><span class="sxs-lookup"><span data-stu-id="3c2d3-104">This topic shows how to set up project invoicing between two companies in your organization.</span></span> <span data-ttu-id="3c2d3-105">I den här uppgiften används datauppsättningen USSI.</span><span class="sxs-lookup"><span data-stu-id="3c2d3-105">This task uses the USSI data set.</span></span>

1. <span data-ttu-id="3c2d3-106">I navigeringsfönstret, gå till **Moduler > Leverantörsreskontra > Leverantörer > Alla leverantörer**.</span><span class="sxs-lookup"><span data-stu-id="3c2d3-106">In the navigation pane, go to **Modules > Accounts payable > Vendors > All vendors**.</span></span>
2. <span data-ttu-id="3c2d3-107">Sök efter och markera önskad post i listan **Alla leverantörer**.</span><span class="sxs-lookup"><span data-stu-id="3c2d3-107">In the **All vendors** list, find and select the desired record.</span></span>
3. <span data-ttu-id="3c2d3-108">Välj **Allmänt** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="3c2d3-108">On the Action Pane, select **General**.</span></span>
4. <span data-ttu-id="3c2d3-109">Välj **Koncernintern**.</span><span class="sxs-lookup"><span data-stu-id="3c2d3-109">Select **Intercompany**.</span></span>
5. <span data-ttu-id="3c2d3-110">Ange **Aktiv** som **Ja** för att aktivera koncernintern handel.</span><span class="sxs-lookup"><span data-stu-id="3c2d3-110">Set **Active** to **Yes** to enable intercompany trading.</span></span>
6. <span data-ttu-id="3c2d3-111">Ange eller välj ett värde i fältet **Kundföretag**.</span><span class="sxs-lookup"><span data-stu-id="3c2d3-111">In the **Customer company** field, enter or select a value.</span></span>
7. <span data-ttu-id="3c2d3-112">Ange eller välj ett värde i fältet **Mitt konto**.</span><span class="sxs-lookup"><span data-stu-id="3c2d3-112">In the **My account** field, enter or select a value.</span></span>
8. <span data-ttu-id="3c2d3-113">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="3c2d3-113">Select **Save**.</span></span>
9. <span data-ttu-id="3c2d3-114">Stäng sidorna om du vill gå tillbaka till startsidan.</span><span class="sxs-lookup"><span data-stu-id="3c2d3-114">Close the pages to return to the home page.</span></span>
10. <span data-ttu-id="3c2d3-115">I navigeringsfönstret, gå till **Moduler > Projekthantering och redovisning > Inställningar > Parametrar för projekthantering och redovisning**.</span><span class="sxs-lookup"><span data-stu-id="3c2d3-115">In the navigation pane, go to **Modules > Project management and accounting > Setup > Project management and accounting parameters**.</span></span>
11. <span data-ttu-id="3c2d3-116">Välj fliken **Koncernintern**.</span><span class="sxs-lookup"><span data-stu-id="3c2d3-116">Select the **Intercompany** tab.</span></span>
12. <span data-ttu-id="3c2d3-117">Flytta reglaget till **Ja** för att aktivera koncernintern resursplanering och tidrapporter.</span><span class="sxs-lookup"><span data-stu-id="3c2d3-117">Move the slider to **Yes** to enable intercompany resource scheduling and timesheets.</span></span>
13. <span data-ttu-id="3c2d3-118">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="3c2d3-118">In the list, mark the selected row.</span></span>
14. <span data-ttu-id="3c2d3-119">Välj **Ny**.</span><span class="sxs-lookup"><span data-stu-id="3c2d3-119">Select **New**.</span></span>
15. <span data-ttu-id="3c2d3-120">Ange eller välj ett värde i fältet **Lånande juridisk person**.</span><span class="sxs-lookup"><span data-stu-id="3c2d3-120">In the **Borrowing legal entity** field, enter or select a value.</span></span>
16. <span data-ttu-id="3c2d3-121">Välj kryssrutan **Upplupen intäkt**.</span><span class="sxs-lookup"><span data-stu-id="3c2d3-121">Select the **Accrue revenue** check box.</span></span>
17. <span data-ttu-id="3c2d3-122">Ange eller välj ett värde i fältet **Standardkategori för tidrapport**.</span><span class="sxs-lookup"><span data-stu-id="3c2d3-122">In the **Default timesheet category** field, enter or select a value.</span></span>
18. <span data-ttu-id="3c2d3-123">Ange eller välj ett värde i fältet **Standardkategori för utgift**.</span><span class="sxs-lookup"><span data-stu-id="3c2d3-123">In the **Default expense category** field, enter or select a value.</span></span>
19. <span data-ttu-id="3c2d3-124">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="3c2d3-124">Select **Save**.</span></span>
20. <span data-ttu-id="3c2d3-125">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="3c2d3-125">Close the page.</span></span>
21. <span data-ttu-id="3c2d3-126">I navigeringsfönstret, gå till **Moduler > Projekthantering och redovisning > Inställningar > Bokföring > Inställning av redovisningsbokföring**.</span><span class="sxs-lookup"><span data-stu-id="3c2d3-126">In the navigation pane, go to **Modules > Project management and accounting > Setup > Posting > Ledger posting setup**.</span></span>
22. <span data-ttu-id="3c2d3-127">Välj ett alternativ i fältet **Huvudbokskontotyper**.</span><span class="sxs-lookup"><span data-stu-id="3c2d3-127">In the **Ledger account types** field, select an option.</span></span>
23. <span data-ttu-id="3c2d3-128">Välj **Ny**.</span><span class="sxs-lookup"><span data-stu-id="3c2d3-128">Select **New**.</span></span>
24. <span data-ttu-id="3c2d3-129">Ange önskade värden i fältet **Huvudkonto** för den nya raden.</span><span class="sxs-lookup"><span data-stu-id="3c2d3-129">In the **Main account** field of the new row, specify the desired values.</span></span>
25. <span data-ttu-id="3c2d3-130">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="3c2d3-130">Select **Save**.</span></span>
26. <span data-ttu-id="3c2d3-131">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="3c2d3-131">Close the page.</span></span>
27. <span data-ttu-id="3c2d3-132">I navigeringsfönstret, gå till **Moduler > Projekthantering och redovisning > Inställningar > Priser > Internpris**.</span><span class="sxs-lookup"><span data-stu-id="3c2d3-132">In the navigation pane, go to **Modules > Project management and accounting > Setup > Prices > Transfer price**.</span></span>
28. <span data-ttu-id="3c2d3-133">Välj **Ny**.</span><span class="sxs-lookup"><span data-stu-id="3c2d3-133">Select **New**.</span></span>
29. <span data-ttu-id="3c2d3-134">Ange ett datum i fältet **Giltighetsdatum**.</span><span class="sxs-lookup"><span data-stu-id="3c2d3-134">In the **Effective date** field, enter a date.</span></span>
30. <span data-ttu-id="3c2d3-135">Ange eller välj ett värde i fältet **Lånande juridisk person**.</span><span class="sxs-lookup"><span data-stu-id="3c2d3-135">In the **Borrowing legal entity** field, enter or select a value.</span></span>
31. <span data-ttu-id="3c2d3-136">Välj ett alternativ i fältet **Modell för överföringspris**.</span><span class="sxs-lookup"><span data-stu-id="3c2d3-136">In the **Transfer price model** field, select an option.</span></span>
32. <span data-ttu-id="3c2d3-137">Ange ett nummer i fältet **Pris**.</span><span class="sxs-lookup"><span data-stu-id="3c2d3-137">In the **Pricing** field, enter a number.</span></span>
33. <span data-ttu-id="3c2d3-138">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="3c2d3-138">Select **Save**.</span></span>

