---
title: "Hantera artiklar som lånas till arbetare"
description: "Låneartiklar är poster som gör det enklare för chefer att spåra fysiska artiklar som företaget lånar ut till arbetare."
author: kherr75
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
ms.search.form: HcmLoanItem, HcmLoanType, HcmPersonLoan
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Core, Operations
ms.custom: 3581
ms.assetid: b14bdddb-f10e-4619-9f91-8c88439da862
ms.search.region: Global
ms.author: kherr
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Talent July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: e7b29b1cca0b61f295449045a2d4e38abacf05b5
ms.contentlocale: sv-se
ms.lasthandoff: 11/03/2017

---

# <a name="manage-items-lent-to-workers"></a><span data-ttu-id="04b20-103">Hantera artiklar som lånas till arbetare</span><span class="sxs-lookup"><span data-stu-id="04b20-103">Manage items lent to workers</span></span>

[!include[banner](includes/banner.md)]


<span data-ttu-id="04b20-104">Låneartiklar är poster som gör det enklare för chefer att spåra fysiska artiklar som företaget lånar ut till arbetare.</span><span class="sxs-lookup"><span data-stu-id="04b20-104">Loan items are records that help managers track the physical items that your company lends to its workers.</span></span> 

<span data-ttu-id="04b20-105">Följande exempel anger exempel på artiklar som ett företag kan låna till anställda:</span><span class="sxs-lookup"><span data-stu-id="04b20-105">The following points list examples of items that a company might lend to workers:</span></span>
-   <span data-ttu-id="04b20-106">Mobiltelefoner</span><span class="sxs-lookup"><span data-stu-id="04b20-106">Mobile telephones</span></span>
-   <span data-ttu-id="04b20-107">Bilar</span><span class="sxs-lookup"><span data-stu-id="04b20-107">Automobiles</span></span>
-   <span data-ttu-id="04b20-108">Datorutrustning</span><span class="sxs-lookup"><span data-stu-id="04b20-108">Computer equipment</span></span>

<span data-ttu-id="04b20-109">Varje fysisk artikel måste ha en motsvarande låneartikel.</span><span class="sxs-lookup"><span data-stu-id="04b20-109">Each physical item must have a corresponding loan item.</span></span> <span data-ttu-id="04b20-110">Varje låneartikelpost bör beskriva vad som lånas ut, vem som är ansvarig för lånet och antalet dagar som artikeln kan lånas ut till arbetaren.</span><span class="sxs-lookup"><span data-stu-id="04b20-110">Each loan item record should describe what is being loaned, who is responsible for the loan, and the number of days the item can loaned to a worker.</span></span> <span data-ttu-id="04b20-111">Du kan skapa flera låneartiklar samtidigt, till exempel för nycklar, passerkort eller uniformer.</span><span class="sxs-lookup"><span data-stu-id="04b20-111">You can create multiple loan items, for items such as keys, access cards or uniforms, at the same time.</span></span> 

<span data-ttu-id="04b20-112">När en artikel lånas registrerar du datumet då artikeln lånades samt planerat återlämningsdatum.</span><span class="sxs-lookup"><span data-stu-id="04b20-112">When loaning an item, enter the date that the item was loaned, and the planned return date.</span></span> <span data-ttu-id="04b20-113">När artikeln lämnas tillbaka anger du det faktiska återlämningsdatumet.</span><span class="sxs-lookup"><span data-stu-id="04b20-113">When the item is returned, enter the actual return date.</span></span>

<span data-ttu-id="04b20-114">Medarbetare kan se posterna för de artiklar som har lånats ut till dem via arbetsytan Självbetjäning för medarbetare.</span><span class="sxs-lookup"><span data-stu-id="04b20-114">Employees can view the records of the items that have been loaned to them using the Employee self-service workspace.</span></span> <span data-ttu-id="04b20-115">De kan också redigera befintliga poster eller ange nya låneartiklar, om de har fått ytterligare fysiska artiklar.</span><span class="sxs-lookup"><span data-stu-id="04b20-115">They can also edit the existing records or enter new loan items, if they've received additional physical items.</span></span>  <span data-ttu-id="04b20-116">Arbetsflödet kan ställas in att dirigera vägändringar till nya eller befintliga låneartiklar via en godkännandeprocess.</span><span class="sxs-lookup"><span data-stu-id="04b20-116">Workflow can be set up to route changes to new or existing loan items through an approval process.</span></span> 

<span data-ttu-id="04b20-117">Chefer kan visa lånade artiklar för deras underställda.</span><span class="sxs-lookup"><span data-stu-id="04b20-117">Managers can view loaned items for their direct reports.</span></span> <span data-ttu-id="04b20-118">De kan också beviljas behörighet att lägga till nya låneartiklar åt deras medarbetare.</span><span class="sxs-lookup"><span data-stu-id="04b20-118">They can also be granted permission to add new loan items on behalf of their employees.</span></span>

 <a name="account-for-lost-or-misplaced-loan-items"></a><span data-ttu-id="04b20-119"> Konto för förlorade eller borttappade låneartiklar</span><span class="sxs-lookup"><span data-stu-id="04b20-119">Account for lost or misplaced loan items</span></span>
-----------------------------------------

<span data-ttu-id="04b20-120">Om en artikel skadas eller tappas bort anger du ett fiktivt återlämnande.</span><span class="sxs-lookup"><span data-stu-id="04b20-120">If an item becomes damaged or misplaced, enter a fictitious return record.</span></span> <span data-ttu-id="04b20-121">Sedan raderar du artikeln eller behåller den i översikten och ändrar beskrivningen så att det framgår att den inte är tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="04b20-121">Then either delete the item or keep it in the overview and change the description to indicate that the item is not available.</span></span>

 
<a name="see-also"></a><span data-ttu-id="04b20-122">Se även</span><span class="sxs-lookup"><span data-stu-id="04b20-122">See also</span></span>
--------

[<span data-ttu-id="04b20-123">Personal</span><span class="sxs-lookup"><span data-stu-id="04b20-123">Human resources</span></span>](index.md)




