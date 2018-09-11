--- 
title: " Skapa kundtjänstorder"
description: "Den här proceduren går igenom hur du söker efter en kund, skapar en ny order, söker efter en produkt och tar emot betalningen från kunden."
author: josaw1
manager: AnnBe
ms.date: 8/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: MCRCustomerService, SalesTable, MCRSourceIdTargetLookup, MCRSalesQuickQuote, MCRSalesOrderRecap, MCRCustPaymDialog, MCRCustPaymLookup
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 32d71167fdad65cb1dec37671999a497759ca484
ms.openlocfilehash: 9280d791c1d846eff2429891c26291ce05d6e6dd
ms.contentlocale: sv-se
ms.lasthandoff: 09/11/2018

---
# <a name="create-call-center-orders"></a><span data-ttu-id="dc160-103"> Skapa kundtjänstorder</span><span class="sxs-lookup"><span data-stu-id="dc160-103">Create call center orders</span></span>

[!include[task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="dc160-104">Den här proceduren går igenom hur du söker efter en kund, skapar en ny order, söker efter en produkt och tar emot betalningen från kunden.</span><span class="sxs-lookup"><span data-stu-id="dc160-104">This procedure walks through looking up a customer, creating a new order, searching for a product, and collecting payment from the customer.</span></span> <span data-ttu-id="dc160-105">I den här proceduren används demonstrationsdataföretaget USRT och är avsedd för Försäljningsorderansvarig.</span><span class="sxs-lookup"><span data-stu-id="dc160-105">This procedure uses demo data company USRT and is intended for the Sales Order Clerk.</span></span> <span data-ttu-id="dc160-106">Förutsättningar: Användaren som utför proceduren ställs in som kundtjänstanvändare och halvårsutgåvan av Fabrikam-katalogen publiceras med minst en källkod på den.</span><span class="sxs-lookup"><span data-stu-id="dc160-106">Pre-requisites:  The user who completes the procedure is set up as a Call center user and the Fabrikam Semi-Annual Catalog is published with at least one Source code on it.</span></span>

1. <span data-ttu-id="dc160-107">Gå till Butik och handel > Kunder > Kundtjänst.</span><span class="sxs-lookup"><span data-stu-id="dc160-107">Go to Retail and commerce > Customers > Customer service.</span></span>
2. <span data-ttu-id="dc160-108">I fältet Söktext, ange sökkriterierna för att hitta kunden.</span><span class="sxs-lookup"><span data-stu-id="dc160-108">In the SearchText field, enter the search criteria to look up the customer.</span></span>
    * <span data-ttu-id="dc160-109">För den här exempelproceduren, skriv ”karen” och tryck på fliken.</span><span class="sxs-lookup"><span data-stu-id="dc160-109">For this example procedure type in 'karen' and press tab.</span></span>  
3. <span data-ttu-id="dc160-110">Klicka på Sök.</span><span class="sxs-lookup"><span data-stu-id="dc160-110">Click Search.</span></span>
    * <span data-ttu-id="dc160-111">Eftersom det bara finns en kund med namnet Karen i demodata, kommer de automatiskt markeras.</span><span class="sxs-lookup"><span data-stu-id="dc160-111">Since there is only one customer named Karen in demo data they will be automatically selected.</span></span>  
4. <span data-ttu-id="dc160-112">Klicka på Ny försäljningsorder.</span><span class="sxs-lookup"><span data-stu-id="dc160-112">Click New sales order.</span></span>
5. <span data-ttu-id="dc160-113">Expandera eller komprimera avsnittet Försäljningsorderhuvud.</span><span class="sxs-lookup"><span data-stu-id="dc160-113">Expand or collapse the Sales order header section.</span></span>
6. <span data-ttu-id="dc160-114">Välj källkoden för katalogen.</span><span class="sxs-lookup"><span data-stu-id="dc160-114">Select the source code for the catalog.</span></span>
    * <span data-ttu-id="dc160-115">Om det inte finns några aktiva källkoder kan du stänga källfältet och hoppa över det här steget.</span><span class="sxs-lookup"><span data-stu-id="dc160-115">If there are no active Source codes you can close the Source field and skip this step.</span></span>  
7. <span data-ttu-id="dc160-116">Klicka på Lägg till rad.</span><span class="sxs-lookup"><span data-stu-id="dc160-116">Click Add line.</span></span>
8. <span data-ttu-id="dc160-117">Ange artikelsöktermen i fältet Artikelnummer.</span><span class="sxs-lookup"><span data-stu-id="dc160-117">In the Item number field, enter the item search term.</span></span>
    * <span data-ttu-id="dc160-118">För den här exempelproceduren, ange ett delvis artikelnummer 8111 och tryck på fliken. Då poppar artikelsökningsfönstret upp.</span><span class="sxs-lookup"><span data-stu-id="dc160-118">For this sample procedure enter a partial item number of '8111' and press tab. This will pop up the item search window.</span></span>  
9. <span data-ttu-id="dc160-119">Välj produkten att lägga till försäljningsordern</span><span class="sxs-lookup"><span data-stu-id="dc160-119">Select the product to add to the sales order</span></span>
10. <span data-ttu-id="dc160-120">Ange försäljningskvantiteten.</span><span class="sxs-lookup"><span data-stu-id="dc160-120">Enter the sales quantity.</span></span>
11. <span data-ttu-id="dc160-121">Klicka på Skapa.</span><span class="sxs-lookup"><span data-stu-id="dc160-121">Click Create.</span></span>
12. <span data-ttu-id="dc160-122">Klicka på Slutför för att registrera kundbetalningen.</span><span class="sxs-lookup"><span data-stu-id="dc160-122">Click Complete to capture the customer payment.</span></span>
13. <span data-ttu-id="dc160-123">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="dc160-123">Click Add.</span></span>
    * <span data-ttu-id="dc160-124">Lägg till länk finns på betalningsfliken. Expandera fliken Betalning om den är komprimerad.</span><span class="sxs-lookup"><span data-stu-id="dc160-124">The Add link is in the Payments tab. Expand the Payments tab if it is collapsed.</span></span>  
14. <span data-ttu-id="dc160-125">Välj betalningsmetod.</span><span class="sxs-lookup"><span data-stu-id="dc160-125">Select the payment method.</span></span>
    * <span data-ttu-id="dc160-126">Välj betalningsmetoden kontant för den här proceduren.</span><span class="sxs-lookup"><span data-stu-id="dc160-126">For this procedure, select the cash payment method.</span></span>  
15. <span data-ttu-id="dc160-127">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="dc160-127">Close the page.</span></span>
16. <span data-ttu-id="dc160-128">Ange belopp.</span><span class="sxs-lookup"><span data-stu-id="dc160-128">Enter the amount.</span></span>
    * <span data-ttu-id="dc160-129">För den här proceduren, ange ett belopp lika med ordersaldot som kan visas på sammanfattningssidan för försäljningsorder till vänster om beloppsfältet.</span><span class="sxs-lookup"><span data-stu-id="dc160-129">For this procedure enter an amount equal to the order balance which can be seen in the Sales order summary page to the left of the amount field.</span></span> <span data-ttu-id="dc160-130">Detta gör att du slutför ordern som helt betald.</span><span class="sxs-lookup"><span data-stu-id="dc160-130">This will allow you to complete the order as fully paid.</span></span>  
17. <span data-ttu-id="dc160-131">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="dc160-131">Click OK.</span></span>
18. <span data-ttu-id="dc160-132">Klicka på Skicka.</span><span class="sxs-lookup"><span data-stu-id="dc160-132">Click Submit.</span></span>


