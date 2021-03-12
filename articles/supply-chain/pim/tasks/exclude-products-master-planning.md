---
title: Skapa ett produktlivscykeltillstånd för att utesluta produkter från huvudplanering
description: Den här proceduren beskriver hur du skapar ett nytt livscykeltillstånd för produkt som exkluderar produkter från huvudplanering och strukturlistenivåberäkningen.
author: cvocph
manager: tfehr
ms.date: 12/05/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 6bb18f876e7d279624f60f01c5fbf4e449e9ab27
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "4986889"
---
# <a name="create-a-product-lifecycle-state-to-exclude-products-from-master-planning"></a><span data-ttu-id="3cf0a-103">Skapa ett produktlivscykeltillstånd för att utesluta produkter från huvudplanering</span><span class="sxs-lookup"><span data-stu-id="3cf0a-103">Create a product lifecycle state to exclude products from Master planning</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="3cf0a-104">Den här proceduren beskriver hur du skapar ett nytt livscykeltillstånd för produkt som exkluderar produkter från huvudplanering och strukturlistenivåberäkningen.</span><span class="sxs-lookup"><span data-stu-id="3cf0a-104">This procedure shows how to create a new product lifecycle state that excludes the products from Master planning and BOM-level calculation.</span></span>


## <a name="create-an-obsolete-state"></a><span data-ttu-id="3cf0a-105">Skapa ett föråldrat tillstånd</span><span class="sxs-lookup"><span data-stu-id="3cf0a-105">Create an obsolete state</span></span>
1. <span data-ttu-id="3cf0a-106">Gå till Produktinformationshantering > Inställningar > produktlivscykeltillstånd.</span><span class="sxs-lookup"><span data-stu-id="3cf0a-106">Go to Product information management > Setup > Product lifecycle state.</span></span>
2. <span data-ttu-id="3cf0a-107">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="3cf0a-107">Click New.</span></span>
3. <span data-ttu-id="3cf0a-108">Ange ett värde i fältet Tillstånd.</span><span class="sxs-lookup"><span data-stu-id="3cf0a-108">In the State field, type a value.</span></span>
4. <span data-ttu-id="3cf0a-109">Välj Nej i fältet Är aktiv för planering.</span><span class="sxs-lookup"><span data-stu-id="3cf0a-109">Select No in the Is active for planning field.</span></span>
5. <span data-ttu-id="3cf0a-110">Ange ett värde i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="3cf0a-110">In the Description field, type a value.</span></span>

## <a name="associate-the-obsolete-state-to-a-released-product"></a><span data-ttu-id="3cf0a-111">Koppla föråldrade tillståndet till frisläppt produkt</span><span class="sxs-lookup"><span data-stu-id="3cf0a-111">Associate the obsolete state to a released product</span></span>
1. <span data-ttu-id="3cf0a-112">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="3cf0a-112">Close the page.</span></span>
2. <span data-ttu-id="3cf0a-113">Gå till Produktinformationshantering > Produkter > Frisläppta produkter.</span><span class="sxs-lookup"><span data-stu-id="3cf0a-113">Go to Product information management > Products > Released products.</span></span>
3. <span data-ttu-id="3cf0a-114">Använd snabbfiltret för att söka efter poster.</span><span class="sxs-lookup"><span data-stu-id="3cf0a-114">Use the Quick Filter to find records.</span></span> <span data-ttu-id="3cf0a-115">Filtrera till exempel i fältet Söknamn med värdet "M00".</span><span class="sxs-lookup"><span data-stu-id="3cf0a-115">For example, filter on the Search name field with a value of 'M00'.</span></span>
4. <span data-ttu-id="3cf0a-116">Klicka på Redigera.</span><span class="sxs-lookup"><span data-stu-id="3cf0a-116">Click Edit.</span></span>
5. <span data-ttu-id="3cf0a-117">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="3cf0a-117">In the list, mark the selected row.</span></span>
6. <span data-ttu-id="3cf0a-118">Ange eller välj ett värde i fältet produktlivscykeltillstånd.</span><span class="sxs-lookup"><span data-stu-id="3cf0a-118">In the Product lifecycle state field, enter or select a value.</span></span>

