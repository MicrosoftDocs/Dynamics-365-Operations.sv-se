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
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 08cf4ec805e632470ef778f31beb87597e0ca096
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "4976201"
---
# <a name="settle-a-postdated-check-for-a-vendor"></a><span data-ttu-id="aff60-103">Kvitta en efterdaterad check för en leverantör</span><span class="sxs-lookup"><span data-stu-id="aff60-103">Settle a postdated check for a vendor</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="aff60-104">Kvitta en efterdaterad check som utfärdats till en leverantör när banken har rensat checktransaktionen efter att checken har förfallit till betalning och avförts av banken.</span><span class="sxs-lookup"><span data-stu-id="aff60-104">Settle a postdated check issued to a vendor when the bank has cleared the check transaction after the check has been overdue and cleared by the bank.</span></span> 

<span data-ttu-id="aff60-105">Slutför följande procedurer innan du börjar med denna:</span><span class="sxs-lookup"><span data-stu-id="aff60-105">Complete the following procedures before you start this one.</span></span>

1) <span data-ttu-id="aff60-106">Ställ in efterdaterade checkar</span><span class="sxs-lookup"><span data-stu-id="aff60-106">Set up postdated checks</span></span>

2) <span data-ttu-id="aff60-107">Registrera och bokför en efterdaterad check för en leverantör</span><span class="sxs-lookup"><span data-stu-id="aff60-107">Register and post a postdated check for a vendor</span></span>



<span data-ttu-id="aff60-108">Rollen för den här proceduren är Kassaförvaltare.</span><span class="sxs-lookup"><span data-stu-id="aff60-108">The role of this procedure is Treasurer.</span></span> <span data-ttu-id="aff60-109">I den här proceduren används demonstrationsföretaget USMF.</span><span class="sxs-lookup"><span data-stu-id="aff60-109">This procedure uses the USMF demo company.</span></span>

1. <span data-ttu-id="aff60-110">Gå till Leverantörsreskontra > Betalningar > Leverantörens efterdaterade checkar.</span><span class="sxs-lookup"><span data-stu-id="aff60-110">Go to Accounts payable > Payments > Vendor postdated checks.</span></span>
2. <span data-ttu-id="aff60-111">Klicka på Kvitta.</span><span class="sxs-lookup"><span data-stu-id="aff60-111">Click Settle.</span></span>
3. <span data-ttu-id="aff60-112">Klicka på Kvitta clearingposter.</span><span class="sxs-lookup"><span data-stu-id="aff60-112">Click Settle clearing entries.</span></span>
    * <span data-ttu-id="aff60-113">Kvitta leverantörskontot för checktransaktionen.</span><span class="sxs-lookup"><span data-stu-id="aff60-113">Settle the vendor account for the check transaction.</span></span>  
4. <span data-ttu-id="aff60-114">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="aff60-114">Close the page.</span></span>
5. <span data-ttu-id="aff60-115">Gå till Redovisning > Journalposter > Allmänna journaler.</span><span class="sxs-lookup"><span data-stu-id="aff60-115">Go to General ledger > Journal entries > General journals.</span></span>
6. <span data-ttu-id="aff60-116">I fältet Visa, välj Alla.</span><span class="sxs-lookup"><span data-stu-id="aff60-116">In the Show field, select 'All'.</span></span>
7. <span data-ttu-id="aff60-117">Markera eller avmarkera kryssrutan Visa enbart användarskapade.</span><span class="sxs-lookup"><span data-stu-id="aff60-117">Select or clear the Show user-created only check box.</span></span>
8. <span data-ttu-id="aff60-118">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="aff60-118">In the list, mark the selected row.</span></span>
9. <span data-ttu-id="aff60-119">Klicka på Rader.</span><span class="sxs-lookup"><span data-stu-id="aff60-119">Click Lines.</span></span>
10. <span data-ttu-id="aff60-120">Klicka på Verifikation.</span><span class="sxs-lookup"><span data-stu-id="aff60-120">Click Voucher.</span></span>
11. <span data-ttu-id="aff60-121">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="aff60-121">Close the page.</span></span>

