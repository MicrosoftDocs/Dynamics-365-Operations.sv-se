---
title: Förbättra spårningsresultat av genererade ER-rapporter för att jämföra med originalvärden
description: Det här ämnet beskriver förbättringar av ER-baslinjefunktionen i Microsoft Dynamics 365 for Finance and Operations version 10.0.3 (juni 2019).
author: NickSelin
ms.date: 06/19/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: 220314
ms.assetid: 2685df16-5ec8-4fd7-9495-c0f653e82567
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2018-04-01
ms.dyn365.ops.version: Release 8.0
ms.openlocfilehash: 49ca9a878b9289b02f9bb9346190425197e0ceea
ms.sourcegitcommit: 53b797ff1b524f581046b48cdde42f50b37495bc
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/28/2021
ms.locfileid: "6117045"
---
# <a name="improve-tracing-the-results-of-generated-er-reports-to-compare-with-baseline-values"></a><span data-ttu-id="f6ba2-103">Förbättra spårningsresultat av genererade ER-rapporter för att jämföra med originalvärden</span><span class="sxs-lookup"><span data-stu-id="f6ba2-103">Improve tracing the results of generated ER reports to compare with baseline values</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="f6ba2-104">I det här avsnittet beskrivs den första uppsättningen med förbättringar av funktionen för baslinje i det elektroniska rapportramverket (ER).</span><span class="sxs-lookup"><span data-stu-id="f6ba2-104">This topic describes the first set of improvements that have been made to the baseline feature of the Electronic reporting (ER) framework.</span></span> <span data-ttu-id="f6ba2-105">Dessa förbättringar finns i Microsoft Dynamics 365 for Finance and Operations version 10.0.3 (juni 2019) och senare.</span><span class="sxs-lookup"><span data-stu-id="f6ba2-105">These improvements are available in Microsoft Dynamics 365 for Finance and Operations version 10.0.3 (June 2019) and later.</span></span>

## <a name="automate-the-setting-of-baseline-rules"></a><span data-ttu-id="f6ba2-106">Automatisera inställningen av baslinjeregler</span><span class="sxs-lookup"><span data-stu-id="f6ba2-106">Automate the setting of baseline rules</span></span>

<span data-ttu-id="f6ba2-107">Ämnet [Spårningsgenererade rapportresultat och jämföra dem med baslinjevärden](er-trace-reports-compare-baseline.md) beskriver hur du konfigurerar ER-ramverket för insamling av information om ER-formatering och utvärdering av resultaten av dessa körningar.</span><span class="sxs-lookup"><span data-stu-id="f6ba2-107">The [Trace generated report results and compare them with baseline values](er-trace-reports-compare-baseline.md) topic explains how to configure the ER framework to collect information about ER format executions and evaluate the results of those executions.</span></span> <span data-ttu-id="f6ba2-108">I exemplet i det här avsnittet visas de steg som måste utföras.</span><span class="sxs-lookup"><span data-stu-id="f6ba2-108">The example in this topic shows the steps that must be completed.</span></span>

<span data-ttu-id="f6ba2-109">Här följer några steg:</span><span class="sxs-lookup"><span data-stu-id="f6ba2-109">Here are some of the steps:</span></span>

- <span data-ttu-id="f6ba2-110">Kör ett ER-format för att skapa en utgående fil och spara filen lokalt.</span><span class="sxs-lookup"><span data-stu-id="f6ba2-110">Run an ER format to generate an outbound file, and store the file locally.</span></span>
- <span data-ttu-id="f6ba2-111">Lägg till den lokalt lagrade filen som en bilaga till den baslinje som lades till för ER-format.</span><span class="sxs-lookup"><span data-stu-id="f6ba2-111">Add the locally stored file as an attachment of the baseline that was added for an ER format.</span></span>
- <span data-ttu-id="f6ba2-112">Konfigurera baslinjergeln för den tillagda baslinjen.</span><span class="sxs-lookup"><span data-stu-id="f6ba2-112">Configure the baseline rule for the added baseline.</span></span> <span data-ttu-id="f6ba2-113">Den här konfigurationen omfattar följande steg:</span><span class="sxs-lookup"><span data-stu-id="f6ba2-113">This configuration includes the following steps:</span></span>

    - <span data-ttu-id="f6ba2-114">Ange ett ER-formatelement som används för att generera en utgående fil.</span><span class="sxs-lookup"><span data-stu-id="f6ba2-114">Specify an ER format element that is used to generate an outbound file.</span></span>
    - <span data-ttu-id="f6ba2-115">Markera den bilaga som refererar till den genererade utgående filen.</span><span class="sxs-lookup"><span data-stu-id="f6ba2-115">Select the attachment that refers to the generated outbound file.</span></span>

> [!NOTE]
> <span data-ttu-id="f6ba2-116">Du måste utföra dessa steg manuellt, även om de nya ER-funktionerna gör det möjligt att automatisera dem.</span><span class="sxs-lookup"><span data-stu-id="f6ba2-116">These steps must be done manually, even though the new ER capabilities enable them to be automated.</span></span> <span data-ttu-id="f6ba2-117">Om du vill veta mer om den här funktionen fyller du i följande exempel.</span><span class="sxs-lookup"><span data-stu-id="f6ba2-117">To learn more about this feature, complete the following example.</span></span>

