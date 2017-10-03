---
title: "Behovsprognoser inställning"
description: "Detta avsnitt beskriver de uppgifter som du måste utföra för att förbereda behovsprognoser."
author: roxanadiaconu
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ReqDemPlanDefaultAlgorithmParameters, ReqDemPlanForecastParameters
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 72653
ms.assetid: c5fa4b09-512d-4349-ac51-cc13da69a160
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 869151f2486b7a481e4694cfb6992d0ee2cfc008
ms.openlocfilehash: 74d520199410711b80b750a12ee726633e09d01c
ms.contentlocale: sv-se
ms.lasthandoff: 06/13/2017

---

# <a name="demand-forecasting-setup"></a>Behovsprognoser inställning

[!include[banner](../includes/banner.md)]


Detta avsnitt beskriver de uppgifter som du måste utföra för att förbereda behovsprognoser.  

Förval uppgifter ingår att inrätta följande data och parametrar.

## <a name="item-allocation-key"></a>Artikelallokeringsnyckel
En efterfrågan prognosen beräknas för ett objekt och dess dimensioner endast om objektet är en del av en fördelningsnyckel. Denna regel tillämpas för att gruppera ett stort antal artiklar i syfte att kunna efterfrågeprognoser kan skapas snabbare. Procentandelen för artikelallokeringsnyckel ignoreras när efterfrågeprognoser genereras. Prognoser är skapade baserad på historiska data bara. 

Ett objekt och dess dimensioner måste vara en del av endast en punkt fördelningsnyckel om posten fördelningsnyckel används under prognos. 

För att lägga till en lagerhållningsenhet (SKU) i en artikelallokeringsnyckel, gå till **Huvudplanering** &gt; **Inställningar** &gt; **Efterfrågeprognosticering** &gt; **Artikelallokeringsnycklar**. Använd **Tilldela artiklar** sidan till att tilldela ett objekt till en fördelningsnyckel.

## <a name="intercompany-planning-groups"></a>Koncerninterna planeringsgrupper
Behovsprognoser genererar gränsöverskridande företag prognoser. Företag som planeras tillsammans grupperas i en enda koncernintern planeringsgrupp i Microsoft Dynamics 365 for Finance and Operations. För att ange (efter företag) vilka artikelallokeringsnycklar som ska beaktas för efterfrågeprognosticering, associera en artikelallokeringsnyckel med den koncerninterna planeringsgruppmedlemmen genom att gå till **Huvudplanering** &gt; **Inställningar** &gt; **Koncerninterna planeringsgrupper**. 

Om inga artikelallokeringsnycklar tilldelas företagsinterna planeringsgruppmedlemmar, kommer en efterfrågeprognos som standard att beräknas för alla artiklar som tilldelats till samtliga artikelallokeringsnycklar från alla Finance and Operations-företag. Extra filtering alternativ för företag och fördelningsnycklar finns på **generera statistiska basprognosen** sida. 

Kontrollera antalet objekt som prognostiseras. Onödiga objekt kan orsaka ökade kostnader när du använder Microsoft Azure maskinen lärande.

## <a name="demand-forecasting-parameters"></a>Parametrar för efterfrågeprognosticering
Gå till **Huvudplanering** &gt; **Inställningar** &gt; **Parametrar för efterfrågeprognosticering** för att skapa parametrar för efterfrågeprognosticering. Eftersom efterfrågan prognostisera körs cross-firma, installationen är global. Med andra ord, gäller för alla företag. 

Behovsprognoser genereras prognosen i mängder. Därför är den enhet som kvantiteten bör uttryckas i måste specificeras i **efterfrågan** . Enheten måste vara unikt, för att garantera att aggregering och procentuell fördelning. För mer information om summering och procentuell fördelning, se [göra manuella justeringar av den ursprungliga prognosen](manual-adjustments-baseline-forecast.md). För varje enhet som används för artiklar som ingår i behovsprognoser, se till att det finns en konverteringsregel för enheten och den allmänna prognoser enhet. När prognosen generation, en lista över poster som inte har en enhet omräkning finnas loggat, så att du lätt kan korrigera inställningen. 

