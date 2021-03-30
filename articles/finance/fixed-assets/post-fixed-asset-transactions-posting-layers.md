---
title: Bokför transaktioner för anläggningstillgång i bokföringsskikt
description: Den här artikeln ger en översikt över bokföringsskiktsfunktionen för transaktioner för anläggningstillgångar.
author: moaamer
manager: AnnBe
ms.date: 04/25/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetBookTable, LedgerJournalTransAsset
audience: Application User
ms.reviewer: roschlom
ms.custom: 3001
ms.assetid: 7dabde57-0843-47c3-85ef-f36b6f472e30
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 9a52374d52b3dcd435c79033d462a2982316a68b
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5240868"
---
# <a name="post-fixed-asset-transactions-to-posting-layers"></a><span data-ttu-id="cb173-103">Bokför transaktioner för anläggningstillgång i bokföringsskikt</span><span class="sxs-lookup"><span data-stu-id="cb173-103">Post fixed asset transactions to posting layers</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="cb173-104">Den här artikeln ger en översikt över bokföringsskiktsfunktionen för transaktioner för anläggningstillgångar.</span><span class="sxs-lookup"><span data-stu-id="cb173-104">This article gives an overview of posting layer functionality for fixed asset transactions.</span></span>

<span data-ttu-id="cb173-105">En anläggningstillgång skrivs ofta av på olika sätt för olika syften.</span><span class="sxs-lookup"><span data-stu-id="cb173-105">A fixed asset is often depreciated in different ways for different purposes.</span></span> <span data-ttu-id="cb173-106">Avskrivning av skatteskäl beräknas enligt aktuella skatteregler för att uppnå högsta möjliga avskrivning före skatt, men avskrivning av rapporteringsskäl beräknas enligt redovisningslagar och -standarder.</span><span class="sxs-lookup"><span data-stu-id="cb173-106">Depreciation for tax purposes is calculated by using current tax rules to achieve the highest possible depreciation before taxes, but depreciation for reporting purposes is calculated according to accounting laws and standards.</span></span> <span data-ttu-id="cb173-107">De olika typerna av avskrivning beräknas och registreras separat i bokföringsskikten.</span><span class="sxs-lookup"><span data-stu-id="cb173-107">The various kinds of depreciation are calculated and recorded separately in the posting layers.</span></span>

<span data-ttu-id="cb173-108">Varje bok som är kopplad till en anläggningstillgång ställs in för ett visst bokföringsskikt som har ett allmänt avskrivningsmål.</span><span class="sxs-lookup"><span data-stu-id="cb173-108">Each book that is attached to a fixed asset is set up for a particular posting layer that has an overall depreciation objective.</span></span> <span data-ttu-id="cb173-109">Det finns tio bokföringsskikt: Current (Aktuellt), Operations (Verksamhet), Tax (Skatt) samt sju Customs-lager (Anpassade).</span><span class="sxs-lookup"><span data-stu-id="cb173-109">There are ten posting layers: Current, Operations, Tax, and seven Custom layers.</span></span> <span data-ttu-id="cb173-110">Du kan också avaktivera bokföring i redovisningen för boken genom att ange fältet Bokför i huvudboken som Nej.</span><span class="sxs-lookup"><span data-stu-id="cb173-110">You can also disable posting to the general ledger for the book by setting the Post to general ledger field to No.</span></span> <span data-ttu-id="cb173-111">Fältet Bokföring layer ställs sedan automatiskt in på None.</span><span class="sxs-lookup"><span data-stu-id="cb173-111">The Posting layer field is then automatically set to None.</span></span> <span data-ttu-id="cb173-112">Böcker som inte bokför i redovisningen används som regel för momsrapporteringssyften.</span><span class="sxs-lookup"><span data-stu-id="cb173-112">Typically, books that don’t post to the general ledger are used for tax reporting purposes.</span></span> <span data-ttu-id="cb173-113">Denna metod ger dig dessutom flexibilitet att ta bort historiska transaktioner för tillgångsboken, detta eftersom de inte har nedtecknats i redovisningen.</span><span class="sxs-lookup"><span data-stu-id="cb173-113">This approach gives you the additional flexibility to delete historical transactions for the asset book, because they haven’t been committed to the general ledger.</span></span>

