---
title: Schemalägga arbetsskapande under cykel
description: Det här avsnittet beskriver hur du ställer in och använder metoden Schemalägga arbetsskapande under cykel.
author: perlynne
manager: mirzaab
ms.date: 01/14/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSPostMethod, WHSWavePostMethodTaskConfig, WHSWaveTemplateTable, WHSParameters, WHSWaveTableListPage, WHSWorkTableListPage, WHSWorkTable, BatchJobEnhanced, WHSPlannedWorkOrder
audience: Application User
ms.reviewer: ''
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2021-01-14
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: ed8f43c7db139b7b16ac6901d5db56ba2f021690
ms.sourcegitcommit: b7a7a14f8650913f6797ae1c4a82ad8adfe415fd
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/28/2021
ms.locfileid: "5078308"
---
# <a name="schedule-work-creation-during-wave"></a><span data-ttu-id="135dd-103">Schemalägga arbetsskapande under cykel</span><span class="sxs-lookup"><span data-stu-id="135dd-103">Schedule work creation during wave</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="135dd-104">Använd funktionen *Schemalägga arbetsskapande* som en del av din påfyllnadsprocess för att öka påfyllnadsprocessens genomströmning genom att systemet skapar arbete med parallell bearbetning.</span><span class="sxs-lookup"><span data-stu-id="135dd-104">Use the *Schedule work creation* feature as part of your waving process to help increase wave processing throughput by having the system create work using parallel processing.</span></span>

<span data-ttu-id="135dd-105">När funktionaliteten är aktiverad kommer planerat arbete automatiskt att få skapat, vilket systemet så småningom kommer att bearbeta för att skapa verkligt arbete.</span><span class="sxs-lookup"><span data-stu-id="135dd-105">When the functionality is enabled, planned work will automatically get created, which the system will eventually process to create actual work.</span></span> <span data-ttu-id="135dd-106">Om antalet påfyllnadsbelastningsrader når ett förutbestämt tröskelvärde kommer systemet att skapa verkligt arbete snabbare genom att tillämpa parallell, asynkron bearbetning.</span><span class="sxs-lookup"><span data-stu-id="135dd-106">If the number of wave load lines reaches a predetermined threshold, the system will create actual work more quickly by applying parallel, asynchronous processing.</span></span>

## <a name="enable-the-schedule-work-creation-feature"></a><span data-ttu-id="135dd-107">Aktivera funktionen Schemalägga arbetsskapande</span><span class="sxs-lookup"><span data-stu-id="135dd-107">Enable the Schedule work creation feature</span></span>

### <a name="enable-the-feature-in-feature-management"></a><span data-ttu-id="135dd-108">Aktivera nya funktioner i funktionshantering</span><span class="sxs-lookup"><span data-stu-id="135dd-108">Enable the feature in feature management</span></span>

<span data-ttu-id="135dd-109">Innan du kan använda funktionen *Schemalägga arbetsskapande* den aktiveras i ditt system.</span><span class="sxs-lookup"><span data-stu-id="135dd-109">Before you can use the *Schedule work creation* feature, it must be turned on in your system.</span></span> <span data-ttu-id="135dd-110">Administratörer kan använda arbetsytan [funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) för att kontrollera funktionens status och aktivera den om det behövs.</span><span class="sxs-lookup"><span data-stu-id="135dd-110">Admins can use the [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) workspace to check the status of the feature and turn it on if it's required.</span></span> <span data-ttu-id="135dd-111">Funktionen visas på följande sätt:</span><span class="sxs-lookup"><span data-stu-id="135dd-111">There, the feature is listed in the following way:</span></span>

- <span data-ttu-id="135dd-112">**Modul:** *Lagerstyrning*</span><span class="sxs-lookup"><span data-stu-id="135dd-112">**Module:** *Warehouse management*</span></span>
- <span data-ttu-id="135dd-113">**Funktionens namn:** *Schemalägga arbetsskapande*</span><span class="sxs-lookup"><span data-stu-id="135dd-113">**Feature name:** *Schedule work creation*</span></span>

