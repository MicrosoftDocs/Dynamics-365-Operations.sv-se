---
title: Lägga till datafält i momsintegreringen genom att använda tillägg
description: I det här avsnittet beskrivs hur du använder X++-tillägg för att lägga till datafält i momsintegreringen.
author: qire
ms.date: 03/26/2021
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
ms.openlocfilehash: fdf112bbdd5245d19ab1d07cfcf94c58bf8208c5
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5830350"
---
# <a name="add-data-fields-in-the-tax-integration-by-using-extension"></a><span data-ttu-id="41c74-103">Lägga till datafält i momsintegreringen genom att använda tillägg</span><span class="sxs-lookup"><span data-stu-id="41c74-103">Add data fields in the tax integration by using extension</span></span>

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

<span data-ttu-id="41c74-104">I det här avsnittet beskrivs hur du använder X++-tillägg för att lägga till datafält i momsintegreringen.</span><span class="sxs-lookup"><span data-stu-id="41c74-104">This topic explains how to use X++ extensions to add data fields in the tax integration.</span></span> <span data-ttu-id="41c74-105">De här fälten kan utökas till momsdatamodellen för momstjänsten och användas för att bestämma momskoder.</span><span class="sxs-lookup"><span data-stu-id="41c74-105">These fields can be extended to the tax data model of the tax service and used to determine tax codes.</span></span> <span data-ttu-id="41c74-106">Mer information finns i [Lägg till datafält i momskonfigurationer](tax-service-add-data-fields-tax-configurations.md).</span><span class="sxs-lookup"><span data-stu-id="41c74-106">For more information, see [Add data fields in tax configurations](tax-service-add-data-fields-tax-configurations.md).</span></span>

## <a name="data-model"></a><span data-ttu-id="41c74-107">Datamodell</span><span class="sxs-lookup"><span data-stu-id="41c74-107">Data model</span></span>

<span data-ttu-id="41c74-108">Data i datamodellen transporteras av objekt och implementeras av klasser.</span><span class="sxs-lookup"><span data-stu-id="41c74-108">The data in the data model is carried by objects and implemented by classes.</span></span>

<span data-ttu-id="41c74-109">Här är en lista över huvudobjekt:</span><span class="sxs-lookup"><span data-stu-id="41c74-109">Here is a list of the major objects:</span></span>

* <span data-ttu-id="41c74-110">AxClass/TaxIntegration **Document** Object</span><span class="sxs-lookup"><span data-stu-id="41c74-110">AxClass/TaxIntegration **Document** Object</span></span>
* <span data-ttu-id="41c74-111">AxClass/TaxIntegration **Line** Object</span><span class="sxs-lookup"><span data-stu-id="41c74-111">AxClass/TaxIntegration **Line** Object</span></span>
* <span data-ttu-id="41c74-112">AxClass/TaxIntegration **TaxLine** Object</span><span class="sxs-lookup"><span data-stu-id="41c74-112">AxClass/TaxIntegration **TaxLine** Object</span></span>

<span data-ttu-id="41c74-113">I följande bild visas hur de här objekten är relaterade.</span><span class="sxs-lookup"><span data-stu-id="41c74-113">The following illustration shows how these objects are related.</span></span>

<span data-ttu-id="41c74-114">[![Datamodellobjekt relation](./media/tax-service-customize-image1.png)](./media/tax-service-customize-image1.png)</span><span class="sxs-lookup"><span data-stu-id="41c74-114">[![Data model object relationship](./media/tax-service-customize-image1.png)](./media/tax-service-customize-image1.png)</span></span>

<span data-ttu-id="41c74-115">Ett **Dokument** objekt kan innehålla många **Rad** objekt.</span><span class="sxs-lookup"><span data-stu-id="41c74-115">A **Document** object can contain many **Line** objects.</span></span> <span data-ttu-id="41c74-116">Varje objekt innehåller metadata för momstjänsten.</span><span class="sxs-lookup"><span data-stu-id="41c74-116">Each object contains metadata for the tax service.</span></span>

