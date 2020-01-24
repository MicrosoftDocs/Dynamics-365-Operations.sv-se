---
title: Lista över ER-funktioner i logisk kategori
description: Det här ämnet ger information om logiska funktionerna som stöds i elektronisk rapportering (ER).
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
ms.openlocfilehash: 408b3c5ec37b24e0ccf6e368012a936701eedf0f
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/20/2019
ms.locfileid: "2916647"
---
# <a name="list-of-er-functions-in-the-logical-category"></a><span data-ttu-id="05396-103">Lista över ER-funktioner i logisk kategori</span><span class="sxs-lookup"><span data-stu-id="05396-103">List of ER functions in the logical category</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="05396-104">Logiska funktioner för elektronisk rapportering (ER) kan användas för att arbeta med logiska värden för att utföra mer än en jämförelse i ett enda uttryck eller testa flera villkor.</span><span class="sxs-lookup"><span data-stu-id="05396-104">Electronic reporting (ER) logical functions can be used to work with logical values to perform more than one comparison in a single expression or test multiple conditions.</span></span> <span data-ttu-id="05396-105">Det här avsnittet innehåller en sammanfattning av dessa funktioner.</span><span class="sxs-lookup"><span data-stu-id="05396-105">This topic provides a summary of these functions.</span></span>

## <a name="list-of-supported-functions"></a><span data-ttu-id="05396-106">Lista över funktioner som stöds</span><span class="sxs-lookup"><span data-stu-id="05396-106">List of supported functions</span></span>

