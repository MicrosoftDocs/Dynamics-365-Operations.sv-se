---
title: Skapa en fråga beroende av svaret på den föregående frågan
description: Med villkorsstyrda frågor kan du ange vilken uppföljningsfråga som ska visas för en svarande, baserat på svaret på föregående fråga.
author: andreabichsel
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KMCollection, KMCollectionQuestion, KMCollectionQuestionTree
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a6e49814212b69a618fc3d855b7e290e6b6ff303
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/03/2020
ms.locfileid: "3010675"
---
# <a name="make-a-question-dependent-on-the-answer-of-the-previous-question"></a><span data-ttu-id="09c9a-103">Skapa en fråga beroende av svaret på den föregående frågan</span><span class="sxs-lookup"><span data-stu-id="09c9a-103">Make a question dependent on the answer of the previous question</span></span>



<span data-ttu-id="09c9a-104">Med villkorsstyrda frågor kan du ange vilken uppföljningsfråga som ska visas för en svarande, baserat på svaret på föregående fråga.</span><span class="sxs-lookup"><span data-stu-id="09c9a-104">Conditional questions allow you to specify what follow-up question will be presented to a respondent, based on the answer to the preceding question.</span></span> <span data-ttu-id="09c9a-105">Om du till exempel frågar "Föredrar du kaffe eller te”, kan en logisk uppföljningsfråga fastställas beroende på om den svarande väljer kaffe eller te som svar.</span><span class="sxs-lookup"><span data-stu-id="09c9a-105">For example, if you ask "Do you prefer coffee or tea," a logical follow-up question can be determined depending on whether the respondent selects coffee or tea as their answer.</span></span> <span data-ttu-id="09c9a-106">Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF.</span><span class="sxs-lookup"><span data-stu-id="09c9a-106">The demo data company used to create this procedure is USMF.</span></span>


## <a name="find-the-existing-questionnaire"></a><span data-ttu-id="09c9a-107">Hitta den befintliga enkäten</span><span class="sxs-lookup"><span data-stu-id="09c9a-107">Find the existing questionnaire</span></span>
1. <span data-ttu-id="09c9a-108">Gå till Enkät > Design > Enkäter.</span><span class="sxs-lookup"><span data-stu-id="09c9a-108">Go to Questionnaire > Design > Questionnaires.</span></span>
2. <span data-ttu-id="09c9a-109">Välj enkäten WorkFH i listan.</span><span class="sxs-lookup"><span data-stu-id="09c9a-109">In the list, select the WorkFH questionnaire.</span></span>

## <a name="add-all-questions-and-sub-questions-to-the-questionnaire"></a><span data-ttu-id="09c9a-110">Lägg till alla frågor och underfrågor till enkäten</span><span class="sxs-lookup"><span data-stu-id="09c9a-110">Add all questions and sub-questions to the Questionnaire</span></span>
1. <span data-ttu-id="09c9a-111">Klicka på Frågor.</span><span class="sxs-lookup"><span data-stu-id="09c9a-111">Click Questions.</span></span>
2. <span data-ttu-id="09c9a-112">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="09c9a-112">Click New.</span></span>
3. <span data-ttu-id="09c9a-113">Välj fråga nummer 00016 i fältet Fråga.</span><span class="sxs-lookup"><span data-stu-id="09c9a-113">In the Question field, select question number 00016.</span></span>
4. <span data-ttu-id="09c9a-114">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="09c9a-114">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="09c9a-115">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="09c9a-115">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="09c9a-116">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="09c9a-116">Click Save.</span></span>
7. <span data-ttu-id="09c9a-117">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="09c9a-117">Close the page.</span></span>

## <a name="set-the-questionnaire-sequence-to-conditional-and-make-the-question-dependent-on-the-appropriate-question"></a><span data-ttu-id="09c9a-118">Ange enkätsekvensen till villkorsstyrd och gör frågan beroende av lämplig fråga</span><span class="sxs-lookup"><span data-stu-id="09c9a-118">Set the Questionnaire Sequence to Conditional and make the question dependent on the appropriate question</span></span>
1. <span data-ttu-id="09c9a-119">Klicka på Redigera.</span><span class="sxs-lookup"><span data-stu-id="09c9a-119">Click Edit.</span></span>
2. <span data-ttu-id="09c9a-120">Expandera avsnittet Inställningar.</span><span class="sxs-lookup"><span data-stu-id="09c9a-120">Expand the Setup section.</span></span>
3. <span data-ttu-id="09c9a-121">Välj "Villkor" i fältet Frågeordning.</span><span class="sxs-lookup"><span data-stu-id="09c9a-121">In the Question order field, select 'Conditional'.</span></span>
4. <span data-ttu-id="09c9a-122">Klicka på Villkorsfråga.</span><span class="sxs-lookup"><span data-stu-id="09c9a-122">Click Conditional question.</span></span>
5. <span data-ttu-id="09c9a-123">Välj ”Frågor\varför du besvarade föregående fråga sätt som du gjorde?" i trädet.</span><span class="sxs-lookup"><span data-stu-id="09c9a-123">In the tree, select 'Questions\Explain why you answered the previous question the way you did?'.</span></span>
6. <span data-ttu-id="09c9a-124">Välj fråga 00009 i fältet Primär fråga</span><span class="sxs-lookup"><span data-stu-id="09c9a-124">In the Primary question field, select question 00009</span></span>
7. <span data-ttu-id="09c9a-125">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="09c9a-125">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="09c9a-126">Ange svarssekvens-ID för det svarsalternativ som du vill göra frågan beroende av i fältet Svar.</span><span class="sxs-lookup"><span data-stu-id="09c9a-126">In the Answer field, enter the answer sequence ID of the answer option you want to make the question dependent on.</span></span> <span data-ttu-id="09c9a-127">Ange till exempel 1 för det första svarsalternativet.</span><span class="sxs-lookup"><span data-stu-id="09c9a-127">For example, enter 1 for the first answer option.</span></span>
9. <span data-ttu-id="09c9a-128">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="09c9a-128">Click Save.</span></span>
10. <span data-ttu-id="09c9a-129">Välj "Frågor\Jag betalas rättvist för det arbete jag gör” i trädet.</span><span class="sxs-lookup"><span data-stu-id="09c9a-129">In the tree, select 'Questions\I am paid fairly for the work I do.'.</span></span>
    * <span data-ttu-id="09c9a-130">Observera att frågeträdet har uppdateras för att visa beroendet.</span><span class="sxs-lookup"><span data-stu-id="09c9a-130">Note that the question tree updated to show the dependency.</span></span>  

