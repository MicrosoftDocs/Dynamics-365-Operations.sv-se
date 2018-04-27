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
ms.search.scope: Core, Operations, Talent
ms.custom: 3581
ms.assetid: b14bdddb-f10e-4619-9f91-8c88439da862
ms.search.region: Global
ms.author: kherr
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Talent July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: ba1b158908ac2328c29f7efe23756248be5be33c
ms.contentlocale: sv-se
ms.lasthandoff: 04/13/2018

---

# <a name="manage-items-lent-to-workers"></a><span data-ttu-id="0b343-103">Hantera artiklar som lånas till arbetare</span><span class="sxs-lookup"><span data-stu-id="0b343-103">Manage items lent to workers</span></span>

[!INCLUDE [banner](includes/banner.md)]

<span data-ttu-id="0b343-104">Låneartiklar är poster som gör det enklare för chefer att spåra fysiska artiklar som företaget lånar ut till arbetare.</span><span class="sxs-lookup"><span data-stu-id="0b343-104">Loan items are records that help managers track the physical items that your company lends to its workers.</span></span> 

<span data-ttu-id="0b343-105">Följande exempel anger exempel på artiklar som ett företag kan låna till anställda:</span><span class="sxs-lookup"><span data-stu-id="0b343-105">The following points list examples of items that a company might lend to workers:</span></span>
-   <span data-ttu-id="0b343-106">Mobiltelefoner</span><span class="sxs-lookup"><span data-stu-id="0b343-106">Mobile telephones</span></span>
-   <span data-ttu-id="0b343-107">Bilar</span><span class="sxs-lookup"><span data-stu-id="0b343-107">Automobiles</span></span>
-   <span data-ttu-id="0b343-108">Datorutrustning</span><span class="sxs-lookup"><span data-stu-id="0b343-108">Computer equipment</span></span>

<span data-ttu-id="0b343-109">Varje fysisk artikel måste ha en motsvarande låneartikel.</span><span class="sxs-lookup"><span data-stu-id="0b343-109">Each physical item must have a corresponding loan item.</span></span> <span data-ttu-id="0b343-110">Varje låneartikelpost bör beskriva vad som lånas ut, vem som är ansvarig för lånet och antalet dagar som artikeln kan lånas ut till arbetaren.</span><span class="sxs-lookup"><span data-stu-id="0b343-110">Each loan item record should describe what is being loaned, who is responsible for the loan, and the number of days the item can loaned to a worker.</span></span> <span data-ttu-id="0b343-111">Du kan skapa flera låneartiklar samtidigt, till exempel för nycklar, passerkort eller uniformer.</span><span class="sxs-lookup"><span data-stu-id="0b343-111">You can create multiple loan items, for items such as keys, access cards or uniforms, at the same time.</span></span> 

<span data-ttu-id="0b343-112">När en artikel lånas registrerar du datumet då artikeln lånades samt planerat återlämningsdatum.</span><span class="sxs-lookup"><span data-stu-id="0b343-112">When loaning an item, enter the date that the item was loaned, and the planned return date.</span></span> <span data-ttu-id="0b343-113">När artikeln lämnas tillbaka anger du det faktiska återlämningsdatumet.</span><span class="sxs-lookup"><span data-stu-id="0b343-113">When the item is returned, enter the actual return date.</span></span>

<span data-ttu-id="0b343-114">Medarbetare kan se posterna för de artiklar som har lånats ut till dem via arbetsytan Självbetjäning för medarbetare.</span><span class="sxs-lookup"><span data-stu-id="0b343-114">Employees can view the records of the items that have been loaned to them using the Employee self-service workspace.</span></span> <span data-ttu-id="0b343-115">De kan också redigera befintliga poster eller ange nya låneartiklar, om de har fått ytterligare fysiska artiklar.</span><span class="sxs-lookup"><span data-stu-id="0b343-115">They can also edit the existing records or enter new loan items, if they've received additional physical items.</span></span>  <span data-ttu-id="0b343-116">Arbetsflödet kan ställas in att dirigera vägändringar till nya eller befintliga låneartiklar via en godkännandeprocess.</span><span class="sxs-lookup"><span data-stu-id="0b343-116">Workflow can be set up to route changes to new or existing loan items through an approval process.</span></span> 

<span data-ttu-id="0b343-117">Chefer kan visa lånade artiklar för deras underställda.</span><span class="sxs-lookup"><span data-stu-id="0b343-117">Managers can view loaned items for their direct reports.</span></span> <span data-ttu-id="0b343-118">De kan också beviljas behörighet att lägga till nya låneartiklar åt deras medarbetare.</span><span class="sxs-lookup"><span data-stu-id="0b343-118">They can also be granted permission to add new loan items on behalf of their employees.</span></span>

 <a name="account-for-lost-or-misplaced-loan-items"></a><span data-ttu-id="0b343-119"> Konto för förlorade eller borttappade låneartiklar</span><span class="sxs-lookup"><span data-stu-id="0b343-119">Account for lost or misplaced loan items</span></span>
-----------------------------------------

<span data-ttu-id="0b343-120">Om en artikel skadas eller tappas bort anger du ett fiktivt återlämnande.</span><span class="sxs-lookup"><span data-stu-id="0b343-120">If an item becomes damaged or misplaced, enter a fictitious return record.</span></span> <span data-ttu-id="0b343-121">Sedan raderar du artikeln eller behåller den i översikten och ändrar beskrivningen så att det framgår att den inte är tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="0b343-121">Then either delete the item or keep it in the overview and change the description to indicate that the item is not available.</span></span>


<a name="see-also"></a><span data-ttu-id="0b343-122">Se även</span><span class="sxs-lookup"><span data-stu-id="0b343-122">See also</span></span>
--------

[<span data-ttu-id="0b343-123">Personal</span><span class="sxs-lookup"><span data-stu-id="0b343-123">Human resources</span></span>](index.md)




