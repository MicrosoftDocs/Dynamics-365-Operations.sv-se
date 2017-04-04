---
title: "Ställ in matchningsregler för bankavstämning"
description: "Det här avsnittet innehåller en beskrivning av hur du kan ställa in matchningsregler för avstämning och matchningsregeluppsättningar för avstämning som hjälp vid bankavstämningsprocessen. Avstämningsmatchningsregler är en uppsättning kriterier som används för att filtrera bankutdragsrader och bankdokumentrader under avstämningsprocessen."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: BankReconciliationMatchRule, BankReconciliationMatchRuleSet
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 12971
ms.assetid: b5073f83-31dc-404f-af42-3fd84a02a7c6
ms.search.region: Global
ms.author: leguo
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 3b16ef53f9fb57a6663db0be1f7e0a57471db2fb
ms.openlocfilehash: e4c07a6afb90535c57f372d5b850919b5b34aaa4
ms.lasthandoff: 03/31/2017


---

# <a name="set-up-bank-reconciliation-matching-rules"></a>Ställ in matchningsregler för bankavstämning

Det här avsnittet innehåller en beskrivning av hur du kan ställa in matchningsregler för avstämning och matchningsregeluppsättningar för avstämning som hjälp vid bankavstämningsprocessen. Avstämningsmatchningsregler är en uppsättning kriterier som används för att filtrera bankutdragsrader och bankdokumentrader under avstämningsprocessen.

Du kan ställa in avstämningsmatchningsregler och avstämningsmatchningsregeluppsättningar som hjälp vid bankavstämningsprocessen. Matchningsregel för bankavstämning är en uppsättning villkor som används för att filtrera bankutdragsrader och Microsoft Dynamics 365 för operationer bank transaktionsrader under avstämningsprocessen. Använd sidan **Matchningsregler för avstämning** för att ställa in avstämningsmatchningsreglerna. Du kan ställa in fler än en matchningsregel och sedan skapa en avstämningsmatchningsregel som visas på sidan **Matchningsregeluppsättningar för avstämning**. 

> [!NOTE] 
> Bank-avstämning matchningsregler används om du stämmer av en elektronisk bankutdrag med avancerad bankavstämning. 

På sidan **Matchningsregler för avstämning** kan du välja vilka åtgärder, och urvalskriterier, som ska användas när matchningsregeln körs. I den **åtgärder** grupp, markera den åtgärd som ska utföras när matchningsregeln körs under avstämningsprocessen.  

> [!NOTE] 
> Alternativet du väljer bestämmer vilka fält som visas.

|                                    |                                                                                                                                                                                                                                                                                                               |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
|------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Åtgärd**                         |                                                                                                                                                                                                                                                                                                               | **Tillgängliga urvalskriterier när åtgärd är markerad**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| **Matcha med bankdokument**       | Skapa villkor för att ange hur bankdokument och bankutdragsrader matchas när matchningsregeln körs från sidan **Bankavstämningskalkylblad**. Transaktionsraderna markeras i enlighet med de kriterier som ställts in på snabbflikarna.                                | **Steg 1: Definiera matchningsregeln** – Välj criterias för att ange vilka bankutdrag ska matchas med Dynamics 365 för operationer banktransaktioner. **Steg 2 (valfritt): Välj utdragsrader för att köra matchningsregler mot:** Använd ett filter på utdragsraden att köra reglerna mot.                                                                                                                                                                                                                                                                                                               |
| **Rensa alla återföringsutdragsrader** | Skapa villkor för att ange hur återföringsutdragrader ska tas bort från sidan **Bankavstämningskalkylblad** när matchningsregeln körs. Det här alternativet används när ett bankfel gör att två bankutdragsrader anges i det importerade bankutdraget, och raderna måste vara avstämda. | **Steg 1**:** Sök efter återföringsutdragsrader **– Lägg till urvalskriterier i valda återföringsbankutdragrader. Om du exempelvis bara vill välja checkar väljer du **Banktransaktionskod**i fältet, sedan plustecknet i fältet **Operator** och anger sedan **Checkar** i värdefältet. **Steg 2: Sök efter ursprungliga utdragsrader** – Du kan lägga till urvalskriterier för att matcha bankdokumentrader mot bankutdragsrader. ** Steg 3: Hitta Dynamics 365 operationer banktransaktioner ** – du kan lägga till urvalskriterierna så att de matchar Dynamics 365 för operationer bank transaktioner bankutdragsrader. |
| **Mark new transactions**          | Skapa villkor för att ange hur nya transaktioner ska markeras på sidan **Bankavstämningskalkylblad** när matchningsregeln körs.                                                                                                                                                                 | **Steg 1: Sök efter utdragsrader **– Lägg till urvalsfält för att ange vilka bankutdragrader som ska väljas från sidan **Bankavstämningskalkylblad**. ** Steg 2: Sök efter Dynamics 365 för operationer banktransaktioner ** – du kan lägga till urvalskriterier för att söka efter rader som banken. Om inget bankdokument finns markeras en utdragsrad som en ny transaktion.                                                                                                                                                                                                                                             |

 




