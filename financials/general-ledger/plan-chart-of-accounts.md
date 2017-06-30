---
title: Planera din kontoplan
description: "Det här avsnittet innehåller information som hjälper dig att planera kontoplanen för din organisation."
author: RobinARH
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: DimensionConfigureAccountStructure, LedgerChartOfAccounts
audience: Application User
ms.reviewer: RobinARH
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 14051
ms.assetid: 10edb129-33f0-4cf9-b2a7-4b7ffa09b229
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 4c57c4fe8cc66228062f7b64c88efe255657d016
ms.contentlocale: sv-se
ms.lasthandoff: 05/25/2017


---

# <a name="plan-your-chart-of-accounts"></a>Planera din kontoplan

[!include[banner](../includes/banner.md)]


Det här avsnittet innehåller information som hjälper dig att planera kontoplanen för din organisation.

Följ och underhålla ekonomisk information i en organisation genom att lägga upp en kontoplan. En kontoplan är en samling av konton som definierar ett ekonomisk ramverk. För att följa transaktionerna i dessa konton kan du lägga till segment, som kallas ekonomiska dimensioner. Ett utgiftskonto kan till exempel inkludera ekonomiska dimensioner som kallas avdelning, kostnadsställe och syfte. Användardefinierade regler, som kallas kontostrukturer och avancerade regler, anger sambandet mellan dessa ekonomiska dimensioner och huvudkontona och andra ekonomiska dimensioner, och även hur transaktioner kan registreras. 

Kontoplanen är en strukturerad lista över en juridisk persons huvudbokskonton. Listan används för att förbereda ekonomiska rapporter för myndigheter och ägare. Kontona grupperas i kontotyper och sedan i större kategorier. På den allmännaste nivån grupperas kontona som kostnader och intäkter (rörelsekonton) samt tillgångar och skulder (balanskonton). 

En kontoplan kan delas och användas av alla juridiska personer i organisationen. Kontoplanen som används av en juridisk person definieras på sidan **Redovisning**. 

Här är några av faktorerna du måste ta hänsyn till när du lägger upp kontoplanen för organisationen:

-   Rapporteringskraven i det land eller den region där organisationen har sin bas
-   Rapporteringskraven för en juridisk person
-   Specificeringsgraden som behövs, både för externa organisationer och för din organisation

Skapa kontoplanen på sidan **Kontoplan**. Huvudkonton kan skapas på sidan **Kontoplan** eller **Huvudkonton**. I dina huvudkonton ska inte användas specialtecken som används som kontoplanavgränsare. Om du har ett specialtecken som är samma som din kontoplanavgränsare, kan du få instabilitet eller också måste du alltid använda uppslagningar eller den utfällbara menyn när du anger konto- och dimensionskombinationer. 

Det är en bra idé att länka huvudkontona till huvudkontokategorier, så att du kan använda ekonomiska standardrapporterna utan att behöva göra några ändringar. Därför kan du snabbt och enkelt designa och underhålla rapporter. 

Använd sidan **Konfigurera kontostrukturer** för att konfigurera kontostrukturer. Kontostrukturer definierar giltiga kombinationer. Kombinationerna, tillsammans med huvudkontona, bildar en kontoplan. 

**Juridisk person åsidosätter** 

Alla huvudkonton är inte giltiga för alla juridiska personer, och några kanske bara är relevanta under en viss tidsperiod. I det här scenariot kan åsidosättandet av juridisk person användas för att identifiera vilka företag huvudkontot ska uppskjutas för, vem ägaren är och tidsperioden dimensionen är aktiv i. Åsidosättandet på den delade nivån kan inte vara restriktivare än åsidosättandet på nivån för juridisk person.

Mer information finns i [Ekonomiska dimensioner](financial-dimensions.md).