- <span data-ttu-id="41c74-117">`TaxIntegrationDocumentObject` har `originAddress` metadata, som innehåller information om källadressen och `includingTax` metadata, som anger om radbeloppet inkluderar moms.</span><span class="sxs-lookup"><span data-stu-id="41c74-117">`TaxIntegrationDocumentObject` has `originAddress` metadata, which contains information about the source address, and `includingTax` metadata, which indicates whether the line amount includes sales tax.</span></span>
- <span data-ttu-id="41c74-118">`TaxIntegrationLineObject` har `itemId`, `quantity` och `categoryId` metadata.</span><span class="sxs-lookup"><span data-stu-id="41c74-118">`TaxIntegrationLineObject` has `itemId`, `quantity`, and `categoryId` metadata.</span></span>

> [!NOTE]
> <span data-ttu-id="41c74-119">`TaxIntegrationLineObject` implementerar även **Avgift** objekt.</span><span class="sxs-lookup"><span data-stu-id="41c74-119">`TaxIntegrationLineObject` also implements **Charge** objects.</span></span>

## <a name="integration-flow"></a><span data-ttu-id="41c74-120">Integreringsflöde</span><span class="sxs-lookup"><span data-stu-id="41c74-120">Integration flow</span></span>

<span data-ttu-id="41c74-121">Data i flödet hanteras av aktiviteter.</span><span class="sxs-lookup"><span data-stu-id="41c74-121">The data in the flow is manipulated by activities.</span></span>

### <a name="key-activities"></a><span data-ttu-id="41c74-122">Huvudaktiviteter</span><span class="sxs-lookup"><span data-stu-id="41c74-122">Key activities</span></span>

* <span data-ttu-id="41c74-123">AxClass/TaxIntegration **Calculation** ActivityOnDocument</span><span class="sxs-lookup"><span data-stu-id="41c74-123">AxClass/TaxIntegration **Calculation** ActivityOnDocument</span></span>
* <span data-ttu-id="41c74-124">AxClass/TaxIntegration **CurrencyExchange** ActivityOnDocument</span><span class="sxs-lookup"><span data-stu-id="41c74-124">AxClass/TaxIntegration **CurrencyExchange** ActivityOnDocument</span></span>
* <span data-ttu-id="41c74-125">AxClass/TaxIntegration **DataPersistence** ActivityOnDocument</span><span class="sxs-lookup"><span data-stu-id="41c74-125">AxClass/TaxIntegration **DataPersistence** ActivityOnDocument</span></span>
* <span data-ttu-id="41c74-126">AxClass/TaxIntegration **DataRetrieval** ActivityOnDocument</span><span class="sxs-lookup"><span data-stu-id="41c74-126">AxClass/TaxIntegration **DataRetrieval** ActivityOnDocument</span></span>
* <span data-ttu-id="41c74-127">AxClass/TaxIntegration **SettingRetrieval** ActivityOnDocument</span><span class="sxs-lookup"><span data-stu-id="41c74-127">AxClass/TaxIntegration **SettingRetrieval** ActivityOnDocument</span></span>

<span data-ttu-id="41c74-128">Aktiviteter körs i följande ordning:</span><span class="sxs-lookup"><span data-stu-id="41c74-128">Activities are run in the following order:</span></span>

1. <span data-ttu-id="41c74-129">Ställa in hämtning</span><span class="sxs-lookup"><span data-stu-id="41c74-129">Setting Retrieval</span></span>
2. <span data-ttu-id="41c74-130">Datahämtning</span><span class="sxs-lookup"><span data-stu-id="41c74-130">Data Retrieval</span></span>
3. <span data-ttu-id="41c74-131">Beräkningstjänst</span><span class="sxs-lookup"><span data-stu-id="41c74-131">Calculation Service</span></span>
4. <span data-ttu-id="41c74-132">Valutakurs</span><span class="sxs-lookup"><span data-stu-id="41c74-132">Currency Exchange</span></span>
5. <span data-ttu-id="41c74-133">Databeständighet</span><span class="sxs-lookup"><span data-stu-id="41c74-133">Data Persistence</span></span>

