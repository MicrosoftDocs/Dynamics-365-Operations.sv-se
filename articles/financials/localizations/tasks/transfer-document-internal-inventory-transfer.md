---
title: Generera ett överföringsdokument för en intern lageröverföring
description: I den här proceduren visas hur du skapar överföringsdokument för varurörelser i ett företag.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventTransferOrders, InventLocationIdLookup, TransportationDocument, HcmWorkerLookUp, SrsReportViewerForm, InventTransferParmShip
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: epopov
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 4b9ef0026129d958b4214bb6e235c288de023d10
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/15/2019
ms.locfileid: "1566659"
---
# <a name="generate-a-transfer-document-for-an-internal-inventory-transfer"></a><span data-ttu-id="bb7ad-103">Generera ett överföringsdokument för en intern lageröverföring</span><span class="sxs-lookup"><span data-stu-id="bb7ad-103">Generate a transfer document for an internal inventory transfer</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="bb7ad-104">I den här proceduren visas hur du skapar överföringsdokument för varurörelser i ett företag.</span><span class="sxs-lookup"><span data-stu-id="bb7ad-104">This procedure shows how to create transfer documents for goods movement inside a company.</span></span> <span data-ttu-id="bb7ad-105">Denna procedur är bara tillgänglig för juridiska personer med en primär adress i Litauen.</span><span class="sxs-lookup"><span data-stu-id="bb7ad-105">This procedure is only available for legal entities with a primary address in Lithuania.</span></span> <span data-ttu-id="bb7ad-106">Proceduren skapades med hjälp av demonstrationsdataföretaget DEMF, med primär adress i Litauen.</span><span class="sxs-lookup"><span data-stu-id="bb7ad-106">The procedure was created using the demo data company DEMF with a primary address in Lithuania.</span></span> <span data-ttu-id="bb7ad-107">Innan du kan slutföra denna procedur måste du först slutföra proceduren "Set up transfer documents for goods movement inside a company".</span><span class="sxs-lookup"><span data-stu-id="bb7ad-107">Before you can complete this procedure, you must complete the “Set up transfer documents for goods movement inside a company” procedure.</span></span> <span data-ttu-id="bb7ad-108">Proceduren är avsedd för lagerredovisare.</span><span class="sxs-lookup"><span data-stu-id="bb7ad-108">This procedure is intended for inventory accountants.</span></span> <span data-ttu-id="bb7ad-109">Denna procedur är avsedd för en funktion som lades till i Dynamics 365 for Operations version 1611.</span><span class="sxs-lookup"><span data-stu-id="bb7ad-109">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="create-a-transfer-order"></a><span data-ttu-id="bb7ad-110">Skapa en överföringsorder</span><span class="sxs-lookup"><span data-stu-id="bb7ad-110">Create a transfer order</span></span>
1. <span data-ttu-id="bb7ad-111">Gå till Inventory management > Inbound orders > Transfer order.</span><span class="sxs-lookup"><span data-stu-id="bb7ad-111">Go to Inventory management > Inbound orders > Transfer order.</span></span>
2. <span data-ttu-id="bb7ad-112">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="bb7ad-112">Click New.</span></span>
3. <span data-ttu-id="bb7ad-113">Ange eller välj ett värde i fältet Från lagerställe.</span><span class="sxs-lookup"><span data-stu-id="bb7ad-113">In the From warehouse field, enter or select a value.</span></span>
4. <span data-ttu-id="bb7ad-114">Ange eller välj ett värde i fältet Till lagerställe.</span><span class="sxs-lookup"><span data-stu-id="bb7ad-114">In the To warehouse field, enter or select a value.</span></span>
5. <span data-ttu-id="bb7ad-115">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="bb7ad-115">Click Add.</span></span>
6. <span data-ttu-id="bb7ad-116">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="bb7ad-116">In the list, mark the selected row.</span></span>
7. <span data-ttu-id="bb7ad-117">Ange eller välj ett värde i fältet Artikelnummer.</span><span class="sxs-lookup"><span data-stu-id="bb7ad-117">In the Item number field, enter or select a value.</span></span>

