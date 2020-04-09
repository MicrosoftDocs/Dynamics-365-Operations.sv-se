---
title: " Kategoriprissättningsregler för att skapa handelsavtal"
description: I den här proceduren visas hur du skapar handelsavtal för försäljningspris med hjälp av en kategoriprissättningsregel.
author: scott-tucker
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, RetailDiscountPricingWorkspace, RetailPricingDiscountCategoryPriceRule, RetailCategoryPriceRule, EcoResCategorySingleLookup, RetailCategoryPriceWizard, PriceDiscAdm, PriceDiscAdmTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: scotttuc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 21b1986aa36aab23f50a5af434435f9e93318e45
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/18/2020
ms.locfileid: "3141093"
---
# <a name="category-pricing-rules-to-create-trade-agreements"></a><span data-ttu-id="2059a-103"> Kategoriprissättningsregler för att skapa handelsavtal</span><span class="sxs-lookup"><span data-stu-id="2059a-103">Category pricing rules to create trade agreements</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="2059a-104">I den här proceduren visas hur du skapar handelsavtal för försäljningspris med hjälp av en kategoriprissättningsregel.</span><span class="sxs-lookup"><span data-stu-id="2059a-104">This procedure demonstrates how to create sales price trade agreements using a category pricing rule.</span></span> <span data-ttu-id="2059a-105">Det demonstrationsdataföretag som används för att skapa den här uppgiften är USRT.</span><span class="sxs-lookup"><span data-stu-id="2059a-105">The demo data company used to create this task is USRT.</span></span> <span data-ttu-id="2059a-106">Denna uppgift är avsedd för rollen marknadsföringschef (handel).</span><span class="sxs-lookup"><span data-stu-id="2059a-106">This task is intended for the Commerce merchandising manager role.</span></span>

1. <span data-ttu-id="2059a-107">Klicka på prissättning och rabatter.</span><span class="sxs-lookup"><span data-stu-id="2059a-107">Click Pricing and discount management.</span></span>
2. <span data-ttu-id="2059a-108">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="2059a-108">Click New.</span></span>
3. <span data-ttu-id="2059a-109">Klicka på Kategoriprisregel.</span><span class="sxs-lookup"><span data-stu-id="2059a-109">Click Category price rule.</span></span>
4. <span data-ttu-id="2059a-110">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="2059a-110">In the list, mark the selected row.</span></span>
5. <span data-ttu-id="2059a-111">I fältet Kontokod, välj ett alternativ.</span><span class="sxs-lookup"><span data-stu-id="2059a-111">In the Account code field, select an option.</span></span>
    * <span data-ttu-id="2059a-112">En Grupp-typkontokod används för att ställa in handelsavtal som är specifika för kanaler, bonusprogram, kataloger och anknytningar.</span><span class="sxs-lookup"><span data-stu-id="2059a-112">A "Group" type account code is used to set up sales price trade agreements that are specific for Channels, Loyalty programs, Catalogs, and Affiliations.</span></span>  
6. <span data-ttu-id="2059a-113">I fältet Kontomarkering, ange eller välj ett värde.</span><span class="sxs-lookup"><span data-stu-id="2059a-113">In the Account selection field, enter or select a value.</span></span>
7. <span data-ttu-id="2059a-114">I fältet Kategori, ange eller välj ett värde.</span><span class="sxs-lookup"><span data-stu-id="2059a-114">In the Category field, enter or select a value.</span></span>
8. <span data-ttu-id="2059a-115">I fältet Belopp/procent, ange ett tal.</span><span class="sxs-lookup"><span data-stu-id="2059a-115">In the Amount/Percent field, enter a number.</span></span>
9. <span data-ttu-id="2059a-116">I fältet Avrundningsversion, ange eller välj ett värde.</span><span class="sxs-lookup"><span data-stu-id="2059a-116">In the Rounding version field, enter or select a value.</span></span>
10. <span data-ttu-id="2059a-117">Klicka på Skapa handelsavtal.</span><span class="sxs-lookup"><span data-stu-id="2059a-117">Click Generate trade agreements.</span></span>
11. <span data-ttu-id="2059a-118">Klicka på Nästa.</span><span class="sxs-lookup"><span data-stu-id="2059a-118">Click Next.</span></span>
12. <span data-ttu-id="2059a-119">Ange ett datum i fältet Från datum.</span><span class="sxs-lookup"><span data-stu-id="2059a-119">In the From date field, enter a date.</span></span>
13. <span data-ttu-id="2059a-120">Ange ett datum i fältet Till datum.</span><span class="sxs-lookup"><span data-stu-id="2059a-120">In the To date field, enter a date.</span></span>
14. <span data-ttu-id="2059a-121">Välj Ja i fältet Sök nästa.</span><span class="sxs-lookup"><span data-stu-id="2059a-121">Select Yes in the Find next field.</span></span>
15. <span data-ttu-id="2059a-122">Klicka på Nästa.</span><span class="sxs-lookup"><span data-stu-id="2059a-122">Click Next.</span></span>
16. <span data-ttu-id="2059a-123">Klicka på Avsluta.</span><span class="sxs-lookup"><span data-stu-id="2059a-123">Click Finish.</span></span>
    * <span data-ttu-id="2059a-124">Då skapas en handelsavtalsjournal som öppnas för granskning.</span><span class="sxs-lookup"><span data-stu-id="2059a-124">This creates a Trade agreement journal and opens it for your review.</span></span>  
17. <span data-ttu-id="2059a-125">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="2059a-125">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="2059a-126">Handelsavtalsjournalerna som skapas från kategoriprissättningsreglerna bokförs inte.</span><span class="sxs-lookup"><span data-stu-id="2059a-126">The trade agreement journals created from the Category pricing rules aren't posted.</span></span> <span data-ttu-id="2059a-127">Du kan granska och redigera priserna som skapas innan du bokför dem.</span><span class="sxs-lookup"><span data-stu-id="2059a-127">You can  review and edit the prices generated before posting them.</span></span>  
18. <span data-ttu-id="2059a-128">Klicka på Redigera.</span><span class="sxs-lookup"><span data-stu-id="2059a-128">Click Edit.</span></span>
19. <span data-ttu-id="2059a-129">Ange ett nummer i fältet Belopp i valuta.</span><span class="sxs-lookup"><span data-stu-id="2059a-129">In the Amount in currency field, enter a number.</span></span>
20. <span data-ttu-id="2059a-130">Klicka på Bokför.</span><span class="sxs-lookup"><span data-stu-id="2059a-130">Click Post.</span></span>
21. <span data-ttu-id="2059a-131">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="2059a-131">Click OK.</span></span>
22. <span data-ttu-id="2059a-132">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="2059a-132">Close the page.</span></span>
23. <span data-ttu-id="2059a-133">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="2059a-133">Close the page.</span></span>
24. <span data-ttu-id="2059a-134">Klicka på fliken Kategoriprisregler.</span><span class="sxs-lookup"><span data-stu-id="2059a-134">Click the Category price rules tab.</span></span>
    * <span data-ttu-id="2059a-135">Kanalspecifika kategoriprissättningsregler visas i den här listan.</span><span class="sxs-lookup"><span data-stu-id="2059a-135">Channel specific Category pricing rules will show in this list.</span></span>  

