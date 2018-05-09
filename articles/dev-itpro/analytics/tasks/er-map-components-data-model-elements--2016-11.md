--- 
title: "Mappa komponenter för det skapade formatet till datamodellelement för elektronisk rapportering (ER)"
description: "I följande procedur beskrivs hur en användare med roll som systemadministratör eller utvecklare elektronisk rapportering kan mappa datamodellelement med komponenter i den skapade elektroniska rapporteringskonfigurationen (ER), som definierar ett elektroniskt dokumentformat för affärsdomänen för betalningar."
author: NickSelin
manager: AnnBe
ms.date: 02/27/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 921e00051e8d9647f16b1e29dfbda8821f28c7e5
ms.contentlocale: sv-se
ms.lasthandoff: 05/08/2018

---
# <a name="map-components-of-the-created-format-to-data-model-elements-for-electronic-reporting-er"></a><span data-ttu-id="245e8-103">Mappa komponenter för det skapade formatet till datamodellelement för elektronisk rapportering (ER)</span><span class="sxs-lookup"><span data-stu-id="245e8-103">Map components of the created format to data model elements for electronic reporting (ER)</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="245e8-104">I följande procedur beskrivs hur en användare med roll som systemadministratör eller utvecklare elektronisk rapportering kan mappa datamodellelement med komponenter i den skapade elektroniska rapporteringskonfigurationen (ER), som definierar ett elektroniskt dokumentformat för affärsdomänen för betalningar.</span><span class="sxs-lookup"><span data-stu-id="245e8-104">The following procedure shows how a user in either the System administrator or Electronic reporting developer role can map data model elements to components of the created Electronic reporting (ER) configuration, which defines an electronic document format for the payments business domain.</span></span> <span data-ttu-id="245e8-105">Detta format används senare för att generera elektroniska dokument för att bearbeta betalningar.</span><span class="sxs-lookup"><span data-stu-id="245e8-105">This format will be used later to generate electronic documents for processing payments.</span></span> <span data-ttu-id="245e8-106">I det här exemplet skapar du en formatkonfiguration för exempelföretaget "Litware, Inc.".</span><span class="sxs-lookup"><span data-stu-id="245e8-106">In this example, you will create a format configuration for the sample company, ‘Litware, Inc.’.</span></span> <span data-ttu-id="245e8-107">Dessa steg kan utföras i alla företag, eftersom ER-konfigurationer delas mellan alla företag.</span><span class="sxs-lookup"><span data-stu-id="245e8-107">These steps can be performed in any company as ER configurations are shared for all companies.</span></span> <span data-ttu-id="245e8-108">För att slutföra dessa steg måste du först slutföra stegen i uppgiftsguiden "Skapa en formatkonfiguration".</span><span class="sxs-lookup"><span data-stu-id="245e8-108">To complete these steps, you must first complete the steps in the “Create a format configuration” task guide.</span></span>


## <a name="select-a-format-configuration"></a><span data-ttu-id="245e8-109">Välj en formatkonfiguration</span><span class="sxs-lookup"><span data-stu-id="245e8-109">Select a format configuration</span></span>
1. <span data-ttu-id="245e8-110">Gå till Organisationsadministration > Arbetsytor > Elektronisk rapportering.</span><span class="sxs-lookup"><span data-stu-id="245e8-110">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="245e8-111">Klicka på Reporting configurations.</span><span class="sxs-lookup"><span data-stu-id="245e8-111">Click Reporting configurations.</span></span>
3. <span data-ttu-id="245e8-112">Visa "Betalningar (förenklad modell)" i trädet.</span><span class="sxs-lookup"><span data-stu-id="245e8-112">In the tree, expand 'Payments (simplified model)'.</span></span>
4. <span data-ttu-id="245e8-113">Välj "Betalningar (förenklad modell))\BACS (UK fiktivt)" i trädet.</span><span class="sxs-lookup"><span data-stu-id="245e8-113">In the tree, select 'Payments (simplified model)\BACS (UK fictitious)'.</span></span>
5. <span data-ttu-id="245e8-114">Klicka på Designer.</span><span class="sxs-lookup"><span data-stu-id="245e8-114">Click Designer.</span></span>

