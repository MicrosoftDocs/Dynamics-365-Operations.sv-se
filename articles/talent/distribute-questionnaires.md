---
title: Schemalägg och skicka ut enkäter
description: Den här artikeln beskriver hur du fördelar de enkäter som du utformar så att de blir tillgängliga för den person eller grupp som ska fylla i dem.
author: andreabichsel
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: KMConnectionType, KMKnowledgeCollectorPlanningTabel, SysEmailParameters
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations, Talent
ms.custom: 17424
ms.assetid: fd8d867a-2446-400a-b91f-ad4085427470
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 37c9392263e8c113c541b64e8e79853520a13d11
ms.sourcegitcommit: 608e68b603afef9eb98d8fb25e90109c2473ef87
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2019
ms.locfileid: "857971"
---
# <a name="distribute-and-schedule-questionnaires"></a><span data-ttu-id="a6d2a-103">Schemalägg och skicka ut enkäter</span><span class="sxs-lookup"><span data-stu-id="a6d2a-103">Distribute and schedule questionnaires</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="a6d2a-104">Den här artikeln beskriver hur du fördelar de enkäter som du utformar så att de blir tillgängliga för den person eller grupp som ska fylla i dem.</span><span class="sxs-lookup"><span data-stu-id="a6d2a-104">This topic explains how distribute the questionnaires that you design, so that they are available to the person or group of people who will complete them.</span></span> 

<span data-ttu-id="a6d2a-105">Det finns flera sätt att distribuera en enkät:</span><span class="sxs-lookup"><span data-stu-id="a6d2a-105">There are multiple ways to distribute a questionnaire:</span></span>

-   <span data-ttu-id="a6d2a-106">Markera enkäten som aktiv.</span><span class="sxs-lookup"><span data-stu-id="a6d2a-106">Mark the questionnaire as active.</span></span> <span data-ttu-id="a6d2a-107">Enkäten är då tillgänglig för alla medarbetare, om inte en enkätgrupp har ställts in för att begränsa åtkomst till den.</span><span class="sxs-lookup"><span data-stu-id="a6d2a-107">The questionnaire is then available to all employees, unless a questionnaire group is set up to restrict access to it.</span></span>
-   <span data-ttu-id="a6d2a-108">Tilldela rättigheter till en enkätgrupp.</span><span class="sxs-lookup"><span data-stu-id="a6d2a-108">Assign rights to a questionnaire group.</span></span> <span data-ttu-id="a6d2a-109">Enkäten är då tillgänglig för alla medlemmar i den valda gruppen.</span><span class="sxs-lookup"><span data-stu-id="a6d2a-109">The questionnaire is then available to all members of the selected group.</span></span>
-   <span data-ttu-id="a6d2a-110">Skapa planerade svarsomgångar.</span><span class="sxs-lookup"><span data-stu-id="a6d2a-110">Create planned answer sessions.</span></span> <span data-ttu-id="a6d2a-111">Enkäten är då endast tillgänglig för en viss person.</span><span class="sxs-lookup"><span data-stu-id="a6d2a-111">The questionnaire is then available only to a particular person.</span></span>
-   <span data-ttu-id="a6d2a-112">Skapa en tidsplan.</span><span class="sxs-lookup"><span data-stu-id="a6d2a-112">Create a schedule.</span></span> <span data-ttu-id="a6d2a-113">Enkäten kan sedan vara tillgänglig för flera personer.</span><span class="sxs-lookup"><span data-stu-id="a6d2a-113">The questionnaire can then be available to multiple people.</span></span>

## <a name="marking-a-questionnaire-as-active"></a><span data-ttu-id="a6d2a-114">Markera en enkät som aktiv.</span><span class="sxs-lookup"><span data-stu-id="a6d2a-114">Marking a questionnaire as active</span></span>
<span data-ttu-id="a6d2a-115">Genom att ange fältet **Aktiv** som **Ja** på sidan **Enkäter** kan du göra enkäten tillgänglig för alla medarbetare.</span><span class="sxs-lookup"><span data-stu-id="a6d2a-115">By setting the **Active** field to **Yes** on the **Questionnaires** page, you make the questionnaire available for all employees to complete.</span></span> <span data-ttu-id="a6d2a-116">De svarande kan fylla i formuläret flera gånger.</span><span class="sxs-lookup"><span data-stu-id="a6d2a-116">Respondents can complete the questionnaire multiple times.</span></span> <span data-ttu-id="a6d2a-117">Denna funktion är användbar om du vill samla in feedback kontinuerligt under hela året.</span><span class="sxs-lookup"><span data-stu-id="a6d2a-117">This functionality is useful if you want to gather continual feedback throughout the year.</span></span> <span data-ttu-id="a6d2a-118">Du kan till exempel göra en enkät där anställda ger feedback om lunchtjänsten i kafeterian.</span><span class="sxs-lookup"><span data-stu-id="a6d2a-118">For example, you can make a questionnaire that employees use to give feedback about the lunch service in the cafeteria.</span></span>

