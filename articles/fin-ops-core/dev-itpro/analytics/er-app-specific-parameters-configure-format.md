---
title: Konfigurera ER-format för användning av parametrar som anges per juridisk person
description: I det här avsnittet beskrivs hur du kan konfigurera format för elektroniska rapporter (ER) att använda parametrar som anges per juridisk person.
author: NickSelin
manager: AnnBe
ms.date: 10/26/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERSolutionTable, EROperationDesigner, ERLookupDesigner, ERComponentLookupStructureEditing
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2019-01-01
ms.dyn365.ops.version: Release 8.1.3
ms.openlocfilehash: d32da76ee46ff5293ae8fefb16d251564b6be21a
ms.sourcegitcommit: d6196d83c7b9166ddb4fe43a91e6bd0ad9da2099
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/31/2019
ms.locfileid: "2694256"
---
# <a name="configure-er-formats-to-use-parameters-that-are-specified-per-legal-entity"></a><span data-ttu-id="60cae-103">Konfigurera ER-format för användning av parametrar som anges per juridisk person</span><span class="sxs-lookup"><span data-stu-id="60cae-103">Configure ER formats to use parameters that are specified per legal entity</span></span>

[!include[banner](../includes/banner.md)]

## <a name="overview"></a><span data-ttu-id="60cae-104">Översikt</span><span class="sxs-lookup"><span data-stu-id="60cae-104">Overview</span></span>

<span data-ttu-id="60cae-105">I många av de format för elektroniska rapportering (ER) som du vill utforma måste du filtrera data genom att använda en uppsättning värden som är specifika för varje juridisk person i din instans (t.ex. en uppsättning momskoder som filtrerar momstransaktioner).</span><span class="sxs-lookup"><span data-stu-id="60cae-105">In many of the Electronic reporting (ER) formats that you will design, you must filter data by using a set of values that are specific to each legal entity of your instance (for example, a set of tax codes to filter tax transactions).</span></span> <span data-ttu-id="60cae-106">När filtrering av den här typen har konfigurerats i ett ER-format används värden som är beroende av den juridiska personen (t.ex. momskoder) i uttrycken i ER-format för att ange datafiltreringsregler.</span><span class="sxs-lookup"><span data-stu-id="60cae-106">Currently, when filtering of this type is configured in an ER format, values that are dependent on the legal entity (for example, tax codes) are used in expressions of the ER format to specify data filtering rules.</span></span> <span data-ttu-id="60cae-107">Det innebär att ER-formatet blir juridiskt-specifikt och att du kan generera de nödvändiga rapporterna måste du skapa härledda kopior av det ursprungliga ER-formatet för varje juridisk person där du måste köra ER-formatet.</span><span class="sxs-lookup"><span data-stu-id="60cae-107">Therefore, the ER format is made legal entity–specific, and to generate the required reports, you must create derived copies of the original ER format for each legal entity where you have to run the ER format.</span></span> <span data-ttu-id="60cae-108">Varje härlett ER-format måste redigeras för att få juridiska enheter-specifika värden i den, baserat på när den ursprungliga (bas) versionen har uppdaterats, exporterats från en testmiljö och importerats till en produktionsmiljö när den måste distribueras för produktionsanvändning och så vidare.</span><span class="sxs-lookup"><span data-stu-id="60cae-108">Each derived ER format must be edited to bring legal entity–specific values into it, rebased whenever the original (base) version has been updated, exported from a test environment and imported into a production environment when it must be deployed for production use, and so on.</span></span> <span data-ttu-id="60cae-109">Det innebär att underhåll av den här typen av ER-lösning är ganska komplicerat och tar lång tid av flera skäl:</span><span class="sxs-lookup"><span data-stu-id="60cae-109">Therefore, maintenance of this type of configured ER solution is quite complex and time-consuming for several reasons:</span></span>

-   <span data-ttu-id="60cae-110">Ju fler juridiska enheter, desto fler ER-format måste konfigureras.</span><span class="sxs-lookup"><span data-stu-id="60cae-110">The more legal entities there are, the more ER format configurations must be maintained.</span></span>
-   <span data-ttu-id="60cae-111">Underhåll av ER-konfigurationer kräver att företags användare har ER-kunskap.</span><span class="sxs-lookup"><span data-stu-id="60cae-111">Maintenance of ER configurations requires that business users have ER knowledge.</span></span>

<span data-ttu-id="60cae-112">Med hjälp av parametrarna för ER-programspecifika parametrar kan avancerade användare konfigurera datafiltrering i ett ER-format så att det baseras på en uppsättning abstrakta regler.</span><span class="sxs-lookup"><span data-stu-id="60cae-112">The ER application-specific parameters feature lets power users configure data filtering in an ER format so that it's based on a set of abstract rules.</span></span> <span data-ttu-id="60cae-113">Den här uppsättningen regler kan konfigureras till att använda datakällor som är tillgängliga i ett ER-format.</span><span class="sxs-lookup"><span data-stu-id="60cae-113">This set of rules can be configured to use the data sources that are available in an ER format.</span></span> <span data-ttu-id="60cae-114">Affärsanvändare kan sedan ange verkliga regler utanför ER-ramverket med hjälp av det användargränssnitt som genereras automatiskt baserat på inställningarna för motsvarande ER-format och de aktuella data för juridiska personer som kommer att användas av ER-formatets datakällor.</span><span class="sxs-lookup"><span data-stu-id="60cae-114">Business users can then specify real rules beyond the ER framework by using the user interface (UI) that is automatically generated based on the settings of the corresponding ER format and the current legal entity data that will be accessed by the ER format's data sources.</span></span> <span data-ttu-id="60cae-115">Uppsättningen regler som anges för ett ER-format kan exporteras från den aktuella juridiska personen för instansen Dynamics 365 Finance (Finance).</span><span class="sxs-lookup"><span data-stu-id="60cae-115">The set of rules that is specified for an ER format can be exported from the current legal entity of the Dynamics 365 Finance (Finance) instance.</span></span> <span data-ttu-id="60cae-116">Den kan sedan importeras till en annan juridisk person, antingen för samma finansieringsinstans eller till en annan instans, som en uppsättning regler för samma ER-format.</span><span class="sxs-lookup"><span data-stu-id="60cae-116">It can then be imported into another legal entity of either the same Finance instance or a different instance as a set of rules for the same ER format.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="60cae-117">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="60cae-117">Prerequisites</span></span>

<span data-ttu-id="60cae-118">För att slutföra exemplen i detta ämne måste du ha åtkomst till instansen av Regulatory Configuration Services (RCS) som har etablerats för samma innehavare som Finance för en av följande roller:</span><span class="sxs-lookup"><span data-stu-id="60cae-118">To complete the examples in this topic, you must have access to the instance of Regulatory Configuration Services (RCS) that has been provisioned for the same tenant as Finance for one of the following roles:</span></span>

- <span data-ttu-id="60cae-119">Utvecklare för elektronisk rapportering</span><span class="sxs-lookup"><span data-stu-id="60cae-119">Electronic reporting developer</span></span>
- <span data-ttu-id="60cae-120">Konsult för funktionen för elektronisk rapportering</span><span class="sxs-lookup"><span data-stu-id="60cae-120">Electronic reporting functional consultant</span></span>
- <span data-ttu-id="60cae-121">Systemadministratör</span><span class="sxs-lookup"><span data-stu-id="60cae-121">System administrator</span></span>

