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
ms.search.scope: Core, Operations
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6f6f3326c9ca5cdcb3cef52f243d6d3da34251ce
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/20/2019
ms.locfileid: "2915934"
---
# <span data-ttu-id="89074-103"><a name="ISVALIDCHARACTERISO7064">ISVALIDCHARACTERISO7064 ER-funktion</a></span><span class="sxs-lookup"><span data-stu-id="89074-103"><a name="ISVALIDCHARACTERISO7064">ISVALIDCHARACTERISO7064 ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="89074-104">`ISVALIDCHARACTERISO7064`-funktionen returnerar ett *booleskt* värde för **SANT** när en specificerad sträng representerar ett giltigt internationellt bankkontonummer (IBAN).</span><span class="sxs-lookup"><span data-stu-id="89074-104">The `ISVALIDCHARACTERISO7064` function returns a *Boolean* value of **TRUE** if the specified string represents a valid international bank account number (IBAN).</span></span> <span data-ttu-id="89074-105">Annars returnerar uttrycket värdet *boolesk* av **FALSK**.</span><span class="sxs-lookup"><span data-stu-id="89074-105">Otherwise, it returns a *Boolean* value of **FALSE**.</span></span>

## <a name="syntax"></a><span data-ttu-id="89074-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="89074-106">Syntax</span></span>

```
ISVALIDCHARACTERISO7064 (text)
```

## <a name="arguments"></a><span data-ttu-id="89074-107">Argument</span><span class="sxs-lookup"><span data-stu-id="89074-107">Arguments</span></span>

<span data-ttu-id="89074-108">`text`: *Sträng*</span><span class="sxs-lookup"><span data-stu-id="89074-108">`text`: *String*</span></span>

<span data-ttu-id="89074-109">Ett textvärde som representerar ett IBAN.</span><span class="sxs-lookup"><span data-stu-id="89074-109">A text value that represents an IBAN.</span></span>

## <a name="return-values"></a><span data-ttu-id="89074-110">Returvärden</span><span class="sxs-lookup"><span data-stu-id="89074-110">Return values</span></span>

<span data-ttu-id="89074-111">*Sträng*</span><span class="sxs-lookup"><span data-stu-id="89074-111">*String*</span></span>

<span data-ttu-id="89074-112">Det resulterande textvärdet.</span><span class="sxs-lookup"><span data-stu-id="89074-112">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="89074-113">Exempel</span><span class="sxs-lookup"><span data-stu-id="89074-113">Example</span></span>

<span data-ttu-id="89074-114">`ISVALIDCHARACTERISO7064 ("AT61 1904 3002 3457 3201")` returnerar **"SANT**.</span><span class="sxs-lookup"><span data-stu-id="89074-114">`ISVALIDCHARACTERISO7064 ("AT61 1904 3002 3457 3201")` returns **TRUE**.</span></span> 

<span data-ttu-id="89074-115">`ISVALIDCHARACTERISO7064 ("AT61")` returnerar **FALSKT**.</span><span class="sxs-lookup"><span data-stu-id="89074-115">`ISVALIDCHARACTERISO7064 ("AT61")` returns **FALSE**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="89074-116">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="89074-116">Additional resources</span></span>

[<span data-ttu-id="89074-117">Andra (företagsdomänspecifika) funktioner</span><span class="sxs-lookup"><span data-stu-id="89074-117">Other (business domain–specific) functions</span></span>](er-functions-category-other.md)