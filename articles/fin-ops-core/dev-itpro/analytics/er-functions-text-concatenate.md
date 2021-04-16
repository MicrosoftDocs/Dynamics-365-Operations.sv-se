---
title: CONCATENATE ER-funktion
description: Det här avsnittet innehåller information om hur funktionen CONCATENATE elektronisk rapportering (ER) används.
author: NickSelin
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
ms.openlocfilehash: f1a47a05127412588f4628cb425eab0379493c3c
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5746493"
---
# <a name="concatenate-er-function"></a><span data-ttu-id="40fd3-103">CONCATENATE ER-funktion</span><span class="sxs-lookup"><span data-stu-id="40fd3-103">CONCATENATE ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="40fd3-104">`CONCATENATE`-funktionen returnerar alla angivna textsträngar som ett *sträng*-värde när de har sammanfogas till en sträng.</span><span class="sxs-lookup"><span data-stu-id="40fd3-104">The `CONCATENATE` function returns all the specified text strings as a *String* value after they have been joined into one string.</span></span>

## <a name="syntax"></a><span data-ttu-id="40fd3-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="40fd3-105">Syntax</span></span>

```vb
CONCATENATE (text 1[, text 2, …, text N])
```

## <a name="arguments"></a><span data-ttu-id="40fd3-106">Argument</span><span class="sxs-lookup"><span data-stu-id="40fd3-106">Arguments</span></span>

<span data-ttu-id="40fd3-107">`text 1`: *Sträng*</span><span class="sxs-lookup"><span data-stu-id="40fd3-107">`text 1`: *String*</span></span>

<span data-ttu-id="40fd3-108">En referens till en datakälla av datatypen *Sträng*.</span><span class="sxs-lookup"><span data-stu-id="40fd3-108">A reference to a data source of the *String* data type.</span></span> <span data-ttu-id="40fd3-109">Detta argument krävs.</span><span class="sxs-lookup"><span data-stu-id="40fd3-109">This argument is required.</span></span>

<span data-ttu-id="40fd3-110">`text N`: *Sträng*</span><span class="sxs-lookup"><span data-stu-id="40fd3-110">`text N`: *String*</span></span>

<span data-ttu-id="40fd3-111">En referens till en datakälla av datatypen *Sträng*.</span><span class="sxs-lookup"><span data-stu-id="40fd3-111">A reference to a data source of the *String* data type.</span></span> <span data-ttu-id="40fd3-112">Dessa ytterligare argument är valfria.</span><span class="sxs-lookup"><span data-stu-id="40fd3-112">These additional arguments are optional.</span></span>

## <a name="return-values"></a><span data-ttu-id="40fd3-113">Returvärden</span><span class="sxs-lookup"><span data-stu-id="40fd3-113">Return values</span></span>

<span data-ttu-id="40fd3-114">*Sträng*</span><span class="sxs-lookup"><span data-stu-id="40fd3-114">*String*</span></span>

<span data-ttu-id="40fd3-115">Det resulterande textvärdet.</span><span class="sxs-lookup"><span data-stu-id="40fd3-115">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="40fd3-116">Exempel</span><span class="sxs-lookup"><span data-stu-id="40fd3-116">Example</span></span>

<span data-ttu-id="40fd3-117">`CONCATENATE ("abc", "def")` returnerar **"abcdef"**.</span><span class="sxs-lookup"><span data-stu-id="40fd3-117">`CONCATENATE ("abc", "def")` returns **"abcdef"**.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="40fd3-118">Användningsanteckningar</span><span class="sxs-lookup"><span data-stu-id="40fd3-118">Usage notes</span></span>

<span data-ttu-id="40fd3-119">Uttrycket `"abc" & "def"` returnerar också **"abcdef"**.</span><span class="sxs-lookup"><span data-stu-id="40fd3-119">The expression `"abc" & "def"` also returns **"abcdef"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="40fd3-120">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="40fd3-120">Additional resources</span></span>

[<span data-ttu-id="40fd3-121">Textfunktioner</span><span class="sxs-lookup"><span data-stu-id="40fd3-121">Text functions</span></span>](er-functions-category-text.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]