> [!NOTE]
> <span data-ttu-id="135dd-114">Funktionen *Arbetsspärr för hela organisationen* måste vara aktiverad innan du kan aktivera *Schemalägga arbetsskapande*.</span><span class="sxs-lookup"><span data-stu-id="135dd-114">The *Organization-wide work blocking* feature must be enabled before you can enable *Schedule work creation*.</span></span>

### <a name="manually-enable-batch-processing-of-waves"></a><span data-ttu-id="135dd-115">Aktivera batchbearbetning av påfyllnad manuellt</span><span class="sxs-lookup"><span data-stu-id="135dd-115">Manually enable batch processing of waves</span></span>

<span data-ttu-id="135dd-116">För att dra nytta av en parallell asynkron metod för att skapa lagerarbete, måste din påfyllnadsprocess köras i batch.</span><span class="sxs-lookup"><span data-stu-id="135dd-116">To take advantage of a parallel asynchronous method to create warehouse work, your wave process must be running in batch.</span></span> <span data-ttu-id="135dd-117">Så här ställer du in det:</span><span class="sxs-lookup"><span data-stu-id="135dd-117">To set this up:</span></span>

1. <span data-ttu-id="135dd-118">Gå till  **Lagerstyrning\>Inställningar\>Parametrar för lagerstyrning**.</span><span class="sxs-lookup"><span data-stu-id="135dd-118">Go to **Warehouse management \> Setup \> Warehouse management parameters**.</span></span>

1. <span data-ttu-id="135dd-119">På sidan **Allmänt**, ange **Behandla påfyllnader i batch** till *Ja*.</span><span class="sxs-lookup"><span data-stu-id="135dd-119">On the **General** tab, set **Process waves in batch** to *Yes*.</span></span> <span data-ttu-id="135dd-120">Eventuellt kan du också välja en dedikerad **Batchgrupp för påfyllnadsbearbetning** för att förhindra att din batch-kö bearbetning körs samtidigt som andra processer.</span><span class="sxs-lookup"><span data-stu-id="135dd-120">Optionally, you can also select a dedicated **Wave processing batch group** to prevent your batch queue processing from running at the same time as other processes.</span></span>

1. <span data-ttu-id="135dd-121">Ange **Vänta på lås (ms) tid**, som gäller när systemet bearbetar flera påfyllningar samtidigt.</span><span class="sxs-lookup"><span data-stu-id="135dd-121">Set the **Wait for lock (ms) time**, which applies when the system is processing several waves at the same time.</span></span> <span data-ttu-id="135dd-122">För de flesta större påfyllningsprocesser rekommenderar vi ett värde på *60000*.</span><span class="sxs-lookup"><span data-stu-id="135dd-122">For most larger waving processes, we recommend a value of *60000*.</span></span>

### <a name="manually-enable-the-new-wave-step-method-for-existing-wave-templates"></a><span data-ttu-id="135dd-123">Aktivera metoden nytt påfyllnadssteg manuellt för befintliga påfyllnadsmallar</span><span class="sxs-lookup"><span data-stu-id="135dd-123">Manually enable the new wave step method for existing wave templates</span></span>

<span data-ttu-id="135dd-124">Börja med att skapa den nya påfyllnadsstegmetoden och aktivera den för parallell asynkron uppgiftsbearbetning.</span><span class="sxs-lookup"><span data-stu-id="135dd-124">Start by creating the new wave step method and enabling it for parallel asynchronous task processing.</span></span>

1. <span data-ttu-id="135dd-125">Gå till  **Lagerstyrning \> Inställningar \> Påfyllnader \> Metoder för påfyllnadsprocess**.</span><span class="sxs-lookup"><span data-stu-id="135dd-125">Go to **Warehouse management \> Setup \> Waves \> Wave process methods**.</span></span>

