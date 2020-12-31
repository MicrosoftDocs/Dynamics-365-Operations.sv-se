---
title: Skapa en budget av transaktionskonton och totalkonton
description: Det här avsnittet innehåller en översikt över processen för att skapa budgetar baserat på saldokonton. Det innehåller även information om hur du aktiverar budgetkontroll för saldokonton, om budgetkontroll krävs.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BudgetControlConfiguration, BudgetPlanGenerate
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 13051
ms.assetid: fb1bb2d3-445c-402f-a9a3-aa6503eed78e
ms.search.region: Global
ms.author: sigitac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f60963bee790737c85161dff03278df0572e3abc
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "4448129"
---
# <a name="create-a-budget-from-transaction-accounts-and-total-accounts"></a>Skapa en budget av transaktionskonton och totalkonton

[!include [banner](../includes/banner.md)]

Det här avsnittet innehåller en översikt över processen för att skapa budgetar baserat på saldokonton. Det innehåller även information om hur du aktiverar budgetkontroll för saldokonton, om budgetkontroll krävs.

Dokument för båda budgetplanposter och budgetregisterposter tillåter budgetering på huvudkonton som har typen **Summa**. Utfall kan bara bokföras på transaktionshuvudkonton. 

För den periodiska processen **Generera budgetplan från huvudbok** på fliken **Källa** kan du ange huvudkontotypen **Summa** som villkor. I det här fallet kommer varje summahuvudkonto inkluderas i målbudgetplanen, och beloppet är lika med det totala beloppet i intervallet för valda huvudkonton. 

Du kan aktivera budgetkontroll för huvudkonton med typen **Summa**. Den här funktionen stöds genom användning av budgetgrupper. För varje summahuvudkonto måste budgeten som ska kontrolleras för en budgetgrupp skapas på sidan **Budgetkontrollkonfiguration**. De kriterier som du anger måste innehålla summahuvudkontot och kontointervallet. För att påskynda processen med att skapa budgetgrupper kan du använda datatabellen för budgetkontrollgrupper. 

När en budget används i rapporteringen, till exempel ett bokslut, består budgetsumman för saldokontot av följande belopp:

-   Budgetarna som skapar av varje transaktionsredovisning i intervallet för saldokontot.
-   Budgetbeloppet som anges direkt på saldokontot.

Därför kan du skapa separata budgetar för de viktigaste transaktionskontona i intervallet för saldokontot och sedan lägga till det tillgängliga budgetbeloppet på saldokontot.



