---
title: Skapa begäranstyper och göra poängvillkor för anbudsförfrågan
description: I den här handboken visas hur du skapar en typ av begäran och associerar med en poängmetod.
author: mkirknel
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchRFQSolicitationType, PurchRFQCaseTableListPage, PurchCreateRFQCase, PurchRFQCaseTable, PurchRFQScoringRFQCaseCriteria, PurchRFQScoringCriteriaCopy
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 14fd7d0bfa17427883f97c5e0a72044016d4965e
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2019
ms.locfileid: "344626"
---
# <a name="create-solicitation-types-and-scoring-criteria-for-rfqs"></a><span data-ttu-id="e1285-103">Skapa begäranstyper och göra poängvillkor för anbudsförfrågan</span><span class="sxs-lookup"><span data-stu-id="e1285-103">Create solicitation types and scoring criteria for RFQs</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="e1285-104">I den här handboken visas hur du skapar en typ av begäran och associerar med en poängmetod.</span><span class="sxs-lookup"><span data-stu-id="e1285-104">This guide shows you how to create a solicitation type and associate this with a scoring method.</span></span> <span data-ttu-id="e1285-105">Den visar även hur du använder typen av begäran på en anbudsförfrågan som sedan anger standardpoängmetoden.</span><span class="sxs-lookup"><span data-stu-id="e1285-105">It also shows how to use the solicitation type on a request for quotation (RFQ) which then sets the default scoring method.</span></span> <span data-ttu-id="e1285-106">Dessa uppgifter utförs vanligtvis av en inköpschef.</span><span class="sxs-lookup"><span data-stu-id="e1285-106">These tasks would typically be carried out by a purchasing manager.</span></span> <span data-ttu-id="e1285-107">Du kan använda den här proceduren i demonstrationsföretaget USMF eller på dina egna data.</span><span class="sxs-lookup"><span data-stu-id="e1285-107">You can use this procedure in demo data company USMF or on your own data.</span></span> <span data-ttu-id="e1285-108">Du behöver ha en tillgänglig poängmetod innan du börjar.</span><span class="sxs-lookup"><span data-stu-id="e1285-108">You need to have a scoring method available before you start.</span></span>


## <a name="create-a-solicitation-type"></a><span data-ttu-id="e1285-109">Skapa en typ av begäran</span><span class="sxs-lookup"><span data-stu-id="e1285-109">Create a solicitation type</span></span>
1. <span data-ttu-id="e1285-110">Gå till Anskaffning och källa > Inställning > Anbudsförfrågan > Begärantyp.</span><span class="sxs-lookup"><span data-stu-id="e1285-110">Go to Procurement and sourcing > Setup > Request for quotation > Solicitation type.</span></span>
2. <span data-ttu-id="e1285-111">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="e1285-111">Click New.</span></span>
3. <span data-ttu-id="e1285-112">Skriv ett värde i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="e1285-112">In the Name field, type a value.</span></span>
4. <span data-ttu-id="e1285-113">Ange ett värde i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="e1285-113">In the Description field, type a value.</span></span>
5. <span data-ttu-id="e1285-114">Välj den poängmetod du vill använda för den här typen av begäran i fältet Poängmetod.</span><span class="sxs-lookup"><span data-stu-id="e1285-114">In the Scoring method field, select the scoring method that you want to use for this solicitation type.</span></span>
6. <span data-ttu-id="e1285-115">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="e1285-115">Click Save.</span></span>
7. <span data-ttu-id="e1285-116">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="e1285-116">Close the page.</span></span>

## <a name="use-the-solicitation-type"></a><span data-ttu-id="e1285-117">Använd typen av begäran</span><span class="sxs-lookup"><span data-stu-id="e1285-117">Use the solicitation type</span></span>
1. <span data-ttu-id="e1285-118">Gå till Anskaffning och källa > Anbudsförfrågningar > Alla anbudsförfrågningar.</span><span class="sxs-lookup"><span data-stu-id="e1285-118">Go to Procurement and sourcing > Requests for quotations > All requests for quotations.</span></span>
2. <span data-ttu-id="e1285-119">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="e1285-119">Click New.</span></span>
3. <span data-ttu-id="e1285-120">Välj typen av begäran som du nyss skapat i fältet Typ av begäran.</span><span class="sxs-lookup"><span data-stu-id="e1285-120">In the Solicitation type field, select the solicitation type that you have just created.</span></span> 
    *   
4. <span data-ttu-id="e1285-121">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="e1285-121">Click OK.</span></span>
5. <span data-ttu-id="e1285-122">Klicka på Poängkriterier.</span><span class="sxs-lookup"><span data-stu-id="e1285-122">Click Scoring criteria.</span></span>
    * <span data-ttu-id="e1285-123">Poängkriterierna som visas är de från den poängmetod som du har associerat med typen av begäran.</span><span class="sxs-lookup"><span data-stu-id="e1285-123">The scoring criteria that are shown are the ones from the scoring method that you associated with the solicitation type.</span></span> <span data-ttu-id="e1285-124">Du kan välja att lägga till eller ta bort kriterier på den här sidan.</span><span class="sxs-lookup"><span data-stu-id="e1285-124">You can choose to add or delete criteria on this page.</span></span> <span data-ttu-id="e1285-125">Det går också att lägga till nya kriterier, genom att kopiera dem från andra poängmetoder.</span><span class="sxs-lookup"><span data-stu-id="e1285-125">It's also possible to add new criteria by copying them from other scoring methods.</span></span>  
6. <span data-ttu-id="e1285-126">Klicka på Kopiera kriterier.</span><span class="sxs-lookup"><span data-stu-id="e1285-126">Click Copy criteria.</span></span>
7. <span data-ttu-id="e1285-127">Ange eller välj ett värde i fältet Poängmetod.</span><span class="sxs-lookup"><span data-stu-id="e1285-127">In the Scoring method field, enter or select a value.</span></span>
8. <span data-ttu-id="e1285-128">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="e1285-128">Click OK.</span></span>
9. <span data-ttu-id="e1285-129">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="e1285-129">Close the page.</span></span>

