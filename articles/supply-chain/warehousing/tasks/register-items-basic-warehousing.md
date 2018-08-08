--- 
title: "Registrera artiklar för en grundläggande lagerstyrningsaktiverad artikel med hjälp av en artikelinförseljournal"
description: "I den här proceduren visas hur du registrerar artiklar via artikelinförseljournalen när du använder “grundläggande lagerstyrning” i modulen Lagerhantering."
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
ms.search.industry: Distribution
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 1d98cbff30620256c9d13e7b4a90314db150e33e
ms.openlocfilehash: fdc483b44544c2dd580ba6435ba5f84d940be2a9
ms.contentlocale: sv-se
ms.lasthandoff: 08/07/2018

---
# <a name="register-items-for-a-basic-warehousing-enabled-item-using-an-item-arrival-journal"></a><span data-ttu-id="4bf4a-103">Registrera artiklar för en grundläggande lagerstyrningsaktiverad artikel med hjälp av en artikelinförseljournal</span><span class="sxs-lookup"><span data-stu-id="4bf4a-103">Register items for a basic warehousing enabled item using an item arrival journal</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="4bf4a-104">I den här proceduren visas hur du registrerar artiklar via artikelinförseljournalen när du använder “grundläggande lagerstyrning” i modulen Lagerhantering.</span><span class="sxs-lookup"><span data-stu-id="4bf4a-104">This procedure shows you how to register items using the item arrival journal when you are using “basic warehousing” in the Inventory management module.</span></span> <span data-ttu-id="4bf4a-105">Detta görs vanligtvis av en inleveransansvarig.</span><span class="sxs-lookup"><span data-stu-id="4bf4a-105">This would usually be done by a receiving clerk.</span></span> <span data-ttu-id="4bf4a-106">Du kan köra den här proceduren i demonstrationsdataföretaget USMF med exempelvärdena som visas.</span><span class="sxs-lookup"><span data-stu-id="4bf4a-106">You can run this procedure in demo data company USMF with the example values that are shown.</span></span>  <span data-ttu-id="4bf4a-107">Om du inte använder USMF måste du ha en bekräftad inköpsorder med en öppen inköpsorderrad innan du startar den här guiden.</span><span class="sxs-lookup"><span data-stu-id="4bf4a-107">If you are not using USMF, you need to have a confirmed purchase order with an open purchase order line before you start this guide.</span></span> <span data-ttu-id="4bf4a-108">Artikeln på raden måste finnas i lager och får inte innehålla produktvarianter och spårningsdimensioner.</span><span class="sxs-lookup"><span data-stu-id="4bf4a-108">The item on the line must be stocked, and it must not use product variants, and must not have tracking dimensions.</span></span> <span data-ttu-id="4bf4a-109">Och artikeln behöver associeras med en lagringsdimension grupp, där webbplats och lagerställe är aktiva.</span><span class="sxs-lookup"><span data-stu-id="4bf4a-109">And the item needs to be associated with a storage dimension group, where site and warehouse are active.</span></span>


## <a name="create-item-arrival-journal-header"></a><span data-ttu-id="4bf4a-110">Skapa artikelinförseljournalhuvudet</span><span class="sxs-lookup"><span data-stu-id="4bf4a-110">Create item arrival journal header</span></span>
1. <span data-ttu-id="4bf4a-111">Gå till Lagerhantering > Poster i redovisningsjournal > Artikelinförsel > Artikelinförsel.</span><span class="sxs-lookup"><span data-stu-id="4bf4a-111">Go to Inventory management > Journal entries > Item arrival > Item arrival.</span></span>
2. <span data-ttu-id="4bf4a-112">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="4bf4a-112">Click New.</span></span>
3. <span data-ttu-id="4bf4a-113">Skriv ett värde i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="4bf4a-113">In the Name field, type a value.</span></span>
    * <span data-ttu-id="4bf4a-114">Om du använder USMF kan du skriva WHS.</span><span class="sxs-lookup"><span data-stu-id="4bf4a-114">If you are using USMF, you can type WHS.</span></span> <span data-ttu-id="4bf4a-115">Om du använder andra data måste journalen vars namn du väljer ha följande egenskaper: Kontrollera plockplats måste anges till Nej och Karantänhantering måste anges till Nej.</span><span class="sxs-lookup"><span data-stu-id="4bf4a-115">If you’re using other data, the journal whose name you choose has to have the following properties: check picking location must be set to No, and Quarantine management must be set to No.</span></span>  
