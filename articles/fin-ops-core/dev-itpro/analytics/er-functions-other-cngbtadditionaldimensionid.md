---
title: CN_GBT_ADDITIONALDIMENSIONID ER-funktion
description: Det här avsnittet innehåller information om hur funktionen CN_GBT_ADDITIONALDIMENSIONID elektronisk rapportering (ER) används.
author: NickSelin
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
ms.openlocfilehash: ac0b54476265171b3826e43600f99097701231e1
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5744401"
---
# <a name="cn_gbt_additionaldimensionid-er-function"></a><span data-ttu-id="78627-103">CN_GBT_ADDITIONALDIMENSIONID ER-funktion</span><span class="sxs-lookup"><span data-stu-id="78627-103">CN_GBT_ADDITIONALDIMENSIONID ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="78627-104">`CN_GBT_ADDITIONALDIMENSIONID`-funktionen returnerar ett *sträng*-värde som representerar ett enda ekonomisk dimensions-ID som hämtas från den angivna strängen.</span><span class="sxs-lookup"><span data-stu-id="78627-104">The `CN_GBT_ADDITIONALDIMENSIONID` function returns a *String* value that represents a single financial dimension ID that is taken from the specified string.</span></span> <span data-ttu-id="78627-105">Den angivna strängen visar alla dimensioner som en kommaseparerad lista med ID:n.</span><span class="sxs-lookup"><span data-stu-id="78627-105">The specified string presents all dimensions as a comma-separated list of IDs.</span></span>

## <a name="syntax"></a><span data-ttu-id="78627-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="78627-106">Syntax</span></span>

```vb
CN_GBT_ADDITIONALDIMENSIONID (text, number)
```

## <a name="arguments"></a><span data-ttu-id="78627-107">Argument</span><span class="sxs-lookup"><span data-stu-id="78627-107">Arguments</span></span>

<span data-ttu-id="78627-108">`text`: *Sträng*</span><span class="sxs-lookup"><span data-stu-id="78627-108">`text`: *String*</span></span>

<span data-ttu-id="78627-109">Ett *sträng*-värde som visar alla dimensioner som en kommaseparerad lista med ID:n.</span><span class="sxs-lookup"><span data-stu-id="78627-109">A *String* value that presents all dimensions as a comma-separated list of IDs.</span></span>

<span data-ttu-id="78627-110">`number`: Heltal</span><span class="sxs-lookup"><span data-stu-id="78627-110">`number`: Integer</span></span>

<span data-ttu-id="78627-111">Värdet *heltal* definierar den begärda dimensionens seriekod i den angivna strängen.</span><span class="sxs-lookup"><span data-stu-id="78627-111">An *Integer* value that defines the sequence code of the requested dimension in the specified string.</span></span>

## <a name="return-values"></a><span data-ttu-id="78627-112">Returvärden</span><span class="sxs-lookup"><span data-stu-id="78627-112">Return values</span></span>

<span data-ttu-id="78627-113">*Sträng*</span><span class="sxs-lookup"><span data-stu-id="78627-113">*String*</span></span>

<span data-ttu-id="78627-114">Det resulterande textvärdet.</span><span class="sxs-lookup"><span data-stu-id="78627-114">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="78627-115">Exempel</span><span class="sxs-lookup"><span data-stu-id="78627-115">Example</span></span>

<span data-ttu-id="78627-116">`CN_GBT_AdditionalDimensionID ("AA,BB,CC,DD,EE,FF,GG,HH", 3)` returnerar **"CC"**.</span><span class="sxs-lookup"><span data-stu-id="78627-116">`CN_GBT_AdditionalDimensionID ("AA,BB,CC,DD,EE,FF,GG,HH", 3)` returns **"CC"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="78627-117">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="78627-117">Additional resources</span></span>

[<span data-ttu-id="78627-118">Andra (företagsdomänspecifika) funktioner</span><span class="sxs-lookup"><span data-stu-id="78627-118">Other (business domain–specific) functions</span></span>](er-functions-category-other.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]