---
title: Konfigurera namn för leasingjournal
description: I det här ämnet beskrivs hur du definierar namn på leasingjournaler. Namn på leasingjournaler anger de journaler som poster som kommer från Leasing av tillgångar bokförs på.
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
ms.openlocfilehash: e8b1b908dfd6d1d6072b6efa83f13ae5784c85c1
ms.sourcegitcommit: aeee39c01d3f93a6dfcf2013965fa975a740596a
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/28/2020
ms.locfileid: "4448198"
---
# <a name="set-up-lease-journal-names"></a>Konfigurera namn för leasingjournal

[!include [banner](../includes/banner.md)]

Namn på leasingjournaler anger de journaler som transaktioner i Leasing av tillgångar bokförs till. Endast journalnamn som tilldelas journaltypen **Leasing av tillgångar** visas i fälten **Första redovisningstillfälle** och **Namn på månatlig journal** på sidan **Parametrar för tillgångsleasing**. Endast journaltypen **Registrering av leverantörsfaktura** kan tilldelas fältet **Namn på fakturajournal**.

Konfigurera namn på leasingjournaler genom att följa stegen nedan.

1. Gå till **Leasing av tillgångar \> Konfigurera \> Parametrar för tillgångsleasing**.
2. Välj en journal på fliken **Allmänt** i fältet **Journalnamn för första redovisningstillfälle**. Alla journalposter för första redovisningstillfälle bokförs med det här journalnamnet.
3. Välj en journal i fältet **Namn på fakturajournal**. Om alternativet **Betala till leverantör** är inställt på **Ja** för leasingboken bokförs fakturor för leasing och utgiftsbetalning till det här journalnamnet.
4. Välj en journal i fältet **Namn för leasingjournal**. Alla avskrivnings-, ränte-och omklassificeringstransaktioner för kortfristiga poster bokförs till det här journalnamnet. Om alternativet **Betala till leverantör** är inställt på **Nej** för leasingboken bokförs poster för leasingbetalningar och utgiftsbetalning också till det här journalnamnet.
