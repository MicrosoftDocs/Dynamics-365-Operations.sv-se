---
title: Göra självstudier med Regression Suite Automation Tool
description: Det här avsnittet visar hur du använder RSAT (Regression Suite Automation Tool). Den beskriver olika funktioner och ger exempel som använder avancerad skriptanvändning.
author: robinarh
manager: AnnBe
ms.date: 06/09/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: 21761
ms.search.region: Global
ms.author: rhaertle
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: AX 7.0.0, Operations
ms.openlocfilehash: 2d3dde69b102ce161e5c1f1dd393ffceca608bcb
ms.sourcegitcommit: 4fdee254649a751d46632fb4d0d48698e112fa72
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/08/2020
ms.locfileid: "3248746"
---
# <a name="use-the-regression-suite-automation-tool-tutorial"></a><span data-ttu-id="549c6-104">Använda självstudie för Regression Suite Automation Tool</span><span class="sxs-lookup"><span data-stu-id="549c6-104">Use the Regression suite automation tool tutorial</span></span>

[!include [banner](../includes/banner.md)]

> [!NOTE]
> <span data-ttu-id="549c6-105">Använd webbläsarverktygen för att hämta och spara sidan i PDF-format.</span><span class="sxs-lookup"><span data-stu-id="549c6-105">Use your internet browser tools to download and save this page in pdf format.</span></span> 

<span data-ttu-id="549c6-106">I den här vägledningen får du hjälp med några av de avancerade funktionerna i RSAT (Regression Suite Automation Tool), inkluderar en demotilldelning och beskriver strategi- och nyckelutbildningspunkter.</span><span class="sxs-lookup"><span data-stu-id="549c6-106">This tutorial walks through some of the advanced features of the Regression suite automation tool (RSAT), includes a demo assignment, and describes strategy and key learning points.</span></span> 

## <a name="notable-features-of-rsat-and-task-recorder"></a><span data-ttu-id="549c6-107">Viktiga funktioner för RSAT och uppgiftsinspelning</span><span class="sxs-lookup"><span data-stu-id="549c6-107">Notable Features of RSAT and Task recorder</span></span>

### <a name="validate-a-field-value"></a><span data-ttu-id="549c6-108">Validera fältvärdet</span><span class="sxs-lookup"><span data-stu-id="549c6-108">Validate a field value</span></span>

<span data-ttu-id="549c6-109">Med RSAT kan du inkludera valideringssteg i testärendet för att validera förväntade värden.</span><span class="sxs-lookup"><span data-stu-id="549c6-109">RSAT allows you to include validation steps within your test case to validate expected values.</span></span> <span data-ttu-id="549c6-110">Mer information om den här funktionen finns i artikeln [validera förväntade värden](../../dev-itpro/perf-test/rsat/rsat-validate-expected.md).</span><span class="sxs-lookup"><span data-stu-id="549c6-110">For information about this feature, see the article [Validate expected values](../../dev-itpro/perf-test/rsat/rsat-validate-expected.md).</span></span>

<span data-ttu-id="549c6-111">I följande exempel visas hur du kan använda den här funktionen för att validera om lagerbehållningen är större än 0 (noll).</span><span class="sxs-lookup"><span data-stu-id="549c6-111">The following example shows how you can use this feature to validate whether the on-hand inventory is more than 0 (zero).</span></span>

1. <span data-ttu-id="549c6-112">I demonstrationsdata i **USMF**-företaget skapar du en uppgiftsregistrering med följande steg:</span><span class="sxs-lookup"><span data-stu-id="549c6-112">In the demo data in the **USMF** company, create a task recording that has the following steps:</span></span>

    1. <span data-ttu-id="549c6-113">Gå till **Produktinformationshantering \> Produkter \> Frisläppta produkter**.</span><span class="sxs-lookup"><span data-stu-id="549c6-113">Go to **Product information management \> Products \> Released products**.</span></span>
    2. <span data-ttu-id="549c6-114">Använd snabbfiltret för att söka efter poster.</span><span class="sxs-lookup"><span data-stu-id="549c6-114">Use the Quick Filter to find records.</span></span> <span data-ttu-id="549c6-115">Filtrera till exempel i fältet **Artikelnummer** med värdet **1000**.</span><span class="sxs-lookup"><span data-stu-id="549c6-115">For example, filter on a value of **1000** for the **Item number** field.</span></span>
    3. <span data-ttu-id="549c6-116">Välj **lagerbehållning**</span><span class="sxs-lookup"><span data-stu-id="549c6-116">Select **On-hand inventory**.</span></span>
    4. <span data-ttu-id="549c6-117">Använd snabbfiltret för att söka efter poster.</span><span class="sxs-lookup"><span data-stu-id="549c6-117">Use the Quick Filter to find records.</span></span> <span data-ttu-id="549c6-118">Filtrera till exempel på värdet **1** i fältet **Plats**.</span><span class="sxs-lookup"><span data-stu-id="549c6-118">For example, filter on a value of **1** for the **Site** field.</span></span>
    5. <span data-ttu-id="549c6-119">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="549c6-119">In the list, mark the selected row.</span></span>
    6. <span data-ttu-id="549c6-120">Validera att värdet i fältet **totala tillgängliga** är **411,0000000000000000**.</span><span class="sxs-lookup"><span data-stu-id="549c6-120">Validate that the value of the **Total available** field is **411.0000000000000000**.</span></span>

2. <span data-ttu-id="549c6-121">Spara uppgiftsinspelningen och koppla den till ditt testfall i Azure Devops.</span><span class="sxs-lookup"><span data-stu-id="549c6-121">Save the task recording and attach it to your test case in Azure Devops.</span></span>
3. <span data-ttu-id="549c6-122">Lägg till testfallet testplanen och läs in testfallet i RSAT.</span><span class="sxs-lookup"><span data-stu-id="549c6-122">Add the test case to the test plan, and load the test case into RSAT.</span></span>
4. <span data-ttu-id="549c6-123">Öppna Excel-parameterfilen.</span><span class="sxs-lookup"><span data-stu-id="549c6-123">Open the Excel parameter file.</span></span> <span data-ttu-id="549c6-124">På fliken **InventOnhandItem** visas avsnittet **validera InventOnhandItem** som innehåller fältet **Operatör**.</span><span class="sxs-lookup"><span data-stu-id="549c6-124">On the **InventOnhandItem** tab, you will see a **Validate InventOnhandItem** section that includes an **Operator** field.</span></span>

    ![Fältet Operatör](./media/use_rsa_tool_08.png)

5. <span data-ttu-id="549c6-126">Om du vill validera om lagerbehållningen alltid är större än 0 ändrar du värdet i fältet **värde** från **411** till **0** och värdet för fältet **Operatör** från ett likhetstecken (**=**) till ett större än-tecken (**\>**).</span><span class="sxs-lookup"><span data-stu-id="549c6-126">To validate whether the inventory on-hand will always be more than 0, change the value of the **Value** field from **411** to **0** and the value of the **Operator** field from an equal sign (**=**) to a greater than sign (**\>**).</span></span>

    ![Värden för fälten värde och operatör har ändrats](./media/use_rsa_tool_09.png)

6. <span data-ttu-id="549c6-128">Spara och stäng Excel-parameterfilen.</span><span class="sxs-lookup"><span data-stu-id="549c6-128">Save and close the Excel parameter file.</span></span>
7. <span data-ttu-id="549c6-129">Välj **överför** om du vill spara ändringarna som du gjorde i Excel-parameterfilen till Azure DevOps.</span><span class="sxs-lookup"><span data-stu-id="549c6-129">Select **Upload** to save the changes that you made to the Excel parameter file to Azure DevOps.</span></span>

