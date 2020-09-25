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
ms.openlocfilehash: 7fdc4527bc6115bdb3fca9d6a92d3d77a7c264c2
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/01/2020
ms.locfileid: "3744441"
---
# <a name="cn_gbt_additionaldimensionid-er-function"></a><span data-ttu-id="18b1b-103">CN_GBT_ADDITIONALDIMENSIONID ER-funktion</span><span class="sxs-lookup"><span data-stu-id="18b1b-103">CN_GBT_ADDITIONALDIMENSIONID ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="18b1b-104">`CN_GBT_ADDITIONALDIMENSIONID`-funktionen returnerar ett *sträng*-värde som representerar ett enda ekonomisk dimensions-ID som hämtas från den angivna strängen.</span><span class="sxs-lookup"><span data-stu-id="18b1b-104">The `CN_GBT_ADDITIONALDIMENSIONID` function returns a *String* value that represents a single financial dimension ID that is taken from the specified string.</span></span> <span data-ttu-id="18b1b-105">Den angivna strängen visar alla dimensioner som en kommaseparerad lista med ID:n.</span><span class="sxs-lookup"><span data-stu-id="18b1b-105">The specified string presents all dimensions as a comma-separated list of IDs.</span></span>

## <a name="syntax"></a><span data-ttu-id="18b1b-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="18b1b-106">Syntax</span></span>

```vb
CN_GBT_ADDITIONALDIMENSIONID (text, number)
```

## <a name="arguments"></a><span data-ttu-id="18b1b-107">Argument</span><span class="sxs-lookup"><span data-stu-id="18b1b-107">Arguments</span></span>

<span data-ttu-id="18b1b-108">`text`: *Sträng*</span><span class="sxs-lookup"><span data-stu-id="18b1b-108">`text`: *String*</span></span>

<span data-ttu-id="18b1b-109">Ett *sträng*-värde som visar alla dimensioner som en kommaseparerad lista med ID:n.</span><span class="sxs-lookup"><span data-stu-id="18b1b-109">A *String* value that presents all dimensions as a comma-separated list of IDs.</span></span>

<span data-ttu-id="18b1b-110">`number`: Heltal</span><span class="sxs-lookup"><span data-stu-id="18b1b-110">`number`: Integer</span></span>

<span data-ttu-id="18b1b-111">Värdet *heltal* definierar den begärda dimensionens seriekod i den angivna strängen.</span><span class="sxs-lookup"><span data-stu-id="18b1b-111">An *Integer* value that defines the sequence code of the requested dimension in the specified string.</span></span>

## <a name="return-values"></a><span data-ttu-id="18b1b-112">Returvärden</span><span class="sxs-lookup"><span data-stu-id="18b1b-112">Return values</span></span>

<span data-ttu-id="18b1b-113">*Sträng*</span><span class="sxs-lookup"><span data-stu-id="18b1b-113">*String*</span></span>

<span data-ttu-id="18b1b-114">Det resulterande textvärdet.</span><span class="sxs-lookup"><span data-stu-id="18b1b-114">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="18b1b-115">Exempel</span><span class="sxs-lookup"><span data-stu-id="18b1b-115">Example</span></span>

<span data-ttu-id="18b1b-116">`CN_GBT_AdditionalDimensionID ("AA,BB,CC,DD,EE,FF,GG,HH", 3)` returnerar **"CC"**.</span><span class="sxs-lookup"><span data-stu-id="18b1b-116">`CN_GBT_AdditionalDimensionID ("AA,BB,CC,DD,EE,FF,GG,HH", 3)` returns **"CC"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="18b1b-117">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="18b1b-117">Additional resources</span></span>

[<span data-ttu-id="18b1b-118">Andra (företagsdomänspecifika) funktioner</span><span class="sxs-lookup"><span data-stu-id="18b1b-118">Other (business domain–specific) functions</span></span>](er-functions-category-other.md)
