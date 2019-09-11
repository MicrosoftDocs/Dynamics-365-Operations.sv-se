---
title: Konfigurera transportföretag
description: I det här avsnittet beskrivs hur du ställer in ett transportföretag och definierar detaljer som tjänster, leveranssätt, transportanbud, transportbegränsningar och leveranskostnader.
author: ShylaThompson
manager: AnnBe
ms.date: 07/19/2019
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
ms.openlocfilehash: 7a43a99e10b915f1265be14f2442069dae3a22e5
ms.sourcegitcommit: a368682f9cf3897347d155f1a2d4b33e555cc2c4
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/08/2019
ms.locfileid: "1867037"
---
# <a name="set-up-shipping-carriers"></a><span data-ttu-id="efb8f-103">Konfigurera transportföretag</span><span class="sxs-lookup"><span data-stu-id="efb8f-103">Set up shipping carriers</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="efb8f-104">I det här avsnittet beskrivs hur du ställer in ett transportföretag och definierar detaljer som tjänster, leveranssätt, transportanbud, transportbegränsningar och leveranskostnader.</span><span class="sxs-lookup"><span data-stu-id="efb8f-104">This topic shows how to set up a shipping carrier and define details such as service, shipment mode, transportation tender, transportation constraints, and shipping rate.</span></span> <span data-ttu-id="efb8f-105">En transportkoordinator kan sedan tilldela ett transportföretag till en inkommande eller utgående beläggning.</span><span class="sxs-lookup"><span data-stu-id="efb8f-105">A transportation coordinator can then assign a shipping carrier to an inbound or outbound load.</span></span>


## <a name="create-a-new-shipping-carrier"></a><span data-ttu-id="efb8f-106">Skapa ett nytt transportföretag</span><span class="sxs-lookup"><span data-stu-id="efb8f-106">Create a new shipping carrier</span></span>
1. <span data-ttu-id="efb8f-107">Gå till **Navigeringsfönster > Moduler >Transporthantering > Inställningar > Transportföretag > Transportföretag**.</span><span class="sxs-lookup"><span data-stu-id="efb8f-107">Go to **Navigation pane > Modules > Transportation management > Setup > Carriers > Shipping carriers**.</span></span>
2. <span data-ttu-id="efb8f-108">Välj **Ny** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="efb8f-108">Select **New** in the Action pane.</span></span>
3. <span data-ttu-id="efb8f-109">Skriv ett värde i fältet **Transportföretag**.</span><span class="sxs-lookup"><span data-stu-id="efb8f-109">In the **Shipping carrier** field, type a value.</span></span>
4. <span data-ttu-id="efb8f-110">Skriv ett värde i fältet **Namn**.</span><span class="sxs-lookup"><span data-stu-id="efb8f-110">In the **Name** field, type a value.</span></span>
5. <span data-ttu-id="efb8f-111">I fältet **Metod** väljer du ett alternativ i den nedrullningsbara menyn.</span><span class="sxs-lookup"><span data-stu-id="efb8f-111">In the **Mode** field, select an option from the drop-down menu.</span></span>