<span data-ttu-id="549c6-130">Om värdet för fältet **totalt tillgängliga** för den angivna artikeln i lagret är högre än 0 (noll), kommer testerna att lyckas, oavsett det faktiska lagerbehållningsvärdet.</span><span class="sxs-lookup"><span data-stu-id="549c6-130">Now, if the value of the **Total Available** field for the specified item in inventory is more than 0 (zero), tests will pass, regardless of the actual on-hand inventory value.</span></span>

### <a name="saved-variables-and-chaining-of-test-cases"></a><span data-ttu-id="549c6-131">Sparade variabler och kedjor för testärenden</span><span class="sxs-lookup"><span data-stu-id="549c6-131">Saved variables and chaining of test cases</span></span>

<span data-ttu-id="549c6-132">En nyckelegenskap i RSAT är en kedja av testfall, det vill säga förmågan hos ett test för att överföra variabler till andra tester.</span><span class="sxs-lookup"><span data-stu-id="549c6-132">One of the key features of RSAT is the chaining of test cases, that is, the ability of a test to pass variables to other tests.</span></span> <span data-ttu-id="549c6-133">Mer information finns i artikeln [kopiera variabler för att kedja testärenden](../../dev-itpro/perf-test/rsat/rsat-chain-test-cases.md).</span><span class="sxs-lookup"><span data-stu-id="549c6-133">For more information, see the article [Copy variables to chain test cases](../../dev-itpro/perf-test/rsat/rsat-chain-test-cases.md).</span></span>

### <a name="derived-test-case"></a><span data-ttu-id="549c6-134">Härlett testfall</span><span class="sxs-lookup"><span data-stu-id="549c6-134">Derived test case</span></span>

<span data-ttu-id="549c6-135">Med RSAT kan du använda samma uppgiftsinspelning med flera testärenden, vilket gör att en uppgift kan köras med olika datakonfigurationer.</span><span class="sxs-lookup"><span data-stu-id="549c6-135">RSAT lets you use the same task recording with multiple test cases, enabling a task to run with different data configurations.</span></span> <span data-ttu-id="549c6-136">Mer information finns i artikeln [härledda testärenden](../../dev-itpro/perf-test/rsat/rsat-derived-test-cases.md).</span><span class="sxs-lookup"><span data-stu-id="549c6-136">See the article [Derived test cases](../../dev-itpro/perf-test/rsat/rsat-derived-test-cases.md) for more information.</span></span>

### <a name="validate-notifications-and-messages"></a><span data-ttu-id="549c6-137">Validera aviseringar och meddelanden</span><span class="sxs-lookup"><span data-stu-id="549c6-137">Validate notifications and messages</span></span>

<span data-ttu-id="549c6-138">Den här funktionen kan användas för att validera om en åtgärd utförts.</span><span class="sxs-lookup"><span data-stu-id="549c6-138">This feature can be used to validate whether an action occurred.</span></span> <span data-ttu-id="549c6-139">När till exempel en tillverkningsorder skapas, uppskattas och sedan startas, visar appen meddelandet "produktion – start" för att meddela dig att tillverkningsordern har startats.</span><span class="sxs-lookup"><span data-stu-id="549c6-139">For example, when a production order is created, estimated, and then started, the app shows a "Production – Start" message to notify you that the production order has been started.</span></span>

![Produktion - starta meddelande](./media/use_rsa_tool_05.png)

<span data-ttu-id="549c6-141">Du kan validera det här meddelandet genom RSAT genom att ange meddelande texten på fliken **MessageValidation** i Excel-parameterfilen för lämplig inspelning.</span><span class="sxs-lookup"><span data-stu-id="549c6-141">You can validate this message through RSAT by entering the message text on the **MessageValidation** tab of the Excel parameter file for the appropriate recording.</span></span>

![Fliken Meddelandevalidering](./media/use_rsa_tool_06.png)

<span data-ttu-id="549c6-143">När testfallet har körts, jämförs meddelandet i Excel-parameterfilen i det meddelande som visas.</span><span class="sxs-lookup"><span data-stu-id="549c6-143">After the test case is run, the message in the Excel parameter file is compared to the message that is shown.</span></span> <span data-ttu-id="549c6-144">Om meddelandena inte matchar kommer testfallet att misslyckas.</span><span class="sxs-lookup"><span data-stu-id="549c6-144">If the messages don't match, the test case will fail.</span></span>

> [!NOTE]
> <span data-ttu-id="549c6-145">Du kan ange mer än ett meddelande på fliken **MessageValidation** i Excel-parameterfilen.</span><span class="sxs-lookup"><span data-stu-id="549c6-145">You can enter more than one message on the **MessageValidation** tab in the Excel parameter file.</span></span> <span data-ttu-id="549c6-146">Meddelandena kan också vara fel- eller varningsmeddelanden i stället för informationsmeddelanden.</span><span class="sxs-lookup"><span data-stu-id="549c6-146">The messages also can be error or warning messages instead of informational messages.</span></span>

### <a name="snapshot"></a><span data-ttu-id="549c6-147">Ögonblicksbild</span><span class="sxs-lookup"><span data-stu-id="549c6-147">Snapshot</span></span>

<span data-ttu-id="549c6-148">Den här funktionen tar skärmbilder av de steg som har utförts under uppgiftsregistreringen.</span><span class="sxs-lookup"><span data-stu-id="549c6-148">This feature takes screenshots of the steps that were performed during task recording.</span></span> <span data-ttu-id="549c6-149">Den är användbar för granskning och felsökning.</span><span class="sxs-lookup"><span data-stu-id="549c6-149">It is useful for auditing or debugging purposes.</span></span>

- <span data-ttu-id="549c6-150">Om du vill använda den här funktionen öppnar du filen **Microsoft.Dynamics.RegressionSuite.WindowsApp.exe.config** under RSAT-installationsmappen (t.ex. **C:\\programfiler (x86)\\Regression Suite Automation Tool**) och ändrar värdet i följande element från **falskt** till **sant**.</span><span class="sxs-lookup"><span data-stu-id="549c6-150">To use this feature, open the **Microsoft.Dynamics.RegressionSuite.WindowsApp.exe.config** file under the RSAT installation folder (for example, **C:\\Program Files (x86)\\Regression Suite Automation Tool**), and change the value of the following element from **false** to **true**.</span></span>

    ```xml
    <add key="VerboseSnapshotsEnabled" value="false" />
    ```

<span data-ttu-id="549c6-151">När du kör testärendet genererar RSAT ögonblicksbilder (bilder) av stegen i mappen uppspelning i testärenden i arbetskatalogen.</span><span class="sxs-lookup"><span data-stu-id="549c6-151">When your run the test case, RSAT will generate snapshots (images) of the steps in the playback folder of the test cases in the working diretory.</span></span> <span data-ttu-id="549c6-152">Om du använder en äldre version av RSAT sparas bilderna i **C:\\Användare\\\<Användarnamn\>\\AppData\\Roaming\\regressionTool\\playback**, en separat mapp skapas för varje testärende som körs.</span><span class="sxs-lookup"><span data-stu-id="549c6-152">If you are using an older version of RSAT, the images are saved to **C:\\Users\\\<Username\>\\AppData\\Roaming\\regressionTool\\playback**, a separate folder is created for each test case that is run.</span></span>

## <a name="assignment"></a><span data-ttu-id="549c6-153">Uppdrag</span><span class="sxs-lookup"><span data-stu-id="549c6-153">Assignment</span></span>

### <a name="scenario"></a><span data-ttu-id="549c6-154">Scenario</span><span class="sxs-lookup"><span data-stu-id="549c6-154">Scenario</span></span>

