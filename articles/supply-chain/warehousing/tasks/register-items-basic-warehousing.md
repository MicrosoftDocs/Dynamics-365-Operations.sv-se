---
title: Registrera artiklar för en grundläggande lagerstyrningsaktiverad artikel med hjälp av en artikelinförseljournal
description: I den här proceduren visas hur du registrerar artiklar via artikelinförseljournalen när du använder “grundläggande lagerstyrning” i modulen Lagerhantering.
author: ShylaThompson
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchTable, PurchTablePart, PurchCreateOrder, WMSJournalTable, WMSJournalCreate, PurchEditLines
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 3edf84135e675b6259972327f80c9b6a91821139
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5254177"
---
# <a name="register-items-for-a-basic-warehousing-enabled-item-using-an-item-an-item-arrival-journal"></a><span data-ttu-id="2278c-103">Registrera artiklar för en grundläggande lagerstyrningsaktiverad artikel med hjälp av en artikelinförseljournal</span><span class="sxs-lookup"><span data-stu-id="2278c-103">Register items for a basic warehousing enabled item using an item an item arrival journal</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="2278c-104">I den här proceduren visas hur du registrerar artiklar via artikelinförseljournalen när du använder “grundläggande lagerstyrning” i modulen Lagerhantering.</span><span class="sxs-lookup"><span data-stu-id="2278c-104">This procedure shows you how to register items using the item arrival journal when you are using "basic warehousing" in the Inventory management module.</span></span> <span data-ttu-id="2278c-105">Detta görs vanligtvis av en inleveransansvarig.</span><span class="sxs-lookup"><span data-stu-id="2278c-105">This would usually be done by a receiving clerk.</span></span> <span data-ttu-id="2278c-106">Du kan köra den här proceduren i demonstrationsdataföretaget USMF med exempelvärdena som visas.</span><span class="sxs-lookup"><span data-stu-id="2278c-106">You can run this procedure in demo data company USMF with the example values that are shown.</span></span>  <span data-ttu-id="2278c-107">Om du inte använder USMF måste du ha en bekräftad inköpsorder med en öppen inköpsorderrad innan du startar den här guiden.</span><span class="sxs-lookup"><span data-stu-id="2278c-107">If you are not using USMF, you need to have a confirmed purchase order with an open purchase order line before you start this guide.</span></span> <span data-ttu-id="2278c-108">Artikeln på raden måste lagras.</span><span class="sxs-lookup"><span data-stu-id="2278c-108">The item on the line must be stocked.</span></span> <span data-ttu-id="2278c-109">Och artikeln behöver associeras med en lagringsdimension grupp, där webbplats och lagerställe är aktiva.</span><span class="sxs-lookup"><span data-stu-id="2278c-109">And the item needs to be associated with a storage dimension group, where site and warehouse are active.</span></span>


## <a name="create-item-arrival-journal-header"></a><span data-ttu-id="2278c-110">Skapa artikelinförseljournalhuvudet</span><span class="sxs-lookup"><span data-stu-id="2278c-110">Create item arrival journal header</span></span>
1. <span data-ttu-id="2278c-111">Gå till Lagerhantering > Poster i redovisningsjournal > Artikelinförsel > Artikelinförsel.</span><span class="sxs-lookup"><span data-stu-id="2278c-111">Go to Inventory management > Journal entries > Item arrival > Item arrival.</span></span>
2. <span data-ttu-id="2278c-112">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="2278c-112">Click New.</span></span>
3. <span data-ttu-id="2278c-113">Skriv ett värde i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="2278c-113">In the Name field, type a value.</span></span>
    * <span data-ttu-id="2278c-114">Om du använder USMF kan du skriva WHS.</span><span class="sxs-lookup"><span data-stu-id="2278c-114">If you are using USMF, you can type WHS.</span></span> <span data-ttu-id="2278c-115">Om du använder andra data måste journalen vars namn du väljer ha följande egenskaper: Kontrollera plockplats måste anges till Nej och Karantänhantering måste anges till Nej.</span><span class="sxs-lookup"><span data-stu-id="2278c-115">If you're using other data, the journal whose name you choose has to have the following properties: cheque picking location must be set to No, and Quarantine management must be set to No.</span></span>  
