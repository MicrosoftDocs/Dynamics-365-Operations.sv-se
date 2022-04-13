---
title: Självstudie för Regression Suite Automation Tool
description: Det här avsnittet visar hur du använder RSAT (Regression Suite Automation Tool). Den beskriver olika funktioner och ger exempel som använder avancerad skriptanvändning.
author: FrankDahl
ms.date: 09/23/2021
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: tfehr
ms.search.region: Global
ms.author: fdahl
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: AX 7.0.0, Operations
ms.openlocfilehash: e2273aefb98880a1ae746ef7ec65b4f2262f3560
ms.sourcegitcommit: 49c97b0c94e916db5efca5672d85df70c3450755
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/29/2022
ms.locfileid: "8492932"
---
# <a name="regression-suite-automation-tool-tutorial"></a>Självstudie för Regression Suite Automation Tool

[!include [banner](../../includes/banner.md)]

> [!NOTE]
> Använd webbläsarverktygen för att hämta och spara sidan i PDF-format.

I den här vägledningen får du hjälp med några av de avancerade funktionerna i RSAT (Regression Suite Automation Tool), inkluderar en demotilldelning och beskriver strategi- och nyckelutbildningspunkter.

## <a name="notable-features-of-rsat-and-task-recorder"></a>Viktiga funktioner för RSAT och uppgiftsinspelning

### <a name="validate-a-field-value"></a>Validera fältvärdet

Med RSAT kan du inkludera valideringssteg i testärendet för att validera förväntade värden. Mer information om den här funktionen finns i artikeln [validera förväntade värden](rsat-validate-expected.md).

I följande exempel visas hur du kan använda den här funktionen för att validera om lagerbehållningen är större än 0 (noll).

1. I demonstrationsdata i **USMF**-företaget skapar du en uppgiftsregistrering med följande steg:

    1. Gå till **Produktinformationshantering \> Produkter \> Frisläppta produkter**.
    2. Använd snabbfiltret för att söka efter poster. Filtrera till exempel i fältet **Artikelnummer** med värdet **1000**.
    3. Välj **lagerbehållning**
    4. Använd snabbfiltret för att söka efter poster. Filtrera till exempel på värdet **1** i fältet **Plats**.
    5. Markera vald rad i listan.
    6. Validera att värdet i fältet **totala tillgängliga** är **411,0000000000000000**.

2. Spara uppgiftsinspelningen som **utvecklingsregistrering** och koppla den till ditt testfall i Azure DevOps.
3. Lägg till testfallet testplanen och läs in testfallet i RSAT.
4. Öppna Excel-parameterfilen och gå till fliken **TestCaseSteps**.
5. Om du vill validera om lagerbehållningen alltid kommer att vara över **0**, gå till steget **Validera totalt tillgängligt** och ändrar värdet från **411** till **0**. Ändra värdet i fältet **Operatör** till ett lika med-tecken (**=**) till ett större än-tecken (**\>**).
6. Spara och stäng Excel-parameterfilen.
7. Välj **överför** om du vill spara ändringarna som du gjorde i Excel-parameterfilen till Azure DevOps.

Om värdet för fältet **totalt tillgängliga** för den angivna artikeln i lagret är högre än 0 (noll), kommer testerna att lyckas, oavsett det faktiska lagerbehållningsvärdet.

### <a name="saved-variables-and-chaining-of-test-cases"></a>Sparade variabler och kedjor för testärenden

En nyckelegenskap i RSAT är en kedja av testfall, det vill säga förmågan hos ett test för att överföra variabler till andra tester. Mer information finns i artikeln [kopiera variabler för att kedja testärenden](rsat-chain-test-cases.md).

### <a name="derived-test-case"></a>Härlett testfall

Med RSAT kan du använda samma uppgiftsinspelning med flera testärenden, vilket gör att en uppgift kan köras med olika datakonfigurationer. Mer information finns i artikeln [härledda testärenden](rsat-derived-test-cases.md).

### <a name="validate-notifications-and-messages"></a>Validera aviseringar och meddelanden

Den här funktionen kan användas för att validera om en åtgärd utförts. När till exempel en tillverkningsorder skapas, uppskattas och sedan startas, visar appen meddelandet "produktion – start" för att meddela dig att tillverkningsordern har startats.

![Produktion – Startameddelande.](./media/use_rsa_tool_05.png)

Du kan validera det här meddelandet genom RSAT genom att ange meddelande texten på fliken **MessageValidation** i Excel-parameterfilen för lämplig inspelning.

