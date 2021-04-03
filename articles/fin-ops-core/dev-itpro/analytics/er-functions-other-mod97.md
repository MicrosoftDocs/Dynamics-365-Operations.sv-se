---
title: MOD_97 ER-funktion
description: Det här avsnittet innehåller information om hur funktionen MOD_97 elektronisk rapportering (ER) används.
author: NickSelin
manager: kfend
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
ms.openlocfilehash: 618cb2b101dd0b1c91b3b1538ef3f87c21e4a70a
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/09/2021
ms.locfileid: "5563352"
---
# <a name="mod_97-er-function"></a><span data-ttu-id="ce16c-103">MOD_97 ER-funktion</span><span class="sxs-lookup"><span data-stu-id="ce16c-103">MOD_97 ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="ce16c-104">`MOD_97`-funktionen returnerar ett *sträng*-värde som representerar en betalningsmottagarreferens som ett MOD97-uttryck, baserat på siffrorna i det angivna fakturanumret.</span><span class="sxs-lookup"><span data-stu-id="ce16c-104">The `MOD_97` function returns a *String* value that represents a creditor reference as a MOD97 expression, based on the digits of the specified invoice number.</span></span>

## <a name="syntax"></a><span data-ttu-id="ce16c-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="ce16c-105">Syntax</span></span>

```vb
MOD_97 (invoice number digits)
```

## <a name="arguments"></a><span data-ttu-id="ce16c-106">Argument</span><span class="sxs-lookup"><span data-stu-id="ce16c-106">Arguments</span></span>

<span data-ttu-id="ce16c-107">`invoice number digits`: *Sträng*</span><span class="sxs-lookup"><span data-stu-id="ce16c-107">`invoice number digits`: *String*</span></span>

<span data-ttu-id="ce16c-108">Ett textvärde som representerar siffrorna i ett fakturanummer.</span><span class="sxs-lookup"><span data-stu-id="ce16c-108">A text value that represents the digits of an invoice number.</span></span>

## <a name="return-values"></a><span data-ttu-id="ce16c-109">Returvärden</span><span class="sxs-lookup"><span data-stu-id="ce16c-109">Return values</span></span>

<span data-ttu-id="ce16c-110">*Sträng*</span><span class="sxs-lookup"><span data-stu-id="ce16c-110">*String*</span></span>

<span data-ttu-id="ce16c-111">Det resulterande textvärdet.</span><span class="sxs-lookup"><span data-stu-id="ce16c-111">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="ce16c-112">Exempel</span><span class="sxs-lookup"><span data-stu-id="ce16c-112">Example</span></span>

<span data-ttu-id="ce16c-113">`MOD_97 ("VEND-200002")` returnerar **"20000285"**.</span><span class="sxs-lookup"><span data-stu-id="ce16c-113">`MOD_97 ("VEND-200002")` returns **"20000285"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="ce16c-114">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="ce16c-114">Additional resources</span></span>

[<span data-ttu-id="ce16c-115">Andra (företagsdomänspecifika) funktioner</span><span class="sxs-lookup"><span data-stu-id="ce16c-115">Other (business domain–specific) functions</span></span>](er-functions-category-other.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]