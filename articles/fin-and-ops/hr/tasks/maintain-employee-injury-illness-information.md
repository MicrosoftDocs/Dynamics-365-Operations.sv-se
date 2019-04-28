---
title: Underhålla information om medarbetares skador och sjukdomar
description: Vi rekommenderar att du slutför uppgiftsguiden Ställ in skador och sjukdomar först eftersom en del av inställningsinformationen används här.
author: andreabichsel
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: HRMInjuryIncident, HcmWorkerLookUp
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7324a1ce08bfe07a7ef96f4a733ebd44cd392ba6
ms.sourcegitcommit: 608e68b603afef9eb98d8fb25e90109c2473ef87
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2019
ms.locfileid: "856794"
---
# <a name="maintain-employee-injury-and-illness-information"></a><span data-ttu-id="4d141-103">Underhålla information om medarbetares skador och sjukdomar</span><span class="sxs-lookup"><span data-stu-id="4d141-103">Maintain employee injury and illness information</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="4d141-104">Vi rekommenderar att du slutför uppgiftsguiden Ställ in skador och sjukdomar först eftersom en del av inställningsinformationen används här.</span><span class="sxs-lookup"><span data-stu-id="4d141-104">It is recommended to complete the 'Setup injury and illness' task guide first, as some of the setup information is used here.</span></span> 



<span data-ttu-id="4d141-105">Registreringen av den här uppgiften omfattar de grundläggande stegen för att skapa ett skade- eller sjukdomsärende.</span><span class="sxs-lookup"><span data-stu-id="4d141-105">This task recording covers the basic steps to creating an injury or illness case.</span></span> <span data-ttu-id="4d141-106">Förutom att följa information om skadan eller sjukdomen finns det en ärendestatus som dessutom följs.</span><span class="sxs-lookup"><span data-stu-id="4d141-106">Besides tracking the details of the injury or illness, there is a case status that is tracked as well.</span></span>  <span data-ttu-id="4d141-107">Ärendet har som standard en öppen status.</span><span class="sxs-lookup"><span data-stu-id="4d141-107">The case defaults with an 'open' status.</span></span>  <span data-ttu-id="4d141-108">Statusarna kan hanteras via menyn Ärendestatus i programfältet högst upp i formuläret.</span><span class="sxs-lookup"><span data-stu-id="4d141-108">The statuses can be managed from the 'Case status' menu item in the application bar at the top of the form.</span></span>

1. <span data-ttu-id="4d141-109">Gå till Personal > Arbetare > Skador och sjukdomar > Skade- eller sjukdomsincidenter.</span><span class="sxs-lookup"><span data-stu-id="4d141-109">Go to Human resources > Workers > Injury and illness > Injury or illness incidents.</span></span>
2. <span data-ttu-id="4d141-110">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="4d141-110">Click New.</span></span>
3. <span data-ttu-id="4d141-111">I fältet Ärendebeskrivning, skriv ett värde.</span><span class="sxs-lookup"><span data-stu-id="4d141-111">In the Case description field, type a value.</span></span>
    * <span data-ttu-id="4d141-112">Exempel: handledskada</span><span class="sxs-lookup"><span data-stu-id="4d141-112">Example:  Wrist injury</span></span>  
4. <span data-ttu-id="4d141-113">I fältet Arbetare, ange eller välj ett värde.</span><span class="sxs-lookup"><span data-stu-id="4d141-113">In the Worker field, enter or select a value.</span></span>
    * <span data-ttu-id="4d141-114">Exempel: Ahmed Barnett</span><span class="sxs-lookup"><span data-stu-id="4d141-114">Example: Ahmed Barnett</span></span>  
5. <span data-ttu-id="4d141-115">I fältet Datum och tid för incident, ange datum och tid.</span><span class="sxs-lookup"><span data-stu-id="4d141-115">In the Date and time of incident field, enter a date and time.</span></span>
    * <span data-ttu-id="4d141-116">Exempel: 2016-01-20 kl. 10:00</span><span class="sxs-lookup"><span data-stu-id="4d141-116">Example:  1/20/2016 10:00 AM</span></span>  
