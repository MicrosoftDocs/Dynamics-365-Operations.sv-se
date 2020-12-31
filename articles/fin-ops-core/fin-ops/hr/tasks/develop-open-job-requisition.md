---
title: Utveckla och öppna jobbrekvisition
description: Med rekryteringsprojekt kan du hantera rekryteringsprocessen.
author: andreabichsel
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: HRMRecruitingTable, HcmWorkerLookUp, HcmJobLookup, HRMRecruitingMedia, HRMRecruitingJobAd
audience: Application User
ms.reviewer: anbichse
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 20ee5d1bb624943d1ee67bbf2e7b5ecef1d59e9d
ms.sourcegitcommit: f5e31c34640add6d40308ac1365cc0ee60e60e24
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/08/2020
ms.locfileid: "4693098"
---
# <a name="develop-and-open-job-requisition"></a><span data-ttu-id="8b8ea-103">Utveckla och öppna jobbrekvisition</span><span class="sxs-lookup"><span data-stu-id="8b8ea-103">Develop and open job requisition</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="8b8ea-104">Med rekryteringsprojekt kan du hantera rekryteringsprocessen.</span><span class="sxs-lookup"><span data-stu-id="8b8ea-104">Recruitment projects help manage the recruiting process.</span></span> <span data-ttu-id="8b8ea-105">För varje rekryteringsprojekt kan du konfigurera information, till exempel jobbet som rekryteringen gäller, namnet på rekryteraren, projektets status och den avdelning som jobbet ska finns på.</span><span class="sxs-lookup"><span data-stu-id="8b8ea-105">For each recruitment project, you can set up information, such as the job that recruiting is for, the name of the recruiter, the status of the project and the department that the job will be located in.</span></span> <span data-ttu-id="8b8ea-106">När du har skapat ett rekryteringsprojekt, kan du skriva en jobbannons för projektet, publicera annonsen på medarbetarnas självbetjäningssidor, koppla jobbansökningar till projektet och spåra aktiviteter för det här projekt.</span><span class="sxs-lookup"><span data-stu-id="8b8ea-106">After creating a recruitment project, you can write a job advertisement for the project, publish the ad on Employee self-service pages, associate applications for employment with the project, and track activities for that project.</span></span> <span data-ttu-id="8b8ea-107">Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF.</span><span class="sxs-lookup"><span data-stu-id="8b8ea-107">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="8b8ea-108">Börja proceduren genom att gå till Personal > Rekrytering > Rekryteringsprojekt > Rekryteringsprojekt</span><span class="sxs-lookup"><span data-stu-id="8b8ea-108">To begin the procedure, go to Human resources > Recruitment > Recruitment projects > Recruitment projects</span></span>

1. <span data-ttu-id="8b8ea-109">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="8b8ea-109">Click New.</span></span>
2. <span data-ttu-id="8b8ea-110">Skriv ett värde i fältet Rekryteringsprojekt.</span><span class="sxs-lookup"><span data-stu-id="8b8ea-110">In the Recruitment project field, type a value.</span></span>
3. <span data-ttu-id="8b8ea-111">Ange ett värde i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="8b8ea-111">In the Description field, type a value.</span></span>
4. <span data-ttu-id="8b8ea-112">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Rekryterare.</span><span class="sxs-lookup"><span data-stu-id="8b8ea-112">In the Recruiter field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="8b8ea-113">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="8b8ea-113">In the list, find and select the desired record.</span></span>
6. <span data-ttu-id="8b8ea-114">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="8b8ea-114">In the list, click the link in the selected row.</span></span>
7. <span data-ttu-id="8b8ea-115">Klicka på Välj.</span><span class="sxs-lookup"><span data-stu-id="8b8ea-115">Click Select.</span></span>
8. <span data-ttu-id="8b8ea-116">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Avdelning.</span><span class="sxs-lookup"><span data-stu-id="8b8ea-116">In the Department field, click the drop-down button to open the lookup.</span></span>
9. <span data-ttu-id="8b8ea-117">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="8b8ea-117">In the list, click the link in the selected row.</span></span>
10. <span data-ttu-id="8b8ea-118">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Jobb.</span><span class="sxs-lookup"><span data-stu-id="8b8ea-118">In the Job field, click the drop-down button to open the lookup.</span></span>
11. <span data-ttu-id="8b8ea-119">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="8b8ea-119">In the list, find and select the desired record.</span></span>
12. <span data-ttu-id="8b8ea-120">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="8b8ea-120">In the list, click the link in the selected row.</span></span>
13. <span data-ttu-id="8b8ea-121">Ange ett antal i fältet Antal lediga jobb.</span><span class="sxs-lookup"><span data-stu-id="8b8ea-121">In the Number of openings field, enter a number.</span></span>
14. <span data-ttu-id="8b8ea-122">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Anställande chef.</span><span class="sxs-lookup"><span data-stu-id="8b8ea-122">In the Hiring manager field, click the drop-down button to open the lookup.</span></span>
15. <span data-ttu-id="8b8ea-123">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="8b8ea-123">In the list, find and select the desired record.</span></span>
16. <span data-ttu-id="8b8ea-124">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="8b8ea-124">In the list, click the link in the selected row.</span></span>
17. <span data-ttu-id="8b8ea-125">Klicka på Välj.</span><span class="sxs-lookup"><span data-stu-id="8b8ea-125">Click Select.</span></span>
18. <span data-ttu-id="8b8ea-126">Ange ett datum i fältet Deadline för ansökning.</span><span class="sxs-lookup"><span data-stu-id="8b8ea-126">In the Application deadline field, enter a date.</span></span>
19. <span data-ttu-id="8b8ea-127">Klicka på Media.</span><span class="sxs-lookup"><span data-stu-id="8b8ea-127">Click Media.</span></span>
    * <span data-ttu-id="8b8ea-128">Rekryteringsprojekt har alternativ för att ange mediakanaler som ska användas för att annonsera vakanta befattningar.</span><span class="sxs-lookup"><span data-stu-id="8b8ea-128">Recruitment projects include the option to specify media outlets to use to advertise open positions.</span></span>  
