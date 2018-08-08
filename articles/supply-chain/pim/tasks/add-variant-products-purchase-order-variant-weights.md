--- 
title: "Lägg till variantprodukter i inköpsorder med hjälp av variantvikter"
description: "Den här proceduren går igenom stegen vid användning av variantvikt för att automatiskt fylla i inköpsorderrader för varje variant av en produkt."
author: ShylaThompson
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
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 1d98cbff30620256c9d13e7b4a90314db150e33e
ms.openlocfilehash: 446260a09bd5177877637ac8a288ad584dfa2b2b
ms.contentlocale: sv-se
ms.lasthandoff: 08/07/2018

---
# <a name="add-variant-products-to-purchase-orders-using-variant-weights"></a><span data-ttu-id="7577e-103">Lägg till variantprodukter i inköpsorder med hjälp av variantvikter</span><span class="sxs-lookup"><span data-stu-id="7577e-103">Add variant products to purchase orders using variant weights</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="7577e-104">Den här proceduren går igenom stegen vid användning av variantvikt för att automatiskt fylla i inköpsorderrader för varje variant av en produkt.</span><span class="sxs-lookup"><span data-stu-id="7577e-104">This procedure walks through the steps for using variant weights to auto populate purchase order lines for each variant of a product.</span></span> <span data-ttu-id="7577e-105">När du väljer kvantiteten av produkten som du vill köpa, inköpsorderrader skapas för alla varianter av produkten med föreslagna kvantiteter som baseras på de vikter som konfigureras på produktvarianterna.</span><span class="sxs-lookup"><span data-stu-id="7577e-105">When you select the quantity of the product you want to purchase, purchase order lines are created for all the variants of the product with suggested quantities based on the weights configured on the product variants.</span></span> <span data-ttu-id="7577e-106">Den här proceduren inkluderar inte steg för att konfigurera viktvärden på produktdimensioner och produktvarianter.</span><span class="sxs-lookup"><span data-stu-id="7577e-106">This procedure doesn’t include steps to configure weight values on product dimensions and product variants.</span></span> <span data-ttu-id="7577e-107">I proceduren används demonstrationsföretaget USRT.</span><span class="sxs-lookup"><span data-stu-id="7577e-107">This procedure uses the USRT company in demo data.</span></span>

1. <span data-ttu-id="7577e-108">Gå till leverantörsskulder > inköpsorder > Alla inköpsorder.</span><span class="sxs-lookup"><span data-stu-id="7577e-108">Go to Accounts payable > Purchase orders > All purchase orders.</span></span>
2. <span data-ttu-id="7577e-109">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="7577e-109">Click New.</span></span>
3. <span data-ttu-id="7577e-110">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Leverantörskonto.</span><span class="sxs-lookup"><span data-stu-id="7577e-110">In the Vendor account field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="7577e-111">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="7577e-111">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="7577e-112">Växla utökningen av avsnittet Allmänt.</span><span class="sxs-lookup"><span data-stu-id="7577e-112">Toggle the expansion of the General section.</span></span>
6. <span data-ttu-id="7577e-113">Öppna sökningen genom att klicka på listruteknappen i fältet Plats.</span><span class="sxs-lookup"><span data-stu-id="7577e-113">In the Site field, click the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="7577e-114">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="7577e-114">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="7577e-115">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Lagerställe.</span><span class="sxs-lookup"><span data-stu-id="7577e-115">In the Warehouse field, click the drop-down button to open the lookup.</span></span>
9. <span data-ttu-id="7577e-116">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="7577e-116">In the list, find and select the desired record.</span></span>
10. <span data-ttu-id="7577e-117">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="7577e-117">In the list, click the link in the selected row.</span></span>
11. <span data-ttu-id="7577e-118">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="7577e-118">Click OK.</span></span>
12. <span data-ttu-id="7577e-119">Växla expanderingen av avsnittet Raddetaljer.</span><span class="sxs-lookup"><span data-stu-id="7577e-119">Toggle the expansion of the Line details section.</span></span>
13. <span data-ttu-id="7577e-120">Klicka på fliken Varianter.</span><span class="sxs-lookup"><span data-stu-id="7577e-120">Click the Variants tab.</span></span>
14. <span data-ttu-id="7577e-121">Klicka på Lägg till rad.</span><span class="sxs-lookup"><span data-stu-id="7577e-121">Click Add line.</span></span>
15. <span data-ttu-id="7577e-122">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="7577e-122">In the list, mark the selected row.</span></span>
16. <span data-ttu-id="7577e-123">Skriv 0140 i fältet Artikelnummer.</span><span class="sxs-lookup"><span data-stu-id="7577e-123">In the Item number field, type '0140'.</span></span>
17. <span data-ttu-id="7577e-124">Ställ in kvantiteten på 1000.</span><span class="sxs-lookup"><span data-stu-id="7577e-124">Set Quantity to '1000'.</span></span>
18. <span data-ttu-id="7577e-125">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="7577e-125">Click Save.</span></span>


