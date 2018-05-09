--- 
title: "Skapa ett produktlivscykeltillstånd för att utesluta produkter från huvudplanering"
description: "Den här proceduren beskriver hur du skapar ett nytt livscykeltillstånd för produkt som exkluderar produkter från huvudplanering och strukturlistenivåberäkningen."
author: cvocph
manager: AnnBe
ms.date: 12/05/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.author: conradv
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 127bdf9ad1664f3ff8179075e7a3f78e39a5e1a2
ms.contentlocale: sv-se
ms.lasthandoff: 05/08/2018

---
# <a name="create-a-product-lifecycle-state-to-exclude-products-from-master-planning"></a><span data-ttu-id="f0935-103">Skapa ett produktlivscykeltillstånd för att utesluta produkter från huvudplanering</span><span class="sxs-lookup"><span data-stu-id="f0935-103">Create a product lifecycle state to exclude products from Master planning</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="f0935-104">Den här proceduren beskriver hur du skapar ett nytt livscykeltillstånd för produkt som exkluderar produkter från huvudplanering och strukturlistenivåberäkningen.</span><span class="sxs-lookup"><span data-stu-id="f0935-104">This procedure shows how to create a new product lifecycle state that excludes the products from Master planning and BOM-level calculation.</span></span>


## <a name="create-an-obsolete-state"></a><span data-ttu-id="f0935-105">Skapa ett föråldrat tillstånd</span><span class="sxs-lookup"><span data-stu-id="f0935-105">Create an obsolete state</span></span>
1. <span data-ttu-id="f0935-106">Gå till Produktinformationshantering > Inställningar > produktlivscykeltillstånd.</span><span class="sxs-lookup"><span data-stu-id="f0935-106">Go to Product information management > Setup > Product lifecycle state.</span></span>
2. <span data-ttu-id="f0935-107">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="f0935-107">Click New.</span></span>
3. <span data-ttu-id="f0935-108">Ange ett värde i fältet Tillstånd.</span><span class="sxs-lookup"><span data-stu-id="f0935-108">In the State field, type a value.</span></span>
4. <span data-ttu-id="f0935-109">Välj Nej i fältet Är aktiv för planering.</span><span class="sxs-lookup"><span data-stu-id="f0935-109">Select No in the Is active for planning field.</span></span>
5. <span data-ttu-id="f0935-110">Ange ett värde i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="f0935-110">In the Description field, type a value.</span></span>

## <a name="associate-the-obsolete-state-to-a-released-product"></a><span data-ttu-id="f0935-111">Koppla föråldrade tillståndet till frisläppt produkt</span><span class="sxs-lookup"><span data-stu-id="f0935-111">Associate the obsolete state to a released product</span></span>
1. <span data-ttu-id="f0935-112">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="f0935-112">Close the page.</span></span>
2. <span data-ttu-id="f0935-113">Gå till Produktinformationshantering > Produkter > Frisläppta produkter.</span><span class="sxs-lookup"><span data-stu-id="f0935-113">Go to Product information management > Products > Released products.</span></span>
3. <span data-ttu-id="f0935-114">Använd snabbfiltret för att söka efter poster.</span><span class="sxs-lookup"><span data-stu-id="f0935-114">Use the Quick Filter to find records.</span></span> <span data-ttu-id="f0935-115">Filtrera till exempel i fältet Söknamn med värdet "M00".</span><span class="sxs-lookup"><span data-stu-id="f0935-115">For example, filter on the Search name field with a value of 'M00'.</span></span>
4. <span data-ttu-id="f0935-116">Klicka på Redigera.</span><span class="sxs-lookup"><span data-stu-id="f0935-116">Click Edit.</span></span>
5. <span data-ttu-id="f0935-117">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="f0935-117">In the list, mark the selected row.</span></span>
6. <span data-ttu-id="f0935-118">Ange eller välj ett värde i fältet produktlivscykeltillstånd.</span><span class="sxs-lookup"><span data-stu-id="f0935-118">In the Product lifecycle state field, enter or select a value.</span></span>


