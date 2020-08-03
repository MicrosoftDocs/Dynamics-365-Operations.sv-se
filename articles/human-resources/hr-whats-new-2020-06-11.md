---
title: Nyheter och ändringar i Dynamics 365 Human Resources (11 juni 2020)
description: Det här ämnet beskriver nya eller ändrade funktioner i Microsoft Dynamics 365 Human Resources.
author: Darinkramer
manager: AnnBe
ms.date: 6/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2020-06-11
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: cba6e48899ec39fc4de6656f8151a42b8aa43261
ms.sourcegitcommit: bd9ff0d28718d535356ffbe1cffaaf60310dd430
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/13/2020
ms.locfileid: "3555205"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-june-11-2020"></a><span data-ttu-id="c1311-103">Nyheter och ändringar i Dynamics 365 Human Resources (11 juni 2020)</span><span class="sxs-lookup"><span data-stu-id="c1311-103">What's new or changed in Dynamics 365 Human Resources (June 11, 2020)</span></span>

<span data-ttu-id="c1311-104">Den här artikeln innehåller en beskrivning av nya eller ändrade funktioner i Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="c1311-104">This article describes features that are either new or changed in Dynamics 365 Human Resources.</span></span> <span data-ttu-id="c1311-105">Ändringarna tillämpas på versionsnummer 8.1.3316.</span><span class="sxs-lookup"><span data-stu-id="c1311-105">Changes apply to build number 8.1.3316.</span></span> <span data-ttu-id="c1311-106">Siffror inom parenteser i vissa rubriker refererar till LCS-supportnummer för referens.</span><span class="sxs-lookup"><span data-stu-id="c1311-106">The numbers in parentheses in some headings refer to LCS support numbers for reference.</span></span>

## <a name="streamlined-employee-form-sometimes-causes-child-form-close-x-buttons-to-stop-working-442369"></a><span data-ttu-id="c1311-107">Ett strömlinjeformat medarbetarformulär ger ibland det underordnade formuläret att stänga (X) knappar för att sluta fungera (442369)</span><span class="sxs-lookup"><span data-stu-id="c1311-107">Streamlined employee form sometimes causes child form close (X) buttons to stop working (442369)</span></span>

<span data-ttu-id="c1311-108">När det nya formuläret **Arbetare** aktiverades fungerade inte stängningsknappen (**X**) ibland i underordnade formulär.</span><span class="sxs-lookup"><span data-stu-id="c1311-108">When the new **Worker** form was enabled, the close (**X**) button occasionally didn't work on child forms.</span></span> <span data-ttu-id="c1311-109">Det här problemet var tillfälligt.</span><span class="sxs-lookup"><span data-stu-id="c1311-109">This problem was intermittent.</span></span> <span data-ttu-id="c1311-110">Du kan stänga formuläret efter att ha lämnat det och sedan komma tillbaka till det.</span><span class="sxs-lookup"><span data-stu-id="c1311-110">You could close the form after leaving and coming back to it.</span></span> <span data-ttu-id="c1311-111">Du kan till exempel välja ett menyalternativ till vänster och navigera tillbaka till formuläret **Arbetare** och stänga det.</span><span class="sxs-lookup"><span data-stu-id="c1311-111">For example, you could select a menu item on the left, and navigate back to the **Worker** form, and then close it.</span></span> <span data-ttu-id="c1311-112">Det här problemet åtgärdas med den här veckans utgivningsversion.</span><span class="sxs-lookup"><span data-stu-id="c1311-112">This week's release fixes this problem.</span></span> 

## <a name="the-worker-personal-contact-person-entity-doesnt-export-personal-contacts-with-a-parent-relationship-type"></a><span data-ttu-id="c1311-113">Entiteten Personlig kontaktperson för medarbetare exporterar inte personliga kontakter med en överordnad relationstyp</span><span class="sxs-lookup"><span data-stu-id="c1311-113">The Worker personal contact person entity doesn't export personal contacts with a parent relationship type</span></span>

