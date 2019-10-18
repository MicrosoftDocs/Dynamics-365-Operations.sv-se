---
title: Destinationer för elektronisk rapportering (ER)
description: Du kan konfigurera en mål för varje elektronisk rapportering (ER) formatkonfiguration för elektronisk rapportering (ER) (en mapp eller en fil). Användare med rätt behörighet kan även ändra målsinställningarna vid körning. Den här artikeln innehåller en beskrivning av hur ER-mål, typer av mål som stöds och säkerhetsaspekter hanteras.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: DocuType, ERSolutionTable
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 97423
ms.assetid: f3055a27-717a-4c94-a912-f269a1288be6
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.openlocfilehash: 5b52e1765d3afbe1730e96f58b601aebccd12787
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/27/2019
ms.locfileid: "2181276"
---
# <a name="electronic-reporting-er-destinations"></a>Destinationer för elektronisk rapportering (ER)

[!include [banner](../includes/banner.md)]

Du kan konfigurera en mål för varje elektronisk rapportering (ER) formatkonfiguration för elektronisk rapportering (ER) (en mapp eller en fil). Användare med rätt behörighet kan även ändra målsinställningarna vid körning. Den här artikeln innehåller en beskrivning av hur ER-mål, typer av mål som stöds och säkerhetsaspekter hanteras.

Formatkonfigurationer för elektronisk rapportering (ER) innehåller vanligtvis minst en utdatakomponent: en fil. Vanligtvis innehåller konfigurationerna flera filutdatakomponenter av olika typer (till exempel XML, TXT eller XLSX) som är grupperade i en enda mapp eller i flera mappar. Med hjälp av målshantering för ER kan du förkonfigurera vad som händer när du kör varje komponent. När du kör en konfiguration visas automatiskt en dialogruta som låter användaren spara eller öppna filen. Samma beteende uppvisas när du importerar en ER-konfiguration och inte konfigurerar några specifika mål för den. När du har skapat en mål för en huvudutdatakomponent åsidosätter målen standardbeteendet och mappen eller filen skickas enligt inställningarna för målen.

## <a name="availability-and-general-prerequisites"></a>Tillgänglighet och allmänna förutsättningar
Funktionen för ER-målen är inte tillgänglig i Microsoft Dynamics AX 7.0 (februari 2016). Därför måste du installera Microsoft Dynamics 365 for Operations version 1611 (November 2016) att använda de funktioner som beskrivs i detta avsnitt. Alternativt kan du installera någon av följande förutsättningar: Notera emellertid att dessa alternativ ger en mer begränsad upplevelse av ER-målen.