## <a name="questionnaire-groups"></a><span data-ttu-id="a6d2a-119">Enkätgrupper</span><span class="sxs-lookup"><span data-stu-id="a6d2a-119">Questionnaire groups</span></span>
<span data-ttu-id="a6d2a-120">Du kan ställa in enkätgrupper och sedan inkludera de svarande som ett frågeformulär ska distribueras till.</span><span class="sxs-lookup"><span data-stu-id="a6d2a-120">You can set up questionnaire groups and then include the respondents that a questionnaire should be distributed to.</span></span> 

<span data-ttu-id="a6d2a-121">Du kan skapa enkätgrupper på följande sidor:</span><span class="sxs-lookup"><span data-stu-id="a6d2a-121">You can create questionnaire groups from the following pages:</span></span>

-   <span data-ttu-id="a6d2a-122">**Enkätgrupper**– Endast personer i en enkätgrupp kan avsluta en vald enkät.</span><span class="sxs-lookup"><span data-stu-id="a6d2a-122">**Questionnaire groups** – Only individuals in a questionnaire group can complete a selected questionnaire.</span></span> <span data-ttu-id="a6d2a-123">Till exempel om din målgrupp är leverantörer, då skapar du en enkätgrupp som är specifik för dessa svarande.</span><span class="sxs-lookup"><span data-stu-id="a6d2a-123">For example, your intended audience is contractors, so you create a questionnaire group that is specific to those respondents.</span></span>
-   <span data-ttu-id="a6d2a-124">**Enkätgruppsmedlemmar** – Du kan lägga till kontakter till enkätgrupperna.</span><span class="sxs-lookup"><span data-stu-id="a6d2a-124">**Questionnaire group members** – You can add people to the questionnaire groups.</span></span>

<span data-ttu-id="a6d2a-125">På sidan **Enkäter** klickar du på **Användarrättigheter** för att tilldela en enkätgrupp till en enkät.</span><span class="sxs-lookup"><span data-stu-id="a6d2a-125">To assign a questionnaire group to a questionnaire, on the **Questionnaires** page, click **User rights**.</span></span> <span data-ttu-id="a6d2a-126">Medlemmarna i enkätgruppen kan fylla i enkäten när enkäten har sparats som aktiv.</span><span class="sxs-lookup"><span data-stu-id="a6d2a-126">After the questionnaire is saved as active, the members of the questionnaire group can complete the questionnaire.</span></span> <span data-ttu-id="a6d2a-127">Denna funktion är användbar om du vill testa en enkät i en utvald grupp användare innan du skickar ut den till en större grupp, eller om du vill rikta enkäten till en mycket specifik målgrupp.</span><span class="sxs-lookup"><span data-stu-id="a6d2a-127">This functionality is helpful if you want to test a questionnaire on a select group of people before you roll it out to a larger group, or if you want to target a questionnaire to a very specific audience.</span></span>

## <a name="planned-answer-sessions-in-a-questionnaire"></a><span data-ttu-id="a6d2a-128">Planerade svarsomgångar i en enkät</span><span class="sxs-lookup"><span data-stu-id="a6d2a-128">Planned answer sessions in a questionnaire</span></span>
<span data-ttu-id="a6d2a-129">Planerade svarsomgångar är enkäter som du har utformat för och valt svarande till.</span><span class="sxs-lookup"><span data-stu-id="a6d2a-129">Planned answer sessions are questionnaires that you've designed and selected the respondents for.</span></span> 

> <span data-ttu-id="a6d2a-130">**Anm.:** Innan du kan ställa in planerade svarsomgångar måste du utforma en enkät.</span><span class="sxs-lookup"><span data-stu-id="a6d2a-130">**Note** Before you can set up planned answer sessions, you must design a questionnaire.</span></span> 

