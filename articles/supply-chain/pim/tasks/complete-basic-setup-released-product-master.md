---
title: Slutför grundläggande inställningar för en frisläppt produktmall
description: I den här proceduren visas hur du slutför de basinställningar som krävs innan produktmallen kan användas i strukturversioner.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResProductDetailsExtended, InventTableInventoryDimensionGroups, InventItemOrderSetup
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 0d3a91977c38c0ce0f9fe114bec943c7cb32a5d4
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/15/2019
ms.locfileid: "1568785"
---
# <a name="complete-basic-setup-of-a-released-product-master"></a><span data-ttu-id="5da75-103">Slutför grundläggande inställningar för en frisläppt produktmall</span><span class="sxs-lookup"><span data-stu-id="5da75-103">Complete basic setup of a released product master</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="5da75-104">I den här proceduren visas hur du slutför de basinställningar som krävs innan produktmallen kan användas i strukturversioner.</span><span class="sxs-lookup"><span data-stu-id="5da75-104">This procedure shows how to complete the minimum setup that is required before the product master can be used in BOM versions.</span></span>

<span data-ttu-id="5da75-105">Detta är den tredje proceduren utav åtta som förklarar hur du ställer upp kombinationer för dimensionsbaserad konfiguration.</span><span class="sxs-lookup"><span data-stu-id="5da75-105">This is the third procedure out of eight which explains how to build combinations for dimension-based configuration.</span></span> <span data-ttu-id="5da75-106">Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF.</span><span class="sxs-lookup"><span data-stu-id="5da75-106">The demo data company used to create this procedure is USMF.</span></span>

1. <span data-ttu-id="5da75-107">Gå till Produktinformationshantering > Produkter > Frisläppta produkter.</span><span class="sxs-lookup"><span data-stu-id="5da75-107">Go to Product information management > Products > Released products.</span></span>
2. <span data-ttu-id="5da75-108">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="5da75-108">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="5da75-109">Välj den produktmall som har frisläppts i den andra proceduren.</span><span class="sxs-lookup"><span data-stu-id="5da75-109">Select the product master that you have released in the second procedure.</span></span> <span data-ttu-id="5da75-110">Den här produktmallen skapas med dimensionsbaserad konfigurationsteknik.</span><span class="sxs-lookup"><span data-stu-id="5da75-110">This product master is created with the dimension-based configuration technology.</span></span>  
3. <span data-ttu-id="5da75-111">Klicka på Produkt i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="5da75-111">On the Action Pane, click Product.</span></span>
4. <span data-ttu-id="5da75-112">Klicka på Dimensionsgrupper för att öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="5da75-112">Click Dimension groups to open the drop dialog.</span></span>
5. <span data-ttu-id="5da75-113">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Lagringsdimensionsgrupp.</span><span class="sxs-lookup"><span data-stu-id="5da75-113">In the Storage dimension group field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="5da75-114">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="5da75-114">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="5da75-115">Lagringsdimensionsgruppen avgör vilka lagringsdimensioner som används för produkttransaktion.</span><span class="sxs-lookup"><span data-stu-id="5da75-115">The storage dimension group determines which storage dimensions are used for product transaction.</span></span> <span data-ttu-id="5da75-116">Välj Plats för den här proceduren.</span><span class="sxs-lookup"><span data-stu-id="5da75-116">Select Site for this procedure.</span></span>  
7. <span data-ttu-id="5da75-117">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="5da75-117">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="5da75-118">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Spårningsdimensionsgrupp.</span><span class="sxs-lookup"><span data-stu-id="5da75-118">In the Tracking dimension group field, click the drop-down button to open the lookup.</span></span>
9. <span data-ttu-id="5da75-119">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="5da75-119">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="5da75-120">Spårningsdimensionsgruppen avgör vilka spårningsdimensioner som används för produkttransaktion.</span><span class="sxs-lookup"><span data-stu-id="5da75-120">The tracking dimension group determines which tracking dimensions are used for product transaction.</span></span> <span data-ttu-id="5da75-121">Välj Ingen för den här proceduren.</span><span class="sxs-lookup"><span data-stu-id="5da75-121">Select None for this procedure.</span></span>  
10. <span data-ttu-id="5da75-122">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="5da75-122">In the list, click the link in the selected row.</span></span>
11. <span data-ttu-id="5da75-123">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="5da75-123">Click OK.</span></span>
12. <span data-ttu-id="5da75-124">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="5da75-124">In the list, click the link in the selected row.</span></span>
13. <span data-ttu-id="5da75-125">Klicka på Redigera.</span><span class="sxs-lookup"><span data-stu-id="5da75-125">Click Edit.</span></span>
    * <span data-ttu-id="5da75-126">Öppna formuläret Information om frisläppt produkt om du vill fortsätta med inställningsuppgiften.</span><span class="sxs-lookup"><span data-stu-id="5da75-126">Open the Released product details form to continue the setup task.</span></span>  
