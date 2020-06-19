---
title: Ange projekttidrapporter
description: Den här proceduren låter dig skapa en tidrapport genom att använda ett tomt tidrapportformulär.
author: andreabichsel
manager: AnnBe
ms.date: 08/08/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Operations, Human Resources
ms.search.region: Global
ms.search.industry: Service industries
ms.author: anbichse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 10dbb43cec47a758d11362947f27932a4911911a
ms.sourcegitcommit: ba340f836e472f13f263dec46a49847c788fca44
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/04/2020
ms.locfileid: "3430289"
---
# <a name="enter-project-timesheets"></a><span data-ttu-id="1822d-103">Ange projekttidrapporter</span><span class="sxs-lookup"><span data-stu-id="1822d-103">Enter project timesheets</span></span>



<span data-ttu-id="1822d-104">Den här proceduren låter dig skapa en tidrapport genom att använda ett tomt tidrapportformulär.</span><span class="sxs-lookup"><span data-stu-id="1822d-104">This procedure lets you create a timesheet by using an empty timesheet form.</span></span> <span data-ttu-id="1822d-105">Den nya tidrapporten kan baseras på information från en tidigare tidrapport eller från projekt- och aktivitetstilldelningar på sidan **Mina favoriter**.</span><span class="sxs-lookup"><span data-stu-id="1822d-105">The new timesheet can be based on information from a previous timesheet, or from project and activity assignments in the **My favorites** page.</span></span> <span data-ttu-id="1822d-106">Som standard visas listsidan **Alla tidrapporter** där alla dina tidrapporter för den aktuella perioden visas.</span><span class="sxs-lookup"><span data-stu-id="1822d-106">By default, the **All timesheets** list page displays all your timesheets for the current period.</span></span> <span data-ttu-id="1822d-107">Du kan använda listrutan för fältet **Visa** på sidan **Mina tidrapporter** för att filtrera tidrapportlistan per tidsperiod eller projekt eller visa tidrapporter som har skapats på uppdrag av andra arbetare.</span><span class="sxs-lookup"><span data-stu-id="1822d-107">You can use the drop-down list for the **Show** field in the **My timesheets** page to filter the timesheet list by time period or project, or to view timesheets that were created on behalf of other workers.</span></span> <span data-ttu-id="1822d-108">Det demonstrationsdataföretag som används för att skapa den här proceduren är USSI.</span><span class="sxs-lookup"><span data-stu-id="1822d-108">The demo data company used to create this procedure is USSI.</span></span> 

1. <span data-ttu-id="1822d-109">I **navigeringsfönstret**, gå till **Moduler > Projekthantering och redovisning > Tidrapporter > Mina tidrapporter**.</span><span class="sxs-lookup"><span data-stu-id="1822d-109">In the **Navigation pane**, go to **Modules > Project management and accounting > Timesheets > My timesheets**.</span></span>
2. <span data-ttu-id="1822d-110">Klicka på **Ny** om du vill ange en ny tidrapport.</span><span class="sxs-lookup"><span data-stu-id="1822d-110">To enter a new timesheet, click **New**.</span></span>
    - <span data-ttu-id="1822d-111">Listrutan Resurs visar som standard den arbetare som har tilldelats den aktuella användaren.</span><span class="sxs-lookup"><span data-stu-id="1822d-111">The Resource drop-down list shows the worker assigned to the current user, by default.</span></span>  
    - <span data-ttu-id="1822d-112">Om användaren är utsedd till ombud, kommer namnen att listas så att en användare kan ange en tidrapport åt dem.</span><span class="sxs-lookup"><span data-stu-id="1822d-112">If the user is designated as a delegate, this will list the names so that a user can enter a timesheet on their behalf.</span></span>  
