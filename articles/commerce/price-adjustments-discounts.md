---
title: Prisjusteringar och rabatter
description: Denna artikel innehåller information om prisjusteringar och rabatter i Dynamics 365 Commerce.
author: scott-tucker
ms.date: 06/11/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RetailParameters, RetailPeriodicDiscount
audience: Application User
ms.reviewer: josaw
ms.custom: 15891
ms.assetid: bab5adf3-ddf0-4c22-a2eb-b4d25b88de99
ms.search.region: global
ms.search.industry: Retail
ms.author: scotttuc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 44c03ae0a04d648e788a72d8f6dcc3671c5736c7
ms.sourcegitcommit: 7c9d6be464db058511df9cb6ba162d21dc0554e8
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/11/2021
ms.locfileid: "6240952"
---
# <a name="price-adjustments-and-discounts"></a><span data-ttu-id="7efd7-103">Prisjusteringar och rabatter</span><span class="sxs-lookup"><span data-stu-id="7efd7-103">Price adjustments and discounts</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="7efd7-104">Denna artikel innehåller information om prisjusteringar och rabatter i Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="7efd7-104">This article provides information about price adjustments and discounts in Dynamics 365 Commerce.</span></span>

<span data-ttu-id="7efd7-105">I Commerce kan du justera priset på produkter och även ställa in rabatter som används på en radartikel eller en transaktion i POS, en försäljningsorder i kundtjänst eller på en beställning online.</span><span class="sxs-lookup"><span data-stu-id="7efd7-105">In Commerce, you can make price adjustments to products, and can also set up discounts that are applied to a line item or a transaction at the point of sale (POS), in a call center sales order, or in an online order.</span></span> <span data-ttu-id="7efd7-106">Både prisjusteringar och rabatter kan länkas till prisgrupper.</span><span class="sxs-lookup"><span data-stu-id="7efd7-106">Both price adjustments and discounts can be linked to price groups.</span></span> <span data-ttu-id="7efd7-107">För både prisjusteringar och rabatter kan du ange ett enskilt datum för startdatum och slutdatum eller en återkommande period, en rabatt kod och eventuella ytterligare attribut.</span><span class="sxs-lookup"><span data-stu-id="7efd7-107">For both price adjustments and discounts, you can specify a single start date and end date or a reoccurring period, a discount code, and a few additional attributes.</span></span> 

<span data-ttu-id="7efd7-108">Prisjusteringar och rabatter kan användas för produkter, varianter eller kategorier.</span><span class="sxs-lookup"><span data-stu-id="7efd7-108">Price adjustments and discounts can be applied to products, variants, or categories.</span></span> <span data-ttu-id="7efd7-109">Om mer än en rabatt gäller för en produkt, kan en kund ta emot antingen en av rabatterna eller en kombinerad rabatt, beroende på konfigurationen av rabatten.</span><span class="sxs-lookup"><span data-stu-id="7efd7-109">If more than one discount applies to a product, a customer might receive either one of the discounts or a combined discount, depending on the configuration of the discount.</span></span> <span data-ttu-id="7efd7-110">Commerce använder automatiskt rabatten eller en kombination av rabatter som ger kunden det bästa priset.</span><span class="sxs-lookup"><span data-stu-id="7efd7-110">Commerce automatically applies the discount or combination of discounts that gives the best price to the customer.</span></span> <span data-ttu-id="7efd7-111">Kontrollera att du bekräftar att prisgruppen tilldelas de korrekta kanalerna, katalogerna, anknytningarna eller bonusprogrammen som du vill att rabatten ska gälla för när du konfigurerar en prisjustering eller rabatt.</span><span class="sxs-lookup"><span data-stu-id="7efd7-111">When you set up a price adjustment or a discount, be sure to confirm that price groups are assigned to the correct channels, catalogs, affiliations, or loyalty programs that you want the discount to apply to.</span></span> <span data-ttu-id="7efd7-112">Om du vill skapa rabatt-ID automatiskt kan du ställa in nummerserier på sidan **Handelsparametrar** innan du definierar en ny prisjustering eller rabatt.</span><span class="sxs-lookup"><span data-stu-id="7efd7-112">Additionally, if you want to automatically generate the discount ID, set up number sequences on the **Commerce parameters** page before you define a new price adjustment or discount.</span></span>

> [!NOTE]
> <span data-ttu-id="7efd7-113">Du kan ta bort en prisjustering eller rabatt.</span><span class="sxs-lookup"><span data-stu-id="7efd7-113">You can delete a price adjustment or a discount.</span></span> <span data-ttu-id="7efd7-114">Statistisk information går dock förlorad.</span><span class="sxs-lookup"><span data-stu-id="7efd7-114">However, statistical information will be lost.</span></span>

## <a name="types-of-discounts"></a><span data-ttu-id="7efd7-115">Typer av rabatter</span><span class="sxs-lookup"><span data-stu-id="7efd7-115">Types of discounts</span></span>

<span data-ttu-id="7efd7-116">Det finns många olika typer av rabatter:</span><span class="sxs-lookup"><span data-stu-id="7efd7-116">There are many types of discounts:</span></span>