1. <span data-ttu-id="549c6-155">Produktdesignern skapar en ny frisläppt produkt.</span><span class="sxs-lookup"><span data-stu-id="549c6-155">The product designer creates a new released product.</span></span>
2. <span data-ttu-id="549c6-156">Produktionschefen initierar en tillverkningsorder för att ta med lagernivån till två delar.</span><span class="sxs-lookup"><span data-stu-id="549c6-156">The production manager initiates a production order to bring the stock level to two pieces.</span></span>
3. <span data-ttu-id="549c6-157">Produktion startar och avslutar produktionsordern och verifierar att lagerkvantiteten är två enheter.</span><span class="sxs-lookup"><span data-stu-id="549c6-157">Manufacturing starts and ends the production order, and verifies that the on-hand quantity is two pieces.</span></span>
4. <span data-ttu-id="549c6-158">Försäljningsteamet får en på fyra enheter av den nya produkten.</span><span class="sxs-lookup"><span data-stu-id="549c6-158">The sales team receives an order for four pieces of the new product.</span></span> <span data-ttu-id="549c6-159">Därför uppdaterar försäljningsteamet nettokraven via den dynamiska planen.</span><span class="sxs-lookup"><span data-stu-id="549c6-159">Therefore, the sales team updates the net requirements via the dynamic plan.</span></span> <span data-ttu-id="549c6-160">Eftersom ingen ytterligare kapacitet finns tillgänglig, anges standardorderprincipen till köp istället för tillverka.</span><span class="sxs-lookup"><span data-stu-id="549c6-160">Because no additional capacity is available, the default order policy is set to "buy instead of make."</span></span> <span data-ttu-id="549c6-161">Därför kapas en planerad inköpsorder.</span><span class="sxs-lookup"><span data-stu-id="549c6-161">Therefore, a planned purchase order is created.</span></span>
5. <span data-ttu-id="549c6-162">Köparen lägger till en leverantör, signerar den planerade inköpsordern och bekräftar sedan inköpsordern.</span><span class="sxs-lookup"><span data-stu-id="549c6-162">The buyer adds a vendor, firms the planned purchase order, and then confirms the purchase order.</span></span>
6. <span data-ttu-id="549c6-163">När varorna som köpts in anländer till butiken söker butiksoperatören efter den relaterade inköpsordern och tar emot varorna.</span><span class="sxs-lookup"><span data-stu-id="549c6-163">When the goods that were purchased arrive at the store, the store operator searches the related purchase order and receives the goods.</span></span> <span data-ttu-id="549c6-164">Eftersom ordern nu är slutförd kan varor plockas och förpackas mot försäljningsordern.</span><span class="sxs-lookup"><span data-stu-id="549c6-164">Because the order is now completed, goods can be picked and packed against the sales order.</span></span>
7. <span data-ttu-id="549c6-165">Ekonomi bokför inköpsfakturan och försäljningsfakturan.</span><span class="sxs-lookup"><span data-stu-id="549c6-165">Finance posts the purchase invoice and sales invoice.</span></span>

<span data-ttu-id="549c6-166">Följande bild visar flödet för det här scenariot.</span><span class="sxs-lookup"><span data-stu-id="549c6-166">The following illustration shows the flow for this scenario.</span></span>

![Flöde för demoscenariot](./media/use_rsa_tool_14.png)

<span data-ttu-id="549c6-168">Följande bild visar hierarkin för affärsprocesser för det här scenariot i LCS affärsprocessmodelleraren.</span><span class="sxs-lookup"><span data-stu-id="549c6-168">The following illustration shows the business processes hierarchy for this scenario in the LCS Business Process Modeler.</span></span>

![Affärsprocesser för demoscenariot](./media/use_rsa_tool_15.png)

## <a name="strategy--key-learning"></a><span data-ttu-id="549c6-170">Strategi – viktiga utbildningsmaterial</span><span class="sxs-lookup"><span data-stu-id="549c6-170">Strategy – Key learning</span></span>

### <a name="data"></a><span data-ttu-id="549c6-171">Data</span><span class="sxs-lookup"><span data-stu-id="549c6-171">Data</span></span>

- <span data-ttu-id="549c6-172">Se till att du har representativa datavolymer (en kopia av produktions- och gyllene konfigurationsdata plus migrerade data).</span><span class="sxs-lookup"><span data-stu-id="549c6-172">Make sure that you have representative data volumes (a copy of production/golden configuration data plus migrated data).</span></span>
- <span data-ttu-id="549c6-173">När du genererar nya data via uppgiftsregistrering ska du skapa testnamn som inte är i konflikt med befintliga namn (du kan till exempel använda prefix som **RSATxxx**).</span><span class="sxs-lookup"><span data-stu-id="549c6-173">When you generate new data via Task recorder, create test names that won't conflict with existing names (for example, use a prefix such as **RSATxxx**).</span></span>
- <span data-ttu-id="549c6-174">Använd Azure tidpunktsåterställning för att köra om tester på andra miljöer än icke-nivå 1.</span><span class="sxs-lookup"><span data-stu-id="549c6-174">Use Azure Point-In-Time restore to rerun tests in non-Tier 1 environments.</span></span>
- <span data-ttu-id="549c6-175">Även om du kan använda Excel-funktionerna **SLUMPMÄSSIGA** och **NU** för att generera en unik kombination, är arbetsinsatsen betydligt hög.</span><span class="sxs-lookup"><span data-stu-id="549c6-175">Although you can use the **RANDOM** and **NOW** Excel functions to generate a unique combination, the effort is considerably high.</span></span> <span data-ttu-id="549c6-176">Här är ett exempel:</span><span class="sxs-lookup"><span data-stu-id="549c6-176">Here is an example.</span></span>

    ```Excel
    product = "AT" &TEXT(NOW(),"yyymmddhhmm")
    ```

### <a name="task-recorder"></a><span data-ttu-id="549c6-177">Uppgiftsregistrering</span><span class="sxs-lookup"><span data-stu-id="549c6-177">Task recorder</span></span>

