---
title: "Distribuera och slutföra en enkät"
description: "Den här artikeln beskriver hur du fördelar de enkäter som du utformar så att de blir tillgängliga för den person eller grupp som ska fylla i dem."
author: kherr75
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
ms.search.form: KMConnectionType, KMKnowledgeCollectorPlanningTabel, SysEmailParameters
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Core, Operations, Talent
ms.custom: 17424
ms.assetid: fd8d867a-2446-400a-b91f-ad4085427470
ms.search.region: Global
ms.author: kherr
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: ea07d8e91c94d9fdad4c2d05533981e254420188
ms.openlocfilehash: 3954ec2a06c7a2ec964b656e088f8c677094c963
ms.contentlocale: sv-se
ms.lasthandoff: 02/07/2018

---

# <a name="distribute-and-complete-a-questionnaire"></a><span data-ttu-id="efa2e-103">Distribuera och slutföra en enkät</span><span class="sxs-lookup"><span data-stu-id="efa2e-103">Distribute and complete a questionnaire</span></span>

[!include[banner](includes/banner.md)]


<span data-ttu-id="efa2e-104">Den här artikeln beskriver hur du fördelar de enkäter som du utformar så att de blir tillgängliga för den person eller grupp som ska fylla i dem.</span><span class="sxs-lookup"><span data-stu-id="efa2e-104">This topic explains how distribute the questionnaires that you design, so that they are available to the person or group of people who will complete them.</span></span> 

<span data-ttu-id="efa2e-105">Det finns flera sätt att distribuera en enkät:</span><span class="sxs-lookup"><span data-stu-id="efa2e-105">There are multiple ways to distribute a questionnaire:</span></span>

-   <span data-ttu-id="efa2e-106">Markera enkäten som aktiv.</span><span class="sxs-lookup"><span data-stu-id="efa2e-106">Mark the questionnaire as active.</span></span> <span data-ttu-id="efa2e-107">Enkäten är då tillgänglig för alla medarbetare, om inte en enkätgrupp har ställts in för att begränsa åtkomst till den.</span><span class="sxs-lookup"><span data-stu-id="efa2e-107">The questionnaire is then available to all employees, unless a questionnaire group is set up to restrict access to it.</span></span>
-   <span data-ttu-id="efa2e-108">Tilldela rättigheter till en enkätgrupp.</span><span class="sxs-lookup"><span data-stu-id="efa2e-108">Assign rights to a questionnaire group.</span></span> <span data-ttu-id="efa2e-109">Enkäten är då tillgänglig för alla medlemmar i den valda gruppen.</span><span class="sxs-lookup"><span data-stu-id="efa2e-109">The questionnaire is then available to all members of the selected group.</span></span>
-   <span data-ttu-id="efa2e-110">Skapa planerade svarsomgångar.</span><span class="sxs-lookup"><span data-stu-id="efa2e-110">Create planned answer sessions.</span></span> <span data-ttu-id="efa2e-111">Enkäten är då endast tillgänglig för en viss person.</span><span class="sxs-lookup"><span data-stu-id="efa2e-111">The questionnaire is then available only to a particular person.</span></span>
-   <span data-ttu-id="efa2e-112">Skapa en tidsplan.</span><span class="sxs-lookup"><span data-stu-id="efa2e-112">Create a schedule.</span></span> <span data-ttu-id="efa2e-113">Enkäten kan sedan vara tillgänglig för flera personer.</span><span class="sxs-lookup"><span data-stu-id="efa2e-113">The questionnaire can then be available to multiple people.</span></span>

## <a name="marking-a-questionnaire-as-active"></a><span data-ttu-id="efa2e-114">Markera en enkät som aktiv.</span><span class="sxs-lookup"><span data-stu-id="efa2e-114">Marking a questionnaire as active</span></span>
<span data-ttu-id="efa2e-115">Genom att ange fältet **Aktiv** som **Ja** på sidan **Enkäter** kan du göra enkäten tillgänglig för alla medarbetare.</span><span class="sxs-lookup"><span data-stu-id="efa2e-115">By setting the **Active** field to **Yes** on the **Questionnaires** page, you make the questionnaire available for all employees to complete.</span></span> <span data-ttu-id="efa2e-116">De svarande kan fylla i formuläret flera gånger.</span><span class="sxs-lookup"><span data-stu-id="efa2e-116">Respondents can complete the questionnaire multiple times.</span></span> <span data-ttu-id="efa2e-117">Denna funktion är användbar om du vill samla in feedback kontinuerligt under hela året.</span><span class="sxs-lookup"><span data-stu-id="efa2e-117">This functionality is useful if you want to gather continual feedback throughout the year.</span></span> <span data-ttu-id="efa2e-118">Du kan till exempel göra en enkät där anställda ger feedback om lunchtjänsten i kafeterian.</span><span class="sxs-lookup"><span data-stu-id="efa2e-118">For example, you can make a questionnaire that employees use to give feedback about the lunch service in the cafeteria.</span></span>

