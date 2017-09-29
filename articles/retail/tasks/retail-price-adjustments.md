--- 
title: " Underhåll butiksprisjusteringar"
description: "Den här proceduren går igenom hur du skapar en butiksprisjustering."
author: josaw1
manager: AnnBe
ms.date: 06/07/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: dab14468713f9f23d20e7ca648711e2a4337cf7c
ms.contentlocale: sv-se
ms.lasthandoff: 08/29/2017

---
# <a name="retail-price-adjustments"></a><span data-ttu-id="b258c-103"> Underhåll butiksprisjusteringar</span><span class="sxs-lookup"><span data-stu-id="b258c-103">Retail price adjustments</span></span>

[!include[task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="b258c-104">Den här proceduren går igenom hur du skapar en butiksprisjustering.</span><span class="sxs-lookup"><span data-stu-id="b258c-104">This procedure will walk through creating a retail price adjustment.</span></span> <span data-ttu-id="b258c-105">En butiksprisjustering kan ange en artikels försäljningspris direkt eller ändra dess basförsäljningspris eller handelsavtalsförsäljningspris.</span><span class="sxs-lookup"><span data-stu-id="b258c-105">A retail price adjustment can set an item's sale price directly, or modify its base sale price or trade agreement sale price.</span></span> <span data-ttu-id="b258c-106">I proceduren används demonstrationsföretaget USRT.</span><span class="sxs-lookup"><span data-stu-id="b258c-106">This procedure uses the USRT demo data company.</span></span>

1. <span data-ttu-id="b258c-107">Klicka på prissättning och rabatter.</span><span class="sxs-lookup"><span data-stu-id="b258c-107">Click Pricing and discount management.</span></span>
2. <span data-ttu-id="b258c-108">Klicka på fliken Prisjusteringar.</span><span class="sxs-lookup"><span data-stu-id="b258c-108">Click the Price adjustments tab.</span></span>
3. <span data-ttu-id="b258c-109">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="b258c-109">Click New.</span></span>
    * <span data-ttu-id="b258c-110">Härifrån kan du skapa alla de flesta vanliga regler för prissättning och rabatter, inklusive butiksrabatter, prisjusteringar, handelsavtalsjournaler och kategoriprissättningsregler.</span><span class="sxs-lookup"><span data-stu-id="b258c-110">From here you can create all of the most commonly used price and discount rules, including retail discounts, price adjustments, trade agreement journals, and category pricing rules.</span></span>  
4. <span data-ttu-id="b258c-111">Klicka på Prisjustering.</span><span class="sxs-lookup"><span data-stu-id="b258c-111">Click Price adjustment.</span></span>
5. <span data-ttu-id="b258c-112">Skriv ett värde i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="b258c-112">In the Name field, type a value.</span></span>
6. <span data-ttu-id="b258c-113">Expandera avsnittet Rader.</span><span class="sxs-lookup"><span data-stu-id="b258c-113">Expand the Lines section.</span></span>
7. <span data-ttu-id="b258c-114">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="b258c-114">Click Add.</span></span>
    * <span data-ttu-id="b258c-115">Ange 81126 i fältet Produkt i det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="b258c-115">For this example, enter '81126' in the Product field.</span></span>    <span data-ttu-id="b258c-116">Ange sedan värdet 10,0 i fältet Rabattprocent.</span><span class="sxs-lookup"><span data-stu-id="b258c-116">Then, enter '10.0' in the Discount percentage field.</span></span>  
    * <span data-ttu-id="b258c-117">En prisjustering för typ av rabattprocent minskar ett basförsäljningspris eller handelsavtalsförsäljningspris.</span><span class="sxs-lookup"><span data-stu-id="b258c-117">A discount percentage type price adjustment will reduce a base sales price or trade agreement sales price.</span></span>  
8. <span data-ttu-id="b258c-118">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="b258c-118">Click Add.</span></span>
    * <span data-ttu-id="b258c-119">Ange 81125 i fältet Produkt i det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="b258c-119">For this example, enter '81125' in the Product field.</span></span>    <span data-ttu-id="b258c-120">Välj sedan Kassarabattbelopp i fältet Rabattmetod.</span><span class="sxs-lookup"><span data-stu-id="b258c-120">Then, select 'Cash discount amount' in the Discount method field.</span></span>    <span data-ttu-id="b258c-121">Ange slutligen 5,0 i fältet Kassarabattbelopp.</span><span class="sxs-lookup"><span data-stu-id="b258c-121">Finally, enter '5.0' in the Cash discount amount field.</span></span>  
    * <span data-ttu-id="b258c-122">En rabattyp för kassarabatt i beloppsform är ett belopp som dras av från ett baspris eller ett handelsavtalspris.</span><span class="sxs-lookup"><span data-stu-id="b258c-122">A Cash discount amount discount type is an amount taken off from a base price or a trade agreement price.</span></span>  
9. <span data-ttu-id="b258c-123">Klicka på prisgrupper.</span><span class="sxs-lookup"><span data-stu-id="b258c-123">Click Price groups.</span></span>
    * <span data-ttu-id="b258c-124">Välj RP-Houston i fältet Prisgrupp.</span><span class="sxs-lookup"><span data-stu-id="b258c-124">Select 'RP-Houston' in the Price group field.</span></span>  
    * <span data-ttu-id="b258c-125">Det kopplar prisjusteringen till Houston-butiken.</span><span class="sxs-lookup"><span data-stu-id="b258c-125">This will associate the Price adjustment to the Houston store.</span></span>  
10. <span data-ttu-id="b258c-126">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="b258c-126">Click Save.</span></span>
11. <span data-ttu-id="b258c-127">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="b258c-127">Close the page.</span></span>
12. <span data-ttu-id="b258c-128">Välj Aktiverad i fältet Status.</span><span class="sxs-lookup"><span data-stu-id="b258c-128">In the Status field, select 'Enabled'.</span></span>
13. <span data-ttu-id="b258c-129">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="b258c-129">Click Save.</span></span>
14. <span data-ttu-id="b258c-130">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="b258c-130">Close the page.</span></span>
15. <span data-ttu-id="b258c-131">Uppdatera sidan.</span><span class="sxs-lookup"><span data-stu-id="b258c-131">Refresh the page.</span></span>


