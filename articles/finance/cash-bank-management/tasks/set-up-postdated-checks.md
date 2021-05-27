---
title: Ställ in efterdaterade checkar
description: I det här avsnittet beskrivs hur du anger om du vill bokföra journalposter för postdaterade checkar och vilka bokföringsjournaler som ska användas för att rensa poster och leverantörsbetalningar.
author: kweekley
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: BankParameters, VendPaymMode, CustPaymMode
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d0d4afd74f9a0f9018629fa92ab6595bfa94f973
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026215"
---
# <a name="set-up-postdated-checks"></a><span data-ttu-id="df80b-103">Ställ in efterdaterade checkar</span><span class="sxs-lookup"><span data-stu-id="df80b-103">Set up postdated checks</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="df80b-104">I det här avsnittet beskrivs hur du anger om du vill bokföra journalposter för postdaterade checkar och vilka bokföringsjournaler som ska användas för att rensa poster och leverantörsbetalningar.</span><span class="sxs-lookup"><span data-stu-id="df80b-104">This topic explains how to specify whether to post journal entries for postdated checks and which posting journals to use for clearing entries and vendor payments.</span></span> <span data-ttu-id="df80b-105">Du kan även ange clearingkonton för Betalda checkar, Mottagna checkar och källskatt.</span><span class="sxs-lookup"><span data-stu-id="df80b-105">You can also specify clearing accounts for issued checks, received checks, and withholding tax.</span></span> <span data-ttu-id="df80b-106">Efterdaterade checkar som har utfärdats för att skapa och ta emot betalningar vid ett framtida datum.</span><span class="sxs-lookup"><span data-stu-id="df80b-106">Postdated checks that are issued to make and receive payments on a future date.</span></span> <span data-ttu-id="df80b-107">Du kan ange om checken ska återspeglas i dina redovisningsböcker före dess förfallodag.</span><span class="sxs-lookup"><span data-stu-id="df80b-107">You can specify whether the check must be reflected in the accounting books before its maturity date.</span></span>



<span data-ttu-id="df80b-108">Rollen för den här proceduren är Kassaförvaltare.</span><span class="sxs-lookup"><span data-stu-id="df80b-108">The role of this procedure is Treasurer.</span></span> <span data-ttu-id="df80b-109">I den här proceduren används demonstrationsföretaget USMF.</span><span class="sxs-lookup"><span data-stu-id="df80b-109">This procedure uses the USMF demo company.</span></span>


## <a name="set-up-postdated-checks"></a><span data-ttu-id="df80b-110">Ställ in efterdaterade checkar</span><span class="sxs-lookup"><span data-stu-id="df80b-110">Set up postdated checks</span></span>
1. <span data-ttu-id="df80b-111">Gå till Kassa- och bankhantering > Inställningar > Parametrar för kassa- och bankhantering.</span><span class="sxs-lookup"><span data-stu-id="df80b-111">Go to Cash and bank management > Setup > Cash and bank management parameters.</span></span>
2. <span data-ttu-id="df80b-112">Klicka på fliken Efterdaterade checkar.</span><span class="sxs-lookup"><span data-stu-id="df80b-112">Click the Postdated checks tab.</span></span>
3. <span data-ttu-id="df80b-113">Markera eller avmarkera kryssrutan Aktivera efterdaterade checkar.</span><span class="sxs-lookup"><span data-stu-id="df80b-113">Select or clear the Enable postdated checks check box.</span></span>
4. <span data-ttu-id="df80b-114">Markera eller avmarkera kryssrutan Bokför journalposter för efterdaterade checkar.</span><span class="sxs-lookup"><span data-stu-id="df80b-114">Select or clear the Post journal entries for postdated checks check box.</span></span>
5. <span data-ttu-id="df80b-115">I fältet Clearingkonto för utfärdade checkar, ange de önskade värdena.</span><span class="sxs-lookup"><span data-stu-id="df80b-115">In the Clearing account for issued checks field, specify the desired values.</span></span>
6. <span data-ttu-id="df80b-116">I fältet Clearingkonto för mottagna checkar, ange de önskade värdena.</span><span class="sxs-lookup"><span data-stu-id="df80b-116">In the Clearing account for received checks field, specify the desired values.</span></span>
7. <span data-ttu-id="df80b-117">I fältet Allmän journal för clearingposter, skriv ett värde.</span><span class="sxs-lookup"><span data-stu-id="df80b-117">In the General journal for clearing entries field, type a value.</span></span>
8. <span data-ttu-id="df80b-118">I fältet Överför efterdaterade checkar till den här leverantörsbetalningsjournalen, skriv ett värde.</span><span class="sxs-lookup"><span data-stu-id="df80b-118">In the Transfer postdated checks to this vendor payment journal field, type a value.</span></span>
9. <span data-ttu-id="df80b-119">I fältet Clearingkonto för källskattebelopp, ange de önskade värdena.</span><span class="sxs-lookup"><span data-stu-id="df80b-119">In the Withholding tax clearing account field, specify the desired values.</span></span>
10. <span data-ttu-id="df80b-120">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="df80b-120">Click Save.</span></span>
11. <span data-ttu-id="df80b-121">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="df80b-121">Close the page.</span></span>
12. <span data-ttu-id="df80b-122">Gå till Leverantörsreskontra > Betalningsinställning > Betalsätt.</span><span class="sxs-lookup"><span data-stu-id="df80b-122">Go to Accounts payable > Payment setup > Methods of payment.</span></span>
13. <span data-ttu-id="df80b-123">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="df80b-123">Click New.</span></span>
14. <span data-ttu-id="df80b-124">Skriv ett värde i fältet Betalningsmetod.</span><span class="sxs-lookup"><span data-stu-id="df80b-124">In the Method of payment field, type a value.</span></span>
15. <span data-ttu-id="df80b-125">Välj alternativet Clearingbokföring av efterdaterad check om du vill ange att checkbeloppet bokförs på ett clearingkonto.</span><span class="sxs-lookup"><span data-stu-id="df80b-125">Select the Postdated check clearing posting option to indicate that the check amount is posted to a clearing account.</span></span>
16. <span data-ttu-id="df80b-126">Välj "Bank" i fältet Kontotyp.</span><span class="sxs-lookup"><span data-stu-id="df80b-126">In the Account type field, select 'Bank'.</span></span>
    * <span data-ttu-id="df80b-127">Motkontot för betalsättet kommer att vara en bank.</span><span class="sxs-lookup"><span data-stu-id="df80b-127">The offset account of the payment method will be a bank.</span></span>  