20. <span data-ttu-id="8b8ea-129">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="8b8ea-129">Click New.</span></span>
21. <span data-ttu-id="8b8ea-130">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Media.</span><span class="sxs-lookup"><span data-stu-id="8b8ea-130">In the Media field, click the drop-down button to open the lookup.</span></span>
22. <span data-ttu-id="8b8ea-131">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="8b8ea-131">In the list, click the link in the selected row.</span></span>
23. <span data-ttu-id="8b8ea-132">Ange ett datum i fältet Startdatum.</span><span class="sxs-lookup"><span data-stu-id="8b8ea-132">In the Start date field, enter a date.</span></span>
24. <span data-ttu-id="8b8ea-133">Ange ett datum i fältet Slutdatum.</span><span class="sxs-lookup"><span data-stu-id="8b8ea-133">In the End date field, enter a date.</span></span>
25. <span data-ttu-id="8b8ea-134">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="8b8ea-134">Click Save.</span></span>
26. <span data-ttu-id="8b8ea-135">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="8b8ea-135">Close the page.</span></span>
27. <span data-ttu-id="8b8ea-136">Klicka på Platsannonser.</span><span class="sxs-lookup"><span data-stu-id="8b8ea-136">Click Job ads.</span></span>
28. <span data-ttu-id="8b8ea-137">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="8b8ea-137">Click Save.</span></span>
29. <span data-ttu-id="8b8ea-138">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="8b8ea-138">Close the page.</span></span>
30. <span data-ttu-id="8b8ea-139">Markera eller avmarkera kryssrutan Visa i självbetjäningen för medarbetare.</span><span class="sxs-lookup"><span data-stu-id="8b8ea-139">Check or uncheck the Display on employee self service checkbox.</span></span>
    * <span data-ttu-id="8b8ea-140">Markera kryssrutan Visa i självbetjäningen för medarbetare om du vill göra rekryteringsprojektet synligt för medarbetare på deras medarbetarsjälvbetjäningssidor.</span><span class="sxs-lookup"><span data-stu-id="8b8ea-140">Select the Display on employee self service check box to make the recruitment project visible to employees on their Employee self-service pages.</span></span>  
31. <span data-ttu-id="8b8ea-141">Klicka på Rekryteringsprojektets status.</span><span class="sxs-lookup"><span data-stu-id="8b8ea-141">Click Recruitment project status.</span></span>
32. <span data-ttu-id="8b8ea-142">Klicka på Start.</span><span class="sxs-lookup"><span data-stu-id="8b8ea-142">Click Start.</span></span>
    * <span data-ttu-id="8b8ea-143">Statusen Startad innebär att projektet är redo att ta emot ansökningar.</span><span class="sxs-lookup"><span data-stu-id="8b8ea-143">The Started status means that the project is ready to receive applications.</span></span>  
33. <span data-ttu-id="8b8ea-144">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="8b8ea-144">Click OK.</span></span>