## <a name="questionnaire-groups"></a><span data-ttu-id="efa2e-119">Enkätgrupper</span><span class="sxs-lookup"><span data-stu-id="efa2e-119">Questionnaire groups</span></span>
<span data-ttu-id="efa2e-120">Du kan ställa in enkätgrupper och sedan inkludera de svarande som ett frågeformulär ska distribueras till.</span><span class="sxs-lookup"><span data-stu-id="efa2e-120">You can set up questionnaire groups and then include the respondents that a questionnaire should be distributed to.</span></span> 

<span data-ttu-id="efa2e-121">Du kan skapa enkätgrupper på följande sidor:</span><span class="sxs-lookup"><span data-stu-id="efa2e-121">You can create questionnaire groups from the following pages:</span></span>

-   <span data-ttu-id="efa2e-122">**Enkätgrupper**– Endast personer i en enkätgrupp kan avsluta en vald enkät.</span><span class="sxs-lookup"><span data-stu-id="efa2e-122">**Questionnaire groups** – Only individuals in a questionnaire group can complete a selected questionnaire.</span></span> <span data-ttu-id="efa2e-123">Till exempel om din målgrupp är leverantörer, då skapar du en enkätgrupp som är specifik för dessa svarande.</span><span class="sxs-lookup"><span data-stu-id="efa2e-123">For example, your intended audience is contractors, so you create a questionnaire group that is specific to those respondents.</span></span>
-   <span data-ttu-id="efa2e-124">**Enkätgruppsmedlemmar** – Du kan lägga till kontakter till enkätgrupperna.</span><span class="sxs-lookup"><span data-stu-id="efa2e-124">**Questionnaire group members** – You can add people to the questionnaire groups.</span></span>

<span data-ttu-id="efa2e-125">På sidan **Enkäter** klickar du på **Användarrättigheter** för att tilldela en enkätgrupp till en enkät.</span><span class="sxs-lookup"><span data-stu-id="efa2e-125">To assign a questionnaire group to a questionnaire, on the **Questionnaires** page, click **User rights**.</span></span> <span data-ttu-id="efa2e-126">Medlemmarna i enkätgruppen kan fylla i enkäten när enkäten har sparats som aktiv.</span><span class="sxs-lookup"><span data-stu-id="efa2e-126">After the questionnaire is saved as active, the members of the questionnaire group can complete the questionnaire.</span></span> <span data-ttu-id="efa2e-127">Denna funktion är användbar om du vill testa en enkät i en utvald grupp användare innan du skickar ut den till en större grupp, eller om du vill rikta enkäten till en mycket specifik målgrupp.</span><span class="sxs-lookup"><span data-stu-id="efa2e-127">This functionality is helpful if you want to test a questionnaire on a select group of people before you roll it out to a larger group, or if you want to target a questionnaire to a very specific audience.</span></span>

## <a name="planned-answer-sessions-in-a-questionnaire"></a><span data-ttu-id="efa2e-128">Planerade svarsomgångar i en enkät</span><span class="sxs-lookup"><span data-stu-id="efa2e-128">Planned answer sessions in a questionnaire</span></span>
<span data-ttu-id="efa2e-129">Planerade svarsomgångar är enkäter som du har utformat för och valt svarande till.</span><span class="sxs-lookup"><span data-stu-id="efa2e-129">Planned answer sessions are questionnaires that you've designed and selected the respondents for.</span></span> 

> <span data-ttu-id="efa2e-130">**Anm.:** Innan du kan ställa in planerade svarsomgångar måste du utforma en enkät.</span><span class="sxs-lookup"><span data-stu-id="efa2e-130">**Note** Before you can set up planned answer sessions, you must design a questionnaire.</span></span> 