<span data-ttu-id="41c74-134">Du kan till exempel utöka **datahämtning** före **beräkningstjänsten**.</span><span class="sxs-lookup"><span data-stu-id="41c74-134">For example, extend **Data Retrieval** before **Calculation Service**.</span></span>

#### <a name="data-retrieval-activities"></a><span data-ttu-id="41c74-135">Datahämtningsaktiviteter</span><span class="sxs-lookup"><span data-stu-id="41c74-135">Data Retrieval activities</span></span>

<span data-ttu-id="41c74-136">**Datahämtning** aktiviteter hämtar data från databasen.</span><span class="sxs-lookup"><span data-stu-id="41c74-136">**Data Retrieval** activities retrieve data from the database.</span></span> <span data-ttu-id="41c74-137">Adaptrar för olika transaktioner är tillgängliga för att hämta data från olika transaktionsregister:</span><span class="sxs-lookup"><span data-stu-id="41c74-137">Adapters for different transactions are available to retrieve data from different transaction tables:</span></span>

- <span data-ttu-id="41c74-138">AxClass/TaxIntegration **PurchTable** DataRetrieval</span><span class="sxs-lookup"><span data-stu-id="41c74-138">AxClass/TaxIntegration **PurchTable** DataRetrieval</span></span>
- <span data-ttu-id="41c74-139">AxClass/TaxIntegration **PurchParmTable** DataRetrieval</span><span class="sxs-lookup"><span data-stu-id="41c74-139">AxClass/TaxIntegration **PurchParmTable** DataRetrieval</span></span>
- <span data-ttu-id="41c74-140">AxClass/TaxIntegration **PurchREQTable** DataRetrieval</span><span class="sxs-lookup"><span data-stu-id="41c74-140">AxClass/TaxIntegration **PurchREQTable** DataRetrieval</span></span>
- <span data-ttu-id="41c74-141">AxClass/TaxIntegration **PurchRFQTable** DataRetrieval</span><span class="sxs-lookup"><span data-stu-id="41c74-141">AxClass/TaxIntegration **PurchRFQTable** DataRetrieval</span></span>
- <span data-ttu-id="41c74-142">AxClass/TaxIntegration **VendInvoiceInfoTable** DataRetrieval</span><span class="sxs-lookup"><span data-stu-id="41c74-142">AxClass/TaxIntegration **VendInvoiceInfoTable** DataRetrieval</span></span>
- <span data-ttu-id="41c74-143">AxClass/TaxIntegration **SalesTable** DataRetrieval</span><span class="sxs-lookup"><span data-stu-id="41c74-143">AxClass/TaxIntegration **SalesTable** DataRetrieval</span></span>
- <span data-ttu-id="41c74-144">AxClass/TaxIntegration **SalesParm** DataRetrieval</span><span class="sxs-lookup"><span data-stu-id="41c74-144">AxClass/TaxIntegration **SalesParm** DataRetrieval</span></span>

<span data-ttu-id="41c74-145">I dessa **datahämtning** aktiviteter kopieras data från databasen till `TaxIntegrationDocumentObject` och `TaxIntegrationLineObject`.</span><span class="sxs-lookup"><span data-stu-id="41c74-145">In these **Data Retrieval** activities, data is copied from the database to `TaxIntegrationDocumentObject` and `TaxIntegrationLineObject`.</span></span> <span data-ttu-id="41c74-146">Eftersom alla dessa aktiviteter utökar samma abstrakta mallklass har de vanliga metoder.</span><span class="sxs-lookup"><span data-stu-id="41c74-146">Because all these activities extend the same abstract template class, they have common methods.</span></span>

#### <a name="calculation-service-activities"></a><span data-ttu-id="41c74-147">Beräkning av serviceaktiviteter</span><span class="sxs-lookup"><span data-stu-id="41c74-147">Calculation Service activities</span></span>

