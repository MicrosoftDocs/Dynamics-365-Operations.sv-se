---
title: Skapa en strukturlista för en dimensionsbaserad produktmall
description: För den här proceduren bör du ha slutfört de tidigare 4 guiderna i denna sekvens av åtta inspelningar.
author: ShylaThompson
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductMaintainWorkspace, EcoResProductOpenCasesFormPart, EcoResProductDetailsExtended, BOMConsistOf, BOMTable, InventItemIdLookupSimple, HcmWorkerLookUp
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 13053dd87242963586678b46c64493feb3383c4c
ms.sourcegitcommit: fa99a36c3d30d0c0577fd3f63ed6bf2f71599e40
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/20/2021
ms.locfileid: "5920715"
---
# <a name="create-a-bill-of-materials-for-a-dimension-based-product-master"></a><span data-ttu-id="c80f1-103">Skapa en strukturlista för en dimensionsbaserad produktmall</span><span class="sxs-lookup"><span data-stu-id="c80f1-103">Create a bill of materials for a dimension-based product master</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="c80f1-104">För den här proceduren bör du ha slutfört de tidigare 4 guiderna i denna sekvens av åtta inspelningar.</span><span class="sxs-lookup"><span data-stu-id="c80f1-104">For this procedure you should have completed the previous 4 guides in this sequence of eight recordings.</span></span> <span data-ttu-id="c80f1-105">De första 4 inspelningarna anger de data som krävs för att slutföra den här proceduren.</span><span class="sxs-lookup"><span data-stu-id="c80f1-105">The first 4 recordings set up data that is required to complete this procedure.</span></span> <span data-ttu-id="c80f1-106">Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF.</span><span class="sxs-lookup"><span data-stu-id="c80f1-106">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="c80f1-107">Denna uppgift utförs vanligtvis av produktdesignern.</span><span class="sxs-lookup"><span data-stu-id="c80f1-107">This task is typically handled by the product designer.</span></span>

## <a name="select-the-product"></a><span data-ttu-id="c80f1-108">Välj produkten</span><span class="sxs-lookup"><span data-stu-id="c80f1-108">Select the product</span></span>

1. <span data-ttu-id="c80f1-109">Gå till **Produktinformationshantering \> Produkter \> Frisläppta produkter**.</span><span class="sxs-lookup"><span data-stu-id="c80f1-109">Go to **Product information management \> Products \> Released products**.</span></span>
1. <span data-ttu-id="c80f1-110">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="c80f1-110">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="c80f1-111">Hitta den frisläppta produktmallen med dimensionsbaserad konfigurationsteknologi som du skapade i den första uppgiftsguiden i denna sekvens.</span><span class="sxs-lookup"><span data-stu-id="c80f1-111">Find the released product master with dimension-based configuration technology that you created in the first task guide in this sequence.</span></span>  
1. <span data-ttu-id="c80f1-112">Klicka på **Tekniker** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="c80f1-112">On the Action Pane, select **Engineer**.</span></span>
1. <span data-ttu-id="c80f1-113">Välj **Strukturlisteversioner**.</span><span class="sxs-lookup"><span data-stu-id="c80f1-113">Select **BOM versions**.</span></span>

## <a name="create-new-bom-and-bom-version"></a><span data-ttu-id="c80f1-114">Skapa en ny strukturlista och strukturlisteversion</span><span class="sxs-lookup"><span data-stu-id="c80f1-114">Create new BOM and BOM version</span></span>

