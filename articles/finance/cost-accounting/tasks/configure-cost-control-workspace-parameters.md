---
title: Konfigurera parametrar för arbetsytan för kostnadskontroll
description: Använd den här proceduren för att konfigurera arbetsytan Kostnadskontroll så att chefer på olika nivåer i en organisation kan få inblick i deras kostnadsobjekt, till exempel kostnadsställen och produktgrupper.
author: ShylaThompson
manager: AnnBe
ms.date: 06/27/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CAMCostControlWorkspaceConfigurationPerUser
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 61f25b93440495b2d1b70227ecda011c43c2e564
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5208785"
---
# <a name="configure-cost-control-workspace-parameters"></a><span data-ttu-id="6c294-103">Konfigurera parametrar för arbetsytan för kostnadskontroll</span><span class="sxs-lookup"><span data-stu-id="6c294-103">Configure cost control workspace parameters</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="6c294-104">Använd den här proceduren för att konfigurera arbetsytan Kostnadskontroll så att chefer på olika nivåer i en organisation kan få inblick i deras kostnadsobjekt, till exempel kostnadsställen och produktgrupper.</span><span class="sxs-lookup"><span data-stu-id="6c294-104">Use this procedure to configure the Cost control workspace so that managers at various levels in an organization can gain insight into their cost objects, such as cost centers and product groups.</span></span> <span data-ttu-id="6c294-105">Demonstrationsföretaget USP2 användes för att skapa den här inspelningen.</span><span class="sxs-lookup"><span data-stu-id="6c294-105">The USP2 demo company was used to create this recording.</span></span>

1. <span data-ttu-id="6c294-106">Gå till Kostnadsredovisning > Inställningar > Konfiguration av arbetsytan för kostnadsstyrning.</span><span class="sxs-lookup"><span data-stu-id="6c294-106">Go to Cost accounting > Setup > Cost control workspace configuration.</span></span>
2. <span data-ttu-id="6c294-107">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="6c294-107">Click New.</span></span>
3. <span data-ttu-id="6c294-108">Skriv ett värde i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="6c294-108">In the Name field, type a value.</span></span>
4. <span data-ttu-id="6c294-109">Ange ett värde i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="6c294-109">In the Description field, type a value.</span></span>
5. <span data-ttu-id="6c294-110">Välj Ja i fältet Publicerad.</span><span class="sxs-lookup"><span data-stu-id="6c294-110">Select Yes in the Published field.</span></span>
    * <span data-ttu-id="6c294-111">Om du väljer Ja kan en användare med någon av följande roller se rapporter i arbetsytan Kostnadskontroll: kostnadsredovisningschef, kostnadsrevisor, ansvarig kostnadsredovisare och kostnadsobjektcontroller.</span><span class="sxs-lookup"><span data-stu-id="6c294-111">If you set this option to Yes, users who are assigned one of these roles can see the report in the Cost control workspace: cost accounting manager, cost accountant, cost accountant clerk, or cost object controller.</span></span> <span data-ttu-id="6c294-112">Om du väljer Nej kan bara användare med någon av följande roller se rapporter i arbetsytan Kostnadskontroll: kostnadsredovisningschef, kostnadsrevisor och ansvarig kostnadsredovisare.</span><span class="sxs-lookup"><span data-stu-id="6c294-112">If you set this option to No, only users who are assigned one of these roles can see the report in the Cost control workspace: cost accounting manager, cost accountant, or cost accountant clerk.</span></span>  
