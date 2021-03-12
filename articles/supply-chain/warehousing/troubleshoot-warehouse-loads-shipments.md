---
title: Felsöka lastuppbyggnad och utleveranser
description: Det här avsnittet beskriver hur du åtgärdar vanliga problem som du kan stöta på när du arbetar med lastuppbyggnad och leveranser i Microsoft Dynamics 365 Supply Chain Management.
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
ms.openlocfilehash: f49a91afe9281f912d6d3579ac8e52cb1d8e5b5d
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "4994063"
---
# <a name="troubleshoot-load-building-and-shipments"></a><span data-ttu-id="2faf2-103">Felsöka lastuppbyggnad och utleveranser</span><span class="sxs-lookup"><span data-stu-id="2faf2-103">Troubleshoot load building and shipments</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="2faf2-104">Det här avsnittet beskriver hur du åtgärdar vanliga problem som du kan stöta på när du arbetar med lastuppbyggnad och leveranser i Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="2faf2-104">This topic describes how to fix common issues that you might encounter while you work with load building and shipments in Microsoft Dynamics 365 Supply Chain Management.</span></span>

## <a name="i-receive-the-following-error-message-you-cant-create-a-load-line-for-this-order-line-because-it-contains-inventory-dimensions-that-are-invalid"></a><span data-ttu-id="2faf2-105">Följande felmeddelande visas: "du kan inte skapa en lastrad för den här orderraden eftersom den innehåller lagerdimensioner som är ogiltiga..."</span><span class="sxs-lookup"><span data-stu-id="2faf2-105">I receive the following error message: "You can't create a load line for this order line because it contains inventory dimensions that are invalid..."</span></span>

### <a name="issue-description"></a><span data-ttu-id="2faf2-106">Problembeskrivning</span><span class="sxs-lookup"><span data-stu-id="2faf2-106">Issue description</span></span>

<span data-ttu-id="2faf2-107">Följande felmeddelande visas när du försöker frisläppa en returförsäljningsorder till lagerstället:</span><span class="sxs-lookup"><span data-stu-id="2faf2-107">You receive the following error message when you try to release a return sales order to the warehouse:</span></span>

> <span data-ttu-id="2faf2-108">Du kan inte skapa en lastrad för den här orderraden eftersom den innehåller lagerdimensioner som är ogiltiga.</span><span class="sxs-lookup"><span data-stu-id="2faf2-108">You can't create a load line for this order line because it contains inventory dimensions that are invalid.</span></span> <span data-ttu-id="2faf2-109">Du kan inte referera lagerdimensioner som finns under platsdimensionen i den här reservationshierarkin.</span><span class="sxs-lookup"><span data-stu-id="2faf2-109">You can't reference inventory dimensions that are located below the location dimension in the reservation hierarchy.</span></span> <span data-ttu-id="2faf2-110">Ta bort de ogiltiga dimensionerna från orderraden.</span><span class="sxs-lookup"><span data-stu-id="2faf2-110">Remove the invalid dimensions from the order line.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="2faf2-111">Problemlösning</span><span class="sxs-lookup"><span data-stu-id="2faf2-111">Issue resolution</span></span>

<span data-ttu-id="2faf2-112">Tyvärr har produkten inte stöd för lastbearbetning för en försäljningsreturprocess.</span><span class="sxs-lookup"><span data-stu-id="2faf2-112">Unfortunately, the product doesn't support load processing for a sales return process.</span></span> <span data-ttu-id="2faf2-113">Därför kan du inte frisläppa returförsäljningsordern till lagerstället.</span><span class="sxs-lookup"><span data-stu-id="2faf2-113">Therefore, you can't release the return sales order to the warehouse.</span></span>

<span data-ttu-id="2faf2-114">På försäljningsordertransaktioner kan du inte referera till lagerdimensioner som ligger under dimensionen **Plats** i reservationshierarkin.</span><span class="sxs-lookup"><span data-stu-id="2faf2-114">On sales order transactions, you can't reference inventory dimensions that are located below the **Location** dimension in the reservation hierarchy.</span></span> <span data-ttu-id="2faf2-115">Upplösningen är att ta bort ogiltiga dimensioner från orderraden.</span><span class="sxs-lookup"><span data-stu-id="2faf2-115">The resolution is to remove the invalid dimensions from the order line.</span></span>

## <a name="i-receive-the-following-error-message-one-of-the-lines-is-already-on-a-load-unable-to-release-to-warehouse"></a><span data-ttu-id="2faf2-116">Följande felmeddelande visas: "en av raderna finns redan i en last.</span><span class="sxs-lookup"><span data-stu-id="2faf2-116">I receive the following error message: "One of the lines is already on a load.</span></span> <span data-ttu-id="2faf2-117">Det gick inte att frisläppa till lagret."</span><span class="sxs-lookup"><span data-stu-id="2faf2-117">Unable to release to warehouse."</span></span>

### <a name="issue-description"></a><span data-ttu-id="2faf2-118">Problembeskrivning</span><span class="sxs-lookup"><span data-stu-id="2faf2-118">Issue description</span></span>

