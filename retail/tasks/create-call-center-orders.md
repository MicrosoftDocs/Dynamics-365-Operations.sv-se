--- 
title: " Skapa kundtjänstorder"
description: "Den här proceduren går igenom hur du söker efter en kund, skapar en ny order, söker efter en produkt och tar emot betalningen från kunden."
author: josaw1
manager: AnnBe
ms.date: 11/14/2016
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
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 55b22d246d6bfa9e8159fb844da95f61fcf07c62
ms.openlocfilehash: 62f88cc2e28405a9d2eb43819fb09d83a64658b6
ms.contentlocale: sv-se
ms.lasthandoff: 07/28/2017

---
# <a name="create-call-center-orders"></a><span data-ttu-id="6159d-103"> Skapa kundtjänstorder</span><span class="sxs-lookup"><span data-stu-id="6159d-103">Create call center orders</span></span>

[!include[task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="6159d-104">Den här proceduren går igenom hur du söker efter en kund, skapar en ny order, söker efter en produkt och tar emot betalningen från kunden.</span><span class="sxs-lookup"><span data-stu-id="6159d-104">This procedure walks through looking up a customer, creating a new order, searching for a product, and collecting payment from the customer.</span></span> <span data-ttu-id="6159d-105">I den här proceduren används demonstrationsdataföretaget USRT och är avsedd för Försäljningsorderansvarig.</span><span class="sxs-lookup"><span data-stu-id="6159d-105">This procedure uses demo data company USRT and is intended for the Sales Order Clerk.</span></span> <span data-ttu-id="6159d-106">Förutsättningar: Användaren som utför proceduren ställs in som kundtjänstanvändare och halvårsutgåvan av Fabrikam-katalogen publiceras med minst en källkod på den.</span><span class="sxs-lookup"><span data-stu-id="6159d-106">Pre-requisites:  The user who completes the procedure is set up as a Call center user and the Fabrikam Semi-Annual Catalog is published with at least one Source code on it.</span></span>

1. <span data-ttu-id="6159d-107">Gå till Butik och handel > Kunder > Kundtjänst.</span><span class="sxs-lookup"><span data-stu-id="6159d-107">Go to Retail and commerce > Customers > Customer service.</span></span>
2. <span data-ttu-id="6159d-108">I fältet Söktext, ange sökkriterierna för att hitta kunden.</span><span class="sxs-lookup"><span data-stu-id="6159d-108">In the SearchText field, enter the search criteria to look up the customer.</span></span>
    * <span data-ttu-id="6159d-109">För den här exempelproceduren, skriv ”karen” och tryck på fliken.</span><span class="sxs-lookup"><span data-stu-id="6159d-109">For this example procedure type in 'karen' and press tab.</span></span>  
3. <span data-ttu-id="6159d-110">Klicka på Sök.</span><span class="sxs-lookup"><span data-stu-id="6159d-110">Click Search.</span></span>
    * <span data-ttu-id="6159d-111">Eftersom det bara finns en kund med namnet Karen i demodata, kommer de automatiskt markeras.</span><span class="sxs-lookup"><span data-stu-id="6159d-111">Since there is only one customer named Karen in demo data they will be automatically selected.</span></span>  
4. <span data-ttu-id="6159d-112">Klicka på Ny försäljningsorder.</span><span class="sxs-lookup"><span data-stu-id="6159d-112">Click New sales order.</span></span>
5. <span data-ttu-id="6159d-113">Expandera eller komprimera avsnittet Försäljningsorderhuvud.</span><span class="sxs-lookup"><span data-stu-id="6159d-113">Expand or collapse the Sales order header section.</span></span>
6. <span data-ttu-id="6159d-114">Välj källkoden för katalogen.</span><span class="sxs-lookup"><span data-stu-id="6159d-114">Select the source code for the catalog.</span></span>
    * <span data-ttu-id="6159d-115">Om det inte finns några aktiva källkoder kan du stänga källfältet och hoppa över det här steget.</span><span class="sxs-lookup"><span data-stu-id="6159d-115">If there are no active Source codes you can close the Source field and skip this step.</span></span>  
7. <span data-ttu-id="6159d-116">Klicka på Lägg till rad.</span><span class="sxs-lookup"><span data-stu-id="6159d-116">Click Add line.</span></span>
8. <span data-ttu-id="6159d-117">Ange artikelsöktermen i fältet Artikelnummer.</span><span class="sxs-lookup"><span data-stu-id="6159d-117">In the Item number field, enter the item search term.</span></span>
    * <span data-ttu-id="6159d-118">För den här exempelproceduren, ange ett delvis artikelnummer 8111 och tryck på fliken.</span><span class="sxs-lookup"><span data-stu-id="6159d-118">For this sample procedure enter a partial item number of '8111' and press tab.</span></span> <span data-ttu-id="6159d-119">Då poppar artikelsökningsfönstret upp.</span><span class="sxs-lookup"><span data-stu-id="6159d-119">This will pop up the item search window.</span></span>  
9. <span data-ttu-id="6159d-120">Välj produkten att lägga till försäljningsordern</span><span class="sxs-lookup"><span data-stu-id="6159d-120">Select the product to add to the sales order</span></span>
10. <span data-ttu-id="6159d-121">Ange försäljningskvantiteten.</span><span class="sxs-lookup"><span data-stu-id="6159d-121">Enter the sales quantity.</span></span>
11. <span data-ttu-id="6159d-122">Klicka på Skapa.</span><span class="sxs-lookup"><span data-stu-id="6159d-122">Click Create.</span></span>
12. <span data-ttu-id="6159d-123">Klicka på Slutför för att registrera kundbetalningen.</span><span class="sxs-lookup"><span data-stu-id="6159d-123">Click Complete to capture the customer payment.</span></span>
13. <span data-ttu-id="6159d-124">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="6159d-124">Click Add.</span></span>
    * <span data-ttu-id="6159d-125">Lägg till länk finns på betalningsfliken.</span><span class="sxs-lookup"><span data-stu-id="6159d-125">The Add link is in the Payments tab.</span></span> <span data-ttu-id="6159d-126">Expandera fliken Betalning om den är komprimerad.</span><span class="sxs-lookup"><span data-stu-id="6159d-126">Expand the Payments tab if it is collapsed.</span></span>  
14. <span data-ttu-id="6159d-127">Välj betalningsmetod.</span><span class="sxs-lookup"><span data-stu-id="6159d-127">Select the payment method.</span></span>
    * <span data-ttu-id="6159d-128">Välj betalningsmetoden kontant för den här proceduren.</span><span class="sxs-lookup"><span data-stu-id="6159d-128">For this procedure, select the cash payment method.</span></span>  
15. <span data-ttu-id="6159d-129">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="6159d-129">Close the page.</span></span>
16. <span data-ttu-id="6159d-130">Ange belopp.</span><span class="sxs-lookup"><span data-stu-id="6159d-130">Enter the amount.</span></span>
    * <span data-ttu-id="6159d-131">För den här proceduren, ange ett belopp lika med ordersaldot som kan visas på sammanfattningssidan för försäljningsorder till vänster om beloppsfältet.</span><span class="sxs-lookup"><span data-stu-id="6159d-131">For this procedure enter an amount equal to the order balance which can be seen in the Sales order summary page to the left of the amount field.</span></span> <span data-ttu-id="6159d-132">Detta gör att du slutför ordern som helt betald.</span><span class="sxs-lookup"><span data-stu-id="6159d-132">This will allow you to complete the order as fully paid.</span></span>  
17. <span data-ttu-id="6159d-133">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="6159d-133">Click OK.</span></span>
18. <span data-ttu-id="6159d-134">Klicka på Skicka.</span><span class="sxs-lookup"><span data-stu-id="6159d-134">Click Submit.</span></span>


