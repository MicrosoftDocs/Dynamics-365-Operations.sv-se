---
title: Fakturahantering för B2B-näthandelssajter
description: Denna artikel beskriver fakturahantering i Microsoft Dynamics 365 Commerce B2B-näthandelssajter.
author: shajain
ms.date: 02/16/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RetailOperations
audience: Application User, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.search.industry: retail
ms.author: shajain
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: fa6b81187481a6b7f47ea02291e5a581052d6c7b
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8854936"
---
# <a name="invoice-management-for-b2b-e-commerce-websites"></a>Fakturahantering för B2B-näthandelssajter

[!include [banner](../../includes/banner.md)]

Denna artikel beskriver fakturahantering i Microsoft Dynamics 365 Commerce B2B-näthandelssajter.

Det är vanligt att företag som hanterar B2B-transaktioner accepterar order på kundkredit och sedan skickar en faktura till kunder efter att de har fullföljt ordern. Betalningsvillkor definieras för kunder och det kan finnas vissa rabatter för att motivera kunder att betala i tid eller före tid. Om du vill öka sannolikheten för att betalningarna tas emot i tid kan B2B-näthandelssajter visa alla kunders fakturor. Kunden kan enkelt filtrera fakturorna så att de visas med betalda, obetalda och delvis betalda fakturor tillsammans med förfallodatum.

![Fakturasida på en B2B-webbplats.](../media/ViewInvoices.png)

> [!NOTE]
> En inloggad användare kan bara visa och betala sina egna fakturor. Om ett organisationskonto är konfigurerat på rullgardinsmenyn **Fakturakonto** på snabbfliken **Faktura och leverans** i kundposten i Commerce headquarters, kommer användaren att kunna se och betala fakturor för organisationskontot.

På sidan **faktura** för en B2B-webbplats kan en användare välja en obetald eller delvis betald faktura och sedan välja **Betalningsfaktura**. Den valda fakturan läggs till i vagnen, och användaren kan gå vidare med betalningen. Användaren kan sedan bestämma om han eller hon ska betala hela fakturan eller ett delbelopp. Användaren kan inte använda betalningsmetoden på konto för att betala för fakturor.

> [!NOTE]
> Fakturor kan bara läggas till i vagnen om det inte finns några artiklar i den. Omvänt kan artiklar läggas till i kundvagnen endast om inga fakturor för närvarande finns i den. Microsoft planerar att ta bort denna begränsning i framtida Commerce-versioner.

![Vagnssidan på en B2B-webbplats.](../media/PayInvoice.png)

På sidan **Fakturor** kan en användare också välja **Begär faktura** bredvid en faktura. På det här sättet kan användaren begära att få detaljerad information om fakturan skickad till sin registrerade e-postadress.

![Begär fakturadialogruta.](../media/RequestInvoice2.png)

När en användare har begärt en faktura flyttas denna begäran till avsnittet **B2B-förfrågningar** på sidan **Mitt konto**. Sedan, efter att **P-0001** och **Synkronisera order och jobb för kanalbegäran** har körts i Commerce headquarters, utlöses e-postmeddelandet med fakturan och statusen för B2B-begäran markeras som slutförd.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
