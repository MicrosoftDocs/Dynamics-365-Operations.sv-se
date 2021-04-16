---
title: Ställ in parametrarna för ett ER-format per juridisk person
description: I det här avsnittet beskrivs hur du kan konfigurera parametrar för ett format för elektroniska rapporter (ER) per juridisk person.
author: NickSelin
ms.date: 10/29/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERSolutionTable, EROperationDesigner, ERLookupDesigner, ERComponentLookupStructureEditing
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2019-01-01
ms.dyn365.ops.version: Release 8.1.3
ms.openlocfilehash: 4003208a1f02db134bbec1ecf90c1cdd2973e67f
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5751164"
---
# <a name="set-up-the-parameters-of-an-er-format-per-legal-entity"></a><span data-ttu-id="d00f1-103">Ställ in parametrarna för ett ER-format per juridisk person</span><span class="sxs-lookup"><span data-stu-id="d00f1-103">Set up the parameters of an ER format per legal entity</span></span>

[!include[banner](../includes/banner.md)]

## <a name="prerequisites"></a><span data-ttu-id="d00f1-104">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="d00f1-104">Prerequisites</span></span>

<span data-ttu-id="d00f1-105">För att kunna utföra de här stegen måste du först slutföra stegen i [konfigurera ER-format för att använda parametrar som anges per juridisk person](er-app-specific-parameters-configure-format.md).</span><span class="sxs-lookup"><span data-stu-id="d00f1-105">To complete these steps, you must first complete the steps in the [Configure ER formats to use parameters that are specified per legal entity](er-app-specific-parameters-configure-format.md) topic.</span></span>

<span data-ttu-id="d00f1-106">Om du vill slutföra exemplen i det här avsnittet måste du ha tillgång till Microsoft Dynamics 365 Finance (Finance) för en av följande roller:</span><span class="sxs-lookup"><span data-stu-id="d00f1-106">To complete the examples in this topic, you must have access to Microsoft Dynamics 365 Finance (Finance) for one of the following roles:</span></span>

- <span data-ttu-id="d00f1-107">Utvecklare för elektronisk rapportering</span><span class="sxs-lookup"><span data-stu-id="d00f1-107">Electronic reporting developer</span></span>
- <span data-ttu-id="d00f1-108">Konsult för funktionen för elektronisk rapportering</span><span class="sxs-lookup"><span data-stu-id="d00f1-108">Electronic reporting functional consultant</span></span>
- <span data-ttu-id="d00f1-109">Systemadministratör</span><span class="sxs-lookup"><span data-stu-id="d00f1-109">System administrator</span></span>

## <a name="import-er-configurations"></a><span data-ttu-id="d00f1-110">Importera ER-konfigurationer</span><span class="sxs-lookup"><span data-stu-id="d00f1-110">Import ER configurations</span></span>

1.  <span data-ttu-id="d00f1-111">Logga in på miljön.</span><span class="sxs-lookup"><span data-stu-id="d00f1-111">Sign in to your environment.</span></span>
2.  <span data-ttu-id="d00f1-112">Välj **elektronisk rapportering** på standardinstrumentpanelen.</span><span class="sxs-lookup"><span data-stu-id="d00f1-112">On the default dashboard, select **Electronic reporting**.</span></span>
3.  <span data-ttu-id="d00f1-113">Välj **rapporteringskonfigurationer**.</span><span class="sxs-lookup"><span data-stu-id="d00f1-113">Select **Reporting configurations**.</span></span>
4.  <span data-ttu-id="d00f1-114">Importera i den aktuella instansen av Finance de konfigurationer som du har exporterat från Regulatory Configuration Services (RCS) medan du slutförde stegen i avsnittet [konfigurera ER-format för användning av parametrar som anges per juridisk person](er-app-specific-parameters-configure-format.md).</span><span class="sxs-lookup"><span data-stu-id="d00f1-114">Import, into the current instance of Finance, the configurations that you exported from Regulatory Configuration Services (RCS) while you were completing the steps in the [Configure ER formats to use parameters that are specified per legal entity](er-app-specific-parameters-configure-format.md) topic.</span></span> <span data-ttu-id="d00f1-115">Följ de här stegen för varje konfiguration i elektronisk rapportering (ER) i följande ordning: datamodell, modellmappning och format.</span><span class="sxs-lookup"><span data-stu-id="d00f1-115">Follow these steps for each Electronic reporting (ER) configuration, in the following order: data model, model mapping, and formats.</span></span>

    1. <span data-ttu-id="d00f1-116">Välj **Kurs \> Läs in från XML-fil**.</span><span class="sxs-lookup"><span data-stu-id="d00f1-116">Select **Exchange \> Load from XML file**.</span></span>
    2. <span data-ttu-id="d00f1-117">Välj **bläddra** om du vill välja en fil för den nödvändiga ER-konfigurationen i XML-format.</span><span class="sxs-lookup"><span data-stu-id="d00f1-117">Select **Browse** to select the file for the required ER configuration in XML format.</span></span>
    3. <span data-ttu-id="d00f1-118">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="d00f1-118">Select **OK**.</span></span>
    
    <span data-ttu-id="d00f1-119">Följande illustration visar vilka konfigurationer du måste ha när du är klar.</span><span class="sxs-lookup"><span data-stu-id="d00f1-119">The following illustration shows the configurations that you must have when you've finished.</span></span>

    ![Sidan ER-konfigurationer](./media/GER-AppSpecParms-ImportedConfigurations.PNG)

