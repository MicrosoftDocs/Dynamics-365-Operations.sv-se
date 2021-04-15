---
title: Automatisera testning med elektronisk rapportering
description: I det här avsnittet beskrivs hur du kan använda baslinjefunktionen för elektronik rapportering (ER) för att automatisera testning av funktioner.
author: NickSelin
ms.date: 07/02/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERSolutionTable, ERFormatBaselineTable, ERFormatMappingRunLogTable, ERParameters
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2018-04-01
ms.dyn365.ops.version: Release 8.0
ms.openlocfilehash: 0d029773d9aa59b27f80d2f670984a352e163122
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5743881"
---
# <a name="automate-testing-with-electronic-reporting"></a><span data-ttu-id="e3378-103">Automatisera testning med elektronisk rapportering</span><span class="sxs-lookup"><span data-stu-id="e3378-103">Automate testing with Electronic reporting</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="e3378-104">I det här avsnittet beskrivs hur du kan använda ramverket för elektronik rapportering (ER) för att automatisera testning av vissa funktioner.</span><span class="sxs-lookup"><span data-stu-id="e3378-104">This topic explains how you can use the Electronic reporting (ER) framework to automate testing of some functionality.</span></span> <span data-ttu-id="e3378-105">Exemplet i det här avsnittet visar hur du automatiserar testningen av bearbetning av leverantörsbetalningar.</span><span class="sxs-lookup"><span data-stu-id="e3378-105">The example in this topic shows how to automate the testing of vendor payment processing.</span></span>

<span data-ttu-id="e3378-106">Appen använder ER-ramverket för att generera betalningsfiler och motsvarande dokument under bearbetning av leverantörsbetalningar.</span><span class="sxs-lookup"><span data-stu-id="e3378-106">The application uses the ER framework to generate payment files and corresponding documents during vendor payment processing.</span></span> <span data-ttu-id="e3378-107">ER-ramverket består av en datamodell, modellmappning och formatkomponenter som stöder betalningsbearbetning för olika betalningstyper och genereringen av dokument i olika format.</span><span class="sxs-lookup"><span data-stu-id="e3378-107">The ER framework consists of a data model, model mappings, and format components that support payment processing for different payment types and the generation of documents in different formats.</span></span> <span data-ttu-id="e3378-108">Dessa komponenter kan hämtas från Microsoft Dynamics LCS (Lifecycle Services) och importeras till instansen.</span><span class="sxs-lookup"><span data-stu-id="e3378-108">These components can be downloaded from Microsoft Dynamics Lifecycle Services (LCS) and imported into the instance.</span></span>

<span data-ttu-id="e3378-109">Du kan också anpassa varje komponent i Microsoft och använda den som grund för din egen anpassade komponent.</span><span class="sxs-lookup"><span data-stu-id="e3378-109">You also can customize each Microsoft component and use it as the basis of your own custom component.</span></span> <span data-ttu-id="e3378-110">Genom att skapa en anpassad version kan du göra ändringar som stöder specifika krav.</span><span class="sxs-lookup"><span data-stu-id="e3378-110">By creating a custom version, you can make changes that support specific requirements.</span></span> <span data-ttu-id="e3378-111">Du kan t.ex. ändra mappningen för ER-datamodell och ER-modell för att få åtkomst till kundspecifika programdata, eller ändra ett återställningsformat om du vill ändra layouten i ett genererat dokument.</span><span class="sxs-lookup"><span data-stu-id="e3378-111">For example, you can adjust the ER data model and ER model mapping to access customer-specific application data, or you can change an ER format to modify the layout of a generated document.</span></span>

<span data-ttu-id="e3378-112">Du kan använda anpassade ER-format för att bearbeta betalningsfiler som genererar leverantörsbetalningar och även för att bearbeta kontrollrapporter.</span><span class="sxs-lookup"><span data-stu-id="e3378-112">You can use customized ER formats to process payment files that generate vendor payments and also to process control reports.</span></span> <span data-ttu-id="e3378-113">Versionsnumrering stöds i ER-komponenter.</span><span class="sxs-lookup"><span data-stu-id="e3378-113">Versioning is supported in ER components.</span></span> <span data-ttu-id="e3378-114">Därför kan Microsoft tillhandahålla uppdaterade versioner av ER-lösningar för bearbetning av leverantörsbetalningar, och du kan automatiskt slå samman den uppdaterade versionen med den anpassade komponenten genom att ombasera den.</span><span class="sxs-lookup"><span data-stu-id="e3378-114">Therefore, Microsoft can provide updated versions of ER solutions for vendor payment processing, and you can automatically merge the updated version with your customized component by rebasing it.</span></span> <span data-ttu-id="e3378-115">Du måste dock testa den ombaserade versionen för att vara säker på att den fungerar som förväntat.</span><span class="sxs-lookup"><span data-stu-id="e3378-115">However, you must test the rebased version to make sure that it works as you expect.</span></span>

<span data-ttu-id="e3378-116">ER-datamodeller och ER-modellmappningar är vanliga för många ER-format som används för att bearbeta betalningar av olika typer och för att generera lands-/regionspecifika betalningsdokument.</span><span class="sxs-lookup"><span data-stu-id="e3378-116">ER data models and ER model mappings are common for many ER formats that are used to process payments of different types and to generate country/region-specific payment documents.</span></span> <span data-ttu-id="e3378-117">Därför är det starkt önskvärt att automatisera godkännandet av användare och integration så att det utförs automatiskt i flera företag men tar hänsyn till land- eller regionssammanhanget för varje målföretag, använder olika datauppsättningar, och så vidare.</span><span class="sxs-lookup"><span data-stu-id="e3378-117">Therefore, it's highly desirable to automate user acceptance and integration testing so that it's automatically done in multiple companies but considers the country/region context of each target company, uses different datasets, and so on.</span></span>

<span data-ttu-id="e3378-118">Mer information om hur du skapar en anpassad version av ett format som baseras på det format som du har fått från en konfigurationsleverantör finns i [ER uppgraderar ditt format genom att anta en ny, grundläggande version av det formatet](./tasks/er-upgrade-format.md).</span><span class="sxs-lookup"><span data-stu-id="e3378-118">For more information about how to create a custom version of a format that is based on the format that you received from a configuration provider, see [ER Upgrade your format by adopting a new, base version of that format](./tasks/er-upgrade-format.md).</span></span>

## <a name="key-concepts"></a><span data-ttu-id="e3378-119">Viktiga begrepp</span><span class="sxs-lookup"><span data-stu-id="e3378-119">Key concepts</span></span>

<span data-ttu-id="e3378-120">Funktionella privilegierade användare kan skapa godtagande och integrationstestning för användare utan att behöva skriva källkoden.</span><span class="sxs-lookup"><span data-stu-id="e3378-120">Functional power users can author user acceptance and integration testing without having to write source code.</span></span>

- <span data-ttu-id="e3378-121">Använd funktionen ER-baslinje för att jämföra genererade dokument med huvudkopior.</span><span class="sxs-lookup"><span data-stu-id="e3378-121">Use the ER baseline feature to compare generated documents to master copies.</span></span> <span data-ttu-id="e3378-122">Mer information finns i [Spåra genererade rapportresultat och jämför dem med baslinjevärden](er-trace-reports-compare-baseline.md).</span><span class="sxs-lookup"><span data-stu-id="e3378-122">For more information, see [Trace generated report results and compare them with baseline values](er-trace-reports-compare-baseline.md).</span></span>
- <span data-ttu-id="e3378-123">Använd uppgiftsinspelare om du vill registrera testfall och ta med utvärdering av baslinje.</span><span class="sxs-lookup"><span data-stu-id="e3378-123">Use Task recorder to record test cases, and include baseline assessment.</span></span> <span data-ttu-id="e3378-124">Mer information finns i [Uppgiftsinspelarresurser](../user-interface/task-recorder.md).</span><span class="sxs-lookup"><span data-stu-id="e3378-124">For more information, see [Task recorder resources](../user-interface/task-recorder.md).</span></span>
- <span data-ttu-id="e3378-125">Gruppera testfall för obligatoriska testscenarier.</span><span class="sxs-lookup"><span data-stu-id="e3378-125">Group test cases for required test scenarios.</span></span> <span data-ttu-id="e3378-126">Mer information finns i [skapa och automatisera användaracceptanstest](../lifecycle-services/using-task-guides-and-bpm-to-create-user-acceptance-tests.md).</span><span class="sxs-lookup"><span data-stu-id="e3378-126">For more information, see [Create and automate user acceptance tests](../lifecycle-services/using-task-guides-and-bpm-to-create-user-acceptance-tests.md).</span></span>

    - <span data-ttu-id="e3378-127">Använd affärsprocessmodelleraren (BPM) i LCS för att göra bibliotek för användaracceptanstester.</span><span class="sxs-lookup"><span data-stu-id="e3378-127">Use Business process modeler (BPM) in LCS to make libraries for user acceptance tests.</span></span>
    - <span data-ttu-id="e3378-128">Använd BPM-testbibliotek för att skapa en testplan och testpaket i Microsoft Azure DevOps Services (Azure DevOps).</span><span class="sxs-lookup"><span data-stu-id="e3378-128">Use BPM test libraries to create a test plan and test suites in Microsoft Azure DevOps Services (Azure DevOps).</span></span>

<span data-ttu-id="e3378-129">Funktionella privilegierade användare kan köra tester av användarens acceptans och integration.</span><span class="sxs-lookup"><span data-stu-id="e3378-129">Functional power users can run user acceptance and integration tests.</span></span>

