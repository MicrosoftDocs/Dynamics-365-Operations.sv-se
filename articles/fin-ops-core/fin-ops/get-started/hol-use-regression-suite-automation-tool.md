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
ms.openlocfilehash: 6cdaa89fb6d50ebaaaefe7f92d7224a1567d17d1
ms.sourcegitcommit: 3dede95a3b17de920bb0adcb33029f990682752b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/18/2020
ms.locfileid: "3070830"
---
# <a name="use-the-regression-suite-automation-tool-tutorial"></a><span data-ttu-id="57f61-104">Använda självstudie för Regression Suite Automation Tool</span><span class="sxs-lookup"><span data-stu-id="57f61-104">Use the Regression suite automation tool tutorial</span></span>

[!include [banner](../includes/banner.md)]

> [!NOTE]
> <span data-ttu-id="57f61-105">Använd webbläsarverktygen för att hämta och spara sidan i PDF-format.</span><span class="sxs-lookup"><span data-stu-id="57f61-105">Use your internet browser tools to download and save this page in pdf format.</span></span> 

<span data-ttu-id="57f61-106">I den här vägledningen får du hjälp med några av de avancerade funktionerna i RSAT (Regression Suite Automation Tool), inkluderar en demotilldelning och beskriver strategi- och nyckelutbildningspunkter.</span><span class="sxs-lookup"><span data-stu-id="57f61-106">This tutorial walks through some of the advanced features of the Regression suite automation tool (RSAT), includes a demo assignment, and describes strategy and key learning points.</span></span>

## <a name="features-of-rsattask-recorder"></a><span data-ttu-id="57f61-107">Funktioner av RSAT/Uppgiftsregistrering</span><span class="sxs-lookup"><span data-stu-id="57f61-107">Features of RSAT/Task recorder</span></span>

### <a name="validate-a-field-value"></a><span data-ttu-id="57f61-108">Validera fältvärdet</span><span class="sxs-lookup"><span data-stu-id="57f61-108">Validate a field value</span></span>

