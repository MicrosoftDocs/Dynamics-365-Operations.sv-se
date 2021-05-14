---
title: Underhåll strukturlista för produktkonfigurationsmodell
description: När du kör den här proceduren krävs en befintlig modell för produktkonfiguration.
author: ShylaThompson
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCProductConfigurationModelDetails, PCBOMLineDetails, InventItemIdLookupSimple
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b4ad73265e321b6339c061a7866b55cb2769954b
ms.sourcegitcommit: fa99a36c3d30d0c0577fd3f63ed6bf2f71599e40
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/20/2021
ms.locfileid: "5921327"
---
# <a name="maintain-bom-for-a-product-configuration-model"></a><span data-ttu-id="9ccdf-103">Underhåll strukturlista för produktkonfigurationsmodell</span><span class="sxs-lookup"><span data-stu-id="9ccdf-103">Maintain BOM for a product configuration model</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="9ccdf-104">När du kör den här proceduren krävs en befintlig modell för produktkonfiguration.</span><span class="sxs-lookup"><span data-stu-id="9ccdf-104">Running this procedure requires an existing product configuration model.</span></span> <span data-ttu-id="9ccdf-105">Högtalarmodellen i demonstrationsföretaget USMF används för att skapa den här proceduren.</span><span class="sxs-lookup"><span data-stu-id="9ccdf-105">The High end speaker model in the demo company USMF is used to create this procedure.</span></span>

## <a name="add-a-bom-line"></a><span data-ttu-id="9ccdf-106">Lägga till en strukturlisterad</span><span class="sxs-lookup"><span data-stu-id="9ccdf-106">Add a BOM line</span></span>

1. <span data-ttu-id="9ccdf-107">Gå till **Produktinformationshantering \> Produkter \> Produktkonfigurationsmodeller**.</span><span class="sxs-lookup"><span data-stu-id="9ccdf-107">Go to **Product information management \> Products \> Product configuration models**.</span></span>
1. <span data-ttu-id="9ccdf-108">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="9ccdf-108">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="9ccdf-109">Välj den avancerade högtalaren till proceduren.</span><span class="sxs-lookup"><span data-stu-id="9ccdf-109">Select the High end speaker for this procedure.</span></span>  
1. <span data-ttu-id="9ccdf-110">Klicka på länken på önskad rad i valda listan.</span><span class="sxs-lookup"><span data-stu-id="9ccdf-110">In the list, select the link in the selected row.</span></span>
1. <span data-ttu-id="9ccdf-111">Expandera avsnittet **Strukturlisterader**.</span><span class="sxs-lookup"><span data-stu-id="9ccdf-111">Expand the **BOM lines** section.</span></span>
1. <span data-ttu-id="9ccdf-112">Markera **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="9ccdf-112">Select **Add**.</span></span>
1. <span data-ttu-id="9ccdf-113">Skriv ett värde i fältet **Namn**.</span><span class="sxs-lookup"><span data-stu-id="9ccdf-113">In the **Name** field, type a value.</span></span>
1. <span data-ttu-id="9ccdf-114">I fältet **Beskrivning** anger du ett värde.</span><span class="sxs-lookup"><span data-stu-id="9ccdf-114">In the **Description** field, type a value.</span></span>
1. <span data-ttu-id="9ccdf-115">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="9ccdf-115">Select **Save**.</span></span>

## <a name="add-bom-line-details"></a><span data-ttu-id="9ccdf-116">Lägga till information om strukturlisterad</span><span class="sxs-lookup"><span data-stu-id="9ccdf-116">Add BOM line details</span></span>

1. <span data-ttu-id="9ccdf-117">Välj **Detaljerad information för strukturlisterader**.</span><span class="sxs-lookup"><span data-stu-id="9ccdf-117">Select **BOM line details**.</span></span>
2. <span data-ttu-id="9ccdf-118">I fältet **artikelnummer** anger du eller väljer ett värde.</span><span class="sxs-lookup"><span data-stu-id="9ccdf-118">In the **Item number** field, enter or select a value.</span></span>
    * <span data-ttu-id="9ccdf-119">Du kan till exempel välja artikeln M0055.</span><span class="sxs-lookup"><span data-stu-id="9ccdf-119">For example, you can select the item M0055.</span></span>  
    * <span data-ttu-id="9ccdf-120">För varje strukturlisteradsegenskap kan du välja om det behövs ett fast värde eller om det ska mappas till ett attribut.</span><span class="sxs-lookup"><span data-stu-id="9ccdf-120">For each BOM line property, you can select if it takes a fixed value or is mapped to an attribute.</span></span>  
3. <span data-ttu-id="9ccdf-121">Markera kryssrutan **Ställ in**.</span><span class="sxs-lookup"><span data-stu-id="9ccdf-121">Select the **Set** check box.</span></span>
4. <span data-ttu-id="9ccdf-122">Välj *Ja* i fältet **Beräkning**.</span><span class="sxs-lookup"><span data-stu-id="9ccdf-122">Select *Yes* in the **Calculation** field.</span></span>
    * <span data-ttu-id="9ccdf-123">När du ställer in egenskapen **Beräkning** som *Ja* garanteras att strukturlisteraden inkluderas i avgiftsberäkningarna.</span><span class="sxs-lookup"><span data-stu-id="9ccdf-123">Setting the **Calculation** property to *Yes* ensures that the BOM line is included in cost calculations.</span></span>  
5. <span data-ttu-id="9ccdf-124">Välj fliken **Inställningar**.</span><span class="sxs-lookup"><span data-stu-id="9ccdf-124">Select the **Setup** tab.</span></span>
6. <span data-ttu-id="9ccdf-125">Markera kryssrutan **Ställ in**.</span><span class="sxs-lookup"><span data-stu-id="9ccdf-125">Select the **Set** check box.</span></span>
7. <span data-ttu-id="9ccdf-126">Ange ett nummer i fältet **Kvantitet**.</span><span class="sxs-lookup"><span data-stu-id="9ccdf-126">In the **Quantity** field, enter a number.</span></span>
    * <span data-ttu-id="9ccdf-127">Kvantitetsfältet bestämmer hur mycket av artikeln som ska inkluderas i strukturlistan.</span><span class="sxs-lookup"><span data-stu-id="9ccdf-127">The quantity field determines how much of the item that will be included in the BOM.</span></span> <span data-ttu-id="9ccdf-128">Detta kan vara en uppenbar kandidat till en attributmappning.</span><span class="sxs-lookup"><span data-stu-id="9ccdf-128">This could be an obvious candidate for an attribute mapping.</span></span>  
8. <span data-ttu-id="9ccdf-129">Välj fliken **Dimension**.</span><span class="sxs-lookup"><span data-stu-id="9ccdf-129">Select the **Dimension** tab.</span></span>
    * <span data-ttu-id="9ccdf-130">Kontrollera om någon av produktdimensionerna är aktiva, och därför måste ha ett värde eller ett attribut.</span><span class="sxs-lookup"><span data-stu-id="9ccdf-130">Verify if any of the product dimensions are active,  and therefore must have a value or attribute assigned.</span></span>  
9. <span data-ttu-id="9ccdf-131">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="9ccdf-131">Select **OK**.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]