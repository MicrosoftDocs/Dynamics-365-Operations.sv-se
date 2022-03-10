---
title: Konfigurera namn för leasingjournal
description: I det här ämnet beskrivs hur du definierar namn på leasingjournaler. Namn på leasingjournaler anger de journaler som poster som kommer från Leasing av tillgångar bokförs på.
author: moaamer
ms.date: 12/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetLeasePostingAccounts
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: b9d8136ae4f960a586b9526751fc8bf6e7675c8d
ms.sourcegitcommit: c85eac17fbfbd311288b50664f9e2bae101c1fe6
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/03/2021
ms.locfileid: "7890760"
---
# <a name="set-up-lease-journal-names"></a>Konfigurera namn för leasingjournal

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]


Namn på leasingjournaler anger de journaler som transaktioner i Leasing av tillgångar bokförs till. Endast journalnamn som tilldelas journaltypen **Leasing av tillgångar** visas i fälten **Första redovisningstillfälle** och **Namn på månatlig journal** på sidan **Parametrar för tillgångsleasing**. Endast journaltypen **Registrering av leverantörsfaktura** kan tilldelas fältet **Namn på fakturajournal**.

Systemet låser vissa ekonomiska fält från att redigeras i syfte att förhindra eventuella avvikelser mellan transaktioner och tidsplaner. Fält som är låsta inkluderar följande: **Kontro**, **Belopp**, **Ekonomiska dimensioner**, **Valuta** och **Transaktionstyp**. Du kan vidare inte lägga till eller ta bort journalpostrader från någon journalpost för tillgångsleasing eftersom detta kan orsaka avvikelser mellan tidsplanerna och transaktionerna.


Konfigurera namn på leasingjournaler genom att slutföra stegen nedan.

1. Gå till **Leasing av tillgångar \> Konfigurera \> Parametrar för tillgångsleasing**.
2. Välj en journal på fliken **Allmänt** i fältet **Journalnamn för första redovisningstillfälle**. Alla journalposter för första redovisningstillfälle bokförs med det här journalnamnet.
3. Välj en journal i fältet **Namn på fakturajournal**. Om alternativet **Betala till leverantör** är inställt på **Ja** för leasingboken bokförs fakturor för leasing och utgiftsbetalning till det här journalnamnet.
4. Välj en journal i fältet **Namn för leasingjournal**. Alla avskrivnings-, ränte-och omklassificeringstransaktioner för kortfristiga poster bokförs till det här journalnamnet. Om alternativet **Betala till leverantör** är inställt på **Nej** för leasingboken bokförs poster för leasingbetalningar och utgiftsbetalning också till det här journalnamnet.
5. Välj en journal i fältet **Journalnamn för leasingändring**. Transaktioner för leasingjustering, uppsägning och nedskrivningar bokförs i journalnamnet. Journalnamnet som du väljer ska inte ha tilldelat ett arbetsflöde eller godkännande. Om journalnamnet för leasingändring inte definieras bokförs transaktioner med leasingjustering, uppsägning och nedskrivningar i journalnamnet som har valts i fältet **Leasingjournalnamn**.  


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