## <a name="example-automate-the-setting-of-baseline-rules"></a><span data-ttu-id="f6ba2-118">Exempel: Automatisera inställningen av baslinjeregler</span><span class="sxs-lookup"><span data-stu-id="f6ba2-118">Example: Automate the setting of baseline rules</span></span>

<span data-ttu-id="f6ba2-119">Om du vill slutföra stegen i det här exemplet måste du först slutföra stegen i exemplet i [Spåra skapade rapportresultat och jämföra dem med baslinjevärden](er-trace-reports-compare-baseline.md) i avsnittet "lägga till en ny baslinjeplan för ett utformat ER-format".</span><span class="sxs-lookup"><span data-stu-id="f6ba2-119">To complete the steps in this example, you must first complete the steps in the example in the [Trace generated report results and compare them with baseline values](er-trace-reports-compare-baseline.md) topic, up through the "Add a new baseline for a designed ER format" section.</span></span>

### <a name="review-added-baseline"></a><span data-ttu-id="f6ba2-120">Granska tillagda baslinjer</span><span class="sxs-lookup"><span data-stu-id="f6ba2-120">Review added baseline</span></span>

1. <span data-ttu-id="f6ba2-121">Gå till **Organisationsadministration** \> **Elektronisk rapportering** \> **Konfigurationer**.</span><span class="sxs-lookup"><span data-stu-id="f6ba2-121">Go to **Organization administration** \> **Electronic reporting** \> **Configurations**.</span></span>
2. <span data-ttu-id="f6ba2-122">Välj **baslinjer**.</span><span class="sxs-lookup"><span data-stu-id="f6ba2-122">Select **Baselines**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="f6ba2-123">Knappen **baslinjer** i åtgärdsfönstret är bara tillgänglig om parametern **kör i felsökningsläge** ER-användarparameter är aktiverad för det aktuella företaget.</span><span class="sxs-lookup"><span data-stu-id="f6ba2-123">The **Baselines** button on the Action Pane is available only when the **Run in debug mode** ER user parameter is turned on for the current company.</span></span>

<span data-ttu-id="f6ba2-124">Baslinjen har lagts till för det valda formatet **Format för att lära ER-baslinjer** men baslinjereglerna har ännu inte lagts till för denna baslinje.</span><span class="sxs-lookup"><span data-stu-id="f6ba2-124">The baseline has been added for the selected **Format to learn ER baselines** format, but the baseline rules haven't yet been added for this baseline.</span></span>

<span data-ttu-id="f6ba2-125">![Sidan Baslinjer med elektroniskt rapporteringsformat, inga regler ännu](media/GER-BaselineSample-AddBaseline2.PNG "Skärmbild av sidan Baslinjer med elektroniskt rapporteringsformat")</span><span class="sxs-lookup"><span data-stu-id="f6ba2-125">![Electronic reporting format baselines page, no rules yet](media/GER-BaselineSample-AddBaseline2.PNG "Screenshot of the Electronic reporting format baselines page")</span></span>

### <a name="make-a-new-baseline-rule"></a><span data-ttu-id="f6ba2-126">Skapa en ny baslinjeregel</span><span class="sxs-lookup"><span data-stu-id="f6ba2-126">Make a new baseline rule</span></span>

1. <span data-ttu-id="f6ba2-127">Gå till **Organisationsadministration** \> **Elektronisk rapportering** \> **Konfigurationer**.</span><span class="sxs-lookup"><span data-stu-id="f6ba2-127">Go to **Organization administration** \> **Electronic reporting** \> **Configurations**.</span></span>
2. <span data-ttu-id="f6ba2-128">I trädet expanderar du **modell för att lära sig ER-baslinjer**.</span><span class="sxs-lookup"><span data-stu-id="f6ba2-128">In the tree, expand **Model to learn ER baselines**.</span></span>
3. <span data-ttu-id="f6ba2-129">Välj **modell för att lära dig ER-baslinjer\\format för att lära dig ER-baslinjer**.</span><span class="sxs-lookup"><span data-stu-id="f6ba2-129">In the tree, select **Model to learn ER baselines\\Format to learn ER baselines**.</span></span>
4. <span data-ttu-id="f6ba2-130">Klicka på **Kör** på snabbfliken **Versioner**.</span><span class="sxs-lookup"><span data-stu-id="f6ba2-130">On the **Versions** FastTab, select **Run**.</span></span>
5. <span data-ttu-id="f6ba2-131">I fältet **Ange Id** anger du **1**.</span><span class="sxs-lookup"><span data-stu-id="f6ba2-131">In the **Enter Id** field, enter **1**.</span></span>
6. <span data-ttu-id="f6ba2-132">Ställ in alternativet **gör baslinjefiler** till **Ja**.</span><span class="sxs-lookup"><span data-stu-id="f6ba2-132">Set the **Make baseline files** option to **Yes**.</span></span>
7. <span data-ttu-id="f6ba2-133">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="f6ba2-133">Select **OK**.</span></span>
8. <span data-ttu-id="f6ba2-134">Välj **baslinjer**.</span><span class="sxs-lookup"><span data-stu-id="f6ba2-134">Select **Baselines**.</span></span>

    <span data-ttu-id="f6ba2-135">![Sidan Baslinjer med elektroniskt rapporteringsformat, baslinjer valda](media/GER-BaselineSample-ReviewAddedBaselineLine.PNG "Skärmbild av sidan Baslinjer med elektroniskt rapporteringsformat")</span><span class="sxs-lookup"><span data-stu-id="f6ba2-135">![Electronic reporting format baselines page, baselines selected](media/GER-BaselineSample-ReviewAddedBaselineLine.PNG "Screenshot of the Electronic reporting format baselines page")</span></span>

    <span data-ttu-id="f6ba2-136">Den genererade utgående filen har automatiskt kopplats till baslinjen för det körda ER-formatet.</span><span class="sxs-lookup"><span data-stu-id="f6ba2-136">The generated outbound file has been automatically attached to the baseline of the executed ER format.</span></span> <span data-ttu-id="f6ba2-137">Baslinjeregeln läggs automatiskt till i denna baslinje och innehåller också referensen till den bifogade filen.</span><span class="sxs-lookup"><span data-stu-id="f6ba2-137">The baseline rule has been automatically added to this baseline and also contains the reference to the attached file.</span></span>

