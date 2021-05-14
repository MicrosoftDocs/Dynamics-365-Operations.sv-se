---
title: Du kan inte avbryta arbete som tilldelats en användare
description: Du kan inte avbryta arbete som tilldelats en användare
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
ms.openlocfilehash: e5f6912cfb1d5be8e46b7989856af99f8a611c11
ms.sourcegitcommit: 5f5afb46431e1abd8fb6e92e0189914b598dc7fd
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2021
ms.locfileid: "5924411"
---
# <a name="you-cant-cancel-work-that-is-on-a-user"></a><span data-ttu-id="94a96-103">Du kan inte avbryta arbete som tilldelats en användare</span><span class="sxs-lookup"><span data-stu-id="94a96-103">You can't cancel work that is on a user</span></span>

<span data-ttu-id="94a96-104">Felkod: WAX708</span><span class="sxs-lookup"><span data-stu-id="94a96-104">Error code: WAX708</span></span>

## <a name="symptoms"></a><span data-ttu-id="94a96-105">Symtom</span><span class="sxs-lookup"><span data-stu-id="94a96-105">Symptoms</span></span>

<span data-ttu-id="94a96-106">Systemet visar följande felmeddelande:</span><span class="sxs-lookup"><span data-stu-id="94a96-106">The system shows the following error message:</span></span>

> <span data-ttu-id="94a96-107">Du kan inte avbryta ett arbete som ligger på en användare.</span><span class="sxs-lookup"><span data-stu-id="94a96-107">You cannot cancel work that is on a user.</span></span>

## <a name="cause"></a><span data-ttu-id="94a96-108">Orsak</span><span class="sxs-lookup"><span data-stu-id="94a96-108">Cause</span></span>

<span data-ttu-id="94a96-109">Arbetet har spärrats av en användare och kan inte avbrytas.</span><span class="sxs-lookup"><span data-stu-id="94a96-109">The work is locked by a user and can't be canceled.</span></span> <span data-ttu-id="94a96-110">Om du vill bekräfta detta öppnar du arbets-ID:t och sedan fliken **Allmänt**. Om arbetet är spärrat kommer fältet **Arbetsstatus** att ställas in som *Pågår* och fältet **spärrat av** erhåller ett användar-ID.</span><span class="sxs-lookup"><span data-stu-id="94a96-110">To confirm this, open the work ID and then open the **General** tab. If the work is locked, the **Work status** field will be set to *In progress*, and the **Locked by** field will be set to a user ID.</span></span>

## <a name="resolution"></a><span data-ttu-id="94a96-111">Upplösning</span><span class="sxs-lookup"><span data-stu-id="94a96-111">Resolution</span></span>

<span data-ttu-id="94a96-112">Om du vill avbryta arbetet följer du stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="94a96-112">To cancel the work, follow these steps.</span></span>

1. <span data-ttu-id="94a96-113">Gå till **Lagerstyrning \> Periodiska uppgifter \> Rensa upp \> Avbryt arbete**.</span><span class="sxs-lookup"><span data-stu-id="94a96-113">Go to **Warehouse management \> Periodic tasks \> Clean up \> Cancel work**.</span></span>
1. <span data-ttu-id="94a96-114">I fältet **Arbets-ID** anger du ID-numret för det arbete som du vil avbryta.</span><span class="sxs-lookup"><span data-stu-id="94a96-114">In the **Work ID** field, specify the ID of the work that you want to cancel.</span></span>
1. <span data-ttu-id="94a96-115">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="94a96-115">Select **OK**.</span></span>
1. <span data-ttu-id="94a96-116">Välj **Ja** för att bekräfta att du vill avbryta arbetet.</span><span class="sxs-lookup"><span data-stu-id="94a96-116">Select **Yes** to confirm that you want to cancel the work.</span></span>

<span data-ttu-id="94a96-117">Mer information finns i [Avbryt lagerarbete för undantagshantering](../../warehousing/cancel-warehouse-work.md).</span><span class="sxs-lookup"><span data-stu-id="94a96-117">For more information, see [Cancel warehouse work for exception handling](../../warehousing/cancel-warehouse-work.md).</span></span>
