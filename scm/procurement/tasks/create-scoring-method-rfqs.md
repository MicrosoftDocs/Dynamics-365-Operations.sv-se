--- 
title: "Skapa en poängmetod för anbudsförfrågan"
description: "Den här proceduren visar hur du skapar en poängmetod."
author: mkirknel
manager: AnnBe
ms.date: 08/23/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 6d72678db60254801c6c899f4d405f1c59de8d65
ms.contentlocale: sv-se
ms.lasthandoff: 08/29/2017

---
# <a name="create-a-scoring-method-for-rfqs"></a><span data-ttu-id="b32fa-103">Skapa en poängmetod för anbudsförfrågan</span><span class="sxs-lookup"><span data-stu-id="b32fa-103">Create a scoring method for RFQs</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="b32fa-104">Den här proceduren visar hur du skapar en poängmetod.</span><span class="sxs-lookup"><span data-stu-id="b32fa-104">This procedure shows you how to create a scoring method.</span></span> <span data-ttu-id="b32fa-105">En poängmetod är en uppsättning kriterier som kan användas för att jämföra bud som skickas som svar på en anbudsförfrågan.</span><span class="sxs-lookup"><span data-stu-id="b32fa-105">A scoring method is a set of criteria that can be used to compare bids that are sent in reply to a request for quotation (RFQ).</span></span> <span data-ttu-id="b32fa-106">Du kanske till exempel vill utvärdera en leverantör för tidigare prestationer, eller bedöma om företaget är miljövänligt eller en bra samarbetspartner, eller du kanske vill jämföra bud baserat på pris.</span><span class="sxs-lookup"><span data-stu-id="b32fa-106">For example, you might want to rate a vendor on past performance, or rate whether the company is environmentally friendly or a good collaborator, or you might want to compare bids based on price.</span></span> <span data-ttu-id="b32fa-107">Poängmetoden kan kopplas till en typ av begäran som standardpoängmetoden för anbudsförfrågan av den typen.</span><span class="sxs-lookup"><span data-stu-id="b32fa-107">The scoring method can be associated with a solicitation type as the default scoring method for RFQs of that type.</span></span> <span data-ttu-id="b32fa-108">Dessa uppgifter utförs vanligtvis av en inköpschef.</span><span class="sxs-lookup"><span data-stu-id="b32fa-108">These tasks would typically be carried out by a purchasing manager.</span></span> <span data-ttu-id="b32fa-109">Du kan använda den här proceduren i demonstrationsföretaget USMF eller på dina egna data.</span><span class="sxs-lookup"><span data-stu-id="b32fa-109">You can use this procedure in demo data company USMF or on your own data.</span></span>

1. <span data-ttu-id="b32fa-110">Gå till Anskaffning och källa > Inställning > Anbudsförfrågan > Poängsättningsmetod.</span><span class="sxs-lookup"><span data-stu-id="b32fa-110">Go to Procurement and sourcing > Setup > Request for quotation > Scoring method.</span></span>
2. <span data-ttu-id="b32fa-111">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="b32fa-111">Click New.</span></span>
3. <span data-ttu-id="b32fa-112">Skriv ett värde i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="b32fa-112">In the Name field, type a value.</span></span>
4. <span data-ttu-id="b32fa-113">Ange ett värde i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="b32fa-113">In the Description field, type a value.</span></span>
5. <span data-ttu-id="b32fa-114">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="b32fa-114">Click Save.</span></span>
6. <span data-ttu-id="b32fa-115">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="b32fa-115">Click New.</span></span>
7. <span data-ttu-id="b32fa-116">Skriv ett värde i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="b32fa-116">In the Name field, type a value.</span></span>
8. <span data-ttu-id="b32fa-117">Ange ett värde i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="b32fa-117">In the Description field, type a value.</span></span>
    * <span data-ttu-id="b32fa-118">Beskrivningen visas tillsammans med poängmetodsnamnet när en poängmetod markeras för en anbudsförfrågan.</span><span class="sxs-lookup"><span data-stu-id="b32fa-118">This description is shown along with the scoring method name when a scoring method is selected for an RFQ.</span></span>  
9. <span data-ttu-id="b32fa-119">Ange ett nummer i fältet Intervall från.</span><span class="sxs-lookup"><span data-stu-id="b32fa-119">In the Range from field, enter a number.</span></span>
    * <span data-ttu-id="b32fa-120">Intervallgränserna som anskaffningsproffset kan ange som en poäng.</span><span class="sxs-lookup"><span data-stu-id="b32fa-120">The range limits what the procurement professional can enter as a score.</span></span> <span data-ttu-id="b32fa-121">Om det finns flera poängkriterier på en anbudsförfrågan, kommer poängen som har angetts läggas till varandra och summan görs tillgänglig för att låta jämföra buden.</span><span class="sxs-lookup"><span data-stu-id="b32fa-121">When there are multiple scoring criteria on an RFQ, the scores that have been entered are added to each other and the sum is made available to allow the bids to be compared.</span></span>  
10. <span data-ttu-id="b32fa-122">Ange ett nummer i fältet Intervall till.</span><span class="sxs-lookup"><span data-stu-id="b32fa-122">In the Range to field, enter a number.</span></span>
11. <span data-ttu-id="b32fa-123">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="b32fa-123">Click New.</span></span>
12. <span data-ttu-id="b32fa-124">Skriv ett värde i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="b32fa-124">In the Name field, type a value.</span></span>
13. <span data-ttu-id="b32fa-125">Ange ett värde i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="b32fa-125">In the Description field, type a value.</span></span>
14. <span data-ttu-id="b32fa-126">Ange ett nummer i fältet Intervall från.</span><span class="sxs-lookup"><span data-stu-id="b32fa-126">In the Range from field, enter a number.</span></span>
15. <span data-ttu-id="b32fa-127">Ange ett nummer i fältet Intervall till.</span><span class="sxs-lookup"><span data-stu-id="b32fa-127">In the Range to field, enter a number.</span></span>