6. <span data-ttu-id="4d141-117">I fältet Typ av skada eller sjukdom, ange eller välj ett värde.</span><span class="sxs-lookup"><span data-stu-id="4d141-117">In the Injury or illness type field, enter or select a value.</span></span>
    * <span data-ttu-id="4d141-118">Exempel:  Brott</span><span class="sxs-lookup"><span data-stu-id="4d141-118">Example:  Fracture</span></span>  
7. <span data-ttu-id="4d141-119">I fältet Kroppsdel, ange eller välj ett värde.</span><span class="sxs-lookup"><span data-stu-id="4d141-119">In the Body part field, enter or select a value.</span></span>
    * <span data-ttu-id="4d141-120">Exempel:  Handled</span><span class="sxs-lookup"><span data-stu-id="4d141-120">Example:  Wrist</span></span>  
8. <span data-ttu-id="4d141-121">I fältet Resultattyp, ange eller välj ett värde.</span><span class="sxs-lookup"><span data-stu-id="4d141-121">In the Outcome type field, enter or select a value.</span></span>
    * <span data-ttu-id="4d141-122">Exempel:  Terapi</span><span class="sxs-lookup"><span data-stu-id="4d141-122">Example:  Therapy</span></span>  
9. <span data-ttu-id="4d141-123">I fältet Rapporterat datum och rapporterad tid, ange datum och tid.</span><span class="sxs-lookup"><span data-stu-id="4d141-123">In the Date and time reported field, enter a date and time.</span></span>
    * <span data-ttu-id="4d141-124">Datumet och tiden som rapporteras måste infalla senare än datumet och tiden för incidenten.</span><span class="sxs-lookup"><span data-stu-id="4d141-124">The date and time reported must be later than the date and time of incident.</span></span>  
10. <span data-ttu-id="4d141-125">I fältet Person som rapporterade ärendet, ange eller välj ett värde.</span><span class="sxs-lookup"><span data-stu-id="4d141-125">In the Person who reported case field, enter or select a value.</span></span>
    * <span data-ttu-id="4d141-126">Detta kan vara medarbetaren eller ett annat vittne till incidenten.</span><span class="sxs-lookup"><span data-stu-id="4d141-126">This could be the employee or another witness to the incident.</span></span>  <span data-ttu-id="4d141-127">Exempel: Ahmed Barnett</span><span class="sxs-lookup"><span data-stu-id="4d141-127">Example: Ahmed Barnett</span></span>  
11. <span data-ttu-id="4d141-128">Expandera avsnittet Incident.</span><span class="sxs-lookup"><span data-stu-id="4d141-128">Expand the Incident section.</span></span>
12. <span data-ttu-id="4d141-129">I fältet Var incidenten inträffade, skriv ett värde.</span><span class="sxs-lookup"><span data-stu-id="4d141-129">In the Where incident occurred field, type a value.</span></span>
    * <span data-ttu-id="4d141-130">Exempel: lagerställe</span><span class="sxs-lookup"><span data-stu-id="4d141-130">Example:  Warehouse</span></span>  
13. <span data-ttu-id="4d141-131">Välj Ja i fältet På arbetsplatsen.</span><span class="sxs-lookup"><span data-stu-id="4d141-131">Select Yes in the On work premises field.</span></span>
    * <span data-ttu-id="4d141-132">Välj ja om incidenten inträffade på arbetsplatsen.</span><span class="sxs-lookup"><span data-stu-id="4d141-132">If the incident occurred on work premises, select yes.</span></span>  
14. <span data-ttu-id="4d141-133">I fältet Datum och tid då arbetet började, ange datum och tid.</span><span class="sxs-lookup"><span data-stu-id="4d141-133">In the Date and time began work field, enter a date and time.</span></span>
    * <span data-ttu-id="4d141-134">Ange datumet och tiden då den påverkade individen började arbeta, innan incidenten inträffade.</span><span class="sxs-lookup"><span data-stu-id="4d141-134">Enter the date and time that affected individual started working, prior to the incident occurring.</span></span>  
