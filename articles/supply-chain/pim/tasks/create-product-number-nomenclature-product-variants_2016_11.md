---
title: Skapa en produktnummernomenklatur för konfigurerade produktvarianter
description: I den här proceduren visas hur du ställer in en produktnummernomenklatur för konfigurerade produktvarianter, och hur denna kan kopplas till en konfigurerbar produktmall.
author: ShylaThompson
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, EcoResNomenclature, EcoResProductListPage, EcoResProductDetails, PCProductConfigurationModelListPage, PCProductConfigurationModelDetails
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7ea30dc107213b1a2c6b2a109188066a6ea82159
ms.sourcegitcommit: fa99a36c3d30d0c0577fd3f63ed6bf2f71599e40
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/20/2021
ms.locfileid: "5921021"
---
# <a name="create-a-product-number-nomenclature-for-configured-product-variants"></a><span data-ttu-id="e9b79-103">Skapa en produktnummernomenklatur för konfigurerade produktvarianter</span><span class="sxs-lookup"><span data-stu-id="e9b79-103">Create a product number nomenclature for configured product variants</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="e9b79-104">I den här proceduren visas hur du ställer in en produktnummernomenklatur för konfigurerade produktvarianter, och hur denna kan kopplas till en konfigurerbar produktmall.</span><span class="sxs-lookup"><span data-stu-id="e9b79-104">This procedure shows you how to set up a product number nomenclature for configured product variants, and how it can be attached to a configurable product master.</span></span> <span data-ttu-id="e9b79-105">I den här proceduren visas även hur du kan skapa en konfigurationsnomenklatur för en modellkomponent för en produktkonfiguration.</span><span class="sxs-lookup"><span data-stu-id="e9b79-105">This procedure also demonstrates how you can build a configuration nomenclature for a product configuration model component.</span></span> <span data-ttu-id="e9b79-106">Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF.</span><span class="sxs-lookup"><span data-stu-id="e9b79-106">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="e9b79-107">Den nya produktnummernomenklaturen tilldelas produktmallen D0004.</span><span class="sxs-lookup"><span data-stu-id="e9b79-107">The new product number nomenclature is assigned to the D0004 product master.</span></span> <span data-ttu-id="e9b79-108">Den här uppgiften utförs vanligtvis av en produktdesigner.</span><span class="sxs-lookup"><span data-stu-id="e9b79-108">This task would typically be done by a product designer.</span></span>

## <a name="create-a-product-number-nomenclature"></a><span data-ttu-id="e9b79-109">Skapa en nomenklatur för produktnummer</span><span class="sxs-lookup"><span data-stu-id="e9b79-109">Create a product number nomenclature</span></span>

1. <span data-ttu-id="e9b79-110">Gå till **Hantering av produktinformation \> Inställningar \> Produktnomenklatur**.</span><span class="sxs-lookup"><span data-stu-id="e9b79-110">Go to **Product information management \> Setup \> Product nomenclature**.</span></span>
1. <span data-ttu-id="e9b79-111">Välj **Ny**.</span><span class="sxs-lookup"><span data-stu-id="e9b79-111">Select **New**.</span></span>
1. <span data-ttu-id="e9b79-112">Skriv ett värde i fältet **Namn**.</span><span class="sxs-lookup"><span data-stu-id="e9b79-112">In the **Name** field, type a value.</span></span>
1. <span data-ttu-id="e9b79-113">I fältet **Beskrivning** anger du ett värde.</span><span class="sxs-lookup"><span data-stu-id="e9b79-113">In the **Description** field, type a value.</span></span>
1. <span data-ttu-id="e9b79-114">Markera **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="e9b79-114">Select **Add**.</span></span>
1. <span data-ttu-id="e9b79-115">Välj **Produktmallsnummer**.</span><span class="sxs-lookup"><span data-stu-id="e9b79-115">Select **Product master number**.</span></span>
1. <span data-ttu-id="e9b79-116">Markera **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="e9b79-116">Select **Add**.</span></span>
1. <span data-ttu-id="e9b79-117">Välj **Textkonstant**.</span><span class="sxs-lookup"><span data-stu-id="e9b79-117">Select **Text constant**.</span></span>
1. <span data-ttu-id="e9b79-118">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="e9b79-118">In the list, mark the selected row.</span></span>
1. <span data-ttu-id="e9b79-119">Skriv ett värde i fältet **Text**.</span><span class="sxs-lookup"><span data-stu-id="e9b79-119">In the **Text** field, type a value.</span></span>
1. <span data-ttu-id="e9b79-120">Markera **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="e9b79-120">Select **Add**.</span></span>
1. <span data-ttu-id="e9b79-121">Välj **Konfiguration**.</span><span class="sxs-lookup"><span data-stu-id="e9b79-121">Select **Configuration**.</span></span>
1. <span data-ttu-id="e9b79-122">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="e9b79-122">Close the page.</span></span>

