---
title: Förbättringar i spårning av resultaten från genererade ER-rapporter och jämföra dem med baslinjevärden
description: Det här avsnittet innehåller information om hur funktionen ER-baslinje har förbättrats i Microsoft Dynamics 365 for Finance and Operations version 10.0.3 (juni 2019).
author: NickSelin
manager: AnnBe
ms.date: 06/19/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 220314
ms.assetid: 2685df16-5ec8-4fd7-9495-c0f653e82567
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2018-04-01
ms.dyn365.ops.version: Release 8.0
ms.openlocfilehash: 222a415f686c8028fc2a414f97eed0291d850ae7
ms.sourcegitcommit: 9917df8c0c9320955c61186cd922c8df894a4f25
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/21/2019
ms.locfileid: "1700692"
---
# <a name="improvements-in-tracing-the-results-of-generated-er-reports-and-comparing-them-with-baseline-values"></a><span data-ttu-id="e52c4-103">Förbättringar i spårning av resultaten från genererade ER-rapporter och jämföra dem med baslinjevärden</span><span class="sxs-lookup"><span data-stu-id="e52c4-103">Improvements in tracing the results of generated ER reports and comparing them with baseline values</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="e52c4-104">I det här avsnittet beskrivs den första uppsättningen med förbättringar av funktionen för baslinje i det elektroniska rapportramverket (ER).</span><span class="sxs-lookup"><span data-stu-id="e52c4-104">This topic describes the first set of improvements that have been made to the baseline feature of the Electronic reporting (ER) framework.</span></span> <span data-ttu-id="e52c4-105">Dessa förbättringar finns i Microsoft Dynamics 365 for Finance and Operations version 10.0.3 (juni 2019) och senare.</span><span class="sxs-lookup"><span data-stu-id="e52c4-105">These improvements are available in Microsoft Dynamics 365 for Finance and Operations version 10.0.3 (June 2019) and later.</span></span>

## <a name="automate-the-setting-of-baseline-rules"></a><span data-ttu-id="e52c4-106">Automatisera inställningen av baslinjeregler</span><span class="sxs-lookup"><span data-stu-id="e52c4-106">Automate the setting of baseline rules</span></span>

<span data-ttu-id="e52c4-107">Ämnet [Spårningsgenererade rapportresultat och jämföra dem med baslinjevärden](er-trace-reports-compare-baseline.md) beskriver hur du konfigurerar ER-ramverket för insamling av information om ER-formatering och utvärdering av resultaten av dessa körningar.</span><span class="sxs-lookup"><span data-stu-id="e52c4-107">The [Trace generated report results and compare them with baseline values](er-trace-reports-compare-baseline.md) topic explains how to configure the ER framework to collect information about ER format executions and evaluate the results of those executions.</span></span> <span data-ttu-id="e52c4-108">I exemplet i det här avsnittet visas de steg som måste utföras.</span><span class="sxs-lookup"><span data-stu-id="e52c4-108">The example in this topic shows the steps that must be completed.</span></span>

<span data-ttu-id="e52c4-109">Här följer några steg:</span><span class="sxs-lookup"><span data-stu-id="e52c4-109">Here are some of the steps:</span></span>

- <span data-ttu-id="e52c4-110">Kör ett ER-format för att skapa en utgående fil och spara filen lokalt.</span><span class="sxs-lookup"><span data-stu-id="e52c4-110">Run an ER format to generate an outbound file, and store the file locally.</span></span>
- <span data-ttu-id="e52c4-111">Lägg till den lokalt lagrade filen som en bilaga till den baslinje som lades till för ER-format.</span><span class="sxs-lookup"><span data-stu-id="e52c4-111">Add the locally stored file as an attachment of the baseline that was added for an ER format.</span></span>
- <span data-ttu-id="e52c4-112">Konfigurera baslinjergeln för den tillagda baslinjen.</span><span class="sxs-lookup"><span data-stu-id="e52c4-112">Configure the baseline rule for the added baseline.</span></span> <span data-ttu-id="e52c4-113">Den här konfigurationen omfattar följande steg:</span><span class="sxs-lookup"><span data-stu-id="e52c4-113">This configuration includes the following steps:</span></span>

    - <span data-ttu-id="e52c4-114">Ange ett ER-formatelement som används för att generera en utgående fil.</span><span class="sxs-lookup"><span data-stu-id="e52c4-114">Specify an ER format element that is used to generate an outbound file.</span></span>
    - <span data-ttu-id="e52c4-115">Markera den bilaga som refererar till den genererade utgående filen.</span><span class="sxs-lookup"><span data-stu-id="e52c4-115">Select the attachment that refers to the generated outbound file.</span></span>

> [!NOTE]
> <span data-ttu-id="e52c4-116">Du måste utföra dessa steg manuellt, även om de nya ER-funktionerna gör det möjligt att automatisera dem.</span><span class="sxs-lookup"><span data-stu-id="e52c4-116">These steps must be done manually, even though the new ER capabilities enable them to be automated.</span></span> <span data-ttu-id="e52c4-117">Om du vill veta mer om den här funktionen fyller du i följande exempel.</span><span class="sxs-lookup"><span data-stu-id="e52c4-117">To learn more about this feature, complete the following example.</span></span>

