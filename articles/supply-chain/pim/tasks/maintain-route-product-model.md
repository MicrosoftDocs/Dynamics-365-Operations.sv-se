---
title: Underhåll flöde för produktkonfigurationsmodellen
description: När du kör den här proceduren krävs det att det finns en modell för produktkonfiguration.
author: ShylaThompson
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCProductConfigurationModelDetails, PCRouteOperationDetails, WrkCtrCapabilityLookUp
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 45c6b1e6e75645bb17ce4defa0bca0e6d2131b6e
ms.sourcegitcommit: fa99a36c3d30d0c0577fd3f63ed6bf2f71599e40
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/20/2021
ms.locfileid: "5921275"
---
# <a name="maintain-route-for-a-product-model"></a><span data-ttu-id="ee65b-103">Underhåll flöde för produktkonfigurationsmodellen</span><span class="sxs-lookup"><span data-stu-id="ee65b-103">Maintain route for a product model</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="ee65b-104">När du kör den här proceduren krävs det att det finns en modell för produktkonfiguration.</span><span class="sxs-lookup"><span data-stu-id="ee65b-104">Running this procedure requires that a product configuration model exists.</span></span> <span data-ttu-id="ee65b-105">I den här proceduren använder högtalarmodellen i demonstrationsföretaget USMF.</span><span class="sxs-lookup"><span data-stu-id="ee65b-105">This procedure uses the High end speaker model in the demo company USMF to walk you through the process.</span></span>

## <a name="add-a-route-operation"></a><span data-ttu-id="ee65b-106">Lägga till en flödesoperation</span><span class="sxs-lookup"><span data-stu-id="ee65b-106">Add a route operation</span></span>

1. <span data-ttu-id="ee65b-107">Gå till **Produktinformationshantering \> Produkter \> Produktkonfigurationsmodeller**.</span><span class="sxs-lookup"><span data-stu-id="ee65b-107">Go to **Product information management \> Products \> Product configuration models**.</span></span>
1. <span data-ttu-id="ee65b-108">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="ee65b-108">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="ee65b-109">Välj högtalarmodellen till den här övningen.</span><span class="sxs-lookup"><span data-stu-id="ee65b-109">Select the High end speaker model for this exercise.</span></span>  
1. <span data-ttu-id="ee65b-110">Klicka på länken på önskad rad i valda listan.</span><span class="sxs-lookup"><span data-stu-id="ee65b-110">In the list, select the link in the selected row.</span></span>
1. <span data-ttu-id="ee65b-111">Expandera avsnittet **Flödesfunktioner**.</span><span class="sxs-lookup"><span data-stu-id="ee65b-111">Expand the **Route operations** section.</span></span>
1. <span data-ttu-id="ee65b-112">Markera **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="ee65b-112">Select **Add**.</span></span>
1. <span data-ttu-id="ee65b-113">Skriv ett värde i fältet **Namn**.</span><span class="sxs-lookup"><span data-stu-id="ee65b-113">In the **Name** field, type a value.</span></span>
1. <span data-ttu-id="ee65b-114">I fältet **Beskrivning** anger du ett värde.</span><span class="sxs-lookup"><span data-stu-id="ee65b-114">In the **Description** field, type a value.</span></span>
1. <span data-ttu-id="ee65b-115">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="ee65b-115">Select **Save**.</span></span>

## <a name="enter-route-operation-details"></a><span data-ttu-id="ee65b-116">Ange flödesoperationsinformation</span><span class="sxs-lookup"><span data-stu-id="ee65b-116">Enter route operation details</span></span>

1. <span data-ttu-id="ee65b-117">Välj **Information om flödesfunktioner**.</span><span class="sxs-lookup"><span data-stu-id="ee65b-117">Select **Route operation details**.</span></span>
1. <span data-ttu-id="ee65b-118">Ange eller välj ett värde i fältet **Funktion**.</span><span class="sxs-lookup"><span data-stu-id="ee65b-118">In the **Operation** field, enter or select a value.</span></span>
1. <span data-ttu-id="ee65b-119">I fältet **Funktionsnr.**</span><span class="sxs-lookup"><span data-stu-id="ee65b-119">In the **Oper. No.**</span></span> <span data-ttu-id="ee65b-120">fältet anger du ett tal.</span><span class="sxs-lookup"><span data-stu-id="ee65b-120">field, enter a number.</span></span>
    * <span data-ttu-id="ee65b-121">Operationsnummer bestämmer ordningsföljden.</span><span class="sxs-lookup"><span data-stu-id="ee65b-121">Operation numbers determine the route sequence.</span></span>  
    * <span data-ttu-id="ee65b-122">Varje egenskap i en flödesoperation kan få ett statiskt värde eller mappas till ett attribut.</span><span class="sxs-lookup"><span data-stu-id="ee65b-122">Each property on a route operation can get a static value or be mapped to an attribute.</span></span> <span data-ttu-id="ee65b-123">Mappning till ett attribut leder till att värdet ställs in dom en del av konfigurationen.</span><span class="sxs-lookup"><span data-stu-id="ee65b-123">Mapping to an attribute will result in the value being set as part of the configuration.</span></span>  
