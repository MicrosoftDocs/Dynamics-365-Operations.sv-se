---
title: Lägga till datafält i momsintegreringen genom att använda tillägg
description: I det här avsnittet beskrivs hur du använder X++-tillägg för att lägga till datafält i momsintegreringen.
author: qire
ms.date: 04/20/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 8e3573f9c9971d4a5af33ece08b7e0b43f2e813a
ms.sourcegitcommit: fa99a36c3d30d0c0577fd3f63ed6bf2f71599e40
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/20/2021
ms.locfileid: "5921175"
---
# <a name="add-data-fields-in-the-tax-integration-by-using-extension"></a>Lägga till datafält i momsintegreringen genom att använda tillägg

[!include [banner](../includes/banner.md)]


I det här avsnittet beskrivs hur du använder X++-tillägg för att lägga till datafält i momsintegreringen. De här fälten kan utökas till momsdatamodellen för momstjänsten och användas för att bestämma momskoder. Mer information finns i [Lägg till datafält i momskonfigurationer](tax-service-add-data-fields-tax-configurations.md).

## <a name="data-model"></a>Datamodell

Data i datamodellen transporteras av objekt och implementeras av klasser.

Här är en lista över huvudobjekt:

* AxClass/TaxIntegration **Document** Object
* AxClass/TaxIntegration **Line** Object
* AxClass/TaxIntegration **TaxLine** Object

I följande bild visas hur de här objekten är relaterade.

[![Datamodellobjekt relation](./media/tax-service-customize-image1.png)](./media/tax-service-customize-image1.png)

Ett **Dokument** objekt kan innehålla många **Rad** objekt. Varje objekt innehåller metadata för momstjänsten.

- `TaxIntegrationDocumentObject` har `originAddress` metadata, som innehåller information om källadressen och `includingTax` metadata, som anger om radbeloppet inkluderar moms.
- `TaxIntegrationLineObject` har `itemId`, `quantity` och `categoryId` metadata.

> [!NOTE]
> `TaxIntegrationLineObject` implementerar även **Avgift** objekt.

## <a name="integration-flow"></a>Integreringsflöde

Data i flödet hanteras av aktiviteter.

### <a name="key-activities"></a>Huvudaktiviteter

* AxClass/TaxIntegration **Calculation** ActivityOnDocument
* AxClass/TaxIntegration **CurrencyExchange** ActivityOnDocument
* AxClass/TaxIntegration **DataPersistence** ActivityOnDocument
* AxClass/TaxIntegration **DataRetrieval** ActivityOnDocument
* AxClass/TaxIntegration **SettingRetrieval** ActivityOnDocument

Aktiviteter körs i följande ordning:

1. Ställa in hämtning
2. Datahämtning
3. Beräkningstjänst
4. Valutakurs
5. Databeständighet

Du kan till exempel utöka **datahämtning** före **beräkningstjänsten**.

#### <a name="data-retrieval-activities"></a>Datahämtningsaktiviteter

**Datahämtning** aktiviteter hämtar data från databasen. Adaptrar för olika transaktioner är tillgängliga för att hämta data från olika transaktionsregister:

- AxClass/TaxIntegration **PurchTable** DataRetrieval
- AxClass/TaxIntegration **PurchParmTable** DataRetrieval
- AxClass/TaxIntegration **PurchREQTable** DataRetrieval
- AxClass/TaxIntegration **PurchRFQTable** DataRetrieval
- AxClass/TaxIntegration **VendInvoiceInfoTable** DataRetrieval
- AxClass/TaxIntegration **SalesTable** DataRetrieval
- AxClass/TaxIntegration **SalesParm** DataRetrieval

I dessa **datahämtning** aktiviteter kopieras data från databasen till `TaxIntegrationDocumentObject` och `TaxIntegrationLineObject`. Eftersom alla dessa aktiviteter utökar samma abstrakta mallklass har de vanliga metoder.

#### <a name="calculation-service-activities"></a>Beräkning av serviceaktiviteter

Aktiviteten **Beräkningstjänst** är länken mellan momstjänsten och momsintegrationen. Den här aktiviteten ansvarar för följande funktioner:

1. Konstruera begäran.
2. Bokför begäran till momstjänsten.
3. Få svaret från momstjänsten.
4. Analysera svaret.

Ett datafält som du lägger till på denna begäran bokförs tillsammans med andra metadata. 

## <a name="extension-implementation"></a>Implementering av filnamnstillägg

