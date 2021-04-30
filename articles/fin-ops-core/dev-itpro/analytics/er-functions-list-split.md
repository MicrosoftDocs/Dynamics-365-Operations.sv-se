---
title: Funktionen SPLIT ER
description: Det här avsnittet innehåller information om hur funktionen SPLIT elektronisk rapportering (ER) används.
author: NickSelin
ms.date: 04/01/2021
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
ms.openlocfilehash: 26b6ddeb2880fc220283b6389327a497549a4511
ms.sourcegitcommit: 74f5b04b482b2ae023c728e0df0eb78305493c6a
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/02/2021
ms.locfileid: "5853453"
---
# <a name="split-er-function"></a><span data-ttu-id="bdbeb-103">Funktionen SPLIT ER</span><span class="sxs-lookup"><span data-stu-id="bdbeb-103">SPLIT ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="bdbeb-104">`SPLIT`-funktionen delar den angivna indatasträngen i delsträngar och returnerar resultatet som ett nytt värde för *postlistan*.</span><span class="sxs-lookup"><span data-stu-id="bdbeb-104">The `SPLIT` function splits the specified input string into substrings and returns the result as a new *Record list* value.</span></span>

## <a name="syntax-1"></a><span data-ttu-id="bdbeb-105">Syntax 1</span><span class="sxs-lookup"><span data-stu-id="bdbeb-105">Syntax 1</span></span>

```vb
SPLIT (input, length)
```

<span data-ttu-id="bdbeb-106">Denna syntax används för att dela upp den definierade indatasträngen i delsträngar som var och en är av den definierade längden.</span><span class="sxs-lookup"><span data-stu-id="bdbeb-106">This syntax is used to split the specified input string into substrings, each of which has the specified length.</span></span>

## <a name="syntax-2"></a><span data-ttu-id="bdbeb-107">Syntax 2</span><span class="sxs-lookup"><span data-stu-id="bdbeb-107">Syntax 2</span></span>

```vb
SPLIT (input, delimiter)
```

<span data-ttu-id="bdbeb-108">Dennna syntax används för att dela upp den definierade indatasträngen i delsträngar baserat på den definierade avgränsaren.</span><span class="sxs-lookup"><span data-stu-id="bdbeb-108">This syntax is used to split the specified input string into substrings, based on the specified delimiter.</span></span>

## <a name="arguments"></a><span data-ttu-id="bdbeb-109">Argument</span><span class="sxs-lookup"><span data-stu-id="bdbeb-109">Arguments</span></span>

<span data-ttu-id="bdbeb-110">`input`: *Sträng*</span><span class="sxs-lookup"><span data-stu-id="bdbeb-110">`input`: *String*</span></span>

<span data-ttu-id="bdbeb-111">Texten som ska delas upp</span><span class="sxs-lookup"><span data-stu-id="bdbeb-111">The text to split.</span></span>

<span data-ttu-id="bdbeb-112">`length`: *Heltal*</span><span class="sxs-lookup"><span data-stu-id="bdbeb-112">`length`: *Integer*</span></span>

<span data-ttu-id="bdbeb-113">Den maximala längden för en enskild delsträng.</span><span class="sxs-lookup"><span data-stu-id="bdbeb-113">The maximum length of a single substring.</span></span>

<span data-ttu-id="bdbeb-114">`delimiter`: *Sträng*</span><span class="sxs-lookup"><span data-stu-id="bdbeb-114">`delimiter`: *String*</span></span>

<span data-ttu-id="bdbeb-115">En avgränsare som används för att avgränsa delsträngar.</span><span class="sxs-lookup"><span data-stu-id="bdbeb-115">A delimiter that is used to separate substrings.</span></span>

## <a name="return-values"></a><span data-ttu-id="bdbeb-116">Returvärden</span><span class="sxs-lookup"><span data-stu-id="bdbeb-116">Return values</span></span>

<span data-ttu-id="bdbeb-117">*Post-lista*</span><span class="sxs-lookup"><span data-stu-id="bdbeb-117">*Record list*</span></span>

<span data-ttu-id="bdbeb-118">Den resulterande listan med poster.</span><span class="sxs-lookup"><span data-stu-id="bdbeb-118">The resulting list of records.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="bdbeb-119">Användningsanteckningar</span><span class="sxs-lookup"><span data-stu-id="bdbeb-119">Usage notes</span></span>

<span data-ttu-id="bdbeb-120">Poststrukturen i listan som returneras består av fältet **Värde** av typen *Sträng*.</span><span class="sxs-lookup"><span data-stu-id="bdbeb-120">The record structure of the list that is returned consists of the **Value** field of the *String* type.</span></span> <span data-ttu-id="bdbeb-121">Varje post i listan som returneras innehåller genererade delsträngar i det här fältet.</span><span class="sxs-lookup"><span data-stu-id="bdbeb-121">Every record of the list that is returned contains generated substrings in this field.</span></span>

<span data-ttu-id="bdbeb-122">Om argumentet `delimiter` är tom returneras en ny lista som består av en post med ett fält för **Värde** av typen *Sträng*.</span><span class="sxs-lookup"><span data-stu-id="bdbeb-122">If the `delimiter` argument is empty, the new list that is returned consists of one record that has the **Value** field of the *String* type.</span></span> <span data-ttu-id="bdbeb-123">Det här fältet innehåller indatatext.</span><span class="sxs-lookup"><span data-stu-id="bdbeb-123">This field contains the input text.</span></span>

