---
title: Policyer för lagerarbete – översikt
description: Policyer för lagerställearbete styr om lagerställearbete skapas av lagerprocesser i produktionen, baserat på arbetsordertyp, lagerställe och produkt.
author: johanhoffmann
manager: AnnBe
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSWorkPolicy
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 196561
ms.assetid: cbf48ec6-1836-48d5-ad66-a9b534af1786
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.openlocfilehash: 7476cf797685feb4c50e3cefef4c53ca37b82dff
ms.sourcegitcommit: 2460d0da812c45fce67a061386db52e0ae46b0f3
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/30/2019
ms.locfileid: "2251418"
---
# <a name="warehouse-work-policies-overview"></a><span data-ttu-id="23e64-103">Policyer för lagerarbete – översikt</span><span class="sxs-lookup"><span data-stu-id="23e64-103">Warehouse work policies overview</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="23e64-104">Policyer för lagerställearbete styr om lagerställearbete skapas av lagerprocesser i produktionen, baserat på arbetsordertyp, lagerställe och produkt.</span><span class="sxs-lookup"><span data-stu-id="23e64-104">Warehouse work policies control whether warehouse work is created by warehouse processes in manufacturing, based on work order type, inventory location, and product.</span></span>

<span data-ttu-id="23e64-105">Denna arbetspolicy styr huruvida arbetsuppgifter på lagerstället skapas för lagerställeprocesser inom tillverkningen.</span><span class="sxs-lookup"><span data-stu-id="23e64-105">This work policy controls whether warehouse work is created for warehouse processes in manufacturing.</span></span> <span data-ttu-id="23e64-106">Du kan ställa in arbetspolicyn genom att använda en kombination av **arbetsordertyper**, en **lagerplats** samt en **produkt**</span><span class="sxs-lookup"><span data-stu-id="23e64-106">You can set up the work policy by using a combination of **work order types**, an **inventory location**, and a **product**.</span></span> <span data-ttu-id="23e64-107">Exempelvis rapporteras produkt L0101 som färdig till utleveransplats 001.</span><span class="sxs-lookup"><span data-stu-id="23e64-107">For example, product L0101 is reported as finished to output location 001.</span></span> <span data-ttu-id="23e64-108">Den färdiga varan förbrukas senare i en annan produktionsorder på utleveransplats 001.</span><span class="sxs-lookup"><span data-stu-id="23e64-108">The finished good is later consumed in another production order at output location 001.</span></span> <span data-ttu-id="23e64-109">I det här fallet kan du ställa in en arbetspolicy för att förhindra arbete för inlagring av färdiga varor skapas när du rapporterar produkt L0101 som färdig till utleveransplats 001.</span><span class="sxs-lookup"><span data-stu-id="23e64-109">In this case, you can set up a work policy to prevent the work for finished goods put-away from being created when you report product L0101 as finished to output location 001.</span></span> <span data-ttu-id="23e64-110">Arbetspolicyn är en enskild enhet som kan beskrivas genom följande information:</span><span class="sxs-lookup"><span data-stu-id="23e64-110">The work policy is an individual entity that can be described through the following information:</span></span>

-   <span data-ttu-id="23e64-111">**Arbetspolicynamn**(den unika identifieraren för arbetspolicyn)</span><span class="sxs-lookup"><span data-stu-id="23e64-111">**Work policy name** (the unique identifier of the work policy)</span></span>
-   <span data-ttu-id="23e64-112">**Arbetsordertyper** och **Metod för skapande av arbetsuppgift**</span><span class="sxs-lookup"><span data-stu-id="23e64-112">**Work order types** and **Work creation method**</span></span>
-   <span data-ttu-id="23e64-113">**Lagerplatser**</span><span class="sxs-lookup"><span data-stu-id="23e64-113">**Inventory locations**</span></span>
-   <span data-ttu-id="23e64-114">**Produkter**</span><span class="sxs-lookup"><span data-stu-id="23e64-114">**Products**</span></span>

## <a name="work-order-types"></a><span data-ttu-id="23e64-115">Typer av arbetsorder</span><span class="sxs-lookup"><span data-stu-id="23e64-115">Work order types</span></span>
<span data-ttu-id="23e64-116">Du kan välja bland följande arbetsuppgifter:</span><span class="sxs-lookup"><span data-stu-id="23e64-116">You can select the following work order types:</span></span>

