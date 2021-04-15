---
title: Ange anpassade lagringsplatser för genererade dokument
description: Det här avsnittet beskriver hur du utökar listan över lagringsplatser för dokument som genererats av elektroniska rapporteringsformat (ER).
author: NickSelin
ms.date: 10/29/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2019-3-31
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: 25719de3d86785442e00f7375de525b95bdb094d
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5753706"
---
# <a name="specify-custom-storage-locations-for-generated-documents"></a><span data-ttu-id="1ccc1-103">Ange anpassade lagringsplatser för genererade dokument</span><span class="sxs-lookup"><span data-stu-id="1ccc1-103">Specify custom storage locations for generated documents</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="1ccc1-104">API (application programming interface) för ramverket för elektronisk rapportering (ER) låter dig utöka lagringsplatser för dokument som ER-format genererar.</span><span class="sxs-lookup"><span data-stu-id="1ccc1-104">The application programming interface (API) of the Electronic reporting (ER) framework lets you extend the list of storage locations for documents that ER formats generate.</span></span> <span data-ttu-id="1ccc1-105">I det här avsnittet beskrivs hur du lägger till en anpassad lagringsplats för genererade dokument genom att delegera uppgiften att skapa ER-mål till standardmålfabriken och sedan implementera en anpassad klass som har sin egen mållogik.</span><span class="sxs-lookup"><span data-stu-id="1ccc1-105">This topic explains how to add a custom storage location for generated documents by delegating the task of creating ER destinations to the default destination factory and then implementing a custom class that has its own destination logic.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="1ccc1-106">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="1ccc1-106">Prerequisites</span></span>

<span data-ttu-id="1ccc1-107">Distribuera en topologi som stöder kontinuerlig version.</span><span class="sxs-lookup"><span data-stu-id="1ccc1-107">Deploy a topology that supports continuous build.</span></span> <span data-ttu-id="1ccc1-108">Mer information finns i [distribuera topologier som stöder kontinuerlig automatisering av bygga och testa](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/perf-test/continuous-build-test-automation).</span><span class="sxs-lookup"><span data-stu-id="1ccc1-108">For more information, see [Deploy topologies that support continuous build and test automation](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/perf-test/continuous-build-test-automation).</span></span> <span data-ttu-id="1ccc1-109">Du måste också ha tillgång till topologin för någon av följande roller:</span><span class="sxs-lookup"><span data-stu-id="1ccc1-109">You must have access to this topology for one of the following roles:</span></span>

- <span data-ttu-id="1ccc1-110">Utvecklare för elektronisk rapportering</span><span class="sxs-lookup"><span data-stu-id="1ccc1-110">Electronic reporting developer</span></span>
- <span data-ttu-id="1ccc1-111">Konsult för funktionen för elektronisk rapportering</span><span class="sxs-lookup"><span data-stu-id="1ccc1-111">Electronic reporting functional consultant</span></span>
- <span data-ttu-id="1ccc1-112">Systemadministratör</span><span class="sxs-lookup"><span data-stu-id="1ccc1-112">System administrator</span></span>

<span data-ttu-id="1ccc1-113">Du måste också ha tillgång till utvecklingsmiljön för den här topologin.</span><span class="sxs-lookup"><span data-stu-id="1ccc1-113">You must also have access to the development environment for this topology.</span></span>

<span data-ttu-id="1ccc1-114">Alla uppgifter i det här avsnittet kan slutföras i företaget **USMF**.</span><span class="sxs-lookup"><span data-stu-id="1ccc1-114">All the tasks in this topic can be completed in the **USMF** company.</span></span>

## <a name="import-the-fixed-asset-roll-forward-er-format"></a><span data-ttu-id="1ccc1-115">Importera ER-formatet för uppdateringsrapport för anläggningstillgång</span><span class="sxs-lookup"><span data-stu-id="1ccc1-115">Import the Fixed asset roll forward ER format</span></span>

<span data-ttu-id="1ccc1-116">För att generera de dokument som du planerar att lägga till en anpassad lagringsplats för [importerar](er-download-configurations-global-repo.md) du ER-formatkonfigurationen för **uppdateringsrapport för anläggningstillgång** till den aktuella topologin.</span><span class="sxs-lookup"><span data-stu-id="1ccc1-116">To generate the documents that you plan to add a custom storage location for, [import](er-download-configurations-global-repo.md) the **Fixed asset roll forward** ER format configuration into the current topology.</span></span>

