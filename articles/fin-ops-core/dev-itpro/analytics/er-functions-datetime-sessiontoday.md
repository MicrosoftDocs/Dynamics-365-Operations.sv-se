---
title: SESSIONTODAY ER-funktion
description: Det här avsnittet innehåller information om hur funktionen SESSIONTODAY elektronisk rapportering (ER) används.
author: NickSelin
manager: kfend
ms.date: 12/05/2019
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
ms.openlocfilehash: e6ad28e642fcfae3cfa2692a4e41b99fae7fc9df
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/09/2021
ms.locfileid: "5561360"
---
# <a name="sessiontoday-er-function"></a><span data-ttu-id="98e68-103">SESSIONTODAY ER-funktion</span><span class="sxs-lookup"><span data-stu-id="98e68-103">SESSIONTODAY ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="98e68-104">`SESSIONTODAY`-funktionen returnerar ett *Datum*-värde som representerar aktuella programmets sessionsdatum.</span><span class="sxs-lookup"><span data-stu-id="98e68-104">The `SESSIONTODAY` function returns a *Date* value that represents the current application session date.</span></span>

## <a name="syntax"></a><span data-ttu-id="98e68-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="98e68-105">Syntax</span></span>

```vb
SESSIONTODAY ()
```

## <a name="return-values"></a><span data-ttu-id="98e68-106">Returvärden</span><span class="sxs-lookup"><span data-stu-id="98e68-106">Return values</span></span>

<span data-ttu-id="98e68-107">*Datum*</span><span class="sxs-lookup"><span data-stu-id="98e68-107">*Date*</span></span>

<span data-ttu-id="98e68-108">Det resulterande datum-värdet.</span><span class="sxs-lookup"><span data-stu-id="98e68-108">The resulting date value.</span></span>

## <a name="example"></a><span data-ttu-id="98e68-109">Exempel</span><span class="sxs-lookup"><span data-stu-id="98e68-109">Example</span></span>

<span data-ttu-id="98e68-110">`DATEFORMAT (SESSIONTODAY (), "d", "DE")` returnerar det aktuella datumet för programsessionen, 24 december 2015 som strängen **"2015-12-24"**, baserat på den valda tyska kulturen och det angivna formatet.</span><span class="sxs-lookup"><span data-stu-id="98e68-110">`DATEFORMAT (SESSIONTODAY (), "d", "DE")` returns the current application session date, December 24, 2015, as the string **"24-12-2015"**, based on the selected German culture and the specified format.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="98e68-111">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="98e68-111">Additional resources</span></span>

[<span data-ttu-id="98e68-112">Datum- och tidsfunktioner</span><span class="sxs-lookup"><span data-stu-id="98e68-112">Date and time functions</span></span>](er-functions-category-datetime.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]