1. <span data-ttu-id="ee65b-124">Ange eller välj ett värde i fältet **Flödesgrupp**.</span><span class="sxs-lookup"><span data-stu-id="ee65b-124">In the **Route group** field, enter or select a value.</span></span>
    * <span data-ttu-id="ee65b-125">Flödesgruppen bestämmer beteendet för kostnadsredovisning, förbrukning och inställning.</span><span class="sxs-lookup"><span data-stu-id="ee65b-125">The route group determines essential behavior for costing, consumption, and setup.</span></span>  
1. <span data-ttu-id="ee65b-126">Välj fliken **Inställningar**.</span><span class="sxs-lookup"><span data-stu-id="ee65b-126">Select the **Setup** tab.</span></span>
1. <span data-ttu-id="ee65b-127">Välj fliken **Tider**.</span><span class="sxs-lookup"><span data-stu-id="ee65b-127">Select the **Times** tab.</span></span>
1. <span data-ttu-id="ee65b-128">I fältet **Processkvantitet** anger du ett värde.</span><span class="sxs-lookup"><span data-stu-id="ee65b-128">In the **Process qty.** field, enter a number.</span></span>
    * <span data-ttu-id="ee65b-129">Bestäm hur många som ska bearbetas under en operation.</span><span class="sxs-lookup"><span data-stu-id="ee65b-129">Determine how many will be processed during one operation.</span></span>  
1. <span data-ttu-id="ee65b-130">I fältet **Timmar/tid** anger du ett värde.</span><span class="sxs-lookup"><span data-stu-id="ee65b-130">In the **Hours/time** field, enter a number.</span></span>
    * <span data-ttu-id="ee65b-131">Ange en tid.</span><span class="sxs-lookup"><span data-stu-id="ee65b-131">Enter the time ratio.</span></span>  
1. <span data-ttu-id="ee65b-132">Markera kryssrutan **Ställ in**.</span><span class="sxs-lookup"><span data-stu-id="ee65b-132">Select the **Set** check box.</span></span>
1. <span data-ttu-id="ee65b-133">I fältet **Körningstid** anger du ett värde.</span><span class="sxs-lookup"><span data-stu-id="ee65b-133">In the **Run time** field, enter a number.</span></span>
    * <span data-ttu-id="ee65b-134">Bestäm bearbetningstiden för den kvantitet som du har angett.</span><span class="sxs-lookup"><span data-stu-id="ee65b-134">Determine the processing time for the quantity that you have specified.</span></span>  
1. <span data-ttu-id="ee65b-135">Välj fliken **Resurskrav**.</span><span class="sxs-lookup"><span data-stu-id="ee65b-135">Select the **Resource requirements** tab.</span></span>
1. <span data-ttu-id="ee65b-136">Markera **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="ee65b-136">Select **Add**.</span></span>
1. <span data-ttu-id="ee65b-137">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="ee65b-137">In the list, mark the selected row.</span></span>
1. <span data-ttu-id="ee65b-138">I fältet **Kravtyp** väljer du ett alternativ.</span><span class="sxs-lookup"><span data-stu-id="ee65b-138">In the **Requirement type** field, select an option.</span></span>
    * <span data-ttu-id="ee65b-139">Bestäm om du vill ange specifika resurser eller kvalifikationer som de måste ha.</span><span class="sxs-lookup"><span data-stu-id="ee65b-139">Decide if you want to specify specific resources or capabilities that they must possess.</span></span>  
1. <span data-ttu-id="ee65b-140">I fältet **Krav** anger eller väljer du ett värde.</span><span class="sxs-lookup"><span data-stu-id="ee65b-140">In the **Requirement** field, enter or select a value.</span></span>
1. <span data-ttu-id="ee65b-141">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="ee65b-141">Select **OK**.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]