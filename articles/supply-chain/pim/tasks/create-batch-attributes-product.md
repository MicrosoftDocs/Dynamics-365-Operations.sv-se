---
title: Skapa batchattribut för en produkt
description: I den här proceduren visas hur du skapar ett batchattribut, tilldelar standardvärdeintervall och inkluderar attributet i en grupp.
author: ShylaThompson
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: PdsBatchAttrib
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5deb35028ee499633fb6b0bb5155df2fd91e643a
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5820116"
---
# <a name="create-batch-attributes-for-a-product"></a><span data-ttu-id="ce311-103">Skapa batchattribut för en produkt</span><span class="sxs-lookup"><span data-stu-id="ce311-103">Create batch attributes for a product</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="ce311-104">I den här proceduren visas hur du skapar ett batchattribut, tilldelar standardvärdeintervall och inkluderar attributet i en grupp.</span><span class="sxs-lookup"><span data-stu-id="ce311-104">This procedure shows how to create a batch attribute, assign default value ranges, and include the attribute in a group.</span></span> <span data-ttu-id="ce311-105">Det demonstrationsdataföretag som används för att skapa den här proceduren är företaget USP2.</span><span class="sxs-lookup"><span data-stu-id="ce311-105">The demo data company used to create this procedure is the USP2 Company.</span></span>

1. <span data-ttu-id="ce311-106">Gå till Lagerhantering > Inställningar > Batch > Batchattribut.</span><span class="sxs-lookup"><span data-stu-id="ce311-106">Go to Inventory management > Setup > Batch > Batch attributes.</span></span>
2. <span data-ttu-id="ce311-107">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="ce311-107">Click New.</span></span>
3. <span data-ttu-id="ce311-108">Skriv ett värde i fältet Attribut.</span><span class="sxs-lookup"><span data-stu-id="ce311-108">In the Attribute field, type a value.</span></span>
4. <span data-ttu-id="ce311-109">Ange ett värde i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="ce311-109">In the Description field, type a value.</span></span>
5. <span data-ttu-id="ce311-110">Välj "Del" i fältet Attributtyp.</span><span class="sxs-lookup"><span data-stu-id="ce311-110">In the Attribute type field, select 'Fraction'.</span></span>
    * <span data-ttu-id="ce311-111">I den här proceduren används deltypen för att aktivera decimalvärden.</span><span class="sxs-lookup"><span data-stu-id="ce311-111">This procedure uses the Fraction type to enable decimal values.</span></span> <span data-ttu-id="ce311-112">Du kan välja andra attributtyper.</span><span class="sxs-lookup"><span data-stu-id="ce311-112">You can select other attribute types.</span></span> <span data-ttu-id="ce311-113">Om du väljer uppräkningstypen måste du ange värden i uppräkningslista, innan du kan ange ett värde i målfältet.</span><span class="sxs-lookup"><span data-stu-id="ce311-113">If you select the Enumeration type, you must enter values in the enumeration list before you can enter a value in the Target field.</span></span>  
6. <span data-ttu-id="ce311-114">Ange ett nummer i fältet Minimum.</span><span class="sxs-lookup"><span data-stu-id="ce311-114">In the Minimum field, enter a number.</span></span>
7. <span data-ttu-id="ce311-115">Ange ett nummer i fältet Maximum.</span><span class="sxs-lookup"><span data-stu-id="ce311-115">In the Maximum field, enter a number.</span></span>
8. <span data-ttu-id="ce311-116">Välj ett nummer i fältet Stegvis.</span><span class="sxs-lookup"><span data-stu-id="ce311-116">In the Increment field, enter a number.</span></span>
9. <span data-ttu-id="ce311-117">Skriv ett värde i fältet Mål.</span><span class="sxs-lookup"><span data-stu-id="ce311-117">In the Target field, type a value.</span></span>
10. <span data-ttu-id="ce311-118">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="ce311-118">Click Save.</span></span>
11. <span data-ttu-id="ce311-119">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="ce311-119">Close the page.</span></span>
12. <span data-ttu-id="ce311-120">Gå till Lagerhantering > Inställningar > Batch > Batchattributgrupper.</span><span class="sxs-lookup"><span data-stu-id="ce311-120">Go to Inventory management > Setup > Batch > Batch attribute groups.</span></span>
13. <span data-ttu-id="ce311-121">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="ce311-121">Click New.</span></span>
14. <span data-ttu-id="ce311-122">Skriv ett värde i fältet Attributgrupp.</span><span class="sxs-lookup"><span data-stu-id="ce311-122">In the Attribute group field, type a value.</span></span>
15. <span data-ttu-id="ce311-123">Ange ett värde i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="ce311-123">In the Description field, type a value.</span></span>
16. <span data-ttu-id="ce311-124">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="ce311-124">Click Save.</span></span>
17. <span data-ttu-id="ce311-125">Klicka på Gruppattribut.</span><span class="sxs-lookup"><span data-stu-id="ce311-125">Click Group attributes.</span></span>
18. <span data-ttu-id="ce311-126">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="ce311-126">Click New.</span></span>
19. <span data-ttu-id="ce311-127">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Attribut.</span><span class="sxs-lookup"><span data-stu-id="ce311-127">In the Attribute field, click the drop-down button to open the lookup.</span></span>
20. <span data-ttu-id="ce311-128">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="ce311-128">In the list, find and select the desired record.</span></span>
21. <span data-ttu-id="ce311-129">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="ce311-129">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="ce311-130">Ett attribut kan inkluderas i någon av grupperna.</span><span class="sxs-lookup"><span data-stu-id="ce311-130">An attribute can be included in any of the groups.</span></span>  
22. <span data-ttu-id="ce311-131">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="ce311-131">Click Save.</span></span>
23. <span data-ttu-id="ce311-132">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="ce311-132">Close the page.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]