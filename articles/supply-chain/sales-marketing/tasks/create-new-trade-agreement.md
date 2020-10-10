---
title: Skapa ett nytt handelsavtal
description: I den här proceduren visas hur du skapar ett handelsavtal där du registrerar ett nytt produktförsäljningspris som du har avtalat med en viss kund.
author: omulvad
manager: tfehr
ms.date: 06/25/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TradeNonStockedConversion, TradeNonStockedConversionChangeWizard, TradeNonStockedConversionCheckWorksheet, TradeNonStockedConversionWizard, TradeNonStockedRegister
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Operations
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c1e1b48531e7ef7d55774936cb71130d048cdab7
ms.sourcegitcommit: 54da65a7da0efd4f0d9760c5b14ff785b28751c4
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/22/2020
ms.locfileid: "3830475"
---
# <a name="create-a-new-trade-agreement"></a><span data-ttu-id="f58c1-103">Skapa ett nytt handelsavtal</span><span class="sxs-lookup"><span data-stu-id="f58c1-103">Create a new trade agreement</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="f58c1-104">I den här proceduren visas hur du skapar ett handelsavtal där du registrerar ett nytt produktförsäljningspris som du har avtalat med en viss kund.</span><span class="sxs-lookup"><span data-stu-id="f58c1-104">This procedure shows you how to create a trade agreement where you register a new product sales price that you've agreed with a specific customer.</span></span> <span data-ttu-id="f58c1-105">Du kan köra den här proceduren i demonstrationsföretaget USMF eller på dina egna data.</span><span class="sxs-lookup"><span data-stu-id="f58c1-105">You can run this procedure in demo data company USMF or on your own data.</span></span> <span data-ttu-id="f58c1-106">Om du använder dina egna data måste du se till att det finns ett namn på handelsavtalsjournalen där standardrelationen har angetts till "Pris (försäljning)" innan du startar den här guiden.</span><span class="sxs-lookup"><span data-stu-id="f58c1-106">If you're using your own data, before you start this guide you need to make sure that a Trade agreement journal name exists where the Default relation is set to "Price (sales)".</span></span>


## <a name="create-and-post-a-new-trade-agreement-journal"></a><span data-ttu-id="f58c1-107">Skapa och bokför en ny handelsavtalsjournal.</span><span class="sxs-lookup"><span data-stu-id="f58c1-107">Create and post a new trade agreement journal</span></span>
1. <span data-ttu-id="f58c1-108">Gå till **Navigeringsrutan > Moduler > Försäljning och marknadsföring > Priser och rabatter > Handelsavtalsjournaler**.</span><span class="sxs-lookup"><span data-stu-id="f58c1-108">Go to **Navigation pane > Modules > Sales and marketing > Prices and discounts > Trade agreement journals**.</span></span>
2. <span data-ttu-id="f58c1-109">Klicka på **Ny**.</span><span class="sxs-lookup"><span data-stu-id="f58c1-109">Click **New**.</span></span>
3. <span data-ttu-id="f58c1-110">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet **Namn**.</span><span class="sxs-lookup"><span data-stu-id="f58c1-110">In the **Name** field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="f58c1-111">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="f58c1-111">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="f58c1-112">Klicka på **Rader** i **åtgärdsfönstret**.</span><span class="sxs-lookup"><span data-stu-id="f58c1-112">On **Action Pane**, click **Lines**.</span></span>
6. <span data-ttu-id="f58c1-113">I fältet **Kontokod**, välj Tabell.</span><span class="sxs-lookup"><span data-stu-id="f58c1-113">In the **Account code** field, select 'Table'.</span></span>
    
    <span data-ttu-id="f58c1-114">I det här exemplet uppdaterar du priset för en viss kund, vilket innebär att du måste välja Tabell.</span><span class="sxs-lookup"><span data-stu-id="f58c1-114">In this example, you're updating the price for a specific customer, which means you need to choose Table.</span></span> <span data-ttu-id="f58c1-115">Om du har uppdaterat produktens listpris, du vill markera alla, så att det nya priset är giltigt för alla kunder.</span><span class="sxs-lookup"><span data-stu-id="f58c1-115">If you were updating the product's list price, you would select 'All', so that the new price is valid for all customers.</span></span> <span data-ttu-id="f58c1-116">Om du differentiera priser mellan olika kundsegment, då skulle du välja grupp.</span><span class="sxs-lookup"><span data-stu-id="f58c1-116">If you were differentiating prices among different customer segments, then you would select Group.</span></span> <span data-ttu-id="f58c1-117">Du måste ha ställt in Kundprisgrupper för att välja Grupp.</span><span class="sxs-lookup"><span data-stu-id="f58c1-117">To select Group, you must have set up Customer price groups.</span></span>  