<span data-ttu-id="efa2e-131">På sidan **Planerad svarsomgång** kan du skapa en planerad svarsomgång för en enskild medarbetare.</span><span class="sxs-lookup"><span data-stu-id="efa2e-131">On the **Planned answer session** page, you can create a planned answer session for an individual employee.</span></span> <span data-ttu-id="efa2e-132">Listan på sidan visar alla planerade enkäter.</span><span class="sxs-lookup"><span data-stu-id="efa2e-132">The list on the page displays all planned questionnaires.</span></span> 

<span data-ttu-id="efa2e-133">Planerade svarsomgångar används också på sidan **Tidsplaner för enkäter** där du kan planera enkäter för flera personer:</span><span class="sxs-lookup"><span data-stu-id="efa2e-133">Planned answer sessions are also used on the **Questionnaire schedules** page, where you can plan questionnaires for multiple people:</span></span>

-   <span data-ttu-id="efa2e-134">Medarbetare</span><span class="sxs-lookup"><span data-stu-id="efa2e-134">Employees</span></span>
-   <span data-ttu-id="efa2e-135">Kursdeltagare</span><span class="sxs-lookup"><span data-stu-id="efa2e-135">Course participants</span></span>
-   <span data-ttu-id="efa2e-136">Organisationsenheter</span><span class="sxs-lookup"><span data-stu-id="efa2e-136">Organizational units</span></span>

<span data-ttu-id="efa2e-137">Varje person får besvara enkäten en gång.</span><span class="sxs-lookup"><span data-stu-id="efa2e-137">Each person can answer the questionnaire only one time.</span></span>

## <a name="scheduling-a-questionnaire"></a><span data-ttu-id="efa2e-138">Tidsplanera en enkät</span><span class="sxs-lookup"><span data-stu-id="efa2e-138">Scheduling a questionnaire</span></span>
<span data-ttu-id="efa2e-139">Det går även att tidsplanera en enkät för flera svarande.</span><span class="sxs-lookup"><span data-stu-id="efa2e-139">You can optionally schedule a questionnaire for multiple respondents.</span></span>

### <a name="planning-types"></a><span data-ttu-id="efa2e-140">Planeringstyper</span><span class="sxs-lookup"><span data-stu-id="efa2e-140">Planning types</span></span>

<span data-ttu-id="efa2e-141">Planeringstyper krävs om du vill schemalägga planerade svarsomgångar för flera svarande.</span><span class="sxs-lookup"><span data-stu-id="efa2e-141">Planning types are required if you want to schedule planned answer sessions for multiple respondents.</span></span> <span data-ttu-id="efa2e-142">Planeringstyper används för att klassificera enkättidsplaner.</span><span class="sxs-lookup"><span data-stu-id="efa2e-142">Planning types are used to classify questionnaire schedules.</span></span> <span data-ttu-id="efa2e-143">Du kan till exempel tidsplanera enkäter för följande syften:</span><span class="sxs-lookup"><span data-stu-id="efa2e-143">For example, you can schedule questionnaires for the following purposes:</span></span>

-   <span data-ttu-id="efa2e-144">Utvärdering</span><span class="sxs-lookup"><span data-stu-id="efa2e-144">Evaluation</span></span>
-   <span data-ttu-id="efa2e-145">Översikt</span><span class="sxs-lookup"><span data-stu-id="efa2e-145">Survey</span></span>
-   <span data-ttu-id="efa2e-146">Testa</span><span class="sxs-lookup"><span data-stu-id="efa2e-146">Testing</span></span>

<span data-ttu-id="efa2e-147">Du kan ange planeringstyper för en enkät på sidan **Tidsplaner för enkäter** .</span><span class="sxs-lookup"><span data-stu-id="efa2e-147">You can specify planning types for a questionnaire schedule on the **Questionnaire schedules** page.</span></span>

### <a name="reference-types-for-questionnaire"></a><span data-ttu-id="efa2e-148">Referenstyper för enkät</span><span class="sxs-lookup"><span data-stu-id="efa2e-148">Reference types for questionnaire</span></span>

