---
title: Ställ in efterdaterade checkar
description: I det här avsnittet beskrivs hur du anger om du vill bokföra journalposter för postdaterade checkar och vilka bokföringsjournaler som ska användas för att rensa poster och leverantörsbetalningar.
author: kweekley
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BankParameters, VendPaymMode, CustPaymMode
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e4b18ebe1388998b45e5ef38318b0ade9153f7c8
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2019
ms.locfileid: "342625"
---
# <a name="set-up-postdated-checks"></a><span data-ttu-id="d5fc5-103">Ställ in efterdaterade checkar</span><span class="sxs-lookup"><span data-stu-id="d5fc5-103">Set up postdated checks</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="d5fc5-104">I det här avsnittet beskrivs hur du anger om du vill bokföra journalposter för postdaterade checkar och vilka bokföringsjournaler som ska användas för att rensa poster och leverantörsbetalningar.</span><span class="sxs-lookup"><span data-stu-id="d5fc5-104">This topic explains how to specify whether to post journal entries for postdated checks and which posting journals to use for clearing entries and vendor payments.</span></span> <span data-ttu-id="d5fc5-105">Du kan även ange clearingkonton för Betalda checkar, Mottagna checkar och källskatt.</span><span class="sxs-lookup"><span data-stu-id="d5fc5-105">You can also specify clearing accounts for issued checks, received checks, and withholding tax.</span></span> <span data-ttu-id="d5fc5-106">Efterdaterade checkar som har utfärdats för att skapa och ta emot betalningar vid ett framtida datum.</span><span class="sxs-lookup"><span data-stu-id="d5fc5-106">Postdated checks that are issued to make and receive payments on a future date.</span></span> <span data-ttu-id="d5fc5-107">Du kan ange om checken ska återspeglas i dina redovisningsböcker före dess förfallodag.</span><span class="sxs-lookup"><span data-stu-id="d5fc5-107">You can specify whether the check must be reflected in the accounting books before its maturity date.</span></span>



<span data-ttu-id="d5fc5-108">Rollen för den här proceduren är Kassaförvaltare.</span><span class="sxs-lookup"><span data-stu-id="d5fc5-108">The role of this procedure is Treasurer.</span></span> <span data-ttu-id="d5fc5-109">I den här proceduren används demonstrationsföretaget USMF.</span><span class="sxs-lookup"><span data-stu-id="d5fc5-109">This procedure uses the USMF demo company.</span></span>


## <a name="set-up-postdated-checks"></a><span data-ttu-id="d5fc5-110">Ställ in efterdaterade checkar</span><span class="sxs-lookup"><span data-stu-id="d5fc5-110">Set up postdated checks</span></span>
1. <span data-ttu-id="d5fc5-111">Gå till Kassa- och bankhantering > Inställningar > Parametrar för kassa- och bankhantering.</span><span class="sxs-lookup"><span data-stu-id="d5fc5-111">Go to Cash and bank management > Setup > Cash and bank management parameters.</span></span>
2. <span data-ttu-id="d5fc5-112">Klicka på fliken Efterdaterade checkar.</span><span class="sxs-lookup"><span data-stu-id="d5fc5-112">Click the Postdated checks tab.</span></span>
3. <span data-ttu-id="d5fc5-113">Markera eller avmarkera kryssrutan Aktivera efterdaterade checkar.</span><span class="sxs-lookup"><span data-stu-id="d5fc5-113">Select or clear the Enable postdated checks check box.</span></span>
4. <span data-ttu-id="d5fc5-114">Markera eller avmarkera kryssrutan Bokför journalposter för efterdaterade checkar.</span><span class="sxs-lookup"><span data-stu-id="d5fc5-114">Select or clear the Post journal entries for postdated checks check box.</span></span>
5. <span data-ttu-id="d5fc5-115">I fältet Clearingkonto för utfärdade checkar, ange de önskade värdena.</span><span class="sxs-lookup"><span data-stu-id="d5fc5-115">In the Clearing account for issued checks field, specify the desired values.</span></span>
6. <span data-ttu-id="d5fc5-116">I fältet Clearingkonto för mottagna checkar, ange de önskade värdena.</span><span class="sxs-lookup"><span data-stu-id="d5fc5-116">In the Clearing account for received checks field, specify the desired values.</span></span>
7. <span data-ttu-id="d5fc5-117">I fältet Allmän journal för clearingposter, skriv ett värde.</span><span class="sxs-lookup"><span data-stu-id="d5fc5-117">In the General journal for clearing entries field, type a value.</span></span>
8. <span data-ttu-id="d5fc5-118">I fältet Överför efterdaterade checkar till den här leverantörsbetalningsjournalen, skriv ett värde.</span><span class="sxs-lookup"><span data-stu-id="d5fc5-118">In the Transfer postdated checks to this vendor payment journal field, type a value.</span></span>
9. <span data-ttu-id="d5fc5-119">I fältet Clearingkonto för källskattebelopp, ange de önskade värdena.</span><span class="sxs-lookup"><span data-stu-id="d5fc5-119">In the Withholding tax clearing account field, specify the desired values.</span></span>
10. <span data-ttu-id="d5fc5-120">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="d5fc5-120">Click Save.</span></span>
11. <span data-ttu-id="d5fc5-121">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="d5fc5-121">Close the page.</span></span>
12. <span data-ttu-id="d5fc5-122">Gå till Leverantörsreskontra > Betalningsinställning > Betalningsmetoder.</span><span class="sxs-lookup"><span data-stu-id="d5fc5-122">Go to Accounts payable > Payment setup > Methods of payment.</span></span>
13. <span data-ttu-id="d5fc5-123">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="d5fc5-123">Click New.</span></span>
14. <span data-ttu-id="d5fc5-124">Skriv ett värde i fältet Betalningsmetod.</span><span class="sxs-lookup"><span data-stu-id="d5fc5-124">In the Method of payment field, type a value.</span></span>
15. <span data-ttu-id="d5fc5-125">Välj alternativet Clearingbokföring av efterdaterad check om du vill ange att checkbeloppet bokförs på ett clearingkonto.</span><span class="sxs-lookup"><span data-stu-id="d5fc5-125">Select the Postdated check clearing posting option to indicate that the check amount is posted to a clearing account.</span></span>
16. <span data-ttu-id="d5fc5-126">Välj "Bank" i fältet Kontotyp.</span><span class="sxs-lookup"><span data-stu-id="d5fc5-126">In the Account type field, select 'Bank'.</span></span>
    * <span data-ttu-id="d5fc5-127">Motkontot för betalningsmetoden kommer att vara en bank.</span><span class="sxs-lookup"><span data-stu-id="d5fc5-127">The offset account of the payment method will be a bank.</span></span>  