<span data-ttu-id="41c74-148">Aktiviteten **Beräkningstjänst** är länken mellan momstjänsten och momsintegrationen.</span><span class="sxs-lookup"><span data-stu-id="41c74-148">The **Calculation Service** activity is the link between the tax service and the tax integration.</span></span> <span data-ttu-id="41c74-149">Den här aktiviteten ansvarar för följande funktioner:</span><span class="sxs-lookup"><span data-stu-id="41c74-149">This activity is responsible for the following functions:</span></span>

1. <span data-ttu-id="41c74-150">Konstruera begäran.</span><span class="sxs-lookup"><span data-stu-id="41c74-150">Construct the request.</span></span>
2. <span data-ttu-id="41c74-151">Bokför begäran till momstjänsten.</span><span class="sxs-lookup"><span data-stu-id="41c74-151">Post the request to the tax service.</span></span>
3. <span data-ttu-id="41c74-152">Få svaret från momstjänsten.</span><span class="sxs-lookup"><span data-stu-id="41c74-152">Get the response from the tax service.</span></span>
4. <span data-ttu-id="41c74-153">Analysera svaret.</span><span class="sxs-lookup"><span data-stu-id="41c74-153">Parse the response.</span></span>

<span data-ttu-id="41c74-154">Ett datafält som du lägger till på denna begäran bokförs tillsammans med andra metadata.</span><span class="sxs-lookup"><span data-stu-id="41c74-154">A data field that you add to the request will be posted together with other metadata.</span></span> 

## <a name="extension-implementation"></a><span data-ttu-id="41c74-155">Implementering av filnamnstillägg</span><span class="sxs-lookup"><span data-stu-id="41c74-155">Extension implementation</span></span>

<span data-ttu-id="41c74-156">I det här avsnittet finns detaljerade steg som förklarar hur du implementerar filnamnstillägget.</span><span class="sxs-lookup"><span data-stu-id="41c74-156">This section provides detailed steps that explain how to implement the extension.</span></span> <span data-ttu-id="41c74-157">Det använder **Kostnadsställe** och **Projekt** ekonomiska dimensioner som exempel.</span><span class="sxs-lookup"><span data-stu-id="41c74-157">It uses the **Cost center** and **Project** financial dimensions as examples.</span></span>

### <a name="step-1-add-the-data-variable-in-the-object-class"></a><span data-ttu-id="41c74-158">Steg 1.</span><span class="sxs-lookup"><span data-stu-id="41c74-158">Step 1.</span></span> <span data-ttu-id="41c74-159">Lägg till datavariabeln i objektklassen</span><span class="sxs-lookup"><span data-stu-id="41c74-159">Add the data variable in the object class</span></span>

<span data-ttu-id="41c74-160">Objektklassen innehåller datavariabeln och getter-/ setter-metoderna för data.</span><span class="sxs-lookup"><span data-stu-id="41c74-160">The object class contains the data variable and getter/setter methods for the data.</span></span> <span data-ttu-id="41c74-161">Lägg till datafältet till antingen `TaxIntegrationDocumentObject` eller `TaxIntegrationLineObject`, beroende på vilken nivå fältet har.</span><span class="sxs-lookup"><span data-stu-id="41c74-161">Add the data field to either `TaxIntegrationDocumentObject` or `TaxIntegrationLineObject`, depending on the level of the field.</span></span> <span data-ttu-id="41c74-162">I följande exempel används radnivån och filnamnet är `TaxIntegrationLineObject_Extension.xpp`.</span><span class="sxs-lookup"><span data-stu-id="41c74-162">The following example uses the line level, and the file name is `TaxIntegrationLineObject_Extension.xpp`.</span></span>

> [!NOTE]
> <span data-ttu-id="41c74-163">Om datafältet som du lägger till är på dokumentnivå, ändrar du filnamnet till `TaxIntegrationDocumentObject_Extension.xpp`.</span><span class="sxs-lookup"><span data-stu-id="41c74-163">If the data field that you're adding is at the document level, change the file name to `TaxIntegrationDocumentObject_Extension.xpp`.</span></span>

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