<span data-ttu-id="a6d2a-131">På sidan **Planerad svarsomgång** kan du skapa en planerad svarsomgång för en enskild medarbetare.</span><span class="sxs-lookup"><span data-stu-id="a6d2a-131">On the **Planned answer session** page, you can create a planned answer session for an individual employee.</span></span> <span data-ttu-id="a6d2a-132">Listan på sidan visar alla planerade enkäter.</span><span class="sxs-lookup"><span data-stu-id="a6d2a-132">The list on the page displays all planned questionnaires.</span></span> 

<span data-ttu-id="a6d2a-133">Planerade svarsomgångar används också på sidan **Tidsplaner för enkäter** där du kan planera enkäter för flera personer:</span><span class="sxs-lookup"><span data-stu-id="a6d2a-133">Planned answer sessions are also used on the **Questionnaire schedules** page, where you can plan questionnaires for multiple people:</span></span>

-   <span data-ttu-id="a6d2a-134">Medarbetare</span><span class="sxs-lookup"><span data-stu-id="a6d2a-134">Employees</span></span>
-   <span data-ttu-id="a6d2a-135">Kursdeltagare</span><span class="sxs-lookup"><span data-stu-id="a6d2a-135">Course participants</span></span>
-   <span data-ttu-id="a6d2a-136">Organisationsenheter</span><span class="sxs-lookup"><span data-stu-id="a6d2a-136">Organizational units</span></span>

<span data-ttu-id="a6d2a-137">Varje person får besvara enkäten en gång.</span><span class="sxs-lookup"><span data-stu-id="a6d2a-137">Each person can answer the questionnaire only one time.</span></span>

## <a name="scheduling-a-questionnaire"></a><span data-ttu-id="a6d2a-138">Tidsplanera en enkät</span><span class="sxs-lookup"><span data-stu-id="a6d2a-138">Scheduling a questionnaire</span></span>
<span data-ttu-id="a6d2a-139">Det går även att tidsplanera en enkät för flera svarande.</span><span class="sxs-lookup"><span data-stu-id="a6d2a-139">You can optionally schedule a questionnaire for multiple respondents.</span></span>

### <a name="planning-types"></a><span data-ttu-id="a6d2a-140">Planeringstyper</span><span class="sxs-lookup"><span data-stu-id="a6d2a-140">Planning types</span></span>

<span data-ttu-id="a6d2a-141">Planeringstyper krävs om du vill schemalägga planerade svarsomgångar för flera svarande.</span><span class="sxs-lookup"><span data-stu-id="a6d2a-141">Planning types are required if you want to schedule planned answer sessions for multiple respondents.</span></span> <span data-ttu-id="a6d2a-142">Planeringstyper används för att klassificera enkättidsplaner.</span><span class="sxs-lookup"><span data-stu-id="a6d2a-142">Planning types are used to classify questionnaire schedules.</span></span> <span data-ttu-id="a6d2a-143">Du kan till exempel tidsplanera enkäter för följande syften:</span><span class="sxs-lookup"><span data-stu-id="a6d2a-143">For example, you can schedule questionnaires for the following purposes:</span></span>

-   <span data-ttu-id="a6d2a-144">Utvärdering</span><span class="sxs-lookup"><span data-stu-id="a6d2a-144">Evaluation</span></span>
-   <span data-ttu-id="a6d2a-145">Översikt</span><span class="sxs-lookup"><span data-stu-id="a6d2a-145">Survey</span></span>
-   <span data-ttu-id="a6d2a-146">Testa</span><span class="sxs-lookup"><span data-stu-id="a6d2a-146">Testing</span></span>

<span data-ttu-id="a6d2a-147">Du kan ange planeringstyper för en enkät på sidan **Tidsplaner för enkäter** .</span><span class="sxs-lookup"><span data-stu-id="a6d2a-147">You can specify planning types for a questionnaire schedule on the **Questionnaire schedules** page.</span></span>

### <a name="reference-types-for-questionnaire"></a><span data-ttu-id="a6d2a-148">Referenstyper för enkät</span><span class="sxs-lookup"><span data-stu-id="a6d2a-148">Reference types for questionnaire</span></span>

