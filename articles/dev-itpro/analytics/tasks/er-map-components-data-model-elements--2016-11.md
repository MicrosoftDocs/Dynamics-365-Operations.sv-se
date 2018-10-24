--- 
title: "ER Mappa komponenter för det skapade till datamodellelement (november 2016)"
description: "I följande procedur beskrivs hur en användare med roll som systemadministratör eller utvecklare elektronisk rapportering kan mappa datamodellelement med komponenter i den skapade elektroniska rapporteringskonfigurationen (ER), som definierar ett elektroniskt dokumentformat för affärsdomänen för betalningar."
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ERWorkspace, ERSolutionTable, EROperationDesigner
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0312b8cfadd45f8e59225e9daba78b9e216cff51
ms.openlocfilehash: a24ef0e091379f14a163a6385be988143a1ec608
ms.contentlocale: sv-se
ms.lasthandoff: 09/14/2018

---
# <a name="er-map-components-of-the-created-format-to-data-model-elements-november-2016"></a><span data-ttu-id="6fe70-103">ER Mappa komponenter för det skapade till datamodellelement (november 2016)</span><span class="sxs-lookup"><span data-stu-id="6fe70-103">ER Map components of the created format to data model elements (November 2016)</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="6fe70-104">I följande procedur beskrivs hur en användare med roll som systemadministratör eller utvecklare elektronisk rapportering kan mappa datamodellelement med komponenter i den skapade elektroniska rapporteringskonfigurationen (ER), som definierar ett elektroniskt dokumentformat för affärsdomänen för betalningar.</span><span class="sxs-lookup"><span data-stu-id="6fe70-104">The following procedure shows how a user in either the System administrator or Electronic reporting developer role can map data model elements to components of the created Electronic reporting (ER) configuration, which defines an electronic document format for the payments business domain.</span></span> <span data-ttu-id="6fe70-105">Detta format används senare för att skapa elektroniska dokument för att bearbeta betalningar.</span><span class="sxs-lookup"><span data-stu-id="6fe70-105">This format will be used later to generate electronic documents for processing payments.</span></span> <span data-ttu-id="6fe70-106">I det här exemplet skapar du en formatkonfiguration för exempelföretaget "Litware, Inc.".</span><span class="sxs-lookup"><span data-stu-id="6fe70-106">In this example, you will create a format configuration for the sample company, ‘Litware, Inc.’.</span></span> <span data-ttu-id="6fe70-107">Dessa steg kan utföras i alla företag, eftersom ER-konfigurationer delas mellan alla företag.</span><span class="sxs-lookup"><span data-stu-id="6fe70-107">These steps can be performed in any company as ER configurations are shared for all companies.</span></span> <span data-ttu-id="6fe70-108">För att slutföra dessa steg måste du först slutföra stegen i uppgiftsguiden "Skapa en formatkonfiguration".</span><span class="sxs-lookup"><span data-stu-id="6fe70-108">To complete these steps, you must first complete the steps in the “Create a format configuration” task guide.</span></span>


## <a name="select-a-format-configuration"></a><span data-ttu-id="6fe70-109">Välj en formatkonfiguration</span><span class="sxs-lookup"><span data-stu-id="6fe70-109">Select a format configuration</span></span>
1. <span data-ttu-id="6fe70-110">Gå till Organisationsadministration > Arbetsytor > Elektronisk rapportering.</span><span class="sxs-lookup"><span data-stu-id="6fe70-110">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="6fe70-111">Klicka på Reporting configurations.</span><span class="sxs-lookup"><span data-stu-id="6fe70-111">Click Reporting configurations.</span></span>
3. <span data-ttu-id="6fe70-112">Visa "Betalningar (förenklad modell)" i trädet.</span><span class="sxs-lookup"><span data-stu-id="6fe70-112">In the tree, expand 'Payments (simplified model)'.</span></span>
4. <span data-ttu-id="6fe70-113">Välj "Betalningar (förenklad modell)\BACS (UK fiktivt)" i trädet.</span><span class="sxs-lookup"><span data-stu-id="6fe70-113">In the tree, select 'Payments (simplified model)\BACS (UK fictitious)'.</span></span>
5. <span data-ttu-id="6fe70-114">Klicka på Designer.</span><span class="sxs-lookup"><span data-stu-id="6fe70-114">Click Designer.</span></span>

