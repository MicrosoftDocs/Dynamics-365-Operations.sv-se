---
title: Budgetplaneringsmallar för Excel
description: Det här avsnittet beskriver hur du skapar Microsoft Excel-mallar som kan användas med budgetplaner.
author: ryansandness
manager: AnnBe
ms.date: 01/12/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BudgetPlanSetLayout
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 261794
ms.assetid: 1d8e99c1-b70d-41ba-991e-ab50b16797e0
ms.search.region: Global
ms.author: ryansand
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 079aa6bb4be020fc050b81c400050ed23d48f6ca
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2019
ms.locfileid: "337059"
---
# <a name="budget-planning-templates-for-excel"></a><span data-ttu-id="8afe7-103">Budgetplaneringsmallar för Excel</span><span class="sxs-lookup"><span data-stu-id="8afe7-103">Budget planning templates for Excel</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="8afe7-104">Det här avsnittet beskriver hur du skapar Microsoft Excel-mallar som kan användas med budgetplaner.</span><span class="sxs-lookup"><span data-stu-id="8afe7-104">This topic describes how to create Microsoft Excel templates that can be used with budget plans.</span></span>

<span data-ttu-id="8afe7-105">Det här avsnittet beskriver hur du skapar Excel-mallar som ska användas med budgetplaner som använder vanlig demodatauppsättning och administratörsinloggning.</span><span class="sxs-lookup"><span data-stu-id="8afe7-105">This topic shows how to create Excel templates that will be used with budget plans using the standard demo data set and the Admin user login.</span></span> <span data-ttu-id="8afe7-106">Mer information om budgetplanering finns [Översikt för budgetplanering.](budget-planning-overview-configuration.md)</span><span class="sxs-lookup"><span data-stu-id="8afe7-106">For more information about budget planning, see [Budget planning overview.](budget-planning-overview-configuration.md)</span></span> <span data-ttu-id="8afe7-107">Du kan även följa guiden [Budgetplanering 101](budget-plan.md) för att lära dig grundläggande modulkonfiguration och användning.</span><span class="sxs-lookup"><span data-stu-id="8afe7-107">You can also follow the [Budget planning 101](budget-plan.md) tutorial to learn basic module configuration and usage principles.</span></span>

## <a name="generate-a-worksheet-using-budget-plan-document-layout"></a><span data-ttu-id="8afe7-108">Skapa ett kalkylblad med en dokumentlayout för budgetplan</span><span class="sxs-lookup"><span data-stu-id="8afe7-108">Generate a worksheet using budget plan document layout</span></span>

<span data-ttu-id="8afe7-109">Budgetplandokument kan visas och redigeras med hjälp av en eller flera av layouter.</span><span class="sxs-lookup"><span data-stu-id="8afe7-109">Budget plan documents can be viewed and edited using one or more layouts.</span></span> <span data-ttu-id="8afe7-110">Varje layout kan ha en associerad budgetplansmall som låter dig visa och redigera budgetplandata i ett Excel-kalkylblad.</span><span class="sxs-lookup"><span data-stu-id="8afe7-110">Each layout can have an associated budget plan document template to view and edit the budget plan data in an Excel worksheet.</span></span> <span data-ttu-id="8afe7-111">I det här avsnittet genereras en budgetplansmall med hjälp av en befintlig layoutkonfiguration.</span><span class="sxs-lookup"><span data-stu-id="8afe7-111">In this topic, a budget plan document template will be generated using an existing layout configuration.</span></span> 

1. <span data-ttu-id="8afe7-112">Öppna **Budgetplanlista** (**Budgetering** &gt; **Budgetplaner**).</span><span class="sxs-lookup"><span data-stu-id="8afe7-112">Open the **Budget plans list** (**Budgeting** &gt; **Budget plans**).</span></span> 
2. <span data-ttu-id="8afe7-113">Klicka på **Ny** om du vill skapa en ny budgetplan.</span><span class="sxs-lookup"><span data-stu-id="8afe7-113">Click **New** to create a new budget plan document.</span></span> 

   <span data-ttu-id="8afe7-114">[![Budgetplanslista](./media/bpt11-1024x552.png)](./media/bpt11.png)</span><span class="sxs-lookup"><span data-stu-id="8afe7-114">[![Budget plans list](./media/bpt11-1024x552.png)](./media/bpt11.png)</span></span> 

