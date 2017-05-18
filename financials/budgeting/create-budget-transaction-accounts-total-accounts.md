---
title: Skapa en budget av transaktionskonton och totalkonton
description: "Det här avsnittet innehåller en översikt över processen för att skapa budgetar baserat på saldokonton. Det innehåller även information om hur du aktiverar budgetkontroll för saldokonton, om budgetkontroll krävs."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: BudgetControlConfiguration, BudgetPlanGenerate
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 13051
ms.assetid: fb1bb2d3-445c-402f-a9a3-aa6503eed78e
ms.search.region: Global
ms.author: sigitac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: fd3392eba3a394bd4b92112093c1f1f9b894426d
ms.openlocfilehash: ea1f8230c360a196f505e0f9d0fb178b43a9072f
ms.contentlocale: sv-se
ms.lasthandoff: 04/25/2017


---

# <a name="create-a-budget-from-transaction-accounts-and-total-accounts"></a>Skapa en budget av transaktionskonton och totalkonton

[!include[banner](../includes/banner.md)]


Det här avsnittet innehåller en översikt över processen för att skapa budgetar baserat på saldokonton. Det innehåller även information om hur du aktiverar budgetkontroll för saldokonton, om budgetkontroll krävs.

Dokument för båda budgetplanposter och budgetregisterposter tillåter budgetering på huvudkonton som har typen **Summa**. Utfall kan bara bokföras på transaktionshuvudkonton. 

För den periodiska processen **Generera budgetplan från huvudbok** på fliken **Källa** kan du ange huvudkontotypen **Summa** som villkor. I det här fallet kommer varje summahuvudkonto inkluderas i målbudgetplanen, och beloppet är lika med det totala beloppet i intervallet för valda huvudkonton. 

Du kan aktivera budgetkontroll för huvudkonton med typen **Summa**. Den här funktionen stöds genom användning av budgetgrupper. För varje summahuvudkonto måste budgeten som ska kontrolleras för en budgetgrupp skapas på sidan **Budgetkontrollkonfiguration**. De kriterier som du anger måste innehålla summahuvudkontot och kontointervallet. För att påskynda processen med att skapa budgetgrupper kan du använda datatabellen för budgetkontrollgrupper. 

När en budget används i rapporteringen, till exempel ett bokslut, består budgetsumman för saldokontot av följande belopp:

-   Budgetarna som skapar av varje transaktionsredovisning i intervallet för saldokontot.
-   Budgetbeloppet som anges direkt på saldokontot.

Därför kan du skapa separata budgetar för de viktigaste transaktionskontona i intervallet för saldokontot och sedan lägga till det tillgängliga budgetbeloppet på saldokontot.




