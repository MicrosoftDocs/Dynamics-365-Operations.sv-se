---
title: Ställa in utbildningskurser
description: Personalresursadministratörer och chefer kan använda kursfunktionerna för att underhålla information om utbildningen som ges till arbetare.
author: andreabichsel
manager: tfehr
ms.date: 06/24/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
ms.search.form: HcmCourseType, HcmCourseTypeGroup, HRMCourseTable, HcmLearningWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7532
ms.assetid: a6950c29-8b3e-45b2-9084-ddfb1317ffaa
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Human Resources
ms.openlocfilehash: 8557416cee8ae23bb0e9d837677bf8140ecd8a3e
ms.sourcegitcommit: 18e626c49ccfdb12c1484b985e3a275e51f61320
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/04/2021
ms.locfileid: "5115160"
---
# <a name="set-up-training-courses"></a><span data-ttu-id="4d1d2-103">Ställa in utbildningskurser</span><span class="sxs-lookup"><span data-stu-id="4d1d2-103">Set up training courses</span></span>

<span data-ttu-id="4d1d2-104">Personalresursadministratörer och chefer kan använda kursfunktionerna för att underhålla information om utbildningen som ges till arbetare.</span><span class="sxs-lookup"><span data-stu-id="4d1d2-104">Human resources administrators and managers can use the courses features to maintain information about the training that's offered to workers.</span></span>

 <a name="set-up-prerequisites"></a><span data-ttu-id="4d1d2-105"> Konfigurera krav</span><span class="sxs-lookup"><span data-stu-id="4d1d2-105">Set up prerequisites</span></span>
---------------------

<span data-ttu-id="4d1d2-106">Följande information krävs och måste ställas in innan du skapar kurser.</span><span class="sxs-lookup"><span data-stu-id="4d1d2-106">The following information is required and must be set up before you create courses.</span></span>
-   <span data-ttu-id="4d1d2-107">**Kurstyper**</span><span class="sxs-lookup"><span data-stu-id="4d1d2-107">**Course types**</span></span>

<span data-ttu-id="4d1d2-108">Följande information är valfri information som du kan ange för kurser.</span><span class="sxs-lookup"><span data-stu-id="4d1d2-108">The following information is optional information that you can specify for courses.</span></span> <span data-ttu-id="4d1d2-109">Om du vet att du ska ange denna information för kurser, ska du ställa in informationen, innan du skapar kursposter.</span><span class="sxs-lookup"><span data-stu-id="4d1d2-109">If you know that you will be entering this information for courses, you should set up this information before you create course records.</span></span>
-   <span data-ttu-id="4d1d2-110">**Klassrumsgrupper**</span><span class="sxs-lookup"><span data-stu-id="4d1d2-110">**Classroom groups**</span></span>
-   <span data-ttu-id="4d1d2-111">**Kursgrupper**</span><span class="sxs-lookup"><span data-stu-id="4d1d2-111">**Course groups**</span></span>
-   <span data-ttu-id="4d1d2-112">**Kursplatser**</span><span class="sxs-lookup"><span data-stu-id="4d1d2-112">**Course locations**</span></span>
-   <span data-ttu-id="4d1d2-113">**Klassrum**</span><span class="sxs-lookup"><span data-stu-id="4d1d2-113">**Classrooms**</span></span>
-   <span data-ttu-id="4d1d2-114">**Lärare**</span><span class="sxs-lookup"><span data-stu-id="4d1d2-114">**Instructors**</span></span>

## <a name="course-types"></a><span data-ttu-id="4d1d2-115">Kurstyper</span><span class="sxs-lookup"><span data-stu-id="4d1d2-115">Course types</span></span>
<span data-ttu-id="4d1d2-116">Du kan använda kurstyper för att kategorisera kurser enligt strukturen eller innehållet i kursen.</span><span class="sxs-lookup"><span data-stu-id="4d1d2-116">You can use course types to categorize courses according to the structure or content of the course.</span></span> <span data-ttu-id="4d1d2-117">Du kan skapa kurstyper på sidan **Kurstyper**.</span><span class="sxs-lookup"><span data-stu-id="4d1d2-117">You can create course types on the **Course types** page.</span></span> <span data-ttu-id="4d1d2-118">Du måste välja en kurstyp när du skapar en kurspost.</span><span class="sxs-lookup"><span data-stu-id="4d1d2-118">You must select a course type when you create a course record.</span></span>

