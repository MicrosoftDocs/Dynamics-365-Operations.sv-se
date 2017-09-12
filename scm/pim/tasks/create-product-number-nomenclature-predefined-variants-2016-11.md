--- 
title: "Skapa ett produktnummer för fördefinierade produktvarianter"
description: "Denna guide visar dig hur du skapar en produktnummernomenklatur för fördefinierade produktvarianter, samt hur du tilldelar denna till lämplig produktdimensionsgrupp."
author: BibiSp
manager: AnnBe
ms.date: 09/26/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.author: bis
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 6294e4608b31c37aa713e3a7a2028b409b5a8366
ms.contentlocale: sv-se
ms.lasthandoff: 08/29/2017

---
# <a name="create-a-product-number-for-predefined-product-variants"></a><span data-ttu-id="2f0e1-103">Skapa ett produktnummer för fördefinierade produktvarianter</span><span class="sxs-lookup"><span data-stu-id="2f0e1-103">Create a product number for predefined product variants</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="2f0e1-104">Denna guide visar dig hur du skapar en produktnummernomenklatur för fördefinierade produktvarianter, samt hur du tilldelar denna till lämplig produktdimensionsgrupp.</span><span class="sxs-lookup"><span data-stu-id="2f0e1-104">This guide shows you how to set up a product number nomenclature for predefined product variants, and how you assign it to the appropriate product dimension group.</span></span> <span data-ttu-id="2f0e1-105">Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF.</span><span class="sxs-lookup"><span data-stu-id="2f0e1-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="2f0e1-106">Den nya produktnummernomenklaturen tilldelas till produktdimensionsgruppen Color and Size.</span><span class="sxs-lookup"><span data-stu-id="2f0e1-106">The new product number nomenclature is assigned to the Color and Size product dimension group.</span></span> <span data-ttu-id="2f0e1-107">Den här uppgiften utförs vanligtvis av en produktdesigner.</span><span class="sxs-lookup"><span data-stu-id="2f0e1-107">This task would typically be done by a product designer.</span></span>


## <a name="create-a-product-number-nomenclature"></a><span data-ttu-id="2f0e1-108">Skapa en nomenklatur för produktnummer</span><span class="sxs-lookup"><span data-stu-id="2f0e1-108">Create a product number nomenclature</span></span>
1. <span data-ttu-id="2f0e1-109">Klicka på Definition av produktvariantmodell.</span><span class="sxs-lookup"><span data-stu-id="2f0e1-109">Click Product variant model definition.</span></span>
2. <span data-ttu-id="2f0e1-110">Klicka på Product nomenclature.</span><span class="sxs-lookup"><span data-stu-id="2f0e1-110">Click Product nomenclature.</span></span>
3. <span data-ttu-id="2f0e1-111">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="2f0e1-111">Click New.</span></span>
4. <span data-ttu-id="2f0e1-112">I fältet Namn anger du ett nomenklatursnamn som gör det enkelt att identifiera målproduktdimensionsgruppen, till exempel ColorSize.</span><span class="sxs-lookup"><span data-stu-id="2f0e1-112">In the Name field, enter a nomenclature name that helps to identify the target product dimension group, for example, ColorSize..</span></span>
5. <span data-ttu-id="2f0e1-113">Ange ett värde i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="2f0e1-113">In the Description field, type a value.</span></span>
6. <span data-ttu-id="2f0e1-114">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="2f0e1-114">Click Add.</span></span>
7. <span data-ttu-id="2f0e1-115">Klicka på Product master number.</span><span class="sxs-lookup"><span data-stu-id="2f0e1-115">Click Product master number.</span></span>
8. <span data-ttu-id="2f0e1-116">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="2f0e1-116">Click Add.</span></span>
9. <span data-ttu-id="2f0e1-117">Klicka på Text constant.</span><span class="sxs-lookup"><span data-stu-id="2f0e1-117">Click Text constant.</span></span>
10. <span data-ttu-id="2f0e1-118">Skriv ett värde i fältet Text.</span><span class="sxs-lookup"><span data-stu-id="2f0e1-118">In the Text field, type a value.</span></span>
11. <span data-ttu-id="2f0e1-119">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="2f0e1-119">Click Add.</span></span>
12. <span data-ttu-id="2f0e1-120">Klicka på Color.</span><span class="sxs-lookup"><span data-stu-id="2f0e1-120">Click Color.</span></span>
13. <span data-ttu-id="2f0e1-121">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="2f0e1-121">Click Add.</span></span>
14. <span data-ttu-id="2f0e1-122">Klicka på Text constant.</span><span class="sxs-lookup"><span data-stu-id="2f0e1-122">Click Text constant.</span></span>
15. <span data-ttu-id="2f0e1-123">Skriv ett värde i fältet Text.</span><span class="sxs-lookup"><span data-stu-id="2f0e1-123">In the Text field, type a value.</span></span>
16. <span data-ttu-id="2f0e1-124">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="2f0e1-124">Click Add.</span></span>
17. <span data-ttu-id="2f0e1-125">Klicka på Size.</span><span class="sxs-lookup"><span data-stu-id="2f0e1-125">Click Size.</span></span>
18. <span data-ttu-id="2f0e1-126">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="2f0e1-126">Close the page.</span></span>

## <a name="assign-the-nomenclature-to-a-product-master"></a><span data-ttu-id="2f0e1-127">Tilldela nummernomenklaturen till en produktmall</span><span class="sxs-lookup"><span data-stu-id="2f0e1-127">Assign the nomenclature to a product master</span></span>
1. <span data-ttu-id="2f0e1-128">Klicka på Product dimension groups.</span><span class="sxs-lookup"><span data-stu-id="2f0e1-128">Click Product dimension groups.</span></span>
2. <span data-ttu-id="2f0e1-129">Välj produktdimensionsgruppen SizeCol.</span><span class="sxs-lookup"><span data-stu-id="2f0e1-129">Select the SizeCol product dimension group.</span></span>
3. <span data-ttu-id="2f0e1-130">Klicka på Redigera.</span><span class="sxs-lookup"><span data-stu-id="2f0e1-130">Click Edit.</span></span>
4. <span data-ttu-id="2f0e1-131">Välj Yes i fältet Use nomenclature.</span><span class="sxs-lookup"><span data-stu-id="2f0e1-131">Select Yes in the Use nomenclature field.</span></span>
5. <span data-ttu-id="2f0e1-132">I nomenklatursfältet Product variant number anger eller väljer du ett värde.</span><span class="sxs-lookup"><span data-stu-id="2f0e1-132">In the Product variant number nomenclature field, enter or select a value.</span></span>
6. <span data-ttu-id="2f0e1-133">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="2f0e1-133">Close the page.</span></span>