3. <span data-ttu-id="8afe7-115">Använd radalternativet **Lägg till** för att lägga till rader.</span><span class="sxs-lookup"><span data-stu-id="8afe7-115">Use the **Add** line option to add lines.</span></span> <span data-ttu-id="8afe7-116">Klicka på **Layout** för att visa dokumentlayoutens konfiguration för budgetplanen.</span><span class="sxs-lookup"><span data-stu-id="8afe7-116">Click **Layouts** to view the budget plan document layout configuration.</span></span> 

   <span data-ttu-id="8afe7-117">[![Lägg till budgetplaner](./media/bpt2-1024x274.png)](./media/bpt2.png)</span><span class="sxs-lookup"><span data-stu-id="8afe7-117">[![Budget plans add](./media/bpt2-1024x274.png)](./media/bpt2.png)</span></span> 

<span data-ttu-id="8afe7-118">Du kan granska layoutkonfigurationen och justera den efter behov.</span><span class="sxs-lookup"><span data-stu-id="8afe7-118">You can review the layout configuration and adjust it as needed.</span></span> 
1. <span data-ttu-id="8afe7-119">Navigera till **Mall** &gt; **Generera** för att skapa en Excel-fil för den här layouten.</span><span class="sxs-lookup"><span data-stu-id="8afe7-119">Go to **Template** &gt; **Generate** to create an Excel file for this layout.</span></span> 
2. <span data-ttu-id="8afe7-120">När mallen har skapats går du till **Mall** &gt; **Visa** om du vill öppna och granska mallen för budgetplan.</span><span class="sxs-lookup"><span data-stu-id="8afe7-120">After the template is generated, go to **Template** &gt; **View** to open and review the budget plan document template.</span></span> <span data-ttu-id="8afe7-121">Du kan spara Excel-filen på hårddisken.</span><span class="sxs-lookup"><span data-stu-id="8afe7-121">You can save the Excel file to your local drive.</span></span> 

<span data-ttu-id="8afe7-122">[![Spara som](./media/bpt3-1024x545.png)](./media/bpt3.png)</span><span class="sxs-lookup"><span data-stu-id="8afe7-122">[![Save as](./media/bpt3-1024x545.png)](./media/bpt3.png)</span></span>

> [!NOTE] 
> <span data-ttu-id="8afe7-123">Budgetplanens dokumentlayout kan inte redigeras sedan en Excel-mall har associerats med den.</span><span class="sxs-lookup"><span data-stu-id="8afe7-123">The Budget plan document layout cannot be edited after an Excel template is associated with it.</span></span> <span data-ttu-id="8afe7-124">För att ändra layouten, ta bort associerad Excel-mallfil och återskapa den.</span><span class="sxs-lookup"><span data-stu-id="8afe7-124">To modify the layout, delete the associated Excel template file and regenerate it.</span></span> <span data-ttu-id="8afe7-125">Detta krävs för att hålla fälten i layouten och kalkylbladet synkroniserade.</span><span class="sxs-lookup"><span data-stu-id="8afe7-125">This is required to keep the fields in the layout and the worksheet synchronized.</span></span> 

<span data-ttu-id="8afe7-126">Excel-mallen innehåller alla element från budgetplanens dokumentlayout, där kolumnen **Tillgängliga i kalkylbladet** har angetts som True.</span><span class="sxs-lookup"><span data-stu-id="8afe7-126">The Excel template will contain all of the elements from the budget plan document layout, where the **Available in Worksheet** column is set to True.</span></span> <span data-ttu-id="8afe7-127">Överlappande element tillåts inte i Excel-mallen.</span><span class="sxs-lookup"><span data-stu-id="8afe7-127">Overlapping elements are not allowed in the Excel template.</span></span> <span data-ttu-id="8afe7-128">Om layouten exempelvis innehåller kolumner för Begäran K1, Begäran K2, Begäran K3 och Begäran K4 och en kolumn för total begäran som motsvarar summan för alla 4 kvartalkolumner, är endast den kvartalsvisa kolumnen (totalkolumnen) tillgänglig att användas i Excel-mallen.</span><span class="sxs-lookup"><span data-stu-id="8afe7-128">For example, if the layout contains Request Q1, Request Q2, Request Q3, and Request Q4 columns, and a total request column that represents a sum of all 4 quarterly columns, only the quarterly columns or total column is available to be used in the Excel template.</span></span> <span data-ttu-id="8afe7-129">Excel-filen kan inte uppdatera överlappande kolumner under uppdateringen, detta eftersom informationen i tabellen kan bli för gammal eller felaktig.</span><span class="sxs-lookup"><span data-stu-id="8afe7-129">The Excel file cannot update overlapping columns during the update because data in the table could become out of date and inaccurate.</span></span>

