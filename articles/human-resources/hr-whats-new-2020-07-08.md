---
title: Nyheter och ändringar i Dynamics 365 Human Resources (08 juli 2020)
description: Det här ämnet beskriver nya eller ändrade funktioner i Microsoft Dynamics 365 Human Resources 8 juli 2020.
author: Darinkramer
manager: AnnBe
ms.date: 07/08/2020
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
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: d2f542195693e825391b85efc4a7e91fdfea3944
ms.sourcegitcommit: 2bcacef1e010c312f019dbf9740ce87d627848a7
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/20/2020
ms.locfileid: "3711902"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-july-8-2020"></a><span data-ttu-id="20179-103">Nyheter och ändringar i Dynamics 365 Human Resources (8 juli 2020)</span><span class="sxs-lookup"><span data-stu-id="20179-103">What's new or changed in Dynamics 365 Human Resources (July 8, 2020)</span></span>

<span data-ttu-id="20179-104">Det här ämnet beskriver nya eller ändrade funktioner i Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="20179-104">This topic describes features that are either new or changed in Dynamics 365 Human Resources.</span></span> <span data-ttu-id="20179-105">Ändringarna tillämpas på versionsnummer 8.1.3382.</span><span class="sxs-lookup"><span data-stu-id="20179-105">Changes apply to build number 8.1.3382.</span></span> <span data-ttu-id="20179-106">Siffror inom parenteser i vissa rubriker refererar till LCS-supportnummer för referens.</span><span class="sxs-lookup"><span data-stu-id="20179-106">The numbers in parentheses in some headings refer to LCS support numbers for reference.</span></span>

## <a name="database-logging"></a><span data-ttu-id="20179-107">Databasloggning</span><span class="sxs-lookup"><span data-stu-id="20179-107">Database logging</span></span>

<span data-ttu-id="20179-108">Databasloggning kan du bestämma vilka register och fält som ska övervakas.</span><span class="sxs-lookup"><span data-stu-id="20179-108">Database logging allows you to determine which tables and fields to monitor.</span></span> <span data-ttu-id="20179-109">Du kan också bestämma vilka händelser som ska utlösa ändringsspårningen.</span><span class="sxs-lookup"><span data-stu-id="20179-109">It also lets you determine the events that should trigger change tracking.</span></span> <span data-ttu-id="20179-110">Du använder funktionerna för databasloggning för att visa dessa ändringar över tiden.</span><span class="sxs-lookup"><span data-stu-id="20179-110">You use database logging capabilities to see these changes over time.</span></span> <span data-ttu-id="20179-111">Mer information finns i [Konfigurera och hantera databasloggning](hr-admin-database-logging.md).</span><span class="sxs-lookup"><span data-stu-id="20179-111">For more information, see [Configure and manage database logging](hr-admin-database-logging.md).</span></span>

## <a name="configure-the-name-of-employee-self-service"></a><span data-ttu-id="20179-112">Konfigurera namnet på självbetjäning för medarbetare</span><span class="sxs-lookup"><span data-stu-id="20179-112">Configure the name of Employee self service</span></span>

<span data-ttu-id="20179-113">I **personalparametrar** kan du nu ändra namnet på arbetsytan **självbetjäning för medarbetare** till **självservice**.</span><span class="sxs-lookup"><span data-stu-id="20179-113">In **Human Resources parameters**, you can now change the name of the **Employee self service** workspace to **Self service**.</span></span> <span data-ttu-id="20179-114">Mer information finns i [Ändra namn på arbetsytan för självbetjäning för medarbetare](hr-employee-self-service-workspace-name.md)</span><span class="sxs-lookup"><span data-stu-id="20179-114">For more information, see [Change Employee self service workspace name](hr-employee-self-service-workspace-name.md)</span></span>

## <a name="benefits-management-open-enrollment-access-outside-of-period"></a><span data-ttu-id="20179-115">Hantering av förmåner öppna registreringsåtkomst utanför period</span><span class="sxs-lookup"><span data-stu-id="20179-115">Benefits management open enrollment access outside of period</span></span>