1. <span data-ttu-id="135dd-126">Välj  **återskapa metoder** och observera att *WHSScheduleWorkCreationWaveStepMethod* har lagts till i listan över metoder för påfyllnadsprocess kan du använda i påfyllnadsmallar för leverans.</span><span class="sxs-lookup"><span data-stu-id="135dd-126">Select  **Regenerate method** and note that *WHSScheduleWorkCreationWaveStepMethod* has been added to the list of wave process methods you can use in your shipping wave templates.</span></span>

1. <span data-ttu-id="135dd-127">Välj posten med **metodnamnet** *WHSScheduleWorkCreationWaveStepMethod* och välj **Konfiguration av uppgift**.</span><span class="sxs-lookup"><span data-stu-id="135dd-127">Select the record with the **Method name** *WHSScheduleWorkCreationWaveStepMethod* and select **Task configuration**.</span></span>

1. <span data-ttu-id="135dd-128">Välj om du vill lägga till en ny rad i rutnätet **Ny** i åtgärdsfönstret och använd följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="135dd-128">To add a new row to the grid, select **New** on the Action Pane and use the following settings:</span></span>

    - <span data-ttu-id="135dd-129">**Lagerställe** - Välj det lager du ska använda för att schemalägga bearbetning av arbete.</span><span class="sxs-lookup"><span data-stu-id="135dd-129">**Warehouse** - Select the warehouse you will use to schedule work creation processing.</span></span>

    - <span data-ttu-id="135dd-130">**Maximalt antal batchuppgifter** - Ange ett maximalt antal batchuppgifter.</span><span class="sxs-lookup"><span data-stu-id="135dd-130">**Maximum number of batch tasks** - Specify a maximum number of batch tasks.</span></span> <span data-ttu-id="135dd-131">I de flesta fall bör detta värde vara i intervallet från 8-16, men vi rekommenderar att du experimenterar med den optimala inställningen baserat på dina scenarier.</span><span class="sxs-lookup"><span data-stu-id="135dd-131">In most cases, this value should be in the range from 8-16, however we recommend that you experiment with the optimal setting based on your scenarios.</span></span>

    - <span data-ttu-id="135dd-132">**Batchgrupp för påfyllnadsbearbetning** - Välj en särskild batchgrupp för påfyllnadsbearbetning för att optimera bearbetning av batchkö.</span><span class="sxs-lookup"><span data-stu-id="135dd-132">**Wave processing batch group** - Select a dedicated wave processing batch group to optimize your batch queue processing.</span></span>

<span data-ttu-id="135dd-133">Nu är du redo att uppdatera en befintlig påfyllnadsmall (eller skapa en ny) för att använda metoden för påfyllnadsbearbetning *Schemalägga arbetsskapande*.</span><span class="sxs-lookup"><span data-stu-id="135dd-133">Now you are ready to update an existing wave template (or create a new one) to use the *Schedule work creation* wave processing method.</span></span>

1. <span data-ttu-id="135dd-134">Gå till  **Lagerstyrning \> Inställningar \> Påfyllnader \> Påfyllnadsmallar**.</span><span class="sxs-lookup"><span data-stu-id="135dd-134">Go to **Warehouse management \> Setup \> Waves \> Wave templates**.</span></span>

1. <span data-ttu-id="135dd-135">I åtgärdsfönstret väljer du **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="135dd-135">Select **Edit** on the Action Pane.</span></span>

1. <span data-ttu-id="135dd-136">I listfönstret väljer du den påfyllnadsmall som du vill uppdatera (om du testar med demodata kan du använda *standardvärdet för leverans 24*).</span><span class="sxs-lookup"><span data-stu-id="135dd-136">In the list pane, select the wave template you would like to update (if you are testing using demo data, then you could use *24 Shipping default*).</span></span>

