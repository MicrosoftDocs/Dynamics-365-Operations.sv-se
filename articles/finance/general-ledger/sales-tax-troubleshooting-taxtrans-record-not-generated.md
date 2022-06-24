---
title: TaxTrans-post genereras inte
description: Detta ämne tillhandahåller felsökningsinformation som kan vara till hjälp när en TaxTrans-post inte genereras.
author: qire
ms.date: 04/13/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: kfend
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.1
ms.openlocfilehash: 402b1200e96ec8130034a03447ca071477544a88
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8846724"
---
# <a name="taxtrans-record-isnt-generated"></a>TaxTrans-post genereras inte

[!include [banner](../includes/banner.md)]

Om du väljer **Bokförd moms** för en transaktion men sidan **Bokförd moms** antingen inte anger några momsrader eller saknar en momsrad, kanske posten **TaxTrans** inte har genererats.

[![Bokförd momssida som inte innehåller några radartiklar.](./media/taxtrans-is-not-generated-Picture1.png)](./media/taxtrans-is-not-generated-Picture1.png)

Felsök det här problemet genom att följa stegen i följande avsnitt.

## <a name="check-the-sales-tax-before-you-post-the-transaction"></a>Kontrollera momsen innan du bokför transaktionen

1. Innan du bokför transaktionen väljer du, på sidan **Bokföring av faktura**, **Moms** för att kontrollera beräkningen.

    [![Knappen Moms på sidan Bokföring av faktura.](./media/taxtrans-is-not-generated-Picture2.png)](./media/taxtrans-is-not-generated-Picture2.png)

2. På sidan **Tillfälliga momstransaktioner** kan du granska resultatet av beräkningen. Om ingen moms beräknas, gå till [Moms beräknas inte, eller också är momsbeloppet noll](sales-tax-troubleshooting-tax-not-calculated-amount-zero.md).

## <a name="find-the-taxtrans-record-in-all-posted-sales-tax"></a>Hitta TaxTrans-posten i all bokförd moms

1. Gå till **Moms** \> **Förfrågningar och rapporter** \> **Momsförfrågningar** > **Bokförd moms**.
2. I kolumnrubriken för **Verifikation** väljer du filtersymbolen för att hitta posten **TaxTrans**.
3. Kontrollera datumet om det finns momsposter du letar efter. Om datumet inte är det samma som datumet för journalrubriken skapar du en Microsoft-servicebegäran för ytterligare support.

    [![Sidan Bokförd moms.](./media/taxtrans-is-not-generated-Picture4.png)](./media/taxtrans-is-not-generated-Picture4.png)

## <a name="debug-to-check-details"></a>Felsöka om du vill kontrollera detaljer

1. Mer information om hur du felsöker och fastställer huruvida **TmpTaxWorkTrans** och **TaxUncommitted** har genererats korrekt, se [Fältvärdet i TaxTrans är felaktigt](sales-tax-troubleshooting-field-value-taxtrans-incorrect.md).
2. Om **TaxTmpWorkTrans** eller **TaxUncommitted** har genererats korrekt lägger du till en brytpunkt för **TaxPost::SaveAndPost()** och **Tax::SaveAndPost** i syfte att felsöka orsaken till att **TaxTrans** inte förts in.

    [![Brytpunkter tillagda i kod.](./media/taxtrans-is-not-generated-Picture5.png)](./media/taxtrans-is-not-generated-Picture5.png)

    [![Resultat av tillagda brytpunkter.](./media/taxtrans-is-not-generated-Picture6.png)](./media/taxtrans-is-not-generated-Picture6.png)

## <a name="determine-whether-customization-exists"></a>Bestäm om anpassning finns

Om du har utfört stegen i de föregående avsnitten men inte hittat något problem, ska du fastställa om det finns någon anpassning. Om det inte finns någon anpassning skapar du en Microsoft-servicebegäran för ytterligare support.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
