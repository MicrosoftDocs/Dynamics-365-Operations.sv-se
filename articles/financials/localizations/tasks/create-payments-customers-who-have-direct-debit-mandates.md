--- 
title: "Skapa betalningar för en kund som har autogiromedgivanden"
description: "Denna uppgift visar hur du skapar en ISO20022-betalningsfil för autogiro för en kund som har autogiro konfigurerat och en faktura som ska betalas."
author: mrolecki
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CustFreeInvoice, CustTableLookup, CustPostInvoiceJob, LedgerJournalTable, LedgerJournalTransCustPaym, SysQueryForm, CustPaymProposalEdit, BankAccountTableLookUp
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: acd6a8076288d8d1d1aa05af33e306c6a29780f7
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---
# <a name="create-payments-for-a-customer-who-have-direct-debit-mandates"></a>Skapa betalningar för en kund som har autogiromedgivanden

[!include [task guide banner](../../includes/task-guide-banner.md)]

Denna uppgift visar hur du skapar en ISO20022-betalningsfil för autogiro för en kund som har autogiro konfigurerat och en faktura som ska betalas. Att skapa och bokföra en faktura är valfritt. Istället för att ha en faktura som ska betalas kan du välja en fullmakt i en journal innan du genererar en betalningsfil, detta för att stödja ett scenario för kundförskottsbetalning.



Det demonstrationsdataföretag som används för att skapa den här proceduren är DEMF.



Detta är den femte av fem procedurer av fem som demonstrerar kundbetalningsprocessen med hjälp av elektroniska rapporteringskonfigurationer. Innan du kan slutföra uppgiften, måste du genomföra de föregående uppgifterna. Du måste först importera konfigurationer för elektronisk rapportering om kundbetalning, konfigurera betalningsmetoder och konfigurerar ditt företag och dina kunduppgifter. 


## <a name="post-a-free-text-invoice-with-direct-debit-information"></a>Bokför en fritextfaktura med information om direktdebitering
1. Gå till Kundreskontra > Fakturor > Alla fritextfakturor.
2. Klicka på Ny.
3. I fältet Kundkonto, ange eller välj ett värde.
    * Välj till exempel DE-010.  
4. Ange eller välj ett värde i fältet Betalningsmetod.
    * Till exempel: välj "Electronic".  
5. Ange eller välj ett värde i fältet Autogiromedgivande-ID.
6. Klicka på Lägg till rad.
7. Skriv ett värde i fältet Beskrivning.
8. Ange önskade värden i fältet Huvudkonto.
9. Ange ett tal i fältet Enhetspris.
10. Klicka på Bokför.
11. Klicka på OK.

## <a name="create-a-payment"></a>Skapa en betalning
1. Gå till Kundreskontra > Betalningar > Betalningsjournal.
2. Klicka på Ny.
3. Ange eller välj ett värde i fältet Namn.
4. Klicka på Rader.
5. Klicka på Betalningsförslag.
6. Klicka på Skapa betalningsförslag.
7. Expandera avsnittet Poster som ska ingå.
8. Klicka på Filter.
9. Markera raden för kundtransaktionregistret och fältet Betalningsmetod i listan.
    * Du kan använda valfria villkor för att välja kundtransaktioner för betalning. Använd "Electronic" som en betalningsmetod för att filtrera transaktioner i det här exemplet.  
10. Ange eller välj ett värde i fältet Kriterier.
11. Klicka på OK.
12. Klicka på OK.
13. Klicka på Skapa betalningar.

## <a name="generate-a-payment-file"></a>Generera en betalningsfil