## <a name="example-automate-the-setting-of-baseline-rules"></a><span data-ttu-id="e52c4-118">Exempel: Automatisera inställningen av baslinjeregler</span><span class="sxs-lookup"><span data-stu-id="e52c4-118">Example: Automate the setting of baseline rules</span></span>

<span data-ttu-id="e52c4-119">Om du vill slutföra stegen i det här exemplet måste du först slutföra stegen i exemplet i [Spåra skapade rapportresultat och jämföra dem med baslinjevärden](er-trace-reports-compare-baseline.md) i avsnittet "lägga till en ny baslinjeplan för ett utformat ER-format".</span><span class="sxs-lookup"><span data-stu-id="e52c4-119">To complete the steps in this example, you must first complete the steps in the example in the [Trace generated report results and compare them with baseline values](er-trace-reports-compare-baseline.md) topic, up through the "Add a new baseline for a designed ER format" section.</span></span>

### <a name="review-added-baseline"></a><span data-ttu-id="e52c4-120">Granska tillagda baslinjer</span><span class="sxs-lookup"><span data-stu-id="e52c4-120">Review added baseline</span></span>

1. <span data-ttu-id="e52c4-121">Gå till **Organisationsadministration** \> **Elektronisk rapportering** \> **Konfigurationer**.</span><span class="sxs-lookup"><span data-stu-id="e52c4-121">Go to **Organization administration** \> **Electronic reporting** \> **Configurations**.</span></span>
2. <span data-ttu-id="e52c4-122">Välj **baslinjer**.</span><span class="sxs-lookup"><span data-stu-id="e52c4-122">Select **Baselines**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="e52c4-123">Knappen **baslinjer** i åtgärdsfönstret är bara tillgänglig om parametern **kör i felsökningsläge** ER-användarparameter är aktiverad för det aktuella företaget.</span><span class="sxs-lookup"><span data-stu-id="e52c4-123">The **Baselines** button on the Action Pane is available only when the **Run in debug mode** ER user parameter is turned on for the current company.</span></span>

<span data-ttu-id="e52c4-124">Baslinjen har lagts till för det valda formatet **Format för att lära ER-baslinjer** men baslinjereglerna har ännu inte lagts till för denna baslinje.</span><span class="sxs-lookup"><span data-stu-id="e52c4-124">The baseline has been added for the selected **Format to learn ER baselines** format, but the baseline rules haven't yet been added for this baseline.</span></span>

<span data-ttu-id="e52c4-125">![Sidan Baslinjer med elektroniskt rapporteringsformat](media/GER-BaselineSample-AddBaseline2.PNG "Skärmbild av sidan Baslinjer med elektroniskt rapporteringsformat")</span><span class="sxs-lookup"><span data-stu-id="e52c4-125">![Electronic reporting format baselines page](media/GER-BaselineSample-AddBaseline2.PNG "Screenshot of the Electronic reporting format baselines page")</span></span>

### <a name="make-a-new-baseline-rule"></a><span data-ttu-id="e52c4-126">Skapa en ny baslinjeregel</span><span class="sxs-lookup"><span data-stu-id="e52c4-126">Make a new baseline rule</span></span>

1. <span data-ttu-id="e52c4-127">Gå till **Organisationsadministration** \> **Elektronisk rapportering** \> **Konfigurationer**.</span><span class="sxs-lookup"><span data-stu-id="e52c4-127">Go to **Organization administration** \> **Electronic reporting** \> **Configurations**.</span></span>
2. <span data-ttu-id="e52c4-128">I trädet expanderar du **modell för att lära sig ER-baslinjer**.</span><span class="sxs-lookup"><span data-stu-id="e52c4-128">In the tree, expand **Model to learn ER baselines**.</span></span>
3. <span data-ttu-id="e52c4-129">Välj **modell för att lära dig ER-baslinjer\\format för att lära dig ER-baslinjer**.</span><span class="sxs-lookup"><span data-stu-id="e52c4-129">In the tree, select **Model to learn ER baselines\\Format to learn ER baselines**.</span></span>
4. <span data-ttu-id="e52c4-130">Klicka på **Kör** på snabbfliken **Versioner**.</span><span class="sxs-lookup"><span data-stu-id="e52c4-130">On the **Versions** FastTab, select **Run**.</span></span>
5. <span data-ttu-id="e52c4-131">I fältet **Ange Id** anger du **1**.</span><span class="sxs-lookup"><span data-stu-id="e52c4-131">In the **Enter Id** field, enter **1**.</span></span>
6. <span data-ttu-id="e52c4-132">Ställ in alternativet **gör baslinjefiler** till **Ja**.</span><span class="sxs-lookup"><span data-stu-id="e52c4-132">Set the **Make baseline files** option to **Yes**.</span></span>
7. <span data-ttu-id="e52c4-133">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="e52c4-133">Select **OK**.</span></span>

    <span data-ttu-id="e52c4-134">![Dialogrutan elektroniska rapportparametrar](media/GER-BaselineSample-FormatRunToMakeBaselineFile3.PNG "Skärmbild av dialogrutan elektroniska rapportparametrar")</span><span class="sxs-lookup"><span data-stu-id="e52c4-134">![Electronic report parameters dialog box](media/GER-BaselineSample-FormatRunToMakeBaselineFile3.PNG "Screenshot of the Electronic report parameters dialog box")</span></span>

