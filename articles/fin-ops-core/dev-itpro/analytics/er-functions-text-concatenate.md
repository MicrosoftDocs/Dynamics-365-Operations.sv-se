---
title: CONCATENATE ER-funktion
description: Det här avsnittet innehåller information om hur funktionen CONCATENATE elektronisk rapportering (ER) används.
author: NickSelin
manager: kfend
ms.date: 12/12/2019
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
ms.openlocfilehash: 903429994ae5618b597aa0ab0991e9f6783a96ed
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/05/2020
ms.locfileid: "4687948"
---
# <a name="concatenate-er-function"></a><span data-ttu-id="af655-103">CONCATENATE ER-funktion</span><span class="sxs-lookup"><span data-stu-id="af655-103">CONCATENATE ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="af655-104">`CONCATENATE`-funktionen returnerar alla angivna textsträngar som ett *sträng*-värde när de har sammanfogas till en sträng.</span><span class="sxs-lookup"><span data-stu-id="af655-104">The `CONCATENATE` function returns all the specified text strings as a *String* value after they have been joined into one string.</span></span>

## <a name="syntax"></a><span data-ttu-id="af655-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="af655-105">Syntax</span></span>

```vb
CONCATENATE (text 1[, text 2, …, text N])
```

## <a name="arguments"></a><span data-ttu-id="af655-106">Argument</span><span class="sxs-lookup"><span data-stu-id="af655-106">Arguments</span></span>

<span data-ttu-id="af655-107">`text 1`: *Sträng*</span><span class="sxs-lookup"><span data-stu-id="af655-107">`text 1`: *String*</span></span>

<span data-ttu-id="af655-108">En referens till en datakälla av datatypen *Sträng*.</span><span class="sxs-lookup"><span data-stu-id="af655-108">A reference to a data source of the *String* data type.</span></span> <span data-ttu-id="af655-109">Detta argument krävs.</span><span class="sxs-lookup"><span data-stu-id="af655-109">This argument is required.</span></span>

<span data-ttu-id="af655-110">`text N`: *Sträng*</span><span class="sxs-lookup"><span data-stu-id="af655-110">`text N`: *String*</span></span>

<span data-ttu-id="af655-111">En referens till en datakälla av datatypen *Sträng*.</span><span class="sxs-lookup"><span data-stu-id="af655-111">A reference to a data source of the *String* data type.</span></span> <span data-ttu-id="af655-112">Dessa ytterligare argument är valfria.</span><span class="sxs-lookup"><span data-stu-id="af655-112">These additional arguments are optional.</span></span>

## <a name="return-values"></a><span data-ttu-id="af655-113">Returvärden</span><span class="sxs-lookup"><span data-stu-id="af655-113">Return values</span></span>

<span data-ttu-id="af655-114">*Sträng*</span><span class="sxs-lookup"><span data-stu-id="af655-114">*String*</span></span>

<span data-ttu-id="af655-115">Det resulterande textvärdet.</span><span class="sxs-lookup"><span data-stu-id="af655-115">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="af655-116">Exempel</span><span class="sxs-lookup"><span data-stu-id="af655-116">Example</span></span>

<span data-ttu-id="af655-117">`CONCATENATE ("abc", "def")` returnerar **"abcdef"**.</span><span class="sxs-lookup"><span data-stu-id="af655-117">`CONCATENATE ("abc", "def")` returns **"abcdef"**.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="af655-118">Användningsanteckningar</span><span class="sxs-lookup"><span data-stu-id="af655-118">Usage notes</span></span>

<span data-ttu-id="af655-119">Uttrycket `"abc" & "def"` returnerar också **"abcdef"**.</span><span class="sxs-lookup"><span data-stu-id="af655-119">The expression `"abc" & "def"` also returns **"abcdef"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="af655-120">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="af655-120">Additional resources</span></span>

[<span data-ttu-id="af655-121">Textfunktioner</span><span class="sxs-lookup"><span data-stu-id="af655-121">Text functions</span></span>](er-functions-category-text.md)
