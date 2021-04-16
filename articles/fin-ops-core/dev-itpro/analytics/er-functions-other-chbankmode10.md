---
title: CH_BANK_MOD_10 ER-funktion
description: Det här avsnittet innehåller information om hur funktionen CH_BANK_MOD_10 elektronisk rapportering (ER) används.
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
ms.openlocfilehash: 92750ca7e7396077d8c56c3b336f495c228dddce
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5744425"
---
# <a name="ch_bank_mod_10-er-function"></a><span data-ttu-id="45ae0-103">CH_BANK_MOD_10 ER-funktion</span><span class="sxs-lookup"><span data-stu-id="45ae0-103">CH_BANK_MOD_10 ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="45ae0-104">`CH_BANK_MOD_10`-funktionen returnerar ett *sträng*-värde som representerar en betalningsmottagarreferens som ett MOD10-uttryck, baserat på siffrorna i det angivna fakturanumret.</span><span class="sxs-lookup"><span data-stu-id="45ae0-104">The `CH_BANK_MOD_10` function returns a *String* value that represents a creditor reference as an MOD10 expression, based on the digits of the specified invoice number.</span></span>

## <a name="syntax"></a><span data-ttu-id="45ae0-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="45ae0-105">Syntax</span></span>

```vb
CH_BANK_MOD_10 (invoice number digits)
```

## <a name="arguments"></a><span data-ttu-id="45ae0-106">Argument</span><span class="sxs-lookup"><span data-stu-id="45ae0-106">Arguments</span></span>

<span data-ttu-id="45ae0-107">`invoice number digits`: *Sträng*</span><span class="sxs-lookup"><span data-stu-id="45ae0-107">`invoice number digits`: *String*</span></span>

<span data-ttu-id="45ae0-108">Ett textvärde som representerar siffrorna i ett fakturanummer.</span><span class="sxs-lookup"><span data-stu-id="45ae0-108">A text value that represents the digits of an invoice number.</span></span>

## <a name="return-values"></a><span data-ttu-id="45ae0-109">Returvärden</span><span class="sxs-lookup"><span data-stu-id="45ae0-109">Return values</span></span>

<span data-ttu-id="45ae0-110">*Sträng*</span><span class="sxs-lookup"><span data-stu-id="45ae0-110">*String*</span></span>

<span data-ttu-id="45ae0-111">Det resulterande textvärdet.</span><span class="sxs-lookup"><span data-stu-id="45ae0-111">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="45ae0-112">Exempel</span><span class="sxs-lookup"><span data-stu-id="45ae0-112">Example</span></span>

<span data-ttu-id="45ae0-113">`CH_BANK_MOD_10 ("VEND-200002")` returnerar **3**.</span><span class="sxs-lookup"><span data-stu-id="45ae0-113">`CH_BANK_MOD_10 ("VEND-200002")` returns **3**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="45ae0-114">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="45ae0-114">Additional resources</span></span>

[<span data-ttu-id="45ae0-115">Andra (företagsdomänspecifika) funktioner</span><span class="sxs-lookup"><span data-stu-id="45ae0-115">Other (business domain–specific) functions</span></span>](er-functions-category-other.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]