## <a name="assign-the-product-number-nomenclature-to-a-product-master"></a><span data-ttu-id="e9b79-123">Tilldela produktnummernomenklaturen till en produktmall</span><span class="sxs-lookup"><span data-stu-id="e9b79-123">Assign the product number nomenclature to a product master</span></span>

1. <span data-ttu-id="e9b79-124">Gå till **Hantering av produktinformation \> Produkter \> Produktmallar**.</span><span class="sxs-lookup"><span data-stu-id="e9b79-124">Go to **Product information management \> Products \> Product masters**.</span></span>
1. <span data-ttu-id="e9b79-125">Använd snabbfiltret för att söka efter poster.</span><span class="sxs-lookup"><span data-stu-id="e9b79-125">Use the Quick Filter to find records.</span></span> <span data-ttu-id="e9b79-126">Filtrera till exempel på fältet **Produktnummer** med värdet "D".</span><span class="sxs-lookup"><span data-stu-id="e9b79-126">For example, filter on the **Product number** field with a value of 'D'.</span></span>
1. <span data-ttu-id="e9b79-127">Klicka på länken på önskad rad i valda listan.</span><span class="sxs-lookup"><span data-stu-id="e9b79-127">In the list, select the link in the selected row.</span></span>
1. <span data-ttu-id="e9b79-128">Välj **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="e9b79-128">Select **Edit**.</span></span>
1. <span data-ttu-id="e9b79-129">Välj *Ja* i fältet **Använd nomenklatur**.</span><span class="sxs-lookup"><span data-stu-id="e9b79-129">Select *Yes* in the **Use nomenclature** field.</span></span>
1. <span data-ttu-id="e9b79-130">I fältet **Nomenklatur för produktvariantnummer**, ange eller välj ett värde.</span><span class="sxs-lookup"><span data-stu-id="e9b79-130">In the **Product variant number nomenclature** field, enter or select a value.</span></span>
1. <span data-ttu-id="e9b79-131">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="e9b79-131">Close the page.</span></span>
1. <span data-ttu-id="e9b79-132">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="e9b79-132">Close the page.</span></span>

## <a name="create-nomenclature-for-a-product-configuration-model-component"></a><span data-ttu-id="e9b79-133">Skapa en nomenklatur för en komponent i en produktkonfigurationsmodell</span><span class="sxs-lookup"><span data-stu-id="e9b79-133">Create nomenclature for a product configuration model component</span></span>

