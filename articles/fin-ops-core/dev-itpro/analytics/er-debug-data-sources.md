---
title: Felsöka datakällor i ett kört ER-format för analys av dataflöde och omvandling
description: I det här avsnittet beskrivs hur du kan felsöka datakällorna i ett exekverat ER-format för att bättre förstå det konfigurerade dataflödet och omvandlingen.
author: NickSelin
manager: AnnBe
ms.date: 04/22/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERSolutionTable, EROperationDesigner
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2020-04-01
ms.dyn365.ops.version: Release 10.0.11
ms.openlocfilehash: 3a486800f37dda7829aeeaa56a30285a92a61b9d
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/05/2020
ms.locfileid: "4680792"
---
# <a name="debug-data-sources-of-an-executed-er-format-to-analyze-data-flow-and-transformation"></a>Felsöka datakällor i ett kört ER-format för analys av dataflöde och omvandling

[!include[banner](../includes/banner.md)]

[!include[banner](../includes/preview-banner.md)]

När du [konfigurerar](tasks/er-format-configuration-2016-11.md) en elektronisk rapportlösning (ER) för att generera elektroniska dokument, definierar du den metod som används för att hämta data från programmet och anger den i genererad utdata. För att du ska kunna göra livscykelsupport för ER-lösningen mer effektiv bör din lösning bestå av en ER [datamodell ](general-electronic-reporting.md#DataModelComponent)och dess [mappnings](general-electronic-reporting.md#ModelMappingComponent)-komponenter, och också ett återställnings[format ](general-electronic-reporting.md#FormatComponentOutbound) med dess mappningskomponenter så att modellmappningen är programspecifik, medan andra komponenter fortfarande är programagnostiska. Därför kan flera ER-komponenter [påverka](general-electronic-reporting.md#FormatComponentOutbound) processen att ange data i den genererade utmatningen.

Ibland ser data i den genererade utmatningen annorlunda ut än samma data i programdatabasen. I dessa fall vill du ta reda på vilken ER-komponent som ansvarar för dataomvandlingen. Funktionen för felsökning av ER-datakällan minskar markant både tid och kostnad för undersökningen. Du kan avbryta körningen av ett ER-format och öppna gränssnittet för datakällans felsökning. Där kan du bläddra bland tillgängliga datakällor och välja en enskild datakälla att köra. Denna manuella körning simulerar körning av datakällan när ett ER-format körs på riktigt. Resultatet visas på en sida där du kan analysera de data som har tagits emot.

Om du vill aktivera funktionen för felsökning av datakälla anger du alternativet **Aktivera datafelsökning vid formatkörning** till **Ja** i ER:s användarparametrar. Du kan sedan starta felsökningen av datakällan när du kör ett ER-format för att generera utgående dokument. Du kan också använda alternativet **Starta felsökning** om du vill initiera felsökning av datakällor för ett ER-format som har konfigurerats i [ER-åtgärdsdesigner](./tasks/er-format-configuration-2016-11.md#design-the-format-of-an-electronic-document).

Det här avsnittet innehåller riktlinjer för initiering av felsökning av datakällor för körda ER-format. Det förklarar hur informationen kan hjälpa dig att förstå dataflödet och dataomvandlingar. I exemplen i det här avsnittet används affärsprocessen för bearbetning av leverantörsbetalningar.

## <a name="limitations"></a>Begränsningar

Datakällans felsökare kan användas för att få åtkomst till datakällor som används i ER-format för att generera utgående dokument. Den kan inte användas för att felsöka datakällor i ER-format som är utformade för att tolka inkommande dokument.

Följande inställningar för ER-format är för närvarande inte tillgängliga för felsökning av datakällor:

- Formatomvandlingar
- Formatera och mappa valideringsregler
- Aktivera uttryck
- Information om datainsamling i minnet

## <a name="prerequisites"></a>Förutsättningar

- Om du vill slutföra exemplen i det här avsnittet måste du ha tillgång till en av följande [roller](../sysadmin/tasks/assign-users-security-roles.md):

    - Utvecklare för elektronisk rapportering
    - Konsult för funktionen för elektronisk rapportering
    - Systemadministratör

- Företaget måste vara inställt på **DEMF**.

- Följ instruktionerna i [Bilaga 1](#appendix1) i det här avsnittet för att hämta komponenterna för den Microsoft ER-lösning som krävs för att bearbeta leverantörsbetalningar.
- Följ instruktionerna i [Bilaga 2](#appendix2) till det här avsnittet för att förbereda leverantörsreskontra för bearbetning av leverantörsbetalningar genom att använda den ER-lösning som du ska hämta.

## <a name="process-a-vendor-payment-to-get-a-payment-file"></a>Bearbeta en leverantörsbetalning för att få en betalningsfil

1. Följ instruktionerna i [Bilaga 3](#appendix3) till det här avsnittet för att bearbeta leverantörsbetalningar.

    ![Bearbetning av leverantörsbetalningar pågår](./media/er-data-debugger-process-payment.png)

2. Hämta och spara zip-filen på din lokala dator.
3. Packa upp betalningsfilen **ISO20022 Credit transfer.xml** från zip-filen.
4. Öppna den extraherade betalningsfilen med hjälp av XML-granskaren.

    I betalningsfilen finns IBAN-koden (International Bank Account Number) för leverantörens bankkonto utan blanksteg. Därför skiljer det sig från värdet som [angavs](#enteredIBANcode) på sidan **Bankkonton**.

    ![IBAN-kod utan blanksteg](./media/er-data-debugger-payment-file.png)

    Du kan använda felsökaren för ER-datakälla om du vill veta vilken del av ER-lösningen som används för att ta bort blanksteg i IBAN-koden.

## <a name="turn-on-data-source-debugging"></a>Aktivera felsökning av datakälla

1. Gå till **Organisationsadministration** \> **Elektronisk rapportering** \> **Konfigurationer**.
2. På sidan **Konfigurationer** i åtgärdsfönstret, på fliken **Konfigurationer** i gruppen **Avancerad inställningar** markerar du **Använd parametrar**.
3. Ställ in alternativet **Aktivera felsökning av data vid formatkörning** som **Ja**.

    > [!NOTE]
    > Den här parametern är specifik för användaren och företaget.

    ![Dialogruta Användarparametrar](./media/er-data-debugger-user-parameters.png)

## <a name="process-a-vendor-payment-for-debugging"></a>Bearbeta en leverantörsbetalning för felsökning

1. Följ instruktionerna i [Bilaga 3](#appendix3) till det här avsnittet för att bearbeta leverantörsbetalningar.
2. I meddelanderutan väljer du **Ja** för att bekräfta att du vill avbryta bearbetning av leverantörsbetalningar och i stället starta felsökning av datakällor på sidan **Felsökning av datakällor**.

    ![Ruta för bekräftelsemeddelande](./media/er-data-debugger-start-debugging.png)

## <a name="debug-data-sources-that-are-used-in-payment-processing"></a>Felsökning av datakällor som används vid betalningsbearbetning

### <a name="debug-the-model-mapping"></a>Felsöka modellmappningen

1. På sidan **Felsök datakällor**, i åtgärdsfönstret, väljer du **Modellmappning** för att starta felsökning från denna ER-komponent.
2. Markera datakällan **\$notSentTransactions** i fönstret med datakällor till vänster och välj sedan **Läs alla poster**.

    Du kan välja **Läs 1 post**, **Läs 10 poster**, **Läs 100 poster** eller **Läs alla poster** för att tvinga korrekt antal poster att läsas från den valda datakällan. På så sätt kan du simulera åtkomst till datakällan från det pågående ER-formatet.

3. I datarutan till höger, välj **Expandera allt**.

    Du ser att den valda datakällan för **postlistetypen** innehåller en enda post.

4. Expandera datakällan **\$notSentTransactions** och välj den kapslade metoden **vendBankAccountInTransactionCompany()**.
5. Expandera metoden **vendBankAccountInTransactionCompany()** och välj det kapslade fältet **IBAN**.
6. Välj **Hämta värde**.

    Du kan välja **Hämta värde** för att tvinga värdet i ett markerat fält i den valda datakällan att läsas. På så sätt kan du simulera åtkomst till fältet i fråga från det pågående ER-formatet.

7. Välj **Expandera alla**.

    ![Värdet i IBAN-fältet i modellmappningen](./media/er-data-debugger-debugging-model-mapping.png)

    Som du ser är modellmappningen inte ansvarig för avkortningar, eftersom IBAN-koden som den returnerar för leverantörens bankkonto innehåller blanksteg. Därför måste du fortsätta felsökningen av datakällan.

### <a name="debug-the-format-mapping"></a>Felsök formatmappningen

1. På sidan **Felsök datakällor** väljer du i åtgärdsfönstret **Formatmappning** för att fortsätta felsökning från denna ER-komponent.
2. Välj datakällan **\$PaymentByDebtor** och välj sedan **Läs alla poster**.
3. Expandera **\$PaymentByDebtor**.
4. Expandera **\$PaymentByDebtor.Lines** och välj sedan **Läs alla poster**.
5. Expandera **\$PaymentByDebtor.Lines.CreditorAccount**.
6. Expandera **\$PaymentByDebtor.Lines.CreditorAccount.Identification** och välj sedan **\$PaymentByDebtor.Lines.CreditorAccount.Identification.IBAN**.
7. Välj **Hämta värde**.
8. Välj **Expandera alla**.

    ![Värdet i IBAN-fältet i formatmappningen](./media/er-data-debugger-debugging-format-mapping.png)

    Som du ser är datakällorna för formatmappningen inte ansvariga för avkortningar, eftersom IBAN-koden som de returnerar för leverantörens bankkonto innehåller blanksteg. Därför måste du fortsätta felsökningen av datakällan.

### <a name="debug-the-format"></a>Felsök formatet

1. På sidan **Felsök datakällor** väljer du **Format** i åtgärdsfönstret för att fortsätta felsökning från denna ER-komponent.
2. Expandera formatelementen för att välja **ISO20022CTReports** \> **XMLHeader** \> **Document** \> **CstmrCdtTrfInitn** \> **PmtInf** och välj sedan **Läs alla poster**.
3. Expandera formatelementen för att välja **ISO20022CTReports** \> **XMLHeader** \> **Document** \> **CstmrCdtTrfInitn** \> **PmtInf** \> **CdtTrfTxInf** och välj sedan **Läs alla poster**.
4. Expandera formatelementen för att välja **ISO20022CTReports** \> **XMLHeader** \> **Document** \> **CstmrCdtTrfInitn** \> **PmtInf** \> **CdtTrfTxInf** \> **CdtrAcct** \> **Id** \> **IBAN** \> **BankIBAN** och välj sedan **Hämta värde**.
5. Välj **Expandera alla**.

    ![Värdet i IBAN-fältet i formatet](./media/er-data-debugger-debugging-format.png)

   Som du ser är formatbindningen inte ansvarig för avkortningar, eftersom IBAN-koden som den returnerar för leverantörens bankkonto innehåller blanksteg. Därför konfigureras elementet **BankIBAN** att använda formatomvandling som avkortar blanksteg.

6. Stäng felsökaren för datakälla.

### <a name="review-the-format-transformations"></a>Granska formatomvandlingarna

1. Gå till **Organisationsadministration** \> **Elektronisk rapportering** \> **Konfigurationer**.
2. På sidan **Konfigurationer** väljer du **Betalningsmodell** \> **ISO20022-kreditöverföring**.
3. Välj **Designer** och expandera sedan elementen för att välja **Document** \> **CstmrCdtTrfInitn** \> **PmtInf** \> **CdtTrfTxInf** \> **CdtrAcct** \> **Id** \> **IBAN** \> **BankIBAN**.

    ![BankIBAN-element på sidan Formatdesigner](./media/er-data-debugger-referred-transformation.png)

    Som du ser är elementet **BankIBAN** konfigurerat att använda **ta bort icke alfanumerisk** omvandling.

4. Välj fliken **Omvandlingar**.

    ![Fliken omvandlingar för BankIBAN-elementet](./media/er-data-debugger-transformation.png)

    Som du ser konfigureras omvandlingen **ta bort icke alfanumeriska** att använda ett uttryck som avkortar blanksteg från den angivna textsträngen.

## <a name="start-to-debug-in-the-operation-designer"></a>Starta felsökning i åtgärdsdesigner

När du konfigurerar en utkastversion av ER-format som kan köras direkt från åtgärdsdesignern, kan du öppna felsökningen för datakälla genom att välja **Starta felsökning** i åtgärdsfönstret.

![Knappen Starta felsökning på sidan formatdesigner](./media/er-data-debugger-run-from-designer.png)

Formatmappning och formatkomponenter för ER-formatet som redigeras är tillgängliga för felsökning.

## <a name="start-to-debug-in-the-model-mapping-designer"></a>Starta felsökning i modellmappningsdesigner

När du konfigurerar en ER-modellmappning som kan köras från sidan **Modellmappning** kan du öppna felsökning för datakälla genom att välja **Starta felsökning** i åtgärdsfönstret.

![Knappen Starta felsökning på sidan modellmappningsdesigner](./media/er-data-debugger-run-from-designer-mapping.png)

Modellmappningskomponenten i ER-mappningen som redigeras är tillgänglig för felsökning.

## <a name="appendix-1-get-an-er-solution"></a><a name="appendix1"></a>Bilaga 1: Hämta en ER-lösning

### <a name="download-an-er-solution"></a>Hämta en ER-lösning

Om du vill använda en ER-lösning för att generera en elektronisk betalningsfil för en leverantörsbetalning som bearbetas, kan du [hämta](download-electronic-reporting-configuration-lcs.md) ER-betalningsformatet **ISO20022-kreditöverföring** som finns i det delade resursbiblioteket i Microsoft Dynamics Lifecycle Services (LCS) eller i den globala databasen.

![Importera ER-betalningsformatet på sidan konfigurationsdatabas](./media/er-data-debugger-import-from-repo.png)

Förutom det valda ER-formatet måste följande [konfigurationer](general-electronic-reporting.md#Configuration) automatiskt importeras till din Microsoft Dynamics 365 Finance-instans som del av ER-lösningen **ISO20022-kreditöverföring**:

- **Betalningsmodell** [ER-datamodellkonfiguration](general-electronic-reporting.md#DataModelComponent)
- **ISO20022-kreditöverföring** [ER-formatkonfiguration](general-electronic-reporting.md#FormatComponentOutbound)
- **Betalningsmodellmappning 1611** [ER-modellmappningskonfiguration](general-electronic-reporting.md#ModelMappingComponent)
- **Betalningsmodellmappning till destination ISO20022** ER-modellmappningskonfiguration

Du hittar dessa konfigurationer på sidan **Konfigurationer** i ER-ramverket (**Organisationsadministration** \> **Elektronisk rapportering** \> **Konfigurationer**).

![Importerade konfigurationer på sidan Konfigurationer](./media/er-data-debugger-configurations.png)

Om några av de tidigare listade konfigurationerna saknas i konfigurationsträdet måste du hämta dem manuellt från LCS delade resursbibliotek på samma sätt som du har hämtat ER-betalningsformatet **ISO20022 kreditöverföring**.

### <a name="analyze-the-downloaded-er-solution"></a>Analysera den hämtade ER-lösningen

#### <a name="review-the-model-mapping"></a>Granska modellmappningen

1. Gå till **Organisationsadministration** \> **Elektronisk rapportering** \> **Konfigurationer**.
2. Välj **Betalningsmodell** \> **Betalningsmodellmappning 1611**.
3. Välj **Designer**.
4. Välj mappningsposten **Betalningsmodellmappning ISO20022 CT**.
5. Välj **Designer** och granska sedan modellmappningen som öppnas.

    Observera att fältet **Betalningar** i datamodellen är knutet till datakällan **\$notSentTransactions** som returnerar listan med leverantörsbetalningsrader som bearbetas.

    ![Fältet Betalningar på sidan modellmappningsdesigner](./media/er-data-debugger-model-mapping.png)

#### <a name="review-the-format-mapping"></a>Granska formatmappningen

1. Gå till **Organisationsadministration** \> **Elektronisk rapportering** \> **Konfigurationer**.
2. Välj **Betalningsmodell** \> **ISO20022 kreditöverföring**.
3. Välj **Designer**.
4. På fliken **Mappning** granskar du formatmappningen som öppnas.

    Observera att elementet **Dokument** \> **CstmrCdtTrfInitn** \> **PmtInf** i **ISO20022CTReports** \> **XMLHeader**-filen är knutet till datakällan **\$PaymentByDebtor** som är konfigurerad för att gruppera poster i datamodellens fält **Betalningar**.

    ![PmtInf-element på sidan Formatdesigner](./media/er-data-debugger-format-mapping.png)

#### <a name="review-the-format"></a>Granska formatet

1. Gå till **Organisationsadministration** \> **Elektronisk rapportering** \> **Konfigurationer**.
2. Välj **Betalningsmodell** \> **ISO20022 kreditöverföring**.
3. Välj **Designer** och granska sedan formatet som öppnas.

    Observera att formatelementet under **Dokument** \> **CstmrCdtTrfInitn** \> **PmtInf** \> **CdtTrfTxInf** \> **CdtrAccts** \> **ID** \> **IBAN** \> **BankIBAN** har konfigurerats för att ange IBAN-kod för leverantörens konto i betalningsfilen.

    ![BankIBAN-element på sidan Formatdesigner](./media/er-data-debugger-format.png)

## <a name="appendix-2-configure-accounts-payable"></a><a name="appendix2"></a>Bilaga 2: Konfigurera leverantörsreskontra

### <a name="modify-a-vendor-property"></a>Ändra en leverantörsegenskap

1. Gå till **Leverantörsreskontra** \> **Leverantörer** \> **Alla leverantörer**.
2. Välj leverantör **DE-01002** och sedan, i åtgärdsfönstret på fliken **Leverantör**, i gruppen **Ställ in** väljer du **Bankkonton**.
3. På snabbfliken **Identifiering**, i fältet **IBAN**, <a name="enteredIBANcode"></a>anger du **GB33 BUKB 2020 1555 5555 55**.
4. Välj **Spara**.

![IBAN-fält inställt på sidan Leverantörsbankkonton](./media/er-data-debugger-iban.png)

### <a name="set-up-a-method-of-payment"></a>Skapa betalningsmetod

1. Gå till **Leverantörsreskontra** \> **Betalningsinställning** \> **Betalningsmetoder**.
2. Välj betalningsmetod **SEPA CT**.
3. På snabbfliken **Filformat**, avsnittet **Filformat**, ställer du in alternativet **Allmänt elektroniskt exportformat** till **Ja**.
4. I fältet **Exportformatkonfiguration** väljer du ER-formatet **ISO20022 kredit överföring**.
5. Välj **Spara**.

![Filformatinställningar på sidan Betalningsmetoder](./media/er-data-debugger-payment-method.png)

### <a name="add-a-vendor-payment"></a>Lägg till en leverantörsbetalning

1. Gå till **Leverantörsreskontra** \> **Betalningar** \> **Leverantörsbetalningsjournal**.
2. Lägg till en ny betalningsjournal.
3. Välj **Rader** och lägg till en ny betalningsrad.
4. I fältet **Konto** väljer du leverantör **DE-01002**.
5. I fältet **Debit** anger du ett värde.
6. I fältet **Betalningsmetod** väljer du **SEPA CT**.
7. Välj **Spara**.

![Leverantörsbetalning har lagts till på sidan Leverantörsbetalningar](./media/er-data-debugger-payment-journal.png)

## <a name="appendix-3-process-a-vendor-payment"></a><a name="appendix3"></a>Bilaga 3: Bearbeta leverantörsbetalningstransaktioner

1. Gå till **Leverantörsreskontra** \> **Betalningar** \> **Leverantörsbetalningsjournal**.
2. På sidan **Leverantörsbetalningsjournal** väljer du den betalningsjournal som du skapade tidigare och väljer sedan **Rader**.
3. Markera betalningsraden och välj **Betalningsstatus** \> **Ingen**.
4. Välj **Generera betalningar**.
5. I fältet **Betalningsmetod** väljer du **SEPA CT**.
6. I fältet **Bankkonto** väljer du **DEMF OPER**.
7. I dialogrutan **Generera betalningar** väljer du **OK**.
8. I dialogrutan **Parametrar för elektronisk rapportering** väljer du **OK**.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]