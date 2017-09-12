--- 
title: "Underhåll ett flöde för en produktmodell"
description: "När du kör den här proceduren krävs det att det finns en modell för produktkonfiguration."
author: BibiSp
manager: AnnBe
ms.date: 03/02/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bibis
ms.search.scope: Operations
ms.search.region: Global
ms.author: bibis
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 55b22d246d6bfa9e8159fb844da95f61fcf07c62
ms.openlocfilehash: 3f6bacc54664c32a7d42f2befc51c420e29ada56
ms.contentlocale: sv-se
ms.lasthandoff: 07/28/2017

---
# <a name="maintain-a-route-for-a-product-model"></a><span data-ttu-id="81d52-103">Underhåll ett flöde för en produktmodell</span><span class="sxs-lookup"><span data-stu-id="81d52-103">Maintain a route for a product model</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="81d52-104">När du kör den här proceduren krävs det att det finns en modell för produktkonfiguration.</span><span class="sxs-lookup"><span data-stu-id="81d52-104">Running this procedure requires that a product configuration model exists.</span></span> <span data-ttu-id="81d52-105">I den här proceduren använder högtalarmodellen i demonstrationsföretaget USMF.</span><span class="sxs-lookup"><span data-stu-id="81d52-105">This procedure uses the High end speaker model in the demo company USMF to walk you through the process.</span></span>


## <a name="add-a-route-operation"></a><span data-ttu-id="81d52-106">Lägga till en flödesoperation</span><span class="sxs-lookup"><span data-stu-id="81d52-106">Add a route operation</span></span>
1. <span data-ttu-id="81d52-107">Klicka på Definition av produktvariantmodell.</span><span class="sxs-lookup"><span data-stu-id="81d52-107">Click Product variant model definition.</span></span>
2. <span data-ttu-id="81d52-108">Klicka på Modeller för produktkonfiguration.</span><span class="sxs-lookup"><span data-stu-id="81d52-108">Click Product configuration models.</span></span>
3. <span data-ttu-id="81d52-109">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="81d52-109">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="81d52-110">Välj högtalarmodellen till den här övningen.</span><span class="sxs-lookup"><span data-stu-id="81d52-110">Select the High end speaker model for this exercise.</span></span>  
4. <span data-ttu-id="81d52-111">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="81d52-111">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="81d52-112">Expandera avsnittet Flödesoperationer.</span><span class="sxs-lookup"><span data-stu-id="81d52-112">Expand the Route operations section.</span></span>
6. <span data-ttu-id="81d52-113">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="81d52-113">Click Add.</span></span>
7. <span data-ttu-id="81d52-114">Skriv ett värde i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="81d52-114">In the Name field, type a value.</span></span>
8. <span data-ttu-id="81d52-115">Ange ett värde i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="81d52-115">In the Description field, type a value.</span></span>
9. <span data-ttu-id="81d52-116">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="81d52-116">Click Save.</span></span>

## <a name="enter-route-operation-details"></a><span data-ttu-id="81d52-117">Ange flödesoperationsinformation</span><span class="sxs-lookup"><span data-stu-id="81d52-117">Enter route operation details</span></span>
1. <span data-ttu-id="81d52-118">Klicka på Flödesoperationsinformation.</span><span class="sxs-lookup"><span data-stu-id="81d52-118">Click Route operation details.</span></span>
2. <span data-ttu-id="81d52-119">Ange eller välj ett värde i fältet Operation.</span><span class="sxs-lookup"><span data-stu-id="81d52-119">In the Operation field, enter or select a value.</span></span>
3. <span data-ttu-id="81d52-120">I oper.</span><span class="sxs-lookup"><span data-stu-id="81d52-120">In the Oper.</span></span> <span data-ttu-id="81d52-121">Nr.</span><span class="sxs-lookup"><span data-stu-id="81d52-121">No.</span></span> <span data-ttu-id="81d52-122">fältet anger du ett tal.</span><span class="sxs-lookup"><span data-stu-id="81d52-122">field, enter a number.</span></span>
    * <span data-ttu-id="81d52-123">Operationsnummer bestämmer ordningsföljden.</span><span class="sxs-lookup"><span data-stu-id="81d52-123">Operation numbers determine the route sequence.</span></span>  
    * <span data-ttu-id="81d52-124">Varje egenskap i en flödesoperation kan få ett statiskt värde eller mappas till ett attribut.</span><span class="sxs-lookup"><span data-stu-id="81d52-124">Each property on a route operation can get a static value or be mapped to an attribute.</span></span> <span data-ttu-id="81d52-125">Mappning till ett attribut leder till att värdet ställs in dom en del av konfigurationen.</span><span class="sxs-lookup"><span data-stu-id="81d52-125">Mapping to an attribute will result in the value being set as part of the configuration.</span></span>  
