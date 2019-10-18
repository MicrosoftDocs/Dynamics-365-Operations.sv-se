---
title: Tids- och närvarohantering i Retail
description: Det här avsnittet beskriver scenarierna som stöds för tids- och närvarohantering i detaljhandel i Dynamics 365 Retail.
author: aamirallaqaband
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: JMGParameters
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 62813
ms.assetid: 821994a6-cd29-45a3-a526-ce204064f080
ms.search.region: global
ms.search.industry: Retail
ms.author: aamiral
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: d541de550df41b7d4616492960bd4f2aae46d45e
ms.sourcegitcommit: f87de0f949b5d60993b19e0f61297f02d42b5bef
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/24/2019
ms.locfileid: "2024993"
---
# <a name="time-and-attendance-management-in-retail"></a><span data-ttu-id="a3db9-103">Tids- och närvarohantering i Retail</span><span class="sxs-lookup"><span data-stu-id="a3db9-103">Time and attendance management in Retail</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="a3db9-104">Det här avsnittet beskriver scenarierna som stöds för tids- och närvarohantering i detaljhandel i Dynamics 365 Retail.</span><span class="sxs-lookup"><span data-stu-id="a3db9-104">This topic describes the scenarios that are supported for time and attendance management in Dynamics 365 Retail.</span></span>

## <a name="manage-worker-setup-and-scheduling"></a><span data-ttu-id="a3db9-105">Hantera inställningar för arbetare och schemaläggning</span><span class="sxs-lookup"><span data-stu-id="a3db9-105">Manage worker setup and scheduling</span></span>

### <a name="initial-configuration"></a><span data-ttu-id="a3db9-106"> Ursprunglig konfiguration</span><span class="sxs-lookup"><span data-stu-id="a3db9-106">Initial configuration</span></span>

- <span data-ttu-id="a3db9-107">Kör guiden för konfiguration.</span><span class="sxs-lookup"><span data-stu-id="a3db9-107">Run the configuration wizard.</span></span>
- <span data-ttu-id="a3db9-108">Registrera arbetstagare som projekttid arbetstagare.</span><span class="sxs-lookup"><span data-stu-id="a3db9-108">Register workers as time registration workers.</span></span>

### <a name="plan-worker-schedules"></a><span data-ttu-id="a3db9-109">Planen arbetstagaren scheman</span><span class="sxs-lookup"><span data-stu-id="a3db9-109">Plan worker schedules</span></span>