<span data-ttu-id="c1311-114">Med den här versionen exporterar entiteten **Personlig kontaktperson för medarbetare** alla relationstyper.</span><span class="sxs-lookup"><span data-stu-id="c1311-114">With this release, the **Worker personal contact person** entity exports all relationship types.</span></span>

## <a name="the-hcmpositionworkerassignmentv2entity-should-be-part-of-the-ceridian-payroll-integration-package-by-default-448506"></a><span data-ttu-id="c1311-115">HcmPositionWorkerAssignmentV2Entity bör ingå i Ceridian löneintegreringspaket som standard (448506)</span><span class="sxs-lookup"><span data-stu-id="c1311-115">The HcmPositionWorkerAssignmentV2Entity should be part of the Ceridian payroll integration package by default (448506)</span></span>

<span data-ttu-id="c1311-116">Med den här ändringen inkluderas **HcmPositionWorkerAssignmentV2Entity** i Ceridian löneintegreringspaket.</span><span class="sxs-lookup"><span data-stu-id="c1311-116">With this change, the **HcmPositionWorkerAssignmentV2Entity** is included in the Ceridian payroll integration package.</span></span>

## <a name="in-preview"></a><span data-ttu-id="c1311-117">I förhandsgranskning</span><span class="sxs-lookup"><span data-stu-id="c1311-117">In preview</span></span>

## <a name="database-logging"></a><span data-ttu-id="c1311-118">Databasloggning</span><span class="sxs-lookup"><span data-stu-id="c1311-118">Database logging</span></span>

<span data-ttu-id="c1311-119">Med funktionen för databasloggning kan du bestämma vilka register och fält som ska övervakas.</span><span class="sxs-lookup"><span data-stu-id="c1311-119">The database logging feature allows you to determine which tables and fields to monitor.</span></span> <span data-ttu-id="c1311-120">Du kan också bestämma vilka händelser som ska utlösa ändringsspårningen.</span><span class="sxs-lookup"><span data-stu-id="c1311-120">It also lets you determine the events that should trigger change tracking.</span></span> <span data-ttu-id="c1311-121">Du använder funktionerna för databasloggning för att visa dessa ändringar över tiden.</span><span class="sxs-lookup"><span data-stu-id="c1311-121">You use database logging capabilities to see these changes over time.</span></span> <span data-ttu-id="c1311-122">Mer information finns i [Konfigurera och hantera databasloggning](hr-admin-database-logging.md).</span><span class="sxs-lookup"><span data-stu-id="c1311-122">For more information, see [Configure and manage database logging](hr-admin-database-logging.md).</span></span>

## <a name="human-resources-application-in-teams"></a><span data-ttu-id="c1311-123">Personalapp i Teams</span><span class="sxs-lookup"><span data-stu-id="c1311-123">Human Resources application in Teams</span></span>

