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
ms.search.scope: Core, Operations
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a0b4c93a4705cd0e382b9b6c7af1d199beeceabe
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/20/2019
ms.locfileid: "2916003"
---
# <span data-ttu-id="19574-103"><a name="GETCURRENTCOMPANY">GETCURRENTCOMPANY ER-funktionen</a></span><span class="sxs-lookup"><span data-stu-id="19574-103"><a name="GETCURRENTCOMPANY">GETCURRENTCOMPANY ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="19574-104">Funktionen `GETCURRENTCOMPANY` returnerar ett *Sträng*-värde som representerar koden för den juridiska person (företag) som användaren är inloggad i för närvarande.</span><span class="sxs-lookup"><span data-stu-id="19574-104">The `GETCURRENTCOMPANY` function returns a *String* value that represents the code for the legal entity (company) that a user is currently signed in to.</span></span>

## <a name="syntax"></a><span data-ttu-id="19574-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="19574-105">Syntax</span></span>

```
GETCURRENTCOMPANY ()
```

## <a name="return-values"></a><span data-ttu-id="19574-106">Returvärden</span><span class="sxs-lookup"><span data-stu-id="19574-106">Return values</span></span>

<span data-ttu-id="19574-107">*Sträng*</span><span class="sxs-lookup"><span data-stu-id="19574-107">*String*</span></span>

<span data-ttu-id="19574-108">Det resulterande textvärdet.</span><span class="sxs-lookup"><span data-stu-id="19574-108">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="19574-109">Exempel</span><span class="sxs-lookup"><span data-stu-id="19574-109">Example</span></span>

<span data-ttu-id="19574-110">`GETCURRENTCOMPANY ()` returnerar **USMF** för en användare som är inloggad på företaget **Contoso Entertainment System USA**.</span><span class="sxs-lookup"><span data-stu-id="19574-110">`GETCURRENTCOMPANY ()` returns **USMF** for a user who is signed in to the **Contoso Entertainment System USA** company.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="19574-111">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="19574-111">Additional resources</span></span>

[<span data-ttu-id="19574-112">Andra (företagsdomänspecifika) funktioner</span><span class="sxs-lookup"><span data-stu-id="19574-112">Other (business domain–specific) functions</span></span>](er-functions-category-other.md)