## <a name="set-up-parameters-for-the-demf-company"></a><span data-ttu-id="d00f1-121">Ställa in parametrar för DEMF-företaget</span><span class="sxs-lookup"><span data-stu-id="d00f1-121">Set up parameters for the DEMF company</span></span>

<span data-ttu-id="d00f1-122">Du kan använda ER-ramverket för att ställa in programspecifika parametrar för ett ER-format.</span><span class="sxs-lookup"><span data-stu-id="d00f1-122">You can use the ER framework to set up application-specific parameters for an ER format.</span></span>

1.  <span data-ttu-id="d00f1-123">Välj den juridiska personen **DEMF**.</span><span class="sxs-lookup"><span data-stu-id="d00f1-123">Select the **DEMF** legal entity.</span></span>
2.  <span data-ttu-id="d00f1-124">I konfigurationsträdet väljer du formatet **format för att lära dig hur du letar upp LE-data**.</span><span class="sxs-lookup"><span data-stu-id="d00f1-124">In the configurations tree, select the **Format to learn how to lookup LE data** format.</span></span>
3.  <span data-ttu-id="d00f1-125">I Åtgärdsfönstret, på fliken **Konfigurationer**, i gruppen **Appspecifika parametrar**, markerar du **Konfigurera**.</span><span class="sxs-lookup"><span data-stu-id="d00f1-125">On the Action Pane, on the **Configurations** tab, in the **Application specific parameters** group, select **Setup**.</span></span>

    ![Sidan Importera ER-programspecifika parametrar](./media/GER-AppSpecParms-LookupForm.PNG)
    
    <span data-ttu-id="d00f1-127">På sidan **Programspecifika parametrar** kan du konfigurera reglerna för datakällan **väljare** för formatet **format för att lära dig hur du söker efter LE-data**.</span><span class="sxs-lookup"><span data-stu-id="d00f1-127">On the **Application specific parameters** page, you can configure the rules for the **Selector** data source of the **Format to learn how to lookup LE data** format.</span></span>
    
    <span data-ttu-id="d00f1-128">Om bas ER-basformatet kommer att innehålla flera datakällor av typen **Slå upp** måste du välja önskad datakälla på snabbfliken **sökningar** innan du kan börja konfigurera uppsättningen regler för datakällan.</span><span class="sxs-lookup"><span data-stu-id="d00f1-128">If the base ER format will contain several data sources of the **Lookup** type, you must select the desired data source on the **Lookups** FastTab before you can start to configure the set of rules for the data source.</span></span>
    
    <span data-ttu-id="d00f1-129">För varje datakälla kan du konfigurera separata regler för varje version av det valda ER-formatet.</span><span class="sxs-lookup"><span data-stu-id="d00f1-129">For each data source, you can configure separate rules for each version of the selected ER format.</span></span>
    
    <span data-ttu-id="d00f1-130">Hela uppsättningen regler för alla datakällor för sökning som är tillgängliga i den valda versionen av ER-basformatet utgör de programspecifika parametrarna för ER-format.</span><span class="sxs-lookup"><span data-stu-id="d00f1-130">The whole set of rules for all lookup data sources that are available in the selected version of the base ER format makes up the application-specific parameters for the ER format.</span></span>

4.  <span data-ttu-id="d00f1-131">Välj version **1.1.1** av ER-formatet.</span><span class="sxs-lookup"><span data-stu-id="d00f1-131">Select version **1.1.1** of the ER format.</span></span>
5.  <span data-ttu-id="d00f1-132">På snabbfliken **Villkor** väljer du **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="d00f1-132">On the **Conditions** FastTab, select **Add**.</span></span>
6.  <span data-ttu-id="d00f1-133">I fältet **Kod** för den nya posten väljer du nedrullningsbara pilen för att öppna uppslaget.</span><span class="sxs-lookup"><span data-stu-id="d00f1-133">In the **Code** field of the new record, select the drop-down arrow to open the lookup.</span></span>

    <span data-ttu-id="d00f1-134">Sökningen visar en lista över momskoder för urvalet.</span><span class="sxs-lookup"><span data-stu-id="d00f1-134">The lookup presents the list of tax codes for selection.</span></span> <span data-ttu-id="d00f1-135">Den här listan returneras av datakällan **Model.Data.Tax** som har konfigurerats i ER-basformat.</span><span class="sxs-lookup"><span data-stu-id="d00f1-135">This list is returned by the **Model.Data.Tax** data source that has been configured in the base ER format.</span></span> <span data-ttu-id="d00f1-136">Eftersom datakällan innehåller fältet **namn** visas namnet på varje skattekod i sökningen.</span><span class="sxs-lookup"><span data-stu-id="d00f1-136">Because this data source contains the **Name** field, the name of each tax code appears in the lookup.</span></span>

    ![Sidan Importera ER-programspecifika parametrar](./media/GER-AppSpecParms-LookupForm-CodeFldPicker.PNG)
    
