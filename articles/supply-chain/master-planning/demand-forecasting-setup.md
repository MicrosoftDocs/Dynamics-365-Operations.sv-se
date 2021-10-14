---
title: Behovsprognoser inställning
description: Detta avsnitt beskriver de uppgifter som du måste utföra för att förbereda behovsprognoser.
author: ChristianRytt
ms.date: 08/09/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqDemPlanDefaultAlgorithmParameters, ReqDemPlanForecastParameters
audience: Application User
ms.reviewer: kamaybac
ms.custom: 72653
ms.assetid: c5fa4b09-512d-4349-ac51-cc13da69a160
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6f71d7a1ef2e8b6a113124d3fb17f1681d62aed9
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/29/2021
ms.locfileid: "7575762"
---
# <a name="demand-forecasting-setup"></a>Behovsprognoser inställning

[!include [banner](../includes/banner.md)]

Detta avsnitt beskriver de uppgifter som du måste utföra för att förbereda behovsprognoser.  

Förval uppgifter ingår att inrätta följande data och parametrar.

## <a name="item-allocation-keys"></a>Artikelallokeringsnycklar

En efterfrågan prognosen beräknas för ett objekt och dess dimensioner endast om objektet är en del av en fördelningsnyckel. Denna regel tillämpas för att gruppera ett stort antal artiklar i syfte att kunna efterfrågeprognoser kan skapas snabbare. Procentandelen för artikelallokeringsnyckel ignoreras när efterfrågeprognoser genereras. Prognoser är skapade baserad på historiska data bara.

Ett objekt och dess dimensioner måste vara en del av endast en punkt fördelningsnyckel om posten fördelningsnyckel används under prognos.

För att lägga till en lagerhållningsenhet (SKU) i en artikelallokeringsnyckel, gå till **Huvudplanering \> Konfigurera \> Efterfrågeprognosticering \> Artikelallokeringsnycklar**. Använd **Tilldela artiklar** sidan till att tilldela ett objekt till en fördelningsnyckel.

## <a name="intercompany-planning-groups"></a>Koncerninterna planeringsgrupper

Behovsprognoser genererar gränsöverskridande företag prognoser. I Dynamics 365 Supply Chain Management grupperas företag som är planerade tillsammans i en koncernintern planeringsgrupp. För att ange (efter företag) vilka artikelallokeringsnycklar som ska beaktas för efterfrågeprognosticering, associera en artikelallokeringsnyckel med den koncerninterna planeringsgruppmedlemmen genom att gå till **Huvudplanering \> Konfigurera \> Koncerninterna planeringsgrupper**.

Om inget objekt fördelningsnycklar tilldelas företagsinterna planering gruppmedlemmar, en efterfrågan prognosen beräknas för alla artiklar som är tilldelade till alla objekt fördelningsnycklar från alla företag. Extra filtering alternativ för företag och fördelningsnycklar finns på **generera statistiska basprognosen** sida.

Kontrollera antalet objekt som prognostiseras. Onödiga objekt kan orsaka ökade kostnader när du använder Microsoft Azure Machine Learning.

## <a name="demand-forecasting-parameters"></a>Parametrar för efterfrågeprognosticering

Gå till **Huvudplanering \> Konfigurera \> \> Efterfrågeprognosticering \> Parametrar för efterfrågeprognosticering** för att konfigurera parametrar för efterfrågeprognosticering. Eftersom efterfrågan prognostisera körs cross-firma, installationen är global. Det betyder att konfigurationen gäller för alla företag.

Behovsprognoser genereras prognosen i mängder. Därför är den enhet som kvantiteten bör uttryckas i måste specificeras i **efterfrågan** . Måttenheten måste vara unikt, för att säkerställa att aggregering och procentuell fördelning blir förståelig. För mer information om summering och procentuell fördelning, se [göra manuella justeringar av den ursprungliga prognosen](manual-adjustments-baseline-forecast.md). För varje enhet som används för artiklar som ingår i behovsprognoser, se till att det finns en konverteringsregel för enheten och den allmänna prognoser enhet. När prognosen generation, en lista över poster som inte har en enhet omräkning finnas loggat, så att du lätt kan korrigera inställningen.

