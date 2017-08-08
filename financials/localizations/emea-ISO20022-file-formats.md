---
title: Importera ISO20022-filer
description: "I det här avsnittet beskrivs hur du importerar betalningsfiler i ISO 20022 camt.054 och pain.002-format i Microsoft Dynamics 365 for Finance and Operations, Enterprise edition."
author: neserovleo
manager: AnnBe
ms.date: 05/25/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations, UnifiedOperations
ms.search.region: Austria, Belgium, Czech Republic, Denmark, Estonia, Finland, France, Germany, Hungary, Italy, Latvia, Lithuania, Norway, Poland, Spain, Sweden, Switzerland, United Kingdom
ms.author: v-lenest
ms.search.validFrom: 2017-06-01T00:00:00.000Z
ms.dyn365.ops.version: Enterprise edition, July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 48e280bf0a6c5db237bd389fe448c9d698d3ae12
ms.openlocfilehash: acf6ed5f503d77f372d802a51a71cec062c2b24b
ms.contentlocale: sv-se
ms.lasthandoff: 07/25/2017

---

# <a name="import-iso20022-files"></a>Importera ISO20022-filer

## <a name="overview"></a>Översikt
Du kan importera betalningsfiler som har följande format:

 - **ISO20022 camt.054 kreditföreslag** – importera inkommande betalningar från en fil i det här formatet till kundbetalningsjournalen.
 - **ISO20022 pain.002 statusretur** och **ISO20022 camt.054 debetföreslag** – importera returfiler i dessa format till AP-betalningsöverföringsjournaler.

## <a name="prerequisites-for-importing-the-camt054-credit-advice-file"></a>Förutsättningar för att importera filen camt.054 kreditföreslag
Du måste slutföra följande förutsättningar för att importera bankmeddelanden i formatet camt.054.001.002 till kundbetalningsjournalen.

1. Importera **ISO20022 camt.054** konfigurationen för elektronisk rapportering (ER) från Microsoft Dynamics Lifecycle Services (LCS). Klicka sedan på sidan **kundens betalningsmetod** på fältet **Importera formatkonfiguration** och välj den konfigurationen. Mer information finns i [Filformat för betalningsmetoder](emea-select-file-formats-for-the-method-of-payments.md).
2. På sidan **alla kunder** kan du ange ett namn och organisationsnummer för varje kund.
3. På sidan **kundbankkonto** skapar du en kundbankkontopost genom att ange följande information: IBAN eller bankkontonummer och SWIFT-kod eller organisationsnummer.
4. På sidan **Bbankkonton** skapar du ett bankkonto för juridisk person genom att ange följande information: IBAN eller bankkontonummer och SWIFT-kod eller organisationsnummer, valuta och adress.

    > [!NOTE]
    > Om du planerar att använda avancerad bankavstämning, på snabbfliken **avstämning** ange alternativet **avancerad bankavstämning** till **Ja**. Om du planerar att synkronisera importerade ej bokförda betalningar, ange **Använd bankutdrag som en bekräftelse på elektroniska betalningar** till **Ja**.

5. Valfritt: På sdian **Transaktionskodsmappning** anger du mappningen mellan banktransaktionskoder i filen och banktransaktionstyper.
6. Om filen innehåller transaktionskostnader som du vill bokföra tillsammans med inkommande betalning, skapa en betalningsavgift på sidan **Kundbetalningsavgift**. Klicka sedan på sidan **betalningsmetoder**, koppla betalningsavgiften till bankkontot i betalningsavgiftsinställningarna.
7. Om ESR-betalningar ska importeras och innehåller ISR-referenser (gäller för juridiska personer i Schweiz), utför du följande inställningar:

    - I fältet **kundbetalningar, kontolängder** anger du längden på kundkoden som används för automatisk identifiering av kunden eller ISR-referenser.
    - Se till att kundnummer och fakturanummer (nummerserier) endast innehåller siffror. De får inte innehålla några andra tecken. Fakturanumret får inte ha inledande nollor.
    - Ange ESR, BESR och organisationsnummer för juridiska personens bankkonto. Mer information finns i [äldre ESR-funktion](emea-che-esr-customer-payments-import.md), eftersom det krävs liknande inställningar.
    