## <a name="map-format-components-to-data-model-elements"></a><span data-ttu-id="245e8-115">Mappa formatkomponenter till datamodellelement</span><span class="sxs-lookup"><span data-stu-id="245e8-115">Map format components to data model elements</span></span>
1. <span data-ttu-id="245e8-116">Klicka på Expandera/Komprimera.</span><span class="sxs-lookup"><span data-stu-id="245e8-116">Click Expand/collapse.</span></span>
2. <span data-ttu-id="245e8-117">Klicka på fliken Mappning.</span><span class="sxs-lookup"><span data-stu-id="245e8-117">Click the Mapping tab.</span></span>
3. <span data-ttu-id="245e8-118">Expandera "modell" i trädet.</span><span class="sxs-lookup"><span data-stu-id="245e8-118">In the tree, expand 'model'.</span></span>
4. <span data-ttu-id="245e8-119">Välj "Xml\Message\ProcessingDate\DateTime" i trädet.</span><span class="sxs-lookup"><span data-stu-id="245e8-119">In the tree, select 'Xml\Message\ProcessingDate\DateTime'.</span></span>
5. <span data-ttu-id="245e8-120">Välj "model\ProcessingDateTime" i trädet.</span><span class="sxs-lookup"><span data-stu-id="245e8-120">In the tree, select 'model\ProcessingDateTime'.</span></span>
6. <span data-ttu-id="245e8-121">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="245e8-121">Click Bind.</span></span>
7. <span data-ttu-id="245e8-122">Välj "Xml\Message\MessageId\String" i trädet.</span><span class="sxs-lookup"><span data-stu-id="245e8-122">In the tree, select 'Xml\Message\MessageId\String'.</span></span>
8. <span data-ttu-id="245e8-123">Välj "model\MessageIdentification" i trädet.</span><span class="sxs-lookup"><span data-stu-id="245e8-123">In the tree, select 'model\MessageIdentification'.</span></span>
9. <span data-ttu-id="245e8-124">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="245e8-124">Click Bind.</span></span>
10. <span data-ttu-id="245e8-125">Expandera "modell\Betalningar" i trädet.</span><span class="sxs-lookup"><span data-stu-id="245e8-125">In the tree, expand 'model\Payments'.</span></span>
11. <span data-ttu-id="245e8-126">Välj "Xml\Message\Payments\Item\Amount\String" i trädet.</span><span class="sxs-lookup"><span data-stu-id="245e8-126">In the tree, select 'Xml\Message\Payments\Item\Amount\String'.</span></span>
12. <span data-ttu-id="245e8-127">Välj "model\Payments\InstructedAmount" i trädet.</span><span class="sxs-lookup"><span data-stu-id="245e8-127">In the tree, select 'model\Payments\InstructedAmount'.</span></span>
13. <span data-ttu-id="245e8-128">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="245e8-128">Click Bind.</span></span>
14. <span data-ttu-id="245e8-129">Välj "Xml\Message\Payments\Item\TransDate\DateTime" i trädet.</span><span class="sxs-lookup"><span data-stu-id="245e8-129">In the tree, select 'Xml\Message\Payments\Item\TransDate\DateTime'.</span></span>
15. <span data-ttu-id="245e8-130">Välj "model\Payments\TransactionDate" i trädet.</span><span class="sxs-lookup"><span data-stu-id="245e8-130">In the tree, select 'model\Payments\TransactionDate'.</span></span>
16. <span data-ttu-id="245e8-131">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="245e8-131">Click Bind.</span></span>
17. <span data-ttu-id="245e8-132">Välj "Xml\Message\Payments\Item\Description\String" i trädet.</span><span class="sxs-lookup"><span data-stu-id="245e8-132">In the tree, select 'Xml\Message\Payments\Item\Description\String'.</span></span>
18. <span data-ttu-id="245e8-133">Välj "modell\Betalningar\Beskrivning" i trädet.</span><span class="sxs-lookup"><span data-stu-id="245e8-133">In the tree, select 'model\Payments\Description'.</span></span>
19. <span data-ttu-id="245e8-134">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="245e8-134">Click Bind.</span></span>
20. <span data-ttu-id="245e8-135">Välj "Xml\Message\Payments\Item\Currency\String" i trädet.</span><span class="sxs-lookup"><span data-stu-id="245e8-135">In the tree, select 'Xml\Message\Payments\Item\Currency\String'.</span></span>
21. <span data-ttu-id="245e8-136">Välj "modell\Betalningar\Valuta" i trädet.</span><span class="sxs-lookup"><span data-stu-id="245e8-136">In the tree, select 'model\Payments\Currency'.</span></span>
22. <span data-ttu-id="245e8-137">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="245e8-137">Click Bind.</span></span>
23. <span data-ttu-id="245e8-138">Välj "Xml\Message\Payments\Item\Id" i trädet.</span><span class="sxs-lookup"><span data-stu-id="245e8-138">In the tree, select 'Xml\Message\Payments\Item\Id'.</span></span>
24. <span data-ttu-id="245e8-139">Välj "model\Payments\End2EndID" i trädet.</span><span class="sxs-lookup"><span data-stu-id="245e8-139">In the tree, select 'model\Payments\End2EndID'.</span></span>
25. <span data-ttu-id="245e8-140">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="245e8-140">Click Bind.</span></span>
26. <span data-ttu-id="245e8-141">Expandera "modell\Betalningar\Betalningsmottagare" i trädet.</span><span class="sxs-lookup"><span data-stu-id="245e8-141">In the tree, expand 'model\Payments\Creditor'.</span></span>
27. <span data-ttu-id="245e8-142">Expandera "modell\Betalningar\Betalningsmottagare\Konto" i trädet.</span><span class="sxs-lookup"><span data-stu-id="245e8-142">In the tree, expand 'model\Payments\Creditor\Account'.</span></span>
28. <span data-ttu-id="245e8-143">Expandera "modell\Betalningar\Betalningsmottagare\Agent" i trädet.</span><span class="sxs-lookup"><span data-stu-id="245e8-143">In the tree, expand 'model\Payments\Creditor\Agent'.</span></span>
29. <span data-ttu-id="245e8-144">Välj "Xml\Message\Payments\Item\Vendor\Name\String" i trädet.</span><span class="sxs-lookup"><span data-stu-id="245e8-144">In the tree, select 'Xml\Message\Payments\Item\Vendor\Name\String'.</span></span>
30. <span data-ttu-id="245e8-145">Välj "modell\Betalningar\Betalningsmottagare\Namn" i trädet.</span><span class="sxs-lookup"><span data-stu-id="245e8-145">In the tree, select 'model\Payments\Creditor\Name'.</span></span>
31. <span data-ttu-id="245e8-146">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="245e8-146">Click Bind.</span></span>
32. <span data-ttu-id="245e8-147">Välj "Xml\Message\Payments\Item\Vendor\Bank\RoutingNumber\String" i trädet.</span><span class="sxs-lookup"><span data-stu-id="245e8-147">In the tree, select 'Xml\Message\Payments\Item\Vendor\Bank\RoutingNumber\String'.</span></span>
33. <span data-ttu-id="245e8-148">Välj "model\Payments\Creditor\Agent\RoutingNumber" i trädet.</span><span class="sxs-lookup"><span data-stu-id="245e8-148">In the tree, select 'model\Payments\Creditor\Agent\RoutingNumber'.</span></span>
34. <span data-ttu-id="245e8-149">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="245e8-149">Click Bind.</span></span>
35. <span data-ttu-id="245e8-150">Välj "Xml\Message\Payments\Item\Vendor\Bank\AccountNumber\String" i trädet.</span><span class="sxs-lookup"><span data-stu-id="245e8-150">In the tree, select 'Xml\Message\Payments\Item\Vendor\Bank\AccountNumber\String'.</span></span>
36. <span data-ttu-id="245e8-151">Välj "modell\Betalningar\Betalningsmottagare\Konto\Nummer" i trädet.</span><span class="sxs-lookup"><span data-stu-id="245e8-151">In the tree, select 'model\Payments\Creditor\Account\Number'.</span></span>
37. <span data-ttu-id="245e8-152">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="245e8-152">Click Bind.</span></span>
38. <span data-ttu-id="245e8-153">Välj "Xml\Message\Payments\Item\Payer\Name\String" i trädet.</span><span class="sxs-lookup"><span data-stu-id="245e8-153">In the tree, select 'Xml\Message\Payments\Item\Payer\Name\String'.</span></span>
39. <span data-ttu-id="245e8-154">Expandera "modell\Betalningar\Betalare" i trädet.</span><span class="sxs-lookup"><span data-stu-id="245e8-154">In the tree, expand 'model\Payments\Debtor'.</span></span>
40. <span data-ttu-id="245e8-155">Expandera "modell\Betalningar\Betalare\Konto" i trädet.</span><span class="sxs-lookup"><span data-stu-id="245e8-155">In the tree, expand 'model\Payments\Debtor\Account'.</span></span>
41. <span data-ttu-id="245e8-156">Expandera "modell\Betalningar\Betalare\Agent" i trädet.</span><span class="sxs-lookup"><span data-stu-id="245e8-156">In the tree, expand 'model\Payments\Debtor\Agent'.</span></span>
42. <span data-ttu-id="245e8-157">Välj "modell\Betalningar\Betalare\Namn" i trädet.</span><span class="sxs-lookup"><span data-stu-id="245e8-157">In the tree, select 'model\Payments\Debtor\Name'.</span></span>
43. <span data-ttu-id="245e8-158">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="245e8-158">Click Bind.</span></span>
44. <span data-ttu-id="245e8-159">Välj "Xml\Message\Payments\Item\Payer\Bank\RoutingNumber\String" i trädet.</span><span class="sxs-lookup"><span data-stu-id="245e8-159">In the tree, select 'Xml\Message\Payments\Item\Payer\Bank\RoutingNumber\String'.</span></span>
45. <span data-ttu-id="245e8-160">Välj "model\Payments\Debtor\Agent\RoutingNumber" i trädet.</span><span class="sxs-lookup"><span data-stu-id="245e8-160">In the tree, select 'model\Payments\Debtor\Agent\RoutingNumber'.</span></span>
46. <span data-ttu-id="245e8-161">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="245e8-161">Click Bind.</span></span>
47. <span data-ttu-id="245e8-162">Välj "Xml\Message\Payments\Item\Payer\Bank\AccountNumber\String" i trädet.</span><span class="sxs-lookup"><span data-stu-id="245e8-162">In the tree, select 'Xml\Message\Payments\Item\Payer\Bank\AccountNumber\String'.</span></span>
48. <span data-ttu-id="245e8-163">Välj "modell\Betalningar\Betalare\Konto\Nummer" i trädet.</span><span class="sxs-lookup"><span data-stu-id="245e8-163">In the tree, select 'model\Payments\Debtor\Account\Number'.</span></span>
49. <span data-ttu-id="245e8-164">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="245e8-164">Click Bind.</span></span>
50. <span data-ttu-id="245e8-165">Välj "Xml\Message\Payments\Item" i trädet.</span><span class="sxs-lookup"><span data-stu-id="245e8-165">In the tree, select 'Xml\Message\Payments\Item'.</span></span>
51. <span data-ttu-id="245e8-166">Välj "modell\Betalningar" i trädet.</span><span class="sxs-lookup"><span data-stu-id="245e8-166">In the tree, select 'model\Payments'.</span></span>
52. <span data-ttu-id="245e8-167">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="245e8-167">Click Bind.</span></span>
53. <span data-ttu-id="245e8-168">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="245e8-168">Click Save.</span></span>

