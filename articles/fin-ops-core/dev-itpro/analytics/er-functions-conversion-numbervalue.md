---
title: NUMBERVALUE ER-funktion
description: Det här avsnittet innehåller information om hur funktionen NUMBERVALUE elektronisk rapportering (ER) används.
author: NickSelin
manager: kfend
ms.date: 12/05/2019
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
ms.openlocfilehash: 80f0606dc3842cdfa56d41e2815eccd7518218b8
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/20/2019
ms.locfileid: "2916532"
---
# <span data-ttu-id="2c19b-103"><a name="NUMBERVALUE">NUMBERVALUE ER-funktion</a></span><span class="sxs-lookup"><span data-stu-id="2c19b-103"><a name="NUMBERVALUE">NUMBERVALUE ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="2c19b-104">`NUMBERVALUE`-funktionen returnerar ett *verkligt* värde som konverteras från den angivna värdet *strängen*.</span><span class="sxs-lookup"><span data-stu-id="2c19b-104">The `NUMBERVALUE` function returns a *Real* value that is converted from the specified *String* value.</span></span> <span data-ttu-id="2c19b-105">Under konverteringen beaktas de angivna decimal- och siffergrupperingsavgränsarna.</span><span class="sxs-lookup"><span data-stu-id="2c19b-105">During the conversion, the specified decimal and digit grouping separators are considered.</span></span>

## <a name="syntax"></a><span data-ttu-id="2c19b-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="2c19b-106">Syntax</span></span>

```
NUMBERVALUE (text, decimal separator, digit grouping separator)
```

## <a name="arguments"></a><span data-ttu-id="2c19b-107">Argument</span><span class="sxs-lookup"><span data-stu-id="2c19b-107">Arguments</span></span>

<span data-ttu-id="2c19b-108">`text`: *Sträng*</span><span class="sxs-lookup"><span data-stu-id="2c19b-108">`text`: *String*</span></span>

<span data-ttu-id="2c19b-109">Ett textvärde som måste konverteras till ett *Realtal*-nummer.</span><span class="sxs-lookup"><span data-stu-id="2c19b-109">A text value that must be converted to a *Real* number.</span></span>

<span data-ttu-id="2c19b-110">`decimal separator`: Sträng</span><span class="sxs-lookup"><span data-stu-id="2c19b-110">`decimal separator`: String</span></span>

<span data-ttu-id="2c19b-111">En decimalavgränsare.</span><span class="sxs-lookup"><span data-stu-id="2c19b-111">A decimal separator.</span></span> <span data-ttu-id="2c19b-112">Det används för att separera heltal och fraktionerad delar av ett decimaltal.</span><span class="sxs-lookup"><span data-stu-id="2c19b-112">It's used to separate the integer and fractional parts of a decimal number.</span></span>

<span data-ttu-id="2c19b-113">`digit grouping separator`: *Sträng*</span><span class="sxs-lookup"><span data-stu-id="2c19b-113">`digit grouping separator`: *String*</span></span>

<span data-ttu-id="2c19b-114">En siffergrupperingsavgränsare.</span><span class="sxs-lookup"><span data-stu-id="2c19b-114">A digit grouping separator.</span></span> <span data-ttu-id="2c19b-115">Den används som tusentalsavgränsare.</span><span class="sxs-lookup"><span data-stu-id="2c19b-115">It's used as the thousands separator.</span></span>

## <a name="return-values"></a><span data-ttu-id="2c19b-116">Returvärden</span><span class="sxs-lookup"><span data-stu-id="2c19b-116">Return values</span></span>

<span data-ttu-id="2c19b-117">*Realtal*</span><span class="sxs-lookup"><span data-stu-id="2c19b-117">*Real*</span></span>

<span data-ttu-id="2c19b-118">Det resulterande numeriska värdet.</span><span class="sxs-lookup"><span data-stu-id="2c19b-118">The resulting numeric value.</span></span>

## <a name="example"></a><span data-ttu-id="2c19b-119">Exempel</span><span class="sxs-lookup"><span data-stu-id="2c19b-119">Example</span></span>

<span data-ttu-id="2c19b-120">`NUMBERVALUE( "1 234,56", ",", " ")` returnerar **1234.56**.</span><span class="sxs-lookup"><span data-stu-id="2c19b-120">`NUMBERVALUE( "1 234,56", ",", " ")` returns **1234.56**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="2c19b-121">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="2c19b-121">Additional resources</span></span>

[<span data-ttu-id="2c19b-122">Funktioner för typkonvertering</span><span class="sxs-lookup"><span data-stu-id="2c19b-122">Type conversion functions</span></span>](er-functions-category-type-conversion.md)