1. <span data-ttu-id="c80f1-115">Välj **Ny**.</span><span class="sxs-lookup"><span data-stu-id="c80f1-115">Select **New**.</span></span>
1. <span data-ttu-id="c80f1-116">Välj **Strukturlista och strukturlisteversion**.</span><span class="sxs-lookup"><span data-stu-id="c80f1-116">Select **BOM and BOM version**.</span></span>
1. <span data-ttu-id="c80f1-117">Skriv ett värde i fältet **Namn**.</span><span class="sxs-lookup"><span data-stu-id="c80f1-117">In the **Name** field, type a value.</span></span>
    * <span data-ttu-id="c80f1-118">Ange en site</span><span class="sxs-lookup"><span data-stu-id="c80f1-118">Setting a site</span></span>  
    * <span data-ttu-id="c80f1-119">I den här proceduren anger vi inte en specifik site för strukturlistan.</span><span class="sxs-lookup"><span data-stu-id="c80f1-119">In this procedure we don't set a specific site for the BOM.</span></span>  
1. <span data-ttu-id="c80f1-120">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="c80f1-120">Select **OK**.</span></span>
1. <span data-ttu-id="c80f1-121">Välj **Ny**.</span><span class="sxs-lookup"><span data-stu-id="c80f1-121">Select **New**.</span></span>
    * <span data-ttu-id="c80f1-122">I den här proceduren kommer vi att lägga till fyra rader i strukturlistan.</span><span class="sxs-lookup"><span data-stu-id="c80f1-122">In this procedure we will add four lines to the BOM.</span></span> <span data-ttu-id="c80f1-123">Två rader representerar kabelalternativ, och två rader representerar skåpalternativ.</span><span class="sxs-lookup"><span data-stu-id="c80f1-123">Two lines represent cable options and two lines represent cabinet options.</span></span>  
1. <span data-ttu-id="c80f1-124">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="c80f1-124">In the list, mark the selected row.</span></span>
1. <span data-ttu-id="c80f1-125">I fältet **artikelnummer** anger du eller väljer ett värde.</span><span class="sxs-lookup"><span data-stu-id="c80f1-125">In the **Item number** field, enter or select a value.</span></span>
    * <span data-ttu-id="c80f1-126">Välj artikelnummer A0001, HDMI 6 tums kablar.</span><span class="sxs-lookup"><span data-stu-id="c80f1-126">Select item number A0001, HDMI 6' Cables.</span></span>  
1. <span data-ttu-id="c80f1-127">I fältet **Konfigurationsgrupp** anger eller väljer du ett värde.</span><span class="sxs-lookup"><span data-stu-id="c80f1-127">In the **Configuration group** field, enter or select a value.</span></span>
    * <span data-ttu-id="c80f1-128">Välj kabelkonfigurationsgruppen som skapas i guide 4 i denna sekvens.</span><span class="sxs-lookup"><span data-stu-id="c80f1-128">Select the cable configuration group created in guide 4 in this sequence.</span></span>  
1. <span data-ttu-id="c80f1-129">Välj **Ny**.</span><span class="sxs-lookup"><span data-stu-id="c80f1-129">Select **New**.</span></span>
    * <span data-ttu-id="c80f1-130">Välj artikelnummer A0002, HDMI 12 tums kablar.</span><span class="sxs-lookup"><span data-stu-id="c80f1-130">Select item number A0002, HDMI 12' Cables.</span></span>  
1. <span data-ttu-id="c80f1-131">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="c80f1-131">In the list, mark the selected row.</span></span>
1. <span data-ttu-id="c80f1-132">I fältet **artikelnummer** anger du eller väljer ett värde.</span><span class="sxs-lookup"><span data-stu-id="c80f1-132">In the **Item number** field, enter or select a value.</span></span>
1. <span data-ttu-id="c80f1-133">I fältet **Konfigurationsgrupp** anger eller väljer du ett värde.</span><span class="sxs-lookup"><span data-stu-id="c80f1-133">In the **Configuration group** field, enter or select a value.</span></span>
    * <span data-ttu-id="c80f1-134">Markera kabelkonfigurationsgruppen igen.</span><span class="sxs-lookup"><span data-stu-id="c80f1-134">Select the cable configuration group again.</span></span>  
