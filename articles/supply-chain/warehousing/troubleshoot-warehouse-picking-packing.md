---
title: Felsöka plockning och packning
description: I det här avsnittet beskrivs hur du åtgärdar vanliga problem som kan uppstå när du ställer in plockning och packning i Microsoft Dynamics 365 Supply Chain Management.
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
ms.openlocfilehash: 01e33b63e09a035f5243bd57faf53b522737c987
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5223252"
---
# <a name="troubleshoot-picking-and-packing"></a><span data-ttu-id="3c40b-103">Felsöka plockning och packning</span><span class="sxs-lookup"><span data-stu-id="3c40b-103">Troubleshoot picking and packing</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="3c40b-104">I det här avsnittet beskrivs hur du åtgärdar vanliga problem som kan uppstå när du ställer in plockning och packning i Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="3c40b-104">This topic describes how to fix common issues that you might encounter while you pick and pack in Microsoft Dynamics 365 Supply Chain Management.</span></span>

## <a name="i-receive-the-following-error-message-dimension-location-cant-be-left-blank-if-dimension-serial-number-is-set"></a><span data-ttu-id="3c40b-105">Följande felmeddelande visas: "dimensionsplats kan inte lämnas tom om serienummer för dimension har angetts."</span><span class="sxs-lookup"><span data-stu-id="3c40b-105">I receive the following error message: "Dimension location can't be left blank if dimension serial number is set."</span></span>

### <a name="issue-description"></a><span data-ttu-id="3c40b-106">Problembeskrivning</span><span class="sxs-lookup"><span data-stu-id="3c40b-106">Issue description</span></span>

<span data-ttu-id="3c40b-107">Det här felmeddelandet visas om du skapar en överföringsorder för varor med serienummer med hjälp av ett lagerställe som har aktiveratstas för WMS (avancerad lagerstyrning) och du sedan försöker bekräfta leveransen när arbetet har slutförts.</span><span class="sxs-lookup"><span data-stu-id="3c40b-107">You receive this error message if you create a transfer order for a serial item by using a warehouse that is enabled for advanced warehouse management (WMS), and then, after the work is completed, you try to confirm the shipment.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="3c40b-108">Problemlösning</span><span class="sxs-lookup"><span data-stu-id="3c40b-108">Issue resolution</span></span>

<span data-ttu-id="3c40b-109">Fältet **Standardinleveransplats** är tomt för transit lager av "från"-lagerstället.</span><span class="sxs-lookup"><span data-stu-id="3c40b-109">The **Default receipt location** field is blank for a transit warehouse of the "from" warehouse.</span></span> <span data-ttu-id="3c40b-110">Du åtgärdar det här problemet genom att ange en standard inleveransplats i transitlagret.</span><span class="sxs-lookup"><span data-stu-id="3c40b-110">To fix this issue, specify a default receipt location in the transit warehouse.</span></span> <span data-ttu-id="3c40b-111">Kontrollera att den här platsen styrs av ett ID-nummer.</span><span class="sxs-lookup"><span data-stu-id="3c40b-111">Make sure that this location is license plate–controlled.</span></span>

## <a name="i-receive-the-following-error-message-invalid-license-plate"></a><span data-ttu-id="3c40b-112">Följande felmeddelande visas: "Ogiltigt ID-nummer".</span><span class="sxs-lookup"><span data-stu-id="3c40b-112">I receive the following error message: "Invalid license plate."</span></span>

### <a name="issue-description"></a><span data-ttu-id="3c40b-113">Problembeskrivning</span><span class="sxs-lookup"><span data-stu-id="3c40b-113">Issue description</span></span>

<span data-ttu-id="3c40b-114">Det här felmeddelandet i distributionslagerappen visas när du skannar ett ID-nummer.</span><span class="sxs-lookup"><span data-stu-id="3c40b-114">You receive this error message in the warehouse app when you scan a license plate ID.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="3c40b-115">Problemlösning</span><span class="sxs-lookup"><span data-stu-id="3c40b-115">Issue resolution</span></span>

