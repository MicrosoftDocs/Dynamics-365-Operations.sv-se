---
title: MID ER-funktion
description: Det här avsnittet innehåller information om hur funktionen MID elektronisk rapportering (ER) används.
author: NickSelin
ms.date: 12/10/2019
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
ms.openlocfilehash: 9a9ff3f1055f6757d6d4073dbb816773d8bfc8ba
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5746277"
---
# <a name="mid-er-function"></a><span data-ttu-id="89607-103">MID ER-funktion</span><span class="sxs-lookup"><span data-stu-id="89607-103">MID ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="89607-104">`MID`-funktionen returnerar ett *sträng*-värde som visar angivet antal tecken från början av den angivna strängen som börjar vid den angivna positionen.</span><span class="sxs-lookup"><span data-stu-id="89607-104">The `MID` function returns a *String* value that presents the specified number of characters from the specified string, starting at the specified position.</span></span>

## <a name="syntax"></a><span data-ttu-id="89607-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="89607-105">Syntax</span></span>

```vb
MID (text, starting position, number of characters)
```

## <a name="arguments"></a><span data-ttu-id="89607-106">Argument</span><span class="sxs-lookup"><span data-stu-id="89607-106">Arguments</span></span>

<span data-ttu-id="89607-107">`text`: *Sträng*</span><span class="sxs-lookup"><span data-stu-id="89607-107">`text`: *String*</span></span>

<span data-ttu-id="89607-108">Ett *sträng*-värde som anger vilken text som ska returnera tecken från.</span><span class="sxs-lookup"><span data-stu-id="89607-108">A *String* value that specifies the text to return characters from.</span></span>

<span data-ttu-id="89607-109">`starting position`: *Heltal*</span><span class="sxs-lookup"><span data-stu-id="89607-109">`starting position`: *Integer*</span></span>

<span data-ttu-id="89607-110">Ett *heltal*-värde som anger positionen för det första tecknet som måste returneras från den angivna texten.</span><span class="sxs-lookup"><span data-stu-id="89607-110">An *Integer* value that specifies the position of the first character that must be returned from the specified text.</span></span>

<span data-ttu-id="89607-111">`number of characters`: *Heltal*</span><span class="sxs-lookup"><span data-stu-id="89607-111">`number of characters`: *Integer*</span></span>

<span data-ttu-id="89607-112">Ett *heltal*-värde som anger antalet tecken som måste returneras med början från den angivna startpositionen.</span><span class="sxs-lookup"><span data-stu-id="89607-112">An *Integer* value that specifies the number of characters that must be returned, starting at the specified starting position.</span></span>

## <a name="return-values"></a><span data-ttu-id="89607-113">Returvärden</span><span class="sxs-lookup"><span data-stu-id="89607-113">Return values</span></span>

<span data-ttu-id="89607-114">*Sträng*</span><span class="sxs-lookup"><span data-stu-id="89607-114">*String*</span></span>

<span data-ttu-id="89607-115">Det resulterande textvärdet.</span><span class="sxs-lookup"><span data-stu-id="89607-115">The resulting text value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="89607-116">Användningsanteckningar</span><span class="sxs-lookup"><span data-stu-id="89607-116">Usage notes</span></span>

<span data-ttu-id="89607-117">Om värdet för `starting position`-argumentet är mindre än 0 (noll), räknas de tecken som returneras från den första positionen i den angivna strängen.</span><span class="sxs-lookup"><span data-stu-id="89607-117">If the value of the `starting position` argument is less than 0 (zero), the characters that are returned are counted from the first position in the specified string.</span></span>

<span data-ttu-id="89607-118">Om värdet för `starting position`-argumentet överskrider längden på den angivna strängen, returneras en tom sträng.</span><span class="sxs-lookup"><span data-stu-id="89607-118">If the value of the `starting position` argument exceeds length of the specified string, an empty string is returned.</span></span>

## <a name="example"></a><span data-ttu-id="89607-119">Exempel</span><span class="sxs-lookup"><span data-stu-id="89607-119">Example</span></span>

<span data-ttu-id="89607-120">`MID ("Sample", 2, 3)` returnerar **"amp"**.</span><span class="sxs-lookup"><span data-stu-id="89607-120">`MID ("Sample", 2, 3)` returns **"amp"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="89607-121">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="89607-121">Additional resources</span></span>

[<span data-ttu-id="89607-122">Textfunktioner</span><span class="sxs-lookup"><span data-stu-id="89607-122">Text functions</span></span>](er-functions-category-text.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]