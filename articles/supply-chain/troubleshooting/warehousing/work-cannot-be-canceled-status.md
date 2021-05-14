---
title: Arbete kan inte avbrytas på grund av dess status
description: Arbete kan inte avbrytas på grund av dess status
author: perlynne
ms.date: 04/15/2021
ms.topic: troubleshooting
ms.search.form: WHSWorkTable_WHSWorkCancel, WHSWorkTableListPage_WHSWorkCancel
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-05-15
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 60b4da44ca5e6790302e0797640317cef8493db7
ms.sourcegitcommit: 5f5afb46431e1abd8fb6e92e0189914b598dc7fd
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2021
ms.locfileid: "5924265"
---
# <a name="work-cant-be-canceled-because-of-its-status"></a><span data-ttu-id="ec9b8-103">Arbete kan inte avbrytas på grund av dess status</span><span class="sxs-lookup"><span data-stu-id="ec9b8-103">Work can't be canceled because of its status</span></span>

<span data-ttu-id="ec9b8-104">Felkod: WAX2190</span><span class="sxs-lookup"><span data-stu-id="ec9b8-104">Error code: WAX2190</span></span>

## <a name="symptoms"></a><span data-ttu-id="ec9b8-105">Symtom</span><span class="sxs-lookup"><span data-stu-id="ec9b8-105">Symptoms</span></span>

<span data-ttu-id="ec9b8-106">Systemet visar följande felmeddelande:</span><span class="sxs-lookup"><span data-stu-id="ec9b8-106">The system shows the following error message:</span></span>

> <span data-ttu-id="ec9b8-107">Det går inte att annullera arbetet %1 eftersom det har status %2.</span><span class="sxs-lookup"><span data-stu-id="ec9b8-107">You cannot cancel work %1 because it has a status of %2.</span></span>

## <a name="cause"></a><span data-ttu-id="ec9b8-108">Orsak</span><span class="sxs-lookup"><span data-stu-id="ec9b8-108">Cause</span></span>

<span data-ttu-id="ec9b8-109">Arbetet kan inte avbrytas i sitt aktuella tillstånd.</span><span class="sxs-lookup"><span data-stu-id="ec9b8-109">The work can't be canceled in its current state.</span></span>

<span data-ttu-id="ec9b8-110">Arbetsrubriken eller arbetsraderna har inte det förväntade värdet **Arbetsstatus**.</span><span class="sxs-lookup"><span data-stu-id="ec9b8-110">The work header or work lines don't have the expected **Work status** value.</span></span> <span data-ttu-id="ec9b8-111">Fältet **Arbetsstatus** i arbetsrubriken är inte inställt på *Öppen* eller *Pågår*.</span><span class="sxs-lookup"><span data-stu-id="ec9b8-111">The **Work status** field on the work header isn't set to *Open* or *In progress*.</span></span>

## <a name="resolution"></a><span data-ttu-id="ec9b8-112">Upplösning</span><span class="sxs-lookup"><span data-stu-id="ec9b8-112">Resolution</span></span>

<span data-ttu-id="ec9b8-113">Om du vill avbryta arbetet följer du stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="ec9b8-113">To cancel the work, follow these steps.</span></span>

1. <span data-ttu-id="ec9b8-114">Gå till **Lagerstyrning \> Periodiska uppgifter \> Rensa upp \> Avbryt arbete**.</span><span class="sxs-lookup"><span data-stu-id="ec9b8-114">Go to **Warehouse management \> Periodic tasks \> Clean up \> Cancel work**.</span></span>
1. <span data-ttu-id="ec9b8-115">I fältet **Arbets-ID** anger du ID-numret för det arbete som du vil avbryta.</span><span class="sxs-lookup"><span data-stu-id="ec9b8-115">In the **Work ID** field, specify the ID of the work that you want to cancel.</span></span>
1. <span data-ttu-id="ec9b8-116">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="ec9b8-116">Select **OK**.</span></span>
1. <span data-ttu-id="ec9b8-117">Välj **Ja** för att bekräfta att du vill avbryta arbetet.</span><span class="sxs-lookup"><span data-stu-id="ec9b8-117">Select **Yes** to confirm that you want to cancel the work.</span></span>

<span data-ttu-id="ec9b8-118">Mer information finns i [Avbryt lagerarbete för undantagshantering](../../warehousing/cancel-warehouse-work.md).</span><span class="sxs-lookup"><span data-stu-id="ec9b8-118">For more information, see [Cancel warehouse work for exception handling](../../warehousing/cancel-warehouse-work.md).</span></span>