<span data-ttu-id="20179-116">Genom den här utgåvan åtgärdas ett fel där medarbetarna kan få åtkomst till förmåner vid en öppen registrering utanför anmälningsperioden eller utan livshändelser.</span><span class="sxs-lookup"><span data-stu-id="20179-116">This release fixes a bug where employees could access benefits open enrollment outside of the enrollment period or without a life event.</span></span> <span data-ttu-id="20179-117">Om du behöver demo öppna en registrering i självbetjäning för medarbetare måste du justera de öppna anmälningsdatumen till idag (eller tidigare) för att göra det tillgängligt.</span><span class="sxs-lookup"><span data-stu-id="20179-117">As a result, if you need to demo open enrollment in Employee self service, you must adjust the open enrollment dates to today (or earlier) to make it accessible.</span></span> <span data-ttu-id="20179-118">Du kan ändra den här inställningen under **förmånshantering > regler och alternativperioder**.</span><span class="sxs-lookup"><span data-stu-id="20179-118">You can change this setting under **Benefits management > Rules and options periods**.</span></span>

## <a name="email-employee-enrollment-confirmation"></a><span data-ttu-id="20179-119">Bekräftelse på e-postanmälan om medarbetare</span><span class="sxs-lookup"><span data-stu-id="20179-119">Email employee enrollment confirmation</span></span>

<span data-ttu-id="20179-120">Du kan nu skicka e-postmeddelanden till medarbetare efter att de slutfört urvalet av förmåner.</span><span class="sxs-lookup"><span data-stu-id="20179-120">You can now send emails to employees after they complete their benefits selection.</span></span> <span data-ttu-id="20179-121">Du kan antingen skicka ett standardmeddelande eller använda en organisations e-postmall.</span><span class="sxs-lookup"><span data-stu-id="20179-121">You can either send a default message or use an organization email template.</span></span> <span data-ttu-id="20179-122">Dessa inställningar finns under **Personalparametrar > Hantering av förmåner**.</span><span class="sxs-lookup"><span data-stu-id="20179-122">These settings are under **Human resource parameters > Benefits management**.</span></span>

## <a name="canceled-leave-still-appears-in-upcoming-time-off-on-people-workspace-441358"></a><span data-ttu-id="20179-123">Annullerad ledighet visas fortfarande i kommande ledighet på arbetsytan personer (441358)</span><span class="sxs-lookup"><span data-stu-id="20179-123">Canceled leave still appears in upcoming time off on People workspace (441358)</span></span>

<span data-ttu-id="20179-124">Annullerad låt visas inte längre som kommande ledighet på tjänstledighetskortet på arbetsytan **personer**.</span><span class="sxs-lookup"><span data-stu-id="20179-124">Canceled leave no longer displays as upcoming time off on the leave cards in the **People** workspace.</span></span>

## <a name="unable-to-use-the-department-entity-property-in-the-positionv2-entity-456486"></a><span data-ttu-id="20179-125">Det går inte att använda egenskapen avdelningsenhet i PositionV2-entiteten (456486)</span><span class="sxs-lookup"><span data-stu-id="20179-125">Unable to use the department entity property in the PositionV2 entity (456486)</span></span>

<span data-ttu-id="20179-126">Nu kan du lägga till en avdelning utan att skapa en duplicerad relation.</span><span class="sxs-lookup"><span data-stu-id="20179-126">You can now add a department without creating a duplicate relation.</span></span>

## <a name="payrollworkerenrolledbenefitdetailentity-should-only-use-calculated-field-for-retirement-plans-459779"></a><span data-ttu-id="20179-127">PayrollWorkerEnrolledBenefitDetailEntity bör endast använda beräknade fält för pensionsplaner (459779)</span><span class="sxs-lookup"><span data-stu-id="20179-127">PayrollWorkerEnrolledBenefitDetailEntity should only use calculated field for retirement plans (459779)</span></span>

<span data-ttu-id="20179-128">När du exporterar **PayrollWorkerEnrolledBenefitDetailEntity**-entiteten avgör exporten om det ska använda ett beräknat fält baserat på en kostnadstabell eller använda fältet **ContributionAmountCur** i säkerhetstabellen.</span><span class="sxs-lookup"><span data-stu-id="20179-128">When exporting the **PayrollWorkerEnrolledBenefitDetailEntity** entity, the export determines whether it should use a calculated field based on a rate table or use the **ContributionAmountCur** field on the backing table.</span></span> <span data-ttu-id="20179-129">Logiken som används av dataenheten använder kostnadstabellen i situationer där programmet normalt inte är det.</span><span class="sxs-lookup"><span data-stu-id="20179-129">The logic used by the data entity uses the rate table in situations where the application normally doesn't.</span></span> <span data-ttu-id="20179-130">Den här logiken gör att enhetens export returnerar ett nollvärde för den här kolumnen eftersom ingen beräkningsavgiftstabell och produkten inte tillåter kunden att ange en sådan.</span><span class="sxs-lookup"><span data-stu-id="20179-130">This logic causes the entity exports to return a zero value for this column, because there's no calculation rate table and the product doesn't allow the customer to specify one.</span></span>
 
