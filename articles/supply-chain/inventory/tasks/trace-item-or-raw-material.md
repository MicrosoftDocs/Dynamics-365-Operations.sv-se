---
title: Spåra en artikel eller råmaterial
description: I den här proceduren visas hur du använder artikelspårning för att identifiera var artiklar eller råmaterial har använts eller används.
author: pjacobse
ms.date: 08/12/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: InventTrackingDimTracing, InventTrackingDimTracingCriteria, InventTrackingItemIdLookup, InventBatchIdLookup, CustTable, SalesLine
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: pjacobse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7a3b2ab752089b2c60c5c5e02cb2c558c17dcf8b
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5829822"
---
# <a name="trace-an-item-or-raw-material"></a><span data-ttu-id="939b6-103">Spåra en artikel eller råmaterial</span><span class="sxs-lookup"><span data-stu-id="939b6-103">Trace an item or raw material</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="939b6-104">I den här proceduren visas hur du använder artikelspårning för att identifiera var artiklar eller råmaterial har använts eller används.</span><span class="sxs-lookup"><span data-stu-id="939b6-104">This procedure demonstrates how to use item tracing to identify where items or raw materials have been used or are being used.</span></span> <span data-ttu-id="939b6-105">Med den här proceduren kan identifiera en artikel, spåra den tillbaka till källan och sedan spåra framåt igenom produktionen och försäljningen av den färdiga produkten.</span><span class="sxs-lookup"><span data-stu-id="939b6-105">With this procedure, you can identify an item, trace it back to the source, and then trace forward through the production and sale of the finished product.</span></span> <span data-ttu-id="939b6-106">Processen kan användas för att undersöka berörda kunder, försäljningsorder och annat.</span><span class="sxs-lookup"><span data-stu-id="939b6-106">The process can be used to investigate the customers impacted, the sales orders affected, and more.</span></span> <span data-ttu-id="939b6-107">I proceduren används demonstrationsföretag USP2.</span><span class="sxs-lookup"><span data-stu-id="939b6-107">This procedure uses demo data company USP2.</span></span>


## <a name="trace-an-item-backwards-using-a-known-batch-number"></a><span data-ttu-id="939b6-108">Spåra en artikel bakåt med ett känt batchnummer</span><span class="sxs-lookup"><span data-stu-id="939b6-108">Trace an item backwards using a known batch number</span></span>
1. <span data-ttu-id="939b6-109">I **navigeringsfönstret**, gå till **Moduler > Lagerhantering > Förfrågningar och rapporter > Spårningsdimensioner > Artikelspårning**.</span><span class="sxs-lookup"><span data-stu-id="939b6-109">In the **Navigation pane**, go to **Modules > Inventory management > Inquiries and reports > Tracking dimensions > Item tracing**.</span></span>
2. <span data-ttu-id="939b6-110">Välj P9100 i fältet **Artikelnummer**.</span><span class="sxs-lookup"><span data-stu-id="939b6-110">In the **Item number** field, select 'P9100'.</span></span>
3. <span data-ttu-id="939b6-111">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="939b6-111">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="939b6-112">Välj Bakåt i fältet **Framåt eller bakåt.**</span><span class="sxs-lookup"><span data-stu-id="939b6-112">In the **Forward or backward** field, select 'Backward'.</span></span>
5. <span data-ttu-id="939b6-113">I fältet **Batchnummer**, välj "as-12-344-01".</span><span class="sxs-lookup"><span data-stu-id="939b6-113">In the **Batch number** field, select 'as-12-344-01'.</span></span>
6. <span data-ttu-id="939b6-114">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="939b6-114">In the list, click the link in the selected row.</span></span>
7. <span data-ttu-id="939b6-115">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="939b6-115">Click **OK**.</span></span>

## <a name="identify-an-item-trace-it-forward-and-make-an-analysis"></a><span data-ttu-id="939b6-116">Identifiera en artikel, spåra den framåt och gör en analys</span><span class="sxs-lookup"><span data-stu-id="939b6-116">Identify an item, trace it forward, and make an analysis</span></span>

