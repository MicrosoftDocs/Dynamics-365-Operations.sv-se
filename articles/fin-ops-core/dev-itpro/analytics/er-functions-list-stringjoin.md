---
title: STRINGJOIN ER-funktion
description: Det här avsnittet innehåller information om hur funktionen STRINGJOIN elektronisk rapportering (ER) används.
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
ms.openlocfilehash: 10a98e98d913b0b4fe36690f7effd5d8d9a3faf4
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/12/2020
ms.locfileid: "3041801"
---
# <span data-ttu-id="d1570-103"><a name="STRINGJOIN">STRINGJOIN ER-funktion</a></span><span class="sxs-lookup"><span data-stu-id="d1570-103"><a name="STRINGJOIN">STRINGJOIN ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="d1570-104">`STRINGJOIN`-funktionen returnerar ett *Sträng*-värde som består av de konkatenerade värdena från det definierade fältet från den angivna listan.</span><span class="sxs-lookup"><span data-stu-id="d1570-104">The `STRINGJOIN` function returns a *String* value that consists of concatenated values of the specified field from the specified list.</span></span> <span data-ttu-id="d1570-105">Värdena kan avgränsas med angivna avgränsare.</span><span class="sxs-lookup"><span data-stu-id="d1570-105">The values can be separated by the specified delimiter.</span></span>

## <a name="syntax"></a><span data-ttu-id="d1570-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="d1570-106">Syntax</span></span>

```vb
STRINGJOIN (list, field, delimiter)
```

## <a name="arguments"></a><span data-ttu-id="d1570-107">Argument</span><span class="sxs-lookup"><span data-stu-id="d1570-107">Arguments</span></span>

<span data-ttu-id="d1570-108">`list`: *Post-lista*</span><span class="sxs-lookup"><span data-stu-id="d1570-108">`list`: *Record list*</span></span>

<span data-ttu-id="d1570-109">Den giltiga sökvägen av en datakälla för datatypen *Postlista*.</span><span class="sxs-lookup"><span data-stu-id="d1570-109">The valid path of a data source of the *Record list* data type.</span></span>

<span data-ttu-id="d1570-110">`field`: *Fält*</span><span class="sxs-lookup"><span data-stu-id="d1570-110">`field`: *Field*</span></span>

<span data-ttu-id="d1570-111">Den giltiga sökvägen för ett fält med datatypen *sträng* skriver den angivna listan.</span><span class="sxs-lookup"><span data-stu-id="d1570-111">The valid path of a field of the *String* data type in the specified list.</span></span>

<span data-ttu-id="d1570-112">`delimiter`: *Sträng*</span><span class="sxs-lookup"><span data-stu-id="d1570-112">`delimiter`: *String*</span></span>

<span data-ttu-id="d1570-113">En avgränsare som används för att avgränsa delsträngar.</span><span class="sxs-lookup"><span data-stu-id="d1570-113">A delimiter that is used to separate substrings.</span></span>

## <a name="return-values"></a><span data-ttu-id="d1570-114">Returvärden</span><span class="sxs-lookup"><span data-stu-id="d1570-114">Return values</span></span>

<span data-ttu-id="d1570-115">*Sträng*</span><span class="sxs-lookup"><span data-stu-id="d1570-115">*String*</span></span>

<span data-ttu-id="d1570-116">Det resulterande textvärdet.</span><span class="sxs-lookup"><span data-stu-id="d1570-116">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="d1570-117">Exempel</span><span class="sxs-lookup"><span data-stu-id="d1570-117">Example</span></span>

<span data-ttu-id="d1570-118">Om du anger `SPLIT("abc" , 1)` som datakälla **DS** returnerar uttrycket `STRINGJOIN (DS, DS.Value, "-")`**"a-b-c"**.</span><span class="sxs-lookup"><span data-stu-id="d1570-118">If you enter `SPLIT("abc" , 1)` as data source **DS**, the expression `STRINGJOIN (DS, DS.Value, "-")` returns **"a-b-c"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="d1570-119">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="d1570-119">Additional resources</span></span>

[<span data-ttu-id="d1570-120">Lista över funktioner</span><span class="sxs-lookup"><span data-stu-id="d1570-120">List functions</span></span>](er-functions-category-list.md)