## <a name="confusing-translations-in-czech-language-in-personnel-management-and-employee-self-service-400276"></a><span data-ttu-id="20179-131">Förvirrande översättningar på tjeckiska språk i personalhantering och Självbetjäning för medarbetare (400276)</span><span class="sxs-lookup"><span data-stu-id="20179-131">Confusing translations in Czech language in Personnel management and Employee self service (400276)</span></span>

<span data-ttu-id="20179-132">Den här versionen korrigerar översättningarna för **Företagskatalogen**, **Nästa registrerade kurs**, **Jobb** och **Befattning**.</span><span class="sxs-lookup"><span data-stu-id="20179-132">This release corrects the translations for **Company directory**, **Next registered course**, **Job**, and **Position**.</span></span>
 
## <a name="the-workcalendaremployment-table-doesnt-have-the-created-and-modified-system-fields-enabled-460171"></a><span data-ttu-id="20179-133">De skapade och ändrade systemfälten är inte aktiverade i WorkCalendarEmployment-registret (460171)</span><span class="sxs-lookup"><span data-stu-id="20179-133">The WorkCalendarEmployment table doesn't have the created and modified system fields enabled (460171)</span></span>

<span data-ttu-id="20179-134">Skapade och ändrade systemfält har nu aktiverats i registret **WorkCalendarEmployment** i personal.</span><span class="sxs-lookup"><span data-stu-id="20179-134">Created and modified system fields are now enabled on the **WorkCalendarEmployment** table in Human Resources.</span></span>
 
## <a name="null-reference-exception-for-hire-and-add-details-for-future-employee-455475"></a><span data-ttu-id="20179-135">Null-referens undantag för anställning och lägg till detaljer för framtida medarbetare (455475)</span><span class="sxs-lookup"><span data-stu-id="20179-135">Null reference exception for Hire and add details for future employee (455475)</span></span>

<span data-ttu-id="20179-136">Den här versionen korrigerar ett fel (null-referens) i strömlinjeformad medarbetartransaktion när du anställer en medarbetare med alternativet att **anställa och lägga till detaljer**.</span><span class="sxs-lookup"><span data-stu-id="20179-136">This release corrects an error (null reference) in streamlined employee entry when you hire an employee using the option to **Hire and add details**.</span></span>

## <a name="changes-made-in-the-common-data-service-worker-entity-dont-reflect-in-human-resources-455652"></a><span data-ttu-id="20179-137">Ändringar gjorda i Common Data Service arbetsenheten visas inte i personal (455652)</span><span class="sxs-lookup"><span data-stu-id="20179-137">Changes made in the Common Data Service Worker entity don't reflect in Human Resources (455652)</span></span>

<span data-ttu-id="20179-138">Ändringar som görs i följande fält i entiteten **Arbetare** i Common Data Service kommer nu att visas i personal:</span><span class="sxs-lookup"><span data-stu-id="20179-138">Changes made to the following fields in the **Worker** entity in Common Data Service will now show up in Human Resources:</span></span>

- <span data-ttu-id="20179-139">**Arbetar hemifrån**</span><span class="sxs-lookup"><span data-stu-id="20179-139">**Works from home**</span></span>
- <span data-ttu-id="20179-140">**Datum för tjänsteålder**</span><span class="sxs-lookup"><span data-stu-id="20179-140">**Seniority date**</span></span>
- <span data-ttu-id="20179-141">**Jubileumsdatum**</span><span class="sxs-lookup"><span data-stu-id="20179-141">**Anniversary date**</span></span>
- <span data-ttu-id="20179-142">**Ursprungligt anställningsdatum**</span><span class="sxs-lookup"><span data-stu-id="20179-142">**Original hire date**</span></span>

## <a name="correct-compensation-level-doesnt-default-based-on-the-job-assigned-to-the-position-394136"></a><span data-ttu-id="20179-143">Korrekt kompensationsnivå är inte standard baserad på jobbet som tilldelats befattningen (394136)</span><span class="sxs-lookup"><span data-stu-id="20179-143">Correct compensation level doesn't default based on the job assigned to the position (394136)</span></span>