- Microsoft Dynamics AX programversion 7.0.1 (maj 2016)
- [Snabbkorrigering av programvara](https://fix.lcs.dynamics.com/issue/results/?q=3160213) för ER-målshantering

Du kan enbart ställa in mål för ER-konfigurationer som har importerats och för de format som är tillgängliga på sidan **Konfigurationer för elektronisk rapportering**.

## <a name="overview"></a>Översikt
Funktionen för ER-målshantering är tillgänglig via **Organisationsadministration** &gt; **Elektronisk rapportering**. Här kan du åsidosätta standardbeteendet för en konfiguration. Importerade konfigurationer visas inte här förrän du har klickat på **Ny** och sedan gått till fältet **Referens** och valt en konfiguration för att skapa målsinställningar.

[![Välja en konfiguration i fältet Referens](./media/ger-destinations-2-1611-1024x574.jpg)](./media/ger-destinations-2-1611.jpg)

När du har skapat en referens kan du skapa en filmål för varje mapp eller för en fil.

[![Skapa en filmål](./media/ger-destinations-1611-1024x586.jpg)](./media/ger-destinations-1611.jpg)

> [!NOTE]
> Du kan skapa en filmål för varje utdatakomponent av samma format, såsom en mapp eller en fil som väljs i fältet **Filnamn**. Du kan sedan aktivera och inaktivera enskilda mål för filmålen i dialogrutan **målsinställningar**. Knappen **Inställningar** används för att styra alla mål för en markerad filmål. I dialogrutan **målsinställningar** kan du styra varje mål separat genom att ställa inte alternativet **Aktiverad** för den.

[![Dialogruta för målsinställningar](./media/ger-destinations-settings-1611-1024x589.jpg)](./media/ger-destinations-settings-1611.jpg)

## <a name="destination-types"></a>målstyper
Det finns stöd för olika målstyper. Du kan inaktivera eller aktivera alla typer samtidigt. På det här sättet kan du antingen inte göra någonting eller skicka komponenten till alla konfigurerade mål. Följande avsnitt innehåller en beskrivning av de mål som stöds.

### <a name="email-destination"></a>E-postmål

Ställ in **Aktiverad** till **Ja** för att skicka en utdatafil via e-post. När det här alternativet är aktiverat kan du ange e-postmottagare samt redigera e-postmeddelandets ämne och brödtext. Du kan skapa konstanta texter mailets rubrik och brödtext, eller använda ER-formler för att skapa e-posttexter dynamiskt. Du kan konfigurera e-postadresser för ER på två sätt. Konfigurationen kan slutföras på samma sätt som funktionen för utskriftshantering i appen slutför den. Du kan också lösa en e-postadress genom att använda en direktreferens till ER-konfigurationen via en formel.

### <a name="email-address-types"></a>E-postadresstyper

När du klickar på **Redigera** för fältet **Till** eller **Cc**, visas dialogrutan **E-posta**. Du kan sedan välja vilken typ av e-postadress som ska användas.

[![Dialogrutan E-posta](./media/ger-destinations-email-1-1611-1024x588.jpg)](./media/ger-destinations-email-1-1611.jpg)

#### <a name="print-management"></a>Utskriftshantering

Om du väljer typen **Utskriftshantering för e-postmeddelanden** kan du ange fasta e-postadresser i fältet **Till**. Du måste välja källtyp för e-postmeddelanden till en filmål om du vill använda e-postadresser som inte är fasta. Följande värden kan användas: **Kund**, **Leverantör**, **Potentiell kund**, **Kontakt**, **Konkurrent**, **Arbetare**, **Sökande**, **Potentiell leverantör** samt **Otillåten leverantör**. När du har valt en e-posttyp klickar du på knappen bredvid fältet **Källkonto för e-post** för att öppna formuläret **Formeldesigner**. Du kan använda det här formuläret för att bifoga en formel som representerar det markerade kontot till målet för e-post.

[![Konfigurera e-posttyp för utskriftshantering](./media/ger-destinations-email-2-1611-1024x588.jpg)](./media/ger-destinations-email-2-1611.jpg)

Observera att formlerna är specifika för ER-konfigurationen. Ange en dokumentspecifik referens till en kund- eller leverantörsparttyp i fältet **Formel**. I stället för skriva in datakällanoden kan du hitta den som representerar kund- eller leverantörskontot och klicka på **Lägg till datakälla** om du vill uppdatera formeln. Exempel: Om du använder ISO 20022-konfigurationen för kreditöverföring är noden som representerar ett leverantörskonto **'$PaymentsForCoveringLetter'.Creditor.Identification.SourceID**. I annat fall, ange ett strängvärde såsom **DE-001** om du vill spara en formel.

[![Formeldesigner](./media/ger_formuladesignerfordestination-1024x541.jpg)](./media/ger_formuladesignerfordestination.jpg)

I dialogrutan **E-posta till** klickar du på papperskorgen bredvid fältet **Källkonto för e-post** om du vill ta bort formeln för källkontot för e-post permanent. Alternativt kan du även öppna formeldesignern om du vill ändra en formel som tidigare har sparats. Om du vill tilldela e-postadresser, klicka då på **Redigera** för att öppna dialogrutan **Tilldela e-postadresser**.

[![Tilldela e-postadresser till ett mål för e-post](./media/ger-destinations-email-3-1611-1024x587.jpg)](./media/ger-destinations-email-3-1611.jpg)

#### <a name="configuration-email"></a>Konfigurations-e-postmeddelande

Använd den här typen av e-post om den konfiguration som du använder har en nod i datakällorna som representerar en e-postadress. Du kan använda datakällor och funktioner i formeldesignern för att få en korrekt formaterad e-postadress.

[![Tilldela en datakälla för e-postadress till en e-postmål](./media/ger-destinations-email-4-1611-1024x587.jpg)](./media/ger-destinations-email-4-1611.jpg)

> [!NOTE]
> En Simple Mail Transfer Protocol (SMTP)-server måste vara konfigurerad och tillgänglig. Du kan ange SMTP-servern i **Systemadministration** &gt; **Inställningar** &gt; **E-pos** &gt; **E-postparametrar**.

### <a name="archive-destination"></a>Arkivmål

Du kan använda detta alternativ för att skicka utdata till en Microsoft SharePoint-mapp eller till Microsoft Azure Storage. Ställ in **Aktiverad** till **Ja** för att skicka utdata till en mål som definierats av den valda dokumenttypen. Endast dokumenttyper där gruppen är inställd på **Fil** kan väljas. Du kan ange dokumenttyper via **Organisationsadministration** &gt; **Dokumenthantering** &gt; **Dokumenttyper**. Konfigurationen för ER-mål är samma som konfigurationen för dokumenthanteringssystemet.

[![Sida för dokumenttyper](./media/ger_documenttypefile-1024x542.jpg)](./media/ger_documenttypefile.jpg)

Platsen avgör var filen sparas. När målen **Arkiv** har aktiverats kan resultaten av konfigurationskörningen sparas i jobbarkivet. Du kan visa resultaten via **Organisationsadministration** &gt; **Elektronisk rapportering** &gt; **Arkiverade elektroniska rapporteringsjobb**.

> [!NOTE]
> Du kan välja en dokumenttyp för jobbarkivet i **Organisationsadministration** &gt; **Arbetsytor** &gt; **Elektronisk rapportering** &gt; **Parametrar för elektronisk rapportering**.

#### <a name="sharepoint"></a>SharePoint

Du kan spara en fil i en viss SharePoint-mapp. Du anger förvald SharePoint-server på **Organisationsadministration** &gt; **Dokumenthantering** &gt; **Parametrar för dokumenthantering**, på fliken **SharePoint**. När SharePoint mappen har konfigurerats kan du välja den som den mapp där ER-resultatet sparas för dokumenttypen.

[![Markera SharePoint-mappen](./media/ger_sharepointfolderselection-1024x543.jpg)](./media/ger_sharepointfolderselection.jpg)

#### <a name="azure-storage"></a>Azure Storage

När dokumenttypens plats är inställd på **Arkivkatalog** kan du spara en fil i Azure Storage.

### <a name="file-destination"></a>Filmål

Om du anger **Aktiverad** som **Ja** visas en dialogruta för Öppna eller Spara när konfigurationen är slutförd.

### <a name="screen-destination"></a>Skärmmål

Om du ställer in **Aktiverad** som **Ja** skapas en förhandsgranskning av resultatet. Du kan visa vissa filtyper, till exempel XML, TXT eller PDF, direkt i ett webbläsarfönster. För andra filtyper som exempelvis Microsoft Excel eller Word, används tjänsten Microsoft Office.

### <a name="power-bi-destination"></a>Power BI-destination

Ange **Aktiverad** till **Ja** om du vill använda din konfiguration för elektronisk rapportering (ER) för att ordna överföringen av data från din instans till Microsoft Power BI-tjänster. De överförda filerna lagras i en Microsoft SharePoint-serverinstans som måste ha konfigurerats för det syftet. Mer information finns i [Använd en elektronisk rapporteringskonfiguration för att tillhandahålla Power BI med data från Finance](general-electronic-reporting-report-configuration-get-data-powerbi.md).

> [!TIP]
> Om du vill åsidosätta standardbeteendet (dvs. dialogrutan för en konfiguration) kan du skapa en målsreferens och en målsfil för huvudutdatakomponenten och sedan inaktivera alla mål.

## <a name="security-considerations"></a>Säkerhetsaspekter
Två typer av behörigheter och uppgifter används för ER-mål. En typ styr möjligheten att bibehålla de övergripande målen som har konfigurerats för en juridisk person (dvs. den styr åtkomsten till sidan **mål för elektronisk rapportering**). Den andra typen styr programanvändarens möjlighet att vid körning åsidosätta målsinställningar som är konfigurerade av en ER-utvecklare eller en ER-funktionskonsult.

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

### <a name="is-there-any-way-to-define-which-azure-storage-account-and-azure-blob-storage-are-used"></a>Finns det något sätt att definiera vilket Azure Storage-konto och vilken Azure Blob-lagring som används?

Nr. Standardlagringen för Azure Blob som är definierad och används för dokumenthanteringssystem används.

### <a name="what-is-the-purpose-of-the-file-destination-in-the-destination-settings-what-does-that-setting-do"></a>Vad är syftet med filmålen i målsinställningarna? Vad innebär inställningen?

**Fil**-målen används för att styra en dialogruta. Om du aktiverar den här målen eller om ingen mål har definierats för en konfiguration, ser du dialogrutan Öppna eller Spara efter det att en utdatafil har skapats.

### <a name="can-you-give-an-example-of-the-formula-that-refers-to-a-vendor-account-that-i-can-send-email-to"></a>Kan du ge ett exempel på en formel som refererar till ett leverantörskonto som jag kan skicka e-postmeddelande till?

Formeln är specifik för ER-konfigurationen. Till exempel, om du använder ISO 20022-konfigurationen för kreditöverföring, kan du använda **'$PaymentsForCoveringLetter'.Creditor.Identification.SourceID** eller **model.Payments.Creditor.Identification.SourceID** för att hämta ett associerat leverantörskonto.

### <a name="one-of-my-format-configurations-contains-multiple-files-that-are-group-into-one-folder-for-example-folder1-contains-file1-file2-and-file3-how-do-i-set-up-destinations-so-that-folder1zip-isnt-created-at-all-file1-is-sent-by-email-file2-is-sent-to-sharepoint-and-i-can-open-file3-immediately-after-the-configuration-is-run"></a>En av mina formatkonfigurationer innehåller flera filer som grupperade i en mapp (till exempel innehåller Mapp1 fil1, fil2 och fil3). Hur ställer jag in mål så att Folder1.zip inte skapas alla, fil1 skickas via e-post, fil2 skickas till SharePoint och jag kan öppna fil3 omedelbart efter att konfigurationen har körts?

Förutsättningen är att formatet är tillgängligt i ER-konfigurationerna. Om du har ett format kan du öppna sidan **mål för elektronisk rapportering** och skapa en ny referens till den här konfigurationen. Du måste ha fyra filmål, ett för varje utdatakomponent. Skapa den första filmålen, ge den ett namn såsom **Mapp** och välj ett filnamn som representerar en mapp i din konfiguration. Klicka på **Inställningar** och se till att alla mål är inaktiverade. För den här filmålen kommer mappen inte att skapas. På grund av hierarkiska beroenden mellan filer och överordnade mappar kommer filerna som standard att uppföra sig på samma sätt. Med andra ord skickas de inte någonstans. Om du vill åsidosätta standardbeteendet måste du skapa tre filmål till, en för varje fil. I målsinställningarna för varje mål måste du aktivera målen som filen ska skickas till.

## <a name="additional-resources"></a>Ytterligare resurser

[Översikt över elektronisk rapportering](general-electronic-reporting.md)
