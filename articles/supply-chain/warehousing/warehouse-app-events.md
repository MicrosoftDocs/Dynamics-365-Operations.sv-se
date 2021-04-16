---
title: Lagerställeapphändelser
description: Det här ämnet beskriver den bearbetning av apphändelse i distributionslagret som används för att bearbeta apphändelse meddelanden för lagerstället som en del av ett batchjobb.
author: perlynne
ms.date: 09/02/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSMobileDeviceQueueEvent
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-10-09
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: d63cdea8917bed762bf8d970a408e5931aec48b7
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5837403"
---
# <a name="warehouse-app-event-processing"></a><span data-ttu-id="b520b-103">Händelsebearbetning i distributionslagerappen</span><span class="sxs-lookup"><span data-stu-id="b520b-103">Warehouse app event processing</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b520b-104">Batchjobb som körs i Supply Chain Management kan använda data från en kö för bearbetning av händelser som utfärdats av mobilappen för distributionslagerhantering för att vid behov reagera på signalerade händelser.</span><span class="sxs-lookup"><span data-stu-id="b520b-104">Batch jobs running in Supply Chain Management can use data from a queue for processing events issued by the Warehouse Management mobile app to react as needed to the signaled events.</span></span> <span data-ttu-id="b520b-105">Den här funktionen lägger till relevanta händelser i kön som svar på vissa typer av åtgärder som utförs av medarbetarna som använder appen.</span><span class="sxs-lookup"><span data-stu-id="b520b-105">This feature add relevant events to the queue in response to certain types of actions taken by workers using the app.</span></span> <span data-ttu-id="b520b-106">Ett exempel: när du använder funktionen *Skapa och bearbeta överföringsorder från lagerställeappen* skapas och uppdateras överföringsorderrubriken och -raderna i servern när du kör batchjobbet **Bearbeta händelser för lagerställeapp**.</span><span class="sxs-lookup"><span data-stu-id="b520b-106">An example is when using the *Create and process transfer orders from the warehouse app* feature, the transfer order header and lines get created and updated in the back end when the system is running the **Process warehouse app events** batch job.</span></span>

## <a name="enable-the-process-warehouse-app-events-feature"></a><span data-ttu-id="b520b-107">Aktivera funktionen bearbeta händelser för lagerställeapp</span><span class="sxs-lookup"><span data-stu-id="b520b-107">Enable the Process warehouse app events feature</span></span>

<span data-ttu-id="b520b-108">Innan du kan använda den här funktionen måste du aktivera den i ditt system.</span><span class="sxs-lookup"><span data-stu-id="b520b-108">Before you can use this feature, it must be enabled on your system.</span></span> <span data-ttu-id="b520b-109">Administratörer kan använda sidan [funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) för att kontrollera funktionens status och aktivera den om det behövs.</span><span class="sxs-lookup"><span data-stu-id="b520b-109">Administrators can use the [feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) page to check the feature status and enable it if needed.</span></span> <span data-ttu-id="b520b-110">Funktionen bearbeta händelser för lagerställeapp anges som:</span><span class="sxs-lookup"><span data-stu-id="b520b-110">The Process warehouse app events feature is listed as:</span></span>

- <span data-ttu-id="b520b-111">**Modul** – Lagerstyrning</span><span class="sxs-lookup"><span data-stu-id="b520b-111">**Module** - Warehouse management</span></span>
- <span data-ttu-id="b520b-112">**Funktionsnamn** - Bearbeta händelser för lagerställeapp</span><span class="sxs-lookup"><span data-stu-id="b520b-112">**Feature name** - Process warehouse app events</span></span>

## <a name="set-up-a-batch-job-to-process-warehouse-app-events"></a><span data-ttu-id="b520b-113">Ställ in ett batchjobb för att bearbeta händelser för lagerställeapp</span><span class="sxs-lookup"><span data-stu-id="b520b-113">Set up a batch job to process warehouse app events</span></span>

### <a name="process-warehouse-app-events"></a><span data-ttu-id="b520b-114">Bearbeta lagerställeapphändelser</span><span class="sxs-lookup"><span data-stu-id="b520b-114">Process warehouse app events</span></span>

<span data-ttu-id="b520b-115">Ställ in ett schemalagt batchjobb för bearbetning händelser för lagerställeapp för skapande av överförda order och raduppdateringar.</span><span class="sxs-lookup"><span data-stu-id="b520b-115">Set up a scheduled batch job to process the warehouse app events for the transfer order creation and line updates.</span></span>

