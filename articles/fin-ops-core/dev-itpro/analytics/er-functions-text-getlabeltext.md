---
title: GETLABELTEXT ER-funktion
description: Det här avsnittet innehåller information om hur funktionen GETLABELTEXT elektronisk rapportering (ER) används.
author: NickSelin
ms.date: 03/18/2022
ms.prod: ''
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2022-01-01
ms.dyn365.ops.version: AX 10.0.25
ms.openlocfilehash: 2ce66c9410abeee16bbd074204262edf79bf6d68
ms.sourcegitcommit: c0f7ee7f8837fec881e97b2a3f12e7f63cf96882
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/22/2022
ms.locfileid: "8462423"
---
# <a name="getlabeltext-er-function"></a>GETLABELTEXT ER-funktion

[!include [banner](../includes/banner.md)]

Med `GETLABELTEXT`-funktion söker du efter en specifik etikett för att returnera ett *[sträng](er-formula-supported-data-types-primitive.md#string)* värde som representerar översättningen av den angivna etiketten på det angivna språket.

## <a name="syntax"></a>Syntax

```vb
GETLABELTEXT (label id, language)
```

## <a name="arguments"></a>Argument

### <a name="label-id"></a>Etikett-ID

`label id`: *Sträng* eller *Etikett-ID*

Giltigt ID för en av följande etiketttyper:

- [Elektronisk rapportering (ER)](general-electronic-reporting.md) etikett
- Microsoft Dynamics 365 Finance etikett

#### <a name="usage-notes"></a>Användningsanteckningar

Detta argument kan bara definieras som en konstant genom att använda något av följande mönster som stöds:

- För ER-etiketter:

    - `@"GER_LABEL:<LABEL ID>"`
    - `"GER_LABEL:<LABEL ID>"`

- För Ekonomi-etiketter:

    - `@"<LABEL ID>"`
    - `"<LABEL ID>"`

> [!NOTE]
> Vid designtiden visas ett valideringsfelmeddelande på sidan **[Formeldesigner](er-advanced-formula-editor.md)** om ingen etikett kan hittas genom att använda det medföljande etikett-ID.

### <a name="language"></a>Språk

`language`: *Sträng*

En sträng som representerar en språkkod.

#### <a name="usage-notes"></a>Användningsanteckningar

Detta argument kan definieras som en textkonstant eller som sökväg för ett datakällfält som returnerar ett *sträng* värde.

> [!NOTE]
> Vid designtiden visas ett valideringsfel om ingen språkkod går att hitta med hjälp av det angivna `language`-argumentet när det har definierats som en textkonstant.
>
> Vid körning returneras översättningen av `EN-US` systemspråket för en angiven etikett om ingen språkkod har hittats med det angivna argumentet `language`.

## <a name="return-values"></a>Returvärden

*Sträng*

Det resulterande textvärdet.

## <a name="example-1-system-label"></a><a name=example-1></a>Exempel 1: Systemetikett

Uttrycken `GETLABELTEXT (@"SYS70894", "en-us")` och `GETLABELTEXT ("SYS70894", "en-us")` returnera den engelska översättningen "Inget att skriva ut" för den `@SYS70894` appetikett.

## <a name="example-2-er-label"></a><a name=example-2></a>Exempel 2: ER-etikett

Du börjar redigera en ER [konfiguration](general-electronic-reporting.md#Configuration) som har [härletts](er-quick-start2-customize-report.md#DeriveProvidedFormat) från **ISO20022 kreditöverföring (DE)** konfiguration, ange en ny datakälla för typen *[Beräknat fält](er-calculated-field-ds-performance.md)* och konfigurrera uttrycket `GETLABELTEXT(@"GER_LABEL:VendorName", "de")` för denna datakälla. I det här fallet, vid körning, returnerar datakällan den tyska översättningen "Kreditorenname" för `@GER_LABEL:VendorName` ER-etikett som ursprungligen konfigurerades i basen **ISO20022 kreditöverföring (DE)** ER-konfiguration.

## <a name="additional-resources"></a>Ytterligare resurser

[Textfunktioner](er-functions-category-text.md)

[Designa flerspråkiga rapporter i elektronisk rapportering](er-design-multilingual-reports.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]