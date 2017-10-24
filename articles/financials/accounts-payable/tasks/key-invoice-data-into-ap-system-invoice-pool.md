--- 
title: "Mata in fakturadata i LR-systemet genom att använda fakturapool"
description: "Den här uppgifthandbok visas om hur du använder ankomstregistreringen om du vill skapa fakturor."
author: abruer
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
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 96040b1c1ba130f773ba0defbf7bf1dcebedfc13
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---
# <a name="key-invoice-data-into-the-ap-system-using-invoice-pool"></a>Mata in fakturadata i LR-systemet genom att använda fakturapool

[!include[task guide banner](../../includes/task-guide-banner.md)]

Den här uppgifthandbok visas om hur du använder ankomstregistreringen om du vill skapa fakturor.  Använd sedan fakturapoolen för att matcha fakturan till en inköpsorder och för att slutföra utgiften i leverantörsfakturasidan.


## <a name="create-a-purchase-order"></a>Skapa en inköpsorder
1. Gå till Leverantörsreskontra > Inköpsorder > Inköpsorder.
2. Skapa en inköpsorder genom att klicka på Nytt.
3. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Vendor account.
4. Välj leverantören i listan. Till exempel visas leverantör 1001.
5. Klicka på OK.
6. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Item number.
7. Hitta tjänstartikelnumret i listan. Välj till exempel S0001.
8. Klicka på artikelnumret och välj det.
    * Nettobeloppet är 75.00.  Det är det belopp som ska förvänta vi på fakturan.  
9. Klicka på Inköp i åtgärdsfönstret.
10. Klicka på Bekräfta.

## <a name="create-and-post-and-invoice"></a>Skapa och bokför och fakturera
1. Gå till Leverantörsreskontra > Fakturor > Fakturaregister.
2. Klicka på Ny.
3. Öppna sökningen för att välja namnet på det fakturaregister som du vill använda.
4. Välj namnet på det fakturaregister som du vill använda.
5. Klicka på på Rader om du vill öppna registret och ange utgiftsrader.
6. Välj en leverantör i sökningen. Klicka till exempel på leverantör 1001.
7. Ange fakturanumret i fältet Faktura.
8. Skriv ett värde i fältet Beskrivning.
9. Välj ett tal i fältet Kredit.
10. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Purchase order.
11. Välj inköpsordern som du skapat förut.
12. Öppna sökningen genom att klicka på den nedrullningsbara knappen Approved by.
13. Välj en godkännare och klicka sedan på Välj om du vill välja den godkännaren.
14. Klicka på Bokför.
15. Stäng formuläret.
16. Stäng formuläret.

## <a name="open-an-invoice-from-the-pool-and-match-it-to-a-purchase-order-to-complete-the-invoice-process"></a>Öppna en faktura från poolen och matcha den till en inköpsorder för att slutföra fakturaprocessen
1. Gå till Leverantörsreskontra > Fakturor > Fakturapool.
2. Klicka på Inköpsorder om du vill skapa en leverantörsfaktura från fakturan i poolen.
3. Välj fakturan som du vill granska.
4. Klicka på Uppdatera matchningsstatus så utförs matchningen.
5. Klicka på Alternativ i åtgärdsfönstret.
6. Klicka på Ändra vy.
7. Klicka på Diagramvy.
8. Klicka på Bokför.
9. Stäng formuläret.
10. Gå till leverantörsreskontra > Leverantörer > Leverantörer.
11. Välj leverantören på inköpsordern. Välj till exempel leverantör 1001.
12. Klicka på länken på den valda raden i listan.
13. Klicka på Leverantör i åtgärdsfönstret.
14. Klicka på Transaktioner.
15. Välj den faktura som du själv har skapat.
    * Ankomstregistreringaccrualen återfördes och bokförts i lämplig utgiftskonto.  


