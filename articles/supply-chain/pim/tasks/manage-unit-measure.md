---
title: Hantera måttenhet
description: I den här proceduren visas hur du definierar en måttenhet, anger översättningar för enheten och dess beskrivning och definierar konverteringsregler för relaterade enheter.
author: sorenva
manager: tfehr
ms.date: 07/08/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResProductMaintainWorkspace, EcoResProductOpenCasesFormPart, UnitOfMeasure, UnitOfMeasureReportingTranslation, UnitOfMeasureTranslation, UnitOfMeasureConversion, UnitOfMeasureConversionEditOrCreate, UnitOfMeasureLookup
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: sorenand
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a7f7e2220a8eca9f9bf45216491f606ef0a2eb18
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/02/2020
ms.locfileid: "3203559"
---
# <a name="manage-unit-of-measure"></a><span data-ttu-id="b17ac-103">Hantera måttenhet</span><span class="sxs-lookup"><span data-stu-id="b17ac-103">Manage unit of measure</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="b17ac-104">I den här proceduren visas hur du definierar en måttenhet, anger översättningar för enheten och dess beskrivning och definierar konverteringsregler för relaterade enheter.</span><span class="sxs-lookup"><span data-stu-id="b17ac-104">This procedure shows how to define a unit of measure, provide translations for the unit and it's description, and define conversion rules for related units.</span></span> <span data-ttu-id="b17ac-105">Du kan gå igenom den här proceduren med hjälp av demodata eller använda egna data.</span><span class="sxs-lookup"><span data-stu-id="b17ac-105">You can walk through this procedure using demo data, or using your own data.</span></span>

1. <span data-ttu-id="b17ac-106">Gå till **Navigeringsfönster > Moduler > Produktinformationshantering > Underhåll av frisläppt produkt**.</span><span class="sxs-lookup"><span data-stu-id="b17ac-106">Go to **Navigation pane > Modules > Product information management > Released product maintenance**.</span></span>
2. <span data-ttu-id="b17ac-107">Klicka på **Enheter**.</span><span class="sxs-lookup"><span data-stu-id="b17ac-107">Click **Units**.</span></span>

## <a name="create-a-unit-of-measure"></a><span data-ttu-id="b17ac-108">Skapa en måttenhet</span><span class="sxs-lookup"><span data-stu-id="b17ac-108">Create a unit of measure</span></span>
1. <span data-ttu-id="b17ac-109">Klicka på **Ny**.</span><span class="sxs-lookup"><span data-stu-id="b17ac-109">Click **New**.</span></span>
2. <span data-ttu-id="b17ac-110">Fältet **Enhet** anger du ett värde.</span><span class="sxs-lookup"><span data-stu-id="b17ac-110">In the **Unit** field, type a value.</span></span> <span data-ttu-id="b17ac-111">Ange ID eller symbolen som ska användas när du refererar till måttenheten.</span><span class="sxs-lookup"><span data-stu-id="b17ac-111">Enter the ID or symbol to use when referring to the unit of measure.</span></span>  
3. <span data-ttu-id="b17ac-112">I fältet **Beskrivning** anger du ett värde.</span><span class="sxs-lookup"><span data-stu-id="b17ac-112">In the **Description** field, type a value.</span></span> <span data-ttu-id="b17ac-113">Ange ett beskrivande namn för måttenheten i systemspråket.</span><span class="sxs-lookup"><span data-stu-id="b17ac-113">Enter a descriptive name for the unit of measure in the system language.</span></span>  
4. <span data-ttu-id="b17ac-114">Välj ett alternativ i fältet **Enhetsklass**.</span><span class="sxs-lookup"><span data-stu-id="b17ac-114">In the **Unit class** field, select an option.</span></span> <span data-ttu-id="b17ac-115">Enhetsklassen definierar vilken logisk gruppering, till exempel område, massa eller kvantitet som måttenheten ingår i.</span><span class="sxs-lookup"><span data-stu-id="b17ac-115">The unit class defines what logical grouping, such as area, mass, or quantity, the unit of measure is part of.</span></span>  
5. <span data-ttu-id="b17ac-116">Ange ett nummer i fältet **Decimalprecision**.</span><span class="sxs-lookup"><span data-stu-id="b17ac-116">In the **Decimal precision** field, enter a number.</span></span> <span data-ttu-id="b17ac-117">Ange antalet decimaler som den konverterade måttenheten måste avrundas till när en beräkning slutförs för måttenheten.</span><span class="sxs-lookup"><span data-stu-id="b17ac-117">Specify the number of decimals that the converted unit of measure must be rounded to when a calculation is completed for the unit of measure.</span></span>  
6. <span data-ttu-id="b17ac-118">Klicka på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="b17ac-118">Click **Save**.</span></span>