## <a name="validate-format-mapping"></a><span data-ttu-id="245e8-169">Validera formatmappning</span><span class="sxs-lookup"><span data-stu-id="245e8-169">Validate format mapping</span></span>
1. <span data-ttu-id="245e8-170">Klicka på Validera.</span><span class="sxs-lookup"><span data-stu-id="245e8-170">Click Validate.</span></span>
    * <span data-ttu-id="245e8-171">Bekräfta den nya mappningen för att säkerställa att alla bindningar är korrekta.</span><span class="sxs-lookup"><span data-stu-id="245e8-171">Validate the new mapping to ensure that all bindings are okay.</span></span>  
2. <span data-ttu-id="245e8-172">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="245e8-172">Close the page.</span></span>

## <a name="change-status-of-the-current-version-of-format-configuration"></a><span data-ttu-id="245e8-173">Ändra status för den aktuella versionen av formatkonfigurationen</span><span class="sxs-lookup"><span data-stu-id="245e8-173">Change status of the current version of format configuration</span></span>
    * <span data-ttu-id="245e8-174">I följande steg ändrar du status för formatkonfigurationen från Utkast till Slutförd för att göra den tillgänglig för genereringen av betalningsdokument.</span><span class="sxs-lookup"><span data-stu-id="245e8-174">In the next steps, you’ll change the status of the format configuration from Draft to Completed to make it available for payment document generation.</span></span>  
