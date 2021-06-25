---
title: Arbetsbelastning för tillverknings körning för moln och kantskalningsenheter
description: I det här avsnittet beskrivs hur arbetsbelastningar för tillverkningskörning fungerar med moln och kantskalningsenheter.
author: cabeln
ms.date: 10/06/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: SCM
ms.author: cabeln
ms.search.validFrom: 2020-10-06
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 9cd7dd8b9241171bdfdb3cc1379211a2fe99bbe1
ms.sourcegitcommit: 8d50c905a0c9d4347519549b587bdebab8ffc628
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2021
ms.locfileid: "6184006"
---
# <a name="manufacturing-execution-workloads-for-cloud-and-edge-scale-units"></a><span data-ttu-id="69957-103">Arbetsbelastningar för tillverkningskörning för moln- och kantskalningsenheter</span><span class="sxs-lookup"><span data-stu-id="69957-103">Manufacturing execution workloads for cloud and edge scale units</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

> [!WARNING]
> <span data-ttu-id="69957-104">Arbetsbelastningen för tillverkningskörningen är vid den här tidpunkten tillgänglig i förhandsgranskning.</span><span class="sxs-lookup"><span data-stu-id="69957-104">The manufacturing execution workload is available in preview at this point in time.</span></span>
> <span data-ttu-id="69957-105">Vissa företagsfunktioner stöds inte fullt ut i den allmänna förhandsgranskningen när enheter för belastningsenheter används.</span><span class="sxs-lookup"><span data-stu-id="69957-105">Some business functionality isn't fully supported in the public preview when workload scale units are used.</span></span>

<span data-ttu-id="69957-106">Vid tillverkningskörningen har skalningsenheter följande funktioner:</span><span class="sxs-lookup"><span data-stu-id="69957-106">In manufacturing execution, scale units deliver the following capabilities:</span></span>

- <span data-ttu-id="69957-107">Maskinoperatörer och arbetsledare kan komma åt den operationella produktionsplanen.</span><span class="sxs-lookup"><span data-stu-id="69957-107">Machine operators and shop floor supervisors can access the operational production plan.</span></span>
- <span data-ttu-id="69957-108">Maskinoperatörer kan hålla planen aktuell genom att köra separata jobb för bearbetning och processtillverkning.</span><span class="sxs-lookup"><span data-stu-id="69957-108">Machine operators can keep the plan up to date by running discrete and process manufacturing jobs.</span></span>
- <span data-ttu-id="69957-109">Arbetsledaren kan justera driftsplanen.</span><span class="sxs-lookup"><span data-stu-id="69957-109">The shop floor supervisor can adjust the operational plan.</span></span>
- <span data-ttu-id="69957-110">Arbetare kan få åtkomst till tid och närvaro för in- och utstämpling "on the edge" - i utkanten av nätverket istället för som annars centralt - för att säkerställa korrekt löneberäkning för arbetare.</span><span class="sxs-lookup"><span data-stu-id="69957-110">Workers can access time and attendance for clock-in and clock-out on the edge, to ensure correct worker pay calculation.</span></span>

<span data-ttu-id="69957-111">I det här avsnittet beskrivs hur arbetsbelastningar för tillverkningskörning fungerar med moln och kantskalningsenheter.</span><span class="sxs-lookup"><span data-stu-id="69957-111">This topic describes how manufacturing execution workloads work with cloud and edge scale units.</span></span>

## <a name="the-manufacturing-lifecycle"></a><span data-ttu-id="69957-112">Tillverkningslivscykeln</span><span class="sxs-lookup"><span data-stu-id="69957-112">The manufacturing lifecycle</span></span>

<span data-ttu-id="69957-113">Som visas i bilden nedan är tillverkningslivscykeln uppdelad i tre faser: *planera*, *utföra* och *slutföra*.</span><span class="sxs-lookup"><span data-stu-id="69957-113">As the following illustration shows, the manufacturing lifecycle is divided into three phases: *Plan*, *Execute*, and *Finalize*.</span></span>

