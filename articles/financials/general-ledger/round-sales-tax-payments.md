---
title: Momsbetalningar och avrundningregler
description: Den här artikeln beskriver hur avrundningsregelinställningar på skattemyndigheter fungerar och avrundning av momssaldot under jobbet Kvitta och bokför moms.
author: ShylaThompson
manager: AnnBe
ms.date: 05/30/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TaxAuthority
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 6134
ms.assetid: 7dcd3cf5-ebdf-4a9f-806c-1296c7da0331
ms.search.region: Global
ms.author: yijialuan
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 168c2fb9edfc994617ef6764a5b9f5949d599882
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/01/2019
ms.locfileid: "1835008"
---
# <a name="sales-tax-payments-and-rounding-rules"></a>Momsbetalningar och avrundningregler

[!include [banner](../includes/banner.md)]

Den här artikeln beskriver hur avrundningsregelinställningar på skattemyndigheter fungerar och avrundning av momssaldot under jobbet Kvitta och bokför moms.

Moms måste regelbundet rapporteras och betalas till skattemyndigheten. Detta gör du genom att köra kvittnings- och bokföringsmomsprocess på sidan Moms. Moms för en period kommer att kvittas mot momskontona och momssaldot kommer att bokföras på momskvittningskontot. Momssaldot som bokförs på momskvittningskontot, kan avrundas enligt som krävs av skattemyndigheten genom att ställa in en avrundningsregel på sidan Moms. 

Avrundningsdifferensen bokförs på Momsavrundningkontot som valts i fältet Konton för automatisk transaktion i huvudboken.

Exemplet nedanför illustrerar hur avrundningsregeln fungerar för Skattemyndigheten.

## <a name="examples"></a>Exempel

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
| Egen fördel, för ett debetsaldo  | 98,765.43              | 98,765.50              | 98,766.00              | 98,800.00                |


### <a name="no-rounding-at-all-since-the-round-off-is-000"></a>Ingen avrundning, eftersom avrundningen är 0,00

avrundning (1,0151, 0,00) = 1,0151 avrundning (1,0149, 0,00) = 1,0149

### <a name="normal-round-and-round-precision-is-001"></a>Normal avrundning och avrundningsprecision är 0,01

<table>
  <tr>
    <td>Avrundning
    </td>
    <td>Beräkningsprocess
    </td>
  </tr>
    <tr>
    <td>avrundning (1,015, 0,01) = 1,02
    </td>
    <td>
      <ol>
        <li>avrundning (1,015 / 0,01, 0) = avrundning (101,5, 0) = 102
        </li>
        <li>102 * 0,01 = 1,02
        </li>
      </ol>
    </td>
  </tr>
    <tr>
    <td>avrundning (1,014, 0,01) = 1,01
    </td>
    <td> <ol>
        <li>avrundning (1,014 / 0,01, 0) = avrundning (101,4, 0) = 101
        </li>
        <li>101 * 0,01 = 1,01
        </li>
      </ol>
    </td>
  </tr>
    <tr>
    <td>avrundning (1,011, 0,02) = 1,02
    </td>
    <td> <ol>
        <li>avrundning (1,011 / 0,02, 0) = avrundning (50,55, 0) = 51
        </li>
        <li>51 * 0,02 = 1,02
        </li>
      </ol>
    </td>
  </tr>
    <tr>
    <td>avrundning (1,009, 0,02) = 1,00
    </td>
    <td> <ol>
        <li>avrundning (1,009 / 0,02, 0) = avrundning (50,45, 0) = 50
        </li>
        <li>50 * 0,02 = 1,00
        </li>
      </ol>
    </td>
  </tr>
</table>

> [!NOTE]                                                                                  
> Om du väljer Egen fördel är alltid avrundningen till fördelen för den juridiska personen. 

Mer information finns i följande avsnitt:
- [Momsöversikt](indirect-taxes-overview.md)
- [Skapa en momsbetalning](tasks/create-sales-tax-payment.md)
- [Skapa försäljningstransaktioner i dokument](tasks/create-sales-tax-transactions-documents.md)
- [Visa bokförda momstransaktioner](tasks/view-posted-sales-tax-transactions.md)
- [avrundningsfunktionen](https://msdn.microsoft.com/library/aa850656.aspx)


