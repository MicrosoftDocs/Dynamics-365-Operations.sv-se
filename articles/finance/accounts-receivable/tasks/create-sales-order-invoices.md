---
title: Skapa fakturor för försäljningsorder
description: Den tta ämne beskriver fakturering av en försäljningsorder, inklusive sammanslående av fakturor och batchbearbetning.
author: ShivamPandey-msft
ms.date: 06/25/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: SalesTableListPage, SalesEditLines,  SysQueryForm, SysRecurrence
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 3ff76eac54da6621d999d9b629fac920ba8de294
ms.sourcegitcommit: 9c4638c4bb5b5f8adc7508542a0a2c3e1de5190c
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/15/2022
ms.locfileid: "9778395"
---
# <a name="create-sales-order-invoices"></a>Skapa fakturor för försäljningsorder

[!include [banner](../../includes/banner.md)]

Den tta ämne beskriver fakturering av en försäljningsorder, inklusive sammanslående av fakturor och batchbearbetning. I den här proceduren används demonstrationsföretaget USMF.


## <a name="create-an-invoice-from-a-sales-order"></a>Skapa en faktura från en försäljningsorder.
1. Gå till **Navigeringsfönstret > Moduler > Kundreskontra > Order > Levererade men inte fakturerade försäljningsorder**.
2. Välj en försäljningsorder i listan. 
3. I **åtgärdsrutan**, klicka på **Faktura > Generera > Faktura**. Observera att den här försäljningsordern har flera följesedlar som associeras med den. Här visas bara ordet *multipel* i stället för följesedelsnumret.  
4. Expandera avsnittet **Parametrar**.
    - Bokföring måste ställas in på **Ja** när du vill bokföra fakturan. Du kan även stänga av bokföring och bara skriva ut fakturan. Men du kan få samma resultat genom att skapa en proformafaktura i stället för en faktura.  
    - Detta alternativ används för batchjobb. Frågan körs när batchjobbet körs.
5. I fältet **Skriv ut**, välj **Efter**.
6. Välj **Ja** för **Skriv ut faktura**. Med Utskriftshantering kan du skriva ut flera kopior av fakturan och också skicka fakturan med e-post som en PDF-fil.  
7. I fältet **Skriv ut avgifter** väljer du **Summera**.
8. I fältet **checkkreditgräns** väljer du **Saldo**.
9. Klicka på **Avbryt**.

## <a name="combine-orders-into-a-single-invoice"></a>Kombinera order till en enda faktura
1. Gå till **Navigeringsfönstret > Moduler > Kundreskontra > Order > Alla försäljningsorder**.
2. Leta upp en kund som har flera öppna fakturor.
3. Välj flera öppna försäljningsorder från samma kund.
4. I **åtgärdsrutan**, klicka på **Faktura > Generera > Faktura**.
5. Expandera avsnittet **Parametrar**.
6. I fältet **Kvantitet**, välj **Alla**. Observera att det finns två fakturor som anges i översiktsavsnittet. Låt oss nu sammanslå dem till en enda faktura.  
7. I fältet **Samlingsuppdatering för**, välj **Fakturakonto**.
8. Klicka på **ordna** så slår du ihop dessa försäljningsorder till en enda faktura. Dessa två försäljningsorder sammanslås nu till en enda faktura.   
9. Klicka på **Avbryt**.
10. Klicka på **Ja**.

## <a name="post-invoices-in-a-batch"></a>Bokför fakturor i en batch
1. Gå till **Navigeringsfönster > Moduler > Kundreskontra > Fakturor > Batchfakturering > Faktura**.
2. Klicka på **Välj**.
3. Klicka på **OK**.
4. Klicka på **batch**.
5. Välj **Ja** i **batchbearbetning**.
6. Klicka på **Upprepning.**
7. Välj **Dagar**
8. Klicka på **OK**.
9. Klicka på **OK**.
10. Klicka på **Avbryt**.
11. Klicka på **Ja**.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
