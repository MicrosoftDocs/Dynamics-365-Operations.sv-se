--- 
title: "Distribuera en enkät med hjälp av tidsplanering"
description: "Enkättidsplanering gör att du kan planera och distribuera enkäter till flera svaranden."
author: kherr75
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: KMKnowledgeCollectorPlanningTable, KMKnowledgeCollectorPlanningMulti, SysQueryForm, HcmPersonLookup, KMKnowledgeCollectorPlanning
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kherr
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0312b8cfadd45f8e59225e9daba78b9e216cff51
ms.openlocfilehash: b66389a7d63c51f059a39495b8c7fbd325ef41e8
ms.contentlocale: sv-se
ms.lasthandoff: 09/14/2018

---
# <a name="distribute-questionnaires-using-scheduling"></a><span data-ttu-id="d2d9a-103">Distribuera en enkät med hjälp av tidsplanering</span><span class="sxs-lookup"><span data-stu-id="d2d9a-103">Distribute questionnaires using scheduling</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="d2d9a-104">Enkättidsplanering gör att du kan planera och distribuera enkäter till flera svaranden.</span><span class="sxs-lookup"><span data-stu-id="d2d9a-104">Questionnaire scheduling allows you to plan and distribute questionnaires to multiple respondents.</span></span> <span data-ttu-id="d2d9a-105">Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF.</span><span class="sxs-lookup"><span data-stu-id="d2d9a-105">The demo data company used to create this procedure is USMF.</span></span>


## <a name="create-a-questionnaire-schedule"></a><span data-ttu-id="d2d9a-106">Skapa en tidsplan för enkäter</span><span class="sxs-lookup"><span data-stu-id="d2d9a-106">Create a questionnaire schedule</span></span>
1. <span data-ttu-id="d2d9a-107">Gå till Enkät > Distribuera > Tidsplaner för enkät.</span><span class="sxs-lookup"><span data-stu-id="d2d9a-107">Go to Questionnaire > Distribute > Questionnaire schedules.</span></span>
2. <span data-ttu-id="d2d9a-108">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="d2d9a-108">Click New.</span></span>
3. <span data-ttu-id="d2d9a-109">Ange ett värde i fältet Tidsplanering.</span><span class="sxs-lookup"><span data-stu-id="d2d9a-109">In the Scheduling field, type a value.</span></span>
4. <span data-ttu-id="d2d9a-110">Ange ett värde i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="d2d9a-110">In the Description field, type a value.</span></span>
    * <span data-ttu-id="d2d9a-111">Ställ in schemat till Anonymt, om svaren ska registreras utan tillhörande namn till svaret.</span><span class="sxs-lookup"><span data-stu-id="d2d9a-111">Set the schedule to Anonymous if the responses should be recorded without names associated to the response.</span></span>  
    * <span data-ttu-id="d2d9a-112">Om du vill tillåta anonyma resultat måste detta ställas in bland personalparametrarna först.</span><span class="sxs-lookup"><span data-stu-id="d2d9a-112">Allowing anonymous results must be set up in the HR parameters first.</span></span>  
5. <span data-ttu-id="d2d9a-113">Välj planeringstypen i fältet Typ.</span><span class="sxs-lookup"><span data-stu-id="d2d9a-113">In the Type field, select the planning type.</span></span>  <span data-ttu-id="d2d9a-114">I detta exempel använder vi nöjdhetstypen.</span><span class="sxs-lookup"><span data-stu-id="d2d9a-114">In this example we will use the Satisfaction type.</span></span>
6. <span data-ttu-id="d2d9a-115">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="d2d9a-115">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="d2d9a-116">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="d2d9a-116">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="d2d9a-117">Ange ett datum i fältet Datum.</span><span class="sxs-lookup"><span data-stu-id="d2d9a-117">In the Date field, enter a date.</span></span>
9. <span data-ttu-id="d2d9a-118">Expandera avsnittet Email for employee self service section.</span><span class="sxs-lookup"><span data-stu-id="d2d9a-118">Expand the Email for employee self service section.</span></span>
10. <span data-ttu-id="d2d9a-119">Skriv ett värde i fältet Ämne.</span><span class="sxs-lookup"><span data-stu-id="d2d9a-119">In the Subject field, type a value.</span></span>
    * <span data-ttu-id="d2d9a-120">Exempel: Enkät tillgänglig</span><span class="sxs-lookup"><span data-stu-id="d2d9a-120">Example: Questionnaire available</span></span>  