I det här avsnittet finns detaljerade steg som förklarar hur du implementerar filnamnstillägget. Det använder **Kostnadsställe** och **Projekt** ekonomiska dimensioner som exempel.

### <a name="step-1-add-the-data-variable-in-the-object-class"></a>Steg 1. Lägg till datavariabeln i objektklassen

Objektklassen innehåller datavariabeln och getter-/ setter-metoderna för data. Lägg till datafältet till antingen `TaxIntegrationDocumentObject` eller `TaxIntegrationLineObject`, beroende på vilken nivå fältet har. I följande exempel används radnivån och filnamnet är `TaxIntegrationLineObject_Extension.xpp`.

> [!NOTE]
> Om datafältet som du lägger till är på dokumentnivå, ändrar du filnamnet till `TaxIntegrationDocumentObject_Extension.xpp`.

```X++
[ExtensionOf(classStr(TaxIntegrationLineObject))]
final class TaxIntegrationLineObject_Extension
{
    private OMOperatingUnitNumber costCenter;
    private ProjId projectId;

    /// <summary>
    /// Gets a costCenter.
    /// </summary>
    /// <returns>The cost center.</returns>
    public final OMOperatingUnitNumber getCostCenter()
    {
        return this.costCenter;
    }

    /// <summary>
    /// Sets the cost center.
    /// </summary>
    /// <param name = "_value">The cost center.</param>
    public final void setCostCenter(OMOperatingUnitNumber _value)
    {
        this.costCenter = _value;
    }

    /// <summary>
    /// Gets a project ID.
    /// </summary>
    /// <returns>The project ID.</returns>
    public final ProjId getProjectId()
    {
        return this.projectId;
    }

    /// <summary>
    /// Sets the project ID.
    /// </summary>
    /// <param name = "_value">The project ID.</param>
    public final void setProjectId(ProjId _value)
    {
        this.projectId = _value;
    }
}
```

**Kostnadsställe** och **Projekt** läggs till som privata variabler. Skapa getter- och setter-metoder för dessa datafält för att manipulera data.

### <a name="step-2-retrieve-data-from-the-database"></a>Steg 2. Hämta data från databasen

Ange transaktionen och utöka lämpliga adapterklasser för att hämta data. Om du till exempel använder en **inköpsorder** transaktion, måste du utöka `TaxIntegrationPurchTableDataRetrieval` och `TaxIntegrationVendInvoiceInfoTableDataRetrieval`. 

> [!NOTE]
> `TaxIntegrationPurchParmTableDataRetrieval` ärvs från `TaxIntegrationPurchTableDataRetrieval`. Det bör inte ändras om inte logiken och tabellerna `purchTable` och `purchParmTable` skiljer sig åt.

Om datafältet ska läggas till för alla transaktioner, förläng alla `DataRetrieval` klasser.

Eftersom alla **Datahämtning** utöka samma mallklass, klasstrukturer, variabler och metoder liknar varandra.

```X++
protected TaxIntegrationDocumentObject document;

/// <summary>
/// Copies to the document.
/// </summary>
protected abstract void copyToDocument()
{
    // It is recommended to implement as:
    //
    // this.copyToDocumentByDefault();
    // this.copyToDocumentFromHeaderTable();
    // this.copyAddressToDocument();
}
 
/// <summary>
/// Copies to the current line of the document.
/// </summary>
/// <param name = "_line">The current line of the document.</param>
protected abstract void copyToLine(TaxIntegrationLineObject _line)
{
    // It is recommended to implement as:
    //
    // this.copyToLineByDefault(_line);
    // this.copyToLineFromLineTable(_line);
    // this.copyQuantityAndTransactionAmountToLine(_line);
    // this.copyAddressToLine(_line);
    // this.copyToLineFromHeaderTable(_line);
}
```

Följande exempel visar basstrukturen när registret `PurchTable` används.

```X++
public class TaxIntegrationPurchTableDataRetrieval extends TaxIntegrationAbstractDataRetrievalTemplate
{
    protected PurchTable purchTable;
    protected PurchLine purchLine;

    // Query builder methods
    [Replaceable]
    protected SysDaQueryObject getDocumentQueryObject()
    [Replaceable]
    protected SysDaQueryObject getLineQueryObject()
    [Replaceable]
    protected SysDaQueryObject getDocumentChargeQueryObject()
    [Replaceable]
    protected SysDaQueryObject getLineChargeQueryObject()

    // Data retrieval methods
    protected void copyToDocument()
    protected void copyToDocumentFromHeaderTable()
    protected void copyToLine(TaxIntegrationLineObject _line)
    protected void copyToLineFromLineTable(TaxIntegrationLineObject _line)
    ...
}
```