<span data-ttu-id="939b6-117">Den övre noden i trädet representerar lagerbehållningen för den valda artikeln och batchen.</span><span class="sxs-lookup"><span data-stu-id="939b6-117">The top node of the tree represents the on hand quantity of the selected item and batch.</span></span> <span data-ttu-id="939b6-118">Du behöver expandera noderna i trädstrukturen för att hitta artikeln som framåtspårningen ska köras på.</span><span class="sxs-lookup"><span data-stu-id="939b6-118">You need to expand the nodes of the tree to find the item that the forward trace should be executed on.</span></span>   
1. <span data-ttu-id="939b6-119">Expandera ”noder som beskrivs nedan och välj sedan den senaste noden” i trädet.</span><span class="sxs-lookup"><span data-stu-id="939b6-119">In the tree, expand 'the nodes described below, and then select the last node'.</span></span>
    
    <span data-ttu-id="939b6-120">Visa: "P9100 / 1 / 10 / as-12-344-01 ● 2 keg ● 7,00 gal \P9100 ● Plockad ● Försäljningsorder 000072 ● 12/22/2015  ● -1 keg ● -4,00 gal ● Site=1, Lagerställe=10, Batchnummer=as-12-344-01 \P9100 ● Produktion B-000050 ● 12/9/2015● 7 keg ● 27,00 gal ● Site=1, Lagerställe=10, Batchnummer=as-12-344-01 ● Samprodukter: P9101" och sedan väljer du den noden.</span><span class="sxs-lookup"><span data-stu-id="939b6-120">Expand: 'P9100 / 1 / 10 / as-12-344-01 ● 2 keg ● 7.00 gal  \P9100 ● Picked ● Sales order 000072 ● 12/22/2015  ● -1 keg ● -4.00 gal ● Site=1, Warehouse=10, Batch number=as-12-344-01  \P9100 ● Production B-000050 ● 12/9/2015● 7 keg ● 27.00 gal ● Site=1,Warehouse=10,Batch number=as-12-344-01 ● Co-products: P9101' and then select that node.</span></span>     
2. <span data-ttu-id="939b6-121">Expandera ”noden som beskrivs nedan och välj sedan den noden” i trädet.</span><span class="sxs-lookup"><span data-stu-id="939b6-121">In the tree, expand 'the node described below and then select that node'.</span></span>
    
    <span data-ttu-id="939b6-122">Med start från noden som du just har markerat visar du "M9103 ● Produktionsrad B-000050 ● 12/9/2015  ● -160,00 lb ● Storlek=70, Färg=OK, Site=1, Lagerställe=10, Batchnummer=App01" och sedan väljer du den noden.</span><span class="sxs-lookup"><span data-stu-id="939b6-122">Starting from the node that you've just selected,  expand 'M9103 ● Production line B-000050 ● 12/9/2015  ● -160.00 lb ● Size=70, Color=OK, Site=1, Warehouse=10, Batch number=App01' and then select that node.</span></span>  
3. <span data-ttu-id="939b6-123">Klicka på **Spåra från nod.**</span><span class="sxs-lookup"><span data-stu-id="939b6-123">Click **Trace from node**.</span></span>
4. <span data-ttu-id="939b6-124">Klicka på **Framåt.**</span><span class="sxs-lookup"><span data-stu-id="939b6-124">Click **Forward**.</span></span>
5. <span data-ttu-id="939b6-125">Klicka på **Spårning** i **åtgärdsfönstret**.</span><span class="sxs-lookup"><span data-stu-id="939b6-125">On the **Action Pane**, click **Tracing**.</span></span>
    
    <span data-ttu-id="939b6-126">Det finns flera spårningsalternativ som ger information om kunder som har påverkats av artikeln som du spårar och de försäljningsorder som är relaterade till artikeln och som inte har levererats.</span><span class="sxs-lookup"><span data-stu-id="939b6-126">There are several tracing options which provide information about the customers impacted by the item that you're tracing, and the sales orders related to the item which have and haven't been shipped.</span></span>   
6. <span data-ttu-id="939b6-127">Klicka på **Kunder.**</span><span class="sxs-lookup"><span data-stu-id="939b6-127">Click **Customers**.</span></span>
7. <span data-ttu-id="939b6-128">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="939b6-128">Close the page.</span></span>
8. <span data-ttu-id="939b6-129">Klicka på **Spårning** i **åtgärdsfönstret**.</span><span class="sxs-lookup"><span data-stu-id="939b6-129">On the **Action Pane**, click **Tracing**.</span></span>
9. <span data-ttu-id="939b6-130">Klicka på **Levererade försäljningsorder.**</span><span class="sxs-lookup"><span data-stu-id="939b6-130">Click **Shipped sales orders**.</span></span>
10. <span data-ttu-id="939b6-131">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="939b6-131">Close the page.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]