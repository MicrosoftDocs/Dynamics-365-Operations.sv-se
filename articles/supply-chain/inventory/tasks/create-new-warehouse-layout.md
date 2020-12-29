---
title: Skapa en ny layout för lagerställe
description: I det här avsnittet beskrivs hur du ställer in information om platser i ett lagerställe.
author: perlynne
manager: tfehr
ms.date: 07/29/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventParameters, DefaultDashboard, InventLocation, WMSLocationWizard
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 09666e95cc90913f1bf8555b9ff2c48aa55369ed
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "4437933"
---
# <a name="create-a-new-warehouse-layout"></a><span data-ttu-id="9bebe-103">Skapa en ny layout för lagerställe</span><span class="sxs-lookup"><span data-stu-id="9bebe-103">Create a new warehouse layout</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="9bebe-104">I det här avsnittet beskrivs hur du ställer in information om platser i ett lagerställe.</span><span class="sxs-lookup"><span data-stu-id="9bebe-104">This topic describes how to set up information about the locations in a warehouse.</span></span> <span data-ttu-id="9bebe-105">Detta gäller endast lagerställen som skapats med hjälp av ”grundläggande lagerstyrning” i lagerhanteringmodulen och inte för lagerställen som skapats i lagerstyrningsmodulen.</span><span class="sxs-lookup"><span data-stu-id="9bebe-105">This applies only to warehouses created using "basic warehousing" in the Inventory management module, not to warehouses created in the Warehouse management module.</span></span> <span data-ttu-id="9bebe-106">Du kan använda den här proceduren i demonstrationsföretaget USMF eller med dina egna data.</span><span class="sxs-lookup"><span data-stu-id="9bebe-106">You can use this procedure in demo data company USMF, or on your own data.</span></span>


## <a name="set-the-default-location-capacity"></a><span data-ttu-id="9bebe-107">Ange standardplatskapaciteten</span><span class="sxs-lookup"><span data-stu-id="9bebe-107">Set the default location capacity</span></span>
1. <span data-ttu-id="9bebe-108">I navigeringsfönstret, gå till **Moduler > Lagerhantering > Inställningar > Parametrar för hantering av lager och lagerstyrning**.</span><span class="sxs-lookup"><span data-stu-id="9bebe-108">In the navigation pane, go to **Modules > Inventory management > Setup > Inventory and warehouse management parameters**.</span></span>
2. <span data-ttu-id="9bebe-109">Välj fliken **Platser**.</span><span class="sxs-lookup"><span data-stu-id="9bebe-109">Select the **Locations** tab.</span></span>
3. <span data-ttu-id="9bebe-110">Välj ett nummer i fältet **Standardbredd.**</span><span class="sxs-lookup"><span data-stu-id="9bebe-110">In the **Standard width** field, enter a number.</span></span>
4. <span data-ttu-id="9bebe-111">Välj ett nummer i fältet **Standarddjup.**</span><span class="sxs-lookup"><span data-stu-id="9bebe-111">In the **Standard depth** field, enter a number.</span></span>
5. <span data-ttu-id="9bebe-112">Välj ett nummer i fältet **Standardhöjd.**</span><span class="sxs-lookup"><span data-stu-id="9bebe-112">In the **Standard height** field, enter a number.</span></span>
6. <span data-ttu-id="9bebe-113">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="9bebe-113">Select **Save**.</span></span>
7. <span data-ttu-id="9bebe-114">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="9bebe-114">Close the page.</span></span>