## <a name="enter-transportation-details-for-the-transfer-order"></a><span data-ttu-id="bb7ad-118">Fyll i transportinformation för överföringsordern</span><span class="sxs-lookup"><span data-stu-id="bb7ad-118">Enter transportation details for the transfer order</span></span>
1. <span data-ttu-id="bb7ad-119">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="bb7ad-119">Click Save.</span></span>
2. <span data-ttu-id="bb7ad-120">Klicka på Ship i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="bb7ad-120">On the Action Pane, click Ship.</span></span>
3. <span data-ttu-id="bb7ad-121">Klicka på Transportation details.</span><span class="sxs-lookup"><span data-stu-id="bb7ad-121">Click Transportation details.</span></span>
4. <span data-ttu-id="bb7ad-122">Välj Yes i fältet Print transportation details.</span><span class="sxs-lookup"><span data-stu-id="bb7ad-122">Select Yes in the Print transportation details field.</span></span>
5. <span data-ttu-id="bb7ad-123">Ange eller välj ett värde i fältet Goods issued by.</span><span class="sxs-lookup"><span data-stu-id="bb7ad-123">In the Goods issued by field, enter or select a value.</span></span>
6. <span data-ttu-id="bb7ad-124">Ange ett värde i fältet Package.</span><span class="sxs-lookup"><span data-stu-id="bb7ad-124">In the Package field, type a value.</span></span>
7. <span data-ttu-id="bb7ad-125">Ange ett värde i fältet Risk level of the load.</span><span class="sxs-lookup"><span data-stu-id="bb7ad-125">In the Risk level of the load field, type a value.</span></span>
8. <span data-ttu-id="bb7ad-126">Ange eller välj ett värde i fältet Carrier.</span><span class="sxs-lookup"><span data-stu-id="bb7ad-126">In the Carrier field, enter or select a value.</span></span>
9. <span data-ttu-id="bb7ad-127">Ange eller välj ett värde i fältet Model.</span><span class="sxs-lookup"><span data-stu-id="bb7ad-127">In the Model field, enter or select a value.</span></span>
10. <span data-ttu-id="bb7ad-128">Ange ett värde i fältet Registration number.</span><span class="sxs-lookup"><span data-stu-id="bb7ad-128">In the Registration number field, type a value.</span></span>
11. <span data-ttu-id="bb7ad-129">Ange ett värde i fältet Trailer registration number.</span><span class="sxs-lookup"><span data-stu-id="bb7ad-129">In the Trailer registration number field, type a value.</span></span>
12. <span data-ttu-id="bb7ad-130">Ange eller välj ett värde i fältet Driver.</span><span class="sxs-lookup"><span data-stu-id="bb7ad-130">In the Driver field, enter or select a value.</span></span>
13. <span data-ttu-id="bb7ad-131">Ange ett värde i fältet Driver name.</span><span class="sxs-lookup"><span data-stu-id="bb7ad-131">In the Driver name field, type a value.</span></span>
14. <span data-ttu-id="bb7ad-132">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="bb7ad-132">Click Save.</span></span>
15. <span data-ttu-id="bb7ad-133">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="bb7ad-133">Close the page.</span></span>

## <a name="view-the-packing-slip-for-the-unposted-transfer-order"></a><span data-ttu-id="bb7ad-134">Visa följesedeln för den ej bokförda överföringsordern</span><span class="sxs-lookup"><span data-stu-id="bb7ad-134">View the packing slip for the unposted transfer order</span></span>
1. <span data-ttu-id="bb7ad-135">Klicka på Följesedel.</span><span class="sxs-lookup"><span data-stu-id="bb7ad-135">Click Packing slip.</span></span>
2. <span data-ttu-id="bb7ad-136">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="bb7ad-136">Click OK.</span></span>
3. <span data-ttu-id="bb7ad-137">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="bb7ad-137">Close the page.</span></span>

## <a name="view-the-packing-slip-for-the-posted-transfer-order"></a><span data-ttu-id="bb7ad-138">Visa följesedeln för den bokförda överföringsordern</span><span class="sxs-lookup"><span data-stu-id="bb7ad-138">View the packing slip for the posted transfer order</span></span>
1. <span data-ttu-id="bb7ad-139">Klicka på Transfer order i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="bb7ad-139">On the Action Pane, click Transfer order.</span></span>
2. <span data-ttu-id="bb7ad-140">Klicka på Ship i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="bb7ad-140">On the Action Pane, click Ship.</span></span>
3. <span data-ttu-id="bb7ad-141">Klicka på Ship transfer order.</span><span class="sxs-lookup"><span data-stu-id="bb7ad-141">Click Ship transfer order.</span></span>
4. <span data-ttu-id="bb7ad-142">Klicka på fliken Allmänt.</span><span class="sxs-lookup"><span data-stu-id="bb7ad-142">Click the General tab.</span></span>
5. <span data-ttu-id="bb7ad-143">Markera ett alternativ i fältet Update.</span><span class="sxs-lookup"><span data-stu-id="bb7ad-143">In the Update field, select an option.</span></span>
6. <span data-ttu-id="bb7ad-144">Klicka på fliken Översikt.</span><span class="sxs-lookup"><span data-stu-id="bb7ad-144">Click the Overview tab.</span></span>
7. <span data-ttu-id="bb7ad-145">Skriv ett värde i fältet Följesedel.</span><span class="sxs-lookup"><span data-stu-id="bb7ad-145">In the Packing slip field, type a value.</span></span>
8. <span data-ttu-id="bb7ad-146">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="bb7ad-146">Click OK.</span></span>
9. <span data-ttu-id="bb7ad-147">Klicka på Ship i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="bb7ad-147">On the Action Pane, click Ship.</span></span>
10. <span data-ttu-id="bb7ad-148">Klicka på Följesedel.</span><span class="sxs-lookup"><span data-stu-id="bb7ad-148">Click Packing slip.</span></span>
11. <span data-ttu-id="bb7ad-149">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="bb7ad-149">Click OK.</span></span>

