---
title: TRIM ER-funktion
description: Det här avsnittet innehåller information om hur funktionen TRIM elektronisk rapportering (ER) används.
author: NickSelin
ms.date: 12/05/2019
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
ms.openlocfilehash: 93b08792a7aab7245d0443da05e0330bf8b2d56e
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5746059"
---
# <a name="trim-er-function"></a><span data-ttu-id="ab07c-103">TRIM ER-funktion</span><span class="sxs-lookup"><span data-stu-id="ab07c-103">TRIM ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="ab07c-104">`TRIM`-funktionen returnerar den angivna textsträngen som ett *Sträng*-värde efter att inledande och efterföljande blanksteg har trunkerats och multipla blanksteg mellan ord har tagits bort.</span><span class="sxs-lookup"><span data-stu-id="ab07c-104">The `TRIM` function returns the specified text string as a *String* value after leading and trailing spaces have been truncated, and after multiple spaces between words have been removed.</span></span>

## <a name="syntax"></a><span data-ttu-id="ab07c-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="ab07c-105">Syntax</span></span>

```vb
TRIM (text )
```

## <a name="arguments"></a><span data-ttu-id="ab07c-106">Argument</span><span class="sxs-lookup"><span data-stu-id="ab07c-106">Arguments</span></span>

<span data-ttu-id="ab07c-107">`text`: *Sträng*</span><span class="sxs-lookup"><span data-stu-id="ab07c-107">`text`: *String*</span></span>

<span data-ttu-id="ab07c-108">Den giltiga sökvägen till en datakälla av typen *Sträng*.</span><span class="sxs-lookup"><span data-stu-id="ab07c-108">The valid path of a data source of the *String* type.</span></span>

## <a name="return-values"></a><span data-ttu-id="ab07c-109">Returvärden</span><span class="sxs-lookup"><span data-stu-id="ab07c-109">Return values</span></span>

<span data-ttu-id="ab07c-110">*Sträng*</span><span class="sxs-lookup"><span data-stu-id="ab07c-110">*String*</span></span>

<span data-ttu-id="ab07c-111">Det resulterande textvärdet.</span><span class="sxs-lookup"><span data-stu-id="ab07c-111">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="ab07c-112">Exempel</span><span class="sxs-lookup"><span data-stu-id="ab07c-112">Example</span></span>

<span data-ttu-id="ab07c-113">`TRIM ("`&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`Sample`&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`text`&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`")` returnerar **"Exempeltext"**.</span><span class="sxs-lookup"><span data-stu-id="ab07c-113">`TRIM ("`&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`Sample`&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`text`&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`")` returns **"Sample text"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="ab07c-114">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="ab07c-114">Additional resources</span></span>

[<span data-ttu-id="ab07c-115">Textfunktioner</span><span class="sxs-lookup"><span data-stu-id="ab07c-115">Text functions</span></span>](er-functions-category-text.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]