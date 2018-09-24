---
title: "Rapportdefinitioner i designer för ekonomiska rapporter"
description: "En raddefinition är en rapportkomponent eller byggblock som anger innehållet på varje rad i en ekonomisk rapport. En raddefinition kan kombineras med kolumndefinitioner, rapportträddefinitioner och rapportdefinitioner för att skapa en byggblocksgrupp som kan användas av flera företag."
author: aprilolson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
ms.search.form: FinancialReports
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 68873
ms.assetid: 2fd7b5da-700f-48cb-9003-90c0d82f818f
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 821d8927211d7ac3e479848c7e7bef9f650d4340
ms.openlocfilehash: c829af1da1b3109f4687c9a2536dd156339d5c76
ms.contentlocale: sv-se
ms.lasthandoff: 08/13/2018

---

# <a name="row-definitions-in-financial-report-designer"></a><span data-ttu-id="7c4f4-104">Rapportdefinitioner i designer för ekonomiska rapporter</span><span class="sxs-lookup"><span data-stu-id="7c4f4-104">Row definitions in financial report designer</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="7c4f4-105">En raddefinition är en rapportkomponent eller byggblock som anger innehållet på varje rad i en ekonomisk rapport.</span><span class="sxs-lookup"><span data-stu-id="7c4f4-105">A row definition is a report component, or building block, that specifies the contents of each row on a financial report.</span></span> <span data-ttu-id="7c4f4-106">En raddefinition kan kombineras med kolumndefinitioner, rapportträddefinitioner och rapportdefinitioner för att skapa en byggblocksgrupp som kan användas av flera företag.</span><span class="sxs-lookup"><span data-stu-id="7c4f4-106">A row definition can be combined with column definitions, reporting tree definitions, and report definitions to create a building block group that can be used by multiple companies.</span></span>

## <a name="create-a-row-definition"></a><span data-ttu-id="7c4f4-107">Skapa en raddefinition</span><span class="sxs-lookup"><span data-stu-id="7c4f4-107">Create a row definition</span></span>

1. <span data-ttu-id="7c4f4-108">Klicka på **Raddefinitioner** i navigeringsfönstret i Report Designer.</span><span class="sxs-lookup"><span data-stu-id="7c4f4-108">In Report Designer, in the navigation pane, click **Row Definitions**.</span></span>
2. <span data-ttu-id="7c4f4-109">Gå till menyn **Fil** och klicka först på **Ny** och sedan på **Raddefinition**.</span><span class="sxs-lookup"><span data-stu-id="7c4f4-109">On the **File** menu, click **New**, and then click **Row Definition**.</span></span> <span data-ttu-id="7c4f4-110">Mer information om innehållet i varje cell finns på [Ändra definitionscell](modify-row-definition-cells-financial-reporting.md).</span><span class="sxs-lookup"><span data-stu-id="7c4f4-110">For more information about the content of each cell, see [Modify row definition cells](modify-row-definition-cells-financial-reporting.md).</span></span>

## <a name="open-a-row-definition"></a><span data-ttu-id="7c4f4-111">Öppna en raddefinition</span><span class="sxs-lookup"><span data-stu-id="7c4f4-111">Open a row definition</span></span>
1. <span data-ttu-id="7c4f4-112">Klicka på **Raddefinitioner** i navigeringsfönstret i Report Designer.</span><span class="sxs-lookup"><span data-stu-id="7c4f4-112">In Report Designer, in the navigation pane, click **Row Definitions**.</span></span>
2. <span data-ttu-id="7c4f4-113">Dubbelklicka på namnet på raddefinitionen som du vill öppna.</span><span class="sxs-lookup"><span data-stu-id="7c4f4-113">Double-click the name of the row definition to open.</span></span>
3. <span data-ttu-id="7c4f4-114">Om du vill visa alla byggblock som är associerade med raddefinitionen, högerklicka på raddefinitionen och välj sedan **Associationer**.</span><span class="sxs-lookup"><span data-stu-id="7c4f4-114">To view any building blocks that are associated with the row definition, right-click the row definition, and then select **Associations**.</span></span>

## <a name="contents-of-a-row-definition"></a><span data-ttu-id="7c4f4-115"> Innehåll i en raddefinition</span><span class="sxs-lookup"><span data-stu-id="7c4f4-115">Contents of a row definition</span></span>
<span data-ttu-id="7c4f4-116">En raddefinition kan innehålla upp till 20 000 rader för ekonomiska dimensioner och kan innehålla följande information:</span><span class="sxs-lookup"><span data-stu-id="7c4f4-116">A row definition can contain up to 20,000 financial dimension rows and can include the following information:</span></span>