<span data-ttu-id="69957-114">[![Tillverkningskörningsfaser när en enskild miljö används](media/mes-phases.png "Tillverkningskörningsfaser när en enskild miljö används")](media/mes-phases-large.png)</span><span class="sxs-lookup"><span data-stu-id="69957-114">[![Manufacturing execution phases when a single environment is used](media/mes-phases.png "Manufacturing execution phases when a single environment is used")](media/mes-phases-large.png)</span></span>

<span data-ttu-id="69957-115">_Planeringsfasen_ omfattar produktdefinition, planering, skapande och tidsplanering av order och frisläppning.</span><span class="sxs-lookup"><span data-stu-id="69957-115">The _Plan_ phase includes product definition, planning, order creation and scheduling, and release.</span></span> <span data-ttu-id="69957-116">Frisläppningssteget visar över gången från _planeringsfasen_ till _körningsfasen_.</span><span class="sxs-lookup"><span data-stu-id="69957-116">The release step indicates the transition from the _Plan_ phase to the _Execute_ phase.</span></span> <span data-ttu-id="69957-117">När en tillverkningsorder frisläpps visas produktionsorderjobben på produktionsvåningen och är klara för körning.</span><span class="sxs-lookup"><span data-stu-id="69957-117">When a production order is released, the production order jobs will be visible on the production floor and ready for execution.</span></span>

<span data-ttu-id="69957-118">När ett produktionsjobb markeras som slutfört flyttas det från _körningsfasen_ till _avslutningsfasen_.</span><span class="sxs-lookup"><span data-stu-id="69957-118">When a production job is marked as completed, it moves from the _Execute_ phase to the _Finalize_ phase.</span></span> <span data-ttu-id="69957-119">I _Avslutningsfasen_ går registreringar från *Körningsfasen* går igenom ett godkännandearbetsflöde där de beräknas, godkänns och överförs.</span><span class="sxs-lookup"><span data-stu-id="69957-119">In the _Finalize_ phase, the registrations from the *Execute* phase go through an approval workflow, where they are calculated, approved, and transferred.</span></span> <span data-ttu-id="69957-120">Vid den tidpunkten slutförs tillverkningsordern.</span><span class="sxs-lookup"><span data-stu-id="69957-120">At that point, the production order is completed.</span></span> <span data-ttu-id="69957-121">Underlaget för arbetarens lön genereras därför.</span><span class="sxs-lookup"><span data-stu-id="69957-121">Therefore, the basis for the workers' pay is generated.</span></span>

## <a name="splitting-the-execute-phase-into-a-separate-workload"></a><span data-ttu-id="69957-122">Dela körningsfasen i en separat arbetsbelastning</span><span class="sxs-lookup"><span data-stu-id="69957-122">Splitting the Execute phase into a separate workload</span></span>

<span data-ttu-id="69957-123">Som följande bild visar, när skalenheter används delas _körningsfasen_ ut som separat arbetsbelastning.</span><span class="sxs-lookup"><span data-stu-id="69957-123">As the following illustration shows, when scale units are used, the _Execute_ phase is split out as a separate workload.</span></span>

<span data-ttu-id="69957-124">[![Produktionskörningsfaser när skalenheter används](media/mes-phases-workloads.png "Produktionskörningsfaser när skalenheter används")](media/mes-phases-workloads-large.png)</span><span class="sxs-lookup"><span data-stu-id="69957-124">[![Manufacturing execution phases when scale units are used](media/mes-phases-workloads.png "Manufacturing execution phases when scale units are used")](media/mes-phases-workloads-large.png)</span></span>

<span data-ttu-id="69957-125">Modellen hämtas nu från en installation med enkel instans till en modell som baseras på navet och skalenheten.</span><span class="sxs-lookup"><span data-stu-id="69957-125">The model now goes from a single-instance installation to a model that is based on the hub and scale units.</span></span> <span data-ttu-id="69957-126">_Planeringsfasen_ och _avslutningsfasen_ körs som backoffice-operationer på navet och arbetsbelastningen för tillverkningskörning körs på skalenheterna.</span><span class="sxs-lookup"><span data-stu-id="69957-126">The _Plan_ and _Finalize_ phases run as back-office operations on the hub, and the manufacturing execution workload runs on the scale units.</span></span> <span data-ttu-id="69957-127">Data överförs asynkront mellan nav och skalenhet.</span><span class="sxs-lookup"><span data-stu-id="69957-127">Data is transferred asynchronously between the hub and scale units.</span></span>

