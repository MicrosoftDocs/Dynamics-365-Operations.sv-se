--- 
title: "Utforma konfigurationer för att tolka inkommande dokument för uppdatering av programdata (ER)"
description: "Denna procedur visar hur du utformar ER-konfigurationer (elektronisk rapportering) för att tolka ett inkommande elektroniskt dokument."
author: NickSelin
manager: AnnBe
ms.date: 12/12/2017
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
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 74606b1378e94e8a6945a408520c8b68648970d8
ms.openlocfilehash: 96c9397c6a83d61b679492f66f4aa6661f1f8621
ms.contentlocale: sv-se
ms.lasthandoff: 02/07/2018

---
# <a name="design-configurations-to-parse-incoming-documents-for-application-data-updates-er"></a><span data-ttu-id="a51ba-103">Utforma konfigurationer för att tolka inkommande dokument för uppdatering av programdata (ER)</span><span class="sxs-lookup"><span data-stu-id="a51ba-103">Design configurations to parse incoming documents for application data updates (ER)</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="a51ba-104">Denna procedur visar hur du utformar ER-konfigurationer (elektronisk rapportering) för att tolka ett inkommande elektroniskt dokument.</span><span class="sxs-lookup"><span data-stu-id="a51ba-104">This procedure shows how to design Electronic reporting (ER) configurations to parse an incoming electronic document.</span></span> <span data-ttu-id="a51ba-105">I den här proceduren ska du importera erforderliga ER-konfigurationer som har skapats för exempelföretaget Litware, Inc. och använda dem för att tolka inkommande elektroniska dokument.</span><span class="sxs-lookup"><span data-stu-id="a51ba-105">In this procedure, you will import the required ER configurations that have been created for the sample company, Litware, Inc. and use them for parsing incoming electronic documents.</span></span> <span data-ttu-id="a51ba-106">För att slutföra stegen i den här proceduren måste du först slutföra stegen i proceduren "ER Skapa en konfigurationsleverantör och markera den som aktiv."</span><span class="sxs-lookup"><span data-stu-id="a51ba-106">To complete the steps in this procedure, you must first complete the procedure, “ER Create a configuration provider and mark it as active.”</span></span>

<span data-ttu-id="a51ba-107">Den här proceduren har skapats för användare med rollen Systemadministratör eller Utvecklare för elektronisk rapportering.</span><span class="sxs-lookup"><span data-stu-id="a51ba-107">This procedure is created for users with the assigned role of System administrator or Electronic reporting developer.</span></span> 

