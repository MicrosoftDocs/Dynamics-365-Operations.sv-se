---
title: CN_GBT_ADDITIONALDIMENSIONID ER-funktion
description: Det här avsnittet innehåller information om hur funktionen CN_GBT_ADDITIONALDIMENSIONID elektronisk rapportering (ER) används.
author: NickSelin
manager: kfend
ms.date: 12/17/2019
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
ms.openlocfilehash: df693d745d1fe74b4500dd3fda0cc0c4be21142d
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/20/2019
ms.locfileid: "2917038"
---
# <span data-ttu-id="6c3d3-103"><a name="CN_GBT_ADDITIONALDIMENSIONID">CN_GBT_ADDITIONALDIMENSIONID ER-funktion</a></span><span class="sxs-lookup"><span data-stu-id="6c3d3-103"><a name="CN_GBT_ADDITIONALDIMENSIONID">CN_GBT_ADDITIONALDIMENSIONID ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="6c3d3-104">`CN_GBT_ADDITIONALDIMENSIONID`-funktionen returnerar ett *sträng*-värde som representerar ett enda ekonomisk dimensions-ID som hämtas från den angivna strängen.</span><span class="sxs-lookup"><span data-stu-id="6c3d3-104">The `CN_GBT_ADDITIONALDIMENSIONID` function returns a *String* value that represents a single financial dimension ID that is taken from the specified string.</span></span> <span data-ttu-id="6c3d3-105">Den angivna strängen visar alla dimensioner som en kommaseparerad lista med ID:n.</span><span class="sxs-lookup"><span data-stu-id="6c3d3-105">The specified string presents all dimensions as a comma-separated list of IDs.</span></span>

## <a name="syntax"></a><span data-ttu-id="6c3d3-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="6c3d3-106">Syntax</span></span>

```
CN_GBT_ADDITIONALDIMENSIONID (text, number)
```

## <a name="arguments"></a><span data-ttu-id="6c3d3-107">Argument</span><span class="sxs-lookup"><span data-stu-id="6c3d3-107">Arguments</span></span>

<span data-ttu-id="6c3d3-108">`text`: *Sträng*</span><span class="sxs-lookup"><span data-stu-id="6c3d3-108">`text`: *String*</span></span>

<span data-ttu-id="6c3d3-109">Ett *sträng*-värde som visar alla dimensioner som en kommaseparerad lista med ID:n.</span><span class="sxs-lookup"><span data-stu-id="6c3d3-109">A *String* value that presents all dimensions as a comma-separated list of IDs.</span></span>

<span data-ttu-id="6c3d3-110">`number`: Heltal</span><span class="sxs-lookup"><span data-stu-id="6c3d3-110">`number`: Integer</span></span>

<span data-ttu-id="6c3d3-111">Värdet *heltal* definierar den begärda dimensionens seriekod i den angivna strängen.</span><span class="sxs-lookup"><span data-stu-id="6c3d3-111">An *Integer* value that defines the sequence code of the requested dimension in the specified string.</span></span>

## <a name="return-values"></a><span data-ttu-id="6c3d3-112">Returvärden</span><span class="sxs-lookup"><span data-stu-id="6c3d3-112">Return values</span></span>

<span data-ttu-id="6c3d3-113">*Sträng*</span><span class="sxs-lookup"><span data-stu-id="6c3d3-113">*String*</span></span>

<span data-ttu-id="6c3d3-114">Det resulterande textvärdet.</span><span class="sxs-lookup"><span data-stu-id="6c3d3-114">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="6c3d3-115">Exempel</span><span class="sxs-lookup"><span data-stu-id="6c3d3-115">Example</span></span>

<span data-ttu-id="6c3d3-116">`CN_GBT_AdditionalDimensionID ("AA,BB,CC,DD,EE,FF,GG,HH", 3)` returnerar **"CC"**.</span><span class="sxs-lookup"><span data-stu-id="6c3d3-116">`CN_GBT_AdditionalDimensionID ("AA,BB,CC,DD,EE,FF,GG,HH", 3)` returns **"CC"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="6c3d3-117">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="6c3d3-117">Additional resources</span></span>

[<span data-ttu-id="6c3d3-118">Andra (företagsdomänspecifika) funktioner</span><span class="sxs-lookup"><span data-stu-id="6c3d3-118">Other (business domain–specific) functions</span></span>](er-functions-category-other.md)
