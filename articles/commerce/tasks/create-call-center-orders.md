---
title: " Skapa kundtjänstorder"
description: Den här proceduren går igenom hur du söker efter en kund, skapar en ny order, söker efter en produkt och tar emot betalningen från kunden.
author: josaw1
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: MCRCustomerService, SalesTable, MCRSourceIdTargetLookup, MCRSalesQuickQuote, MCRSalesOrderRecap, MCRCustPaymDialog, MCRCustPaymLookup
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: c875eaa85d9da997b75b296ad9ace99ae1e91798
ms.sourcegitcommit: 597476103bb695e3cbe6d9ffcd7a466400346636
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/20/2020
ms.locfileid: "4594246"
---
# <a name="create-call-center-orders"></a><span data-ttu-id="3d846-103"> Skapa kundtjänstorder</span><span class="sxs-lookup"><span data-stu-id="3d846-103">Create call center orders</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="3d846-104">Den här proceduren går igenom hur du söker efter en kund, skapar en ny order, söker efter en produkt och tar emot betalningen från kunden.</span><span class="sxs-lookup"><span data-stu-id="3d846-104">This procedure walks through looking up a customer, creating a new order, searching for a product, and collecting payment from the customer.</span></span> <span data-ttu-id="3d846-105">I den här proceduren används demonstrationsdataföretaget USRT och är avsedd för Försäljningsorderansvarig.</span><span class="sxs-lookup"><span data-stu-id="3d846-105">This procedure uses demo data company USRT and is intended for the Sales Order Clerk.</span></span> <span data-ttu-id="3d846-106">Förutsättningar: Användaren som utför proceduren ställs in som kundtjänstanvändare och halvårsutgåvan av Fabrikam-katalogen publiceras med minst en källkod på den.</span><span class="sxs-lookup"><span data-stu-id="3d846-106">Pre-requisites:  The user who completes the procedure is set up as a Call center user and the Fabrikam Semi-Annual Catalog is published with at least one Source code on it.</span></span>

1. <span data-ttu-id="3d846-107">Gå till **Butik och handel \> Kunder \> Kundtjänst**.</span><span class="sxs-lookup"><span data-stu-id="3d846-107">Go to **Retail and Commerce \> Customers \> Customer service**.</span></span>
2. <span data-ttu-id="3d846-108">För **Söktext**, ange sökkriterierna för att hitta kunden.</span><span class="sxs-lookup"><span data-stu-id="3d846-108">For **SearchText**, enter the search criteria to look up the customer.</span></span>
    * <span data-ttu-id="3d846-109">För den här exempelproceduren, skriv ”karen” och tryck på **flik**.</span><span class="sxs-lookup"><span data-stu-id="3d846-109">For this example procedure, enter "Karen" and select **Tab**.</span></span>  
3. <span data-ttu-id="3d846-110">Välj Sök.</span><span class="sxs-lookup"><span data-stu-id="3d846-110">Select Search.</span></span>
    * <span data-ttu-id="3d846-111">Eftersom det bara finns en kund med namnet Karen i demodata, kommer resultatet automatiskt markeras.</span><span class="sxs-lookup"><span data-stu-id="3d846-111">Since there is only one customer named "Karen" in demo data, the result will be automatically selected.</span></span>  
4. <span data-ttu-id="3d846-112">Välj **Ny försäljningsorder**.</span><span class="sxs-lookup"><span data-stu-id="3d846-112">Select **New sales order**.</span></span>
5. <span data-ttu-id="3d846-113">Expandera eller komprimera avsnittet **Försäljningsorderhuvud**.</span><span class="sxs-lookup"><span data-stu-id="3d846-113">Expand or collapse the **Sales order** header section.</span></span>
6. <span data-ttu-id="3d846-114">Välj källkoden för katalogen.</span><span class="sxs-lookup"><span data-stu-id="3d846-114">Select the source code for the catalog.</span></span>
    * <span data-ttu-id="3d846-115">Om det inte finns några aktiva källkoder kan du hoppa över det här steget.</span><span class="sxs-lookup"><span data-stu-id="3d846-115">If there are no active source codes you can skip this step.</span></span>  
