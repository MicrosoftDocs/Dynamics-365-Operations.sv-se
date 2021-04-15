---
title: Skapa en inköpsfrisläppningsorder när inköpsordern skapas
description: I den här proceduren visas hur du använder en inköpsavtal när du skapar en inköpsorder.
author: kamaybac
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: dabourq
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d2f02961f5f7da9bff389737b447e3b143dd72e3
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5812283"
---
# <a name="create-a-purchase-release-order-when-creating-the-purchase-order"></a><span data-ttu-id="f0e62-103">Skapa en inköpsfrisläppningsorder när inköpsordern skapas</span><span class="sxs-lookup"><span data-stu-id="f0e62-103">Create a purchase release order when creating the purchase order</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="f0e62-104">I den här proceduren visas hur du använder en inköpsavtal när du skapar en inköpsorder.</span><span class="sxs-lookup"><span data-stu-id="f0e62-104">This procedure shows how to use a purchase agreement when you create a purchase order.</span></span> <span data-ttu-id="f0e62-105">Inköpsavtalet måste tillämpas när du skapar inköpsordern eftersom det finns allmänna villkor som ska kopieras till inköpsorderhuvudet.</span><span class="sxs-lookup"><span data-stu-id="f0e62-105">The purchase agreement has to be applied when you create the purchase order because there are general terms that should be copied to the purchase order header.</span></span> <span data-ttu-id="f0e62-106">Uppgiften utförs vanligtvis av en inköpsagent.</span><span class="sxs-lookup"><span data-stu-id="f0e62-106">Typically this task would be carried out by a purchasing agent.</span></span> <span data-ttu-id="f0e62-107">Som en förutsättning för den här guiden måste du ha ett giltigt inköpsavtal med en produktkvantitetsutfästelse för en leverantör och artiklar.</span><span class="sxs-lookup"><span data-stu-id="f0e62-107">As a prerequisite for this guide, you must have an effective purchase agreement with a product quantity commitment for a vendor and items.</span></span> <span data-ttu-id="f0e62-108">Samma procedur kan användas om du har en inköpsavtal med andra typer av utfästelser.</span><span class="sxs-lookup"><span data-stu-id="f0e62-108">The same procedure can be used if you have a purchase agreement with other types of commitments.</span></span> <span data-ttu-id="f0e62-109">Du kan köra den här handboken i demonstrationsdataföretaget USMF.</span><span class="sxs-lookup"><span data-stu-id="f0e62-109">You can run this guide in demo data company USMF.</span></span> <span data-ttu-id="f0e62-110">Om du använder USMF kan du köra guiden "Skapa ett inköpsavtal" först när du vill ställa in de nödvändiga förutsättningarna för den här guiden.</span><span class="sxs-lookup"><span data-stu-id="f0e62-110">If you're using USMF, you can run the "Create a purchase agreement" guide first to set up the necessary preconditions for this guide.</span></span>


## <a name="create-a-purchase-order"></a><span data-ttu-id="f0e62-111">Skapa en inköpsorder</span><span class="sxs-lookup"><span data-stu-id="f0e62-111">Create a purchase order</span></span>
1. <span data-ttu-id="f0e62-112">Öppna arbetsyta för inköpsorderförberedelse.</span><span class="sxs-lookup"><span data-stu-id="f0e62-112">Open the purchase order preparation workspace.</span></span>
2. <span data-ttu-id="f0e62-113">Klicka på Ny inköpsorder.</span><span class="sxs-lookup"><span data-stu-id="f0e62-113">Click New purchase order.</span></span>
3. <span data-ttu-id="f0e62-114">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Leverantörskonto.</span><span class="sxs-lookup"><span data-stu-id="f0e62-114">In the Vendor account field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="f0e62-115">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="f0e62-115">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="f0e62-116">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="f0e62-116">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="f0e62-117">Växla utökningen av avsnittet Allmänt.</span><span class="sxs-lookup"><span data-stu-id="f0e62-117">Toggle the expansion of the General section.</span></span>
7. <span data-ttu-id="f0e62-118">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Inköpsavtal.</span><span class="sxs-lookup"><span data-stu-id="f0e62-118">In the Purchase agreement field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="f0e62-119">Alla tillgängliga avtal för leverantören anges här.</span><span class="sxs-lookup"><span data-stu-id="f0e62-119">All available agreements for the vendor are listed here.</span></span> <span data-ttu-id="f0e62-120">Sök efter det giltiga avtal som du vill använda.</span><span class="sxs-lookup"><span data-stu-id="f0e62-120">Find the effective agreement that you want to use.</span></span>  
8. <span data-ttu-id="f0e62-121">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="f0e62-121">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="f0e62-122">Klicka på Ja.</span><span class="sxs-lookup"><span data-stu-id="f0e62-122">Click Yes.</span></span>
10. <span data-ttu-id="f0e62-123">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="f0e62-123">Click OK.</span></span>

