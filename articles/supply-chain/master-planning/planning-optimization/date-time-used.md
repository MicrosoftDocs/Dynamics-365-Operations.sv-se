---
title: Parametrar för datum och tid som används i Planeringsoptimering
description: Det här ämnet innehåller information om de datum- och tidsparametrar som planeringsoptimering använder under operationen.
author: t-benebo
ms.date: 09/21/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2021-09-21
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 0708404f286253449e0400fc65680e903f6d1e9b
ms.sourcegitcommit: ad1afc6893a8dc32d1363395666b0fe1d50e983a
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2022
ms.locfileid: "8468844"
---
# <a name="date-and-time-parameters-used-by-planning-optimization"></a>Parametrar för datum och tid som används i Planeringsoptimering

[!include [banner](../../includes/banner.md)]

Det här ämnet innehåller information om de datum- och tidsparametrar som planeringsoptimering använder under operationen.

Medan den inbyggda huvudplaneringsmotorn använder transaktionsdatum i alla beräkningar fungerar Planeringsoptimering med datum- och tidsvärden som konverteras till datum. Den här skillnaden i beteende kan leda till situationer där prognostransaktioner som skapas vid midnatt den dagen när huvudplaneringen körs inte inkluderas eftersom Planeringsoptimering tar hänsyn till att de har skapats före aktuellt datum.

## <a name="parameters-for-issue-and-demand-transactions"></a>Parametrar för ut- och efterfrågetransaktioner

I följande tabell visas de parametrar som planeringsoptimering använder när ut- och efterfrågetransaktioner bearbetas.

| Parameter | Parameternamn i Planeringsoptimering | Beskrivning | Motsvarande fält i Microsoft Dynamics 365 Supply Chain Management (i registret ReqTrans) |
|---|---|---|---|
| Planerad utleveranstid | `PlannedIssueTime` | Det datum som utleveransen som planeras för. | **Till datum** (`FuturesDate`) och **försenad till tid** (`FuturesTime`) |
| Begärd utleveranstid | `RequestedIssueTime` | Det utfärdandedatum som användaren begärt och angetts i Supply Chain Management. Den här parametern kan bara användas för frisläppta eller godkända planerade order. För planerade order är den tom som standard. | **Begärt datum** (`ReqDateDlvOrig`) |
| Begärd utleveranstid | `RequiredIssueTime` | Det ut utfärdandedatum som justeras genom Planeringsoptimering. Om den begärda ut utfärdandetiden redan har körts när Planeringsoptimering körs, justeras den begärda utfärdandetiden till den första öppna dagen som inte är tidigare än dagens datum. Om den begärda ut utfärdandetiden markeras som blockerad i kalendern, justeras den begärda ut utfärdandetiden till den första öppna dagen före detta datum. | **Behovsdatum** (`ReqDate`) och **Behovstid** (`ReqTime`) |
| Utfärda tidsfördröjning | `IssueTimeDelay` | Tidsskillnaden mellan den planerade ut utfärdandetiden och antingen den begärda ut utfärdandetiden för godkända och frisläppta order eller den begärda ut utfärdandetiden. | **Fördröjning (i dagar)** (`FuturesDays`) |

## <a name="parameters-for-receipt-and-supply-transactions"></a>Parametrar för inleverans- och leveranstransaktioner

I följande tabell visas de parametrar som planeringsoptimering använder när inleverans- och leveranstransaktioner bearbetas.

| Parameter | Parameternamn i Planeringsoptimering | Beskrivning | Motsvarande fält i Supply Chain Management (i registret ReqTrans eller ReqPO) |
|---|---|---|---|
| Planerad tillgänglighetstid | `PlannedAvailabilityTime` | Datumet då kvittot planeras vara tillgängligt. | **Behovsdatum** (`ReqDate`) och **Behovstid** (`ReqTime`) |
| Planerad inleveranstid | `PlannedReceiptTime` | Det datum då inleveransen anländer till platsen. | **Till datum** (`FuturesDate`), **Försenad till tid** (`FuturesTime`) och **Leveransdatum** (`ReqDateDlv`) eller **Begärt datum** (`ReqDateDlvOrig`) om beställningen inte har släppts ännu. |
| Krävd tillgänglighetstid | `RequiredAvailabilityTime` | Det krävda tillgänglighetsdatum som justeras genom Planeringsoptimering. | **Behovsdatum** (`ReqDate`) och **Behovstid** (`ReqTime`) |
| Förväntad inleveranstid | `ExpectedReceiptTime` | Förväntat inleveransdatum för en frisläppt inleverans. Värdet ställs in av användaren i Supply Chain Management och justeras inte genom Planeringsoptimering. Den här parametern gäller bara för frisläppta inleveranser. | **Begärt datum** (`ReqDateDlvOrig`) |
| Obligatorisk inleveranstid | `RequiredReceiptTime` | Det krävda inleveransdatum som justeras genom Planeringsoptimering. | **Behovsdatum** (`ReqDate`) och **Behovstid** (`ReqTime`) |
| Planerad ordertid | `PlannedOrderingTime` | Orderdatumet som beräknas av Planeringsoptimering. | **Orderdatum** (`ReqDateOrder`) och **Ordertid** (`ReqTimeOrder`) |
| Starttid för planerad aktivitet | `PlannedActivityStartTime` | Det datum då aktiviteten för den här inleveransen ska starta. | **Startdatum** (`SchedFromDate`) |
| Fördröjning för inleverans | `ReceiptTimeDelay` | Tidsskillnaden mellan den planerade inleveranstiden och den begärda inleveranstiden. | **Fördröjning (dagar)** (`FuturesDays`) och **Försenad till tid** (`FuturesTime`) |

