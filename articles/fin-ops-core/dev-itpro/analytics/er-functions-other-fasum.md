---
title: FA_SUM ER-funktion
description: Det här avsnittet innehåller information om hur funktionen FA_SUM elektronisk rapportering (ER) används.
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
ms.openlocfilehash: fccd318a8ab67528f0ce048fc770a2037f625d7a
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/01/2020
ms.locfileid: "3744152"
---
# <a name="fa_sum-er-function"></a><span data-ttu-id="df095-103">FA_SUM ER-funktion</span><span class="sxs-lookup"><span data-stu-id="df095-103">FA_SUM ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="df095-104">`FA_SUM`-funktionen returnerar ett värde för *behållare (post)* som består av data för anläggningstillgångsbeloppen för den angivna anläggningstillgångsartikeln, värdemodellkoden och datumperioden.</span><span class="sxs-lookup"><span data-stu-id="df095-104">The `FA_SUM` function returns a *Container (record)* value that consists of data for the fixed asset amounts for the specified fixed asset item, value model code, and period of dates.</span></span>

## <a name="syntax"></a><span data-ttu-id="df095-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="df095-105">Syntax</span></span>

```vb
FA_SUM (fixed asset code, value model code, start date, end date)
```

## <a name="arguments"></a><span data-ttu-id="df095-106">Argument</span><span class="sxs-lookup"><span data-stu-id="df095-106">Arguments</span></span>

<span data-ttu-id="df095-107">`fixed asset code`: *Sträng*</span><span class="sxs-lookup"><span data-stu-id="df095-107">`fixed asset code`: *String*</span></span>

<span data-ttu-id="df095-108">Ett *sträng*-värde som representerar koden för en anläggningstillgångsartikel som saldot beräknas för.</span><span class="sxs-lookup"><span data-stu-id="df095-108">A *String* value that represents the code of a fixed asset item that the balance is calculated for.</span></span>

<span data-ttu-id="df095-109">`value model code`: *Sträng*</span><span class="sxs-lookup"><span data-stu-id="df095-109">`value model code`: *String*</span></span>

<span data-ttu-id="df095-110">Ett *sträng*-värde som representerar koden för en värdemodell som saldot beräknas för.</span><span class="sxs-lookup"><span data-stu-id="df095-110">A *String* value that represents the code of a value model that the balance is calculated for.</span></span>

<span data-ttu-id="df095-111">`start date`: *Datum*</span><span class="sxs-lookup"><span data-stu-id="df095-111">`start date`: *Date*</span></span>

<span data-ttu-id="df095-112">Ett *datum*-värde som representerar startdatumet för en period som anläggningstillgångens belopp beräknas för.</span><span class="sxs-lookup"><span data-stu-id="df095-112">A *Date* value that represents the start date of a period that the fixed asset amounts are calculated for.</span></span>

<span data-ttu-id="df095-113">`end date`: *Datum*</span><span class="sxs-lookup"><span data-stu-id="df095-113">`end date`: *Date*</span></span>

<span data-ttu-id="df095-114">Ett *datum*-värde som representerar slutdatumet för en period som anläggningstillgångens belopp beräknas för.</span><span class="sxs-lookup"><span data-stu-id="df095-114">A *Date* value that represents the end date of a period that the fixed asset amounts are calculated for.</span></span>

## <a name="return-values"></a><span data-ttu-id="df095-115">Returvärden</span><span class="sxs-lookup"><span data-stu-id="df095-115">Return values</span></span>

<span data-ttu-id="df095-116">*Behållare (post)*</span><span class="sxs-lookup"><span data-stu-id="df095-116">*Container (record)*</span></span>

<span data-ttu-id="df095-117">Det resulterande postvärdet.</span><span class="sxs-lookup"><span data-stu-id="df095-117">The resulting record value.</span></span>

## <a name="example"></a><span data-ttu-id="df095-118">Exempel</span><span class="sxs-lookup"><span data-stu-id="df095-118">Example</span></span>

<span data-ttu-id="df095-119">`FA_SUM ("COMP-000001", "Current", Date1, Date2)` returnerar databehållaren för anläggningstillgången **COMP-000001** som har förberetts för den **aktuella** värdemodellen och för en period från **Datum1** till **Datum2**.</span><span class="sxs-lookup"><span data-stu-id="df095-119">`FA_SUM ("COMP-000001", "Current", Date1, Date2)` returns the data container for fixed asset **COMP-000001** that has been prepared for the **Current** value model and for a period from **Date1** to **Date2**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="df095-120">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="df095-120">Additional resources</span></span>

[<span data-ttu-id="df095-121">Andra (företagsdomänspecifika) funktioner</span><span class="sxs-lookup"><span data-stu-id="df095-121">Other (business domain–specific) functions</span></span>](er-functions-category-other.md)
