---
title: Den senast stängda arbetsraden måste ha värdet Placera
description: Den senast stängda arbetsraden måste ha värdet Placera
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
ms.openlocfilehash: a5b78154b51252b3ac96ba28c254e823caf87019
ms.sourcegitcommit: 5f5afb46431e1abd8fb6e92e0189914b598dc7fd
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2021
ms.locfileid: "5924385"
---
# <a name="the-last-closed-work-line-must-be-a-put"></a><span data-ttu-id="555d5-103">Den senast stängda arbetsraden måste ha värdet Placera</span><span class="sxs-lookup"><span data-stu-id="555d5-103">The last closed work line must be a put</span></span>

<span data-ttu-id="555d5-104">Felkod: WAX1285</span><span class="sxs-lookup"><span data-stu-id="555d5-104">Error code: WAX1285</span></span>

## <a name="symptoms"></a><span data-ttu-id="555d5-105">Symtom</span><span class="sxs-lookup"><span data-stu-id="555d5-105">Symptoms</span></span>

<span data-ttu-id="555d5-106">Systemet visar följande felmeddelande:</span><span class="sxs-lookup"><span data-stu-id="555d5-106">The system shows the following error message:</span></span>

> <span data-ttu-id="555d5-107">Den senast stängda arbetsraden måste ha värdet Placera.</span><span class="sxs-lookup"><span data-stu-id="555d5-107">The last closed work line must be a put.</span></span>

## <a name="cause"></a><span data-ttu-id="555d5-108">Orsak</span><span class="sxs-lookup"><span data-stu-id="555d5-108">Cause</span></span>

<span data-ttu-id="555d5-109">Arbetet kan inte avbrytas i sitt aktuella tillstånd.</span><span class="sxs-lookup"><span data-stu-id="555d5-109">The work can't be canceled in its current state.</span></span>

<span data-ttu-id="555d5-110">På den sista arbetsraden ställs fältet **Arbetsstatus** in på *Stängd*, men fältet **Arbetstyp** är inte satt som *Placera*.</span><span class="sxs-lookup"><span data-stu-id="555d5-110">On the last work line, the **Work status** field is set to *Closed*, but the **Work type** field isn't set to *Put*.</span></span>

## <a name="resolution"></a><span data-ttu-id="555d5-111">Upplösning</span><span class="sxs-lookup"><span data-stu-id="555d5-111">Resolution</span></span>

<span data-ttu-id="555d5-112">Om du vill avbryta arbetet följer du stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="555d5-112">To cancel the work, follow these steps.</span></span>

1. <span data-ttu-id="555d5-113">Gå till **Lagerstyrning \> Periodiska uppgifter \> Rensa upp \> Avbryt arbete**.</span><span class="sxs-lookup"><span data-stu-id="555d5-113">Go to **Warehouse management \> Periodic tasks \> Clean up \> Cancel work**.</span></span>
1. <span data-ttu-id="555d5-114">I fältet **Arbets-ID** anger du ID-numret för det arbete som du vil avbryta.</span><span class="sxs-lookup"><span data-stu-id="555d5-114">In the **Work ID** field, specify the ID of the work that you want to cancel.</span></span>
1. <span data-ttu-id="555d5-115">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="555d5-115">Select **OK**.</span></span>
1. <span data-ttu-id="555d5-116">Välj **Ja** för att bekräfta att du vill avbryta arbetet.</span><span class="sxs-lookup"><span data-stu-id="555d5-116">Select **Yes** to confirm that you want to cancel the work.</span></span>

<span data-ttu-id="555d5-117">Mer information finns i [Avbryt lagerarbete för undantagshantering](../../warehousing/cancel-warehouse-work.md).</span><span class="sxs-lookup"><span data-stu-id="555d5-117">For more information, see [Cancel warehouse work for exception handling](../../warehousing/cancel-warehouse-work.md).</span></span>
