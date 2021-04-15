---
title: IF ER-funktion
description: Det här avsnittet innehåller information om hur funktionen IF elektronisk rapportering (ER) används.
author: NickSelin
ms.date: 12/12/2019
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
ms.openlocfilehash: 3674618acae79170daf94413895d17d86a491996
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5753178"
---
# <a name="if-er-function"></a><span data-ttu-id="8acf6-103">IF ER-funktion</span><span class="sxs-lookup"><span data-stu-id="8acf6-103">IF ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="8acf6-104">`IF`-funktionen returnerar det första definierade värdet när det definierade villkoret uppfylls.</span><span class="sxs-lookup"><span data-stu-id="8acf6-104">The `IF` function returns the first specified value if the specified condition is met.</span></span> <span data-ttu-id="8acf6-105">Returnera annars det andra angivna värdet.</span><span class="sxs-lookup"><span data-stu-id="8acf6-105">Otherwise, it returns the second specified value.</span></span> <span data-ttu-id="8acf6-106">Värdet som returneras kan vara ett värde för någon av datatyperna som stöds.</span><span class="sxs-lookup"><span data-stu-id="8acf6-106">The value that is returned can be a value of any of the supported data types.</span></span>

## <a name="syntax"></a><span data-ttu-id="8acf6-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="8acf6-107">Syntax</span></span>

```vb
IF (condition, first value, second value) as any of the supported data types
```

## <a name="arguments"></a><span data-ttu-id="8acf6-108">Argument</span><span class="sxs-lookup"><span data-stu-id="8acf6-108">Arguments</span></span>

<span data-ttu-id="8acf6-109">`condition`: *Boolesk*</span><span class="sxs-lookup"><span data-stu-id="8acf6-109">`condition`: *Boolean*</span></span>

<span data-ttu-id="8acf6-110">Ett giltigt villkorsuttryck som måste testas.</span><span class="sxs-lookup"><span data-stu-id="8acf6-110">A valid conditional expression that must be tested.</span></span>

<span data-ttu-id="8acf6-111">`first value`: *Någon av de datatyper som stöds*</span><span class="sxs-lookup"><span data-stu-id="8acf6-111">`first value`: *Any of the supported data types*</span></span>

<span data-ttu-id="8acf6-112">Resultatet som returneras om villkoret uppfylls.</span><span class="sxs-lookup"><span data-stu-id="8acf6-112">The result that is returned if the condition is met.</span></span>

<span data-ttu-id="8acf6-113">`second value`: *Någon av de datatyper som stöds*</span><span class="sxs-lookup"><span data-stu-id="8acf6-113">`second value`: *Any of the supported data types*</span></span>

<span data-ttu-id="8acf6-114">Resultatet som returneras om villkoret inte uppfylls.</span><span class="sxs-lookup"><span data-stu-id="8acf6-114">The result that is returned if the condition isn't met.</span></span>

## <a name="return-values"></a><span data-ttu-id="8acf6-115">Returvärden</span><span class="sxs-lookup"><span data-stu-id="8acf6-115">Return values</span></span>

<span data-ttu-id="8acf6-116">*Någon av de datatyper som stöds*</span><span class="sxs-lookup"><span data-stu-id="8acf6-116">*Any of the supported data types*</span></span>

<span data-ttu-id="8acf6-117">Resultatvärdet för någon av datatyperna som stöds.</span><span class="sxs-lookup"><span data-stu-id="8acf6-117">The resulting value of any of the supported data types.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="8acf6-118">Användningsanteckningar</span><span class="sxs-lookup"><span data-stu-id="8acf6-118">Usage notes</span></span>

<span data-ttu-id="8acf6-119">`first value` och `second value`-argumenten måste anges med samma datatyp.</span><span class="sxs-lookup"><span data-stu-id="8acf6-119">The `first value` and `second value` arguments must be specified by using the same data type.</span></span> <span data-ttu-id="8acf6-120">Ett undantag genereras vid designtillfället om datatyperna för de konfigurerade värdena inte matchar.</span><span class="sxs-lookup"><span data-stu-id="8acf6-120">An exception is thrown at design time if the data types of the configured values don't match.</span></span>

<span data-ttu-id="8acf6-121">Om det första värdet och det andra värdet är värden för datatypen *behållare (post*) eller *postlista*, har resultatet bara de fält som finns i båda värdena.</span><span class="sxs-lookup"><span data-stu-id="8acf6-121">If the first value and the second value are values of the *Container (record)* or *Record list* data type, the result has only the fields that exist in both values.</span></span>

## <a name="example"></a><span data-ttu-id="8acf6-122">Exempel</span><span class="sxs-lookup"><span data-stu-id="8acf6-122">Example</span></span>

<span data-ttu-id="8acf6-123">`IF (1=2, "condition is met", "condition is not met")` returnerar strängen **"villkoret är inte uppfyllt"**.</span><span class="sxs-lookup"><span data-stu-id="8acf6-123">`IF (1=2, "condition is met", "condition is not met")` returns the string **"condition is not met"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="8acf6-124">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="8acf6-124">Additional resources</span></span>

[<span data-ttu-id="8acf6-125">Logiska funktioner</span><span class="sxs-lookup"><span data-stu-id="8acf6-125">Logical functions</span></span>](er-functions-category-logical.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]