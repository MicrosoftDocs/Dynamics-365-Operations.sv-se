---
title: Avancerad inställningsprocess för bankavstämning
description: Med hjälp av Avancerad bankavstämning kan du importera elektroniska bankutdrag och utföra en automatiskt avstämning mot banktransaktioner i Microsoft Dynamics 365 Finance. Den här artikeln innehåller en beskrivning av hur du ställer in processer för avstämning.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BankReconciliationMatchRule, BankReconciliationMatchRuleSet
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 98303
ms.assetid: ae071f04-f038-4b17-812d-0a241ed15521
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 405af4e3e122953bbfa74e7e91d2feef8f068708
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/06/2019
ms.locfileid: "2772638"
---
# <a name="advanced-bank-reconciliation-setup-process"></a>Avancerad inställningsprocess för bankavstämning

[!include [banner](../includes/banner.md)]

Med hjälp av Avancerad bankavstämning kan du importera elektroniska bankutdrag och utföra en automatiskt avstämning mot banktransaktioner i Microsoft Dynamics 365 Finance. Den här artikeln innehåller en beskrivning av hur du ställer in processer för avstämning.  

Det finns ett antal delar som måste ställas in innan du använder funktionen för avancerad bankavstämning. Mer information om hur du ställer in import av bankutdrag finns i [Ställa in importprocessen för avancerad bankavstämning](set-up-advanced-bank-reconciliation-import-process.md).  Kraven för konfigurering av avstämningsprocessen beskrivs nedan.

## <a name="transaction-codes"></a>Transaktionskoder
Transaktionskoder kan användas som en del av matchningsreglerna för bankavstämning. Transaktionskoder hjälper till att matcha endast samma transaktionstyper mellan Finance och bankutdraget. För att kunna utföra den här typen av matchning, måste du först definiera de transaktionstyper som används för banktransaktioner från Finance och sedan mappa dessa typer med de transaktionskoder som används av banken. Transaktionstyper för banktransaktioner definieras på sidan **Banktransaktionstyp**. Det är också här som du definierar det huvudkonto som ska användas för bokföringar associerade med transaktionstypen. 

När dina banktransaktionskoder har definierats, kan du mappa dessa till de transaktionskoder som används på dina elektroniska bankutdrag. Denna mappningsprocess sker med hjälp av sidan **Mappning av transaktionskoder**. Mappning av transaktionskoder slutförs separat för varje bankkonto.

## <a name="matching-rules-and-matching-rule-sets"></a>Matchningsregler och matchningsregeluppsättningar
Med matchande regler kan du definiera kriterier för automatisk avstämning mellan banktransaktioner i Finance och bankutdragstransaktioner. Du skapar matchande regler på sidan **Matchningsregler för avstämning**. Mer information finns i [Ställa in matchningsregler för bankavstämning](set-up-bank-reconciliation-matching-rules.md). 

En matchningsregeluppsättning används för att definiera en uppsättning matchningsregler som körs i sekvens under bankutdragsavstämningsprocessen.  Matchande regeluppsättningar konfigureras på sidan **Avstämning av matchande regeluppsättningar**.

## <a name="cash-and-bank-management-parameters"></a>Parametrar för kassa- och bankhantering
Det finns ett antal parametrar som är specifika för avancerad bankavstämningsprocess på sidan **Hanteringsparametrar för kassa och bank**.  **Visa belopp för utdragsrad i debet/kredit** ändrar visningen av belopp på sidan **Bankutdrag**. Om det här alternativet är markerat visas transaktionsbeloppen för bankutdrag i separata debet- och kreditkolumner. Om det inte har markerats kommer transaktionsbeloppen för bankutdrag att visas i en enda beloppskolumn med lämpligt förtecken. 

De verifieringsalternativ som angetts på parametersidan åsidosätter valen för matchningsregler. Exempelvis kan du inte manuellt eller automatiskt matcha dokument utanför den datumskillnad som angetts på parametersidan. Om alternativet **Validera mappning av transaktionstyp** har markerats måste transaktionstyperna dessutom mappas mellan Finance banktransaktionen och bankutdragstransaktionen för att transaktionerna ska kunna matchas manuellt eller automatiskt. 

Du måste också konfigurera nödvändiga nummerserier på sidan **Parametrar för kassa- och bankhantering**.  På fliken **Nummerserier** anger du nummerseriekoder för hämtningens **ID, utdrags-ID, avstämnings-ID och bankavstämningens** referenser.

## <a name="bank-account-reconciliation-options"></a>Alternativ för bankkontoavstämning
Du måste först aktivera avancerad bankavstämning för bankkontot. Ett antal ytterligare alternativ är tillgängliga på sidan **Bankkonto** när funktionen för avancerad bankavstämning har aktiverats. 

Funktionen **Använd bankutdrag som en bekräftelse på elektronisk betalning** integrerar funktionen för bankavstämning med statusen för elektronisk betalning. När detta aktiveras skapas ett bankdokument automatiskt för elektronisk betalningsstatus med värdet **Skickad**. Dessutom uppdateras statusen för en elektronisk betalning från **Skickad** till **Mottagen** när betalningen matchas, stäms av och bokförs. 

Fältet **Bankkontots namn i rapporter** är det namn som används för bankkontot på dina elektroniska bankutdrag. Detta namn används när det ska fastställas vilka transaktioner som ska importeras för ett bankkonto från ett utdrag som kan innehålla information om flera olika bankkonton. 

Alternativet för **Avstämning efter import** kommer automatiskt att validera bankutdraget, skapa en ny bankavstämning och ett nytt kalkylblad, samt köra standarduppsättningen matchningsregler. Den här funktionen automatiserar processen fram till de transaktioner som måste stämmas av manuellt. Inställningen för bankkontot återgår till standardvärdet när du importerar.