- <span data-ttu-id="549c6-178">Definiera scenarier innan du startar inspelningen.</span><span class="sxs-lookup"><span data-stu-id="549c6-178">Define scenarios before you start recording.</span></span> <span data-ttu-id="549c6-179">Ett välhanterat projekt har fördefinierade testscenarier.</span><span class="sxs-lookup"><span data-stu-id="549c6-179">A well-managed project has predefined test scenarios.</span></span> <span data-ttu-id="549c6-180">Om du vill bygga ett testfall bör du överväga hur förutsägbara resultatet av testscenarierna är.</span><span class="sxs-lookup"><span data-stu-id="549c6-180">To build a test case, consider how predictable the outcome of those test scenarios is.</span></span>
- <span data-ttu-id="549c6-181">Dela upp inspelningar om de utförs av olika roller eller om det finns väntetid eller extern händelse före nästa steg.</span><span class="sxs-lookup"><span data-stu-id="549c6-181">Split recordings if they are performed by different roles, or if there is waiting time or an external event before the next step.</span></span>
- <span data-ttu-id="549c6-182">Undvik att markera värden i listor.</span><span class="sxs-lookup"><span data-stu-id="549c6-182">Avoid selecting values in lists.</span></span> <span data-ttu-id="549c6-183">Använd i stället textformat, t.ex. **FIFO**. **AudioRM** och **SiteWH**.</span><span class="sxs-lookup"><span data-stu-id="549c6-183">Instead, use text formats, such as **FIFO**, **AudioRM**, and **SiteWH**.</span></span> <span data-ttu-id="549c6-184">När du väljer i en lista registreras placeringen av värdet i listan, inte själva värdet.</span><span class="sxs-lookup"><span data-stu-id="549c6-184">When you select in a list, the position of the value in the list is recorded, not the value itself.</span></span> <span data-ttu-id="549c6-185">Om du lägger till objekt i listan kan placeringen av värdet ändras.</span><span class="sxs-lookup"><span data-stu-id="549c6-185">If items are added to that list, the position of the value can change.</span></span> <span data-ttu-id="549c6-186">Därför kommer din registrering att använda en annan parameter och resten av scenariot kan påverkas.</span><span class="sxs-lookup"><span data-stu-id="549c6-186">Therefore, your recording will use a different parameter, and the rest of the scenario might be affected.</span></span>
- <span data-ttu-id="549c6-187">Tänk på hur flera användare fungerar.</span><span class="sxs-lookup"><span data-stu-id="549c6-187">Think about multi-user behavior.</span></span> <span data-ttu-id="549c6-188">Antag till exempel inte att den nya försäljningsordern alltid väljs automatiskt.</span><span class="sxs-lookup"><span data-stu-id="549c6-188">For example, don't assume that your newly created sales order will always be automatically selected.</span></span> <span data-ttu-id="549c6-189">I stället ska du alltid använda filtret för att hitta rätt ordning.</span><span class="sxs-lookup"><span data-stu-id="549c6-189">Instead, always use the filter to find the correct order.</span></span>
- <span data-ttu-id="549c6-190">Använd kopieringsfunktionen i uppgiftsinspelning om du vill spara namnet på en nyskapad produkt så att den kan användas i kedjade testfall.</span><span class="sxs-lookup"><span data-stu-id="549c6-190">Use the Copy function in Task recorder to save the name of a newly created product so it can be used in chained test cases.</span></span>
- <span data-ttu-id="549c6-191">Använd funktionen validera i uppgiftsregistrering om du vill ställa in kontrollpunkter som verifierar att stegen har körts på rätt sätt.</span><span class="sxs-lookup"><span data-stu-id="549c6-191">Use the Validate function in Task recorder to set checkpoints that verify that steps have been run correctly.</span></span>

### <a name="rsat"></a><span data-ttu-id="549c6-192">RSAT</span><span class="sxs-lookup"><span data-stu-id="549c6-192">RSAT</span></span>

- <span data-ttu-id="549c6-193">Om du vill köra testet i ett annat företag kan du ändra företaget på fliken **allmänt** i Excel-parameterfilen.</span><span class="sxs-lookup"><span data-stu-id="549c6-193">To run the test in another company, you can change the company on the **General** tab of the Excel parameter file.</span></span> <span data-ttu-id="549c6-194">Kontrollera att inställningar och data är tillgängliga i det valda företaget.</span><span class="sxs-lookup"><span data-stu-id="549c6-194">Make sure that settings and data are available in the newly selected company.</span></span>
- <span data-ttu-id="549c6-195">Du kan ändra testanvändaren på fliken **allmänt** i Excel-parameterfilen.</span><span class="sxs-lookup"><span data-stu-id="549c6-195">You can change the test user on the **General** tab of the Excel parameter file.</span></span> <span data-ttu-id="549c6-196">Ange e-post-ID för den användare som ska köra test fallet.</span><span class="sxs-lookup"><span data-stu-id="549c6-196">Specify the email ID of the user who will run the test case.</span></span> <span data-ttu-id="549c6-197">På så sätt kan testfallet köras med hjälp av den angivna användarens säkerhetsbehörigheter.</span><span class="sxs-lookup"><span data-stu-id="549c6-197">In this way, the test case can be run by using the security permissions of the specified user.</span></span>
- <span data-ttu-id="549c6-198">Om du vill vänta innan testet påbörjas kan du definiera en paus på fliken **allmänt** i Excel-parameterfilen.</span><span class="sxs-lookup"><span data-stu-id="549c6-198">To wait before the test is started, you can define a pause on the **General** tab of the Excel parameter file.</span></span> <span data-ttu-id="549c6-199">Denna paus kan användas i ett batchjobb (t.ex. om ett arbetsflöde måste köras innan nästa steg kan utföras.)</span><span class="sxs-lookup"><span data-stu-id="549c6-199">This pause can be used in a batch job (for example, if a workflow must be run before the next step can be performed.)</span></span>

## <a name="advanced-scripting"></a><span data-ttu-id="549c6-200">Avancerade skript</span><span class="sxs-lookup"><span data-stu-id="549c6-200">Advanced scripting</span></span>

### <a name="cli"></a><span data-ttu-id="549c6-201">CLI</span><span class="sxs-lookup"><span data-stu-id="549c6-201">CLI</span></span>

<span data-ttu-id="549c6-202">RSAT kan anropas från fönstret **kommandotolk** eller **PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="549c6-202">RSAT can be called from a **Command Prompt** or **PowerShell** window.</span></span>

> [!NOTE]
> <span data-ttu-id="549c6-203">Kontrollera att miljövariabeln **TestRoot** anges till RSAT installationens sökväg.</span><span class="sxs-lookup"><span data-stu-id="549c6-203">Verify that the **TestRoot** environment variable is set to the RSAT installation path.</span></span> <span data-ttu-id="549c6-204">(I Microsoft Windows, öppna **kontrollkontroll**, välj **Systemoch säkerhet \> System \> Avancerade systeminställningar** och välj sedan **miljövariabler**.)</span><span class="sxs-lookup"><span data-stu-id="549c6-204">(In Microsoft Windows, open **Control Panel**, select **System and Security \> System \> Advanced system settings**, and then select **Environment Variables**.)</span></span>

1. <span data-ttu-id="549c6-205">Öppna ett **kommandotolk** eller **PowerShell** som admin.</span><span class="sxs-lookup"><span data-stu-id="549c6-205">Open a **Command Prompt** or **PowerShell** window as an admin.</span></span>
2. <span data-ttu-id="549c6-206">Navigera till installationskatalogen för RSAT.</span><span class="sxs-lookup"><span data-stu-id="549c6-206">Navigate to the RSAT installation directory.</span></span>

    ```Console
    cd "c:\Program Files (x86)\Regression Suite Automation Tool\"
    ```

3. <span data-ttu-id="549c6-207">Lista alla kommandon.</span><span class="sxs-lookup"><span data-stu-id="549c6-207">List all commands.</span></span>

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

#### <a name=""></a><span data-ttu-id="549c6-208">?</span><span class="sxs-lookup"><span data-stu-id="549c6-208">?</span></span> 
<span data-ttu-id="549c6-209">Visar hjälp om alla tillgängliga kommandon och deras parametrar.</span><span class="sxs-lookup"><span data-stu-id="549c6-209">Shows help about all available commands and their parameters.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``?``**``[command]``

##### <a name="optional-parameters"></a><span data-ttu-id="549c6-210">Valfria parametrar</span><span class="sxs-lookup"><span data-stu-id="549c6-210">Optional parameters</span></span>

**``command``**


<span data-ttu-id="549c6-211">Där ``[command]`` är ett av de kommandon som anges nedan.</span><span class="sxs-lookup"><span data-stu-id="549c6-211">Where ``[command]`` is one of the commands specified below.</span></span>


#### <a name="about"></a><span data-ttu-id="549c6-212">om</span><span class="sxs-lookup"><span data-stu-id="549c6-212">about</span></span>
<span data-ttu-id="549c6-213">Visar den aktuella versionen.</span><span class="sxs-lookup"><span data-stu-id="549c6-213">Displays the current version.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``about``**

#### <a name="cls"></a><span data-ttu-id="549c6-214">cls</span><span class="sxs-lookup"><span data-stu-id="549c6-214">cls</span></span>
<span data-ttu-id="549c6-215">Rensar skärmen.</span><span class="sxs-lookup"><span data-stu-id="549c6-215">Clears the screen.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``cls``**