8. <span data-ttu-id="e52c4-135">Välj **baslinjer**.</span><span class="sxs-lookup"><span data-stu-id="e52c4-135">Select **Baselines**.</span></span>

    <span data-ttu-id="e52c4-136">![Sidan Baslinjer med elektroniskt rapporteringsformat](media/GER-BaselineSample-ReviewAddedBaselineLine.PNG "Skärmbild av sidan Baslinjer med elektroniskt rapporteringsformat")</span><span class="sxs-lookup"><span data-stu-id="e52c4-136">![Electronic reporting format baselines page](media/GER-BaselineSample-ReviewAddedBaselineLine.PNG "Screenshot of the Electronic reporting format baselines page")</span></span>

    <span data-ttu-id="e52c4-137">Den genererade utgående filen har automatiskt kopplats till baslinjen för det körda ER-formatet.</span><span class="sxs-lookup"><span data-stu-id="e52c4-137">The generated outbound file has been automatically attached to the baseline of the executed ER format.</span></span> <span data-ttu-id="e52c4-138">Baslinjeregeln läggs automatiskt till i denna baslinje och innehåller också referensen till den bifogade filen.</span><span class="sxs-lookup"><span data-stu-id="e52c4-138">The baseline rule has been automatically added to this baseline and also contains the reference to the attached file.</span></span>

9. <span data-ttu-id="e52c4-139">Skriv **Baslinje 1** i fältet **Namn**.</span><span class="sxs-lookup"><span data-stu-id="e52c4-139">In the **Name** field, enter **Baseline 1**.</span></span>
10. <span data-ttu-id="e52c4-140">I fältet **Filnamnmask**, ange **.xml**.</span><span class="sxs-lookup"><span data-stu-id="e52c4-140">In the **File name mask** field, enter **.xml**.</span></span>
11. <span data-ttu-id="e52c4-141">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="e52c4-141">Select **Save**.</span></span>

### <a name="run-the-format"></a><span data-ttu-id="e52c4-142">Kör formatet</span><span class="sxs-lookup"><span data-stu-id="e52c4-142">Run the format</span></span>

<span data-ttu-id="e52c4-143">Du är nu redo att slutföra de återstående stegen i exemplet i [Spåra skapade rapportresultat och jämföra dem med baslinjevärden](er-trace-reports-compare-baseline.md) med hjälp av avsnittet "kör det utformade ER-formatet och granska loggen för analys av resultaten".</span><span class="sxs-lookup"><span data-stu-id="e52c4-143">You're now ready to complete the remaining steps in the example in the [Trace generated report results and compare them with baseline values](er-trace-reports-compare-baseline.md) topic, starting from the "Run the designed ER format and review the log to analyze the results" section.</span></span>

> [!NOTE]
> <span data-ttu-id="e52c4-144">När du tar bort den automatiskt tillagda baslinjeregeln på snabbfliken **Baslinjer** tas refererade bifogade filer inte bort automatiskt.</span><span class="sxs-lookup"><span data-stu-id="e52c4-144">When you delete the automatically added baseline rule on the **Baselines** FastTab, the referenced attachment isn't automatically deleted.</span></span>

## <a name="configure-the-baseline-so-that-it-ignores-constantly-changing-parts-of-the-er-output"></a><span data-ttu-id="e52c4-145">Konfigurera baslinjen så att den ignorerar konstant ändring av delar av ER-resultat</span><span class="sxs-lookup"><span data-stu-id="e52c4-145">Configure the baseline so that it ignores constantly changing parts of the ER output</span></span>

<span data-ttu-id="e52c4-146">När ett ER-format har utformats för att innehålla information som ändras när formatet körs måste formatet vara obligatoriskt för användning av funktionen ER-baslinje för att jämföra genererade resultat med baslinjevärden.</span><span class="sxs-lookup"><span data-stu-id="e52c4-146">When an ER format has been designed to contain information that is changed when the format is run, the format must be required to use the ER baseline feature to compare the generated results with baseline values.</span></span> <span data-ttu-id="e52c4-147">Informationen kan till exempel vara bearbetningsdatum och -tid eller en unik identifierare för ett genererat dokument i olika format (globala unika identifieraren\[GUID\] och så vidare).</span><span class="sxs-lookup"><span data-stu-id="e52c4-147">For example, the information might be the processing date and time or the unique identifier of a generated document in different formats (globally unique identifier \[GUID\], and so on).</span></span> <span data-ttu-id="e52c4-148">Med de nya ER-funktionerna kan du konfigurera baslijeregler så att den ignorerar ändringsbara element i ett ER- format när formatet körs med syftet att jämföra baslinjevärden med resultatet av formatets körning.</span><span class="sxs-lookup"><span data-stu-id="e52c4-148">The new ER capabilities let you configure the baseline rule so that it ignores changeable elements of an ER format when the format is run with the purpose of comparing baseline values with the results of the format's execution.</span></span> <span data-ttu-id="e52c4-149">Om du vill veta mer om den här funktionen fyller du i följande exempel.</span><span class="sxs-lookup"><span data-stu-id="e52c4-149">To learn more about this feature, complete the following example.</span></span>