![Fliken Meddelandevalidering.](./media/use_rsa_tool_06.png)

När testfallet har körts, jämförs meddelandet i Excel-parameterfilen i det meddelande som visas. Om meddelandena inte matchar kommer testfallet att misslyckas.

> [!NOTE]
> Du kan ange mer än ett meddelande på fliken **MessageValidation** i Excel-parameterfilen. Meddelandena kan också vara fel- eller varningsmeddelanden i stället för informationsmeddelanden.

### <a name="snapshot"></a>Ögonblicksbild

Den här funktionen tar skärmbilder av de steg som har utförts under uppgiftsregistreringen. Den är användbar för granskning och felsökning.

- Om du vill använda den här funktionen medan du kör RSAT med användargränssnittet öppnar du filen **Microsoft.Dynamics.RegressionSuite.WindowsApp.exe.config** under RSAT-installationsmappen (t.ex. **C:\\programfiler (x86)\\Regression Suite Automation Tool**) och ändrar värdet i följande element från **falskt** till **sant**.

    ```xml
    <add key="VerboseSnapshotsEnabled" value="false" />
    ```

- Om du vill använda den här funktionen medan du kör RSAT med CLI (t.ex. Azure DevOps) öppnar du filen **Microsoft.Dynamics.RegressionSuite.ConsoleApp.exe.config** under RSAT-installationsmappen (t.ex. **C:\\programfiler (x86)\\Regression Suite Automation Tool**) och ändrar värdet i följande element från **falskt** till **sant**.

    ```xml
    <add key="VerboseSnapshotsEnabled" value="false" />
    ```

När du kör testärendet genererar RSAT ögonblicksbilder (bilder) av stegen och sparar dem i mappen uppspelning i testärenden i arbetskatalogen. I den mapp som innehåller en mapp skapas en separat undermapp med namnet **StepSnapshots**.  Mappen innehåller ögonblicksbilder för testärenden som körs.

## <a name="assignment"></a>Uppdrag

### <a name="scenario"></a>Scenario

1. Produktdesignern skapar en ny frisläppt produkt.
2. Produktionschefen initierar en tillverkningsorder för att ta med lagernivån till två delar.
3. Produktion startar och avslutar produktionsordern och verifierar att lagerkvantiteten är två enheter.
4. Försäljningsteamet får en på fyra enheter av den nya produkten. Därför uppdaterar försäljningsteamet nettokraven via den dynamiska planen. Eftersom ingen ytterligare kapacitet finns tillgänglig, anges standardorderprincipen till köp istället för tillverka. Därför kapas en planerad inköpsorder.
5. Köparen lägger till en leverantör, signerar den planerade inköpsordern och bekräftar sedan inköpsordern.
6. När varorna som köpts in anländer till butiken söker butiksoperatören efter den relaterade inköpsordern och tar emot varorna. Eftersom ordern nu är slutförd kan varor plockas och förpackas mot försäljningsordern.
7. Finance bokför inköpsfakturan och försäljningsfakturan.

Följande bild visar flödet för det här scenariot.

![Flöde för demoscenariot.](./media/use_rsa_tool_14.png)

Följande bild visar hierarkin för affärsprocesser för det här scenariot i LCS affärsprocessmodelleraren.

![Affärsprocesser för demoscenariot.](./media/use_rsa_tool_15.png)

## <a name="strategy--key-learning"></a>Strategi – viktiga utbildningsmaterial

### <a name="data"></a>Data

- Se till att du har representativa datavolymer (en kopia av produktions- och gyllene konfigurationsdata plus migrerade data).
- När du genererar nya data via uppgiftsregistrering ska du skapa testnamn som inte är i konflikt med befintliga namn (du kan till exempel använda prefix som **RSATxxx**).
- Använd Azure tidpunktsåterställning för att köra om tester på andra miljöer än icke-nivå 1.
- Även om du kan använda Excel-funktionerna **SLUMPMÄSSIGA** och **NU** för att generera en unik kombination, är arbetsinsatsen betydligt hög. Här är ett exempel:

    ```Excel
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

### <a name="cli"></a>CLI

RSAT kan anropas från fönstret **kommandotolk** eller **PowerShell**.

> [!NOTE]
> Kontrollera att miljövariabeln **TestRoot** anges till RSAT installationens sökväg. (I Microsoft Windows, öppna **kontrollkontroll**, välj **Systemoch säkerhet \> System \> Avancerade systeminställningar** och välj sedan **miljövariabler**.)

1. Öppna ett **kommandotolk** eller **PowerShell** som admin.
2. Navigera till installationskatalogen för RSAT.

    ```Console
    cd "c:\Program Files (x86)\Regression Suite Automation Tool\"
    ```

3. Lista alla kommandon.

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
        downloadsuite
        edit
        generate
        generatederived
        generatetestonly
        generatetestsuite
        help
        list
        listtestplans
        listtestsuite
        listtestsuitebyid
        listtestsuitenames
        playback
        playbackbyid
        playbackmany
        playbacksuite
        playbacksuitebyid
        quit
        upload
        uploadrecording
        usage
    ```