-   <span data-ttu-id="23e64-117">Plats för slutförda varor</span><span class="sxs-lookup"><span data-stu-id="23e64-117">Finished goods put away</span></span>
-   <span data-ttu-id="23e64-118">Plats för samprodukt och biprodukt</span><span class="sxs-lookup"><span data-stu-id="23e64-118">Co-product and by-product put away</span></span>
-   <span data-ttu-id="23e64-119">Råmaterialhämtning</span><span class="sxs-lookup"><span data-stu-id="23e64-119">Raw material picking</span></span>

<span data-ttu-id="23e64-120">Fältet **Metod för att skapa arbete** har värdet **Aldrig**.</span><span class="sxs-lookup"><span data-stu-id="23e64-120">The **Work creation method** field has the value **Never**.</span></span> <span data-ttu-id="23e64-121">Det här värdet anger att arbetspolicyn förhindrar att arbetsuppgifter på lagerstället skapas för vald arbetsordertyp.</span><span class="sxs-lookup"><span data-stu-id="23e64-121">This value indicates that the work policy will prevent warehouse work from being created for the selected work order type.</span></span>

## <a name="inventory-locations"></a><span data-ttu-id="23e64-122">Lagerplatser</span><span class="sxs-lookup"><span data-stu-id="23e64-122">Inventory locations</span></span>
<span data-ttu-id="23e64-123">Du kan välja en plats som arbetspolicyn gäller för.</span><span class="sxs-lookup"><span data-stu-id="23e64-123">You can select a location that the work policy applies to.</span></span> <span data-ttu-id="23e64-124">Om ingen plats finns associerad med en arbetspolicy, gäller inte arbetspolicyn för några processer.</span><span class="sxs-lookup"><span data-stu-id="23e64-124">If no location is associated with a work policy, the work policy doesn’t apply to any processes.</span></span> <span data-ttu-id="23e64-125">På sidan **Locations** kan du också välja eller avbryta valet av arbetspolicy för en viss plats.</span><span class="sxs-lookup"><span data-stu-id="23e64-125">On the **Locations** page, you can also select or cancel the selection of the work policy for a specific location.</span></span>

## <a name="products"></a><span data-ttu-id="23e64-126">Produkter</span><span class="sxs-lookup"><span data-stu-id="23e64-126">Products</span></span>
<span data-ttu-id="23e64-127">Du kan välja en produkt som arbetspolicyn gäller för.</span><span class="sxs-lookup"><span data-stu-id="23e64-127">You can select a product that the work policy applies to.</span></span> <span data-ttu-id="23e64-128">Du kan använda arbetspolicyn antingen på alla produkter eller på utvalda produkter.</span><span class="sxs-lookup"><span data-stu-id="23e64-128">You can apply the work policy to either all products or selected products.</span></span>

## <a name="example"></a><span data-ttu-id="23e64-129">Exempel</span><span class="sxs-lookup"><span data-stu-id="23e64-129">Example</span></span>
<span data-ttu-id="23e64-130">I följande exempel finns det två produktionsorder, PRD-001 och PRD-00*2*.</span><span class="sxs-lookup"><span data-stu-id="23e64-130">In the following example, there are two production orders, PRD-001 and PRD-00*2*.</span></span> <span data-ttu-id="23e64-131">Produktionsorder PRD-001 har en åtgärd med namnet **Sammansättning**, där produkten SC1 rapporterats som färdig till plats O1.</span><span class="sxs-lookup"><span data-stu-id="23e64-131">Production order PRD-001 has an operation that is named **Assembly**, where product SC1 is being reported as finished to location O1.</span></span> <span data-ttu-id="23e64-132">Produktionsorder PRD-002 har en åtgärd med namnet **Painting** och förbrukar produkten SC1 från platsen O1.</span><span class="sxs-lookup"><span data-stu-id="23e64-132">Production order PRD-002 has an operation that is named **Painting** and consumes product SC1 from location O1.</span></span> <span data-ttu-id="23e64-133">Produktionsorder PRD-002 förbrukar även råmaterial RM1 från platsen O1.</span><span class="sxs-lookup"><span data-stu-id="23e64-133">Production order PRD-002 also consumes raw material RM1 from location O1.</span></span> <span data-ttu-id="23e64-134">RM1 lagras på lagerställeplats och BULK-001 och plockas till platsen O1 av lagerställets arbetsuppgift för plockning av råmaterial.</span><span class="sxs-lookup"><span data-stu-id="23e64-134">RM1 is stored in warehouse location BULK-001 and will be picked to location O1 by warehouse work for raw material picking.</span></span> <span data-ttu-id="23e64-135">Plockningsarbetet skapas när produktion PRD-002 frisläpps.</span><span class="sxs-lookup"><span data-stu-id="23e64-135">The picking work is generated when production PRD-002 is released.</span></span> 

