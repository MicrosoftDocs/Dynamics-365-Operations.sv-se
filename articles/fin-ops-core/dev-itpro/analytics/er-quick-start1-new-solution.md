---
title: Skapa en ny ER-lösning för att skriva ut en egen rapport
description: I det här avsnittet beskrivs hur du utformar en elektronisk rapporteringslösning (ER) för att skriva ut en egen rapport.
author: NickSelin
manager: AnnBe
ms.date: 08/10/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, ERParameters, ERDataModelDesigner, ERModelMappingTable, ERModelMappingDesigner, EROperationDesigner, ERVendorTable
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: 220314
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: c5bbfae36fb15437f2baadc66663cbfdb28691e8
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/09/2021
ms.locfileid: "5562621"
---
# <a name="design-a-new-er-solution-to-print-a-custom-report"></a><span data-ttu-id="e9013-103">Skapa en ny ER-lösning för att skriva ut en egen rapport</span><span class="sxs-lookup"><span data-stu-id="e9013-103">Design a new ER solution to print a custom report</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="e9013-104">Följande steg beskriver hur en roll för användare i en systemadministratör, elektronisk rapportutvecklare eller en funktionell konsult för elektronisk rapportering kan konfigurera parametrar för ER-ramverk, utforma nödvändiga ER-konfigurationer för en ny ER-lösning för att komma åt data i en viss affärsdomän och skapa en anpassad rapport i Microsoft Office-formatet.</span><span class="sxs-lookup"><span data-stu-id="e9013-104">The following steps explain how a user in the System Administrator, Electronic Reporting Developer, or Electronic Reporting Functional Consultant role can configure parameters of the ER framework, design the required ER configurations of a new ER solution to access the data of a particular business domain, and generate a custom report in Microsoft Office format.</span></span> <span data-ttu-id="e9013-105">Dessa steg kan slutföras i **USMF**-företaget.</span><span class="sxs-lookup"><span data-stu-id="e9013-105">These steps can be completed in the **USMF** company.</span></span>

