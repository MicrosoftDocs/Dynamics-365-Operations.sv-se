---
title: Konfigurera leasingböcker
description: I det här ämnet beskrivs informationen som upprätthålls i leasingböcker. Leasingböcker innehåller redovisningsprinciper som bestämmer hur en leasing redovisas i systemet.
author: moaamer
manager: Ann Beebe
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TaxTable
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations, Retail
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 28518341544327f1983e563b719b0f455b6e1c43
ms.sourcegitcommit: aeee39c01d3f93a6dfcf2013965fa975a740596a
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/28/2020
ms.locfileid: "4448206"
---
# <a name="set-up-lease-books"></a><span data-ttu-id="07d91-104">Konfigurera leasingböcker</span><span class="sxs-lookup"><span data-stu-id="07d91-104">Set up lease books</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="07d91-105">Leasingböcker innehåller redovisningsprinciper som bestämmer hur en leasing redovisas i systemet.</span><span class="sxs-lookup"><span data-stu-id="07d91-105">Lease books contain the accounting policies that determine how a lease is accounted for in the system.</span></span> <span data-ttu-id="07d91-106">Utöver kontantredovisning följer Leasing av tillgångar följande standarder:</span><span class="sxs-lookup"><span data-stu-id="07d91-106">In addition to cash basis accounting, Asset leasing supports the following standards:</span></span>

- <span data-ttu-id="07d91-107">God redovisningssed i USA (US GAAP, Generally Accepted Accounting Principles)</span><span class="sxs-lookup"><span data-stu-id="07d91-107">Generally Accepted Accounting Principles in the United States (US GAAP)</span></span>
- <span data-ttu-id="07d91-108">Accounting Standards Codification Topic 842 (ASC 842)</span><span class="sxs-lookup"><span data-stu-id="07d91-108">Accounting Standards Codification Topic 842 (ASC 842)</span></span>
- <span data-ttu-id="07d91-109">ASC 840</span><span class="sxs-lookup"><span data-stu-id="07d91-109">ASC 840</span></span>
- <span data-ttu-id="07d91-110">International Financial Reporting Standard 16 (IFRS 16)</span><span class="sxs-lookup"><span data-stu-id="07d91-110">International Financial Reporting Standard 16 (IFRS 16)</span></span>
- <span data-ttu-id="07d91-111">International Accounting Standard 17 (IAS 17)</span><span class="sxs-lookup"><span data-stu-id="07d91-111">International Accounting Standard 17 (IAS 17)</span></span>

<span data-ttu-id="07d91-112">Följ dessa steg för att skapa en leasingbok.</span><span class="sxs-lookup"><span data-stu-id="07d91-112">To create a lease book, follow these steps.</span></span>

