---
title: Funktionen NULLDATETIME ER
description: Det här avsnittet innehåller information om hur funktionen NULLDATETIME elektronisk rapportering (ER) används.
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
ms.openlocfilehash: 4165f6e064d12200907ac76b6779d35bc578daba
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/20/2019
ms.locfileid: "2917498"
---
# <span data-ttu-id="4c86b-103"><a name="NULLDATETIME">Funktionen NULLDATETIME ER</a></span><span class="sxs-lookup"><span data-stu-id="4c86b-103"><a name="NULLDATETIME">NULLDATETIME ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="4c86b-104">`NULLDATETIME`-funktionen returnerar ett *DateTime*-värde som representerar **noll** datum/-tid-värdet (1 januari 1900) i Coordinated Universal Time (Greenwich Mean Time \[GMT\]).</span><span class="sxs-lookup"><span data-stu-id="4c86b-104">The `NULLDATETIME` function returns a *DateTime* value that represents the **null** date/time value (January 1, 1900) in Coordinated Universal Time (Greenwich Mean Time \[GMT\]).</span></span>

## <a name="syntax"></a><span data-ttu-id="4c86b-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="4c86b-105">Syntax</span></span>

```
NULLDATETIME ()
```

## <a name="return-values"></a><span data-ttu-id="4c86b-106">Returvärden</span><span class="sxs-lookup"><span data-stu-id="4c86b-106">Return values</span></span>

<span data-ttu-id="4c86b-107">*Datum/tid*</span><span class="sxs-lookup"><span data-stu-id="4c86b-107">*DateTime*</span></span>

<span data-ttu-id="4c86b-108">Det resulterande datum/tid-värdet.</span><span class="sxs-lookup"><span data-stu-id="4c86b-108">The resulting date/time value.</span></span>

## <a name="example"></a><span data-ttu-id="4c86b-109">Exempel</span><span class="sxs-lookup"><span data-stu-id="4c86b-109">Example</span></span>

<span data-ttu-id="4c86b-110">`DATETIMEFORMAT( NULLDATETIME(), "O")` returnerar strängvärdet **1900-01-01T00:00:00.0000000+00:00** när det anropas under en process som initierades av en programanvändare som har tidszonsvärde **(GMT) Coordinated Universal Time** i avsnittet **Språk och land/regionpreferenser**.</span><span class="sxs-lookup"><span data-stu-id="4c86b-110">`DATETIMEFORMAT( NULLDATETIME(), "O")` returns the string value **1900-01-01T00:00:00.0000000+00:00** when it's called during a process that was initiated by an application user who has the time zone value **(GMT) Coordinated Universal Time** in the **Language and country/region preferences** section.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="4c86b-111">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="4c86b-111">Additional resources</span></span>

[<span data-ttu-id="4c86b-112">Datum- och tidsfunktioner</span><span class="sxs-lookup"><span data-stu-id="4c86b-112">Date and time functions</span></span>](er-functions-category-datetime.md)