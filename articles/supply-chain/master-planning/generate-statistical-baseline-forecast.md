---
title: Generera en statistisk baslinjeprognos
description: Det här ämne innehåller information om parametrar och filter som används i beräkningen av behovsprognoser.
author: roxanadiaconu
manager: tfehr
ms.date: 07/08/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqDemPlanCreateForecastDialog
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 72683
ms.assetid: 42190463-2a64-4f63-b653-10cac3df0692
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: db0ac2d56db46f283716df6615e404a5354f8d3e
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/10/2020
ms.locfileid: "3982855"
---
# <a name="generate-a-statistical-baseline-forecast"></a>Generera en statistisk baslinjeprognos

[!include [banner](../includes/banner.md)]

Det här ämne innehåller information om parametrar och filter som används i beräkningen av behovsprognoser. 

När du skapar en baslinjeprognos måste du först ange parametrar och filter som används i beräkningen. Du kan till exempel skapa en baslinjeprognos som uppskattar behov baserat på transaktionsdata från det tidigare året för ett specifikt företag, för den föregående månaden och för en vald grupp av artiklar. 

För att generera en efterfrågeprognosticering, gå till **Huvudplanering &gt; Prognoser &gt; Efterfrågeprognos &gt; Generera statistisk baslinjeprognos**. 

Prognosen skopan kan väljas vid prognos generation tid. Tillgängliga värden är: Dag, vecka och månad. 

Antalet perioder för att skapa en prognos för ligger i **prognoshorisonten** . 

När prognosen är inställd på att **kopiera över historiska behov**, slutet av den historiska horisonten ignoreras. Systemet kopierar det antal grupper som anges i fältet **Prognoshorisont** till fältet för prognostiserad efterfrågan, med början på det datum som anges i fältet **Startdatum** under **Historisk horisont**. Genom att kopiera historisk efterfrågan från ett visst datum framåt, Produktionsplanerare kan göra planen för nästa kvartal på två sätt:

-   Genom att kopiera efterfrågan från samma kvartal förra året.
-   Genom att kopiera behovet från föregående kvartal.

För att undvika förvirring i produktionsplaner, ett visst antal prognos kostnadsslag kan frysas. Numret anges i **frys tidsgräns** . Om det **justerade behovet prognos** sida, celler för fryst skopor är avaktiverad, för att ge en visuell indikation på att dessa värden bör inte ändras. 

Startdatum för baslinjen efterfrågan behöver inte vara dagens datum eller ett datum i framtiden. Om du vill ställa in ett annat startdatum, använd den **ursprungliga prognosen startdatum – från fältet datum** . Till exempel, i juni, användare kan generera en prognos för nästa år. Eftersom prognosen hinkar mellan slutet av historisk efterfrågan och start av baslinjen saknas förutsägelser kanske inte exakt. Om du använder tjänsten behovsprognoser finns det fyra sätt som du kan fylla i de felande luckor. Du kan välja den metod som du vill använda genom att ange parametern MISSING\_VALUE\_SUBSTITUTION på sidan **Parametrar för efterfrågeprognosticering**. 

> [!NOTE]
> Saknad värdeersättning fungerar endast för luckor i data mellan start- och slutdatum för historiska data. Den kommer inte att fylla i data före eller efter den sista fysiska datapunkten, men den fungerar bara som extrapolering mellan faktiska, befintliga datapunkter. 

Värdet i fältet **Startdatum för statistisk baslinje prognos** - **Startdatum** måste vara i början på prognosgruppen, till exempel (i USA) en söndag om prognosgruppen är veckan. Systemet justerar automatiskt fältet **Startdatum för baslinjeprognos** - **Startdatum** så att detta matchar början på en prognosgrupp. 

Fältet **Startdatum för prognosgrupp** - **Startdatum** kan också anges som ett datum som redan passerat. Med andra ord är det möjligt att generera en efterfrågan i det förflutna. Detta är användbart, därför att den låter användarna justera prognosen serviceparametrar så att den statistiska prognosen genererades tidigare matchar den faktiska historiska behov. Användarna kan sedan fortsätta använda dessa parameterinställningar för att generera en statistisk ursprungliga prognosen för framtiden. 

Manuella justeringar som gjorts i tidigare behovsprognoser iterationer kan tillämpas automatiskt på den nya baslinjen prognos om **överföringen manuella justeringar till efterfrågan prognos**är markerad. Om kryssrutan är avmarkerad, manuella justeringar inte läggas till den ursprungliga prognosen – men de tas inte bort. Manuella justeringar av prognosen kan bara tas bort vid prognos importera tid, genom att rentvå **spara den manuella justeringar av baslinjen demand forecast** kryssruta. Manuella inställningar sparas på tillståndet. Om en användare gör manuella justeringar av prognosen men inte auktoriserar prognosen tillbaka till Supply Chain Management, kommer ändringarna därför att försvinna. Mer information om manuell justeringar och hur de fungerar, se [Auktorisera justerad prognos](authorize-adjusted-forecast.md). 

En demand forecast generationen kan ha ett namn och kommentarer för att hjälpa användare att identifiera den prognos som har genererats. Dessa värden visas i prognosen generations historia om **statistisk utgångspunkt prognosen generations historia** sida. 

Den företagsinterna planering grupp, objekt fördelningsnycklar, och andra kan filter appliceras på prognosen generation tid. Dessa kan användas för att förbättra prestanda eller att dela upp data i hanterbara bitar. Notera dock att efterfrågan inte genereras för medlemmar av någon fördelningsnyckel som inte är associerade med en intern planering grupp, även om posten fördelningsnyckel är markerat i urvalsdialogen. 

> [!TIP]
> Ibland användare kan få fel samtidigt som det genererar en efterfrågan eller prognos generation kompletteras med någon sessionslogg. Detta kan ske på grund av överblivna uppgifterna i fråga som tidigare använts för prognos generation. För att lösa problemet klickar **du på för** att öppna fönstret **Fråga** sidan klickar du på **Återställ** och sedan återskapa den ursprungliga prognosen. 

Om prognosen inte skapas för en stor grupp objekt, utan (till exempel) för en enda artikel eller en artikelallokeringsnyckel åt gången, kan du markera kryssrutan **Använd svarsläge för begäran** på fliken **Huvudplanering - Inställningar - Efterfrågeprognosticering** - **Parametrar för efterfrågeprognosticering** för att få en bättre prestanda.

> [!NOTE]
> En potentiell prognos som ser platt ut kan bero på historiska data som måste vara en längre historisk tidsram (minst tre tidsperioder för att kunna plocka ut mönster, t.ex. 3 år med månatlig prognos). Om du vill få ett bättre resultat kan du försöka med att ändra tidsområdets granularitet eller öka tidsintervallet.

<a name="additional-resources"></a>Ytterligare resurser
--------

- [Inställning av efterfrågeprognosticering](demand-forecasting-setup.md)

- [Gör manuella justeringar på baslinjeprognosen](manual-adjustments-baseline-forecast.md)

- [Auktorisera en justerad efterfrågeprognos](authorize-adjusted-forecast.md)
