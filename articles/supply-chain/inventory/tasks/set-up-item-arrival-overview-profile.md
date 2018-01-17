---
title: "Ställ in en översiktsprofil för artikelinförsel"
description: "Denna uppgift är avsedd för att ställa in en översiktsprofil för införsel."
author: perlynne
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: bis
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 029511634e56aec7fdd91bad9441cd12951fbd8d
ms.openlocfilehash: d4248882608a3d1e23c8c9e9dc8069caaa8352c2
ms.contentlocale: sv-se
ms.lasthandoff: 01/17/2018

---
# <a name="set-up-an-item-arrival-overview-profile"></a><span data-ttu-id="0a108-103">Ställ in en översiktsprofil för artikelinförsel</span><span class="sxs-lookup"><span data-stu-id="0a108-103">Set up an item arrival overview profile</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="0a108-104">Denna uppgift är avsedd för att ställa in en översiktsprofil för införsel.</span><span class="sxs-lookup"><span data-stu-id="0a108-104">This task focuses on the setup of an arrival overview profile.</span></span> <span data-ttu-id="0a108-105">Översiktsprofilen för införsel är en grupp regler som tillämpas när sidan Införselöversikt öppnas av en användare.</span><span class="sxs-lookup"><span data-stu-id="0a108-105">The arrival overview profile is a collection of rules that will be applied when the Arrival overview page is opened by a user.</span></span> <span data-ttu-id="0a108-106">Du kan köra den här proceduren i demonstrationsdataföretaget USMF.</span><span class="sxs-lookup"><span data-stu-id="0a108-106">You can use this procedure in demo data company USMF.</span></span> <span data-ttu-id="0a108-107">Den här proceduren utförs vanligtvis av en inleveransansvarig.</span><span class="sxs-lookup"><span data-stu-id="0a108-107">This procedure would typically be carried out by a receiving clerk.</span></span>





1. <span data-ttu-id="0a108-108">Gå till Lagerstyrning > Inställningar > Distribution > Översiktsprofiler för införsel.</span><span class="sxs-lookup"><span data-stu-id="0a108-108">Go to Inventory management > Setup > Distribution > Arrival overview profiles.</span></span>
2. <span data-ttu-id="0a108-109">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="0a108-109">Click New.</span></span>
    * <span data-ttu-id="0a108-110">Eftersom du nästan ska arbeta på samma lagerställe där fulla lastbilsbeläggningar lastas av, bör du skapa en översiktsprofil för införsel för att förenkla processen att registrera inlevererade artiklar.</span><span class="sxs-lookup"><span data-stu-id="0a108-110">Because you will almost always work in the same warehouse offloading full truck loads, you should create an arrival overview profile to simplify the process of registering received items.</span></span>  
3. <span data-ttu-id="0a108-111">Skriv ett värde i fältet Namn på översiktsprofil för införsel.</span><span class="sxs-lookup"><span data-stu-id="0a108-111">In the Arrival overview profile name field, type a value.</span></span>
4. <span data-ttu-id="0a108-112">Välj ett alternativ i fältet Visa rader.</span><span class="sxs-lookup"><span data-stu-id="0a108-112">In the Show lines field, select an option.</span></span>
    * <span data-ttu-id="0a108-113">Välj vilka rader som ska visas för inleveranserna: Alla – visa alla rader, oavsett status.</span><span class="sxs-lookup"><span data-stu-id="0a108-113">Select which lines to show for the receipts:   All – Show all lines, regardless of status.</span></span>   <span data-ttu-id="0a108-114">Pågår – Visa rader för inleveranser där förloppet är Slutfört eller Delvis.</span><span class="sxs-lookup"><span data-stu-id="0a108-114">In progress – Show lines for receipts in which the progress is Complete or Partly.</span></span> <span data-ttu-id="0a108-115">Detta innebär att för varje rad har antingen hela kvantiteten eller en del av kvantiteten registrerats i en införseljournal.</span><span class="sxs-lookup"><span data-stu-id="0a108-115">This means that for each line, either the full quantity or part of the quantity has been registered in an arrival journal.</span></span>   <span data-ttu-id="0a108-116">Ej fullständigt – Visa rader för inleveranser där förloppet är Inget eller Delvis.</span><span class="sxs-lookup"><span data-stu-id="0a108-116">Not complete – Show lines for receipts in which the progress is None or Partly.</span></span> <span data-ttu-id="0a108-117">Detta innebär för varje rad att ingenting eller bara en del av kvantiteten registrerats i en införseljournal.</span><span class="sxs-lookup"><span data-stu-id="0a108-117">This means that for each line, nothing or only part of the quantity has been registered in an arrival journal.</span></span>  
