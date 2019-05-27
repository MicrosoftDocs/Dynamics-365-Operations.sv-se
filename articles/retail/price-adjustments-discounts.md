---
title: Prisjusteringar och rabatter
description: Denna artikel innehåller information om prisjusteringar och rabatter i Microsoft Dynamics 365 for Retail.
author: scott-tucker
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailParameters, RetailPeriodicDiscount
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 15891
ms.assetid: bab5adf3-ddf0-4c22-a2eb-b4d25b88de99
ms.search.region: global
ms.search.industry: Retail
ms.author: scotttuc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 61ac8e5fbdc4d91bb5bc5372a7fb96633043473a
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/15/2019
ms.locfileid: "1549462"
---
# <a name="price-adjustments-and-discounts"></a><span data-ttu-id="1788a-103">Prisjusteringar och rabatter</span><span class="sxs-lookup"><span data-stu-id="1788a-103">Price adjustments and discounts</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="1788a-104">Denna artikel innehåller information om prisjusteringar och rabatter i Microsoft Dynamics 365 for Retail.</span><span class="sxs-lookup"><span data-stu-id="1788a-104">This article provides information about price adjustments and discounts in Microsoft Dynamics 365 for Retail.</span></span>

<span data-ttu-id="1788a-105">I Dynamics 365 for Retail kan du justera priset på produkter och även ställa in rabatter som används på en radartikel eller en transaktion i kassan, en försäljningsorder i kundtjänst eller på en beställning online.</span><span class="sxs-lookup"><span data-stu-id="1788a-105">In Dynamics 365 for Retail, you can make price adjustments to products, and can also set up discounts that are applied to a line item or a transaction at the point of sale (POS), in a call center sales order, or in an online order.</span></span> <span data-ttu-id="1788a-106">Både prisjusteringar och rabatter kan länkas till prisgrupper.</span><span class="sxs-lookup"><span data-stu-id="1788a-106">Both price adjustments and discounts can be linked to price groups.</span></span> <span data-ttu-id="1788a-107">För både prisjusteringar och rabatter kan du ange ett enskilt datum för startdatum och slutdatum eller en återkommande period, en rabatt kod och eventuella ytterligare attribut.</span><span class="sxs-lookup"><span data-stu-id="1788a-107">For both price adjustments and discounts, you can specify a single start date and end date or a reoccurring period, a discount code, and a few additional attributes.</span></span> <span data-ttu-id="1788a-108">Prisjusteringar och rabatter kan användas för produkter, varianter eller kategorier.</span><span class="sxs-lookup"><span data-stu-id="1788a-108">Price adjustments and discounts can be applied to products, variants, or categories.</span></span> <span data-ttu-id="1788a-109">Om mer än en rabatt gäller för en produkt, kan en kund ta emot antingen en av rabatterna eller en kombinerad rabatt, beroende på konfigurationen av rabatten.</span><span class="sxs-lookup"><span data-stu-id="1788a-109">If more than one discount applies to a product, a customer might receive either one of the discounts or a combined discount, depending on the configuration of the discount.</span></span> <span data-ttu-id="1788a-110">Dynamics 365 for Retail använder automatiskt rabatten eller en kombination av rabatter som ger kunden det bästa priset.</span><span class="sxs-lookup"><span data-stu-id="1788a-110">Dynamics 365 for Retail automatically applies the discount or combination of discounts that gives the best price to the customer.</span></span> <span data-ttu-id="1788a-111">Kontrollera att du bekräftar att prisgruppen tilldelas de korrekta kanalerna, katalogerna, anknytningarna eller bonusprogrammen som du vill att rabatten ska gälla för när du konfigurerar en prisjustering eller rabatt.</span><span class="sxs-lookup"><span data-stu-id="1788a-111">When you set up a price adjustment or a discount, be sure to confirm that price groups are assigned to the correct channels, catalogs, affiliations, or loyalty programs that you want the discount to apply to.</span></span> <span data-ttu-id="1788a-112">Om du vill skapa rabatt-ID automatiskt kan du ställa in nummerserier på sidan **Butiksparametrar** innan du definierar en ny prisjustering eller rabatt.</span><span class="sxs-lookup"><span data-stu-id="1788a-112">Additionally, if you want to automatically generate the discount ID, set up number sequences on the **Retail parameters** page before you define a new price adjustment or discount.</span></span>

> [!NOTE]
> <span data-ttu-id="1788a-113">Du kan ta bort en prisjustering eller rabatt.</span><span class="sxs-lookup"><span data-stu-id="1788a-113">You can delete a price adjustment or a discount.</span></span> <span data-ttu-id="1788a-114">Statistisk information går dock förlorad.</span><span class="sxs-lookup"><span data-stu-id="1788a-114">However, statistical information will be lost.</span></span>

## <a name="types-of-discounts"></a><span data-ttu-id="1788a-115">Typer av rabatter</span><span class="sxs-lookup"><span data-stu-id="1788a-115">Types of discounts</span></span>

<span data-ttu-id="1788a-116">Det finns fyra typer av butiksrabatter:</span><span class="sxs-lookup"><span data-stu-id="1788a-116">There are four types of retail discounts:</span></span>

- <span data-ttu-id="1788a-117">**Enkel rabatt** – En procentandel eller ett belopp.</span><span class="sxs-lookup"><span data-stu-id="1788a-117">**Simple discount** – A single percentage or amount.</span></span>
- <span data-ttu-id="1788a-118">**Rabatterad kvantitet** – En rabatt som används när två eller fler produkter köps.</span><span class="sxs-lookup"><span data-stu-id="1788a-118">**Quantity discount** – A discount that is applied when two or more products are purchased.</span></span>
- <span data-ttu-id="1788a-119">**Mixa-och-matcha-rabatt** – En rabatt som används när en specifik kombination av produkter köps in.</span><span class="sxs-lookup"><span data-stu-id="1788a-119">**Mix and match discount** – A discount that is applied when a specific combination of products is purchased.</span></span>
- <span data-ttu-id="1788a-120">**Tröskelrabatt** – En rabatt som används när transaktionens summa är mer än ett angivet belopp.</span><span class="sxs-lookup"><span data-stu-id="1788a-120">**Threshold discount** – A discount that is applied when the transaction total is more than a specified amount.</span></span>

<span data-ttu-id="1788a-121">Både prisjusteringar och rabatter kan associeras till prisgrupper.</span><span class="sxs-lookup"><span data-stu-id="1788a-121">Both price adjustments and discounts can be associated with price groups.</span></span> <span data-ttu-id="1788a-122">Prisgrupper kan sedan associeras till kanaler, kataloger, anknytningar och bonusprogram.</span><span class="sxs-lookup"><span data-stu-id="1788a-122">Price groups can then be associated with channels, catalogs, affiliations, and loyalty programs.</span></span>
