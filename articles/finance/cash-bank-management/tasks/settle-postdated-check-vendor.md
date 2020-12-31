---
title: Kvitta en efterdaterad check för en leverantör
description: Kvitta en efterdaterad check som utfärdats till en leverantör när banken har rensat checktransaktionen efter att checken har förfallit till betalning och avförts av banken.
author: kweekley
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendPostDatedChecks, LedgerJournalTable, LedgerJournalTransDaily, LedgerTransVoucher
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ee66bdb93d1252486efc7be25adeb6ee7cc6ce05
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "4448070"
---
# <a name="settle-a-postdated-check-for-a-vendor"></a><span data-ttu-id="2566b-103">Kvitta en efterdaterad check för en leverantör</span><span class="sxs-lookup"><span data-stu-id="2566b-103">Settle a postdated check for a vendor</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="2566b-104">Kvitta en efterdaterad check som utfärdats till en leverantör när banken har rensat checktransaktionen efter att checken har förfallit till betalning och avförts av banken.</span><span class="sxs-lookup"><span data-stu-id="2566b-104">Settle a postdated check issued to a vendor when the bank has cleared the check transaction after the check has been overdue and cleared by the bank.</span></span> 

<span data-ttu-id="2566b-105">Slutför följande procedurer innan du börjar med denna:</span><span class="sxs-lookup"><span data-stu-id="2566b-105">Complete the following procedures before you start this one.</span></span>

1) <span data-ttu-id="2566b-106">Ställ in efterdaterade checkar</span><span class="sxs-lookup"><span data-stu-id="2566b-106">Set up postdated checks</span></span>

2) <span data-ttu-id="2566b-107">Registrera och bokför en efterdaterad check för en leverantör</span><span class="sxs-lookup"><span data-stu-id="2566b-107">Register and post a postdated check for a vendor</span></span>



<span data-ttu-id="2566b-108">Rollen för den här proceduren är Kassaförvaltare.</span><span class="sxs-lookup"><span data-stu-id="2566b-108">The role of this procedure is Treasurer.</span></span> <span data-ttu-id="2566b-109">I den här proceduren används demonstrationsföretaget USMF.</span><span class="sxs-lookup"><span data-stu-id="2566b-109">This procedure uses the USMF demo company.</span></span>

1. <span data-ttu-id="2566b-110">Gå till Leverantörsreskontra > Betalningar > Leverantörens efterdaterade checkar.</span><span class="sxs-lookup"><span data-stu-id="2566b-110">Go to Accounts payable > Payments > Vendor postdated checks.</span></span>
2. <span data-ttu-id="2566b-111">Klicka på Kvitta.</span><span class="sxs-lookup"><span data-stu-id="2566b-111">Click Settle.</span></span>
3. <span data-ttu-id="2566b-112">Klicka på Kvitta clearingposter.</span><span class="sxs-lookup"><span data-stu-id="2566b-112">Click Settle clearing entries.</span></span>
    * <span data-ttu-id="2566b-113">Kvitta leverantörskontot för checktransaktionen.</span><span class="sxs-lookup"><span data-stu-id="2566b-113">Settle the vendor account for the check transaction.</span></span>  
4. <span data-ttu-id="2566b-114">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="2566b-114">Close the page.</span></span>
5. <span data-ttu-id="2566b-115">Gå till Redovisning > Journalposter > Allmänna journaler.</span><span class="sxs-lookup"><span data-stu-id="2566b-115">Go to General ledger > Journal entries > General journals.</span></span>
6. <span data-ttu-id="2566b-116">I fältet Visa, välj Alla.</span><span class="sxs-lookup"><span data-stu-id="2566b-116">In the Show field, select 'All'.</span></span>
7. <span data-ttu-id="2566b-117">Markera eller avmarkera kryssrutan Visa enbart användarskapade.</span><span class="sxs-lookup"><span data-stu-id="2566b-117">Select or clear the Show user-created only check box.</span></span>
8. <span data-ttu-id="2566b-118">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="2566b-118">In the list, mark the selected row.</span></span>
9. <span data-ttu-id="2566b-119">Klicka på Rader.</span><span class="sxs-lookup"><span data-stu-id="2566b-119">Click Lines.</span></span>
10. <span data-ttu-id="2566b-120">Klicka på Verifikation.</span><span class="sxs-lookup"><span data-stu-id="2566b-120">Click Voucher.</span></span>
11. <span data-ttu-id="2566b-121">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="2566b-121">Close the page.</span></span>

