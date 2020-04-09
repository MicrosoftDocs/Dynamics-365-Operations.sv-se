---
title: Skapa och underhålla en lagerspärr
description: I den här proceduren visas hur du kan förhindra den fysiska lagerbehållningen från att reserveras av andra utgående källdokument genom att använda lagerspärren.
author: perlynne
manager: AnnBe
ms.date: 08/08/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventBlocking, InventItemIdLookupSimple, InventLocationIdLookup
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 2408addea3615ffe6dbc4db8baecfdef6a65e839
ms.sourcegitcommit: fcb27d6a46cd544feef34f6ec7607bdd46b0c12b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/18/2020
ms.locfileid: "3145834"
---
# <a name="create-and-maintain-an-inventory-blocking"></a><span data-ttu-id="cfa86-103">Skapa och underhålla en lagerspärr</span><span class="sxs-lookup"><span data-stu-id="cfa86-103">Create and maintain an inventory blocking</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="cfa86-104">I den här proceduren visas hur du kan förhindra den fysiska lagerbehållningen från att reserveras av andra utgående källdokument genom att använda lagerspärren.</span><span class="sxs-lookup"><span data-stu-id="cfa86-104">This procedure shows how to prevent physical on-hand inventory from being reserved by other outbound source documents by using the inventory blocking.</span></span> <span data-ttu-id="cfa86-105">Du kan köra proceduren i demonstrationsdataföretaget USMF med hjälp av exempelvärdena som visas.</span><span class="sxs-lookup"><span data-stu-id="cfa86-105">You can run the procedure in demo data company USMF using the example values that are shown.</span></span> <span data-ttu-id="cfa86-106">Du behöver ha en artikel med fysisk lagerbehållning tillgänglig innan du startar den här proceduren.</span><span class="sxs-lookup"><span data-stu-id="cfa86-106">You need to have an item with physical on-hand inventory available before you start this procedure.</span></span>


## <a name="create-an-inventory-blocking"></a><span data-ttu-id="cfa86-107">Skapa en lagerspärr</span><span class="sxs-lookup"><span data-stu-id="cfa86-107">Create an inventory blocking</span></span>
1. <span data-ttu-id="cfa86-108">I **navigeringsfönstret**, gå till **Moduler > Lagerhantering >Periodiska uppgifter > Lagerspärr**.</span><span class="sxs-lookup"><span data-stu-id="cfa86-108">In the **Navigation pane**, go to **Modules > Inventory management > Periodic tasks > Inventory blocking**.</span></span>
2. <span data-ttu-id="cfa86-109">Klicka på **Ny**.</span><span class="sxs-lookup"><span data-stu-id="cfa86-109">Click **New**.</span></span>
3. <span data-ttu-id="cfa86-110">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet **Artikelnummer**.</span><span class="sxs-lookup"><span data-stu-id="cfa86-110">In the **Item number** field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="cfa86-111">Välj den artikel som du vill ha i listan.</span><span class="sxs-lookup"><span data-stu-id="cfa86-111">In the list, select the item you want to choose.</span></span> <span data-ttu-id="cfa86-112">Välj ett artikelnummer med fysisk lagerbehållning som du vill spärra.</span><span class="sxs-lookup"><span data-stu-id="cfa86-112">Select an item number with physical on-hand inventory that you want to block.</span></span> <span data-ttu-id="cfa86-113">Om du använder USMF kan du välja artikeln M9201.</span><span class="sxs-lookup"><span data-stu-id="cfa86-113">If you're using USMF you can select item M9201.</span></span>  
5. <span data-ttu-id="cfa86-114">Ange ett nummer i fältet **Kvantitet**.</span><span class="sxs-lookup"><span data-stu-id="cfa86-114">In the **Quantity** field, enter a number.</span></span> <span data-ttu-id="cfa86-115">Om du använder artikeln M9201 måste du välja lägre än 200.</span><span class="sxs-lookup"><span data-stu-id="cfa86-115">If you're using item M9201, you need to select less than 200.</span></span>
6. <span data-ttu-id="cfa86-116">Expandera snabbfliken **Lagerdimensioner.**</span><span class="sxs-lookup"><span data-stu-id="cfa86-116">Expand the **Inventory dimensions** fastTab.</span></span>
7. <span data-ttu-id="cfa86-117">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet **Lagerställe**.</span><span class="sxs-lookup"><span data-stu-id="cfa86-117">In the **Warehouse** field, click the drop-down button to open the lookup.</span></span>
8. <span data-ttu-id="cfa86-118">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="cfa86-118">In the list, find and select the desired record.</span></span> <span data-ttu-id="cfa86-119">Om du använder artikeln M9201 kan du välja lager 51.</span><span class="sxs-lookup"><span data-stu-id="cfa86-119">If you're using item M9201, you can select warehouse 51.</span></span>  
9. <span data-ttu-id="cfa86-120">Klicka på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="cfa86-120">Click **Save**.</span></span>

## <a name="update-the-conditions-of-the-inventory-blocking"></a><span data-ttu-id="cfa86-121">Uppdatera villkoren för lagerspärrren</span><span class="sxs-lookup"><span data-stu-id="cfa86-121">Update the conditions of the inventory blocking</span></span>
1. <span data-ttu-id="cfa86-122">Ange ett nummer på snabbfliken **Allmänt**, i fältet **Kvantitet**.</span><span class="sxs-lookup"><span data-stu-id="cfa86-122">In the **General** fastTab, in the **Quantity** field, enter a number.</span></span> <span data-ttu-id="cfa86-123">Uppdatera lagerkvantitetsfältet som speglar kvantiteten som ska spärras.</span><span class="sxs-lookup"><span data-stu-id="cfa86-123">Update the inventory quantity field to reflect the quantity to block.</span></span>  
2. <span data-ttu-id="cfa86-124">Ange ett datum i fältet **Förväntat datum.**</span><span class="sxs-lookup"><span data-stu-id="cfa86-124">In the **Expected date** field, enter a date.</span></span> <span data-ttu-id="cfa86-125">Du kanske vill ange när det spärrade lagret förväntas bli tillgängligt för reservation genom att tilldela ett förväntat datum.</span><span class="sxs-lookup"><span data-stu-id="cfa86-125">You might want to indicate when the blocked inventory is expected to become available for reservation by assigning an expected date.</span></span> <span data-ttu-id="cfa86-126">Om du väljer alternativet Förväntade inleveranser för lagerspärren som anges som standard när du skapar en spärr manuellt, kommer detta datum visas på den förväntade transaktionen.</span><span class="sxs-lookup"><span data-stu-id="cfa86-126">If the Expected receipts option is selected for the inventory blocking, as it is by default when you manually create a blocking, this date will appear on the expected transaction.</span></span>  
3. <span data-ttu-id="cfa86-127">Klicka på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="cfa86-127">Click **Save**.</span></span>

## <a name="remove-the-inventory-blocking"></a><span data-ttu-id="cfa86-128">Ta bort lagerspärren</span><span class="sxs-lookup"><span data-stu-id="cfa86-128">Remove the inventory blocking</span></span>
1. <span data-ttu-id="cfa86-129">Klicka på **Ta bort** i **åtgärdsfönstret**.</span><span class="sxs-lookup"><span data-stu-id="cfa86-129">On the **Action pane**, click **Delete**.</span></span>
2. <span data-ttu-id="cfa86-130">Klicka på **Ja**.</span><span class="sxs-lookup"><span data-stu-id="cfa86-130">Click **Yes**.</span></span>
3. <span data-ttu-id="cfa86-131">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="cfa86-131">Close the page.</span></span>