1. <span data-ttu-id="c80f1-135">Välj **Ny**.</span><span class="sxs-lookup"><span data-stu-id="c80f1-135">Select **New**.</span></span>
1. <span data-ttu-id="c80f1-136">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="c80f1-136">In the list, mark the selected row.</span></span>
1. <span data-ttu-id="c80f1-137">I fältet **artikelnummer** anger du eller väljer ett värde.</span><span class="sxs-lookup"><span data-stu-id="c80f1-137">In the **Item number** field, enter or select a value.</span></span>
    * <span data-ttu-id="c80f1-138">Välj artikelnummer D0002 Skåp.</span><span class="sxs-lookup"><span data-stu-id="c80f1-138">Select item number D0002 Cabinet.</span></span>  
1. <span data-ttu-id="c80f1-139">I fältet **Konfigurationsgrupp** anger eller väljer du ett värde.</span><span class="sxs-lookup"><span data-stu-id="c80f1-139">In the **Configuration group** field, enter or select a value.</span></span>
    * <span data-ttu-id="c80f1-140">Välj skåpkonfigurationsgruppen för denna strukturlisterad.</span><span class="sxs-lookup"><span data-stu-id="c80f1-140">Select the cabinet configuration group for this BOM line.</span></span>  
1. <span data-ttu-id="c80f1-141">Välj **Ny**.</span><span class="sxs-lookup"><span data-stu-id="c80f1-141">Select **New**.</span></span>
1. <span data-ttu-id="c80f1-142">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="c80f1-142">In the list, mark the selected row.</span></span>
1. <span data-ttu-id="c80f1-143">I fältet **artikelnummer** anger du eller väljer ett värde.</span><span class="sxs-lookup"><span data-stu-id="c80f1-143">In the **Item number** field, enter or select a value.</span></span>
    * <span data-ttu-id="c80f1-144">Välj artikelnummer M0007 Standardskåp som sista strukturlisteraden.</span><span class="sxs-lookup"><span data-stu-id="c80f1-144">Select Item number M0007 StandardCabinet as the last BOM line.</span></span>  
1. <span data-ttu-id="c80f1-145">I fältet **Konfigurationsgrupp** anger eller väljer du ett värde.</span><span class="sxs-lookup"><span data-stu-id="c80f1-145">In the **Configuration group** field, enter or select a value.</span></span>
    * <span data-ttu-id="c80f1-146">Välj skåpkonfigurationsgruppen för den sista strukturlisteraden.</span><span class="sxs-lookup"><span data-stu-id="c80f1-146">Select the Cabinet configuration group for the last BOM line.</span></span>  

## <a name="approve-and-activate"></a><span data-ttu-id="c80f1-147">Godkänn och aktivera</span><span class="sxs-lookup"><span data-stu-id="c80f1-147">Approve and activate</span></span>

1. <span data-ttu-id="c80f1-148">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="c80f1-148">Close the page.</span></span>
1. <span data-ttu-id="c80f1-149">Välj **Godkänn**.</span><span class="sxs-lookup"><span data-stu-id="c80f1-149">Select **Approve**.</span></span>
1. <span data-ttu-id="c80f1-150">I fältet **Godkändes av** anger eller väljer du ett värde.</span><span class="sxs-lookup"><span data-stu-id="c80f1-150">In the **Approved by** field, enter or select a value.</span></span>
1. <span data-ttu-id="c80f1-151">Välj *Ja* i fältet **Vill du även godkänna strukturlistan?**.</span><span class="sxs-lookup"><span data-stu-id="c80f1-151">Select *Yes* in the **Do you also want to approve the bill of materials?** field.</span></span>
1. <span data-ttu-id="c80f1-152">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="c80f1-152">Select **OK**.</span></span>
1. <span data-ttu-id="c80f1-153">Välj **aktivera**.</span><span class="sxs-lookup"><span data-stu-id="c80f1-153">Select **Activate**.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]