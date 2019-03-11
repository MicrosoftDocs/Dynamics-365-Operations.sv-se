---
title: Skapa en materialplan för samprodukter
description: Produktionsplaneraren planerar materialbehoven för de artiklar som är samprodukter för formeln.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, SalesOrderProcessingWorkspace, SalesCreateOrder, SalesTable, ReqCreatePlanWorkspace, ReqTransPlanCard, SysQueryForm, ReqTransPo
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 2958f1e5c2e8a0cfa9cc6312f688d3b11b8e013c
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2019
ms.locfileid: "337151"
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
1. Stäng sidan.
2. Stäng sidan.
3. Klcka på Huvudplanering.
4. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Plan.
5. Klicka på länken på den valda raden i listan.
    * Exempel: MasterPlan  
6. Klicka på Kör.
7. Utöka eller komprimera avsnittet Poster som ska ingå.
8. Klicka på Filter.
9. Välj raden för fält = artikelnummer i listan.
10. Ange ett värde i fältet Kriterier.
    * Exempel: P6003  
11. Klicka på OK.
12. Klicka på OK.
13. Klicka på Planerade order.
14. Använd snabbfiltret för att söka efter poster. Filtrera till exempel i fältet Artikelnummer med värdet "P6000".
    * Filtrera efter den receptartikel som har en samprodukt för den artikel som du har skapat en försäljningsorder för.  
15. Markera vald rad i listan.
    * Välj någon av de rader som returneras av filtret.  
16. Klicka på länken på den valda raden i listan.
17. Expandera eller komprimera avsnittet Pegging.
18. Klicka på länken på den valda raden i listan.
    * Den planerade ordern peggas till försäljningsordern för samprodukten.  
19. Stäng sidan.

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
1. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Plan.
2. Klicka på länken på den valda raden i listan.
    * Exempel: MasterPlan  
3. Klicka på Kör.
4. Utöka eller komprimera avsnittet Poster som ska ingå.
5. Klicka på Filter.
6. Välj raden för fält = artikelnummer i listan.
7. Ange ett värde i fältet Kriterier.
    * Exempel: P6003  
8. Klicka på OK.
9. Klicka på OK.
10. Klicka på Planerade order.
11. Använd snabbfiltret för att söka efter poster. Filtrera till exempel i fältet Artikelnummer med värdet "P6000".
    * Filtrera efter den receptartikel som har en samprodukt för den artikel som du har skapat en försäljningsorder för.  
12. Markera vald rad i listan.
    * Välj någon av de rader som returneras av filtret.  
13. Klicka på länken på den valda raden i listan.
14. Expandera eller komprimera avsnittet Pegging.
15. Klicka på länken på den valda raden i listan.
    * Den planerade ordern peggas till försäljningsordern för samprodukten.  
16. Stäng sidan.
17. Klcka på Huvudplanering.
18. Gå till Huvudplanering > Inställningar > Huvudplaneringsparametrar.
19. Välj Nej i fältet Inaktivera alla planeringsprocesser.
20. Stäng sidan.

