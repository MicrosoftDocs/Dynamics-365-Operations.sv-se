---
title: "Översikt för efterfrågeprognosticering"
description: "Behovsprognoser används för att förutsäga oberoende efterfrågan från beställningar och beroende efterfrågan på någon frikoppling för kundorder. De förbättrade minskningsreglerna för efterfrågeprognosticering ger en perfekt lösning för massanpassning."
author: roxanadiaconu
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ReqDemPlanCreateForecastDialog
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 72004
ms.assetid: 916707c9-1333-460f-a0fa-4e95f6fda2ad
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 869151f2486b7a481e4694cfb6992d0ee2cfc008
ms.openlocfilehash: 6b4498ae05b9495918c0a079cc88903820192a59
ms.contentlocale: sv-se
ms.lasthandoff: 06/13/2017

---

# <a name="demand-forecasting-overview"></a>Översikt för efterfrågeprognosticering

[!include[banner](../includes/banner.md)]


Behovsprognoser används för att förutsäga oberoende efterfrågan från beställningar och beroende efterfrågan på någon frikoppling för kundorder. De förbättrade minskningsreglerna för efterfrågeprognosticering ger en perfekt lösning för massanpassning.

För att generera den ursprungliga prognosen, en sammanfattning av historiska transaktioner överförs till en Microsoft Azure maskinen lärande service som finnas värtt på Azure. Eftersom denna tjänst är inte delas mellan användare, det kan lätt anpassas till branschspecifika krav. Du kan använda Finance and Operations för att visualisera prognosen, justera prognosen och visa viktiga resultatindikatorer (KPI) om prognosprecisionen.

## <a name="key-features-of-demand-forecasting"></a>Nyckeldrag av behovsprognoser
Här är några av de viktigaste funktionerna i behovsprognoser:

-   Generera en statistisk utgångspunkt prognosen som bygger på historiska data.
-   Använd en dynamisk uppsättning prognos dimensioner.
-   Visualisera trender i efterfrågan, konfidensintervall, och justeringar av prognosen.
-   Attestera den justerade prognosen att användas i planeringsprocessen.
-   Ta bort avvikare.
-   Skapa mätningar av prognosprecision.

## <a name="major-themes-in-demand-forecasting"></a>Viktiga teman i behovsprognoser
Tre stora teman genomförs i behovsprognoser:

-   **Modularitet** – Behovsprognoser är modulär och enkel att konfigurera. Du kan aktivera och avaktivera funktionen genom att ändra konfigurationen på **Handel** &gt; **Lagerprognos** &gt; **Efterfrågeprognosticering**.
-   **Återanvändning av Microsoft-stapeln** – Microsoft lanserade plattformen för maskininlärning i februari 2015. Med maskininlärning, som nu ingår i Microsoft Cortana Analytics Suite, kan du snabbt och enkelt skapa försök förutsägbara analysexperiment, till exempel experiment för efterfrågeuppskattning, genom att använda R-algoritmer eller programmeringsspråket Python och ett enkelt gränssnitt för dra och släpp.
    -   Du kan hämta Finance and Operations experiment för efterfrågeprognosticering , ändra dessa för att uppfylla dina affärsbehov, publicera dem som en webbtjänst på Azure och använda dem för att skapa efterfrågeprognoser. Experimenten är tillgängliga för nedladdning om du har köpt en Finance and Operations-prenumeration för en produktionsplanerare som användare på företagsnivå.
    -   Du kan hämta några av de för närvarande tillgängliga efterfrågan prediction experiment från [Cortana Analytics galleri](https://gallery.cortanaanalytics.com/). Medan experimenten för efterfrågeprognos i Finance and Operations automatiskt integreras med Finance and Operations, måste kunder och partner hantera integreringen av experiment som de hämtar från [Cortana Analytics-galleriet](https://gallery.cortanaanalytics.com/). Experiment från [Cortana Analytics-galleriet](https://gallery.cortanaanalytics.com/) kan därför inte användas lika enkelt som experimenten för efterfrågeprognosticering för Finance and Operations. Du måste modifiera koden för experimenten så att de använder programmeringsgränssnittet (API) för Finance and Operations-program.
    -   Du kan skapar dina egna experiment i Microsoft Azure maskinen lärande Studio, publicerar dem som tjänster på Azure, och använda dem för att skapa prognoser.
    -   Om du inte kräver höga prestanda, eller om du inte kräver att en stor mängd data som bearbetas kan du använda den fria Machine Learning-nivån. Vi rekommenderar att du alltid börja från denna planet, särskilt under implementering och testning faser. Om du behöver högre prestanda och ytterligare lagringsutrymme kan du använda maskinen lärande standard nivå. Denna nivå kräver en prenumeration på Azure och innebär ytterligare kostnader. För mer information om maskinen lärande prissättning, se <Http://aka.ms/machine-learning-price-info>.
-   **Prognostiserad minskning vid någon frikoppling** – Efterfrågeprognosticering i Finance and Operations bygger på denna funktion, som låter dig prognosticera såväl beroende som oberoende behov hos någon frikoppling.

## <a name="basic-flow-in-demand-forecasting"></a>Grundflöde i behovsprognoser
Följande diagram visar grundflöde i behovsprognoser. 

[![Introduktionsdiagram till efterfrågeprognosticering](./media/demand-forecasting-introduction.png)](./media/demand-forecasting-introduction.png)

Generering av efterfrågeprognoser börjar i Finance and Operations. Historiska transaktionsdata från transaktionsdatabasen för Finance and Operations samlas in och fyller en mellanlagringstabell. Mellanlagringstabellen matas senare vidare till en maskininlärningstjänst. Genom att utföra minimal anpassning kan du ansluta olika datakällor till mellanlagringstabellen. Datakällorna kan innehålla Microsoft Excel-filer, filer med kommaavgränsade värden (CSV), samt data från Microsoft Dynamics AX 2009 och Microsoft Dynamics AX 2012. Därför kan du generera efterfrågeprognoser som beaktar historiska data spridda över flera system. Men huvuddata, såsom namn och enheter av åtgärden, måste vara den samma i de olika datakällorna.

Om du använder maskininlärningsexperiment för efterfrågeprognos för Finance and Operations, så söker dessa efter den bästa matchningen bland fem prognosticeringsmetoder med tidsserier för att beräkna en baslinje för prognosen. Parametrarna för dessa prognosticeringsmetoder hanteras i Finance and Operations. 

Prognoser, historiska data och alla eventuella ändringar som gjorts i efterfrågeprognoserna i föregående versioner finns sedan tillgängliga i Finance and Operations. 

Du kan använda Finance and Operations för att visualisera och modifiera baslinjeprognoserna. Manuella justeringar måste attesteras innan de prognoser som kan användas för planering.

## <a name="limitations"></a>Begränsningar
Efterfrågeprognosticering i Finance and Operations är ett verktyg som hjälper kunder inom tillverkningsindustrin att skapa prognosprocesser. Det erbjuder kärnfunktionen hos efterfrågeprognosticeringslösningen, och har utformats så att det enkelt kan utökas. Efterfrågeprognosticering är kanske inte det bästa valet för kunder inom exempelvis återförsäljning, grossist, lagring, transport eller andra professionella tjänster.

<a name="see-also"></a>Se även
--------

[Inställningar för behovsprognosticering](demand-forecasting-setup.md)

[Generera en statistisk baslinjeprognos](generate-statistical-baseline-forecast.md)

[Gör manuella justeringar till den ursprungliga prognosen](manual-adjustments-baseline-forecast.md)

[Auktorisering av den justerade prognosen](authorize-adjusted-forecast.md)

[Övervaka prognosprecision](monitor-forecast-accuracy.md)

[Ta bort avskilda från historiska transaktionsdata vid beräkning av en efterfrågeprognos](remove-historical-outliers-calculating-demand-forecast.md)




