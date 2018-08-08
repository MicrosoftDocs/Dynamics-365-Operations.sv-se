--- 
title: "Skapa en materialplan för samprodukter"
description: "Produktionsplaneraren planerar materialbehoven för de artiklar som är samprodukter för formeln."
author: ShylaThompson
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: c8805ca02525ae001fbd5e10ad9405fe60c7473e
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---
# <a name="create-a-material-plan-for-co-products"></a>Skapa en materialplan för samprodukter

[!include [task guide banner](../../includes/task-guide-banner.md)]

Produktionsplaneraren planerar materialbehoven för de artiklar som är samprodukter för formeln. Det demonstrationsdataföretag som används för att skapa den här proceduren är USP2.


## <a name="create-requirement-for-a-co-product"></a>Skapa behov för en samprodukt
1. Gå till standardinstrumentpanelen.
2. Klicka på Bearbetning och förfrågan om försäljningsorder.
3. Klicka på Ny.
4. Klicka på Försäljningsorder.
5. Ange ett värde i fältet Kundkonto.
    * Exempel: US-001  
6. Klicka på OK.
7. Skriv ett värde i fältet Artikelnummer.
    * Exempel: P6003  
8. Ange ett tal i fältet Kvantitet.
    * Exempel: 50 000  
9. Klicka på Spara.

## <a name="create-a-material-plan-for-co-products"></a>Skapa en materialplan för samprodukter
1. Klcka på Huvudplanering.
2. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Plan.
3. Klicka på länken på den valda raden i listan.
    * Exempel: MasterPlan  
4. Klicka på Kör.
5. Utöka eller komprimera avsnittet Poster som ska ingå.
6. Klicka på Filter.
7. Välj raden för fält = artikelnummer i listan.
8. Ange ett värde i fältet Kriterier.
    * Exempel: P6003  
9. Klicka på OK.
10. Klicka på OK.
11. Klicka på Planerade order.
12. Använd snabbfiltret för att söka efter poster. Filtrera till exempel i fältet Artikelnummer med värdet "P6000".
    * Filtrera efter den receptartikel som har en samprodukt för den artikel som du har skapat en försäljningsorder för.  
13. Markera vald rad i listan.
    * Välj någon av de rader som returneras av filtret.  
14. Klicka på länken på den valda raden i listan.
15. Expandera eller komprimera avsnittet Pegging.
16. Klicka på länken på den valda raden i listan.
    * Den planerade ordern peggas till försäljningsordern för samprodukten.  
17. Stäng sidan.


