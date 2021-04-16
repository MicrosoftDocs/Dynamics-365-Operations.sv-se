---
title: Base64StringToContainer ER-funktion
description: Det här avsnittet innehåller information om hur funktionen Base64StringToContainer elektronisk rapportering (ER) används.
author: NickSelin
ms.date: 12/14/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2020-12-01
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 6fd08d9a2522bdf497b1926c884a4583065d9f19
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5754384"
---
# <a name="base64stringtocontainer-er-function"></a>Base64StringToContainer ER-funktion

[!include [banner](../includes/banner.md)]

`BASE64STRINGTOCONTAINER` [funktion](er-formula-language.md#functions) konverterar det angivna indata för typen *Sträng* till ett dataobjekt i typen *[Behållare](er-functions-category-container.md)*.

## <a name="syntax"></a>Syntax

```vb
BASE64STRINGTOCONTAINER (input)
```

## <a name="arguments"></a>Argument

`input`: *Sträng*

Den giltiga sökvägen till en datakälla av typen *Sträng*.

## <a name="return-values"></a>Returvärden

*Container*

Det resulterande binära värdet i binärt stort objekt (BLOB) format.

## <a name="usage-notes"></a>Användningsanteckningar

Undantaget "Parameter är inte giltig" är aktuell om indatasträngen inte ger en korrekt Base64-grupp av binär-till-text-kodningsscheman.

## <a name="example"></a>Exempel

Du definierar följande datakällor i din modellmappning:

- Roten **DocuTypeGroupEnum**-datakällan för typen *Dynamics 365 for Operations / uppräkning* som refererar till **DocuTypeGroup** programuppräkning
- Roten **Kund** datakälla av typen *Dynamics 365 for Operations / Tabellregister* som refererar till programtabellen **CustTable**
- Datakällan **\#Media** av typen *Calculated field* som konfigureras på följande sätt:

    - Den läggs till som underordnad datakälla till datakällan **kund**.
    - Den innehåller uttrycket `WHERE(@.'<Relations'.'<Documents', @.'<Relations'.'<Documents'.'docuType()'.TypeGroup = DocuTypeGroupEnum.Image)`.

- Datakällan **\#MediaAsBase64String** av typen *Calculated field* som konfigureras på följande sätt:

    - Den läggs till som underordnad datakälla till datakällan **Kund.'\#Media'**.
    - Den innehåller uttrycket `Customer.'#Media'.'getFileContentAsBase64String()'`.

- Datakällan **\#BlobFomBase64** av typen *Calculated field* som konfigureras på följande sätt:

    - Den läggs till som underordnad datakälla till datakällan **Kund.'\#Media'**.
    - Den innehåller uttrycket `Base64StringToContainer(Customer.'#Media'.'#MediaAsBase64String')'`.

I det här exemplet kodar datakällan **\#MediaAsBase64String** det binära innehållet i den aktuella mediebilagan som text som representerar en Base64-grupp med binär-till-text-kodningsscheman. Datakällan **\#BlobFomBase64** avkodar Base64-strängen och returnerar ett binärt värde i BLOB-format.

![Exempeldatakälla på sidan för ER-modellmappningsdesigner](./media/er-functions-container-base64stringtocontainer-1.png)

## <a name="additional-resources"></a>Ytterligare resurser

[Behållarfunktioner](er-functions-category-container.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]