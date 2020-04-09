---
title: Ställ in attributbaserad prissättning för konfigurerbara produkter
description: I det här avsnittet visas hur du ställer in attributbaserad prissättning.
author: ShylaThompson
manager: AnnBe
ms.date: 08/20/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCPriceModelList, PCPriceModel, PCConstraintEditor
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d23030b79670e31cc237b9ca53b0b3881678786f
ms.sourcegitcommit: fcb27d6a46cd544feef34f6ec7607bdd46b0c12b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/18/2020
ms.locfileid: "3149836"
---
# <a name="set-up-attribute-based-pricing-for-configurable-products"></a><span data-ttu-id="5c791-103">Ställ in attributbaserad prissättning för konfigurerbara produkter</span><span class="sxs-lookup"><span data-stu-id="5c791-103">Set up attribute-based pricing for configurable products</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="5c791-104">I det här avsnittet visas hur du ställer in attributbaserad prissättning.</span><span class="sxs-lookup"><span data-stu-id="5c791-104">This topic explains how to set up attribute-based pricing.</span></span> <span data-ttu-id="5c791-105">Som en förutsättning måste du ha en modell för produktkonfiguration som har en eller flera komponenter och attribut.</span><span class="sxs-lookup"><span data-stu-id="5c791-105">As a prerequisite, you must have a product configuration model that has one or more components and attributes.</span></span> <span data-ttu-id="5c791-106">Detta exempel använder produktmodellen High End Speaker i demonstrationsföretaget USMF.</span><span class="sxs-lookup"><span data-stu-id="5c791-106">This example uses the High End Speaker product model in the USMF demo data company.</span></span> <span data-ttu-id="5c791-107">Vanligtvis använder en produktchef denna procedur.</span><span class="sxs-lookup"><span data-stu-id="5c791-107">Typically, a product manager uses this procedure.</span></span>


## <a name="create-a-new-price-model"></a><span data-ttu-id="5c791-108">Skapa en ny prismodell</span><span class="sxs-lookup"><span data-stu-id="5c791-108">Create a new price model</span></span>
1. <span data-ttu-id="5c791-109">Välj **Definition av produktvariantmodell** på startsidan.</span><span class="sxs-lookup"><span data-stu-id="5c791-109">Select **Product variant model definition** on the home page.</span></span>
2. <span data-ttu-id="5c791-110">Välj **Modeller för produktkonfiguration** i avsnitet **Länkar**.</span><span class="sxs-lookup"><span data-stu-id="5c791-110">Select **Product configuration models** in the **links** section.</span></span>
3. <span data-ttu-id="5c791-111">Välj raden **High End Speaker** i listan, men välj inte länken för namn.</span><span class="sxs-lookup"><span data-stu-id="5c791-111">In the list, select the **High End Speaker** line, but don't select the link for the name.</span></span>
4. <span data-ttu-id="5c791-112">Klicka på **Modell** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="5c791-112">On the Action Pane, select **Model**.</span></span>
5. <span data-ttu-id="5c791-113">Välj **Prismodeller**.</span><span class="sxs-lookup"><span data-stu-id="5c791-113">Select **Price models**.</span></span>
6. <span data-ttu-id="5c791-114">Välj **Ny**.</span><span class="sxs-lookup"><span data-stu-id="5c791-114">Select **New**.</span></span>
7. <span data-ttu-id="5c791-115">Ange ett värde i fältet **Prismodellnamn**.</span><span class="sxs-lookup"><span data-stu-id="5c791-115">In the **Price model name** field, type a value.</span></span> <span data-ttu-id="5c791-116">Använd ett namn som gör modellen enkel att identifiera.</span><span class="sxs-lookup"><span data-stu-id="5c791-116">Use a name that makes the model easy to identify.</span></span>  
8. <span data-ttu-id="5c791-117">I fältet **Beskrivning** anger du ett värde.</span><span class="sxs-lookup"><span data-stu-id="5c791-117">In the **Description** field, type a value.</span></span>
9. <span data-ttu-id="5c791-118">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="5c791-118">Select **Save**.</span></span>

