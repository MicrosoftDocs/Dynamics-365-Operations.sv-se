---
title: Momsbetalningar och avrundningregler
description: "Den här artikeln beskriver hur avrundningsregelinställningar på skattemyndigheter fungerar och avrundning av momssaldot under jobbet Kvitta och bokför moms."
author: twheeloc
manager: AnnBe
ms.date: 08/01/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: TaxAuthority
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 6134
ms.assetid: 7dcd3cf5-ebdf-4a9f-806c-1296c7da0331
ms.search.region: Global
ms.author: vstehman
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 13470282efc6b9135e86355cf8071b841aad3071
ms.contentlocale: sv-se
ms.lasthandoff: 11/03/2017

---

# <a name="sales-tax-payments-and-rounding-rules"></a>Momsbetalningar och avrundningregler

[!INCLUDE [banner](../includes/banner.md)]

Den här artikeln beskriver hur avrundningsregelinställningar på skattemyndigheter fungerar och avrundning av momssaldot under jobbet Kvitta och bokför moms.

Moms måste regelbundet rapporteras och betalas till skattemyndigheten. Detta gör du genom att köra kvittnings- och bokföringsmomsprocess på sidan Moms. Moms för en period kommer att kvittas mot momskontona och momssaldot kommer att bokföras på momskvittningskontot. Momssaldot som bokförs på momskvittningskontot, kan avrundas enligt som krävs av skattemyndigheten genom att ställa in en avrundningsregel på sidan Moms. 

Avrundningsdifferensen bokförs på Momsavrundningkontot som valts i fältet Konton för automatisk transaktion i huvudboken.

Exemplet nedanför illustrerar hur avrundningsregeln fungerar för Skattemyndigheten.

### <a name="example"></a>Exempel:

Det totala momsen för en period visar ett kreditsaldo på -98 765,43. Den juridiska personen samlade in mer moms än vad som har betalats. Därför är den juridiska personen skyldig pengar till skattemyndigheten. 

Den juridiska personen vill använda en avrundningsmetod som rundar av saldot till närmaste hela 1,00. Användaren som ansvarar för momsredovisningen måste då göra följande steg.

1.  Klicka på Skatt &gt; Indirekt moms &gt; Moms &gt; Skattemyndigheter
2.  I snabbfliken Standard, välj Normal i fältet Avrundningssätt.
3.  I fältet Avrundning anger du 1,00.
4.  När det är dags att betala moms till skattemyndigheten öppnar du Kvitta och bokför moms. (Klicka på Skatt &gt; Deklarationer &gt; Moms &gt; Kvitta och bokför moms.)
5.  På momskvittningkontot avrundas skatteskuldbeloppet på 98 765,43 till 98 765.

Följande tabell visar hur ett belopp på 98 765,43 avrundas med hjälp av varje avrundningsmetod som är tillgänglig i fältet Avrundningsätt på sidan Skattemyndigheten.

| Aternativ för avrundningssätt                | Avrundningsvärde = 0,01 | Avrundningsvärde = 0,10 | Avrundningsvärde = 1,00 | Avrundningsvärde = 100,00 |
|-------------------------------------|------------------------|------------------------|------------------------|--------------------------|
| Normal                              | 98 765,43              | 98 765,40              | 98 765,00              | 98 800,00                |
| Nedåt                            | 98 765,43              | 98 765,40              | 98 765,00              | 98 700,00                |
| Uppåt                         | 98 765,43              | 98 765,50              | 98 766,00              | 98 800,00                |
| Egen fördel, för ett kreditsaldo | 98 765,43              | 98 765,40              | 98 765,00              | 98 700,00                |
| Egen fördel, för ett debetsaldo  | 98 765,43              | 98 765,50              | 98 766,00              | 98 800,00                |

> [!NOTE]                                                                                  
> Om du väljer Egen fördel är alltid avrundningen till fördelen för den juridiska personen. 

Mer information finns i följande avsnitt:
- [Momsöversikt](indirect-taxes-overview.md)
- [Skapa en momsbetalning](tasks/create-sales-tax-payment.md)
- [Skapa försäljningstransaktioner i dokument](tasks/create-sales-tax-transactions-documents.md)
- [Visa bokförda momstransaktioner](tasks/view-posted-sales-tax-transactions.md)