När `CopyToDocument` metoden anropas finns `this.purchTable` bufferten redan. Syftet med denna metod är att kopiera alla nödvändiga data från `this.purchTable` till `document` genom att använda settermetoden som skapades i `DocumentObject` klassen.

På samma sätt finns det redan en `this.purchLine` buffert i `CopyToLine`-metoden. Syftet med denna metod är att kopiera alla nödvändiga data från `this.purchLine` till `_line` genom att använda settermetoden som skapades i `LineObject` klassen.

Det enklaste tillvägagångssättet är att utvidga `CopyToDocument` och `CopyToLine` metods. Vi rekommenderar dock att du först försöker `copyToDocumentFromHeaderTable` och `copyToLineFromLineTable` metoderna. Om de inte fungerar som du behöver, implementera din egen metod och anropa den `CopyToDocument` och `CopyToLine`. Det finns tre vanliga situationer där du kan använda det här sättet:

- Det obligatoriska fältet är i `PurchTable` eller `PurchLine`. I denna situation kan du utöka `copyToDocumentFromHeaderTable` och `copyToLineFromLineTable`. Här är exempelkoden.

    ```X++
    /// <summary>
    /// Copies to the current line of the document from.
    /// </summary>
    /// <param name = "_line">The current line of the document.</param>
    protected void copyToLineFromLineTable(TaxIntegrationLineObject _line)
    {
        next copyToLineFromLineTable(_line);
        // if we already added XXX in TaxIntegrationLineObject
        _line.setXXX(this.purchLine.XXX);
    }
    ```

- Den obligatoriska informationen finns inte i standardregistret för transaktionen. Det finns dock vissa kopplingsrelationer till standardregistret, och fältet är obligatoriskt på de flesta rader. I den här situationen, byt ut `getDocumentQueryObject` eller `getLineObject` att fråga tabellen efter anslutningsförhållande. I följande exempel är fältet **Leverera nu** integreras med försäljningsordern på radnivå.

    ```X++
    public class TaxIntegrationSalesTableDataRetrieval
    {
        protected MCRSalesLineDropShipment mcrSalesLineDropShipment;

        /// <summary>
        /// Gets the query for the lines of the document.
        /// </summary>
        /// <returns>The query for the lines of the document</returns>
        [Replaceable]
        protected SysDaQueryObject getLineQueryObject()
        {
            return SysDaQueryObjectBuilder::from(this.salesLine)
                .where(this.salesLine, fieldStr(SalesLine, SalesId)).isEqualToLiteral(this.salesTable.SalesId)
                .outerJoin(this.mcrSalesLineDropShipment)
                .where(this.mcrSalesLineDropShipment, fieldStr(MCRSalesLineDropShipment, SalesLine)).isEqualTo(this.salesLine, fieldStr(SalesLine, RecId))
                .toSysDaQueryObject();
        }
    }
    ```

    I det här exemplet `mcrSalesLineDropShipment` buffert och frågan definieras i `getLineQueryObject`. Frågan använder relationen `MCRSalesLineDropShipment.SalesLine == SalesLine.RecId`. Medan du utökar i den här situationen kan du ersätta `getLineQueryObject` med ditt eget uppbyggda frågeobjekt. Observera dock följande poäng:

    * Eftersom returvärdet för metoden `getLineQueryObject` metoden är `SysDaQueryObject`, du måste konstruera det här objektet med SysDa-metoden.
    * Det går inte att ta bort register som finns.

