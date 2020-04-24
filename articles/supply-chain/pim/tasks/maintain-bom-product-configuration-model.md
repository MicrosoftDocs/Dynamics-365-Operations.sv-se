---
title: Underhåll strukturlista för produktkonfigurationsmodell
description: När du kör den här proceduren krävs en befintlig modell för produktkonfiguration.
author: ShylaThompson
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCProductConfigurationModelDetails, PCBOMLineDetails, InventItemIdLookupSimple
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 1aa2a22056ff4435d4c66f13c170aeadc02fbe03
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/02/2020
ms.locfileid: "3203582"
---
# <a name="maintain-bom-for-a-product-configuration-model"></a><span data-ttu-id="d92eb-103">Underhåll strukturlista för produktkonfigurationsmodell</span><span class="sxs-lookup"><span data-stu-id="d92eb-103">Maintain BOM for a product configuration model</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="d92eb-104">När du kör den här proceduren krävs en befintlig modell för produktkonfiguration.</span><span class="sxs-lookup"><span data-stu-id="d92eb-104">Running this procedure requires an existing product configuration model.</span></span> <span data-ttu-id="d92eb-105">Högtalarmodellen i demonstrationsföretaget USMF används för att skapa den här proceduren.</span><span class="sxs-lookup"><span data-stu-id="d92eb-105">The High end speaker model in the demo company USMF is used to create this procedure.</span></span>


## <a name="add-a-bom-line"></a><span data-ttu-id="d92eb-106">Lägga till en strukturlisterad</span><span class="sxs-lookup"><span data-stu-id="d92eb-106">Add a BOM line</span></span>
1. <span data-ttu-id="d92eb-107">Klicka på Definition av produktvariantmodell.</span><span class="sxs-lookup"><span data-stu-id="d92eb-107">Click Product variant model definition.</span></span>
2. <span data-ttu-id="d92eb-108">Klicka på Modeller för produktkonfiguration.</span><span class="sxs-lookup"><span data-stu-id="d92eb-108">Click Product configuration models.</span></span>
3. <span data-ttu-id="d92eb-109">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="d92eb-109">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="d92eb-110">Välj den avancerade högtalaren till proceduren.</span><span class="sxs-lookup"><span data-stu-id="d92eb-110">Select the High end speaker for this procedure.</span></span>  
4. <span data-ttu-id="d92eb-111">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="d92eb-111">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="d92eb-112">Expandera avsnittet Strukturlisterader.</span><span class="sxs-lookup"><span data-stu-id="d92eb-112">Expand the BOM lines section.</span></span>
6. <span data-ttu-id="d92eb-113">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="d92eb-113">Click Add.</span></span>
7. <span data-ttu-id="d92eb-114">Skriv ett värde i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="d92eb-114">In the Name field, type a value.</span></span>
8. <span data-ttu-id="d92eb-115">Ange ett värde i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="d92eb-115">In the Description field, type a value.</span></span>
9. <span data-ttu-id="d92eb-116">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="d92eb-116">Click Save.</span></span>

## <a name="add-bom-line-details"></a><span data-ttu-id="d92eb-117">Lägga till information om strukturlisterad</span><span class="sxs-lookup"><span data-stu-id="d92eb-117">Add BOM line details</span></span>
1. <span data-ttu-id="d92eb-118">Klicka på Information för strukturlisterad.</span><span class="sxs-lookup"><span data-stu-id="d92eb-118">Click BOM line details.</span></span>
2. <span data-ttu-id="d92eb-119">Ange eller välj ett värde i fältet Artikelnummer.</span><span class="sxs-lookup"><span data-stu-id="d92eb-119">In the Item number field, enter or select a value.</span></span>
    * <span data-ttu-id="d92eb-120">Du kan till exempel välja artikeln M0055.</span><span class="sxs-lookup"><span data-stu-id="d92eb-120">For example, you can select the item M0055.</span></span>  
    * <span data-ttu-id="d92eb-121">För varje strukturlisteradsegenskap kan du välja om det behövs ett fast värde eller om det ska mappas till ett attribut.</span><span class="sxs-lookup"><span data-stu-id="d92eb-121">For each BOM line property, you can select if it takes a fixed value or is mapped to an attribute.</span></span>  
3. <span data-ttu-id="d92eb-122">Markera kryssrutan Uppsättning.</span><span class="sxs-lookup"><span data-stu-id="d92eb-122">Select the Set check box.</span></span>
4. <span data-ttu-id="d92eb-123">Välj Ja i fältet Beräkning.</span><span class="sxs-lookup"><span data-stu-id="d92eb-123">Select Yes in the Calculation field.</span></span>
    * <span data-ttu-id="d92eb-124">När du ställer in beräkningsegenskapen på Ja garanteras att strukturlisteraden ingår i kostnadsberäkningarna.</span><span class="sxs-lookup"><span data-stu-id="d92eb-124">Setting the Calculation property to Yes ensures that the BOM line is included in cost calculations.</span></span>  
5. <span data-ttu-id="d92eb-125">Klicka på fliken Inställningar.</span><span class="sxs-lookup"><span data-stu-id="d92eb-125">Click the Setup tab.</span></span>
6. <span data-ttu-id="d92eb-126">Markera kryssrutan Uppsättning.</span><span class="sxs-lookup"><span data-stu-id="d92eb-126">Select the Set check box.</span></span>
7. <span data-ttu-id="d92eb-127">Ange ett tal i fältet Kvantitet.</span><span class="sxs-lookup"><span data-stu-id="d92eb-127">In the Quantity field, enter a number.</span></span>
    * <span data-ttu-id="d92eb-128">Kvantitetsfältet bestämmer hur mycket av artikeln som ska inkluderas i strukturlistan.</span><span class="sxs-lookup"><span data-stu-id="d92eb-128">The quantity field determines how much of the item that will be included in the BOM.</span></span> <span data-ttu-id="d92eb-129">Detta kan vara en uppenbar kandidat till en attributmappning.</span><span class="sxs-lookup"><span data-stu-id="d92eb-129">This could be an obvious candidate for an attribute mapping.</span></span>  
8. <span data-ttu-id="d92eb-130">Klicka på fliken Dimension.</span><span class="sxs-lookup"><span data-stu-id="d92eb-130">Click the Dimension tab.</span></span>
    * <span data-ttu-id="d92eb-131">Kontrollera om någon av produktdimensionerna är aktiva, och därför måste ha ett värde eller ett attribut.</span><span class="sxs-lookup"><span data-stu-id="d92eb-131">Verify if any of the product dimensions are active,  and therefore must have a value or attribute assigned.</span></span>  
9. <span data-ttu-id="d92eb-132">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="d92eb-132">Click OK.</span></span>

