---
title: NUMSEQVALUE ER-funktion
description: Den här artikeln innehåller information om hur funktionen NUMSEQVALUE elektronisk rapportering (ER) används.
author: kfend
ms.date: 12/17/2019
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
ms.openlocfilehash: 62255f0a47d3c67468cf2cf3922a1886c29c03d6
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9271566"
---
# <a name="numseqvalue-er-function"></a>NUMSEQVALUE ER-funktion

[!include [banner](../includes/banner.md)]

`NUMSEQVALUE`-funktionen returnerar ett *Sträng*-värde som representerar det nya genererade värdet för en nummerserie, baserat på den angivna nummersekvensen, omfattningen och omfattnings-ID. Omfattnings-ID är lika med företagskoden som tillhandahålls av kontexten som ER-formatet (elektronisk rapportering) körs under.

## <a name="syntax-1"></a>Syntax 1

```vb
NUMSEQVALUE (number sequence code)
```

## <a name="syntax-2"></a>Syntax 2

```vb
NUMSEQVALUE (number sequence record ID)
```

## <a name="syntax-3"></a>Syntax 3

```vb
NUMSEQVALUE (number sequence code, scope type, scope ID)
```

## <a name="arguments"></a>Argument

`number sequence code`: *Sträng*

Ett textvärde som representerar koden för den nummerserie som ett nytt värde krävs i.

`number sequence record ID`: *Int64*

Ett *Int64*-värde som representerar post-ID för en post i tabellen NumberSequenceTable som innehåller definitionen av den nummerserie som ett nytt värde krävs i.

`scope type`: *Uppräknat värde*

Ett numreringsvärde för uppräkningen **ERExpressionNumberSequenceScopeType** som definierar omfattningen för den nummerserie som ett nytt värde krävs i. Tillgängliga omfattningstyper är **delade**, **juridisk person** och **företag**.

`scope ID`: *Sträng*

Ett *sträng* värde som identifierar scopet baserat på den angivna omfattningstypen.

## <a name="return-values"></a>Returvärden

*Sträng*

Det resulterande textvärdet.

## <a name="usage-notes"></a>Användningsanteckningar

För omfattningstypen **delad**, ange en tom sträng som områdes-ID.

För omfattningstypen **företag** och **juridisk person**, ange företagskoden som områdes-ID. Om du anger en tom sträng som områdes-ID för dessa omfattningstyper, används aktuella företagskoden.

När syntax 1 används begärs nummerserien för omfattningstypen **företag** och företagskoden tillhandahålls av kontexten som ER-formatet körs under.

## <a name="example-1"></a>Exempel 1

I ER-format definierar du **AskNumSeq**-datakällan för parametertypen *Användarindataparametrar*. Den här datakällan refererar till den utökade datatypen **Beskrivning** (EDT). Därefter definierar **NumSeq**-datakällan för typen *beräknade fält*. Datakällan innehåller uttrycket `NUMSEQVALUE (AskNumSeq)`. När **NumSeq**-datakällan anropas returneras det nya genererade värdet för den nummersekvens som angavs vid körningen genom att ange dess kod i dialogrutan. Nummerserien begärs för omfattningstypen **företag**. Företagskoden tillhandahålls av kontexten som ER-formatet körs under.

## <a name="example-2"></a>Exempel 2

Du definierar följande datakällor i din modellmappning:

- Datakällan **LedgerParms** för typen *tabell*. Den här datakällan refererar till tabellen LedgerParameters.
- **NumSeq**-datakällan för typen *beräknade fält*. Datakällan innehåller uttrycket `NUMSEQVALUE ( LedgerParameters.'numRefJournalNum()'.NumberSequenceId)`.

När datakällan **NumSeq** kallas, returneras det nya genererade värdet för nummerserien som har konfigurerats i Redovisningsparametrar för det företag som tillhandahåller den kontext som ER-formatet körs under. Den här nummerserien identifierar unikt journaler och fungerar som ett batchnummer som kopplar ihop transaktionerna.

## <a name="example-3"></a>Exempel 3

Du definierar följande datakällor i din modellmappning:

- **enumScope**-datakällan för Microsoft Dynamics 365 Finance typen *uppräkning*. Den här datakällan refererar till den utökade uppräkningen **ERExpressionNumberSequenceScopeType**.
- **NumSeq**-datakällan för typen *beräknade fält*. Datakällan innehåller uttrycket `NUMSEQVALUE ("Gene_1", enumScope.Company, "")`.

När datakällan **NumSeq** kallas, returneras det nya genererade värdet för nummerserien **Gen\_1** som har konfigurerats för det företag som tillhandahåller den kontext som ER-formatet körs under.

## <a name="additional-resources"></a>Ytterligare resurser

[Andra (företagsdomänspecifika) funktioner](er-functions-category-other.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