<span data-ttu-id="23e64-136">[![Policyer för lagerarbete](./media/warehouse-work-policies.png)](./media/warehouse-work-policies.png)</span><span class="sxs-lookup"><span data-stu-id="23e64-136">[![Warehouse work policies](./media/warehouse-work-policies.png)](./media/warehouse-work-policies.png)</span></span> 

<span data-ttu-id="23e64-137">När du planerar att konfigurera en arbetspolicy för detta scenario på lagerstället, bör du beakta följande information:</span><span class="sxs-lookup"><span data-stu-id="23e64-137">When you plan to configure a warehouse work policy for this scenario, you should consider the following information:</span></span>

-   <span data-ttu-id="23e64-138">Arbetsuppgifter för förvaring av färdiga varor på lagerställen krävs inte när du rapporterar produkten SC1 som färdig från produktionsorder PRD-001 till platsen O1.</span><span class="sxs-lookup"><span data-stu-id="23e64-138">Warehouse work for finished goods put-away isn’t required when you report product SC1 as finished from production order PRD-001 to location O1.</span></span> <span data-ttu-id="23e64-139">Detta eftersom åtgärden **Painting** för produktionsorder PRD-002 förbrukar SC1 på samma plats.</span><span class="sxs-lookup"><span data-stu-id="23e64-139">This is because the **Painting** operation for production order PRD-002 consumes SC1 at the same location.</span></span>
-   <span data-ttu-id="23e64-140">Lagerställearbete för plockning av råmaterial krävs för att flytta råmaterialet RM1 från lagerplats BULK-001 till plats O1.</span><span class="sxs-lookup"><span data-stu-id="23e64-140">Warehouse work for raw material picking is required in order to move raw material RM1 from warehouse location BULK-001 to location O1.</span></span>

<span data-ttu-id="23e64-141">Här följer ett exempel på en arbetspolicy som du kan ställa in, baserat på dessa överväganden.</span><span class="sxs-lookup"><span data-stu-id="23e64-141">Here is an example of the work policy that you can set up, based on these considerations.</span></span>


