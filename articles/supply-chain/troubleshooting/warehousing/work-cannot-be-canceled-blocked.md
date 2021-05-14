---
title: Arbetet kan inte avbrytas eftersom det är spärrat
description: Arbetet kan inte avbrytas eftersom det är spärrat
author: perlynne
ms.date: 04/15/2021
ms.topic: troubleshooting
ms.search.form: WHSWorkTable_WHSWorkCancel
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-05-15
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: a7ab4c7263947767164702fb7dd6da7573175253
ms.sourcegitcommit: 5f5afb46431e1abd8fb6e92e0189914b598dc7fd
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2021
ms.locfileid: "5924289"
---
# <a name="work-cant-be-canceled-because-its-blocked"></a><span data-ttu-id="2f589-103">Arbetet kan inte avbrytas eftersom det är spärrat</span><span class="sxs-lookup"><span data-stu-id="2f589-103">Work can't be canceled because it's blocked</span></span>

<span data-ttu-id="2f589-104">Felkod: WHSCancellationOfWorkBlockedByExecutingWave_ErrorMessage</span><span class="sxs-lookup"><span data-stu-id="2f589-104">Error code: WHSCancellationOfWorkBlockedByExecutingWave_ErrorMessage</span></span>

## <a name="symptoms"></a><span data-ttu-id="2f589-105">Symtom</span><span class="sxs-lookup"><span data-stu-id="2f589-105">Symptoms</span></span>

<span data-ttu-id="2f589-106">Systemet visar följande felmeddelande:</span><span class="sxs-lookup"><span data-stu-id="2f589-106">The system shows the following error message:</span></span>

> <span data-ttu-id="2f589-107">Arbete %1 kan inte avbrytas eftersom det spärrats på grund av orsakstyp %2.</span><span class="sxs-lookup"><span data-stu-id="2f589-107">Work %1 cannot be cancelled because it is blocked by reason type %2.</span></span> <span data-ttu-id="2f589-108">Arbetet måste frisättas innan det kan avbrytas.</span><span class="sxs-lookup"><span data-stu-id="2f589-108">The work must be unblocked before it can be cancelled.</span></span>

## <a name="cause"></a><span data-ttu-id="2f589-109">Orsak</span><span class="sxs-lookup"><span data-stu-id="2f589-109">Cause</span></span>

<span data-ttu-id="2f589-110">Arbetet har spärrats och kan inte avbrytas.</span><span class="sxs-lookup"><span data-stu-id="2f589-110">The work is blocked and can't be canceled.</span></span>

<span data-ttu-id="2f589-111">På sidan **Arbete**, på fliken **Allmänt**, är alternativet **Spärrat** inställt på *Ja*.</span><span class="sxs-lookup"><span data-stu-id="2f589-111">On the **Work** page, on the **General** tab, the **Blocked** option is set to *Yes*.</span></span> <span data-ttu-id="2f589-112">Denna inställning visar att arbetet är spärrat.</span><span class="sxs-lookup"><span data-stu-id="2f589-112">This setting indicates that the work is blocked.</span></span> <span data-ttu-id="2f589-113">Fliken **Spärrorsaker** anger varför arbetet spärrats.</span><span class="sxs-lookup"><span data-stu-id="2f589-113">The **Blocking reasons** tab shows why the work was blocked.</span></span>

## <a name="resolution"></a><span data-ttu-id="2f589-114">Upplösning</span><span class="sxs-lookup"><span data-stu-id="2f589-114">Resolution</span></span>

<span data-ttu-id="2f589-115">För att frisätta arbetet väljer du **Spärrorsaker** och gör sedan på följande sätt:</span><span class="sxs-lookup"><span data-stu-id="2f589-115">To unblock the work, select the **Blocking reasons** tab, and then follow one of these steps:</span></span>

- <span data-ttu-id="2f589-116">Om fältet **Orsak till arbetsspärr** har ställts in på *Odefinierad orsak*: I åtgärdsfältet, på fliken **Arbete** i gruppen **Arbete**, väljer du **Frisätt arbete**.</span><span class="sxs-lookup"><span data-stu-id="2f589-116">If the **Work blocking reason** field is set to *Undefined reason*: On the Action Pane, on the **Work** tab, in the **Work** group, select **Unblock work**.</span></span>
- <span data-ttu-id="2f589-117">Om fältet **Orsak till arbetsspärr** är inställt på *Bearbetning av cykel*: I åtgärdsfältet, på fliken **Relaterad information** i gruppen **Relaterad information**, väljer du **Cykel**.</span><span class="sxs-lookup"><span data-stu-id="2f589-117">If the **Work blocking reason** field is set to *Processing wave*: On the Action Pane, on the **Related information** tab, in the **Related information** group, select **Wave**.</span></span> <span data-ttu-id="2f589-118">På sidan **Cykler** väljer du sedan i åtgärdsfältet, på fliken **Cykel**, i gruppen **Cykel**, **Rensa cykeldata**.</span><span class="sxs-lookup"><span data-stu-id="2f589-118">Then, on the **Waves** page, on the Action Pane, on the **Wave** tab, in the **Wave** group, select **Cleanup wave data**.</span></span>

## <a name="workaround"></a><span data-ttu-id="2f589-119">Lösning</span><span class="sxs-lookup"><span data-stu-id="2f589-119">Workaround</span></span>

<span data-ttu-id="2f589-120">Om de föregående stegen inte åtgärdat problemet kan du avbryta arbetet genom att följa stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="2f589-120">If the previous steps didn't fix the issue, you can cancel the work by following these steps.</span></span>

1. <span data-ttu-id="2f589-121">Gå till **Lagerstyrning \> Periodiska uppgifter \> Rensa upp \> Avbryt arbete**.</span><span class="sxs-lookup"><span data-stu-id="2f589-121">Go to **Warehouse management \> Periodic tasks \> Clean up \> Cancel work**.</span></span>
1. <span data-ttu-id="2f589-122">I fältet **Arbets-ID** anger du ID:t för det arbete du vill avbryta och som i nuläget har ett värde för **Arbetsstatus** som är antingen *Öppen*, *Pågår*, *Avbruten*, *Kombinerad* eller *Stängd*.</span><span class="sxs-lookup"><span data-stu-id="2f589-122">In the **Work ID** field, specify the ID of the work that you want to cancel, and that currently has a **Work status** value of *Open*, *In progress*, *Canceled*, *Combined*, or *Closed*.</span></span>
1. <span data-ttu-id="2f589-123">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="2f589-123">Select **OK**.</span></span>
1. <span data-ttu-id="2f589-124">Välj **Ja** för att bekräfta att du vill avbryta arbetet.</span><span class="sxs-lookup"><span data-stu-id="2f589-124">Select **Yes** to confirm that you want to cancel the work.</span></span>

<span data-ttu-id="2f589-125">Mer information finns i [Avbryt lagerarbete för undantagshantering](../../warehousing/cancel-warehouse-work.md).</span><span class="sxs-lookup"><span data-stu-id="2f589-125">For more information, see [Cancel warehouse work for exception handling](../../warehousing/cancel-warehouse-work.md).</span></span>