#### <a name=""></a>?

Listar alla kommandon eller visar hjälp för ett specifikt kommando, tillsammans med tillgängliga parametrar.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``?``**``[command]``

##### <a name="-optional-parameters"></a>?: Valfria parametrar

`command`: Var ``[command]`` finns ett av kommandona i den föregående listan.

#### <a name="about"></a>om

Visar versionen av den installerade RSAT.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``about``**

#### <a name="cls"></a>cls

Rensar skärmen.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``cls``**

#### <a name="download"></a>hämta

Laddar ned bilagor (inspelnings-, körnings- och parameterfiler) för det angivna testfallet från Azure DevOps i utdatapanelen. Du kan använda kommandot ``list`` för att få alla tillgängliga testfall, och använda alla värden från den första kolumnen som **test_case_id** parameter.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``download``**``[/retry[=<seconds>]] [test_case_id] [output_dir]``

##### <a name="download-optional-switches"></a>hämtning: valfria växlingar

+ `/retry[=seconds]`: Om denna switch är angiven, och falltestfall spärras av andra RSAT-instanser, väntar hämtningsprocessen angivet antal sekunder och sedan försöker du en gång till. Standardmallvärdet är \[sekunder\] är 120 sekunder. Om du inte använder denna växel kommer processen att avbrytas omedelbart om testfallen är spärrade.

##### <a name="download-required-parameters"></a>hämtning: parametrar som krävs

+ `test_case_id` Representerar ID för testärende.

##### <a name="download-optional-parameters"></a>nedladdning: valfria parametrar

+ `output_dir` Representerar katalogen för arbetskatalogen. Katalogen måste finnas. Arbetskatalogen från inställningarna används om den här parametern inte har angetts.

##### <a name="download-examples"></a>hämta: exempel

`download 123 c:\temp\rsat`

`download /retry=240 765`

#### <a name="downloadsuite"></a>downloadsuite

Laddar ned bilagor (inspelnings-, körnings- och parameterfiler) för alla testfall i den angivna testsviten från Azure DevOps i utdatapanelen. Du kan använda kommandot ``listtestsuitenames`` för att få alla tillgängliga testsviter och använd valfritt värde som en **test_suite_name** parameter.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``downloadsuite``**``[/retry[=<seconds>]] ([test_suite_name] | [/byid] [test_suite_id]) [output_dir]``

##### <a name="downloadsuite-optional-switches"></a>downloadsuite: valfria växlingar

+ `/retry[=seconds]`: Om denna switch är angiven, och falltestfall spärras av andra RSAT-instanser, väntar hämtningsprocessen angivet antal sekunder och sedan försöker du en gång till. Standardmallvärdet är \[sekunder\] är 120 sekunder. Om du inte använder denna växel kommer processen att avbrytas omedelbart om testfallen är spärrade.
+ `/byid`: Denna växel anger att den önskade testsviten identifieras med sitt Azure DevOps ID i stället för namnet på testsviten.

##### <a name="downloadsuite-required-parameters"></a>downloadsuite: parametrar som krävs

+ `test_suite_name`: Representerar testpaketets namn. Denna parameter är nödvändig om /byid-växeln **inte** har angetts. Detta är testsvitens Azure DevOps namn.
+ `test_suite_id`: Representerar ID för testpaketet. Denna parameter är nödvändig om /byid-växeln **är** har angetts. Detta ID är testsvit-ID Azure DevOps.

##### <a name="downloadsuite-optional-parameters"></a>downloadsuite: valfria parametrar

+ `output_dir` Representerar katalogen för arbetskatalogen. Katalogen måste finnas. Arbetskatalogen från inställningarna används om den här parametern inte har angetts.

##### <a name="downloadsuite-examples"></a>downloadsuite: exempel

`downloadsuite NameOfTheSuite c:\temp\rsat`

`downloadsuite /byid 123 c:\temp\rsat`

`downloadsuite /retry=240 /byid 765`

`downloadsuite /retry=240 /byid 765 c:\temp\rsat`

