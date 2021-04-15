---
title: ISVALIDCHARACTERISO7064 ER-funktion
description: Det här avsnittet innehåller information om hur funktionen ISVALIDCHARACTERISO7064 elektronisk rapportering (ER) används.
author: NickSelin
ms.date: 12/17/2019
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
ms.openlocfilehash: 1f102a6a3eafe3b066101370b94fa2f17ad3ad8b
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5748303"
---
# <a name="isvalidcharacteriso7064-er-function"></a><span data-ttu-id="6da66-103">ISVALIDCHARACTERISO7064 ER-funktion</span><span class="sxs-lookup"><span data-stu-id="6da66-103">ISVALIDCHARACTERISO7064 ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="6da66-104">`ISVALIDCHARACTERISO7064`-funktionen returnerar ett *booleskt* värde för **SANT** när en specificerad sträng representerar ett giltigt internationellt bankkontonummer (IBAN).</span><span class="sxs-lookup"><span data-stu-id="6da66-104">The `ISVALIDCHARACTERISO7064` function returns a *Boolean* value of **TRUE** if the specified string represents a valid international bank account number (IBAN).</span></span> <span data-ttu-id="6da66-105">Annars returnerar uttrycket värdet *boolesk* av **FALSK**.</span><span class="sxs-lookup"><span data-stu-id="6da66-105">Otherwise, it returns a *Boolean* value of **FALSE**.</span></span>

## <a name="syntax"></a><span data-ttu-id="6da66-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="6da66-106">Syntax</span></span>

```vb
ISVALIDCHARACTERISO7064 (text)
```

## <a name="arguments"></a><span data-ttu-id="6da66-107">Argument</span><span class="sxs-lookup"><span data-stu-id="6da66-107">Arguments</span></span>

<span data-ttu-id="6da66-108">`text`: *Sträng*</span><span class="sxs-lookup"><span data-stu-id="6da66-108">`text`: *String*</span></span>

<span data-ttu-id="6da66-109">Ett textvärde som representerar ett IBAN.</span><span class="sxs-lookup"><span data-stu-id="6da66-109">A text value that represents an IBAN.</span></span>

## <a name="return-values"></a><span data-ttu-id="6da66-110">Returvärden</span><span class="sxs-lookup"><span data-stu-id="6da66-110">Return values</span></span>

<span data-ttu-id="6da66-111">*Sträng*</span><span class="sxs-lookup"><span data-stu-id="6da66-111">*String*</span></span>

<span data-ttu-id="6da66-112">Det resulterande textvärdet.</span><span class="sxs-lookup"><span data-stu-id="6da66-112">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="6da66-113">Exempel</span><span class="sxs-lookup"><span data-stu-id="6da66-113">Example</span></span>

<span data-ttu-id="6da66-114">`ISVALIDCHARACTERISO7064 ("AT61 1904 3002 3457 3201")` returnerar **"SANT**.</span><span class="sxs-lookup"><span data-stu-id="6da66-114">`ISVALIDCHARACTERISO7064 ("AT61 1904 3002 3457 3201")` returns **TRUE**.</span></span> 

<span data-ttu-id="6da66-115">`ISVALIDCHARACTERISO7064 ("AT61")` returnerar **FALSKT**.</span><span class="sxs-lookup"><span data-stu-id="6da66-115">`ISVALIDCHARACTERISO7064 ("AT61")` returns **FALSE**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="6da66-116">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="6da66-116">Additional resources</span></span>

[<span data-ttu-id="6da66-117">Andra (företagsdomänspecifika) funktioner</span><span class="sxs-lookup"><span data-stu-id="6da66-117">Other (business domain–specific) functions</span></span>](er-functions-category-other.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]