9. <span data-ttu-id="f6ba2-138">Skriv **Baslinje 1** i fältet **Namn**.</span><span class="sxs-lookup"><span data-stu-id="f6ba2-138">In the **Name** field, enter **Baseline 1**.</span></span>
10. <span data-ttu-id="f6ba2-139">I fältet **Filnamnmask**, ange **.xml**.</span><span class="sxs-lookup"><span data-stu-id="f6ba2-139">In the **File name mask** field, enter **.xml**.</span></span>
11. <span data-ttu-id="f6ba2-140">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="f6ba2-140">Select **Save**.</span></span>

### <a name="run-the-format"></a><span data-ttu-id="f6ba2-141">Kör formatet</span><span class="sxs-lookup"><span data-stu-id="f6ba2-141">Run the format</span></span>

<span data-ttu-id="f6ba2-142">Du är nu redo att slutföra de återstående stegen i exemplet i [Spåra skapade rapportresultat och jämföra dem med baslinjevärden](er-trace-reports-compare-baseline.md) med hjälp av avsnittet "kör det utformade ER-formatet och granska loggen för analys av resultaten".</span><span class="sxs-lookup"><span data-stu-id="f6ba2-142">You're now ready to complete the remaining steps in the example in the [Trace generated report results and compare them with baseline values](er-trace-reports-compare-baseline.md) topic, starting from the "Run the designed ER format and review the log to analyze the results" section.</span></span>

> [!NOTE]
> <span data-ttu-id="f6ba2-143">När du tar bort den automatiskt tillagda baslinjeregeln på snabbfliken **Baslinjer** tas refererade bifogade filer inte bort automatiskt.</span><span class="sxs-lookup"><span data-stu-id="f6ba2-143">When you delete the automatically added baseline rule on the **Baselines** FastTab, the referenced attachment isn't automatically deleted.</span></span>

## <a name="configure-the-baseline-so-that-it-ignores-constantly-changing-parts-of-the-er-output"></a><span data-ttu-id="f6ba2-144">Konfigurera baslinjen så att den ignorerar konstant ändring av delar av ER-resultat</span><span class="sxs-lookup"><span data-stu-id="f6ba2-144">Configure the baseline so that it ignores constantly changing parts of the ER output</span></span>

<span data-ttu-id="f6ba2-145">När ett ER-format har utformats för att innehålla information som ändras när formatet körs måste formatet vara obligatoriskt för användning av funktionen ER-baslinje för att jämföra genererade resultat med baslinjevärden.</span><span class="sxs-lookup"><span data-stu-id="f6ba2-145">When an ER format has been designed to contain information that is changed when the format is run, the format must be required to use the ER baseline feature to compare the generated results with baseline values.</span></span> <span data-ttu-id="f6ba2-146">Informationen kan till exempel vara bearbetningsdatum och -tid eller en unik identifierare för ett genererat dokument i olika format (globala unika identifieraren\[GUID\] och så vidare).</span><span class="sxs-lookup"><span data-stu-id="f6ba2-146">For example, the information might be the processing date and time or the unique identifier of a generated document in different formats (globally unique identifier \[GUID\], and so on).</span></span> <span data-ttu-id="f6ba2-147">Med de nya ER-funktionerna kan du konfigurera baslijeregler så att den ignorerar ändringsbara element i ett ER- format när formatet körs med syftet att jämföra baslinjevärden med resultatet av formatets körning.</span><span class="sxs-lookup"><span data-stu-id="f6ba2-147">The new ER capabilities let you configure the baseline rule so that it ignores changeable elements of an ER format when the format is run with the purpose of comparing baseline values with the results of the format's execution.</span></span> <span data-ttu-id="f6ba2-148">Om du vill veta mer om den här funktionen fyller du i följande exempel.</span><span class="sxs-lookup"><span data-stu-id="f6ba2-148">To learn more about this feature, complete the following example.</span></span>