7. <span data-ttu-id="f58c1-118">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet **Kontomarkering**.</span><span class="sxs-lookup"><span data-stu-id="f58c1-118">In the **Account selection** field, click the drop-down button to open the lookup.</span></span>
8. <span data-ttu-id="f58c1-119">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="f58c1-119">In the list, find and select the desired record.</span></span>
9. <span data-ttu-id="f58c1-120">Fältet **Artikelkod**, väljTabell.</span><span class="sxs-lookup"><span data-stu-id="f58c1-120">In the **Item code** field, select 'Table'.</span></span>
    
    <span data-ttu-id="f58c1-121">När du registrerar ett handelsavtal av typen "Pris (försäljning), måste du först markera "Tabell" i fältet **artikelkod**.</span><span class="sxs-lookup"><span data-stu-id="f58c1-121">When you are entering a trade agreement of type 'Price (sales)', you must only select 'Table' in the **Item code** field.</span></span> <span data-ttu-id="f58c1-122">Detta beror på att ett pris är ett absolut värde och kan inte vara samma för alla produkter eller en grupp av produkter.</span><span class="sxs-lookup"><span data-stu-id="f58c1-122">This is because a price is an absolute value and cannot be same for all products or a group of products.</span></span>
    
10. <span data-ttu-id="f58c1-123">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet **Artikelrelation**.</span><span class="sxs-lookup"><span data-stu-id="f58c1-123">In the **Item relation** field, click the drop-down button to open the lookup.</span></span>
11. <span data-ttu-id="f58c1-124">I listan väljer du vilken produkt som du vill inkludera i avtalet.</span><span class="sxs-lookup"><span data-stu-id="f58c1-124">In the list, select the product you want to include in the agreement.</span></span> <span data-ttu-id="f58c1-125">Gör en notering för vilken produkt du har valt.</span><span class="sxs-lookup"><span data-stu-id="f58c1-125">Make a note of which product you've selected.</span></span>  
12. <span data-ttu-id="f58c1-126">I fältet **Från**, ange en minsta kvantitet.</span><span class="sxs-lookup"><span data-stu-id="f58c1-126">In the **From** field, enter a minimum quantity.</span></span>
    - <span data-ttu-id="f58c1-127">Om kunden har en minsta kvantitet innan de kan kvalificera sig för det nya priset, alltså du nöd till preciserar kvantiteten här.</span><span class="sxs-lookup"><span data-stu-id="f58c1-127">If the customer has to order a minimum quantity before they can qualify for the new price, then you need to specify that quantity here.</span></span>  
    - <span data-ttu-id="f58c1-128">Ange ett värde i fältet **Till** för att ange den maximala kvantitet som avtalet är priset inte vara giltig.</span><span class="sxs-lookup"><span data-stu-id="f58c1-128">Enter a value in the **To** field to specify the maximum quantity above which the agreement's price will not be valid.</span></span> <span data-ttu-id="f58c1-129">Om du erbjuder priser och rabatter baserade på flera kvantitetssteg, ange sedan varje kvantitet fäste som ett par minimala och maximala kvantiteten i **från** och **till** respektive fält.</span><span class="sxs-lookup"><span data-stu-id="f58c1-129">If you offer prices and discounts based on multiple quantity breaks, then specify each quantity bracket as a pair of minimum and maximum quantity in the **From** and **To** fields respectively.</span></span>
