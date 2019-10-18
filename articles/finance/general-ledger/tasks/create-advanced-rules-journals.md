---
title: Skapa avancerade regler för journaler
description: Den här proceduren går igenom hur du kan skapa avancerade regler för journaler.
author: aprilolson
manager: AnnBe
ms.date: 08/08/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalSetup, LedgerJournalControl, CompanyLookup, LedgerJournalPostControl
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 3eb34ac419aeab3663a8931d022abf7bcbfddd37
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/27/2019
ms.locfileid: "2186243"
---
# <a name="create-advanced-rules-for-journals"></a><span data-ttu-id="d4f72-103">Skapa avancerade regler för journaler</span><span class="sxs-lookup"><span data-stu-id="d4f72-103">Create advanced rules for journals</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="d4f72-104">Den här proceduren går igenom hur du kan skapa avancerade regler för journaler.</span><span class="sxs-lookup"><span data-stu-id="d4f72-104">This procedure steps through creating advanced rules for journals.</span></span> <span data-ttu-id="d4f72-105">Detta inkluderar att ställa in begränsningar för journalkontroll och användarbokföring.</span><span class="sxs-lookup"><span data-stu-id="d4f72-105">This includes setting up journal control and user posting restrictions.</span></span> <span data-ttu-id="d4f72-106">I proceduren används demonstrationsföretag USMF.</span><span class="sxs-lookup"><span data-stu-id="d4f72-106">This procedure uses the USMF demo data company.</span></span>


## <a name="set-up-journal-control"></a><span data-ttu-id="d4f72-107">Ställ in journalkontroll</span><span class="sxs-lookup"><span data-stu-id="d4f72-107">Set up journal control</span></span>
1. <span data-ttu-id="d4f72-108">I **Navigeringsfönstret**, gå till **Moduler > Redovisning > Journalkonfiguration > Journalnamn**.</span><span class="sxs-lookup"><span data-stu-id="d4f72-108">In the **Navigation pane**, go to **Modules > General ledger > Journal setup > Journal names**.</span></span>
2. <span data-ttu-id="d4f72-109">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="d4f72-109">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="d4f72-110">Klicka på **Journalkontroll** i **Åtgärdsfönstret**.</span><span class="sxs-lookup"><span data-stu-id="d4f72-110">On the **Action pane**, click **Journal control**.</span></span>
4. <span data-ttu-id="d4f72-111">På snabbfliken **Vilka kontotyper kan bokföras**, klicka på **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="d4f72-111">In the **Which account types can be posted** fastTab, click **Add**.</span></span>
5. <span data-ttu-id="d4f72-112">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet **Företagskonton**.</span><span class="sxs-lookup"><span data-stu-id="d4f72-112">In the **Company accounts** field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="d4f72-113">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="d4f72-113">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="d4f72-114">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="d4f72-114">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="d4f72-115">På snabbfliken **Vilka segmentvärden är giltiga för den här journalen** klicka på **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="d4f72-115">In the **Which segment values are valid for this journal** fastTab, click **Add**.</span></span>
9. <span data-ttu-id="d4f72-116">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet **Kontostruktur**.</span><span class="sxs-lookup"><span data-stu-id="d4f72-116">In the **Account structure** field, click the drop-down button to open the lookup.</span></span>
10. <span data-ttu-id="d4f72-117">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="d4f72-117">In the list, find and select the desired record.</span></span>
11. <span data-ttu-id="d4f72-118">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="d4f72-118">In the list, click the link in the selected row.</span></span>
12. <span data-ttu-id="d4f72-119">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet **Segment**.</span><span class="sxs-lookup"><span data-stu-id="d4f72-119">In the **Segment** field, click the drop-down button to open the lookup.</span></span>
13. <span data-ttu-id="d4f72-120">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="d4f72-120">In the list, click the link in the selected row.</span></span>
14. <span data-ttu-id="d4f72-121">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet **Från-värde**.</span><span class="sxs-lookup"><span data-stu-id="d4f72-121">In the **From value** field, click the drop-down button to open the lookup.</span></span>
15. <span data-ttu-id="d4f72-122">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="d4f72-122">In the list, find and select the desired record.</span></span>
16. <span data-ttu-id="d4f72-123">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="d4f72-123">In the list, click the link in the selected row.</span></span>
17. <span data-ttu-id="d4f72-124">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet **Till-värde**.</span><span class="sxs-lookup"><span data-stu-id="d4f72-124">In the **To value** field, click the drop-down button to open the lookup.</span></span>
18. <span data-ttu-id="d4f72-125">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="d4f72-125">In the list, find and select the desired record.</span></span>
19. <span data-ttu-id="d4f72-126">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="d4f72-126">In the list, click the link in the selected row.</span></span>

## <a name="set-up-posting-restrictions"></a><span data-ttu-id="d4f72-127">Konfigurera bokföringsrestriktioner</span><span class="sxs-lookup"><span data-stu-id="d4f72-127">Set up posting restrictions</span></span>
1. <span data-ttu-id="d4f72-128">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="d4f72-128">Close the page.</span></span>
2. <span data-ttu-id="d4f72-129">Klicka på **Bokföringsrestriktioner**.</span><span class="sxs-lookup"><span data-stu-id="d4f72-129">Click **Posting restrictions**.</span></span>
3. <span data-ttu-id="d4f72-130">Välj Efter användargrupp i fältet **Hur vill du ställa in bokföringsrestriktioner**.</span><span class="sxs-lookup"><span data-stu-id="d4f72-130">In the **How do you want to set up posting restrictions** field, select 'By user group'.</span></span>
4. <span data-ttu-id="d4f72-131">Markera gruppen du vill tillåta bokföring för när det gäller journalnamnet i trädet.</span><span class="sxs-lookup"><span data-stu-id="d4f72-131">In the tree, check 'the group that you want to allow posting for this journal name.'.</span></span>
5. <span data-ttu-id="d4f72-132">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="d4f72-132">Click **OK**.</span></span>