## <a name="example-configure-the-baseline-so-that-it-ignores-constantly-changing-parts-of-the-er-output"></a><span data-ttu-id="f6ba2-149">Exempel: Konfigurera baslinjen så att den ignorerar konstant ändring av delar av ER-resultat</span><span class="sxs-lookup"><span data-stu-id="f6ba2-149">Example: Configure the baseline so that it ignores constantly changing parts of the ER output</span></span>

<span data-ttu-id="f6ba2-150">Om du vill slutföra stegen i det här exemplet måste du först slutföra stegen i exemplet i [Spåra skapade rapportresultat och jämföra dem med baslinjevärden](er-trace-reports-compare-baseline.md).</span><span class="sxs-lookup"><span data-stu-id="f6ba2-150">To complete the steps in this example, you must first complete the steps in the example in the [Trace generated report results and compare them with baseline values](er-trace-reports-compare-baseline.md) topic.</span></span>

### <a name="modify-a-configured-er-format"></a><span data-ttu-id="f6ba2-151">Ändra ett konfigurerat ER-format</span><span class="sxs-lookup"><span data-stu-id="f6ba2-151">Modify a configured ER format</span></span>

1. <span data-ttu-id="f6ba2-152">Gå till **Organisationsadministration** \> **Elektronisk rapportering** \> **Konfigurationer**.</span><span class="sxs-lookup"><span data-stu-id="f6ba2-152">Go to **Organization administration** \> **Electronic reporting** \> **Configurations**.</span></span>
2. <span data-ttu-id="f6ba2-153">I trädet expanderar du **modell för att lära sig ER-baslinjer**.</span><span class="sxs-lookup"><span data-stu-id="f6ba2-153">In the tree, expand **Model to learn ER baselines**.</span></span>
3. <span data-ttu-id="f6ba2-154">Välj **modell för att lära dig ER-baslinjer\\format för att lära dig ER-baslinjer**.</span><span class="sxs-lookup"><span data-stu-id="f6ba2-154">In the tree, select **Model to learn ER baselines\\Format to learn ER baselines**.</span></span>
4. <span data-ttu-id="f6ba2-155">Välj **Designer**.</span><span class="sxs-lookup"><span data-stu-id="f6ba2-155">Select **Designer**.</span></span>
5. <span data-ttu-id="f6ba2-156">I trädet, välj **Utdata\\Dokument**.</span><span class="sxs-lookup"><span data-stu-id="f6ba2-156">In the tree, select **Output\\Document**.</span></span>
6. <span data-ttu-id="f6ba2-157">Markera **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="f6ba2-157">Select **Add**.</span></span>
7. <span data-ttu-id="f6ba2-158">I listrutan i trädet väljer du **XML\\Attribut**.</span><span class="sxs-lookup"><span data-stu-id="f6ba2-158">In the drop-down dialog box, in the tree, select **XML\\Attribute**.</span></span>
8. <span data-ttu-id="f6ba2-159">I fältet **Namn** anger du **ProcessingDateTime**.</span><span class="sxs-lookup"><span data-stu-id="f6ba2-159">In the **Name** field, enter **ProcessingDateTime**.</span></span>
9. <span data-ttu-id="f6ba2-160">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="f6ba2-160">Select **OK**.</span></span>
10. <span data-ttu-id="f6ba2-161">På fliken **Mappning** i trädet väljer du **Resultat\\Dokument\\ProcessingDateTime**.</span><span class="sxs-lookup"><span data-stu-id="f6ba2-161">On the **Mapping** tab, in the tree, select **Output\\Document\\ProcessingDateTime**.</span></span>
11. <span data-ttu-id="f6ba2-162">Välj **Redigera recept**.</span><span class="sxs-lookup"><span data-stu-id="f6ba2-162">Select **Edit formula**.</span></span>
12. <span data-ttu-id="f6ba2-163">I fältet **Formel** anger du följande uttryck: **DATETIMEFORMAT(NOW(), "O")**</span><span class="sxs-lookup"><span data-stu-id="f6ba2-163">In the **Formula** field, enter the following expression: **DATETIMEFORMAT(NOW(), "O")**</span></span>
13. <span data-ttu-id="f6ba2-164">Välj **spara** och välj sedan **test**.</span><span class="sxs-lookup"><span data-stu-id="f6ba2-164">Select **Save**, and then select **Test**.</span></span>
14. <span data-ttu-id="f6ba2-165">Välj **test** igen om du vill testa om det konfigurerade uttrycket.</span><span class="sxs-lookup"><span data-stu-id="f6ba2-165">Select **Test** again to retest the configured expression.</span></span>

    <span data-ttu-id="f6ba2-166">![Sidan Formeldesigner](media/GER-BaselineSample-DefineProcessingDTExpression.PNG "Skärmbild av sidan Formeldesigner")</span><span class="sxs-lookup"><span data-stu-id="f6ba2-166">![Formula designer page](media/GER-BaselineSample-DefineProcessingDTExpression.PNG "Screenshot of the Formula designer page")</span></span>

    > [!NOTE]
    > <span data-ttu-id="f6ba2-167">På fliken **testresultat** visas att det konfigurerade uttrycket returnerar ett annat datum- och tidsvärde när det anropas.</span><span class="sxs-lookup"><span data-stu-id="f6ba2-167">The **Test result** tab shows that the configured expression returns a different date and time value whenever it's called.</span></span>

