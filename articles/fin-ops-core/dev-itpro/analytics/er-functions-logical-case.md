---
title: CASE ER-funktion
description: Det här avsnittet innehåller information om hur funktionen CASE elektronisk rapportering (ER) används.
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
ms.openlocfilehash: 3bba9cd190db61fda3636cc3c8093030f886b9bd
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/12/2020
ms.locfileid: "3041778"
---
# <span data-ttu-id="05149-103"><a name="CASE">CASE ER-funktion</a></span><span class="sxs-lookup"><span data-stu-id="05149-103"><a name="CASE">CASE ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="05149-104">`CASE`-funktionen utvärderar värdet för det angivna uttrycket mot de angivna alternativa och returnerar resultatet av det första alternativet som är lika med värdet för det angivna uttrycket.</span><span class="sxs-lookup"><span data-stu-id="05149-104">The `CASE` function evaluates the value of the specified expression against the specified alternative options and returns the result of the first option that equals the value of the specified expression.</span></span> <span data-ttu-id="05149-105">Annars returneras ett valfritt standard resultat om ett standard resultat anges som det sista argumentet för den anropade funktionen som inte föregås av ett alternativ.</span><span class="sxs-lookup"><span data-stu-id="05149-105">Otherwise, it returns the optional default result, if a default result is specified as the last argument of the called function that isn't preceded by an option.</span></span> <span data-ttu-id="05149-106">Värdet som returneras kan vara ett värde för någon av datatyperna som stöds.</span><span class="sxs-lookup"><span data-stu-id="05149-106">The value that is returned can be a value of any of the supported data types.</span></span>

## <a name="syntax"></a><span data-ttu-id="05149-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="05149-107">Syntax</span></span>

```vb
CASE (expression, option 1, result 1[, option 2, result 2, …, option N, result N, default result])
```

## <a name="arguments"></a><span data-ttu-id="05149-108">Argument</span><span class="sxs-lookup"><span data-stu-id="05149-108">Arguments</span></span>

<span data-ttu-id="05149-109">`expression`: *Primitiv datatyp* (booleskt, numeriskt eller text)</span><span class="sxs-lookup"><span data-stu-id="05149-109">`expression`: *Primitive data type* (Boolean, numeric, or text)</span></span>

<span data-ttu-id="05149-110">Ett giltigt uttryck som returnerar ett värde av den primitiva datatypen.</span><span class="sxs-lookup"><span data-stu-id="05149-110">A valid expression that returns a value of the primitive data type.</span></span>

<span data-ttu-id="05149-111">`option 1`: *Primitiv datatyp* (booleskt, numeriskt eller text)</span><span class="sxs-lookup"><span data-stu-id="05149-111">`option 1`: *Primitive data type* (Boolean, numeric, or text)</span></span>

<span data-ttu-id="05149-112">Ett giltigt uttryck som returnerar ett värde av samma primitiva datatyp som `expression`-argumentet för den anropade funktionen.</span><span class="sxs-lookup"><span data-stu-id="05149-112">A valid expression that returns a value of the same primitive data type as the `expression` argument of the called function.</span></span> <span data-ttu-id="05149-113">Detta argument krävs.</span><span class="sxs-lookup"><span data-stu-id="05149-113">This argument is required.</span></span>

<span data-ttu-id="05149-114">`result 1`: *Någon av de datatyper som stöds*</span><span class="sxs-lookup"><span data-stu-id="05149-114">`result 1`: *Any of the supported data types*</span></span>

<span data-ttu-id="05149-115">Det returnerade resultatet som motsvarar det föregående alternativet.</span><span class="sxs-lookup"><span data-stu-id="05149-115">The returned result that corresponds to the preceding option.</span></span> <span data-ttu-id="05149-116">Detta argument krävs.</span><span class="sxs-lookup"><span data-stu-id="05149-116">This argument is required.</span></span>

<span data-ttu-id="05149-117">`option N`: *Primitiv datatyp* (booleskt, numeriskt eller text)</span><span class="sxs-lookup"><span data-stu-id="05149-117">`option N`: *Primitive data type* (Boolean, numeric, or text)</span></span>

<span data-ttu-id="05149-118">Ett giltigt uttryck som returnerar ett värde av samma primitiva datatyp som `expression`-argumentet för den anropade funktionen.</span><span class="sxs-lookup"><span data-stu-id="05149-118">A valid expression that returns a value of the same primitive data type as the `expression` argument of the called function.</span></span> <span data-ttu-id="05149-119">Detta argument är valfritt.</span><span class="sxs-lookup"><span data-stu-id="05149-119">This argument is optional.</span></span>