- [<span data-ttu-id="e9013-106">Konfigurera ER-ramverket</span><span class="sxs-lookup"><span data-stu-id="e9013-106">Configure the ER framework</span></span>](#ConfigureFramework)

    - [<span data-ttu-id="e9013-107">Konfigurera ER-parametrar</span><span class="sxs-lookup"><span data-stu-id="e9013-107">Configure ER parameters</span></span>](#ConfigureParameters)
    - [<span data-ttu-id="e9013-108">Aktivera en ER-konfigurationsleverantör</span><span class="sxs-lookup"><span data-stu-id="e9013-108">Activate an ER configuration provider</span></span>](#ActivateProvider)

        - [<span data-ttu-id="e9013-109">Granska listan med ER-konfigurationsleverantörer</span><span class="sxs-lookup"><span data-stu-id="e9013-109">Review the list of ER configuration providers</span></span>](#ReviewProvidersList)
        - [<span data-ttu-id="e9013-110">Lägg till en ny ER-konfigurationsleverantör</span><span class="sxs-lookup"><span data-stu-id="e9013-110">Add a new ER configuration provider</span></span>](#AddProvider)
        - [<span data-ttu-id="e9013-111">Aktivera en ER-konfigurationsleverantör</span><span class="sxs-lookup"><span data-stu-id="e9013-111">Activate an ER configuration provider</span></span>](#ActivateAddedProvider)

- [<span data-ttu-id="e9013-112">Utforma domänspecifik datamodell</span><span class="sxs-lookup"><span data-stu-id="e9013-112">Design a domain-specific data model</span></span>](#DesignModel)

    - [<span data-ttu-id="e9013-113">Importera en ny konfiguration för datamodell</span><span class="sxs-lookup"><span data-stu-id="e9013-113">Import a new data model configuration</span></span>](#ImportDataModel)
    - [<span data-ttu-id="e9013-114">Skapa en ny datamodellskonfiguration</span><span class="sxs-lookup"><span data-stu-id="e9013-114">Create a new data model configuration</span></span>](#DesignDataModel)

        - [<span data-ttu-id="e9013-115">Namnge och datamodellen</span><span class="sxs-lookup"><span data-stu-id="e9013-115">Name the data model</span></span>](#NameDataModel)
        - [<span data-ttu-id="e9013-116">Lägg till fält för datamodell</span><span class="sxs-lookup"><span data-stu-id="e9013-116">Add data model fields</span></span>](#FieldsEntry)
        - [<span data-ttu-id="e9013-117">Färdigställa datamodellens utformning</span><span class="sxs-lookup"><span data-stu-id="e9013-117">Complete the design of the data model</span></span>](#CompleteDataModel)

- [<span data-ttu-id="e9013-118">Designa en modellmappning för den konfigurerade datamodellen</span><span class="sxs-lookup"><span data-stu-id="e9013-118">Design a model mapping for the configured data model</span></span>](#DesignMapping)

    - [<span data-ttu-id="e9013-119">Importera en ny konfiguration för modellmappning</span><span class="sxs-lookup"><span data-stu-id="e9013-119">Import a new model mapping configuration</span></span>](#ImportModelMapping)
    - [<span data-ttu-id="e9013-120">Skapa en ny konfiguration av modellmappning</span><span class="sxs-lookup"><span data-stu-id="e9013-120">Create a new model mapping configuration</span></span>](#CreateModelMapping)

        - [<span data-ttu-id="e9013-121">Designa en ny modellmappningskomponent</span><span class="sxs-lookup"><span data-stu-id="e9013-121">Design a new model mapping component</span></span>](#DesignMappingComponent)
        - [<span data-ttu-id="e9013-122">Lägga till datakällor för att öppna programtabeller</span><span class="sxs-lookup"><span data-stu-id="e9013-122">Add data sources to access application tables</span></span>](#AddMmDataSource1)
        - [<span data-ttu-id="e9013-123">Lägga till datakällor för att öppna programuppräkningar</span><span class="sxs-lookup"><span data-stu-id="e9013-123">Add data sources to access application enumerations</span></span>](#AddMmDataSource2)
        - [<span data-ttu-id="e9013-124">Lägga till ER-etiketter för att generera en rapport på ett angivet språk</span><span class="sxs-lookup"><span data-stu-id="e9013-124">Add ER labels to generate a report in a specified language</span></span>](#AddMmLabels)
        - [<span data-ttu-id="e9013-125">Lägga till en datakälla som transformerar resultaten från att jämföra uppräkningsvärden till ett textvärde</span><span class="sxs-lookup"><span data-stu-id="e9013-125">Add a data source to transform the results of comparing enumeration values to a text value</span></span>](#AddMmDataSource3)
        - [<span data-ttu-id="e9013-126">Binda datakällor till fält för datamodell</span><span class="sxs-lookup"><span data-stu-id="e9013-126">Bind data sources to data model fields</span></span>](#AddMmBindings1)
        - [<span data-ttu-id="e9013-127">Färdigställa modellmappningens utformning</span><span class="sxs-lookup"><span data-stu-id="e9013-127">Complete the design of the model mapping</span></span>](#CompleteModelMapping)

- [<span data-ttu-id="e9013-128">Utforma en mall för en anpassad rapport</span><span class="sxs-lookup"><span data-stu-id="e9013-128">Design a template for a custom report</span></span>](#DesignReportTemplate)
- [<span data-ttu-id="e9013-129">Designa ett format</span><span class="sxs-lookup"><span data-stu-id="e9013-129">Design a format</span></span>](#DesignFormat)

    - [<span data-ttu-id="e9013-130">Importera en utformad formatkonfiguration</span><span class="sxs-lookup"><span data-stu-id="e9013-130">Import a designed format configuration</span></span>](#FormatImport)
    - [<span data-ttu-id="e9013-131">Skapa en ny formatkonfiguration</span><span class="sxs-lookup"><span data-stu-id="e9013-131">Create a new format configuration</span></span>](#FormatCreate)

        - [<span data-ttu-id="e9013-132">Importera rapportmall</span><span class="sxs-lookup"><span data-stu-id="e9013-132">Import a report template</span></span>](#ImportReportTemplate)
        - [<span data-ttu-id="e9013-133">Konfigurera ett format</span><span class="sxs-lookup"><span data-stu-id="e9013-133">Configure a format</span></span>](#ConfigureFormat)
        - [<span data-ttu-id="e9013-134">Definiera databindningen för en rapportrubrik</span><span class="sxs-lookup"><span data-stu-id="e9013-134">Define the data binding for a report title</span></span>](#DefineFormatBindings)
        - [<span data-ttu-id="e9013-135">Granska modellens datakälla</span><span class="sxs-lookup"><span data-stu-id="e9013-135">Review the model data source</span></span>](#ReviewModelDataSource)
        - [<span data-ttu-id="e9013-136">Binda formatelement till fält för datakällor</span><span class="sxs-lookup"><span data-stu-id="e9013-136">Bind format elements to data source fields</span></span>](#BindFormatElements)

    - [<span data-ttu-id="e9013-137">Kör ett format som skapats från ER</span><span class="sxs-lookup"><span data-stu-id="e9013-137">Run a designed format from ER</span></span>](#RunFormatFromER)

- [<span data-ttu-id="e9013-138">Justera ett utformat format</span><span class="sxs-lookup"><span data-stu-id="e9013-138">Tune a designed format</span></span>](#TuneFormat)

    - [<span data-ttu-id="e9013-139">Ändra ett format för att ändra namnet på ett skapat dokument</span><span class="sxs-lookup"><span data-stu-id="e9013-139">Modify a format to change the name of a generated document</span></span>](#ModifyToChangeName)
    - [<span data-ttu-id="e9013-140">Ändra ett format för att ändra ordning på frågorna</span><span class="sxs-lookup"><span data-stu-id="e9013-140">Modify a format to change the order of questions</span></span>](#ModifyToOrder)
    - [<span data-ttu-id="e9013-141">Kör ett ändrat format från ER</span><span class="sxs-lookup"><span data-stu-id="e9013-141">Run a modified format from ER</span></span>](#RunFormatFromER2)
    - [<span data-ttu-id="e9013-142">Slutför formatdesignen</span><span class="sxs-lookup"><span data-stu-id="e9013-142">Complete the format design</span></span>](#CompleteFormat)

- [<span data-ttu-id="e9013-143">Utveckla programartefakter för att anropa den utformade rapporten</span><span class="sxs-lookup"><span data-stu-id="e9013-143">Develop application artefacts to call the designed report</span></span>](#DevelopCustomCode)

    - [<span data-ttu-id="e9013-144">Modifiera källkod</span><span class="sxs-lookup"><span data-stu-id="e9013-144">Modify source code</span></span>](#ModifySourceCode)

        - [<span data-ttu-id="e9013-145">Lägga till en datakontraktklass</span><span class="sxs-lookup"><span data-stu-id="e9013-145">Add a data contract class</span></span>](#DataContractClass)
        - [<span data-ttu-id="e9013-146">Lägg till en UI-skaparklass</span><span class="sxs-lookup"><span data-stu-id="e9013-146">Add a UI builder class</span></span>](#UIBuilderClass)
        - [<span data-ttu-id="e9013-147">Lägga till en dataleverantörsklass</span><span class="sxs-lookup"><span data-stu-id="e9013-147">Add a data provider class</span></span>](#DataProviderClass)
        - [<span data-ttu-id="e9013-148">Lägga till en etikettfil</span><span class="sxs-lookup"><span data-stu-id="e9013-148">Add a labels file</span></span>](#LabelsFile)
        - [<span data-ttu-id="e9013-149">Lägg till en rapporttjänstklass</span><span class="sxs-lookup"><span data-stu-id="e9013-149">Add a report service class</span></span>](#ServiceClass)
        - [<span data-ttu-id="e9013-150">Lägg till en rapportkontrollantklass</span><span class="sxs-lookup"><span data-stu-id="e9013-150">Add a report controller class</span></span>](#ControllerClass)
        - [<span data-ttu-id="e9013-151">Lägg till ett menyalternativ</span><span class="sxs-lookup"><span data-stu-id="e9013-151">Add a menu item</span></span>](#MenuItem)
        - [<span data-ttu-id="e9013-152">Lägg till ett menyalternativ till en meny</span><span class="sxs-lookup"><span data-stu-id="e9013-152">Add a menu item to a menu</span></span>](#Menu)
        - [<span data-ttu-id="e9013-153">Bygga ett Visual Studio-projekt</span><span class="sxs-lookup"><span data-stu-id="e9013-153">Build a Visual Studio project</span></span>](#BuildVSProject)

    - [<span data-ttu-id="e9013-154">Kör ett format från programmet</span><span class="sxs-lookup"><span data-stu-id="e9013-154">Run a format from the application</span></span>](#RunFormatFromApp)

- [<span data-ttu-id="e9013-155">Finjustera en designad ER-lösning</span><span class="sxs-lookup"><span data-stu-id="e9013-155">Tune a designed ER solution</span></span>](#TuneSolution)

    - [<span data-ttu-id="e9013-156">Ändra modellmappning</span><span class="sxs-lookup"><span data-stu-id="e9013-156">Modify a model mapping</span></span>](#ModifyModelMapping)

        - [<span data-ttu-id="e9013-157">Lägga till datakällor för att öppna ett datakontraktobjekt</span><span class="sxs-lookup"><span data-stu-id="e9013-157">Add data sources to access a data contract object</span></span>](#AddDataSource1)
        - [<span data-ttu-id="e9013-158">Lägga till en datakälla för åtkomst av mappningsposter för ER-format</span><span class="sxs-lookup"><span data-stu-id="e9013-158">Add a data source to access ER format mapping records</span></span>](#AddDataSource2)
        - [<span data-ttu-id="e9013-159">Lägga till en datakälla för åtkomst av formatmappningsposter för ett ER-format som körs</span><span class="sxs-lookup"><span data-stu-id="e9013-159">Add a data source to access a format mapping record of a running ER format</span></span>](#AddDataSource3)
        - [<span data-ttu-id="e9013-160">Ange namnet på det ER-format som körs i datamodellen</span><span class="sxs-lookup"><span data-stu-id="e9013-160">Enter the name of the running ER format in the data model</span></span>](#AddBinding)
        - [<span data-ttu-id="e9013-161">Färdigställa modellmappningens utformning</span><span class="sxs-lookup"><span data-stu-id="e9013-161">Complete the design of the model mapping</span></span>](#CompleteModelMapping2)

    - [<span data-ttu-id="e9013-162">Ändra ett format</span><span class="sxs-lookup"><span data-stu-id="e9013-162">Modify a format</span></span>](#ModifyFormat)

        - [<span data-ttu-id="e9013-163">Lägg till ett nytt formatelement</span><span class="sxs-lookup"><span data-stu-id="e9013-163">Add a new format element</span></span>](#AddFormatElement)
        - [<span data-ttu-id="e9013-164">Bind det tillagda formatelementet</span><span class="sxs-lookup"><span data-stu-id="e9013-164">Bind the added format element</span></span>](#BindAddedFormatElement)
        - [<span data-ttu-id="e9013-165">Slutför formatdesignen</span><span class="sxs-lookup"><span data-stu-id="e9013-165">Complete the format design</span></span>](#CompleteFormat2)

    - [<span data-ttu-id="e9013-166">Kör ett format från programmet</span><span class="sxs-lookup"><span data-stu-id="e9013-166">Run a format from the application</span></span>](#RunFormatFromApp2)
    - [<span data-ttu-id="e9013-167">Kör ett format från ER</span><span class="sxs-lookup"><span data-stu-id="e9013-167">Run a format from ER</span></span>](#RunFormatFromER3)
    - [<span data-ttu-id="e9013-168">Konfigurera ett formatmål för förhandsvisning på skärmen</span><span class="sxs-lookup"><span data-stu-id="e9013-168">Configure a format destination for on-screen preview</span></span>](#ConfigureDestination)
    - [<span data-ttu-id="e9013-169">Kör ett format från programmet för att förhandsgranska det som ett PDF-dokument</span><span class="sxs-lookup"><span data-stu-id="e9013-169">Run a format from the application to preview it as a PDF document</span></span>](#RunFormatFromApp3)

- [<span data-ttu-id="e9013-170">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="e9013-170">Additional resources</span></span>](#References)

<span data-ttu-id="e9013-171">I det här exemplet ska du skapa en ny ER-lösning för modulen [enkät](https://docs.microsoft.com/dynamics365/human-resources/hr-learning-questionnaires).</span><span class="sxs-lookup"><span data-stu-id="e9013-171">In this example, you will create a new ER solution for the [Questionnaire](https://docs.microsoft.com/dynamics365/human-resources/hr-learning-questionnaires) module.</span></span> <span data-ttu-id="e9013-172">Med den nya ER-lösningen kan du utforma en rapport genom att använda ett Microsoft Excel kalkylblad som en mall.</span><span class="sxs-lookup"><span data-stu-id="e9013-172">This new ER solution lets you design a report by using a Microsoft Excel worksheet as a template.</span></span> <span data-ttu-id="e9013-173">Du kan sedan generera **enkät**-rapport i Excel-eller PDF-format, förutom att generera den befintliga rapporten från SQL Server Reporting Services (SSRS).</span><span class="sxs-lookup"><span data-stu-id="e9013-173">You can then generate the **Questionnaire** report in Excel or PDF format, in addition to generating the existing SQL Server Reporting Services (SSRS) report.</span></span> <span data-ttu-id="e9013-174">Du kan också senare ändra den nya rapporten vid begäran.</span><span class="sxs-lookup"><span data-stu-id="e9013-174">You can also modify the new report later, upon request.</span></span> <span data-ttu-id="e9013-175">Ingen kod behövs.</span><span class="sxs-lookup"><span data-stu-id="e9013-175">No coding is required.</span></span>

1. <span data-ttu-id="e9013-176">Om du vill köra den befintliga rapporten går du till **enkät** \> **design** \> **enkätrapport**.</span><span class="sxs-lookup"><span data-stu-id="e9013-176">To run the existing report, go to **Questionnaire** \> **Design** \> **Questionnaires report**.</span></span>

    ![Att välja menyalternativet enkätrapport i modulen enkät för att köra den befintliga SSRS-rapporten](./media/er-quick-start1-application-menu-origin.png)

2. <span data-ttu-id="e9013-178">I dialogrutan **enkätrapport** ange urvalskriterier.</span><span class="sxs-lookup"><span data-stu-id="e9013-178">In the **Questionnaires report** dialog box, specify selection criteria.</span></span> <span data-ttu-id="e9013-179">Använd ett filter så att rapporten bara innehåller **SBCCrsExam** enkät.</span><span class="sxs-lookup"><span data-stu-id="e9013-179">Apply a filter so that the report includes only the **SBCCrsExam** questionnaire.</span></span>

    ![Ange urvalskriterier i dialogrutan för enkätrapport](./media/er-quick-start1-ssrs-report-dialog.png)

<span data-ttu-id="e9013-181">Följande bild visar den genererade versionen av SSRS-rapporten för **SBCCrsExam**-enkät.</span><span class="sxs-lookup"><span data-stu-id="e9013-181">The following illustration shows the generated version of the SSRS report for the **SBCCrsExam** questionnaire.</span></span>

![Genererad SSRS-rapport](./media/er-quick-start1-ssrs-report.png)

## <a name="configure-the-er-framework"></a><a name="ConfigureFramework"></a><span data-ttu-id="e9013-183">Konfigurera ER-ramverket</span><span class="sxs-lookup"><span data-stu-id="e9013-183">Configure the ER framework</span></span>

<span data-ttu-id="e9013-184">Som användare i rollen Utvecklare för elektronisk rapportering måste du konfigurera den minsta uppsättningen ER-parametrar innan du kan börja använda ER-ramverket för att designa din nya ER-lösning.</span><span class="sxs-lookup"><span data-stu-id="e9013-184">As a user in the Electronic Reporting Developer role, you must configure the minimal set of ER parameters before you can start to use the ER framework to design your new ER solution.</span></span>

### <a name="configure-er-parameters"></a><a name="ConfigureParameters"></a><span data-ttu-id="e9013-185">Konfigurera ER-parametrar</span><span class="sxs-lookup"><span data-stu-id="e9013-185">Configure ER parameters</span></span>

1. <span data-ttu-id="e9013-186">Gå till **Organisationsadministration** \> **Arbetsytor** \> **Elektronisk rapportering**.</span><span class="sxs-lookup"><span data-stu-id="e9013-186">Go to **Organization administration** \> **Workspaces** \> **Electronic reporting**.</span></span>
2. <span data-ttu-id="e9013-187">På arbetsytan **Elektronisk rprogramortering** väljer du **Elektroniska rprogramorteringsparametrar**.</span><span class="sxs-lookup"><span data-stu-id="e9013-187">In the **Electronic reporting** workspace, select **Electronic reporting parameters**.</span></span>
3. <span data-ttu-id="e9013-188">På sidan **parametrar för elektronisk rapportering** på fliken **allmänna** anger du alternativet till **aktivera designläge** till **Ja**.</span><span class="sxs-lookup"><span data-stu-id="e9013-188">On the **Electronic reporting parameters** page, on the **General** tab, set the **Enable design mode** option to **Yes**.</span></span>
4. <span data-ttu-id="e9013-189">Ange följande parametrar på fliken **Bilagor**:</span><span class="sxs-lookup"><span data-stu-id="e9013-189">On the **Attachments** tab, set the following parameters:</span></span>

    - <span data-ttu-id="e9013-190">Ange fältet **Konfigurationer** till **Fil** för **USMF**-företaget.</span><span class="sxs-lookup"><span data-stu-id="e9013-190">Set the **Configurations** field to **File** for the **USMF** company.</span></span>
    - <span data-ttu-id="e9013-191">Ange **Jobbarkiv**, **Tillfälliga**, **Baslinje** och **Andra** till **Fil**.</span><span class="sxs-lookup"><span data-stu-id="e9013-191">Set **Job archive**, **Temporary**, **Baseline**, and **Others** fields to **File**.</span></span>

<span data-ttu-id="e9013-192">Mer information om ER-parametrar finns i [Konfigurera om ER-ramverket](electronic-reporting-er-configure-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="e9013-192">For more information about ER parameters, see [Configure the ER framework](electronic-reporting-er-configure-parameters.md).</span></span>

### <a name="activate-an-er-configuration-provider"></a><a name="ActivateProvider"></a><span data-ttu-id="e9013-193">Aktivera en ER-konfigurationsleverantör</span><span class="sxs-lookup"><span data-stu-id="e9013-193">Activate an ER configuration provider</span></span>

<span data-ttu-id="e9013-194">Varje ER-konfiguration markeras som ägd av en ER-konfigurationsleverantör.</span><span class="sxs-lookup"><span data-stu-id="e9013-194">Every ER configuration is marked as owned by an ER configuration provider.</span></span> <span data-ttu-id="e9013-195">Därför måste du aktivera en ER-konfigurationsleverantör i arbetsytan **Elektronisk rapportering** innan du börjar lägga till eller redigera ER-konfigurationer.</span><span class="sxs-lookup"><span data-stu-id="e9013-195">Therefore, you must activate an ER configuration provider in the **Electronic reporting** workspace before you start to add or edit any ER configurations.</span></span>

> [!NOTE]
> <span data-ttu-id="e9013-196">Endast ägaren till en ER-konfiguration kan redigera den.</span><span class="sxs-lookup"><span data-stu-id="e9013-196">Only the owner of an ER configuration can edit it.</span></span> <span data-ttu-id="e9013-197">Därför måste en lämplig ER-konfigurationsleverantör aktiveras innan en ER-konfiguration kan redigeras arbetsytan **Elektronisk rapportering**.</span><span class="sxs-lookup"><span data-stu-id="e9013-197">Therefore, before an ER configuration can be edited, the appropriate ER configuration provider must be activated in the **Electronic reporting** workspace.</span></span>

#### <a name="review-the-list-of-er-configuration-providers"></a><a name="ReviewProvidersList"></a><span data-ttu-id="e9013-198">Granska listan med ER-konfigurationsleverantörer</span><span class="sxs-lookup"><span data-stu-id="e9013-198">Review the list of ER configuration providers</span></span>

1. <span data-ttu-id="e9013-199">Gå till **Organisationsadministration** \> **Arbetsytor** \> **Elektronisk rapportering**.</span><span class="sxs-lookup"><span data-stu-id="e9013-199">Go to **Organization administration** \> **Workspaces** \> **Electronic reporting**.</span></span>
2. <span data-ttu-id="e9013-200">I arbetsytan **elektronisk rapportering** i avsnittet **Relaterade länkar** väljer du **Konfigurationsleverantörer**.</span><span class="sxs-lookup"><span data-stu-id="e9013-200">In the **Electronic reporting** workspace, in the **Related links** section, select **Configuration providers**.</span></span>
3. <span data-ttu-id="e9013-201">På sidan **Konfigurationsleverantörer** har varje konfigurationsleverantörspost ett unikt namn och en URL.</span><span class="sxs-lookup"><span data-stu-id="e9013-201">On the **Configuration providers** page, each configuration provider record has a unique name and URL.</span></span> <span data-ttu-id="e9013-202">Granska innehållet på den här sidan.</span><span class="sxs-lookup"><span data-stu-id="e9013-202">Review the contents of this page.</span></span> <span data-ttu-id="e9013-203">Om det redan finns en post för **Litware, Inc.** (`https://www.litware.com`) hoppar du över nästa procedur [Lägg till en ny ER-konfigurationsleverantör](#ActivateProvider).</span><span class="sxs-lookup"><span data-stu-id="e9013-203">If a record for **Litware, Inc.** (`https://www.litware.com`) already exists, skip the next procedure, [Add a new ER configuration provider](#ActivateProvider).</span></span>

#### <a name="add-a-new-er-configuration-provider"></a><a name="AddProvider"></a><span data-ttu-id="e9013-204">Lägg till en ny ER-konfigurationsleverantör</span><span class="sxs-lookup"><span data-stu-id="e9013-204">Add a new ER configuration provider</span></span>

1. <span data-ttu-id="e9013-205">Välj **Konfigurationsleverantörer** på sidan **Leveranssätt**.</span><span class="sxs-lookup"><span data-stu-id="e9013-205">On the **Configuration providers** page, select **New**.</span></span>
2. <span data-ttu-id="e9013-206">I fältet **Namn** anger du **Litware, Inc.**.</span><span class="sxs-lookup"><span data-stu-id="e9013-206">In the **Name** field, enter **Litware, Inc.**</span></span>
3. <span data-ttu-id="e9013-207">I fältet **Internetadress** anger du `https://www.litware.com`.</span><span class="sxs-lookup"><span data-stu-id="e9013-207">In the **Internet address** field, enter `https://www.litware.com`.</span></span>
4. <span data-ttu-id="e9013-208">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="e9013-208">Select **Save**.</span></span>

#### <a name="activate-an-er-configuration-provider"></a><a name="ActivateAddedProvider"></a><span data-ttu-id="e9013-209">Aktivera en ER-konfigurationsleverantör</span><span class="sxs-lookup"><span data-stu-id="e9013-209">Activate an ER configuration provider</span></span>

1. <span data-ttu-id="e9013-210">Gå till **Organisationsadministration** \> **Arbetsytor** \> **Elektronisk rapportering**.</span><span class="sxs-lookup"><span data-stu-id="e9013-210">Go to **Organization administration** \> **Workspaces** \> **Electronic reporting**.</span></span>
2. <span data-ttu-id="e9013-211">I arbetsytan **Elektronisk rapportering** väljer du **Litware, Inc.** för din konfigurationsleverantör.</span><span class="sxs-lookup"><span data-stu-id="e9013-211">In the **Electronic reporting** workspace, select the **Litware, Inc.** configuration provider.</span></span>
3. <span data-ttu-id="e9013-212">Ställ in **Ange aktiva**.</span><span class="sxs-lookup"><span data-stu-id="e9013-212">Select **Set active**.</span></span>

<span data-ttu-id="e9013-213">Mer information om ER-konfigurationsleverantörer finns i [Skapa konfigurationsleverantörer och markera dem som aktiva](tasks/er-configuration-provider-mark-it-active-2016-11.md).</span><span class="sxs-lookup"><span data-stu-id="e9013-213">For more information about ER configuration providers, see [Create configuration providers and mark them as active](tasks/er-configuration-provider-mark-it-active-2016-11.md).</span></span>

## <a name="design-a-domain-specific-data-model"></a><a name="DesignModel"></a><span data-ttu-id="e9013-214">Ange urvalskriterier i dialogrutan för frågeformulär</span><span class="sxs-lookup"><span data-stu-id="e9013-214">Design a domain-specific data model</span></span>

<span data-ttu-id="e9013-215">Du måste skapa en ny ER-konfiguration som innehåller komponenten [datamodell](general-electronic-reporting.md#data-model-and-model-mapping-components) för affärsdomänen **Enkät**.</span><span class="sxs-lookup"><span data-stu-id="e9013-215">You must create a new ER configuration that contains a [data model](general-electronic-reporting.md#data-model-and-model-mapping-components) component for the **Questionnaire** business domain.</span></span> <span data-ttu-id="e9013-216">Den här datamodellen kommer senare att användas som datakälla när du designar ett ER-format för att generera **enkät**-rapporten.</span><span class="sxs-lookup"><span data-stu-id="e9013-216">This data model will later be used as a data source when you design an ER format to generate the **Questionnaire** report.</span></span>

<span data-ttu-id="e9013-217">Genom att slutföra stegen i avsnittet [Importera en ny konfiguration för datamodell](#ImportDataModel) kan du importera den datamodell som krävs från den angivna XML-filen.</span><span class="sxs-lookup"><span data-stu-id="e9013-217">By completing the steps in the [Import a new data model configuration](#ImportDataModel) section, you can import the required data model from the provided XML file.</span></span> <span data-ttu-id="e9013-218">Du kan också slutföra stegen i avsnittet [Skapa en ny konfiguration för datamodell](#DesignDataModel) om du vill designa den här datamodellen från början.</span><span class="sxs-lookup"><span data-stu-id="e9013-218">Alternatively, you can complete the steps in the [Create a new data model configuration](#DesignDataModel) section to design this data model from scratch.</span></span>

### <a name="import-a-new-data-model-configuration"></a><a name="ImportDataModel"></a><span data-ttu-id="e9013-219">Importera en ny konfiguration för datamodell</span><span class="sxs-lookup"><span data-stu-id="e9013-219">Import a new data model configuration</span></span>

1. <span data-ttu-id="e9013-220">Hämta filen [enkätmodell.version.1.xml](https://go.microsoft.com/fwlink/?linkid=851448) och spara den på den lokala datorn.</span><span class="sxs-lookup"><span data-stu-id="e9013-220">Download the [Questionnaires model.version.1.xml](https://go.microsoft.com/fwlink/?linkid=851448) file, and save it to your local computer.</span></span>
2. <span data-ttu-id="e9013-221">Gå till **Organisationsadministration** \> **Arbetsytor** \> **Elektronisk rapportering**.</span><span class="sxs-lookup"><span data-stu-id="e9013-221">Go to **Organization administration** \> **Workspaces** \> **Electronic reporting**.</span></span>
3. <span data-ttu-id="e9013-222">På arbetsytan **Elektronisk rapportering** väljer du **Rapporteringskonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="e9013-222">In the **Electronic reporting** workspace, select **Reporting configurations**.</span></span>
4. <span data-ttu-id="e9013-223">På Åtgärdsfönster väljer du **växla** \> **läs in från XML-fil**.</span><span class="sxs-lookup"><span data-stu-id="e9013-223">On the Action Pane, select **Exchange** \> **Load from XML file**.</span></span>
5. <span data-ttu-id="e9013-224">Välj **Bläddra** och leta sedan reda på och markera filen **enkätmodell.version.1.xml**.</span><span class="sxs-lookup"><span data-stu-id="e9013-224">Select **Browse**, and then find and select the **Questionnaires model.version.1.xml** file.</span></span>
6. <span data-ttu-id="e9013-225">Välj **OK** för att importera konfigurationen.</span><span class="sxs-lookup"><span data-stu-id="e9013-225">Select **OK** to import the configuration.</span></span>

<span data-ttu-id="e9013-226">Om du vill fortsätta hoppar du över nästa procedur, [skapa en ny konfiguration för datamodell](#DesignDataModel).</span><span class="sxs-lookup"><span data-stu-id="e9013-226">To continue, skip the next procedure, [Create a new data model configuration](#DesignDataModel).</span></span>

### <a name="create-a-new-data-model-configuration"></a><a name="DesignDataModel"></a><span data-ttu-id="e9013-227">Skapa en ny datamodellskonfiguration</span><span class="sxs-lookup"><span data-stu-id="e9013-227">Create a new data model configuration</span></span>

1. <span data-ttu-id="e9013-228">Gå till **Organisationsadministration** \> **Arbetsytor** \> **Elektronisk rapportering**.</span><span class="sxs-lookup"><span data-stu-id="e9013-228">Go to **Organization administration** \> **Workspaces** \> **Electronic reporting**.</span></span>
2. <span data-ttu-id="e9013-229">På arbetsytan **Elektronisk rapportering** väljer du **Rapporteringskonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="e9013-229">In the **Electronic reporting** workspace, select **Reporting configurations**.</span></span>
3. <span data-ttu-id="e9013-230">Välj **Skapa konfiguration**.</span><span class="sxs-lookup"><span data-stu-id="e9013-230">Select **Create configuration**.</span></span>
4. <span data-ttu-id="e9013-231">I listrutan i fältet **Namn** anger du **enkätmodell**.</span><span class="sxs-lookup"><span data-stu-id="e9013-231">In the drop-down dialog box, in the **Name** field, enter **Questionnaire model**.</span></span>
5. <span data-ttu-id="e9013-232">Välj **Skapa konfiguration** för att skapa konfigurationen.</span><span class="sxs-lookup"><span data-stu-id="e9013-232">Select **Create configuration** to create the configuration.</span></span>

#### <a name="name-the-data-model"></a><a name="NameDataModel"></a><span data-ttu-id="e9013-233">Namnge och datamodellen</span><span class="sxs-lookup"><span data-stu-id="e9013-233">Name the data model</span></span>

1. <span data-ttu-id="e9013-234">På sidan **konfigurationer** i konfigurationsträdet väljer du **enkätmodell**.</span><span class="sxs-lookup"><span data-stu-id="e9013-234">On the **Configurations** page, in the configuration tree, select **Questionnaire model**.</span></span>
2. <span data-ttu-id="e9013-235">Välj **Designer**.</span><span class="sxs-lookup"><span data-stu-id="e9013-235">Select **Designer**.</span></span>
3. <span data-ttu-id="e9013-236">På sidan **Datamodelldesigner** på snabbfliken **Allmänt** i fält **Namn** ange <a name="DataModeName"></a>**Enkät**.</span><span class="sxs-lookup"><span data-stu-id="e9013-236">On the **Data model designer** page, on the **General** FastTab, in the **Name** field, enter <a name="DataModeName"></a>**Questionnaires**.</span></span>

#### <a name="add-new-data-model-fields"></a><a name="FieldsEntry"></a><span data-ttu-id="e9013-237">Lägg till nya fält för datamodell</span><span class="sxs-lookup"><span data-stu-id="e9013-237">Add new data model fields</span></span>

1. <span data-ttu-id="e9013-238">Välj **Nytt** på sidan **Datamodelldesigner**.</span><span class="sxs-lookup"><span data-stu-id="e9013-238">On the **Data model designer** page, select **New**.</span></span>
2. <span data-ttu-id="e9013-239">Gör så här i listrutan för att lägga till en datamodellnod:</span><span class="sxs-lookup"><span data-stu-id="e9013-239">In the drop-down dialog box for adding a data model node, follow these steps:</span></span>

    1. <span data-ttu-id="e9013-240">Välj **modellrot** som typ för den nya noden.</span><span class="sxs-lookup"><span data-stu-id="e9013-240">Select **Model root** as the type of the new node.</span></span>
    2. <span data-ttu-id="e9013-241">Skriv <a name="RootDefinitionName"></a>**Kassa** i fältet **Rot**.</span><span class="sxs-lookup"><span data-stu-id="e9013-241">In the **Name** field, enter <a name="RootDefinitionName"></a>**Root**.</span></span>
    3. <span data-ttu-id="e9013-242">Välj **Lägg till** för att lägga till en ny nod.</span><span class="sxs-lookup"><span data-stu-id="e9013-242">Select **Add** to add the new node.</span></span>

    <span data-ttu-id="e9013-243">Den här rotbeskrivningen används för att tillhandahålla data för rapporten **enkät**.</span><span class="sxs-lookup"><span data-stu-id="e9013-243">This root descriptor will be used to provide data for the **Questionnaire** report.</span></span> <span data-ttu-id="e9013-244">En enskild datamodell kan ha flera beskrivare.</span><span class="sxs-lookup"><span data-stu-id="e9013-244">A single data model can have multiple descriptors.</span></span> <span data-ttu-id="e9013-245">Varje beskrivning kan anges för ett enda ER-format, för att identifiera de data som krävs för att generera rapporten.</span><span class="sxs-lookup"><span data-stu-id="e9013-245">Each descriptor can be specified for a single ER format, to identify data that is required to generate the report.</span></span>

3. <span data-ttu-id="e9013-246">Välj **Ny** igen och sedan, i rullgardinsmenyn för att lägga till en datamodellnod, följ dessa steg:</span><span class="sxs-lookup"><span data-stu-id="e9013-246">Select **New** again, and then, in the drop-down dialog box for adding a data model node, follow these steps:</span></span>

    1. <span data-ttu-id="e9013-247">Välj **Underordnad av en aktiv nod** som typ för den nya noden.</span><span class="sxs-lookup"><span data-stu-id="e9013-247">Select **Child of an active node** as the type of the new node.</span></span>
    2. <span data-ttu-id="e9013-248">Skriv **Namn** i fältet **CompanyName**.</span><span class="sxs-lookup"><span data-stu-id="e9013-248">In the **Name** field, enter **CompanyName**.</span></span>
    3. <span data-ttu-id="e9013-249">Välj **Sträng** i fältet **Artikeltyp**.</span><span class="sxs-lookup"><span data-stu-id="e9013-249">In the **Item type** field, select **String**.</span></span>
    4. <span data-ttu-id="e9013-250">Välj **Lägg till** för att lägga till ett nytt fält.</span><span class="sxs-lookup"><span data-stu-id="e9013-250">Select **Add** to add the new field.</span></span>

    <span data-ttu-id="e9013-251">Det här fältet är obligatoriskt om du vill skicka namnet på det aktuella företaget till en ER-rapport som använder den här datamodellen som datakälla.</span><span class="sxs-lookup"><span data-stu-id="e9013-251">This field is required to pass the name of the current company to an ER report that consumes this data model as a data source.</span></span>

4. <span data-ttu-id="e9013-252">Välj **Ny** igen och sedan, i rullgardinsmenyn för att lägga till en datamodellnod, följ dessa steg:</span><span class="sxs-lookup"><span data-stu-id="e9013-252">Select **New** again, and then, in the drop-down dialog box for adding a data model node, follow these steps:</span></span>

    1. <span data-ttu-id="e9013-253">Välj **Underordnad av en aktiv nod** som typ för den nya noden.</span><span class="sxs-lookup"><span data-stu-id="e9013-253">Select **Child of an active node** as the type of the new node.</span></span>
    2. <span data-ttu-id="e9013-254">Skriv **Namn** i fältet **Enkät**.</span><span class="sxs-lookup"><span data-stu-id="e9013-254">In the **Name** field, enter **Questionnaire**.</span></span>
    3. <span data-ttu-id="e9013-255">Välj **Postlista** i fältet **Artikeltyp**.</span><span class="sxs-lookup"><span data-stu-id="e9013-255">In the **Item type** field, select **Record list**.</span></span>
    4. <span data-ttu-id="e9013-256">Välj **Lägg till** för att lägga till ett nytt fält.</span><span class="sxs-lookup"><span data-stu-id="e9013-256">Select **Add** to add the new field.</span></span>

    <span data-ttu-id="e9013-257">Detta fält kommer att användas för att skicka listan över enkäter på det aktuella företaget till en ER-rapport som använder den här datamodellen som datakälla.</span><span class="sxs-lookup"><span data-stu-id="e9013-257">This field will be used to pass the list of questionnaires to an ER report that consumes this data model as a data source.</span></span>

5. <span data-ttu-id="e9013-258">Välj nod **enkät** .</span><span class="sxs-lookup"><span data-stu-id="e9013-258">Select the **Questionnaire** node.</span></span>
6. <span data-ttu-id="e9013-259">Fortsätt att lägga till de obligatoriska fälten i den redigerbara datamodellen på samma sätt tills du har slutfört följande datamodellstruktur.</span><span class="sxs-lookup"><span data-stu-id="e9013-259">Continue to add the required fields of the editable data model in the same manner until you complete the following data model structure.</span></span>

    | <span data-ttu-id="e9013-260">Sökväg för fält</span><span class="sxs-lookup"><span data-stu-id="e9013-260">Field path</span></span>                                                    | <span data-ttu-id="e9013-261">Datatyp</span><span class="sxs-lookup"><span data-stu-id="e9013-261">Data type</span></span>   | <span data-ttu-id="e9013-262">Fältbeteckning/returnerat värde</span><span class="sxs-lookup"><span data-stu-id="e9013-262">Field designation/returned value</span></span> |
    |---------------------------------------------------------------|-------------|----------------------------------|
    | <span data-ttu-id="e9013-263">Rot</span><span class="sxs-lookup"><span data-stu-id="e9013-263">Root</span></span>                                                          |             | <span data-ttu-id="e9013-264">Referenspunkten för att begära enkätdata.</span><span class="sxs-lookup"><span data-stu-id="e9013-264">The reference point to request questionnaire data.</span></span> |
    | <span data-ttu-id="e9013-265">Root\\CompanyName</span><span class="sxs-lookup"><span data-stu-id="e9013-265">Root\\CompanyName</span></span>                                             | <span data-ttu-id="e9013-266">Sträng</span><span class="sxs-lookup"><span data-stu-id="e9013-266">String</span></span>      | <span data-ttu-id="e9013-267">Namnet på det aktuella företaget.</span><span class="sxs-lookup"><span data-stu-id="e9013-267">The name of the current company.</span></span> |
    | <span data-ttu-id="e9013-268">Root\\ExecutionContext</span><span class="sxs-lookup"><span data-stu-id="e9013-268">Root\\ExecutionContext</span></span>                                        | <span data-ttu-id="e9013-269">Registrera</span><span class="sxs-lookup"><span data-stu-id="e9013-269">Record</span></span>      | <span data-ttu-id="e9013-270">Information om formatkörning.</span><span class="sxs-lookup"><span data-stu-id="e9013-270">Format execution details.</span></span> |
    | <span data-ttu-id="e9013-271">Root\\ExecutionContext\\FormatName</span><span class="sxs-lookup"><span data-stu-id="e9013-271">Root\\ExecutionContext\\FormatName</span></span>                            | <span data-ttu-id="e9013-272">Sträng</span><span class="sxs-lookup"><span data-stu-id="e9013-272">String</span></span>      | <span data-ttu-id="e9013-273">Namnet på ER-formatet som körs.</span><span class="sxs-lookup"><span data-stu-id="e9013-273">The name of the ER format that is being run.</span></span> |
    | <span data-ttu-id="e9013-274">Root\\Questionnaire</span><span class="sxs-lookup"><span data-stu-id="e9013-274">Root\\Questionnaire</span></span>                                           | <span data-ttu-id="e9013-275">Postlista</span><span class="sxs-lookup"><span data-stu-id="e9013-275">Record list</span></span> | <span data-ttu-id="e9013-276">Listan över enkäter</span><span class="sxs-lookup"><span data-stu-id="e9013-276">The list of questionnaires</span></span> |
    | <span data-ttu-id="e9013-277">Root\\Questionnaire\\Active</span><span class="sxs-lookup"><span data-stu-id="e9013-277">Root\\Questionnaire\\Active</span></span>                                   | <span data-ttu-id="e9013-278">Sträng</span><span class="sxs-lookup"><span data-stu-id="e9013-278">String</span></span>      | <span data-ttu-id="e9013-279">Status för aktuella enkäten.</span><span class="sxs-lookup"><span data-stu-id="e9013-279">The status of the current questionnaire.</span></span> |
    | <span data-ttu-id="e9013-280">Root\\Questionnaire\\Code</span><span class="sxs-lookup"><span data-stu-id="e9013-280">Root\\Questionnaire\\Code</span></span>                                     | <span data-ttu-id="e9013-281">Sträng</span><span class="sxs-lookup"><span data-stu-id="e9013-281">String</span></span>      | <span data-ttu-id="e9013-282">Kod för aktuell aktuella enkäten.</span><span class="sxs-lookup"><span data-stu-id="e9013-282">The code of the current questionnaire.</span></span> |
    | <span data-ttu-id="e9013-283">Root\\Questionnaire\\Description</span><span class="sxs-lookup"><span data-stu-id="e9013-283">Root\\Questionnaire\\Description</span></span>                              | <span data-ttu-id="e9013-284">Sträng</span><span class="sxs-lookup"><span data-stu-id="e9013-284">String</span></span>      | <span data-ttu-id="e9013-285">Beskrivning för aktuella enkäten.</span><span class="sxs-lookup"><span data-stu-id="e9013-285">The description of the current questionnaire.</span></span> |
    | <span data-ttu-id="e9013-286">Root\\Questionnaire\\QuestionnaireType</span><span class="sxs-lookup"><span data-stu-id="e9013-286">Root\\Questionnaire\\QuestionnaireType</span></span>                        | <span data-ttu-id="e9013-287">Sträng</span><span class="sxs-lookup"><span data-stu-id="e9013-287">String</span></span>      | <span data-ttu-id="e9013-288">Typ för aktuella enkäten.</span><span class="sxs-lookup"><span data-stu-id="e9013-288">The type of the current questionnaire.</span></span> |
    | <span data-ttu-id="e9013-289">Root\\Questionnaire\\QuestionOrder</span><span class="sxs-lookup"><span data-stu-id="e9013-289">Root\\Questionnaire\\QuestionOrder</span></span>                            | <span data-ttu-id="e9013-290">Sträng</span><span class="sxs-lookup"><span data-stu-id="e9013-290">String</span></span>      | <span data-ttu-id="e9013-291">Den numeriska ordningen för aktuella enkäten.</span><span class="sxs-lookup"><span data-stu-id="e9013-291">The numerical order of the current questionnaire.</span></span> |
    | <span data-ttu-id="e9013-292">Root\\Questionnaire\\ResultsGroup</span><span class="sxs-lookup"><span data-stu-id="e9013-292">Root\\Questionnaire\\ResultsGroup</span></span>                             | <span data-ttu-id="e9013-293">Registrera</span><span class="sxs-lookup"><span data-stu-id="e9013-293">Record</span></span>      | <span data-ttu-id="e9013-294">De resulterande parametrarna för aktuella enkäten.</span><span class="sxs-lookup"><span data-stu-id="e9013-294">The result parameters of the current questionnaire.</span></span> |
    | <span data-ttu-id="e9013-295">Root\\Questionnaire\\ResultsGroup\\Code</span><span class="sxs-lookup"><span data-stu-id="e9013-295">Root\\Questionnaire\\ResultsGroup\\Code</span></span>                       | <span data-ttu-id="e9013-296">Sträng</span><span class="sxs-lookup"><span data-stu-id="e9013-296">String</span></span>      | <span data-ttu-id="e9013-297">Identifieringskoden för den aktuella resultatgruppen.</span><span class="sxs-lookup"><span data-stu-id="e9013-297">The identification code of the current result group.</span></span> |
    | <span data-ttu-id="e9013-298">Root\\Questionnaire\\ResultsGroup\\Description</span><span class="sxs-lookup"><span data-stu-id="e9013-298">Root\\Questionnaire\\ResultsGroup\\Description</span></span>                | <span data-ttu-id="e9013-299">Sträng</span><span class="sxs-lookup"><span data-stu-id="e9013-299">String</span></span>      | <span data-ttu-id="e9013-300">Beskrivning för aktuella resultatgruppen.</span><span class="sxs-lookup"><span data-stu-id="e9013-300">The description of the current result group.</span></span> |
    | <span data-ttu-id="e9013-301">Root\\Questionnaire\\ResultsGroup\\MaxNumberOfPoints</span><span class="sxs-lookup"><span data-stu-id="e9013-301">Root\\Questionnaire\\ResultsGroup\\MaxNumberOfPoints</span></span>          | <span data-ttu-id="e9013-302">Realtal</span><span class="sxs-lookup"><span data-stu-id="e9013-302">Real</span></span>        | <span data-ttu-id="e9013-303">Det maximala antal poäng som kan intjänas.</span><span class="sxs-lookup"><span data-stu-id="e9013-303">The maximum number of points that could be earned.</span></span> |
    | <span data-ttu-id="e9013-304">Root\\Questionnaire\\Question</span><span class="sxs-lookup"><span data-stu-id="e9013-304">Root\\Questionnaire\\Question</span></span>                                 | <span data-ttu-id="e9013-305">Postlista</span><span class="sxs-lookup"><span data-stu-id="e9013-305">Record list</span></span> | <span data-ttu-id="e9013-306">Listan med frågor för den aktuella enkäten.</span><span class="sxs-lookup"><span data-stu-id="e9013-306">The list of questions for the current questionnaire.</span></span> |
    | <span data-ttu-id="e9013-307">Root\\Questionnaire\\Question\\CollectionSequenceNumber</span><span class="sxs-lookup"><span data-stu-id="e9013-307">Root\\Questionnaire\\Question\\CollectionSequenceNumber</span></span>       | <span data-ttu-id="e9013-308">Heltal</span><span class="sxs-lookup"><span data-stu-id="e9013-308">Integer</span></span>     | <span data-ttu-id="e9013-309">Sekvensnumret för den aktuella svarssamlingen.</span><span class="sxs-lookup"><span data-stu-id="e9013-309">The sequence number of the current answer collection.</span></span> |
    | <span data-ttu-id="e9013-310">Root\\Questionnaire\\Question\\Id</span><span class="sxs-lookup"><span data-stu-id="e9013-310">Root\\Questionnaire\\Question\\Id</span></span>                             | <span data-ttu-id="e9013-311">Sträng</span><span class="sxs-lookup"><span data-stu-id="e9013-311">String</span></span>      | <span data-ttu-id="e9013-312">Identifieringskoden för den aktuella frågan.</span><span class="sxs-lookup"><span data-stu-id="e9013-312">The identification code of the current question.</span></span> |
    | <span data-ttu-id="e9013-313">Root\\Questionnaire\\Question\\MustBeCompleted</span><span class="sxs-lookup"><span data-stu-id="e9013-313">Root\\Questionnaire\\Question\\MustBeCompleted</span></span>                | <span data-ttu-id="e9013-314">Sträng</span><span class="sxs-lookup"><span data-stu-id="e9013-314">String</span></span>      | <span data-ttu-id="e9013-315">En flagga som anger om den aktuella frågan måste besvaras.</span><span class="sxs-lookup"><span data-stu-id="e9013-315">A flag that indicates whether the current question must be answered.</span></span> |
    | <span data-ttu-id="e9013-316">Root\\Questionnaire\\Question\\PrimaryQuestion</span><span class="sxs-lookup"><span data-stu-id="e9013-316">Root\\Questionnaire\\Question\\PrimaryQuestion</span></span>                | <span data-ttu-id="e9013-317">Sträng</span><span class="sxs-lookup"><span data-stu-id="e9013-317">String</span></span>      | <span data-ttu-id="e9013-318">En flagga som anger om den aktuella frågan är primär.</span><span class="sxs-lookup"><span data-stu-id="e9013-318">A flag that indicates whether the current question is primary.</span></span> |
    | <span data-ttu-id="e9013-319">Root\\Questionnaire\\Question\\SequenceNumber</span><span class="sxs-lookup"><span data-stu-id="e9013-319">Root\\Questionnaire\\Question\\SequenceNumber</span></span>                 | <span data-ttu-id="e9013-320">Heltal</span><span class="sxs-lookup"><span data-stu-id="e9013-320">Integer</span></span>     | <span data-ttu-id="e9013-321">Sekvensnumret för den aktuella frågan.</span><span class="sxs-lookup"><span data-stu-id="e9013-321">The sequence number of the current question.</span></span> |
    | <span data-ttu-id="e9013-322">Root\\Questionnaire\\Question\\Text</span><span class="sxs-lookup"><span data-stu-id="e9013-322">Root\\Questionnaire\\Question\\Text</span></span>                           | <span data-ttu-id="e9013-323">Sträng</span><span class="sxs-lookup"><span data-stu-id="e9013-323">String</span></span>      | <span data-ttu-id="e9013-324">Texten för den aktuella frågan.</span><span class="sxs-lookup"><span data-stu-id="e9013-324">The text of the current question.</span></span> |
    | <span data-ttu-id="e9013-325">Root\\Questionnaire\\Question\\Answer</span><span class="sxs-lookup"><span data-stu-id="e9013-325">Root\\Questionnaire\\Question\\Answer</span></span>                         | <span data-ttu-id="e9013-326">Postlista</span><span class="sxs-lookup"><span data-stu-id="e9013-326">Record list</span></span> | <span data-ttu-id="e9013-327">Listan med svar för den aktuella frågan.</span><span class="sxs-lookup"><span data-stu-id="e9013-327">The list of answers for the current question.</span></span> |
    | <span data-ttu-id="e9013-328">Root\\Questionnaire\\Question\\Answer\\CorrectAnswer</span><span class="sxs-lookup"><span data-stu-id="e9013-328">Root\\Questionnaire\\Question\\Answer\\CorrectAnswer</span></span>          | <span data-ttu-id="e9013-329">Sträng</span><span class="sxs-lookup"><span data-stu-id="e9013-329">String</span></span>      | <span data-ttu-id="e9013-330">En flagga som anger om det aktuella svaret är korrekt.</span><span class="sxs-lookup"><span data-stu-id="e9013-330">A flag that indicates whether the current answer is correct.</span></span> |
    | <span data-ttu-id="e9013-331">Root\\Questionnaire\\Question\\Answer\\Points</span><span class="sxs-lookup"><span data-stu-id="e9013-331">Root\\Questionnaire\\Question\\Answer\\Points</span></span>                 | <span data-ttu-id="e9013-332">Realtal</span><span class="sxs-lookup"><span data-stu-id="e9013-332">Real</span></span>        | <span data-ttu-id="e9013-333">De poäng som intjänas när det aktuella svaret väljs.</span><span class="sxs-lookup"><span data-stu-id="e9013-333">The points that are earned when the current answer is selected.</span></span> |
    | <span data-ttu-id="e9013-334">Root\\Questionnaire\\Question\\Answer\\SequenceNumber</span><span class="sxs-lookup"><span data-stu-id="e9013-334">Root\\Questionnaire\\Question\\Answer\\SequenceNumber</span></span>         | <span data-ttu-id="e9013-335">Heltal</span><span class="sxs-lookup"><span data-stu-id="e9013-335">Integer</span></span>     | <span data-ttu-id="e9013-336">Sekvensnumret för det aktuella svaret.</span><span class="sxs-lookup"><span data-stu-id="e9013-336">The sequence number of the current answer.</span></span> |
    | <span data-ttu-id="e9013-337">Root\\Questionnaire\\Question\\Answer\\Text</span><span class="sxs-lookup"><span data-stu-id="e9013-337">Root\\Questionnaire\\Question\\Answer\\Text</span></span>                   | <span data-ttu-id="e9013-338">Sträng</span><span class="sxs-lookup"><span data-stu-id="e9013-338">String</span></span>      | <span data-ttu-id="e9013-339">Texten för det aktuella svaret.</span><span class="sxs-lookup"><span data-stu-id="e9013-339">The text of the current answer.</span></span> |

    <span data-ttu-id="e9013-340">I bilden nedan visas den färdiga redigerbara datamodellen på sidan **Datamodelldesigner**.</span><span class="sxs-lookup"><span data-stu-id="e9013-340">The following illustration shows the completed editable data model on the **Data model designer** page.</span></span>

    ![Konfigurerad datamodell i ER-datamodelldesigner](./media/er-quick-start1-model2.png)

7. <span data-ttu-id="e9013-342">Spara ändringarna.</span><span class="sxs-lookup"><span data-stu-id="e9013-342">Save your changes.</span></span>
8. <span data-ttu-id="e9013-343">Stäng sidan **datamodelldesigner**.</span><span class="sxs-lookup"><span data-stu-id="e9013-343">Close the **Data model designer** page.</span></span>

#### <a name="complete-the-design-of-the-data-model"></a><a name="CompleteDataModel"></a><span data-ttu-id="e9013-344">Färdigställa datamodellens utformning</span><span class="sxs-lookup"><span data-stu-id="e9013-344">Complete the design of the data model</span></span>

1. <span data-ttu-id="e9013-345">Gå till **Organisationsadministration** \> **Elektronisk rapportering** \> **Konfigurationer**.</span><span class="sxs-lookup"><span data-stu-id="e9013-345">Go to **Organization administration** \> **Electronic reporting** \> **Configurations**.</span></span>
2. <span data-ttu-id="e9013-346">På sidan **konfigurationer** i konfigurationsträdet väljer du **enkätmodell**.</span><span class="sxs-lookup"><span data-stu-id="e9013-346">On the **Configurations** page, in the configuration tree, select **Questionnaire model**.</span></span>
3. <span data-ttu-id="e9013-347">På snabbfliken **Versioner** väljer du den konfigurationsversion som har statusen **Utkast**.</span><span class="sxs-lookup"><span data-stu-id="e9013-347">On the **Versions** FastTab, select the configuration version that has a status of **Draft**.</span></span>
4. <span data-ttu-id="e9013-348">Välj **Ändra status** \> **Slutför**.</span><span class="sxs-lookup"><span data-stu-id="e9013-348">Select **Change status** \> **Complete**.</span></span>

<span data-ttu-id="e9013-349">Status för version 1 av denna konfiguration ändras från **utkast** till **slutförd**.</span><span class="sxs-lookup"><span data-stu-id="e9013-349">The status of version 1 of this configuration is changed from **Draft** to **Completed**.</span></span> <span data-ttu-id="e9013-350">Version 1 kan inte längre ändras.</span><span class="sxs-lookup"><span data-stu-id="e9013-350">Version 1 can no longer be changed.</span></span> <span data-ttu-id="e9013-351">Den här versionen innehåller den konfigurerade datamodellen och kan användas som grund för andra ER-konfigurationer.</span><span class="sxs-lookup"><span data-stu-id="e9013-351">This version contains the configured data model and can be used as the basis for other ER configurations.</span></span> <span data-ttu-id="e9013-352">Version 2 av denna konfiguration skapas och har statusen **utkast**.</span><span class="sxs-lookup"><span data-stu-id="e9013-352">Version 2 of this configuration is created and has a status of **Draft**.</span></span> <span data-ttu-id="e9013-353">Du kan redigera den här versionen för att justera datamodellen **enkät**.</span><span class="sxs-lookup"><span data-stu-id="e9013-353">You can edit this version to adjust the **Questionnaire** data model.</span></span>

![Versioner av den redigerbara ER-konfigurationen på sidan konfigurationer](./media/er-quick-start1-model-configuration.png)

<span data-ttu-id="e9013-355">Mer information om versionshantering för ER-konfigurationer finns i [Översikt över elektroniska rapporter (ER)](general-electronic-reporting.md#component-versioning).</span><span class="sxs-lookup"><span data-stu-id="e9013-355">For more information about versioning for ER configurations, see [Electronic reporting (ER) overview](general-electronic-reporting.md#component-versioning).</span></span>

> [!NOTE]
> <span data-ttu-id="e9013-356">Den konfigurerade datamodellen är din abstrakta representation av affärsdomänen **enkät** och innehåller inga relationer till artefakter som är specifika för Microsoft Dynamics 365 Finance.</span><span class="sxs-lookup"><span data-stu-id="e9013-356">The configured data model is your abstract representation of the **Questionnaire** business domain and contains no relations to artefacts that are specific to Microsoft Dynamics 365 Finance.</span></span>

## <a name="design-a-model-mapping-for-the-configured-data-model"></a><a name="DesignMapping"></a><span data-ttu-id="e9013-357">Designa en modellmappning för den konfigurerade datamodellen</span><span class="sxs-lookup"><span data-stu-id="e9013-357">Design a model mapping for the configured data model</span></span>

<span data-ttu-id="e9013-358">Som användare i rollen som elektronisk rapporteringsutvecklare måste du skapa en ny ER-konfiguration som innehåller en komponent för [modellmappning](general-electronic-reporting.md#data-model-and-model-mapping-components) för datamodellen **enkät**.</span><span class="sxs-lookup"><span data-stu-id="e9013-358">As a user in the Electronic Reporting Developer role, you must create a new ER configuration that contains a [model mapping](general-electronic-reporting.md#data-model-and-model-mapping-components) component for the **Questionnaire** data model.</span></span> <span data-ttu-id="e9013-359">Eftersom den här komponenten implementerar den konfigurerade datamodellen för Finance, är den Finance-specifik.</span><span class="sxs-lookup"><span data-stu-id="e9013-359">Because this component implements the configured data model for Finance, it's Finance-specific.</span></span> <span data-ttu-id="e9013-360">Du måste konfigurera komponenten för modellmappning för att ange vilka programobjekt som ska användas för att fylla i den konfigurerade datamodellen med programdata vid körning.</span><span class="sxs-lookup"><span data-stu-id="e9013-360">You must configure the model mapping component to specify the application objects that must be used to fill in the configured data model with application data at runtime.</span></span> <span data-ttu-id="e9013-361">För att slutföra den här uppgiften måste du vara medveten om implementeringsinformationen för datastrukturen i affärsdomänen **enkät** i Finance.</span><span class="sxs-lookup"><span data-stu-id="e9013-361">To complete this task, you must be aware of the implementation details of the data structure of the **Questionnaire** business domain in Finance.</span></span>

<span data-ttu-id="e9013-362">Genom att slutföra stegen i avsnittet [Importera en ny konfiguration för modellmappning](#ImportModelMapping) som följer kan du importera den konfiguration av modellmappning som krävs från den angivna XML-filen.</span><span class="sxs-lookup"><span data-stu-id="e9013-362">By completing the steps in the [Import a new model mapping configuration](#ImportModelMapping) section that follows, you can import the required model mapping configuration from the provided XML file.</span></span> <span data-ttu-id="e9013-363">Du kan också slutföra stegen i avsnittet [Skapa en ny konfiguration för modellmappning](#CreateModelMapping) om du vill designa den här modellmappningen från början.</span><span class="sxs-lookup"><span data-stu-id="e9013-363">Alternatively, you can complete the steps in the [Create a new model mapping configuration](#CreateModelMapping) section to design this model mapping from scratch.</span></span>

### <a name="import-a-new-model-mapping-configuration"></a><a name="ImportModelMapping"></a><span data-ttu-id="e9013-364">Importera en ny konfiguration för modellmappning</span><span class="sxs-lookup"><span data-stu-id="e9013-364">Import a new model mapping configuration</span></span>

1. <span data-ttu-id="e9013-365">Hämta filen [enkätmappning.version.1.xml](https://go.microsoft.com/fwlink/?linkid=851448) och spara den på den lokala datorn.</span><span class="sxs-lookup"><span data-stu-id="e9013-365">Download the [Questionnaires mapping.version.1.1.xml](https://go.microsoft.com/fwlink/?linkid=851448) file, and save it to your local computer.</span></span>
2. <span data-ttu-id="e9013-366">Gå till **Organisationsadministration** \> **Arbetsytor** \> **Elektronisk rapportering**.</span><span class="sxs-lookup"><span data-stu-id="e9013-366">Go to **Organization administration** \> **Workspaces** \> **Electronic reporting**.</span></span>
3. <span data-ttu-id="e9013-367">På arbetsytan **Elektronisk rapportering** väljer du **Rapporteringskonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="e9013-367">In the **Electronic reporting** workspace, select **Reporting configurations**.</span></span>
4. <span data-ttu-id="e9013-368">På Åtgärdsfönster väljer du **växla** \> **läs in från XML-fil**.</span><span class="sxs-lookup"><span data-stu-id="e9013-368">On the Action Pane, select **Exchange** \> **Load from XML file**.</span></span>
5. <span data-ttu-id="e9013-369">Välj **Bläddra** och leta sedan reda på och markera filen **enkätmappning.version.1.1.xml**.</span><span class="sxs-lookup"><span data-stu-id="e9013-369">Select **Browse**, and then find and select the **Questionnaires mapping.version.1.1.xml** file.</span></span>
6. <span data-ttu-id="e9013-370">Välj **OK** för att importera konfigurationen.</span><span class="sxs-lookup"><span data-stu-id="e9013-370">Select **OK** to import the configuration.</span></span>

<span data-ttu-id="e9013-371">Om du vill fortsätta hoppar du över nästa procedur, [skapa en ny konfiguration för modellmappning](#CreateModelMapping).</span><span class="sxs-lookup"><span data-stu-id="e9013-371">To continue, skip the next procedure, [Create a new model mapping configuration](#CreateModelMapping).</span></span>

### <a name="create-a-new-model-mapping-configuration"></a><a name="CreateModelMapping"></a><span data-ttu-id="e9013-372">Skapa en ny konfiguration av modellmappning</span><span class="sxs-lookup"><span data-stu-id="e9013-372">Create a new model mapping configuration</span></span>

1. <span data-ttu-id="e9013-373">Gå till **Organisationsadministration** \> **Elektronisk rapportering** \> **Konfigurationer**.</span><span class="sxs-lookup"><span data-stu-id="e9013-373">Go to **Organization administration** \> **Electronic reporting** \> **Configurations**.</span></span>
2. <span data-ttu-id="e9013-374">På sidan **konfigurationer** i konfigurationsträdet väljer du **enkätmodell**.</span><span class="sxs-lookup"><span data-stu-id="e9013-374">On the **Configurations** page, in the configuration tree, select **Questionnaire model**.</span></span>
3. <span data-ttu-id="e9013-375">Välj **Skapa konfiguration**.</span><span class="sxs-lookup"><span data-stu-id="e9013-375">Select **Create configuration**.</span></span>
4. <span data-ttu-id="e9013-376">Gör följande i listrutan:</span><span class="sxs-lookup"><span data-stu-id="e9013-376">In the drop-down dialog box, follow these steps:</span></span>

    1. <span data-ttu-id="e9013-377">I fältet **Nytt** väljer du **Modellmappning baserat på datamodellenkäter**.</span><span class="sxs-lookup"><span data-stu-id="e9013-377">In the **New** field, select **Model Mapping based on data model Questionnaires**.</span></span>
    2. <span data-ttu-id="e9013-378">Ange **enkätmappning** i fältet **Namn**.</span><span class="sxs-lookup"><span data-stu-id="e9013-378">In the **Name** field, enter **Questionnaire mapping**.</span></span>
    3. <span data-ttu-id="e9013-379">I fältet **Definition av datamodell** välj definitionen **Rot**.</span><span class="sxs-lookup"><span data-stu-id="e9013-379">In the **Data model definition** field, select the **Root** definition.</span></span>
    4. <span data-ttu-id="e9013-380">Välj **Skapa konfiguration** för att skapa konfigurationen.</span><span class="sxs-lookup"><span data-stu-id="e9013-380">Select **Create configuration** to create the configuration.</span></span>

#### <a name="design-a-new-model-mapping-component"></a><a name="DesignMappingComponent"></a><span data-ttu-id="e9013-381">Designa en ny modellmappningskomponent</span><span class="sxs-lookup"><span data-stu-id="e9013-381">Design a new model mapping component</span></span>

1. <span data-ttu-id="e9013-382">På sidan **konfigurationer** i konfigurationsträdet väljer du **enkätmappning**.</span><span class="sxs-lookup"><span data-stu-id="e9013-382">On the **Configurations** page, in the configuration tree, select **Questionnaire mapping**.</span></span>
2. <span data-ttu-id="e9013-383">Välj **designer** om du vill öppna listan över mappningar.</span><span class="sxs-lookup"><span data-stu-id="e9013-383">Select **Designer** to open the list of mappings.</span></span>
3. <span data-ttu-id="e9013-384">Välj den **enkätmappning** som automatiskt lades till för definitionen **Rot**</span><span class="sxs-lookup"><span data-stu-id="e9013-384">Select the **Questionnaires mapping** mapping that was automatically added for the **Root** definition</span></span>
4. <span data-ttu-id="e9013-385">Välj **Designer** om du vill starta konfigurationen av den valda mappningen.</span><span class="sxs-lookup"><span data-stu-id="e9013-385">Select **Designer** to start to configure the selected mapping.</span></span>

<span data-ttu-id="e9013-386">En ny mappning läggs automatiskt till för definitionen **rot**.</span><span class="sxs-lookup"><span data-stu-id="e9013-386">A new mapping is automatically added for the **Root** definition.</span></span> <span data-ttu-id="e9013-387">Den här mappningen har riktningen **Till modell**.</span><span class="sxs-lookup"><span data-stu-id="e9013-387">This mapping has the **To model** direction.</span></span> <span data-ttu-id="e9013-388">Denna mappning kan därför användas för att fylla i en datamodell med de data som krävs.</span><span class="sxs-lookup"><span data-stu-id="e9013-388">Therefore, this mapping can be used to fill in a data model with required data.</span></span>

#### <a name="add-data-sources-to-access-application-tables"></a><a name="AddMmDataSource1"></a><span data-ttu-id="e9013-389">Lägga till datakällor för att öppna programtabeller</span><span class="sxs-lookup"><span data-stu-id="e9013-389">Add data sources to access application tables</span></span>

<span data-ttu-id="e9013-390">Du måste konfigurera datakällor för att få åtkomst till programtabellerna som innehåller enkätuppgifter.</span><span class="sxs-lookup"><span data-stu-id="e9013-390">You must configure data sources to access the application tables that contain questionnaire details.</span></span>

1. <span data-ttu-id="e9013-391">På sidan **Modellmappingsdesigner** i fönstret **Datakälltyper** väljer du **Dynamics 365 for Operations\\Tabellregister**.</span><span class="sxs-lookup"><span data-stu-id="e9013-391">On the **Model mapping designer** page, in the **Data source types** pane, select **Dynamics 365 for Operations\\Table records**.</span></span>
2. <span data-ttu-id="e9013-392">Lägg till en ny datakälla som ska användas för att komma åt KMCollection-registret, där varje post representerar en enda enkät:</span><span class="sxs-lookup"><span data-stu-id="e9013-392">Add a new data source that will be used to access the KMCollection table, where every record represents a single questionnaire:</span></span>

    1. <span data-ttu-id="e9013-393">I fönstret **Datakällor** välj **Lägg till rot**.</span><span class="sxs-lookup"><span data-stu-id="e9013-393">In the **Data sources** pane, select **Add root**.</span></span>
    2. <span data-ttu-id="e9013-394">I dialogrutan i fältet **Namn**, ange **enkät**.</span><span class="sxs-lookup"><span data-stu-id="e9013-394">In dialog box, in the **Name** field, enter **Questionnaire**.</span></span>
    3. <span data-ttu-id="e9013-395">I fältet **Tabell** ange **KMCollection**.</span><span class="sxs-lookup"><span data-stu-id="e9013-395">In the **Table** field, enter **KMCollection**.</span></span>
    4. <span data-ttu-id="e9013-396">Ange alternativet **Fråga efter fråga** till **Ja**.</span><span class="sxs-lookup"><span data-stu-id="e9013-396">Set the **Ask for query** option to **Yes**.</span></span> <span data-ttu-id="e9013-397">Du kan sedan ange alternativet [filtrering](../../fin-ops/get-started/advanced-filtering-query-options.md) för det här registret i dialogrutan för systemfråga under körning.</span><span class="sxs-lookup"><span data-stu-id="e9013-397">You will then be able to specify [filtering](../../fin-ops/get-started/advanced-filtering-query-options.md) options for this table in the system query dialog box at runtime.</span></span>
    5. <span data-ttu-id="e9013-398">Klicka på **OK** om du vill lägga till den nya datakällan.</span><span class="sxs-lookup"><span data-stu-id="e9013-398">Select **OK** to add the new data source.</span></span>

3. <span data-ttu-id="e9013-399">I fönstret **Datakälltyper** välj **Dynamics 365 for Operations\\registerposter**.</span><span class="sxs-lookup"><span data-stu-id="e9013-399">In the **Data source types** pane, select **Dynamics 365 for Operations\\Table records**.</span></span>
4. <span data-ttu-id="e9013-400">Lägg till en ny datakälla som ska användas för att komma åt KMQuestion-registret, där varje post representerar en enda fråga i en enkät:</span><span class="sxs-lookup"><span data-stu-id="e9013-400">Add a new data source that will be used to access the KMQuestion table, where every record represents a single question in a questionnaire:</span></span>

    1. <span data-ttu-id="e9013-401">I fönstret **Datakällor** välj **Lägg till rot**.</span><span class="sxs-lookup"><span data-stu-id="e9013-401">In the **Data sources** pane, select **Add root**.</span></span>
    2. <span data-ttu-id="e9013-402">I dialogrutan i fältet **Namn**, ange **Fråga**.</span><span class="sxs-lookup"><span data-stu-id="e9013-402">In the dialog box, in the **Name** field, enter **Question**.</span></span>
    3. <span data-ttu-id="e9013-403">I fältet **Tabell** ange **KMQuestion**.</span><span class="sxs-lookup"><span data-stu-id="e9013-403">In the **Table** field, enter **KMQuestion**.</span></span>
    4. <span data-ttu-id="e9013-404">Klicka på **OK** om du vill lägga till den nya datakällan.</span><span class="sxs-lookup"><span data-stu-id="e9013-404">Select **OK** to add the new data source.</span></span>

5. <span data-ttu-id="e9013-405">I fönstret **Datakälltyper** välj **Dynamics 365 for Operations\\registerposter**.</span><span class="sxs-lookup"><span data-stu-id="e9013-405">In the **Data source types** pane, select **Dynamics 365 for Operations\\Table records**.</span></span>
6. <span data-ttu-id="e9013-406">Lägg till en ny datakälla som ska användas för att komma åt KMAnswer-registret, där varje post representerar ett enda svar på en fråga i en enkät:</span><span class="sxs-lookup"><span data-stu-id="e9013-406">Add a new data source try that will be used to access the KMAnswer table, where every record represents a single answer to a question in a questionnaire:</span></span>

    1. <span data-ttu-id="e9013-407">I fönstret **Datakällor** välj **Lägg till rot**.</span><span class="sxs-lookup"><span data-stu-id="e9013-407">In the **Data sources** pane, select **Add root**.</span></span>
    2. <span data-ttu-id="e9013-408">I fältet **Namn** ange **Svar**.</span><span class="sxs-lookup"><span data-stu-id="e9013-408">In the **Name** field, enter **Answer**.</span></span>
    3. <span data-ttu-id="e9013-409">I fältet **Tabell** ange **KMAnswer**.</span><span class="sxs-lookup"><span data-stu-id="e9013-409">In the **Table** field, enter **KMAnswer**.</span></span>
    4. <span data-ttu-id="e9013-410">Klicka på **OK** om du vill lägga till den nya datakällan.</span><span class="sxs-lookup"><span data-stu-id="e9013-410">Select **OK** to add the new data source.</span></span>

7. <span data-ttu-id="e9013-411">I fönstret **Datakälltyper** välj **Funktioner\\Beräknade fält**.</span><span class="sxs-lookup"><span data-stu-id="e9013-411">In the **Data source types** pane, select **Functions\\Calculated field**.</span></span>
8. <span data-ttu-id="e9013-412">Lägg till ett nytt beräknat fält som ska användas för att komma åt en post i KMQuestionResultGroup-registret från alla poster i det överordnade KMCollection-registret:</span><span class="sxs-lookup"><span data-stu-id="e9013-412">Add a new calculated field that will be used to access a record of the KMQuestionResultGroup table from every record of the parent KMCollection table:</span></span>

    1. <span data-ttu-id="e9013-413">I fönstret **Datakällor** välj **Enkät**.</span><span class="sxs-lookup"><span data-stu-id="e9013-413">In the **Data sources** pane, select **Questionnaire**.</span></span>
    2. <span data-ttu-id="e9013-414">Markera **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="e9013-414">Select **Add**.</span></span>
    3. <span data-ttu-id="e9013-415">I dialogrutan i fältet **Namn** ange **\$ResultGroup**.</span><span class="sxs-lookup"><span data-stu-id="e9013-415">In the dialog box, in the **Name** field, enter **\$ResultGroup**.</span></span>
    4. <span data-ttu-id="e9013-416">Välj **Redigera recept**.</span><span class="sxs-lookup"><span data-stu-id="e9013-416">Select **Edit formula**.</span></span>
    5. <span data-ttu-id="e9013-417">I [ER-formelredigeraren](general-electronic-reporting-formula-designer.md), i fältet **Formel** ange **FIRSTORNULL(\@.'\<Relations'.KMQuestionResultGroup)** för att använda [sökväg](er-formula-language.md#paths) för 1:n-relation mellan register KMCollection och KMQuestionResultGroup.</span><span class="sxs-lookup"><span data-stu-id="e9013-417">In the [ER formula editor](general-electronic-reporting-formula-designer.md), in the **Formula** field, enter **FIRSTORNULL(\@.'\<Relations'.KMQuestionResultGroup)** to use the [path](er-formula-language.md#paths) of the one-to-many relation between the KMCollection and KMQuestionResultGroup tables.</span></span>
    6. <span data-ttu-id="e9013-418">Markera **Spara** och stäng sedan formelredigeraren.</span><span class="sxs-lookup"><span data-stu-id="e9013-418">Select **Save**, and close the formula editor.</span></span>
    7. <span data-ttu-id="e9013-419">Klicka på **OK** om du vill lägga till nya beräknade fält.</span><span class="sxs-lookup"><span data-stu-id="e9013-419">Select **OK** to add the new calculated field.</span></span>

9. <span data-ttu-id="e9013-420">I fönstret **Datakälltyper** välj **Funktioner\\Beräknade fält**.</span><span class="sxs-lookup"><span data-stu-id="e9013-420">In the **Data source types** pane, select **Functions\\Calculated field**.</span></span>
10. <span data-ttu-id="e9013-421">Lägg till ett nytt beräknat fält som ska användas för att komma åt poster i KMQuestion-registret från alla poster i det överordnade KMCollectionQuestion-registret:</span><span class="sxs-lookup"><span data-stu-id="e9013-421">Add a new calculated field that will be used to access question records of the KMQuestion table from every record of the parent KMCollectionQuestion table:</span></span>

    1. <span data-ttu-id="e9013-422">I fönstret **Datakällor** välj **Enkät**.</span><span class="sxs-lookup"><span data-stu-id="e9013-422">In the **Data sources** pane, select **Questionnaire**.</span></span>
    2. <span data-ttu-id="e9013-423">Expandera noden **\<relationer** som innehåller 1:n-relationer i KMCollection-registret.</span><span class="sxs-lookup"><span data-stu-id="e9013-423">Expand the **\<Relations** node that contains one-to-many relations of the KMCollection table.</span></span>
    3. <span data-ttu-id="e9013-424">Välj relaterat **KMCollectionQuestion**-register och välj sedan **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="e9013-424">Select the related **KMCollectionQuestion** table, and then select **Add**.</span></span>
    4. <span data-ttu-id="e9013-425">I dialogrutan i fältet **Namn** ange **\$Fråga**.</span><span class="sxs-lookup"><span data-stu-id="e9013-425">In the dialog box, in the **Name** field, enter **\$Question**.</span></span>
    5. <span data-ttu-id="e9013-426">Välj **Redigera recept**.</span><span class="sxs-lookup"><span data-stu-id="e9013-426">Select **Edit formula**.</span></span>
    6. <span data-ttu-id="e9013-427">I formelredigeraren i fältet **Formel** ange **FIRSTORNULL (FILTER(Question, Question.kmQuestionId = \@.kmQuestionId))** för att returnera lämpliga frågerader från KMQuestion-registret.</span><span class="sxs-lookup"><span data-stu-id="e9013-427">In the formula editor, in the **Formula** field, enter **FIRSTORNULL (FILTER(Question, Question.kmQuestionId = \@.kmQuestionId))** to return the appropriate question records from the KMQuestion table.</span></span>
    7. <span data-ttu-id="e9013-428">Markera **Spara** och stäng sedan formelredigeraren.</span><span class="sxs-lookup"><span data-stu-id="e9013-428">Select **Save**, and close the formula editor.</span></span>
    8. <span data-ttu-id="e9013-429">Klicka på **OK** om du vill lägga till nya beräknade fält.</span><span class="sxs-lookup"><span data-stu-id="e9013-429">Select **OK** to add the new calculated field.</span></span>

11. <span data-ttu-id="e9013-430">I fönstret **Datakälltyper** välj **Funktioner\\Beräknade fält**.</span><span class="sxs-lookup"><span data-stu-id="e9013-430">In the **Data source types** pane, select **Functions\\Calculated field**.</span></span>
12. <span data-ttu-id="e9013-431">Lägg till ett nytt beräknat fält som ska användas för att komma åt svarsposter i KMAnswer-registret från alla poster i det överordnade KMQuestion-registret:</span><span class="sxs-lookup"><span data-stu-id="e9013-431">Add a new calculated field that will be used to access answer records of the KMAnswer table from every record of the parent KMQuestion table:</span></span>

    1. <span data-ttu-id="e9013-432">I fönstret **Datakällor** välj **enkät.\<Relations.KMCollectionQuestion.\$fråga** och välj sedan **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="e9013-432">In the **Data sources** pane, select **Questionnaire.\<Relations.KMCollectionQuestion.\$Question**, and then select **Add**.</span></span>
    2. <span data-ttu-id="e9013-433">I dialogrutan i fältet **Namn** ange **\$Svar**.</span><span class="sxs-lookup"><span data-stu-id="e9013-433">In the dialog box, in the **Name** field, enter **\$Answer**.</span></span>
    3. <span data-ttu-id="e9013-434">Välj **Redigera recept**.</span><span class="sxs-lookup"><span data-stu-id="e9013-434">Select **Edit formula**.</span></span>
    4. <span data-ttu-id="e9013-435">I formelredigeraren i fältet **Formel** ange **FILTER (Answer, Answer.kmAnswerCollectionId = \@.kmAnswerCollectionId)** för att returnera lämpliga svarsrader från KMAnswer-registret.</span><span class="sxs-lookup"><span data-stu-id="e9013-435">In the formula editor, in the **Formula** field, enter **FILTER (Answer, Answer.kmAnswerCollectionId = \@.kmAnswerCollectionId)** to return the appropriate answer records from the KMAnswer table.</span></span>
    5. <span data-ttu-id="e9013-436">Markera **Spara** och stäng sedan formelredigeraren.</span><span class="sxs-lookup"><span data-stu-id="e9013-436">Select **Save**, and close the formula editor.</span></span>
    6. <span data-ttu-id="e9013-437">Klicka på **OK** om du vill lägga till nya beräknade fält.</span><span class="sxs-lookup"><span data-stu-id="e9013-437">Select **OK** to add the new calculated field.</span></span>

13. <span data-ttu-id="e9013-438">I fönstret **Datakälltyper** välj **Dynamics 365 for Operations\\register**.</span><span class="sxs-lookup"><span data-stu-id="e9013-438">In the **Data source types** pane, select **Dynamics 365 for Operations\\Table**.</span></span>
14. <span data-ttu-id="e9013-439">Lägg till en ny datakälla som ska användas för att komma åt metoder i CompanyInfo-registret.</span><span class="sxs-lookup"><span data-stu-id="e9013-439">Add a new data source that will be used to access methods of the CompanyInfo table.</span></span> <span data-ttu-id="e9013-440">Observera att metoden **find()** i det här registret returnerar en post som representerar ett företag för den aktuella Finance-instansen som den här mappningen anropas i kontexten för.</span><span class="sxs-lookup"><span data-stu-id="e9013-440">Note that the **find()** method of this table returns a record that represents a company of the current Finance instance that this mapping is called in the context of.</span></span>

    1. <span data-ttu-id="e9013-441">I fönstret **Datakällor** välj **Lägg till rot**.</span><span class="sxs-lookup"><span data-stu-id="e9013-441">In the **Data sources** pane, select **Add root**.</span></span>
    2. <span data-ttu-id="e9013-442">I dialogrutan i fältet **Namn**, ange **CompanyInfo**.</span><span class="sxs-lookup"><span data-stu-id="e9013-442">In the dialog box, in the **Name** field, enter **CompanyInfo**.</span></span>
    3. <span data-ttu-id="e9013-443">I fältet **Tabell** ange **CompanyInfo**.</span><span class="sxs-lookup"><span data-stu-id="e9013-443">In the **Table** field, enter **CompanyInfo**.</span></span>
    4. <span data-ttu-id="e9013-444">Klicka på **OK** om du vill lägga till den nya datakällan.</span><span class="sxs-lookup"><span data-stu-id="e9013-444">Select **OK** to add the new data source.</span></span>

#### <a name="add-data-sources-to-access-application-enumerations"></a><a name="AddMmDataSource2"></a><span data-ttu-id="e9013-445">Lägga till datakällor för att öppna programuppräkningar</span><span class="sxs-lookup"><span data-stu-id="e9013-445">Add data sources to access application enumerations</span></span>

<span data-ttu-id="e9013-446">Du måste konfigurera datakällor för att få åtkomst till programuppräkningar och jämföra deras värden med värden i fälten för typen **uppräkning** i programtabellerna.</span><span class="sxs-lookup"><span data-stu-id="e9013-446">You must configure data sources to access application enumerations and compare their values with values of fields of the **Enumeration** type in the application tables.</span></span> <span data-ttu-id="e9013-447">Du måste använda resultatet av jämförelsen för att fylla i lämpliga fält i datamodellen.</span><span class="sxs-lookup"><span data-stu-id="e9013-447">You must use the result of the comparison to fill in appropriate fields of the data model.</span></span>

1. <span data-ttu-id="e9013-448">På sidan **Modellmappingsdesigner** i fönstret **Datakälltyper** väljer du **Dynamics 365 for Operations\\Uppräkning**.</span><span class="sxs-lookup"><span data-stu-id="e9013-448">On the **Model mapping designer** page, in the **Data source types** pane, select **Dynamics 365 for Operations\\Enumeration**.</span></span>
2. <span data-ttu-id="e9013-449">Lägg till en ny datakälla som ska användas för att komma åt värden i uppräkningen **EnumAppNoYes**:</span><span class="sxs-lookup"><span data-stu-id="e9013-449">Add a new data source that will be used to access values of the **EnumAppNoYes** enumeration:</span></span>

    1. <span data-ttu-id="e9013-450">I fönstret **Datakällor** välj **Lägg till rot**.</span><span class="sxs-lookup"><span data-stu-id="e9013-450">In the **Data sources** pane, select **Add root**.</span></span>
    2. <span data-ttu-id="e9013-451">I dialogrutan i fältet **Namn**, ange **EnumAppNoYes**.</span><span class="sxs-lookup"><span data-stu-id="e9013-451">In the dialog box, in the **Name** field, enter **EnumAppNoYes**.</span></span>
    3. <span data-ttu-id="e9013-452">I fältet **Uppräkning** ange **NoYes**.</span><span class="sxs-lookup"><span data-stu-id="e9013-452">In the **Enumeration** field, enter **NoYes**.</span></span>
    4. <span data-ttu-id="e9013-453">Klicka på **OK** om du vill lägga till den nya datakällan.</span><span class="sxs-lookup"><span data-stu-id="e9013-453">Select **OK** to add the new data source.</span></span>

3. <span data-ttu-id="e9013-454">I fönstret **Datakälltyper** välj **Dynamics 365 for Operations\\Uppräkning**.</span><span class="sxs-lookup"><span data-stu-id="e9013-454">In the **Data source types** pane, select **Dynamics 365 for Operations\\Enumeration**.</span></span>
4. <span data-ttu-id="e9013-455">Lägg till en ny datakälla som ska användas för att komma åt värden i uppräkningen **KMCollectionQuestionMode**:</span><span class="sxs-lookup"><span data-stu-id="e9013-455">Add a new data source that will be used to access the values of the **KMCollectionQuestionMode** enumeration:</span></span>

    1. <span data-ttu-id="e9013-456">I fönstret **Datakällor** välj **Lägg till rot**.</span><span class="sxs-lookup"><span data-stu-id="e9013-456">In the **Data sources** pane, select **Add root**.</span></span>
    2. <span data-ttu-id="e9013-457">Ange **KMCollectionQuestionMode** i dialogrutan i fältet **namn**.</span><span class="sxs-lookup"><span data-stu-id="e9013-457">In the dialog box, in the **Name** field, enter **EnumAppQuestionOrder**.</span></span>
    3. <span data-ttu-id="e9013-458">I fältet **Uppräkning** ange **KMCollectionQuestionMode**.</span><span class="sxs-lookup"><span data-stu-id="e9013-458">In the **Enumeration** field, enter **KMCollectionQuestionMode**.</span></span>
    4. <span data-ttu-id="e9013-459">Klicka på **OK** om du vill lägga till den nya datakällan.</span><span class="sxs-lookup"><span data-stu-id="e9013-459">Select **OK** to add the new data source.</span></span>

#### <a name="add-er-labels-to-generate-a-report-in-a-specified-language"></a><a name="AddMmLabels"></a><span data-ttu-id="e9013-460">Lägga till ER-etiketter för att generera en rapport på ett angivet språk</span><span class="sxs-lookup"><span data-stu-id="e9013-460">Add ER labels to generate a report in a specified language</span></span>

<span data-ttu-id="e9013-461">Du kan lägga till ER-etiketter för att konfigurera vissa av dina datakällor för att returnera värden som är beroende av språket som definieras i kontexten för modellmappningens anrop.</span><span class="sxs-lookup"><span data-stu-id="e9013-461">You can add ER labels to configure some of your data sources to return values that depend on the language that is defined in the context of the model mapping's call.</span></span>

1. <span data-ttu-id="e9013-462">På sidan **Modellmappingsdesigner** i fönstret **Datakällor** väljer du **Svar** och sedan **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="e9013-462">On the **Model mapping designer** page, in the **Data sources** pane, select **Answer**, and then select **Edit**.</span></span>
2. <span data-ttu-id="e9013-463">Aktivera fältet **etikett**.</span><span class="sxs-lookup"><span data-stu-id="e9013-463">Activate the **Label** field.</span></span>
3. <span data-ttu-id="e9013-464">Välj **översätt**.</span><span class="sxs-lookup"><span data-stu-id="e9013-464">Select **Translate**.</span></span>
4. <span data-ttu-id="e9013-465">I dialogrutan **Textöversättning** gör följande:</span><span class="sxs-lookup"><span data-stu-id="e9013-465">In the **Text translation** dialog box, follow these steps:</span></span>

    1. <span data-ttu-id="e9013-466">I fältet **Etikett-ID** anger du **PositiveAnswer**.</span><span class="sxs-lookup"><span data-stu-id="e9013-466">In the **Label Id** field, enter **PositiveAnswer**.</span></span>
    2. <span data-ttu-id="e9013-467">I fältet **text på standardspråk** anger du **Ja**.</span><span class="sxs-lookup"><span data-stu-id="e9013-467">In the **Text in default language** field, enter **Yes**.</span></span>
    3. <span data-ttu-id="e9013-468">Välj **översätt**.</span><span class="sxs-lookup"><span data-stu-id="e9013-468">Select **Translate**.</span></span>
    4. <span data-ttu-id="e9013-469">I fältet **Etikett-ID** anger du **NegativeAnswer**.</span><span class="sxs-lookup"><span data-stu-id="e9013-469">In the **Label Id** field, enter **NegativeAnswer**.</span></span>
    5. <span data-ttu-id="e9013-470">I fältet **text på standardspråk** anger du **Nej**.</span><span class="sxs-lookup"><span data-stu-id="e9013-470">In the **Text in default language** field, enter **No**.</span></span>
    6. <span data-ttu-id="e9013-471">Välj **översätt**.</span><span class="sxs-lookup"><span data-stu-id="e9013-471">Select **Translate**.</span></span>

5. <span data-ttu-id="e9013-472">Stäng dialogrutan **textöversättning**.</span><span class="sxs-lookup"><span data-stu-id="e9013-472">Close the **Text translation** dialog box.</span></span>
6. <span data-ttu-id="e9013-473">Välj **Avbryt**.</span><span class="sxs-lookup"><span data-stu-id="e9013-473">Select **Cancel**.</span></span>

![Lägga till ER-etiketter för redigerbar modellmappning](./media/er-quick-start1-adding-labels.png)

<span data-ttu-id="e9013-475">Du har bara angett ER-etiketter för standardspråket.</span><span class="sxs-lookup"><span data-stu-id="e9013-475">You've entered ER labels only for the default language.</span></span> <span data-ttu-id="e9013-476">Information om hur ER-etiketter kan översättas till andra språk finns i [utforma flerspråkiga rapporter](er-design-multilingual-reports.md).</span><span class="sxs-lookup"><span data-stu-id="e9013-476">For information about how ER labels can be translated into other languages, see [Design multilingual reports](er-design-multilingual-reports.md).</span></span>

#### <a name="add-a-data-source-to-transform-the-results-of-comparing-enumeration-values-to-a-text-value"></a><a name="AddMmDataSource3"></a><span data-ttu-id="e9013-477">Lägga till en datakälla som transformerar resultaten från att jämföra uppräkningsvärden till ett textvärde</span><span class="sxs-lookup"><span data-stu-id="e9013-477">Add a data source to transform the results of comparing enumeration values to a text value</span></span>

<span data-ttu-id="e9013-478">Eftersom du måste transformera resultaten av jämförelsen mellan uppräkningsvärden och textvärden flera gånger för differenskällor kan det vara en bra idé att konfigurera den här logiken som en enda datakälla.</span><span class="sxs-lookup"><span data-stu-id="e9013-478">Because you must transform the results of the comparison between enumeration values and text values several times for difference sources, it's a good idea to configure this logic as a single data source.</span></span> <span data-ttu-id="e9013-479">Om du vill kunna använda datakällan igen måste du dock konfigurera den som parametriserad datakälla.</span><span class="sxs-lookup"><span data-stu-id="e9013-479">However, to make this data source reusable, you must then configure it as the parametrized data source.</span></span> <span data-ttu-id="e9013-480">För mer information, se [Stöd parameteranrop till ER-datakällor för beräknad fälttyp](er-calculated-field-type.md).</span><span class="sxs-lookup"><span data-stu-id="e9013-480">For more information, see [Support parameterized calls of ER data sources of the Calculated field type](er-calculated-field-type.md).</span></span>

1. <span data-ttu-id="e9013-481">På sidan **Modellmappingsdesigner** i fönstret **Datakälltyper** väljer du **Allmänt\\Tom behållare**.</span><span class="sxs-lookup"><span data-stu-id="e9013-481">On the **Model mapping designer** page, in the **Data source types** pane, select **General\\Empty container**.</span></span>
2. <span data-ttu-id="e9013-482">Lägg till en ny datakälla för behållare:</span><span class="sxs-lookup"><span data-stu-id="e9013-482">Add a new container data source:</span></span>

    1. <span data-ttu-id="e9013-483">I fönstret **Datakällor** välj **Lägg till rot**.</span><span class="sxs-lookup"><span data-stu-id="e9013-483">In the **Data sources** pane, select **Add root**.</span></span>
    2. <span data-ttu-id="e9013-484">I dialogrutan i fältet **Namn**, ange **Stödprocess**.</span><span class="sxs-lookup"><span data-stu-id="e9013-484">In the dialog box, in the **Name** field, enter **Helper**.</span></span>
    3. <span data-ttu-id="e9013-485">Klicka på **OK** om du vill lägga till den nya datakällan för behållare.</span><span class="sxs-lookup"><span data-stu-id="e9013-485">Select **OK** to add the new container data source.</span></span>

3. <span data-ttu-id="e9013-486">I fönstret **Datakälltyper** välj **Funktioner\\Beräknade fält**.</span><span class="sxs-lookup"><span data-stu-id="e9013-486">In the **Data source types** pane, select **Functions\\Calculated field**.</span></span>
4. <span data-ttu-id="e9013-487">Lägg till en ny datakälla:</span><span class="sxs-lookup"><span data-stu-id="e9013-487">Add a new data source:</span></span>

    1. <span data-ttu-id="e9013-488">Välj **Stödprocess** i fönstret **Datakällor**.</span><span class="sxs-lookup"><span data-stu-id="e9013-488">In the **Data sources** pane, select **Helper**.</span></span>
    2. <span data-ttu-id="e9013-489">Markera **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="e9013-489">Select **Add**.</span></span>
    3. <span data-ttu-id="e9013-490">Ange **NoYesEnumToString** i dialogrutan i fältet **namn**.</span><span class="sxs-lookup"><span data-stu-id="e9013-490">In the dialog box, in the **Name** field, enter **NoYesEnumToString**.</span></span>
    4. <span data-ttu-id="e9013-491">Välj **Redigera recept**.</span><span class="sxs-lookup"><span data-stu-id="e9013-491">Select **Edit formula**.</span></span>
    5. <span data-ttu-id="e9013-492">Välj **parametrar** i formelredigeraren.</span><span class="sxs-lookup"><span data-stu-id="e9013-492">In the formula editor, select **Parameters**.</span></span>
    6. <span data-ttu-id="e9013-493">Följ dessa steg för att ange parametrar för det konfigurerade uttrycket:</span><span class="sxs-lookup"><span data-stu-id="e9013-493">Follow these steps to specify parameters for the configured expression:</span></span>

        1. <span data-ttu-id="e9013-494">Välj **Ny**.</span><span class="sxs-lookup"><span data-stu-id="e9013-494">Select **New**.</span></span>
        2. <span data-ttu-id="e9013-495">I dialogrutan i fältet **Namn**, ange **Argument**.</span><span class="sxs-lookup"><span data-stu-id="e9013-495">In the dialog box, in the **Name** field, enter **Argument**.</span></span>
        3. <span data-ttu-id="e9013-496">I fältet **Typ** välj datatypen **Boolesk**.</span><span class="sxs-lookup"><span data-stu-id="e9013-496">In the **Type** field, select the **Boolean** data type.</span></span>
        4. <span data-ttu-id="e9013-497">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="e9013-497">Select **OK**.</span></span>

    7. <span data-ttu-id="e9013-498">I fältet **Formel** ange **IF (Argument = true, \@"GER\_LABEL:PositiveAnswer", \@"GER\_LABEL:NegativeAnswer")** du vill returnera texten i motsvarande ER-etikett, beroende på språket för körningskontexten och värdet för den angivna parametern.</span><span class="sxs-lookup"><span data-stu-id="e9013-498">In the **Formula** field, enter **IF (Argument = true, \@"GER\_LABEL:PositiveAnswer", \@"GER\_LABEL:NegativeAnswer")** to return the text of the appropriate ER label, depending on the language of the execution context and value of the specified parameter.</span></span>
    8. <span data-ttu-id="e9013-499">Markera **Spara** och stäng sedan formelredigeraren.</span><span class="sxs-lookup"><span data-stu-id="e9013-499">Select **Save**, and close the formula editor.</span></span>
    9. <span data-ttu-id="e9013-500">Klicka på **OK** om du vill lägga till den nya datakällan.</span><span class="sxs-lookup"><span data-stu-id="e9013-500">Select **OK** to add the new data source.</span></span>

![Konfigurerad modellmappning i ER-modellmappningsdesigner](./media/er-quick-start1-added-data-sources.png)

#### <a name="bind-data-sources-to-data-model-fields"></a><a name="AddMmBindings1"></a><span data-ttu-id="e9013-502">Binda datakällor till fält för datamodell</span><span class="sxs-lookup"><span data-stu-id="e9013-502">Bind data sources to data model fields</span></span>

<span data-ttu-id="e9013-503">Du måste binda de konfigurerade datakällorna till fälten i datamodellen för att ange hur datamodellen ska fyllas i med programdata vid körning.</span><span class="sxs-lookup"><span data-stu-id="e9013-503">You must bind the configured data sources to the fields of the data model to specify how the data model will by filled in with application data at runtime.</span></span>

1. <span data-ttu-id="e9013-504">På sidan **Modellmappingsdesigner** i fönstret **Datamodell** väljer du **CompanyName**.</span><span class="sxs-lookup"><span data-stu-id="e9013-504">On the **Model mapping designer** page, in the **Data model** pane, select **CompanyName**.</span></span>
2. <span data-ttu-id="e9013-505">I fönstret **Datakällor** expanderar **CompanyInfo** och följer sedan de här stegen:</span><span class="sxs-lookup"><span data-stu-id="e9013-505">In the **Data sources** pane, expand **CompanyInfo**, and then follow these steps:</span></span>

    1. <span data-ttu-id="e9013-506">Expandera noden **CompanyInfo.find()** som representerar **find()**-metoden i CompanyInfo-registret.</span><span class="sxs-lookup"><span data-stu-id="e9013-506">Expand the **CompanyInfo.find()** node that represents the **find()** method of the CompanyInfo table.</span></span>
    2. <span data-ttu-id="e9013-507">Välj **CompanyInfo.find().Name**.</span><span class="sxs-lookup"><span data-stu-id="e9013-507">Select **CompanyInfo.find().Name**.</span></span>
    3. <span data-ttu-id="e9013-508">Välj **Bind** om du vill fylla i namnet på det företag som den konfigurerade modellmappningen anropas i kontexten vid körning.</span><span class="sxs-lookup"><span data-stu-id="e9013-508">Select **Bind** to fill in the name of the company that the configured model mapping is called in the context of at runtime.</span></span>

3. <span data-ttu-id="e9013-509">I fönstret **Datamodell** välj **Enkät**.</span><span class="sxs-lookup"><span data-stu-id="e9013-509">In the **Data model** pane, select **Questionnaire**.</span></span>
4. <span data-ttu-id="e9013-510">I fönstret **Datakällor** välj **Enkät** och välj sedan **Bind** för att fylla i enkätposter.</span><span class="sxs-lookup"><span data-stu-id="e9013-510">In the **Data sources** pane, select **Questionnaire**, and then select **Bind** to fill in questionnaire records.</span></span>
5. <span data-ttu-id="e9013-511">I fönstret **Datamodell** expanderar du **Enkät** och följer sedan de här stegen:</span><span class="sxs-lookup"><span data-stu-id="e9013-511">In the **Data model** pane, expand **Questionnaire**, and then follow these steps:</span></span>

    1. <span data-ttu-id="e9013-512">I fönstret **Datamodell** välj **Aktiv**.</span><span class="sxs-lookup"><span data-stu-id="e9013-512">In the **Data model** pane, select **Active**.</span></span>
    2. <span data-ttu-id="e9013-513">I fönstret **Datamodell** välj **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="e9013-513">In the **Data model** pane, select **Edit**.</span></span>
    3. <span data-ttu-id="e9013-514">I fältet **Formel** ange **Helper.NoYesEnumToString (\@.Active = EnumAppNoYes.Yes)** om du vill fylla det textberoende och språkberoende resultatet i jämförelsen mellan uppräkningsvärden.</span><span class="sxs-lookup"><span data-stu-id="e9013-514">In the **Formula** field, enter **Helper.NoYesEnumToString (\@.Active = EnumAppNoYes.Yes)** to fill the text-dependent and language-dependent result of the comparison between enumeration values.</span></span>

6. <span data-ttu-id="e9013-515">Fortsätt att binda datakällor till datamodellfält på samma sätt tills du uppnår följande resultat.</span><span class="sxs-lookup"><span data-stu-id="e9013-515">Continue to bind data sources to data model fields in the same manner until you achieve the following result.</span></span>

    | <span data-ttu-id="e9013-516">Sökväg för fält</span><span class="sxs-lookup"><span data-stu-id="e9013-516">Field path</span></span>                                              | <span data-ttu-id="e9013-517">Datatyp</span><span class="sxs-lookup"><span data-stu-id="e9013-517">Data type</span></span>   | <span data-ttu-id="e9013-518">Åtgärd</span><span class="sxs-lookup"><span data-stu-id="e9013-518">Action</span></span> | <span data-ttu-id="e9013-519">Bindningsuttryck</span><span class="sxs-lookup"><span data-stu-id="e9013-519">Binding expression</span></span> |
    |---------------------------------------------------------|-------------|--------|--------------------|
    | <span data-ttu-id="e9013-520">CompanyName</span><span class="sxs-lookup"><span data-stu-id="e9013-520">CompanyName</span></span>                                             | <span data-ttu-id="e9013-521">Sträng</span><span class="sxs-lookup"><span data-stu-id="e9013-521">String</span></span>      | <span data-ttu-id="e9013-522">Bind</span><span class="sxs-lookup"><span data-stu-id="e9013-522">Bind</span></span>   | <span data-ttu-id="e9013-523">CompanyInfo.'find()'.Name</span><span class="sxs-lookup"><span data-stu-id="e9013-523">CompanyInfo.'find()'.Name</span></span> |
    | <span data-ttu-id="e9013-524">Enkät</span><span class="sxs-lookup"><span data-stu-id="e9013-524">Questionnaire</span></span>                                           | <span data-ttu-id="e9013-525">Postlista</span><span class="sxs-lookup"><span data-stu-id="e9013-525">Record list</span></span> | <span data-ttu-id="e9013-526">Bind</span><span class="sxs-lookup"><span data-stu-id="e9013-526">Bind</span></span>   | <span data-ttu-id="e9013-527">Enkät</span><span class="sxs-lookup"><span data-stu-id="e9013-527">Questionnaire</span></span> |
    | <span data-ttu-id="e9013-528">Etikett\\Aktiv</span><span class="sxs-lookup"><span data-stu-id="e9013-528">Questionnaire\\Active</span></span>                                   | <span data-ttu-id="e9013-529">Sträng</span><span class="sxs-lookup"><span data-stu-id="e9013-529">String</span></span>      | <span data-ttu-id="e9013-530">Redigera</span><span class="sxs-lookup"><span data-stu-id="e9013-530">Edit</span></span>   | <span data-ttu-id="e9013-531">Helper.NoYesEnumToString(\@.active = EnumAppNoYes.Yes)</span><span class="sxs-lookup"><span data-stu-id="e9013-531">Helper.NoYesEnumToString(\@.active = EnumAppNoYes.Yes)</span></span> |
    | <span data-ttu-id="e9013-532">Enkät\\Kod</span><span class="sxs-lookup"><span data-stu-id="e9013-532">Questionnaire\\Code</span></span>                                     | <span data-ttu-id="e9013-533">Sträng</span><span class="sxs-lookup"><span data-stu-id="e9013-533">String</span></span>      | <span data-ttu-id="e9013-534">Bind</span><span class="sxs-lookup"><span data-stu-id="e9013-534">Bind</span></span>   | <span data-ttu-id="e9013-535">\@.kmCollectionId</span><span class="sxs-lookup"><span data-stu-id="e9013-535">\@.kmCollectionId</span></span> |
    | <span data-ttu-id="e9013-536">Enkät\\Beskrivning</span><span class="sxs-lookup"><span data-stu-id="e9013-536">Questionnaire\\Description</span></span>                              | <span data-ttu-id="e9013-537">Sträng</span><span class="sxs-lookup"><span data-stu-id="e9013-537">String</span></span>      | <span data-ttu-id="e9013-538">Bind</span><span class="sxs-lookup"><span data-stu-id="e9013-538">Bind</span></span>   | <span data-ttu-id="e9013-539">\@.Description</span><span class="sxs-lookup"><span data-stu-id="e9013-539">\@.Description</span></span> |
    | <span data-ttu-id="e9013-540">Questionnaire\\QuestionnaireType</span><span class="sxs-lookup"><span data-stu-id="e9013-540">Questionnaire\\QuestionnaireType</span></span>                        | <span data-ttu-id="e9013-541">Sträng</span><span class="sxs-lookup"><span data-stu-id="e9013-541">String</span></span>      | <span data-ttu-id="e9013-542">Bind</span><span class="sxs-lookup"><span data-stu-id="e9013-542">Bind</span></span>   | <span data-ttu-id="e9013-543">\@.'&gt;Relations'.kmCollectionTypeId.Description</span><span class="sxs-lookup"><span data-stu-id="e9013-543">\@.'&gt;Relations'.kmCollectionTypeId.Description</span></span> |
    | <span data-ttu-id="e9013-544">Questionnaire\\QuestionOrder</span><span class="sxs-lookup"><span data-stu-id="e9013-544">Questionnaire\\QuestionOrder</span></span>                            | <span data-ttu-id="e9013-545">Sträng</span><span class="sxs-lookup"><span data-stu-id="e9013-545">String</span></span>      | <span data-ttu-id="e9013-546">Redigera</span><span class="sxs-lookup"><span data-stu-id="e9013-546">Edit</span></span>   | <span data-ttu-id="e9013-547">CASE (\@.questionMode,</span><span class="sxs-lookup"><span data-stu-id="e9013-547">CASE (\@.questionMode,</span></span><br><span data-ttu-id="e9013-548">EnumAppQuestionOrder.Conditional, "Conditional",</span><span class="sxs-lookup"><span data-stu-id="e9013-548">EnumAppQuestionOrder.Conditional, "Conditional",</span></span><br><span data-ttu-id="e9013-549">EnumAppQuestionOrder.Random, "Slumpmässig (procent i enkät)",</span><span class="sxs-lookup"><span data-stu-id="e9013-549">EnumAppQuestionOrder.Random, "Random (percentage in questionnaire)",</span></span><br><span data-ttu-id="e9013-550">EnumAppQuestionOrder.RandomGroup, "Slumpmässig (procent i resultatgrupper)",</span><span class="sxs-lookup"><span data-stu-id="e9013-550">EnumAppQuestionOrder.RandomGroup, "Random (percentage in result groups)",</span></span><br><span data-ttu-id="e9013-551">EnumAppQuestionOrder.Sequence, "Sekventiell",</span><span class="sxs-lookup"><span data-stu-id="e9013-551">EnumAppQuestionOrder.Sequence, "Sequential",</span></span><br><span data-ttu-id="e9013-552">"")</span><span class="sxs-lookup"><span data-stu-id="e9013-552">"")</span></span> |
    | <span data-ttu-id="e9013-553">Questionnaire\\ResultsGroup</span><span class="sxs-lookup"><span data-stu-id="e9013-553">Questionnaire\\ResultsGroup</span></span>                             | <span data-ttu-id="e9013-554">Registrera</span><span class="sxs-lookup"><span data-stu-id="e9013-554">Record</span></span>      |        | |
    | <span data-ttu-id="e9013-555">Questionnaire\\ResultsGroup\\Code</span><span class="sxs-lookup"><span data-stu-id="e9013-555">Questionnaire\\ResultsGroup\\Code</span></span>                       | <span data-ttu-id="e9013-556">Sträng</span><span class="sxs-lookup"><span data-stu-id="e9013-556">String</span></span>      | <span data-ttu-id="e9013-557">Bind</span><span class="sxs-lookup"><span data-stu-id="e9013-557">Bind</span></span>   | <span data-ttu-id="e9013-558">\@.'\$ResultGroup'.kmQuestionResultGroupId</span><span class="sxs-lookup"><span data-stu-id="e9013-558">\@.'\$ResultGroup'.kmQuestionResultGroupId</span></span> |
    | <span data-ttu-id="e9013-559">Questionnaire\\ResultsGroup\\Description</span><span class="sxs-lookup"><span data-stu-id="e9013-559">Questionnaire\\ResultsGroup\\Description</span></span>                | <span data-ttu-id="e9013-560">Sträng</span><span class="sxs-lookup"><span data-stu-id="e9013-560">String</span></span>      | <span data-ttu-id="e9013-561">Bind</span><span class="sxs-lookup"><span data-stu-id="e9013-561">Bind</span></span>   | <span data-ttu-id="e9013-562">\@.'\$ResultGroup'.description</span><span class="sxs-lookup"><span data-stu-id="e9013-562">\@.'\$ResultGroup'.description</span></span> |
    | <span data-ttu-id="e9013-563">Questionnaire\\ResultsGroup\\MaxNumberOfPoints</span><span class="sxs-lookup"><span data-stu-id="e9013-563">Questionnaire\\ResultsGroup\\MaxNumberOfPoints</span></span>          | <span data-ttu-id="e9013-564">Realtal</span><span class="sxs-lookup"><span data-stu-id="e9013-564">Real</span></span>        | <span data-ttu-id="e9013-565">Bind</span><span class="sxs-lookup"><span data-stu-id="e9013-565">Bind</span></span>   | <span data-ttu-id="e9013-566">\@.'\$ResultGroup'.maxPoint</span><span class="sxs-lookup"><span data-stu-id="e9013-566">\@.'\$ResultGroup'.maxPoint</span></span> |
    | <span data-ttu-id="e9013-567">Questionnaire\\Question</span><span class="sxs-lookup"><span data-stu-id="e9013-567">Questionnaire\\Question</span></span>                                 | <span data-ttu-id="e9013-568">Postlista</span><span class="sxs-lookup"><span data-stu-id="e9013-568">Record list</span></span> | <span data-ttu-id="e9013-569">Bind</span><span class="sxs-lookup"><span data-stu-id="e9013-569">Bind</span></span>   | <span data-ttu-id="e9013-570">\@.'&lt;Relations'.KMCollectionQuestion</span><span class="sxs-lookup"><span data-stu-id="e9013-570">\@.'&lt;Relations'.KMCollectionQuestion</span></span> |
    | <span data-ttu-id="e9013-571">Questionnaire\\Question\\CollectionSequenceNumber</span><span class="sxs-lookup"><span data-stu-id="e9013-571">Questionnaire\\Question\\CollectionSequenceNumber</span></span>       | <span data-ttu-id="e9013-572">Heltal</span><span class="sxs-lookup"><span data-stu-id="e9013-572">Integer</span></span>     | <span data-ttu-id="e9013-573">Bind</span><span class="sxs-lookup"><span data-stu-id="e9013-573">Bind</span></span>   | <span data-ttu-id="e9013-574">\@.answerCollectionSequenceNumber</span><span class="sxs-lookup"><span data-stu-id="e9013-574">\@.answerCollectionSequenceNumber</span></span> |
    | <span data-ttu-id="e9013-575">Questionnaire\\Question\\Id</span><span class="sxs-lookup"><span data-stu-id="e9013-575">Questionnaire\\Question\\Id</span></span>                             | <span data-ttu-id="e9013-576">Sträng</span><span class="sxs-lookup"><span data-stu-id="e9013-576">String</span></span>      | <span data-ttu-id="e9013-577">Bind</span><span class="sxs-lookup"><span data-stu-id="e9013-577">Bind</span></span>   | <span data-ttu-id="e9013-578">\@.kmQuestionId</span><span class="sxs-lookup"><span data-stu-id="e9013-578">\@.kmQuestionId</span></span> |
    | <span data-ttu-id="e9013-579">Questionnaire\\Question\\MustBeCompleted</span><span class="sxs-lookup"><span data-stu-id="e9013-579">Questionnaire\\Question\\MustBeCompleted</span></span>                | <span data-ttu-id="e9013-580">Sträng</span><span class="sxs-lookup"><span data-stu-id="e9013-580">String</span></span>      | <span data-ttu-id="e9013-581">Redigera</span><span class="sxs-lookup"><span data-stu-id="e9013-581">Edit</span></span>   | <span data-ttu-id="e9013-582">Helper.NoYesEnumToString(\@.mandatory = EnumAppNoYes.Yes)</span><span class="sxs-lookup"><span data-stu-id="e9013-582">Helper.NoYesEnumToString(\@.mandatory = EnumAppNoYes.Yes)</span></span> |
    | <span data-ttu-id="e9013-583">Questionnaire\\Question\\PrimaryQuestion</span><span class="sxs-lookup"><span data-stu-id="e9013-583">Questionnaire\\Question\\PrimaryQuestion</span></span>                | <span data-ttu-id="e9013-584">Sträng</span><span class="sxs-lookup"><span data-stu-id="e9013-584">String</span></span>      | <span data-ttu-id="e9013-585">Bind</span><span class="sxs-lookup"><span data-stu-id="e9013-585">Bind</span></span>   | <span data-ttu-id="e9013-586">\@.parentQuestionId</span><span class="sxs-lookup"><span data-stu-id="e9013-586">\@.parentQuestionId</span></span> |
    | <span data-ttu-id="e9013-587">Questionnaire\\Question\\SequenceNumber</span><span class="sxs-lookup"><span data-stu-id="e9013-587">Questionnaire\\Question\\SequenceNumber</span></span>                 | <span data-ttu-id="e9013-588">Heltal</span><span class="sxs-lookup"><span data-stu-id="e9013-588">Integer</span></span>     | <span data-ttu-id="e9013-589">Bind</span><span class="sxs-lookup"><span data-stu-id="e9013-589">Bind</span></span>   | <span data-ttu-id="e9013-590">\@.SequenceNumber</span><span class="sxs-lookup"><span data-stu-id="e9013-590">\@.SequenceNumber</span></span> |
    | <span data-ttu-id="e9013-591">Questionnaire\\Question\\Text</span><span class="sxs-lookup"><span data-stu-id="e9013-591">Questionnaire\\Question\\Text</span></span>                           | <span data-ttu-id="e9013-592">Sträng</span><span class="sxs-lookup"><span data-stu-id="e9013-592">String</span></span>      | <span data-ttu-id="e9013-593">Bind</span><span class="sxs-lookup"><span data-stu-id="e9013-593">Bind</span></span>   | <span data-ttu-id="e9013-594">\@.'\$Question'.text</span><span class="sxs-lookup"><span data-stu-id="e9013-594">\@.'\$Question'.text</span></span> |
    | <span data-ttu-id="e9013-595">Questionnaire\\Question\\Answer</span><span class="sxs-lookup"><span data-stu-id="e9013-595">Questionnaire\\Question\\Answer</span></span>                         | <span data-ttu-id="e9013-596">Postlista</span><span class="sxs-lookup"><span data-stu-id="e9013-596">Record list</span></span> | <span data-ttu-id="e9013-597">Bind</span><span class="sxs-lookup"><span data-stu-id="e9013-597">Bind</span></span>   | <span data-ttu-id="e9013-598">\@.'\$Question'.'\$Answer'</span><span class="sxs-lookup"><span data-stu-id="e9013-598">\@.'\$Question'.'\$Answer'</span></span> |
    | <span data-ttu-id="e9013-599">Questionnaire\\Question\\Answer\\CorrectAnswer</span><span class="sxs-lookup"><span data-stu-id="e9013-599">Questionnaire\\Question\\Answer\\CorrectAnswer</span></span>          | <span data-ttu-id="e9013-600">Sträng</span><span class="sxs-lookup"><span data-stu-id="e9013-600">String</span></span>      | <span data-ttu-id="e9013-601">Redigera</span><span class="sxs-lookup"><span data-stu-id="e9013-601">Edit</span></span>   | <span data-ttu-id="e9013-602">Helper.NoYesEnumToString(\@.correctAnswer = EnumAppNoYes.Yes)</span><span class="sxs-lookup"><span data-stu-id="e9013-602">Helper.NoYesEnumToString(\@.correctAnswer = EnumAppNoYes.Yes)</span></span> |
    | <span data-ttu-id="e9013-603">Questionnaire\\Question\\Answer\\Points</span><span class="sxs-lookup"><span data-stu-id="e9013-603">Questionnaire\\Question\\Answer\\Points</span></span>                 | <span data-ttu-id="e9013-604">Realtal</span><span class="sxs-lookup"><span data-stu-id="e9013-604">Real</span></span>        | <span data-ttu-id="e9013-605">Bind</span><span class="sxs-lookup"><span data-stu-id="e9013-605">Bind</span></span>   | <span data-ttu-id="e9013-606">\@.point</span><span class="sxs-lookup"><span data-stu-id="e9013-606">\@.point</span></span> |
    | <span data-ttu-id="e9013-607">Questionnaire\\Question\\Answer\\SequenceNumber</span><span class="sxs-lookup"><span data-stu-id="e9013-607">Questionnaire\\Question\\Answer\\SequenceNumber</span></span>         | <span data-ttu-id="e9013-608">Heltal</span><span class="sxs-lookup"><span data-stu-id="e9013-608">Integer</span></span>     | <span data-ttu-id="e9013-609">Bind</span><span class="sxs-lookup"><span data-stu-id="e9013-609">Bind</span></span>   | <span data-ttu-id="e9013-610">\@.sequenceNumber</span><span class="sxs-lookup"><span data-stu-id="e9013-610">\@.sequenceNumber</span></span> |
    | <span data-ttu-id="e9013-611">Questionnaire\\Question\\Answer\\Text</span><span class="sxs-lookup"><span data-stu-id="e9013-611">Questionnaire\\Question\\Answer\\Text</span></span>                   | <span data-ttu-id="e9013-612">Sträng</span><span class="sxs-lookup"><span data-stu-id="e9013-612">String</span></span>      | <span data-ttu-id="e9013-613">Bind</span><span class="sxs-lookup"><span data-stu-id="e9013-613">Bind</span></span>   | <span data-ttu-id="e9013-614">\@.text</span><span class="sxs-lookup"><span data-stu-id="e9013-614">\@.text</span></span> |

    <span data-ttu-id="e9013-615">Bilden nedan visar det slutliga tillståndet för den konfigurerade modellmappningen på sidan **modellmappningsdesigner**.</span><span class="sxs-lookup"><span data-stu-id="e9013-615">The following illustration shows the final state of the configured model mapping on the **Model mapping designer** page.</span></span>

    ![Helt konfigurerad modellmappning i ER-modellmappningsdesigner](./media/er-quick-start1-mapping2.png)

7. <span data-ttu-id="e9013-617">Spara ändringarna.</span><span class="sxs-lookup"><span data-stu-id="e9013-617">Save your changes.</span></span>
8. <span data-ttu-id="e9013-618">Stäng sidan **modellmappningsdesigner**.</span><span class="sxs-lookup"><span data-stu-id="e9013-618">Close the **Model mapping designer** page.</span></span>

#### <a name="complete-the-design-of-the-model-mapping"></a><a name="CompleteModelMapping"></a><span data-ttu-id="e9013-619">Färdigställa modellmappningens utformning</span><span class="sxs-lookup"><span data-stu-id="e9013-619">Complete the design of the model mapping</span></span>

1. <span data-ttu-id="e9013-620">Gå till **Organisationsadministration** \> **Elektronisk rapportering** \> **Konfigurationer**.</span><span class="sxs-lookup"><span data-stu-id="e9013-620">Go to **Organization administration** \> **Electronic reporting** \> **Configurations**.</span></span>
2. <span data-ttu-id="e9013-621">På sidan **konfigurationer** i konfigurationsträdet väljer du **enkätmappning**.</span><span class="sxs-lookup"><span data-stu-id="e9013-621">On the **Configurations** page, in the configuration tree, select **Questionnaire mapping**.</span></span>
3. <span data-ttu-id="e9013-622">På snabbfliken **Versioner** väljer du den konfigurationsversion som har statusen **Utkast**.</span><span class="sxs-lookup"><span data-stu-id="e9013-622">On the **Versions** FastTab, select the configuration version that has a status of **Draft**.</span></span>
4. <span data-ttu-id="e9013-623">Välj **Ändra status** \> **Slutför**.</span><span class="sxs-lookup"><span data-stu-id="e9013-623">Select **Change status** \> **Complete**.</span></span>

<span data-ttu-id="e9013-624">Status för version 1.1 av denna konfiguration ändras från **utkast** till **slutförd**.</span><span class="sxs-lookup"><span data-stu-id="e9013-624">The status of version 1.1 of this configuration is changed from **Draft** to **Completed**.</span></span> <span data-ttu-id="e9013-625">Version 1.1 kan inte längre ändras.</span><span class="sxs-lookup"><span data-stu-id="e9013-625">Version 1.1 can no longer be changed.</span></span> <span data-ttu-id="e9013-626">Den här versionen innehåller den konfigurerade modellmappningen och kan användas som grund för andra ER-konfigurationer.</span><span class="sxs-lookup"><span data-stu-id="e9013-626">This version contains the configured model mapping and can be used as the basis for other ER configurations.</span></span> <span data-ttu-id="e9013-627">Version 1.2 av denna konfiguration skapas och har statusen **utkast**.</span><span class="sxs-lookup"><span data-stu-id="e9013-627">Version 1.2 of this configuration is created and has a status of **Draft**.</span></span> <span data-ttu-id="e9013-628">Du kan redigera den här versionen för att justera konfigurationen **enkätmappningen**.</span><span class="sxs-lookup"><span data-stu-id="e9013-628">You can edit this version to adjust the **Questionnaire mapping** configuration.</span></span>

![Versioner av den redigerbara ER-konfigurationen på sidan konfigurationer](./media/er-quick-start1-mapping-configuration.png)

> [!NOTE]
> <span data-ttu-id="e9013-630">Den konfigurerade modellmappningen är din Finance-specifika implementering av den abstrakta datamodellen som representerar affärsdomän **enkät**.</span><span class="sxs-lookup"><span data-stu-id="e9013-630">The configured model mapping is your Finance-specific implementation of the abstract data model that represents the **Questionnaire** business domain.</span></span>

## <a name="design-a-template-for-a-custom-report"></a><a name="DesignReportTemplate"></a><span data-ttu-id="e9013-631">Utforma en mall för en anpassad rapport</span><span class="sxs-lookup"><span data-stu-id="e9013-631">Design a template for a custom report</span></span>

<span data-ttu-id="e9013-632">ER-ramverket använder fördefinierade mallar för att generera rapporter i Microsoft Office-format (Excel-arbetsböcker eller Word-dokument).</span><span class="sxs-lookup"><span data-stu-id="e9013-632">The ER framework uses predefined templates to generate reports in Microsoft Office formats (Excel workbooks or Word documents).</span></span> <span data-ttu-id="e9013-633">Medan den rapport som krävs skapas fylls en mall i med de data som krävs enligt det konfigurerade dataflöden.</span><span class="sxs-lookup"><span data-stu-id="e9013-633">While the required report is being generated, a template is filled in with required data according to the configured dataflow.</span></span> <span data-ttu-id="e9013-634">Därför måste du först designa en mall för din anpassade rapport.</span><span class="sxs-lookup"><span data-stu-id="e9013-634">Therefore, you must first design a template for your custom report.</span></span> <span data-ttu-id="e9013-635">Den här mallen måste vara utformad som en Excel-arbetsbok, vars struktur representerar layouten i en anpassad rapport.</span><span class="sxs-lookup"><span data-stu-id="e9013-635">This template must be designed as an Excel workbook, the structure of which represents the layout of a custom report.</span></span> <span data-ttu-id="e9013-636">Du måste namnge varje Excel-artikel som du tänker fylla i med nödvändiga data.</span><span class="sxs-lookup"><span data-stu-id="e9013-636">You must name every Excel item that you plan to fill in with required data.</span></span>

1. <span data-ttu-id="e9013-637">Hämta filen [enkätrapportmall.xslx](https://go.microsoft.com/fwlink/?linkid=851448) och spara den på den lokala datorn.</span><span class="sxs-lookup"><span data-stu-id="e9013-637">Download the [Questionnaires report template.xslx](https://go.microsoft.com/fwlink/?linkid=851448) file, and save it to your local computer.</span></span>
2. <span data-ttu-id="e9013-638">Öppna filen i Excel och granska arbetsbokens struktur.</span><span class="sxs-lookup"><span data-stu-id="e9013-638">Open the file in Excel, and review the structure of the workbook.</span></span>

<span data-ttu-id="e9013-639">Som visas i bilden nedan har den hämtade mallen utformats för att skriva ut angivna enkäter som visar en enkätfrågor tillsammans med lämpliga svar.</span><span class="sxs-lookup"><span data-stu-id="e9013-639">As the following illustration shows, the downloaded template has been designed to print specified questionnaires that present a questionnaire's questions together with appropriate answers.</span></span>

![Excel-mall för att skriva ut angivna enkäter](./media/er-quick-start1-template-layout.png)

<span data-ttu-id="e9013-641">Excel-namn har lagts till i den här mallen för ifyllning av enkätinformation.</span><span class="sxs-lookup"><span data-stu-id="e9013-641">Excel names have been added to this template to fill in the questionnaire details.</span></span> <span data-ttu-id="e9013-642">Du kan använda namnhanteraren för att granska Excel-namnen.</span><span class="sxs-lookup"><span data-stu-id="e9013-642">You can use Name Manager to review the Excel names.</span></span>

![Använda namnhanteraren för att granska Excel-namn i den medföljande Excel-mallen](./media/er-quick-start1-template-names.png)

<span data-ttu-id="e9013-644">Rapportetiketter har lagts till som fast text på engelska.</span><span class="sxs-lookup"><span data-stu-id="e9013-644">Report labels have been added as fixed text in the English language.</span></span> <span data-ttu-id="e9013-645">Du kan ersätta rapportetiketterna med nya Excel-namn som fyller i etiketterna med språkberoende text genom att använda etiketterna för återställningsformat [etikett](#AddMmLabels), på samma sätt som för språkberoende uttryck i den konfigurerade modellmappningen.</span><span class="sxs-lookup"><span data-stu-id="e9013-645">You can replace the report labels with new Excel names that fill in the labels with language-dependent text by using the ER format [labels](#AddMmLabels), as you did for language-dependent expressions in the configured model mapping.</span></span> <span data-ttu-id="e9013-646">I det här fallet måste du lägga till ER-etiketter i det redigerbara återställningsformatet.</span><span class="sxs-lookup"><span data-stu-id="e9013-646">In this case, ER labels must be added in the editable ER format.</span></span>

<span data-ttu-id="e9013-647">Som visas i bilden nedan har det anpassade rapporthuvudet angetts för att Excel ska kunna göra sidindelning.</span><span class="sxs-lookup"><span data-stu-id="e9013-647">As the following illustration shows, the custom report header has been specified to enable Excel to do paging.</span></span>

![Anpassat rapporthuvud i den angivna Excel-mallen](./media/er-quick-start1-template-header.png)

## <a name="design-a-format"></a><a name="DesignFormat"></a><span data-ttu-id="e9013-649">Designa ett format</span><span class="sxs-lookup"><span data-stu-id="e9013-649">Design a format</span></span>

<span data-ttu-id="e9013-650">Som användare i rollen funktionell konsult för elektronisk rapportering måste du skapa en ny ER-konfiguration som innehåller komponenten [format](general-electronic-reporting.md#FormatComponentOutbound).</span><span class="sxs-lookup"><span data-stu-id="e9013-650">As a user in the Electronic Reporting Functional Consultant role, you must create a new ER configuration that contains a [format](general-electronic-reporting.md#FormatComponentOutbound) component.</span></span> <span data-ttu-id="e9013-651">Du måste konfigurera formatkomponenten för att ange hur en rapportmall ska fyllas i med nödvändiga data vid körning.</span><span class="sxs-lookup"><span data-stu-id="e9013-651">You must configure the format component to specify how a report template will be filled in with required data at runtime.</span></span>

<span data-ttu-id="e9013-652">Genom att slutföra stegen i avsnittet [Importera en utformad formatkonfiguration](#FormatImport) kan du importera det format som krävs från den angivna XML-filen.</span><span class="sxs-lookup"><span data-stu-id="e9013-652">By completing the steps in the [Import a designed format configuration](#FormatImport) section, you can import the required format from the provided XML file.</span></span> <span data-ttu-id="e9013-653">Du kan också slutföra stegen i avsnittet [Skapa en ny formatkonfiguration](#FormatCreate) om du vill designa det här formatet från början.</span><span class="sxs-lookup"><span data-stu-id="e9013-653">Alternatively, you can complete the steps in the [Create a new format configuration](#FormatCreate) section to design this format from scratch.</span></span>

### <a name="import-a-designed-format-configuration"></a><a name="FormatImport"></a><span data-ttu-id="e9013-654">Importera en utformad formatkonfiguration</span><span class="sxs-lookup"><span data-stu-id="e9013-654">Import a designed format configuration</span></span>

1. <span data-ttu-id="e9013-655">Hämta filen [enkätformat.version.1.xml](https://go.microsoft.com/fwlink/?linkid=851448) och spara den på den lokala datorn.</span><span class="sxs-lookup"><span data-stu-id="e9013-655">Download the [Questionnaires format.version.1.1.xml](https://go.microsoft.com/fwlink/?linkid=851448) file, and save it to your local computer.</span></span>
2. <span data-ttu-id="e9013-656">Gå till **Organisationsadministration** \> **Arbetsytor** \> **Elektronisk rapportering**.</span><span class="sxs-lookup"><span data-stu-id="e9013-656">Go to **Organization administration** \> **Workspaces** \> **Electronic reporting**.</span></span>
3. <span data-ttu-id="e9013-657">På arbetsytan **Elektronisk rapportering** väljer du **Rapporteringskonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="e9013-657">In the **Electronic reporting** workspace, select **Reporting configurations**.</span></span>
4. <span data-ttu-id="e9013-658">På Åtgärdsfönster väljer du **växla** \> **läs in från XML-fil**.</span><span class="sxs-lookup"><span data-stu-id="e9013-658">On the Action pane, Select **Exchange** \> **Load from XML file**.</span></span>
5. <span data-ttu-id="e9013-659">Välj **Bläddra** och leta sedan reda på och markera filen **enkätformat.version.1.1.xml**.</span><span class="sxs-lookup"><span data-stu-id="e9013-659">Select **Browse**, and then find and select the **Questionnaires format.version.1.1.xml** file.</span></span>
6. <span data-ttu-id="e9013-660">Välj **OK** för att importera konfigurationen.</span><span class="sxs-lookup"><span data-stu-id="e9013-660">Select **OK** to import the configuration.</span></span>

<span data-ttu-id="e9013-661">Om du vill fortsätta hoppar du över nästa procedur, [skapa en ny formatkonfiguration](#FormatCreate).</span><span class="sxs-lookup"><span data-stu-id="e9013-661">To continue, skip the next procedure, [Create a new format configuration](#FormatCreate).</span></span>

### <a name="create-a-new-format-configuration"></a><a name="FormatCreate"></a><span data-ttu-id="e9013-662">Skapa en ny formatkonfiguration</span><span class="sxs-lookup"><span data-stu-id="e9013-662">Create a new format configuration</span></span>
 
1. <span data-ttu-id="e9013-663">Gå till **Organisationsadministration** \> **Elektronisk rapportering** \> **Konfigurationer**.</span><span class="sxs-lookup"><span data-stu-id="e9013-663">Go to **Organization administration** \> **Electronic reporting** \> **Configurations**.</span></span>
2. <span data-ttu-id="e9013-664">På sidan **konfigurationer** i konfigurationsträdet väljer du **enkätmodell**.</span><span class="sxs-lookup"><span data-stu-id="e9013-664">On the **Configurations** page, in the configuration tree, select **Questionnaire model**.</span></span>
3. <span data-ttu-id="e9013-665">Välj **Skapa konfiguration**.</span><span class="sxs-lookup"><span data-stu-id="e9013-665">Select **Create configuration**.</span></span>
4. <span data-ttu-id="e9013-666">Gör följande i listrutan:</span><span class="sxs-lookup"><span data-stu-id="e9013-666">In the drop-down dialog box, follow these steps:</span></span>

    1. <span data-ttu-id="e9013-667">I fältet **Nytt** väljer du **Format baserat på datamodellenkäter**.</span><span class="sxs-lookup"><span data-stu-id="e9013-667">In the **New** field, select **Format based on data model Questionnaires**.</span></span>
    2. <span data-ttu-id="e9013-668">Ange **enkätrapport** i fältet **Namn**.</span><span class="sxs-lookup"><span data-stu-id="e9013-668">In the **Name** field, enter **Questionnaire report**.</span></span>
    3. <span data-ttu-id="e9013-669">I fältet **Datamodellversion** välj **1**.</span><span class="sxs-lookup"><span data-stu-id="e9013-669">In the **Data model version** field, select **1**.</span></span>

        > [!NOTE]
        > - <span data-ttu-id="e9013-670">Om du väljer en specifik version av basdatamodellen, kommer strukturen för motsvarande version av datamodellen att presenteras för dig som strukturen för datakällan **Modell** i det format som skapas.</span><span class="sxs-lookup"><span data-stu-id="e9013-670">If you select a specific version of the base data model, the structure of the corresponding version of the data model will be presented to you as the structure of the **Model** data source in the format that is created.</span></span>
        > - <span data-ttu-id="e9013-671">Fältet kan vara tomt.</span><span class="sxs-lookup"><span data-stu-id="e9013-671">You can leave this field blank.</span></span> <span data-ttu-id="e9013-672">I så fall visas strukturen på **utkast**-versionen av datamodellen som en struktur för datakällan **modell** i det format som skapas.</span><span class="sxs-lookup"><span data-stu-id="e9013-672">In that case, the structure of the **Draft** version of the data model will be presented to you as the structure of the **Model** data source in the format that is created.</span></span> <span data-ttu-id="e9013-673">Du kan sedan justera modellen och omedelbart se justeringarna i formatet.</span><span class="sxs-lookup"><span data-stu-id="e9013-673">You can then adjust your model and immediately see those adjustments in your format.</span></span> <span data-ttu-id="e9013-674">Den här metoden kan förbättra effektiviteten hos ER-lösningen när du konfigurerar datamodellen, modellmappningen och formaterar samtidigt.</span><span class="sxs-lookup"><span data-stu-id="e9013-674">This approach might improve the efficiency of ER solution design when you configure your data model, model mapping, and format simultaneously.</span></span>
        > - <span data-ttu-id="e9013-675">Om du väljer en specifik version av basdatamodellen kan du senare växla till att använda **utkast**-versionen när du börjar redigera ett format.</span><span class="sxs-lookup"><span data-stu-id="e9013-675">If you select a specific version of the base data model, you can switch to using the **Draft** version later, when you start to edit a format.</span></span>

    4. <span data-ttu-id="e9013-676">I fältet **Definition av datamodell** välj definitionen **Rot**.</span><span class="sxs-lookup"><span data-stu-id="e9013-676">In the **Data model definition** field, select the **Root** definition.</span></span>

5. <span data-ttu-id="e9013-677">Välj **Skapa konfiguration** för att skapa konfigurationen.</span><span class="sxs-lookup"><span data-stu-id="e9013-677">Select **Create configuration** to create the configuration.</span></span>

#### <a name="import-a-report-template"></a><a name="ImportReportTemplate"></a><span data-ttu-id="e9013-678">Importera rapportmall</span><span class="sxs-lookup"><span data-stu-id="e9013-678">Import a report template</span></span>

1. <span data-ttu-id="e9013-679">På sidan **konfigurationer** i konfigurationsträdet väljer du **enkätrapport**.</span><span class="sxs-lookup"><span data-stu-id="e9013-679">On the **Configurations** page, in the configuration tree, select **Questionnaire report**.</span></span>
2. <span data-ttu-id="e9013-680">Välj **Designer** om du vill starta konfigureringen av ett anpassat format.</span><span class="sxs-lookup"><span data-stu-id="e9013-680">Select **Designer** to start to configure a custom format.</span></span>
3. <span data-ttu-id="e9013-681">På snabbfliken **Formatdesigner** på åtgärdsfönstret väljer du **Importera** \> **Importera från Excel**.</span><span class="sxs-lookup"><span data-stu-id="e9013-681">On the **Format designer** page, on the Action Pane, select **Import** \> **Import from Excel**.</span></span>
4. <span data-ttu-id="e9013-682">Gör följande i dialogrutan:</span><span class="sxs-lookup"><span data-stu-id="e9013-682">In the dialog box, follow these steps:</span></span>

    1. <span data-ttu-id="e9013-683">Välj **Lägg till mall**.</span><span class="sxs-lookup"><span data-stu-id="e9013-683">Select **Add template**.</span></span>
    2. <span data-ttu-id="e9013-684">Sök och markera den lokalt sparade filen **enkätrapportmall.xslx** och välj sedan **Öppna**.</span><span class="sxs-lookup"><span data-stu-id="e9013-684">Find and select the locally saved **Questionnaires report template.xslx** file, and then select **Open**.</span></span>
    3. <span data-ttu-id="e9013-685">Välj **OK** för att importera mallen.</span><span class="sxs-lookup"><span data-stu-id="e9013-685">Select **OK** to import the template.</span></span>

    ![Importera en rapportmall](./media/er-quick-start1-template-import.png)

<span data-ttu-id="e9013-687">Formatelementet **Excel\\File** läggs automatiskt till i det redigerbara formatet som ett rotelement.</span><span class="sxs-lookup"><span data-stu-id="e9013-687">The **Excel\\File** format element is automatically added to the editable format as a root element.</span></span> <span data-ttu-id="e9013-688">Dessutom läggs formatelementet **Excel\\Range** eller formatelementet **Excel\\Cell** automatiskt till för varje identifierat Excel-namn i den importerade mallen.</span><span class="sxs-lookup"><span data-stu-id="e9013-688">Additionally, either the **Excel\\Range** format element or the **Excel\\Cell** format element is automatically added for every recognized Excel name of the imported template.</span></span> <span data-ttu-id="e9013-689">Formatet **Excel\\Header** som har kapslade **Sträng**-element läggs automatiskt till för att avspegla rubrikinställningarna för den importerade mallen.</span><span class="sxs-lookup"><span data-stu-id="e9013-689">The **Excel\\Header** format that has the nested **String** element is automatically added to reflect the header settings of the imported template.</span></span>

![Formatstruktur som innehåller automatiskt tillagda element i ER-åtgärdsdesigner.](./media/er-quick-start1-template-import2.png)

#### <a name="configure-a-format"></a><a name="ConfigureFormat"></a><span data-ttu-id="e9013-691">Konfigurera ett format</span><span class="sxs-lookup"><span data-stu-id="e9013-691">Configure a format</span></span>

1. <span data-ttu-id="e9013-692">På sidan **Formatdesigner** i formatträdet, välj rotelementet **Excel**.</span><span class="sxs-lookup"><span data-stu-id="e9013-692">On the **Format designer** page, in the format tree, select the **Excel** root element.</span></span>
2. <span data-ttu-id="e9013-693">Gå till fliken **Format** på sidans högra sida, ange en rapport i fältet **Namn** anger <a name="AddFormatRootElement"></a>**rapport**.</span><span class="sxs-lookup"><span data-stu-id="e9013-693">On the **Format** tab on the right side of the page, in the **Name** field, enter <a name="AddFormatRootElement"></a>**Report**.</span></span>
3. <span data-ttu-id="e9013-694">I fältet **Språkinställningar** välj **Användarinställningar** om du vill köra rapporten på användarens önskade språk.</span><span class="sxs-lookup"><span data-stu-id="e9013-694">In the **Language preference** field, select **User preference** to run the report in the user's preferred language.</span></span>
4. <span data-ttu-id="e9013-695">I fältet **Kulturinställningar** välj **Användarinställningar** om du vill köra rapporten i användarens önskade kultur.</span><span class="sxs-lookup"><span data-stu-id="e9013-695">In the **Culture preference** field, select **User preference** to run the report in the user's preferred culture.</span></span>

    <span data-ttu-id="e9013-696">Information om hur du anger språk och kulturkontexter för en ER-process finns i [utforma flerspråkiga rapporter](er-design-multilingual-reports.md).</span><span class="sxs-lookup"><span data-stu-id="e9013-696">For information about how to specify the language and culture contexts for an ER process, see [Design multilingual reports](er-design-multilingual-reports.md).</span></span>

    ![Konfigurera språk- och kulturinställningar för den designade rapporten i ER-åtgärdsdesigner](./media/er-quick-start1-template-format-structure1.png)

5. <span data-ttu-id="e9013-698">Expandera rotnoden i formatträdet och välj sedan **ResultsGroup**.</span><span class="sxs-lookup"><span data-stu-id="e9013-698">In the format tree, expand the root node, and then select **ResultsGroup**.</span></span>
6. <span data-ttu-id="e9013-699">På fliken **Format** i fältet **Replikeringsriktning** välj **Ingen replikering**, eftersom du inte förväntar dig att ha flera resultatgrupper för en enda enkät.</span><span class="sxs-lookup"><span data-stu-id="e9013-699">On the **Format** tab, in the **Replication direction** field, select **No replication**, because you don't expect to have multiple result groups for a single questionnaire.</span></span>

    ![Definiera riktning för replikering för områdesformatelement i ER-åtgärdsdesigner](./media/er-quick-start1-template-format-structure2.png)

7. <span data-ttu-id="e9013-701">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="e9013-701">Select **Save**.</span></span>

#### <a name="define-the-data-binding-for-a-report-title"></a><a name="DefineFormatBindings"></a><span data-ttu-id="e9013-702">Definiera databindningen för en rapportrubrik</span><span class="sxs-lookup"><span data-stu-id="e9013-702">Define the data binding for a report title</span></span>

<span data-ttu-id="e9013-703">Du måste ange en databindning för ett formatelement som används för att fylla i rubriken för en genererad rapport.</span><span class="sxs-lookup"><span data-stu-id="e9013-703">You must specify a data binding for a format element that is used to fill in the title of a generated report.</span></span>

1. <span data-ttu-id="e9013-704">På sidan **Formatdesigner** på fliken **Mappning** till höger väljer du elementet **Report\\ReportTitle**.</span><span class="sxs-lookup"><span data-stu-id="e9013-704">On the **Format designer** page, on the **Mapping** tab on the right, select the **Report\\ReportTitle** element.</span></span>
2. <span data-ttu-id="e9013-705">Välj **Redigera recept**.</span><span class="sxs-lookup"><span data-stu-id="e9013-705">Select **Edit formula**.</span></span>
3. <span data-ttu-id="e9013-706">Välj **översätt** i formelredigeraren.</span><span class="sxs-lookup"><span data-stu-id="e9013-706">In the formula editor, select **Translate**.</span></span>
4. <span data-ttu-id="e9013-707">I dialogrutan **Textöversättning** gör följande:</span><span class="sxs-lookup"><span data-stu-id="e9013-707">In the **Text translation** dialog box, follow these steps:</span></span>

    1. <span data-ttu-id="e9013-708">I fältet **Etikett-ID** anger du **ReportTitle**.</span><span class="sxs-lookup"><span data-stu-id="e9013-708">In the **Label ID** field, enter **ReportTitle**.</span></span>
    2. <span data-ttu-id="e9013-709">I fältet **text på standardspråk** anger du **enkätrapport**.</span><span class="sxs-lookup"><span data-stu-id="e9013-709">In the **Text in default language** field, enter **Questionnaires report**.</span></span>
    3. <span data-ttu-id="e9013-710">Välj **Översätt** och välj sedan **Spara**.</span><span class="sxs-lookup"><span data-stu-id="e9013-710">Select **Translate**, and then select **Save**.</span></span>
    4. <span data-ttu-id="e9013-711">Välj **Översätt** om du vill stänga dialogrutan **textöversättning**.</span><span class="sxs-lookup"><span data-stu-id="e9013-711">Select **Translate** to close the **Text translation** dialog box.</span></span>

5. <span data-ttu-id="e9013-712">Stäng formelredigeraren.</span><span class="sxs-lookup"><span data-stu-id="e9013-712">Close the formula editor.</span></span>

    ![Konfigurera bindningen så att den fyller i rubriken på en genererad rapport](./media/er-quick-start1-add-report-title-label.png)

<span data-ttu-id="e9013-714">Du kan använda den här tekniken för att göra alla andra etiketter för den aktuella mallspråkberoende.</span><span class="sxs-lookup"><span data-stu-id="e9013-714">You can use this technique to make all other labels of the current template language-dependent.</span></span> <span data-ttu-id="e9013-715">Information om hur tillagda etiketter för en enskild ER-konfiguration kan översättas till alla språk som stöds finns i [utforma flerspråkiga rapporter](er-design-multilingual-reports.md).</span><span class="sxs-lookup"><span data-stu-id="e9013-715">For information about how the added labels of a single ER configuration can be translated into all supported languages, see [Design multilingual reports](er-design-multilingual-reports.md).</span></span>

#### <a name="review-model-data-source"></a><a name="ReviewModelDataSource"></a><span data-ttu-id="e9013-716">Granska modellens datakälla</span><span class="sxs-lookup"><span data-stu-id="e9013-716">Review model data source</span></span>

1. <span data-ttu-id="e9013-717">På sidan **Formatdesigner** på fliken **Mappning** välj datakällan <a name="ModelDSName"></a>**modell** som representerar basdatamodellen för det här ER-formatet.</span><span class="sxs-lookup"><span data-stu-id="e9013-717">On the **Format designer** page, on the **Mapping** tab, select the <a name="ModelDSName"></a>**model** data source that represents the base data model of this ER format.</span></span>
2. <span data-ttu-id="e9013-718">Välj **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="e9013-718">Select **Edit**.</span></span>
3. <span data-ttu-id="e9013-719">Granska informationen i dialogrutan **Egenskaper för datakälla**.</span><span class="sxs-lookup"><span data-stu-id="e9013-719">Review the information in the **Data source properties** dialog box.</span></span> <span data-ttu-id="e9013-720">Den här datakällan representerar version 1 av den datamodellkomponent för **enkäter** som finns i ER-konfigurationen för **enkätmodell**.</span><span class="sxs-lookup"><span data-stu-id="e9013-720">This data source represents version 1 of the **Questionnaires** data model component that resides in the **Questionnaires model** ER configuration.</span></span>

![Egenskaper för modelldatakällan i ER-åtgärdsdesigner](./media/er-quick-start1-model-data-source.png)

#### <a name="bind-format-elements-to-data-source-fields"></a><a name="BindFormatElements"></a><span data-ttu-id="e9013-722">Binda formatelement till fält för datakällor</span><span class="sxs-lookup"><span data-stu-id="e9013-722">Bind format elements to data source fields</span></span>

<span data-ttu-id="e9013-723">Om du vill ange hur en mall ska fyllas i vid körning måste du binda varje formatelement som är associerat med ett lämpligt Excel-namn till ett enda fält i det här formatets datakälla.</span><span class="sxs-lookup"><span data-stu-id="e9013-723">To specify how a template is filled in at runtime, you must bind every format element that is associated with an appropriate Excel name to a single field of this format's data source.</span></span>

1. <span data-ttu-id="e9013-724">På sidan **Formatdesigner** i formatträdet, välj formatelementet **Report\\CompanyName**.</span><span class="sxs-lookup"><span data-stu-id="e9013-724">On the **Format designer** page, in the format tree, select the **Report\\CompanyName** format element.</span></span>
2. <span data-ttu-id="e9013-725">På fliken **mappning** välj datakällfältet **model.CompanyName** på typen **sträng**.</span><span class="sxs-lookup"><span data-stu-id="e9013-725">On the **Mapping** tab, select the **model.CompanyName** data source field of the **String** type.</span></span>
3. <span data-ttu-id="e9013-726">Välj **Bind** om du vill ange ett företagsnamn i en mall.</span><span class="sxs-lookup"><span data-stu-id="e9013-726">Select **Bind** to enter a company name in a template.</span></span>
4. <span data-ttu-id="e9013-727">I formatträdet, välj elementet **Report\\Questionnaire**.</span><span class="sxs-lookup"><span data-stu-id="e9013-727">In the format tree, select the **Report\\Questionnaire** element.</span></span>
5. <span data-ttu-id="e9013-728">På fliken **mappning** välj datakällfältet **model.Questionnaire** på typen **postlista**.</span><span class="sxs-lookup"><span data-stu-id="e9013-728">On the **Mapping** tab, select the **model.Questionnaire** data source field of the **Record list** type.</span></span>
6. <span data-ttu-id="e9013-729">Välj **bind**.</span><span class="sxs-lookup"><span data-stu-id="e9013-729">Select **Bind**.</span></span>
7. <span data-ttu-id="e9013-730">Välj **Visa detaljer** om du vill visa mer information för formatelement.</span><span class="sxs-lookup"><span data-stu-id="e9013-730">Select **Show details** to see more details for format elements.</span></span>

    <span data-ttu-id="e9013-731">Områdesformatelement **enkät** intervall konfigureras som vertikalt replikerat.</span><span class="sxs-lookup"><span data-stu-id="e9013-731">The **Questionnaire** range format element is configured as vertically replicated.</span></span> <span data-ttu-id="e9013-732">När den är bunden till en datakälla för typen **postlista** upprepas det korrekta intervallet **enkät** för Excel-mallen för varje post i den bundna datakällan.</span><span class="sxs-lookup"><span data-stu-id="e9013-732">When it's bound to a data source of the **Record list** type, the appropriate **Questionnaire** range of the Excel template is repeated for every record of the bound data source.</span></span>
 
    ![Bindande områdesformatelement för enkät till lämpliga datakällor för postlista i ER-åtgärdsdesigner](./media/er-quick-start1-bindings1.png)

    <span data-ttu-id="e9013-734">Eftersom området **enkät** för Excel-mallen definieras mellan raderna 5 till 14, upprepas dessa rader för varje rapporterad enkät.</span><span class="sxs-lookup"><span data-stu-id="e9013-734">Because the **Questionnaire** range of the Excel template is defined between rows 5 through 14, these rows are repeated for every reported questionnaire.</span></span>

    ![De rader i Excel-mallen som ska upprepas i en genererad rapport för varje post i postlistans datakällor.](./media/er-quick-start1-template-questionnaire-range.png)

8. <span data-ttu-id="e9013-736">Konfigurera liknande bindningar för de återstående formatelementen enligt beskrivningen i följande tabell.</span><span class="sxs-lookup"><span data-stu-id="e9013-736">Configure similar bindings for the remaining format elements, as described in the following table.</span></span>

    > [!NOTE]
    > <span data-ttu-id="e9013-737">I den här tabellen förutsätter informationen i kolumnen "sökväg till datakälla" att den [relativa sökvägen](relative-path-data-bindings-er-models-format.md) ER-funktion är aktiverad.</span><span class="sxs-lookup"><span data-stu-id="e9013-737">In this table, the information in the "Data source path" column assumes that the [relative path](relative-path-data-bindings-er-models-format.md) ER feature is turned on.</span></span>

    | <span data-ttu-id="e9013-738">Formatera element för sökväg</span><span class="sxs-lookup"><span data-stu-id="e9013-738">Format element path</span></span>                                      | <span data-ttu-id="e9013-739">Sökväg för datakälla</span><span class="sxs-lookup"><span data-stu-id="e9013-739">Data source path</span></span> |
    |----------------------------------------------------------|------------------|
    | <span data-ttu-id="e9013-740">Excel\\ReportTitle</span><span class="sxs-lookup"><span data-stu-id="e9013-740">Excel\\ReportTitle</span></span>                                       | <span data-ttu-id="e9013-741">**\@"GER\_LABEL:ReportTitle"**</span><span class="sxs-lookup"><span data-stu-id="e9013-741">**\@"GER\_LABEL:ReportTitle"**</span></span> |
    | <span data-ttu-id="e9013-742">Excel\\CompanyName</span><span class="sxs-lookup"><span data-stu-id="e9013-742">Excel\\CompanyName</span></span>                                       | <span data-ttu-id="e9013-743">**model.CompanyName**</span><span class="sxs-lookup"><span data-stu-id="e9013-743">**model.CompanyName**</span></span> |
    | <span data-ttu-id="e9013-744">Excel\\Questionnaire</span><span class="sxs-lookup"><span data-stu-id="e9013-744">Excel\\Questionnaire</span></span>                                     | <span data-ttu-id="e9013-745">**model.Questionnaire**</span><span class="sxs-lookup"><span data-stu-id="e9013-745">**model.Questionnaire**</span></span> |
    | <span data-ttu-id="e9013-746">Excel\\Questionnaire\\Active</span><span class="sxs-lookup"><span data-stu-id="e9013-746">Excel\\Questionnaire\\Active</span></span>                             | <span data-ttu-id="e9013-747">**\@.Active**, where **\@** is **model.Questionnaire**</span><span class="sxs-lookup"><span data-stu-id="e9013-747">**\@.Active**, where **\@** is **model.Questionnaire**</span></span> |
    | <span data-ttu-id="e9013-748">Excel\\Questionnaire\\Code</span><span class="sxs-lookup"><span data-stu-id="e9013-748">Excel\\Questionnaire\\Code</span></span>                               | <span data-ttu-id="e9013-749">**\@.Code**</span><span class="sxs-lookup"><span data-stu-id="e9013-749">**\@.Code**</span></span> |
    | <span data-ttu-id="e9013-750">Excel\\Questionnaire\\Description</span><span class="sxs-lookup"><span data-stu-id="e9013-750">Excel\\Questionnaire\\Description</span></span>                        | <span data-ttu-id="e9013-751">**\@.Description**</span><span class="sxs-lookup"><span data-stu-id="e9013-751">**\@.Description**</span></span> |
    | <span data-ttu-id="e9013-752">Excel\\Questionnaire\\QuestionnaireType</span><span class="sxs-lookup"><span data-stu-id="e9013-752">Excel\\Questionnaire\\QuestionnaireType</span></span>                  | <span data-ttu-id="e9013-753">**\@.QuestionnaireType**</span><span class="sxs-lookup"><span data-stu-id="e9013-753">**\@.QuestionnaireType**</span></span> |
    | <span data-ttu-id="e9013-754">Excel\\Questionnaire\\QuestionOrder</span><span class="sxs-lookup"><span data-stu-id="e9013-754">Excel\\Questionnaire\\QuestionOrder</span></span>                      | <span data-ttu-id="e9013-755">**\@.QuestionOrder**</span><span class="sxs-lookup"><span data-stu-id="e9013-755">**\@.QuestionOrder**</span></span> |
    | <span data-ttu-id="e9013-756">Excel\\Questionnaire\\ResultsGroup\\Code\_</span><span class="sxs-lookup"><span data-stu-id="e9013-756">Excel\\Questionnaire\\ResultsGroup\\Code\_</span></span>               | <span data-ttu-id="e9013-757">**\@.ResultsGroup.Code**</span><span class="sxs-lookup"><span data-stu-id="e9013-757">**\@.ResultsGroup.Code**</span></span> |
    | <span data-ttu-id="e9013-758">Excel\\Questionnaire\\ResultsGroup\\Description\_</span><span class="sxs-lookup"><span data-stu-id="e9013-758">Excel\\Questionnaire\\ResultsGroup\\Description\_</span></span>        | <span data-ttu-id="e9013-759">**\@.ResultsGroup.Description**</span><span class="sxs-lookup"><span data-stu-id="e9013-759">**\@.ResultsGroup.Description**</span></span> |
    | <span data-ttu-id="e9013-760">Excel\\Questionnaire\\ResultsGroup\\MaxNumberOfPoints</span><span class="sxs-lookup"><span data-stu-id="e9013-760">Excel\\Questionnaire\\ResultsGroup\\MaxNumberOfPoints</span></span>    | <span data-ttu-id="e9013-761">**\@.ResultsGroup.MaxNumberOfPoint**</span><span class="sxs-lookup"><span data-stu-id="e9013-761">**\@.ResultsGroup.MaxNumberOfPoint**</span></span> |
    | <span data-ttu-id="e9013-762">Excel\\Questionnaire\\Question</span><span class="sxs-lookup"><span data-stu-id="e9013-762">Excel\\Questionnaire\\Question</span></span>                           | <span data-ttu-id="e9013-763">**\@.Question**</span><span class="sxs-lookup"><span data-stu-id="e9013-763">**\@.Question**</span></span> |
    | <span data-ttu-id="e9013-764">Excel\\Questionnaire\\Question\\CollectionSequenceNumber</span><span class="sxs-lookup"><span data-stu-id="e9013-764">Excel\\Questionnaire\\Question\\CollectionSequenceNumber</span></span> | <span data-ttu-id="e9013-765">**\@.CollectionSequenceNumber**, where **\@** is **model.Questionnaire.Question**</span><span class="sxs-lookup"><span data-stu-id="e9013-765">**\@.CollectionSequenceNumber**, where **\@** is **model.Questionnaire.Question**</span></span> |
    | <span data-ttu-id="e9013-766">Excel\\Questionnaire\\Question\\Id</span><span class="sxs-lookup"><span data-stu-id="e9013-766">Excel\\Questionnaire\\Question\\Id</span></span>                       | <span data-ttu-id="e9013-767">**\@.Id**</span><span class="sxs-lookup"><span data-stu-id="e9013-767">**\@.Id**</span></span> |
    | <span data-ttu-id="e9013-768">Excel\\Questionnaire\\Question\\MustBeCompleted</span><span class="sxs-lookup"><span data-stu-id="e9013-768">Excel\\Questionnaire\\Question\\MustBeCompleted</span></span>          | <span data-ttu-id="e9013-769">**\@.MustBeCompleted**</span><span class="sxs-lookup"><span data-stu-id="e9013-769">**\@.MustBeCompleted**</span></span> |
    | <span data-ttu-id="e9013-770">Excel\\Questionnaire\\Question\\PrimaryQuestion</span><span class="sxs-lookup"><span data-stu-id="e9013-770">Excel\\Questionnaire\\Question\\PrimaryQuestion</span></span>          | <span data-ttu-id="e9013-771">**\@.PrimaryQuestion**</span><span class="sxs-lookup"><span data-stu-id="e9013-771">**\@.PrimaryQuestion**</span></span> |
    | <span data-ttu-id="e9013-772">Excel\\Questionnaire\\Question\\SequenceNumber</span><span class="sxs-lookup"><span data-stu-id="e9013-772">Excel\\Questionnaire\\Question\\SequenceNumber</span></span>           | <span data-ttu-id="e9013-773">**\@.SequenceNumber**</span><span class="sxs-lookup"><span data-stu-id="e9013-773">**\@.SequenceNumber**</span></span> |
    | <span data-ttu-id="e9013-774">Excel\\Questionnaire\\Question\\Text</span><span class="sxs-lookup"><span data-stu-id="e9013-774">Excel\\Questionnaire\\Question\\Text</span></span>                     | <span data-ttu-id="e9013-775">**\@.Text**</span><span class="sxs-lookup"><span data-stu-id="e9013-775">**\@.Text**</span></span> |
    | <span data-ttu-id="e9013-776">Excel\\Questionnaire\\Question\\Answer</span><span class="sxs-lookup"><span data-stu-id="e9013-776">Excel\\Questionnaire\\Question\\Answer</span></span>                   | <span data-ttu-id="e9013-777">**\@.Answer**</span><span class="sxs-lookup"><span data-stu-id="e9013-777">**\@.Answer**</span></span> |
    | <span data-ttu-id="e9013-778">Excel\\Questionnaire\\Question\\Answer\\CorrectAnswer</span><span class="sxs-lookup"><span data-stu-id="e9013-778">Excel\\Questionnaire\\Question\\Answer\\CorrectAnswer</span></span>    | <span data-ttu-id="e9013-779">**\@.CorrectAnswer**, where **\@** is **model.Questionnaire.Answer**</span><span class="sxs-lookup"><span data-stu-id="e9013-779">**\@.CorrectAnswer**, where **\@** is **model.Questionnaire.Answer**</span></span> |
    | <span data-ttu-id="e9013-780">Excel\\Questionnaire\\Question\\Answer\\Points</span><span class="sxs-lookup"><span data-stu-id="e9013-780">Excel\\Questionnaire\\Question\\Answer\\Points</span></span>           | <span data-ttu-id="e9013-781">**\@.Points**</span><span class="sxs-lookup"><span data-stu-id="e9013-781">**\@.Points**</span></span> |
    | <span data-ttu-id="e9013-782">Excel\\Questionnaire\\Question\\Answer\\Text</span><span class="sxs-lookup"><span data-stu-id="e9013-782">Excel\\Questionnaire\\Question\\Answer\\Text</span></span>             | <span data-ttu-id="e9013-783">**\@.Text**</span><span class="sxs-lookup"><span data-stu-id="e9013-783">**\@.Text**</span></span> |

9. <span data-ttu-id="e9013-784">Välj **Spara** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="e9013-784">When you've finished, select **Save**.</span></span>

<span data-ttu-id="e9013-785">Bilden nedan visar det slutliga tillståndet för den konfigurerade databindningar på sidan **Formatdesigner**.</span><span class="sxs-lookup"><span data-stu-id="e9013-785">The following illustration shows the final state of the configured data bindings on the **Format designer** page.</span></span>

![Konfigurerad databindningar i ER-åtgärdsdesigner](./media/er-quick-start1-bindings2.png)

> [!IMPORTANT]
> <span data-ttu-id="e9013-787">Hela mängden med angivna datakällor och bindningar representerar en formatmappningskomponent i det konfigurerade formatet.</span><span class="sxs-lookup"><span data-stu-id="e9013-787">The whole collection of specified data sources and bindings represents a format mapping component of the configured format.</span></span> <span data-ttu-id="e9013-788">Den här formatmappningen anropas när du kör det konfigurerade formatet för rapportgenerering.</span><span class="sxs-lookup"><span data-stu-id="e9013-788">This format mapping is called when you run the configured format for report generation.</span></span>

### <a name="run-a-designed-format-from-er"></a><a name="RunFormatFromER"></a><span data-ttu-id="e9013-789">Kör ett format som skapats från ER</span><span class="sxs-lookup"><span data-stu-id="e9013-789">Run a designed format from ER</span></span>

<span data-ttu-id="e9013-790">Du kan nu köra ett utformat format för testning från sidan **konfigurationer**.</span><span class="sxs-lookup"><span data-stu-id="e9013-790">You can now run a designed format for testing purposes from the **Configurations** page.</span></span>

1. <span data-ttu-id="e9013-791">Gå till **Organisationsadministration** \> **Elektronisk rapportering** \> **Konfigurationer**.</span><span class="sxs-lookup"><span data-stu-id="e9013-791">Go to **Organization administration** \> **Electronic reporting** \> **Configurations**.</span></span>
2. <span data-ttu-id="e9013-792">På sidan **konfiguration** i konfigurationsträdet i vänster fönster expanderar du **enkätmodell** och väljer sedan **enkätrapport**.</span><span class="sxs-lookup"><span data-stu-id="e9013-792">On the **Configuration** page, in the configuration tree, expand **Questionnaire model**, and then select **Questionnaire report**.</span></span>
3. <span data-ttu-id="e9013-793">Välj **Designer** för formatversionen som har statusen **utkast**.</span><span class="sxs-lookup"><span data-stu-id="e9013-793">Select **Designer** for the format version that has a status of **Draft**.</span></span>
4. <span data-ttu-id="e9013-794">Välj **Formatdesigner** på sidan **Kör**.</span><span class="sxs-lookup"><span data-stu-id="e9013-794">On the **Format designer** page, select **Run**.</span></span>
5. <span data-ttu-id="e9013-795">I dialogrutan **ER-parametrar** på snabbfliken **Poster som ska ingå** konfigurerar du filtreringsalternativet så att bara enkäten **SBCCrsExam** ingår.</span><span class="sxs-lookup"><span data-stu-id="e9013-795">In the **ER parameters** dialog box, on the **Records to include** FastTab, configure the filtering option so that only the **SBCCrsExam** questionnaire is included.</span></span>
6. <span data-ttu-id="e9013-796">Bekräfta filtreringsåtgärden genom att välja **OK**.</span><span class="sxs-lookup"><span data-stu-id="e9013-796">Select **OK** to confirm the filtering option.</span></span>
7. <span data-ttu-id="e9013-797">Klicka på **OK** om du vill köra rapporten.</span><span class="sxs-lookup"><span data-stu-id="e9013-797">Select **OK** to run the report.</span></span>
8. <span data-ttu-id="e9013-798">Granska den genererade rapporten.</span><span class="sxs-lookup"><span data-stu-id="e9013-798">Review the generated report.</span></span>

<span data-ttu-id="e9013-799">Som [standard](electronic-reporting-destinations.md#default-behavior) levereras en genererad rapport som en Excel-fil som du kan hämta.</span><span class="sxs-lookup"><span data-stu-id="e9013-799">By [default](electronic-reporting-destinations.md#default-behavior), a generated report is delivered as an Excel file that you can download.</span></span> <span data-ttu-id="e9013-800">I följande illustrationer visas två sidor i den genererade rapporten i Excel-format.</span><span class="sxs-lookup"><span data-stu-id="e9013-800">The following illustrations show two pages of the generated report in Excel format.</span></span>

![Exempel på en genererad rapport i Excel-format, sidan 1](./media/er-quick-start1-report1a.png)

![Exempel på en genererad rapport i Excel-format, sidan 2](./media/er-quick-start1-report1b.png)

## <a name="tune-a-designed-format"></a><a name="TuneFormat"></a><span data-ttu-id="e9013-803">Justera ett utformat format</span><span class="sxs-lookup"><span data-stu-id="e9013-803">Tune a designed format</span></span>

### <a name="modify-a-format-to-change-the-name-of-a-generated-document"></a><a name="ModifyToChangeName"></a><span data-ttu-id="e9013-804">Ändra ett format för att ändra namnet på ett skapat dokument</span><span class="sxs-lookup"><span data-stu-id="e9013-804">Modify a format to change the name of a generated document</span></span>

<span data-ttu-id="e9013-805">Som standard namnges ett genererat dokument med hjälp av den aktuella användarens alias.</span><span class="sxs-lookup"><span data-stu-id="e9013-805">By default, a generated document is named by using the alias of the current user.</span></span> <span data-ttu-id="e9013-806">Genom att ändra formatet kan du ändra det här beteendet så att ett genererat dokument namnges baserat på din anpassade logik.</span><span class="sxs-lookup"><span data-stu-id="e9013-806">By modifying the format, you can change this behavior so that a generated document is named based on your custom logic.</span></span> <span data-ttu-id="e9013-807">Namnet på ett dokument kan till exempel baseras på dagens datum och aktuell tid och på rapportens titel.</span><span class="sxs-lookup"><span data-stu-id="e9013-807">For example, the name of a generated document can be based on the current session date and time, and on the report's title.</span></span>

1. <span data-ttu-id="e9013-808">På sidan **Formatdesigner** välj rotobjekt **Rapport**.</span><span class="sxs-lookup"><span data-stu-id="e9013-808">On the **Format designer** page, select the **Report** root item.</span></span>
2. <span data-ttu-id="e9013-809">På fliken **Mappning** välj **Redigera filnamn**.</span><span class="sxs-lookup"><span data-stu-id="e9013-809">On the **Mapping** tab, select **Edit file name**.</span></span>
3. <span data-ttu-id="e9013-810">I fältet **Formel** ange **CONCATENATE (\@"GER\_LABEL:ReportTitle", " - ", DATETIMEFORMAT(SESSIONNOW(), "yyyy-MM-dd hh-mm-ss"))**.</span><span class="sxs-lookup"><span data-stu-id="e9013-810">In the **Formula** field, enter **CONCATENATE (\@"GER\_LABEL:ReportTitle", " - ", DATETIMEFORMAT(SESSIONNOW(), "yyyy-MM-dd hh-mm-ss"))**.</span></span>
4. <span data-ttu-id="e9013-811">Markera **Spara** och stäng sedan formelredigeraren.</span><span class="sxs-lookup"><span data-stu-id="e9013-811">Select **Save**, and close the formula editor.</span></span>
5. <span data-ttu-id="e9013-812">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="e9013-812">Select **Save**.</span></span>

### <a name="modify-a-format-to-change-the-order-of-questions"></a><a name="ModifyToOrder"></a><span data-ttu-id="e9013-813">Ändra ett format för att ändra ordning på frågorna</span><span class="sxs-lookup"><span data-stu-id="e9013-813">Modify a format to change the order of questions</span></span>

<span data-ttu-id="e9013-814">Frågorna ordnas inte korrekt i en genererad rapport.</span><span class="sxs-lookup"><span data-stu-id="e9013-814">The questions aren't correctly ordered in a generated report.</span></span> <span data-ttu-id="e9013-815">Du kan ändra ordningen genom att ändra formatet.</span><span class="sxs-lookup"><span data-stu-id="e9013-815">You can change the order by modifying the format.</span></span>

1. <span data-ttu-id="e9013-816">På sidan **Formatdesigner** välj rotobjekt **Rapport**.</span><span class="sxs-lookup"><span data-stu-id="e9013-816">On the **Format designer** page, select the **Report** root item.</span></span>
2. <span data-ttu-id="e9013-817">På fliken **Mappning** i formatträdet, expandera **Report\\Questionnaire\\Question**.</span><span class="sxs-lookup"><span data-stu-id="e9013-817">On the **Mapping** tab, in the format tree, expand **Report\\Questionnaire\\Question**.</span></span>

    ![Element i frågetyp i intervalltypen för ER-åtgärdsdesigner](./media/er-quick-start1-bindings3.png)

3. <span data-ttu-id="e9013-819">På fliken **Mappning** välj **model.Questionnaire**.</span><span class="sxs-lookup"><span data-stu-id="e9013-819">On the **Mapping** tab, select **model.Questionnaire**.</span></span>
4. <span data-ttu-id="e9013-820">Välj **Lägg till** \> **funktioner\\beräknat fält** och skriv sedan i fältet **Name** **OrderedQuestions**.</span><span class="sxs-lookup"><span data-stu-id="e9013-820">Select **Add** \> **Functions\\Calculated field**, and then, in the **Name** field, enter **OrderedQuestions**.</span></span>
5. <span data-ttu-id="e9013-821">Välj **Redigera recept**.</span><span class="sxs-lookup"><span data-stu-id="e9013-821">Select **Edit formula**.</span></span>
6. <span data-ttu-id="e9013-822">I formelredigeraren i fältet **Formel** anger du **ORDERBY (model.Questionnaire.Question, model.Questionnaire.Question.SequenceNumber)** om du vill beställa en lista med frågor i den aktuella enkäten utifrån sekvensordernumret.</span><span class="sxs-lookup"><span data-stu-id="e9013-822">In the formula editor, in the **Formula** field, enter **ORDERBY (model.Questionnaire.Question, model.Questionnaire.Question.SequenceNumber)** to order the list of questions of the current questionnaire by the sequence order number.</span></span>
7. <span data-ttu-id="e9013-823">Markera **Spara** och stäng sedan formelredigeraren.</span><span class="sxs-lookup"><span data-stu-id="e9013-823">Select **Save**, and close the formula editor.</span></span>
8. <span data-ttu-id="e9013-824">Välj **OK** för att slutföra posten för ett nytt beräknat fält.</span><span class="sxs-lookup"><span data-stu-id="e9013-824">Select **OK** to complete the entry of a new calculated field.</span></span>
9. <span data-ttu-id="e9013-825">På fliken **Mappning** välj **model.Questionnaire.OrderedQuestions**.</span><span class="sxs-lookup"><span data-stu-id="e9013-825">On the **Mapping** tab, select **model.Questionnaire.OrderedQuestions**.</span></span>
10. <span data-ttu-id="e9013-826">I formatträdet, välj **Excel\\Questionnaire\\Question**.</span><span class="sxs-lookup"><span data-stu-id="e9013-826">In the format tree, select **Excel\\Questionnaire\\Question**.</span></span>
11. <span data-ttu-id="e9013-827">Välj **Bind** och bekräfta att den aktuella sökvägen **model.Questionnaire.Questions** ersätts av den nya sökvägen **model.Questionnaire.OrderedQuestions** i alla bindningar för kapslade element.</span><span class="sxs-lookup"><span data-stu-id="e9013-827">Select **Bind**, and then confirm that the current **model.Questionnaire.Questions** path is replaced by the new **model.Questionnaire.OrderedQuestions** path in all bindings of nested elements.</span></span>
12. <span data-ttu-id="e9013-828">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="e9013-828">Select **Save**.</span></span>

![Bind frågeformatelementet till den konfigurerade OrderedQuestions-datakällan i ER-åtgärdsdesigner](./media/er-quick-start1-bindings4.png)

### <a name="run-a-modified-format-from-er"></a><a name="RunFormatFromER2"></a><span data-ttu-id="e9013-830">Kör ett ändrat format från ER</span><span class="sxs-lookup"><span data-stu-id="e9013-830">Run a modified format from ER</span></span>

<span data-ttu-id="e9013-831">Du kan nu köra ett ändrat format för testning från ER-ramverket.</span><span class="sxs-lookup"><span data-stu-id="e9013-831">You can now run a modified format for testing purposes from the ER framework.</span></span>

1. <span data-ttu-id="e9013-832">Välj **Formatdesigner** på sidan **Kör**.</span><span class="sxs-lookup"><span data-stu-id="e9013-832">On the **Format designer** page, select **Run**.</span></span>
2. <span data-ttu-id="e9013-833">I dialogrutan **ER-parametrar** på snabbfliken **Poster som ska ingå** konfigurerar du filtreringsalternativet så att bara enkäten **SBCCrsExam** ingår.</span><span class="sxs-lookup"><span data-stu-id="e9013-833">In the **ER parameters** dialog box, on the **Records to include** FastTab, configure the filtering option so that only the **SBCCrsExam** questionnaire is included.</span></span>
3. <span data-ttu-id="e9013-834">Bekräfta filtreringsåtgärden genom att välja **OK**.</span><span class="sxs-lookup"><span data-stu-id="e9013-834">Select **OK** to confirm the filtering option.</span></span>
4. <span data-ttu-id="e9013-835">Klicka på **OK** om du vill köra rapporten.</span><span class="sxs-lookup"><span data-stu-id="e9013-835">Select **OK** to run the report.</span></span>
5. <span data-ttu-id="e9013-836">Granska den genererade rapporten.</span><span class="sxs-lookup"><span data-stu-id="e9013-836">Review the generated report.</span></span>

<span data-ttu-id="e9013-837">Följande bild visar en genererad rapport i Excel-format där frågorna har beställts på rätt sätt.</span><span class="sxs-lookup"><span data-stu-id="e9013-837">The following illustration shows a generated report in Excel format where the questions are correctly ordered.</span></span>

![Genererad rapport i Excel-format med korrekt ordnade frågor](./media/er-quick-start1-report2.png)

### <a name="complete-the-format-design"></a><a name="CompleteFormat"></a><span data-ttu-id="e9013-839">Slutför formatdesignen</span><span class="sxs-lookup"><span data-stu-id="e9013-839">Complete the format design</span></span>

1. <span data-ttu-id="e9013-840">Gå till **Organisationsadministration** \> **Elektronisk rapportering** \> **Konfigurationer**.</span><span class="sxs-lookup"><span data-stu-id="e9013-840">Go to **Organization administration** \> **Electronic reporting** \> **Configurations**.</span></span>
2. <span data-ttu-id="e9013-841">På sidan **konfigurationer** i konfigurationsträdet i vänster fönster expanderar du **enkätmodell** och väljer sedan **enkätrapport**.</span><span class="sxs-lookup"><span data-stu-id="e9013-841">On the **Configurations** page, in the configuration tree, expand **Questionnaire model**, and then select **Questionnaire report**.</span></span>
3. <span data-ttu-id="e9013-842">På snabbfliken **Versioner** väljer du den konfigurationsversion som har statusen **Utkast**.</span><span class="sxs-lookup"><span data-stu-id="e9013-842">On the **Versions** FastTab, select the configuration version that has a status of **Draft**.</span></span>
4. <span data-ttu-id="e9013-843">Välj **Ändra status** \> **Slutför**.</span><span class="sxs-lookup"><span data-stu-id="e9013-843">Select **Change status** \> **Complete**.</span></span>

<span data-ttu-id="e9013-844">Status för version 1.1 av denna konfiguration ändras från **utkast** till **slutförd**.</span><span class="sxs-lookup"><span data-stu-id="e9013-844">The status of version 1.1 of this configuration is changed from **Draft** to **Completed**.</span></span> <span data-ttu-id="e9013-845">Version 1.1 kan inte längre ändras.</span><span class="sxs-lookup"><span data-stu-id="e9013-845">Version 1.1 can no longer be changed.</span></span> <span data-ttu-id="e9013-846">Den här versionen innehåller det konfigurerade formatet och kan användas för att skriva ut din anpassade rapport.</span><span class="sxs-lookup"><span data-stu-id="e9013-846">This version contains the configured format and can be used to print your custom report.</span></span> <span data-ttu-id="e9013-847">Version 1.2 av denna konfiguration skapas och har statusen **utkast**.</span><span class="sxs-lookup"><span data-stu-id="e9013-847">Version 1.2 of this configuration is created and has a status of **Draft**.</span></span> <span data-ttu-id="e9013-848">Du kan redigera den här versionen för att justera formatet för rapporten **enkät**.</span><span class="sxs-lookup"><span data-stu-id="e9013-848">You can edit this version to adjust the format of your **Questionnaire** report.</span></span>

![Versioner av den redigerbara ER-konfigurationen på sidan konfigurationer](./media/er-quick-start1-format-configuration.png)

> [!NOTE]
> <span data-ttu-id="e9013-850">Det konfigurerade formatet är din design av **enkät**-rapporten och innehåller inga relationer till de Finance-specifika artefakter.</span><span class="sxs-lookup"><span data-stu-id="e9013-850">The configured format is your design of the **Questionnaire** report and contains no relations to the Finance-specific artefacts.</span></span>

## <a name="develop-application-artefacts-to-call-the-designed-report"></a><a name="DevelopCustomCode"></a><span data-ttu-id="e9013-851">Utveckla programartefakter för att anropa den utformade rapporten</span><span class="sxs-lookup"><span data-stu-id="e9013-851">Develop application artefacts to call the designed report</span></span>

<span data-ttu-id="e9013-852">Som användare i rollen systemadministratör måste du utveckla en ny logik så att det konfigurerade ER-formatet kan anropas från programmets användargränssnitt för att skapa din anpassade rapport.</span><span class="sxs-lookup"><span data-stu-id="e9013-852">As a user in the System Administrator role, you must develop new logic so that the configured ER format can be called from the application user interface (UI) to generate your custom report.</span></span> <span data-ttu-id="e9013-853">För närvarande erbjuder ER inte någon möjlighet att konfigurera den här typen av logik.</span><span class="sxs-lookup"><span data-stu-id="e9013-853">Currently, ER doesn't offer any capability for configuring this type of logic.</span></span> <span data-ttu-id="e9013-854">Därför krävs en del konstruktionsarbete.</span><span class="sxs-lookup"><span data-stu-id="e9013-854">Therefore, some engineering work is required.</span></span> 

<span data-ttu-id="e9013-855">För att utveckla den nya logiken måste du distribuera en topologi som stöder kontinuerlig version.</span><span class="sxs-lookup"><span data-stu-id="e9013-855">To develop the new logic, you must deploy a topology that supports continuous build.</span></span> <span data-ttu-id="e9013-856">Mer information finns i [distribuera topologier som stöder kontinuerlig automatisering av bygga och testa](../perf-test/continuous-build-test-automation.md).</span><span class="sxs-lookup"><span data-stu-id="e9013-856">For more information, see [Deploy topologies that support continuous build and test automation](../perf-test/continuous-build-test-automation.md).</span></span> <span data-ttu-id="e9013-857">Du måste också ha tillgång till utvecklingsmiljön för den här topologin.</span><span class="sxs-lookup"><span data-stu-id="e9013-857">You must also have access to the development environment for this topology.</span></span> <span data-ttu-id="e9013-858">Mer information om tillgängliga ER API:er finns i [ER-ramverks-API](er-apis-app73.md).</span><span class="sxs-lookup"><span data-stu-id="e9013-858">For more information about the available ER API, see [ER framework API](er-apis-app73.md).</span></span>

### <a name="modify-source-code"></a><a name="ModifySourceCode"></a><span data-ttu-id="e9013-859">Modifiera källkod</span><span class="sxs-lookup"><span data-stu-id="e9013-859">Modify source code</span></span>

#### <a name="add-a-data-contract-class"></a><a name="DataContractClass"></a><span data-ttu-id="e9013-860">Lägga till en datakontraktklass</span><span class="sxs-lookup"><span data-stu-id="e9013-860">Add a data contract class</span></span>

<span data-ttu-id="e9013-861">Lägg till den nya klassen **QuestionnairesErReportContract** till ditt Microsoft Visual Studio-projekt och skriv kod som anger det datakontrakt som ska användas för att köra det konfigurerade ER-formatet.</span><span class="sxs-lookup"><span data-stu-id="e9013-861">Add the new **QuestionnairesErReportContract** class to your Microsoft Visual Studio project, and write code that specifies the data contract that should be used to run the configured ER format.</span></span>

```xpp
/// <summary>
///     This class is the data contract class for the <c>QuestionnairesErReportDP</c> class.
/// </summary>
/// <remarks>
///    This is the data contract class for the Questionnaires ER report.
/// </remarks>
[
    DataContractAttribute,
    SysOperationContractProcessingAttribute(classStr(QuestionnairesErReportUIBuilder))
    ]
    public class QuestionnairesErReportContract extends ERFormatMappingRunBaseContract implements SysOperationValidatable
{
    ERFormatMappingId formatMapping;

    /// <summary>
    ///    Validates the report parameters.
    /// </summary>
    /// <returns>
    ///    true if no errors; otherwise, false.
    /// </returns>
    public boolean validate()
    {
        boolean ret = true;
        if (!formatMapping)
        {
            ret = checkFailed(strFmt("@SYS26332", new SysDictType(extendedTypeNum(ERFormatMappingId)).label()));
        }
        return ret;
    }
    [
        DataMemberAttribute('FormatMapping'),
        SysOperationLabelAttribute(literalstr("@ElectronicReporting:FormatMapping")),
        SysOperationHelpTextAttribute(literalstr("@ElectronicReporting:FormatMapping"))
    ]
    public ERFormatMappingId parmFormatMapping(ERFormatMappingId _formatMapping = formatMapping)
    {
        formatMapping = _formatMapping;
        return formatMapping;
    }
}
```

#### <a name="add-a-ui-builder-class"></a><a name="UIBuilderClass"></a><span data-ttu-id="e9013-862">Lägg till en UI-skaparklass</span><span class="sxs-lookup"><span data-stu-id="e9013-862">Add a UI builder class</span></span>

<span data-ttu-id="e9013-863">Lägg till den nya **QuestionnairesErReportUIBuilder**-klassen i Visual Studio-projektet och skriv kod för att skapa en dialogruta för körning som ska användas för att slå upp formatmappnings-ID:t för det återställningsformat som måste köras.</span><span class="sxs-lookup"><span data-stu-id="e9013-863">Add the new **QuestionnairesErReportUIBuilder** class to your Visual Studio project, and write code to generate a runtime dialog box that will be used to look up the format mapping ID of the ER format that must be run.</span></span> <span data-ttu-id="e9013-864">Den angivna koden söker bara efter ER-format som innehåller en datakälla för den typ av **Datamodell** som refererar till **[enkät](#DataModeName)** datamodell med definitionen **[Rot](#RootDefinitionName)**.</span><span class="sxs-lookup"><span data-stu-id="e9013-864">The provided code looks up only ER formats that contain a data source of the **Data model** type that refers to the **[Questionnaires](#DataModeName)** data model by using the **[Root](#RootDefinitionName)** definition.</span></span>

> [!NOTE]
> <span data-ttu-id="e9013-865">Alternativt kan du använda ER-integreringspunkter för att filtrera ER-format.</span><span class="sxs-lookup"><span data-stu-id="e9013-865">Alternatively, you can use ER integration points to filter ER formats.</span></span> <span data-ttu-id="e9013-866">Mer information finns i [API för att visa sökning efter formatmappningar](er-apis-app10-0-11.md#api-to-show-a-format-mapping-lookup).</span><span class="sxs-lookup"><span data-stu-id="e9013-866">For more information, see [API to show a format mapping lookup](er-apis-app10-0-11.md#api-to-show-a-format-mapping-lookup).</span></span>

```xpp
/// <summary>
/// The UIBuilder class for Questionnaires ER report
/// </summary>
class QuestionnairesErReportUIBuilder extends SysOperationAutomaticUIBuilder
{
    public const str ERQuestionnairesModel = 'Questionnaires';
    public const str ERQuestionnairesDataContainer = 'Root';

    /// <summary>
    /// Action after build of the dialog UI.
    /// </summary>
    public void postBuild()
    {
        DialogField formatMapping;
        super();
        formatMapping = this.bindInfo().getDialogField(this.dataContractObject(),
            methodStr(QuestionnairesErReportContract, parmFormatMapping));
        formatMapping.registerOverrideMethod(
            methodStr(FormReferenceControl, lookupReference),
            methodStr(QuestionnairesErReportUIBuilder, formatMappingLookup),
            this);
    }

    /// <summary>
    /// Performs the lookup form for format mapping.
    /// </summary>
    /// <param name="_referenceGroupControl">
    /// The control to perform lookup form.
    /// </param>
    public void formatMappingLookup(FormReferenceControl _referenceGroupControl)
    {
        ERObjectsFactory::createFormatMappingTableLookupForControlAndModel(
            _referenceGroupControl,
            ERQuestionnairesModel,
            ERQuestionnairesDataContainer).performFormLookup();
    }
}
```

#### <a name="add-a-data-provider-class"></a><a name="DataProviderClass"></a><span data-ttu-id="e9013-867">Lägga till en dataleverantörsklass</span><span class="sxs-lookup"><span data-stu-id="e9013-867">Add a data provider class</span></span>

<span data-ttu-id="e9013-868">Lägg till den nya klassen **QuestionnairesErReportDP** till ditt Microsoft Visual Studio-projekt och skriv kod som introducerar den dataleverantör som ska användas för att köra det konfigurerade ER-formatet.</span><span class="sxs-lookup"><span data-stu-id="e9013-868">Add the new **QuestionnairesErReportDP** class to your Visual Studio project, and write code that introduces the data provider that should used to run the configured ER format.</span></span> <span data-ttu-id="e9013-869">Den angivna koden inkluderar bara datakontraktet för denna dataleverantör.</span><span class="sxs-lookup"><span data-stu-id="e9013-869">The provided code includes only the data contract for this data provider.</span></span>

```xpp
/// <summary>
/// Data provider class for Questionnaires ER report.
/// </summary>
public class QuestionnairesErReportDP
{
    QuestionnairesErReportContract contract;
    public static QuestionnairesErReportDP construct()
    {
        QuestionnairesErReportDP  dataProvider;
        dataProvider = new QuestionnairesErReportDP();
        return dataProvider;
    }
}
```

#### <a name="add-a-labels-file"></a><a name="LabelsFile"></a><span data-ttu-id="e9013-870">Lägga till en etikettfil</span><span class="sxs-lookup"><span data-stu-id="e9013-870">Add a labels file</span></span>

<span data-ttu-id="e9013-871">Lägg till den nya etikettfilen **QuestionnairesErReportLabels\_en-US** till ditt Visual Studio-projekt och ange följande etiketter för nya användargränssnittsresurser:</span><span class="sxs-lookup"><span data-stu-id="e9013-871">Add the new **QuestionnairesErReportLabels\_en-US** labels file to your Visual Studio project, and specify the following labels for new UI resources:</span></span>

- <span data-ttu-id="e9013-872">Etiketten **\@QuestionnairesReport** för ett nytt menyalternativ som innehåller följande text på amerikansk engelska (en-US): **enkätrappoprt (drivs av ER)**</span><span class="sxs-lookup"><span data-stu-id="e9013-872">The **\@QuestionnairesReport** label for a new menu item that contains the following text in US English (en-US): **Questionnaires report (powered by ER)**</span></span>
- <span data-ttu-id="e9013-873">Etiketten **\@QuestionnairesReportBatchJobDescription** för en batch-jobbtitel om ett valt ER-format schemaläggs för körning av ett batchjobb</span><span class="sxs-lookup"><span data-stu-id="e9013-873">The **\@QuestionnairesReportBatchJobDescription** label for a batch job title if a selected ER format is scheduled for execution as a batch job</span></span>

#### <a name="add-a-report-service-class"></a><a name="ServiceClass"></a><span data-ttu-id="e9013-874">Lägg till en rapporttjänstklass</span><span class="sxs-lookup"><span data-stu-id="e9013-874">Add a report service class</span></span>

<span data-ttu-id="e9013-875">Lägg till den nya klassen **QuestionnairesErReportService** i Visual Studio-projektet och skriv kod som anropar ett ER-format, identifierar den med ett format mappnings-ID och tillhandahåller ett datakontrakt som parameter.</span><span class="sxs-lookup"><span data-stu-id="e9013-875">Add the new **QuestionnairesErReportService** class to your Visual Studio project, and write code that calls an ER format, identifies it by a format mapping ID, and provides a data contract as a parameter.</span></span>

```xpp
using Microsoft.Dynamics365.LocalizationFramework;
/// <summary>
/// The electronic reporting service class for Questionnaires ER report
/// </summary>
class QuestionnairesErReportService extends SysOperationServiceBase
{
    public const str ERModelDataSourceName = 'model';
    public const str DefaultExportedFileName = 'Questionnaires report';
    public const str ParametersDataSourceName = 'RunTimeParameters';

    /// <summary>
    /// Generates report by using Electronic reporting framework
    /// </summary>
    /// <param name = "_contract">The Questionnaires report contract</param>
    public void generateReportByGER(QuestionnairesErReportContract _contract)
    {
        ERFormatMappingId formatMappingId;
        QuestionnairesErReportDP  dataProvider;
        dataProvider = QuestionnairesErReportDP::construct();
        formatMappingId = _contract.parmFormatMapping();
        if (formatMappingId)
        {
            try
            {
                ERIModelDefinitionParamsAction parameters = new ERModelDefinitionParamsUIActionComposite()
                    .add(new ERModelDefinitionObjectParameterAction(ERModelDataSourceName, ParametersDataSourceName, _contract, true));

                // Call ER to generate the report.
                ERIFormatMappingRun formatMappingRun = ERObjectsFactory::createFormatMappingRunByFormatMappingId(formatMappingId, DefaultExportedFileName);
                if (formatMappingRun.parmShowPromptDialog(true))
                {
                    formatMappingRun.withParameter(parameters);
                    formatMappingRun.withFileDestination(_contract.getFileDestination());
                    formatMappingRun.run();
                }
            }
            catch
            {
                // An error occurred while exporting data.
                error("@SYP4861341");
            }
        }
        else
        {
            // There is no data available.
            info("@SYS300117");
        }
    }
}
```

<span data-ttu-id="e9013-876">När du måste använda ett ER-format som kör programdata måste du konfigurera en datakälla för typen **datamodellen** i formatmappningen.</span><span class="sxs-lookup"><span data-stu-id="e9013-876">When you must use an ER format that runs application data, you must configure a data source of the **Data model** type in the format mapping.</span></span> <span data-ttu-id="e9013-877">Den här datakällan refererar till en specifik del av den angivna datamodellen genom att använda en enda rotdefinition.</span><span class="sxs-lookup"><span data-stu-id="e9013-877">This data source refers to a specific part of the specified data model by using a single root definition.</span></span> <span data-ttu-id="e9013-878">När ER-formatet körs anropar det denna datakälla för att komma åt lämplig ER-modellmappning som konfigurerats för en viss modell och rotdefinition.</span><span class="sxs-lookup"><span data-stu-id="e9013-878">When the ER format is run, it calls this data source to access the appropriate ER model mapping that is configured for a given model and root definition.</span></span>

<span data-ttu-id="e9013-879">All information som du kan förbereda i källkoden och butiken som en del av datakontraktet kan överföras till ER-format med hjälp av en ER-modellmappning av den här typen.</span><span class="sxs-lookup"><span data-stu-id="e9013-879">All the information that you might prepare in the source code and store as part of the data contract can be passed to the running ER format by using an ER model mapping of this type.</span></span> <span data-ttu-id="e9013-880">I ER-modellmappningen måste du konfigurera en datakälla för **objekt** typen som refererar till **[QuestionnairesErReportContract](#DataContractClass)**.</span><span class="sxs-lookup"><span data-stu-id="e9013-880">In the ER model mapping, you must configure a data source of the **Object** type that refers to the **[QuestionnairesErReportContract](#DataContractClass)** class.</span></span> <span data-ttu-id="e9013-881">Om du vill identifiera en modellmappning måste du ange en datakälla som anropar den här modellmappningen.</span><span class="sxs-lookup"><span data-stu-id="e9013-881">To identify a model mapping, you must specify a data source that calls this model mapping.</span></span> <span data-ttu-id="e9013-882">I den angivna koden är denna datakälla angiven av **ERModelDataSourceName** konstanten som har värdet **[modell](#ModelDSName)**.</span><span class="sxs-lookup"><span data-stu-id="e9013-882">In the provided code, this data source specified by the **ERModelDataSourceName** constant that has the **[model](#ModelDSName)** value.</span></span> <span data-ttu-id="e9013-883">Om du vill identifiera vilken datakälla som används för att visa datakontraktet i modellmappningen måste du ange namnet på en datakälla.</span><span class="sxs-lookup"><span data-stu-id="e9013-883">To identify which data source is used to expose the data contract in the model mapping, you must specify a data source name.</span></span> <span data-ttu-id="e9013-884">I den angivna koden är detta namn angivet av konstanten **ParametersDataSourceName** som har värdet <a name="DataContractDSName"></a>**RunTimeParameters**.</span><span class="sxs-lookup"><span data-stu-id="e9013-884">In the provided code, this name is specified by the **ParametersDataSourceName** constant that has <a name="DataContractDSName"></a>**RunTimeParameters** value.</span></span>

> [!NOTE]
> <span data-ttu-id="e9013-885">I en ny miljö kan du behöva uppdatera ER-metadata så att den här typen av klass finns tillgänglig i ER-modellmappningsdesigner.</span><span class="sxs-lookup"><span data-stu-id="e9013-885">In a new environment, you might have to refresh the ER metadata so that this type of class is available in the ER model mapping designer.</span></span> <span data-ttu-id="e9013-886">Mer information finns i [Konfigurera ER-ramverket](electronic-reporting-er-configure-parameters.md#frequently-asked-questions).</span><span class="sxs-lookup"><span data-stu-id="e9013-886">For more information, see [Configure the ER framework](electronic-reporting-er-configure-parameters.md#frequently-asked-questions).</span></span>

#### <a name="add-a-report-controller-class"></a><a name="ControllerClass"></a><span data-ttu-id="e9013-887">Lägg till en rapportkontrollantklass</span><span class="sxs-lookup"><span data-stu-id="e9013-887">Add a report controller class</span></span>

<span data-ttu-id="e9013-888">Lägg till den nya klassen **QuestionnairesErReportController** till ditt Visual Studio projekt och skriv kod som kör ett ER-format i antingen synkront läge eller batchläge, vilket du föredrar, i den dialogruta som har skapats baserat på logiken i den angivna klassen **QuestionnairesErReportUIBuilder**.</span><span class="sxs-lookup"><span data-stu-id="e9013-888">Add the new **QuestionnairesErReportController** class to your Visual Studio project, and write code that runs an ER format in either synchronous mode or batch mode, as you prefer, in the dialog box that is built based on the logic of the provided **QuestionnairesErReportUIBuilder** class.</span></span>

```xpp
/// <summary>
/// The controller for Questionnaires ER report
/// </summary>
class QuestionnairesErReportController extends ERFormatMappingRunBaseController
{
    /// <summary>
    /// The main entrance of the controller
    /// </summary>
    /// <param name = "args">The arguments</param>
    public static void main(Args args)
    {
        QuestionnairesErReportController operation;
        operation = new QuestionnairesErReportController(
            classStr(QuestionnairesErReportService),
            methodStr(QuestionnairesErReportService, generateReportByGER),
            SysOperationExecutionMode::Synchronous);
        operation.startOperation();
    }

    /// <summary>
    /// Gets caption of the dialog.
    /// </summary>
    /// <returns>Caption of the dialog</returns>
    public ClassDescription defaultCaption()
    {
        ClassDescription batchDescription;
        batchDescription = "Questionnaires report (powered by ER)";
        return batchDescription;
    }
}
```

#### <a name="add-a-menu-item"></a><a name="MenuItem"></a><span data-ttu-id="e9013-889">Lägg till ett menyalternativ</span><span class="sxs-lookup"><span data-stu-id="e9013-889">Add a menu item</span></span>

<span data-ttu-id="e9013-890">Lägg till det nya menyalternativet **QuestionnairesErReport** till ditt Visual Studio-projektet.</span><span class="sxs-lookup"><span data-stu-id="e9013-890">Add the new **QuestionnairesErReport** menu item to your Visual Studio project.</span></span> <span data-ttu-id="e9013-891">I egenskapen **Objekt** hänvisar det här menyalternativet till klassen **QuestionnairesErReportController** och används för att ange en användarbehörighet för att välja och köra ett ER-format.</span><span class="sxs-lookup"><span data-stu-id="e9013-891">In the **Object** property, this menu item refers to the **QuestionnairesErReportController** class, and it's used to specify a user permission to select and run an ER format.</span></span> <span data-ttu-id="e9013-892">I egenskapen **etikett** refererar det här menyalternativet till etiketten **\@QuestionnairesReport** som du skapade tidigare, så att korrekt text visas i programgränssnittet.</span><span class="sxs-lookup"><span data-stu-id="e9013-892">In the **Label** property, this menu item refers to the **\@QuestionnairesReport** label that you created earlier, so that correct text is presented in the application UI.</span></span>

#### <a name="add-a-menu-item-to-a-menu"></a><a name="Menu"></a><span data-ttu-id="e9013-893">Lägg till ett menyalternativ till en meny</span><span class="sxs-lookup"><span data-stu-id="e9013-893">Add a menu item to a menu</span></span>

<span data-ttu-id="e9013-894">Lägg till den befintliga **KM**-menyn i Visual Studio-projektet.</span><span class="sxs-lookup"><span data-stu-id="e9013-894">Add the existing **KM** menu to your Visual Studio project.</span></span> <span data-ttu-id="e9013-895">Du måste lägga till ett nytt **QuestionnairesErReport**-objekt av typen **Utdata** i den här menyn.</span><span class="sxs-lookup"><span data-stu-id="e9013-895">You must add a new **QuestionnairesErReport** item of the **Output** type to this menu.</span></span> <span data-ttu-id="e9013-896">Det här objektet måste referera till menyartikeln **QuestionnairesErReport** som beskrivs i föregående avsnitt.</span><span class="sxs-lookup"><span data-stu-id="e9013-896">This item must refer to the **QuestionnairesErReport** menu item that is described in the previous section.</span></span>

#### <a name="build-a-visual-studio-project"></a><a name="BuildVSProject"></a><span data-ttu-id="e9013-897">Bygga ett Visual Studio-projekt</span><span class="sxs-lookup"><span data-stu-id="e9013-897">Build a Visual Studio project</span></span>

<span data-ttu-id="e9013-898">Bygg ditt projekt för att göra ett nytt menyalternativ tillgängligt för användare.</span><span class="sxs-lookup"><span data-stu-id="e9013-898">Build your project to make a new menu item available to users.</span></span>

### <a name="run-a-format-from-the-application"></a><a name="RunFormatFromApp"></a><span data-ttu-id="e9013-899">Kör ett format från programmet</span><span class="sxs-lookup"><span data-stu-id="e9013-899">Run a format from the application</span></span>

1. <span data-ttu-id="e9013-900">Gå till **Enkät** \> **Design** \> **Enkätrapport (drivs av ER)**.</span><span class="sxs-lookup"><span data-stu-id="e9013-900">Go to **Questionnaire** \> **Design** \> **Questionnaires report (powered by ER)**.</span></span>

    ![Att välja menyalternativet enkätrapport (drivs av ER) i modulen enkät för att köra det konfigurerade ER-formatet](./media/er-quick-start1-application-menu-modified.png)

2. <span data-ttu-id="e9013-902">I dialogrutan i fältet **Formatmappning** välj **Enkätrapport**.</span><span class="sxs-lookup"><span data-stu-id="e9013-902">In the dialog box, in the **Format mapping** field, select **Questionnaires report**.</span></span>
3. <span data-ttu-id="e9013-903">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="e9013-903">Select **OK**.</span></span>
4. <span data-ttu-id="e9013-904">I dialogrutan **Elektroniska rapportparametrar** på snabbfliken **Poster som ska ingå** konfigurerar du filtreringsalternativet så att bara enkäten **SBCCrsExam** ingår.</span><span class="sxs-lookup"><span data-stu-id="e9013-904">In the **Electronic report parameters** dialog box, on the **Records to include** FastTab, configure the filtering option so that only the **SBCCrsExam** questionnaire is included.</span></span>
5. <span data-ttu-id="e9013-905">Bekräfta filtreringsåtgärden genom att välja **OK**.</span><span class="sxs-lookup"><span data-stu-id="e9013-905">Select **OK** to confirm the filtering option.</span></span>
6. <span data-ttu-id="e9013-906">Klicka på **OK** om du vill köra rapporten.</span><span class="sxs-lookup"><span data-stu-id="e9013-906">Select **OK** to run the report.</span></span>

    ![Ange urvalskriterier i dialogrutan för Elektronisk rapport](./media/er-quick-start1-report-run-dialog-page.png)

7. <span data-ttu-id="e9013-908">Granska den genererade rapporten.</span><span class="sxs-lookup"><span data-stu-id="e9013-908">Review the generated report.</span></span>

## <a name="tune-a-designed-er-solution"></a><a name="TuneSolution"></a><span data-ttu-id="e9013-909">Finjustera en designad ER-lösning</span><span class="sxs-lookup"><span data-stu-id="e9013-909">Tune a designed ER solution</span></span>

<span data-ttu-id="e9013-910">Du kan ändra den konfigurerade ER-lösningen så att den använder dataleverantörsklassen som du utvecklade för att få åtkomst till detaljer i det ER-format som körs och så att det anger namnet på detta ER-format i en genererad rapport.</span><span class="sxs-lookup"><span data-stu-id="e9013-910">You can modify the configured ER solution so that it uses the data provider class that you developed to access details of the running ER format, and so that it enters the name of this ER format in a generated report.</span></span>

### <a name="modify-a-model-mapping"></a><a name="ModifyModelMapping"></a><span data-ttu-id="e9013-911">Ändra modellmappning</span><span class="sxs-lookup"><span data-stu-id="e9013-911">Modify a model mapping</span></span>

#### <a name="add-data-sources-to-access-a-data-contract-object"></a><a name="AddDataSource1"></a><span data-ttu-id="e9013-912">Lägga till datakällor för att öppna ett datakontraktobjekt</span><span class="sxs-lookup"><span data-stu-id="e9013-912">Add data sources to access a data contract object</span></span>

1. <span data-ttu-id="e9013-913">Gå till **Organisationsadministration** \> **Elektronisk rapportering** \> **Konfigurationer**.</span><span class="sxs-lookup"><span data-stu-id="e9013-913">Go to **Organization administration** \> **Electronic reporting** \> **Configurations**.</span></span>
2. <span data-ttu-id="e9013-914">På sidan **konfigurationer** i konfigurationsträdet i vänster fönster expanderar du **enkätmodell** och väljer sedan **enkätmappning**.</span><span class="sxs-lookup"><span data-stu-id="e9013-914">On the **Configurations** page, in the configuration tree, expand **Questionnaire model**, and then select **Questionnaire mapping**.</span></span>
3. <span data-ttu-id="e9013-915">Välj **Designer** om du vill öppna sidan **Modell till mappning av datakälla**.</span><span class="sxs-lookup"><span data-stu-id="e9013-915">Select **Designer** to open the **Model to datasource mapping** page.</span></span>
4. <span data-ttu-id="e9013-916">Välj **Designer** om du vill öppna den markerade mappningen i modellmappningsdesigner.</span><span class="sxs-lookup"><span data-stu-id="e9013-916">Select **Designer** to open the selected mapping in the model mapping designer.</span></span>
5. <span data-ttu-id="e9013-917">På sidan **Modellmappingsdesigner** i fönstret **Datakälltyper** väljer du **Dynamics 365 for Operations\\Objekt**.</span><span class="sxs-lookup"><span data-stu-id="e9013-917">On the **Model mapping designer** page, in the **Data source types** pane, select **Dynamics 365 for Operations\\Object**.</span></span>
6. <span data-ttu-id="e9013-918">I fönstret **Datakällor** välj **Lägg till rot**.</span><span class="sxs-lookup"><span data-stu-id="e9013-918">In the **Data sources** pane, select **Add root**.</span></span>
7. <span data-ttu-id="e9013-919">I dialogrutan i fältet **Namn** ange **[RunTimeParameters](#DataContractDSName)**, som definieras i källkoden för klassen **QuestionnairesErReportService**.</span><span class="sxs-lookup"><span data-stu-id="e9013-919">In the dialog box, in the **Name** field, enter **[RunTimeParameters](#DataContractDSName)**, as defined in the source code of the **QuestionnairesErReportService** class.</span></span>
8. <span data-ttu-id="e9013-920">I fältet **Klass** ange **[QuestionnairesErReportContract](#DataContractClass)**, som har kodats tidigare.</span><span class="sxs-lookup"><span data-stu-id="e9013-920">In the **Class** field, enter **[QuestionnairesErReportContract](#DataContractClass)**, which was coded earlier.</span></span>
9. <span data-ttu-id="e9013-921">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="e9013-921">Select **OK**.</span></span>
10. <span data-ttu-id="e9013-922">Expandera **RunTimeParameters**.</span><span class="sxs-lookup"><span data-stu-id="e9013-922">Expand **RunTimeParameters**.</span></span>

<span data-ttu-id="e9013-923">Den tillagda datakällan innehåller information om post-ID för den ER-formatmappning som körs.</span><span class="sxs-lookup"><span data-stu-id="e9013-923">The added data source provides information about the record ID of the running ER format mapping.</span></span>

![Tillagd datakälla i ER-modellmappningsdesigner](./media/er-quick-start1-mapping3.png)

#### <a name="add-a-data-source-to-access-er-format-mapping-records"></a><a name="AddDataSource2"></a><span data-ttu-id="e9013-925">Lägga till en datakälla för åtkomst av mappningsposter för ER-format</span><span class="sxs-lookup"><span data-stu-id="e9013-925">Add a data source to access ER format mapping records</span></span>

<span data-ttu-id="e9013-926">Fortsätt att redigera den valda modellmappningen genom att lägga till en datakälla för att komma åt mappningsposter för ER-format.</span><span class="sxs-lookup"><span data-stu-id="e9013-926">Continue to edit the selected model mapping by adding a data source to access ER format mapping records.</span></span>

1. <span data-ttu-id="e9013-927">På sidan **Modellmappingsdesigner** i fönstret **Datakälltyper** väljer du **Dynamics 365 for Operations\\Tabellregister**.</span><span class="sxs-lookup"><span data-stu-id="e9013-927">On the **Model mapping designer** page, in the **Data source types** pane, select **Dynamics 365 for Operations\\Table records**.</span></span>
2. <span data-ttu-id="e9013-928">I fönstret **Datakällor** välj **Lägg till rot**.</span><span class="sxs-lookup"><span data-stu-id="e9013-928">In the **Data sources** pane, select **Add root**.</span></span>
3. <span data-ttu-id="e9013-929">I dialogrutan i fältet **Namn**, ange **ER1**.</span><span class="sxs-lookup"><span data-stu-id="e9013-929">In the dialog box, in the **Name** field, enter **ER1**.</span></span>
4. <span data-ttu-id="e9013-930">I fältet **Tabell** ange **ERFormatMappingTable**.</span><span class="sxs-lookup"><span data-stu-id="e9013-930">In the **Table** field, enter **ERFormatMappingTable**.</span></span>
5. <span data-ttu-id="e9013-931">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="e9013-931">Select **OK**.</span></span>

#### <a name="add-a-data-source-to-access-a-format-mapping-record-of-a-running-er-format"></a><a name="AddDataSource3"></a><span data-ttu-id="e9013-932">Lägga till en datakälla för åtkomst av formatmappningsposter för ett ER-format som körs</span><span class="sxs-lookup"><span data-stu-id="e9013-932">Add a data source to access a format mapping record of a running ER format</span></span>

<span data-ttu-id="e9013-933">Fortsätt att redigera den valda modellmappningen genom att lägga till en datakälla för att komma åt formatmappningsposter för det ER-format som körs.</span><span class="sxs-lookup"><span data-stu-id="e9013-933">Continue to edit the selected model mapping by adding a data source to access the format mapping record of the running ER format.</span></span>

1. <span data-ttu-id="e9013-934">På sidan **Modellmappingsdesigner** i fönstret **Datakälltyper** väljer du **Funktioner\\Beräknade fält**.</span><span class="sxs-lookup"><span data-stu-id="e9013-934">On the **Model mapping designer** page, in the **Data source types** pane, select **Functions\\Calculated field**.</span></span>
2. <span data-ttu-id="e9013-935">I fönstret **Datakällor** välj **Lägg till rot**.</span><span class="sxs-lookup"><span data-stu-id="e9013-935">In the **Data sources** pane, select **Add root**.</span></span>
3. <span data-ttu-id="e9013-936">I dialogrutan i fältet **Namn**, ange **ER2**.</span><span class="sxs-lookup"><span data-stu-id="e9013-936">In the dialog box, in the **Name** field, enter **ER2**.</span></span>
4. <span data-ttu-id="e9013-937">Välj **Redigera recept**.</span><span class="sxs-lookup"><span data-stu-id="e9013-937">Select **Edit formula**.</span></span>
5. <span data-ttu-id="e9013-938">I formelredigeraren i fältet **Formel** ange **FIRSTORNULL (FILTER(ER1, ER1.RecId = RunTimeParameters.parmFormatMapping))**.</span><span class="sxs-lookup"><span data-stu-id="e9013-938">In the formula editor, in the **Formula** field, enter **FIRSTORNULL (FILTER(ER1, ER1.RecId = RunTimeParameters.parmFormatMapping))**.</span></span>
6. <span data-ttu-id="e9013-939">Markera **Spara** och stäng sedan formelredigeraren.</span><span class="sxs-lookup"><span data-stu-id="e9013-939">Select **Save**, and close the formula editor.</span></span>
7. <span data-ttu-id="e9013-940">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="e9013-940">Select **OK**.</span></span>

#### <a name="enter-the-name-of-the-running-er-format-in-the-data-model"></a><a name="AddBinding"></a><span data-ttu-id="e9013-941">Ange namnet på det ER-format som körs i datamodellen</span><span class="sxs-lookup"><span data-stu-id="e9013-941">Enter the name of the running ER format in the data model</span></span>

<span data-ttu-id="e9013-942">Fortsätt att redigera den valda modellmappningen så att namnet på det ER-format som körs anges i datamodellen.</span><span class="sxs-lookup"><span data-stu-id="e9013-942">Continue to edit the selected model mapping so that the name of the running ER format is entered in the data model.</span></span>

1. <span data-ttu-id="e9013-943">På sidan **Modellmappingsdesigner** i fönstret **Datamodell** expandera **ExecutionContext** och välj sedan **ExecutionContext\\FormatName**.</span><span class="sxs-lookup"><span data-stu-id="e9013-943">On the **Model mapping designer** page, in the **Data model** pane, expand **ExecutionContext**, and then select **ExecutionContext\\FormatName**.</span></span>
2. <span data-ttu-id="e9013-944">I fönstret **Datamodell** välj **Redigera** för att konfigurera en databindning för den valda datamodellens fält.</span><span class="sxs-lookup"><span data-stu-id="e9013-944">In the **Data model** pane, select **Edit** to configure a data binding for the selected data model's field.</span></span>
3. <span data-ttu-id="e9013-945">I formelredigeraren i fältet **Formel** anger du **FIRSTORNULL (ER2.'\>Relations'.Format).Name**.</span><span class="sxs-lookup"><span data-stu-id="e9013-945">In the formula editor, in the **Formula** field, enter **FIRSTORNULL (ER2.'\>Relations'.Format).Name**.</span></span>
4. <span data-ttu-id="e9013-946">Markera **Spara** och stäng sedan formelredigeraren.</span><span class="sxs-lookup"><span data-stu-id="e9013-946">Select **Save**, and close the formula editor.</span></span>

<span data-ttu-id="e9013-947">Eftersom du använde fältet **FormatName** visar den konfigurerade modellmappningen namnet på ett ER-format som anropar modellmappningen under körningen.</span><span class="sxs-lookup"><span data-stu-id="e9013-947">Because you used the **FormatName** field, the configured model mapping now exposes the name of an ER format that calls this model mapping during execution.</span></span>

![Bind datamodellfältet till metoden för den tillagda datakällan i ER-modellmappningsdesigner](./media/er-quick-start1-mapping4.png)

#### <a name="complete-the-design-of-the-model-mapping"></a><a name="CompleteModelMapping2"></a><span data-ttu-id="e9013-949">Färdigställa modellmappningens utformning</span><span class="sxs-lookup"><span data-stu-id="e9013-949">Complete the design of the model mapping</span></span>

1. <span data-ttu-id="e9013-950">På sidan **Modellmappningsdesigner** välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="e9013-950">On the **Model mapping designer** page, select **Save**.</span></span>
2. <span data-ttu-id="e9013-951">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="e9013-951">Close the page.</span></span>
3. <span data-ttu-id="e9013-952">Stäng sidan modellmappningar.</span><span class="sxs-lookup"><span data-stu-id="e9013-952">Close the model mappings page.</span></span>
4. <span data-ttu-id="e9013-953">På sidan **konfigurationer** i konfigurationsträdet, se till att konfigurationen **enkätmappning** fortfarande är vald.</span><span class="sxs-lookup"><span data-stu-id="e9013-953">On the **Configurations** page, in the configuration tree, make sure that the **Questionnaire mapping** configuration is still selected.</span></span> <span data-ttu-id="e9013-954">På snabbfliken **Versioner** väljer du den konfigurationsversion som har statusen **Utkast**.</span><span class="sxs-lookup"><span data-stu-id="e9013-954">Then, on the **Versions** FastTab, select the configuration version that has a status of **Draft**.</span></span>
5. <span data-ttu-id="e9013-955">Välj **Ändra status** \> **Slutför**.</span><span class="sxs-lookup"><span data-stu-id="e9013-955">Select **Change status** \> **Complete**.</span></span>

<span data-ttu-id="e9013-956">Status för version 1.2 av denna konfiguration ändras från **utkast** till **slutförd**.</span><span class="sxs-lookup"><span data-stu-id="e9013-956">The status of version 1.2 of this configuration is changed from **Draft** to **Completed**.</span></span> <span data-ttu-id="e9013-957">Version 1.2 kan inte längre ändras.</span><span class="sxs-lookup"><span data-stu-id="e9013-957">Version 1.2 can no longer be changed.</span></span> <span data-ttu-id="e9013-958">Den här versionen innehåller den konfigurerade modellmappningen och kan användas som grund för andra ER-konfigurationer.</span><span class="sxs-lookup"><span data-stu-id="e9013-958">This version contains the configured model mapping and can be used as the basis for other ER configurations.</span></span> <span data-ttu-id="e9013-959">Version 1.3 av denna konfiguration skapas och har statusen **utkast**.</span><span class="sxs-lookup"><span data-stu-id="e9013-959">Version 1.3 of this configuration is created and has a status of **Draft**.</span></span> <span data-ttu-id="e9013-960">Du kan redigera den här versionen för att justera modellmappningen **enkät**.</span><span class="sxs-lookup"><span data-stu-id="e9013-960">You can edit this version to adjust the **Questionnaire** model mapping.</span></span>

### <a name="modify-a-format"></a><a name="ModifyFormat"></a><span data-ttu-id="e9013-961">Ändra ett format</span><span class="sxs-lookup"><span data-stu-id="e9013-961">Modify a format</span></span>

<span data-ttu-id="e9013-962">Du kan ändra det konfigurerade ER-formatet så att namnet visas i sidfoten i en rapport som genereras när ER-formatet körs.</span><span class="sxs-lookup"><span data-stu-id="e9013-962">You can modify the configured ER format so that its name is shown in the footer of a report that is generated when the ER format is run.</span></span>

#### <a name="add-a-new-format-element"></a><a name="AddFormatElement"></a><span data-ttu-id="e9013-963">Lägg till ett nytt formatelement.</span><span class="sxs-lookup"><span data-stu-id="e9013-963">Add a new format element</span></span>

1. <span data-ttu-id="e9013-964">Gå till **Organisationsadministration** \> **Elektronisk rapportering** \> **Konfigurationer**.</span><span class="sxs-lookup"><span data-stu-id="e9013-964">Go to **Organization administration** \> **Electronic reporting** \> **Configurations**.</span></span>
2. <span data-ttu-id="e9013-965">På sidan **konfigurationer** i konfigurationsträdet i vänster fönster expanderar du **enkätmodell** och väljer sedan **enkätrapport**.</span><span class="sxs-lookup"><span data-stu-id="e9013-965">On the **Configurations** page, in the configuration tree, expand **Questionnaire model**, and then select **Questionnaire report**.</span></span>
3. <span data-ttu-id="e9013-966">Välj **Designer**.</span><span class="sxs-lookup"><span data-stu-id="e9013-966">Select **Designer**.</span></span>
4. <span data-ttu-id="e9013-967">På sidan **Formatdesigner** välj rotobjekt **Rapport**.</span><span class="sxs-lookup"><span data-stu-id="e9013-967">On the **Format designer** page, select the **Report** root item.</span></span>
5. <span data-ttu-id="e9013-968">Välj **Lägg till** om du vill lägga till ett nytt kapslat formatelement för det markerade rotobjektet **rapport**.</span><span class="sxs-lookup"><span data-stu-id="e9013-968">Select **Add** to add a new nested format element for the selected **Report** root item.</span></span>
6. <span data-ttu-id="e9013-969">Välj **Excel\\Footer**.</span><span class="sxs-lookup"><span data-stu-id="e9013-969">Select **Excel\\Footer**.</span></span>
7. <span data-ttu-id="e9013-970">I fältet **Namn** ange **Sidfot**.</span><span class="sxs-lookup"><span data-stu-id="e9013-970">In the **Name** field, enter **Footer**.</span></span>
8. <span data-ttu-id="e9013-971">Markera **Report\Footer** och välj sedan **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="e9013-971">Select **Report\Footer**, and then select **Add**.</span></span>
9. <span data-ttu-id="e9013-972">Välj **Text\\String**.</span><span class="sxs-lookup"><span data-stu-id="e9013-972">Select **Text\\String**.</span></span>

#### <a name="bind-the-added-format-element"></a><a name="BindAddedFormatElement"></a><span data-ttu-id="e9013-973">Bind det tillagda formatelementet</span><span class="sxs-lookup"><span data-stu-id="e9013-973">Bind the added format element</span></span>

1. <span data-ttu-id="e9013-974">På sidan **Formatdesigner** på fliken **Mappning** i formatträdet för det aktiva elementet **Footer\\String** välj **Redigera formel**.</span><span class="sxs-lookup"><span data-stu-id="e9013-974">On the **Format designer** page, on the **Mapping** tab, in the format tree, for the active **Footer\\String** element, select **Edit formula**.</span></span>
2. <span data-ttu-id="e9013-975">I formelredigeraren i fältet **Formel** ange **CONCATENATE ("\&C\&10", FORMAT("Generated by'\%1' ER solution", model.ExecutionContext.FormatName))**.</span><span class="sxs-lookup"><span data-stu-id="e9013-975">In the formula editor, in the **Formula** field, enter **CONCATENATE ("\&C\&10", FORMAT("Generated by'\%1' ER solution", model.ExecutionContext.FormatName))**.</span></span>
3. <span data-ttu-id="e9013-976">Markera **Spara** och stäng sedan formelredigeraren.</span><span class="sxs-lookup"><span data-stu-id="e9013-976">Select **Save**, and close the formula editor.</span></span>
4. <span data-ttu-id="e9013-977">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="e9013-977">Select **Save**.</span></span>

<span data-ttu-id="e9013-978">Det konfigurerade formatet har nu ändrats så att namnet infogas i sidfoten i en genererad rapport med hjälp av elementet **Footer\\String**.</span><span class="sxs-lookup"><span data-stu-id="e9013-978">The configured format has now been modified so that its name will be entered in the footer of a generated report by using the **Footer\\String** element.</span></span>

![Lägga till elementet sidfotsformat i det konfigurerade formatet i ER-åtgärdsdesigner](./media/er-quick-start1-template-format-structure3.png)

#### <a name="complete-the-format-design"></a><a name="CompleteFormat2"></a><span data-ttu-id="e9013-980">Slutför formatdesignen</span><span class="sxs-lookup"><span data-stu-id="e9013-980">Complete the format design</span></span>

1. <span data-ttu-id="e9013-981">Stäng sidan **Formatdesigner**.</span><span class="sxs-lookup"><span data-stu-id="e9013-981">Close the **Format designer** page.</span></span>
2. <span data-ttu-id="e9013-982">På sidan **konfigurationer** i konfigurationsträdet, se till att konfigurationen **enkätrapport** fortfarande är vald.</span><span class="sxs-lookup"><span data-stu-id="e9013-982">On the **Configurations** page, in the configuration tree, make sure that the **Questionnaire report** configuration is still selected.</span></span> <span data-ttu-id="e9013-983">På snabbfliken **Versioner** väljer du den konfigurationsversion som har statusen **Utkast**.</span><span class="sxs-lookup"><span data-stu-id="e9013-983">Then, on the **Versions** FastTab, select the configuration version that has a status of **Draft**.</span></span>
3. <span data-ttu-id="e9013-984">Välj **Ändra status** \> **Slutför**.</span><span class="sxs-lookup"><span data-stu-id="e9013-984">Select **Change status** \> **Complete**.</span></span>

<span data-ttu-id="e9013-985">Status för version 1.2 av denna konfiguration ändras från **utkast** till **slutförd**.</span><span class="sxs-lookup"><span data-stu-id="e9013-985">The status of version 1.2 of this configuration is changed from **Draft** to **Completed**.</span></span> <span data-ttu-id="e9013-986">Version 1.2 kan inte längre ändras.</span><span class="sxs-lookup"><span data-stu-id="e9013-986">Version 1.2 can no longer be changed.</span></span> <span data-ttu-id="e9013-987">Den här versionen innehåller det konfigurerade format och kan användas som grund för andra ER-konfigurationer.</span><span class="sxs-lookup"><span data-stu-id="e9013-987">This version contains the configured format and can be used as the basis for other ER configurations.</span></span> <span data-ttu-id="e9013-988">Version 1.3 av denna konfiguration skapas och har statusen **utkast**.</span><span class="sxs-lookup"><span data-stu-id="e9013-988">Version 1.3 of this configuration is created and has a status of **Draft**.</span></span> <span data-ttu-id="e9013-989">Du kan redigera den här versionen för att justera rapporten **enkät**.</span><span class="sxs-lookup"><span data-stu-id="e9013-989">You can edit this version to adjust the **Questionnaire** report.</span></span>

### <a name="run-a-format-from-the-application"></a><a name="RunFormatFromApp2"></a><span data-ttu-id="e9013-990">Kör ett format från programmet</span><span class="sxs-lookup"><span data-stu-id="e9013-990">Run a format from the application</span></span>

1. <span data-ttu-id="e9013-991">Gå till **Enkät** \> **Design** \> **Enkätrapport (drivs av ER)**.</span><span class="sxs-lookup"><span data-stu-id="e9013-991">Go to **Questionnaire** \> **Design** \> **Questionnaires report (powered by ER)**.</span></span>
2. <span data-ttu-id="e9013-992">I dialogrutan i fältet **Formatmappning** välj **Enkätrapport**.</span><span class="sxs-lookup"><span data-stu-id="e9013-992">In the dialog box, in the **Format mapping** field, select **Questionnaires report**.</span></span>
3. <span data-ttu-id="e9013-993">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="e9013-993">Select **OK**.</span></span>
4. <span data-ttu-id="e9013-994">I dialogrutan **ER-parametrar** på snabbfliken **Poster som ska ingå** konfigurerar du filtreringsalternativet så att bara enkäten **SBCCrsExam** ingår.</span><span class="sxs-lookup"><span data-stu-id="e9013-994">In the **ER parameters** dialog box, on the **Records to include** FastTab, configure the filtering option so that only the **SBCCrsExam** questionnaire is included.</span></span>
5. <span data-ttu-id="e9013-995">Bekräfta filtreringsåtgärden genom att välja **OK**.</span><span class="sxs-lookup"><span data-stu-id="e9013-995">Select **OK** to confirm the filtering option.</span></span>
6. <span data-ttu-id="e9013-996">Klicka på **OK** om du vill köra rapporten.</span><span class="sxs-lookup"><span data-stu-id="e9013-996">Select **OK** to run the report.</span></span>
7. <span data-ttu-id="e9013-997">Granska den genererade rapporten i Excel-format.</span><span class="sxs-lookup"><span data-stu-id="e9013-997">Review the generated report in Excel format.</span></span>

<span data-ttu-id="e9013-998">Observera att den genererade rapportens sidfot innehåller namnet på det ER-format som användes för att generera den.</span><span class="sxs-lookup"><span data-stu-id="e9013-998">Notice that the footer of the generated report contains the name of the ER format that was used to generate it.</span></span>

![Genererad rapport i Excel-format](./media/er-quick-start1-report4.png)

### <a name="run-a-format-from-er"></a><a name="RunFormatFromER3"></a><span data-ttu-id="e9013-1000">Kör ett format från ER</span><span class="sxs-lookup"><span data-stu-id="e9013-1000">Run a format from ER</span></span>

1. <span data-ttu-id="e9013-1001">Gå till **Organisationsadministration** \> **Elektronisk rapportering** \> **Konfigurationer**.</span><span class="sxs-lookup"><span data-stu-id="e9013-1001">Go to **Organization administration** \> **Electronic reporting** \> **Configurations**.</span></span>
2. <span data-ttu-id="e9013-1002">På sidan **konfigurationer** i konfigurationsträdet i vänster fönster expanderar du **enkätmodell** och väljer sedan **enkätrapport**.</span><span class="sxs-lookup"><span data-stu-id="e9013-1002">On the **Configurations** page, in the configuration tree, expand **Questionnaire model**, and then select **Questionnaire report**.</span></span>
3. <span data-ttu-id="e9013-1003">Klicka på **Kör** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="e9013-1003">On the Action Pane, select **Run**.</span></span>
4. <span data-ttu-id="e9013-1004">I dialogrutan **Elektroniska rapportparametrar** på snabbfliken **Poster som ska ingå** konfigurerar du filtreringsalternativet så att bara enkäten **SBCCrsExam** ingår.</span><span class="sxs-lookup"><span data-stu-id="e9013-1004">In the **Electronic report parameters** dialog box, on the **Records to include** FastTab, configure the filtering option so that only the **SBCCrsExam** questionnaire is included.</span></span>
5. <span data-ttu-id="e9013-1005">Bekräfta filtreringsåtgärden genom att välja **OK**.</span><span class="sxs-lookup"><span data-stu-id="e9013-1005">Select **OK** to confirm the filtering option.</span></span>
6. <span data-ttu-id="e9013-1006">Klicka på **OK** om du vill köra rapporten.</span><span class="sxs-lookup"><span data-stu-id="e9013-1006">Select **OK** to run the report.</span></span>
7. <span data-ttu-id="e9013-1007">Granska den genererade rapporten i Excel-format.</span><span class="sxs-lookup"><span data-stu-id="e9013-1007">Review the generated report in Excel format.</span></span>

<span data-ttu-id="e9013-1008">Observera att den genererade rapportens sidfot inte innehåller namnet på ER-formatet som användes för att generera den, eftersom datakontraktets objekt inte skickades till modellmappningen vid körning när det anropades av det ER-format som kördes från ER.</span><span class="sxs-lookup"><span data-stu-id="e9013-1008">Notice that the footer of the generated report doesn't contain the name of ER format that was used to generate it, because the data contract object wasn't passed to the running model mapping when it was called by the ER format that was run from ER.</span></span>

### <a name="configure-a-format-destination-for-on-screen-preview"></a><a name="ConfigureDestination"></a><span data-ttu-id="e9013-1009">Konfigurera ett formatmål för förhandsvisning på skärmen</span><span class="sxs-lookup"><span data-stu-id="e9013-1009">Configure a format destination for on-screen preview</span></span>

1. <span data-ttu-id="e9013-1010">Gå till **Organisationsadministration** \> **Elektronisk rapportering** \> **Elektroniska rapporteringsmål**.</span><span class="sxs-lookup"><span data-stu-id="e9013-1010">Go to **Organization administration** \> **Electronic reporting** \> **Electronic reporting destination**.</span></span>
2. <span data-ttu-id="e9013-1011">På sidan **Destination för elektronisk rapportering** lägger du till en målpost för det konfigurerade ER-formatet **enkätrapport**.</span><span class="sxs-lookup"><span data-stu-id="e9013-1011">On the **Electronic reporting destination** page, add a destination record for the configured **Questionnaire report** ER format.</span></span>
3. <span data-ttu-id="e9013-1012">På snabbfliken **Filmål** ange **Skärm** [destination](er-destination-type-screen.md) för formatkomponenten **rapport** som har [lagts till](#AddFormatRootElement) som rotelement för det konfigurerade ER-formatet **enkätrapport**.</span><span class="sxs-lookup"><span data-stu-id="e9013-1012">On the **File destination** FastTab, set up the **Screen** [destination](er-destination-type-screen.md) for the **Report** format component that has been [added](#AddFormatRootElement) as the root element of the configured **Questionnaire report** ER format.</span></span>
4. <span data-ttu-id="e9013-1013">På snabbfliken **inställningar av PDF-konvertering** konfigurera destinationen för att konvertera en rapport till [PDF-format](electronic-reporting-destinations.md#OutputConversionToPDF) som använder sidorienteringen **liggande**.</span><span class="sxs-lookup"><span data-stu-id="e9013-1013">On the **PDF conversion settings** FastTab, configure the destination to convert a report to [PDF format](electronic-reporting-destinations.md#OutputConversionToPDF) that uses the **Landscape** page orientation.</span></span>

![Konfigurera den anpassade skärmens destination för ER-format på sidan Destination för elektronisk rapportering](./media/er-quick-start1-destination.png)

### <a name="run-a-format-from-the-application-to-preview-it-as-a-pdf-document"></a><a name="RunFormatFromApp3"></a><span data-ttu-id="e9013-1015">Kör ett format från programmet för att förhandsgranska det som ett PDF-dokument</span><span class="sxs-lookup"><span data-stu-id="e9013-1015">Run a format from the application to preview it as a PDF document</span></span>

1. <span data-ttu-id="e9013-1016">Gå till **Enkät** \> **Design** \> **Enkätrapport (drivs av ER)**.</span><span class="sxs-lookup"><span data-stu-id="e9013-1016">Go to **Questionnaire** \> **Design** \> **Questionnaires report (powered by ER)**.</span></span>
2. <span data-ttu-id="e9013-1017">I dialogrutan i fältet **Formatmappning** välj **Enkätrapport**.</span><span class="sxs-lookup"><span data-stu-id="e9013-1017">In the dialog box, in the **Format mapping** field, select **Questionnaires report**.</span></span>
3. <span data-ttu-id="e9013-1018">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="e9013-1018">Select **OK**.</span></span>
4. <span data-ttu-id="e9013-1019">I dialogrutan **Elektroniska rapportparametrar** på snabbfliken **Poster som ska ingå** konfigurerar du filtreringsalternativet så att bara enkäten **SBCCrsExam** ingår.</span><span class="sxs-lookup"><span data-stu-id="e9013-1019">In the **Electronic report parameters** dialog box, on the **Records to include** FastTab, configure the filtering option so that only the **SBCCrsExam** questionnaire is included.</span></span>
5. <span data-ttu-id="e9013-1020">Bekräfta filtreringsåtgärden genom att välja **OK**.</span><span class="sxs-lookup"><span data-stu-id="e9013-1020">Select **OK** to confirm the filtering option.</span></span>

    <span data-ttu-id="e9013-1021">På snabbfliken **destinationer** ser du att fältet **resultat** är angivet till **skärm**.</span><span class="sxs-lookup"><span data-stu-id="e9013-1021">On the **Destinations** FastTab, notice that the **Output** field is set to **Screen**.</span></span> <span data-ttu-id="e9013-1022">Om du vill ändra det konfigurerade målet väljer du **ändra**.</span><span class="sxs-lookup"><span data-stu-id="e9013-1022">If you want to change the configured destination, select **Change**.</span></span>

    ![Dialogrutan ER-rapportkörning där du kan ändra det konfigurerade målet](./media/er-quick-start1-run-settings.png)

6. <span data-ttu-id="e9013-1024">Klicka på **OK** om du vill köra rapporten.</span><span class="sxs-lookup"><span data-stu-id="e9013-1024">Select **OK** to run the report.</span></span>
7. <span data-ttu-id="e9013-1025">Granska den genererade rapporten i PDF-format.</span><span class="sxs-lookup"><span data-stu-id="e9013-1025">Review the generated report in PDF format.</span></span>

    ![Granska den genererade rapporten i PDF-format på skärmen.](./media/er-quick-start1-preview-PDF.png)

## <a name="additional-resources"></a><a name="References"></a><span data-ttu-id="e9013-1027">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="e9013-1027">Additional resources</span></span>

- [<span data-ttu-id="e9013-1028">Översikt över elektronisk rapportering</span><span class="sxs-lookup"><span data-stu-id="e9013-1028">Electronic Reporting overview</span></span>](general-electronic-reporting.md)
- [<span data-ttu-id="e9013-1029">Formelspråk i elektronisk rapportering</span><span class="sxs-lookup"><span data-stu-id="e9013-1029">Electronic reporting formula language</span></span>](er-formula-language.md)
- [<span data-ttu-id="e9013-1030">Utforma flerspråkiga rapporter</span><span class="sxs-lookup"><span data-stu-id="e9013-1030">Design multilingual reports</span></span>](er-design-multilingual-reports.md)
- [<span data-ttu-id="e9013-1031">API för ER-ramverk</span><span class="sxs-lookup"><span data-stu-id="e9013-1031">ER framework API</span></span>](er-apis-app73.md)
- [<span data-ttu-id="e9013-1032">CASE-funktion</span><span class="sxs-lookup"><span data-stu-id="e9013-1032">CASE function</span></span>](er-functions-logical-case.md)
- [<span data-ttu-id="e9013-1033">CONCATENATE-funktion</span><span class="sxs-lookup"><span data-stu-id="e9013-1033">CONCATENATE function</span></span>](er-functions-text-concatenate.md)
- [<span data-ttu-id="e9013-1034">DATETIMEFORMAT-funktion</span><span class="sxs-lookup"><span data-stu-id="e9013-1034">DATETIMEFORMAT function</span></span>](er-functions-datetime-datetimeformat.md)
- [<span data-ttu-id="e9013-1035">FILTER-funktion</span><span class="sxs-lookup"><span data-stu-id="e9013-1035">FILTER function</span></span>](er-functions-list-filter.md)
- [<span data-ttu-id="e9013-1036">FIRSTORNULL-funktion</span><span class="sxs-lookup"><span data-stu-id="e9013-1036">FIRSTORNULL function</span></span>](er-functions-list-firstornull.md)
- [<span data-ttu-id="e9013-1037">FORMAT-funktion</span><span class="sxs-lookup"><span data-stu-id="e9013-1037">FORMAT function</span></span>](er-functions-text-format.md)
- [<span data-ttu-id="e9013-1038">IF-funktion</span><span class="sxs-lookup"><span data-stu-id="e9013-1038">IF function</span></span>](er-functions-logical-if.md)
- [<span data-ttu-id="e9013-1039">ORDERBY-funktion</span><span class="sxs-lookup"><span data-stu-id="e9013-1039">ORDERBY function</span></span>](er-functions-list-orderby.md)
- [<span data-ttu-id="e9013-1040">SESSIONNOW-funktion</span><span class="sxs-lookup"><span data-stu-id="e9013-1040">SESSIONNOW function</span></span>](er-functions-datetime-sessionnow.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]