15. <span data-ttu-id="f6ba2-168">Stäng sidan **Formeldesigner** och välj sedan **Spara**.</span><span class="sxs-lookup"><span data-stu-id="f6ba2-168">Close the **Formula designer** page, and then select **Save**.</span></span>

    <span data-ttu-id="f6ba2-169">![Formatdesignersida](media/GER-BaselineSample-FormatMappingDesign2.PNG "Skärmbild av sidan Formatdesigner")</span><span class="sxs-lookup"><span data-stu-id="f6ba2-169">![Format designer page](media/GER-BaselineSample-FormatMappingDesign2.PNG "Screenshot of the Format designer page")</span></span>

16. <span data-ttu-id="f6ba2-170">Stäng sidan **Formatdesigner**.</span><span class="sxs-lookup"><span data-stu-id="f6ba2-170">Close the **Format designer** page.</span></span>

### <a name="remove-an-existing-baseline-rule"></a><span data-ttu-id="f6ba2-171">Ta bort en befintlig baslinjeregel</span><span class="sxs-lookup"><span data-stu-id="f6ba2-171">Remove an existing baseline rule</span></span>

1. <span data-ttu-id="f6ba2-172">Gå till **Organisationsadministration** \> **Elektronisk rapportering** \> **Konfigurationer**.</span><span class="sxs-lookup"><span data-stu-id="f6ba2-172">Go to **Organization administration** \> **Electronic reporting** \> **Configurations**.</span></span>
2. <span data-ttu-id="f6ba2-173">Välj **baslinjer**.</span><span class="sxs-lookup"><span data-stu-id="f6ba2-173">Select **Baselines**.</span></span>
3. <span data-ttu-id="f6ba2-174">I listan över baslinjer väljer du den baslinje som har konfigurerats för formatet **Format för att lära sig ER-baslinjer**.</span><span class="sxs-lookup"><span data-stu-id="f6ba2-174">In the list of baselines, select the baseline that is configured for the **Format to learn ER baselines** format.</span></span>
4. <span data-ttu-id="f6ba2-175">På snabbfliken **baslinjer** väljer du **ta bort** för att ta bort den baslinjeregel som du konfigurerade tidigare.</span><span class="sxs-lookup"><span data-stu-id="f6ba2-175">On the **Baselines** FastTab, select **Delete** to remove the baseline rule that you configured earlier.</span></span>

<span data-ttu-id="f6ba2-176">![Sidan Baslinjer med elektroniskt rapporteringsformat, borttagen](media/GER-BaselineSample-AddBaseline3.PNG "Skärmbild av sidan Baslinjer med elektroniskt rapporteringsformat")</span><span class="sxs-lookup"><span data-stu-id="f6ba2-176">![Electronic reporting format baselines page, deleted](media/GER-BaselineSample-AddBaseline3.PNG "Screenshot of the Electronic reporting format baselines page")</span></span>

### <a name="define-replacements-for-bindings-of-designed-er-format"></a><span data-ttu-id="f6ba2-177">Definiera ersättningar för bindningar av utformade ER-format</span><span class="sxs-lookup"><span data-stu-id="f6ba2-177">Define replacements for bindings of designed ER format</span></span>

1. <span data-ttu-id="f6ba2-178">På sidan **konfigurationer** på snabbfliken **ersättningar**, välj **välj komponenter**.</span><span class="sxs-lookup"><span data-stu-id="f6ba2-178">On the **Configurations** page, on the **Replacements** FastTab, select **Select components**.</span></span>
2. <span data-ttu-id="f6ba2-179">I trädet formatkomponenter expanderar du **Utdata**, expanderar **Utdata\\dokument** och markerar sedan kryssrutan **Utdata\\dokument\\ProcessingDateTime**.</span><span class="sxs-lookup"><span data-stu-id="f6ba2-179">In the format components tree, expand **Output**, expand **Output\\Document**, and then select the check box for **Output\\Document\\ProcessingDateTime**.</span></span>
3. <span data-ttu-id="f6ba2-180">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="f6ba2-180">Select **OK**.</span></span>

<span data-ttu-id="f6ba2-181">![Sidan Baslinjer med elektroniskt rapporteringsformat, komponenter](media/GER-BaselineSample-AddBaseline4.PNG "Skärmbild av sidan Baslinjer med elektroniskt rapporteringsformat")</span><span class="sxs-lookup"><span data-stu-id="f6ba2-181">![Electronic reporting format baselines page, components](media/GER-BaselineSample-AddBaseline4.PNG "Screenshot of the Electronic reporting format baselines page")</span></span>

