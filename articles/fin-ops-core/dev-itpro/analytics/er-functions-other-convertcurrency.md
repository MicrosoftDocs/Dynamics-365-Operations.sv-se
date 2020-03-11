---
title: Funktionen CONVERTCURRENCY ER
description: Det här avsnittet innehåller information om hur funktionen CONVERTCURRENCY elektronisk rapportering (ER) används.
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
ms.openlocfilehash: 1d0c168e07252f7c423271bc808f3fca3834077f
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/12/2020
ms.locfileid: "3041525"
---
# <span data-ttu-id="abdec-103"><a name="CONVERTCURRENCY">Funktionen CONVERTCURRENCY ER</a></span><span class="sxs-lookup"><span data-stu-id="abdec-103"><a name="CONVERTCURRENCY">CONVERTCURRENCY ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="abdec-104">`CONVERTCURRENCY`-funktionen returnerar ett *Realtal*-värde som representerar resultatet av att konvertera det angivna monetära beloppet från den angivna källvalutan till den angivna målvalutan genom att använda inställningarna för det angivna företaget på det angivna datumet.</span><span class="sxs-lookup"><span data-stu-id="abdec-104">The `CONVERTCURRENCY` function returns a *Real* value that represents the result of converting the specified monetary amount from the specified source currency to the specified target currency by using the settings of the specified company on the specified date.</span></span>

## <a name="syntax"></a><span data-ttu-id="abdec-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="abdec-105">Syntax</span></span>

```vb
CONVERTCURRENCY (amount, source currency, target currency, date, company)
```

## <a name="arguments"></a><span data-ttu-id="abdec-106">Argument</span><span class="sxs-lookup"><span data-stu-id="abdec-106">Arguments</span></span>

<span data-ttu-id="abdec-107">`amount`: *Heltal* eller *Realtal*</span><span class="sxs-lookup"><span data-stu-id="abdec-107">`amount`: *Integer* or *Real*</span></span>

<span data-ttu-id="abdec-108">Ett numeriskt värde som representerar det monetära belopp som måste konverteras.</span><span class="sxs-lookup"><span data-stu-id="abdec-108">A numeric value that represents the monetary amount that must be converted.</span></span>

<span data-ttu-id="abdec-109">`source currency`: *Sträng*</span><span class="sxs-lookup"><span data-stu-id="abdec-109">`source currency`: *String*</span></span>

<span data-ttu-id="abdec-110">Koden för källvalutan.</span><span class="sxs-lookup"><span data-stu-id="abdec-110">The code of the source currency.</span></span>

<span data-ttu-id="abdec-111">`target currency`: *Sträng*</span><span class="sxs-lookup"><span data-stu-id="abdec-111">`target currency`: *String*</span></span>

<span data-ttu-id="abdec-112">Koden för målvalutan.</span><span class="sxs-lookup"><span data-stu-id="abdec-112">The code of the target currency.</span></span>

<span data-ttu-id="abdec-113">`date`: *Datum*</span><span class="sxs-lookup"><span data-stu-id="abdec-113">`date`: *Date*</span></span>

<span data-ttu-id="abdec-114">Ett *datum*-värde som representerar det datum som används för att bestämma valutakursen för konverteringen.</span><span class="sxs-lookup"><span data-stu-id="abdec-114">A *Date* value that represents the date that is used to determine the exchange rate for the conversion.</span></span>

<span data-ttu-id="abdec-115">`company`: *Sträng*</span><span class="sxs-lookup"><span data-stu-id="abdec-115">`company`: *String*</span></span>

<span data-ttu-id="abdec-116">Ett *sträng*-värde som representerar koden för ett företag som tillhandahåller de inställningar som används för konverteringen.</span><span class="sxs-lookup"><span data-stu-id="abdec-116">A *String* value that represents the code of a company that supplies the settings that are used for the conversion.</span></span>

## <a name="return-values"></a><span data-ttu-id="abdec-117">Returvärden</span><span class="sxs-lookup"><span data-stu-id="abdec-117">Return values</span></span>

<span data-ttu-id="abdec-118">*Realtal*</span><span class="sxs-lookup"><span data-stu-id="abdec-118">*Real*</span></span>

<span data-ttu-id="abdec-119">Det resulterande numeriska värdet.</span><span class="sxs-lookup"><span data-stu-id="abdec-119">The resulting numeric value.</span></span>

## <a name="example"></a><span data-ttu-id="abdec-120">Exempel</span><span class="sxs-lookup"><span data-stu-id="abdec-120">Example</span></span>

<span data-ttu-id="abdec-121">`CONVERTCURRENCY (1, "EUR", "USD", TODAY(), "DEMF")` returnerar motsvarigheten för en euro i US-dollar för det aktuella sessionsdatumet baserat på inställningarna för **DEMF**-företaget.</span><span class="sxs-lookup"><span data-stu-id="abdec-121">`CONVERTCURRENCY (1, "EUR", "USD", TODAY(), "DEMF")` returns the equivalent of one euro in US dollars on the current session date, based on settings for the **DEMF** company.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="abdec-122">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="abdec-122">Additional resources</span></span>

[<span data-ttu-id="abdec-123">Andra (företagsdomänspecifika) funktioner</span><span class="sxs-lookup"><span data-stu-id="abdec-123">Other (business domain–specific) functions</span></span>](er-functions-category-other.md)
