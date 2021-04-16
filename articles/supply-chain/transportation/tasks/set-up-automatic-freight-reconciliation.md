---
title: Ställ in automatisk fraktavstämning
description: Denna procedur visar hur du ställer in data för automatisk fraktavstämning.
author: ShylaThompson
ms.date: 10/16/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: TMSFreightBillType, TMSFreightBillTypeAssignment, TMSCarrierCodeLookup, DefaultDashboard, TMSAuditMaster
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e4bc3998dea2e953191151f8e54345ec648ff33e
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5837619"
---
# <a name="set-up-automatic-freight-reconciliation"></a><span data-ttu-id="f002f-103">Ställ in automatisk fraktavstämning</span><span class="sxs-lookup"><span data-stu-id="f002f-103">Set up automatic freight reconciliation</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="f002f-104">Denna procedur visar hur du ställer in data för automatisk fraktavstämning.</span><span class="sxs-lookup"><span data-stu-id="f002f-104">This procedure shows how to set up data for automatic freight reconciliation.</span></span> <span data-ttu-id="f002f-105">Detta utförs normalt av en lagerchef.</span><span class="sxs-lookup"><span data-stu-id="f002f-105">This is typically done by a warehouse manager.</span></span> <span data-ttu-id="f002f-106">Du kan köra den här proceduren i demonstrationsdataföretaget USMF.</span><span class="sxs-lookup"><span data-stu-id="f002f-106">You can use this procedure in demo data company USMF.</span></span>


## <a name="set-up-the-freight-bill-type"></a><span data-ttu-id="f002f-107">Ställ in fraktsedelstypen</span><span class="sxs-lookup"><span data-stu-id="f002f-107">Set up the freight bill type</span></span>
1. <span data-ttu-id="f002f-108">Gå till Transporthantering > Inställningar > Fraktavstämning > Fraktsedelstyp.</span><span class="sxs-lookup"><span data-stu-id="f002f-108">Go to Transportation management > Setup > Freight reconciliation > Freight bill type.</span></span>
    * <span data-ttu-id="f002f-109">Rehabiliteringstypen anger hur frakträkningar och transportfakturor ska matchas.</span><span class="sxs-lookup"><span data-stu-id="f002f-109">The freight bill type defines how freight bills and carrier invoices  should be matched.</span></span>  
2. <span data-ttu-id="f002f-110">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="f002f-110">Click New.</span></span>
3. <span data-ttu-id="f002f-111">Ange ett värde i fältet Fredlighet Bill typ.</span><span class="sxs-lookup"><span data-stu-id="f002f-111">In the Freight bill type field, type a value.</span></span>
4. <span data-ttu-id="f002f-112">Ange "Microsoft.Dynamics.Ax.Tms.dll" i fältet Motorsammansättning.</span><span class="sxs-lookup"><span data-stu-id="f002f-112">In the Engine assembly field, type 'Microsoft.Dynamics.Ax.Tms.dll'.</span></span>
    * <span data-ttu-id="f002f-113">Detta är jodbiblioteket för den vanliga förbränningsmotorn för transportledningen.</span><span class="sxs-lookup"><span data-stu-id="f002f-113">This is the standard Transportation management matching engine code library.</span></span>  
5. <span data-ttu-id="f002f-114">Ange "Microsoft.Dynamics.Ax.Tms.Bll.GenericNormalizer" i fältet Motorklass.</span><span class="sxs-lookup"><span data-stu-id="f002f-114">In the Engine class field, type 'Microsoft.Dynamics.Ax.Tms.Bll.GenericNormalizer'.</span></span>
    * <span data-ttu-id="f002f-115">Detta är den vanliga klassificeringen för transportledningen.</span><span class="sxs-lookup"><span data-stu-id="f002f-115">This is the standard Transportation management matching engine class.</span></span>  
6. <span data-ttu-id="f002f-116">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="f002f-116">Click New.</span></span>
7. <span data-ttu-id="f002f-117">Välj det värde som ska matcha på frakträkningen och transportföretag i fältet Deskription.</span><span class="sxs-lookup"><span data-stu-id="f002f-117">In the Description field, choose the value that should match on the freight bill and the carrier invoice.</span></span>  
8. <span data-ttu-id="f002f-118">Välj "Res" i fältet Match reducibel.</span><span class="sxs-lookup"><span data-stu-id="f002f-118">In the Match required field, select 'Yes'.</span></span>
    * <span data-ttu-id="f002f-119">Om du ställer in detta fält som Res innebär detta att värdet som valdes i fältet Deskription måste matcha både frakträkningen och transportföretag.</span><span class="sxs-lookup"><span data-stu-id="f002f-119">If you set this field to Yes this means that the value selected in the Description field needs to match on both the freight bill and the carrier invoice.</span></span> <span data-ttu-id="f002f-120">Om du har ställt in detta som O kan fältet vara tomt på en av dessa.</span><span class="sxs-lookup"><span data-stu-id="f002f-120">If you set it to No, the field can be blank on one of these.</span></span>  
9. <span data-ttu-id="f002f-121">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="f002f-121">Click Save.</span></span>