<span data-ttu-id="efa2e-149">Du kan använda referenstyper när du vill ställa in kriterier för svarande som du kan välja när du tidsplanerar en enkät.</span><span class="sxs-lookup"><span data-stu-id="efa2e-149">You can use reference types to enter criteria for the respondents that you might select when you schedule a questionnaire.</span></span> 

<span data-ttu-id="efa2e-150">Använd sidan **Referenstyper** för att ställa in referenstyper för en enkät.</span><span class="sxs-lookup"><span data-stu-id="efa2e-150">Use the **Reference types** page to set up reference types for a questionnaire.</span></span> <span data-ttu-id="efa2e-151">Varje referenstyp motsvarar en tabell i Microsoft Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="efa2e-151">Each reference type corresponds to a table in Microsoft Dynamics 365 for Finance and Operations.</span></span> <span data-ttu-id="efa2e-152">När du skapar enkättidsplaner kan du ange de enskilda posterna i tabellen eller ett intervall med poster som enkäten ska associeras med.</span><span class="sxs-lookup"><span data-stu-id="efa2e-152">When you create questionnaire schedules, you can specify individual records in the table or a range of records that the questionnaire will be associated with.</span></span> 

<span data-ttu-id="efa2e-153">Om du till exempel väljer tabellen Kurser kan du bestämma vilken specifik kurs enkäten ska gälla för.</span><span class="sxs-lookup"><span data-stu-id="efa2e-153">For example, if you select the Courses table, you can decide which specific course the questionnaire will be for.</span></span> <span data-ttu-id="efa2e-154">När du ställer in en referens för tabellen Kurser blir alla fält och knappar på sidan **Kurser** tillgängliga.</span><span class="sxs-lookup"><span data-stu-id="efa2e-154">When you set up a reference for the Courses table, some fields and buttons on the **Courses** page become available.</span></span>

### <a name="questionnaire-schedules"></a><span data-ttu-id="efa2e-155">Tidsplaner för enkäter</span><span class="sxs-lookup"><span data-stu-id="efa2e-155">Questionnaire schedules</span></span>

<span data-ttu-id="efa2e-156">Du kan använda enkättidsplaner för att generera flera planerade svarsomgångar för ett antal användare, baserat på en referenstyp.</span><span class="sxs-lookup"><span data-stu-id="efa2e-156">You can use questionnaire schedules to generate multiple planned answer sessions for a group of users, based on a reference type.</span></span> <span data-ttu-id="efa2e-157">Skapa ett schema på sidan **Enkättidsplaner**.</span><span class="sxs-lookup"><span data-stu-id="efa2e-157">Create a schedule on the **Questionnaire schedules** page.</span></span> <span data-ttu-id="efa2e-158">Välj planeringstyp för att kategorisera schemat, och välj även den referenstyp som ska användas för att ställa frågor i systemet för enskilda användare.</span><span class="sxs-lookup"><span data-stu-id="efa2e-158">Select the planning type to categorize the schedule, and also select the reference type that should be used to query the system for specific users.</span></span> <span data-ttu-id="efa2e-159">Om du anger referenstypen som tabellen Kurser, kan du exempelvis välja en viss kurs i fältet **Referens**.</span><span class="sxs-lookup"><span data-stu-id="efa2e-159">For example, if you set the reference type to the Courses table, you can select a specific course in the **Reference** field.</span></span> 

<span data-ttu-id="efa2e-160">Klicka på **Inställningsdetaljer** om du vill välja enkäten och andra kriterier.</span><span class="sxs-lookup"><span data-stu-id="efa2e-160">Click **Setup details** to select the questionnaire and other criteria.</span></span> <span data-ttu-id="efa2e-161">Ange exempelvis namnet på läraren som ett kriterium om enkäten utgör en utvärdering av instruktören.</span><span class="sxs-lookup"><span data-stu-id="efa2e-161">For example, specify the instructor's name as a criterion if the questionnaire is an evaluation of the instructor.</span></span> <span data-ttu-id="efa2e-162">När du är klar med att ange inställningsinformationen, genererar systemet planerade svarsomgångar för de användare som deltar i enkäten.</span><span class="sxs-lookup"><span data-stu-id="efa2e-162">After you've finished entering the setup details, the system generates planned answer sessions for the users that are included in the query.</span></span> 

