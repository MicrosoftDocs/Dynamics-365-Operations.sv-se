--- 
title: "Skapa fakturor för försäljningsorder"
description: "Den här uppgiftsguiden beskriver fakturering av en försäljningsorder, inklusive att sammanslå fakturor och batchbearbetning."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 11/10/2016
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
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 4b72d5b283f9401d358ee68f4650c486ebb2fd7d
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---
# <a name="create-sales-order-invoices"></a>Skapa fakturor för försäljningsorder

[!include [task guide banner](../../includes/task-guide-banner.md)]

Den här uppgiftsguiden beskriver fakturering av en försäljningsorder, inklusive att sammanslå fakturor och batchbearbetning. I den här proceduren används demonstrationsföretaget USMF.


## <a name="create-an-invoice-from-a-sales-order"></a>Skapa en faktura från en försäljningsorder.
1. Gå till Kundreskontra > Order > Levererade men inte fakturerade försäljningsorder.
2. Välj en försäljningsorder i listan. 
3. Klicka på Faktura i åtgärdsfönstret.
4. Klicka på Faktura.
    * Observera att den här försäljningsordern har flera följesedlar som associeras med den. Här visas bara ordet <multiple> i stället för följesedelsnumret.  
5. Expandera avsnittet Parametrar.
    * Bokföring måste ställas in på Ja när du vill bokföra fakturan. Du kan även stänga av bokföring och bara skriva ut fakturan. Men du kan få samma resultat genom att skapa en proformafaktura i stället för en faktura.  
    * Detta alternativ används för batchjobb. Frågan körs när batchjobbet körs.    
6. Välj "Efter" i fältet Skriv ut.
7. Välj Ja för Skriv ut faktura.
    * Med Utskriftshantering kan du skriva ut flera kopior av fakturan och också skicka fakturan med e-post som en PDF-fil.  
8. I fältet Skriv ut avgifter väljer du "Summera".
9. I checkkreditgränsfältet väljer du ”Saldo”.
10. Klicka på Avbryt.

## <a name="combine-orders-into-a-single-invoice"></a>Kombinera order till en enda faktura
1. Gå till Leverantörsreskontra > Order > Alla försäljningsorder.
2. Leta upp en kund som har flera öppna fakturor.
3. Välj en öppen försäljningsorder.
4. Visa en annan öppen försäljningsorder för samma kund.
5. Klicka på Faktura i åtgärdsfönstret.
6. Klicka på faktura.
7. Expandera avsnittet Parametrar.
8. Välj Alla i fältet Kvantitet.
    * Observera att det finns två fakturor som anges i översiktsavsnittet. Låt oss nu sammanslå dem till en enda faktura.  
9. Välj "Fakturakonto" i fältet Samlingsuppdatera.
10. Klicka på ordna så slår du ihop dessa försäljningsorder till en enda faktura.
    * Dessa två försäljningsorder sammanslås nu till en enda faktura.   
11. Klicka på Avbryt.
12. Klicka på Ja.

## <a name="post-invoices-in-a-batch"></a>Bokför fakturor i en batch
1. Gå till Kundreskontra > Fakturor > Batchfakturering > Faktura.
2. Klicka på Välj.
3. Klicka på OK.
4. Klicka på Batch.
5. Klicka på Ja om du vill slå på batchbearbetning.
6. Klicka på Upprepning.
7. Välj Dagar
8. Klicka på OK.
9. Klicka på OK.
10. Klicka på Avbryt.
11. Klicka på Ja.


