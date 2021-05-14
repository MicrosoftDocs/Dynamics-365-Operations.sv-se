---
title: Resultatet av momsberäkningen påverkar transaktioner
description: Detta ämne innehåller felsökningsinformation som är relaterad till momsberäkningsprestanda och dess effekt på transaktioner.
author: shtao
manager: beya
ms.date: 04/07/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application user
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.1
ms.openlocfilehash: 7ff9d9b80172c3b337737b1cd53b4c56d1befe57
ms.sourcegitcommit: 57668404d61359b33e0c0280f2f7c4eb829b1ed2
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/27/2021
ms.locfileid: "5947713"
---
# <a name="tax-calculation-performance-affects-transactions"></a>Resultatet av momsberäkningen påverkar transaktioner

[!include [banner](../includes/banner.md)]

Ibland påverkas en transaktion av prestandaproblem som momsberäkningen har. Felsök det här problemet genom att följa stegen i följande avsnitt.

## <a name="review-the-transaction-line-count"></a>Granska antalet transaktionsrader

Bestäm huruvida transaktionen har ett stort antal rader (t.ex. fler än flera hundra). Om den inte gör det går du vidare till nästa avsnitt. Om transaktionen har flera hundra rader försenar du momsberäkningen. Mer information finns i [Aktivera fördröjd momsberäkning i journaler](enable-delayed-tax-calculation.md). 

Du kan sedan avgöra om något av följande villkor uppfylls:

- Det finns importtransaktioner från stora filer.
- Flera sessioner bearbetar samma transaktionsskatteberäkning samtidigt.
- Transaktionen har flera rader och vyerna uppdateras i realtid. Till exempel uppdateras fältet **Beräknat momsbelopp** på sidan **Allmän journal** uppdateras i realtid när en rads fält ändras.

   [![Beräknat momsbeloppsfält på sidan Journalverifikation](./media/tax-calculation-bad-performance-impacts-transaction-Picture1.png)](./media/tax-calculation-bad-performance-impacts-transaction-Picture1.png)

Om något av dessa villkor uppfylls ska du försena momsberäkningen.

## <a name="review-the-call-stack"></a>Granska anropsstacken

Granska anropsstacken för att avgöra om momsberäkningen anropas flera gånger. Om den inte gör det går du vidare till nästa avsnitt. Om anropsstacken anropas flera gånger följer du dessa steg för att minska momsberäkningstiderna.

1. Om transaktionen har övervägts i journalen försenar du momsberäkningen. Mer information finns i [Aktivera fördröjd momsberäkning i journaler](enable-delayed-tax-calculation.md).
2. Om transaktionen är en inköpsorder och programversionen är senare än 10.0.15 kan du försena momsberäkningen till den slutliga beräkningen genom att aktivera förhandsversionen för **PurchTableChangeMgmtDistributionUpdateOnToggle_KillSwitch**.

## <a name="review-the-call-stack-timeline"></a>Granska tidslinjen för anropsstacken

Granska tidslinjen för anropsstacken och ta reda på huruvida följande problem finns: Om de gör det ska du aktivera förhandsversionen för **TaxUncommittedDoIsolateScopeFlighting** för att åtgärda problemet.

- Transaktionen gör att systemet slutar svara tills sessionen avslutas. Därför kan momsresultatet inte beräknas i transaktionen. I följande bild visas meddelandet "Sessionen avslutad" som du får.

    [![Meddelande om att sessionen avslutats](./media/tax-calculation-bad-performance-impacts-transaction-Picture2.png)](./media/tax-calculation-bad-performance-impacts-transaction-Picture2.png)

- Metoden **TaxUncommitted** tar mer tid än andra metoder. I följande illustration tar metoden **TaxUncommitted::updateTaxUncommitted()** 43 347,42 sekunder, men andra metoder tar 0,09 sekunder.

    [![Tidslängder för metod](./media/tax-calculation-bad-performance-impacts-transaction-Picture3.png)](./media/tax-calculation-bad-performance-impacts-transaction-Picture3.png)

## <a name="customizing-and-calling-tax-calculation"></a>Anpassa och anropa momsberäkning

När du anpassar ska du inte anropa momsberäkningen vid metoden **insert()** eller **update()** för respektive rad. Momsberäkning ska anropas på transaktionsnivå.

## <a name="determine-whether-customization-exists"></a>Bestäm om anpassning finns

Om du har utfört stegen i de föregående avsnitten men inte hittat något problem, ska du fastställa om det finns någon anpassning. Om det inte finns någon anpassning skapar du en Microsoft-servicebegäran för ytterligare support.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
