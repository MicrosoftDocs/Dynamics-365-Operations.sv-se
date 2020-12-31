---
title: TODAY ER-funktion
description: Det här avsnittet innehåller information om hur funktionen TODAY elektronisk rapportering (ER) används.
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
ms.openlocfilehash: a93a9171456fb69e16c8104b0afb9ad485311b1a
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/05/2020
ms.locfileid: "4683805"
---
# <a name="today-er-function"></a><span data-ttu-id="da2aa-103">TODAY ER-funktion</span><span class="sxs-lookup"><span data-stu-id="da2aa-103">TODAY ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="da2aa-104">`TODAY`-funktionen returnerar ett *Datum*-värde som representerar aktuella programmets serverdatum.</span><span class="sxs-lookup"><span data-stu-id="da2aa-104">The `TODAY` function returns a *Date* value that represents the current application server date.</span></span>

## <a name="syntax"></a><span data-ttu-id="da2aa-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="da2aa-105">Syntax</span></span>

```xpp
TODAY ()
```

## <a name="return-values"></a><span data-ttu-id="da2aa-106">Returvärden</span><span class="sxs-lookup"><span data-stu-id="da2aa-106">Return values</span></span>

<span data-ttu-id="da2aa-107">*Datum*</span><span class="sxs-lookup"><span data-stu-id="da2aa-107">*Date*</span></span>

<span data-ttu-id="da2aa-108">Det resulterande datum-värdet.</span><span class="sxs-lookup"><span data-stu-id="da2aa-108">The resulting date value.</span></span>

## <a name="example"></a><span data-ttu-id="da2aa-109">Exempel</span><span class="sxs-lookup"><span data-stu-id="da2aa-109">Example</span></span>

<span data-ttu-id="da2aa-110">`DATEFORMAT (TODAY (), "dd-MM-yyyy")` returnerar det aktuella datumet för serverprogrammet 24 december 2015, som strängen **"2015-12-24"**, baserat på det definierade och anpassade formatet.</span><span class="sxs-lookup"><span data-stu-id="da2aa-110">`DATEFORMAT (TODAY (), "dd-MM-yyyy")` returns the current application server date, December 24, 2015, as the string **"24-12-2015"**, based on the specified custom format.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="da2aa-111">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="da2aa-111">Additional resources</span></span>

[<span data-ttu-id="da2aa-112">Datum- och tidsfunktioner</span><span class="sxs-lookup"><span data-stu-id="da2aa-112">Date and time functions</span></span>](er-functions-category-datetime.md)
