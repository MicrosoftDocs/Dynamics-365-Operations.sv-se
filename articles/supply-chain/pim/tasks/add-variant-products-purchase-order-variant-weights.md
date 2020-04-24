---
title: Lägg till variantprodukter i inköpsorder med hjälp av variantvikter
description: Den här proceduren går igenom stegen vid användning av variantvikt för att automatiskt fylla i inköpsorderrader för varje variant av en produkt.
author: ShylaThompson
manager: tfehr
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0199f4b05c23eec5c03c770c37111a6ee6d13efe
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/02/2020
ms.locfileid: "3208396"
---
# <a name="add-variant-products-to-purchase-orders-using-variant-weights"></a><span data-ttu-id="fb0a6-103">Lägg till variantprodukter i inköpsorder med hjälp av variantvikter</span><span class="sxs-lookup"><span data-stu-id="fb0a6-103">Add variant products to purchase orders using variant weights</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="fb0a6-104">Den här proceduren går igenom stegen vid användning av variantvikt för att automatiskt fylla i inköpsorderrader för varje variant av en produkt.</span><span class="sxs-lookup"><span data-stu-id="fb0a6-104">This procedure walks through the steps for using variant weights to auto populate purchase order lines for each variant of a product.</span></span> <span data-ttu-id="fb0a6-105">När du väljer kvantiteten av produkten som du vill köpa, inköpsorderrader skapas för alla varianter av produkten med föreslagna kvantiteter som baseras på de vikter som konfigureras på produktvarianterna.</span><span class="sxs-lookup"><span data-stu-id="fb0a6-105">When you select the quantity of the product you want to purchase, purchase order lines are created for all the variants of the product with suggested quantities based on the weights configured on the product variants.</span></span> <span data-ttu-id="fb0a6-106">Den här proceduren inkluderar inte steg för att konfigurera viktvärden på produktdimensioner och produktvarianter.</span><span class="sxs-lookup"><span data-stu-id="fb0a6-106">This procedure doesn't include steps to configure weight values on product dimensions and product variants.</span></span> <span data-ttu-id="fb0a6-107">I proceduren används demonstrationsföretaget USRT.</span><span class="sxs-lookup"><span data-stu-id="fb0a6-107">This procedure uses the USRT company in demo data.</span></span>

1. <span data-ttu-id="fb0a6-108">Gå till leverantörsskulder > inköpsorder > Alla inköpsorder.</span><span class="sxs-lookup"><span data-stu-id="fb0a6-108">Go to Accounts payable > Purchase orders > All purchase orders.</span></span>
2. <span data-ttu-id="fb0a6-109">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="fb0a6-109">Click New.</span></span>
3. <span data-ttu-id="fb0a6-110">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Leverantörskonto.</span><span class="sxs-lookup"><span data-stu-id="fb0a6-110">In the Vendor account field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="fb0a6-111">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="fb0a6-111">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="fb0a6-112">Växla utökningen av avsnittet Allmänt.</span><span class="sxs-lookup"><span data-stu-id="fb0a6-112">Toggle the expansion of the General section.</span></span>
6. <span data-ttu-id="fb0a6-113">Öppna sökningen genom att klicka på listruteknappen i fältet Plats.</span><span class="sxs-lookup"><span data-stu-id="fb0a6-113">In the Site field, click the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="fb0a6-114">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="fb0a6-114">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="fb0a6-115">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Lagerställe.</span><span class="sxs-lookup"><span data-stu-id="fb0a6-115">In the Warehouse field, click the drop-down button to open the lookup.</span></span>
9. <span data-ttu-id="fb0a6-116">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="fb0a6-116">In the list, find and select the desired record.</span></span>
10. <span data-ttu-id="fb0a6-117">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="fb0a6-117">In the list, click the link in the selected row.</span></span>
11. <span data-ttu-id="fb0a6-118">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="fb0a6-118">Click OK.</span></span>
12. <span data-ttu-id="fb0a6-119">Växla expanderingen av avsnittet Raddetaljer.</span><span class="sxs-lookup"><span data-stu-id="fb0a6-119">Toggle the expansion of the Line details section.</span></span>
13. <span data-ttu-id="fb0a6-120">Klicka på fliken Varianter.</span><span class="sxs-lookup"><span data-stu-id="fb0a6-120">Click the Variants tab.</span></span>
14. <span data-ttu-id="fb0a6-121">Klicka på Lägg till rad.</span><span class="sxs-lookup"><span data-stu-id="fb0a6-121">Click Add line.</span></span>
15. <span data-ttu-id="fb0a6-122">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="fb0a6-122">In the list, mark the selected row.</span></span>
16. <span data-ttu-id="fb0a6-123">Skriv 0140 i fältet Artikelnummer.</span><span class="sxs-lookup"><span data-stu-id="fb0a6-123">In the Item number field, type '0140'.</span></span>
17. <span data-ttu-id="fb0a6-124">Ställ in kvantiteten på 1000.</span><span class="sxs-lookup"><span data-stu-id="fb0a6-124">Set Quantity to '1000'.</span></span>
18. <span data-ttu-id="fb0a6-125">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="fb0a6-125">Click Save.</span></span>

