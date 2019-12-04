---
title: Göra självstudier med Regression Suite Automation Tool
description: Det här avsnittet visar hur du använder RSAT (Regression Suite Automation Tool). Den beskriver olika funktioner och ger exempel som använder avancerad skriptanvändning.
author: kfend
manager: AnnBe
ms.date: 06/09/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 21761
ms.search.region: Global
ms.author: kfend
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: AX 7.0.0, Operations
ms.openlocfilehash: 654685a382ca5f3f462ad8a9c506b51b52c3758c
ms.sourcegitcommit: 57bc7e17682e2edb5e1766496b7a22f4621819dd
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/18/2019
ms.locfileid: "2811659"
---
# <a name="use-the-regression-suite-automation-tool-tutorial"></a><span data-ttu-id="111cb-104">Använda självstudie för Regression Suite Automation Tool</span><span class="sxs-lookup"><span data-stu-id="111cb-104">Use the Regression suite automation tool tutorial</span></span>

[!include [banner](../includes/banner.md)]

> [!NOTE]
> <span data-ttu-id="111cb-105">Använd webbläsarverktygen för att hämta och spara sidan i PDF-format.</span><span class="sxs-lookup"><span data-stu-id="111cb-105">Use your internet browser tools to download and save this page in pdf format.</span></span> 

<span data-ttu-id="111cb-106">I den här vägledningen får du hjälp med några av de avancerade funktionerna i RSAT (Regression Suite Automation Tool), inkluderar en demotilldelning och beskriver strategi- och nyckelutbildningspunkter.</span><span class="sxs-lookup"><span data-stu-id="111cb-106">This tutorial walks through some of the advanced features of the Regression suite automation tool (RSAT), includes a demo assignment, and describes strategy and key learning points.</span></span>

## <a name="features-of-rsattask-recorder"></a><span data-ttu-id="111cb-107">Funktioner av RSAT/Uppgiftsregistrering</span><span class="sxs-lookup"><span data-stu-id="111cb-107">Features of RSAT/Task recorder</span></span>

### <a name="validate-a-field-value"></a><span data-ttu-id="111cb-108">Validera fältvärdet</span><span class="sxs-lookup"><span data-stu-id="111cb-108">Validate a field value</span></span>

