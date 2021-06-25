---
title: Felsöka prestandaproblem i ER-konfigurationer
description: I det här avsnittet beskrivs hur du hittar och åtgärdar prestandaproblem i ER-konfigurationer (elektronisk rapportering).
author: NickSelin
ms.date: 06/08/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERModelMappingDesigner, EROperationDesigner, ERFormatMappingRunJobTable, ERParameters, ERSolutionTable
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: 220314
ms.assetid: ''
ms.search.region: Global
ms.author: maximbel
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.1
ms.openlocfilehash: d77c2aad904ba911ac19009d6a981ea4153aaa48
ms.sourcegitcommit: 60afcd85b3b5b9e5e8981ebbb57c0161cf05e54b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/09/2021
ms.locfileid: "6216875"
---
# <a name="troubleshooting-performance-issues-in-er-configurations"></a><span data-ttu-id="d65b9-103">Felsöka prestandaproblem i ER-konfigurationer</span><span class="sxs-lookup"><span data-stu-id="d65b9-103">Troubleshooting performance issues in ER configurations</span></span>

<span data-ttu-id="d65b9-104">I det här avsnittet beskrivs hur du hittar och löser prestandaproblem i [ER](general-electronic-reporting.md)-[konfigurationer (ER)](general-electronic-reporting.md#Configuration).</span><span class="sxs-lookup"><span data-stu-id="d65b9-104">This topic explains how to find and solve performance issues in [Electronic reporting](general-electronic-reporting.md) (ER) [configurations](general-electronic-reporting.md#Configuration).</span></span>

<span data-ttu-id="d65b9-105">Vanligtvis består prestandaundersökningen av flera steg.</span><span class="sxs-lookup"><span data-stu-id="d65b9-105">Typically, performance investigation consists of several steps.</span></span>

1. <span data-ttu-id="d65b9-106">[Samla in](#collecting-data) data.</span><span class="sxs-lookup"><span data-stu-id="d65b9-106">[Collect](#collecting-data) data.</span></span>
2. <span data-ttu-id="d65b9-107">Analysera insamlade data.</span><span class="sxs-lookup"><span data-stu-id="d65b9-107">Analyze the collected data.</span></span>
3. <span data-ttu-id="d65b9-108">Baserat på resultaten av analysen använder du ER-konfigurationer för att [göra ändringar](#making-changes) eller bestämmer dig för att samla in mer data.</span><span class="sxs-lookup"><span data-stu-id="d65b9-108">Based on the results of the analysis, use ER configurations to [make changes](#making-changes), or decide to collect more data.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="d65b9-109">Felsökning</span><span class="sxs-lookup"><span data-stu-id="d65b9-109">Troubleshooting</span></span>

### <a name="analyze-execution-time"></a><span data-ttu-id="d65b9-110">Analysera körningstid</span><span class="sxs-lookup"><span data-stu-id="d65b9-110">Analyze execution time</span></span>

<span data-ttu-id="d65b9-111">Körningstiden kan bero på oförutsägbara faktorer, till exempel andra aktiviteter som körs i samma miljö och cachelagring som använder data när de anropas för första gången.</span><span class="sxs-lookup"><span data-stu-id="d65b9-111">Execution time can depend on unpredictable factors, such as other tasks that are running in the same environment and caching that uses data when it's called for the first time.</span></span> <span data-ttu-id="d65b9-112">Därför bör du upprepa körningen och mätningen flera gånger.</span><span class="sxs-lookup"><span data-stu-id="d65b9-112">Therefore, you should repeat the execution and measurement several times.</span></span>

<span data-ttu-id="d65b9-113">Ibland orsakas prestandaproblem inte av en ER-formatkonfiguration som används för rapportering.</span><span class="sxs-lookup"><span data-stu-id="d65b9-113">Sometimes, performance issues aren't caused by an ER format configuration that is used for reporting.</span></span> <span data-ttu-id="d65b9-114">Istället orsakas de av X++ -koden som används för att öppna ER-formatkonfigurationen.</span><span class="sxs-lookup"><span data-stu-id="d65b9-114">Instead, they are caused by the X++ code that is used to open that ER format configuration.</span></span>

1. <span data-ttu-id="d65b9-115">I antingen [Åtgärdscentret](#infolog-time) eller [händelseloggen](#event-log-time) tittar du på rapportens körningstid.</span><span class="sxs-lookup"><span data-stu-id="d65b9-115">In either the [Action center](#infolog-time) or the [event log](#event-log-time), look at the execution time of the report.</span></span>
2. <span data-ttu-id="d65b9-116">Jämför körningstiden för rapporten med den totala körningstiden i scenariot.</span><span class="sxs-lookup"><span data-stu-id="d65b9-116">Compare the execution time of the report with the total execution time in the scenario.</span></span>
3. <span data-ttu-id="d65b9-117">Om körningstiden för rapporten är mycket kortare än den totala körningstiden bör du tänka på hur mycket data rapporten bearbetar:</span><span class="sxs-lookup"><span data-stu-id="d65b9-117">If the execution time of the report is much less than the total execution time, consider the amount of data that the report processes:</span></span>

    - <span data-ttu-id="d65b9-118">Om rapporten bearbetar en liten mängd data kan problemet inbegripa inläsningstiden för konfigurationen.</span><span class="sxs-lookup"><span data-stu-id="d65b9-118">If the report processes a small amount of data, the issue might involve the loading time of the configuration.</span></span>
    - <span data-ttu-id="d65b9-119">Om rapporten bearbetar en stor mängd data kan problemet inbegripa förbearbetning av X++.</span><span class="sxs-lookup"><span data-stu-id="d65b9-119">If the report processes a large amount of data, the issue might involve preprocessing X++.</span></span> <span data-ttu-id="d65b9-120">Använd [Trace parser](#analyze-trace-parser-trace) för att analysera det här fallet.</span><span class="sxs-lookup"><span data-stu-id="d65b9-120">Use [Trace parser](#analyze-trace-parser-trace) to analyze this case.</span></span>

    <span data-ttu-id="d65b9-121">I andra fall, se nästa avsnitt.</span><span class="sxs-lookup"><span data-stu-id="d65b9-121">For other cases, see the next sections.</span></span>

4. <span data-ttu-id="d65b9-122">Kör flera tester som involverar olika mängder data för att avgöra hur körningstiden beror på mängden data.</span><span class="sxs-lookup"><span data-stu-id="d65b9-122">Run multiple tests that involve different amounts of data to determine how the execution time depends on the amount of data.</span></span>

### <a name="analyze-trace-parser-traces"></a><a name="analyze-trace-parser-trace"></a><span data-ttu-id="d65b9-123">Analysera Trace parser-spår</span><span class="sxs-lookup"><span data-stu-id="d65b9-123">Analyze Trace parser traces</span></span>

<span data-ttu-id="d65b9-124">Förbered ett mindre exempel eller samla in flera spår under slumpmässiga delar av rapportgenereringen.</span><span class="sxs-lookup"><span data-stu-id="d65b9-124">Prepare a small example, or collect several traces during random parts of the report generation.</span></span>

<span data-ttu-id="d65b9-125">I [Trace parser](#trace-parser) gör du sedan en standardanalys nedifrån och upp och besvarar följande frågor:</span><span class="sxs-lookup"><span data-stu-id="d65b9-125">Then, in [Trace parser](#trace-parser), do a standard bottom-to-up analysis, and answer the following questions:</span></span>

- <span data-ttu-id="d65b9-126">Vilka är de bästa metoderna när det gäller tidsförbrukning?</span><span class="sxs-lookup"><span data-stu-id="d65b9-126">What are the top methods in terms of time consumption?</span></span>
- <span data-ttu-id="d65b9-127">Vilken del av den totala tiden använder dessa metoder?</span><span class="sxs-lookup"><span data-stu-id="d65b9-127">What part of the overall time do those methods use?</span></span>

<span data-ttu-id="d65b9-128">Besvara samma frågor för frågor.</span><span class="sxs-lookup"><span data-stu-id="d65b9-128">Answer the same questions for queries.</span></span>

<span data-ttu-id="d65b9-129">Om du ser att metoderna föregås av "ER" går du vidare till nästa avsnitt.</span><span class="sxs-lookup"><span data-stu-id="d65b9-129">If you see that methods are prefixed with "ER," move on to the next section.</span></span>

<span data-ttu-id="d65b9-130">Om du ser att metoder eller frågor har sitt ursprung i programsviten bör du överväga allmänna optimeringar (till exempel skapa index).</span><span class="sxs-lookup"><span data-stu-id="d65b9-130">If you see that methods or queries originated in the application suite, consider generic optimizations (for example, create indexes).</span></span>

<span data-ttu-id="d65b9-131">Analysera antalet anrop.</span><span class="sxs-lookup"><span data-stu-id="d65b9-131">Analyze the number of calls.</span></span> <span data-ttu-id="d65b9-132">Om antalet är betydligt högre än förväntat bör du överväga att cachelagra motsvarande noder i konfigurationen.</span><span class="sxs-lookup"><span data-stu-id="d65b9-132">If the number is significantly higher than expected, consider caching the corresponding nodes of the configuration.</span></span>

### <a name="analyze-database-calls"></a><a name="analyze-database-calls"></a><span data-ttu-id="d65b9-133">Analysera databasanrop</span><span class="sxs-lookup"><span data-stu-id="d65b9-133">Analyze database calls</span></span>

<span data-ttu-id="d65b9-134">Förbered ett exempel som har en liten mängd data, så att du kan samla in en [ER-spårning](#electronic-reporting-traces).</span><span class="sxs-lookup"><span data-stu-id="d65b9-134">Prepare an example that has a small amount of data, so that you can collect an [ER trace](#electronic-reporting-traces).</span></span>

<span data-ttu-id="d65b9-135">Öppna sedan spårningen i ER-modellmappningsdesignern och titta längst ned på sidan.</span><span class="sxs-lookup"><span data-stu-id="d65b9-135">Then open the trace in the ER model mapping designer, and look at the bottom of the page.</span></span> <span data-ttu-id="d65b9-136">Besvara följande frågor:</span><span class="sxs-lookup"><span data-stu-id="d65b9-136">Answer the following questions:</span></span>

- <span data-ttu-id="d65b9-137">Finns det några frågedubbletter?</span><span class="sxs-lookup"><span data-stu-id="d65b9-137">Is there any query duplication?</span></span> <span data-ttu-id="d65b9-138">Om så är fallet, överväg någon av följande korrigeringar:</span><span class="sxs-lookup"><span data-stu-id="d65b9-138">If there is, consider one of the following fixes:</span></span>

    - <span data-ttu-id="d65b9-139">[Använd cachelagring](#use-caching) om du tror att det finns flera anrop i en enda överordnad post.</span><span class="sxs-lookup"><span data-stu-id="d65b9-139">[Use caching](#use-caching) if you think that there are several calls inside one parent record.</span></span>
    - <span data-ttu-id="d65b9-140">[Använd ett cachelagrat, parametriserat beräknat fält](#cached-parameterized) om du tror att det finns anrop till samma post i olika poster.</span><span class="sxs-lookup"><span data-stu-id="d65b9-140">[Use a cached, parameterized calculated field](#cached-parameterized) if you think that there are calls to the same record inside different records.</span></span>
    - <span data-ttu-id="d65b9-141">[Använd en **KOPPLA**-datakälla](#use-join-datasource) om du måste läsa till ett stort antal olika poster från en databas.</span><span class="sxs-lookup"><span data-stu-id="d65b9-141">[Use a **JOIN** data source](#use-join-datasource) if you have to read to a substantial number of different records from a database.</span></span>

- <span data-ttu-id="d65b9-142">Motsvarar antalet frågor och hämtade poster den totala mängden data?</span><span class="sxs-lookup"><span data-stu-id="d65b9-142">Does the number of queries and fetched records correspond to the overall amount of data?</span></span> <span data-ttu-id="d65b9-143">Om ett dokument till exempel har 10 rader, visar då statistiken att rapporten extraherar 10 rader eller 1 000 rader?</span><span class="sxs-lookup"><span data-stu-id="d65b9-143">For example, if a document has 10 lines, do the statistics show that the report extracts 10 lines or 1,000 lines?</span></span> <span data-ttu-id="d65b9-144">Om du har ett stort antal hämtade poster bör du överväga någon av följande korrigeringar:</span><span class="sxs-lookup"><span data-stu-id="d65b9-144">If you have a substantial number of fetched records, consider one of the following fixes:</span></span>

    - <span data-ttu-id="d65b9-145">[Använd funktionern **FILTER** istället för funktionen **VAR**](#filter) för att bearbeta data på SQL Server-sidan.</span><span class="sxs-lookup"><span data-stu-id="d65b9-145">[Use the **FILTER** function instead of the **WHERE** function](#filter) to process data on the SQL Server side.</span></span>
    - <span data-ttu-id="d65b9-146">Använd cachelagring för att undvika att hämta samma data.</span><span class="sxs-lookup"><span data-stu-id="d65b9-146">Use caching to avoid fetching the same data.</span></span>
    - <span data-ttu-id="d65b9-147">[Använd insamlade datafunktioner](#collected-data) för att undvika att hämta samma data för summering.</span><span class="sxs-lookup"><span data-stu-id="d65b9-147">[Use collected data functions](#collected-data) to avoid fetching the same data for summarization.</span></span>

### <a name="analyze-perfview-traces"></a><span data-ttu-id="d65b9-148">Analysera PerfView-spår</span><span class="sxs-lookup"><span data-stu-id="d65b9-148">Analyze PerfView traces</span></span>

<span data-ttu-id="d65b9-149">[PerfView](#perfview) är ett verktyg för erfarna utvecklare.</span><span class="sxs-lookup"><span data-stu-id="d65b9-149">[PerfView](#perfview) is a tool for experienced developers.</span></span> <span data-ttu-id="d65b9-150">Mer detaljerad information om följande steg finns i [Utredningsgrunder för processtid](https://channel9.msdn.com/Series/PerfView-Tutorial/Tutorial-12-Wall-Clock-Time-Investigation-Basics).</span><span class="sxs-lookup"><span data-stu-id="d65b9-150">For more detailed information about the following steps, see [Wall Clock Time Investigation Basics](https://channel9.msdn.com/Series/PerfView-Tutorial/Tutorial-12-Wall-Clock-Time-Investigation-Basics).</span></span>

1. <span data-ttu-id="d65b9-151">Samla in en spårning med hjälp av trådtid.</span><span class="sxs-lookup"><span data-stu-id="d65b9-151">Collect a trace by using thread time.</span></span>
2. <span data-ttu-id="d65b9-152">Inkludera endast staplar som använder **runUnattended** för att endast filtrera tråden som har konfigurationskörning.</span><span class="sxs-lookup"><span data-stu-id="d65b9-152">Include only stacks that use **runUnattended**, to filter only the thread that has configuration execution.</span></span> <span data-ttu-id="d65b9-153">(Lägg till **runUnattended** i indatarutan **IncPats**.)</span><span class="sxs-lookup"><span data-stu-id="d65b9-153">(Add **runUnattended** to the **IncPats** input box.)</span></span>
3. <span data-ttu-id="d65b9-154">Vik all processor-, nätverks- och blockerad tid.</span><span class="sxs-lookup"><span data-stu-id="d65b9-154">Fold all CPU, network, and blocked time.</span></span>
4. <span data-ttu-id="d65b9-155">Läs in [ER-förinställningar för PerfView](https://download.microsoft.com/download/2/d/0/2d037b0f-ffd1-4d65-b64f-fcdf51f2c81f/ER_PerfViewPresets.xml).</span><span class="sxs-lookup"><span data-stu-id="d65b9-155">Load [ER presets for PerfView](https://download.microsoft.com/download/2/d/0/2d037b0f-ffd1-4d65-b64f-fcdf51f2c81f/ER_PerfViewPresets.xml).</span></span>
5. <span data-ttu-id="d65b9-156">Välj **ER** \> **Annan förinställning**.</span><span class="sxs-lookup"><span data-stu-id="d65b9-156">Select **ER** \> **Other preset**.</span></span>
6. <span data-ttu-id="d65b9-157">Titta på namnen:</span><span class="sxs-lookup"><span data-stu-id="d65b9-157">Look at the names:</span></span>

    - <span data-ttu-id="d65b9-158">Du kommer förmodligen att se den plattformskod som förbrukar mest tid.</span><span class="sxs-lookup"><span data-stu-id="d65b9-158">You will probably see the platform code that consumes the most time.</span></span>
    - <span data-ttu-id="d65b9-159">Du kan dubbeltrycka (eller dubbelklicka) och gå upp via **mottagare**.</span><span class="sxs-lookup"><span data-stu-id="d65b9-159">You can double-tap (or double-click) and go up through **callees**.</span></span>

        <span data-ttu-id="d65b9-160">Om du hittar klasser som har prefixet "ERExpression", och om dessa är funktioner som är relaterade till formler kan du gissa funktionsnamnet baserat på klassnamnet och du kan titta på ER-lagringsplatsen för att visa attributen.</span><span class="sxs-lookup"><span data-stu-id="d65b9-160">If you find classes that have the prefix "ERExpression," and if they are functions that are related to formulas, you can guess the function name based on the class name, and you can look at the ER repo to view the attributes.</span></span>

### <a name="fixes"></a><span data-ttu-id="d65b9-161">Korrigeringar</span><span class="sxs-lookup"><span data-stu-id="d65b9-161">Fixes</span></span>

- <span data-ttu-id="d65b9-162">Om du ser att större delen av processortiden förbrukas av frågor försöker du minska antalet frågor:</span><span class="sxs-lookup"><span data-stu-id="d65b9-162">If you see that most of the CPU time is consumed by queries, try to reduce the number of queries:</span></span>

    - <span data-ttu-id="d65b9-163">[Granska ER-spårningen](#analyze-database-calls) för duplicerade frågor.</span><span class="sxs-lookup"><span data-stu-id="d65b9-163">[Review the ER trace](#analyze-database-calls) for duplicated queries.</span></span>
    - <span data-ttu-id="d65b9-164">Se hur många poster som hämtas och utvärdera hur mycket data som teoretiskt ska hämtas.</span><span class="sxs-lookup"><span data-stu-id="d65b9-164">See how many records are fetched, and evaluate how much data should theoretically be fetched.</span></span>

- <span data-ttu-id="d65b9-165">Om du ser att större delen av processortiden förbrukas av de funktioner som används kan du försöka hitta den plats i konfigurationen som förbrukar flest resurser.</span><span class="sxs-lookup"><span data-stu-id="d65b9-165">If you see that most of the CPU time is consumed by the functions that are used, try to find the place in the configuration that consumes the most resources.</span></span>
- <span data-ttu-id="d65b9-166">Om du ser att större delen av processortiden förbrukas av datainsamlingsfunktioner bör du överväga att ersätta dem med *SQL-grupp efter* på modellmappningssidan.</span><span class="sxs-lookup"><span data-stu-id="d65b9-166">If you see that most of the CPU time is consumed by data collection functions, consider replacing them with *SQL group by* on the model mapping side.</span></span>

### <a name="collecting-data"></a><a name="collecting-data"></a><span data-ttu-id="d65b9-167">Datainsamling</span><span class="sxs-lookup"><span data-stu-id="d65b9-167">Collecting data</span></span>

<span data-ttu-id="d65b9-168">Beroende på din miljö finns det flera sätt att samla in tillgängliga data:</span><span class="sxs-lookup"><span data-stu-id="d65b9-168">Depending on your environment, there are several ways to collect available data:</span></span>

- <span data-ttu-id="d65b9-169">Få den totala körningstiden:</span><span class="sxs-lookup"><span data-stu-id="d65b9-169">Get the total running time:</span></span>

    - <span data-ttu-id="d65b9-170">Från åtgärdscentret</span><span class="sxs-lookup"><span data-stu-id="d65b9-170">From the Action center</span></span>
    - <span data-ttu-id="d65b9-171">Från händelseloggen</span><span class="sxs-lookup"><span data-stu-id="d65b9-171">From the event log</span></span>

- <span data-ttu-id="d65b9-172">Profilera körningen:</span><span class="sxs-lookup"><span data-stu-id="d65b9-172">Profile the execution:</span></span>

    - <span data-ttu-id="d65b9-173">Genom att använda ER-verktyg</span><span class="sxs-lookup"><span data-stu-id="d65b9-173">By using ER tools</span></span>
    - <span data-ttu-id="d65b9-174">Genom att använda Trace parser</span><span class="sxs-lookup"><span data-stu-id="d65b9-174">By using Trace parser</span></span>
    - <span data-ttu-id="d65b9-175">Genom att använda PerfView</span><span class="sxs-lookup"><span data-stu-id="d65b9-175">By using PerfView</span></span>

#### <a name="collecting-data-in-a-production-environment"></a><span data-ttu-id="d65b9-176">Samla in data i en produktionsmiljö</span><span class="sxs-lookup"><span data-stu-id="d65b9-176">Collecting data in a production environment</span></span>

<span data-ttu-id="d65b9-177">Ibland kan problem endast reproduceras i en produktionsmiljö.</span><span class="sxs-lookup"><span data-stu-id="d65b9-177">Sometimes, issues can be reproduced only in a production environment.</span></span> <span data-ttu-id="d65b9-178">Data kan samlas in på följande sätt:</span><span class="sxs-lookup"><span data-stu-id="d65b9-178">Data can be collected in the following ways:</span></span>

- <span data-ttu-id="d65b9-179">Genom att använda [Trace parser](../perf-test/trace-trace-tutorial.md)spår.</span><span class="sxs-lookup"><span data-stu-id="d65b9-179">By using [Trace parser](../perf-test/trace-trace-tutorial.md) traces</span></span>
- <span data-ttu-id="d65b9-180">Genom att använda spårningar efter [ER-körning](trace-execution-er-troubleshoot-perf.md)</span><span class="sxs-lookup"><span data-stu-id="d65b9-180">By using [ER execution](trace-execution-er-troubleshoot-perf.md) traces</span></span>
- <span data-ttu-id="d65b9-181">Genom att använda den totala körningstiden</span><span class="sxs-lookup"><span data-stu-id="d65b9-181">By using the total execution time</span></span>

#### <a name="collecting-data-in-a-development-environment"></a><span data-ttu-id="d65b9-182">Samla in data i en utvecklingsmiljö</span><span class="sxs-lookup"><span data-stu-id="d65b9-182">Collecting data in a development environment</span></span>

<span data-ttu-id="d65b9-183">Förutom de verktyg som kan användas i en produktionsmiljö finns det flera verktyg du kan använda i en utvecklingsmiljö:</span><span class="sxs-lookup"><span data-stu-id="d65b9-183">In addition to the tools that can be used in a production environment, there are several tools that you can use in a development environment:</span></span>

- <span data-ttu-id="d65b9-184">Händelselogg (Microsoft-Dynamics-ElectronicReporting).</span><span class="sxs-lookup"><span data-stu-id="d65b9-184">Event log (Microsoft-Dynamics-ElectronicReporting).</span></span> <span data-ttu-id="d65b9-185">Denna logg kan ge dig den totala körningstiden.</span><span class="sxs-lookup"><span data-stu-id="d65b9-185">This log can give you the total execution time.</span></span>
- <span data-ttu-id="d65b9-186">Vanliga .NET-verktyg, till exempel PerfView.</span><span class="sxs-lookup"><span data-stu-id="d65b9-186">Common .NET tools, such as PerfView.</span></span>

<span data-ttu-id="d65b9-187">Dessutom ger en utvecklingsmiljö dig mer flexibilitet att experimentera.</span><span class="sxs-lookup"><span data-stu-id="d65b9-187">Additionally, a development environment gives you more flexibility to experiment.</span></span> <span data-ttu-id="d65b9-188">Du kan till exempel stänga av delar av rapporter för att se hur körningstiden påverkas.</span><span class="sxs-lookup"><span data-stu-id="d65b9-188">For example, you can turn off parts of reports to see how the execution time is affected.</span></span>

### <a name="tools"></a><a name="tools"></a><span data-ttu-id="d65b9-189">Verktyg</span><span class="sxs-lookup"><span data-stu-id="d65b9-189">Tools</span></span>

#### <a name="execution-time-in-the-action-center"></a><a name="infolog-time"></a><span data-ttu-id="d65b9-190">Körningstid i åtgärdscentret</span><span class="sxs-lookup"><span data-stu-id="d65b9-190">Execution time in the Action center</span></span>

<span data-ttu-id="d65b9-191">ER kan visa körningstiden för konfigurationen i åtgärdscentret.</span><span class="sxs-lookup"><span data-stu-id="d65b9-191">ER can show the execution time of the configuration in the Action center.</span></span> <span data-ttu-id="d65b9-192">Detta alternativ fungerar bara för en viss användare och ett visst företag, och endast för interaktiva sessioner.</span><span class="sxs-lookup"><span data-stu-id="d65b9-192">This option works only for a specific user and a specific company, and only for interactive sessions.</span></span> <span data-ttu-id="d65b9-193">Följ dessa steg för att göra denna funktion tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="d65b9-193">To make this feature available, follow these steps.</span></span>

1. <span data-ttu-id="d65b9-194">Gå till **Organisationsadministration** \> **Elektronisk rapportering** \> **Konfigurationer**.</span><span class="sxs-lookup"><span data-stu-id="d65b9-194">Go to **Organization administration** \> **Electronic reporting** \> **Configurations**.</span></span>
2. <span data-ttu-id="d65b9-195">På sidan **Konfigurationer** i åtgärdsfönstret, på fliken **Konfigurationer** i gruppen **Avancerad inställningar** markerar du **Använd parametrar**.</span><span class="sxs-lookup"><span data-stu-id="d65b9-195">On the **Configurations** page, on the Action Pane, on the **Configurations** tab, in the **Advanced settings** group, select **User parameters**.</span></span>
3. <span data-ttu-id="d65b9-196">I dialogrutan **Användarparametrar** anger du alternativet **Visa genereringstid för fil** som **Ja**.</span><span class="sxs-lookup"><span data-stu-id="d65b9-196">In the **User parameters** dialog box, set the **Show file generation time** option to **Yes**.</span></span>

#### <a name="execution-time-in-the-event-log"></a><a name="event-log-time"></a><span data-ttu-id="d65b9-197">Körningstid i händelseloggen</span><span class="sxs-lookup"><span data-stu-id="d65b9-197">Execution time in the event log</span></span>

1. <span data-ttu-id="d65b9-198">Öppna Loggboken i Windows.</span><span class="sxs-lookup"><span data-stu-id="d65b9-198">Open Windows Event Viewer.</span></span>
2. <span data-ttu-id="d65b9-199">Under **Program- och tjänsteloggar** öppnar du **Microsoft-Dynamics-ElectronicReporting/Operational**.</span><span class="sxs-lookup"><span data-stu-id="d65b9-199">Under **Applications and Services logs**, open **Microsoft-Dynamics-ElectronicReporting/Operational**.</span></span>
3. <span data-ttu-id="d65b9-200">Leta efter **FormatMapingRun**-händelser där **EventID=2**, detta eftersom dessa händelser innehåller information om förfluten tid.</span><span class="sxs-lookup"><span data-stu-id="d65b9-200">Look for **FormatMapingRun** events where **EventID=2**, because these events contain the information about elapsed time.</span></span>

#### <a name="trace-parser-traces"></a><a name="trace-parser"></a><span data-ttu-id="d65b9-201">Trace parser-spår</span><span class="sxs-lookup"><span data-stu-id="d65b9-201">Trace parser traces</span></span> 

<span data-ttu-id="d65b9-202">Eftersom ER implementeras i X++kan du använda vanliga X++ -verktyg för att analysera prestanda.</span><span class="sxs-lookup"><span data-stu-id="d65b9-202">Because ER is implemented in X++, you can use common X++ tools to analyze performance.</span></span> <span data-ttu-id="d65b9-203">Mer information finns i [Spåra med hjälp av Trace parser](../perf-test/trace-trace-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="d65b9-203">For more information, see [Take traces by using Trace parser](../perf-test/trace-trace-tutorial.md).</span></span>

<span data-ttu-id="d65b9-204">Det finns några begränsningar i samband med detta tillvägagångssätt.</span><span class="sxs-lookup"><span data-stu-id="d65b9-204">There are a few limitations to this approach.</span></span> <span data-ttu-id="d65b9-205">Eftersom en del av ER implementeras i C# kommer inte alla detaljer att vara tillgängliga.</span><span class="sxs-lookup"><span data-stu-id="d65b9-205">Because part of ER is implemented in C#, not all the details will be available.</span></span> <span data-ttu-id="d65b9-206">Du kan dock visa detaljerad information om dataanvändningen.</span><span class="sxs-lookup"><span data-stu-id="d65b9-206">However, you can view the data usage details.</span></span> <span data-ttu-id="d65b9-207">Dessutom kan långa rapportkörningar komma att överskrida begränsningar för spårningslagring.</span><span class="sxs-lookup"><span data-stu-id="d65b9-207">Additionally, long report runs can exceed trace storage limitations.</span></span>

#### <a name="er-traces"></a><a name="electronic-reporting-traces"></a><span data-ttu-id="d65b9-208">ER-spår</span><span class="sxs-lookup"><span data-stu-id="d65b9-208">ER traces</span></span>

<span data-ttu-id="d65b9-209">ER kan samla sina egna spår, och har visualiserings- och analysverktyg för dessa spår.</span><span class="sxs-lookup"><span data-stu-id="d65b9-209">ER can collect its own traces, and it has visualization and analysis tools for those traces.</span></span> <span data-ttu-id="d65b9-210">För mer information, se [Spåra körningen av ER-format för att felsöka prestandaproblem](trace-execution-er-troubleshoot-perf.md).</span><span class="sxs-lookup"><span data-stu-id="d65b9-210">For more information, see [Trace the execution of ER formats to troubleshoot performance issues](trace-execution-er-troubleshoot-perf.md).</span></span>

#### <a name="perfview"></a><a name="perfview"></a><span data-ttu-id="d65b9-211">PerfView</span><span class="sxs-lookup"><span data-stu-id="d65b9-211">PerfView</span></span>

<span data-ttu-id="d65b9-212">Eftersom både X++ och ER implementeras ovanpå .NET-plattformen kan du använda vanliga .NET-verktyg.</span><span class="sxs-lookup"><span data-stu-id="d65b9-212">Because both X++ and ER are implemented on top of the .NET platform, you can use common .NET tools.</span></span> <span data-ttu-id="d65b9-213">Du kan till exempel använda det kostnadsfria verktyget [PerfView](https://github.com/Microsoft/perfview).</span><span class="sxs-lookup"><span data-stu-id="d65b9-213">For example, you can use the free [PerfView](https://github.com/Microsoft/perfview) tool.</span></span>

<span data-ttu-id="d65b9-214">Du kan också samla in data från kommandoraden.</span><span class="sxs-lookup"><span data-stu-id="d65b9-214">You can also collect data from the command line.</span></span> <span data-ttu-id="d65b9-215">Följande Windows PowerShell-skript samlar till exempel in körningstiden tills alla formatkörningar stoppats på datorn.</span><span class="sxs-lookup"><span data-stu-id="d65b9-215">For example, the following Windows PowerShell script collects the execution time until any format execution is stopped on the machine.</span></span>

```powershell
c:\programs\PerfView collect "e:\traces\$(date -format "ddMMyyyy_hhmm").etl" `
    -CircularMB:20000 -ThreadTime `
    -NoNGenRundown `
    -StopOnEtwEvent:Microsoft-Dynamics-ElectronicReporting/FormatMappingRun/Stop
```

<span data-ttu-id="d65b9-216">Det finns några begränsningar i samband med detta tillvägagångssätt.</span><span class="sxs-lookup"><span data-stu-id="d65b9-216">There are a few limitations to this approach.</span></span> <span data-ttu-id="d65b9-217">Du måste ha administratörsåtkomst till maskinen.</span><span class="sxs-lookup"><span data-stu-id="d65b9-217">You must have administrative access to the machine.</span></span> <span data-ttu-id="d65b9-218">Du måste dessutom vara en erfaren utvecklare, detta eftersom inlärningskurvan är brant.</span><span class="sxs-lookup"><span data-stu-id="d65b9-218">Additionally, you must be an experienced developer, because there is a steep learning curve.</span></span>

### <a name="making-changes"></a><a name="making-changes"></a><span data-ttu-id="d65b9-219">Göra ändringar</span><span class="sxs-lookup"><span data-stu-id="d65b9-219">Making changes</span></span>

#### <a name="use-caching"></a><a name="use-caching"></a><span data-ttu-id="d65b9-220">Använd cachelagring</span><span class="sxs-lookup"><span data-stu-id="d65b9-220">Use caching</span></span>

<span data-ttu-id="d65b9-221">Även om cachelagring minskar den tid som krävs för att hämta data igen, så kostar den minne.</span><span class="sxs-lookup"><span data-stu-id="d65b9-221">Although caching reduces the amount of time that is required to fetch data again, it costs memory.</span></span> <span data-ttu-id="d65b9-222">Använd cachelagring i de fall där mängden hämtade data inte är särskilt stor.</span><span class="sxs-lookup"><span data-stu-id="d65b9-222">Use caching in cases where the amount of fetched data isn't very large.</span></span> <span data-ttu-id="d65b9-223">Mer information och ett exempel som visar hur du använder cachelagring finns i [Förbättra modellmappningen baserat på information från körningsspårningen](trace-execution-er-troubleshoot-perf.md#improve-the-model-mapping-based-on-information-from-the-execution-trace).</span><span class="sxs-lookup"><span data-stu-id="d65b9-223">For more information and an example that shows how to use caching, see [Improve the model mapping based on information from the execution trace](trace-execution-er-troubleshoot-perf.md#improve-the-model-mapping-based-on-information-from-the-execution-trace).</span></span>

#### <a name="use-a-cached-parameterized-calculated-field"></a><a name="cached-parameterized"></a><span data-ttu-id="d65b9-224">Använd ett cachelagrat, parameteriserat beräknat fält</span><span class="sxs-lookup"><span data-stu-id="d65b9-224">Use a cached, parameterized calculated field</span></span>

<span data-ttu-id="d65b9-225">Ibland måste värdena sökas upprepade gånger.</span><span class="sxs-lookup"><span data-stu-id="d65b9-225">Sometimes, values must be looked up repeatedly.</span></span> <span data-ttu-id="d65b9-226">Exempel på detta är kontonamn och kontonummer.</span><span class="sxs-lookup"><span data-stu-id="d65b9-226">Examples include account names and account numbers.</span></span> <span data-ttu-id="d65b9-227">För att spara tid kan du skapa ett beräknat fält som har parametrar på den översta nivån och sedan lägga till fältet i cacheminnet.</span><span class="sxs-lookup"><span data-stu-id="d65b9-227">To help save time, you can create a calculated field that has parameters on the top level, and then add the field to the cache.</span></span>

<span data-ttu-id="d65b9-228">Vi rekommenderar att du bara använder den här metoden när storleken på cachelagrade data är liten.</span><span class="sxs-lookup"><span data-stu-id="d65b9-228">We recommend that you use this approach only when the size of the cached data is small.</span></span> <span data-ttu-id="d65b9-229">Mer information finns i [Förbättra prestanda för ER-lösningar genom att lägga till parametriserade datakällor för BERÄKNADE FÄLT](er-calculated-field-ds-performance.md).</span><span class="sxs-lookup"><span data-stu-id="d65b9-229">For more information, see [Improve the performance of ER solutions by adding parameterized CALCULATED FIELD data sources](er-calculated-field-ds-performance.md).</span></span>

#### <a name="use-a-join-data-source"></a><a name="use-join-datasource"></a><span data-ttu-id="d65b9-230">Använd en KOPPLA-datakälla</span><span class="sxs-lookup"><span data-stu-id="d65b9-230">Use a JOIN data source</span></span>

<span data-ttu-id="d65b9-231">Med en **KOPPLA**-datakälla kan flera anslutna poster hämtas av en enda fråga.</span><span class="sxs-lookup"><span data-stu-id="d65b9-231">A **JOIN** data source enables several connected records to be fetched by one query.</span></span> <span data-ttu-id="d65b9-232">En separat fråga behöver inte användas för att hämta varje ansluten post.</span><span class="sxs-lookup"><span data-stu-id="d65b9-232">A separate query doesn't have to be used to fetch each connected record.</span></span> <span data-ttu-id="d65b9-233">Om du till exempel har 1 000 rader och hämtar artikeldata för respektive rad efter relation, får du 1 001 frågor (= 1 000 + 1).</span><span class="sxs-lookup"><span data-stu-id="d65b9-233">For example, if you have 1,000 lines, and you fetch item data for each line by relation, you will have 1,001 queries (= 1,000 + 1).</span></span> <span data-ttu-id="d65b9-234">Om du använder en **KOPPLA**-datakälla använder du bara en enda fråga för att hämta samma data.</span><span class="sxs-lookup"><span data-stu-id="d65b9-234">If you use a **JOIN** data source, you will use only one query to fetch the same data.</span></span> <span data-ttu-id="d65b9-235">Se [Använd KOPPL-datakällor i ER-modellmappningar för att hämta data från flera programtabeller](er-join-data-sources.md) om du vill ha mer information.</span><span class="sxs-lookup"><span data-stu-id="d65b9-235">For more information, see [Use JOIN data sources in ER model mappings to get data from multiple application tables](er-join-data-sources.md).</span></span>

#### <a name="use-the-filter-function-instead-of-the-where-function"></a><a name="filter"></a><span data-ttu-id="d65b9-236">Använd funktionen FILTER istället för funktionen VAR</span><span class="sxs-lookup"><span data-stu-id="d65b9-236">Use the FILTER function instead of the WHERE function</span></span>

<span data-ttu-id="d65b9-237">Funktionen **[FILTER](er-functions-list-filter.md)** kör villkor på SQL Server, medan funktionen **VAR** hämtar alla data i listan - en post i taget - och applicerar villkoret för respektive post.</span><span class="sxs-lookup"><span data-stu-id="d65b9-237">The **[FILTER](er-functions-list-filter.md)** function runs conditions on SQL Server, whereas the **WHERE** function fetches all data from the list, one record at a time, and applies the condition for each record.</span></span> <span data-ttu-id="d65b9-238">Du vill till exempel välja en enda post av 1 000 poster.</span><span class="sxs-lookup"><span data-stu-id="d65b9-238">For example, you want to select one record out of 1,000 records.</span></span> <span data-ttu-id="d65b9-239">Om du använder **VAR** hämtas alla 1 000 poster.</span><span class="sxs-lookup"><span data-stu-id="d65b9-239">If you use **WHERE**, all 1,000 records will be fetched.</span></span> <span data-ttu-id="d65b9-240">Om du emellertid använder **FILTER** hämtas exakt en (1) post.</span><span class="sxs-lookup"><span data-stu-id="d65b9-240">However, if you use **FILTER**, exactly one record will be fetched.</span></span> <span data-ttu-id="d65b9-241">**FILTER** kan också använda index på databassidan.</span><span class="sxs-lookup"><span data-stu-id="d65b9-241">**FILTER** can also use indexes on the database side.</span></span>

#### <a name="using-collected-data-functions-or-an-accumulated-data-data-source"></a><a name="collected-data"></a><span data-ttu-id="d65b9-242">Använda insamlade datafunktioner eller en ackumulerad datakälla</span><span class="sxs-lookup"><span data-stu-id="d65b9-242">Using collected data functions or an accumulated data data source</span></span>

<span data-ttu-id="d65b9-243">Om konfigurationen har en *gruppera efter*-komponent som sammanfattar tidigare hämtade data efter rapport, hämtar komponenten alla data igen.</span><span class="sxs-lookup"><span data-stu-id="d65b9-243">If your configuration has a *group by* component that summarizes previously fetched data by report, the component will fetch all the data again.</span></span> <span data-ttu-id="d65b9-244">Genom att använda insamlade datafunktioner gör du det möjligt för ER att samla in data under den första hämtningen.</span><span class="sxs-lookup"><span data-stu-id="d65b9-244">By using collected data functions, you enable ER to accumulate data during the first fetch.</span></span> <span data-ttu-id="d65b9-245">Mer information finns i [Konfigurera format för inventering och summering i ER](tasks/er-format-counting-summing-2.md).</span><span class="sxs-lookup"><span data-stu-id="d65b9-245">For more information, see [ER Configure format to do counting and summing](tasks/er-format-counting-summing-2.md).</span></span>

#### <a name="rewrite-parts-of-the-configuration-in-x"></a><span data-ttu-id="d65b9-246">Skriva om delar av konfigurationen i X++</span><span class="sxs-lookup"><span data-stu-id="d65b9-246">Rewrite parts of the configuration in X++</span></span>

<span data-ttu-id="d65b9-247">ER stöder anropmetoder för tabeller och klasser, inklusive tillägg.</span><span class="sxs-lookup"><span data-stu-id="d65b9-247">ER supports calling methods of tables and classes, including extensions.</span></span> <span data-ttu-id="d65b9-248">Överväg att skriva om delar av modellmappningen i X++ för att förbättra prestandan.</span><span class="sxs-lookup"><span data-stu-id="d65b9-248">Consider rewriting parts of the model mapping in X++ to help improve performance.</span></span>

<span data-ttu-id="d65b9-249">ER kan använda data från följande källor:</span><span class="sxs-lookup"><span data-stu-id="d65b9-249">ER can consume data from the following sources:</span></span>

- <span data-ttu-id="d65b9-250">Klasser (datakällorna **objekt** och **klass**)</span><span class="sxs-lookup"><span data-stu-id="d65b9-250">Classes (**object** and **class** data sources)</span></span>
- <span data-ttu-id="d65b9-251">Tabeller (datakällorna **tabell** och **tabellposter**)</span><span class="sxs-lookup"><span data-stu-id="d65b9-251">Tables (**table** and **table records** data sources)</span></span>

<span data-ttu-id="d65b9-252">[ER-API:n](er-apis-app73.md#how-to-access-internal-x-objects-by-using-erobjectsfactory) ger också ett sätt att skicka förberäknade data från den anropande koden.</span><span class="sxs-lookup"><span data-stu-id="d65b9-252">The [ER API](er-apis-app73.md#how-to-access-internal-x-objects-by-using-erobjectsfactory) also provides a way to send precalculated data from the calling code.</span></span> <span data-ttu-id="d65b9-253">Programserien innehåller många exempel på den här metoden.</span><span class="sxs-lookup"><span data-stu-id="d65b9-253">The application suite contains numerous examples of this approach.</span></span>