<span data-ttu-id="f6ba2-182">Den valda ER-formatkomponenten har lagts till i listan över komponenter på snabbfliken **ersättningar**.</span><span class="sxs-lookup"><span data-stu-id="f6ba2-182">The selected ER format component has been added to the list of components on the **Replacements** FastTab.</span></span> <span data-ttu-id="f6ba2-183">När bas-ER-formatet körs i felsökningsläge ersätts formatets bindning för varje komponent med bindningen som visas i kolumnen **bindning**.</span><span class="sxs-lookup"><span data-stu-id="f6ba2-183">When the base ER format is run in debug mode, the format's binding for each component will be replaced by the binding that is shown in the **Binding** column.</span></span> <span data-ttu-id="f6ba2-184">Om du vill ändra standardbindningen för en komponent som visas på snabbfliken **ersättningar** väljer du **redigera**.</span><span class="sxs-lookup"><span data-stu-id="f6ba2-184">To change the default binding for a component that is listed on the **Replacements** FastTab, select **Edit**.</span></span>

### <a name="make-a-new-baseline-rule"></a><span data-ttu-id="f6ba2-185">Skapa en ny baslinjeregel</span><span class="sxs-lookup"><span data-stu-id="f6ba2-185">Make a new baseline rule</span></span>

<span data-ttu-id="f6ba2-186">Följ stegen i avsnittet "exempel: automatisera inställningen av baslinjeregler" ovan i det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="f6ba2-186">Follow the steps in the "Example: Automate the setting of baseline rules" section earlier in this topic.</span></span> <span data-ttu-id="f6ba2-187">Ett meddelande visas med en varning om att den utgående filen har genererats med hjälp av inställningar för baslinje och att formatbindningarna har bytts ut.</span><span class="sxs-lookup"><span data-stu-id="f6ba2-187">A notification warns you that the outbound file has been generated by using baseline settings, and that a forced replacement of the format bindings has occurred.</span></span>

<span data-ttu-id="f6ba2-188">![Meddelande på sidan Konfigurationer](media/GER-BaselineSample-FormatRunToMakeBaselineFile4.PNG "Skärmbild av meddelande på sidan Konfigurationer")</span><span class="sxs-lookup"><span data-stu-id="f6ba2-188">![Notification on the Configurations page](media/GER-BaselineSample-FormatRunToMakeBaselineFile4.PNG "Screenshot of the notification on the Configurations page")</span></span>

### <a name="suppress-warnings-about-the-replacement-of-format-bindings"></a><span data-ttu-id="f6ba2-189">Ignorera varningar om byte av formatbindningar</span><span class="sxs-lookup"><span data-stu-id="f6ba2-189">Suppress warnings about the replacement of format bindings</span></span>

<span data-ttu-id="f6ba2-190">Genom att ställa in specifika ER-parametrar kan du utelämna meddelanden som varnar vid byte av formatbindningar.</span><span class="sxs-lookup"><span data-stu-id="f6ba2-190">By setting specific ER parameters, you can suppress notifications that warn about the replacement of format bindings.</span></span> <span data-ttu-id="f6ba2-191">Denna undertryckning kan vara användbar när formatbindningar ersätts i obevakat läge med hjälp av Regression Suite Automation Tool.</span><span class="sxs-lookup"><span data-stu-id="f6ba2-191">This suppression can be useful when format bindings are replaced in an unattended mode by using the Regression Suite Automation Tool.</span></span> <span data-ttu-id="f6ba2-192">I det här fallet kan varningen betraktas som ett fel i testfallet som körs.</span><span class="sxs-lookup"><span data-stu-id="f6ba2-192">In this case, the warning can be considered a failure of the test case that is running.</span></span>

1. <span data-ttu-id="f6ba2-193">På sidan **Konfigurationer** i åtgärdsfönstret, på fliken **Konfigurationer** markerar du **Använd parametrar**.</span><span class="sxs-lookup"><span data-stu-id="f6ba2-193">On the **Configurations** page, on the Action Pane, on the **Configurations** tab, select **User parameters**.</span></span>
2. <span data-ttu-id="f6ba2-194">Ange alternativet **Undertryck baslinjevarningar** till **Ja** och välj sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="f6ba2-194">Set the **Suppress baseline warnings** option to **Yes**, and then select **OK**.</span></span>

### <a name="review-the-generated-baseline-file"></a><span data-ttu-id="f6ba2-195">Granska den skapade baslinjefilen.</span><span class="sxs-lookup"><span data-stu-id="f6ba2-195">Review the generated baseline file</span></span>

1. <span data-ttu-id="f6ba2-196">Gå till **Organisationsadministration** \> **Elektronisk rapportering** \> **Konfigurationer**.</span><span class="sxs-lookup"><span data-stu-id="f6ba2-196">Go to **Organization administration** \> **Electronic reporting** \> **Configurations**.</span></span>
2. <span data-ttu-id="f6ba2-197">Välj **baslinjer**.</span><span class="sxs-lookup"><span data-stu-id="f6ba2-197">Select **Baselines**.</span></span>
3. <span data-ttu-id="f6ba2-198">Välj **bilagor**.</span><span class="sxs-lookup"><span data-stu-id="f6ba2-198">Select **Attachments**.</span></span>
    > [!NOTE]
    > <span data-ttu-id="f6ba2-199">Den genererade filen innehåller bearbetningsdatumet och tidstexten (**"#"**) från bindningen som konfigurerats i den tillagda baslinjeregeln, inte från formatets bindning.</span><span class="sxs-lookup"><span data-stu-id="f6ba2-199">The generated file contains the processing date and time text (**"#"**) from the binding that was configured in the added baseline rule, not from the format's binding.</span></span>
    
