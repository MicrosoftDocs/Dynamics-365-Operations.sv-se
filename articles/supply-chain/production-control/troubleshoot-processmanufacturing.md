---
title: Felsöka processtillverkning
description: I det här avsnittet beskrivs hur du åtgärdar problem som kan uppstå när du arbetar med processtillverkning.
author: SmithaNataraj
manager: tfehr
ms.date: 11/04/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: smnatara
ms.search.validFrom: 2020-11-04
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: d999c91aa1cc14f29ebfa6be8e456e45ef0d3fa4
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "4966190"
---
# <a name="troubleshoot-process-manufacturing"></a>Felsöka processtillverkning

I det här avsnittet beskrivs hur du åtgärdar problem som kan uppstå när du arbetar med processtillverkning.

## <a name="when-i-use-the-job-card-device-to-report-a-partial-quantity-on-the-last-job-in-a-production-order-all-the-previous-jobs-on-that-order-that-have-a-status-of-in-progress-are-automatically-ended"></a>När jag använder jobbkortsenheten för att rapportera en delkvantitet för det sista jobbet i en tillverkningsorder, avslutas automatiskt alla tidigare jobb på den ordern som har statusen pågår.

Detta beteende är av design. På sidan **Standarder för produktionsorde** på fliken **Rapportera som färdigt** finns ett alternativ som heter **Slutmarkera flöde**. Om det här avsnittet är inställt på *Ja*, bokförs en flödeskortjournal när en arbetare använder jobbkortsenhet eller jobbkortsterminal för att rapportera den senaste operationen. Den här journalen markerar alla operationer som slutförda och avslutar alla produktionsjobb. När alternativet **Slutmarkera flöde** anges till *Ja* tar systemet inte hänsyn till jobbstatus som den anställde valde när de rapporterade den senaste operationen. Systemet betraktar inte heller om arbetaren rapporterar en fullständig eller partiell kvantitet.

## <a name="when-i-attempt-a-stock-closing-i-receive-the-following-warning-message-no-execution-of-backflush-costing-calculation-with-a-date-1-matching-period-end-has-been-registered"></a>När jag försöker stänga aktier får jag följande varningsmeddelande: "Inget utförande av kostnadskalkylering med automatisk lageravräkning med datum %1 matchningsperiodens slut har registrerats".

I versioner före release 10.0.13 får du följande felaktiga varningsmeddelande under lagerstängning om du inte använder det lean produktionskostnadsflödet:

> Du utför en lagerstängning med ett datum %1. Ingen kostnadskalkylering med automatisk lageravräkning med datum %1 matchningsperiodens slut har registrerats. Kom ihåg att utföra en kostnadskalkylering med automatisk lageravräkning med datum %1 matchningsperiodens slut. Värderingen av lager, sålda varor och avvikelser kan inte vara korrekt i delredovisning eller redovisning förrän denna har utförts.

Det här problemet har korrigerats i version 10.0.13 och senare. Mer information finns i [KB 4582468](https://fix.lcs.dynamics.com/Issue/Details?kb=4582468&bugId=468844&dbType=3&qc=fcd64080446a27382cfde3e4c3bdcfb714279185932259cd11ceb0d500617296).
