--- 
title: Skapa en ny produkt
description: "Den här uppgiften visar hur du skapar en ny delad produkt."
author: BibiSp
manager: AnnBe
ms.date: 06/08/2016
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
ms.openlocfilehash: d9307abf5e9543c8a2c880330c4430f5e4c5b340
ms.contentlocale: sv-se
ms.lasthandoff: 08/29/2017

---
# <a name="create-a-new-product"></a><span data-ttu-id="eb733-103">Skapa en ny produkt</span><span class="sxs-lookup"><span data-stu-id="eb733-103">Create a new product</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="eb733-104">Den här uppgiften visar hur du skapar en ny delad produkt.</span><span class="sxs-lookup"><span data-stu-id="eb733-104">This task shows how to create a new shared product.</span></span> <span data-ttu-id="eb733-105">Den utförs vanligtvis av en produktdesigner.</span><span class="sxs-lookup"><span data-stu-id="eb733-105">It is usually carried out by a product designer.</span></span> <span data-ttu-id="eb733-106">Det demonstrationsdataföretag som används för att skapa den här uppgiften är USMF.</span><span class="sxs-lookup"><span data-stu-id="eb733-106">The demo data company used to create this task is USMF.</span></span>

1. <span data-ttu-id="eb733-107">Gå till Hantering av produktinformation > Produkter > Produkter.</span><span class="sxs-lookup"><span data-stu-id="eb733-107">Go to Product information management > Products > Products.</span></span>

## <a name="create-a-product"></a><span data-ttu-id="eb733-108">Skapa en produkt</span><span class="sxs-lookup"><span data-stu-id="eb733-108">Create a product</span></span>
1. <span data-ttu-id="eb733-109">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="eb733-109">Click New.</span></span>
2. <span data-ttu-id="eb733-110">Skriv ett värde i fältet Produktnummer.</span><span class="sxs-lookup"><span data-stu-id="eb733-110">In the Product number field, type a value.</span></span>
    * <span data-ttu-id="eb733-111">Om en nummerserie inte har ställts in för den produktnumret, måste den anges manuellt.</span><span class="sxs-lookup"><span data-stu-id="eb733-111">If a number sequence has not been set up for the product number, it must be entered manually.</span></span>  
3. <span data-ttu-id="eb733-112">Skriv ett värde i fältet Produktnamn.</span><span class="sxs-lookup"><span data-stu-id="eb733-112">In the Product name field, type a value.</span></span>
    * <span data-ttu-id="eb733-113">Produktnamnet anges som standard till söknamnet.</span><span class="sxs-lookup"><span data-stu-id="eb733-113">The product name defaults to the search name.</span></span> <span data-ttu-id="eb733-114">Du kan ändra detta om det behövs.</span><span class="sxs-lookup"><span data-stu-id="eb733-114">You can change this if needed.</span></span>  
4. <span data-ttu-id="eb733-115">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="eb733-115">Click OK.</span></span>

## <a name="set-up-dimension-groups"></a><span data-ttu-id="eb733-116">Ställ in dimensionsgrupper</span><span class="sxs-lookup"><span data-stu-id="eb733-116">Set up dimension groups</span></span>
1. <span data-ttu-id="eb733-117">Klicka på Dimensionsgrupper för att öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="eb733-117">Click Dimension groups to open the drop dialog.</span></span>
2. <span data-ttu-id="eb733-118">Ange eller välj ett värde i fältet Lagringsdimensionsgrupp.</span><span class="sxs-lookup"><span data-stu-id="eb733-118">In the Storage dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="eb733-119">Lagringsdimensiongruppen avgör vilka lagringsdimensioner du måste ange för varje transaktion för produkten och hur den ska spåras i lagret.</span><span class="sxs-lookup"><span data-stu-id="eb733-119">The storage dimension group determines which storage dimensions you must enter on each transaction for the product and how it will be tracked in inventory.</span></span>  
3. <span data-ttu-id="eb733-120">Ange eller välj ett värde i fältet Spårningsdimensionsgrupp.</span><span class="sxs-lookup"><span data-stu-id="eb733-120">In the Tracking dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="eb733-121">Spårningsdimensiongruppen avgör vilka spårningsdimensioner du måste ange för varje transaktion för produkten och hur den ska hanteras i lagret.</span><span class="sxs-lookup"><span data-stu-id="eb733-121">The tracking dimension group determines which tracking dimensions you must enter for each transaction for the product, and how it will be handled in inventory.</span></span>  
4. <span data-ttu-id="eb733-122">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="eb733-122">Click OK.</span></span>


