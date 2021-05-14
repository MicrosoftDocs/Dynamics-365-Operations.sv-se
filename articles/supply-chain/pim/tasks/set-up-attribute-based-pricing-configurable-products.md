---
title: Ställ in attributbaserad prissättning för konfigurerbara produkter
description: I det här avsnittet visas hur du ställer in attributbaserad prissättning.
author: ShylaThompson
ms.date: 08/20/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCPriceModelList, PCPriceModel, PCConstraintEditor
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 0c30c520e7265c2676937f5191844f6789c364e6
ms.sourcegitcommit: fa99a36c3d30d0c0577fd3f63ed6bf2f71599e40
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/20/2021
ms.locfileid: "5921251"
---
# <a name="set-up-attribute-based-pricing-for-configurable-products"></a><span data-ttu-id="ec53d-103">Ställ in attributbaserad prissättning för konfigurerbara produkter</span><span class="sxs-lookup"><span data-stu-id="ec53d-103">Set up attribute-based pricing for configurable products</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="ec53d-104">I det här avsnittet visas hur du ställer in attributbaserad prissättning.</span><span class="sxs-lookup"><span data-stu-id="ec53d-104">This topic explains how to set up attribute-based pricing.</span></span> <span data-ttu-id="ec53d-105">Som en förutsättning måste du ha en modell för produktkonfiguration som har en eller flera komponenter och attribut.</span><span class="sxs-lookup"><span data-stu-id="ec53d-105">As a prerequisite, you must have a product configuration model that has one or more components and attributes.</span></span> <span data-ttu-id="ec53d-106">Detta exempel använder produktmodellen High End Speaker i demonstrationsföretaget USMF.</span><span class="sxs-lookup"><span data-stu-id="ec53d-106">This example uses the High End Speaker product model in the USMF demo data company.</span></span> <span data-ttu-id="ec53d-107">Vanligtvis använder en produktchef denna procedur.</span><span class="sxs-lookup"><span data-stu-id="ec53d-107">Typically, a product manager uses this procedure.</span></span>


## <a name="create-a-new-price-model"></a><span data-ttu-id="ec53d-108">Skapa en ny prismodell</span><span class="sxs-lookup"><span data-stu-id="ec53d-108">Create a new price model</span></span>

1. <span data-ttu-id="ec53d-109">Gå till **Produktinformationshantering \> Produkter \> Produktkonfigurationsmodeller**.</span><span class="sxs-lookup"><span data-stu-id="ec53d-109">Go to **Product information management \> Products \> Product configuration models**.</span></span>
1. <span data-ttu-id="ec53d-110">Välj raden **High End Speaker** i listan, men välj inte länken för namn.</span><span class="sxs-lookup"><span data-stu-id="ec53d-110">In the list, select the **High End Speaker** line, but don't select the link for the name.</span></span>
1. <span data-ttu-id="ec53d-111">Klicka på **Modell** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="ec53d-111">On the Action Pane, select **Model**.</span></span>
1. <span data-ttu-id="ec53d-112">Välj **Prismodeller**.</span><span class="sxs-lookup"><span data-stu-id="ec53d-112">Select **Price models**.</span></span>
1. <span data-ttu-id="ec53d-113">Välj **Ny**.</span><span class="sxs-lookup"><span data-stu-id="ec53d-113">Select **New**.</span></span>
1. <span data-ttu-id="ec53d-114">Ange ett värde i fältet **Prismodellnamn**.</span><span class="sxs-lookup"><span data-stu-id="ec53d-114">In the **Price model name** field, type a value.</span></span> <span data-ttu-id="ec53d-115">Använd ett namn som gör modellen enkel att identifiera.</span><span class="sxs-lookup"><span data-stu-id="ec53d-115">Use a name that makes the model easy to identify.</span></span>  
1. <span data-ttu-id="ec53d-116">I fältet **Beskrivning** anger du ett värde.</span><span class="sxs-lookup"><span data-stu-id="ec53d-116">In the **Description** field, type a value.</span></span>
1. <span data-ttu-id="ec53d-117">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="ec53d-117">Select **Save**.</span></span>

