---
title: Felsöka huvudplanering
description: I det här avsnittet beskrivs hur du åtgärdar problem som kan uppstå när du arbetar med huvudplanering.
author: SmithaNataraj
manager: tfehr
ms.date: 11/04/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: smnatara
ms.search.validFrom: 2020-11-04
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: db336946873fa1b5cc3f669823541af8cab4115b
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5216115"
---
# <a name="troubleshoot-master-planning"></a><span data-ttu-id="0a2ca-103">Felsöka huvudplanering</span><span class="sxs-lookup"><span data-stu-id="0a2ca-103">Troubleshoot master planning</span></span>

<span data-ttu-id="0a2ca-104">I det här avsnittet beskrivs hur du åtgärdar problem som kan uppstå när du arbetar med huvudplanering.</span><span class="sxs-lookup"><span data-stu-id="0a2ca-104">This topic describes how to fix issues that you might encounter while you work with master planning.</span></span>

## <a name="bill-of-materials-explosion-behaves-differently-for-firmed-production-orders-and-for-estimated-production-orders-for-manually-created-work"></a><span data-ttu-id="0a2ca-105">Nedbrytning av strukturlistor fungerar annorlunda för fasta produktionsorder och för uppskattade tillverkningsorder för manuellt skapat arbete.</span><span class="sxs-lookup"><span data-stu-id="0a2ca-105">Bill of materials explosion behaves differently for firmed production orders and for estimated production orders for manually created work.</span></span>

### <a name="issue-description"></a><span data-ttu-id="0a2ca-106">Problembeskrivning</span><span class="sxs-lookup"><span data-stu-id="0a2ca-106">Issue description</span></span>

<span data-ttu-id="0a2ca-107">När en tillverkningsorder bekräftas bryts artiklarna inte ned när du bryter ned strukturlistan.</span><span class="sxs-lookup"><span data-stu-id="0a2ca-107">When a production order is firmed, the items aren't exploded when you explode the bill of materials (BOM).</span></span> <span data-ttu-id="0a2ca-108">Men när du skapar en arbetsorder manuellt och sedan uppskattar tillverkningsordern, bryts artiklarna ned.</span><span class="sxs-lookup"><span data-stu-id="0a2ca-108">However, when you manually create a work order and then estimate the production order, the items are exploded.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="0a2ca-109">Problemlösning</span><span class="sxs-lookup"><span data-stu-id="0a2ca-109">Issue resolution</span></span>

<span data-ttu-id="0a2ca-110">Systemet fungerar som förväntat.</span><span class="sxs-lookup"><span data-stu-id="0a2ca-110">The system is working as expected.</span></span> <span data-ttu-id="0a2ca-111">Nedbrytningen som inträffar när tillverkningsordern bekräftas pekar på den planerade ordern, men den visas inte om den planerade ordern för närvarande är bekräftad i detta fall.</span><span class="sxs-lookup"><span data-stu-id="0a2ca-111">The explosion that occurs when the production order is firmed will point to the planned order, but it doesn't appear that the planned order is currently firmed in this case.</span></span> <span data-ttu-id="0a2ca-112">Om tillverkningsordern har uppskattats utlöses nedbrytningen från den släppta produktionsordern där det inte finns någon planerad order.</span><span class="sxs-lookup"><span data-stu-id="0a2ca-112">However, if the production order has been estimated, the explosion is triggered from the released production order where no planned order exists.</span></span>

## <a name="the-delay-value-isnt-updated-when-i-reschedule-a-planned-order"></a><span data-ttu-id="0a2ca-113">Värdet för fördröjningen uppdateras inte när jag planerar om en planerad order.</span><span class="sxs-lookup"><span data-stu-id="0a2ca-113">The Delay value isn't updated when I reschedule a planned order.</span></span>