## <a name="add-a-line"></a><span data-ttu-id="f0e62-124">Lägga till en rad</span><span class="sxs-lookup"><span data-stu-id="f0e62-124">Add a line</span></span>
1. <span data-ttu-id="f0e62-125">Skriv ett värde i fältet Artikelnummer.</span><span class="sxs-lookup"><span data-stu-id="f0e62-125">In the Item number field, type a value.</span></span>
    * <span data-ttu-id="f0e62-126">Om det finns specifika lager- eller platsdimensioner på utfästelsen måste du ange samma värden på inköpsorderraden för att underlätta användningen av avtalet.</span><span class="sxs-lookup"><span data-stu-id="f0e62-126">If there are specific inventory or location dimensions on the commitment you must enter the same values on the purchase order line to make use of the agreement.</span></span>  
2. <span data-ttu-id="f0e62-127">Öppna sökningen genom att klicka på listruteknappen i fältet Plats.</span><span class="sxs-lookup"><span data-stu-id="f0e62-127">In the Site field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="f0e62-128">Webbplatsen kan redan ha fyllts i med standardvärdet från ordern eller från leverantören.</span><span class="sxs-lookup"><span data-stu-id="f0e62-128">The site may already be populated with the default value from the order, or from the vendor.</span></span> <span data-ttu-id="f0e62-129">Om så är fallet hoppar du över detta steg.</span><span class="sxs-lookup"><span data-stu-id="f0e62-129">If this is the case, skip this step.</span></span>  
3. <span data-ttu-id="f0e62-130">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="f0e62-130">In the list, find and select the desired record.</span></span>
4. <span data-ttu-id="f0e62-131">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="f0e62-131">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="f0e62-132">Ange ett tal i fältet Kvantitet.</span><span class="sxs-lookup"><span data-stu-id="f0e62-132">In the Quantity field, enter a number.</span></span>
    * <span data-ttu-id="f0e62-133">Validera att priset kopieras från utfästelsen.</span><span class="sxs-lookup"><span data-stu-id="f0e62-133">Validate that the price is copied from the commitment.</span></span>  

## <a name="look-up-the-commitment"></a><span data-ttu-id="f0e62-134">Slå upp utfästelsen</span><span class="sxs-lookup"><span data-stu-id="f0e62-134">Look up the commitment</span></span>
1. <span data-ttu-id="f0e62-135">Klicka på Uppdatera rad.</span><span class="sxs-lookup"><span data-stu-id="f0e62-135">Click Update line.</span></span>
2. <span data-ttu-id="f0e62-136">Klicka på Kopplat.</span><span class="sxs-lookup"><span data-stu-id="f0e62-136">Click Attached.</span></span>
    * <span data-ttu-id="f0e62-137">Här kan du få information om inköpsavtalet.</span><span class="sxs-lookup"><span data-stu-id="f0e62-137">Here you can get details for the purchase agreement.</span></span> <span data-ttu-id="f0e62-138">Du kan till exempel se priset och om priset och rabatten är fasta, vilket innebär att om du ändrar priset eller rabatten på inköpsordern till ett annat värde än på utfästelsen, så tas länken bort så att inköpsorderraden inte uppfyller utfästelsen.</span><span class="sxs-lookup"><span data-stu-id="f0e62-138">For example, you can see the price and whether the price and discount are fixed, which means that if you change price or discount on the purchase order to a different value than on the commitment, the system will remove the link so the purchase order line does not fulfill the commitment.</span></span> <span data-ttu-id="f0e62-139">Du kan även se om alternativet Max framtvingas, vilket innebär att kvantiteten på utfästelsen inte kan överskridas genom att summera alla inköp som uppfyller utfästelsen.</span><span class="sxs-lookup"><span data-stu-id="f0e62-139">You can also see if the Max is enforced option is selected, which means that the quantity on the commitment cannot be exceeded by summing all of the purchases that fulfill the commitment.</span></span>  
3. <span data-ttu-id="f0e62-140">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="f0e62-140">Close the page.</span></span>

## <a name="look-up-the-purchase-agreement"></a><span data-ttu-id="f0e62-141">Slå upp inköpsavtalet</span><span class="sxs-lookup"><span data-stu-id="f0e62-141">Look up the purchase agreement</span></span>
1. <span data-ttu-id="f0e62-142">Klicka på Allmänt i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="f0e62-142">On the Action Pane, click General.</span></span>
2. <span data-ttu-id="f0e62-143">Klicka på Inköpsavtal.</span><span class="sxs-lookup"><span data-stu-id="f0e62-143">Click Purchase agreement.</span></span>
3. <span data-ttu-id="f0e62-144">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="f0e62-144">Close the page.</span></span>
4. <span data-ttu-id="f0e62-145">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="f0e62-145">Close the page.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]