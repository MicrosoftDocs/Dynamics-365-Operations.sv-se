---
title: Uppdatera överföringsbudgeten efter reduceringar av inköpsorder och fakturor
description: I den här artikeln beskrivs hur du kontrollerar vad som händer med överföringsbudgeten när inköpsorder annulleras eller minskas och när fakturor reduceras.
author: TaylorVH
ms.date: ''
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: TaylorVH
ms.search.validFrom: 2022-02-01
ms.dyn365.ops.version: Version 1611
ms.search.form: LedgerFund
ms.openlocfilehash: 790f1e770fd77d5209436c1c89e0f6125aac150f
ms.sourcegitcommit: 1a7729a6ce4f3fcf68bdc4cfdad746a5553da3c5
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/22/2022
ms.locfileid: "9573057"
---
# <a name="update-the-carry-forward-budget-after-reductions-in-purchase-orders-and-invoices"></a>Uppdatera överföringsbudgeten efter reduceringar av inköpsorder och fakturor

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

I den här artikeln beskrivs hur du kontrollerar vad som händer med överföringsbudgeten när inköpsorder annulleras eller minskas och när fakturor reduceras.

Mer information om hur inköpsorder bearbetas vid årets slut finns i [Bearbeta inköpsorder vid årets slut](/dynamicsax-2012/appuser-itpro/process-purchase-orders-at-year-end).

## <a name="turn-carry-forward-budget-reductions-for-invoice-variances-on-or-off"></a>Aktivera och inaktivera budgetreduceringar för fakturaavvikelser

Systemet kan alltid uppdatera överföringsbudgeten när en inköpsorder annulleras eller reduceras. Men om du vill uppdatera överföringsbudgeten när en faktura reduceras måste du aktivera funktionen *Minska överförd budget när en faktura mot en inköpsorder reduceras med en avvikelse*. Administratörer kan aktivera eller inaktivera den här funktionen genom att söka efter den på arbetsytan **[Funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)**.

## <a name="purchase-order-reductions-and-cancellations"></a>Inköpsorderreduceringar och annulleringar

Oavsett om funktionen *Minska överförd budget när en faktura mot en inköpsorder reduceras med en avvikelse* är aktiverad uppdateras budgeten för överföringen när en kvalificerad inköpsorder annulleras eller minskas. Du kan ställa in att respektive redovisningsfond ska svara på något av följande sätt:

- Behåll den framåtriktade budgeten så som den skapades.
- Justera överföringsbudgeten automatiskt för att ta bort det annullerade eller reducerade beloppet.

Endast inköpsorderrader som har distributioner som inkluderar en fond är tillgängliga för automatisk budgetjustering. Den automatiska budgetjusteringen sker när inköpsordern slutförs eller när en reducering av inköpsordern bekräftas.

## <a name="invoice-reductions"></a>Fakturareduceringar

När funktionen *Minska överförd budget när en faktura mot en inköpsorder reduceras med en avvikelse* är aktiverat kan du ange om varje fond ska minska överföringsbudgeten när en faktura reduceras, utöver när en inköpsorder reduceras eller annulleras. Fakturan måste vara för en inköpsorder som har en framåtbudget. Reduceringar inkluderar prisavvikelser, avgiftsavvikelser och momsavvikelser. När en inköpsorder för överföring minskas under faktureringen, skapas en avvikelse. När fakturan bokförs minskas inköpsorderinteckningen med beloppet för avvikelsen. Funktionen skapar också den automatiska budgetjusteringen för avvikelsebeloppet.

När funktionen *Minska överförd budget när en faktura mot en inköpsorder reduceras med en avvikelse* är inaktiverad, reduceras inte budgeten för överföring i detta scenario. Därför lämnas resterande överföringsbudget för avvikelsebeloppet efter.

## <a name="configure-the-carry-forward-budget-options-for-each-fund"></a>Konfigurera alternativ för överförd budget för varje fond

Följ de här stegen för varje redovisningsfond som ska kunna minska överföringsbudgeten när en inköpsorder eller faktura reduceras.

1. Gå till **Redovisning \> Kontoplan \> Fonder \> Fonder**.
1. Välj den fond du vill skapa.
1. Under **Årsslutsprocess för inköpsorder**, se till att alternativet **Åsidosätt valt alternativ för årsbokslut** anges till *Ja*.
1. Under **Status för överförd budget** ska du ställa in fältet **Återinför budgeten när en överförd inköpsorder annulleras eller minskas** efter behov. Inställningarna har lite olika effekter, beroende på om funktionen *Minska överförd budget när en faktura mot en inköpsorder reduceras med en avvikelse* aktiveras i systemet.

    - När funktionen är inaktiverad ingår det bara i systemet att annullera eller reducerade inköpsorder. Alternativinställningarna fungerar på följande sätt:

        - *Nej* – En budgetregisterpost skapas för resten av saldot av inköpsorder som har annullerats eller reducerats.
        - *Ja* – Systemet tillåter att inköpsorder annulleras eller minskas, men skapar ingen budgetregisterpost. Den överförda budgeten förblir tillgänglig för förbrukning i andra dokument.

    - När funktionen är påslagen reagerar systemet både på fakturaavvikelser och på annullerade eller minskade inköpsorder. Alternativinställningarna fungerar på följande sätt:

        - *Nej* – För fakturaavvikelser skapar systemet en budgetregisterpost mot inköpsordern för avvikelsereduceringsbeloppet. För annullerade eller reducerade inköpsorder har den här inställningen samma effekt när funktionen är inaktiverad.
        - *Ja* – För fakturaavvikelser tillåter systemet en fakturareducering men ingen budgetregisterpost skapas. Den överförda budgeten förblir tillgänglig för förbrukning i andra dokument. För annullerade eller reducerade inköpsorder har den här inställningen samma effekt när funktionen är inaktiverad.

## <a name="additional-resources"></a>Ytterligare resurser

- [Bearbeta inköpsorder vid Årssluts](/dynamicsax-2012/appuser-itpro/process-purchase-orders-at-year-end)
- [Underhåll huvudbudgetreservationer](general-budget-reservation-tasks.md)
- [Medel i offentlig sektor](funds-public-sector.md)
- [Ställa in en fond i offentliga sektorn](tasks/set-up-fund-public-sector.md)