<span data-ttu-id="60cae-122">Vi rekommenderar att du slutför stegen i avsnittet [supportparametersamtal för ER-datakällor av typen BERÄKNADE FÄLT](er-calculated-field-type.md).</span><span class="sxs-lookup"><span data-stu-id="60cae-122">We recommend that you complete the steps in the [Support parameterized calls of ER data sources of CALCULATED FIELD type](er-calculated-field-type.md) topic.</span></span> <span data-ttu-id="60cae-123">Om du redan har slutfört dessa steg kan du hoppa över stegen i avsnittet **importera ER-konfigurationer till RCS** nedan.</span><span class="sxs-lookup"><span data-stu-id="60cae-123">If you've already completed those steps, you can skip the steps in the **Import ER configurations into RCS** section that follows.</span></span>

## <a name="import-er-configurations-into-rcs"></a><span data-ttu-id="60cae-124">Importera ER-konfigurationer till RCS</span><span class="sxs-lookup"><span data-stu-id="60cae-124">Import ER configurations into RCS</span></span>

<span data-ttu-id="60cae-125">Från [Microsoft Download Center](https://go.microsoft.com/fwlink/?linkid=851448), hämta den komprimerade filen **Stödparameteranrop till ER-datakällor för typen BERÄKNAT FÄLT**.</span><span class="sxs-lookup"><span data-stu-id="60cae-125">From [Microsoft Download Center](https://go.microsoft.com/fwlink/?linkid=851448), download the **Support parameterized calls of ER data sources of CALCULATED FIELD type** zip file.</span></span> <span data-ttu-id="60cae-126">Denna zip-fil innehåller följande ER-konfigurationer som måste extraheras och lagras lokalt.</span><span class="sxs-lookup"><span data-stu-id="60cae-126">This zip file contains the following ER configurations that must be extracted and stored locally.</span></span>

| <span data-ttu-id="60cae-127">**Beskrivning av innehåll**</span><span class="sxs-lookup"><span data-stu-id="60cae-127">**Content description**</span></span>                        | <span data-ttu-id="60cae-128">**Filnamn**</span><span class="sxs-lookup"><span data-stu-id="60cae-128">**File name**</span></span>                                        |
|------------------------------------------------|------------------------------------------------------|
| <span data-ttu-id="60cae-129">Konfigurationsfil av exempel på **ER-datamodell**.</span><span class="sxs-lookup"><span data-stu-id="60cae-129">Sample **ER data model** configuration file</span></span>    | <span data-ttu-id="60cae-130">Modell för att lära dig parameteranrop.version.1.xml</span><span class="sxs-lookup"><span data-stu-id="60cae-130">Model to learn parameterized calls.version.1.xml</span></span>     |
| <span data-ttu-id="60cae-131">Konfigurationsfil av exempel på **ER-metadata**.</span><span class="sxs-lookup"><span data-stu-id="60cae-131">Sample **ER metadata** configuration file</span></span>      | <span data-ttu-id="60cae-132">Metadata för att lära dig parameteranrop.version.1.xml</span><span class="sxs-lookup"><span data-stu-id="60cae-132">Metadata to learn parameterized calls.version.1.xml</span></span>  |
| <span data-ttu-id="60cae-133">Konfigurationsfil av exempel på **ER-modellmappning**</span><span class="sxs-lookup"><span data-stu-id="60cae-133">Sample **ER model mapping** configuration file</span></span> | <span data-ttu-id="60cae-134">Mappning för att lära dig parameteranrop.version.1.1.xml</span><span class="sxs-lookup"><span data-stu-id="60cae-134">Mapping to learn parameterized calls.version.1.1.xml</span></span> |
| <span data-ttu-id="60cae-135">Konfiguration av exempel på **ER-format**.</span><span class="sxs-lookup"><span data-stu-id="60cae-135">Sample **ER format** configuration</span></span>             | <span data-ttu-id="60cae-136">Format för att lära dig parameteranrop.version.1.1.xml</span><span class="sxs-lookup"><span data-stu-id="60cae-136">Format to learn parameterized calls.version.1.1.xml</span></span>  |

<span data-ttu-id="60cae-137">Logga sedan in på RCS-instansen.</span><span class="sxs-lookup"><span data-stu-id="60cae-137">Next, sign in to your RCS instance.</span></span>

<span data-ttu-id="60cae-138">I det här exemplet ska du skapa en konfiguration för exempelföretaget, Litware.</span><span class="sxs-lookup"><span data-stu-id="60cae-138">In this example, you will create a configuration for the Litware, Inc sample company.</span></span> <span data-ttu-id="60cae-139">Innan du kan slutföra stegen i den här proceduren måste du först slutföra stegen i avsnittet [Skapa en konfigurationsleverantör och markera den som aktiv](tasks/er-configuration-provider-mark-it-active-2016-11.md) i RCS.</span><span class="sxs-lookup"><span data-stu-id="60cae-139">Before you can complete this procedure, you must complete the steps in the [Create a configuration provider and mark it as active](tasks/er-configuration-provider-mark-it-active-2016-11.md) topic in RCS.</span></span>

1.  <span data-ttu-id="60cae-140">Välj **elektronisk rapportering**på standardinstrumentpanelen.</span><span class="sxs-lookup"><span data-stu-id="60cae-140">On the default dashboard, select **Electronic reporting**.</span></span>
2.  <span data-ttu-id="60cae-141">Välj **rapporteringskonfigurationer**.</span><span class="sxs-lookup"><span data-stu-id="60cae-141">Select **Reporting configurations**.</span></span>
3.  <span data-ttu-id="60cae-142">Importera de ER-konfigurationer du laddade ned innan till RCS i följande ordning: datamodell, metadata, modellmappning och format.</span><span class="sxs-lookup"><span data-stu-id="60cae-142">Import the ER configurations that you downloaded earlier into RCS, in the following order: data model, metadata, model mapping, and format.</span></span> <span data-ttu-id="60cae-143">Följ dessa steg för varje ER-konfiguration:</span><span class="sxs-lookup"><span data-stu-id="60cae-143">For each ER configuration, follow these steps:</span></span>

    1.  <span data-ttu-id="60cae-144">Välj **kurs**</span><span class="sxs-lookup"><span data-stu-id="60cae-144">Select **Exchange**.</span></span>
    2.  <span data-ttu-id="60cae-145">Välj **Läs in från XML-fil**.</span><span class="sxs-lookup"><span data-stu-id="60cae-145">Select **Load from XML file**.</span></span>
    3.  <span data-ttu-id="60cae-146">Välj **bläddra** om du vill välja en fil för den nödvändiga ER-konfigurationen i XML-format.</span><span class="sxs-lookup"><span data-stu-id="60cae-146">Select **Browse** to select the file for the required ER configuration in XML format.</span></span>
    4.  <span data-ttu-id="60cae-147">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="60cae-147">Select **OK**.</span></span>

## <a name="review-the-er-solution-that-is-provided"></a><span data-ttu-id="60cae-148">Granska den medföljande ER-lösningen</span><span class="sxs-lookup"><span data-stu-id="60cae-148">Review the ER solution that is provided</span></span>

1.  <span data-ttu-id="60cae-149">I konfigurationsträdet expanderar du innehållet i objektet **modell för att lära dig parameteranrop**.</span><span class="sxs-lookup"><span data-stu-id="60cae-149">In the configuration tree, expand the contents of the **Model to learn parameterized calls** item.</span></span>
2.  <span data-ttu-id="60cae-150">Välj objektet **format för att lära sig mer parameteranrop**.</span><span class="sxs-lookup"><span data-stu-id="60cae-150">Select the **Format to learn parameterized calls** item.</span></span>
3.  <span data-ttu-id="60cae-151">Välj **Designer**.</span><span class="sxs-lookup"><span data-stu-id="60cae-151">Select **Designer**.</span></span>
4.  <span data-ttu-id="60cae-152">Växla mellan **expandering/komprimering**.</span><span class="sxs-lookup"><span data-stu-id="60cae-152">Select **Expand/Collapse**.</span></span>

    <span data-ttu-id="60cae-153">ER-formatet **Formatet för att lära sig parameteranrop** är utformat för att generera en momsrapport i XML-format som visar flera momsnivåer (vanlig, reducerad och ingen).</span><span class="sxs-lookup"><span data-stu-id="60cae-153">The **Format to learn parameterized calls** ER format is designed to generate a tax statement in XML format that presents several levels of taxation (regular, reduced, and none).</span></span> <span data-ttu-id="60cae-154">Varje nivå har ett annat antal detaljer.</span><span class="sxs-lookup"><span data-stu-id="60cae-154">Each level has a different number of details.</span></span>

    ![ER-åtgärdsdesignersida](./media/RCS-AppSpecParms-ReviewFormat.PNG)

5.  <span data-ttu-id="60cae-156">På fliken **mappning** expanderar du objekten **modell**, **data** och **sammanfattnings**.</span><span class="sxs-lookup"><span data-stu-id="60cae-156">On the **Mapping** tab, expand the **Model**, **Data**, and **Summary** items.</span></span>

    <span data-ttu-id="60cae-157">Datakällan **Model.Data.Summar** returnerar listan över momstransaktioner.</span><span class="sxs-lookup"><span data-stu-id="60cae-157">The **Model.Data.Summary** data source returns the list of tax transactions.</span></span> <span data-ttu-id="60cae-158">Transaktionernas sammanfattas per momskod.</span><span class="sxs-lookup"><span data-stu-id="60cae-158">These transactions are summarized by tax code.</span></span> <span data-ttu-id="60cae-159">För den här datakällan har det beräknade fältet **Model.Data.Summary.Level** konfigurerats att returnera koden för momsnivån för varje summerad post.</span><span class="sxs-lookup"><span data-stu-id="60cae-159">For this data source, the **Model.Data.Summary.Level** calculated field has been configured to return the code for the taxation level of each summarized record.</span></span> <span data-ttu-id="60cae-160">För alla momskoder som kan hämtas från datakällan **Model.Data.Summary** vid körning returnerar det beräknade fältet beskattningsnivåskod (**normal**, **reducerad**, **ingen** eller **annan**) som textvärde.</span><span class="sxs-lookup"><span data-stu-id="60cae-160">For any tax code that can be retrieved from the **Model.Data.Summary** data source at runtime, the calculated field returns the taxation level code (**Regular**, **Reduced**, **None**, or **Other**) as a text value.</span></span> <span data-ttu-id="60cae-161">Det beräknade fältet **Model.Data.Summary.Level** används för att filtrera poster av datakällan **Model.Data.Summary** och ange de filtrerade data i varje XML-element representerar en beskattningsnivå genom att använda fältet **Model.Data2.Level1**, **Model.Data2.Level2** och **Model.Data2.Level3**.</span><span class="sxs-lookup"><span data-stu-id="60cae-161">The **Model.Data.Summary.Level** calculated field is used to filter records of the **Model.Data.Summary** data source and enter the filtered data in each XML element that represents a taxation level by using the **Model.Data2.Level1**, **Model.Data2.Level2**, and **Model.Data2.Level3** fields.</span></span>

    ![ER-åtgärdsdesignersida](./media/RCS-AppSpecParms-ReviewFormat-Data2Fld.PNG)

    <span data-ttu-id="60cae-163">Det beräknade fältet **Model.Data.Summary.Level** har konfigurerats så att det innehåller ett ER-uttryck.</span><span class="sxs-lookup"><span data-stu-id="60cae-163">The **Model.Data.Summary.Level** calculated field has been configured so that it contains an ER expression.</span></span> <span data-ttu-id="60cae-164">Observera att momskoder (**VAT19**, **InVAT19**, **VAT7**, **InVAT7**, **THIRD** och **InVAT0**) är hårdkodad i den här konfigurationen.</span><span class="sxs-lookup"><span data-stu-id="60cae-164">Note that tax codes (**VAT19**, **InVAT19**, **VAT7**, **InVAT7**, **THIRD**, and **InVAT0**) are hardcoded into this configuration.</span></span> <span data-ttu-id="60cae-165">Därför beror detta ER-format på den juridiska person där dessa momskoder har konfigurerats.</span><span class="sxs-lookup"><span data-stu-id="60cae-165">Therefore, this ER format is dependent on the legal entity where these tax codes were configured.</span></span>

    ![ER-åtgärdsdesignersida](./media/RCS-AppSpecParms-ReviewFormat-LevelFld.PNG)

    <span data-ttu-id="60cae-167">Om du vill stödja en annan uppsättning momskoder för varje juridisk person måste du göra följande:</span><span class="sxs-lookup"><span data-stu-id="60cae-167">To support a different set of tax codes for each legal entity, you must follow these steps:</span></span>

    - <span data-ttu-id="60cae-168">Skapa en härledd version av ER-formatet för varje juridisk person.</span><span class="sxs-lookup"><span data-stu-id="60cae-168">Create a derived version of the ER format for each legal entity.</span></span>
    - <span data-ttu-id="60cae-169">Uppdatera momskoderna i beräknade fältet **Model.Data.Summary.Level** baserat på inställningen för juridisk person.</span><span class="sxs-lookup"><span data-stu-id="60cae-169">Update the tax codes in the **Model.Data.Summary.Level** calculated field, based on the legal entity setting.</span></span>

6.  <span data-ttu-id="60cae-170">Stäng sidan **Formatdesigner**.</span><span class="sxs-lookup"><span data-stu-id="60cae-170">Close the **Format designer** page.</span></span>

## <a name="create-a-derived-format"></a><span data-ttu-id="60cae-171">Skapa ett härlett format</span><span class="sxs-lookup"><span data-stu-id="60cae-171">Create a derived format</span></span>

<span data-ttu-id="60cae-172">Därefter ska du använda funktionen ER-programspecifika parametrar för att stödja en annan uppsättning momskoder för varje juridisk person i ett enda ER-format.</span><span class="sxs-lookup"><span data-stu-id="60cae-172">Next, you will use the ER application-specific parameters feature to support a different set of tax codes for each legal entity in a single ER format.</span></span>

1.  <span data-ttu-id="60cae-173">I konfigurationsträdet expanderar du innehållet i objektet **modell för att lära dig parameteranrop**.</span><span class="sxs-lookup"><span data-stu-id="60cae-173">In the configuration tree, expand the contents of the **Model to learn parameterized calls** item.</span></span>
2.  <span data-ttu-id="60cae-174">Välj objektet **format för att lära sig mer parameteranrop**.</span><span class="sxs-lookup"><span data-stu-id="60cae-174">Select the **Format to learn parameterized calls** item.</span></span>
3.  <span data-ttu-id="60cae-175">Välj **Skapa konfiguration**.</span><span class="sxs-lookup"><span data-stu-id="60cae-175">Select **Create configuration**.</span></span>
4.  <span data-ttu-id="60cae-176">Välj alternativet **Härled från namn: format om du vill lära dig parameteranrop, Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="60cae-176">Select the **Derive from Name: Format to learn parameterized calls, Microsoft** option.</span></span>
5.  <span data-ttu-id="60cae-177">I fältet **namn** anger du **format för att lära dig hur du slår upp IE-data**.</span><span class="sxs-lookup"><span data-stu-id="60cae-177">In the **Name** field, enter **Format to learn how to lookup LE data**.</span></span>
6.  <span data-ttu-id="60cae-178">Välj **Skapa konfiguration**.</span><span class="sxs-lookup"><span data-stu-id="60cae-178">Select **Create configuration**.</span></span>

## <a name="configure-a-derived-format"></a><span data-ttu-id="60cae-179">Konfigurera ett härlett format</span><span class="sxs-lookup"><span data-stu-id="60cae-179">Configure a derived format</span></span>

### <a name="add-a-format-enumeration"></a><span data-ttu-id="60cae-180">Lägg till formatuppräkning</span><span class="sxs-lookup"><span data-stu-id="60cae-180">Add a format enumeration</span></span>

<span data-ttu-id="60cae-181">Nu ska du lägga till en ny uppräkning för ER-format.</span><span class="sxs-lookup"><span data-stu-id="60cae-181">Next, you will add a new ER format enumeration.</span></span> <span data-ttu-id="60cae-182">Värdena i detta formatuppräkningsformulär visas för företagsanvändare, som anger juridiska personer – beroende uppsättningar med momskoder för de olika skattenivåerna som används i ER-format.</span><span class="sxs-lookup"><span data-stu-id="60cae-182">The values of this format enumeration will be presented to business users, who will specify legal entity–dependent sets of tax codes for the various taxation levels that are used in the ER format.</span></span>

1.  <span data-ttu-id="60cae-183">Välj **Designer**.</span><span class="sxs-lookup"><span data-stu-id="60cae-183">Select **Designer**.</span></span>
2.  <span data-ttu-id="60cae-184">Välj **formatuppräkningar**.</span><span class="sxs-lookup"><span data-stu-id="60cae-184">Select **Format enumerations**.</span></span>
3.  <span data-ttu-id="60cae-185">Markera **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="60cae-185">Select **Add**.</span></span>
4.  <span data-ttu-id="60cae-186">I fältet **Namn** anger du **Lista över beskattningsnivåer**.</span><span class="sxs-lookup"><span data-stu-id="60cae-186">In the **Name** field, enter **List of taxation levels**.</span></span>
5.  <span data-ttu-id="60cae-187">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="60cae-187">Select **Save**.</span></span>
6.  <span data-ttu-id="60cae-188">På fliken **Format uppräkningsvärden** välj **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="60cae-188">On the **Format enumeration values** tab, select **Add**.</span></span>
7.  <span data-ttu-id="60cae-189">I fältet **Namn** anger du **Regelbunden beskattning**.</span><span class="sxs-lookup"><span data-stu-id="60cae-189">In the **Name** field, enter **Regular taxation**.</span></span>
8.  <span data-ttu-id="60cae-190">Välj **Lägg till** igen.</span><span class="sxs-lookup"><span data-stu-id="60cae-190">Select **Add** again.</span></span>
9.  <span data-ttu-id="60cae-191">I fältet **Namn** anger du **Reducerad beskattning**.</span><span class="sxs-lookup"><span data-stu-id="60cae-191">In the **Name** field, enter **Reduced taxation**.</span></span>
10. <span data-ttu-id="60cae-192">Välj **Lägg till** igen.</span><span class="sxs-lookup"><span data-stu-id="60cae-192">Select **Add** again.</span></span>
11. <span data-ttu-id="60cae-193">I fältet **Namn** anger du **Ingen beskattning**.</span><span class="sxs-lookup"><span data-stu-id="60cae-193">In the **Name** field, enter **No taxation**.</span></span>
12. <span data-ttu-id="60cae-194">Välj **Lägg till** igen.</span><span class="sxs-lookup"><span data-stu-id="60cae-194">Select **Add** again.</span></span>
13. <span data-ttu-id="60cae-195">Skriv **Utdata** i fältet **Andra**.</span><span class="sxs-lookup"><span data-stu-id="60cae-195">In the **Name** field, enter **Other**.</span></span>

    ![ER-åtgärdsdesignersida](./media/RCS-AppSpecParms-ConfigureFormat-Enum.PNG)

    <span data-ttu-id="60cae-197">Eftersom olika språk används i affärsanvändarna för att ange uppsättningar av momskoder som är beroende av den juridiska personen rekommenderar vi att du översätter värdena för denna uppräkning till de språk som är konfigurerade som prioriterade språk för dessa användare i Finance.</span><span class="sxs-lookup"><span data-stu-id="60cae-197">Because the business users might use different languages to specify legal entity–dependent sets of tax codes, we recommend that you translate the values of this enumeration into the languages that are configured as the preferred languages for those users in Finance.</span></span>

14. <span data-ttu-id="60cae-198">Välj posten **ingen avgift**.</span><span class="sxs-lookup"><span data-stu-id="60cae-198">Select the **No taxation** record.</span></span>
15. <span data-ttu-id="60cae-199">Klicka i fältet **etikett**.</span><span class="sxs-lookup"><span data-stu-id="60cae-199">Click in the **Label** field.</span></span>
16. <span data-ttu-id="60cae-200">Välj **översätt**.</span><span class="sxs-lookup"><span data-stu-id="60cae-200">Select **Translate**.</span></span>
17. <span data-ttu-id="60cae-201">I fönstret **Textöversättning** i fältet **etikett-ID**, ange **LBL_LEVELENUM_NO**.</span><span class="sxs-lookup"><span data-stu-id="60cae-201">In the **Text translation** pane, in the **Label Id** field, enter **LBL_LEVELENUM_NO**.</span></span>
18. <span data-ttu-id="60cae-202">I fältet **text på standardspråk** anger du **ingen beskattning**.</span><span class="sxs-lookup"><span data-stu-id="60cae-202">In the **Text in default language** field, enter **No taxation**.</span></span>
19. <span data-ttu-id="60cae-203">I fältet **Språk** välj **DE**.</span><span class="sxs-lookup"><span data-stu-id="60cae-203">In the **Language** field, select **DE**.</span></span>
20. <span data-ttu-id="60cae-204">I fältet **Översatt text** anger du **keine Besteuerung**.</span><span class="sxs-lookup"><span data-stu-id="60cae-204">In the **Translated text** field, enter **keine Besteuerung**.</span></span>
21. <span data-ttu-id="60cae-205">Välj **översätt**.</span><span class="sxs-lookup"><span data-stu-id="60cae-205">Select **Translate**.</span></span>

    ![ER-åtgärdsdesignersida](./media/RCS-AppSpecParms-ConfigureFormat-EnumTranslate.PNG)

22. <span data-ttu-id="60cae-207">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="60cae-207">Select **Save**.</span></span>
23. <span data-ttu-id="60cae-208">Stäng sidan **formatuppräkningar**.</span><span class="sxs-lookup"><span data-stu-id="60cae-208">Close the **Format enumerations** page.</span></span>

### <a name="add-a-new-lookup-data-source"></a><span data-ttu-id="60cae-209">Lägg till en ny datakälla för sökning</span><span class="sxs-lookup"><span data-stu-id="60cae-209">Add a new lookup data source</span></span>

<span data-ttu-id="60cae-210">Därefter ska du lägga till en ny datakälla som anger hur affärsanvändare ska ange regler som är beroende av den juridiska personen för att känna igen den korrekta momsnivån för varje summerad transaktionspost.</span><span class="sxs-lookup"><span data-stu-id="60cae-210">Next, you will add a new data source to specify how business users will specify legal entity–dependent rules to recognize the correct taxation level for each summarized transaction record.</span></span>

1.  <span data-ttu-id="60cae-211">Välj **ta bort** på fliken **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="60cae-211">On the **Mapping** tab, select **Add**.</span></span>
2.  <span data-ttu-id="60cae-212">Välj **formatuppräkning\uppslag**.</span><span class="sxs-lookup"><span data-stu-id="60cae-212">Select **Format enumeration\Lookup**.</span></span>

    <span data-ttu-id="60cae-213">Du har just identifierat att varje regel som affärsanvändare anger för att beräkna skattenivå returnerar ett värde i ett ER-format uppräkningsresultat.</span><span class="sxs-lookup"><span data-stu-id="60cae-213">You just identified that each rule that business users specify for taxation level recognition will return a value of an ER format enumeration.</span></span> <span data-ttu-id="60cae-214">Observera att datakällatypen **uppslag** kan nås under **datamodellen** och **Dynamics 365 for Operations**-blocken förutom blocket **formatuppräkning**.</span><span class="sxs-lookup"><span data-stu-id="60cae-214">Notice that the **Lookup** data source type can be accessed under the **Data model** and **Dynamics 365 for Operations** blocks in addition to the **Format enumeration** block.</span></span> <span data-ttu-id="60cae-215">Därför kan ER-datamodellens uppräkning och programuppräkningar användas för att ange vilken typ av värden som returneras för datakällor av den typen.</span><span class="sxs-lookup"><span data-stu-id="60cae-215">Therefore, ER data model enumerations and application enumerations can be used to specify the type of values that is are returned for data sources of that type.</span></span>
    
3.  <span data-ttu-id="60cae-216">Skriv **väljare** i fältet **Namn**.</span><span class="sxs-lookup"><span data-stu-id="60cae-216">In the **Name** field, enter **Selector**.</span></span>
4.  <span data-ttu-id="60cae-217">I fältet **Formatuppräkning** anger du **Lista över beskattningsnivåer**.</span><span class="sxs-lookup"><span data-stu-id="60cae-217">In the **Format enumeration** field, select **List of taxation levels**.</span></span>

    <span data-ttu-id="60cae-218">Du har precis angett att för en affärsanvändare måste välja ett av värdena för varje regel som anges i den här datakällan i formatuppräkningen **Lista över beskattningsnivåer** som ett returnerat värde för varje regel som anges i denna datakälla.</span><span class="sxs-lookup"><span data-stu-id="60cae-218">You just specified that, for each rule that is specified in this data source, a business user must select one of the values of the **List of taxation levels** format enumeration as a returned value.</span></span>
    
5.  <span data-ttu-id="60cae-219">Välj **redigera uppslag**.</span><span class="sxs-lookup"><span data-stu-id="60cae-219">Select **Edit lookup**.</span></span>
6.  <span data-ttu-id="60cae-220">Välj **kolumner**.</span><span class="sxs-lookup"><span data-stu-id="60cae-220">Select **Columns**.</span></span>
7.  <span data-ttu-id="60cae-221">Expandera objektet **Modell**.</span><span class="sxs-lookup"><span data-stu-id="60cae-221">Expand the **Model** item.</span></span>
8.  <span data-ttu-id="60cae-222">Expandera objektet **Data**.</span><span class="sxs-lookup"><span data-stu-id="60cae-222">Expand the **Data** item.</span></span>
9.  <span data-ttu-id="60cae-223">Expandera objektet **Moms**.</span><span class="sxs-lookup"><span data-stu-id="60cae-223">Expand the **Tax** item.</span></span>
10. <span data-ttu-id="60cae-224">Välj objektet **Model.Data.Tax.Code**.</span><span class="sxs-lookup"><span data-stu-id="60cae-224">Select the **Model.Data.Tax.Code** item.</span></span>
11. <span data-ttu-id="60cae-225">Välj knappen **Lägg till** (högerpilen).</span><span class="sxs-lookup"><span data-stu-id="60cae-225">Select the **Add** button (the right arrow).</span></span>

    ![ER-åtgärdsdesignersida](./media/RCS-AppSpecParms-ConfigureFormat-Lookup1.PNG)

    <span data-ttu-id="60cae-227">Du har precis angett att för varje regel som anges i denna datakälla för erkännande av beskattningsnivå måste en företagsanvändare välja en av skattekoderna som villkor.</span><span class="sxs-lookup"><span data-stu-id="60cae-227">You just specified that, for each rule that is specified in this data source for taxation level recognition, a business user must select one of the tax codes as a condition.</span></span> <span data-ttu-id="60cae-228">Listan över momskoder som affärsanvändaren kan välja returneras av datakällan **Model.Data.Tax**.</span><span class="sxs-lookup"><span data-stu-id="60cae-228">The list of tax codes that the business user can select will be returned by the **Model.Data.Tax** data source.</span></span> <span data-ttu-id="60cae-229">Eftersom datakällan innehåller fältet **namn** visas namnet på momskoden för varje momskodvärde i sökningen som visas för affärsanvändaren.</span><span class="sxs-lookup"><span data-stu-id="60cae-229">Because this data source contains the **Name** field, the name of the tax code will be shown for each tax code value in the lookup that is presented to the business user.</span></span>
    
12. <span data-ttu-id="60cae-230">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="60cae-230">Select **OK**.</span></span>

    ![ER-åtgärdsdesignersida](./media/RCS-AppSpecParms-ConfigureFormat-Lookup2.PNG)

    <span data-ttu-id="60cae-232">Affärsanvändare kan lägga till flera regler som poster i den här datakällan.</span><span class="sxs-lookup"><span data-stu-id="60cae-232">Business users can add multiple rules as records of this data source.</span></span> <span data-ttu-id="60cae-233">Varje post kommer att numreras med en radkod.</span><span class="sxs-lookup"><span data-stu-id="60cae-233">Each record will be numbered by a line code.</span></span> <span data-ttu-id="60cae-234">Regler kommer att utvärderas i stigande ordning på radnumret.</span><span class="sxs-lookup"><span data-stu-id="60cae-234">Rules will be evaluated in order of increasing line number.</span></span>

    <span data-ttu-id="60cae-235">Eftersom du har valt fältet **Momskod** som ett villkor för regler i denna uppslagningsdatakälla och därför anges **Momskod** anges som fält för datatypen **Sträng** utvärderas varje regel vid körning genom att jämföra momskoden som skickas till datakällan med momskoden som har definierats i den här posten i datakällan.</span><span class="sxs-lookup"><span data-stu-id="60cae-235">Because you selected the **Tax code** field as a condition for rules in this lookup data source, and because **Tax code** is set up as a field of the **String** data type, each rule will be evaluated at runtime by comparing the tax code that is passed to the data source with the tax code that is defined in this record of the data source.</span></span>

    <span data-ttu-id="60cae-236">När en regel som uppfyller det konfigurerade villkoret hittas returnerar denna datakälla uppslagsvärden för regeln som definieras i fältet **uppslagsresultat**.</span><span class="sxs-lookup"><span data-stu-id="60cae-236">When a rule that satisfies the configured condition is found, this data source returns the lookup value of the rule that is defined in the **Lookup result** field.</span></span> <span data-ttu-id="60cae-237">Om ingen regel hittas genereras ett undantag för att meddela användaren att den aktuella datakällan inte kan returnera ett korrekt värde.</span><span class="sxs-lookup"><span data-stu-id="60cae-237">If no rule is found, an exception is thrown to notify the user that the current data source can't return a correct value.</span></span>

13. <span data-ttu-id="60cae-238">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="60cae-238">Select **Save**.</span></span>
14. <span data-ttu-id="60cae-239">Stäng sidan **Sökningsdesigner**.</span><span class="sxs-lookup"><span data-stu-id="60cae-239">Close the **Lookup designer** page.</span></span>
15. <span data-ttu-id="60cae-240">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="60cae-240">Select **OK**.</span></span>

    <span data-ttu-id="60cae-241">Lägg märke till att du har lagt till en ny datakälla som returnerar momsnivån som värdet i **listan över beskattningsnivåer** formatberäkning för eventuella momskoder som skickas till datakällan som argument till parametern **Kod** för datatypen **sträng**.</span><span class="sxs-lookup"><span data-stu-id="60cae-241">Notice that you added a new data source that will return the taxation level as the value of the **List of taxation levels** format enumeration for any tax code that is passed to the data source as the argument of the **Code** parameter of the **String** data type.</span></span>
    
    ![ER-åtgärdsdesignersida](./media/RCS-AppSpecParms-ConfigureFormat-SelectorFld.PNG)

    <span data-ttu-id="60cae-243">Observera att utvärderingen av konfigurerade regler beror på datatypen för de fält som har valts för att definiera villkoren för dessa regler.</span><span class="sxs-lookup"><span data-stu-id="60cae-243">Note that the evaluation of configured rules depends on the data type of the fields that have been selected to define conditions of those rules.</span></span> <span data-ttu-id="60cae-244">När du väljer ett fält som är konfigurerat som ett fält av datatypen **numerisk** eller **datum**, skiljer sig villkoren från kriterierna som beskrevs tidigare för datatypen **sträng**.</span><span class="sxs-lookup"><span data-stu-id="60cae-244">When you select a field that is configured as a field of either the **Numeric** or **Date** data type, the criteria will differ from the criteria that were described earlier for the **String** data type.</span></span> <span data-ttu-id="60cae-245">För fälten **numerisk** och **datum** måste regeln anges som ett värdeintervall.</span><span class="sxs-lookup"><span data-stu-id="60cae-245">For **Numeric** and **Date** fields, the rule must be specified as a range of values.</span></span> <span data-ttu-id="60cae-246">Regelns villkor kommer då att betraktas som uppfyllt när ett värde som skickas till datakällan finns i det konfigurerade intervallet.</span><span class="sxs-lookup"><span data-stu-id="60cae-246">The condition of the rule will then be considered satisfied when a value that is passed to the data source is in the configured range.</span></span>
    
    <span data-ttu-id="60cae-247">Följande illustration visar ett exempel på den här typen av inställning.</span><span class="sxs-lookup"><span data-stu-id="60cae-247">The following illustration shows an example of this type of setup.</span></span> <span data-ttu-id="60cae-248">Förutom fältet **Model.Data.Tax.Code** för datatypen **Sträng** används fältet **Model.Tax.Summary.Base** för datatypen **Real** används för att ange villkor för en datakälla för sökning.</span><span class="sxs-lookup"><span data-stu-id="60cae-248">In addition to the **Model.Data.Tax.Code** field of the **String** data type, the **Model.Tax.Summary.Base** field of the **Real** data type is used to specify conditions for a lookup data source.</span></span>
    
    ![ER-åtgärdsdesignersida](./media/RCS-AppSpecParms-ConfigureFormat-SelectorFld2.PNG)

    <span data-ttu-id="60cae-250">Eftersom fälten **Model.Data.Tax.Code** och **Model.Tax.Summary.Base** markeras för den här datakälla för sökning konfigureras varje regel för den här datakällan på följande sätt:</span><span class="sxs-lookup"><span data-stu-id="60cae-250">Because the **Model.Data.Tax.Code** and **Model.Tax.Summary.Base** fields are selected for this lookup data source, each rule of this data source will be configured in the following way:</span></span>
    
    -   <span data-ttu-id="60cae-251">I listan som visas måste värdet i formatet **Lista över beskattningsnivåer** väljs som ett returnerat värde.</span><span class="sxs-lookup"><span data-stu-id="60cae-251">In the list that is presented, the value of the **List of taxation levels** format enumeration must be selected as a returned value.</span></span>
    -   <span data-ttu-id="60cae-252">Momskoden måste anges som villkor för regeln.</span><span class="sxs-lookup"><span data-stu-id="60cae-252">The tax code must be entered as a condition of this rule.</span></span> <span data-ttu-id="60cae-253">Endast momskoder som tillhandahålls av datakällan **Model.Data.Tax** är tillämpliga.</span><span class="sxs-lookup"><span data-stu-id="60cae-253">Only tax codes that are provided by the **Model.Data.Tax** data source are applicable.</span></span>
    -   <span data-ttu-id="60cae-254">Lägsta och högsta värde för basbeloppet måste anges som villkor för regeln.</span><span class="sxs-lookup"><span data-stu-id="60cae-254">Minimum and maximum values of the tax base amount must be entered as conditions of this rule.</span></span>

    <span data-ttu-id="60cae-255">Så här kommer varje regel för den här datakällan att utvärderas under körning:</span><span class="sxs-lookup"><span data-stu-id="60cae-255">Here is how each rule of this data source will be evaluated at runtime:</span></span>
    -   <span data-ttu-id="60cae-256">Är koden för datatypen **sträng** skickades till den här datakällan lika med momskoden för en regel?</span><span class="sxs-lookup"><span data-stu-id="60cae-256">Does the code of the **String** data type that was passed to this data source equal the tax code of a rule?</span></span>
    -   <span data-ttu-id="60cae-257">Faller värdet på datatypen **verklig** som skickades till den här datakällan mellan specifika lägsta och högsta värde?</span><span class="sxs-lookup"><span data-stu-id="60cae-257">Does the value of the **Real** data type that was passed to this data source fall between specific minimum and maximum values?</span></span>

    <span data-ttu-id="60cae-258">En regel kommer att betraktas som tillämplig när båda villkoren uppfylls.</span><span class="sxs-lookup"><span data-stu-id="60cae-258">A rule will be considered applicable when both conditions are satisfied.</span></span>

### <a name="translate-the-label-of-the-lookup-data-source-that-was-added"></a><span data-ttu-id="60cae-259">Översätt etiketten för datakälla för sökning som lades till</span><span class="sxs-lookup"><span data-stu-id="60cae-259">Translate the label of the lookup data source that was added</span></span>

<span data-ttu-id="60cae-260">Eftersom olika språk används i affärsanvändarna för att ange uppsättningar av momskoder som är beroende av den juridiska personen rekommenderar vi att du översätter etiketten för alla datakällor för sökning som du lägger till, så att den presenteras på varje användares önskade språk på motsvarande sida.</span><span class="sxs-lookup"><span data-stu-id="60cae-260">Because business users might use different languages to specify legal entity–dependent sets of tax codes, we recommend that you translate the label of any lookup data source that you add, so that it's presented in each user's preferred language on the corresponding page.</span></span>

1.  <span data-ttu-id="60cae-261">Markera datakällan **Model.Data.Selector**.</span><span class="sxs-lookup"><span data-stu-id="60cae-261">Select the **Model.Data.Selector** data source.</span></span>
2.  <span data-ttu-id="60cae-262">Välj **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="60cae-262">Select **Edit**.</span></span>
3.  <span data-ttu-id="60cae-263">Klicka i fältet **etikett**.</span><span class="sxs-lookup"><span data-stu-id="60cae-263">Click in the **Label** field.</span></span>
4.  <span data-ttu-id="60cae-264">Välj **översätt**.</span><span class="sxs-lookup"><span data-stu-id="60cae-264">Select **Translate**.</span></span>
5.  <span data-ttu-id="60cae-265">I fönstret **Textöversättning** i fältet **etikett-ID**, ange **LBL_SELECTOR_DS**.</span><span class="sxs-lookup"><span data-stu-id="60cae-265">In the **Text translation** pane, in the **Label Id** field, enter **LBL_SELECTOR_DS**.</span></span>
6.  <span data-ttu-id="60cae-266">I fältet **text i standardfältet** anger du **Välj momsnivå per momskod**.</span><span class="sxs-lookup"><span data-stu-id="60cae-266">In the **Text in default language** field, enter **Select tax level by tax code**.</span></span>
7.  <span data-ttu-id="60cae-267">I fältet **Språk** välj **DE**.</span><span class="sxs-lookup"><span data-stu-id="60cae-267">In the **Language** field, select **DE**.</span></span>
8.  <span data-ttu-id="60cae-268">I fältet **Översätt text**, ange **Steuerebene für Steuerkennzeichen auswählen**.</span><span class="sxs-lookup"><span data-stu-id="60cae-268">In the **Translated text** field, enter **Steuerebene für Steuerkennzeichen auswählen**.</span></span>
9.  <span data-ttu-id="60cae-269">Välj **översätt**.</span><span class="sxs-lookup"><span data-stu-id="60cae-269">Select **Translate**.</span></span>
10. <span data-ttu-id="60cae-270">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="60cae-270">Select **OK**.</span></span>

    ![ER-åtgärdsdesignersida](./media/RCS-AppSpecParms-ConfigureFormat-SelectorFldTranslate.PNG)

### <a name="add-a-new-field-to-consume-the-configured-lookup"></a><span data-ttu-id="60cae-272">Lägg till ett nytt fält för att förbruka det konfigurerade uppslaget</span><span class="sxs-lookup"><span data-stu-id="60cae-272">Add a new field to consume the configured lookup</span></span>

1.  <span data-ttu-id="60cae-273">Expandera objektet **Model.Data**.</span><span class="sxs-lookup"><span data-stu-id="60cae-273">Expand the **Model.Data** item.</span></span>
2.  <span data-ttu-id="60cae-274">Välj objektet **Model.Data.Summary**.</span><span class="sxs-lookup"><span data-stu-id="60cae-274">Select the **Model.Data.Summary** item.</span></span>
3.  <span data-ttu-id="60cae-275">Markera **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="60cae-275">Select **Add**.</span></span>
4.  <span data-ttu-id="60cae-276">Välj **Fältet funktioner/beräknat fält**.</span><span class="sxs-lookup"><span data-stu-id="60cae-276">Select **Functions/Calculated field**.</span></span>
5.  <span data-ttu-id="60cae-277">I fältet **Namn** anger du **LevelByLookup**.</span><span class="sxs-lookup"><span data-stu-id="60cae-277">In the **Name** field, enter **LevelByLookup**.</span></span>
6.  <span data-ttu-id="60cae-278">Välj **Redigera recept**.</span><span class="sxs-lookup"><span data-stu-id="60cae-278">Select **Edit formula**.</span></span>
7.  <span data-ttu-id="60cae-279">I **fältet formel**, ange **Model.Selector(Model.Data.Summary.Code)**.</span><span class="sxs-lookup"><span data-stu-id="60cae-279">In the **Formula field**, enter **Model.Selector(Model.Data.Summary.Code)**.</span></span>
8.  <span data-ttu-id="60cae-280">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="60cae-280">Select **Save**.</span></span>

    ![ER-åtgärdsdesignersida](./media/RCS-AppSpecParms-ConfigureFormat-AddLevelByLookupFld.PNG)

9.  <span data-ttu-id="60cae-282">Stäng sidan **receptredigering**.</span><span class="sxs-lookup"><span data-stu-id="60cae-282">Close the **Formula editor** page.</span></span>
10. <span data-ttu-id="60cae-283">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="60cae-283">Select **OK**.</span></span>

    ![ER-åtgärdsdesignersida](./media/RCS-AppSpecParms-ConfigureFormat-AddLevelByLookupFld2.PNG)

    <span data-ttu-id="60cae-285">Observera att det beräknade fältet **LevelByLookup** som du har lagt till kommer att återge beskattningsnivån som värdet på formatuppräkningen **Lista över beskattningsnivåer** för varje sammanfattad skattetransaktionspost.</span><span class="sxs-lookup"><span data-stu-id="60cae-285">Notice that the **LevelByLookup** calculated field that you added will return the taxation level as the value of the **List of taxation levels** format enumeration for each summarized tax transactions record.</span></span> <span data-ttu-id="60cae-286">Momskoden för posten skickas till datakälla för sökning **Model.Selector** och uppsättningen med regler för den här datakällan används för att välja korrekt beskattningsnivå.</span><span class="sxs-lookup"><span data-stu-id="60cae-286">The tax code of the record will be passed to the **Model.Selector** lookup data source, and the set of rules for this data source will be used to select the correct taxation level.</span></span>

### <a name="add-a-new-format-enumeration-based-data-source"></a><span data-ttu-id="60cae-287">Lägg till ett nytt format med beräkningsbaserad datakälla.</span><span class="sxs-lookup"><span data-stu-id="60cae-287">Add a new format enumeration-based data source</span></span>

<span data-ttu-id="60cae-288">Därefter ska du lägga till en ny datakälla som refererar till uppräkningen av format som du lade till tidigare.</span><span class="sxs-lookup"><span data-stu-id="60cae-288">Next, you will add a new data source that refers to the format enumeration that you added earlier.</span></span> <span data-ttu-id="60cae-289">Värden för denna datakälla kommer att användas i ett formatuttryck för ER-formatering senare.</span><span class="sxs-lookup"><span data-stu-id="60cae-289">Values of this data source will be used in an ER format expression later.</span></span>

1.  <span data-ttu-id="60cae-290">Välj **Lägg till rot**.</span><span class="sxs-lookup"><span data-stu-id="60cae-290">Select **Add root**.</span></span>
2.  <span data-ttu-id="60cae-291">Välj **formatuppräkningar\uppräkningar**.</span><span class="sxs-lookup"><span data-stu-id="60cae-291">Select **Format enumerations\Enumeration**.</span></span>
3.  <span data-ttu-id="60cae-292">I fältet **Namn** anger du **TaxationLevel**.</span><span class="sxs-lookup"><span data-stu-id="60cae-292">In the **Name** field, enter **TaxationLevel**.</span></span>
4.  <span data-ttu-id="60cae-293">I fältet **Formatuppräkning** anger du **Lista över beskattningsnivåer**.</span><span class="sxs-lookup"><span data-stu-id="60cae-293">In the **Format enumeration** field, select **List of taxation levels**.</span></span>
5.  <span data-ttu-id="60cae-294">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="60cae-294">Select **Save**.</span></span>

### <a name="modify-an-existing-field-to-start-to-use-the-lookup"></a><span data-ttu-id="60cae-295">Ändra ett befintligt fält till start om du vill använda sökningen</span><span class="sxs-lookup"><span data-stu-id="60cae-295">Modify an existing field to start to use the lookup</span></span>

<span data-ttu-id="60cae-296">Därefter ska du ändra det befintliga beräknade fältet så att det använder den konfigurerade datakälla för sökning för att returnera rätt momsnivåvärde, beroende på momskoden.</span><span class="sxs-lookup"><span data-stu-id="60cae-296">Next, you will modify the existing calculated field so that it uses the configured lookup data source to return the correct taxation level value, depending on the tax code.</span></span>

1.  <span data-ttu-id="60cae-297">Välj objektet **Model.Data.Summary.Level**.</span><span class="sxs-lookup"><span data-stu-id="60cae-297">Select the **Model.Data.Summary.Level** item.</span></span>
2.  <span data-ttu-id="60cae-298">Välj **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="60cae-298">Select **Edit**.</span></span>
3.  <span data-ttu-id="60cae-299">Välj **Redigera recept**.</span><span class="sxs-lookup"><span data-stu-id="60cae-299">Select **Edit formula**.</span></span>

    <span data-ttu-id="60cae-300">Observera att det aktuella uttrycket för fältet **Model.Data.Summary.Level** innehåller följande hårdkodade momskoder:</span><span class="sxs-lookup"><span data-stu-id="60cae-300">Notice that the current expression of the **Model.Data.Summary.Level** field includes the following hard-coded tax codes:</span></span>
    
    <span data-ttu-id="60cae-301">CASE (@.Code, "VAT19", "Regular", "InVAT19", "Regular", "VAT7", "Reduced", "InVAT7", "Reduced", "THIRD", "None", "InVAT0", "None", "Other")</span><span class="sxs-lookup"><span data-stu-id="60cae-301">CASE (@.Code, "VAT19", "Regular", "InVAT19", "Regular", "VAT7", "Reduced", "InVAT7", "Reduced", "THIRD", "None", "InVAT0", "None", "Other")</span></span>

4.  <span data-ttu-id="60cae-302">I fältet **Formula** ange **CASE(@.LevelByLookup, TaxationLevel.'Regular taxation', "Regular", TaxationLevel.'Reduced taxation', "Reduced", TaxationLevel.'No taxation', "None", "Other")**.</span><span class="sxs-lookup"><span data-stu-id="60cae-302">In the **Formula** field, enter **CASE(@.LevelByLookup, TaxationLevel.'Regular taxation', "Regular", TaxationLevel.'Reduced taxation', "Reduced", TaxationLevel.'No taxation', "None", "Other")**.</span></span>

    ![ER-åtgärdsdesignersida](./media/RCS-AppSpecParms-ConfigureFormat-ChangeLookupFld.PNG)
    
    <span data-ttu-id="60cae-304">Lägg märke till att uttrycket för fältet **Model.Data.Summary.Level** returnerar skattenivån, baserat på den aktuella postens momskod och den uppsättning regler som en affärsanvändare konfigurerar i **Model.Data.Selector**.</span><span class="sxs-lookup"><span data-stu-id="60cae-304">Notice that the expression of the **Model.Data.Summary.Level** field will now return the taxation level, based on the tax code of the current record and the set of rules that that a business user configures in the **Model.Data.Selector** lookup data source.</span></span>
    
5.  <span data-ttu-id="60cae-305">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="60cae-305">Select **Save**.</span></span>
6.  <span data-ttu-id="60cae-306">Stäng sidan **Formeldesigner**.</span><span class="sxs-lookup"><span data-stu-id="60cae-306">Close **Formula designer** page.</span></span>
7.  <span data-ttu-id="60cae-307">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="60cae-307">Select **OK**.</span></span>
8.  <span data-ttu-id="60cae-308">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="60cae-308">Select **Save**.</span></span>
9.  <span data-ttu-id="60cae-309">Stäng sidan **Formatdesigner**.</span><span class="sxs-lookup"><span data-stu-id="60cae-309">Close **Format designer** page.</span></span>

## <a name="complete-the-draft-version-of-a-derived-format"></a><span data-ttu-id="60cae-310">Slutför utkastversion av ett härlett format</span><span class="sxs-lookup"><span data-stu-id="60cae-310">Complete the draft version of a derived format</span></span>

1.  <span data-ttu-id="60cae-311">På snabbfliken **versioner** väljer du **ändra status**.</span><span class="sxs-lookup"><span data-stu-id="60cae-311">On the **Versions** fast tab, select **Change status**.</span></span>
2.  <span data-ttu-id="60cae-312">Välj **Slutför**.</span><span class="sxs-lookup"><span data-stu-id="60cae-312">Select **Complete**.</span></span>
3.  <span data-ttu-id="60cae-313">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="60cae-313">Select **OK**.</span></span>

## <a name="export-completed-version-of-modified-format"></a><span data-ttu-id="60cae-314">Exportera slutförd justerad version av ett modifierat format</span><span class="sxs-lookup"><span data-stu-id="60cae-314">Export completed version of modified format</span></span>

1.  <span data-ttu-id="60cae-315">I konfigurationsträdet väljer du objektet **format för att lära dig hur du letar upp LE-data**.</span><span class="sxs-lookup"><span data-stu-id="60cae-315">In the configuration tree, select the **Format to learn how to lookup LE data** item.</span></span>
2.  <span data-ttu-id="60cae-316">På snabbfliken **Versioner** väljer du den post som har statusen **Slutförd**.</span><span class="sxs-lookup"><span data-stu-id="60cae-316">On the **Versions** fast tab, select the record that has a status of **Completed**.</span></span>
3.  <span data-ttu-id="60cae-317">Välj **kurs**</span><span class="sxs-lookup"><span data-stu-id="60cae-317">Select **Exchange**.</span></span>
4.  <span data-ttu-id="60cae-318">Välj **Exportera som XML-fil**.</span><span class="sxs-lookup"><span data-stu-id="60cae-318">Select **Export as XML file**.</span></span>
5.  <span data-ttu-id="60cae-319">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="60cae-319">Select **OK**.</span></span>
6.  <span data-ttu-id="60cae-320">Webbläsaren hämtar filen **format för att lära dig att leta upp filen LE data.xml**.</span><span class="sxs-lookup"><span data-stu-id="60cae-320">The web browser downloads a **Format to learn how to lookup LE data.xml** file.</span></span> <span data-ttu-id="60cae-321">Spara den här filen lokalt.</span><span class="sxs-lookup"><span data-stu-id="60cae-321">Store this file locally.</span></span>

<span data-ttu-id="60cae-322">Upprepa stegen i det här avsnittet för överordnade objekt i **formatet om du vill ha information om hur du söker efter LE-data** och lagrar följande filer lokalt:</span><span class="sxs-lookup"><span data-stu-id="60cae-322">Repeat steps in this section for parent items of the **Format to learn how to lookup LE data** format, and store the following files locally:</span></span>

-   <span data-ttu-id="60cae-323">Format för att lära dig parameteranrop.xml</span><span class="sxs-lookup"><span data-stu-id="60cae-323">Format to learn parameterized calls.xml</span></span>
-   <span data-ttu-id="60cae-324">Mappning för att lära dig parameteranrop.xml</span><span class="sxs-lookup"><span data-stu-id="60cae-324">Mapping to learn parameterized calls.xml</span></span>
-   <span data-ttu-id="60cae-325">Modell för att lära dig parameteranrop.xml</span><span class="sxs-lookup"><span data-stu-id="60cae-325">Model to learn parameterized calls.xml</span></span>

<span data-ttu-id="60cae-326">Så här lär du dig hur du använder konfigurerade ER-formatet **format för att lära dig hur du slår upp IE-data** för att ställa in uppsättningar med momskoder som är beroende av den juridiska personen genom att använda olika beskattningsnivåer, slutför stegen i avsnittet [Ange parametrar ett ER-format per juridisk person](er-app-specific-parameters-set-up.md).</span><span class="sxs-lookup"><span data-stu-id="60cae-326">To learn how to use the configured **Format to learn how to lookup LE data** ER format to set up legal entity–dependent sets of tax codes to filter tax transactions by different taxation levels, complete the steps in the [Set up the parameters of an ER format per legal entity](er-app-specific-parameters-set-up.md) topic.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="60cae-327">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="60cae-327">Additional resources</span></span>

[<span data-ttu-id="60cae-328">Formeldesigner i elektronisk rapportering</span><span class="sxs-lookup"><span data-stu-id="60cae-328">Formula designer in Electronic reporting</span></span>](general-electronic-reporting-formula-designer.md)

[<span data-ttu-id="60cae-329">Ställ in parametrarna för ett ER-format per juridisk person</span><span class="sxs-lookup"><span data-stu-id="60cae-329">Set up the parameters of an ER format per legal entity</span></span>](er-app-specific-parameters-set-up.md)