## <a name="set-up-the-freight-bill-type-assignment"></a><span data-ttu-id="f002f-122">Ställa in tilldelningen för fraktsedelstyp</span><span class="sxs-lookup"><span data-stu-id="f002f-122">Set up the freight bill type assignment</span></span>
1. <span data-ttu-id="f002f-123">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="f002f-123">Close the page.</span></span>
2. <span data-ttu-id="f002f-124">Gå till Transporthantering > Inställningar > Fraktavstämning > Typtilldelningar för fraktsedel.</span><span class="sxs-lookup"><span data-stu-id="f002f-124">Go to Transportation management > Setup > Freight reconciliation > Freight bill type assignments.</span></span>
    * <span data-ttu-id="f002f-125">Tilldelningen av omräkningstal används för att ange vilken typ av för frakträkning som används för en viss transportör.</span><span class="sxs-lookup"><span data-stu-id="f002f-125">The freight bill type assignment is used to specify which freight bill type is used for a particular carrier.</span></span>   
3. <span data-ttu-id="f002f-126">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="f002f-126">Click New.</span></span>
4. <span data-ttu-id="f002f-127">Ange eller välj ett värde i fältet Mode.</span><span class="sxs-lookup"><span data-stu-id="f002f-127">In the Mode field, enter or select a value.</span></span>
5. <span data-ttu-id="f002f-128">Ange eller välj ett värde i fältet Shopping Harriet.</span><span class="sxs-lookup"><span data-stu-id="f002f-128">In the Shipping carrier field, enter or select a value.</span></span>
6. <span data-ttu-id="f002f-129">Välj den omräkningstal som du skapade tidigare i fältet för Fredlighet Bill typ.</span><span class="sxs-lookup"><span data-stu-id="f002f-129">In the Freight bill type field, select the freight bill type that you created earlier.</span></span>
7. <span data-ttu-id="f002f-130">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="f002f-130">Close the page.</span></span>

## <a name="set-up-the-audit-master"></a><span data-ttu-id="f002f-131">Ställ in revisionsmallen</span><span class="sxs-lookup"><span data-stu-id="f002f-131">Set up the audit master</span></span>
1. <span data-ttu-id="f002f-132">Gå till Transporthantering > Inställningar > Fraktavstämning > Granskningsmall.</span><span class="sxs-lookup"><span data-stu-id="f002f-132">Go to Transportation management > Setup > Freight reconciliation > Audit master.</span></span>
    * <span data-ttu-id="f002f-133">Revisionsmallen anger toleransgränserna för automatisk fraktavstämning.</span><span class="sxs-lookup"><span data-stu-id="f002f-133">The audit master defines the tolerance limits for automatic freight reconciliation.</span></span> <span data-ttu-id="f002f-134">Den anger hur mycket penningbeloppen på frakträkningen och transportföretag kan skilja sig åt och ändå medge avstämning.</span><span class="sxs-lookup"><span data-stu-id="f002f-134">It specifies by how much the monetary amounts on the freight bill and the carrier invoice can differ and still allow reconciliation to occur.</span></span> <span data-ttu-id="f002f-135">Den definierar även hur du hanterar avvikelser.</span><span class="sxs-lookup"><span data-stu-id="f002f-135">It also defines how to handle discrepancies.</span></span>  
2. <span data-ttu-id="f002f-136">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="f002f-136">Click New.</span></span>
3. <span data-ttu-id="f002f-137">Skriv in ett värde i fältet Audit master ID.</span><span class="sxs-lookup"><span data-stu-id="f002f-137">In the Audit master ID field, type a value.</span></span>
4. <span data-ttu-id="f002f-138">Markera samma transportföretag som tidigare i fältet Shipping carrier.</span><span class="sxs-lookup"><span data-stu-id="f002f-138">In the Shipping carrier  field, select the same shipping carrier as you did earlier.</span></span>
5. <span data-ttu-id="f002f-139">Välj den omräkningstal som du skapade tidigare i fältet för Fredlighet Bill typ.</span><span class="sxs-lookup"><span data-stu-id="f002f-139">In the Freight bill type field, select the freight bill type that you created earlier.</span></span>
6. <span data-ttu-id="f002f-140">Expandera avsnittet Tolerance.</span><span class="sxs-lookup"><span data-stu-id="f002f-140">Expand the Tolerance section.</span></span>
7. <span data-ttu-id="f002f-141">Ange ett värde i fältet Minimum tolerance level.</span><span class="sxs-lookup"><span data-stu-id="f002f-141">In the Minimum tolerance level field, enter a number.</span></span>
8. <span data-ttu-id="f002f-142">Ange ett värde i fältet Maximum tolerance level.</span><span class="sxs-lookup"><span data-stu-id="f002f-142">In the Maximum tolerance level field, enter a number.</span></span>
9. <span data-ttu-id="f002f-143">Expandera avsnittet Result.</span><span class="sxs-lookup"><span data-stu-id="f002f-143">Expand the Result section.</span></span>
10. <span data-ttu-id="f002f-144">Ange eller välj ett värde i fältet Overpayment reason code.</span><span class="sxs-lookup"><span data-stu-id="f002f-144">In the Overpayment reason code field, enter or select a value.</span></span>
    * <span data-ttu-id="f002f-145">Om penningbeloppen skiljer sig åt på frakträkningen och transportföretag, anger koderna för över- och återbetalningsskyldig de konton som skillnaden bör registreras på, så länge skillnaden är inom toleransnivåerna.</span><span class="sxs-lookup"><span data-stu-id="f002f-145">If the monetary amounts differ on the freight bill and the carrier invoice, the overpayment and underpayment reason codes specify the accounts that the difference should be registered on, as long as the difference is within the tolerance levels.</span></span>  
11. <span data-ttu-id="f002f-146">Ange eller välj ett värde i fältet Underpayment reason code.</span><span class="sxs-lookup"><span data-stu-id="f002f-146">In the Underpayment reason code field, enter or select a value.</span></span>
12. <span data-ttu-id="f002f-147">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="f002f-147">Close the page.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]