## <a name="map-format-components-to-data-model-elements"></a><span data-ttu-id="6fe70-115">Mappa formatkomponenter till datamodellelement</span><span class="sxs-lookup"><span data-stu-id="6fe70-115">Map format components to data model elements</span></span>
1. <span data-ttu-id="6fe70-116">Klicka på Expandera/Komprimera.</span><span class="sxs-lookup"><span data-stu-id="6fe70-116">Click Expand/collapse.</span></span>
2. <span data-ttu-id="6fe70-117">Klicka på fliken Mappning.</span><span class="sxs-lookup"><span data-stu-id="6fe70-117">Click the Mapping tab.</span></span>
3. <span data-ttu-id="6fe70-118">Expandera "modell" i trädet.</span><span class="sxs-lookup"><span data-stu-id="6fe70-118">In the tree, expand 'model'.</span></span>
4. <span data-ttu-id="6fe70-119">Välj "Xml\Message\ProcessingDate\DateTime" i trädet.</span><span class="sxs-lookup"><span data-stu-id="6fe70-119">In the tree, select 'Xml\Message\ProcessingDate\DateTime'.</span></span>
5. <span data-ttu-id="6fe70-120">Välj "model\ProcessingDateTime" i trädet.</span><span class="sxs-lookup"><span data-stu-id="6fe70-120">In the tree, select 'model\ProcessingDateTime'.</span></span>
6. <span data-ttu-id="6fe70-121">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="6fe70-121">Click Bind.</span></span>
7. <span data-ttu-id="6fe70-122">Välj "Xml\Message\MessageId\String" i trädet.</span><span class="sxs-lookup"><span data-stu-id="6fe70-122">In the tree, select 'Xml\Message\MessageId\String'.</span></span>
8. <span data-ttu-id="6fe70-123">Välj "model\MessageIdentification" i trädet.</span><span class="sxs-lookup"><span data-stu-id="6fe70-123">In the tree, select 'model\MessageIdentification'.</span></span>
9. <span data-ttu-id="6fe70-124">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="6fe70-124">Click Bind.</span></span>
10. <span data-ttu-id="6fe70-125">Expandera "modell\Betalningar" i trädet.</span><span class="sxs-lookup"><span data-stu-id="6fe70-125">In the tree, expand 'model\Payments'.</span></span>
11. <span data-ttu-id="6fe70-126">Välj "Xml\Message\Payments\Item\Amount\String" i trädet.</span><span class="sxs-lookup"><span data-stu-id="6fe70-126">In the tree, select 'Xml\Message\Payments\Item\Amount\String'.</span></span>
12. <span data-ttu-id="6fe70-127">Välj "model\Payments\InstructedAmount" i trädet.</span><span class="sxs-lookup"><span data-stu-id="6fe70-127">In the tree, select 'model\Payments\InstructedAmount'.</span></span>
13. <span data-ttu-id="6fe70-128">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="6fe70-128">Click Bind.</span></span>
14. <span data-ttu-id="6fe70-129">Välj "Xml\Message\Payments\Item\TransDate\DateTime" i trädet.</span><span class="sxs-lookup"><span data-stu-id="6fe70-129">In the tree, select 'Xml\Message\Payments\Item\TransDate\DateTime'.</span></span>
15. <span data-ttu-id="6fe70-130">Välj "model\Payments\TransactionDate" i trädet.</span><span class="sxs-lookup"><span data-stu-id="6fe70-130">In the tree, select 'model\Payments\TransactionDate'.</span></span>
16. <span data-ttu-id="6fe70-131">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="6fe70-131">Click Bind.</span></span>
17. <span data-ttu-id="6fe70-132">Välj "Xml\Message\Payments\Item\Description\String" i trädet.</span><span class="sxs-lookup"><span data-stu-id="6fe70-132">In the tree, select 'Xml\Message\Payments\Item\Description\String'.</span></span>
18. <span data-ttu-id="6fe70-133">Välj "modell\Betalningar\Beskrivning" i trädet.</span><span class="sxs-lookup"><span data-stu-id="6fe70-133">In the tree, select 'model\Payments\Description'.</span></span>
19. <span data-ttu-id="6fe70-134">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="6fe70-134">Click Bind.</span></span>
20. <span data-ttu-id="6fe70-135">Välj "Xml\Message\Payments\Item\Currency\String" i trädet.</span><span class="sxs-lookup"><span data-stu-id="6fe70-135">In the tree, select 'Xml\Message\Payments\Item\Currency\String'.</span></span>
21. <span data-ttu-id="6fe70-136">Välj "modell\Betalningar\Valuta" i trädet.</span><span class="sxs-lookup"><span data-stu-id="6fe70-136">In the tree, select 'model\Payments\Currency'.</span></span>
22. <span data-ttu-id="6fe70-137">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="6fe70-137">Click Bind.</span></span>
23. <span data-ttu-id="6fe70-138">Välj "Xml\Message\Payments\Item\Id" i trädet.</span><span class="sxs-lookup"><span data-stu-id="6fe70-138">In the tree, select 'Xml\Message\Payments\Item\Id'.</span></span>
24. <span data-ttu-id="6fe70-139">Välj "model\Payments\End2EndID" i trädet.</span><span class="sxs-lookup"><span data-stu-id="6fe70-139">In the tree, select 'model\Payments\End2EndID'.</span></span>
25. <span data-ttu-id="6fe70-140">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="6fe70-140">Click Bind.</span></span>
26. <span data-ttu-id="6fe70-141">Expandera "modell\Betalningar\Betalningsmottagare" i trädet.</span><span class="sxs-lookup"><span data-stu-id="6fe70-141">In the tree, expand 'model\Payments\Creditor'.</span></span>
27. <span data-ttu-id="6fe70-142">Expandera "modell\Betalningar\Betalningsmottagare\Konto" i trädet.</span><span class="sxs-lookup"><span data-stu-id="6fe70-142">In the tree, expand 'model\Payments\Creditor\Account'.</span></span>
28. <span data-ttu-id="6fe70-143">Expandera "modell\Betalningar\Betalningsmottagare\Agent" i trädet.</span><span class="sxs-lookup"><span data-stu-id="6fe70-143">In the tree, expand 'model\Payments\Creditor\Agent'.</span></span>
29. <span data-ttu-id="6fe70-144">Välj "Xml\Message\Payments\Item\Vendor\Name\String" i trädet.</span><span class="sxs-lookup"><span data-stu-id="6fe70-144">In the tree, select 'Xml\Message\Payments\Item\Vendor\Name\String'.</span></span>
30. <span data-ttu-id="6fe70-145">Välj "modell\Betalningar\Betalningsmottagare\Namn" i trädet.</span><span class="sxs-lookup"><span data-stu-id="6fe70-145">In the tree, select 'model\Payments\Creditor\Name'.</span></span>
31. <span data-ttu-id="6fe70-146">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="6fe70-146">Click Bind.</span></span>
32. <span data-ttu-id="6fe70-147">Välj "Xml\Message\Payments\Item\Vendor\Bank\RoutingNumber\String" i trädet.</span><span class="sxs-lookup"><span data-stu-id="6fe70-147">In the tree, select 'Xml\Message\Payments\Item\Vendor\Bank\RoutingNumber\String'.</span></span>
33. <span data-ttu-id="6fe70-148">Välj "model\Payments\Creditor\Agent\RoutingNumber" i trädet.</span><span class="sxs-lookup"><span data-stu-id="6fe70-148">In the tree, select 'model\Payments\Creditor\Agent\RoutingNumber'.</span></span>
34. <span data-ttu-id="6fe70-149">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="6fe70-149">Click Bind.</span></span>
35. <span data-ttu-id="6fe70-150">Välj "Xml\Message\Payments\Item\Vendor\Bank\AccountNumber\String" i trädet.</span><span class="sxs-lookup"><span data-stu-id="6fe70-150">In the tree, select 'Xml\Message\Payments\Item\Vendor\Bank\AccountNumber\String'.</span></span>
36. <span data-ttu-id="6fe70-151">Välj "modell\Betalningar\Betalningsmottagare\Konto\Nummer" i trädet.</span><span class="sxs-lookup"><span data-stu-id="6fe70-151">In the tree, select 'model\Payments\Creditor\Account\Number'.</span></span>
37. <span data-ttu-id="6fe70-152">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="6fe70-152">Click Bind.</span></span>
38. <span data-ttu-id="6fe70-153">Välj "Xml\Message\Payments\Item\Payer\Name\String" i trädet.</span><span class="sxs-lookup"><span data-stu-id="6fe70-153">In the tree, select 'Xml\Message\Payments\Item\Payer\Name\String'.</span></span>
39. <span data-ttu-id="6fe70-154">Expandera "modell\Betalningar\Betalare" i trädet.</span><span class="sxs-lookup"><span data-stu-id="6fe70-154">In the tree, expand 'model\Payments\Debtor'.</span></span>
40. <span data-ttu-id="6fe70-155">Expandera "modell\Betalningar\Betalare\Konto" i trädet.</span><span class="sxs-lookup"><span data-stu-id="6fe70-155">In the tree, expand 'model\Payments\Debtor\Account'.</span></span>
41. <span data-ttu-id="6fe70-156">Expandera "modell\Betalningar\Betalare\Agent" i trädet.</span><span class="sxs-lookup"><span data-stu-id="6fe70-156">In the tree, expand 'model\Payments\Debtor\Agent'.</span></span>
42. <span data-ttu-id="6fe70-157">Välj "modell\Betalningar\Betalare\Namn" i trädet.</span><span class="sxs-lookup"><span data-stu-id="6fe70-157">In the tree, select 'model\Payments\Debtor\Name'.</span></span>
43. <span data-ttu-id="6fe70-158">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="6fe70-158">Click Bind.</span></span>
44. <span data-ttu-id="6fe70-159">Välj "Xml\Message\Payments\Item\Payer\Bank\RoutingNumber\String" i trädet.</span><span class="sxs-lookup"><span data-stu-id="6fe70-159">In the tree, select 'Xml\Message\Payments\Item\Payer\Bank\RoutingNumber\String'.</span></span>
45. <span data-ttu-id="6fe70-160">Välj "model\Payments\Debtor\Agent\RoutingNumber" i trädet.</span><span class="sxs-lookup"><span data-stu-id="6fe70-160">In the tree, select 'model\Payments\Debtor\Agent\RoutingNumber'.</span></span>
46. <span data-ttu-id="6fe70-161">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="6fe70-161">Click Bind.</span></span>
47. <span data-ttu-id="6fe70-162">Välj "Xml\Message\Payments\Item\Payer\Bank\AccountNumber\String" i trädet.</span><span class="sxs-lookup"><span data-stu-id="6fe70-162">In the tree, select 'Xml\Message\Payments\Item\Payer\Bank\AccountNumber\String'.</span></span>
48. <span data-ttu-id="6fe70-163">Välj "modell\Betalningar\Betalare\Konto\Nummer" i trädet.</span><span class="sxs-lookup"><span data-stu-id="6fe70-163">In the tree, select 'model\Payments\Debtor\Account\Number'.</span></span>
49. <span data-ttu-id="6fe70-164">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="6fe70-164">Click Bind.</span></span>
50. <span data-ttu-id="6fe70-165">Välj "Xml\Message\Payments\Item" i trädet.</span><span class="sxs-lookup"><span data-stu-id="6fe70-165">In the tree, select 'Xml\Message\Payments\Item'.</span></span>
51. <span data-ttu-id="6fe70-166">Välj "modell\Betalningar" i trädet.</span><span class="sxs-lookup"><span data-stu-id="6fe70-166">In the tree, select 'model\Payments'.</span></span>
52. <span data-ttu-id="6fe70-167">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="6fe70-167">Click Bind.</span></span>
53. <span data-ttu-id="6fe70-168">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="6fe70-168">Click Save.</span></span>

