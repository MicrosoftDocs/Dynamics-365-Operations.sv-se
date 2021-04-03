---
title: Stödparameteranrop till ER-datakällor för typen beräknat fält
description: Det här avsnittet innehåller information om hur du använder typen beräknat fält för ER-datakällor.
author: NickSelin
manager: AnnBe
ms.date: 08/06/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: ''
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 1c2c13cd3f165826e0d5b5ac901ffa61895301e7
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/09/2021
ms.locfileid: "5569211"
---
# <a name="support-parameterized-calls-of-er-data-sources-of-the-calculated-field-type"></a><span data-ttu-id="88479-103">Stödparameteranrop till ER-datakällor för typen beräknat fält</span><span class="sxs-lookup"><span data-stu-id="88479-103">Support parameterized calls of ER data sources of the Calculated field type</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="88479-104">I det här avsnittet beskrivs hur du kan utforma en data källa med elektronisk rapportering (ER) med hjälp av typen **beräknat fält**.</span><span class="sxs-lookup"><span data-stu-id="88479-104">This topic explains how you can design an Electronic reporting (ER) data source by using the **Calculated field** type.</span></span> <span data-ttu-id="88479-105">Den här datakällan kan innehålla ett ER-uttryck som vid körning kan kontrolleras av värdena i parameterargumenten som är konfigurerade i en bindning som anropar den här datakällan.</span><span class="sxs-lookup"><span data-stu-id="88479-105">This data source may contain an ER expression that, when executed, can be controlled by the values of the parameter arguments that are configured in a binding that calls this data source.</span></span> <span data-ttu-id="88479-106">Genom att konfigurera parametriserade anrop av en sådan datakälla kan du återanvända en enskild datakälla i många bindningar, vilket minskar det totala antalet datakällor som måste konfigureras i ER-modellmappningar eller ER-format.</span><span class="sxs-lookup"><span data-stu-id="88479-106">By configuring parameterized calls of such a data source, you can reuse a single data source in many bindings, which reduces the total number of data sources that must be configured in ER model mappings or ER formats.</span></span> <span data-ttu-id="88479-107">Det förenklar också den konfigurerade ER-komponenten, vilket minskar underhållskostnaderna och kostnaderna för användning av andra konsumenter.</span><span class="sxs-lookup"><span data-stu-id="88479-107">It also simplifies the configured ER component, which reduces the maintenance costs and the cost of use by other consumers.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="88479-108">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="88479-108">Prerequisites</span></span>
<span data-ttu-id="88479-109">För att slutföra exemplet i det här avsnittet måste du ha följande åtkomst:</span><span class="sxs-lookup"><span data-stu-id="88479-109">To complete the examples in this topic, you must have the following access:</span></span>

- <span data-ttu-id="88479-110">Åtkomst till en av dessa roller:</span><span class="sxs-lookup"><span data-stu-id="88479-110">Access to one of these roles:</span></span>

    - <span data-ttu-id="88479-111">Utvecklare för elektronisk rapportering</span><span class="sxs-lookup"><span data-stu-id="88479-111">Electronic reporting developer</span></span>
    - <span data-ttu-id="88479-112">Konsult för funktionen för elektronisk rapportering</span><span class="sxs-lookup"><span data-stu-id="88479-112">Electronic reporting functional consultant</span></span>
    - <span data-ttu-id="88479-113">Systemadministratör</span><span class="sxs-lookup"><span data-stu-id="88479-113">System administrator</span></span>

- <span data-ttu-id="88479-114">Åtkomst till Regulatory Configuration Services (RCS) som har etablerats för samma innehavare som Finance and Operations för en av följande roller:</span><span class="sxs-lookup"><span data-stu-id="88479-114">Access to Regulatory Configuration Services (RCS) that have been provisioned for the same tenant as Finance and Operations for one of the following roles:</span></span>

    - <span data-ttu-id="88479-115">Utvecklare för elektronisk rapportering</span><span class="sxs-lookup"><span data-stu-id="88479-115">Electronic reporting developer</span></span>
    - <span data-ttu-id="88479-116">Konsult för funktionen för elektronisk rapportering</span><span class="sxs-lookup"><span data-stu-id="88479-116">Electronic reporting functional consultant</span></span>
    - <span data-ttu-id="88479-117">Systemadministratör</span><span class="sxs-lookup"><span data-stu-id="88479-117">System administrator</span></span>

<span data-ttu-id="88479-118">Du måste också hämta följande filer och lagra dem lokalt.</span><span class="sxs-lookup"><span data-stu-id="88479-118">You must also download and locally store the following files.</span></span>

