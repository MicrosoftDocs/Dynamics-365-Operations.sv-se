---
title: Förbättra prestanda för ER-lösningar genom att lägga till parametriserade datakällor för BERÄKNADE FÄLT
description: I det här avsnittet beskrivs hur du kan förbättra prestandan hos elektronisk rapportering (ER)-lösningar genom att lägga till parametriserade datakällor för BERÄKNADE FÄLT.
author: NickSelin
ms.date: 09/02/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: ''
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 299570d6a94b0f9e7ee7cf490d4c1aeeb86d5716
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5749523"
---
# <a name="improve-the-performance-of-er-solutions-by-adding-parameterized-calculated-field-data-sources"></a><span data-ttu-id="ea091-103">Förbättra prestanda för ER-lösningar genom att lägga till parametriserade datakällor för BERÄKNADE FÄLT</span><span class="sxs-lookup"><span data-stu-id="ea091-103">Improve the performance of ER solutions by adding parameterized CALCULATED FIELD data sources</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="ea091-104">I det här avsnittet beskrivs hur du kan göra [prestandaspårningar](trace-execution-er-troubleshoot-perf.md) av formatet [elektronisk rapportering (ER)](general-electronic-reporting.md) som körs och sedan använda informationen från dessa spårningar för att förbättra prestanda genom att konfigurera en parameter för datakälla **beräknat fält**.</span><span class="sxs-lookup"><span data-stu-id="ea091-104">This topic explains how you can take [performance traces](trace-execution-er-troubleshoot-perf.md) of [Electronic reporting (ER)](general-electronic-reporting.md) formats that are run, and then use the information from those traces to help improve performance by configuring a parameterized **Calculated field** data source.</span></span>

<span data-ttu-id="ea091-105">Som en del av processen att utforma ER-konfigurationer för att generera affärsdokument definierar du metoden som används för att hämta data från applikationen och mata in den i den genererade utdata.</span><span class="sxs-lookup"><span data-stu-id="ea091-105">As part of the process of designing ER configurations to generate business documents, you define the method that is used to retrieve data from the application and enter it in the generated output.</span></span> <span data-ttu-id="ea091-106">Genom att utforma en parametriserad ER-datakälla av typen **beräknade fält** kan du minska antalet databasanrop och avsevärt minska den tid och kostnad som krävs för att samla in information om ER-formatkörning.</span><span class="sxs-lookup"><span data-stu-id="ea091-106">By designing a parametrized ER data source of the **Calculated field** type, you can reduce the number of database calls, and significantly reduce the time and cost that are involved in collecting the details of ER format execution.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="ea091-107">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="ea091-107">Prerequisites</span></span>

- <span data-ttu-id="ea091-108">Om du vill slutföra exemplen i det här avsnittet måste du ha tillgång till en av följande [roller](../sysadmin/tasks/assign-users-security-roles.md):</span><span class="sxs-lookup"><span data-stu-id="ea091-108">To complete the examples in this topic, you must have the access to one of the following [roles](../sysadmin/tasks/assign-users-security-roles.md):</span></span>

    - <span data-ttu-id="ea091-109">Utvecklare för elektronisk rapportering</span><span class="sxs-lookup"><span data-stu-id="ea091-109">Electronic reporting developer</span></span>
    - <span data-ttu-id="ea091-110">Konsult för funktionen för elektronisk rapportering</span><span class="sxs-lookup"><span data-stu-id="ea091-110">Electronic reporting functional consultant</span></span>
    - <span data-ttu-id="ea091-111">Systemadministratör</span><span class="sxs-lookup"><span data-stu-id="ea091-111">System administrator</span></span>