## <a name="course-setup-type"></a><span data-ttu-id="4d1d2-119">Kursinställningstyp</span><span class="sxs-lookup"><span data-stu-id="4d1d2-119">Course setup type</span></span>
<span data-ttu-id="4d1d2-120">Följande tabell listar de tre inställningstyperna för kurser.</span><span class="sxs-lookup"><span data-stu-id="4d1d2-120">The following table lists the three setup types for courses.</span></span> <span data-ttu-id="4d1d2-121">Inställningstyper bestämmer strukturen för kursen.</span><span class="sxs-lookup"><span data-stu-id="4d1d2-121">Setup types determine the structure of the course.</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="4d1d2-122">Inställningstyp</span><span class="sxs-lookup"><span data-stu-id="4d1d2-122">Setup type</span></span></th>
<th><span data-ttu-id="4d1d2-123">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="4d1d2-123">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="4d1d2-124"><strong>Standard</strong></span><span class="sxs-lookup"><span data-stu-id="4d1d2-124"><strong>Standard</strong></span></span></td>
<td><span data-ttu-id="4d1d2-125">Välj den här typen för kurser som inte ska ha en daglig agenda.</span><span class="sxs-lookup"><span data-stu-id="4d1d2-125">Select this type for courses that will not have a daily agenda.</span></span> <span data-ttu-id="4d1d2-126">Detta är standardinställningen när du skapar en ny kurs.</span><span class="sxs-lookup"><span data-stu-id="4d1d2-126">This is the default setup type when you create a new course.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="4d1d2-127"><strong>Agenda</strong></span><span class="sxs-lookup"><span data-stu-id="4d1d2-127"><strong>Agenda</strong></span></span></td>
<td><span data-ttu-id="4d1d2-128">Välj den här typen för att planera information om varje dag i en kurs som hålls över flera dagar.</span><span class="sxs-lookup"><span data-stu-id="4d1d2-128">Select this type to plan the details of each day of a course that takes place over multiple days.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="4d1d2-129"><strong>Agenda + session</strong></span><span class="sxs-lookup"><span data-stu-id="4d1d2-129"><strong>Agenda + session</strong></span></span></td>
<td><span data-ttu-id="4d1d2-130">Välj den här typen för mer komplexa de kurser.</span><span class="sxs-lookup"><span data-stu-id="4d1d2-130">Select this type for the more complex courses.</span></span> <span data-ttu-id="4d1d2-131">Du kan till exempel dela in kursprogrammet i spårningar och sessioner.</span><span class="sxs-lookup"><span data-stu-id="4d1d2-131">For example, you can divide the agenda for the course into tracks and sessions.</span></span>
<ul>
<li><span data-ttu-id="4d1d2-132"><strong>Spår</strong> – Spår är specifika ämnesområden för en kurs.</span><span class="sxs-lookup"><span data-stu-id="4d1d2-132"><strong>Track</strong> – Tracks are specific subject areas for a course.</span></span></li>
<li><span data-ttu-id="4d1d2-133"><strong>Sessioner</strong> – Sessioner används för att dela upp spår och kan omfatta specifika processer eller tekniker som är relevanta för varje spår.</span><span class="sxs-lookup"><span data-stu-id="4d1d2-133"><strong>Sessions</strong> – Sessions divide up tracks and help identify specific processes or techniques that are relevant to the track.</span></span></li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="course-tasks"></a><span data-ttu-id="4d1d2-134">Kursuppgifter</span><span class="sxs-lookup"><span data-stu-id="4d1d2-134">Course tasks</span></span>
<span data-ttu-id="4d1d2-135">Du kan utföra följande uppgifter för varje kurs.</span><span class="sxs-lookup"><span data-stu-id="4d1d2-135">For each course, you can complete the following tasks.</span></span>
- <span data-ttu-id="4d1d2-136">Registrera deltagare</span><span class="sxs-lookup"><span data-stu-id="4d1d2-136">Register participants</span></span>
- <span data-ttu-id="4d1d2-137">Ange en deadline för registreringen</span><span class="sxs-lookup"><span data-stu-id="4d1d2-137">Specify a registration deadline</span></span>
- <span data-ttu-id="4d1d2-138">Ange lägsta och högsta antal deltagare</span><span class="sxs-lookup"><span data-stu-id="4d1d2-138">Define the minimum and maximum number of participants</span></span>
- <span data-ttu-id="4d1d2-139">Tilldela en plats och ett klassrum för kursen</span><span class="sxs-lookup"><span data-stu-id="4d1d2-139">Assign a course location and classroom</span></span>
- <span data-ttu-id="4d1d2-140">Rekommendera hotell för kursdeltagare</span><span class="sxs-lookup"><span data-stu-id="4d1d2-140">Recommend hotels to course participants</span></span>
- <span data-ttu-id="4d1d2-141">Skapa en kursbeskrivning som du sedan kan annonsera på Självbetjäning för medarbetare</span><span class="sxs-lookup"><span data-stu-id="4d1d2-141">Create a course description, which you can then advertise on Employee self service</span></span>

  ><span data-ttu-id="4d1d2-142">**Obs!** Du kan bara ta bort en kurs om ingen har registrerat sig för den.</span><span class="sxs-lookup"><span data-stu-id="4d1d2-142">**Note** You can delete a course only if no one has registered for it.</span></span> 

