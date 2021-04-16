---
title: Ställ in en översiktsprofil för artikelinförsel
description: Detta avsnitt är avsett för att ställa in en översiktsprofil för införsel.
author: ShylaThompson
ms.date: 07/30/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: WMSArrivalOverviewProfile
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b0394d1b4288dac0ff913b125017571a8c0bc95a
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5829846"
---
# <a name="set-up-an-item-arrival-overview-profile"></a><span data-ttu-id="b9fa9-103">Ställ in en översiktsprofil för artikelinförsel</span><span class="sxs-lookup"><span data-stu-id="b9fa9-103">Set up an item arrival overview profile</span></span>

<span data-ttu-id="b9fa9-104">[!include [banner](../../includes/banner.md)]]</span><span class="sxs-lookup"><span data-stu-id="b9fa9-104">[!include [banner](../../includes/banner.md)]]</span></span>

<span data-ttu-id="b9fa9-105">Detta avsnitt är avsett för att ställa in en översiktsprofil för införsel.</span><span class="sxs-lookup"><span data-stu-id="b9fa9-105">This topic focuses on the setup of an arrival overview profile.</span></span> <span data-ttu-id="b9fa9-106">Översiktsprofilen för införsel är en grupp regler som tillämpas när sidan Införselöversikt öppnas av en användare.</span><span class="sxs-lookup"><span data-stu-id="b9fa9-106">The arrival overview profile is a collection of rules that will be applied when the Arrival overview page is opened by a user.</span></span> <span data-ttu-id="b9fa9-107">Du kan köra den här proceduren i demonstrationsdataföretaget USMF.</span><span class="sxs-lookup"><span data-stu-id="b9fa9-107">You can use this procedure in demo data company USMF.</span></span> <span data-ttu-id="b9fa9-108">Den här proceduren utförs vanligtvis av en inleveransansvarig.</span><span class="sxs-lookup"><span data-stu-id="b9fa9-108">This procedure would typically be carried out by a receiving clerk.</span></span>

1. <span data-ttu-id="b9fa9-109">I navigeringsfönstret gå till **Moduler > Lagerhantering > Inställningar > Fördelning > Översiktsprofiler för införsel**.</span><span class="sxs-lookup"><span data-stu-id="b9fa9-109">In the navigation pane, go to **Modules > Inventory management > Setup > Distribution > Arrival overview profiles**.</span></span>
2. <span data-ttu-id="b9fa9-110">Välj **Ny**.</span><span class="sxs-lookup"><span data-stu-id="b9fa9-110">Select **New**.</span></span> <span data-ttu-id="b9fa9-111">Eftersom du nästan ska arbeta på samma lagerställe där fulla lastbilsbeläggningar lastas av, bör du skapa en översiktsprofil för införsel för att förenkla processen att registrera inlevererade artiklar.</span><span class="sxs-lookup"><span data-stu-id="b9fa9-111">Because you will almost always work in the same warehouse offloading full truck loads, you should create an arrival overview profile to simplify the process of registering received items.</span></span>  
3. <span data-ttu-id="b9fa9-112">Skriv ett värde i fältet **Namn på översiktsprofil för införsel**.</span><span class="sxs-lookup"><span data-stu-id="b9fa9-112">In the **Arrival overview profile name** field, type a value.</span></span>
4. <span data-ttu-id="b9fa9-113">Välj ett alternativ i fältet **Visa rader**.</span><span class="sxs-lookup"><span data-stu-id="b9fa9-113">In the **Show lines** field, select an option.</span></span> <span data-ttu-id="b9fa9-114">Välj vilka rader som ska visas för inleveranserna:</span><span class="sxs-lookup"><span data-stu-id="b9fa9-114">Select which lines to show for the receipts:</span></span>  

    - <span data-ttu-id="b9fa9-115">**Alla** – Visa alla rader, oavsett status.</span><span class="sxs-lookup"><span data-stu-id="b9fa9-115">**All** – Show all lines, regardless of status.</span></span>   
    - <span data-ttu-id="b9fa9-116">**Pågår** – Visa rader för inleveranser där förloppet är Slutfört eller Delvis.</span><span class="sxs-lookup"><span data-stu-id="b9fa9-116">**In progress** – Show lines for receipts in which the progress is Complete or Partly.</span></span> <span data-ttu-id="b9fa9-117">Detta innebär att för varje rad har antingen hela kvantiteten eller en del av kvantiteten registrerats i en införseljournal.</span><span class="sxs-lookup"><span data-stu-id="b9fa9-117">This means that for each line, either the full quantity or part of the quantity has been registered in an arrival journal.</span></span>   
    - <span data-ttu-id="b9fa9-118">**Ej fullständigt** – Visa rader för inleveranser där förloppet är Inget eller Delvis.</span><span class="sxs-lookup"><span data-stu-id="b9fa9-118">**Not complete** – Show lines for receipts in which the progress is None or Partly.</span></span> <span data-ttu-id="b9fa9-119">Detta innebär för varje rad att ingenting eller bara en del av kvantiteten registrerats i en införseljournal.</span><span class="sxs-lookup"><span data-stu-id="b9fa9-119">This means that for each line, nothing or only part of the quantity has been registered in an arrival journal.</span></span>  

