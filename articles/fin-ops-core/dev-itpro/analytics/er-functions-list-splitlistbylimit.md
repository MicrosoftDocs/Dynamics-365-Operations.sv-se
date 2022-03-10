---
title: Funktionen SPLITLISTBYLIMIT ER
description: Det här avsnittet innehåller information om hur funktionen SPLITLISTBYLIMIT elektronisk rapportering (ER) används.
author: NickSelin
ms.date: 12/12/2019
ms.prod: ''
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
ms.openlocfilehash: 52351c131480119ce9fb98a75307ebf6026cb12b9977e8b4236d3a24ef6a140e
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6744444"
---
# <a name="splitlistbylimit-er-function"></a>Funktionen SPLITLISTBYLIMIT ER

[!include [banner](../includes/banner.md)]

`SPLITLISTBYLIMIT`-funktionen delar upp den angivna listan i en ny lista över underlistor (batchar). Antalet poster i varje batch beräknas dynamiskt. Funktionen returnerar sedan resultatet som ett nytt värde för *postlistan* som består av batchar.

## <a name="syntax"></a>Syntax

```vb
SPLITLISTBYLIMIT (list, limit value, limit source)
```

## <a name="arguments"></a>Argument

`list`: *Post-lista*

Den giltiga sökvägen av en datakälla för datatypen *Postlista*.

`limit value`: *Heltal* eller *Realtal*

Det högsta värdet för den gräns som används för att dela upp den ursprungliga listan i batchar.

`limit source`: *Fält*

Den giltiga sökvägen för ett fält med typen *Heltal* eller *Realtaltal* i den angivna listan. Värdet i det här fältet definierar steget som den totala summan ökas på.

## <a name="return-values"></a>Returvärden

*Post-lista*

Den resulterande listan med poster.

## <a name="usage-notes"></a>Användningsanteckningar

Listan av batchar som returneras innehåller följande element:

- **Värde**: *lista*

    Listan över poster som tillhör den aktuella batchen.

- **Batchnumber**: *heltal*

    Numret på den aktuella batchen i den returnerade listan.

Gränsen tillämpas inte på en enskild artikel i ursprungslistan när gränskällan överskrider angiven gräns.

## <a name="example"></a>Exempel

Följande illustration visar flödet av ER-format (elektronisk rapportering).

<a href="./media/ger-splitlistbylimit-format.png"><img src="./media/ger-splitlistbylimit-format.png" alt="Format" class="alignnone size-full wp-image-1204063" width="396" height="195" /></a>

I följande illustrationer visar de datakällor som används för det formatet.

<a href="./media/ger-splitlistbylimit-datasources.png"><img src="./media/ger-splitlistbylimit-datasources.png" alt="Data sources" class="alignnone size-full wp-image-1204073" width="320" height="208" /></a>

Följande illustration visar resultatet när formatet har körts. I det här fallet är resultatet en förenklad lista över varuartiklar.

<a href="./media/ger-splitlistbylimit-output.png"><img src="./media/ger-splitlistbylimit-output.png" alt="Output" class="alignnone size-full wp-image-1204083" width="462" height="204" /></a>

I följande exempel visas samma format som har justerats för att visa listan med varuartiklar i batchar, där varje enskild batch måste innehålla varuartiklar och inte överskrida gränsen på 9.

<a href="./media/ger-splitlistbylimit-format-1.png"><img src="./media/ger-splitlistbylimit-format-1.png" alt="Adjusted format" class="alignnone size-full wp-image-1204103" width="466" height="438" /></a>

<a href="./media/ger-splitlistbylimit-datasources-1.png"><img src="./media/ger-splitlistbylimit-datasources-1.png" alt="Data sources for the adjusted format" class="alignnone size-full wp-image-1204093" width="645" height="507" /></a>

Följande illustration visar resultatet när det anpassade formatet har körts.

<a href="./media/ger-splitlistbylimit-output-1.png"><img src="./media/ger-splitlistbylimit-output-1.png" alt="Output of the adjusted format" class="alignnone size-full wp-image-1204113" width="676" height="611" /></a>

> [!NOTE] 
> Gränsen tillämpas inte på den sista artikeln i den ursprungliga listan eftersom värdet (**11**) i gränskälla (**vikt**) överskrider angiven gräns (**9**). För att ignorera underlistor under rapportgenerering använder du antingen `WHERE` eller uttrycket **Aktiverad** för respektive formatelement du önskar.

## <a name="additional-resources"></a>Ytterligare resurser

[Lista över funktioner](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]