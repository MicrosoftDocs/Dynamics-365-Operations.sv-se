---
title: ALLITEMS ER-funktionen
description: Det här avsnittet innehåller information om hur funktionen ALLITEMS elektronisk rapportering (ER) används.
author: NickSelin
manager: kfend
ms.date: 12/04/2019
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
ms.openlocfilehash: 47113d52e15d3d61f00b3c54229e286eb0f1a8d7
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/01/2020
ms.locfileid: "3745403"
---
# <a name="allitems-er-function"></a><span data-ttu-id="5cd68-103">ALLITEMS ER-funktionen</span><span class="sxs-lookup"><span data-stu-id="5cd68-103">ALLITEMS ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="5cd68-104">`ALLITEMS`-funktionen körs som ett inbyggt minnesval och returnerar ett nytt utplattat värde för *postlista* som en lista med poster som representerar alla objekt som matchar den angivna sökvägen.</span><span class="sxs-lookup"><span data-stu-id="5cd68-104">The `ALLITEMS` function runs as an in-memory selection and returns a new flattened *Record list* value as a list of records that represents all items that match the specified path.</span></span>

## <a name="syntax"></a><span data-ttu-id="5cd68-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="5cd68-105">Syntax</span></span>

```vb
ALLITEMS (path)
```

## <a name="arguments"></a><span data-ttu-id="5cd68-106">Argument</span><span class="sxs-lookup"><span data-stu-id="5cd68-106">Arguments</span></span>

<span data-ttu-id="5cd68-107">`path`: *Post-lista*</span><span class="sxs-lookup"><span data-stu-id="5cd68-107">`path`: *Record list*</span></span>

<span data-ttu-id="5cd68-108">Den giltiga sökvägen av en datakälla för datatypen *Postlista*.</span><span class="sxs-lookup"><span data-stu-id="5cd68-108">The valid path of a data source of the *Record list* data type.</span></span>

## <a name="return-values"></a><span data-ttu-id="5cd68-109">Returvärden</span><span class="sxs-lookup"><span data-stu-id="5cd68-109">Return values</span></span>

<span data-ttu-id="5cd68-110">*Post-lista*</span><span class="sxs-lookup"><span data-stu-id="5cd68-110">*Record list*</span></span>

<span data-ttu-id="5cd68-111">Den resulterande listan med poster.</span><span class="sxs-lookup"><span data-stu-id="5cd68-111">The resulting list of records.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="5cd68-112">Användningsanteckningar</span><span class="sxs-lookup"><span data-stu-id="5cd68-112">Usage notes</span></span>

<span data-ttu-id="5cd68-113">Sökvägen måste anges som en giltig datakällsökväg för ett datakällselement av datatypen *postlista*.</span><span class="sxs-lookup"><span data-stu-id="5cd68-113">The path must be defined as a valid data source path of a data source element of the *Record list* data type.</span></span> <span data-ttu-id="5cd68-114">Dataelement som sökväg och datum bör skapa ett fel i Elektronisk rapportering (ER)-uttrycksgeneratorn vid designtidpunkten.</span><span class="sxs-lookup"><span data-stu-id="5cd68-114">Data elements such as the path string and date should raise an error in the Electronic reporting (ER) expression builder at design time.</span></span>

<span data-ttu-id="5cd68-115">Vi rekommenderar inte att du använder den här funktionen för transaktionsdatakällor som kan innehålla en stor mängd data.</span><span class="sxs-lookup"><span data-stu-id="5cd68-115">We don't recommend that you use this function for transactional data sources that might contain a large volume of data.</span></span> <span data-ttu-id="5cd68-116">Överväg i stället att använda funktionen [ALLTEMSQUERY](er-functions-list-allitemsquery.md).</span><span class="sxs-lookup"><span data-stu-id="5cd68-116">Instead, consider using the [ALLTEMSQUERY](er-functions-list-allitemsquery.md) function.</span></span>

## <a name="example-1"></a><span data-ttu-id="5cd68-117">Exempel 1</span><span class="sxs-lookup"><span data-stu-id="5cd68-117">Example 1</span></span>

<span data-ttu-id="5cd68-118">Om du anger `SPLIT("abcdef" , 2)` som datakälla **DS** returnerar uttrycket `COUNT( ALLITEMS (DS))`**3**.</span><span class="sxs-lookup"><span data-stu-id="5cd68-118">If you enter `SPLIT("abcdef" , 2)` as data source **DS**, the expression `COUNT( ALLITEMS (DS))` returns **3**.</span></span>

## <a name="example-2"></a><span data-ttu-id="5cd68-119">Exempel 2</span><span class="sxs-lookup"><span data-stu-id="5cd68-119">Example 2</span></span>

<span data-ttu-id="5cd68-120">Om du anger **Lev** som datakällan för datatypen *Postlista* som refererar till programtabellen VendTable returnerar uttrycket `ALLITEMS (Vend.'<Relations'.ContactPerson)` en förenklad lista med poster som har registerstrukturen **ContactPerson** och innehåller alla kontaktpersoner som kan nås med hjälp **ContactPerson.ContactForParty == VendTable.Party**-relation och som är tillgänglig för alla leverantörer från tabellen refererad leverantör.</span><span class="sxs-lookup"><span data-stu-id="5cd68-120">If you enter **Vend** as the data source of the *Record list* data type that refers to the VendTable application table, the expression `ALLITEMS (Vend.'<Relations'.ContactPerson)` returns a flattened list of records that has the **ContactPerson** table structure and contains all contact persons that can be accessed by using the **ContactPerson.ContactForParty == VendTable.Party** relation, and that is available for all vendors from the referenced vendor table.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="5cd68-121">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="5cd68-121">Additional resources</span></span>

[<span data-ttu-id="5cd68-122">Lista över funktioner</span><span class="sxs-lookup"><span data-stu-id="5cd68-122">List functions</span></span>](er-functions-category-list.md)
