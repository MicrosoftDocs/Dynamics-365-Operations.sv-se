---
title: Förbrukningsavskrivning
description: Den här avsnittet innehåller en översikt över förbrukningsmetoden för avskrivning.
author: ShylaThompson
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetDepreciationProfile
audience: Application User
ms.reviewer: roschlom
ms.custom: 13751
ms.assetid: d25a681f-49a5-4bfc-aa76-1c6373e35dd8
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 9a11389d1042eb62ed081d7615fea2f370de8255
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5827012"
---
# <a name="consumption-depreciation"></a><span data-ttu-id="11d45-103">Förbrukningsavskrivning</span><span class="sxs-lookup"><span data-stu-id="11d45-103">Consumption depreciation</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="11d45-104">Den här avsnittet innehåller en översikt över förbrukningsmetoden för avskrivning.</span><span class="sxs-lookup"><span data-stu-id="11d45-104">This article gives an overview of the Consumption method of depreciation.</span></span>

<span data-ttu-id="11d45-105">Om du ställer in en avskrivningsprofil för anläggningstillgångar och väljer **Förbrukning** i fältet **Metod** på sidan **Avskrivningsprofiler** tilldelas anläggningstillgångar till avskrivningsprofilen utifrån deras användning.</span><span class="sxs-lookup"><span data-stu-id="11d45-105">If you set up a depreciation profile for fixed assets and select **Consumption** in the **Method** field on the **Depreciation profiles** page, fixed assets are assigned to the depreciation profile based on their usage.</span></span> <span data-ttu-id="11d45-106">Det är inte nödvändigt att ställa in procenttal och intervaller på sidan **Avskrivningsprofiler**.</span><span class="sxs-lookup"><span data-stu-id="11d45-106">You don't have to set up percentages and intervals on the **Depreciation profiles** page.</span></span> <span data-ttu-id="11d45-107">När du har skapat en avskrivningsprofil som använder förbrukningsmetoden kan du ställa in metoden på olika sätt.</span><span class="sxs-lookup"><span data-stu-id="11d45-107">After you create a depreciation profile that uses the Consumption method, you can set up the method in various ways.</span></span>

