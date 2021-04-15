---
title: LISTDISTINCT ER-funktion
description: Det här avsnittet innehåller information om hur funktionen LISTDISTINCT elektronisk rapportering (ER) används.
author: NickSelin
ms.date: 7/30/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2020-08-01
ms.dyn365.ops.version: AX 10.0.14
ms.openlocfilehash: 9ab9354b0fdb1c08c192b90e6bab303cb85ea41a
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5743833"
---
# <a name="listdistinct-er-function"></a><span data-ttu-id="bba9b-103">LISTDISTINCT ER-funktion</span><span class="sxs-lookup"><span data-stu-id="bba9b-103">LISTDISTINCT ER Function</span></span>

[!include [banner](../includes/banner.md)]
[!include [banner](../includes/preview-banner.md)]

<span data-ttu-id="bba9b-104">Den här `LISTDISTINCT`-funktionen beräknar det angivna uttrycket som en väljare för varje post i den angivna listan.</span><span class="sxs-lookup"><span data-stu-id="bba9b-104">The `LISTDISTINCT` function calculates the specified expression as a selector for every record of the specified list.</span></span> <span data-ttu-id="bba9b-105">Det returnerar ett nytt värde för *postlista* som innehåller en enskild post för varje unikt väljarvärde.</span><span class="sxs-lookup"><span data-stu-id="bba9b-105">It returns a new *Record list* value that contains a single record for each unique selector value.</span></span>

## <a name="syntax"></a><span data-ttu-id="bba9b-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="bba9b-106">Syntax</span></span>

```
LISTDISTINCT (list, selector)
```

## <a name="arguments"></a><span data-ttu-id="bba9b-107">Argument</span><span class="sxs-lookup"><span data-stu-id="bba9b-107">Arguments</span></span>

<span data-ttu-id="bba9b-108">`list`: *Post-lista*</span><span class="sxs-lookup"><span data-stu-id="bba9b-108">`list`: *Record list*</span></span>

<span data-ttu-id="bba9b-109">Den giltiga sökvägen av en datakälla för datatypen *Postlista*.</span><span class="sxs-lookup"><span data-stu-id="bba9b-109">The valid path of a data source of the *Record list* data type.</span></span>

<span data-ttu-id="bba9b-110">`selector`: *Primitiva datatyp*</span><span class="sxs-lookup"><span data-stu-id="bba9b-110">`selector`: *Primitive data type*</span></span>

<span data-ttu-id="bba9b-111">Ett giltigt uttryck som används för att beräkna ett väljarvärde för varje post i den angivna listan.</span><span class="sxs-lookup"><span data-stu-id="bba9b-111">A valid expression that is used to calculate a selector value for every record in the specified list.</span></span>

<span data-ttu-id="bba9b-112">Följande datatyper stöds för den här parametern:</span><span class="sxs-lookup"><span data-stu-id="bba9b-112">The following data types are supported for this parameter:</span></span>

- <span data-ttu-id="bba9b-113">Booleskt</span><span class="sxs-lookup"><span data-stu-id="bba9b-113">Boolean</span></span>
- <span data-ttu-id="bba9b-114">Datum</span><span class="sxs-lookup"><span data-stu-id="bba9b-114">Date</span></span>
- <span data-ttu-id="bba9b-115">DatumTid</span><span class="sxs-lookup"><span data-stu-id="bba9b-115">DateTime</span></span>
- <span data-ttu-id="bba9b-116">GUID</span><span class="sxs-lookup"><span data-stu-id="bba9b-116">GUID</span></span>
- <span data-ttu-id="bba9b-117">Heltal</span><span class="sxs-lookup"><span data-stu-id="bba9b-117">Integer</span></span>
- <span data-ttu-id="bba9b-118">Int64</span><span class="sxs-lookup"><span data-stu-id="bba9b-118">Int64</span></span>
- <span data-ttu-id="bba9b-119">Realtal</span><span class="sxs-lookup"><span data-stu-id="bba9b-119">Real</span></span>
- <span data-ttu-id="bba9b-120">Sträng</span><span class="sxs-lookup"><span data-stu-id="bba9b-120">String</span></span>

## <a name="return-values"></a><span data-ttu-id="bba9b-121">Returvärden</span><span class="sxs-lookup"><span data-stu-id="bba9b-121">Return values</span></span>

<span data-ttu-id="bba9b-122">*Postlista*</span><span class="sxs-lookup"><span data-stu-id="bba9b-122">*Record list*</span></span>

<span data-ttu-id="bba9b-123">Den resulterande listan med poster.</span><span class="sxs-lookup"><span data-stu-id="bba9b-123">The resulting list of records.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="bba9b-124">Användningsanteckningar</span><span class="sxs-lookup"><span data-stu-id="bba9b-124">Usage notes</span></span>

<span data-ttu-id="bba9b-125">Strukturen för listan som skapas matchar strukturen i den angivna listan.</span><span class="sxs-lookup"><span data-stu-id="bba9b-125">The structure of the list that is created matches the structure of the specified list.</span></span>

<span data-ttu-id="bba9b-126">Samma väljarvärde kan beräknas för flera poster i den angivna listan.</span><span class="sxs-lookup"><span data-stu-id="bba9b-126">The same selector value might be calculated for multiple records in the specified list.</span></span> <span data-ttu-id="bba9b-127">I det här fallet är fältvärdena för motsvarande post i listan skapad lika med värdena för den första posten från den angivna listan som väljar värdet för.</span><span class="sxs-lookup"><span data-stu-id="bba9b-127">In this case, field values of the corresponding record in the created list equal the values of the first record from the specified list that the selector value is calculated for.</span></span>

