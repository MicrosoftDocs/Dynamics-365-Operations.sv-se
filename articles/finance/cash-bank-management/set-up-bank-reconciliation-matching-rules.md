---
title: Ställa in matchningsregler för bankavstämning
description: Det här ämnet innehåller en beskrivning av hur du kan ställa in matchningsregler för avstämning och matchningsregeluppsättningar för avstämning som hjälp vid bankavstämningsprocessen. Avstämningsmatchningsregler är en uppsättning kriterier som används för att filtrera bankutdragsrader och bankdokumentrader under avstämningsprocessen.
author: angelad116
ms.date: 08/24/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BankReconciliationMatchRule, BankReconciliationMatchRuleSet
audience: Application User
ms.reviewer: kfend
ms.custom: 12971
ms.assetid: b5073f83-31dc-404f-af42-3fd84a02a7c6
ms.search.region: Global
ms.author: angelading
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ed8572eca14beb8a0e3c382f0f328cc6d118491c
ms.sourcegitcommit: 0b7a034e644f4d93fe55c7baca5a3f89dbe56898
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/14/2022
ms.locfileid: "9151325"
---
# <a name="set-up-bank-reconciliation-matching-rules"></a>Ställa in matchningsregler för bankavstämning

[!include [banner](../includes/banner.md)]

Det här ämnet innehåller en beskrivning av hur du kan ställa in matchningsregler för avstämning och matchningsregeluppsättningar för avstämning som hjälp vid bankavstämningsprocessen. Avstämningsmatchningsregler är en uppsättning kriterier som används för att filtrera bankutdragsrader och bankdokumentrader under avstämningsprocessen.

Du kan ställa in avstämningsmatchningsregler och avstämningsmatchningsregeluppsättningar som hjälp vid bankavstämningsprocessen. Avstämningsmatchningsregler är en uppsättning kriterier som används för att filtrera bankutdragsrader och Dynamics 365 Finance-banktransaktionsrader under avstämningsprocessen. Använd sidan **Matchningsregler för avstämning** för att ställa in avstämningsmatchningsreglerna. Du kan ställa in fler än en matchningsregel och sedan skapa en avstämningsmatchningsregel som visas på sidan **Matchningsregeluppsättningar för avstämning**. 

> [!NOTE] 
> Bankavstämningsmatchningsregler används om du stämmer av ett elektroniskt bankutdrag med avancerad bankavstämning. 

På sidan **Matchningsregler för avstämning** kan du välja vilka åtgärder, och urvalskriterier, som ska användas när matchningsregeln körs. I fältgruppen **Åtgärder** väljer du den åtgärd som ska utföras när matchningsregeln körs under avstämningsprocessen.  

Som standard matchar matchningsreglerna det första bankdokumentet som uppfyller kriterierna för matchningsregeln. Om flera bankdokument uppfyller regelkriteriet kan parametern som kräver manuell matchning vara aktiverad genom att gå till **kontant- och bankhantering > inställningar > kassa- och bankhanteringsparametrar > bankavstämning > kräver manuell matchning när avancerade matchningsregler för bankavstämning söker efter flera dokument som matchar beloppet**.

> [!NOTE] 
> Alternativet du väljer bestämmer vilka fält som visas.

| Åtgärd | beskrivning   | Tillgängliga urvalskriterier när åtgärd är markerad     |
|--------|---------------|----------------------------------------------------------|
| **Matcha med bankdokument**       | Skapa villkor för att ange hur bankdokument och bankutdragsrader matchas när matchningsregeln körs från sidan **Bankavstämningskalkylblad**. Transaktionsraderna markeras i enlighet med de kriterier som ställts in på snabbflikarna.                                | **Steg 1: Definiera matchningsregeln**– Välj villkor som anger vilka bankutdrag som ska matchas med Finance-banktransaktionerna. **Steg 2 (valfritt): Välj utdragsrader för att köra matchningsregler mot:** Använd ett filter på utdragsraden att köra reglerna mot.                                                                                                                                                                                                                                                                                                               |
| **Rensa alla återföringsutdragsrader** | Skapa villkor för att ange hur återföringsutdragrader ska tas bort från sidan **Bankavstämningskalkylblad** när matchningsregeln körs. Det här alternativet används när ett bankfel gör att två bankutdragsrader anges i det importerade bankutdraget, och raderna måste vara avstämda. | **Steg 1**:**Sök efter återföringsutdragsrader**– Lägg till urvalskriterier i valda återföringsbankutdragrader. Om du exempelvis bara vill välja checkar väljer du **Banktransaktionskod** i fältet, sedan plustecknet i fältet **Operatör** och anger sedan **Checkar** i värdefältet. **Steg 2: Sök efter ursprungliga utdragsrader** – Du kan lägga till urvalskriterier för att matcha bankdokumentrader mot bankutdragsrader. **Steg 3: Sök efter Finance-banktransaktioner** – Du kan lägga till urvalskriterier för att matcha Finance-banktransaktioner mot bankutdragsrader. |
| **Markera nya transaktioner**          | Skapa villkor för att ange hur nya transaktioner ska markeras på sidan **Bankavstämningskalkylblad** när matchningsregeln körs.                                                                                                                                                                 | **Steg 1: Sök efter utdragsrader**– Lägg till urvalsfält för att ange vilka bankutdragrader som ska väljas från sidan **Bankavstämningskalkylblad**. **Steg 2: Söka efter Ekonomi och drift** – Du kan lägga till urvalskriterier för att söka efter bankdokumentrader. Om inget bankdokument finns markeras en utdragsrad som en ny transaktion.                                                                                                                                                                                                                                             |


[!INCLUDE[footer-include](../../includes/footer-banner.md)]

