---
title: Felsöka distributionslagerkonfiguration
description: I det här avsnittet beskrivs hur du åtgärdar vanliga problem som kan uppstå när du konfigurerar i Microsoft Dynamics 365 Supply Chain Management.
author: perlynne
manager: tfehr
ms.date: 10/19/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-10-19
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 09b5770190fea9591f422b61ce6deedb2b9fa790
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "4994013"
---
# <a name="troubleshoot-warehouse-configuration"></a><span data-ttu-id="92561-103">Felsöka distributionslagerkonfiguration</span><span class="sxs-lookup"><span data-stu-id="92561-103">Troubleshoot warehouse configuration</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="92561-104">I det här avsnittet beskrivs hur du åtgärdar vanliga problem som kan uppstå när du konfigurerar i Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="92561-104">This topic describes how to fix common issues that you might encounter while you configure Microsoft Dynamics 365 Supply Chain Management.</span></span>

## <a name="i-receive-the-following-error-message-the-license-plate-or-location-is-not-valid"></a><span data-ttu-id="92561-105">Jag får följande felmeddelande: "ID-nummer eller platsen är inte giltig."</span><span class="sxs-lookup"><span data-stu-id="92561-105">I receive the following error message: "The license plate or location is not valid."</span></span>

### <a name="issue-description"></a><span data-ttu-id="92561-106">Problembeskrivning</span><span class="sxs-lookup"><span data-stu-id="92561-106">Issue description</span></span>

<span data-ttu-id="92561-107">Det här felmeddelandet visas när du skannar ett ID-nummer eller en plats.</span><span class="sxs-lookup"><span data-stu-id="92561-107">You receive this error message when you scan a license plate ID or location.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="92561-108">Problemlösning</span><span class="sxs-lookup"><span data-stu-id="92561-108">Issue resolution</span></span>

<span data-ttu-id="92561-109">Se till att licensens ID-nummer inte har reserverats av något annat.</span><span class="sxs-lookup"><span data-stu-id="92561-109">Make sure that the license plate ID isn't reserved by something else.</span></span> <span data-ttu-id="92561-110">Det här problemet uppstår när värdet som en användare skannade i lagerstället var både en giltig plats och ett giltigt licensens ID-nummer.</span><span class="sxs-lookup"><span data-stu-id="92561-110">This issue used to occur when the value that a user scanned in the warehouse app was both a valid location and a valid license plate ID.</span></span> <span data-ttu-id="92561-111">Det här problemet löstes emellertid i versionen 10.0.11.</span><span class="sxs-lookup"><span data-stu-id="92561-111">However, this issue was resolved in version 10.0.11.</span></span>

## <a name="i-receive-the-following-error-message-license-plate-must-be-specified-for-this-location"></a><span data-ttu-id="92561-112">Jag får följande felmeddelande: "ID-nummer måste anges för denna för denna plats".</span><span class="sxs-lookup"><span data-stu-id="92561-112">I receive the following error message: "License plate must be specified for this location."</span></span>

### <a name="issue-description"></a><span data-ttu-id="92561-113">Problembeskrivning</span><span class="sxs-lookup"><span data-stu-id="92561-113">Issue description</span></span>

<span data-ttu-id="92561-114">Det här felmeddelandet visas om du skapar en överföringsorder med hjälp av ett lager ställe som har aktiverats ATS för WMS (avancerad lagerstyrning) och du sedan försöker bekräfta leveransen när arbetet har slutförts.</span><span class="sxs-lookup"><span data-stu-id="92561-114">You receive this error message if you create a transfer order by using a warehouse that is enabled for advanced warehouse management (WMS), and then, after the work is completed, you try to confirm the shipment.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="92561-115">Problemlösning</span><span class="sxs-lookup"><span data-stu-id="92561-115">Issue resolution</span></span>