Behovsprognoser kan användas för att förutse både beroende och oberoende behov. Om till exempel endast **försäljningen för** kryssrutan är markerad och om alla punkter som anses för behovsprognoser är artiklar som säljs, beräknar systemet oberoende efterfrågan. Men kritiska delkomponenterna kan läggas till punkt fördelningsnycklar och ingår i behovsprognoser. I det här fallet, om **Produktionslinje** kryssrutan är markerad, beräknas en beroendeprognos. 

Det finns två metoder för att skapa en baslinjeprognos i Finance and Operations. Du kan använda modeller för prognoser på toppen av historiska data, eller kan du bara kopiera över historiska data till prognosen. **Prognosen generation strategi** fältet kan du välja mellan dessa två metoder. För att använda prognosmodeller, välj **Azure Machine Learning**. 

Genom att klicka på **prognosdimensioner** i den vänstra rutan i **behovsprognosparametrar** sidan kan du även välja prognos dimensioner som ska användas när behovsprognosen genereras. En prognos dimensionen anger nivån av detaljen att prognosen är definierad för. Företag, ort och objekt fördelningsnyckel är obligatoriska prognos dimensioner, men du kan också generera prognoser på lager, lager status, kundgrupp, land/region, stat och objekt samt alla objekt dimension nivåer. 

Du kan när som helst lägga prognosen dimensioner till listan av dimensioner som används för behovsprognoser. Du kan också ta bort prognos mått från listan. Men manuella justeringar går förlorade om du lägger till eller tar bort en prognos dimension. 

Inte alla objekt beter sig på samma sätt från en behovsprognoser perspektiv. Liknande poster kan grupperas i en fördelningsnyckel och parametrar såsom transaktionstyper och prognosmetod inställningar kan anges per post fördelningsnyckel. Klicka på **alternativet fördelningsnycklar** i den vänstra rutan i **behovsprognoser parametrar sidan**. 

Finance and Operations använder en webbtjänst för maskininlärning för att generera prognosen. För att ansluta till tjänsten måste du tillhandahålla Finance and Operations följande information när du loggar in på Microsoft Azure Machine Learning Studio:

-   Web Service API (application programming interface)
-   Webbtjänstens slutpunktsadress
-   Azure Storage kontonamn
-   Azure Storage kontonyckel

**Obs!** Azure-lagringskontonamn och nyckeln behövs bara om du använder ett anpassat lagringskonto. Om du använder den lokala versionen måste du ha ett anpassat lagringskonto på Azure, detta så att maskininlärningstjänsten kan få åtkomst till historiska data. 

För att skapa efterfrågeförutsägelser kan du använda din egen service genom att använda Machine Learning Studio eller Finance and Operations behovsprognoser för efterfrågeprognoser. Instruktioner för att implementera Finance and Operations experiment för efterfrågeprognosticering som en webbtjänst finns i Finance and Operations På **behovsprognosparametrar** sidan, klicka på **Azure Machine Learning** fliken.

## <a name="settings-for-the-finance-and-operations-demand-forecasting-machine-learning-service"></a>Inställningar för Finance and Operations maskininlärningstjänst för efterfrågeprognosticering
Gå till **Huvudplanering** &gt; **Inställningar** &gt; **Efterfrågeprognosticering** &gt; **Algoritmparametrar för prognos** om du vill visa de parametrar som kan konfigureras för Finance and Operations tjänst för efterfrågeprognosticering. Sidan **Algoritmparametrar för prognoser** visas standardvärden för parametrar. Du kan skriva över dessa parametrar på sidan **Parametrar för efterfrågeprognosticering**. På **fliken Allmänt om du** vill skriva över parametrar globalt, eller använda **posten fördelningsnycklar för** att skriva över parametrar per punkt fördelningsnyckel. Parametrar som är över för en fördelningsnyckel som endast påverkar prognosen för de objekt som associeras med objektet fördelningsnyckel.

<a name="see-also"></a>Se även
--------

[Introduktion till efterfrågeprognosticering](introduction-demand-forecasting.md)

[Generera en statistisk baslinjeprognos](generate-statistical-baseline-forecast.md)

[Gör manuella justeringar till den ursprungliga prognosen](manual-adjustments-baseline-forecast.md)