<span data-ttu-id="0a2ca-114">Om du vill uppdatera fördröjningen för planerade order öppnar du dialogrutan **Omplanering** för den planerade ordern.</span><span class="sxs-lookup"><span data-stu-id="0a2ca-114">To update the delay for planned orders, open the **Rescheduling** dialog box for the planned order.</span></span> <span data-ttu-id="0a2ca-115">På snabbfliken **Nedbrytning** ser du till att alternativet **Utför explosion efter omplanering** anges till *Ja*.</span><span class="sxs-lookup"><span data-stu-id="0a2ca-115">On the **Explosion** FastTab, make sure that the **Perform explosion after rescheduling** option is set to *Yes*.</span></span>

## <a name="production-scheduling-doesnt-consider-the-safety-margins-that-are-set-on-the-item-coverage-for-pegged-supply"></a><span data-ttu-id="0a2ca-116">Vid produktionsplaneringen beaktas inte de säkerhetsmarginaler som ställs in för artikeldisponering för peggad leverans.</span><span class="sxs-lookup"><span data-stu-id="0a2ca-116">Production scheduling doesn't consider the safety margins that are set on the item coverage for pegged supply.</span></span>

### <a name="issue-description"></a><span data-ttu-id="0a2ca-117">Problembeskrivning</span><span class="sxs-lookup"><span data-stu-id="0a2ca-117">Issue description</span></span>

<span data-ttu-id="0a2ca-118">Huvudplaneringen tar hänsyn till säkerhetsmarginalerna.</span><span class="sxs-lookup"><span data-stu-id="0a2ca-118">Master planning considers the safety margins.</span></span> <span data-ttu-id="0a2ca-119">Säkerhetsmarginalerna ignoreras dock när planerade tillverkningsorder planeras.</span><span class="sxs-lookup"><span data-stu-id="0a2ca-119">However, the safety margins are ignored when planned production orders are scheduled.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="0a2ca-120">Problemlösning</span><span class="sxs-lookup"><span data-stu-id="0a2ca-120">Issue resolution</span></span>

<span data-ttu-id="0a2ca-121">Marginaler beaktas endast vid huvudplanering, inte vid manuell tidsplanering.</span><span class="sxs-lookup"><span data-stu-id="0a2ca-121">Margins are considered only during master planning, not during manual scheduling.</span></span> <span data-ttu-id="0a2ca-122">Marginaler är utformade för att fungera som buffert under planeringsfasen, vilket ger en del "marginal" för den faktiska processen.</span><span class="sxs-lookup"><span data-stu-id="0a2ca-122">Margins are designed to act as a buffer during the planning phase, to give some "margin" for the actual process.</span></span>

<span data-ttu-id="0a2ca-123">Du kan få önskat resultat genom att ta bort marginalen.</span><span class="sxs-lookup"><span data-stu-id="0a2ca-123">To get the desired result, you can remove the margin.</span></span> <span data-ttu-id="0a2ca-124">Flödet måste sedan uppdateras så att det innehåller önskad tid (t.ex. kötid).</span><span class="sxs-lookup"><span data-stu-id="0a2ca-124">The route must then be updated so that it includes the desired time (for example, as queue time).</span></span> <span data-ttu-id="0a2ca-125">Samma resultat skapas då i både huvudplanering och manuell planering.</span><span class="sxs-lookup"><span data-stu-id="0a2ca-125">Both master planning and manual scheduling should then produce the same result.</span></span>

## <a name="planned-orders-are-generated-even-though-we-have-items-in-stock-and-production-orders-already-exist-for-them"></a><span data-ttu-id="0a2ca-126">Planerade order skapas trots att det redan finns artiklar i lager- och tillverkningsorder för dem.</span><span class="sxs-lookup"><span data-stu-id="0a2ca-126">Planned orders are generated even though we have items in stock and production orders already exist for them.</span></span>

