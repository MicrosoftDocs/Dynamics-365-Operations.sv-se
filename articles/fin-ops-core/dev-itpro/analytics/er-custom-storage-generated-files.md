---
title: Ange anpassade lagringsplatser för genererade dokument
description: Den här artikeln beskriver hur du utökar listan över lagringsplatser för dokument som genererats av elektroniska rapporteringsformat (ER).
author: kfend
ms.date: 10/29/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2019-03-31
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: f938762d722493360614fd53e81bc5a4eba99928
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9268189"
---
# <a name="specify-custom-storage-locations-for-generated-documents"></a>Ange anpassade lagringsplatser för genererade dokument

[!include[banner](../includes/banner.md)]

API (application programming interface) för ramverket för elektronisk rapportering (ER) låter dig utöka lagringsplatser för dokument som ER-format genererar. I den här artikeln beskrivs hur du lägger till en anpassad lagringsplats för genererade dokument genom att delegera uppgiften att skapa ER-mål till standardmålfabriken och sedan implementera en anpassad klass som har sin egen mållogik.

## <a name="prerequisites"></a>Förutsättningar

Distribuera en topologi som stöder kontinuerlig version. Mer information finns i [distribuera topologier som stöder kontinuerlig automatisering av bygga och testa](/dynamics365/unified-operations/dev-itpro/perf-test/continuous-build-test-automation). Du måste också ha tillgång till topologin för någon av följande roller:

- Utvecklare för elektronisk rapportering
- Konsult för funktionen för elektronisk rapportering
- Systemadministratör

Du måste också ha tillgång till utvecklingsmiljön för den här topologin.

Alla uppgifter i den här artikeln kan slutföras i företaget **USMF**.

## <a name="import-the-fixed-asset-roll-forward-er-format"></a>Importera ER-formatet för uppdateringsrapport för anläggningstillgång

För att generera de dokument som du planerar att lägga till en anpassad lagringsplats för [importerar](er-download-configurations-global-repo.md) du ER-formatkonfigurationen för **uppdateringsrapport för anläggningstillgång** till den aktuella topologin.

![Sidan Konfigurationsdatabas.](./media/er-custom-storage-generated-files-import-format.png)

## <a name="run-the-fixed-asset-roll-forward-report"></a>Kör rapporten för Uppdateringsrapport för anläggningstillgång

1. Gå till **Anläggningstillgångar** \> **Förfrågningar och rapporter** \> **Transaktionsrapporter** \> **Uppdatering av anäggningstillgång**.
2. I fältet **Från datum** anger du **1/1/2017** (1 januari, 2017).
3. I fältet **Till datum** anger du **1/31/2017** (31 januari, 2017).
4. I **valutafältet** väljer du **Redovisningsvaluta**.
5. I fältet **Formatmappning** väljer du **Uppdateringsrapport för anläggningstillgång**.
6. Välj **OK**.

![Körningsdialogruta för Uppdateringsrapport över anläggningstillgångar.](./media/er-custom-storage-generated-files-runtime-dialog.png)

I Microsoft Excel granskar du det utgående dokument som genereras och är tillgängligt för hämtning. Detta är [standardbeteendet](electronic-reporting-destinations.md#default-behavior) för ett ER-format som inte är konfigurerat för [destinationer](electronic-reporting-destinations.md) och som körs i interaktivt läge.

## <a name="review-the-source-code"></a>Granska källkoden

Granska koden för metoden `generateReportByGER()` för klassen `AssetRollForwardService`. Observera att metoden `Run()` används för att anropa ER-ramverket och generera en rapport för **Uppdateringsrapport för anläggningstillgång**.

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

## <a name="modify-the-source-code"></a>Modifiera källkoden

1. I projektet Visual Studio lägger du till en ny klass (`AssetRollForwardDestination` i det här exemplet) och skriver kod för att implementera den anpassade destinationen för rapporter för **Uppdateringsrapport för anläggningstillgång** som har genererats.

    - Metoden `new()` är utformad för att hämta det ursprungliga ER-destinationsobjektet och den programlogikbaserade parameter som anger den anpassade plats där genererade rapporter ska lagras. I det här exemplet är den anpassade platsen namnet på en mapp i det lokala filsystemet på servern som kör programobjektservertjänsten (AOS).
    - Metoden `saveFile()` är utformad för att spara ett genererat dokument i en mapp i det lokala filsystemet på servern som kör AOS-tjänsten.

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

2. I projektet Visual Studio lägger du till en ny klass (`AssetRollForwardDestinationFactory` i det här exemplet) och skriver kod för att ställa in en anpassad destinationsfabrik som delegerar att skapa en destination till standarddestinationsfabriken, och för att radbryta en fildestination med din egen destination.

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

3. Ändra den befintliga `AssetRollForwardService`-klassen och skriv kod för att ställa in en anpassad destinationsfabrik för rapportköraren. Observera att den programbaserade parametern som anger en målmapp skickas när en anpassad destinationsfabrik skapas. På så sätt används den målmappen för att lagra genererade filer.

    > [!NOTE] 
    > Kontrollera att den angivna mappen (**c:\\0** i det här exemplet) finns i det lokala filsystemet på servern där AOS-tjänsten körs. I annat fall kommer ett [DirectoryNotFoundException](/dotnet/api/system.io.directorynotfoundexception)-undantag att skapas vid körning.

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

4. Återskapa ditt projekt

## <a name="re-run-the-fixed-asset-roll-forward-report"></a>Kör rapporten för Uppdateringsrapporten för anläggningstillgång på nytt

1. Gå till **Anläggningstillgångar** \> **Förfrågningar och rapporter** \> **Transaktionsrapporter** \> **Uppdatering av anäggningstillgång**.
2. I fältet **Från datum** anger du **1/1/2017**.
3. I fältet **Till datum** anger du **1/31/2017**.
4. I **valutafältet** väljer du **Redovisningsvaluta**.
5. I fältet **Formatmappning** väljer du **Uppdateringsrapport för anläggningstillgång**.
6. Välj **OK**.
7. Bläddra i den lokala **C:\\0**-mappen för att hitta den genererade filen.

> [!NOTE]
> Eftersom objektet `originDestination` inte används i objektet `AssetRollForwardDestination` i det här exemplet kommer konfigurationerna för ER-formatets [destinationer](electronic-reporting-destinations.md) att ignoreras vid körning.

## <a name="additional-resources"></a>Ytterligare resurser

- [Destinationer för elektronisk rapportering (ER)](electronic-reporting-destinations.md)
- [Startsida för utbyggbarhet](../extensibility/extensibility-home-page.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