4. <span data-ttu-id="f6ba2-200">Stäng sidan **Bilagor**.</span><span class="sxs-lookup"><span data-stu-id="f6ba2-200">Close the **Attachments** page.</span></span>

### <a name="run-the-designed-er-format-and-review-the-log-to-analyze-the-results"></a><span data-ttu-id="f6ba2-201">Kör det utformade ER-formatet och granska loggen för att analysera resultaten</span><span class="sxs-lookup"><span data-stu-id="f6ba2-201">Run the designed ER format and review the log to analyze the results</span></span>

1. <span data-ttu-id="f6ba2-202">Gå till **Organisationsadministration** \> **Elektronisk rapportering** \> **Konfigurationer**.</span><span class="sxs-lookup"><span data-stu-id="f6ba2-202">Go to **Organization administration** \> **Electronic reporting** \> **Configurations**.</span></span>
2. <span data-ttu-id="f6ba2-203">I trädet expanderar du **modell för att lära sig ER-baslinjer**.</span><span class="sxs-lookup"><span data-stu-id="f6ba2-203">In the tree, expand **Model to learn ER baselines**.</span></span>
3. <span data-ttu-id="f6ba2-204">Välj **modell för att lära dig ER-baslinjer\\format för att lära dig ER-baslinjer**.</span><span class="sxs-lookup"><span data-stu-id="f6ba2-204">In the tree, select **Model to learn ER baselines\\Format to learn ER baselines**.</span></span>
4. <span data-ttu-id="f6ba2-205">Klicka på **Kör** på snabbfliken **Versioner**.</span><span class="sxs-lookup"><span data-stu-id="f6ba2-205">On the **Versions** FastTab select **Run**.</span></span>
5. <span data-ttu-id="f6ba2-206">I fältet **Ange Id** anger du **1**.</span><span class="sxs-lookup"><span data-stu-id="f6ba2-206">In the **Enter Id** field, type **1**.</span></span>
6. <span data-ttu-id="f6ba2-207">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="f6ba2-207">Select **OK**.</span></span>
7. <span data-ttu-id="f6ba2-208">Gå till **Organisationsadministration** \> **Elektronisk rapportering** \> **Konfiguration av felsökningsloggar**.</span><span class="sxs-lookup"><span data-stu-id="f6ba2-208">Go to **Organization administration** \> **Electronic reporting** \> **Configuration debug logs**.</span></span>

<span data-ttu-id="f6ba2-209">Körningsloggen innehåller information om resultaten av jämförelsen mellan den genererade filen och den konfigurerade baslinjen.</span><span class="sxs-lookup"><span data-stu-id="f6ba2-209">The execution log contains information about the results of the comparison of the generated file with the configured baseline.</span></span> <span data-ttu-id="f6ba2-210">Loggen anger att den genererade filen och baslinjen är lika även om det körda formatet innehåller bindningen för att ange ett konstant värde för datum och tid i den utgående filen.</span><span class="sxs-lookup"><span data-stu-id="f6ba2-210">The log indicates that the generated file and the baseline are equal, even though the executed format contains the binding to enter a constantly changing date and time value in the outbound file.</span></span>

> [!NOTE]
> <span data-ttu-id="f6ba2-211">Även om den utgående filen har genererats med hjälp av inställningar för baslinje som tvingar fram bindningar av formatets bindningar, får du inga varningar om ersättningen.</span><span class="sxs-lookup"><span data-stu-id="f6ba2-211">Although the outbound file has been generated by using baseline settings that force the replacement of the format's bindings, you don't receive any warnings about the replacement.</span></span>

## <a name="exchange-baseline-settings-between-environments"></a><span data-ttu-id="f6ba2-212">Inställningar för byte av baslinjeinstllningar mellan miljöer</span><span class="sxs-lookup"><span data-stu-id="f6ba2-212">Exchange baseline settings between environments</span></span>

### <a name="export-baseline-settings"></a><span data-ttu-id="f6ba2-213">Exportera baslinjeinställningar</span><span class="sxs-lookup"><span data-stu-id="f6ba2-213">Export baseline settings</span></span>

<span data-ttu-id="f6ba2-214">Med de nya ER-funktionerna kan du exportera baslinjeinställningar för det valda ER-formatet från den aktuella miljön och lagra dem som XML-filer.</span><span class="sxs-lookup"><span data-stu-id="f6ba2-214">The new ER capabilities let you export baseline settings for the selected ER format from the current environment and store them as XML files.</span></span> 