<span data-ttu-id="3c40b-116">Kontrol lera att det finns ett ID-nummer i registret med ID-nummer och att artiklarna och kvantiteterna på ID-numret är tillgängliga (dvs. de spärras inte).</span><span class="sxs-lookup"><span data-stu-id="3c40b-116">Make sure that the license plate ID exists in the license plates table, and that the items and quantities on the license plate are available (in other words, they aren't blocked).</span></span>

## <a name="i-receive-the-following-error-message-field-load-weight-1-can-only-contain-positive-numbers-update-has-been-canceled"></a><span data-ttu-id="3c40b-117">Jag får följande felmeddelande: "fältet Lastvikt (=-%1) kan bara innehålla positiva tal.</span><span class="sxs-lookup"><span data-stu-id="3c40b-117">I receive the following error message: "Field 'Load weight'(=-%1) can only contain positive numbers.</span></span> <span data-ttu-id="3c40b-118">Uppdateringen har avbrutits".</span><span class="sxs-lookup"><span data-stu-id="3c40b-118">Update has been canceled."</span></span>

### <a name="issue-description"></a><span data-ttu-id="3c40b-119">Problembeskrivning</span><span class="sxs-lookup"><span data-stu-id="3c40b-119">Issue description</span></span>

<span data-ttu-id="3c40b-120">Det här felmeddelandet visas om det är öppet när du bearbetar arbete från förpackningsplatser till mellan platser, eller från mellanlagringsplatser till dockningsplatser.</span><span class="sxs-lookup"><span data-stu-id="3c40b-120">You receive this error message if there is open work when you process work from packing locations to staging locations, or from staging locations to dock locations.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="3c40b-121">Problemlösning</span><span class="sxs-lookup"><span data-stu-id="3c40b-121">Issue resolution</span></span>

<span data-ttu-id="3c40b-122">Du löser det här problemet genom att gå till **Systemadministration \> Periodiska uppgifter \> Databas \> Konsekvenskontroll** och köra processen för **Konsekvenskontroll för lagerplatsstatus**.</span><span class="sxs-lookup"><span data-stu-id="3c40b-122">To fix this issue, go to **System administration \> Periodic tasks \> Database \> Consistency check**, and run the process for **Warehouse load weight consistency check**.</span></span>

## <a name="i-receive-the-following-error-message-the-quantity-is-not-valid-for-unit-1"></a><span data-ttu-id="3c40b-123">Jag får följande felmeddelande: "Kvantiteten gäller inte för enhet %1."</span><span class="sxs-lookup"><span data-stu-id="3c40b-123">I receive the following error message: "The quantity is not valid for unit %1."</span></span>

### <a name="issue-description"></a><span data-ttu-id="3c40b-124">Problembeskrivning</span><span class="sxs-lookup"><span data-stu-id="3c40b-124">Issue description</span></span>

<span data-ttu-id="3c40b-125">Det här felmeddelandet visas när du försöker göra en *delad plockning* i flera batchar.</span><span class="sxs-lookup"><span data-stu-id="3c40b-125">You receive this error message when you try to perform a *split pick* across multiple batches.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="3c40b-126">Problemlösning</span><span class="sxs-lookup"><span data-stu-id="3c40b-126">Issue resolution</span></span>

<span data-ttu-id="3c40b-127">Lagerarbetaren måste använda en process *kort plockning* i distributionslagerappen.</span><span class="sxs-lookup"><span data-stu-id="3c40b-127">The warehouse worker must use the *Short picking* process in the warehouse app.</span></span> <span data-ttu-id="3c40b-128">Om du försöker att plocka flera batchar från samma plats kan du även använda alternativet **fullständig** i distributionslagerappen.</span><span class="sxs-lookup"><span data-stu-id="3c40b-128">If you're trying to pick multiple batches from the same location, you can also use the **Full** option in the warehouse app.</span></span>

## <a name="i-cant-move-inventory-to-a-location-that-is-license-platecontrolled"></a><span data-ttu-id="3c40b-129">Jag kan inte flytta lagret till en plats som är kontrollerad av ID-nummer.</span><span class="sxs-lookup"><span data-stu-id="3c40b-129">I can't move inventory to a location that is license plate–controlled.</span></span>

### <a name="issue-description"></a><span data-ttu-id="3c40b-130">Problembeskrivning</span><span class="sxs-lookup"><span data-stu-id="3c40b-130">Issue description</span></span>

<span data-ttu-id="3c40b-131">Du kan inte minska plockade kvantiteter på en last.</span><span class="sxs-lookup"><span data-stu-id="3c40b-131">You can't reduce picked quantities on a load.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="3c40b-132">Problemlösning</span><span class="sxs-lookup"><span data-stu-id="3c40b-132">Issue resolution</span></span>

<span data-ttu-id="3c40b-133">I tidigare versioner kunde du inte minska plockade kvantiteter på en last.</span><span class="sxs-lookup"><span data-stu-id="3c40b-133">In earlier versions, you can't reduce picked quantities on a load.</span></span> <span data-ttu-id="3c40b-134">Du kan dock nu välja bort till en plats som kontrolleras av ID-nummer.</span><span class="sxs-lookup"><span data-stu-id="3c40b-134">However, you can now unpick to a license plate–controlled location.</span></span> <span data-ttu-id="3c40b-135">Du måste ange både ett värde för **plats** och ett värde för **ID-nummer** för lastraden **Minska plockad kvantitet**.</span><span class="sxs-lookup"><span data-stu-id="3c40b-135">You must specify both a **Location** value and a **License plate** value for the load line on the **Reduce picked quantity** page.</span></span>

## <a name="can-i-print-a-delivery-note-or-packing-content-by-warehouse"></a><span data-ttu-id="3c40b-136">Kan jag skriva ut en följesedel eller förpackningsinnehåll per lagerställe?</span><span class="sxs-lookup"><span data-stu-id="3c40b-136">Can I print a delivery note or packing content by warehouse?</span></span>

### <a name="issue-description"></a><span data-ttu-id="3c40b-137">Problembeskrivning</span><span class="sxs-lookup"><span data-stu-id="3c40b-137">Issue description</span></span>

<span data-ttu-id="3c40b-138">Du vill skriva ut en följesedel eller ett förpackningsinnehåll per lagerställe eller plats på sidan **raduppdatering av arbetsgranskningsmall**.</span><span class="sxs-lookup"><span data-stu-id="3c40b-138">You want to print a delivery note or packing content by warehouse or site on the **Work audit template line update** page.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="3c40b-139">Problemlösning</span><span class="sxs-lookup"><span data-stu-id="3c40b-139">Issue resolution</span></span>

<span data-ttu-id="3c40b-140">När du skriver ut ett dokument med inställningar för utskriftshantering, begränsar du omfattningen (webbplats/lager) genom utskriftshantering istället för genom att välja **Redigera utskriftsinställningar** på sidan **Raduppdatering av arbetsgranskningsmall**.</span><span class="sxs-lookup"><span data-stu-id="3c40b-140">When you print a document by using Print management settings, limit the scope (site/warehouse) through Print management instead of by selecting **Edit print settings** on the **Work audit template line update** page.</span></span>

## <a name="i-cant-cancel-a-packing-slip-after-its-posted-from-a-sales-order"></a><span data-ttu-id="3c40b-141">Jag kan inte annullera en följesedel efter att den har bokförts från en försäljningsorder.</span><span class="sxs-lookup"><span data-stu-id="3c40b-141">I can't cancel a packing slip after it's posted from a sales order.</span></span>

### <a name="issue-description"></a><span data-ttu-id="3c40b-142">Problembeskrivning</span><span class="sxs-lookup"><span data-stu-id="3c40b-142">Issue description</span></span>

<span data-ttu-id="3c40b-143">När plocknings- och leveransprocesser är aktiverade för WMS kan du inte annullera en följesedel efter att den har bokförts från en försäljningsorder.</span><span class="sxs-lookup"><span data-stu-id="3c40b-143">When picking and shipping processes are enabled for WMS, you can't cancel a packing slip after it's posted from a sales order.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="3c40b-144">Problemlösning</span><span class="sxs-lookup"><span data-stu-id="3c40b-144">Issue resolution</span></span>

<span data-ttu-id="3c40b-145">För att korrigera bokförda paket för artiklar som är aktiverade för WMS måste bokningen ske från lasten, inte från beställningen.</span><span class="sxs-lookup"><span data-stu-id="3c40b-145">To correct posted packing slips for items that are enabled for WMS, the posting must occur from the load, not from the order.</span></span> <span data-ttu-id="3c40b-146">Microsoft har utvärderat det här problemet och har fastställt att det är en funktionsbegränsning.</span><span class="sxs-lookup"><span data-stu-id="3c40b-146">Microsoft has evaluated this issue and has determined that it's a feature limitation.</span></span> <span data-ttu-id="3c40b-147">I allmänhet kan en försäljningsorder som har plockats och levererats via lagerstyrningsprocesser följesedel – uppdateras från beläggningen eller utleveransen och själva försäljningsorderdokumentet.</span><span class="sxs-lookup"><span data-stu-id="3c40b-147">In general, a sales order that has been picked and shipped through warehouse management processes can be packing slip–updated from the load or shipment and the sales order document itself.</span></span> <span data-ttu-id="3c40b-148">Om du packar upp försäljningsordern från försäljningsorderdokumentet kan det dock fortfarande inte göras någon återföring av följesedeln från försäljningsordern.</span><span class="sxs-lookup"><span data-stu-id="3c40b-148">However, if you packing slip–update the sales order from the sales order document, packing slip reversal still can't be done from the load or sales order.</span></span> <span data-ttu-id="3c40b-149">Därför rekommenderar vi att du använder följesedels bokföringen från lasten.</span><span class="sxs-lookup"><span data-stu-id="3c40b-149">Therefore, we recommend that you use the packing slip posting from the load.</span></span> <span data-ttu-id="3c40b-150">I det här fallet kommer den återföring som måste göras från lasten att aktiveras.</span><span class="sxs-lookup"><span data-stu-id="3c40b-150">In this case, the reversal that must be done from the load will be enabled.</span></span>

## <a name="i-receive-the-following-error-message-not-enough-work-can-be-found-for-cluster"></a><span data-ttu-id="3c40b-151">Jag får följande felmeddelande: "det går inte att hitta tillräckligt med arbete för klustret."</span><span class="sxs-lookup"><span data-stu-id="3c40b-151">I receive the following error message: "Not enough work can be found for cluster."</span></span>

### <a name="issue-description"></a><span data-ttu-id="3c40b-152">Problembeskrivning</span><span class="sxs-lookup"><span data-stu-id="3c40b-152">Issue description</span></span>

<span data-ttu-id="3c40b-153">När du använder processen *Systemdirigerad klusterplockning* om du konfigurerar en klusterprofil där till exempel 10 positioner kan väljas, fungerar processen som planerat när det finns tillräckligt med arbete för att välja till 10 positioner.</span><span class="sxs-lookup"><span data-stu-id="3c40b-153">When you use the *System directed cluster picking* process, if you configure a cluster profile where, for example, 10 positions can be picked, the process works as planned when there is enough work to pick to 10 positions.</span></span> <span data-ttu-id="3c40b-154">Om det bara finns åtta positioner att plocka får du det här felmeddelandet, eftersom det inte finns tillräckligt med arbete för ett kluster.</span><span class="sxs-lookup"><span data-stu-id="3c40b-154">However, if there are only eight positions to pick, you receive this error message, because there isn't enough work for one cluster.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="3c40b-155">Problemlösning</span><span class="sxs-lookup"><span data-stu-id="3c40b-155">Issue resolution</span></span>

<span data-ttu-id="3c40b-156">Åtgärda problemet genom att redigera klusterprofilen och ställa in alternativet **Aktivera positioner** på *Nej*.</span><span class="sxs-lookup"><span data-stu-id="3c40b-156">To fix this issue, edit the cluster profile, and set the **Activate positions** option to *No*.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]