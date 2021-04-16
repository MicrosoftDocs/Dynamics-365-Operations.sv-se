---
title: Kvitta en efterdaterad check för en leverantör
description: Kvitta en efterdaterad check som utfärdats till en leverantör när banken har rensat checktransaktionen efter att checken har förfallit till betalning och avförts av banken.
author: kweekley
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: VendPostDatedChecks, LedgerJournalTable, LedgerJournalTransDaily, LedgerTransVoucher
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 89acad0c9421960ff4d07ed8eec798b9068424d5
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5834582"
---
# <a name="settle-a-postdated-check-for-a-vendor"></a><span data-ttu-id="d3522-103">Kvitta en efterdaterad check för en leverantör</span><span class="sxs-lookup"><span data-stu-id="d3522-103">Settle a postdated check for a vendor</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="d3522-104">Kvitta en efterdaterad check som utfärdats till en leverantör när banken har rensat checktransaktionen efter att checken har förfallit till betalning och avförts av banken.</span><span class="sxs-lookup"><span data-stu-id="d3522-104">Settle a postdated check issued to a vendor when the bank has cleared the check transaction after the check has been overdue and cleared by the bank.</span></span> 

<span data-ttu-id="d3522-105">Slutför följande procedurer innan du börjar med denna:</span><span class="sxs-lookup"><span data-stu-id="d3522-105">Complete the following procedures before you start this one.</span></span>

1) <span data-ttu-id="d3522-106">Ställ in efterdaterade checkar</span><span class="sxs-lookup"><span data-stu-id="d3522-106">Set up postdated checks</span></span>

2) <span data-ttu-id="d3522-107">Registrera och bokför en efterdaterad check för en leverantör</span><span class="sxs-lookup"><span data-stu-id="d3522-107">Register and post a postdated check for a vendor</span></span>



<span data-ttu-id="d3522-108">Rollen för den här proceduren är Kassaförvaltare.</span><span class="sxs-lookup"><span data-stu-id="d3522-108">The role of this procedure is Treasurer.</span></span> <span data-ttu-id="d3522-109">I den här proceduren används demonstrationsföretaget USMF.</span><span class="sxs-lookup"><span data-stu-id="d3522-109">This procedure uses the USMF demo company.</span></span>

1. <span data-ttu-id="d3522-110">Gå till Leverantörsreskontra > Betalningar > Leverantörens efterdaterade checkar.</span><span class="sxs-lookup"><span data-stu-id="d3522-110">Go to Accounts payable > Payments > Vendor postdated checks.</span></span>
2. <span data-ttu-id="d3522-111">Klicka på Kvitta.</span><span class="sxs-lookup"><span data-stu-id="d3522-111">Click Settle.</span></span>
3. <span data-ttu-id="d3522-112">Klicka på Kvitta clearingposter.</span><span class="sxs-lookup"><span data-stu-id="d3522-112">Click Settle clearing entries.</span></span>
    * <span data-ttu-id="d3522-113">Kvitta leverantörskontot för checktransaktionen.</span><span class="sxs-lookup"><span data-stu-id="d3522-113">Settle the vendor account for the check transaction.</span></span>  
4. <span data-ttu-id="d3522-114">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="d3522-114">Close the page.</span></span>
5. <span data-ttu-id="d3522-115">Gå till Redovisning > Journalposter > Allmänna journaler.</span><span class="sxs-lookup"><span data-stu-id="d3522-115">Go to General ledger > Journal entries > General journals.</span></span>
6. <span data-ttu-id="d3522-116">I fältet Visa, välj Alla.</span><span class="sxs-lookup"><span data-stu-id="d3522-116">In the Show field, select 'All'.</span></span>
7. <span data-ttu-id="d3522-117">Markera eller avmarkera kryssrutan Visa enbart användarskapade.</span><span class="sxs-lookup"><span data-stu-id="d3522-117">Select or clear the Show user-created only check box.</span></span>
8. <span data-ttu-id="d3522-118">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="d3522-118">In the list, mark the selected row.</span></span>
9. <span data-ttu-id="d3522-119">Klicka på Rader.</span><span class="sxs-lookup"><span data-stu-id="d3522-119">Click Lines.</span></span>
10. <span data-ttu-id="d3522-120">Klicka på Verifikation.</span><span class="sxs-lookup"><span data-stu-id="d3522-120">Click Voucher.</span></span>
11. <span data-ttu-id="d3522-121">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="d3522-121">Close the page.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]