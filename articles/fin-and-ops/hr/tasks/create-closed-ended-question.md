---
title: Skapa en stängd avslutad fråga
description: Med stängda frågor kan du ange alternativ som den svarande kan välja mellan.
author: kherr75
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KMAnswerCollection, KMAnswer, KMQuestion
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kherr
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 6b08988a3872cec39b7592732d23862e959aae79
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2019
ms.locfileid: "332275"
---
# <a name="create-a-closed-ended-question"></a><span data-ttu-id="208a9-103">Skapa en stängd avslutad fråga</span><span class="sxs-lookup"><span data-stu-id="208a9-103">Create a closed ended question</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="208a9-104">Med stängda frågor kan du ange alternativ som den svarande kan välja mellan.</span><span class="sxs-lookup"><span data-stu-id="208a9-104">Closed-ended questions allow you to provide options for the respondent to choose from.</span></span> <span data-ttu-id="208a9-105">Först måste du skapa svarsgruppen med svaren och sedan skapa frågan som använder svarsgruppen.</span><span class="sxs-lookup"><span data-stu-id="208a9-105">First, you need to create the Answer group with the answers, then create the question that will use the answer group.</span></span> <span data-ttu-id="208a9-106">Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF.</span><span class="sxs-lookup"><span data-stu-id="208a9-106">The demo data company used to create this procedure is USMF.</span></span>


## <a name="create-an-answer-group"></a><span data-ttu-id="208a9-107">Skapa en svarsgrupp</span><span class="sxs-lookup"><span data-stu-id="208a9-107">Create an answer group</span></span>
1. <span data-ttu-id="208a9-108">Gå till Enkät > Design > Svarsgrupper.</span><span class="sxs-lookup"><span data-stu-id="208a9-108">Go to Questionnaire > Design > Answer groups.</span></span>
2. <span data-ttu-id="208a9-109">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="208a9-109">Click New.</span></span>
3. <span data-ttu-id="208a9-110">Skriv ett värde i fältet Svarsgrupp.</span><span class="sxs-lookup"><span data-stu-id="208a9-110">In the Answer group field, type a value.</span></span>
4. <span data-ttu-id="208a9-111">Ange ett värde i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="208a9-111">In the Description field, type a value.</span></span>
    * <span data-ttu-id="208a9-112">Använd slumpfunktionen för att slumpmässigt placera svaren i en annan ordning varje gång svarsgruppen används för en fråga.</span><span class="sxs-lookup"><span data-stu-id="208a9-112">Use the Randomize functionality to randomly place the answers in a different order each time the answer group is used for a question.</span></span>  
5. <span data-ttu-id="208a9-113">Klicka på Svar.</span><span class="sxs-lookup"><span data-stu-id="208a9-113">Click Answer.</span></span>
6. <span data-ttu-id="208a9-114">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="208a9-114">Click New.</span></span>
    * <span data-ttu-id="208a9-115">Sekvensnummerkontrollerar ordern svaren som visas i, om inte Slumpmässigt har valts för svarsgruppen.</span><span class="sxs-lookup"><span data-stu-id="208a9-115">Sequence number controls the order in which the answers are displayed, unless Randomize is selected for the Answer group.</span></span>  
    * <span data-ttu-id="208a9-116">Poäng kan tilldelas svar för att användas vid poängsättning av enkäten.</span><span class="sxs-lookup"><span data-stu-id="208a9-116">Points can be awarded to answers for use in scoring the questionnaire.</span></span>  
7. <span data-ttu-id="208a9-117">Välj ett nummer i fältet Poäng.</span><span class="sxs-lookup"><span data-stu-id="208a9-117">In the Points field, enter a number.</span></span>
    * <span data-ttu-id="208a9-118">Det korrekta svaret kan markeras för att visa att det valda svaret är korrekt.</span><span class="sxs-lookup"><span data-stu-id="208a9-118">The correct answer can be marked to indicate that the selected answer is the correct one.</span></span> <span data-ttu-id="208a9-119">Detta kan användas för att poängsätta enkäten.</span><span class="sxs-lookup"><span data-stu-id="208a9-119">This can be used for scoring the questionnaire.</span></span>  
