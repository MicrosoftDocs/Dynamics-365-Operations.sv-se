---
title: SESSIONTODAY ER-funktion
description: Det här avsnittet innehåller information om hur funktionen SESSIONTODAY elektronisk rapportering (ER) används.
author: NickSelin
manager: kfend
ms.date: 12/05/2019
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
ms.openlocfilehash: bcfb36d6e3fb8475546f7cfb420c4aca848ac896
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/20/2019
ms.locfileid: "2917475"
---
# <span data-ttu-id="46a19-103"><a name="SESSIONTODAY">SESSIONTODAY ER-funktion</a></span><span class="sxs-lookup"><span data-stu-id="46a19-103"><a name="SESSIONTODAY">SESSIONTODAY ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="46a19-104">`SESSIONTODAY`-funktionen returnerar ett *Datum*-värde som representerar aktuella programmets sessionsdatum.</span><span class="sxs-lookup"><span data-stu-id="46a19-104">The `SESSIONTODAY` function returns a *Date* value that represents the current application session date.</span></span>

## <a name="syntax"></a><span data-ttu-id="46a19-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="46a19-105">Syntax</span></span>

```
SESSIONTODAY ()
```

## <a name="return-values"></a><span data-ttu-id="46a19-106">Returvärden</span><span class="sxs-lookup"><span data-stu-id="46a19-106">Return values</span></span>

<span data-ttu-id="46a19-107">*Datum*</span><span class="sxs-lookup"><span data-stu-id="46a19-107">*Date*</span></span>

<span data-ttu-id="46a19-108">Det resulterande datum-värdet.</span><span class="sxs-lookup"><span data-stu-id="46a19-108">The resulting date value.</span></span>

## <a name="example"></a><span data-ttu-id="46a19-109">Exempel</span><span class="sxs-lookup"><span data-stu-id="46a19-109">Example</span></span>

<span data-ttu-id="46a19-110">`DATEFORMAT (SESSIONTODAY (), "d", "DE")` returnerar det aktuella datumet för programsessionen, 24 december 2015 som strängen **"2015-12-24"**, baserat på den valda tyska kulturen och det angivna formatet.</span><span class="sxs-lookup"><span data-stu-id="46a19-110">`DATEFORMAT (SESSIONTODAY (), "d", "DE")` returns the current application session date, December 24, 2015, as the string **"24-12-2015"**, based on the selected German culture and the specified format.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="46a19-111">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="46a19-111">Additional resources</span></span>

[<span data-ttu-id="46a19-112">Datum- och tidsfunktioner</span><span class="sxs-lookup"><span data-stu-id="46a19-112">Date and time functions</span></span>](er-functions-category-datetime.md)