## <a name="validate-format-mapping"></a><span data-ttu-id="6fe70-169">Validera formatmappning</span><span class="sxs-lookup"><span data-stu-id="6fe70-169">Validate format mapping</span></span>
1. <span data-ttu-id="6fe70-170">Klicka på Validera.</span><span class="sxs-lookup"><span data-stu-id="6fe70-170">Click Validate.</span></span>
    * <span data-ttu-id="6fe70-171">Bekräfta den nya mappningen för att säkerställa att alla bindningar är korrekta.</span><span class="sxs-lookup"><span data-stu-id="6fe70-171">Validate the new mapping to ensure that all bindings are okay.</span></span>  
2. <span data-ttu-id="6fe70-172">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="6fe70-172">Close the page.</span></span>

## <a name="change-status-of-the-current-version-of-format-configuration"></a><span data-ttu-id="6fe70-173">Ändra status för den aktuella versionen av formatkonfigurationen</span><span class="sxs-lookup"><span data-stu-id="6fe70-173">Change status of the current version of format configuration</span></span>
    * <span data-ttu-id="6fe70-174">I följande steg ändrar du status för formatkonfigurationen från Utkast till Slutförd för att göra den tillgänglig för genereringen av betalningsdokument.</span><span class="sxs-lookup"><span data-stu-id="6fe70-174">In the next steps, you’ll change the status of the format configuration from Draft to Completed to make it available for payment document generation.</span></span>  