<span data-ttu-id="8afe7-130">[![Exempel](./media/bpt4-1024x615.png)](./media/bpt4.png)</span><span class="sxs-lookup"><span data-stu-id="8afe7-130">[![Example](./media/bpt4-1024x615.png)](./media/bpt4.png)</span></span>

> [!NOTE] 
> <span data-ttu-id="8afe7-131">Om du vill undvika problem med att visa och redigera budgetplandata med Excel, bör samma användare vara inloggad på både Microsoft Dynamics 365 for Finance and Operations och Office-tillägget för datakoppling till Microsoft Dynamics.</span><span class="sxs-lookup"><span data-stu-id="8afe7-131">To avoid potential issues with viewing and editing budget plan data using Excel, the same user should be logged into both Microsoft Dynamics 365 for Finance and Operations and the Microsoft Dynamics Office Add-in Data Connector.</span></span>

## <a name="add-a-header-to-budget-plan-document-template"></a><span data-ttu-id="8afe7-132">Lägg till en sidrubrik i en dokumentmall för budgetplan</span><span class="sxs-lookup"><span data-stu-id="8afe7-132">Add a header to budget plan document template</span></span>
<span data-ttu-id="8afe7-133">För att lägga till sidrubriksinformation, markera den översta raden i Excel-filen och infoga tomma rader.</span><span class="sxs-lookup"><span data-stu-id="8afe7-133">To add header information, select the top row in the Excel file and insert empty rows.</span></span> <span data-ttu-id="8afe7-134">Klicka på **Design** i **Datakoppling** för att lägga till sidhuvudfält i Excel-filen.</span><span class="sxs-lookup"><span data-stu-id="8afe7-134">Click **Design** in the **Data Connector** to add header fields to the Excel file.</span></span>

<span data-ttu-id="8afe7-135">[![bpt5](./media/bpt5-1024x615.png)](./media/bpt5.png)</span><span class="sxs-lookup"><span data-stu-id="8afe7-135">[![bpt5](./media/bpt5-1024x615.png)](./media/bpt5.png)</span></span> 

<span data-ttu-id="8afe7-136">I fliken **Design**, klicka på fälten **Lägg till** och markera sedan **BudgetPlanHeader** som datakälla för enheten.</span><span class="sxs-lookup"><span data-stu-id="8afe7-136">In the **Design** tab, click **Add** fields, and then select **BudgetPlanHeader** as the entity data source.</span></span>

<span data-ttu-id="8afe7-137">[![bpt6](./media/bpt6-1024x615.png)](./media/bpt6.png)</span><span class="sxs-lookup"><span data-stu-id="8afe7-137">[![bpt6](./media/bpt6-1024x615.png)](./media/bpt6.png)</span></span>

<span data-ttu-id="8afe7-138">Peka markören på önskad plats i Excel-filen.</span><span class="sxs-lookup"><span data-stu-id="8afe7-138">Point the cursor to the desired location in the Excel file.</span></span> <span data-ttu-id="8afe7-139">Klicka på knappen **Lägg till etikett** för att lägga till fältetiketten på vald plats.</span><span class="sxs-lookup"><span data-stu-id="8afe7-139">Click **Add label** to add the field label to the selected location.</span></span> <span data-ttu-id="8afe7-140">Välj **Lägg till värde** för att lägga till värdefältet på vald plats.</span><span class="sxs-lookup"><span data-stu-id="8afe7-140">Select **Add Value** to add the value field to the selected place.</span></span> <span data-ttu-id="8afe7-141">Klicka på **Klart** för att stänga designverktyget.</span><span class="sxs-lookup"><span data-stu-id="8afe7-141">Click **Done** to close the designer.</span></span>

