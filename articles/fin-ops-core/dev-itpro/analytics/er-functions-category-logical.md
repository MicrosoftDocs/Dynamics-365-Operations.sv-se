---
title: Lista över ER-funktioner i logisk kategori
description: Det här ämnet ger information om logiska funktionerna som stöds i elektronisk rapportering (ER).
author: NickSelin
manager: kfend
ms.date: 08/19/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
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
ms.openlocfilehash: a37b3341b05fde1283a21a0c52faec26cd1a7030
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/05/2020
ms.locfileid: "4686204"
---
# <a name="list-of-er-functions-in-the-logical-category"></a><span data-ttu-id="d17a3-103">Lista över ER-funktioner i logisk kategori</span><span class="sxs-lookup"><span data-stu-id="d17a3-103">List of ER functions in the logical category</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="d17a3-104">Logiska funktioner för elektronisk rapportering (ER) kan användas för att arbeta med logiska värden för att utföra mer än en jämförelse i ett enda uttryck eller testa flera villkor.</span><span class="sxs-lookup"><span data-stu-id="d17a3-104">Electronic reporting (ER) logical functions can be used to work with logical values to perform more than one comparison in a single expression or test multiple conditions.</span></span> <span data-ttu-id="d17a3-105">Det här avsnittet innehåller en sammanfattning av dessa funktioner.</span><span class="sxs-lookup"><span data-stu-id="d17a3-105">This topic provides a summary of these functions.</span></span>

## <a name="list-of-supported-functions"></a><span data-ttu-id="d17a3-106">Lista över funktioner som stöds</span><span class="sxs-lookup"><span data-stu-id="d17a3-106">List of supported functions</span></span>

