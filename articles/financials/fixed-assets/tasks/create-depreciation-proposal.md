---
title: "Skapa avskrivningsförslag"
description: "Den här proceduren beskriver hur avskrivningsbatchförslag fungerar och förklarar hur man föreslår avskrivning för anläggningstillgångar."
author: abruer
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: LedgerJournalTable, LedgerJournalTransAsset
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0312b8cfadd45f8e59225e9daba78b9e216cff51
ms.openlocfilehash: d11554ee5f26ef5a85e799194d2f75757a31c254
ms.contentlocale: sv-se
ms.lasthandoff: 09/14/2018

---

# <a name="create-depreciation-proposal"></a><span data-ttu-id="9fce6-103">Skapa avskrivningsförslag</span><span class="sxs-lookup"><span data-stu-id="9fce6-103">Create depreciation proposal</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="9fce6-104">Den här proceduren beskriver hur avskrivningsbatchförslag fungerar och förklarar hur man föreslår avskrivning för anläggningstillgångar.</span><span class="sxs-lookup"><span data-stu-id="9fce6-104">This procedure describes how depreciation batch proposals work and explains how to propose depreciation for fixed assets.</span></span> <span data-ttu-id="9fce6-105">I denna uppgift används USMF-demonstrationföretaget och revisorrollen.</span><span class="sxs-lookup"><span data-stu-id="9fce6-105">This task uses the USMF demo company and the accountant role.</span></span>


## <a name="create-depreciation-proposal"></a><span data-ttu-id="9fce6-106">Skapa avskrivningsförslag</span><span class="sxs-lookup"><span data-stu-id="9fce6-106">Create depreciation proposal</span></span>
1. <span data-ttu-id="9fce6-107">Gå till Anläggningstillgångar > Journalposter > Skapa avskrivningsförslag.</span><span class="sxs-lookup"><span data-stu-id="9fce6-107">Go to Fixed assets > Journal entries > Create depreciation proposal.</span></span>
2. <span data-ttu-id="9fce6-108">I fältet Journalnamn, öppna sökningen genom att klicka på den nedrullningsbara knappen.</span><span class="sxs-lookup"><span data-stu-id="9fce6-108">In the Name of journal field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="9fce6-109">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="9fce6-109">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="9fce6-110">Ange ett datum i fältet Till datum.</span><span class="sxs-lookup"><span data-stu-id="9fce6-110">In the To date field, enter a date.</span></span>
    * <span data-ttu-id="9fce6-111">Markera alternativet Summera avskrivning för att summera månadsvisa avskrivningar till en journalrad.</span><span class="sxs-lookup"><span data-stu-id="9fce6-111">Select the Summarize depreciation option to summarize monthly depreciations into one journal line.</span></span>  
    * <span data-ttu-id="9fce6-112">Till exempel om värdet för Till-datum är 31 mars 2015 skapas följande beskrivning: ”avskrivning sedan 31 januari 31 2015”.</span><span class="sxs-lookup"><span data-stu-id="9fce6-112">For example, if the To date value is March 31, 2015, the following description is generated: “Depreciation since January 31, 2015.”</span></span> <span data-ttu-id="9fce6-113">Datumfältet på de föreslagna journalraderna ställs sedan in till 31:a mars 2015.</span><span class="sxs-lookup"><span data-stu-id="9fce6-113">The Date field on the proposed journal lines is then set to March 31, 2015.</span></span>  
    * <span data-ttu-id="9fce6-114">Avskrivningsförslaget kan filtreras per tillgång, tillgångsgrupp eller andra kriterier med hjälp av filteralternativet.</span><span class="sxs-lookup"><span data-stu-id="9fce6-114">The depreciation proposal can be filtered by asset, asset group, or other criteria using the Filter option.</span></span>  
    * <span data-ttu-id="9fce6-115">När du använder formuläret Skapa förvärvs- eller avskrivningsförslag för anläggningstillgångar, kan du ange avskrivning i batchar.</span><span class="sxs-lookup"><span data-stu-id="9fce6-115">When you use the Create acquisition or depreciation proposals for fixed assets form, you can propose depreciation in batches.</span></span> <span data-ttu-id="9fce6-116">Detta rekommenderas för större förslag som kräver mer systemresurser.</span><span class="sxs-lookup"><span data-stu-id="9fce6-116">This is recommended for larger proposals that will use more system resources.</span></span> <span data-ttu-id="9fce6-117">Om du väljer batchalternativet, kan du fortfarande använda slutföra andra uppgifter under den tidsperioden.</span><span class="sxs-lookup"><span data-stu-id="9fce6-117">If you select the batch option, you can still complete other tasks during that time.</span></span> <span data-ttu-id="9fce6-118">När du föreslår avskrivning på detta sätt, beräknas avskrivningen för värdemodeller för anläggningstillgångar.</span><span class="sxs-lookup"><span data-stu-id="9fce6-118">When you propose depreciation in this way, depreciation is calculated for value models for fixed assets.</span></span>  
5. <span data-ttu-id="9fce6-119">Kicka på Skapa journal.</span><span class="sxs-lookup"><span data-stu-id="9fce6-119">Click Create journal.</span></span>

## <a name="review-depreciation-entries"></a><span data-ttu-id="9fce6-120">Granska avskrivningposter</span><span class="sxs-lookup"><span data-stu-id="9fce6-120">Review depreciation entries</span></span>
1. <span data-ttu-id="9fce6-121">Gå till Anläggningstillgångar > Journalposter > Journal för anläggningstillgångar.</span><span class="sxs-lookup"><span data-stu-id="9fce6-121">Go to Fixed assets > Journal entries > Fixed assets journal.</span></span>
2. <span data-ttu-id="9fce6-122">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="9fce6-122">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="9fce6-123">Klicka på Rader.</span><span class="sxs-lookup"><span data-stu-id="9fce6-123">Click Lines.</span></span>
4. <span data-ttu-id="9fce6-124">Klicka på Bokför.</span><span class="sxs-lookup"><span data-stu-id="9fce6-124">Click Post.</span></span>


