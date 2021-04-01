---
title: Tids- och närvarohantering i Retail
description: Det här avsnittet beskriver scenarierna som stöds för tids- och närvarohantering i detaljhandel i Dynamics 365 Commerce.
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
ms.custom: 62813
ms.assetid: 821994a6-cd29-45a3-a526-ce204064f080
ms.search.region: global
ms.search.industry: Retail
ms.author: aamiral
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 28f4f72cd1272bd4562a58e343e50157143fac2c
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5254923"
---
# <a name="time-and-attendance-management-in-retail"></a><span data-ttu-id="32764-103">Tids- och närvarohantering i Retail</span><span class="sxs-lookup"><span data-stu-id="32764-103">Time and attendance management in Retail</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="32764-104">Det här avsnittet beskriver scenarierna som stöds för tids- och närvarohantering i detaljhandel i Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="32764-104">This topic describes the scenarios that are supported for time and attendance management in Dynamics 365 Commerce.</span></span>

## <a name="manage-worker-setup-and-scheduling"></a><span data-ttu-id="32764-105">Hantera inställningar för arbetare och schemaläggning</span><span class="sxs-lookup"><span data-stu-id="32764-105">Manage worker setup and scheduling</span></span>

### <a name="initial-configuration"></a><span data-ttu-id="32764-106"> Ursprunglig konfiguration</span><span class="sxs-lookup"><span data-stu-id="32764-106">Initial configuration</span></span>

- <span data-ttu-id="32764-107">Kör guiden för konfiguration.</span><span class="sxs-lookup"><span data-stu-id="32764-107">Run the configuration wizard.</span></span>
- <span data-ttu-id="32764-108">Registrera arbetstagare som projekttid arbetstagare.</span><span class="sxs-lookup"><span data-stu-id="32764-108">Register workers as time registration workers.</span></span>

### <a name="plan-worker-schedules"></a><span data-ttu-id="32764-109">Planen arbetstagaren scheman</span><span class="sxs-lookup"><span data-stu-id="32764-109">Plan worker schedules</span></span>

