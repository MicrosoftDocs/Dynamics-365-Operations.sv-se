---
title: "Ställa in utbildningskurser"
description: "Personalresursadministratörer och chefer kan använda kursfunktionerna för att underhålla information om utbildningen som ges till arbetare."
author: rschloma
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
ms.search.form: HcmCourseType, HcmCourseTypeGroup, HRMCourseTable
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Core, Operations, Talent
ms.custom: 7532
ms.assetid: a6950c29-8b3e-45b2-9084-ddfb1317ffaa
ms.search.region: Global
ms.author: rschloma
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Talent July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 95d5bf26c22238753586cf4a7aaf5c26f061a705
ms.openlocfilehash: 27fbc54afca384b804f2b0468206242ff89d4031
ms.contentlocale: sv-se
ms.lasthandoff: 02/23/2018

---

# <a name="set-up-training-courses"></a><span data-ttu-id="44cfc-103">Ställa in utbildningskurser</span><span class="sxs-lookup"><span data-stu-id="44cfc-103">Set up training courses</span></span>

[!include[banner](includes/banner.md)]


<span data-ttu-id="44cfc-104">Personalresursadministratörer och chefer kan använda kursfunktionerna för att underhålla information om utbildningen som ges till arbetare.</span><span class="sxs-lookup"><span data-stu-id="44cfc-104">Human resources administrators and managers can use the courses features to maintain information about the training that's offered to workers.</span></span>

 <a name="set-up-prerequisites"></a><span data-ttu-id="44cfc-105"> Konfigurera krav</span><span class="sxs-lookup"><span data-stu-id="44cfc-105">Set up prerequisites</span></span>
---------------------

<span data-ttu-id="44cfc-106">Följande information krävs och måste ställas in innan du skapar kurser.</span><span class="sxs-lookup"><span data-stu-id="44cfc-106">The following information is required and must be set up before you create courses.</span></span>
-   <span data-ttu-id="44cfc-107">**Kurstyper**</span><span class="sxs-lookup"><span data-stu-id="44cfc-107">**Course types**</span></span>

<span data-ttu-id="44cfc-108">Följande information är valfri information som du kan ange för kurser.</span><span class="sxs-lookup"><span data-stu-id="44cfc-108">The following information is optional information that you can specify for courses.</span></span> <span data-ttu-id="44cfc-109">Om du vet att du ska ange denna information för kurser, ska du ställa in informationen, innan du skapar kursposter.</span><span class="sxs-lookup"><span data-stu-id="44cfc-109">If you know that you will be entering this information for courses, you should set up this information before you create course records.</span></span>
-   <span data-ttu-id="44cfc-110">**Klassrumsgrupper**</span><span class="sxs-lookup"><span data-stu-id="44cfc-110">**Classroom groups**</span></span>
-   <span data-ttu-id="44cfc-111">**Kursgrupper**</span><span class="sxs-lookup"><span data-stu-id="44cfc-111">**Course groups**</span></span>
-   <span data-ttu-id="44cfc-112">**Kursplatser**</span><span class="sxs-lookup"><span data-stu-id="44cfc-112">**Course locations**</span></span>
-   <span data-ttu-id="44cfc-113">**Klassrum**</span><span class="sxs-lookup"><span data-stu-id="44cfc-113">**Classrooms**</span></span>
-   <span data-ttu-id="44cfc-114">**Lärare**</span><span class="sxs-lookup"><span data-stu-id="44cfc-114">**Instructors**</span></span>

## <a name="course-types"></a><span data-ttu-id="44cfc-115">Kurstyper</span><span class="sxs-lookup"><span data-stu-id="44cfc-115">Course types</span></span>
<span data-ttu-id="44cfc-116">Du kan använda kurstyper för att kategorisera kurser enligt strukturen eller innehållet i kursen.</span><span class="sxs-lookup"><span data-stu-id="44cfc-116">You can use course types to categorize courses according to the structure or content of the course.</span></span> <span data-ttu-id="44cfc-117">Du kan skapa kurstyper på sidan **Kurstyper**.</span><span class="sxs-lookup"><span data-stu-id="44cfc-117">You can create course types on the **Course types** page.</span></span> <span data-ttu-id="44cfc-118">Du måste välja en kurstyp när du skapar en kurspost.</span><span class="sxs-lookup"><span data-stu-id="44cfc-118">You must select a course type when you create a course record.</span></span>

