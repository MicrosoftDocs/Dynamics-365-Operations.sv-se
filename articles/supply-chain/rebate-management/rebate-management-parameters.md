---
title: Parametrar för rabatthantering
description: Det här ämnet beskriver sidan Parametrar för rabatthantering. På den här sidan finns inställningar som påverkar bokföring, statusuppdateringar, nummerserier och andra beteende.
author: sherry-zheng
ms.date: 02/19/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: TAMRebateParameters
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-02-19
ms.dyn365.ops.version: Release 10.0.18
ms.openlocfilehash: dc41df33d01c3c8523afb6d8f16bfec88e0c42b8
ms.sourcegitcommit: dc4898aa32f381620c517bf89c7856e693563ace
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/17/2021
ms.locfileid: "6271039"
---
# <a name="rebate-management-parameters"></a>Parametrar för rabatthantering

[!include [banner](../includes/banner.md)]

Sidan **Parametrar för rabatthantering** används för att definiera inställningar som gäller i modulen **Rabatthantering**. Dessa inställningar som påverkar bokföring, statusuppdateringar, nummerserier och andra beteende. Inställningarna på den här sidan delas av juridiska personer och kan ändras av användare med rätt säkerhetsbehörighet.

Öppna sidan **Parametrar för rabatthantering**, gå till **Rabatthantering \> Inställningar \> Parametrar för rabatthantering**. Ställ sedan in fälten enligt beskrivningen i följande underavsnitt på varje snabbflik.

## <a name="rebate-management-tab"></a>Fliken Rabatthantering

I följande tabell beskrivs fälten som är tillgängliga på fliken **Rabatthantering** i **Parametrar för rabatthantering**.

| Fält | beskrivning |
|---|---|
| Standardstatus | Välj standardstatus för alla nya erbjudanden. För att definiera den uppsättning statusvärden som är tillgängliga för val, använd [**Rabattstatus**](rebate-statuses.md). |
| Bearbeta per dimension | Välj om provisions-, rabatt- och avskrivningstransaktioner ska bearbetas med ekonomisk dimension. När det här alternativet aktiveras används ekonomiska dimensioner för källtransaktionerna i måltransaktioner. |
| Kontrollera om någon har bokförts tidigare | <p>Välj systembeteendet om ej bokförda rabattransaktioner bearbetas mer än en gång för samma period:</p><ul><li>**Varning** – Systemet tillåter användarna att åsidosätta de ursprungliga transaktionsraderna, men en varning visas.</li><li>**Fel** – Systemet förhindrar att användarna åsidosätter de ursprungliga transaktionsraderna och ett felmeddelande visas. |
| Bokför journaler automatiskt | Välj om föreslagna journaler ska bokföras automatiskt i systemet. Dessa journaler omfattar dagliga journaler som används för avräkningar och kundavdrag, samt journaler för leverantörsskattefakturor. |
| Bokföra fritextfakturor automatiskt | Välj om föreslagna journaler ska bokföras automatiskt i fritextfakturor. Detta alternativ gäller endast fritextfakturor där betalningstypen är inställd på *Momsfaktura och kundavdrag*. |
| Referens för rabattartikelorder | Välj den rabattreferens som ska användas på försäljnings- och inköpsorder som genereras från rabattprocessen (*Ingen*, *Rabatthanteringsavtal*, *Rabatthanteringsnummer*, *Rabatt transaktionsnummer* eller *Dokumentnoteringar*). |
| Använd anspråksprocess | <p>Ställ in det här alternativet till *Ja* om du vill använda en anspråksprocess. På det här sättet kan du markera transaktioner som Rabatthantering skapar som antingen begärde eller oanade, och sedan bokföra enbart de begärde transaktionerna.</p><p>Du kan till exempel beräkna rabatter för en månads transaktioner, men kunden har lämnat två dagar oläst. I så fall skapas de olästa transaktionerna på samma gång som du kör funktionen *Process* för nästa period.</p><p>Om du ställer in detta alternativ till *Nej*, bokförs alla anspråkstransaktioner.</p> |
| Inkludera ordertypsjournal | För erbjudanden eller erbjudanderader där transaktionstypen är inställd på *Order* styr det här alternativet om en försäljningsorder av typen *Journal* ska inkluderas. Det är flexibelt om dessa ordertyper används i scenarier där en rabatt ännu inte ska gälla. |

## <a name="number-sequences-tab"></a>Fliken Nummerserie

Använd fliken **Nummerserier** på sidan **Rabatthanteringsparametrar** om du vill tilldela nummerseriekoder till olika nummerserier som Rabatthantering använder. I tabellen nedan beskrivs syftet med var och en av dessa nummerserier. Mer information om nummerserier finns i [översikten över nummerserier](../../fin-ops-core/fin-ops/organization-administration/number-sequence-overview.md) samt relaterade ämnen.

| Referens | beskrivning |
|---|---|
| Rabatthanteringsavtal | Nummerserien tilldelar ett unikt nyckelvärde till varje rabattavtal. Den här nyckeln används när erbjudanden skapas. |
| Rabatthanteringsnummer | Nummerserien tilldelar ett unikt nyckelvärde till varje rabatt. Den här nyckeln används för att identifiera rabattrelationer. |
| Transaktionsnummer för rabatt | Nummerserien tilldelar ett unikt nyckelvärde till varje rabattransaktion. Den här nyckeln används för att identifiera rabattransaktioner. |
| Momsfaktura | Nummerserien tilldelar ett unikt nyckelvärde till varje rabattfaktura. Den här nyckeln används när rabattjournaler bokförs automatiskt. |

## <a name="feature-visibility-tab"></a>Fliken Funktionssynlighet

Rabatthantering lägger till funktioner (fält och funktioner) till flera vanliga sidor i Microsoft Dynamics 365 Supply Chain Management. Dessa sidor innehåller sidor som hör till försäljningsorder och försäljningserbjudanden. Om du använder Rabatthantering måste du göra dessa funktioner synliga överallt innan du kan dra fördel av dem. Om du inte använder Rabatthantering kan du dölja funktionerna för att hålla dem utanför vägen.

På fliken **Funktionssynlighet** på sidan **Parametrar för rabatthantering** ange alternativet **Aktivera** till *Ja* för att göra funktionerna Rabatthantering var de än är tillgängliga. Ange *Nej* om du vill dölja funktionerna på gemensamma sidor utanför modulen **Rabatthantering**. Även om alternativet ställs in på *Nej*, är modulen, inklusive sidan **parametrar för rabatthantering**, förblir tillgänglig för användare som har rätt behörighet att komma åt den.
