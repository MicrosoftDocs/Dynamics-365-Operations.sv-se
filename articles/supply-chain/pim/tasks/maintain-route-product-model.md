---
title: Underhåll flöde för produktkonfigurationsmodellen
description: När du kör den här proceduren krävs det att det finns en modell för produktkonfiguration.
author: ShylaThompson
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCProductConfigurationModelDetails, PCRouteOperationDetails, WrkCtrCapabilityLookUp
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 13bbdc706280317c5a1ab7fb21c9585f1c7d48ad
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5247800"
---
# <a name="maintain-route-for-a-product-model"></a><span data-ttu-id="5b98a-103">Underhåll flöde för produktkonfigurationsmodellen</span><span class="sxs-lookup"><span data-stu-id="5b98a-103">Maintain route for a product model</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="5b98a-104">När du kör den här proceduren krävs det att det finns en modell för produktkonfiguration.</span><span class="sxs-lookup"><span data-stu-id="5b98a-104">Running this procedure requires that a product configuration model exists.</span></span> <span data-ttu-id="5b98a-105">I den här proceduren använder högtalarmodellen i demonstrationsföretaget USMF.</span><span class="sxs-lookup"><span data-stu-id="5b98a-105">This procedure uses the High end speaker model in the demo company USMF to walk you through the process.</span></span>


## <a name="add-a-route-operation"></a><span data-ttu-id="5b98a-106">Lägga till en flödesoperation</span><span class="sxs-lookup"><span data-stu-id="5b98a-106">Add a route operation</span></span>
1. <span data-ttu-id="5b98a-107">Klicka på Definition av produktvariantmodell.</span><span class="sxs-lookup"><span data-stu-id="5b98a-107">Click Product variant model definition.</span></span>
2. <span data-ttu-id="5b98a-108">Klicka på Modeller för produktkonfiguration.</span><span class="sxs-lookup"><span data-stu-id="5b98a-108">Click Product configuration models.</span></span>
3. <span data-ttu-id="5b98a-109">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="5b98a-109">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="5b98a-110">Välj högtalarmodellen till den här övningen.</span><span class="sxs-lookup"><span data-stu-id="5b98a-110">Select the High end speaker model for this exercise.</span></span>  
4. <span data-ttu-id="5b98a-111">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="5b98a-111">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="5b98a-112">Expandera avsnittet Flödesoperationer.</span><span class="sxs-lookup"><span data-stu-id="5b98a-112">Expand the Route operations section.</span></span>
6. <span data-ttu-id="5b98a-113">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="5b98a-113">Click Add.</span></span>
7. <span data-ttu-id="5b98a-114">Skriv ett värde i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="5b98a-114">In the Name field, type a value.</span></span>
8. <span data-ttu-id="5b98a-115">Ange ett värde i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="5b98a-115">In the Description field, type a value.</span></span>
9. <span data-ttu-id="5b98a-116">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="5b98a-116">Click Save.</span></span>

## <a name="enter-route-operation-details"></a><span data-ttu-id="5b98a-117">Ange flödesoperationsinformation</span><span class="sxs-lookup"><span data-stu-id="5b98a-117">Enter route operation details</span></span>
1. <span data-ttu-id="5b98a-118">Klicka på Flödesoperationsinformation.</span><span class="sxs-lookup"><span data-stu-id="5b98a-118">Click Route operation details.</span></span>
2. <span data-ttu-id="5b98a-119">Ange eller välj ett värde i fältet Operation.</span><span class="sxs-lookup"><span data-stu-id="5b98a-119">In the Operation field, enter or select a value.</span></span>
3. <span data-ttu-id="5b98a-120">I oper.</span><span class="sxs-lookup"><span data-stu-id="5b98a-120">In the Oper.</span></span> <span data-ttu-id="5b98a-121">Nr.</span><span class="sxs-lookup"><span data-stu-id="5b98a-121">No.</span></span> <span data-ttu-id="5b98a-122">fältet anger du ett tal.</span><span class="sxs-lookup"><span data-stu-id="5b98a-122">field, enter a number.</span></span>
    * <span data-ttu-id="5b98a-123">Operationsnummer bestämmer ordningsföljden.</span><span class="sxs-lookup"><span data-stu-id="5b98a-123">Operation numbers determine the route sequence.</span></span>  
    * <span data-ttu-id="5b98a-124">Varje egenskap i en flödesoperation kan få ett statiskt värde eller mappas till ett attribut.</span><span class="sxs-lookup"><span data-stu-id="5b98a-124">Each property on a route operation can get a static value or be mapped to an attribute.</span></span> <span data-ttu-id="5b98a-125">Mappning till ett attribut leder till att värdet ställs in dom en del av konfigurationen.</span><span class="sxs-lookup"><span data-stu-id="5b98a-125">Mapping to an attribute will result in the value being set as part of the configuration.</span></span>  