<span data-ttu-id="69957-128">När en tillverknings order frisläpps på navet överförs alla data som krävs för att bearbeta produktions jobben till skalenheten.</span><span class="sxs-lookup"><span data-stu-id="69957-128">When a production order is released on the hub, all data that is required to process production jobs is transferred to the scale unit.</span></span> <span data-ttu-id="69957-129">Dessa data omfattar produktionsorder, produktionsflöden, strukturlistor och produkter.</span><span class="sxs-lookup"><span data-stu-id="69957-129">This data includes production orders, production routes, bills of materials, and products.</span></span> <span data-ttu-id="69957-130">Data som inte är relaterade till en tillverkningsorder (t.ex. indirekta aktiviteter, frånvarokoder och produktionsparametrar) överförs också från navet till skalenheten.</span><span class="sxs-lookup"><span data-stu-id="69957-130">Data that isn't related to a production order (such as indirect activities, absence codes, and production parameters) is also transferred from the hub to the scale unit.</span></span> <span data-ttu-id="69957-131">Som regel kan data som kommer från navet och som överförs till skalenheten bara skapas eller uppdateras på navet.</span><span class="sxs-lookup"><span data-stu-id="69957-131">As a rule, data that originates from the hub and that is transferred to the scale unit can be created or updated only on the hub.</span></span> <span data-ttu-id="69957-132">En ny frånvarokod eller indirekt aktivitet kan till exempel inte skapas i skalenheten&mdash;de kan bara användas för registrering.</span><span class="sxs-lookup"><span data-stu-id="69957-132">For example, a new absence code or indirect activity can't be created on the scale unit&mdash;they can be used only for registration.</span></span> <span data-ttu-id="69957-133">Registreringarna som görs på skalenheten under körningen överförs sedan till navet, där godkännande av tid och närvaro, lager och ekonomiska uppdateringar bearbetas.</span><span class="sxs-lookup"><span data-stu-id="69957-133">The registrations that are made on the scale unit during execution are then transferred to the hub, where time and attendance approval, inventory, and financial updates are processed.</span></span>

## <a name="manufacturing-execution-tasks-that-can-be-run-on-workloads"></a><span data-ttu-id="69957-134">Tillverkningskörningsuppgifter som kan köras på arbetsbelastningar</span><span class="sxs-lookup"><span data-stu-id="69957-134">Manufacturing execution tasks that can be run on workloads</span></span>

<span data-ttu-id="69957-135">Följande uppgifter för tillverkningskörning kan förnärvarande köras på arbetsbelastningar när skalenheter används:</span><span class="sxs-lookup"><span data-stu-id="69957-135">The following manufacturing execution tasks can currently be run on workloads when scale units are used:</span></span>