<span data-ttu-id="a6d2a-149">Du kan använda referenstyper när du vill ställa in kriterier för svarande som du kan välja när du tidsplanerar en enkät.</span><span class="sxs-lookup"><span data-stu-id="a6d2a-149">You can use reference types to enter criteria for the respondents that you might select when you schedule a questionnaire.</span></span> 

<span data-ttu-id="a6d2a-150">Använd sidan **Referenstyper** för att ställa in referenstyper för en enkät.</span><span class="sxs-lookup"><span data-stu-id="a6d2a-150">Use the **Reference types** page to set up reference types for a questionnaire.</span></span> <span data-ttu-id="a6d2a-151">Varje referenstyp motsvarar en tabell i Microsoft Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="a6d2a-151">Each reference type corresponds to a table in Microsoft Dynamics 365 for Finance and Operations.</span></span> <span data-ttu-id="a6d2a-152">När du skapar enkättidsplaner kan du ange de enskilda posterna i tabellen eller ett intervall med poster som enkäten ska associeras med.</span><span class="sxs-lookup"><span data-stu-id="a6d2a-152">When you create questionnaire schedules, you can specify individual records in the table or a range of records that the questionnaire will be associated with.</span></span> 

<span data-ttu-id="a6d2a-153">Om du till exempel väljer tabellen Kurser kan du bestämma vilken specifik kurs enkäten ska gälla för.</span><span class="sxs-lookup"><span data-stu-id="a6d2a-153">For example, if you select the Courses table, you can decide which specific course the questionnaire will be for.</span></span> <span data-ttu-id="a6d2a-154">När du ställer in en referens för tabellen Kurser blir alla fält och knappar på sidan **Kurser** tillgängliga.</span><span class="sxs-lookup"><span data-stu-id="a6d2a-154">When you set up a reference for the Courses table, some fields and buttons on the **Courses** page become available.</span></span>

### <a name="questionnaire-schedules"></a><span data-ttu-id="a6d2a-155">Tidsplaner för enkäter</span><span class="sxs-lookup"><span data-stu-id="a6d2a-155">Questionnaire schedules</span></span>

<span data-ttu-id="a6d2a-156">Du kan använda enkättidsplaner för att skapa flera planerade svarsomgångar för ett antal användare, baserat på en referenstyp.</span><span class="sxs-lookup"><span data-stu-id="a6d2a-156">You can use questionnaire schedules to generate multiple planned answer sessions for a group of users, based on a reference type.</span></span> <span data-ttu-id="a6d2a-157">Skapa ett schema på sidan **Enkättidsplaner**.</span><span class="sxs-lookup"><span data-stu-id="a6d2a-157">Create a schedule on the **Questionnaire schedules** page.</span></span> <span data-ttu-id="a6d2a-158">Välj planeringstyp för att kategorisera schemat, och välj även den referenstyp som ska användas för att ställa frågor i systemet för enskilda användare.</span><span class="sxs-lookup"><span data-stu-id="a6d2a-158">Select the planning type to categorize the schedule, and also select the reference type that should be used to query the system for specific users.</span></span> <span data-ttu-id="a6d2a-159">Om du anger referenstypen som tabellen Kurser, kan du exempelvis välja en viss kurs i fältet **Referens**.</span><span class="sxs-lookup"><span data-stu-id="a6d2a-159">For example, if you set the reference type to the Courses table, you can select a specific course in the **Reference** field.</span></span> 

<span data-ttu-id="a6d2a-160">Klicka på **Inställningsdetaljer** om du vill välja enkäten och andra kriterier.</span><span class="sxs-lookup"><span data-stu-id="a6d2a-160">Click **Setup details** to select the questionnaire and other criteria.</span></span> <span data-ttu-id="a6d2a-161">Ange exempelvis namnet på läraren som ett kriterium om enkäten utgör en utvärdering av instruktören.</span><span class="sxs-lookup"><span data-stu-id="a6d2a-161">For example, specify the instructor's name as a criterion if the questionnaire is an evaluation of the instructor.</span></span> <span data-ttu-id="a6d2a-162">När du är klar med att ange inställningsinformationen, skapar systemet planerade svarsomgångar för de användare som deltar i enkäten.</span><span class="sxs-lookup"><span data-stu-id="a6d2a-162">After you've finished entering the setup details, the system generates planned answer sessions for the users that are included in the query.</span></span> 