## <a name="fill-in-the-general-information-for-the-shipping-carrier"></a><span data-ttu-id="efb8f-112">Fyll i den allmänna informationen för transportföretaget</span><span class="sxs-lookup"><span data-stu-id="efb8f-112">Fill in the general information for the shipping carrier</span></span>
1. <span data-ttu-id="efb8f-113">Växla expanderingen av avsnittet **Översikt**.</span><span class="sxs-lookup"><span data-stu-id="efb8f-113">Toggle the expansion of the **Overview** section.</span></span>
2. <span data-ttu-id="efb8f-114">Markera eller avmarkera kryssrutan **Aktivera transportföretag**.</span><span class="sxs-lookup"><span data-stu-id="efb8f-114">Check or uncheck the **Activate shipping carrier** checkbox.</span></span>
3. <span data-ttu-id="efb8f-115">I fältet **Leverantörskonto** väljer du ett alternativ i den nedrullningsbara menyn.</span><span class="sxs-lookup"><span data-stu-id="efb8f-115">In the **Vendor account** field, select an option from the drop-down menu.</span></span> <span data-ttu-id="efb8f-116">Välj det leverantörskonto som du vill tilldela transportföretaget till.</span><span class="sxs-lookup"><span data-stu-id="efb8f-116">Select the vendor account to assign the shipping carrier to.</span></span>  
4. <span data-ttu-id="efb8f-117">Välj ett alternativ i fältet **Typ av transportanbud**.</span><span class="sxs-lookup"><span data-stu-id="efb8f-117">In the **Transportation tender type** field, select an option.</span></span> <span data-ttu-id="efb8f-118">Välj **Manuell** för att använda sidan Transportanbud eller välj **EDI** för att uppdatera anbudet med hjälp av EDI (Electronic Data Interchange).</span><span class="sxs-lookup"><span data-stu-id="efb8f-118">Select **Manual** to use the Transportation Tender page, or select **EDI** to update the tender by using Electronic Data Interchange (EDI).</span></span>  
5. <span data-ttu-id="efb8f-119">Markera eller avmarkera kryssrutan **Aktivera värdering av transportföretag**.</span><span class="sxs-lookup"><span data-stu-id="efb8f-119">Check or uncheck the **Activate carrier rating** checkbox.</span></span>

## <a name="create-the-necessary-services-for-the-shipping-carrier"></a><span data-ttu-id="efb8f-120">Skapa nödvändiga tjänster för det transportföretaget</span><span class="sxs-lookup"><span data-stu-id="efb8f-120">Create the necessary services for the shipping carrier</span></span>
1. <span data-ttu-id="efb8f-121">Växla expanderingen av avsnittet **Tjänster**.</span><span class="sxs-lookup"><span data-stu-id="efb8f-121">Toggle the expansion of the **Services** section.</span></span>
2. <span data-ttu-id="efb8f-122">Välj **Ny**.</span><span class="sxs-lookup"><span data-stu-id="efb8f-122">Select **New**.</span></span>
3. <span data-ttu-id="efb8f-123">Skriv ett värde i fältet **Transportföretagstjänst**.</span><span class="sxs-lookup"><span data-stu-id="efb8f-123">In the **Carrier service** field, type a value.</span></span>
4. <span data-ttu-id="efb8f-124">Skriv ett värde i fältet **Namn**.</span><span class="sxs-lookup"><span data-stu-id="efb8f-124">In the **Name** field, type a value.</span></span>
5. <span data-ttu-id="efb8f-125">I fältet **Transportmetod** väljer du ett alternativ i den nedrullningsbara menyn.</span><span class="sxs-lookup"><span data-stu-id="efb8f-125">In the **Transportation method** field, select an option from the drop-down menu.</span></span>

## <a name="set-up-the-address-for-the-carrier-optional"></a><span data-ttu-id="efb8f-126">Ställ in för adress för transportföretaget (valfritt)</span><span class="sxs-lookup"><span data-stu-id="efb8f-126">Set up the address for the carrier (optional)</span></span>
1. <span data-ttu-id="efb8f-127">Växla utökningen av avsnittet **Adresser** .</span><span class="sxs-lookup"><span data-stu-id="efb8f-127">Toggle the expansion of the **Addresses** section.</span></span>
2. <span data-ttu-id="efb8f-128">Välj **Ny**.</span><span class="sxs-lookup"><span data-stu-id="efb8f-128">Select **New**.</span></span>
3. <span data-ttu-id="efb8f-129">Skriv ett värde i fältet **Namn eller beskrivning**.</span><span class="sxs-lookup"><span data-stu-id="efb8f-129">In the **Name or description** field, type a value.</span></span>
4. <span data-ttu-id="efb8f-130">I fältet **Land/region** väljer du ett alternativ i den nedrullningsbara menyn.</span><span class="sxs-lookup"><span data-stu-id="efb8f-130">In the **Country/region** field, select an option from the drop-down menu.</span></span>
5. <span data-ttu-id="efb8f-131">I fältet **Postnummer** väljer du ett alternativ i den nedrullningsbara menyn.</span><span class="sxs-lookup"><span data-stu-id="efb8f-131">In the **ZIP/postal code** field, select an option from the drop-down menu.</span></span>
6. <span data-ttu-id="efb8f-132">Ange ett värde i fältet **Gata**.</span><span class="sxs-lookup"><span data-stu-id="efb8f-132">In the **Street** field, type a value.</span></span>
7. <span data-ttu-id="efb8f-133">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="efb8f-133">Select **OK**.</span></span>

