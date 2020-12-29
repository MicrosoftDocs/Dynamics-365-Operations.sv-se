---
title: Skapa en inköpsorder med en leveransplan
description: Det här avsnittet visar hur du kan skapa en leveransplan för en inköpsorder.
author: mkirknel
manager: tfehr
ms.date: 08/01/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchTable, PurchTablePart, PurchCreateOrder, InventItemIdLookupPurchase, PurchDeliverySchedule, PurchEditLines
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 9c4e8dca93fdf9ee605ffeb63f259389b58a4b36
ms.sourcegitcommit: 827d77c638555396b32d36af5d22d1b61dafb0e8
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/16/2020
ms.locfileid: "4438065"
---
# <a name="create-a-purchase-order-with-a-delivery-schedule"></a>Skapa en inköpsorder med en leveransplan

[!include [banner](../../includes/banner.md)]

Det här avsnittet visar hur du kan skapa en leveransplan för en inköpsorder. En leveransplan används när en kvantitet på en order eller en journal begärs för att levereras i flera försändelser. De exempel som visas i den här handboken kan användas i demoföretaget USMF. Denna procedur görs normalt av en inköpsagent.

## <a name="create-a-delivery-schedule"></a>Skapa en leveransplan
1. I navigeringsfönstret, gå till **Moduler > Anskaffning och källa > Inköpsorder > Alla inköpsorder**.
2. Klicka på **Ny** i åtgärdsfönstret.
3. I fältet **Leverantörskonto** ange `US-101`.
4. Välj **OK**.
5. I fältet **artikelnummer** anger du `M0001`.
6. I fältet **Kvantitet** anger du `10`.
7. Välj **inköpsorderrad**.
8. Välj **leveransplan**.
- Sidan **Leveransplan** låter dig ange antalet leveranser för den totala kvantiteten på orderraden som ska levereras från leverantören.  
- Som standard kopierar systemet den totala kvantiteten och andra leveransdetaljer för de ursprungliga inköpsraderna till den första leveransplanraden. I det här exemplet ska du skapa ett schema för två leveranser, med det andra leveransdatumet med förskjutning på en vecka efter den första leveransen.  
9. Ändra kvantiteten till `4` i fältet **Kvantitet**.
10. Välj **Ny**.
11. Ange `6` som den återstående kvantiteten i fältet **Kvantitet**.
- Välj ett datum som infaller en vecka efter datumet på den första leveransraden i fältet Leveransdatum.  
- Du kan spåra den totala kvantiteten som tilldelas till leveransplanraderna genom att visa **summan** och **återstående** fält. När den resterande kvantiteten är noll, har den fullständiga kvantiteten från den ursprungliga raden allokerats till tidsplaneringen.  
12. Expandera avsnittet **Konvertering av avgifter**.
- Alternativen här låter dig kontrollera hur du vill att avgifter ska fördelas mellan leveransplanraderna. Om du väljer **Kopiera bruttobelopp**, kopieras avgiftsbeloppet på den ursprungliga orderraden till varje leverandsrad. Alternativet **Fördela på leveransrader** delar upp den ursprungliga radavgiften enligt kvantiteten på varje leveransrad.  
13. Komprimera avsnittet **Konvertering av avgifter**.
14. Välj **OK**.
- Leveransplanen har nu tillämpats på orderraderna.  
- Den ursprungliga orderraden som nu kallas för en kommersiell rad, har konverterats till en orderrad med flera leveranser. Den markeras med en särskild ikon och fungerar som rubrik för leveransraderna.  
15. Välj den andra orderraden, som är den första av de två leveransraderna.
- De två nya raderna som kallas för leveransrader utgör en leveransplan. Ordern ska bearbetas mot dessa rader och inte den ursprungliga raden. Om dokument som bekräftelser, produktinleveransjournaler eller fakturor skrivs ut, visas bara leveransraderna.  

## <a name="change-the-delivery-schedule"></a>Ändra leveransplanen
Du kan ändra leveranskvantitet på leveransraderna. Om du gör detta, uppdateras den kommersiella raden automatiskt till den totala kvantiteten för leveransraden.  
1. Ändra kvantiteten från `4` till `5` i fältet **Kvantitet** för den första leveransraden.
2. Välj den första orderraden (den kommersiella raden).  
- Kvantiteten på den kommersiella raden har ändrats till 11.  

## <a name="process-product-receipt-using-delivery-schedules"></a>Bearbeta produktinleveransen med hjälp av leveransplaner
Inköpsordern måste bekräftas före produktinleveransen kan bearbetas. I detta exempel registreras inleveransen direkt på inköpsordern. Inleveransen kan också ha registrerats, när varorna ankom till lagerstället.  
1. I åtgärdsfönstret, välj **Inköp**.
2. Välj **Bekräfta**.
3. Välj **Ta emot** i åtgärdsfönstret.
4. Välj **produktinleverans** I fältet **Produktinleverans** anger du ett värde.
- Det här fältet används för att ange en referens som ska användas som verifikation för produktinleveransjournalen.  
- I fältet **Kvantitet**, välj **Beställd kvantitet**. Det här alternativet innebär att inleverans kommer att bearbetas för den kvantitet som orderradena skapades med.  
- Kontrollera att fältet **Skriv ut produktinleverans** inte anges till **Nej**. Utskrift är inte nödvändigt i det här exemplet.  
5. Expandera avsnittet **Rader**.
- Observera hur produktinleveransen skapas för de två leveransraderna och inte den ursprungliga orderraden. Om inleveransen har registrerats i lagerstället, har den också registrerats på leveransplanraderna.  
6. Komprimera avsnittet **Rader**.
7. Välj **OK** när du vill bokföra inleveransen.

