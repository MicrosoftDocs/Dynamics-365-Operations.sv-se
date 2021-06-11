---
title: Distribuera en enkät med hjälp av tidsplanering
description: Enkättidsplanering gör att du kan planera och distribuera enkäter till flera svaranden.
author: andreabichsel
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: KMKnowledgeCollectorPlanningTable, KMKnowledgeCollectorPlanningMulti, SysQueryForm, HcmPersonLookup, KMKnowledgeCollectorPlanning, HcmLearningWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 952048ce0a2ac94be70d7bde0dc52610f19151ed
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/18/2021
ms.locfileid: "6056310"
---
# <a name="distribute-questionnaires-using-scheduling"></a><span data-ttu-id="2077d-103">Distribuera en enkät med hjälp av tidsplanering</span><span class="sxs-lookup"><span data-stu-id="2077d-103">Distribute questionnaires using scheduling</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="2077d-104">Enkättidsplanering gör att du kan planera och distribuera enkäter till flera svaranden.</span><span class="sxs-lookup"><span data-stu-id="2077d-104">Questionnaire scheduling allows you to plan and distribute questionnaires to multiple respondents.</span></span> <span data-ttu-id="2077d-105">Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF.</span><span class="sxs-lookup"><span data-stu-id="2077d-105">The demo data company used to create this procedure is USMF.</span></span>

## <a name="create-a-questionnaire-schedule"></a><span data-ttu-id="2077d-106">Skapa en tidsplan för enkäter</span><span class="sxs-lookup"><span data-stu-id="2077d-106">Create a questionnaire schedule</span></span>

1. <span data-ttu-id="2077d-107">Gå till Enkät > Distribuera > Tidsplaner för enkät.</span><span class="sxs-lookup"><span data-stu-id="2077d-107">Go to Questionnaire > Distribute > Questionnaire schedules.</span></span>

2. <span data-ttu-id="2077d-108">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="2077d-108">Click New.</span></span>

3. <span data-ttu-id="2077d-109">Ange ett värde i fältet Tidsplanering.</span><span class="sxs-lookup"><span data-stu-id="2077d-109">In the Scheduling field, type a value.</span></span>

4. <span data-ttu-id="2077d-110">Ange ett värde i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="2077d-110">In the Description field, type a value.</span></span>
    * <span data-ttu-id="2077d-111">Ställ in schemat till Anonymt, om svaren ska registreras utan tillhörande namn till svaret.</span><span class="sxs-lookup"><span data-stu-id="2077d-111">Set the schedule to Anonymous if the responses should be recorded without names associated to the response.</span></span>  
    * <span data-ttu-id="2077d-112">Om du vill tillåta anonyma resultat måste detta ställas in bland personalparametrarna först.</span><span class="sxs-lookup"><span data-stu-id="2077d-112">Allowing anonymous results must be set up in the HR parameters first.</span></span>  

5. <span data-ttu-id="2077d-113">Välj planeringstypen i fältet Typ.</span><span class="sxs-lookup"><span data-stu-id="2077d-113">In the Type field, select the planning type.</span></span>  <span data-ttu-id="2077d-114">I detta exempel använder vi nöjdhetstypen.</span><span class="sxs-lookup"><span data-stu-id="2077d-114">In this example we will use the Satisfaction type.</span></span>

6. <span data-ttu-id="2077d-115">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="2077d-115">In the list, find and select the desired record.</span></span>

7. <span data-ttu-id="2077d-116">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="2077d-116">In the list, click the link in the selected row.</span></span>

8. <span data-ttu-id="2077d-117">Ange ett datum i fältet Datum.</span><span class="sxs-lookup"><span data-stu-id="2077d-117">In the Date field, enter a date.</span></span>

9. <span data-ttu-id="2077d-118">Expandera avsnittet Email for employee self service section.</span><span class="sxs-lookup"><span data-stu-id="2077d-118">Expand the Email for employee self service section.</span></span>

10. <span data-ttu-id="2077d-119">Skriv ett värde i fältet Ämne.</span><span class="sxs-lookup"><span data-stu-id="2077d-119">In the Subject field, type a value.</span></span>

    * <span data-ttu-id="2077d-120">Exempel: Enkät tillgänglig</span><span class="sxs-lookup"><span data-stu-id="2077d-120">Example: Questionnaire available</span></span>  

