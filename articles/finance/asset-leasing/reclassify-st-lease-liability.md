---
title: Omklassificera den kortfristiga delen av en leasingskuld
description: I det här ämnet beskrivs hur du skapar en månatlig journalpost som klassificerar en del av leasingskulden som kortsiktig.
author: moaamer
manager: Ann Beebe
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations, Retail
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 46bcd396c93bc1d2944241165d438f8ccc013e20
ms.sourcegitcommit: aeee39c01d3f93a6dfcf2013965fa975a740596a
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/28/2020
ms.locfileid: "4448201"
---
# <a name="reclassify-the-short-term-portion-of-lease-liability"></a><span data-ttu-id="462ef-103">Omklassificera den kortfristiga delen av leasingskuld</span><span class="sxs-lookup"><span data-stu-id="462ef-103">Reclassify the short-term portion of lease liability</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="462ef-104">I det här ämnet beskrivs hur du skapar en månatlig journalpost som klassificerar en del av leasingskulden som kortsiktig.</span><span class="sxs-lookup"><span data-stu-id="462ef-104">This topic explains how to create a monthly journal entry to reclassify a portion of the lease liability as short-term.</span></span> <span data-ttu-id="462ef-105">När det schema som har valts i batchprocessen är **Omklassificering av korttidsleasingskuld**, skapas en journalpost.</span><span class="sxs-lookup"><span data-stu-id="462ef-105">When the schedule that is selected in the batch process is **Short-term lease liability reclass**, a journal entry is created.</span></span> <span data-ttu-id="462ef-106">Den här posten används för att bokföra den aktuella delen av leasingskulden den sista dagen i månaden.</span><span class="sxs-lookup"><span data-stu-id="462ef-106">This entry is used to post the current portion of the lease liability on the last day of the month.</span></span> <span data-ttu-id="462ef-107">Samtidigt bokförs en återföringspost från den första dagen i nästa månad.</span><span class="sxs-lookup"><span data-stu-id="462ef-107">At the same time, a reversal entry is posted as of the first day of the next month.</span></span>

<span data-ttu-id="462ef-108">Den kortfristiga delen av leasingskulden visas i planen för amortering av skulder.</span><span class="sxs-lookup"><span data-stu-id="462ef-108">The short-term portion of the lease liability is shown on the liability amortization schedule.</span></span> <span data-ttu-id="462ef-109">När journaltransaktionen bokförs blir kolumnen **Omklassificeringsjournal för skuld skapad** tillgänglig, och journal-ID:t anges också i planen.</span><span class="sxs-lookup"><span data-stu-id="462ef-109">When the journal entry is posted, the **Liability reclass journal created** column becomes available, and the journal ID is also filled in on the schedule.</span></span>

<span data-ttu-id="462ef-110">Om du vill skapa och bokföra journalposten för omklassificering av kortfristiga skulder följer du dessa steg.</span><span class="sxs-lookup"><span data-stu-id="462ef-110">To create and post the short-term liability reclassification journal entry, follow these steps.</span></span>

1. <span data-ttu-id="462ef-111">Gå till **Leasing av tillgångar \> Periodisk \> Batchgenerering av journal**.</span><span class="sxs-lookup"><span data-stu-id="462ef-111">Go to **Asset leasing \> Periodic \> Batch journal creation**.</span></span>
2. <span data-ttu-id="462ef-112">I dialogrutan **Batchgenerering av journal**, i fältet **Välj plan**, väljer du **Omklassificering av kortfristig leasingskuld**.</span><span class="sxs-lookup"><span data-stu-id="462ef-112">In the **Batch journal creation** dialog box, in the **Select schedule** field, select **Short-term lease liability reclass**.</span></span>
3. <span data-ttu-id="462ef-113">Välj en leasinggrupp i fältet **Leasinggrupp**.</span><span class="sxs-lookup"><span data-stu-id="462ef-113">In the **Lease group** field, select a lease group.</span></span> <span data-ttu-id="462ef-114">Du kan också välja bok-ID i fältet **Bok-ID**.</span><span class="sxs-lookup"><span data-stu-id="462ef-114">Alternatively, in the **Book ID** field, select the book ID.</span></span>
4. <span data-ttu-id="462ef-115">Aktivera parametern **Bokför**.</span><span class="sxs-lookup"><span data-stu-id="462ef-115">Turn on the **Post** parameter.</span></span> <span data-ttu-id="462ef-116">Om posten ska skapas men inte bokföras lämnar du den här parametern inaktiverad.</span><span class="sxs-lookup"><span data-stu-id="462ef-116">Alternatively, if the entry should be created but not posted, leave this parameter turned off.</span></span>
5. <span data-ttu-id="462ef-117">Aktivera parametern **Förhandsgranska före bokföring** för att visa posten innan den bokförs.</span><span class="sxs-lookup"><span data-stu-id="462ef-117">Turn on the **Preview before posting** parameter to view the entry before it's posted.</span></span>
6. <span data-ttu-id="462ef-118">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="462ef-118">Select **OK**.</span></span>