- <span data-ttu-id="69957-136">Instämpling, inloggning, utstämpling och frånvaro</span><span class="sxs-lookup"><span data-stu-id="69957-136">Clock-in, log-in, clock-out, and absence</span></span>
- <span data-ttu-id="69957-137">Startjobb</span><span class="sxs-lookup"><span data-stu-id="69957-137">Start job</span></span>
- <span data-ttu-id="69957-138">Bunta jobb</span><span class="sxs-lookup"><span data-stu-id="69957-138">Bundle jobs</span></span>
- <span data-ttu-id="69957-139">Rapportförlopp</span><span class="sxs-lookup"><span data-stu-id="69957-139">Report progress</span></span>
- <span data-ttu-id="69957-140">Rapportera kassation</span><span class="sxs-lookup"><span data-stu-id="69957-140">Report scrap</span></span>
- <span data-ttu-id="69957-141">Indirekt aktivitet</span><span class="sxs-lookup"><span data-stu-id="69957-141">Indirect activity</span></span>
- <span data-ttu-id="69957-142">Avbrott</span><span class="sxs-lookup"><span data-stu-id="69957-142">Break</span></span>
- <span data-ttu-id="69957-143">Rapportera som färdig och artikelinförsel (kräver att du även kör arbetsbelastningen för lagerställekörningen på din skalningsenhet, se även [Rapportera som färdig och artikelinförsel](#RAF))</span><span class="sxs-lookup"><span data-stu-id="69957-143">Report as finished and putaway (requires that you also run the warehouse execution workload on your scale unit, see also [Report as finished and putaway on a scale unit](#RAF))</span></span>

## <a name="working-with-manufacturing-execution-workloads-on-the-hub"></a><span data-ttu-id="69957-144">Arbeta med arbetsbelastningar för tillverkningskörning på navet</span><span class="sxs-lookup"><span data-stu-id="69957-144">Working with manufacturing execution workloads on the hub</span></span>

<span data-ttu-id="69957-145">De processer som krävs för att köra arbetsbelastningar i tillverkningsprocessen körs automatiskt för att behålla navet och alla skalenheter synkroniserade efter behov.</span><span class="sxs-lookup"><span data-stu-id="69957-145">Usually, the processes that are required to run manufacturing execution workloads run automatically to keep the hub and all the scale units in sync, as needed.</span></span> <span data-ttu-id="69957-146">Om du däremot har problem kan du manuellt utlösa bearbetningen av råregistreringar som tas emot från arbetsbelastningar och/eller kontrollera bearbetningsloggen för registrering.</span><span class="sxs-lookup"><span data-stu-id="69957-146">However, if you're having trouble, you can manually trigger the processing of raw registrations that are received from workloads and/or check the registration processing log.</span></span>

### <a name="manually-process-raw-registrations"></a><span data-ttu-id="69957-147">Bearbeta råregistreringar manuellt</span><span class="sxs-lookup"><span data-stu-id="69957-147">Manually process raw registrations</span></span>

<span data-ttu-id="69957-148">Ett batchjobb i Supply Chain Management körs automatiskt för att bearbeta alla registreringar som har mottagits från arbetsbördan.</span><span class="sxs-lookup"><span data-stu-id="69957-148">A batch job in Supply Chain Management runs automatically to process all the registrations that have been received from the workloads.</span></span> <span data-ttu-id="69957-149">Det här jobbet skapar de nödvändiga produktionsjournalerna och loggboksposter när en registrering bearbetas för ett slutfört jobb på arbetsbelastningen.</span><span class="sxs-lookup"><span data-stu-id="69957-149">This job creates the required production journals and logbook entries when a registration is processed for a completed job on the workload.</span></span>

<span data-ttu-id="69957-150">Även om jobbet vanligtvis körs automatiskt kan du när som helst köra det manuellt genom att logga in på navet och gå till **produktionskontrollen \> periodiska uppgifter \> hantering av backoffice-arbetsbelastning \> behandla råregistreringar**.</span><span class="sxs-lookup"><span data-stu-id="69957-150">Although the job usually runs automatically, you can run it manually at any time by signing in to the hub and going to **Production control \> Periodic tasks \> Backoffice workload management \> Process raw registrations**.</span></span>

### <a name="check-the-raw-registration-processing-log"></a><span data-ttu-id="69957-151">Kontrollera bearbetningsloggen för råregistreringar</span><span class="sxs-lookup"><span data-stu-id="69957-151">Check the raw registration processing log</span></span>

<span data-ttu-id="69957-152">Du kan granska bearbetningsloggen för registrering genom att logga in på navet och gå till **tillverkningskontroll \> periodiska uppgifter \> hantering av backoffice-arbetsbelastning \> bearbetningslogg för råregistrering**.</span><span class="sxs-lookup"><span data-stu-id="69957-152">To review the registration processing log, sign in to the hub, and go to **Production control \> Periodic tasks \> Backoffice workload management \> Raw registration processing log**.</span></span> <span data-ttu-id="69957-153">På sidan **bearbetningslogg för råregistrering** visas en lista över bearbetade råregistreringar och status för varje registrering.</span><span class="sxs-lookup"><span data-stu-id="69957-153">The **Raw registration processing log** page shows a list of processed raw registrations and the status of each registration.</span></span>

<span data-ttu-id="69957-154">![Sidan bearbetningslogg för råregistreringar](media/mes-processing-log.png "Sidan bearbetningslogg för råregistreringar")</span><span class="sxs-lookup"><span data-stu-id="69957-154">![Raw registration processing log page](media/mes-processing-log.png "Raw registration processing log page")</span></span>

<span data-ttu-id="69957-155">Du kan arbeta med valfri registrering i listan genom att markera den och sedan välja någon av följande knappar i åtgärdsfönstret:</span><span class="sxs-lookup"><span data-stu-id="69957-155">You can work on any registration in the list by selecting it and then selecting one of the following buttons on the Action Pane:</span></span>

- <span data-ttu-id="69957-156">**Process** – bearbeta den valda registreringen manuellt.</span><span class="sxs-lookup"><span data-stu-id="69957-156">**Process** – Manually process the selected registration.</span></span> <span data-ttu-id="69957-157">Den här åtgärden kan vara användbar om jobbet _Bearbeta råregistreringar_ inte körs eller om det misslyckas.</span><span class="sxs-lookup"><span data-stu-id="69957-157">This action can be useful if the _Process raw registrations_ job hasn't run, or if it failed.</span></span>
- <span data-ttu-id="69957-158">**Avbryt** – Avbryt den valda registreringen.</span><span class="sxs-lookup"><span data-stu-id="69957-158">**Cancel** – Cancel the selected registration.</span></span>

## <a name="working-with-manufacturing-execution-workloads-on-a-scale-unit"></a><span data-ttu-id="69957-159">Arbeta med arbetsbelastningar för tillverkningskörning på en skalenhet</span><span class="sxs-lookup"><span data-stu-id="69957-159">Working with manufacturing execution workloads on a scale unit</span></span>

<span data-ttu-id="69957-160">De processer som krävs för att köra arbetsbelastningar i tillverkningsprocessen körs automatiskt för att behålla navet och alla skalenheter synkroniserade efter behov.</span><span class="sxs-lookup"><span data-stu-id="69957-160">Usually, the processes that are required to run manufacturing execution workloads run automatically to keep the hub and all the scale units in sync, as needed.</span></span> <span data-ttu-id="69957-161">Om du har problem kan du emellertid kontrollera historiken för order som har bearbetats på en skalenhet eller köra jobbet _tillverkningsnav till skalenhet meddelandeprocessor_.</span><span class="sxs-lookup"><span data-stu-id="69957-161">However, if you're having trouble, you can check the history of orders that have been processed on a scale unit or manually run the _Manufacturing hub to scale unit message processor_ job.</span></span>

### <a name="view-the-history-of-manufacturing-jobs-that-have-been-processed-on-a-scale-unit"></a><span data-ttu-id="69957-162">Visa historiken för tillverkningsjobb som har bearbetats på en skalenhet</span><span class="sxs-lookup"><span data-stu-id="69957-162">View the history of manufacturing jobs that have been processed on a scale unit</span></span>

<span data-ttu-id="69957-163">För att granska historiken om tillverkningsjobb som har bearbetats på en skalenhet, logga in på skalenheten och gå till **tillverkningskontroll \> periodiska uppgifter \> hantering av backoffice-arbetsbelastning \> historiken för bearbetning av tillverkningsjobb**.</span><span class="sxs-lookup"><span data-stu-id="69957-163">To review the history of manufacturing jobs that have been processed on a scale unit, sign in to the scale unit machine, and go to **Production control \> Periodic tasks \> Backoffice workload management \> Manufacturing jobs processing history**.</span></span> <span data-ttu-id="69957-164">Sidan **historik för bearbetning av tillverkningsjobb** visar bearbetningshistoriken för tillverkningsorder på skalenheten.</span><span class="sxs-lookup"><span data-stu-id="69957-164">The **Manufacturing jobs processing history** page shows the processing history of the production orders on the scale unit.</span></span> <span data-ttu-id="69957-165">Du kan arbeta med valfri produktionsorder i listan genom att markera den och sedan välja någon av följande knappar i åtgärdsfönstret:</span><span class="sxs-lookup"><span data-stu-id="69957-165">You can work on any production order in the list by selecting it and then selecting one of the following buttons on the Action Pane:</span></span>

- <span data-ttu-id="69957-166">**Process** – bearbeta den valda produktionsorder manuellt.</span><span class="sxs-lookup"><span data-stu-id="69957-166">**Process** – Manually process the selected production order.</span></span>
- <span data-ttu-id="69957-167">**Avbryt** – Avbryt den valda produktionsordern.</span><span class="sxs-lookup"><span data-stu-id="69957-167">**Cancel** – Cancel the selected production order.</span></span>

### <a name="manufacturing-hub-to-scale-unit-message-processor-job"></a><span data-ttu-id="69957-168">Tillverkningsnav till skalenhet meddelande processorjobb</span><span class="sxs-lookup"><span data-stu-id="69957-168">Manufacturing hub to scale unit message processor job</span></span>

<span data-ttu-id="69957-169">Jobbet _Tillverkningsnav till skalenhet meddelande processorjobb_ bearbetar data från navet till skalenheten.</span><span class="sxs-lookup"><span data-stu-id="69957-169">The _Manufacturing hub to scale unit message processor_ job processes data from the hub to the scale unit.</span></span> <span data-ttu-id="69957-170">Det här jobbet startas automatiskt när arbetsbelastning för tillverkningskörningen distribueras.</span><span class="sxs-lookup"><span data-stu-id="69957-170">This job is automatically started when the manufacturing execution workload is deployed.</span></span> <span data-ttu-id="69957-171">Du kan dock köra den manuellt när som helst genom att gå till **tillverkningskontroll \> periodiska uppgifter \> hantering av backoffice-arbetsbelastning \> Tillverkningsnav till skalenhet meddelande processorjobb**.</span><span class="sxs-lookup"><span data-stu-id="69957-171">However, you can run it manually at any time by going to **Production control \> Periodic tasks \> Backoffice workload management \> Manufacturing hub to scale unit message processor**.</span></span>

<a name="RAF"></a>

## <a name="report-as-finished-and-putaway-on-a-scale-unit"></a><span data-ttu-id="69957-172">Rapportera som färdig och artikelinförsel på en skalningsenhet</span><span class="sxs-lookup"><span data-stu-id="69957-172">Report as finished and putaway on a scale unit</span></span>

<!-- KFM: 
This section describes how to enable the abilities to report as finished and then putaway finished items when you are using to a scale unit.

### Enable and use report as finished and putaway on a scale unit -->

<span data-ttu-id="69957-173">I den aktuella versionen stöds funktionerna "rapportera som färdig" och "artikelinförsel" (för färdiga produkter, samprodukter och biprodukter) av [körningsarbetsbelastningen för lagerställe](cloud-edge-workload-warehousing.md) (inte av körningsarbetsbelastningen för tillverkning).</span><span class="sxs-lookup"><span data-stu-id="69957-173">In the current release, report as finished and putaway operations (for finished products, co-products, and by-products) are supported by the [warehouse execution workload](cloud-edge-workload-warehousing.md) (not the manufacturing execution workload).</span></span> <span data-ttu-id="69957-174">Om du vill använda den här funktionen vid anslutning till en skalningsenhet måste du därför göra följande:</span><span class="sxs-lookup"><span data-stu-id="69957-174">Therefore, to use this functionality when connected to a scale unit, you must do the following:</span></span>

- <span data-ttu-id="69957-175">Installera både körningsarbetsbelastningen för lagerstället och körningsarbetsbelastningen för tillverkning på din skalningsenhet.</span><span class="sxs-lookup"><span data-stu-id="69957-175">Install both the warehouse execution workload and the manufacturing execution workload on your scale unit.</span></span>
- <span data-ttu-id="69957-176">Använd mobilapplikationen Warehouse Management om du vill rapportera som färdig och bearbeta artikelinförselarbetet.</span><span class="sxs-lookup"><span data-stu-id="69957-176">Use the Warehouse Management mobile app to report as finished and process the putaway work.</span></span> <span data-ttu-id="69957-177">Körningsgränssnittet för produktionsgolv har för närvarande inte stöd för dessa processer.</span><span class="sxs-lookup"><span data-stu-id="69957-177">The production floor execution interface does not currently support these processes.</span></span>

<!-- KFM: API details needed

### Customize report as finished and putaway functionality

 -->

[!INCLUDE [cloud-edge-privacy-notice](../../includes/cloud-edge-privacy-notice.md)]

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
