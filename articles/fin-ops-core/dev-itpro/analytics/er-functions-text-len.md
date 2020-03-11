---
title: LEN ER-funktion
description: Det här avsnittet innehåller information om hur funktionen LEN elektronisk rapportering (ER) används.
author: NickSelin
manager: kfend
ms.date: 12/11/2019
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
ms.openlocfilehash: 3e0ba19e762574dde4f9038b87ce352d13f714f4
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/12/2020
ms.locfileid: "3041065"
---
# <span data-ttu-id="36159-103"><a name="LEN">LEN ER-funktion</a></span><span class="sxs-lookup"><span data-stu-id="36159-103"><a name="LEN">LEN ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="36159-104">`LEN`-funktionen returnerar antalet tecken i den angivna strängen som ett *heltals*-värde.</span><span class="sxs-lookup"><span data-stu-id="36159-104">The `LEN` function returns the number of characters in the specified string as an *Integer* value.</span></span>

## <a name="syntax"></a><span data-ttu-id="36159-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="36159-105">Syntax</span></span>

```vb
LEN (text)
```

## <a name="arguments"></a><span data-ttu-id="36159-106">Argument</span><span class="sxs-lookup"><span data-stu-id="36159-106">Arguments</span></span>

<span data-ttu-id="36159-107">`text`: *Sträng*</span><span class="sxs-lookup"><span data-stu-id="36159-107">`text`: *String*</span></span>

<span data-ttu-id="36159-108">Ett *sträng*-värde som anger texten.</span><span class="sxs-lookup"><span data-stu-id="36159-108">A *String* value that specifies the text.</span></span>

## <a name="return-values"></a><span data-ttu-id="36159-109">Returvärden</span><span class="sxs-lookup"><span data-stu-id="36159-109">Return values</span></span>

<span data-ttu-id="36159-110">*Heltal*</span><span class="sxs-lookup"><span data-stu-id="36159-110">*Integer*</span></span>

<span data-ttu-id="36159-111">Det resulterande numeriska värdet.</span><span class="sxs-lookup"><span data-stu-id="36159-111">The resulting numeric value.</span></span>

## <a name="example"></a><span data-ttu-id="36159-112">Exempel</span><span class="sxs-lookup"><span data-stu-id="36159-112">Example</span></span>

<span data-ttu-id="36159-113">`LEN ("Sample")` returnerar **6**.</span><span class="sxs-lookup"><span data-stu-id="36159-113">`LEN ("Sample")` returns **6**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="36159-114">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="36159-114">Additional resources</span></span>

[<span data-ttu-id="36159-115">Textfunktioner</span><span class="sxs-lookup"><span data-stu-id="36159-115">Text functions</span></span>](er-functions-category-text.md)