<span data-ttu-id="0a2ca-127">Du kanske kan åtgärda det här problemet genom att öka värdet för **Positiva dagar** för relevanta grupper på sidan **Disponeringsgrupp**.</span><span class="sxs-lookup"><span data-stu-id="0a2ca-127">You might be able to fix this issue by increasing the **Positive days** value for the relevant groups on the **Coverage group** page.</span></span> <span data-ttu-id="0a2ca-128">Den här ändringen gör att systemet avgör om lagerbehållning kan användas för efterfrågan.</span><span class="sxs-lookup"><span data-stu-id="0a2ca-128">This change will cause the system to determine whether on-hand inventory can be used for the demand.</span></span> <span data-ttu-id="0a2ca-129">Sedan genereras en ny planerad order för de artiklar som finns i lager.</span><span class="sxs-lookup"><span data-stu-id="0a2ca-129">Then a new planned order won't be generated for the items that are in stock.</span></span>

## <a name="master-planning-doesnt-seem-to-respect-capacity-limitations-and-is-scheduling-more-than-the-available-capacity"></a><span data-ttu-id="0a2ca-130">Huvudplaneringen verkar inte respektera kapacitetsbegränsningarna och tidsplaneringen överstiger den tillgängliga kapaciteten.</span><span class="sxs-lookup"><span data-stu-id="0a2ca-130">Master planning doesn't seem to respect capacity limitations and is scheduling more than the available capacity.</span></span>

### <a name="issue-description"></a><span data-ttu-id="0a2ca-131">Problembeskrivning</span><span class="sxs-lookup"><span data-stu-id="0a2ca-131">Issue description</span></span>

<span data-ttu-id="0a2ca-132">När du använder operationsplanering där det finns ändlig kapacitet och där flödet anger en blandning av behov för både en resursgrupp och enskilda resurser, finns det en liten chans att göra en del av med överordningen på grund av det sätt på vilket algoritmen validerar kapacitetskonflikter.</span><span class="sxs-lookup"><span data-stu-id="0a2ca-132">When you use operation scheduling where there is finite capacity, and where the route specifies a mix of requirements for both a resource group and individual resources, there is a small chance of overbooking because of the way that the algorithm validates for capacity conflicts.</span></span> <span data-ttu-id="0a2ca-133">Denna bokning kan ske om du använder hjälpprogram för att köra huvudplanering.</span><span class="sxs-lookup"><span data-stu-id="0a2ca-133">This overbooking can occur when you use helpers to run master planning.</span></span> <span data-ttu-id="0a2ca-134">Det är mest sannolikt att det uppstår om det finns många jobb med en relativt kortkörning.</span><span class="sxs-lookup"><span data-stu-id="0a2ca-134">It's most likely to occur if there are many jobs that have a relatively short runtime.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="0a2ca-135">Problemlösning</span><span class="sxs-lookup"><span data-stu-id="0a2ca-135">Issue resolution</span></span>

<span data-ttu-id="0a2ca-136">Om det är viktigt att ingen överbokning inträffar för grovplanering kan du göra schemaläggningen till en del av huvudplaneringen genom att aktivera alternativet **Rätt begränsad kapacitet för grovplanering** på sidan **Huvudplaneringsparametrar**.</span><span class="sxs-lookup"><span data-stu-id="0a2ca-136">If it's essential that no overbooking occur for operation scheduling, you can make the scheduling part of master planning single-threaded by turning on the **Accurate finite capacity for Operation Scheduling** option on the **Master planning parameters** page.</span></span> <span data-ttu-id="0a2ca-137">Det här alternativet är inte tillgängligt som standard.</span><span class="sxs-lookup"><span data-stu-id="0a2ca-137">This option isn't available by default.</span></span> <span data-ttu-id="0a2ca-138">Du måste lägga till den manuellt på sidan genom att använda anpassningsfunktioner.</span><span class="sxs-lookup"><span data-stu-id="0a2ca-138">You must manually add it to the page by using personalization features.</span></span> <span data-ttu-id="0a2ca-139">När du använder det här alternativet körs tidsplanering långsammare på grund av brist på parallell bearbetning.</span><span class="sxs-lookup"><span data-stu-id="0a2ca-139">When you use this option, scheduling will run more slowly because of the lack of parallel processing.</span></span>

