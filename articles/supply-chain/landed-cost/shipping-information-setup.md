---
title: Inställningar för leveransinformation
description: I det här avsnittet beskrivs hur du ställer in leveransinformation för modulen hemtagningskostnad.
author: sherry-zheng
manager: tfehr
ms.date: 12/04/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ITMGoodsDescriptionTable, ITMVesselTable, ITMExporterTable, ITMCommodityCodeTable, ITMCustomsDescription
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2020-12-04
ms.dyn365.ops.version: Release 10.0.17
ms.openlocfilehash: 90794a154eb2a63f33277383cda80323dafd77b0
ms.sourcegitcommit: 2b4809e60974e72df9476ffd62706b1bfc8da4a7
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/04/2021
ms.locfileid: "5500944"
---
# <a name="shipping-information-setup"></a><span data-ttu-id="1ea33-103">Inställningar för leveransinformation</span><span class="sxs-lookup"><span data-stu-id="1ea33-103">Shipping information setup</span></span>

[!include [banner](../../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="1ea33-104">I det här avsnittet beskrivs hur du ställer in leveransinformation för modulen **hemtagningskostnad**.</span><span class="sxs-lookup"><span data-stu-id="1ea33-104">This topic describes how to set up shipping information for the **Landed cost** module.</span></span>

## <a name="description-of-goods"></a><a name="description-of-goods"></a><span data-ttu-id="1ea33-105">Beskrivning av varor</span><span class="sxs-lookup"><span data-stu-id="1ea33-105">Description of goods</span></span>

<span data-ttu-id="1ea33-106">Beskrivningar av varor gör det möjligt att identifiera en leveransbehållare eller ett folio för gods som finns i den.</span><span class="sxs-lookup"><span data-stu-id="1ea33-106">Descriptions of goods help identify a voyage, shipping container, or folio of goods, and the goods in it.</span></span> <span data-ttu-id="1ea33-107">Du kan välja en beskrivning av gods i leveransbehållarens rubrik eller i folio sidhuvud.</span><span class="sxs-lookup"><span data-stu-id="1ea33-107">You can select a description of goods on the shipping container header or the folio header.</span></span>

<span data-ttu-id="1ea33-108">Om du vill arbeta med beskrivningar av varor går du till **Hemtagningskostnad \> Inställning av leveransinformation \> Beskrivning av varor**.</span><span class="sxs-lookup"><span data-stu-id="1ea33-108">To work with descriptions of goods, go to **Landed cost \> Shipping information setup \> Description of goods**.</span></span> <span data-ttu-id="1ea33-109">Där kan du visa, öppna, skapa och ta bort poster för varubeskrivningar.</span><span class="sxs-lookup"><span data-stu-id="1ea33-109">There, you can view, open, create, and delete records for descriptions of goods.</span></span> <span data-ttu-id="1ea33-110">Följande register beskriver de fält som är tillgängliga för varje post.</span><span class="sxs-lookup"><span data-stu-id="1ea33-110">The following table describes the fields that are available for each record.</span></span>

| <span data-ttu-id="1ea33-111">Fält</span><span class="sxs-lookup"><span data-stu-id="1ea33-111">Field</span></span> | <span data-ttu-id="1ea33-112">beskrivning</span><span class="sxs-lookup"><span data-stu-id="1ea33-112">Description</span></span> |
|---|---|
| <span data-ttu-id="1ea33-113">Beskrivning av varor</span><span class="sxs-lookup"><span data-stu-id="1ea33-113">Description of goods</span></span> | <span data-ttu-id="1ea33-114">Ange ett unikt ID-namn/nummer för den typ av varor som kommer att använda den här beskrivningen.</span><span class="sxs-lookup"><span data-stu-id="1ea33-114">Enter a unique identification name/number for the type of goods that will use this description.</span></span> |
| <span data-ttu-id="1ea33-115">beskrivning</span><span class="sxs-lookup"><span data-stu-id="1ea33-115">Description</span></span> | <span data-ttu-id="1ea33-116">Ange en beskrivning av typen av varor i denna kategori.</span><span class="sxs-lookup"><span data-stu-id="1ea33-116">Enter a description of the type of goods in this category.</span></span> |

## <a name="vessels"></a><a name="vessels"></a><span data-ttu-id="1ea33-117">Fartyg</span><span class="sxs-lookup"><span data-stu-id="1ea33-117">Vessels</span></span>

<span data-ttu-id="1ea33-118">Ett fartyg är det unika namn som ett skepp eller fartyg som ett transportföretag eller en förmedling använder.</span><span class="sxs-lookup"><span data-stu-id="1ea33-118">A vessel is the unique name of a ship or vessel that a shipping company or agency uses.</span></span> <span data-ttu-id="1ea33-119">När du skapar en färd måste du alltid välja eller ange att du inte ska använda ett fartyg för den.</span><span class="sxs-lookup"><span data-stu-id="1ea33-119">When you create a voyage, you must always either select or enter a vessel for it.</span></span> <span data-ttu-id="1ea33-120">Om du ofta använder samma fartyg kan du göra det snabbare och enklare att skapa en ny färd genom att skapa en fartygspost och på så sätt göra det möjligt för användarna att välja ur en lista istället för att ange namnet eller numret manuellt varje gång.</span><span class="sxs-lookup"><span data-stu-id="1ea33-120">If you often use the same vessels, then you can make it faster and easier to create a new voyage by creating a vessel record for each of them, thereby allowing users to select the vessel from a list rather then enter the name or number manually each time.</span></span>

<span data-ttu-id="1ea33-121">Om du vill arbeta med fartyg, gå till **Hemtagningskostnad \> Inställning av leveransinformation \> Fartyg**.</span><span class="sxs-lookup"><span data-stu-id="1ea33-121">To work with vessels, go to **Landed cost \> Shipping information setup \> Vessels**.</span></span> <span data-ttu-id="1ea33-122">Där kan du visa, öppna, skapa och ta bort poster för fartyg.</span><span class="sxs-lookup"><span data-stu-id="1ea33-122">There, you can view, open, create, and delete records for vessels.</span></span> <span data-ttu-id="1ea33-123">Följande register beskriver de fält som är tillgängliga för varje post.</span><span class="sxs-lookup"><span data-stu-id="1ea33-123">The following table describes the fields that are available for each record.</span></span>

| <span data-ttu-id="1ea33-124">Fält</span><span class="sxs-lookup"><span data-stu-id="1ea33-124">Field</span></span> | <span data-ttu-id="1ea33-125">beskrivning</span><span class="sxs-lookup"><span data-stu-id="1ea33-125">Description</span></span> |
|---|---|
| <span data-ttu-id="1ea33-126">Fartyg</span><span class="sxs-lookup"><span data-stu-id="1ea33-126">Vessel</span></span> | <span data-ttu-id="1ea33-127">Ange ett unikt ID-namn/nummer för det skepp som ska användas vid transport av gods i en färd.</span><span class="sxs-lookup"><span data-stu-id="1ea33-127">Enter a unique identification name/number for the ship that will be used to transport goods on a voyage.</span></span> |
| <span data-ttu-id="1ea33-128">beskrivning</span><span class="sxs-lookup"><span data-stu-id="1ea33-128">Description</span></span> | <span data-ttu-id="1ea33-129">Ange en beskrivning av fartyget.</span><span class="sxs-lookup"><span data-stu-id="1ea33-129">Enter a description of the vessel.</span></span> <span data-ttu-id="1ea33-130">Vanligtvis identifierar denna beskrivning namnet på transportföretaget/agenten.</span><span class="sxs-lookup"><span data-stu-id="1ea33-130">Typically, this description identifies the name of the ship and the shipping company/agent.</span></span> |
| <span data-ttu-id="1ea33-131">Leveranssätt</span><span class="sxs-lookup"><span data-stu-id="1ea33-131">Mode of delivery</span></span> | <span data-ttu-id="1ea33-132">Välj det leveranssätt som fartyget använder (t.ex. _Flyg_, _Fartyg_ eller _Tåg_).</span><span class="sxs-lookup"><span data-stu-id="1ea33-132">Select the mode of delivery that the vessel uses (such as _Air_, _Ocean_, or _Train_).</span></span> |

## <a name="exporters"></a><span data-ttu-id="1ea33-133">Exportörer</span><span class="sxs-lookup"><span data-stu-id="1ea33-133">Exporters</span></span>

<span data-ttu-id="1ea33-134">Varje exportörpost identifierar en leverantör eller exportör som kan definieras som leverantör för en kund.</span><span class="sxs-lookup"><span data-stu-id="1ea33-134">Each exporter record identifies a vendor or exporter that can be defined as the vendor for a voyage.</span></span> <span data-ttu-id="1ea33-135">Exportören kan kopplas till en exportör och användas för rapportering.</span><span class="sxs-lookup"><span data-stu-id="1ea33-135">The exporter can be associated with a voyage and used for reporting.</span></span>

<span data-ttu-id="1ea33-136">Om du vill arbeta med exportörer, gå till **Hemtagningskostnad \> Inställning av leveransinformation \> exportörer**.</span><span class="sxs-lookup"><span data-stu-id="1ea33-136">To work with exporters, go to **Landed cost \> Shipping information setup \> Exporters**.</span></span> <span data-ttu-id="1ea33-137">Där kan du visa, öppna, skapa och ta bort poster för exportörer.</span><span class="sxs-lookup"><span data-stu-id="1ea33-137">There, you can view, open, create, and delete records for exporters.</span></span> <span data-ttu-id="1ea33-138">Följande register beskriver de fält som är tillgängliga för varje post.</span><span class="sxs-lookup"><span data-stu-id="1ea33-138">The following table describes the fields that are available for each record.</span></span>

| <span data-ttu-id="1ea33-139">Fält</span><span class="sxs-lookup"><span data-stu-id="1ea33-139">Field</span></span> | <span data-ttu-id="1ea33-140">beskrivning</span><span class="sxs-lookup"><span data-stu-id="1ea33-140">Description</span></span> |
|---|---|
| <span data-ttu-id="1ea33-141">Exportör</span><span class="sxs-lookup"><span data-stu-id="1ea33-141">Exporter</span></span> | <span data-ttu-id="1ea33-142">Ange ett unikt ID-namn/nummer för den exportör av varor som transporteras på en färd.</span><span class="sxs-lookup"><span data-stu-id="1ea33-142">Enter a unique identification name/number for the exporter of goods that are transported on a voyage.</span></span> |
| <span data-ttu-id="1ea33-143">beskrivning</span><span class="sxs-lookup"><span data-stu-id="1ea33-143">Description</span></span> | <span data-ttu-id="1ea33-144">Ange en beskrivning av exportören.</span><span class="sxs-lookup"><span data-stu-id="1ea33-144">Enter a description of the exporter.</span></span> <span data-ttu-id="1ea33-145">Vanligtvis identifierar denna beskrivning det fullständiga namnet på transportföretaget/agenten.</span><span class="sxs-lookup"><span data-stu-id="1ea33-145">Typically, this description identifies the full name of the shipping company/agent.</span></span> |

## <a name="commodity-codes"></a><span data-ttu-id="1ea33-146">Artikelkoder</span><span class="sxs-lookup"><span data-stu-id="1ea33-146">Commodity codes</span></span>

<span data-ttu-id="1ea33-147">Du använder artikelkoder som hjälp när du vill tullidentifiera och beräkna tullsatser för varor på en gång.</span><span class="sxs-lookup"><span data-stu-id="1ea33-147">You use commodity codes to help with customs identification and the calculation of duty rates for goods on a voyage.</span></span> <span data-ttu-id="1ea33-148">Du kan välja artikelkoder på sidan **Frisläppta produkter**.</span><span class="sxs-lookup"><span data-stu-id="1ea33-148">You can select commodity codes on the **Released products** page.</span></span>

<span data-ttu-id="1ea33-149">Om du vill arbeta med artikelkoder, gå till **Hemtagningskostnad \> Inställning av leveransinformation \> Artikelkoder**.</span><span class="sxs-lookup"><span data-stu-id="1ea33-149">To work with commodity codes, go to **Landed cost \> Shipping information setup \> Commodity codes**.</span></span> <span data-ttu-id="1ea33-150">Där kan du visa, öppna, skapa och ta bort poster för artikelkoder.</span><span class="sxs-lookup"><span data-stu-id="1ea33-150">There, you can view, open, create, and delete records for commodity codes.</span></span> <span data-ttu-id="1ea33-151">Följande register beskriver de fält som är tillgängliga för varje post.</span><span class="sxs-lookup"><span data-stu-id="1ea33-151">The following table describes the fields that are available for each record.</span></span>

| <span data-ttu-id="1ea33-152">Fält</span><span class="sxs-lookup"><span data-stu-id="1ea33-152">Field</span></span> | <span data-ttu-id="1ea33-153">beskrivning</span><span class="sxs-lookup"><span data-stu-id="1ea33-153">Description</span></span> |
|---|---|
| <span data-ttu-id="1ea33-154">Artikelkod</span><span class="sxs-lookup"><span data-stu-id="1ea33-154">Commodity code</span></span> | <span data-ttu-id="1ea33-155">Ange en unik kod för den här typen av vara.</span><span class="sxs-lookup"><span data-stu-id="1ea33-155">Enter a unique code for this type of commodity.</span></span> |
| <span data-ttu-id="1ea33-156">beskrivning</span><span class="sxs-lookup"><span data-stu-id="1ea33-156">Description</span></span> | <span data-ttu-id="1ea33-157">Ange en beskrivning av artikelkoder.</span><span class="sxs-lookup"><span data-stu-id="1ea33-157">Enter a description of the commodity type.</span></span> |

## <a name="customs-description"></a><span data-ttu-id="1ea33-158">Tullbeskrivning</span><span class="sxs-lookup"><span data-stu-id="1ea33-158">Customs description</span></span>

<span data-ttu-id="1ea33-159">Med hjälp av tullbeskrivningar kan varor identifieras för tulländamål.</span><span class="sxs-lookup"><span data-stu-id="1ea33-159">Customs descriptions help identify goods for customs purposes.</span></span> <span data-ttu-id="1ea33-160">Du kan välja en tullbeskrivning på sidan **Frisläppta produkter** eller på inköpsorderrader.</span><span class="sxs-lookup"><span data-stu-id="1ea33-160">You can select a customs description on the **Released products** page or on purchase order lines.</span></span>

<span data-ttu-id="1ea33-161">Om du vill arbeta med tullbeskrivningar av varor går du till **Hemtagningskostnad \> Inställning av leveransinformation \> Tullbeskrivning**.</span><span class="sxs-lookup"><span data-stu-id="1ea33-161">To work with customs descriptions, go to **Landed cost \> Shipping information setup \> Customs description**.</span></span> <span data-ttu-id="1ea33-162">Där kan du visa, öppna, skapa och ta bort poster för tullbeskrivningar.</span><span class="sxs-lookup"><span data-stu-id="1ea33-162">There, you can view, open, create, and delete records for custom descriptions.</span></span> <span data-ttu-id="1ea33-163">Följande register beskriver de fält som är tillgängliga för varje post.</span><span class="sxs-lookup"><span data-stu-id="1ea33-163">The following table describes the fields that are available for each record.</span></span>

| <span data-ttu-id="1ea33-164">Fält</span><span class="sxs-lookup"><span data-stu-id="1ea33-164">Field</span></span> | <span data-ttu-id="1ea33-165">beskrivning</span><span class="sxs-lookup"><span data-stu-id="1ea33-165">Description</span></span> |
|---|---|
| <span data-ttu-id="1ea33-166">Tullbeskrivning</span><span class="sxs-lookup"><span data-stu-id="1ea33-166">Customs description</span></span> | <span data-ttu-id="1ea33-167">Ange en unik kod för den här typen av tullklassificering.</span><span class="sxs-lookup"><span data-stu-id="1ea33-167">Enter a unique code for this type of customs classification.</span></span> <span data-ttu-id="1ea33-168">Ofta blir den här koden den officiella beskrivningen som ges av en tullmyndighet för beskrivningen av och det kvalitativa värdet av varorna.</span><span class="sxs-lookup"><span data-stu-id="1ea33-168">Often, this code will be the official description that is provided by a customs authority for the description and qualitative value of the goods.</span></span> |
| <span data-ttu-id="1ea33-169">beskrivning</span><span class="sxs-lookup"><span data-stu-id="1ea33-169">Description</span></span> | <span data-ttu-id="1ea33-170">Ange en beskrivning av tullklassificeringen.</span><span class="sxs-lookup"><span data-stu-id="1ea33-170">Enter a description of the customs classification.</span></span> |
