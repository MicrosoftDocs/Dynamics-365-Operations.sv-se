--- 
title: Skapa butiksprisjusteringar
description: "Den här proceduren går igenom hur du skapar en butiksprisjustering."
author: josaw1
manager: AnnBe
ms.date: 06/07/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations, Retail
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 5098fb3339403b6f2779dfe3bb7ef5c4ca78051f
ms.openlocfilehash: 6dd4e12008838460c0bb0ade907ea78d06c80fed
ms.contentlocale: sv-se
ms.lasthandoff: 08/09/2018

---
# <a name="create-retail-price-adjustments"></a><span data-ttu-id="fc9c7-103">Skapa butiksprisjusteringar</span><span class="sxs-lookup"><span data-stu-id="fc9c7-103">Create retail price adjustments</span></span>

[!include [task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="fc9c7-104">Den här proceduren går igenom hur du skapar en butiksprisjustering.</span><span class="sxs-lookup"><span data-stu-id="fc9c7-104">This procedure will walk through creating a retail price adjustment.</span></span> <span data-ttu-id="fc9c7-105">En butiksprisjustering kan ange en artikels försäljningspris direkt eller ändra dess basförsäljningspris eller handelsavtalsförsäljningspris.</span><span class="sxs-lookup"><span data-stu-id="fc9c7-105">A retail price adjustment can set an item's sale price directly, or modify its base sale price or trade agreement sale price.</span></span> <span data-ttu-id="fc9c7-106">I proceduren används demonstrationsföretaget USRT.</span><span class="sxs-lookup"><span data-stu-id="fc9c7-106">This procedure uses the USRT demo data company.</span></span>

1. <span data-ttu-id="fc9c7-107">Klicka på prissättning och rabatter.</span><span class="sxs-lookup"><span data-stu-id="fc9c7-107">Click Pricing and discount management.</span></span>
2. <span data-ttu-id="fc9c7-108">Klicka på fliken Prisjusteringar.</span><span class="sxs-lookup"><span data-stu-id="fc9c7-108">Click the Price adjustments tab.</span></span>
3. <span data-ttu-id="fc9c7-109">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="fc9c7-109">Click New.</span></span>
    * <span data-ttu-id="fc9c7-110">Härifrån kan du skapa alla de flesta vanliga regler för prissättning och rabatter, inklusive butiksrabatter, prisjusteringar, handelsavtalsjournaler och kategoriprissättningsregler.</span><span class="sxs-lookup"><span data-stu-id="fc9c7-110">From here you can create all of the most commonly used price and discount rules, including retail discounts, price adjustments, trade agreement journals, and category pricing rules.</span></span>  
4. <span data-ttu-id="fc9c7-111">Klicka på Prisjustering.</span><span class="sxs-lookup"><span data-stu-id="fc9c7-111">Click Price adjustment.</span></span>
5. <span data-ttu-id="fc9c7-112">Skriv ett värde i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="fc9c7-112">In the Name field, type a value.</span></span>
6. <span data-ttu-id="fc9c7-113">Expandera avsnittet Rader.</span><span class="sxs-lookup"><span data-stu-id="fc9c7-113">Expand the Lines section.</span></span>
7. <span data-ttu-id="fc9c7-114">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="fc9c7-114">Click Add.</span></span>
    * <span data-ttu-id="fc9c7-115">Ange 81126 i fältet Produkt i det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="fc9c7-115">For this example, enter '81126' in the Product field.</span></span>    <span data-ttu-id="fc9c7-116">Ange sedan värdet 10,0 i fältet Rabattprocent.</span><span class="sxs-lookup"><span data-stu-id="fc9c7-116">Then, enter '10.0' in the Discount percentage field.</span></span>  
    * <span data-ttu-id="fc9c7-117">En prisjustering för typ av rabattprocent minskar ett basförsäljningspris eller handelsavtalsförsäljningspris.</span><span class="sxs-lookup"><span data-stu-id="fc9c7-117">A discount percentage type price adjustment will reduce a base sales price or trade agreement sales price.</span></span>  
8. <span data-ttu-id="fc9c7-118">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="fc9c7-118">Click Add.</span></span>
    * <span data-ttu-id="fc9c7-119">Ange 81125 i fältet Produkt i det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="fc9c7-119">For this example, enter '81125' in the Product field.</span></span>    <span data-ttu-id="fc9c7-120">Välj sedan Kassarabattbelopp i fältet Rabattmetod.</span><span class="sxs-lookup"><span data-stu-id="fc9c7-120">Then, select 'Cash discount amount' in the Discount method field.</span></span>    <span data-ttu-id="fc9c7-121">Ange slutligen 5,0 i fältet Kassarabattbelopp.</span><span class="sxs-lookup"><span data-stu-id="fc9c7-121">Finally, enter '5.0' in the Cash discount amount field.</span></span>  
    * <span data-ttu-id="fc9c7-122">En rabattyp för kassarabatt i beloppsform är ett belopp som dras av från ett baspris eller ett handelsavtalspris.</span><span class="sxs-lookup"><span data-stu-id="fc9c7-122">A Cash discount amount discount type is an amount taken off from a base price or a trade agreement price.</span></span>  
9. <span data-ttu-id="fc9c7-123">Klicka på prisgrupper.</span><span class="sxs-lookup"><span data-stu-id="fc9c7-123">Click Price groups.</span></span>
    * <span data-ttu-id="fc9c7-124">Välj RP-Houston i fältet Prisgrupp.</span><span class="sxs-lookup"><span data-stu-id="fc9c7-124">Select 'RP-Houston' in the Price group field.</span></span>  
    * <span data-ttu-id="fc9c7-125">Det kopplar prisjusteringen till Houston-butiken.</span><span class="sxs-lookup"><span data-stu-id="fc9c7-125">This will associate the Price adjustment to the Houston store.</span></span>  
10. <span data-ttu-id="fc9c7-126">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="fc9c7-126">Click Save.</span></span>
11. <span data-ttu-id="fc9c7-127">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="fc9c7-127">Close the page.</span></span>
12. <span data-ttu-id="fc9c7-128">Välj Aktiverad i fältet Status.</span><span class="sxs-lookup"><span data-stu-id="fc9c7-128">In the Status field, select 'Enabled'.</span></span>
13. <span data-ttu-id="fc9c7-129">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="fc9c7-129">Click Save.</span></span>
14. <span data-ttu-id="fc9c7-130">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="fc9c7-130">Close the page.</span></span>
15. <span data-ttu-id="fc9c7-131">Uppdatera sidan.</span><span class="sxs-lookup"><span data-stu-id="fc9c7-131">Refresh the page.</span></span>


