--- 
title: Definiera diskret tillverkningsresursgrupp
description: "En resursgrupp är en uppsättning verksamhetsresurser som normalt motsvarar den fysiska organisationen av arbetsgrupper som definieras av gula rader i produktionen."
author: sorenva
manager: AnnBe
ms.date: 11/03/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: sorenand
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 2d74620761f01e2385288263e4f229872460fa21
ms.contentlocale: sv-se
ms.lasthandoff: 04/13/2018

---
# <a name="define-discrete-manufacturing-resource-group"></a><span data-ttu-id="1b1e9-103">Definiera diskret tillverkningsresursgrupp</span><span class="sxs-lookup"><span data-stu-id="1b1e9-103">Define discrete manufacturing resource group</span></span>

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="1b1e9-104">En resursgrupp är en uppsättning verksamhetsresurser som normalt motsvarar den fysiska organisationen av arbetsgrupper som definieras av gula rader i produktionen.</span><span class="sxs-lookup"><span data-stu-id="1b1e9-104">A resource group is a set of operations resources that typically correspond to the physical organization of work cells, defined by yellow lines on the production shop floor.</span></span> <span data-ttu-id="1b1e9-105">Den här proceduren visar hur du definierar en resursgrupp för användning i den diskreta produktionen.</span><span class="sxs-lookup"><span data-stu-id="1b1e9-105">This procedure shows you how to define a resource group for use in discrete production.</span></span> <span data-ttu-id="1b1e9-106">Du kan gå igenom den här proceduren i demonstrationsdataföretaget USMF eller använda dina egna data.</span><span class="sxs-lookup"><span data-stu-id="1b1e9-106">You can walk through this procedure in demo data company USMF, or use your own data.</span></span>

1. <span data-ttu-id="1b1e9-107">Gå till Resursgrupper.</span><span class="sxs-lookup"><span data-stu-id="1b1e9-107">Go to Resource groups.</span></span>
2. <span data-ttu-id="1b1e9-108">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="1b1e9-108">Click New.</span></span>
3. <span data-ttu-id="1b1e9-109">Skriv ett värde i fältet Resursgrupp.</span><span class="sxs-lookup"><span data-stu-id="1b1e9-109">In the Resource group field, type a value.</span></span>
4. <span data-ttu-id="1b1e9-110">Ange ett värde i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="1b1e9-110">In the Description field, type a value.</span></span>
5. <span data-ttu-id="1b1e9-111">Ange eller välj ett värde i fältet Plats.</span><span class="sxs-lookup"><span data-stu-id="1b1e9-111">In the Site field, enter or select a value.</span></span>
6. <span data-ttu-id="1b1e9-112">Ange eller välj ett värde i fältet Produktion.</span><span class="sxs-lookup"><span data-stu-id="1b1e9-112">In the Production unit field, enter or select a value.</span></span>

## <a name="define-default-operational-parameters"></a><span data-ttu-id="1b1e9-113">Definiera standarddriftsparametrar</span><span class="sxs-lookup"><span data-stu-id="1b1e9-113">Define default operational parameters</span></span>
1. <span data-ttu-id="1b1e9-114">Expandera avsnittet Operation.</span><span class="sxs-lookup"><span data-stu-id="1b1e9-114">Expand the Operation section.</span></span>
2. <span data-ttu-id="1b1e9-115">Ange ett nummer i fältet Kassationsprocent.</span><span class="sxs-lookup"><span data-stu-id="1b1e9-115">In the Scrap percentage field, enter a number.</span></span>
3. <span data-ttu-id="1b1e9-116">I fältet Inställningskategori, ange eller välj ett värde.</span><span class="sxs-lookup"><span data-stu-id="1b1e9-116">In the Setup category field, enter or select a value.</span></span>
4. <span data-ttu-id="1b1e9-117">I fältet Kategori för körtid, ange eller välj ett värde.</span><span class="sxs-lookup"><span data-stu-id="1b1e9-117">In the Run time category field, enter or select a value.</span></span>
5. <span data-ttu-id="1b1e9-118">Ange ett tal i fältet Grovplaneringsprocent.</span><span class="sxs-lookup"><span data-stu-id="1b1e9-118">In the Operations scheduling percentage field, enter a number.</span></span>

## <a name="define-operating-hours"></a><span data-ttu-id="1b1e9-119">Definiera driftstimmar</span><span class="sxs-lookup"><span data-stu-id="1b1e9-119">Define operating hours</span></span>
1. <span data-ttu-id="1b1e9-120">Expandera avsnittet Kalendrar.</span><span class="sxs-lookup"><span data-stu-id="1b1e9-120">Expand the Calendars section.</span></span>
2. <span data-ttu-id="1b1e9-121">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="1b1e9-121">Click Add.</span></span>
3. <span data-ttu-id="1b1e9-122">Ange eller välj ett värde i fältet Kalender.</span><span class="sxs-lookup"><span data-stu-id="1b1e9-122">In the Calendar field, enter or select a value.</span></span>

## <a name="add-operations-resources"></a><span data-ttu-id="1b1e9-123">Lägg till verksamhetsresurser</span><span class="sxs-lookup"><span data-stu-id="1b1e9-123">Add operations resources</span></span>
1. <span data-ttu-id="1b1e9-124">Expandera avsnittet Resurser.</span><span class="sxs-lookup"><span data-stu-id="1b1e9-124">Expand the Resources section.</span></span>
2. <span data-ttu-id="1b1e9-125">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="1b1e9-125">Click Add.</span></span>
3. <span data-ttu-id="1b1e9-126">Ange eller välj ett värde i fältet Resurs.</span><span class="sxs-lookup"><span data-stu-id="1b1e9-126">In the Resource field, enter or select a value.</span></span>
4. <span data-ttu-id="1b1e9-127">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="1b1e9-127">Click Add.</span></span>
5. <span data-ttu-id="1b1e9-128">Ange eller välj ett värde i fältet Resurs.</span><span class="sxs-lookup"><span data-stu-id="1b1e9-128">In the Resource field, enter or select a value.</span></span>
6. <span data-ttu-id="1b1e9-129">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="1b1e9-129">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="1b1e9-130">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="1b1e9-130">In the list, click the link in the selected row.</span></span>