<span data-ttu-id="92561-116">Fältet **Standardinleveransplats** är tomt för transit lager av "från"-lagerstället.</span><span class="sxs-lookup"><span data-stu-id="92561-116">The **Default receipt location** field is blank for a transit warehouse of the "from" warehouse.</span></span> <span data-ttu-id="92561-117">Du åtgärdar det här problemet genom att ange en standard inleveransplats i transitlagret.</span><span class="sxs-lookup"><span data-stu-id="92561-117">To fix this issue, specify a default receipt location in the transit warehouse.</span></span> <span data-ttu-id="92561-118">Kontrollera att den här platsen styrs av ett ID-nummer.</span><span class="sxs-lookup"><span data-stu-id="92561-118">Make sure that this location is license plate–controlled.</span></span>

## <a name="i-receive-the-following-error-message-you-cant-create-a-work-template-line-for-inventory-status-change-because-the-work-type-is-not-valid-select-a-different-work-type"></a><span data-ttu-id="92561-119">Följande felmeddelande visas: "du kan inte skapa en rad för lagerstatusändring eftersom arbetstypen är ogiltig.</span><span class="sxs-lookup"><span data-stu-id="92561-119">I receive the following error message: "You can't create a work template line for Inventory status change because the work type is not valid.</span></span> <span data-ttu-id="92561-120">Välj en annan arbetstyp".</span><span class="sxs-lookup"><span data-stu-id="92561-120">Select a different work type."</span></span>

### <a name="issue-description"></a><span data-ttu-id="92561-121">Problembeskrivning</span><span class="sxs-lookup"><span data-stu-id="92561-121">Issue description</span></span>

<span data-ttu-id="92561-122">Om det är en arbetsgrupp kan du inte markera *lagerstatusändring* i kolumnen **arbetstyp** i avsnittet **information om arbetsmallen**.</span><span class="sxs-lookup"><span data-stu-id="92561-122">For a work template, you can't select *Inventory status change* in the **Work type** column of the **Work template details** section.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="92561-123">Problemlösning</span><span class="sxs-lookup"><span data-stu-id="92561-123">Issue resolution</span></span>

<span data-ttu-id="92561-124">Detta beteende är av design.</span><span class="sxs-lookup"><span data-stu-id="92561-124">This behavior is by design.</span></span> <span data-ttu-id="92561-125">Arbetstypen *Ändring av lagerstatus* används endast av systemprocesser.</span><span class="sxs-lookup"><span data-stu-id="92561-125">The *Inventory status change* work type is used only by system processes.</span></span> <span data-ttu-id="92561-126">Det kan inte konfigureras.</span><span class="sxs-lookup"><span data-stu-id="92561-126">It can't be configured.</span></span> <span data-ttu-id="92561-127">Eftersom listan med arbetstyper är fast som en uppräkning kan inte de extra posterna filtreras från den nedrullningsbara menyn **Arbetstyp**.</span><span class="sxs-lookup"><span data-stu-id="92561-127">Because the list of work types is fixed as an enumeration, the extra entries can't be filtered out of the **Work type** drop-down menu.</span></span>

## <a name="i-receive-the-following-error-message-the-quantity-is-not-valid-for-unit-1"></a><span data-ttu-id="92561-128">Jag får följande felmeddelande: "Kvantiteten gäller inte för enhet 1 %".</span><span class="sxs-lookup"><span data-stu-id="92561-128">I receive the following error message: "The Quantity is not valid for unit 1%."</span></span>

### <a name="issue-description"></a><span data-ttu-id="92561-129">Problembeskrivning</span><span class="sxs-lookup"><span data-stu-id="92561-129">Issue description</span></span>

<span data-ttu-id="92561-130">Kvantiteten är inte giltig för *ea* enheten när det finns ett plockningsarbete med flera ID-nummer på en plats.</span><span class="sxs-lookup"><span data-stu-id="92561-130">The quantity isn't valid for the *ea* unit when there is picking work that has multiple license plates in one location.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="92561-131">Problemlösning</span><span class="sxs-lookup"><span data-stu-id="92561-131">Issue resolution</span></span>

