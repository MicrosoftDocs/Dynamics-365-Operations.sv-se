---
title: Konfigurera transportföretag
description: I den här proceduren beskrivs hur du ställer in ett transportföretag och definierar detaljer som tjänster, leveranssätt, transportanbud, transportbegränsningar och leveranskostnader.
author: ShylaThompson
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6c5ac13d17c97f20ee79e7faf57c570f02158424
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2019
ms.locfileid: "314496"
---
# <a name="set-up-shipping-carriers"></a><span data-ttu-id="5f1b9-103">Konfigurera transportföretag</span><span class="sxs-lookup"><span data-stu-id="5f1b9-103">Set up shipping carriers</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="5f1b9-104">I den här proceduren beskrivs hur du ställer in ett transportföretag och definierar detaljer som tjänster, leveranssätt, transportanbud, transportbegränsningar och leveranskostnader.</span><span class="sxs-lookup"><span data-stu-id="5f1b9-104">This procedure shows how to set up a shipping carrier and define details such as service, shipment mode, transportation tender, transportation constraints, and shipping rate.</span></span> <span data-ttu-id="5f1b9-105">En transportkoordinator kan sedan tilldela ett transportföretag till en inkommande eller utgående beläggning.</span><span class="sxs-lookup"><span data-stu-id="5f1b9-105">A transportation coordinator can then assign a shipping carrier to an inbound or outbound load.</span></span>


## <a name="create-a-new-shipping-carrier"></a><span data-ttu-id="5f1b9-106">Skapa ett nytt transportföretag</span><span class="sxs-lookup"><span data-stu-id="5f1b9-106">Create a new shipping carrier</span></span>
1. <span data-ttu-id="5f1b9-107">Gå till Transporthantering > Inställningar > Transportföretag > Transportföretag.</span><span class="sxs-lookup"><span data-stu-id="5f1b9-107">Go to Transportation management > Setup > Carriers > Shipping carriers.</span></span>
2. <span data-ttu-id="5f1b9-108">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="5f1b9-108">Click New.</span></span>
3. <span data-ttu-id="5f1b9-109">Skriv ett värde i fältet Transportföretag.</span><span class="sxs-lookup"><span data-stu-id="5f1b9-109">In the Shipping carrier field, type a value.</span></span>
4. <span data-ttu-id="5f1b9-110">Skriv ett värde i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="5f1b9-110">In the Name field, type a value.</span></span>
5. <span data-ttu-id="5f1b9-111">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Metod.</span><span class="sxs-lookup"><span data-stu-id="5f1b9-111">In the Mode field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="5f1b9-112">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="5f1b9-112">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="5f1b9-113">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="5f1b9-113">In the list, click the link in the selected row.</span></span>

## <a name="fill-in-the-general-information-for-the-shipping-carrier"></a><span data-ttu-id="5f1b9-114">Fyll i den allmänna informationen för transportföretaget</span><span class="sxs-lookup"><span data-stu-id="5f1b9-114">Fill in the general information for the shipping carrier</span></span>
1. <span data-ttu-id="5f1b9-115">Växla expanderingen av avsnittet Översikt.</span><span class="sxs-lookup"><span data-stu-id="5f1b9-115">Toggle the expansion of the Overview section.</span></span>
2. <span data-ttu-id="5f1b9-116">Markera eller avmarkera kryssrutan Aktivera transportföretag.</span><span class="sxs-lookup"><span data-stu-id="5f1b9-116">Check or uncheck the Activate shipping carrier checkbox.</span></span>
3. <span data-ttu-id="5f1b9-117">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Leverantör.</span><span class="sxs-lookup"><span data-stu-id="5f1b9-117">In the Vendor field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="5f1b9-118">Välj det leverantörskonto som du vill tilldela transportföretaget till.</span><span class="sxs-lookup"><span data-stu-id="5f1b9-118">Select the vendor account to assign the shipping carrier to.</span></span>  
4. <span data-ttu-id="5f1b9-119">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="5f1b9-119">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="5f1b9-120">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="5f1b9-120">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="5f1b9-121">Välj ett alternativ i fältet Typ av transportanbud.</span><span class="sxs-lookup"><span data-stu-id="5f1b9-121">In the Transportation tender type field, select an option.</span></span>
    * <span data-ttu-id="5f1b9-122">Välj Manuell för att använda sidan Transportanbud eller välj EDI för att uppdatera anbudet med hjälp av EDI (Electronic Data Interchange).</span><span class="sxs-lookup"><span data-stu-id="5f1b9-122">Select Manual to use the Transportation Tender page, or select EDI to update the tender by using Electronic Data Interchange (EDI).</span></span>  
7. <span data-ttu-id="5f1b9-123">Markera eller avmarkera kryssrutan Aktivera värdering av transportföretag.</span><span class="sxs-lookup"><span data-stu-id="5f1b9-123">Check or uncheck the Activate carrier rating checkbox.</span></span>

## <a name="create-the-necessary-services-for-the-shipping-carrier"></a><span data-ttu-id="5f1b9-124">Skapa nödvändiga tjänster för det transportföretaget</span><span class="sxs-lookup"><span data-stu-id="5f1b9-124">Create the necessary services for the shipping carrier</span></span>
1. <span data-ttu-id="5f1b9-125">Växla expanderingen av avsnittet Tjänster.</span><span class="sxs-lookup"><span data-stu-id="5f1b9-125">Toggle the expansion of the Services section.</span></span>
2. <span data-ttu-id="5f1b9-126">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="5f1b9-126">Click New.</span></span>
3. <span data-ttu-id="5f1b9-127">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="5f1b9-127">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="5f1b9-128">Skriv ett värde i fältet Transportföretagstjänst.</span><span class="sxs-lookup"><span data-stu-id="5f1b9-128">In the Carrier service field, type a value.</span></span>
5. <span data-ttu-id="5f1b9-129">Skriv ett värde i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="5f1b9-129">In the Name field, type a value.</span></span>
6. <span data-ttu-id="5f1b9-130">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Transportmetod.</span><span class="sxs-lookup"><span data-stu-id="5f1b9-130">In the Transportation method field, click the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="5f1b9-131">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="5f1b9-131">In the list, find and select the desired record.</span></span>
8. <span data-ttu-id="5f1b9-132">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="5f1b9-132">In the list, click the link in the selected row.</span></span>