<span data-ttu-id="41c74-164">**Kostnadsställe** och **Projekt** läggs till som privata variabler.</span><span class="sxs-lookup"><span data-stu-id="41c74-164">**Cost center** and **Project** are added as private variables.</span></span> <span data-ttu-id="41c74-165">Skapa getter- och setter-metoder för dessa datafält för att manipulera data.</span><span class="sxs-lookup"><span data-stu-id="41c74-165">Create getter and setter methods for these data fields to manipulate the data.</span></span>

### <a name="step-2-retrieve-data-from-the-database"></a><span data-ttu-id="41c74-166">Steg 2.</span><span class="sxs-lookup"><span data-stu-id="41c74-166">Step 2.</span></span> <span data-ttu-id="41c74-167">Hämta data från databasen</span><span class="sxs-lookup"><span data-stu-id="41c74-167">Retrieve data from the database</span></span>

<span data-ttu-id="41c74-168">Ange transaktionen och utöka lämpliga adapterklasser för att hämta data.</span><span class="sxs-lookup"><span data-stu-id="41c74-168">Specify the transaction, and extend the appropriate adapter classes to retrieve the data.</span></span> <span data-ttu-id="41c74-169">Om du till exempel använder en **inköpsorder** transaktion, måste du utöka `TaxIntegrationPurchTableDataRetrieval` och `TaxIntegrationVendInvoiceInfoTableDataRetrieval`.</span><span class="sxs-lookup"><span data-stu-id="41c74-169">For example, if you use a **Purchase order** transaction, you must extend `TaxIntegrationPurchTableDataRetrieval` and `TaxIntegrationVendInvoiceInfoTableDataRetrieval`.</span></span> 

> [!NOTE]
> <span data-ttu-id="41c74-170">`TaxIntegrationPurchParmTableDataRetrieval` ärvs från `TaxIntegrationPurchTableDataRetrieval`.</span><span class="sxs-lookup"><span data-stu-id="41c74-170">`TaxIntegrationPurchParmTableDataRetrieval` is inherited from `TaxIntegrationPurchTableDataRetrieval`.</span></span> <span data-ttu-id="41c74-171">Det bör inte ändras om inte logiken och tabellerna `purchTable` och `purchParmTable` skiljer sig åt.</span><span class="sxs-lookup"><span data-stu-id="41c74-171">It should not be changed unless the logic of the `purchTable` and `purchParmTable` tables differs.</span></span>

<span data-ttu-id="41c74-172">Om datafältet ska läggas till för alla transaktioner, förläng alla `DataRetrieval` klasser.</span><span class="sxs-lookup"><span data-stu-id="41c74-172">If the data field should be added for all transactions, extend all `DataRetrieval` classes.</span></span>

<span data-ttu-id="41c74-173">Eftersom alla **Datahämtning** utöka samma mallklass, klasstrukturer, variabler och metoder liknar varandra.</span><span class="sxs-lookup"><span data-stu-id="41c74-173">Because all **Data Retrieval** activities extend the same template class, the class structures, variables, and methods are similar.</span></span>

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

<span data-ttu-id="41c74-174">Följande exempel visar basstrukturen när registret `PurchTable` används.</span><span class="sxs-lookup"><span data-stu-id="41c74-174">The following example shows the basic structure when the `PurchTable` table is used.</span></span>

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

<span data-ttu-id="41c74-175">När `CopyToDocument` metoden anropas finns `this.purchTable` bufferten redan.</span><span class="sxs-lookup"><span data-stu-id="41c74-175">When the `CopyToDocument` method is called, the `this.purchTable` buffer already exists.</span></span> <span data-ttu-id="41c74-176">Syftet med denna metod är att kopiera alla nödvändiga data från `this.purchTable` till `document` genom att använda settermetoden som skapades i `DocumentObject` klassen.</span><span class="sxs-lookup"><span data-stu-id="41c74-176">The purpose of this method is to copy all the required data from `this.purchTable` to the `document` object by using the setter method that was created in the `DocumentObject` class.</span></span>

