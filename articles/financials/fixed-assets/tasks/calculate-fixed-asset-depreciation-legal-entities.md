--- 
title: "Beräkna avskrivning av anläggningstillgången över juridiska personer"
description: "Den här proceduren visar hur du ställer in och kör avskrivningsprocessen för flera juridiska personer."
author: saraschi2
manager: AnnBe
ms.date: 11/02/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: d804480167414cd038f8229db312dc9c52d131f8
ms.openlocfilehash: 4c45da124136b7fecb916d2ff9098c8ffeff6cb1
ms.contentlocale: sv-se
ms.lasthandoff: 11/02/2017

---
# <a name="calculate-fixed-asset-depreciation-across-legal-entities"></a><span data-ttu-id="3e934-103">Beräkna avskrivning av anläggningstillgången över juridiska personer</span><span class="sxs-lookup"><span data-stu-id="3e934-103">Calculate fixed asset depreciation across legal entities</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="3e934-104">Avskrivning av anläggningstillgångar kan köras över juridiska personer i ett enda steg.</span><span class="sxs-lookup"><span data-stu-id="3e934-104">Fixed asset depreciation can be run across legal entities in a single step.</span></span> <span data-ttu-id="3e934-105">Den här proceduren visar hur du ställer in och kör processen för flera juridiska personer.</span><span class="sxs-lookup"><span data-stu-id="3e934-105">This procedure shows you to how set up and run the process for multiple legal entities.</span></span> <span data-ttu-id="3e934-106">Den använder rollen Revisor.</span><span class="sxs-lookup"><span data-stu-id="3e934-106">It uses the accountant role.</span></span>  

<span data-ttu-id="3e934-107">I den här registreringen används demonstrationsföretaget USMF.</span><span class="sxs-lookup"><span data-stu-id="3e934-107">This recording uses the USMF demo company.</span></span>


<span data-ttu-id="3e934-108">Steg (16) Deluppgift: Ställ avskrivningsjournaler som körs mellan företag.</span><span class="sxs-lookup"><span data-stu-id="3e934-108">Steps (16) Sub-task: Set up cross company depreciation run journals.</span></span> 

1. <span data-ttu-id="3e934-109">Först måste du konfigurera journalerna som ska användas i avskrivningkörningar mellan företag i respektive juridisk person.</span><span class="sxs-lookup"><span data-stu-id="3e934-109">First, you must set up the journals to be used in the cross company depreciation run in each legal entity.</span></span> <span data-ttu-id="3e934-110">Gå till Anläggningstillgångar > Inställning > Parametrar för anläggningstillgångar.</span><span class="sxs-lookup"><span data-stu-id="3e934-110">Go to Fixed assets > Setup > Fixed assets parameters.</span></span> 
2. <span data-ttu-id="3e934-111">Expandera avsnittet Förslag på anläggningstillgång.</span><span class="sxs-lookup"><span data-stu-id="3e934-111">Expand the Fixed asset proposals section.</span></span> 
3. <span data-ttu-id="3e934-112">Skapa en post med journalnamnet som ska användas för varje bokföringsskikt hos den juridiska personen.</span><span class="sxs-lookup"><span data-stu-id="3e934-112">Create a record with the journal name to be used for each posting layer in the legal entity.</span></span> <span data-ttu-id="3e934-113">Om avskrivningsregler inte bokförs i redovisningen, bör inget bokföringsskikt väljas med tillhörande journal.</span><span class="sxs-lookup"><span data-stu-id="3e934-113">If books do not post to the general ledger, then the None posting layer should be selected with the associated journal.</span></span> <span data-ttu-id="3e934-114">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="3e934-114">Click Add.</span></span> 
4. <span data-ttu-id="3e934-115">Ange bokföringsskikt eller välj ett värde i bokföringsfältet.</span><span class="sxs-lookup"><span data-stu-id="3e934-115">In the Posting layer field, enter or select a value.</span></span> 
5. <span data-ttu-id="3e934-116">Ange eller välj ett värde i fältet Journal name.</span><span class="sxs-lookup"><span data-stu-id="3e934-116">In the Journal name field, enter or select a value.</span></span> 
6. <span data-ttu-id="3e934-117">Upprepa journalinställningen på sidan Parametrar för anläggningstillgångar i respektive juridisk person.</span><span class="sxs-lookup"><span data-stu-id="3e934-117">Repeat the journal setup on the Fixed asset parameters page in each legal entity.</span></span> 

<span data-ttu-id="3e934-118">Deluppgift: Beräkna avskrivning.</span><span class="sxs-lookup"><span data-stu-id="3e934-118">Sub-task: Calculate depreciation</span></span>

