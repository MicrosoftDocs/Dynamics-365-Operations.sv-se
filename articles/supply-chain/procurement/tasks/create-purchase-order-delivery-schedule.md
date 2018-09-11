--- 
title: "Skapa en inköpsorder med en leveransplan"
description: "Den här proceduren visas hur du kan skapa en leveransplan för en inköpsorder."
author: FrankDahl
manager: AnnBe
ms.date: 8/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: PurchTable, PurchCreateOrder, InventItemIdLookupPurchase, PurchDeliverySchedule, PurchEditLines
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: fdahl
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 1e4a0204d74c8966cd90b52ae13c88e222ebc3ef
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---
# <a name="create-a-purchase-order-with-a-delivery-schedule"></a>Skapa en inköpsorder med en leveransplan

[!include [task guide banner](../../includes/task-guide-banner.md)]

Den här proceduren visas hur du kan skapa en leveransplan för en inköpsorder. En leveransplan används när en kvantitet på en order eller en journal begärs för att levereras i flera försändelser. De exempel som visas i den här handboken kan användas i demoföretaget USMF. Denna procedur görs normalt av en inköpsagent.


## <a name="create-a-delivery-schedule"></a>Skapa en leveransplan
1. Gå till Anskaffning och källa > Inköpsorder > Alla inköpsorder.
2. Klicka på Ny.
3. Ange "US-101" i fältet Leverantörskonto.
4. Klicka på OK.
5. Ange ett artikelnummer i fältet M0001.
6. Ange 10 i fältet Kvantitet.
7. Klicka på Inköpsorderrad.
8. Klicka på Leveransplan.
    * Sidan Leveransplan låter dig ange antalet leveranser för den totala kvantiteten på orderraden som ska levereras från leverantören.  
    * Som standard kopierar systemet den totala kvantiteten och andra leveransdetaljer för de ursprungliga inköpsraderna till den första leveransplanraden. I det här exemplet ska du skapa ett schema för två leveranser, med det andra leveransdatumet med förskjutning på en vecka efter den första leveransen.  
9. Ändra kvantiteten till 4 i fältet Kvantitet.
10. Klicka på Ny.
11. Ange 6 som den återstående kvantiteten i fältet Kvantitet.
    * Välj ett datum som infaller en vecka efter datumet på den första leveransraden i fältet Leveransdatum.  
    * Du kan spåra den totala kvantiteten som tilldelas till leveransplanraderna genom att visa summan och återstående fält. När den resterande kvantiteten är noll, har den fullständiga kvantiteten från den ursprungliga raden allokerats till tidsplaneringen.  
12. Expandera avsnittet Konvertering av avgifter.
    * Alternativen här låter dig kontrollera hur du vill att avgifter ska fördelas mellan leveransplanraderna. Om du väljer Kopiera bruttobelopp, kopieras avgiftsbeloppet på den ursprungliga orderraden till varje leverandsrad. Alternativet Fördela på leveransrader delar upp den ursprungliga radavgiften enligt kvantiteten på varje leveransrad.  
13. Komprimera avsnittet Konvertering av avgifter.
14. Klicka på OK.
    * Leveransplanen har nu tillämpats på orderraderna.  
    * Den ursprungliga orderraden som nu kallas för en kommersiell rad, har konverterats till en orderrad med flera leveranser. Den markeras med en särskild ikon och fungerar som rubrik för leveransraderna.  
15. Välj den andra orderraden, som är den första av de två leveransraderna.
    * De två nya raderna som kallas för leveransrader utgör en leveransplan. Ordern ska bearbetas mot dessa rader och inte den ursprungliga raden. Om dokument som bekräftelser, produktinleveransjournaler eller fakturor skrivs ut, visas bara leveransraderna.  

## <a name="change-the-delivery-schedule"></a>Ändra leveransplanen
    * Du kan ändra leveranskvantitet på leveransraderna. Om du gör detta, uppdateras den kommersiella raden automatiskt till den totala kvantiteten för leveransraden.  
1. Ändra kvantiteten från 4 till 5 i fältet Kvantitet för den första leveransraden.
2. Välj den första orderraden (den kommersiella raden).
    * Kvantiteten på den kommersiella raden har ändrats till 11.  

## <a name="process-product-receipt-using-delivery-schedules"></a>Bearbeta produktinleveransen med hjälp av leveransplaner
    * Inköpsordern måste bekräftas före produktinleveransen kan bearbetas. I detta exempel registreras inleveransen direkt på inköpsordern. Inleveransen kan också ha registrerats, när varorna ankom till lagerstället.  
1. Klicka på Inköp i åtgärdsfönstret.
2. Klicka på Bekräfta.
3. Klicka på Ta emot i åtgärdsfönstret.
4. Klicka på Produktinleverans.
5. I fältet Produktinleverans anger du ett värde.
    * Det här fältet används för att ange en referens som ska användas som verifikation för produktinleveransjournalen.  
    * Välj "Beställd kvantitet" i fältet Kvantitet. Det här alternativet innebär att inleverans kommer att bearbetas för den kvantitet som orderradena skapades med.  
    * Kontrollera att fältet Skriv ut produktinleverans inte anges till Nej. Utskrift är inte nödvändigt i det här exemplet.  
6. Expandera avsnittet Rader.
    * Observera hur produktinleveransen skapas för de två leveransraderna och inte den ursprungliga orderraden. Om inleveransen har registrerats i lagerstället, har den också registrerats på leveransplanraderna.  
7. Komprimera avsnittet Rader.
8. Klicka på OK när du vill bokföra inleveransen.