## <a name="add-price-elements"></a><span data-ttu-id="ec53d-118">Lägg till priselement</span><span class="sxs-lookup"><span data-stu-id="ec53d-118">Add price elements</span></span>

1. <span data-ttu-id="ec53d-119">Välj **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="ec53d-119">Select **Edit**.</span></span> <span data-ttu-id="ec53d-120">Varje komponent i en produktmodell kan ha ett grundpriselement och ett valfritt antal prisuttrycksregler.</span><span class="sxs-lookup"><span data-stu-id="ec53d-120">Each component in a product model can have a base price element and any number of price expression rules.</span></span> <span data-ttu-id="ec53d-121">Du kan också lägga till priser i olika valutor.</span><span class="sxs-lookup"><span data-stu-id="ec53d-121">You can also add prices in different currencies.</span></span>  
2. <span data-ttu-id="ec53d-122">Ange ett värde i fältet **Grundprisuttryck**.</span><span class="sxs-lookup"><span data-stu-id="ec53d-122">In the **Base price expression** field, type a value.</span></span> <span data-ttu-id="ec53d-123">Ange till exempel 100.</span><span class="sxs-lookup"><span data-stu-id="ec53d-123">For example, type 100.</span></span> <span data-ttu-id="ec53d-124">Ett grundprisuttryck kan utgöras av ett numeriskt värde eller bestå av en aritmetisk beräkning som gäller ett eller flera attribut.</span><span class="sxs-lookup"><span data-stu-id="ec53d-124">A base price expression can be a numerical value, or it can consist of an arithmetic calculation that involves one or more attributes.</span></span>  
3. <span data-ttu-id="ec53d-125">Markera **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="ec53d-125">Select **Add**.</span></span>
4. <span data-ttu-id="ec53d-126">I fältet **Namn** skriver du `Rosewood`.</span><span class="sxs-lookup"><span data-stu-id="ec53d-126">In the **Name** field, type `Rosewood`.</span></span> <span data-ttu-id="ec53d-127">Namnet för prisuttrycket hjälper till att identifiera det som priselementet representerar.</span><span class="sxs-lookup"><span data-stu-id="ec53d-127">The price expression name helps identify what the price element represents.</span></span> <span data-ttu-id="ec53d-128">I detta exempel skapar vi ett priselement för alternativet med rosenträfinish på högtalarkabinettet.</span><span class="sxs-lookup"><span data-stu-id="ec53d-128">In this example, we are creating a price element for the Rosewood speaker cabinet finish option.</span></span>  
5. <span data-ttu-id="ec53d-129">Välj **Redigeringsvillkor**.</span><span class="sxs-lookup"><span data-stu-id="ec53d-129">Select **Edit condition**.</span></span> <span data-ttu-id="ec53d-130">Ett prisvillkor hjälper till att säkerställa att ett prisuttryckselement ingår i försäljningspriset endast om en specifik attributkombination förekommer.</span><span class="sxs-lookup"><span data-stu-id="ec53d-130">A price condition helps guarantee that a price expression element is included in the sales price only if a specific combination of attributes is present.</span></span>  
6. <span data-ttu-id="ec53d-131">Ange `CabinetFinish=="Rosewood"` i fältet **ConstraintBody**.</span><span class="sxs-lookup"><span data-stu-id="ec53d-131">In the **ConstraintBody** field, enter `CabinetFinish=="Rosewood"`.</span></span>
7. <span data-ttu-id="ec53d-132">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="ec53d-132">Select **OK**.</span></span>
8. <span data-ttu-id="ec53d-133">Ange ett värde i fältet **Uttryck**.</span><span class="sxs-lookup"><span data-stu-id="ec53d-133">In the **Expression** field, type a value.</span></span> <span data-ttu-id="ec53d-134">Ange till exempel `50`.</span><span class="sxs-lookup"><span data-stu-id="ec53d-134">For example, type `50`.</span></span> 
9. <span data-ttu-id="ec53d-135">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="ec53d-135">Close the page.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]