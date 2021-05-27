---
title: Inställningar för leveransinformation
description: I det här avsnittet beskrivs hur du ställer in leveransinformation för modulen hemtagningskostnad.
author: sherry-zheng
ms.date: 12/04/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ITMGoodsDescriptionTable, ITMVesselTable, ITMExporterTable, ITMCommodityCodeTable, ITMCustomsDescription
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2020-12-04
ms.dyn365.ops.version: Release 10.0.17
ms.openlocfilehash: 5093e42b0b5247c24c271ad50c80889516586d58
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/11/2021
ms.locfileid: "6020897"
---
# <a name="shipping-information-setup"></a><span data-ttu-id="ad27b-103">Inställningar för leveransinformation</span><span class="sxs-lookup"><span data-stu-id="ad27b-103">Shipping information setup</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="ad27b-104">I det här avsnittet beskrivs hur du ställer in leveransinformation för modulen **hemtagningskostnad**.</span><span class="sxs-lookup"><span data-stu-id="ad27b-104">This topic describes how to set up shipping information for the **Landed cost** module.</span></span>

## <a name="description-of-goods"></a><a name="description-of-goods"></a><span data-ttu-id="ad27b-105">Beskrivning av varor</span><span class="sxs-lookup"><span data-stu-id="ad27b-105">Description of goods</span></span>

<span data-ttu-id="ad27b-106">Beskrivningar av varor gör det möjligt att identifiera en leveransbehållare eller ett folio för gods som finns i den.</span><span class="sxs-lookup"><span data-stu-id="ad27b-106">Descriptions of goods help identify a voyage, shipping container, or folio of goods, and the goods in it.</span></span> <span data-ttu-id="ad27b-107">Du kan välja en beskrivning av gods i leveransbehållarens rubrik eller i folio sidhuvud.</span><span class="sxs-lookup"><span data-stu-id="ad27b-107">You can select a description of goods on the shipping container header or the folio header.</span></span>

<span data-ttu-id="ad27b-108">Om du vill arbeta med beskrivningar av varor går du till **Hemtagningskostnad \> Inställning av leveransinformation \> Beskrivning av varor**.</span><span class="sxs-lookup"><span data-stu-id="ad27b-108">To work with descriptions of goods, go to **Landed cost \> Shipping information setup \> Description of goods**.</span></span> <span data-ttu-id="ad27b-109">Där kan du visa, öppna, skapa och ta bort poster för varubeskrivningar.</span><span class="sxs-lookup"><span data-stu-id="ad27b-109">There, you can view, open, create, and delete records for descriptions of goods.</span></span> <span data-ttu-id="ad27b-110">Följande register beskriver de fält som är tillgängliga för varje post.</span><span class="sxs-lookup"><span data-stu-id="ad27b-110">The following table describes the fields that are available for each record.</span></span>

| <span data-ttu-id="ad27b-111">Fält</span><span class="sxs-lookup"><span data-stu-id="ad27b-111">Field</span></span> | <span data-ttu-id="ad27b-112">beskrivning</span><span class="sxs-lookup"><span data-stu-id="ad27b-112">Description</span></span> |
|---|---|
| <span data-ttu-id="ad27b-113">Beskrivning av varor</span><span class="sxs-lookup"><span data-stu-id="ad27b-113">Description of goods</span></span> | <span data-ttu-id="ad27b-114">Ange ett unikt ID-namn/nummer för den typ av varor som kommer att använda den här beskrivningen.</span><span class="sxs-lookup"><span data-stu-id="ad27b-114">Enter a unique identification name/number for the type of goods that will use this description.</span></span> |
| <span data-ttu-id="ad27b-115">beskrivning</span><span class="sxs-lookup"><span data-stu-id="ad27b-115">Description</span></span> | <span data-ttu-id="ad27b-116">Ange en beskrivning av typen av varor i denna kategori.</span><span class="sxs-lookup"><span data-stu-id="ad27b-116">Enter a description of the type of goods in this category.</span></span> |

## <a name="vessels"></a><a name="vessels"></a><span data-ttu-id="ad27b-117">Fartyg</span><span class="sxs-lookup"><span data-stu-id="ad27b-117">Vessels</span></span>