- <span data-ttu-id="32764-110">Använda profiler med arbete planerare.</span><span class="sxs-lookup"><span data-stu-id="32764-110">Apply profiles by using the work planner.</span></span> <span data-ttu-id="32764-111">Mer information finns i [Använd profiler med arbetsplanering](https://technet.microsoft.com/library/aa551234.aspx).</span><span class="sxs-lookup"><span data-stu-id="32764-111">For more information, see [Apply profiles using work planner](https://technet.microsoft.com/library/aa551234.aspx).</span></span>

<span data-ttu-id="32764-112">Mer information om konfigurationsstegen finns i [inställning av tid och närvaro](https://technet.microsoft.com/library/aa496971.aspx).</span><span class="sxs-lookup"><span data-stu-id="32764-112">For information about the configuration steps, see [Setting up time and attendance](https://technet.microsoft.com/library/aa496971.aspx).</span></span>

### <a name="commerce-specific-configuration"></a><span data-ttu-id="32764-113">Handelsspecifik konfiguration</span><span class="sxs-lookup"><span data-stu-id="32764-113">Commerce-specific configuration</span></span>

- <span data-ttu-id="32764-114">Aktivera en funktion profil för klocka, för arbetstagare som du vill aktivera tidsregistreringar.</span><span class="sxs-lookup"><span data-stu-id="32764-114">Enable a functionality profile for Time Clock, for workers that you want to enable time registrations for.</span></span> <span data-ttu-id="32764-115">Klicka på **Kassafunktionsprofiler** &gt; **Funktioner** &gt; **Tidsregistreringar vid kassa** &gt; **Aktivera tidsregistreringar**.</span><span class="sxs-lookup"><span data-stu-id="32764-115">Click **POS functionality profiles** &gt; **Functions** &gt; **POS time registrations** &gt; **Enable time registrations**.</span></span>
- <span data-ttu-id="32764-116">Konfigurera point of sale (POS) behörigheter grupper att visa timeclock poster tillstånd.</span><span class="sxs-lookup"><span data-stu-id="32764-116">Configure point of sale (POS) permissions groups to enable the View timeclock entries permission.</span></span> <span data-ttu-id="32764-117">Detta tillstånd kan en användare visa tid klocka registreringar av andra arbetstagare i affären (och från alla andra som användaren är kopplad till, via adressboken).</span><span class="sxs-lookup"><span data-stu-id="32764-117">This permission lets a user view the time clock registrations of other workers in the store (and from any other store that the user is associated with, via the address book).</span></span> <span data-ttu-id="32764-118">Du kanske vill aktivera detta tillstånd för en chef roll men inte för en kassör roll.</span><span class="sxs-lookup"><span data-stu-id="32764-118">You might want to enable this permission for a manager role but not for a cashier role.</span></span> <span data-ttu-id="32764-119">Klicka på **Kassabehörighetsgrupper** &gt; **Visa stämpelklocksregistreringar**.</span><span class="sxs-lookup"><span data-stu-id="32764-119">Click **POS permission groups** &gt; **View time clock entries**.</span></span>

## <a name="register-time"></a><span data-ttu-id="32764-120">Kassatid</span><span class="sxs-lookup"><span data-stu-id="32764-120">Register time</span></span>

### <a name="cashier-and-non-cashier-time-registrations"></a><span data-ttu-id="32764-121">Kassa och icke-kassa tidsregistreringar</span><span class="sxs-lookup"><span data-stu-id="32764-121">Cashier and non-cashier time registrations</span></span>

- <span data-ttu-id="32764-122">På POS:</span><span class="sxs-lookup"><span data-stu-id="32764-122">On POS:</span></span>

    - <span data-ttu-id="32764-123">Klocka-operationer:</span><span class="sxs-lookup"><span data-stu-id="32764-123">Clock-in operations:</span></span>

        - <span data-ttu-id="32764-124">Logga in med en icke-lådan eller nya skift.</span><span class="sxs-lookup"><span data-stu-id="32764-124">Log on with a non-drawer operation or New shift.</span></span>
        - <span data-ttu-id="32764-125">Välj en tid klockan.</span><span class="sxs-lookup"><span data-stu-id="32764-125">Select a Time Clock operation.</span></span>
        - <span data-ttu-id="32764-126">Välj önskad funktion:</span><span class="sxs-lookup"><span data-stu-id="32764-126">Select a desired operation:</span></span>

            - <span data-ttu-id="32764-127">Instämpling</span><span class="sxs-lookup"><span data-stu-id="32764-127">Clock-in</span></span>
            - <span data-ttu-id="32764-128">Avbrott för arbete</span><span class="sxs-lookup"><span data-stu-id="32764-128">Break for Work</span></span>
            - <span data-ttu-id="32764-129">Lunchrast</span><span class="sxs-lookup"><span data-stu-id="32764-129">Break for Lunch</span></span>
            - <span data-ttu-id="32764-130">Utstämpling</span><span class="sxs-lookup"><span data-stu-id="32764-130">Clock-out</span></span>

        <table>
        <thead>
        <tr>
        <th><span data-ttu-id="32764-131">Aktuell status</span><span class="sxs-lookup"><span data-stu-id="32764-131">Current state</span></span></th>
        <th><span data-ttu-id="32764-132">Tillgängliga funktioner</span><span class="sxs-lookup"><span data-stu-id="32764-132">Available operations</span></span></th>
        </tr>
        </thead>
        <tbody>
        <tr>
        <td><span data-ttu-id="32764-133">Instämpling</span><span class="sxs-lookup"><span data-stu-id="32764-133">Clock-in</span></span></td>
        <td>
        <ul>
        <li><span data-ttu-id="32764-134">Avbrott för arbete</span><span class="sxs-lookup"><span data-stu-id="32764-134">Break for Work</span></span></li>
        <li><span data-ttu-id="32764-135">Lunchrast</span><span class="sxs-lookup"><span data-stu-id="32764-135">Break for Lunch</span></span></li>
        <li><span data-ttu-id="32764-136">Utstämpling</span><span class="sxs-lookup"><span data-stu-id="32764-136">Clock-out</span></span></li>
        </ul>
        </td>
        </tr>
        <tr>
        <td><span data-ttu-id="32764-137">Avbrott för arbete</span><span class="sxs-lookup"><span data-stu-id="32764-137">Break for Work</span></span></td>
        <td><span data-ttu-id="32764-138">Instämpling</span><span class="sxs-lookup"><span data-stu-id="32764-138">Clock-in</span></span></td>
        </tr>
        <tr>
        <td><span data-ttu-id="32764-139">Lunchrast</span><span class="sxs-lookup"><span data-stu-id="32764-139">Break for Lunch</span></span></td>
        <td><span data-ttu-id="32764-140">Instämpling</span><span class="sxs-lookup"><span data-stu-id="32764-140">Clock-in</span></span></td>
        </tr>
        <tr>
        <td><span data-ttu-id="32764-141">Utstämpling</span><span class="sxs-lookup"><span data-stu-id="32764-141">Clock-out</span></span></td>
        <td><span data-ttu-id="32764-142">Instämpling</span><span class="sxs-lookup"><span data-stu-id="32764-142">Clock-in</span></span></td>
        </tr>
        </tbody>
        </table>

        <span data-ttu-id="32764-143">[![Stämpelklockstillstånd](./media/timeclockstates.png)](./media/timeclockstates.png)</span><span class="sxs-lookup"><span data-stu-id="32764-143">[![Time Clock States](./media/timeclockstates.png)](./media/timeclockstates.png)</span></span>

- <span data-ttu-id="32764-144">Visa bekräftelsemeddelandet och verifiera att den aktuella aktivitet tid är korrekt.</span><span class="sxs-lookup"><span data-stu-id="32764-144">View the confirmation message, and validate that the current activity time is correct.</span></span>
- <span data-ttu-id="32764-145">Loggbok:</span><span class="sxs-lookup"><span data-stu-id="32764-145">Logbook:</span></span>

    - <span data-ttu-id="32764-146">Klicka på **Loggbok för** att visa tid klockan aktivitet.</span><span class="sxs-lookup"><span data-stu-id="32764-146">Click **Logbook** to view time clock activity.</span></span>
    - <span data-ttu-id="32764-147">Använd filter för att välja olika tidfönster.</span><span class="sxs-lookup"><span data-stu-id="32764-147">Use time filters to select different time windows.</span></span>
    - <span data-ttu-id="32764-148">Om du arbetar hos flera butiker kan du se din tidsregistreringar från alla butiker där du registrerade tid.</span><span class="sxs-lookup"><span data-stu-id="32764-148">If you work at multiple store locations, you see your time registrations from all the stores where you recorded time.</span></span> <span data-ttu-id="32764-149">Du kan använda butiken filter för att visa tidsregistreringar från en vald butik.</span><span class="sxs-lookup"><span data-stu-id="32764-149">You can use the store filter to view time registrations from a selected store.</span></span>

- <span data-ttu-id="32764-150">Olika tidszoner:</span><span class="sxs-lookup"><span data-stu-id="32764-150">Different time zones:</span></span>

    - <span data-ttu-id="32764-151">Om du från en annan plats (för kassören loggbok, eller genom att använda **Visa timeclock poster** för en chef scenario) och platsen är i en annan tidszon, tid som du ser, finnas görat om till din lokala tidzon.</span><span class="sxs-lookup"><span data-stu-id="32764-151">If you view time from a different location (for the cashier logbook, or by using **View timeclock entries** for a manager scenario), and that location is in a different time zone, the time records that you see are converted to your local time zone.</span></span> <span data-ttu-id="32764-152">Du är till exempel chef för två butiker, en i Arizona och den andra i Nevada.</span><span class="sxs-lookup"><span data-stu-id="32764-152">For example, you are a manager for two stores, one in Arizona and the other in Nevada.</span></span> <span data-ttu-id="32764-153">En kassör registrerar en instämpling klockan 09:00</span><span class="sxs-lookup"><span data-stu-id="32764-153">A cashier registers a clock-in at 9:00 A.M.</span></span> <span data-ttu-id="32764-154">i Arizona.</span><span class="sxs-lookup"><span data-stu-id="32764-154">in Arizona.</span></span> <span data-ttu-id="32764-155">I det ögonblicket i Nevada är 08.00.</span><span class="sxs-lookup"><span data-stu-id="32764-155">At that moment, the time in Nevada is 8:00 A.M.</span></span> <span data-ttu-id="32764-156">Därför, om du är i Nevada lagra och titta på gång inskrivningurkunder, projekttid är markerade som 08.00</span><span class="sxs-lookup"><span data-stu-id="32764-156">Therefore, if you are in the Nevada store and look at time registration records, the time registration is marked as 8 A.M.</span></span>

## <a name="view-worker-time-registrations"></a><span data-ttu-id="32764-157">Visa arbetstidsregistrering</span><span class="sxs-lookup"><span data-stu-id="32764-157">View worker time registrations</span></span>

### <a name="view-worker-time-registrations-and-filter-by-store-or-activity-type"></a><span data-ttu-id="32764-158">Visa arbetstagaren tidsregistreringar och filtrera genom butik eller aktivitetstyp</span><span class="sxs-lookup"><span data-stu-id="32764-158">View worker time registrations, and filter by store or activity type</span></span>

<span data-ttu-id="32764-159">På POS:</span><span class="sxs-lookup"><span data-stu-id="32764-159">On POS:</span></span>

- <span data-ttu-id="32764-160">Välj **Visa timeclock poster**.</span><span class="sxs-lookup"><span data-stu-id="32764-160">Select **View timeclock entries**.</span></span>
- <span data-ttu-id="32764-161">Du ser tid klocka registrering verksamheter från alla anställda som är tilldelade till samma butiker som du tilldelats.</span><span class="sxs-lookup"><span data-stu-id="32764-161">You see time clock registration activities from all workers that are assigned to the same stores that you're assigned to.</span></span>
- <span data-ttu-id="32764-162">Du kan använda aktivitetstyp och lagra filter för att filtrera på tidsregistreringar.</span><span class="sxs-lookup"><span data-stu-id="32764-162">You can use the activity type and store filters to filter on time registrations.</span></span>

## <a name="process-and-manage-time-registrations"></a><span data-ttu-id="32764-163">Bearbeta och hantera tidsregistreringar</span><span class="sxs-lookup"><span data-stu-id="32764-163">Process and manage time registrations</span></span>

<span data-ttu-id="32764-164">En Commerce-användare följer arbetsgången för att beräkna, godkänna och överföra tidsregistreringar till lönesystemet.</span><span class="sxs-lookup"><span data-stu-id="32764-164">A Commerce user follows the workflow to calculate, approve, and transfer time registrations to payroll.</span></span>

### <a name="primary-operations"></a><span data-ttu-id="32764-165">Primära verksamheter</span><span class="sxs-lookup"><span data-stu-id="32764-165">Primary operations</span></span>

- <span data-ttu-id="32764-166">Beräkna</span><span class="sxs-lookup"><span data-stu-id="32764-166">Calculate</span></span>
- <span data-ttu-id="32764-167">Godkänn</span><span class="sxs-lookup"><span data-stu-id="32764-167">Approve</span></span>
- <span data-ttu-id="32764-168">Skicka till lönesystem</span><span class="sxs-lookup"><span data-stu-id="32764-168">Submit to payroll</span></span>

### <a name="other-common-operations"></a><span data-ttu-id="32764-169">Andra gemensamma åtgärder</span><span class="sxs-lookup"><span data-stu-id="32764-169">Other common operations</span></span>

- <span data-ttu-id="32764-170">Bulk klocka-ut</span><span class="sxs-lookup"><span data-stu-id="32764-170">Bulk Clock-out</span></span>
- <span data-ttu-id="32764-171">Registrera frånvaro</span><span class="sxs-lookup"><span data-stu-id="32764-171">Register Absence</span></span>

<span data-ttu-id="32764-172">Läs mer om hur du bearbetar registreringar för tid och närvaro i [Bearbeta registreringar för tid och närvaro](https://technet.microsoft.com/library/aa573180.aspx).</span><span class="sxs-lookup"><span data-stu-id="32764-172">For more information about how to process time and attendance registrations, see [Process time and attendance registrations](https://technet.microsoft.com/library/aa573180.aspx).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]