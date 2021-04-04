---
title: NUMBERVALUE ER-funktion
description: Det här avsnittet innehåller information om hur funktionen NUMBERVALUE elektronisk rapportering (ER) används.
author: NickSelin
manager: kfend
ms.date: 12/05/2019
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
ms.openlocfilehash: f542621c4bcc29e03d8c92b0c700e2c80c9846f6
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/09/2021
ms.locfileid: "5561432"
---
# <a name="numbervalue-er-function"></a><span data-ttu-id="e4e08-103">NUMBERVALUE ER-funktion</span><span class="sxs-lookup"><span data-stu-id="e4e08-103">NUMBERVALUE ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="e4e08-104">`NUMBERVALUE`-funktionen returnerar ett *verkligt* värde som konverteras från den angivna värdet *strängen*.</span><span class="sxs-lookup"><span data-stu-id="e4e08-104">The `NUMBERVALUE` function returns a *Real* value that is converted from the specified *String* value.</span></span> <span data-ttu-id="e4e08-105">Under konverteringen beaktas de angivna decimal- och siffergrupperingsavgränsarna.</span><span class="sxs-lookup"><span data-stu-id="e4e08-105">During the conversion, the specified decimal and digit grouping separators are considered.</span></span>

## <a name="syntax"></a><span data-ttu-id="e4e08-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="e4e08-106">Syntax</span></span>

```vb
NUMBERVALUE (text, decimal separator, digit grouping separator)
```

## <a name="arguments"></a><span data-ttu-id="e4e08-107">Argument</span><span class="sxs-lookup"><span data-stu-id="e4e08-107">Arguments</span></span>

<span data-ttu-id="e4e08-108">`text`: *Sträng*</span><span class="sxs-lookup"><span data-stu-id="e4e08-108">`text`: *String*</span></span>

<span data-ttu-id="e4e08-109">Ett textvärde som måste konverteras till ett *Realtal*-nummer.</span><span class="sxs-lookup"><span data-stu-id="e4e08-109">A text value that must be converted to a *Real* number.</span></span>

<span data-ttu-id="e4e08-110">`decimal separator`: Sträng</span><span class="sxs-lookup"><span data-stu-id="e4e08-110">`decimal separator`: String</span></span>

<span data-ttu-id="e4e08-111">En decimalavgränsare.</span><span class="sxs-lookup"><span data-stu-id="e4e08-111">A decimal separator.</span></span> <span data-ttu-id="e4e08-112">Det används för att separera heltal och fraktionerad delar av ett decimaltal.</span><span class="sxs-lookup"><span data-stu-id="e4e08-112">It's used to separate the integer and fractional parts of a decimal number.</span></span>

<span data-ttu-id="e4e08-113">`digit grouping separator`: *Sträng*</span><span class="sxs-lookup"><span data-stu-id="e4e08-113">`digit grouping separator`: *String*</span></span>

<span data-ttu-id="e4e08-114">En siffergrupperingsavgränsare.</span><span class="sxs-lookup"><span data-stu-id="e4e08-114">A digit grouping separator.</span></span> <span data-ttu-id="e4e08-115">Den används som tusentalsavgränsare.</span><span class="sxs-lookup"><span data-stu-id="e4e08-115">It's used as the thousands separator.</span></span>

## <a name="return-values"></a><span data-ttu-id="e4e08-116">Returvärden</span><span class="sxs-lookup"><span data-stu-id="e4e08-116">Return values</span></span>

<span data-ttu-id="e4e08-117">*Realtal*</span><span class="sxs-lookup"><span data-stu-id="e4e08-117">*Real*</span></span>

<span data-ttu-id="e4e08-118">Det resulterande numeriska värdet.</span><span class="sxs-lookup"><span data-stu-id="e4e08-118">The resulting numeric value.</span></span>

## <a name="example"></a><span data-ttu-id="e4e08-119">Exempel</span><span class="sxs-lookup"><span data-stu-id="e4e08-119">Example</span></span>

<span data-ttu-id="e4e08-120">`NUMBERVALUE( "1 234,56", ",", " ")` returnerar **1234.56**.</span><span class="sxs-lookup"><span data-stu-id="e4e08-120">`NUMBERVALUE( "1 234,56", ",", " ")` returns **1234.56**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="e4e08-121">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="e4e08-121">Additional resources</span></span>

[<span data-ttu-id="e4e08-122">Funktioner för typkonvertering</span><span class="sxs-lookup"><span data-stu-id="e4e08-122">Type conversion functions</span></span>](er-functions-category-type-conversion.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]