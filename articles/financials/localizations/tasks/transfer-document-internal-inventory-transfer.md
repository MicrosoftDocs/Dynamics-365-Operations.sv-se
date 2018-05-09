--- 
title: "Generera ett överföringsdokument för en intern lageröverföring"
description: "I den här proceduren visas hur du skapar överföringsdokument för varurörelser i ett företag."
author: EvgenyPopovMBS
manager: AnnBe
ms.date: 10/27/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: epopov
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 699f7562f3b3a91f6544f85b892a55d371f4137f
ms.contentlocale: sv-se
ms.lasthandoff: 05/08/2018

---
# <a name="generate-a-transfer-document-for-an-internal-inventory-transfer"></a><span data-ttu-id="0fcad-103">Generera ett överföringsdokument för en intern lageröverföring</span><span class="sxs-lookup"><span data-stu-id="0fcad-103">Generate a transfer document for an internal inventory transfer</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="0fcad-104">I den här proceduren visas hur du skapar överföringsdokument för varurörelser i ett företag.</span><span class="sxs-lookup"><span data-stu-id="0fcad-104">This procedure shows how to create transfer documents for goods movement inside a company.</span></span> <span data-ttu-id="0fcad-105">Denna procedur är bara tillgänglig för juridiska personer med en primär adress i Litauen.</span><span class="sxs-lookup"><span data-stu-id="0fcad-105">This procedure is only available for legal entities with a primary address in Lithuania.</span></span> <span data-ttu-id="0fcad-106">Proceduren skapades med hjälp av demonstrationsdataföretaget DEMF, med primär adress i Litauen.</span><span class="sxs-lookup"><span data-stu-id="0fcad-106">The procedure was created using the demo data company DEMF with a primary address in Lithuania.</span></span> <span data-ttu-id="0fcad-107">Innan du kan slutföra denna procedur måste du först slutföra proceduren "Set up transfer documents for goods movement inside a company".</span><span class="sxs-lookup"><span data-stu-id="0fcad-107">Before you can complete this procedure, you must complete the “Set up transfer documents for goods movement inside a company” procedure.</span></span> <span data-ttu-id="0fcad-108">Proceduren är avsedd för lagerredovisare.</span><span class="sxs-lookup"><span data-stu-id="0fcad-108">This procedure is intended for inventory accountants.</span></span> <span data-ttu-id="0fcad-109">Denna procedur är avsedd för en funktion som lades till i Dynamics 365 for Operations version 1611.</span><span class="sxs-lookup"><span data-stu-id="0fcad-109">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="create-a-transfer-order"></a><span data-ttu-id="0fcad-110">Skapa en överföringsorder</span><span class="sxs-lookup"><span data-stu-id="0fcad-110">Create a transfer order</span></span>
1. <span data-ttu-id="0fcad-111">Gå till Inventory management > Inbound orders > Transfer order.</span><span class="sxs-lookup"><span data-stu-id="0fcad-111">Go to Inventory management > Inbound orders > Transfer order.</span></span>
2. <span data-ttu-id="0fcad-112">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="0fcad-112">Click New.</span></span>
3. <span data-ttu-id="0fcad-113">Ange eller välj ett värde i fältet Från lagerställe.</span><span class="sxs-lookup"><span data-stu-id="0fcad-113">In the From warehouse field, enter or select a value.</span></span>
4. <span data-ttu-id="0fcad-114">Ange eller välj ett värde i fältet Till lagerställe.</span><span class="sxs-lookup"><span data-stu-id="0fcad-114">In the To warehouse field, enter or select a value.</span></span>
5. <span data-ttu-id="0fcad-115">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="0fcad-115">Click Add.</span></span>
6. <span data-ttu-id="0fcad-116">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="0fcad-116">In the list, mark the selected row.</span></span>
7. <span data-ttu-id="0fcad-117">Ange eller välj ett värde i fältet Artikelnummer.</span><span class="sxs-lookup"><span data-stu-id="0fcad-117">In the Item number field, enter or select a value.</span></span>