1. <span data-ttu-id="135dd-137">Expandera snabbflikarna **Metoder** och markera raden med hjälp av **Namn** *Schemalägga arbetsskapande* i rutnätet **Resterande metoder**.</span><span class="sxs-lookup"><span data-stu-id="135dd-137">Expand the **Methods** FastTab and select the row with the **Name** *Schedule work creation* in the **Remaining methods** grid.</span></span>

1. <span data-ttu-id="135dd-138">Markera pilen som pekar på kolumnen **Markerade metoder** om du vill flytta den markerade raden till den kolumnen.</span><span class="sxs-lookup"><span data-stu-id="135dd-138">Select the arrow pointing to the **Selected methods** column to move the selected row to that column.</span></span> <span data-ttu-id="135dd-139">(Du kan bara ha en vald metod åt gången som använder endera *WHSScheduleWorkCreationWaveStepMethod* eller *createWork*, så den befintliga raden med **metodnamn** *createWork* flyttas automatiskt till rutnätet **Resterande metoder**.)</span><span class="sxs-lookup"><span data-stu-id="135dd-139">(You can only have one selected method at a time that uses either *WHSScheduleWorkCreationWaveStepMethod* or *createWork*, so the existing row with **Method name** *createWork* is automatically moved to the **Remaining methods** grid.)</span></span>

## <a name="set-wave-task-processing-threshold-data"></a><span data-ttu-id="135dd-140">Ställ in tröskelvärdesdata för bearbetning av påfyllnadsuppgift</span><span class="sxs-lookup"><span data-stu-id="135dd-140">Set wave task processing threshold data</span></span>

<span data-ttu-id="135dd-141">Systemet skapar tröskeldata för standardaktivitetsbearbetning första gången en påfyllnadsprocess körs med hjälp av uppgiftsbaserad bearbetning.</span><span class="sxs-lookup"><span data-stu-id="135dd-141">The system will create default wave task processing threshold data the first time a wave process runs using any task-based processing.</span></span> <span data-ttu-id="135dd-142">Data används för att kontrollera när påfyllnadsbearbetningen kommer att köras asynkront och vara uppgiftsbaserad, vilket gör det möjligt att bearbeta och skapa arbete parallellt.</span><span class="sxs-lookup"><span data-stu-id="135dd-142">The data is used to control when wave processing will run asynchronously and be task-based, which enables it to process and create work in parallel.</span></span>

<span data-ttu-id="135dd-143">Standarddata använder inledningsvis ett tröskelvärde på 15 för minsta antal belastningsrader (MINIMUMLINESLOADLINES).</span><span class="sxs-lookup"><span data-stu-id="135dd-143">The default data will initially use a threshold value of 15 for the minimum number of load lines (MINIMUMWAVELOADLINES).</span></span> <span data-ttu-id="135dd-144">Det innebär att när systemet bearbetar en våg med mer än 15 belastningsrader kommer den att använda asynkron uppgiftsbearbetning.</span><span class="sxs-lookup"><span data-stu-id="135dd-144">This means that when the system processes a wave with more than 15 loads lines, it will use asynchronous task processing.</span></span> <span data-ttu-id="135dd-145">Du kan manuellt infoga/uppdatera dessa data i tabellen **WHSWaveTaskProcessingThresholdParameters** i testmiljöerna, men om du behöver ändra den här inställningen i en produktionsmiljö måste du kontakta Microsoft Support och begära uppdateringen.</span><span class="sxs-lookup"><span data-stu-id="135dd-145">You can manually insert/update this data in the **WHSWaveTaskProcessingThresholdParameters** table in your test environments, but if you need to change this setting in a production environment, you must contact Microsoft Support to request the update.</span></span>

## <a name="work-with-the-feature"></a><span data-ttu-id="135dd-146">Arbeta med funktionen</span><span class="sxs-lookup"><span data-stu-id="135dd-146">Work with the feature</span></span>