8. <span data-ttu-id="208a9-120">Skriv ett värde i fältet Svar.</span><span class="sxs-lookup"><span data-stu-id="208a9-120">In the Answer field, type a value.</span></span>
    * <span data-ttu-id="208a9-121">Fortsätt att skapa svarsurvalsalternativ för svarsgruppen.</span><span class="sxs-lookup"><span data-stu-id="208a9-121">Continue to create answer selection options for the answer group.</span></span>  
9. <span data-ttu-id="208a9-122">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="208a9-122">Click New.</span></span>
10. <span data-ttu-id="208a9-123">Välj ett nummer i fältet Poäng.</span><span class="sxs-lookup"><span data-stu-id="208a9-123">In the Points field, enter a number.</span></span>
11. <span data-ttu-id="208a9-124">Skriv ett värde i fältet Svar.</span><span class="sxs-lookup"><span data-stu-id="208a9-124">In the Answer field, type a value.</span></span>
12. <span data-ttu-id="208a9-125">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="208a9-125">Click New.</span></span>
13. <span data-ttu-id="208a9-126">Välj ett nummer i fältet Poäng.</span><span class="sxs-lookup"><span data-stu-id="208a9-126">In the Points field, enter a number.</span></span>
14. <span data-ttu-id="208a9-127">Skriv ett värde i fältet Svar.</span><span class="sxs-lookup"><span data-stu-id="208a9-127">In the Answer field, type a value.</span></span>
15. <span data-ttu-id="208a9-128">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="208a9-128">Click New.</span></span>
16. <span data-ttu-id="208a9-129">Välj ett nummer i fältet Poäng.</span><span class="sxs-lookup"><span data-stu-id="208a9-129">In the Points field, enter a number.</span></span>
17. <span data-ttu-id="208a9-130">Skriv ett värde i fältet Svar.</span><span class="sxs-lookup"><span data-stu-id="208a9-130">In the Answer field, type a value.</span></span>
18. <span data-ttu-id="208a9-131">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="208a9-131">Click New.</span></span>
19. <span data-ttu-id="208a9-132">Välj ett nummer i fältet Poäng.</span><span class="sxs-lookup"><span data-stu-id="208a9-132">In the Points field, enter a number.</span></span>
20. <span data-ttu-id="208a9-133">Skriv ett värde i fältet Svar.</span><span class="sxs-lookup"><span data-stu-id="208a9-133">In the Answer field, type a value.</span></span>
21. <span data-ttu-id="208a9-134">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="208a9-134">Close the page.</span></span>
22. <span data-ttu-id="208a9-135">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="208a9-135">Close the page.</span></span>

## <a name="create-the-question"></a><span data-ttu-id="208a9-136">Skapa frågan</span><span class="sxs-lookup"><span data-stu-id="208a9-136">Create the question</span></span>
1. <span data-ttu-id="208a9-137">Gå till Enkät > Design > Frågor.</span><span class="sxs-lookup"><span data-stu-id="208a9-137">Go to Questionnaire > Design > Questions.</span></span>
2. <span data-ttu-id="208a9-138">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="208a9-138">Click New.</span></span>
3. <span data-ttu-id="208a9-139">Använd fältet Typ för att gruppera relaterade frågor tillsammans.</span><span class="sxs-lookup"><span data-stu-id="208a9-139">Use the Type field to group related questions together.</span></span>
    * <span data-ttu-id="208a9-140">Du kan använda ange indatatyper för kryssrutan, alternativsknappen eller kombinationsrutan för stängda frågor.</span><span class="sxs-lookup"><span data-stu-id="208a9-140">You can use input types of Check box, Alternative button, or Combo box for closed-ended questions.</span></span>  
4. <span data-ttu-id="208a9-141">Välj ett alternativ i fältet Indatatyp.</span><span class="sxs-lookup"><span data-stu-id="208a9-141">In the Input type field, select an option.</span></span>
5. <span data-ttu-id="208a9-142">Ange eller välj ett värde i fältet Svarsgrupper.</span><span class="sxs-lookup"><span data-stu-id="208a9-142">In the Answer group field, enter or select a value.</span></span>
6. <span data-ttu-id="208a9-143">Skriv ett värde i fältet Text.</span><span class="sxs-lookup"><span data-stu-id="208a9-143">In the Text field, type a value.</span></span>

