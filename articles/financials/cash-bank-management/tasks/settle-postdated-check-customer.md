---
title: Kvitta en efterdaterad check från en kund
description: Du kan kvitta en postdaterad check när checken har clearats av banken.
author: kweekley
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustPostDatedChecks, SystemDate, LedgerJournalTable, LedgerJournalTransDaily, LedgerTransVoucher
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 86cefaac99a1ce5aa777f4f62456c3248045cc27
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2019
ms.locfileid: "338255"
---
# <a name="settle-a-postdated-check-from-a-customer"></a><span data-ttu-id="50fb3-103">Kvitta en efterdaterad check från en kund</span><span class="sxs-lookup"><span data-stu-id="50fb3-103">Settle a postdated check from a customer</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="50fb3-104">Du kan kvitta en postdaterad check när checken har clearats av banken.</span><span class="sxs-lookup"><span data-stu-id="50fb3-104">You can settle a postdated check after the check has been cleared by the bank.</span></span> <span data-ttu-id="50fb3-105">Den ekonomiska transaktionen stäms också av mot interimskontotransaktionen för den postdaterade checken.</span><span class="sxs-lookup"><span data-stu-id="50fb3-105">This financial transaction also clears the bridge account transaction for the postdated check.</span></span> 

<span data-ttu-id="50fb3-106">Följande uppgifter måste ha slutförts innan du börjar med den här.</span><span class="sxs-lookup"><span data-stu-id="50fb3-106">The following tasks must be complete before you start this one.</span></span>

1) <span data-ttu-id="50fb3-107">Ställ in efterdaterade checkar</span><span class="sxs-lookup"><span data-stu-id="50fb3-107">Set up postdated checks</span></span>

2) <span data-ttu-id="50fb3-108">Registrera och bokför en efterdaterad check för en kund</span><span class="sxs-lookup"><span data-stu-id="50fb3-108">Register and post a postdated check for a customer</span></span> 



<span data-ttu-id="50fb3-109">Rollen för den här uppgiftsguiden är Kassaförvaltare.</span><span class="sxs-lookup"><span data-stu-id="50fb3-109">The role of this task guides is Treasurer.</span></span>



<span data-ttu-id="50fb3-110">I den här proceduren används demonstrationsföretaget USMF.</span><span class="sxs-lookup"><span data-stu-id="50fb3-110">This procedure uses the USMF demo company.</span></span>

1. <span data-ttu-id="50fb3-111">Gå till Kredit och inkasso > Förfrågningar och rapporter > Betalningar > Kunds efterdaterade checkar.</span><span class="sxs-lookup"><span data-stu-id="50fb3-111">Go to Credit and collections > Inquiries and reports > Payments > Customer postdated checks.</span></span>
2. <span data-ttu-id="50fb3-112">Klicka på Kvitta.</span><span class="sxs-lookup"><span data-stu-id="50fb3-112">Click Settle.</span></span>
3. <span data-ttu-id="50fb3-113">Klicka på Kvitta clearingposter.</span><span class="sxs-lookup"><span data-stu-id="50fb3-113">Click Settle clearing entries.</span></span>
    * <span data-ttu-id="50fb3-114">Kvitta kundkontot för checktransaktionen.</span><span class="sxs-lookup"><span data-stu-id="50fb3-114">Settle the customer account for the check transaction.</span></span>  
4. <span data-ttu-id="50fb3-115">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="50fb3-115">Close the page.</span></span>
5. <span data-ttu-id="50fb3-116">Gå till Redovisning > Journalposter > Allmänna journaler.</span><span class="sxs-lookup"><span data-stu-id="50fb3-116">Go to General ledger > Journal entries > General journals.</span></span>
6. <span data-ttu-id="50fb3-117">I fältet Visa, välj ett alternativ.</span><span class="sxs-lookup"><span data-stu-id="50fb3-117">In the Show field, select an option.</span></span>
7. <span data-ttu-id="50fb3-118">Markera eller avmarkera kryssrutan Visa enbart användarskapade.</span><span class="sxs-lookup"><span data-stu-id="50fb3-118">Select or clear the Show user-created only check box.</span></span>
8. <span data-ttu-id="50fb3-119">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="50fb3-119">In the list, find and select the desired record.</span></span>
9. <span data-ttu-id="50fb3-120">Klicka på Rader.</span><span class="sxs-lookup"><span data-stu-id="50fb3-120">Click Lines.</span></span>
10. <span data-ttu-id="50fb3-121">Klicka på Verifikation.</span><span class="sxs-lookup"><span data-stu-id="50fb3-121">Click Voucher.</span></span>
11. <span data-ttu-id="50fb3-122">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="50fb3-122">Close the page.</span></span>

