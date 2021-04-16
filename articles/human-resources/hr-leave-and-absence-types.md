---
title: Konfigurera typer av tjänstledighet och frånvaro
description: Ställ in tjänstledighetstyper som medarbetarna kan göra i Dynamics 365 Human Resources.
author: andreabichsel
ms.date: 06/01/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LeavePlanFormPart, LeaveAbsenceWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: bf868ad44e52b0ed7d0ca6e1f133efa030f3c4a8
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5794575"
---
# <a name="configure-leave-and-absence-types"></a><span data-ttu-id="8c300-103">Konfigurera typer av tjänstledighet och frånvaro</span><span class="sxs-lookup"><span data-stu-id="8c300-103">Configure leave and absence types</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="8c300-104">Tjänstledighetstyper i Dynamics 365 Human Resources definierar olika typer av frånvaro som medarbetare kan rapportera.</span><span class="sxs-lookup"><span data-stu-id="8c300-104">Leave types in Dynamics 365 Human Resources define the types of absences that employees can report.</span></span> <span data-ttu-id="8c300-105">Du kan skräddarsy tjänstledighetstyper enligt organisationens behov.</span><span class="sxs-lookup"><span data-stu-id="8c300-105">You can tailor leave types according to the needs of your organization.</span></span> <span data-ttu-id="8c300-106">Exempel på tjänstledighetstyper:</span><span class="sxs-lookup"><span data-stu-id="8c300-106">Examples of leave types include:</span></span>

- <span data-ttu-id="8c300-107">Betald ledighet (PTO)</span><span class="sxs-lookup"><span data-stu-id="8c300-107">Paid time off (PTO)</span></span>
- <span data-ttu-id="8c300-108">Obetald tjänstledighet</span><span class="sxs-lookup"><span data-stu-id="8c300-108">Unpaid leave</span></span>
- <span data-ttu-id="8c300-109">Betald semester</span><span class="sxs-lookup"><span data-stu-id="8c300-109">Paid vacation</span></span>
- <span data-ttu-id="8c300-110">Sjukfrånvaro</span><span class="sxs-lookup"><span data-stu-id="8c300-110">Sick leave</span></span>
- <span data-ttu-id="8c300-111">Sjukledighet</span><span class="sxs-lookup"><span data-stu-id="8c300-111">Medical leave</span></span>
- <span data-ttu-id="8c300-112">Föräldraledighet</span><span class="sxs-lookup"><span data-stu-id="8c300-112">Family leave</span></span>
- <span data-ttu-id="8c300-113">Kortvarig funktionsnedsättning</span><span class="sxs-lookup"><span data-stu-id="8c300-113">Short-term disability</span></span>
- <span data-ttu-id="8c300-114">Ledighet p.g.a. dödsfall</span><span class="sxs-lookup"><span data-stu-id="8c300-114">Bereavement leave</span></span>

## <a name="add-a-leave-type"></a><span data-ttu-id="8c300-115">Lägg till en tjänstledighetstyp</span><span class="sxs-lookup"><span data-stu-id="8c300-115">Add a leave type</span></span>

1. <span data-ttu-id="8c300-116">På sidan **tjänstledighet och frånvaro** välj fliken **Länkar**.</span><span class="sxs-lookup"><span data-stu-id="8c300-116">On the **Leave and absence** page, select the **Links** tab.</span></span>

2. <span data-ttu-id="8c300-117">Under **Inställningar**, välj **Typer av tjänstledighet och frånvaro**.</span><span class="sxs-lookup"><span data-stu-id="8c300-117">Under **Setup**, select **Leave and absence types**.</span></span>

3. <span data-ttu-id="8c300-118">Välj **Ny**.</span><span class="sxs-lookup"><span data-stu-id="8c300-118">Select **New**.</span></span>

4. <span data-ttu-id="8c300-119">Ange ett namn för tjänstledighetstyp under **Typ**, välj ett arbetsflöde från **arbetsflödes-ID** och ange en beskrivning under **Beskrivning**.</span><span class="sxs-lookup"><span data-stu-id="8c300-119">Enter a name for the leave type under **Type**, select a workflow from **Workflow ID**, and enter a description under **Description**.</span></span>

5. <span data-ttu-id="8c300-120">I **Allmänhet**, välj **Ingen**, **Schemalagd** eller **Ej schemalagd** från listrutan **Kategori**.</span><span class="sxs-lookup"><span data-stu-id="8c300-120">In **General**, select **None**, **Scheduled**, or **Unscheduled** from the **Category** dropdown.</span></span>

6. <span data-ttu-id="8c300-121">Välj en inkomstkod i listrutan **inkomstkod**.</span><span class="sxs-lookup"><span data-stu-id="8c300-121">Select an earning code from the **Earning code** dropdown.</span></span>

