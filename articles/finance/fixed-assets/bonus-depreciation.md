---
title: Bonusavskrivning
description: Det här avsnittet innehåller en översikt över funktionen för bonusavskrivning.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetBonus
audience: Application User
ms.reviewer: roschlom
ms.custom: 3621
ms.assetid: 835ec594-744e-461c-a676-1b9abc094173
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1500eb6dd74576e21708907229d60362a6534077
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5257595"
---
# <a name="bonus-depreciation"></a><span data-ttu-id="1d392-103">Bonusavskrivning</span><span class="sxs-lookup"><span data-stu-id="1d392-103">Bonus depreciation</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="1d392-104">Det här avsnittet innehåller en översikt över funktionen för bonusavskrivning.</span><span class="sxs-lookup"><span data-stu-id="1d392-104">This article provides an overview of the bonus depreciation functionality.</span></span>

<span data-ttu-id="1d392-105">För bonusavskrivning kan du ta extra- eller bonusavskrivningsbelopp under det första året som tillgången tas i drift och skrivs av.</span><span class="sxs-lookup"><span data-stu-id="1d392-105">For bonus depreciation, you can take extra or bonus depreciation amounts during the first year that the asset is put in service and depreciated.</span></span> <span data-ttu-id="1d392-106">Bonusavskrivning måste göras före andra avskrivningsberäkningar.</span><span class="sxs-lookup"><span data-stu-id="1d392-106">Bonus depreciation must be taken before any other depreciation calculations.</span></span> <span data-ttu-id="1d392-107">Därför är det bäst att använda bonusavskrivning med böcker där funktionen Bokför i huvudboken har inaktiverats.</span><span class="sxs-lookup"><span data-stu-id="1d392-107">Therefore, it's best to use bonus depreciation with books where the Post to general ledger functionality is disabled.</span></span> <span data-ttu-id="1d392-108">Du kan använda alternativet **Radera transaktioner som inte har bokförts i redovisning** för att radera historiska transaktioner för böcker som inte bokförs i redovisningen.</span><span class="sxs-lookup"><span data-stu-id="1d392-108">You can use the **Delete transactions not posted to general ledger** option to delete historical transactions for books that don't post to the general ledger.</span></span> <span data-ttu-id="1d392-109">Du kan sedan tillgodose bonusavskrivningen senare i tillgångens livscykel genom att ta bort avskrivningstransaktioner som tidigare bokförts.</span><span class="sxs-lookup"><span data-stu-id="1d392-109">You can then accommodate bonus depreciation later in the asset life cycle by deleting depreciation transactions that were previously posted.</span></span> 

<span data-ttu-id="1d392-110">Du kan beräkna bonusavskrivning med förslagsprocessen eller skapa manuella transaktioner för bonusavskrivningar.</span><span class="sxs-lookup"><span data-stu-id="1d392-110">You can calculate bonus depreciation by using the proposal process, or you can create manual bonus depreciation transactions.</span></span> <span data-ttu-id="1d392-111">Du kan inte skapa transaktioner för bonusavskrivning om det finns transaktioner för avskrivning eller avskrivningsjustering för den tillgångsförteckningen.</span><span class="sxs-lookup"><span data-stu-id="1d392-111">You can't create bonus depreciation transactions if depreciation transactions or depreciation adjustment transactions exist for that asset book.</span></span>

<span data-ttu-id="1d392-112">När du använder förslagsprocessen för att beräkna bonusavskrivning tas alla befintliga bonustransaktioner med i beräkningen av basen.</span><span class="sxs-lookup"><span data-stu-id="1d392-112">When you use the proposal process to calculate bonus depreciation, all existing bonus transactions are included in the calculation of the basis.</span></span> <span data-ttu-id="1d392-113">Beräkningen innefattar också eventuella tidigare bonusavskrivningar som du manuellt har angett för tillgången.</span><span class="sxs-lookup"><span data-stu-id="1d392-113">The calculation also includes any previous bonus depreciations that you manually entered for the asset.</span></span> 

<span data-ttu-id="1d392-114">Om mer än en bonusavskrivning ska göras för en tillgång tas hänsyn till prioriteten.</span><span class="sxs-lookup"><span data-stu-id="1d392-114">If more than one bonus depreciation will be taken for an asset, the priority is considered.</span></span> <span data-ttu-id="1d392-115">Varje bonus reducerar tillgångsunderlaget för nästa bonus.</span><span class="sxs-lookup"><span data-stu-id="1d392-115">Each bonus reduces the asset basis for the next bonus.</span></span> <span data-ttu-id="1d392-116">Skrotvärdet räknas inte in i tillgångsunderlaget för beräkningar av bonusavskrivning, och avskrivningspraxis gäller inte för bonusavskrivningar.</span><span class="sxs-lookup"><span data-stu-id="1d392-116">Salvage value isn't considered in the asset basis for bonus depreciation calculations, and the depreciation convention doesn't apply for bonus depreciation.</span></span> 