<span data-ttu-id="cb173-114">Journaler för anläggningstillgångar har definierats genom att använda sidan Journal names i Huvudbok > Journalinställningar > Journalnamn.</span><span class="sxs-lookup"><span data-stu-id="cb173-114">Fixed asset journals are defined by using the Journal names page at General ledger > Journal setup > Journal names.</span></span> <span data-ttu-id="cb173-115">Varje journal som du kan bokföra avskrivningar i definieras av sitt journalnamn för ett bokföringsskikt.</span><span class="sxs-lookup"><span data-stu-id="cb173-115">Each journal that you can post depreciations in is defined by its journal name for only one posting layer.</span></span> <span data-ttu-id="cb173-116">Bokföringsskiktet i journalen kan inte ändras.</span><span class="sxs-lookup"><span data-stu-id="cb173-116">The posting layer in the journal can’t be changed.</span></span> <span data-ttu-id="cb173-117">Denna begränsning hjälper till att säkerställa att transaktioner för respektive bokföringsskikt hålls åtskilda.</span><span class="sxs-lookup"><span data-stu-id="cb173-117">This restriction helps guarantee that transactions for each posting layer are kept separate.</span></span> <span data-ttu-id="cb173-118">Minst ett journalnamn måste skapas för varje bokföringsskikt.</span><span class="sxs-lookup"><span data-stu-id="cb173-118">At least one journal name must be created for each posting layer.</span></span> <span data-ttu-id="cb173-119">Om du använder böcker som inte bokför i redovisningen, måste du också skapa en journal där bokföringsskiktet är inställt på Ingen.</span><span class="sxs-lookup"><span data-stu-id="cb173-119">If you’re using books that don’t post to the general ledger, you must also create a journal where the posting layer is set to None.</span></span>

<span data-ttu-id="cb173-120">Du kan ange huvudbokskonton för anläggningstillgångar på sidan Bokföringsprofiler för anläggningstillgångar.</span><span class="sxs-lookup"><span data-stu-id="cb173-120">You can designate ledger accounts for fixed asset transactions on the Fixed asset posting profiles page.</span></span> <span data-ttu-id="cb173-121">För varje bokföringsprofil måste du välja relevant transaktionstyp och bok, och sedan välja huvudbokskonton.</span><span class="sxs-lookup"><span data-stu-id="cb173-121">For each posting profile, you must select the relevant transaction type and book, and then designate the ledger accounts.</span></span> <span data-ttu-id="cb173-122">Ställ in en profilpost för bokföring för varje bok som ska bokföra i redovisningen.</span><span class="sxs-lookup"><span data-stu-id="cb173-122">Set up a posting profile record for each book that will post to the general ledger.</span></span>

<span data-ttu-id="cb173-123">Anläggningstillgången kan anges i dokument som bara stöder det **aktuella** bokföringsskiktet, som **Inköpsorder**, **Pågående leverantörsfaktura**, **Försäljningsorder** och **Fritextfaktura**.</span><span class="sxs-lookup"><span data-stu-id="cb173-123">The fixed asset can be entered in documents that only support the **Current** posting layer, like **Purchase order**, **Pending vendor invoice**, **Sales order**, or **Free text invoice**.</span></span> <span data-ttu-id="cb173-124">När du väljer ett anläggningstillgångs-ID i något av dessa dokument, filtreras till tillgångsboken med **aktuellt** bokföringsskikt och fylls i automatiskt vid bokföring när systemet validerar att bokföringsskiktet för anläggningstillgången är **Aktuellt**.</span><span class="sxs-lookup"><span data-stu-id="cb173-124">While selecting a fixed asset ID in any of those documents the asset book is filtered to the book with **Current** posting layer, and will be filled in automatically, during posting when the system validates that the fixed asset posting layer is **Current**.</span></span> <span data-ttu-id="cb173-125">Om valideringen inte kan slutföras avbryts bokföringsprocessen.</span><span class="sxs-lookup"><span data-stu-id="cb173-125">If that validation can't be completed, the posting process will be stopped.</span></span> 

> [!NOTE] 
> <span data-ttu-id="cb173-126">Genom att använda härledda böcker kan du bokföra transaktioner samtidigt till olika bokföringsskikt.</span><span class="sxs-lookup"><span data-stu-id="cb173-126">By using derived books, you can post transactions to different posting layers at the same time.</span></span> <span data-ttu-id="cb173-127">Transaktionerna för den primära boken skapas i en journal eller ett källdokument där bokföringsskiktet motsvarar bokens bokföringsskikt.</span><span class="sxs-lookup"><span data-stu-id="cb173-127">The transactions of the primary book are created in a journal or source document where the posting layer corresponds to the book posting layer.</span></span> <span data-ttu-id="cb173-128">I samband med bokföring bokförs transaktionerna för den härledda boken till lämpliga bokföringsskikt.</span><span class="sxs-lookup"><span data-stu-id="cb173-128">During posting, the derived book transactions will be posted to the appropriate posting layers.</span></span> 


<span data-ttu-id="cb173-129">Mer information finns i [Härledda böcker](derived-books.md) och [Bokföra med härledda böcker](post-derived-value-models.md).</span><span class="sxs-lookup"><span data-stu-id="cb173-129">For more information see, [Derived books](derived-books.md) and [Post with derived books](post-derived-value-models.md).</span></span>





[!INCLUDE[footer-include](../../includes/footer-banner.md)]