## <a name="set-up-and-use-consumption-depreciation"></a><span data-ttu-id="11d45-108">Ställa in och använda förbrukningsavskrivning</span><span class="sxs-lookup"><span data-stu-id="11d45-108">Set up and use consumption depreciation</span></span>
1.  <span data-ttu-id="11d45-109">Skapa avskrivningsprofilen på sidan **Avskrivningsprofiler**.</span><span class="sxs-lookup"><span data-stu-id="11d45-109">On the **Depreciation profiles** page, create the depreciation profile.</span></span> <span data-ttu-id="11d45-110">För förbrukningsberäkningar måste avskrivningsprofilen ha ett ID och ett namn, och **Förbrukning** måste väljas i fältet **Metod**.</span><span class="sxs-lookup"><span data-stu-id="11d45-110">For consumption calculations, the depreciation profile must have an ID and a name, and **Consumption** must be selected in the **Method** field.</span></span>
2.  <span data-ttu-id="11d45-111">På sidan **Förbrukningsfaktorer** ställer du in förbrukningsfaktorer.</span><span class="sxs-lookup"><span data-stu-id="11d45-111">On the **Consumption factors** page, set up consumption factors.</span></span> <span data-ttu-id="11d45-112">Varje förbrukningsfaktor måste ha ett ID och ett namn och en förbrukningsfaktor som anges som antingen en kvantitet eller ett procenttal.</span><span class="sxs-lookup"><span data-stu-id="11d45-112">Each consumption factor must have an ID and a name, and a consumption factor that is specified as either a quantity or a percentage.</span></span>
3.  <span data-ttu-id="11d45-113">På sidan **Förbrukningsenheter** ställer du in förbrukningsenheter.</span><span class="sxs-lookup"><span data-stu-id="11d45-113">On the **Consumption units** page, set up consumption units.</span></span> <span data-ttu-id="11d45-114">Varje förbrukningsenhet måste ha ett ID och ett namn.</span><span class="sxs-lookup"><span data-stu-id="11d45-114">Each consumption unit must have an ID and a name.</span></span> <span data-ttu-id="11d45-115">Avskrivningsenheter används för att beräkna förbrukningsavskrivningen på sidan **Förbrukningsavskrivning**.</span><span class="sxs-lookup"><span data-stu-id="11d45-115">Depreciation units are used to calculate consumption depreciation on the **Consumption depreciation** page.</span></span> <span data-ttu-id="11d45-116">Exempel på enheter är kilometer (km), kilo (kg) och timme.</span><span class="sxs-lookup"><span data-stu-id="11d45-116">Examples of units are kilometer (km), kilogram (kg), and hour.</span></span>
4.  <span data-ttu-id="11d45-117">På sidan **Anläggningstillgångar** ställer du in enskilda anläggningstillgångar.</span><span class="sxs-lookup"><span data-stu-id="11d45-117">On the **Fixed assets** page, set up individual fixed assets.</span></span> <span data-ttu-id="11d45-118">För varje anläggningstillgång väljer du värdemodeller och avskrivningsregler som har avskrivningsprofiler.</span><span class="sxs-lookup"><span data-stu-id="11d45-118">For each fixed asset, select value models and depreciation books that have depreciation profiles.</span></span> <span data-ttu-id="11d45-119">Du måste ställa in värdemodeller och avskrivningsregler för förbrukningsavskrivning om vissa av dina anläggningstillgångar använder avskrivningsprofiler som baseras på förbrukningsmetoden.</span><span class="sxs-lookup"><span data-stu-id="11d45-119">You must set up value models or depreciation books for consumption depreciation if any of your fixed assets use depreciation profiles that are based on the Consumption method.</span></span> <span data-ttu-id="11d45-120">Den här inställningen görs antingen på fliken **Avskrivning** på sidan **Värdemodeller** eller på snabbfliken **Allmänt** på sidan **Avskrivningsprofil**.</span><span class="sxs-lookup"><span data-stu-id="11d45-120">This setup is done either on the **Depreciation** tab of the **Value models** page or on the **General** FastTab of the **Depreciation profile** page.</span></span> <span data-ttu-id="11d45-121">Du kan använda samma värdemodell för flera anläggningstillgångar.</span><span class="sxs-lookup"><span data-stu-id="11d45-121">You can use the same value model for multiple fixed assets.</span></span> <span data-ttu-id="11d45-122">Avskrivningsprofiler är en del av värdemodellen eller avskrivningsregeln som du väljer för varje anläggningstillgång.</span><span class="sxs-lookup"><span data-stu-id="11d45-122">Depreciation profiles are part of the value model or depreciation book that you select for each fixed asset.</span></span> <span data-ttu-id="11d45-123">Du kan inte lägga till eller ändra avskrivningsprofiler direkt på sidan **Anläggningstillgångar**.</span><span class="sxs-lookup"><span data-stu-id="11d45-123">You can't add or modify depreciation profiles directly on the **Fixed assets** page.</span></span> <span data-ttu-id="11d45-124">Du kan endast ändra avskrivningsprofiler på sidan **Avskrivningsregler**.</span><span class="sxs-lookup"><span data-stu-id="11d45-124">You can modify depreciation profiles only on the **Depreciation books** page.</span></span>
5.  <span data-ttu-id="11d45-125">Ange information i följande fält på sidan **Värdemodeller** eller sidan **Avskrivningsregler**, i fältgruppen **Förbrukningsavskrivning**:</span><span class="sxs-lookup"><span data-stu-id="11d45-125">On the **Value models** page or the **Depreciation books** page, in the **Consumption depreciation** field group, enter information in the following fields:</span></span>
    -   <span data-ttu-id="11d45-126">Förbrukningsfaktor</span><span class="sxs-lookup"><span data-stu-id="11d45-126">Consumption factor</span></span>
    -   <span data-ttu-id="11d45-127">Enhet</span><span class="sxs-lookup"><span data-stu-id="11d45-127">Unit</span></span>
    -   <span data-ttu-id="11d45-128">Enhetsavskrivning</span><span class="sxs-lookup"><span data-stu-id="11d45-128">Unit depreciation</span></span>
    -   <span data-ttu-id="11d45-129">Uppskattad förbrukning</span><span class="sxs-lookup"><span data-stu-id="11d45-129">Estimated consumption</span></span>

    <span data-ttu-id="11d45-130">Fältet **Bokförd förbrukning** visar förbrukningsavskrivningen, i enheter, som redan har bokförts antingen för kombinationen av anläggningstillgången och värdemodellen eller för avskrivningsregeln.</span><span class="sxs-lookup"><span data-stu-id="11d45-130">The **Posted consumption** field shows the consumption depreciation, in units, that has already been posted either for the combination of the fixed asset and value model, or for the depreciation book.</span></span> <span data-ttu-id="11d45-131">Du kan inte att uppdatera värdet i det här fältet.</span><span class="sxs-lookup"><span data-stu-id="11d45-131">You can't manually update the value in this field.</span></span>