<span data-ttu-id="ad27b-118">Ett fartyg är det unika namn som ett skepp eller fartyg som ett transportföretag eller en förmedling använder.</span><span class="sxs-lookup"><span data-stu-id="ad27b-118">A vessel is the unique name of a ship or vessel that a shipping company or agency uses.</span></span> <span data-ttu-id="ad27b-119">När du skapar en färd måste du alltid välja eller ange att du inte ska använda ett fartyg för den.</span><span class="sxs-lookup"><span data-stu-id="ad27b-119">When you create a voyage, you must always either select or enter a vessel for it.</span></span> <span data-ttu-id="ad27b-120">Om du ofta använder samma fartyg kan du göra det snabbare och enklare att skapa en ny färd genom att skapa en fartygspost och på så sätt göra det möjligt för användarna att välja ur en lista istället för att ange namnet eller numret manuellt varje gång.</span><span class="sxs-lookup"><span data-stu-id="ad27b-120">If you often use the same vessels, then you can make it faster and easier to create a new voyage by creating a vessel record for each of them, thereby allowing users to select the vessel from a list rather then enter the name or number manually each time.</span></span>

<span data-ttu-id="ad27b-121">Om du vill arbeta med fartyg, gå till **Hemtagningskostnad \> Inställning av leveransinformation \> Fartyg**.</span><span class="sxs-lookup"><span data-stu-id="ad27b-121">To work with vessels, go to **Landed cost \> Shipping information setup \> Vessels**.</span></span> <span data-ttu-id="ad27b-122">Där kan du visa, öppna, skapa och ta bort poster för fartyg.</span><span class="sxs-lookup"><span data-stu-id="ad27b-122">There, you can view, open, create, and delete records for vessels.</span></span> <span data-ttu-id="ad27b-123">Följande register beskriver de fält som är tillgängliga för varje post.</span><span class="sxs-lookup"><span data-stu-id="ad27b-123">The following table describes the fields that are available for each record.</span></span>

| <span data-ttu-id="ad27b-124">Fält</span><span class="sxs-lookup"><span data-stu-id="ad27b-124">Field</span></span> | <span data-ttu-id="ad27b-125">beskrivning</span><span class="sxs-lookup"><span data-stu-id="ad27b-125">Description</span></span> |
|---|---|
| <span data-ttu-id="ad27b-126">Fartyg</span><span class="sxs-lookup"><span data-stu-id="ad27b-126">Vessel</span></span> | <span data-ttu-id="ad27b-127">Ange ett unikt ID-namn/nummer för det skepp som ska användas vid transport av gods i en färd.</span><span class="sxs-lookup"><span data-stu-id="ad27b-127">Enter a unique identification name/number for the ship that will be used to transport goods on a voyage.</span></span> |
| <span data-ttu-id="ad27b-128">beskrivning</span><span class="sxs-lookup"><span data-stu-id="ad27b-128">Description</span></span> | <span data-ttu-id="ad27b-129">Ange en beskrivning av fartyget.</span><span class="sxs-lookup"><span data-stu-id="ad27b-129">Enter a description of the vessel.</span></span> <span data-ttu-id="ad27b-130">Vanligtvis identifierar denna beskrivning namnet på transportföretaget/agenten.</span><span class="sxs-lookup"><span data-stu-id="ad27b-130">Typically, this description identifies the name of the ship and the shipping company/agent.</span></span> |
| <span data-ttu-id="ad27b-131">Leveranssätt</span><span class="sxs-lookup"><span data-stu-id="ad27b-131">Mode of delivery</span></span> | <span data-ttu-id="ad27b-132">Välj det leveranssätt som fartyget använder (t.ex. _Flyg_, _Fartyg_ eller _Tåg_).</span><span class="sxs-lookup"><span data-stu-id="ad27b-132">Select the mode of delivery that the vessel uses (such as _Air_, _Ocean_, or _Train_).</span></span> |

## <a name="exporters"></a><span data-ttu-id="ad27b-133">Exportörer</span><span class="sxs-lookup"><span data-stu-id="ad27b-133">Exporters</span></span>

