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
ms.search.scope: Core, Operations
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 3f8a8e2006fe279b25bbf154c6e1802babf51117
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/01/2020
ms.locfileid: "3744369"
---
# <a name="padleft-er-function"></a><span data-ttu-id="430b0-103">PADLEFT ER-funktion</span><span class="sxs-lookup"><span data-stu-id="430b0-103">PADLEFT ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="430b0-104">`PADLEFT`-funktioner returnerar ett *Sträng*-värde med angiven längd i de fall den aktuella strängens början är utfylld med de angivna tecknen.</span><span class="sxs-lookup"><span data-stu-id="430b0-104">The `PADLEFT` function returns a *String* value of the specified length, where the start of the specified string is padded with the specified characters.</span></span>

## <a name="syntax"></a><span data-ttu-id="430b0-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="430b0-105">Syntax</span></span>

```vb
PADLEFT (text, length, padding chars)
```

## <a name="arguments"></a><span data-ttu-id="430b0-106">Argument</span><span class="sxs-lookup"><span data-stu-id="430b0-106">Arguments</span></span>

<span data-ttu-id="430b0-107">`text`: *Sträng*</span><span class="sxs-lookup"><span data-stu-id="430b0-107">`text`: *String*</span></span>

<span data-ttu-id="430b0-108">Ett *sträng*-värde som representerar den ursprungliga texten.</span><span class="sxs-lookup"><span data-stu-id="430b0-108">A *String* value that represents the original text.</span></span>

<span data-ttu-id="430b0-109">`length`: *Heltal*</span><span class="sxs-lookup"><span data-stu-id="430b0-109">`length`: *Integer*</span></span>

<span data-ttu-id="430b0-110">Ett *heltal*-värde som representerar det sista antalet tecken i den stoppade strängen.</span><span class="sxs-lookup"><span data-stu-id="430b0-110">An *Integer* value that represents the final number of characters in the padded string.</span></span>

<span data-ttu-id="430b0-111">`padding chars`: *Sträng*</span><span class="sxs-lookup"><span data-stu-id="430b0-111">`padding chars`: *String*</span></span>

<span data-ttu-id="430b0-112">De tecken som ska användas för utfyllnad.</span><span class="sxs-lookup"><span data-stu-id="430b0-112">The characters to use for padding.</span></span>

## <a name="return-values"></a><span data-ttu-id="430b0-113">Returvärden</span><span class="sxs-lookup"><span data-stu-id="430b0-113">Return values</span></span>

<span data-ttu-id="430b0-114">*Sträng*</span><span class="sxs-lookup"><span data-stu-id="430b0-114">*String*</span></span>

<span data-ttu-id="430b0-115">Det resulterande textvärdet.</span><span class="sxs-lookup"><span data-stu-id="430b0-115">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="430b0-116">Exempel</span><span class="sxs-lookup"><span data-stu-id="430b0-116">Example</span></span>

<span data-ttu-id="430b0-117">`PADLEFT ("1234", 10, "`&nbsp;`")` returnerar textsträngen **"&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;1234"**.</span><span class="sxs-lookup"><span data-stu-id="430b0-117">`PADLEFT ("1234", 10, "`&nbsp;`")` returns the text string **"&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;1234"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="430b0-118">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="430b0-118">Additional resources</span></span>

[<span data-ttu-id="430b0-119">Textfunktioner</span><span class="sxs-lookup"><span data-stu-id="430b0-119">Text functions</span></span>](er-functions-category-text.md)