7.  <span data-ttu-id="d00f1-138">Välj momskoden **VAT19**.</span><span class="sxs-lookup"><span data-stu-id="d00f1-138">Select the **VAT19** tax code.</span></span>
8.  <span data-ttu-id="d00f1-139">I fältet **Sökningsresultat** för den nya posten väljer du nedrullningsbara pilen för att öppna uppslaget.</span><span class="sxs-lookup"><span data-stu-id="d00f1-139">In the **Lookup result** field of the new record, select the drop-down arrow to open the lookup.</span></span> <span data-ttu-id="d00f1-140">Sökningen visar en lista med värden för TaxationLevel formatuppräkning för urval.</span><span class="sxs-lookup"><span data-stu-id="d00f1-140">The lookup presents the list of values for the TaxationLevel format enumeration for selection.</span></span>

    <span data-ttu-id="d00f1-141">Observera att om tyska har valts som det prioriterade språket för den användare som du är inloggad på som, kommer etiketterna för värdena i sökningen att vara på tyska, förutsatt att de har översatts i ER-basformatet.</span><span class="sxs-lookup"><span data-stu-id="d00f1-141">Note that, if German is selected as the preferred language of the user that you're signed in as, the labels of the values in the lookup will be in German, provided that they have been translated in the base ER format.</span></span> <span data-ttu-id="d00f1-142">Dessutom, om etiketten för en datakälla för sökning har översatts, kommer den etiketten att visas på användarens önskade språk på fliken **sökningar**.</span><span class="sxs-lookup"><span data-stu-id="d00f1-142">Additionally, if the label of a lookup data source has been translated, that label will appear in the user's preferred language on the **Lookups** tab.</span></span>

    ![Sidan Importera ER-programspecifika parametrar](./media/GER-AppSpecParms-LookupForm-LookupFldPicker.PNG)

9.  <span data-ttu-id="d00f1-144">Välj värdet **vanlig beskattning**.</span><span class="sxs-lookup"><span data-stu-id="d00f1-144">Select the **Regular taxation** value.</span></span>

    <span data-ttu-id="d00f1-145">Genom att lägga till den här posten definierar du följande regel: När datakällan för sökning **Väljare** begärs och momskoden **VAT19** skickas som ett argument, **vanlig beskattning** returneras som den begärda momsnivån.</span><span class="sxs-lookup"><span data-stu-id="d00f1-145">By adding this record, you define the following rule: Whenever the **Selector** lookup data source is requested, and the **VAT19** tax code is passed as an argument, **Regular taxation** will be returned as the requested taxation level.</span></span>

10. <span data-ttu-id="d00f1-146">Välj **Lägg till** och gör sedan följande:</span><span class="sxs-lookup"><span data-stu-id="d00f1-146">Select **Add**, and then follow these steps:</span></span>

    1. <span data-ttu-id="d00f1-147">I fältet **Kod**, välj momskod **InVAT19**.</span><span class="sxs-lookup"><span data-stu-id="d00f1-147">In the **Code** field, select the **InVAT19** tax code.</span></span>
    2. <span data-ttu-id="d00f1-148">I fältet **Sökningsresultat** välj värdet **vanlig beskattning**.</span><span class="sxs-lookup"><span data-stu-id="d00f1-148">In the **Lookup result** field, select the **Regular taxation** value.</span></span>
    
11. <span data-ttu-id="d00f1-149">Välj **Lägg till** igen och gör sedan följande:</span><span class="sxs-lookup"><span data-stu-id="d00f1-149">Select **Add** again, and then follow these steps:</span></span>

    1. <span data-ttu-id="d00f1-150">I fältet **Kod**, välj momskod **VAT7**.</span><span class="sxs-lookup"><span data-stu-id="d00f1-150">In the **Code** field, select the **VAT7** tax code.</span></span>
    2. <span data-ttu-id="d00f1-151">I fältet **Sökningsresultat** välj värdet **Reducerad beskattning**.</span><span class="sxs-lookup"><span data-stu-id="d00f1-151">In the **Lookup result** field, select the **Reduced taxation** value.</span></span>
    
12. <span data-ttu-id="d00f1-152">Välj **Lägg till** igen och gör sedan följande:</span><span class="sxs-lookup"><span data-stu-id="d00f1-152">Select **Add** again, and then follow these steps:</span></span>

    1. <span data-ttu-id="d00f1-153">I fältet **Kod**, välj momskod **InVAT7**.</span><span class="sxs-lookup"><span data-stu-id="d00f1-153">In the **Code** field, select the **InVAT7** tax code.</span></span>
    2. <span data-ttu-id="d00f1-154">I fältet **Sökningsresultat** välj värdet **Reducerad beskattning**.</span><span class="sxs-lookup"><span data-stu-id="d00f1-154">In the **Lookup result** field, select the **Reduced taxation** value.</span></span>
    
13. <span data-ttu-id="d00f1-155">Välj **Lägg till** igen och gör sedan följande:</span><span class="sxs-lookup"><span data-stu-id="d00f1-155">Select **Add** again, and then follow these steps:</span></span>

    1. <span data-ttu-id="d00f1-156">I fältet **Kod**, välj momskod **THIRD**.</span><span class="sxs-lookup"><span data-stu-id="d00f1-156">In the **Code** field, select the **THIRD** tax code.</span></span>
    2. <span data-ttu-id="d00f1-157">I fältet **Sökningsresultat** välj värdet **Ingen beskattning**.</span><span class="sxs-lookup"><span data-stu-id="d00f1-157">In the **Lookup result** field, select the **No taxation** value.</span></span>
    
