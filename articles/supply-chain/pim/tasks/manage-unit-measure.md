--- 
title: "Hantera måttenhet"
description: "I den här proceduren visas hur du definierar en måttenhet, anger översättningar för enheten och dess beskrivning och definierar konverteringsregler för relaterade enheter."
author: sorenva
manager: AnnBe
ms.date: 02/12/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: sorenand
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 1d98cbff30620256c9d13e7b4a90314db150e33e
ms.openlocfilehash: 49c2df35e03d1e633379eab49aea54a549cd3d62
ms.contentlocale: sv-se
ms.lasthandoff: 08/07/2018

---
# <a name="manage-unit-of-measure"></a><span data-ttu-id="320dc-103">Hantera måttenhet</span><span class="sxs-lookup"><span data-stu-id="320dc-103">Manage unit of measure</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="320dc-104">I den här proceduren visas hur du definierar en måttenhet, anger översättningar för enheten och dess beskrivning och definierar konverteringsregler för relaterade enheter.</span><span class="sxs-lookup"><span data-stu-id="320dc-104">This procedure shows how to define a unit of measure, provide translations for the unit and it's description, and define conversion rules for related units.</span></span> <span data-ttu-id="320dc-105">Du kan gå igenom den här proceduren med hjälp av demodata eller använda egna data.</span><span class="sxs-lookup"><span data-stu-id="320dc-105">You can walk through this procedure using demo data, or using your own data.</span></span>

1. <span data-ttu-id="320dc-106">Gå till Underhåll av frisläppt produkt.</span><span class="sxs-lookup"><span data-stu-id="320dc-106">Go to Released product maintenance.</span></span>
2. <span data-ttu-id="320dc-107">Klicka på Enheter.</span><span class="sxs-lookup"><span data-stu-id="320dc-107">Click Units.</span></span>

## <a name="create-a-unit-of-measure"></a><span data-ttu-id="320dc-108">Skapa en måttenhet</span><span class="sxs-lookup"><span data-stu-id="320dc-108">Create a unit of measure</span></span>
1. <span data-ttu-id="320dc-109">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="320dc-109">Click New.</span></span>
2. <span data-ttu-id="320dc-110">Skriv ett värde i fältet Enhet.</span><span class="sxs-lookup"><span data-stu-id="320dc-110">In the Unit field, type a value.</span></span>
    * <span data-ttu-id="320dc-111">Ange ID eller symbolen som ska användas när du refererar till måttenheten.</span><span class="sxs-lookup"><span data-stu-id="320dc-111">Enter the ID or symbol to use when referring to the unit of measure.</span></span>  
3. <span data-ttu-id="320dc-112">Ange ett värde i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="320dc-112">In the Description field, type a value.</span></span>
    * <span data-ttu-id="320dc-113">Ange ett beskrivande namn för måttenheten i systemspråket.</span><span class="sxs-lookup"><span data-stu-id="320dc-113">Enter a descriptive name for the unit of measure in the system language.</span></span>  
4. <span data-ttu-id="320dc-114">Välj ett alternativ i fältet Enhetsklass.</span><span class="sxs-lookup"><span data-stu-id="320dc-114">In the Unit class field, select an option.</span></span>
    * <span data-ttu-id="320dc-115">Enhetsklassen definierar vilken logisk gruppering, till exempel område, massa eller kvantitet som måttenheten ingår i.</span><span class="sxs-lookup"><span data-stu-id="320dc-115">The unit class defines what logical grouping, such as area, mass, or quantity, the unit of measure is part of.</span></span>  
5. <span data-ttu-id="320dc-116">Ange ett nummer i fältet Decimalprecision.</span><span class="sxs-lookup"><span data-stu-id="320dc-116">In the Decimal precision field, enter a number.</span></span>
    * <span data-ttu-id="320dc-117">Ange antalet decimaler som den konverterade måttenheten måste avrundas till när en beräkning slutförs för måttenheten.</span><span class="sxs-lookup"><span data-stu-id="320dc-117">Specify the number of decimals that the converted unit of measure must be rounded to when a calculation is completed for the unit of measure.</span></span>  
6. <span data-ttu-id="320dc-118">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="320dc-118">Click Save.</span></span>

