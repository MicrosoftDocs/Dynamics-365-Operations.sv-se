---
title: TEXT ER-funktion
description: Det här avsnittet innehåller information om hur funktionen TEXT elektronisk rapportering (ER) används.
author: NickSelin
manager: kfend
ms.date: 12/10/2019
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
ms.openlocfilehash: 5da7375020be827f432ba97740da37abe48962fc
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/09/2021
ms.locfileid: "5560071"
---
# <a name="text-er-function"></a><span data-ttu-id="efb1d-103">TEXT ER-funktion</span><span class="sxs-lookup"><span data-stu-id="efb1d-103">TEXT ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="efb1d-104">Returnera `TEXT`-funktionen det specificerade numret som ett *Sträng*-värde efter att den har konverteras till en textsträng formaterad enligt serverns lokala inställningar för den aktuella programinstansen.</span><span class="sxs-lookup"><span data-stu-id="efb1d-104">The `TEXT` function returns the specified number as a *String* value after it has been converted to a text string that is formatted according to the server locale settings of the current application instance.</span></span>

## <a name="syntax"></a><span data-ttu-id="efb1d-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="efb1d-105">Syntax</span></span>

```vb
TEXT (number)
```

## <a name="arguments"></a><span data-ttu-id="efb1d-106">Argument</span><span class="sxs-lookup"><span data-stu-id="efb1d-106">Arguments</span></span>

<span data-ttu-id="efb1d-107">`number`: *Heltal* eller *Realtal*</span><span class="sxs-lookup"><span data-stu-id="efb1d-107">`number`: *Integer* or *Real*</span></span>

<span data-ttu-id="efb1d-108">Ett tal som måste konverteras till en textsträng.</span><span class="sxs-lookup"><span data-stu-id="efb1d-108">A number that must be converted to a text string.</span></span>

## <a name="return-values"></a><span data-ttu-id="efb1d-109">Returvärden</span><span class="sxs-lookup"><span data-stu-id="efb1d-109">Return values</span></span>

<span data-ttu-id="efb1d-110">*Sträng*</span><span class="sxs-lookup"><span data-stu-id="efb1d-110">*String*</span></span>

<span data-ttu-id="efb1d-111">Det resulterande textvärdet.</span><span class="sxs-lookup"><span data-stu-id="efb1d-111">The resulting text value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="efb1d-112">Användningsanteckningar</span><span class="sxs-lookup"><span data-stu-id="efb1d-112">Usage notes</span></span>

<span data-ttu-id="efb1d-113">För värden av typen *Realtal* är strängkonverteringen begränsad till två decimaler.</span><span class="sxs-lookup"><span data-stu-id="efb1d-113">For values of the *Real* type, the string conversion is limited to two decimal places.</span></span>

## <a name="example"></a><span data-ttu-id="efb1d-114">Exempel</span><span class="sxs-lookup"><span data-stu-id="efb1d-114">Example</span></span>

<span data-ttu-id="efb1d-115">Om serverns lokala inställningar för Microsoft Dynamics 365 Finance-instansen definieras som **EN-US**, `TEXT (NOW ())` returnerar det aktuella Finance sessionsdatumet, 17 december 2015, som textsträng **"12/17/2015 07:59:23 AM"**.</span><span class="sxs-lookup"><span data-stu-id="efb1d-115">If the server locale of the Microsoft Dynamics 365 Finance instance is defined as **EN-US**, `TEXT (NOW ())` returns the current Finance session date, December 17, 2015, as the text string **"12/17/2015 07:59:23 AM"**.</span></span> <span data-ttu-id="efb1d-116">`TEXT (1/3)` returnerar **"0.33"**.</span><span class="sxs-lookup"><span data-stu-id="efb1d-116">`TEXT (1/3)` returns **"0.33"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="efb1d-117">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="efb1d-117">Additional resources</span></span>

[<span data-ttu-id="efb1d-118">Textfunktioner</span><span class="sxs-lookup"><span data-stu-id="efb1d-118">Text functions</span></span>](er-functions-category-text.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]