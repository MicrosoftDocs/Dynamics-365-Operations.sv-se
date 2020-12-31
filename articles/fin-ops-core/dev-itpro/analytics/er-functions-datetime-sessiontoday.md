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
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 87e8d5498c82d7c9ca6ee0a855f139dde77d75ab
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/05/2020
ms.locfileid: "4683829"
---
# <a name="sessiontoday-er-function"></a><span data-ttu-id="97f43-103">SESSIONTODAY ER-funktion</span><span class="sxs-lookup"><span data-stu-id="97f43-103">SESSIONTODAY ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="97f43-104">`SESSIONTODAY`-funktionen returnerar ett *Datum*-värde som representerar aktuella programmets sessionsdatum.</span><span class="sxs-lookup"><span data-stu-id="97f43-104">The `SESSIONTODAY` function returns a *Date* value that represents the current application session date.</span></span>

## <a name="syntax"></a><span data-ttu-id="97f43-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="97f43-105">Syntax</span></span>

```vb
SESSIONTODAY ()
```

## <a name="return-values"></a><span data-ttu-id="97f43-106">Returvärden</span><span class="sxs-lookup"><span data-stu-id="97f43-106">Return values</span></span>

<span data-ttu-id="97f43-107">*Datum*</span><span class="sxs-lookup"><span data-stu-id="97f43-107">*Date*</span></span>

<span data-ttu-id="97f43-108">Det resulterande datum-värdet.</span><span class="sxs-lookup"><span data-stu-id="97f43-108">The resulting date value.</span></span>

## <a name="example"></a><span data-ttu-id="97f43-109">Exempel</span><span class="sxs-lookup"><span data-stu-id="97f43-109">Example</span></span>

<span data-ttu-id="97f43-110">`DATEFORMAT (SESSIONTODAY (), "d", "DE")` returnerar det aktuella datumet för programsessionen, 24 december 2015 som strängen **"2015-12-24"**, baserat på den valda tyska kulturen och det angivna formatet.</span><span class="sxs-lookup"><span data-stu-id="97f43-110">`DATEFORMAT (SESSIONTODAY (), "d", "DE")` returns the current application session date, December 24, 2015, as the string **"24-12-2015"**, based on the selected German culture and the specified format.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="97f43-111">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="97f43-111">Additional resources</span></span>

[<span data-ttu-id="97f43-112">Datum- och tidsfunktioner</span><span class="sxs-lookup"><span data-stu-id="97f43-112">Date and time functions</span></span>](er-functions-category-datetime.md)
