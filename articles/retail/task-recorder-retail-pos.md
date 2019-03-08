---
title: Uppgiftsinspelare och hjälp för Retail Modern POS (MPOS) och molnbaserad kassa
description: Det här avsnittet beskriver hur du använder uppgiftsinspelaren i Retail Modern POS och molnbaserad kassa.
author: mugunthanm
manager: AnnBe
ms.date: 06/19/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailTerminalTable, SystemParameters
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 1205393
ms.assetid: 2f13e9cf-55b5-458b-8c32-3f8cd98c9ecf
ms.search.region: Global
ms.search.industry: Retail
ms.author: mumani
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: a74a1275f08e3dba60a1002a102e143eb37fcd9a
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2019
ms.locfileid: "346006"
---
# <a name="task-recorder-and-help-for-retail-modern-pos-mpos-and-cloud-pos"></a><span data-ttu-id="515c2-103">Uppgiftsinspelare och hjälp för Retail Modern POS (MPOS) och molnbaserad kassa</span><span class="sxs-lookup"><span data-stu-id="515c2-103">Task recorder and Help for Retail Modern POS (MPOS) and Cloud POS</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="515c2-104">Det här avsnittet beskriver hur du använder uppgiftsinspelaren i Retail Modern POS och molnbaserad kassa.</span><span class="sxs-lookup"><span data-stu-id="515c2-104">This topic describes how to use Task recorder in Retail Modern POS and Cloud POS.</span></span>

## <a name="overview"></a><span data-ttu-id="515c2-105">Översikt</span><span class="sxs-lookup"><span data-stu-id="515c2-105">Overview</span></span>