11. <span data-ttu-id="d2d9a-121">I textrutan skriver du brödtexten i ditt e-postmeddelande.</span><span class="sxs-lookup"><span data-stu-id="d2d9a-121">In the Text field, type the body of your email message.</span></span> <span data-ttu-id="d2d9a-122">Notera att variabeln kan användas för att byta ut värdena i systemet.</span><span class="sxs-lookup"><span data-stu-id="d2d9a-122">Note, the variable can be used to substitue values in the system.</span></span>
    * <span data-ttu-id="d2d9a-123">Exempel: Bästa %P%, vänligen logga in på Employee Self Service för att slutföra personalhälsoenkäten.</span><span class="sxs-lookup"><span data-stu-id="d2d9a-123">Example:   Dear %P%,  Please log in to Employee Self Service to complete the Workforce Health questionnaire.</span></span>  <span data-ttu-id="d2d9a-124">Contoso</span><span class="sxs-lookup"><span data-stu-id="d2d9a-124">Contoso</span></span>  
12. <span data-ttu-id="d2d9a-125">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="d2d9a-125">Click Save.</span></span>

## <a name="use-the-setup-details-to-select-the-questionnaires-to-be-answered-as-well-as-any-queries-to-use-to-select-respondents"></a><span data-ttu-id="d2d9a-126">Använd inställningsinformationen för att välja den/de enkät(er) som ska besvaras, samt alla eventuella frågor som ska användas för att välja svarande.</span><span class="sxs-lookup"><span data-stu-id="d2d9a-126">Use the Setup details to select the questionnaire(s) to be answered as well as any queries to use to select respondents.</span></span>
1. <span data-ttu-id="d2d9a-127">Klicka på Inställningsdetaljer.</span><span class="sxs-lookup"><span data-stu-id="d2d9a-127">Click Setup details.</span></span>
2. <span data-ttu-id="d2d9a-128">I listan väljer du en fråga att använda för att söka igenom systemet efter svarande till enkäten.</span><span class="sxs-lookup"><span data-stu-id="d2d9a-128">In the list, select a query to use to search the system for respondents for the questionnaire.</span></span>
    * <span data-ttu-id="d2d9a-129">Exempel: Arbetare</span><span class="sxs-lookup"><span data-stu-id="d2d9a-129">Example: Workers</span></span>  
3. <span data-ttu-id="d2d9a-130">Klicka på Visa eller ändra frågan, om du vill välja specifika personer eller justera frågan för att hitta personer som uppfyller vissa villkor.</span><span class="sxs-lookup"><span data-stu-id="d2d9a-130">Click View or modify query to select specific people or adjust the query to find people who match specific criteria.</span></span>
    * <span data-ttu-id="d2d9a-131">Observera att alla svaranden även måste vara användare i systemet.</span><span class="sxs-lookup"><span data-stu-id="d2d9a-131">Note that all respondents must also be users in the system.</span></span>  
4. <span data-ttu-id="d2d9a-132">Markera raden för Person i listan.</span><span class="sxs-lookup"><span data-stu-id="d2d9a-132">In the list, mark the row for Person</span></span>
5. <span data-ttu-id="d2d9a-133">Ange eller välj ett värde i fältet Kriterier.</span><span class="sxs-lookup"><span data-stu-id="d2d9a-133">In the Criteria field, enter or select a value.</span></span>
    * <span data-ttu-id="d2d9a-134">Välj Julia Funderburk</span><span class="sxs-lookup"><span data-stu-id="d2d9a-134">Select Julia Funderburk</span></span>  
6. <span data-ttu-id="d2d9a-135">I listan väljer du Julia Funderburk</span><span class="sxs-lookup"><span data-stu-id="d2d9a-135">In the list, select Julia Funderburk</span></span>
7. <span data-ttu-id="d2d9a-136">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="d2d9a-136">Click OK.</span></span>
8. <span data-ttu-id="d2d9a-137">Klicka på fliken Enkät.</span><span class="sxs-lookup"><span data-stu-id="d2d9a-137">Click the Questionnaires tab.</span></span>
9. <span data-ttu-id="d2d9a-138">Expandera "the node for the questionnaire type Satisfaction Survey" i trädet.</span><span class="sxs-lookup"><span data-stu-id="d2d9a-138">In the tree, expand 'the node for the questionnaire type Satisfaction Survey'.</span></span>
10. <span data-ttu-id="d2d9a-139">Kontrollera "Workforce Health Assessment" i trädet.</span><span class="sxs-lookup"><span data-stu-id="d2d9a-139">In the tree, check 'Workforce Health Assessment'.</span></span>
11. <span data-ttu-id="d2d9a-140">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="d2d9a-140">Click OK.</span></span>
12. <span data-ttu-id="d2d9a-141">Klicka på Planerad svarsomgång.</span><span class="sxs-lookup"><span data-stu-id="d2d9a-141">Click Planned answer session.</span></span>
    * <span data-ttu-id="d2d9a-142">Observera att Planerade svarsomgångar har skapats för varje vald/tillfrågad användare.</span><span class="sxs-lookup"><span data-stu-id="d2d9a-142">Note that Planned answer sessions have been created for each selected/queried user.</span></span>  
