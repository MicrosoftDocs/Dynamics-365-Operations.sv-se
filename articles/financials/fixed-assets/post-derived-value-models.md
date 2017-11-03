---
title: "Bokför med härledda böcker"
description: "Det här avsnittet beskriver hur du använder härledda böcker."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: AssetBookTable, LedgerJournalTransAsset
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 3421
ms.assetid: f5187c21-eec5-4148-b178-b8a5feff7f23
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 94eb82936da2a51a25105b26723088fb7dee9ae5
ms.contentlocale: sv-se
ms.lasthandoff: 11/03/2017

---

# <a name="post-with-derived-books"></a><span data-ttu-id="321b6-103">Bokför med härledda böcker</span><span class="sxs-lookup"><span data-stu-id="321b6-103">Post with derived books</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="321b6-104">Det här avsnittet beskriver hur du använder härledda böcker.</span><span class="sxs-lookup"><span data-stu-id="321b6-104">This article describes how to use derived books.</span></span>

<span data-ttu-id="321b6-105">När transaktioner bokförs för en bok som innehåller härledda böcker, bokförs de härledda boktransaktionerna automatiskt i journaler, inköpsorder eller fritextfakturor.</span><span class="sxs-lookup"><span data-stu-id="321b6-105">When you post transactions for a book that contains derived books, the derived book transactions are posted automatically in journals, purchase orders, or free text invoices.</span></span> <span data-ttu-id="321b6-106">Om du emellertid förbereder de primära boktransaktionerna i journalen för anläggningstillgångar kan du visa och ändra beloppen för härledda transaktioner innan de bokförs.</span><span class="sxs-lookup"><span data-stu-id="321b6-106">However, if you prepare the primary book transactions in the Fixed assets journal, you can view and modify the amounts of the derived transactions before you post them.</span></span>
-   <span data-ttu-id="321b6-107">Vissa konton, som till exempel moms- och kund- eller leverantörskonton, uppdateras bara en gång genom bokföring av den primära boken.</span><span class="sxs-lookup"><span data-stu-id="321b6-107">Certain accounts, such as sales tax and customer or vendor accounts, are updated only once by postings of the primary book.</span></span> <span data-ttu-id="321b6-108">Härledda boktransaktioner bokförs på de konton som har definierats för den härledda boken på sidan för bokföringsprofiler för anläggningstillgångar.</span><span class="sxs-lookup"><span data-stu-id="321b6-108">The derived book transactions are posted to the accounts that have been defined for the derived book in the Fixed asset posting profiles page.</span></span>
-   <span data-ttu-id="321b6-109">Anskaffning (Acquisition) används ofta som transaktionstyp för härledda böcker.</span><span class="sxs-lookup"><span data-stu-id="321b6-109">Acquisition is often used as the transaction type for the derived books.</span></span> <span data-ttu-id="321b6-110">Den används när boken och härledd bok ska tillämpas för anläggningstillgången från och med dess anskaffningsdatum.</span><span class="sxs-lookup"><span data-stu-id="321b6-110">You use this when the book and the derived book should be applied to the fixed asset from the time of the acquisition of the fixed asset.</span></span>
-   <span data-ttu-id="321b6-111">Även andra värden kan gälla för transaktionstypen.</span><span class="sxs-lookup"><span data-stu-id="321b6-111">Other values for the transaction type can also apply.</span></span> <span data-ttu-id="321b6-112">Om till exempel den primära boken och de härledda böckerna har samma intervaller vad gäller försäljning eller avyttring, blir alla transaktionstyper tillgängliga för inställningen av en härledd bok.</span><span class="sxs-lookup"><span data-stu-id="321b6-112">For example, if the primary book and the derived books have the same intervals regarding sale or disposal, all fixed asset transaction types are available for the setup of a derived book.</span></span>

> [!WARNING]
> <span data-ttu-id="321b6-113">Den avskrivning som är bokförd i härledd bok kommer att vara densamma som det belopp som bokfördes för den primära boken.</span><span class="sxs-lookup"><span data-stu-id="321b6-113">Depreciation posted in the derived book will be the same amount as was posted for the primary book.</span></span> <span data-ttu-id="321b6-114">Om avskrivningsmetoderna skiljer sig åt mellan böckerna bör du inte generera avskrivningstransaktioner med den härledda processen.</span><span class="sxs-lookup"><span data-stu-id="321b6-114">If the depreciation methods are different between the books, you should not generate depreciation transactions using the derived process.</span></span> |

## <a name="example"></a><span data-ttu-id="321b6-115">Exempel</span><span class="sxs-lookup"><span data-stu-id="321b6-115">Example</span></span> 
<span data-ttu-id="321b6-116">Följande information beskriver hur du skapar anskaffningstransaktioner med funktionerna för den härledda boken.</span><span class="sxs-lookup"><span data-stu-id="321b6-116">The following information describes how to set up acquisition transactions with the derived book functionality.</span></span>

1.  <span data-ttu-id="321b6-117">Skapa böckerna på boksidan (Böcker).</span><span class="sxs-lookup"><span data-stu-id="321b6-117">Create the books on the Books page.</span></span>
    -   <span data-ttu-id="321b6-118">Bok för redovisning: VM 1, aktuellt bokföringsskikt</span><span class="sxs-lookup"><span data-stu-id="321b6-118">The book for accounting: VM 1, Current posting layer</span></span>
    -   <span data-ttu-id="321b6-119">Bok för skattesyften: VM 2, momsbokföringsskikt</span><span class="sxs-lookup"><span data-stu-id="321b6-119">The book for tax purposes: VM 2, Tax posting layer</span></span>

2.  <span data-ttu-id="321b6-120">Klicka på fliken Härledda böcker i VM 1. Välj VM 2 i fältet Bok samt Tillgång i fältet Transaktionstyp.</span><span class="sxs-lookup"><span data-stu-id="321b6-120">On VM 1, click the Derived books tab. Select VM 2 in the Book field, and Acquisition in the Transaction type field.</span></span>

<span data-ttu-id="321b6-121">Böckerna kan sedan kopplas till specifika anläggningstillgångar.</span><span class="sxs-lookup"><span data-stu-id="321b6-121">The books then can be attached to specific fixed assets.</span></span> 

<span data-ttu-id="321b6-122">När en anskaffning bokförs för en anläggningstillgång med bok VM 1 bokförs anskaffningen inte bara på VM 1 utan även på den härledda boken VM 2.</span><span class="sxs-lookup"><span data-stu-id="321b6-122">When an acquisition is posted for a fixed asset with book VM 1, the acquisition is posted not only on VM 1, but also on the derived book VM 2.</span></span> <span data-ttu-id="321b6-123">Statusen för båda böckerna för anläggningstillgång uppdateras till Öppen.</span><span class="sxs-lookup"><span data-stu-id="321b6-123">The status of both fixed asset books is updated to Open.</span></span>

> [!NOTE]                                                                                                         
> <span data-ttu-id="321b6-124">Om härledda böcker inte används måste du bokföra anskaffningen av anläggningstillgången för både boken VM 1 och boken VM 2.</span><span class="sxs-lookup"><span data-stu-id="321b6-124">If you do not use derived books, you must post the acquisition of the fixed asset both for book VM 1 and book VM 2.</span></span>

<span data-ttu-id="321b6-125">Mer information finns i [Härledda böcker](derived-books.md).</span><span class="sxs-lookup"><span data-stu-id="321b6-125">For more information, see [Derived books](derived-books.md)</span></span>




