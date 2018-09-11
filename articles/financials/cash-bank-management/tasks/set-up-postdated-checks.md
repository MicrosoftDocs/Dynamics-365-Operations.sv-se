--- 
title: "Ställ in efterdaterade checkar"
description: "I det här avsnittet beskrivs hur du anger om du vill bokföra journalposter för postdaterade checkar och vilka bokföringsjournaler som ska användas för att rensa poster och leverantörsbetalningar."
author: kweekley
manager: AnnBe
ms.date: 8/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: BankParameters, VendPaymMode, CustPaymMode
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 32d71167fdad65cb1dec37671999a497759ca484
ms.openlocfilehash: 9cf1f6cc29f023977642380ee2583d4f07c53138
ms.contentlocale: sv-se
ms.lasthandoff: 09/11/2018

---
# <a name="set-up-postdated-checks"></a><span data-ttu-id="3b119-103">Ställ in efterdaterade checkar</span><span class="sxs-lookup"><span data-stu-id="3b119-103">Set up postdated checks</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="3b119-104">I det här avsnittet beskrivs hur du anger om du vill bokföra journalposter för postdaterade checkar och vilka bokföringsjournaler som ska användas för att rensa poster och leverantörsbetalningar.</span><span class="sxs-lookup"><span data-stu-id="3b119-104">This topic explains how to specify whether to post journal entries for postdated checks and which posting journals to use for clearing entries and vendor payments.</span></span> <span data-ttu-id="3b119-105">Du kan även ange clearingkonton för Betalda checkar, Mottagna checkar och källskatt.</span><span class="sxs-lookup"><span data-stu-id="3b119-105">You can also specify clearing accounts for issued checks, received checks, and withholding tax.</span></span> <span data-ttu-id="3b119-106">Efterdaterade checkar som har utfärdats för att skapa och ta emot betalningar vid ett framtida datum.</span><span class="sxs-lookup"><span data-stu-id="3b119-106">Postdated checks that are issued to make and receive payments on a future date.</span></span> <span data-ttu-id="3b119-107">Du kan ange om checken ska återspeglas i dina redovisningsböcker före dess förfallodag.</span><span class="sxs-lookup"><span data-stu-id="3b119-107">You can specify whether the check must be reflected in the accounting books before its maturity date.</span></span>



<span data-ttu-id="3b119-108">Rollen för den här proceduren är Kassaförvaltare.</span><span class="sxs-lookup"><span data-stu-id="3b119-108">The role of this procedure is Treasurer.</span></span> <span data-ttu-id="3b119-109">I den här proceduren används demonstrationsföretaget USMF.</span><span class="sxs-lookup"><span data-stu-id="3b119-109">This procedure uses the USMF demo company.</span></span>