5. <span data-ttu-id="b9fa9-120">Visa eller dölj avsnittet **Alternativ för införsel**.</span><span class="sxs-lookup"><span data-stu-id="b9fa9-120">Expand or collapse the **Arrival options** section.</span></span>
6. <span data-ttu-id="b9fa9-121">Skriv ett värde i fältet **Dagar framåt**.</span><span class="sxs-lookup"><span data-stu-id="b9fa9-121">In the **Days forward** field, type a value.</span></span> <span data-ttu-id="b9fa9-122">Detta anger ett filter för att visa inleveransraderna som förväntas inlevereras inom de närmsta dagar (beroende på det antal du anger).</span><span class="sxs-lookup"><span data-stu-id="b9fa9-122">This sets a filter to show the receipt lines expected to be received within the next few days (depending on the number you set).</span></span>  
7. <span data-ttu-id="b9fa9-123">Skriv ett värde i fältet **Dagar bakåt**.</span><span class="sxs-lookup"><span data-stu-id="b9fa9-123">In the **Days back** field, type a value.</span></span> <span data-ttu-id="b9fa9-124">Detta anger ett filter för att visa inleveransraderna som förväntas inlevereras ett antal dagar före idag.</span><span class="sxs-lookup"><span data-stu-id="b9fa9-124">This sets a filter to show the receipt lines expected to be received a number of days before today.</span></span>  
8. <span data-ttu-id="b9fa9-125">Skriv ett värde i fältet **Lagerställen**.</span><span class="sxs-lookup"><span data-stu-id="b9fa9-125">In the **Warehouses** field, type a value.</span></span> <span data-ttu-id="b9fa9-126">Filtrera på ett eller flera lagerställen.</span><span class="sxs-lookup"><span data-stu-id="b9fa9-126">Filter on one or more warehouses.</span></span>  
9. <span data-ttu-id="b9fa9-127">Välj ett värde i fältet **Leveranssätt**.</span><span class="sxs-lookup"><span data-stu-id="b9fa9-127">In the **Mode of delivery** field, select a value.</span></span> <span data-ttu-id="b9fa9-128">Detta anger ett filter för att endast visa de inleveransrader med det här leveranssättet.</span><span class="sxs-lookup"><span data-stu-id="b9fa9-128">This sets a filter to show only the receipt lines with this Mode of delivery.</span></span>  
10. <span data-ttu-id="b9fa9-129">Välj WHS i fältet **Namn** .</span><span class="sxs-lookup"><span data-stu-id="b9fa9-129">In the **Name** field, select WHS.</span></span>
11. <span data-ttu-id="b9fa9-130">Välj lagerställe 24 i fältet **Lagerställe**.</span><span class="sxs-lookup"><span data-stu-id="b9fa9-130">In the **Warehouse** field, select warehouse 24.</span></span> <span data-ttu-id="b9fa9-131">Detta är det standardlagerställe som ska användas för registrerade inleveransrader som använder den här profilen.</span><span class="sxs-lookup"><span data-stu-id="b9fa9-131">This is the default warehouse that will be used for registered receipt lines that use this profile.</span></span>  
12. <span data-ttu-id="b9fa9-132">Välj **Baydoor** i fältet **Plats**.</span><span class="sxs-lookup"><span data-stu-id="b9fa9-132">In the **Location** field, select **Baydoor**.</span></span> <span data-ttu-id="b9fa9-133">Detta är den standardplats som ska användas för registrerade inleveransrader som använder den här profilen.</span><span class="sxs-lookup"><span data-stu-id="b9fa9-133">This is the default location that will be used for registered receipt lines that use this profile.</span></span>  
13. <span data-ttu-id="b9fa9-134">Visa eller dölj avsnittet **Detaljer för fråga om införsel**.</span><span class="sxs-lookup"><span data-stu-id="b9fa9-134">Expand or collapse the **Arrival query details** section.</span></span>
14. <span data-ttu-id="b9fa9-135">Välj plats 2 i fältet **Begränsa till plats**.</span><span class="sxs-lookup"><span data-stu-id="b9fa9-135">In the **Restrict to site** field, select site 2.</span></span> <span data-ttu-id="b9fa9-136">Detta anger ett filter för att endast visa inleveransraderna med den här webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="b9fa9-136">This sets a filter to show only the receipt lines with this site.</span></span>  
15. <span data-ttu-id="b9fa9-137">Ange alternativet **Inköpsorder** till **Ja**.</span><span class="sxs-lookup"><span data-stu-id="b9fa9-137">Set the **Purchase orders** option to **Yes**.</span></span> <span data-ttu-id="b9fa9-138">Välj rader från inköpsorder.</span><span class="sxs-lookup"><span data-stu-id="b9fa9-138">Select receipt lines from purchase orders.</span></span>  
16. <span data-ttu-id="b9fa9-139">Ange orderalternativet **Överför** till **Ja**.</span><span class="sxs-lookup"><span data-stu-id="b9fa9-139">Set the **Transfer** orders option to **Yes**.</span></span> <span data-ttu-id="b9fa9-140">Välj inköpsrader från överföringsorder.</span><span class="sxs-lookup"><span data-stu-id="b9fa9-140">Select receipt lines from transfer orders.</span></span>  
17. <span data-ttu-id="b9fa9-141">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="b9fa9-141">Select **Save**.</span></span>
18. <span data-ttu-id="b9fa9-142">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="b9fa9-142">Close the page.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]