13. <span data-ttu-id="d2d9a-143">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="d2d9a-143">Close the page.</span></span>

## <a name="start-the-questionnaire-schedule-in-order-to-make-the-questionnaire-available-for-respondents-to-complete"></a><span data-ttu-id="d2d9a-144">Starta enkättidsplanen om du vill göra enkäten tillgänglig för de svarande att fylla i.</span><span class="sxs-lookup"><span data-stu-id="d2d9a-144">Start the questionnaire schedule in order to make the questionnaire available for respondents to complete.</span></span>
1. <span data-ttu-id="d2d9a-145">Klicka på Funktioner.</span><span class="sxs-lookup"><span data-stu-id="d2d9a-145">Click Functions.</span></span>
2. <span data-ttu-id="d2d9a-146">Klicka på Start.</span><span class="sxs-lookup"><span data-stu-id="d2d9a-146">Click Start.</span></span>
3. <span data-ttu-id="d2d9a-147">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="d2d9a-147">Click OK.</span></span>

## <a name="send-the-email-to-inform-respondents-of-the-available-questionnaire"></a><span data-ttu-id="d2d9a-148">Skicka e-postmeddelandet som informerar de svarande om den tillgängliga enkäten.</span><span class="sxs-lookup"><span data-stu-id="d2d9a-148">Send the email to inform respondents of the available questionnaire.</span></span>
1. <span data-ttu-id="d2d9a-149">Klicka på Funktioner.</span><span class="sxs-lookup"><span data-stu-id="d2d9a-149">Click Functions.</span></span>
2. <span data-ttu-id="d2d9a-150">Klicka på Send email.</span><span class="sxs-lookup"><span data-stu-id="d2d9a-150">Click Send email.</span></span>
3. <span data-ttu-id="d2d9a-151">Klicka på Avbryt.</span><span class="sxs-lookup"><span data-stu-id="d2d9a-151">Click Cancel.</span></span>

## <a name="use-planned-answer-sessions-to-monitor-who-needs-to-complete-the-questionnaire"></a><span data-ttu-id="d2d9a-152">Använd "Planned answer sessions" för att övervaka vem som måste fylla i enkäten.</span><span class="sxs-lookup"><span data-stu-id="d2d9a-152">Use Planned answer sessions to monitor who needs to complete the questionnaire.</span></span>
1. <span data-ttu-id="d2d9a-153">Klicka på Planerad svarsomgång.</span><span class="sxs-lookup"><span data-stu-id="d2d9a-153">Click Planned answer session.</span></span>
    * <span data-ttu-id="d2d9a-154">Ta bort alla återstående planerade svarsomgångar när du är klar att avsluta den schemalagda sessionen.</span><span class="sxs-lookup"><span data-stu-id="d2d9a-154">Delete any remaining planned answer session when you're ready to end the scheduled session.</span></span>  
2. <span data-ttu-id="d2d9a-155">Klicka på Ta bort.</span><span class="sxs-lookup"><span data-stu-id="d2d9a-155">Click Delete.</span></span>
3. <span data-ttu-id="d2d9a-156">Klicka på Ja.</span><span class="sxs-lookup"><span data-stu-id="d2d9a-156">Click Yes.</span></span>
4. <span data-ttu-id="d2d9a-157">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="d2d9a-157">Close the page.</span></span>

## <a name="end-the-schedule-when-all-respondents-have-completed-the-questionnaire-andor-all-remaining-planned-answer-sessions-have-been-deleted"></a><span data-ttu-id="d2d9a-158">Avsluta tidsplaneringen när alla svarande har fyllt i enkäten och/eller alla återstående planerade svarsomgångar har raderats.</span><span class="sxs-lookup"><span data-stu-id="d2d9a-158">End the schedule when all respondents have completed the questionnaire and/or all remaining Planned answer sessions have been deleted.</span></span>
1. <span data-ttu-id="d2d9a-159">Klicka på Funktioner.</span><span class="sxs-lookup"><span data-stu-id="d2d9a-159">Click Functions.</span></span>
2. <span data-ttu-id="d2d9a-160">Klicka på Slut.</span><span class="sxs-lookup"><span data-stu-id="d2d9a-160">Click End.</span></span>
3. <span data-ttu-id="d2d9a-161">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="d2d9a-161">Click OK.</span></span>


