---
title: "Behovsprognoser inställning"
description: "Detta avsnitt beskriver de uppgifter som du måste utföra för att förbereda behovsprognoser."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: ReqDemPlanDefaultAlgorithmParameters, ReqDemPlanForecastParameters
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 72653
ms.assetid: c5fa4b09-512d-4349-ac51-cc13da69a160
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ccbe5815ebb54e00265e130be9c82491aebabce
ms.openlocfilehash: f629329f4f50bd7c8edcfd70641bace01a1c53aa
ms.lasthandoff: 03/31/2017


---

# <a name="demand-forecasting-setup"></a>Behovsprognoser inställning

Detta avsnitt beskriver de uppgifter som du måste utföra för att förbereda behovsprognoser.  

Förval uppgifter ingår att inrätta följande data och parametrar.

## <a name="item-allocation-key"></a>Artikelallokeringsnyckel
En efterfrågan prognosen beräknas för ett objekt och dess dimensioner endast om objektet är en del av en fördelningsnyckel. Regeln gäller till gruppen har många artiklar, så att du kan skapa efterfrågeprognoser snabbare. Den viktigaste artikel allokeringsprocenten ignoreras när efterfrågeprognoser genereras. Prognoser är skapade baserad på historiska data bara. 

Ett objekt och dess dimensioner måste vara en del av endast en punkt fördelningsnyckel om posten fördelningsnyckel används under prognos. 

Lägg till lagerhållningsenhet (SKU) en artikelallokeringsnyckel genom att gå till **huvudplanering**&gt;**inställningar**&gt;**efterfrågeprognosticering**&gt;**artikel fördelningsnycklar**. Använd **Tilldela artiklar** sidan till att tilldela ett objekt till en fördelningsnyckel.

## <a name="intercompany-planning-groups"></a>Koncerninterna planeringsgrupper
Behovsprognoser genererar gränsöverskridande företag prognoser. Företag som planeras tillsammans grupperas i Microsoft Dynamics 365 för operationer i en koncerninterna planeringsgruppen. Om du vill ange per företag vilka artikelallokeringsnycklar anses vara efterfrågan prognoser, associera en artikelallokeringsnyckel med koncernintern planering gruppmedlem genom att gå till **huvudplanering**&gt;**inställningar**&gt;**koncerninterna planeringsgrupper**. 

Om ingen artikelallokeringsnycklar tilldelas koncernintern huvudplanering gruppmedlemmar beräknas en efterfrågeprognos för alla artiklar som har tilldelats alla artikelallokeringsnycklar från alla Dynamics 365 för operationer företag. Extra filtering alternativ för företag och fördelningsnycklar finns på **generera statistiska basprognosen** sida. 

Kontrollera antalet objekt som prognostiseras. Onödiga objekt kan orsaka ökade kostnader när du använder Microsoft Azure maskinen lärande.

## <a name="demand-forecasting-parameters"></a>Parametrar för efterfrågeprognosticering
Ställ in efterfrågan prognoser parametrar genom att gå till **huvudplanering**&gt;**inställningar**&gt;**efterfrågan prognoser parametrar**. Eftersom efterfrågan prognostisera körs cross-firma, installationen är global. Med andra ord, gäller för alla företag. 

Behovsprognoser genereras prognosen i mängder. Därför är den enhet som kvantiteten bör uttryckas i måste specificeras i **efterfrågan** . Enheten måste vara unikt, för att garantera att aggregering och procentuell fördelning. För mer information om summering och procentuell fördelning, se [göra manuella justeringar av den ursprungliga prognosen](manual-adjustments-baseline-forecast.md). För varje enhet som används för artiklar som ingår i behovsprognoser, se till att det finns en konverteringsregel för enheten och den allmänna prognoser enhet. När prognosen generation, en lista över poster som inte har en enhet omräkning finnas loggat, så att du lätt kan korrigera inställningen. 

