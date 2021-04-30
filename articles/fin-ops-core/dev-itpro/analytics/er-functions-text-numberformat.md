---
title: Funktionen NUMBERFORMAT ER
description: Det här avsnittet innehåller information om hur funktionen NUMBERFORMAT elektronisk rapportering (ER) används.
author: NickSelin
ms.date: 12/10/2019
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
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4a383b3f7c0ca7c4e5afc609cc8a7b1b07021b02
ms.sourcegitcommit: 951393b05bf409333cb3c7ad977bcaa804aa801b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/13/2021
ms.locfileid: "5890393"
---
# <a name="numberformat-er-function"></a><span data-ttu-id="3cc10-103">Funktionen NUMBERFORMAT ER</span><span class="sxs-lookup"><span data-stu-id="3cc10-103">NUMBERFORMAT ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="3cc10-104">`NUMBERFORMAT`-funktionen returnerar ett värde för *Sträng* som visar det angivna numret i det angivna formatet och i en valfri angiven [kultur](/bingmaps/rest-services/common-parameters-and-types/supported-culture-codes).</span><span class="sxs-lookup"><span data-stu-id="3cc10-104">The `NUMBERFORMAT` function returns a *String* value that presents the specified number in the specified format and in an optionally specified [culture](/bingmaps/rest-services/common-parameters-and-types/supported-culture-codes).</span></span> <span data-ttu-id="3cc10-105">Om du vill ha mer information om format som stöds, se [Standard](/dotnet/standard/base-types/standard-numeric-format-strings) och [Anpassat](/dotnet/standard/base-types/custom-numeric-format-strings).</span><span class="sxs-lookup"><span data-stu-id="3cc10-105">For information about the supported formats, see [standard](/dotnet/standard/base-types/standard-numeric-format-strings) and [custom](/dotnet/standard/base-types/custom-numeric-format-strings).</span></span>

## <a name="syntax-1"></a><span data-ttu-id="3cc10-106">Syntax 1</span><span class="sxs-lookup"><span data-stu-id="3cc10-106">Syntax 1</span></span>

```vb
NUMBERFORMAT (number, format)
```

## <a name="syntax-2"></a><span data-ttu-id="3cc10-107">Syntax 2</span><span class="sxs-lookup"><span data-stu-id="3cc10-107">Syntax 2</span></span>

```vb
NUMBERFORMAT (number, format, culture)
```

## <a name="arguments"></a><span data-ttu-id="3cc10-108">Argument</span><span class="sxs-lookup"><span data-stu-id="3cc10-108">Arguments</span></span>

<span data-ttu-id="3cc10-109">`number`: *Heltal* eller *Realtal*</span><span class="sxs-lookup"><span data-stu-id="3cc10-109">`number`: *Integer* or *Real*</span></span>

<span data-ttu-id="3cc10-110">Ett numeriskt värde som anger det tal som måste formateras.</span><span class="sxs-lookup"><span data-stu-id="3cc10-110">A numeric value that specifies the number that must be formatted.</span></span>

<span data-ttu-id="3cc10-111">`format`: *Sträng*</span><span class="sxs-lookup"><span data-stu-id="3cc10-111">`format` : *String*</span></span>

<span data-ttu-id="3cc10-112">Ett *sträng*-värde som representerar det formatet.</span><span class="sxs-lookup"><span data-stu-id="3cc10-112">A *String* value that represents the format.</span></span>

<span data-ttu-id="3cc10-113">`culture`: *Sträng*</span><span class="sxs-lookup"><span data-stu-id="3cc10-113">`culture`: *String*</span></span>

<span data-ttu-id="3cc10-114">Ett *sträng* värde som representerar kulturen som ska användas för formatering.</span><span class="sxs-lookup"><span data-stu-id="3cc10-114">A *String* value that represents the culture to use for formatting.</span></span>

## <a name="return-values"></a><span data-ttu-id="3cc10-115">Returvärden</span><span class="sxs-lookup"><span data-stu-id="3cc10-115">Return values</span></span>

<span data-ttu-id="3cc10-116">*Sträng*</span><span class="sxs-lookup"><span data-stu-id="3cc10-116">*String*</span></span>

<span data-ttu-id="3cc10-117">Det resulterande textvärdet.</span><span class="sxs-lookup"><span data-stu-id="3cc10-117">The resulting text value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="3cc10-118">Användningsanteckningar</span><span class="sxs-lookup"><span data-stu-id="3cc10-118">Usage notes</span></span>

<span data-ttu-id="3cc10-119">Om kulturen inte definieras som ett argument för den anropade funktionen, avgör kontexten som den här funktionen körs i den kultur som används för att formatera tal.</span><span class="sxs-lookup"><span data-stu-id="3cc10-119">If the culture isn't defined as an argument of the called function, the context that this function is run in determines the culture that is used to format numbers.</span></span>

## <a name="example-1"></a><span data-ttu-id="3cc10-120">Exempel 1</span><span class="sxs-lookup"><span data-stu-id="3cc10-120">Example 1</span></span>

<span data-ttu-id="3cc10-121">För en **EN-US**-kultur returnerar `NUMBERFORMAT (0.45, "p")` **"45,00 %"** och `NUMBERFORMAT (10.45, "#")` returnerar **"10"**.</span><span class="sxs-lookup"><span data-stu-id="3cc10-121">For the **EN-US** culture, `NUMBERFORMAT (0.45, "p")` returns **"45.00 %"**, and `NUMBERFORMAT (10.45, "#")` returns **"10"**.</span></span>

## <a name="example-2"></a><span data-ttu-id="3cc10-122">Exempel 2</span><span class="sxs-lookup"><span data-stu-id="3cc10-122">Example 2</span></span>

<span data-ttu-id="3cc10-123">`NUMBERFORMAT (10/3, "F2", "de")` returnerar **3,33**, medan `NUMBERFORMAT (10/3, "F2", "en-us")` returnerar **3,33**.</span><span class="sxs-lookup"><span data-stu-id="3cc10-123">`NUMBERFORMAT (10/3, "F2", "de")` returns **3,33**, whereas `NUMBERFORMAT (10/3, "F2", "en-us")` returns **3.33**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="3cc10-124">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="3cc10-124">Additional resources</span></span>

[<span data-ttu-id="3cc10-125">Textfunktioner</span><span class="sxs-lookup"><span data-stu-id="3cc10-125">Text functions</span></span>](er-functions-category-text.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]