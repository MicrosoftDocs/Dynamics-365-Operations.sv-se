---
title: Momsbetalningar och avrundningregler
description: Den här artikeln beskriver hur avrundningsregelinställningar på skattemyndigheter fungerar och avrundning av momssaldot under jobbet Kvitta och bokför moms.
author: kailiang
ms.date: 10/29/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: TaxAuthority
audience: Application User
ms.reviewer: kfend
ms.custom: 6134
ms.assetid: 7dcd3cf5-ebdf-4a9f-806c-1296c7da0331
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5c24a9850543e9d08ee1726186f433c7cfd26608
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8865695"
---
# <a name="sales-tax-payments-and-rounding-rules"></a>Momsbetalningar och avrundningregler

[!include [banner](../includes/banner.md)]

Den här artikeln beskriver hur avrundningsregelinställningar på skattemyndigheter fungerar och avrundning av momssaldot under jobbet Kvitta och bokför moms.

Moms måste regelbundet rapporteras och betalas till skattemyndigheten. Den här åtgärden kan slutföras genom att köra processen Reglera och bokför moms på sidan **Moms**. Moms för en period kommer att kvittas mot momskontona och momssaldot kommer att bokföras på momskvittningskontot. Momssaldot som bokförs på momskvittningskontot kan avrundas enligt som krävs av skattemyndigheten genom att ställa in en avrundningsregel på sidan **Moms**. 

Avrundningsdifferensen bokförs på Momsavrundningkontot som valts i fältet Konton för automatisk transaktion i huvudboken.

Exemplet nedanför illustrerar hur avrundningsregeln fungerar för Skattemyndigheten.

## <a name="examples"></a>Exempel

Det totala momsen för en period visar ett kreditsaldo på -98 765,43. Den juridiska personen samlade in mer moms än vad som har betalats. Därför är den juridiska personen skyldig pengar till skattemyndigheten. 

Den juridiska personen vill använda en avrundningsmetod som rundar av saldot till närmaste hela 1,00. Användaren som ansvarar för momsredovisningen måste då göra följande steg.

1. Klicka på **Skatt** > **Indirekt moms** > **Moms** > **Momsmyndigheter**.
2. I snabbfliken **Allmän** i fältet **Avrundningssätt**, välj **Normal**.
3. I fältet **Avrundning** anger du 1,00.
4. När det är dags att betala moms till skattemyndigheten, gå till **Skatt** > **Deklarationer** > **Moms** > **Kvitta och bokför moms**. På momskvittningskontot kan du se att skatteskuldbeloppet på **98 765,43** avrundas till **98 765**.

Följande tabell visar hur ett belopp på 98 765,43 avrundas med hjälp av varje avrundningsmetod som är tillgänglig i fältet **Avrundningsätt** på sidan **Momsmyndigheter**.

> [!NOTE]                                                                                  
> Om värdet för avrunda är inställt på 0,00 är:
>
> - Vid normal avrundning är avrundningsbeteendet detsamma som för **Avrundning = 0,01**.
> - För **Alternativ för avrundningssätt**, **Nedåt**, **Uppåt** och **Egen fördel** är beteendet detsamma som för **Avrundning = 1,00**.

| Aternativ för avrundningssätt                | Avrundningsvärde = 0,01 | Avrundningsvärde = 0,10 | Avrundningsvärde = 1,00 | Avrundningsvärde = 100,00 | Avrundningsvärde = 0,00   |
|-------------------------------------|------------------------|------------------------|------------------------|--------------------------|--------------------------|
| Normal                              | 98,765.43              | 98,765.40              | 98,765.00              | 98,800.00                | 98,765.43                |
| Nedåt                            | 98,765.43              | 98,765.40              | 98,765.00              | 98,700.00                | 98,765.00                |
| Uppåt                         | 98,765.43              | 98,765.50              | 98,766.00              | 98,800.00                | 98,766.00                |
| Egen fördel, för ett kreditsaldo | 98,765.43              | 98,765.40              | 98,765.00              | 98,700.00                | 98,765.00                |
| Egen fördel, för ett debetsaldo  | 98,765.43              | 98,765.50              | 98,766.00              | 98,800.00                | 98,766.00                |

### <a name="normal-round-and-round-precision-is-001"></a>Normal avrundning och avrundningsprecision är 0,01

```<table>
  <tr>
    <td>Rounding
    </td>
    <td>Calculation process
    </td>
  </tr>
    <tr>
    <td>round(1.015, 0.01) = 1.02
    </td>
    <td>
      <ol>
        <li>round(1.015 / 0.01, 0) = round(101.5, 0) = 102
        </li>
        <li>102 * 0.01 = 1.02
        </li>
      </ol>
    </td>
  </tr>
    <tr>
    <td>round(1.014, 0.01) = 1.01
    </td>
    <td> <ol>
        <li>round(1.014 / 0.01, 0) = round(101.4, 0) = 101
        </li>
        <li>101 * 0.01 = 1.01
        </li>
      </ol>
    </td>
  </tr>
    <tr>
    <td>round(1.011, 0.02) = 1.02
    </td>
    <td> <ol>
        <li>round(1.011 / 0.02, 0) = round(50.55, 0) = 51
        </li>
        <li>51 * 0.02 = 1.02
        </li>
      </ol>
    </td>
  </tr>
    <tr>
    <td>round(1.009, 0.02) = 1.00
    </td>
    <td> <ol>
        <li>round(1.009 / 0.02, 0) = round(50.45, 0) = 50
        </li>
        <li>50 * 0.02 = 1.00
        </li>
      </ol>
    </td>
  </tr>
</table>
```

> [!NOTE]                                                                                  
> Om du väljer Egen fördel är alltid avrundningen till fördelen för den juridiska personen. 

Mer information finns i följande avsnitt:
- [Momsöversikt](indirect-taxes-overview.md)
- [Skapa en momsbetalning](tasks/create-sales-tax-payment.md)
- [Skapa momstransaktioner i dokument](tasks/create-sales-tax-transactions-documents.md)
- [Visa bokförda momstransaktioner](tasks/view-posted-sales-tax-transactions.md)
- [avrundningsfunktionen](/previous-versions/dynamics/ax-2012/reference/aa850656(v=ax.60))




[!INCLUDE[footer-include](../../includes/footer-banner.md)]