## <a name="bpt7mediabpt7pngmediabpt7png"></a><span data-ttu-id="8afe7-142">[![bpt7](./media/bpt7.png)](./media/bpt7.png)</span><span class="sxs-lookup"><span data-stu-id="8afe7-142">[![bpt7](./media/bpt7.png)](./media/bpt7.png)</span></span>

<a name="add-a-calculated-column-to-budget-plan-document-template-table"></a><span data-ttu-id="8afe7-143">Lägg till beräknad kolumn i ett dokumentmallsregister för budgetplan</span><span class="sxs-lookup"><span data-stu-id="8afe7-143">Add a calculated column to budget plan document template table</span></span>
--------------------------------------------------------------

<span data-ttu-id="8afe7-144">Därefter kommer beräknade kolumner att läggas till i dokumentmall för budgetplan.</span><span class="sxs-lookup"><span data-stu-id="8afe7-144">Next, calculated columns will be added to generated budget plan document template.</span></span> <span data-ttu-id="8afe7-145">En kolumn vid namn **Total begäran**, som sammanfattar kolumnerna Begäran K1: Begäran K4, samt en **Justering**-kolumn, som beräknar kolumnen **Total begäran** genom en fördefinierad faktor.</span><span class="sxs-lookup"><span data-stu-id="8afe7-145">A **Total request** column, which summarizes Request Q1: Request Q4 columns, and an **Adjustment** column, which recalculates the **Total Request** column by a predefined factor.</span></span>

<span data-ttu-id="8afe7-146">Klicka på **Design** i **Datakoppling** för att lägga till kolumner i registret.</span><span class="sxs-lookup"><span data-stu-id="8afe7-146">Click **Design** in the **Data connector** to add columns to the table.</span></span> <span data-ttu-id="8afe7-147">Klicka på **Redigera** bredvid datakällan **BudgetPlanWorksheet** om du vill börja lägga till kolumner.</span><span class="sxs-lookup"><span data-stu-id="8afe7-147">Click **Edit** next to **BudgetPlanWorksheet** data source to start adding columns.</span></span>

<span data-ttu-id="8afe7-148">[![bpt8](./media/bpt8-1024x301.png)](./media/bpt8.png)</span><span class="sxs-lookup"><span data-stu-id="8afe7-148">[![bpt8](./media/bpt8-1024x301.png)](./media/bpt8.png)</span></span> 

<span data-ttu-id="8afe7-149">Den valda fältgruppen visar de kolumner som finns i mallen.</span><span class="sxs-lookup"><span data-stu-id="8afe7-149">The selected field group displays the columns that are available in the template.</span></span> <span data-ttu-id="8afe7-150">Klicka på **Formel** för att lägga till en ny kolumn.</span><span class="sxs-lookup"><span data-stu-id="8afe7-150">Click **Formula** to add a new column.</span></span> <span data-ttu-id="8afe7-151">Namnge den nya kolumnen och klistra sedan in formeln i fältet **Formel**.</span><span class="sxs-lookup"><span data-stu-id="8afe7-151">Name the new column and then paste the formula into the **Formula** field.</span></span> <span data-ttu-id="8afe7-152">Klicka på **Uppdatera** för att klistra in kolumnen.</span><span class="sxs-lookup"><span data-stu-id="8afe7-152">Click **Update** to insert the column.</span></span>

<span data-ttu-id="8afe7-153">[![bpt12](./media/bpt12-1024x565.png)](./media/bpt12.png)</span><span class="sxs-lookup"><span data-stu-id="8afe7-153">[![bpt12](./media/bpt12-1024x565.png)](./media/bpt12.png)</span></span>

