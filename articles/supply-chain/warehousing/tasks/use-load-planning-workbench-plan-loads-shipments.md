---
title: Planera laster och utleveranser med workbench för lastplanering
description: I det här avsnittet visas hur du använder workbench för lastplanering om för att skapa en beläggning för en försäljningsorder.
author: ShylaThompson
ms.date: 07/08/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: WHSHistory, WHSLoadTable, WHSLoadPlanningListPage, WHSLoadPlanningWorkbench
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f5c343ac75d3f2d587dc3298adc2ba9f4b3d08a7ce87a0dd8dd0791cf4d4e050
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6723417"
---
# <a name="plan-loads-and-shipments-using-the-load-planning-workbench"></a>Planera laster och utleveranser med workbench för lastplanering

[!include [banner](../../includes/banner.md)]

I det här avsnittet visas hur du använder workbench för lastplanering om för att skapa en beläggning för en försäljningsorder. Som en förutsättning skapar vi försäljningsordern först. Den här proceduren utgör en del av det dagliga arbetet för transportkoordinatorn. Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF.


## <a name="create-a-sales-order"></a>Skapa en försäljningsorder
1. Gå till **Navigeringsfönstret > Moduler > Kundreskontra > Order > Alla försäljningsorder**.
2. Välj **Ny**.
3. På fältet **Kundkonto** klicka på knappen för att öppna sökning.
4. Välj kontot **US-004**.
5. Välj **OK**.
6. På fält **Artikelnummer** klicka på nedrullningsbara knappen för att öppna sökningen.
7. Välj artikel **A0001**. **A0001** har aktiverats för transporthantering.  
8. I fältet **Plats** klicka på nedrullningsbara knappen för att öppna sökningen och välj sedan en artikel.
9. Ange ett nummer i fältet **Kvantitet**.
10. I fältet **Lagerställe** skriver du "24" för det här exemplet. Lagerstället aktiveras för transportledning och avancerad lagerstyrning.  
11. Välj **Spara**.
12. Stäng sidan.

## <a name="create-a-new-load"></a>Skapa en ny beläggning.
1. Gå till **Navigeringsfönstret > Moduler > Transporthantering > Planering > Workbench för lastplanering**.
2. Välj fliken **Försäljningsrader**. Nu skapar du beläggningen för den försäljningsorder som du precis skapade. Beläggningar kan skapas med utgångspunkt i tillgång och efterfrågan från inköpsorder, överföringsorder och försäljningsorder.  
3. I åtgärdsfönstret väljer du **Tillgång och efterfrågan**.
4. Välj **Till ny last**.
5. I fältet **Lastmall-ID** väljer du den nedrullningsbara knappen för att öppna sökningen. Beläggningsmallen definierar maximala mått för vikt och volym för hela beläggningen. Beläggningsmallen kan till exempel representera storleken på en behållare eller en lastbil. Markera en artikel.
6. Välj **OK**.

## <a name="rate-and-route-the-load"></a>Tariff och rutt för beläggningen
1. Välj **värdering och flöde**.
2. Välj **workbench för tariff/rutt**.
3. Välj **Tariffbutik**.
4. Hitta och markera önskad post i listan.
5. Välj **Tilldela**.
6. Stäng sidan.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]