<span data-ttu-id="41c74-177">På samma sätt finns det redan en `this.purchLine` buffert i `CopyToLine`-metoden.</span><span class="sxs-lookup"><span data-stu-id="41c74-177">Likewise, a `this.purchLine` buffer already exists in the `CopyToLine` method.</span></span> <span data-ttu-id="41c74-178">Syftet med denna metod är att kopiera alla nödvändiga data från `this.purchLine` till `_line` genom att använda settermetoden som skapades i `LineObject` klassen.</span><span class="sxs-lookup"><span data-stu-id="41c74-178">The purpose of this method is to copy all the required data from `this.purchLine` to the `_line` object by using the setter method that was created in the `LineObject` class.</span></span>

<span data-ttu-id="41c74-179">Det enklaste tillvägagångssättet är att utvidga `CopyToDocument` och `CopyToLine` metods.</span><span class="sxs-lookup"><span data-stu-id="41c74-179">The most straightforward approach is to extend the `CopyToDocument` and `CopyToLine` methods.</span></span> <span data-ttu-id="41c74-180">Vi rekommenderar dock att du först försöker `copyToDocumentFromHeaderTable` och `copyToLineFromLineTable` metoderna.</span><span class="sxs-lookup"><span data-stu-id="41c74-180">However, we recommend that you try the `copyToDocumentFromHeaderTable` and `copyToLineFromLineTable` methods first.</span></span> <span data-ttu-id="41c74-181">Om de inte fungerar som du behöver, implementera din egen metod och anropa den `CopyToDocument` och `CopyToLine`.</span><span class="sxs-lookup"><span data-stu-id="41c74-181">If they don't work as you require, implement your own method, and call it in `CopyToDocument` and `CopyToLine`.</span></span> <span data-ttu-id="41c74-182">Det finns tre vanliga situationer där du kan använda det här sättet:</span><span class="sxs-lookup"><span data-stu-id="41c74-182">There are three common situations where you might use this approach:</span></span>

- <span data-ttu-id="41c74-183">Det obligatoriska fältet är i `PurchTable` eller `PurchLine`.</span><span class="sxs-lookup"><span data-stu-id="41c74-183">The required field is in `PurchTable` or `PurchLine`.</span></span> <span data-ttu-id="41c74-184">I denna situation kan du utöka `copyToDocumentFromHeaderTable` och `copyToLineFromLineTable`.</span><span class="sxs-lookup"><span data-stu-id="41c74-184">In this situation, you can extend `copyToDocumentFromHeaderTable` and `copyToLineFromLineTable`.</span></span> <span data-ttu-id="41c74-185">Här är exempelkoden.</span><span class="sxs-lookup"><span data-stu-id="41c74-185">Here is the sample code.</span></span>

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