1. <span data-ttu-id="6fe70-175">Klicka på Ändra status.</span><span class="sxs-lookup"><span data-stu-id="6fe70-175">Click Change status.</span></span>
2. <span data-ttu-id="6fe70-176">Klicka på Slutför.</span><span class="sxs-lookup"><span data-stu-id="6fe70-176">Click Complete.</span></span>
3. <span data-ttu-id="6fe70-177">Ange ett värde i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="6fe70-177">In the Description field, type a value.</span></span>
    * <span data-ttu-id="6fe70-178">Till exempel "Version 1".</span><span class="sxs-lookup"><span data-stu-id="6fe70-178">For example, 'version 1'.</span></span>  
4. <span data-ttu-id="6fe70-179">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="6fe70-179">Click OK.</span></span>
5. <span data-ttu-id="6fe70-180">Välj den slutförda versionen av den aktuella versionen.</span><span class="sxs-lookup"><span data-stu-id="6fe70-180">Select completed version of the current configuration.</span></span>
    * <span data-ttu-id="6fe70-181">Observera att konfigurationen sparas som slutförd version 1.1: version 1 av formatet, vilket baseras på version 1 av datamodellen.</span><span class="sxs-lookup"><span data-stu-id="6fe70-181">Note that the configuration is saved as completed version 1.1: version 1 of the format based on the version 1 of the data model.</span></span>  