## <a name="course-setup-type"></a><span data-ttu-id="44cfc-119">Kursinställningstyp</span><span class="sxs-lookup"><span data-stu-id="44cfc-119">Course setup type</span></span>
<span data-ttu-id="44cfc-120">Följande tabell listar de tre inställningstyperna för kurser.</span><span class="sxs-lookup"><span data-stu-id="44cfc-120">The following table lists the three setup types for courses.</span></span> <span data-ttu-id="44cfc-121">Inställningstyper bestämmer strukturen för kursen.</span><span class="sxs-lookup"><span data-stu-id="44cfc-121">Setup types determine the structure of the course.</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="44cfc-122">Inställningstyp</span><span class="sxs-lookup"><span data-stu-id="44cfc-122">Setup type</span></span></th>
<th><span data-ttu-id="44cfc-123">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="44cfc-123">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="44cfc-124"><strong>Standard</strong></span><span class="sxs-lookup"><span data-stu-id="44cfc-124"><strong>Standard</strong></span></span></td>
<td><span data-ttu-id="44cfc-125">Välj den här typen för kurser som inte ska ha en daglig agenda.</span><span class="sxs-lookup"><span data-stu-id="44cfc-125">Select this type for courses that will not have a daily agenda.</span></span> <span data-ttu-id="44cfc-126">Detta är standardinställningen när du skapar en ny kurs.</span><span class="sxs-lookup"><span data-stu-id="44cfc-126">This is the default setup type when you create a new course.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="44cfc-127"><strong>Agenda</strong></span><span class="sxs-lookup"><span data-stu-id="44cfc-127"><strong>Agenda</strong></span></span></td>
<td><span data-ttu-id="44cfc-128">Välj den här typen för att planera information om varje dag i en kurs som hålls över flera dagar.</span><span class="sxs-lookup"><span data-stu-id="44cfc-128">Select this type to plan the details of each day of a course that takes place over multiple days.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="44cfc-129"><strong>Agenda + session</strong></span><span class="sxs-lookup"><span data-stu-id="44cfc-129"><strong>Agenda + session</strong></span></span></td>
<td><span data-ttu-id="44cfc-130">Välj den här typen för mer komplexa de kurser.</span><span class="sxs-lookup"><span data-stu-id="44cfc-130">Select this type for the more complex courses.</span></span> <span data-ttu-id="44cfc-131">Du kan till exempel dela in kursprogrammet i spårningar och sessioner.</span><span class="sxs-lookup"><span data-stu-id="44cfc-131">For example, you can divide the agenda for the course into tracks and sessions.</span></span>
<ul>
<li><span data-ttu-id="44cfc-132"><strong>Spår</strong> – Spår är specifika ämnesområden för en kurs.</span><span class="sxs-lookup"><span data-stu-id="44cfc-132"><strong>Track</strong> – Tracks are specific subject areas for a course.</span></span></li>
<li><span data-ttu-id="44cfc-133"><strong>Sessioner</strong> – Sessioner används för att dela upp spår och kan omfatta specifika processer eller tekniker som är relevanta för varje spår.</span><span class="sxs-lookup"><span data-stu-id="44cfc-133"><strong>Sessions</strong> – Sessions divide up tracks and help identify specific processes or techniques that are relevant to the track.</span></span></li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="course-tasks"></a><span data-ttu-id="44cfc-134">Kursuppgifter</span><span class="sxs-lookup"><span data-stu-id="44cfc-134">Course tasks</span></span>
<span data-ttu-id="44cfc-135">Du kan utföra följande uppgifter för varje kurs.</span><span class="sxs-lookup"><span data-stu-id="44cfc-135">For each course, you can complete the following tasks.</span></span>
-   <span data-ttu-id="44cfc-136">Registrera deltagare</span><span class="sxs-lookup"><span data-stu-id="44cfc-136">Register participants</span></span>
-   <span data-ttu-id="44cfc-137">Ange en deadline för registreringen</span><span class="sxs-lookup"><span data-stu-id="44cfc-137">Specify a registration deadline</span></span>
-   <span data-ttu-id="44cfc-138">Ange lägsta och högsta antal deltagare</span><span class="sxs-lookup"><span data-stu-id="44cfc-138">Define the minimum and maximum number of participants</span></span>
-   <span data-ttu-id="44cfc-139">Tilldela en plats och ett klassrum för kursen</span><span class="sxs-lookup"><span data-stu-id="44cfc-139">Assign a course location and classroom</span></span>
-   <span data-ttu-id="44cfc-140">Rekommendera hotell för kursdeltagare</span><span class="sxs-lookup"><span data-stu-id="44cfc-140">Recommend hotels to course participants</span></span>
-   <span data-ttu-id="44cfc-141">Skapa en kursbeskrivning som du sedan kan annonsera på Självbetjäning för medarbetare</span><span class="sxs-lookup"><span data-stu-id="44cfc-141">Create a course description, which you can then advertise on Employee self service</span></span>

  ><span data-ttu-id="44cfc-142">**Obs!** Du kan bara ta bort en kurs om ingen har registrerat sig för den.</span><span class="sxs-lookup"><span data-stu-id="44cfc-142">**Note** You can delete a course only if no one has registered for it.</span></span> 
    
