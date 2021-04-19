---
title: Prisjusteringar och rabatter
description: Denna artikel innehåller information om prisjusteringar och rabatter i Dynamics 365 Commerce.
author: scott-tucker
ms.date: 11/16/2020
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
ms.openlocfilehash: 2d3e8025c5ab28296713634094694156f9addf62
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5802801"
---
# <a name="price-adjustments-and-discounts"></a><span data-ttu-id="0b380-103">Prisjusteringar och rabatter</span><span class="sxs-lookup"><span data-stu-id="0b380-103">Price adjustments and discounts</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="0b380-104">Denna artikel innehåller information om prisjusteringar och rabatter i Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="0b380-104">This article provides information about price adjustments and discounts in Dynamics 365 Commerce.</span></span>

<span data-ttu-id="0b380-105">I Commerce kan du justera priset på produkter och även ställa in rabatter som används på en radartikel eller en transaktion i POS, en försäljningsorder i kundtjänst eller på en beställning online.</span><span class="sxs-lookup"><span data-stu-id="0b380-105">In Commerce, you can make price adjustments to products, and can also set up discounts that are applied to a line item or a transaction at the point of sale (POS), in a call center sales order, or in an online order.</span></span> <span data-ttu-id="0b380-106">Både prisjusteringar och rabatter kan länkas till prisgrupper.</span><span class="sxs-lookup"><span data-stu-id="0b380-106">Both price adjustments and discounts can be linked to price groups.</span></span> <span data-ttu-id="0b380-107">För både prisjusteringar och rabatter kan du ange ett enskilt datum för startdatum och slutdatum eller en återkommande period, en rabatt kod och eventuella ytterligare attribut.</span><span class="sxs-lookup"><span data-stu-id="0b380-107">For both price adjustments and discounts, you can specify a single start date and end date or a reoccurring period, a discount code, and a few additional attributes.</span></span> 

<span data-ttu-id="0b380-108">Prisjusteringar och rabatter kan användas för produkter, varianter eller kategorier.</span><span class="sxs-lookup"><span data-stu-id="0b380-108">Price adjustments and discounts can be applied to products, variants, or categories.</span></span> <span data-ttu-id="0b380-109">Om mer än en rabatt gäller för en produkt, kan en kund ta emot antingen en av rabatterna eller en kombinerad rabatt, beroende på konfigurationen av rabatten.</span><span class="sxs-lookup"><span data-stu-id="0b380-109">If more than one discount applies to a product, a customer might receive either one of the discounts or a combined discount, depending on the configuration of the discount.</span></span> <span data-ttu-id="0b380-110">Commerce använder automatiskt rabatten eller en kombination av rabatter som ger kunden det bästa priset.</span><span class="sxs-lookup"><span data-stu-id="0b380-110">Commerce automatically applies the discount or combination of discounts that gives the best price to the customer.</span></span> <span data-ttu-id="0b380-111">Kontrollera att du bekräftar att prisgruppen tilldelas de korrekta kanalerna, katalogerna, anknytningarna eller bonusprogrammen som du vill att rabatten ska gälla för när du konfigurerar en prisjustering eller rabatt.</span><span class="sxs-lookup"><span data-stu-id="0b380-111">When you set up a price adjustment or a discount, be sure to confirm that price groups are assigned to the correct channels, catalogs, affiliations, or loyalty programs that you want the discount to apply to.</span></span> <span data-ttu-id="0b380-112">Om du vill skapa rabatt-ID automatiskt kan du ställa in nummerserier på sidan **Handelsparametrar** innan du definierar en ny prisjustering eller rabatt.</span><span class="sxs-lookup"><span data-stu-id="0b380-112">Additionally, if you want to automatically generate the discount ID, set up number sequences on the **Commerce parameters** page before you define a new price adjustment or discount.</span></span>

> [!NOTE]
> <span data-ttu-id="0b380-113">Du kan ta bort en prisjustering eller rabatt.</span><span class="sxs-lookup"><span data-stu-id="0b380-113">You can delete a price adjustment or a discount.</span></span> <span data-ttu-id="0b380-114">Statistisk information går dock förlorad.</span><span class="sxs-lookup"><span data-stu-id="0b380-114">However, statistical information will be lost.</span></span>

## <a name="types-of-discounts"></a><span data-ttu-id="0b380-115">Typer av rabatter</span><span class="sxs-lookup"><span data-stu-id="0b380-115">Types of discounts</span></span>

<span data-ttu-id="0b380-116">Det finns många olika typer av rabatter:</span><span class="sxs-lookup"><span data-stu-id="0b380-116">There are many types of discounts:</span></span>

- <span data-ttu-id="0b380-117">**Enkel rabatt** – En procentandel eller ett belopp.</span><span class="sxs-lookup"><span data-stu-id="0b380-117">**Simple discount** – A single percentage or amount.</span></span>
- <span data-ttu-id="0b380-118">**Rabatterad kvantitet** – En rabatt som används när två eller fler produkter köps.</span><span class="sxs-lookup"><span data-stu-id="0b380-118">**Quantity discount** – A discount that is applied when two or more products are purchased.</span></span>
- <span data-ttu-id="0b380-119">**Mixa-och-matcha-rabatt** – En rabatt som används när en specifik kombination av produkter köps in.</span><span class="sxs-lookup"><span data-stu-id="0b380-119">**Mix and match discount** – A discount that is applied when a specific combination of products is purchased.</span></span>
- <span data-ttu-id="0b380-120">**Tröskelrabatt** – En rabatt som används när transaktionens summa är mer än ett angivet belopp.</span><span class="sxs-lookup"><span data-stu-id="0b380-120">**Threshold discount** – A discount that is applied when the transaction total is more than a specified amount.</span></span>
- <span data-ttu-id="0b380-121">**Kassabaserad rabatt** – En rabatt som tillämpas när transaktionens totalsumma överstiger ett angivet belopp och ett visst betalsätt (t. ex. kassa, kredit eller betalkort) används för betalning.</span><span class="sxs-lookup"><span data-stu-id="0b380-121">**Tender-based discount** – A discount that is applied when the transaction total is more than a specified amount and a specific payment type (for example, cash, credit, or debit card) is used for payment.</span></span>
- <span data-ttu-id="0b380-122">**Leveransrabatt** – En rabatt som tillämpas när transaktionssumman är mer än ett angivet belopp och ett specifikt leveranssätt (t. ex. två dagars leverans nästföljande dag) används på ordern.</span><span class="sxs-lookup"><span data-stu-id="0b380-122">**Shipping discount** – A discount that is applied when the transaction total is more than a specified amount and a specific mode of delivery (for example, two day shipping or overnight shipping) is used on the order.</span></span>

<span data-ttu-id="0b380-123">Både prisjusteringar och rabatter kan associeras till prisgrupper.</span><span class="sxs-lookup"><span data-stu-id="0b380-123">Both price adjustments and discounts can be associated with price groups.</span></span> <span data-ttu-id="0b380-124">Prisgrupper kan sedan associeras till kanaler, kataloger, anknytningar och bonusprogram.</span><span class="sxs-lookup"><span data-stu-id="0b380-124">Price groups can then be associated with channels, catalogs, affiliations, and loyalty programs.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]