|                                       |                                       |
|---------------------------------------|---------------------------------------|
| <span data-ttu-id="23e64-142"><strong>Namn på arbetspolicy</strong></span><span class="sxs-lookup"><span data-stu-id="23e64-142"><strong>Work policy name</strong></span></span><br> | <span data-ttu-id="23e64-143"><strong>Typer av arbetsorder</strong></span><span class="sxs-lookup"><span data-stu-id="23e64-143"><strong>Work order types</strong></span></span><br> |
|         <span data-ttu-id="23e64-144">Lagringsfri 01</span><span class="sxs-lookup"><span data-stu-id="23e64-144">No put away 01     \`</span></span>          |     <span data-ttu-id="23e64-145">- Lagring av färdig vara</span><span class="sxs-lookup"><span data-stu-id="23e64-145">- Finished good put away</span></span><br>      |
|                                       |    <span data-ttu-id="23e64-146"><strong>Platser</strong></span><span class="sxs-lookup"><span data-stu-id="23e64-146"><strong>Locations</strong></span></span><br>     |
|                                       |                 <span data-ttu-id="23e64-147">- O1</span><span class="sxs-lookup"><span data-stu-id="23e64-147">- O1</span></span>                  |
|                                       |    <span data-ttu-id="23e64-148"><strong>Produkter</strong></span><span class="sxs-lookup"><span data-stu-id="23e64-148"><strong>Products</strong></span></span> <br>     |
|                                       |                 <span data-ttu-id="23e64-149">- SC1</span><span class="sxs-lookup"><span data-stu-id="23e64-149">- SC1</span></span>                 |

<span data-ttu-id="23e64-150">Följande procedurer innehåller steg-för-steg-instruktioner om hur du ställer in arbetspolicyn för lagerstället för detta scenario.</span><span class="sxs-lookup"><span data-stu-id="23e64-150">The following procedures provide step-by-step instructions about how to set up the warehouse work policy for this scenario.</span></span> <span data-ttu-id="23e64-151">En exempelinställning som visar hur du rapporterar en produktionsorder som slutförd till en plats som inte kontrolleras via registreringsskylt beskrivs också.</span><span class="sxs-lookup"><span data-stu-id="23e64-151">A sample setup showing how to report a production order as finished to a location that isn’t license plate–controlled is also described.</span></span>

## <a name="set-up-a-warehouse-work-policy"></a><span data-ttu-id="23e64-152">Konfigurera en policy för lagerarbete</span><span class="sxs-lookup"><span data-stu-id="23e64-152">Set up a warehouse work policy</span></span>
<span data-ttu-id="23e64-153">Lagerställeprocesser inkluderar inte alltid lagerarbete.</span><span class="sxs-lookup"><span data-stu-id="23e64-153">Warehouse processes don’t always include warehouse work.</span></span> <span data-ttu-id="23e64-154">Genom att definiera en arbetspolicy kan du förhindra skapande av arbete för råmaterialhämtning och inlagring av färdiga varor för en uppsättning av produkter på specifika platser.</span><span class="sxs-lookup"><span data-stu-id="23e64-154">By defining a work policy, you can prevent the creation of work for raw material picking and put-away of finished goods for a set of products at specific locations.</span></span> <span data-ttu-id="23e64-155">Demonstrationsdataföretaget USMF har använts för att skapa denna procedur.</span><span class="sxs-lookup"><span data-stu-id="23e64-155">The USMF demo data company was used to create this procedure.</span></span> 

<span data-ttu-id="23e64-156">STEG (21)</span><span class="sxs-lookup"><span data-stu-id="23e64-156">STEPS (21)</span></span>

|     |                                                                            |
|-----|----------------------------------------------------------------------------|
| <span data-ttu-id="23e64-157">1.</span><span class="sxs-lookup"><span data-stu-id="23e64-157">1.</span></span>  | <span data-ttu-id="23e64-158">Gå till Lagerstyrning &gt; Inställningar &gt; Arbete &gt; Arbetspolicyer.</span><span class="sxs-lookup"><span data-stu-id="23e64-158">Go to Warehouse management &gt; Setup &gt; Work &gt; Work policies.</span></span>        |
| <span data-ttu-id="23e64-159">2.</span><span class="sxs-lookup"><span data-stu-id="23e64-159">2.</span></span>  | <span data-ttu-id="23e64-160">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="23e64-160">Click New.</span></span>                                                                 |
| <span data-ttu-id="23e64-161">3.</span><span class="sxs-lookup"><span data-stu-id="23e64-161">3.</span></span>  | <span data-ttu-id="23e64-162">Skriv in "Inget inlagrat arbete" i fältet Namn på arbetspolicy.</span><span class="sxs-lookup"><span data-stu-id="23e64-162">In the Work policy name field, type 'No put-away work'.</span></span>                    |
| <span data-ttu-id="23e64-163">4.</span><span class="sxs-lookup"><span data-stu-id="23e64-163">4.</span></span>  | <span data-ttu-id="23e64-164">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="23e64-164">Click Save.</span></span>                                                                |
| <span data-ttu-id="23e64-165">5.</span><span class="sxs-lookup"><span data-stu-id="23e64-165">5.</span></span>  | <span data-ttu-id="23e64-166">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="23e64-166">Click Add.</span></span>                                                                 |
| <span data-ttu-id="23e64-167">6.</span><span class="sxs-lookup"><span data-stu-id="23e64-167">6.</span></span>  | <span data-ttu-id="23e64-168">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="23e64-168">In the list, mark the selected row.</span></span>                                        |
| <span data-ttu-id="23e64-169">7.</span><span class="sxs-lookup"><span data-stu-id="23e64-169">7.</span></span>  | <span data-ttu-id="23e64-170">Skriv in "Plats för slutförda varor" i fältet Typ av arbetsorder.</span><span class="sxs-lookup"><span data-stu-id="23e64-170">In the Work order type field, select 'Finished goods put away'.</span></span>            |
| <span data-ttu-id="23e64-171">8.</span><span class="sxs-lookup"><span data-stu-id="23e64-171">8.</span></span>  | <span data-ttu-id="23e64-172">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="23e64-172">Click Add.</span></span>                                                                 |
| <span data-ttu-id="23e64-173">9.</span><span class="sxs-lookup"><span data-stu-id="23e64-173">9.</span></span>  | <span data-ttu-id="23e64-174">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="23e64-174">In the list, mark the selected row.</span></span>                                        |
| <span data-ttu-id="23e64-175">10.</span><span class="sxs-lookup"><span data-stu-id="23e64-175">10.</span></span> | <span data-ttu-id="23e64-176">Välj ”Plats för samprodukt och biprodukt” i fältet Typ arbetsorder.</span><span class="sxs-lookup"><span data-stu-id="23e64-176">In the Work order type field, select 'Co-product and by-product put away'.</span></span> |
| <span data-ttu-id="23e64-177">11.</span><span class="sxs-lookup"><span data-stu-id="23e64-177">11.</span></span> | <span data-ttu-id="23e64-178">Visa avsnittet Lagerplatser.</span><span class="sxs-lookup"><span data-stu-id="23e64-178">Expand the Inventory locations section.</span></span>                                    |
| <span data-ttu-id="23e64-179">12.</span><span class="sxs-lookup"><span data-stu-id="23e64-179">12.</span></span> | <span data-ttu-id="23e64-180">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="23e64-180">Click Add.</span></span>                                                                 |
| <span data-ttu-id="23e64-181">13.</span><span class="sxs-lookup"><span data-stu-id="23e64-181">13.</span></span> | <span data-ttu-id="23e64-182">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="23e64-182">In the list, mark the selected row.</span></span>                                        |
| <span data-ttu-id="23e64-183">14.</span><span class="sxs-lookup"><span data-stu-id="23e64-183">14.</span></span> | <span data-ttu-id="23e64-184">Ange ”51" i lagerställets lista.</span><span class="sxs-lookup"><span data-stu-id="23e64-184">In the Warehouse list, enter '51'.</span></span>                                         |
| <span data-ttu-id="23e64-185">15.</span><span class="sxs-lookup"><span data-stu-id="23e64-185">15.</span></span> | <span data-ttu-id="23e64-186">Ange eller välj "001" i fältet Plats.</span><span class="sxs-lookup"><span data-stu-id="23e64-186">In the Location field, enter or select '001'.</span></span>                              |
| <span data-ttu-id="23e64-187">16.</span><span class="sxs-lookup"><span data-stu-id="23e64-187">16.</span></span> | <span data-ttu-id="23e64-188">Expandera avsnittet Produkter.</span><span class="sxs-lookup"><span data-stu-id="23e64-188">Expand the Products section.</span></span>                                               |
| <span data-ttu-id="23e64-189">17.</span><span class="sxs-lookup"><span data-stu-id="23e64-189">17.</span></span> | <span data-ttu-id="23e64-190">Välj "Markerad" i fältet Produktval.</span><span class="sxs-lookup"><span data-stu-id="23e64-190">In the Product selection field, select 'Selected'.</span></span>                         |
| <span data-ttu-id="23e64-191">18.</span><span class="sxs-lookup"><span data-stu-id="23e64-191">18.</span></span> | <span data-ttu-id="23e64-192">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="23e64-192">Click Add.</span></span>                                                                 |
| <span data-ttu-id="23e64-193">19.</span><span class="sxs-lookup"><span data-stu-id="23e64-193">19.</span></span> | <span data-ttu-id="23e64-194">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="23e64-194">In the list, mark the selected row.</span></span>                                        |
| <span data-ttu-id="23e64-195">20.</span><span class="sxs-lookup"><span data-stu-id="23e64-195">20.</span></span> | <span data-ttu-id="23e64-196">Ange eller välj "L0101" i fältet Artikelnummer.</span><span class="sxs-lookup"><span data-stu-id="23e64-196">In the Item number field, enter or select 'L0101'.</span></span>                         |
| <span data-ttu-id="23e64-197">21.</span><span class="sxs-lookup"><span data-stu-id="23e64-197">21.</span></span> | <span data-ttu-id="23e64-198">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="23e64-198">Click Save.</span></span>                                                                |

## <a name="report-a-production-order-as-finished-to-a-location-that-isnt-license-platecontrolled"></a><span data-ttu-id="23e64-199">Rapportera en produktionsorder som slutförd till en plats som inte kontrolleras via registreringsskylt</span><span class="sxs-lookup"><span data-stu-id="23e64-199">Report a production order as finished to a location that isn’t license plate–controlled</span></span>
<span data-ttu-id="23e64-200">Denna procedur visar ett exempel på rapportering som slutförd till en plats som inte kontrolleras via registreringsskylt.</span><span class="sxs-lookup"><span data-stu-id="23e64-200">This procedure shows an example of reporting as finished to a location that isn't license plate–controlled.</span></span> <span data-ttu-id="23e64-201">En tillämplig arbetspolicy är förutsättningen är den här uppgiften.</span><span class="sxs-lookup"><span data-stu-id="23e64-201">An applicable work policy is the prerequisite for this task.</span></span> <span data-ttu-id="23e64-202">Föregående procedur anger arbetspolicyns konfiguration.</span><span class="sxs-lookup"><span data-stu-id="23e64-202">The previous procedure shows the setup of the work policy.</span></span> 

<span data-ttu-id="23e64-203">STEG (25)</span><span class="sxs-lookup"><span data-stu-id="23e64-203">STEPS (25)</span></span>

<table>
<tbody>
<tr>
<td colspan="3"><span data-ttu-id="23e64-204"><strong>Deluppgift: Ställ in en utleveransplats.</strong></span><span class="sxs-lookup"><span data-stu-id="23e64-204"><strong>Sub-task: Set up an output location.</strong></span></span></td>
</tr>
<tr>
<td></td>
<td>1.</td>
<td><span data-ttu-id="23e64-205">Gå till Organisationsadministration &gt; Resurser &gt; Resursgrupper.</span><span class="sxs-lookup"><span data-stu-id="23e64-205">Go to Organization administration &gt; Resources &gt; Resource groups.</span></span></td>
</tr>
<tr>
<td></td>
<td>2.</td>
<td><span data-ttu-id="23e64-206">Välj resursgrupp 5102 i listan.</span><span class="sxs-lookup"><span data-stu-id="23e64-206">In the list, select resource group &#39;5102&#39;.</span></span></td>
</tr>
<tr>
<td></td>
<td>3.</td>
<td><span data-ttu-id="23e64-207">Klicka på Redigera.</span><span class="sxs-lookup"><span data-stu-id="23e64-207">Click Edit.</span></span></td>
</tr>
<tr>
<td></td>
<td>4.</td>
<td><span data-ttu-id="23e64-208">Ange 51 i fältet Utleveranslagerställe.</span><span class="sxs-lookup"><span data-stu-id="23e64-208">In the Output warehouse field, enter &#39;51&#39;.</span></span></td>
</tr>
<tr>
<td></td>
<td>5.</td>
<td><span data-ttu-id="23e64-209">Ange 001 fältet Utleveransplats.</span><span class="sxs-lookup"><span data-stu-id="23e64-209">In the Output location field, enter &#39;001&#39;.</span></span></td>
</tr>
<tr>
<td></td>
<td>6.</td>
<td><span data-ttu-id="23e64-210">Plats 001 är en ej ID-nummerstyrd plats.</span><span class="sxs-lookup"><span data-stu-id="23e64-210">Location 001 isn&#39;t a license plate–controlled location.</span></span> <span data-ttu-id="23e64-211">Du kan ställa in en plats för ej ID-nummertyrd utleveransplats bara om en lämplig arbetspolicy finns för platsen.</span><span class="sxs-lookup"><span data-stu-id="23e64-211">You can set up a non–license plate output location only if an applicable work policy exists for the location.</span></span></td>
</tr>
<tr>
<td colspan="3"><span data-ttu-id="23e64-212"><strong>Deluppgift: Skapa en produktionsorder och rapportera den som färdig.</strong></span><span class="sxs-lookup"><span data-stu-id="23e64-212"><strong>Sub-task: Create a production order and report it as finished.</strong></span></span></td>
</tr>
<tr>
<td></td>
<td>1.</td>
<td><span data-ttu-id="23e64-213">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="23e64-213">Close the page.</span></span></td>
</tr>
<tr>
<td></td>
<td>2.</td>
<td><span data-ttu-id="23e64-214">Gå till Produktionskontroll &gt; Produktionsorder &gt; Alla produktionsorder.</span><span class="sxs-lookup"><span data-stu-id="23e64-214">Go to Production control &gt; Production orders &gt; All production orders.</span></span></td>
</tr>
<tr>
<td></td>
<td>3.</td>
<td><span data-ttu-id="23e64-215">Klicka på Ny produktionsorder.</span><span class="sxs-lookup"><span data-stu-id="23e64-215">Click New production order.</span></span></td>
</tr>
<tr>
<td></td>
<td>4.</td>
<td><span data-ttu-id="23e64-216">Ange L0101 i fältet Artikelnummer.</span><span class="sxs-lookup"><span data-stu-id="23e64-216">In the Item number field, enter &#39;L0101&#39;.</span></span></td>
</tr>
<tr>
<td></td>
<td>5.</td>
<td><span data-ttu-id="23e64-217">Klicka på Skapa.</span><span class="sxs-lookup"><span data-stu-id="23e64-217">Click Create.</span></span></td>
</tr>
<tr>
<td></td>
<td>6.</td>
<td><span data-ttu-id="23e64-218">Klicka på Produktionsorder i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="23e64-218">On the Action Pane, click Production order.</span></span></td>
</tr>
<tr>
<td></td>
<td>7.</td>
<td><span data-ttu-id="23e64-219">Klicka på Uppskattning.</span><span class="sxs-lookup"><span data-stu-id="23e64-219">Click Estimate.</span></span></td>
</tr>
<tr>
<td></td>
<td>8.</td>
<td><span data-ttu-id="23e64-220">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="23e64-220">Click OK.</span></span></td>
</tr>
<tr>
<td></td>
<td>9.</td>
<td><span data-ttu-id="23e64-221">Klicka på Start.</span><span class="sxs-lookup"><span data-stu-id="23e64-221">Click Start.</span></span></td>
</tr>
<tr>
<td></td>
<td>10.</td>
<td><span data-ttu-id="23e64-222">Klicka på fliken Allmänt.</span><span class="sxs-lookup"><span data-stu-id="23e64-222">Click the General tab.</span></span></td>
</tr>
<tr>
<td></td>
<td>11.</td>
<td><span data-ttu-id="23e64-223">Välj Aldrig i fältet Automatisk strukturlisteförbrukning.</span><span class="sxs-lookup"><span data-stu-id="23e64-223">In the Automatic BOM consumption field, select &#39;Never&#39;.</span></span></td>
</tr>
<tr>
<td></td>
<td>12.</td>
<td><span data-ttu-id="23e64-224">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="23e64-224">Click OK.</span></span></td>
</tr>
<tr>
<td></td>
<td>13.</td>
<td><span data-ttu-id="23e64-225">Klicka på Rapportera som färdig.</span><span class="sxs-lookup"><span data-stu-id="23e64-225">Click Report as finished.</span></span></td>
</tr>
<tr>
<td></td>
<td>14.</td>
<td><span data-ttu-id="23e64-226">Klicka på fliken Allmänt.</span><span class="sxs-lookup"><span data-stu-id="23e64-226">Click the General tab.</span></span></td>
</tr>
<tr>
<td></td>
<td>15.</td>
<td><span data-ttu-id="23e64-227">Välj Ja i fältet Godkänn fel.</span><span class="sxs-lookup"><span data-stu-id="23e64-227">Select Yes in the Accept error field.</span></span></td>
</tr>
<tr>
<td></td>
<td>16.</td>
<td><span data-ttu-id="23e64-228">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="23e64-228">Click OK.</span></span></td>
</tr>
<tr>
<td></td>
<td>17.</td>
<td><span data-ttu-id="23e64-229">Klicka på Lagerställe i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="23e64-229">On the Action Pane, click Warehouse.</span></span></td>
</tr>
<tr>
<td></td>
<td>18.</td>
<td><span data-ttu-id="23e64-230">Klicka på Information om arbete.</span><span class="sxs-lookup"><span data-stu-id="23e64-230">Click Work details.</span></span></td>
</tr>
<tr>
<td></td>
<td>19.</td>
<td><span data-ttu-id="23e64-231">När tillverkningsordern rapporterades som färdig, genererades inget arbete för plats.</span><span class="sxs-lookup"><span data-stu-id="23e64-231">When the production order was reported as finished, no work was generated for put-away.</span></span> <span data-ttu-id="23e64-232">Detta inträffar, eftersom en arbetspolicy definieras som hindrar arbete från att genereras när produkten L0101 rapporterats som färdig till plats 001.</span><span class="sxs-lookup"><span data-stu-id="23e64-232">This occurs because a work policy is defined that prevents work from being generated when product L0101 is reported as finished to location 001.</span></span></td>
</tr>
</tbody>
</table>