## <a name="define-unit-translations"></a><span data-ttu-id="320dc-119">Definiera enhetsöversättningar</span><span class="sxs-lookup"><span data-stu-id="320dc-119">Define unit translations</span></span>
1. <span data-ttu-id="320dc-120">Klicka på Enhetstexter.</span><span class="sxs-lookup"><span data-stu-id="320dc-120">Click Unit texts.</span></span>
2. <span data-ttu-id="320dc-121">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="320dc-121">Click New.</span></span>
    * <span data-ttu-id="320dc-122">Använd enhettext om du vill skapa en översättning av ID:t eller en symbol som representerar måttenheten för användning på externa dokument i kund - eller leverantörsspecifika språk.</span><span class="sxs-lookup"><span data-stu-id="320dc-122">Use unit text to create a translation of the ID or a symbol representing the unit of measure for use on external documents in customer- or vendor-specific languages.</span></span>  
3. <span data-ttu-id="320dc-123">Ange eller välj ett värde i fältet Språk.</span><span class="sxs-lookup"><span data-stu-id="320dc-123">In the Language field, enter or select a value.</span></span>
4. <span data-ttu-id="320dc-124">Skriv ett värde i fältet Text.</span><span class="sxs-lookup"><span data-stu-id="320dc-124">In the Text field, type a value.</span></span>
5. <span data-ttu-id="320dc-125">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="320dc-125">Click Save.</span></span>
6. <span data-ttu-id="320dc-126">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="320dc-126">Close the page.</span></span>
7. <span data-ttu-id="320dc-127">Klicka på Översatta enhetsbeskrivningar.</span><span class="sxs-lookup"><span data-stu-id="320dc-127">Click Translated unit descriptions.</span></span>
8. <span data-ttu-id="320dc-128">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="320dc-128">Click New.</span></span>
    * <span data-ttu-id="320dc-129">Definiera språkspecifika beskrivningar för måttenheten.</span><span class="sxs-lookup"><span data-stu-id="320dc-129">Define language-specific descriptions for the unit of measure.</span></span>  
9. <span data-ttu-id="320dc-130">Ange eller välj ett värde i fältet Språk.</span><span class="sxs-lookup"><span data-stu-id="320dc-130">In the Language field, enter or select a value.</span></span>
10. <span data-ttu-id="320dc-131">Ange ett värde i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="320dc-131">In the Description field, type a value.</span></span>
11. <span data-ttu-id="320dc-132">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="320dc-132">Click Save.</span></span>
12. <span data-ttu-id="320dc-133">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="320dc-133">Close the page.</span></span>

## <a name="define-unit-conversion-rules"></a><span data-ttu-id="320dc-134">Definiera enhetskonverteringsregler</span><span class="sxs-lookup"><span data-stu-id="320dc-134">Define unit conversion rules</span></span>
1. <span data-ttu-id="320dc-135">Klicka på Enhetskonverteringar.</span><span class="sxs-lookup"><span data-stu-id="320dc-135">Click Unit conversions.</span></span>
    * <span data-ttu-id="320dc-136">Definiera regler för att konvertera måttenheten till och från andra enheter i den valda enhetsklassen.</span><span class="sxs-lookup"><span data-stu-id="320dc-136">Define rules for converting the unit of measure to and from other units of measure in the selected unit class.</span></span>  
2. <span data-ttu-id="320dc-137">Klicka på Nytt om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="320dc-137">Click New to open the drop dialog.</span></span>
3. <span data-ttu-id="320dc-138">Ange ett nummer i fältet Faktor.</span><span class="sxs-lookup"><span data-stu-id="320dc-138">In the Factor field, enter a number.</span></span>
    * <span data-ttu-id="320dc-139">Konverteringsfaktor mellan Från enhet och Till enhet.</span><span class="sxs-lookup"><span data-stu-id="320dc-139">Conversion factor between the From unit and the To unit.</span></span> <span data-ttu-id="320dc-140">Till exempel är konverteringsfaktorn från centimeter till meter 100, eftersom det går 100 centimeter på en meter.</span><span class="sxs-lookup"><span data-stu-id="320dc-140">For example, the conversion factor from centimeter to meter is 100 because there are 100 centimeters in one meter.</span></span>  
4. <span data-ttu-id="320dc-141">Ange eller välj ett värde i fältet Till enhet.</span><span class="sxs-lookup"><span data-stu-id="320dc-141">In the To unit field, enter or select a value.</span></span>
5. <span data-ttu-id="320dc-142">Markera ett alternativ i fältet Avrundning.</span><span class="sxs-lookup"><span data-stu-id="320dc-142">In the Rounding field, select an option.</span></span>
    * <span data-ttu-id="320dc-143">Definiera hur det konverterade värdet ska avrundas.</span><span class="sxs-lookup"><span data-stu-id="320dc-143">Define how the converted value should be rounded.</span></span>  
6. <span data-ttu-id="320dc-144">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="320dc-144">Click OK.</span></span>
7. <span data-ttu-id="320dc-145">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="320dc-145">Close the page.</span></span>