| <span data-ttu-id="05396-107">Funktion</span><span class="sxs-lookup"><span data-stu-id="05396-107">Function</span></span> | <span data-ttu-id="05396-108">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="05396-108">Description</span></span> |
|----------|-------------|
| [<span data-ttu-id="05396-109">Och</span><span class="sxs-lookup"><span data-stu-id="05396-109">And</span></span>](er-functions-logical-and.md)                       | <span data-ttu-id="05396-110">Den här funktionen returnerar ett *booleskt* värde på **SANT** om alla angivna villkor är sant.</span><span class="sxs-lookup"><span data-stu-id="05396-110">This function returns a *Boolean* value of **TRUE** if all the specified conditions are true.</span></span> <span data-ttu-id="05396-111">Annars returnerar uttrycket värdet *boolesk* av **FALSK**.</span><span class="sxs-lookup"><span data-stu-id="05396-111">Otherwise, it returns a *Boolean* value of **FALSE**.</span></span> |
| [<span data-ttu-id="05396-112">Ärende</span><span class="sxs-lookup"><span data-stu-id="05396-112">Case</span></span>](er-functions-logical-case.md)                     | <span data-ttu-id="05396-113">Den här funktionen utvärderar värdet för det angivna uttrycket mot de angivna alternativa och returnerar resultatet av det första alternativet som är lika med värdet för det angivna uttrycket.</span><span class="sxs-lookup"><span data-stu-id="05396-113">This function evaluates the value of the specified expression against the specified alternative options and returns the result of the first option that equals the value of the specified expression.</span></span> <span data-ttu-id="05396-114">Annars returneras ett valfritt standard resultat om ett standard resultat anges som det sista argumentet för den anropade funktionen som inte föregås av ett alternativ.</span><span class="sxs-lookup"><span data-stu-id="05396-114">Otherwise, it returns an optional default result, if a default result is specified as the last argument of the called function that isn't preceded by an option.</span></span> <span data-ttu-id="05396-115">Värdet som returneras kan vara ett värde för någon av datatyperna som stöds.</span><span class="sxs-lookup"><span data-stu-id="05396-115">The value that is returned can be a value of any of the supported data types.</span></span> |
| [<span data-ttu-id="05396-116">Om</span><span class="sxs-lookup"><span data-stu-id="05396-116">If</span></span>](er-functions-logical-if.md)                         | <span data-ttu-id="05396-117">Denna funktion returnerar det första definierade värdet när det definierade villkoret uppfylls.</span><span class="sxs-lookup"><span data-stu-id="05396-117">This function returns the first specified value if the specified condition is met.</span></span> <span data-ttu-id="05396-118">Returnera annars det andra angivna värdet.</span><span class="sxs-lookup"><span data-stu-id="05396-118">Otherwise, it returns the second specified value.</span></span> <span data-ttu-id="05396-119">Värdet som returneras kan vara ett värde för någon av datatyperna som stöds.</span><span class="sxs-lookup"><span data-stu-id="05396-119">The value that is returned can be a value of any of the supported data types.</span></span> |
| [<span data-ttu-id="05396-120">Inte</span><span class="sxs-lookup"><span data-stu-id="05396-120">Not</span></span>](er-functions-logical-not.md)                       | <span data-ttu-id="05396-121">Den här funktionen returnerar omvända logiska värdet för det angivna villkoret som ett *Booleskt* värde.</span><span class="sxs-lookup"><span data-stu-id="05396-121">This function returns the reversed logical value of the specified condition as a *Boolean* value.</span></span> |
| [<span data-ttu-id="05396-122">Eller</span><span class="sxs-lookup"><span data-stu-id="05396-122">Or</span></span>](er-functions-logical-or.md)                         | <span data-ttu-id="05396-123">Den här funktionen returnerar ett *booleskt* värde på **FALSK** om alla angivna villkor är falsk.</span><span class="sxs-lookup"><span data-stu-id="05396-123">This function returns a *Boolean* value of **FALSE** if all the specified conditions are false.</span></span> <span data-ttu-id="05396-124">Den här funktionen returnerar ett *booleskt* värde på **SANT** om alla angivna villkor är sant.</span><span class="sxs-lookup"><span data-stu-id="05396-124">If any specified condition is true, the function returns a *Boolean* value of **TRUE**.</span></span> |
| [<span data-ttu-id="05396-125">ValueIn</span><span class="sxs-lookup"><span data-stu-id="05396-125">ValueIn</span></span>](er-functions-logical-valuein.md)               | <span data-ttu-id="05396-126">Denna funktion bestämmer om specifik indata matchar något värde för en angiven objekt i den angivna listan.</span><span class="sxs-lookup"><span data-stu-id="05396-126">This function determines whether the specified input matches any value of a specified item in the specified list.</span></span> <span data-ttu-id="05396-127">Det returnerar ett *booleskt* värde på **SANT** om den angivna indata matchar resultatet av att köra det angivna uttrycket för minst en post i den angivna listan.</span><span class="sxs-lookup"><span data-stu-id="05396-127">It returns a *Boolean* value of **TRUE** if the specified input matches the result of running the specified expression for at least one record of the specified list.</span></span> <span data-ttu-id="05396-128">Annars returnerar uttrycket värdet *boolesk* av **FALSK**.</span><span class="sxs-lookup"><span data-stu-id="05396-128">Otherwise, it returns a *Boolean* value of **FALSE**.</span></span> |

## <a name="additional-resources"></a><span data-ttu-id="05396-129">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="05396-129">Additional resources</span></span>

[<span data-ttu-id="05396-130">Översikt över elektronisk rapportering</span><span class="sxs-lookup"><span data-stu-id="05396-130">Electronic Reporting overview</span></span>](general-electronic-reporting.md)

[<span data-ttu-id="05396-131">Formeldesigner i elektronisk rapportering</span><span class="sxs-lookup"><span data-stu-id="05396-131">Formula designer in Electronic reporting</span></span>](general-electronic-reporting-formula-designer.md)

[<span data-ttu-id="05396-132">Formelspråk i elektronisk rapportering</span><span class="sxs-lookup"><span data-stu-id="05396-132">Electronic reporting formula language</span></span>](er-formula-language.md)