| <span data-ttu-id="d17a3-107">Funktion</span><span class="sxs-lookup"><span data-stu-id="d17a3-107">Function</span></span> | <span data-ttu-id="d17a3-108">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="d17a3-108">Description</span></span> |
|----------|-------------|
| [<span data-ttu-id="d17a3-109">Och</span><span class="sxs-lookup"><span data-stu-id="d17a3-109">And</span></span>](er-functions-logical-and.md)                       | <span data-ttu-id="d17a3-110">Den här funktionen returnerar ett *booleskt* värde på **SANT** om alla angivna villkor är sant.</span><span class="sxs-lookup"><span data-stu-id="d17a3-110">This function returns a *Boolean* value of **TRUE** if all the specified conditions are true.</span></span> <span data-ttu-id="d17a3-111">Annars returnerar uttrycket värdet *boolesk* av **FALSK**.</span><span class="sxs-lookup"><span data-stu-id="d17a3-111">Otherwise, it returns a *Boolean* value of **FALSE**.</span></span> |
| [<span data-ttu-id="d17a3-112">Ärende</span><span class="sxs-lookup"><span data-stu-id="d17a3-112">Case</span></span>](er-functions-logical-case.md)                     | <span data-ttu-id="d17a3-113">Den här funktionen utvärderar värdet för det angivna uttrycket mot de angivna alternativa och returnerar resultatet av det första alternativet som är lika med värdet för det angivna uttrycket.</span><span class="sxs-lookup"><span data-stu-id="d17a3-113">This function evaluates the value of the specified expression against the specified alternative options and returns the result of the first option that equals the value of the specified expression.</span></span> <span data-ttu-id="d17a3-114">Annars returneras ett valfritt standard resultat om ett standard resultat anges som det sista argumentet för den anropade funktionen som inte föregås av ett alternativ.</span><span class="sxs-lookup"><span data-stu-id="d17a3-114">Otherwise, it returns an optional default result, if a default result is specified as the last argument of the called function that isn't preceded by an option.</span></span> <span data-ttu-id="d17a3-115">Värdet som returneras kan vara ett värde för någon av datatyperna som stöds.</span><span class="sxs-lookup"><span data-stu-id="d17a3-115">The value that is returned can be a value of any of the supported data types.</span></span> |
| [<span data-ttu-id="d17a3-116">Om</span><span class="sxs-lookup"><span data-stu-id="d17a3-116">If</span></span>](er-functions-logical-if.md)                         | <span data-ttu-id="d17a3-117">Denna funktion returnerar det första definierade värdet när det definierade villkoret uppfylls.</span><span class="sxs-lookup"><span data-stu-id="d17a3-117">This function returns the first specified value if the specified condition is met.</span></span> <span data-ttu-id="d17a3-118">Returnera annars det andra angivna värdet.</span><span class="sxs-lookup"><span data-stu-id="d17a3-118">Otherwise, it returns the second specified value.</span></span> <span data-ttu-id="d17a3-119">Värdet som returneras kan vara ett värde för någon av datatyperna som stöds.</span><span class="sxs-lookup"><span data-stu-id="d17a3-119">The value that is returned can be a value of any of the supported data types.</span></span> |
| [<span data-ttu-id="d17a3-120">Inte</span><span class="sxs-lookup"><span data-stu-id="d17a3-120">Not</span></span>](er-functions-logical-not.md)                       | <span data-ttu-id="d17a3-121">Den här funktionen returnerar omvända logiska värdet för det angivna villkoret som ett *Booleskt* värde.</span><span class="sxs-lookup"><span data-stu-id="d17a3-121">This function returns the reversed logical value of the specified condition as a *Boolean* value.</span></span> |
| [<span data-ttu-id="d17a3-122">Eller</span><span class="sxs-lookup"><span data-stu-id="d17a3-122">Or</span></span>](er-functions-logical-or.md)                         | <span data-ttu-id="d17a3-123">Den här funktionen returnerar ett *booleskt* värde på **FALSK** om alla angivna villkor är falsk.</span><span class="sxs-lookup"><span data-stu-id="d17a3-123">This function returns a *Boolean* value of **FALSE** if all the specified conditions are false.</span></span> <span data-ttu-id="d17a3-124">Den här funktionen returnerar ett *booleskt* värde på **SANT** om alla angivna villkor är sant.</span><span class="sxs-lookup"><span data-stu-id="d17a3-124">If any specified condition is true, the function returns a *Boolean* value of **TRUE**.</span></span> |
| [<span data-ttu-id="d17a3-125">ValueIn</span><span class="sxs-lookup"><span data-stu-id="d17a3-125">ValueIn</span></span>](er-functions-logical-valuein.md)               | <span data-ttu-id="d17a3-126">Denna funktion bestämmer om specifik indata matchar något värde för en angiven objekt i den angivna listan.</span><span class="sxs-lookup"><span data-stu-id="d17a3-126">This function determines whether the specified input matches any value of a specified item in the specified list.</span></span> <span data-ttu-id="d17a3-127">Det returnerar ett *booleskt* värde på **SANT** om den angivna indata matchar resultatet av att köra det angivna uttrycket för minst en post i den angivna listan.</span><span class="sxs-lookup"><span data-stu-id="d17a3-127">It returns a *Boolean* value of **TRUE** if the specified input matches the result of running the specified expression for at least one record of the specified list.</span></span> <span data-ttu-id="d17a3-128">Annars returnerar uttrycket värdet *boolesk* av **FALSK**.</span><span class="sxs-lookup"><span data-stu-id="d17a3-128">Otherwise, it returns a *Boolean* value of **FALSE**.</span></span> |
| [<span data-ttu-id="d17a3-129">ValueInLarge</span><span class="sxs-lookup"><span data-stu-id="d17a3-129">ValueInLarge</span></span>](er-functions-logical-valueinlarge.md)     | <span data-ttu-id="d17a3-130">Denna funktion bestämmer om specifik indata av typen *Int64* eller *heltal* matchar något värde för en angiven objekt i den angivna listan.</span><span class="sxs-lookup"><span data-stu-id="d17a3-130">This function determines whether the specified input of the *Int64* or *Integer* type matches any value of a specified item in the specified list.</span></span> <span data-ttu-id="d17a3-131">Det returnerar ett *booleskt* värde på **SANT** om den angivna indata matchar resultatet av att köra det angivna uttrycket för minst en post i den angivna listan.</span><span class="sxs-lookup"><span data-stu-id="d17a3-131">It returns a *Boolean* value of **TRUE** if the specified input matches the result of running the specified expression for at least one record of the specified list.</span></span> <span data-ttu-id="d17a3-132">Annars returnerar uttrycket värdet *boolesk* av **FALSK**.</span><span class="sxs-lookup"><span data-stu-id="d17a3-132">Otherwise, it returns a *Boolean* value of **FALSE**.</span></span> |


## <a name="additional-resources"></a><span data-ttu-id="d17a3-133">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="d17a3-133">Additional resources</span></span>

[<span data-ttu-id="d17a3-134">Översikt över elektronisk rapportering</span><span class="sxs-lookup"><span data-stu-id="d17a3-134">Electronic Reporting overview</span></span>](general-electronic-reporting.md)

[<span data-ttu-id="d17a3-135">Formeldesigner i elektronisk rapportering</span><span class="sxs-lookup"><span data-stu-id="d17a3-135">Formula designer in Electronic reporting</span></span>](general-electronic-reporting-formula-designer.md)

[<span data-ttu-id="d17a3-136">Formelspråk i elektronisk rapportering</span><span class="sxs-lookup"><span data-stu-id="d17a3-136">Electronic reporting formula language</span></span>](er-formula-language.md)
