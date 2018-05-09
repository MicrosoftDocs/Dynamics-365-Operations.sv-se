--- 
title: "Skapa begäranstyper och göra poängvillkor för anbudsförfrågan"
description: "I den här handboken visas hur du skapar en typ av begäran och associerar med en poängmetod."
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
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 6876f8ed0f69ec5a34c4c9671081c76245945b1e
ms.contentlocale: sv-se
ms.lasthandoff: 05/08/2018

---
# <a name="create-solicitation-types-and-scoring-criteria-for-rfqs"></a><span data-ttu-id="289f1-103">Skapa begäranstyper och göra poängvillkor för anbudsförfrågan</span><span class="sxs-lookup"><span data-stu-id="289f1-103">Create solicitation types and scoring criteria for RFQs</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="289f1-104">I den här handboken visas hur du skapar en typ av begäran och associerar med en poängmetod.</span><span class="sxs-lookup"><span data-stu-id="289f1-104">This guide shows you how to create a solicitation type and associate this with a scoring method.</span></span> <span data-ttu-id="289f1-105">Den visar även hur du använder typen av begäran på en anbudsförfrågan som sedan anger standardpoängmetoden.</span><span class="sxs-lookup"><span data-stu-id="289f1-105">It also shows how to use the solicitation type on a request for quotation (RFQ) which then sets the default scoring method.</span></span> <span data-ttu-id="289f1-106">Dessa uppgifter utförs vanligtvis av en inköpschef.</span><span class="sxs-lookup"><span data-stu-id="289f1-106">These tasks would typically be carried out by a purchasing manager.</span></span> <span data-ttu-id="289f1-107">Du kan använda den här proceduren i demonstrationsföretaget USMF eller på dina egna data.</span><span class="sxs-lookup"><span data-stu-id="289f1-107">You can use this procedure in demo data company USMF or on your own data.</span></span> <span data-ttu-id="289f1-108">Du behöver ha en tillgänglig poängmetod innan du börjar.</span><span class="sxs-lookup"><span data-stu-id="289f1-108">You need to have a scoring method available before you start.</span></span>


## <a name="create-a-solicitation-type"></a><span data-ttu-id="289f1-109">Skapa en typ av begäran</span><span class="sxs-lookup"><span data-stu-id="289f1-109">Create a solicitation type</span></span>
1. <span data-ttu-id="289f1-110">Gå till Anskaffning och källa > Inställning > Anbudsförfrågan > Begärantyp.</span><span class="sxs-lookup"><span data-stu-id="289f1-110">Go to Procurement and sourcing > Setup > Request for quotation > Solicitation type.</span></span>
2. <span data-ttu-id="289f1-111">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="289f1-111">Click New.</span></span>
3. <span data-ttu-id="289f1-112">Skriv ett värde i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="289f1-112">In the Name field, type a value.</span></span>
4. <span data-ttu-id="289f1-113">Ange ett värde i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="289f1-113">In the Description field, type a value.</span></span>
5. <span data-ttu-id="289f1-114">Välj den poängmetod du vill använda för den här typen av begäran i fältet Poängmetod.</span><span class="sxs-lookup"><span data-stu-id="289f1-114">In the Scoring method field, select the scoring method that you want to use for this solicitation type.</span></span>
6. <span data-ttu-id="289f1-115">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="289f1-115">Click Save.</span></span>
7. <span data-ttu-id="289f1-116">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="289f1-116">Close the page.</span></span>

## <a name="use-the-solicitation-type"></a><span data-ttu-id="289f1-117">Använd typen av begäran</span><span class="sxs-lookup"><span data-stu-id="289f1-117">Use the solicitation type</span></span>
1. <span data-ttu-id="289f1-118">Gå till Anskaffning och källa > Anbudsförfrågningar > Alla anbudsförfrågningar.</span><span class="sxs-lookup"><span data-stu-id="289f1-118">Go to Procurement and sourcing > Requests for quotations > All requests for quotations.</span></span>
2. <span data-ttu-id="289f1-119">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="289f1-119">Click New.</span></span>
3. <span data-ttu-id="289f1-120">Välj typen av begäran som du nyss skapat i fältet Typ av begäran.</span><span class="sxs-lookup"><span data-stu-id="289f1-120">In the Solicitation type field, select the solicitation type that you have just created.</span></span> 
4. <span data-ttu-id="289f1-121">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="289f1-121">Click OK.</span></span>
5. <span data-ttu-id="289f1-122">Klicka på Poängkriterier.</span><span class="sxs-lookup"><span data-stu-id="289f1-122">Click Scoring criteria.</span></span>
    * <span data-ttu-id="289f1-123">Poängkriterierna som visas är de från den poängmetod som du har associerat med typen av begäran.</span><span class="sxs-lookup"><span data-stu-id="289f1-123">The scoring criteria that are shown are the ones from the scoring method that you associated with the solicitation type.</span></span> <span data-ttu-id="289f1-124">Du kan välja att lägga till eller ta bort kriterier på den här sidan.</span><span class="sxs-lookup"><span data-stu-id="289f1-124">You can choose to add or delete criteria on this page.</span></span> <span data-ttu-id="289f1-125">Det går också att lägga till nya kriterier, genom att kopiera dem från andra poängmetoder.</span><span class="sxs-lookup"><span data-stu-id="289f1-125">It's also possible to add new criteria by copying them from other scoring methods.</span></span>  
6. <span data-ttu-id="289f1-126">Klicka på Kopiera kriterier.</span><span class="sxs-lookup"><span data-stu-id="289f1-126">Click Copy criteria.</span></span>
7. <span data-ttu-id="289f1-127">Ange eller välj ett värde i fältet Poängmetod.</span><span class="sxs-lookup"><span data-stu-id="289f1-127">In the Scoring method field, enter or select a value.</span></span>
8. <span data-ttu-id="289f1-128">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="289f1-128">Click OK.</span></span>
9. <span data-ttu-id="289f1-129">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="289f1-129">Close the page.</span></span>


