---
title: "Översikt över avancerad bankavstämning"
description: "Avancerad bankavstämning kan du importera elektroniska bankutdrag och synkronisera med banktransaktioner i Microsoft Dynamics 365 för operationer.  Den här artikeln innehåller en beskrivning av hur du ställer in processer för avstämning."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 98303
ms.assetid: ae071f04-f038-4b17-812d-0a241ed15521
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 3b16ef53f9fb57a6663db0be1f7e0a57471db2fb
ms.openlocfilehash: c2fc9e858f61d7d0122393bbf306ba64ac3659b8
ms.lasthandoff: 03/31/2017


---

# <a name="advanced-bank-reconciliation-overview"></a>Översikt över avancerad bankavstämning

Avancerad bankavstämning kan du importera elektroniska bankutdrag och synkronisera med banktransaktioner i Microsoft Dynamics 365 för operationer.  Den här artikeln innehåller en beskrivning av hur du ställer in processer för avstämning.  

Det finns ett antal delar som måste ställas in innan du använder funktionen avancerad avstämning. Mer information om hur du ställer in bank satsen import finns [ställa in importen bank utdraget](set-up-advanced-bank-reconciliation-import-process.md).  Krav för konfigurering avstämningsprocessen beskrivs nedan.

## <a name="transaction-codes"></a>Transaktionskoder
Transaktionskoder kan användas som en del av avstämningen matchningsregler.  Transaktionskoder hjälper till att matcha endast de samma transaktionstyperna mellan Dynamics 365 för operationer och bankutdraget.  För att kunna utföra den här typen av matchning måste du först definiera transaktionstyper används för banktransaktioner från Dynamics 365 för operationer och sedan dessa typer motsvarar transaktionskoder används av banken.  Transaktionstyper för Dynamics 365 för banktransaktioner operationer definieras i den **banktransaktionstyp** sida.  Dessutom är det här du definierar huvudkontot som ska användas för bokföring som associeras med transaktionen. 

När Dynamics 365 om transaktionskoder operationer bank har definierats kan mappa du sedan dessa till transaktionskoder som används i din elektroniska bankutdrag.  Proceduren mappningen sker med hjälp av den **Transaktionskodsmappning** sida.  Mappning av transaktion slutförs separat för varje bankkonto.

## <a name="matching-rules-and-matching-rule-sets"></a>Matchningsregler och matchningsregeluppsättningar
Matchande regler kan du definiera kriterier för automatisk avstämning mellan Dynamics 365 för operationer banktransaktioner och bankkontotransaktioner.  Av matchande regler görs på **avstämning matchningsregler** sida.  Mer information finns i [skapa matchningsregler bankavstämning](set-up-bank-reconciliation-matching-rules.md). 

Matchande regeluppsättningar för att definiera en grupp med matchande regler som körs i ordning under bankkontoavstämningsprocessen.  Matchande regeluppsättningar har konfigurerats på den **avstämning matchningsregeluppsättningar** sida.

## <a name="cash-and-bank-management-parameters"></a>Parametrar för kassa- och bankhantering
Ett antal parametrar är specifika för avancerad avstämningsprocessen i den **kontant- och bankhanteringsparametrar** sida.  Den **Visa radbeloppet i debet/kredit** ändras visningen av beloppen i den **bankutdraget** sida.  Om det här alternativet är markerat visas transaktionsbeloppen bank utdrag i separata debet och kredit kolumner.  Överför inte visas transaktionsbeloppen bank utdrag i en kolumn för enstaka belopp med rätt tecken. 

Verifieringsalternativ på sidan parametrar åsidosätta val på matchningsregler.  Exempelvis kan du inte manuellt eller matcha automatiskt dokument utanför datumskillnaden på sidan parametrar.  Även om kan **Validera mappning av transaktionstyp för** är markerad transaktionstyperna måste mappas mellan Dynamics 365 för banktransaktionen operationer och bankkontoutdragstransaktion för att transaktionerna ska manuellt eller automatiskt matchas. 

Du måste också konfigurera nödvändiga nummerserier på de **kontant- och bankhanteringsparametrar** sida.  I den **nummerserier** fliken ange nummerseriekoder hämtningen **ID, utdrags-ID, Stäm av ID och Bank-avstämning** referenser.

## <a name="bank-account-reconciliation-options"></a>Alternativ för bankkontoavstämning
Du måste först aktivera avancerad bankavstämning för bankkontot.  Ytterligare alternativ är tillgängliga i den **bankkonto** sidan när funktionen avancerad avstämning ska aktiveras. 

**Använd bankutdrag som en bekräftelse på elektronisk betalning** funktionen integreras funktionerna bank avstämning med statusen elektronisk betalning.  När detta aktiveras ett bankdokument att skapas automatiskt för elektronisk betalningsstatus har värdet **skickad**.  Dessutom uppdateras statusen för en elektronisk betalning från **skickad** till **mottagna** när betalningen matchas avstämd och bokförts. 

Den **bankkonto namn i rapporter** är det namn som används för bankkontot på din elektroniska bankutdrag.  Det här namnet används när det fastställs vilka transaktioner ska importeras för ett bankkonto från ett uttryck som kan innehålla information för flera bankkonton. 

Alternativet för **avstämning efter importen** kommer automatiskt Validera bankkonto bankutdraget, skapa en ny bankkontoavstämning och kalkylblad och kör matchningsregeluppsättning standard.  Den här funktionen automatiserar processen tills transaktionerna måste matchas manuellt.  Om bankkontot kommer standardvärdet när du importerar.