11. <span data-ttu-id="2077d-121">I textrutan skriver du brödtexten i ditt e-postmeddelande.</span><span class="sxs-lookup"><span data-stu-id="2077d-121">In the Text field, type the body of your email message.</span></span> <span data-ttu-id="2077d-122">Notera att variabeln kan användas för att byta ut värdena i systemet.</span><span class="sxs-lookup"><span data-stu-id="2077d-122">Note, the variable can be used to substitue values in the system.</span></span>

    * <span data-ttu-id="2077d-123">Exempel: Bästa %P%, vänligen logga in på Självbetjäning för medarbetare för att slutföra personalhälsoenkäten.</span><span class="sxs-lookup"><span data-stu-id="2077d-123">Example: Dear %P%, Please log in to Employee Self Service to complete the Workforce Health questionnaire.</span></span>  <span data-ttu-id="2077d-124">Contoso</span><span class="sxs-lookup"><span data-stu-id="2077d-124">Contoso</span></span>  

12. <span data-ttu-id="2077d-125">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="2077d-125">Click Save.</span></span>

## <a name="use-the-setup-details-to-select-the-questionnaires-to-be-answered-as-well-as-any-queries-to-use-to-select-respondents"></a><span data-ttu-id="2077d-126">Använd inställningsinformationen för att välja den/de enkät(er) som ska besvaras, samt alla eventuella frågor som ska användas för att välja svarande.</span><span class="sxs-lookup"><span data-stu-id="2077d-126">Use the Setup details to select the questionnaire(s) to be answered as well as any queries to use to select respondents.</span></span>

1. <span data-ttu-id="2077d-127">Klicka på Inställningsdetaljer.</span><span class="sxs-lookup"><span data-stu-id="2077d-127">Click Setup details.</span></span>

2. <span data-ttu-id="2077d-128">I listan väljer du en fråga att använda för att söka igenom systemet efter svarande till enkäten.</span><span class="sxs-lookup"><span data-stu-id="2077d-128">In the list, select a query to use to search the system for respondents for the questionnaire.</span></span>

    * <span data-ttu-id="2077d-129">Exempel: Arbetare</span><span class="sxs-lookup"><span data-stu-id="2077d-129">Example: Workers</span></span>  

3. <span data-ttu-id="2077d-130">Klicka på Visa eller ändra frågan, om du vill välja specifika personer eller justera frågan för att hitta personer som uppfyller vissa villkor.</span><span class="sxs-lookup"><span data-stu-id="2077d-130">Click View or modify query to select specific people or adjust the query to find people who match specific criteria.</span></span>

    * <span data-ttu-id="2077d-131">Observera att alla svaranden även måste vara användare i systemet.</span><span class="sxs-lookup"><span data-stu-id="2077d-131">Note that all respondents must also be users in the system.</span></span>  

4. <span data-ttu-id="2077d-132">Markera raden för Person i listan.</span><span class="sxs-lookup"><span data-stu-id="2077d-132">In the list, mark the row for Person</span></span>

5. <span data-ttu-id="2077d-133">Ange eller välj ett värde i fältet Kriterier.</span><span class="sxs-lookup"><span data-stu-id="2077d-133">In the Criteria field, enter or select a value.</span></span>

    * <span data-ttu-id="2077d-134">Välj Julia Funderburk</span><span class="sxs-lookup"><span data-stu-id="2077d-134">Select Julia Funderburk</span></span>  

6. <span data-ttu-id="2077d-135">I listan väljer du Julia Funderburk</span><span class="sxs-lookup"><span data-stu-id="2077d-135">In the list, select Julia Funderburk</span></span>

7. <span data-ttu-id="2077d-136">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="2077d-136">Click OK.</span></span>

8. <span data-ttu-id="2077d-137">Klicka på fliken Enkät.</span><span class="sxs-lookup"><span data-stu-id="2077d-137">Click the Questionnaires tab.</span></span>

9. <span data-ttu-id="2077d-138">Expandera "the node for the questionnaire type Satisfaction Survey" i trädet.</span><span class="sxs-lookup"><span data-stu-id="2077d-138">In the tree, expand 'the node for the questionnaire type Satisfaction Survey'.</span></span>

10. <span data-ttu-id="2077d-139">Kontrollera "Workforce Health Assessment" i trädet.</span><span class="sxs-lookup"><span data-stu-id="2077d-139">In the tree, check 'Workforce Health Assessment'.</span></span>

11. <span data-ttu-id="2077d-140">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="2077d-140">Click OK.</span></span>

