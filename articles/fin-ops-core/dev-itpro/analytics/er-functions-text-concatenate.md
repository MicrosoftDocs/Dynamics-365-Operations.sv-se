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
ms.openlocfilehash: 1a21140e5636ebd96eca4be90308c915e77510e1
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/01/2020
ms.locfileid: "3743913"
---
# <a name="concatenate-er-function"></a><span data-ttu-id="0bf49-103">CONCATENATE ER-funktion</span><span class="sxs-lookup"><span data-stu-id="0bf49-103">CONCATENATE ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="0bf49-104">`CONCATENATE`-funktionen returnerar alla angivna textsträngar som ett *sträng*-värde när de har sammanfogas till en sträng.</span><span class="sxs-lookup"><span data-stu-id="0bf49-104">The `CONCATENATE` function returns all the specified text strings as a *String* value after they have been joined into one string.</span></span>

## <a name="syntax"></a><span data-ttu-id="0bf49-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="0bf49-105">Syntax</span></span>

```vb
CONCATENATE (text 1[, text 2, …, text N])
```

## <a name="arguments"></a><span data-ttu-id="0bf49-106">Argument</span><span class="sxs-lookup"><span data-stu-id="0bf49-106">Arguments</span></span>

<span data-ttu-id="0bf49-107">`text 1`: *Sträng*</span><span class="sxs-lookup"><span data-stu-id="0bf49-107">`text 1`: *String*</span></span>

<span data-ttu-id="0bf49-108">En referens till en datakälla av datatypen *Sträng*.</span><span class="sxs-lookup"><span data-stu-id="0bf49-108">A reference to a data source of the *String* data type.</span></span> <span data-ttu-id="0bf49-109">Detta argument krävs.</span><span class="sxs-lookup"><span data-stu-id="0bf49-109">This argument is required.</span></span>

<span data-ttu-id="0bf49-110">`text N`: *Sträng*</span><span class="sxs-lookup"><span data-stu-id="0bf49-110">`text N`: *String*</span></span>

<span data-ttu-id="0bf49-111">En referens till en datakälla av datatypen *Sträng*.</span><span class="sxs-lookup"><span data-stu-id="0bf49-111">A reference to a data source of the *String* data type.</span></span> <span data-ttu-id="0bf49-112">Dessa ytterligare argument är valfria.</span><span class="sxs-lookup"><span data-stu-id="0bf49-112">These additional arguments are optional.</span></span>

## <a name="return-values"></a><span data-ttu-id="0bf49-113">Returvärden</span><span class="sxs-lookup"><span data-stu-id="0bf49-113">Return values</span></span>

<span data-ttu-id="0bf49-114">*Sträng*</span><span class="sxs-lookup"><span data-stu-id="0bf49-114">*String*</span></span>

<span data-ttu-id="0bf49-115">Det resulterande textvärdet.</span><span class="sxs-lookup"><span data-stu-id="0bf49-115">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="0bf49-116">Exempel</span><span class="sxs-lookup"><span data-stu-id="0bf49-116">Example</span></span>

<span data-ttu-id="0bf49-117">`CONCATENATE ("abc", "def")` returnerar **"abcdef"**.</span><span class="sxs-lookup"><span data-stu-id="0bf49-117">`CONCATENATE ("abc", "def")` returns **"abcdef"**.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="0bf49-118">Användningsanteckningar</span><span class="sxs-lookup"><span data-stu-id="0bf49-118">Usage notes</span></span>

<span data-ttu-id="0bf49-119">Uttrycket `"abc" & "def"` returnerar också **"abcdef"**.</span><span class="sxs-lookup"><span data-stu-id="0bf49-119">The expression `"abc" & "def"` also returns **"abcdef"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="0bf49-120">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="0bf49-120">Additional resources</span></span>

[<span data-ttu-id="0bf49-121">Textfunktioner</span><span class="sxs-lookup"><span data-stu-id="0bf49-121">Text functions</span></span>](er-functions-category-text.md)
