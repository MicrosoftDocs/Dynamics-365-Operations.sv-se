---
title: FIRSTORNULL ER-funktion
description: Det här avsnittet förklarar hur funktionen FIRSTORNULL elektronisk rapportering (ER) används.
author: NickSelin
manager: kfend
ms.date: 11/29/2019
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
ms.openlocfilehash: 86c8a0ae21ffeb6268efbbd198f7c709c2ad54f6
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/12/2020
ms.locfileid: "3042123"
---
# <span data-ttu-id="d636c-103"><a name="FIRSTORNULL">FIRSTORNULL ER-funktion</a></span><span class="sxs-lookup"><span data-stu-id="d636c-103"><a name="FIRSTORNULL">FIRSTORNULL ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="d636c-104">`FIRSTORNULL`-funktionen returnerar den första posten i den angivna listan som ett *behållarvärde (post)* om posten inte är tom.</span><span class="sxs-lookup"><span data-stu-id="d636c-104">The `FIRSTORNULL` function returns the first record of the specified list as a *Container (record)* value, if that record isn't empty.</span></span> <span data-ttu-id="d636c-105">Om posten är tom returnerar den här funktionen ett nullvärde *behållare (post)*.</span><span class="sxs-lookup"><span data-stu-id="d636c-105">If the record is empty, this function returns a null *Container (record)* value.</span></span>

## <a name="syntax"></a><span data-ttu-id="d636c-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="d636c-106">Syntax</span></span>

```vb
FIRSTORNULL (list)
```

## <a name="arguments"></a><span data-ttu-id="d636c-107">Argument</span><span class="sxs-lookup"><span data-stu-id="d636c-107">Arguments</span></span>

<span data-ttu-id="d636c-108">`list`: *Post-lista*</span><span class="sxs-lookup"><span data-stu-id="d636c-108">`list`: *Record list*</span></span>

<span data-ttu-id="d636c-109">Den giltiga sökvägen av en datakälla för datatypen *Postlista*.</span><span class="sxs-lookup"><span data-stu-id="d636c-109">The valid path of a data source of the *Record list* data type.</span></span>

## <a name="return-values"></a><span data-ttu-id="d636c-110">Returvärden</span><span class="sxs-lookup"><span data-stu-id="d636c-110">Return values</span></span>

<span data-ttu-id="d636c-111">*Behållare (post)*</span><span class="sxs-lookup"><span data-stu-id="d636c-111">*Container (record)*</span></span>

<span data-ttu-id="d636c-112">Det resulterande postvärdet.</span><span class="sxs-lookup"><span data-stu-id="d636c-112">The resulting record value.</span></span>

## <a name="example"></a><span data-ttu-id="d636c-113">Exempel</span><span class="sxs-lookup"><span data-stu-id="d636c-113">Example</span></span>

<span data-ttu-id="d636c-114">Uttrycket `FIRSTORNULL(SPLIT("",1)).Value` returnerar en tom sträng (**""**).</span><span class="sxs-lookup"><span data-stu-id="d636c-114">The expression `FIRSTORNULL(SPLIT("",1)).Value` returns an empty string (**""**).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="d636c-115">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="d636c-115">Additional resources</span></span>

[<span data-ttu-id="d636c-116">Lista över funktioner</span><span class="sxs-lookup"><span data-stu-id="d636c-116">List functions</span></span>](er-functions-category-list.md)