| <span data-ttu-id="88479-119">**Innehåll**</span><span class="sxs-lookup"><span data-stu-id="88479-119">**Content**</span></span>                           | <span data-ttu-id="88479-120">**Filnamn**</span><span class="sxs-lookup"><span data-stu-id="88479-120">**File name**</span></span>                                        |
|---------------------------------------|------------------------------------------------------|
| <span data-ttu-id="88479-121">Konfiguration av exempel på ER-datamodell.</span><span class="sxs-lookup"><span data-stu-id="88479-121">Sample ER data model configuration</span></span>    | [<span data-ttu-id="88479-122">Modell för att lära dig parameteranrop.version.1.xml</span><span class="sxs-lookup"><span data-stu-id="88479-122">Model to learn parameterized calls.version.1.xml</span></span>](https://mbs.microsoft.com/customersource/global/AX/downloads/hot-fixes/365optelecrepeg)     |
| <span data-ttu-id="88479-123">Konfiguration av exempel på ER-metadata.</span><span class="sxs-lookup"><span data-stu-id="88479-123">Sample ER metadata configuration</span></span>      | [<span data-ttu-id="88479-124">Metadata för att lära dig parameteranrop.version.1.xml</span><span class="sxs-lookup"><span data-stu-id="88479-124">Metadata to learn parameterized calls.version.1.xml</span></span>](https://mbs.microsoft.com/customersource/global/AX/downloads/hot-fixes/365optelecrepeg)  |
| <span data-ttu-id="88479-125">Konfiguration av exempel på ER-modellmappning</span><span class="sxs-lookup"><span data-stu-id="88479-125">Sample ER model mapping configuration</span></span> | [<span data-ttu-id="88479-126">Mappning för att lära dig parameteranrop.version.1.1.xml</span><span class="sxs-lookup"><span data-stu-id="88479-126">Mapping to learn parameterized calls.version.1.1.xml</span></span>](https://mbs.microsoft.com/customersource/global/AX/downloads/hot-fixes/365optelecrepeg) |
| <span data-ttu-id="88479-127">Konfiguration av exempel på ER-format.</span><span class="sxs-lookup"><span data-stu-id="88479-127">Sample ER format configuration</span></span>        | [<span data-ttu-id="88479-128">Format för att lära dig parameteranrop.version.1.1.xml</span><span class="sxs-lookup"><span data-stu-id="88479-128">Format to learn parameterized calls.version.1.1.xml</span></span>](https://mbs.microsoft.com/customersource/global/AX/downloads/hot-fixes/365optelecrepeg)  |

## <a name="sign-in-to-your-rcs-instance"></a><span data-ttu-id="88479-129">Logga in på RCS-instansen.</span><span class="sxs-lookup"><span data-stu-id="88479-129">Sign in to your RCS instance</span></span>
<span data-ttu-id="88479-130">I det här exemplet skapar du en konfiguration för exempelföretaget, Litware, Inc. Först, i RCS, måste du slutföra stegen i proceduren [Skapa en konfigurationsleverantör och markera den som aktiv](tasks/er-configuration-provider-mark-it-active-2016-11.md):</span><span class="sxs-lookup"><span data-stu-id="88479-130">In this example, you will create a configuration for the sample company, Litware, Inc. First, in RCS, you must complete the steps in the [Create configuration providers and mark them as active](tasks/er-configuration-provider-mark-it-active-2016-11.md) procedure:</span></span>

1. <span data-ttu-id="88479-131">Välj **elektronisk rapportering** på standardinstrumentpanelen.</span><span class="sxs-lookup"><span data-stu-id="88479-131">On the default dashboard, select **Electronic reporting**.</span></span>
2. <span data-ttu-id="88479-132">Välj **rapporteringskonfigurationer**.</span><span class="sxs-lookup"><span data-stu-id="88479-132">Select **Reporting configurations**.</span></span>
3. <span data-ttu-id="88479-133">Importera nedladdade konfigurationer till RCS i följande ordning: datamodell, metadata, modellmappning, format.</span><span class="sxs-lookup"><span data-stu-id="88479-133">Import the downloaded configurations to RCS in the following sequence: data model, metadata, model mapping, format.</span></span> <span data-ttu-id="88479-134">Utför följande steg för varje ER-konfiguration:</span><span class="sxs-lookup"><span data-stu-id="88479-134">Complete the following steps for each ER configuration:</span></span>

    1. <span data-ttu-id="88479-135">Välj **kurs**</span><span class="sxs-lookup"><span data-stu-id="88479-135">Select **Exchange.**</span></span>
    2. <span data-ttu-id="88479-136">Välj **Läs in från XML-fil**.</span><span class="sxs-lookup"><span data-stu-id="88479-136">Select **Load from XML file**.</span></span>
    3. <span data-ttu-id="88479-137">Välj **bläddra** och sedan den nödvändiga ER-konfigurationen i XML-format.</span><span class="sxs-lookup"><span data-stu-id="88479-137">Select **Browse**, and then select the required ER configuration in XML format.</span></span>
    4. <span data-ttu-id="88479-138">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="88479-138">Select **OK.**</span></span>

## <a name="review-the-provided-er-solution"></a><span data-ttu-id="88479-139">Granska den medföljande ER-lösningen</span><span class="sxs-lookup"><span data-stu-id="88479-139">Review the provided ER solution</span></span>

### <a name="review-model-mapping"></a><span data-ttu-id="88479-140">Granska modellmappning</span><span class="sxs-lookup"><span data-stu-id="88479-140">Review model mapping</span></span>

1. <span data-ttu-id="88479-141">I konfigurationsträdet expanderar du innehållet i objektet **modell för att lära dig parameteranrop**.</span><span class="sxs-lookup"><span data-stu-id="88479-141">In the configuration tree, expand the content of the **Model to learn parameterized calls** item.</span></span>
2. <span data-ttu-id="88479-142">Välj **Mappning för att lära dig parameteranrop**.</span><span class="sxs-lookup"><span data-stu-id="88479-142">Select **Mapping to learn parameterized calls**.</span></span>
3. <span data-ttu-id="88479-143">Välj **Designer**.</span><span class="sxs-lookup"><span data-stu-id="88479-143">Select **Designer**.</span></span>
4. <span data-ttu-id="88479-144">Välj **Designer**.</span><span class="sxs-lookup"><span data-stu-id="88479-144">Select **Designer**.</span></span>  
   
    <span data-ttu-id="88479-145">Den här ER-modellmappningen har utformats för att göra följande:</span><span class="sxs-lookup"><span data-stu-id="88479-145">This ER model mapping is designed to do the following:</span></span>

    - <span data-ttu-id="88479-146">Hämta listan över momskoder **(moms** datakälla) som finns i **TaxTable**-registret.</span><span class="sxs-lookup"><span data-stu-id="88479-146">Fetch the list of tax codes (**Tax** data source) residing in the **TaxTable** table.</span></span>
    - <span data-ttu-id="88479-147">Hämta listan över momstransaktioner **(Trans** datakälla) som finns i **TaxTrans**-registret.</span><span class="sxs-lookup"><span data-stu-id="88479-147">Fetch the list of tax transactions (**Trans** data source) residing in the **TaxTrans** table:</span></span>
    
        - <span data-ttu-id="88479-148">Gruppera listan över hämtade transaktioner (**Gr** datakälla) efter momskod.</span><span class="sxs-lookup"><span data-stu-id="88479-148">Group the list of fetched transactions (**Gr** data source) by tax code.</span></span>
        - <span data-ttu-id="88479-149">Beräkna för grupperade transaktioner efter aggregerade värden per momskod:</span><span class="sxs-lookup"><span data-stu-id="88479-149">Calculate for grouped transactions following aggregated values per tax code:</span></span>

            - <span data-ttu-id="88479-150">Summa av basvärde för moms.</span><span class="sxs-lookup"><span data-stu-id="88479-150">Sum of tax base values.</span></span>
            - <span data-ttu-id="88479-151">Summa av momsvärden.</span><span class="sxs-lookup"><span data-stu-id="88479-151">Sum of tax values.</span></span>
            - <span data-ttu-id="88479-152">Lägsta värde för tillämpad momssats.</span><span class="sxs-lookup"><span data-stu-id="88479-152">Minimum value of applied tax rate.</span></span>

    <span data-ttu-id="88479-153">Modellmappningen i den här konfigurationen implementerar basdatamodellen för alla ER-format som skapas för den här modellen och körs i Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="88479-153">The model mapping in this configuration implements the base data model for any of the ER formats created for this model and executed in Finance and Operations.</span></span> <span data-ttu-id="88479-154">Detta innebär att innehållet i datakällorna **Moms** och **Gr** visas för ER-format, t.ex. abstrakta datakällor.</span><span class="sxs-lookup"><span data-stu-id="88479-154">As a result, the content of the **Tax** and **Gr** data sources is exposed for ER formats such as abstract data sources.</span></span>

    ![Sidan modellmappningsdesigner med datakällorna Moms och Gr](media/er-calculated-field-type-01.png)

5.  <span data-ttu-id="88479-156">Stäng sidan **modellmappningsdesigner**.</span><span class="sxs-lookup"><span data-stu-id="88479-156">Close the **Model mapping designer** page.</span></span>
6.  <span data-ttu-id="88479-157">Stäng sidan **modellmappning**.</span><span class="sxs-lookup"><span data-stu-id="88479-157">Close the **Model mapping** page.</span></span>

### <a name="review-format"></a><span data-ttu-id="88479-158">Granska format</span><span class="sxs-lookup"><span data-stu-id="88479-158">Review format</span></span>

1. <span data-ttu-id="88479-159">I konfigurationsträdet expanderar du innehållet i objektet **modell för att lära dig parameteranrop**.</span><span class="sxs-lookup"><span data-stu-id="88479-159">In the configuration tree, expand the content of the **Model to learn parameterized calls** item.</span></span>
2. <span data-ttu-id="88479-160">Välj **Format för att lära dig parameteranrop**.</span><span class="sxs-lookup"><span data-stu-id="88479-160">Select **Format to learn parameterized calls**.</span></span>
3. <span data-ttu-id="88479-161">Välj **Designer**.</span><span class="sxs-lookup"><span data-stu-id="88479-161">Select **Designer**.</span></span> <span data-ttu-id="88479-162">Det här ER-formatet har utformats för att göra följande:</span><span class="sxs-lookup"><span data-stu-id="88479-162">This ER format is designed to do the following:</span></span>

    - <span data-ttu-id="88479-163">Generera en skattedeklaration i XML-format.</span><span class="sxs-lookup"><span data-stu-id="88479-163">Generate a tax statement in XML format.</span></span>
    - <span data-ttu-id="88479-164">Lägga fram följande beskattningsnivåer i momsrapporten: vanlig, reducerad och ingen.</span><span class="sxs-lookup"><span data-stu-id="88479-164">Present the following levels of taxation in the tax statement: regular, reduced, and none.</span></span>
    - <span data-ttu-id="88479-165">Presentera flera detaljer för varje beskattningsnivå, med olika antal detaljer på varje nivå.</span><span class="sxs-lookup"><span data-stu-id="88479-165">Present multiple details at each taxation level, having a different number of details in each level.</span></span>

    ![Formatdesignersida](media/er-calculated-field-type-02.png)

4. <span data-ttu-id="88479-167">Välj **mappning**.</span><span class="sxs-lookup"><span data-stu-id="88479-167">Select **Mapping**.</span></span>
5. <span data-ttu-id="88479-168">Expandera artiklarna **Modell**, **Data** och **Sammanfattning**.</span><span class="sxs-lookup"><span data-stu-id="88479-168">Expand the **Model**, **Data,** and **Summary** items.</span></span> 

    <span data-ttu-id="88479-169">Den beräknade fältet **Model.Data.Summary.Level** innehåller det uttryck som returnerar koden för beskattningsnivån (**normal**, **reducerad**, **ingen,** eller **annan**) som ett textvärde för alla momskoder som kan hämtas från datakällan **Model.Data.Summary** vid körningstillfället.</span><span class="sxs-lookup"><span data-stu-id="88479-169">The calculated field **Model.Data.Summary.Level** contains the expression that returns the code of the taxation level (**Regular**, **Reduced**, **None,** or **Other**) as a text value for any tax code that can be retrieved from the **Model.Data.Summary** data source at run time.</span></span>

    ![Sidan Formatera designer med information om datamodellen Modell för att lära sig parameteranrop](media/er-calculated-field-type-03.png)

6. <span data-ttu-id="88479-171">Expandera **Modell**. **Data2**-objektet.</span><span class="sxs-lookup"><span data-stu-id="88479-171">Expand the **Model**.**Data2** item.</span></span>
7. <span data-ttu-id="88479-172">Expandera **Modell**. **Data2.Summary2**-objektet.</span><span class="sxs-lookup"><span data-stu-id="88479-172">Expand the **Model**.**Data2.Summary2** item.</span></span>
   
    <span data-ttu-id="88479-173">Datakällan **Modell**.**Data2.Summary2** har konfigurerats för att gruppera datakällan **Model.Data.Summary**  transaktionsdetaljer per beskattningsnivå (returneras av **Model.Data.Summary.Level** beräknat fält) och beräkna aggregeringar.</span><span class="sxs-lookup"><span data-stu-id="88479-173">The **Model**.**Data2.Summary2** data source is configured to group the **Model.Data.Summary** data source transaction details by taxation level (returned by the **Model.Data.Summary.Level** calculated field) and compute the aggregations.</span></span>

    ![Sidan Formatera designer med information om datakällan Model.Data2.Summary2 data source](media/er-calculated-field-type-04.png)

8. <span data-ttu-id="88479-175">Granska beräknade fält **Modell**.**Data2.Level1**, **Modell**.**Data2.Level2** och **Modell**.**Data2.Level3.**</span><span class="sxs-lookup"><span data-stu-id="88479-175">Review the calculated fields **Model**.**Data2.Level1**, **Model**.**Data2.Level2**, and **Model**.**Data2.Level3.**</span></span> <span data-ttu-id="88479-176">De här beräknade fälten används för att filtrera **Modell**. **Data2. Summary2**-postlista och returnerar endast poster som representerar en viss beskattningsnivå.</span><span class="sxs-lookup"><span data-stu-id="88479-176">These calculated fields are used to filter the **Model**.**Data2.Summary2** records list and return only records that represent a particular taxation level.</span></span>
9. <span data-ttu-id="88479-177">Stäng sidan **Formatdesigner**.</span><span class="sxs-lookup"><span data-stu-id="88479-177">Close the **Format designer** page.</span></span>

## <a name="create-a-derived-format"></a><span data-ttu-id="88479-178">Skapa ett härlett format</span><span class="sxs-lookup"><span data-stu-id="88479-178">Create a derived format</span></span>
<span data-ttu-id="88479-179">Du kan förbättra det angivna formatet genom att lägga till ett beräknat fält för att filtrera den begärda skattenivån i stället för att använda befintliga tre fält: **Modell**.**Data2.Level1**, **Modell**.**Data2.Level2,** och **Modell**.**Data2.Level3**.</span><span class="sxs-lookup"><span data-stu-id="88479-179">You can improve the provided format by adding one calculated field to filter the required taxation level instead of using the existing three fields: **Model**.**Data2.Level1**, **Model**.**Data2.Level2,** and **Model**.**Data2.Level3**.</span></span> <span data-ttu-id="88479-180">Den obligatoriska skattenivån kan anges på platsen där det nya beräknade fältet ska anropas.</span><span class="sxs-lookup"><span data-stu-id="88479-180">The required taxation level can be specified in the location where this new calculated field will be called.</span></span>

1. <span data-ttu-id="88479-181">I konfigurationsträdet expanderar du innehållet i objektet **modell för att lära dig parameteranrop**.</span><span class="sxs-lookup"><span data-stu-id="88479-181">In the configuration tree, expand the content of the **Model to learn parameterized calls** item.</span></span>
2. <span data-ttu-id="88479-182">Välj **Format för att lära dig parameteranrop**.</span><span class="sxs-lookup"><span data-stu-id="88479-182">Select **Format to learn parameterized calls**.</span></span>
3. <span data-ttu-id="88479-183">Välj **Skapa konfiguration**.</span><span class="sxs-lookup"><span data-stu-id="88479-183">Select **Create configuration**.</span></span>
4. <span data-ttu-id="88479-184">Välj **Härled från namn: format om du vill lära dig parameteranrop, Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="88479-184">Select **Derive from Name: Format to learn parameterized calls, Microsoft**.</span></span>
5. <span data-ttu-id="88479-185">I fältet **namn** anger du **format för att lära parameteranrop (anpassad)**.</span><span class="sxs-lookup"><span data-stu-id="88479-185">In the **Name** field, enter **Format to learn parameterized calls (custom)**.</span></span>
6. <span data-ttu-id="88479-186">Välj **Skapa konfiguration**.</span><span class="sxs-lookup"><span data-stu-id="88479-186">Select **Create configuration.**</span></span>

## <a name="configure-a-parameterized-calculated-field-that-returns-a-list-of-records"></a><span data-ttu-id="88479-187">Konfigurera ett parameter beräknat fält som returnerar en lista med poster</span><span class="sxs-lookup"><span data-stu-id="88479-187">Configure a parameterized calculated field that returns a list of records</span></span>

### <a name="start-adding-a-new-calculated-field"></a><span data-ttu-id="88479-188">Börja lägga till ett nytt beräknat fält</span><span class="sxs-lookup"><span data-stu-id="88479-188">Start adding a new calculated field</span></span>

1. <span data-ttu-id="88479-189">Välj **Designer**.</span><span class="sxs-lookup"><span data-stu-id="88479-189">Select **Designer**.</span></span>
2. <span data-ttu-id="88479-190">Välj **expandera/komprimera** om du vill expandera alla formatobjekt.</span><span class="sxs-lookup"><span data-stu-id="88479-190">Select **Expand/collapse** to expand all format items.</span></span>
3. <span data-ttu-id="88479-191">Välj **mappning**.</span><span class="sxs-lookup"><span data-stu-id="88479-191">Select **Mapping**.</span></span>
4. <span data-ttu-id="88479-192">Expandera objektet **Modell**.</span><span class="sxs-lookup"><span data-stu-id="88479-192">Expand the **Model** item.</span></span>
5. <span data-ttu-id="88479-193">Välj objektet **Model.Data2**.</span><span class="sxs-lookup"><span data-stu-id="88479-193">Select the **Model.Data2** item.</span></span>
6. <span data-ttu-id="88479-194">Markera **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="88479-194">Select **Add**.</span></span>
7. <span data-ttu-id="88479-195">Välj **Funktioner\\Beräknat fält**.</span><span class="sxs-lookup"><span data-stu-id="88479-195">Select **Functions\\Calculated field**.</span></span>
8. <span data-ttu-id="88479-196">Skriv **Utdata** i fältet **Nivåer**.</span><span class="sxs-lookup"><span data-stu-id="88479-196">In the **Name** field, enter **Levels**.</span></span>
9. <span data-ttu-id="88479-197">Välj **Redigera recept**.</span><span class="sxs-lookup"><span data-stu-id="88479-197">Select **Edit formula**.</span></span>

### <a name="define-a-parameter-for-adding-a-calculated-field"></a><span data-ttu-id="88479-198">Definiera en parameter för att lägga till ett beräknat fält</span><span class="sxs-lookup"><span data-stu-id="88479-198">Define a parameter for adding a calculated field</span></span>

1. <span data-ttu-id="88479-199">Välj **parametrar**.</span><span class="sxs-lookup"><span data-stu-id="88479-199">Select **Parameters**.</span></span>
2. <span data-ttu-id="88479-200">Välj **Ny**.</span><span class="sxs-lookup"><span data-stu-id="88479-200">Select **New**.</span></span>
3. <span data-ttu-id="88479-201">I fältet **Namn** anger du **beskattningsnivå**.</span><span class="sxs-lookup"><span data-stu-id="88479-201">In the **Name** field, enter **Taxation Level**.</span></span>
4. <span data-ttu-id="88479-202">Välj **Typ** i fältet **Artikeltyp**.</span><span class="sxs-lookup"><span data-stu-id="88479-202">In the **Type** field, select **String**.</span></span>

    <span data-ttu-id="88479-203">Endast primitiva datatyper kan användas för att ange typen för parameterns argument.</span><span class="sxs-lookup"><span data-stu-id="88479-203">Only primitive data types can be used to specify the type of the parameter’s argument.</span></span> <span data-ttu-id="88479-204">Därför kan typerna **postlist**, **post** och **fasttext** inte användas för detta syfte.</span><span class="sxs-lookup"><span data-stu-id="88479-204">Therefore, **Record list**, **Record**, and **Enum** types cannot be used for this purpose.</span></span>

    <span data-ttu-id="88479-205">Det maximala antalet parametrar som kan anges för ett enskilt beräknat fält är 8.</span><span class="sxs-lookup"><span data-stu-id="88479-205">The maximum number of parameters that can be specified for a single calculated field is 8.</span></span>

    ![Lista över parameterdatakällor](media/er-calculated-field-type-05.png)

5. <span data-ttu-id="88479-207">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="88479-207">Select **OK**.</span></span>

<span data-ttu-id="88479-208">Genom att lägga till den här parametern anger du det villkor som måste finnas på platser för att det här beräknade fältet ska kunna anropas.</span><span class="sxs-lookup"><span data-stu-id="88479-208">By adding this parameter, you specify the condition that must be in place to call this calculated field.</span></span> <span data-ttu-id="88479-209">När du ringer detta beräknade fält måste du ange argumentet för parametern **beskattningsnivå** som ett värde med formatet **sträng**.</span><span class="sxs-lookup"><span data-stu-id="88479-209">When you call this calculated field, you need to specify the argument of the **Taxation Level** parameter as a value with **String** format.</span></span>

   <span data-ttu-id="88479-210">Se till att du bara definierar parametrar för de beräknade fält som finns i en behållare (antingen **postlist**, **post** eller **behållare**).</span><span class="sxs-lookup"><span data-stu-id="88479-210">Make sure that you define parameters only for those calculated fields that reside in a container (either **Record list**, **Record**, or **Container**).</span></span>

   <span data-ttu-id="88479-211">Den konfigurerade parametern finns i listan över datakällor för det här beräknade fältet.</span><span class="sxs-lookup"><span data-stu-id="88479-211">The configured parameter is available in the list of data sources for this calculated field.</span></span> <span data-ttu-id="88479-212">Du kan lägga till parametern i det konfigurerade uttrycket genom att välja **Lägg till datakälla**.</span><span class="sxs-lookup"><span data-stu-id="88479-212">You can add the parameter to the configured expression by selecting **Add data source**.</span></span>

   ![Datakällfält](media/er-calculated-field-type-06.png)

### <a name="define-an-expression-for-adding-a-calculated-field"></a><span data-ttu-id="88479-214">Definiera ett uttryck för att lägga till ett beräknat fält</span><span class="sxs-lookup"><span data-stu-id="88479-214">Define an expression for adding a calculated field</span></span>

1. <span data-ttu-id="88479-215">I fältet **Formel**, ange:</span><span class="sxs-lookup"><span data-stu-id="88479-215">In the **Formula** field, enter:</span></span> 

    <span data-ttu-id="88479-216">**WHERE(\@.Summary2, \@.Summary2.grouped.Level =**</span><span class="sxs-lookup"><span data-stu-id="88479-216">**WHERE(\@.Summary2, \@.Summary2.grouped.Level =**</span></span>
    
2. <span data-ttu-id="88479-217">Välj parametern **skattenivå** i listan över datakällor.</span><span class="sxs-lookup"><span data-stu-id="88479-217">Select the **Taxation Level** parameter in the list of data sources.</span></span>
3. <span data-ttu-id="88479-218">Välj **Lägg till datakälla**.</span><span class="sxs-lookup"><span data-stu-id="88479-218">Select **Add data source**.</span></span>
4. <span data-ttu-id="88479-219">I fältet **formel** slutför uttryck:</span><span class="sxs-lookup"><span data-stu-id="88479-219">In the **Formula** field, finalize the expression as:</span></span>  

    <span data-ttu-id="88479-220">**WHERE(\@.Summary2, \@.Summary2.grouped.Level = 'Taxation Level')**</span><span class="sxs-lookup"><span data-stu-id="88479-220">**WHERE(\@.Summary2, \@.Summary2.grouped.Level = 'Taxation Level')**</span></span>

5. <span data-ttu-id="88479-221">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="88479-221">Select **Save**.</span></span>

    ![Information om datakälla](media/er-calculated-field-type-07.png)

6. <span data-ttu-id="88479-223">Stäng sidan **Formeldesigner**.</span><span class="sxs-lookup"><span data-stu-id="88479-223">Close the **Formula designer** page.</span></span>

### <a name="finish-adding-a-new-calculated-field"></a><span data-ttu-id="88479-224">Sluta lägga till ett nytt beräknat fält</span><span class="sxs-lookup"><span data-stu-id="88479-224">Finish adding a new calculated field</span></span>

- <span data-ttu-id="88479-225">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="88479-225">Select **OK**.</span></span>

<span data-ttu-id="88479-226">På sidan **formatdesigner** kräver det konfigurerade parametriserade beräknade fältet **nivåer** argumentet **sträng**.</span><span class="sxs-lookup"><span data-stu-id="88479-226">On the **Format designer** page, the configured parameterized calculated field **Levels** requires a **String** argument.</span></span>

![Utökad lista över beräknade fältnivåer](media/er-calculated-field-type-08.png)

### <a name="use-the-configured-calculated-field-for-binding-format-elements"></a><span data-ttu-id="88479-228">Använd det konfigurerade beräknade fältet för bindningsformatelement</span><span class="sxs-lookup"><span data-stu-id="88479-228">Use the configured calculated field for binding format elements</span></span>

1. <span data-ttu-id="88479-229">Välj **Model.Data2.Levels** för att välja det konfigurerade beräknade fältet.</span><span class="sxs-lookup"><span data-stu-id="88479-229">Select **Model.Data2.Levels** to select the configured calculated field.</span></span>
2. <span data-ttu-id="88479-230">Välj formatelementet **Statement.Taxation.Regular**.</span><span class="sxs-lookup"><span data-stu-id="88479-230">Select the **Statement.Taxation.Regular** format element.</span></span>
3. <span data-ttu-id="88479-231">Välj **bind**.</span><span class="sxs-lookup"><span data-stu-id="88479-231">Select **Bind**.</span></span>
4. <span data-ttu-id="88479-232">Välj **ja** om du vill ersätta den för tillfället använda datakällan, **level1**, med den nya datakällan, **nivåer** i alla kapslade formatelement i det valda formatelementet.</span><span class="sxs-lookup"><span data-stu-id="88479-232">Select **Yes** to confirm the replacement of the currently used data source, **Level1**, by the new data source, **Levels**, in all nested format elements of the selected format element.</span></span>

    <span data-ttu-id="88479-233">Tillämpad bindning har byggts som ett anrop till det parametriserade beräknade fältet.</span><span class="sxs-lookup"><span data-stu-id="88479-233">Applied binding has been built as a call of the parameterized calculated field.</span></span> <span data-ttu-id="88479-234">Som standard används namnet på det bundna formatelementet som ett argument för parametriserade beräknat fält under följande förhållanden:</span><span class="sxs-lookup"><span data-stu-id="88479-234">By default, the name of the bound format element is used as an argument for parameterized calculated field under the following conditions:</span></span>

      - <span data-ttu-id="88479-235">Det beräknade fältet konfigureras för att använda en enda parameter.</span><span class="sxs-lookup"><span data-stu-id="88479-235">The calculated field is configured to use a single parameter.</span></span>
      - <span data-ttu-id="88479-236">Datatypen för den här parametern definieras som **sträng**.</span><span class="sxs-lookup"><span data-stu-id="88479-236">The data type of this parameter is defined as **String**.</span></span>

    <span data-ttu-id="88479-237">När namnet på det bundna formatelementet är tomt används namnet på datakällan för det här elementet i tillämpad bindning.</span><span class="sxs-lookup"><span data-stu-id="88479-237">When the name of the bound format element is blank, the data source name of this element is used in applied binding.</span></span>

5. <span data-ttu-id="88479-238">Välj formatelementet **Statement.Taxation.Reduced**.</span><span class="sxs-lookup"><span data-stu-id="88479-238">Select the **Statement.Taxation.Reduced** format element.</span></span>
6. <span data-ttu-id="88479-239">Välj **bind**.</span><span class="sxs-lookup"><span data-stu-id="88479-239">Select **Bind**.</span></span>
7. <span data-ttu-id="88479-240">Välj **ja** om du vill ersätta den för tillfället använda datakällan, **level2**, med den nya datakällan, **nivåer** i alla kapslade formatelement under det valda formatelementet.</span><span class="sxs-lookup"><span data-stu-id="88479-240">Select **Yes** to confirm the replacement of the currently used data source, **Level2**, by the new data source, **Levels**, in all nested format elements under the selected format element.</span></span>
8. <span data-ttu-id="88479-241">Välj formatelementet **Statement.Taxation.None**.</span><span class="sxs-lookup"><span data-stu-id="88479-241">Select the **Statement.Taxation.None** format element.</span></span>
9. <span data-ttu-id="88479-242">Välj **bind**.</span><span class="sxs-lookup"><span data-stu-id="88479-242">Select **Bind**.</span></span>
10. <span data-ttu-id="88479-243">Välj **ja** om du vill ersätta den för tillfället använda datakällan, **level3**, med den nya datakällan, **nivåer** i alla kapslade formatelement under det valda formatelementet.</span><span class="sxs-lookup"><span data-stu-id="88479-243">Select **Yes** to confirm the replacement of the currently used data source, **Level3**, by the new data source, **Levels**, in all nested format elements under the selected format element.</span></span>

   <span data-ttu-id="88479-244">Om du anger argumentet för det parametriserade beräknade fältet för XML-elementet som representerar beskattningsnivån (t.ex. **Model.Data2.Levels("Reduced")** som ett textvärde), behöver du inte göra samma sak för kapslade XML-attribut, dvs. bindningar ärver automatiskt värdet för argumentet som definieras på den överordnade nivån (**Model.Data2.Levels.aggregated.Base**, inte **Model.Data2.Levels("Reduced").aggregated.Base**).</span><span class="sxs-lookup"><span data-stu-id="88479-244">When you specify the argument of the parameterized calculated field for the XML element representing taxation level (for example, **Model.Data2.Levels("Reduced")** as a text value), you don’t need to do the same for nested XML attributes—their bindings will automatically inherit the value of the argument defined on the parent level (**Model.Data2.Levels.aggregated.Base**, not **Model.Data2.Levels("Reduced").aggregated.Base**).</span></span>

<span data-ttu-id="88479-245">Återkommande anrop av valfritt parametriserat beräknat fält stöds inte.</span><span class="sxs-lookup"><span data-stu-id="88479-245">Recurrent calls of any parameterized calculated field are not supported.</span></span>

<span data-ttu-id="88479-246">Du kan välja **Redigera formel** och ändra det argument som används som standard det parametiserade beräknade fältet i den valda bindningen.</span><span class="sxs-lookup"><span data-stu-id="88479-246">You can select **Edit formula**, and change the applied-by-default argument of the parameterized calculated field in the selected binding.</span></span> <span data-ttu-id="88479-247">Om detta argument saknas kan det orsaka fel under körningen och användarna informeras om en sådan situation när det aktuella formatet valideras.</span><span class="sxs-lookup"><span data-stu-id="88479-247">If this argument is missing, it can cause errors at run time — users are informed about such a situation when the current format is validated.</span></span>

![Varningsmeddelande för validering](media/er-calculated-field-type-10.png)

## <a name="configure-a-parameterized-calculated-field-to-return-a-record"></a><span data-ttu-id="88479-249">Konfigurera ett parameter beräknat fält som returnera en post</span><span class="sxs-lookup"><span data-stu-id="88479-249">Configure a parameterized calculated field to return a record</span></span>
<span data-ttu-id="88479-250">När ett parametiserat beräknat fält returnerar en post måste du stödja bindningar av enskilda fält i den här posten för att kunna formatera element.</span><span class="sxs-lookup"><span data-stu-id="88479-250">When a parameterized calculated field returns a record, you need to support binding of individual fields of this record to format elements.</span></span> <span data-ttu-id="88479-251">I sådana fall kommer det inte att finnas någon överordnad bindning som innehåller värdet för ett argument för anrop av ett parameteriserat beräknat fält, det här värdet måste definieras i bindningen av en enskild posts fält.</span><span class="sxs-lookup"><span data-stu-id="88479-251">In such cases there will be no parent binding that contains the value of an argument to call a parameterized calculated field — this value must be defined in the binding of a single record’s field.</span></span>

### <a name="start-adding-a-new-calculated-field"></a><span data-ttu-id="88479-252">Börja lägga till ett nytt beräknat fält</span><span class="sxs-lookup"><span data-stu-id="88479-252">Start adding a new calculated field</span></span>

1. <span data-ttu-id="88479-253">Välj objektet **Model.Data2**.</span><span class="sxs-lookup"><span data-stu-id="88479-253">Select the **Model.Data2** item.</span></span>
2. <span data-ttu-id="88479-254">Markera **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="88479-254">Select **Add**.</span></span>
3. <span data-ttu-id="88479-255">Välj **Funktioner\\Beräknat fält**.</span><span class="sxs-lookup"><span data-stu-id="88479-255">Select **Functions\\Calculated field**.</span></span>
4. <span data-ttu-id="88479-256">Skriv **Dokument** i fältet **LevelRecord**.</span><span class="sxs-lookup"><span data-stu-id="88479-256">In the **Name** field, enter **LevelRecord**.</span></span>
5. <span data-ttu-id="88479-257">Välj **Redigera recept**.</span><span class="sxs-lookup"><span data-stu-id="88479-257">Select **Edit formula**.</span></span>

### <a name="define-a-parameter-for-adding-a-calculated-field"></a><span data-ttu-id="88479-258">Definiera en parameter för att lägga till ett beräknat fält</span><span class="sxs-lookup"><span data-stu-id="88479-258">Define a parameter for adding a calculated field</span></span>

1. <span data-ttu-id="88479-259">Välj **parametrar**.</span><span class="sxs-lookup"><span data-stu-id="88479-259">Select **Parameters**.</span></span>
2. <span data-ttu-id="88479-260">Välj **Ny**.</span><span class="sxs-lookup"><span data-stu-id="88479-260">Select **New**.</span></span>
3. <span data-ttu-id="88479-261">I fältet **Namn** anger du **beskattningsnivå**.</span><span class="sxs-lookup"><span data-stu-id="88479-261">In the **Name** field, enter **Taxation Level**.</span></span>
4. <span data-ttu-id="88479-262">Välj **Typ** i fältet **Artikeltyp**.</span><span class="sxs-lookup"><span data-stu-id="88479-262">In the **Type** field, select **String**.</span></span>
5. <span data-ttu-id="88479-263">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="88479-263">Select **OK**.</span></span>

### <a name="define-an-expression-for-adding-a-calculated-field"></a><span data-ttu-id="88479-264">Definiera ett uttryck för att lägga till ett beräknat fält</span><span class="sxs-lookup"><span data-stu-id="88479-264">Define an expression for adding a calculated field</span></span>

1. <span data-ttu-id="88479-265">I fältet **formel** anger du följande:</span><span class="sxs-lookup"><span data-stu-id="88479-265">In the **Formula** field, enter the following:</span></span>  
    
    <span data-ttu-id="88479-266">**FIRSTORNULL(\@.Levels(**</span><span class="sxs-lookup"><span data-stu-id="88479-266">**FIRSTORNULL(\@.Levels(**</span></span>

2. <span data-ttu-id="88479-267">Välj parametern **skattenivå**.</span><span class="sxs-lookup"><span data-stu-id="88479-267">Select the **Taxation Level** parameter.</span></span>
3. <span data-ttu-id="88479-268">Välj **Lägg till datakälla**.</span><span class="sxs-lookup"><span data-stu-id="88479-268">Select **Add data source**.</span></span>
4. <span data-ttu-id="88479-269">I fältet **formel** lägger du till **"momsnivå"))** till det som du angav i steg 1 för att färdigställa uttrycket till:</span><span class="sxs-lookup"><span data-stu-id="88479-269">In the **Formula** field, append **'Taxation Level'))** to what you entered in Step 1 to finalize the expression to:</span></span>  
    
    <span data-ttu-id="88479-270">**FIRSTORNULL(\@.Levels('Taxation Level'))**</span><span class="sxs-lookup"><span data-stu-id="88479-270">**FIRSTORNULL(\@.Levels('Taxation Level'))**</span></span>

5. <span data-ttu-id="88479-271">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="88479-271">Select **Save**.</span></span>
6. <span data-ttu-id="88479-272">Stäng sidan **Formeldesigner**.</span><span class="sxs-lookup"><span data-stu-id="88479-272">Close **the Formula designer** page.</span></span>

### <a name="finish-adding-a-new-calculated-field"></a><span data-ttu-id="88479-273">Sluta lägga till ett nytt beräknat fält</span><span class="sxs-lookup"><span data-stu-id="88479-273">Finish adding a new calculated field</span></span>

-   <span data-ttu-id="88479-274">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="88479-274">Select **OK**.</span></span>

### <a name="use-the-configured-calculated-field-to-bind-format-elements"></a><span data-ttu-id="88479-275">Använd det konfigurerade beräknade fältet för bindningsformatelement</span><span class="sxs-lookup"><span data-stu-id="88479-275">Use the configured calculated field to bind format elements</span></span>

1. <span data-ttu-id="88479-276">Expandera **Model.Data2.LevelRecord** för att välja det konfigurerade beräknade fältet.</span><span class="sxs-lookup"><span data-stu-id="88479-276">Expand **Model.Data2.LevelRecord** to select the configured calculated field.</span></span>
2. <span data-ttu-id="88479-277">Expandera behållaren **Model.Data2.LevelRecord.aggregated** för att välja det konfigurerade beräknade fältet.</span><span class="sxs-lookup"><span data-stu-id="88479-277">Expand the **Model.Data2.LevelRecord.aggregated** container of the configured calculated field.</span></span>
3. <span data-ttu-id="88479-278">Markera fältet **Model.Data2.LevelRecord.aggregated.Base**.</span><span class="sxs-lookup"><span data-stu-id="88479-278">Select the **Model.Data2.LevelRecord.aggregated.Base** field.</span></span>
4. <span data-ttu-id="88479-279">Välj formatelementet **Statement.Taxation.None**.</span><span class="sxs-lookup"><span data-stu-id="88479-279">Select the **Statement.Taxation.None** format element.</span></span>
5. <span data-ttu-id="88479-280">Välj **Avbind**.</span><span class="sxs-lookup"><span data-stu-id="88479-280">Select **Unbind**.</span></span>
6. <span data-ttu-id="88479-281">Välj formatelementet **Statement.Taxation.None.Base**.</span><span class="sxs-lookup"><span data-stu-id="88479-281">Select the **Statement.Taxation.None.Base** format element.</span></span>
7. <span data-ttu-id="88479-282">Välj **bind**.</span><span class="sxs-lookup"><span data-stu-id="88479-282">Select **Bind**.</span></span>
8. <span data-ttu-id="88479-283">Välj **Redigera recept**.</span><span class="sxs-lookup"><span data-stu-id="88479-283">Select **Edit formula**.</span></span>
9. <span data-ttu-id="88479-284">Ändra uttrycket till **Model.Data2.LevelRecord("None").aggregated.Base**.</span><span class="sxs-lookup"><span data-stu-id="88479-284">Change the expression to **Model.Data2.LevelRecord("None").aggregated.Base**.</span></span>

![Uppdaterat uttryck](media/er-calculated-field-type-11.png)

## <a name="remove-calculated-fields-that-are-not-used"></a><span data-ttu-id="88479-286">Ta bort beräknade fält som inte används</span><span class="sxs-lookup"><span data-stu-id="88479-286">Remove calculated fields that are not used</span></span>

1. <span data-ttu-id="88479-287">Välj **Model.Data2.Level1**.</span><span class="sxs-lookup"><span data-stu-id="88479-287">Select **Model.Data2.Level1**.</span></span>
2. <span data-ttu-id="88479-288">Välj **Ta bort**.</span><span class="sxs-lookup"><span data-stu-id="88479-288">Select **Delete**.</span></span>
3. <span data-ttu-id="88479-289">Välj **Model.Data2.Level2**.</span><span class="sxs-lookup"><span data-stu-id="88479-289">Select **Model.Data2.Level2**.</span></span>
4. <span data-ttu-id="88479-290">Välj **Ta bort**.</span><span class="sxs-lookup"><span data-stu-id="88479-290">Select **Delete**.</span></span>
5. <span data-ttu-id="88479-291">Välj **Model.Data2.Level3**.</span><span class="sxs-lookup"><span data-stu-id="88479-291">Select **Model.Data2.Level3**.</span></span>
6. <span data-ttu-id="88479-292">Välj **Ta bort**.</span><span class="sxs-lookup"><span data-stu-id="88479-292">Select **Delete**.</span></span>
7. <span data-ttu-id="88479-293">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="88479-293">Select **Save**.</span></span>

  > [!NOTE]
  > <span data-ttu-id="88479-294">Du återanvänder samma beräknade fält **Model.Data2.Levels** flera gånger i formatbindningar.</span><span class="sxs-lookup"><span data-stu-id="88479-294">You reused the same calculated field **Model.Data2.Levels** several times in format bindings.</span></span> <span data-ttu-id="88479-295">Det är mycket enklare att använda och underhålla ett enda beräknat fält i stället för att göra detta för flera likartade fält.</span><span class="sxs-lookup"><span data-stu-id="88479-295">It is much easier to use and maintain a single calculated field instead of doing this for multiple similar fields.</span></span>

8. <span data-ttu-id="88479-296">Stäng sidan **Formatdesigner**.</span><span class="sxs-lookup"><span data-stu-id="88479-296">Close the **Format designer** page.</span></span>

## <a name="complete-adjusted-version-of-a-derived-format"></a><span data-ttu-id="88479-297">Slutför justerad version av ett härlett format</span><span class="sxs-lookup"><span data-stu-id="88479-297">Complete adjusted version of a derived format</span></span>

1. <span data-ttu-id="88479-298">På snabbfliken **versioner** väljer du **ändra status**.</span><span class="sxs-lookup"><span data-stu-id="88479-298">In the **Versions** FastTab, select **Change status**.</span></span>
2. <span data-ttu-id="88479-299">Välj **Slutför**.</span><span class="sxs-lookup"><span data-stu-id="88479-299">Select **Complete**.</span></span>

## <a name="export-completed-version-of-a-derived-format"></a><span data-ttu-id="88479-300">Exportera slutförd justerad version av ett härlett format</span><span class="sxs-lookup"><span data-stu-id="88479-300">Export completed version of a derived format</span></span>

1. <span data-ttu-id="88479-301">Välj formatet **format om du vill läsa parametriserade anrop (anpassat)** i konfigurationsträdet.</span><span class="sxs-lookup"><span data-stu-id="88479-301">Select **Format to learn parameterized calls (custom)** format in the configurations tree.</span></span>
2. <span data-ttu-id="88479-302">På snabbfliken **Versioner**, välj slutförd version 1.1.1.</span><span class="sxs-lookup"><span data-stu-id="88479-302">In the **Versions** FastTab, select the completed version 1.1.1.</span></span>
3. <span data-ttu-id="88479-303">Välj **kurs**</span><span class="sxs-lookup"><span data-stu-id="88479-303">Select **Exchange**.</span></span>
4. <span data-ttu-id="88479-304">Välj **Exportera som XML-fil**.</span><span class="sxs-lookup"><span data-stu-id="88479-304">Select **Export as XML file**.</span></span>
5. <span data-ttu-id="88479-305">Lagra den hämtade konfigurationen lokalt i XML-format.</span><span class="sxs-lookup"><span data-stu-id="88479-305">Store the downloaded configuration locally, in XML format.</span></span>

## <a name="test-er-formats"></a><span data-ttu-id="88479-306">Testa ER-format</span><span class="sxs-lookup"><span data-stu-id="88479-306">Test ER formats</span></span> 
<span data-ttu-id="88479-307">Du kan köra de ursprungliga och de förbättrade ER-formaten för att säkerställa att konfigurerade parameterbaserade beräknade fält fungerar som de ska.</span><span class="sxs-lookup"><span data-stu-id="88479-307">You can run the initial and improved ER formats to make sure that configured parameterized calculated fields work properly.</span></span>

### <a name="import-er-configurations"></a><span data-ttu-id="88479-308">Importera ER-konfigurationer</span><span class="sxs-lookup"><span data-stu-id="88479-308">Import ER configurations</span></span>
<span data-ttu-id="88479-309">Du kan importera granskade konfigurationer från RCS med hjälp av ER-databasen för **RCS**-typen.</span><span class="sxs-lookup"><span data-stu-id="88479-309">You can import reviewed configurations from RCS by using the ER repository of the **RCS** type.</span></span> <span data-ttu-id="88479-310">Om du redan gick igenom stegen i avsnittet [Importera konfigurationer för elektronisk rapportering (ER) från Regulatory Configuration Services (RCS)](rcs-download-configurations.md), använder du den konfigurerade återställningsdatabasen för att importera konfigurationer som beskrivs tidigare i det här avsnittet till din miljö.</span><span class="sxs-lookup"><span data-stu-id="88479-310">If you already went through the steps in the topic, [Import Electronic reporting (ER) configurations from Regulatory Configuration Services (RCS)](rcs-download-configurations.md), use the configured ER repository to import configurations discussed earlier in this topic to your environment.</span></span> <span data-ttu-id="88479-311">Annars följer du dessa steg:</span><span class="sxs-lookup"><span data-stu-id="88479-311">Otherwise, follow these steps:</span></span>

1. <span data-ttu-id="88479-312">Markera företaget **DEMF** och välj sedan **elektronisk rapportering** på standardinstrumentpanelen.</span><span class="sxs-lookup"><span data-stu-id="88479-312">Select the **DEMF** company and on the default dashboard, select **Electronic reporting**.</span></span>
2. <span data-ttu-id="88479-313">Välj **rapporteringskonfigurationer**.</span><span class="sxs-lookup"><span data-stu-id="88479-313">Select **Reporting configurations**.</span></span>
3. <span data-ttu-id="88479-314">Importera konfigurationer från Microsoft Download Center i följande ordning: datamodell, modellmappning, format.</span><span class="sxs-lookup"><span data-stu-id="88479-314">Import the configurations from Microsoft Download Center in the following sequence: data model, model mapping, format.</span></span> <span data-ttu-id="88479-315">Utför följande steg för varje ER-konfiguration:</span><span class="sxs-lookup"><span data-stu-id="88479-315">Complete the following steps for each ER configuration:</span></span>

    1. <span data-ttu-id="88479-316">Välj **kurs**</span><span class="sxs-lookup"><span data-stu-id="88479-316">Select **Exchange.**</span></span>
    2. <span data-ttu-id="88479-317">Välj **Läs in från XML-fil**.</span><span class="sxs-lookup"><span data-stu-id="88479-317">Select **Load from XML file**.</span></span>
    3. <span data-ttu-id="88479-318">Välj **bläddra** och sedan den nödvändiga ER-konfigurationen i XML-format.</span><span class="sxs-lookup"><span data-stu-id="88479-318">Select **Browse** to select the required ER configuration in XML format.</span></span>
    4. <span data-ttu-id="88479-319">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="88479-319">Select **OK**.</span></span>

4. <span data-ttu-id="88479-320">Importera exporterade från RCS slutförd version 1.1.1 av formatet **Format för att lära dig parameteranrop**:</span><span class="sxs-lookup"><span data-stu-id="88479-320">Import the exported from RCS completed version 1.1.1 of the **Format to learn parameterized calls (custom)** format:</span></span>

    1. <span data-ttu-id="88479-321">Välj **kurs**</span><span class="sxs-lookup"><span data-stu-id="88479-321">Select **Exchange.**</span></span>
    2. <span data-ttu-id="88479-322">Välj **Läs in från XML-fil**.</span><span class="sxs-lookup"><span data-stu-id="88479-322">Select **Load from XML file**.</span></span>
    3. <span data-ttu-id="88479-323">Välj **bläddra** om du vill välja den lokalt lagrade filen **Format för att lära dig parameteranrop (anpassade)** i XML-format.</span><span class="sxs-lookup"><span data-stu-id="88479-323">Select **Browse** to select the locally stored **Format to learn parameterized calls (custom)** file in XML format.</span></span>
    4. <span data-ttu-id="88479-324">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="88479-324">Select **OK**.</span></span>

### <a name="run-er-formats"></a><span data-ttu-id="88479-325">Kör ER-format</span><span class="sxs-lookup"><span data-stu-id="88479-325">Run ER formats</span></span>

1. <span data-ttu-id="88479-326">I konfigurationsträdet expanderar du innehållet i objektet **modell för att lära dig parameteranrop**.</span><span class="sxs-lookup"><span data-stu-id="88479-326">In the configuration tree, expand the content of the **Model to learn parameterized calls** item.</span></span>
2. <span data-ttu-id="88479-327">Välj **Format för att lära dig parameteranrop**.</span><span class="sxs-lookup"><span data-stu-id="88479-327">Select **Format to learn parameterized calls**.</span></span>
3. <span data-ttu-id="88479-328">Välj **kör** på menyfliken högst upp.</span><span class="sxs-lookup"><span data-stu-id="88479-328">Select **Run** on the top-most ribbon.</span></span>
4. <span data-ttu-id="88479-329">Spara de lokalt genererade utdata.</span><span class="sxs-lookup"><span data-stu-id="88479-329">Save the locally generated output.</span></span>
5. <span data-ttu-id="88479-330">Välj objektet **format för att lära sig mer parameteranrop (anpassat**).</span><span class="sxs-lookup"><span data-stu-id="88479-330">Select the **Format to learn parameterized calls (custom)** item.</span></span>
6. <span data-ttu-id="88479-331">Välj **kör** på menyfliken högst upp.</span><span class="sxs-lookup"><span data-stu-id="88479-331">Select **Run** on the top-most ribbon.</span></span>
7. <span data-ttu-id="88479-332">Spara genererade utdata lokalt.</span><span class="sxs-lookup"><span data-stu-id="88479-332">Save the generated output locally.</span></span> 
8. <span data-ttu-id="88479-333">Jämför innehållet i de genererade utflödena.</span><span class="sxs-lookup"><span data-stu-id="88479-333">Compare the contents of the generated outputs.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="88479-334">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="88479-334">Additional resources</span></span>

- [<span data-ttu-id="88479-335">Formeldesigner i elektronisk rapportering (ER)</span><span class="sxs-lookup"><span data-stu-id="88479-335">Formula designer in Electronic reporting (ER)</span></span>](general-electronic-reporting-formula-designer.md)
- [<span data-ttu-id="88479-336">Förbättra prestanda för ER-lösningar genom att lägga till parametriserade datakällor för BERÄKNADE FÄLT</span><span class="sxs-lookup"><span data-stu-id="88479-336">Improve performance of ER solutions by adding parameterized CALCULATED FIELD data sources</span></span>](er-calculated-field-ds-performance.md)



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]