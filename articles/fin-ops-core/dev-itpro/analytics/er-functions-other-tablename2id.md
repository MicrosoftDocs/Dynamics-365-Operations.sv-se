---
title: TABLENAME2ID ER-funktion
description: Det här avsnittet innehåller information om hur funktionen TABLENAME2ID elektronisk rapportering (ER) används.
author: NickSelin
manager: kfend
ms.date: 12/12/2019
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
ms.openlocfilehash: 77d889f75f38b3c07855a96bf65f1456ac2f42e2
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/20/2019
ms.locfileid: "2915819"
---
# <span data-ttu-id="dc84e-103"><a name="TABLENAME2ID">TABLENAME2ID ER-funktion</a></span><span class="sxs-lookup"><span data-stu-id="dc84e-103"><a name="TABLENAME2ID">TABLENAME2ID ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="dc84e-104">`TABLENAME2ID`-funktionen returnerar en numerisk representation av tabell-ID för det angivna tabellnamnet som värdet *heltal*.</span><span class="sxs-lookup"><span data-stu-id="dc84e-104">The `TABLENAME2ID` function returns a numeric representation of the table ID for the specified table name as an *Integer* value.</span></span>

## <a name="syntax"></a><span data-ttu-id="dc84e-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="dc84e-105">Syntax</span></span>

```
TABLENAME2ID (text)
```

## <a name="arguments"></a><span data-ttu-id="dc84e-106">Argument</span><span class="sxs-lookup"><span data-stu-id="dc84e-106">Arguments</span></span>

<span data-ttu-id="dc84e-107">`text`: *Sträng*</span><span class="sxs-lookup"><span data-stu-id="dc84e-107">`text`: *String*</span></span>

<span data-ttu-id="dc84e-108">Ett textvärde som representerar ett giltigt tabellnamn.</span><span class="sxs-lookup"><span data-stu-id="dc84e-108">A text value that represents a valid table name.</span></span>

## <a name="return-values"></a><span data-ttu-id="dc84e-109">Returvärden</span><span class="sxs-lookup"><span data-stu-id="dc84e-109">Return values</span></span>

<span data-ttu-id="dc84e-110">*Heltal*</span><span class="sxs-lookup"><span data-stu-id="dc84e-110">*Integer*</span></span>

<span data-ttu-id="dc84e-111">Det resulterande numeriska värdet.</span><span class="sxs-lookup"><span data-stu-id="dc84e-111">The resulting numeric value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="dc84e-112">Användningsanteckningar</span><span class="sxs-lookup"><span data-stu-id="dc84e-112">Usage notes</span></span>

<span data-ttu-id="dc84e-113">Körningen av den här funktionen kan ha olika resultat i olika instanser av Microsoft Dynamics 365 Finance, även om samma företagsnamn används.</span><span class="sxs-lookup"><span data-stu-id="dc84e-113">Execution of this function can have different results in different instances of Microsoft Dynamics 365 Finance, even if the same company name is used.</span></span>

## <a name="example"></a><span data-ttu-id="dc84e-114">Exempel</span><span class="sxs-lookup"><span data-stu-id="dc84e-114">Example</span></span>

<span data-ttu-id="dc84e-115">`TABLENAME2ID ("Intrastat")` returnerar **1510**.</span><span class="sxs-lookup"><span data-stu-id="dc84e-115">`TABLENAME2ID ("Intrastat")` returns **1510**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="dc84e-116">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="dc84e-116">Additional resources</span></span>

[<span data-ttu-id="dc84e-117">Andra (företagsdomänspecifika) funktioner</span><span class="sxs-lookup"><span data-stu-id="dc84e-117">Other (business domain–specific) functions</span></span>](er-functions-category-other.md)
