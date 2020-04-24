---
title: Associera ett produktlivscykeltillstånd till en frisläppt produktmall
description: Nedan beskrivs proceduren för att tilldela ett livscykeltillstånd till en frisläppt produktmall och dess varianter.
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
ms.openlocfilehash: ab8c4e02a064fe84446fa54cc05b9a6a902c1860
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/02/2020
ms.locfileid: "3213157"
---
# <a name="assign-a-product-lifecycle-state-to-a-released-product-master"></a><span data-ttu-id="ac6ca-103">Associera ett produktlivscykeltillstånd till en frisläppt produktmall</span><span class="sxs-lookup"><span data-stu-id="ac6ca-103">Assign a product lifecycle state to a released product master</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="ac6ca-104">Nedan beskrivs proceduren för att tilldela ett livscykeltillstånd till en frisläppt produktmall och dess varianter.</span><span class="sxs-lookup"><span data-stu-id="ac6ca-104">This procedure shows how to assign a product lifecycle state to a released product master and its variants.</span></span> <span data-ttu-id="ac6ca-105">Förutsättning: Du behöver spela uppgiftsguiden ”skapa ett nytt tillstånd för produktlivscykel” först för att se till att minst ett produktlivscykeltillstånd skapas innan du kan spela upp den här uppgiftsguiden.</span><span class="sxs-lookup"><span data-stu-id="ac6ca-105">Prerequisite: You need to play the task guide "Create a new product lifecycle state" first to make sure that you have at least one product lifecycle state created before you can play this task guide.</span></span>


## <a name="find-a-released-product-master"></a><span data-ttu-id="ac6ca-106">Hitta den frisläppta produktmallen</span><span class="sxs-lookup"><span data-stu-id="ac6ca-106">Find a released product master</span></span>
1. <span data-ttu-id="ac6ca-107">Gå till Produktinformationshantering > Produkter > Frisläppta produkter.</span><span class="sxs-lookup"><span data-stu-id="ac6ca-107">Go to Product information management > Products > Released products.</span></span>
2. <span data-ttu-id="ac6ca-108">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="ac6ca-108">In the list, find and select the desired record.</span></span>

> [!NOTE]
> <span data-ttu-id="ac6ca-109">En produktmall har produktundertypen Produktmall.</span><span class="sxs-lookup"><span data-stu-id="ac6ca-109">A product master has the Product subtype Product master.</span></span>  

## <a name="update-the-lifecycle-state"></a><span data-ttu-id="ac6ca-110">Uppdatera livscykeltillståndet</span><span class="sxs-lookup"><span data-stu-id="ac6ca-110">Update the lifecycle state</span></span>
1. <span data-ttu-id="ac6ca-111">Klicka på Redigera.</span><span class="sxs-lookup"><span data-stu-id="ac6ca-111">Click Edit.</span></span>
2. <span data-ttu-id="ac6ca-112">Ange eller välj ett värde i fältet produktlivscykeltillstånd.</span><span class="sxs-lookup"><span data-stu-id="ac6ca-112">In the Product lifecycle state field, enter or select a value.</span></span>
3. <span data-ttu-id="ac6ca-113">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="ac6ca-113">Click Save.</span></span>
4. <span data-ttu-id="ac6ca-114">Klicka på Ja.</span><span class="sxs-lookup"><span data-stu-id="ac6ca-114">Click Yes.</span></span>

> [!NOTE]
> <span data-ttu-id="ac6ca-115">Om Ja väljs uppdateras även alla relaterade frisläppta produktvarianter som har samma ursprungliga tillstånd, eftersom frisläppt produktmall även uppdateras till det nya produktlivscykeltillståndet.</span><span class="sxs-lookup"><span data-stu-id="ac6ca-115">If Yes is selected, all the related released product variants that have the same original status as the released product master are also updated to the new product lifecycle state.</span></span> <span data-ttu-id="ac6ca-116">Om Nej är markerat kommer alla varianter behålla sina verkliga tillstånd.</span><span class="sxs-lookup"><span data-stu-id="ac6ca-116">If No is selected, all variants keep their actual state.</span></span> <span data-ttu-id="ac6ca-117">Varianter som har ett annat produktlivscykeltillstånd än den frisläppta produktmallen uppdateras inte.</span><span class="sxs-lookup"><span data-stu-id="ac6ca-117">Variants that have a different product lifecycle state from the released product master are not updated.</span></span>  

## <a name="verify-the-lifecycle-state-of-the-variants"></a><span data-ttu-id="ac6ca-118">Kontrollera livscykelstatus för varianterna</span><span class="sxs-lookup"><span data-stu-id="ac6ca-118">Verify the lifecycle state of the variants</span></span>
1. <span data-ttu-id="ac6ca-119">Klicka på Frisläppta produktvarianter.</span><span class="sxs-lookup"><span data-stu-id="ac6ca-119">Click Released product variants.</span></span>

> [!NOTE]
> <span data-ttu-id="ac6ca-120">Observera att alla varianter har ärvt det valda livscykeltillståndet från den frisläppt produktmallen.</span><span class="sxs-lookup"><span data-stu-id="ac6ca-120">Note that all variants have inherited the selected lifecycle state from the released product master.</span></span>  

2. <span data-ttu-id="ac6ca-121">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="ac6ca-121">In the list, mark the selected row.</span></span>
3. <span data-ttu-id="ac6ca-122">Ange eller välj ett värde i fältet produktlivscykeltillstånd.</span><span class="sxs-lookup"><span data-stu-id="ac6ca-122">In the Product lifecycle state field, enter or select a value.</span></span>

