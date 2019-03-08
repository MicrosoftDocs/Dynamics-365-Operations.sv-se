---
title: Härledda räkenskapsböcker
description: Den här artikeln ger en översikt över funktionerna för härledda böcker.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetBookTable
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 3401
ms.assetid: 862d6450-187b-497f-9822-cce45f2c65a9
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 153b6437205d5a849fa6a90c0d3b9f3d51dd6768
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2019
ms.locfileid: "313921"
---
# <a name="derived-books"></a><span data-ttu-id="d5d12-103">Härledda räkenskapsböcker</span><span class="sxs-lookup"><span data-stu-id="d5d12-103">Derived books</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="d5d12-104">Den här artikeln ger en översikt över funktionerna för härledda böcker.</span><span class="sxs-lookup"><span data-stu-id="d5d12-104">This article provides an overview of derived book functionality.</span></span>

<span data-ttu-id="d5d12-105">Ändamålet med härledda böcker att att förenkla bokföringen av transaktioner för anläggningstillgångar som planeras med jämna mellanrum.</span><span class="sxs-lookup"><span data-stu-id="d5d12-105">The purpose of derived books is to simplify the posting of fixed asset book transactions that are planned for regular intervals.</span></span>  <span data-ttu-id="d5d12-106">Du kan välja en bok som primär bok.</span><span class="sxs-lookup"><span data-stu-id="d5d12-106">You choose one book as the primary book.</span></span> <span data-ttu-id="d5d12-107">Denna är vanligtvis boken som används för redovisningsavskrivning.</span><span class="sxs-lookup"><span data-stu-id="d5d12-107">This usually is the book that is used for accounting depreciation.</span></span> <span data-ttu-id="d5d12-108">Du kopplar sedan andra böcker till den som har ställts in för bokföring av transaktioner med samma intervaller som den primära boken.</span><span class="sxs-lookup"><span data-stu-id="d5d12-108">You then attach to it other books that are set up to post transactions in the same intervals as the primary book.</span></span> <span data-ttu-id="d5d12-109">Böcker för momsavskrivning anges ofta som härledda böcker.</span><span class="sxs-lookup"><span data-stu-id="d5d12-109">Tax depreciation books are often set up as derived books.</span></span> 

<span data-ttu-id="d5d12-110">De vanligaste transaktionerna att ställas in för redovisning i härledda böcker är anskaffningar, anskaffningsjusteringar och avyttringar.</span><span class="sxs-lookup"><span data-stu-id="d5d12-110">The most common transactions to set up to post to derived books are acquisitions, acquisition adjustments, and disposals.</span></span> 

## <a name="example"></a><span data-ttu-id="d5d12-111">Exempel</span><span class="sxs-lookup"><span data-stu-id="d5d12-111">Example</span></span>

<span data-ttu-id="d5d12-112">Bok B och C ställs in som härledda böcker för bok A för typen anskaffningstransaktion.</span><span class="sxs-lookup"><span data-stu-id="d5d12-112">Book B and book C are set up as derived books for book A for the Acquisition transaction type.</span></span> <span data-ttu-id="d5d12-113">I bok A anger du en anskaffningstransaktion för tillgång 123 på 1 500,00.</span><span class="sxs-lookup"><span data-stu-id="d5d12-113">In book A, you enter an acquisition transaction for asset 123 for 1,500.00.</span></span> 

<span data-ttu-id="d5d12-114">Vid bokföringen av transaktionen genereras en anskaffningstransaktion som bokförs i tillgång 123 för bok B, samt i tillgång 123 för bok C på 1 500,00.</span><span class="sxs-lookup"><span data-stu-id="d5d12-114">When the transaction is posted, an acquisition transaction is generated and posted in asset 123 for book B and in asset 123 for book C for 1,500.00.</span></span> <span data-ttu-id="d5d12-115">När du förbereder transaktionerna för den primära boken för bokföring i Anläggningstillgångsjournalen, kan du också visa och ändra transaktionerna för de härledda böckerna.</span><span class="sxs-lookup"><span data-stu-id="d5d12-115">When you prepare the transactions of the primary book for posting in the fixed asset journal, you can also view and modify the transactions of the derived books.</span></span> <span data-ttu-id="d5d12-116">Om du förbereder transaktionerna för den primära boken i en annan journal, visas inte transaktionerna för det härledda värdet.</span><span class="sxs-lookup"><span data-stu-id="d5d12-116">If you prepare the primary book transactions in another journal, the transactions of the derived value are not displayed.</span></span> <span data-ttu-id="d5d12-117">De bokförs dock på tillämpliga konton och bokföringsskikt när du bokför transaktionerna för den primära boken.</span><span class="sxs-lookup"><span data-stu-id="d5d12-117">However, they are posted to the appropriate accounts and posting layers when you post the primary book transactions.</span></span>

> [!NOTE]                                                                                                                               
> <span data-ttu-id="d5d12-118">Böcker som ställs in för att bokföra transaktioner med andra intervall än de primära bokintervallen måste kopplas till anläggningstillgången som separata böcker och inte som härledda böcker.</span><span class="sxs-lookup"><span data-stu-id="d5d12-118">Books that are set up to post transactions at intervals other than the primary book intervals must be attached to the fixed asset as separate books and not as derived books.</span></span>  

<span data-ttu-id="d5d12-119">Mer information finns i [Bokföring med härledda böcker](post-derived-value-models.md).</span><span class="sxs-lookup"><span data-stu-id="d5d12-119">For more information, see [Posting with derived books](post-derived-value-models.md).</span></span>