14. <span data-ttu-id="d00f1-158">Välj **Lägg till** igen och gör sedan följande:</span><span class="sxs-lookup"><span data-stu-id="d00f1-158">Select **Add** again, and then follow these steps:</span></span>

    1. <span data-ttu-id="d00f1-159">I fältet **Kod**, välj momskod **InVAT0**.</span><span class="sxs-lookup"><span data-stu-id="d00f1-159">In the **Code** field, select the **InVAT0** tax code.</span></span>
    2. <span data-ttu-id="d00f1-160">I fältet **Sökningsresultat** välj värdet **Ingen beskattning**.</span><span class="sxs-lookup"><span data-stu-id="d00f1-160">In the **Lookup result** field, select the **No taxation** value.</span></span>
    
15. <span data-ttu-id="d00f1-161">Välj **Lägg till** igen och gör sedan följande:</span><span class="sxs-lookup"><span data-stu-id="d00f1-161">Select **Add** again, and then follow these steps:</span></span>

    1. <span data-ttu-id="d00f1-162">Välj alternativet **Kod** välj alternativet **\*Ej tomt\***.</span><span class="sxs-lookup"><span data-stu-id="d00f1-162">In the **Code** field, select the **\*Not blank\*** option.</span></span>
    2. <span data-ttu-id="d00f1-163">I fältet **Sökningsresultat** välj värdet **Övrig**.</span><span class="sxs-lookup"><span data-stu-id="d00f1-163">In the **Lookup result** field, select the **Other** value.</span></span>
    
    <span data-ttu-id="d00f1-164">Genom att lägga till den här posten definierar du följande regel: När datakällan för sökning skicka eftersom ett argument inte uppfyller någon av de tidigare reglerna, kommer uppslagning datakällan tillbaka **Övrig** som den begärda momsnivån.</span><span class="sxs-lookup"><span data-stu-id="d00f1-164">By adding this last record, you define the following rule: Whenever the tax code that is passed as an argument doesn't satisfy any of the previous rules, the lookup data source will return **Other** as the requested taxation level.</span></span>

    ![Sidan Importera ER-programspecifika parametrar](./media/GER-AppSpecParms-LookupForm-RulesSet.PNG)
    
16. <span data-ttu-id="d00f1-166">I fältet **Stat**, välj **Slutförd**.</span><span class="sxs-lookup"><span data-stu-id="d00f1-166">In the **State** field, select **Completed**.</span></span>

    <span data-ttu-id="d00f1-167">När du kör en ER-formatversion som har statusen antingen **slutförd** eller **delad**, måste denna uppsättning regler vara **slutförd**.</span><span class="sxs-lookup"><span data-stu-id="d00f1-167">When you run an ER format version that has a status of either **Completed** or **Shared**, this set of rules must be in the **Completed** state.</span></span> <span data-ttu-id="d00f1-168">I annat fall avbryts körningen av ER-basformatet när formatet försöker läsa in data från den här uppsättningen regler medan datakälla för sökning **väljare** körs.</span><span class="sxs-lookup"><span data-stu-id="d00f1-168">Otherwise, execution of the base ER format will be interrupted when the format tries to load data from this set of rules while the **Selector** lookup data source is being run.</span></span>
    
    <span data-ttu-id="d00f1-169">När du kör en ER-formatversion som har statusen **utkast** kan ER-basformatet komma åt denna uppsättning regler, oavsett status.</span><span class="sxs-lookup"><span data-stu-id="d00f1-169">When you run an ER format version that has a status of **Draft**, the base ER format can access this set of rules, regardless of its state.</span></span>
    
17. <span data-ttu-id="d00f1-170">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="d00f1-170">Select **Save**.</span></span>
18. <span data-ttu-id="d00f1-171">Stäng sidan **Appspecifika parametrar**.</span><span class="sxs-lookup"><span data-stu-id="d00f1-171">Close the **Application specific parameters** page.</span></span>

## <a name="run-the-er-format-in-the-demf-company"></a><span data-ttu-id="d00f1-172">Kör ER-formatet i DEMF-företaget</span><span class="sxs-lookup"><span data-stu-id="d00f1-172">Run the ER format in the DEMF company</span></span>

1.  <span data-ttu-id="d00f1-173">I konfigurationsträdet väljer du formatet **format för att lära dig hur du letar upp LE-data**.</span><span class="sxs-lookup"><span data-stu-id="d00f1-173">In the configurations tree, select the **Format to learn how to lookup LE data** format.</span></span>
2.  <span data-ttu-id="d00f1-174">Klicka på **Kör** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="d00f1-174">On the Action Pane, select **Run**.</span></span>
3.  <span data-ttu-id="d00f1-175">I dialogrutan som visas väljer du **OK**.</span><span class="sxs-lookup"><span data-stu-id="d00f1-175">In the dialog box that appears, select **OK**.</span></span>
4.  <span data-ttu-id="d00f1-176">Hämta det utdrag som genereras och spara det lokalt.</span><span class="sxs-lookup"><span data-stu-id="d00f1-176">Download the statement that is generated and store it locally.</span></span>

    <span data-ttu-id="d00f1-177">Observera i det genererade utdraget att sammanfattningen av momskoden **InVAT7** har placerats på nivån **reducerad** och sammanfattningar av **VAT19** och **InVA19** momskoder har placerats på nivån **normal**.</span><span class="sxs-lookup"><span data-stu-id="d00f1-177">In the generated statement, notice that the summary of the **InVAT7** tax code has been put on the **Reduced** level, and the summaries of the **VAT19** and **InVA19** tax codes have been put on the **Regular** level.</span></span> <span data-ttu-id="d00f1-178">Det här beteendet bestäms av konfigurationen i de regler som är beroende av den juridiska personen.</span><span class="sxs-lookup"><span data-stu-id="d00f1-178">This behavior is determined by the configuration in the legal entity–dependent set of rules.</span></span>
    
