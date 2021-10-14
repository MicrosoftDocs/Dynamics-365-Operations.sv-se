---
title: Översikt för efterfrågeprognosticering
description: Behovsprognoser används för att förutsäga oberoende efterfrågan från beställningar och beroende efterfrågan på någon frikoppling för kundorder. De förbättrade minskningsreglerna för efterfrågeprognosticering ger en perfekt lösning för massanpassning.
author: ChristianRytt
ms.date: 07/07/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqDemPlanCreateForecastDialog
audience: Application User
ms.reviewer: kamaybac
ms.custom:
- "72004"
- intro-internal
ms.assetid: 916707c9-1333-460f-a0fa-4e95f6fda2ad
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 980001dda67e96ab3f428ad60cb7951dd5de4d0c
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/29/2021
ms.locfileid: "7571027"
---
# <a name="demand-forecasting-overview"></a>Översikt för efterfrågeprognosticering

[!include [banner](../includes/banner.md)]

Behovsprognoser används för att förutsäga oberoende efterfrågan från beställningar och beroende efterfrågan på någon frikoppling för kundorder. De förbättrade minskningsreglerna för efterfrågeprognosticering ger en perfekt lösning för massanpassning.

För att generera den ursprungliga prognosen, en sammanfattning av historiska transaktioner överförs till en Microsoft Azure Machine Learning som finns på Azure. Eftersom denna tjänst är inte delas mellan användare, det kan lätt anpassas till branschspecifika krav. Du kan använda Supply Chain Management för att visualisera prognosen, justera prognosen och visa viktiga resultatindikatorer (KPI) om prognosprecisionen.

