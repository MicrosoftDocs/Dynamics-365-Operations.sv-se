---
title: Slutför grundläggande inställningar för en frisläppt produktmall
description: Det här avsnittet visar hur du slutför de basinställningar som krävs innan produktmallen kan användas i strukturversioner.
author: ShylaThompson
manager: tfehr
ms.date: 07/08/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResProductDetailsExtended, InventTableInventoryDimensionGroups, InventItemOrderSetup
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 8ac4ceeb3e21ab089eb16565bb6e38c7eb44be80
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "4437679"
---
# <a name="complete-basic-setup-of-a-released-product-master"></a><span data-ttu-id="742cd-103">Slutför grundläggande inställningar för en frisläppt produktmall</span><span class="sxs-lookup"><span data-stu-id="742cd-103">Complete basic setup of a released product master</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="742cd-104">Det här avsnittet visar hur du slutför de basinställningar som krävs innan produktmallen kan användas i strukturversioner.</span><span class="sxs-lookup"><span data-stu-id="742cd-104">This topic shows how to complete the minimum setup that is required before the product master can be used in BOM versions.</span></span>

<span data-ttu-id="742cd-105">Detta är den tredje proceduren utav åtta som förklarar hur du ställer upp kombinationer för dimensionsbaserad konfiguration.</span><span class="sxs-lookup"><span data-stu-id="742cd-105">This is the third procedure out of eight which explains how to build combinations for dimension-based configuration.</span></span> <span data-ttu-id="742cd-106">Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF.</span><span class="sxs-lookup"><span data-stu-id="742cd-106">The demo data company used to create this procedure is USMF.</span></span>