<span data-ttu-id="111cb-109">Mer information om den här funktionen finns i [skapa en ny uppgiftsregistrering som har en Validera-funktion](./hol-set-up-regression-suite-automation-tool.md#create-a-new-task-recording-that-has-a-validate-function).</span><span class="sxs-lookup"><span data-stu-id="111cb-109">For information about this feature, see the [Create a new task recording that has a Validate function](./hol-set-up-regression-suite-automation-tool.md#create-a-new-task-recording-that-has-a-validate-function).</span></span>

### <a name="saved-variable"></a><span data-ttu-id="111cb-110">Sparad variabel</span><span class="sxs-lookup"><span data-stu-id="111cb-110">Saved variable</span></span>

<span data-ttu-id="111cb-111">Mer information om den här funktionen finns i [ändra en befintlig uppgiftsregistrering och skapa en sparad variabel](./hol-set-up-regression-suite-automation-tool.md#modify-an-existing-task-recording-to-create-a-saved-variable).</span><span class="sxs-lookup"><span data-stu-id="111cb-111">For information about this feature, see the [Modify an existing task recording to create a saved variable](./hol-set-up-regression-suite-automation-tool.md#modify-an-existing-task-recording-to-create-a-saved-variable).</span></span>

### <a name="derived-test-case"></a><span data-ttu-id="111cb-112">Härlett testfall</span><span class="sxs-lookup"><span data-stu-id="111cb-112">Derived test case</span></span>

1. <span data-ttu-id="111cb-113">Öppna verktyget RSAT (Regression Suite Automation Tool) och markera båda testärenden som du har skapat i [Självstudie för konfigurera och installera Regression Suite Automation Tool](./hol-set-up-regression-suite-automation-tool.md).</span><span class="sxs-lookup"><span data-stu-id="111cb-113">Open Regression suite automation tool (RSAT), and select both the test cases that you created in [Set up and install Regression suite automation tool tutorial](./hol-set-up-regression-suite-automation-tool.md).</span></span>
2. <span data-ttu-id="111cb-114">Välj **ny \> skapa härlett testfall**.</span><span class="sxs-lookup"><span data-stu-id="111cb-114">Select **New \> Create derived test case**.</span></span>

    ![Kommandot Skapa härlett testfallkommando på den nya menyn](./media/use_rsa_tool_01.png)

3. <span data-ttu-id="111cb-116">Ett meddelande visas om att ett härlett testfall kommer att skapas för varje valt testfall i det aktuella testpaketet och att varje härlett testfall har en egen kopia av Excel-parameterfilen.</span><span class="sxs-lookup"><span data-stu-id="111cb-116">You receive a message that states that a derived test case will be created for each selected test case in the current test suite, and that each derived test case will have its own copy of the Excel parameter file.</span></span> <span data-ttu-id="111cb-117">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="111cb-117">Select **OK**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="111cb-118">När du kör ett härlett testfall använder det uppgiftsinspelningen av det överordnade testfallet och den egna kopian av Excel-parameterfilen.</span><span class="sxs-lookup"><span data-stu-id="111cb-118">When you run a derived test case, it uses the task recording of its parent test case and its own copy of the Excel parameter file.</span></span> <span data-ttu-id="111cb-119">På så sätt kan du köra samma test med olika parametrar utan att behöva underhålla fler än en uppgiftsinspelning.</span><span class="sxs-lookup"><span data-stu-id="111cb-119">In this way, you can run the same test with different parameters, without having to maintain more than one task recording.</span></span> <span data-ttu-id="111cb-120">Ett härlett testfall behöver inte vara en del av samma testserie som det överordnade testfallet.</span><span class="sxs-lookup"><span data-stu-id="111cb-120">A derived test case doesn't have to be part of the same test suite as its parent test case.</span></span>

    ![Meddelanderuta](./media/use_rsa_tool_02.png)

    <span data-ttu-id="111cb-122">Två ytterligare härledda testfall skapas och kryssrutan **härledda?** markeras för dem.</span><span class="sxs-lookup"><span data-stu-id="111cb-122">Two additional derived test cases are created, and the **Derived?** check box is selected for them.</span></span>

    ![Härledda testfall har skapats](./media/use_rsa_tool_03.png)

    <span data-ttu-id="111cb-124">Ett härlett testfall skapas automatiskt i Azure DevOps.</span><span class="sxs-lookup"><span data-stu-id="111cb-124">A derived test case is automatically created in Azure DevOps.</span></span> <span data-ttu-id="111cb-125">Det är ett underordnat objekt till testfallet **skapa en ny produkt** och märks med ett särskilt nyckelord: **RSAT:DerivedTestSteps**.</span><span class="sxs-lookup"><span data-stu-id="111cb-125">It's a child item of the **Create a new product** test case and is tagged with a special keyword: **RSAT:DerivedTestSteps**.</span></span> <span data-ttu-id="111cb-126">Dessa testfall läggs också automatiskt till i testplanen i Azure DevOps.</span><span class="sxs-lookup"><span data-stu-id="111cb-126">These test cases are also automatically added to the test plan in Azure DevOps.</span></span>

    ![RSAT:DerivedTestSteps-nyckelord](./media/use_rsa_tool_04.png)

    > [!NOTE]
    > <span data-ttu-id="111cb-128">Om de härledda testfallet som skapas inte finns i rätt ordning går du till Azure DevOps och beställer testfallen igen i testpaketet så att RSAT kan köras i rätt ordning.</span><span class="sxs-lookup"><span data-stu-id="111cb-128">If, for any reason, the derived test cases that are created aren't in the correct order, go to Azure DevOps, and reorder the test cases in the test suite, so that RSAT can run them in the correct order.</span></span>

4. <span data-ttu-id="111cb-129">Markera de härledda testfall och välj sedan **redigera** för att öppna motsvarande Excel-parameterfiler.</span><span class="sxs-lookup"><span data-stu-id="111cb-129">Select the derived test cases, and then select **Edit** to open the corresponding Excel parameter files.</span></span>
5. <span data-ttu-id="111cb-130">Redigera dessa Excel-parametervärden på samma sätt som du redigerade de överordnade filerna.</span><span class="sxs-lookup"><span data-stu-id="111cb-130">Edit these Excel parameter files in the same way that you edited the parent files.</span></span> <span data-ttu-id="111cb-131">Med andra ord måste du se till att produkt-ID:t är inställt så att det skapas automatiskt.</span><span class="sxs-lookup"><span data-stu-id="111cb-131">In other words, make sure that the product ID is set so that it's automatically generated.</span></span> <span data-ttu-id="111cb-132">Kontrollera också att den sparade variabeln kopieras till relevanta fält.</span><span class="sxs-lookup"><span data-stu-id="111cb-132">Also make sure that the saved variable is copied to the relevant fields.</span></span>
6. <span data-ttu-id="111cb-133">På fliken **allmänt** i båda Excel-parameterfiler uppdaterar du värdet för fältet **företag** till **Ussi**, så att de härledda testfallen kan köras mot en annan juridisk person än det överordnade testfallet.</span><span class="sxs-lookup"><span data-stu-id="111cb-133">On the **General** tab of both Excel parameter files, update the value of the **Company** field to **USSI**, so that the derived test cases will be run against a different legal entity than the parent test case.</span></span> <span data-ttu-id="111cb-134">Om du vill köra testfall mot mot en viss användare (eller den roll som är associerad med en viss användare) kan du uppdatera värdet i fältet **testanvändare.**</span><span class="sxs-lookup"><span data-stu-id="111cb-134">To run the test cases against a specific user (or the role that is associated with a specific user), you can update the value of the **Test User** field.</span></span>
7. <span data-ttu-id="111cb-135">Välj **kör**och validera att produkten har skapats i både den USMF juridiska personen och den USSI juridiska personen.</span><span class="sxs-lookup"><span data-stu-id="111cb-135">Select **Run**, and validate that the product is created in both the USMF legal entity and the USSI legal entity.</span></span>

### <a name="validate-notifications"></a><span data-ttu-id="111cb-136">Validera meddelanden</span><span class="sxs-lookup"><span data-stu-id="111cb-136">Validate notifications</span></span>

<span data-ttu-id="111cb-137">Den här funktionen kan användas för att validera om en åtgärd utförts.</span><span class="sxs-lookup"><span data-stu-id="111cb-137">This feature can be used to validate whether an action occurred.</span></span> <span data-ttu-id="111cb-138">När till exempel en tillverkningsorder skapas, uppskattas och sedan startas, visar appen meddelandet "produktion – start" för att meddela dig att tillverkningsordern har startats.</span><span class="sxs-lookup"><span data-stu-id="111cb-138">For example, when a production order is created, estimated, and then started, the app shows a "Production – Start" message to notify you that the production order has been started.</span></span>

![Produktion - starta meddelande](./media/use_rsa_tool_05.png)

<span data-ttu-id="111cb-140">Du kan validera det här meddelandet genom RSAT genom att ange meddelande texten på fliken **MessageValidation** i Excel-parameterfilen för lämplig inspelning.</span><span class="sxs-lookup"><span data-stu-id="111cb-140">You can validate this message through RSAT by entering the message text on the **MessageValidation** tab of the Excel parameter file for the appropriate recording.</span></span>

![Fliken Meddelandevalidering](./media/use_rsa_tool_06.png)

<span data-ttu-id="111cb-142">När testfallet har körts, jämförs meddelandet i Excel-parameterfilen i det meddelande som visas.</span><span class="sxs-lookup"><span data-stu-id="111cb-142">After the test case is run, the message in the Excel parameter file is compared to the message that is shown.</span></span> <span data-ttu-id="111cb-143">Om meddelandena inte matchar kommer testfallet att misslyckas.</span><span class="sxs-lookup"><span data-stu-id="111cb-143">If the messages don't match, the test case will fail.</span></span>

> [!NOTE]
> <span data-ttu-id="111cb-144">Du kan ange mer än ett meddelande på fliken **MessageValidation** i Excel-parameterfilen.</span><span class="sxs-lookup"><span data-stu-id="111cb-144">You can enter more than one message on the **MessageValidation** tab in the Excel parameter file.</span></span> <span data-ttu-id="111cb-145">Meddelandena kan också vara fel- eller varningsmeddelanden i stället för informationsmeddelanden.</span><span class="sxs-lookup"><span data-stu-id="111cb-145">The messages also can be error or warning messages instead of informational messages.</span></span>

### <a name="validate-values-by-using-operators"></a><span data-ttu-id="111cb-146">Validera värden med hjälp av operatörer</span><span class="sxs-lookup"><span data-stu-id="111cb-146">Validate values by using operators</span></span>

<span data-ttu-id="111cb-147">I tidigare versioner av RSAT kunde du bara validera värden om ett kontrollvärde är lika med ett förväntat värde.</span><span class="sxs-lookup"><span data-stu-id="111cb-147">In previous versions of RSAT, you could validate values only if a control value equaled an expected value.</span></span> <span data-ttu-id="111cb-148">Med den nya funktionen kan du validera att en variabel inte är lika med, är mindre än eller mer än ett angivet värde.</span><span class="sxs-lookup"><span data-stu-id="111cb-148">The new feature lets you validate that a variable isn't equal to, is less than, or is more than a specified value.</span></span>

- <span data-ttu-id="111cb-149">Om du vill använda den här funktionen öppnar du filen **Microsoft.Dynamics.RegressionSuite.WindowsApp.exe.config** under RSAT-installationsmappen (t.ex. **C:\\programfiler (x86)\\Regression Suite Automation Tool**) och ändrar värdet i följande element från **falskt** till **sant**.</span><span class="sxs-lookup"><span data-stu-id="111cb-149">To use this feature, open the **Microsoft.Dynamics.RegressionSuite.WindowsApp.exe.config** file under the RSAT installation folder (for example, **C:\\Program Files (x86)\\Regression Suite Automation Tool**), and change the value in the following element from **false** to **true**.</span></span>

    ```
    <add key="AddOperatorFieldsToExcelValidation" value="false" />
    ```

    <span data-ttu-id="111cb-150">I Excel-parameterfilen visas ett nytt fält med **operatör**.</span><span class="sxs-lookup"><span data-stu-id="111cb-150">In the Excel parameter file, a new **Operator** field appears.</span></span>

    > [!NOTE]
    > <span data-ttu-id="111cb-151">Om du har använt en äldre version av RSAT måste du generera nya Excel-parameterstyrda filer.</span><span class="sxs-lookup"><span data-stu-id="111cb-151">If you've been using an older version of RSAT, you must generate new Excel parameter files.</span></span>

    ![Fältet Operatör](./media/use_rsa_tool_07.png)

<span data-ttu-id="111cb-153">I följande exempel visas hur du kan använda den här funktionen för att validera om lagerbehållningen är större än 0 (noll).</span><span class="sxs-lookup"><span data-stu-id="111cb-153">The following example shows how you can use this feature to validate whether the on-hand inventory is more than 0 (zero).</span></span>

1. <span data-ttu-id="111cb-154">I demonstrationsdata i **USMF**-företaget skapar du en uppgiftsregistrering med följande steg:</span><span class="sxs-lookup"><span data-stu-id="111cb-154">In the demo data in the **USMF** company, create a task recording that has the following steps:</span></span>

    1. <span data-ttu-id="111cb-155">Gå till **Produktinformationshantering \> Produkter \> Frisläppta produkter**.</span><span class="sxs-lookup"><span data-stu-id="111cb-155">Go to **Product information management \> Products \> Released products**.</span></span>
    2. <span data-ttu-id="111cb-156">Använd snabbfiltret för att söka efter poster.</span><span class="sxs-lookup"><span data-stu-id="111cb-156">Use the Quick Filter to find records.</span></span> <span data-ttu-id="111cb-157">Filtrera till exempel i fältet **Artikelnummer** med värdet **1000**.</span><span class="sxs-lookup"><span data-stu-id="111cb-157">For example, filter on a value of **1000** for the **Item number** field.</span></span>
    3. <span data-ttu-id="111cb-158">Välj **lagerbehållning**</span><span class="sxs-lookup"><span data-stu-id="111cb-158">Select **On-hand inventory**.</span></span>
    4. <span data-ttu-id="111cb-159">Använd snabbfiltret för att söka efter poster.</span><span class="sxs-lookup"><span data-stu-id="111cb-159">Use the Quick Filter to find records.</span></span> <span data-ttu-id="111cb-160">Filtrera till exempel på värdet **1** i fältet **Plats**.</span><span class="sxs-lookup"><span data-stu-id="111cb-160">For example, filter on a value of **1** for the **Site** field.</span></span>
    5. <span data-ttu-id="111cb-161">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="111cb-161">In the list, mark the selected row.</span></span>
    6. <span data-ttu-id="111cb-162">Validera att värdet i fältet **totala tillgängliga** är **411,0000000000000000**.</span><span class="sxs-lookup"><span data-stu-id="111cb-162">Validate that the value of the **Total available** field is **411.0000000000000000**.</span></span>

2. <span data-ttu-id="111cb-163">Spara uppgiftsinspelningen till BPM-bibliotek i LCS och synkronisera den till Azure DevOps.</span><span class="sxs-lookup"><span data-stu-id="111cb-163">Save the task recording to the BPM library in LCS, and sync it to Azure DevOps.</span></span>
3. <span data-ttu-id="111cb-164">Lägg till testfallet testplanen och läs in testfallet i RSAT.</span><span class="sxs-lookup"><span data-stu-id="111cb-164">Add the test case to the test plan, and load the test case into RSAT.</span></span>
4. <span data-ttu-id="111cb-165">Öppna Excel-parameterfilen.</span><span class="sxs-lookup"><span data-stu-id="111cb-165">Open the Excel parameter file.</span></span> <span data-ttu-id="111cb-166">På fliken **InventOnhandItem** visas avsnittet **validera InventOnhandItem** som innehåller fältet **Operatör**.</span><span class="sxs-lookup"><span data-stu-id="111cb-166">On the **InventOnhandItem** tab, you will see a **Validate InventOnhandItem** section that includes an **Operator** field.</span></span>

    ![Fältet Operatör](./media/use_rsa_tool_08.png)

5. <span data-ttu-id="111cb-168">Om du vill validera om lagerbehållningen alltid är större än 0 ändrar du värdet i fältet **värde** från **411** till **0** och värdet för fältet **Operatör** från ett likhetstecken (**=**) till ett större än-tecken (**\>**).</span><span class="sxs-lookup"><span data-stu-id="111cb-168">To validate whether the inventory on-hand will always be more than 0, change the value of the **Value** field from **411** to **0** and the value of the **Operator** field from an equal sign (**=**) to a greater than sign (**\>**).</span></span>

    ![Värden för fälten värde och operatör har ändrats](./media/use_rsa_tool_09.png)

6. <span data-ttu-id="111cb-170">Spara och stäng Excel-parameterfilen.</span><span class="sxs-lookup"><span data-stu-id="111cb-170">Save and close the Excel parameter file.</span></span>
7. <span data-ttu-id="111cb-171">Välj **överför** om du vill spara ändringarna som du gjorde i Excel-parameterfilen till Azure DevOps.</span><span class="sxs-lookup"><span data-stu-id="111cb-171">Select **Upload** to save the changes that you made to the Excel parameter file to Azure DevOps.</span></span>

<span data-ttu-id="111cb-172">Om värdet för fältet **totalt tillgängliga** för den angivna artikeln i lagret är högre än 0 (noll), kommer testerna att lyckas, oavsett det faktiska lagerbehållningsvärdet.</span><span class="sxs-lookup"><span data-stu-id="111cb-172">Now, if the value of the **Total Available** field for the specified item in inventory is more than 0 (zero), tests will pass, regardless of the actual on-hand inventory value.</span></span>

### <a name="generator-logs"></a><span data-ttu-id="111cb-173">Generatorloggar</span><span class="sxs-lookup"><span data-stu-id="111cb-173">Generator logs</span></span>

<span data-ttu-id="111cb-174">Med den här funktionen skapas en mapp som innehåller loggarna för de testfall som har körts.</span><span class="sxs-lookup"><span data-stu-id="111cb-174">This feature creates a folder that contains the logs of the test cases that have been run.</span></span>

- <span data-ttu-id="111cb-175">Om du vill använda den här funktionen öppnar du filen **Microsoft.Dynamics.RegressionSuite.WindowsApp.exe.config** under RSAT-installationsmappen (t.ex. **C:\\programfiler (x86)\\Regression Suite Automation Tool**) och ändrar värdet i följande element från **falskt** till **sant**.</span><span class="sxs-lookup"><span data-stu-id="111cb-175">To use this feature, open the **Microsoft.Dynamics.RegressionSuite.WindowsApp.exe.config** file under the RSAT installation folder (for example, **C:\\Program Files (x86)\\Regression Suite Automation Tool**), and change the value in the following element from **false** to **true**.</span></span>

    ```
    <add key="LogGeneration" value="false" />
    ```

<span data-ttu-id="111cb-176">När testfallen har körts kan du hitta loggfilerna under **C:\\användare\\\<användarnamn\>\\AppData\\roaming\\regressionTool\\generatorLogs**.</span><span class="sxs-lookup"><span data-stu-id="111cb-176">After the test cases are run, you can find the log files under **C:\\Users\\\<Username\>\\AppData\\Roaming\\regressionTool\\generatorLogs**.</span></span>

![GeneratorLogs-mappen](./media/use_rsa_tool_10.png)

> [!NOTE]
> <span data-ttu-id="111cb-178">Om det finns existerande testfall innan du ändrade värdet i .config-filen, kommer inga loggar att genereras för dessa tester förrän du har genererat nya testkörningsfiler.</span><span class="sxs-lookup"><span data-stu-id="111cb-178">If there were existing test cases before you changed the value in the .config file, logs won't be generated for those test cases until you generate new test execution files.</span></span>
> 
> ![Generera kommandot endast textexekveringar på menyn Ny](./media/use_rsa_tool_11.png)

### <a name="snapshot"></a><span data-ttu-id="111cb-180">Ögonblicksbild</span><span class="sxs-lookup"><span data-stu-id="111cb-180">Snapshot</span></span>

<span data-ttu-id="111cb-181">Den här funktionen tar skärmbilder av de steg som har utförts under uppgiftsregistreringen.</span><span class="sxs-lookup"><span data-stu-id="111cb-181">This feature takes screenshots of the steps that were performed during task recording.</span></span>

- <span data-ttu-id="111cb-182">Om du vill använda den här funktionen öppnar du filen **Microsoft.Dynamics.RegressionSuite.WindowsApp.exe.config** under RSAT-installationsmappen (t.ex. **C:\\programfiler (x86)\\Regression Suite Automation Tool**) och ändrar värdet i följande element från **falskt** till **sant**.</span><span class="sxs-lookup"><span data-stu-id="111cb-182">To use this feature, open the **Microsoft.Dynamics.RegressionSuite.WindowsApp.exe.config** file under the RSAT installation folder (for example, **C:\\Program Files (x86)\\Regression Suite Automation Tool**), and change the value of the following element from **false** to **true**.</span></span>

    ```
    <add key="VerboseSnapshotsEnabled" value="false" />
    ```

<span data-ttu-id="111cb-183">Under **C:\\användare\\\<användarnamn\>\\AppData\\Roaming\\regressionTool\\uppspelning**, skapas en separat mapp för varje testfall som körs.</span><span class="sxs-lookup"><span data-stu-id="111cb-183">Under **C:\\Users\\\<Username\>\\AppData\\Roaming\\regressionTool\\playback**, a separate folder is created for each test case that is run.</span></span>

![Mappen ögonblicksbild för ett testfall](./media/use_rsa_tool_12.png)

<span data-ttu-id="111cb-185">I var och en av dessa mappar kan du söka efter ögonblicksbilder av stegen som utfördes medan testerna kördes.</span><span class="sxs-lookup"><span data-stu-id="111cb-185">In each of these folders, you can find snapshots of the steps that were performed while the test cases were run.</span></span>

![Ögonblicksbildfiler](./media/use_rsa_tool_13.png)

## <a name="assignment"></a><span data-ttu-id="111cb-187">Tilldelning</span><span class="sxs-lookup"><span data-stu-id="111cb-187">Assignment</span></span>

### <a name="scenario"></a><span data-ttu-id="111cb-188">Scenario</span><span class="sxs-lookup"><span data-stu-id="111cb-188">Scenario</span></span>

1. <span data-ttu-id="111cb-189">Produktdesignern skapar en ny frisläppt produkt.</span><span class="sxs-lookup"><span data-stu-id="111cb-189">The product designer creates a new released product.</span></span>
2. <span data-ttu-id="111cb-190">Produktionschefen initierar en tillverkningsorder för att ta med lagernivån till två delar.</span><span class="sxs-lookup"><span data-stu-id="111cb-190">The production manager initiates a production order to bring the stock level to two pieces.</span></span>
3. <span data-ttu-id="111cb-191">Produktion startar och avslutar produktionsordern och verifierar att lagerkvantiteten är två enheter.</span><span class="sxs-lookup"><span data-stu-id="111cb-191">Manufacturing starts and ends the production order, and verifies that the on-hand quantity is two pieces.</span></span>
4. <span data-ttu-id="111cb-192">Försäljningsteamet får en på fyra enheter av den nya produkten.</span><span class="sxs-lookup"><span data-stu-id="111cb-192">The sales team receives an order for four pieces of the new product.</span></span> <span data-ttu-id="111cb-193">Därför uppdaterar försäljningsteamet nettokraven via den dynamiska planen.</span><span class="sxs-lookup"><span data-stu-id="111cb-193">Therefore, the sales team updates the net requirements via the dynamic plan.</span></span> <span data-ttu-id="111cb-194">Eftersom ingen ytterligare kapacitet finns tillgänglig, anges standardorderprincipen till köp istället för tillverka.</span><span class="sxs-lookup"><span data-stu-id="111cb-194">Because no additional capacity is available, the default order policy is set to "buy instead of make."</span></span> <span data-ttu-id="111cb-195">Därför kapas en planerad inköpsorder.</span><span class="sxs-lookup"><span data-stu-id="111cb-195">Therefore, a planned purchase order is created.</span></span>
5. <span data-ttu-id="111cb-196">Köparen lägger till en leverantör, signerar den planerade inköpsordern och bekräftar sedan inköpsordern.</span><span class="sxs-lookup"><span data-stu-id="111cb-196">The buyer adds a vendor, firms the planned purchase order, and then confirms the purchase order.</span></span>
6. <span data-ttu-id="111cb-197">När varorna som köpts in anländer till butiken söker butiksoperatören efter den relaterade inköpsordern och tar emot varorna.</span><span class="sxs-lookup"><span data-stu-id="111cb-197">When the goods that were purchased arrive at the store, the store operator searches the related purchase order and receives the goods.</span></span> <span data-ttu-id="111cb-198">Eftersom ordern nu är slutförd kan varor plockas och förpackas mot försäljningsordern.</span><span class="sxs-lookup"><span data-stu-id="111cb-198">Because the order is now completed, goods can be picked and packed against the sales order.</span></span>
7. <span data-ttu-id="111cb-199">Ekonomi bokför inköpsfakturan och försäljningsfakturan.</span><span class="sxs-lookup"><span data-stu-id="111cb-199">Finance posts the purchase invoice and sales invoice.</span></span>

<span data-ttu-id="111cb-200">Följande bild visar flödet för det här scenariot.</span><span class="sxs-lookup"><span data-stu-id="111cb-200">The following illustration shows the flow for this scenario.</span></span>

![Flöde för demoscenariot](./media/use_rsa_tool_14.png)

<span data-ttu-id="111cb-202">Följande bild visar affärsprocesser för det här scenariot i RSAT.</span><span class="sxs-lookup"><span data-stu-id="111cb-202">The following illustration shows the business processes for this scenario in RSAT.</span></span>

![Affärsprocesser för demoscenariot](./media/use_rsa_tool_15.png)

## <a name="strategy--key-learning"></a><span data-ttu-id="111cb-204">Strategi – viktiga utbildningsmaterial</span><span class="sxs-lookup"><span data-stu-id="111cb-204">Strategy – Key learning</span></span>

### <a name="data"></a><span data-ttu-id="111cb-205">Data</span><span class="sxs-lookup"><span data-stu-id="111cb-205">Data</span></span>

- <span data-ttu-id="111cb-206">Se till att du har representativa datavolymer (en kopia av produktions- och gyllene konfigurationsdata plus migrerade data).</span><span class="sxs-lookup"><span data-stu-id="111cb-206">Make sure that you have representative data volumes (a copy of production/golden configuration data plus migrated data).</span></span>
- <span data-ttu-id="111cb-207">När du genererar nya data via uppgiftsregistrering ska du skapa testnamn som inte är i konflikt med befintliga namn (du kan till exempel använda prefix som **RSATxxx**).</span><span class="sxs-lookup"><span data-stu-id="111cb-207">When you generate new data via Task recorder, create test names that won't conflict with existing names (for example, use a prefix such as **RSATxxx**).</span></span>
- <span data-ttu-id="111cb-208">Använd Azure tidpunktsåterställning för att köra om tester på andra miljöer än icke-nivå 1.</span><span class="sxs-lookup"><span data-stu-id="111cb-208">Use Azure Point-In-Time restore to rerun tests in non-Tier 1 environments.</span></span>
- <span data-ttu-id="111cb-209">Även om du kan använda Excel-funktionerna **SLUMPMÄSSIGA** och **NU** för att generera en unik kombination, är arbetsinsatsen betydligt hög.</span><span class="sxs-lookup"><span data-stu-id="111cb-209">Although you can use the **RANDOM** and **NOW** Excel functions to generate a unique combination, the effort is considerably high.</span></span> <span data-ttu-id="111cb-210">Här är ett exempel:</span><span class="sxs-lookup"><span data-stu-id="111cb-210">Here is an example.</span></span>

    ```
    product = "AT" &TEXT(NOW(),"yyymmddhhmm")
    ```

### <a name="task-recorder"></a><span data-ttu-id="111cb-211">Uppgiftsregistrering</span><span class="sxs-lookup"><span data-stu-id="111cb-211">Task recorder</span></span>

- <span data-ttu-id="111cb-212">Definiera scenarier innan du startar inspelningen.</span><span class="sxs-lookup"><span data-stu-id="111cb-212">Define scenarios before you start recording.</span></span> <span data-ttu-id="111cb-213">Ett välhanterat projekt har fördefinierade testscenarier.</span><span class="sxs-lookup"><span data-stu-id="111cb-213">A well-managed project has predefined test scenarios.</span></span> <span data-ttu-id="111cb-214">Om du vill bygga ett testfall bör du överväga hur förutsägbara resultatet av testscenarierna är.</span><span class="sxs-lookup"><span data-stu-id="111cb-214">To build a test case, consider how predictable the outcome of those test scenarios is.</span></span>
- <span data-ttu-id="111cb-215">Dela upp inspelningar om de utförs av olika roller eller om det finns väntetid eller extern händelse före nästa steg.</span><span class="sxs-lookup"><span data-stu-id="111cb-215">Split recordings if they are performed by different roles, or if there is waiting time or an external event before the next step.</span></span>
- <span data-ttu-id="111cb-216">Undvik att markera värden i listor.</span><span class="sxs-lookup"><span data-stu-id="111cb-216">Avoid selecting values in lists.</span></span> <span data-ttu-id="111cb-217">Använd i stället textformat, t.ex. **FIFO**. **AudioRM** och **SiteWH**.</span><span class="sxs-lookup"><span data-stu-id="111cb-217">Instead, use text formats, such as **FIFO**, **AudioRM**, and **SiteWH**.</span></span> <span data-ttu-id="111cb-218">När du väljer i en lista registreras placeringen av värdet i listan, inte själva värdet.</span><span class="sxs-lookup"><span data-stu-id="111cb-218">When you select in a list, the position of the value in the list is recorded, not the value itself.</span></span> <span data-ttu-id="111cb-219">Om du lägger till objekt i listan kan placeringen av värdet ändras.</span><span class="sxs-lookup"><span data-stu-id="111cb-219">If items are added to that list, the position of the value can change.</span></span> <span data-ttu-id="111cb-220">Därför kommer din registrering att använda en annan parameter och resten av scenariot kan påverkas.</span><span class="sxs-lookup"><span data-stu-id="111cb-220">Therefore, your recording will use a different parameter, and the rest of the scenario might be affected.</span></span>
- <span data-ttu-id="111cb-221">Tänk på hur flera användare fungerar.</span><span class="sxs-lookup"><span data-stu-id="111cb-221">Think about multi-user behavior.</span></span> <span data-ttu-id="111cb-222">Antag till exempel inte att den nya försäljningsordern alltid väljs automatiskt.</span><span class="sxs-lookup"><span data-stu-id="111cb-222">For example, don't assume that your newly created sales order will always be automatically selected.</span></span> <span data-ttu-id="111cb-223">I stället ska du alltid använda filtret för att hitta rätt ordning.</span><span class="sxs-lookup"><span data-stu-id="111cb-223">Instead, always use the filter to find the correct order.</span></span>
- <span data-ttu-id="111cb-224">Använd kopieringsfunktionen i uppgiftsinspelning om du vill spara namnet på en nyskapad produkt så att den kan användas i kedjade testfall.</span><span class="sxs-lookup"><span data-stu-id="111cb-224">Use the Copy function in Task recorder to save the name of a newly created product so it can be used in chained test cases.</span></span>
- <span data-ttu-id="111cb-225">Använd funktionen validera i uppgiftsregistrering om du vill ställa in kontrollpunkter som verifierar att stegen har körts på rätt sätt.</span><span class="sxs-lookup"><span data-stu-id="111cb-225">Use the Validate function in Task recorder to set checkpoints that verify that steps have been run correctly.</span></span>

### <a name="rsat"></a><span data-ttu-id="111cb-226">RSAT</span><span class="sxs-lookup"><span data-stu-id="111cb-226">RSAT</span></span>

- <span data-ttu-id="111cb-227">Om du vill köra testet i ett annat företag kan du ändra företaget på fliken **allmänt** i Excel-parameterfilen.</span><span class="sxs-lookup"><span data-stu-id="111cb-227">To run the test in another company, you can change the company on the **General** tab of the Excel parameter file.</span></span> <span data-ttu-id="111cb-228">Kontrollera att inställningar och data är tillgängliga i det valda företaget.</span><span class="sxs-lookup"><span data-stu-id="111cb-228">Make sure that settings and data are available in the newly selected company.</span></span>
- <span data-ttu-id="111cb-229">Du kan ändra testanvändaren på fliken **allmänt** i Excel-parameterfilen.</span><span class="sxs-lookup"><span data-stu-id="111cb-229">You can change the test user on the **General** tab of the Excel parameter file.</span></span> <span data-ttu-id="111cb-230">Ange e-post-ID för den användare som ska köra test fallet.</span><span class="sxs-lookup"><span data-stu-id="111cb-230">Specify the email ID of the user who will run the test case.</span></span> <span data-ttu-id="111cb-231">På så sätt kan testfallet köras med hjälp av den angivna användarens säkerhetsbehörigheter.</span><span class="sxs-lookup"><span data-stu-id="111cb-231">In this way, the test case can be run by using the security permissions of the specified user.</span></span>
- <span data-ttu-id="111cb-232">Om du vill vänta innan testet påbörjas kan du definiera en paus på fliken **allmänt** i Excel-parameterfilen.</span><span class="sxs-lookup"><span data-stu-id="111cb-232">To wait before the test is started, you can define a pause on the **General** tab of the Excel parameter file.</span></span> <span data-ttu-id="111cb-233">Denna paus kan användas i ett batchjobb (t.ex. om ett arbetsflöde måste köras innan nästa steg kan utföras.)</span><span class="sxs-lookup"><span data-stu-id="111cb-233">This pause can be used in a batch job (for example, if a workflow must be run before the next step can be performed.)</span></span>

## <a name="advanced-scripting"></a><span data-ttu-id="111cb-234">Avancerade skript</span><span class="sxs-lookup"><span data-stu-id="111cb-234">Advanced scripting</span></span>

### <a name="command-line"></a><span data-ttu-id="111cb-235">Kommandorad</span><span class="sxs-lookup"><span data-stu-id="111cb-235">Command line</span></span>

<span data-ttu-id="111cb-236">RSAT kan anropas från fönstret **kommandotolk**.</span><span class="sxs-lookup"><span data-stu-id="111cb-236">RSAT can be called from a **Command Prompt** window.</span></span>

> [!NOTE]
> <span data-ttu-id="111cb-237">Kontrollera att miljövariabeln **TestRoot** anges till RSAT installationens sökväg.</span><span class="sxs-lookup"><span data-stu-id="111cb-237">Verify that the **TestRoot** environment variable is set to the RSAT installation path.</span></span> <span data-ttu-id="111cb-238">(I Microsoft Windows, öppna **kontrollkontroll**, välj **Systemoch säkerhet \> System \> Avancerade systeminställningar** och välj sedan **miljövariabler**.)</span><span class="sxs-lookup"><span data-stu-id="111cb-238">(In Microsoft Windows, open **Control Panel**, select **System and Security \> System \> Advanced system settings**, and then select **Environment Variables**.)</span></span>

1. <span data-ttu-id="111cb-239">Öppna ett **kommandotolk**-fönster som en adminstratör.</span><span class="sxs-lookup"><span data-stu-id="111cb-239">Open a **Command Prompt** window as an admin.</span></span>
2. <span data-ttu-id="111cb-240">Kör verktyget från installationskatalogen.</span><span class="sxs-lookup"><span data-stu-id="111cb-240">Run the tool from the installation directory.</span></span>

    ```
    cd "c:\Program Files (x86)\Regression Suite Automation Tool\"
    ```

3. <span data-ttu-id="111cb-241">Lista alla kommandon.</span><span class="sxs-lookup"><span data-stu-id="111cb-241">List all commands.</span></span>

    ```
    C:\Program Files (x86)\Regression Suite Automation Tool>Microsoft.Dynamics.RegressionSuite.ConsoleApp.exe help

    Usage:
        Microsoft.Dynamics.RegressionSuite.ConsoleApp.exe command
        or
        Microsoft.Dynamics.RegressionSuite.ConsoleApp.exe /settings "C:\Path to\file.settings" command

    Available commands:
        list
        listtestsuite suite_name
        download test_case_id output_dir
        generate test_case_id output_dir
        generatederived parent_test_case_id test_plan_id test_suite_id
        generatetestonly test_case_id output_dir
        edit excel_file
        playback excel_file
        playbackmany excel_file1 [excel_file2 [.. excel_fileN]]
        playbackbyid test_case_id1 [test_case_id2 [.. test_case_idN]]
        playbacksuite suite_name
        clear
        help
        about
        quit
    ```

### <a name="windows-powershell-examples"></a><span data-ttu-id="111cb-242">Windows PowerShell-exempel</span><span class="sxs-lookup"><span data-stu-id="111cb-242">Windows PowerShell examples</span></span>

#### <a name="run-a-test-case-in-a-loop"></a><span data-ttu-id="111cb-243">Kör ett testfall i en slinga</span><span class="sxs-lookup"><span data-stu-id="111cb-243">Run a test case in a loop</span></span>

<span data-ttu-id="111cb-244">Du har ett testskript som skapar en ny kund.</span><span class="sxs-lookup"><span data-stu-id="111cb-244">You have a test script that creates a new customer.</span></span> <span data-ttu-id="111cb-245">Via skript kan det här testfallet köras i en slinga genom att göra slumpmässiga följandande data innan varje iteration körs:</span><span class="sxs-lookup"><span data-stu-id="111cb-245">Via scripting, this test case can be run in a loop by randomizing the following data before each iteration is run:</span></span>

- <span data-ttu-id="111cb-246">Kund-ID</span><span class="sxs-lookup"><span data-stu-id="111cb-246">Customer ID</span></span>
- <span data-ttu-id="111cb-247">Kundnamn</span><span class="sxs-lookup"><span data-stu-id="111cb-247">Customer name</span></span>
- <span data-ttu-id="111cb-248">Adress till kund</span><span class="sxs-lookup"><span data-stu-id="111cb-248">Customer address</span></span>

<span data-ttu-id="111cb-249">Kund-ID:t anges i formatet *ATCUS\<nummer\>*, där \<nummer\> är ett värde mellan **000000001** och **999999999**.</span><span class="sxs-lookup"><span data-stu-id="111cb-249">The customer ID will be in the format *ATCUS\<number\>*, where \<number\> is a value between **000000001** and **999999999**.</span></span>

<span data-ttu-id="111cb-250">I följande exempel används en parameter, **Start**för att definiera det första numret som används.</span><span class="sxs-lookup"><span data-stu-id="111cb-250">The following example uses one parameter, **start**, to define the first number that is used.</span></span> <span data-ttu-id="111cb-251">Det använder en andra parameter, **nr**, för att definiera antalet kunder som måste skapas.</span><span class="sxs-lookup"><span data-stu-id="111cb-251">Is uses a second parameter, **nr**, to define the number of customers that must be created.</span></span> <span data-ttu-id="111cb-252">För varje upprepning ändras parametrarna i Excel-parameterfil med hjälp av en UpdateCustomer-funktion.</span><span class="sxs-lookup"><span data-stu-id="111cb-252">For each iteration, the parameters in the Excel parameter file are changed by using an UpdateCustomer function.</span></span> <span data-ttu-id="111cb-253">Då anropas kommando raden för RSAT i en RunTestCase-funktion.</span><span class="sxs-lookup"><span data-stu-id="111cb-253">Then the RSAT command line is called in a RunTestCase function.</span></span>

<span data-ttu-id="111cb-254">Öppna Microsoft Windows PowerShell ISE (Integrated Scripting Environment) i administrationsläge och klistra in följande kod i fönstret med namnet **Untitled1.ps1**.</span><span class="sxs-lookup"><span data-stu-id="111cb-254">Open Microsoft Windows PowerShell Integrated Scripting Environment (ISE) in admin mode, and paste the following code into the window that is named **Untitled1.ps1**.</span></span>

```
param ( [int]$start = 1, [int]$nr = 1 )
function UpdateCustomer
{
    param ([string]$paramFilename, [string]$sheetName, [string]$CustId)
    $xl = New-Object -COM "Excel.Application"
    $xl.Visible = $false
    $wb = $xl.Workbooks.Open($paramFilename)
    $ws = $wb.Sheets.Item($sheetName)
    $ws.Cells.Item(3, 2).Value = "ATCUS" + $CustId
    $ws.Cells.Item(4, 2).Value = "Automated Test Customer " + $CustId
    $ws.Cells.Item(8, 2).Value = "Automated Test Street " + $CustId
    $wb.Save()
    $wb.Close()
    $xl.Quit()
    [System.Runtime.Interopservices.Marshal]::ReleaseComObject($xl)
}
function RunTestCase
{
    param ( [string]$filename )
    $cmd = "cd c:\Program Files (x86)\Regression Suite Automation Tool\ &&  "
    $cmd = $cmd + "Microsoft.Dynamics.RegressionSuite.ConsoleApp.exe playback "
    $cmd = $cmd + $filename
    cmd /c $cmd
}
$excelFilename = "full path to excel file parameter file"
l$sheetName = "DirPartyQuickCreateForm"
for ($i = $start; $i -lt $start + $nr; $i++ )
{
    $CustomerId = $i.ToString("000000000")
    Write-Host "customer : " $CustomerId
    UpdateCustomer $excelFilename $sheetName $CustomerId
    RunTestCase $excelFilename
```

#### <a name="run-a-script-that-depends-on-data-in-microsoft-dynamics-365"></a><span data-ttu-id="111cb-255">Köra ett skript som är beroende av data i Microsoft Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="111cb-255">Run a script that depends on data in Microsoft Dynamics 365</span></span>

<span data-ttu-id="111cb-256">I följande exempel används ett OData-anrop (Open Data Protocol) för att hitta orderstatusen för en inköpsorder.</span><span class="sxs-lookup"><span data-stu-id="111cb-256">The following example uses an Open Data Protocol (OData) call to find the order status of a purchase order.</span></span> <span data-ttu-id="111cb-257">Om statusvärdet inte har **fakturerats** kan du t.ex. anropa ett testfall för RSAT som bokför fakturan.</span><span class="sxs-lookup"><span data-stu-id="111cb-257">If the status isn't **invoiced**, you can, for example, call an RSAT test case that posts the invoice.</span></span>

```
function Odata_Get
{
    Param ( [string] $environment, [string] $cmd )
    [Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12
    $tenant = "your tenant"
    $creds = @{
        grant_type = "client_credentials"
        client_id = "your client application Id"
        client_secret = "your client secret"
        resource = $environment
    }
    $headers = $null
    $bearer = Invoke-RestMethod https://login.microsoftonline.com/$tenant/oauth2/token -Method Post -Body $creds -Headers $headers;
    $headers = @{
        Authorization = "Bearer " + $bearer.access_token
    }
    $Odata_cmd = $environment + '/data/' + $cmd
    return (Invoke-RestMethod -Uri $Odata_cmd -Method Get -Headers $headers -ContentType application/json )
}
function PurchaseOrderStatus
{
    Param ( [string] $environment, [string] $purchaseOrderNumber )
    $cmd = 'PurchaseOrderHeaders?$filter=PurchaseOrderNumber eq '
    $cmd = $cmd + "'" + $purchaseOrderNumber + "'"
    $response = Odata_Get -environment $environment -cmd $cmd
    return $response.value.PurchaseOrderStatus
}
$environment = "https://your environment"
$orderStatus = PurchaseOrderStatus -environment $environment -purchaseOrderNumber '000003'
if ($orderStatus -eq $null) {   write-host 'doesn''t exist'}
elseif ($orderStatus -ne 'invoiced') { RunTestCase "PostInvoice" }
```
