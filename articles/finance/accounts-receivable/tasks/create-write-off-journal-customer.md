---
title: Skapa en avskrivningsjournal för en kund
description: Den här uppgiftsguiden innehåller information om hur du ställer in parametrar för avskrivningar och sedan skriver av transaktioner från sidan Inkasso, sidan Öppna kundfakturor och sidan Kund.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 07/01/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustParameters, CustPosting, DefaultDashboard, CustCollectionsPoolsListPage, CustWriteOff, LedgerJournalTable, LedgerJournalTransDaily, CustCollections, CustOpenInvoicesListPage, CustTable
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: dd97f91f1ba53b56150b556fffdfed10a0c8911a
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/18/2020
ms.locfileid: "3140247"
---
# <a name="create-a-write-off-journal-for-a-customer"></a>Skapa en avskrivningsjournal för en kund

[!include [banner](../../includes/banner.md)]

Den här uppgiftsguiden innehåller information om hur du ställer in parametrar för avskrivningar och sedan skriver av transaktioner från sidan Inkasso, sidan Öppna kundfakturor och sidan Kund. I den här uppgiften används demonstrationsföretaget USMF.


## <a name="set-up-the-write-off-parameters"></a>Konfigurera avskrivningsparametrar
1. Gå till **Navigeringsfönster > Moduler > Kredit och inkasso > Inställningar > Parametrar för kundreskontra**.
2. Klicka på fliken **Inkasso.**
3. Expandera eller komprimera avsnittet **Avskrivning**.
    - **Avskrivningsjournalen** är den allmänna journal som ska innehålla de avskrivningstransaktioner som du skapar.  
    - Du kan koppla en orsakskod till varje avskrivning. Du kan åsidosätta den här standarden vid avskrivningen.  
    - Ange **Separat moms** till Ja om du vill separera momsen från den ursprungliga transaktionen i avskrivningen.  
4. Stäng sidan.
5. Gå till **Kredit och inkasso > Inställningar > Kundbokföringsprofiler**. Avskrivningskontot ska användas som utgiftskonto eller reserveringsjustering i den allmänna journalen.
6. Stäng sidan.

## <a name="write-off-a-customer-balance-from-the-aged-balances-page"></a>Skriv av en kundbalans på sidan Åldersfördelade saldon.
1. Gå till **Kredit och inkasso > Inkasso > Åldersfördelade saldon**.
2. Markera raden för den kund som du vill skriva av. Markera till exempel raden med företaget Birch.
3. I **åtgärdsfönstret**, klicka på **Inkasso**.
4. Klicka på **Skriv av**.
5. Klicka på **OK**.
6. Stäng sidan.
7. Gå till **Navigeringsfönstret > Moduler > Redovisning > Journalposter > Allmänna journaler**.
8. Välj journalbatchnumret för den journal som innehåller din avskrivning. En rad skapas för att återföra kundbalansen. En eller flera rader skapas för att bokföra avskrivningen till avskrivningskontot.  
9. Stäng sidan.
10. Stäng sidan.

## <a name="write-off-transactions-from-the-collections-form"></a>Skriv av transaktioner från inkassoformuläret.
1. Gå till **Kredit och inkasso > Inkasso > Åldersfördelade saldon**.
2. Välj namnet på kunden som har de transaktioner som du vill skriva av. Välj till exempel Cave Wholesales (US-004).
3. Markera raden för den första transaktionen.
4. Markera raden för den andra transaktionen.
5. Klicka på **Skriv av**.
6. Skriv "Dåliga skulder" i fältet **Orsakskommentar**.
7. Klicka på **OK**.
8. Stäng sidan.
9. Stäng sidan.
10. Gå till **Redovisning > Journalposter > Allmänna journaler**.
11. Välj journalbatchnumret för den journal som innehåller din avskrivning. En rad skapas för att återföra kundbalansen. En eller flera rader skapas för att bokföra avskrivningen till avskrivningskontot.  
12. Stäng sidan.
13. Stäng sidan.

## <a name="write-off-an-invoice-from-the-open-customers-invoices-page"></a>Skriv av en faktura från sidan Öppna kundfakturor
1. Gå till **Navigeringsfönster > Moduler > Kundreskontra > Fakturor > Öppna kundfakturor**.
2. Markera raden för en faktura. Markera till exempel raden för CIV-000667.
3. Klicka på **Faktura** i **åtgärdsfönstret**.
4. Klicka på **Skriv av**.
5. Klicka på **OK**.
6. Stäng sidan.

## <a name="write-off-a-customer-balance-from-the-customer-page"></a>Skriv av ett kundsaldo från sidan Kunder
1. Gå till **Leverantörsreskontra > Kunder > Alla kunder**.
2. Välj ett kundkonto. Välj till exempel US-001 (Contoso Retail San Diego).
3. I **åtgärdsfönstret**, klicka på **Inkasso**.
4. Klicka på **Skriv av**.
5. Klicka på **OK**.
6. Stäng sidan.

