--- 
title: "Skapa en avskrivningsjournal för en kund"
description: "Den här uppgiftsguiden innehåller information om hur du ställer in parametrar för avskrivningar och sedan skriver av transaktioner från sidan Inkasso, sidan Öppna kundfakturor och sidan Kund."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: 1c7ecd07c294b7357e4bda9f4183deb346b3e6ee
ms.contentlocale: sv-se
ms.lasthandoff: 07/27/2017

---
# <a name="create-a-write-off-journal-for-a-customer"></a>Skapa en avskrivningsjournal för en kund

[!include[task guide banner](../../includes/task-guide-banner.md)]

Den här uppgiftsguiden innehåller information om hur du ställer in parametrar för avskrivningar och sedan skriver av transaktioner från sidan Inkasso, sidan Öppna kundfakturor och sidan Kund. I den här uppgiften används demonstrationsföretaget USMF.


## <a name="set-up-the-write-off-parameters"></a>Konfigurera avskrivningsparametrar
1. Gå till Kredit och inkasso > Setup > Parametrar för kundreskontra.
2. Klicka på fliken Inkasso.
3. Expandera eller komprimera avsnittet Avskrivning.
    * Avskrivningsjournalen är den allmänna journal som ska innehålla de avskrivningstransaktioner som du skapar.  
    * Du kan koppla en orsakskod till varje avskrivning. Du kan åsidosätta den här standarden vid avskrivningen.  
    * Ange detta till Ja om du vill separera momsen från den ursprungliga transaktionen i avskrivningen.  
4. Stäng sidan.
5. Gå till Kredit och inkasso > Inställningar > Kundbokföringsprofiler.
    * Avskrivningskontot ska användas som utgiftskonto eller reserveringsjustering i den allmänna journalen   
6. Stäng sidan.

## <a name="write-off-a-customer-balance-from-the-aged-balances-page"></a>Skriv av en kundbalans på sidan Åldersfördelade saldon.
1. Gå till Kredit och inkasso > Inkasso > Åldersfördelade saldon.
2. Markera raden för den kund som du vill skriva av. Markera till exempel raden med företaget Birch.
3. Klicka på Inkasso i åtgärdsfönstret.
4. Klicka på Skriv av.
5. Klicka på OK.
6. Stäng sidan.
7. Gå till Redovisning > Journalposter > Allmänna journaler.
8. Välj journalbatchnumret för den journal som innehåller din avskrivning.
    * En rad skapas för att återföra kundbalansen. En eller flera rader skapas för att bokföra avskrivningen till avskrivningskontot.  
9. Stäng sidan.
10. Stäng sidan.

## <a name="write-off-transactions-from-the-collections-form"></a>Skriv av transaktioner från inkassoformuläret.
1. Gå till Kredit och inkasso > Inkasso > Åldersfördelade saldon.
2. Välj namnet på kunden som har de transaktioner som du vill skriva av. Välj till exempel Cave Wholesales (US-004).
3. Markera raden för den första transaktionen.
4. Markera raden för den andra transaktionen.
5. Klicka på Skriv av.
6. Skriv "Dåliga skulder" i fältet Orsakskommentar.
7. Klicka på OK.
8. Stäng sidan.
9. Stäng sidan.
10. Gå till Redovisning > Journalposter > Allmänna journaler.
11. Välj journalbatchnumret för den journal som innehåller din avskrivning.
    * En rad skapas för att återföra kundbalansen. En eller flera rader skapas för att bokföra avskrivningen till avskrivningskontot.  
12. Stäng sidan.
13. Stäng sidan.

## <a name="write-off-an-invoice-from-the-open-customers-invoices-page"></a>Skriv av en faktura från sidan Öppna kundfakturor
1. Gå till Kundreskontra > Fakturor > Öppna kundfakturor.
2. Markera raden för en faktura. Markera till exempel raden för CIV-000667.
3. Klicka på Faktura i åtgärdsfönstret.
4. Klicka på Skriv av.
5. Klicka på OK.
6. Stäng sidan.

## <a name="write-off-a-customer-balance-from-the-customer-page"></a>Skriv av ett kundsaldo från sidan Kunder
1. Gå till Leverantörsreskontra > Kunder > Alla kunder.
2. Välj ett kundkonto. Välj till exempel US-001 (Contoso Retail San Diego).
3. Klicka på Inkasso i åtgärdsfönstret.
4. Klicka på Skriv av.
5. Klicka på OK.
6. Stäng sidan.