#### <a name="download"></a><span data-ttu-id="549c6-216">hämta</span><span class="sxs-lookup"><span data-stu-id="549c6-216">download</span></span>
<span data-ttu-id="549c6-217">Hämtar bifogade filer för det angivna testfallet till utdatafilen.</span><span class="sxs-lookup"><span data-stu-id="549c6-217">Downloads attachments for the specified test case to the output directory.</span></span> <span data-ttu-id="549c6-218">Du kan använda ``list`` kommandot för att hämta alla tillgängliga testärenden.</span><span class="sxs-lookup"><span data-stu-id="549c6-218">You can use the ``list`` command to get all available test cases.</span></span> <span data-ttu-id="549c6-219">Använd valfritt värde från den första kolumnen som en **test_case_id** parameter.</span><span class="sxs-lookup"><span data-stu-id="549c6-219">Use any value from the first column as a **test_case_id** parameter.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``download``**``[test_case_id] [output_dir]``

##### <a name="required-parameters"></a><span data-ttu-id="549c6-220">Obligatoriska parametrar</span><span class="sxs-lookup"><span data-stu-id="549c6-220">Required parameters</span></span>
<span data-ttu-id="549c6-221">**``test_case_id``** Representerar ID för testärende.</span><span class="sxs-lookup"><span data-stu-id="549c6-221">**``test_case_id``** Represents the test case ID.</span></span>  
<span data-ttu-id="549c6-222">**``output_dir``** Representerar katalogen för utdata.</span><span class="sxs-lookup"><span data-stu-id="549c6-222">**``output_dir``** Represents the output directory.</span></span> <span data-ttu-id="549c6-223">Katalogen måste finnas.</span><span class="sxs-lookup"><span data-stu-id="549c6-223">The directory must exist.</span></span>

##### <a name="examples"></a><span data-ttu-id="549c6-224">Exempel</span><span class="sxs-lookup"><span data-stu-id="549c6-224">Examples</span></span>

``download 123 c:\temp\rsat``   
``download 765 c:\rsat\last``


#### <a name="edit"></a><span data-ttu-id="549c6-225">redigera</span><span class="sxs-lookup"><span data-stu-id="549c6-225">edit</span></span>
<span data-ttu-id="549c6-226">Gör att du kan öppna parameter filen i Excel-programmet och redigera den.</span><span class="sxs-lookup"><span data-stu-id="549c6-226">Allows you to open parameters file in Excel program and edit it.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``edit``**``[excel_file]``

##### <a name="required-parameters"></a><span data-ttu-id="549c6-227">Obligatoriska parametrar</span><span class="sxs-lookup"><span data-stu-id="549c6-227">Required parameters</span></span>
<span data-ttu-id="549c6-228">**``excel_file``** Måste innehålla en fullständig sökväg till en befintlig Excel-fil.</span><span class="sxs-lookup"><span data-stu-id="549c6-228">**``excel_file``** Must contain a full path to an existing Excel file.</span></span>

##### <a name="examples"></a><span data-ttu-id="549c6-229">Exempel</span><span class="sxs-lookup"><span data-stu-id="549c6-229">Examples</span></span>
``edit c:\RSAT\TestCase_123_Base.xlsx``  
``edit e:\temp\TestCase_456_Base.xlsx``


#### <a name="generate"></a><span data-ttu-id="549c6-230">skapa</span><span class="sxs-lookup"><span data-stu-id="549c6-230">generate</span></span>
<span data-ttu-id="549c6-231">Skapar test körnings- och parametervärden för det angivna testärendet i utdatapanelen.</span><span class="sxs-lookup"><span data-stu-id="549c6-231">Generates test execution and parameter files for the specified test case in the output directory.</span></span>
<span data-ttu-id="549c6-232">Du kan använda ``list`` kommandot för att hämta alla tillgängliga testärenden.</span><span class="sxs-lookup"><span data-stu-id="549c6-232">You can use the ``list`` command to get all available test cases.</span></span> <span data-ttu-id="549c6-233">Använd valfritt värde från den första kolumnen som en **test_case_id** parameter.</span><span class="sxs-lookup"><span data-stu-id="549c6-233">Use any value from the first column as a **test_case_id** parameter.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``generate``**``[test_case_id] [output_dir]``

##### <a name="required-parameters"></a><span data-ttu-id="549c6-234">Obligatoriska parametrar</span><span class="sxs-lookup"><span data-stu-id="549c6-234">Required parameters</span></span>
<span data-ttu-id="549c6-235">**``test_case_id``** Representerar ID för testärende.</span><span class="sxs-lookup"><span data-stu-id="549c6-235">**``test_case_id``** Represents the test case ID.</span></span>  
<span data-ttu-id="549c6-236">**``output_dir``** Representerar katalogen för utdata.</span><span class="sxs-lookup"><span data-stu-id="549c6-236">**``output_dir``** Represents the output directory.</span></span> <span data-ttu-id="549c6-237">Katalogen måste finnas.</span><span class="sxs-lookup"><span data-stu-id="549c6-237">The directory must exist.</span></span>

##### <a name="examples"></a><span data-ttu-id="549c6-238">Exempel</span><span class="sxs-lookup"><span data-stu-id="549c6-238">Examples</span></span>
``generate 123 c:\temp\rsat``  
``generate 765 c:\rsat\last``


#### <a name="generatederived"></a><span data-ttu-id="549c6-239">generatederived</span><span class="sxs-lookup"><span data-stu-id="549c6-239">generatederived</span></span>
<span data-ttu-id="549c6-240">Genererar ett nytt testärende som härletts från det angivna testärendet.</span><span class="sxs-lookup"><span data-stu-id="549c6-240">Generates a new test case, derived from the provided test case.</span></span> <span data-ttu-id="549c6-241">Du kan använda ``list`` kommandot för att hämta alla tillgängliga testärenden.</span><span class="sxs-lookup"><span data-stu-id="549c6-241">You can use the ``list`` command to get all available test cases.</span></span> <span data-ttu-id="549c6-242">Använd valfritt värde från den första kolumnen som en **test_case_id** parameter.</span><span class="sxs-lookup"><span data-stu-id="549c6-242">Use any value from the first column as a **test_case_id** parameter.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``generatederived``**``[parent_test_case_id] [test_plan_id] [test_suite_id]``

##### <a name="required-parameters"></a><span data-ttu-id="549c6-243">Obligatoriska parametrar</span><span class="sxs-lookup"><span data-stu-id="549c6-243">Required parameters</span></span>
<span data-ttu-id="549c6-244">**``parent_test_case_id``** Representerar överordnat ID för testärende.</span><span class="sxs-lookup"><span data-stu-id="549c6-244">**``parent_test_case_id``** Represents the parent test case ID.</span></span>  
<span data-ttu-id="549c6-245">**``test_plan_id``** Representerar ID för testplan.</span><span class="sxs-lookup"><span data-stu-id="549c6-245">**``test_plan_id``** Represents the test plan ID.</span></span>  
<span data-ttu-id="549c6-246">**``test_suite_id``** Representerar ID för testpaketet.</span><span class="sxs-lookup"><span data-stu-id="549c6-246">**``test_suite_id``** Represents the test suite ID.</span></span>

##### <a name="examples"></a><span data-ttu-id="549c6-247">Exempel</span><span class="sxs-lookup"><span data-stu-id="549c6-247">Examples</span></span>
``generatederived 123 8901 678``


