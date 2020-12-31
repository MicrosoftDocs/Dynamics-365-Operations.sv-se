---
title: Bokföringstyper för leasing
description: Det här ämnet beskriver de bokföringstyper som används för leasingtransaktioner för tillgångar.
author: moaamer
manager: Ann Beebe
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations, Retail
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: ceb4fbeb4dbf2f535e05a9d46c84169435d2803b
ms.sourcegitcommit: aeee39c01d3f93a6dfcf2013965fa975a740596a
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/28/2020
ms.locfileid: "4448217"
---
# <a name="lease-posting-types"></a>Bokföringstyper för leasing

[!include [banner](../includes/banner.md)]

Det här ämnet beskriver de bokföringstyper som används för leasingtransaktioner för tillgångar.

## <a name="lease-asset"></a>Leasingtillgång

Kontot är kopplat till tillgången med nyttjanderätt (ROU, Right Of Use). Det här kontot debiteras när en leasing först redovisas enligt de nya bokföringsstandarderna för leasing, Accounting Standards Codification Topic 842 (ASC 842) och International Financial Reporting Standard 16 (IFRS 16). För en modifierad leasing kan detta konto antingen debiteras eller krediteras, beroende på om ändringen ökar eller minskar leasingskulden.

**Exempel på journalposter:** Första redovisningstillfället<br>
**Debet:** Leasingtillgång XXX<br>
**Kredit:** Leasingskuld XXX

## <a name="lease-liability"></a>Leasingskuld

Kontot är kopplat till den leasingskuld som uppstår när betalningarna diskonteras enligt de nya IFRS 16- och ASC 842-standarderna. Det här kontot krediteras när en leasing först redovisas enligt de nya standarderna. Det debiteras för leasingbetalningar och krediteras för upplupna räntor.

**Exempel på journalposter:** Första redovisningstillfället<br>
**Debet:** Leasingtillgång XXX<br>
**Kredit:** Leasingskuld XXX

**Exempel på journalposter:** Upplupen ränta<br>
**Debet:** Räntekostnad XXX<br>
**Kredit:** Leasingskuld XXX

**Exempel på journalposter:** Leasingbetalning<br>
**Debet:** Leasingskuld XXX<br>
**Kredit:** Leverantörsskuld/leasingbetalning XXX

## <a name="short-term-lease-liability"></a>Kortfristig leasingskuld

Kontot associeras med korttidsleasingskulden när korttidsleasingens journalpost för omklassificering bokförs. Det här kontot krediteras för kortfristiga skulder från amorteringsplanen på den sista dagen i månaden. Samma belopp debiteras på den första dagen i nästa månad.

**Exempel på journalposter:** Omklassificering av kortfristig leasingskuld<br>
**Debet:** Leasingskuld XXX<br>
**Kredit:** Kortfristig leasingskuld XXX<br>
**Debet:** Kortfristig leasingskuld XXX<br>
**Kredit:** Leasingskuld XXX

## <a name="depreciation-expense"></a>Avskrivningsutgift

Kontot är kopplat till den kostnad som är relaterad till avskrivningen av ROU-tillgången enligt IFRS 16, ASC 842 och finansiella leasingavtal enligt IAS 17 och ASC 840. Det här kontot debiteras när en ROU-tillgång skrivs av varje månad.

**Exempel på journalposter:** Upplupen avskrivning<br>
**Debet:** Avskrivningskostnad XXX<br>
**Kredit:** Ackumulerad avskrivning XXX

## <a name="gainloss-on-lease-modification"></a>Vinst/förlust vid leasingändring

Kontot är kopplat till vinster eller förluster som uppstår vid ändringar av leasingavtalet. En vinst kan uppstå under en leasingändring om ändringen minskar leasingskulden med ett belopp som överstiger det bokförda värdet för ROU-tillgången.

Ett leasingavtal har till exempel ett aktuellt bokfört värde för låneskulden på 150 000 USD och ett bokfört värde på ROU-tillgången på 100 000 USD. Leasingavtalet ändras och denna ändring ger ett nytt nuvärde för de framtida lägsta leasingbetalningarna (PVFMLP) på 40 000 USD. Därför debiteras leasingskulden med 110 000 USD (150 000 USD - 40 000 USD). Eftersom ROU-tillgången bara är 100 000 USD gör minskningen på 110 000 USD att tillgången minskar under 0 (noll). Därför anger redovisningsvägledningen att resten ska bokföras på ett vinstkonto. I det här fallet är den slutliga journalposten en debitering till leasingskulden på 110 000 USD, en kredit till leasingtillgången på 100 000 USD och en kredit till vinstkontot på 10 000 USD.

**Exempel på journalposter:** Leasingändring<br>
**Debet:** Leasingskuld XXX<br>
**Kredit:** Leasingtillgång XXX<br>
**Kredit:** Vinst XXX

## <a name="accumulated-depreciation"></a>Ackumulerad avskrivning