5.  <span data-ttu-id="d00f1-179">Gå till **Moms \> Indirekt moms \> Moms \> Momskoder**.</span><span class="sxs-lookup"><span data-stu-id="d00f1-179">Go to **Tax \> Indirect taxes \> Sales tax \> Sales tax codes**.</span></span>
6.  <span data-ttu-id="d00f1-180">Välj momskoden **InVAT7**.</span><span class="sxs-lookup"><span data-stu-id="d00f1-180">Select the **InVAT7** tax code.</span></span>
7.  <span data-ttu-id="d00f1-181">I åtgärdsfönstret på fliken **Momskod** i gruppen **Förfrågningar** välj **Bokförd moms** om du vill visa information om momsvärde och tillämpad momssats per momskod.</span><span class="sxs-lookup"><span data-stu-id="d00f1-181">On the Action Pane, on the **Sales tax code** tab, in the **Inquiries** group, select **Posted sales tax** to view information about the tax value and applied tax rate per tax code.</span></span>

    ![Sidan Bokförd moms](./media/GER-AppSpecParms-Statement.PNG)

8.  <span data-ttu-id="d00f1-183">Stäng sidan Bokförd moms.</span><span class="sxs-lookup"><span data-stu-id="d00f1-183">Close the Posted sales tax page.</span></span>

## <a name="set-up-parameters-for-the-usmf-company"></a><span data-ttu-id="d00f1-184">Ställa in parametrar för USMF-företaget</span><span class="sxs-lookup"><span data-stu-id="d00f1-184">Set up parameters for the USMF company</span></span>

1.  <span data-ttu-id="d00f1-185">Välj den juridiska personen **USMF**.</span><span class="sxs-lookup"><span data-stu-id="d00f1-185">Select the **USMF** legal entity.</span></span>
2.  <span data-ttu-id="d00f1-186">Gå till **Organisationsadministration  \> Elektronisk rapportering \> Konfigurationer**.</span><span class="sxs-lookup"><span data-stu-id="d00f1-186">Go to **Organization administration \> Electronic reporting \> Configurations**.</span></span>
3.  <span data-ttu-id="d00f1-187">I konfigurationsträdet expanderar du objektet **Modell för att lära dig parameteranrop** expanderar du objektet **Format för att lära dig parameteranrop** och välj formatet **format för att lära dig hur du slår upp LE-data**.</span><span class="sxs-lookup"><span data-stu-id="d00f1-187">In the configurations tree, expand the **Model to learn parameterized calls** item, expand the **Format to learn parameterized calls** item, and select the **Format to learn how to lookup LE data** format.</span></span>
4.  <span data-ttu-id="d00f1-188">I Åtgärdsfönstret, på fliken **Konfigurationer**, i gruppen **Appspecifika parametrar**, markerar du **Konfigurera**.</span><span class="sxs-lookup"><span data-stu-id="d00f1-188">On the Action Pane, on the **Configurations** tab, in the **Application specific parameters** group, select **Setup**.</span></span>
5.  <span data-ttu-id="d00f1-189">Välj version **1.1.1** av det valda ER-formatet.</span><span class="sxs-lookup"><span data-stu-id="d00f1-189">Select version **1.1.1** of the selected ER format.</span></span>
6.  <span data-ttu-id="d00f1-190">På snabbfliken **Villkor** väljer du **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="d00f1-190">On the **Conditions** FastTab, select **Add**.</span></span>
7.  <span data-ttu-id="d00f1-191">I fältet **Kod** för den nya posten väljer du nedrullningsbara pilen för att öppna uppslaget.</span><span class="sxs-lookup"><span data-stu-id="d00f1-191">In the **Code** field of the new record, select the drop-down arrow to open the lookup.</span></span>

    <span data-ttu-id="d00f1-192">Sökningen visar nu en lista över momskoder för **USMF** företagsmoms för urvalet.</span><span class="sxs-lookup"><span data-stu-id="d00f1-192">The lookup now presents the list of tax codes for the **USMF** company tax for selection.</span></span>

    ![Sidan Importera ER-programspecifika parametrar](./media/GER-AppSpecParms-LookupForm-CodeFldPicker2.PNG)
    