#### <a name="generatetestonly"></a><span data-ttu-id="549c6-248">generatetestonly</span><span class="sxs-lookup"><span data-stu-id="549c6-248">generatetestonly</span></span>
<span data-ttu-id="549c6-249">Skapar endast test körningsfil för det angivna testärendet i utdatapanelen.</span><span class="sxs-lookup"><span data-stu-id="549c6-249">Generates only test execution file for the specified test case in the output directory.</span></span> <span data-ttu-id="549c6-250">Du kan använda ``list`` kommandot för att hämta alla tillgängliga testärenden.</span><span class="sxs-lookup"><span data-stu-id="549c6-250">You can use the ``list`` command to get all available test cases.</span></span> <span data-ttu-id="549c6-251">Använd valfritt värde från den första kolumnen som en **test_case_id** parameter.</span><span class="sxs-lookup"><span data-stu-id="549c6-251">Use any value from the first column as a **test_case_id** parameter.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``generatetestonly``**``[test_case_id] [output_dir]``

##### <a name="required-parameters"></a><span data-ttu-id="549c6-252">Obligatoriska parametrar</span><span class="sxs-lookup"><span data-stu-id="549c6-252">Required parameters</span></span>
<span data-ttu-id="549c6-253">**``test_case_id``** Representerar ID för testärende.</span><span class="sxs-lookup"><span data-stu-id="549c6-253">**``test_case_id``** Represents the test case ID.</span></span>  
<span data-ttu-id="549c6-254">**``output_dir``** Representerar katalogen för utdata.</span><span class="sxs-lookup"><span data-stu-id="549c6-254">**``output_dir``** Represents the output directory.</span></span> <span data-ttu-id="549c6-255">Katalogen måste finnas.</span><span class="sxs-lookup"><span data-stu-id="549c6-255">The directory must exist.</span></span>

##### <a name="examples"></a><span data-ttu-id="549c6-256">Exempel</span><span class="sxs-lookup"><span data-stu-id="549c6-256">Examples</span></span>
``generatetestonly 123 c:\temp\rsat``  
``generatetestonly 765 c:\rsat\last``


#### <a name="generatetestsuite"></a><span data-ttu-id="549c6-257">generatetestsuite</span><span class="sxs-lookup"><span data-stu-id="549c6-257">generatetestsuite</span></span>
<span data-ttu-id="549c6-258">Genererar alla testärenden för det angivna paketet i utdatakatalogen.</span><span class="sxs-lookup"><span data-stu-id="549c6-258">Generates all test cases for the specified suite in the output directory.</span></span>
<span data-ttu-id="549c6-259">Du kan använda ``listtestsuitenames`` kommandot för att hämta alla tillgängliga testpaket.</span><span class="sxs-lookup"><span data-stu-id="549c6-259">You can use ``listtestsuitenames`` command to get all available test suits.</span></span> <span data-ttu-id="549c6-260">Använd valfritt värde kolumnen som en **test_suite_name** parameter.</span><span class="sxs-lookup"><span data-stu-id="549c6-260">Use any value from the column as a **test_suite_name** parameter.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``generatetestsuite``**``[test_suite_name] [output_dir]``

##### <a name="required-parameters"></a><span data-ttu-id="549c6-261">Obligatoriska parametrar</span><span class="sxs-lookup"><span data-stu-id="549c6-261">Required parameters</span></span>
<span data-ttu-id="549c6-262">**``test_suite_name``** Representerar testpaketets namn.</span><span class="sxs-lookup"><span data-stu-id="549c6-262">**``test_suite_name``** Represents the test suite name.</span></span>  
<span data-ttu-id="549c6-263">**``output_dir``** Representerar katalogen för utdata.</span><span class="sxs-lookup"><span data-stu-id="549c6-263">**``output_dir``** Represents the output directory.</span></span> <span data-ttu-id="549c6-264">Katalogen måste finnas.</span><span class="sxs-lookup"><span data-stu-id="549c6-264">The directory must exist.</span></span>

##### <a name="examples"></a><span data-ttu-id="549c6-265">Exempel</span><span class="sxs-lookup"><span data-stu-id="549c6-265">Examples</span></span>
``generatetestsuite Tests c:\temp\rsat``   
``generatetestsuite Purchase c:\rsat\last``


