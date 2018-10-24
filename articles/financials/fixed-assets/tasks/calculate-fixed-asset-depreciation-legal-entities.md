--- 
title: "Beräkna avskrivning av anläggningstillgången över juridiska personer"
description: "Avskrivning av anläggningstillgångar kan köras över juridiska personer i ett enda steg."
author: saraschi2
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: AssetParameters, AssetProposalDepreciation, DefaultDashboard, LedgerJournalTable
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0312b8cfadd45f8e59225e9daba78b9e216cff51
ms.openlocfilehash: b2575354af322827972ffa650e9c732170c5a6eb
ms.contentlocale: sv-se
ms.lasthandoff: 09/14/2018

---
# <a name="calculate-fixed-asset-depreciation-across-legal-entities"></a><span data-ttu-id="99044-103">Beräkna avskrivning av anläggningstillgången över juridiska personer</span><span class="sxs-lookup"><span data-stu-id="99044-103">Calculate fixed asset depreciation across legal entities</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="99044-104">Avskrivning av anläggningstillgångar kan köras över juridiska personer i ett enda steg.</span><span class="sxs-lookup"><span data-stu-id="99044-104">Fixed asset depreciation can be run across legal entities in a single step.</span></span> <span data-ttu-id="99044-105">Den här proceduren visar hur du ställer in och kör processen för flera juridiska personer.</span><span class="sxs-lookup"><span data-stu-id="99044-105">This procedure shows you to how set up and run the process for multiple legal entities.</span></span> <span data-ttu-id="99044-106">Här används revisorrollen och demonstrationsdata för den juridiska USMF-personen.</span><span class="sxs-lookup"><span data-stu-id="99044-106">It uses the accountant role and demo data for the USMF legal entity.</span></span>


## <a name="set-up-cross-company-depreciation-run-journals"></a><span data-ttu-id="99044-107">Ställ avskrivningsjournaler som körs mellan företag.</span><span class="sxs-lookup"><span data-stu-id="99044-107">Set up cross company depreciation run journals</span></span>
1. <span data-ttu-id="99044-108">Gå till Anläggningstillgångar > Inställning > Parametrar för anläggningstillgångar.</span><span class="sxs-lookup"><span data-stu-id="99044-108">Go to Fixed assets > Setup > Fixed assets parameters.</span></span>
2. <span data-ttu-id="99044-109">Expandera avsnittet Förslag på anläggningstillgång.</span><span class="sxs-lookup"><span data-stu-id="99044-109">Expand the Fixed asset proposals section.</span></span>
3. <span data-ttu-id="99044-110">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="99044-110">Click Add.</span></span>
4. <span data-ttu-id="99044-111">Ange bokföringsskikt eller välj ett värde i bokföringsfältet.</span><span class="sxs-lookup"><span data-stu-id="99044-111">In the Posting layer field, enter or select a value.</span></span>
5. <span data-ttu-id="99044-112">Ange eller välj ett värde i fältet Journal name.</span><span class="sxs-lookup"><span data-stu-id="99044-112">In the Journal name field, enter or select a value.</span></span>
    * <span data-ttu-id="99044-113">Upprepa journalinställningen på sidan Parametrar för anläggningstillgångar i respektive juridisk person.</span><span class="sxs-lookup"><span data-stu-id="99044-113">Repeat the journal setup on the Fixed asset parameters page in each legal entity.</span></span>  

## <a name="depreciation-run"></a><span data-ttu-id="99044-114">Avskrivningskörning</span><span class="sxs-lookup"><span data-stu-id="99044-114">Depreciation run</span></span>
1. <span data-ttu-id="99044-115">Gå till Anläggningstillgångar > Journalposter > Skapa avskrivningsförslag.</span><span class="sxs-lookup"><span data-stu-id="99044-115">Go to Fixed assets > Journal entries > Create depreciation proposal.</span></span>
2. <span data-ttu-id="99044-116">Ange bokföringsskikt eller välj ett värde i bokföringsfältet.</span><span class="sxs-lookup"><span data-stu-id="99044-116">In the Posting layer field, enter or select a value.</span></span>
    * <span data-ttu-id="99044-117">Journalnamnet hämtas som standard från parametrar för anläggningstillgångar.</span><span class="sxs-lookup"><span data-stu-id="99044-117">The journal name will default from the Fixed asset parameters.</span></span> <span data-ttu-id="99044-118">Det kan ändras här för den aktuella juridiska personen.</span><span class="sxs-lookup"><span data-stu-id="99044-118">It can be changed here for the current legal entity.</span></span>  
3. <span data-ttu-id="99044-119">Ange ett datum i fältet Till datum.</span><span class="sxs-lookup"><span data-stu-id="99044-119">In the To date field, enter a date.</span></span>
    * <span data-ttu-id="99044-120">Välj de juridiska personerna som ska inkluderas i avskrivningskörningen.</span><span class="sxs-lookup"><span data-stu-id="99044-120">Select the legal entities to be included in the depreciation run.</span></span>  
    * <span data-ttu-id="99044-121">Endast juridiska personer med journaler som är inställda för Förslag på anläggningstillgång på sidan Parametrar för anläggningstillgånga visas i listan.</span><span class="sxs-lookup"><span data-stu-id="99044-121">Only legal entities with journals set up for Fixed asset proposals on the Fixed asset parameters page will be shown in the list.</span></span>  
4. <span data-ttu-id="99044-122">Välj Ja i fältet Bokför journaler.</span><span class="sxs-lookup"><span data-stu-id="99044-122">Select Yes in the Post journals field.</span></span>
    * <span data-ttu-id="99044-123">Filtrering av fält inkluderar alla anläggningstillgångar, grupper och böcker för de juridiska personerna som valts för denna avskrivning.</span><span class="sxs-lookup"><span data-stu-id="99044-123">Filtering fields include all fixed assets, groups, and books for the legal entities selected for this depreciation run.</span></span>  
    * <span data-ttu-id="99044-124">Alternativet Batchbearbetning aktiveras som standard.</span><span class="sxs-lookup"><span data-stu-id="99044-124">The Batch processing option is enabled by default.</span></span> <span data-ttu-id="99044-125">När detta alternativ är aktiverat körs skapande och bokföring av avskrivningjournal i bakgrunden.</span><span class="sxs-lookup"><span data-stu-id="99044-125">When this option is enabled, the depreciation journal creation and posting will run in the background.</span></span>  
5. <span data-ttu-id="99044-126">Kicka på Skapa journal.</span><span class="sxs-lookup"><span data-stu-id="99044-126">Click Create journal.</span></span>
6. <span data-ttu-id="99044-127">Gå till Anläggningstillgångar > Journalposter > Journal för anläggningstillgångar.</span><span class="sxs-lookup"><span data-stu-id="99044-127">Go to Fixed assets > Journal entries > Fixed assets journal.</span></span>


