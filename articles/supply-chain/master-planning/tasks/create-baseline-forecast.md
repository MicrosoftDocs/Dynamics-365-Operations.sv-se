---
title: 'Guide: Skapa en baslinjeprognos'
description: En produktionsplanerare kan skapa en baslinjeprognos, antingen genom att använda tidsserieprognosmodeller eller genom att kopiera den historiska efterfrågan.
author: ShylaThompson
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ReqIntercompanyPlanningGroupSetup, ReqIntercompanyPlanningGroupAllocKeys, ReqDemPlanForecastParameters, ReqDemPlanCreateForecastDialog, SysQueryForm, ReqDemPlanForecastViewer
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 34a82dac3ea8cf87eeb184dee05ce27c83707e3082469e955e9ffbaf6da5c638
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6733478"
---
# <a name="guide-create-a-baseline-forecast"></a>Guide: Skapa en baslinjeprognos

[!include [banner](../../includes/banner.md)]

En produktionsplanerare kan skapa en baslinjeprognos, antingen genom att använda tidsserieprognosmodeller eller genom att kopiera den historiska efterfrågan. Denna procedur visas hur du kopierar en historisk efterfrågan med syfte att skapa en baslinjeprognos för alla produkter med hjälp av en artikelallokeringsnyckel.

## <a name="set-up-an-item-allocation-key"></a>Ställ in en nyckel för artikelallokering

1. Gå till **Huvudplanering > Inställningar > Koncerninterna planeringsgrupper**.
2. Använd snabbfiltret för att söka efter poster. Filtrera till exempel på fältet *Namn* med värdet *10*.
    * Efterfrågeprognosticering körs över juridiska personer. Det är därför du måste ställa in alla företag som du vill generera prognoser för i en koncernintern planeringsgrupp.  
3. Hitta och markera önskad post i listan.
4. Välj **Artikelallokeringsnyckel**.
    * Markera alla artikelallokeringsnycklar som du vill skapa prognoser för.  
5. Markera vald rad i listan.
    * Markera artikelallokeringsnyckeln D_Aloc.  
6. Markera **>**.
7. Stäng sidan.
8. Stäng sidan.

## <a name="set-up-the-demand-forecasting-parameters"></a>Ställ in parametrar för efterfrågeprognosticering

1. Gå till **Huvudplanering > Inställningar > Efterfrågeprognosticering > Parametrar för efterfrågeprognosticering**.
2. Expandera avsnittet **Prognosticera algoritmparametrar**.
3. I fältet **Prognosticera generationsstrategi** väljer du **Kopiera över historiskt krav**.
4. Välj **Spara**.

## <a name="create-a-baseline-forecast"></a>Skapa en baslinjeprognos

1. Gå till **Huvudplanering > Prognosticering > Efterfrågeprognosticering > Generera statistisk baslinjeprognos**.
2. I fältet **Från datum** anger du ett datum.
    * Ange detta datum om du har försäljningsorder som startar från 1 januari 2015. Om du inte har det anger du det tidigaste datumet för dina försäljningsorder.  
3. I fältet **Till-datum**, anger du ett datum.
    * Ange det sista datumet för dina försäljningsorder, t.ex. *2015-03-31*.  
4. I fältet **Från datum** anger du ett datum.
    * Ange *2015-04-01*. Det här datumet beräknas automatiskt som startdatumet för nästa prognosgrupp.  
5. Expandera avsnittet **Poster som ska ingå**.
6. Välj **filter**.
7. Markera vald rad i listan.
    * Markera raden där **Fält** = *Koncernintern planeringsgrupp*.  
8. I fältet **Kriterier** skriver du ett värde.
    * Skriv den koncerninterna planeringsgruppen, till exempel *10*, som du använde i den första uppgiften.  
9. Hitta och markera önskad post i listan.
    * Markera raden där **Fält** = *Artikelallokeringsnyckel*.  
10. I fältet **Kriterier** skriver du ett värde.
11. Välj **OK**.
12. Expandera avsnittet **Avancerade parametrar**.
13. I fältet **Prognosgrupp** väljer du *Månad*.
14. I fältet **Prognoshorisont** anger du *3*.
15. I fältet **Frystidsgräns** anger du *1*.
16. Välj **OK**.

## <a name="visualize-the-demand-forecast"></a>Visualisera efterfrågeprognosen

1. Gå till **Huvudplanering > Prognosticering > Efterfrågeprognosticering > Justerad efterfrågeprognosticering**.
2. Välj cellen i rad 1, kolumn 2 i tabellen AggregatedViewTable. Detta är den andra månaden som du har skapat prognos för.
3. Ange **QtyCell** som *400*.
    * I cellen anger du ett annat nummer än det som har prognosticerats, till exempel 400.  
4. Du har gjort en manuell justering av prognosen. Observera den grafiska indikeringen i nästa steg.
5. Markera **Raddetaljer för prognos**.
    * På den här sidan kan du se precisionsvärdena, den historiska efterfrågan och prognosen. Du kan fortfarande göra ändringar även i prognosen.  

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]