4. <span data-ttu-id="2278c-116">Skriv ett värde i fältet Följesedel.</span><span class="sxs-lookup"><span data-stu-id="2278c-116">In the Packing slip field, type a value.</span></span>
    * <span data-ttu-id="2278c-117">Detta är följesedels-id:t från den följesedel som har utfärdats av leverantören.</span><span class="sxs-lookup"><span data-stu-id="2278c-117">This is the packing slip ID from the packing slip issued by the vendor.</span></span> <span data-ttu-id="2278c-118">Lägg till ett unikt nummer.</span><span class="sxs-lookup"><span data-stu-id="2278c-118">Add a unique number.</span></span>  
5. <span data-ttu-id="2278c-119">Välj inköpsordern i fältet Antal i fältet Antal.</span><span class="sxs-lookup"><span data-stu-id="2278c-119">In the Number field, In the Number field, select the purchase order..</span></span>
6. <span data-ttu-id="2278c-120">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="2278c-120">Click OK.</span></span>

## <a name="add-lines-to-item-arrival-journal"></a><span data-ttu-id="2278c-121">Lägg till rader till artikelinförseljournal</span><span class="sxs-lookup"><span data-stu-id="2278c-121">Add lines to item arrival journal</span></span>
1. <span data-ttu-id="2278c-122">Klicka på Funktioner.</span><span class="sxs-lookup"><span data-stu-id="2278c-122">Click Functions.</span></span>
2. <span data-ttu-id="2278c-123">Klicka på Skapa rader.</span><span class="sxs-lookup"><span data-stu-id="2278c-123">Click Create lines.</span></span>
    * <span data-ttu-id="2278c-124">Raderna kan anges manuellt i den här journalen eller skapas automatiskt.</span><span class="sxs-lookup"><span data-stu-id="2278c-124">The lines can be entered manually into this journal or created automatically.</span></span> <span data-ttu-id="2278c-125">Detta visar hur du skapar detta automatiskt.</span><span class="sxs-lookup"><span data-stu-id="2278c-125">This will show you how to create this automatically.</span></span>  
3. <span data-ttu-id="2278c-126">Markera eller avmarkera kryssrutan Initiera kvantitet.</span><span class="sxs-lookup"><span data-stu-id="2278c-126">Check or uncheck the Initialize quantity checkbox.</span></span>
    * <span data-ttu-id="2278c-127">Detta initierar kvantiteten på journalraderna med den kvantitet som inte ännu har registrerats från inköpsorderraden.</span><span class="sxs-lookup"><span data-stu-id="2278c-127">This will initialize the quantity on the journal lines with the quantity not registered from the purchase order line.</span></span>  
4. <span data-ttu-id="2278c-128">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="2278c-128">Click OK.</span></span>

## <a name="post-the-journal"></a><span data-ttu-id="2278c-129">Bokför journalen</span><span class="sxs-lookup"><span data-stu-id="2278c-129">Post the journal</span></span>
1. <span data-ttu-id="2278c-130">Klicka på Bokför.</span><span class="sxs-lookup"><span data-stu-id="2278c-130">Click Post.</span></span>
2. <span data-ttu-id="2278c-131">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="2278c-131">Click OK.</span></span>

## <a name="generate-the-product-receipt"></a><span data-ttu-id="2278c-132">Generera produktinleveransen</span><span class="sxs-lookup"><span data-stu-id="2278c-132">Generate the product receipt</span></span>
1. <span data-ttu-id="2278c-133">Klicka på Funktioner.</span><span class="sxs-lookup"><span data-stu-id="2278c-133">Click Functions.</span></span>
2. <span data-ttu-id="2278c-134">Klicka på Produktinleverans.</span><span class="sxs-lookup"><span data-stu-id="2278c-134">Click Product receipt.</span></span>
3. <span data-ttu-id="2278c-135">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="2278c-135">Click OK.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]