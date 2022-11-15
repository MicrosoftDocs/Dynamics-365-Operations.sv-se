---
title: Felsöka Planeringsoptimering
description: I denna artikel beskrivs hur du åtgärdar problem som kan uppstå när du arbetar med Planeringsoptimering.
author: t-benebo
ms.date: 05/07/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: benebotg
ms.search.validFrom: 2020-5-7
ms.dyn365.ops.version: AX 10.0.9
ms.openlocfilehash: 37c38ab9cec8ae3c9d4decf8043b43ea2251083e
ms.sourcegitcommit: 491ab9ae2b6ed991b4eb0317e396fef542d3a21b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/03/2022
ms.locfileid: "9739740"
---
# <a name="troubleshoot-planning-optimization"></a>Felsöka Planeringsoptimering 

[!include [banner](../../includes/banner.md)]

I denna artikel beskrivs hur du åtgärdar vanliga problem som kan uppstå när du arbetar med Planeringsoptimering.

## <a name="installation-of-the-planning-optimization-add-in-doesnt-complete"></a>Installationen av tillägget för Planeringsoptimering slutförs inte

Planeringsoptimering kräver en LCS-aktiverad miljö med hög tillgänglighet, lägst nivå 2, (inte en OneBox-miljö) med Dynamics 365 Supply Chain Management version 10.0.7 eller senare. Om du försöker installera tillägget på i en OneBox-miljö slutförs inte installationen.

**Korrigering**: Avbryt installationen och använd en miljö med hög tillgänglighet, nivå 2 eller högre (inte en Onebox-miljö).

## <a name="planning-of-batch-jobs-fails-when-planning-optimization-is-enabled"></a>Planering av batchjobb misslyckas när Planeringsoptimeringen aktiveras

När du aktiverar Planeringsoptimering inaktiveras den inaktuella huvudplaneringsmotorn automatiskt. Huvudplaneringsjobb i batch som har skapats för den inaktuella huvudplaneringsmotorn kommer att misslyckas om de utlöses medan Planeringsoptimeringen är aktiverad. Ett felmeddelande, till exempel *Denna åtgärd utlöste en huvudplanering som inte stöds när Planeringsoptimering har aktiverats*, kan komma att visas.

**Korrigera**: Avbryt alla batchjobb för huvudplanering som har skapats för den inaktuella huvudplaneringsmotorn.

## <a name="planning-optimization-results-are-different-from-earlier-results"></a>Resultaten av Planeringsoptimeringen skiljer sig från tidigare resultat

Planeringsoptimeringen skiljer sig från den inaktuella huvudplaneringsmotorn i vissa områden. Detta kan också orsakas av väntande funktioner.

**Korrigera**: Kör anpassningsanalys av Planeringsoptimeringen och analysera resultatet när du refererar till den tillhörande dokumentationen i syfte att förstå konsekvenserna. Mer information finns i [anpassningsanalys för Planeringsoptimering](planning-optimization-fit-analysis.md).

## <a name="cant-enable-planning-optimization"></a>Kan du inte aktivera Planeringsoptimeringen?

**Anslutningsstatusen** måste vara **Ansluten** innan du kan ange **Använd Planeringsoptimering** som **Ja**. Mer information finns i [komma igång med Planeringsoptimering](get-started.md).

**Korrigera**: Kontrollera att tillägget för Planeringsoptimering har installerats.

## <a name="error-message-is-shown-during-ctp"></a>Felmeddelande visas under CTP

Om du försöker köra CTP ("capabel to promise") från en försäljningsorder när Planeringsoptimering är aktiverad, visas följande felmeddelande: *Denna åtgärd utlöser huvudplanering som inte stöds när Planeringsoptimering aktiveras*.

Detta är relaterat till en väntande funktion som planeras som en del av supporten för tillverkningsorder.

**Korrigera;** Undvik CTP-beräkningar när Planeringsoptimering är aktiverat tills CTP-stödet är tillgängligt.

## <a name="additional-resources"></a>Ytterligare resurser

- [Kom i gång med huvudplanering](get-started.md)
- [Bristanalys för Planeringsoptimering](planning-optimization-fit-analysis.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]