- De data som krävs är relaterade till transaktionsregistret av en komplicerad sammankopplingsrelation, eller relationen s.k. ett till ett (1:1) men ett till många (1:N). I den här situationen blir det lite komplicerat. Situationen gäller exemplet på ekonomiska dimensioner. 

    I den situationen kan du implementera egna metoder för att hämta data. Här är exempelkoden i `TaxIntegrationPurchTableDataRetrieval_Extension.xpp` filen.

    ```X++
    [ExtensionOf(classStr(TaxIntegrationPurchTableDataRetrieval))]
    final class TaxIntegrationPurchTableDataRetrieval_Extension
    {
        private const str CostCenterKey = 'CostCenter';
        private const str ProjectKey = 'Project';

        /// <summary>
        /// Copies to the current line of the document from.
        /// </summary>
        /// <param name = "_line">The current line of the document.</param>
        protected void copyToLineFromLineTable(TaxIntegrationLineObject _line)
        {
            Map dimensionAttributeMap = this.getDimensionAttributeMapByDefaultDimension(this.purchline.DefaultDimension);
            if (dimensionAttributeMap.exists(CostCenterKey))
            {
                _line.setCostCenter(dimensionAttributeMap.lookup(CostCenterKey));
            }
            if (dimensionAttributeMap.exists(ProjectKey))
            {
                _line.setProjectId(dimensionAttributeMap.lookup(ProjectKey));
            }
            next copyToLineFromLineTable(_line);
        }
        private Map getDimensionAttributeMapByDefaultDimension(RefRecId _defaultDimension)
        {
            DimensionAttribute dimensionAttribute;
            DimensionAttributeValue dimensionAttributeValue;
            DimensionAttributeValueSetItem dimensionAttributeValueSetItem;
            Map ret = new Map(Types::String, Types::String);

            select Name, RecId from dimensionAttribute
                join dimensionAttributeValue
                    where dimensionAttributeValue.dimensionAttribute == dimensionAttribute.RecId
                join DimensionAttributeValueSetItem
                    where DimensionAttributeValueSetItem.DimensionAttributeValue == DimensionAttributeValue.RecId
                        && DimensionAttributeValueSetItem.DimensionAttributeValueSet == _defaultDimension;

            while(dimensionAttribute.RecId)
            {
                ret.insert(dimensionAttribute.Name, dimensionAttributeValue.DisplayValue);
                next dimensionAttribute;
            }
            return ret;
        }
    }
    ```

### <a name="step-3-add-data-to-the-request"></a>Steg 3. Lägga till data i en begäran

Utöka eller `copyToTaxableDocumentHeaderWrapperFromTaxIntegrationDocumentObject` eller `copyToTaxableDocumentLineWrapperFromTaxIntegrationLineObjectByLine` metod för att lägga till data i begäran. Här är exempelkoden i `TaxIntegrationCalculationActivityOnDocument_CalculationService_Extension.xpp` filen.

```X++
[ExtensionOf(classStr(TaxIntegrationCalculationActivityOnDocument_CalculationService))]
final static class TaxIntegrationCalculationActivityOnDocument_CalculationService_Extension
{
    // Define key for the form in post request
    private const str IOCostCenter = 'Cost Center';
    private const str IOProject = 'Project';

    /// <summary>
    /// Copies to <c>TaxableDocumentLineWrapper</c> from <c>TaxIntegrationLineObject</c> by line.
    /// </summary>
    /// <param name = "_destination"><c>TaxableDocumentLineWrapper</c>.</param>
    /// <param name = "_source"><c>TaxIntegrationLineObject</c>.</param>
    protected static void copyToTaxableDocumentLineWrapperFromTaxIntegrationLineObjectByLine(Microsoft.Dynamics.TaxCalculation.ApiContracts.TaxableDocumentLineWrapper _destination, TaxIntegrationLineObject _source)
    {
        next copyToTaxableDocumentLineWrapperFromTaxIntegrationLineObjectByLine(_destination, _source);
        // Set the field we need to integrated for tax service
        _destination.SetField(IOCostCenter, _source.getCostCenter());
        _destination.SetField(IOProject, _source.getProjectId());
    }
}
```

I den här koden `_destination` är omslagsobjektet som används för att generera postförfrågan och `_source` är `TaxIntegrationLineObject` objektet. 

> [!NOTE]
> * Definiera nyckeln som används i förfrågningsformuläret som `private const str`.
> * Ställ in fältet i `copyToTaxableDocumentLineWrapperFromTaxIntegrationLineObjectByLine` metoden med hjälp av `SetField` metoden. Datatypen för den andra parametern bör vara `string`. Om datatypen inte finns kan du `string` konvertera den till `string`.

## <a name="appendix"></a>Bilaga

Denna visar den fullständiga exempelkoden för integrering av ekonomiska dimensioner (**Kostnadsställe** och **Projekt**) på radnivå.

### <a name="taxintegrationlineobject_extensionxpp"></a>TaxIntegrationLineObject_Extension.xpp

