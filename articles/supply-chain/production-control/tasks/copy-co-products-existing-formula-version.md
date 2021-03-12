---
title: Kopiera samprodukter från en befintlig formelversion
description: I den här proceduren visas hur du kopierar samprodukter från en befintlig formelversion till en annan formelversion för en frisläppt produkt.
author: ShylaThompson
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResProductDetailsExtended, BOMConsistOf, PmfFormulaCoBy, BOMRouteCopyDialog
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 0a16a6c8651b401dddfa47c0eb29efb0c3a49038
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "4981341"
---
# <a name="copy-co-products-from-an-existing-formula-version"></a><span data-ttu-id="a5928-103">Kopiera samprodukter från en befintlig formelversion</span><span class="sxs-lookup"><span data-stu-id="a5928-103">Copy co-products from an existing formula version</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="a5928-104">I den här proceduren visas hur du kopierar samprodukter från en befintlig formelversion till en annan formelversion för en frisläppt produkt.</span><span class="sxs-lookup"><span data-stu-id="a5928-104">This procedure shows how to copy co-products from an existing formula version to a different formula version for a released product.</span></span> <span data-ttu-id="a5928-105">Det är en förutsättning att det finns minst en formelversion som associeras med samprodukter.</span><span class="sxs-lookup"><span data-stu-id="a5928-105">It is a prerequisite that there is at least one formula version associated with co-products.</span></span> <span data-ttu-id="a5928-106">Demonstrationsdataföretaget USP2 används för att skapa den här proceduren.</span><span class="sxs-lookup"><span data-stu-id="a5928-106">The demo data company USP2 is used to create this procedure.</span></span>


## <a name="find-a-released-product"></a><span data-ttu-id="a5928-107">Sök efter en frisläppt produkt</span><span class="sxs-lookup"><span data-stu-id="a5928-107">Find a released product</span></span>
1. <span data-ttu-id="a5928-108">Gå till Frisläppta produkter.</span><span class="sxs-lookup"><span data-stu-id="a5928-108">Go to Released products.</span></span>
2. <span data-ttu-id="a5928-109">Klicka på Visa filter.</span><span class="sxs-lookup"><span data-stu-id="a5928-109">Click Show filters.</span></span>
    * <span data-ttu-id="a5928-110">Du håller på att lägga till fältet Produktionstyp i dialogrutan Filter.</span><span class="sxs-lookup"><span data-stu-id="a5928-110">You are about to add the field Production type in the filter dialog box.</span></span>  
3. <span data-ttu-id="a5928-111">Klicka på fältet Lägg till ett filter om du vill lägga till fältet Produktionstyp.</span><span class="sxs-lookup"><span data-stu-id="a5928-111">Click Add a filter field to add the field Production type.</span></span>
    * <span data-ttu-id="a5928-112">I nästa steg måste du manuellt ange Formel i fältet Produktiontyp innan du väljer Verkställ.</span><span class="sxs-lookup"><span data-stu-id="a5928-112">In the next step, you need to manually enter Formula in the Production type field before you select Apply.</span></span> <span data-ttu-id="a5928-113">Detta ställer in filtret i listan över frisläppta produkter.</span><span class="sxs-lookup"><span data-stu-id="a5928-113">This sets the filter on the list of released products.</span></span>  
4. <span data-ttu-id="a5928-114">Ange manuellt Formel i fältet Produktionstyp.</span><span class="sxs-lookup"><span data-stu-id="a5928-114">Manually enter Formula in the Production type field.</span></span>
5. <span data-ttu-id="a5928-115">Klicka på Verkställ.</span><span class="sxs-lookup"><span data-stu-id="a5928-115">Click Apply.</span></span>

## <a name="select-a-released-product"></a><span data-ttu-id="a5928-116">Välj en frisläppt produkt</span><span class="sxs-lookup"><span data-stu-id="a5928-116">Select a released product</span></span>
1. <span data-ttu-id="a5928-117">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="a5928-117">In the list, find and select the desired record.</span></span>
2. <span data-ttu-id="a5928-118">Klicka på Formelversioner.</span><span class="sxs-lookup"><span data-stu-id="a5928-118">Click Formula versions.</span></span>
    * <span data-ttu-id="a5928-119">I åtgärdsfönstret Teknik, klicka på Formelversioner.</span><span class="sxs-lookup"><span data-stu-id="a5928-119">On the Engineering Action Pane, click Formula versions.</span></span>  

## <a name="copy-co-products"></a><span data-ttu-id="a5928-120">Kopiera samprodukter</span><span class="sxs-lookup"><span data-stu-id="a5928-120">Copy co-products</span></span>
1. <span data-ttu-id="a5928-121">Klicka på Formelversion i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="a5928-121">On the Action Pane, click Formula version.</span></span>
2. <span data-ttu-id="a5928-122">Klicka på Samprodukter.</span><span class="sxs-lookup"><span data-stu-id="a5928-122">Click Co-products.</span></span>
3. <span data-ttu-id="a5928-123">Klicka på Kopiera.</span><span class="sxs-lookup"><span data-stu-id="a5928-123">Click Copy.</span></span>
4. <span data-ttu-id="a5928-124">Ange eller välj ett värde i fältet Artikelnummer.</span><span class="sxs-lookup"><span data-stu-id="a5928-124">In the Item number field, enter or select a value.</span></span>
5. <span data-ttu-id="a5928-125">I fältet Formelversion, ange eller välj ett värde.</span><span class="sxs-lookup"><span data-stu-id="a5928-125">In the Formula version field, enter or select a value.</span></span>
6. <span data-ttu-id="a5928-126">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="a5928-126">Click OK.</span></span>
7. <span data-ttu-id="a5928-127">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="a5928-127">Close the page.</span></span>

