---
title: Ställ in attributbaserad prissättning för konfigurerbara produkter
description: I den här proceduren visas hur du ställer in attributbaserad prissättning.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCPriceModelList, PCPriceModel, PCConstraintEditor
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 8568b5f4933ae58bc2d55a169c798668e03bed2a
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/15/2019
ms.locfileid: "1573290"
---
# <a name="set-up-attribute-based-pricing-for-configurable-products"></a><span data-ttu-id="20822-103">Ställ in attributbaserad prissättning för konfigurerbara produkter</span><span class="sxs-lookup"><span data-stu-id="20822-103">Set up attribute-based pricing for configurable products</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="20822-104">I den här proceduren visas hur du ställer in attributbaserad prissättning.</span><span class="sxs-lookup"><span data-stu-id="20822-104">This procedure shows how to set up attribute-based pricing.</span></span> <span data-ttu-id="20822-105">Som en förutsättning måste du ha en modell för produktkonfiguration som har en eller flera komponenter och attribut.</span><span class="sxs-lookup"><span data-stu-id="20822-105">As a prerequisite, you must have a product configuration model that has one or more components and attributes.</span></span> <span data-ttu-id="20822-106">Detta exempel använder produktmodellen High End Speaker i demonstrationsföretaget USMF.</span><span class="sxs-lookup"><span data-stu-id="20822-106">This example uses the High End Speaker product model in the USMF demo data company.</span></span> <span data-ttu-id="20822-107">Vanligtvis använder en produktchef denna procedur.</span><span class="sxs-lookup"><span data-stu-id="20822-107">Typically, a product manager uses this procedure.</span></span>


## <a name="create-a-new-price-model"></a><span data-ttu-id="20822-108">Skapa en ny prismodell</span><span class="sxs-lookup"><span data-stu-id="20822-108">Create a new price model</span></span>
1. <span data-ttu-id="20822-109">Klicka på Definition av produktvariantmodell.</span><span class="sxs-lookup"><span data-stu-id="20822-109">Click Product variant model definition.</span></span>
2. <span data-ttu-id="20822-110">Klicka på Modeller för produktkonfiguration.</span><span class="sxs-lookup"><span data-stu-id="20822-110">Click Product configuration models.</span></span>
3. <span data-ttu-id="20822-111">Välj raden High End Speaker i listan, men inte klicka på länken för namn.</span><span class="sxs-lookup"><span data-stu-id="20822-111">In the list, select the High End Speaker line, but don’t click the link for the name.</span></span>
4. <span data-ttu-id="20822-112">Klicka på Modell i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="20822-112">On the Action Pane, click Model.</span></span>
5. <span data-ttu-id="20822-113">Klicka på Price models.</span><span class="sxs-lookup"><span data-stu-id="20822-113">Click Price models.</span></span>
6. <span data-ttu-id="20822-114">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="20822-114">Click New.</span></span>
7. <span data-ttu-id="20822-115">Ange ett värde i fältet Price model name.</span><span class="sxs-lookup"><span data-stu-id="20822-115">In the Price model name field, type a value.</span></span>
    * <span data-ttu-id="20822-116">Använd ett namn som gör modellen enkel att identifiera.</span><span class="sxs-lookup"><span data-stu-id="20822-116">Use a name that makes the model easy to identify.</span></span>  
8. <span data-ttu-id="20822-117">Ange ett värde i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="20822-117">In the Description field, type a value.</span></span>
9. <span data-ttu-id="20822-118">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="20822-118">Click Save.</span></span>

## <a name="add-price-elements"></a><span data-ttu-id="20822-119">Lägg till priselement</span><span class="sxs-lookup"><span data-stu-id="20822-119">Add price elements</span></span>
1. <span data-ttu-id="20822-120">Klicka på Redigera.</span><span class="sxs-lookup"><span data-stu-id="20822-120">Click Edit.</span></span>
    * <span data-ttu-id="20822-121">Varje komponent i en produktmodell kan ha ett grundpriselement och ett valfritt antal prisuttrycksregler.</span><span class="sxs-lookup"><span data-stu-id="20822-121">Each component in a product model can have a base price element and any number of price expression rules.</span></span> <span data-ttu-id="20822-122">Du kan också lägga till priser i olika valutor.</span><span class="sxs-lookup"><span data-stu-id="20822-122">You can also add prices in different currencies.</span></span>  
2. <span data-ttu-id="20822-123">Ange ett värde i fältet Base price expression.</span><span class="sxs-lookup"><span data-stu-id="20822-123">In the Base price expression field, type a value.</span></span>
    * <span data-ttu-id="20822-124">Ange till exempel 100.</span><span class="sxs-lookup"><span data-stu-id="20822-124">For example, type 100.</span></span>   <span data-ttu-id="20822-125">Ett grundprisuttryck kan utgöras av ett numeriskt värde eller bestå av en aritmetisk beräkning som gäller ett eller flera attribut.</span><span class="sxs-lookup"><span data-stu-id="20822-125">A base price expression can be a numerical value, or it can consist of an arithmetic calculation that involves one or more attributes.</span></span>  
3. <span data-ttu-id="20822-126">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="20822-126">Click Add.</span></span>
4. <span data-ttu-id="20822-127">Ange "Rosewood" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="20822-127">In the Name field, type ‘Rosewood’.</span></span>
    * <span data-ttu-id="20822-128">Namnet för prisuttrycket hjälper till att identifiera det som priselementet representerar.</span><span class="sxs-lookup"><span data-stu-id="20822-128">The price expression name helps identify what the price element represents.</span></span> <span data-ttu-id="20822-129">I detta exempel skapar vi ett priselement för alternativet med rosenträfinish på högtalarkabinettet.</span><span class="sxs-lookup"><span data-stu-id="20822-129">In this example, we are creating a price element for the Rosewood speaker cabinet finish option.</span></span>  
5. <span data-ttu-id="20822-130">Klicka på Edit condition.</span><span class="sxs-lookup"><span data-stu-id="20822-130">Click Edit condition.</span></span>
    * <span data-ttu-id="20822-131">Ett prisvillkor hjälper till att säkerställa att ett prisuttryckselement ingår i försäljningspriset endast om en specifik attributkombination förekommer.</span><span class="sxs-lookup"><span data-stu-id="20822-131">A price condition helps guarantee that a price expression element is included in the sales price only if a specific combination of attributes is present.</span></span>  
6. <span data-ttu-id="20822-132">I fältet ConstraintBody anger du "CabinetFinish=="Rosewood"".</span><span class="sxs-lookup"><span data-stu-id="20822-132">In the ConstraintBody field, enter 'CabinetFinish=="Rosewood"'.</span></span>
7. <span data-ttu-id="20822-133">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="20822-133">Click OK.</span></span>
8. <span data-ttu-id="20822-134">Ange ett värde i fältet Expression.</span><span class="sxs-lookup"><span data-stu-id="20822-134">In the Expression field, type a value.</span></span>
    * <span data-ttu-id="20822-135">Ange till exempel 50.</span><span class="sxs-lookup"><span data-stu-id="20822-135">For example, type 50.</span></span>  
9. <span data-ttu-id="20822-136">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="20822-136">Close the page.</span></span>
10. <span data-ttu-id="20822-137">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="20822-137">Close the page.</span></span>