<span data-ttu-id="bba9b-128">Det går att utföra den här funktionen på alla datakällor [elektronisk rapportering (ER)](general-electronic-reporting.md) av *postlista* typen som finns i minnet.</span><span class="sxs-lookup"><span data-stu-id="bba9b-128">The execution of this function is done on any [Electronic reporting (ER)](general-electronic-reporting.md) data source of the *Record list* type that is present in memory.</span></span>

<span data-ttu-id="bba9b-129">Datakällan **GROUPBY** för att generera listan med poster som väljs av en väljare som har distinkta värden.</span><span class="sxs-lookup"><span data-stu-id="bba9b-129">The **GROUPBY** data source can also be used to generate the list of records that the selector that has distinct values is calculated for.</span></span> <span data-ttu-id="bba9b-130">Från ett prestanda- och minnesförbrukningsperspektiv är det emellertid bättre att använda `LISTDISTINCT`-funktionen än **GROUPBY**-datakällan, eftersom körningen av funktionen utförs i minnet.</span><span class="sxs-lookup"><span data-stu-id="bba9b-130">However, from a performance and memory consumption perspective, it's better to use the `LISTDISTINCT` function than the **GROUPBY** data source, because the execution of the function is done in memory.</span></span>

## <a name="example"></a><span data-ttu-id="bba9b-131">Exempel</span><span class="sxs-lookup"><span data-stu-id="bba9b-131">Example</span></span>

<span data-ttu-id="bba9b-132">Följande exempel visar hur du kan få listan med unika kundkontonummer som minst en försäljningsfaktura eller projektfaktura har utfärdats för under en viss period.</span><span class="sxs-lookup"><span data-stu-id="bba9b-132">The following example shows how you can get the list of unique customer account numbers that at least one sales invoice or project invoice has been issued to during a specific period.</span></span>

1. <span data-ttu-id="bba9b-133">Ange datakällan **SalesInvoice** för den `Record list`-typ som refererar till **CustInvoiceJour** programregister och filtrerar försäljningsfakturor för specifika perioder.</span><span class="sxs-lookup"><span data-stu-id="bba9b-133">Enter the **SalesInvoice** data source of the `Record list` type that refers to the **CustInvoiceJour** application table and filters sales invoices for specific periods.</span></span>

    <span data-ttu-id="bba9b-134">`InvoiceAccount`-fältet i den här datakällan returnerar kontonumret för en fakturerad kund.</span><span class="sxs-lookup"><span data-stu-id="bba9b-134">The `InvoiceAccount` field of this data source returns the account number of an invoiced customer.</span></span>

2. <span data-ttu-id="bba9b-135">Ange datakällan **ProjectInvoice** för den `Record list`-typ som refererar till **ProjectInvoice** programregister och filtrerar projektfakturor för specifika perioder.</span><span class="sxs-lookup"><span data-stu-id="bba9b-135">Enter the **ProjectInvoice** data source of the `Record list` type that refers to the **ProjInvoiceJour** application table and filters project invoices for specific periods.</span></span>

    <span data-ttu-id="bba9b-136">`InvoiceAccount`-fältet i den här datakällan returnerar kontonumret för en fakturerad kund.</span><span class="sxs-lookup"><span data-stu-id="bba9b-136">The `InvoiceAccount` field of this data source returns the account number of an invoiced customer.</span></span>

3. <span data-ttu-id="bba9b-137">Konfigurera datakällan **AllInvoices** som innehåller uttrycket `Calculated field` som innehåller uttrycket `LISTJOIN(SalesInvoice, ProjectInvoice)`.</span><span class="sxs-lookup"><span data-stu-id="bba9b-137">Configure the **AllInvoices** data source of the `Calculated field` type that contains the expression `LISTJOIN(SalesInvoice, ProjectInvoice)`.</span></span>

    <span data-ttu-id="bba9b-138">Den här datakällan returnerar den kopplade listan över försäljningsfakturor och projektfakturor.</span><span class="sxs-lookup"><span data-stu-id="bba9b-138">This data source returns the joined list of sales invoices and project invoices.</span></span>

4. <span data-ttu-id="bba9b-139">Konfigurera datakällan **InvoicedCustomer** som innehåller uttrycket `Record list` som innehåller uttrycket `LISTDISTINCT(AllInvoices, AllInvoices.InvoiceAccount)`.</span><span class="sxs-lookup"><span data-stu-id="bba9b-139">Configure the **InvoicedCustomer** data source of the `Record list` type that contains the expression `LISTDISTINCT(AllInvoices, AllInvoices.InvoiceAccount)`.</span></span>

    <span data-ttu-id="bba9b-140">Den här datakällan returnerar en ny lista som innehåller en enda post för varje unik kund som har fakturerats under den angivna perioden.</span><span class="sxs-lookup"><span data-stu-id="bba9b-140">This data source returns a new list that contains a single record for every unique customer that has been invoiced during the defined period.</span></span> <span data-ttu-id="bba9b-141">`InvoiceAccount`-fältet i den här listan innehåller ett kundkontonummer.</span><span class="sxs-lookup"><span data-stu-id="bba9b-141">The `InvoiceAccount` field of this list contains a customer account number.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="bba9b-142">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="bba9b-142">Additional resources</span></span>

[<span data-ttu-id="bba9b-143">Lista över funktioner</span><span class="sxs-lookup"><span data-stu-id="bba9b-143">List functions</span></span>](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]