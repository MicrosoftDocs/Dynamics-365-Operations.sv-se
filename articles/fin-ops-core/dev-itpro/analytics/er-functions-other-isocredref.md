---
title: Funktionen ISOCREDREF ER
description: Det här avsnittet innehåller information om hur funktionen ISOCREDREF elektronisk rapportering (ER) används.
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
ms.openlocfilehash: a9378028a4b308aae7796b861b37a5f89ddfe49c
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/09/2021
ms.locfileid: "5563423"
---
# <a name="isocredref-er-function"></a><span data-ttu-id="b4082-103">Funktionen ISOCREDREF ER</span><span class="sxs-lookup"><span data-stu-id="b4082-103">ISOCREDREF ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b4082-104">Funktionen `ISOCREDREF` returnerar ett *Sträng*-värde som representerar en International Organization for Standardization (ISO)-betalningsmottagarreferens baserad på siffror och bokstäver i det angivna fakturanumret.</span><span class="sxs-lookup"><span data-stu-id="b4082-104">The `ISOCREDREF` function returns a *String* value that represents an International Organization for Standardization (ISO) creditor reference, based on the digits and alphabetic symbols of the specified invoice number.</span></span>

## <a name="syntax"></a><span data-ttu-id="b4082-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="b4082-105">Syntax</span></span>

```vb
ISOCREDREF (invoice number digits)
```

## <a name="arguments"></a><span data-ttu-id="b4082-106">Argument</span><span class="sxs-lookup"><span data-stu-id="b4082-106">Arguments</span></span>

<span data-ttu-id="b4082-107">`invoice number digits`: *Sträng*</span><span class="sxs-lookup"><span data-stu-id="b4082-107">`invoice number digits`: *String*</span></span>

<span data-ttu-id="b4082-108">Ett textvärde som representerar siffrorna i ett fakturanummer.</span><span class="sxs-lookup"><span data-stu-id="b4082-108">A text value that represents the digits of an invoice number.</span></span>

## <a name="return-values"></a><span data-ttu-id="b4082-109">Returvärden</span><span class="sxs-lookup"><span data-stu-id="b4082-109">Return values</span></span>

<span data-ttu-id="b4082-110">*Sträng*</span><span class="sxs-lookup"><span data-stu-id="b4082-110">*String*</span></span>

<span data-ttu-id="b4082-111">Det resulterande textvärdet.</span><span class="sxs-lookup"><span data-stu-id="b4082-111">The resulting text value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="b4082-112">Användningsanteckningar</span><span class="sxs-lookup"><span data-stu-id="b4082-112">Usage notes</span></span>

> [!NOTE] 
> <span data-ttu-id="b4082-113">Om du vill ta bort symboler som inte överensstämmer med ISO-standarden måste argumentet `invoice number digits` översättas innan den skickas till den här funktionen.</span><span class="sxs-lookup"><span data-stu-id="b4082-113">To eliminate symbols from alphabets that are't ISO-compliant, the `invoice number digits` argument must be translated before it's passed to this function.</span></span>

## <a name="example"></a><span data-ttu-id="b4082-114">Exempel</span><span class="sxs-lookup"><span data-stu-id="b4082-114">Example</span></span>

<span data-ttu-id="b4082-115">`ISOCredRef ("VEND-200002")` returnerar **"RF23VEND-200002"**.</span><span class="sxs-lookup"><span data-stu-id="b4082-115">`ISOCredRef ("VEND-200002")` returns **"RF23VEND-200002"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="b4082-116">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="b4082-116">Additional resources</span></span>

[<span data-ttu-id="b4082-117">Andra (företagsdomänspecifika) funktioner</span><span class="sxs-lookup"><span data-stu-id="b4082-117">Other (business domain–specific) functions</span></span>](er-functions-category-other.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]