17. <span data-ttu-id="d5fc5-128">I fältet Betalningskonto, ange önskade värden.</span><span class="sxs-lookup"><span data-stu-id="d5fc5-128">In the Payment account field, specify the desired values.</span></span>
    * <span data-ttu-id="d5fc5-129">Välj det bankkonto som används för att dra av fakturabeloppet.</span><span class="sxs-lookup"><span data-stu-id="d5fc5-129">Select the bank account that is used to deduct the invoice amount.</span></span>  
18. <span data-ttu-id="d5fc5-130">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="d5fc5-130">Close the page.</span></span>
19. <span data-ttu-id="d5fc5-131">Gå till Kundreskontra > Betalningsinställning > Betalningsmetoder</span><span class="sxs-lookup"><span data-stu-id="d5fc5-131">Go to Accounts receivable > Payment setup > Methods of payment</span></span>
20. <span data-ttu-id="d5fc5-132">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="d5fc5-132">Click New.</span></span>
21. <span data-ttu-id="d5fc5-133">Skriv ett värde i fältet Betalningsmetod.</span><span class="sxs-lookup"><span data-stu-id="d5fc5-133">In the Method of payment field, type a value.</span></span>
22. <span data-ttu-id="d5fc5-134">Välj alternativet Clearingbokföring av efterdaterad check om du vill ange att checkbeloppet bokförs på ett clearingkonto.</span><span class="sxs-lookup"><span data-stu-id="d5fc5-134">Select the Postdated check clearing posting option to indicate that the check amount is posted to a clearing account.</span></span>
23. <span data-ttu-id="d5fc5-135">Välj "Bank" i fältet Kontotyp.</span><span class="sxs-lookup"><span data-stu-id="d5fc5-135">In the Account type field, select 'Bank'.</span></span>
    * <span data-ttu-id="d5fc5-136">Motkontot för betalningsmetoden kommer att vara en bank.</span><span class="sxs-lookup"><span data-stu-id="d5fc5-136">The offset account of the payment method will be a bank.</span></span>  
24. <span data-ttu-id="d5fc5-137">I fältet Betalningskonto, ange önskade värden.</span><span class="sxs-lookup"><span data-stu-id="d5fc5-137">In the Payment account field, specify the desired values.</span></span>
    * <span data-ttu-id="d5fc5-138">Välj det bankkonto som används för att dra av fakturabeloppet.</span><span class="sxs-lookup"><span data-stu-id="d5fc5-138">Select the bank account that is used to deduct the invoice amount.</span></span>  
25. <span data-ttu-id="d5fc5-139">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="d5fc5-139">Close the page.</span></span>

