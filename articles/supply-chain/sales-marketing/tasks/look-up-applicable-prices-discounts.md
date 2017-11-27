--- 
title: "Slå upp tillämpliga priser och rabatter"
description: "I den här proceduren visas hur du hittar pris och/eller rabatt för en produkt som för närvarande är giltig för en viss kund, utan att skapa en försäljningsorder."
author: omulvad
manager: AnnBe
ms.date: 11/10/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 809a1466b0f4674f503bc654175d8f94b37a6508
ms.openlocfilehash: 7ef63151f352b3664bccd7a59e7417dfddc7470b
ms.contentlocale: sv-se
ms.lasthandoff: 11/02/2017

---
# <a name="look-up-applicable-prices-and-discounts"></a><span data-ttu-id="2b79d-103">Slå upp tillämpliga priser och rabatter</span><span class="sxs-lookup"><span data-stu-id="2b79d-103">Look up applicable prices and discounts</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="2b79d-104">I den här proceduren visas hur du hittar pris och/eller rabatt för en produkt som för närvarande är giltig för en viss kund, utan att skapa en försäljningsorder.</span><span class="sxs-lookup"><span data-stu-id="2b79d-104">This procedure shows how to find the price and/or discount for a product which is currently valid for a specific customer, without creating a sales order.</span></span> <span data-ttu-id="2b79d-105">I proceduren går vi igenom ett visst exempel och du måste följa exemplet med hjälp av USMF-demonstrationsföretaget för att välja de nödvändiga värdena.</span><span class="sxs-lookup"><span data-stu-id="2b79d-105">The procedure walks through a specific example, and you need follow the example using the USMF demo company in order to select the necessary values.</span></span>


## <a name="find-the-applicable-price"></a><span data-ttu-id="2b79d-106">Sök efter det tillämpliga priset</span><span class="sxs-lookup"><span data-stu-id="2b79d-106">Find the applicable price</span></span>
1. <span data-ttu-id="2b79d-107">Gå till försäljning och marknadsföring > Priser och rabatter > Sök priser.</span><span class="sxs-lookup"><span data-stu-id="2b79d-107">Go to Sales and marketing > Prices and discounts > Find prices.</span></span>
2. <span data-ttu-id="2b79d-108">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Kundkonto.</span><span class="sxs-lookup"><span data-stu-id="2b79d-108">In the Customer account field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="2b79d-109">Hitta och markera kunden US-001 i listan.</span><span class="sxs-lookup"><span data-stu-id="2b79d-109">In the list, find and select customer US-001.</span></span>
4. <span data-ttu-id="2b79d-110">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="2b79d-110">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="2b79d-111">Skriv "T0004" i fältet Artikelnummer.</span><span class="sxs-lookup"><span data-stu-id="2b79d-111">In the Item number field, type 'T0004'.</span></span>
    * <span data-ttu-id="2b79d-112">Som standard är fältet Kvantitet inställt på värdet 1.</span><span class="sxs-lookup"><span data-stu-id="2b79d-112">By default, the Quantity field is set to 1.</span></span> <span data-ttu-id="2b79d-113">Men om du vet storleken av den order som kunden avser att placera för produkten i fråga och ange sedan värdet i stället.</span><span class="sxs-lookup"><span data-stu-id="2b79d-113">However, if you know the size of the order that the customer intends to place for the product in question, then enter this value instead.</span></span> <span data-ttu-id="2b79d-114">Den här informationen är bara relevant om handelsavtal med kunden ha kvantitet avbrott, dvs. produktens pris beror på den minsta kvantitet som kunden köpt.</span><span class="sxs-lookup"><span data-stu-id="2b79d-114">This information is relevant if the trade agreements with the customer have quantity breaks, that is, the product's price depends on the minimum quantity purchased.</span></span>  
6. <span data-ttu-id="2b79d-115">Ange ett datum för när kunden beräknar att göra en beställning i fältet Datum.</span><span class="sxs-lookup"><span data-stu-id="2b79d-115">In the Date field, enter a date for when the customer expects to place an order.</span></span> 
    * <span data-ttu-id="2b79d-116">Datumet kan vara dagens datum eller vilket datum som helst i framtiden.</span><span class="sxs-lookup"><span data-stu-id="2b79d-116">The date can be today's date or any date in the future.</span></span>  
    * <span data-ttu-id="2b79d-117">Systemet returnerar nu priset som gäller för den valda produkten när den köps av det valda kunden på det valda datumet med en angiven kvantitet.</span><span class="sxs-lookup"><span data-stu-id="2b79d-117">The system now returns the price that is valid for the selected product when bought by the selected customer on the selected date with a specified quantity.</span></span> <span data-ttu-id="2b79d-118">I detta exempel, om kunden oss-001 köpte 1 enhet av produkten T0004 idag, de skulle debiteras 350 CAD per enhet.</span><span class="sxs-lookup"><span data-stu-id="2b79d-118">In this example, if the customer US-001 bought 1 unit of product T0004 today, they would be charged 350 CAD a unit.</span></span> <span data-ttu-id="2b79d-119">Detta pris kommer från en befintlig och aktiv handel avtalet med kunden.</span><span class="sxs-lookup"><span data-stu-id="2b79d-119">This price comes from an existing and active trade agreement with the customer.</span></span>      <span data-ttu-id="2b79d-120">Andra fält på sidan innehåller mer information om produktpriset och produktkostnaden (om det har ställts in på produktmallen) och uppskattad vinst.</span><span class="sxs-lookup"><span data-stu-id="2b79d-120">Other fields on the page provide more details about the product price and product cost (if set up on the product master), and calculated profitability.</span></span>  
    * <span data-ttu-id="2b79d-121">Om alternativet Visa relaterade produktvarianter har valts innebär det att det finns ytterligare handelsavtal för produktvarianterna.</span><span class="sxs-lookup"><span data-stu-id="2b79d-121">If the Show related product variants option is selected, it means that there are additional trade agreements for product's variants.</span></span>  