15. <span data-ttu-id="4d141-135">I fältet Medarbetarens jobb eller uppgift, skriv ett värde.</span><span class="sxs-lookup"><span data-stu-id="4d141-135">In the Employee job or task field, type a value.</span></span>
    * <span data-ttu-id="4d141-136">Ange jobbet eller uppgiften som arbetaren utförde när incidenten inträffade.</span><span class="sxs-lookup"><span data-stu-id="4d141-136">Enter the job or task the worker was performing when the incident occurred.</span></span>  <span data-ttu-id="4d141-137">Exempel: lastning av lådor</span><span class="sxs-lookup"><span data-stu-id="4d141-137">Example:  Loading boxes</span></span>  
16. <span data-ttu-id="4d141-138">I fältet Orsak till incident, ange ett värde.</span><span class="sxs-lookup"><span data-stu-id="4d141-138">In the Cause of incident field, type a value.</span></span>
    * <span data-ttu-id="4d141-139">Ange orsaken till incidenten.</span><span class="sxs-lookup"><span data-stu-id="4d141-139">Enter the cause of the incident.</span></span>  <span data-ttu-id="4d141-140">Exempel: halkade på vått golv</span><span class="sxs-lookup"><span data-stu-id="4d141-140">Example:  Slipped on wet floor</span></span>  
17. <span data-ttu-id="4d141-141">I fältet Allvarlighetsnivå, ange eller välj ett värde.</span><span class="sxs-lookup"><span data-stu-id="4d141-141">In the Severity level field, enter or select a value.</span></span>
18. <span data-ttu-id="4d141-142">I fältet Åtgärd som ska utföras, ange ett värde.</span><span class="sxs-lookup"><span data-stu-id="4d141-142">In the Action to be taken field, type a value.</span></span>
    * <span data-ttu-id="4d141-143">Exempel: städa upp spill omedelbart</span><span class="sxs-lookup"><span data-stu-id="4d141-143">Example:  Clean up spills promptly</span></span>  
19. <span data-ttu-id="4d141-144">I fältet Förväntade dagar borta från arbetet, ange ett nummer.</span><span class="sxs-lookup"><span data-stu-id="4d141-144">In the Expected days away from work field, enter a number.</span></span>
    * <span data-ttu-id="4d141-145">Ange antal dagar som personen förväntas vara borta från arbetet.</span><span class="sxs-lookup"><span data-stu-id="4d141-145">Enter the number of days that the individual is expected to be away from work.</span></span>  <span data-ttu-id="4d141-146">När personen kommer tillbaka till arbetet, uppdatera fältet Dagar borta från arbetet med den verkliga antalet frånvarodagar.</span><span class="sxs-lookup"><span data-stu-id="4d141-146">Once the individual returns to work, update the 'Days away from work' field with the actual number of days away.</span></span>  
20. <span data-ttu-id="4d141-147">Expandera avsnittet Kostnader för skadan eller sjukdomen.</span><span class="sxs-lookup"><span data-stu-id="4d141-147">Expand the Injury or illness costs section.</span></span>
21. <span data-ttu-id="4d141-148">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="4d141-148">Click Add.</span></span>
22. <span data-ttu-id="4d141-149">Ange ett datum i fältet Datum.</span><span class="sxs-lookup"><span data-stu-id="4d141-149">In the Date field, enter a date.</span></span>
23. <span data-ttu-id="4d141-150">I fältet Kostnadstyp, ange eller välj ett värde.</span><span class="sxs-lookup"><span data-stu-id="4d141-150">In the Cost type field, enter or select a value.</span></span>
    * <span data-ttu-id="4d141-151">Exempel: terapi. Du kan även ange ett belopp och koppla all stödjande dokumentation såsom fakturor eller en läkares anteckningar till kostnaden.</span><span class="sxs-lookup"><span data-stu-id="4d141-151">Example:  Therapy    You can also enter in an amount, and attach any supporting documentation such as invoices or doctor's notes to the cost.</span></span>  
24. <span data-ttu-id="4d141-152">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="4d141-152">Click Add.</span></span>
25. <span data-ttu-id="4d141-153">Ange ett datum i fältet Datum.</span><span class="sxs-lookup"><span data-stu-id="4d141-153">In the Date field, enter a date.</span></span>
26. <span data-ttu-id="4d141-154">I fältet Kostnadstyp, ange eller välj ett värde.</span><span class="sxs-lookup"><span data-stu-id="4d141-154">In the Cost type field, enter or select a value.</span></span>
    * <span data-ttu-id="4d141-155">Exempel: läkare</span><span class="sxs-lookup"><span data-stu-id="4d141-155">Example: Doctor</span></span>  