7. <span data-ttu-id="8c300-122">Ange **under orsakskod** som krävs om du vill kräva en orsakskod.</span><span class="sxs-lookup"><span data-stu-id="8c300-122">Under **Reason code required**, choose whether you want to require a reason code.</span></span> <span data-ttu-id="8c300-123">Om du vill kräva orsakskoder kan du behöva lägga till dem.</span><span class="sxs-lookup"><span data-stu-id="8c300-123">If you want to require reason codes, you might need to add them.</span></span> <span data-ttu-id="8c300-124">Under **Orsakskoder**, välj **Lägg till**, välj en orsakskod och markera sedan kryssrutan **Aktivera** bredvid den.</span><span class="sxs-lookup"><span data-stu-id="8c300-124">Under **Reason codes**, select **Add**, select a reason code, and then select the **Enabled** checkbox next to it.</span></span>

8. <span data-ttu-id="8c300-125">Under **begränsa åtkomst till valda roller** väljer du om du vill begränsa åtkomsten.</span><span class="sxs-lookup"><span data-stu-id="8c300-125">Under **Restrict access to selected roles**, choose whether you want to restrict access.</span></span> <span data-ttu-id="8c300-126">Välj sedan säkerhetsrollerna under **säkerhetsroller för denna tjänstledighetstyp**.</span><span class="sxs-lookup"><span data-stu-id="8c300-126">Then select the security roles under **Security roles for this leave type**.</span></span> <span data-ttu-id="8c300-127">Säkerhetsrollerna definieras i det arbetsflöde du markerade under **arbetsflödes-ID** tidigare i den här proceduren.</span><span class="sxs-lookup"><span data-stu-id="8c300-127">The security roles are defined in the workflow you selected under **Workflow ID** earlier in this procedure.</span></span>

9. <span data-ttu-id="8c300-128">Under **Kalenderfärg**, välj vilken färg du vill visa på tjänstledighets- och frånvarokalendrar för den här tjänstledighetstypen.</span><span class="sxs-lookup"><span data-stu-id="8c300-128">Under **Calendar color**, choose what color to display on leave and absence calendars for this leave type.</span></span> 

10. <span data-ttu-id="8c300-129">Under **Uppskjutningsrelationer**, välj om du vill att den här tjänstledighetstypen antingen ska skjuta upp en annan tjänstledighetstyp eller skjutas upp av en annan tjänstledighetstyp.</span><span class="sxs-lookup"><span data-stu-id="8c300-129">Under **Suspension relations**, choose if you want to have this leave type either suspend another leave type or be suspended by another leave type.</span></span> <span data-ttu-id="8c300-130">När en ledighetsansökan lämnas in för den uppskjutna tjänstledighetstypen, skapas en uppskjutning av tjänstledighet automatiskt för den uppskjutna tjänstledighetstypen.</span><span class="sxs-lookup"><span data-stu-id="8c300-130">When a leave of absence request is submitted for the suspending leave type, a leave suspension will automatically be created for the suspended leave type.</span></span> 

10. <span data-ttu-id="8c300-131">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="8c300-131">Select **Save**.</span></span>

## <a name="configure-leave-type-rules"></a><span data-ttu-id="8c300-132">Konfigurera regler för tjänstledighetstyp</span><span class="sxs-lookup"><span data-stu-id="8c300-132">Configure leave type rules</span></span>

1. <span data-ttu-id="8c300-133">Ange avrundningsalternativ för tjänstledighetstypen.</span><span class="sxs-lookup"><span data-stu-id="8c300-133">Set rounding options for the leave type.</span></span> <span data-ttu-id="8c300-134">Alternativen inkluderar **Ingen**, **Upp**, **Ned** och **Närmast**.</span><span class="sxs-lookup"><span data-stu-id="8c300-134">Options include **None**, **Up**, **Down**, and **Nearest**.</span></span> <span data-ttu-id="8c300-135">Du kan också ställa in avrundningsprecision för tjänstledighetstypen.</span><span class="sxs-lookup"><span data-stu-id="8c300-135">You can also set rounding precision for the leave type.</span></span>