<span data-ttu-id="c1311-124">Medarbetare kan visa och begära ledighet från arbetet inom Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="c1311-124">Employees can view and request time away from work within Microsoft Teams.</span></span> <span data-ttu-id="c1311-125">De kan samverka med en bot för att skapa tjänstledighetsansökan.</span><span class="sxs-lookup"><span data-stu-id="c1311-125">They can interact with a bot to create leave requests.</span></span> <span data-ttu-id="c1311-126">Mer information finns [i personalapp i Teams](https://go.microsoft.com/fwlink/?linkid=2127841).</span><span class="sxs-lookup"><span data-stu-id="c1311-126">For more information, see [Human Resources app in Teams](https://go.microsoft.com/fwlink/?linkid=2127841).</span></span> 

## <a name="data-management-framework-dmf-entities-for-benefits-management"></a><span data-ttu-id="c1311-127">DMF-enheter (Data Management Framework) för förmånshantering</span><span class="sxs-lookup"><span data-stu-id="c1311-127">Data management framework (DMF) entities for Benefits management</span></span>
 
<span data-ttu-id="c1311-128">Entiteter för hantering av förmåner släpps.</span><span class="sxs-lookup"><span data-stu-id="c1311-128">Benefits management entities are releasing.</span></span> <span data-ttu-id="c1311-129">DMF-enheter gör det möjligt att importera och exportera data för att enkelt konfigurera hantering av förmåner.</span><span class="sxs-lookup"><span data-stu-id="c1311-129">DMF entities allow you to import and export data to easily configure benefits management.</span></span> <span data-ttu-id="c1311-130">En mall för hantering av förmåner kan användas för att flytta data.</span><span class="sxs-lookup"><span data-stu-id="c1311-130">A Benefits management template will be available to move data.</span></span> <span data-ttu-id="c1311-131">Mallen exporterar och importerar data sekventiellt för att respektera databeroenden.</span><span class="sxs-lookup"><span data-stu-id="c1311-131">The template exports and imports the data sequentially to respect data dependencies.</span></span>

## <a name="buy-and-sell-leave"></a><span data-ttu-id="c1311-132">Köpa och sälja tjänstledighet</span><span class="sxs-lookup"><span data-stu-id="c1311-132">Buy and sell leave</span></span> 

<span data-ttu-id="c1311-133">Vissa organisationer ger en förmån som gör det möjligt för medarbetare att köpa eller sälja sin tjänstledighet.</span><span class="sxs-lookup"><span data-stu-id="c1311-133">Some organizations provide a benefit that allows employees to buy or sell their leave.</span></span> <span data-ttu-id="c1311-134">Den här processen hanteras ofta manuellt.</span><span class="sxs-lookup"><span data-stu-id="c1311-134">This process is often managed manually.</span></span> <span data-ttu-id="c1311-135">Med den här funktionen automatiseras hanteringen av principer och begäranden för personalavdelningen.</span><span class="sxs-lookup"><span data-stu-id="c1311-135">This feature automates managing policies and requests for the HR department.</span></span> <span data-ttu-id="c1311-136">Det effektiviserar hanteringsprocessen och hjälper till att eliminera misstag.</span><span class="sxs-lookup"><span data-stu-id="c1311-136">It streamlines the leave management process and helps eliminate mistakes.</span></span> <span data-ttu-id="c1311-137">Mer information finns i:</span><span class="sxs-lookup"><span data-stu-id="c1311-137">For more information, see:</span></span>

- [<span data-ttu-id="c1311-138">Hantera principer för köpa och sälja tjänstledighet</span><span class="sxs-lookup"><span data-stu-id="c1311-138">Manage buy and sell leave policies</span></span>](hr-leave-and-absence-manage-buy-and-sell-leave-policies.md)
- [<span data-ttu-id="c1311-139">Köpa och sälja tjänstledighet</span><span class="sxs-lookup"><span data-stu-id="c1311-139">Buy and sell leave</span></span>](hr-employee-self-service-buy-sell-leave.md)

## <a name="leave-accrual-for-a-single-company-or-single-plan"></a><span data-ttu-id="c1311-140">Lämna periodisering för ett enskilt företag eller en plan</span><span class="sxs-lookup"><span data-stu-id="c1311-140">Leave accrual for a single company or single plan</span></span>

<span data-ttu-id="c1311-141">Kunder kan bearbeta periodiseringar för ett enskilt företag eller en enskild plan för tjänstledighet och frånvaro.</span><span class="sxs-lookup"><span data-stu-id="c1311-141">Customers can process accruals for a single company or a single leave and absence plan.</span></span> <span data-ttu-id="c1311-142">Denna möjlighet ger klarhet i den periodiserade processen för kunder med olika tjänstledighetsår eller principer för periodisering av tjänstledighet.</span><span class="sxs-lookup"><span data-stu-id="c1311-142">This ability provides clarity into the accrual process for customers with different leave years or leave accrual policies.</span></span> <span data-ttu-id="c1311-143">Mer information finns i [tjänstledighet per företag eller per tjänstledighetsplan](hr-leave-and-absence-accrue.md#accrue-leave-per-company-or-per-leave-plan).</span><span class="sxs-lookup"><span data-stu-id="c1311-143">For more information, see [Accrue leave per company or per leave plan](hr-leave-and-absence-accrue.md#accrue-leave-per-company-or-per-leave-plan).</span></span>

## <a name="add-attachments-to-time-off-requests"></a><span data-ttu-id="c1311-144">Lägg till bifogade filer i ledighetsansökningar</span><span class="sxs-lookup"><span data-stu-id="c1311-144">Add attachments to time off requests</span></span>

<span data-ttu-id="c1311-145">Möjligheten att lägga till bilagor till godkända ansökan om tjänstledighet är viktigt i den aktuella COVID-19 miljön.</span><span class="sxs-lookup"><span data-stu-id="c1311-145">The ability to add attachments to approved leave requests is critical in the current COVID-19 environment.</span></span> <span data-ttu-id="c1311-146">Medarbetarna kan nu lägga till dessa bilagor.</span><span class="sxs-lookup"><span data-stu-id="c1311-146">Employees can now add these attachments.</span></span> <span data-ttu-id="c1311-147">De har också mer inblick i hur uppdateringar görs för att lämna förfrågningar.</span><span class="sxs-lookup"><span data-stu-id="c1311-147">They also have more insight into how updates are made to leave requests.</span></span> <span data-ttu-id="c1311-148">Mer information finns i [lägga till en bilaga till en befintlig begäran](hr-employee-self-service-request-time-off.md#add-an-attachment-to-an-existing-request).</span><span class="sxs-lookup"><span data-stu-id="c1311-148">For more information, see [Add an attachment to an existing request](hr-employee-self-service-request-time-off.md#add-an-attachment-to-an-existing-request).</span></span>

## <a name="add-reason-code-to-accrual-suspensions"></a><span data-ttu-id="c1311-149">Lägg till orsakskod för periodiserade avstängningar</span><span class="sxs-lookup"><span data-stu-id="c1311-149">Add reason code to accrual suspensions</span></span> 

<span data-ttu-id="c1311-150">Orsakskoder har lagts till den periodiserade avstängningen.</span><span class="sxs-lookup"><span data-stu-id="c1311-150">Reason codes have been added to the accrual suspension.</span></span>

## <a name="carry-forward-rules"></a><span data-ttu-id="c1311-151">Överför regler</span><span class="sxs-lookup"><span data-stu-id="c1311-151">Carry forward rules</span></span> 

<span data-ttu-id="c1311-152">Du kan ange en överför tjänstledighetstyp för överföringsaldon där överför justeringar överförs.</span><span class="sxs-lookup"><span data-stu-id="c1311-152">You can specify a carry forward leave type for carry forward balances where carry forward adjustments are transferred.</span></span> <span data-ttu-id="c1311-153">Om en medarbetare till exempel överförs 10 dagar kan du välja en annan tjänstledighetstyp för de 10 dagarna.</span><span class="sxs-lookup"><span data-stu-id="c1311-153">For example, if an employee carries forward 10 days, you can pick a different leave type for those 10 days.</span></span> <span data-ttu-id="c1311-154">Mer information finns i [konfigurera tjänstledighet och frånvarotyper](hr-leave-and-absence-types.md).</span><span class="sxs-lookup"><span data-stu-id="c1311-154">For more information, see [Configure leave and absence types](hr-leave-and-absence-types.md).</span></span>

## <a name="suspend-leave-accrual-for-specified-leave-types"></a><span data-ttu-id="c1311-155">Pausa tjänstledighetsperiodisering för angivna tjänstledighetstyper</span><span class="sxs-lookup"><span data-stu-id="c1311-155">Suspend leave accrual for specified leave types</span></span>

<span data-ttu-id="c1311-156">Du kan skapa en regel för att pausa tjänstledighetsperiodiseringar för medarbetare som har lämnat förfrågningar om obetald tjänstledighet.</span><span class="sxs-lookup"><span data-stu-id="c1311-156">You can create a rule to suspend leave accruals for employees with leave requests entered for unpaid leave.</span></span> <span data-ttu-id="c1311-157">Obetald tjänstledighet kan vara en typ, men behöver inte vara det.</span><span class="sxs-lookup"><span data-stu-id="c1311-157">Unpaid leave can be a type, but doesn't have to be.</span></span> <span data-ttu-id="c1311-158">Du kan pausa eventuell tjänstledighet baserat på annan tjänstledighetstyp.</span><span class="sxs-lookup"><span data-stu-id="c1311-158">You can suspend any leave based on another leave type.</span></span>

## <a name="dmf-entity-available-for-accrual-suspensions"></a><span data-ttu-id="c1311-159">DMF-enhet tillgänglig för periodiserade avstängningar</span><span class="sxs-lookup"><span data-stu-id="c1311-159">DMF entity available for accrual suspensions</span></span> 

<span data-ttu-id="c1311-160">Nu är en DMF-enhet tillgänglig för periodiserade avstängningar.</span><span class="sxs-lookup"><span data-stu-id="c1311-160">A DMF entity is now available for accrual suspensions.</span></span>

## <a name="coming-soon"></a><span data-ttu-id="c1311-161">Kommer snart</span><span class="sxs-lookup"><span data-stu-id="c1311-161">Coming soon</span></span>

## <a name="new-platform-capabilities"></a><span data-ttu-id="c1311-162">Nya plattformsfunktioner</span><span class="sxs-lookup"><span data-stu-id="c1311-162">New platform capabilities</span></span> 

<span data-ttu-id="c1311-163">Du kan göra fält obligatoriska genom att använda anpassningar.</span><span class="sxs-lookup"><span data-stu-id="c1311-163">You'll be able to make fields mandatory by using personalization.</span></span> <span data-ttu-id="c1311-164">Den här funktionen kräver att du aktiverar **sparade vyer**.</span><span class="sxs-lookup"><span data-stu-id="c1311-164">This feature will require you to enable **Saved views**.</span></span>

## <a name="configure-the-name-of-employee-self-service"></a><span data-ttu-id="c1311-165">Konfigurera namnet på självbetjäning för medarbetare</span><span class="sxs-lookup"><span data-stu-id="c1311-165">Configure the name of Employee self-service</span></span>

<span data-ttu-id="c1311-166">Ett nytt alternativ är tillgängligt i personalparametrarna för att uppdatera namnet på arbetsytan självbetjäning för medarbetare till självbetjäning.</span><span class="sxs-lookup"><span data-stu-id="c1311-166">A new option will be available in Human Resources parameters to update the name of the Employee self service workspace to Self service.</span></span> 

## <a name="see-also"></a><span data-ttu-id="c1311-167">Se även</span><span class="sxs-lookup"><span data-stu-id="c1311-167">See also</span></span>

[<span data-ttu-id="c1311-168">Nyheter och ändringar i Human Resources</span><span class="sxs-lookup"><span data-stu-id="c1311-168">What's new or changed in Human Resources</span></span>](hr-admin-whats-new.md)</br>
[<span data-ttu-id="c1311-169">Översikt över Dynamics 365 Human Resources 2019 utgivningsvåg 2</span><span class="sxs-lookup"><span data-stu-id="c1311-169">Overview of Dynamics 365 Human Resources 2019 release wave 2</span></span>](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[<span data-ttu-id="c1311-170">Uppdatera process</span><span class="sxs-lookup"><span data-stu-id="c1311-170">Update process</span></span>](hr-admin-setup-update-process.md)</br>
[<span data-ttu-id="c1311-171">Hantera funktioner</span><span class="sxs-lookup"><span data-stu-id="c1311-171">Manage features</span></span>](hr-admin-manage-features.md)