- <span data-ttu-id="41c74-186">Den obligatoriska informationen finns inte i standardregistret för transaktionen.</span><span class="sxs-lookup"><span data-stu-id="41c74-186">The required data isn't in the default table of the transaction.</span></span> <span data-ttu-id="41c74-187">Det finns dock vissa kopplingsrelationer till standardregistret, och fältet är obligatoriskt på de flesta rader.</span><span class="sxs-lookup"><span data-stu-id="41c74-187">However, there are some join relationships with the default table, and the field is required on most lines.</span></span> <span data-ttu-id="41c74-188">I den här situationen, byt ut `getDocumentQueryObject` eller `getLineObject` att fråga tabellen efter anslutningsförhållande.</span><span class="sxs-lookup"><span data-stu-id="41c74-188">In this situation, replace `getDocumentQueryObject` or `getLineObject` to query the table by join relationship.</span></span> <span data-ttu-id="41c74-189">I följande exempel är fältet **Leverera nu** integreras med försäljningsordern på radnivå.</span><span class="sxs-lookup"><span data-stu-id="41c74-189">In the following example, the **Deliver Now** field is integrated with the sales order at the line level.</span></span>

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

    <span data-ttu-id="41c74-190">I det här exemplet `mcrSalesLineDropShipment` buffert och frågan definieras i `getLineQueryObject`.</span><span class="sxs-lookup"><span data-stu-id="41c74-190">In this example, a `mcrSalesLineDropShipment` buffer is declared, and the query is defined in `getLineQueryObject`.</span></span> <span data-ttu-id="41c74-191">Frågan använder relationen `MCRSalesLineDropShipment.SalesLine == SalesLine.RecId`.</span><span class="sxs-lookup"><span data-stu-id="41c74-191">The query uses the relationship `MCRSalesLineDropShipment.SalesLine == SalesLine.RecId`.</span></span> <span data-ttu-id="41c74-192">Medan du utökar i den här situationen kan du ersätta `getLineQueryObject` med ditt eget uppbyggda frågeobjekt.</span><span class="sxs-lookup"><span data-stu-id="41c74-192">While you're extending in this situation, you can replace `getLineQueryObject` with your own constructed query object.</span></span> <span data-ttu-id="41c74-193">Observera dock följande poäng:</span><span class="sxs-lookup"><span data-stu-id="41c74-193">However, note the following points:</span></span>

    * <span data-ttu-id="41c74-194">Eftersom returvärdet för metoden `getLineQueryObject` metoden är `SysDaQueryObject`, du måste konstruera det här objektet med SysDa-metoden.</span><span class="sxs-lookup"><span data-stu-id="41c74-194">Because the return value of the `getLineQueryObject` method is `SysDaQueryObject`, you must construct this object by using the SysDa approach.</span></span>
    * <span data-ttu-id="41c74-195">Det går inte att ta bort register som finns.</span><span class="sxs-lookup"><span data-stu-id="41c74-195">Can't remove existed table.</span></span>

- <span data-ttu-id="41c74-196">De data som krävs är relaterade till transaktionsregistret av en komplicerad sammankopplingsrelation, eller relationen s.k. ett till ett (1:1) men ett till många (1:N).</span><span class="sxs-lookup"><span data-stu-id="41c74-196">The required data is related to the transaction table by a complicated join relationship, or the relation isn't one to one (1:1) but one to many (1:N).</span></span> <span data-ttu-id="41c74-197">I den här situationen blir det lite komplicerat.</span><span class="sxs-lookup"><span data-stu-id="41c74-197">In this situation, things become a little complicated.</span></span> <span data-ttu-id="41c74-198">Situationen gäller exemplet på ekonomiska dimensioner.</span><span class="sxs-lookup"><span data-stu-id="41c74-198">This situation applies to the example of financial dimensions.</span></span> 

    <span data-ttu-id="41c74-199">I den situationen kan du implementera egna metoder för att hämta data.</span><span class="sxs-lookup"><span data-stu-id="41c74-199">In this situation, you can implement your own method to retrieve the data.</span></span> <span data-ttu-id="41c74-200">Här är exempelkoden i `TaxIntegrationPurchTableDataRetrieval_Extension.xpp` filen.</span><span class="sxs-lookup"><span data-stu-id="41c74-200">Here is the sample code in the `TaxIntegrationPurchTableDataRetrieval_Extension.xpp` file.</span></span>

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

### <a name="step-3-add-data-to-the-request"></a><span data-ttu-id="41c74-201">Steg 3.</span><span class="sxs-lookup"><span data-stu-id="41c74-201">Step 3.</span></span> <span data-ttu-id="41c74-202">Lägga till data i en begäran</span><span class="sxs-lookup"><span data-stu-id="41c74-202">Add data to the request</span></span>

