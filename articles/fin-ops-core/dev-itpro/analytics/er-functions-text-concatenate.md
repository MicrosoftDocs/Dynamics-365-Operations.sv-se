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
ms.search.scope: Core, Operations
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 04c7b32e2a9578f8864570a552817ec3ce28fa43
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/12/2020
ms.locfileid: "3041200"
---
# <span data-ttu-id="ada64-103"><a name="CONCATENATE">CONCATENATE ER-funktion</a></span><span class="sxs-lookup"><span data-stu-id="ada64-103"><a name="CONCATENATE">CONCATENATE ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="ada64-104">`CONCATENATE`-funktionen returnerar alla angivna textsträngar som ett *sträng*-värde när de har sammanfogas till en sträng.</span><span class="sxs-lookup"><span data-stu-id="ada64-104">The `CONCATENATE` function returns all the specified text strings as a *String* value after they have been joined into one string.</span></span>

## <a name="syntax"></a><span data-ttu-id="ada64-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="ada64-105">Syntax</span></span>

```vb
CONCATENATE (text 1[, text 2, …, text N])
```

## <a name="arguments"></a><span data-ttu-id="ada64-106">Argument</span><span class="sxs-lookup"><span data-stu-id="ada64-106">Arguments</span></span>

<span data-ttu-id="ada64-107">`text 1`: *Sträng*</span><span class="sxs-lookup"><span data-stu-id="ada64-107">`text 1`: *String*</span></span>

<span data-ttu-id="ada64-108">En referens till en datakälla av datatypen *Sträng*.</span><span class="sxs-lookup"><span data-stu-id="ada64-108">A reference to a data source of the *String* data type.</span></span> <span data-ttu-id="ada64-109">Detta argument krävs.</span><span class="sxs-lookup"><span data-stu-id="ada64-109">This argument is required.</span></span>

<span data-ttu-id="ada64-110">`text N`: *Sträng*</span><span class="sxs-lookup"><span data-stu-id="ada64-110">`text N`: *String*</span></span>

<span data-ttu-id="ada64-111">En referens till en datakälla av datatypen *Sträng*.</span><span class="sxs-lookup"><span data-stu-id="ada64-111">A reference to a data source of the *String* data type.</span></span> <span data-ttu-id="ada64-112">Dessa ytterligare argument är valfria.</span><span class="sxs-lookup"><span data-stu-id="ada64-112">These additional arguments are optional.</span></span>

## <a name="return-values"></a><span data-ttu-id="ada64-113">Returvärden</span><span class="sxs-lookup"><span data-stu-id="ada64-113">Return values</span></span>

<span data-ttu-id="ada64-114">*Sträng*</span><span class="sxs-lookup"><span data-stu-id="ada64-114">*String*</span></span>

<span data-ttu-id="ada64-115">Det resulterande textvärdet.</span><span class="sxs-lookup"><span data-stu-id="ada64-115">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="ada64-116">Exempel</span><span class="sxs-lookup"><span data-stu-id="ada64-116">Example</span></span>

<span data-ttu-id="ada64-117">`CONCATENATE ("abc", "def")` returnerar **"abcdef"**.</span><span class="sxs-lookup"><span data-stu-id="ada64-117">`CONCATENATE ("abc", "def")` returns **"abcdef"**.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="ada64-118">Användningsanteckningar</span><span class="sxs-lookup"><span data-stu-id="ada64-118">Usage notes</span></span>

<span data-ttu-id="ada64-119">Uttrycket `"abc" & "def"` returnerar också **"abcdef"**.</span><span class="sxs-lookup"><span data-stu-id="ada64-119">The expression `"abc" & "def"` also returns **"abcdef"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="ada64-120">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="ada64-120">Additional resources</span></span>

[<span data-ttu-id="ada64-121">Textfunktioner</span><span class="sxs-lookup"><span data-stu-id="ada64-121">Text functions</span></span>](er-functions-category-text.md)