```X++
[ExtensionOf(classStr(TaxIntegrationLineObject))]
final class TaxIntegrationLineObject_Extension
{
    private OMOperatingUnitNumber costCenter;
    private ProjId projectId;

    /// <summary>
    /// Gets a costCenter.
    /// </summary>
    /// <returns>The cost center.</returns>
    public final OMOperatingUnitNumber getCostCenter()
    {
        return this.costCenter;
    }

    /// <summary>
    /// Sets the cost center.
    /// </summary>
    /// <param name = "_value">The cost center.</param>
    public final void setCostCenter(OMOperatingUnitNumber _value)
    {
        this.costCenter = _value;
    }

    /// <summary>
    /// Gets a project ID.
    /// </summary>
    /// <returns>The project ID.</returns>
    public final ProjId getProjectId()
    {
        return this.projectId;
    }

    /// <summary>
    /// Sets the project ID.
    /// </summary>
    /// <param name = "_value">The project ID.</param>
    public final void setProjectId(ProjId _value)
    {
        this.projectId = _value;
    }
}
```

### <a name="taxintegrationpurchtabledataretrieval_extensionxpp"></a>TaxIntegrationPurchTableDataRetrieval_Extension.xpp

```X++
[ExtensionOf(classStr(TaxIntegrationPurchTableDataRetrieval))]
final class TaxIntegrationPurchTableDataRetrieval_Extension
{
    private const str CostCenterKey = 'CostCenter';
    private const str ProjectKey = 'Project';

    /// <summary>
    /// Copies to the current line of the document from.
    /// </summary>
    /// <param name = "_line">The current line of the document.</param>
    protected void copyToLineFromLineTable(TaxIntegrationLineObject _line)
    {
        Map dimensionAttributeMap = this.getDimensionAttributeMapByDefaultDimension(this.purchline.DefaultDimension);
        if (dimensionAttributeMap.exists(CostCenterKey))
        {
            _line.setCostCenter(dimensionAttributeMap.lookup(CostCenterKey));
        }
        if (dimensionAttributeMap.exists(ProjectKey))
        {
            _line.setProjectId(dimensionAttributeMap.lookup(ProjectKey));
        }
        next copyToLineFromLineTable(_line);
    }
    private Map getDimensionAttributeMapByDefaultDimension(RefRecId _defaultDimension)
    {
        DimensionAttribute dimensionAttribute;
        DimensionAttributeValue dimensionAttributeValue;
        DimensionAttributeValueSetItem dimensionAttributeValueSetItem;
        Map ret = new Map(Types::String, Types::String);
        select Name, RecId from dimensionAttribute
            join dimensionAttributeValue
                where dimensionAttributeValue.dimensionAttribute == dimensionAttribute.RecId
            join DimensionAttributeValueSetItem
                where DimensionAttributeValueSetItem.DimensionAttributeValue == DimensionAttributeValue.RecId
                    && DimensionAttributeValueSetItem.DimensionAttributeValueSet == _defaultDimension;
        while(dimensionAttribute.RecId)
        {
            ret.insert(dimensionAttribute.Name, dimensionAttributeValue.DisplayValue);
            next dimensionAttribute;
        }
        return ret;
    }
}
```

### <a name="taxintegrationcalculationactivityondocument_calculationservice_extensionxpp"></a>TaxIntegrationCalculationActivityOnDocument_CalculationService_Extension.xpp

```X++
[ExtensionOf(classStr(TaxIntegrationCalculationActivityOnDocument_CalculationService))]
final static class TaxIntegrationCalculationActivityOnDocument_CalculationService_Extension
{
    // Define key for the form in post request
    private const str IOCostCenter = 'Cost Center';
    private const str IOProject = 'Project';

    /// <summary>
    /// Copies to <c>TaxableDocumentLineWrapper</c> from <c>TaxIntegrationLineObject</c> by line.
    /// </summary>
    /// <param name = "_destination"><c>TaxableDocumentLineWrapper</c>.</param>
    /// <param name = "_source"><c>TaxIntegrationLineObject</c>.</param>
    protected static void copyToTaxableDocumentLineWrapperFromTaxIntegrationLineObjectByLine(Microsoft.Dynamics.TaxCalculation.ApiContracts.TaxableDocumentLineWrapper _destination, TaxIntegrationLineObject _source)
    {
        next copyToTaxableDocumentLineWrapperFromTaxIntegrationLineObjectByLine(_destination, _source);
        // Set the field we need to integrated for tax service
        _destination.SetField(IOCostCenter, _source.getCostCenter());
        _destination.SetField(IOProject, _source.getProjectId());
    }
}
```
