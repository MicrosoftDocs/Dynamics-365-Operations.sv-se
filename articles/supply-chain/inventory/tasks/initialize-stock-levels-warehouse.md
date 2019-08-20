---
title: Initiera lagernivåer i lagerstället
description: Den här proceduren visar hur du kan uppdatera lagerbehållningen manuellt genom att använda en journal för lagerrörelse.
author: perlynne
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventJournalMovement, InventJournalCreate, InventItemIdLookupSimple, InventLocationIdLookup, WMSLocationIdLookup
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: dbd6dc6c2e5b7c1abe6e19f00a5df285e0147a92
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/01/2019
ms.locfileid: "1845411"
---
# <a name="initialize-stock-levels-in-the-warehouse"></a><span data-ttu-id="d2fed-103">Initiera lagernivåer i lagerstället</span><span class="sxs-lookup"><span data-stu-id="d2fed-103">Initialize stock levels in the warehouse</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="d2fed-104">Den här proceduren visar hur du kan uppdatera lagerbehållningen manuellt genom att använda en journal för lagerrörelse.</span><span class="sxs-lookup"><span data-stu-id="d2fed-104">This procedure shows you how to get the on-hand inventory updated manually using an Inventory movement journal.</span></span> <span data-ttu-id="d2fed-105">(Det går också att uppdatera lagerbehållningen genom att importera transaktioner i dataenheter.) Du kan köra den här guiden i demonstrationsdataföretaget USMF där alla förutsättningar som journalnamn, artikelinställningar, bokföringsprofiler och konton är tillgängliga.</span><span class="sxs-lookup"><span data-stu-id="d2fed-105">(It’s also possible to update on-hand inventory by importing transactions in data entities.) You can run this guide in demo data company USMF where all the prerequisites like journal name, item setup, posting profiles, and accounts are available.</span></span> <span data-ttu-id="d2fed-106">Guiden föreslår specifika värden för artikeln och dimensioner som används.</span><span class="sxs-lookup"><span data-stu-id="d2fed-106">The guide suggests specific values for the item and dimensions that are used.</span></span> <span data-ttu-id="d2fed-107">Om du väljer en annan artikel kan du behöva ange värden för olika dimensioner.</span><span class="sxs-lookup"><span data-stu-id="d2fed-107">If you choose a different item, you may need to enter values for different dimensions.</span></span>

1. <span data-ttu-id="d2fed-108">Gå till Lagerhantering > Journalposter > Artiklar > Rörelse.</span><span class="sxs-lookup"><span data-stu-id="d2fed-108">Go to Inventory management > Journal entries > Items > Movement.</span></span>
2. <span data-ttu-id="d2fed-109">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="d2fed-109">Click New.</span></span>
3. <span data-ttu-id="d2fed-110">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="d2fed-110">In the Name field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="d2fed-111">Välj IMov.</span><span class="sxs-lookup"><span data-stu-id="d2fed-111">Select IMov.</span></span>
    * <span data-ttu-id="d2fed-112">Det är ett bra tips att använda olika journalnamnmallar för de olika arbetssyftena.</span><span class="sxs-lookup"><span data-stu-id="d2fed-112">It’s a good practise to use different journal name templates for the different business purposes.</span></span>  
5. <span data-ttu-id="d2fed-113">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="d2fed-113">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="d2fed-114">Ange värdena "140200" i fältet Motkonto.</span><span class="sxs-lookup"><span data-stu-id="d2fed-114">In the Offset account field, specify the values '140200'.</span></span>
    * <span data-ttu-id="d2fed-115">Det här är motkontot som används som standardmotkonto på journalrader.</span><span class="sxs-lookup"><span data-stu-id="d2fed-115">This is the offset account that will be the default account on the journal lines.</span></span> <span data-ttu-id="d2fed-116">Det går att åsidosätta standardinställningen för att tilldela olika motkonton per rad.</span><span class="sxs-lookup"><span data-stu-id="d2fed-116">It’s possible to override the default to assign different offset accounts per line.</span></span>  