1. <span data-ttu-id="245e8-175">Klicka på Ändra status.</span><span class="sxs-lookup"><span data-stu-id="245e8-175">Click Change status.</span></span>
2. <span data-ttu-id="245e8-176">Klicka på Slutför.</span><span class="sxs-lookup"><span data-stu-id="245e8-176">Click Complete.</span></span>
3. <span data-ttu-id="245e8-177">Ange ett värde i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="245e8-177">In the Description field, type a value.</span></span>
    * <span data-ttu-id="245e8-178">Till exempel "Version 1".</span><span class="sxs-lookup"><span data-stu-id="245e8-178">For example, 'version 1'.</span></span>  
4. <span data-ttu-id="245e8-179">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="245e8-179">Click OK.</span></span>
5. <span data-ttu-id="245e8-180">Välj den slutförda versionen av den aktuella versionen.</span><span class="sxs-lookup"><span data-stu-id="245e8-180">Select completed version of the current configuration.</span></span>
    * <span data-ttu-id="245e8-181">Observera att konfigurationen sparas som slutförd version 1.1: version 1 av formatet, vilket baseras på version 1 av datamodellen.</span><span class="sxs-lookup"><span data-stu-id="245e8-181">Note that the configuration is saved as completed version 1.1: version 1 of the format based on the version 1 of the data model.</span></span>  