## <a name="import-the-camt054-credit-advice-file-into-the-customer-payment-journal"></a>Importera filen camt.054 kreditavi till kundbetalningsjournalen
1. På sidan **Rader i kundbetalningsjournal** klickar du på **funktioner** > **Importera betalningar**.
2. Välj betalningsmetod med de obligatoriska inställningarna för ISO20022 camt.054-format.
3. Ange nödvändiga parametrar och sökvägen till filen och klicka sedan på **OK**.

Filen har importerats.

## <a name="prerequisites-for-importing-files-in-the-pain002-status-return-and-camt054-debit-advice-formats-into-the-ap-payment-transfer-journal"></a>Förutsättningar för importering av fil i pain.002 statusretur och camt.054 debetavi till AP-betalningsöverföringsjournaler.
Du måste utföra följande förutsättningar för att importera bankmeddelanden i följande ISO20022-format till sidan **leverantörsbetalning** sida: pain.002.001.003 status returmeddelanden och camt.054.001.002 debetavi.

1. Importera ER-konfigurationerna **ISO20022 camt.054** och **ISO20022 pain.002** från LCS.
2. På sdian **Leverantörens betalningsmetod** i fälten den **returformatets konfiguration** och **returformatets sekundära formatkonfigurationen**, välj de ER-konfigurationer som du har importerat. Du måste aktivera allmänna elektroniska returnerade formatet för den valda betalningsmetoden.
3. På sidan **Statusmappning för returformat** anger du mappning av statuskoder mellan pain.002-status och leverantörsbetalningjournalstatus.

    Här följer ett exempel på en statusinställning.

    Returstatus | Betalningsstatus
    --------------|---------------
    RJCT          | Avvisat
    ACCP          | Godkänd
    ACSP          | Inlevererat

4. På sidan **Felkoder för returformat**, ange pain.002 felkoder och beskrivningar i enlighet med externa ISO20022 statusorsakskoder.

    Här följer ett exempel på en del av ett fel inställningar.

    Kod | Namn
    -----|-----
    AC01 | IncorrectAccountNumber
    AC02 | InvalidDebtorAccountNumber
    AC03 | InvalidCreditorAccountNumber
    AC04 | ClosedAccountNumber
    AC05 | ClosedDebtorAccountNumber
    AC06 | BlockedAccount

5. Om filen camt.054 innehåller transaktionskostnader som du vill bokföra tillsammans med inkommande betalning, skapa en betalningsavgift på sidan **Leverantörsbetalningsavgift**. Klicka sedan på sidan **betalningsmetoder**, koppla betalningsavgiften till bankkontot i betalningsavgiftsinställningarna.

## <a name="import-the-pain002-status-return-or-camt054-debit-advice-files-into-the-vendor-payment-journal"></a>Importera pain.002 statusretur eller camt.054 debetavifiler till leverantörsbetalningsjournalen
1. Öppna sidan **betalningsöverföringar** i menyn Leverantörsreskontra.
2. På sidan **betalningsöverföringar** klickar du på **Returfil - leverantör**.
3. Välj betalningsmetod med de obligatoriska inställningarna för ISO20022-filer och klicka sedan på **OK**.
4. Välj det filformat som du vill importera och klicka sedan på **OK**.
5. Ange nödvändiga parametrar och sökvägen till filen och klicka sedan på **OK**.

Om du importerar filen pain.002 uppdateras statusvärdet för leverantörens betalningsrader, baserat på informationen i den importerade filen.

Om du importerar filen camt.054 ska du ange följande ytterligare parametrar:

- **Avgifts-ID** – ange avgifts-ID som definierar de nya betalningsavgiftraderna som skapas på leverantörens utbetalningsjournalrad om ett avgiftsbelopp finns i filen camt.054.
- **Nytt journalnamn** och **ny journalbeskrivning** – ange namn och beskrivning för journalen som bearbetas av transaktioner som ska överföras till. Nytt verifikationsnummer ska tilldelas den nya journalen efter överföringen.
- **Importera autogirotransaktioner** – ange det här alternativet till **Ja** om utgående autogiro måste importeras till leverantörsbetalningsjournalen.
- **Journalnamn** – ange ett nytt journalnamn för autogiro för importerade transaktioner.
- **Kvitta transaktioner** – ange detta alternativ till **Ja** om importerade leverantörsbetalningar måste kvittas mot fakturor som finns i systemet.

Du hittar den importerade informationen på sidan **betalningsöverföringar**. 