<span data-ttu-id="92561-132">Kontrollera att fälten **enhetsseriegrupp-ID** och **enhetskonvertering** på den frisläppta produkten eller produktvarianten är korrekt inställda.</span><span class="sxs-lookup"><span data-stu-id="92561-132">Verify that the **Unit sequence group ID** and **Unit conversions** fields on the released product or product variant are set correctly.</span></span>

<span data-ttu-id="92561-133">Observera att felmeddelandet har förbättrats i version 10.0.15 (se [KB 4581627](https://fix.lcs.dynamics.com/Issue/Details/?bugId=486531)).</span><span class="sxs-lookup"><span data-stu-id="92561-133">Note that the error message has been improved in version 10.0.15 (see [KB 4581627](https://fix.lcs.dynamics.com/Issue/Details/?bugId=486531)).</span></span> <span data-ttu-id="92561-134">Det nya felmeddelandet är, "kvantiteten är ogiltig.</span><span class="sxs-lookup"><span data-stu-id="92561-134">The new error message is, "The quantity is not valid.</span></span> <span data-ttu-id="92561-135">Förväntat %1 %2."</span><span class="sxs-lookup"><span data-stu-id="92561-135">Expected %1 %2."</span></span>

## <a name="in-location-directives-for-sales-order-put-work-the-multiple-sku-option-doesnt-evaluate-multiple-location-directive-actions"></a><span data-ttu-id="92561-136">I platsdirektiv för placeringsarbete för försäljningsorder utvärderas inte flera platsdirektivåtgärder med alternativet flera SKU:er.</span><span class="sxs-lookup"><span data-stu-id="92561-136">In location directives for sales order put work, the multiple SKU option doesn't evaluate multiple location directive actions.</span></span>

### <a name="issue-description"></a><span data-ttu-id="92561-137">Problembeskrivning</span><span class="sxs-lookup"><span data-stu-id="92561-137">Issue description</span></span>

<span data-ttu-id="92561-138">Plats direktiv av typen arbetsorder *försäljningsorder* och arbetstypen *Placera* utvärderar inte flera lokaliseringsdirektivåtgärder när alternativet **Flera SKU-enheter** är valt.</span><span class="sxs-lookup"><span data-stu-id="92561-138">Location directives of the *Sales orders* work order type and the *Put* work type don't evaluate multiple location directive actions when the **Multiple SKU** option is selected.</span></span> <span data-ttu-id="92561-139">Endast den första åtgärden i platsdirektivets utvärderas.</span><span class="sxs-lookup"><span data-stu-id="92561-139">Only the first location directive action is evaluated.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="92561-140">Problemlösning</span><span class="sxs-lookup"><span data-stu-id="92561-140">Issue resolution</span></span>

<span data-ttu-id="92561-141">En ny funktion *Utvärdera alla åtgärder för platsdirektiv med flera SKU-enheter* har lagts till i version 10.0.15 (se [KB 4579866](https://fix.lcs.dynamics.com/Issue/Details?kb=4579866&bugId=475946&dbType=3&qc=1bc41a56de7a3ee419fa76397a6bf282fce5be9b93e427c08a6d916d1dfa3091)).</span><span class="sxs-lookup"><span data-stu-id="92561-141">A new feature, *Evaluate all actions for Multi SKU location directives*, has been added in version 10.0.15 (see [KB 4579866](https://fix.lcs.dynamics.com/Issue/Details?kb=4579866&bugId=475946&dbType=3&qc=1bc41a56de7a3ee419fa76397a6bf282fce5be9b93e427c08a6d916d1dfa3091)).</span></span> <span data-ttu-id="92561-142">Den här funktionen utvärderar alla åtgärder för platsdirektiv med flera SKU-enheter.</span><span class="sxs-lookup"><span data-stu-id="92561-142">This feature evaluates all actions for multi-SKU location directives.</span></span> <span data-ttu-id="92561-143">Om du vill ha denna funktion använd [funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) för att aktivera den.</span><span class="sxs-lookup"><span data-stu-id="92561-143">If you require this feature, use [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) to turn it on.</span></span>

## <a name="i-cant-use-the-warehouse-app-to-do-partial-picking"></a><span data-ttu-id="92561-144">Jag kan inte använda distributionslagerappen för delplockning.</span><span class="sxs-lookup"><span data-stu-id="92561-144">I can't use the warehouse app to do partial picking.</span></span>

### <a name="issue-description"></a><span data-ttu-id="92561-145">Problembeskrivning</span><span class="sxs-lookup"><span data-stu-id="92561-145">Issue description</span></span>

<span data-ttu-id="92561-146">För försäljnings- och överföringsorder kan du inte slopa artiklar och utföra delplockning.</span><span class="sxs-lookup"><span data-stu-id="92561-146">For sales and transfer orders, you can't skip items and do partial picking.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="92561-147">Problemlösning</span><span class="sxs-lookup"><span data-stu-id="92561-147">Issue resolution</span></span>

<span data-ttu-id="92561-148">På sidan **Menyalternativ på mobil enhet** för varje menyalternativ som har ställts in för att bearbeta försäljningsorder eller överföringsorder, anger du alternativet **Tillåt delning av arbete** på snabbfliken **Allmänt** till *Ja*.</span><span class="sxs-lookup"><span data-stu-id="92561-148">On the **Mobile device menu items** page, for each menu item that is set up to process sales orders or transfer orders, set the **Allow splitting of work** option on the **General** FastTab to *Yes*.</span></span>

## <a name="how-can-i-do-an-inventory-status-change-for-partial-quantity-work"></a><span data-ttu-id="92561-149">Hur kan jag göra en lagerstatusändring för delkvantitetsarbete?</span><span class="sxs-lookup"><span data-stu-id="92561-149">How can I do an inventory status change for partial quantity work?</span></span>

### <a name="issue-description"></a><span data-ttu-id="92561-150">Problembeskrivning</span><span class="sxs-lookup"><span data-stu-id="92561-150">Issue description</span></span>

<span data-ttu-id="92561-151">Du vill utföra en lagerstatusändring för en delkvantitet av en batch.</span><span class="sxs-lookup"><span data-stu-id="92561-151">You want to do an inventory status change for a partial quantity of a batch.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="92561-152">Problemlösning</span><span class="sxs-lookup"><span data-stu-id="92561-152">Issue resolution</span></span>

<span data-ttu-id="92561-153">Om du vill att arbetare ska kunna göra denna ändring kan du skapa ett menyalternativ för lagerstället.</span><span class="sxs-lookup"><span data-stu-id="92561-153">To enable workers to make this change, you can create a menu item for the warehouse app.</span></span> <span data-ttu-id="92561-154">På sidan **Menyalternativ på mobil enhet** skapa (eller redigera) ett menyalternativ för följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="92561-154">On the **Mobile device menu items** page, create (or edit) a menu item that has the following settings:</span></span>

- <span data-ttu-id="92561-155">**Läge:** *arbete*</span><span class="sxs-lookup"><span data-stu-id="92561-155">**Mode:** *Work*</span></span>
- <span data-ttu-id="92561-156">**Använd befintligt arbete:** *Nej*</span><span class="sxs-lookup"><span data-stu-id="92561-156">**Use existing work:** *No*</span></span>
- <span data-ttu-id="92561-157">**Arbetsskapandeprocess:** *Rörelse*</span><span class="sxs-lookup"><span data-stu-id="92561-157">**Work creation process:** *Movement*</span></span>
- <span data-ttu-id="92561-158">**Visa lagerstatus:** *Ja*</span><span class="sxs-lookup"><span data-stu-id="92561-158">**Display inventory status:** *Yes*</span></span>

<span data-ttu-id="92561-159">Du kan ställa in andra fält på sidan efter behov.</span><span class="sxs-lookup"><span data-stu-id="92561-159">You can set other fields on the page as you require.</span></span>