![Sidan Konfigurationsdatabas](./media/er-custom-storage-generated-files-import-format.png)

## <a name="run-the-fixed-asset-roll-forward-report"></a><span data-ttu-id="1ccc1-118">Kör rapporten för Uppdateringsrapport för anläggningstillgång</span><span class="sxs-lookup"><span data-stu-id="1ccc1-118">Run the Fixed asset roll forward report</span></span>

1. <span data-ttu-id="1ccc1-119">Gå till **Anläggningstillgångar** \> **Förfrågningar och rapporter** \> **Transaktionsrapporter** \> **Uppdatering av anäggningstillgång**.</span><span class="sxs-lookup"><span data-stu-id="1ccc1-119">Go to **Fixed assets** \> **Inquiries and reports** \> **Transaction reports** \> **Fixed asset roll forward**.</span></span>
2. <span data-ttu-id="1ccc1-120">I fältet **Från datum** anger du **1/1/2017** (1 januari, 2017).</span><span class="sxs-lookup"><span data-stu-id="1ccc1-120">In the **From date** field, enter **1/1/2017** (January 1, 2017).</span></span>
3. <span data-ttu-id="1ccc1-121">I fältet **Till datum** anger du **1/31/2017** (31 januari, 2017).</span><span class="sxs-lookup"><span data-stu-id="1ccc1-121">In the **To date** field, enter **1/31/2017** (January 31, 2017).</span></span>
4. <span data-ttu-id="1ccc1-122">I **valutafältet** väljer du **Redovisningsvaluta**.</span><span class="sxs-lookup"><span data-stu-id="1ccc1-122">In the **Currency field**, select **Accounting currency**.</span></span>
5. <span data-ttu-id="1ccc1-123">I fältet **Formatmappning** väljer du **Uppdateringsrapport för anläggningstillgång**.</span><span class="sxs-lookup"><span data-stu-id="1ccc1-123">In the **Format mapping** field, select **Fixed asset roll forward**.</span></span>
6. <span data-ttu-id="1ccc1-124">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="1ccc1-124">Select **OK**.</span></span>

![Körningsdialogruta för rapport om Uppdateringsrapport för anläggningstillgång](./media/er-custom-storage-generated-files-runtime-dialog.png)