<span data-ttu-id="1d392-117">I USA räknas för närvarande viss egendom som paragraf 179-egendom.</span><span class="sxs-lookup"><span data-stu-id="1d392-117">Currently, in the United States, some property qualifies as Section 179 property.</span></span> <span data-ttu-id="1d392-118">Genom att använda avdrag enligt paragraf 179 kan du skriva av hela eller en del av kostnaden för viss egendom, upp till en viss gräns.</span><span class="sxs-lookup"><span data-stu-id="1d392-118">By using the Section 179 deduction, you can recover all or part of the cost of some property, up to a limit.</span></span> <span data-ttu-id="1d392-119">Du kan skriva av kostnaden genom att dra av den under det år då egendomen tas i drift.</span><span class="sxs-lookup"><span data-stu-id="1d392-119">You can recover the cost by deducting it in the year when you put the property in service.</span></span>

## <a name="example"></a><span data-ttu-id="1d392-120">Exempel</span><span class="sxs-lookup"><span data-stu-id="1d392-120">Example</span></span>
<span data-ttu-id="1d392-121">Följande bonusavskrivningar är associerade med en tillgångsförteckning:</span><span class="sxs-lookup"><span data-stu-id="1d392-121">The following bonus depreciations are associated with an asset book:</span></span>

-   <span data-ttu-id="1d392-122">**Paragraf 179:** 1 000,00, Prioritet 1</span><span class="sxs-lookup"><span data-stu-id="1d392-122">**Section 179:** 1,000.00, Priority 1</span></span>
-   <span data-ttu-id="1d392-123">**Frihetszon:** 30 procent, Prioritet 2</span><span class="sxs-lookup"><span data-stu-id="1d392-123">**Liberty Zone:** 30 percent, Priority 2</span></span>

<span data-ttu-id="1d392-124">Anskaffningskostnaden för tillgången är 5 000,00 $.</span><span class="sxs-lookup"><span data-stu-id="1d392-124">The asset acquisition cost is 5,000.00.</span></span> <span data-ttu-id="1d392-125">När bonusavskrivningen beräknas blir det första bonusavskrivningsbeloppet 1 000,00 $ för paragraf 179-avskrivningen.</span><span class="sxs-lookup"><span data-stu-id="1d392-125">When bonus depreciation is calculated, the first bonus depreciation amount is 1,000.00 for the Section 179 depreciation.</span></span> 

<span data-ttu-id="1d392-126">Nästa bonusavskrivningsbelopp – för Liberty Zone-avskrivningen – beräknas enligt följande:</span><span class="sxs-lookup"><span data-stu-id="1d392-126">The next bonus depreciation amount, for the Liberty Zone depreciation, is calculated as follows:</span></span> 

<span data-ttu-id="1d392-127">Anskaffningskostnad – 1 000 (paragraf 179-avskrivning) x 30 % = 1 200</span><span class="sxs-lookup"><span data-stu-id="1d392-127">Acquisition cost – 1,000 (Section 179 depreciation) × 30 percent = 1,200</span></span> 

<span data-ttu-id="1d392-128">Om bonusavskrivningsbeloppet överstiger resterande anskaffningskostnad, blir bonusavskrivningsbeloppet antingen resultatet av den beräknade bonusavskrivning eller den återstående anskaffningskostnaden (det lägre beloppet av dessa).</span><span class="sxs-lookup"><span data-stu-id="1d392-128">If the bonus depreciation amount is more than the remaining acquisition cost, the bonus depreciation amount is either the result of the bonus depreciation calculation or the remaining acquisition cost, whichever amount is less.</span></span> 

<span data-ttu-id="1d392-129">Om resterande anskaffningskostnad är noll eller lägre kan bonusavskrivningstransaktionerna inte genereras.</span><span class="sxs-lookup"><span data-stu-id="1d392-129">If the remaining acquisition cost is 0 (zero) or less, bonus depreciation transactions isn't generated.</span></span> 

<span data-ttu-id="1d392-130">När bonusavskrivning beräknas med förslagsprocessen skapas en transaktion för bonusavskrivning för alla tillämpliga bonusavskrivningsposter som är associerade med tillgångsförteckningen.</span><span class="sxs-lookup"><span data-stu-id="1d392-130">When bonus depreciation is calculated by using the proposal process, a bonus depreciation transaction is created for all applicable bonus depreciation records that are associated with the asset book.</span></span> 

<span data-ttu-id="1d392-131">Du kan skapa ett obegränsat antal bonusavskrivningsposter.</span><span class="sxs-lookup"><span data-stu-id="1d392-131">You can create an unlimited number of bonus depreciation records.</span></span> <span data-ttu-id="1d392-132">När du har tilldelat dessa poster till en räkenskapsbok, appliceras de på tillgångsförteckningen.</span><span class="sxs-lookup"><span data-stu-id="1d392-132">After you assign those records to the asset group book, they are applied to the asset book.</span></span> 

<span data-ttu-id="1d392-133">Bonusavskrivning anges i procent eller som ett fast belopp.</span><span class="sxs-lookup"><span data-stu-id="1d392-133">Bonus depreciation is entered as either a percentage or a fixed amount.</span></span> <span data-ttu-id="1d392-134">När du bokför avskrivningsförslag, bokförs transaktioner för bonusavskrivning till boken som transaktioner som är skilda från avskrivningstransaktionerna.</span><span class="sxs-lookup"><span data-stu-id="1d392-134">When you post depreciation proposals, bonus depreciation transactions are posted to the book as separate transactions from the depreciation transactions.</span></span>





[!INCLUDE[footer-include](../../includes/footer-banner.md)]