7. <span data-ttu-id="d2fed-117">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="d2fed-117">Click OK.</span></span>
8. <span data-ttu-id="d2fed-118">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="d2fed-118">Click New.</span></span>
9. <span data-ttu-id="d2fed-119">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Artikelnummer.</span><span class="sxs-lookup"><span data-stu-id="d2fed-119">In the Item number field, click the drop-down button to open the lookup.</span></span>
10. <span data-ttu-id="d2fed-120">Välj artikel A0001.</span><span class="sxs-lookup"><span data-stu-id="d2fed-120">Select item A0001.</span></span>
11. <span data-ttu-id="d2fed-121">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="d2fed-121">In the list, click the link in the selected row.</span></span>
12. <span data-ttu-id="d2fed-122">Klicka på fliken Lagerdimensioner.</span><span class="sxs-lookup"><span data-stu-id="d2fed-122">Click the Inventory dimensions tab.</span></span>
13. <span data-ttu-id="d2fed-123">Öppna sökningen genom att klicka på listruteknappen i fältet Plats.</span><span class="sxs-lookup"><span data-stu-id="d2fed-123">In the Site field, click the drop-down button to open the lookup.</span></span>
14. <span data-ttu-id="d2fed-124">Välj plats 1.</span><span class="sxs-lookup"><span data-stu-id="d2fed-124">Select site 1.</span></span>
15. <span data-ttu-id="d2fed-125">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Lagerställe.</span><span class="sxs-lookup"><span data-stu-id="d2fed-125">In the Warehouse field, click the drop-down button to open the lookup.</span></span>
16. <span data-ttu-id="d2fed-126">Välj lagerställe 13.</span><span class="sxs-lookup"><span data-stu-id="d2fed-126">Select warehouse 13.</span></span>
17. <span data-ttu-id="d2fed-127">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="d2fed-127">In the list, click the link in the selected row.</span></span>
18. <span data-ttu-id="d2fed-128">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Plats.</span><span class="sxs-lookup"><span data-stu-id="d2fed-128">In the Location field, click the drop-down button to open the lookup.</span></span>
19. <span data-ttu-id="d2fed-129">Välj plats 13.</span><span class="sxs-lookup"><span data-stu-id="d2fed-129">Select location 13.</span></span>
20. <span data-ttu-id="d2fed-130">Ange ett tal i fältet Kvantitet.</span><span class="sxs-lookup"><span data-stu-id="d2fed-130">In the Quantity field, enter a number.</span></span>
21. <span data-ttu-id="d2fed-131">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="d2fed-131">Click Save.</span></span>
22. <span data-ttu-id="d2fed-132">Klicka på Bokför.</span><span class="sxs-lookup"><span data-stu-id="d2fed-132">Click Post.</span></span>
23. <span data-ttu-id="d2fed-133">Markera eller avmarkera kryssrutan Överför alla bokföringsfel till en ny journal.</span><span class="sxs-lookup"><span data-stu-id="d2fed-133">Check or uncheck the Transfer all posting errors to a new journal check box.</span></span>
    * <span data-ttu-id="d2fed-134">Om du aktiverar det här alternativet kopieras alla rader som inte kan bokföras till en ny journal.</span><span class="sxs-lookup"><span data-stu-id="d2fed-134">If you enable this option, any lines that fail to post will be copied to a new journal.</span></span> <span data-ttu-id="d2fed-135">Du kan använda informationen i loggen för att korrigera utleveranserna och sedan bokföra raderna igen.</span><span class="sxs-lookup"><span data-stu-id="d2fed-135">You can use the information in the log to correct the issues and then re-post the lines.</span></span>  
24. <span data-ttu-id="d2fed-136">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="d2fed-136">Click OK.</span></span>
25. <span data-ttu-id="d2fed-137">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="d2fed-137">Close the page.</span></span>
26. <span data-ttu-id="d2fed-138">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="d2fed-138">Close the page.</span></span>