<span data-ttu-id="efa2e-163">Klicka på **Planerade svarsomgångar** om du vill visa svarsomgången för tidsplanen.</span><span class="sxs-lookup"><span data-stu-id="efa2e-163">Click **Planned answer sessions** to view the answer sessions for the schedule.</span></span> <span data-ttu-id="efa2e-164">Därefter kan du manuellt skapa ytterligare planerade svarsomgångar eller ta bort planerade svarsomgångar som inte har besvarats.</span><span class="sxs-lookup"><span data-stu-id="efa2e-164">You can then manually create additional planned answer sessions or delete planned answer sessions that haven't been answered.</span></span> 

<span data-ttu-id="efa2e-165">Klicka på **Funktioner** &gt; **Start** för att göra enkäten tillgänglig för användarna i relaterade planerade svarsomgångar.</span><span class="sxs-lookup"><span data-stu-id="efa2e-165">Click **Functions** &gt; **Start** to make the questionnaire available to the users in related planned answer sessions.</span></span> <span data-ttu-id="efa2e-166">Klicka på **Svar** om du vill visa de ifyllda svaren på enkäten.</span><span class="sxs-lookup"><span data-stu-id="efa2e-166">Click **Answers** to view the completed responses to the questionnaire.</span></span> <span data-ttu-id="efa2e-167">Du kan också kopiera enkätens tidsplaninställningar, planerade svarsomgångar och svaren till en ny enkättidsplan.</span><span class="sxs-lookup"><span data-stu-id="efa2e-167">You can optionally copy the questionnaire schedule settings, planned answer sessions, and answers to a new questionnaire schedule.</span></span>

## <a name="notifying-respondents-about-questionnaires-that-are-available-to-them"></a><span data-ttu-id="efa2e-168">Meddela svarande om enkäter som är tillgängliga för dem</span><span class="sxs-lookup"><span data-stu-id="efa2e-168">Notifying respondents about questionnaires that are available to them</span></span>
<span data-ttu-id="efa2e-169">När du distribuerar en enkät måste du meddela svarande att enkäter finns tillgängliga för dem.</span><span class="sxs-lookup"><span data-stu-id="efa2e-169">When you distribute a questionnaire, you must notify respondents that questionnaires are available to them.</span></span> 

### <a name="notifying-respondents-about-a-planned-answer-session"></a><span data-ttu-id="efa2e-170">Meddela svarande om en planerad svarsomgång</span><span class="sxs-lookup"><span data-stu-id="efa2e-170">Notifying respondents about a planned answer session</span></span>

<span data-ttu-id="efa2e-171">Om du använder en planerad svarsomgång måste du meddela personen direkt, till exempel per telefon eller e-post.</span><span class="sxs-lookup"><span data-stu-id="efa2e-171">If you use a planned answer session, you must notify the person directly, such as by telephone or email.</span></span>

### <a name="notifying-respondents-about-a-scheduling"></a><span data-ttu-id="efa2e-172">Meddela svarande om en planering</span><span class="sxs-lookup"><span data-stu-id="efa2e-172">Notifying respondents about a scheduling</span></span>

<span data-ttu-id="efa2e-173">Använd sidan **Tidsplaner för enkäter** för att förbereda och skicka ett e-postmeddelande till alla svarande som är kopplade till enkäten.</span><span class="sxs-lookup"><span data-stu-id="efa2e-173">Use the **Questionnaire schedules** page to prepare and send email to all respondents who are assigned to the questionnaire.</span></span> <span data-ttu-id="efa2e-174">Ange e-posttexten på fliken **E-postadress för självbetjäning för medarbetare**. När schemat har startats klickar du på **Funktioner** &gt; **Skicka e-post** för att generera och skicka mailet till mottagarna.</span><span class="sxs-lookup"><span data-stu-id="efa2e-174">Enter the email text on the **E-mail for employee self service** tab. After the schedule has been started, click **Functions** &gt; **Send e-mail** to generate and send the email to the respondents.</span></span> <span data-ttu-id="efa2e-175">De svarande kan sedan logga in på webbplatsen och fylla i enkäten.</span><span class="sxs-lookup"><span data-stu-id="efa2e-175">Respondents can then sign in to the website and complete the questionnaire.</span></span> 

> <span data-ttu-id="efa2e-176">**Anm.:** Innan du kan använda e-postfunktionen måste din IT-administratör ange e-postinställningarna på sidan **E-postparametrar**.</span><span class="sxs-lookup"><span data-stu-id="efa2e-176">**Note** Before you can use the email functionality, your IT administrator must enter the email settings on the **E-mail parameters** page.</span></span>

