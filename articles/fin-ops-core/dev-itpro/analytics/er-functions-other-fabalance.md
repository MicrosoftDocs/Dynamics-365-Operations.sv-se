---
title: FA_BALANCE ER-funktion
description: Det här avsnittet innehåller information om hur funktionen FA_BALANCE elektronisk rapportering (ER) används.
author: NickSelin
manager: kfend
ms.date: 12/17/2019
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
ms.openlocfilehash: 76a087157ae53e2c571654ade7383d7bd7a005c3
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/12/2020
ms.locfileid: "3041456"
---
# <span data-ttu-id="3f176-103"><a name="FA_BALANCE">FA_BALANCE ER-funktion</a></span><span class="sxs-lookup"><span data-stu-id="3f176-103"><a name="FA_BALANCE">FA_BALANCE ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="3f176-104">`FA_BALANCE`-funktionen returnerar ett värde för *behållare (post)* som består av data för anläggningstillgångssaldo för den angivna anläggningstillgångsartikeln, värdemodellkoden, rapporteringsår och rapporterigsdatum.</span><span class="sxs-lookup"><span data-stu-id="3f176-104">The `FA_BALANCE` function returns a *Container (record)* value that consists of data for the fixed asset balance for the specified fixed asset item, value model code, reporting year, and reporting date.</span></span>

## <a name="syntax"></a><span data-ttu-id="3f176-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="3f176-105">Syntax</span></span>

```vb
FA_BALANCE (fixed asset code, value model code, reporting year, reporting date)
```

## <a name="arguments"></a><span data-ttu-id="3f176-106">Argument</span><span class="sxs-lookup"><span data-stu-id="3f176-106">Arguments</span></span>

<span data-ttu-id="3f176-107">`fixed asset code`: *Sträng*</span><span class="sxs-lookup"><span data-stu-id="3f176-107">`fixed asset code`: *String*</span></span>

<span data-ttu-id="3f176-108">Ett *sträng*-värde som representerar koden för en anläggningstillgångsartikel som saldot beräknas för.</span><span class="sxs-lookup"><span data-stu-id="3f176-108">A *String* value that represents the code of a fixed asset item that the balance is calculated for.</span></span>

<span data-ttu-id="3f176-109">`value model code`: *Sträng*</span><span class="sxs-lookup"><span data-stu-id="3f176-109">`value model code`: *String*</span></span>

<span data-ttu-id="3f176-110">Ett *sträng*-värde som representerar koden för en värdemodell som saldot beräknas för.</span><span class="sxs-lookup"><span data-stu-id="3f176-110">A *String* value that represents the code of a value model that the balance is calculated for.</span></span>

<span data-ttu-id="3f176-111">`reporting year`: *Fasttextvärde*</span><span class="sxs-lookup"><span data-stu-id="3f176-111">`reporting year`: *Enumeration value*</span></span>

<span data-ttu-id="3f176-112">Ett fasttextvärde för programuppräkningen **AssetYear** som definierar en period för saldoberäkningen.</span><span class="sxs-lookup"><span data-stu-id="3f176-112">An enumeration value of the **AssetYear** application enumeration that defines a period for the balance calculation.</span></span>

<span data-ttu-id="3f176-113">`reporting date`: *Datum*</span><span class="sxs-lookup"><span data-stu-id="3f176-113">`reporting date`: *Date*</span></span>

<span data-ttu-id="3f176-114">Ett *datum*-värde som definierar ett datum för saldoberäkningen.</span><span class="sxs-lookup"><span data-stu-id="3f176-114">A *Date* value that defines a date for the balance calculation.</span></span>

## <a name="return-values"></a><span data-ttu-id="3f176-115">Returvärden</span><span class="sxs-lookup"><span data-stu-id="3f176-115">Return values</span></span>

<span data-ttu-id="3f176-116">*Behållare (post)*</span><span class="sxs-lookup"><span data-stu-id="3f176-116">*Container (record)*</span></span>

<span data-ttu-id="3f176-117">Det resulterande postvärdet.</span><span class="sxs-lookup"><span data-stu-id="3f176-117">The resulting record value.</span></span>

## <a name="example"></a><span data-ttu-id="3f176-118">Exempel</span><span class="sxs-lookup"><span data-stu-id="3f176-118">Example</span></span>

<span data-ttu-id="3f176-119">`FA_ BALANCE ("COMP-000001", "Current", AxEnumAssetYear.ThisYear, SESSIONTODAY ())` returnerar databehållaren för belopp tillhörande anläggningstillgången **COMP-000001** som har förberetts för värdemodellen **Aktuell** på aktuellt programsessionsdatum.</span><span class="sxs-lookup"><span data-stu-id="3f176-119">`FA_ BALANCE ("COMP-000001", "Current", AxEnumAssetYear.ThisYear, SESSIONTODAY ())` returns the data container of balances for fixed asset **COMP-000001** that has been prepared for the **Current** value model on the current application session date.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="3f176-120">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="3f176-120">Additional resources</span></span>

[<span data-ttu-id="3f176-121">Andra (företagsdomänspecifika) funktioner</span><span class="sxs-lookup"><span data-stu-id="3f176-121">Other (business domain–specific) functions</span></span>](er-functions-category-other.md)