<span data-ttu-id="a6d2a-163">Klicka på **Planerade svarsomgångar** om du vill visa svarsomgången för tidsplanen.</span><span class="sxs-lookup"><span data-stu-id="a6d2a-163">Click **Planned answer sessions** to view the answer sessions for the schedule.</span></span> <span data-ttu-id="a6d2a-164">Därefter kan du manuellt skapa ytterligare planerade svarsomgångar eller ta bort planerade svarsomgångar som inte har besvarats.</span><span class="sxs-lookup"><span data-stu-id="a6d2a-164">You can then manually create additional planned answer sessions or delete planned answer sessions that haven't been answered.</span></span> 

<span data-ttu-id="a6d2a-165">Klicka på **Funktioner** &gt; **Start** för att göra enkäten tillgänglig för användarna i relaterade planerade svarsomgångar.</span><span class="sxs-lookup"><span data-stu-id="a6d2a-165">Click **Functions** &gt; **Start** to make the questionnaire available to the users in related planned answer sessions.</span></span> <span data-ttu-id="a6d2a-166">Klicka på **Svar** om du vill visa de ifyllda svaren på enkäten.</span><span class="sxs-lookup"><span data-stu-id="a6d2a-166">Click **Answers** to view the completed responses to the questionnaire.</span></span> <span data-ttu-id="a6d2a-167">Du kan också kopiera enkätens tidsplaninställningar, planerade svarsomgångar och svaren till en ny enkättidsplan.</span><span class="sxs-lookup"><span data-stu-id="a6d2a-167">You can optionally copy the questionnaire schedule settings, planned answer sessions, and answers to a new questionnaire schedule.</span></span>

## <a name="notifying-respondents-about-questionnaires-that-are-available-to-them"></a><span data-ttu-id="a6d2a-168">Meddela svarande om enkäter som är tillgängliga för dem</span><span class="sxs-lookup"><span data-stu-id="a6d2a-168">Notifying respondents about questionnaires that are available to them</span></span>
<span data-ttu-id="a6d2a-169">När du distribuerar en enkät måste du meddela svarande att enkäter finns tillgängliga för dem.</span><span class="sxs-lookup"><span data-stu-id="a6d2a-169">When you distribute a questionnaire, you must notify respondents that questionnaires are available to them.</span></span> 

### <a name="notifying-respondents-about-a-planned-answer-session"></a><span data-ttu-id="a6d2a-170">Meddela svarande om en planerad svarsomgång</span><span class="sxs-lookup"><span data-stu-id="a6d2a-170">Notifying respondents about a planned answer session</span></span>

<span data-ttu-id="a6d2a-171">Om du använder en planerad svarsomgång måste du meddela personen direkt, till exempel per telefon eller e-post.</span><span class="sxs-lookup"><span data-stu-id="a6d2a-171">If you use a planned answer session, you must notify the person directly, such as by telephone or email.</span></span>

### <a name="notifying-respondents-about-a-scheduling"></a><span data-ttu-id="a6d2a-172">Meddela svarande om en planering</span><span class="sxs-lookup"><span data-stu-id="a6d2a-172">Notifying respondents about a scheduling</span></span>

<span data-ttu-id="a6d2a-173">Använd sidan **Tidsplaner för enkäter** för att förbereda och skicka ett e-postmeddelande till alla svarande som är kopplade till enkäten.</span><span class="sxs-lookup"><span data-stu-id="a6d2a-173">Use the **Questionnaire schedules** page to prepare and send email to all respondents who are assigned to the questionnaire.</span></span> <span data-ttu-id="a6d2a-174">Ange e-posttexten på fliken **E-postadress för självbetjäning för medarbetare**. När schemat har startats klickar du på **Funktioner** &gt; **Skicka e-post** för att skapa och skicka mailet till mottagarna.</span><span class="sxs-lookup"><span data-stu-id="a6d2a-174">Enter the email text on the **E-mail for employee self service** tab. After the schedule has been started, click **Functions** &gt; **Send e-mail** to generate and send the email to the respondents.</span></span> <span data-ttu-id="a6d2a-175">De svarande kan sedan logga in på webbplatsen och fylla i enkäten.</span><span class="sxs-lookup"><span data-stu-id="a6d2a-175">Respondents can then sign in to the website and complete the questionnaire.</span></span> 