8.  <span data-ttu-id="d00f1-194">Välj momskoden **EXEMPT**.</span><span class="sxs-lookup"><span data-stu-id="d00f1-194">Select the **EXEMPT** tax code.</span></span>
9.  <span data-ttu-id="d00f1-195">I fältet **Sökningsresultat** för den nya posten, välj värdet **Ingen beskattning**.</span><span class="sxs-lookup"><span data-stu-id="d00f1-195">In the **Lookup resul** t field of the new record, select the **No taxation** value.</span></span>
10. <span data-ttu-id="d00f1-196">Välj **Lägg till** igen.</span><span class="sxs-lookup"><span data-stu-id="d00f1-196">Select **Add** again.</span></span>
11. <span data-ttu-id="d00f1-197">I fältet **Kod** för den nya posten, välj alternativet **\*Ej tomt\***.</span><span class="sxs-lookup"><span data-stu-id="d00f1-197">In the **Code** field of the new record, select the **\*Not blank\*** option.</span></span>
12. <span data-ttu-id="d00f1-198">I fältet **Sökningsresultat** för den nya posten, välj värdet **Vanlig beskattning**.</span><span class="sxs-lookup"><span data-stu-id="d00f1-198">In the **Lookup result** field of the new record, select the **Regular taxation** value.</span></span>
13. <span data-ttu-id="d00f1-199">I fältet **Stat**, välj **Slutförd**.</span><span class="sxs-lookup"><span data-stu-id="d00f1-199">In the **State** field, select **Completed**.</span></span>
14. <span data-ttu-id="d00f1-200">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="d00f1-200">Select **Save**.</span></span>

    ![Sidan Importera ER-programspecifika parametrar](./media/GER-AppSpecParms-LookupForm-RulesSet2.PNG)
    
15. <span data-ttu-id="d00f1-202">Stäng sidan **Appspecifika parametrar**.</span><span class="sxs-lookup"><span data-stu-id="d00f1-202">Close the **Application specific parameters** page.</span></span>

## <a name="run-the-er-format-in-the-usmf-company"></a><span data-ttu-id="d00f1-203">Kör ER-formatet i USMF-företaget</span><span class="sxs-lookup"><span data-stu-id="d00f1-203">Run the ER format in the USMF company</span></span>

1.  <span data-ttu-id="d00f1-204">I konfigurationsträdet väljer du formatet **format för att lära dig hur du letar upp LE-data**.</span><span class="sxs-lookup"><span data-stu-id="d00f1-204">In the configurations tree, select the **Format to learn how to lookup LE data** format.</span></span>
2.  <span data-ttu-id="d00f1-205">Klicka på **Kör** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="d00f1-205">On the Action Pane, select **Run**.</span></span>
3.  <span data-ttu-id="d00f1-206">I dialogrutan som visas väljer du **OK**.</span><span class="sxs-lookup"><span data-stu-id="d00f1-206">In the dialog box that appears, select **OK**.</span></span>
4.  <span data-ttu-id="d00f1-207">Hämta det utdrag som genereras och spara det lokalt.</span><span class="sxs-lookup"><span data-stu-id="d00f1-207">Download the statement that is generated and store it locally.</span></span>

    <span data-ttu-id="d00f1-208">Observera i det genererade uttrycket att du nu har återanvänt ER-formatet för en annan juridisk person utan att göra några justeringar av ER-format.</span><span class="sxs-lookup"><span data-stu-id="d00f1-208">In the generated statement, notice that you've now reused the same ER format for a different legal entity, but without making any adjustments to the ER format.</span></span>

## <a name="reuse-legal-entitydependent-parameters"></a><span data-ttu-id="d00f1-209">Återanvänd parametrar som är beroende av den juridiska personen.</span><span class="sxs-lookup"><span data-stu-id="d00f1-209">Reuse legal entity–dependent parameters</span></span>

### <a name="export-parameters"></a><span data-ttu-id="d00f1-210">Exportera parametrar</span><span class="sxs-lookup"><span data-stu-id="d00f1-210">Export parameters</span></span>

1.  <span data-ttu-id="d00f1-211">Gå till **Organisationsadministration \> Arbetsytor \> Elektronisk rapportering**.</span><span class="sxs-lookup"><span data-stu-id="d00f1-211">Go to **Organization administration \> Workspaces \> Electronic reporting**.</span></span>
2.  <span data-ttu-id="d00f1-212">Välj **rapporteringskonfigurationer**.</span><span class="sxs-lookup"><span data-stu-id="d00f1-212">Select **Reporting configurations**.</span></span>
3.  <span data-ttu-id="d00f1-213">I konfigurationsträdet väljer du formatet **format för att lära dig hur du letar upp LE-data**.</span><span class="sxs-lookup"><span data-stu-id="d00f1-213">In the configurations tree, select the **Format to learn how to lookup LE data** format.</span></span>
4.  <span data-ttu-id="d00f1-214">I Åtgärdsfönstret, på fliken **Konfigurationer**, i gruppen **Appspecifika parametrar**, markerar du **Konfigurera**.</span><span class="sxs-lookup"><span data-stu-id="d00f1-214">On the Action Pane, on the **Configurations** tab, in the **Application specific parameters** group, select **Setup**.</span></span>
5.  <span data-ttu-id="d00f1-215">Välj version **1.1.1** av ER-formatet.</span><span class="sxs-lookup"><span data-stu-id="d00f1-215">Select version **1.1.1** of the ER format.</span></span>
6.  <span data-ttu-id="d00f1-216">Välj **Export** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="d00f1-216">On the Action Pane, select **Export**.</span></span>
7.  <span data-ttu-id="d00f1-217">Hämta den fil som genereras och spara det lokalt.</span><span class="sxs-lookup"><span data-stu-id="d00f1-217">Download the file that is generated and store it locally.</span></span>

    <span data-ttu-id="d00f1-218">Den konfigurerade uppsättningen programspecifika parametrar har nu exporterats som en XML-fil.</span><span class="sxs-lookup"><span data-stu-id="d00f1-218">The configured set of application-specific parameters has now been exported as an XML file.</span></span>

### <a name="import-parameters"></a><span data-ttu-id="d00f1-219">Importera parametrar</span><span class="sxs-lookup"><span data-stu-id="d00f1-219">Import parameters</span></span>