<span data-ttu-id="1ccc1-126">I Microsoft Excel granskar du det utgående dokument som genereras och är tillgängligt för hämtning.</span><span class="sxs-lookup"><span data-stu-id="1ccc1-126">In Microsoft Excel, review the outbound document that is generated and available for download.</span></span> <span data-ttu-id="1ccc1-127">Detta är [standardbeteendet](electronic-reporting-destinations.md#default-behavior) för ett ER-format som inte är konfigurerat för [destinationer](electronic-reporting-destinations.md) och som körs i interaktivt läge.</span><span class="sxs-lookup"><span data-stu-id="1ccc1-127">This behavior is the [default behavior](electronic-reporting-destinations.md#default-behavior) for an ER format that no [destinations](electronic-reporting-destinations.md) are configured for, and that is running in interactive mode.</span></span>

## <a name="review-the-source-code"></a><span data-ttu-id="1ccc1-128">Granska källkoden</span><span class="sxs-lookup"><span data-stu-id="1ccc1-128">Review the source code</span></span>

<span data-ttu-id="1ccc1-129">Granska koden för metoden `generateReportByGER()` för klassen `AssetRollForwardService`.</span><span class="sxs-lookup"><span data-stu-id="1ccc1-129">Review the code of the `generateReportByGER()` method of the `AssetRollForwardService` class.</span></span> <span data-ttu-id="1ccc1-130">Observera att metoden `Run()` används för att anropa ER-ramverket och generera en rapport för **Uppdateringsrapport för anläggningstillgång**.</span><span class="sxs-lookup"><span data-stu-id="1ccc1-130">Notice that the `Run()` method is used to call the ER framework and generate the **Fixed asset roll forward** report.</span></span>

```xpp
class AssetRollForwardService extends SysOperationServiceBase
{
    public const str ERFormatModelName = 'Fixed assets';
    public const str ERModelDataSourceName = 'model';
    public const str DefaultExportedFileName = 'AssetRollForward';

    /// <summary>
    /// Generates report by general electronic reporting
    /// </summary>
    /// <param name = "_contract">The Asset Period Statement contract</param>
    public void generateReportByGER(AssetRollForwardContract _contract)
    {
        ERFormatMappingId   formatMappingId;
        AssetRollForwardDP  dataProvider;
        AssetRollForwardTmp assetRollForwardTmp;
        Query               query;

        query = new Query(SysOperationHelper::base64Decode(_contract.parmQuery()));
        dataProvider = AssetRollForwardDP::construct();
        formatMappingId = _contract.parmFormatMapping();
        assetRollForwardTmp = dataProvider.getAssetRollForwardTmp(_contract, query);

        if (assetRollForwardTmp)
        {
            try
            {
                ERIModelDefinitionParamsAction parameters = new ERModelDefinitionParamsUIActionComposite()
                    .add(new ERModelDefinitionDatabaseContext().addTemporaryTable(assetRollForwardTmp))
                    .add(new ERModelDefinitionObjectParameterAction(ERModelDataSourceName, 'MyParameters', _contract, true));

                // Call ER to generate the report.
                ERObjectsFactory::createFormatMappingRunByFormatMappingId(formatMappingId, DefaultExportedFileName)
                    .withParameter(parameters)
                    .withFileDestination(_contract.getFileDestination())
                    .run();
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

## <a name="modify-the-source-code"></a><span data-ttu-id="1ccc1-131">Modifiera källkoden</span><span class="sxs-lookup"><span data-stu-id="1ccc1-131">Modify the source code</span></span>

1. <span data-ttu-id="1ccc1-132">I projektet Visual Studio lägger du till en ny klass (`AssetRollForwardDestination` i det här exemplet) och skriver kod för att implementera den anpassade destinationen för rapporter för **Uppdateringsrapport för anläggningstillgång** som har genererats.</span><span class="sxs-lookup"><span data-stu-id="1ccc1-132">In your Visual Studio project, add a new class (`AssetRollForwardDestination` in this example), and write code to implement your custom destination for **Fixed asset roll forward** reports that are generated.</span></span>

    - <span data-ttu-id="1ccc1-133">Metoden `new()` är utformad för att hämta det ursprungliga ER-destinationsobjektet och den programlogikbaserade parameter som anger den anpassade plats där genererade rapporter ska lagras.</span><span class="sxs-lookup"><span data-stu-id="1ccc1-133">The `new()` method is designed to get the original ER destination object and the application logic–driven parameter that specifies the custom location where generated reports should be stored.</span></span> <span data-ttu-id="1ccc1-134">I det här exemplet är den anpassade platsen namnet på en mapp i det lokala filsystemet på servern som kör programobjektservertjänsten (AOS).</span><span class="sxs-lookup"><span data-stu-id="1ccc1-134">In this example, the custom location is the name of a folder of the local file system of the server that runs the Application Object Server (AOS) service.</span></span>
    - <span data-ttu-id="1ccc1-135">Metoden `saveFile()` är utformad för att spara ett genererat dokument i en mapp i det lokala filsystemet på servern som kör AOS-tjänsten.</span><span class="sxs-lookup"><span data-stu-id="1ccc1-135">The `saveFile()` method is designed to save a generated document to a folder of the local file system of the server that runs the AOS service.</span></span>

    ```xpp
    using Microsoft.Dynamics365.LocalizationFramework;

    /// <summary>
    /// Destination class for <c>AssetRollForwardDestinationFactory</c> that stores a generated report.
    /// </summary>
    public class AssetRollForwardDestination implements ERIFileDestination
    {
        private ERIFileDestination originDestination;
        private str TargetFolder;

        /// <summary>
        /// Creates a stream for new file.
        /// </summary>
        /// <param name = "_fileName">Name of a new file.</param>
        /// <returns>Stream for new file.</returns>
        public System.IO.Stream newFileStream(System.String _fileName)
        {
            return originDestination.newFileStream(_fileName);
        }

        /// <summary>
        /// Saves file in destination.
        /// </summary>
        /// <param name = "_stream">A stream to save.</param>
        /// <param name = "_fileName">A file name.</param>
        /// <returns>Saved stream.</returns>
        public System.IO.Stream saveFile(System.IO.Stream _stream, System.String _fileName)
        {
            _stream.Seek(0, System.IO.SeekOrigin::Begin);
            using (var localStream = System.IO.File::OpenWrite(TargetFolder + _fileName))
            {
                _stream.CopyTo(localStream);
            }
            return _stream;
        }

        /// <summary>
        /// Constructs destination for fixed asset roll forward report.
        /// </summary>
        /// <param name = "_originDestination">The original destination.</param>
        /// <param name = "_TargetFoder">The folder to store a report that's being created.</param>
        /// <returns>The fixed asset roll forward destination.</returns>
        public static AssetRollForwardDestination construct(ERIFileDestination _originDestination, str _TargetFoder)
        {
            return new AssetRollForwardDestination(_originDestination, _TargetFoder);
        }

        protected void new(ERIFileDestination _originDestination, str _TargetFoder)
        {
            originDestination = _originDestination;
            TargetFolder = _TargetFoder;
        }
    }
    ```

2. <span data-ttu-id="1ccc1-136">I projektet Visual Studio lägger du till en ny klass (`AssetRollForwardDestinationFactory` i det här exemplet) och skriver kod för att ställa in en anpassad destinationsfabrik som delegerar att skapa en destination till standarddestinationsfabriken, och för att radbryta en fildestination med din egen destination.</span><span class="sxs-lookup"><span data-stu-id="1ccc1-136">In your Visual Studio project, add a new class (`AssetRollForwardDestinationFactory` in this example), and write code to set up a custom destination factory that delegates the creation of a destination to the default destination factory, and to wrap a file destination with your own destination.</span></span>

    ```xpp
    using Microsoft.Dynamics365.LocalizationFramework;
    using Microsoft.Dynamics365.LocalizationFramework.Format.FileGeneration;

    /// <summary>
    /// Destination factory for using <c>AssetRollForwardDestinationFactory</c>.
    /// </summary>
    public class AssetRollForwardDestinationFactory implements ERIFileDestinationFactory, ERIFileDestinationFactoryPostProcessor
    {
        private ERIFileDestinationFactory originDestinationFactory;
        private str TargetFolder;

        /// <summary>
        /// Creates file destination for print management.
        /// </summary>
        /// <param name = "_fileDestination">A default file destination.</param>
        /// <param name = "_identification">An identification strategy.</param>
        /// <param name = "_rootContext">A root context.</param>
        /// <param name = "_root">A root element.</param>
        /// <returns>A file destination.</returns>
        public ERIDataDrivenFileDestination createPrintMgmtDestination(
            ERIFileDestination _fileDestination,
            ERIObjectIdentificationStrategy _identification,
            ERTextFormatDataContext _rootContext,
            ERTextFormatIFileComponent _root)
        {
            ERIDataDrivenFileDestination dataDrivenDestination = originDestinationFactory.createPrintMgmtDestination(
                _fileDestination,
                _identification,
                _rootContext,
                _root);

            IFileDestinationHost fileDestinationHost = dataDrivenDestination as IFileDestinationHost;
            if (fileDestinationHost)
            {
                fileDestinationHost.FileDestination = AssetRollForwardDestination::construct(
                    fileDestinationHost.get_FileDestination(),
                    TargetFolder);
            }

            return dataDrivenDestination;
        }

        /// <summary>
        /// Constructs the fixed asset roll forward destination factory.
        /// </summary>
        /// <param name = "_originDestinationFactory">The original destination.</param>
        /// <param name = "_TargetFolder">The string containing a folder name that corresponds to the report, that's being created.</param>
        /// <returns>The destination factory for the fixed asset roll forward report.</returns>
        public static AssetRollForwardDestinationFactory construct(ERIFileDestinationFactory _originDestinationFactory, str _TargetFolder)
        {
            AssetRollForwardDestinationFactory destinationFactory = new AssetRollForwardDestinationFactory(_originDestinationFactory, _TargetFolder);

            ERIFileDestinationFactoryPostProcessorsHost factoryPostProcessing = ERCast::asObject(destinationFactory.originDestinationFactory) as ERIFileDestinationFactoryPostProcessorsHost;

            if (factoryPostProcessing)
            {
                factoryPostProcessing.addDestinationPostProcessor(destinationFactory);
            }
            return destinationFactory;
        }

        public ERIFileDestination processDestinationAfterCreation(ERIFileDestination _sourceDestination)
        {
            return AssetRollForwardDestination::construct(_sourceDestination, TargetFolder);
        }

        protected void new(ERIFileDestinationFactory _originDestinationFactory, str _TargetFolder)
        {
            originDestinationFactory = _originDestinationFactory;
            TargetFolder = _TargetFolder;
        }
    }
    ```

3. <span data-ttu-id="1ccc1-137">Ändra den befintliga `AssetRollForwardService`-klassen och skriv kod för att ställa in en anpassad destinationsfabrik för rapportköraren.</span><span class="sxs-lookup"><span data-stu-id="1ccc1-137">Modify the existing `AssetRollForwardService` class, and write code to set up a custom destination factory for the report runner.</span></span> <span data-ttu-id="1ccc1-138">Observera att den programbaserade parametern som anger en målmapp skickas när en anpassad destinationsfabrik skapas.</span><span class="sxs-lookup"><span data-stu-id="1ccc1-138">Notice that when a custom destination factory is constructed, the application-driven parameter that specifies a target folder is passed.</span></span> <span data-ttu-id="1ccc1-139">På så sätt används den målmappen för att lagra genererade filer.</span><span class="sxs-lookup"><span data-stu-id="1ccc1-139">In this way, that target folder is used to store generated files.</span></span>

    > [!NOTE] 
    > <span data-ttu-id="1ccc1-140">Kontrollera att den angivna mappen (**c:\\0** i det här exemplet) finns i det lokala filsystemet på servern där AOS-tjänsten körs.</span><span class="sxs-lookup"><span data-stu-id="1ccc1-140">Make sure that the specified folder (**c:\\0** in this example) is present in the local file system of the server that runs the AOS service.</span></span> <span data-ttu-id="1ccc1-141">I annat fall kommer ett [DirectoryNotFoundException](https://docs.microsoft.com/dotnet/api/system.io.directorynotfoundexception?view=netcore-3.1)-undantag att skapas vid körning.</span><span class="sxs-lookup"><span data-stu-id="1ccc1-141">Otherwise, a [DirectoryNotFoundException](https://docs.microsoft.com/dotnet/api/system.io.directorynotfoundexception?view=netcore-3.1) exception will be thrown at runtime.</span></span>

    ```xpp
    using Microsoft.Dynamics365.LocalizationFramework;
    /// <summary>
    /// The electronic reporting service class for fixed asset roll forward report
    /// </summary>
    class AssetRollForwardService extends SysOperationServiceBase
    {
        public const str ERFormatModelName = 'Fixed assets';
        public const str ERModelDataSourceName = 'model';
        public const str DefaultExportedFileName = 'AssetRollForward';

        /// <summary>
        /// Generates report by general electronic reporting
        /// </summary>
        /// <param name = "_contract">The Asset Period Statement contract</param>
        public void generateReportByGER(AssetRollForwardContract _contract)
        {
            ERFormatMappingId   formatMappingId;
            AssetRollForwardDP  dataProvider;
            AssetRollForwardTmp assetRollForwardTmp;
            Query               query;

            query = new Query(SysOperationHelper::base64Decode(_contract.parmQuery()));
            dataProvider = AssetRollForwardDP::construct();
            formatMappingId = _contract.parmFormatMapping();
            assetRollForwardTmp = dataProvider.getAssetRollForwardTmp(_contract, query);

            if (assetRollForwardTmp)
            {
                try
                {
                    ERIModelDefinitionParamsAction parameters = new ERModelDefinitionParamsUIActionComposite()
                        .add(new ERModelDefinitionDatabaseContext().addTemporaryTable(assetRollForwardTmp))
                        .add(new ERModelDefinitionObjectParameterAction(ERModelDataSourceName, 'MyParameters', _contract, true));

                    // Call ER to generate the report.
                    ERIFormatMappingRun formatMappingRun = ERObjectsFactory::createFormatMappingRunByFormatMappingId(formatMappingId, DefaultExportedFileName);
                    formatMappingRun.withParameter(parameters);
                    formatMappingRun.withFileDestination(_contract.getFileDestination());

                    ERIFileDestinationFactoryHost factoryHost = ERCast::asObject(formatMappingRun) as ERIFileDestinationFactoryHost;
                    if (factoryHost)
                    {
                        ERIFileDestinationFactory fileDestinationFactory = factoryHost.getFileDestinationFactory();
                        factoryHost.setFileDestinationFactory(AssetRollForwardDestinationFactory::construct(fileDestinationFactory, @'c:\0\'));
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

4. <span data-ttu-id="1ccc1-142">Återskapa ditt projekt</span><span class="sxs-lookup"><span data-stu-id="1ccc1-142">Rebuild your project.</span></span>

## <a name="re-run-the-fixed-asset-roll-forward-report"></a><span data-ttu-id="1ccc1-143">Kör rapporten för Uppdateringsrapporten för anläggningstillgång på nytt</span><span class="sxs-lookup"><span data-stu-id="1ccc1-143">Re-run the Fixed asset roll forward report</span></span>

1. <span data-ttu-id="1ccc1-144">Gå till **Anläggningstillgångar** \> **Förfrågningar och rapporter** \> **Transaktionsrapporter** \> **Uppdatering av anäggningstillgång**.</span><span class="sxs-lookup"><span data-stu-id="1ccc1-144">Go to **Fixed assets** \> **Inquiries and reports** \> **Transaction reports** \> **Fixed asset roll forward**.</span></span>
2. <span data-ttu-id="1ccc1-145">I fältet **Från datum** anger du **1/1/2017**.</span><span class="sxs-lookup"><span data-stu-id="1ccc1-145">In the **From date** field, enter **1/1/2017**.</span></span>
3. <span data-ttu-id="1ccc1-146">I fältet **Till datum** anger du **1/31/2017**.</span><span class="sxs-lookup"><span data-stu-id="1ccc1-146">In the **To date** field, enter **1/31/2017**.</span></span>
4. <span data-ttu-id="1ccc1-147">I **valutafältet** väljer du **Redovisningsvaluta**.</span><span class="sxs-lookup"><span data-stu-id="1ccc1-147">In the **Currency field**, select **Accounting currency**.</span></span>
5. <span data-ttu-id="1ccc1-148">I fältet **Formatmappning** väljer du **Uppdateringsrapport för anläggningstillgång**.</span><span class="sxs-lookup"><span data-stu-id="1ccc1-148">In the **Format mapping** field, select **Fixed asset roll forward**.</span></span>
6. <span data-ttu-id="1ccc1-149">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="1ccc1-149">Select **OK**.</span></span>
7. <span data-ttu-id="1ccc1-150">Bläddra i den lokala **C:\\0**-mappen för att hitta den genererade filen.</span><span class="sxs-lookup"><span data-stu-id="1ccc1-150">Browse the local **C:\\0** folder to find the generated file.</span></span>

> [!NOTE]
> <span data-ttu-id="1ccc1-151">Eftersom objektet `originDestination` inte används i objektet `AssetRollForwardDestination` i det här exemplet kommer konfigurationerna för ER-formatets [destinationer](electronic-reporting-destinations.md) att ignoreras vid körning.</span><span class="sxs-lookup"><span data-stu-id="1ccc1-151">Because the `originDestination` object isn't used in the `AssetRollForwardDestination` object in this example, the configurations for the ER format [destinations](electronic-reporting-destinations.md) will be ignored at runtime.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="1ccc1-152">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="1ccc1-152">Additional resources</span></span>

- [<span data-ttu-id="1ccc1-153">Destinationer för elektronisk rapportering (ER)</span><span class="sxs-lookup"><span data-stu-id="1ccc1-153">Electronic reporting (ER) destinations</span></span>](electronic-reporting-destinations.md)
- [<span data-ttu-id="1ccc1-154">Startsida för utbyggbarhet</span><span class="sxs-lookup"><span data-stu-id="1ccc1-154">Extensibility home page</span></span>](../extensibility/extensibility-home-page.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]