- <span data-ttu-id="ea091-112">Företaget måste vara inställt på **DEMF**.</span><span class="sxs-lookup"><span data-stu-id="ea091-112">The company must be set to **DEMF**.</span></span>
- <span data-ttu-id="ea091-113">Följ instruktionerna i [Bilaga 1](#appendix1) i det här avsnittet för att hämta komponenterna för exemplet Microsoft ER-lösning som krävs för att slutföra exemplen i detta ämne.</span><span class="sxs-lookup"><span data-stu-id="ea091-113">Follow the steps in [Appendix 1](#appendix1) of this topic to download the components of the sample Microsoft ER solution that is required to complete the examples in this topic.</span></span>
- <span data-ttu-id="ea091-114">Följ stegen i [tillägg 2](#appendix2) i det här avsnittet om du vill konfigurera den minsta uppsättningen ER-parametrar som krävs för att använda ER-ramverket för att förbättra prestanda i exempel Microsoft ER-lösningen.</span><span class="sxs-lookup"><span data-stu-id="ea091-114">Follow the steps in [Appendix 2](#appendix2) of this topic to configure the minimal set of ER parameters that is required to use the ER framework to help improve the performance of the sample Microsoft ER solution.</span></span>

## <a name="import-the-sample-er-solution"></a><span data-ttu-id="ea091-115">Importera ER-exempellösning</span><span class="sxs-lookup"><span data-stu-id="ea091-115">Import the sample ER solution</span></span>

<span data-ttu-id="ea091-116">Tänk dig att du måste designa en ER-lösning för att skapa en ny rapport som visar leverantörstransaktioner.</span><span class="sxs-lookup"><span data-stu-id="ea091-116">Imagine that you must design an ER solution to generate a new report that shows vendor transactions.</span></span> <span data-ttu-id="ea091-117">För närvarande kan du hitta transaktionerna för en vald leverantör på sidan **leverantörstransaktioner** (gå till **leverantörsreskontra** \> **leverantörer** \> **alla leverantörer**, välj en leverantörer och sedan i åtgärdspanelen på fliken **leverantörer** i gruppen **transaktioner** väljer du **transaktioner**).</span><span class="sxs-lookup"><span data-stu-id="ea091-117">Currently, you can find the transactions for a selected vendor on the **Vendor transactions** page (go to **Account payable** \> **Vendors** \> **All vendors**, select a vendor, and then, on the Action Pane, on the **Vendor** tab, in the **Transactions** group, select **Transactions**).</span></span> <span data-ttu-id="ea091-118">Du vill dock ha alla leverantörstransaktioner samtidigt i ett elektroniskt dokument i XML-format.</span><span class="sxs-lookup"><span data-stu-id="ea091-118">However, you want to have all vendor transactions together in one electronic document in XML format.</span></span> <span data-ttu-id="ea091-119">Den här lösningen består av flera ER-konfigurationer som innehåller den nödvändiga datamodellen, modellmappning och formatkomponenter.</span><span class="sxs-lookup"><span data-stu-id="ea091-119">This solution will consist of several ER configurations that contain the required data model, model mapping, and format components.</span></span>

<span data-ttu-id="ea091-120">Det första steget är att importera exempel ER-lösningen för att generera en leverantörstransaktionsrapport.</span><span class="sxs-lookup"><span data-stu-id="ea091-120">The first step is to import the sample ER solution to generate a vendor transactions report.</span></span>

1. <span data-ttu-id="ea091-121">Logga in på den instans av Microsoft Dynamics 365 Finance som har etablerats för ditt företag.</span><span class="sxs-lookup"><span data-stu-id="ea091-121">Sign in to the instance of Microsoft Dynamics 365 Finance that is provisioned for your company.</span></span>
2. <span data-ttu-id="ea091-122">I det här avsnittet ska du skapa och ändra konfigurationer för exempelföretaget **Litware, Inc**.</span><span class="sxs-lookup"><span data-stu-id="ea091-122">In this topic, you will create and modify configurations for the **Litware, Inc.** sample company.</span></span> <span data-ttu-id="ea091-123">Kontrollera att denna konfigurationsleverantör har lagts till i din Finance-instans och valts som aktiv.</span><span class="sxs-lookup"><span data-stu-id="ea091-123">Make sure that this configuration provider has been added to your Finance instance and is marked as active.</span></span> <span data-ttu-id="ea091-124">Mer information finns i [Skapa konfigurationsleverantörer och markera dem som aktiva](tasks/er-configuration-provider-mark-it-active-2016-11.md).</span><span class="sxs-lookup"><span data-stu-id="ea091-124">For more information, see [Create configuration providers and mark them as active](tasks/er-configuration-provider-mark-it-active-2016-11.md).</span></span>
3. <span data-ttu-id="ea091-125">På arbetsytan **Elektronisk rapportering** väljer du panelen **Rapporteringskonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="ea091-125">In the **Electronic reporting** workspace, select the **Reporting configurations** tile.</span></span>
4. <span data-ttu-id="ea091-126">På sidan **konfigurationer** importerar du de ER-konfigurationer som du hämtade som en förutsättning i Finance i följande ordning: datamodell, modellmappning, format.</span><span class="sxs-lookup"><span data-stu-id="ea091-126">On the **Configurations** page, import the ER configurations that you downloaded as a prerequisite into Finance, in the following order: data model, model mapping, format.</span></span> <span data-ttu-id="ea091-127">Följ dessa steg för varje konfiguration:</span><span class="sxs-lookup"><span data-stu-id="ea091-127">For each configuration, follow these steps:</span></span>

    1. <span data-ttu-id="ea091-128">På Åtgärdsfönster väljer du **växla** \> **läs in från XML-fil**.</span><span class="sxs-lookup"><span data-stu-id="ea091-128">On the Action Pane, select **Exchange** \> **Load from XML file**.</span></span>
    2. <span data-ttu-id="ea091-129">Välj **bläddra** om du vill välja en fil för ER-konfigurationen i XML-format.</span><span class="sxs-lookup"><span data-stu-id="ea091-129">Select **Browse**, and select the appropriate file for the ER configuration in XML format.</span></span>
    3. <span data-ttu-id="ea091-130">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="ea091-130">Select **OK**.</span></span>

![Importerade konfigurationer på sidan Konfigurationer](./media/er-calculated-field-ds-performance-imported-configurations.png)

## <a name="review-the-sample-er-solution"></a><span data-ttu-id="ea091-132">Granska ER-exempellösning</span><span class="sxs-lookup"><span data-stu-id="ea091-132">Review the sample ER solution</span></span>

### <a name="review-the-model-mapping"></a><span data-ttu-id="ea091-133">Granska modellmappningen</span><span class="sxs-lookup"><span data-stu-id="ea091-133">Review the model mapping</span></span>

1. <span data-ttu-id="ea091-134">På sidan **konfigurationer** i konfigurationsträdet i vänster fönster expanderar du **modell för prestandaförbättring** och väljer sedan **mappning av prestandaförbättring**.</span><span class="sxs-lookup"><span data-stu-id="ea091-134">On the **Configurations** page, in the configuration tree, expand **Performance improvement model**, and select **Performance improvement mapping**.</span></span>
2. <span data-ttu-id="ea091-135">Klicka på **Designer** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="ea091-135">On the Action Pane, select **Designer**.</span></span>
3. <span data-ttu-id="ea091-136">På sidan **Modell till mappning av datakälla** i åtgärdsfönstret, välj **Designer**.</span><span class="sxs-lookup"><span data-stu-id="ea091-136">On the **Model to datasource mapping** page, on the Action Pane, select **Designer**.</span></span>

    <span data-ttu-id="ea091-137">Den här ER-modellmappningen har utformats för att göra följande åtgärder:</span><span class="sxs-lookup"><span data-stu-id="ea091-137">This ER model mapping is designed to perform the following actions:</span></span>

    - <span data-ttu-id="ea091-138">Hämta listan med leverantörstransaktioner som är lagrade i registret VendTrans (**Trans** datakälla).</span><span class="sxs-lookup"><span data-stu-id="ea091-138">Fetch the list of vendor transactions that are stored in the VendTrans table (**Trans** data source).</span></span>
    - <span data-ttu-id="ea091-139">För varje transaktion hämtas från tabellen VendTable, posten för en leverantör som transaktionen har bokförts för (**\#Vend** datakälla).</span><span class="sxs-lookup"><span data-stu-id="ea091-139">For every transaction, fetch, from the VendTable table, the record of a vendor that the transaction has been posted for (**\#Vend** data source).</span></span>

    > [!NOTE]
    > <span data-ttu-id="ea091-140">Datakälla **\#Vend** är konfigurerad för att hämta motsvarande leverantörspost genom att använda den befintliga många till en-relationen **\@.'\>Relations'.VendTable\_AccountNum**.</span><span class="sxs-lookup"><span data-stu-id="ea091-140">The **\#Vend** data source is configured to fetch the corresponding vendor record by using the existing many-to-one relation **\@.'\>Relations'.VendTable\_AccountNum**.</span></span>

    <span data-ttu-id="ea091-141">Modellmappningen i den här konfigurationen implementerar basdatamodellen för alla ER-format som skapas för den här modellen och körs i Finance.</span><span class="sxs-lookup"><span data-stu-id="ea091-141">The model mapping in this configuration implements the base data model for any ER formats that are created for this model and run in Finance.</span></span> <span data-ttu-id="ea091-142">Detta innebär att innehållet i datakällan **Trans** visas för ER-format, t.ex. abstrakta datakällor **modell**.</span><span class="sxs-lookup"><span data-stu-id="ea091-142">Therefore, the content of the **Trans** data source is exposed for ER formats such as abstract **model** data sources.</span></span>

    ![Trans datakälla på sidan för modellmappningsdesigner](media/er-calculated-field-ds-performance-mapping-1.png)

4. <span data-ttu-id="ea091-144">Stäng sidan **modellmappningsdesigner**.</span><span class="sxs-lookup"><span data-stu-id="ea091-144">Close the **Model mapping designer** page.</span></span>
5. <span data-ttu-id="ea091-145">Stäng sidan **modell till mappning av datakälla**.</span><span class="sxs-lookup"><span data-stu-id="ea091-145">Close the **Model to datasource mapping** page.</span></span>

### <a name="review-format"></a><span data-ttu-id="ea091-146">Granska format</span><span class="sxs-lookup"><span data-stu-id="ea091-146">Review format</span></span>

1. <span data-ttu-id="ea091-147">På sidan **konfigurationer** i konfigurationsträdet i vänster fönster expanderar du **modell för prestandaförbättring** och väljer sedan **format för prestandaförbättring**.</span><span class="sxs-lookup"><span data-stu-id="ea091-147">On the **Configurations** page, in the configuration tree, expand **Performance improvement model**, and select **Performance improvement format**.</span></span>
2. <span data-ttu-id="ea091-148">Klicka på **Designer** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="ea091-148">On the Action Pane, select **Designer**.</span></span>
3. <span data-ttu-id="ea091-149">På sidan **Formatdesigner** på fliken **Mappning** välj **Utöka/Komprimera**.</span><span class="sxs-lookup"><span data-stu-id="ea091-149">On the **Format designer** page, on the **Mapping** tab, select **Expand/Collapse**.</span></span>
4. <span data-ttu-id="ea091-150">Expandera artiklarna **Modell**, **Data** och **Transaktion**.</span><span class="sxs-lookup"><span data-stu-id="ea091-150">Expand the **Model**, **Data,** and **Transaction** items.</span></span>

    <span data-ttu-id="ea091-151">Det här ER-formatet är utformat för att skapa en leverantörstransaktionsrapport i XML-format.</span><span class="sxs-lookup"><span data-stu-id="ea091-151">This ER format is designed to generate a vendor transactions report in XML format.</span></span>

    ![Formatera datakällor och konfigurerade bindningar för formatelement på sidan formatdesigner](media/er-calculated-field-ds-performance-format.png)

5. <span data-ttu-id="ea091-153">Stäng sidan **Formatdesigner**.</span><span class="sxs-lookup"><span data-stu-id="ea091-153">Close the **Format designer** page.</span></span>

## <a name="run-the-sample-er-solution-to-trace-execution"></a><span data-ttu-id="ea091-154">Kör exempel ER-lösning för att spåra körning</span><span class="sxs-lookup"><span data-stu-id="ea091-154">Run the sample ER solution to trace execution</span></span>

<span data-ttu-id="ea091-155">Anta att du har skapat den första versionen av ER-lösningen.</span><span class="sxs-lookup"><span data-stu-id="ea091-155">Imagine that you've finished designing the first version of the ER solution.</span></span> <span data-ttu-id="ea091-156">Du vill nu testa lösningen i Finance-instansen och analysera körningsprestanda.</span><span class="sxs-lookup"><span data-stu-id="ea091-156">You now want to test the solution in your Finance instance and analyze the execution performance.</span></span>

### <a name="turn-on-the-er-performance-trace"></a><span data-ttu-id="ea091-157">Aktivera ER-prestandaspårning</span><span class="sxs-lookup"><span data-stu-id="ea091-157">Turn on the ER performance trace</span></span>

1. <span data-ttu-id="ea091-158">Välj företaget **DEMF**.</span><span class="sxs-lookup"><span data-stu-id="ea091-158">Select the **DEMF** company.</span></span>
2. <span data-ttu-id="ea091-159">Följ stegen i [Aktivera ER-prestationsspårning](trace-execution-er-troubleshoot-perf.md#turn-on-the-er-performance-trace) för att generera en prestandaspårning medan ett ER-format körs.</span><span class="sxs-lookup"><span data-stu-id="ea091-159">Follow the steps in [Turn on the ER performance trace](trace-execution-er-troubleshoot-perf.md#turn-on-the-er-performance-trace) to generate a performance trace while an ER format is run.</span></span>

    ![Dialogruta Användarparametrar](media/er-calculated-field-ds-performance-format-user-parameters.png)

### <a name="run-the-er-format"></a><a id="run-format"></a><span data-ttu-id="ea091-161">Kör ER-format</span><span class="sxs-lookup"><span data-stu-id="ea091-161">Run the ER format</span></span>

1. <span data-ttu-id="ea091-162">Gå till **Organisationsadministration** \> **Elektronisk rapportering** \> **Konfigurationer**.</span><span class="sxs-lookup"><span data-stu-id="ea091-162">Go to **Organization administration** \> **Electronic reporting** \> **Configurations**.</span></span>
2. <span data-ttu-id="ea091-163">På sidan **konfigurationer** i konfigurationsträdet väljer du artikeln **Prestandaförbättringsformat**.</span><span class="sxs-lookup"><span data-stu-id="ea091-163">On the **Configurations** page, in the configuration tree, select **Performance improvement format**.</span></span>
3. <span data-ttu-id="ea091-164">Klicka på **Kör** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="ea091-164">On the Action Pane, select **Run**.</span></span>

## <a name="use-the-performance-trace-to-analyze-model-mapping-performance"></a><span data-ttu-id="ea091-165">Använd prestandaspårning för att analysera modell mappningsresultat</span><span class="sxs-lookup"><span data-stu-id="ea091-165">Use the performance trace to analyze model mapping performance</span></span>

1. <span data-ttu-id="ea091-166">På sidan **konfigurationer** i konfigurationsträdet väljer du artikeln **Prestandaförbättringsmappning**.</span><span class="sxs-lookup"><span data-stu-id="ea091-166">On the **Configurations** page, in the configuration tree, select **Performance improvement mapping**.</span></span>
2. <span data-ttu-id="ea091-167">Klicka på **Designer** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="ea091-167">On the Action Pane, select **Designer**.</span></span>
3. <span data-ttu-id="ea091-168">På sidan **Modellmappning** i åtgärdsfönstret, välj **Designer**.</span><span class="sxs-lookup"><span data-stu-id="ea091-168">On the **Model mappings** page, on the Action Pane, select **Designer**.</span></span>
4. <span data-ttu-id="ea091-169">På snabbfliken **Modellmappningsdesigner** på åtgärdsfönstret väljer du **Prestandaspårningsformat**.</span><span class="sxs-lookup"><span data-stu-id="ea091-169">On the **Model mapping designer** page, on the Action Pane, select **Performance trace**.</span></span>
5. <span data-ttu-id="ea091-170">Markera den senaste spårningen som genererades och välj sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="ea091-170">Select the most recent trace that was generated, and then select **OK**.</span></span>

<span data-ttu-id="ea091-171">Ny information är nu tillgänglig för vissa datakällobjekt i den aktuella modellmappningen:</span><span class="sxs-lookup"><span data-stu-id="ea091-171">New information is now available for some data source items of the current model mapping:</span></span>

- <span data-ttu-id="ea091-172">Den faktiska tid som användes för att hämta data genom att använda datakällan</span><span class="sxs-lookup"><span data-stu-id="ea091-172">The actual time that was spent getting data by using the data source</span></span>
- <span data-ttu-id="ea091-173">Samma tid uttryckt i procent av den totala tid som användes för att köra hela modellmappningen</span><span class="sxs-lookup"><span data-stu-id="ea091-173">The same time expressed as a percentage of the total time that was spent running the whole model mapping</span></span>

![Körningstid på sidan modellmappningsdesigner](./media/er-calculated-field-ds-performance-mapping-2.png)

<span data-ttu-id="ea091-175">Rutnätet **Prestandastatistik** visar att datakällan **Trans** anropar VendTrans-registret en gång.</span><span class="sxs-lookup"><span data-stu-id="ea091-175">The **Performance statistics** grid shows that the **Trans** data source calls the VendTrans table one time.</span></span> <span data-ttu-id="ea091-176">Värdet **\[265\]\[Q:265\]** för datakällan **Trans** anger att 265 leverantörstransaktioner har hämtats från appregistret och återgått till datamodellen.</span><span class="sxs-lookup"><span data-stu-id="ea091-176">The value **\[265\]\[Q:265\]** of the **Trans** data source indicates that 265 vendor transactions have been fetched from the application table and returned to the data model.</span></span>

<span data-ttu-id="ea091-177">I rutnätet **Prestandastatistik** visas också att den aktuella modellmappningen duplicerar databas begäran när datakällan **\#Vend** körs.</span><span class="sxs-lookup"><span data-stu-id="ea091-177">The **Performance statistics** grid also shows that the current model mapping duplicates database requests while the **\#Vend** data source is run.</span></span> <span data-ttu-id="ea091-178">Denna dubblering sker på grund av följande:</span><span class="sxs-lookup"><span data-stu-id="ea091-178">This duplication occurs for the following reasons:</span></span>

- <span data-ttu-id="ea091-179">Leverantörsregistret kallas två gånger för var och en av de 265 upprepade leverantörstransaktionerna, för totalt 530 samtal:</span><span class="sxs-lookup"><span data-stu-id="ea091-179">The vendor table is called two times for each of the 265 iterated vendor transactions, for a total of 530 calls:</span></span>

    - <span data-ttu-id="ea091-180">Ett samtal görs för att ange leverantörskontonumret.</span><span class="sxs-lookup"><span data-stu-id="ea091-180">One call is made to enter the vendor account number.</span></span>
    - <span data-ttu-id="ea091-181">Ett samtal görs för att ange leverantörsnamnet.</span><span class="sxs-lookup"><span data-stu-id="ea091-181">One call is made to enter the vendor name.</span></span>

- <span data-ttu-id="ea091-182">Leverantörsregistret anropas för varje förbrukad leverantörstransaktion även om de hämtade transaktionerna bara har bokförts för fem leverantörer.</span><span class="sxs-lookup"><span data-stu-id="ea091-182">The vendor table is called for each iterated vendor transaction, even though the fetched transactions have been posted for only five vendors.</span></span> <span data-ttu-id="ea091-183">Av 530 samtal, 525 är dubbletter.</span><span class="sxs-lookup"><span data-stu-id="ea091-183">Of the 530 calls, 525 are duplicates.</span></span> <span data-ttu-id="ea091-184">Följande illustration visar meddelandet som du får om att ringa upp (databas begäran).</span><span class="sxs-lookup"><span data-stu-id="ea091-184">The following illustration shows the message that you receive about duplicate calls (database requests).</span></span>

![Meddelande om dubbla databasbegäranden på sidan modellmappningsdesigner](./media/er-calculated-field-ds-performance-mapping-2a.png)

<span data-ttu-id="ea091-186">För den totala modellmappningens körningstid (ungefär åtta sekunder), lägg märke till att mer än 80 procent (cirka sex sekunder) har hämtats till värden från apptabellen för VendTable.</span><span class="sxs-lookup"><span data-stu-id="ea091-186">Of the total model mapping execution time (approximately eight seconds), notice that more than 80 percent (approximately six seconds) has been spent retrieving values from the VendTable application table.</span></span> <span data-ttu-id="ea091-187">Procentandelen är för stor för två attribut för fem leverantörer, jämfört med mängden information från apptabellen VendTrans.</span><span class="sxs-lookup"><span data-stu-id="ea091-187">That percentage is too large for two attributes of five vendors, compared with the volume of information from the VendTrans application table.</span></span>

<span data-ttu-id="ea091-188">Om du vill minska antalet samtal som görs för att hämta leverantörsinformation för varje transaktion och förbättra modellmappningens prestanda, kan du använda cachelagring för datakällan **\#Vend**.</span><span class="sxs-lookup"><span data-stu-id="ea091-188">To reduce the number of calls that are made to get the vendor details for every transaction, and to improve the performance of the model mapping, you can use caching for the **\#Vend** data source.</span></span>

> [!NOTE]
> <span data-ttu-id="ea091-189">Datakällan **Trans\\\#Vend** cachelagras i omfånget för den aktuella transaktionen i datakällan **Trans** vid körning.</span><span class="sxs-lookup"><span data-stu-id="ea091-189">The **Trans\\\#Vend** data source will be cached in the scope of the current transaction of the **Trans** data source at runtime.</span></span>

<span data-ttu-id="ea091-190">Genom att cachelagra datakällan **\#Vend** minskar du antalet duplicerade samtal från 525 till 260, men du eliminerar inte dubbletterna helt.</span><span class="sxs-lookup"><span data-stu-id="ea091-190">By caching the **\#Vend** data source, you reduce the number of duplicated calls from 525 to 260, but you don't completely eliminate the duplication.</span></span> <span data-ttu-id="ea091-191">Om du vill ta bort duplicering helt kan du konfigurera en ny parametriserad datakälla för typen **beräknade fält**.</span><span class="sxs-lookup"><span data-stu-id="ea091-191">To completely eliminate duplication, you can configure a new parameterized data source of the **Calculated field** type.</span></span>

## <a name="improve-the-model-mapping-based-on-information-from-the-execution-trace"></a><span data-ttu-id="ea091-192">Förbättra modellmappningen utifrån information från körningsspårningen</span><span class="sxs-lookup"><span data-stu-id="ea091-192">Improve the model mapping based on information from the execution trace</span></span>

### <a name="change-the-logic-of-the-model-mapping"></a><span data-ttu-id="ea091-193">Ändra logiken för modellmappningen</span><span class="sxs-lookup"><span data-stu-id="ea091-193">Change the logic of the model mapping</span></span>

<span data-ttu-id="ea091-194">Gör så här om du vill använda cachelagring och en datakälla för typen **beräknat fält** för att förhindra att samtal till databasen dubbleras.</span><span class="sxs-lookup"><span data-stu-id="ea091-194">Follow these steps to use caching and a data source of the **Calculated field** type, to help prevent duplicate calls to the database.</span></span>

1. <span data-ttu-id="ea091-195">På sidan **konfigurationer** i konfigurationsträdet väljer du artikeln **Prestandaförbättringsmappning**.</span><span class="sxs-lookup"><span data-stu-id="ea091-195">On the **Configurations** page, in the configuration tree, select **Performance improvement mapping**.</span></span>
2. <span data-ttu-id="ea091-196">Klicka på **Designer** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="ea091-196">On the Action Pane, select **Designer**.</span></span>
3. <span data-ttu-id="ea091-197">På sidan **Modellmappning** i åtgärdsfönstret, välj **Designer**.</span><span class="sxs-lookup"><span data-stu-id="ea091-197">On the **Model mappings** page, on the Action Pane, select **Designer**.</span></span>
4. <span data-ttu-id="ea091-198">På sidan **modellmappningsdesigner** följer du dessa steg för att lägga till en datakälla för typen **Tabellregister** för åtkomst till poster i VendTable-appregistret:</span><span class="sxs-lookup"><span data-stu-id="ea091-198">On the **Model mapping designer** page, follow these steps to add a data source of the **Table records** type to access records in the VendTable application table:</span></span>

    1. <span data-ttu-id="ea091-199">I fönstret **Datakälltyper** expandera **Dynamics 365 for Operations** och välj **registerposter**.</span><span class="sxs-lookup"><span data-stu-id="ea091-199">In the **Data source types** pane, expand **Dynamics 365 for Operations**, and select **Table records**.</span></span>
    2. <span data-ttu-id="ea091-200">Välj **Lägg till rot**.</span><span class="sxs-lookup"><span data-stu-id="ea091-200">Select **Add root**.</span></span>
    3. <span data-ttu-id="ea091-201">I dialogrutan i fältet **Namn**, ange **Vend**.</span><span class="sxs-lookup"><span data-stu-id="ea091-201">In the dialog box, in the **Name** field, enter **Vend**.</span></span>
    4. <span data-ttu-id="ea091-202">I fältet **Tabell** ange **VendTable**.</span><span class="sxs-lookup"><span data-stu-id="ea091-202">In the **Table** field, enter **VendTable**.</span></span>
    5. <span data-ttu-id="ea091-203">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="ea091-203">Select **OK**.</span></span>

5. <span data-ttu-id="ea091-204">Du kan endast parameteranrop till datakällor av typen **beräknat fält** om dessa datakällor finns i en behållare.</span><span class="sxs-lookup"><span data-stu-id="ea091-204">You can parameterize calls to data sources of the **Calculated field** type only if those data sources reside in a container.</span></span> <span data-ttu-id="ea091-205">Följ därför dessa steg för att lägga till en datakälla för typen **tomma behållare** för att lagra en ny parametriserad datakälla för typen **beräknat fält**:</span><span class="sxs-lookup"><span data-stu-id="ea091-205">Therefore, follow these steps to add a data source of the **Empty container** type to hold a new parameterized data source of the **Calculated field** type:</span></span>

    1. <span data-ttu-id="ea091-206">I fönstret **Datakälltyper** expandera **Allmän** och välj **Töm behållare**.</span><span class="sxs-lookup"><span data-stu-id="ea091-206">In the **Data source types** pane, expand **General**, and select **Empty container**.</span></span>
    2. <span data-ttu-id="ea091-207">Välj **Lägg till rot**.</span><span class="sxs-lookup"><span data-stu-id="ea091-207">Select **Add root**.</span></span>
    3. <span data-ttu-id="ea091-208">I dialogrutan i fältet **Namn**, ange **Ruta**.</span><span class="sxs-lookup"><span data-stu-id="ea091-208">In the dialog box, in the **Name** field, enter **Box**.</span></span>
    3. <span data-ttu-id="ea091-209">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="ea091-209">Select **OK**.</span></span>

    ![Ruta datakälla på sidan för modellmappningsdesigner](./media/er-calculated-field-ds-performance-mapping-3.png)

6. <span data-ttu-id="ea091-211">Följ dessa steg för att lägga till en parameteriserad datakälla för typen **beräknat fält**:</span><span class="sxs-lookup"><span data-stu-id="ea091-211">Follow these steps to add a parameterized data source of the **Calculated field** type:</span></span>

    1. <span data-ttu-id="ea091-212">I fönstret **datakällor** välj **ruta**.</span><span class="sxs-lookup"><span data-stu-id="ea091-212">In the **Data sources** pane, select **Box**.</span></span>
    2. <span data-ttu-id="ea091-213">I fönstret **datakälltyper** expanderar du **funktioner** och markerar **beräknade fält**.</span><span class="sxs-lookup"><span data-stu-id="ea091-213">In the **Data source types** pane, expand **Functions**, and select **Calculated field**.</span></span>
    3. <span data-ttu-id="ea091-214">Markera **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="ea091-214">Select **Add**.</span></span>
    4. <span data-ttu-id="ea091-215">I dialogrutan i fältet **Namn**, ange **Vend**.</span><span class="sxs-lookup"><span data-stu-id="ea091-215">In the dialog box, in the **Name** field, enter **Vend**.</span></span>
    5. <span data-ttu-id="ea091-216">Välj **Redigera recept**.</span><span class="sxs-lookup"><span data-stu-id="ea091-216">Select **Edit formula**.</span></span>
    6. <span data-ttu-id="ea091-217">På sidan **Formeldesigner** välj **Parametrar** för att ange vilka parametrar som måste anges när denna datakälla anropas.</span><span class="sxs-lookup"><span data-stu-id="ea091-217">On the **Formula designer** page, select **Parameters** to specify the parameters that must be provided when this data source is called.</span></span>
    7. <span data-ttu-id="ea091-218">I dialogrutan **Parametrar** välj **Ny**.</span><span class="sxs-lookup"><span data-stu-id="ea091-218">In the **Parameters** dialog box, select **New**.</span></span>
    8. <span data-ttu-id="ea091-219">I fältet **Namn** anger du **parmVendAccNumber**.</span><span class="sxs-lookup"><span data-stu-id="ea091-219">In the **Name** field, enter **parmVendAccNumber**.</span></span>
    9. <span data-ttu-id="ea091-220">Välj **Typ** i fältet **Artikeltyp**.</span><span class="sxs-lookup"><span data-stu-id="ea091-220">In the **Type** field, select **String**.</span></span>
    10. <span data-ttu-id="ea091-221">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="ea091-221">Select **OK**.</span></span>
    11. <span data-ttu-id="ea091-222">I fältet **Formel** anger du **FIRSTORNULL(FILTER(Vend, Vend.AccountNum=parmVendAccNumber))**.</span><span class="sxs-lookup"><span data-stu-id="ea091-222">In the **Formula** field, enter **FIRSTORNULL(FILTER(Vend, Vend.AccountNum=parmVendAccNumber))**.</span></span>
    12. <span data-ttu-id="ea091-223">Stäng sidan **Spara** och **Formeldesigner**.</span><span class="sxs-lookup"><span data-stu-id="ea091-223">Select **Save**, and close the **Formula designer** page.</span></span>
    13. <span data-ttu-id="ea091-224">Klicka på **OK** om du vill lägga till den nya datakällan.</span><span class="sxs-lookup"><span data-stu-id="ea091-224">Select **OK** to add the new data source.</span></span>

7. <span data-ttu-id="ea091-225">Markera den tillagda datakällan som cachelagrad under körningen genom att följa stegen nedan:</span><span class="sxs-lookup"><span data-stu-id="ea091-225">Follow these steps to mark the added data source as cached during the execution:</span></span>

    1. <span data-ttu-id="ea091-226">I **Datakällor** välj **Box\\Vend**.</span><span class="sxs-lookup"><span data-stu-id="ea091-226">In the **Data sources** pane, select **Box\\Vend**.</span></span>
    2. <span data-ttu-id="ea091-227">Välj **cache**.</span><span class="sxs-lookup"><span data-stu-id="ea091-227">Select **Cache**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="ea091-228">Datakällan **Box\\Vend** cachelagras i omfånget för alla leverantörstransaktionen i datakällan **Trans** vid körning.</span><span class="sxs-lookup"><span data-stu-id="ea091-228">The **Box\\Vend** data source will be cached in the scope of all vendor transactions of the **Trans** data source at runtime.</span></span>

8. <span data-ttu-id="ea091-229">Följ dessa steg för att uppdatera den kapslade datakällan **Trans\\\#Vend** så att den använder fältet datakälla **Box\\Vend**:</span><span class="sxs-lookup"><span data-stu-id="ea091-229">Follow these steps to update the nested **Trans\\\#Vend** data source so that it uses the **Box\\Vend** data source:</span></span>

    1. <span data-ttu-id="ea091-230">Välj **Stödprocess** i fönstret expandera **Trans**.</span><span class="sxs-lookup"><span data-stu-id="ea091-230">In the **Data sources** pane, expand **Trans**.</span></span>
    2. <span data-ttu-id="ea091-231">Markera den datakällan **Trans\\\#Vend** och välj **Redigera** \> **Redigera recept**.</span><span class="sxs-lookup"><span data-stu-id="ea091-231">Select the **Trans\\\#Vend** data source, and then select **Edit** \> **Edit formula**.</span></span>
    3. <span data-ttu-id="ea091-232">På sidan **Formeldesigner** i fältet **Formel** ange **Box.Vend(\@.AccountNum)**.</span><span class="sxs-lookup"><span data-stu-id="ea091-232">On the **Formula designer** page, in the **Formula** field, enter **Box.Vend(\@.AccountNum)**.</span></span>
    4. <span data-ttu-id="ea091-233">Välj **Spara** och stäng sedan sidan **Formeldesigner**.</span><span class="sxs-lookup"><span data-stu-id="ea091-233">Select **Save**, and then close the **Formula designer** page.</span></span>
    5. <span data-ttu-id="ea091-234">Klicka på **OK** om du vill slutföra ändringarna i den valda datakällan.</span><span class="sxs-lookup"><span data-stu-id="ea091-234">Select **OK** to complete your changes to the selected data source.</span></span>

9. <span data-ttu-id="ea091-235">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="ea091-235">Select **Save**.</span></span>

    ![Vend datakälla på sidan för modellmappningsdesigner](./media/er-calculated-field-ds-performance-mapping-4.png)

10. <span data-ttu-id="ea091-237">Stäng sidan **modellmappningsdesigner**.</span><span class="sxs-lookup"><span data-stu-id="ea091-237">Close the **Model mapping designer** page.</span></span>
11. <span data-ttu-id="ea091-238">Stäng sidan **modellmappningar**.</span><span class="sxs-lookup"><span data-stu-id="ea091-238">Close the **Model mappings** page.</span></span>

### <a name="complete-the-modified-version-of-the-er-model-mapping"></a><span data-ttu-id="ea091-239">Slutför den ändrade versionen av ER-modellmappningen</span><span class="sxs-lookup"><span data-stu-id="ea091-239">Complete the modified version of the ER model mapping</span></span>

1. <span data-ttu-id="ea091-240">På sidan **Konfigurationer** på snabbfliken **Versioner** FastTab, välj version **1.2** av konfigurationen **prestandaförbättringsmappning**.</span><span class="sxs-lookup"><span data-stu-id="ea091-240">On the **Configurations** page, on the **Versions** FastTab, select version **1.2** of the **Performance improvement mapping** configuration.</span></span>
2. <span data-ttu-id="ea091-241">Välj **Ändra status** \> **Slutför** och välj sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="ea091-241">Select **Change status** \> **Complete**, and then select **OK**.</span></span>

## <a name="run-the-modified-er-solution-to-trace-execution"></a><span data-ttu-id="ea091-242">Kör modifierad ER-lösning för att spåra körning</span><span class="sxs-lookup"><span data-stu-id="ea091-242">Run the modified ER solution to trace execution</span></span>

<span data-ttu-id="ea091-243">Upprepa stegen i avsnittet [kör ER-format](#run-format) tidigare i det här avsnittet om du vill generera en ny prestandaspårning.</span><span class="sxs-lookup"><span data-stu-id="ea091-243">Repeat the steps in the [Run the ER format](#run-format) section earlier in this topic to generate a new performance trace.</span></span>

## <a name="use-the-performance-trace-to-analyze-adjustments-to-the-model-mapping"></a><span data-ttu-id="ea091-244">Använd prestandaspårning för att analysera justeringar till modellmappning</span><span class="sxs-lookup"><span data-stu-id="ea091-244">Use the performance trace to analyze adjustments to the model mapping</span></span> 

1. <span data-ttu-id="ea091-245">På sidan **konfigurationer** i konfigurationsträdet väljer du artikeln **Prestandaförbättringsmappning**.</span><span class="sxs-lookup"><span data-stu-id="ea091-245">On the **Configurations** page, in the configuration tree, select **Performance improvement mapping**.</span></span>
2. <span data-ttu-id="ea091-246">Klicka på **Designer** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="ea091-246">On the Action Pane, select **Designer**.</span></span>
3. <span data-ttu-id="ea091-247">På sidan **Modellmappning** i åtgärdsfönstret, välj **Designer**.</span><span class="sxs-lookup"><span data-stu-id="ea091-247">On the **Model mappings** page, on the Action Pane, select **Designer**.</span></span>
4. <span data-ttu-id="ea091-248">På snabbfliken **Modellmappningsdesigner** på åtgärdsfönstret väljer du **Prestandaspårningsformat**.</span><span class="sxs-lookup"><span data-stu-id="ea091-248">On the **Model mapping designer** page, on the Action Pane, select **Performance trace**.</span></span>
5. <span data-ttu-id="ea091-249">Markera den senaste spårningen som genererades och välj sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="ea091-249">Select the most recent trace that was generated, and then select **OK**.</span></span>

<span data-ttu-id="ea091-250">Observera att justeringarna som du har gjort av modellmappningen har eliminerat dubbla frågor till databasen.</span><span class="sxs-lookup"><span data-stu-id="ea091-250">Notice that the adjustments that you made to the model mapping have eliminated duplicate queries to database.</span></span> <span data-ttu-id="ea091-251">Antalet anrop till databasregister och datakällor för den här modellmappningen har också minskats.</span><span class="sxs-lookup"><span data-stu-id="ea091-251">The number of calls to database tables and data sources for this model mapping has also been reduced.</span></span>

![Spåra information på sidan för modellmappningsdesigner 1](./media/er-calculated-field-ds-performance-mapping-5.png)

<span data-ttu-id="ea091-253">Den totala körningstiden har reducerats omkring 20 gånger (från cirka 8 sekunder till cirka 400 millisekunder).</span><span class="sxs-lookup"><span data-stu-id="ea091-253">The total execution time has been reduced about 20 times (from about 8 seconds to about 400 milliseconds).</span></span> <span data-ttu-id="ea091-254">Därför har hela ER-lösningens prestanda förbättrats.</span><span class="sxs-lookup"><span data-stu-id="ea091-254">Therefore, the performance of the whole ER solution has been improved.</span></span>

![Spåra information på sidan för modellmappningsdesigner 2](./media/er-calculated-field-ds-performance-mapping-5a.png)

## <a name="appendix-1-download-the-components-of-the-sample-microsoft-er-solution"></a><a name="appendix1"></a><span data-ttu-id="ea091-256">Tillägg 1: Hämta komponenterna i exemplet Microsoft ER-lösning</span><span class="sxs-lookup"><span data-stu-id="ea091-256">Appendix 1: Download the components of the sample Microsoft ER solution</span></span>

<span data-ttu-id="ea091-257">Du måste ladda ner följande filer och lagra dem lokalt.</span><span class="sxs-lookup"><span data-stu-id="ea091-257">You must download the following files and store them locally.</span></span>

| <span data-ttu-id="ea091-258">Fil</span><span class="sxs-lookup"><span data-stu-id="ea091-258">File</span></span>                                        | <span data-ttu-id="ea091-259">Innehåll</span><span class="sxs-lookup"><span data-stu-id="ea091-259">Content</span></span> |
|---------------------------------------------|---------|
| <span data-ttu-id="ea091-260">Prestandaförbättringsmodell.version.1</span><span class="sxs-lookup"><span data-stu-id="ea091-260">Performance improvement model.version.1</span></span>     | [<span data-ttu-id="ea091-261">Konfiguration av exempel på ER-datamodell.</span><span class="sxs-lookup"><span data-stu-id="ea091-261">Sample ER data model configuration</span></span>](https://mbs.microsoft.com/customersource/Global/AX/downloads/hot-fixes/365optelecrepeg) |
| <span data-ttu-id="ea091-262">Prestandaförbättringsmappning.version.1.1</span><span class="sxs-lookup"><span data-stu-id="ea091-262">Performance improvement mapping.version.1.1</span></span> | [<span data-ttu-id="ea091-263">Konfiguration av exempel på ER-modellmappning</span><span class="sxs-lookup"><span data-stu-id="ea091-263">Sample ER model mapping configuration</span></span>](https://mbs.microsoft.com/customersource/Global/AX/downloads/hot-fixes/365optelecrepeg) |
| <span data-ttu-id="ea091-264">Prestandaförbättringsformat.version.1.1</span><span class="sxs-lookup"><span data-stu-id="ea091-264">Performance improvement format.version.1.1</span></span>  | [<span data-ttu-id="ea091-265">Konfiguration av exempel på ER-format.</span><span class="sxs-lookup"><span data-stu-id="ea091-265">Sample ER format configuration</span></span>](https://mbs.microsoft.com/customersource/Global/AX/downloads/hot-fixes/365optelecrepeg) |

## <a name="appendix-2-configure-the-er-framework"></a><a name="appendix2"></a><span data-ttu-id="ea091-266">Bilaga 2: Konfigurera ER-ramverket</span><span class="sxs-lookup"><span data-stu-id="ea091-266">Appendix 2: Configure the ER framework</span></span>

<span data-ttu-id="ea091-267">Innan du kan börja använda ER-ramverket för att förbättra prestanda i exempel Microsoft ER-lösningen måste du konfigurera den minsta uppsättningen ER-parametrar.</span><span class="sxs-lookup"><span data-stu-id="ea091-267">Before you can start to use the ER framework to improve the performance of the sample Microsoft ER solution, you must configure the minimal set of ER parameters.</span></span>

### <a name="configure-er-parameters"></a><a id="ConfigureParameters"></a><span data-ttu-id="ea091-268">Konfigurera ER-parametrar</span><span class="sxs-lookup"><span data-stu-id="ea091-268">Configure ER parameters</span></span>

1. <span data-ttu-id="ea091-269">Gå till **Organisationsadministration** \> **Arbetsytor** \> **Elektronisk rapportering**.</span><span class="sxs-lookup"><span data-stu-id="ea091-269">Go to **Organization administration** \> **Workspaces** \> **Electronic reporting**.</span></span>
2. <span data-ttu-id="ea091-270">På sidan **lokaliseringskonfiguration** i avsnittet **Relaterade länkar** väljer du **parametrar för elektronisk rapportering**.</span><span class="sxs-lookup"><span data-stu-id="ea091-270">On the **Localization configurations** page, in the **Related links** section, select **Electronic reporting parameters**.</span></span>
3. <span data-ttu-id="ea091-271">På sidan **parametrar för elektronisk rapportering** på fliken **allmänna** anger du alternativet till **aktivera designläge** till **Ja**.</span><span class="sxs-lookup"><span data-stu-id="ea091-271">On the **Electronic reporting parameters** page, on the **General** tab, set the **Enable design mode** option to **Yes**.</span></span>
4. <span data-ttu-id="ea091-272">Ange följande parametrar på fliken **Bilagor**:</span><span class="sxs-lookup"><span data-stu-id="ea091-272">On the **Attachments** tab, set the following parameters:</span></span>

    - <span data-ttu-id="ea091-273">I fältet **Konfigurationer** välj typen **Fil** för **DEMF**-företaget.</span><span class="sxs-lookup"><span data-stu-id="ea091-273">In the **Configurations** field, select the **File** type for the **DEMF** company.</span></span>
    - <span data-ttu-id="ea091-274">I fältet **Jobbarkiv**, **Tillfälliga**, **Baslinje** och **Andra** och välj typen **Fil**.</span><span class="sxs-lookup"><span data-stu-id="ea091-274">In the **Job archive**, **Temporary**, **Baseline**, and **Others** fields, select the **File** type.</span></span>

<span data-ttu-id="ea091-275">Mer information om ER-parametrar finns i [Konfigurera om ER-ramverket](electronic-reporting-er-configure-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="ea091-275">For more information about ER parameters, see [Configure the ER framework](electronic-reporting-er-configure-parameters.md).</span></span>

### <a name="activate-an-er-configuration-provider"></a><a id="ActivateProvider"></a><span data-ttu-id="ea091-276">Aktivera en ER-konfigurationsleverantör</span><span class="sxs-lookup"><span data-stu-id="ea091-276">Activate an ER configuration provider</span></span>

<span data-ttu-id="ea091-277">Varje ER-konfiguration som läggs till markeras som ägd av en ER-konfigurationsleverantör.</span><span class="sxs-lookup"><span data-stu-id="ea091-277">Every ER configuration that is added is marked as owned by an ER configuration provider.</span></span> <span data-ttu-id="ea091-278">Den ER-konfigurationsleverantör för ER som aktiveras i arbetsytan **Elektronisk rapportering** används för det här syftet.</span><span class="sxs-lookup"><span data-stu-id="ea091-278">The ER configuration provider that is activated in the **Electronic reporting** workspace is used for this purpose.</span></span> <span data-ttu-id="ea091-279">Därför måste du aktivera en ER-konfigurationsleverantör i arbetsytan **Elektronisk rapportering** innan du börjar lägga till eller redigera ER-konfigurationer.</span><span class="sxs-lookup"><span data-stu-id="ea091-279">Therefore, you must activate an ER configuration provider in the **Electronic reporting** workspace before you start to add or edit ER configurations.</span></span>

> [!NOTE]
> <span data-ttu-id="ea091-280">Endast ägaren till en ER-konfiguration kan redigera konfigurationen.</span><span class="sxs-lookup"><span data-stu-id="ea091-280">Only the owner of an ER configuration can edit the configuration.</span></span> <span data-ttu-id="ea091-281">Därför måste en lämplig ER-konfigurationsleverantör aktiveras innan en ER-konfiguration kan redigeras arbetsytan **Elektronisk rapportering**.</span><span class="sxs-lookup"><span data-stu-id="ea091-281">Therefore, before an ER configuration can be edited, the appropriate ER configuration provider must be activated in the **Electronic reporting** workspace.</span></span>

#### <a name="review-the-list-of-er-configuration-providers"></a><a id="ReviewProvidersList"></a><span data-ttu-id="ea091-282">Granska listan med ER-konfigurationsleverantörer</span><span class="sxs-lookup"><span data-stu-id="ea091-282">Review the list of ER configuration providers</span></span>

1. <span data-ttu-id="ea091-283">Gå till **Organisationsadministration** \> **Arbetsytor** \> **Elektronisk rapportering**.</span><span class="sxs-lookup"><span data-stu-id="ea091-283">Go to **Organization administration** \> **Workspaces** \> **Electronic reporting**.</span></span>
2. <span data-ttu-id="ea091-284">På sidan **lokaliseringskonfiguration** i avsnittet **Relaterade länkar** väljer du **Konfigurationsleverantörer**.</span><span class="sxs-lookup"><span data-stu-id="ea091-284">On the **Localization configurations** page, in the **Related links** section, select **Configuration providers**.</span></span>
3. <span data-ttu-id="ea091-285">På sidan **Tabellen konfigurationsleverantörer** har varje leverantörspost ett unikt namn och en URL.</span><span class="sxs-lookup"><span data-stu-id="ea091-285">On the **Configuration provider table** page, each provider record has a unique name and URL.</span></span> <span data-ttu-id="ea091-286">Granska innehållet på den här sidan.</span><span class="sxs-lookup"><span data-stu-id="ea091-286">Review the contents of this page.</span></span> <span data-ttu-id="ea091-287">Om det redan finns en post för **Litware, Inc.** hoppar du över nästa procedur [Lägg till en ny ER-konfigurationsleverantör](#ActivateProvider).</span><span class="sxs-lookup"><span data-stu-id="ea091-287">If a record for **Litware, Inc.** already exists, skip the next procedure, [Add a new ER configuration provider](#ActivateProvider).</span></span>

#### <a name="add-a-new-er-configuration-provider"></a><a id="ActivateProvider"></a><span data-ttu-id="ea091-288">Lägg till en ny ER-konfigurationsleverantör</span><span class="sxs-lookup"><span data-stu-id="ea091-288">Add a new ER configuration provider</span></span>

1. <span data-ttu-id="ea091-289">Gå till **Organisationsadministration** \> **Arbetsytor** \> **Elektronisk rapportering**.</span><span class="sxs-lookup"><span data-stu-id="ea091-289">Go to **Organization administration** \> **Workspaces** \> **Electronic reporting**.</span></span>
2. <span data-ttu-id="ea091-290">På sidan **lokaliseringskonfiguration** i avsnittet **Relaterade länkar** väljer du **Konfigurationsleverantörer**.</span><span class="sxs-lookup"><span data-stu-id="ea091-290">On the **Localization configurations** page, in the **Related links** section, select **Configuration providers**.</span></span>
3. <span data-ttu-id="ea091-291">Välj **Konfigurationsleverantörer** på sidan **Leveranssätt**.</span><span class="sxs-lookup"><span data-stu-id="ea091-291">On the **Configuration providers** page, select **New**.</span></span>
4. <span data-ttu-id="ea091-292">I fältet **Namn** anger du **Litware, Inc.**.</span><span class="sxs-lookup"><span data-stu-id="ea091-292">In the **Name** field, enter **Litware, Inc.**</span></span>
5. <span data-ttu-id="ea091-293">I fältet **Internetadress** anger du `https://www.litware.com`.</span><span class="sxs-lookup"><span data-stu-id="ea091-293">In the **Internet address** field, enter `https://www.litware.com`.</span></span>
6. <span data-ttu-id="ea091-294">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="ea091-294">Select **Save**.</span></span>

#### <a name="activate-an-er-configuration-provider"></a><a id="ActivateAddedProvider"></a><span data-ttu-id="ea091-295">Aktivera en ER-konfigurationsleverantörer</span><span class="sxs-lookup"><span data-stu-id="ea091-295">Activate an ER configuration provider</span></span>

1. <span data-ttu-id="ea091-296">Gå till **Organisationsadministration** \> **Arbetsytor** \> **Elektronisk rapportering**.</span><span class="sxs-lookup"><span data-stu-id="ea091-296">Go to **Organization administration** \> **Workspaces** \> **Electronic reporting**.</span></span>
2. <span data-ttu-id="ea091-297">På sidan **lokaliseringskonfiguration** i avsnittet **konfigurationsleverantörer** välj panelen **Litware, Inc.** och välj sedan **Ange aktiv**.</span><span class="sxs-lookup"><span data-stu-id="ea091-297">On the **Localization configurations** page, in the **Configuration providers** section, select the **Litware, Inc.** tile, and then select **Set active**.</span></span>

<span data-ttu-id="ea091-298">Mer information om ER-konfigurationsleverantörer finns i [Skapa konfigurationsleverantörer och markera dem som aktiva](tasks/er-configuration-provider-mark-it-active-2016-11.md).</span><span class="sxs-lookup"><span data-stu-id="ea091-298">For more information about ER configuration providers, see [Create configuration providers and mark them as active](tasks/er-configuration-provider-mark-it-active-2016-11.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="ea091-299">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="ea091-299">Additional resources</span></span>

- [<span data-ttu-id="ea091-300">Översikt över elektronisk rapportering</span><span class="sxs-lookup"><span data-stu-id="ea091-300">Electronic Reporting overview</span></span>](general-electronic-reporting.md)
- [<span data-ttu-id="ea091-301">Spåra körningen av ER-format för att felsöka prestandaproblem</span><span class="sxs-lookup"><span data-stu-id="ea091-301">Trace the execution of ER formats to troubleshoot performance issues</span></span>](trace-execution-er-troubleshoot-perf.md)
- [<span data-ttu-id="ea091-302">Stödparameteranrop till ER-datakällor för typen beräknat fält</span><span class="sxs-lookup"><span data-stu-id="ea091-302">Support parameterized calls of ER data sources of the Calculated field type</span></span>](er-calculated-field-type.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]