## <a name="define-the-location-name-format"></a><span data-ttu-id="9bebe-115">Definiera platsnamnformatet</span><span class="sxs-lookup"><span data-stu-id="9bebe-115">Define the location name format</span></span>
1. <span data-ttu-id="9bebe-116">I navigeringsfönstret, gå till **Moduler > Lagerhantering > Inställningar > Lagerindelning > Lagerställen**.</span><span class="sxs-lookup"><span data-stu-id="9bebe-116">In the navigation pane, go to **Modules > Inventory management > Setup > Inventory breakdown > Warehouses**.</span></span>
2. <span data-ttu-id="9bebe-117">Välj **Ny**.</span><span class="sxs-lookup"><span data-stu-id="9bebe-117">Select **New**.</span></span>
3. <span data-ttu-id="9bebe-118">Ange ett värde i fältet **Lagerställe**.</span><span class="sxs-lookup"><span data-stu-id="9bebe-118">In the **Warehouse** field, type a value.</span></span>
4. <span data-ttu-id="9bebe-119">Skriv ett värde i fältet **Namn**.</span><span class="sxs-lookup"><span data-stu-id="9bebe-119">In the **Name** field, type a value.</span></span>
5. <span data-ttu-id="9bebe-120">På fält **Plats** klicka på önskad post från sökningen.</span><span class="sxs-lookup"><span data-stu-id="9bebe-120">In the **Site** field, select the desired record in the lookup.</span></span>
6. <span data-ttu-id="9bebe-121">Växla utökningen av avsnittet **Platsnamn**.</span><span class="sxs-lookup"><span data-stu-id="9bebe-121">Toggle the expansion of the **Location names** section.</span></span> <span data-ttu-id="9bebe-122">Alternativen i detta avsnitt definierar standardformatet på platsnamn.</span><span class="sxs-lookup"><span data-stu-id="9bebe-122">The options in this section define the default format for location names.</span></span> <span data-ttu-id="9bebe-123">I vårt exempel ska vi inkludera gångnummer, ställningsnummer och hyllnummer.</span><span class="sxs-lookup"><span data-stu-id="9bebe-123">In our example, we'll include the aisle number, rack number and shelf number.</span></span>  
7. <span data-ttu-id="9bebe-124">Ange alternativet **Inkludera gång** till **Ja**.</span><span class="sxs-lookup"><span data-stu-id="9bebe-124">Set the **Include aisle** option to **Yes**.</span></span>
8. <span data-ttu-id="9bebe-125">Ange alternativet **Inkludera ställning** till **Ja**.</span><span class="sxs-lookup"><span data-stu-id="9bebe-125">Set the **Include rack** option to **Yes**.</span></span> 
9. <span data-ttu-id="9bebe-126">I fältet **Format** skriver du in ett värde för ställningen.</span><span class="sxs-lookup"><span data-stu-id="9bebe-126">In the **Format** field, for the rack, type a value.</span></span>
10. <span data-ttu-id="9bebe-127">Ange alternativet **Inkludera hylla** till **Ja**.</span><span class="sxs-lookup"><span data-stu-id="9bebe-127">Set the **Include shelf** option to **Yes**.</span></span>
11. <span data-ttu-id="9bebe-128">I fältet **Format** skriver du in ett värde för hyllan.</span><span class="sxs-lookup"><span data-stu-id="9bebe-128">In the **Format** field, for the shelf, type a value.</span></span>

## <a name="define-warehouse-locations"></a><span data-ttu-id="9bebe-129">Definiera lagerställesplatser</span><span class="sxs-lookup"><span data-stu-id="9bebe-129">Define warehouse locations</span></span>
1. <span data-ttu-id="9bebe-130">Klicka på **Lagerställe** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="9bebe-130">On the Action Pane, select **Warehouse**.</span></span>
2. <span data-ttu-id="9bebe-131">Välj **Platsguide**.</span><span class="sxs-lookup"><span data-stu-id="9bebe-131">Select **Location Wizard**.</span></span>
3. <span data-ttu-id="9bebe-132">Välj **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="9bebe-132">Select **Next**.</span></span>
4. <span data-ttu-id="9bebe-133">Avmarkera alternativet **Utlastningsplatser**</span><span class="sxs-lookup"><span data-stu-id="9bebe-133">De-select the **Outbound docks** option</span></span>
5. <span data-ttu-id="9bebe-134">Avmarkera alternativet **Bulkplatser**</span><span class="sxs-lookup"><span data-stu-id="9bebe-134">De-select the **Bulk locations** option</span></span>
6. <span data-ttu-id="9bebe-135">Välj **Nästa** tills du kommer till det här alternativet för att välja **Slutför**.</span><span class="sxs-lookup"><span data-stu-id="9bebe-135">Select **Next** until you come to the option to select **Finish**.</span></span>
7. <span data-ttu-id="9bebe-136">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="9bebe-136">Close the page.</span></span>
8. <span data-ttu-id="9bebe-137">Uppdatera sidan.</span><span class="sxs-lookup"><span data-stu-id="9bebe-137">Refresh the page.</span></span>

