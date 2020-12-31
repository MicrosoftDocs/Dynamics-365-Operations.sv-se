---
title: GETCURRENTCOMPANY ER-funktionen
description: Det här avsnittet innehåller information om hur funktionen GETCURRENTCOMPANY elektronisk rapportering (ER) används.
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
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 3e14c6a8aaff0a32a115117938d0e853bb34bb14
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/05/2020
ms.locfileid: "4684869"
---
# <a name="getcurrentcompany-er-function"></a><span data-ttu-id="9ca97-103">GETCURRENTCOMPANY ER-funktionen</span><span class="sxs-lookup"><span data-stu-id="9ca97-103">GETCURRENTCOMPANY ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="9ca97-104">Funktionen `GETCURRENTCOMPANY` returnerar ett *Sträng*-värde som representerar koden för den juridiska person (företag) som användaren är inloggad i för närvarande.</span><span class="sxs-lookup"><span data-stu-id="9ca97-104">The `GETCURRENTCOMPANY` function returns a *String* value that represents the code for the legal entity (company) that a user is currently signed in to.</span></span>

## <a name="syntax"></a><span data-ttu-id="9ca97-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="9ca97-105">Syntax</span></span>

```vb
GETCURRENTCOMPANY ()
```

## <a name="return-values"></a><span data-ttu-id="9ca97-106">Returvärden</span><span class="sxs-lookup"><span data-stu-id="9ca97-106">Return values</span></span>

<span data-ttu-id="9ca97-107">*Sträng*</span><span class="sxs-lookup"><span data-stu-id="9ca97-107">*String*</span></span>

<span data-ttu-id="9ca97-108">Det resulterande textvärdet.</span><span class="sxs-lookup"><span data-stu-id="9ca97-108">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="9ca97-109">Exempel</span><span class="sxs-lookup"><span data-stu-id="9ca97-109">Example</span></span>

<span data-ttu-id="9ca97-110">`GETCURRENTCOMPANY ()` returnerar **USMF** för en användare som är inloggad på företaget **Contoso Entertainment System USA**.</span><span class="sxs-lookup"><span data-stu-id="9ca97-110">`GETCURRENTCOMPANY ()` returns **USMF** for a user who is signed in to the **Contoso Entertainment System USA** company.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="9ca97-111">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="9ca97-111">Additional resources</span></span>

[<span data-ttu-id="9ca97-112">Andra (företagsdomänspecifika) funktioner</span><span class="sxs-lookup"><span data-stu-id="9ca97-112">Other (business domain–specific) functions</span></span>](er-functions-category-other.md)