- <span data-ttu-id="7efd7-117">**Enkel rabatt** – En procentandel eller ett belopp.</span><span class="sxs-lookup"><span data-stu-id="7efd7-117">**Simple discount** – A single percentage or amount.</span></span>
- <span data-ttu-id="7efd7-118">**Rabatterad kvantitet** – En rabatt som används när två eller fler produkter köps.</span><span class="sxs-lookup"><span data-stu-id="7efd7-118">**Quantity discount** – A discount that is applied when two or more products are purchased.</span></span>
- <span data-ttu-id="7efd7-119">**Mixa-och-matcha-rabatt** – En rabatt som används när en specifik kombination av produkter köps in.</span><span class="sxs-lookup"><span data-stu-id="7efd7-119">**Mix and match discount** – A discount that is applied when a specific combination of products is purchased.</span></span>
- <span data-ttu-id="7efd7-120">**Tröskelrabatt** – En rabatt som används när transaktionens summa är mer än ett angivet belopp.</span><span class="sxs-lookup"><span data-stu-id="7efd7-120">**Threshold discount** – A discount that is applied when the transaction total is more than a specified amount.</span></span>
- <span data-ttu-id="7efd7-121">**Kassabaserad rabatt** – En rabatt som tillämpas när transaktionens totalsumma överstiger ett angivet belopp och ett visst betalsätt (t. ex. kassa, kredit eller betalkort) används för betalning.</span><span class="sxs-lookup"><span data-stu-id="7efd7-121">**Tender-based discount** – A discount that is applied when the transaction total is more than a specified amount and a specific payment type (for example, cash, credit, or debit card) is used for payment.</span></span>
- <span data-ttu-id="7efd7-122">**Leveransrabatt** – En rabatt som tillämpas när transaktionssumman är mer än ett angivet belopp och ett specifikt leveranssätt (t. ex. två dagars leverans nästföljande dag) används på ordern.</span><span class="sxs-lookup"><span data-stu-id="7efd7-122">**Shipping discount** – A discount that is applied when the transaction total is more than a specified amount and a specific mode of delivery (for example, two day shipping or overnight shipping) is used on the order.</span></span>

<span data-ttu-id="7efd7-123">Både prisjusteringar och rabatter kan associeras till prisgrupper.</span><span class="sxs-lookup"><span data-stu-id="7efd7-123">Both price adjustments and discounts can be associated with price groups.</span></span> <span data-ttu-id="7efd7-124">Prisgrupper kan sedan associeras till kanaler, kataloger, anknytningar och bonusprogram.</span><span class="sxs-lookup"><span data-stu-id="7efd7-124">Price groups can then be associated with channels, catalogs, affiliations, and loyalty programs.</span></span>

> [!NOTE]
> <span data-ttu-id="7efd7-125">Mixa och matcha-rabatten och tröskelrabatten har egenskaper som kallas "Räkna icke-rabatterbara produkter" respektive "Räkna icke-rabatterbara produkter mot tröskel".</span><span class="sxs-lookup"><span data-stu-id="7efd7-125">The mix and match discount and the threshold discount have properties named "Count non-discountable products" and "Count non-discountable products towards threshold", respectively.</span></span> <span data-ttu-id="7efd7-126">Om dessa egenskaper är aktiverade kan en artikel som inte berättigar till rabatt ändå hjälpa till att kvalificera en transaktion för rabatten, men den icke-berättigade artikeln får inte rabatten.</span><span class="sxs-lookup"><span data-stu-id="7efd7-126">If these properties are enabled, an item that is not eligible for any discount can still help qualify a transaction for the discount, but the ineligible item will not get the discount.</span></span> 
> 
> <span data-ttu-id="7efd7-127">Om du till exempel skapar en mixa och matcha-rabatt med två rader, A och B, där en kund ska få 10 % rabatt på båda artiklarna, men artikel A har konfigurationen "Förhindra alla rabatter" markerad, skulle detta normalt hindra artikel A från att inkluderas i rabatten.</span><span class="sxs-lookup"><span data-stu-id="7efd7-127">For example, if you create a mix and match discount with two lines, A and B, where a customer should get 10% off on both items, but item A has the configuration "Prevent all discounts" checked, then this would typically stop item A from being included in the discount.</span></span> <span data-ttu-id="7efd7-128">Om egenskapen "Räkna icke-rabatterbara produkter" är aktiverad kan emellertid artikel A användas för att kvalificera sig för mixa och matcha-rabatten, men 10 %-rabatten tillämpas endast på artikel B. Liknande logik gäller för tröskelrabatten.</span><span class="sxs-lookup"><span data-stu-id="7efd7-128">However, if the "Count non-discountable products" property is enabled, then item A can be used to qualify for the mix and match discount, but the 10% discount will only be applied to item B. Similar logic applies to the threshold discount.</span></span> 
>
> <span data-ttu-id="7efd7-129">Egenskapen "Räkna icke-rabatterbara produkter mot tröskel" har emellertid en ytterligare kapacitet när den jämförs med egenskapen "Räkna icke-rabatterbara produkter" för mixa och matcha-rabatterna.</span><span class="sxs-lookup"><span data-stu-id="7efd7-129">However, the property "Count non-discountable products towards threshold" has an additional capability when compared to the "Count non-discountable products" property of the mix and match discounts.</span></span> <span data-ttu-id="7efd7-130">Om tröskelrabatten är aktiverad, och om det finns en artikel som har en befintlig rabatt som hindrar artikeln från att omfattas av andra rabatter, blir priset som betalas för artikeln lika med eller högre än tröskelvärdet, men artikeln får inte ytterligare rabatt.</span><span class="sxs-lookup"><span data-stu-id="7efd7-130">If the threshold discount is enabled, and if there is an item that has an existing discount which would prevent the item from any other discounts, then  the price paid for this item would qualify towards meeting the threshold, but this item will not get the additional discount.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
