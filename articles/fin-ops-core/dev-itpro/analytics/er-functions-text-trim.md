---
title: TRIM ER-funktion
description: Det här avsnittet innehåller information om hur funktionen TRIM elektronisk rapportering (ER) används.
author: NickSelin
manager: kfend
ms.date: 12/05/2019
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
ms.openlocfilehash: 2673b0167f7602a6d6eaa79be639905028e99822
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/20/2019
ms.locfileid: "2915543"
---
# <span data-ttu-id="fa929-103"><a name="TRIM">TRIM ER-funktion</a></span><span class="sxs-lookup"><span data-stu-id="fa929-103"><a name="TRIM">TRIM ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="fa929-104">`TRIM`-funktionen returnerar den angivna textsträngen som ett *Sträng*-värde efter att inledande och efterföljande blanksteg har trunkerats och multipla blanksteg mellan ord har tagits bort.</span><span class="sxs-lookup"><span data-stu-id="fa929-104">The `TRIM` function returns the specified text string as a *String* value after leading and trailing spaces have been truncated, and after multiple spaces between words have been removed.</span></span>

## <a name="syntax"></a><span data-ttu-id="fa929-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="fa929-105">Syntax</span></span>

```
TRIM (text )
```

## <a name="arguments"></a><span data-ttu-id="fa929-106">Argument</span><span class="sxs-lookup"><span data-stu-id="fa929-106">Arguments</span></span>

<span data-ttu-id="fa929-107">`text`: *Sträng*</span><span class="sxs-lookup"><span data-stu-id="fa929-107">`text`: *String*</span></span>

<span data-ttu-id="fa929-108">Den giltiga sökvägen till en datakälla av typen *Sträng*.</span><span class="sxs-lookup"><span data-stu-id="fa929-108">The valid path of a data source of the *String* type.</span></span>

## <a name="return-values"></a><span data-ttu-id="fa929-109">Returvärden</span><span class="sxs-lookup"><span data-stu-id="fa929-109">Return values</span></span>

<span data-ttu-id="fa929-110">*Sträng*</span><span class="sxs-lookup"><span data-stu-id="fa929-110">*String*</span></span>

<span data-ttu-id="fa929-111">Det resulterande textvärdet.</span><span class="sxs-lookup"><span data-stu-id="fa929-111">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="fa929-112">Exempel</span><span class="sxs-lookup"><span data-stu-id="fa929-112">Example</span></span>

<span data-ttu-id="fa929-113">`TRIM ("`&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`Sample`&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`text`&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`")` returnerar **"Exempeltext"**.</span><span class="sxs-lookup"><span data-stu-id="fa929-113">`TRIM ("`&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`Sample`&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`text`&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`")` returns **"Sample text"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="fa929-114">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="fa929-114">Additional resources</span></span>

[<span data-ttu-id="fa929-115">Textfunktioner</span><span class="sxs-lookup"><span data-stu-id="fa929-115">Text functions</span></span>](er-functions-category-text.md)