#### <a name="help"></a><span data-ttu-id="549c6-266">hjälp</span><span class="sxs-lookup"><span data-stu-id="549c6-266">help</span></span>
<span data-ttu-id="549c6-267">Är identisk med [?](#section)</span><span class="sxs-lookup"><span data-stu-id="549c6-267">Identical to the [?](#section)</span></span> <span data-ttu-id="549c6-268">kommando</span><span class="sxs-lookup"><span data-stu-id="549c6-268">command</span></span>


#### <a name="list"></a><span data-ttu-id="549c6-269">listan</span><span class="sxs-lookup"><span data-stu-id="549c6-269">list</span></span>
<span data-ttu-id="549c6-270">Visar alla tillgängliga testärenden.</span><span class="sxs-lookup"><span data-stu-id="549c6-270">Lists all available test cases.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``list``**


#### <a name="listtestplans"></a><span data-ttu-id="549c6-271">listtestplans</span><span class="sxs-lookup"><span data-stu-id="549c6-271">listtestplans</span></span>
<span data-ttu-id="549c6-272">Visar alla tillgängliga testplaner.</span><span class="sxs-lookup"><span data-stu-id="549c6-272">Lists all available test plans.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``listtestplans``**


#### <a name="listtestsuite"></a><span data-ttu-id="549c6-273">listtestsuite</span><span class="sxs-lookup"><span data-stu-id="549c6-273">listtestsuite</span></span>
<span data-ttu-id="549c6-274">Visar testärenden för angivet testpaket.</span><span class="sxs-lookup"><span data-stu-id="549c6-274">Lists test cases for the specified test suite.</span></span> <span data-ttu-id="549c6-275">Du kan använda ``listtestsuitenames`` kommandot för att hämta alla tillgängliga testpaket.</span><span class="sxs-lookup"><span data-stu-id="549c6-275">You can use ``listtestsuitenames`` command to get all available test suites.</span></span> <span data-ttu-id="549c6-276">Använd valfritt värde från första kolumnen som en **suite_name** parameter.</span><span class="sxs-lookup"><span data-stu-id="549c6-276">Use any value from first column as **suite_name** parameter.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``listtestsuite``**``[suite_name]``

##### <a name="required-parameters"></a><span data-ttu-id="549c6-277">Obligatoriska parametrar</span><span class="sxs-lookup"><span data-stu-id="549c6-277">Required parameters</span></span>
<span data-ttu-id="549c6-278">**``suite_name``** Namn på önskat paket.</span><span class="sxs-lookup"><span data-stu-id="549c6-278">**``suite_name``** Name of the desired suite.</span></span>

##### <a name="examples"></a><span data-ttu-id="549c6-279">Exempel</span><span class="sxs-lookup"><span data-stu-id="549c6-279">Examples</span></span>
``listtestsuite "sample suite name"``  
``listtestsuite NameOfTheSuite``


#### <a name="listtestsuitenames"></a><span data-ttu-id="549c6-280">listtestsuitenames</span><span class="sxs-lookup"><span data-stu-id="549c6-280">listtestsuitenames</span></span>
<span data-ttu-id="549c6-281">Visar alla tillgängliga testpaket.</span><span class="sxs-lookup"><span data-stu-id="549c6-281">Lists all available test suites.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``listtestsuitenames``**


#### <a name="playback"></a><span data-ttu-id="549c6-282">playback</span><span class="sxs-lookup"><span data-stu-id="549c6-282">playback</span></span>
<span data-ttu-id="549c6-283">Spelar upp ett testärende med hjälp av en Excel-fil.</span><span class="sxs-lookup"><span data-stu-id="549c6-283">Plays back a test case using an Excel file.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``playback``**``[excel_file]``

##### <a name="required-parameters"></a><span data-ttu-id="549c6-284">Obligatoriska parametrar</span><span class="sxs-lookup"><span data-stu-id="549c6-284">Required parameters</span></span>
<span data-ttu-id="549c6-285">**``excel_file``** En fullständig sökväg till Excel-filen.</span><span class="sxs-lookup"><span data-stu-id="549c6-285">**``excel_file``** A full path to the Excel file.</span></span> <span data-ttu-id="549c6-286">Filen måste finnas.</span><span class="sxs-lookup"><span data-stu-id="549c6-286">File must exist.</span></span> 

##### <a name="examples"></a><span data-ttu-id="549c6-287">Exempel</span><span class="sxs-lookup"><span data-stu-id="549c6-287">Examples</span></span>
``
playback c:\RSAT\TestCaseParameters\sample1.xlsx
playback e:\temp\test.xlsx
``


#### <a name="playbackbyid"></a><span data-ttu-id="549c6-288">playbackbyid</span><span class="sxs-lookup"><span data-stu-id="549c6-288">playbackbyid</span></span>
<span data-ttu-id="549c6-289">Spelar upp flera testärenden samtidigt.</span><span class="sxs-lookup"><span data-stu-id="549c6-289">Plays back multiple test cases at once.</span></span>
<span data-ttu-id="549c6-290">Du kan använda ``list`` kommandot för att hämta alla tillgängliga testärenden.</span><span class="sxs-lookup"><span data-stu-id="549c6-290">You can use the ``list`` command to get all available test cases.</span></span> <span data-ttu-id="549c6-291">Använd valfritt värde från den första kolumnen som en **test_case_id** parameter.</span><span class="sxs-lookup"><span data-stu-id="549c6-291">Use any value from the first column as a **test_case_id** parameter.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``playbackbyid``**``[test_case_id1] [test_case_id2] ... [test_case_idN]``

##### <a name="required-parameters"></a><span data-ttu-id="549c6-292">Obligatoriska parametrar</span><span class="sxs-lookup"><span data-stu-id="549c6-292">Required parameters</span></span>
<span data-ttu-id="549c6-293">**``test_case_id1``** ID för befintliga testärenden.</span><span class="sxs-lookup"><span data-stu-id="549c6-293">**``test_case_id1``** ID of exisiting test case.</span></span>  
<span data-ttu-id="549c6-294">**``test_case_id2``** ID för befintliga testärenden.</span><span class="sxs-lookup"><span data-stu-id="549c6-294">**``test_case_id2``** ID of exisiting test case.</span></span>  
<span data-ttu-id="549c6-295">**``test_case_idN``** ID för befintliga testärenden.</span><span class="sxs-lookup"><span data-stu-id="549c6-295">**``test_case_idN``** ID of exisiting test case.</span></span>  

##### <a name="examples"></a><span data-ttu-id="549c6-296">Exempel</span><span class="sxs-lookup"><span data-stu-id="549c6-296">Examples</span></span>
``playbackbyid 878``  
``playbackbyid 2345 667 135``


#### <a name="playbackmany"></a><span data-ttu-id="549c6-297">playbackmany</span><span class="sxs-lookup"><span data-stu-id="549c6-297">playbackmany</span></span>
<span data-ttu-id="549c6-298">Spelar upp många testärenden samtidigt, med Excel-filer.</span><span class="sxs-lookup"><span data-stu-id="549c6-298">Plays back many test cases at once, using Excel files.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``playbackmany``**``[excel_file1] [excel_file2] ... [excel_fileN]``

##### <a name="required-parameters"></a><span data-ttu-id="549c6-299">Obligatoriska parametrar</span><span class="sxs-lookup"><span data-stu-id="549c6-299">Required parameters</span></span>
<span data-ttu-id="549c6-300">**``excel_file1``** Fullständig sökväg till Excel-filen.</span><span class="sxs-lookup"><span data-stu-id="549c6-300">**``excel_file1``** Full path to the Excel file.</span></span> <span data-ttu-id="549c6-301">Filen måste finnas.</span><span class="sxs-lookup"><span data-stu-id="549c6-301">File must exist.</span></span>  
<span data-ttu-id="549c6-302">**``excel_file2``** Fullständig sökväg till Excel-filen.</span><span class="sxs-lookup"><span data-stu-id="549c6-302">**``excel_file2``** Full path to the Excel file.</span></span> <span data-ttu-id="549c6-303">Filen måste finnas.</span><span class="sxs-lookup"><span data-stu-id="549c6-303">File must exist.</span></span>  
<span data-ttu-id="549c6-304">**``excel_fileN``** Fullständig sökväg till Excel-filen.</span><span class="sxs-lookup"><span data-stu-id="549c6-304">**``excel_fileN``** Full path to the Excel file.</span></span> <span data-ttu-id="549c6-305">Filen måste finnas.</span><span class="sxs-lookup"><span data-stu-id="549c6-305">File must exist.</span></span>  

##### <a name="examples"></a><span data-ttu-id="549c6-306">Exempel</span><span class="sxs-lookup"><span data-stu-id="549c6-306">Examples</span></span>
``playbackmany c:\RSAT\TestCaseParameters\param1.xlsx``  
``playbackmany e:\temp\test.xlsx f:\rsat\sample1.xlsx c:\RSAT\sample2.xlsx``


#### <a name="playbacksuite"></a><span data-ttu-id="549c6-307">playbacksuite</span><span class="sxs-lookup"><span data-stu-id="549c6-307">playbacksuite</span></span>
<span data-ttu-id="549c6-308">Spelar upp alla testärende från angiven testpaket.</span><span class="sxs-lookup"><span data-stu-id="549c6-308">Plays back all test cases from the specified test suite.</span></span> <span data-ttu-id="549c6-309">Du kan använda ``listtestsuitenames`` kommandot för att hämta alla tillgängliga testpaket.</span><span class="sxs-lookup"><span data-stu-id="549c6-309">You can use ``listtestsuitenames`` command to get all available test suites.</span></span> <span data-ttu-id="549c6-310">Använd valfritt värde från första kolumnen som en **suite_name** parameter.</span><span class="sxs-lookup"><span data-stu-id="549c6-310">Use any value from first column as **suite_name** parameter.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``playbacksuite``**``[suite_name]``

##### <a name="required-parameters"></a><span data-ttu-id="549c6-311">Obligatoriska parametrar</span><span class="sxs-lookup"><span data-stu-id="549c6-311">Required parameters</span></span>
<span data-ttu-id="549c6-312">**``suite_name``** Namn på önskat paket.</span><span class="sxs-lookup"><span data-stu-id="549c6-312">**``suite_name``** Name of the desired suite.</span></span>

##### <a name="examples"></a><span data-ttu-id="549c6-313">Exempel</span><span class="sxs-lookup"><span data-stu-id="549c6-313">Examples</span></span>
``playbacksuite suiteName``  
``playbacksuite sample_suite``


#### <a name="quit"></a><span data-ttu-id="549c6-314">avsluta</span><span class="sxs-lookup"><span data-stu-id="549c6-314">quit</span></span>
<span data-ttu-id="549c6-315">Stänger programmet.</span><span class="sxs-lookup"><span data-stu-id="549c6-315">Closes the  application.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``quit``**


#### <a name="upload"></a><span data-ttu-id="549c6-316">överför</span><span class="sxs-lookup"><span data-stu-id="549c6-316">upload</span></span>
<span data-ttu-id="549c6-317">Överför alla filer som hör till de angivna testpaketen eller testärenden.</span><span class="sxs-lookup"><span data-stu-id="549c6-317">Uploads all files belonging to the specified test suite or test cases.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``upload``**``[suite_name] [testcase_id]``

#### <a name="required-parameters"></a><span data-ttu-id="549c6-318">Obligatoriska parametrar</span><span class="sxs-lookup"><span data-stu-id="549c6-318">Required parameters</span></span>
<span data-ttu-id="549c6-319">**``suite_name``** Alla filer som hör till de angivna testpaketen kommer att laddas upp.</span><span class="sxs-lookup"><span data-stu-id="549c6-319">**``suite_name``** All files belonging to the specified test suite will be uploaded.</span></span>
<span data-ttu-id="549c6-320">**``testcase_id``** Alla filer hör till de angivna testärenden kommer att laddas upp.</span><span class="sxs-lookup"><span data-stu-id="549c6-320">**``testcase_id``** All files beloning to the specified test case(s) will be uploaded.</span></span>

##### <a name="examples"></a><span data-ttu-id="549c6-321">Exempel</span><span class="sxs-lookup"><span data-stu-id="549c6-321">Examples</span></span>
``upload sample_suite``  
``upload 123``  
``upload 123 456``


#### <a name="uploadrecording"></a><span data-ttu-id="549c6-322">uploadrecording</span><span class="sxs-lookup"><span data-stu-id="549c6-322">uploadrecording</span></span>
<span data-ttu-id="549c6-323">Överför endast registreringsfil som hör till de angivna testärenden.</span><span class="sxs-lookup"><span data-stu-id="549c6-323">Uploads only recording file belonging to the specified test cases.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``uploadrecording``**``[testcase_id]``

##### <a name="required-parameters"></a><span data-ttu-id="549c6-324">Obligatoriska parametrar</span><span class="sxs-lookup"><span data-stu-id="549c6-324">Required parameters</span></span>
<span data-ttu-id="549c6-325">**``testcase_id``** Registreringsfil som hör till de angivna testärenden kommer att överföras.</span><span class="sxs-lookup"><span data-stu-id="549c6-325">**``testcase_id``** Recording file belonging to the specified test cases will be uploaded.</span></span>

##### <a name="examples"></a><span data-ttu-id="549c6-326">Exempel</span><span class="sxs-lookup"><span data-stu-id="549c6-326">Examples</span></span>
``uploadrecording 123``  
``uploadrecording 123 456``


#### <a name="usage"></a><span data-ttu-id="549c6-327">användning</span><span class="sxs-lookup"><span data-stu-id="549c6-327">usage</span></span>
<span data-ttu-id="549c6-328">Visar två sätt att anropa det här programmet: ett som använder en standardinställningsfil, ett annat som en inställningsfil.</span><span class="sxs-lookup"><span data-stu-id="549c6-328">Shows two ways to invoke this application: one using a default setting file, another one providing a setting file.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``usage``**


### <a name="windows-powershell-examples"></a><span data-ttu-id="549c6-329">Windows PowerShell-exempel</span><span class="sxs-lookup"><span data-stu-id="549c6-329">Windows PowerShell examples</span></span>

[!IMPORTANT] <span data-ttu-id="549c6-330">Exempelskripten nedan tillhandahålls i befintligt skick för illustration och stöds inte av Microsoft.</span><span class="sxs-lookup"><span data-stu-id="549c6-330">The example scripts below are provided AS IS for illustration purposes and are not supported by Microsoft.</span></span>

#### <a name="run-a-test-case-in-a-loop"></a><span data-ttu-id="549c6-331">Kör ett testfall i en slinga</span><span class="sxs-lookup"><span data-stu-id="549c6-331">Run a test case in a loop</span></span>

<span data-ttu-id="549c6-332">Du har ett testskript som skapar en ny kund.</span><span class="sxs-lookup"><span data-stu-id="549c6-332">You have a test script that creates a new customer.</span></span> <span data-ttu-id="549c6-333">Via skript kan det här testfallet köras i en slinga genom att göra slumpmässiga följandande data innan varje iteration körs:</span><span class="sxs-lookup"><span data-stu-id="549c6-333">Via scripting, this test case can be run in a loop by randomizing the following data before each iteration is run:</span></span>

- <span data-ttu-id="549c6-334">Kund-ID</span><span class="sxs-lookup"><span data-stu-id="549c6-334">Customer ID</span></span>
- <span data-ttu-id="549c6-335">Kundnamn</span><span class="sxs-lookup"><span data-stu-id="549c6-335">Customer name</span></span>
- <span data-ttu-id="549c6-336">Adress till kund</span><span class="sxs-lookup"><span data-stu-id="549c6-336">Customer address</span></span>

<span data-ttu-id="549c6-337">Kund-ID:t anges i formatet *ATCUS\<nummer\>*, där \<nummer\> är ett värde mellan **000000001** och **999999999**.</span><span class="sxs-lookup"><span data-stu-id="549c6-337">The customer ID will be in the format *ATCUS\<number\>*, where \<number\> is a value between **000000001** and **999999999**.</span></span>

<span data-ttu-id="549c6-338">I följande exempel används en parameter, **Start**för att definiera det första numret som används.</span><span class="sxs-lookup"><span data-stu-id="549c6-338">The following example uses one parameter, **start**, to define the first number that is used.</span></span> <span data-ttu-id="549c6-339">Det använder en andra parameter, **nr**, för att definiera antalet kunder som måste skapas.</span><span class="sxs-lookup"><span data-stu-id="549c6-339">Is uses a second parameter, **nr**, to define the number of customers that must be created.</span></span> <span data-ttu-id="549c6-340">För varje upprepning ändras parametrarna i Excel-parameterfil med hjälp av en UpdateCustomer-funktion.</span><span class="sxs-lookup"><span data-stu-id="549c6-340">For each iteration, the parameters in the Excel parameter file are changed by using an UpdateCustomer function.</span></span> <span data-ttu-id="549c6-341">Då anropas kommando raden för RSAT i en RunTestCase-funktion.</span><span class="sxs-lookup"><span data-stu-id="549c6-341">Then the RSAT command line is called in a RunTestCase function.</span></span>

<span data-ttu-id="549c6-342">Öppna Microsoft Windows PowerShell ISE (Integrated Scripting Environment) i administrationsläge och klistra in följande kod i fönstret med namnet **Untitled1.ps1**.</span><span class="sxs-lookup"><span data-stu-id="549c6-342">Open Microsoft Windows PowerShell Integrated Scripting Environment (ISE) in admin mode, and paste the following code into the window that is named **Untitled1.ps1**.</span></span>

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
$excelFilename = "full path to Excel parameter file"
l$sheetName = "DirPartyQuickCreateForm"
for ($i = $start; $i -lt $start + $nr; $i++ )
{
    $CustomerId = $i.ToString("000000000")
    Write-Host "customer : " $CustomerId
    UpdateCustomer $excelFilename $sheetName $CustomerId
    RunTestCase $excelFilename
```

#### <a name="run-a-script-that-depends-on-data-in-microsoft-dynamics-365"></a><span data-ttu-id="549c6-343">Köra ett skript som är beroende av data i Microsoft Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="549c6-343">Run a script that depends on data in Microsoft Dynamics 365</span></span>

<span data-ttu-id="549c6-344">I följande exempel används ett OData-anrop (Open Data Protocol) för att hitta orderstatusen för en inköpsorder.</span><span class="sxs-lookup"><span data-stu-id="549c6-344">The following example uses an Open Data Protocol (OData) call to find the order status of a purchase order.</span></span> <span data-ttu-id="549c6-345">Om statusvärdet inte har **fakturerats** kan du t.ex. anropa ett testfall för RSAT som bokför fakturan.</span><span class="sxs-lookup"><span data-stu-id="549c6-345">If the status isn't **invoiced**, you can, for example, call an RSAT test case that posts the invoice.</span></span>

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