## <a name="example-configure-the-baseline-so-that-it-ignores-constantly-changing-parts-of-the-er-output"></a><span data-ttu-id="e52c4-150">Exempel: Konfigurera baslinjen så att den ignorerar konstant ändring av delar av ER-resultat</span><span class="sxs-lookup"><span data-stu-id="e52c4-150">Example: Configure the baseline so that it ignores constantly changing parts of the ER output</span></span>

<span data-ttu-id="e52c4-151">Om du vill slutföra stegen i det här exemplet måste du först slutföra stegen i exemplet i [Spåra skapade rapportresultat och jämföra dem med baslinjevärden](er-trace-reports-compare-baseline.md).</span><span class="sxs-lookup"><span data-stu-id="e52c4-151">To complete the steps in this example, you must first complete the steps in the example in the [Trace generated report results and compare them with baseline values](er-trace-reports-compare-baseline.md) topic.</span></span>

### <a name="modify-a-configured-er-format"></a><span data-ttu-id="e52c4-152">Ändra ett konfigurerat ER-format</span><span class="sxs-lookup"><span data-stu-id="e52c4-152">Modify a configured ER format</span></span>

1. <span data-ttu-id="e52c4-153">Gå till **Organisationsadministration** \> **Elektronisk rapportering** \> **Konfigurationer**.</span><span class="sxs-lookup"><span data-stu-id="e52c4-153">Go to **Organization administration** \> **Electronic reporting** \> **Configurations**.</span></span>
2. <span data-ttu-id="e52c4-154">I trädet expanderar du **modell för att lära sig ER-baslinjer**.</span><span class="sxs-lookup"><span data-stu-id="e52c4-154">In the tree, expand **Model to learn ER baselines**.</span></span>
3. <span data-ttu-id="e52c4-155">Välj **modell för att lära dig ER-baslinjer\\format för att lära dig ER-baslinjer**.</span><span class="sxs-lookup"><span data-stu-id="e52c4-155">In the tree, select **Model to learn ER baselines\\Format to learn ER baselines**.</span></span>
4. <span data-ttu-id="e52c4-156">Välj **Designer**.</span><span class="sxs-lookup"><span data-stu-id="e52c4-156">Select **Designer**.</span></span>
5. <span data-ttu-id="e52c4-157">I trädet, välj **Utdata\\Dokument**.</span><span class="sxs-lookup"><span data-stu-id="e52c4-157">In the tree, select **Output\\Document**.</span></span>
6. <span data-ttu-id="e52c4-158">Markera **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="e52c4-158">Select **Add**.</span></span>
7. <span data-ttu-id="e52c4-159">I listrutan i trädet väljer du **XML\\Attribut**.</span><span class="sxs-lookup"><span data-stu-id="e52c4-159">In the drop-down dialog box, in the tree, select **XML\\Attribute**.</span></span>
8. <span data-ttu-id="e52c4-160">I fältet **Namn** anger du **ProcessingDateTime**.</span><span class="sxs-lookup"><span data-stu-id="e52c4-160">In the **Name** field, enter **ProcessingDateTime**.</span></span>
9. <span data-ttu-id="e52c4-161">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="e52c4-161">Select **OK**.</span></span>
10. <span data-ttu-id="e52c4-162">På fliken **Mappning** i trädet väljer du **Resultat\\Dokument\\ProcessingDateTime**.</span><span class="sxs-lookup"><span data-stu-id="e52c4-162">On the **Mapping** tab, in the tree, select **Output\\Document\\ProcessingDateTime**.</span></span>
11. <span data-ttu-id="e52c4-163">Välj **Redigera recept**.</span><span class="sxs-lookup"><span data-stu-id="e52c4-163">Select **Edit formula**.</span></span>
12. <span data-ttu-id="e52c4-164">I fältet **Formel** anger du följande uttryck: **DATETIMEFORMAT(NOW(), "O")**</span><span class="sxs-lookup"><span data-stu-id="e52c4-164">In the **Formula** field, enter the following expression: **DATETIMEFORMAT(NOW(), "O")**</span></span>
13. <span data-ttu-id="e52c4-165">Välj **spara**och välj sedan **test**.</span><span class="sxs-lookup"><span data-stu-id="e52c4-165">Select **Save**, and then select **Test**.</span></span>
14. <span data-ttu-id="e52c4-166">Välj **test** igen om du vill testa om det konfigurerade uttrycket.</span><span class="sxs-lookup"><span data-stu-id="e52c4-166">Select **Test** again to retest the configured expression.</span></span>

    <span data-ttu-id="e52c4-167">![Sidan formeldesigner](media/GER-BaselineSample-DefineProcessingDTExpression.PNG "Skärmbild av sidan formeldesigner")</span><span class="sxs-lookup"><span data-stu-id="e52c4-167">![Formula designer page](media/GER-BaselineSample-DefineProcessingDTExpression.PNG "Screenshot of the Formula designer page")</span></span>

    > [!NOTE]
    > <span data-ttu-id="e52c4-168">På fliken **testresultat** visas att det konfigurerade uttrycket returnerar ett annat datum- och tidsvärde när det anropas.</span><span class="sxs-lookup"><span data-stu-id="e52c4-168">The **Test result** tab shows that the configured expression returns a different date and time value whenever it's called.</span></span>