7. <span data-ttu-id="3d846-116">Välj **Markera rad**.</span><span class="sxs-lookup"><span data-stu-id="3d846-116">Select **Add line**.</span></span>
8. <span data-ttu-id="3d846-117">För **Artikelnummer** ange artikelsöktermen.</span><span class="sxs-lookup"><span data-stu-id="3d846-117">For **Item number**, enter the item search term.</span></span>
    * <span data-ttu-id="3d846-118">För den här exempelproceduren, ange ett delvis artikelnummer 8111 och tryck på fliken. Denna åtgärd öppnar artikelsökningsfönstret.</span><span class="sxs-lookup"><span data-stu-id="3d846-118">For this sample procedure, enter a partial item number of '8111' and press tab. This action will bring up the item search window.</span></span>  
9. <span data-ttu-id="3d846-119">Välj produkten att lägga till försäljningsordern.</span><span class="sxs-lookup"><span data-stu-id="3d846-119">Select the product to add to the sales order.</span></span>
10. <span data-ttu-id="3d846-120">Ange försäljningskvantiteten.</span><span class="sxs-lookup"><span data-stu-id="3d846-120">Enter the sales quantity.</span></span>
11. <span data-ttu-id="3d846-121">Markera **Skapa**.</span><span class="sxs-lookup"><span data-stu-id="3d846-121">Select **Create**.</span></span>
12. <span data-ttu-id="3d846-122">Klicka på **Slutför** för att registrera kundbetalningen.</span><span class="sxs-lookup"><span data-stu-id="3d846-122">Select **Complete** to capture the customer payment.</span></span>
13. <span data-ttu-id="3d846-123">Markera **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="3d846-123">Select **Add**.</span></span>
    * <span data-ttu-id="3d846-124">Lägg till länk finns på betalningsfliken. Expandera fliken Betalning om den är komprimerad.</span><span class="sxs-lookup"><span data-stu-id="3d846-124">The Add link is in the Payments tab. Expand the Payments tab if it is collapsed.</span></span>  
14. <span data-ttu-id="3d846-125">Välj betalningsmetod.</span><span class="sxs-lookup"><span data-stu-id="3d846-125">Select the payment method.</span></span>
    * <span data-ttu-id="3d846-126">Välj betalningsmetoden kontant för den här proceduren.</span><span class="sxs-lookup"><span data-stu-id="3d846-126">For this procedure, select the cash payment method.</span></span>  
15. <span data-ttu-id="3d846-127">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="3d846-127">Close the page.</span></span>
16. <span data-ttu-id="3d846-128">Ange belopp.</span><span class="sxs-lookup"><span data-stu-id="3d846-128">Enter the amount.</span></span>
    * <span data-ttu-id="3d846-129">För den här proceduren, ange ett belopp lika med ordersaldot som kan visas på sammanfattningssidan för försäljningsorder till vänster om beloppsfältet.</span><span class="sxs-lookup"><span data-stu-id="3d846-129">For this procedure, enter an amount equal to the order balance that can be seen in the Sales order summary page to the left of the amount field.</span></span> <span data-ttu-id="3d846-130">Denna åtgärd gör att du slutför ordern som helt betald.</span><span class="sxs-lookup"><span data-stu-id="3d846-130">This action will allow you to complete the order as fully paid.</span></span>  
17. <span data-ttu-id="3d846-131">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="3d846-131">Select **OK**.</span></span>
18. <span data-ttu-id="3d846-132">Välj **skicka**.</span><span class="sxs-lookup"><span data-stu-id="3d846-132">Select **Submit**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="3d846-133">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="3d846-133">Additional resources</span></span>

[<span data-ttu-id="3d846-134">Anpassa transaktionsmeddelanden via e-post efter leveranssätt</span><span class="sxs-lookup"><span data-stu-id="3d846-134">Customize transactional emails by mode of delivery</span></span>](../customize-email-delivery-mode.md)

[<span data-ttu-id="3d846-135">Ändra leveranssätt i kassan</span><span class="sxs-lookup"><span data-stu-id="3d846-135">Change mode of delivery in POS</span></span>](../pos-change-delivery-mode.md)