1. <span data-ttu-id="b520b-116">Gå till **lagerstyrning \> periodiska uppgifter \> bearbeta händelser för lagerställeapp**.</span><span class="sxs-lookup"><span data-stu-id="b520b-116">Go to **Warehouse management \> Periodic tasks \> Process warehouse app events**.</span></span>
1. <span data-ttu-id="b520b-117">Dialogrutan bearbeta händelser för lagerställeapp öppnas.</span><span class="sxs-lookup"><span data-stu-id="b520b-117">The Process warehouse app events dialog box opens.</span></span> <span data-ttu-id="b520b-118">Expandera snabbfliken **Kör i bakgrunden** ange **Batchbearbetning** till **Ja**.</span><span class="sxs-lookup"><span data-stu-id="b520b-118">Expand the **Run in background** FastTab and set **Batch processing** to **Yes**.</span></span>
1. <span data-ttu-id="b520b-119">På snabbfliken **kör i bakgrunden** väljer du **återkommande**.</span><span class="sxs-lookup"><span data-stu-id="b520b-119">On the **Run in the background** FastTab, select **Recurrence**.</span></span>
1. <span data-ttu-id="b520b-120">Dialogrutan **Definiera återkommande** öppnas.</span><span class="sxs-lookup"><span data-stu-id="b520b-120">The **Define recurrence** dialog box opens.</span></span> <span data-ttu-id="b520b-121">Ange det körschema som behövs för ditt företag.</span><span class="sxs-lookup"><span data-stu-id="b520b-121">Set the run schedule as needed for your business.</span></span>
1. <span data-ttu-id="b520b-122">Välj **OK** om du vill återgå till dialogrutan **Bearbeta händelser för lagerställeapp**.</span><span class="sxs-lookup"><span data-stu-id="b520b-122">Select **OK** to return to the **Process warehouse app events** dialog box.</span></span>
1. <span data-ttu-id="b520b-123">Välj **OK** i dialogrutan **Bearbeta händelser för lagerställeapp** för att lägga till batchjobbet i batchkön.</span><span class="sxs-lookup"><span data-stu-id="b520b-123">Select **OK** in the **Process warehouse app events** dialog box to add the batch job to the batch queue.</span></span>

## <a name="query-warehouse-app-events"></a><span data-ttu-id="b520b-124">Fråga händelser för lagerställeapp</span><span class="sxs-lookup"><span data-stu-id="b520b-124">Query warehouse app events</span></span>

<span data-ttu-id="b520b-125">Du kan visa den händelsekön och de händelsemeddelanden som har genererats av mobilappen för distributionslagerhantering genom att gå till **Hantering av distributionslager \> Frågor och rapporter \> Loggar för mobil enhet \> Lagerställeapp händelser**.</span><span class="sxs-lookup"><span data-stu-id="b520b-125">You can view the event queue and events messages generated by the Warehouse Management mobile app by going to **Warehouse management \> Inquiries and reports \> Mobile device logs \> Warehouse app events**.</span></span>

## <a name="the-standard-event-queue-process"></a><span data-ttu-id="b520b-126">Standardkö för händelser för lagerställeapp</span><span class="sxs-lookup"><span data-stu-id="b520b-126">The standard event queue process</span></span>

<span data-ttu-id="b520b-127">Kön för händelser för lagerställeapp används vanligtvis tillsammans med följande beskrivna flöde:</span><span class="sxs-lookup"><span data-stu-id="b520b-127">The warehouse app events queue will typically be used with the following described flow:</span></span>