## <a name="set-up-postdated-checks"></a><span data-ttu-id="3b119-110">Ställ in efterdaterade checkar</span><span class="sxs-lookup"><span data-stu-id="3b119-110">Set up postdated checks</span></span>
1. <span data-ttu-id="3b119-111">Gå till Kassa- och bankhantering > Inställningar > Parametrar för kassa- och bankhantering.</span><span class="sxs-lookup"><span data-stu-id="3b119-111">Go to Cash and bank management > Setup > Cash and bank management parameters.</span></span>
2. <span data-ttu-id="3b119-112">Klicka på fliken Efterdaterade checkar.</span><span class="sxs-lookup"><span data-stu-id="3b119-112">Click the Postdated checks tab.</span></span>
3. <span data-ttu-id="3b119-113">Markera eller avmarkera kryssrutan Aktivera efterdaterade checkar.</span><span class="sxs-lookup"><span data-stu-id="3b119-113">Select or clear the Enable postdated checks check box.</span></span>
4. <span data-ttu-id="3b119-114">Markera eller avmarkera kryssrutan Bokför journalposter för efterdaterade checkar.</span><span class="sxs-lookup"><span data-stu-id="3b119-114">Select or clear the Post journal entries for postdated checks check box.</span></span>
5. <span data-ttu-id="3b119-115">I fältet Clearingkonto för utfärdade checkar, ange de önskade värdena.</span><span class="sxs-lookup"><span data-stu-id="3b119-115">In the Clearing account for issued checks field, specify the desired values.</span></span>
6. <span data-ttu-id="3b119-116">I fältet Clearingkonto för mottagna checkar, ange de önskade värdena.</span><span class="sxs-lookup"><span data-stu-id="3b119-116">In the Clearing account for received checks field, specify the desired values.</span></span>
7. <span data-ttu-id="3b119-117">I fältet Allmän journal för clearingposter, skriv ett värde.</span><span class="sxs-lookup"><span data-stu-id="3b119-117">In the General journal for clearing entries field, type a value.</span></span>
8. <span data-ttu-id="3b119-118">I fältet Överför efterdaterade checkar till den här leverantörsbetalningsjournalen, skriv ett värde.</span><span class="sxs-lookup"><span data-stu-id="3b119-118">In the Transfer postdated checks to this vendor payment journal field, type a value.</span></span>
9. <span data-ttu-id="3b119-119">I fältet Clearingkonto för källskattebelopp, ange de önskade värdena.</span><span class="sxs-lookup"><span data-stu-id="3b119-119">In the Withholding tax clearing account field, specify the desired values.</span></span>
10. <span data-ttu-id="3b119-120">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="3b119-120">Click Save.</span></span>
11. <span data-ttu-id="3b119-121">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="3b119-121">Close the page.</span></span>
12. <span data-ttu-id="3b119-122">Gå till Leverantörsreskontra > Betalningsinställning > Betalningsmetoder.</span><span class="sxs-lookup"><span data-stu-id="3b119-122">Go to Accounts payable > Payment setup > Methods of payment.</span></span>
13. <span data-ttu-id="3b119-123">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="3b119-123">Click New.</span></span>
14. <span data-ttu-id="3b119-124">Skriv ett värde i fältet Betalningsmetod.</span><span class="sxs-lookup"><span data-stu-id="3b119-124">In the Method of payment field, type a value.</span></span>
15. <span data-ttu-id="3b119-125">Välj alternativet Clearingbokföring av efterdaterad check om du vill ange att checkbeloppet bokförs på ett clearingkonto.</span><span class="sxs-lookup"><span data-stu-id="3b119-125">Select the Postdated check clearing posting option to indicate that the check amount is posted to a clearing account.</span></span>
16. <span data-ttu-id="3b119-126">Välj "Bank" i fältet Kontotyp.</span><span class="sxs-lookup"><span data-stu-id="3b119-126">In the Account type field, select 'Bank'.</span></span>
    * <span data-ttu-id="3b119-127">Motkontot för betalningsmetoden kommer att vara en bank.</span><span class="sxs-lookup"><span data-stu-id="3b119-127">The offset account of the payment method will be a bank.</span></span>  
17. <span data-ttu-id="3b119-128">I fältet Betalningskonto, ange önskade värden.</span><span class="sxs-lookup"><span data-stu-id="3b119-128">In the Payment account field, specify the desired values.</span></span>
    * <span data-ttu-id="3b119-129">Välj det bankkonto som används för att dra av fakturabeloppet.</span><span class="sxs-lookup"><span data-stu-id="3b119-129">Select the bank account that is used to deduct the invoice amount.</span></span>  
18. <span data-ttu-id="3b119-130">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="3b119-130">Close the page.</span></span>
19. <span data-ttu-id="3b119-131">Gå till Kundreskontra > Betalningsinställning > Betalningsmetoder</span><span class="sxs-lookup"><span data-stu-id="3b119-131">Go to Accounts receivable > Payment setup > Methods of payment</span></span>
20. <span data-ttu-id="3b119-132">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="3b119-132">Click New.</span></span>
21. <span data-ttu-id="3b119-133">Skriv ett värde i fältet Betalningsmetod.</span><span class="sxs-lookup"><span data-stu-id="3b119-133">In the Method of payment field, type a value.</span></span>
22. <span data-ttu-id="3b119-134">Välj alternativet Clearingbokföring av efterdaterad check om du vill ange att checkbeloppet bokförs på ett clearingkonto.</span><span class="sxs-lookup"><span data-stu-id="3b119-134">Select the Postdated check clearing posting option to indicate that the check amount is posted to a clearing account.</span></span>
23. <span data-ttu-id="3b119-135">Välj "Bank" i fältet Kontotyp.</span><span class="sxs-lookup"><span data-stu-id="3b119-135">In the Account type field, select 'Bank'.</span></span>
    * <span data-ttu-id="3b119-136">Motkontot för betalningsmetoden kommer att vara en bank.</span><span class="sxs-lookup"><span data-stu-id="3b119-136">The offset account of the payment method will be a bank.</span></span>  
24. <span data-ttu-id="3b119-137">I fältet Betalningskonto, ange önskade värden.</span><span class="sxs-lookup"><span data-stu-id="3b119-137">In the Payment account field, specify the desired values.</span></span>
    * <span data-ttu-id="3b119-138">Välj det bankkonto som används för att dra av fakturabeloppet.</span><span class="sxs-lookup"><span data-stu-id="3b119-138">Select the bank account that is used to deduct the invoice amount.</span></span>  
25. <span data-ttu-id="3b119-139">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="3b119-139">Close the page.</span></span>


