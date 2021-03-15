---
title: Destinationer för elektronisk rapportering (ER)
description: I det här avsnittet finns information om hantering av mål för elektroniska rapportering, vilka typer av destinationer som stöds samt säkerhetsaspekter.
author: nselin
manager: AnnBe
ms.date: 01/21/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: DocuType, ERSolutionTable
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: f3055a27-717a-4c94-a912-f269a1288be6
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.openlocfilehash: 725ded9d777a65e5a38a7971c1da8cb74cf0dd47
ms.sourcegitcommit: 872600103d2a444d78963867e5e0cdc62e68c3ec
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/01/2021
ms.locfileid: "5097291"
---
# <a name="electronic-reporting-er-destinations"></a>Destinationer för elektronisk rapportering (ER)

[!include [banner](../includes/banner.md)]

Du kan konfigurera en mål för varje elektronisk rapportering (ER) formatkonfiguration för elektronisk rapportering (ER) (en mapp eller en fil). Användare med rätt behörighet kan även ändra inställningar för mål vid körning. Den här artikeln innehåller en beskrivning av hur ER-mål, typer av mål som stöds och säkerhetsaspekter hanteras.

Formatkonfigurationer för elektronisk rapportering (ER) innehåller vanligtvis minst en utdatakomponent: en fil. Vanligtvis innehåller konfigurationerna flera filutdatakomponenter av olika typer (till exempel XML, TXT, XLSX, DOCX eller PDF) som är grupperade i en enda mapp eller i flera mappar. Med hjälp av målshantering för ER kan du förkonfigurera vad som händer när du kör varje komponent. När du kör en konfiguration visas automatiskt en dialogruta som låter dig spara eller öppna filen. Samma beteende uppvisas när du importerar en ER-konfiguration och inte konfigurerar några specifika mål för den. När du har skapat en mål för en huvudutdatakomponent åsidosätter målen standardbeteendet och mappen eller filen skickas enligt inställningarna för målen.

## <a name="availability-and-general-prerequisites"></a>Tillgänglighet och allmänna förutsättningar

Funktionen för ER-målen är inte tillgänglig i Microsoft Dynamics AX 7.0 (februari 2016). Därför måste du installera Microsoft Dynamics 365 for Operations version 1611 (november 2016) eller senare för att kunna använda följande måltyper:

- [E-postadress](er-destination-type-email.md)
- [Arkivera](er-destination-type-archive.md)
- [Fil](er-destination-type-file.md)
- [Skärm](er-destination-type-screen.md)
- [Power BI](er-destination-type-powerbi.md)

Alternativt kan du installera någon av följande förutsättningar: Notera emellertid att dessa alternativ ger en mer begränsad upplevelse av ER-målen.