15. <span data-ttu-id="e52c4-169">Stäng sidan **Formeldesigner** och välj sedan **Spara**.</span><span class="sxs-lookup"><span data-stu-id="e52c4-169">Close the **Formula designer** page, and then select **Save**.</span></span>

    <span data-ttu-id="e52c4-170">![Sidan formatdesigner](media/GER-BaselineSample-FormatMappingDesign2.PNG "Skärmbild av sidan formatdesigner")</span><span class="sxs-lookup"><span data-stu-id="e52c4-170">![Format designer page](media/GER-BaselineSample-FormatMappingDesign2.PNG "Screenshot of the Format designer page")</span></span>

16. <span data-ttu-id="e52c4-171">Stäng sidan **Formatdesigner**.</span><span class="sxs-lookup"><span data-stu-id="e52c4-171">Close the **Format designer** page.</span></span>

### <a name="remove-an-existing-baseline-rule"></a><span data-ttu-id="e52c4-172">Ta bort en befintlig baslinjeregel</span><span class="sxs-lookup"><span data-stu-id="e52c4-172">Remove an existing baseline rule</span></span>

1. <span data-ttu-id="e52c4-173">Gå till **Organisationsadministration** \> **Elektronisk rapportering** \> **Konfigurationer**.</span><span class="sxs-lookup"><span data-stu-id="e52c4-173">Go to **Organization administration** \> **Electronic reporting** \> **Configurations**.</span></span>
2. <span data-ttu-id="e52c4-174">Välj **baslinjer**.</span><span class="sxs-lookup"><span data-stu-id="e52c4-174">Select **Baselines**.</span></span>
3. <span data-ttu-id="e52c4-175">I listan över baslinjer väljer du den baslinje som har konfigurerats för formatet **Format för att lära sig ER-baslinjer**.</span><span class="sxs-lookup"><span data-stu-id="e52c4-175">In the list of baselines, select the baseline that is configured for the **Format to learn ER baselines** format.</span></span>
4. <span data-ttu-id="e52c4-176">På snabbfliken **baslinjer** väljer du **ta bort** för att ta bort den baslinjeregel som du konfigurerade tidigare.</span><span class="sxs-lookup"><span data-stu-id="e52c4-176">On the **Baselines** FastTab, select **Delete** to remove the baseline rule that you configured earlier.</span></span>

<span data-ttu-id="e52c4-177">![Sidan Baslinjer med elektroniskt rapporteringsformat](media/GER-BaselineSample-AddBaseline3.PNG "Skärmbild av sidan Baslinjer med elektroniskt rapporteringsformat")</span><span class="sxs-lookup"><span data-stu-id="e52c4-177">![Electronic reporting format baselines page](media/GER-BaselineSample-AddBaseline3.PNG "Screenshot of the Electronic reporting format baselines page")</span></span>

### <a name="define-replacements-for-bindings-of-designed-er-format"></a><span data-ttu-id="e52c4-178">Definiera ersättningar för bindningar av utformade ER-format</span><span class="sxs-lookup"><span data-stu-id="e52c4-178">Define replacements for bindings of designed ER format</span></span>

1. <span data-ttu-id="e52c4-179">På sidan **konfigurationer** på snabbfliken **ersättningar**, välj **välj komponenter**.</span><span class="sxs-lookup"><span data-stu-id="e52c4-179">On the **Configurations** page, on the **Replacements** FastTab, select **Select components**.</span></span>
2. <span data-ttu-id="e52c4-180">I trädet formatkomponenter expanderar du **Utdata**, expanderar **Utdata\\dokument** och markerar sedan kryssrutan **Utdata\\dokument\\ProcessingDateTime**.</span><span class="sxs-lookup"><span data-stu-id="e52c4-180">In the format components tree, expand **Output**, expand **Output\\Document**, and then select the check box for **Output\\Document\\ProcessingDateTime**.</span></span>

    <span data-ttu-id="e52c4-181">![Dialogrutan välj komponenter](media/GER-BaselineSample-SelectComponentForBindingReplacement.PNG "Skärmbild av dialogrutan välj komponenter")</span><span class="sxs-lookup"><span data-stu-id="e52c4-181">![Select Components dialog box](media/GER-BaselineSample-SelectComponentForBindingReplacement.PNG "Screenshot of the Select Components dialog box")</span></span>

3. <span data-ttu-id="e52c4-182">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="e52c4-182">Select **OK**.</span></span>

<span data-ttu-id="e52c4-183">![Sidan Baslinjer med elektroniskt rapporteringsformat](media/GER-BaselineSample-AddBaseline4.PNG "Skärmbild av sidan Baslinjer med elektroniskt rapporteringsformat")</span><span class="sxs-lookup"><span data-stu-id="e52c4-183">![Electronic reporting format baselines page](media/GER-BaselineSample-AddBaseline4.PNG "Screenshot of the Electronic reporting format baselines page")</span></span>

