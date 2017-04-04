---
title: "Generera utgångspunkt statistiska prognos"
description: "Den här artikeln innehåller information om parametrar och filter som används i beräkningen av behovsprognoser."
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
ms.custom: 72683
ms.assetid: 42190463-2a64-4f63-b653-10cac3df0692
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ccbe5815ebb54e00265e130be9c82491aebabce
ms.openlocfilehash: c0c918b94fe96d123bb6c25c42fe168a026cd8a9
ms.lasthandoff: 03/31/2017


---

# <a name="generate-a-statistical-baseline-forecast"></a>Generera utgångspunkt statistiska prognos

Den här artikeln innehåller information om parametrar och filter som används i beräkningen av behovsprognoser. 

När du skapar en baslinjeprognos måste du först ange parametrar och filter som används i beräkningen. Du kan till exempel skapa en baslinjeprognos som uppskattar behov baserat på transaktionsdata från det tidigare året för ett specifikt företag, för den föregående månaden och för en vald grupp av artiklar. 

Gå till om du vill generera en efterfrågeprognos **huvudplanering &gt;prognostisering &gt;efterfrågeprognosticering &gt;generera statistiska originalplan prognos**. 

Prognosen skopan kan väljas vid prognos generation tid. Tillgängliga värden är: Dag, vecka och månad. 

Antalet perioder för att skapa en prognos för ligger i** prognoshorisonten** . 

När prognosen är inställd på att **kopiera över historiska behov**, slutet av den historiska horisonten ignoreras. Kopieras antalet behållare som anges i den **prognos horisonten** den prognostiserade efterfrågan från och med datumet i fältet den **från datum** fältgruppen **historiska horisonten**. Genom att kopiera historisk efterfrågan från ett visst datum framåt, Produktionsplanerare kan göra planen för nästa kvartal på två sätt:

-   Genom att kopiera efterfrågan från samma kvartal förra året.
-   Genom att kopiera behovet från föregående kvartal.

För att undvika förvirring i produktionsplaner, ett visst antal prognos kostnadsslag kan frysas. Numret anges i **frys tidsgräns** . Om det **justerade behovet prognos **sida, celler för fryst skopor är avaktiverad, för att ge en visuell indikation på att dessa värden bör inte ändras. 

Startdatum för baslinjen efterfrågan behöver inte vara dagens datum eller ett datum i framtiden. Om du vill ställa in ett annat startdatum, använd den **ursprungliga prognosen startdatum – från fältet datum** . Till exempel, i juni, användare kan generera en prognos för nästa år. Eftersom prognosen hinkar mellan slutet av historisk efterfrågan och start av baslinjen saknas förutsägelser kanske inte exakt. Om du använder Microsoft Dynamics 365 operationer efterfrågan prognoser service finns fyra olika sätt du kan fylla i tomrummen saknas. Du kan välja den metod som du vill genom att ställa in SAKNAT\_värdet\_ersättningsparameter på den **efterfrågan prognoser parametrar** sida. 

Den **prognos originalplanens startdatum** - **från datum** fält måste anges till början av en prognos åldersgrupp, till exempel USA, söndag om veckan produktionsprognos åldersgrupp. Systemet justerar automatiskt den **prognos originalplanens startdatum** - **från datum** fältet att matcha början på en prognos åldersgrupp. 

Den **prognos originalplanens startdatum** - **från datum** fält kan ställas in på ett datum i förflutna. Med andra ord är det möjligt att generera en efterfrågan i det förflutna. Detta finnas användbart, därför att den låter användarna finjustera prognosen service parametrar så att den statistiska prognosen genererades tidigare matchar den faktiska historiska behov. Användarna kan sedan fortsätta använda dessa parameterinställningar för att generera en statistisk ursprungliga prognosen för framtiden. 

Manuella justeringar som gjorts i tidigare behovsprognoser iterationer kan tillämpas automatiskt på den nya baslinjen prognos om **överföringen manuella justeringar till efterfrågan prognos**är markerad. Om kryssrutan är avmarkerad, manuella justeringar inte läggas till den ursprungliga prognosen – men de tas inte bort. Manuella justeringar av prognosen kan bara tas bort vid prognos importera tid, genom att rentvå **spara den manuella justeringar av baslinjen demand forecast** kryssruta. Manuella inställningar sparas på tillståndet. Därför om en användare gör manuella justeringar för prognosen, betyder inte auktorisera prognos till Dynamics 365 för operationer förloras ändringarna. Mer information om manuella justeringar och hur de fungerar finns i [auktorisera justerade prognosen](authorize-adjusted-forecast.md). 

En demand forecast generationen kan ha ett namn och kommentarer för att hjälpa användare att identifiera den prognos som har genererats. Dessa värden visas i prognosen generations historia om **statistisk utgångspunkt prognosen generations historia** sida. 

Den företagsinterna planering grupp, objekt fördelningsnycklar, och andra kan filter appliceras på prognosen generation tid. Dessa kan användas för att förbättra prestanda eller att dela upp data i hanterbara bitar. Notera dock att efterfrågan inte genereras för medlemmar av någon fördelningsnyckel som inte är associerade med en intern planering grupp, även om posten fördelningsnyckel är markerat i urvalsdialogen. 

**Tips!** Ibland användare kan få fel samtidigt som det genererar en efterfrågan eller prognos generation kompletteras med någon sessionslogg. Detta kan ske på grund av överblivna uppgifterna i fråga som tidigare använts för prognos generation. För att lösa problemet klickar **du på för** att öppna fönstret **Fråga** sidan klickar du på **Återställ**och sedan återskapa den ursprungliga prognosen. 

Om prognosen skapas inte för ett stort antal objekt, men, till exempel för en artikel eller en artikelallokeringsnyckel samtidigt och du kan välja för att få bättre prestanda i **Använd lägen svar** kryssrutan på den **Master planning - Setup - efterfrågeprognosticering** - **efterfrågan prognoser parametrar - Azure maskin inlärning** fliken.

<a name="see-also"></a>Se även
--------

[Demand forecasting setup](demand-forecasting-setup.md)

[Making manual adjustments to the baseline forecast](manual-adjustments-baseline-forecast.md)

[Authorizing the adjusted forecast](authorize-adjusted-forecast.md)