13. <span data-ttu-id="f58c1-130">I **Belopp i valutafältet**, ange ett pris.</span><span class="sxs-lookup"><span data-stu-id="f58c1-130">In the **Amount in currency field**, enter a price.</span></span>
14. <span data-ttu-id="f58c1-131">Under avsnittet **Detaljer**, i fältet **Fråndatum**, anger du ett datum från vilket detta avtal skall vara giltigt.</span><span class="sxs-lookup"><span data-stu-id="f58c1-131">Under the **Details** section, in the **From date** field, enter a date from which this agreement will be valid.</span></span>
15. <span data-ttu-id="f58c1-132">Klicka på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="f58c1-132">Click **Save**.</span></span>
16. <span data-ttu-id="f58c1-133">Klicka på **Validera.**</span><span class="sxs-lookup"><span data-stu-id="f58c1-133">Click **Validate**.</span></span>
17. <span data-ttu-id="f58c1-134">Klickar på **Validera markerade rader**.</span><span class="sxs-lookup"><span data-stu-id="f58c1-134">Click **Validate selected lines**.</span></span>
18. <span data-ttu-id="f58c1-135">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="f58c1-135">Click **OK**.</span></span>
19. <span data-ttu-id="f58c1-136">Klicka på **Bokför**.</span><span class="sxs-lookup"><span data-stu-id="f58c1-136">Click **Post**.</span></span>
20. <span data-ttu-id="f58c1-137">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="f58c1-137">Click **OK**.</span></span>

## <a name="view-trade-agreements-for-a-product"></a><span data-ttu-id="f58c1-138">Visa handelsavtal för en produkt.</span><span class="sxs-lookup"><span data-stu-id="f58c1-138">View trade agreements for a product</span></span>
1. <span data-ttu-id="f58c1-139">Gå till **Navigeringsfönster > Moduler > Produktinformationshantering > Produkter > Frisläppta produkter**.</span><span class="sxs-lookup"><span data-stu-id="f58c1-139">Go to **Navigation pane > Modules > Product information management > Products > Released products**.</span></span>
2. <span data-ttu-id="f58c1-140">Hitta och markera den produkt vars pris du precis har uppdaterat.</span><span class="sxs-lookup"><span data-stu-id="f58c1-140">In the list, find and select the product whose price you have just updated.</span></span>
3. <span data-ttu-id="f58c1-141">Klicka på **Sälj** i **åtgärdsfönstret**.</span><span class="sxs-lookup"><span data-stu-id="f58c1-141">On the **Action Pane**, click **Sell**.</span></span>
4. <span data-ttu-id="f58c1-142">Klicka på **Visa handelsavtal**.</span><span class="sxs-lookup"><span data-stu-id="f58c1-142">Click **View trade agreements**.</span></span>
    
    <span data-ttu-id="f58c1-143">Granska informationen i prishandelsavtalet som du precis har skapat.</span><span class="sxs-lookup"><span data-stu-id="f58c1-143">Review the details of the price trade agreement you have just created.</span></span>    

5. <span data-ttu-id="f58c1-144">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="f58c1-144">Close the page.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="f58c1-145">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="f58c1-145">Additional resources</span></span>
### <a name="community-blogs"></a><span data-ttu-id="f58c1-146">Bloggar</span><span class="sxs-lookup"><span data-stu-id="f58c1-146">Community blogs</span></span>
- [<span data-ttu-id="f58c1-147">Försäljningspriser i Dynamics 365 for Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="f58c1-147">Sales prices in Dynamics 365 for Finance and Operations</span></span>](https://financefunction.tech/2018/11/14/sales-prices-in-dynamics-365-for-finance-and-operations/#sales_price_in_trade_agreements)
