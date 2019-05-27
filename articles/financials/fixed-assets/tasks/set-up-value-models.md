---
title: Ställ in värdemodeller
description: I den här proceduren visas hur du skapar en ny förteckning över anläggningstillgångar och kopplar den till en anläggningstillgångsgrupp.
author: saraschi2
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetBookTable, AssetGroupBookSetup
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e067173b27488422fd05ad45f37528f00f04a2bd
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/15/2019
ms.locfileid: "1571676"
---
# <a name="set-up-value-models"></a><span data-ttu-id="bd8d3-103">Ställ in värdemodeller</span><span class="sxs-lookup"><span data-stu-id="bd8d3-103">Set up value models</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="bd8d3-104">I den här proceduren visas hur du skapar en ny förteckning över anläggningstillgångar och kopplar den till en anläggningstillgångsgrupp.</span><span class="sxs-lookup"><span data-stu-id="bd8d3-104">This procedure shows you to how create a new fixed asset book and associate it with a fixed asset group.</span></span> <span data-ttu-id="bd8d3-105">Här används revisorrollen och demonstrationsdata för den juridiska USMF-personen.</span><span class="sxs-lookup"><span data-stu-id="bd8d3-105">It uses the accountant role and demo data for the USMF legal entity.</span></span>


## <a name="create-a-book"></a><span data-ttu-id="bd8d3-106">Skapa en räkenskapsbok</span><span class="sxs-lookup"><span data-stu-id="bd8d3-106">Create a book</span></span>
1. <span data-ttu-id="bd8d3-107">Gå till Anläggningstillgångar > Inställningar > Böcker.</span><span class="sxs-lookup"><span data-stu-id="bd8d3-107">Go to Fixed assets > Setup > Books.</span></span>
2. <span data-ttu-id="bd8d3-108">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="bd8d3-108">Click New.</span></span>
3. <span data-ttu-id="bd8d3-109">Ange ett värde i fältet Book.</span><span class="sxs-lookup"><span data-stu-id="bd8d3-109">In the Book field, type a value.</span></span>
4. <span data-ttu-id="bd8d3-110">Ange ett värde i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="bd8d3-110">In the Description field, type a value.</span></span>
    * <span data-ttu-id="bd8d3-111">När Calculate depreciation markeras kommer associerad räkenskapsbok att tas med i avskrivningsförslagen.</span><span class="sxs-lookup"><span data-stu-id="bd8d3-111">If Calculate depreciation is selected, the associated asset book will be included in depreciation proposals.</span></span> <span data-ttu-id="bd8d3-112">Om räkenskapsboken inte markeras, skrivs den inte av automatiskt.</span><span class="sxs-lookup"><span data-stu-id="bd8d3-112">If it is not selected, the asset book will not be automatically depreciated.</span></span>  
5. <span data-ttu-id="bd8d3-113">Välj Yes i fältet Calculate depreciation field.</span><span class="sxs-lookup"><span data-stu-id="bd8d3-113">Select Yes in the Calculate depreciation field.</span></span>
6. <span data-ttu-id="bd8d3-114">Ange eller välj ett värde i fältet Depreciation.</span><span class="sxs-lookup"><span data-stu-id="bd8d3-114">In the Depreciation profile field, enter or select a value.</span></span>
    * <span data-ttu-id="bd8d3-115">En alternativ avskrivningsprofil kallas också för en omställningsmetod för avskrivning.</span><span class="sxs-lookup"><span data-stu-id="bd8d3-115">An alternative depreciation profile is also known as a switchover method of depreciation.</span></span> <span data-ttu-id="bd8d3-116">Avskrivningsförslaget ställs om till denna profil när den alternativa profilen ska beräkna ett avskrivningsbelopp som är lika med eller högre än standardavskrivningsprofilen.</span><span class="sxs-lookup"><span data-stu-id="bd8d3-116">The depreciation proposal will switch to this profile when the alternative profile calculates a depreciation amount that is equal to or greater than the default depreciation profile.</span></span>  
    * <span data-ttu-id="bd8d3-117">Den extraordinära avskrivningsprofilen används för ytterligare avskrivning av en tillgång i ovanliga omständigheter.</span><span class="sxs-lookup"><span data-stu-id="bd8d3-117">The Extraordinary depreciation profile is used for additional depreciation of an asset in unusual circumstances.</span></span> <span data-ttu-id="bd8d3-118">Du kan till exempel använda det för att registrera den avskrivning på grund av naturkatastrofer.</span><span class="sxs-lookup"><span data-stu-id="bd8d3-118">For example, you might use this to record depreciation that results from a natural disaster.</span></span>  
    * <span data-ttu-id="bd8d3-119">När Skapa avskrivningsjusteringar med basjusteringar markeras, skapas avskrivningsjusteringar automatiskt när värdet på tillgången uppdateras.</span><span class="sxs-lookup"><span data-stu-id="bd8d3-119">If Create depreciation adjustments with basis adjustments is selected, depreciation adjustments will be automatically created when the value of the asset is updated.</span></span> <span data-ttu-id="bd8d3-120">Om det inte markeras, kommer det uppdaterade tillgångvärdet påverka endast avskrivningsberäkningar framåt.</span><span class="sxs-lookup"><span data-stu-id="bd8d3-120">If it is not selected, the updated asset value will only affect depreciation calculations going forward.</span></span>  