- <span data-ttu-id="e3378-130">Använda Regression Suite Automation Tool (RSAT) för att köra testfall av önskat testprogrampaket.</span><span class="sxs-lookup"><span data-stu-id="e3378-130">Use Regression suite automation tool (RSAT) to run test cases of the desired test suite.</span></span>
- <span data-ttu-id="e3378-131">Rapportera resultaten från testet till Azure DevOps, och undersök dessa resultat med hjälp av den här tjänsten.</span><span class="sxs-lookup"><span data-stu-id="e3378-131">Report the results of the testing to Azure DevOps, and use this service to investigate those results.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="e3378-132">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="e3378-132">Prerequisites</span></span>

<span data-ttu-id="e3378-133">Innan du kan slutföra uppgifterna i detta ämne måste du slutföra följande förutsättningar:</span><span class="sxs-lookup"><span data-stu-id="e3378-133">Before you can complete the tasks in this topic, you must complete the following prerequisites:</span></span>

- <span data-ttu-id="e3378-134">Distribuera en topologi som stöder testautomatisering.</span><span class="sxs-lookup"><span data-stu-id="e3378-134">Deploy a topology that supports test automation.</span></span> <span data-ttu-id="e3378-135">Du måste ha tillgång till instansen av denna topologi för rollen **systemadministratör**.</span><span class="sxs-lookup"><span data-stu-id="e3378-135">You must have access to the instance of this topology for the **System administrator** role.</span></span> <span data-ttu-id="e3378-136">Den här topologin måste innehålla de demodata som ska användas i det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="e3378-136">This topology must contain the demo data that will be used in this example.</span></span> <span data-ttu-id="e3378-137">Mer information finns i [distribuera och använd en miljö som stöder kontinuerlig automatisering av bygga och testa](../perf-test/continuous-build-test-automation.md).</span><span class="sxs-lookup"><span data-stu-id="e3378-137">For more information, see [Deploy and use an environment that supports continuous build and test automation](../perf-test/continuous-build-test-automation.md).</span></span>
- <span data-ttu-id="e3378-138">Om du vill köra acceptans- och integrationstest automatiskt måste du installera RSAT i den topologi som du använder och konfigurera det på lämpligt sätt.</span><span class="sxs-lookup"><span data-stu-id="e3378-138">To run user acceptance and integration tests automatically, you must install RSAT in the topology that you're using and configure it in the appropriate manner.</span></span> <span data-ttu-id="e3378-139">Information om hur du installerar och konfigurerar RSAT och konfigurerar den för att fungera med Finance and Operations och Azure DevOps finns i [Regression Suite Automation Tool](https://www.microsoft.com/download/details.aspx?id=57357).</span><span class="sxs-lookup"><span data-stu-id="e3378-139">For information about how to install and configure RSAT and configure it to work with Finance and Operations apps and Azure DevOps, see [Regression Suite Automation Tool](https://www.microsoft.com/download/details.aspx?id=57357).</span></span> <span data-ttu-id="e3378-140">Var uppmärksam på förutsättningarna för att använda verktyget.</span><span class="sxs-lookup"><span data-stu-id="e3378-140">Pay attention to the prerequisites for using the tool.</span></span> <span data-ttu-id="e3378-141">Följande illustration visar ett exempel på RSAT-inställningar.</span><span class="sxs-lookup"><span data-stu-id="e3378-141">The following illustration shows an example of the RSAT settings.</span></span> <span data-ttu-id="e3378-142">Den blå rektangeln innesluter parametrarna som anger åtkomsten till Azure DevOps.</span><span class="sxs-lookup"><span data-stu-id="e3378-142">The blue rectangle encloses the parameters that specify access to Azure DevOps.</span></span> <span data-ttu-id="e3378-143">Den gröna rektangeln innesluter parametrarna som anger åtkomsten till instansen.</span><span class="sxs-lookup"><span data-stu-id="e3378-143">The green rectangle encloses the parameters that specify access to the instance.</span></span>

    <span data-ttu-id="e3378-144">![RSAT-inställningar](media/GER-Configure.png "Skärmbild av dialogrutan RSAT-inställningar")</span><span class="sxs-lookup"><span data-stu-id="e3378-144">![RSAT settings](media/GER-Configure.png "Screenshot of the RSAT Settings dialog box")</span></span>