1. <span data-ttu-id="742cd-107">Gå till **Navigeringsfönster > Moduler > Produktinformationshantering > Produkter > Frisläppta produkter**.</span><span class="sxs-lookup"><span data-stu-id="742cd-107">Go to **Navigation pane > Modules > Product information management > Products > Released products**.</span></span>
2. <span data-ttu-id="742cd-108">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="742cd-108">In the list, find and select the desired record.</span></span> <span data-ttu-id="742cd-109">Välj den produktmall som har frisläppts i den andra proceduren.</span><span class="sxs-lookup"><span data-stu-id="742cd-109">Select the product master that you have released in the second procedure.</span></span> <span data-ttu-id="742cd-110">Den här produktmallen skapas med dimensionsbaserad konfigurationsteknik.</span><span class="sxs-lookup"><span data-stu-id="742cd-110">This product master is created with the dimension-based configuration technology.</span></span>  
3. <span data-ttu-id="742cd-111">Välj **Produkt** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="742cd-111">On the Action Pane, select **Product**.</span></span>
4. <span data-ttu-id="742cd-112">Välj **Dimensionsgrupper** för att öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="742cd-112">Select **Dimension groups** to open the drop dialog.</span></span>
5. <span data-ttu-id="742cd-113">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet **Lagringsdimensionsgrupp**.</span><span class="sxs-lookup"><span data-stu-id="742cd-113">In the **Storage dimension group** field, select the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="742cd-114">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="742cd-114">In the list, find and select the desired record.</span></span> <span data-ttu-id="742cd-115">Lagringsdimensionsgruppen avgör vilka lagringsdimensioner som används för produkttransaktion.</span><span class="sxs-lookup"><span data-stu-id="742cd-115">The storage dimension group determines which storage dimensions are used for product transaction.</span></span> <span data-ttu-id="742cd-116">Välj **Plats** för den här proceduren.</span><span class="sxs-lookup"><span data-stu-id="742cd-116">Select **Site** for this procedure.</span></span>  
7. <span data-ttu-id="742cd-117">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet **Spårningsdimensionsgrupp**.</span><span class="sxs-lookup"><span data-stu-id="742cd-117">In the **Tracking dimension group** field, select the drop-down button to open the lookup.</span></span>
8. <span data-ttu-id="742cd-118">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="742cd-118">In the list, find and select the desired record.</span></span> <span data-ttu-id="742cd-119">Spårningsdimensionsgruppen avgör vilka spårningsdimensioner som används för produkttransaktion.</span><span class="sxs-lookup"><span data-stu-id="742cd-119">The tracking dimension group determines which tracking dimensions are used for product transaction.</span></span> <span data-ttu-id="742cd-120">Välj **Ingen** för den här proceduren.</span><span class="sxs-lookup"><span data-stu-id="742cd-120">Select **None** for this procedure.</span></span>  
9. <span data-ttu-id="742cd-121">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="742cd-121">Click **OK**.</span></span>
10. <span data-ttu-id="742cd-122">Klicka på **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="742cd-122">Click **Edit**.</span></span>
11. <span data-ttu-id="742cd-123">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet **Artikelmodellgrupp**.</span><span class="sxs-lookup"><span data-stu-id="742cd-123">In the **Item model group** field, select the drop-down button to open the lookup.</span></span>
12. <span data-ttu-id="742cd-124">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="742cd-124">In the list, find and select the desired record.</span></span> <span data-ttu-id="742cd-125">Artikelmodellgrupper innehåller inställningar som bestämmer hur artiklar kontrolleras och hanteras för artikelinleveranser och artikelutleveranser.</span><span class="sxs-lookup"><span data-stu-id="742cd-125">Item model groups contain settings that determine how items are controlled and handled on item receipts and issues.</span></span> <span data-ttu-id="742cd-126">De bestämmer även hur artikelförbrukningen beräknas.</span><span class="sxs-lookup"><span data-stu-id="742cd-126">They also determine how item consumption is calculated.</span></span> <span data-ttu-id="742cd-127">Välj **FIFO** för den här proceduren.</span><span class="sxs-lookup"><span data-stu-id="742cd-127">Select **FIFO** for this procedure.</span></span>  
13. <span data-ttu-id="742cd-128">Expandera avsnittet **Hantera kostnader**.</span><span class="sxs-lookup"><span data-stu-id="742cd-128">Expand the **Manage costs** section.</span></span>
14. <span data-ttu-id="742cd-129">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet **Artikelgrupp**.</span><span class="sxs-lookup"><span data-stu-id="742cd-129">In the **Item group** field, select the drop-down button to open the lookup.</span></span>
15. <span data-ttu-id="742cd-130">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="742cd-130">In the list, find and select the desired record.</span></span> <span data-ttu-id="742cd-131">Artikelgrupper används för att hantera lager genom att dela upp lagerartiklar i grupper.</span><span class="sxs-lookup"><span data-stu-id="742cd-131">Item groups are used to manage inventory by dividing inventory items into groups.</span></span> <span data-ttu-id="742cd-132">Välj **CarAudio** för den här proceduren.</span><span class="sxs-lookup"><span data-stu-id="742cd-132">Select **CarAudio** for this procedure.</span></span>  
16. <span data-ttu-id="742cd-133">Klicka på **Plan** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="742cd-133">On the Action Pane, select **Plan**.</span></span>
17. <span data-ttu-id="742cd-134">Välj **Standardorderinställningar**.</span><span class="sxs-lookup"><span data-stu-id="742cd-134">Select **Default order settings**.</span></span>
18. <span data-ttu-id="742cd-135">Välj ett alternativ i fältet **Standardordertyp**.</span><span class="sxs-lookup"><span data-stu-id="742cd-135">In the **Default order type field**, select an option.</span></span> <span data-ttu-id="742cd-136">Välj **Produktion** om du vill ange att standardleveransalternativet för den här produktmall är att producera den.</span><span class="sxs-lookup"><span data-stu-id="742cd-136">Select **Production** to specify that the default supply option for this product master is to produce it.</span></span>  
19. <span data-ttu-id="742cd-137">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="742cd-137">Select **Save**.</span></span>
20. <span data-ttu-id="742cd-138">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="742cd-138">Close the page.</span></span>
21. <span data-ttu-id="742cd-139">Stäng formuläret **Information om frisläppt produkt**.</span><span class="sxs-lookup"><span data-stu-id="742cd-139">Close the **Released product details** form.</span></span>