<span data-ttu-id="20179-144">Med denna ändring är den korrekta kompensationsnivån standard baserad på poster för **giltighetsdatum** för **befattningsdetaljer** och **Startdatum** för **Tilldelning av kompensationsplan**.</span><span class="sxs-lookup"><span data-stu-id="20179-144">With this change, the correct compensation level defaults based on the **Date effective** records for the **Position details** and the **Start date** of the **Compensation plan assignment**.</span></span>

## <a name="in-preview"></a><span data-ttu-id="20179-145">I förhandsgranskning</span><span class="sxs-lookup"><span data-stu-id="20179-145">In preview</span></span>

## <a name="mandatory-fields"></a><span data-ttu-id="20179-146">Obligatoriska fält</span><span class="sxs-lookup"><span data-stu-id="20179-146">Mandatory fields</span></span> 

<span data-ttu-id="20179-147">Du kan nu göra fält obligatoriska genom att använda anpassningsfunktioner för personal.</span><span class="sxs-lookup"><span data-stu-id="20179-147">You can now make fields mandatory by using Human Resources personalization capabilities.</span></span> <span data-ttu-id="20179-148">Den här funktionen kräver **sparade vyer**.</span><span class="sxs-lookup"><span data-stu-id="20179-148">This feature requires **Saved views**.</span></span>

## <a name="human-resources-application-in-teams"></a><span data-ttu-id="20179-149">Personalapp i Teams</span><span class="sxs-lookup"><span data-stu-id="20179-149">Human Resources application in Teams</span></span>

