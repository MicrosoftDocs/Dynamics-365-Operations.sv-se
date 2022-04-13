---
title: Felsöka planeringsoptimering
description: I det här avsnittet beskrivs hur du åtgärdar problem som kan uppstå när du arbetar med planeringsoptimering.
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
ms.openlocfilehash: 667a4ea1fc720feca95fc34c0e2437b4ad9862f2
ms.sourcegitcommit: ad1afc6893a8dc32d1363395666b0fe1d50e983a
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2022
ms.locfileid: "8469685"
---
# <a name="troubleshoot-planning-optimization"></a>Felsöka planeringsoptimering 

[!include [banner](../../includes/banner.md)]

I det här avsnittet beskrivs hur du åtgärdar vanliga problem som kan uppstå när du arbetar med planeringsoptimering.

## <a name="installation-of-the-planning-optimization-add-in-doesnt-complete"></a>Installationen av tillägget för planeringsoptimering slutförs inte

Planeringsoptimering kräver en LCS-aktiverad miljö med hög tillgänglighet, lägst nivå 2, (inte en OneBox-miljö) med Dynamics 365 Supply Chain Management version 10.0.7 eller senare. Om du försöker installera tillägget på i en OneBox-miljö slutförs inte installationen.

**Korrigering**: Avbryt installationen och använd en miljö med hög tillgänglighet, nivå 2 eller högre (inte en Onebox-miljö).

## <a name="planning-of-batch-jobs-fails-when-planning-optimization-is-enabled"></a>Planering av batchjobb misslyckas när planeringsoptimeringen aktiveras

När du aktiverar planeringsoptimering inaktiveras den inbyggda huvudplaneringsmotorn automatiskt. Huvudplaneringsjobb i batch som har skapats för den inbyggda Supply Chain Management-motorn kommer att misslyckas om de utlöses medan planeringsoptimeringen är aktiverad. Ett felmeddelande, till exempel *Denna åtgärd utlöste en huvudplanering som inte stöds när planeringsoptimering har aktiverats*, kan komma att visas.

**Korrigera**: Avbryt alla batchjobb för huvudplanering som har skapats för den inbyggda planeringsmotorn för Supply Chain Management.

## <a name="planning-optimization-results-are-different-from-earlier-results"></a>Resultaten av planeringsoptimeringen skiljer sig från tidigare resultat

Planeringsoptimeringen skiljer sig från den inbyggda huvudplaneringsdesignen i vissa områden. Detta kan också orsakas av väntande funktioner.

**Korrigera**: Kör anpassningsanalys av planeringsoptimeringen och analysera resultatet när du refererar till den tillhörande dokumentationen i syfte att förstå konsekvenserna. Mer information finns i [anpassningsanalys för planeringsoptimering](planning-optimization-fit-analysis.md).

## <a name="cant-enable-planning-optimization"></a>Kan du inte aktivera planeringsoptimeringen?

**Anslutningsstatusen** måste vara **Ansluten** innan du kan ange **Använd planeringsoptimering** som **Ja**. Mer information finns i [komma igång med planeringsoptimering](get-started.md).

**Korrigera**: Kontrollera att tillägget för planeringsoptimering har installerats.

## <a name="error-message-is-shown-during-ctp"></a>Felmeddelande visas under CTP

Om du försöker köra CTP ("capabel to promise") från en försäljningsorder när planeringsoptimering är aktiverad, visas följande felmeddelande: *Denna åtgärd utlöser huvudplanering som inte stöds när planeringsoptimering aktiveras*.

Detta är relaterat till en väntande funktion som planeras som en del av supporten för tillverkningsorder.

**Korrigera;** Undvik CTP-beräkningar när planeringsoptimering är aktiverat tills CTP-stödet är tillgängligt.

## <a name="additional-resources"></a>Ytterligare resurser

[Kom igång med planeringsoptimering](get-started.md)

[Bristanalys för planeringsoptimering](planning-optimization-fit-analysis.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]