---
title: Skapa en produktnummernomenklatur för fördefinierade produktvarianter
description: Detta avsnitt visar dig hur du skapar en produktnummernomenklatur för fördefinierade produktvarianter, samt hur du tilldelar denna till lämplig produktdimensionsgrupp.
author: ShylaThompson
ms.date: 08/20/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, EcoResNomenclature, EcoResProductDimensionGroup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 4bb73854f52525c0722683086d1b4f1dd7173306
ms.sourcegitcommit: fa99a36c3d30d0c0577fd3f63ed6bf2f71599e40
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/20/2021
ms.locfileid: "5920667"
---
# <a name="create-a-product-number-nomenclature-for-predefined-product-variants"></a><span data-ttu-id="63256-103">Skapa en produktnummernomenklatur för fördefinierade produktvarianter</span><span class="sxs-lookup"><span data-stu-id="63256-103">Create a product number nomenclature for predefined product variants</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="63256-104">Detta avsnitt visar dig hur du skapar en produktnummernomenklatur för fördefinierade produktvarianter, samt hur du tilldelar denna till lämplig produktdimensionsgrupp.</span><span class="sxs-lookup"><span data-stu-id="63256-104">This topic explains how to set up a product number nomenclature for predefined product variants, and how you assign it to the appropriate product dimension group.</span></span> <span data-ttu-id="63256-105">Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF.</span><span class="sxs-lookup"><span data-stu-id="63256-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="63256-106">Den nya produktnummernomenklaturen tilldelas till produktdimensionsgruppen Color and Size.</span><span class="sxs-lookup"><span data-stu-id="63256-106">The new product number nomenclature is assigned to the Color and Size product dimension group.</span></span> <span data-ttu-id="63256-107">Den här uppgiften utförs vanligtvis av en produktdesigner.</span><span class="sxs-lookup"><span data-stu-id="63256-107">This task would typically be done by a product designer.</span></span>


## <a name="create-a-product-number-nomenclature"></a><span data-ttu-id="63256-108">Skapa en nomenklatur för produktnummer</span><span class="sxs-lookup"><span data-stu-id="63256-108">Create a product number nomenclature</span></span>

1. <span data-ttu-id="63256-109">Gå till **Hantering av produktinformation \> Inställningar \> Produktnomenklatur**.</span><span class="sxs-lookup"><span data-stu-id="63256-109">Go to **Product information management \> Setup \> Product nomenclature**.</span></span>
1. <span data-ttu-id="63256-110">Välj **Ny**.</span><span class="sxs-lookup"><span data-stu-id="63256-110">Select **New**.</span></span>
1. <span data-ttu-id="63256-111">I fältet **Namn** anger du ett nomenklatursnamn som gör det enkelt att identifiera målproduktdimensionsgruppen, till exempel `ColorSize`.</span><span class="sxs-lookup"><span data-stu-id="63256-111">In the **Name** field, enter a nomenclature name that helps to identify the target product dimension group, for example, `ColorSize`.</span></span>
1. <span data-ttu-id="63256-112">I fältet **Beskrivning** anger du ett värde.</span><span class="sxs-lookup"><span data-stu-id="63256-112">In the **Description** field, type a value.</span></span>
1. <span data-ttu-id="63256-113">Markera **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="63256-113">Select **Add**.</span></span>
1. <span data-ttu-id="63256-114">Välj **Produktmallsnummer**.</span><span class="sxs-lookup"><span data-stu-id="63256-114">Select **Product master** number.</span></span>
1. <span data-ttu-id="63256-115">Markera **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="63256-115">Select **Add**.</span></span>
1. <span data-ttu-id="63256-116">Välj **Textkonstant**.</span><span class="sxs-lookup"><span data-stu-id="63256-116">Select **Text constant**.</span></span>
1. <span data-ttu-id="63256-117">Skriv ett värde i fältet **Text**.</span><span class="sxs-lookup"><span data-stu-id="63256-117">In the **Text** field, type a value.</span></span>
1. <span data-ttu-id="63256-118">Markera **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="63256-118">Select **Add**.</span></span>
1. <span data-ttu-id="63256-119">Välj **Färg**.</span><span class="sxs-lookup"><span data-stu-id="63256-119">Select **Color**.</span></span>
1. <span data-ttu-id="63256-120">Markera **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="63256-120">Select **Add**.</span></span>
1. <span data-ttu-id="63256-121">Välj **Textkonstant**.</span><span class="sxs-lookup"><span data-stu-id="63256-121">Select **Text constant**.</span></span>
1. <span data-ttu-id="63256-122">Skriv ett värde i fältet **Text**.</span><span class="sxs-lookup"><span data-stu-id="63256-122">In the **Text** field, type a value.</span></span>
1. <span data-ttu-id="63256-123">Markera **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="63256-123">Select **Add**.</span></span>
1. <span data-ttu-id="63256-124">Välj **Storlek**.</span><span class="sxs-lookup"><span data-stu-id="63256-124">Select **Size**.</span></span>
1. <span data-ttu-id="63256-125">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="63256-125">Close the page.</span></span>

## <a name="assign-the-nomenclature-to-a-product-master"></a><span data-ttu-id="63256-126">Tilldela nummernomenklaturen till en produktmall</span><span class="sxs-lookup"><span data-stu-id="63256-126">Assign the nomenclature to a product master</span></span>

1. <span data-ttu-id="63256-127">Välj **Produktdimensionsgrupper**.</span><span class="sxs-lookup"><span data-stu-id="63256-127">Select **Product dimension groups**.</span></span>
2. <span data-ttu-id="63256-128">Välj **produktdimensionsgruppen SizeCol**.</span><span class="sxs-lookup"><span data-stu-id="63256-128">Select the **SizeCol product dimension** group.</span></span>
3. <span data-ttu-id="63256-129">Välj **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="63256-129">Select **Edit**.</span></span>
4. <span data-ttu-id="63256-130">Välj **Ja** i fältet **Använd nomenklatur**.</span><span class="sxs-lookup"><span data-stu-id="63256-130">Select **Yes** in the **Use nomenclature** field.</span></span>
5. <span data-ttu-id="63256-131">I fältet **Nomenklatur för produktvariantnummer**, ange eller välj ett värde.</span><span class="sxs-lookup"><span data-stu-id="63256-131">In the **Product variant number nomenclature** field, enter or select a value.</span></span>
6. <span data-ttu-id="63256-132">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="63256-132">Close the page.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]