## <a name="course-statuses"></a><span data-ttu-id="4d1d2-143">Kursstatus</span><span class="sxs-lookup"><span data-stu-id="4d1d2-143">Course statuses</span></span>
<span data-ttu-id="4d1d2-144">Följande tabell listar möjliga kursstatusvärden och de åtgärder som du kan utföra när kursen har en viss status.</span><span class="sxs-lookup"><span data-stu-id="4d1d2-144">The following table lists the possible course statuses and the actions that you can complete when the course has a specific status.</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="4d1d2-145">Status</span><span class="sxs-lookup"><span data-stu-id="4d1d2-145">Status</span></span></th>
<th><span data-ttu-id="4d1d2-146">Åtgärder</span><span class="sxs-lookup"><span data-stu-id="4d1d2-146">Actions</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="4d1d2-147"><strong>Skapad</strong></span><span class="sxs-lookup"><span data-stu-id="4d1d2-147"><strong>Created</strong></span></span></td>
<td><ul>
<li><span data-ttu-id="4d1d2-148">Ange och ändra kursinformation.</span><span class="sxs-lookup"><span data-stu-id="4d1d2-148">Enter and modify course information.</span></span></li>
<li><span data-ttu-id="4d1d2-149">Ändra kursstatus till <strong>Öppen</strong> så att arbetare kan registrera sig för kursen.</span><span class="sxs-lookup"><span data-stu-id="4d1d2-149">Change the course status to <strong>Open</strong> so that workers can register for the course.</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="4d1d2-150"><strong>Öppna</strong></span><span class="sxs-lookup"><span data-stu-id="4d1d2-150"><strong>Open</strong></span></span></td>
<td><ul>
<li><span data-ttu-id="4d1d2-151">Registrera deltagare till kursen.</span><span class="sxs-lookup"><span data-stu-id="4d1d2-151">Register participants for the course.</span></span></li>
<li><span data-ttu-id="4d1d2-152">Ta bort deltagare från kursen.</span><span class="sxs-lookup"><span data-stu-id="4d1d2-152">Remove participants from the course.</span></span></li>
<li><span data-ttu-id="4d1d2-153">Bekräfta deltagare för kursen.</span><span class="sxs-lookup"><span data-stu-id="4d1d2-153">Confirm participants for the course.</span></span></li>
<li><span data-ttu-id="4d1d2-154">Ändra kursens status till <strong>Stängd</strong> eller <strong>Inställd</strong>.</span><span class="sxs-lookup"><span data-stu-id="4d1d2-154">Change the course status to <strong>Closed</strong> or <strong>Canceled</strong>.</span></span></li>
<li><span data-ttu-id="4d1d2-155">Planera enkäter för deltagare vilkas status är <strong>Bekräftad</strong>.</span><span class="sxs-lookup"><span data-stu-id="4d1d2-155">Plan questionnaires for participants whose status is <strong>Confirmed</strong>.</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="4d1d2-156"><strong>Stängt</strong></span><span class="sxs-lookup"><span data-stu-id="4d1d2-156"><strong>Closed</strong></span></span></td>
<td><span data-ttu-id="4d1d2-157">Du kan öppna kursen igen.</span><span class="sxs-lookup"><span data-stu-id="4d1d2-157">You can reopen the course.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="4d1d2-158"><strong>Avbrutna</strong></span><span class="sxs-lookup"><span data-stu-id="4d1d2-158"><strong>Canceled</strong></span></span></td>
<td><span data-ttu-id="4d1d2-159">Du kan öppna kursen igen.</span><span class="sxs-lookup"><span data-stu-id="4d1d2-159">You can reopen the course.</span></span></td>
</tr>
</tbody>
</table>

## <a name="course-participants"></a><span data-ttu-id="4d1d2-160">Kursdeltagare</span><span class="sxs-lookup"><span data-stu-id="4d1d2-160">Course participants</span></span>
<span data-ttu-id="4d1d2-161">Kursdeltagare är arbetare som deltar i en utbildningskurs eller en händelse.</span><span class="sxs-lookup"><span data-stu-id="4d1d2-161">Course participants are workers who participate in a training course or event.</span></span> <span data-ttu-id="4d1d2-162">Du kan bara registrera deltagare för öppna kurser.</span><span class="sxs-lookup"><span data-stu-id="4d1d2-162">You can only register participants for open courses.</span></span> <span data-ttu-id="4d1d2-163">Det minsta och det högsta antalet deltagare som du kan registrera för en kurs definieras på snabbfliken **Allmänt** på sidan **Kurser**.</span><span class="sxs-lookup"><span data-stu-id="4d1d2-163">The minimum and maximum number of participants that you can register for a course is defined on the **General** FastTab on the **Courses** page.</span></span>

<a name="workflow"></a><span data-ttu-id="4d1d2-164">Arbetsflöde</span><span class="sxs-lookup"><span data-stu-id="4d1d2-164">Workflow</span></span>
--------

<span data-ttu-id="4d1d2-165">Medarbetare som registrerar sig för en kurs via sidan **Självbetjäning för medarbetare** kan få sin registrering skickad via arbetsflödet för godkännande.</span><span class="sxs-lookup"><span data-stu-id="4d1d2-165">Employees who register for a course through the **Employee self service** page can have their registration routed through workflow for approval.</span></span> <span data-ttu-id="4d1d2-166">Du kan tilldela ett arbetsflöde till en kurs i snabbfliken **Allmänt** på sidan **Kurser**.</span><span class="sxs-lookup"><span data-stu-id="4d1d2-166">You can assign a workflow to a course on the **General** FastTab on the **Courses** page.</span></span>