6. <span data-ttu-id="6c294-113">Expandera avsnittet Filtrering av data.</span><span class="sxs-lookup"><span data-stu-id="6c294-113">Expand the Data filtering section.</span></span>
7. <span data-ttu-id="6c294-114">Ange eller välj ett värde i fältet Kostnadsstyrenhet.</span><span class="sxs-lookup"><span data-stu-id="6c294-114">In the Cost control unit field, enter or select a value.</span></span>
8. <span data-ttu-id="6c294-115">Ange eller välj ett värde i fältet Ursprunglig budgetversion.</span><span class="sxs-lookup"><span data-stu-id="6c294-115">In the Budget original version field, enter or select a value.</span></span>
9. <span data-ttu-id="6c294-116">Ange eller välj ett värde i fältet Dimensionshierarki för kostnadselement.</span><span class="sxs-lookup"><span data-stu-id="6c294-116">In the Cost element dimension hierarchy field, enter or select a value.</span></span>
10. <span data-ttu-id="6c294-117">Ange eller välj ett värde i fältet Dimensionshierarki för kostnadsobjekt.</span><span class="sxs-lookup"><span data-stu-id="6c294-117">In the Cost object dimension hierarchy field, enter or select a value.</span></span>
11. <span data-ttu-id="6c294-118">Expandera avsnittet Tilldela beräkningsposter.</span><span class="sxs-lookup"><span data-stu-id="6c294-118">Expand the Assign calculation records section.</span></span>
12. <span data-ttu-id="6c294-119">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="6c294-119">Click New.</span></span>
13. <span data-ttu-id="6c294-120">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="6c294-120">In the list, mark the selected row.</span></span>
14. <span data-ttu-id="6c294-121">Ange eller välj ett värde i fältet Räkenskapskalenderperiod.</span><span class="sxs-lookup"><span data-stu-id="6c294-121">In the Fiscal calendar period field, enter or select a value.</span></span>
15. <span data-ttu-id="6c294-122">Ange eller välj ett värde i fältet Faktisk version.</span><span class="sxs-lookup"><span data-stu-id="6c294-122">In the Actual version field, enter or select a value.</span></span>
16. <span data-ttu-id="6c294-123">Expandera avsnittet Räkenskapsperioder per kolumn.</span><span class="sxs-lookup"><span data-stu-id="6c294-123">Expand the Fiscal periods per column section.</span></span>
17. <span data-ttu-id="6c294-124">Välj Ja i fältet Aktuell period.</span><span class="sxs-lookup"><span data-stu-id="6c294-124">Select Yes in the Current period field.</span></span>
18. <span data-ttu-id="6c294-125">Expandera avsnittet Kolumner att visa för kostnader.</span><span class="sxs-lookup"><span data-stu-id="6c294-125">Expand the Columns to display for costs section.</span></span>
19. <span data-ttu-id="6c294-126">Välj Ja i fältet Fast kostnad.</span><span class="sxs-lookup"><span data-stu-id="6c294-126">Select Yes in the Fixed cost field.</span></span>
20. <span data-ttu-id="6c294-127">Välj Ja i fältet Rörlig kostnad.</span><span class="sxs-lookup"><span data-stu-id="6c294-127">Select Yes in the Variable cost field.</span></span>
21. <span data-ttu-id="6c294-128">Välj Ja i fältet Totalkostnad.</span><span class="sxs-lookup"><span data-stu-id="6c294-128">Select Yes in the Total cost field.</span></span>
22. <span data-ttu-id="6c294-129">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="6c294-129">Click Save.</span></span>
23. <span data-ttu-id="6c294-130">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="6c294-130">Close the page.</span></span>
24. <span data-ttu-id="6c294-131">Gå till Kostnadsredovisning > Arbetsytor > Kostnadskontroll.</span><span class="sxs-lookup"><span data-stu-id="6c294-131">Go to Cost accounting > Workspaces > Cost control.</span></span>
25. <span data-ttu-id="6c294-132">Välj ett utdrag om du vill visa fasta, rörliga, totala och oklassificerade kostnader för valda räkenskapsperioder.</span><span class="sxs-lookup"><span data-stu-id="6c294-132">Select a statement to see fixed, variable, total, and unclassified costs for the selected fiscal periods.</span></span>
26. <span data-ttu-id="6c294-133">Ange eller välj ett värde i fältet Räkenskapskalenderperiod.</span><span class="sxs-lookup"><span data-stu-id="6c294-133">In the Fiscal calendar period field, enter or select a value.</span></span>
27. <span data-ttu-id="6c294-134">Ange eller välj ett värde i fältet Dimensionshierarkinod för kostnadsobjekt.</span><span class="sxs-lookup"><span data-stu-id="6c294-134">In the Cost object dimension hierarchy node field, enter or select a value.</span></span>
    * <span data-ttu-id="6c294-135">När du har valt en dimensionshierarki för kostnadsobjekt ska du expandera kostnadselementets dimensionshierarki om du vill visa önskade kostnadsvärden.</span><span class="sxs-lookup"><span data-stu-id="6c294-135">After you've selected a Cost object dimension hierarchy, expand the Cost element dimension hierarchy to see the desired cost values.</span></span> <span data-ttu-id="6c294-136">Exempelvis kan du expandera hierarkin till Tillverkningsomkostnader för att visa värdet.</span><span class="sxs-lookup"><span data-stu-id="6c294-136">For example, you can expand the hierarchy to Manufacturing overhead to see the value.</span></span>  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]