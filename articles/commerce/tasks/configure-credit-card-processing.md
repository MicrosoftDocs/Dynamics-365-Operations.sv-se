---
title: " Konfigurera kreditkortsbearbetning"
description: Den här proceduren går igenom hur du visar en lista med betalningsförmedlare och hur du konfigurerar ett betalningskonto för kundreskontra.
author: jashanno
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations, Retail
ms.search.region: Global
ms.search.industry: Retail
ms.author: jashanno
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2cfec44bc1c767dff1109c4ecd4e2862443fb1d0
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/18/2020
ms.locfileid: "3141509"
---
# <a name="configure-credit-card-processing"></a><span data-ttu-id="18620-103"> Konfigurera kreditkortsbearbetning</span><span class="sxs-lookup"><span data-stu-id="18620-103">Configure credit card processing</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="18620-104">Den här proceduren går igenom hur du visar en lista med betalningsförmedlare och hur du konfigurerar ett betalningskonto för kundreskontra.</span><span class="sxs-lookup"><span data-stu-id="18620-104">This procedure walks through how to view the list of payment providers and how to configure a payment account for accounts receivable.</span></span> <span data-ttu-id="18620-105">I den här proceduren används i USRT-företaget med demodata och är avsedda för administratörer och IT-ansvariga.</span><span class="sxs-lookup"><span data-stu-id="18620-105">This procedure uses the USRT company in demo data and is intended for Administrators and IT Professionals.</span></span>


## <a name="view-a-list-of-payment-providers"></a><span data-ttu-id="18620-106">Visa en lista med betalningsförmedlare</span><span class="sxs-lookup"><span data-stu-id="18620-106">View a list of payment providers</span></span>
1. <span data-ttu-id="18620-107">Gå till kundfordringar > Betalningar inställning > betaltjänster.</span><span class="sxs-lookup"><span data-stu-id="18620-107">Go to Accounts receivable > Payments setup > Payment services.</span></span>
2. <span data-ttu-id="18620-108">Klicka på Visa tillgängliga leverantörer.</span><span class="sxs-lookup"><span data-stu-id="18620-108">Click View available providers.</span></span>

## <a name="configure-payment-account"></a><span data-ttu-id="18620-109">Konfigurera betalningskonto</span><span class="sxs-lookup"><span data-stu-id="18620-109">Configure payment account</span></span>
1. <span data-ttu-id="18620-110">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="18620-110">Click New.</span></span>
2. <span data-ttu-id="18620-111">Skriv ett värde i fältet Betalningstjänst.</span><span class="sxs-lookup"><span data-stu-id="18620-111">In the Payment service field, type a value.</span></span>
3. <span data-ttu-id="18620-112">Välj ett alternativ i fältet Betalningskoppling.</span><span class="sxs-lookup"><span data-stu-id="18620-112">In the Payment connector field, select an option.</span></span>
4. <span data-ttu-id="18620-113">Växla utökningen av avsnittet Konto för betaltjänster.</span><span class="sxs-lookup"><span data-stu-id="18620-113">Toggle the expansion of the Payment service account section.</span></span>
5. <span data-ttu-id="18620-114">I fältet Miljö, skriv PROD.</span><span class="sxs-lookup"><span data-stu-id="18620-114">In the Environment: field, type 'PROD'.</span></span>
6. <span data-ttu-id="18620-115">Klicka på Kreditkortstyper.</span><span class="sxs-lookup"><span data-stu-id="18620-115">Click Credit card types.</span></span>
7. <span data-ttu-id="18620-116">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Betalningsjournal.</span><span class="sxs-lookup"><span data-stu-id="18620-116">In the Payment journal field, click the drop-down button to open the lookup.</span></span>
8. <span data-ttu-id="18620-117">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="18620-117">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="18620-118">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="18620-118">Click Add.</span></span>
10. <span data-ttu-id="18620-119">Ange ett värde i fältet Valuta.</span><span class="sxs-lookup"><span data-stu-id="18620-119">In the Currency field, type a value.</span></span>
11. <span data-ttu-id="18620-120">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="18620-120">In the list, find and select the desired record.</span></span>
12. <span data-ttu-id="18620-121">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Betalningsjournal.</span><span class="sxs-lookup"><span data-stu-id="18620-121">In the Payment journal field, click the drop-down button to open the lookup.</span></span>
13. <span data-ttu-id="18620-122">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="18620-122">In the list, click the link in the selected row.</span></span>
14. <span data-ttu-id="18620-123">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="18620-123">Click Add.</span></span>
15. <span data-ttu-id="18620-124">Ange ett värde i fältet Valuta.</span><span class="sxs-lookup"><span data-stu-id="18620-124">In the Currency field, type a value.</span></span>
16. <span data-ttu-id="18620-125">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="18620-125">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="18620-126">Du kan upprepa dessa steg för så många korttyper som du behöver.</span><span class="sxs-lookup"><span data-stu-id="18620-126">You can repeat these steps for as many card types as you need.</span></span>  
17. <span data-ttu-id="18620-127">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Betalningsjournal.</span><span class="sxs-lookup"><span data-stu-id="18620-127">In the Payment journal field, click the drop-down button to open the lookup.</span></span>
18. <span data-ttu-id="18620-128">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="18620-128">In the list, click the link in the selected row.</span></span>
19. <span data-ttu-id="18620-129">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="18620-129">Click Add.</span></span>
20. <span data-ttu-id="18620-130">Ange ett värde i fältet Valuta.</span><span class="sxs-lookup"><span data-stu-id="18620-130">In the Currency field, type a value.</span></span>
21. <span data-ttu-id="18620-131">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="18620-131">Click Save.</span></span>
22. <span data-ttu-id="18620-132">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="18620-132">Close the page.</span></span>
23. <span data-ttu-id="18620-133">Klicka på Validera.</span><span class="sxs-lookup"><span data-stu-id="18620-133">Click Validate.</span></span>
24. <span data-ttu-id="18620-134">Klicka på kryssrutan Standardföretag för nya kreditkort.</span><span class="sxs-lookup"><span data-stu-id="18620-134">Click the Default processor for new credit cards checkbox.</span></span>
25. <span data-ttu-id="18620-135">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="18620-135">Click Save.</span></span>