17. <span data-ttu-id="df80b-128">I fältet Betalningskonto, ange önskade värden.</span><span class="sxs-lookup"><span data-stu-id="df80b-128">In the Payment account field, specify the desired values.</span></span>
    * <span data-ttu-id="df80b-129">Välj det bankkonto som används för att dra av fakturabeloppet.</span><span class="sxs-lookup"><span data-stu-id="df80b-129">Select the bank account that is used to deduct the invoice amount.</span></span>  
18. <span data-ttu-id="df80b-130">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="df80b-130">Click Save.</span></span>
19. <span data-ttu-id="df80b-131">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="df80b-131">Close the page.</span></span>
> [!NOTE]
> <span data-ttu-id="df80b-132">Om du vill kunna bokföra en bokförd check på ett bankkonto när sessionsdatumet är större än eller lika med förfallodagen, måste du aktivera funktionen **Förfallodatumvalidering för bokföring av betalningsjournal med bokförda checkar på bankkonto**.</span><span class="sxs-lookup"><span data-stu-id="df80b-132">To be able to post a postdated check to a bank account when the session date is greater than or equal to the maturity date, you must enable the feature **Maturity date validation of posting payment journal with postdated checks to bank account**.</span></span> <span data-ttu-id="df80b-133">Med den här funktionen kan du bokföra betalningsjournaler för leverantörer eller kunder med efterbokade checkar när sessionsdatum är större än eller lika med förfallodatumet.</span><span class="sxs-lookup"><span data-stu-id="df80b-133">This feature allows you to post payment journals for vendors or customers with postdated checks, when the session date is greater than or equal to the maturity date.</span></span>
> 
> <span data-ttu-id="df80b-134">När du ställer in **Betalningsmetod** (**leverantörsreskontra > Betalningsinställning > Betalningsmetoder**) ska du inte fylla i **Bryggningskonto**.</span><span class="sxs-lookup"><span data-stu-id="df80b-134">When setting the **Method of payment** (**Accounts payable > Payment setup > Methods of payment**), do not fill in **Bridging account**.</span></span> <span data-ttu-id="df80b-135">I det här fallet fylls motkontot i med bankkontot, som ställs in i **Betalningsmetod**.</span><span class="sxs-lookup"><span data-stu-id="df80b-135">In this case, the offset account is filled in with the bank account, which is set up in the **Method of payment**.</span></span>
>  
> <span data-ttu-id="df80b-136">När funktionen är aktiverad och sessionsdatum är mindre än förfallodagen visas följande felmeddelande när en betalningsjournal bokförs, "Förfallodagen måste vara mindre eller lika med sessionsdatum om motkontotypen är Bank".</span><span class="sxs-lookup"><span data-stu-id="df80b-136">When the feature is enabled and the session date is less than the maturity date, the following error message is displayed when posting a payment journal, "Maturity date must be less or equal to the session date if offset account type is Bank".</span></span> <span data-ttu-id="df80b-137">Om funktionen inte är aktiverad kan du bokföra en betalningsjournal med en bokförd check när sessionsdatum är mindre än förfallodatumet.</span><span class="sxs-lookup"><span data-stu-id="df80b-137">If the feature is not enabled, you can post a payment journal with a postdated check when the session date is less than the maturity date.</span></span>    

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
