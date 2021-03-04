---
title: Lista över ER-funktioner i listkategorin
description: Det här ämnet ger information om listfunktionerna som stöds i elektronisk rapportering (ER).
author: NickSelin
manager: kfend
ms.date: 04/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e2e708c59bceebf845ee78c98057133bb2892cf9
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/05/2020
ms.locfileid: "4686197"
---
# <a name="list-of-er-functions-in-the-list-category"></a>Lista över ER-funktioner i listkategorin

[!include [banner](../includes/banner.md)]

Listfunktioner för elektronisk rapportering (ER) kan användas för att extrahera information från och utföra åtgärder på datakällor för datatypen *postlista* och *behållare (post)*. Det här avsnittet innehåller en sammanfattning av dessa funktioner.

## <a name="list-of-supported-functions"></a>Lista över funktioner som stöds

| Funktion | Beskrivning |
|----------|-------------|
| [AllItems](er-functions-list-allitems.md)                 | Den här funktionen körs som ett urval i minnet. Den returnerar ett nytt tillplattat värde för *postlista* som består av en lista med poster som representerar alla objekt som matchar den angivna sökvägen. |
| [AllItemsQuery](er-functions-list-allitemsquery.md)       | Den här funktionen körs som en sammanslagen SQL-fråga. Den returnerar ett nytt tillplattat värde för *postlista* som består av en lista med poster som representerar alla objekt som matchar den angivna sökvägen. |
| [Antal](er-functions-list-count.md)                       | Den här funktionen returnerar ett *heltal*-värde som representerar antalet poster i den angivna listan, om listan inte är tom. Om listan är tom returnerar den här funktionen **0** (noll). |
| [EmptyList](er-functions-list-emptylist.md)               | Den här funktionen returnerar en tomt värde för *Postlista* genom att använda den definierade en lista som källa för liststrukturen.|
| [Uppräkning](er-functions-list-enumerate.md)               | Den här funktionen returnerar ett nytt *postlista*-värde som består av fasta poster i den angivna listan. |
| [Filtrera](er-functions-list-filter.md)                     | Den här funktionen returnerar den angivna listan som ett värde för *postlista* efter att frågan har ändrats så att dess filter enligt det angivna villkoret. |
| [Först](er-functions-list-first.md)                       | Den här funktionen returnerar den första posten i den angivna listan som ett *behållarvärde (post)* om den listan inte är tom. Om listan är tom, genererar den här funktionen ett undantag. |
| [FirstOrNull](er-functions-list-firstornull.md)           | Den här funktionen returnerar den första posten i den angivna listan som ett *behållarvärde (post)* om posten inte är tom. Om posten är tom returnerar den här funktionen ett nullvärde *behållare (post)*. |
| [Index](er-functions-list-index.md)                       | Den här funktionen returnerar värde för *behållare (post)* som väljs med hjälp av det angivna numeriska indexet i den angivna listan. Om indexet är utom räckvidd för posterna i den angivna listan erhåller denna funktion ett undantag. |
| [IsEmpty](er-functions-list-isempty.md)                   | Den här funktionen returnerar *booleskt värde* för **SANT** om den angivna listan inte innehåller några poster. Annars returnerar uttrycket värdet *boolesk* av **FALSK**. |
| [Lista](er-functions-list-list.md)                         | Den här funktionen returnerar ett *postlista*-värde som består av en ny lista som skapas från de angivna argumenten.|
| [ListDistinct](er-functions-list-listdistinct.md)         | Den här funktionen beräknar det angivna uttrycket som en väljare för varje post i den angivna listan. Det returnerar ett nytt värde för *postlista* som innehåller en enskild post för varje unikt väljarvärde.|
| [ListJoin](er-functions-list-listjoin.md)                 | Den här funktionen returnerar ett *postlista*-värde som representerar en ny sammanslagen lista som skapas från de angivna argumenten.|
| [ListOfFields](er-functions-list-listoffields.md)         | Den här funktionen returnerar ett *postlista*-värde som skapas baserat på strukturen för det angivna argumentet i typen *uppräkning* eller *behållare (post)*. |
| [ListOfFirstItem](er-functions-list-listoffirstitem.md)   | Den här funktionen returnerar ett *postlista*-värde som endast består av den första posten i den angivna listan.|
| [OrderBy](er-functions-list-orderby.md)                   | Den här funktionen returnerar den angivna listan som ett värde för *postlista* efter att den har sorterats enligt de angivna argumenten. Du kan definiera följande argument som uttryck. |
| [Återför](er-functions-list-reverse.md)                   | Den här funktionen returnerar den angivna listan som ett värde *postlista* i omvänd sorteringsordning. |
| [Dela](er-functions-list-split.md)                       | Den här funktionen delar den angivna indatasträngen i delsträngar och returnerar resultatet som ett nytt värde för *postlistan*. |
| [SplitList](er-functions-list-splitlist.md)               | Den här funktionen delar upp angivna listan i underlistor (eller batchar) som var och en innehåller det definierade antalet poster. Den returnerar sedan resultatet som ett nytt värde för *postlistan* som består av batchar. |
| [SplitListByLimit](er-functions-list-splitlistbylimit.md) | Den här funktionen delar upp den angivna listan i en ny lista över underlistor (batchar). Antalet poster i varje batch beräknas dynamiskt. Funktionen returnerar sedan resultatet som ett nytt värde för *postlistan* som består av batchar. |
| [StringJoin](er-functions-list-stringjoin.md)             | Den här funktionen returnerar ett *Sträng*-värde som består av de konkatenerade värdena från det definierade fältet från den angivna listan. Värdena kan avgränsas med angivna avgränsare. |
| [Var](er-functions-list-where.md)                       | Den här funktionen returnerar den angivna listan som ett värde för *postlista* efter att den har filtreras enligt det angivna villkoret. |

## <a name="additional-resources"></a>Ytterligare resurser

[Översikt över elektronisk rapportering](general-electronic-reporting.md)

[Formeldesigner i elektronisk rapportering](general-electronic-reporting-formula-designer.md)

[Formelspråk i elektronisk rapportering](er-formula-language.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]