1.  <span data-ttu-id="d00f1-220">Välj version **1.1.2** av ER-formatet.</span><span class="sxs-lookup"><span data-stu-id="d00f1-220">Select version **1.1.2** of the ER format.</span></span>
2.  <span data-ttu-id="d00f1-221">Välj **Import** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="d00f1-221">On the Action Pane, select **Import**.</span></span>
3.  <span data-ttu-id="d00f1-222">Välj **ja** för att bekräfta att du vill åsidosätta de befintliga programspecifika parametrarna för den här formatversionen.</span><span class="sxs-lookup"><span data-stu-id="d00f1-222">Select **Yes** to confirm that you want to override the existing application-specific parameters for this format version.</span></span>
4.  <span data-ttu-id="d00f1-223">Välj **bläddra** om du vill söka efter filen som innehåller de exporterade programspecifika parametrarna för version **1.1.1**.</span><span class="sxs-lookup"><span data-stu-id="d00f1-223">Select **Browse** to find the file that contains the exported application-specific parameters for version **1.1.1**.</span></span>
5.  <span data-ttu-id="d00f1-224">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="d00f1-224">Select **OK**.</span></span>

    <span data-ttu-id="d00f1-225">Version **1.1.2** av ER-formatet har nu samma programspecifika parametrar som du ursprungligen konfigurerade för version **1.1.1**.</span><span class="sxs-lookup"><span data-stu-id="d00f1-225">Version **1.1.2** of the ER format now has the same application-specific parameters that you originally configured for version **1.1.1**.</span></span>
    
    <span data-ttu-id="d00f1-226">Observera att de programspecifika parametrarna för ett ER-format som är beroende av den juridiska personen.</span><span class="sxs-lookup"><span data-stu-id="d00f1-226">Note that the application-specific parameters of an ER format are legal entity–dependent.</span></span> <span data-ttu-id="d00f1-227">Om du vill återanvända de programspecifika parametrarna som konfigurerats för en juridisk person i en annan juridisk person, måste du exportera dem när du är inloggad på den första juridiska personen och sedan importera dem när du har loggat in på den andra juridiska personen.</span><span class="sxs-lookup"><span data-stu-id="d00f1-227">To reuse the application-specific parameters that were configured for one legal entity in a different legal entity, you must export them while you're signed in to the first legal entity and then import them after you sign in to the other legal entity.</span></span>

    <span data-ttu-id="d00f1-228">Du kan också använda den här metoden om du vill överföra ER-formatrelaterade programspecifika parametrar som ursprungligen konfigurerades i en Finance-instans till en annan Finance-instans.</span><span class="sxs-lookup"><span data-stu-id="d00f1-228">You can also use this approach to transfer an ER format related application-specific parameters that were originally configured in one instance of Finance to another instance of Finance.</span></span>

    <span data-ttu-id="d00f1-229">Tänk på att om du konfigurerar programspecifika parametrar för en version av ett ER-format och importerar en högre version av samma format till den aktuella Finance-instansen används inte de befintliga programspecifika parametrarna för den importerade versionen.</span><span class="sxs-lookup"><span data-stu-id="d00f1-229">Be aware that if you configure application-specific parameters for one version of an ER format and import a higher version of the same format into the current Finance instance, the existing application-specific parameters won't be applied for the imported version.</span></span>
    
    <span data-ttu-id="d00f1-230">Tänk också på att när du väljer en fil för import, jämförs även programspecifika parametrar i den filen med strukturen för motsvarande datakälla av typen **uppslag** för det återställningsformat som valts för import.</span><span class="sxs-lookup"><span data-stu-id="d00f1-230">Also be aware that, when you select a file for import, the structure of the application-specific parameters in that file is compared with the structure of the corresponding data source of the **Lookup** type in the ER format that is selected for import.</span></span> <span data-ttu-id="d00f1-231">Importen görs när strukturen för varje programspecifik parameter matchar strukturen för motsvarande datakälla i det återställningsformat som har valts för import.</span><span class="sxs-lookup"><span data-stu-id="d00f1-231">The import is done when the structure of each application-specific parameter matches the structure of the corresponding data source in the ER format that is selected for import.</span></span> <span data-ttu-id="d00f1-232">Om strukturlistorna inte matchar får du ett varningsmeddelande om att importen inte kan utföras.</span><span class="sxs-lookup"><span data-stu-id="d00f1-232">If the structures don't match, you receive a warning message that states that the import can't be done.</span></span> <span data-ttu-id="d00f1-233">Om du tvingar importen att utföras rensas de befintliga programspecifika parametrarna för det valda återställningsformatet och du måste ställa in dem från början.</span><span class="sxs-lookup"><span data-stu-id="d00f1-233">If you force the import to be done, the existing application-specific parameters for the selected ER format will be cleaned up, and you must set them up from the beginning.</span></span>

## <a name="relationship-between-application-specific-parameters-and-an-er-format"></a><span data-ttu-id="d00f1-234">Relation mellan programspecifika parametrar och ett ER-format</span><span class="sxs-lookup"><span data-stu-id="d00f1-234">Relationship between application-specific parameters and an ER format</span></span>