<span data-ttu-id="57f61-109">Mer information om den här funktionen finns i [skapa en ny uppgiftsregistrering som har en Validera-funktion](./hol-set-up-regression-suite-automation-tool.md#create-a-new-task-recording-that-has-a-validate-function).</span><span class="sxs-lookup"><span data-stu-id="57f61-109">For information about this feature, see the [Create a new task recording that has a Validate function](./hol-set-up-regression-suite-automation-tool.md#create-a-new-task-recording-that-has-a-validate-function).</span></span>

### <a name="saved-variable"></a><span data-ttu-id="57f61-110">Sparad variabel</span><span class="sxs-lookup"><span data-stu-id="57f61-110">Saved variable</span></span>

<span data-ttu-id="57f61-111">Mer information om den här funktionen finns i [ändra en befintlig uppgiftsregistrering och skapa en sparad variabel](./hol-set-up-regression-suite-automation-tool.md#modify-an-existing-task-recording-to-create-a-saved-variable).</span><span class="sxs-lookup"><span data-stu-id="57f61-111">For information about this feature, see the [Modify an existing task recording to create a saved variable](./hol-set-up-regression-suite-automation-tool.md#modify-an-existing-task-recording-to-create-a-saved-variable).</span></span>

### <a name="derived-test-case"></a><span data-ttu-id="57f61-112">Härlett testfall</span><span class="sxs-lookup"><span data-stu-id="57f61-112">Derived test case</span></span>

1. <span data-ttu-id="57f61-113">Öppna verktyget RSAT (Regression Suite Automation Tool) och markera båda testärenden som du har skapat i [Självstudie för konfigurera och installera Regression Suite Automation Tool](./hol-set-up-regression-suite-automation-tool.md).</span><span class="sxs-lookup"><span data-stu-id="57f61-113">Open Regression suite automation tool (RSAT), and select both the test cases that you created in [Set up and install Regression suite automation tool tutorial](./hol-set-up-regression-suite-automation-tool.md).</span></span>
2. <span data-ttu-id="57f61-114">Välj **ny \> skapa härlett testfall**.</span><span class="sxs-lookup"><span data-stu-id="57f61-114">Select **New \> Create derived test case**.</span></span>

    ![Kommandot Skapa härlett testfallkommando på den nya menyn](./media/use_rsa_tool_01.png)

3. <span data-ttu-id="57f61-116">Ett meddelande visas om att ett härlett testfall kommer att skapas för varje valt testfall i det aktuella testpaketet och att varje härlett testfall har en egen kopia av Excel-parameterfilen.</span><span class="sxs-lookup"><span data-stu-id="57f61-116">You receive a message that states that a derived test case will be created for each selected test case in the current test suite, and that each derived test case will have its own copy of the Excel parameter file.</span></span> <span data-ttu-id="57f61-117">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="57f61-117">Select **OK**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="57f61-118">När du kör ett härlett testfall använder det uppgiftsinspelningen av det överordnade testfallet och den egna kopian av Excel-parameterfilen.</span><span class="sxs-lookup"><span data-stu-id="57f61-118">When you run a derived test case, it uses the task recording of its parent test case and its own copy of the Excel parameter file.</span></span> <span data-ttu-id="57f61-119">På så sätt kan du köra samma test med olika parametrar utan att behöva underhålla fler än en uppgiftsinspelning.</span><span class="sxs-lookup"><span data-stu-id="57f61-119">In this way, you can run the same test with different parameters, without having to maintain more than one task recording.</span></span> <span data-ttu-id="57f61-120">Ett härlett testfall behöver inte vara en del av samma testserie som det överordnade testfallet.</span><span class="sxs-lookup"><span data-stu-id="57f61-120">A derived test case doesn't have to be part of the same test suite as its parent test case.</span></span>

    ![Meddelanderuta](./media/use_rsa_tool_02.png)

    <span data-ttu-id="57f61-122">Två ytterligare härledda testfall skapas och kryssrutan **härledda?** markeras för dem.</span><span class="sxs-lookup"><span data-stu-id="57f61-122">Two additional derived test cases are created, and the **Derived?** check box is selected for them.</span></span>

    ![Härledda testfall har skapats](./media/use_rsa_tool_03.png)

    <span data-ttu-id="57f61-124">Ett härlett testfall skapas automatiskt i Azure DevOps.</span><span class="sxs-lookup"><span data-stu-id="57f61-124">A derived test case is automatically created in Azure DevOps.</span></span> <span data-ttu-id="57f61-125">Det är ett underordnat objekt till testfallet **skapa en ny produkt** och märks med ett särskilt nyckelord: **RSAT:DerivedTestSteps**.</span><span class="sxs-lookup"><span data-stu-id="57f61-125">It's a child item of the **Create a new product** test case and is tagged with a special keyword: **RSAT:DerivedTestSteps**.</span></span> <span data-ttu-id="57f61-126">Dessa testfall läggs också automatiskt till i testplanen i Azure DevOps.</span><span class="sxs-lookup"><span data-stu-id="57f61-126">These test cases are also automatically added to the test plan in Azure DevOps.</span></span>

    ![RSAT:DerivedTestSteps-nyckelord](./media/use_rsa_tool_04.png)

    > [!NOTE]
    > <span data-ttu-id="57f61-128">Om de härledda testfallet som skapas inte finns i rätt ordning går du till Azure DevOps och beställer testfallen igen i testpaketet så att RSAT kan köras i rätt ordning.</span><span class="sxs-lookup"><span data-stu-id="57f61-128">If, for any reason, the derived test cases that are created aren't in the correct order, go to Azure DevOps, and reorder the test cases in the test suite, so that RSAT can run them in the correct order.</span></span>

4. <span data-ttu-id="57f61-129">Markera de härledda testfall och välj sedan **redigera** för att öppna motsvarande Excel-parameterfiler.</span><span class="sxs-lookup"><span data-stu-id="57f61-129">Select the derived test cases, and then select **Edit** to open the corresponding Excel parameter files.</span></span>
5. <span data-ttu-id="57f61-130">Redigera dessa Excel-parametervärden på samma sätt som du redigerade de överordnade filerna.</span><span class="sxs-lookup"><span data-stu-id="57f61-130">Edit these Excel parameter files in the same way that you edited the parent files.</span></span> <span data-ttu-id="57f61-131">Med andra ord måste du se till att produkt-ID:t är inställt så att det skapas automatiskt.</span><span class="sxs-lookup"><span data-stu-id="57f61-131">In other words, make sure that the product ID is set so that it's automatically generated.</span></span> <span data-ttu-id="57f61-132">Kontrollera också att den sparade variabeln kopieras till relevanta fält.</span><span class="sxs-lookup"><span data-stu-id="57f61-132">Also make sure that the saved variable is copied to the relevant fields.</span></span>
6. <span data-ttu-id="57f61-133">På fliken **allmänt** i båda Excel-parameterfiler uppdaterar du värdet för fältet **företag** till **Ussi**, så att de härledda testfallen kan köras mot en annan juridisk person än det överordnade testfallet.</span><span class="sxs-lookup"><span data-stu-id="57f61-133">On the **General** tab of both Excel parameter files, update the value of the **Company** field to **USSI**, so that the derived test cases will be run against a different legal entity than the parent test case.</span></span> <span data-ttu-id="57f61-134">Om du vill köra testfall mot mot en viss användare (eller den roll som är associerad med en viss användare) kan du uppdatera värdet i fältet **testanvändare.**</span><span class="sxs-lookup"><span data-stu-id="57f61-134">To run the test cases against a specific user (or the role that is associated with a specific user), you can update the value of the **Test User** field.</span></span>
7. <span data-ttu-id="57f61-135">Välj **kör**och validera att produkten har skapats i både den USMF juridiska personen och den USSI juridiska personen.</span><span class="sxs-lookup"><span data-stu-id="57f61-135">Select **Run**, and validate that the product is created in both the USMF legal entity and the USSI legal entity.</span></span>

### <a name="validate-notifications"></a><span data-ttu-id="57f61-136">Validera meddelanden</span><span class="sxs-lookup"><span data-stu-id="57f61-136">Validate notifications</span></span>

<span data-ttu-id="57f61-137">Den här funktionen kan användas för att validera om en åtgärd utförts.</span><span class="sxs-lookup"><span data-stu-id="57f61-137">This feature can be used to validate whether an action occurred.</span></span> <span data-ttu-id="57f61-138">När till exempel en tillverkningsorder skapas, uppskattas och sedan startas, visar appen meddelandet "produktion – start" för att meddela dig att tillverkningsordern har startats.</span><span class="sxs-lookup"><span data-stu-id="57f61-138">For example, when a production order is created, estimated, and then started, the app shows a "Production – Start" message to notify you that the production order has been started.</span></span>

![Produktion - starta meddelande](./media/use_rsa_tool_05.png)

<span data-ttu-id="57f61-140">Du kan validera det här meddelandet genom RSAT genom att ange meddelande texten på fliken **MessageValidation** i Excel-parameterfilen för lämplig inspelning.</span><span class="sxs-lookup"><span data-stu-id="57f61-140">You can validate this message through RSAT by entering the message text on the **MessageValidation** tab of the Excel parameter file for the appropriate recording.</span></span>

![Fliken Meddelandevalidering](./media/use_rsa_tool_06.png)

<span data-ttu-id="57f61-142">När testfallet har körts, jämförs meddelandet i Excel-parameterfilen i det meddelande som visas.</span><span class="sxs-lookup"><span data-stu-id="57f61-142">After the test case is run, the message in the Excel parameter file is compared to the message that is shown.</span></span> <span data-ttu-id="57f61-143">Om meddelandena inte matchar kommer testfallet att misslyckas.</span><span class="sxs-lookup"><span data-stu-id="57f61-143">If the messages don't match, the test case will fail.</span></span>

> [!NOTE]
> <span data-ttu-id="57f61-144">Du kan ange mer än ett meddelande på fliken **MessageValidation** i Excel-parameterfilen.</span><span class="sxs-lookup"><span data-stu-id="57f61-144">You can enter more than one message on the **MessageValidation** tab in the Excel parameter file.</span></span> <span data-ttu-id="57f61-145">Meddelandena kan också vara fel- eller varningsmeddelanden i stället för informationsmeddelanden.</span><span class="sxs-lookup"><span data-stu-id="57f61-145">The messages also can be error or warning messages instead of informational messages.</span></span>

### <a name="validate-values-by-using-operators"></a><span data-ttu-id="57f61-146">Validera värden med hjälp av operatörer</span><span class="sxs-lookup"><span data-stu-id="57f61-146">Validate values by using operators</span></span>

<span data-ttu-id="57f61-147">I tidigare versioner av RSAT kunde du bara validera värden om ett kontrollvärde är lika med ett förväntat värde.</span><span class="sxs-lookup"><span data-stu-id="57f61-147">In previous versions of RSAT, you could validate values only if a control value equaled an expected value.</span></span> <span data-ttu-id="57f61-148">Med den nya funktionen kan du validera att en variabel inte är lika med, är mindre än eller mer än ett angivet värde.</span><span class="sxs-lookup"><span data-stu-id="57f61-148">The new feature lets you validate that a variable isn't equal to, is less than, or is more than a specified value.</span></span>

- <span data-ttu-id="57f61-149">Om du vill använda den här funktionen öppnar du filen **Microsoft.Dynamics.RegressionSuite.WindowsApp.exe.config** under RSAT-installationsmappen (t.ex. **C:\\programfiler (x86)\\Regression Suite Automation Tool**) och ändrar värdet i följande element från **falskt** till **sant**.</span><span class="sxs-lookup"><span data-stu-id="57f61-149">To use this feature, open the **Microsoft.Dynamics.RegressionSuite.WindowsApp.exe.config** file under the RSAT installation folder (for example, **C:\\Program Files (x86)\\Regression Suite Automation Tool**), and change the value in the following element from **false** to **true**.</span></span>

    ```xml
    <add key="AddOperatorFieldsToExcelValidation" value="false" />
    ```

    <span data-ttu-id="57f61-150">I Excel-parameterfilen visas ett nytt fält med **operatör**.</span><span class="sxs-lookup"><span data-stu-id="57f61-150">In the Excel parameter file, a new **Operator** field appears.</span></span>

    > [!NOTE]
    > <span data-ttu-id="57f61-151">Om du har använt en äldre version av RSAT måste du generera nya Excel-parameterstyrda filer.</span><span class="sxs-lookup"><span data-stu-id="57f61-151">If you've been using an older version of RSAT, you must generate new Excel parameter files.</span></span>

    ![Fältet Operatör](./media/use_rsa_tool_07.png)

<span data-ttu-id="57f61-153">I följande exempel visas hur du kan använda den här funktionen för att validera om lagerbehållningen är större än 0 (noll).</span><span class="sxs-lookup"><span data-stu-id="57f61-153">The following example shows how you can use this feature to validate whether the on-hand inventory is more than 0 (zero).</span></span>

1. <span data-ttu-id="57f61-154">I demonstrationsdata i **USMF**-företaget skapar du en uppgiftsregistrering med följande steg:</span><span class="sxs-lookup"><span data-stu-id="57f61-154">In the demo data in the **USMF** company, create a task recording that has the following steps:</span></span>

    1. <span data-ttu-id="57f61-155">Gå till **Produktinformationshantering \> Produkter \> Frisläppta produkter**.</span><span class="sxs-lookup"><span data-stu-id="57f61-155">Go to **Product information management \> Products \> Released products**.</span></span>
    2. <span data-ttu-id="57f61-156">Använd snabbfiltret för att söka efter poster.</span><span class="sxs-lookup"><span data-stu-id="57f61-156">Use the Quick Filter to find records.</span></span> <span data-ttu-id="57f61-157">Filtrera till exempel i fältet **Artikelnummer** med värdet **1000**.</span><span class="sxs-lookup"><span data-stu-id="57f61-157">For example, filter on a value of **1000** for the **Item number** field.</span></span>
    3. <span data-ttu-id="57f61-158">Välj **lagerbehållning**</span><span class="sxs-lookup"><span data-stu-id="57f61-158">Select **On-hand inventory**.</span></span>
    4. <span data-ttu-id="57f61-159">Använd snabbfiltret för att söka efter poster.</span><span class="sxs-lookup"><span data-stu-id="57f61-159">Use the Quick Filter to find records.</span></span> <span data-ttu-id="57f61-160">Filtrera till exempel på värdet **1** i fältet **Plats**.</span><span class="sxs-lookup"><span data-stu-id="57f61-160">For example, filter on a value of **1** for the **Site** field.</span></span>
    5. <span data-ttu-id="57f61-161">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="57f61-161">In the list, mark the selected row.</span></span>
    6. <span data-ttu-id="57f61-162">Validera att värdet i fältet **totala tillgängliga** är **411,0000000000000000**.</span><span class="sxs-lookup"><span data-stu-id="57f61-162">Validate that the value of the **Total available** field is **411.0000000000000000**.</span></span>

2. <span data-ttu-id="57f61-163">Spara uppgiftsinspelningen till BPM-bibliotek i LCS och synkronisera den till Azure DevOps.</span><span class="sxs-lookup"><span data-stu-id="57f61-163">Save the task recording to the BPM library in LCS, and sync it to Azure DevOps.</span></span>
3. <span data-ttu-id="57f61-164">Lägg till testfallet testplanen och läs in testfallet i RSAT.</span><span class="sxs-lookup"><span data-stu-id="57f61-164">Add the test case to the test plan, and load the test case into RSAT.</span></span>
4. <span data-ttu-id="57f61-165">Öppna Excel-parameterfilen.</span><span class="sxs-lookup"><span data-stu-id="57f61-165">Open the Excel parameter file.</span></span> <span data-ttu-id="57f61-166">På fliken **InventOnhandItem** visas avsnittet **validera InventOnhandItem** som innehåller fältet **Operatör**.</span><span class="sxs-lookup"><span data-stu-id="57f61-166">On the **InventOnhandItem** tab, you will see a **Validate InventOnhandItem** section that includes an **Operator** field.</span></span>

    ![Fältet Operatör](./media/use_rsa_tool_08.png)

5. <span data-ttu-id="57f61-168">Om du vill validera om lagerbehållningen alltid är större än 0 ändrar du värdet i fältet **värde** från **411** till **0** och värdet för fältet **Operatör** från ett likhetstecken (**=**) till ett större än-tecken (**\>**).</span><span class="sxs-lookup"><span data-stu-id="57f61-168">To validate whether the inventory on-hand will always be more than 0, change the value of the **Value** field from **411** to **0** and the value of the **Operator** field from an equal sign (**=**) to a greater than sign (**\>**).</span></span>

    ![Värden för fälten värde och operatör har ändrats](./media/use_rsa_tool_09.png)

6. <span data-ttu-id="57f61-170">Spara och stäng Excel-parameterfilen.</span><span class="sxs-lookup"><span data-stu-id="57f61-170">Save and close the Excel parameter file.</span></span>
7. <span data-ttu-id="57f61-171">Välj **överför** om du vill spara ändringarna som du gjorde i Excel-parameterfilen till Azure DevOps.</span><span class="sxs-lookup"><span data-stu-id="57f61-171">Select **Upload** to save the changes that you made to the Excel parameter file to Azure DevOps.</span></span>

<span data-ttu-id="57f61-172">Om värdet för fältet **totalt tillgängliga** för den angivna artikeln i lagret är högre än 0 (noll), kommer testerna att lyckas, oavsett det faktiska lagerbehållningsvärdet.</span><span class="sxs-lookup"><span data-stu-id="57f61-172">Now, if the value of the **Total Available** field for the specified item in inventory is more than 0 (zero), tests will pass, regardless of the actual on-hand inventory value.</span></span>

### <a name="generator-logs"></a><span data-ttu-id="57f61-173">Generatorloggar</span><span class="sxs-lookup"><span data-stu-id="57f61-173">Generator logs</span></span>

<span data-ttu-id="57f61-174">Med den här funktionen skapas en mapp som innehåller loggarna för de testfall som har körts.</span><span class="sxs-lookup"><span data-stu-id="57f61-174">This feature creates a folder that contains the logs of the test cases that have been run.</span></span>

- <span data-ttu-id="57f61-175">Om du vill använda den här funktionen öppnar du filen **Microsoft.Dynamics.RegressionSuite.WindowsApp.exe.config** under RSAT-installationsmappen (t.ex. **C:\\programfiler (x86)\\Regression Suite Automation Tool**) och ändrar värdet i följande element från **falskt** till **sant**.</span><span class="sxs-lookup"><span data-stu-id="57f61-175">To use this feature, open the **Microsoft.Dynamics.RegressionSuite.WindowsApp.exe.config** file under the RSAT installation folder (for example, **C:\\Program Files (x86)\\Regression Suite Automation Tool**), and change the value in the following element from **false** to **true**.</span></span>

    ```xml
    <add key="LogGeneration" value="false" />
    ```

<span data-ttu-id="57f61-176">När testfallen har körts kan du hitta loggfilerna under **C:\\användare\\\<användarnamn\>\\AppData\\roaming\\regressionTool\\generatorLogs**.</span><span class="sxs-lookup"><span data-stu-id="57f61-176">After the test cases are run, you can find the log files under **C:\\Users\\\<Username\>\\AppData\\Roaming\\regressionTool\\generatorLogs**.</span></span>

![GeneratorLogs-mappen](./media/use_rsa_tool_10.png)

> [!NOTE]
> <span data-ttu-id="57f61-178">Om det finns existerande testfall innan du ändrade värdet i .config-filen, kommer inga loggar att genereras för dessa tester förrän du har genererat nya testkörningsfiler.</span><span class="sxs-lookup"><span data-stu-id="57f61-178">If there were existing test cases before you changed the value in the .config file, logs won't be generated for those test cases until you generate new test execution files.</span></span>
> 
> ![Generera kommandot endast textexekveringar på menyn Ny](./media/use_rsa_tool_11.png)

### <a name="snapshot"></a><span data-ttu-id="57f61-180">Ögonblicksbild</span><span class="sxs-lookup"><span data-stu-id="57f61-180">Snapshot</span></span>

<span data-ttu-id="57f61-181">Den här funktionen tar skärmbilder av de steg som har utförts under uppgiftsregistreringen.</span><span class="sxs-lookup"><span data-stu-id="57f61-181">This feature takes screenshots of the steps that were performed during task recording.</span></span>

- <span data-ttu-id="57f61-182">Om du vill använda den här funktionen öppnar du filen **Microsoft.Dynamics.RegressionSuite.WindowsApp.exe.config** under RSAT-installationsmappen (t.ex. **C:\\programfiler (x86)\\Regression Suite Automation Tool**) och ändrar värdet i följande element från **falskt** till **sant**.</span><span class="sxs-lookup"><span data-stu-id="57f61-182">To use this feature, open the **Microsoft.Dynamics.RegressionSuite.WindowsApp.exe.config** file under the RSAT installation folder (for example, **C:\\Program Files (x86)\\Regression Suite Automation Tool**), and change the value of the following element from **false** to **true**.</span></span>

    ```xml
    <add key="VerboseSnapshotsEnabled" value="false" />
    ```

<span data-ttu-id="57f61-183">Under **C:\\användare\\\<användarnamn\>\\AppData\\Roaming\\regressionTool\\uppspelning**, skapas en separat mapp för varje testfall som körs.</span><span class="sxs-lookup"><span data-stu-id="57f61-183">Under **C:\\Users\\\<Username\>\\AppData\\Roaming\\regressionTool\\playback**, a separate folder is created for each test case that is run.</span></span>

![Mappen ögonblicksbild för ett testfall](./media/use_rsa_tool_12.png)

<span data-ttu-id="57f61-185">I var och en av dessa mappar kan du söka efter ögonblicksbilder av stegen som utfördes medan testerna kördes.</span><span class="sxs-lookup"><span data-stu-id="57f61-185">In each of these folders, you can find snapshots of the steps that were performed while the test cases were run.</span></span>

![Ögonblicksbildfiler](./media/use_rsa_tool_13.png)

## <a name="assignment"></a><span data-ttu-id="57f61-187">Tilldelning</span><span class="sxs-lookup"><span data-stu-id="57f61-187">Assignment</span></span>

### <a name="scenario"></a><span data-ttu-id="57f61-188">Scenario</span><span class="sxs-lookup"><span data-stu-id="57f61-188">Scenario</span></span>

1. <span data-ttu-id="57f61-189">Produktdesignern skapar en ny frisläppt produkt.</span><span class="sxs-lookup"><span data-stu-id="57f61-189">The product designer creates a new released product.</span></span>
2. <span data-ttu-id="57f61-190">Produktionschefen initierar en tillverkningsorder för att ta med lagernivån till två delar.</span><span class="sxs-lookup"><span data-stu-id="57f61-190">The production manager initiates a production order to bring the stock level to two pieces.</span></span>
3. <span data-ttu-id="57f61-191">Produktion startar och avslutar produktionsordern och verifierar att lagerkvantiteten är två enheter.</span><span class="sxs-lookup"><span data-stu-id="57f61-191">Manufacturing starts and ends the production order, and verifies that the on-hand quantity is two pieces.</span></span>
4. <span data-ttu-id="57f61-192">Försäljningsteamet får en på fyra enheter av den nya produkten.</span><span class="sxs-lookup"><span data-stu-id="57f61-192">The sales team receives an order for four pieces of the new product.</span></span> <span data-ttu-id="57f61-193">Därför uppdaterar försäljningsteamet nettokraven via den dynamiska planen.</span><span class="sxs-lookup"><span data-stu-id="57f61-193">Therefore, the sales team updates the net requirements via the dynamic plan.</span></span> <span data-ttu-id="57f61-194">Eftersom ingen ytterligare kapacitet finns tillgänglig, anges standardorderprincipen till köp istället för tillverka.</span><span class="sxs-lookup"><span data-stu-id="57f61-194">Because no additional capacity is available, the default order policy is set to "buy instead of make."</span></span> <span data-ttu-id="57f61-195">Därför kapas en planerad inköpsorder.</span><span class="sxs-lookup"><span data-stu-id="57f61-195">Therefore, a planned purchase order is created.</span></span>
5. <span data-ttu-id="57f61-196">Köparen lägger till en leverantör, signerar den planerade inköpsordern och bekräftar sedan inköpsordern.</span><span class="sxs-lookup"><span data-stu-id="57f61-196">The buyer adds a vendor, firms the planned purchase order, and then confirms the purchase order.</span></span>
6. <span data-ttu-id="57f61-197">När varorna som köpts in anländer till butiken söker butiksoperatören efter den relaterade inköpsordern och tar emot varorna.</span><span class="sxs-lookup"><span data-stu-id="57f61-197">When the goods that were purchased arrive at the store, the store operator searches the related purchase order and receives the goods.</span></span> <span data-ttu-id="57f61-198">Eftersom ordern nu är slutförd kan varor plockas och förpackas mot försäljningsordern.</span><span class="sxs-lookup"><span data-stu-id="57f61-198">Because the order is now completed, goods can be picked and packed against the sales order.</span></span>
7. <span data-ttu-id="57f61-199">Ekonomi bokför inköpsfakturan och försäljningsfakturan.</span><span class="sxs-lookup"><span data-stu-id="57f61-199">Finance posts the purchase invoice and sales invoice.</span></span>

<span data-ttu-id="57f61-200">Följande bild visar flödet för det här scenariot.</span><span class="sxs-lookup"><span data-stu-id="57f61-200">The following illustration shows the flow for this scenario.</span></span>

![Flöde för demoscenariot](./media/use_rsa_tool_14.png)

<span data-ttu-id="57f61-202">Följande bild visar affärsprocesser för det här scenariot i RSAT.</span><span class="sxs-lookup"><span data-stu-id="57f61-202">The following illustration shows the business processes for this scenario in RSAT.</span></span>

![Affärsprocesser för demoscenariot](./media/use_rsa_tool_15.png)

## <a name="strategy--key-learning"></a><span data-ttu-id="57f61-204">Strategi – viktiga utbildningsmaterial</span><span class="sxs-lookup"><span data-stu-id="57f61-204">Strategy – Key learning</span></span>

### <a name="data"></a><span data-ttu-id="57f61-205">Data</span><span class="sxs-lookup"><span data-stu-id="57f61-205">Data</span></span>

- <span data-ttu-id="57f61-206">Se till att du har representativa datavolymer (en kopia av produktions- och gyllene konfigurationsdata plus migrerade data).</span><span class="sxs-lookup"><span data-stu-id="57f61-206">Make sure that you have representative data volumes (a copy of production/golden configuration data plus migrated data).</span></span>
- <span data-ttu-id="57f61-207">När du genererar nya data via uppgiftsregistrering ska du skapa testnamn som inte är i konflikt med befintliga namn (du kan till exempel använda prefix som **RSATxxx**).</span><span class="sxs-lookup"><span data-stu-id="57f61-207">When you generate new data via Task recorder, create test names that won't conflict with existing names (for example, use a prefix such as **RSATxxx**).</span></span>
- <span data-ttu-id="57f61-208">Använd Azure tidpunktsåterställning för att köra om tester på andra miljöer än icke-nivå 1.</span><span class="sxs-lookup"><span data-stu-id="57f61-208">Use Azure Point-In-Time restore to rerun tests in non-Tier 1 environments.</span></span>
- <span data-ttu-id="57f61-209">Även om du kan använda Excel-funktionerna **SLUMPMÄSSIGA** och **NU** för att generera en unik kombination, är arbetsinsatsen betydligt hög.</span><span class="sxs-lookup"><span data-stu-id="57f61-209">Although you can use the **RANDOM** and **NOW** Excel functions to generate a unique combination, the effort is considerably high.</span></span> <span data-ttu-id="57f61-210">Här är ett exempel:</span><span class="sxs-lookup"><span data-stu-id="57f61-210">Here is an example.</span></span>

    ```Excel
    product = "AT" &TEXT(NOW(),"yyymmddhhmm")
    ```

### <a name="task-recorder"></a><span data-ttu-id="57f61-211">Uppgiftsregistrering</span><span class="sxs-lookup"><span data-stu-id="57f61-211">Task recorder</span></span>

- <span data-ttu-id="57f61-212">Definiera scenarier innan du startar inspelningen.</span><span class="sxs-lookup"><span data-stu-id="57f61-212">Define scenarios before you start recording.</span></span> <span data-ttu-id="57f61-213">Ett välhanterat projekt har fördefinierade testscenarier.</span><span class="sxs-lookup"><span data-stu-id="57f61-213">A well-managed project has predefined test scenarios.</span></span> <span data-ttu-id="57f61-214">Om du vill bygga ett testfall bör du överväga hur förutsägbara resultatet av testscenarierna är.</span><span class="sxs-lookup"><span data-stu-id="57f61-214">To build a test case, consider how predictable the outcome of those test scenarios is.</span></span>
- <span data-ttu-id="57f61-215">Dela upp inspelningar om de utförs av olika roller eller om det finns väntetid eller extern händelse före nästa steg.</span><span class="sxs-lookup"><span data-stu-id="57f61-215">Split recordings if they are performed by different roles, or if there is waiting time or an external event before the next step.</span></span>
- <span data-ttu-id="57f61-216">Undvik att markera värden i listor.</span><span class="sxs-lookup"><span data-stu-id="57f61-216">Avoid selecting values in lists.</span></span> <span data-ttu-id="57f61-217">Använd i stället textformat, t.ex. **FIFO**. **AudioRM** och **SiteWH**.</span><span class="sxs-lookup"><span data-stu-id="57f61-217">Instead, use text formats, such as **FIFO**, **AudioRM**, and **SiteWH**.</span></span> <span data-ttu-id="57f61-218">När du väljer i en lista registreras placeringen av värdet i listan, inte själva värdet.</span><span class="sxs-lookup"><span data-stu-id="57f61-218">When you select in a list, the position of the value in the list is recorded, not the value itself.</span></span> <span data-ttu-id="57f61-219">Om du lägger till objekt i listan kan placeringen av värdet ändras.</span><span class="sxs-lookup"><span data-stu-id="57f61-219">If items are added to that list, the position of the value can change.</span></span> <span data-ttu-id="57f61-220">Därför kommer din registrering att använda en annan parameter och resten av scenariot kan påverkas.</span><span class="sxs-lookup"><span data-stu-id="57f61-220">Therefore, your recording will use a different parameter, and the rest of the scenario might be affected.</span></span>
- <span data-ttu-id="57f61-221">Tänk på hur flera användare fungerar.</span><span class="sxs-lookup"><span data-stu-id="57f61-221">Think about multi-user behavior.</span></span> <span data-ttu-id="57f61-222">Antag till exempel inte att den nya försäljningsordern alltid väljs automatiskt.</span><span class="sxs-lookup"><span data-stu-id="57f61-222">For example, don't assume that your newly created sales order will always be automatically selected.</span></span> <span data-ttu-id="57f61-223">I stället ska du alltid använda filtret för att hitta rätt ordning.</span><span class="sxs-lookup"><span data-stu-id="57f61-223">Instead, always use the filter to find the correct order.</span></span>
- <span data-ttu-id="57f61-224">Använd kopieringsfunktionen i uppgiftsinspelning om du vill spara namnet på en nyskapad produkt så att den kan användas i kedjade testfall.</span><span class="sxs-lookup"><span data-stu-id="57f61-224">Use the Copy function in Task recorder to save the name of a newly created product so it can be used in chained test cases.</span></span>
- <span data-ttu-id="57f61-225">Använd funktionen validera i uppgiftsregistrering om du vill ställa in kontrollpunkter som verifierar att stegen har körts på rätt sätt.</span><span class="sxs-lookup"><span data-stu-id="57f61-225">Use the Validate function in Task recorder to set checkpoints that verify that steps have been run correctly.</span></span>

### <a name="rsat"></a><span data-ttu-id="57f61-226">RSAT</span><span class="sxs-lookup"><span data-stu-id="57f61-226">RSAT</span></span>

- <span data-ttu-id="57f61-227">Om du vill köra testet i ett annat företag kan du ändra företaget på fliken **allmänt** i Excel-parameterfilen.</span><span class="sxs-lookup"><span data-stu-id="57f61-227">To run the test in another company, you can change the company on the **General** tab of the Excel parameter file.</span></span> <span data-ttu-id="57f61-228">Kontrollera att inställningar och data är tillgängliga i det valda företaget.</span><span class="sxs-lookup"><span data-stu-id="57f61-228">Make sure that settings and data are available in the newly selected company.</span></span>
- <span data-ttu-id="57f61-229">Du kan ändra testanvändaren på fliken **allmänt** i Excel-parameterfilen.</span><span class="sxs-lookup"><span data-stu-id="57f61-229">You can change the test user on the **General** tab of the Excel parameter file.</span></span> <span data-ttu-id="57f61-230">Ange e-post-ID för den användare som ska köra test fallet.</span><span class="sxs-lookup"><span data-stu-id="57f61-230">Specify the email ID of the user who will run the test case.</span></span> <span data-ttu-id="57f61-231">På så sätt kan testfallet köras med hjälp av den angivna användarens säkerhetsbehörigheter.</span><span class="sxs-lookup"><span data-stu-id="57f61-231">In this way, the test case can be run by using the security permissions of the specified user.</span></span>
- <span data-ttu-id="57f61-232">Om du vill vänta innan testet påbörjas kan du definiera en paus på fliken **allmänt** i Excel-parameterfilen.</span><span class="sxs-lookup"><span data-stu-id="57f61-232">To wait before the test is started, you can define a pause on the **General** tab of the Excel parameter file.</span></span> <span data-ttu-id="57f61-233">Denna paus kan användas i ett batchjobb (t.ex. om ett arbetsflöde måste köras innan nästa steg kan utföras.)</span><span class="sxs-lookup"><span data-stu-id="57f61-233">This pause can be used in a batch job (for example, if a workflow must be run before the next step can be performed.)</span></span>

## <a name="advanced-scripting"></a><span data-ttu-id="57f61-234">Avancerade skript</span><span class="sxs-lookup"><span data-stu-id="57f61-234">Advanced scripting</span></span>

### <a name="cli"></a><span data-ttu-id="57f61-235">CLI</span><span class="sxs-lookup"><span data-stu-id="57f61-235">CLI</span></span>

<span data-ttu-id="57f61-236">RSAT kan anropas från fönstret **kommandotolk** eller **PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="57f61-236">RSAT can be called from a **Command Prompt** or **PowerShell** window.</span></span>

> [!NOTE]
> <span data-ttu-id="57f61-237">Kontrollera att miljövariabeln **TestRoot** anges till RSAT installationens sökväg.</span><span class="sxs-lookup"><span data-stu-id="57f61-237">Verify that the **TestRoot** environment variable is set to the RSAT installation path.</span></span> <span data-ttu-id="57f61-238">(I Microsoft Windows, öppna **kontrollkontroll**, välj **Systemoch säkerhet \> System \> Avancerade systeminställningar** och välj sedan **miljövariabler**.)</span><span class="sxs-lookup"><span data-stu-id="57f61-238">(In Microsoft Windows, open **Control Panel**, select **System and Security \> System \> Advanced system settings**, and then select **Environment Variables**.)</span></span>

1. <span data-ttu-id="57f61-239">Öppna ett **kommandotolk** eller **PowerShell** som admin.</span><span class="sxs-lookup"><span data-stu-id="57f61-239">Open a **Command Prompt** or **PowerShell** window as an admin.</span></span>
2. <span data-ttu-id="57f61-240">Navigera till installationskatalogen för RSAT.</span><span class="sxs-lookup"><span data-stu-id="57f61-240">Navigate to the RSAT installation directory.</span></span>

    ```Console
    cd "c:\Program Files (x86)\Regression Suite Automation Tool\"
    ```

3. <span data-ttu-id="57f61-241">Lista alla kommandon.</span><span class="sxs-lookup"><span data-stu-id="57f61-241">List all commands.</span></span>

    ```Console
    C:\Program Files (x86)\Regression Suite Automation Tool>Microsoft.Dynamics.RegressionSuite.ConsoleApp.exe help

    Usage:
        Microsoft.Dynamics.RegressionSuite.ConsoleApp.exe command
        or
        Microsoft.Dynamics.RegressionSuite.ConsoleApp.exe /settings "C:\Path to\file.settings" command

    Available commands:
        ?
        about
        cls
        download
        edit
        generate
        generatederived
        generatetestonly
        generatetestsuite
        help
        list
        listtestplans
        listtestsuite
        listtestsuitenames
        playback
        playbackbyid
        playbackmany
        playbacksuite
        quit
        upload
        uploadrecording
        usage
    ```

#### <a name=""></a><span data-ttu-id="57f61-242">?</span><span class="sxs-lookup"><span data-stu-id="57f61-242">?</span></span> 
<span data-ttu-id="57f61-243">Visar hjälp om alla tillgängliga kommandon och deras parametrar.</span><span class="sxs-lookup"><span data-stu-id="57f61-243">Shows help about all available commands and their parameters.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``?``**``[command]``

##### <a name="optional-parameters"></a><span data-ttu-id="57f61-244">Valfria parametrar</span><span class="sxs-lookup"><span data-stu-id="57f61-244">Optional parameters</span></span>

**``command``**


<span data-ttu-id="57f61-245">Där ``[command]`` är ett av de kommandon som anges nedan.</span><span class="sxs-lookup"><span data-stu-id="57f61-245">Where ``[command]`` is one of the commands specified below.</span></span>


#### <a name="about"></a><span data-ttu-id="57f61-246">om</span><span class="sxs-lookup"><span data-stu-id="57f61-246">about</span></span>
<span data-ttu-id="57f61-247">Visar den aktuella versionen.</span><span class="sxs-lookup"><span data-stu-id="57f61-247">Displays the current version.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``about``**

#### <a name="cls"></a><span data-ttu-id="57f61-248">cls</span><span class="sxs-lookup"><span data-stu-id="57f61-248">cls</span></span>
<span data-ttu-id="57f61-249">Rensar skärmen.</span><span class="sxs-lookup"><span data-stu-id="57f61-249">Clears the screen.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``cls``**


#### <a name="download"></a><span data-ttu-id="57f61-250">hämta</span><span class="sxs-lookup"><span data-stu-id="57f61-250">download</span></span>
<span data-ttu-id="57f61-251">Hämtar bifogade filer för det angivna testfallet till utdatafilen.</span><span class="sxs-lookup"><span data-stu-id="57f61-251">Downloads attachments for the specified test case to the output directory.</span></span> <span data-ttu-id="57f61-252">Du kan använda ``list`` kommandot för att hämta alla tillgängliga testärenden.</span><span class="sxs-lookup"><span data-stu-id="57f61-252">You can use the ``list`` command to get all available test cases.</span></span> <span data-ttu-id="57f61-253">Använd valfritt värde från den första kolumnen som en **test_case_id** parameter.</span><span class="sxs-lookup"><span data-stu-id="57f61-253">Use any value from the first column as a **test_case_id** parameter.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``download``**``[test_case_id] [output_dir]``

##### <a name="required-parameters"></a><span data-ttu-id="57f61-254">Obligatoriska parametrar</span><span class="sxs-lookup"><span data-stu-id="57f61-254">Required parameters</span></span>
<span data-ttu-id="57f61-255">**``test_case_id``** Representerar ID för testärende.</span><span class="sxs-lookup"><span data-stu-id="57f61-255">**``test_case_id``** Represents the test case ID.</span></span>  
<span data-ttu-id="57f61-256">**``output_dir``** Representerar katalogen för utdata.</span><span class="sxs-lookup"><span data-stu-id="57f61-256">**``output_dir``** Represents the output directory.</span></span> <span data-ttu-id="57f61-257">Katalogen måste finnas.</span><span class="sxs-lookup"><span data-stu-id="57f61-257">The directory must exist.</span></span>

##### <a name="examples"></a><span data-ttu-id="57f61-258">Exempel</span><span class="sxs-lookup"><span data-stu-id="57f61-258">Examples</span></span>

``download 123 c:\temp\rsat``   
``download 765 c:\rsat\last``


#### <a name="edit"></a><span data-ttu-id="57f61-259">redigera</span><span class="sxs-lookup"><span data-stu-id="57f61-259">edit</span></span>
<span data-ttu-id="57f61-260">Gör att du kan öppna parameter filen i Excel-programmet och redigera den.</span><span class="sxs-lookup"><span data-stu-id="57f61-260">Allows you to open parameters file in Excel program and edit it.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``edit``**``[excel_file]``

##### <a name="required-parameters"></a><span data-ttu-id="57f61-261">Obligatoriska parametrar</span><span class="sxs-lookup"><span data-stu-id="57f61-261">Required parameters</span></span>
<span data-ttu-id="57f61-262">**``excel_file``** Måste innehålla en fullständig sökväg till en befintlig Excel-fil.</span><span class="sxs-lookup"><span data-stu-id="57f61-262">**``excel_file``** Must contain a full path to an existing Excel file.</span></span>

##### <a name="examples"></a><span data-ttu-id="57f61-263">Exempel</span><span class="sxs-lookup"><span data-stu-id="57f61-263">Examples</span></span>
``edit c:\RSAT\TestCase_123_Base.xlsx``  
``edit e:\temp\TestCase_456_Base.xlsx``


#### <a name="generate"></a><span data-ttu-id="57f61-264">skapa</span><span class="sxs-lookup"><span data-stu-id="57f61-264">generate</span></span>
<span data-ttu-id="57f61-265">Skapar test körnings- och parametervärden för det angivna testärendet i utdatapanelen.</span><span class="sxs-lookup"><span data-stu-id="57f61-265">Generates test execution and parameter files for the specified test case in the output directory.</span></span>
<span data-ttu-id="57f61-266">Du kan använda ``list`` kommandot för att hämta alla tillgängliga testärenden.</span><span class="sxs-lookup"><span data-stu-id="57f61-266">You can use the ``list`` command to get all available test cases.</span></span> <span data-ttu-id="57f61-267">Använd valfritt värde från den första kolumnen som en **test_case_id** parameter.</span><span class="sxs-lookup"><span data-stu-id="57f61-267">Use any value from the first column as a **test_case_id** parameter.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``generate``**``[test_case_id] [output_dir]``

##### <a name="required-parameters"></a><span data-ttu-id="57f61-268">Obligatoriska parametrar</span><span class="sxs-lookup"><span data-stu-id="57f61-268">Required parameters</span></span>
<span data-ttu-id="57f61-269">**``test_case_id``** Representerar ID för testärende.</span><span class="sxs-lookup"><span data-stu-id="57f61-269">**``test_case_id``** Represents the test case ID.</span></span>  
<span data-ttu-id="57f61-270">**``output_dir``** Representerar katalogen för utdata.</span><span class="sxs-lookup"><span data-stu-id="57f61-270">**``output_dir``** Represents the output directory.</span></span> <span data-ttu-id="57f61-271">Katalogen måste finnas.</span><span class="sxs-lookup"><span data-stu-id="57f61-271">The directory must exist.</span></span>

##### <a name="examples"></a><span data-ttu-id="57f61-272">Exempel</span><span class="sxs-lookup"><span data-stu-id="57f61-272">Examples</span></span>
``generate 123 c:\temp\rsat``  
``generate 765 c:\rsat\last``


#### <a name="generatederived"></a><span data-ttu-id="57f61-273">generatederived</span><span class="sxs-lookup"><span data-stu-id="57f61-273">generatederived</span></span>
<span data-ttu-id="57f61-274">Genererar ett nytt testärende som härletts från det angivna testärendet.</span><span class="sxs-lookup"><span data-stu-id="57f61-274">Generates a new test case, derived from the provided test case.</span></span> <span data-ttu-id="57f61-275">Du kan använda ``list`` kommandot för att hämta alla tillgängliga testärenden.</span><span class="sxs-lookup"><span data-stu-id="57f61-275">You can use the ``list`` command to get all available test cases.</span></span> <span data-ttu-id="57f61-276">Använd valfritt värde från den första kolumnen som en **test_case_id** parameter.</span><span class="sxs-lookup"><span data-stu-id="57f61-276">Use any value from the first column as a **test_case_id** parameter.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``generatederived``**``[parent_test_case_id] [test_plan_id] [test_suite_id]``

##### <a name="required-parameters"></a><span data-ttu-id="57f61-277">Obligatoriska parametrar</span><span class="sxs-lookup"><span data-stu-id="57f61-277">Required parameters</span></span>
<span data-ttu-id="57f61-278">**``parent_test_case_id``** Representerar överordnat ID för testärende.</span><span class="sxs-lookup"><span data-stu-id="57f61-278">**``parent_test_case_id``** Represents the parent test case ID.</span></span>  
<span data-ttu-id="57f61-279">**``test_plan_id``** Representerar ID för testplan.</span><span class="sxs-lookup"><span data-stu-id="57f61-279">**``test_plan_id``** Represents the test plan ID.</span></span>  
<span data-ttu-id="57f61-280">**``test_suite_id``** Representerar ID för testpaketet.</span><span class="sxs-lookup"><span data-stu-id="57f61-280">**``test_suite_id``** Represents the test suite ID.</span></span>

##### <a name="examples"></a><span data-ttu-id="57f61-281">Exempel</span><span class="sxs-lookup"><span data-stu-id="57f61-281">Examples</span></span>
``generatederived 123 8901 678``


#### <a name="generatetestonly"></a><span data-ttu-id="57f61-282">generatetestonly</span><span class="sxs-lookup"><span data-stu-id="57f61-282">generatetestonly</span></span>
<span data-ttu-id="57f61-283">Skapar endast test körningsfil för det angivna testärendet i utdatapanelen.</span><span class="sxs-lookup"><span data-stu-id="57f61-283">Generates only test execution file for the specified test case in the output directory.</span></span> <span data-ttu-id="57f61-284">Du kan använda ``list`` kommandot för att hämta alla tillgängliga testärenden.</span><span class="sxs-lookup"><span data-stu-id="57f61-284">You can use the ``list`` command to get all available test cases.</span></span> <span data-ttu-id="57f61-285">Använd valfritt värde från den första kolumnen som en **test_case_id** parameter.</span><span class="sxs-lookup"><span data-stu-id="57f61-285">Use any value from the first column as a **test_case_id** parameter.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``generatetestonly``**``[test_case_id] [output_dir]``

##### <a name="required-parameters"></a><span data-ttu-id="57f61-286">Obligatoriska parametrar</span><span class="sxs-lookup"><span data-stu-id="57f61-286">Required parameters</span></span>
<span data-ttu-id="57f61-287">**``test_case_id``** Representerar ID för testärende.</span><span class="sxs-lookup"><span data-stu-id="57f61-287">**``test_case_id``** Represents the test case ID.</span></span>  
<span data-ttu-id="57f61-288">**``output_dir``** Representerar katalogen för utdata.</span><span class="sxs-lookup"><span data-stu-id="57f61-288">**``output_dir``** Represents the output directory.</span></span> <span data-ttu-id="57f61-289">Katalogen måste finnas.</span><span class="sxs-lookup"><span data-stu-id="57f61-289">The directory must exist.</span></span>

##### <a name="examples"></a><span data-ttu-id="57f61-290">Exempel</span><span class="sxs-lookup"><span data-stu-id="57f61-290">Examples</span></span>
``generatetestonly 123 c:\temp\rsat``  
``generatetestonly 765 c:\rsat\last``


#### <a name="generatetestsuite"></a><span data-ttu-id="57f61-291">generatetestsuite</span><span class="sxs-lookup"><span data-stu-id="57f61-291">generatetestsuite</span></span>
<span data-ttu-id="57f61-292">Genererar alla testärenden för det angivna paketet i utdatakatalogen.</span><span class="sxs-lookup"><span data-stu-id="57f61-292">Generates all test cases for the specified suite in the output directory.</span></span>
<span data-ttu-id="57f61-293">Du kan använda ``listtestsuitenames`` kommandot för att hämta alla tillgängliga testpaket.</span><span class="sxs-lookup"><span data-stu-id="57f61-293">You can use ``listtestsuitenames`` command to get all available test suits.</span></span> <span data-ttu-id="57f61-294">Använd valfritt värde kolumnen som en **test_suite_name** parameter.</span><span class="sxs-lookup"><span data-stu-id="57f61-294">Use any value from the column as a **test_suite_name** parameter.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``generatetestsuite``**``[test_suite_name] [output_dir]``

##### <a name="required-parameters"></a><span data-ttu-id="57f61-295">Obligatoriska parametrar</span><span class="sxs-lookup"><span data-stu-id="57f61-295">Required parameters</span></span>
<span data-ttu-id="57f61-296">**``test_suite_name``** Representerar testpaketets namn.</span><span class="sxs-lookup"><span data-stu-id="57f61-296">**``test_suite_name``** Represents the test suite name.</span></span>  
<span data-ttu-id="57f61-297">**``output_dir``** Representerar katalogen för utdata.</span><span class="sxs-lookup"><span data-stu-id="57f61-297">**``output_dir``** Represents the output directory.</span></span> <span data-ttu-id="57f61-298">Katalogen måste finnas.</span><span class="sxs-lookup"><span data-stu-id="57f61-298">The directory must exist.</span></span>

##### <a name="examples"></a><span data-ttu-id="57f61-299">Exempel</span><span class="sxs-lookup"><span data-stu-id="57f61-299">Examples</span></span>
``generatetestsuite Tests c:\temp\rsat``   
``generatetestsuite Purchase c:\rsat\last``


#### <a name="help"></a><span data-ttu-id="57f61-300">hjälp</span><span class="sxs-lookup"><span data-stu-id="57f61-300">help</span></span>
<span data-ttu-id="57f61-301">Är identisk med [?](####?)</span><span class="sxs-lookup"><span data-stu-id="57f61-301">Identical to the [?](####?)</span></span> <span data-ttu-id="57f61-302">kommando</span><span class="sxs-lookup"><span data-stu-id="57f61-302">command</span></span>


#### <a name="list"></a><span data-ttu-id="57f61-303">listan</span><span class="sxs-lookup"><span data-stu-id="57f61-303">list</span></span>
<span data-ttu-id="57f61-304">Visar alla tillgängliga testärenden.</span><span class="sxs-lookup"><span data-stu-id="57f61-304">Lists all available test cases.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``list``**


#### <a name="listtestplans"></a><span data-ttu-id="57f61-305">listtestplans</span><span class="sxs-lookup"><span data-stu-id="57f61-305">listtestplans</span></span>
<span data-ttu-id="57f61-306">Visar alla tillgängliga testplaner.</span><span class="sxs-lookup"><span data-stu-id="57f61-306">Lists all available test plans.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``listtestplans``**


#### <a name="listtestsuite"></a><span data-ttu-id="57f61-307">listtestsuite</span><span class="sxs-lookup"><span data-stu-id="57f61-307">listtestsuite</span></span>
<span data-ttu-id="57f61-308">Visar testärenden för angivet testpaket.</span><span class="sxs-lookup"><span data-stu-id="57f61-308">Lists test cases for the specified test suite.</span></span> <span data-ttu-id="57f61-309">Du kan använda ``listtestsuitenames`` kommandot för att hämta alla tillgängliga testpaket.</span><span class="sxs-lookup"><span data-stu-id="57f61-309">You can use ``listtestsuitenames`` command to get all available test suites.</span></span> <span data-ttu-id="57f61-310">Använd valfritt värde från första kolumnen som en **suite_name** parameter.</span><span class="sxs-lookup"><span data-stu-id="57f61-310">Use any value from first column as **suite_name** parameter.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``listtestsuite``**``[suite_name]``

##### <a name="required-parameters"></a><span data-ttu-id="57f61-311">Obligatoriska parametrar</span><span class="sxs-lookup"><span data-stu-id="57f61-311">Required parameters</span></span>
<span data-ttu-id="57f61-312">**``suite_name``** Namn på önskat paket.</span><span class="sxs-lookup"><span data-stu-id="57f61-312">**``suite_name``** Name of the desired suite.</span></span>

##### <a name="examples"></a><span data-ttu-id="57f61-313">Exempel</span><span class="sxs-lookup"><span data-stu-id="57f61-313">Examples</span></span>
``listtestsuite "sample suite name"``  
``listtestsuite NameOfTheSuite``


#### <a name="listtestsuitenames"></a><span data-ttu-id="57f61-314">listtestsuitenames</span><span class="sxs-lookup"><span data-stu-id="57f61-314">listtestsuitenames</span></span>
<span data-ttu-id="57f61-315">Visar alla tillgängliga testpaket.</span><span class="sxs-lookup"><span data-stu-id="57f61-315">Lists all available test suites.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``listtestsuitenames``**


#### <a name="playback"></a><span data-ttu-id="57f61-316">playback</span><span class="sxs-lookup"><span data-stu-id="57f61-316">playback</span></span>
<span data-ttu-id="57f61-317">Spelar upp ett testärende med hjälp av en Excel-fil.</span><span class="sxs-lookup"><span data-stu-id="57f61-317">Plays back a test case using an Excel file.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``playback``**``[excel_file]``

##### <a name="required-parameters"></a><span data-ttu-id="57f61-318">Obligatoriska parametrar</span><span class="sxs-lookup"><span data-stu-id="57f61-318">Required parameters</span></span>
<span data-ttu-id="57f61-319">**``excel_file``** En fullständig sökväg till Excel-filen.</span><span class="sxs-lookup"><span data-stu-id="57f61-319">**``excel_file``** A full path to the Excel file.</span></span> <span data-ttu-id="57f61-320">Filen måste finnas.</span><span class="sxs-lookup"><span data-stu-id="57f61-320">File must exist.</span></span> 

##### <a name="examples"></a><span data-ttu-id="57f61-321">Exempel</span><span class="sxs-lookup"><span data-stu-id="57f61-321">Examples</span></span>
``
playback c:\RSAT\TestCaseParameters\sample1.xlsx
playback e:\temp\test.xlsx
``


#### <a name="playbackbyid"></a><span data-ttu-id="57f61-322">playbackbyid</span><span class="sxs-lookup"><span data-stu-id="57f61-322">playbackbyid</span></span>
<span data-ttu-id="57f61-323">Spelar upp flera testärenden samtidigt.</span><span class="sxs-lookup"><span data-stu-id="57f61-323">Plays back multiple test cases at once.</span></span>
<span data-ttu-id="57f61-324">Du kan använda ``list`` kommandot för att hämta alla tillgängliga testärenden.</span><span class="sxs-lookup"><span data-stu-id="57f61-324">You can use the ``list`` command to get all available test cases.</span></span> <span data-ttu-id="57f61-325">Använd valfritt värde från den första kolumnen som en **test_case_id** parameter.</span><span class="sxs-lookup"><span data-stu-id="57f61-325">Use any value from the first column as a **test_case_id** parameter.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``playbackbyid``**``[test_case_id1] [test_case_id2] ... [test_case_idN]``

##### <a name="required-parameters"></a><span data-ttu-id="57f61-326">Obligatoriska parametrar</span><span class="sxs-lookup"><span data-stu-id="57f61-326">Required parameters</span></span>
<span data-ttu-id="57f61-327">**``test_case_id1``** ID för befintliga testärenden.</span><span class="sxs-lookup"><span data-stu-id="57f61-327">**``test_case_id1``** ID of exisiting test case.</span></span>  
<span data-ttu-id="57f61-328">**``test_case_id2``** ID för befintliga testärenden.</span><span class="sxs-lookup"><span data-stu-id="57f61-328">**``test_case_id2``** ID of exisiting test case.</span></span>  
<span data-ttu-id="57f61-329">**``test_case_idN``** ID för befintliga testärenden.</span><span class="sxs-lookup"><span data-stu-id="57f61-329">**``test_case_idN``** ID of exisiting test case.</span></span>  

##### <a name="examples"></a><span data-ttu-id="57f61-330">Exempel</span><span class="sxs-lookup"><span data-stu-id="57f61-330">Examples</span></span>
``playbackbyid 878``  
``playbackbyid 2345 667 135``


#### <a name="playbackmany"></a><span data-ttu-id="57f61-331">playbackmany</span><span class="sxs-lookup"><span data-stu-id="57f61-331">playbackmany</span></span>
<span data-ttu-id="57f61-332">Spelar upp många testärenden samtidigt, med Excel-filer.</span><span class="sxs-lookup"><span data-stu-id="57f61-332">Plays back many test cases at once, using Excel files.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``playbackmany``**``[excel_file1] [excel_file2] ... [excel_fileN]``

##### <a name="required-parameters"></a><span data-ttu-id="57f61-333">Obligatoriska parametrar</span><span class="sxs-lookup"><span data-stu-id="57f61-333">Required parameters</span></span>
<span data-ttu-id="57f61-334">**``excel_file1``** Fullständig sökväg till Excel-filen.</span><span class="sxs-lookup"><span data-stu-id="57f61-334">**``excel_file1``** Full path to the Excel file.</span></span> <span data-ttu-id="57f61-335">Filen måste finnas.</span><span class="sxs-lookup"><span data-stu-id="57f61-335">File must exist.</span></span>  
<span data-ttu-id="57f61-336">**``excel_file2``** Fullständig sökväg till Excel-filen.</span><span class="sxs-lookup"><span data-stu-id="57f61-336">**``excel_file2``** Full path to the Excel file.</span></span> <span data-ttu-id="57f61-337">Filen måste finnas.</span><span class="sxs-lookup"><span data-stu-id="57f61-337">File must exist.</span></span>  
<span data-ttu-id="57f61-338">**``excel_fileN``** Fullständig sökväg till Excel-filen.</span><span class="sxs-lookup"><span data-stu-id="57f61-338">**``excel_fileN``** Full path to the Excel file.</span></span> <span data-ttu-id="57f61-339">Filen måste finnas.</span><span class="sxs-lookup"><span data-stu-id="57f61-339">File must exist.</span></span>  

##### <a name="examples"></a><span data-ttu-id="57f61-340">Exempel</span><span class="sxs-lookup"><span data-stu-id="57f61-340">Examples</span></span>
``playbackmany c:\RSAT\TestCaseParameters\param1.xlsx``  
``playbackmany e:\temp\test.xlsx f:\rsat\sample1.xlsx c:\RSAT\sample2.xlsx``


#### <a name="playbacksuite"></a><span data-ttu-id="57f61-341">playbacksuite</span><span class="sxs-lookup"><span data-stu-id="57f61-341">playbacksuite</span></span>
<span data-ttu-id="57f61-342">Spelar upp alla testärende från angiven testpaket.</span><span class="sxs-lookup"><span data-stu-id="57f61-342">Plays back all test cases from the specified test suite.</span></span> <span data-ttu-id="57f61-343">Du kan använda ``listtestsuitenames`` kommandot för att hämta alla tillgängliga testpaket.</span><span class="sxs-lookup"><span data-stu-id="57f61-343">You can use ``listtestsuitenames`` command to get all available test suites.</span></span> <span data-ttu-id="57f61-344">Använd valfritt värde från första kolumnen som en **suite_name** parameter.</span><span class="sxs-lookup"><span data-stu-id="57f61-344">Use any value from first column as **suite_name** parameter.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``playbacksuite``**``[suite_name]``

##### <a name="required-parameters"></a><span data-ttu-id="57f61-345">Obligatoriska parametrar</span><span class="sxs-lookup"><span data-stu-id="57f61-345">Required parameters</span></span>
<span data-ttu-id="57f61-346">**``suite_name``** Namn på önskat paket.</span><span class="sxs-lookup"><span data-stu-id="57f61-346">**``suite_name``** Name of the desired suite.</span></span>

##### <a name="examples"></a><span data-ttu-id="57f61-347">Exempel</span><span class="sxs-lookup"><span data-stu-id="57f61-347">Examples</span></span>
``playbacksuite suiteName``  
``playbacksuite sample_suite``


#### <a name="quit"></a><span data-ttu-id="57f61-348">avsluta</span><span class="sxs-lookup"><span data-stu-id="57f61-348">quit</span></span>
<span data-ttu-id="57f61-349">Stänger programmet.</span><span class="sxs-lookup"><span data-stu-id="57f61-349">Closes the  application.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``quit``**


#### <a name="upload"></a><span data-ttu-id="57f61-350">överför</span><span class="sxs-lookup"><span data-stu-id="57f61-350">upload</span></span>
<span data-ttu-id="57f61-351">Överför alla filer som hör till de angivna testpaketen eller testärenden.</span><span class="sxs-lookup"><span data-stu-id="57f61-351">Uploads all files belonging to the specified test suite or test cases.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``upload``**``[suite_name] [testcase_id]``

#### <a name="required-parameters"></a><span data-ttu-id="57f61-352">Obligatoriska parametrar</span><span class="sxs-lookup"><span data-stu-id="57f61-352">Required parameters</span></span>
<span data-ttu-id="57f61-353">**``suite_name``** Alla filer som hör till de angivna testpaketen kommer att laddas upp.</span><span class="sxs-lookup"><span data-stu-id="57f61-353">**``suite_name``** All files belonging to the specified test suite will be uploaded.</span></span>
<span data-ttu-id="57f61-354">**``testcase_id``** Alla filer hör till de angivna testärenden kommer att laddas upp.</span><span class="sxs-lookup"><span data-stu-id="57f61-354">**``testcase_id``** All files beloning to the specified test case(s) will be uploaded.</span></span>

##### <a name="examples"></a><span data-ttu-id="57f61-355">Exempel</span><span class="sxs-lookup"><span data-stu-id="57f61-355">Examples</span></span>
``upload sample_suite``  
``upload 123``  
``upload 123 456``


#### <a name="uploadrecording"></a><span data-ttu-id="57f61-356">uploadrecording</span><span class="sxs-lookup"><span data-stu-id="57f61-356">uploadrecording</span></span>
<span data-ttu-id="57f61-357">Överför endast registreringsfil som hör till de angivna testärenden.</span><span class="sxs-lookup"><span data-stu-id="57f61-357">Uploads only recording file belonging to the specified test cases.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``uploadrecording``**``[testcase_id]``

##### <a name="required-parameters"></a><span data-ttu-id="57f61-358">Obligatoriska parametrar</span><span class="sxs-lookup"><span data-stu-id="57f61-358">Required parameters</span></span>
<span data-ttu-id="57f61-359">**``testcase_id``** Registreringsfil som hör till de angivna testärenden kommer att överföras.</span><span class="sxs-lookup"><span data-stu-id="57f61-359">**``testcase_id``** Recording file belonging to the specified test cases will be uploaded.</span></span>

##### <a name="examples"></a><span data-ttu-id="57f61-360">Exempel</span><span class="sxs-lookup"><span data-stu-id="57f61-360">Examples</span></span>
``uploadrecording 123``  
``uploadrecording 123 456``


#### <a name="usage"></a><span data-ttu-id="57f61-361">användning</span><span class="sxs-lookup"><span data-stu-id="57f61-361">usage</span></span>
<span data-ttu-id="57f61-362">Visar två sätt att anropa det här programmet: ett som använder en standardinställningsfil, ett annat som en inställningsfil.</span><span class="sxs-lookup"><span data-stu-id="57f61-362">Shows two ways to invoke this application: one using a default setting file, another one providing a setting file.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``usage``**


### <a name="windows-powershell-examples"></a><span data-ttu-id="57f61-363">Windows PowerShell-exempel</span><span class="sxs-lookup"><span data-stu-id="57f61-363">Windows PowerShell examples</span></span>

#### <a name="run-a-test-case-in-a-loop"></a><span data-ttu-id="57f61-364">Kör ett testfall i en slinga</span><span class="sxs-lookup"><span data-stu-id="57f61-364">Run a test case in a loop</span></span>

<span data-ttu-id="57f61-365">Du har ett testskript som skapar en ny kund.</span><span class="sxs-lookup"><span data-stu-id="57f61-365">You have a test script that creates a new customer.</span></span> <span data-ttu-id="57f61-366">Via skript kan det här testfallet köras i en slinga genom att göra slumpmässiga följandande data innan varje iteration körs:</span><span class="sxs-lookup"><span data-stu-id="57f61-366">Via scripting, this test case can be run in a loop by randomizing the following data before each iteration is run:</span></span>

- <span data-ttu-id="57f61-367">Kund-ID</span><span class="sxs-lookup"><span data-stu-id="57f61-367">Customer ID</span></span>
- <span data-ttu-id="57f61-368">Kundnamn</span><span class="sxs-lookup"><span data-stu-id="57f61-368">Customer name</span></span>
- <span data-ttu-id="57f61-369">Adress till kund</span><span class="sxs-lookup"><span data-stu-id="57f61-369">Customer address</span></span>

<span data-ttu-id="57f61-370">Kund-ID:t anges i formatet *ATCUS\<nummer\>*, där \<nummer\> är ett värde mellan **000000001** och **999999999**.</span><span class="sxs-lookup"><span data-stu-id="57f61-370">The customer ID will be in the format *ATCUS\<number\>*, where \<number\> is a value between **000000001** and **999999999**.</span></span>

<span data-ttu-id="57f61-371">I följande exempel används en parameter, **Start**för att definiera det första numret som används.</span><span class="sxs-lookup"><span data-stu-id="57f61-371">The following example uses one parameter, **start**, to define the first number that is used.</span></span> <span data-ttu-id="57f61-372">Det använder en andra parameter, **nr**, för att definiera antalet kunder som måste skapas.</span><span class="sxs-lookup"><span data-stu-id="57f61-372">Is uses a second parameter, **nr**, to define the number of customers that must be created.</span></span> <span data-ttu-id="57f61-373">För varje upprepning ändras parametrarna i Excel-parameterfil med hjälp av en UpdateCustomer-funktion.</span><span class="sxs-lookup"><span data-stu-id="57f61-373">For each iteration, the parameters in the Excel parameter file are changed by using an UpdateCustomer function.</span></span> <span data-ttu-id="57f61-374">Då anropas kommando raden för RSAT i en RunTestCase-funktion.</span><span class="sxs-lookup"><span data-stu-id="57f61-374">Then the RSAT command line is called in a RunTestCase function.</span></span>

<span data-ttu-id="57f61-375">Öppna Microsoft Windows PowerShell ISE (Integrated Scripting Environment) i administrationsläge och klistra in följande kod i fönstret med namnet **Untitled1.ps1**.</span><span class="sxs-lookup"><span data-stu-id="57f61-375">Open Microsoft Windows PowerShell Integrated Scripting Environment (ISE) in admin mode, and paste the following code into the window that is named **Untitled1.ps1**.</span></span>

```powershell
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

#### <a name="run-a-script-that-depends-on-data-in-microsoft-dynamics-365"></a><span data-ttu-id="57f61-376">Köra ett skript som är beroende av data i Microsoft Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="57f61-376">Run a script that depends on data in Microsoft Dynamics 365</span></span>

<span data-ttu-id="57f61-377">I följande exempel används ett OData-anrop (Open Data Protocol) för att hitta orderstatusen för en inköpsorder.</span><span class="sxs-lookup"><span data-stu-id="57f61-377">The following example uses an Open Data Protocol (OData) call to find the order status of a purchase order.</span></span> <span data-ttu-id="57f61-378">Om statusvärdet inte har **fakturerats** kan du t.ex. anropa ett testfall för RSAT som bokför fakturan.</span><span class="sxs-lookup"><span data-stu-id="57f61-378">If the status isn't **invoiced**, you can, for example, call an RSAT test case that posts the invoice.</span></span>

```xpp
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