<span data-ttu-id="ad27b-134">Varje exportörpost identifierar en leverantör eller exportör som kan definieras som leverantör för en kund.</span><span class="sxs-lookup"><span data-stu-id="ad27b-134">Each exporter record identifies a vendor or exporter that can be defined as the vendor for a voyage.</span></span> <span data-ttu-id="ad27b-135">Exportören kan kopplas till en exportör och användas för rapportering.</span><span class="sxs-lookup"><span data-stu-id="ad27b-135">The exporter can be associated with a voyage and used for reporting.</span></span>

<span data-ttu-id="ad27b-136">Om du vill arbeta med exportörer, gå till **Hemtagningskostnad \> Inställning av leveransinformation \> exportörer**.</span><span class="sxs-lookup"><span data-stu-id="ad27b-136">To work with exporters, go to **Landed cost \> Shipping information setup \> Exporters**.</span></span> <span data-ttu-id="ad27b-137">Där kan du visa, öppna, skapa och ta bort poster för exportörer.</span><span class="sxs-lookup"><span data-stu-id="ad27b-137">There, you can view, open, create, and delete records for exporters.</span></span> <span data-ttu-id="ad27b-138">Följande register beskriver de fält som är tillgängliga för varje post.</span><span class="sxs-lookup"><span data-stu-id="ad27b-138">The following table describes the fields that are available for each record.</span></span>

| <span data-ttu-id="ad27b-139">Fält</span><span class="sxs-lookup"><span data-stu-id="ad27b-139">Field</span></span> | <span data-ttu-id="ad27b-140">beskrivning</span><span class="sxs-lookup"><span data-stu-id="ad27b-140">Description</span></span> |
|---|---|
| <span data-ttu-id="ad27b-141">Exportör</span><span class="sxs-lookup"><span data-stu-id="ad27b-141">Exporter</span></span> | <span data-ttu-id="ad27b-142">Ange ett unikt ID-namn/nummer för den exportör av varor som transporteras på en färd.</span><span class="sxs-lookup"><span data-stu-id="ad27b-142">Enter a unique identification name/number for the exporter of goods that are transported on a voyage.</span></span> |
| <span data-ttu-id="ad27b-143">beskrivning</span><span class="sxs-lookup"><span data-stu-id="ad27b-143">Description</span></span> | <span data-ttu-id="ad27b-144">Ange en beskrivning av exportören.</span><span class="sxs-lookup"><span data-stu-id="ad27b-144">Enter a description of the exporter.</span></span> <span data-ttu-id="ad27b-145">Vanligtvis identifierar denna beskrivning det fullständiga namnet på transportföretaget/agenten.</span><span class="sxs-lookup"><span data-stu-id="ad27b-145">Typically, this description identifies the full name of the shipping company/agent.</span></span> |

## <a name="commodity-codes"></a><span data-ttu-id="ad27b-146">Artikelkoder</span><span class="sxs-lookup"><span data-stu-id="ad27b-146">Commodity codes</span></span>

<span data-ttu-id="ad27b-147">Du använder artikelkoder som hjälp när du vill tullidentifiera och beräkna tullsatser för varor på en gång.</span><span class="sxs-lookup"><span data-stu-id="ad27b-147">You use commodity codes to help with customs identification and the calculation of duty rates for goods on a voyage.</span></span> <span data-ttu-id="ad27b-148">Du kan välja artikelkoder på sidan **Frisläppta produkter**.</span><span class="sxs-lookup"><span data-stu-id="ad27b-148">You can select commodity codes on the **Released products** page.</span></span>

<span data-ttu-id="ad27b-149">Om du vill arbeta med artikelkoder, gå till **Hemtagningskostnad \> Inställning av leveransinformation \> Artikelkoder**.</span><span class="sxs-lookup"><span data-stu-id="ad27b-149">To work with commodity codes, go to **Landed cost \> Shipping information setup \> Commodity codes**.</span></span> <span data-ttu-id="ad27b-150">Där kan du visa, öppna, skapa och ta bort poster för artikelkoder.</span><span class="sxs-lookup"><span data-stu-id="ad27b-150">There, you can view, open, create, and delete records for commodity codes.</span></span> <span data-ttu-id="ad27b-151">Följande register beskriver de fält som är tillgängliga för varje post.</span><span class="sxs-lookup"><span data-stu-id="ad27b-151">The following table describes the fields that are available for each record.</span></span>

