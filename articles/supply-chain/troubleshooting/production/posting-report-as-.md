---
title: Fel när journalen Rapportera som klar bokförs
description: När du bokför journalen Rapportera som klar får du ett felmeddelande om att den beställda kvantiteten inte kan minskas.
author: johanhoffmann
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: ProdTableListPage, ProdParameters
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 55db7d0033dd66c1b973abf96671a20ab05d61d8
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026904"
---
# <a name="error-when-the-report-as-finished-journal-is-posted"></a><span data-ttu-id="2d31c-103">Fel när journalen Rapportera som klar bokförs</span><span class="sxs-lookup"><span data-stu-id="2d31c-103">Error when the Report as finished journal is posted</span></span>

<span data-ttu-id="2d31c-104">KB-nummer: 4612891</span><span class="sxs-lookup"><span data-stu-id="2d31c-104">KB number: 4612891</span></span>

## <a name="symptoms"></a><span data-ttu-id="2d31c-105">Symtom</span><span class="sxs-lookup"><span data-stu-id="2d31c-105">Symptoms</span></span>

<span data-ttu-id="2d31c-106">När du bokför journalen **Rapportera som klar** uppstår ett fel och följande felmeddelande visas:</span><span class="sxs-lookup"><span data-stu-id="2d31c-106">When you post the **Report as finished** journal, an error occurs, and you receive the following error message:</span></span>

> <span data-ttu-id="2d31c-107">Det går inte att minska beställd kvantitet eftersom det inte finns tillräckligt med öppna lagertransaktioner med status Beställt.</span><span class="sxs-lookup"><span data-stu-id="2d31c-107">Quantity ordered cannot be reduced because there are not enough open inventory transactions with the ordered status.</span></span> <span data-ttu-id="2d31c-108">Artiklarna köps, tas emot eller registreras.</span><span class="sxs-lookup"><span data-stu-id="2d31c-108">The items are Purchased, Received or Registered.</span></span>

<span data-ttu-id="2d31c-109">Det här felet uppstår endast när fältet **Felkvantitet** är inställt på den första raden av journalen **Rapporter som klar** och fältet **Bra kvantitet** är inställt på den sista raden.</span><span class="sxs-lookup"><span data-stu-id="2d31c-109">This error occurs only when the **Error quantity** field is set on the first line of the **Report as finished** journal, and the **Good quantity** field is set on the last line.</span></span> <span data-ttu-id="2d31c-110">Om fältet **Felkvantitet** anges på den sista raden uppstår inget fel.</span><span class="sxs-lookup"><span data-stu-id="2d31c-110">If the **Error quantity** field is set on the last line, no error occurs.</span></span>

## <a name="resolution"></a><span data-ttu-id="2d31c-111">Upplösning</span><span class="sxs-lookup"><span data-stu-id="2d31c-111">Resolution</span></span>

<span data-ttu-id="2d31c-112">För att förhindra detta fel öppnar du sidan **Produktionskontrollparametrar** och sedan, under fliken **Allmänt**, ställer du in alternativet **Öka kvarvarande kvantitet med felkvantitet** på *Ja*.</span><span class="sxs-lookup"><span data-stu-id="2d31c-112">To prevent this error, open the **Production control parameters** page, and then, on the **General** tab, set the **Increase remain qty with error qty** option to *Yes*.</span></span>