<span data-ttu-id="05149-120">`result N`: *Någon av de datatyper som stöds*</span><span class="sxs-lookup"><span data-stu-id="05149-120">`result N`: *Any of the supported data types*</span></span>

<span data-ttu-id="05149-121">Det returnerade resultatet som motsvarar det föregående alternativet.</span><span class="sxs-lookup"><span data-stu-id="05149-121">The returned result that corresponds to the preceding option.</span></span> <span data-ttu-id="05149-122">Detta argument är valfritt.</span><span class="sxs-lookup"><span data-stu-id="05149-122">This argument is optional.</span></span>

<span data-ttu-id="05149-123">`default result`: *Någon av de datatyper som stöds*</span><span class="sxs-lookup"><span data-stu-id="05149-123">`default result`: *Any of the supported data types*</span></span>

<span data-ttu-id="05149-124">Resultatet som ska returneras om det inte finns någon matchning.</span><span class="sxs-lookup"><span data-stu-id="05149-124">The result that should be returned if there is no match.</span></span> <span data-ttu-id="05149-125">Detta argument är valfritt.</span><span class="sxs-lookup"><span data-stu-id="05149-125">This argument is optional.</span></span>

## <a name="return-values"></a><span data-ttu-id="05149-126">Returvärden</span><span class="sxs-lookup"><span data-stu-id="05149-126">Return values</span></span>

<span data-ttu-id="05149-127">*Någon av de datatyper som stöds*</span><span class="sxs-lookup"><span data-stu-id="05149-127">*Any of the supported data types*</span></span>

<span data-ttu-id="05149-128">Resultatvärdet för någon av datatyperna som stöds.</span><span class="sxs-lookup"><span data-stu-id="05149-128">The resulting value of any of the supported data types.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="05149-129">Användningsanteckningar</span><span class="sxs-lookup"><span data-stu-id="05149-129">Usage notes</span></span>

<span data-ttu-id="05149-130">Ett undantagsfel utlöses vid körning om det inte finns någon matchning och ett valfritt standard resultat inte har definierats.</span><span class="sxs-lookup"><span data-stu-id="05149-130">An exception is thrown at runtime if there is no match and an optional default result isn't defined.</span></span>

<span data-ttu-id="05149-131">Alla resultat måste anges med samma datatyp.</span><span class="sxs-lookup"><span data-stu-id="05149-131">All results must be specified by using the same data type.</span></span> <span data-ttu-id="05149-132">Ett undantag genereras vid designtillfället om datatyperna för de konfigurerade resultaten inte matchar.</span><span class="sxs-lookup"><span data-stu-id="05149-132">An exception is thrown at design time if the data types of the configured results don't match.</span></span>

<span data-ttu-id="05149-133">Om det första resultatvärdet och *N*th resultatvärdet är värden för datatypen *behållare (post)* eller *postlista* har resultatet bara de fält som finns i båda värdena.</span><span class="sxs-lookup"><span data-stu-id="05149-133">If the first result value and the *N*th result value are values of the *Container (record)* or *Record list* data type, the result has only the fields that exist in both values.</span></span>

## <a name="example"></a><span data-ttu-id="05149-134">Exempel</span><span class="sxs-lookup"><span data-stu-id="05149-134">Example</span></span>

<span data-ttu-id="05149-135">`CASE( DATETIMEFORMAT( NOW(), "MM"), "10", "WINTER", "11", "WINTER", "12", "WINTER", "")` returnerar strängen **"WINTER"** om det aktuella programsessionsdatumet är mellan oktober och december.</span><span class="sxs-lookup"><span data-stu-id="05149-135">`CASE( DATETIMEFORMAT( NOW(), "MM"), "10", "WINTER", "11", "WINTER", "12", "WINTER", "")` returns the string **"WINTER"** if the current application session date is between October and December.</span></span> <span data-ttu-id="05149-136">Annars returneras en tom sträng.</span><span class="sxs-lookup"><span data-stu-id="05149-136">Otherwise, it returns a blank string.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="05149-137">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="05149-137">Additional resources</span></span>

[<span data-ttu-id="05149-138">Logiska funktioner</span><span class="sxs-lookup"><span data-stu-id="05149-138">Logical functions</span></span>](er-functions-category-logical.md)