## <a name="ending-a-scheduled-questionnaire"></a><span data-ttu-id="efa2e-177">Avsluta en tidsplanerad enkät</span><span class="sxs-lookup"><span data-stu-id="efa2e-177">Ending a scheduled questionnaire</span></span>
<span data-ttu-id="efa2e-178">Du kan avsluta en tidsplanerad enkät när alla svaranden har avslutat sina tilldelade svarsomgångar.</span><span class="sxs-lookup"><span data-stu-id="efa2e-178">You can end a scheduled questionnaire after all respondents have completed their assigned answer sessions.</span></span> <span data-ttu-id="efa2e-179">När planerad enkät slutförs kan du inte kopiera inställningarna till en ny tidsplan.</span><span class="sxs-lookup"><span data-stu-id="efa2e-179">After a scheduled questionnaire is ended, you can't copy its settings to a new schedule.</span></span> 

> <span data-ttu-id="efa2e-180">**Anm.:** Om en eller flera svarande inte har fyllt i enkäten och du fortfarande vill avsluta tidsplanen måste du först radera dessa svarande från listan på sidan **Planerad svarsomgång**.</span><span class="sxs-lookup"><span data-stu-id="efa2e-180">**Note** If one or more respondents haven't completed the questionnaire, but you still want to end the scheduling, you must first delete those respondents from the list on the **Planned answer session** page.</span></span> <span data-ttu-id="efa2e-181">Sedan kan du avsluta tidsplanen.</span><span class="sxs-lookup"><span data-stu-id="efa2e-181">You can then end the schedule.</span></span>

## <a name="completing-questionnaires"></a><span data-ttu-id="efa2e-182">Fylla i enkäter</span><span class="sxs-lookup"><span data-stu-id="efa2e-182">Completing questionnaires</span></span>
<span data-ttu-id="efa2e-183">När du har utformat och har fördelat en enkät kan den besvaras av valda svarande.</span><span class="sxs-lookup"><span data-stu-id="efa2e-183">After you've designed and distributed a questionnaire, the questionnaire can be completed by selected respondents.</span></span> <span data-ttu-id="efa2e-184">Du kan fylla i de tillgängliga frågeformulären från två platser:</span><span class="sxs-lookup"><span data-stu-id="efa2e-184">You can complete the questionnaires that are available to you from two locations:</span></span>

-   <span data-ttu-id="efa2e-185">I navigeringsfönstret klickar du på **Enkäter** &gt; **Fördela** &gt; **Fyll i en enkät**.</span><span class="sxs-lookup"><span data-stu-id="efa2e-185">In the navigation pane, click **Questionnaires** &gt; **Distribute** &gt; **Complete a questionnaire**.</span></span>
-   <span data-ttu-id="efa2e-186">Klicka på **Enkäter att fylla i** i Medarbetarsjälvbetjäning.</span><span class="sxs-lookup"><span data-stu-id="efa2e-186">In Employee self-service, click **Questionnaires to complete**.</span></span>

<span data-ttu-id="efa2e-187">Enkäter kan göras tillgängliga för vissa användare eller grupper av användare eller för alla användare i ett nätverk.</span><span class="sxs-lookup"><span data-stu-id="efa2e-187">Questionnaires can made be available to specific users or groups of users, or to all users in a network.</span></span>

<a name="see-also"></a><span data-ttu-id="efa2e-188">Se även</span><span class="sxs-lookup"><span data-stu-id="efa2e-188">See also</span></span>
--------

[<span data-ttu-id="efa2e-189">Utforma enkäter</span><span class="sxs-lookup"><span data-stu-id="efa2e-189">Designing questionnaires</span></span>](design-questionnaires.md)

[<span data-ttu-id="efa2e-190">Använda enkäter</span><span class="sxs-lookup"><span data-stu-id="efa2e-190">Using questionnaires</span></span>](questionnaires.md)

[<span data-ttu-id="efa2e-191">Visa och utvärdera resultaten av en enkät</span><span class="sxs-lookup"><span data-stu-id="efa2e-191">Viewing and evaluating the results of questionnaires</span></span>](evaluate-questionnaire-results.md)