<span data-ttu-id="41c74-203">Utöka eller `copyToTaxableDocumentHeaderWrapperFromTaxIntegrationDocumentObject` eller `copyToTaxableDocumentLineWrapperFromTaxIntegrationLineObjectByLine` metod för att lägga till data i begäran.</span><span class="sxs-lookup"><span data-stu-id="41c74-203">Extend the `copyToTaxableDocumentHeaderWrapperFromTaxIntegrationDocumentObject` or `copyToTaxableDocumentLineWrapperFromTaxIntegrationLineObjectByLine` method to add data to the request.</span></span> <span data-ttu-id="41c74-204">Här är exempelkoden i `TaxIntegrationCalculationActivityOnDocument_CalculationService_Extension.xpp` filen.</span><span class="sxs-lookup"><span data-stu-id="41c74-204">Here is the sample code in the `TaxIntegrationCalculationActivityOnDocument_CalculationService_Extension.xpp` file.</span></span>

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

<span data-ttu-id="41c74-205">I den här koden `_destination` är omslagsobjektet som används för att generera postförfrågan och `_source` är `TaxIntegrationLineObject` objektet.</span><span class="sxs-lookup"><span data-stu-id="41c74-205">In this code, `_destination` is the wrapper object that is used to generate the post request, and `_source` is the `TaxIntegrationLineObject` object.</span></span> 

> [!NOTE]
> * <span data-ttu-id="41c74-206">Definiera nyckeln som används i förfrågningsformuläret som `private const str`.</span><span class="sxs-lookup"><span data-stu-id="41c74-206">Define the key that is used in the request form as `private const str`.</span></span>
> * <span data-ttu-id="41c74-207">Ställ in fältet i `copyToTaxableDocumentLineWrapperFromTaxIntegrationLineObjectByLine` metoden med hjälp av `SetField` metoden.</span><span class="sxs-lookup"><span data-stu-id="41c74-207">Set the field in the `copyToTaxableDocumentLineWrapperFromTaxIntegrationLineObjectByLine` method by using the `SetField` method.</span></span> <span data-ttu-id="41c74-208">Datatypen för den andra parametern bör vara `string`.</span><span class="sxs-lookup"><span data-stu-id="41c74-208">The data type of the second parameter should be `string`.</span></span> <span data-ttu-id="41c74-209">Om datatypen inte finns kan du `string` konvertera den till `string`.</span><span class="sxs-lookup"><span data-stu-id="41c74-209">If the data type isn't `string`, convert it to `string`.</span></span>

## <a name="appendix"></a><span data-ttu-id="41c74-210">Bilaga</span><span class="sxs-lookup"><span data-stu-id="41c74-210">Appendix</span></span>

<span data-ttu-id="41c74-211">Denna visar den fullständiga exempelkoden för integrering av ekonomiska dimensioner (**Kostnadsställe** och **Projekt**) på radnivå.</span><span class="sxs-lookup"><span data-stu-id="41c74-211">This appendix shows the complete sample code for the integration of financial dimensions (**Cost center** and **Project**) at the line level.</span></span>

### <a name="taxintegrationlineobject_extensionxpp"></a><span data-ttu-id="41c74-212">TaxIntegrationLineObject_Extension.xpp</span><span class="sxs-lookup"><span data-stu-id="41c74-212">TaxIntegrationLineObject_Extension.xpp</span></span>

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

### <a name="taxintegrationpurchtabledataretrieval_extensionxpp"></a><span data-ttu-id="41c74-213">TaxIntegrationPurchTableDataRetrieval_Extension.xpp</span><span class="sxs-lookup"><span data-stu-id="41c74-213">TaxIntegrationPurchTableDataRetrieval_Extension.xpp</span></span>

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

### <a name="taxintegrationcalculationactivityondocument_calculationservice_extensionxpp"></a><span data-ttu-id="41c74-214">TaxIntegrationCalculationActivityOnDocument_CalculationService_Extension.xpp</span><span class="sxs-lookup"><span data-stu-id="41c74-214">TaxIntegrationCalculationActivityOnDocument_CalculationService_Extension.xpp</span></span>

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
