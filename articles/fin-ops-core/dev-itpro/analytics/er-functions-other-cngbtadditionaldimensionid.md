---
title: CN_GBT_ADDITIONALDIMENSIONID ER-funktion
description: Det här avsnittet innehåller information om hur funktionen CN_GBT_ADDITIONALDIMENSIONID elektronisk rapportering (ER) används.
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
ms.openlocfilehash: 5774bb6928ae321af923819d6b2cc609dbf35b99
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/09/2021
ms.locfileid: "5564152"
---
# <a name="cn_gbt_additionaldimensionid-er-function"></a><span data-ttu-id="9eb30-103">CN_GBT_ADDITIONALDIMENSIONID ER-funktion</span><span class="sxs-lookup"><span data-stu-id="9eb30-103">CN_GBT_ADDITIONALDIMENSIONID ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="9eb30-104">`CN_GBT_ADDITIONALDIMENSIONID`-funktionen returnerar ett *sträng*-värde som representerar ett enda ekonomisk dimensions-ID som hämtas från den angivna strängen.</span><span class="sxs-lookup"><span data-stu-id="9eb30-104">The `CN_GBT_ADDITIONALDIMENSIONID` function returns a *String* value that represents a single financial dimension ID that is taken from the specified string.</span></span> <span data-ttu-id="9eb30-105">Den angivna strängen visar alla dimensioner som en kommaseparerad lista med ID:n.</span><span class="sxs-lookup"><span data-stu-id="9eb30-105">The specified string presents all dimensions as a comma-separated list of IDs.</span></span>

## <a name="syntax"></a><span data-ttu-id="9eb30-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="9eb30-106">Syntax</span></span>

```vb
CN_GBT_ADDITIONALDIMENSIONID (text, number)
```

## <a name="arguments"></a><span data-ttu-id="9eb30-107">Argument</span><span class="sxs-lookup"><span data-stu-id="9eb30-107">Arguments</span></span>

<span data-ttu-id="9eb30-108">`text`: *Sträng*</span><span class="sxs-lookup"><span data-stu-id="9eb30-108">`text`: *String*</span></span>

<span data-ttu-id="9eb30-109">Ett *sträng*-värde som visar alla dimensioner som en kommaseparerad lista med ID:n.</span><span class="sxs-lookup"><span data-stu-id="9eb30-109">A *String* value that presents all dimensions as a comma-separated list of IDs.</span></span>

<span data-ttu-id="9eb30-110">`number`: Heltal</span><span class="sxs-lookup"><span data-stu-id="9eb30-110">`number`: Integer</span></span>

<span data-ttu-id="9eb30-111">Värdet *heltal* definierar den begärda dimensionens seriekod i den angivna strängen.</span><span class="sxs-lookup"><span data-stu-id="9eb30-111">An *Integer* value that defines the sequence code of the requested dimension in the specified string.</span></span>

## <a name="return-values"></a><span data-ttu-id="9eb30-112">Returvärden</span><span class="sxs-lookup"><span data-stu-id="9eb30-112">Return values</span></span>

<span data-ttu-id="9eb30-113">*Sträng*</span><span class="sxs-lookup"><span data-stu-id="9eb30-113">*String*</span></span>

<span data-ttu-id="9eb30-114">Det resulterande textvärdet.</span><span class="sxs-lookup"><span data-stu-id="9eb30-114">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="9eb30-115">Exempel</span><span class="sxs-lookup"><span data-stu-id="9eb30-115">Example</span></span>

<span data-ttu-id="9eb30-116">`CN_GBT_AdditionalDimensionID ("AA,BB,CC,DD,EE,FF,GG,HH", 3)` returnerar **"CC"**.</span><span class="sxs-lookup"><span data-stu-id="9eb30-116">`CN_GBT_AdditionalDimensionID ("AA,BB,CC,DD,EE,FF,GG,HH", 3)` returns **"CC"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="9eb30-117">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="9eb30-117">Additional resources</span></span>

[<span data-ttu-id="9eb30-118">Andra (företagsdomänspecifika) funktioner</span><span class="sxs-lookup"><span data-stu-id="9eb30-118">Other (business domain–specific) functions</span></span>](er-functions-category-other.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]