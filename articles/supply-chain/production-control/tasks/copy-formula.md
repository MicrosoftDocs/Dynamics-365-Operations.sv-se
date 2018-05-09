--- 
title: Kopiera en formel
description: "Den här proceduren fokuserar på att skapa en formel som innehåller samma ingredienser som en befintlig formel, men med mindre skillnader."
author: YuyuScheller
manager: AnnBe
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 61985d18f03a4afd8d94b23486cc462d2a868493
ms.contentlocale: sv-se
ms.lasthandoff: 05/08/2018

---
# <a name="copy-a-formula"></a><span data-ttu-id="61e4d-103">Kopiera en formel</span><span class="sxs-lookup"><span data-stu-id="61e4d-103">Copy a formula</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="61e4d-104">Den här proceduren fokuserar på att skapa en formel som innehåller samma ingredienser som en befintlig formel, men med mindre skillnader.</span><span class="sxs-lookup"><span data-stu-id="61e4d-104">This procedure focuses on creating a formula that includes the same ingredients as an existing formula, but with minor differences.</span></span> <span data-ttu-id="61e4d-105">Om du vill skapa formelraderna kan du använda kopieringsfunktionen för att kopiera en befintlig formel som har innehåller de flesta av de ingredienser som du behöver.</span><span class="sxs-lookup"><span data-stu-id="61e4d-105">To create the formula lines, you can use the Copy function to copy an existing formula that has most of the ingredients that you need.</span></span> <span data-ttu-id="61e4d-106">Du kan sedan göra nödvändiga ändringar på enskilda rader i den nya versionen.</span><span class="sxs-lookup"><span data-stu-id="61e4d-106">You can then make any necessary changes to the individual lines in the new version.</span></span> <span data-ttu-id="61e4d-107">Genom att använda kopieringsfunktionen behöver du inte skapa flera formler som är nästan identiska.</span><span class="sxs-lookup"><span data-stu-id="61e4d-107">By using the Copy function, you do not have to create multiple formulas that are almost identical.</span></span> <span data-ttu-id="61e4d-108">Det demonstrationsdataföretag som används för att skapa den här uppgiften är USP2.</span><span class="sxs-lookup"><span data-stu-id="61e4d-108">The demo data company used to create this task is USP2.</span></span>


## <a name="create-a-formula"></a><span data-ttu-id="61e4d-109">Skapa ett recept</span><span class="sxs-lookup"><span data-stu-id="61e4d-109">Create a formula</span></span>
1. <span data-ttu-id="61e4d-110">Gå till Produktinformationshantering > Strukturlistor och formler > Formler.</span><span class="sxs-lookup"><span data-stu-id="61e4d-110">Go to Product information management > Bills of materials and formulas > Formulas.</span></span>
2. <span data-ttu-id="61e4d-111">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="61e4d-111">Click New.</span></span>
3. <span data-ttu-id="61e4d-112">Skriv ett värde i fältet Formel.</span><span class="sxs-lookup"><span data-stu-id="61e4d-112">In the Formula field, type a value.</span></span>
4. <span data-ttu-id="61e4d-113">Skriv ett värde i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="61e4d-113">In the Name field, type a value.</span></span>
    * <span data-ttu-id="61e4d-114">Skriv ett beskrivande namn för formeln.</span><span class="sxs-lookup"><span data-stu-id="61e4d-114">Type a meaningful name for the formula.</span></span>  
5. <span data-ttu-id="61e4d-115">Öppna sökningen genom att klicka på listruteknappen i fältet Plats.</span><span class="sxs-lookup"><span data-stu-id="61e4d-115">In the Site field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="61e4d-116">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="61e4d-116">In the list, click the link in the selected row.</span></span>
7. <span data-ttu-id="61e4d-117">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Artikelgrupp.</span><span class="sxs-lookup"><span data-stu-id="61e4d-117">In the Item group field, click the drop-down button to open the lookup.</span></span>
8. <span data-ttu-id="61e4d-118">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="61e4d-118">In the list, find and select the desired record.</span></span>
9. <span data-ttu-id="61e4d-119">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="61e4d-119">In the list, click the link in the selected row.</span></span>
10. <span data-ttu-id="61e4d-120">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="61e4d-120">Click Save.</span></span>

## <a name="copy-formula-lines"></a><span data-ttu-id="61e4d-121">Kopiera formelrader</span><span class="sxs-lookup"><span data-stu-id="61e4d-121">Copy formula lines</span></span>
1. <span data-ttu-id="61e4d-122">Klicka på Formel i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="61e4d-122">On the Action Pane, click Formula.</span></span>
2. <span data-ttu-id="61e4d-123">Klicka på Kopiera.</span><span class="sxs-lookup"><span data-stu-id="61e4d-123">Click Copy.</span></span>
3. <span data-ttu-id="61e4d-124">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Artikelnummer.</span><span class="sxs-lookup"><span data-stu-id="61e4d-124">In the Item number field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="61e4d-125">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="61e4d-125">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="61e4d-126">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Formelversion.</span><span class="sxs-lookup"><span data-stu-id="61e4d-126">In the Formula version field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="61e4d-127">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="61e4d-127">In the list, click the link in the selected row.</span></span>
7. <span data-ttu-id="61e4d-128">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="61e4d-128">Click OK.</span></span>

## <a name="adjust-copied-formula-lines"></a><span data-ttu-id="61e4d-129">Justera kopierade formelrader</span><span class="sxs-lookup"><span data-stu-id="61e4d-129">Adjust copied formula lines</span></span>
1. <span data-ttu-id="61e4d-130">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="61e4d-130">In the list, mark the selected row.</span></span>
2. <span data-ttu-id="61e4d-131">Klicka på Ta bort.</span><span class="sxs-lookup"><span data-stu-id="61e4d-131">Click Delete.</span></span>
3. <span data-ttu-id="61e4d-132">Klicka på Ja.</span><span class="sxs-lookup"><span data-stu-id="61e4d-132">Click Yes.</span></span>

## <a name="approve-formula"></a><span data-ttu-id="61e4d-133">Godkänn recept</span><span class="sxs-lookup"><span data-stu-id="61e4d-133">Approve formula</span></span>
1. <span data-ttu-id="61e4d-134">Klicka på Formel i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="61e4d-134">On the Action Pane, click Formula.</span></span>
2. <span data-ttu-id="61e4d-135">Klicka på Godkänn recept.</span><span class="sxs-lookup"><span data-stu-id="61e4d-135">Click Approve formula.</span></span>
3. <span data-ttu-id="61e4d-136">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Godkänt av.</span><span class="sxs-lookup"><span data-stu-id="61e4d-136">In the Approved by field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="61e4d-137">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="61e4d-137">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="61e4d-138">Klicka på Välj.</span><span class="sxs-lookup"><span data-stu-id="61e4d-138">Click Select.</span></span>
6. <span data-ttu-id="61e4d-139">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="61e4d-139">Click OK.</span></span>