5. <span data-ttu-id="0a108-118">Visa eller dölj avsnittet Alternativ för införsel.</span><span class="sxs-lookup"><span data-stu-id="0a108-118">Expand or collapse the Arrival options section.</span></span>
6. <span data-ttu-id="0a108-119">Skriv ett värde i fältet Dagar framåt.</span><span class="sxs-lookup"><span data-stu-id="0a108-119">In the Days forward field, type a value.</span></span>
    * <span data-ttu-id="0a108-120">Detta anger ett filter för att visa inleveransraderna som förväntas inlevereras inom de närmsta dagar (beroende på det antal du anger).</span><span class="sxs-lookup"><span data-stu-id="0a108-120">This sets a filter to show the receipt lines expected to be received within the next few days (depending on the number you set).</span></span>  
7. <span data-ttu-id="0a108-121">Skriv ett värde i fältet Dagar bakåt.</span><span class="sxs-lookup"><span data-stu-id="0a108-121">In the Days back field, type a value.</span></span>
    * <span data-ttu-id="0a108-122">Detta anger ett filter för att visa inleveransraderna som förväntas inlevereras ett antal dagar före idag.</span><span class="sxs-lookup"><span data-stu-id="0a108-122">This sets a filter to show the receipt lines expected to be received a number of days before today.</span></span>  
8. <span data-ttu-id="0a108-123">Skriv ett värde i fältet Lagerställen.</span><span class="sxs-lookup"><span data-stu-id="0a108-123">In the Warehouses field, type a value.</span></span>
    * <span data-ttu-id="0a108-124">Filtrera på ett eller flera lagerställen.</span><span class="sxs-lookup"><span data-stu-id="0a108-124">Filter on one or more warehouses.</span></span>  
9. <span data-ttu-id="0a108-125">Välj ett värde i fältet Leveranssätt.</span><span class="sxs-lookup"><span data-stu-id="0a108-125">In the Mode of delivery field, select a value.</span></span>
    * <span data-ttu-id="0a108-126">Detta anger ett filter för att endast visa de inleveransrader med det här leveranssättet.</span><span class="sxs-lookup"><span data-stu-id="0a108-126">This sets a filter to show only the receipt lines with this Mode of delivery.</span></span>  
10. <span data-ttu-id="0a108-127">Välj WHS i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="0a108-127">In the Name field, select WHS.</span></span>
11. <span data-ttu-id="0a108-128">Välj lagerställe 24 i fältet Lagerställe.</span><span class="sxs-lookup"><span data-stu-id="0a108-128">In the Warehouse field, select warehouse 24.</span></span>
    * <span data-ttu-id="0a108-129">Detta är det standardlagerställe som ska användas för registrerade inleveransrader som använder den här profilen.</span><span class="sxs-lookup"><span data-stu-id="0a108-129">This is the default warehouse that will be used for registered receipt lines that use this profile.</span></span>  
12. <span data-ttu-id="0a108-130">Markera ett Baydoor i fältet Plats.</span><span class="sxs-lookup"><span data-stu-id="0a108-130">In the Location field, select Baydoor.</span></span>
    * <span data-ttu-id="0a108-131">Detta är den standardplats som ska användas för registrerade inleveransrader som använder den här profilen.</span><span class="sxs-lookup"><span data-stu-id="0a108-131">This is the default location that will be used for registered receipt lines that use this profile.</span></span>  
13. <span data-ttu-id="0a108-132">Visa eller dölj avsnittet Detaljer för fråga om införsel.</span><span class="sxs-lookup"><span data-stu-id="0a108-132">Expand or collapse the Arrival query details section.</span></span>
14. <span data-ttu-id="0a108-133">Välj site 2 i fältet Begränsa till plats.</span><span class="sxs-lookup"><span data-stu-id="0a108-133">In the Restrict to site field, select site 2.</span></span>
    * <span data-ttu-id="0a108-134">Detta anger ett filter för att endast visa inleveransraderna med den här webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="0a108-134">This sets a filter to show only the receipt lines with this site.</span></span>  
15. <span data-ttu-id="0a108-135">Ange alternativet Inköpsorder till Ja.</span><span class="sxs-lookup"><span data-stu-id="0a108-135">Set the Purchase orders option to Yes.</span></span>
    * <span data-ttu-id="0a108-136">Välj rader från inköpsorder.</span><span class="sxs-lookup"><span data-stu-id="0a108-136">Select receipt lines from purchase orders.</span></span>  
16. <span data-ttu-id="0a108-137">Ange alternativet Överföringsorder till Ja.</span><span class="sxs-lookup"><span data-stu-id="0a108-137">Set the Transfer orders option to Yes.</span></span>
    * <span data-ttu-id="0a108-138">Välj inköpsrader från överföringsorder.</span><span class="sxs-lookup"><span data-stu-id="0a108-138">Select receipt lines from transfer orders.</span></span>  
17. <span data-ttu-id="0a108-139">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="0a108-139">Click Save.</span></span>
18. <span data-ttu-id="0a108-140">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="0a108-140">Close the page.</span></span>

