---
title: Avskrivning av anläggningstillgång
description: Den här ämnet ger en översikt över avskrivning för anläggningstillgångar.
author: ShylaThompson
ms.date: 10/30/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetBonus, AssetBookTable
audience: Application User
ms.reviewer: roschlom
ms.custom: 3121
ms.assetid: 98ff891f-e0e2-4184-b618-28107a50851f
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1ec8544b885485781b0b9c0a59ec47f90fdceb6b
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5826892"
---
# <a name="fixed-asset-depreciation"></a><span data-ttu-id="9fc79-103">Avskrivning av anläggningstillgång</span><span class="sxs-lookup"><span data-stu-id="9fc79-103">Fixed asset depreciation</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="9fc79-104">Den här ämnet ger en översikt över avskrivning för anläggningstillgångar.</span><span class="sxs-lookup"><span data-stu-id="9fc79-104">This topic provides an overview of depreciation for fixed assets.</span></span>

<span data-ttu-id="9fc79-105">Avskrivning är en periodisk transaktion som normalt minskar anläggningstillgångens värde i balansräkningen och debiteras som en utgift på ett resultatkonto.</span><span class="sxs-lookup"><span data-stu-id="9fc79-105">Depreciation is a periodic transaction that typically reduces the value of the fixed asset on the balance sheet, and is charged as an expenditure to a profit and loss account.</span></span> <span data-ttu-id="9fc79-106">Därför används vanligtvis ett huvudkonto för att kreditera den periodiska avskrivningen i balansräkningen.</span><span class="sxs-lookup"><span data-stu-id="9fc79-106">Therefore, a main account is typically used to credit the periodic depreciation on the balance sheet.</span></span> <span data-ttu-id="9fc79-107">Ett motkonto är ett konto i kontoplanens resultatdel.</span><span class="sxs-lookup"><span data-stu-id="9fc79-107">An offset account is an account in the profit and loss part of the chart of accounts.</span></span>

## <a name="depreciation-adjustment"></a><span data-ttu-id="9fc79-108">Avskrivningsjustering</span><span class="sxs-lookup"><span data-stu-id="9fc79-108">Depreciation adjustment</span></span>
<span data-ttu-id="9fc79-109">Vanligtvis bokförs bara en korrigering av en redan bokförd avskrivningstransaktion som en avskrivningsjustering.</span><span class="sxs-lookup"><span data-stu-id="9fc79-109">Usually, only a correction to a posted depreciation transaction is posted as a depreciation adjustment.</span></span> <span data-ttu-id="9fc79-110">Därför ställs både huvudkontot och motkontot in på samma sätt som kontona för avskrivning.</span><span class="sxs-lookup"><span data-stu-id="9fc79-110">Therefore, both the main account and the offset account are set up just like the accounts for depreciation.</span></span> <span data-ttu-id="9fc79-111">En avskrivningsjustering kan vara antingen ett positivt eller negativt belopp, men funktionen för huvudkontot (som balansräkningskonto) och motkontot (vanligtvis som ett resultatkonto) förblir oförändrad.</span><span class="sxs-lookup"><span data-stu-id="9fc79-111">A depreciation adjustment can be either a positive amount or a negative amount, but the functionality of the main account (as a balance sheet account) and the functionality of the offset account (usually as a profit and loss account) remain the same.</span></span>

## <a name="extraordinary-depreciation"></a><span data-ttu-id="9fc79-112">Extraordinär avskrivning</span><span class="sxs-lookup"><span data-stu-id="9fc79-112">Extraordinary depreciation</span></span>
<span data-ttu-id="9fc79-113">En extraordinär avskrivning fungerar som en grundläggande avskrivning.</span><span class="sxs-lookup"><span data-stu-id="9fc79-113">Extraordinary depreciation works like basic depreciation.</span></span> <span data-ttu-id="9fc79-114">Därför används ett huvudkonto används för att kreditera avskrivningsbeloppet till balansräkningen och minska värdet på anläggningstillgången.</span><span class="sxs-lookup"><span data-stu-id="9fc79-114">Therefore, a main account is used to credit the depreciation amount to the balance sheet and reduce the value of the fixed asset.</span></span> <span data-ttu-id="9fc79-115">En motkonto är ett resultatkonto där avskrivningen som beräknas för räkenskapsperioden, debiteras som en utgift.</span><span class="sxs-lookup"><span data-stu-id="9fc79-115">An offset account is a profit and loss account, where the depreciation that is calculated for the fiscal period is charged as an expenditure.</span></span> 

<span data-ttu-id="9fc79-116">Extraordinär avskrivning fungerar oberoende av den grundläggande avskrivningen.</span><span class="sxs-lookup"><span data-stu-id="9fc79-116">Extraordinary depreciation works independently of basic depreciation.</span></span> <span data-ttu-id="9fc79-117">Genom att ha extraordinär avskrivning som en separat transaktionstyp kan du bokföra och rapportera den extraordinära avskrivningen separat från den grundläggande avskrivningen.</span><span class="sxs-lookup"><span data-stu-id="9fc79-117">By having extraordinary depreciation as a separate transaction type, you can post and report the extraordinary depreciation separately from the basic depreciation.</span></span>

