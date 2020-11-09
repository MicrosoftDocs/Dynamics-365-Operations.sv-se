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
ms.openlocfilehash: dce2fdd9d91c2bd867f0455573733aefb0796fa7
ms.sourcegitcommit: 776758a0ff95c3c7398986095104d1d2b9814514
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/24/2020
ms.locfileid: "4107362"
---
# <a name="create-call-center-orders"></a><span data-ttu-id="538de-103"> Skapa kundtjänstorder</span><span class="sxs-lookup"><span data-stu-id="538de-103">Create call center orders</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="538de-104">Den här proceduren går igenom hur du söker efter en kund, skapar en ny order, söker efter en produkt och tar emot betalningen från kunden.</span><span class="sxs-lookup"><span data-stu-id="538de-104">This procedure walks through looking up a customer, creating a new order, searching for a product, and collecting payment from the customer.</span></span> <span data-ttu-id="538de-105">I den här proceduren används demonstrationsdataföretaget USRT och är avsedd för Försäljningsorderansvarig.</span><span class="sxs-lookup"><span data-stu-id="538de-105">This procedure uses demo data company USRT and is intended for the Sales Order Clerk.</span></span> <span data-ttu-id="538de-106">Förutsättningar: Användaren som utför proceduren ställs in som kundtjänstanvändare och halvårsutgåvan av Fabrikam-katalogen publiceras med minst en källkod på den.</span><span class="sxs-lookup"><span data-stu-id="538de-106">Pre-requisites:  The user who completes the procedure is set up as a Call center user and the Fabrikam Semi-Annual Catalog is published with at least one Source code on it.</span></span>

1. <span data-ttu-id="538de-107">Gå till **Butik och handel \> Kunder \> Kundtjänst**.</span><span class="sxs-lookup"><span data-stu-id="538de-107">Go to **Retail and Commerce \> Customers \> Customer service**.</span></span>
2. <span data-ttu-id="538de-108">För **Söktext** , ange sökkriterierna för att hitta kunden.</span><span class="sxs-lookup"><span data-stu-id="538de-108">For **SearchText** , enter the search criteria to look up the customer.</span></span>
    * <span data-ttu-id="538de-109">För den här exempelproceduren, skriv ”karen” och tryck på **flik**.</span><span class="sxs-lookup"><span data-stu-id="538de-109">For this example procedure, enter "Karen" and select **Tab**.</span></span>  
3. <span data-ttu-id="538de-110">Välj Sök.</span><span class="sxs-lookup"><span data-stu-id="538de-110">Select Search.</span></span>
    * <span data-ttu-id="538de-111">Eftersom det bara finns en kund med namnet Karen i demodata, kommer resultatet automatiskt markeras.</span><span class="sxs-lookup"><span data-stu-id="538de-111">Since there is only one customer named "Karen" in demo data, the result will be automatically selected.</span></span>  
4. <span data-ttu-id="538de-112">Välj **Ny försäljningsorder**.</span><span class="sxs-lookup"><span data-stu-id="538de-112">Select **New sales order**.</span></span>
5. <span data-ttu-id="538de-113">Expandera eller komprimera avsnittet **Försäljningsorderhuvud**.</span><span class="sxs-lookup"><span data-stu-id="538de-113">Expand or collapse the **Sales order** header section.</span></span>
6. <span data-ttu-id="538de-114">Välj källkoden för katalogen.</span><span class="sxs-lookup"><span data-stu-id="538de-114">Select the source code for the catalog.</span></span>
    * <span data-ttu-id="538de-115">Om det inte finns några aktiva källkoder kan du hoppa över det här steget.</span><span class="sxs-lookup"><span data-stu-id="538de-115">If there are no active source codes you can skip this step.</span></span>  
7. <span data-ttu-id="538de-116">Välj **Markera rad**.</span><span class="sxs-lookup"><span data-stu-id="538de-116">Select **Add line**.</span></span>
8. <span data-ttu-id="538de-117">För **Artikelnummer** ange artikelsöktermen.</span><span class="sxs-lookup"><span data-stu-id="538de-117">For **Item number** , enter the item search term.</span></span>
    * <span data-ttu-id="538de-118">För den här exempelproceduren, ange ett delvis artikelnummer 8111 och tryck på fliken. Denna åtgärd öppnar artikelsökningsfönstret.</span><span class="sxs-lookup"><span data-stu-id="538de-118">For this sample procedure, enter a partial item number of '8111' and press tab. This action will bring up the item search window.</span></span>  
9. <span data-ttu-id="538de-119">Välj produkten att lägga till försäljningsordern.</span><span class="sxs-lookup"><span data-stu-id="538de-119">Select the product to add to the sales order.</span></span>
10. <span data-ttu-id="538de-120">Ange försäljningskvantiteten.</span><span class="sxs-lookup"><span data-stu-id="538de-120">Enter the sales quantity.</span></span>
11. <span data-ttu-id="538de-121">Markera **Skapa**.</span><span class="sxs-lookup"><span data-stu-id="538de-121">Select **Create**.</span></span>
12. <span data-ttu-id="538de-122">Klicka på **Slutför** för att registrera kundbetalningen.</span><span class="sxs-lookup"><span data-stu-id="538de-122">Select **Complete** to capture the customer payment.</span></span>
13. <span data-ttu-id="538de-123">Markera **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="538de-123">Select **Add**.</span></span>
    * <span data-ttu-id="538de-124">Lägg till länk finns på betalningsfliken. Expandera fliken Betalning om den är komprimerad.</span><span class="sxs-lookup"><span data-stu-id="538de-124">The Add link is in the Payments tab. Expand the Payments tab if it is collapsed.</span></span>  
14. <span data-ttu-id="538de-125">Välj betalningsmetod.</span><span class="sxs-lookup"><span data-stu-id="538de-125">Select the payment method.</span></span>
    * <span data-ttu-id="538de-126">Välj betalningsmetoden kontant för den här proceduren.</span><span class="sxs-lookup"><span data-stu-id="538de-126">For this procedure, select the cash payment method.</span></span>  
15. <span data-ttu-id="538de-127">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="538de-127">Close the page.</span></span>
16. <span data-ttu-id="538de-128">Ange belopp.</span><span class="sxs-lookup"><span data-stu-id="538de-128">Enter the amount.</span></span>
    * <span data-ttu-id="538de-129">För den här proceduren, ange ett belopp lika med ordersaldot som kan visas på sammanfattningssidan för försäljningsorder till vänster om beloppsfältet.</span><span class="sxs-lookup"><span data-stu-id="538de-129">For this procedure, enter an amount equal to the order balance that can be seen in the Sales order summary page to the left of the amount field.</span></span> <span data-ttu-id="538de-130">Denna åtgärd gör att du slutför ordern som helt betald.</span><span class="sxs-lookup"><span data-stu-id="538de-130">This action will allow you to complete the order as fully paid.</span></span>  
17. <span data-ttu-id="538de-131">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="538de-131">Select **OK**.</span></span>
18. <span data-ttu-id="538de-132">Välj **skicka**.</span><span class="sxs-lookup"><span data-stu-id="538de-132">Select **Submit**.</span></span>

