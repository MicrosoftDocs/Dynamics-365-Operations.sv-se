---
title: Beräkna avskrivning av anläggningstillgången över juridiska personer
description: Avskrivning av anläggningstillgångar kan köras över juridiska personer i ett enda steg.
author: saraschi2
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: AssetParameters, AssetProposalDepreciation, DefaultDashboard, LedgerJournalTable
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 85a1e71967fb126be29a76a8a29ea5e4ae2b2199
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5818474"
---
# <a name="calculate-fixed-asset-depreciation-across-legal-entities"></a><span data-ttu-id="7718d-103">Beräkna avskrivning av anläggningstillgången över juridiska personer</span><span class="sxs-lookup"><span data-stu-id="7718d-103">Calculate fixed asset depreciation across legal entities</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="7718d-104">Avskrivning av anläggningstillgångar kan köras över juridiska personer i ett enda steg.</span><span class="sxs-lookup"><span data-stu-id="7718d-104">Fixed asset depreciation can be run across legal entities in a single step.</span></span> <span data-ttu-id="7718d-105">Den här proceduren visar hur du ställer in och kör processen för flera juridiska personer.</span><span class="sxs-lookup"><span data-stu-id="7718d-105">This procedure shows you to how set up and run the process for multiple legal entities.</span></span> <span data-ttu-id="7718d-106">Här används revisorrollen och demonstrationsdata för den juridiska USMF-personen.</span><span class="sxs-lookup"><span data-stu-id="7718d-106">It uses the accountant role and demo data for the USMF legal entity.</span></span>


## <a name="set-up-cross-company-depreciation-run-journals"></a><span data-ttu-id="7718d-107">Ställ avskrivningsjournaler som körs mellan företag.</span><span class="sxs-lookup"><span data-stu-id="7718d-107">Set up cross company depreciation run journals</span></span>
1. <span data-ttu-id="7718d-108">Gå till Anläggningstillgångar > Inställning > Parametrar för anläggningstillgångar.</span><span class="sxs-lookup"><span data-stu-id="7718d-108">Go to Fixed assets > Setup > Fixed assets parameters.</span></span>
2. <span data-ttu-id="7718d-109">Expandera avsnittet Förslag på anläggningstillgång.</span><span class="sxs-lookup"><span data-stu-id="7718d-109">Expand the Fixed asset proposals section.</span></span>
3. <span data-ttu-id="7718d-110">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="7718d-110">Click Add.</span></span>
4. <span data-ttu-id="7718d-111">Ange bokföringsskikt eller välj ett värde i bokföringsfältet.</span><span class="sxs-lookup"><span data-stu-id="7718d-111">In the Posting layer field, enter or select a value.</span></span>
5. <span data-ttu-id="7718d-112">Ange eller välj ett värde i fältet Journal name.</span><span class="sxs-lookup"><span data-stu-id="7718d-112">In the Journal name field, enter or select a value.</span></span>
    * <span data-ttu-id="7718d-113">Upprepa journalinställningen på sidan Parametrar för anläggningstillgångar i respektive juridisk person.</span><span class="sxs-lookup"><span data-stu-id="7718d-113">Repeat the journal setup on the Fixed asset parameters page in each legal entity.</span></span>  

## <a name="depreciation-run"></a><span data-ttu-id="7718d-114">Avskrivningskörning</span><span class="sxs-lookup"><span data-stu-id="7718d-114">Depreciation run</span></span>
1. <span data-ttu-id="7718d-115">Gå till Anläggningstillgångar > Journalposter > Skapa avskrivningsförslag.</span><span class="sxs-lookup"><span data-stu-id="7718d-115">Go to Fixed assets > Journal entries > Create depreciation proposal.</span></span>
2. <span data-ttu-id="7718d-116">Ange bokföringsskikt eller välj ett värde i bokföringsfältet.</span><span class="sxs-lookup"><span data-stu-id="7718d-116">In the Posting layer field, enter or select a value.</span></span>
    * <span data-ttu-id="7718d-117">Journalnamnet hämtas som standard från parametrar för anläggningstillgångar.</span><span class="sxs-lookup"><span data-stu-id="7718d-117">The journal name will default from the Fixed asset parameters.</span></span> <span data-ttu-id="7718d-118">Det kan ändras här för den aktuella juridiska personen.</span><span class="sxs-lookup"><span data-stu-id="7718d-118">It can be changed here for the current legal entity.</span></span>  
3. <span data-ttu-id="7718d-119">Ange ett datum i fältet Till datum.</span><span class="sxs-lookup"><span data-stu-id="7718d-119">In the To date field, enter a date.</span></span>
    * <span data-ttu-id="7718d-120">Välj de juridiska personerna som ska inkluderas i avskrivningskörningen.</span><span class="sxs-lookup"><span data-stu-id="7718d-120">Select the legal entities to be included in the depreciation run.</span></span>  
    * <span data-ttu-id="7718d-121">Endast juridiska personer med journaler som är inställda för Förslag på anläggningstillgång på sidan Parametrar för anläggningstillgånga visas i listan.</span><span class="sxs-lookup"><span data-stu-id="7718d-121">Only legal entities with journals set up for Fixed asset proposals on the Fixed asset parameters page will be shown in the list.</span></span>  
4. <span data-ttu-id="7718d-122">Välj Ja i fältet Bokför journaler.</span><span class="sxs-lookup"><span data-stu-id="7718d-122">Select Yes in the Post journals field.</span></span>
    * <span data-ttu-id="7718d-123">Filtrering av fält inkluderar alla anläggningstillgångar, grupper och böcker för de juridiska personerna som valts för denna avskrivning.</span><span class="sxs-lookup"><span data-stu-id="7718d-123">Filtering fields include all fixed assets, groups, and books for the legal entities selected for this depreciation run.</span></span>  
    * <span data-ttu-id="7718d-124">Alternativet Batchbearbetning aktiveras som standard.</span><span class="sxs-lookup"><span data-stu-id="7718d-124">The Batch processing option is enabled by default.</span></span> <span data-ttu-id="7718d-125">När detta alternativ är aktiverat körs skapande och bokföring av avskrivningjournal i bakgrunden.</span><span class="sxs-lookup"><span data-stu-id="7718d-125">When this option is enabled, the depreciation journal creation and posting will run in the background.</span></span>  
5. <span data-ttu-id="7718d-126">Kicka på Skapa journal.</span><span class="sxs-lookup"><span data-stu-id="7718d-126">Click Create journal.</span></span>
6. <span data-ttu-id="7718d-127">Gå till Anläggningstillgångar > Journalposter > Journal för anläggningstillgångar.</span><span class="sxs-lookup"><span data-stu-id="7718d-127">Go to Fixed assets > Journal entries > Fixed assets journal.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]