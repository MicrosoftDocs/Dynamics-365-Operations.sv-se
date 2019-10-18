---
title: Stödparameteranrop till ER-datakällor för beräknad fälttyp
description: Det här avsnittet innehåller information om hur du använder typen beräknat fält för ER-datakällor.
author: NickSelin
manager: AnnBe
ms.date: 09/09/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: ''
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 86efa927fa97be0d54e965bf33b1a18519025c22
ms.sourcegitcommit: 2460d0da812c45fce67a061386db52e0ae46b0f3
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/30/2019
ms.locfileid: "2248687"
---
# <a name="support-parameterized-calls-of-er-data-sources-of-the-calculated-field-type"></a><span data-ttu-id="31fab-103">Stödparameteranrop till ER-datakällor för typen beräknat fält</span><span class="sxs-lookup"><span data-stu-id="31fab-103">Support parameterized calls of ER data sources of the Calculated field type</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="31fab-104">I det här avsnittet beskrivs hur du kan utforma en data källa med elektronisk rapportering (ER) med hjälp av typen **beräknat fält**.</span><span class="sxs-lookup"><span data-stu-id="31fab-104">This topic explains how you can design an Electronic reporting (ER) data source by using the **Calculated field** type.</span></span> <span data-ttu-id="31fab-105">Den här datakällan kan innehålla ett ER-uttryck som vid körning kan kontrolleras av värdena i parameterargumenten som är konfigurerade i en bindning som anropar den här datakällan.</span><span class="sxs-lookup"><span data-stu-id="31fab-105">This data source may contain an ER expression that, when executed, can be controlled by the values of the parameter arguments that are configured in a binding that calls this data source.</span></span> <span data-ttu-id="31fab-106">Genom att konfigurera parametriserade anrop av en sådan datakälla kan du återanvända en enskild datakälla i många bindningar, vilket minskar det totala antalet datakällor som måste konfigureras i ER-modellmappningar eller ER-format.</span><span class="sxs-lookup"><span data-stu-id="31fab-106">By configuring parameterized calls of such a data source, you can reuse a single data source in many bindings, which reduces the total number of data sources that must be configured in ER model mappings or ER formats.</span></span> <span data-ttu-id="31fab-107">Det förenklar också den konfigurerade ER-komponenten, vilket minskar underhållskostnaderna och kostnaderna för användning av andra konsumenter.</span><span class="sxs-lookup"><span data-stu-id="31fab-107">It also simplifies the configured ER component, which reduces the maintenance costs and the cost of use by other consumers.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="31fab-108">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="31fab-108">Prerequisites</span></span>
<span data-ttu-id="31fab-109">För att slutföra exemplet i det här avsnittet måste du ha följande åtkomst:</span><span class="sxs-lookup"><span data-stu-id="31fab-109">To complete the examples in this topic, you must have the following access:</span></span>

- <span data-ttu-id="31fab-110">Åtkomst till en av dessa roller:</span><span class="sxs-lookup"><span data-stu-id="31fab-110">Access to one of these roles:</span></span>

    - <span data-ttu-id="31fab-111">Utvecklare för elektronisk rapportering</span><span class="sxs-lookup"><span data-stu-id="31fab-111">Electronic reporting developer</span></span>
    - <span data-ttu-id="31fab-112">Konsult för funktionen för elektronisk rapportering</span><span class="sxs-lookup"><span data-stu-id="31fab-112">Electronic reporting functional consultant</span></span>
    - <span data-ttu-id="31fab-113">Systemadministratör</span><span class="sxs-lookup"><span data-stu-id="31fab-113">System administrator</span></span>

- <span data-ttu-id="31fab-114">Åtkomst till Regulatory Configuration Services (RCS) som har etablerats för samma innehavare som Finance and Operations för en av följande roller:</span><span class="sxs-lookup"><span data-stu-id="31fab-114">Access to Regulatory Configuration Services (RCS) that have been provisioned for the same tenant as Finance and Operations for one of the following roles:</span></span>

    - <span data-ttu-id="31fab-115">Utvecklare för elektronisk rapportering</span><span class="sxs-lookup"><span data-stu-id="31fab-115">Electronic reporting developer</span></span>
    - <span data-ttu-id="31fab-116">Konsult för funktionen för elektronisk rapportering</span><span class="sxs-lookup"><span data-stu-id="31fab-116">Electronic reporting functional consultant</span></span>
    - <span data-ttu-id="31fab-117">Systemadministratör</span><span class="sxs-lookup"><span data-stu-id="31fab-117">System administrator</span></span>

