---
title: MOD_97 ER-funktion
description: Det här avsnittet innehåller information om hur funktionen MOD_97 elektronisk rapportering (ER) används.
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
ms.openlocfilehash: b2e4e40fbd953b31225ccc0f54912b26933ccc48
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/05/2020
ms.locfileid: "4680648"
---
# <a name="mod_97-er-function"></a><span data-ttu-id="0b04f-103">MOD_97 ER-funktion</span><span class="sxs-lookup"><span data-stu-id="0b04f-103">MOD_97 ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="0b04f-104">`MOD_97`-funktionen returnerar ett *sträng*-värde som representerar en betalningsmottagarreferens som ett MOD97-uttryck, baserat på siffrorna i det angivna fakturanumret.</span><span class="sxs-lookup"><span data-stu-id="0b04f-104">The `MOD_97` function returns a *String* value that represents a creditor reference as a MOD97 expression, based on the digits of the specified invoice number.</span></span>

## <a name="syntax"></a><span data-ttu-id="0b04f-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="0b04f-105">Syntax</span></span>

```vb
MOD_97 (invoice number digits)
```

## <a name="arguments"></a><span data-ttu-id="0b04f-106">Argument</span><span class="sxs-lookup"><span data-stu-id="0b04f-106">Arguments</span></span>

<span data-ttu-id="0b04f-107">`invoice number digits`: *Sträng*</span><span class="sxs-lookup"><span data-stu-id="0b04f-107">`invoice number digits`: *String*</span></span>

<span data-ttu-id="0b04f-108">Ett textvärde som representerar siffrorna i ett fakturanummer.</span><span class="sxs-lookup"><span data-stu-id="0b04f-108">A text value that represents the digits of an invoice number.</span></span>

## <a name="return-values"></a><span data-ttu-id="0b04f-109">Returvärden</span><span class="sxs-lookup"><span data-stu-id="0b04f-109">Return values</span></span>

<span data-ttu-id="0b04f-110">*Sträng*</span><span class="sxs-lookup"><span data-stu-id="0b04f-110">*String*</span></span>

<span data-ttu-id="0b04f-111">Det resulterande textvärdet.</span><span class="sxs-lookup"><span data-stu-id="0b04f-111">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="0b04f-112">Exempel</span><span class="sxs-lookup"><span data-stu-id="0b04f-112">Example</span></span>

<span data-ttu-id="0b04f-113">`MOD_97 ("VEND-200002")` returnerar **"20000285"**.</span><span class="sxs-lookup"><span data-stu-id="0b04f-113">`MOD_97 ("VEND-200002")` returns **"20000285"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="0b04f-114">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="0b04f-114">Additional resources</span></span>

[<span data-ttu-id="0b04f-115">Andra (företagsdomänspecifika) funktioner</span><span class="sxs-lookup"><span data-stu-id="0b04f-115">Other (business domain–specific) functions</span></span>](er-functions-category-other.md)