1. <span data-ttu-id="b520b-128">En händelse läggs till i kön med ett händelsemeddelande.</span><span class="sxs-lookup"><span data-stu-id="b520b-128">An event gets added to the queue  with an event message.</span></span> <span data-ttu-id="b520b-129">Det nya meddelandet har inledningsvis händelsetillståndet **väntar**, vilket innebär att batch-jobbet **Bearbeta händelser för lagerställeapp** inte kommer att hämta och bearbeta meddelandet.</span><span class="sxs-lookup"><span data-stu-id="b520b-129">The new message initially has an Event state of **Waiting**, which means that the **Process warehouse app events** batch job will not pick up and process this message.</span></span>
1. <span data-ttu-id="b520b-130">Så snart status för meddelandet har uppdaterats till **I kö** kommer händelsens batchjobb **Bearbeta händelser för lagerställeapp** hämtas och bearbeta händelsen.</span><span class="sxs-lookup"><span data-stu-id="b520b-130">As soon as the message state is updated to **Queued**, the **Process warehouse app** events batch job will pick up and process the event.</span></span>
1. <span data-ttu-id="b520b-131">När batch-jobbet körs uppdateras händelsetillstånden till antingen **slutförd** eller **misslyckad**, beroende på om den begärda processen var möjlig eller inte.</span><span class="sxs-lookup"><span data-stu-id="b520b-131">The batch job updates the event states to either **Completed** or **Failed**, depending on whether the requested process was possible.</span></span>
1. <span data-ttu-id="b520b-132">När alla relaterade händelsemeddelanden har **slutförts** tas händelsen bort från kön.</span><span class="sxs-lookup"><span data-stu-id="b520b-132">When all the related event messages are **Completed**, the event is deleted from the queue.</span></span>

 <span data-ttu-id="b520b-133">Ett detaljerat exempel finns i [skapa överföringsorder från bearbetning av lagerställeapp](create-transfer-order-from-warehouse-app.md).</span><span class="sxs-lookup"><span data-stu-id="b520b-133">For a detailed example, see [Create transfer order from warehouse app process](create-transfer-order-from-warehouse-app.md).</span></span>

## <a name="handle-event-errors"></a><span data-ttu-id="b520b-134">Hantera händelsefel</span><span class="sxs-lookup"><span data-stu-id="b520b-134">Handle event errors</span></span>

<span data-ttu-id="b520b-135">Som en del av bearbetning av händelser för lagerställe kan den begärda meddelande aktiviteten inte ta emot processer från batchjobbet.</span><span class="sxs-lookup"><span data-stu-id="b520b-135">As part of the warehouse event processing, the requested message activity may not receive processes from the batch job.</span></span> <span data-ttu-id="b520b-136">I det här fallet ändras händelse meddelandet till **misslyckad**.</span><span class="sxs-lookup"><span data-stu-id="b520b-136">In this case, the event message will change to **Failed**.</span></span> <span data-ttu-id="b520b-137">Du kan använda **batch-logg** informationen om du vill veta varför och vidta nödvändiga åtgärder för att rätta till eventuella problem.</span><span class="sxs-lookup"><span data-stu-id="b520b-137">You can use the **Batch log** information to learn why and take needed action to correct any problems.</span></span>

<span data-ttu-id="b520b-138">Ett detaljerat exempel finns i [skapa överföringsorder från lagerställeapp](create-transfer-order-from-warehouse-app.md).</span><span class="sxs-lookup"><span data-stu-id="b520b-138">For a detailed example, see [Create transfer order from warehouse app](create-transfer-order-from-warehouse-app.md).</span></span>

<span data-ttu-id="b520b-139">Så här återställer du ett misslyckat meddelande för händelse för lagerställeapp:</span><span class="sxs-lookup"><span data-stu-id="b520b-139">To reset a failed warehouse app event message:</span></span>

1. <span data-ttu-id="b520b-140">Gå till **Lagerlager \> förfrågningar och rapporter \> loggar för mobila enheter \> händelser för lagerställeapp**.</span><span class="sxs-lookup"><span data-stu-id="b520b-140">Go to **Warehouse management \> Inquiries and reports \> Mobile device logs \> Warehouse app events**.</span></span>
1. <span data-ttu-id="b520b-141">På snabbfliken **meddelande för händelse för lagerställeapp**, hitta och välj en relevant händelse som visar **misslyckad** i kolumnen **händelsetillstånd**.</span><span class="sxs-lookup"><span data-stu-id="b520b-141">On the **Warehouse app event messages** FastTab, find and select a relevant event that is showing **Failed** in the **Event state** column.</span></span>
1. <span data-ttu-id="b520b-142">Välj **Återställ** från verktygsfältet **Meddelande om händelse för lagerställe**.</span><span class="sxs-lookup"><span data-stu-id="b520b-142">Select **Reset** from the **Warehouse app event messages** toolbar.</span></span>
1. <span data-ttu-id="b520b-143">Fortsätt arbeta tills alla relevanta meddelanden har återställts.</span><span class="sxs-lookup"><span data-stu-id="b520b-143">Continue working until all relevant messages are reset.</span></span>

<span data-ttu-id="b520b-144">Du kan också ta bort **misslyckat** händelsemeddelande genom att använda alternativet **ta bort** i verktygsfältet **meddelande om händelse för lagerställe**.</span><span class="sxs-lookup"><span data-stu-id="b520b-144">You can also remove a **Failed** event message by using the **Delete** option on the **Warehouse app event messages** toolbar.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]