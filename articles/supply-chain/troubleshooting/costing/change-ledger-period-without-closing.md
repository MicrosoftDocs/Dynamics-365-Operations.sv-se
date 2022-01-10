---
title: Varningar eller fel vid ändring av redovisningsperiodstatus utan att stänga lager
description: Varningar eller fel vid ändring av redovisningsperiodstatus utan att stänga lager
author: AndersGirke
ms.date: 05/31/2021
ms.topic: troubleshooting
ms.search.form: InventAgingStorage, InventAgingStorageChart, InventAgingStorageDetails, InventValueProcess, InventValueReportSetup, InventClosing
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: aevengir
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 05851753e29da75f014d2cc77e2b8df259620eee
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477618"
---
# <a name="warnings-or-errors-on-changing-ledger-period-status-without-closing-inventory"></a>Varningar eller fel vid ändring av redovisningsperiodstatus utan att stänga lager

Microsoft introducerade följande valideringar för att förhindra problem som orsakas av felaktig periodslutprocess kring kostnadsredovisning. Om du stöter på något av följande felmeddelanden hittar du [KB 4561987](https://fix.lcs.dynamics.com/Issue/Details?kb=4561987&bugId=445351&dbType=3&qc=f514f2adcddcddceec43af58c26ae8a9020effdc7cdfe085d9d0deeb8cc7b6a3) för mer information om hur du löser dessa problem.

- Du kör en ny beräkning med ett datum %1 (10-02-2019). Den senast registrerade omberäkningen kördes under en tidigare period med ett datum %2 (20-01-2019). Inget utförande av en inventering nära ett datum %3 (31-01-2019) matchningsperiodens slut har registrerats. Kom ihåg att köra en lagerstängning från och med %3 (31-01-2019) som matchar periodens slut. Värderingen av lager, sålda varor och avvikelser kan inte vara korrekt i delredovisning eller redovisning förrän denna har utförts.

- Du håller på att ändra status för redovisningsperioden %1 till %2. Inget utförande av en inventering nära ett datum %3 matchningsperiodens slut har registrerats. Kör en lagerstängning för att %3 matcha periodens slut innan du ändrar status. Värderingen av lager, sålda varor och avvikelser kan inte vara korrekt i delredovisning eller redovisning förrän denna har utförts. Rapporterad från juridisk person %4. För tillfället i informationssyfte, men du måste utföra en sådan åtgärd i framtiden.

- Kontostrukturen %1 har ändrats. Ett eller flera huvudkonton %2 finns inte längre. Dessa huvudkonton är obligatoriska för %3 med ett datum %4. Lägg till dessa huvudkonton i kontostrukturen %1 innan du kan återuppta %3 jobbet. För tillfället i informationssyfte, men du måste utföra en sådan åtgärd i framtiden.

- Du håller på att utföra en inventering nära ett datum %1 (31-01-2019). Ingen kostnadskalkylering med automatisk lageravräkning med datum %2 (31-01-2019) matchningsperiodens slut har registrerats. Kom ihåg att utföra en kostnadskalkylering med automatisk lageravräkning med datum %3 (31-01-2019) matchningsperiodens slut. Värderingen av lager, sålda varor och avvikelser kan inte vara korrekt i delredovisning eller redovisning förrän denna har utförts.

- Du håller på att utföra en ny kostnadskalkylering med automatisk lageravräkning med ett datum %1 (28-02-2019). Den senast registrerade kostnadskalkylering med automatisk lageravräkning kördes under en tidigare period med ett datum %2 (31-01-2019). Inget utförande av en inventering nära ett datum %3 (31-01-2019) matchningsperiodens slut har registrerats.

Kom ihåg att köra en lagerstängning från och med %3 (31-01-2019) som matchar periodens slut. Värderingen av lager, sålda varor och avvikelser kan inte vara korrekt i delredovisning eller redovisning förrän lagerstängningen har utförts.