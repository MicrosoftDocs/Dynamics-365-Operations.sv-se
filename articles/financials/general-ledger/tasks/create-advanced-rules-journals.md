--- 
title: "Skapa avancerade regler för journaler"
description: "Den här proceduren går igenom hur du kan skapa avancerade regler för journaler."
author: aprilolson
manager: AnnBe
ms.date: 11/10/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 7ecddd4ea17d917bab8985dcda0c91e6c8615d7c
ms.contentlocale: sv-se
ms.lasthandoff: 05/08/2018

---
# <a name="create-advanced-rules-for-journals"></a><span data-ttu-id="efa02-103">Skapa avancerade regler för journaler</span><span class="sxs-lookup"><span data-stu-id="efa02-103">Create advanced rules for journals</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="efa02-104">Den här proceduren går igenom hur du kan skapa avancerade regler för journaler.</span><span class="sxs-lookup"><span data-stu-id="efa02-104">This procedure steps through creating advanced rules for journals.</span></span> <span data-ttu-id="efa02-105">Detta inkluderar att ställa in begränsningar för journalkontroll och användarbokföring.</span><span class="sxs-lookup"><span data-stu-id="efa02-105">This includes setting up journal control and user posting restrictions.</span></span> <span data-ttu-id="efa02-106">I proceduren används demonstrationsföretag USMF.</span><span class="sxs-lookup"><span data-stu-id="efa02-106">This procedure uses the USMF demo data company.</span></span>


## <a name="set-up-journal-control"></a><span data-ttu-id="efa02-107">Ställ in journalkontroll</span><span class="sxs-lookup"><span data-stu-id="efa02-107">Set up journal control</span></span>
1. <span data-ttu-id="efa02-108">Gå till Redovisning > Journalkonfigurering > Journalnamn.</span><span class="sxs-lookup"><span data-stu-id="efa02-108">Go to General ledger > Journal setup > Journal names.</span></span>
2. <span data-ttu-id="efa02-109">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="efa02-109">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="efa02-110">Klicka på Journalkontroll.</span><span class="sxs-lookup"><span data-stu-id="efa02-110">Click Journal control.</span></span>
4. <span data-ttu-id="efa02-111">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="efa02-111">Click Add.</span></span>
5. <span data-ttu-id="efa02-112">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Företagskonton.</span><span class="sxs-lookup"><span data-stu-id="efa02-112">In the Company accounts field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="efa02-113">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="efa02-113">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="efa02-114">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="efa02-114">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="efa02-115">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="efa02-115">Click Add.</span></span>
9. <span data-ttu-id="efa02-116">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Kontostruktur.</span><span class="sxs-lookup"><span data-stu-id="efa02-116">In the Account structure field, click the drop-down button to open the lookup.</span></span>
10. <span data-ttu-id="efa02-117">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="efa02-117">In the list, find and select the desired record.</span></span>
11. <span data-ttu-id="efa02-118">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="efa02-118">In the list, click the link in the selected row.</span></span>
12. <span data-ttu-id="efa02-119">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Segment.</span><span class="sxs-lookup"><span data-stu-id="efa02-119">In the Segment field, click the drop-down button to open the lookup.</span></span>
13. <span data-ttu-id="efa02-120">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="efa02-120">In the list, click the link in the selected row.</span></span>
14. <span data-ttu-id="efa02-121">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Från-värde.</span><span class="sxs-lookup"><span data-stu-id="efa02-121">In the From value field, click the drop-down button to open the lookup.</span></span>
15. <span data-ttu-id="efa02-122">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="efa02-122">In the list, find and select the desired record.</span></span>
16. <span data-ttu-id="efa02-123">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="efa02-123">In the list, click the link in the selected row.</span></span>
17. <span data-ttu-id="efa02-124">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Till-värde.</span><span class="sxs-lookup"><span data-stu-id="efa02-124">In the To value field, click the drop-down button to open the lookup.</span></span>
18. <span data-ttu-id="efa02-125">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="efa02-125">In the list, find and select the desired record.</span></span>
19. <span data-ttu-id="efa02-126">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="efa02-126">In the list, click the link in the selected row.</span></span>

## <a name="set-up-posting-restrictions"></a><span data-ttu-id="efa02-127">Konfigurera bokföringsrestriktioner</span><span class="sxs-lookup"><span data-stu-id="efa02-127">Set up posting restrictions</span></span>
1. <span data-ttu-id="efa02-128">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="efa02-128">Close the page.</span></span>
2. <span data-ttu-id="efa02-129">Klicka på Bokföringsrestriktioner.</span><span class="sxs-lookup"><span data-stu-id="efa02-129">Click Posting restrictions.</span></span>
3. <span data-ttu-id="efa02-130">Välj Efter användargrupp i Hur vill du ställa in bokföringsrestriktioner.</span><span class="sxs-lookup"><span data-stu-id="efa02-130">In the How do you want to set up posting restrictions, select By user group.</span></span>
4. <span data-ttu-id="efa02-131">Markera gruppen du vill tillåta bokföring för när det gäller journalnamnet i trädet.</span><span class="sxs-lookup"><span data-stu-id="efa02-131">In the tree, check 'the group that you want to allow posting for this journal name.'.</span></span>
5. <span data-ttu-id="efa02-132">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="efa02-132">Click OK.</span></span>


