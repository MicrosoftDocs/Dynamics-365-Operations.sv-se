--- 
title: "Registrera inleverans av varor på en inköpsorder"
description: "Den här proceduren visar dig hur du registrerar inleverans av varor direkt i en inköpsorder."
author: FrankDahl
manager: AnnBe
ms.date: 08/23/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.author: fdahl
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 9b2300a593c9e153ee598fa72e29907c82f2b79e
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---
# <a name="record-the-receipt-of-goods-on-the-purchase-order"></a>Registrera inleverans av varor på en inköpsorder

[!include [task guide banner](../../includes/task-guide-banner.md)]

Den här proceduren visar dig hur du registrerar inleverans av varor direkt i en inköpsorder. Det går också att registrera produktinleveransen på lagret och bokföra den senare på inköpsordern. Denna uppgift görs vanligtvis av en inköpsagent eller en leverantörsreskontrakoordinator. De exempel som visas i den här handboken kan användas i demoföretaget USMF. Exemplet omfattar steg för att skapa en enda inköpsorder, så att du kan spela upp proceduren som en uppgiftsguide. Om du använder proceduren på dina egna data ska du börja med underuppgiften Registrera inleverans av varor.


## <a name="prepare-a-new-purchase-order-for-receipt-of-goods"></a>Förbered en ny inköpsorder för inleverans av varor.
1. Gå till Anskaffning och källa > Inköpsorder > Alla inköpsorder.
2. Klicka på Ny.
3. Ange "US-101" i fältet Leverantörskonto.
4. Klicka på OK.
5. Ange ett artikelnummer i fältet M0001.
6. Ange 5 i fältet Kvantitet.
7. Klicka på Inköp i åtgärdsfönstret.
8. Klicka på Bekräfta.

## <a name="record-receipt-of-goods"></a>Registrera inleverans av varor
1. Klicka på Ta emot i åtgärdsfönstret.
2. Klicka på Produktinleverans.
    * Fältet Kvantitet låter dig välja olika alternativ för den kvantitet som du vill ta emot. Till exempel om en kvantitet tidigare har registrerats i lagerstället, kan du välja registrerad kvantitet.  Använd värdet Beställd kvantitet för det här exemplet.   
3. I fältet Produktinleverans anger du ett värde.
    * Det här fältet används för att ange en referens som ska användas som verifikation för produktinleveransjournalen.  
4. Expandera avsnittet Rader.
5. Ställ in kvantiteten på 4.
    * Här kan du manuellt ange den kvantitet som har inlevererats för varje rad i ordern.  
6. Komprimera avsnittet Rader.
7. Klicka på OK.
    * Varorna har nu registrerats som inlevererade på inköpsordern och en produktinleveransjournal har skapats som dokumentet för att återspegla detta. Du kan använda åtgärden Produktinleverans om du vill granska journalerna som skapats med inköpsordern och se vad som har levererats och när.  