<span data-ttu-id="e52c4-184">Den valda ER-formatkomponenten har lagts till i listan över komponenter på snabbfliken **ersättningar**.</span><span class="sxs-lookup"><span data-stu-id="e52c4-184">The selected ER format component has been added to the list of components on the **Replacements** FastTab.</span></span> <span data-ttu-id="e52c4-185">När bas-ER-formatet körs i felsökningsläge ersätts formatets bindning för varje komponent med bindningen som visas i kolumnen **bindning**.</span><span class="sxs-lookup"><span data-stu-id="e52c4-185">When the base ER format is run in debug mode, the format's binding for each component will be replaced by the binding that is shown in the **Binding** column.</span></span> <span data-ttu-id="e52c4-186">Om du vill ändra standardbindningen för en komponent som visas på snabbfliken **ersättningar** väljer du **redigera**.</span><span class="sxs-lookup"><span data-stu-id="e52c4-186">To change the default binding for a component that is listed on the **Replacements** FastTab, select **Edit**.</span></span>

### <a name="make-a-new-baseline-rule"></a><span data-ttu-id="e52c4-187">Skapa en ny baslinjeregel</span><span class="sxs-lookup"><span data-stu-id="e52c4-187">Make a new baseline rule</span></span>

<span data-ttu-id="e52c4-188">Följ stegen i avsnittet "exempel: automatisera inställningen av baslinjeregler" ovan i det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="e52c4-188">Follow the steps in the "Example: Automate the setting of baseline rules" section earlier in this topic.</span></span> <span data-ttu-id="e52c4-189">Ett meddelande visas med en varning om att den utgående filen har genererats med hjälp av inställningar för baslinje och att formatbindningarna har bytts ut.</span><span class="sxs-lookup"><span data-stu-id="e52c4-189">A notification warns you that the outbound file has been generated by using baseline settings, and that a forced replacement of the format bindings has occurred.</span></span>

<span data-ttu-id="e52c4-190">![Meddelande på sidan Konfigurationer](media/GER-BaselineSample-FormatRunToMakeBaselineFile4.PNG "Skärmbild av meddelande på sidan Konfigurationer")</span><span class="sxs-lookup"><span data-stu-id="e52c4-190">![Notification on the Configurations page](media/GER-BaselineSample-FormatRunToMakeBaselineFile4.PNG "Screenshot of the notification on the Configurations page")</span></span>

### <a name="suppress-warnings-about-the-replacement-of-format-bindings"></a><span data-ttu-id="e52c4-191">Ignorera varningar om byte av formatbindningar</span><span class="sxs-lookup"><span data-stu-id="e52c4-191">Suppress warnings about the replacement of format bindings</span></span>

<span data-ttu-id="e52c4-192">Genom att ställa in specifika ER-parametrar kan du utelämna meddelanden som varnar vid byte av formatbindningar.</span><span class="sxs-lookup"><span data-stu-id="e52c4-192">By setting specific ER parameters, you can suppress notifications that warn about the replacement of format bindings.</span></span> <span data-ttu-id="e52c4-193">Denna undertryckning kan vara användbar när formatbindningar ersätts i obevakat läge med hjälp av Regression Suite Automation Tool.</span><span class="sxs-lookup"><span data-stu-id="e52c4-193">This suppression can be useful when format bindings are replaced in an unattended mode by using the Regression Suite Automation Tool.</span></span> <span data-ttu-id="e52c4-194">I det här fallet kan varningen betraktas som ett fel i testfallet som körs.</span><span class="sxs-lookup"><span data-stu-id="e52c4-194">In this case, the warning can be considered a failure of the test case that is running.</span></span>

1. <span data-ttu-id="e52c4-195">På sidan **Konfigurationer** i åtgärdsfönstret, på fliken **Konfigurationer** markerar du **Använd parametrar**.</span><span class="sxs-lookup"><span data-stu-id="e52c4-195">On the **Configurations** page, on the Action Pane, on the **Configurations** tab, select **User parameters**.</span></span>
2. <span data-ttu-id="e52c4-196">Ange alternativet **Undertryck baslinjevarningar** till **Ja** och välj sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="e52c4-196">Set the **Suppress baseline warnings** option to **Yes**, and then select **OK**.</span></span>

<span data-ttu-id="e52c4-197">![Dialogrutan användarparametrar](media/GER-BaselineSample-ERUserParameters1.png "Skärmbild av ialogrutan användarparametrar")</span><span class="sxs-lookup"><span data-stu-id="e52c4-197">![User parameters dialog box](media/GER-BaselineSample-ERUserParameters1.png "Screenshot of the User parameters dialog box")</span></span>

### <a name="review-the-generated-baseline-file"></a><span data-ttu-id="e52c4-198">Granska den skapade baslinjefilen.</span><span class="sxs-lookup"><span data-stu-id="e52c4-198">Review the generated baseline file</span></span>

