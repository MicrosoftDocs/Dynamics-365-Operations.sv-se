---
title: PADLEFT ER-funktion
description: Det här avsnittet innehåller information om hur funktionen PADLEFT elektronisk rapportering (ER) används.
author: NickSelin
manager: kfend
ms.date: 12/10/2019
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
ms.openlocfilehash: 268941d8bc0bd4dc6de6d2597c05a11c1f530f15
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/05/2020
ms.locfileid: "4680156"
---
# <a name="padleft-er-function"></a><span data-ttu-id="94e65-103">PADLEFT ER-funktion</span><span class="sxs-lookup"><span data-stu-id="94e65-103">PADLEFT ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="94e65-104">`PADLEFT`-funktioner returnerar ett *Sträng*-värde med angiven längd i de fall den aktuella strängens början är utfylld med de angivna tecknen.</span><span class="sxs-lookup"><span data-stu-id="94e65-104">The `PADLEFT` function returns a *String* value of the specified length, where the start of the specified string is padded with the specified characters.</span></span>

## <a name="syntax"></a><span data-ttu-id="94e65-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="94e65-105">Syntax</span></span>

```vb
PADLEFT (text, length, padding chars)
```

## <a name="arguments"></a><span data-ttu-id="94e65-106">Argument</span><span class="sxs-lookup"><span data-stu-id="94e65-106">Arguments</span></span>

<span data-ttu-id="94e65-107">`text`: *Sträng*</span><span class="sxs-lookup"><span data-stu-id="94e65-107">`text`: *String*</span></span>

<span data-ttu-id="94e65-108">Ett *sträng*-värde som representerar den ursprungliga texten.</span><span class="sxs-lookup"><span data-stu-id="94e65-108">A *String* value that represents the original text.</span></span>

<span data-ttu-id="94e65-109">`length`: *Heltal*</span><span class="sxs-lookup"><span data-stu-id="94e65-109">`length`: *Integer*</span></span>

<span data-ttu-id="94e65-110">Ett *heltal*-värde som representerar det sista antalet tecken i den stoppade strängen.</span><span class="sxs-lookup"><span data-stu-id="94e65-110">An *Integer* value that represents the final number of characters in the padded string.</span></span>

<span data-ttu-id="94e65-111">`padding chars`: *Sträng*</span><span class="sxs-lookup"><span data-stu-id="94e65-111">`padding chars`: *String*</span></span>

<span data-ttu-id="94e65-112">De tecken som ska användas för utfyllnad.</span><span class="sxs-lookup"><span data-stu-id="94e65-112">The characters to use for padding.</span></span>

## <a name="return-values"></a><span data-ttu-id="94e65-113">Returvärden</span><span class="sxs-lookup"><span data-stu-id="94e65-113">Return values</span></span>

<span data-ttu-id="94e65-114">*Sträng*</span><span class="sxs-lookup"><span data-stu-id="94e65-114">*String*</span></span>

<span data-ttu-id="94e65-115">Det resulterande textvärdet.</span><span class="sxs-lookup"><span data-stu-id="94e65-115">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="94e65-116">Exempel</span><span class="sxs-lookup"><span data-stu-id="94e65-116">Example</span></span>

<span data-ttu-id="94e65-117">`PADLEFT ("1234", 10, "`&nbsp;`")` returnerar textsträngen **"&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;1234"**.</span><span class="sxs-lookup"><span data-stu-id="94e65-117">`PADLEFT ("1234", 10, "`&nbsp;`")` returns the text string **"&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;1234"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="94e65-118">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="94e65-118">Additional resources</span></span>

[<span data-ttu-id="94e65-119">Textfunktioner</span><span class="sxs-lookup"><span data-stu-id="94e65-119">Text functions</span></span>](er-functions-category-text.md)