## <a name="set-up-the-address-for-the-carrier-optional"></a><span data-ttu-id="5f1b9-133">Ställ in för adress för transportföretaget (valfritt)</span><span class="sxs-lookup"><span data-stu-id="5f1b9-133">Set up the address for the carrier (optional)</span></span>
1. <span data-ttu-id="5f1b9-134">Växla utökningen av avsnittet Adresser.</span><span class="sxs-lookup"><span data-stu-id="5f1b9-134">Toggle the expansion of the Addresses section.</span></span>
2. <span data-ttu-id="5f1b9-135">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="5f1b9-135">Click New.</span></span>
3. <span data-ttu-id="5f1b9-136">Skriv ett värde i fältet Namn eller beskrivning.</span><span class="sxs-lookup"><span data-stu-id="5f1b9-136">In the Name or description field, type a value.</span></span>
4. <span data-ttu-id="5f1b9-137">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Land/region.</span><span class="sxs-lookup"><span data-stu-id="5f1b9-137">In the Country/region field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="5f1b9-138">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="5f1b9-138">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="5f1b9-139">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Postnummer.</span><span class="sxs-lookup"><span data-stu-id="5f1b9-139">In the ZIP/postal code field, click the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="5f1b9-140">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="5f1b9-140">In the list, find and select the desired record.</span></span>
8. <span data-ttu-id="5f1b9-141">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="5f1b9-141">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="5f1b9-142">Ange ett värde i fältet Gata.</span><span class="sxs-lookup"><span data-stu-id="5f1b9-142">In the Street field, type a value.</span></span>
10. <span data-ttu-id="5f1b9-143">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="5f1b9-143">Click OK.</span></span>

## <a name="set-up-the-rating-profile-for-the-shipping-carrier"></a><span data-ttu-id="5f1b9-144">Ställa in bedömningsprofil för transportföretaget</span><span class="sxs-lookup"><span data-stu-id="5f1b9-144">Set up the rating profile for the shipping carrier</span></span>
1. <span data-ttu-id="5f1b9-145">Växla expanderingen av avsnittet Bedömningsprofiler.</span><span class="sxs-lookup"><span data-stu-id="5f1b9-145">Toggle the expansion of the Rating profiles section.</span></span>
2. <span data-ttu-id="5f1b9-146">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="5f1b9-146">Click New.</span></span>
3. <span data-ttu-id="5f1b9-147">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="5f1b9-147">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="5f1b9-148">Skriv ett värde i fältet Bedömningsprofil.</span><span class="sxs-lookup"><span data-stu-id="5f1b9-148">In the Rating profile field, type a value.</span></span>
5. <span data-ttu-id="5f1b9-149">Skriv ett värde i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="5f1b9-149">In the Name field, type a value.</span></span>
6. <span data-ttu-id="5f1b9-150">Öppna sökningen genom att klicka på listruteknappen i fältet Plats.</span><span class="sxs-lookup"><span data-stu-id="5f1b9-150">In the Site field, click the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="5f1b9-151">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="5f1b9-151">In the list, find and select the desired record.</span></span>
8. <span data-ttu-id="5f1b9-152">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="5f1b9-152">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="5f1b9-153">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Lagerställe.</span><span class="sxs-lookup"><span data-stu-id="5f1b9-153">In the Warehouse field, click the drop-down button to open the lookup.</span></span>
10. <span data-ttu-id="5f1b9-154">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="5f1b9-154">In the list, find and select the desired record.</span></span>
11. <span data-ttu-id="5f1b9-155">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="5f1b9-155">In the list, click the link in the selected row.</span></span>
12. <span data-ttu-id="5f1b9-156">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Tariffmotor.</span><span class="sxs-lookup"><span data-stu-id="5f1b9-156">In the Rate engine field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="5f1b9-157">Välj den tariffmotor som överensstämmer med det kontrakt som du har för transportföretaget.</span><span class="sxs-lookup"><span data-stu-id="5f1b9-157">Select the Rate engine that is in accordance with the contract that you have with the carrier.</span></span>  
13. <span data-ttu-id="5f1b9-158">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="5f1b9-158">In the list, find and select the desired record.</span></span>
14. <span data-ttu-id="5f1b9-159">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="5f1b9-159">In the list, click the link in the selected row.</span></span>
15. <span data-ttu-id="5f1b9-160">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Tariffmall.</span><span class="sxs-lookup"><span data-stu-id="5f1b9-160">In the Rate master field, click the drop-down button to open the lookup.</span></span>
16. <span data-ttu-id="5f1b9-161">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="5f1b9-161">In the list, find and select the desired record.</span></span>
17. <span data-ttu-id="5f1b9-162">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="5f1b9-162">In the list, click the link in the selected row.</span></span>
18. <span data-ttu-id="5f1b9-163">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Transporttidsmotor.</span><span class="sxs-lookup"><span data-stu-id="5f1b9-163">In the Transit time engine field, click the drop-down button to open the lookup.</span></span>
19. <span data-ttu-id="5f1b9-164">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="5f1b9-164">In the list, click the link in the selected row.</span></span>
20. <span data-ttu-id="5f1b9-165">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="5f1b9-165">Click Save.</span></span>