1. <span data-ttu-id="07d91-113">Gå till **Leasing av tillgångar \> Konfigurera \> Leasingböcker**.</span><span class="sxs-lookup"><span data-stu-id="07d91-113">Go to **Asset leasing \> Setup \> Lease books**.</span></span>
2. <span data-ttu-id="07d91-114">Välj **Ny** för att lägga till en bok.</span><span class="sxs-lookup"><span data-stu-id="07d91-114">Select **New** to add a book.</span></span>
3. <span data-ttu-id="07d91-115">Ange följande fält.</span><span class="sxs-lookup"><span data-stu-id="07d91-115">Set the following fields.</span></span>

    | <span data-ttu-id="07d91-116">Namn</span><span class="sxs-lookup"><span data-stu-id="07d91-116">Name</span></span>                                     | <span data-ttu-id="07d91-117">beskrivning</span><span class="sxs-lookup"><span data-stu-id="07d91-117">Description</span></span> |
    |------------------------------------------|-------------|
    | <span data-ttu-id="07d91-118">Bokföringsskikt</span><span class="sxs-lookup"><span data-stu-id="07d91-118">Posting layer</span></span>                            | <span data-ttu-id="07d91-119">Välj vilket bokföringsskikt som ska användas.</span><span class="sxs-lookup"><span data-stu-id="07d91-119">Select the posting layer to use.</span></span> <span data-ttu-id="07d91-120">Varje bok som är kopplad till en leasing konfigureras för ett specifikt bokföringsskikt.</span><span class="sxs-lookup"><span data-stu-id="07d91-120">Each book that is attached to a lease is set up for a specific posting layer.</span></span> <span data-ttu-id="07d91-121">Varje bokföringsskikt har olika bokföringssyften.</span><span class="sxs-lookup"><span data-stu-id="07d91-121">Each posting layer has different posting purposes.</span></span> |
    | <span data-ttu-id="07d91-122">Leasingtyp</span><span class="sxs-lookup"><span data-stu-id="07d91-122">Lease type</span></span>                               | <span data-ttu-id="07d91-123">Välj om leasingen ska klassificeras automatiskt eller om den ska vara fördefinierat som finansiell eller operationell leasing.</span><span class="sxs-lookup"><span data-stu-id="07d91-123">Select whether the lease should be classified automatically, or whether it should be predefined as a finance or operating lease.</span></span> |
    | <span data-ttu-id="07d91-124">Ramverk för redovisning</span><span class="sxs-lookup"><span data-stu-id="07d91-124">Accounting framework</span></span>                     | <span data-ttu-id="07d91-125">Välj det ramverk som du vill associera boken med.</span><span class="sxs-lookup"><span data-stu-id="07d91-125">Select the framework that is associated with the book.</span></span> |
    | <span data-ttu-id="07d91-126">Konfiguration av leasingperiod/livslängd</span><span class="sxs-lookup"><span data-stu-id="07d91-126">Lease term/Useful life Set Up</span></span>          | <span data-ttu-id="07d91-127">Leasingen klassificeras som finansiell om leasingtypen är inställd på **Automatisk** och om leasingperioden över tillgångens livslängd är större än eller lika med den procentsats som anges i det här fältet.</span><span class="sxs-lookup"><span data-stu-id="07d91-127">The system will classify the lease as a finance lease if the lease type is set to **Automatic**, and if the lease term over useful life of the asset is greater than or equal to the percentage entered in this field.</span></span>  |
    | <span data-ttu-id="07d91-128">Konfiguration av nuvärde/tillgångens verkliga värde</span><span class="sxs-lookup"><span data-stu-id="07d91-128">Present value / Asset fair value setup</span></span>   | <span data-ttu-id="07d91-129">Ange ett heltal för att definiera tröskeln som bestämmer leasingtypen.</span><span class="sxs-lookup"><span data-stu-id="07d91-129">Enter a whole number to define the threshold that will determine the lease type.</span></span> <span data-ttu-id="07d91-130">Om nuvärdet av framtida minsta leasingbetalningar är mer än det användardefinierade värdet från bokkonfigurationen, och om bokens leasingklassificering är inställd på automatisk, klassificeras leasingen som en finansiell leasing.</span><span class="sxs-lookup"><span data-stu-id="07d91-130">If the present value of future minimum lease payments is more than the user-defined value from the book setup, and if the book's lease classification is set to automatic, the system will classify the lease as a finance lease.</span></span> |
    | <span data-ttu-id="07d91-131">Korttidströskel</span><span class="sxs-lookup"><span data-stu-id="07d91-131">Short-term threshold</span></span>                     | <span data-ttu-id="07d91-132">Ange antalet månader som ska användas som ett tröskelvärde för kortfristig leasing.</span><span class="sxs-lookup"><span data-stu-id="07d91-132">Enter the number of months to use as a threshold for short-term leases.</span></span> <span data-ttu-id="07d91-133">Om leasingperioden är mindre än eller lika med antalet månader som du anger här, klassificeras leasingen som en kortsiktig leasing och behandlingen med uppskov av leasingavgift kommer att tillämpas.</span><span class="sxs-lookup"><span data-stu-id="07d91-133">If the lease term is less than or equal to the number of months that you enter here, the system will classify the lease as a short-term lease, and the deferred rent treatment will be applied.</span></span> |
    | <span data-ttu-id="07d91-134">Lågvärdeströskel</span><span class="sxs-lookup"><span data-stu-id="07d91-134">Low value threshold</span></span>                      | <span data-ttu-id="07d91-135">Ange ett belopp som ska användas som tröskelvärde för lågvärdesleasing.</span><span class="sxs-lookup"><span data-stu-id="07d91-135">Enter an amount to use as a threshold for low-value leases.</span></span> <span data-ttu-id="07d91-136">Om tillgångens verkliga värde är mindre än eller lika med värdet som du anger här, klassificeras leasingen som en lågvärdesleasing och behandlingen med uppskov av leasingavgift kommer att tillämpas.</span><span class="sxs-lookup"><span data-stu-id="07d91-136">If the fair value of the asset is less than or equal or the value that you enter here, the system will classify the lease as a low-value lease, and the deferred rent treatment will be applied.</span></span> |
    | <span data-ttu-id="07d91-137">Betala till leverantör</span><span class="sxs-lookup"><span data-stu-id="07d91-137">Pay to vendor</span></span>                            | <span data-ttu-id="07d91-138">Ställ in det här alternativet **Ja** för att låta leasingbetalningar bokföras, som en faktura, till det leverantörskonto som anges för varje leasing.</span><span class="sxs-lookup"><span data-stu-id="07d91-138">Set this option to **Yes** to allow lease payments to be posted, as an invoice, to the vendor account that is specified on each lease.</span></span> <span data-ttu-id="07d91-139">När en leasingbetalning bokförs kommer leverantörskontot att krediteras.</span><span class="sxs-lookup"><span data-stu-id="07d91-139">When a lease payment is posted, the vendor account will be credited.</span></span> <span data-ttu-id="07d91-140">Om det här alternativet är inställt på **Nej**, krediteras det konto som anges för bokföringstypen **Leasingbetalning** på sidan **Parametrar för bokföring av leasing** i stället.</span><span class="sxs-lookup"><span data-stu-id="07d91-140">If this option is set to **No**, the account that is specified for the **Lease payment** posting type on the **Lease posting parameters** page will be credited instead.</span></span> |