## <a name="define-unit-translations"></a><span data-ttu-id="b17ac-119">Definiera enhetsöversättningar</span><span class="sxs-lookup"><span data-stu-id="b17ac-119">Define unit translations</span></span>
1. <span data-ttu-id="b17ac-120">Klicka på **Enhetstexter** i **åtgärdsfönstret**.</span><span class="sxs-lookup"><span data-stu-id="b17ac-120">On the **Action pane**, click **Unit texts**.</span></span>
2. <span data-ttu-id="b17ac-121">Klicka på **Ny**.</span><span class="sxs-lookup"><span data-stu-id="b17ac-121">Click **New**.</span></span> <span data-ttu-id="b17ac-122">Använd enhettext om du vill skapa en översättning av ID:t eller en symbol som representerar måttenheten för användning på externa dokument i kund - eller leverantörsspecifika språk.</span><span class="sxs-lookup"><span data-stu-id="b17ac-122">Use unit text to create a translation of the ID or a symbol representing the unit of measure for use on external documents in customer- or vendor-specific languages.</span></span>  
3. <span data-ttu-id="b17ac-123">Ange eller välj ett värde i fältet **Språk**.</span><span class="sxs-lookup"><span data-stu-id="b17ac-123">In the **Language** field, enter or select a value.</span></span>
4. <span data-ttu-id="b17ac-124">Skriv ett värde i fältet **Text**.</span><span class="sxs-lookup"><span data-stu-id="b17ac-124">In the **Text** field, type a value.</span></span>
5. <span data-ttu-id="b17ac-125">Klicka på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="b17ac-125">Click **Save**.</span></span>
6. <span data-ttu-id="b17ac-126">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="b17ac-126">Close the page.</span></span>
7. <span data-ttu-id="b17ac-127">Klicka på **Översatta enhetsbeskrivningar** i **åtgärdsfönstret**.</span><span class="sxs-lookup"><span data-stu-id="b17ac-127">On the **Action pane**, click **Translated unit descriptions**.</span></span>
8. <span data-ttu-id="b17ac-128">Klicka på **Ny**.</span><span class="sxs-lookup"><span data-stu-id="b17ac-128">Click **New**.</span></span> <span data-ttu-id="b17ac-129">Definiera språkspecifika beskrivningar för måttenheten.</span><span class="sxs-lookup"><span data-stu-id="b17ac-129">Define language-specific descriptions for the unit of measure.</span></span>  
9. <span data-ttu-id="b17ac-130">Ange eller välj ett värde i fältet **Språk**.</span><span class="sxs-lookup"><span data-stu-id="b17ac-130">In the **Language** field, enter or select a value.</span></span>
10. <span data-ttu-id="b17ac-131">I fältet **Beskrivning** anger du ett värde.</span><span class="sxs-lookup"><span data-stu-id="b17ac-131">In the **Description** field, type a value.</span></span>
11. <span data-ttu-id="b17ac-132">Klicka på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="b17ac-132">Click **Save**.</span></span>
12. <span data-ttu-id="b17ac-133">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="b17ac-133">Close the page.</span></span>

## <a name="define-unit-conversion-rules"></a><span data-ttu-id="b17ac-134">Definiera enhetskonverteringsregler</span><span class="sxs-lookup"><span data-stu-id="b17ac-134">Define unit conversion rules</span></span>
1. <span data-ttu-id="b17ac-135">Klicka på **Enhetskonversationer** i **åtgärdsfönstret**.</span><span class="sxs-lookup"><span data-stu-id="b17ac-135">On the **Action pane**, click **Unit conversions**.</span></span> <span data-ttu-id="b17ac-136">Definiera regler för att konvertera måttenheten till och från andra enheter i den valda enhetsklassen.</span><span class="sxs-lookup"><span data-stu-id="b17ac-136">Define rules for converting the unit of measure to and from other units of measure in the selected unit class.</span></span>  
2. <span data-ttu-id="b17ac-137">Klicka på **Nytt** om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="b17ac-137">Click **New** to open the drop dialog.</span></span>
3. <span data-ttu-id="b17ac-138">Ange ett nummer i fältet **Faktor**.</span><span class="sxs-lookup"><span data-stu-id="b17ac-138">In the **Factor** field, enter a number.</span></span> <span data-ttu-id="b17ac-139">Konverteringsfaktor mellan Från enhet och Till enhet.</span><span class="sxs-lookup"><span data-stu-id="b17ac-139">Conversion factor between the From unit and the To unit.</span></span> <span data-ttu-id="b17ac-140">Till exempel är konverteringsfaktorn från centimeter till meter 100, eftersom det går 100 centimeter på en meter.</span><span class="sxs-lookup"><span data-stu-id="b17ac-140">For example, the conversion factor from centimeter to meter is 100 because there are 100 centimeters in one meter.</span></span>  
4. <span data-ttu-id="b17ac-141">Ange eller välj ett värde i fältet **Till enhet**.</span><span class="sxs-lookup"><span data-stu-id="b17ac-141">In the **To unit** field, enter or select a value.</span></span>
5. <span data-ttu-id="b17ac-142">Markera ett alternativ i fältet **Avrundning**.</span><span class="sxs-lookup"><span data-stu-id="b17ac-142">In the **Rounding** field, select an option.</span></span> <span data-ttu-id="b17ac-143">Definiera hur det konverterade värdet ska avrundas.</span><span class="sxs-lookup"><span data-stu-id="b17ac-143">Define how the converted value should be rounded.</span></span>  
6. <span data-ttu-id="b17ac-144">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="b17ac-144">Click **OK**.</span></span>
7. <span data-ttu-id="b17ac-145">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="b17ac-145">Close the page.</span></span>