<span data-ttu-id="31fab-118">Från [Microsoft Download Center](https://go.microsoft.com/fwlink/?linkid=874684), hämta den komprimerade filen **Stödparameteranrop till ER-datakällor för beräknad fälttyp**.</span><span class="sxs-lookup"><span data-stu-id="31fab-118">From the [Microsoft Download Center](https://go.microsoft.com/fwlink/?linkid=874684), download the zipped (compressed) file **Support parameterized calls of ER data sources of Calculated field type**.</span></span> <span data-ttu-id="31fab-119">Den innehåller följande ER-konfigurationer som måste extraheras och lagras lokalt.</span><span class="sxs-lookup"><span data-stu-id="31fab-119">It contains the following ER configurations that must be extracted and stored locally.</span></span>

| <span data-ttu-id="31fab-120">**Innehåll**</span><span class="sxs-lookup"><span data-stu-id="31fab-120">**Content**</span></span>                           | <span data-ttu-id="31fab-121">**Filnamn**</span><span class="sxs-lookup"><span data-stu-id="31fab-121">**File name**</span></span>                                        |
|---------------------------------------|------------------------------------------------------|
| <span data-ttu-id="31fab-122">Konfiguration av exempel på ER-datamodell.</span><span class="sxs-lookup"><span data-stu-id="31fab-122">Sample ER data model configuration</span></span>    | <span data-ttu-id="31fab-123">Modell för att lära dig parameteranrop.version.1.xml</span><span class="sxs-lookup"><span data-stu-id="31fab-123">Model to learn parameterized calls.version.1.xml</span></span>     |
| <span data-ttu-id="31fab-124">Konfiguration av exempel på ER-metadata.</span><span class="sxs-lookup"><span data-stu-id="31fab-124">Sample ER metadata configuration</span></span>      | <span data-ttu-id="31fab-125">Metadata för att lära dig parameteranrop.version.1.xml</span><span class="sxs-lookup"><span data-stu-id="31fab-125">Metadata to learn parameterized calls.version.1.xml</span></span>  |
| <span data-ttu-id="31fab-126">Konfiguration av exempel på ER-modellmappning</span><span class="sxs-lookup"><span data-stu-id="31fab-126">Sample ER model mapping configuration</span></span> | <span data-ttu-id="31fab-127">Mappning för att lära dig parameteranrop.version.1.1.xml</span><span class="sxs-lookup"><span data-stu-id="31fab-127">Mapping to learn parameterized calls.version.1.1.xml</span></span> |
| <span data-ttu-id="31fab-128">Konfiguration av exempel på ER-format.</span><span class="sxs-lookup"><span data-stu-id="31fab-128">Sample ER format configuration</span></span>        | <span data-ttu-id="31fab-129">Format för att lära dig parameteranrop.version.1.1.xml</span><span class="sxs-lookup"><span data-stu-id="31fab-129">Format to learn parameterized calls.version.1.1.xml</span></span>  |

## <a name="sign-in-to-your-rcs-instance"></a><span data-ttu-id="31fab-130">Logga in på RCS-instansen.</span><span class="sxs-lookup"><span data-stu-id="31fab-130">Sign in to your RCS instance</span></span>
<span data-ttu-id="31fab-131">I det här exemplet skapar du en konfiguration för exempelföretaget, Litware, Inc. Först, i RCS, måste du slutföra stegen i proceduren [Skapa en konfigurationsleverantör och markera den som aktiv](tasks/er-configuration-provider-mark-it-active-2016-11.md):</span><span class="sxs-lookup"><span data-stu-id="31fab-131">In this example, you will create a configuration for the sample company, Litware, Inc. First, in RCS, you must complete the steps in the [Create a configuration provider and mark it as active](tasks/er-configuration-provider-mark-it-active-2016-11.md) procedure:</span></span>

1. <span data-ttu-id="31fab-132">Välj **elektronisk rapportering**på standardinstrumentpanelen.</span><span class="sxs-lookup"><span data-stu-id="31fab-132">On the default dashboard, select **Electronic reporting**.</span></span>
2. <span data-ttu-id="31fab-133">Välj **rapporteringskonfigurationer**.</span><span class="sxs-lookup"><span data-stu-id="31fab-133">Select **Reporting configurations**.</span></span>
3. <span data-ttu-id="31fab-134">Importera nedladdade konfigurationer till RCS i följande ordning: datamodell, metadata, modellmappning, format.</span><span class="sxs-lookup"><span data-stu-id="31fab-134">Import the downloaded configurations to RCS in the following sequence: data model, metadata, model mapping, format.</span></span> <span data-ttu-id="31fab-135">Utför följande steg för varje ER-konfiguration:</span><span class="sxs-lookup"><span data-stu-id="31fab-135">Complete the following steps for each ER configuration:</span></span>

    1. <span data-ttu-id="31fab-136">Välj **kurs**</span><span class="sxs-lookup"><span data-stu-id="31fab-136">Select **Exchange.**</span></span>
    2. <span data-ttu-id="31fab-137">Välj **Läs in från XML-fil**.</span><span class="sxs-lookup"><span data-stu-id="31fab-137">Select **Load from XML file**.</span></span>
    3. <span data-ttu-id="31fab-138">Välj **bläddra** och sedan den nödvändiga ER-konfigurationen i XML-format.</span><span class="sxs-lookup"><span data-stu-id="31fab-138">Select **Browse**, and then select the required ER configuration in XML format.</span></span>
    4. <span data-ttu-id="31fab-139">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="31fab-139">Select **OK.**</span></span>

## <a name="review-the-provided-er-solution"></a><span data-ttu-id="31fab-140">Granska den medföljande ER-lösningen</span><span class="sxs-lookup"><span data-stu-id="31fab-140">Review the provided ER solution</span></span>

### <a name="review-model-mapping"></a><span data-ttu-id="31fab-141">Granska modellmappning</span><span class="sxs-lookup"><span data-stu-id="31fab-141">Review model mapping</span></span>

1. <span data-ttu-id="31fab-142">I konfigurationsträdet expanderar du innehållet i objektet **modell för att lära dig parameteranrop**.</span><span class="sxs-lookup"><span data-stu-id="31fab-142">In the configuration tree, expand the content of the **Model to learn parameterized calls** item.</span></span>
2. <span data-ttu-id="31fab-143">Välj **Mappning för att lära dig parameteranrop**.</span><span class="sxs-lookup"><span data-stu-id="31fab-143">Select **Mapping to learn parameterized calls**.</span></span>
3. <span data-ttu-id="31fab-144">Välj **Designer**.</span><span class="sxs-lookup"><span data-stu-id="31fab-144">Select **Designer**.</span></span>
4. <span data-ttu-id="31fab-145">Välj **Designer**.</span><span class="sxs-lookup"><span data-stu-id="31fab-145">Select **Designer**.</span></span>  
   
<span data-ttu-id="31fab-146">Den här ER-modellmappningen har utformats för att göra följande:</span><span class="sxs-lookup"><span data-stu-id="31fab-146">This ER model mapping is designed to do the following:</span></span>

- <span data-ttu-id="31fab-147">Hämta listan över momskoder **(moms** datakälla) som finns i **TaxTable**-registret.</span><span class="sxs-lookup"><span data-stu-id="31fab-147">Fetch the list of tax codes (**Tax** data source) residing in the   **TaxTable** table.</span></span>
- <span data-ttu-id="31fab-148">Hämta listan över momstransaktioner **(Trans** datakälla) som finns i **TaxTrans**-registret.</span><span class="sxs-lookup"><span data-stu-id="31fab-148">Fetch the list of tax transactions (**Trans** data source) residing in the   **TaxTrans** table:</span></span>
    
    - <span data-ttu-id="31fab-149">Gruppera listan över hämtade transaktioner (**Gr** datakälla) efter momskod.</span><span class="sxs-lookup"><span data-stu-id="31fab-149">Group the list of fetched transactions (**Gr** data source) by tax code.</span></span>
    - <span data-ttu-id="31fab-150">Beräkna för grupperade transaktioner efter aggregerade värden per momskod:</span><span class="sxs-lookup"><span data-stu-id="31fab-150">Calculate for grouped transactions following aggregated values per   tax code:</span></span>

        - <span data-ttu-id="31fab-151">Summa av basvärde för moms.</span><span class="sxs-lookup"><span data-stu-id="31fab-151">Sum of tax base values.</span></span>
        - <span data-ttu-id="31fab-152">Summa av momsvärden.</span><span class="sxs-lookup"><span data-stu-id="31fab-152">Sum of tax values.</span></span>
        - <span data-ttu-id="31fab-153">Lägsta värde för tillämpad momssats.</span><span class="sxs-lookup"><span data-stu-id="31fab-153">Minimum value of applied tax rate.</span></span>

<span data-ttu-id="31fab-154">Modellmappningen i den här konfigurationen implementerar basdatamodellen för alla ER-format som skapas för den här modellen och körs i Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="31fab-154">The model mapping in this configuration implements the base data model for any of the ER formats created for this model and executed in Finance and Operations.</span></span> <span data-ttu-id="31fab-155">Detta innebär att innehållet i datakällorna **Moms** och **Gr** visas för ER-format, t.ex. abstrakta datakällor.</span><span class="sxs-lookup"><span data-stu-id="31fab-155">As a result, the content of the **Tax** and **Gr** data sources is exposed for ER formats such as abstract data sources.</span></span>

  ![Sidan modellmappningsdesigner med datakällorna Moms och Gr](media/er-calculated-field-type-01.png)

5.  <span data-ttu-id="31fab-157">Stäng sidan **modellmappningsdesigner**.</span><span class="sxs-lookup"><span data-stu-id="31fab-157">Close the **Model mapping designer** page.</span></span>
6.  <span data-ttu-id="31fab-158">Stäng sidan **modellmappning**.</span><span class="sxs-lookup"><span data-stu-id="31fab-158">Close the **Model mapping** page.</span></span>

### <a name="review-format"></a><span data-ttu-id="31fab-159">Granska format</span><span class="sxs-lookup"><span data-stu-id="31fab-159">Review format</span></span>

1. <span data-ttu-id="31fab-160">I konfigurationsträdet expanderar du innehållet i objektet **modell för att lära dig parameteranrop**.</span><span class="sxs-lookup"><span data-stu-id="31fab-160">In the configuration tree, expand the content of the **Model to learn parameterized calls** item.</span></span>
2. <span data-ttu-id="31fab-161">Välj **Format för att lära dig parameteranrop**.</span><span class="sxs-lookup"><span data-stu-id="31fab-161">Select **Format to learn parameterized calls**.</span></span>
3. <span data-ttu-id="31fab-162">Välj **Designer**.</span><span class="sxs-lookup"><span data-stu-id="31fab-162">Select **Designer**.</span></span> <span data-ttu-id="31fab-163">Det här ER-formatet har utformats för att göra följande:</span><span class="sxs-lookup"><span data-stu-id="31fab-163">This ER format is designed to do the following:</span></span>

  - <span data-ttu-id="31fab-164">Generera en skattedeklaration i XML-format.</span><span class="sxs-lookup"><span data-stu-id="31fab-164">Generate a tax statement in XML format.</span></span>
  - <span data-ttu-id="31fab-165">Lägga fram följande beskattningsnivåer i momsrapporten: vanlig, reducerad och ingen.</span><span class="sxs-lookup"><span data-stu-id="31fab-165">Present the following levels of taxation in the tax statement: regular, reduced, and none.</span></span>
  - <span data-ttu-id="31fab-166">Presentera flera detaljer för varje beskattningsnivå, med olika antal detaljer på varje nivå.</span><span class="sxs-lookup"><span data-stu-id="31fab-166">Present multiple details at each taxation level, having a different number of details in each level.</span></span>

  ![Formatdesignersida](media/er-calculated-field-type-02.png)

4. <span data-ttu-id="31fab-168">Välj **mappning**.</span><span class="sxs-lookup"><span data-stu-id="31fab-168">Select **Mapping**.</span></span>
5. <span data-ttu-id="31fab-169">Expandera artiklarna **Modell**, **Data** och **Sammanfattning**.</span><span class="sxs-lookup"><span data-stu-id="31fab-169">Expand the **Model**, **Data,** and **Summary** items.</span></span> 

   <span data-ttu-id="31fab-170">Den beräknade fältet **Model.Data.Summary.Level** innehåller det uttryck som returnerar koden för beskattningsnivån (**normal**, **reducerad**, **ingen,** eller **annan**) som ett textvärde för alla momskoder som kan hämtas från datakällan **Model.Data.Summary** vid körningstillfället.</span><span class="sxs-lookup"><span data-stu-id="31fab-170">The calculated field **Model.Data.Summary.Level** contains the expression that returns the code of the taxation level (**Regular**, **Reduced**, **None,** or **Other**) as a text value for any tax code that can be retrieved from the **Model.Data.Summary** data source at run time.</span></span>

  ![Sidan Formatera designer med information om datamodellen Modell för att lära sig parameteranrop](media/er-calculated-field-type-03.png)

6. <span data-ttu-id="31fab-172">Expandera **Modell**. **Data2**-objektet.</span><span class="sxs-lookup"><span data-stu-id="31fab-172">Expand the **Model**.**Data2** item.</span></span>
7. <span data-ttu-id="31fab-173">Expandera **Modell**. **Data2.Summary2**-objektet.</span><span class="sxs-lookup"><span data-stu-id="31fab-173">Expand the **Model**.**Data2.Summary2** item.</span></span>
   
   <span data-ttu-id="31fab-174">Datakällan **Modell**.**Data2.Summary2** har konfigurerats för att gruppera datakällan **Model.Data.Summary**  transaktionsdetaljer per beskattningsnivå (returneras av **Model.Data.Summary.Level** beräknat fält) och beräkna aggregeringar.</span><span class="sxs-lookup"><span data-stu-id="31fab-174">The **Model**.**Data2.Summary2** data source is configured to group the **Model.Data.Summary** data source transaction details by taxation level (returned by the **Model.Data.Summary.Level** calculated field) and compute the aggregations.</span></span>

  ![Sidan Formatera designer med information om datakällan Model.Data2.Summary2 data source](media/er-calculated-field-type-04.png)

8. <span data-ttu-id="31fab-176">Granska beräknade fält **Modell**.**Data2.Level1**, **Modell**.**Data2.Level2** och **Modell**.**Data2.Level3.**</span><span class="sxs-lookup"><span data-stu-id="31fab-176">Review the calculated fields **Model**.**Data2.Level1**, **Model**.**Data2.Level2**, and **Model**.**Data2.Level3.**</span></span> <span data-ttu-id="31fab-177">De här beräknade fälten används för att filtrera **Modell**. **Data2. Summary2**-postlista och returnerar endast poster som representerar en viss beskattningsnivå.</span><span class="sxs-lookup"><span data-stu-id="31fab-177">These calculated fields are used to filter the **Model**.**Data2.Summary2** records list and return only records that represent a particular taxation level.</span></span>
9. <span data-ttu-id="31fab-178">Stäng sidan **Formatdesigner**.</span><span class="sxs-lookup"><span data-stu-id="31fab-178">Close the **Format designer** page.</span></span>

## <a name="create-a-derived-format"></a><span data-ttu-id="31fab-179">Skapa ett härlett format</span><span class="sxs-lookup"><span data-stu-id="31fab-179">Create a derived format</span></span>
<span data-ttu-id="31fab-180">Du kan förbättra det angivna formatet genom att lägga till ett beräknat fält för att filtrera den begärda skattenivån i stället för att använda befintliga tre fält: **Modell**.**Data2.Level1**, **Modell**.**Data2.Level2,** och **Modell**.**Data2.Level3**.</span><span class="sxs-lookup"><span data-stu-id="31fab-180">You can improve the provided format by adding one calculated field to filter the required taxation level instead of using the existing three fields: **Model**.**Data2.Level1**, **Model**.**Data2.Level2,** and **Model**.**Data2.Level3**.</span></span> <span data-ttu-id="31fab-181">Den obligatoriska skattenivån kan anges på platsen där det nya beräknade fältet ska anropas.</span><span class="sxs-lookup"><span data-stu-id="31fab-181">The required taxation level can be specified in the location where this new calculated field will be called.</span></span>

1. <span data-ttu-id="31fab-182">I konfigurationsträdet expanderar du innehållet i objektet **modell för att lära dig parameteranrop**.</span><span class="sxs-lookup"><span data-stu-id="31fab-182">In the configuration tree, expand the content of the **Model to learn parameterized calls** item.</span></span>
2. <span data-ttu-id="31fab-183">Välj **Format för att lära dig parameteranrop**.</span><span class="sxs-lookup"><span data-stu-id="31fab-183">Select **Format to learn parameterized calls**.</span></span>
3. <span data-ttu-id="31fab-184">Välj **Skapa konfiguration**.</span><span class="sxs-lookup"><span data-stu-id="31fab-184">Select **Create configuration**.</span></span>
4. <span data-ttu-id="31fab-185">Välj **Härled från namn: format om du vill lära dig parameteranrop, Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="31fab-185">Select **Derive from Name: Format to learn parameterized calls, Microsoft**.</span></span>
5. <span data-ttu-id="31fab-186">I fältet **namn** anger du **format för att lära parameteranrop (anpassad)**.</span><span class="sxs-lookup"><span data-stu-id="31fab-186">In the **Name** field, enter **Format to learn parameterized calls (custom)**.</span></span>
6. <span data-ttu-id="31fab-187">Välj **Skapa konfiguration**.</span><span class="sxs-lookup"><span data-stu-id="31fab-187">Select **Create configuration.**</span></span>

## <a name="configure-a-parameterized-calculated-field-that-returns-a-list-of-records"></a><span data-ttu-id="31fab-188">Konfigurera ett parameter beräknat fält som returnerar en lista med poster</span><span class="sxs-lookup"><span data-stu-id="31fab-188">Configure a parameterized calculated field that returns a list of records</span></span>

### <a name="start-adding-a-new-calculated-field"></a><span data-ttu-id="31fab-189">Börja lägga till ett nytt beräknat fält</span><span class="sxs-lookup"><span data-stu-id="31fab-189">Start adding a new calculated field</span></span>

1. <span data-ttu-id="31fab-190">Välj **Designer**.</span><span class="sxs-lookup"><span data-stu-id="31fab-190">Select **Designer**.</span></span>
2. <span data-ttu-id="31fab-191">Välj **expandera/komprimera** om du vill expandera alla formatobjekt.</span><span class="sxs-lookup"><span data-stu-id="31fab-191">Select **Expand/collapse** to expand all format items.</span></span>
3. <span data-ttu-id="31fab-192">Välj **mappning**.</span><span class="sxs-lookup"><span data-stu-id="31fab-192">Select **Mapping**.</span></span>
4. <span data-ttu-id="31fab-193">Expandera objektet **Modell**.</span><span class="sxs-lookup"><span data-stu-id="31fab-193">Expand the **Model** item.</span></span>
5. <span data-ttu-id="31fab-194">Välj objektet **Model.Data2**.</span><span class="sxs-lookup"><span data-stu-id="31fab-194">Select the **Model.Data2** item.</span></span>
6. <span data-ttu-id="31fab-195">Markera **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="31fab-195">Select **Add**.</span></span>
7. <span data-ttu-id="31fab-196">Välj **Funktioner\\Beräknat fält**.</span><span class="sxs-lookup"><span data-stu-id="31fab-196">Select **Functions\\Calculated field**.</span></span>
8. <span data-ttu-id="31fab-197">Skriv **Utdata** i fältet **Nivåer**.</span><span class="sxs-lookup"><span data-stu-id="31fab-197">In the **Name** field, enter **Levels**.</span></span>
9. <span data-ttu-id="31fab-198">Välj **Redigera recept**.</span><span class="sxs-lookup"><span data-stu-id="31fab-198">Select **Edit formula**.</span></span>

### <a name="define-a-parameter-for-adding-a-calculated-field"></a><span data-ttu-id="31fab-199">Definiera en parameter för att lägga till ett beräknat fält</span><span class="sxs-lookup"><span data-stu-id="31fab-199">Define a parameter for adding a calculated field</span></span>

1. <span data-ttu-id="31fab-200">Välj **parametrar**.</span><span class="sxs-lookup"><span data-stu-id="31fab-200">Select **Parameters**.</span></span>
2. <span data-ttu-id="31fab-201">Välj **Ny**.</span><span class="sxs-lookup"><span data-stu-id="31fab-201">Select **New**.</span></span>
3. <span data-ttu-id="31fab-202">I fältet **Namn** anger du **beskattningsnivå**.</span><span class="sxs-lookup"><span data-stu-id="31fab-202">In the **Name** field, enter **Taxation Level**.</span></span>
4. <span data-ttu-id="31fab-203">Välj **Typ** i fältet **Artikeltyp**.</span><span class="sxs-lookup"><span data-stu-id="31fab-203">In the **Type** field, select **String**.</span></span>

    <span data-ttu-id="31fab-204">Endast primitiva datatyper kan användas för att ange typen för parameterns argument.</span><span class="sxs-lookup"><span data-stu-id="31fab-204">Only primitive data types can be used to specify the type of the parameter’s argument.</span></span> <span data-ttu-id="31fab-205">Därför kan typerna **postlist**, **post** och **fasttext** inte användas för detta syfte.</span><span class="sxs-lookup"><span data-stu-id="31fab-205">Therefore, **Record list**, **Record**, and **Enum** types cannot be used for this purpose.</span></span>

    <span data-ttu-id="31fab-206">Det maximala antalet parametrar som kan anges för ett enskilt beräknat fält är 8.</span><span class="sxs-lookup"><span data-stu-id="31fab-206">The maximum number of parameters that can be specified for a single calculated field is 8.</span></span>

    ![Lista över parameterdatakällor](media/er-calculated-field-type-05.png)

5. <span data-ttu-id="31fab-208">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="31fab-208">Select **OK**.</span></span>

<span data-ttu-id="31fab-209">Genom att lägga till den här parametern anger du det villkor som måste finnas på platser för att det här beräknade fältet ska kunna anropas.</span><span class="sxs-lookup"><span data-stu-id="31fab-209">By adding this parameter, you specify the condition that must be in place to call this calculated field.</span></span> <span data-ttu-id="31fab-210">När du ringer detta beräknade fält måste du ange argumentet för parametern **beskattningsnivå** som ett värde med formatet **sträng**.</span><span class="sxs-lookup"><span data-stu-id="31fab-210">When you call this calculated field, you need to specify the argument of the **Taxation Level** parameter as a value with **String** format.</span></span>

   <span data-ttu-id="31fab-211">Se till att du bara definierar parametrar för de beräknade fält som finns i en behållare (antingen **postlist**, **post** eller **behållare**).</span><span class="sxs-lookup"><span data-stu-id="31fab-211">Make sure that you define parameters only for those calculated fields that reside in a container (either **Record list**, **Record**, or **Container**).</span></span>

   <span data-ttu-id="31fab-212">Den konfigurerade parametern finns i listan över datakällor för det här beräknade fältet.</span><span class="sxs-lookup"><span data-stu-id="31fab-212">The configured parameter is available in the list of data sources for this calculated field.</span></span> <span data-ttu-id="31fab-213">Du kan lägga till parametern i det konfigurerade uttrycket genom att välja **Lägg till datakälla**.</span><span class="sxs-lookup"><span data-stu-id="31fab-213">You can add the parameter to the configured expression by selecting **Add data source**.</span></span>

   ![Datakällfält](media/er-calculated-field-type-06.png)

### <a name="define-an-expression-for-adding-a-calculated-field"></a><span data-ttu-id="31fab-215">Definiera ett uttryck för att lägga till ett beräknat fält</span><span class="sxs-lookup"><span data-stu-id="31fab-215">Define an expression for adding a calculated field</span></span>

1. <span data-ttu-id="31fab-216">I fältet **Formel**, ange:</span><span class="sxs-lookup"><span data-stu-id="31fab-216">In the **Formula** field, enter:</span></span> 

    <span data-ttu-id="31fab-217">**WHERE(\@.Summary2, \@.Summary2.grouped.Level =**</span><span class="sxs-lookup"><span data-stu-id="31fab-217">**WHERE(\@.Summary2, \@.Summary2.grouped.Level =**</span></span>
    
2. <span data-ttu-id="31fab-218">Välj parametern **skattenivå** i listan över datakällor.</span><span class="sxs-lookup"><span data-stu-id="31fab-218">Select the **Taxation Level** parameter in the list of data sources.</span></span>
3. <span data-ttu-id="31fab-219">Välj **Lägg till datakälla**.</span><span class="sxs-lookup"><span data-stu-id="31fab-219">Select **Add data source**.</span></span>
4. <span data-ttu-id="31fab-220">I fältet **formel** slutför uttryck:</span><span class="sxs-lookup"><span data-stu-id="31fab-220">In the **Formula** field, finalize the expression as:</span></span>  

    <span data-ttu-id="31fab-221">**WHERE(\@.Summary2, \@.Summary2.grouped.Level = 'Taxation Level')**</span><span class="sxs-lookup"><span data-stu-id="31fab-221">**WHERE(\@.Summary2, \@.Summary2.grouped.Level = 'Taxation Level')**</span></span>

5. <span data-ttu-id="31fab-222">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="31fab-222">Select **Save**.</span></span>

    ![Information om datakälla](media/er-calculated-field-type-07.png)

6. <span data-ttu-id="31fab-224">Stäng sidan **Formeldesigner**.</span><span class="sxs-lookup"><span data-stu-id="31fab-224">Close the **Formula designer** page.</span></span>

### <a name="finish-adding-a-new-calculated-field"></a><span data-ttu-id="31fab-225">Sluta lägga till ett nytt beräknat fält</span><span class="sxs-lookup"><span data-stu-id="31fab-225">Finish adding a new calculated field</span></span>

- <span data-ttu-id="31fab-226">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="31fab-226">Select **OK**.</span></span>

<span data-ttu-id="31fab-227">På sidan **formatdesigner** kräver det konfigurerade parametriserade beräknade fältet **nivåer** argumentet **sträng**.</span><span class="sxs-lookup"><span data-stu-id="31fab-227">On the **Format designer** page, the configured parameterized calculated field **Levels** requires a **String** argument.</span></span>

![Utökad lista över beräknade fältnivåer](media/er-calculated-field-type-08.png)

### <a name="use-the-configured-calculated-field-for-binding-format-elements"></a><span data-ttu-id="31fab-229">Använd det konfigurerade beräknade fältet för bindningsformatelement</span><span class="sxs-lookup"><span data-stu-id="31fab-229">Use the configured calculated field for binding format elements</span></span>

1. <span data-ttu-id="31fab-230">Välj **Model.Data2.Levels** för att välja det konfigurerade beräknade fältet.</span><span class="sxs-lookup"><span data-stu-id="31fab-230">Select **Model.Data2.Levels** to select the configured calculated field.</span></span>
2. <span data-ttu-id="31fab-231">Välj formatelementet **Statement.Taxation.Regular**.</span><span class="sxs-lookup"><span data-stu-id="31fab-231">Select the **Statement.Taxation.Regular** format element.</span></span>
3. <span data-ttu-id="31fab-232">Välj **bind**.</span><span class="sxs-lookup"><span data-stu-id="31fab-232">Select **Bind**.</span></span>
4. <span data-ttu-id="31fab-233">Välj **ja** om du vill ersätta den för tillfället använda datakällan, **level1**, med den nya datakällan, **nivåer** i alla kapslade formatelement i det valda formatelementet.</span><span class="sxs-lookup"><span data-stu-id="31fab-233">Select **Yes** to confirm the replacement of the currently used data source, **Level1**, by the new data source, **Levels**, in all nested format elements of the selected format element.</span></span>

    <span data-ttu-id="31fab-234">Tillämpad bindning har byggts som ett anrop till det parametriserade beräknade fältet.</span><span class="sxs-lookup"><span data-stu-id="31fab-234">Applied binding has been built as a call of the parameterized calculated field.</span></span> <span data-ttu-id="31fab-235">Som standard används namnet på det bundna formatelementet som ett argument för parametriserade beräknat fält under följande förhållanden:</span><span class="sxs-lookup"><span data-stu-id="31fab-235">By default, the name of the bound format element is used as an argument for parameterized calculated field under the following conditions:</span></span>

      - <span data-ttu-id="31fab-236">Det beräknade fältet konfigureras för att använda en enda parameter.</span><span class="sxs-lookup"><span data-stu-id="31fab-236">The calculated field is configured to use a single parameter.</span></span>
      - <span data-ttu-id="31fab-237">Datatypen för den här parametern definieras som **sträng**.</span><span class="sxs-lookup"><span data-stu-id="31fab-237">The data type of this parameter is defined as **String**.</span></span>

    <span data-ttu-id="31fab-238">När namnet på det bundna formatelementet är tomt används namnet på datakällan för det här elementet i tillämpad bindning.</span><span class="sxs-lookup"><span data-stu-id="31fab-238">When the name of the bound format element is blank, the data source name of this element is used in applied binding.</span></span>

5. <span data-ttu-id="31fab-239">Välj formatelementet **Statement.Taxation.Reduced**.</span><span class="sxs-lookup"><span data-stu-id="31fab-239">Select the **Statement.Taxation.Reduced** format element.</span></span>
6. <span data-ttu-id="31fab-240">Välj **bind**.</span><span class="sxs-lookup"><span data-stu-id="31fab-240">Select **Bind**.</span></span>
7. <span data-ttu-id="31fab-241">Välj **ja** om du vill ersätta den för tillfället använda datakällan, **level2**, med den nya datakällan, **nivåer** i alla kapslade formatelement under det valda formatelementet.</span><span class="sxs-lookup"><span data-stu-id="31fab-241">Select **Yes** to confirm the replacement of the currently used data source, **Level2**, by the new data source, **Levels**, in all nested format elements under the selected format element.</span></span>
8. <span data-ttu-id="31fab-242">Välj formatelementet **Statement.Taxation.None**.</span><span class="sxs-lookup"><span data-stu-id="31fab-242">Select the **Statement.Taxation.None** format element.</span></span>
9. <span data-ttu-id="31fab-243">Välj **bind**.</span><span class="sxs-lookup"><span data-stu-id="31fab-243">Select **Bind**.</span></span>
10. <span data-ttu-id="31fab-244">Välj **ja** om du vill ersätta den för tillfället använda datakällan, **level3**, med den nya datakällan, **nivåer** i alla kapslade formatelement under det valda formatelementet.</span><span class="sxs-lookup"><span data-stu-id="31fab-244">Select **Yes** to confirm the replacement of the currently used data source, **Level3**, by the new data source, **Levels**, in all nested format elements under the selected format element.</span></span>

   <span data-ttu-id="31fab-245">Om du anger argumentet för det parametriserade beräknade fältet för XML-elementet som representerar beskattningsnivån (t.ex. **Model.Data2.Levels("Reduced")** som ett textvärde), behöver du inte göra samma sak för kapslade XML-attribut, dvs. bindningar ärver automatiskt värdet för argumentet som definieras på den överordnade nivån (**Model.Data2.Levels.aggregated.Base**, inte **Model.Data2.Levels("Reduced").aggregated.Base**).</span><span class="sxs-lookup"><span data-stu-id="31fab-245">When you specify the argument of the parameterized calculated field for the XML element representing taxation level (for example, **Model.Data2.Levels("Reduced")** as a text value), you don’t need to do the same for nested XML attributes—their bindings will automatically inherit the value of the argument defined on the parent level (**Model.Data2.Levels.aggregated.Base**, not **Model.Data2.Levels("Reduced").aggregated.Base**).</span></span>

<span data-ttu-id="31fab-246">Återkommande anrop av valfritt parametriserat beräknat fält stöds inte.</span><span class="sxs-lookup"><span data-stu-id="31fab-246">Recurrent calls of any parameterized calculated field are not supported.</span></span>

<span data-ttu-id="31fab-247">Du kan välja **Redigera formel**och ändra det argument som används som standard det parametiserade beräknade fältet i den valda bindningen.</span><span class="sxs-lookup"><span data-stu-id="31fab-247">You can select **Edit formula**, and change the applied-by-default argument of the parameterized calculated field in the selected binding.</span></span> <span data-ttu-id="31fab-248">Om detta argument saknas kan det orsaka fel under körningen och användarna informeras om en sådan situation när det aktuella formatet valideras.</span><span class="sxs-lookup"><span data-stu-id="31fab-248">If this argument is missing, it can cause errors at run time — users are informed about such a situation when the current format is validated.</span></span>

![Varningsmeddelande för validering](media/er-calculated-field-type-10.png)

## <a name="configure-a-parameterized-calculated-field-to-return-a-record"></a><span data-ttu-id="31fab-250">Konfigurera ett parameter beräknat fält som returnera en post</span><span class="sxs-lookup"><span data-stu-id="31fab-250">Configure a parameterized calculated field to return a record</span></span>
<span data-ttu-id="31fab-251">När ett parametiserat beräknat fält returnerar en post måste du stödja bindningar av enskilda fält i den här posten för att kunna formatera element.</span><span class="sxs-lookup"><span data-stu-id="31fab-251">When a parameterized calculated field returns a record, you need to support binding of individual fields of this record to format elements.</span></span> <span data-ttu-id="31fab-252">I sådana fall kommer det inte att finnas någon överordnad bindning som innehåller värdet för ett argument för anrop av ett parameteriserat beräknat fält, det här värdet måste definieras i bindningen av en enskild posts fält.</span><span class="sxs-lookup"><span data-stu-id="31fab-252">In such cases there will be no parent binding that contains the value of an argument to call a parameterized calculated field — this value must be defined in the binding of a single record’s field.</span></span>

### <a name="start-adding-a-new-calculated-field"></a><span data-ttu-id="31fab-253">Börja lägga till ett nytt beräknat fält</span><span class="sxs-lookup"><span data-stu-id="31fab-253">Start adding a new calculated field</span></span>

1. <span data-ttu-id="31fab-254">Välj objektet **Model.Data2**.</span><span class="sxs-lookup"><span data-stu-id="31fab-254">Select the **Model.Data2** item.</span></span>
2. <span data-ttu-id="31fab-255">Markera **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="31fab-255">Select **Add**.</span></span>
3. <span data-ttu-id="31fab-256">Välj **Funktioner\\Beräknat fält**.</span><span class="sxs-lookup"><span data-stu-id="31fab-256">Select **Functions\\Calculated field**.</span></span>
4. <span data-ttu-id="31fab-257">Skriv **Dokument** i fältet **LevelRecord**.</span><span class="sxs-lookup"><span data-stu-id="31fab-257">In the **Name** field, enter **LevelRecord**.</span></span>
5. <span data-ttu-id="31fab-258">Välj **Redigera recept**.</span><span class="sxs-lookup"><span data-stu-id="31fab-258">Select **Edit formula**.</span></span>

### <a name="define-a-parameter-for-adding-a-calculated-field"></a><span data-ttu-id="31fab-259">Definiera en parameter för att lägga till ett beräknat fält</span><span class="sxs-lookup"><span data-stu-id="31fab-259">Define a parameter for adding a calculated field</span></span>

1. <span data-ttu-id="31fab-260">Välj **parametrar**.</span><span class="sxs-lookup"><span data-stu-id="31fab-260">Select **Parameters**.</span></span>
2. <span data-ttu-id="31fab-261">Välj **Ny**.</span><span class="sxs-lookup"><span data-stu-id="31fab-261">Select **New**.</span></span>
3. <span data-ttu-id="31fab-262">I fältet **Namn** anger du **beskattningsnivå**.</span><span class="sxs-lookup"><span data-stu-id="31fab-262">In the **Name** field, enter **Taxation Level**.</span></span>
4. <span data-ttu-id="31fab-263">Välj **Typ** i fältet **Artikeltyp**.</span><span class="sxs-lookup"><span data-stu-id="31fab-263">In the **Type** field, select **String**.</span></span>
5. <span data-ttu-id="31fab-264">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="31fab-264">Select **OK**.</span></span>

### <a name="define-an-expression-for-adding-a-calculated-field"></a><span data-ttu-id="31fab-265">Definiera ett uttryck för att lägga till ett beräknat fält</span><span class="sxs-lookup"><span data-stu-id="31fab-265">Define an expression for adding a calculated field</span></span>

1. <span data-ttu-id="31fab-266">I fältet **formel** anger du följande:</span><span class="sxs-lookup"><span data-stu-id="31fab-266">In the **Formula** field, enter the following:</span></span>  
    
    <span data-ttu-id="31fab-267">**FIRSTORNULL(\@.Levels(**</span><span class="sxs-lookup"><span data-stu-id="31fab-267">**FIRSTORNULL(\@.Levels(**</span></span>

2. <span data-ttu-id="31fab-268">Välj parametern **skattenivå**.</span><span class="sxs-lookup"><span data-stu-id="31fab-268">Select the **Taxation Level** parameter.</span></span>
3. <span data-ttu-id="31fab-269">Välj **Lägg till datakälla**.</span><span class="sxs-lookup"><span data-stu-id="31fab-269">Select **Add data source**.</span></span>
4. <span data-ttu-id="31fab-270">I fältet **formel** lägger du till **"momsnivå"))** till det som du angav i steg 1 för att färdigställa uttrycket till:</span><span class="sxs-lookup"><span data-stu-id="31fab-270">In the **Formula** field, append **'Taxation Level'))** to what you entered in Step 1 to finalize the expression to:</span></span>  
    
    <span data-ttu-id="31fab-271">**FIRSTORNULL(\@.Levels('Taxation Level'))**</span><span class="sxs-lookup"><span data-stu-id="31fab-271">**FIRSTORNULL(\@.Levels('Taxation Level'))**</span></span>

5. <span data-ttu-id="31fab-272">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="31fab-272">Select **Save**.</span></span>
6. <span data-ttu-id="31fab-273">Stäng sidan **Formeldesigner**.</span><span class="sxs-lookup"><span data-stu-id="31fab-273">Close **the Formula designer** page.</span></span>

### <a name="finish-adding-a-new-calculated-field"></a><span data-ttu-id="31fab-274">Sluta lägga till ett nytt beräknat fält</span><span class="sxs-lookup"><span data-stu-id="31fab-274">Finish adding a new calculated field</span></span>

-   <span data-ttu-id="31fab-275">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="31fab-275">Select **OK**.</span></span>

### <a name="use-the-configured-calculated-field-to-bind-format-elements"></a><span data-ttu-id="31fab-276">Använd det konfigurerade beräknade fältet för bindningsformatelement</span><span class="sxs-lookup"><span data-stu-id="31fab-276">Use the configured calculated field to bind format elements</span></span>

1. <span data-ttu-id="31fab-277">Expandera **Model.Data2.LevelRecord** för att välja det konfigurerade beräknade fältet.</span><span class="sxs-lookup"><span data-stu-id="31fab-277">Expand **Model.Data2.LevelRecord** to select the configured calculated field.</span></span>
2. <span data-ttu-id="31fab-278">Expandera behållaren **Model.Data2.LevelRecord.aggregated** för att välja det konfigurerade beräknade fältet.</span><span class="sxs-lookup"><span data-stu-id="31fab-278">Expand the **Model.Data2.LevelRecord.aggregated** container of the configured calculated field.</span></span>
3. <span data-ttu-id="31fab-279">Markera fältet **Model.Data2.LevelRecord.aggregated.Base**.</span><span class="sxs-lookup"><span data-stu-id="31fab-279">Select the **Model.Data2.LevelRecord.aggregated.Base** field.</span></span>
4. <span data-ttu-id="31fab-280">Välj formatelementet **Statement.Taxation.None**.</span><span class="sxs-lookup"><span data-stu-id="31fab-280">Select the **Statement.Taxation.None** format element.</span></span>
5. <span data-ttu-id="31fab-281">Välj **Avbind**.</span><span class="sxs-lookup"><span data-stu-id="31fab-281">Select **Unbind**.</span></span>
6. <span data-ttu-id="31fab-282">Välj formatelementet **Statement.Taxation.None.Base**.</span><span class="sxs-lookup"><span data-stu-id="31fab-282">Select the **Statement.Taxation.None.Base** format element.</span></span>
7. <span data-ttu-id="31fab-283">Välj **bind**.</span><span class="sxs-lookup"><span data-stu-id="31fab-283">Select **Bind**.</span></span>
8. <span data-ttu-id="31fab-284">Välj **Redigera recept**.</span><span class="sxs-lookup"><span data-stu-id="31fab-284">Select **Edit formula**.</span></span>
9. <span data-ttu-id="31fab-285">Ändra uttrycket till **Model.Data2.LevelRecord("None").aggregated.Base**.</span><span class="sxs-lookup"><span data-stu-id="31fab-285">Change the expression to **Model.Data2.LevelRecord("None").aggregated.Base**.</span></span>

![Uppdaterat uttryck](media/er-calculated-field-type-11.png)

## <a name="remove-calculated-fields-that-are-not-used"></a><span data-ttu-id="31fab-287">Ta bort beräknade fält som inte används</span><span class="sxs-lookup"><span data-stu-id="31fab-287">Remove calculated fields that are not used</span></span>

1. <span data-ttu-id="31fab-288">Välj **Model.Data2.Level1**.</span><span class="sxs-lookup"><span data-stu-id="31fab-288">Select **Model.Data2.Level1**.</span></span>
2. <span data-ttu-id="31fab-289">Välj **Ta bort**.</span><span class="sxs-lookup"><span data-stu-id="31fab-289">Select **Delete**.</span></span>
3. <span data-ttu-id="31fab-290">Välj **Model.Data2.Level2**.</span><span class="sxs-lookup"><span data-stu-id="31fab-290">Select **Model.Data2.Level2**.</span></span>
4. <span data-ttu-id="31fab-291">Välj **Ta bort**.</span><span class="sxs-lookup"><span data-stu-id="31fab-291">Select **Delete**.</span></span>
5. <span data-ttu-id="31fab-292">Välj **Model.Data2.Level3**.</span><span class="sxs-lookup"><span data-stu-id="31fab-292">Select **Model.Data2.Level3**.</span></span>
6. <span data-ttu-id="31fab-293">Välj **Ta bort**.</span><span class="sxs-lookup"><span data-stu-id="31fab-293">Select **Delete**.</span></span>
7. <span data-ttu-id="31fab-294">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="31fab-294">Select **Save**.</span></span>

  > [!NOTE]
  > <span data-ttu-id="31fab-295">Du återanvänder samma beräknade fält **Model.Data2.Levels** flera gånger i formatbindningar.</span><span class="sxs-lookup"><span data-stu-id="31fab-295">You reused the same calculated field **Model.Data2.Levels** several times in format bindings.</span></span> <span data-ttu-id="31fab-296">Det är mycket enklare att använda och underhålla ett enda beräknat fält i stället för att göra detta för flera likartade fält.</span><span class="sxs-lookup"><span data-stu-id="31fab-296">It is much easier to use and maintain a single calculated field instead of doing this for multiple similar fields.</span></span>

8. <span data-ttu-id="31fab-297">Stäng sidan **Formatdesigner**.</span><span class="sxs-lookup"><span data-stu-id="31fab-297">Close the **Format designer** page.</span></span>

## <a name="complete-adjusted-version-of-a-derived-format"></a><span data-ttu-id="31fab-298">Slutför justerad version av ett härlett format</span><span class="sxs-lookup"><span data-stu-id="31fab-298">Complete adjusted version of a derived format</span></span>

1. <span data-ttu-id="31fab-299">På snabbfliken **versioner** väljer du **ändra status**.</span><span class="sxs-lookup"><span data-stu-id="31fab-299">In the **Versions** FastTab, select **Change status**.</span></span>
2. <span data-ttu-id="31fab-300">Välj **Slutför**.</span><span class="sxs-lookup"><span data-stu-id="31fab-300">Select **Complete**.</span></span>

## <a name="export-completed-version-of-a-derived-format"></a><span data-ttu-id="31fab-301">Exportera slutförd justerad version av ett härlett format</span><span class="sxs-lookup"><span data-stu-id="31fab-301">Export completed version of a derived format</span></span>

1. <span data-ttu-id="31fab-302">Välj formatet **format om du vill läsa parametriserade anrop (anpassat)** i konfigurationsträdet.</span><span class="sxs-lookup"><span data-stu-id="31fab-302">Select **Format to learn parameterized calls (custom)** format in the configurations tree.</span></span>
2. <span data-ttu-id="31fab-303">På snabbfliken **Versioner**, välj slutförd version 1.1.1.</span><span class="sxs-lookup"><span data-stu-id="31fab-303">In the **Versions** FastTab, select the completed version 1.1.1.</span></span>
3. <span data-ttu-id="31fab-304">Välj **kurs**</span><span class="sxs-lookup"><span data-stu-id="31fab-304">Select **Exchange**.</span></span>
4. <span data-ttu-id="31fab-305">Välj **Exportera som XML-fil**.</span><span class="sxs-lookup"><span data-stu-id="31fab-305">Select **Export as XML file**.</span></span>
5. <span data-ttu-id="31fab-306">Lagra den hämtade konfigurationen lokalt i XML-format.</span><span class="sxs-lookup"><span data-stu-id="31fab-306">Store the downloaded configuration locally, in XML format.</span></span>

## <a name="test-er-formats"></a><span data-ttu-id="31fab-307">Testa ER-format</span><span class="sxs-lookup"><span data-stu-id="31fab-307">Test ER formats</span></span> 
<span data-ttu-id="31fab-308">Du kan köra de ursprungliga och de förbättrade ER-formaten för att säkerställa att konfigurerade parameterbaserade beräknade fält fungerar som de ska.</span><span class="sxs-lookup"><span data-stu-id="31fab-308">You can run the initial and improved ER formats to make sure that configured parameterized calculated fields work properly.</span></span>

### <a name="import-er-configurations"></a><span data-ttu-id="31fab-309">Importera ER-konfigurationer</span><span class="sxs-lookup"><span data-stu-id="31fab-309">Import ER configurations</span></span>
<span data-ttu-id="31fab-310">Du kan importera granskade konfigurationer från RCS med hjälp av ER-databasen för **RCS**-typen.</span><span class="sxs-lookup"><span data-stu-id="31fab-310">You can import reviewed configurations from RCS by using the ER repository of the **RCS** type.</span></span> <span data-ttu-id="31fab-311">Om du redan gick igenom stegen i avsnittet [Importera konfigurationer för elektronisk rapportering från Regulatory Configuration Services](rcs-download-configurations.md), använder du den konfigurerade återställningsdatabasen för att importera konfigurationer som beskrivs tidigare i det här avsnittet till din miljö.</span><span class="sxs-lookup"><span data-stu-id="31fab-311">If you already went through the steps in the topic, [Import Electronic reporting configurations from Regulatory Configuration Services](rcs-download-configurations.md), use the configured ER repository to import configurations discussed earlier in this topic to your environment.</span></span> <span data-ttu-id="31fab-312">Annars följer du dessa steg:</span><span class="sxs-lookup"><span data-stu-id="31fab-312">Otherwise, follow these steps:</span></span>

1. <span data-ttu-id="31fab-313">Markera företaget **DEMF** och välj sedan **elektronisk rapportering** på standardinstrumentpanelen.</span><span class="sxs-lookup"><span data-stu-id="31fab-313">Select the **DEMF** company and on the default dashboard, select **Electronic reporting**.</span></span>
2. <span data-ttu-id="31fab-314">Välj **rapporteringskonfigurationer**.</span><span class="sxs-lookup"><span data-stu-id="31fab-314">Select **Reporting configurations**.</span></span>
3. <span data-ttu-id="31fab-315">Importera konfigurationer från Microsoft Download Center i följande ordning: datamodell, modellmappning, format.</span><span class="sxs-lookup"><span data-stu-id="31fab-315">Import the configurations from Microsoft Download Center in the following sequence: data model, model mapping, format.</span></span> <span data-ttu-id="31fab-316">Utför följande steg för varje ER-konfiguration:</span><span class="sxs-lookup"><span data-stu-id="31fab-316">Complete the following steps for each ER configuration:</span></span>

    1. <span data-ttu-id="31fab-317">Välj **kurs**</span><span class="sxs-lookup"><span data-stu-id="31fab-317">Select **Exchange.**</span></span>
    2. <span data-ttu-id="31fab-318">Välj **Läs in från XML-fil**.</span><span class="sxs-lookup"><span data-stu-id="31fab-318">Select **Load from XML file**.</span></span>
    3. <span data-ttu-id="31fab-319">Välj **bläddra** och sedan den nödvändiga ER-konfigurationen i XML-format.</span><span class="sxs-lookup"><span data-stu-id="31fab-319">Select **Browse** to select the required ER configuration in XML format.</span></span>
    4. <span data-ttu-id="31fab-320">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="31fab-320">Select **OK**.</span></span>

4. <span data-ttu-id="31fab-321">Importera exporterade från RCS slutförd version 1.1.1 av formatet **Format för att lära dig parameteranrop**:</span><span class="sxs-lookup"><span data-stu-id="31fab-321">Import the exported from RCS completed version 1.1.1 of the **Format to learn parameterized calls (custom)** format:</span></span>

    1. <span data-ttu-id="31fab-322">Välj **kurs**</span><span class="sxs-lookup"><span data-stu-id="31fab-322">Select **Exchange.**</span></span>
    2. <span data-ttu-id="31fab-323">Välj **Läs in från XML-fil**.</span><span class="sxs-lookup"><span data-stu-id="31fab-323">Select **Load from XML file**.</span></span>
    3. <span data-ttu-id="31fab-324">Välj **bläddra** om du vill välja den lokalt lagrade filen **Format för att lära dig parameteranrop (anpassade)** i XML-format.</span><span class="sxs-lookup"><span data-stu-id="31fab-324">Select **Browse** to select the locally stored **Format to learn parameterized calls (custom)** file in XML format.</span></span>
    4. <span data-ttu-id="31fab-325">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="31fab-325">Select **OK**.</span></span>

### <a name="run-er-formats"></a><span data-ttu-id="31fab-326">Kör ER-format</span><span class="sxs-lookup"><span data-stu-id="31fab-326">Run ER formats</span></span>

1. <span data-ttu-id="31fab-327">I konfigurationsträdet expanderar du innehållet i objektet **modell för att lära dig parameteranrop**.</span><span class="sxs-lookup"><span data-stu-id="31fab-327">In the configuration tree, expand the content of the **Model to learn parameterized calls** item.</span></span>
2. <span data-ttu-id="31fab-328">Välj **Format för att lära dig parameteranrop**.</span><span class="sxs-lookup"><span data-stu-id="31fab-328">Select **Format to learn parameterized calls**.</span></span>
3. <span data-ttu-id="31fab-329">Välj **kör** på menyfliken högst upp.</span><span class="sxs-lookup"><span data-stu-id="31fab-329">Select **Run** on the top-most ribbon.</span></span>
4. <span data-ttu-id="31fab-330">Spara de lokalt genererade utdata.</span><span class="sxs-lookup"><span data-stu-id="31fab-330">Save the locally generated output.</span></span>
5. <span data-ttu-id="31fab-331">Välj objektet **format för att lära sig mer parameteranrop (anpassat**).</span><span class="sxs-lookup"><span data-stu-id="31fab-331">Select the **Format to learn parameterized calls (custom)** item.</span></span>
6. <span data-ttu-id="31fab-332">Välj **kör** på menyfliken högst upp.</span><span class="sxs-lookup"><span data-stu-id="31fab-332">Select **Run** on the top-most ribbon.</span></span>
7. <span data-ttu-id="31fab-333">Spara genererade utdata lokalt.</span><span class="sxs-lookup"><span data-stu-id="31fab-333">Save the generated output locally.</span></span> 
8. <span data-ttu-id="31fab-334">Jämför innehållet i de genererade utflödena.</span><span class="sxs-lookup"><span data-stu-id="31fab-334">Compare the contents of the generated outputs.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="31fab-335">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="31fab-335">Additional resources</span></span>
[<span data-ttu-id="31fab-336">Formeldesigner i elektronisk rapportering</span><span class="sxs-lookup"><span data-stu-id="31fab-336">Formula designer in Electronic reporting</span></span>](general-electronic-reporting-formula-designer.md)