## <a name="examples"></a><span data-ttu-id="11d45-132">Exempel</span><span class="sxs-lookup"><span data-stu-id="11d45-132">Examples</span></span>
### <a name="example-1"></a><span data-ttu-id="11d45-133">Exempel 1</span><span class="sxs-lookup"><span data-stu-id="11d45-133">Example 1</span></span>

<span data-ttu-id="11d45-134">Följande förbrukningsfaktor är inställd för 31 januari:</span><span class="sxs-lookup"><span data-stu-id="11d45-134">The following consumption factor is set up for January 31:</span></span>

-   <span data-ttu-id="11d45-135">Kvantiteten är 1 000.</span><span class="sxs-lookup"><span data-stu-id="11d45-135">The quantity is 1,000.</span></span>
-   <span data-ttu-id="11d45-136">Enhetsavskrivningspriset som anges för anläggningstillgången är 1,5.</span><span class="sxs-lookup"><span data-stu-id="11d45-136">The unit depreciation price that is specified for the fixed asset is 1.5.</span></span>

<span data-ttu-id="11d45-137">Avskrivningsförslaget den 31 januari är som följer: Kvantitet × Enhetsavskrivning 1 000 × 1,5 = 1 500 Om faktorn som anges för anläggningstillgången är en procentfaktor, multipliceras kvantiteten som beräknas i fältet **Uppskattad förbrukning** för värdemodellen för anläggningstillgång med procenttalet som har ställts in för det valda slutdatumet.</span><span class="sxs-lookup"><span data-stu-id="11d45-137">The depreciation proposal on January 31 is as follows: Quantity × Unit depreciation 1,000 × 1.5 = 1,500 If the factor that is specified for the fixed asset is a percentage factor, the quantity that is estimated in the **Estimated consumption** field for the value model of the fixed asset is multiplied by the percentage that is set up for the selected end date.</span></span> <span data-ttu-id="11d45-138">Den resulterande kvantiteten föreslås sedan som avskrivningskvantitet för perioden.</span><span class="sxs-lookup"><span data-stu-id="11d45-138">The resulting quantity is then suggested as the depreciation quantity for the period.</span></span>

### <a name="example-2"></a><span data-ttu-id="11d45-139">Exempel 2</span><span class="sxs-lookup"><span data-stu-id="11d45-139">Example 2</span></span>

<span data-ttu-id="11d45-140">Följande faktor för förbrukningsavskrivning är inställd för 31 januari:</span><span class="sxs-lookup"><span data-stu-id="11d45-140">The following factor for consumption depreciation is set up for January 31:</span></span>

-   <span data-ttu-id="11d45-141">Procenttalet är 10 procent.</span><span class="sxs-lookup"><span data-stu-id="11d45-141">The percentage is 10 percent.</span></span>
-   <span data-ttu-id="11d45-142">Enhetsavskrivningspriset som anges för anläggningstillgången är 1,5.</span><span class="sxs-lookup"><span data-stu-id="11d45-142">The unit depreciation price that is specified for the fixed asset is 1.5.</span></span>
-   <span data-ttu-id="11d45-143">Den uppskattade kvantiteten för anläggningstillgången är 2 000.</span><span class="sxs-lookup"><span data-stu-id="11d45-143">The estimated quantity of the fixed asset is 2,000.</span></span>

<span data-ttu-id="11d45-144">Avskrivningsförslaget den 31 januari är som följer: Beräknad kvantitet × Procent × Enhetsavskrivning 2 000 × 0,10 × 1,5 = 300</span><span class="sxs-lookup"><span data-stu-id="11d45-144">The depreciation proposal on January 31 is as follows: Estimated quantity × Percentage × Unit depreciation 2,000 × .10 × 1.5 = 300</span></span>





[!INCLUDE[footer-include](../../includes/footer-banner.md)]