<span data-ttu-id="135dd-147">När funktionen *Schemalägga arbetsskapande* är aktiverad kommer påfyllnadsbehandling att skapa planerat arbete, som så småningom kommer att användas av den nya arbetsskapande processen.</span><span class="sxs-lookup"><span data-stu-id="135dd-147">When the *Schedule work creation* functionality is enabled, wave processing will create planned work, which will eventually be used by the new work creation process.</span></span> <span data-ttu-id="135dd-148">När arbetet skapas spärras arbetet med funktionen *Arbetsspärr för hela organisationen*.</span><span class="sxs-lookup"><span data-stu-id="135dd-148">During work creation, the work will be blocked using the *Organization-wide work blocking* feature.</span></span>

<span data-ttu-id="135dd-149">Flödesschemat nedan visar hur planerat arbete skapas under påfyllnadsbearbetning.</span><span class="sxs-lookup"><span data-stu-id="135dd-149">The following flowchart shows how planned work is created during wave processing.</span></span>

![Skapa tidsplan för arbete](media/schedule-work-creation-process.png)

### <a name="planned-work"></a><span data-ttu-id="135dd-151">Planerat arbete</span><span class="sxs-lookup"><span data-stu-id="135dd-151">Planned work</span></span>

<span data-ttu-id="135dd-152">Sidan **Information om planerat arbete** (**Lagerstyrning \> Arbete \> Information om planerat arbete**) visar information om det planerade arbetet som ursprungligen skapas under påfyllnadsbehandling.</span><span class="sxs-lookup"><span data-stu-id="135dd-152">The **Planned work details** page (**Warehouse management \> Work \> Planned work details**) shows information about the planned work, which is initially created during wave processing.</span></span> <span data-ttu-id="135dd-153">Följande värden för **Processtatus** finns:</span><span class="sxs-lookup"><span data-stu-id="135dd-153">The following **Process status** values are available:</span></span>

- <span data-ttu-id="135dd-154">**Köad** - Det planerade arbetet väntar på att användas för att skapa arbete.</span><span class="sxs-lookup"><span data-stu-id="135dd-154">**Queued** - The planned work is waiting to be used to create work.</span></span>
- <span data-ttu-id="135dd-155">**Slutfört** - Det planerade arbetet har använts för att skapa arbete.</span><span class="sxs-lookup"><span data-stu-id="135dd-155">**Completed** - The planned work has been used to create work.</span></span>
- <span data-ttu-id="135dd-156">**Misslyckat** - påfyllnadsbearbetningen har misslyckats.</span><span class="sxs-lookup"><span data-stu-id="135dd-156">**Failed** – The wave processing has failed.</span></span> <span data-ttu-id="135dd-157">Observera att det planerade arbetet kan vara i **misslyckat** läge med eller utan relaterat faktiskt arbete.</span><span class="sxs-lookup"><span data-stu-id="135dd-157">Note that the planned work can be in a **Failed** state with or without related actual work.</span></span> <span data-ttu-id="135dd-158">När den faktiska processen för att skapa arbete misslyckas, kvarstår det faktiska arbetet med status *Annullerat*.</span><span class="sxs-lookup"><span data-stu-id="135dd-158">When the actual work creation process fails, the actual work remains in status *Cancelled*.</span></span>

### <a name="batch-job-for-the-work-creation-process"></a><span data-ttu-id="135dd-159">Batchjobb för att skapa arbete</span><span class="sxs-lookup"><span data-stu-id="135dd-159">Batch job for the work creation process</span></span>

<span data-ttu-id="135dd-160">Om du vill visa batchjobben för påfyllnadsbearbetning, välj **batchjobb** i åtgärdsfönstret på sidan **Alla påfyllnader**.</span><span class="sxs-lookup"><span data-stu-id="135dd-160">To view the batch jobs for processing waves, select **Batch jobs** on the Action Pane on the **All waves** page.</span></span>

<span data-ttu-id="135dd-161">Här kan du visa alla batchuppgiftsdetaljer för varje batchjobb-ID.</span><span class="sxs-lookup"><span data-stu-id="135dd-161">From here, you can view all the batch task details for each of the batch job IDs.</span></span>
