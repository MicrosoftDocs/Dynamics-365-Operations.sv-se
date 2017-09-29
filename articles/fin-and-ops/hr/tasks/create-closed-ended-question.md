--- 
title: "Skapa en stängd avslutad fråga"
description: "Med stängda frågor kan du ange alternativ som den svarande kan välja mellan."
author: kherr75
manager: AnnBe
ms.date: 06/10/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Operations
ms.search.region: Global
ms.author: kherr
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 59f1af68e4b1198894a7cdab291021de9f3cf8a9
ms.contentlocale: sv-se
ms.lasthandoff: 08/29/2017

---
# <a name="create-a-closed-ended-question"></a><span data-ttu-id="91106-103">Skapa en stängd avslutad fråga</span><span class="sxs-lookup"><span data-stu-id="91106-103">Create a closed ended question</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="91106-104">Med stängda frågor kan du ange alternativ som den svarande kan välja mellan.</span><span class="sxs-lookup"><span data-stu-id="91106-104">Closed-ended questions allow you to provide options for the respondent to choose from.</span></span> <span data-ttu-id="91106-105">Först måste du skapa svarsgruppen med svaren och sedan skapa frågan som använder svarsgruppen.</span><span class="sxs-lookup"><span data-stu-id="91106-105">First, you need to create the Answer group with the answers, then create the question that will use the answer group.</span></span> <span data-ttu-id="91106-106">Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF.</span><span class="sxs-lookup"><span data-stu-id="91106-106">The demo data company used to create this procedure is USMF.</span></span>


## <a name="create-an-answer-group"></a><span data-ttu-id="91106-107">Skapa en svarsgrupp</span><span class="sxs-lookup"><span data-stu-id="91106-107">Create an answer group</span></span>
1. <span data-ttu-id="91106-108">Gå till Enkät > Design > Svarsgrupper.</span><span class="sxs-lookup"><span data-stu-id="91106-108">Go to Questionnaire > Design > Answer groups.</span></span>
2. <span data-ttu-id="91106-109">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="91106-109">Click New.</span></span>
3. <span data-ttu-id="91106-110">Skriv ett värde i fältet Svarsgrupp.</span><span class="sxs-lookup"><span data-stu-id="91106-110">In the Answer group field, type a value.</span></span>
4. <span data-ttu-id="91106-111">Ange ett värde i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="91106-111">In the Description field, type a value.</span></span>
    * <span data-ttu-id="91106-112">Använd slumpfunktionen för att slumpmässigt placera svaren i en annan ordning varje gång svarsgruppen används för en fråga.</span><span class="sxs-lookup"><span data-stu-id="91106-112">Use the Randomize functionality to randomly place the answers in a different order each time the answer group is used for a question.</span></span>  
5. <span data-ttu-id="91106-113">Klicka på Svar.</span><span class="sxs-lookup"><span data-stu-id="91106-113">Click Answer.</span></span>
6. <span data-ttu-id="91106-114">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="91106-114">Click New.</span></span>
    * <span data-ttu-id="91106-115">Sekvensnummerkontrollerar ordern svaren som visas i, om inte Slumpmässigt har valts för svarsgruppen.</span><span class="sxs-lookup"><span data-stu-id="91106-115">Sequence number controls the order in which the answers are displayed, unless Randomize is selected for the Answer group.</span></span>  
    * <span data-ttu-id="91106-116">Poäng kan tilldelas svar för att användas vid poängsättning av enkäten.</span><span class="sxs-lookup"><span data-stu-id="91106-116">Points can be awarded to answers for use in scoring the questionnaire.</span></span>  
7. <span data-ttu-id="91106-117">Välj ett nummer i fältet Poäng.</span><span class="sxs-lookup"><span data-stu-id="91106-117">In the Points field, enter a number.</span></span>
    * <span data-ttu-id="91106-118">Det korrekta svaret kan markeras för att visa att det valda svaret är korrekt.</span><span class="sxs-lookup"><span data-stu-id="91106-118">The correct answer can be marked to indicate that the selected answer is the correct one.</span></span> <span data-ttu-id="91106-119">Detta kan användas för att poängsätta enkäten.</span><span class="sxs-lookup"><span data-stu-id="91106-119">This can be used for scoring the questionnaire.</span></span>  