Behovsprognoser kan användas för att förutse både beroende och oberoende behov. Om till exempel endast **försäljningen för** kryssrutan är markerad och om alla punkter som anses för behovsprognoser är artiklar som säljs, beräknar systemet oberoende efterfrågan. Men kritiska delkomponenterna kan läggas till punkt fördelningsnycklar och ingår i behovsprognoser. I det här fallet, om **Produktionslinje** kryssrutan är markerad, beräknas en beroendeprognos.

Det finns två metoder för att skapa en baslinje prognos. Du kan använda modeller för prognoser på toppen av historiska data, eller kan du bara kopiera över historiska data till prognosen. **Prognosen generation strategi** fältet kan du välja mellan dessa två metoder. För att använda prognosmodeller, välj **Azure Machine Learning**.

Genom att välja **Prognosdimensioner** i den vänstra rutan på sidan **Parametrar för efterfrågeprognosticering** kan du även välja den uppsättning prognosdimensioner som ska användas när efterfrågeprognosen genereras. En prognos dimensionen anger nivån av detaljen att prognosen är definierad för. Företag, plats och artikelallokeringsnyckel är obligatoriska prognosdimensioner, men du kan också generera prognoser på lagerställe, lagerstatus, kundgrupp, kundkonto, land/region, stat och artikel samt alla objektdimensionsnivåer.

Du kan när som helst lägga prognosen dimensioner till listan av dimensioner som används för behovsprognoser. Du kan också ta bort prognos mått från listan. Men manuella justeringar går förlorade om du lägger till eller tar bort en prognos dimension.

Inte alla objekt beter sig på samma sätt från perspektivet efterfrågeprognosticering. Liknande poster kan grupperas i en fördelningsnyckel och parametrar såsom transaktionstyper och prognosmetod inställningar kan anges per post fördelningsnyckel. Välj **Artikelallokeringsnycklar** i den vänstra rutan på sidan **Parametrar för efterfrågeprognosticering**.

Supply Chain Management använder en webbtjänst för maskininlärning för att generera prognosen. För att ansluta till tjänsten måste du tillhandahålla följande information när du loggar in på Microsoft Azure Machine Learning Studio (klassisk):

- Web Service API (application programming interface)
- Webbtjänstens slutpunktsadress
- Azure Storage kontonamn
- Azure Storage kontonyckel

> [!NOTE]
> Azure-lagringskontonamn och nyckeln behövs bara om du använder ett anpassat lagringskonto. Om du använder den lokala versionen måste du ha ett anpassat lagringskonto på Azure, detta så att maskininlärning kan få åtkomst till historiska data.

För att skapa efterfrågeförutsägelser kan du använda din egen service genom att använda Machine Learning Studio eller Supply Chain Management behovsprognoser för efterfrågeprognoser. Instruktioner för att implementera experiment för efterfrågeprognosticering som en webbtjänst finns i Supply Chain Management. På sidan **Parametrar för efterfrågeprognosticering** öppnar du fliken **Azure Machine Learning**.

## <a name="settings-for-the-demand-forecasting-machine-learning-service"></a>Inställningar för maskininlärningstjänst för behovsprognoser

För att visa de parametrar som kan konfigureras för tjänsten för efterfrågeprognosticering går du till **Huvudplanering \> Konfigurera \> Efterfrågeprognosticering \> Parametrar för prognosalgoritm**. Sidan **Standardparametrar för prognosalgoritm** visar standardvärden för parametrarna. Du kan skriva över dessa parametrar genom att gå till **Huvudplanering \> Konfigurera \> Efterfrågeprognosticering \> Parametrar för efterfrågeprognosticering** där du kan göra följande:

- Använda fliken **Allmänt** för att skriva över parametrarna globalt.
- Använda fliken **Artikelallokeringsnycklar** för att skriva över parametrarna per artikelallokeringsnyckel. Parametrar som är över för en fördelningsnyckel som endast påverkar prognosen för de objekt som associeras med objektet fördelningsnyckel.

### <a name="forecast-algorithm-parameters"></a>Parametrar för prognosalgoritm

På fliken **Artikelallokeringsnycklar** på sidan **Parametrar för efterfrågeprognosticering** kan du använda snabbfliken **Parametrar för prognosalgoritm** för att tilldela prognosalgoritmparametrar för den artikelallokeringsnyckel som har valts i rutnätet till vänster. Använd knapparna **Lägg till** och **Ta bort** i verktygsfältet för att skapa den samling parametrar som krävs. Välj ett av följande värden i fältet **Namn** för varje parameter i listan och ange ett lämpligt värde i fältet **Värde**:

- **Konfidensnivå i procent** – Ett konfidensintervall består av ett antal värden som fungerar som goda prognoser för efterfrågan. En 95-procentig konfidensnivå procenttal indikerar att det finns en 5-procentig risk att framtida efterfrågan faller utanför konfidensintervallet.
- **Framtvinga säsongsvarianter** – Anger om modellen ska använda en viss typ av säsongsvarianter. Gäller endast ARIMA och ETS. Alternativ: AUTO (standard), NONE, ADDITIVE, MULTIPLICATIVE.
- **Prognosmodell** – Alternativ: ARIMA, ETS, STL, ETS+ARIMA, ETS+STL, ALL. För att välja den modell som passar bäst, använd **ALL**.
- **Maximalt prognostiserat värde** – Anger det högsta värde som ska användas för prognoser. Format: + 1E[n] eller numerisk konstant.
- **Minimalt prognostiserat värde** – Anger det minsta värde som ska användas för prognoser. Format: -1E[n] eller numerisk konstant.
- **Värdeersättning saknas** – Anger hur luckor i historiska data ska fyllas i. Alternativ: numeriskt värde, MEAN, PREVIOUS, INTERPOLATE LINEAR, INTERPOLATE POLYNOMIAL.
- **Intervall för ersättning för saknat värde** – Anger om värdesubstitutionen endast gäller datumområdet för varje enskilt granularitetsattribut eller för hela datauppsättningen. Följande alternativ är tillgängliga för att fastställa det datumintervall som används i systemet vid ifyllning av luckor i historiska data:

  - GLOBAL – Systemet använder hela datumintervallet för alla granularitetsattribut.
  - HISTORY_DATE_RANGE – Systemet använder ett specifikt datumintervall som definieras i fälten **Från datum** och **Till datum** i fältgruppen **Historisk horisont** i dialogrutan **Generera statistisk baslinjeprognos**.
  - GRANULARITY_ATTRIBUTE – Systemet använder datumintervallet för det för tillfället bearbetade granularitetsattributet.

  > [!NOTE]
  > Ett granularitetsattribut är en kombination av prognosdimensioner som prognosen görs mot. Du kan definiera prognosdimensioner på sidan **Parametrar för efterfrågeprognosticering**.

- **Ledtråd för säsongsvarianter** – För säsongsvariationsdata anger du en ledtråd för prognosmodellen för att förbättra prognosnoggrannheten. Format: heltal som representerar antalet grupper som ett efterfrågansmönster upprepas. Ange till exempel "6" för data som upprepas var 6:e månad.
- **Testuppsättningsstorlek i procent** – Procentandel av historiska data som ska användas som testuppsättning för beräkning av prognosexakthet.

## <a name="additional-resources"></a>Ytterligare resurser

- [Efterfrågeprognosticering – översikt](introduction-demand-forecasting.md)
- [Generera en statistisk baslinjeprognos](generate-statistical-baseline-forecast.md)
- [Gör manuella justeringar på baslinjeprognosen](manual-adjustments-baseline-forecast.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