4. <span data-ttu-id="4bf4a-116">Skriv ett värde i fältet Följesedel.</span><span class="sxs-lookup"><span data-stu-id="4bf4a-116">In the Packing slip field, type a value.</span></span>
    * <span data-ttu-id="4bf4a-117">Detta är följesedels-id:t från den följesedel som har utfärdats av leverantören.</span><span class="sxs-lookup"><span data-stu-id="4bf4a-117">This is the packing slip ID from the packing slip issued by the vendor.</span></span> <span data-ttu-id="4bf4a-118">Lägg till ett unikt nummer.</span><span class="sxs-lookup"><span data-stu-id="4bf4a-118">Add a unique number.</span></span>  
5. <span data-ttu-id="4bf4a-119">Välj inköpsordern i fältet Antal i fältet Antal.</span><span class="sxs-lookup"><span data-stu-id="4bf4a-119">In the Number field, In the Number field, select the purchase order..</span></span>
6. <span data-ttu-id="4bf4a-120">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="4bf4a-120">Click OK.</span></span>

## <a name="add-lines-to-item-arrival-journal"></a><span data-ttu-id="4bf4a-121">Lägg till rader till artikelinförseljournal</span><span class="sxs-lookup"><span data-stu-id="4bf4a-121">Add lines to item arrival journal</span></span>
1. <span data-ttu-id="4bf4a-122">Klicka på Funktioner.</span><span class="sxs-lookup"><span data-stu-id="4bf4a-122">Click Functions.</span></span>
2. <span data-ttu-id="4bf4a-123">Klicka på Skapa rader.</span><span class="sxs-lookup"><span data-stu-id="4bf4a-123">Click Create lines.</span></span>
    * <span data-ttu-id="4bf4a-124">Raderna kan anges manuellt i den här journalen eller skapas automatiskt.</span><span class="sxs-lookup"><span data-stu-id="4bf4a-124">The lines can be entered manually into this journal or created automatically.</span></span> <span data-ttu-id="4bf4a-125">Detta visar hur du skapar detta automatiskt.</span><span class="sxs-lookup"><span data-stu-id="4bf4a-125">This will show you how to create this automatically.</span></span>  
3. <span data-ttu-id="4bf4a-126">Markera eller avmarkera kryssrutan Initiera kvantitet.</span><span class="sxs-lookup"><span data-stu-id="4bf4a-126">Check or uncheck the Initialize quantity checkbox.</span></span>
    * <span data-ttu-id="4bf4a-127">Detta initierar kvantiteten på journalraderna med den kvantitet som inte ännu har registrerats från inköpsorderraden.</span><span class="sxs-lookup"><span data-stu-id="4bf4a-127">This will initialize the quantity on the journal lines with the quantity not registered from the purchase order line.</span></span>  
4. <span data-ttu-id="4bf4a-128">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="4bf4a-128">Click OK.</span></span>

## <a name="post-the-journal"></a><span data-ttu-id="4bf4a-129">Bokför journalen</span><span class="sxs-lookup"><span data-stu-id="4bf4a-129">Post the journal</span></span>
1. <span data-ttu-id="4bf4a-130">Klicka på Bokför.</span><span class="sxs-lookup"><span data-stu-id="4bf4a-130">Click Post.</span></span>
2. <span data-ttu-id="4bf4a-131">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="4bf4a-131">Click OK.</span></span>

## <a name="generate-the-product-receipt"></a><span data-ttu-id="4bf4a-132">Generera produktinleveransen</span><span class="sxs-lookup"><span data-stu-id="4bf4a-132">Generate the product receipt</span></span>
1. <span data-ttu-id="4bf4a-133">Klicka på Funktioner.</span><span class="sxs-lookup"><span data-stu-id="4bf4a-133">Click Functions.</span></span>
2. <span data-ttu-id="4bf4a-134">Klicka på Produktinleverans.</span><span class="sxs-lookup"><span data-stu-id="4bf4a-134">Click Product receipt.</span></span>
3. <span data-ttu-id="4bf4a-135">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="4bf4a-135">Click OK.</span></span>


