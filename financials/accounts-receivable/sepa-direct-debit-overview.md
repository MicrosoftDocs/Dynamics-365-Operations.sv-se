---
title: "Översikt över SEPA-autogiro"
description: "SEPA (Single Euro Payments Area) skapas av den europeiska kommissionen och anger att alla elektroniska betalningar ska betraktas som inhemska oavsett i vilket land/region personen, företaget eller organisationen och banken finns. Det finns inte någon skillnad mellan nationella och gränsöverskridande betalningar. SEPA inkluderar de 28 medlemsstaterna i Europeiska unionen samt Island, Liechtenstein, Norge, Schweiz, Monaco och San Marino. SEPA hjälper till att skapa en gemensam marknad för betalningstransaktioner inom Europeiska ekonomiska samarbetsområdet (EES). Slutligen förväntas SEPA minska antalet betalningsformat, som banker, företag och individer måste arbeta med."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: BankAccountTable, CustBankAccounts, CustParameters, CustTable
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 11144
ms.assetid: 3277c9b6-e46e-40c9-aa76-9b0449467842
ms.search.region: Global
ms.author: mfalkner
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: eb32cf1b96dfef75131b8c7541e20a93615a87f7
ms.openlocfilehash: 849fea6030c665e1724c3fc8f31353dd4bafed27
ms.lasthandoff: 03/31/2017


---

# <a name="sepa-direct-debit-overview"></a>Översikt över SEPA-autogiro

SEPA (Single Euro Payments Area) skapas av den europeiska kommissionen och anger att alla elektroniska betalningar ska betraktas som inhemska oavsett i vilket land/region personen, företaget eller organisationen och banken finns. Det finns inte någon skillnad mellan nationella och gränsöverskridande betalningar. SEPA inkluderar de 28 medlemsstaterna i Europeiska unionen samt Island, Liechtenstein, Norge, Schweiz, Monaco och San Marino. SEPA hjälper till att skapa en gemensam marknad för betalningstransaktioner inom Europeiska ekonomiska samarbetsområdet (EES). Slutligen förväntas SEPA minska antalet betalningsformat, som banker, företag och individer måste arbeta med.   

<a name="what-is-the-goal-of-sepa-direct-debits"></a>Vad är syftet med SEPA autogiro?
---------------------------------------

En SEPA direktdebitering kan en fordringshavare att samla in medel från en kunds bankkonto, förutsatt att signerade uppdrag har beviljats av kunden långivaren. Kunden signerar en fullmakt som auktoriserar fordringsägaren till att inkassera en betalning och instruerar kundens bank att betala inkasseringen. 

SEPA-autogiro skapar för första gången ett betalningsinstrument som kan användas för både nationella och gränsöverskridande autogirobetalningar i euro i alla 32 SEPA-länder/regioner. 

Det finns två tillgängliga scheman: schemat för direkt debet för SEPA och schemat för debet för SEPA företag till företag (B2B). Båda scheman använder samma filformat.

## <a name="what-is-the-core-direct-debit-scheme"></a>Vad är Core Direct Debit-schemat?
SEPA Core Direct Debit Scheme är grundschemat. Det har följande attribut:
-   Överföring av medel är i euro (även om bankkontona kan innehålla medel i andra valutor.)
-   Kunden och fordringsägaren måste båda ha ett konto hos ett kreditinstitut som finns inom SEPA.
-   Kunden måste ge en signerad fullmakt till fordringsägaren.
-   Fullmakter upphör 36 månader efter det senast initierade kravet.
-   Fordringsägaren måste lagra fullmakter så länge fullmakten är giltig och i minst 14 månader efter sista inkasso.
-   Upplägget kan användas för enkel (en gång) eller återkommande insamling av direkt debet.
-   Kunder har rättighet att ”utan frågor” få en återbetalning i upp till åtta veckor efter debiteringen på kontot.