1. <span data-ttu-id="e52c4-199">Gå till **Organisationsadministration** \> **Elektronisk rapportering** \> **Konfigurationer**.</span><span class="sxs-lookup"><span data-stu-id="e52c4-199">Go to **Organization administration** \> **Electronic reporting** \> **Configurations**.</span></span>
2. <span data-ttu-id="e52c4-200">Välj **baslinjer**.</span><span class="sxs-lookup"><span data-stu-id="e52c4-200">Select **Baselines**.</span></span>
3. <span data-ttu-id="e52c4-201">Välj **bilagor**.</span><span class="sxs-lookup"><span data-stu-id="e52c4-201">Select **Attachments**.</span></span>

    <span data-ttu-id="e52c4-202">![Sidan Bilagor](media/GER-BaselineSample-AttachedBaselineFile.PNG "Skärmbild av sidan Bilagor")</span><span class="sxs-lookup"><span data-stu-id="e52c4-202">![Attachments page](media/GER-BaselineSample-AttachedBaselineFile.PNG "Screenshot of the Attachments page")</span></span>

    > [!NOTE]
    > <span data-ttu-id="e52c4-203">Den genererade filen innehåller bearbetningsdatumet och tidstexten (**"#"**) från bindningen som konfigurerats i den tillagda baslinjeregeln, inte från formatets bindning.</span><span class="sxs-lookup"><span data-stu-id="e52c4-203">The generated file contains the processing date and time text (**"#"**) from the binding that was configured in the added baseline rule, not from the format's binding.</span></span>

4. <span data-ttu-id="e52c4-204">Stäng sidan **Bilagor**.</span><span class="sxs-lookup"><span data-stu-id="e52c4-204">Close the **Attachments** page.</span></span>

### <a name="run-the-designed-er-format-and-review-the-log-to-analyze-the-results"></a><span data-ttu-id="e52c4-205">Kör det utformade ER-formatet och granska loggen för att analysera resultaten</span><span class="sxs-lookup"><span data-stu-id="e52c4-205">Run the designed ER format and review the log to analyze the results</span></span>

1. <span data-ttu-id="e52c4-206">Gå till **Organisationsadministration** \> **Elektronisk rapportering** \> **Konfigurationer**.</span><span class="sxs-lookup"><span data-stu-id="e52c4-206">Go to **Organization administration** \> **Electronic reporting** \> **Configurations**.</span></span>
2. <span data-ttu-id="e52c4-207">I trädet expanderar du **modell för att lära sig ER-baslinjer**.</span><span class="sxs-lookup"><span data-stu-id="e52c4-207">In the tree, expand **Model to learn ER baselines**.</span></span>
3. <span data-ttu-id="e52c4-208">Välj **modell för att lära dig ER-baslinjer\\format för att lära dig ER-baslinjer**.</span><span class="sxs-lookup"><span data-stu-id="e52c4-208">In the tree, select **Model to learn ER baselines\\Format to learn ER baselines**.</span></span>
4. <span data-ttu-id="e52c4-209">Klicka på **Kör** på snabbfliken **Versioner**.</span><span class="sxs-lookup"><span data-stu-id="e52c4-209">On the **Versions** FastTab select **Run**.</span></span>
5. <span data-ttu-id="e52c4-210">I fältet **Ange Id** anger du **1**.</span><span class="sxs-lookup"><span data-stu-id="e52c4-210">In the **Enter Id** field, type **1**.</span></span>
6. <span data-ttu-id="e52c4-211">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="e52c4-211">Select **OK**.</span></span>
7. <span data-ttu-id="e52c4-212">Gå till **Organisationsadministration** \> **Elektronisk rapportering** \> **Konfiguration av felsökningsloggar**.</span><span class="sxs-lookup"><span data-stu-id="e52c4-212">Go to **Organization administration** \> **Electronic reporting** \> **Configuration debug logs**.</span></span>

<span data-ttu-id="e52c4-213">Körningsloggen innehåller information om resultaten av jämförelsen mellan den genererade filen och den konfigurerade baslinjen.</span><span class="sxs-lookup"><span data-stu-id="e52c4-213">The execution log contains information about the results of the comparison of the generated file with the configured baseline.</span></span> <span data-ttu-id="e52c4-214">Loggen anger att den genererade filen och baslinjen är lika även om det körda formatet innehåller bindningen för att ange ett konstant värde för datum och tid i den utgående filen.</span><span class="sxs-lookup"><span data-stu-id="e52c4-214">The log indicates that the generated file and the baseline are equal, even though the executed format contains the binding to enter a constantly changing date and time value in the outbound file.</span></span>

> [!NOTE]
> <span data-ttu-id="e52c4-215">Även om den utgående filen har genererats med hjälp av inställningar för baslinje som tvingar fram bindningar av formatets bindningar, får du inga varningar om ersättningen.</span><span class="sxs-lookup"><span data-stu-id="e52c4-215">Although the outbound file has been generated by using baseline settings that force the replacement of the format's bindings, you don't receive any warnings about the replacement.</span></span>

## <a name="exchange-baseline-settings-between-environments"></a><span data-ttu-id="e52c4-216">Inställningar för byte av baslinjeinstllningar mellan miljöer</span><span class="sxs-lookup"><span data-stu-id="e52c4-216">Exchange baseline settings between environments</span></span>

### <a name="export-baseline-settings"></a><span data-ttu-id="e52c4-217">Exportera baslinjeinställningar</span><span class="sxs-lookup"><span data-stu-id="e52c4-217">Export baseline settings</span></span>

<span data-ttu-id="e52c4-218">Med de nya ER-funktionerna kan du exportera baslinjeinställningar för det valda ER-formatet från den aktuella Finance and Operations-miljön och lagra dem som XML-filer.</span><span class="sxs-lookup"><span data-stu-id="e52c4-218">The new ER capabilities let you export baseline settings for the selected ER format from the current Finance and Operations environment and store them as XML files.</span></span> 

