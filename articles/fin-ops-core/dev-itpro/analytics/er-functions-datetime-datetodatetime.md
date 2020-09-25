---
title: Funktionen DATETODATETIME ER
description: Det här avsnittet innehåller information om hur funktionen DATETODATETIME elektronisk rapportering (ER) används.
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
ms.openlocfilehash: eac09c9b410815ad9ae71dec53fc0416b020ca1e
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/01/2020
ms.locfileid: "3744825"
---
# <a name="datetodatetime-er-function"></a><span data-ttu-id="be799-103">Funktionen DATETODATETIME ER</span><span class="sxs-lookup"><span data-stu-id="be799-103">DATETODATETIME ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="be799-104">`DATETODATETIME` funktionen returnerar värdet *DateTime* som konverteras från ett givet datumvärde till ett datum/tid-värde i Coordinated Universal Time (Greenwich Mean Time \[GMT\]).</span><span class="sxs-lookup"><span data-stu-id="be799-104">The `DATETODATETIME` function returns a *DateTime* value that is converted from a given date value to a date/time value in Coordinated Universal Time (Greenwich Mean Time \[GMT\]).</span></span>

## <a name="syntax"></a><span data-ttu-id="be799-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="be799-105">Syntax</span></span>

```vb
DATETODATETIME (date)
```

## <a name="arguments"></a><span data-ttu-id="be799-106">Argument</span><span class="sxs-lookup"><span data-stu-id="be799-106">Arguments</span></span>

<span data-ttu-id="be799-107">`date`: *Datum*</span><span class="sxs-lookup"><span data-stu-id="be799-107">`date`: *Date*</span></span>

<span data-ttu-id="be799-108">Ett datumvärde som representerar datumet som ska konverteras.</span><span class="sxs-lookup"><span data-stu-id="be799-108">A date value that represents the date to convert.</span></span>

## <a name="return-values"></a><span data-ttu-id="be799-109">Returvärden</span><span class="sxs-lookup"><span data-stu-id="be799-109">Return values</span></span>

<span data-ttu-id="be799-110">*Datum/tid*</span><span class="sxs-lookup"><span data-stu-id="be799-110">*DateTime*</span></span>

<span data-ttu-id="be799-111">Det resulterande datum/tid-värdet.</span><span class="sxs-lookup"><span data-stu-id="be799-111">The resulting date/time value.</span></span>

## <a name="example-1"></a><span data-ttu-id="be799-112">Exempel 1</span><span class="sxs-lookup"><span data-stu-id="be799-112">Example 1</span></span>

<span data-ttu-id="be799-113">`DATETODATETIME (CompInfo. 'getCurrentDate()')`-returnerar datumet för den aktuella Microsoft Dynamics 365 Finance-sessionen, 24 december 2015, som **12/24/2015 12:00:00 AM**.</span><span class="sxs-lookup"><span data-stu-id="be799-113">`DATETODATETIME (CompInfo. 'getCurrentDate()')` returns the date of the current Microsoft Dynamics 365 Finance session, December 24, 2015, as **12/24/2015 12:00:00 AM**.</span></span> <span data-ttu-id="be799-114">I det här exemplet är **CompInfo** en ER-datakälla (Elektronisk rapportering) av typen **Finance and Operations/tabell** och refererar till CompanyInfo-tabellen.</span><span class="sxs-lookup"><span data-stu-id="be799-114">In this example, **CompInfo** is an Electronic reporting (ER) data source of the **Finance and Operations/Table** type, and it refers to the CompanyInfo table.</span></span>

## <a name="example-2"></a><span data-ttu-id="be799-115">Exempel 2</span><span class="sxs-lookup"><span data-stu-id="be799-115">Example 2</span></span>

<span data-ttu-id="be799-116">`DATETODATETIME (DATEVALUE ("2019-11-12T16:00:00.0000000-07:00", "O"))` returnerar datum/tid-värdet **11/12/2019 12:00:00 AM**.</span><span class="sxs-lookup"><span data-stu-id="be799-116">`DATETODATETIME (DATEVALUE ("2019-11-12T16:00:00.0000000-07:00", "O"))` returns the date/time value **11/12/2019 12:00:00 AM**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="be799-117">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="be799-117">Additional resources</span></span>

[<span data-ttu-id="be799-118">Datum- och tidsfunktioner</span><span class="sxs-lookup"><span data-stu-id="be799-118">Date and time functions</span></span>](er-functions-category-datetime.md)