4. <span data-ttu-id="81d52-126">Ange eller välj ett värde i fältet Flödesgrupp.</span><span class="sxs-lookup"><span data-stu-id="81d52-126">In the Route group field, enter or select a value.</span></span>
    * <span data-ttu-id="81d52-127">Flödesgruppen bestämmer beteendet för kostnadsredovisning, förbrukning och inställning.</span><span class="sxs-lookup"><span data-stu-id="81d52-127">The route group determines essential behavior for costing, consumption, and setup.</span></span>  
5. <span data-ttu-id="81d52-128">Klicka på fliken Inställningar.</span><span class="sxs-lookup"><span data-stu-id="81d52-128">Click the Setup tab.</span></span>
6. <span data-ttu-id="81d52-129">Klicka på fliken Tider.</span><span class="sxs-lookup"><span data-stu-id="81d52-129">Click the Times tab.</span></span>
7. <span data-ttu-id="81d52-130">I Processkvantitet</span><span class="sxs-lookup"><span data-stu-id="81d52-130">In the Process qty.</span></span> <span data-ttu-id="81d52-131">fältet anger du ett tal.</span><span class="sxs-lookup"><span data-stu-id="81d52-131">field, enter a number.</span></span>
    * <span data-ttu-id="81d52-132">Bestäm hur många som ska bearbetas under en operation.</span><span class="sxs-lookup"><span data-stu-id="81d52-132">Determine how many will be processed during one operation.</span></span>  
8. <span data-ttu-id="81d52-133">Ange ett värde i fältet Timmar/tid.</span><span class="sxs-lookup"><span data-stu-id="81d52-133">In the Hours/time field, enter a number.</span></span>
    * <span data-ttu-id="81d52-134">Ange en tid.</span><span class="sxs-lookup"><span data-stu-id="81d52-134">Enter the time ratio.</span></span>  
9. <span data-ttu-id="81d52-135">Markera kryssrutan Uppsättning.</span><span class="sxs-lookup"><span data-stu-id="81d52-135">Select the Set check box.</span></span>
10. <span data-ttu-id="81d52-136">Ange ett värde i fältet Körtid.</span><span class="sxs-lookup"><span data-stu-id="81d52-136">In the Run time field, enter a number.</span></span>
    * <span data-ttu-id="81d52-137">Bestäm bearbetningstiden för den kvantitet som du har angett.</span><span class="sxs-lookup"><span data-stu-id="81d52-137">Determine the processing time for the quantity that you have specified.</span></span>  
11. <span data-ttu-id="81d52-138">Klicka på fliken Resurskrav.</span><span class="sxs-lookup"><span data-stu-id="81d52-138">Click the Resource requirements tab.</span></span>
12. <span data-ttu-id="81d52-139">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="81d52-139">Click Add.</span></span>
13. <span data-ttu-id="81d52-140">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="81d52-140">In the list, mark the selected row.</span></span>
14. <span data-ttu-id="81d52-141">Välj ett alternativ i fältet Kravtyp.</span><span class="sxs-lookup"><span data-stu-id="81d52-141">In the Requirement type field, select an option.</span></span>
    * <span data-ttu-id="81d52-142">Bestäm om du vill ange specifika resurser eller kvalifikationer som de måste ha.</span><span class="sxs-lookup"><span data-stu-id="81d52-142">Decide if you want to specify specific resources or capabilities that they must possess.</span></span>  
15. <span data-ttu-id="81d52-143">Ange eller välj ett värde i fältet Behov.</span><span class="sxs-lookup"><span data-stu-id="81d52-143">In the Requirement field, enter or select a value.</span></span>
16. <span data-ttu-id="81d52-144">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="81d52-144">Click OK.</span></span>


