---
title: DAYS ER-funktion
description: Det här avsnittet innehåller information om hur funktionen DAYS elektronisk rapportering (ER) används.
author: NickSelin
manager: kfend
ms.date: 12/04/2019
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
ms.openlocfilehash: 0252a68aebaa9af95de561b88ceb0666b3460d79
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/09/2021
ms.locfileid: "5563496"
---
# <a name="days-er-function"></a><span data-ttu-id="771d9-103">DAYS ER-funktion</span><span class="sxs-lookup"><span data-stu-id="771d9-103">DAYS ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="771d9-104">Funktionen `DAYS` returnerar värdet *heltal* som representerar antalet dagar mellan ett angivet datum och ett andra angivet datum.</span><span class="sxs-lookup"><span data-stu-id="771d9-104">The `DAYS` function returns an *Integer* value that represents the number of days between one specified date and a second specified date.</span></span>

## <a name="syntax"></a><span data-ttu-id="771d9-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="771d9-105">Syntax</span></span>

```vb
DAYS (date 1, date 2) as Integer
```

## <a name="arguments"></a><span data-ttu-id="771d9-106">Argument</span><span class="sxs-lookup"><span data-stu-id="771d9-106">Arguments</span></span>

<span data-ttu-id="771d9-107">`date 1`: *Datum*</span><span class="sxs-lookup"><span data-stu-id="771d9-107">`date 1`: *Date*</span></span>

<span data-ttu-id="771d9-108">Ett datumvärde som representerar det startdatum som ska användas för beräkningen av antalet dagar.</span><span class="sxs-lookup"><span data-stu-id="771d9-108">A date value that represents the start date for the calculation of the number of days.</span></span>

<span data-ttu-id="771d9-109">`date 2`: *Datum*</span><span class="sxs-lookup"><span data-stu-id="771d9-109">`date 2`: *Date*</span></span>

<span data-ttu-id="771d9-110">Ett datumvärde som representerar det slutdatum som ska användas för beräkningen av antalet dagar.</span><span class="sxs-lookup"><span data-stu-id="771d9-110">A date value that represents the end date for the calculation of the number of days.</span></span>

## <a name="return-values"></a><span data-ttu-id="771d9-111">Returvärden</span><span class="sxs-lookup"><span data-stu-id="771d9-111">Return values</span></span>

<span data-ttu-id="771d9-112">*Heltal*</span><span class="sxs-lookup"><span data-stu-id="771d9-112">*Integer*</span></span>

<span data-ttu-id="771d9-113">Det resulterande numeriska värdet.</span><span class="sxs-lookup"><span data-stu-id="771d9-113">The resulting numeric value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="771d9-114">Användningsanteckningar</span><span class="sxs-lookup"><span data-stu-id="771d9-114">Usage notes</span></span>

<span data-ttu-id="771d9-115">`DAYS`-funktionen returnerar ett positivt värde när det första datumet är senare än det andra, returnerar **0** (noll) när det första datumet är lika med det andra och det returnerar ett negativt värde när det första datumet är tidigare än det andra datumet.</span><span class="sxs-lookup"><span data-stu-id="771d9-115">The `DAYS` function returns a positive value when the first date is later than the second date, it returns **0** (zero) when the first date equals the second date, and it returns a negative value when the first date is earlier than the second date.</span></span>

## <a name="example"></a><span data-ttu-id="771d9-116">Exempel</span><span class="sxs-lookup"><span data-stu-id="771d9-116">Example</span></span>

<span data-ttu-id="771d9-117">`DAYS (TODAY (), DATEVALUE( DATETIMEFORMAT( ADDDAYS ( NOW(), 1), "yyyyMMdd"), "yyyyMMdd"))` returnerar **-1**.</span><span class="sxs-lookup"><span data-stu-id="771d9-117">`DAYS (TODAY (), DATEVALUE( DATETIMEFORMAT( ADDDAYS ( NOW(), 1), "yyyyMMdd"), "yyyyMMdd"))` returns **-1**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="771d9-118">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="771d9-118">Additional resources</span></span>

[<span data-ttu-id="771d9-119">Datum- och tidsfunktioner</span><span class="sxs-lookup"><span data-stu-id="771d9-119">Date and time functions</span></span>](er-functions-category-datetime.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]