## <a name="enter-transportation-details-for-the-transfer-order"></a><span data-ttu-id="0fcad-118">Fyll i transportinformation för överföringsordern</span><span class="sxs-lookup"><span data-stu-id="0fcad-118">Enter transportation details for the transfer order</span></span>
1. <span data-ttu-id="0fcad-119">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="0fcad-119">Click Save.</span></span>
2. <span data-ttu-id="0fcad-120">Klicka på Ship i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="0fcad-120">On the Action Pane, click Ship.</span></span>
3. <span data-ttu-id="0fcad-121">Klicka på Transportation details.</span><span class="sxs-lookup"><span data-stu-id="0fcad-121">Click Transportation details.</span></span>
4. <span data-ttu-id="0fcad-122">Välj Yes i fältet Print transportation details.</span><span class="sxs-lookup"><span data-stu-id="0fcad-122">Select Yes in the Print transportation details field.</span></span>
5. <span data-ttu-id="0fcad-123">Ange eller välj ett värde i fältet Goods issued by.</span><span class="sxs-lookup"><span data-stu-id="0fcad-123">In the Goods issued by field, enter or select a value.</span></span>
6. <span data-ttu-id="0fcad-124">Ange ett värde i fältet Package.</span><span class="sxs-lookup"><span data-stu-id="0fcad-124">In the Package field, type a value.</span></span>
7. <span data-ttu-id="0fcad-125">Ange ett värde i fältet Risk level of the load.</span><span class="sxs-lookup"><span data-stu-id="0fcad-125">In the Risk level of the load field, type a value.</span></span>
8. <span data-ttu-id="0fcad-126">Ange eller välj ett värde i fältet Carrier.</span><span class="sxs-lookup"><span data-stu-id="0fcad-126">In the Carrier field, enter or select a value.</span></span>
9. <span data-ttu-id="0fcad-127">Ange eller välj ett värde i fältet Model.</span><span class="sxs-lookup"><span data-stu-id="0fcad-127">In the Model field, enter or select a value.</span></span>
10. <span data-ttu-id="0fcad-128">Ange ett värde i fältet Registration number.</span><span class="sxs-lookup"><span data-stu-id="0fcad-128">In the Registration number field, type a value.</span></span>
11. <span data-ttu-id="0fcad-129">Ange ett värde i fältet Trailer registration number.</span><span class="sxs-lookup"><span data-stu-id="0fcad-129">In the Trailer registration number field, type a value.</span></span>
12. <span data-ttu-id="0fcad-130">Ange eller välj ett värde i fältet Driver.</span><span class="sxs-lookup"><span data-stu-id="0fcad-130">In the Driver field, enter or select a value.</span></span>
13. <span data-ttu-id="0fcad-131">Ange ett värde i fältet Driver name.</span><span class="sxs-lookup"><span data-stu-id="0fcad-131">In the Driver name field, type a value.</span></span>
14. <span data-ttu-id="0fcad-132">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="0fcad-132">Click Save.</span></span>
15. <span data-ttu-id="0fcad-133">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="0fcad-133">Close the page.</span></span>

## <a name="view-the-packing-slip-for-the-unposted-transfer-order"></a><span data-ttu-id="0fcad-134">Visa följesedeln för den ej bokförda överföringsordern</span><span class="sxs-lookup"><span data-stu-id="0fcad-134">View the packing slip for the unposted transfer order</span></span>
1. <span data-ttu-id="0fcad-135">Klicka på Följesedel.</span><span class="sxs-lookup"><span data-stu-id="0fcad-135">Click Packing slip.</span></span>
2. <span data-ttu-id="0fcad-136">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="0fcad-136">Click OK.</span></span>
3. <span data-ttu-id="0fcad-137">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="0fcad-137">Close the page.</span></span>

## <a name="view-the-packing-slip-for-the-posted-transfer-order"></a><span data-ttu-id="0fcad-138">Visa följesedeln för den bokförda överföringsordern</span><span class="sxs-lookup"><span data-stu-id="0fcad-138">View the packing slip for the posted transfer order</span></span>
1. <span data-ttu-id="0fcad-139">Klicka på Transfer order i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="0fcad-139">On the Action Pane, click Transfer order.</span></span>
2. <span data-ttu-id="0fcad-140">Klicka på Ship i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="0fcad-140">On the Action Pane, click Ship.</span></span>
3. <span data-ttu-id="0fcad-141">Klicka på Ship transfer order.</span><span class="sxs-lookup"><span data-stu-id="0fcad-141">Click Ship transfer order.</span></span>
4. <span data-ttu-id="0fcad-142">Klicka på fliken Allmänt.</span><span class="sxs-lookup"><span data-stu-id="0fcad-142">Click the General tab.</span></span>
5. <span data-ttu-id="0fcad-143">Markera ett alternativ i fältet Update.</span><span class="sxs-lookup"><span data-stu-id="0fcad-143">In the Update field, select an option.</span></span>
6. <span data-ttu-id="0fcad-144">Klicka på fliken Översikt.</span><span class="sxs-lookup"><span data-stu-id="0fcad-144">Click the Overview tab.</span></span>
7. <span data-ttu-id="0fcad-145">Skriv ett värde i fältet Följesedel.</span><span class="sxs-lookup"><span data-stu-id="0fcad-145">In the Packing slip field, type a value.</span></span>
8. <span data-ttu-id="0fcad-146">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="0fcad-146">Click OK.</span></span>
9. <span data-ttu-id="0fcad-147">Klicka på Ship i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="0fcad-147">On the Action Pane, click Ship.</span></span>
10. <span data-ttu-id="0fcad-148">Klicka på Följesedel.</span><span class="sxs-lookup"><span data-stu-id="0fcad-148">Click Packing slip.</span></span>
11. <span data-ttu-id="0fcad-149">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="0fcad-149">Click OK.</span></span>


