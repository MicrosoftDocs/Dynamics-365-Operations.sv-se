---
title: QRCODE ER-funktion
description: Den här artikeln innehåller information om hur funktionen QRCODE elektronisk rapportering (ER) används.
author: kfend
ms.date: 12/10/2019
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
ms.openlocfilehash: 9de62eefb82942ccc72e81bd9bf36eed07c99dba
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9287201"
---
# <a name="qrcode-er-function"></a>QRCODE ER-funktion

[!include [banner](../includes/banner.md)]

`QRCODE`-funktionen returnerar ett värde för *behållare* som visar en bild för snabb svarskod (QR-kod) för den angivna strängen i binärt format.

## <a name="syntax"></a>Syntax

```vb
QRCODE (text)
```

## <a name="arguments"></a>Argument

`text`: *Sträng*

Ett *sträng*-värde som representerar den ursprungliga texten.

## <a name="return-values"></a>Returvärden

*Behållare*

Den resulterande binära strömmen.

## <a name="example"></a>Exempel

Du kan konfigurera ett format för elektronisk rapportering (ER) för att generera ett utgående dokument i Microsoft Office-format (Excel-arbetsböcker eller Word-dokument) med hjälp av en fördefinierad mall. Den här mallen kan innehålla ett **bildobjekt** (Excel-arbetsbok) eller en **bildinnehållskontroll** (Word-dokument) som en platshållare för en QR-kodavbildning. Du måste lägga till ett konfigurerade ER-format ett **Cell**-element som ska användas för att fylla platshållaren i. Om du vill ange vilken information som ska lagras i en QR-kod måste du definiera en bindning för det här **Cell**-elementet. Du kan till exempel konfigurera en sådan bindning som innehåller följande uttryck:

```vb
QRCODE (model.ListOfShelfLabels.LabelText)`
```

När du kör det konfigurerade ER-formatet visas textvärdet för **LabelText** för datakällan **model.ListOfShelfLabels** kommer att användas för att generera en QR-kodavbildning. Den här bilden ersätter en platshållare för QR-kodbilder i dokumentmallen med hjälp av för att generera ett utgående dokument. När den här bilden av det genererade dokumentet skannas returneras den text som hämtats från fältet **LabelText** i datakällan **model.ListOfShelfLabels**. För mer information om [Bädda in bilder och former i dokument som du skapar med ER](electronic-reporting-embed-images-shapes.md)

## <a name="additional-resources"></a>Ytterligare resurser

[Textfunktioner](er-functions-category-text.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