7. <span data-ttu-id="2b79d-122">Klicka på kryssrutan Visa relaterade produktvarianter.</span><span class="sxs-lookup"><span data-stu-id="2b79d-122">Click the Show related product variants checkbox.</span></span>
    * <span data-ttu-id="2b79d-123">En lista med produktvarianterna visas, med information om dimensionerna för dessa.</span><span class="sxs-lookup"><span data-stu-id="2b79d-123">A list of the product variants is shown, with information about their dimensions.</span></span>  
8. <span data-ttu-id="2b79d-124">Markera raden som representerar färgen Vit i listan.</span><span class="sxs-lookup"><span data-stu-id="2b79d-124">In the list, mark the line representing color White.</span></span>
    * <span data-ttu-id="2b79d-125">Observera att produktpriset nu skiljer sig från det som tidigare visades när det inte har registrerats per dimension.</span><span class="sxs-lookup"><span data-stu-id="2b79d-125">Notice, that the product price is now different from the one displayed previously when it was not specified per dimension.</span></span>  
9. <span data-ttu-id="2b79d-126">Klicka på Visa försäljningspriser.</span><span class="sxs-lookup"><span data-stu-id="2b79d-126">Click View sales prices.</span></span>
    * <span data-ttu-id="2b79d-127">På sidan Pris (försäljning) visas alla handelsavtal som gäller för produkten, inklusive varianterna för denna.</span><span class="sxs-lookup"><span data-stu-id="2b79d-127">The Price (sales) page displays all the trade agreements applicable to the product, including its variants.</span></span>  
10. <span data-ttu-id="2b79d-128">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="2b79d-128">Close the page.</span></span>

## <a name="find-the-applicable-discount"></a><span data-ttu-id="2b79d-129">Sök efter den tillämpliga rabatten</span><span class="sxs-lookup"><span data-stu-id="2b79d-129">Find the applicable discount</span></span>
    * <span data-ttu-id="2b79d-130">Kontrollera att kundens konto innehåller kundnummer US-001 </span><span class="sxs-lookup"><span data-stu-id="2b79d-130">Make sure the Customer account field contains customer number US-001</span></span>   
1. <span data-ttu-id="2b79d-131">Skriv "T0012" i fältet Artikelnummer.</span><span class="sxs-lookup"><span data-stu-id="2b79d-131">In the Item number field, type 'T0012'.</span></span>
    * <span data-ttu-id="2b79d-132">Kontrollera att fältet Kvantitet har värdet 1.</span><span class="sxs-lookup"><span data-stu-id="2b79d-132">Make sure the Quantity field is set to 1.</span></span>  
    * <span data-ttu-id="2b79d-133">Följande prissättningsdetaljer som visas för produkten T0012, kommer från ett eller flera handelsavtal: Enhetspriset är 10,00 SEK och rabattprocenten är 5.</span><span class="sxs-lookup"><span data-stu-id="2b79d-133">The following pricing details shown for product T0012 come from one or more trade agreements: The unit price is 1,000 CAD and the discount percentage is 5.</span></span>  
2. <span data-ttu-id="2b79d-134">Ställ in kvantiteten på 20.</span><span class="sxs-lookup"><span data-stu-id="2b79d-134">Set Quantity to '20'.</span></span>
    * <span data-ttu-id="2b79d-135">Det ökade orderkvantiteten gör att radrabatten som ska erbjudas kunden ändras från 5 till 7 procent.</span><span class="sxs-lookup"><span data-stu-id="2b79d-135">The increased order quantity causes the line discount that will be offered to the customer to change from 5 to 7 percent.</span></span>  
    * <span data-ttu-id="2b79d-136">Det totala nettobeloppet beräknas baserat på enhetspriset, rabatten och den totala kvantiteten.</span><span class="sxs-lookup"><span data-stu-id="2b79d-136">The Net amount is calculated based on the unit price, discount and the total quantity.</span></span>  
3. <span data-ttu-id="2b79d-137">Klicka på Visa radrabatt.</span><span class="sxs-lookup"><span data-stu-id="2b79d-137">Click View line discount.</span></span>
    * <span data-ttu-id="2b79d-138">Det finns två radrabattavtal för produkten T0012 som anger en rabatt på 5 procent för en orderradskvantitet från mellan 1 till 10 och 7 procents rabatt för orderkvantiteter över 10.</span><span class="sxs-lookup"><span data-stu-id="2b79d-138">There are two line discount agreements for product T0012, specifying a 5 percent discount for an order line quantity from 1 to 10, and 7 percent discount for order quantities above 10.</span></span> <span data-ttu-id="2b79d-139">Observera att rabatter gäller för en grupp produkter, i det här exemplet gruppkod 01, som produkten T0012 tillhör.</span><span class="sxs-lookup"><span data-stu-id="2b79d-139">Note that the discounts are applied to a group of products, in this example, Group code 01, of which product T0012 is a member.</span></span>  
4. <span data-ttu-id="2b79d-140">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="2b79d-140">Close the page.</span></span>


