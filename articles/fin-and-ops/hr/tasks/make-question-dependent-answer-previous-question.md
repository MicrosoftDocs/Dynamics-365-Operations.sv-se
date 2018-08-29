--- 
title: "Skapa frågor beroende av svaret på den föregående frågan"
description: "Med villkorsstyrda frågor kan du ange vilken uppföljningsfråga som ska visas för en svarande, baserat på svaret på föregående fråga."
author: ShylaThompson
manager: AnnBe
ms.date: 02/12/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Operations, Talent
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 1d98cbff30620256c9d13e7b4a90314db150e33e
ms.openlocfilehash: 3e0a6d63a266bf49764c8cdcfd407ff0733ea27c
ms.contentlocale: sv-se
ms.lasthandoff: 08/09/2018

---
# <a name="make-questions-dependent-on-the-answer-of-the-previous-question"></a><span data-ttu-id="f5c04-103">Skapa frågor beroende av svaret på den föregående frågan</span><span class="sxs-lookup"><span data-stu-id="f5c04-103">Make questions dependent on the answer of the previous question</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="f5c04-104">Med villkorsstyrda frågor kan du ange vilken uppföljningsfråga som ska visas för en svarande, baserat på svaret på föregående fråga.</span><span class="sxs-lookup"><span data-stu-id="f5c04-104">Conditional questions allow you to specify what follow-up question will be presented to a respondent, based on the answer to the preceding question.</span></span> <span data-ttu-id="f5c04-105">Om du till exempel frågar "Föredrar du kaffe eller te”, kan en logisk uppföljningsfråga fastställas beroende på om den svarande väljer kaffe eller te som svar.</span><span class="sxs-lookup"><span data-stu-id="f5c04-105">For example, if you ask "Do you prefer coffee or tea," a logical follow-up question can be determined depending on whether the respondent selects coffee or tea as their answer.</span></span> <span data-ttu-id="f5c04-106">Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF.</span><span class="sxs-lookup"><span data-stu-id="f5c04-106">The demo data company used to create this procedure is USMF.</span></span>


## <a name="find-the-existing-questionnaire"></a><span data-ttu-id="f5c04-107">Hitta den befintliga enkäten</span><span class="sxs-lookup"><span data-stu-id="f5c04-107">Find the existing questionnaire</span></span>
1. <span data-ttu-id="f5c04-108">Gå till Enkät > Design > Enkäter.</span><span class="sxs-lookup"><span data-stu-id="f5c04-108">Go to Questionnaire > Design > Questionnaires.</span></span>
2. <span data-ttu-id="f5c04-109">Välj enkäten WorkFH i listan.</span><span class="sxs-lookup"><span data-stu-id="f5c04-109">In the list, select the WorkFH questionnaire.</span></span>

## <a name="add-all-questions-and-sub-questions-to-the-questionnaire"></a><span data-ttu-id="f5c04-110">Lägg till alla frågor och underfrågor till enkäten</span><span class="sxs-lookup"><span data-stu-id="f5c04-110">Add all questions and sub-questions to the Questionnaire</span></span>
1. <span data-ttu-id="f5c04-111">Klicka på Frågor.</span><span class="sxs-lookup"><span data-stu-id="f5c04-111">Click Questions.</span></span>
2. <span data-ttu-id="f5c04-112">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="f5c04-112">Click New.</span></span>
3. <span data-ttu-id="f5c04-113">Välj fråga nummer 00016 i fältet Fråga.</span><span class="sxs-lookup"><span data-stu-id="f5c04-113">In the Question field, select question number 00016.</span></span>
4. <span data-ttu-id="f5c04-114">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="f5c04-114">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="f5c04-115">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="f5c04-115">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="f5c04-116">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="f5c04-116">Click Save.</span></span>
7. <span data-ttu-id="f5c04-117">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="f5c04-117">Close the page.</span></span>

## <a name="set-the-questionnaire-sequence-to-conditional-and-make-the-question-dependent-on-the-appropriate-question"></a><span data-ttu-id="f5c04-118">Ange enkätsekvensen till villkorsstyrd och gör frågan beroende av lämplig fråga</span><span class="sxs-lookup"><span data-stu-id="f5c04-118">Set the Questionnaire Sequence to Conditional and make the question dependent on the appropriate question</span></span>
1. <span data-ttu-id="f5c04-119">Klicka på Redigera.</span><span class="sxs-lookup"><span data-stu-id="f5c04-119">Click Edit.</span></span>
2. <span data-ttu-id="f5c04-120">Expandera avsnittet Inställningar.</span><span class="sxs-lookup"><span data-stu-id="f5c04-120">Expand the Setup section.</span></span>
3. <span data-ttu-id="f5c04-121">Välj "Villkor" i fältet Frågeordning.</span><span class="sxs-lookup"><span data-stu-id="f5c04-121">In the Question order field, select 'Conditional'.</span></span>
4. <span data-ttu-id="f5c04-122">Klicka på Villkorsfråga.</span><span class="sxs-lookup"><span data-stu-id="f5c04-122">Click Conditional question.</span></span>
5. <span data-ttu-id="f5c04-123">Välj ”Frågor\varför du besvarade föregående fråga sätt som du gjorde?" i trädet.</span><span class="sxs-lookup"><span data-stu-id="f5c04-123">In the tree, select 'Questions\Explain why you answered the previous question the way you did?'.</span></span>
6. <span data-ttu-id="f5c04-124">Välj fråga 00009 i fältet Primär fråga</span><span class="sxs-lookup"><span data-stu-id="f5c04-124">In the Primary question field, select question 00009</span></span>
7. <span data-ttu-id="f5c04-125">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="f5c04-125">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="f5c04-126">Ange svarssekvens-ID för det svarsalternativ som du vill göra frågan beroende av i fältet Svar.</span><span class="sxs-lookup"><span data-stu-id="f5c04-126">In the Answer field, enter the answer sequence ID of the answer option you want to make the question dependent on.</span></span> <span data-ttu-id="f5c04-127">Ange till exempel 1 för det första svarsalternativet.</span><span class="sxs-lookup"><span data-stu-id="f5c04-127">For example, enter 1 for the first answer option.</span></span>
9. <span data-ttu-id="f5c04-128">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="f5c04-128">Click Save.</span></span>
10. <span data-ttu-id="f5c04-129">Välj "Frågor\Jag betalas rättvist för det arbete jag gör” i trädet.</span><span class="sxs-lookup"><span data-stu-id="f5c04-129">In the tree, select 'Questions\I am paid fairly for the work I do.'.</span></span>
    * <span data-ttu-id="f5c04-130">Observera att frågeträdet har uppdateras för att visa beroendet.</span><span class="sxs-lookup"><span data-stu-id="f5c04-130">Note that the question tree updated to show the dependency.</span></span>  