3. <span data-ttu-id="1822d-113">Ange ett datum i fältet **Datum.**</span><span class="sxs-lookup"><span data-stu-id="1822d-113">In the **Date** field, enter a date.</span></span> <span data-ttu-id="1822d-114">Om det här alternativet väljs kommer nya tidrapportsrader skapas genom att använda tidrapportinställningarna som har konfigurerats som favoriter.</span><span class="sxs-lookup"><span data-stu-id="1822d-114">If this option is selected, new timesheet lines will be created by using the timesheet settings that were configured as favorites.</span></span>  
4. <span data-ttu-id="1822d-115">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="1822d-115">Click **OK**.</span></span>
5. <span data-ttu-id="1822d-116">Klicka på **Ny rad**.</span><span class="sxs-lookup"><span data-stu-id="1822d-116">Click **New line**.</span></span>
6. <span data-ttu-id="1822d-117">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="1822d-117">In the list, mark the selected row.</span></span> <span data-ttu-id="1822d-118">I fältet **Juridisk person** visas den aktuella juridiska personen som standard.</span><span class="sxs-lookup"><span data-stu-id="1822d-118">The **Legal Entity** field displays the current Legal entity by default.</span></span>   
7. <span data-ttu-id="1822d-119">I fältet **Projekt**, öppna sökningen genom att klicka på den nedrullningsbara knappen.</span><span class="sxs-lookup"><span data-stu-id="1822d-119">In the **Project** field, click the drop-down button to open the lookup.</span></span>
8. <span data-ttu-id="1822d-120">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="1822d-120">In the list, find and select the desired record.</span></span>
9. <span data-ttu-id="1822d-121">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="1822d-121">In the list, click the link in the selected row.</span></span>
10. <span data-ttu-id="1822d-122">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet **Aktivitetsnummer**.</span><span class="sxs-lookup"><span data-stu-id="1822d-122">In the **Activity number** field, click the drop-down button to open the lookup.</span></span>
11. <span data-ttu-id="1822d-123">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="1822d-123">In the list, find and select the desired record.</span></span>
12. <span data-ttu-id="1822d-124">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="1822d-124">In the list, click the link in the selected row.</span></span>
13. <span data-ttu-id="1822d-125">I fältet **Kategori**, öppna sökningen genom att klicka på den nedrullningsbara knappen.</span><span class="sxs-lookup"><span data-stu-id="1822d-125">In the **Category** field, click the drop-down button to open the lookup.</span></span>
14. <span data-ttu-id="1822d-126">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="1822d-126">In the list, find and select the desired record.</span></span>
15. <span data-ttu-id="1822d-127">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="1822d-127">In the list, click the link in the selected row.</span></span>
16. <span data-ttu-id="1822d-128">Ange antalet arbetstimmar för varje dag.</span><span class="sxs-lookup"><span data-stu-id="1822d-128">Enter the number of hours worked each day.</span></span> <span data-ttu-id="1822d-129">Ange timmarna i decimalformat.</span><span class="sxs-lookup"><span data-stu-id="1822d-129">Enter the hours in decimal format.</span></span> <span data-ttu-id="1822d-130">Ange till exempel 2,25, om du har arbetat för två timmar och 15 minuter.</span><span class="sxs-lookup"><span data-stu-id="1822d-130">For example, if you worked for two hours and fifteen minutes, enter 2.25.</span></span>   
17. <span data-ttu-id="1822d-131">Följande uppdateringsalternativ är tillgängliga för **Radinformation**:</span><span class="sxs-lookup"><span data-stu-id="1822d-131">In **Line details**, the following options are available:</span></span>
    - <span data-ttu-id="1822d-132">Lägg till information om skatter och ekonomiska dimensioner på fliken **Allmänt** och fliken **Ekonomiska dimensioner**.</span><span class="sxs-lookup"><span data-stu-id="1822d-132">Add information about taxes and financial dimensions in the **General** and the **Financial Dimensions** tab.</span></span>
    - <span data-ttu-id="1822d-133">Lägg till kommentarer om tidrapportraden på fliken **Kommentar**.</span><span class="sxs-lookup"><span data-stu-id="1822d-133">Add comments about the timesheet line in the **Comment** tab.</span></span>
20. <span data-ttu-id="1822d-134">Klicka på **Arbetsflöde** i **åtgärdsfönstret** för att öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="1822d-134">In the **Action pane**, click **Workflow** to open the drop dialog.</span></span>
21. <span data-ttu-id="1822d-135">Klicka på **Skicka**.</span><span class="sxs-lookup"><span data-stu-id="1822d-135">Click **Submit**.</span></span>
22. <span data-ttu-id="1822d-136">Klicka på **Skicka**.</span><span class="sxs-lookup"><span data-stu-id="1822d-136">Click **Submit**.</span></span>

