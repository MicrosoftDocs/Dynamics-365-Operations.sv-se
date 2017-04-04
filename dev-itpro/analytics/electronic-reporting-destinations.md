---
title: "Destinationer för elektronisk rapportering"
description: "Du kan konfigurera en destination för varje elektronisk rapportering (ER) formatkonfiguration för elektronisk rapportering (ER) (en mapp eller en fil). Användare med rätt behörighet kan även ändra destinationsinställningarna vid körning. Den här artikeln innehåller en beskrivning av hur ER-destinationer, typer av destinationer som stöds och säkerhetsaspekter hanteras."
author: ShylaThompson
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: DocuType, ERSolutionTable
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 97423
ms.assetid: f3055a27-717a-4c94-a912-f269a1288be6
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
translationtype: Human Translation
ms.sourcegitcommit: 4d6cf88788dcc5e982e509137aa444a020137a5e
ms.openlocfilehash: d38d05fe445bf0326d408038dff84ccf8c0ff64c
ms.lasthandoff: 03/31/2017


---

# <a name="electronic-reporting-destinations"></a>Destinationer för elektronisk rapportering

Du kan konfigurera en destination för varje elektronisk rapportering (ER) formatkonfiguration för elektronisk rapportering (ER) (en mapp eller en fil). Användare med rätt behörighet kan även ändra destinationsinställningarna vid körning. Den här artikeln innehåller en beskrivning av hur ER-destinationer, typer av destinationer som stöds och säkerhetsaspekter hanteras.

Formatkonfigurationer för elektronisk rapportering (ER) innehåller vanligtvis minst en utdatakomponent: en fil. Vanligtvis innehåller konfigurationerna flera filutdatakomponenter av olika typer (till exempel XML, TXT eller XLSX) som är grupperade i en enda mapp eller i flera mappar. Med hjälp av destinationshantering för ER kan du förkonfigurera vad som händer när du kör varje komponent. Som standard när en konfiguration har körts visas dialogruta en som låter användaren spara eller öppna filen. Samma beteende uppvisas när du importerar en ER-konfiguration och inte konfigurerar några specifika destinationer för den. När du har skapat en destination för en huvudutdatakomponent åsidosätter destinationen standardbeteendet och mappen eller filen skickas enligt inställningarna för destinationen.

## <a name="availability-and-general-prerequisites"></a>Tillgänglighet och allmänna förutsättningar
ER destinationer funktionen är inte tillgänglig i Microsoft Dynamics 365 för operationer 7.0 (februari 2016)-utgåva. Därför måste du installera Microsoft Dynamics 365 för operationer (November 2016 version) att använda de funktioner som beskrivs i detta avsnitt. Du kan också installera någon av följande förutsättningar. Men tänk på att dessa alternativ ger en mer begränsad erfarenhet av ER destination.