| <span data-ttu-id="ad27b-152">Fält</span><span class="sxs-lookup"><span data-stu-id="ad27b-152">Field</span></span> | <span data-ttu-id="ad27b-153">beskrivning</span><span class="sxs-lookup"><span data-stu-id="ad27b-153">Description</span></span> |
|---|---|
| <span data-ttu-id="ad27b-154">Artikelkod</span><span class="sxs-lookup"><span data-stu-id="ad27b-154">Commodity code</span></span> | <span data-ttu-id="ad27b-155">Ange en unik kod för den här typen av vara.</span><span class="sxs-lookup"><span data-stu-id="ad27b-155">Enter a unique code for this type of commodity.</span></span> |
| <span data-ttu-id="ad27b-156">beskrivning</span><span class="sxs-lookup"><span data-stu-id="ad27b-156">Description</span></span> | <span data-ttu-id="ad27b-157">Ange en beskrivning av artikelkoder.</span><span class="sxs-lookup"><span data-stu-id="ad27b-157">Enter a description of the commodity type.</span></span> |

## <a name="customs-description"></a><span data-ttu-id="ad27b-158">Tullbeskrivning</span><span class="sxs-lookup"><span data-stu-id="ad27b-158">Customs description</span></span>

<span data-ttu-id="ad27b-159">Med hjälp av tullbeskrivningar kan varor identifieras för tulländamål.</span><span class="sxs-lookup"><span data-stu-id="ad27b-159">Customs descriptions help identify goods for customs purposes.</span></span> <span data-ttu-id="ad27b-160">Du kan välja en tullbeskrivning på sidan **Frisläppta produkter** eller på inköpsorderrader.</span><span class="sxs-lookup"><span data-stu-id="ad27b-160">You can select a customs description on the **Released products** page or on purchase order lines.</span></span>

<span data-ttu-id="ad27b-161">Om du vill arbeta med tullbeskrivningar av varor går du till **Hemtagningskostnad \> Inställning av leveransinformation \> Tullbeskrivning**.</span><span class="sxs-lookup"><span data-stu-id="ad27b-161">To work with customs descriptions, go to **Landed cost \> Shipping information setup \> Customs description**.</span></span> <span data-ttu-id="ad27b-162">Där kan du visa, öppna, skapa och ta bort poster för tullbeskrivningar.</span><span class="sxs-lookup"><span data-stu-id="ad27b-162">There, you can view, open, create, and delete records for custom descriptions.</span></span> <span data-ttu-id="ad27b-163">Följande register beskriver de fält som är tillgängliga för varje post.</span><span class="sxs-lookup"><span data-stu-id="ad27b-163">The following table describes the fields that are available for each record.</span></span>

| <span data-ttu-id="ad27b-164">Fält</span><span class="sxs-lookup"><span data-stu-id="ad27b-164">Field</span></span> | <span data-ttu-id="ad27b-165">beskrivning</span><span class="sxs-lookup"><span data-stu-id="ad27b-165">Description</span></span> |
|---|---|
| <span data-ttu-id="ad27b-166">Tullbeskrivning</span><span class="sxs-lookup"><span data-stu-id="ad27b-166">Customs description</span></span> | <span data-ttu-id="ad27b-167">Ange en unik kod för den här typen av tullklassificering.</span><span class="sxs-lookup"><span data-stu-id="ad27b-167">Enter a unique code for this type of customs classification.</span></span> <span data-ttu-id="ad27b-168">Ofta blir den här koden den officiella beskrivningen som ges av en tullmyndighet för beskrivningen av och det kvalitativa värdet av varorna.</span><span class="sxs-lookup"><span data-stu-id="ad27b-168">Often, this code will be the official description that is provided by a customs authority for the description and qualitative value of the goods.</span></span> |
| <span data-ttu-id="ad27b-169">beskrivning</span><span class="sxs-lookup"><span data-stu-id="ad27b-169">Description</span></span> | <span data-ttu-id="ad27b-170">Ange en beskrivning av tullklassificeringen.</span><span class="sxs-lookup"><span data-stu-id="ad27b-170">Enter a description of the customs classification.</span></span> |