## <a name="special-depreciation-allowance"></a><span data-ttu-id="9fc79-118">Särskild avskrivning</span><span class="sxs-lookup"><span data-stu-id="9fc79-118">Special depreciation allowance</span></span>
<span data-ttu-id="9fc79-119">Du kan använda särskilda avskrivningar för att ta extra- eller bonusavskrivningsbelopp under det första året som en tillgång tas i drift och skrivs av.</span><span class="sxs-lookup"><span data-stu-id="9fc79-119">You can use special depreciation allowances to take extra depreciation amounts during the first year that an asset is put in service and depreciated.</span></span> <span data-ttu-id="9fc79-120">Särskilda avskrivningar måste göras före andra avskrivningsberäkningar.</span><span class="sxs-lookup"><span data-stu-id="9fc79-120">Special depreciation allowances must be taken before any other depreciation calculations.</span></span> <span data-ttu-id="9fc79-121">Eftersom särskilda avskrivningar ofta är okända förrän senare under tjänstelivstiden för anläggningstillgången, är det bästa att använda den här typen av avskrivning med en bok som inte bokför i redovisningen.</span><span class="sxs-lookup"><span data-stu-id="9fc79-121">Because special depreciation allowances are often unknown until later in the service life of the fixed asset, it's best to use this type of depreciation with a book that doesn't post to the general ledger.</span></span> <span data-ttu-id="9fc79-122">Du kan använda den periodiska funktionen Radera transaktioner som inte har bokförts i redovisning för att radera transaktionshistoriken för dessa böcker.</span><span class="sxs-lookup"><span data-stu-id="9fc79-122">You can use the Delete transactions not posted to general ledger periodic function to delete the transaction history for these books.</span></span> <span data-ttu-id="9fc79-123">Du kan sedan ta bort avskrivninghistoriken för Anläggningstillgångsboken, bokföra den särskilda avskrivningen när denna är känd, och sedan bokföra årets återstående avskrivningstransaktioner.</span><span class="sxs-lookup"><span data-stu-id="9fc79-123">You can then delete the depreciation history for the fixed asset book, post the special depreciation allowance when it's known, and then post the remaining depreciation transactions for the year.</span></span> 

<span data-ttu-id="9fc79-124">Du kan skapa ett obegränsat antal poster för särskild avdragsavskrivning.</span><span class="sxs-lookup"><span data-stu-id="9fc79-124">You can create an unlimited number of special depreciation allowance records.</span></span> <span data-ttu-id="9fc79-125">När du har tilldelat dessa poster till en räkenskapsbok, appliceras dessa på tillgångsboken.</span><span class="sxs-lookup"><span data-stu-id="9fc79-125">After you assign those records to an asset group book, they are applied to the asset book.</span></span> 

<span data-ttu-id="9fc79-126">En särskild avskrivning anges antingen som en procentsats eller som ett fast belopp.</span><span class="sxs-lookup"><span data-stu-id="9fc79-126">A special depreciation allowance is entered as either a percentage or a fixed amount.</span></span> <span data-ttu-id="9fc79-127">När du bokför avskrivningsförslag bokförs särskilda avskrivningar till boken som transaktioner som är separata från avskrivningstransaktionerna.</span><span class="sxs-lookup"><span data-stu-id="9fc79-127">When you post depreciation proposals, special depreciation allowance transactions are posted to the book as transactions that are separate from the depreciation transactions.</span></span>

## <a name="depreciation-calendars"></a><span data-ttu-id="9fc79-128">Kalender för avskrivning</span><span class="sxs-lookup"><span data-stu-id="9fc79-128">Depreciation calendars</span></span>
<span data-ttu-id="9fc79-129">Varje bok har en kalender som används när du skriver av anläggningstillgångar.</span><span class="sxs-lookup"><span data-stu-id="9fc79-129">Each book has a calendar that is used when you depreciate fixed assets.</span></span> <span data-ttu-id="9fc79-130">Boken använder redovisningskalendern som standard om du inte anger en kalender för boken.</span><span class="sxs-lookup"><span data-stu-id="9fc79-130">By default, if you don't indicate a calendar on the book, the book uses the ledger fiscal calendar.</span></span> <span data-ttu-id="9fc79-131">Du måste välja en räkenskapskalender för en bok när räkenskapsbokens associerade avskrivningsprofil använder ett räkenskapsår.</span><span class="sxs-lookup"><span data-stu-id="9fc79-131">You must select a fiscal calendar for a book when the depreciation profile that is associated with the book uses a fiscal depreciation year.</span></span> 

<span data-ttu-id="9fc79-132">Du kan skapa delade kalendrar genom att använda sidan **Räkenskapskalendrar** i redovisningen.</span><span class="sxs-lookup"><span data-stu-id="9fc79-132">You can create shared calendars by using the **Fiscal calendars** page in General ledger.</span></span>

<span data-ttu-id="9fc79-133">Mer information finns i [Avskrivningsmetoder och avskrivningspraxis](depreciation-methods-conventions.md).</span><span class="sxs-lookup"><span data-stu-id="9fc79-133">For more information, see [Depreciation methods and conventions](depreciation-methods-conventions.md).</span></span>





[!INCLUDE[footer-include](../../includes/footer-banner.md)]