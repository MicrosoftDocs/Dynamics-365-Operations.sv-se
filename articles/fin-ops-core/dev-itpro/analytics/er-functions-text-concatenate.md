---
title: CONCATENATE ER-funktion
description: Det här avsnittet innehåller information om hur funktionen CONCATENATE elektronisk rapportering (ER) används.
author: NickSelin
manager: kfend
ms.date: 12/12/2019
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
ms.openlocfilehash: 6e4800ce44d9da07818acec55c50224a9a000fe6
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/09/2021
ms.locfileid: "5569615"
---
# <a name="concatenate-er-function"></a><span data-ttu-id="7a5ef-103">CONCATENATE ER-funktion</span><span class="sxs-lookup"><span data-stu-id="7a5ef-103">CONCATENATE ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="7a5ef-104">`CONCATENATE`-funktionen returnerar alla angivna textsträngar som ett *sträng*-värde när de har sammanfogas till en sträng.</span><span class="sxs-lookup"><span data-stu-id="7a5ef-104">The `CONCATENATE` function returns all the specified text strings as a *String* value after they have been joined into one string.</span></span>

## <a name="syntax"></a><span data-ttu-id="7a5ef-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="7a5ef-105">Syntax</span></span>

```vb
CONCATENATE (text 1[, text 2, …, text N])
```

## <a name="arguments"></a><span data-ttu-id="7a5ef-106">Argument</span><span class="sxs-lookup"><span data-stu-id="7a5ef-106">Arguments</span></span>

<span data-ttu-id="7a5ef-107">`text 1`: *Sträng*</span><span class="sxs-lookup"><span data-stu-id="7a5ef-107">`text 1`: *String*</span></span>

<span data-ttu-id="7a5ef-108">En referens till en datakälla av datatypen *Sträng*.</span><span class="sxs-lookup"><span data-stu-id="7a5ef-108">A reference to a data source of the *String* data type.</span></span> <span data-ttu-id="7a5ef-109">Detta argument krävs.</span><span class="sxs-lookup"><span data-stu-id="7a5ef-109">This argument is required.</span></span>

<span data-ttu-id="7a5ef-110">`text N`: *Sträng*</span><span class="sxs-lookup"><span data-stu-id="7a5ef-110">`text N`: *String*</span></span>

<span data-ttu-id="7a5ef-111">En referens till en datakälla av datatypen *Sträng*.</span><span class="sxs-lookup"><span data-stu-id="7a5ef-111">A reference to a data source of the *String* data type.</span></span> <span data-ttu-id="7a5ef-112">Dessa ytterligare argument är valfria.</span><span class="sxs-lookup"><span data-stu-id="7a5ef-112">These additional arguments are optional.</span></span>

## <a name="return-values"></a><span data-ttu-id="7a5ef-113">Returvärden</span><span class="sxs-lookup"><span data-stu-id="7a5ef-113">Return values</span></span>

<span data-ttu-id="7a5ef-114">*Sträng*</span><span class="sxs-lookup"><span data-stu-id="7a5ef-114">*String*</span></span>

<span data-ttu-id="7a5ef-115">Det resulterande textvärdet.</span><span class="sxs-lookup"><span data-stu-id="7a5ef-115">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="7a5ef-116">Exempel</span><span class="sxs-lookup"><span data-stu-id="7a5ef-116">Example</span></span>

<span data-ttu-id="7a5ef-117">`CONCATENATE ("abc", "def")` returnerar **"abcdef"**.</span><span class="sxs-lookup"><span data-stu-id="7a5ef-117">`CONCATENATE ("abc", "def")` returns **"abcdef"**.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="7a5ef-118">Användningsanteckningar</span><span class="sxs-lookup"><span data-stu-id="7a5ef-118">Usage notes</span></span>

<span data-ttu-id="7a5ef-119">Uttrycket `"abc" & "def"` returnerar också **"abcdef"**.</span><span class="sxs-lookup"><span data-stu-id="7a5ef-119">The expression `"abc" & "def"` also returns **"abcdef"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="7a5ef-120">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="7a5ef-120">Additional resources</span></span>

[<span data-ttu-id="7a5ef-121">Textfunktioner</span><span class="sxs-lookup"><span data-stu-id="7a5ef-121">Text functions</span></span>](er-functions-category-text.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]