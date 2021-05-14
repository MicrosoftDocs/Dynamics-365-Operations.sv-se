---
title: Arbetet fortsatt spärrat
description: Arbetet fortsatt spärrat
author: perlynne
ms.date: 04/15/2021
ms.topic: troubleshooting
ms.search.form: WHSWorkTableListPage_WHSWorkUnblocking
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-05-15
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: f85364d1ecfadc36b26c3395ab4402d3cb3b1603
ms.sourcegitcommit: 5f5afb46431e1abd8fb6e92e0189914b598dc7fd
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2021
ms.locfileid: "5924140"
---
# <a name="work-remains-blocked"></a><span data-ttu-id="c6cb5-103">Arbetet fortsatt spärrat</span><span class="sxs-lookup"><span data-stu-id="c6cb5-103">Work remains blocked</span></span>

<span data-ttu-id="c6cb5-104">Felkod: WHSWorkBlockingExecutingWaveReason_ErrorMessage</span><span class="sxs-lookup"><span data-stu-id="c6cb5-104">Error code: WHSWorkBlockingExecutingWaveReason_ErrorMessage</span></span>

## <a name="symptoms"></a><span data-ttu-id="c6cb5-105">Symtom</span><span class="sxs-lookup"><span data-stu-id="c6cb5-105">Symptoms</span></span>

<span data-ttu-id="c6cb5-106">Systemet visar följande felmeddelande:</span><span class="sxs-lookup"><span data-stu-id="c6cb5-106">The system shows the following error message:</span></span>

> <span data-ttu-id="c6cb5-107">Arbetet %1 förblir spärrat eftersom den relaterade påfyllnaden %2 har statusvärdet %3.</span><span class="sxs-lookup"><span data-stu-id="c6cb5-107">Work %1 remains blocked because the related wave %2 has status %3.</span></span>

## <a name="cause"></a><span data-ttu-id="c6cb5-108">Orsak</span><span class="sxs-lookup"><span data-stu-id="c6cb5-108">Cause</span></span>

<span data-ttu-id="c6cb5-109">Arbetet bearbetas just nu i en cykel och kan inte frisättas, enligt något av följande villkor:</span><span class="sxs-lookup"><span data-stu-id="c6cb5-109">The work is currently being processed on a wave and can't be unblocked, as indicated by one of the following conditions:</span></span>

- <span data-ttu-id="c6cb5-110">På fliken **Spärrningsorsaker** anges fältet **Orsak till arbetsspärr** för en eller flera rader som *Bearbetning av cykel*.</span><span class="sxs-lookup"><span data-stu-id="c6cb5-110">On the **Blocking reasons** tab, the **Work blocking reason** field for one or more lines is set to *Processing wave*.</span></span>
- <span data-ttu-id="c6cb5-111">När du väljer **Cykel** i gruppen **Relaterad information** på fliken **Relaterad information** på åtgärdssidan anges fältet **Cykelstatus** som *Behandlas*.</span><span class="sxs-lookup"><span data-stu-id="c6cb5-111">When you select **Wave** in the **Related information** group on the **Related information** tab of the Action Pane, the **Wave status** field is set to *Processing*.</span></span>

## <a name="resolution"></a><span data-ttu-id="c6cb5-112">Upplösning</span><span class="sxs-lookup"><span data-stu-id="c6cb5-112">Resolution</span></span>

<span data-ttu-id="c6cb5-113">I åtgärdsfönstret, på fliken **Relaterad information**, i gruppen **Relaterad information**, väljer du **Cykel**.</span><span class="sxs-lookup"><span data-stu-id="c6cb5-113">On the Action Pane, on the **Related information** tab, in the **Related information** group, select **Wave**.</span></span> <span data-ttu-id="c6cb5-114">På sidan **Cykler** väljer du sedan i åtgärdsfältet, på fliken **Cykel**, i gruppen **Cykel**, **Rensa cykeldata**.</span><span class="sxs-lookup"><span data-stu-id="c6cb5-114">Then, on the **Waves** page, on the Action Pane, on the **Wave** tab, in the **Wave** group, select **Cleanup wave data**.</span></span>

## <a name="workaround"></a><span data-ttu-id="c6cb5-115">Lösning</span><span class="sxs-lookup"><span data-stu-id="c6cb5-115">Workaround</span></span>

<span data-ttu-id="c6cb5-116">Om de föregående stegen inte åtgärdat problemet kan du avbryta arbetet genom att följa stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="c6cb5-116">If the previous steps didn't fix the issue, you can cancel the work by following these steps.</span></span>

1. <span data-ttu-id="c6cb5-117">Gå till **Lagerstyrning \> Periodiska uppgifter \> Rensa upp \> Avbryt arbete**.</span><span class="sxs-lookup"><span data-stu-id="c6cb5-117">Go to **Warehouse management \> Periodic tasks \> Clean up \> Cancel work**.</span></span>
1. <span data-ttu-id="c6cb5-118">I fältet **Arbets-ID** anger du ID:t för det arbete du vill avbryta och som i nuläget har ett värde för **Arbetsstatus** som är antingen *Öppen*, *Pågår*, *Avbruten*, *Kombinerad* eller *Stängd*.</span><span class="sxs-lookup"><span data-stu-id="c6cb5-118">In the **Work ID** field, specify the ID of the work that you want to cancel, and that currently has a **Work status** value of *Open*, *In progress*, *Canceled*, *Combined*, or *Closed*.</span></span>
1. <span data-ttu-id="c6cb5-119">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="c6cb5-119">Select **OK**.</span></span>
1. <span data-ttu-id="c6cb5-120">Välj **Ja** för att bekräfta att du vill avbryta arbetet.</span><span class="sxs-lookup"><span data-stu-id="c6cb5-120">Select **Yes** to confirm that you want to cancel the work.</span></span>

<span data-ttu-id="c6cb5-121">Mer information finns i [Avbryt lagerarbete för undantagshantering](../../warehousing/cancel-warehouse-work.md).</span><span class="sxs-lookup"><span data-stu-id="c6cb5-121">For more information, see [Cancel warehouse work for exception handling](../../warehousing/cancel-warehouse-work.md).</span></span>
