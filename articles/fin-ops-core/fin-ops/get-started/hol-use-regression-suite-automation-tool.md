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
ms.openlocfilehash: 9afa98156c58d10c19454430769a3d60343661dc
ms.sourcegitcommit: 75db3b75d35d27034f9b56e7119c9d0cb7666830
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/03/2019
ms.locfileid: "2550967"
---
# <a name="use-the-regression-suite-automation-tool-tutorial"></a>Använda självstudie för Regression Suite Automation Tool

[!include [banner](../includes/banner.md)]

> [!NOTE]
> Använd webbläsarverktygen för att hämta och spara sidan i PDF-format. 

I den här vägledningen får du hjälp med några av de avancerade funktionerna i RSAT (Regression Suite Automation Tool), inkluderar en demotilldelning och beskriver strategi- och nyckelutbildningspunkter.

## <a name="features-of-rsattask-recorder"></a>Funktioner av RSAT/Uppgiftsregistrering

### <a name="validate-a-field-value"></a>Validera fältvärdet

Mer information om den här funktionen finns i [skapa en ny uppgiftsregistrering som har en Validera-funktion](./hol-set-up-regression-suite-automation-tool.md#create-a-new-task-recording-that-has-a-validate-function).

### <a name="saved-variable"></a>Sparad variabel

Mer information om den här funktionen finns i [ändra en befintlig uppgiftsregistrering och skapa en sparad variabel](./hol-set-up-regression-suite-automation-tool.md#modify-an-existing-task-recording-to-create-a-saved-variable).

### <a name="derived-test-case"></a>Härlett testfall

1. Öppna verktyget RSAT (Regression Suite Automation Tool) och markera båda testärenden som du har skapat i [konfigurera och installera Regression Suite Automation Tool](./hol-set-up-regression-suite-automation-tool.md).
2. Välj **ny \> skapa härlett testfall**.

    ![Kommandot Skapa härlett testfallkommando på den nya menyn](./media/use_rsa_tool_01.png)

3. Ett meddelande visas om att ett härlett testfall kommer att skapas för varje valt testfall i det aktuella testpaketet och att varje härlett testfall har en egen kopia av Excel-parameterfilen. Välj **OK**.

    > [!NOTE]
    > När du kör ett härlett testfall använder det uppgiftsinspelningen av det överordnade testfallet och den egna kopian av Excel-parameterfilen. På så sätt kan du köra samma test med olika parametrar utan att behöva underhålla fler än en uppgiftsinspelning. Ett härlett testfall behöver inte vara en del av samma testserie som det överordnade testfallet.

    ![Meddelanderuta](./media/use_rsa_tool_02.png)

    Två ytterligare härledda testfall skapas och kryssrutan **härledda?** markeras för dem.

    ![Härledda testfall har skapats](./media/use_rsa_tool_03.png)

    Ett härlett testfall skapas automatiskt i Azure DevOps. Det är ett underordnat objekt till testfallet **skapa en ny produkt** och märks med ett särskilt nyckelord: **RSAT:DerivedTestSteps**. Dessa testfall läggs också automatiskt till i testplanen i Azure DevOps.

    ![RSAT:DerivedTestSteps-nyckelord](./media/use_rsa_tool_04.png)

    > [!NOTE]
    > Om de härledda testfallet som skapas inte finns i rätt ordning går du till Azure DevOps och beställer testfallen igen i testpaketet så att RSAT kan köras i rätt ordning.

4. Markera de härledda testfall och välj sedan **redigera** för att öppna motsvarande Excel-parameterfiler.
5. Redigera dessa Excel-parametervärden på samma sätt som du redigerade de överordnade filerna. Med andra ord måste du se till att produkt-ID:t är inställt så att det skapas automatiskt. Kontrollera också att den sparade variabeln kopieras till relevanta fält.
6. På fliken **allmänt** i båda Excel-parameterfiler uppdaterar du värdet för fältet **företag** till **Ussi**, så att de härledda testfallen kan köras mot en annan juridisk person än det överordnade testfallet. Om du vill köra testfall mot mot en viss användare (eller den roll som är associerad med en viss användare) kan du uppdatera värdet i fältet **testanvändare.**
7. Välj **kör**och validera att produkten har skapats i både den USMF juridiska personen och den USSI juridiska personen.

### <a name="validate-notifications"></a>Validera meddelanden

Den här funktionen kan användas för att validera om en åtgärd utförts. När till exempel en tillverkningsorder skapas, uppskattas och sedan startas, visar appen meddelandet "produktion – start" för att meddela dig att tillverkningsordern har startats.

![Produktion - starta meddelande](./media/use_rsa_tool_05.png)

Du kan validera det här meddelandet genom RSAT genom att ange meddelande texten på fliken **MessageValidation** i Excel-parameterfilen för lämplig inspelning.

![Fliken Meddelandevalidering](./media/use_rsa_tool_06.png)

När testfallet har körts, jämförs meddelandet i Excel-parameterfilen i det meddelande som visas. Om meddelandena inte matchar kommer testfallet att misslyckas.

> [!NOTE]
> Du kan ange mer än ett meddelande på fliken **MessageValidation** i Excel-parameterfilen. Meddelandena kan också vara fel- eller varningsmeddelanden i stället för informationsmeddelanden.

### <a name="validate-values-by-using-operators"></a>Validera värden med hjälp av operatörer

I tidigare versioner av RSAT kunde du bara validera värden om ett kontrollvärde är lika med ett förväntat värde. Med den nya funktionen kan du validera att en variabel inte är lika med, är mindre än eller mer än ett angivet värde.

- Om du vill använda den här funktionen öppnar du filen **Microsoft.Dynamics.RegressionSuite.WindowsApp.exe.config** under RSAT-installationsmappen (t.ex. **C:\\programfiler (x86)\\Regression Suite Automation Tool**) och ändrar värdet i följande element från **falskt** till **sant**.

    ```
    <add key="AddOperatorFieldsToExcelValidation" value="false" />
    ```

    I Excel-parameterfilen visas ett nytt fält med **operatör**.

    > [!NOTE]
    > Om du har använt en äldre version av RSAT måste du generera nya Excel-parameterstyrda filer.

    ![Fältet Operatör](./media/use_rsa_tool_07.png)

I följande exempel visas hur du kan använda den här funktionen för att validera om lagerbehållningen är större än 0 (noll).

1. I demonstrationsdata i **USMF**-företaget skapar du en uppgiftsregistrering med följande steg:

    1. Gå till **Produktinformationshantering \> Produkter \> Frisläppta produkter**.
    2. Använd snabbfiltret för att söka efter poster. Filtrera till exempel i fältet **Artikelnummer** med värdet **1000**.
    3. Välj **lagerbehållning**
    4. Använd snabbfiltret för att söka efter poster. Filtrera till exempel på värdet **1** i fältet **Plats**.
    5. Markera vald rad i listan.
    6. Validera att värdet i fältet **totala tillgängliga** är **411,0000000000000000**.

2. Spara uppgiftsinspelningen till BPM-bibliotek i LCS och synkronisera den till Azure DevOps.
3. Lägg till testfallet testplanen och läs in testfallet i RSAT.
4. Öppna Excel-parameterfilen. På fliken **InventOnhandItem** visas avsnittet **validera InventOnhandItem** som innehåller fältet **Operatör**.

    ![Fältet Operatör](./media/use_rsa_tool_08.png)

5. Om du vill validera om lagerbehållningen alltid är större än 0 ändrar du värdet i fältet **värde** från **411** till **0** och värdet för fältet **Operatör** från ett likhetstecken (**=**) till ett större än-tecken (**\>**).

    ![Värden för fälten värde och operatör har ändrats](./media/use_rsa_tool_09.png)

6. Spara och stäng Excel-parameterfilen.
7. Välj **överför** om du vill spara ändringarna som du gjorde i Excel-parameterfilen till Azure DevOps.

Om värdet för fältet **totalt tillgängliga** för den angivna artikeln i lagret är högre än 0 (noll), kommer testerna att lyckas, oavsett det faktiska lagerbehållningsvärdet.

### <a name="generator-logs"></a>Generatorloggar

Med den här funktionen skapas en mapp som innehåller loggarna för de testfall som har körts.

- Om du vill använda den här funktionen öppnar du filen **Microsoft.Dynamics.RegressionSuite.WindowsApp.exe.config** under RSAT-installationsmappen (t.ex. **C:\\programfiler (x86)\\Regression Suite Automation Tool**) och ändrar värdet i följande element från **falskt** till **sant**.

    ```
    <add key="LogGeneration" value="false" />
    ```

När testfallen har körts kan du hitta loggfilerna under **C:\\användare\\\<användarnamn\>\\AppData\\roaming\\regressionTool\\generatorLogs**.

![GeneratorLogs-mappen](./media/use_rsa_tool_10.png)

> [!NOTE]
> Om det finns existerande testfall innan du ändrade värdet i .config-filen, kommer inga loggar att genereras för dessa tester förrän du har genererat nya testkörningsfiler.
> 
> ![Generera kommandot endast textexekveringar på menyn Ny](./media/use_rsa_tool_11.png)

### <a name="snapshot"></a>Ögonblicksbild

Den här funktionen tar skärmbilder av de steg som har utförts under uppgiftsregistreringen.

- Om du vill använda den här funktionen öppnar du filen **Microsoft.Dynamics.RegressionSuite.WindowsApp.exe.config** under RSAT-installationsmappen (t.ex. **C:\\programfiler (x86)\\Regression Suite Automation Tool**) och ändrar värdet i följande element från **falskt** till **sant**.

    ```
    <add key="VerboseSnapshotsEnabled" value="false" />
    ```

Under **C:\\användare\\\<användarnamn\>\\AppData\\Roaming\\regressionTool\\uppspelning**, skapas en separat mapp för varje testfall som körs.

![Mappen ögonblicksbild för ett testfall](./media/use_rsa_tool_12.png)

I var och en av dessa mappar kan du söka efter ögonblicksbilder av stegen som utfördes medan testerna kördes.

![Ögonblicksbildfiler](./media/use_rsa_tool_13.png)

## <a name="assignment"></a>Tilldelning

### <a name="scenario"></a>Scenario

1. Produktdesignern skapar en ny frisläppt produkt.
2. Produktionschefen initierar en tillverkningsorder för att ta med lagernivån till två delar.
3. Produktion startar och avslutar produktionsordern och verifierar att lagerkvantiteten är två enheter.
4. Försäljningsteamet får en på fyra enheter av den nya produkten. Därför uppdaterar försäljningsteamet nettokraven via den dynamiska planen. Eftersom ingen ytterligare kapacitet finns tillgänglig, anges standardorderprincipen till köp istället för tillverka. Därför kapas en planerad inköpsorder.
5. Köparen lägger till en leverantör, signerar den planerade inköpsordern och bekräftar sedan inköpsordern.
6. När varorna som köpts in anländer till butiken söker butiksoperatören efter den relaterade inköpsordern och tar emot varorna. Eftersom ordern nu är slutförd kan varor plockas och förpackas mot försäljningsordern.
7. Ekonomi bokför inköpsfakturan och försäljningsfakturan.

Följande bild visar flödet för det här scenariot.

![Flöde för demoscenariot](./media/use_rsa_tool_14.png)

Följande bild visar affärsprocesser för det här scenariot i RSAT.

![Affärsprocesser för demoscenariot](./media/use_rsa_tool_15.png)

## <a name="strategy--key-learning"></a>Strategi – viktiga utbildningsmaterial

### <a name="data"></a>Data

- Se till att du har representativa datavolymer (en kopia av produktions- och gyllene konfigurationsdata plus migrerade data).
- När du genererar nya data via uppgiftsregistrering ska du skapa testnamn som inte är i konflikt med befintliga namn (du kan till exempel använda prefix som **RSATxxx**).
- Använd Azure tidpunktsåterställning för att köra om tester på andra miljöer än icke-nivå 1.
- Även om du kan använda Excel-funktionerna **SLUMPMÄSSIGA** och **NU** för att generera en unik kombination, är arbetsinsatsen betydligt hög. Här är ett exempel:

    ```
    product = "AT" &TEXT(NOW(),"yyymmddhhmm")
    ```

### <a name="task-recorder"></a>Uppgiftsregistrering

- Definiera scenarier innan du startar inspelningen. Ett välhanterat projekt har fördefinierade testscenarier. Om du vill bygga ett testfall bör du överväga hur förutsägbara resultatet av testscenarierna är.
- Dela upp inspelningar om de utförs av olika roller eller om det finns väntetid eller extern händelse före nästa steg.
- Undvik att markera värden i listor. Använd i stället textformat, t.ex. **FIFO**. **AudioRM** och **SiteWH**. När du väljer i en lista registreras placeringen av värdet i listan, inte själva värdet. Om du lägger till objekt i listan kan placeringen av värdet ändras. Därför kommer din registrering att använda en annan parameter och resten av scenariot kan påverkas.
- Tänk på hur flera användare fungerar. Antag till exempel inte att den nya försäljningsordern alltid väljs automatiskt. I stället ska du alltid använda filtret för att hitta rätt ordning.
- Använd kopieringsfunktionen i uppgiftsinspelning om du vill spara namnet på en nyskapad produkt så att den kan användas i kedjade testfall.
- Använd funktionen validera i uppgiftsregistrering om du vill ställa in kontrollpunkter som verifierar att stegen har körts på rätt sätt.

### <a name="rsat"></a>RSAT

- Om du vill köra testet i ett annat företag kan du ändra företaget på fliken **allmänt** i Excel-parameterfilen. Kontrollera att inställningar och data är tillgängliga i det valda företaget.
- Du kan ändra testanvändaren på fliken **allmänt** i Excel-parameterfilen. Ange e-post-ID för den användare som ska köra test fallet. På så sätt kan testfallet köras med hjälp av den angivna användarens säkerhetsbehörigheter.
- Om du vill vänta innan testet påbörjas kan du definiera en paus på fliken **allmänt** i Excel-parameterfilen. Denna paus kan användas i ett batchjobb (t.ex. om ett arbetsflöde måste köras innan nästa steg kan utföras.)

## <a name="advanced-scripting"></a>Avancerade skript

### <a name="command-line"></a>Kommandorad

RSAT kan anropas från fönstret **kommandotolk**.

> [!NOTE]
> Kontrollera att miljövariabeln **TestRoot** anges till RSAT installationens sökväg. (I Microsoft Windows, öppna **kontrollkontroll**, välj **Systemoch säkerhet \> System \> Avancerade systeminställningar** och välj sedan **miljövariabler**.)

1. Öppna ett **kommandotolk**-fönster som en adminstratör.
2. Kör verktyget från installationskatalogen.

    ```
    cd "c:\Program Files (x86)\Regression Suite Automation Tool\"
    ```

3. Lista alla kommandon.

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

### <a name="windows-powershell-examples"></a>Windows PowerShell-exempel

#### <a name="run-a-test-case-in-a-loop"></a>Kör ett testfall i en slinga

Du har ett testskript som skapar en ny kund. Via skript kan det här testfallet köras i en slinga genom att göra slumpmässiga följandande data innan varje iteration körs:

- Kund-ID
- Kundnamn
- Adress till kund

Kund-ID:t anges i formatet *ATCUS\<nummer\>*, där \<nummer\> är ett värde mellan **000000001** och **999999999**.

I följande exempel används en parameter, **Start**för att definiera det första numret som används. Det använder en andra parameter, **nr**, för att definiera antalet kunder som måste skapas. För varje upprepning ändras parametrarna i Excel-parameterfil med hjälp av en UpdateCustomer-funktion. Då anropas kommando raden för RSAT i en RunTestCase-funktion.

Öppna Microsoft Windows PowerShell ISE (Integrated Scripting Environment) i administrationsläge och klistra in följande kod i fönstret med namnet **Untitled1.ps1**.

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

#### <a name="run-a-script-that-depends-on-data-in-microsoft-dynamics-365"></a>Köra ett skript som är beroende av data i Microsoft Dynamics 365

I följande exempel används ett OData-anrop (Open Data Protocol) för att hitta orderstatusen för en inköpsorder. Om statusvärdet inte har **fakturerats** kan du t.ex. anropa ett testfall för RSAT som bokför fakturan.

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