<span data-ttu-id="f6ba2-215">Om du vill exportera inställningar väljer du på sidan **Baslinjer med elektroniskt rapporteringsformat** **Exportera**.</span><span class="sxs-lookup"><span data-stu-id="f6ba2-215">To export baseline settings, on the **Electronic reporting format baselines** page, select **Export**.</span></span>

### <a name="import-baseline-settings"></a><span data-ttu-id="f6ba2-216">Importera baslinjeinställningar</span><span class="sxs-lookup"><span data-stu-id="f6ba2-216">Import baseline settings</span></span>

<span data-ttu-id="f6ba2-217">Exporterade baslinjeinställningar kan importeras till en annan miljö.</span><span class="sxs-lookup"><span data-stu-id="f6ba2-217">Exported baseline settings can be imported into a different environment.</span></span> <span data-ttu-id="f6ba2-218">Miljön måste först importeras som ett ER-format.</span><span class="sxs-lookup"><span data-stu-id="f6ba2-218">The environment must first be imported as an ER format.</span></span> <span data-ttu-id="f6ba2-219">Du kan sedan importera baslinjeinställningarna.</span><span class="sxs-lookup"><span data-stu-id="f6ba2-219">You can then import the baseline settings.</span></span>

<span data-ttu-id="f6ba2-220">Om du vill importera baslinjeinställningar från en lokalt lagrad XML-fil väljer du **Baslinjer med elektroniskt rapporteringsformat** och **Importera** och sedan **bläddra** för att välja XML-filen.</span><span class="sxs-lookup"><span data-stu-id="f6ba2-220">To import baseline settings from a locally stored XML file, on the **Electronic reporting format baselines** page, select **Import**, and then select **Browse** to select the XML file.</span></span>

<span data-ttu-id="f6ba2-221">![Dialogrutan Importera baslinjeinställningar](media/GER-BaselineSample-ImportBaseline1.PNG "Skärmbild av dialogrutan Importera baslinjeinställningar")</span><span class="sxs-lookup"><span data-stu-id="f6ba2-221">![Import baseline settings dialog box](media/GER-BaselineSample-ImportBaseline1.PNG "Screenshot of the Import baseline settings dialog box")</span></span>

<span data-ttu-id="f6ba2-222">Om du vill importera baslinjeinställningar från en XML-fil som är lagrad på Microsoft SharePoint-servern, baserat på de aktuella dokumenthanteringsinställningarna och den valda dokumenttypen väljer du sidan **Baslinjer med elektroniskt rapporteringsformat** och sedan **Importera från källa**.</span><span class="sxs-lookup"><span data-stu-id="f6ba2-222">To import baseline settings from an XML file that is stored on the Microsoft SharePoint Server, based on the current Document management settings and the selected document type, on the **Electronic reporting format baselines** page, select **Import from source**.</span></span> <span data-ttu-id="f6ba2-223">Välj sedan dokumenttyp och XML-fil.</span><span class="sxs-lookup"><span data-stu-id="f6ba2-223">Then select the document type and the XML file.</span></span> <span data-ttu-id="f6ba2-224">Den dokumenttyp som krävs för åtkomst SharePoint-mappen måste konfigureras i förväg.</span><span class="sxs-lookup"><span data-stu-id="f6ba2-224">The required document type to access the SharePoint folder must be configured in advance.</span></span>

<span data-ttu-id="f6ba2-225">![Dialogrutan Importera från källa](media/GER-BaselineSample-ImportBaseline2.PNG "Skärmbild av dialogrutan Importera från källa")</span><span class="sxs-lookup"><span data-stu-id="f6ba2-225">![Import from source dialog box](media/GER-BaselineSample-ImportBaseline2.PNG "Screenshot of the Import from source dialog box")</span></span>

> [!NOTE]
> <span data-ttu-id="f6ba2-226">Du kan använda uppgiftsregistrering för att registrera stegen för att välja önskad dokumenttyp och filnamnet i dialogrutan **importera från källa**.</span><span class="sxs-lookup"><span data-stu-id="f6ba2-226">You can use Task recorder to record the steps for selecting the required document type and the file name in the **Import from source** dialog box.</span></span> <span data-ttu-id="f6ba2-227">På det här sättet kan du behålla de nödvändiga baslinjeinställningarna på SharePoint-servern och sedan automatiskt importera dem genom att spela upp en uppgiftsinspelning när du kör automatiserade tester med hjälp av Regression Suite Automation Tool.</span><span class="sxs-lookup"><span data-stu-id="f6ba2-227">In this way, you can keep required baseline settings on SharePoint Server and then automatically import them by playing a task recording when you run automated tests by using the Regression Suite Automation Tool.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="f6ba2-228">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="f6ba2-228">Additional resources</span></span>

- [<span data-ttu-id="f6ba2-229">Spåra genererade rapportresultat och jämför dem med baslinjevärden</span><span class="sxs-lookup"><span data-stu-id="f6ba2-229">Trace generated report results and compare them with baseline values</span></span>](er-trace-reports-compare-baseline.md)
- [<span data-ttu-id="f6ba2-230">Uppgiftsinspelarresurser</span><span class="sxs-lookup"><span data-stu-id="f6ba2-230">Task recorder resources</span></span>](../user-interface/task-recorder.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