## <a name="add-price-elements"></a><span data-ttu-id="5c791-119">Lägg till priselement</span><span class="sxs-lookup"><span data-stu-id="5c791-119">Add price elements</span></span>
1. <span data-ttu-id="5c791-120">Välj **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="5c791-120">Select **Edit**.</span></span> <span data-ttu-id="5c791-121">Varje komponent i en produktmodell kan ha ett grundpriselement och ett valfritt antal prisuttrycksregler.</span><span class="sxs-lookup"><span data-stu-id="5c791-121">Each component in a product model can have a base price element and any number of price expression rules.</span></span> <span data-ttu-id="5c791-122">Du kan också lägga till priser i olika valutor.</span><span class="sxs-lookup"><span data-stu-id="5c791-122">You can also add prices in different currencies.</span></span>  
2. <span data-ttu-id="5c791-123">Ange ett värde i fältet **Grundprisuttryck**.</span><span class="sxs-lookup"><span data-stu-id="5c791-123">In the **Base price expression** field, type a value.</span></span> <span data-ttu-id="5c791-124">Ange till exempel 100.</span><span class="sxs-lookup"><span data-stu-id="5c791-124">For example, type 100.</span></span> <span data-ttu-id="5c791-125">Ett grundprisuttryck kan utgöras av ett numeriskt värde eller bestå av en aritmetisk beräkning som gäller ett eller flera attribut.</span><span class="sxs-lookup"><span data-stu-id="5c791-125">A base price expression can be a numerical value, or it can consist of an arithmetic calculation that involves one or more attributes.</span></span>  
3. <span data-ttu-id="5c791-126">Markera **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="5c791-126">Select **Add**.</span></span>
4. <span data-ttu-id="5c791-127">I fältet **Namn** skriver du `Rosewood`.</span><span class="sxs-lookup"><span data-stu-id="5c791-127">In the **Name** field, type `Rosewood`.</span></span> <span data-ttu-id="5c791-128">Namnet för prisuttrycket hjälper till att identifiera det som priselementet representerar.</span><span class="sxs-lookup"><span data-stu-id="5c791-128">The price expression name helps identify what the price element represents.</span></span> <span data-ttu-id="5c791-129">I detta exempel skapar vi ett priselement för alternativet med rosenträfinish på högtalarkabinettet.</span><span class="sxs-lookup"><span data-stu-id="5c791-129">In this example, we are creating a price element for the Rosewood speaker cabinet finish option.</span></span>  
5. <span data-ttu-id="5c791-130">Välj **Redigeringsvillkor**.</span><span class="sxs-lookup"><span data-stu-id="5c791-130">Select **Edit condition**.</span></span> <span data-ttu-id="5c791-131">Ett prisvillkor hjälper till att säkerställa att ett prisuttryckselement ingår i försäljningspriset endast om en specifik attributkombination förekommer.</span><span class="sxs-lookup"><span data-stu-id="5c791-131">A price condition helps guarantee that a price expression element is included in the sales price only if a specific combination of attributes is present.</span></span>  
6. <span data-ttu-id="5c791-132">Ange `CabinetFinish=="Rosewood"` i fältet **ConstraintBody**.</span><span class="sxs-lookup"><span data-stu-id="5c791-132">In the **ConstraintBody** field, enter `CabinetFinish=="Rosewood"`.</span></span>
7. <span data-ttu-id="5c791-133">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="5c791-133">Select **OK**.</span></span>
8. <span data-ttu-id="5c791-134">Ange ett värde i fältet **Uttryck**.</span><span class="sxs-lookup"><span data-stu-id="5c791-134">In the **Expression** field, type a value.</span></span> <span data-ttu-id="5c791-135">Ange till exempel `50`.</span><span class="sxs-lookup"><span data-stu-id="5c791-135">For example, type `50`.</span></span> 
9. <span data-ttu-id="5c791-136">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="5c791-136">Close the page.</span></span>