## <a name="course-statuses"></a><span data-ttu-id="44cfc-143">Kursstatus</span><span class="sxs-lookup"><span data-stu-id="44cfc-143">Course statuses</span></span>
<span data-ttu-id="44cfc-144">Följande tabell listar möjliga kursstatusvärden och de åtgärder som du kan utföra när kursen har en viss status.</span><span class="sxs-lookup"><span data-stu-id="44cfc-144">The following table lists the possible course statuses and the actions that you can complete when the course has a specific status.</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="44cfc-145">Status</span><span class="sxs-lookup"><span data-stu-id="44cfc-145">Status</span></span></th>
<th><span data-ttu-id="44cfc-146">Åtgärder</span><span class="sxs-lookup"><span data-stu-id="44cfc-146">Actions</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="44cfc-147"><strong>Skapad</strong></span><span class="sxs-lookup"><span data-stu-id="44cfc-147"><strong>Created</strong></span></span></td>
<td><ul>
<li><span data-ttu-id="44cfc-148">Ange och ändra kursinformation.</span><span class="sxs-lookup"><span data-stu-id="44cfc-148">Enter and modify course information.</span></span></li>
<li><span data-ttu-id="44cfc-149">Ändra kursstatus till <strong>Öppen</strong> så att arbetare kan registrera sig för kursen.</span><span class="sxs-lookup"><span data-stu-id="44cfc-149">Change the course status to <strong>Open</strong> so that workers can register for the course.</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="44cfc-150"><strong>Öppna</strong></span><span class="sxs-lookup"><span data-stu-id="44cfc-150"><strong>Open</strong></span></span></td>
<td><ul>
<li><span data-ttu-id="44cfc-151">Registrera deltagare till kursen.</span><span class="sxs-lookup"><span data-stu-id="44cfc-151">Register participants for the course.</span></span></li>
<li><span data-ttu-id="44cfc-152">Ta bort deltagare från kursen.</span><span class="sxs-lookup"><span data-stu-id="44cfc-152">Remove participants from the course.</span></span></li>
<li><span data-ttu-id="44cfc-153">Bekräfta deltagare för kursen.</span><span class="sxs-lookup"><span data-stu-id="44cfc-153">Confirm participants for the course.</span></span></li>
<li><span data-ttu-id="44cfc-154">Ändra kursens status till <strong>Stängd</strong> eller <strong>Inställd</strong>.</span><span class="sxs-lookup"><span data-stu-id="44cfc-154">Change the course status to <strong>Closed</strong> or <strong>Canceled</strong>.</span></span></li>
<li><span data-ttu-id="44cfc-155">Planera enkäter för deltagare vilkas status är <strong>Bekräftad</strong>.</span><span class="sxs-lookup"><span data-stu-id="44cfc-155">Plan questionnaires for participants whose status is <strong>Confirmed</strong>.</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="44cfc-156"><strong>Stängt</strong></span><span class="sxs-lookup"><span data-stu-id="44cfc-156"><strong>Closed</strong></span></span></td>
<td><span data-ttu-id="44cfc-157">Du kan öppna kursen igen.</span><span class="sxs-lookup"><span data-stu-id="44cfc-157">You can reopen the course.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="44cfc-158"><strong>Avbrutna</strong></span><span class="sxs-lookup"><span data-stu-id="44cfc-158"><strong>Canceled</strong></span></span></td>
<td><span data-ttu-id="44cfc-159">Du kan öppna kursen igen.</span><span class="sxs-lookup"><span data-stu-id="44cfc-159">You can reopen the course.</span></span></td>
</tr>
</tbody>
</table>

## <a name="course-participants"></a><span data-ttu-id="44cfc-160">Kursdeltagare</span><span class="sxs-lookup"><span data-stu-id="44cfc-160">Course participants</span></span>
<span data-ttu-id="44cfc-161">Kursdeltagare är arbetare, sökanden eller kontaktpersoner som deltar i en utbildningskurs eller en händelse.</span><span class="sxs-lookup"><span data-stu-id="44cfc-161">Course participants are workers, applicants, or contact persons who participate in a training course or event.</span></span> <span data-ttu-id="44cfc-162">Du kan bara registrera deltagare för öppna kurser.</span><span class="sxs-lookup"><span data-stu-id="44cfc-162">You can only register participants for open courses.</span></span> <span data-ttu-id="44cfc-163">Det minsta och det högsta antalet deltagare som du kan registrera för en kurs definieras på snabbfliken **Allmänt** på sidan **Kurser**.</span><span class="sxs-lookup"><span data-stu-id="44cfc-163">The minimum and maximum number of participants that you can register for a course is defined on the **General** FastTab on the **Courses** page.</span></span>

<a name="workflow"></a><span data-ttu-id="44cfc-164">Arbetsflöde</span><span class="sxs-lookup"><span data-stu-id="44cfc-164">Workflow</span></span>
--------

<span data-ttu-id="44cfc-165">Medarbetare som registrerar sig för en kurs via sidan **Självbetjäning för medarbetare** kan få sin registrering skickad via arbetsflödet för godkännande.</span><span class="sxs-lookup"><span data-stu-id="44cfc-165">Employees who register for a course through the **Employee self service** page can have their registration routed through workflow for approval.</span></span>  <span data-ttu-id="44cfc-166">Ett arbetsflöde kan tilldelas till en kurs i snabbfliken **Allmänt** på sidan **Kurser**.</span><span class="sxs-lookup"><span data-stu-id="44cfc-166">A workflow can be assigned to a course on the **General** FastTab on the **Courses** page.</span></span>






