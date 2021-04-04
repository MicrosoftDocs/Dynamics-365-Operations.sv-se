---
title: FA_SUM ER-funktion
description: Det här avsnittet innehåller information om hur funktionen FA_SUM elektronisk rapportering (ER) används.
author: NickSelin
manager: kfend
ms.date: 12/17/2019
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
ms.openlocfilehash: c31722537e2a6bae502800953939ca01da4527b9
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/09/2021
ms.locfileid: "5567578"
---
# <a name="fa_sum-er-function"></a><span data-ttu-id="cb267-103">FA_SUM ER-funktion</span><span class="sxs-lookup"><span data-stu-id="cb267-103">FA_SUM ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="cb267-104">`FA_SUM`-funktionen returnerar ett värde för *behållare (post)* som består av data för anläggningstillgångsbeloppen för den angivna anläggningstillgångsartikeln, värdemodellkoden och datumperioden.</span><span class="sxs-lookup"><span data-stu-id="cb267-104">The `FA_SUM` function returns a *Container (record)* value that consists of data for the fixed asset amounts for the specified fixed asset item, value model code, and period of dates.</span></span>

## <a name="syntax"></a><span data-ttu-id="cb267-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="cb267-105">Syntax</span></span>

```vb
FA_SUM (fixed asset code, value model code, start date, end date)
```

## <a name="arguments"></a><span data-ttu-id="cb267-106">Argument</span><span class="sxs-lookup"><span data-stu-id="cb267-106">Arguments</span></span>

<span data-ttu-id="cb267-107">`fixed asset code`: *Sträng*</span><span class="sxs-lookup"><span data-stu-id="cb267-107">`fixed asset code`: *String*</span></span>

<span data-ttu-id="cb267-108">Ett *sträng*-värde som representerar koden för en anläggningstillgångsartikel som saldot beräknas för.</span><span class="sxs-lookup"><span data-stu-id="cb267-108">A *String* value that represents the code of a fixed asset item that the balance is calculated for.</span></span>

<span data-ttu-id="cb267-109">`value model code`: *Sträng*</span><span class="sxs-lookup"><span data-stu-id="cb267-109">`value model code`: *String*</span></span>

<span data-ttu-id="cb267-110">Ett *sträng*-värde som representerar koden för en värdemodell som saldot beräknas för.</span><span class="sxs-lookup"><span data-stu-id="cb267-110">A *String* value that represents the code of a value model that the balance is calculated for.</span></span>

<span data-ttu-id="cb267-111">`start date`: *Datum*</span><span class="sxs-lookup"><span data-stu-id="cb267-111">`start date`: *Date*</span></span>

<span data-ttu-id="cb267-112">Ett *datum*-värde som representerar startdatumet för en period som anläggningstillgångens belopp beräknas för.</span><span class="sxs-lookup"><span data-stu-id="cb267-112">A *Date* value that represents the start date of a period that the fixed asset amounts are calculated for.</span></span>

<span data-ttu-id="cb267-113">`end date`: *Datum*</span><span class="sxs-lookup"><span data-stu-id="cb267-113">`end date`: *Date*</span></span>

<span data-ttu-id="cb267-114">Ett *datum*-värde som representerar slutdatumet för en period som anläggningstillgångens belopp beräknas för.</span><span class="sxs-lookup"><span data-stu-id="cb267-114">A *Date* value that represents the end date of a period that the fixed asset amounts are calculated for.</span></span>

## <a name="return-values"></a><span data-ttu-id="cb267-115">Returvärden</span><span class="sxs-lookup"><span data-stu-id="cb267-115">Return values</span></span>

<span data-ttu-id="cb267-116">*Behållare (post)*</span><span class="sxs-lookup"><span data-stu-id="cb267-116">*Container (record)*</span></span>

<span data-ttu-id="cb267-117">Det resulterande postvärdet.</span><span class="sxs-lookup"><span data-stu-id="cb267-117">The resulting record value.</span></span>

## <a name="example"></a><span data-ttu-id="cb267-118">Exempel</span><span class="sxs-lookup"><span data-stu-id="cb267-118">Example</span></span>

<span data-ttu-id="cb267-119">`FA_SUM ("COMP-000001", "Current", Date1, Date2)` returnerar databehållaren för anläggningstillgången **COMP-000001** som har förberetts för den **aktuella** värdemodellen och för en period från **Datum1** till **Datum2**.</span><span class="sxs-lookup"><span data-stu-id="cb267-119">`FA_SUM ("COMP-000001", "Current", Date1, Date2)` returns the data container for fixed asset **COMP-000001** that has been prepared for the **Current** value model and for a period from **Date1** to **Date2**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="cb267-120">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="cb267-120">Additional resources</span></span>

[<span data-ttu-id="cb267-121">Andra (företagsdomänspecifika) funktioner</span><span class="sxs-lookup"><span data-stu-id="cb267-121">Other (business domain–specific) functions</span></span>](er-functions-category-other.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]