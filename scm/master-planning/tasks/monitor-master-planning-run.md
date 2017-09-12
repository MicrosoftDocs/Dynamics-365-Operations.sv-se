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
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 1e08d9fd3388561563e6fb982416186a652b4ce2
ms.contentlocale: sv-se
ms.lasthandoff: 08/29/2017

---
# <a name="monitor-a-master-planning-run"></a><span data-ttu-id="f6b76-103">Övervaka en huvudplaneringskörning</span><span class="sxs-lookup"><span data-stu-id="f6b76-103">Monitor a master planning run</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="f6b76-104">Produktionsplaneraren vill visa om en huvudplaneringskörning pågår.</span><span class="sxs-lookup"><span data-stu-id="f6b76-104">The production planner wants to see if a master planning run is in progress.</span></span> <span data-ttu-id="f6b76-105">Använd demonstrationsdataföretaget USMF för att utföra den här proceduren.</span><span class="sxs-lookup"><span data-stu-id="f6b76-105">Use the demo data company USMF to complete this procedure.</span></span>


## <a name="run-master-planning"></a><span data-ttu-id="f6b76-106">Kör Huvudplanering</span><span class="sxs-lookup"><span data-stu-id="f6b76-106">Run master planning</span></span>
1. <span data-ttu-id="f6b76-107">Klcka på Huvudplanering.</span><span class="sxs-lookup"><span data-stu-id="f6b76-107">Click Master planning.</span></span>
    * <span data-ttu-id="f6b76-108">Du hittar denna på standardinstrumentpanelen.</span><span class="sxs-lookup"><span data-stu-id="f6b76-108">You'll find this on the default dashboard.</span></span>  
2. <span data-ttu-id="f6b76-109">I fältet Plan, ange eller välj ett värde.</span><span class="sxs-lookup"><span data-stu-id="f6b76-109">In the Plan field, enter or select a value.</span></span>
    * <span data-ttu-id="f6b76-110">Exempel: StaticPlan</span><span class="sxs-lookup"><span data-stu-id="f6b76-110">Example: StaticPlan</span></span>  
3. <span data-ttu-id="f6b76-111">Klicka på Kör.</span><span class="sxs-lookup"><span data-stu-id="f6b76-111">Click Run.</span></span>
4. <span data-ttu-id="f6b76-112">Välj Ja i fältet Spåra bearbetningstid.</span><span class="sxs-lookup"><span data-stu-id="f6b76-112">Select Yes in the Track processing time field.</span></span>
    * <span data-ttu-id="f6b76-113">Om detta fält är markerat hoppar du över detta steg.</span><span class="sxs-lookup"><span data-stu-id="f6b76-113">If the field is already selected, skip this step.</span></span>  
5. <span data-ttu-id="f6b76-114">Ange ett nummer i fältet Antal trådar.</span><span class="sxs-lookup"><span data-stu-id="f6b76-114">In the Number of threads field, enter a number.</span></span>
6. <span data-ttu-id="f6b76-115">Expandera avsnittet Poster som ska ingå.</span><span class="sxs-lookup"><span data-stu-id="f6b76-115">Expand the Records to include section.</span></span>
7. <span data-ttu-id="f6b76-116">Klicka på Filter.</span><span class="sxs-lookup"><span data-stu-id="f6b76-116">Click Filter.</span></span>
8. <span data-ttu-id="f6b76-117">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="f6b76-117">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="f6b76-118">Markera raden där Fält = artikelnumret.</span><span class="sxs-lookup"><span data-stu-id="f6b76-118">Mark the row where Field = Item number.</span></span>  
9. <span data-ttu-id="f6b76-119">Ange eller välj ett värde i fältet Kriterier.</span><span class="sxs-lookup"><span data-stu-id="f6b76-119">In the Criteria field, enter or select a value.</span></span>
    * <span data-ttu-id="f6b76-120">Exempel: T0001</span><span class="sxs-lookup"><span data-stu-id="f6b76-120">Example: T0001</span></span>  
10. <span data-ttu-id="f6b76-121">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="f6b76-121">Click OK.</span></span>
11. <span data-ttu-id="f6b76-122">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="f6b76-122">Click OK.</span></span>

## <a name="monitor-the-master-planning-run"></a><span data-ttu-id="f6b76-123">Övervaka en huvudplaneringskörning</span><span class="sxs-lookup"><span data-stu-id="f6b76-123">Monitor the master planning run</span></span>
1. <span data-ttu-id="f6b76-124">Klicka på historik.</span><span class="sxs-lookup"><span data-stu-id="f6b76-124">Click History.</span></span>
2. <span data-ttu-id="f6b76-125">Klicka på Förfrågningar.</span><span class="sxs-lookup"><span data-stu-id="f6b76-125">Click Inquiries.</span></span>
3. <span data-ttu-id="f6b76-126">Klicka på Processuppgiftens tidslängd.</span><span class="sxs-lookup"><span data-stu-id="f6b76-126">Click Process task duration.</span></span>
4. <span data-ttu-id="f6b76-127">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="f6b76-127">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="f6b76-128">För varje artikel kan du få en översikt över hur länge det tog att använda alla planeringssteg.</span><span class="sxs-lookup"><span data-stu-id="f6b76-128">For each item you can get an overview of how long it took to complete each planning step.</span></span>  


