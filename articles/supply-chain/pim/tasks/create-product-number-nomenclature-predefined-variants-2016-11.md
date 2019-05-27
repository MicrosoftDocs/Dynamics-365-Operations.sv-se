---
title: Skapa en produktnummernomenklatur för fördefinierade produktvarianter
description: Denna guide visar dig hur du skapar en produktnummernomenklatur för fördefinierade produktvarianter, samt hur du tilldelar denna till lämplig produktdimensionsgrupp.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, EcoResNomenclature, EcoResProductDimensionGroup
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 4b49e96677b94d5f669ea41861f64e62e118938c
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/15/2019
ms.locfileid: "1550593"
---
# <a name="create-a-product-number-nomenclature-for-predefined-product-variants"></a><span data-ttu-id="749b3-103">Skapa en produktnummernomenklatur för fördefinierade produktvarianter</span><span class="sxs-lookup"><span data-stu-id="749b3-103">Create a product number nomenclature for predefined product variants</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="749b3-104">Denna guide visar dig hur du skapar en produktnummernomenklatur för fördefinierade produktvarianter, samt hur du tilldelar denna till lämplig produktdimensionsgrupp.</span><span class="sxs-lookup"><span data-stu-id="749b3-104">This guide shows you how to set up a product number nomenclature for predefined product variants, and how you assign it to the appropriate product dimension group.</span></span> <span data-ttu-id="749b3-105">Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF.</span><span class="sxs-lookup"><span data-stu-id="749b3-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="749b3-106">Den nya produktnummernomenklaturen tilldelas till produktdimensionsgruppen Color and Size.</span><span class="sxs-lookup"><span data-stu-id="749b3-106">The new product number nomenclature is assigned to the Color and Size product dimension group.</span></span> <span data-ttu-id="749b3-107">Den här uppgiften utförs vanligtvis av en produktdesigner.</span><span class="sxs-lookup"><span data-stu-id="749b3-107">This task would typically be done by a product designer.</span></span>


## <a name="create-a-product-number-nomenclature"></a><span data-ttu-id="749b3-108">Skapa en nomenklatur för produktnummer</span><span class="sxs-lookup"><span data-stu-id="749b3-108">Create a product number nomenclature</span></span>
1. <span data-ttu-id="749b3-109">Klicka på Definition av produktvariantmodell.</span><span class="sxs-lookup"><span data-stu-id="749b3-109">Click Product variant model definition.</span></span>
2. <span data-ttu-id="749b3-110">Klicka på Product nomenclature.</span><span class="sxs-lookup"><span data-stu-id="749b3-110">Click Product nomenclature.</span></span>
3. <span data-ttu-id="749b3-111">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="749b3-111">Click New.</span></span>
4. <span data-ttu-id="749b3-112">I fältet Namn anger du ett nomenklatursnamn som gör det enkelt att identifiera målproduktdimensionsgruppen, till exempel ColorSize.</span><span class="sxs-lookup"><span data-stu-id="749b3-112">In the Name field, enter a nomenclature name that helps to identify the target product dimension group, for example, ColorSize..</span></span>
5. <span data-ttu-id="749b3-113">Ange ett värde i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="749b3-113">In the Description field, type a value.</span></span>
6. <span data-ttu-id="749b3-114">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="749b3-114">Click Add.</span></span>
7. <span data-ttu-id="749b3-115">Klicka på Product master number.</span><span class="sxs-lookup"><span data-stu-id="749b3-115">Click Product master number.</span></span>
8. <span data-ttu-id="749b3-116">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="749b3-116">Click Add.</span></span>
9. <span data-ttu-id="749b3-117">Klicka på Text constant.</span><span class="sxs-lookup"><span data-stu-id="749b3-117">Click Text constant.</span></span>
10. <span data-ttu-id="749b3-118">Skriv ett värde i fältet Text.</span><span class="sxs-lookup"><span data-stu-id="749b3-118">In the Text field, type a value.</span></span>
11. <span data-ttu-id="749b3-119">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="749b3-119">Click Add.</span></span>
12. <span data-ttu-id="749b3-120">Klicka på Color.</span><span class="sxs-lookup"><span data-stu-id="749b3-120">Click Color.</span></span>
13. <span data-ttu-id="749b3-121">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="749b3-121">Click Add.</span></span>
14. <span data-ttu-id="749b3-122">Klicka på Text constant.</span><span class="sxs-lookup"><span data-stu-id="749b3-122">Click Text constant.</span></span>
15. <span data-ttu-id="749b3-123">Skriv ett värde i fältet Text.</span><span class="sxs-lookup"><span data-stu-id="749b3-123">In the Text field, type a value.</span></span>
16. <span data-ttu-id="749b3-124">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="749b3-124">Click Add.</span></span>
17. <span data-ttu-id="749b3-125">Klicka på Size.</span><span class="sxs-lookup"><span data-stu-id="749b3-125">Click Size.</span></span>
18. <span data-ttu-id="749b3-126">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="749b3-126">Close the page.</span></span>

## <a name="assign-the-nomenclature-to-a-product-master"></a><span data-ttu-id="749b3-127">Tilldela nummernomenklaturen till en produktmall</span><span class="sxs-lookup"><span data-stu-id="749b3-127">Assign the nomenclature to a product master</span></span>
1. <span data-ttu-id="749b3-128">Klicka på Product dimension groups.</span><span class="sxs-lookup"><span data-stu-id="749b3-128">Click Product dimension groups.</span></span>
2. <span data-ttu-id="749b3-129">Välj produktdimensionsgruppen SizeCol.</span><span class="sxs-lookup"><span data-stu-id="749b3-129">Select the SizeCol product dimension group.</span></span>
3. <span data-ttu-id="749b3-130">Klicka på Redigera.</span><span class="sxs-lookup"><span data-stu-id="749b3-130">Click Edit.</span></span>
4. <span data-ttu-id="749b3-131">Välj Yes i fältet Use nomenclature.</span><span class="sxs-lookup"><span data-stu-id="749b3-131">Select Yes in the Use nomenclature field.</span></span>
5. <span data-ttu-id="749b3-132">I nomenklatursfältet Product variant number anger eller väljer du ett värde.</span><span class="sxs-lookup"><span data-stu-id="749b3-132">In the Product variant number nomenclature field, enter or select a value.</span></span>
6. <span data-ttu-id="749b3-133">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="749b3-133">Close the page.</span></span>

