---
title: MID ER-funktion
description: Det här avsnittet innehåller information om hur funktionen MID elektronisk rapportering (ER) används.
author: NickSelin
manager: kfend
ms.date: 12/10/2019
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
ms.openlocfilehash: 6fbaf5952222d90a855956fb93713e0f9ef81305
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/12/2020
ms.locfileid: "3041042"
---
# <span data-ttu-id="3e3c6-103"><a name="MID">MID ER-funktion</a></span><span class="sxs-lookup"><span data-stu-id="3e3c6-103"><a name="MID">MID ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="3e3c6-104">`MID`-funktionen returnerar ett *sträng*-värde som visar angivet antal tecken från början av den angivna strängen som börjar vid den angivna positionen.</span><span class="sxs-lookup"><span data-stu-id="3e3c6-104">The `MID` function returns a *String* value that presents the specified number of characters from the specified string, starting at the specified position.</span></span>

## <a name="syntax"></a><span data-ttu-id="3e3c6-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="3e3c6-105">Syntax</span></span>

```vb
MID (text, starting position, number of characters)
```

## <a name="arguments"></a><span data-ttu-id="3e3c6-106">Argument</span><span class="sxs-lookup"><span data-stu-id="3e3c6-106">Arguments</span></span>

<span data-ttu-id="3e3c6-107">`text`: *Sträng*</span><span class="sxs-lookup"><span data-stu-id="3e3c6-107">`text`: *String*</span></span>

<span data-ttu-id="3e3c6-108">Ett *sträng*-värde som anger vilken text som ska returnera tecken från.</span><span class="sxs-lookup"><span data-stu-id="3e3c6-108">A *String* value that specifies the text to return characters from.</span></span>

<span data-ttu-id="3e3c6-109">`starting position`: *Heltal*</span><span class="sxs-lookup"><span data-stu-id="3e3c6-109">`starting position`: *Integer*</span></span>

<span data-ttu-id="3e3c6-110">Ett *heltal*-värde som anger positionen för det första tecknet som måste returneras från den angivna texten.</span><span class="sxs-lookup"><span data-stu-id="3e3c6-110">An *Integer* value that specifies the position of the first character that must be returned from the specified text.</span></span>

<span data-ttu-id="3e3c6-111">`number of characters`: *Heltal*</span><span class="sxs-lookup"><span data-stu-id="3e3c6-111">`number of characters`: *Integer*</span></span>

<span data-ttu-id="3e3c6-112">Ett *heltal*-värde som anger antalet tecken som måste returneras med början från den angivna startpositionen.</span><span class="sxs-lookup"><span data-stu-id="3e3c6-112">An *Integer* value that specifies the number of characters that must be returned, starting at the specified starting position.</span></span>

## <a name="return-values"></a><span data-ttu-id="3e3c6-113">Returvärden</span><span class="sxs-lookup"><span data-stu-id="3e3c6-113">Return values</span></span>

<span data-ttu-id="3e3c6-114">*Sträng*</span><span class="sxs-lookup"><span data-stu-id="3e3c6-114">*String*</span></span>

<span data-ttu-id="3e3c6-115">Det resulterande textvärdet.</span><span class="sxs-lookup"><span data-stu-id="3e3c6-115">The resulting text value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="3e3c6-116">Användningsanteckningar</span><span class="sxs-lookup"><span data-stu-id="3e3c6-116">Usage notes</span></span>

<span data-ttu-id="3e3c6-117">Om värdet för `starting position`-argumentet är mindre än 0 (noll), räknas de tecken som returneras från den första positionen i den angivna strängen.</span><span class="sxs-lookup"><span data-stu-id="3e3c6-117">If the value of the `starting position` argument is less than 0 (zero), the characters that are returned are counted from the first position in the specified string.</span></span>

<span data-ttu-id="3e3c6-118">Om värdet för `starting position`-argumentet överskrider längden på den angivna strängen, returneras en tom sträng.</span><span class="sxs-lookup"><span data-stu-id="3e3c6-118">If the value of the `starting position` argument exceeds length of the specified string, an empty string is returned.</span></span>

## <a name="example"></a><span data-ttu-id="3e3c6-119">Exempel</span><span class="sxs-lookup"><span data-stu-id="3e3c6-119">Example</span></span>

<span data-ttu-id="3e3c6-120">`MID ("Sample", 2, 3)` returnerar **"amp"**.</span><span class="sxs-lookup"><span data-stu-id="3e3c6-120">`MID ("Sample", 2, 3)` returns **"amp"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="3e3c6-121">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="3e3c6-121">Additional resources</span></span>

[<span data-ttu-id="3e3c6-122">Textfunktioner</span><span class="sxs-lookup"><span data-stu-id="3e3c6-122">Text functions</span></span>](er-functions-category-text.md)