- <span data-ttu-id="7c4f4-117">Beskrivande text som tillför något till rapporten genom att skapa avsnittsrubriker, rader och mellanslag såsom **Kontant** eller **Total intäkt**</span><span class="sxs-lookup"><span data-stu-id="7c4f4-117">Descriptive text that adds meaning to the report by creating section headings, lines, and spaces, such as **Cash** or **Total Revenue**</span></span>
- <span data-ttu-id="7c4f4-118">Länkar till ekonomiska data, vilket kan omfatta dimensionsvärden i Microsoft Dynamics 365 for Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="7c4f4-118">Links to financial data, which can include dimension values in the Microsoft Dynamics 365 for Finance and Operations</span></span>

    > [!NOTE]
    > <span data-ttu-id="7c4f4-119">Du kan konfigurera en raddefinition så att data hämtas från det ekonomiska dimensionssystemet varje gång rapporten genereras.</span><span class="sxs-lookup"><span data-stu-id="7c4f4-119">You can set up a row definition to pull data from the financial dimensions system every time that the report is generated.</span></span>

- <span data-ttu-id="7c4f4-120">Radsummor och formler som baseras på kopplade ekonomiska data.</span><span class="sxs-lookup"><span data-stu-id="7c4f4-120">Row totals and formulas that are based on the linked financial data</span></span>

<span data-ttu-id="7c4f4-121">Vanligtvis innehåller alla raddefinition innehåller en av följande typer av information:</span><span class="sxs-lookup"><span data-stu-id="7c4f4-121">Usually, each row in a row definition contains one of the following types of information:</span></span>

- <span data-ttu-id="7c4f4-122">Referenser till systemet för ekonomiska dimensioner</span><span class="sxs-lookup"><span data-stu-id="7c4f4-122">References to the financial dimensions system</span></span>
- <span data-ttu-id="7c4f4-123">Summor eller beräkningar som är baserade på data</span><span class="sxs-lookup"><span data-stu-id="7c4f4-123">Totals or calculations that are based on the data</span></span>
- <span data-ttu-id="7c4f4-124">Formatering</span><span class="sxs-lookup"><span data-stu-id="7c4f4-124">Formatting</span></span>

<span data-ttu-id="7c4f4-125">Det finns två metoder för att lägga till information i en raddefinition:</span><span class="sxs-lookup"><span data-stu-id="7c4f4-125">There are two methods for entering information in a row definition:</span></span>

- <span data-ttu-id="7c4f4-126">Ange information om raden manuellt i en ny raddefinition.</span><span class="sxs-lookup"><span data-stu-id="7c4f4-126">Manually enter row information in a new row definition.</span></span> <span data-ttu-id="7c4f4-127">Mer information finns i [Ändra raddefinitionceller](modify-row-definition-cells-financial-reporting.md).</span><span class="sxs-lookup"><span data-stu-id="7c4f4-127">For more information, see [Modify row definition cells](modify-row-definition-cells-financial-reporting.md).</span></span>
- <span data-ttu-id="7c4f4-128">Använd rapportdesigner för att hämta radinformation direkt från de ekonomiska dimensionerna.</span><span class="sxs-lookup"><span data-stu-id="7c4f4-128">Use report designer to pull row information directly from the financial dimensions.</span></span> <span data-ttu-id="7c4f4-129">Mer information hittar du i avsnittet "Relaterade formler/rader/enheter" i [Modifiera raddefinitionsceller](modify-row-definition-cells-financial-reporting.md).</span><span class="sxs-lookup"><span data-stu-id="7c4f4-129">For more information, see the "Related formulas/rows/units" section in [Modify row definition cells](modify-row-definition-cells-financial-reporting.md).</span></span>

## <a name="add-dimensions-in-a-row-definition"></a><span data-ttu-id="7c4f4-130"> Lägg till dimensioner i en raddefinition</span><span class="sxs-lookup"><span data-stu-id="7c4f4-130">Add dimensions in a row definition</span></span>
<span data-ttu-id="7c4f4-131">En dimension är en skärningspunkt av data och värden.</span><span class="sxs-lookup"><span data-stu-id="7c4f4-131">A dimension is an intersection of data and values.</span></span> <span data-ttu-id="7c4f4-132">Du kan gruppera data och värden i rapportdesignern.</span><span class="sxs-lookup"><span data-stu-id="7c4f4-132">You can group data and values in report designer.</span></span> <span data-ttu-id="7c4f4-133">Du kan sedan klassificera och analysera transaktioner mer ingående.</span><span class="sxs-lookup"><span data-stu-id="7c4f4-133">You can then classify and analyze transactions in more detail.</span></span> <span data-ttu-id="7c4f4-134">Du kan använda dialogrutan **Infoga rader från dimensioner** om du vill lägga till flera rader i en raddefinition samtidigt.</span><span class="sxs-lookup"><span data-stu-id="7c4f4-134">You can use the **Insert Rows from Dimensions** dialog box to add multiple rows to a row definition at the same time.</span></span> <span data-ttu-id="7c4f4-135">Dialogrutan visar en kolumn för varje dimension.</span><span class="sxs-lookup"><span data-stu-id="7c4f4-135">The dialog box displays one column for each dimension.</span></span> <span data-ttu-id="7c4f4-136">I tabellen nedan beskrivs den typ av information som kan anges för varje dimension.</span><span class="sxs-lookup"><span data-stu-id="7c4f4-136">The following table describes the information that you can specify for each dimension.</span></span>

