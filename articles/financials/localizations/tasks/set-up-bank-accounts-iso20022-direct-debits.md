---
title: Ställ in kunder och kundbankkonton för ISO20022-autogiron
description: Den här uppgiften går igenom hur du ställer in ett kundbankkonto och ett autogiromedgivande för kund som krävs för att generera kundbetalningsfilen som ISO20022-autogiro.
author: mrolecki
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustTable, CustBankAccounts, CustDirectDebitMandate, BankAccountTableLookUp,  LogisticsAddressCityLookup
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e7d7d79b1d496223b027d800beca105ecaa0bd4c
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/15/2019
ms.locfileid: "1552458"
---
# <a name="set-up-customers-and-customer-bank-accounts-for-iso20022-direct-debits"></a>Ställ in kunder och kundbankkonton för ISO20022-autogiron

[!include [task guide banner](../../includes/task-guide-banner.md)]

Den här uppgiften går igenom hur du ställer in ett kundbankkonto och ett autogiromedgivande för kund som krävs för att generera kundbetalningsfilen som ISO20022-autogiro. Beroende på de format för kundbetalningar som har ställts in, kan ytterligare information som inte ingår i den här proceduren kanske komma att krävas för en kund eller ett kundbankkonto. 

Den här uppgiften skapades med hjälp av demonstrationsdataföretaget DEMF med en primär adress för juridisk person i Tyskland.



Detta är den fjärde av fem procedurer som demonstrerar kundbetalningsprocessen med hjälp av elektroniska rapporteringskonfigurationer.


## <a name="set-up-a-customer-bank-account"></a>Ställ in ett kundbankkonto
1. Gå till Leverantörsreskontra > Kunder > Alla kunder.
2. Använd snabbfiltret för att söka efter poster. Filtrera till exempel efter fältet Konto med värdet "DE-010".
3. Klicka på länken på den valda raden i listan.
4. Klicka på Kund i åtgärdsfönstret.
5. Klicka på bankkonton.
6. Klicka på Ny.
7. I fältet Bankkonto, skriv ett värde.
8. Skriv ett värde i fältet Namn.
    * Ange till exempel "EUR bank".  
9. Ange eller välj ett värde i fältet Bankgrupper.
10. Ange ett värde i fältet IBAN.
    * Ange till exempel "DE36200400000628808808".  
11. Skriv ett värde i fältet SWIFT-kod.
    * Ange till exempel "COBADEFFXXX".  Observera att SWIFT\BIC inte krävs för många betalningsformat, men det rekommenderas att registrera det för ett bankkonto.  
12. Klicka på Spara.
13. Stäng sidan.
14. Klicka på Redigera.
15. Expandera avsnittet Standardvärden för betalningar.
16. Ange eller välj ett värde i fältet Bankkonto.

## <a name="add-a-direct-debit-mandate"></a>Lägg till ett autogiromedgivande
1. Expandera avsnittet Autogiromedgivanden.
2. Klicka på Lägg till.
3. Ange eller välj ett värde i fältet Creditor bank account.
    * Välj till exempel "DEMF OPER".  
4. I fältet Datum för undertecknande, ange ett datum.
5. Klicka på Ja om du vill bekräfta datumuppdateringen.
6. Ange eller välj ett värde i fältet Plats för undertecknande.
7. Ange ett antal i fältet Förväntat antal betalningar.
8. Klicka på OK.
9. Klicka på Spara.