## <a name="define-effective-date-for-completed-version-of-format"></a><span data-ttu-id="245e8-182">Definiera giltighetsdatumet för slutförd version av formatet</span><span class="sxs-lookup"><span data-stu-id="245e8-182">Define effective date for completed version of format</span></span>
    * <span data-ttu-id="245e8-183">Varje formatversion kan konfigureras som tillgänglig för användning med start från ett visst datum.</span><span class="sxs-lookup"><span data-stu-id="245e8-183">Each format version can be configured as available for usage starting from a certain date.</span></span> <span data-ttu-id="245e8-184">När mer än en formatversion är aktiv på att visst datum, kommer det senaste formatet (utifrån versionsnumret) att väljas för användning.</span><span class="sxs-lookup"><span data-stu-id="245e8-184">When more than one format version is active on a certain date, the latest format (based on version number) will be selected for usage.</span></span> <span data-ttu-id="245e8-185">Värdet för sessionsdatumet används för ett korrekt versionsurval.</span><span class="sxs-lookup"><span data-stu-id="245e8-185">The session date value is used for proper version selection.</span></span>  

## <a name="restrict-access-to-created-format-from-companies"></a><span data-ttu-id="245e8-186">Begränsa åtkomsten till det skapade formatet från företag</span><span class="sxs-lookup"><span data-stu-id="245e8-186">Restrict access to created format from companies</span></span>
1. <span data-ttu-id="245e8-187">Visa eller dölj avsnittet om ISO-koder för land/region.</span><span class="sxs-lookup"><span data-stu-id="245e8-187">Expand the ISO Country/region codes section.</span></span>
    * <span data-ttu-id="245e8-188">Varje formatåtkomst kan begränsas genom att identifiera särskilda länder/regioner som ett format kan tillämpas på.</span><span class="sxs-lookup"><span data-stu-id="245e8-188">Each format access can be restricted by identifying particular countries/regions in which a format is applicable.</span></span> <span data-ttu-id="245e8-189">När listan över länder/regioner för ett visst format är tomt, kan formatet användas i alla företag.</span><span class="sxs-lookup"><span data-stu-id="245e8-189">When the list of countries/regions for particular format is empty, this format can be used in any company.</span></span> <span data-ttu-id="245e8-190">När vissa ISO-koder för land/region infogas i listan över länder/regioner kan formatet endast användas i företag vars primära adress ligger i landet/regionen.</span><span class="sxs-lookup"><span data-stu-id="245e8-190">When some ISO country/region codes are inserted in the list of countries/regions, the format can only be use in companies if the primary address is in the country/region.</span></span>  


