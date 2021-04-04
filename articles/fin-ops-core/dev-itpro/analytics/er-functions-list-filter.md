---
title: FILTER ER-funktion
description: Det här avsnittet innehåller information om hur funktionen FILTER elektronisk rapportering (ER) används.
author: NickSelin
manager: kfend
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
ms.openlocfilehash: 0e90db1836a93dab42be5dc91e9ea478163a1437
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/09/2021
ms.locfileid: "5559709"
---
# <a name="filter-er-function"></a><span data-ttu-id="e55d8-103">FILTER ER-funktion</span><span class="sxs-lookup"><span data-stu-id="e55d8-103">FILTER ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="e55d8-104">`FILTER`-funktionen returnerar den angivna listan som ett värde för *postlista* efter att frågan har ändrats så att dess filter enligt det angivna villkoret.</span><span class="sxs-lookup"><span data-stu-id="e55d8-104">The `FILTER` function returns the specified list as a *Record list* value after the query has been changed so that it filters for the specified condition.</span></span>

## <a name="syntax"></a><span data-ttu-id="e55d8-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="e55d8-105">Syntax</span></span>

```vb
FILTER (list, condition)
```

## <a name="arguments"></a><span data-ttu-id="e55d8-106">Argument</span><span class="sxs-lookup"><span data-stu-id="e55d8-106">Arguments</span></span>

<span data-ttu-id="e55d8-107">`list`: *Post-lista*</span><span class="sxs-lookup"><span data-stu-id="e55d8-107">`list`: *Record list*</span></span>

<span data-ttu-id="e55d8-108">Den giltiga sökvägen av en datakälla för datatypen *Postlista*.</span><span class="sxs-lookup"><span data-stu-id="e55d8-108">The valid path of a data source of the *Record list* data type.</span></span>

<span data-ttu-id="e55d8-109">`condition`: *Boolesk*</span><span class="sxs-lookup"><span data-stu-id="e55d8-109">`condition`: *Boolean*</span></span>

<span data-ttu-id="e55d8-110">Ett giltigt villkorsuttryck som används för att filtrera poster i den angivna listan.</span><span class="sxs-lookup"><span data-stu-id="e55d8-110">A valid conditional expression that is used to filter records of the specified list.</span></span>

## <a name="return-values"></a><span data-ttu-id="e55d8-111">Returvärden</span><span class="sxs-lookup"><span data-stu-id="e55d8-111">Return values</span></span>

<span data-ttu-id="e55d8-112">*Post-lista*</span><span class="sxs-lookup"><span data-stu-id="e55d8-112">*Record list*</span></span>

<span data-ttu-id="e55d8-113">Den resulterande listan med poster.</span><span class="sxs-lookup"><span data-stu-id="e55d8-113">The resulting list of records.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="e55d8-114">Användningsanteckningar</span><span class="sxs-lookup"><span data-stu-id="e55d8-114">Usage notes</span></span>

<span data-ttu-id="e55d8-115">Till skillnad från funktionen [WHERE](er-functions-list-where.md) tillämpas angivet villkor på alla ER-datakällor (elektronisk rapportering) av typen *Tabellregister* på databasnivå.</span><span class="sxs-lookup"><span data-stu-id="e55d8-115">This function differs from the [WHERE](er-functions-list-where.md) function, because the specified condition is applied to any Electronic reporting (ER) data source of the *Table records* type at the database level.</span></span> <span data-ttu-id="e55d8-116">Listan och villkoret kan definieras med hjälp av tabeller och relationer.</span><span class="sxs-lookup"><span data-stu-id="e55d8-116">The list and condition can be defined by using tables and relations.</span></span>