#### <a name="edit"></a>redigera

Gör att du kan öppna parameter filen i Excel-programmet och redigera den.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``edit``**``[excel_file]``

##### <a name="edit-required-parameters"></a>redigera: obligatoriska parametrar

+ `excel_file`: Måste innehålla en fullständig sökväg till en befintlig Excel-fil.

##### <a name="edit-examples"></a>redigera: exempel

`edit c:\RSAT\123\TestCase_123_Base.xlsx`

`edit e:\temp\TestCase_456_Base.xlsx`

#### <a name="generate"></a>skapa

Skapar test körnings- och parametervärden för det angivna testärendet i utdatapanelen. Du kan använda ``list`` kommandot för att hämta alla tillgängliga testärenden. Använd valfritt värde från den första kolumnen som en **test_case_id** parameter.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``generate``**``[/retry[=<seconds>]] [/dllonly] [/keepcustomexcel] [test_case_id] [output_dir]``

##### <a name="generate-optional-switches"></a>generera: valfria växlar

+ `/retry[=seconds]`: Om denna switch är angiven, och falltestfall spärras av andra RSAT-instanser, väntar genereringsprocessen angivet antal sekunder och sedan försöker du en gång till. Standardmallvärdet är \[sekunder\] är 120 sekunder. Om du inte använder denna växel kommer processen att avbrytas omedelbart om testfallen är spärrade.
+ `/dllonly`: Generera endast testkörningsfiler. Återskapa inte Excel-parameterfilen.
+ `/keepcustomexcel`: Uppgradera den befintliga parameterfilen. Generera också om körningsfiler.

##### <a name="generate-required-parameters"></a>generera: obligatoriska parametrar

+ `test_case_id` Representerar ID för testärende.

##### <a name="generate-optional-parameters"></a>generera: valfria parametrar

+ `output_dir` Representerar katalogen för arbetskatalogen. Katalogen måste finnas. Arbetskatalogen från inställningarna används om den här parametern inte har angetts.

##### <a name="generate-examples"></a>genererar: exempel

`generate 123 c:\temp\rsat`

`generate /retry=240 765 c:\rsat\last`

`generate /retry=240 /dllonly 765`

`generate /retry=240 /keepcustomexcel 765`

#### <a name="generatederived"></a>generatederived

Genererar ett nytt härlett testfall (underordnat testfall) av det angivna testfallet. Det nya testfallet läggs också till i den angivna testsviten. Du kan använda kommandot ``list`` för att få alla tillgängliga testfall, och använda alla värden från den första kolumnen som **test_case_id** parameter.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``generatederived``**``[/retry[=<seconds>]] [parent_test_case_id] [test_plan_id] [test_suite_id]``

##### <a name="generatederived-optional-switches"></a>generatederived: valfria växlar

+ `/retry[=seconds]`: Om denna switch är angiven, och falltestfall spärras av andra RSAT-instanser, väntar genereringsprocessen angivet antal sekunder och sedan försöker du en gång till. Standardmallvärdet är \[sekunder\] är 120 sekunder. Om du inte använder denna växel kommer processen att avbrytas omedelbart om testfallen är spärrade.

##### <a name="generatederived-required-parameters"></a>generatederived: obligatoriska parametrar

+ `parent_test_case_id`: Representerar överordnat ID för testärende.
+ `test_plan_id`: Representerar ID för testplan.
+ `test_suite_id`: Representerar ID för testpaketet.

##### <a name="generatederived-examples"></a>generatederived: exempel

`generatederived 123 8901 678`

`generatederived /retry 123 8901 678`

#### <a name="generatetestonly"></a>generatetestonly

Skapar endast test körningsfil för det angivna testärendet. Det genererar inte Excel-parameterfilen. Filerna genereras i den angivna utdatakatalogen. Du kan använda kommandot ``list`` för att få alla tillgängliga testfall, och använda alla värden från den första kolumnen som **test_case_id** parameter.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``generatetestonly``**``[/retry[=<seconds>]] [test_case_id] [output_dir]``

##### <a name="generatetestonly-optional-switches"></a>generatetestonly: valfria växlar

+ `/retry[=seconds]`: Om denna switch är angiven, och falltestfall spärras av andra RSAT-instanser, väntar genereringsprocessen angivet antal sekunder och sedan försöker du en gång till. Standardmallvärdet är \[sekunder\] är 120 sekunder. Om du inte använder denna växel kommer processen att avbrytas omedelbart om testfallen är spärrade.

