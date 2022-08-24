---
title: Funktionen ORDERBY ER
description: Den här artikeln innehåller information om hur funktionen ORDERBY elektronisk rapportering (ER) används.
author: kfend
ms.date: 12/12/2019
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
ms.openlocfilehash: 23ace859bf75b2adb6ef8604475519a015486948
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9282574"
---
# <a name="orderby-er-function"></a>Funktionen ORDERBY ER

[!include [banner](../includes/banner.md)]

`ORDERBY`-funktionen returnerar den angivna listan som ett värde för *postlista* efter att den har sorterats enligt de angivna argumenten. Du kan definiera följande argument som uttryck.

## <a name="syntax-1"></a><a name="syntax-1"></a>Syntax 1

```vb
ORDERBY (list, expression 1[, expression 2, …, expression N])
```

## <a name="syntax-2"></a><a name="syntax-2"></a>Syntax 2

```vb
ORDERBY (location, list, expression 1[, expression 2, …, expression N])
```

> [!NOTE]
> Den här syntaxen stöds för Microsoft Dynamics 365 Finance version 10.0.25 och senare.

## <a name="arguments"></a>Argument

`location`: *[Sträng](er-formula-supported-data-types-primitive.md#string)*

Platsen där sorteringen ska köras. Följande alternativ är giltig:

- "Fråga"
- "InMemory"

`list`: *[Post-lista](er-formula-supported-data-types-composite.md#record-list)*

Den giltiga sökvägen av en datakälla för datatypen *Postlista*.

`expression 1`: *Fält*

Den giltiga sökvägen för ett fält i datakällan som refereras av `list`-argumentet för den anropade funktionen. Det refererade fältet måste vara ett fält av den primitiva datatypen. Detta argument krävs.

`expression N`: *Fält*

Den giltiga sökvägen för ett fält i datakällan som refereras av `list`-argumentet för den anropade funktionen. Det refererade fältet måste vara ett fält av den primitiva datatypen. Dessa ytterligare argument är valfria.

## <a name="return-values"></a>Returvärden

*Postlista*

Den resulterande listan med poster.

## <a name="usage-notes"></a>Användningsanteckningar

### <a name="syntax-1"></a>Syntax 1

Datasortering sker alltid i programserverns minne. Mer information finns i [exempel 1](#example-1).

### <a name="syntax-2"></a>Syntax 2

### <a name="sorting-in-memory"></a>Sortera i minne

När argumentet `location` anges som **InMemory** görs datasortering i en programservers minne. Mer information finns i [exempel 2](#example-2).

### <a name="sorting-in-database"></a>Sortera i databas

När argumenten `location` anges som **Fråga** utförs datasortering på databasnivå. I det här fallet `list` måste argumentet peka på en av följande datakällor för [elektronisk rapportering (ER)](general-electronic-reporting.md) som anger programkällan som en direkt databasfråga kan skapas för:

- Datakällan In för typen *tabellposter*
- Relationen till en datakälla för *tabellposter*
- Datakälla av typen *Beräknat fält*

Argumenten `expression 1` och `expression N` måste peka på en av följande ER-datakällor för som anger relevanta fält för programkällan som en direkt databasfråga också kan skapas för.

Om det inte går att upprätta en direkt databasfråga, uppstår ett [valideringsfel](er-components-inspections.md#i18) i ER-modellmappningsdesignern. Meddelandet som du tar emot anger att ER-uttrycket som innehåller `ORDERBY`-funktionen inte kan köras under körning.

Vi rekommenderar att du använder alternativet **Fråga** när sorteringen är konfigurerad för programdatakällor som kan innehålla det stora antalet poster (till exempel för transaktionsprogramregister).

> [!NOTE]
> Själva `ORDEBY` funktionen kan inte översättas till en direkt databasfråga. Därför är en ER-datakälla som innehåller den här funktionen inte frågebar. Den kan inte heller användas inom ER-funktionernas område, t.ex. [FILTER](er-functions-list-filter.md) och [ALLITEMSQUERY](er-functions-list-allitemsquery.md), där endast frågebara datakällor kan användas.

Mer information finns i [exempel 3](#example-3) och [exempel 4](#example-4).

### <a name="comparability"></a>Jämförbarhet

Eftersom SQL-databasmotorn och Ekonomi-appservern kan använda ett annat rankningsvärde för ett enskilt tecken, kan sorteringsresultatet för samma lista med poster skilja sig när fältet [Sträng](er-formula-supported-data-types-primitive.md#string) används för sortering. Mer information finns i [exempel 5](#example-5).

## <a name="example-1-in-memory-default-execution"></a><a name="example-1"></a>Exempel 1: Standardkörningen för inminnet

Om du anger datakällans **DS** av typen *Beräknat fält* och den innehåller uttrycket `SPLIT ("C|B|A", "|")`, kommer uttrycket `FIRST( ORDERBY( DS, DS. Value)).Value` att returnera textvärdet **"A"**.

## <a name="example-2-in-memory-explicit-execution"></a><a name="example-2"></a>Exempel 2: Explicit körning för inminnet

Om **Leverantör** konfigureras som en ER-datakälla av typen *Tabellposter* som refererar till tabellen **VendTable** kommer både uttrycket `ORDERBY (Vendor, Vendor.'name()')` och uttrycket `ORDERBY ("InMemory", Vendor, Vendor.'name()')` returnera en lista med leverantörerna sorterade efter namn i stigen ordning.

När du konfigurerar uttrycket `ORDERBY ("Query", Vendor, Vendor.'name()')` i ER-modellmappningsdesignern inträffar ett [valideringsfel](er-components-inspections.md#i8) vid designtiden, eftersom sökvägen `Vendor.'name()'` refererar till en programmetod som har logik som inte kan översättas till en direkt databasfråga.

## <a name="example-3-database-query"></a><a name="example-3"></a>Exempel 3: databasfråga

Om **TaxTransaction** har konfigurerats som en ER-datakälla av typen *Tabellposter* som refererar till tabellen **TaxTrans** sorterar uttrycket `ORDERBY ("Query", TaxTransaction, TaxTransaction.TaxCode)` poster på appdatabasnvå och returnerar en lista över momskod i stigande ordning.

## <a name="example-4-queryable-data-sources"></a><a name="example-4"></a>Exempel 4: frågningsbara datakällor

Om **TaxTransaction** har konfigurerats som en ER-datakälla av typen *Tabellposter* som refererar till tabellen **TaxTrans** kan ER-datakällan **TaxTransactionFiltered** konfigureras så att den innehåller uttrycket `FILTER(TaxTransaction, TaxCode="VAT19")` som hämtar transaktioner för en specificerad momskod. Eftersom den konfigurerade **TaxTransactionFiltered** ER-datakällan kan frågas, kan uttrycket `ORDERBY ("Query", TaxTransactionFiltered, TaxTransactionFiltered.TransDate)` konfigureras att returnera listan med filtrerade momstransaktioner sorterade efter transaktionsdatum i stigande ordning.

Om du konfigurerar **TaxTransactionOrdered** som en ER-datakälla för den *beräknade fälttypen* som innehåller uttrycket `ORDERBY ("Query", TaxTransaction, TaxTransaction.TransDate)` och en ER-datakälla för typen *beräknade fält* som innehåller uttrycket `FILTER(TaxTransactionOrdered, TaxCode="VAT19")` inträffar ett [valideringsfel](er-components-inspections.md#i18) vid designtiden i ER-modellmappningsdesignern. Detta fel inträffar eftersom det första argumentet för funktionen [FILTER](er-functions-list-filter.md#usage-notes) måste hänvisa till en frågebar ER-datakälla, men datakällan **TaxTransactionOrdered** som innehåller funktionen `ORDERBY` kan inte frågas.

## <a name="example-5-comparability"></a><a name="example-5"></a>Exempel 5: Kontinuitet

### <a name="prerequisites"></a>Förutsättningar

1. Ange **DS1**-datakälla av typen *beräknat fält* som innehåller uttrycket `SPLIT ("D1|_D2|D3", "|")`.
2. Öppna sidan **[Värden för ekonomisk dimension](../../../finance/general-ledger/financial-dimensions.md)** och välj dimension **CostCenter**.
3. Ange följande dimensionsvärden: **D1**, **\_D2** och **D3**.

### <a name="sorting-in-memory"></a>Sortera i minne

1. Konfigurera datakälla **DS2**-datakälla av typen *beräknat fält* som innehåller uttrycket `ORDERBY("InMemory", DS1, DS1.Value)`
2. Lägg märke till att uttrycket `FIRST(DS2).Value` returnerar textvärdet **"D1"**, uttrycket `INDEX(DS2, COUNT(DS2)).Value` returnerar textvärdet **"\_D2"** och uttrycket `STRINGJOIN(DS2, DS2.Value, "|")` returnerar textvärdet **"D1\|D3\|\_D2"**.

### <a name="sorting-in-database"></a>Sortera i databas

1. Ange datakälla **DS3** av typen *Tabellregister* som refererar till entiteten **FinancialDimensionValueEntity**.
2. Konfigurera datakälla **DS4**-datakälla av typen *beräknat fält* som innehåller uttrycket `FILTER(DS3, DS3.FinancialDimension="CostCenter")`
3. Konfigurera datakälla **DS5**-datakälla av typen *beräknat fält* som innehåller uttrycket `ORDERBY(DS4, DS4.DimensionValue)`
4. Lägg märke till att uttrycket `FIRST(DS5).Value` returnerar textvärdet **"\_D2"**, uttrycket `INDEX(DS5, COUNT(DS5)).Value` returnerar textvärdet **"D3"** och uttrycket `STRINGJOIN(DS5, DS5.Value, "|")` returnerar textvärdet **"\_D2\|D1\|D3"**.

## <a name="additional-resources"></a>Ytterligare resurser

[Lista över funktioner](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