<span data-ttu-id="2faf2-119">Om du manuellt skapar beläggningar eller om du ställer in processen så att lasten redan har skapats innan försäljningsorderrad har angetts, är antagandet att den efterföljande frisläppningen utförs manuellt och att flödet och värderingen från last kommer att användas.</span><span class="sxs-lookup"><span data-stu-id="2faf2-119">If you manually create loads, or if you set up the process so that loads are already created before sales order line entry occurs, the assumption is that the subsequent release will be done manually, and that the route and rating from the load will be used.</span></span>

<span data-ttu-id="2faf2-120">I ett annat scenario försöker du göra en automatisk frisläppning till lagerstället, men påfyllnadsprocessen kunde inte skapa arbete.</span><span class="sxs-lookup"><span data-stu-id="2faf2-120">In another possible scenario, you're trying to do an automatic release to the warehouse, but the wave process failed to create work.</span></span> <span data-ttu-id="2faf2-121">Därför skapas fortfarande en öppen leverans eller last.</span><span class="sxs-lookup"><span data-stu-id="2faf2-121">Therefore, an open shipment or load is still created.</span></span> <span data-ttu-id="2faf2-122">Den här öppna försändelsen eller lasten spärrar sedan de efterföljande försöken att automatiskt frisläppa ordern tills du antingen tar bort den öppna försändelsen eller lasten, eller manuellt ombearbetar påfyllning.</span><span class="sxs-lookup"><span data-stu-id="2faf2-122">This open shipment or load then blocks subsequent attempts to automatically release the order until you either delete the open shipment or load, or manually reprocess the wave.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="2faf2-123">Problemlösning</span><span class="sxs-lookup"><span data-stu-id="2faf2-123">Issue resolution</span></span>

<span data-ttu-id="2faf2-124">Du kan frisläppa från sidan försäljningsorder, eller automatisk frisläppning kan göras från sidan Frisläpp försäljningsorder, endast om det inte finns någon last före frisläppandet till lagerstället.</span><span class="sxs-lookup"><span data-stu-id="2faf2-124">You can release from the sales order page, or automatic release can be done from the release sales order page, only if no load exists before the release to the warehouse.</span></span> <span data-ttu-id="2faf2-125">Lasten skapas automatiskt när påfyllnad har bearbetats.</span><span class="sxs-lookup"><span data-stu-id="2faf2-125">The load will automatically be created after the wave is processed.</span></span>

## <a name="i-receive-the-following-error-message-the-delivery-note-correction-cant-be-processed-the-delivery-note-only-contains-items-that-are-subject-to-warehouse-management-processes-as-these-are-not-supported-by-delivery-note-correction"></a><span data-ttu-id="2faf2-126">Följande felmeddelande visas: "korrigeringen av följesedel kan inte bearbetas.</span><span class="sxs-lookup"><span data-stu-id="2faf2-126">I receive the following error message: "The delivery note correction can't be processed.</span></span> <span data-ttu-id="2faf2-127">Följesedeln innehåller endast artiklar som är föremål för lagerstyrningsprocesser, eftersom dessa inte stöds av korrigering av följesedel".</span><span class="sxs-lookup"><span data-stu-id="2faf2-127">The delivery note only contains items that are subject to warehouse management processes, as these are not supported by Delivery Note correction."</span></span>

### <a name="issue-description"></a><span data-ttu-id="2faf2-128">Problembeskrivning</span><span class="sxs-lookup"><span data-stu-id="2faf2-128">Issue description</span></span>

<span data-ttu-id="2faf2-129">När du har bokfört en följesedel kan du inte annullera den eftersom knappen **Avbryt** inte är tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="2faf2-129">After you post a delivery note, you can't cancel it, because the **Cancel** button is unavailable.</span></span> <span data-ttu-id="2faf2-130">Det går inte heller att korrigera följesedeln.</span><span class="sxs-lookup"><span data-stu-id="2faf2-130">You also can't correct the delivery note.</span></span> <span data-ttu-id="2faf2-131">Det här felmeddelandet visas om du försöker igen.</span><span class="sxs-lookup"><span data-stu-id="2faf2-131">If you try, you receive this error message.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="2faf2-132">Problemlösning</span><span class="sxs-lookup"><span data-stu-id="2faf2-132">Issue resolution</span></span>

<span data-ttu-id="2faf2-133">Om du vill korrigera bokförda följesedlar för artiklar som är aktiverade för WMS (avancerad lagerstyrning) måste du utföra bokföringen från lasten, inte direkt från ordern.</span><span class="sxs-lookup"><span data-stu-id="2faf2-133">To correct posted packing slips for items that are enabled for advanced warehouse management (WMS), you must do the posting from the load, not directly from the order.</span></span>

## <a name="how-can-i-create-work-from-outbound-loads-instead-of-waves"></a><span data-ttu-id="2faf2-134">Hur kan jag skapa arbete från utgående laster i stället för påfyllningar?</span><span class="sxs-lookup"><span data-stu-id="2faf2-134">How can I create work from outbound loads instead of waves?</span></span>