<span data-ttu-id="bdbeb-124">Om argumentet `input` är tomt returneras en tom ny lista.</span><span class="sxs-lookup"><span data-stu-id="bdbeb-124">If the `input` argument is empty, a new empty list is returned.</span></span> <span data-ttu-id="bdbeb-125">Om antingen `input` eller `delimiter` är ospecificerad (null) kastas ett programundantag.</span><span class="sxs-lookup"><span data-stu-id="bdbeb-125">If either the `input` or `delimiter` argument is unspecified (null), an application exception is thrown.</span></span>

## <a name="example-1"></a><span data-ttu-id="bdbeb-126">Exempel 1</span><span class="sxs-lookup"><span data-stu-id="bdbeb-126">Example 1</span></span>

<span data-ttu-id="bdbeb-127">`SPLIT ("abcd", 3)` returnerar en ny lista som består av två poster som har fältet **Värde** av typen *Sträng*.</span><span class="sxs-lookup"><span data-stu-id="bdbeb-127">`SPLIT ("abcd", 3)` returns a new list that consists of two records that have the **Value** field of the *String* type.</span></span> <span data-ttu-id="bdbeb-128">Fältet **Värde** i den första posten innehåller texten **"abc"** och fältet **Värde** i den andra posten innehåller texten **"d**".</span><span class="sxs-lookup"><span data-stu-id="bdbeb-128">The **Value** field in the first record contains the text **"abc"**, and the **Value** field in the second record contains the text **"d"**.</span></span>

## <a name="example-2"></a><span data-ttu-id="bdbeb-129">Exempel 2</span><span class="sxs-lookup"><span data-stu-id="bdbeb-129">Example 2</span></span>

<span data-ttu-id="bdbeb-130">`SPLIT ("XAb aBy", "aB")` returnerar en ny lista som består av tre poster som har fältet **Värde** av typen *Sträng*.</span><span class="sxs-lookup"><span data-stu-id="bdbeb-130">`SPLIT ("XAb aBy", "aB")` returns a new list that consists of three records that have the **Value** field of the *String* type.</span></span> <span data-ttu-id="bdbeb-131">Fältet **Värde** i den första posten innehåller texten **"X"**, fältet **Värde** i den andra posten innehåller texten **"&nbsp;"** och fältet **Värde** i den tredje posten innehåller texten **"y"**.</span><span class="sxs-lookup"><span data-stu-id="bdbeb-131">The **Value** field in the first record contains the text **"X"**, the **Value** field in the second record contains the text **"&nbsp;"**, and the **Value** field in the third record contains the text **"y"**.</span></span> 

## <a name="example-3"></a><span data-ttu-id="bdbeb-132">Exempel 3</span><span class="sxs-lookup"><span data-stu-id="bdbeb-132">Example 3</span></span>

<span data-ttu-id="bdbeb-133">Du kan använda funktionen [INDEX](er-functions-list-index.md) för att komma åt enskilda element i den angivna inmatningssträngen.</span><span class="sxs-lookup"><span data-stu-id="bdbeb-133">Yo can use the [INDEX](er-functions-list-index.md) function to access individual elements of the specified input string.</span></span> <span data-ttu-id="bdbeb-134">Om du anger datakällan **MyList** för typen **Beräknat fält** och konfigurerar denna för uttrycket `SPLIT("abc", 1)`, kommer uttrycket `INDEX(MyList,2).Value` att returnera textvärdet **"b"**.</span><span class="sxs-lookup"><span data-stu-id="bdbeb-134">If you enter the **MyList** data source of the **Calculated field** type and configure for it the `SPLIT("abc", 1)` expression, the expression `INDEX(MyList,2).Value` returns the text **"b"**.</span></span>

## <a name="example-4"></a><span data-ttu-id="bdbeb-135">Exempel 4</span><span class="sxs-lookup"><span data-stu-id="bdbeb-135">Example 4</span></span>

<span data-ttu-id="bdbeb-136">Funktionen [ENUMERATE](er-functions-list-enumerate.md) kan också ge dig åtkomst till enskilda element för angiven inmatningssträng.</span><span class="sxs-lookup"><span data-stu-id="bdbeb-136">The [ENUMERATE](er-functions-list-enumerate.md) function can also help you access individual elements of the specified input string.</span></span> <span data-ttu-id="bdbeb-137">Om du först anger datakällan **MyList** för typen **Beräknat fält** och konfigurerar denna för uttrycket `SPLIT("abc", 1)`, samt därefter anger datakällan **EnumeratedList** för typen **Beräknat fält** och konfigurerar denna för uttrycket `ENUMERATE(MyList)`, kommer uttrycket `FIRSTORNULL(WHERE(EnumeratedList, EnumeratedList.Number=2)).Value` att returnera texten **"b"**.</span><span class="sxs-lookup"><span data-stu-id="bdbeb-137">If you first enter the **MyList** data source of the **Calculated field** type and configure for it the `SPLIT("abc", 1)` expression, and then enter the **EnumeratedList** data source of the **Calculated field** type and configure for it the `ENUMERATE(MyList)` expression, the expression `FIRSTORNULL(WHERE(EnumeratedList, EnumeratedList.Number=2)).Value` returns the text **"b"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="bdbeb-138">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="bdbeb-138">Additional resources</span></span>

[<span data-ttu-id="bdbeb-139">Lista över funktioner</span><span class="sxs-lookup"><span data-stu-id="bdbeb-139">List functions</span></span>](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