<span data-ttu-id="a51ba-108">Stegen kan utföras med hjälp av valfri datauppsättning.</span><span class="sxs-lookup"><span data-stu-id="a51ba-108">These steps can be completed using any dataset.</span></span> <span data-ttu-id="a51ba-109">Innan du börjar ska du hämta och spara filerna som anges i hjälpavsnittet "Tolka inkommande elektroniska dokument och uppdatera programdata" (https://docs.microsoft.com/en-us/dynamics365/unified-operations/dev-itpro/analytics/parse-incoming-documents-update-application-data).</span><span class="sxs-lookup"><span data-stu-id="a51ba-109">Before you begin, download and save the files listed in the topic, “Parse incoming documents to update application data” (https://docs.microsoft.com/en-us/dynamics365/unified-operations/dev-itpro/analytics/parse-incoming-electronic-documents).</span></span> <span data-ttu-id="a51ba-110">Filerna är: EFSTA, model.xml, EFSTA, format.xml, Response1.xml, Response2.xml, Response3.xml, Response4.xml.</span><span class="sxs-lookup"><span data-stu-id="a51ba-110">The files are: EFSTA model.xml, EFSTA format.xml, Response1.xml, Response2.xml, Response3.xml, Response4.xml.</span></span>

1. <span data-ttu-id="a51ba-111">Gå till Organisationsadministration > Arbetsytor > Elektronisk rapportering.</span><span class="sxs-lookup"><span data-stu-id="a51ba-111">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
    * <span data-ttu-id="a51ba-112">Kontrollera att konfigurationsleverantören för exempelföretaget "Litware, Inc." är markerad som aktiv och är tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="a51ba-112">Make sure that the configuration provider for the sample company, Litware, Inc., is available and marked as Active.</span></span> <span data-ttu-id="a51ba-113">Om du inte ser den här konfigurationsleverantören ska du först slutföra stegen i proceduren Skapa en konfigurationsleverantör och välj den som aktiv.</span><span class="sxs-lookup"><span data-stu-id="a51ba-113">If you don’t see this configuration provider, complete the steps in the procedure, “Create a configuration provider and mark it as active”.</span></span>  
2. <span data-ttu-id="a51ba-114">Klicka på Reporting configurations.</span><span class="sxs-lookup"><span data-stu-id="a51ba-114">Click Reporting configurations.</span></span>
    * <span data-ttu-id="a51ba-115">Följande scenario används för att visa möjligheterna med tolkning av inkommande elektroniska dokument i XML-format: ERP-programmet (Dynamics 365 for Finance and Operations) begär data från webbtjänsten (t ex http://efsta.org/ EFSTA) och tolkar inkommande svar för att uppdatera programdata.</span><span class="sxs-lookup"><span data-stu-id="a51ba-115">The following scenario will be used to show the capabilities of parsing incoming electronic documents in XML format: ERP application (Dynamics 365 for Finance and Operations)  requests data from the web service (such as http://efsta.org/ EFSTA fiscal service) and parses the incoming responses to update application data accordingly.</span></span> <span data-ttu-id="a51ba-116">Det mest effektiva sättet att tolka använder ett enkelt ER-format trots att förväntad struktur på inkommande dokument i XML-format är annorlunda.</span><span class="sxs-lookup"><span data-stu-id="a51ba-116">For the most efficient way to parse, a single ER format is used despite the different structure of expected incoming documents in XML format.</span></span>   

## <a name="import-and-review-er-configurations"></a><span data-ttu-id="a51ba-117">Importera och granska ER-konfigurationer</span><span class="sxs-lookup"><span data-stu-id="a51ba-117">Import and review ER configurations</span></span>
<span data-ttu-id="a51ba-118">Importera ER-modellkonfigurationen som innehåller exempeldatamodellen som är utformad för lagring av information om den importerade filen.</span><span class="sxs-lookup"><span data-stu-id="a51ba-118">Import the ER model configuration that contains the sample data model designed to store the details of the incoming file.</span></span>  
1. <span data-ttu-id="a51ba-119">Klicka på Byt.</span><span class="sxs-lookup"><span data-stu-id="a51ba-119">Click Exchange.</span></span>
2. <span data-ttu-id="a51ba-120">Klicka på Läs in från XML-fil.</span><span class="sxs-lookup"><span data-stu-id="a51ba-120">Click Load from XML file.</span></span>
    * <span data-ttu-id="a51ba-121">Klicka på Bläddra och välj filen EFSTA model.xml-</span><span class="sxs-lookup"><span data-stu-id="a51ba-121">Click Browse and select the EFSTA model.xml file.</span></span>  
3. <span data-ttu-id="a51ba-122">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="a51ba-122">Click OK.</span></span>
4. <span data-ttu-id="a51ba-123">Välj "EFSTA-modell" i trädet.</span><span class="sxs-lookup"><span data-stu-id="a51ba-123">In the tree, select 'EFSTA model'.</span></span>
5. <span data-ttu-id="a51ba-124">Klicka på Designer.</span><span class="sxs-lookup"><span data-stu-id="a51ba-124">Click Designer.</span></span>
    * <span data-ttu-id="a51ba-125">Granska strukturen i den importerade datamodellen.</span><span class="sxs-lookup"><span data-stu-id="a51ba-125">Review the structure of the imported data model.</span></span> <span data-ttu-id="a51ba-126">Observera att enumType-uppräkning har definierats till att känna igen följande typer av tjänstesvar: att få bekräftelse om transaktionens sändning, få information om senaste skickade transaktionen och identifiera svarstyper stöds inte.</span><span class="sxs-lookup"><span data-stu-id="a51ba-126">Note that the enumType enumeration is defined to recognize the following types of service responses: to get confirmation about transaction’s submission, to get info about last transaction submitted, and to recognize unsupported response types.</span></span>   
6. <span data-ttu-id="a51ba-127">Expandera "Svar" i trädet.</span><span class="sxs-lookup"><span data-stu-id="a51ba-127">In the tree, expand 'Response'.</span></span>
    * <span data-ttu-id="a51ba-128">Observera att rotobjektet "Svar" definieras om du vill ange vilka data som måste tas från det tjänstesvar som stöds för att uppdatera programdata på samma sätt.</span><span class="sxs-lookup"><span data-stu-id="a51ba-128">Note that the root item ‘Response’ is defined to specify what kind of data must be taken from a supported service response to update application data accordingly.</span></span>   
7. <span data-ttu-id="a51ba-129">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="a51ba-129">Close the page.</span></span>
    * <span data-ttu-id="a51ba-130">Du importerar ER-formatkonfigurationen som anger hur inkommande dokument ska tolkas för att lagra data i ER-datamodell.</span><span class="sxs-lookup"><span data-stu-id="a51ba-130">You will import the ER format configuration that specifies how the incoming documents will be parsed to store data in the ER data model.</span></span>   
8. <span data-ttu-id="a51ba-131">Klicka på Byt.</span><span class="sxs-lookup"><span data-stu-id="a51ba-131">Click Exchange.</span></span>
9. <span data-ttu-id="a51ba-132">Klicka på Läs in från XML-fil.</span><span class="sxs-lookup"><span data-stu-id="a51ba-132">Click Load from XML file.</span></span>
    * <span data-ttu-id="a51ba-133">Klicka på Bläddra och välj filen EFSTA format.xml.</span><span class="sxs-lookup"><span data-stu-id="a51ba-133">Click Browse and select the EFSTA format.xml file.</span></span>  
10. <span data-ttu-id="a51ba-134">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="a51ba-134">Click OK.</span></span>
11. <span data-ttu-id="a51ba-135">Expandera "EFSTA-modell" i trädet.</span><span class="sxs-lookup"><span data-stu-id="a51ba-135">In the tree, expand 'EFSTA model'.</span></span>
12. <span data-ttu-id="a51ba-136">Välj "EFSTA model\EFSTA format" i trädet.</span><span class="sxs-lookup"><span data-stu-id="a51ba-136">In the tree, select 'EFSTA model\EFSTA format'.</span></span>
13. <span data-ttu-id="a51ba-137">Klicka på Designer.</span><span class="sxs-lookup"><span data-stu-id="a51ba-137">Click Designer.</span></span>
14. <span data-ttu-id="a51ba-138">Klicka på Expandera/Komprimera.</span><span class="sxs-lookup"><span data-stu-id="a51ba-138">Click Expand/collapse.</span></span>
    * <span data-ttu-id="a51ba-139">Observera att CASE-formatelementet används som roten och innehåller tre kapslade FILE-element, vilket innebär att formatet har utformats för att analysera inkommande filer i olika format.</span><span class="sxs-lookup"><span data-stu-id="a51ba-139">Note that the CASE format element is used as the root and contains three nested FILE elements, which means that this format has been designed to parse incoming files of several formats.</span></span>  
15. <span data-ttu-id="a51ba-140">Välj "Responses\Transaction completion\TraC" i trädet.</span><span class="sxs-lookup"><span data-stu-id="a51ba-140">In the tree, select 'Responses\Transaction completion\TraC'.</span></span>
    * <span data-ttu-id="a51ba-141">Observera att svaret om den skickade transaktionen startar från rotelementet "TraC".</span><span class="sxs-lookup"><span data-stu-id="a51ba-141">Note that the response about the submitted transaction starts from the ‘TraC’ root element.</span></span>   
16. <span data-ttu-id="a51ba-142">Välj "Responses\Last transaction request\Tra" i trädet.</span><span class="sxs-lookup"><span data-stu-id="a51ba-142">In the tree, select 'Responses\Last transaction request\Tra'.</span></span>
    * <span data-ttu-id="a51ba-143">Observera att svaret om den senast skickade transaktionen startar från rotelementet "Tra".</span><span class="sxs-lookup"><span data-stu-id="a51ba-143">Note that the response about the last submitted transaction starts from the ‘Tra’ root element.</span></span>   
17. <span data-ttu-id="a51ba-144">Välj "Responses\Unexpected response\Text" i trädet.</span><span class="sxs-lookup"><span data-stu-id="a51ba-144">In the tree, select 'Responses\Unexpected response\Text'.</span></span>
    * <span data-ttu-id="a51ba-145">Det tredje FILE-elementet med kapslade TEXT-element har lagts till andra typer av svar som avviker från ovannämnda känna igen.</span><span class="sxs-lookup"><span data-stu-id="a51ba-145">The third FILE element with nested TEXT element has been added to recognize any other types of responses that differ from mentioned above.</span></span>   
18. <span data-ttu-id="a51ba-146">Klicka på Mappa format till modell.</span><span class="sxs-lookup"><span data-stu-id="a51ba-146">Click Map format to model.</span></span>
    * <span data-ttu-id="a51ba-147">Den här modellmappningen innehåller definitionen av dataflöde för att lagra information om parsade inkommande dokument med datamodellens artiklar.</span><span class="sxs-lookup"><span data-stu-id="a51ba-147">This model mapping contains the definition of data flow to store details of the parsed incoming document with using the data model’s items.</span></span>  
19. <span data-ttu-id="a51ba-148">Klicka på Designer.</span><span class="sxs-lookup"><span data-stu-id="a51ba-148">Click Designer.</span></span>
20. <span data-ttu-id="a51ba-149">Expandera format i trädet.</span><span class="sxs-lookup"><span data-stu-id="a51ba-149">In the tree, expand 'format'.</span></span>
21. <span data-ttu-id="a51ba-150">Expandera "format\Responses: Case(Responses)" i trädet.</span><span class="sxs-lookup"><span data-stu-id="a51ba-150">In the tree, expand 'format\Responses: Case(Responses)'.</span></span>
    * <span data-ttu-id="a51ba-151">Granska strukturen i datamodellen "format".</span><span class="sxs-lookup"><span data-stu-id="a51ba-151">Review the structure of the ‘format’ data source.</span></span> <span data-ttu-id="a51ba-152">Observera att alla tre svarstyper erbjuds separat.</span><span class="sxs-lookup"><span data-stu-id="a51ba-152">Note that all three response types are offered separately.</span></span>   
22. <span data-ttu-id="a51ba-153">Välj "format\Responses: Case(Responses)\aType" i trädet.</span><span class="sxs-lookup"><span data-stu-id="a51ba-153">In the tree, select 'format\Responses: Case(Responses)\aType'.</span></span>
    * <span data-ttu-id="a51ba-154">Datakällaartikeln "aType" har lagts för att ange svarstypen och är bunden till modellartikeln "Typ".</span><span class="sxs-lookup"><span data-stu-id="a51ba-154">The data source item ‘aType’ has been added to indicate the response type and is bound to the data model item ‘Type’.</span></span>  
23. <span data-ttu-id="a51ba-155">Klicka på fliken Valideringar.</span><span class="sxs-lookup"><span data-stu-id="a51ba-155">Click the Validations tab.</span></span>
24. <span data-ttu-id="a51ba-156">Välj "Type = format.Responses.aType" i trädet.</span><span class="sxs-lookup"><span data-stu-id="a51ba-156">In the tree, select 'Type = format.Responses.aType'.</span></span>
    * <span data-ttu-id="a51ba-157">Observera att ER-valideringen har konfigurerats för att informera användaren om situationen när svarsstrukturen inte matchar bekräftelsen om transaktionens sändning eller information om senaste skickade transaktionen (svarsfall som inte stöds).</span><span class="sxs-lookup"><span data-stu-id="a51ba-157">Note that the ER validation has been configured to inform the user about the situation when the response structure does not match the confirmation about transaction’s submission or the information about last transaction submitted (unsupported response case).</span></span>   
25. <span data-ttu-id="a51ba-158">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="a51ba-158">Close the page.</span></span>

## <a name="run-model-mapping-of-er-format-configured-for-parsing-incoming-files"></a><span data-ttu-id="a51ba-159">Kör modellmappning för ER-format som konfigurerats för tolkning av inkommande filer</span><span class="sxs-lookup"><span data-stu-id="a51ba-159">Run model mapping of ER format configured for parsing incoming files</span></span>
<span data-ttu-id="a51ba-160">Du kommer att köra den skapade modellmappningen för testning för att se hur det konfigurerade ER-formatet ska tolka inkommande tjänstesvar.</span><span class="sxs-lookup"><span data-stu-id="a51ba-160">You will run the created model mapping for testing purposes to see how the configured ER format will parse incoming service responses.</span></span> <span data-ttu-id="a51ba-161">Proceduren använder olika XML-filer för att simulera olika typer av tjänstesvar.</span><span class="sxs-lookup"><span data-stu-id="a51ba-161">This step uses different XML files to simulate different type of web service responses.</span></span>   
1. <span data-ttu-id="a51ba-162">Öppna filen Response1.xml i en XML-läsare, till exempel en webbläsare.</span><span class="sxs-lookup"><span data-stu-id="a51ba-162">Open the Response1.xml file in an xml reader, such as a web browser.</span></span> <span data-ttu-id="a51ba-163">Observera att den här filen innehåller bekräftelseinformation om avslutade transaktionen (rotelementet är "TraC”).</span><span class="sxs-lookup"><span data-stu-id="a51ba-163">Note that this file contains confirmation details about the completed transaction (‘TraC’ is the root element).</span></span>   
2. <span data-ttu-id="a51ba-164">Klicka på Kör.</span><span class="sxs-lookup"><span data-stu-id="a51ba-164">Click Run.</span></span>
    * <span data-ttu-id="a51ba-165">Klicka på Bläddra och välj filen Response1.xml.</span><span class="sxs-lookup"><span data-stu-id="a51ba-165">Click Browse and select the Response1.xml file.</span></span>  
3. <span data-ttu-id="a51ba-166">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="a51ba-166">Click OK.</span></span>
    * <span data-ttu-id="a51ba-167">Granska den genererade utleveransen.</span><span class="sxs-lookup"><span data-stu-id="a51ba-167">Review the generated output.</span></span> <span data-ttu-id="a51ba-168">Observera att svarstypen har identifieras korrekt och parsad (ERModelEnumDataSourceHandler#EFSTA model#enumType#C betyder transaktion avslutat fall).</span><span class="sxs-lookup"><span data-stu-id="a51ba-168">Note that the response type has been correctly recognized and parsed (ERModelEnumDataSourceHandler#EFSTA model#enumType#C means transaction completion case).</span></span>   
    * <span data-ttu-id="a51ba-169">Öppna filen Response2.xml i en XML-läsaren.</span><span class="sxs-lookup"><span data-stu-id="a51ba-169">Open the Response2.xml file in an XML reader.</span></span> <span data-ttu-id="a51ba-170">Observera att den här filen innehåller information om senaste inskickade transaktionen (rotelementet är "Tra”).</span><span class="sxs-lookup"><span data-stu-id="a51ba-170">Note that this file contains information about last transaction submitted (‘Tra’ is the root element).</span></span>   
4. <span data-ttu-id="a51ba-171">Klicka på Kör.</span><span class="sxs-lookup"><span data-stu-id="a51ba-171">Click Run.</span></span>
    * <span data-ttu-id="a51ba-172">Klicka på Bläddra och välj filen Response2.xml.</span><span class="sxs-lookup"><span data-stu-id="a51ba-172">Click Browse and select the Response2.xml file.</span></span>  
5. <span data-ttu-id="a51ba-173">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="a51ba-173">Click OK.</span></span>
    * <span data-ttu-id="a51ba-174">Granska den genererade utleveransen.</span><span class="sxs-lookup"><span data-stu-id="a51ba-174">Review the generated output.</span></span> <span data-ttu-id="a51ba-175">Observera att svarstypen har identifieras korrekt och parsad (ERModelEnumDataSourceHandler#EFSTA model#enumType#C betyder systemomstart-fall).</span><span class="sxs-lookup"><span data-stu-id="a51ba-175">Note that the response type has been correctly recognized and parsed (ERModelEnumDataSourceHandler#EFSTA model#enumType#R means system restart case).</span></span>   
    * <span data-ttu-id="a51ba-176">Öppna filen Response3.xml i en XML-läsaren.</span><span class="sxs-lookup"><span data-stu-id="a51ba-176">Open the Response3.xml file in an XML reader.</span></span> <span data-ttu-id="a51ba-177">Observera att den här filen börjar från rotobjektet TraZ och att det här inte är konfigurerad med ER format.</span><span class="sxs-lookup"><span data-stu-id="a51ba-177">Note that this file starts from the TraZ root item and that this structure is not configured using ER format.</span></span>   
6. <span data-ttu-id="a51ba-178">Klicka på Kör.</span><span class="sxs-lookup"><span data-stu-id="a51ba-178">Click Run.</span></span>
    * <span data-ttu-id="a51ba-179">Klicka på Bläddra och välj filen Response3.xml.</span><span class="sxs-lookup"><span data-stu-id="a51ba-179">Click Browse and select the Response3.xml file.</span></span>  
7. <span data-ttu-id="a51ba-180">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="a51ba-180">Click OK.</span></span>
    * <span data-ttu-id="a51ba-181">Granska den genererade utleveransen.</span><span class="sxs-lookup"><span data-stu-id="a51ba-181">Review the generated output.</span></span> <span data-ttu-id="a51ba-182">Observera att svarstypen har identifieras korrekt och inte stöds (ERModelEnumDataSourceHandler#EFSTA model#enumType#U).</span><span class="sxs-lookup"><span data-stu-id="a51ba-182">Note that the response type has been correctly recognized as not-supported (ERModelEnumDataSourceHandler#EFSTA model#enumType#U).</span></span> <span data-ttu-id="a51ba-183">Ett likadant meddelande har placerats i informationsloggen (enligt inställningen för ER-validering) och de flesta datamodeller har inte fyllts i.</span><span class="sxs-lookup"><span data-stu-id="a51ba-183">The corresponding message has been placed in the Infolog (according to the ER validation setting), and most of the data model has not been filled in.</span></span>   
    * <span data-ttu-id="a51ba-184">Öppna filen Response4.xml i en XML-läsaren.</span><span class="sxs-lookup"><span data-stu-id="a51ba-184">Open the Response4.xml file in an XML reader.</span></span> <span data-ttu-id="a51ba-185">Observera att strukturen för den här filen är nästan samma som den parsade Response1.xml, förutom de kapslade elementen för rotelementet "TraC".</span><span class="sxs-lookup"><span data-stu-id="a51ba-185">Note that the structure of this file is almost the same as the successfully parsed Response1.xml, except the sequence of nested elements of the root element ‘TraC’.</span></span>   
8. <span data-ttu-id="a51ba-186">Klicka på Kör.</span><span class="sxs-lookup"><span data-stu-id="a51ba-186">Click Run.</span></span>
    * <span data-ttu-id="a51ba-187">Klicka på Bläddra och välj filen Response4.xml.</span><span class="sxs-lookup"><span data-stu-id="a51ba-187">Click Browse and select the Response4.xml file.</span></span>  
9. <span data-ttu-id="a51ba-188">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="a51ba-188">Click OK.</span></span>
    * <span data-ttu-id="a51ba-189">Granska den genererade utleveransen.</span><span class="sxs-lookup"><span data-stu-id="a51ba-189">Review the generated output.</span></span> <span data-ttu-id="a51ba-190">Observera att svarstypen har identifieras korrekt och inte stöds (ERModelEnumDataSourceHandler#EFSTA model#enumType#U)).</span><span class="sxs-lookup"><span data-stu-id="a51ba-190">Note that the response type has been correctly recognized as not-supported (ERModelEnumDataSourceHandler#EFSTA model#enumType#U)).</span></span> <span data-ttu-id="a51ba-191">Ett likadant meddelande har placerats i informationsloggen och de flesta datamodeller har inte fyllts i.</span><span class="sxs-lookup"><span data-stu-id="a51ba-191">The corresponding message has been placed in the Infolog, and most of the data model has not been filled in.</span></span> <span data-ttu-id="a51ba-192">Detta beror på att den aktuella inställningen för det här ER-formatet förutsätter ett visst antal kapslade element i artikelroten för den importerade filen.</span><span class="sxs-lookup"><span data-stu-id="a51ba-192">This is because the current setting of this ER format assumes a certain sequence of nested elements of the root item of the incoming file.</span></span>   
10. <span data-ttu-id="a51ba-193">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="a51ba-193">Close the page.</span></span>
11. <span data-ttu-id="a51ba-194">Välj "Responses\Transaction completion\TraC" i trädet.</span><span class="sxs-lookup"><span data-stu-id="a51ba-194">In the tree, select 'Responses\Transaction completion\TraC'.</span></span>
12. <span data-ttu-id="a51ba-195">I parsingordern för kapslade element, fälj "Något".</span><span class="sxs-lookup"><span data-stu-id="a51ba-195">In the Parsing order of nested elements field, select 'Any'.</span></span>
    * <span data-ttu-id="a51ba-196">Markera Något i fältet "Parsningsordning för kapslade element" för att låta flera kapslade element för roten XML-objektet.</span><span class="sxs-lookup"><span data-stu-id="a51ba-196">Select Any in the ‘Parsing order of nested elements’ field to allow any sequence of nested elements for this root XML item.</span></span>  
13. <span data-ttu-id="a51ba-197">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="a51ba-197">Click Save.</span></span>
14. <span data-ttu-id="a51ba-198">Klicka på Mappa format till modell.</span><span class="sxs-lookup"><span data-stu-id="a51ba-198">Click Map format to model.</span></span>
15. <span data-ttu-id="a51ba-199">Klicka på Kör.</span><span class="sxs-lookup"><span data-stu-id="a51ba-199">Click Run.</span></span>
    * <span data-ttu-id="a51ba-200">Klicka på Bläddra och välj filen Response4.xml.</span><span class="sxs-lookup"><span data-stu-id="a51ba-200">Click Browse and select the Response4.xml file.</span></span>  
16. <span data-ttu-id="a51ba-201">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="a51ba-201">Click OK.</span></span>
    * <span data-ttu-id="a51ba-202">Granska den genererade utleveransen.</span><span class="sxs-lookup"><span data-stu-id="a51ba-202">Review the generated output.</span></span> <span data-ttu-id="a51ba-203">Observera att svarstypen nu korrekt har erkänts att överensstämma med Response1.xml-fil.</span><span class="sxs-lookup"><span data-stu-id="a51ba-203">Note that the response type has now been properly recognized as equal for Response1.xml file.</span></span>  