> [!NOTE]
> Microsoft Azure Machine Learning Studio (klassisk) krävs för att skapa prognoser med maskininlärning. Från och med den 1 december 2021 kommer du inte att kunna skapa nya resurser för Machine Learning Studio (klassisk). Du kommer dock att kunna fortsätta att använda dina befintliga resurser för Machine Learning studio (klassisk) till den 31 augusti 2024. Uppdaterad information finns i [Azure Machine Learning Studio](/azure/machine-learning/overview-what-is-machine-learning-studio#ml-studio-classic-vs-azure-machine-learning-studio).
> 
> Dynamics 365 Supply Chain Management version 10.0.23 och senare stöd för nya Azure Machine Learning Studio.

## <a name="key-features-of-demand-forecasting"></a>Nyckeldrag av behovsprognoser

Här är några av de viktigaste funktionerna i behovsprognoser:

- Generera en statistisk utgångspunkt prognosen som bygger på historiska data.
- Använd en dynamisk uppsättning prognos dimensioner.
- Visualisera trender i efterfrågan, konfidensintervall, och justeringar av prognosen.
- Attestera den justerade prognosen att användas i planeringsprocessen.
- Ta bort avvikare.
- Skapa mätningar av prognosprecision.

## <a name="major-themes-in-demand-forecasting"></a>Viktiga teman i behovsprognoser

Tre stora teman genomförs i behovsprognoser:

- **Modularitet** – Behovsprognoser är modulär och enkel att konfigurera. Du kan aktivera och avaktivera funktionen genom att ändra konfigurationen på **Handel** &gt; **Lagerprognos** &gt; **Efterfrågeprognosticering**.
- **Återanvändning av Microsoft Stack** – Med maskininlärning, som nu ingår i Microsoft Cortana Analytics Suite, kan du snabbt och enkelt skapa försök förutsägbara analysexperiment, till exempel experiment för efterfrågeuppskattning, genom att använda R-algoritmer eller programmeringsspråket Python och ett enkelt gränssnitt för dra och släpp.
  - Du kan hämta behovsprognoser experiment, ändra dem för att uppfylla dina affärsbehov, publicerar dem som en webbtjänst på Azure, och använda dem för att skapa prognoser. Experimenten är tillgängliga för nedladdning om du har köpt en Supply Chain Management-prenumeration för en produktionsplanerare som användare på företagsnivå.
  - Du kan hämta några av de för närvarande tillgängliga efterfrågan prediction experiment från [Cortana Analytics galleri](https://gallery.cortanaanalytics.com/). Medan experimenten för efterfrågeprognos automatiskt integreras med Supply Chain Management, måste kunder och partner hantera integreringen av experiment som de hämtar från [Cortana Analytics-galleriet](https://gallery.cortanaanalytics.com/). Därför är experiment från [Cortana Analytics-galleri](https://gallery.cortanaanalytics.com/) inte lika enkla att använda som Finance and Operations behovsprognoser experiment. Du måste modifiera koden för experiment så att de använder Finance and Operations (application programming interface).
  - Du kan skapar dina egna experiment i Microsoft Azure Machine Learning Studio (klassisk), publicerar dem som tjänster på Azure, och använda dem för att skapa prognoser.
  - Om du inte kräver höga prestanda, eller om du inte kräver att en stor mängd data som bearbetas kan du använda den fria Machine Learning-nivån. Vi rekommenderar att du alltid börja från denna planet, särskilt under implementering och testning faser. Om du behöver högre prestanda och ytterligare lagringsutrymme kan du använda maskinen lärande standard nivå. Denna nivå kräver en prenumeration på Azure och innebär ytterligare kostnader. För mer information om maskinen lärande prissättning, se [Machine Learning Studio prissättning](https://aka.ms/machine-learning-price-info).
- **Prognostiserad minskning vid någon frikoppling** – Behovsprognoser bygger på denna funktionalitet, vilket låter dig prognosen både beroende och oberoende behov hos någon frikoppling.

## <a name="basic-flow-in-demand-forecasting"></a>Grundflöde i behovsprognoser

Följande diagram visar grundflöde i behovsprognoser.

[![introduktionsdiagram för efterfrågeprognosticering.](./media/demand-forecasting-introduction.png)](./media/demand-forecasting-introduction.png)

Generering av efterfrågeprognos startar i Supply Chain Management. Historiska transaktionsdata från transaktionsdatabasen för Supply Chain Management samlas in och fyller en mellanlagringstabell. Mellanlagringstabellen matas senare vidare till en maskininlärningstjänst. Genom att utföra minimal anpassning kan du ansluta olika datakällor till mellanlagringstabellen. Datakällor kan innehålla Microsoft Excel-filer, kommaavgränsade värdefiler (CSV) och data från Microsoft Dynamics AX 2009 och Microsoft Dynamics AX 2012. Därför kan du generera efterfrågeprognoser som beaktar historiska data spridda över flera system. Men huvuddata, såsom namn och enheter av åtgärden, måste vara den samma i de olika datakällorna.

Om du använder behovsprognoser Machine Learning experiment, de söker en bästa passning mellan fem tidsserier prognosmetoder för att beräkna en baslinje för prognosen. Parametrarna för dessa prognosticeringsmetoder hanteras i Supply Chain Management.

Prognoser, historiska data och alla eventuella ändringar som gjorts i efterfrågeprognoserna i föregående versioner finns sedan tillgängliga i Supply Chain Management.

Du kan använda Supply Chain Management för att visualisera och modifiera baslinjeprognoserna. Manuella justeringar måste attesteras innan de prognoser som kan användas för planering.

## <a name="limitations"></a>Begränsningar

Efterfrågan prognostisera är ett verktyg som hjälper kunder inom tillverkningsindustrin skapar prognosprocesserna. Det erbjuder kärnfunktionen hos efterfrågeprognosticeringslösningen, och har utformats så att det enkelt kan utökas. Efterfrågeprognosticering är kanske inte det bästa valet för kunder inom exempelvis handel, grossist, lagring, transport eller andra professionella tjänster.

### <a name="demand-forecast-variant-conversion-limitation"></a>Konverteringsbegränsning för variant av begärd prognos

Måttenhetskonverteringen (UOM) per variant stöds inte fullt ut när efterfrågeprognosen skapas om lagerenheten skiljer sig från efter efterfrågeprognos UOM.

Generera prognos (**Lagerenhet UOM > Efterfrågeprognos UOM**) använder produktenhetskonvertering. Vid inläsning av historiska data för generering efter efterfrågeprognos kommer enhetskonvertering på produktnivå alltid att användas vid konvertering från lagerenheten till efter efterfrågeprognosenhet, även om det finns konverteringar definierade på variantnivån.

Den första delen av att godkänna prognosen (**Efterfrågeprognosenhet > Lagerenhet**) använder konvertering av produktenhet. Den andra delen av godkänna prognosen ( **lagerenhet > försäljningsenhet**) använder du konvertering av variantenhet. När den genererade efter frågeprognosen är godkänd görs konverteringen till lagerenhet från efterfrågeprognosenhet med enhetskonvertering på produktnivå. Vid samma tidpunkt respekteras konverteringen mellan lagerenheten och försäljningsenheten med de definierade variantkoderna.

Observera att efterfrågeprognosenhet inte behöver ha någon specifik betydelse. Den kan definieras som "efterfrågeenhet". För varje produkt kan du definiera konverteringen till 1:1 med lagerenheten.

## <a name="additional-resources"></a>Ytterligare resurser

[Inställning av efterfrågeprognosticering](demand-forecasting-setup.md)

[Generera en statistisk baslinjeprognos](generate-statistical-baseline-forecast.md)

[Gör manuella justeringar på baslinjeprognosen](manual-adjustments-baseline-forecast.md)

[Auktorisera en justerad efterfrågeprognos](authorize-adjusted-forecast.md)

[Övervaka prognosens exakthet](monitor-forecast-accuracy.md)

[Ta bort avskilda från historiska transaktionsdata när du beräknar en efterfrågeprognos](remove-historical-outliers-calculating-demand-forecast.md)

[Utöka funktionen prognos för efterfrågan](https://www.youtube.com/watch?v=4OIKIXLiNjI&feature=youtu.be)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