1. <span data-ttu-id="e9b79-134">Gå till **Produktinformationshantering \> Produkter \> Produktkonfigurationsmodeller**.</span><span class="sxs-lookup"><span data-stu-id="e9b79-134">Go to **Product information management \> Products \> Product configuration models**.</span></span>
1. <span data-ttu-id="e9b79-135">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="e9b79-135">In the list, find and select the desired record.</span></span>
1. <span data-ttu-id="e9b79-136">Klicka på länken på önskad rad i valda listan.</span><span class="sxs-lookup"><span data-stu-id="e9b79-136">In the list, select the link in the selected row.</span></span>
1. <span data-ttu-id="e9b79-137">Välj **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="e9b79-137">Select **Edit**.</span></span>
1. <span data-ttu-id="e9b79-138">Välj *Ja* i fältet **Använd konfigurationsnomenklatur**.</span><span class="sxs-lookup"><span data-stu-id="e9b79-138">Select *Yes* in the **Use configuration nomenclature** field.</span></span>
1. <span data-ttu-id="e9b79-139">Markera **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="e9b79-139">Select **Add**.</span></span>
1. <span data-ttu-id="e9b79-140">Välj **Attributvärde**.</span><span class="sxs-lookup"><span data-stu-id="e9b79-140">Select **Attribute value**.</span></span>
1. <span data-ttu-id="e9b79-141">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="e9b79-141">In the list, mark the selected row.</span></span>
1. <span data-ttu-id="e9b79-142">I fältet **Attribut** anger eller väljer du ett värde.</span><span class="sxs-lookup"><span data-stu-id="e9b79-142">In the **Attribute** field, enter or select a value.</span></span>
1. <span data-ttu-id="e9b79-143">Markera **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="e9b79-143">Select **Add**.</span></span>
1. <span data-ttu-id="e9b79-144">Välj **Textkonstant**.</span><span class="sxs-lookup"><span data-stu-id="e9b79-144">Select **Text constant**.</span></span>
1. <span data-ttu-id="e9b79-145">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="e9b79-145">In the list, mark the selected row.</span></span>
1. <span data-ttu-id="e9b79-146">Skriv ett värde i fältet **Text**.</span><span class="sxs-lookup"><span data-stu-id="e9b79-146">In the **Text** field, type a value.</span></span>
1. <span data-ttu-id="e9b79-147">Markera **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="e9b79-147">Select **Add**.</span></span>
1. <span data-ttu-id="e9b79-148">Välj **Attributvärde**.</span><span class="sxs-lookup"><span data-stu-id="e9b79-148">Select **Attribute value**.</span></span>
1. <span data-ttu-id="e9b79-149">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="e9b79-149">In the list, mark the selected row.</span></span>
1. <span data-ttu-id="e9b79-150">I fältet **Attribut** anger eller väljer du ett värde.</span><span class="sxs-lookup"><span data-stu-id="e9b79-150">In the **Attribute** field, enter or select a value.</span></span>
1. <span data-ttu-id="e9b79-151">Markera **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="e9b79-151">Select **Add**.</span></span>
1. <span data-ttu-id="e9b79-152">Välj **Textkonstant**.</span><span class="sxs-lookup"><span data-stu-id="e9b79-152">Select **Text constant**.</span></span>
1. <span data-ttu-id="e9b79-153">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="e9b79-153">In the list, mark the selected row.</span></span>
1. <span data-ttu-id="e9b79-154">Skriv ett värde i fältet **Text**.</span><span class="sxs-lookup"><span data-stu-id="e9b79-154">In the **Text** field, type a value.</span></span>
1. <span data-ttu-id="e9b79-155">Markera **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="e9b79-155">Select **Add**.</span></span>
1. <span data-ttu-id="e9b79-156">Välj **Attributvärde**.</span><span class="sxs-lookup"><span data-stu-id="e9b79-156">Select **Attribute value**.</span></span>
1. <span data-ttu-id="e9b79-157">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="e9b79-157">In the list, mark the selected row.</span></span>
1. <span data-ttu-id="e9b79-158">I fältet **Attribut** anger eller väljer du ett värde.</span><span class="sxs-lookup"><span data-stu-id="e9b79-158">In the **Attribute** field, enter or select a value.</span></span>
1. <span data-ttu-id="e9b79-159">Markera **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="e9b79-159">Select **Add**.</span></span>
1. <span data-ttu-id="e9b79-160">Välj **Textkonstant**.</span><span class="sxs-lookup"><span data-stu-id="e9b79-160">Select **Text constant**.</span></span>
1. <span data-ttu-id="e9b79-161">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="e9b79-161">In the list, mark the selected row.</span></span>
1. <span data-ttu-id="e9b79-162">Skriv ett värde i fältet **Text**.</span><span class="sxs-lookup"><span data-stu-id="e9b79-162">In the **Text** field, type a value.</span></span>
1. <span data-ttu-id="e9b79-163">Markera **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="e9b79-163">Select **Add**.</span></span>
1. <span data-ttu-id="e9b79-164">Välj **Attributvärde**.</span><span class="sxs-lookup"><span data-stu-id="e9b79-164">Select **Attribute value**.</span></span>
1. <span data-ttu-id="e9b79-165">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="e9b79-165">In the list, mark the selected row.</span></span>
1. <span data-ttu-id="e9b79-166">I fältet **Attribut** anger eller väljer du ett värde.</span><span class="sxs-lookup"><span data-stu-id="e9b79-166">In the **Attribute** field, enter or select a value.</span></span>
1. <span data-ttu-id="e9b79-167">Markera **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="e9b79-167">Select **Add**.</span></span>
1. <span data-ttu-id="e9b79-168">Välj **Textkonstant**.</span><span class="sxs-lookup"><span data-stu-id="e9b79-168">Select **Text constant**.</span></span>
1. <span data-ttu-id="e9b79-169">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="e9b79-169">In the list, mark the selected row.</span></span>
1. <span data-ttu-id="e9b79-170">Skriv ett värde i fältet **Text**.</span><span class="sxs-lookup"><span data-stu-id="e9b79-170">In the **Text** field, type a value.</span></span>
1. <span data-ttu-id="e9b79-171">Markera **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="e9b79-171">Select **Add**.</span></span>
1. <span data-ttu-id="e9b79-172">Välj **Nummerserievärde**.</span><span class="sxs-lookup"><span data-stu-id="e9b79-172">Select **Number sequence value**.</span></span>
1. <span data-ttu-id="e9b79-173">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="e9b79-173">In the list, mark the selected row.</span></span>
1. <span data-ttu-id="e9b79-174">I fältet **Nummerserie** anger eller väljer du ett värde.</span><span class="sxs-lookup"><span data-stu-id="e9b79-174">In the **Number sequence** field, enter or select a value.</span></span>
1. <span data-ttu-id="e9b79-175">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="e9b79-175">Close the page.</span></span>
1. <span data-ttu-id="e9b79-176">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="e9b79-176">Close the page.</span></span>
1. <span data-ttu-id="e9b79-177">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="e9b79-177">Close the page.</span></span>

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]