- <span data-ttu-id="e3378-145">Om du vill ordna testfall i paket som hjälper till att garantera korrekt körningsordning så att du kan samla in loggar över testkörningar för vidare rapportering och utredning måste du ha åtkomst till Azure DevOps från den distribuerade topologin.</span><span class="sxs-lookup"><span data-stu-id="e3378-145">To organize test cases in suites to help guarantee the correct execution sequence, so that you can collect logs of test executions for further reporting and investigation, you must have access to Azure DevOps from the deployed topology.</span></span>
- <span data-ttu-id="e3378-146">Om du vill slutföra exemplet i det här avsnittet rekommenderar vi att du hämtar [ER-användning för test av RSAT](https://go.microsoft.com/fwlink/?linkid=874684).</span><span class="sxs-lookup"><span data-stu-id="e3378-146">To complete the example in this topic, we recommend that you download [ER usage for RSAT tests](https://go.microsoft.com/fwlink/?linkid=874684).</span></span> <span data-ttu-id="e3378-147">Zip-filen innehåller följande uppgiftsguider:</span><span class="sxs-lookup"><span data-stu-id="e3378-147">This zip file contains the following task guides:</span></span>

    | <span data-ttu-id="e3378-148">Innehåll</span><span class="sxs-lookup"><span data-stu-id="e3378-148">Content</span></span>                                           | <span data-ttu-id="e3378-149">Filnamn och plats</span><span class="sxs-lookup"><span data-stu-id="e3378-149">File name and location</span></span> |
    |---------------------------------------------------|------------------------|
    | <span data-ttu-id="e3378-150">Exempel på uppgiftsinspelning för förberedelse av data för testning</span><span class="sxs-lookup"><span data-stu-id="e3378-150">Sample task recording to prepare data for testing</span></span> | <span data-ttu-id="e3378-151">Förbered\\inspelning.xml</span><span class="sxs-lookup"><span data-stu-id="e3378-151">Prepare\\Recording.xml</span></span> |
    | <span data-ttu-id="e3378-152">Exempel på uppgiftsinspelning för att bearbeta leverantörsbetalning</span><span class="sxs-lookup"><span data-stu-id="e3378-152">Sample task recording to process vendor payment</span></span>   | <span data-ttu-id="e3378-153">Bearbeta\\inspelning.xml</span><span class="sxs-lookup"><span data-stu-id="e3378-153">Process\\Recording.xml</span></span> |

## <a name="prepare-the-accounts-payable-module-to-process-vendor-payments"></a><span data-ttu-id="e3378-154">Förbered modulen leverantörsreskontra om du vill bearbeta leverantörsbetalningar</span><span class="sxs-lookup"><span data-stu-id="e3378-154">Prepare the Accounts payable module to process vendor payments</span></span>

1. <span data-ttu-id="e3378-155">Logga in på instansen.</span><span class="sxs-lookup"><span data-stu-id="e3378-155">Sign in to your instance.</span></span>
2. <span data-ttu-id="e3378-156">Hämta följande ER-konfigurationer från LCS.</span><span class="sxs-lookup"><span data-stu-id="e3378-156">Download the following ER configurations from LCS.</span></span> <span data-ttu-id="e3378-157">För instruktioner, se [ER-importera en konfiguration från Lifecycle Services](./tasks/er-import-configuration-lifecycle-services.md).</span><span class="sxs-lookup"><span data-stu-id="e3378-157">For instructions, see [ER Import a configuration from Lifecycle Services](./tasks/er-import-configuration-lifecycle-services.md).</span></span>

    - <span data-ttu-id="e3378-158">**Betalningsmodell** ER-modellkonfiguration</span><span class="sxs-lookup"><span data-stu-id="e3378-158">**Payment model** ER model configuration</span></span>
    - <span data-ttu-id="e3378-159">**Betalningsmodellmappnning 1611** Mappningskonfiguration för ER-modell</span><span class="sxs-lookup"><span data-stu-id="e3378-159">**Payment model mapping 1611** ER model mapping configuration</span></span>
    - <span data-ttu-id="e3378-160">**BACS (UK)** ER-formatkonfiguration</span><span class="sxs-lookup"><span data-stu-id="e3378-160">**BACS (UK)** ER format configuration</span></span>

    <span data-ttu-id="e3378-161">![Konfigurationer för elektronisk rapportering](media/GER-Configurations.png "Skärmbild av sidan Konfigurationer i elektroniskt rapportering")</span><span class="sxs-lookup"><span data-stu-id="e3378-161">![Electronic reporting configurations](media/GER-Configurations.png "Screenshot of the Configurations page in Electronic reporting")</span></span>

3. <span data-ttu-id="e3378-162">Välj demoföretaget **GBSI** som har kontexten land/region i Storbritannien.</span><span class="sxs-lookup"><span data-stu-id="e3378-162">Select the **GBSI** demo data company, which has a country/region context in Great Britain.</span></span>
4. <span data-ttu-id="e3378-163">Konfigurera parametrar för leverantörsreskontra:</span><span class="sxs-lookup"><span data-stu-id="e3378-163">Configure Accounts payable parameters:</span></span>

    1. <span data-ttu-id="e3378-164">Gå till **Leverantörsreskontra \> Betalningsinställning \> Betalningsmetoder**.</span><span class="sxs-lookup"><span data-stu-id="e3378-164">Go to **Accounts payable \> Payment setup \> Methods of payment**.</span></span>
    2. <span data-ttu-id="e3378-165">Välj Metod för **elektroniska** betalningar.</span><span class="sxs-lookup"><span data-stu-id="e3378-165">Select the **Electronic** method of payment.</span></span>
    3. <span data-ttu-id="e3378-166">Konfigurera den valda betalningsmetoden så att den använder ER-formatet **BACS (UK)** som du hämtade tidigare för bearbetning av leverantörsbetalningar:</span><span class="sxs-lookup"><span data-stu-id="e3378-166">Configure the selected method of payment so that it uses the **BACS (UK)** ER format that you downloaded earlier for vendor payment processing:</span></span>

        1. <span data-ttu-id="e3378-167">På snabbfliken **filformat** ställer du in alternativet **Allmänt elektroniskt exportformat** till **Ja**.</span><span class="sxs-lookup"><span data-stu-id="e3378-167">On the **File formats** FastTab, set the **Generic electronic Export format** option to **Yes**.</span></span>
        2. <span data-ttu-id="e3378-168">I fältet **Exportera formatkonfiguration** väljer du **BACS (UK)**.</span><span class="sxs-lookup"><span data-stu-id="e3378-168">In the **Export format configuration** field, select **BACS (UK)**.</span></span>

    <span data-ttu-id="e3378-169">![Sidan Betalningsmetoder](media/GER-APParameters.png "Skärmbild av sidan betalningsmetoder")</span><span class="sxs-lookup"><span data-stu-id="e3378-169">![Methods of payment page](media/GER-APParameters.png "Screenshot of the Methods of payment page")</span></span>

    > [!NOTE]
    > <span data-ttu-id="e3378-170">Om du har den härledda versionen av det här ER-formatet som har skapats för anpassningar kan du välja den här konfigurationen i betalningsmetoden **elektronisk**.</span><span class="sxs-lookup"><span data-stu-id="e3378-170">If you have the derived version of this ER format that was created to support customizations, you can select this configuration in the **Electronic** method of payment.</span></span>

5. <span data-ttu-id="e3378-171">Skapa ett exempel på en leverantörsbetalning:</span><span class="sxs-lookup"><span data-stu-id="e3378-171">Create an example vendor payment:</span></span>

    1. <span data-ttu-id="e3378-172">Gå till **Leverantörsreskontra \> Betalningar \> Betalningsjournal**.</span><span class="sxs-lookup"><span data-stu-id="e3378-172">Go to **Accounts payable \> Payments \> Payment journal**.</span></span>
    2. <span data-ttu-id="e3378-173">Kontrollera att du inte har bokfört betalningsjournalen.</span><span class="sxs-lookup"><span data-stu-id="e3378-173">Make sure that you haven't posted the payment journal.</span></span>

        <span data-ttu-id="e3378-174">![Sidan betalningsjournal](media/GER-APJournal.png "Skärmbild av sidan betalningsjournal")</span><span class="sxs-lookup"><span data-stu-id="e3378-174">![Payment journal page](media/GER-APJournal.png "Screenshot of the Payment journal page")</span></span>

    3. <span data-ttu-id="e3378-175">Välj **rader** och ange en rad med följande information.</span><span class="sxs-lookup"><span data-stu-id="e3378-175">Select **Lines**, and enter a line that has the following information.</span></span>

        | <span data-ttu-id="e3378-176">Fält</span><span class="sxs-lookup"><span data-stu-id="e3378-176">Field</span></span>               | <span data-ttu-id="e3378-177">Exempelvärde</span><span class="sxs-lookup"><span data-stu-id="e3378-177">Example value</span></span>   |
        |---------------------|-----------------|
        | <span data-ttu-id="e3378-178">Leverantörsnamn</span><span class="sxs-lookup"><span data-stu-id="e3378-178">Vendor name</span></span>         | <span data-ttu-id="e3378-179">GB\_SI\_000001</span><span class="sxs-lookup"><span data-stu-id="e3378-179">GB\_SI\_000001</span></span>  |
        | <span data-ttu-id="e3378-180">Debet</span><span class="sxs-lookup"><span data-stu-id="e3378-180">Debit</span></span>               | <span data-ttu-id="e3378-181">1,000.00</span><span class="sxs-lookup"><span data-stu-id="e3378-181">1,000.00</span></span>        |
        | <span data-ttu-id="e3378-182">Valuta</span><span class="sxs-lookup"><span data-stu-id="e3378-182">Currency</span></span>            | <span data-ttu-id="e3378-183">GBP</span><span class="sxs-lookup"><span data-stu-id="e3378-183">GBP</span></span>             |
        | <span data-ttu-id="e3378-184">Motkontotyp</span><span class="sxs-lookup"><span data-stu-id="e3378-184">Offset account type</span></span> | <span data-ttu-id="e3378-185">Bank</span><span class="sxs-lookup"><span data-stu-id="e3378-185">Bank</span></span>            |
        | <span data-ttu-id="e3378-186">Motkonto</span><span class="sxs-lookup"><span data-stu-id="e3378-186">Offset account</span></span>      | <span data-ttu-id="e3378-187">GBSI-OPERATION</span><span class="sxs-lookup"><span data-stu-id="e3378-187">GBSI OPER</span></span>       |
        | <span data-ttu-id="e3378-188">Betalningsmetod</span><span class="sxs-lookup"><span data-stu-id="e3378-188">Method of payment</span></span>   | <span data-ttu-id="e3378-189">Elektronisk</span><span class="sxs-lookup"><span data-stu-id="e3378-189">Electronic</span></span>      |

    <span data-ttu-id="e3378-190">![Sidan Leverantörsbetalningar](media/GER-APJournalLines.png "Skärmbild av sidan leverantörsbetalningar")</span><span class="sxs-lookup"><span data-stu-id="e3378-190">![Vendor payments page](media/GER-APJournalLines.png "Screenshot of the Vendor payments page")</span></span>

## <a name="prepare-the-er-framework-to-test-vendor-payment-processing"></a><span data-ttu-id="e3378-191">Förbered ER-ramverket för att testa bearbetning av leverantörsbetalning</span><span class="sxs-lookup"><span data-stu-id="e3378-191">Prepare the ER framework to test vendor payment processing</span></span>

### <a name="configure-er-parameters"></a><span data-ttu-id="e3378-192">Konfigurera ER-parametrar</span><span class="sxs-lookup"><span data-stu-id="e3378-192">Configure ER parameters</span></span>

1. <span data-ttu-id="e3378-193">Gå till **Organisationsadministration \> Elektronisk rapportering \> Parametrar för elektronisk rapportering**.</span><span class="sxs-lookup"><span data-stu-id="e3378-193">Go to **Organization administration \> Electronic reporting \> Electronic reporting parameters**.</span></span>
2. <span data-ttu-id="e3378-194">På fliken **Bilagor** i fältet **Baslinje**, välj **Fil** som dokumenttyp som ramverket dokumenthantering (DM) använder för att behålla dokument som är relaterade till baslinjefunktioner som DM-bilagor.</span><span class="sxs-lookup"><span data-stu-id="e3378-194">On the **Attachments** tab, in the **Baseline** field, select **File** as the document type that the Document management (DM) framework uses to keep documents that are related to the baseline feature as DM attachments.</span></span>

    <span data-ttu-id="e3378-195">![Sida för parametrar för elektronisk rapportering](media/GER-ERParameters.png "Skärmbild av sidan parametrar för elektronisk rapportering")</span><span class="sxs-lookup"><span data-stu-id="e3378-195">![Electronic reporting parameters page](media/GER-ERParameters.png "Screenshot of the Electronic reporting parameters page")</span></span>

### <a name="generate-baseline-copies-of-vendor-paymentrelated-documents"></a><span data-ttu-id="e3378-196">Generera baslinjekopior av dokument relaterade till leverantörsbetalningar</span><span class="sxs-lookup"><span data-stu-id="e3378-196">Generate baseline copies of vendor payment–related documents</span></span>

1. <span data-ttu-id="e3378-197">Gå till **Leverantörsreskontra \> Betalningar \> Betalningsjournal**.</span><span class="sxs-lookup"><span data-stu-id="e3378-197">Go to **Accounts payable \> Payments \> Payment journal**.</span></span>
2. <span data-ttu-id="e3378-198">Markera **rader**</span><span class="sxs-lookup"><span data-stu-id="e3378-198">Select **Lines**.</span></span>
3. <span data-ttu-id="e3378-199">Välj **Generera betalningar**.</span><span class="sxs-lookup"><span data-stu-id="e3378-199">Select **Generate payments**.</span></span>
4. <span data-ttu-id="e3378-200">Välj Metod för **elektroniska** betalningar.</span><span class="sxs-lookup"><span data-stu-id="e3378-200">Select the **Electronic** method of payment.</span></span>
5. <span data-ttu-id="e3378-201">Välj bankkontot **GBSI OPER**.</span><span class="sxs-lookup"><span data-stu-id="e3378-201">Select the **GBSI OPER** bank account.</span></span>
6. <span data-ttu-id="e3378-202">Ange alternativet **Skriv ut kontrollrapport** till **Ja**.</span><span class="sxs-lookup"><span data-stu-id="e3378-202">Set the **Print control report** option to **Yes**.</span></span>
7. <span data-ttu-id="e3378-203">Hämta den genererade utdata som en zip-fil.</span><span class="sxs-lookup"><span data-stu-id="e3378-203">Download the generated output as a zip file.</span></span>
8. <span data-ttu-id="e3378-204">Öppna den hämtade filen.</span><span class="sxs-lookup"><span data-stu-id="e3378-204">Open the downloaded file.</span></span>
9. <span data-ttu-id="e3378-205">Extrahera följande filer från den hämtade filen:</span><span class="sxs-lookup"><span data-stu-id="e3378-205">Extract following files from the downloaded file:</span></span>

    - <span data-ttu-id="e3378-206">**Fil** betalningsfil i textformat</span><span class="sxs-lookup"><span data-stu-id="e3378-206">**File** payment file in text format</span></span>
    - <span data-ttu-id="e3378-207">**ERVendOutPaymControlReport** kontrollrapportfil i XLSX-format</span><span class="sxs-lookup"><span data-stu-id="e3378-207">**ERVendOutPaymControlReport** control report file in XLSX format</span></span>

    <span data-ttu-id="e3378-208">![Extraherade filer](media/GER-APJournalProcessed.png "Skärmbild av extraherade filnamn i Utforskaren i Windows")</span><span class="sxs-lookup"><span data-stu-id="e3378-208">![Extracted files](media/GER-APJournalProcessed.png "Screenshot of extracted file names in Windows explorer")</span></span>

### <a name="turn-on-the-er-baseline-feature"></a><span data-ttu-id="e3378-209">Aktivera funktionen för ER-baslinje</span><span class="sxs-lookup"><span data-stu-id="e3378-209">Turn on the ER baseline feature</span></span>

1. <span data-ttu-id="e3378-210">Gå till **Organisationsadministration  \> Elektronisk rapportering \> Konfigurationer**.</span><span class="sxs-lookup"><span data-stu-id="e3378-210">Go to **Organization administration \> Electronic reporting \> Configurations**.</span></span>
2. <span data-ttu-id="e3378-211">Välj **Användarparametrar** på fliken **Konfigurationer** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="e3378-211">On the Action Pane, on the **Configurations** tab, select **User parameters**.</span></span>
3. <span data-ttu-id="e3378-212">Ställ in alternativet **Kör i felsökningsläge** till **Ja**.</span><span class="sxs-lookup"><span data-stu-id="e3378-212">Set the **Run in debug mode** option to **Yes**.</span></span>

<span data-ttu-id="e3378-213">Genom att aktivera parametern **kör i felsökningsläge** tvingar du ER-ramverket att utföra följande åtgärder efter körningen av ett återställningsformat som genererar utgående dokument:</span><span class="sxs-lookup"><span data-stu-id="e3378-213">By turning on the **Run in debug mode** parameter, you force the ER framework to perform the following actions after the execution of any ER format that generates outgoing documents:</span></span>

1. <span data-ttu-id="e3378-214">Fastställ om en baslinje har konfigurerats för någon av komponenterna i det körda ER-formatet.</span><span class="sxs-lookup"><span data-stu-id="e3378-214">Determine whether a baseline was configured for any of components of the executed ER format.</span></span>
2. <span data-ttu-id="e3378-215">Ta reda på om varje konfigurerad baslinje är tillämplig i de aktuella villkoren (företagskod för det inloggade företaget, filnamn och filnamnstillägg för genererade utdata och så vidare).</span><span class="sxs-lookup"><span data-stu-id="e3378-215">Determine whether each configured baseline is applicable in the current conditions (company code of the signed-in company, file name and file name extension of the generated output, and so on).</span></span>
3. <span data-ttu-id="e3378-216">Utför följande åtgärder för varje tillämplig baslinje:</span><span class="sxs-lookup"><span data-stu-id="e3378-216">For each applicable baseline, perform the following actions:</span></span>

    1. <span data-ttu-id="e3378-217">Jämför de utdata som genereras under körningen av ER-formatet med motsvarande baslinje.</span><span class="sxs-lookup"><span data-stu-id="e3378-217">Compare the output that is generated during execution of the ER format with the corresponding baseline.</span></span>
    2. <span data-ttu-id="e3378-218">Spara resultaten av jämförelsen i felsökningsloggen för ER-konfigurationer.</span><span class="sxs-lookup"><span data-stu-id="e3378-218">Store the results of the comparison in the ER configurations debug log.</span></span>

### <a name="configure-er-baselines-for-vendor-payment-processing"></a><span data-ttu-id="e3378-219">Konfigurera ER-baslinjer för bearbetning av leverantörsbetalning</span><span class="sxs-lookup"><span data-stu-id="e3378-219">Configure ER baselines for vendor payment processing</span></span>

1. <span data-ttu-id="e3378-220">Gå till **Organisationsadministration  \> Elektronisk rapportering \> Konfigurationer**.</span><span class="sxs-lookup"><span data-stu-id="e3378-220">Go to **Organization administration \> Electronic reporting \> Configurations**.</span></span>
2. <span data-ttu-id="e3378-221">Välj **baslinjer**.</span><span class="sxs-lookup"><span data-stu-id="e3378-221">Select **Baselines**.</span></span>
3. <span data-ttu-id="e3378-222">Välj **Ny**.</span><span class="sxs-lookup"><span data-stu-id="e3378-222">Select **New**.</span></span>
4. <span data-ttu-id="e3378-223">I fältet **Referenser** väljer du formatet **BACS (UK)**.</span><span class="sxs-lookup"><span data-stu-id="e3378-223">In the **Reference** field, select the **BACS (UK)** format.</span></span>
5. <span data-ttu-id="e3378-224">Välj **bilagor**.</span><span class="sxs-lookup"><span data-stu-id="e3378-224">Select **Attachments**.</span></span>
6. <span data-ttu-id="e3378-225">Lägg till en ny baslinje för leverantörsbetalningsfilen:</span><span class="sxs-lookup"><span data-stu-id="e3378-225">Add a new baseline for the vendor payment file:</span></span>

    1. <span data-ttu-id="e3378-226">Välj **Ny**.</span><span class="sxs-lookup"><span data-stu-id="e3378-226">Select **New**.</span></span>
    2. <span data-ttu-id="e3378-227">I fältet **typ** väljer du DM-dokumenttypen **fil** som du konfigurerade i ER-parametrarna för att lagra baslinjeartefakter.</span><span class="sxs-lookup"><span data-stu-id="e3378-227">In the **Type** field, select the **File** DM document type that you configured in the ER parameters to store baseline artifacts.</span></span>
    3. <span data-ttu-id="e3378-228">Bläddra för att välja den lokalt sparade betalningsfilen **Fil** i textformat.</span><span class="sxs-lookup"><span data-stu-id="e3378-228">Browse to select the locally saved **File** payment file in text format.</span></span>
    4. <span data-ttu-id="e3378-229">I fältet **Beskrivning**, ange **TXT-fil för betalning**.</span><span class="sxs-lookup"><span data-stu-id="e3378-229">In the **Description** field, enter **Payment TXT file**.</span></span>

7. <span data-ttu-id="e3378-230">Lägg till en ny baslinje för kontrollrapporten för leverantörsbetalningen:</span><span class="sxs-lookup"><span data-stu-id="e3378-230">Add a new baseline for the control report for the vendor payment:</span></span>

    1. <span data-ttu-id="e3378-231">Välj **Ny**.</span><span class="sxs-lookup"><span data-stu-id="e3378-231">Select **New**.</span></span>
    2. <span data-ttu-id="e3378-232">I fältet **typ** väljer du DM-dokumenttypen **fil** som du konfigurerade i ER-parametrarna för att lagra baslinjeartefakter.</span><span class="sxs-lookup"><span data-stu-id="e3378-232">In the **Type** field, select the **File** DM document type that you configured in the ER parameters to store baseline artifacts.</span></span>
    3. <span data-ttu-id="e3378-233">Bläddra för att välja den lokalt sparade kontrollrapportfilen **ERVendOutPaymControlReport** i XLSX-format.</span><span class="sxs-lookup"><span data-stu-id="e3378-233">Browse to select the locally saved **ERVendOutPaymControlReport** control report file in XLSX format.</span></span>
    4. <span data-ttu-id="e3378-234">I fältet **Beskrivning**, ange **XLSX-kontrollrapport för betalning**.</span><span class="sxs-lookup"><span data-stu-id="e3378-234">In the **Description** field, enter **Payment XLSX control report**.</span></span>

    <span data-ttu-id="e3378-235">![Baslinjer för leverantörsbetalningsfilen och kontrollrapporten:](media/GER-BaselineAttachments.png "Skärmbild av sidan konfigurationer med rapporten XLSX-kontroll för betalning vald")</span><span class="sxs-lookup"><span data-stu-id="e3378-235">![Baselines for the vendor payment file and control report](media/GER-BaselineAttachments.png "Screenshot of the Configurations page with the Payment XLSX control report selected")</span></span>

8. <span data-ttu-id="e3378-236">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="e3378-236">Close the page.</span></span>
9. <span data-ttu-id="e3378-237">På snabbfliken **Baslinjer** väljer du **Ny** för att konfigurera en baslinje för betalningsfilen:</span><span class="sxs-lookup"><span data-stu-id="e3378-237">On the **Baselines** FastTab, select **New** to configure a baseline for the payment file:</span></span>

    1. <span data-ttu-id="e3378-238">Namnge raden **baslinjeinställning för betalningsfil**.</span><span class="sxs-lookup"><span data-stu-id="e3378-238">Name the line **Baseline setting for payment file**.</span></span>
    2. <span data-ttu-id="e3378-239">I fältet **filkomponentnamn** väljer du **fil** för att använda den här baslinjen till ER-formatets utdata som genererar betalningsfilen i BACS (UK) textformat.</span><span class="sxs-lookup"><span data-stu-id="e3378-239">In the **File component name** field, select **file** to apply this baseline to the ER format output that generates the payment file in BACS (UK) text format.</span></span>
    3. <span data-ttu-id="e3378-240">I fältet **företag** väljer du **GBSI** för att använda denna baslinje när ER-formatet **BACS (UK)** körs i GBSI-företag.</span><span class="sxs-lookup"><span data-stu-id="e3378-240">In the **Companies** field, select **GBSI** to apply this baseline when the **BACS (UK)** ER format is run in the GBSI company.</span></span>
    4. <span data-ttu-id="e3378-241">I fältet **Filnamnsmask** anger du **\*.TXT** för att endast använda den här baslinjen till utdata för den **fil** formatkomponent som har filnamnstillägget **.txt**.</span><span class="sxs-lookup"><span data-stu-id="e3378-241">In **File name mask** field, enter **\*.TXT** to apply this baseline only to outputs of the **file** format component that have the **.txt** file name extension.</span></span>
    5. <span data-ttu-id="e3378-242">I fältet **baslinje** väljer du **TXT-fil för betalning** så att denna baslinje används för jämförelse med den genererade utdata.</span><span class="sxs-lookup"><span data-stu-id="e3378-242">In the **Baseline** field, select **Payment TXT file** so that this baseline is used for comparison with the generated output.</span></span>

10. <span data-ttu-id="e3378-243">Välj **ny** om du vill konfigurera en baslinje för kontrollrapporten:</span><span class="sxs-lookup"><span data-stu-id="e3378-243">Select **New** to configure a baseline for the control report:</span></span>

    1. <span data-ttu-id="e3378-244">Namnge raden **baslinjeinställning för kontrollrapport**.</span><span class="sxs-lookup"><span data-stu-id="e3378-244">Name the line **Baseline setting for control report**.</span></span>
    2. <span data-ttu-id="e3378-245">I fältet **filkomponentnamn** väljer du **ERVendOutPaymControlReport** för att använda den här baslinjen till ER-formatets utdata som genererar kontrollrapporten.</span><span class="sxs-lookup"><span data-stu-id="e3378-245">In the **File component name** field, select **ERVendOutPaymControlReport** to apply this baseline to the ER format output that generates the control report.</span></span>
    3. <span data-ttu-id="e3378-246">I fältet **företag** väljer du **GBSI** för att använda denna baslinje när ER-formatet **BACS (UK)** körs i GBSI-företag.</span><span class="sxs-lookup"><span data-stu-id="e3378-246">In the **Companies** field, select **GBSI** to apply this baseline when the **BACS (UK)** ER format is run in the GBSI company.</span></span>
    4. <span data-ttu-id="e3378-247">I fältet **Filnamnsmask** anger du **\*.XLSX** för att endast använda den här baslinjen till utdata för den **ERVendOutPaymControlReport** formatkomponent som har filnamnstillägget **.xslx**.</span><span class="sxs-lookup"><span data-stu-id="e3378-247">In **File name mask** field, enter **\*.XLSX** to apply this baseline only to outputs of the **ERVendOutPaymControlReport** format component that have the **.xslx** file name extension.</span></span>
    5. <span data-ttu-id="e3378-248">I fältet **baslinje** väljer du **XLSX-kontrollrapport för betalning** så att denna baslinje används för jämförelse med den genererade utdata.</span><span class="sxs-lookup"><span data-stu-id="e3378-248">In the **Baseline** field, select **Payment XLSX control report** so that this baseline is used for comparison with the generated output.</span></span>

    <span data-ttu-id="e3378-249">![Snabbfliken Baslinjer på sidan Konfigurationer](media/GER-BaselineRules.png "Skärmbild av snabbfliken Baslinjer på sidan Konfigurationer")</span><span class="sxs-lookup"><span data-stu-id="e3378-249">![Baselines FastTab on the Configurations page](media/GER-BaselineRules.png "Screenshot of the Baselines FastTab on the Configurations page")</span></span>

## <a name="record-tests-to-validate-vendor-payment-processing"></a><span data-ttu-id="e3378-250">Registrera tester för att validera bearbetning av leverantörsbetalning</span><span class="sxs-lookup"><span data-stu-id="e3378-250">Record tests to validate vendor payment processing</span></span>

<span data-ttu-id="e3378-251">Som funktionell priviligierad användare kan du registrera dina egna steg för att testa bearbetning av leverantörsbetalning.</span><span class="sxs-lookup"><span data-stu-id="e3378-251">As a functional power user, you can record your own steps to test vendor payment processing.</span></span> <span data-ttu-id="e3378-252">Vi rekommenderar att du spelar upp (och redigerar, efter behov) uppgiftsinspelningen **förbereda\\inspelning.xml** som du hämtade tidigare.</span><span class="sxs-lookup"><span data-stu-id="e3378-252">We recommend that you play (and edit, as required) the **Prepare\\Recording.xml** task recording that you downloaded earlier.</span></span> <span data-ttu-id="e3378-253">Den här inspelningen används för att ställa in alla testdata till rätt tillstånd.</span><span class="sxs-lookup"><span data-stu-id="e3378-253">This recording is used to set all testing data to the correct state.</span></span> <span data-ttu-id="e3378-254">Det steget är nödvändigt eftersom testningen kan utföras många gånger, och varje test måste använda data som är i samma tillstånd.</span><span class="sxs-lookup"><span data-stu-id="e3378-254">That step is required because the testing can be done many times, and every test must use data that is in the same state.</span></span>

### <a name="reset-user-settings"></a><span data-ttu-id="e3378-255">Återställ användarinställningar</span><span class="sxs-lookup"><span data-stu-id="e3378-255">Reset user settings</span></span>

1. <span data-ttu-id="e3378-256">Öppna standardinstrumentpanelen.</span><span class="sxs-lookup"><span data-stu-id="e3378-256">Open the default dashboard.</span></span>
2. <span data-ttu-id="e3378-257">Välj knappen **inställningar** (kugghjulssymbolen).</span><span class="sxs-lookup"><span data-stu-id="e3378-257">Select the **Settings** button (the gear symbol).</span></span>
3. <span data-ttu-id="e3378-258">Välj **Användaralternativ**.</span><span class="sxs-lookup"><span data-stu-id="e3378-258">Select **User options**.</span></span>
4. <span data-ttu-id="e3378-259">Välj **Användardata**</span><span class="sxs-lookup"><span data-stu-id="e3378-259">Select **Usage data**.</span></span>
5. <span data-ttu-id="e3378-260">Välj **Återställ**.</span><span class="sxs-lookup"><span data-stu-id="e3378-260">Select **Reset**.</span></span>
6. <span data-ttu-id="e3378-261">Välj **ja** för att bekräfta att du vill återställa användardata.</span><span class="sxs-lookup"><span data-stu-id="e3378-261">Select **Yes** to confirm that you want to reset usage data.</span></span>
7. <span data-ttu-id="e3378-262">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="e3378-262">Close the page.</span></span>

### <a name="record-the-steps-to-prepare-data-for-testing"></a><span data-ttu-id="e3378-263">Registrera stegen för att förbereda data för testning</span><span class="sxs-lookup"><span data-stu-id="e3378-263">Record the steps to prepare data for testing</span></span>

1. <span data-ttu-id="e3378-264">Välj knappen **inställningar** (kugghjulssymbolen).</span><span class="sxs-lookup"><span data-stu-id="e3378-264">Select the **Settings** button (the gear symbol).</span></span>
2. <span data-ttu-id="e3378-265">Välj **uppgiftsregistrering**.</span><span class="sxs-lookup"><span data-stu-id="e3378-265">Select **Task recorder**.</span></span>
3. <span data-ttu-id="e3378-266">Välj **Spela upp inspelning**.</span><span class="sxs-lookup"><span data-stu-id="e3378-266">Select **Playback recording**.</span></span>
4. <span data-ttu-id="e3378-267">Välj **Öppna från datorn**.</span><span class="sxs-lookup"><span data-stu-id="e3378-267">Select **Open from this PC**.</span></span>
5. <span data-ttu-id="e3378-268">Välj **bläddra** och markera den lokalt sparade filen **Förbered\\inspelning.xml**.</span><span class="sxs-lookup"><span data-stu-id="e3378-268">Select **Browse**, and select the locally save **Prepare\\Recording.xml** file.</span></span>
6. <span data-ttu-id="e3378-269">Välj **start**.</span><span class="sxs-lookup"><span data-stu-id="e3378-269">Select **Start**.</span></span>
7. <span data-ttu-id="e3378-270">Fortsätt välja **Spela upp nästa väntande steg** tills alla steg i inspelningen har spelats upp.</span><span class="sxs-lookup"><span data-stu-id="e3378-270">Keep selecting **Play next pending step** until all the steps in the recording have been played.</span></span>

<span data-ttu-id="e3378-271">Den här uppgiftsinspelningen utför följande åtgärder:</span><span class="sxs-lookup"><span data-stu-id="e3378-271">This task recording performs the following actions:</span></span>

1. <span data-ttu-id="e3378-272">Ställ in status för den bearbetade betalningsraden till **ingen**.</span><span class="sxs-lookup"><span data-stu-id="e3378-272">Set the status of the processed payment line to **None**.</span></span>

    <span data-ttu-id="e3378-273">![Uppgiftsinspelning av steg 3 till 4](media/GER-Recording1Review1.png "Skärmbild av uppgiftsinspelning steg 3 till 4")</span><span class="sxs-lookup"><span data-stu-id="e3378-273">![Task recording steps 3 through 4](media/GER-Recording1Review1.png "Screenshot of task recording steps 3 through 4")</span></span>

2. <span data-ttu-id="e3378-274">Aktivera ER-användarparametern **kör i felsökningsläge**.</span><span class="sxs-lookup"><span data-stu-id="e3378-274">Turn on the **Run in debug mode** ER user parameter.</span></span>

    <span data-ttu-id="e3378-275">![Uppgiftsinspelning av steg 9 till 10](media/GER-Recording1Review2.png "Skärmbild av uppgiftsinspelning steg 9 till 10")</span><span class="sxs-lookup"><span data-stu-id="e3378-275">![Task recording steps 9 through 10](media/GER-Recording1Review2.png "Screenshot of task recording steps 9 through 10")</span></span>

3. <span data-ttu-id="e3378-276">Rensa upp ER-felsökningsloggen som innehåller resultaten av jämförelsen mellan skapade filer till baslinjer.</span><span class="sxs-lookup"><span data-stu-id="e3378-276">Clean up the ER debug log that contains the results of the comparison of generated files to baselines.</span></span>

    <span data-ttu-id="e3378-277">![Uppgiftsinspelning av steg 13 till 15](media/GER-Recording1Review3.png "Skärmbild av uppgiftsinspelning steg 13 till 15")</span><span class="sxs-lookup"><span data-stu-id="e3378-277">![Task recording steps 13 through 15](media/GER-Recording1Review3.png "Screenshot of task recording steps 13 through 15")</span></span>

### <a name="record-the-steps-to-test-vendor-payment-processing"></a><span data-ttu-id="e3378-278">Registrera stegen för att testa bearbetning av leverantörsbetalning</span><span class="sxs-lookup"><span data-stu-id="e3378-278">Record the steps to test vendor payment processing</span></span>

<span data-ttu-id="e3378-279">Vi rekommenderar att du spelar upp (och redigerar, efter behov) uppgiftsinspelningen **bearbeta\\inspelning.xml** som du hämtade tidigare.</span><span class="sxs-lookup"><span data-stu-id="e3378-279">We recommend that you play (and edit, as required) the **Process\\Recording.xml** task recording that you downloaded earlier.</span></span> <span data-ttu-id="e3378-280">Den här registreringen används för att bearbeta leverantörsbetalningar och validera resultaten av jämförelsen av genererade dokument till motsvarande baslinjer.</span><span class="sxs-lookup"><span data-stu-id="e3378-280">This recording is used to process vendor payments and validate the results of the comparison of generated documents to corresponding baselines.</span></span>

1. <span data-ttu-id="e3378-281">Välj knappen **inställningar** (kugghjulssymbolen).</span><span class="sxs-lookup"><span data-stu-id="e3378-281">Select the **Settings** button (the gear symbol).</span></span>
2. <span data-ttu-id="e3378-282">Välj **uppgiftsregistrering**.</span><span class="sxs-lookup"><span data-stu-id="e3378-282">Select **Task recorder**.</span></span>
3. <span data-ttu-id="e3378-283">Välj **Spela upp inspelning**.</span><span class="sxs-lookup"><span data-stu-id="e3378-283">Select **Playback recording**.</span></span>
4. <span data-ttu-id="e3378-284">Välj **Öppna från datorn**.</span><span class="sxs-lookup"><span data-stu-id="e3378-284">Select **Open from this PC**.</span></span>
5. <span data-ttu-id="e3378-285">Välj **bläddra** och markera den lokalt sparade filen **Bearbeta\\inspelning.xml**.</span><span class="sxs-lookup"><span data-stu-id="e3378-285">Select **Browse**, and select the locally saved **Process\\Recording.xml** file.</span></span>
6. <span data-ttu-id="e3378-286">Välj **start**.</span><span class="sxs-lookup"><span data-stu-id="e3378-286">Select **Start**.</span></span>
7. <span data-ttu-id="e3378-287">Fortsätt välja **Spela upp nästa väntande steg** tills alla steg i inspelningen har spelats upp.</span><span class="sxs-lookup"><span data-stu-id="e3378-287">Keep selecting **Play next pending step** until all the steps in the recording have been played.</span></span>

<span data-ttu-id="e3378-288">Den här uppgiftsinspelningen utför följande åtgärder:</span><span class="sxs-lookup"><span data-stu-id="e3378-288">This task recording performs the following actions:</span></span>

1. <span data-ttu-id="e3378-289">Starta bearbetning av leverantörsbetalningar</span><span class="sxs-lookup"><span data-stu-id="e3378-289">Start vendor payment processing.</span></span>
2. <span data-ttu-id="e3378-290">Välj korrekta körningsparametrar och aktivera genereringen av en kontrollrapport.</span><span class="sxs-lookup"><span data-stu-id="e3378-290">Select the correct runtime parameters, and turn on generation of a control report.</span></span>

    <span data-ttu-id="e3378-291">![Uppgiftsinspelning av steg 3 till 8](media/GER-Recording2Review1.png "Skärmbild av uppgiftsinspelning steg 3 till 8")</span><span class="sxs-lookup"><span data-stu-id="e3378-291">![Task recording steps 3 through 8](media/GER-Recording2Review1.png "Screenshot of task recording steps 3 through 8")</span></span>

3. <span data-ttu-id="e3378-292">Få åtkomst till ER-felsökningsloggen för att spela in av jämförelsen mellan skapade utdata till motsvarande baslinjer.</span><span class="sxs-lookup"><span data-stu-id="e3378-292">Access the ER debug log to record the results of the comparison of generated outputs to corresponding baselines.</span></span>

    <span data-ttu-id="e3378-293">I ER-felsökningsloggen visas resultatet av jämförelsen i fältet **Genererad text**.</span><span class="sxs-lookup"><span data-stu-id="e3378-293">In the ER debug log, the results of the comparison appear in the **Generated text** field.</span></span> <span data-ttu-id="e3378-294">Fälten **Formatkomponent** och **Formatsökväg som orsakade en loggpost** refererar till den filkomponent för vilken den genererade utdata har jämförts med baslinjen.</span><span class="sxs-lookup"><span data-stu-id="e3378-294">The **Format component** and **Format path that caused a log entry** fields refer to the file component for which the generated output has been compared to the baseline.</span></span>

    <span data-ttu-id="e3378-295">![Poster på sidan elektronisk rapportering körningsloggarna](media/GER-ERDebugLog.png "Skärmbild av poster i körningsloggar för elektronisk rapportering")</span><span class="sxs-lookup"><span data-stu-id="e3378-295">![Entries on the Electronic reporting run logs page](media/GER-ERDebugLog.png "Screenshot of entries on the Electronic reporting run logs page")</span></span>

4. <span data-ttu-id="e3378-296">Jämförelsen mellan aktuella utdata för baslinjen registreras genom att du **validerar** alternativet uppgiftsinspelaren och väljer **aktuellt värde**.</span><span class="sxs-lookup"><span data-stu-id="e3378-296">The comparison of the current output to the baseline is recorded by using the **Validate** Task recorder option and selecting  **Current Value**.</span></span>

    <span data-ttu-id="e3378-297">![Använda alternativet Validera för jämförelse med det aktuella värdet](media/GER-TRRecordValidation.png "Skärmbild för användning av alternativet Validera för jämförelse med det aktuella värdet")</span><span class="sxs-lookup"><span data-stu-id="e3378-297">![Using the Validate option for comparison with the current value](media/GER-TRRecordValidation.png "Screenshot of using the Validate option for comparison with the current value")</span></span>

    <span data-ttu-id="e3378-298">Följande illustration visar hur de inspelade valideringsstegen ser ut i uppgiftsinspelningen.</span><span class="sxs-lookup"><span data-stu-id="e3378-298">The following illustration shows what the recorded validation steps look like in the task recording.</span></span>

    <span data-ttu-id="e3378-299">![Uppgiftsinspelning av steg 13 till 15](media/GER-Recording2Review2.png "Skärmbild av uppgiftsinspelning steg 13 till 15")</span><span class="sxs-lookup"><span data-stu-id="e3378-299">![Task recording steps 13 and 15](media/GER-Recording2Review2.png "Screenshot of task recording steps 13 and 15")</span></span>

## <a name="add-the-recorded-tests-to-azure-devops"></a><span data-ttu-id="e3378-300">Lägg till de registrerade testerna i Azure DevOps</span><span class="sxs-lookup"><span data-stu-id="e3378-300">Add the recorded tests to Azure DevOps</span></span>

1. <span data-ttu-id="e3378-301">Öppna Azure DevOps-miljön.</span><span class="sxs-lookup"><span data-stu-id="e3378-301">Open the Azure DevOps environment.</span></span>
2. <span data-ttu-id="e3378-302">Välj det projekt som du definierade i RSAT-parametrarna när du [konfigurerade verktyget](#prerequisites).</span><span class="sxs-lookup"><span data-stu-id="e3378-302">Select the project that you defined in the RSAT parameters when you [configured the tool](#prerequisites).</span></span>
3. <span data-ttu-id="e3378-303">Välj den testplan som du definierade i RSAT-parametrarna när du [konfigurerade verktyget](#prerequisites).</span><span class="sxs-lookup"><span data-stu-id="e3378-303">Select the test plan that you defined in the RSAT parameters when you [configured the tool](#prerequisites).</span></span>
4. <span data-ttu-id="e3378-304">Skapa ett nytt testfall för den valda testplanen:</span><span class="sxs-lookup"><span data-stu-id="e3378-304">Create a new test case for the selected test plan:</span></span>

    1. <span data-ttu-id="e3378-305">Namnge testfallet **Förbered data för testbearbetning av leverantörens elektroniska betalning**.</span><span class="sxs-lookup"><span data-stu-id="e3378-305">Name the test case **Prepare data to test processing of vendor's electronic payment**.</span></span>
    2. <span data-ttu-id="e3378-306">Bifoga filen **Inspelning.xml** från mappen **Förbered** som du hämtade tidigare.</span><span class="sxs-lookup"><span data-stu-id="e3378-306">Attach the **Recording.xml** file from the **Prepare** folder that you downloaded earlier.</span></span>

5. <span data-ttu-id="e3378-307">Skapa ett nytt testfall för den valda testplanen:</span><span class="sxs-lookup"><span data-stu-id="e3378-307">Create a new test case for the selected test plan:</span></span>

    1. <span data-ttu-id="e3378-308">Namnge testfallet **Testa bearbetning av leverantörsbetalningar genom att använda ER-formatet BACS (UK)**.</span><span class="sxs-lookup"><span data-stu-id="e3378-308">Name the test case **Test processing of vendor payments by using ER format BACS (UK)**.</span></span>
    2. <span data-ttu-id="e3378-309">Bifoga filen **Inspelning.xml** från mappen **Bearbeta** som du hämtade tidigare.</span><span class="sxs-lookup"><span data-stu-id="e3378-309">Attach the **Recording.xml** file from the **Process** folder that you downloaded earlier.</span></span>

    <span data-ttu-id="e3378-310">![Nytt testärende för den valda testplanen](media/GER-RSAT-DevOps-Tests-Passed.png "Skärmbild av nya testärenden för den valda testplanen")</span><span class="sxs-lookup"><span data-stu-id="e3378-310">![New test cases for the selected test plan](media/GER-RSAT-DevOps-Tests-Passed.png "Screenshot of the new test cases for the selected test plan")</span></span>

> [!NOTE]
> <span data-ttu-id="e3378-311">Var uppmärksam på korrekt körningsordning för de tester som läggs till.</span><span class="sxs-lookup"><span data-stu-id="e3378-311">Pay attention to the correct execution order of the tests that are added.</span></span>

## <a name="prepare-rsat-to-run-the-recorded-tests"></a><span data-ttu-id="e3378-312">Förbered RSAT för körning av de registrerade testerna</span><span class="sxs-lookup"><span data-stu-id="e3378-312">Prepare RSAT to run the recorded tests</span></span>

### <a name="load-the-tests-from-azure-devops-to-rsat"></a><span data-ttu-id="e3378-313">Läs in testerna från Azure DevOps till RSAT</span><span class="sxs-lookup"><span data-stu-id="e3378-313">Load the tests from Azure DevOps to RSAT</span></span>

1. <span data-ttu-id="e3378-314">Öppna det lokala programmet för RSAT i den aktuella topologin.</span><span class="sxs-lookup"><span data-stu-id="e3378-314">Open the local RSAT application in the current topology.</span></span>
2. <span data-ttu-id="e3378-315">Välj **Läs in** för att läsa in testerna som för närvarande finns i Azure DevOps i RSAT.</span><span class="sxs-lookup"><span data-stu-id="e3378-315">Select **Load** to load the tests that currently reside in Azure DevOps into RSAT.</span></span>

    <span data-ttu-id="e3378-316">![Tester som lästs in i RSAT](media/GER-RSAT-RSAT-Tests-Loaded.png "Skärmbild av de tester som har lästs in i RSAT")</span><span class="sxs-lookup"><span data-stu-id="e3378-316">![Tests loaded into RSAT](media/GER-RSAT-RSAT-Tests-Loaded.png "Screenshot of the tests loaded into RSAT")</span></span>

### <a name="create-automation-and-parameters-files"></a><span data-ttu-id="e3378-317">Skapa automatisering och parameterfiler</span><span class="sxs-lookup"><span data-stu-id="e3378-317">Create automation and parameters files</span></span>

1. <span data-ttu-id="e3378-318">Välj testerna som du har läst in från Azure DevOps i RSAT.</span><span class="sxs-lookup"><span data-stu-id="e3378-318">In RSAT, select the tests that you loaded from Azure DevOps.</span></span>
2. <span data-ttu-id="e3378-319">Välj **Ny** för att skapa RSAT automatisering och parameterfiler.</span><span class="sxs-lookup"><span data-stu-id="e3378-319">Select **New** to create RSAT automation and parameters files.</span></span>

    <span data-ttu-id="e3378-320">![RSAT automatisering och parameterfiler som skapats i RSAT](media/GER-RSAT-RSAT-Tests-Initiated.png "Skärmbild av RSAT automatisering och parameterfiler som skapats i RSAT")</span><span class="sxs-lookup"><span data-stu-id="e3378-320">![RSAT automation and parameters files created in RSAT](media/GER-RSAT-RSAT-Tests-Initiated.png "Screenshot of the RSAT automation and parameters files created in RSAT")</span></span>

### <a name="modify-the-parameters-files"></a><span data-ttu-id="e3378-321">Ändra parameterfilerna</span><span class="sxs-lookup"><span data-stu-id="e3378-321">Modify the parameters files</span></span>

1. <span data-ttu-id="e3378-322">I RSAT namnger du testfallet **Förbered data för testbearbetning av leverantörens elektroniska betalning**.</span><span class="sxs-lookup"><span data-stu-id="e3378-322">In RSAT, select the **Prepare data to test processing of vendor's electronic payment** test case.</span></span>
2. <span data-ttu-id="e3378-323">Välj **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="e3378-323">Select **Edit**.</span></span>
3. <span data-ttu-id="e3378-324">I Microsoft Excel-arbetsbok som är öppen, i kalkylbladet **allmänt** ändrar du företagskoden till **GBSI**, eftersom detta företag kommer att användas för testkörningen.</span><span class="sxs-lookup"><span data-stu-id="e3378-324">In the Microsoft Excel workbook that is opened, on the **General** worksheet, change the company code to **GBSI**, because this company will be used for test execution.</span></span>
4. <span data-ttu-id="e3378-325">I RSAT väljer du testfallet **Testa bearbetning av leverantörsbetalningar genom att använda ER-formatet BACS (UK)**.</span><span class="sxs-lookup"><span data-stu-id="e3378-325">In RSAT, select the **Test processing of vendor payments by using ER format BACS (UK)** test case.</span></span>
5. <span data-ttu-id="e3378-326">Välj **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="e3378-326">Select **Edit**.</span></span>
6. <span data-ttu-id="e3378-327">I den Excel-arbetsbok som är öppen, i kalkylbladet **allmänt** ändrar du företagskoden till **GBSI**.</span><span class="sxs-lookup"><span data-stu-id="e3378-327">In the Excel workbook that is opened, on the **General** worksheet, change the company code to **GBSI**.</span></span>
7. <span data-ttu-id="e3378-328">I kalkylbladet **ERFormatMappingRunLogTable** ska du notera att celler A:3 och C:3 innehåller texten i fälten i ER-felsökningsloggtabellen som används för att validera resultaten av jämförelsen av utdata till baslinjen.</span><span class="sxs-lookup"><span data-stu-id="e3378-328">On the **ERFormatMappingRunLogTable** worksheet, notice that cells A:3 and C:3 contain the text of the fields in the ER debug log table that are used to validate the results of the comparison of the output to the baseline.</span></span> <span data-ttu-id="e3378-329">Dessa texter används för att utvärdera ER-felsökningsloggposter som skapas under testkörningen.</span><span class="sxs-lookup"><span data-stu-id="e3378-329">These texts will be used to evaluate ER debug log records that are created during test execution.</span></span>

    <span data-ttu-id="e3378-330">![ERFormatMappingRunLogTable kalkylblad](media/GER-RSAT-RSAT-ExcelParameters.png "Skärmbild av kalkylbladet ERFormatMappingRunLogTable")</span><span class="sxs-lookup"><span data-stu-id="e3378-330">![ERFormatMappingRunLogTable worksheet](media/GER-RSAT-RSAT-ExcelParameters.png "Screenshot of the ERFormatMappingRunLogTable worksheet")</span></span>

## <a name="run-the-tests-and-analyze-the-results"></a><span data-ttu-id="e3378-331">Kör testerna och analysera resultaten</span><span class="sxs-lookup"><span data-stu-id="e3378-331">Run the tests and analyze the results</span></span>

### <a name="run-the-tests-in-rsat"></a><span data-ttu-id="e3378-332">Kör testerna i RSAT</span><span class="sxs-lookup"><span data-stu-id="e3378-332">Run the tests in RSAT</span></span>

1. <span data-ttu-id="e3378-333">Markera de inlästa testerna i RSAT.</span><span class="sxs-lookup"><span data-stu-id="e3378-333">In RSAT, select the loaded tests.</span></span>
2. <span data-ttu-id="e3378-334">Välj **kör**.</span><span class="sxs-lookup"><span data-stu-id="e3378-334">Select **Run**.</span></span>

<span data-ttu-id="e3378-335">Observera att testfall körs automatiskt i appen med hjälp av en webbläsare.</span><span class="sxs-lookup"><span data-stu-id="e3378-335">Notice that test cases are automatically run in the application by using a web browser.</span></span>

### <a name="analyze-the-results-of-test-execution"></a><span data-ttu-id="e3378-336">Analysera resultaten av testkörningen</span><span class="sxs-lookup"><span data-stu-id="e3378-336">Analyze the results of test execution</span></span>

<span data-ttu-id="e3378-337">Resultaten från testkörningen lagras i RSAT.</span><span class="sxs-lookup"><span data-stu-id="e3378-337">The results of the test execution are stored in RSAT.</span></span> <span data-ttu-id="e3378-338">Observera att båda testerna godkändes.</span><span class="sxs-lookup"><span data-stu-id="e3378-338">Notice that both tests were passed.</span></span>

<span data-ttu-id="e3378-339">![Test som har godkänts i RSAT](media/GER-RSAT-RSAT-Tests-Passed.png "Skärmbild av tester som har godkänts i RSAT")</span><span class="sxs-lookup"><span data-stu-id="e3378-339">![Tests that passed in RSAT](media/GER-RSAT-RSAT-Tests-Passed.png "Screenshot of tests that passed in RSAT")</span></span>

<span data-ttu-id="e3378-340">Observera att resultaten av testkörningen också skickas till Azure DevOps så att du kan analysera ytterligare.</span><span class="sxs-lookup"><span data-stu-id="e3378-340">Notice that the results of the test execution are also sent to Azure DevOps so that you can do further analysis.</span></span>

<span data-ttu-id="e3378-341">![Resultat från testkörningen i Azure DevOps](media/GER-RSAT-DevOps-Tests-Added.png "Skärmbild av resultaten från testkörningen i Azure DevOps")</span><span class="sxs-lookup"><span data-stu-id="e3378-341">![Results of test execution in Azure DevOps](media/GER-RSAT-DevOps-Tests-Added.png "Screenshot of the results of test execution in Azure DevOps")</span></span>

### <a name="simulate-a-situation-where-tests-fail"></a><span data-ttu-id="e3378-342">Simulera en situation där testerna misslyckas</span><span class="sxs-lookup"><span data-stu-id="e3378-342">Simulate a situation where tests fail</span></span>

<span data-ttu-id="e3378-343">Det här testpaketet måste misslyckas när minst ett av genererade utdata inte matchar motsvarande baslinje.</span><span class="sxs-lookup"><span data-stu-id="e3378-343">This test suite must fail when at least one of the generated outputs doesn't match the corresponding baseline.</span></span> <span data-ttu-id="e3378-344">För att uppnå denna situation kan du använda den härledda versionen av **BACS (UK)** som genererar en betalningsfil med annat innehåll än motsvarande baslinje.</span><span class="sxs-lookup"><span data-stu-id="e3378-344">To achieve this situation, you can use your derived version of the **BACS (UK)** format that will generate a payment file that has different content than the corresponding baseline.</span></span> <span data-ttu-id="e3378-345">Om du vill simulera den här situationen kan du använda samma **BACS (UK)**-format men ändra betalningsbeloppet på den bearbetade betalningsraden.</span><span class="sxs-lookup"><span data-stu-id="e3378-345">To simulate this situation, you can use the same **BACS (UK)** format but change the payment amount on the processed payment line.</span></span>

1. <span data-ttu-id="e3378-346">Öppna appen och gå till **Leverantörsreskontra \> Betalningar \> Betalningsjournal**.</span><span class="sxs-lookup"><span data-stu-id="e3378-346">Open the application and go to **Accounts payable \> Payments \> Payment journal**.</span></span>
2. <span data-ttu-id="e3378-347">Markera **rader**</span><span class="sxs-lookup"><span data-stu-id="e3378-347">Select **Lines**.</span></span>
3. <span data-ttu-id="e3378-348">Markera betalningsraden och välj **betalningsstatus \> ingen**.</span><span class="sxs-lookup"><span data-stu-id="e3378-348">Select the payment line, and then select **Payment status \> None**.</span></span>
4. <span data-ttu-id="e3378-349">I fältet **Debet**, ändra värdet från **1 000,00** till **2 000,00**.</span><span class="sxs-lookup"><span data-stu-id="e3378-349">In the **Debit** field, change the value from **1,000.00** to **2,000.00**.</span></span>
5. <span data-ttu-id="e3378-350">Spara ändringarna genom att klicka på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="e3378-350">Select **Save** to save your changes.</span></span>

### <a name="run-the-tests-in-rsat"></a><span data-ttu-id="e3378-351">Kör testerna i RSAT</span><span class="sxs-lookup"><span data-stu-id="e3378-351">Run the tests in RSAT</span></span>

1. <span data-ttu-id="e3378-352">Markera de inlästa testerna i RSAT.</span><span class="sxs-lookup"><span data-stu-id="e3378-352">In RSAT, select the loaded tests.</span></span>
2. <span data-ttu-id="e3378-353">Välj **kör**.</span><span class="sxs-lookup"><span data-stu-id="e3378-353">Select **Run**.</span></span>

<span data-ttu-id="e3378-354">Observera att testfall körs automatiskt i appen med hjälp av en webbläsare.</span><span class="sxs-lookup"><span data-stu-id="e3378-354">Notice that test cases are automatically run in the application by using a web browser.</span></span>

### <a name="analyze-the-results-of-test-execution"></a><span data-ttu-id="e3378-355">Analysera resultaten av testkörningen</span><span class="sxs-lookup"><span data-stu-id="e3378-355">Analyze the results of test execution</span></span>

<span data-ttu-id="e3378-356">Resultaten från testkörningen lagras i RSAT.</span><span class="sxs-lookup"><span data-stu-id="e3378-356">The results of the test execution are stored in RSAT.</span></span> <span data-ttu-id="e3378-357">Observera att det andra testet misslyckades under det andra körningsförsöket.</span><span class="sxs-lookup"><span data-stu-id="e3378-357">Notice that the second test failed during the second execution.</span></span>

<span data-ttu-id="e3378-358">![Misslyckade testresultat i RSAT](media/GER-RSAT-RSAT-Tests-Failed.png "Skärmbild av misslyckade testresultaten i RSAT")</span><span class="sxs-lookup"><span data-stu-id="e3378-358">![Failed test results in RSAT](media/GER-RSAT-RSAT-Tests-Failed.png "Screenshot of the failed test results in RSAT")</span></span>

<span data-ttu-id="e3378-359">Observera att resultaten av testkörningen också skickas till Azure DevOps så att du kan analysera ytterligare.</span><span class="sxs-lookup"><span data-stu-id="e3378-359">Notice that the results of the test execution are also sent to Azure DevOps so that you can do further analysis.</span></span>

<span data-ttu-id="e3378-360">![Misslyckade testresultat i Azure DevOps](media/GER-RSAT-DevOps-Tests-Failed.png "Skärmbild av misslyckade testresultaten i Azure DevOps")</span><span class="sxs-lookup"><span data-stu-id="e3378-360">![Failed test results in Azure DevOps](media/GER-RSAT-DevOps-Tests-Failed.png "Screenshot of the failed test results in Azure DevOps")</span></span>

<span data-ttu-id="e3378-361">Du får tillgång till status för varje test.</span><span class="sxs-lookup"><span data-stu-id="e3378-361">You can access the status of each test.</span></span> <span data-ttu-id="e3378-362">Du kan också komma åt körningsloggen så att du analyserar orsakerna till eventuella fel.</span><span class="sxs-lookup"><span data-stu-id="e3378-362">You can also access the execution log so that you analyze the reasons for any failure.</span></span> <span data-ttu-id="e3378-363">I följande bild visar körningsloggen att felet uppstod på grund av skillnaden mellan den genererade betalningsfilen och dess baslinje.</span><span class="sxs-lookup"><span data-stu-id="e3378-363">In the following illustration, the execution log shows that the failure occurred because of the difference in content between the generated payment file and its baseline.</span></span>

<span data-ttu-id="e3378-364">![Körningslogg för analys av fel i Azure DevOps](media/GER-RSAT-DevOps-Tests-Failed-Log.png "Skärmbild av körningsloggen för att analysera fel i Azure DevOps")</span><span class="sxs-lookup"><span data-stu-id="e3378-364">![Execution log for analyzing failure in Azure DevOps](media/GER-RSAT-DevOps-Tests-Failed-Log.png "Screenshot of the execution log for analyzing failure in Azure DevOps")</span></span>

<span data-ttu-id="e3378-365">Som du har sett kan funktionen för ett ER-format utvärderas automatiskt med hjälp av RSAT som testplattform och med hjälp av testfall som baseras på uppgiftsinspelare som använder funktionen för ER-baslinje.</span><span class="sxs-lookup"><span data-stu-id="e3378-365">Therefore, as you've seen, the functioning of any ER format can be evaluated automatically by using RSAT as the testing platform and by using Task recorder-based test cases that use the ER baseline feature.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="e3378-366">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="e3378-366">Additional resources</span></span>

- [<span data-ttu-id="e3378-367">Uppgiftsinspelarresurser</span><span class="sxs-lookup"><span data-stu-id="e3378-367">Task recorder resources</span></span>](../user-interface/task-recorder.md)
- [<span data-ttu-id="e3378-368">Regression Suite Automation Tool</span><span class="sxs-lookup"><span data-stu-id="e3378-368">Regression suite automation tool</span></span>](https://www.microsoft.com/download/details.aspx?id=57357)
- [<span data-ttu-id="e3378-369">Skapa och automatisera användaracceptanstest</span><span class="sxs-lookup"><span data-stu-id="e3378-369">Create and automate user acceptance tests</span></span>](../lifecycle-services/using-task-guides-and-bpm-to-create-user-acceptance-tests.md)
- [<span data-ttu-id="e3378-370">Distribuera och använd miljöer som har stöd för kontinuerlig bygg- och testautomatisering</span><span class="sxs-lookup"><span data-stu-id="e3378-370">Deploy and use an environment that supports continuous build and test automation</span></span>](../perf-test/continuous-build-test-automation.md)
- [<span data-ttu-id="e3378-371">Spåra genererade rapportresultat och jämför dem med baslinjevärden</span><span class="sxs-lookup"><span data-stu-id="e3378-371">Trace generated report results and compare them with baseline values</span></span>](er-trace-reports-compare-baseline.md)
- [<span data-ttu-id="e3378-372">ER Uppgradera ditt format genom att implementera en ny basversion för det formatet</span><span class="sxs-lookup"><span data-stu-id="e3378-372">ER Upgrade your format by adopting a new, base version of that format</span></span>](tasks/er-upgrade-format.md)
- [<span data-ttu-id="e3378-373">ER importera en konfiguration från Lifecycle Services</span><span class="sxs-lookup"><span data-stu-id="e3378-373">ER Import a configuration from Lifecycle Services</span></span>](tasks/er-import-configuration-lifecycle-services.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]