> [!NOTE] 
> <span data-ttu-id="8afe7-154">Ange formeln genom att skapa den i kalkylbladet och kopiera den sedan till fönstret **Design**.</span><span class="sxs-lookup"><span data-stu-id="8afe7-154">To define the formula, create the formula in the spreadsheet, and then copy it to the **Design** window.</span></span> <span data-ttu-id="8afe7-155">Ett register avsett för Finance and Operations namnges vanligtvis "AXTable1".</span><span class="sxs-lookup"><span data-stu-id="8afe7-155">A Finance and Operations bound table will typically be named "AXTable1".</span></span> <span data-ttu-id="8afe7-156">För att till exempel summera Begäran K1 : Begäran K4-kolumner i kalkylbladet blir formeln = AxRegister1\[Begäran K1\]+ AxRegister1\[Begäran K2\]+ AxRegister1\[Begäran K3\]+ AxRegister1\[Begäran K4\].</span><span class="sxs-lookup"><span data-stu-id="8afe7-156">For example, to summarize Request Q1 : Request Q4 columns in the spreadsheet, the formula = AxTable1\[Request Q1\]+AxTable1\[Request Q2\]+AxTable1\[Request Q3\]+AxTable1\[Request Q4\].</span></span>

<span data-ttu-id="8afe7-157">Upprepa dessa steg för att infoga kolumnen **Justering**.</span><span class="sxs-lookup"><span data-stu-id="8afe7-157">Repeat these steps to insert the **Adjustment** column.</span></span> <span data-ttu-id="8afe7-158">Använd formeln = AxRegister1\[Total begäran\]\*$I$ 1 för den här kolumnen.</span><span class="sxs-lookup"><span data-stu-id="8afe7-158">Use formula = AxTable1\[Total request\]\*$I$1 for this column.</span></span> <span data-ttu-id="8afe7-159">Detta kommer ta värdet i cell I1 och multiplicera värdena i kolumnen **Total begäran** för att beräkna justeringsbeloppen.</span><span class="sxs-lookup"><span data-stu-id="8afe7-159">This will take the value in cell I1 and multiply the values in the **Total request** column to calculate adjustment amounts.</span></span>

<span data-ttu-id="8afe7-160">Spara och stäng Excel-filen.</span><span class="sxs-lookup"><span data-stu-id="8afe7-160">Save and close the Excel file.</span></span> <span data-ttu-id="8afe7-161">Återgå till Finance and Operations. I **Layout** klickar du på **Mall &gt; Överför** för att överföra den sparade Excel-mallen som ska användas för budgetplanen.</span><span class="sxs-lookup"><span data-stu-id="8afe7-161">Return to Finance and Operations, and in **Layouts**, click **Template &gt; Upload** to upload the saved Excel template to be used for the budget plan.</span></span> 

<span data-ttu-id="8afe7-162">[![bpt10](./media/bpt10-1024x352.png)](./media/bpt10.png)</span><span class="sxs-lookup"><span data-stu-id="8afe7-162">[![bpt10](./media/bpt10-1024x352.png)](./media/bpt10.png)</span></span> 

<span data-ttu-id="8afe7-163">Stäng skjutreglaget **Layout**.</span><span class="sxs-lookup"><span data-stu-id="8afe7-163">Close the **Layouts** slider.</span></span> <span data-ttu-id="8afe7-164">I dokumentet **Budgetplan** klickar du på **Kalkylblad** för att visa och redigera dokumentet i Excel.</span><span class="sxs-lookup"><span data-stu-id="8afe7-164">In **Budget plan** document, click **Worksheet** to view and edit the document in Excel.</span></span> <span data-ttu-id="8afe7-165">Observera att den justerade Excel-mallen användes för att skapa det här budgetplanskalkylbladet, och beräknade kolumner uppdateras med hjälp av de formler som definierades i föregående steg.</span><span class="sxs-lookup"><span data-stu-id="8afe7-165">Note that the adjusted Excel template was used to create this budget plan worksheet and calculated columns are updated using the formulas that were defined in the previous steps.</span></span> 

<span data-ttu-id="8afe7-166">[![bpt11](./media/bpt111-1024x431.png)](./media/bpt111.png)</span><span class="sxs-lookup"><span data-stu-id="8afe7-166">[![bpt11](./media/bpt111-1024x431.png)](./media/bpt111.png)</span></span>

## <a name="tips--tricks-for-creating-budget-plan-templates"></a><span data-ttu-id="8afe7-167">Tips och trick för att skapa budgetplansmallar</span><span class="sxs-lookup"><span data-stu-id="8afe7-167">Tips & tricks for creating budget plan templates</span></span>
### <a name="can-i-add-and-use-additional-data-sources-to-a-budget-plan-template"></a><span data-ttu-id="8afe7-168">Kan jag lägga till och använda ytterligare datakällor i en budgetplansmall?</span><span class="sxs-lookup"><span data-stu-id="8afe7-168">Can I add and use additional data sources to a budget plan template?</span></span>

