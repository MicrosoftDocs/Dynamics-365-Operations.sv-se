---
title: Planera kontoplanen
description: De här ämnena innehåller information som hjälper dig att planera kontoplanen för din organisation.
author: aprilolson
manager: AnnBe
ms.date: 04/02/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DimensionConfigureAccountStructure, LedgerChartOfAccounts
audience: Application User
ms.reviewer: roschlom
ms.custom: 14051
ms.assetid: 10edb129-33f0-4cf9-b2a7-4b7ffa09b229
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6e568fca70ea2048d881681ff7ab8ebc6fad6450
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "4990374"
---
# <a name="plan-your-chart-of-accounts"></a>Planera kontoplanen

[!include [banner](../includes/banner.md)]

Det här ämnet innehåller information som hjälper dig att planera kontoplanen för din organisation.

Följ och underhålla ekonomisk information i en organisation genom att lägga upp en kontoplan. En kontoplan är en samling av konton som definierar ett ekonomisk ramverk. För att ytterligare spåra transaktionerna i kontona, kan du lägga till segment. Dessa segment kallas för ekonomiska dimensioner. Ett utgiftskonto kan till exempel inkludera ekonomiska dimensioner som kallas avdelning, kostnadsställe och syfte. Användardefinierade regler anger sambandet mellan dessa ekonomiska dimensioner och huvudkontona och andra ekonomiska dimensioner, och även hur transaktioner kan registreras. Dessa användardefinierade regler är kallas kontostrukturer och avancerade regler.

Kontoplanen är en strukturerad lista över en juridisk persons huvudbokskonton. Listan används för att förbereda ekonomiska rapporter för myndigheter och ägare. Kontona grupperas först i kontotyper och sedan i större kategorier. På den allmännaste nivån grupperas kontona som kostnader och intäkter (rörelsekonton) samt tillgångar och skulder (balanskonton).

En kontoplan kan delas och användas av alla juridiska personer i organisationen. Kontoplanen som används av en juridisk person definieras på sidan **Redovisning**.

Här är några av faktorerna du måste ta hänsyn till när du lägger upp kontoplanen för organisationen:

- Rapporteringskraven i det land eller den region där organisationen har sin bas
- Rapporteringskraven för en juridisk person
- Specificeringsgraden som behövs, både för externa organisationer och för din organisation

Du skapar kontoplanen på sidan **Kontoplan**. Du kan skapa huvudkonton från sidan **Kontoplan** eller **Huvudkonton**. I dina huvudkonton ska inte användas specialtecken som används som kontoplanavgränsare. Annars kan det uppstå instabilitet eller du kanske alltid måste använda sökningar eller dialogrutan när du anger kombinationer av konton och dimensioner. Mer information finns i [Skapa ett huvudkonto](tasks/create-main-account.md).

> [!NOTE]
> I Dynamics 365 for Finance and Operations version 8.0 (april 2018), kan du ändra kontoplansavgränsare från sidan **Allmänna redovisningsparametrar**.

Det är en bra idé att länka huvudkontona till huvudkontokategorier, så att du kan använda ekonomiska standardrapporterna utan att behöva göra några ändringar. Därför kan du snabbt och enkelt designa och underhålla rapporter.

Du skapar kontostrukturer på sidan **Konfigurera kontostrukturer**. Kontostrukturer definierar giltiga kombinationer. Dessa kombinationer, tillsammans med huvudkontona, bildar en kontoplan. Mer information finns i [Skapa en kontostruktur](tasks/create-account-structures.md).

**Juridisk person åsidosätter**

Alla huvudkonton är inte giltiga för alla juridiska personer, och några huvudkonton kanske bara är relevanta under en viss period. I detta scenario kan du använda avsnittet **Juridisk person åsidosätter** för att identifiera vilka företag som huvudkontot ska uppskjutas för, vem ägaren är och tidsperioden dimensionen är aktiv i. Åsidosättandet på den delade nivån kan inte vara restriktivare än åsidosättandet på nivån för juridisk person.

Mer information finns i följande avsnitt:

- [Ekonomiska dimensioner](financial-dimensions.md)
- [Skapa och tilldela avancerade regelstrukturer](tasks/create-assign-advanced-rule-structures.md)