##### <a name="generatetestonly-required-parameters"></a>generatetestonly: obligatoriska parametrar

+ `test_case_id` Representerar ID för testärende.

##### <a name="generatetestonly-optional-parameters"></a>generatetestonly: valfria parametrar

+ `output_dir` Representerar katalogen för arbetskatalogen. Katalogen måste finnas. Arbetskatalogen från inställningarna används om den här parametern inte har angetts.

##### <a name="generatetestonly-examples"></a>generatetestonly: exempel

`generatetestonly 123 c:\temp\rsat`

`generatetestonly /retry=240 765`

#### <a name="generatetestsuite"></a>generatetestsuite

Genererar testautomatiseringsfiler för alla testfall i den angivna testsviten. Du kan använda kommandot ``listtestsuitenames`` för att få alla tillgängliga testsviter och använd valfritt värde som en **test_suite_name** parameter.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``generatetestsuite``**``[/retry[=<seconds>]] [/dllonly] [/keepcustomexcel] ([test_suite_name] | [/byid] [test_suite_id]) [output_dir]``

##### <a name="generatetestsuite-optional-switches"></a>generatetestsuite: valfria växlar

+ `/retry[=seconds]`: Om denna switch är angiven, och falltestfall spärras av andra RSAT-instanser, väntar genereringsprocessen angivet antal sekunder och sedan försöker du en gång till. Standardmallvärdet är \[sekunder\] är 120 sekunder. Om du inte använder denna växel kommer processen att avbrytas omedelbart om testfallen är spärrade.
+ `/dllonly`: Generera endast testkörningsfiler. Återskapa inte Excel-parameterfilen.
+ `/keepcustomexcel`: Uppgradera den befintliga parameterfilen. Generera också om körningsfiler.
+ `/byid`: Denna växel anger att den önskade testsviten identifieras med sitt Azure DevOps ID i stället för namnet på testsviten.

##### <a name="generatetestsuite-required-parameters"></a>generatetestsuite: obligatoriska parametrar

+ `test_suite_name`: Representerar testpaketets namn. Denna parameter är nödvändig om /byid-växeln **inte** har angetts. Detta är testsvitens Azure DevOps namn.
+ `test_suite_id`: Representerar ID för testpaketet. Denna parameter är nödvändig om /byid-växeln **är** har angetts. Detta ID är testsvit-ID Azure DevOps.

##### <a name="generatetestsuite-optional-parameters"></a>generatetestsuite: valfria parametrar

+ `output_dir` Representerar katalogen för arbetskatalogen. Katalogen måste finnas. Arbetskatalogen från inställningarna används om den här parametern inte har angetts.

##### <a name="generatetestsuite-examples"></a>generatetestsuite: exempel

`generatetestsuite Tests c:\temp\rsat`

`generatetestsuite /retry Purchase c:\rsat\last`

`generatetestsuite /dllonly /byid 121`

`generatetestsuite /keepcustomexcel /byid 121`

#### <a name="help"></a>hjälp