- Microsoft Dynamics AX programversion 7.0.1 (maj 2016)
- [Snabbkorrigering av målhanteringsprogram för elektronisk rapportering](https://fix.lcs.dynamics.com/issue/results/?q=3160213)

Det finns också måltypen [utskrift](er-destination-type-print.md). För att kunna använda den måste du installera Microsoft Dynamics 365 Finance version 10.0.9 (april 2020).

## <a name="overview"></a>Översikt

Du kan enbart ställa in mål för ER-konfigurationer som har [importerats](general-electronic-reporting.md#importing-an-er-component-from-lcs-to-use-it-internally) i aktuella Finance-instansen och för de format som är tillgängliga på sidan **Konfigurationer för elektronisk rapportering**. Funktionen för ER-målshantering är tillgänglig via **Organisationsadministration** \> **Elektronisk rapportering** \> **Elektronisk rapporteringsmål**.

### <a name="default-behavior"></a>Standardbeteende

Standardbeteende för en ER-formatkonfiguration beror på vilken körningstyp du anger när ett ER-format startar.

I dialogrutan **Intrastat-rapport** på snabbfliken **Kör i bakgrunden**, om du ställer in alternativet **Batchbearbetning** som **Nej**,körs ett ER-format omedelbart i interaktivt läge. När körningen har slutförts blir ett genererat utgående dokument tillgängligt för hämtning.

Om du ställer in alternativet **Batchbearbetning** som **Ja** körs ett ER-format i [batchläge](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/sysadmin/batch-processing-overview). Lämpligt batchjobb skapas enligt de parametrar som du anger på fliken **Kör i bakgrunden** i dialogrutan **ER-parametrar**.

> [!NOTE]
> Jobbeskrivningen informerar dig om körning av en ER-formatmappning. Den innehåller även namn på den ER-komponent som körs.

[![Köra ett ER-format](./media/ER_Destinations-RunInBatchMode.png)](./media/ER_Destinations-RunInBatchMode.png)

Du kan hitta information om jobbet på flera ställen:

- Gå till **Standard** \> **Förfrågningar** \> **Batchjobb** \> **Mina batchjobb** för att kontrollera status för det schemalagda jobbet.
- Gå till **Organisationsadministration** \> **Elektronisk rapportering** \> **Elektroniska rapporteringsjobb** för att kontrollera status för det schemalagda jobbet och körningsresultatet för det slutförda jobbet. När jobbet har körts klart väljer du **Visa filer** på sidan **Elektroniska rapporteringsjobb** för att hämta ett genererat utgående dokument.

    > [!NOTE]
    > Dokumentet lagras som en bilaga till den aktuella jobbposten och styrs av ramverket för [dokumenthantering](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/organization-administration/configure-document-management). [Dokumenttypen](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/organization-administration/configure-document-management#configure-document-types) som används för att lagra ER-artefakter av den här typen konfigureras i [ER-parametrar](electronic-reporting-er-configure-parameters.md#parameters-to-manage-documents).

- På sidan **Elektroniska rapporteringsjobb** väljer du **Visa filer** för att visa en lista över eventuella fel och varningar som genererats under jobbkörningen.

    [![Granska listan med ER-jobb](./media/ER_Destinations-ReviewERJobs.png)](./media/ER_Destinations-ReviewERJobs.png)

### <a name="user-configured-behavior"></a>Användarkonfigurerat beteende

På sidan **elektronisk rapporteringsmål** kan du åsidosätta standardbeteendet för en konfiguration. Importerade konfigurationer visas inte på denna sida förrän du har klickat på **Ny** och sedan gått till fältet **Referens** och valt en konfiguration för att skapa målsinställningar.

[![Välja en konfiguration i fältet Referens](./media/ER_Destinations-SelectFormat.png)](./media/ER_Destinations-SelectFormat.png)

När du har skapat en referens kan du skapa ett filmål för varje **mapp** eller **fil** utmatningskomponent i det refererade ER-formatet.

[![Skapa en filmål](./media/ER_Destinations-ConfigureElementDestination.png)](./media/ER_Destinations-ConfigureElementDestination.png)

Sedan i dialogrutan **målinställningar** kan du aktivera och inaktivera enskilda mål för filmålen. Knappen **Inställningar** används för att styra alla mål för en markerad filmål. I dialogrutan **målsinställningar** kan du styra varje mål separat genom att ställa inte alternativet **Aktiverad** för den.

I versioner av Finance **före version 10.0.9**, kan du skapa **ett filmål** för varje utgångskomponent i samma format, till exempel en mapp eller en fil som är vald i fältet **Filnamn**. I **version 10.0.9 och senare** kan du emellertid skapa **flera filmål** för varje utmatningskomponent i samma format.

Du kan till exempel använda den här funktionen för att konfigurera filmål för en filkomponent som används för att generera ett utgående dokument i Excel-format. One destination ([Arkiv](er-destination-type-archive.md)) kan konfigureras till att lagra den ursprungliga Excel-filen i ER-jobbarkivet och ett annat mål ([E-post](er-destination-type-email.md)) konfigureras för att samtidigt [konvertera](#OutputConversionToPDF) Excel-filen till PDF-format och skicka PDF-filen via e-post.

[![Konfigurera flera mål för ett enda formatelement](./media/ER_Destinations-SampleDestinations.png)](./media/ER_Destinations-SampleDestinations.png)

När du kör ett ER-format körs alltid alla destinationer som konfigurerats för komponenter i formatet. Dessutom i Finance **version 10.0.17 och senare** har R-destinationer förbättrats och du kan nu konfigurera olika destinationsuppsättningar för ett enda ER-format. Denna konfiguration markerar varje uppsättning som konfigurerad för en viss användaråtgärd. ER API har [utökats](er-apis-app10-0-17.md) så att en åtgärd kan ges till användaren genom att köra ett ER-format. Den åtgärdskod som tillhandahålls överförs till ER-destinationer. Du kan köra olika destinationer i ett ER-format, beroende på vilken åtgärdskod som anges. Mer information finns i [Konfigurera åtgärdsberoende ER-destinationer](er-action-dependent-destinations.md).

## <a name="destination-types"></a>Destinationstyper

Följande mål stöds för närvarande för ER-format. Du kan inaktivera eller aktivera alla typer samtidigt. På det här sättet kan du antingen inte göra någonting eller skicka komponenten till alla konfigurerade mål.

- [E-postadress](er-destination-type-email.md)
- [Arkivera](er-destination-type-archive.md)
- [Fil](er-destination-type-file.md)
- [Skärm](er-destination-type-screen.md)
- [Power BI](er-destination-type-powerbi.md)
- [Skriv ut](er-destination-type-print.md)

## <a name="applicability"></a>Tillämplighet

Du kan enbart ställa in mål för ER-konfigurationer som har importerats och för de format som är tillgängliga på sidan **Konfigurationer för elektronisk rapportering**.

> [!NOTE]
> Konfigurerade mål är företagsspecifika. Om du planerar att använda ett ER-format i olika företag i den aktuella Finance-instansen måste du konfigurera destinationer för det aktuella ER-formatet för vart och ett av dessa företag.

När du konfigurerar filmål för ett valt format, konfigurerar du dem för hela formatet.

[![Konfigurationslänk](./media/ER_Destinations-ConfigurationLink.png)](./media/ER_Destinations-ConfigurationLink.png)

På samma gång har du kanske flera [versioner](general-electronic-reporting.md#component-versioning) av formatet som har importerats till den aktuella Finance-instansen. Du kan visa dem om du väljer länken **konfigurationer** som erbjuds när du väljer fältet **referens**.

[![Konfigurationsversioner](./media/ER_Destinations-ConfigurationVersions.png)](./media/ER_Destinations-ConfigurationVersions.png)

Som standard används konfigurerade mål bara när du kör en ER-formatversion som har statusen **slutförd** eller **delad**. Du måste dock ibland använda konfigurerade mål när utkastversionen av ett ER-format körs. Du kan till exempel ändra utkastversionen av formatet och du vill använda konfigurerade mål för att testa hur genererade utdata levereras. Följ de här stegen om du vill använda mål för ett ER-format när utkastversionen körs.

1. Gå till **Organisationsadministration** \> **Elektronisk rapportering** \> **Konfigurationer**.
2. På sidan **Konfigurationer** i åtgärdsfönstret, på fliken **Konfigurationer** i gruppen **Avancerad inställningar** markerar du **Använd parametrar**.
3. Ange alternativet **Använd destinationer för utkaststatus** till **Ja**.

[![Alternativet använd destinationer för utkaststatus](./media/ER_Destinations-UserSetting1.png)](./media/ER_Destinations-UserSetting1.png)

Om du vill använda utkastversionen av ett ER-format måste du markera ER-format på lämpligt sätt.

1. Gå till **Organisationsadministration** \> **Elektronisk rapportering** \> **Konfigurationer**.
2. På sidan **Konfigurationer** i åtgärdsfönstret, på fliken **Konfigurationer** i gruppen **Avancerad inställningar** markerar du **Använd parametrar**.
3. Ge alternativet **Kör inställning** värdet **Ja**.

[![Alternativet körinställningar](./media/ER_Destinations-UserSetting2.png)](./media/ER_Destinations-UserSetting2.png)

När du har slutfört den här inställningen blir alternativet **Kör utkast** tillgängligt för de ER-format som du ändrar. Ställ in det här alternativet **Ja** om du vill börja använda utkastversionen av formatet när formatet körs.

[![Alternativet kör utkast](./media/ER_Destinations-FormatSetting.png)](./media/ER_Destinations-FormatSetting.png)

## <a name="destination-failure-handling"></a><a name="DestinationFailure"></a>Hantering av målfel

Vanligtvis körs ett ER-format inom omfånget för en specifik affärsprocess. Leveransen av ett utgående dokument som genereras under körningen av ett ER-format måste ibland betraktas som en del av affärsprocessen. I det här fallet, om leverans av ett utgående dokument till ett konfigurerat mål inte lyckas, måste körningen av affärsprocessen avbrytas. Om du vill konfigurera önskat ER-mål väljer du alternativet **Sluta behandlingen vid misslyckande**.

Till exempel konfigurerar du leverantörens betalningsbearbetning så att ER-formatet **ISO20022 kreditöverföring** för att generera betalningsfilen och tilläggsdokumenten (t.ex. för följebrevet och kontrollrapporten). Om en betalning ska betraktas som korrekt bearbetad endast om följebrevet har levererats via e-post, måste du markera kryssrutan **stoppa bearbetningen vid fel** för komponenten **CoveringLetter** i lämplig filmål, vilket visas i bilden nedan. I det här fallet ändras statusvärdet för den betalning som valts för bearbetning från **Ingen** till **Skickat** när den följebrevet som genereras lyckas accepteras för leverans av en e-postleverantör som konfigurerats i Finance-instansen.

[![Konfigurera processhantering för fel i filmål](./media/ER_Destinations-StopProcessingAtDestinationFailure.png)](./media/ER_Destinations-StopProcessingAtDestinationFailure.png)

Om du avmarkerar kryssrutan **Sluta behandlingen vid misslyckande** för komponenten **CoveringLetter** i målet kommer en betalning att anses ha behandlats framgångsrikt även om följebrevet inte levereras med e-post. Betalningens status kommer att ändras från **Ingen** till **Skickad** även om följebrevet inte kan skickas eftersom till exempel mottagarens eller avsändarens e-postadress saknas eller är felaktig.

## <a name="output-conversion-to-pdf"></a><a name="OutputConversionToPDF"></a>Konvertera utdata till PDF

Du kan använda konverteringsalternativet för PDF om du vill konvertera konvertera i Microsoft Office-format (Excel eller Word) till PDF-format.

### <a name="make-pdf-conversion-available"></a>Gör PDF-konverteringen tillgänglig

För att göra PDF-konverteringsalternativet tillgängligt i den aktuella Finance-instansen, öppna arbetsytan **funktionshantering** och aktivera funktionen **Konvertera utgående dokument från elektronisk rapportering från Microsoft Office-format till PDF**.

[![Aktivera funktionen PDF-konvertering av utgående dokument i funktionshantering](./media/ER_Destinations-EnablePdfConversionFeature.png)](./media/ER_Destinations-EnablePdfConversionFeature.png)

### <a name="applicability"></a>Tillämplighet

Alternativet PDF-konvertering kan bara aktiveras för filkomponenter som används för att generera utdata i Office (Excel eller Word) format (**Excel-fil**). När det här alternativet är aktiverat konverteras utdata som har genererats i Office-format automatiskt till PDF-format.

### <a name="limitations"></a>Begränsningar

> [!NOTE]
> Den här funktionen är en förhandsgranskningsfunktion och används för användningsvillkoren som [Extra användningsvillkor för Microsoft Dynamics 365 förhandsgranskningar](https://go.microsoft.com/fwlink/?linkid=2105274).

Alternativet PDF-konvertering är bara tillgängligt för molndistributioner.

Det producerade PDF-dokumentet är begränsat till en maximal längd på 300 sidor.

I Finance **version 10.0.9** stöds endast liggande sidorientering i PDF-dokumentet som har skapats från en Excel-utdatafil. I Finance **version 10.0.10 (maj 2020) och senare**, kan du [ange sidorientering](#SelectPdfPageOrientation) för PDF-dokument som har skapats från ett Excel-format när du konfigurerar ett ER-mål.

Endast de vanligaste systemteckensnitten i Windows-operativsystemet används för att konvertera utdata som inte innehåller inbäddade teckensnitt.

### <a name="use-the-pdf-conversion-option"></a>Använd PDF-konverteringsalternativet

Om du vill aktivera PDF-konvertering för ett filmål markerar du kryssrutan **konvertera till PDF**.

[![Aktivera PDF-konvertering av ett filmål](./media/ER_Destinations-TurnOnPDFConversion.png)](./media/ER_Destinations-TurnOnPDFConversion.png)

### <a name=""></a><a name="SelectPdfPageOrientation">Välj en sidorientering för PDF-konvertering</a>

Om du skapar en ER-konfiguration i Excel-format och vill konvertera den till PDF-format kan du ange sidorienteringen för PDF-dokument. När du markerar kryssrutan **Konvertera till PDF** för att aktivera PDF-konvertering för en fildestination som producerar en utdatafil i Excel-format, den **sidorientering** blir tillänglig **PDF-inställningar för konverteringar**. Välj önskad **sidorientering** i fältet prioriterad orientering.

[![Välj en sidorientering för PDF-konvertering](./media/ER_Destinations-SelectPDFConversionPageOrientation.png)](./media/ER_Destinations-SelectPDFConversionPageOrientation.png)

> [!NOTE]
> Om du vill välja PDF-sidans orientering måste du installera Finance version 10.0.10 eller senare.
>
> Den valda sidorienteringen tillämpas på alla ER-konfigurationer som genereras i Excel-format och sedan konverteras till PDF-format.
>
> Om en ER-konfiguration i Word-format konverteras till PDF-format, tas sidorientering för PDF-dokument från Word-dokumentet.

## <a name="security-considerations"></a>Säkerhetsaspekter

Två typer av behörigheter och uppgifter används för ER-mål. En typ styr en användares övergripande förmåga att bibehålla målen som har konfigurerats för en juridisk person (dvs. den styr åtkomsten till sidan **mål för elektronisk rapportering**). Den andra typen styr programanvändarens möjlighet att vid körning åsidosätta målsinställningar som är konfigurerade av en ER-utvecklare eller en ER-funktionskonsult.

| Roll (AOT-namn)                     | Rollnamn                                  | Programbehörighet (AOT-namn)                     | Programbehörighetsnamn                                                        |
|-------------------------------------|--------------------------------------------|-------------------------------------|------------------------------------------------------------------|
| ERDeveloper                         | Utvecklare för elektronisk rapportering             | ERFormatmålConfigure        | Konfigurera formatmål för elektronisk rapportering                |
| ERFunctionalConsultant              | Konsult för funktionen för elektronisk rapportering | ERFormatmålConfigure        | Konfigurera formatmål för elektronisk rapportering                |
| PaymAccountsPayablePaymentsClerk    | Ansvarig för leverantörsreskontrabetalningar            | ERFormatmålRuntimeConfigure | Konfigurera formatmål för elektronisk rapportering under körning |
| PaymAccountsReceivablePaymentsClerk | Ansvarig för kundreskontrabetalningar         | ERFormatmålRuntimeConfigure | Konfigurera formatmål för elektronisk rapportering under körning |

> [!NOTE]
> Två privilegier används i föregående programbehörigheter. De här privilegierna har samma namn som motsvarande uppgifter: **ERFormatmålConfigure** och **ERFormatmålRuntimeConfigure**.

## <a name="frequently-asked-questions"></a>Vanliga frågor

### <a name="i-have-imported-electronic-configurations-and-i-see-them-on-the-electronic-reporting-configurations-page-but-why-dont-i-see-them-on-the-electronic-reporting-destinations-page"></a>Jag har importerat elektroniska konfigurationer och jag ser dem på sidan Konfigurationer för elektronisk rapportering. Varför ser jag dem då inte på sidan mål för elektronisk rapportering?

Se till att du klickar på **Ny** och sedan väljer en konfiguration i fältet **Referens**. På sidan **mål för elektronisk rapportering** ser du bara de konfigurationer som mål har konfigurerats för.

### <a name="is-there-any-way-to-define-which-microsoft-azure-storage-account-and-azure-blob-storage-are-used"></a>Finns det något sätt att definiera vilket Microsoft Azure Storage-konto och vilken Azure Blob-lagring som används?

Nr. Standardlagringen för Microsoft Azure Blob som är definierad och används för dokumenthanteringssystem används.

### <a name="what-is-the-purpose-of-the-file-destination-in-the-destination-settings-what-does-that-setting-do"></a>Vad är syftet med filmålen i målsinställningarna? Vad innebär inställningen?

Destinationen **Fil** används för att kontrollera en dialogruta i webbläsaren när du kör ett ER-format i interaktivt läge. Om du aktiverar den här målen eller om ingen mål har definierats för en konfiguration, ser du dialogrutan Öppna eller Spara i din webbläsare efter det att en utdatafil har skapats.

### <a name="can-you-give-an-example-of-the-formula-that-refers-to-a-vendor-account-that-i-can-send-email-to"></a>Kan du ge ett exempel på en formel som refererar till ett leverantörskonto som jag kan skicka e-postmeddelande till?

Formeln är specifik för ER-konfigurationen. Till exempel, om du använder ISO 20022-konfigurationen för kreditöverföring, kan du använda **'$PaymentsForCoveringLetter'.Creditor.Identification.SourceID** eller **model.Payments.Creditor.Identification.SourceID** för att hämta ett associerat leverantörskonto.

### <a name="one-of-my-format-configurations-contains-multiple-files-that-are-grouped-into-one-folder-for-example-folder1-contains-file1-file2-and-file3-how-do-i-set-up-destinations-so-that-folder1zip-isnt-created-at-all-file1-is-sent-by-email-file2-is-sent-to-sharepoint-and-i-can-open-file3-immediately-after-the-configuration-is-run"></a>En av mina formatkonfigurationer innehåller flera filer som grupperade i en mapp (till exempel innehåller Mapp1 fil1, fil2 och fil3). Hur ställer jag in mål så att Folder1.zip inte skapas alla, fil1 skickas via e-post, fil2 skickas till SharePoint och jag kan öppna fil3 omedelbart efter att konfigurationen har körts?

Formatet måste först vara tillgängligt i ER konfigurationer. Om denna förutsättning uppfylls, öppna sidan **mål för elektronisk rapportering** och skapa en ny referens till den här konfigurationen. Du måste ha fyra filmål, ett för varje utdatakomponent. Skapa den första filmålen, ge den ett namn såsom **Mapp** och välj ett filnamn som representerar en mapp i din konfiguration. Klicka på **Inställningar** och se till att alla mål är inaktiverade. För den här filmålen kommer mappen inte att skapas. På grund av hierarkiska beroenden mellan filer och överordnade mappar kommer filerna som standard att uppföra sig på samma sätt. Med andra ord skickas de inte någonstans. Om du vill åsidosätta standardbeteendet måste du skapa tre filmål till, en för varje fil. I målsinställningarna för varje mål måste du aktivera målen som filen ska skickas till.

## <a name="additional-resources"></a>Ytterligare resurser

[Översikt över elektronisk rapportering (ER)](general-electronic-reporting.md)

[Konfigurera åtgärdsberoende ER-destinationer](er-action-dependent-destinations.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]