## <a name="define-effective-date-for-completed-version-of-format"></a><span data-ttu-id="6fe70-182">Definiera giltighetsdatumet för slutförd version av formatet</span><span class="sxs-lookup"><span data-stu-id="6fe70-182">Define effective date for completed version of format</span></span>
    * <span data-ttu-id="6fe70-183">Varje formatversion kan konfigureras som tillgänglig för användning med start från ett visst datum.</span><span class="sxs-lookup"><span data-stu-id="6fe70-183">Each format version can be configured as available for usage starting from a certain date.</span></span> <span data-ttu-id="6fe70-184">När mer än en formatversion är aktiv på att visst datum, kommer det senaste formatet (utifrån versionsnumret) att väljas för användning.</span><span class="sxs-lookup"><span data-stu-id="6fe70-184">When more than one format version is active on a certain date, the latest format (based on version number) will be selected for usage.</span></span> <span data-ttu-id="6fe70-185">Värdet för sessionsdatumet används för ett korrekt versionsurval.</span><span class="sxs-lookup"><span data-stu-id="6fe70-185">The session date value is used for proper version selection.</span></span>  

## <a name="restrict-access-to-created-format-from-companies"></a><span data-ttu-id="6fe70-186">Begränsa åtkomsten till det skapade formatet från företag</span><span class="sxs-lookup"><span data-stu-id="6fe70-186">Restrict access to created format from companies</span></span>
1. <span data-ttu-id="6fe70-187">Visa eller dölj avsnittet om ISO-koder för land/region.</span><span class="sxs-lookup"><span data-stu-id="6fe70-187">Expand the ISO Country/region codes section.</span></span>
    * <span data-ttu-id="6fe70-188">Varje formatåtkomst kan begränsas genom att identifiera särskilda länder/regioner som ett format kan tillämpas på.</span><span class="sxs-lookup"><span data-stu-id="6fe70-188">Each format access can be restricted by identifying particular countries/regions in which a format is applicable.</span></span> <span data-ttu-id="6fe70-189">När listan över länder/regioner för ett visst format är tomt, kan formatet användas i alla företag.</span><span class="sxs-lookup"><span data-stu-id="6fe70-189">When the list of countries/regions for particular format is empty, this format can be used in any company.</span></span> <span data-ttu-id="6fe70-190">När vissa ISO-koder för land/region infogas i listan över länder/regioner kan formatet endast användas i företag vars primära adress ligger i landet/regionen.</span><span class="sxs-lookup"><span data-stu-id="6fe70-190">When some ISO country/region codes are inserted in the list of countries/regions, the format can only be use in companies if the primary address is in the country/region.</span></span>  