| <span data-ttu-id="7c4f4-137">Alternativ</span><span class="sxs-lookup"><span data-stu-id="7c4f4-137">Option</span></span>                | <span data-ttu-id="7c4f4-138">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="7c4f4-138">Description</span></span> |
|-----------------------|-------------|
| <span data-ttu-id="7c4f4-139">Dimension</span><span class="sxs-lookup"><span data-stu-id="7c4f4-139">Dimension</span></span>             | <span data-ttu-id="7c4f4-140">Mönstret som identifierar den dimension du vill lägga till raddefinitionen.</span><span class="sxs-lookup"><span data-stu-id="7c4f4-140">The pattern that identifies the dimension to add to the row definition.</span></span> <span data-ttu-id="7c4f4-141">Detta mönster innehåller ett et-tecken (&) eller nummertecknet (\#) för varje position i dimensionerna.</span><span class="sxs-lookup"><span data-stu-id="7c4f4-141">This pattern contains one ampersand (&) or number sign (\#) for each position in the dimensions.</span></span> <span data-ttu-id="7c4f4-142">Rent allmänt bör du använda et-tecken för dimensionen Huvudkonto och siffertecken för alla andra dimensioner.</span><span class="sxs-lookup"><span data-stu-id="7c4f4-142">Generally, use all ampersands for the Main Account dimension and all number signs for other dimensions.</span></span> |
| <span data-ttu-id="7c4f4-143">Dimensionsintervallets början</span><span class="sxs-lookup"><span data-stu-id="7c4f4-143">Dimension Range Start</span></span> | <span data-ttu-id="7c4f4-144">Dimensionens inledande värde som ska läggas till i raddefinitionen.</span><span class="sxs-lookup"><span data-stu-id="7c4f4-144">The first value for this dimension to add to the row definition.</span></span> |
| <span data-ttu-id="7c4f4-145">Dimensionsintervallets slut</span><span class="sxs-lookup"><span data-stu-id="7c4f4-145">Dimension Range End</span></span>   | <span data-ttu-id="7c4f4-146">Det sista värdet för denna dimension för att lägga till raddefinitionen.</span><span class="sxs-lookup"><span data-stu-id="7c4f4-146">The last value for this dimension to add to the row definition.</span></span> |

<span data-ttu-id="7c4f4-147">Gör på följande sätt för att lägga till dimensioner i en raddefinition:</span><span class="sxs-lookup"><span data-stu-id="7c4f4-147">To add dimensions to a row definition, follow these steps.</span></span>

1. <span data-ttu-id="7c4f4-148">Öppna Rapport Designer, klicka på **Raddefinitioner** och öppna sedan den raddefinition som ska modifieras.</span><span class="sxs-lookup"><span data-stu-id="7c4f4-148">In Report Designer, click **Row Definitions**, and then open the row definition to modify.</span></span>
2. <span data-ttu-id="7c4f4-149">Klicka på menyn **Redigera** och klicka på **Infoga rapportenheter från dimensioner**.</span><span class="sxs-lookup"><span data-stu-id="7c4f4-149">On the **Edit** menu, click **Insert Rows from Dimensions**.</span></span>
3. <span data-ttu-id="7c4f4-150">I dialogrutan **Infoga rader från Dimensioner**, på raden **Dimensioner**, väljer du cellen för dimensionen som ska överföras till raddefinitionen och klickar sedan på **Alla &&&**.</span><span class="sxs-lookup"><span data-stu-id="7c4f4-150">In the **Insert Rows from Dimensions** dialog box, in the **Dimensions** row, select the cell for the dimension to transfer to the row definition, and then click **All &&&**.</span></span>
4. <span data-ttu-id="7c4f4-151">Om du vill begränsa raddimensionen till ett specifikt intervall av dimensionsvärdena anger du startdimensionsvärdet i cellen **Dimensionsintervallstart** och skriv sedan in det avslutande dimensionsvärdet i cellen **Dimensionsintervallslut**.</span><span class="sxs-lookup"><span data-stu-id="7c4f4-151">To limit the row definition to a specific range of dimension values, enter the starting dimension value in the **Dimension Range Start** cell, and then enter the ending dimension value in the **Dimension Range End** cell.</span></span> <span data-ttu-id="7c4f4-152">Låt de här cellerna vara tomma om du vill inkludera den markerade dimensionens alla värden.</span><span class="sxs-lookup"><span data-stu-id="7c4f4-152">To include all values for the selected dimension, leave these cells empty.</span></span>

    > [!NOTE]
    > <span data-ttu-id="7c4f4-153">Beroende på hur data kollationeras i ERP-databasen är det inte säkert att jokertecken (\* eller ?) i dimensionsintervall returnerar önskat resultat.</span><span class="sxs-lookup"><span data-stu-id="7c4f4-153">Wildcard characters (\* or ?) in dimension ranges might not return all the results that you want, depending on how the ERP database collates data.</span></span>

5. <span data-ttu-id="7c4f4-154">Välj radkod för det första dimensionsvärdet i fältet **Startradskod** för att lägga till raddefinitionen.</span><span class="sxs-lookup"><span data-stu-id="7c4f4-154">In the **Starting row code** field, specify the row code for the first dimension value to add to the row definition.</span></span>
6. <span data-ttu-id="7c4f4-155">Ange avståndet mellan efterföljande radkoder i fältet **Öka varje rad med**.</span><span class="sxs-lookup"><span data-stu-id="7c4f4-155">In the **Increment each row by** field, specify the gap between consecutive row codes.</span></span> <span data-ttu-id="7c4f4-156">Om den första radkoden är 100 och stegvärdet är 30 har de nya raderna koderna 100, 130, 160, 190 och 220.</span><span class="sxs-lookup"><span data-stu-id="7c4f4-156">For example, if the first row code is 100, and the increment value is 30, the first new rows have the codes 100, 130, 160, 190, and 220.</span></span> <span data-ttu-id="7c4f4-157">Använd ett stegvärde som ger tillräckligt med utrymme för att infoga nya rader för format och formel.</span><span class="sxs-lookup"><span data-stu-id="7c4f4-157">Use an increment value that provides enough space to insert new format and formula rows.</span></span>
7. <span data-ttu-id="7c4f4-158">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="7c4f4-158">Click **OK**.</span></span> <span data-ttu-id="7c4f4-159">En rad per valt dimensionsvärde läggs till i raddefinitionen.</span><span class="sxs-lookup"><span data-stu-id="7c4f4-159">For each of the selected dimension values, one line is added to the row definition.</span></span>

## <a name="adjust-rounding-in-a-row-definition"></a><span data-ttu-id="7c4f4-160"> Justera avrundning i en raddefinition</span><span class="sxs-lookup"><span data-stu-id="7c4f4-160">Adjust rounding in a row definition</span></span>
<span data-ttu-id="7c4f4-161">Om du har en balansräkning där beloppen avrundas kan det hända att summorna inte balanseras.</span><span class="sxs-lookup"><span data-stu-id="7c4f4-161">If you have a balance sheet where the amounts are rounded, the totals might not balance.</span></span> <span data-ttu-id="7c4f4-162">Det här problemet kan uppstå om du exempelvis använder alternativet avrundning i en balansräkningsrapport och om även rapportdefinitionen använder avrundning.</span><span class="sxs-lookup"><span data-stu-id="7c4f4-162">This issue can occur if, for example, you use the rounding option on a balance sheet report and the report definition also specifies rounding.</span></span> <span data-ttu-id="7c4f4-163">Du kan använda alternativet **Avrundningsjusteringar** i raddefinitionen för att balansera beloppen i balansräkningarna.</span><span class="sxs-lookup"><span data-stu-id="7c4f4-163">You can use the **Rounding adjustment** option in the row definition to balance the amounts in the balance sheets.</span></span> <span data-ttu-id="7c4f4-164">Du kan inaktivera avrundning eller ändra den på fliken **Inställningar** i rapportdefinitionen.</span><span class="sxs-lookup"><span data-stu-id="7c4f4-164">You can turn rounding off or modify it on the **Settings** tab of the report definition.</span></span> <span data-ttu-id="7c4f4-165">Följande tabell visar hur beloppen avrundas.</span><span class="sxs-lookup"><span data-stu-id="7c4f4-165">The following table shows how amounts are rounded.</span></span> <span data-ttu-id="7c4f4-166">I den här tabellen skiljer sig summorna av raderna 100 och 200, när avrundning slås på.</span><span class="sxs-lookup"><span data-stu-id="7c4f4-166">In this table, the totals of rows 100 and 200 differ when rounding is turned on.</span></span>

| <span data-ttu-id="7c4f4-167">Radkod</span><span class="sxs-lookup"><span data-stu-id="7c4f4-167">Row code</span></span> | <span data-ttu-id="7c4f4-168">Belopp utan avrundning</span><span class="sxs-lookup"><span data-stu-id="7c4f4-168">Amounts without rounding</span></span> | <span data-ttu-id="7c4f4-169">Belopp med avrundning till hela tusental</span><span class="sxs-lookup"><span data-stu-id="7c4f4-169">Amount with rounding to whole thousands</span></span> |
|----------|--------------------------|-----------------------------------------|
| <span data-ttu-id="7c4f4-170">100</span><span class="sxs-lookup"><span data-stu-id="7c4f4-170">100</span></span>      | <span data-ttu-id="7c4f4-171">3,600</span><span class="sxs-lookup"><span data-stu-id="7c4f4-171">3,600</span></span>                    | <span data-ttu-id="7c4f4-172">4</span><span class="sxs-lookup"><span data-stu-id="7c4f4-172">4</span></span>                                       |
| <span data-ttu-id="7c4f4-173">200</span><span class="sxs-lookup"><span data-stu-id="7c4f4-173">200</span></span>      | <span data-ttu-id="7c4f4-174">3,700</span><span class="sxs-lookup"><span data-stu-id="7c4f4-174">3,700</span></span>                    | <span data-ttu-id="7c4f4-175">4</span><span class="sxs-lookup"><span data-stu-id="7c4f4-175">4</span></span>                                       |
| <span data-ttu-id="7c4f4-176">Summa</span><span class="sxs-lookup"><span data-stu-id="7c4f4-176">Total</span></span>    | <span data-ttu-id="7c4f4-177">7,300</span><span class="sxs-lookup"><span data-stu-id="7c4f4-177">7,300</span></span>                    | <span data-ttu-id="7c4f4-178">8</span><span class="sxs-lookup"><span data-stu-id="7c4f4-178">8</span></span>                                       |

<span data-ttu-id="7c4f4-179">Gör på följande sätt för att justera avrundningen i en balansräkning.</span><span class="sxs-lookup"><span data-stu-id="7c4f4-179">To adjust rounding in a balance sheet, follow these steps.</span></span>

1. <span data-ttu-id="7c4f4-180">I Rapportdesignern, klicka på **Raddefinitioner** och öppna raddefinitionen för att ändra.</span><span class="sxs-lookup"><span data-stu-id="7c4f4-180">In Report Designer, click **Row Definitions**, and then open the row definition to modify.</span></span>
2. <span data-ttu-id="7c4f4-181">Klicka på **Avrundningsjustering** på **Redigera**-menyn.</span><span class="sxs-lookup"><span data-stu-id="7c4f4-181">On the **Edit** menu, click **Rounding Adjustment**.</span></span>
3. <span data-ttu-id="7c4f4-182">I dialogrutan **Avrundningsjusteringar** anger du följande värden:</span><span class="sxs-lookup"><span data-stu-id="7c4f4-182">In the **Rounding Adjustments** dialog box, enter the following values:</span></span>

    - <span data-ttu-id="7c4f4-183">**Avrundningsjusteringar** – Radkoden för raden som ska justeras för att balansera balansräkningen.</span><span class="sxs-lookup"><span data-stu-id="7c4f4-183">**Rounding adjustment row** – The row code for the row that should be adjusted to balance the balance sheet.</span></span>
    - <span data-ttu-id="7c4f4-184">**Total tillgångsrad** – radkoden för raden i balansräkningen som innehåller de totala tillgångarna.</span><span class="sxs-lookup"><span data-stu-id="7c4f4-184">**Total assets row** – The row code for the row in the balance sheet that contains the total assets.</span></span>
    - <span data-ttu-id="7c4f4-185">**Totala skulder och eget kapital** – Radkoden för raden i balansräkningen som innehåller totala skulder och eget kapital.</span><span class="sxs-lookup"><span data-stu-id="7c4f4-185">**Total liabilities and equity row** – The row code for the row in the balance sheet that contains the total liabilities and equity.</span></span>
    - <span data-ttu-id="7c4f4-186">**Justeringsbeloppsgräns** – Den gräns som uttrycks som ett positivt heltal och som anger gränsen för automatiska justeringar.</span><span class="sxs-lookup"><span data-stu-id="7c4f4-186">**Adjustment amount limit** – A positive whole number that specifies the limit on automatic adjustments.</span></span> <span data-ttu-id="7c4f4-187">Det här beloppet jämförs med den faktiska avrundningsavvikelsens absoluta värde.</span><span class="sxs-lookup"><span data-stu-id="7c4f4-187">This amount is compared with the absolute value of the actual rounding difference.</span></span>

    > [!NOTE]
    > <span data-ttu-id="7c4f4-188">De här radkoderna måste länkas till dina ekonomiska data.</span><span class="sxs-lookup"><span data-stu-id="7c4f4-188">These row codes must be linked to your financial data.</span></span> <span data-ttu-id="7c4f4-189">Det innebär det måste finnas ett dimensionsvärde i radcellen **Länk till ekonomiska dimensioner**.</span><span class="sxs-lookup"><span data-stu-id="7c4f4-189">In other words, the row must have a dimension value in its **Link to Financial Dimensions** cell.</span></span> <span data-ttu-id="7c4f4-190">Referera **inte** en beskrivning (**DESC**) beräknad (**CALC**), eller summerad rad (**TOT**).</span><span class="sxs-lookup"><span data-stu-id="7c4f4-190">Do **not** reference a description (**DESC**), calculated (**CALC**), or totaled (**TOT**) row.</span></span>

<span data-ttu-id="7c4f4-191">Beloppen i din balansräkning balanseras nu jämt när avrundning är aktiverad.</span><span class="sxs-lookup"><span data-stu-id="7c4f4-191">The amounts in your balance sheet will now balance evenly when rounding is turned on.</span></span>

> [!NOTE]
> <span data-ttu-id="7c4f4-192">Justeringsgränsen tillämpas enligt det alternativ för **Avrundningsnoggrannhet** som anges för rapportdefinitionen.</span><span class="sxs-lookup"><span data-stu-id="7c4f4-192">The adjustment limit is applied based on the **Rounding precision** option that is specified for the report definition.</span></span> <span data-ttu-id="7c4f4-193">Om du till exempel väljer att avrunda rapporten till tusental och anger **2** i rutan **Justeringsbeloppsgräns** visas ett varningsmeddelande när värdet som identifieras i **Avrundningsjusteringsrad** ökar eller minskar med mer än 2 000.</span><span class="sxs-lookup"><span data-stu-id="7c4f4-193">For example, if you round your report to thousands and enter **2** in the **Adjustment amount limit** field, you receive a warning message when the value in the **Rounding adjustment row** field increases or decreases by more than 2,000.</span></span>

## <a name="format-row-and-column-text"></a><span data-ttu-id="7c4f4-194">Formatrad och kolumntext</span><span class="sxs-lookup"><span data-stu-id="7c4f4-194">Format row and column text</span></span>
<span data-ttu-id="7c4f4-195">Du kan anpassa utseendet på dina rapporter genom att ändra teckensnitt och formatera texten.</span><span class="sxs-lookup"><span data-stu-id="7c4f4-195">You can customize the appearance of your reports by changing fonts and formatting text.</span></span> <span data-ttu-id="7c4f4-196">Följande avsnitt innehåller information om hur du formaterar utseendet på rader och kolumner i rapporter.</span><span class="sxs-lookup"><span data-stu-id="7c4f4-196">The following sections explain how to format the appearance of rows and columns on reports.</span></span>

### <a name="manage-font-styles"></a><span data-ttu-id="7c4f4-197">Hantera teckenstilar</span><span class="sxs-lookup"><span data-stu-id="7c4f4-197">Manage font styles</span></span>

<span data-ttu-id="7c4f4-198">Du kan skapa och ändra teckensnitt för din rapport.</span><span class="sxs-lookup"><span data-stu-id="7c4f4-198">You can create and modify font styles for your report.</span></span> <span data-ttu-id="7c4f4-199">Du kan sedan tillämpa dessa teckensnitt i dokumentet eller på en viss rad eller kolumn i en rapport.</span><span class="sxs-lookup"><span data-stu-id="7c4f4-199">You can then apply those styles to the document, or to a specific row or column on a report.</span></span>

<table>
<tbody>
<tr>
<td><span data-ttu-id="7c4f4-200"><strong>Skapa ett teckensnitt</strong></span><span class="sxs-lookup"><span data-stu-id="7c4f4-200"><strong>Create a font style</strong></span></span></td>
<td>
<ol>
<li><span data-ttu-id="7c4f4-201">I Report Designer i menyn <strong>Format</strong>klickar du på <strong>Utföranden och formatering</strong>.</span><span class="sxs-lookup"><span data-stu-id="7c4f4-201">In Report Designer, on the <strong>Format</strong> menu, click <strong>Styles and Formatting</strong>.</span></span></li>
<li><span data-ttu-id="7c4f4-202">Klicka på <strong>Ny</strong> i dialogrutan <strong>Format och formatering</strong> och ange ett unikt namn på det nya formatet.</span><span class="sxs-lookup"><span data-stu-id="7c4f4-202">In the <strong>Styles and Formatting</strong> dialog box, click <strong>New</strong>, and then enter a unique name for the new style.</span></span></li>
<li><span data-ttu-id="7c4f4-203">Välj teckensnitt och klicka sedan på <strong>OK</strong>.</span><span class="sxs-lookup"><span data-stu-id="7c4f4-203">Make your font selections, and then click <strong>OK</strong>.</span></span></li>
</ol>
</td>
</tr>
<tr>
<td><span data-ttu-id="7c4f4-204"><strong>Ändra en teckenstil</strong></span><span class="sxs-lookup"><span data-stu-id="7c4f4-204"><strong>Modify a font style</strong></span></span></td>
<td>
<ol>
<li><span data-ttu-id="7c4f4-205">I Report Designer i menyn <strong>Format</strong>klickar du på <strong>Utföranden och formatering</strong>.</span><span class="sxs-lookup"><span data-stu-id="7c4f4-205">In Report Designer, on the <strong>Format</strong> menu, click <strong>Styles and Formatting</strong>.</span></span></li>
<li><span data-ttu-id="7c4f4-206">Markera en stil du vill ändra i dialogrutan <strong>Format och formatering</strong> och klicka sedan på <strong>Ändra</strong>.</span><span class="sxs-lookup"><span data-stu-id="7c4f4-206">In the <strong>Styles and Formatting</strong> dialog box, select a style to modify, and then click <strong>Modify</strong>.</span></span></li>
<li><span data-ttu-id="7c4f4-207">Välj teckensnitt och klicka sedan på <strong>OK</strong>.</span><span class="sxs-lookup"><span data-stu-id="7c4f4-207">Make your font selections, and then click <strong>OK</strong>.</span></span></li>
</ol>
</td>
</tr>
<tr>
<td><span data-ttu-id="7c4f4-208"><strong>Tillämpa ett teckensnitt</strong></span><span class="sxs-lookup"><span data-stu-id="7c4f4-208"><strong>Apply a font style</strong></span></span></td>
<td>
<ol>
<li><span data-ttu-id="7c4f4-209">Öppna Report Designer och välj definition, kolumndefinition, sidhuvud eller sidfot och välj där sedan en eller flera celler.</span><span class="sxs-lookup"><span data-stu-id="7c4f4-209">In Report Designer, in a definition or column definition, or in headers and footers, select one or more cells.</span></span></li>
<li><span data-ttu-id="7c4f4-210">Välj en teckenstil från listan <strong>Formatmall</strong> i verktygsfältet.</span><span class="sxs-lookup"><span data-stu-id="7c4f4-210">In the <strong>Style</strong> list on the toolbar, select a font style.</span></span></li>
</ol>
</td>
</tr>
</tbody>
</table>

### <a name="format-row-text"></a><span data-ttu-id="7c4f4-211">Formatradtext</span><span class="sxs-lookup"><span data-stu-id="7c4f4-211">Format row text</span></span>

<span data-ttu-id="7c4f4-212">Den formatering som anges i raddefinitionen åsidosätter all formatering som anges i kolumndefinitionen och i rapportdefinitionen.</span><span class="sxs-lookup"><span data-stu-id="7c4f4-212">The formatting that is specified in the row definition overrides any formatting that is specified in the column definition and the report definition.</span></span> <span data-ttu-id="7c4f4-213">Du kan ändra textformatet genom att använda kontrollerna i verktygsfältet Formatering.</span><span class="sxs-lookup"><span data-stu-id="7c4f4-213">You can modify the text format by using the controls on the formatting toolbar.</span></span> <span data-ttu-id="7c4f4-214">Dessa kontroller är standardinställda Microsoft Windows-kontroller.</span><span class="sxs-lookup"><span data-stu-id="7c4f4-214">These controls are standard Microsoft Windows controls.</span></span>

1. <span data-ttu-id="7c4f4-215">Öppna raddefinitionen i Report Designer för att ändra den.</span><span class="sxs-lookup"><span data-stu-id="7c4f4-215">In Report Designer, open the row definition to modify.</span></span>
2. <span data-ttu-id="7c4f4-216">Välj cellerna om du vill formatera.</span><span class="sxs-lookup"><span data-stu-id="7c4f4-216">Select the cells to format.</span></span> <span data-ttu-id="7c4f4-217">Håll ned CTRL-tangenten medan du väljer koderna om du vill välja mer än en cell.</span><span class="sxs-lookup"><span data-stu-id="7c4f4-217">To select multiple cells, hold down the Ctrl key while you select the cell.</span></span>
3. <span data-ttu-id="7c4f4-218">Klicka på verktygsfältsknappen av formatet som ska användas.</span><span class="sxs-lookup"><span data-stu-id="7c4f4-218">Click the toolbar button of the format to apply.</span></span> <span data-ttu-id="7c4f4-219">Om du exempelvis vill göra ett indrag på en rad ska du välja raden och klicka sedan på **Öka indrag** ![Öka indrag](https://i-technet.sec.s-msft.com/dynimg/IC679497.gif "Öka indrag") i verktygsfältet.</span><span class="sxs-lookup"><span data-stu-id="7c4f4-219">For example, to indent a row, select the row, and then click **Increase Indent** ![Increase Indent](https://i-technet.sec.s-msft.com/dynimg/IC679497.gif "Increase Indent") on the toolbar.</span></span>

### <a name="adjust-columns-while-you-design-reports"></a><span data-ttu-id="7c4f4-220">Justera kolumner medan du utformar rapporter</span><span class="sxs-lookup"><span data-stu-id="7c4f4-220">Adjust columns while you design reports</span></span>

<span data-ttu-id="7c4f4-221">För att göra det enklare att se kolumnerna som du arbetar med i raddefinitionen kan du justera bredden på en kolumn och dölja (minimera) eller visa kolumner i vyfönstret.</span><span class="sxs-lookup"><span data-stu-id="7c4f4-221">To make it easier to view the columns that you're working on in the row definition, you can adjust the width of a column, and can also hide (minimize) or show columns in the view pane.</span></span> <span data-ttu-id="7c4f4-222">Ändringarna påverkar enbart kolumnernas utseende på skärmen.</span><span class="sxs-lookup"><span data-stu-id="7c4f4-222">The modifications that you make affect only the on-screen appearance of the columns.</span></span> <span data-ttu-id="7c4f4-223">De påverkar inte kolumnformateringen i rapporter.</span><span class="sxs-lookup"><span data-stu-id="7c4f4-223">They don't affect the column formatting on reports.</span></span>

### <a name="change-the-width-of-a-column-in-the-view-pane"></a><span data-ttu-id="7c4f4-224">Ändra bredden på en kolumn i vyfönstret</span><span class="sxs-lookup"><span data-stu-id="7c4f4-224">Change the width of a column in the view pane</span></span>

1. <span data-ttu-id="7c4f4-225">Öppna raddefinitionen i Report Designer för att ändra den.</span><span class="sxs-lookup"><span data-stu-id="7c4f4-225">In Report Designer, open the row definition to modify.</span></span>
2. <span data-ttu-id="7c4f4-226">På menyn **Format** väljer du **Kolumnbredd**.</span><span class="sxs-lookup"><span data-stu-id="7c4f4-226">On the **Format** menu, select **Column Width**.</span></span>
3. <span data-ttu-id="7c4f4-227">Ange ett värde i dialogrutan **Kolumnbredd** och klicka sedan på **OK**.</span><span class="sxs-lookup"><span data-stu-id="7c4f4-227">In the **Column Width** dialog box, enter a value, and then click **OK**.</span></span> <span data-ttu-id="7c4f4-228">Du kan även dra i den högra gränsen för kolumnrubrikcellen för att ändra kolumnens bredd.</span><span class="sxs-lookup"><span data-stu-id="7c4f4-228">Alternatively, you can drag the right boundary of a column heading cell to change the width of the column.</span></span>

### <a name="hide-columns-in-the-view-pane"></a><span data-ttu-id="7c4f4-229">Dölj kolumner i vyfönstret</span><span class="sxs-lookup"><span data-stu-id="7c4f4-229">Hide columns in the view pane</span></span>

1. <span data-ttu-id="7c4f4-230">Öppna raddefinitionen i Report Designer för att ändra den.</span><span class="sxs-lookup"><span data-stu-id="7c4f4-230">In Report Designer, open the row definition to modify.</span></span>
2. <span data-ttu-id="7c4f4-231">Markera den kolumn eller de kolumner du vill minimera.</span><span class="sxs-lookup"><span data-stu-id="7c4f4-231">Select the column or columns to minimize.</span></span>
3. <span data-ttu-id="7c4f4-232">Högerklicka och klicka sedan på **Dölj**.</span><span class="sxs-lookup"><span data-stu-id="7c4f4-232">Right-click, and then click **Hide**.</span></span>

### <a name="show-all-hidden-columns-in-the-view-pane"></a><span data-ttu-id="7c4f4-233">Visa alla dolda kolumner i vyfönstret</span><span class="sxs-lookup"><span data-stu-id="7c4f4-233">Show all hidden columns in the view pane</span></span>

1. <span data-ttu-id="7c4f4-234">Öppna raddefinitionen i Report Designer för att ändra den.</span><span class="sxs-lookup"><span data-stu-id="7c4f4-234">In Report Designer, open the row definition to modify.</span></span>
2. <span data-ttu-id="7c4f4-235">Högerklicka på den dolda kolumnen du vill visa och klicka sedan på **Visa**.</span><span class="sxs-lookup"><span data-stu-id="7c4f4-235">Right-click the minimized column to display, and then click **Unhide**.</span></span>


## <a name="additional-resources"></a><span data-ttu-id="7c4f4-236">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="7c4f4-236">Additional resources</span></span>

[<span data-ttu-id="7c4f4-237">Ekonomisk rapportering</span><span class="sxs-lookup"><span data-stu-id="7c4f4-237">Financial reporting</span></span>](financial-reporting-intro.md)

