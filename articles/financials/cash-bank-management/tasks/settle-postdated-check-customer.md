--- 
title: "Kvitta en efterdaterad check från en kund"
description: "Du kan kvitta en postdaterad check när checken har clearats av banken."
author: kweekley
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 95651e602bd4f576a7fcf96379f61252cdf392f6
ms.contentlocale: sv-se
ms.lasthandoff: 05/08/2018

---
# <a name="settle-a-postdated-check-from-a-customer"></a><span data-ttu-id="7eef1-103">Kvitta en efterdaterad check från en kund</span><span class="sxs-lookup"><span data-stu-id="7eef1-103">Settle a postdated check from a customer</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="7eef1-104">Du kan kvitta en postdaterad check när checken har clearats av banken.</span><span class="sxs-lookup"><span data-stu-id="7eef1-104">You can settle a postdated check after the check has been cleared by the bank.</span></span> <span data-ttu-id="7eef1-105">Den ekonomiska transaktionen stäms också av mot interimskontotransaktionen för den postdaterade checken.</span><span class="sxs-lookup"><span data-stu-id="7eef1-105">This financial transaction also clears the bridge account transaction for the postdated check.</span></span> 

<span data-ttu-id="7eef1-106">Följande uppgifter måste ha slutförts innan du börjar med den här.</span><span class="sxs-lookup"><span data-stu-id="7eef1-106">The following tasks must be complete before you start this one.</span></span>

1) <span data-ttu-id="7eef1-107">Ställ in efterdaterade checkar</span><span class="sxs-lookup"><span data-stu-id="7eef1-107">Set up postdated checks</span></span>

2) <span data-ttu-id="7eef1-108">Registrera och bokför en efterdaterad check för en kund</span><span class="sxs-lookup"><span data-stu-id="7eef1-108">Register and post a postdated check for a customer</span></span> 



<span data-ttu-id="7eef1-109">Rollen för den här uppgiftsguiden är Kassaförvaltare.</span><span class="sxs-lookup"><span data-stu-id="7eef1-109">The role of this task guides is Treasurer.</span></span>



<span data-ttu-id="7eef1-110">I den här proceduren används demonstrationsföretaget USMF.</span><span class="sxs-lookup"><span data-stu-id="7eef1-110">This procedure uses the USMF demo company.</span></span>

1. <span data-ttu-id="7eef1-111">Gå till Kredit och inkasso > Förfrågningar och rapporter > Betalningar > Kunds efterdaterade checkar.</span><span class="sxs-lookup"><span data-stu-id="7eef1-111">Go to Credit and collections > Inquiries and reports > Payments > Customer postdated checks.</span></span>
2. <span data-ttu-id="7eef1-112">Klicka på Kvitta.</span><span class="sxs-lookup"><span data-stu-id="7eef1-112">Click Settle.</span></span>
3. <span data-ttu-id="7eef1-113">Klicka på Kvitta clearingposter.</span><span class="sxs-lookup"><span data-stu-id="7eef1-113">Click Settle clearing entries.</span></span>
    * <span data-ttu-id="7eef1-114">Kvitta kundkontot för checktransaktionen.</span><span class="sxs-lookup"><span data-stu-id="7eef1-114">Settle the customer account for the check transaction.</span></span>  
4. <span data-ttu-id="7eef1-115">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="7eef1-115">Close the page.</span></span>
5. <span data-ttu-id="7eef1-116">Gå till Redovisning > Journalposter > Allmänna journaler.</span><span class="sxs-lookup"><span data-stu-id="7eef1-116">Go to General ledger > Journal entries > General journals.</span></span>
6. <span data-ttu-id="7eef1-117">I fältet Visa, välj ett alternativ.</span><span class="sxs-lookup"><span data-stu-id="7eef1-117">In the Show field, select an option.</span></span>
7. <span data-ttu-id="7eef1-118">Markera eller avmarkera kryssrutan Visa enbart användarskapade.</span><span class="sxs-lookup"><span data-stu-id="7eef1-118">Select or clear the Show user-created only check box.</span></span>
8. <span data-ttu-id="7eef1-119">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="7eef1-119">In the list, find and select the desired record.</span></span>
9. <span data-ttu-id="7eef1-120">Klicka på Rader.</span><span class="sxs-lookup"><span data-stu-id="7eef1-120">Click Lines.</span></span>
10. <span data-ttu-id="7eef1-121">Klicka på Verifikation.</span><span class="sxs-lookup"><span data-stu-id="7eef1-121">Click Voucher.</span></span>
11. <span data-ttu-id="7eef1-122">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="7eef1-122">Close the page.</span></span>