> <span data-ttu-id="a6d2a-176">**Anm.:** Innan du kan använda e-postfunktionen måste din IT-administratör ange e-postinställningarna på sidan **E-postparametrar**.</span><span class="sxs-lookup"><span data-stu-id="a6d2a-176">**Note** Before you can use the email functionality, your IT administrator must enter the email settings on the **E-mail parameters** page.</span></span>

## <a name="ending-a-scheduled-questionnaire"></a><span data-ttu-id="a6d2a-177">Avsluta en tidsplanerad enkät</span><span class="sxs-lookup"><span data-stu-id="a6d2a-177">Ending a scheduled questionnaire</span></span>
<span data-ttu-id="a6d2a-178">Du kan avsluta en tidsplanerad enkät när alla svaranden har avslutat sina tilldelade svarsomgångar.</span><span class="sxs-lookup"><span data-stu-id="a6d2a-178">You can end a scheduled questionnaire after all respondents have completed their assigned answer sessions.</span></span> <span data-ttu-id="a6d2a-179">När planerad enkät slutförs kan du inte kopiera inställningarna till en ny tidsplan.</span><span class="sxs-lookup"><span data-stu-id="a6d2a-179">After a scheduled questionnaire is ended, you can't copy its settings to a new schedule.</span></span> 

> <span data-ttu-id="a6d2a-180">**Anm.:** Om en eller flera svarande inte har fyllt i enkäten och du fortfarande vill avsluta tidsplanen måste du först radera dessa svarande från listan på sidan **Planerad svarsomgång**.</span><span class="sxs-lookup"><span data-stu-id="a6d2a-180">**Note** If one or more respondents haven't completed the questionnaire, but you still want to end the scheduling, you must first delete those respondents from the list on the **Planned answer session** page.</span></span> <span data-ttu-id="a6d2a-181">Sedan kan du avsluta tidsplanen.</span><span class="sxs-lookup"><span data-stu-id="a6d2a-181">You can then end the schedule.</span></span>

## <a name="completing-questionnaires"></a><span data-ttu-id="a6d2a-182">Fylla i enkäter</span><span class="sxs-lookup"><span data-stu-id="a6d2a-182">Completing questionnaires</span></span>
<span data-ttu-id="a6d2a-183">När du har utformat och har fördelat en enkät kan den besvaras av valda svarande.</span><span class="sxs-lookup"><span data-stu-id="a6d2a-183">After you've designed and distributed a questionnaire, the questionnaire can be completed by selected respondents.</span></span> <span data-ttu-id="a6d2a-184">Du kan fylla i de tillgängliga frågeformulären från två platser:</span><span class="sxs-lookup"><span data-stu-id="a6d2a-184">You can complete the questionnaires that are available to you from two locations:</span></span>

-   <span data-ttu-id="a6d2a-185">I navigeringsfönstret klickar du på **Enkäter** &gt; **Fördela** &gt; **Fyll i en enkät**.</span><span class="sxs-lookup"><span data-stu-id="a6d2a-185">In the navigation pane, click **Questionnaires** &gt; **Distribute** &gt; **Complete a questionnaire**.</span></span>
-   <span data-ttu-id="a6d2a-186">Klicka på **Enkäter att fylla i** i Medarbetarsjälvbetjäning.</span><span class="sxs-lookup"><span data-stu-id="a6d2a-186">In Employee self-service, click **Questionnaires to complete**.</span></span>

<span data-ttu-id="a6d2a-187">Enkäter kan göras tillgängliga för vissa användare eller grupper av användare eller för alla användare i ett nätverk.</span><span class="sxs-lookup"><span data-stu-id="a6d2a-187">Questionnaires can made be available to specific users or groups of users, or to all users in a network.</span></span>

<a name="additional-resources"></a><span data-ttu-id="a6d2a-188">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="a6d2a-188">Additional resources</span></span>
--------

[<span data-ttu-id="a6d2a-189">Utforma enkäter</span><span class="sxs-lookup"><span data-stu-id="a6d2a-189">Designing questionnaires</span></span>](design-questionnaires.md)

[<span data-ttu-id="a6d2a-190">Använda enkäter</span><span class="sxs-lookup"><span data-stu-id="a6d2a-190">Using questionnaires</span></span>](questionnaires.md)

[<span data-ttu-id="a6d2a-191">Visa och utvärdera resultaten av en enkät</span><span class="sxs-lookup"><span data-stu-id="a6d2a-191">Viewing and evaluating the results of questionnaires</span></span>](evaluate-questionnaire-results.md)