1. <span data-ttu-id="3e934-119">Använd sidan Skapa avskrivningsförslag för att påbörja din avskrivningskörning i juridiska personer.</span><span class="sxs-lookup"><span data-stu-id="3e934-119">Use the Create depreciation proposal page to start your depreciation run across legal entities.</span></span> <span data-ttu-id="3e934-120">Gå till Anläggningstillgångar > Journalposter > Skapa avskrivningsförslag.</span><span class="sxs-lookup"><span data-stu-id="3e934-120">Go to Fixed assets > Journal entries > Create depreciation proposal.</span></span> 
2. <span data-ttu-id="3e934-121">Ange bokföringsskikt eller välj ett värde i bokföringsfältet.</span><span class="sxs-lookup"><span data-stu-id="3e934-121">In the Posting layer field, enter or select a value.</span></span> 
3. <span data-ttu-id="3e934-122">Journalnamnet hämtas som standard från parametrar för anläggningstillgångar.</span><span class="sxs-lookup"><span data-stu-id="3e934-122">The journal name will default from the Fixed asset parameters.</span></span> <span data-ttu-id="3e934-123">Det kan ändras här för den aktuella juridiska personen.</span><span class="sxs-lookup"><span data-stu-id="3e934-123">It can be changed here for the current legal entity.</span></span> 
4. <span data-ttu-id="3e934-124">Ange ett datum i fältet Till datum.</span><span class="sxs-lookup"><span data-stu-id="3e934-124">In the To date field, enter a date.</span></span> 
5. <span data-ttu-id="3e934-125">Välj de juridiska personerna som ska inkluderas i avskrivningskörningen.</span><span class="sxs-lookup"><span data-stu-id="3e934-125">Select the legal entities to be included in the depreciation run.</span></span> <span data-ttu-id="3e934-126">Endast juridiska personer med journaler som är inställda för Förslag på anläggningstillgång på sidan Parametrar för anläggningstillgånga visas i listan.</span><span class="sxs-lookup"><span data-stu-id="3e934-126">Only legal entities with journals set up for Fixed asset proposals on the Fixed asset parameters page will be shown in the list.</span></span> 
6. <span data-ttu-id="3e934-127">När du har aktiverat det kommer alternativet Bokför journaler automatiskt att bokföra avskrivningsjournalerna när de skapas.</span><span class="sxs-lookup"><span data-stu-id="3e934-127">When enabled, the Post journals option will automatically post the depreciation journals when they are created.</span></span> <span data-ttu-id="3e934-128">När de inte är markerade kommer journalerna att skapas, men inte bokföras, så att du kan granska informationen innan du bokför.</span><span class="sxs-lookup"><span data-stu-id="3e934-128">When not selected, the journals will be created, but not posted, so you can review the details before posting.</span></span> <span data-ttu-id="3e934-129">Välj Ja i fältet Bokför journaler.</span><span class="sxs-lookup"><span data-stu-id="3e934-129">Select Yes in the Post journals field.</span></span> 
7. <span data-ttu-id="3e934-130">Filtrering av fält inkluderar alla anläggningstillgångar, grupper och böcker för de juridiska personerna som valts för denna avskrivning.</span><span class="sxs-lookup"><span data-stu-id="3e934-130">Filtering fields include all fixed assets, groups, and books for the legal entities selected for this depreciation run.</span></span> 
8. <span data-ttu-id="3e934-131">Alternativet Batchbearbetning aktiveras som standard.</span><span class="sxs-lookup"><span data-stu-id="3e934-131">The Batch processing option is enabled by default.</span></span> <span data-ttu-id="3e934-132">När detta alternativ är aktiverat körs skapande och bokföring av avskrivningjournal i bakgrunden.</span><span class="sxs-lookup"><span data-stu-id="3e934-132">When this option is enabled, the depreciation journal creation and posting will run in the background.</span></span> 
9. <span data-ttu-id="3e934-133">Kicka på Skapa journal.</span><span class="sxs-lookup"><span data-stu-id="3e934-133">Click Create journal.</span></span> 
10. <span data-ttu-id="3e934-134">Du måste visa avskrivningsjournalerna som skapades i respektive juridiska personer.</span><span class="sxs-lookup"><span data-stu-id="3e934-134">You must view the depreciation journals created in the respective legal entities.</span></span> <span data-ttu-id="3e934-135">Gå till Anläggningstillgångar > Journalposter > Journal för anläggningstillgångar.</span><span class="sxs-lookup"><span data-stu-id="3e934-135">Go to Fixed assets > Journal entries > Fixed assets journal.</span></span>