## <a name="examples-of-date-parameter-use-by-planning-optimization"></a>Exempel på användning av datumparameter av Planeringsoptimering

Planerna i följande illustrationer finns på dagnivå, men planeringsoptimering körs på en mer detaljerad nivå. Eftersom marginalerna till exempel kan vara i timmar kan planeringsordertiden vara den 22 januari 2021, klockan 11:35 och så vidare.

### <a name="example-1-simple-scenario"></a>Exempel 1: Enkelt scenario

En försäljningsorder som har en begärd ut ärendetid den 22 januari täcks av en inköpsorder. Följande inställningar används:

- Ingen produktionstid
- Inga kalendrar (Alla dagar är öppna.)
- Inga marginaler

Illustrationen nedan visar detta scenario. (Välj illustrationen om du vill öppna en större version.)

[![Enkelt scenario.](media/planning-service-dates-1-small.png)](media/planning-service-dates-1.png)

### <a name="example-2-lead-time-scenario"></a>Exempel 2: Scenario för ledtid

En försäljningsorder som har en begärd ut ärendetid den 22 januari täcks av en inköpsorder. Följande inställningar används:

- Tre dagar med ledtid
- Inga kalendrar (Alla dagar är öppna.)
- Inga marginaler

Illustrationen nedan visar detta scenario. (Välj illustrationen om du vill öppna en större version.)

[![Scenario för ledtid.](media/planning-service-dates-2-small.png)](media/planning-service-dates-2.png)

### <a name="example-3-margin-scenario"></a>Exempel 3: Marginalscenario

En försäljningsorder som har en begärd ut ärendetid den 22 januari täcks av en inköpsorder. Följande inställningar används:

- Tre dagar med ledtid
- Ordermarginal på fyra dagar
- Fem dagars tillgänglighetsmarginal
- Inga kalendrar (Alla dagar är öppna.)

Illustrationen nedan visar detta scenario. (Välj illustrationen om du vill öppna en större version.)

[![Marginalscenario.](media/planning-service-dates-3-small.png)](media/planning-service-dates-3.png)

### <a name="example-4-delay-scenario"></a>Exempel 4: fördröjningsscenario

En försäljningsorder som har en begärd ut ärendetid den 22 januari täcks av en inköpsorder. I det här exemplet används samma inställningar som exempel 3, men planeringsdatumet har flyttats till den 15 januari. Bakåtplaneringen (röda märkningar) misslyckas eftersom den planerade ordertiden måste in vara före dagens datum. Därför måste huvudplaneringen planeras framåt, och förseningar inträffar.

Illustrationen nedan visar detta scenario. (Välj illustrationen om du vill öppna en större version.)

[![Fördröjningsscenario.](media/planning-service-dates-4-small.png)](media/planning-service-dates-4.png)

### <a name="example-5-transfer-scenario"></a>Exempel 5: Överföringsscenario

En försäljningsorder från lagerställe 1 som har en begärd utleveranstid den 22 januari täcks av en överföringsorder från lagerställe 2 som täcks av en planerad inköpsorder. Följande inställningar används:

- Tre dagars ledtid för överföring (distributionslager 1)
- Två dagars ledtid för inköp (distributionslager 2)
- Inga kalendrar (Alla dagar är öppna.)

Illustrationen nedan visar detta scenario. (Välj illustrationen om du vill öppna en större version.)

[![Överföringsscenario.](media/planning-service-dates-5-small.png)](media/planning-service-dates-5.png)

### <a name="example-6-lead-time-with-calendars-scenario"></a>Exempel 6: Ledtid med kalenderscenario

En försäljningsorder som har en begärd ut ärendetid den 22 januari täcks av en inköpsorder. Följande inställningar används:

- Tre dagar med ledtid
- Utfärdandekalender (stängd på fredag)
- Tillgänglighetskalender (stängt på torsdag och fredag)
- Inleveranskalender (stängd på tisdag, onsdag och söndag)
- Ledtidskalender (stängt på torsdag och fredag)
- Orderkalender (öppen på måndag och lördag)

Illustrationen nedan visar detta scenario. (Välj illustrationen om du vill öppna en större version.)

[![Ledtid med kalenderscenario.](media/planning-service-dates-6-small.png)](media/planning-service-dates-6.png)

### <a name="example-7-delay-with-calendars-scenario"></a>Exempel 7: Fördröjning med kalenderscenario

En försäljningsorder som har en begärd ut ärendetid den 22 januari täcks av en inköpsorder. I det här exemplet används samma inställningar som exempel 6, men planeringsdatumet har flyttats till den 13 januari. Bakåtplaneringen (röda märkningar) misslyckas eftersom den planerade ordertiden måste in vara före dagens datum. Därför måste huvudplaneringen planeras framåt, och förseningar inträffar.

Illustrationen nedan visar detta scenario. (Välj illustrationen om du vill öppna en större version.)

[![Fördröjning med kalenderscenario.](media/planning-service-dates-7-small.png)](media/planning-service-dates-7.png)
