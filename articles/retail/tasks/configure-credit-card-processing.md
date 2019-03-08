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
ms.openlocfilehash: d75ff895c252bfd4f70f8bcc4c4adece585d9a22
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2019
ms.locfileid: "320407"
---
# <a name="configure-credit-card-processing"></a><span data-ttu-id="9ea27-103"> Konfigurera kreditkortsbearbetning</span><span class="sxs-lookup"><span data-stu-id="9ea27-103">Configure credit card processing</span></span>

[!include [task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="9ea27-104">Den här proceduren går igenom hur du visar en lista med betalningsförmedlare och hur du konfigurerar ett betalningskonto för kundreskontra.</span><span class="sxs-lookup"><span data-stu-id="9ea27-104">This procedure walks through how to view the list of payment providers and how to configure a payment account for accounts receivable.</span></span> <span data-ttu-id="9ea27-105">I den här proceduren används i USRT-företaget med demodata och är avsedda för administratörer och IT-ansvariga.</span><span class="sxs-lookup"><span data-stu-id="9ea27-105">This procedure uses the USRT company in demo data and is intended for Administrators and IT Professionals.</span></span>


## <a name="view-a-list-of-payment-providers"></a><span data-ttu-id="9ea27-106">Visa en lista med betalningsförmedlare</span><span class="sxs-lookup"><span data-stu-id="9ea27-106">View a list of payment providers</span></span>
1. <span data-ttu-id="9ea27-107">Gå till kundfordringar > Betalningar inställning > betaltjänster.</span><span class="sxs-lookup"><span data-stu-id="9ea27-107">Go to Accounts receivable > Payments setup > Payment services.</span></span>
2. <span data-ttu-id="9ea27-108">Klicka på Visa tillgängliga leverantörer.</span><span class="sxs-lookup"><span data-stu-id="9ea27-108">Click View available providers.</span></span>

## <a name="configure-payment-account"></a><span data-ttu-id="9ea27-109">Konfigurera betalningskonto</span><span class="sxs-lookup"><span data-stu-id="9ea27-109">Configure payment account</span></span>
1. <span data-ttu-id="9ea27-110">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="9ea27-110">Click New.</span></span>
2. <span data-ttu-id="9ea27-111">Skriv ett värde i fältet Betalningstjänst.</span><span class="sxs-lookup"><span data-stu-id="9ea27-111">In the Payment service field, type a value.</span></span>
3. <span data-ttu-id="9ea27-112">Välj ett alternativ i fältet Betalningskoppling.</span><span class="sxs-lookup"><span data-stu-id="9ea27-112">In the Payment connector field, select an option.</span></span>
4. <span data-ttu-id="9ea27-113">Växla utökningen av avsnittet Konto för betaltjänster.</span><span class="sxs-lookup"><span data-stu-id="9ea27-113">Toggle the expansion of the Payment service account section.</span></span>
5. <span data-ttu-id="9ea27-114">I fältet Miljö, skriv PROD.</span><span class="sxs-lookup"><span data-stu-id="9ea27-114">In the Environment: field, type 'PROD'.</span></span>
6. <span data-ttu-id="9ea27-115">Klicka på Kreditkortstyper.</span><span class="sxs-lookup"><span data-stu-id="9ea27-115">Click Credit card types.</span></span>
7. <span data-ttu-id="9ea27-116">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Betalningsjournal.</span><span class="sxs-lookup"><span data-stu-id="9ea27-116">In the Payment journal field, click the drop-down button to open the lookup.</span></span>
8. <span data-ttu-id="9ea27-117">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="9ea27-117">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="9ea27-118">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="9ea27-118">Click Add.</span></span>
10. <span data-ttu-id="9ea27-119">Ange ett värde i fältet Valuta.</span><span class="sxs-lookup"><span data-stu-id="9ea27-119">In the Currency field, type a value.</span></span>
11. <span data-ttu-id="9ea27-120">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="9ea27-120">In the list, find and select the desired record.</span></span>
12. <span data-ttu-id="9ea27-121">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Betalningsjournal.</span><span class="sxs-lookup"><span data-stu-id="9ea27-121">In the Payment journal field, click the drop-down button to open the lookup.</span></span>
13. <span data-ttu-id="9ea27-122">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="9ea27-122">In the list, click the link in the selected row.</span></span>
14. <span data-ttu-id="9ea27-123">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="9ea27-123">Click Add.</span></span>
15. <span data-ttu-id="9ea27-124">Ange ett värde i fältet Valuta.</span><span class="sxs-lookup"><span data-stu-id="9ea27-124">In the Currency field, type a value.</span></span>
16. <span data-ttu-id="9ea27-125">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="9ea27-125">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="9ea27-126">Du kan upprepa dessa steg för så många korttyper som du behöver.</span><span class="sxs-lookup"><span data-stu-id="9ea27-126">You can repeat these steps for as many card types as you need.</span></span>  
17. <span data-ttu-id="9ea27-127">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Betalningsjournal.</span><span class="sxs-lookup"><span data-stu-id="9ea27-127">In the Payment journal field, click the drop-down button to open the lookup.</span></span>
18. <span data-ttu-id="9ea27-128">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="9ea27-128">In the list, click the link in the selected row.</span></span>
19. <span data-ttu-id="9ea27-129">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="9ea27-129">Click Add.</span></span>
20. <span data-ttu-id="9ea27-130">Ange ett värde i fältet Valuta.</span><span class="sxs-lookup"><span data-stu-id="9ea27-130">In the Currency field, type a value.</span></span>
21. <span data-ttu-id="9ea27-131">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="9ea27-131">Click Save.</span></span>
22. <span data-ttu-id="9ea27-132">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="9ea27-132">Close the page.</span></span>
23. <span data-ttu-id="9ea27-133">Klicka på Validera.</span><span class="sxs-lookup"><span data-stu-id="9ea27-133">Click Validate.</span></span>
24. <span data-ttu-id="9ea27-134">Klicka på kryssrutan Standardföretag för nya kreditkort.</span><span class="sxs-lookup"><span data-stu-id="9ea27-134">Click the Default processor for new credit cards checkbox.</span></span>
25. <span data-ttu-id="9ea27-135">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="9ea27-135">Click Save.</span></span>

