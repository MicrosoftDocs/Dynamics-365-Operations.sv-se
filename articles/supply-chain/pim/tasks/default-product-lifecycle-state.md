---
title: Skapa ett standardproduktlivscykeltillstånd
description: Den här proceduren visar hur du skapar produktlivscykelns standardtillstånd och hur du kopplar standardtillståndet till frisläppta produkter.
author: cvocph
manager: tfehr
ms.date: 12/05/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Operations
ms.search.region: Global
ms.author: conradv
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: dd346f338a14476960ab47db2e3013402f4c43af
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/02/2020
ms.locfileid: "3213180"
---
# <a name="create-a-default-product-lifecycle-state"></a><span data-ttu-id="0196b-103">Skapa ett standardproduktlivscykeltillstånd</span><span class="sxs-lookup"><span data-stu-id="0196b-103">Create a default product lifecycle state</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="0196b-104">Den här proceduren visar hur du skapar produktlivscykelns standardtillstånd och hur du kopplar standardtillståndet till frisläppta produkter.</span><span class="sxs-lookup"><span data-stu-id="0196b-104">This procedure shows how to create a default product lifecycle state as well as how to associate the default state with released products.</span></span>


## <a name="create-a-default-lifecycle-state"></a><span data-ttu-id="0196b-105">Skapa ett standardlivscykeltillstånd</span><span class="sxs-lookup"><span data-stu-id="0196b-105">Create a default lifecycle state</span></span>
1. <span data-ttu-id="0196b-106">Gå till Produktinformationshantering > Inställningar > produktlivscykeltillstånd.</span><span class="sxs-lookup"><span data-stu-id="0196b-106">Go to Product information management > Setup > Product lifecycle state.</span></span>
2. <span data-ttu-id="0196b-107">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="0196b-107">Click New.</span></span>
3. <span data-ttu-id="0196b-108">Ange ett värde i fältet Tillstånd.</span><span class="sxs-lookup"><span data-stu-id="0196b-108">In the State field, type a value.</span></span>
4. <span data-ttu-id="0196b-109">Välj Ja i standard när de frisläpps till fältet juridisk person.</span><span class="sxs-lookup"><span data-stu-id="0196b-109">Select Yes in the Default when released to legal entity field.</span></span>
5. <span data-ttu-id="0196b-110">Ange ett värde i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="0196b-110">In the Description field, type a value.</span></span>
6. <span data-ttu-id="0196b-111">Välj Nej i fältet Är aktiv för planering.</span><span class="sxs-lookup"><span data-stu-id="0196b-111">Select No in the Is active for planning field.</span></span>

> [!NOTE]
> <span data-ttu-id="0196b-112">Om en ny frisläppt produkt inte ska ingå i Huvudplanering väljer du Nej.</span><span class="sxs-lookup"><span data-stu-id="0196b-112">If a new released product should not be included in Master planning, select No.</span></span> <span data-ttu-id="0196b-113">Om den ska tas med i huvudplaneringen lämna kontrollen till standardvärdet Ja.</span><span class="sxs-lookup"><span data-stu-id="0196b-113">If it should be included in Master planning, leave the control at its default value Yes.</span></span>  

## <a name="create-a-new-released-product"></a><span data-ttu-id="0196b-114">Skapa en ny frisläppt produkt</span><span class="sxs-lookup"><span data-stu-id="0196b-114">Create a new released product</span></span>
1. <span data-ttu-id="0196b-115">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="0196b-115">Close the page.</span></span>
2. <span data-ttu-id="0196b-116">Gå till Produktinformationshantering > Produkter > Frisläppta produkter.</span><span class="sxs-lookup"><span data-stu-id="0196b-116">Go to Product information management > Products > Released products.</span></span>
3. <span data-ttu-id="0196b-117">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="0196b-117">Click New.</span></span>
4. <span data-ttu-id="0196b-118">Skriv ett värde i fältet Produktnummer.</span><span class="sxs-lookup"><span data-stu-id="0196b-118">In the Product number field, type a value.</span></span>
5. <span data-ttu-id="0196b-119">Skriv ett värde i fältet Produktnamn.</span><span class="sxs-lookup"><span data-stu-id="0196b-119">In the Product name field, type a value.</span></span>
6. <span data-ttu-id="0196b-120">Ange ett värde i fältet Söknamn.</span><span class="sxs-lookup"><span data-stu-id="0196b-120">In the Search name field, type a value.</span></span>
7. <span data-ttu-id="0196b-121">Ange eller välj ett värde i fältet Artikelmodellgrupp.</span><span class="sxs-lookup"><span data-stu-id="0196b-121">In the Item model group field, enter or select a value.</span></span>
8. <span data-ttu-id="0196b-122">Ange eller välj ett värde i fältet Artikelgrupp.</span><span class="sxs-lookup"><span data-stu-id="0196b-122">In the Item group field, enter or select a value.</span></span>
9. <span data-ttu-id="0196b-123">Ange eller välj ett värde i fältet Lagringsdimensionsgrupp.</span><span class="sxs-lookup"><span data-stu-id="0196b-123">In the Storage dimension group field, enter or select a value.</span></span>
10. <span data-ttu-id="0196b-124">Ange eller välj ett värde i fältet Spårningsdimensionsgrupp.</span><span class="sxs-lookup"><span data-stu-id="0196b-124">In the Tracking dimension group field, enter or select a value.</span></span>
11. <span data-ttu-id="0196b-125">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="0196b-125">Click OK.</span></span>

> [!NOTE]
> <span data-ttu-id="0196b-126">Produktlivscykelns standardläge är en global definition.</span><span class="sxs-lookup"><span data-stu-id="0196b-126">The default product lifecycle state is a global definition.</span></span>  

## <a name="change-the-product-to-an-active-state"></a><span data-ttu-id="0196b-127">Ändra produkten till ett aktivt tillstånd.</span><span class="sxs-lookup"><span data-stu-id="0196b-127">Change the product to an active state</span></span>
1. <span data-ttu-id="0196b-128">Ange eller välj ett värde i fältet produktlivscykeltillstånd.</span><span class="sxs-lookup"><span data-stu-id="0196b-128">In the Product lifecycle state field, enter or select a value.</span></span>

> [!NOTE]
> <span data-ttu-id="0196b-129">Anta att du har ställt in ett aktivt tillstånd, kan du nu välja det aktiva tillståndet så att produkten används i huvudplanering och beräkning av strukturlistenivå.</span><span class="sxs-lookup"><span data-stu-id="0196b-129">Assume that you have set up an active state, you can now select the active state to allow the product to be used in Master planning and BOM-level calculation.</span></span> <span data-ttu-id="0196b-130">Självklart lönar det sig bara om produkten har allt som krävs för konsekvent planering.</span><span class="sxs-lookup"><span data-stu-id="0196b-130">Obviously, this only makes sense if all the product details that are required for consistent planning are specified.</span></span>  