## <a name="what-is-the-sepa-business-to-business-b2b-direct-debit-scheme"></a>Vad är SEPA B2B-schemat (Business to Business) och Direct Debit-schemat?
SEPA B2B Direct Debit Scheme gäller för B2B-transaktioner och bygger på SEPA Core Direct Debit Scheme. De största skillnaderna är:
-   SEPA B2B Direct Debit Scheme är inte tillåtet när kunden är en privatperson (konsument).
-   Kunden har inte till att få en återbetalning av en auktoriserad transaktion.
-   Kundbanker måste kontrollera att inkasseringen är godkänd genom att verifiera inkasseringen mot informationen om autogiromedgivandet. Kundbanker och kunder måste avtala om verifiering som ska utföras för varje autogiro.
-   Upplägget ger en kortare tidslinje för att presentera direkta debetar och minskar avkastningstiden.

## <a name="can-i-use-the-cor1-scheme-for-direct-debit-mandates"></a>Kan jag använda COR1-schemat för autogiromedgivanden?
Ja. Du kan använda COR1-schemat för SEPA-autogiromedgivanden i Österrike, Belgien, Tyskland, Frankrike, Italien, Spanien och Nederländerna. Upplägget ger en kortare pre-meddelande period för indrivning av direkt debet för fordringsägaren.

## <a name="what-are-international-bank-account-numbers-iban-and-bank-identifier-codes-bic"></a>Vad är internationella bankkontonummer (IBAN), och BIC-koder?
International Bank Account Number (IBAN) och Bank Identifier Code (BIC) används för att identifiera alla konton i de 32 SEPA-länderna/regionerna. Ange BIC SWIFT-koden och IBAN i fältet IBAN. Båda fälten finns på snabbfliken Ytterligare identifiering på fliken Bankkonto på sidan Bankkonton. Detta gäller för både fordringsägarens bankkonto och kundens bankkonto.

## <a name="where-do-i-enter-creditor-identifiers-direct-debit-ids"></a>Var ställer jag betalningsmottagarens identifieringsreferens (direktdebiterings-ID)?
I SEPA identifieras varje fordringshavare med ett unikt ID. Denna identifiering låter kunden och kundens bank filtrera varje autogiro och sedan dokumentera eller avvisa autogirot enligt kundinstruktioner. Fordringsägare måste begära denna identifierare från sin bank. Ange denna identifierare i fältet ID för direktdebitering för bankkontot för den juridiska personen.

## <a name="what-are-mandates"></a>Vad är medgivanden?
Kunden signerar en fullmakt som auktoriserar fordringsägaren till att inkassera en betalning och instruerar kundens bank att betala inkasseringen. Kunden kan utfärda fullmakten i pappersform eller elektroniskt. Som standard upphör medgivandet 36 månader efter att autogirot senast initierades.

## <a name="where-do-i-specify-the-sepa-direct-debit-file-format-iso-20022"></a>Var ställer jag filformatet för SEPA-autogiron (ISO 20022)?
SEPA-dataformaten baseras på ISO 20022-meddelandestandarderna. Du kommer kryssrutan allmän elektronisk rapportering och väljer debet direkt SEPA formatet som en export formatkonfigurationen när du konfigurerar konton Kundreskontra betalningsmetoder. Du använder den betalningsmetod när du skapar en betalningsfil i en kundbetalningsjournal.

## <a name="in-what-file-formats-can-i-generate-sepa-direct-debit-payment-files"></a>I vilka filformat kan jag skapa SEPA-filer för direktdebitering?
Du kan skapa elektroniska betalningsfiler för SEPA-autogiron i följande format:
-   SEPA-filer för direktdebitering i XML-formatet PAIN.008.001.02 för Belgien, Tyskland, Spanien, Frankrike, Italien och Nederländerna.
-   SEPA-filer för direktdebitering i XML-filformatet PAIN.008.001.02 för Österrike och i XML-filformatet PAIN.008.003.02 för Tyskland.

## <a name="how-do-refunds-and-returns-work-with-sepa-direct-debits"></a>Hur fungerar återbetalningar och returer med SEPA-autogiro?
Under båda scheman för SEPA-autogiro, har kunder vissa rättigheter till återbetalningar. Kunden får återkalla alla auktoriserade transaktioner under en åtta veckor lång period efter förfallodatumet utan att behöva ange en orsak. Om det handlar om obehöriga transaktioner utökas perioden till 13 månader efter förfallodatumet. Återföringar av eventuella betalningar som har gjorts manuellt med knappen Annullera betalning på sidan Kundtransaktioner.




