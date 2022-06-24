---
title: Avrundningsregler för momsberäkning
description: Detta ämne innehåller information om avrundningsreglerna i parametrarna för momsberäkningar för momsberäkningstjänsten.
author: kailiang
ms.date: 07/29/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kfend
ms.custom: ''
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2021-08-02
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: 0f6182ab18a5a408a6e526feec7014ccdfce8af0
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8858313"
---
# <a name="tax-calculation-rounding-rules"></a>Avrundningsregler för momsberäkning

[!include [banner](../includes/banner.md)]

Detta ämne innehåller information om hur avrundningsreglerna fungerar i parametrarna för momsberäkningna för momsberäkningstjänsten.

> [!NOTE] 
> När momsberäkningstjänsten är aktiverad gäller inte avrundningsreglerna på sidorna **Momskod** och **Momsgrupp**.

Du kan visa konfigurationen för avrundningsregler för momsberäkningstjänsten i avsnittet **Avrundningsregel för moms** på snabbfliken **Beräkning** på fliken **Allmänt** på sidan **Parametrar för momsberäkning** (**Moms** \> **Inställningar** \> **Momskonfiguration** \> **Parametrar för momsberäkning**).

[![Avrundningsregelkonfiguration på sidan Parametrar för momsberäkning](./media/tax-calculation-parameters-calculation-1.png)](./media/tax-calculation-parameters-calculation-1.png)

Fälten **Avrundningsprecision** och **Avrundningsmetod** bestämmer hur beräknade belopp i nyttolasten från momsberäkningstjänsten avrundas.

## <a name="rounding-precision"></a>Avrundningsprecision

Fältet **Avrundningsprecision** har stöd för ett värde med upp till sex decimaler. Om du till exempel anger fältet **Avrundningsprecision** som **0,000000** avrundas beräknades belopp till sex decimaler och skickas sedan till Microsoft Dynamics 365 Finance. Om exempelvis avrundningsmetoden **Normal** används kommer beloppet **987,1234567** att avrundas till **987,123457**.

> [!NOTE]
> Ekonomiska avrundningsbelopp enligt avrundningsreglerna för valutor. Därför påverkas momsbeloppen som visas och registreras i transaktionerna av både avrundningsregler för momsberäkningar och avrundningsregler för valuta.

## <a name="rounding-method"></a>Avrundningsmetod

Avrundningsmetoden för momsberäkning kan konfigureras för respektive juridisk person. I fältet **Avrundningsmetod** kan du välja mellan tre olika alternativ: **Normal**, **Nedåt** och **Avrundning**.

### <a name="rounding-example"></a>Exempel på avrundning

Följande tabell innehåller ett exempel som visar hur beloppet **987,345** avrundas för olika kombinationer av avrundningsprecision och avrundningsmetoder.

<table>
<thead>
<tr>
<th rowspan="2">Avrundningsmetod</th>
<th colspan="8">Avrundningsprecision</th>
</tr>
<tr>
<th>0,00</th>
<th>0.01</th>
<th>0.10</th>
<th>1.00</th>
<th>10,00</th>
<th>0.02</th>
<th>0.05</th>
<th>0.25</th>
</tr>
</thead>
<tbody>
<tr>
<td>Normal</td>
<td>987.35</td>
<td>987.35</td>
<td>987.30</td>
<td>987.00</td>
<td>990.00</td>
<td>987.34</td>
<td>987.35</td>
<td>987.25</td>
</tr>
<tr>
<td>Nedåt</td>
<td>987.00</td>
<td>987.34</td>
<td>987.30</td>
<td>987.00</td>
<td>980.00</td>
<td>987.34</td>
<td>987.30</td>
<td>987.25</td>
</tr>
<tr>
<td>Uppåt</td>
<td>988.00</td>
<td>987.35</td>
<td>987.40</td>
<td>988.00</td>
<td>990.00</td>
<td>987.36</td>
<td>987.35</td>
<td>987.50</td>
</tr>
</tbody>
</table>

Beräknings- och avrundningslogik för momsbelopp kan konfigureras enligt beskattningsreglerna.

## <a name="rounding-by"></a>Avrundning efter 

I fältet **Avrundas med** väljer du den avrundningsprincip som gäller för skatterna. Följande alternativ är tillgängliga:

- **Momskoder** – Avrunda momsbeloppet inuti respektive momskod.
- **Kombinationer av momskoder** – Avrunda momsbeloppet inuti kombinationen av momskod på raden.

## <a name="calculation-method"></a>Beräkningsmetod

I fältet **Beräkningsmetod** väljer du om moms på fakturor ska beräknas för respektive rad eller för alla rader. Följande alternativ är tillgängliga:

- **Rad** – Beräkna momsbeloppet rad för rad. Momsbeloppet på respektive rad påverkas inte av momsbeloppet på andra rader.
- **Summa** – Beräkna momsbeloppet för alla rader i ett dokument.

### <a name="rounding-calculation-example"></a>Exempel på avrundningsberäkning

I det här exemplet visas de olika beräkningar som kan göras för en faktura, för olika kombinationer av värden för **Avrundas med** och **Beräkningsmetod**. I detta exempel används följande inställningar:

- Fakturan har fyra rader.
- Det finns två momskoder: **VAT1** (10 procent) och **MOMS2** (10 procent).
- Avrundningsprecisionen är angiven som **0,01**.
- Avrundningsmetoden ställs in på **Uppåt**.

#### <a name="rounding-by--tax-codes-and-calculation-method--line"></a>Avrundning med = Momskoder och Beräkningsmetod = Rad

| Radnummer | Nettobelopp för rad | Bestämda momskoder | Momsbelopp före avrundning | Avrundat momsbelopp |
|-------------|-----------------|----------------------|----------------------------|--------------------|
| 1           | 11.11           | MOMS1                 | 1.111                      | 1.12               |
| 2           | 22.22           | MOMS1; MOMS2           | 2,222; 2,222               | 2,23; 2,23         |
| 3           | 33.33           | MOMS1                 | 3.333                      | 3.34               |
| 4           | 44.44           | MOMS1; MOMS2           | 4,444; 4,444               | 4,45; 4,45         |

#### <a name="rounding-by--tax-code-combinations-and-calculation-method--line"></a>Avrundning med = Kombinationer av momskod och Beräkningsmetod = Rad

| Radnummer | Nettobelopp för rad | Bestämda momskoder | Momsbelopp före avrundning | Avrundat momsbelopp |
|-------------|-----------------|----------------------|----------------------------|--------------------|
| 1           | 11.11           | MOMS1                 | 1.111                      | 1.12               |
| 2\*         | 22.22           | MOMS1; MOMS2           | 2,222; 2,222               | 2,23; 2,22         |
| 3           | 33.33           | MOMS1                 | 3.333                      | 3.34               |
| 4\*\*       | 44.44           | MOMS1; MOMS2           | 4,444; 4,444               | 4,45; 4,44         |

\* Rad 2 = Avrunda\[22,22 × (10 procent + 10 procent)\] = 2,23 + 2,22

\*\* Rad 4 = Avrunda\[44,44 × (10 procent + 10 procent)\] = 4,45 + 4,44

#### <a name="rounding-by--tax-codes-and-calculation-method--total"></a>Avrundning med = Momskoder och Beräkningsmetod = Summa

| Radnummer | Nettobelopp för rad | Bestämda momskoder | Momsbelopp före avrundning | Avrundat momsbelopp |
|-------------|-----------------|----------------------|----------------------------|--------------------|
| 1           | 11.11           | MOMS1\*               | 1.111                      | 1.12               |
| 2           | 22.22           | MOMS1\*; MOMS2\*\*     | 2,222; 2,222               | 2,22; 2,23         |
| 3           | 33.33           | MOMS1\*               | 3.333                      | 3.33               |
| 4           | 44.44           | MOMS1\*; MOMS2\*\*     | 4,444; 4,444               | 4,44; 4,44         |

\* MOMS1 (Rad 1, Rad 2, Rad 3, Rad 4) = Avrunda\[(11,11 + 22,22 + 33,33 + 44,44) × 10 procent\] = 1,12 + 2,22 + 3,33 + 4,44

\*\* MOMS2(Rad 2, Rad 4) = Avrunda\[(22,22 + 44,44) × 10 procent\] = 2,23 + 4,44

#### <a name="rounding-by--tax-code-combinations-and-calculation-method--total"></a>Avrundning med = Kombinationer av momskod och Beräkningsmetod = Summa

| Radnummer | Nettobelopp för rad | Bestämda momskoder | Momsbelopp före avrundning | Avrundat momsbelopp |
|-------------|-----------------|----------------------|----------------------------|--------------------|
| 1\*         | 11.11           | MOMS1                 | 1.111                      | 1.12               |
| 2\*\*       | 22.22           | MOMS1; MOMS2           | 2,222; 2,222               | 2,23; 2,22         |
| 3\*         | 33.33           | MOMS1                 | 3.333                      | 3.33               |
| 4\*\*       | 44.44           | MOMS1; MOMS2           | 4,444; 4,444               | 4,44; 4,45         |

\* Rad 1, Rad 3 = Avrunda\[(11,11 + 33,33) × 10 procent\] = 1,12 + 3,33

\*\* Rad 2, Rad 4 = Avrunda\[(22,22 + 44,44) × (10 procent + 10 procent)\] = 2,23 + 2,22 + 4,44 + 4,45

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