## <a name="set-up-the-rating-profile-for-the-shipping-carrier"></a><span data-ttu-id="efb8f-134">Ställa in bedömningsprofil för transportföretaget</span><span class="sxs-lookup"><span data-stu-id="efb8f-134">Set up the rating profile for the shipping carrier</span></span>
1. <span data-ttu-id="efb8f-135">Växla expanderingen av avsnittet **Bedömningsprofiler**.</span><span class="sxs-lookup"><span data-stu-id="efb8f-135">Toggle the expansion of the **Rating profiles** section.</span></span>
2. <span data-ttu-id="efb8f-136">Välj **Ny**.</span><span class="sxs-lookup"><span data-stu-id="efb8f-136">Select **New**.</span></span>
3. <span data-ttu-id="efb8f-137">Skriv ett värde i fältet **Bedömningsprofil**.</span><span class="sxs-lookup"><span data-stu-id="efb8f-137">In the **Rating profile** field, type a value.</span></span>
4. <span data-ttu-id="efb8f-138">Skriv ett värde i fältet **Namn**.</span><span class="sxs-lookup"><span data-stu-id="efb8f-138">In the **Name** field, type a value.</span></span>
5. <span data-ttu-id="efb8f-139">I fältet **Plats** väljer du ett alternativ i den nedrullningsbara menyn.</span><span class="sxs-lookup"><span data-stu-id="efb8f-139">In the **Site** field, select an option from the drop-down menu.</span></span>
6. <span data-ttu-id="efb8f-140">I fältet **Lagerställe** väljer du ett alternativ i den nedrullningsbara menyn.</span><span class="sxs-lookup"><span data-stu-id="efb8f-140">In the **Warehouse** field, select an option from the drop-down menu.</span></span>
7. <span data-ttu-id="efb8f-141">I fältet **Tariffmotor** väljer du ett alternativ i den nedrullningsbara menyn.</span><span class="sxs-lookup"><span data-stu-id="efb8f-141">In the **Rate engine** field, select an option from the drop-down menu.</span></span> <span data-ttu-id="efb8f-142">Välj den tariffmotor som överensstämmer med det kontrakt som du har för transportföretaget.</span><span class="sxs-lookup"><span data-stu-id="efb8f-142">Select the Rate engine that is in accordance with the contract that you have with the carrier.</span></span>  
8. <span data-ttu-id="efb8f-143">I fältet **Tariffmall** väljer du ett alternativ i den nedrullningsbara menyn.</span><span class="sxs-lookup"><span data-stu-id="efb8f-143">In the **Rate master** field, select an option from the drop-down menu.</span></span>
9. <span data-ttu-id="efb8f-144">I fältet **Transporttidsmotor** väljer du ett alternativ i den nedrullningsbara menyn.</span><span class="sxs-lookup"><span data-stu-id="efb8f-144">In the **Transit time engine** field, select an option from the drop-down menu.</span></span>
10. <span data-ttu-id="efb8f-145">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="efb8f-145">Select **Save**.</span></span>

