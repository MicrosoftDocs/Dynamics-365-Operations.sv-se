---
title: Funktionen NUMBERFORMAT ER
description: Det här avsnittet innehåller information om hur funktionen NUMBERFORMAT elektronisk rapportering (ER) används.
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
ms.openlocfilehash: 392135abaf7db05d5ac591ab56312a0e0f6ae5ff
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/20/2019
ms.locfileid: "2916808"
---
# <span data-ttu-id="93a4d-103"><a name="NUMBERFORMAT">Funktionen NUMBERFORMAT ER</a></span><span class="sxs-lookup"><span data-stu-id="93a4d-103"><a name="NUMBERFORMAT">NUMBERFORMAT ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="93a4d-104">`NUMBERFORMAT`-funktionen returnerar ett värde för *Sträng* som visar det angivna numret i det angivna formatet och i en valfri angiven [kultur](https://docs.microsoft.com/bingmaps/rest-services/common-parameters-and-types/supported-culture-codes).</span><span class="sxs-lookup"><span data-stu-id="93a4d-104">The `NUMBERFORMAT` function returns a *String* value that presents the specified number in the specified format and in an optionally specified [culture](https://docs.microsoft.com/bingmaps/rest-services/common-parameters-and-types/supported-culture-codes).</span></span> <span data-ttu-id="93a4d-105">Om du vill ha mer information om format som stöds, se [Standard](https://msdn.microsoft.com/library/dwhawy9k(v=vs.110).aspx) och [Anpassat](https://msdn.microsoft.com/library/0c899ak8(v=vs.110).aspx).</span><span class="sxs-lookup"><span data-stu-id="93a4d-105">For information about the supported formats, see [standard](https://msdn.microsoft.com/library/dwhawy9k(v=vs.110).aspx) and [custom](https://msdn.microsoft.com/library/0c899ak8(v=vs.110).aspx).</span></span>

## <a name="syntax-1"></a><span data-ttu-id="93a4d-106">Syntax 1</span><span class="sxs-lookup"><span data-stu-id="93a4d-106">Syntax 1</span></span>

```
NUMBERFORMAT (number, format)
```

## <a name="syntax-2"></a><span data-ttu-id="93a4d-107">Syntax 2</span><span class="sxs-lookup"><span data-stu-id="93a4d-107">Syntax 2</span></span>

```
NUMBERFORMAT (number, format, culture)
```

## <a name="arguments"></a><span data-ttu-id="93a4d-108">Argument</span><span class="sxs-lookup"><span data-stu-id="93a4d-108">Arguments</span></span>

<span data-ttu-id="93a4d-109">`number`: *Heltal* eller *Realtal*</span><span class="sxs-lookup"><span data-stu-id="93a4d-109">`number`: *Integer* or *Real*</span></span>

<span data-ttu-id="93a4d-110">Ett numeriskt värde som anger det tal som måste formateras.</span><span class="sxs-lookup"><span data-stu-id="93a4d-110">A numeric value that specifies the number that must be formatted.</span></span>

<span data-ttu-id="93a4d-111">`format`: *Sträng*</span><span class="sxs-lookup"><span data-stu-id="93a4d-111">`format` : *String*</span></span>

<span data-ttu-id="93a4d-112">Ett *sträng*-värde som representerar det formatet.</span><span class="sxs-lookup"><span data-stu-id="93a4d-112">A *String* value that represents the format.</span></span>

<span data-ttu-id="93a4d-113">`culture`: *Sträng*</span><span class="sxs-lookup"><span data-stu-id="93a4d-113">`culture`: *String*</span></span>

<span data-ttu-id="93a4d-114">Ett *sträng* värde som representerar kulturen som ska användas för formatering.</span><span class="sxs-lookup"><span data-stu-id="93a4d-114">A *String* value that represents the culture to use for formatting.</span></span>

## <a name="return-values"></a><span data-ttu-id="93a4d-115">Returvärden</span><span class="sxs-lookup"><span data-stu-id="93a4d-115">Return values</span></span>

<span data-ttu-id="93a4d-116">*Sträng*</span><span class="sxs-lookup"><span data-stu-id="93a4d-116">*String*</span></span>

<span data-ttu-id="93a4d-117">Det resulterande textvärdet.</span><span class="sxs-lookup"><span data-stu-id="93a4d-117">The resulting text value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="93a4d-118">Användningsanteckningar</span><span class="sxs-lookup"><span data-stu-id="93a4d-118">Usage notes</span></span>

<span data-ttu-id="93a4d-119">Om kulturen inte definieras som ett argument för den anropade funktionen, avgör kontexten som den här funktionen körs i den kultur som används för att formatera tal.</span><span class="sxs-lookup"><span data-stu-id="93a4d-119">If the culture isn't defined as an argument of the called function, the context that this function is run in determines the culture that is used to format numbers.</span></span>

## <a name="example-1"></a><span data-ttu-id="93a4d-120">Exempel 1</span><span class="sxs-lookup"><span data-stu-id="93a4d-120">Example 1</span></span>

<span data-ttu-id="93a4d-121">För en **EN-US**-kultur returnerar `NUMBERFORMAT (0.45, "p")` **"45,00 %"** och `NUMBERFORMAT (10.45, "#")` returnerar **"10"**.</span><span class="sxs-lookup"><span data-stu-id="93a4d-121">For the **EN-US** culture, `NUMBERFORMAT (0.45, "p")` returns **"45.00 %"**, and `NUMBERFORMAT (10.45, "#")` returns **"10"**.</span></span>

## <a name="example-2"></a><span data-ttu-id="93a4d-122">Exempel 2</span><span class="sxs-lookup"><span data-stu-id="93a4d-122">Example 2</span></span>

<span data-ttu-id="93a4d-123">`NUMBERFORMAT (10/3, "F2", "de")` returnerar **3,33**, medan `NUMBERFORMAT (10/3, "F2", "en-us")` returnerar **3,33**.</span><span class="sxs-lookup"><span data-stu-id="93a4d-123">`NUMBERFORMAT (10/3, "F2", "de")` returns **3,33**, whereas `NUMBERFORMAT (10/3, "F2", "en-us")` returns **3.33**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="93a4d-124">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="93a4d-124">Additional resources</span></span>

[<span data-ttu-id="93a4d-125">Textfunktioner</span><span class="sxs-lookup"><span data-stu-id="93a4d-125">Text functions</span></span>](er-functions-category-text.md)