Behovsprognoser kan användas för att förutse både beroende och oberoende behov. Om till exempel endast **försäljningen för** kryssrutan är markerad och om alla punkter som anses för behovsprognoser är artiklar som säljs, beräknar systemet oberoende efterfrågan. Men kritiska delkomponenterna kan läggas till punkt fördelningsnycklar och ingår i behovsprognoser. I det här fallet, om **Produktionslinje** kryssrutan är markerad, beräknas en beroendeprognos. 

Det finns två sätt för att skapa en originalplan prognos i Dynamics 365 för operationer. Du kan använda modeller för prognoser på toppen av historiska data, eller kan du bara kopiera över historiska data till prognosen. **Prognosen generation strategi** fältet kan du välja mellan dessa två metoder. För att använda prognosmodeller, välj **Azure Machine Learning**. 

Genom att klicka på **prognosdimensioner** i den vänstra rutan i **behovsprognosparametrar** sidan kan du även välja prognos dimensioner som ska användas när behovsprognosen genereras. En prognos dimensionen anger nivån av detaljen att prognosen är definierad för. Företag, ort och objekt fördelningsnyckel är obligatoriska prognos dimensioner, men du kan också generera prognoser på lager, lager status, kundgrupp, land/region, stat och objekt samt alla objekt dimension nivåer. 

Du kan när som helst lägga prognosen dimensioner till listan av dimensioner som används för behovsprognoser. Du kan också ta bort prognos mått från listan. Men manuella justeringar går förlorade om du lägger till eller tar bort en prognos dimension. 

Inte alla objekt beter sig på samma sätt från en behovsprognoser perspektiv. Liknande poster kan grupperas i en fördelningsnyckel och parametrar såsom transaktionstyper och prognosmetod inställningar kan anges per post fördelningsnyckel. Klicka på **alternativet fördelningsnycklar** i den vänstra rutan i **behovsprognoser parametrar sidan**. 

Om du vill generera prognosen använder Dynamics 365 för operationer en webbtjänst för utbildning på datorn. Om du vill ansluta till tjänsten måste du ange Dynamics 365 för operationer följer om du loggar in på Microsoft Azure maskin inlärning Studio:

-   Web Service API (application programming interface)
-   Webbtjänstens slutpunktsadress
-   Azure Storage kontonamn
-   Azure Storage kontonyckel

**Obs!** Azure-lagringskontonamn och nyckeln behövs bara om du använder ett anpassat lagringskonto. Om du distribuerar en lokal version måste ha du en anpassad lagringslösning konto på Azure måste så att tjänsten maskin-utbildning åt historiska data. 

Skapa efterfrågan förutsägelser distribuera du egna service med maskin inlärning Studio eller Dynamics 365 operationer efterfrågan prognoser försök. Anvisningar för driftssättning av Dynamics 365 operationer efterfrågan prognoser försök som en webbtjänst är tillgängliga Dynamics 365 för operationer. På **behovsprognosparametrar** sidan, klicka på **Azure Machine Learning** fliken.

## <a name="settings-for-the-dynamics-365-for-operations-demand-forecasting-machine-learning-service"></a>Inställningar för Dynamics 365 för åtgärder som kräver produktionsprognos service av utbildning
Visa parametrar som kan konfigureras för Dynamics 365 för operationer kräver produktionsprognos service genom att gå till **huvudplanering**&gt;**inställningar**&gt;**efterfrågeprognosticering**&gt;**prognoser algoritmparametrar**. Den **prognoser algoritmparametrar** visas sidan standardvärden för parametrar. Du kan åsidosätta parametrarna för den **efterfrågan prognoser parametrar** sida. På **fliken Allmänt om du** vill skriva över parametrar globalt, eller använda **posten fördelningsnycklar för** att skriva över parametrar per punkt fördelningsnyckel. Parametrar som är över för en fördelningsnyckel som endast påverkar prognosen för de objekt som associeras med objektet fördelningsnyckel.

<a name="see-also"></a>Se även
--------

[Introduction to demand forecasting](introduction-demand-forecasting.md)

[Generating a statistical baseline forecast](generate-statistical-baseline-forecast.md)

[Making manual adjustments to the baseline forecast](manual-adjustments-baseline-forecast.md)