<span data-ttu-id="8afe7-169">Ja, du kan använda menyn **Design** för att lägga till ytterligare enheter i samma eller andra ark i Excel-mallen.</span><span class="sxs-lookup"><span data-stu-id="8afe7-169">Yes, you can use the **Design** menu to add additional entities to the same or other sheets in the Excel template.</span></span> <span data-ttu-id="8afe7-170">Du kan till exempel lägga till datakällan **BudgetPlanProposedProject** om du vill skapa och underhålla en lista över föreslagna projekt samtidigt som du arbetar med budgetplandata i Excel.</span><span class="sxs-lookup"><span data-stu-id="8afe7-170">For example, you can add the **BudgetPlanProposedProject** data source to create and maintain a list of proposed projects at the same time when working with budget plan data in Excel.</span></span> <span data-ttu-id="8afe7-171">Observera att bland annat omfattande datakällor kan påverka prestandan i Excel-arbetsboken.</span><span class="sxs-lookup"><span data-stu-id="8afe7-171">Note that including high-volume data sources might impact performance of the Excel workbook.</span></span> 

<span data-ttu-id="8afe7-172">Du kan använda alternativet **Filter** **Datakoppling** för att lägga till önskade filter bland ytterligare datakällor.</span><span class="sxs-lookup"><span data-stu-id="8afe7-172">You can use the **Filter** option in the **Data Connector** to add desired filters to additional data sources.</span></span>

### <a name="can-i-hide-the-design-option-in-the-data-connector-for-other-users"></a><span data-ttu-id="8afe7-173">Kan jag dölja alternativet Design i datakopplingen för andra användare?</span><span class="sxs-lookup"><span data-stu-id="8afe7-173">Can I hide the Design option in the Data connector for other users?</span></span>

<span data-ttu-id="8afe7-174">Ja, öppna alternativet **Datakoppling** för att dölja alternativet **Design** från andra användare.</span><span class="sxs-lookup"><span data-stu-id="8afe7-174">Yes, open the **Data Connector** options to hide the **Design** option from other users.</span></span>

<span data-ttu-id="8afe7-175">[![bpt13](./media/bpt13-1024x565.png)](./media/bpt13.png)</span><span class="sxs-lookup"><span data-stu-id="8afe7-175">[![bpt13](./media/bpt13-1024x565.png)](./media/bpt13.png)</span></span>

<span data-ttu-id="8afe7-176">Expandera **Alternativ för datakoppling** och rensa kryssrutan **Aktivera design**.</span><span class="sxs-lookup"><span data-stu-id="8afe7-176">Expand **Data connector options** and clear the **Enable design** check box.</span></span> <span data-ttu-id="8afe7-177">Detta döljer alternativet **Design** från **Datakoppling**.</span><span class="sxs-lookup"><span data-stu-id="8afe7-177">This will hide the **Design** option from the **Data connector**.</span></span>

<span data-ttu-id="8afe7-178">[![bpt14](./media/bpt14-1024x592.png)](./media/bpt14.png)</span><span class="sxs-lookup"><span data-stu-id="8afe7-178">[![bpt14](./media/bpt14-1024x592.png)](./media/bpt14.png)</span></span>

### <a name="can-i-prevent-users-from-accidently-closing-the-data-connector-while-working-with-data"></a><span data-ttu-id="8afe7-179">Kan jag förhindra att användare av misstag stänger datakopplingen när de arbetar med data?</span><span class="sxs-lookup"><span data-stu-id="8afe7-179">Can I prevent users from accidently closing the Data connector while working with data?</span></span>

<span data-ttu-id="8afe7-180">Vi rekommenderar att låsa mallen om du vill hindra användare från att stänga den.</span><span class="sxs-lookup"><span data-stu-id="8afe7-180">We recommend locking the template to prevent users from closing it.</span></span> <span data-ttu-id="8afe7-181">Om du vill aktivera låset klickar du på **Datakoppling**; en pil visas längst upp i det högra hörnet.</span><span class="sxs-lookup"><span data-stu-id="8afe7-181">To turn on the lock, click the **Data connector**, in the top right corner an arrow appears.</span></span> 