<span data-ttu-id="515c2-106">Uppgiftsinspelning i Retail Modern POS eller Cloud POS är en ny lösning som har skapats med fokus på hög tillgänglighet.</span><span class="sxs-lookup"><span data-stu-id="515c2-106">Task recorder in Retail Modern POS or Cloud POS is a new solution that was built with a focus on high responsiveness.</span></span> <span data-ttu-id="515c2-107">Det ger ett flexibelt gränssnitt för programprogrammering (API) för utökningsbarhet och sömlös integrering med företagsprocessinspelningar.</span><span class="sxs-lookup"><span data-stu-id="515c2-107">It provides a flexible application programming interface (API) for extensibility and seamless integration with consumers of business process recordings.</span></span> <span data-ttu-id="515c2-108">Dessutom har uppgiftsinspelarintegrering med affärsprocessmodellerarverktyget (BPM) i Microsoft Dynamics Lifecycle Services ([https://bpm.lcs.dynamics.com](https://bpm.lcs.dynamics.com/)) tillhandahållits.</span><span class="sxs-lookup"><span data-stu-id="515c2-108">Additionally, Task recorder integration with the Business process modeler (BPM) tool on Microsoft Dynamics Lifecycle Services ([https://bpm.lcs.dynamics.com](https://bpm.lcs.dynamics.com/)) has been brought forward.</span></span> <span data-ttu-id="515c2-109">Användare kan därför fortsätta framställa detaljerade affärsprocessdiagram från inspelningar i syfte att analysera och utforma sina program.</span><span class="sxs-lookup"><span data-stu-id="515c2-109">Therefore, users can continue to produce rich business process diagrams from recordings to analyze and design their applications.</span></span>

## <a name="architecture"></a><span data-ttu-id="515c2-110">Arkitektur</span><span class="sxs-lookup"><span data-stu-id="515c2-110">Architecture</span></span>

<span data-ttu-id="515c2-111">Uppgiftsinspelningen kan registrera användaråtgärder i klienten med exakt återgivning.</span><span class="sxs-lookup"><span data-stu-id="515c2-111">Task recorder can record user actions in the client with exact fidelity.</span></span> <span data-ttu-id="515c2-112">Varje kontroll har utrustats för att meddela utförandet av en användaråtgärd till uppgiftsinspelaren.</span><span class="sxs-lookup"><span data-stu-id="515c2-112">Each control is instrumented to notify Task recorder about the execution of a user action.</span></span> <span data-ttu-id="515c2-113">Kontrollen meddelar uppgiftsinspelaren att en händelse har inträffat och vidarebefordrar all relevant information om motsvarande användaråtgärd i realtid.</span><span class="sxs-lookup"><span data-stu-id="515c2-113">The control notifies Task recorder that an event occurred and passes along all pertinent information about the corresponding user action in real time.</span></span> <span data-ttu-id="515c2-114">Utifrån denna information kan uppgiftsinspelaren registrera typen av användaråtgärd (till exempel klick, värde eller navigering) och all information som är relaterad till användaråtgärden (t.ex. indata-värde och typ, formulärssammanhang eller postsammanhang).</span><span class="sxs-lookup"><span data-stu-id="515c2-114">From this information, Task recorder can capture the type of user action (such as a button click, value entry, or navigation) and any data that is related to the user action (such as the input data value and type, form context, or record context).</span></span> <span data-ttu-id="515c2-115">Uppgiftsinspelaren förser informationen med tillräckligt mycket detaljer för att garantera att en uppspelning av inspelningen kan utföra de inspelade åtgärderna precis så som användaren har utfört dem.</span><span class="sxs-lookup"><span data-stu-id="515c2-115">Task recorder persists the information with enough detail to help guarantee that a playback of the recording can perform the recorded actions exactly as the user performed them.</span></span> <span data-ttu-id="515c2-116">(Uppspelningsfunktionen har ännu inte implementerats i Retail modern POS eller Cloud POS.)</span><span class="sxs-lookup"><span data-stu-id="515c2-116">(The playback feature isn't yet implemented at Retail modern POS or Cloud POS.)</span></span>

## <a name="basic-configuration"></a><span data-ttu-id="515c2-117">Standardkonfiguration</span><span class="sxs-lookup"><span data-stu-id="515c2-117">Basic configuration</span></span>

<span data-ttu-id="515c2-118">Följ dessa steg om du vill aktivera uppgiftsinspelning för kassan.</span><span class="sxs-lookup"><span data-stu-id="515c2-118">To enable task recording in POS, follow these steps.</span></span>

1. <span data-ttu-id="515c2-119">Klicka på **Butik** &gt; **Kanalinställningar** &gt; **Kassainställning** &gt; **Kassaapparater**.</span><span class="sxs-lookup"><span data-stu-id="515c2-119">Click **Retail** &gt; **Channel Setup** &gt; **POS Setup** &gt; **Registers**.</span></span>
2. <span data-ttu-id="515c2-120">Klicka på registret för att aktivera uppgiftsinspelningen.</span><span class="sxs-lookup"><span data-stu-id="515c2-120">Click the register to enable task recording on.</span></span>
3. <span data-ttu-id="515c2-121">På fliken **Registrera** på snabbfliken **Allmänt**, ange alternativet **"Aktivera uppgiftsinspelning** som **Ja**.</span><span class="sxs-lookup"><span data-stu-id="515c2-121">On the **Register** tab, on the **General** FastTab, set the **Enable task recording** option to **Yes**.</span></span>
4. <span data-ttu-id="515c2-122">Klicka på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="515c2-122">Click **Save**.</span></span>
5. <span data-ttu-id="515c2-123">Gå till **Butik** &gt; **Butik-IT** &gt; **Distributionsschema**.</span><span class="sxs-lookup"><span data-stu-id="515c2-123">Go to **Retail** &gt; **Retail IT** &gt; **Distribution schedule**.</span></span>
6. <span data-ttu-id="515c2-124">Markera jobbet **Register (1090)** och klicka sedan på **Kör nu**.</span><span class="sxs-lookup"><span data-stu-id="515c2-124">Select the **Registers (1090)** job, and then click **Run now**.</span></span>

## <a name="create-a-recording"></a><span data-ttu-id="515c2-125">Skapa en inspelning</span><span class="sxs-lookup"><span data-stu-id="515c2-125">Create a recording</span></span>

<span data-ttu-id="515c2-126">Följ dessa steg för att skapa en ny inspelning med hjälp av uppgiftsinspelaren.</span><span class="sxs-lookup"><span data-stu-id="515c2-126">Follow these steps to create a new recording using Task recorder.</span></span>

1. <span data-ttu-id="515c2-127">Starta Retail Modern POS eller Cloud POS och logga in.</span><span class="sxs-lookup"><span data-stu-id="515c2-127">Start Retail Modern POS or Cloud POS, and sign in.</span></span>
2. <span data-ttu-id="515c2-128">På sidan **Inställningar**, i avsnittet **Uppgiftsinspelare** klickar du på **Öppna uppgiftsinspelaren**.</span><span class="sxs-lookup"><span data-stu-id="515c2-128">On the **Settings** page, in the **Task Recorder** section, click **Open task recorder**.</span></span> <span data-ttu-id="515c2-129">Sidan **Uppgiftsinspelare** visas.</span><span class="sxs-lookup"><span data-stu-id="515c2-129">The **Task recorder** pane appears.</span></span> <span data-ttu-id="515c2-130">Du kan klicka på knappen **Stäng** (**X**) i det övre högra hörnet för att stänga fönstret **Uppgiftsinspelare** innan du påbörjar en ny inspelning.</span><span class="sxs-lookup"><span data-stu-id="515c2-130">You can click the **Close** button (**X**) in the upper-right corner to close the **Task recorder** pane before you begin a new recording.</span></span> <span data-ttu-id="515c2-131">Upprepa steg 2 för att öppna fönstret.</span><span class="sxs-lookup"><span data-stu-id="515c2-131">To reopen the pane, repeat step 2.</span></span>

    <span data-ttu-id="515c2-132">[![Fönstret Uppgiftsinspelare](./media/newrecording-1024x450.jpg)](./media/newrecording.jpg)</span><span class="sxs-lookup"><span data-stu-id="515c2-132">[![Task recorder pane](./media/newrecording-1024x450.jpg)](./media/newrecording.jpg)</span></span>

3. <span data-ttu-id="515c2-133">Ange ett namn och en beskrivning för inspelningen och klicka sedan på **Starta**.</span><span class="sxs-lookup"><span data-stu-id="515c2-133">Enter a name and description for the recording, and then click **Start**.</span></span> <span data-ttu-id="515c2-134">Inspelningssessionen börjar så fort du klickar på **Starta**.</span><span class="sxs-lookup"><span data-stu-id="515c2-134">The recording session begins as soon as you click **Start**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="515c2-135">Om du klickar på knappen **Stäng** (**X**) det övre högra hörnet när inspelningen pågår, stängs fönstret **Uppgiftsinspelare** men inspelningssessionen avslutas inte.</span><span class="sxs-lookup"><span data-stu-id="515c2-135">If you click the **Close** button (**X**) in the upper-right corner while recording is in progress, the **Task recorder** pane is closed, but the recording session isn't ended.</span></span> <span data-ttu-id="515c2-136">Om du vill öppna fönstret Uppgiftsinspelare, klicka då på knappen **Hjälp** (frågetecken) överst på skärmen.</span><span class="sxs-lookup"><span data-stu-id="515c2-136">To reopen the Task recorder pane, click the **Help** button (question mark) at the top of the screen.</span></span>
    >
    > <span data-ttu-id="515c2-137">[![Frågetecken](./media/help.jpg)](./media/help.jpg)</span><span class="sxs-lookup"><span data-stu-id="515c2-137">[![Question mark](./media/help.jpg)](./media/help.jpg)</span></span>

4. <span data-ttu-id="515c2-138">När du klickar på **Starta** växlar Uppgiftsinspelaren till inspelningsläget.</span><span class="sxs-lookup"><span data-stu-id="515c2-138">After you click **Start**, Task recorder enters recording mode.</span></span> <span data-ttu-id="515c2-139">Fönstret **Uppgiftsinspelare** visar information och kontroller som är relaterade till inspelningsprocessen.</span><span class="sxs-lookup"><span data-stu-id="515c2-139">The **Task recorder** pane shows information and controls that are related to the recording process.</span></span>
5. <span data-ttu-id="515c2-140">Utför de åtgärder som du vill utföra i Retail Modern POS- eller Cloud POS-användargränssnittet (UI).</span><span class="sxs-lookup"><span data-stu-id="515c2-140">Perform the actions that you want to perform in the Retail Modern POS or Cloud POS user interface (UI).</span></span>
6. <span data-ttu-id="515c2-141">Klicka på **Stopp** för att avsluta inspelningssessionen.</span><span class="sxs-lookup"><span data-stu-id="515c2-141">To end the recording session, click **Stop**.</span></span>

## <a name="download-options"></a><span data-ttu-id="515c2-142">Hämtningsalternativ</span><span class="sxs-lookup"><span data-stu-id="515c2-142">Download options</span></span>

<span data-ttu-id="515c2-143">När du avslutar inspelningssessionen visas ett flertal alternativ som gör att du kan hämta din inspelning.</span><span class="sxs-lookup"><span data-stu-id="515c2-143">After you end the recording session, several options are shown, so that you can download your recording.</span></span>

<span data-ttu-id="515c2-144">[![Hämtningsalternativ](./media/downlaod-options.jpg)](./media/downlaod-options.jpg)</span><span class="sxs-lookup"><span data-stu-id="515c2-144">[![Download options](./media/downlaod-options.jpg)](./media/downlaod-options.jpg)</span></span>

### <a name="save-to-this-pc"></a><span data-ttu-id="515c2-145">Spara på datorn</span><span class="sxs-lookup"><span data-stu-id="515c2-145">Save to this PC</span></span>

<span data-ttu-id="515c2-146">Du kan använda inspelningspaketet för att spela upp en uppgiftsguide, bibehålla inspelningen eller redigera kommentarerna i inspelningen.</span><span class="sxs-lookup"><span data-stu-id="515c2-146">You can use the recording package to play a Task guide, maintain the recording, or edit the annotations in the recording.</span></span> <span data-ttu-id="515c2-147">(Denna funktion har ännu inte implementerats i Retail Modern POS eller Cloud POS.)</span><span class="sxs-lookup"><span data-stu-id="515c2-147">(This feature isn't yet implemented in Retail Modern POS and Cloud POS.)</span></span>

### <a name="export-as-word-document"></a><span data-ttu-id="515c2-148">Exportera som Word-dokument</span><span class="sxs-lookup"><span data-stu-id="515c2-148">Export as Word document</span></span>

<span data-ttu-id="515c2-149">Du kan spara inspelningen som ett Microsoft Word-dokument.</span><span class="sxs-lookup"><span data-stu-id="515c2-149">You can save the recording as a Microsoft Word document.</span></span> <span data-ttu-id="515c2-150">Dokumentet innehåller inspelade steg och de skärmdumpar som har registrerats.</span><span class="sxs-lookup"><span data-stu-id="515c2-150">The document will contain the recorded steps and the screenshots that were captured.</span></span>

### <a name="save-as-developer-recording"></a><span data-ttu-id="515c2-151">Spara som utvecklingsregistrering</span><span class="sxs-lookup"><span data-stu-id="515c2-151">Save as developer recording</span></span>

<span data-ttu-id="515c2-152">Inspelningens råformatfil kommer att vara till stor nytta för utvecklingsscenarier som exempelvis generering av testkoder.</span><span class="sxs-lookup"><span data-stu-id="515c2-152">The raw recording file will be useful for developer scenarios such as test code generation.</span></span> <span data-ttu-id="515c2-153">(Den här funktionen är inte implementerad ännu.)</span><span class="sxs-lookup"><span data-stu-id="515c2-153">(This feature isn't yet implemented.)</span></span>

## <a name="recording-controls"></a><span data-ttu-id="515c2-154">Inspelningskontroller</span><span class="sxs-lookup"><span data-stu-id="515c2-154">Recording controls</span></span>

<span data-ttu-id="515c2-155">[![Inspelningskontroller](./media/controls.jpg)](./media/controls.jpg)</span><span class="sxs-lookup"><span data-stu-id="515c2-155">[![Recording controls](./media/controls.jpg)](./media/controls.jpg)</span></span>

### <a name="stop"></a><span data-ttu-id="515c2-156">Stopp</span><span class="sxs-lookup"><span data-stu-id="515c2-156">Stop</span></span>

<span data-ttu-id="515c2-157">Klicka på **Stopp** för att avsluta inspelningssessionen.</span><span class="sxs-lookup"><span data-stu-id="515c2-157">Click **Stop** to end the recording session.</span></span> <span data-ttu-id="515c2-158">Observera att du inte kan starta om en session när du avslutar den.</span><span class="sxs-lookup"><span data-stu-id="515c2-158">Note that you can't restart a session after you end it.</span></span> <span data-ttu-id="515c2-159">Se därför till att inspelningen har slutförts innan du avslutar den.</span><span class="sxs-lookup"><span data-stu-id="515c2-159">Therefore, make sure that the recording is completed before you end it.</span></span>

### <a name="pause"></a><span data-ttu-id="515c2-160">Pausa </span><span class="sxs-lookup"><span data-stu-id="515c2-160">Pause</span></span>

<span data-ttu-id="515c2-161">Klicka på **Pausa** för att tillfälligt stoppa (pausa) inspelningssessionen och fortsätta med processen.</span><span class="sxs-lookup"><span data-stu-id="515c2-161">Click **Pause** to temporarily stop (pause) the recording session and continue with the operation.</span></span> <span data-ttu-id="515c2-162">Steg som du utför efter det att du klickar på **Pausa** spelas inte in.</span><span class="sxs-lookup"><span data-stu-id="515c2-162">Steps that you perform after you click **Pause** aren't recorded.</span></span>

### <a name="continue"></a><span data-ttu-id="515c2-163">Fortsätt</span><span class="sxs-lookup"><span data-stu-id="515c2-163">Continue</span></span>

<span data-ttu-id="515c2-164">Klicka på **Fortsätt** om du vill återuppta inspelningssessionen när du har gjort paus.</span><span class="sxs-lookup"><span data-stu-id="515c2-164">To resume the recording session after you've paused it, click **Continue**.</span></span>

### <a name="capture-screenshots"></a><span data-ttu-id="515c2-165">Ta skärmbilder</span><span class="sxs-lookup"><span data-stu-id="515c2-165">Capture screenshots</span></span>

<span data-ttu-id="515c2-166">Uppgiftsinspelaren kan läsa in skärmdumpar på Retail Modern POS-användargränssnittet när du spelar in en affärsprocess.</span><span class="sxs-lookup"><span data-stu-id="515c2-166">Task recorder can capture screenshots of the Retail Modern POS UI as you record a business process.</span></span> <span data-ttu-id="515c2-167">Aktivera inspelningsfunktionen för skärmbild genom att ange alternativet **Fånga skärmbild** på **Ja** och registrera den.</span><span class="sxs-lookup"><span data-stu-id="515c2-167">To turn on the screenshot capture feature, set the **Capture screenshot** option to **Yes** and then make the recording.</span></span> <span data-ttu-id="515c2-168">När registreringen är klar klickar du på **Stopp** och hämta Word-dokumentet.</span><span class="sxs-lookup"><span data-stu-id="515c2-168">Once the recording is completed, click **Stop** and download the Word document.</span></span> <span data-ttu-id="515c2-169">Dokumentet innehåller steg med relevanta skärmdumpar.</span><span class="sxs-lookup"><span data-stu-id="515c2-169">The document will contain the steps with relevant screenshots.</span></span>

> [!NOTE]
> <span data-ttu-id="515c2-170">Funktionen för att fånga skärmbild stöds inte i Cloud POS.</span><span class="sxs-lookup"><span data-stu-id="515c2-170">Capture screenshot functionality is not supported in Cloud POS.</span></span>

### <a name="start-task-and-end-task"></a><span data-ttu-id="515c2-171">Startuppgift och slutuppgift</span><span class="sxs-lookup"><span data-stu-id="515c2-171">Start task and End task</span></span>

<span data-ttu-id="515c2-172">Du kan ange början och slut för en uppsättning grupperade steg via knapparna **Starta uppgift** och **Avsluta** **uppgift**.</span><span class="sxs-lookup"><span data-stu-id="515c2-172">You can specify the beginning and end of a set of grouped steps by using the **Start task** and **End** **task** buttons.</span></span> <span data-ttu-id="515c2-173">Klicka på **Starta uppgift** för att lägga till steget "Starta uppgift" och utföra de steg som ska tas med i gruppen.</span><span class="sxs-lookup"><span data-stu-id="515c2-173">Click **Start task** to add a "Start Task" step, and then perform the steps that should be included in the group.</span></span> <span data-ttu-id="515c2-174">När du har utfört stegen för gruppen klickar du på **Avsluta uppgift**.</span><span class="sxs-lookup"><span data-stu-id="515c2-174">After you've finished performing the steps for the group, click **End task**.</span></span> <span data-ttu-id="515c2-175">Uppgifter hjälper dig att ordna dina procedurer.</span><span class="sxs-lookup"><span data-stu-id="515c2-175">Tasks help you organize your procedures.</span></span> <span data-ttu-id="515c2-176">Uppgifter kan kapslas in i andra uppgifter.</span><span class="sxs-lookup"><span data-stu-id="515c2-176">Tasks can be nested within other tasks.</span></span> <span data-ttu-id="515c2-177">På så sätt blir det enklare att organisera mycket långa och komplicerade affärsprocesser.</span><span class="sxs-lookup"><span data-stu-id="515c2-177">In this way, you can better organize very long and complex business processes.</span></span>

## <a name="adding-annotations"></a><span data-ttu-id="515c2-178">Lägga till anteckningar</span><span class="sxs-lookup"><span data-stu-id="515c2-178">Adding annotations</span></span>

<span data-ttu-id="515c2-179">En anteckning är ytterligare text som du lägger till i ett steg i en inspelning.</span><span class="sxs-lookup"><span data-stu-id="515c2-179">An annotation is additional text that you add to a step in a recording.</span></span> <span data-ttu-id="515c2-180">Du kan exempelvis använda anteckningar för att ge användaren mer kontext eller instruktioner.</span><span class="sxs-lookup"><span data-stu-id="515c2-180">For example, you can use annotations to give the user more context or instructions.</span></span> <span data-ttu-id="515c2-181">Du kan lägga till anteckningar före eller efter ett steg.</span><span class="sxs-lookup"><span data-stu-id="515c2-181">You can add annotations before or after a step.</span></span> <span data-ttu-id="515c2-182">Du kan lägga till en anteckning till ett steg genom att klicka på knappen **Redigera** (pennsymbol) till höger om steget.</span><span class="sxs-lookup"><span data-stu-id="515c2-182">You can add an annotation to any step by clicking the **Edit** button (pencil symbol) to the right of the step.</span></span>

<span data-ttu-id="515c2-183">[![Redigeringsknapp för ett steg](./media/annotate.jpg)](./media/annotate.jpg)</span><span class="sxs-lookup"><span data-stu-id="515c2-183">[![Edit button for a step](./media/annotate.jpg)](./media/annotate.jpg)</span></span>

### <a name="texts-and-notes"></a><span data-ttu-id="515c2-184">Texter och anteckningar</span><span class="sxs-lookup"><span data-stu-id="515c2-184">Texts and notes</span></span>

<span data-ttu-id="515c2-185">Du kan använda fälten **Texter** och **Anteckningar** om du vill lägga till text som ska associeras med ett steg i en uppgiftsguide.</span><span class="sxs-lookup"><span data-stu-id="515c2-185">You can use the **Texts** and **Notes** fields to add text that should be associated with a step in a Task guide.</span></span>

<span data-ttu-id="515c2-186">[![Text- och anteckningsfält](./media/annotatesteps.jpg)](./media/annotatesteps.jpg)</span><span class="sxs-lookup"><span data-stu-id="515c2-186">[![Text and Notes fields](./media/annotatesteps.jpg)](./media/annotatesteps.jpg)</span></span>

#### <a name="text"></a><span data-ttu-id="515c2-187">Text</span><span class="sxs-lookup"><span data-stu-id="515c2-187">Text</span></span>

<span data-ttu-id="515c2-188">Text som du anger i fältet **Text** visas *ovanför* stegtexten i uppgiftsguiden.</span><span class="sxs-lookup"><span data-stu-id="515c2-188">Text that you enter in the **Text** field appears *above* the step text in the Task guide.</span></span> <span data-ttu-id="515c2-189">Den här platsen är lämplig för den text som du vill att användaren ska läsa innan han eller hon slutför ett steg.</span><span class="sxs-lookup"><span data-stu-id="515c2-189">This location is appropriate for text that you want the user to read before he or she completes the step.</span></span>

#### <a name="notes"></a><span data-ttu-id="515c2-190">Anteckningar</span><span class="sxs-lookup"><span data-stu-id="515c2-190">Notes</span></span>

<span data-ttu-id="515c2-191">Text som du anger i fältet **Anteckningar** visas *under* stegtexten i uppgiftsguiden.</span><span class="sxs-lookup"><span data-stu-id="515c2-191">Text that you enter in the **Notes** field appears *below* the step text in the Task guide.</span></span> <span data-ttu-id="515c2-192">Användaren måste expandera stegtexten i popup-fönstret för att läsa anteckningen.</span><span class="sxs-lookup"><span data-stu-id="515c2-192">To read the note text, the user must expand the step text in the pop-up window.</span></span> <span data-ttu-id="515c2-193">Den här platsen passar valfritt läsmaterial eller annan information som kan vara användbart för användaren, men som användaren inte behöver för att slutföra åtgärden.</span><span class="sxs-lookup"><span data-stu-id="515c2-193">This location is appropriate for optional reading material or other information that might be useful to the user, but that the user doesn't require in order to complete the action.</span></span>

## <a name="help-in-retail-modern-pos-and-cloud-pos"></a><span data-ttu-id="515c2-194">Hjälp i Retail Modern POS och Cloud POS</span><span class="sxs-lookup"><span data-stu-id="515c2-194">Help in Retail Modern POS and Cloud POS</span></span>

<span data-ttu-id="515c2-195">Om du vill visa dina egna anpassade uppgiftsinspelningar i hjälpfönstret för Retail Modern POS och Cloud POS så att de kan spelas upp text, så måste du spara dina uppgiftsinspelningar i ditt eget BPM-bibliotek och sedan uppdatera hjälpsystemparametrarna så att de pekar på ditt BPM-bibliotek.</span><span class="sxs-lookup"><span data-stu-id="515c2-195">To show your own custom task recordings in the Help pane of Retail Modern POS and Cloud POS so that they can be viewed as text, you must save your task recordings to your own BPM library, and then update your Help system parameters to point to your BPM library.</span></span> <span data-ttu-id="515c2-196">Mer information finns i [Ansluta hjälpsystemet](../fin-and-ops/get-started/help-connect.md).</span><span class="sxs-lookup"><span data-stu-id="515c2-196">For more information, see [Connecting the Help system](../fin-and-ops/get-started/help-connect.md).</span></span> <span data-ttu-id="515c2-197">Retail Modern POS och Cloud POS Help söker LCS i realtid.</span><span class="sxs-lookup"><span data-stu-id="515c2-197">Retail Modern POS and Cloud POS Help searches LCS in real time.</span></span> <span data-ttu-id="515c2-198">Det söker igenom alla BPM-bibliotek som valts i systemparametrarna för Microsoft Dynamics 365 for Retail Help och visar relevanta resultat.</span><span class="sxs-lookup"><span data-stu-id="515c2-198">It searches across all the BPM libraries that are selected in the Microsoft Dynamics 365 for Retail Help system parameters and shows the relevant results.</span></span> <span data-ttu-id="515c2-199">För att få åtkomst till menyn **Hjälp** klickar du på knappen **Hjälp** (frågetecken) högst upp på skärmen. Ange sedan ditt processnamn i sökrutan och tryck på sökknappen.</span><span class="sxs-lookup"><span data-stu-id="515c2-199">To access the **Help** menu, click the **Help** button (question mark) at the top of the screen and then in the search box type your process name and hit the search button.</span></span>

<span data-ttu-id="515c2-200">[![Knappen Hjälp](./media/help.jpg)](./media/help.jpg)</span><span class="sxs-lookup"><span data-stu-id="515c2-200">[![Help button](./media/help.jpg)](./media/help.jpg)</span></span>

<span data-ttu-id="515c2-201">När du klickar på en uppgiftsguide i sökresultaten kan du antingen se stegen som ett hjälpavsnitt eller exportera stegen till ett Word-dokument.</span><span class="sxs-lookup"><span data-stu-id="515c2-201">When you click a Task guide in the search results, you can either view the steps as a Help topic or export the steps to a Word document.</span></span>

> [!NOTE]
> <span data-ttu-id="515c2-202">Hjälp i Retail Modern POS och Cloud POS visar inte aktivitetsguiderna i enlighet med det formulär du använder eller den åtgärd du utför.</span><span class="sxs-lookup"><span data-stu-id="515c2-202">Help in Retail Modern POS and Cloud POS will not bring up task guides according to what form you're on or operation you're doing.</span></span> <span data-ttu-id="515c2-203">Skriv in processnamnet i sökrutan och klicka på **Sök**.</span><span class="sxs-lookup"><span data-stu-id="515c2-203">You have to type the process name in the search box and then click **Search**.</span></span>