### <a name="issue-description"></a><span data-ttu-id="2faf2-135">Problembeskrivning</span><span class="sxs-lookup"><span data-stu-id="2faf2-135">Issue description</span></span>

<span data-ttu-id="2faf2-136">Här finns ett sätt att reproducera problemet.</span><span class="sxs-lookup"><span data-stu-id="2faf2-136">Here is one way to reproduce this issue.</span></span>

1. <span data-ttu-id="2faf2-137">Skapa en utgående last med en försäljningsorder eller överföringsorder.</span><span class="sxs-lookup"><span data-stu-id="2faf2-137">Create an outbound load by using a sales order or transfer order.</span></span>
2. <span data-ttu-id="2faf2-138">Frisläpp lasten till lagerstället.</span><span class="sxs-lookup"><span data-stu-id="2faf2-138">Release the load to the warehouse.</span></span>
3. <span data-ttu-id="2faf2-139">Observera att inget plockningsarbete har skapats ännu.</span><span class="sxs-lookup"><span data-stu-id="2faf2-139">Notice that no picking work has yet been generated.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="2faf2-140">Problemlösning</span><span class="sxs-lookup"><span data-stu-id="2faf2-140">Issue resolution</span></span>

<span data-ttu-id="2faf2-141">Om arbete måste genereras direkt när lasten frigörs måste du konfigurera påfyllningsmallen i enlighet med detta.</span><span class="sxs-lookup"><span data-stu-id="2faf2-141">If work must be generated immediately when the load is released, you must configure the wave template accordingly.</span></span> <span data-ttu-id="2faf2-142">Ställ in följande alternativ på påfyllningsmallen *Ja*:</span><span class="sxs-lookup"><span data-stu-id="2faf2-142">On the wave template, set the following options to *Yes*:</span></span>

- <span data-ttu-id="2faf2-143">Automatisera skapande av påfyllnad</span><span class="sxs-lookup"><span data-stu-id="2faf2-143">Automate wave creation</span></span>
- <span data-ttu-id="2faf2-144">Bearbeta påfyllnaden vid släpp till lager</span><span class="sxs-lookup"><span data-stu-id="2faf2-144">Process wave at release to warehouse</span></span>
- <span data-ttu-id="2faf2-145">Automatisera släpp av påfyllnad</span><span class="sxs-lookup"><span data-stu-id="2faf2-145">Automate wave release</span></span>

## <a name="i-cant-re-release-a-partially-shipped-load"></a><span data-ttu-id="2faf2-146">Jag kan inte släppa upp en delvis levererad last.</span><span class="sxs-lookup"><span data-stu-id="2faf2-146">I can't re-release a partially shipped load.</span></span>

### <a name="issue-description"></a><span data-ttu-id="2faf2-147">Problembeskrivning</span><span class="sxs-lookup"><span data-stu-id="2faf2-147">Issue description</span></span>

<span data-ttu-id="2faf2-148">Du kan inte frisläppa en delvis levererad last till lagerstället.</span><span class="sxs-lookup"><span data-stu-id="2faf2-148">You can't release a partially shipped load to the warehouse.</span></span> <span data-ttu-id="2faf2-149">När du gör frisläppningen till lagerstället visas meddelandet "åtgärden är slutförd", men ingenting händer och inget arbete skapas för den återstående kvantiteten.</span><span class="sxs-lookup"><span data-stu-id="2faf2-149">When you do the release to the warehouse, an "Operation complete" message appears, but nothing happens, and no work is created for the remaining quantity.</span></span> <span data-ttu-id="2faf2-150">Det här problemet uppstår när du använder funktionen för transportlast och det finns en ofullständig reservation.</span><span class="sxs-lookup"><span data-stu-id="2faf2-150">This issue occurs when you use transport load functionality and there is an incomplete reservation.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="2faf2-151">Problemlösning</span><span class="sxs-lookup"><span data-stu-id="2faf2-151">Issue resolution</span></span>

<span data-ttu-id="2faf2-152">[KB-ärende 470069](https://fix.lcs.dynamics.com/Issue/Details?kb=4574490&bugId=470069&dbType=3&qc=84ce1e09d7032d8b8ef86f5a0c68b86badf3dfaf29686c5ebbe97c53c0957b5f) ("delvis levererade laster kan återpåfyllas och återbearbetas") har korrigerats i [version 10.0.15](../get-started/whats-new-scm-10-0-15.md).</span><span class="sxs-lookup"><span data-stu-id="2faf2-152">[KB issue 470069](https://fix.lcs.dynamics.com/Issue/Details?kb=4574490&bugId=470069&dbType=3&qc=84ce1e09d7032d8b8ef86f5a0c68b86badf3dfaf29686c5ebbe97c53c0957b5f) ("Partially shipped loads can be re-waved and re-processed") is fixed in [release 10.0.15](../get-started/whats-new-scm-10-0-15.md).</span></span>
