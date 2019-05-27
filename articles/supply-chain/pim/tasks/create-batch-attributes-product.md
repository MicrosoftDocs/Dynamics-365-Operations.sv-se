---
title: Skapa batchattribut för en produkt
description: I den här proceduren visas hur du skapar ett batchattribut, tilldelar standardvärdeintervall och inkluderar attributet i en grupp.
author: ShylaThompson
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 65153dbcfa69046e4f38eb6ffa013bb6fb87ebd8
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/15/2019
ms.locfileid: "1568545"
---
# <a name="create-batch-attributes-for-a-product"></a><span data-ttu-id="5d2c5-103">Skapa batchattribut för en produkt</span><span class="sxs-lookup"><span data-stu-id="5d2c5-103">Create batch attributes for a product</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="5d2c5-104">I den här proceduren visas hur du skapar ett batchattribut, tilldelar standardvärdeintervall och inkluderar attributet i en grupp.</span><span class="sxs-lookup"><span data-stu-id="5d2c5-104">This procedure shows how to create a batch attribute, assign default value ranges, and include the attribute in a group.</span></span> <span data-ttu-id="5d2c5-105">Det demonstrationsdataföretag som används för att skapa den här proceduren är företaget USP2.</span><span class="sxs-lookup"><span data-stu-id="5d2c5-105">The demo data company used to create this procedure is the USP2 Company.</span></span>

1. <span data-ttu-id="5d2c5-106">Gå till Lagerhantering > Inställningar > Batch > Batchattribut.</span><span class="sxs-lookup"><span data-stu-id="5d2c5-106">Go to Inventory management > Setup > Batch > Batch attributes.</span></span>
2. <span data-ttu-id="5d2c5-107">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="5d2c5-107">Click New.</span></span>
3. <span data-ttu-id="5d2c5-108">Skriv ett värde i fältet Attribut.</span><span class="sxs-lookup"><span data-stu-id="5d2c5-108">In the Attribute field, type a value.</span></span>
4. <span data-ttu-id="5d2c5-109">Ange ett värde i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="5d2c5-109">In the Description field, type a value.</span></span>
5. <span data-ttu-id="5d2c5-110">Välj "Del" i fältet Attributtyp.</span><span class="sxs-lookup"><span data-stu-id="5d2c5-110">In the Attribute type field, select 'Fraction'.</span></span>
    * <span data-ttu-id="5d2c5-111">I den här proceduren används deltypen för att aktivera decimalvärden.</span><span class="sxs-lookup"><span data-stu-id="5d2c5-111">This procedure uses the Fraction type to enable decimal values.</span></span> <span data-ttu-id="5d2c5-112">Du kan välja andra attributtyper.</span><span class="sxs-lookup"><span data-stu-id="5d2c5-112">You can select other attribute types.</span></span> <span data-ttu-id="5d2c5-113">Om du väljer uppräkningstypen måste du ange värden i uppräkningslista, innan du kan ange ett värde i målfältet.</span><span class="sxs-lookup"><span data-stu-id="5d2c5-113">If you select the Enumeration type, you must enter values in the enumeration list before you can enter a value in the Target field.</span></span>  
6. <span data-ttu-id="5d2c5-114">Ange ett nummer i fältet Minimum.</span><span class="sxs-lookup"><span data-stu-id="5d2c5-114">In the Minimum field, enter a number.</span></span>
7. <span data-ttu-id="5d2c5-115">Ange ett nummer i fältet Maximum.</span><span class="sxs-lookup"><span data-stu-id="5d2c5-115">In the Maximum field, enter a number.</span></span>
8. <span data-ttu-id="5d2c5-116">Välj ett nummer i fältet Stegvis.</span><span class="sxs-lookup"><span data-stu-id="5d2c5-116">In the Increment field, enter a number.</span></span>
9. <span data-ttu-id="5d2c5-117">Skriv ett värde i fältet Mål.</span><span class="sxs-lookup"><span data-stu-id="5d2c5-117">In the Target field, type a value.</span></span>
10. <span data-ttu-id="5d2c5-118">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="5d2c5-118">Click Save.</span></span>
11. <span data-ttu-id="5d2c5-119">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="5d2c5-119">Close the page.</span></span>
12. <span data-ttu-id="5d2c5-120">Gå till Lagerhantering > Inställningar > Batch > Batchattributgrupper.</span><span class="sxs-lookup"><span data-stu-id="5d2c5-120">Go to Inventory management > Setup > Batch > Batch attribute groups.</span></span>
13. <span data-ttu-id="5d2c5-121">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="5d2c5-121">Click New.</span></span>
14. <span data-ttu-id="5d2c5-122">Skriv ett värde i fältet Attributgrupp.</span><span class="sxs-lookup"><span data-stu-id="5d2c5-122">In the Attribute group field, type a value.</span></span>
15. <span data-ttu-id="5d2c5-123">Ange ett värde i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="5d2c5-123">In the Description field, type a value.</span></span>
16. <span data-ttu-id="5d2c5-124">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="5d2c5-124">Click Save.</span></span>
17. <span data-ttu-id="5d2c5-125">Klicka på Gruppattribut.</span><span class="sxs-lookup"><span data-stu-id="5d2c5-125">Click Group attributes.</span></span>
18. <span data-ttu-id="5d2c5-126">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="5d2c5-126">Click New.</span></span>
19. <span data-ttu-id="5d2c5-127">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Attribut.</span><span class="sxs-lookup"><span data-stu-id="5d2c5-127">In the Attribute field, click the drop-down button to open the lookup.</span></span>
20. <span data-ttu-id="5d2c5-128">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="5d2c5-128">In the list, find and select the desired record.</span></span>
21. <span data-ttu-id="5d2c5-129">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="5d2c5-129">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="5d2c5-130">Ett attribut kan inkluderas i någon av grupperna.</span><span class="sxs-lookup"><span data-stu-id="5d2c5-130">An attribute can be included in any of the groups.</span></span>  
22. <span data-ttu-id="5d2c5-131">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="5d2c5-131">Click Save.</span></span>
23. <span data-ttu-id="5d2c5-132">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="5d2c5-132">Close the page.</span></span>