12. <span data-ttu-id="2077d-141">Klicka på Planerad svarsomgång.</span><span class="sxs-lookup"><span data-stu-id="2077d-141">Click Planned answer session.</span></span>

    * <span data-ttu-id="2077d-142">Observera att Planerade svarsomgångar har skapats för varje vald/tillfrågad användare.</span><span class="sxs-lookup"><span data-stu-id="2077d-142">Note that Planned answer sessions have been created for each selected/queried user.</span></span>  

13. <span data-ttu-id="2077d-143">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="2077d-143">Close the page.</span></span>

## <a name="start-the-questionnaire-schedule-in-order-to-make-the-questionnaire-available-for-respondents-to-complete"></a><span data-ttu-id="2077d-144">Starta enkättidsplanen om du vill göra enkäten tillgänglig för de svarande att fylla i.</span><span class="sxs-lookup"><span data-stu-id="2077d-144">Start the questionnaire schedule in order to make the questionnaire available for respondents to complete.</span></span>

1. <span data-ttu-id="2077d-145">Klicka på Funktioner.</span><span class="sxs-lookup"><span data-stu-id="2077d-145">Click Functions.</span></span>

2. <span data-ttu-id="2077d-146">Klicka på Start.</span><span class="sxs-lookup"><span data-stu-id="2077d-146">Click Start.</span></span>

3. <span data-ttu-id="2077d-147">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="2077d-147">Click OK.</span></span>

## <a name="send-the-email-to-inform-respondents-of-the-available-questionnaire"></a><span data-ttu-id="2077d-148">Skicka e-postmeddelandet som informerar de svarande om den tillgängliga enkäten.</span><span class="sxs-lookup"><span data-stu-id="2077d-148">Send the email to inform respondents of the available questionnaire.</span></span>

1. <span data-ttu-id="2077d-149">Klicka på Funktioner.</span><span class="sxs-lookup"><span data-stu-id="2077d-149">Click Functions.</span></span>

2. <span data-ttu-id="2077d-150">Klicka på Send email.</span><span class="sxs-lookup"><span data-stu-id="2077d-150">Click Send email.</span></span>

3. <span data-ttu-id="2077d-151">Klicka på Avbryt.</span><span class="sxs-lookup"><span data-stu-id="2077d-151">Click Cancel.</span></span>

## <a name="use-planned-answer-sessions-to-monitor-who-needs-to-complete-the-questionnaire"></a><span data-ttu-id="2077d-152">Använd "Planned answer sessions" för att övervaka vem som måste fylla i enkäten.</span><span class="sxs-lookup"><span data-stu-id="2077d-152">Use Planned answer sessions to monitor who needs to complete the questionnaire.</span></span>

1. <span data-ttu-id="2077d-153">Klicka på Planerad svarsomgång.</span><span class="sxs-lookup"><span data-stu-id="2077d-153">Click Planned answer session.</span></span>

    * <span data-ttu-id="2077d-154">Ta bort alla återstående planerade svarsomgångar när du är klar att avsluta den schemalagda sessionen.</span><span class="sxs-lookup"><span data-stu-id="2077d-154">Delete any remaining planned answer session when you're ready to end the scheduled session.</span></span>  

2. <span data-ttu-id="2077d-155">Klicka på Ta bort.</span><span class="sxs-lookup"><span data-stu-id="2077d-155">Click Delete.</span></span>

3. <span data-ttu-id="2077d-156">Klicka på Ja.</span><span class="sxs-lookup"><span data-stu-id="2077d-156">Click Yes.</span></span>

4. <span data-ttu-id="2077d-157">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="2077d-157">Close the page.</span></span>

## <a name="end-the-schedule-when-all-respondents-have-completed-the-questionnaire-andor-all-remaining-planned-answer-sessions-have-been-deleted"></a><span data-ttu-id="2077d-158">Avsluta tidsplaneringen när alla svarande har fyllt i enkäten och/eller alla återstående planerade svarsomgångar har raderats.</span><span class="sxs-lookup"><span data-stu-id="2077d-158">End the schedule when all respondents have completed the questionnaire and/or all remaining Planned answer sessions have been deleted.</span></span>

1. <span data-ttu-id="2077d-159">Klicka på Funktioner.</span><span class="sxs-lookup"><span data-stu-id="2077d-159">Click Functions.</span></span>
2. <span data-ttu-id="2077d-160">Klicka på Slut.</span><span class="sxs-lookup"><span data-stu-id="2077d-160">Click End.</span></span>
3. <span data-ttu-id="2077d-161">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="2077d-161">Click OK.</span></span>



[!INCLUDE[footer-include](../includes/footer-banner.md)]