<span data-ttu-id="20179-150">Medarbetare kan visa och begära ledighet från arbetet inom Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="20179-150">Employees can view and request time away from work within Microsoft Teams.</span></span> <span data-ttu-id="20179-151">De kan samverka med en bot för att skapa tjänstledighetsansökan.</span><span class="sxs-lookup"><span data-stu-id="20179-151">They can interact with a bot to create leave requests.</span></span> <span data-ttu-id="20179-152">Mer information finns [i personalapp i Teams](https://go.microsoft.com/fwlink/?linkid=2127841).</span><span class="sxs-lookup"><span data-stu-id="20179-152">For more information, see [Human Resources app in Teams](https://go.microsoft.com/fwlink/?linkid=2127841).</span></span> 

## <a name="data-management-framework-dmf-entities-for-benefits-management"></a><span data-ttu-id="20179-153">DMF-enheter (Data Management Framework) för förmånshantering</span><span class="sxs-lookup"><span data-stu-id="20179-153">Data management framework (DMF) entities for Benefits management</span></span>
 
<span data-ttu-id="20179-154">Entiteter för hantering av förmåner släpps.</span><span class="sxs-lookup"><span data-stu-id="20179-154">Benefits management entities are releasing.</span></span> <span data-ttu-id="20179-155">DMF-enheter gör det möjligt att importera och exportera data för att enkelt konfigurera hantering av förmåner.</span><span class="sxs-lookup"><span data-stu-id="20179-155">DMF entities allow you to import and export data to easily configure benefits management.</span></span> <span data-ttu-id="20179-156">En mall för hantering av förmåner kan användas för att flytta data.</span><span class="sxs-lookup"><span data-stu-id="20179-156">A Benefits management template will be available to move data.</span></span> <span data-ttu-id="20179-157">Mallen exporterar och importerar data sekventiellt för att respektera databeroenden.</span><span class="sxs-lookup"><span data-stu-id="20179-157">The template exports and imports the data sequentially to respect data dependencies.</span></span>

## <a name="buy-and-sell-leave"></a><span data-ttu-id="20179-158">Köpa och sälja tjänstledighet</span><span class="sxs-lookup"><span data-stu-id="20179-158">Buy and sell leave</span></span> 

<span data-ttu-id="20179-159">Vissa organisationer ger en förmån som gör det möjligt för medarbetare att köpa eller sälja sin tjänstledighet.</span><span class="sxs-lookup"><span data-stu-id="20179-159">Some organizations provide a benefit that allows employees to buy or sell their leave.</span></span> <span data-ttu-id="20179-160">Den här processen hanteras ofta manuellt.</span><span class="sxs-lookup"><span data-stu-id="20179-160">This process is often managed manually.</span></span> <span data-ttu-id="20179-161">Med den här funktionen automatiseras hanteringen av principer och begäranden för personalavdelningen.</span><span class="sxs-lookup"><span data-stu-id="20179-161">This feature automates managing policies and requests for the HR department.</span></span> <span data-ttu-id="20179-162">Det effektiviserar hanteringsprocessen och hjälper till att eliminera misstag.</span><span class="sxs-lookup"><span data-stu-id="20179-162">It streamlines the leave management process and helps eliminate mistakes.</span></span> <span data-ttu-id="20179-163">Mer information finns i:</span><span class="sxs-lookup"><span data-stu-id="20179-163">For more information, see:</span></span>

- [<span data-ttu-id="20179-164">Hantera principer för köpa och sälja tjänstledighet</span><span class="sxs-lookup"><span data-stu-id="20179-164">Manage buy and sell leave policies</span></span>](hr-leave-and-absence-manage-buy-and-sell-leave-policies.md)
- [<span data-ttu-id="20179-165">Köpa och sälja tjänstledighet</span><span class="sxs-lookup"><span data-stu-id="20179-165">Buy and sell leave</span></span>](hr-employee-self-service-buy-sell-leave.md)

## <a name="leave-accrual-for-a-single-company-or-single-plan"></a><span data-ttu-id="20179-166">Lämna periodisering för ett enskilt företag eller en plan</span><span class="sxs-lookup"><span data-stu-id="20179-166">Leave accrual for a single company or single plan</span></span>

<span data-ttu-id="20179-167">Kunder kan bearbeta periodiseringar för ett enskilt företag eller en enskild plan för tjänstledighet och frånvaro.</span><span class="sxs-lookup"><span data-stu-id="20179-167">Customers can process accruals for a single company or a single leave and absence plan.</span></span> <span data-ttu-id="20179-168">Denna möjlighet ger klarhet i den periodiserade processen för kunder med olika tjänstledighetsår eller principer för periodisering av tjänstledighet.</span><span class="sxs-lookup"><span data-stu-id="20179-168">This ability provides clarity for the accrual process for customers with different leave years or leave accrual policies.</span></span> <span data-ttu-id="20179-169">Mer information finns i [tjänstledighet per företag eller per tjänstledighetsplan](hr-leave-and-absence-accrue.md).</span><span class="sxs-lookup"><span data-stu-id="20179-169">For more information, see [Accrue leave per company or per leave plan](hr-leave-and-absence-accrue.md).</span></span>

## <a name="add-attachments-to-time-off-requests"></a><span data-ttu-id="20179-170">Lägg till bifogade filer i ledighetsansökningar</span><span class="sxs-lookup"><span data-stu-id="20179-170">Add attachments to time-off requests</span></span>

<span data-ttu-id="20179-171">Möjligheten att lägga till bilagor till godkända ansökan om tjänstledighet är viktigt i den aktuella COVID-19 miljön.</span><span class="sxs-lookup"><span data-stu-id="20179-171">The ability to add attachments to approved leave requests is critical in the current COVID-19 environment.</span></span> <span data-ttu-id="20179-172">Medarbetarna kan nu lägga till dessa bilagor.</span><span class="sxs-lookup"><span data-stu-id="20179-172">Employees can now add these attachments.</span></span> <span data-ttu-id="20179-173">De har också mer inblick i hur uppdateringar görs för att lämna förfrågningar.</span><span class="sxs-lookup"><span data-stu-id="20179-173">They also have more insight into how updates are made to leave requests.</span></span> <span data-ttu-id="20179-174">Mer information finns i [lägga till en bilaga till en befintlig begäran](hr-employee-self-service-request-time-off.md#add-an-attachment-to-an-existing-request).</span><span class="sxs-lookup"><span data-stu-id="20179-174">For more information, see [Add an attachment to an existing request](hr-employee-self-service-request-time-off.md#add-an-attachment-to-an-existing-request).</span></span>

## <a name="add-reason-code-to-accrual-suspensions"></a><span data-ttu-id="20179-175">Lägg till orsakskod för periodiserade avstängningar</span><span class="sxs-lookup"><span data-stu-id="20179-175">Add reason code to accrual suspensions</span></span> 

<span data-ttu-id="20179-176">Orsakskoder har lagts till den periodiserade avstängningen.</span><span class="sxs-lookup"><span data-stu-id="20179-176">Reason codes have been added to the accrual suspension.</span></span>

## <a name="carry-forward-rules"></a><span data-ttu-id="20179-177">Överför regler</span><span class="sxs-lookup"><span data-stu-id="20179-177">Carry forward rules</span></span> 

<span data-ttu-id="20179-178">Du kan ange en överför tjänstledighetstyp för överföringsaldon där överför justeringar överförs.</span><span class="sxs-lookup"><span data-stu-id="20179-178">You can specify a carry forward leave type for carry forward balances where carry forward adjustments are transferred.</span></span> <span data-ttu-id="20179-179">Om en medarbetare till exempel överförs 10 dagar kan du välja en annan tjänstledighetstyp för de 10 dagarna.</span><span class="sxs-lookup"><span data-stu-id="20179-179">For example, if an employee carries forward 10 days, you can pick a different leave type for those 10 days.</span></span> <span data-ttu-id="20179-180">Mer information finns i [konfigurera tjänstledighet och frånvarotyper](hr-leave-and-absence-types.md).</span><span class="sxs-lookup"><span data-stu-id="20179-180">For more information, see [Configure leave and absence types](hr-leave-and-absence-types.md).</span></span>

## <a name="suspend-leave-accrual-for-specified-leave-types"></a><span data-ttu-id="20179-181">Pausa tjänstledighetsperiodisering för angivna tjänstledighetstyper</span><span class="sxs-lookup"><span data-stu-id="20179-181">Suspend leave accrual for specified leave types</span></span>

<span data-ttu-id="20179-182">Du kan skapa en regel för att pausa tjänstledighetsperiodiseringar för medarbetare som har lämnat förfrågningar om obetald tjänstledighet.</span><span class="sxs-lookup"><span data-stu-id="20179-182">You can create a rule to suspend leave accruals for employees with leave requests entered for unpaid leave.</span></span> <span data-ttu-id="20179-183">Obetald tjänstledighet kan vara en typ, men behöver inte vara det.</span><span class="sxs-lookup"><span data-stu-id="20179-183">Unpaid leave can be a type, but doesn't have to be.</span></span> <span data-ttu-id="20179-184">Du kan pausa eventuell tjänstledighet baserat på annan tjänstledighetstyp.</span><span class="sxs-lookup"><span data-stu-id="20179-184">You can suspend any leave based on another leave type.</span></span>

## <a name="dmf-entity-available-for-accrual-suspensions"></a><span data-ttu-id="20179-185">DMF-enhet tillgänglig för periodiserade avstängningar</span><span class="sxs-lookup"><span data-stu-id="20179-185">DMF entity available for accrual suspensions</span></span> 

<span data-ttu-id="20179-186">Nu är en DMF-enhet tillgänglig för periodiserade avstängningar.</span><span class="sxs-lookup"><span data-stu-id="20179-186">A DMF entity is now available for accrual suspensions.</span></span>

## <a name="coming-soon"></a><span data-ttu-id="20179-187">Kommer snart</span><span class="sxs-lookup"><span data-stu-id="20179-187">Coming soon</span></span>

## <a name="checklist-entities-included-in-common-data-service"></a><span data-ttu-id="20179-188">Entiteter för checklista inkluderade i Common Data Service</span><span class="sxs-lookup"><span data-stu-id="20179-188">Checklist entities included in Common Data Service</span></span>

<span data-ttu-id="20179-189">Entiteter för checklista för registrering, offboard, överföringar och affärsprocesser kommer snart att vara tillgängliga i Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="20179-189">Checklist entities for Onboarding, Offboarding, Transfers, and Business processes will be available soon in Common Data Service.</span></span>

## <a name="see-also"></a><span data-ttu-id="20179-190">Se även</span><span class="sxs-lookup"><span data-stu-id="20179-190">See also</span></span>

[<span data-ttu-id="20179-191">Nyheter och ändringar i Human Resources</span><span class="sxs-lookup"><span data-stu-id="20179-191">What's new or changed in Human Resources</span></span>](hr-admin-whats-new.md)</br>
[<span data-ttu-id="20179-192">Översikt över Dynamics 365 Human Resources 2019 utgivningsvåg 2</span><span class="sxs-lookup"><span data-stu-id="20179-192">Overview of Dynamics 365 Human Resources 2019 release wave 2</span></span>](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[<span data-ttu-id="20179-193">Uppdatera process</span><span class="sxs-lookup"><span data-stu-id="20179-193">Update process</span></span>](hr-admin-setup-update-process.md)</br>
[<span data-ttu-id="20179-194">Hantera funktioner</span><span class="sxs-lookup"><span data-stu-id="20179-194">Manage features</span></span>](hr-admin-manage-features.md)
