--- 
title: Definiera diskret tillverkningsresursgrupp
description: "En resursgrupp är en uppsättning verksamhetsresurser som normalt motsvarar den fysiska organisationen av arbetsgrupper som definieras av gula rader i produktionen."
author: sorenva
manager: AnnBe
ms.date: 02/12/2016
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
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: c2423fe91d1531a326080e3a584195ea864f2e3e
ms.contentlocale: sv-se
ms.lasthandoff: 08/29/2017

---
# <a name="define-discrete-manufacturing-resource-group"></a><span data-ttu-id="92e91-103">Definiera diskret tillverkningsresursgrupp</span><span class="sxs-lookup"><span data-stu-id="92e91-103">Define discrete manufacturing resource group</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="92e91-104">En resursgrupp är en uppsättning verksamhetsresurser som normalt motsvarar den fysiska organisationen av arbetsgrupper som definieras av gula rader i produktionen.</span><span class="sxs-lookup"><span data-stu-id="92e91-104">A resource group is a set of operations resources that typically correspond to the physical organization of work cells, defined by yellow lines on the production shop floor.</span></span> <span data-ttu-id="92e91-105">I den här proceduren visas definitionen av en resursgrupp för användning i diskret produktion.</span><span class="sxs-lookup"><span data-stu-id="92e91-105">This procedure shows you how to define a ressource group for use in discrete production.</span></span> <span data-ttu-id="92e91-106">Du kan gå igenom den här proceduren i demonstrationsdataföretaget USMF eller använda dina egna data.</span><span class="sxs-lookup"><span data-stu-id="92e91-106">You can walk through this procedure in demo data company USMF, or use your own data.</span></span>

1. <span data-ttu-id="92e91-107">Gå till Resursgrupper.</span><span class="sxs-lookup"><span data-stu-id="92e91-107">Go to Resource groups.</span></span>
2. <span data-ttu-id="92e91-108">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="92e91-108">Click New.</span></span>
3. <span data-ttu-id="92e91-109">Skriv ett värde i fältet Resursgrupp.</span><span class="sxs-lookup"><span data-stu-id="92e91-109">In the Resource group field, type a value.</span></span>
4. <span data-ttu-id="92e91-110">Ange ett värde i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="92e91-110">In the Description field, type a value.</span></span>
5. <span data-ttu-id="92e91-111">Ange eller välj ett värde i fältet Plats.</span><span class="sxs-lookup"><span data-stu-id="92e91-111">In the Site field, enter or select a value.</span></span>
6. <span data-ttu-id="92e91-112">Ange eller välj ett värde i fältet Produktion.</span><span class="sxs-lookup"><span data-stu-id="92e91-112">In the Production unit field, enter or select a value.</span></span>

## <a name="define-default-operational-parameters"></a><span data-ttu-id="92e91-113">Definiera standarddriftsparametrar</span><span class="sxs-lookup"><span data-stu-id="92e91-113">Define default operational parameters</span></span>
1. <span data-ttu-id="92e91-114">Expandera avsnittet Operation.</span><span class="sxs-lookup"><span data-stu-id="92e91-114">Expand the Operation section.</span></span>
2. <span data-ttu-id="92e91-115">Ange ett nummer i fältet Kassationsprocent.</span><span class="sxs-lookup"><span data-stu-id="92e91-115">In the Scrap percentage field, enter a number.</span></span>
3. <span data-ttu-id="92e91-116">I fältet Inställningskategori, ange eller välj ett värde.</span><span class="sxs-lookup"><span data-stu-id="92e91-116">In the Setup category field, enter or select a value.</span></span>
4. <span data-ttu-id="92e91-117">I fältet Kategori för körtid, ange eller välj ett värde.</span><span class="sxs-lookup"><span data-stu-id="92e91-117">In the Run time category field, enter or select a value.</span></span>
5. <span data-ttu-id="92e91-118">Ange ett tal i fältet Grovplaneringsprocent.</span><span class="sxs-lookup"><span data-stu-id="92e91-118">In the Operations scheduling percentage field, enter a number.</span></span>

## <a name="define-operating-hours"></a><span data-ttu-id="92e91-119">Definiera driftstimmar</span><span class="sxs-lookup"><span data-stu-id="92e91-119">Define operating hours</span></span>
1. <span data-ttu-id="92e91-120">Expandera avsnittet Kalendrar.</span><span class="sxs-lookup"><span data-stu-id="92e91-120">Expand the Calendars section.</span></span>
2. <span data-ttu-id="92e91-121">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="92e91-121">Click Add.</span></span>
3. <span data-ttu-id="92e91-122">Ange eller välj ett värde i fältet Kalender.</span><span class="sxs-lookup"><span data-stu-id="92e91-122">In the Calendar field, enter or select a value.</span></span>

## <a name="add-operations-resources"></a><span data-ttu-id="92e91-123">Lägg till verksamhetsresurser</span><span class="sxs-lookup"><span data-stu-id="92e91-123">Add operations resources</span></span>
1. <span data-ttu-id="92e91-124">Expandera avsnittet Resurser.</span><span class="sxs-lookup"><span data-stu-id="92e91-124">Expand the Resources section.</span></span>
2. <span data-ttu-id="92e91-125">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="92e91-125">Click Add.</span></span>
3. <span data-ttu-id="92e91-126">Ange eller välj ett värde i fältet Resurs.</span><span class="sxs-lookup"><span data-stu-id="92e91-126">In the Resource field, enter or select a value.</span></span>
4. <span data-ttu-id="92e91-127">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="92e91-127">Click Add.</span></span>
5. <span data-ttu-id="92e91-128">Ange eller välj ett värde i fältet Resurs.</span><span class="sxs-lookup"><span data-stu-id="92e91-128">In the Resource field, enter or select a value.</span></span>
6. <span data-ttu-id="92e91-129">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="92e91-129">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="92e91-130">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="92e91-130">In the list, click the link in the selected row.</span></span>


