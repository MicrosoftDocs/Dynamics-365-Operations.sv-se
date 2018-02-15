---
title: Planera din kontoplan
description: "Det här avsnittet innehåller information som hjälper dig att planera kontoplanen för din organisation."
author: aprilolson
manager: AnnBe
ms.date: 01/04/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: DimensionConfigureAccountStructure, LedgerChartOfAccounts
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 14051
ms.assetid: 10edb129-33f0-4cf9-b2a7-4b7ffa09b229
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: ad55dd57483de4351c8501c5e226180fc73606aa
ms.openlocfilehash: 3d2cdeaf2fdeb2f587f82c97249886fb8db49154
ms.contentlocale: sv-se
ms.lasthandoff: 01/11/2018

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

Skapa kontoplanen på sidan **Kontoplan**. Huvudkonton kan skapas på sidan **Kontoplan** eller **Huvudkonton**. I dina huvudkonton ska inte användas specialtecken som används som kontoplanavgränsare. Om du har ett specialtecken som är samma som din kontoplanavgränsare, kan du få instabilitet eller också måste du alltid använda uppslagningar eller den utfällbara menyn när du anger konto- och dimensionskombinationer. Mer information finns i [Skapa ett huvudkonto](tasks/create-main-account.md).


Det är en bra idé att länka huvudkontona till huvudkontokategorier, så att du kan använda ekonomiska standardrapporterna utan att behöva göra några ändringar. Därför kan du snabbt och enkelt designa och underhålla rapporter. 

Använd sidan **Konfigurera kontostrukturer** för att konfigurera kontostrukturer. Kontostrukturer definierar giltiga kombinationer. Kombinationerna, tillsammans med huvudkontona, bildar en kontoplan.  Mer information finns i [Skapa en kontostruktur](tasks/create-account-structures.md).

**Juridisk person åsidosätter** 

Alla huvudkonton är inte giltiga för alla juridiska personer, och några kanske bara är relevanta under en viss tidsperiod. I det här scenariot kan åsidosättandet av juridisk person användas för att identifiera vilka företag huvudkontot ska uppskjutas för, vem ägaren är och tidsperioden dimensionen är aktiv i. Åsidosättandet på den delade nivån kan inte vara restriktivare än åsidosättandet på nivån för juridisk person.

Mer information finns i följande avsnitt: [Ekonomiska dimensioner](financial-dimensions.md)
[SKapa och tilldela avancerade regelstrukturer](tasks/create-assign-advanced-rule-structures.md)




