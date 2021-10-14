---
title: Skapa en materialplan för samprodukter
description: Produktionsplaneraren planerar materialbehoven för de artiklar som är samprodukter för formeln.
author: ChristianRytt
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, SalesOrderProcessingWorkspace, SalesCreateOrder, SalesTable, ReqCreatePlanWorkspace, ReqTransPlanCard, SysQueryForm, ReqTransPo
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: deae0d7e0295aa02f5ad512f67e9e3d2148c2e33
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/29/2021
ms.locfileid: "7578306"
---
# <a name="create-a-material-plan-for-co-products"></a>Skapa en materialplan för samprodukter

[!include [banner](../../includes/banner.md)]

Produktionsplaneraren planerar materialbehoven för de artiklar som är samprodukter för formeln. Det demonstrationsdataföretag som används för att skapa den här proceduren är USP2.

## <a name="create-requirement-for-a-co-product"></a>Skapa behov för en samprodukt

1. Gå till **Försäljning och marknadsföring \> Arbetsytor \> Försäljningsorderbearbetning och förfrågan**.
1. Välj **Ny**.
1. Välj **Försäljningsorder**.
1. I fältet **kundkonto** och ange ett värde.
    * Exempel: US-001  
1. Välj **OK**.
1. I fältet **Artikelnummer**, skriv ett värde.
    * Exempel: P6003  
1. Ange ett nummer i fältet **Kvantitet**.
    * Exempel: 50 000  
1. Välj **Spara**.

## <a name="create-a-material-plan-for-co-products"></a>Skapa en materialplan för samprodukter

1. Stäng sidan.
1. Stäng sidan.
1. Välj **Huvudplanering**.
1. Öppna sökningen genom att välja listrutan i fältet **Planera**.
1. Klicka på länken på önskad rad i valda listan.
    * Exempel: MasterPlan  
1. Välj **kör**.
1. Utöka eller komprimera avsnittet **Poster som ska ingå**.
1. Välj **filter**.
1. Välj raden för **Fält** = *Artikelnummer* i listan.
1. I fältet **Kriterier** skriver du ett värde.
    * Exempel: P6003  
1. Välj **OK**.
1. Välj **OK**.
1. Välj **Planerade order**.
1. Använd snabbfiltret för att söka efter poster. Filtrera till exempel fältet **Artikelnummer** med värdet "P6000".
    * Filtrera efter den receptartikel som har en samprodukt för den artikel som du har skapat en försäljningsorder för.  
1. Markera vald rad i listan.
    * Välj någon av de rader som returneras av filtret.  
1. Klicka på länken på önskad rad i valda listan.
1. Expandera avsnittet **Pegging**.
1. Klicka på länken på önskad rad i valda listan.
    * Den planerade ordern peggas till försäljningsordern för samprodukten.  
1. Stäng sidan.

## <a name="create-a-second-requirement-for-a-co-product"></a>Skapa ett andra behov för en samprodukt

1. Gå till **Försäljning och marknadsföring \> Arbetsytor \> Försäljningsorderbearbetning och förfrågan**.
1. Välj **Ny**.
1. Välj **Försäljningsorder**.
1. I fältet **kundkonto** och ange ett värde.
    * Exempel: US-001  
1. Välj **OK**.
1. I fältet **Artikelnummer**, skriv ett värde.
    * Exempel: P6003  
1. Ange ett nummer i fältet **Kvantitet**.
    * Exempel: 50 000  
1. Välj **Spara**.

## <a name="create-a-second-material-plan-for-co-products"></a>Skapa en andra materialplan för samprodukter

1. Öppna sökningen genom att välja listrutan i fältet **Planera**.
2. Klicka på länken på önskad rad i valda listan.
    * Exempel: MasterPlan  
3. Välj **kör**.
4. Utöka eller komprimera avsnittet **Poster som ska ingå**.
5. Välj **filter**.
6. Välj raden för **Fält** = *Artikelnummer* i listan.
7. I fältet *Kriterier* skriver du ett värde.
    * Exempel: P6003  
8. Välj **OK**.
9. Välj **OK**.
10. Välj **Planerade order**.
11. Använd snabbfiltret för att söka efter poster. Filtrera till exempel fältet **Artikelnummer** med värdet "P6000".
    * Filtrera efter den receptartikel som har en samprodukt för den artikel som du har skapat en försäljningsorder för.  
12. Markera vald rad i listan.
    * Välj någon av de rader som returneras av filtret.  
13. Klicka på länken på önskad rad i valda listan.
14. Expandera eller komprimera avsnittet **Pegging**.
15. Klicka på länken på önskad rad i valda listan.
    * Den planerade ordern peggas till försäljningsordern för samprodukten.  
16. Stäng sidan.
17. Välj **Huvudplanering**.
18. Gå till **Huvudplanering \> Inställningar \> Huvudplaneringsparametrar**.
19. Välj *Nej* i fältet **Inaktivera samtliga planeringsprocesser**.
20. Stäng sidan.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]