4. <span data-ttu-id="5b98a-126">Ange eller välj ett värde i fältet Flödesgrupp.</span><span class="sxs-lookup"><span data-stu-id="5b98a-126">In the Route group field, enter or select a value.</span></span>
    * <span data-ttu-id="5b98a-127">Flödesgruppen bestämmer beteendet för kostnadsredovisning, förbrukning och inställning.</span><span class="sxs-lookup"><span data-stu-id="5b98a-127">The route group determines essential behavior for costing, consumption, and setup.</span></span>  
5. <span data-ttu-id="5b98a-128">Klicka på fliken Inställningar.</span><span class="sxs-lookup"><span data-stu-id="5b98a-128">Click the Setup tab.</span></span>
6. <span data-ttu-id="5b98a-129">Klicka på fliken Tider.</span><span class="sxs-lookup"><span data-stu-id="5b98a-129">Click the Times tab.</span></span>
7. <span data-ttu-id="5b98a-130">I Processkvantitets- fältet anger du ett tal.</span><span class="sxs-lookup"><span data-stu-id="5b98a-130">In the Process qty. field, enter a number.</span></span>
    * <span data-ttu-id="5b98a-131">Bestäm hur många som ska bearbetas under en operation.</span><span class="sxs-lookup"><span data-stu-id="5b98a-131">Determine how many will be processed during one operation.</span></span>  
8. <span data-ttu-id="5b98a-132">Ange ett värde i fältet Timmar/tid.</span><span class="sxs-lookup"><span data-stu-id="5b98a-132">In the Hours/time field, enter a number.</span></span>
    * <span data-ttu-id="5b98a-133">Ange en tid.</span><span class="sxs-lookup"><span data-stu-id="5b98a-133">Enter the time ratio.</span></span>  
9. <span data-ttu-id="5b98a-134">Markera kryssrutan Uppsättning.</span><span class="sxs-lookup"><span data-stu-id="5b98a-134">Select the Set check box.</span></span>
10. <span data-ttu-id="5b98a-135">Ange ett värde i fältet Körtid.</span><span class="sxs-lookup"><span data-stu-id="5b98a-135">In the Run time field, enter a number.</span></span>
    * <span data-ttu-id="5b98a-136">Bestäm bearbetningstiden för den kvantitet som du har angett.</span><span class="sxs-lookup"><span data-stu-id="5b98a-136">Determine the processing time for the quantity that you have specified.</span></span>  
11. <span data-ttu-id="5b98a-137">Klicka på fliken Resurskrav.</span><span class="sxs-lookup"><span data-stu-id="5b98a-137">Click the Resource requirements tab.</span></span>
12. <span data-ttu-id="5b98a-138">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="5b98a-138">Click Add.</span></span>
13. <span data-ttu-id="5b98a-139">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="5b98a-139">In the list, mark the selected row.</span></span>
14. <span data-ttu-id="5b98a-140">Välj ett alternativ i fältet Kravtyp.</span><span class="sxs-lookup"><span data-stu-id="5b98a-140">In the Requirement type field, select an option.</span></span>
    * <span data-ttu-id="5b98a-141">Bestäm om du vill ange specifika resurser eller kvalifikationer som de måste ha.</span><span class="sxs-lookup"><span data-stu-id="5b98a-141">Decide if you want to specify specific resources or capabilities that they must possess.</span></span>  
15. <span data-ttu-id="5b98a-142">Ange eller välj ett värde i fältet Behov.</span><span class="sxs-lookup"><span data-stu-id="5b98a-142">In the Requirement field, enter or select a value.</span></span>
16. <span data-ttu-id="5b98a-143">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="5b98a-143">Click OK.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]