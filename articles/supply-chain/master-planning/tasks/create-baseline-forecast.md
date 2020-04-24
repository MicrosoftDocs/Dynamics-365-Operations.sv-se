---
title: Skapa en baslinjeprognos
description: En produktionsplanerare kan skapa en baslinjeprognos, antingen genom att använda tidsserieprognosmodeller eller genom att kopiera den historiska efterfrågan.
author: ShylaThompson
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqIntercompanyPlanningGroupSetup, ReqIntercompanyPlanningGroupAllocKeys, ReqDemPlanForecastParameters, ReqDemPlanCreateForecastDialog, SysQueryForm, ReqDemPlanForecastViewer
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 3ea5e269f9216fa1dfcaa4377beb7ef52ef153b5
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/02/2020
ms.locfileid: "3209730"
---
# <a name="create-a-baseline-forecast"></a>Skapa en baslinjeprognos

[!include [banner](../../includes/banner.md)]

En produktionsplanerare kan skapa en baslinjeprognos, antingen genom att använda tidsserieprognosmodeller eller genom att kopiera den historiska efterfrågan. Denna procedur visas hur du kopierar en historisk efterfrågan med syfte att skapa en baslinjeprognos för alla produkter med hjälp av en artikelallokeringsnyckel. 


## <a name="set-up-an-item-allocation-key"></a>Ställ in en nyckel för artikelallokering
1. Gå till Huvudplanering > Inställningar > Koncerninterna planeringsgrupper.
2. Använd snabbfiltret för att söka efter poster. Filtrera till exempel på värdet "10" i fältet Namn.
    * Efterfrågeprognosticering körs över juridiska personer. Det är därför du måste ställa in alla företag som du vill generera prognoser för i en koncernintern planeringsgrupp.  
3. Hitta och markera önskad post i listan.
4. Klicka på Artikelallokeringsnycklar.
    * Markera alla artikelallokeringsnycklar som du vill skapa prognoser för.  
5. Markera vald rad i listan.
    * Markera artikelallokeringsnyckeln D_Aloc.  
6. Klicka på >.
7. Stäng sidan.
8. Stäng sidan.

## <a name="set-up-the-demand-forecasting-paramters"></a>Ställ in parametrar för efterfrågeprognosticering
1. Gå till Huvudplanering > Inställningar > Efterfrågeprognosticering > Parametrar för efterfrågeprognosticering.
2. Expandera avsnittet Forecast algorithm parameters.
3. Välj "Kopiera över historisk efterfrågan" i fältet Strategi för prognosgenerering.
4. Klicka på Spara.

## <a name="create-a-baseline-forecast"></a>Skapa en baslinjeprognos
1. Gå till Huvudplanering > Prognosticering > Efterfrågeprognosticering > Generera statistisk baslinjeprognos.
2. Ange ett datum i fältet Från datum.
    * Ange detta datum om du har försäljningsorder som startar från 1 januari 2015. Om du inte har det anger du det tidigaste datumet för dina försäljningsorder.  
3. Ange ett datum i fältet Till datum.
    * Ange det sista datumet för dina försäljningsorder, t.ex. "2015-03-31".  
4. Ange ett datum i fältet Från datum.
    * Ange "2015-04-01". Det här datumet beräknas automatiskt som startdatumet för nästa prognosgrupp.  
5. Expandera avsnittet Poster som ska ingå.
6. Klicka på Filter.
7. Markera vald rad i listan.
    * Markera raden där Fält = Koncernintern planeringsgrupp.  
8. Ange ett värde i fältet Kriterier.
    * Skriv den koncerninterna planeringsgruppen, till exempel 10, som du använde i den första uppgiften.  
9. Hitta och markera önskad post i listan.
    * Markera raden där Fält = Artikelallokeringsnyckel.  
10. Ange ett värde i fältet Kriterier.
11. Klicka på OK.
12. Expandera avsnittet Avancerade parametrar.
13. Välj "Månad" i fältet Prognosgrupp.
14. Ange "3" i fältet Prognoshorisont.
15. Ange "1" i fältet Frystidsgräns.
16. Klicka på OK.

## <a name="visualize-the-demand-forecast"></a>Visualisera efterfrågeprognosen
1. Gå till Huvudplanering > Prognosticering > Efterfrågeprognosticering > Parametrar för efterfrågeprognosticering.
2. Välj cellen i rad 1, kolumn 2 i tabellen AggregatedViewTable. Detta är den andra månaden som du har skapat prognos för.
3. Ange QtyCell till "400".
    * I cellen anger du ett annat nummer än det som har prognosticerats, till exempel 400.  
4. Du har gjort en manuell justering av prognosen. Observera den grafiska indikeringen i nästa steg.
5. Klicka på Raddetaljer för prognos.
    * På den här sidan kan du se precisionsvärdena, den historiska efterfrågan och prognosen. Du kan fortfarande göra ändringar även i prognosen.  