- <span data-ttu-id="a3db9-110">Använda profiler med arbete planerare.</span><span class="sxs-lookup"><span data-stu-id="a3db9-110">Apply profiles by using the work planner.</span></span> <span data-ttu-id="a3db9-111">Mer information finns i [Använd profiler med arbetsplanering](https://technet.microsoft.com/library/aa551234.aspx).</span><span class="sxs-lookup"><span data-stu-id="a3db9-111">For more information, see [Apply profiles using work planner](https://technet.microsoft.com/library/aa551234.aspx).</span></span>

<span data-ttu-id="a3db9-112">Mer information om konfigurationsstegen finns i [inställning av tid och närvaro](https://technet.microsoft.com/library/aa496971.aspx).</span><span class="sxs-lookup"><span data-stu-id="a3db9-112">For information about the configuration steps, see [Setting up time and attendance](https://technet.microsoft.com/library/aa496971.aspx).</span></span>

### <a name="retail-specific-configuration"></a><span data-ttu-id="a3db9-113">Retail-specifik konfiguration</span><span class="sxs-lookup"><span data-stu-id="a3db9-113">Retail-specific configuration</span></span>

- <span data-ttu-id="a3db9-114">Aktivera en funktion profil för klocka, för arbetstagare som du vill aktivera tidsregistreringar.</span><span class="sxs-lookup"><span data-stu-id="a3db9-114">Enable a functionality profile for Time Clock, for workers that you want to enable time registrations for.</span></span> <span data-ttu-id="a3db9-115">Klicka på **Kassafunktionsprofiler** &gt; **Funktioner** &gt; **Tidsregistreringar vid kassa** &gt; **Aktivera tidsregistreringar**.</span><span class="sxs-lookup"><span data-stu-id="a3db9-115">Click **POS functionality profiles** &gt; **Functions** &gt; **POS time registrations** &gt; **Enable time registrations**.</span></span>
- <span data-ttu-id="a3db9-116">Konfigurera point of sale (POS) behörigheter grupper att visa timeclock poster tillstånd.</span><span class="sxs-lookup"><span data-stu-id="a3db9-116">Configure point of sale (POS) permissions groups to enable the View timeclock entries permission.</span></span> <span data-ttu-id="a3db9-117">Detta tillstånd kan en användare visa tid klocka registreringar av andra arbetstagare i affären (och från alla andra som användaren är kopplad till, via adressboken).</span><span class="sxs-lookup"><span data-stu-id="a3db9-117">This permission lets a user view the time clock registrations of other workers in the store (and from any other store that the user is associated with, via the address book).</span></span> <span data-ttu-id="a3db9-118">Du kanske vill aktivera detta tillstånd för en chef roll men inte för en kassör roll.</span><span class="sxs-lookup"><span data-stu-id="a3db9-118">You might want to enable this permission for a manager role but not for a cashier role.</span></span> <span data-ttu-id="a3db9-119">Klicka på **Kassabehörighetsgrupper** &gt; **Visa stämpelklocksregistreringar**.</span><span class="sxs-lookup"><span data-stu-id="a3db9-119">Click **POS permission groups** &gt; **View time clock entries**.</span></span>

## <a name="register-time"></a><span data-ttu-id="a3db9-120">Kassatid</span><span class="sxs-lookup"><span data-stu-id="a3db9-120">Register time</span></span>

### <a name="cashier-and-non-cashier-time-registrations"></a><span data-ttu-id="a3db9-121">Kassa och icke-kassa tidsregistreringar</span><span class="sxs-lookup"><span data-stu-id="a3db9-121">Cashier and non-cashier time registrations</span></span>

- <span data-ttu-id="a3db9-122">På POS:</span><span class="sxs-lookup"><span data-stu-id="a3db9-122">On POS:</span></span>

    - <span data-ttu-id="a3db9-123">Klocka-operationer:</span><span class="sxs-lookup"><span data-stu-id="a3db9-123">Clock-in operations:</span></span>

        - <span data-ttu-id="a3db9-124">Logga in med en icke-lådan eller nya skift.</span><span class="sxs-lookup"><span data-stu-id="a3db9-124">Log on with a non-drawer operation or New shift.</span></span>
        - <span data-ttu-id="a3db9-125">Välj en tid klockan.</span><span class="sxs-lookup"><span data-stu-id="a3db9-125">Select a Time Clock operation.</span></span>
        - <span data-ttu-id="a3db9-126">Välj önskad funktion:</span><span class="sxs-lookup"><span data-stu-id="a3db9-126">Select a desired operation:</span></span>

            - <span data-ttu-id="a3db9-127">Instämpling</span><span class="sxs-lookup"><span data-stu-id="a3db9-127">Clock-in</span></span>
            - <span data-ttu-id="a3db9-128">Avbrott för arbete</span><span class="sxs-lookup"><span data-stu-id="a3db9-128">Break for Work</span></span>
            - <span data-ttu-id="a3db9-129">Lunchrast</span><span class="sxs-lookup"><span data-stu-id="a3db9-129">Break for Lunch</span></span>
            - <span data-ttu-id="a3db9-130">Utstämpling</span><span class="sxs-lookup"><span data-stu-id="a3db9-130">Clock-out</span></span>

        <table>
        <thead>
        <tr>
        <th><span data-ttu-id="a3db9-131">Aktuell status</span><span class="sxs-lookup"><span data-stu-id="a3db9-131">Current state</span></span></th>
        <th><span data-ttu-id="a3db9-132">Tillgängliga funktioner</span><span class="sxs-lookup"><span data-stu-id="a3db9-132">Available operations</span></span></th>
        </tr>
        </thead>
        <tbody>
        <tr>
        <td><span data-ttu-id="a3db9-133">Instämpling</span><span class="sxs-lookup"><span data-stu-id="a3db9-133">Clock-in</span></span></td>
        <td>
        <ul>
        <li><span data-ttu-id="a3db9-134">Avbrott för arbete</span><span class="sxs-lookup"><span data-stu-id="a3db9-134">Break for Work</span></span></li>
        <li><span data-ttu-id="a3db9-135">Lunchrast</span><span class="sxs-lookup"><span data-stu-id="a3db9-135">Break for Lunch</span></span></li>
        <li><span data-ttu-id="a3db9-136">Utstämpling</span><span class="sxs-lookup"><span data-stu-id="a3db9-136">Clock-out</span></span></li>
        </ul>
        </td>
        </tr>
        <tr>
        <td><span data-ttu-id="a3db9-137">Avbrott för arbete</span><span class="sxs-lookup"><span data-stu-id="a3db9-137">Break for Work</span></span></td>
        <td><span data-ttu-id="a3db9-138">Instämpling</span><span class="sxs-lookup"><span data-stu-id="a3db9-138">Clock-in</span></span></td>
        </tr>
        <tr>
        <td><span data-ttu-id="a3db9-139">Lunchrast</span><span class="sxs-lookup"><span data-stu-id="a3db9-139">Break for Lunch</span></span></td>
        <td><span data-ttu-id="a3db9-140">Instämpling</span><span class="sxs-lookup"><span data-stu-id="a3db9-140">Clock-in</span></span></td>
        </tr>
        <tr>
        <td><span data-ttu-id="a3db9-141">Utstämpling</span><span class="sxs-lookup"><span data-stu-id="a3db9-141">Clock-out</span></span></td>
        <td><span data-ttu-id="a3db9-142">Instämpling</span><span class="sxs-lookup"><span data-stu-id="a3db9-142">Clock-in</span></span></td>
        </tr>
        </tbody>
        </table>

        <span data-ttu-id="a3db9-143">[![TimeClockStates](./media/timeclockstates.png)](./media/timeclockstates.png)</span><span class="sxs-lookup"><span data-stu-id="a3db9-143">[![TimeClockStates](./media/timeclockstates.png)](./media/timeclockstates.png)</span></span>

- <span data-ttu-id="a3db9-144">Visa bekräftelsemeddelandet och verifiera att den aktuella aktivitet tid är korrekt.</span><span class="sxs-lookup"><span data-stu-id="a3db9-144">View the confirmation message, and validate that the current activity time is correct.</span></span>
- <span data-ttu-id="a3db9-145">Loggbok:</span><span class="sxs-lookup"><span data-stu-id="a3db9-145">Logbook:</span></span>

    - <span data-ttu-id="a3db9-146">Klicka på **Loggbok för** att visa tid klockan aktivitet.</span><span class="sxs-lookup"><span data-stu-id="a3db9-146">Click **Logbook** to view time clock activity.</span></span>
    - <span data-ttu-id="a3db9-147">Använd filter för att välja olika tidfönster.</span><span class="sxs-lookup"><span data-stu-id="a3db9-147">Use time filters to select different time windows.</span></span>
    - <span data-ttu-id="a3db9-148">Om du arbetar hos flera butiker kan du se din tidsregistreringar från alla butiker där du registrerade tid.</span><span class="sxs-lookup"><span data-stu-id="a3db9-148">If you work at multiple store locations, you see your time registrations from all the stores where you recorded time.</span></span> <span data-ttu-id="a3db9-149">Du kan använda butiken filter för att visa tidsregistreringar från en vald butik.</span><span class="sxs-lookup"><span data-stu-id="a3db9-149">You can use the store filter to view time registrations from a selected store.</span></span>

- <span data-ttu-id="a3db9-150">Olika tidszoner:</span><span class="sxs-lookup"><span data-stu-id="a3db9-150">Different time zones:</span></span>

    - <span data-ttu-id="a3db9-151">Om du från en annan plats (för kassören loggbok, eller genom att använda **Visa timeclock poster** för en chef scenario) och platsen är i en annan tidszon, tid som du ser, finnas görat om till din lokala tidzon.</span><span class="sxs-lookup"><span data-stu-id="a3db9-151">If you view time from a different location (for the cashier logbook, or by using **View timeclock entries** for a manager scenario), and that location is in a different time zone, the time records that you see are converted to your local time zone.</span></span> <span data-ttu-id="a3db9-152">Du är till exempel chef för två butiker, en i Arizona och den andra i Nevada.</span><span class="sxs-lookup"><span data-stu-id="a3db9-152">For example, you are a manager for two stores, one in Arizona and the other in Nevada.</span></span> <span data-ttu-id="a3db9-153">En kassör registrerar en instämpling klockan 09:00</span><span class="sxs-lookup"><span data-stu-id="a3db9-153">A cashier registers a clock-in at 9:00 A.M.</span></span> <span data-ttu-id="a3db9-154">i Arizona.</span><span class="sxs-lookup"><span data-stu-id="a3db9-154">in Arizona.</span></span> <span data-ttu-id="a3db9-155">I det ögonblicket i Nevada är 08.00.</span><span class="sxs-lookup"><span data-stu-id="a3db9-155">At that moment, the time in Nevada is 8:00 A.M.</span></span> <span data-ttu-id="a3db9-156">Därför, om du är i Nevada lagra och titta på gång inskrivningurkunder, projekttid är markerade som 08.00</span><span class="sxs-lookup"><span data-stu-id="a3db9-156">Therefore, if you are in the Nevada store and look at time registration records, the time registration is marked as 8 A.M.</span></span>

## <a name="view-worker-time-registrations"></a><span data-ttu-id="a3db9-157">Visa arbetstidsregistrering</span><span class="sxs-lookup"><span data-stu-id="a3db9-157">View worker time registrations</span></span>

### <a name="view-worker-time-registrations-and-filter-by-store-or-activity-type"></a><span data-ttu-id="a3db9-158">Visa arbetstagaren tidsregistreringar och filtrera genom butik eller aktivitetstyp</span><span class="sxs-lookup"><span data-stu-id="a3db9-158">View worker time registrations, and filter by store or activity type</span></span>

<span data-ttu-id="a3db9-159">På POS:</span><span class="sxs-lookup"><span data-stu-id="a3db9-159">On POS:</span></span>

- <span data-ttu-id="a3db9-160">Välj **Visa timeclock poster**.</span><span class="sxs-lookup"><span data-stu-id="a3db9-160">Select **View timeclock entries**.</span></span>
- <span data-ttu-id="a3db9-161">Du ser tid klocka registrering verksamheter från alla anställda som är tilldelade till samma butiker som du tilldelats.</span><span class="sxs-lookup"><span data-stu-id="a3db9-161">You see time clock registration activities from all workers that are assigned to the same stores that you're assigned to.</span></span>
- <span data-ttu-id="a3db9-162">Du kan använda aktivitetstyp och lagra filter för att filtrera på tidsregistreringar.</span><span class="sxs-lookup"><span data-stu-id="a3db9-162">You can use the activity type and store filters to filter on time registrations.</span></span>

## <a name="process-and-manage-time-registrations"></a><span data-ttu-id="a3db9-163">Bearbeta och hantera tidsregistreringar</span><span class="sxs-lookup"><span data-stu-id="a3db9-163">Process and manage time registrations</span></span>

<span data-ttu-id="a3db9-164">En Retail-användare följer arbetsgången för att beräkna, godkänna och överföra tidsregistreringar till lönesystemet.</span><span class="sxs-lookup"><span data-stu-id="a3db9-164">A Retail user follows the workflow to calculate, approve, and transfer time registrations to payroll.</span></span>

### <a name="primary-operations"></a><span data-ttu-id="a3db9-165">Primära verksamheter</span><span class="sxs-lookup"><span data-stu-id="a3db9-165">Primary operations</span></span>

- <span data-ttu-id="a3db9-166">Beräkna</span><span class="sxs-lookup"><span data-stu-id="a3db9-166">Calculate</span></span>
- <span data-ttu-id="a3db9-167">Godkänn</span><span class="sxs-lookup"><span data-stu-id="a3db9-167">Approve</span></span>
- <span data-ttu-id="a3db9-168">Skicka till lönesystem</span><span class="sxs-lookup"><span data-stu-id="a3db9-168">Submit to payroll</span></span>

### <a name="other-common-operations"></a><span data-ttu-id="a3db9-169">Andra gemensamma åtgärder</span><span class="sxs-lookup"><span data-stu-id="a3db9-169">Other common operations</span></span>

- <span data-ttu-id="a3db9-170">Bulk klocka-ut</span><span class="sxs-lookup"><span data-stu-id="a3db9-170">Bulk Clock-out</span></span>
- <span data-ttu-id="a3db9-171">Registrera frånvaro</span><span class="sxs-lookup"><span data-stu-id="a3db9-171">Register Absence</span></span>

<span data-ttu-id="a3db9-172">Läs mer om hur du bearbetar registreringar för tid och närvaro i [Bearbeta registreringar för tid och närvaro](https://technet.microsoft.com/library/aa573180.aspx).</span><span class="sxs-lookup"><span data-stu-id="a3db9-172">For more information about how to process time and attendance registrations, see [Process time and attendance registrations](https://technet.microsoft.com/library/aa573180.aspx).</span></span>