<span data-ttu-id="e55d8-117">Om ett eller båda argument som har konfigurerats för den här funktionen (`list` och `condition`) inte tillåter att den här begäran översätts till direkt SQL-anrop, genereras ett undantag vid designtillfället.</span><span class="sxs-lookup"><span data-stu-id="e55d8-117">If one or both arguments that are configured for this function (`list` and `condition`) don't allow this request to be translated to the direct SQL call, an exception is thrown at design time.</span></span> <span data-ttu-id="e55d8-118">Det här undantaget informerar användaren om att antingen `list` eller `condition` inte kan användas för att fråga databasen.</span><span class="sxs-lookup"><span data-stu-id="e55d8-118">This exception informs the user that either `list` or `condition` can't be used to query the database.</span></span>

## <a name="example-1"></a><span data-ttu-id="e55d8-119">Exempel 1</span><span class="sxs-lookup"><span data-stu-id="e55d8-119">Example 1</span></span>

<span data-ttu-id="e55d8-120">Om **Leverantör** konfigureras som en ER-datakälla som refererar till registret VendTable, returnerar uttrycket `FILTER (Vendors, Vendors.VendGroup = "40")` en lista över endast de leverantörer som ingår i leverantörsgrupp 40.</span><span class="sxs-lookup"><span data-stu-id="e55d8-120">If **Vendor** is configured as an ER data source that refers to the VendTable table, the expression `FILTER (Vendors, Vendors.VendGroup = "40")` returns a list of only vendors that belong to vendor group 40.</span></span>

## <a name="example-2"></a><span data-ttu-id="e55d8-121">Exempel 2</span><span class="sxs-lookup"><span data-stu-id="e55d8-121">Example 2</span></span>

<span data-ttu-id="e55d8-122">Om **Leverantör** konfigureras som en ER-datakälla som hänvisar till VendTable-registret och om **parmVendorBankGroup** konfigureras som en ER-datakälla som returnerar ett värde av datatypen *Sträng* returnerar uttrycket `FILTER ( Vendor.'<Relations'.VendBankAccount, Vendor.'<Relations'.VendBankAccount.BankGroupID = parmVendorBankGroup)` returnerar en lista över just de leverantörskonton som tillhör en viss bankgrupp.</span><span class="sxs-lookup"><span data-stu-id="e55d8-122">If **Vendor** is configured as an ER data source that refers to the VendTable table, and if **parmVendorBankGroup** is configured as an ER data source that returns a value of the *String* data type, the expression `FILTER ( Vendor.'<Relations'.VendBankAccount, Vendor.'<Relations'.VendBankAccount.BankGroupID = parmVendorBankGroup)` returns a list of only vendor accounts that belong to a specific bank group.</span></span>

## <a name="example-3"></a><span data-ttu-id="e55d8-123">Exempel 3</span><span class="sxs-lookup"><span data-stu-id="e55d8-123">Example 3</span></span>

<span data-ttu-id="e55d8-124">Du anger datakällan **DS** för typen *beräknat fält* som innehåller uttrycket `SPLIT ("A,B,C", ",")`.</span><span class="sxs-lookup"><span data-stu-id="e55d8-124">You enter data source **DS** of the *Calculated field* type, and it contains the expression `SPLIT ("A,B,C", ",")`.</span></span> <span data-ttu-id="e55d8-125">Du anger sedan ett annat uttryck `FILTER( DS, DS.Value = "B")`.</span><span class="sxs-lookup"><span data-stu-id="e55d8-125">You then enter another expression, `FILTER( DS, DS.Value = "B")`.</span></span> <span data-ttu-id="e55d8-126">När du försöker spara det här uttrycket i ER formeldesigner, genereras följande undantag: "valideringsfel: listuttrycket för FILTER-funktionen är inte frågningsbar."</span><span class="sxs-lookup"><span data-stu-id="e55d8-126">When you try to save this expression in the ER formula designer, the following exception is thrown: "Validation error: The list expression of FILTER function is not queryable."</span></span>

## <a name="additional-resources"></a><span data-ttu-id="e55d8-127">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="e55d8-127">Additional resources</span></span>

[<span data-ttu-id="e55d8-128">Lista över funktioner</span><span class="sxs-lookup"><span data-stu-id="e55d8-128">List functions</span></span>](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]