7. <span data-ttu-id="bd8d3-121">Välj Yes i fältet Create depreciation adjustments with basis adjustments field.</span><span class="sxs-lookup"><span data-stu-id="bd8d3-121">Select Yes in the Create depreciation adjustments with basis adjustments field.</span></span>
    * <span data-ttu-id="bd8d3-122">Som standard kommer transaktioner i förteckningar över anläggningstillgångar att bokföras i redovisningen.</span><span class="sxs-lookup"><span data-stu-id="bd8d3-122">By default, fixed asset book transactions will post to the general ledger.</span></span> <span data-ttu-id="bd8d3-123">Du kan avaktivera bokföring i redovisningen för räkenskapsboken genom att ange fältet Post to general ledger som "No".</span><span class="sxs-lookup"><span data-stu-id="bd8d3-123">You can disable posting to the general ledger for the book by setting the Post to general ledger field to No.</span></span> <span data-ttu-id="bd8d3-124">Räkenskapsböcker som inte bokför i redovisningen används normalt för momsrapporteringssyften.</span><span class="sxs-lookup"><span data-stu-id="bd8d3-124">Books that do not post to the general ledger are typically used for tax reporting purposes.</span></span> <span data-ttu-id="bd8d3-125">Detta ger ytterligare när du vill ta bort historiska transaktioner för tillgångsförteckningen, detta eftersom de inte har förtecknats i redovisningen.</span><span class="sxs-lookup"><span data-stu-id="bd8d3-125">This gives you additional flexibility to delete historical transactions for the asset book because they have not been committed to the general ledger.</span></span>  
    * <span data-ttu-id="bd8d3-126">Bokföringsskikt återgår till det aktuella lagret om räkenskapsboken bokför i redovisningen, eller inget (None) om den inte bokför i redovisningen.</span><span class="sxs-lookup"><span data-stu-id="bd8d3-126">The Posting layer defaults to the Current layer if the book posts to general ledger, and None if it does not post to general ledger.</span></span> <span data-ttu-id="bd8d3-127">Uppdatera bokföringsskiktet om du vill att transaktioner för denna räkenskapsbok bokförs till ett annat skikt.</span><span class="sxs-lookup"><span data-stu-id="bd8d3-127">Update Posting layer if you need transactions for this book to be posted to a different layer.</span></span>  
8. <span data-ttu-id="bd8d3-128">Ange eller välj ett värde i fältet Kalender.</span><span class="sxs-lookup"><span data-stu-id="bd8d3-128">In the Calendar field, enter or select a value.</span></span>
    * <span data-ttu-id="bd8d3-129">Härledda böcker bokför transaktioner samtidigt till olika räkenskapsböcker.</span><span class="sxs-lookup"><span data-stu-id="bd8d3-129">Derived books will post transactions to different books at the same time.</span></span> <span data-ttu-id="bd8d3-130">Du skapar transaktionerna med den primära räkenskapsboken, och under bokföringen bokförs en exakt kopia av transaktionen till den härledda räkenskapsboken.</span><span class="sxs-lookup"><span data-stu-id="bd8d3-130">You create the transactions with the primary book and during posting, an exact copy of the transaction is posted to the derived book.</span></span> <span data-ttu-id="bd8d3-131">Ingen omberäkning med härledda boktransaktioner sker, så den ska inte användas för avskrivningstransaktioner.</span><span class="sxs-lookup"><span data-stu-id="bd8d3-131">There is no recalculation with derived book transactions, so it should not be used for depreciation transactions.</span></span>  

## <a name="associate-the-book-with-a-fixed-asset-group"></a><span data-ttu-id="bd8d3-132">Associera räkenskapsboken till en anläggningstillgångsgrupp</span><span class="sxs-lookup"><span data-stu-id="bd8d3-132">Associate the book with a fixed asset group</span></span>
1. <span data-ttu-id="bd8d3-133">Klicka på Anläggningstillgångsgrupper.</span><span class="sxs-lookup"><span data-stu-id="bd8d3-133">Click Fixed asset groups.</span></span>
2. <span data-ttu-id="bd8d3-134">I fältet Anläggningstillgångsgrupp, ange eller välj ett värde.</span><span class="sxs-lookup"><span data-stu-id="bd8d3-134">In the Fixed asset group field, enter or select a value.</span></span>
3. <span data-ttu-id="bd8d3-135">I fältet Tjänstelivstid, ange ett tal.</span><span class="sxs-lookup"><span data-stu-id="bd8d3-135">In the Service life field, enter a number.</span></span>
    * <span data-ttu-id="bd8d3-136">Notera att avskrivningsperioderna beräknas efter det att du har angett tjänstelivslängden.</span><span class="sxs-lookup"><span data-stu-id="bd8d3-136">Note that Depreciation periods is calculated after setting the Service life.</span></span>  
    * <span data-ttu-id="bd8d3-137">Du kan ange avskrivningspraxis efter vad som krävs i skattesyfte.</span><span class="sxs-lookup"><span data-stu-id="bd8d3-137">You are able to set the depreciation convention as required for tax purposes.</span></span>  