14. <span data-ttu-id="5da75-127">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Artikelmodellgrupp.</span><span class="sxs-lookup"><span data-stu-id="5da75-127">In the Item model group field, click the drop-down button to open the lookup.</span></span>
15. <span data-ttu-id="5da75-128">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="5da75-128">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="5da75-129">Artikelmodellgrupper innehåller inställningar som bestämmer hur artiklar kontrolleras och hanteras för artikelinleveranser och artikelutleveranser.</span><span class="sxs-lookup"><span data-stu-id="5da75-129">Item model groups contain settings that determine how items are controlled and handled on item receipts and issues.</span></span> <span data-ttu-id="5da75-130">De bestämmer även hur artikelförbrukningen beräknas.</span><span class="sxs-lookup"><span data-stu-id="5da75-130">They also determine how item consumption is calculated.</span></span> <span data-ttu-id="5da75-131">Välj FIFO för den här proceduren.</span><span class="sxs-lookup"><span data-stu-id="5da75-131">Select   FIFO for this procedure.</span></span>  
16. <span data-ttu-id="5da75-132">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="5da75-132">In the list, click the link in the selected row.</span></span>
17. <span data-ttu-id="5da75-133">Visa eller dölj avsnittet Hantera kostnader.</span><span class="sxs-lookup"><span data-stu-id="5da75-133">Expand or collapse the Manage costs section.</span></span>
18. <span data-ttu-id="5da75-134">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Artikelgrupp.</span><span class="sxs-lookup"><span data-stu-id="5da75-134">In the Item group field, click the drop-down button to open the lookup.</span></span>
19. <span data-ttu-id="5da75-135">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="5da75-135">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="5da75-136">Artikelgrupper används för att hantera lager genom att dela upp lagerartiklar i grupper.</span><span class="sxs-lookup"><span data-stu-id="5da75-136">Item groups are used to manage inventory by dividing inventory items into groups.</span></span> <span data-ttu-id="5da75-137">Välj CarAudio för den här proceduren.</span><span class="sxs-lookup"><span data-stu-id="5da75-137">Select   CarAudio for this procedure.</span></span>  
20. <span data-ttu-id="5da75-138">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="5da75-138">In the list, click the link in the selected row.</span></span>
21. <span data-ttu-id="5da75-139">Klicka på Plan i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="5da75-139">On the Action Pane, click Plan.</span></span>
22. <span data-ttu-id="5da75-140">Visa standardorderinställningar.</span><span class="sxs-lookup"><span data-stu-id="5da75-140">Click Default order settings.</span></span>
23. <span data-ttu-id="5da75-141">Välj ett alternativ i fältet Standardordertyp.</span><span class="sxs-lookup"><span data-stu-id="5da75-141">In the Default order type field, select an option.</span></span>
    * <span data-ttu-id="5da75-142">Välj Produktion om du vill ange att standardleveransalternativet för den här produktmall är att producera den.</span><span class="sxs-lookup"><span data-stu-id="5da75-142">Select Production to specify that the default supply option for this product master is to produce it.</span></span>  
24. <span data-ttu-id="5da75-143">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="5da75-143">Close the page.</span></span>
25. <span data-ttu-id="5da75-144">Stäng formuläret Information om frisläppt produkt.</span><span class="sxs-lookup"><span data-stu-id="5da75-144">Close the Released product details form.</span></span>

