---
title: Övervaka en huvudplaneringskörning
description: Produktionsplaneraren vill visa om en huvudplaneringskörning pågår.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, ReqCreatePlanWorkspace, ReqTransPlanCard, SysQueryForm, InventItemIdLookupSimple, ReqLog, ReqProcessTaskTrace
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7c2e158d8cbad1f5d4f377f6a8eb43487b34ffdc
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/15/2019
ms.locfileid: "1565629"
---
# <a name="monitor-a-master-planning-run"></a><span data-ttu-id="940b5-103">Övervaka en huvudplaneringskörning</span><span class="sxs-lookup"><span data-stu-id="940b5-103">Monitor a master planning run</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="940b5-104">Produktionsplaneraren vill visa om en huvudplaneringskörning pågår.</span><span class="sxs-lookup"><span data-stu-id="940b5-104">The production planner wants to see if a master planning run is in progress.</span></span> <span data-ttu-id="940b5-105">Använd demonstrationsdataföretaget USMF för att utföra den här proceduren.</span><span class="sxs-lookup"><span data-stu-id="940b5-105">Use the demo data company USMF to complete this procedure.</span></span>


## <a name="run-master-planning"></a><span data-ttu-id="940b5-106">Kör Huvudplanering</span><span class="sxs-lookup"><span data-stu-id="940b5-106">Run master planning</span></span>
1. <span data-ttu-id="940b5-107">Klcka på Huvudplanering.</span><span class="sxs-lookup"><span data-stu-id="940b5-107">Click Master planning.</span></span>
    * <span data-ttu-id="940b5-108">Du hittar denna på standardinstrumentpanelen.</span><span class="sxs-lookup"><span data-stu-id="940b5-108">You'll find this on the default dashboard.</span></span>  
2. <span data-ttu-id="940b5-109">I fältet Plan, ange eller välj ett värde.</span><span class="sxs-lookup"><span data-stu-id="940b5-109">In the Plan field, enter or select a value.</span></span>
    * <span data-ttu-id="940b5-110">Exempel: StaticPlan</span><span class="sxs-lookup"><span data-stu-id="940b5-110">Example: StaticPlan</span></span>  
3. <span data-ttu-id="940b5-111">Klicka på Kör.</span><span class="sxs-lookup"><span data-stu-id="940b5-111">Click Run.</span></span>
4. <span data-ttu-id="940b5-112">Välj Ja i fältet Spåra bearbetningstid.</span><span class="sxs-lookup"><span data-stu-id="940b5-112">Select Yes in the Track processing time field.</span></span>
    * <span data-ttu-id="940b5-113">Om detta fält är markerat hoppar du över detta steg.</span><span class="sxs-lookup"><span data-stu-id="940b5-113">If the field is already selected, skip this step.</span></span>  
5. <span data-ttu-id="940b5-114">Ange ett nummer i fältet Antal trådar.</span><span class="sxs-lookup"><span data-stu-id="940b5-114">In the Number of threads field, enter a number.</span></span>
6. <span data-ttu-id="940b5-115">Expandera avsnittet Poster som ska ingå.</span><span class="sxs-lookup"><span data-stu-id="940b5-115">Expand the Records to include section.</span></span>
7. <span data-ttu-id="940b5-116">Klicka på Filter.</span><span class="sxs-lookup"><span data-stu-id="940b5-116">Click Filter.</span></span>
8. <span data-ttu-id="940b5-117">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="940b5-117">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="940b5-118">Markera raden där Fält = artikelnumret.</span><span class="sxs-lookup"><span data-stu-id="940b5-118">Mark the row where Field = Item number.</span></span>  
9. <span data-ttu-id="940b5-119">Ange eller välj ett värde i fältet Kriterier.</span><span class="sxs-lookup"><span data-stu-id="940b5-119">In the Criteria field, enter or select a value.</span></span>
    * <span data-ttu-id="940b5-120">Exempel: T0001</span><span class="sxs-lookup"><span data-stu-id="940b5-120">Example: T0001</span></span>  
10. <span data-ttu-id="940b5-121">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="940b5-121">Click OK.</span></span>
11. <span data-ttu-id="940b5-122">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="940b5-122">Click OK.</span></span>

## <a name="monitor-the-master-planning-run"></a><span data-ttu-id="940b5-123">Övervaka en huvudplaneringskörning</span><span class="sxs-lookup"><span data-stu-id="940b5-123">Monitor the master planning run</span></span>
1. <span data-ttu-id="940b5-124">Klicka på historik.</span><span class="sxs-lookup"><span data-stu-id="940b5-124">Click History.</span></span>
2. <span data-ttu-id="940b5-125">Klicka på Förfrågningar.</span><span class="sxs-lookup"><span data-stu-id="940b5-125">Click Inquiries.</span></span>
3. <span data-ttu-id="940b5-126">Klicka på Processuppgiftens tidslängd.</span><span class="sxs-lookup"><span data-stu-id="940b5-126">Click Process task duration.</span></span>
4. <span data-ttu-id="940b5-127">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="940b5-127">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="940b5-128">För varje artikel kan du få en översikt över hur länge det tog att använda alla planeringssteg.</span><span class="sxs-lookup"><span data-stu-id="940b5-128">For each item you can get an overview of how long it took to complete each planning step.</span></span>  

