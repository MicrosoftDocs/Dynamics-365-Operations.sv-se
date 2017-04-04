---
title: "Efterfrågan prognoser översikt"
description: "Behovsprognoser används för att förutsäga oberoende efterfrågan från beställningar och beroende efterfrågan på någon frikoppling för kundorder. Förbättrade efterfrågan prognos reducering regler ger en perfekt lösning för massborttagning anpassning."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: ReqDemPlanCreateForecastDialog
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 72004
ms.assetid: 916707c9-1333-460f-a0fa-4e95f6fda2ad
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ccbe5815ebb54e00265e130be9c82491aebabce
ms.openlocfilehash: 9152616b81e7873426f296376b5e57c94439379d
ms.lasthandoff: 03/31/2017


---

# <a name="demand-forecasting-overview"></a>Efterfrågan prognoser översikt

Behovsprognoser används för att förutsäga oberoende efterfrågan från beställningar och beroende efterfrågan på någon frikoppling för kundorder. Förbättrade efterfrågan prognos reducering regler ger en perfekt lösning för massborttagning anpassning.

För att generera den ursprungliga prognosen, en sammanfattning av historiska transaktioner överförs till en Microsoft Azure maskinen lärande service som finnas värtt på Azure. Eftersom denna tjänst är inte delas mellan användare, det kan lätt anpassas till branschspecifika krav. Du kan använda Dynamics 365 för att visualisera prognosen, justera prognosen och visa prestationsindikatorer (KPI: er) om prognos är korrekt.

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

-   **Modularitet** – Behovsprognoser är modulär och enkel att konfigurera. Du kan aktivera och inaktivera funktionen genom att ändra nyckeln i **handel**&gt;**Lagerprognos**&gt;**efterfrågeprognosticering**.
-   **Återanvändning av stapeln Microsoft** – Microsoft lanserat Learning maskin plattform i februari 2015. Inlärning maskin som ingår i Microsoft Cortana analys Suite, kan du snabbt och enkelt skapa försök förutsägbar analys, till exempel efterfrågan uppskattning försök med R algoritmer och programmeringsspråk Python och ett enkelt gränssnitt för dra och släpp.
    -   Du kan hämta Dynamics 365 för operationer på Försök prognoser, ändra dem så att de uppfyller företagets behov, publicera dem som en webbtjänst på Azure och använda dem för att generera efterfrågeprognoser Försök som kan hämtas om du har köpt en Dynamics 365 för abonnemanget operationer för produktionsplanerare som företaget nivåerna användare.
    -   Du kan hämta några av de för närvarande tillgängliga efterfrågan prediction experiment från [Cortana Analytics galleri](https://gallery.cortanaanalytics.com/). Dynamics 365 försök prognoser för operationer automatiskt är integrerad med Dynamics 365 för operationer, kunder och partner hantera integrationen av försök som de hämtas från den [Cortana analys Gallery](https://gallery.cortanaanalytics.com/). Försök därför från den [Cortana analys Gallery](https://gallery.cortanaanalytics.com/) inte så enkel som används som Dynamics 365 för operationer på Prognosticering försök. Antalet försök måste du ändra så att de använder Dynamics 365 för operationer programmeringsgränssnitt (API).
    -   Du kan skapar dina egna experiment i Microsoft Azure maskinen lärande Studio, publicerar dem som tjänster på Azure, och använda dem för att skapa prognoser.
    -   Om du inte kräver höga prestanda, eller om du inte kräver att en stor mängd data som bearbetas kan du använda den fria Machine Learning-nivån. Vi rekommenderar att du alltid börja från denna planet, särskilt under implementering och testning faser. Om du behöver högre prestanda och ytterligare lagringsutrymme kan du använda maskinen lärande standard nivå. Denna nivå kräver en prenumeration på Azure och innebär ytterligare kostnader. För mer information om maskinen lärande prissättning, se <Http://aka.ms/machine-learning-price-info>.
-   **Prognosreducering när som helst decoupling** – prognostisering i Dynamics 365 för operationer bygger på den här funktionen kan du använda prognostiserat behov beroende och de oberoende när som helst decoupling efterfrågan.

## <a name="basic-flow-in-demand-forecasting"></a>Grundflöde i behovsprognoser
Följande diagram visar grundflöde i behovsprognoser. 

[![efterfrågan produktionsprognos introduktion diagram](./media/demand-forecasting-introduction.png)](./media/demand-forecasting-introduction.png)

Efterfrågan prognos börjar generera i Dynamics 365 för operationer. Historiska transaktionsdata från Dynamics 365 för operationer transaktionell databasen samlas och fyller ett mellanlagringsregister. I det här tillfälliga registret matas senare inlärning maskin-tjänsten. Genom att utföra minimal anpassning kan ansluta du olika datakällor till den tillfälliga tabellen. Datakällor kan innehålla Microsoft Excel-filer, kommaavgränsade värden (CSV) filer och data från Microsoft Dynamics AX 2009 och Microsoft Dynamics AX 2012. Därför kan du generera efterfrågeprognoser tänka historiska data sprids bland flera system. Men huvuddata, såsom namn och enheter av åtgärden, måste vara den samma i de olika datakällorna.

Om du använder Dynamics 365 för operationer på Prognosticering maskin inlärning försök de ser ut efter ett bästa val bland fem tid serie produktionsprognos metoder att beräkna utgångspunkt prognos. Parametrarna för dessa metoder produktionsprognos hanteras i Dynamics 365 för operationer. 

Prognoserna historiska data och alla ändringar som har gjorts i efterfrågeprognoser i föregående upprepningar är sedan i Dynamics 365 för operationer. 

Du kan använda Dynamics 365 för operationer att visualisera och ändra originalplan prognoser. Manuella justeringar måste attesteras innan de prognoser som kan användas för planering.

## <a name="limitations"></a>Begränsningar
Efterfrågeprognosticering i Dynamics 365 för operationer är ett verktyg som hjälper kunder att skapa produktionsprognos processer inom tillverkning. Den har kärnfunktioner behov lösningen prognoser och har utformats så att det kan enkelt utökas. Begära prognoser inte kan vara ungefärlig plats för kunder inom exempelvis återförsäljning, grossist, lagring, transport eller andra professionella tjänster.

<a name="see-also"></a>Se även
--------

[Demand forecasting setup](demand-forecasting-setup.md)

[Generating a statistical baseline forecast](generate-statistical-baseline-forecast.md)

[Making manual adjustments to the baseline forecast](manual-adjustments-baseline-forecast.md)

[Authorizing the adjusted forecast](authorize-adjusted-forecast.md)

[Monitoring forecast accuracy](monitor-forecast-accuracy.md)

[Remove outliers from historical transaction data when calculating a demand forecast](remove-historical-outliers-calculating-demand-forecast.md)