27. <span data-ttu-id="4d141-156">Expandera avsnittet Behandlingar av skada eller sjukdom.</span><span class="sxs-lookup"><span data-stu-id="4d141-156">Expand the Injury or illness treatments section.</span></span>
28. <span data-ttu-id="4d141-157">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="4d141-157">Click Add.</span></span>
29. <span data-ttu-id="4d141-158">I fältet Behandlingsdatum, ange datum och tid.</span><span class="sxs-lookup"><span data-stu-id="4d141-158">In the Treatment date field, enter a date and time.</span></span>
30. <span data-ttu-id="4d141-159">I fältet Behandlingstyp, ange eller välj ett värde.</span><span class="sxs-lookup"><span data-stu-id="4d141-159">In the Treatment type field, enter or select a value.</span></span>
    * <span data-ttu-id="4d141-160">Exempel: spjäla</span><span class="sxs-lookup"><span data-stu-id="4d141-160">Example:  Splint</span></span>  
31. <span data-ttu-id="4d141-161">Du kan även välja Ja för avsnittet Besök på akutmottagning.</span><span class="sxs-lookup"><span data-stu-id="4d141-161">Optionally, set the emergency room hospital visit section to Yes.</span></span>
32. <span data-ttu-id="4d141-162">I fältet Behandlingskommentarer, ange ett värde.</span><span class="sxs-lookup"><span data-stu-id="4d141-162">In the Treatment comments field, type a value.</span></span>
    * <span data-ttu-id="4d141-163">Exempel: spjälad under två veckor</span><span class="sxs-lookup"><span data-stu-id="4d141-163">Example:  Splint for 2 weeks</span></span>  
33. <span data-ttu-id="4d141-164">Skriv ett värde i fältet Läkarens namn.</span><span class="sxs-lookup"><span data-stu-id="4d141-164">In the Physician name field, type a value.</span></span>
    * <span data-ttu-id="4d141-165">Example: doktor Anderson</span><span class="sxs-lookup"><span data-stu-id="4d141-165">Example:  Dr. Anderson</span></span>  
34. <span data-ttu-id="4d141-166">I fältet Behandlingsanläggning och plats, ange ett värde.</span><span class="sxs-lookup"><span data-stu-id="4d141-166">In the Treatment facility and location field, type a value.</span></span>
    * <span data-ttu-id="4d141-167">Exempel: Elm St. akutmottagningen</span><span class="sxs-lookup"><span data-stu-id="4d141-167">Example:  Elm St. Emergency</span></span>  
35. <span data-ttu-id="4d141-168">I fältet Behandlingsdetaljer, ange ett värde.</span><span class="sxs-lookup"><span data-stu-id="4d141-168">In the Treatment details field, type a value.</span></span>
    * <span data-ttu-id="4d141-169">Exempel: röntgenundersökning bekräftar fraktur, spjälning måste göras</span><span class="sxs-lookup"><span data-stu-id="4d141-169">Example:  Xray confirms fracture, wear splint</span></span>  
36. <span data-ttu-id="4d141-170">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="4d141-170">Click Save.</span></span>
    * <span data-ttu-id="4d141-171">Ärendets status kan när som helst uppdateras.</span><span class="sxs-lookup"><span data-stu-id="4d141-171">The case status can be updated at any time.</span></span>  <span data-ttu-id="4d141-172">Ange ärendet till pågående om behandlingen av sjukdomen eller skadan pågår.</span><span class="sxs-lookup"><span data-stu-id="4d141-172">Set the case to in process, if the processing of the injury or illness is in process.</span></span>  <span data-ttu-id="4d141-173">När du stänger incidenten kan du bara lägga till eller ta bort kostnader, behandlingar eller arkiveringar som är relaterade till incidenten.</span><span class="sxs-lookup"><span data-stu-id="4d141-173">Once you close the incident you can only add or remove costs, treatments or filings related to the incident.</span></span>  <span data-ttu-id="4d141-174">Öppna ärendet på nytt för att ändra annan information.</span><span class="sxs-lookup"><span data-stu-id="4d141-174">To modify other information, reopen the case.</span></span>  