Kontot är kopplat till motkontot för ROU-tillgången. Det här kontot krediteras när en avskrivningskostnad bokförs.

**Exempel på journalposter:** Upplupen avskrivning<br>
**Debet:** Avskrivningskostnad XXX<br>
**Kredit:** Ackumulerad avskrivning XXX

## <a name="retained-earnings"></a>Balanserade vinstmedel

Kontot är kopplat till balanserade vinstmedel. Detta konto kan antingen debiteras eller krediteras i en journalpost för en övergångsjustering genom att använda den fullständiga retrospektiva metoden eller den kumulativa "catch-up A"-metoden. Skillnaden mellan den ursprungliga ROU-tillgången och leasingskulden bokförs på balanserade vinstmedel. I sällsynta fall kan de balanserade vinstmedlen också påverkas när leasingavtalet ändras, om klassificeringen av ett leasingavtal ändras från finansiellt till operationellt för att skriva upp eller ner ROU-tillgången så att den motsvarar leasingskulden.

**Exempel på journalposter:** Övergångsjustering (metoden fullständigt retroaktivt eller kumulativt "catch-up option A")<br>
**Debet:** Leasingskuld XXX<br>
**Kredit:** Leasingtillgång XXX<br>
**Kredit:** Balanserade vinstmedel XXX

## <a name="variable-payment"></a>Variabel betalning

Kontot är kopplat till variabla leasingbetalningar som skapas genom en indexerad omvärdering enligt ASC 842, ASC 840 och IAS 17-leasingar. I betalningsplanen för leasing inkluderas variabla betalningar i kolumnen **Variabel betalning**. Det här kontot debiteras när en faktura skapas mot en betalningsplanrad som innehåller en variabel betalning.

**Exempel på journalposter:** Leasingbetalning<br>
**Debet:** Leasingskuld XXX<br>
**Debet:** Variabel betalning XXX<br>
**Kredit:** Leverantörsskuld/leasingbetalning XXX

## <a name="deferred-rent-asset-liability"></a>Uppskov av leasingavgift (skuld)

Kontot är kopplat till den uppskjutna leasingavgiften eller skulden som produceras av ett leasingavtal med uppskov av leasingavgift. Det här kontot debiteras när en faktura bokförs mot ett leasingavtal med uppskov av leasingavgift, om leasingbetalningsbeloppet är mer än periodens linjära hyreskostnad. Det krediteras om leasingbetalningen är mindre än periodens linjära hyreskostnad.

**Exempel på journalposter:** Leasingbetalning (leasing med uppskov av leasingavgift)<br>
**Debet:** Leasingkostnad XXX<br>
**Kredit:** Uppskov av leasingavgift (skuld) XXX<br>
**Kredit:** Leverantörsskuld/leasingbetalning XXX

## <a name="lease-expense"></a>Leasingkostnad

Kontot är kopplat till leasingkostnaden om leasingavtalet klassificeras som ett leasingavtal med uppskov av leasingavgift. Det här kontot debiteras när en faktura bokförs mot en leasingavtal med uppskov av leasingavgift.

**Exempel på journalposter:** Leasingbetalning (leasing med uppskov av leasingavgift)<br>
**Debet:** Leasingkostnad XXX<br>
**Kredit:** Uppskov av leasingavgift (skuld) XXX<br>
**Kredit:** Leverantörsskuld/leasingbetalning XXX

## <a name="impairment-expense"></a>Nedskrivningsutgift

Kontot motbokas när en leasing skrivs ner. Det här kontot debiteras men ROU-tillgångskontot krediteras direkt.

**Exempel på journalposter:** Leasingbetalning<br>
**Debet:** Nedskrivningsutgift XXX<br>
**Kredit:** ROU-tillgång XXX

## <a name="lease-payment"></a>Leasingbetalning

Kontot motbokas om parametern **Betala till leverantör** är inaktiverad. Det här kontot krediteras i stället för leverantörsskulden om parametern är inaktiverad.

**Exempel på journalposter:** Leasingbetalning<br>
**Debet:** Leasingskuld XXX<br>
**Kredit:** Leasingbetalning XXX

## <a name="expense-type-postings"></a>Bokföring av utgiftstyp

Det konto som väljs för varje utgiftstyp debiteras när en betalning för den utgiftstypen genereras. Kontot som anges för utgiftstypen **Försäkring** debiteras till exempel när en faktura eller en betalningsjournalpost skapas från verkställighetskostnaden för försäkringsutgift.

**Exempel på journalposter:** Försäkringsbetalning<br>
**Debet:** Konto XXX av försäkringsutgiftstyp<br>
**Kredit:** Motkonto XXX

> [!NOTE]
> Motkontot väljs på leasingnivå på raderna för betalningsplanen för verkställighetskostnad. Det här motkontot kan kopplas till leverantören eller till ett huvudbokskonto.