<span data-ttu-id="d00f1-235">Relationen mellan ett ER-format och dess programspecifika parametrar upprättas genom ER-formatets instansoberoende identifieringskod.</span><span class="sxs-lookup"><span data-stu-id="d00f1-235">The relationship between an ER format and its application-specific parameters is established by the ER format's instance-independent unique identification code.</span></span> <span data-ttu-id="d00f1-236">När du tar bort ett ER-format från Finance behålls därför de programspecifika parametrar som har konfigurerats för ER-format i den aktuella instansen Finance.</span><span class="sxs-lookup"><span data-stu-id="d00f1-236">Therefore, when you remove an ER format from Finance, the application-specific parameters that are configured for the ER format are kept in the current instance of Finance.</span></span> <span data-ttu-id="d00f1-237">De kan nås varje gång som ER-basformatet återimporteras till den här instansen av Finance.</span><span class="sxs-lookup"><span data-stu-id="d00f1-237">They can be accessed whenever the base ER format is reimported into this instance of Finance.</span></span>

## <a name="access-application-specific-parameters-by-using-the-er-framework"></a><span data-ttu-id="d00f1-238">Få åtkomst till programspecifika parametrar med hjälp av ER-ramverket</span><span class="sxs-lookup"><span data-stu-id="d00f1-238">Access application-specific parameters by using the ER framework</span></span>

<span data-ttu-id="d00f1-239">I föregående exempel har du tillgång till programspecifika parametrar för ett ER-format med hjälp av ER-ramverket.</span><span class="sxs-lookup"><span data-stu-id="d00f1-239">In the preceding example, you have accessed application-specific parameters of an ER format by using the ER framework.</span></span> <span data-ttu-id="d00f1-240">Med den här metoden kan du inte begränsa åtkomsten till de programspecifika parametrarna för ett visst ER-format.</span><span class="sxs-lookup"><span data-stu-id="d00f1-240">This approach doesn't let you restrict access to the application-specific parameters of a specific ER format.</span></span> <span data-ttu-id="d00f1-241">Gör så här om du måste tillämpa dessa begränsningar.</span><span class="sxs-lookup"><span data-stu-id="d00f1-241">If you must apply such restrictions, follow these steps.</span></span> 

1.  <span data-ttu-id="d00f1-242">Återanvänd antingen ett befintligt menyalternativ **ERSolutionAppSpecificParametersDesigner** eller implementera dina egna **ERSolutionAppSpecificParametersDesigner** menyalternativ.</span><span class="sxs-lookup"><span data-stu-id="d00f1-242">Either reuse an existing **ERSolutionAppSpecificParametersDesigner** menu item, or implement your own **ERSolutionAppSpecificParametersDesigner** menu item.</span></span>

    ![Visual Studio-sida](./media/GER-AppSpecParms-LookupForm-Access1.PNG)
    
2.  <span data-ttu-id="d00f1-244">Gör något av följande:</span><span class="sxs-lookup"><span data-stu-id="d00f1-244">Follow one of these steps:</span></span>

    1.  <span data-ttu-id="d00f1-245">Skapa en ny knapp för meny objekt och länka den till motsvarande post från tabellen **ERSolutionTable** genom att ange egenskapen **Datakälla** till **ERSolutionTable**.</span><span class="sxs-lookup"><span data-stu-id="d00f1-245">Create a new menu item button, and link it to the corresponding record from the **ERSolutionTable** table by setting its **Data Source** property to **ERSolutionTable**.</span></span>
    
        ![Visual Studio-sida](./media/GER-AppSpecParms-LookupForm-Access2.PNG)
        
    2.  <span data-ttu-id="d00f1-247">Skapa en enkel knapp och åsidosätt den **klickade** metoden som den visas i följande exempel.</span><span class="sxs-lookup"><span data-stu-id="d00f1-247">Create a simple button, and override the **Clicked** method as shown in the following example.</span></span>
    
        <span data-ttu-id="d00f1-248">Genom att använda den här metoden kan du ange ett unikt lösnings-ID (definierat via värdet **GUID**) som tillåter åtkomst till programspecifika parametrar för endast ett visst ER-format och underordnade kopior som har härletts från den.</span><span class="sxs-lookup"><span data-stu-id="d00f1-248">By using this approach, you can specify a unique solution ID (defined via the **GUID** value) to allow access to the application-specific parameters of only a specific ER format and descendant copies that have been derived from it.</span></span>
        
        ```xpp
        public void clicked()
            {
                super();

                ERSolutionTable solutionTableRecord = ERSolutionTable::findByGUID(str2Guid('ADACCB2F-EFD1-4C90-877D-7E1E5D1AEE92'));

                Args args = new Args();
                args.record(solutionTableRecord);
                args.caller(this);

                new MenuFunction(menuItemDisplayStr(ERSolutionAppSpecificParametersDesigner), MenuItemType::Display)
                    .run(args);
            }
        ```

## <a name="additional-resources"></a><span data-ttu-id="d00f1-249">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="d00f1-249">Additional resources</span></span>

[<span data-ttu-id="d00f1-250">Formeldesigner i elektronisk rapportering</span><span class="sxs-lookup"><span data-stu-id="d00f1-250">Formula designer in Electronic reporting</span></span>](general-electronic-reporting-formula-designer.md)

[<span data-ttu-id="d00f1-251">Konfigurera ER-format för användning av parametrar som anges per juridisk person</span><span class="sxs-lookup"><span data-stu-id="d00f1-251">Configure ER formats to use parameters that are specified per legal entity</span></span>](er-app-specific-parameters-configure-format.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]