## <a name="planned-orders-take-a-long-time-to-update"></a><span data-ttu-id="0a2ca-140">Planerade order tar lång tid att uppdatera.</span><span class="sxs-lookup"><span data-stu-id="0a2ca-140">Planned orders take a long time to update.</span></span>

### <a name="issue-description"></a><span data-ttu-id="0a2ca-141">Problembeskrivning</span><span class="sxs-lookup"><span data-stu-id="0a2ca-141">Issue description</span></span>

<span data-ttu-id="0a2ca-142">Vid uppdatering av kravkvantitet och/eller leveransdatum på en planerad order tar det vanligtvis minst 30 sekunder per order för att spara uppdateringen.</span><span class="sxs-lookup"><span data-stu-id="0a2ca-142">When updating the requirement quantity and/or delivery date on a planned order, it typically takes at least 30 seconds per order to save the update.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="0a2ca-143">Problemlösning</span><span class="sxs-lookup"><span data-stu-id="0a2ca-143">Issue resolution</span></span>

<span data-ttu-id="0a2ca-144">Detta är ett känt problem med den inbyggda huvudplaneringsmotorn.</span><span class="sxs-lookup"><span data-stu-id="0a2ca-144">This is a known issue with the built-in master planning engine.</span></span> <span data-ttu-id="0a2ca-145">Det beror på den underliggande automatiska nedbrytningen genom strukturlistan under redigeringar.</span><span class="sxs-lookup"><span data-stu-id="0a2ca-145">It is caused by the underlying auto explosion through the BOM structure during edits.</span></span> <span data-ttu-id="0a2ca-146">Det här problemet åtgärdas i planeringsoptimering, där en planering kan uppdatera och godkänna relevanta order och, när så önskas, utlösa en planeringskörning för att uppdatera planerade order för den underliggande strukturlistan.</span><span class="sxs-lookup"><span data-stu-id="0a2ca-146">This issue is addressed in Planning Optimization, where a planner can update and approve the relevant orders and, when desired, trigger a planning run to update planned orders for the underlying BOM structure.</span></span>

<span data-ttu-id="0a2ca-147">Ett sätt att förbättra prestanda med den inbyggda huvudplaneringsmotorn är att göra följande:</span><span class="sxs-lookup"><span data-stu-id="0a2ca-147">One way to improve performance with the built-in master planning engine is to do the following:</span></span>

1. <span data-ttu-id="0a2ca-148">Gå till **Huvudplanering \> Inställningar \> Planer \> Huvudplaner**.</span><span class="sxs-lookup"><span data-stu-id="0a2ca-148">Go to **Master planning \> Setup \> Plans \> Master plans**.</span></span>
1. <span data-ttu-id="0a2ca-149">Välj en plan.</span><span class="sxs-lookup"><span data-stu-id="0a2ca-149">Select a plan.</span></span>
1. <span data-ttu-id="0a2ca-150">Expandera snabbfliken **Tidsgräns i dagar**.</span><span class="sxs-lookup"><span data-stu-id="0a2ca-150">Expand the **Time fence in days** FastTab.</span></span>
1. <span data-ttu-id="0a2ca-151">Ställ in **Nedbrytning** till *Ja* och ange fältet under den här inställningen till 0 (noll).</span><span class="sxs-lookup"><span data-stu-id="0a2ca-151">Set **Explosion** to *Yes*, and set the field below this setting to 0 (zero).</span></span>

> [!NOTE]
> <span data-ttu-id="0a2ca-152">Detta begränsar tidsperioden för nedbrytningar som utförs för denna huvudplan till en enda dag.</span><span class="sxs-lookup"><span data-stu-id="0a2ca-152">This will limit the period for explosions performed for this master plan to a single day.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]