Är identisk med [?](#section) kommando.

#### <a name="list"></a>lista

Listar alla tillgängliga testfall i den aktuella testplanen.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``list``**

#### <a name="listtestplans"></a>listtestplans

Visar alla tillgängliga testplaner.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``listtestplans``**

#### <a name="listtestsuite"></a>listtestsuite

Visar testärenden för angivet testpaket. Du kan använda kommandot ``listtestsuitenames`` för att få alla tillgängliga testsviter och använd valfritt värde från listan som en **suite_name** parameter.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``listtestsuite``**``[test_suite_name]``

##### <a name="listtestsuite-required-parameters"></a>listtestsuite: obligatoriska parametrar

+ `test_suite_name`: Namn på önskat paket.

##### <a name="listtestsuite-examples"></a>listtestsuite: exempel

`listtestsuite "sample suite name"`

`listtestsuite NameOfTheSuite`

#### <a name="listtestsuitebyid"></a>listtestsuitebyid

Visar testärenden för angivet testpaket.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``listtestsuitebyid``**``[test_suite_id]``

##### <a name="listtestsuitebyid-required-parameters"></a>listtestsuitebyid: obligatoriska parametrar

+ `test_suite_id`: ID på önskat paket.

##### <a name="listtestsuitebyid-examples"></a>listtestsuitebyid: exempel

`listtestsuitebyid 12345`

#### <a name="listtestsuitenames"></a>listtestsuitenames

Listar alla tillgängliga testsviter i den aktuella testplanen.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``listtestsuitenames``**

#### <a name="playback"></a>playback

Testa testfallet som är kopplat till den angivna Excel-parameterfilen. Det här kommandot använder befintliga lokala automationsfiler och hämtar inte filer från Azure DevOps. Det här kommandot stöds inte för POS Commerce testärenden.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``playback``**``[/retry[=<seconds>]] [/comments[="comment"]] [excel_parameter_file]``

##### <a name="playback-optional-switches"></a>uppspelning: valfria växlar

+ `/retry[=seconds]`: Om denna switch är angiven, och falltestfall spärras av andra RSAT-instanser, väntar uppspelningsprocessen angivet antal sekunder och sedan försöker du en gång till. Standardmallvärdet är \[sekunder\] är 120 sekunder. Om du inte använder denna växel kommer processen att avbrytas omedelbart om testfallen är spärrade.
+ `/comments[="comment"]`: Ange en anpassad informationssträng som tas med i fältet **Kommentarer** på sammanfattnings- och testresultatsidorna för Azure DevOps testfallskörningar.

##### <a name="playback-required-parameters"></a>uppspelning: obligatoriska parametrar

+ `excel_parameter_file`: Den fullständiga sökvägen för en Excel-parameterfil. Filen måste finnas.

##### <a name="playback-examples"></a>uppspelning: exempel

`playback c:\RSAT\2745\attachments\Create_Purchase_Order_2745_Base.xlsx`

`playback /retry e:\temp\test.xlsx`

`playback /retry=300 e:\temp\test.xlsx`

`playback /comments="Payroll solution 10.0.0" e:\temp\test.xlsx`

#### <a name="playbackbyid"></a>playbackbyid

Spelar upp flera testärenden samtidigt. Testfallen identifieras med deras ID. Det här kommandot hämtar filer från Azure DevOps. Du kan använda kommandot ``list`` för att få alla tillgängliga testfall, och använda alla värden från den första kolumnen som **test_case_id** parameter.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``playbackbyid``**``[/retry[=<seconds>]] [/comments[="comment"]] [test_case_id1] [test_case_id2] ... [test_case_idN]``

##### <a name="playbackbyid-optional-switches"></a>playbackbyid: valfria växlar

+ `/retry[=seconds]`: Om denna switch är angiven, och falltestfall spärras av andra RSAT-instanser, väntar uppspelningsprocessen angivet antal sekunder och sedan försöker du en gång till. Standardmallvärdet är \[sekunder\] är 120 sekunder. Om du inte använder denna växel kommer processen att avbrytas omedelbart om testfallen är spärrade.
+ `/comments[="comment"]`: Ange en anpassad informationssträng som tas med i fältet **Kommentarer** på sammanfattnings- och testresultatsidorna för Azure DevOps testfallskörningar.

##### <a name="playbackbyid-required-parameters"></a>playbackbyid: obligatoriska parametrar

+ `test_case_id1`: ID för befintliga testärenden.
+ `test_case_id2`: ID för befintliga testärenden.
+ `test_case_idN`: ID för befintliga testärenden.

##### <a name="playbackbyid-examples"></a>playbackbyid: exempel

`playbackbyid 878`

`playbackbyid 2345 667 135`

`playbackbyid /comments="Payroll solution 10.0.0" 2345 667 135`

`playbackbyid /retry /comments="Payroll solution 10.0.0" 2345 667 135`

#### <a name="playbackmany"></a>playbackmany

Spelar upp flera testärenden samtidigt. Testfallen identifieras av Excel-parameterfiler. Det här kommandot använder befintliga lokala automationsfiler och hämtar inte filer från Azure DevOps.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``playbackmany``**``[/retry[=<seconds>]] [/comments[="comment"]] [excel_parameter_file1] [excel_parameter_file2] ... [excel_parameter_fileN]``

##### <a name="playbackmany-optional-switches"></a>playbackmany: valfria växlar

+ `/retry[=seconds]`: Om denna switch är angiven, och falltestfall spärras av andra RSAT-instanser, väntar uppspelningsprocessen angivet antal sekunder och sedan försöker du en gång till. Standardmallvärdet är \[sekunder\] är 120 sekunder. Om du inte använder denna växel kommer processen att avbrytas omedelbart om testfallen är spärrade.
+ `/comments[="comment"]`: Ange en anpassad informationssträng som tas med i fältet **Kommentarer** på sammanfattnings- och testresultatsidorna för Azure DevOps testfallskörningar.

##### <a name="playbackmany-required-parameters"></a>playbackmany: obligatoriska parametrar

+ `excel_parameter_file1`: Den fullständiga sökvägen för en Excel-parameterfil. Filen måste finnas.
+ `excel_parameter_file2`: Den fullständiga sökvägen för en Excel-parameterfil. Filen måste finnas.
+ `excel_parameter_fileN`: Den fullständiga sökvägen för en Excel-parameterfil. Filen måste finnas.

##### <a name="playbackmany-examples"></a>playbackmany: exempel

`playbackmany c:\RSAT\2745\attachments\Create_Purchase_Order_2745_Base.xlsx`

`playbackmany e:\temp\test.xlsx f:\RSAT\sample1.xlsx c:\RSAT\sample2.xlsx`

`playbackmany /retry=180 /comments="Payroll solution 10.0.0" e:\temp\test.xlsx f:\rsat\sample1.xlsx c:\RSAT\sample2.xlsx`

#### <a name="playbacksuite"></a>playbacksuite

Spelar upp alla testfall från en eller flera specificerade testpaket. Om den /lokala växeln anges används lokala bilagor för alltid. Annars hämtas bilagor från Azure DevOps. Du kan använda kommandot ``listtestsuitenames`` för att få alla tillgängliga testsviter och använd valfritt värde från första kolumnen som en **suite_name** parameter.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``playbacksuite``**``[/updatedriver] [/local] [/retry[=<seconds>]] [/comments[="comment"]] ([test_suite_name1] .. [test_suite_nameN] | [/byid] [test_suite_id1] .. [test_suite_idN])``

##### <a name="playbacksuite-optional-switches"></a>playbacksuite: valfria växlar

+ `/updatedriver`: Om denna växel är angiven uppdateras webbläsarens WebDriver så som krävs innan denna process körs.
+ `/local`: I den här växeln anges att lokala bilagor ska användas för växling istället för att hämta filer från Azure DevOps.
+ `/retry[=seconds]`: Om denna switch är angiven, och falltestfall spärras av andra RSAT-instanser, väntar uppspelningsprocessen angivet antal sekunder och sedan försöker du en gång till. Standardmallvärdet är \[sekunder\] är 120 sekunder. Om du inte använder denna växel kommer processen att avbrytas omedelbart om testfallen är spärrade.
+ `/comments[="comment"]`: Ange en anpassad informationssträng som tas med i fältet **Kommentarer** på sammanfattnings- och testresultatsidorna för Azure DevOps testfallskörningar.
+ `/byid`: Denna växel anger att den önskade testsviten identifieras med sitt Azure DevOps ID i stället för namnet på testsviten.

##### <a name="playbacksuite-required-parameters"></a>playbacksuite: obligatoriska parametrar

+ `test_suite_name1`: Representerar testpaketets namn. Denna parameter är nödvändig om /byid-växeln **inte** har angetts. Detta är testsvitens Azure DevOps namn.
+ `test_suite_nameN`: Representerar testpaketets namn. Denna parameter är nödvändig om /byid-växeln **inte** har angetts. Detta är testsvitens Azure DevOps namn.
+ `test_suite_id1`: Representerar ID för testpaketet. Denna parameter är nödvändig om /byid-växeln **är** har angetts. Detta ID är testsvit-ID Azure DevOps.
+ `test_suite_idN`: Representerar ID för testpaketet. Denna parameter är nödvändig om /byid-växeln **är** har angetts. Detta ID är testsvit-ID Azure DevOps.

##### <a name="playbacksuite-examples"></a>playbacksuite: exempel

`playbacksuite suiteName`

`playbacksuite suiteName suiteNameToo`

`playbacksuite /updatedriver /local /retry=180 /byid 151 156`

`playbacksuite /updatedriver /local /comments="Payroll solution 10.0.0" /byid 150`

#### <a name="playbacksuitebyid"></a>playbacksuitebyid

Kör alla testärende från angiven Azure DevOps testpaket.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``playbacksuitebyid``**``[/updatedriver] [/local] [/retry[=<seconds>]] [/comments[="comment"]] [test_suite_id]``

##### <a name="playbacksuitebyid-optional-switches"></a>playbacksuitebyid: valfria växlar

+ `/retry[=seconds]`: Om denna switch är angiven, och falltestfall spärras av andra RSAT-instanser, väntar uppspelningsprocessen angivet antal sekunder och sedan försöker du en gång till. Standardmallvärdet är \[sekunder\] är 120 sekunder. Om du inte använder denna växel kommer processen att avbrytas omedelbart om testfallen är spärrade.
+ `/comments[="comment"]`: Ange en anpassad informationssträng som tas med i fältet **Kommentarer** på sammanfattnings- och testresultatsidorna för Azure DevOps testfallskörningar.
+ `/byid`: Denna växel anger att den önskade testsviten identifieras med sitt Azure DevOps ID i stället för namnet på testsviten.

##### <a name="playbacksuitebyid-required-parameters"></a>playbacksuitebyid: obligatoriska parametrar

+ `test_suite_id`: Representerar testsvit-ID:t så som det finns i Azure DevOps.

##### <a name="playbacksuitebyid-examples"></a>playbacksuitebyid: exempel

`playbacksuitebyid 2900`

`playbacksuitebyid /retry 2099`

`playbacksuitebyid /retry=200 2099`

`playbacksuitebyid /retry=200 /comments="some comment" 2099`

#### <a name="quit"></a>avsluta

Stänger programmet. Det här kommandot är bara användbart när programmen körs i interaktivt läge.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``quit``**

##### <a name="quit-examples"></a>avsluta: exempel

`quit`

#### <a name="upload"></a>överför

Överför bilagefiler (inspelnings-, körnings- och parameterfiler) som tillhör en angiven testsvit eller testfall till Azure DevOps.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``upload``**``([test_suite_name] | [test_case_id1] .. [test_case_idN])``

##### <a name="upload-required-parameters"></a>ladda upp: parametrar som krävs

+ `test_suite_name`: Alla filer som hör till de angivna testpaketen kommer att laddas upp.
+ `test_case_id1`: Representerar det första testfalls-ID som ska överföras. Använd endast denna parameter om inget testsvitnamn har angetts.
+ `test_case_idN`: Representerar det sista testfalls-ID som ska överföras. Använd endast denna parameter om inget testsvitnamn har angetts.

##### <a name="upload-examples"></a>ladda upp: exempel

`upload sample_suite`

`upload 2900`

`upload 123 456`

#### <a name="uploadrecording"></a>uploadrecording

Laddar bara upp inspelningsfilen som tillhör ett eller flera specificerade testfall till Azure DevOps.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``uploadrecording``**``[test_case_id1] .. [test_case_idN]``

##### <a name="uploadrecording-required-parameters"></a>uploadrecording: parametrar som krävs

+ `test_case_id1`: Representerar det första testfalls-ID för inspelningen som ska laddas upp till Azure DevOps.
+ `test_case_idN`: Representerar det sista testfalls-ID för inspelningen som ska laddas upp till Azure DevOps.

##### <a name="uploadrecording-examples"></a>uploadrecording: exempel

`uploadrecording 123`

`uploadrecording 123 456`

#### <a name="usage"></a>användning

Visar de tre användningssätten för det här programmet.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``usage``**

Köra programmet interaktivt:

+ ``Microsoft.Dynamics.RegressionSuite.ConsoleApp``

Köra programmet genom att ange ett kommando:

+ ``Microsoft.Dynamics.RegressionSuite.ConsoleApp ``**``[command]``**

Så här kör du programmet med en inställningsfil:

+ ``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``/settings [drive:\Path to\file.settings] [command]``**

### <a name="windows-powershell-examples"></a>Windows PowerShell-exempel

#### <a name="run-a-test-case-in-a-loop"></a>Kör ett testfall i en slinga

Du har ett testskript som skapar en ny kund. Via skript kan det här testfallet köras i en slinga genom att göra slumpmässiga följandande data innan varje iteration körs:

- Kund-ID
- Kundnamn
- Kundadress

Kund-ID:t anges i formatet *ATCUS\<number\>*, där \<number\> är ett värde mellan **000000001** och **999999999**.

I följande exempel används en parameter, **Start** för att definiera det första numret som används. Det använder en andra parameter, **nr**, för att definiera antalet kunder som måste skapas. För varje upprepning ändras parametrarna i Excel-parameterfil med hjälp av en UpdateCustomer-funktion. Då anropas kommando raden för RSAT i en RunTestCase-funktion.

Öppna Microsoft Windows PowerShell ISE (Integrated Scripting Environment) i administrationsläge och klistra in följande kod i fönstret med namnet **Untitled1.ps1**.

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

#### <a name="run-a-script-that-depends-on-data-in-microsoft-dynamics-365"></a>Köra ett skript som är beroende av data i Microsoft Dynamics 365

I följande exempel används ett OData-anrop (Open Data Protocol) för att hitta orderstatusen för en inköpsorder. Om statusvärdet inte har **fakturerats** kan du t.ex. anropa ett testfall för RSAT som bokför fakturan.

```powershell
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


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