<span data-ttu-id="8afe7-182">[![bpt15](./media/bpt15-1024x285.png)](./media/bpt15.png)</span><span class="sxs-lookup"><span data-stu-id="8afe7-182">[![bpt15](./media/bpt15-1024x285.png)](./media/bpt15.png)</span></span> 

<span data-ttu-id="8afe7-183">Klicka på pilen för att visa en ytterligare meny.</span><span class="sxs-lookup"><span data-stu-id="8afe7-183">Click the arrow for an additional menu.</span></span> <span data-ttu-id="8afe7-184">Välj **Lås**.</span><span class="sxs-lookup"><span data-stu-id="8afe7-184">Select **Lock**.</span></span>

### <a name="bpt16mediabpt16-1024x614pngmediabpt16png"></a><span data-ttu-id="8afe7-185">[![bpt16](./media/bpt16-1024x614.png)](./media/bpt16.png)</span><span class="sxs-lookup"><span data-stu-id="8afe7-185">[![bpt16](./media/bpt16-1024x614.png)](./media/bpt16.png)</span></span>

### <a name="can-i-use-other-excel-features-like-cell-formatting-colors-conditional-formatting-and-charts-with-my-budget-plan-templates"></a><span data-ttu-id="8afe7-186">Kan jag använda andra Excel-funktioner som cellformatering, färger, villkorsstyrd formatering och diagram med mina budgetplansmallar?</span><span class="sxs-lookup"><span data-stu-id="8afe7-186">Can I use other Excel features, like cell formatting, colors, conditional formatting, and charts with my budget plan templates?</span></span>

<span data-ttu-id="8afe7-187">Ja, de flesta vanliga Excel-funktioner fungerar i budgetplansmallar.</span><span class="sxs-lookup"><span data-stu-id="8afe7-187">Yes, most of the standard Excel capabilities will work in budget plan templates.</span></span> <span data-ttu-id="8afe7-188">Vi rekommenderar att använda färgkodning så att användare kan skilja mellan skrivskyddade och redigerbara kolumner.</span><span class="sxs-lookup"><span data-stu-id="8afe7-188">We recommend using color-coding for users to distinguish between read-only and editable columns.</span></span> <span data-ttu-id="8afe7-189">Villkorsstyrd formatering kan användas för att framhäva vissa problematiska delar av budgeten.</span><span class="sxs-lookup"><span data-stu-id="8afe7-189">Conditional formatting can be used to highlight problematic areas of the budget.</span></span> <span data-ttu-id="8afe7-190">Totalsummor för kolumner kan enkelt visas med vanliga Excel-formler ovanför tabellen.</span><span class="sxs-lookup"><span data-stu-id="8afe7-190">Column totals can easily be presented by using standard Excel formulas above the table.</span></span>

<span data-ttu-id="8afe7-191">Du kan också skapa och använda pivottabeller och diagram för ytterligare grupper och visualiseringar av budgetdata.</span><span class="sxs-lookup"><span data-stu-id="8afe7-191">You can also create and use pivot tables and charts for additional groupings and visualizations of budget data.</span></span> <span data-ttu-id="8afe7-192">På fliken **Data**, i gruppen **Anslutningar**, klickar du på **Uppdatera alla** och sedan på **Anslutningsegenskaper**.</span><span class="sxs-lookup"><span data-stu-id="8afe7-192">On the **Data** tab, in the **Connections** group, click **Refresh All**, and then click **Connection Properties**.</span></span> <span data-ttu-id="8afe7-193">Klicka på fliken **Användning**. Under fliken **Uppdatera** markerar du kryssrutan **Uppdatera data när filen öppnas**.</span><span class="sxs-lookup"><span data-stu-id="8afe7-193">Click the **Usage** tab. Under **Refresh**, select the **Refresh data when opening the file** check box.</span></span> 

<span data-ttu-id="8afe7-194">[![bpt17](./media/bpt17-1024x614.png)](./media/bpt17.png)</span><span class="sxs-lookup"><span data-stu-id="8afe7-194">[![bpt17](./media/bpt17-1024x614.png)](./media/bpt17.png)</span></span>