-   Microsoft Dynamics 365 för operationer application version 7.0.1 (maj 2016)
-   [Snabbkorrigering av programvara](https://fix.lcs.dynamics.com/issue/results/?q=3160213) för ER-destinationshantering

Du kan enbart ställa in destinationer för ER-konfigurationer som har importerats och för de format som är tillgängliga på sidan **Konfigurationer för elektronisk rapportering**.

## <a name="overview"></a>Översikt
Hanteringsfunktionen för ER mål finns på **Organisationsadministration**&gt;**elektronisk rapportering**. Här kan du åsidosätta standardbeteendet för en konfiguration. Importerade konfigurationer visas inte här förrän du har klickat på **Ny** och sedan gått till fältet **Referens** och valt en konfiguration för att skapa destinationsinställningar.

[![Om du väljer en konfiguration i fältet Referens](./media/ger-destinations-2-1611-1024x574.jpg)](./media/ger-destinations-2-1611.jpg) 

När du har skapat en referens kan skapa du en filmål för varje mapp eller en fil. 

[![Skapa en plats för filen](./media/ger-destinations-1611-1024x586.jpg)](./media/ger-destinations-1611.jpg)

**Obs!** Du kan skapa en fildestination för varje utdatakomponent av samma format såsom en mapp eller en fil som väljs i fältet **Filnamn**. Du kan aktivera och inaktivera enskilda mål för filen mål i den **inställningar för utskriftsmål** dialogrutan. Knappen **Inställningar** används för att styra alla destinationer för en markerad fildestination. I dialogrutan **Destinationsinställningar** kan du styra varje destination separat genom att ställa inte alternativet **Aktiverad** för den.

[![Dialogrutan Inställningar för mål](./media/ger-destinations-settings-1611-1024x589.jpg)](./media/ger-destinations-settings-1611.jpg)

## <a name="destination-types"></a>Destinationstyper
Det finns stöd för olika destinationstyper. Du kan inaktivera eller aktivera alla typer samtidigt. På det här sättet kan du antingen inte göra någonting eller skicka komponenten till alla konfigurerade destinationer. Följande avsnitt innehåller en beskrivning av de destinationer som stöds.

### <a name="email-destination"></a>E-postdestination

Ställ in **Aktiverad **till **Ja** för att skicka en utdatafil via e-post. När det här alternativet är aktiverat kan du ange en e-postmottagare och redigera ämne och brödtext i e-postmeddelandet. Du kan skriva in konstant för rubrik och brödtext eller ER formler gör att dynamiskt skapa text för e-post. Du kan konfigurera e-postadresser för ER på två sätt. Konfigurationen kan utföras på samma sätt som funktionen Skriv ut management i Dynamics 365 för operationer fyller i den. Du kan också lösa en e-postadress genom att använda en direktreferens till ER konfigurationen via en formel.

### <a name="email-address-types"></a>Typer av e-postadress

När du klickar på **redigera** för den **till** eller **Cc** fältet den **e-post till** dialogruta. Du kan sedan välja vilken typ av e-postadress som ska användas.

[![E-dialogruta](./media/ger-destinations-email-1-1611-1024x588.jpg)](./media/ger-destinations-email-1-1611.jpg)

#### <a name="print-management"></a>Utskriftshantering

Om du väljer den **e-post för utskriftshantering** typ, ange fasta e-postadresserna i den **till** fält. Du måste välja e-källtyp för ett mål för filen för att kunna använda e-postadresser som inte åtgärdats. Följande värden kan användas: **kunden**, **leverantör**, **potentiell kund**, **kontakt**, **konkurrenten**, **arbetare**, **sökande**, **potentiell leverantör**, och **otillåten leverantör**. När du har valt en typ av e-post klickar du på knappen bredvid den **e-källkontot** fältet för att öppna den ** formeldesigner ** formulär. Du kan använda det här formuläret bifogas en formel som representerar det markerade kontot till målet för e-post.

[![Konfigurera Utskriftshantering e-typ](./media/ger-destinations-email-2-1611-1024x588.jpg)](./media/ger-destinations-email-2-1611.jpg) 

Observera att formlerna är specifika för ER-konfigurationen. Ange en dokumentspecifik referens till en kund- eller leverantörsparttyp i fältet **Formel**. I stället för skriva in datakällanoden kan du hitta den som representerar kund- eller leverantörskontot och klicka på **Lägg till datakälla** om du vill uppdatera formeln. Exempel: Om du använder ISO 20022-konfigurationen för kreditöverföring är noden som representerar ett leverantörskonto **'$PaymentsForCoveringLetter'.Creditor.Identification.SourceID**. I annat fall, ange ett strängvärde såsom **DE-001** om du vill spara en formel.

[![Formula designer](./media/ger_formuladesignerfordestination-1024x541.jpg)](./media/ger_formuladesignerfordestination.jpg)

I den **e-posta till** dialogrutan, klickar du på bin på Papperskorgen bredvid den **e-källkontot** fält om du vill ta bort formeln för källkontot e-post. Du kan också öppna formeldesigner om du vill ändra en formel som tidigare har sparats. Klicka på om du vill tilldela e-postadresser **redigera** så att den **tilldela e-postadresser** dialogrutan.

[![Tilldela e-postadresser för ett mål för e-post](./media/ger-destinations-email-3-1611-1024x587.jpg)](./media/ger-destinations-email-3-1611.jpg)

#### <a name="configuration-email"></a>Konfigurations-e-postmeddelande

Använd den här typen av e-post om den konfiguration som du använder har en nod i datakällorna som representerar en e-postadress. Du kan använda datakällor och funktioner i formeln designer för att få en korrekt formaterad e-postadress.

[![Tilldela en e-postadress datakälla för ett mål för e-post](./media/ger-destinations-email-4-1611-1024x587.jpg)](./media/ger-destinations-email-4-1611.jpg) 

**Obs!** En Simple Mail Transfer Protocol (SMTP)-server måste vara konfigurerad och tillgänglig. Du kan ange SMTP-servern i Dynamics 365 för åtgärder vid **systemadministration**&gt;**inställningar**&gt;**e**&gt;**e-parametrar**.

### <a name="archive-destination"></a>Arkivdestination

Du kan använda detta alternativ för att skicka utdata till en Microsoft SharePoint-mapp eller till Microsoft Azure Storage. Ställ in **Aktiverad** till **Ja ** för att skicka utdata till en destination som definierats av den valda dokumenttypen. Endast dokumenttyper där gruppen är inställd på **Fil** kan väljas. Du kan definiera dokumenttyper i **Organisationsadministration**&gt;**dokumenthantering**&gt;**dokumenttyper**. Konfigurationen för ER-destinationer är samma som konfigurationen för dokumenthanteringssystemet.

[![Typer av dokumentsida](./media/ger_documenttypefile-1024x542.jpg)](./media/ger_documenttypefile.jpg) 

Platsen avgör var filen sparas. Efter den **Arkiv** mål är aktiverad kan resultaten av körningen konfiguration kan sparas i arkivet för jobbet. Du kan visa resultaten vid **Organisationsadministration**&gt;**elektronisk rapportering**&gt;**elektronisk rapportering arkiverade projekt**. **Anmärkning:** väljer du en dokumenttyp för jobbet arkivet i Dynamics 365 för åtgärder vid **Organisationsadministration**&gt;**arbetsytor**&gt;**elektronisk rapportering**&gt;**elektronisk rapportering parametrar**.

#### <a name="sharepoint"></a>SharePoint

Du kan spara en fil i en viss SharePoint-mapp. Du definierar standard SharePoint server på **Organisationsadministration**&gt;**dokumenthantering**&gt;**Dokumenthanteringsparametrar**på den **SharePoint** fliken. När SharePoint-mapp har konfigurerats kan välja du det som mappen där ER utdata sparas för dokumenttypen. 

[![Markera en mapp i SharePoint](./media/ger_sharepointfolderselection-1024x543.jpg)](./media/ger_sharepointfolderselection.jpg) 

#### <a name="azure-storage"></a>Azure Storage

När dokumenttypens plats är inställd på **Arkivkatalog** kan du spara en fil i Azure Storage.

### <a name="file-destination"></a>Fildestination

Om du ställer in **aktiverad** till **Ja**, öppna eller spara i dialogrutan som visas när konfigurationen är klar.

### <a name="screen-destination"></a>Skärmen mål

Om du ställer in **aktiverad** till **Ja**, skapas en förhandsgranskning av resultatet. Du kan visa vissa filtyper, till exempel XML, TXT eller PDF-fil direkt i ett webbläsarfönster. För andra filtyper sådana Microsoft Excel eller Word, används tjänsten Microsoft Office Online.

### <a name="power-bi-destination"></a>Power BI-mål

Ange **aktiverad** till **Ja** använda konfigurationen ER för att låta överföringen av data från din version av Dynamics 365 för Microsoft Power BI-tjänster. De överförda filerna lagras på en Microsoft SharePoint Server-instans som måste konfigureras för det ändamålet. Mer information finns i [använda en konfiguration för elektronisk rapportering Power BI med data från Dynamics 365 operationer](general-electronic-reporting-report-configuration-get-data-powerbi.md). **Tips!** Om du vill åsidosätta standardbeteendet (dvs. dialogrutan för en konfiguration) kan du skapa en destinationsreferens och en destinationsfil för huvudutdatakomponenten och sedan inaktivera alla destinationer.

## <a name="security-considerations"></a>Säkerhetsaspekter
Två typer av behörigheter och uppgifter används för ER-destinationer. Objekttyp kontrollerar förmågan att upprätthålla övergripande mål som är konfigurerade för juridisk person (det vill säga det kontrollerar åtkomsten till den **elektronisk rapportering destinationer** sida). Den andra typen styr programanvändarens möjlighet att vid körning åsidosätta destinationsinställningar som är konfigurerade av en ER-utvecklare eller en ER-funktionskonsult.

| Roll (AOT-namn)                     | Rollnamn                                  | Programbehörighet (AOT-namn)                     | Programbehörighetsnamn                                                        |
|-------------------------------------|--------------------------------------------|-------------------------------------|------------------------------------------------------------------|
| ERDeveloper                         | Utvecklare för elektronisk rapportering             | ERFormatDestinationConfigure        | Konfigurera formatmål för elektronisk rapportering                |
| ERFunctionalConsultant              | Konsult för funktionen för elektronisk rapportering | ERFormatDestinationConfigure        | Konfigurera formatmål för elektronisk rapportering                |
| PaymAccountsPayablePaymentsClerk    | Ansvarig för leverantörsreskontrabetalningar            | ERFormatDestinationRuntimeConfigure | Konfigurera formatmål för elektronisk rapportering under körning |
| PaymAccountsReceivablePaymentsClerk | Ansvarig för kundreskontrabetalningar         | ERFormatDestinationRuntimeConfigure | Konfigurera formatmål för elektronisk rapportering under körning |

**Obs!** Två privilegier används i föregående uppgifter. De här privilegierna har samma namn som motsvarande uppgifter: **ERFormatDestinationConfigure** och **ERFormatDestinationRuntimeConfigure**.

## <a name="frequently-asked-questions"></a>Vanliga frågor
### <a name="i-have-imported-electronic-configurations-and-i-see-them-on-the-electronic-reporting-configurations-page-but-why-dont-i-see-them-on-the-electronic-reporting-destinations-page"></a>Jag har importerat elektroniska konfigurationer och jag ser dem på sidan Konfigurationer för elektronisk rapportering. Men Varför ser jag inte dem på sidan elektroniskt destinationer rapportering?

Se till att du markerar **New** och välj en konfiguration i den **referens** fält. På sidan **Destinationer för elektronisk rapportering** ser du bara de konfigurationer som destinationer har konfigurerats för.

### <a name="is-there-any-way-to-define-which-azure-storage-account-and-azure-blob-storage-are-used"></a>Finns det något sätt att definiera vilka Azure lagring konto och lagring av Blob Azure ska användas?

Nr. Azure Blob standardlager som definieras och används för dokumenthanteringssystemet används.

### <a name="what-is-the-purpose-of-the-file-destination-in-the-destination-settings-what-does-that-setting-do"></a>Vad är syftet med filen mål i inställningar för utskriftsmål? Vad innebär inställningen?

**Fil**-destinationen används för att styra en dialogruta. Om du aktiverar det här målet eller inget mål har definierats för en konfiguration finns en öppen eller dialogrutan Spara när en utdatafil har skapats.

### <a name="can-you-give-an-example-of-the-formula-that-refers-to-a-vendor-account-that-i-can-send-email-to"></a>Kan du ge ett exempel på en formel som refererar till ett leverantörskonto som jag kan skicka e-postmeddelande till?

Formeln är specifik för ER-konfigurationen. Till exempel, om du använder ISO 20022-konfigurationen för kreditöverföring, kan du använda **'$PaymentsForCoveringLetter'.Creditor.Identification.SourceID** eller **model.Payments.Creditor.Identification.SourceID** för att hämta ett associerat leverantörskonto.

### <a name="one-of-my-format-configurations-contains-multiple-files-that-are-group-into-one-folder-for-example-folder1-contains-file1-file2-and-file3-how-do-i-set-up-destinations-so-that-folder1zip-isnt-created-at-all-file1-is-sent-by-email-file2-is-sent-to-sharepoint-and-i-can-open-file3-immediately-after-the-configuration-is-run"></a>En av mina formatkonfigurationer innehåller flera filer som grupperade i en mapp (till exempel innehåller Mapp1 fil1, fil2 och fil3). Hur ställer jag in destinationer så att Folder1.zip inte skapas alla, fil1 skickas via e-post, fil2 skickas till SharePoint och jag kan öppna fil3 omedelbart efter att konfigurationen har körts?

Förutsättningen är att ett format måste vara tillgänglig i ER konfigurationer. Om du har ett format kan du öppna sidan **Destination för elektronisk rapportering** och skapa en ny referens till den här konfigurationen. Du måste ha fyra fildestinationer, ett för varje utdatakomponent. Skapa den första fildestinationen, ge den ett namn såsom **Mapp** och välj ett filnamn som representerar en mapp i din konfiguration. Klicka på **Inställningar** och se till att alla destinationer är inaktiverade. För den här fildestinationen kommer mappen inte att skapas. På grund av hierarkiska beroenden mellan filer och överordnade mappar kommer filerna som standard att uppföra sig på samma sätt. Med andra ord skickas de inte någonstans. Om du vill åsidosätta standardbeteendet måste du skapa tre fildestinationer till, en för varje fil. I destinationsinställningarna för varje destination måste du aktivera destinationen som filen ska skickas till.

# <a name="see-also"></a>Se även

[Översikt över elektronisk rapportering](general-electronic-reporting.md)