<span data-ttu-id="e52c4-219">Om du vill exportera inställningar väljer du på sidan **Baslinjer med elektroniskt rapporteringsformat** **Exportera**.</span><span class="sxs-lookup"><span data-stu-id="e52c4-219">To export baseline settings, on the **Electronic reporting format baselines** page, select **Export**.</span></span>

### <a name="import-baseline-settings"></a><span data-ttu-id="e52c4-220">Importera baslinjeinställningar</span><span class="sxs-lookup"><span data-stu-id="e52c4-220">Import baseline settings</span></span>

<span data-ttu-id="e52c4-221">Exporterade baslinjeinställningar kan importeras till en annan Finance and Operations-miljö.</span><span class="sxs-lookup"><span data-stu-id="e52c4-221">Exported baseline settings can be imported into a different Finance and Operations environment.</span></span> <span data-ttu-id="e52c4-222">Miljön måste först importeras som ett ER-format.</span><span class="sxs-lookup"><span data-stu-id="e52c4-222">The environment must first be imported as an ER format.</span></span> <span data-ttu-id="e52c4-223">Du kan sedan importera baslinjeinställningarna.</span><span class="sxs-lookup"><span data-stu-id="e52c4-223">You can then import the baseline settings.</span></span>

<span data-ttu-id="e52c4-224">Om du vill importera baslinjeinställningar från en lokalt lagrad XML-fil väljer du **Baslinjer med elektroniskt rapporteringsformat** och **Importera** och sedan **bläddra** för att välja XML-filen.</span><span class="sxs-lookup"><span data-stu-id="e52c4-224">To import baseline settings from a locally stored XML file, on the **Electronic reporting format baselines** page, select **Import**, and then select **Browse** to select the XML file.</span></span>

<span data-ttu-id="e52c4-225">![Dialogrutan Importera baslinjeinställningar](media/GER-BaselineSample-ImportBaseline1.PNG "Skärmbild av dialogrutan Importera baslinjeinställningar")</span><span class="sxs-lookup"><span data-stu-id="e52c4-225">![Import baseline settings dialog box](media/GER-BaselineSample-ImportBaseline1.PNG "Screenshot of the Import baseline settings dialog box")</span></span>

<span data-ttu-id="e52c4-226">Om du vill importera baslinjeinställningar från en XML-fil som är lagrad på Microsoft SharePoint-servern, baserat på de aktuella dokumenthanteringsinställningarna och den valda dokumenttypen väljer du sidan **Baslinjer med elektroniskt rapporteringsformat** och sedan **Importera från källa**.</span><span class="sxs-lookup"><span data-stu-id="e52c4-226">To import baseline settings from an XML file that is stored on the Microsoft SharePoint Server, based on the current Document management settings and the selected document type, on the **Electronic reporting format baselines** page, select **Import from source**.</span></span> <span data-ttu-id="e52c4-227">Välj sedan dokumenttyp och XML-fil.</span><span class="sxs-lookup"><span data-stu-id="e52c4-227">Then select the document type and the XML file.</span></span> <span data-ttu-id="e52c4-228">Den dokumenttyp som krävs för åtkomst SharePoint-mappen måste konfigureras i förväg.</span><span class="sxs-lookup"><span data-stu-id="e52c4-228">The required document type to access the SharePoint folder must be configured in advance.</span></span>

<span data-ttu-id="e52c4-229">![Dialogrutan Importera från källa](media/GER-BaselineSample-ImportBaseline2.PNG "Skärmbild av dialogrutan Importera från källa")</span><span class="sxs-lookup"><span data-stu-id="e52c4-229">![Import from source dialog box](media/GER-BaselineSample-ImportBaseline2.PNG "Screenshot of the Import from source dialog box")</span></span>

> [!NOTE]
> <span data-ttu-id="e52c4-230">Du kan använda uppgiftsregistrering för att registrera stegen för att välja önskad dokumenttyp och filnamnet i dialogrutan **importera från källa**.</span><span class="sxs-lookup"><span data-stu-id="e52c4-230">You can use Task recorder to record the steps for selecting the required document type and the file name in the **Import from source** dialog box.</span></span> <span data-ttu-id="e52c4-231">På det här sättet kan du behålla de nödvändiga baslinjeinställningarna på SharePoint-servern och sedan automatiskt importera dem genom att spela upp en uppgiftsinspelning när du kör automatiserade tester med hjälp av Regression Suite Automation Tool.</span><span class="sxs-lookup"><span data-stu-id="e52c4-231">In this way, you can keep required baseline settings on SharePoint Server and then automatically import them by playing a task recording when you run automated tests by using the Regression Suite Automation Tool.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="e52c4-232">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="e52c4-232">Additional resources</span></span>

- [<span data-ttu-id="e52c4-233">Spåra skapade rapportresultat och jämföra dem med baslinjevärden</span><span class="sxs-lookup"><span data-stu-id="e52c4-233">Trace generated report results and compare them with baseline values</span></span>](er-trace-reports-compare-baseline.md)
- [<span data-ttu-id="e52c4-234">Uppgiftsregistrering</span><span class="sxs-lookup"><span data-stu-id="e52c4-234">Task recorder</span></span>](../user-interface/task-recorder.md)
