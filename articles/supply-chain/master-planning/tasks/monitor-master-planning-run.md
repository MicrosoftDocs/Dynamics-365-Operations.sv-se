--- 
title: "Övervaka en huvudplaneringskörning"
description: "Produktionsplaneraren vill visa om en huvudplaneringskörning pågår."
author: YuyuScheller
manager: AnnBe
ms.date: 06/10/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.author: yuyus
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: fde6c2b721fc1fa3f224ecb0c9669b1b861633f1
ms.contentlocale: sv-se
ms.lasthandoff: 04/13/2018

---
# <a name="monitor-a-master-planning-run"></a><span data-ttu-id="468cc-103">Övervaka en huvudplaneringskörning</span><span class="sxs-lookup"><span data-stu-id="468cc-103">Monitor a master planning run</span></span>

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="468cc-104">Produktionsplaneraren vill visa om en huvudplaneringskörning pågår.</span><span class="sxs-lookup"><span data-stu-id="468cc-104">The production planner wants to see if a master planning run is in progress.</span></span> <span data-ttu-id="468cc-105">Använd demonstrationsdataföretaget USMF för att utföra den här proceduren.</span><span class="sxs-lookup"><span data-stu-id="468cc-105">Use the demo data company USMF to complete this procedure.</span></span>


## <a name="run-master-planning"></a><span data-ttu-id="468cc-106">Kör Huvudplanering</span><span class="sxs-lookup"><span data-stu-id="468cc-106">Run master planning</span></span>
1. <span data-ttu-id="468cc-107">Klcka på Huvudplanering.</span><span class="sxs-lookup"><span data-stu-id="468cc-107">Click Master planning.</span></span>
    * <span data-ttu-id="468cc-108">Du hittar denna på standardinstrumentpanelen.</span><span class="sxs-lookup"><span data-stu-id="468cc-108">You'll find this on the default dashboard.</span></span>  
2. <span data-ttu-id="468cc-109">I fältet Plan, ange eller välj ett värde.</span><span class="sxs-lookup"><span data-stu-id="468cc-109">In the Plan field, enter or select a value.</span></span>
    * <span data-ttu-id="468cc-110">Exempel: StaticPlan</span><span class="sxs-lookup"><span data-stu-id="468cc-110">Example: StaticPlan</span></span>  
3. <span data-ttu-id="468cc-111">Klicka på Kör.</span><span class="sxs-lookup"><span data-stu-id="468cc-111">Click Run.</span></span>
4. <span data-ttu-id="468cc-112">Välj Ja i fältet Spåra bearbetningstid.</span><span class="sxs-lookup"><span data-stu-id="468cc-112">Select Yes in the Track processing time field.</span></span>
    * <span data-ttu-id="468cc-113">Om detta fält är markerat hoppar du över detta steg.</span><span class="sxs-lookup"><span data-stu-id="468cc-113">If the field is already selected, skip this step.</span></span>  
5. <span data-ttu-id="468cc-114">Ange ett nummer i fältet Antal trådar.</span><span class="sxs-lookup"><span data-stu-id="468cc-114">In the Number of threads field, enter a number.</span></span>
6. <span data-ttu-id="468cc-115">Expandera avsnittet Poster som ska ingå.</span><span class="sxs-lookup"><span data-stu-id="468cc-115">Expand the Records to include section.</span></span>
7. <span data-ttu-id="468cc-116">Klicka på Filter.</span><span class="sxs-lookup"><span data-stu-id="468cc-116">Click Filter.</span></span>
8. <span data-ttu-id="468cc-117">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="468cc-117">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="468cc-118">Markera raden där Fält = artikelnumret.</span><span class="sxs-lookup"><span data-stu-id="468cc-118">Mark the row where Field = Item number.</span></span>  
9. <span data-ttu-id="468cc-119">Ange eller välj ett värde i fältet Kriterier.</span><span class="sxs-lookup"><span data-stu-id="468cc-119">In the Criteria field, enter or select a value.</span></span>
    * <span data-ttu-id="468cc-120">Exempel: T0001</span><span class="sxs-lookup"><span data-stu-id="468cc-120">Example: T0001</span></span>  
10. <span data-ttu-id="468cc-121">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="468cc-121">Click OK.</span></span>
11. <span data-ttu-id="468cc-122">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="468cc-122">Click OK.</span></span>

## <a name="monitor-the-master-planning-run"></a><span data-ttu-id="468cc-123">Övervaka en huvudplaneringskörning</span><span class="sxs-lookup"><span data-stu-id="468cc-123">Monitor the master planning run</span></span>
1. <span data-ttu-id="468cc-124">Klicka på historik.</span><span class="sxs-lookup"><span data-stu-id="468cc-124">Click History.</span></span>
2. <span data-ttu-id="468cc-125">Klicka på Förfrågningar.</span><span class="sxs-lookup"><span data-stu-id="468cc-125">Click Inquiries.</span></span>
3. <span data-ttu-id="468cc-126">Klicka på Processuppgiftens tidslängd.</span><span class="sxs-lookup"><span data-stu-id="468cc-126">Click Process task duration.</span></span>
4. <span data-ttu-id="468cc-127">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="468cc-127">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="468cc-128">För varje artikel kan du få en översikt över hur länge det tog att använda alla planeringssteg.</span><span class="sxs-lookup"><span data-stu-id="468cc-128">For each item you can get an overview of how long it took to complete each planning step.</span></span>  