2. <span data-ttu-id="8c300-136">Ange **helgdagskorrigering** för tjänstledighetstypen.</span><span class="sxs-lookup"><span data-stu-id="8c300-136">Set **Holiday correction** for the leave type.</span></span> <span data-ttu-id="8c300-137">När du väljer det här alternativet använder personal antalet helgdagar som infaller en arbetsdag för att avgöra hur ledighetstypen ska skjutas upp.</span><span class="sxs-lookup"><span data-stu-id="8c300-137">When you select this option, Human Resources uses the number of holidays that fall on a work day to determine how to accrue time off for the leave type.</span></span> <span data-ttu-id="8c300-138">Om t.ex. juldagen infaller på en måndag kommer personalavdelningen att subtrahera en dag från tjänstledighetstypen när periodiseringen bearbetas.</span><span class="sxs-lookup"><span data-stu-id="8c300-138">For example, if Christmas Day falls on a Monday, Human Resources will subtract one day from the leave type when processing accruals.</span></span>

   <span data-ttu-id="8c300-139">Du kan ange helgdagar arbetstidskalender.</span><span class="sxs-lookup"><span data-stu-id="8c300-139">You set holidays in the working time calendar.</span></span> <span data-ttu-id="8c300-140">Mer information finns i [skapa en arbetstidskalender](hr-leave-and-absence-working-time-calendar.md)</span><span class="sxs-lookup"><span data-stu-id="8c300-140">For more information, see [Create a working time calendar](hr-leave-and-absence-working-time-calendar.md)</span></span>
   
 3. <span data-ttu-id="8c300-141">Ange **Överför tjänstledighetstyp** för tjänstledighetstypen.</span><span class="sxs-lookup"><span data-stu-id="8c300-141">Set **Carry-forward leave type** for the leave type.</span></span> <span data-ttu-id="8c300-142">När du väljer det här alternativet överförs alla överförda saldon till den angivna tjänstledighetstypen.</span><span class="sxs-lookup"><span data-stu-id="8c300-142">When you select this option, any carry-forward balances will be transferred to the specified leave type.</span></span> <span data-ttu-id="8c300-143">Tjänstledighetstypen måste också inkluderas i planen för tjänstledighet och frånvaro.</span><span class="sxs-lookup"><span data-stu-id="8c300-143">The carry-forward leave type also needs to be included in the leave and absence plan.</span></span> 
 
 4. <span data-ttu-id="8c300-144">Definiera **utgångsregler** för tjänstledighetstypen.</span><span class="sxs-lookup"><span data-stu-id="8c300-144">Define **Expiration rules** for the leave type.</span></span> <span data-ttu-id="8c300-145">När du konfigurerar det här alternativet kan du välja en enhet med dagar eller månader och ange varaktighet för förfallodatum.</span><span class="sxs-lookup"><span data-stu-id="8c300-145">When you configure this option, you can choose the unit of days or months and set the duration for the expiry.</span></span> <span data-ttu-id="8c300-146">Du kan också ange giltighetsdatum för utgångsregeln.</span><span class="sxs-lookup"><span data-stu-id="8c300-146">You can also set the effective date of the expiration rule.</span></span> <span data-ttu-id="8c300-147">Giltighetsdatumet används för att bestämma när batchjobbet ska köras som bearbetar utgångsdatumet för tjänstledighet eller det datum då regeln börjar gälla.</span><span class="sxs-lookup"><span data-stu-id="8c300-147">The effective date is used to determine when to start running the batch job that processes the leave expiration, or the date when the rule takes effect.</span></span> <span data-ttu-id="8c300-148">Själva utgångsdatumet inträffar alltid på startdatumet för tjänstledighetsplanen när batchjobbet är inställt på att bearbeta.</span><span class="sxs-lookup"><span data-stu-id="8c300-148">The expiration itself will always happen on the leave plan start date once the batch job is set to process.</span></span> <span data-ttu-id="8c300-149">Startdatumet för planen kan till exempel vara den 1 januari 2020, men regeln gäller bara för 2020-06-1.</span><span class="sxs-lookup"><span data-stu-id="8c300-149">For example, the plan start date may be 1/1/2020, but the rule wasn't created until 6/1/2020.</span></span> <span data-ttu-id="8c300-150">Genom att ange giltighetsdatumet till 2020-06-1 bearbetas regeln vid nästa års gräns, så 2021-01-1.</span><span class="sxs-lookup"><span data-stu-id="8c300-150">By setting the effective date to 6/1/2020, the rule will be processed on the next year boundary, so 1/1/2021.</span></span> <span data-ttu-id="8c300-151">Alla tjänstledighetssaldon som finns vid förfallotiden kommer att dras från tjänstledighetstypen och återspeglas i tjänstledighetssaldot.</span><span class="sxs-lookup"><span data-stu-id="8c300-151">Any leave balances that exist at the time of expiry will be subtracted from the leave type and will be reflected in the leave balance.</span></span> 
 
## <a name="see-also"></a><span data-ttu-id="8c300-152">Se även</span><span class="sxs-lookup"><span data-stu-id="8c300-152">See also</span></span>

- [<span data-ttu-id="8c300-153">Översikt över tjänstledighet och frånvaro</span><span class="sxs-lookup"><span data-stu-id="8c300-153">Leave and absence overview</span></span>](hr-leave-and-absence-overview.md)
- [<span data-ttu-id="8c300-154">Skapa en plan för tjänstledighet och frånvaro</span><span class="sxs-lookup"><span data-stu-id="8c300-154">Create a leave and absence plan</span></span>](hr-leave-and-absence-plans.md)
- [<span data-ttu-id="8c300-155">Skapa en arbetstidskalender</span><span class="sxs-lookup"><span data-stu-id="8c300-155">Create a working time calendar</span></span>](hr-leave-and-absence-working-time-calendar.md)
- [<span data-ttu-id="8c300-156">Skjut upp tjänstledighet</span><span class="sxs-lookup"><span data-stu-id="8c300-156">Suspend leave</span></span>](hr-leave-and-absence-suspend-leave.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
