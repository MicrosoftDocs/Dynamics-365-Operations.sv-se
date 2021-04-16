---
title: ALLITEMSQUERY ER-funktionen
description: Det här avsnittet innehåller information om hur funktionen ALLITEMSQUERY elektronisk rapportering (ER) används.
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
ms.openlocfilehash: 7995b497a2bd95d4aec9ae6d5f1c3cb790823ea0
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5746709"
---
# <a name="allitemsquery-er-function"></a><span data-ttu-id="656a3-103">ALLITEMSQUERY ER-funktionen</span><span class="sxs-lookup"><span data-stu-id="656a3-103">ALLITEMSQUERY ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="656a3-104">`ALLITEMSQUERY`-funktionen körs som en sammanslagen SQL-fråga.</span><span class="sxs-lookup"><span data-stu-id="656a3-104">The `ALLITEMSQUERY` function runs as a joined SQL query.</span></span> <span data-ttu-id="656a3-105">Den returnerar ett nytt tillplattat värde för *postlista* som består av en lista med poster som representerar alla objekt som matchar den angivna sökvägen.</span><span class="sxs-lookup"><span data-stu-id="656a3-105">It returns a new flattened *Record list* value that consists of a list of records that represent all items that match the specified path.</span></span>

## <a name="syntax"></a><span data-ttu-id="656a3-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="656a3-106">Syntax</span></span>

```vb
ALLITEMSQUERY (path)
```

## <a name="arguments"></a><span data-ttu-id="656a3-107">Argument</span><span class="sxs-lookup"><span data-stu-id="656a3-107">Arguments</span></span>

<span data-ttu-id="656a3-108">`path`: *Post-lista*</span><span class="sxs-lookup"><span data-stu-id="656a3-108">`path`: *Record list*</span></span>

<span data-ttu-id="656a3-109">Den giltiga sökvägen av en datakälla för datatypen *Postlista*.</span><span class="sxs-lookup"><span data-stu-id="656a3-109">The valid path of a data source of the *Record list* data type.</span></span> <span data-ttu-id="656a3-110">Det måste innehålla minst en relation.</span><span class="sxs-lookup"><span data-stu-id="656a3-110">It must contain at least one relation.</span></span>

## <a name="return-values"></a><span data-ttu-id="656a3-111">Returvärden</span><span class="sxs-lookup"><span data-stu-id="656a3-111">Return values</span></span>

<span data-ttu-id="656a3-112">*Post-lista*</span><span class="sxs-lookup"><span data-stu-id="656a3-112">*Record list*</span></span>

<span data-ttu-id="656a3-113">Den resulterande listan med poster.</span><span class="sxs-lookup"><span data-stu-id="656a3-113">The resulting list of records.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="656a3-114">Användningsanteckningar</span><span class="sxs-lookup"><span data-stu-id="656a3-114">Usage notes</span></span>

<span data-ttu-id="656a3-115">Den angivna sökvägen måste anges som en giltig datakällsökväg för ett datakällselement av datatypen *postlista*.</span><span class="sxs-lookup"><span data-stu-id="656a3-115">The specified path must be defined as a valid data source path of a data source element of the *Record list* data type.</span></span> <span data-ttu-id="656a3-116">Det måste innehålla minst en relation.</span><span class="sxs-lookup"><span data-stu-id="656a3-116">It must also contain at least one relation.</span></span> <span data-ttu-id="656a3-117">Dataelement som sökvägens *sträng* och *datum* bör skapa ett fel i Elektronisk rapportering (ER)-uttrycksgeneratorn vid designtidpunkten.</span><span class="sxs-lookup"><span data-stu-id="656a3-117">Data elements such as the path *String* and *Date* should raise an error in the Electronic reporting (ER) expression builder at design time.</span></span>

<span data-ttu-id="656a3-118">När den här funktionen används för datakällor av typen *postlista* som refererar till ett programobjekt som kan anropas direkt med hjälp av SQL (till exempel en tabell, entitet eller fråga), körs den som en sammanfogade SQL-fråga.</span><span class="sxs-lookup"><span data-stu-id="656a3-118">When this function is applied to data sources of the *Record list* data type that refer to an application object that can be directly called by using SQL (for example, an table, entity, or query), it runs as a joined SQL query.</span></span> <span data-ttu-id="656a3-119">Annars körs i minnet som den [ALLITEMS](er-functions-list-allitems.md)-funktion.</span><span class="sxs-lookup"><span data-stu-id="656a3-119">Otherwise, it runs in memory as the [ALLITEMS](er-functions-list-allitems.md) function.</span></span>

## <a name="example"></a><span data-ttu-id="656a3-120">Exempel</span><span class="sxs-lookup"><span data-stu-id="656a3-120">Example</span></span>

<span data-ttu-id="656a3-121">Du definierar följande datakällor i din modellmappning:</span><span class="sxs-lookup"><span data-stu-id="656a3-121">You define the following data sources in your model mapping:</span></span>

- <span data-ttu-id="656a3-122">En **CustInv** datakälla av typen *registerposter* som refererar till tabellen CustInvoiceTable</span><span class="sxs-lookup"><span data-stu-id="656a3-122">A **CustInv** data source of the *Table records* type that refers to the CustInvoiceTable table</span></span>
- <span data-ttu-id="656a3-123">En **FilteredInv**-datakälla av typen *beräknat fält* som innehåller uttrycket `FILTER (CustInv, CustInv.InvoiceAccount = "US-001")`</span><span class="sxs-lookup"><span data-stu-id="656a3-123">A **FilteredInv** data source of the *Calculated field* type that contains the expression `FILTER (CustInv, CustInv.InvoiceAccount = "US-001")`</span></span>
- <span data-ttu-id="656a3-124">En **JourLines** av typen *beräknat fält* som innehåller uttrycket `ALLITEMSQUERY ( FilteredInv.'<Relations'.CustInvoiceJour.'<Relations'.CustInvoiceTrans)`</span><span class="sxs-lookup"><span data-stu-id="656a3-124">A **JourLines** of the *Calculated field* type that contains the expression `ALLITEMSQUERY ( FilteredInv.'<Relations'.CustInvoiceJour.'<Relations'.CustInvoiceTrans)`</span></span>

<span data-ttu-id="656a3-125">När du kör en modellmappning att anropa datakällan **JourLines**, kör följande SQL-sats:</span><span class="sxs-lookup"><span data-stu-id="656a3-125">When you run the model mapping to call the **JourLines** data source, the following SQL statement is run:</span></span>

```sql
SELECT ... FROM CUSTINVOICETABLE T1 CROSS JOIN CUSTINVOICEJOUR T2 CROSS JOIN
CUSTINVOICETRANS T3 WHERE...
```

## <a name="additional-resources"></a><span data-ttu-id="656a3-126">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="656a3-126">Additional resources</span></span>

[<span data-ttu-id="656a3-127">Lista över funktioner</span><span class="sxs-lookup"><span data-stu-id="656a3-127">List functions</span></span>](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]