8. <span data-ttu-id="91106-120">Skriv ett värde i fältet Svar.</span><span class="sxs-lookup"><span data-stu-id="91106-120">In the Answer field, type a value.</span></span>
    * <span data-ttu-id="91106-121">Fortsätt att skapa svarsurvalsalternativ för svarsgruppen.</span><span class="sxs-lookup"><span data-stu-id="91106-121">Continue to create answer selection options for the answer group.</span></span>  
9. <span data-ttu-id="91106-122">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="91106-122">Click New.</span></span>
10. <span data-ttu-id="91106-123">Välj ett nummer i fältet Poäng.</span><span class="sxs-lookup"><span data-stu-id="91106-123">In the Points field, enter a number.</span></span>
11. <span data-ttu-id="91106-124">Skriv ett värde i fältet Svar.</span><span class="sxs-lookup"><span data-stu-id="91106-124">In the Answer field, type a value.</span></span>
12. <span data-ttu-id="91106-125">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="91106-125">Click New.</span></span>
13. <span data-ttu-id="91106-126">Välj ett nummer i fältet Poäng.</span><span class="sxs-lookup"><span data-stu-id="91106-126">In the Points field, enter a number.</span></span>
14. <span data-ttu-id="91106-127">Skriv ett värde i fältet Svar.</span><span class="sxs-lookup"><span data-stu-id="91106-127">In the Answer field, type a value.</span></span>
15. <span data-ttu-id="91106-128">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="91106-128">Click New.</span></span>
16. <span data-ttu-id="91106-129">Välj ett nummer i fältet Poäng.</span><span class="sxs-lookup"><span data-stu-id="91106-129">In the Points field, enter a number.</span></span>
17. <span data-ttu-id="91106-130">Skriv ett värde i fältet Svar.</span><span class="sxs-lookup"><span data-stu-id="91106-130">In the Answer field, type a value.</span></span>
18. <span data-ttu-id="91106-131">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="91106-131">Click New.</span></span>
19. <span data-ttu-id="91106-132">Välj ett nummer i fältet Poäng.</span><span class="sxs-lookup"><span data-stu-id="91106-132">In the Points field, enter a number.</span></span>
20. <span data-ttu-id="91106-133">Skriv ett värde i fältet Svar.</span><span class="sxs-lookup"><span data-stu-id="91106-133">In the Answer field, type a value.</span></span>
21. <span data-ttu-id="91106-134">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="91106-134">Close the page.</span></span>
22. <span data-ttu-id="91106-135">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="91106-135">Close the page.</span></span>

## <a name="create-the-question"></a><span data-ttu-id="91106-136">Skapa frågan</span><span class="sxs-lookup"><span data-stu-id="91106-136">Create the question</span></span>
1. <span data-ttu-id="91106-137">Gå till Enkät > Design > Frågor.</span><span class="sxs-lookup"><span data-stu-id="91106-137">Go to Questionnaire > Design > Questions.</span></span>
2. <span data-ttu-id="91106-138">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="91106-138">Click New.</span></span>
3. <span data-ttu-id="91106-139">Använd fältet Typ för att gruppera relaterade frågor tillsammans.</span><span class="sxs-lookup"><span data-stu-id="91106-139">Use the Type field to group related questions together.</span></span>
    * <span data-ttu-id="91106-140">Du kan använda ange indatatyper för kryssrutan, alternativsknappen eller kombinationsrutan för stängda frågor.</span><span class="sxs-lookup"><span data-stu-id="91106-140">You can use input types of Check box, Alternative button, or Combo box for closed-ended questions.</span></span>  
4. <span data-ttu-id="91106-141">Välj ett alternativ i fältet Indatatyp.</span><span class="sxs-lookup"><span data-stu-id="91106-141">In the Input type field, select an option.</span></span>
5. <span data-ttu-id="91106-142">Ange eller välj ett värde i fältet Svarsgrupper.</span><span class="sxs-lookup"><span data-stu-id="91106-142">In the Answer group field, enter or select a value.</span></span>
6. <span data-ttu-id="91106-143">Skriv ett värde i fältet Text.</span><span class="sxs-lookup"><span data-stu-id="91106-143">In the Text field, type a value.</span></span>


