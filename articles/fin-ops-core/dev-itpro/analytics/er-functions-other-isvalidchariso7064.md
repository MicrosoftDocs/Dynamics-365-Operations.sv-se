---
title: ISVALIDCHARACTERISO7064 ER-funktion
description: Det här avsnittet innehåller information om hur funktionen ISVALIDCHARACTERISO7064 elektronisk rapportering (ER) används.
author: NickSelin
manager: kfend
ms.date: 12/17/2019
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
ms.openlocfilehash: c3bceb15bbe1dc65abc88c1229459707a6166482
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/05/2020
ms.locfileid: "4680672"
---
# <a name="isvalidcharacteriso7064-er-function"></a><span data-ttu-id="dd409-103">ISVALIDCHARACTERISO7064 ER-funktion</span><span class="sxs-lookup"><span data-stu-id="dd409-103">ISVALIDCHARACTERISO7064 ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="dd409-104">`ISVALIDCHARACTERISO7064`-funktionen returnerar ett *booleskt* värde för **SANT** när en specificerad sträng representerar ett giltigt internationellt bankkontonummer (IBAN).</span><span class="sxs-lookup"><span data-stu-id="dd409-104">The `ISVALIDCHARACTERISO7064` function returns a *Boolean* value of **TRUE** if the specified string represents a valid international bank account number (IBAN).</span></span> <span data-ttu-id="dd409-105">Annars returnerar uttrycket värdet *boolesk* av **FALSK**.</span><span class="sxs-lookup"><span data-stu-id="dd409-105">Otherwise, it returns a *Boolean* value of **FALSE**.</span></span>

## <a name="syntax"></a><span data-ttu-id="dd409-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="dd409-106">Syntax</span></span>

```vb
ISVALIDCHARACTERISO7064 (text)
```

## <a name="arguments"></a><span data-ttu-id="dd409-107">Argument</span><span class="sxs-lookup"><span data-stu-id="dd409-107">Arguments</span></span>

<span data-ttu-id="dd409-108">`text`: *Sträng*</span><span class="sxs-lookup"><span data-stu-id="dd409-108">`text`: *String*</span></span>

<span data-ttu-id="dd409-109">Ett textvärde som representerar ett IBAN.</span><span class="sxs-lookup"><span data-stu-id="dd409-109">A text value that represents an IBAN.</span></span>

## <a name="return-values"></a><span data-ttu-id="dd409-110">Returvärden</span><span class="sxs-lookup"><span data-stu-id="dd409-110">Return values</span></span>

<span data-ttu-id="dd409-111">*Sträng*</span><span class="sxs-lookup"><span data-stu-id="dd409-111">*String*</span></span>

<span data-ttu-id="dd409-112">Det resulterande textvärdet.</span><span class="sxs-lookup"><span data-stu-id="dd409-112">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="dd409-113">Exempel</span><span class="sxs-lookup"><span data-stu-id="dd409-113">Example</span></span>

<span data-ttu-id="dd409-114">`ISVALIDCHARACTERISO7064 ("AT61 1904 3002 3457 3201")` returnerar **"SANT**.</span><span class="sxs-lookup"><span data-stu-id="dd409-114">`ISVALIDCHARACTERISO7064 ("AT61 1904 3002 3457 3201")` returns **TRUE**.</span></span> 

<span data-ttu-id="dd409-115">`ISVALIDCHARACTERISO7064 ("AT61")` returnerar **FALSKT**.</span><span class="sxs-lookup"><span data-stu-id="dd409-115">`ISVALIDCHARACTERISO7064 ("AT61")` returns **FALSE**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="dd409-116">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="dd409-116">Additional resources</span></span>

[<span data-ttu-id="dd409-117">Andra (företagsdomänspecifika) funktioner</span><span class="sxs-lookup"><span data-stu-id="dd409-117">Other (business domain–specific) functions</span></span>](er-functions-category-other.md)
