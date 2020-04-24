---
title: Skapa en produktnummernomenklatur för fördefinierade produktvarianter
description: Detta avsnitt visar dig hur du skapar en produktnummernomenklatur för fördefinierade produktvarianter, samt hur du tilldelar denna till lämplig produktdimensionsgrupp.
author: ShylaThompson
manager: tfehr
ms.date: 08/20/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, EcoResNomenclature, EcoResProductDimensionGroup
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: c39d383c15bcc838e09bc417f7e961c3647828da
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/02/2020
ms.locfileid: "3213295"
---
# <a name="create-a-product-number-nomenclature-for-predefined-product-variants"></a><span data-ttu-id="dbaed-103">Skapa en produktnummernomenklatur för fördefinierade produktvarianter</span><span class="sxs-lookup"><span data-stu-id="dbaed-103">Create a product number nomenclature for predefined product variants</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="dbaed-104">Detta avsnitt visar dig hur du skapar en produktnummernomenklatur för fördefinierade produktvarianter, samt hur du tilldelar denna till lämplig produktdimensionsgrupp.</span><span class="sxs-lookup"><span data-stu-id="dbaed-104">This topic explains how to set up a product number nomenclature for predefined product variants, and how you assign it to the appropriate product dimension group.</span></span> <span data-ttu-id="dbaed-105">Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF.</span><span class="sxs-lookup"><span data-stu-id="dbaed-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="dbaed-106">Den nya produktnummernomenklaturen tilldelas till produktdimensionsgruppen Color and Size.</span><span class="sxs-lookup"><span data-stu-id="dbaed-106">The new product number nomenclature is assigned to the Color and Size product dimension group.</span></span> <span data-ttu-id="dbaed-107">Den här uppgiften utförs vanligtvis av en produktdesigner.</span><span class="sxs-lookup"><span data-stu-id="dbaed-107">This task would typically be done by a product designer.</span></span>


## <a name="create-a-product-number-nomenclature"></a><span data-ttu-id="dbaed-108">Skapa en nomenklatur för produktnummer</span><span class="sxs-lookup"><span data-stu-id="dbaed-108">Create a product number nomenclature</span></span>
1. <span data-ttu-id="dbaed-109">Välj **Definition av produktvariantmodell**.</span><span class="sxs-lookup"><span data-stu-id="dbaed-109">Select **Product variant model definition**.</span></span>
2. <span data-ttu-id="dbaed-110">Välj **Produktnomenklatur**.</span><span class="sxs-lookup"><span data-stu-id="dbaed-110">Select **Product nomenclature**.</span></span>
3. <span data-ttu-id="dbaed-111">Välj **Ny**.</span><span class="sxs-lookup"><span data-stu-id="dbaed-111">Select **New**.</span></span>
4. <span data-ttu-id="dbaed-112">I fältet **Namn** anger du ett nomenklatursnamn som gör det enkelt att identifiera målproduktdimensionsgruppen, till exempel `ColorSize`.</span><span class="sxs-lookup"><span data-stu-id="dbaed-112">In the **Name** field, enter a nomenclature name that helps to identify the target product dimension group, for example, `ColorSize`.</span></span>
5. <span data-ttu-id="dbaed-113">I fältet **Beskrivning** anger du ett värde.</span><span class="sxs-lookup"><span data-stu-id="dbaed-113">In the **Description** field, type a value.</span></span>
6. <span data-ttu-id="dbaed-114">Markera **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="dbaed-114">Select **Add**.</span></span>
7. <span data-ttu-id="dbaed-115">Välj **Produktmallsnummer**.</span><span class="sxs-lookup"><span data-stu-id="dbaed-115">Select **Product master** number.</span></span>
8. <span data-ttu-id="dbaed-116">Markera **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="dbaed-116">Select **Add**.</span></span>
9. <span data-ttu-id="dbaed-117">Välj **Textkonstant**.</span><span class="sxs-lookup"><span data-stu-id="dbaed-117">Select **Text constant**.</span></span>
10. <span data-ttu-id="dbaed-118">Skriv ett värde i fältet **Text**.</span><span class="sxs-lookup"><span data-stu-id="dbaed-118">In the **Text** field, type a value.</span></span>
11. <span data-ttu-id="dbaed-119">Markera **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="dbaed-119">Select **Add**.</span></span>
12. <span data-ttu-id="dbaed-120">Välj **Färg**.</span><span class="sxs-lookup"><span data-stu-id="dbaed-120">Select **Color**.</span></span>
13. <span data-ttu-id="dbaed-121">Markera **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="dbaed-121">Select **Add**.</span></span>
14. <span data-ttu-id="dbaed-122">Välj **Textkonstant**.</span><span class="sxs-lookup"><span data-stu-id="dbaed-122">Select **Text constant**.</span></span>
15. <span data-ttu-id="dbaed-123">Skriv ett värde i fältet **Text**.</span><span class="sxs-lookup"><span data-stu-id="dbaed-123">In the **Text** field, type a value.</span></span>
16. <span data-ttu-id="dbaed-124">Markera **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="dbaed-124">Select **Add**.</span></span>
17. <span data-ttu-id="dbaed-125">Välj **Storlek**.</span><span class="sxs-lookup"><span data-stu-id="dbaed-125">Select **Size**.</span></span>
18. <span data-ttu-id="dbaed-126">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="dbaed-126">Close the page.</span></span>

## <a name="assign-the-nomenclature-to-a-product-master"></a><span data-ttu-id="dbaed-127">Tilldela nummernomenklaturen till en produktmall</span><span class="sxs-lookup"><span data-stu-id="dbaed-127">Assign the nomenclature to a product master</span></span>
1. <span data-ttu-id="dbaed-128">Välj **Produktdimensionsgrupper**.</span><span class="sxs-lookup"><span data-stu-id="dbaed-128">Select **Product dimension groups**.</span></span>
2. <span data-ttu-id="dbaed-129">Välj **produktdimensionsgruppen SizeCol**.</span><span class="sxs-lookup"><span data-stu-id="dbaed-129">Select the **SizeCol product dimension** group.</span></span>
3. <span data-ttu-id="dbaed-130">Välj **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="dbaed-130">Select **Edit**.</span></span>
4. <span data-ttu-id="dbaed-131">Välj **Ja** i fältet **Använd nomenklatur**.</span><span class="sxs-lookup"><span data-stu-id="dbaed-131">Select **Yes** in the **Use nomenclature** field.</span></span>
5. <span data-ttu-id="dbaed-132">I fältet **Nomenklatur för produktvariantnummer**, ange eller välj ett värde.</span><span class="sxs-lookup"><span data-stu-id="dbaed-132">In the **Product variant number nomenclature** field, enter or select a value.</span></span>
6. <span data-ttu-id="dbaed-133">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="dbaed-133">Close the page.</span></span>

