---
title: Spåringskörning av ER-format för att hjälpa dig att felsöka prestandaproblem.
description: Det här avsnittet innehåller information om hur du använder funktionen för prestandaspårning i elektronisk rapportering (ER) för att felsöka prestandaproblem.
author: NickSelin
manager: AnnBe
ms.date: 05/08/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 220314
ms.assetid: 2685df16-5ec8-4fd7-9495-c0f653e82567
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: ''
ms.dyn365.ops.version: 10.0.1
ms.openlocfilehash: aa71db2752889bc905c22bab1cf2fa46d7ee07c7
ms.sourcegitcommit: 67d00b95952faf0db580d341249d4e50be59119c
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/15/2019
ms.locfileid: "1576556"
---
# <a name="trace-the-execution-of-er-formats-to-troubleshoot-performance-issues"></a><span data-ttu-id="8d9bb-103">Spåra körning av ER-format för att felsöka prestanda problem</span><span class="sxs-lookup"><span data-stu-id="8d9bb-103">Trace the execution of ER formats to troubleshoot performance issues</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="8d9bb-104">Som en del i processen att utforma konfiguration av elektroniska rapporter (ER) för att generera elektroniska dokument, definierar du den metod som används för att hämta data från Microsoft Dynamics 365 for Finance and Operations och anger den i genererad utdata.</span><span class="sxs-lookup"><span data-stu-id="8d9bb-104">As part of the process of designing Electronic reporting (ER) configurations to generate electronic documents, you define the method that is used to get data out of Microsoft Dynamics 365 for Finance and Operations and enter it in the output that is generated.</span></span> <span data-ttu-id="8d9bb-105">Funktionen för ER-prestationsspårning hjälper till att avsevärt minska både tid och kostnad när det gäller att samla in information om ER-formatkörning och använda den för att felsöka prestandaproblem.</span><span class="sxs-lookup"><span data-stu-id="8d9bb-105">The ER performance trace feature helps significantly reduce the time and cost that are involved in collecting the details of ER format execution and using them to troubleshoot performance issues.</span></span> <span data-ttu-id="8d9bb-106">I den här självstudien finns riktlinjer för hur du utför prestandaspårning för körda ER-format i Finance and Operations och hur du använder informationen från dessa spårningar för att förbättra prestanda.</span><span class="sxs-lookup"><span data-stu-id="8d9bb-106">This tutorial provides guidelines about how to take performance traces for executed ER formats in Finance and Operations, and how to use the information from these traces to help improve performance.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="8d9bb-107">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="8d9bb-107">Prerequisites</span></span>

<span data-ttu-id="8d9bb-108">För att slutföra exemplet i den här självstudien måste du ha följande åtkomst:</span><span class="sxs-lookup"><span data-stu-id="8d9bb-108">To complete the examples in this tutorial, you must have the following access:</span></span>

- <span data-ttu-id="8d9bb-109">Gå till Finance and Operation för någon av följande roller:</span><span class="sxs-lookup"><span data-stu-id="8d9bb-109">Access to Finance and Operations for one of the following roles:</span></span>

    - <span data-ttu-id="8d9bb-110">Utvecklare för elektronisk rapportering</span><span class="sxs-lookup"><span data-stu-id="8d9bb-110">Electronic reporting developer</span></span>
    - <span data-ttu-id="8d9bb-111">Konsult för funktionen för elektronisk rapportering</span><span class="sxs-lookup"><span data-stu-id="8d9bb-111">Electronic reporting functional consultant</span></span>
    - <span data-ttu-id="8d9bb-112">Systemadministratör</span><span class="sxs-lookup"><span data-stu-id="8d9bb-112">System administrator</span></span>

- <span data-ttu-id="8d9bb-113">Åtkomst till den instans av Regulatory Configuration Services (RCS) som har etablerats för samma innehavare som Finance and Operations för en av följande roller:</span><span class="sxs-lookup"><span data-stu-id="8d9bb-113">Access to the instance of Regulatory Configuration Services (RCS) that has been provisioned for the same tenant as Finance and Operations, for one of the following roles:</span></span>

    - <span data-ttu-id="8d9bb-114">Utvecklare för elektronisk rapportering</span><span class="sxs-lookup"><span data-stu-id="8d9bb-114">Electronic reporting developer</span></span>
    - <span data-ttu-id="8d9bb-115">Konsult för funktionen för elektronisk rapportering</span><span class="sxs-lookup"><span data-stu-id="8d9bb-115">Electronic reporting functional consultant</span></span>
    - <span data-ttu-id="8d9bb-116">Systemadministratör</span><span class="sxs-lookup"><span data-stu-id="8d9bb-116">System administrator</span></span>

<span data-ttu-id="8d9bb-117">Du måste också hämta följande filer och lagra dem lokalt.</span><span class="sxs-lookup"><span data-stu-id="8d9bb-117">You must also download and locally store the following files.</span></span>

| <span data-ttu-id="8d9bb-118">Fil</span><span class="sxs-lookup"><span data-stu-id="8d9bb-118">File</span></span>                                  | <span data-ttu-id="8d9bb-119">Innehåll</span><span class="sxs-lookup"><span data-stu-id="8d9bb-119">Content</span></span>                               |
|---------------------------------------|---------------------------------------|
| <span data-ttu-id="8d9bb-120">Prestandaspårningsmodell.version. 1</span><span class="sxs-lookup"><span data-stu-id="8d9bb-120">Performance trace model.version.1</span></span>     | [<span data-ttu-id="8d9bb-121">Konfiguration av exempel på ER-datamodell.</span><span class="sxs-lookup"><span data-stu-id="8d9bb-121">Sample ER data model configuration</span></span>](https://mbs.microsoft.com/customersource/Global/AX/downloads/hot-fixes/365optelecrepeg)    |
| <span data-ttu-id="8d9bb-122">Prestandaspårningsmetadata.version.1</span><span class="sxs-lookup"><span data-stu-id="8d9bb-122">Performance trace metadata.version.1</span></span>  | [<span data-ttu-id="8d9bb-123">Konfiguration av exempel på ER-metadata.</span><span class="sxs-lookup"><span data-stu-id="8d9bb-123">Sample ER metadata configuration</span></span>](https://mbs.microsoft.com/customersource/Global/AX/downloads/hot-fixes/365optelecrepeg)      |
| <span data-ttu-id="8d9bb-124">Prestandaspårningsmappning.version.1.1</span><span class="sxs-lookup"><span data-stu-id="8d9bb-124">Performance trace mapping.version.1.1</span></span> | [<span data-ttu-id="8d9bb-125">Konfiguration av exempel på ER-modellmappning</span><span class="sxs-lookup"><span data-stu-id="8d9bb-125">Sample ER model mapping configuration</span></span>](https://mbs.microsoft.com/customersource/Global/AX/downloads/hot-fixes/365optelecrepeg) |
| <span data-ttu-id="8d9bb-126">Prestandaspårningsformat.version.1.1</span><span class="sxs-lookup"><span data-stu-id="8d9bb-126">Performance trace format.version.1.1</span></span>  | [<span data-ttu-id="8d9bb-127">Konfiguration av exempel på ER-format.</span><span class="sxs-lookup"><span data-stu-id="8d9bb-127">Sample ER format configuration</span></span>](https://mbs.microsoft.com/customersource/Global/AX/downloads/hot-fixes/365optelecrepeg)       |

### <a name="configure-er-parameters"></a><span data-ttu-id="8d9bb-128">Konfigurera ER-parametrar</span><span class="sxs-lookup"><span data-stu-id="8d9bb-128">Configure ER parameters</span></span>

<span data-ttu-id="8d9bb-129">Varje ER-prestandaspårning som skapas i Finance and Operations lagras som en bilaga till körningsloggposten.</span><span class="sxs-lookup"><span data-stu-id="8d9bb-129">Each ER performance trace that is generated in Finance and Operations is stored as an attachment of the execution log record.</span></span> <span data-ttu-id="8d9bb-130">Dokumenthanteringsramverket (DM) för Finance and Operations används för att hantera dessa bilagor.</span><span class="sxs-lookup"><span data-stu-id="8d9bb-130">The Document management (DM) framework of Finance and Operations is used to manage these attachments.</span></span> <span data-ttu-id="8d9bb-131">Du måste konfigurera återställningsparametrar i förväg för att kunna ange vilken typ av DM-dokument som ska användas för att koppla prestandaspårningar.</span><span class="sxs-lookup"><span data-stu-id="8d9bb-131">You must configure ER parameters in advance, to specify the DM document type that should be used to attach performance traces.</span></span> <span data-ttu-id="8d9bb-132">I Finance and Operations, i arbetsytan **elektronisk rapportering** väljer du **parametrar för elektronisk rapportering**.</span><span class="sxs-lookup"><span data-stu-id="8d9bb-132">In Finance and Operation, in the **Electronic reporting** workspace, select **Electronic reporting parameters**.</span></span> <span data-ttu-id="8d9bb-133">Välj sedan sidan **parametrar för elektronisk rapportering** på fliken **bilagor** i fältet **övriga** och sedan den DM-dokumenttyp som du ska använda för prestandaspårning.</span><span class="sxs-lookup"><span data-stu-id="8d9bb-133">Then, on the **Electronic reporting parameters** page, on the **Attachments** tab, in the **Others** field, select the DM document type to use for performance traces.</span></span>

![Sidan parametrar för elektronisk rapportering i Finance and Operations](./media/GER-PerfTrace-GER-Parameters-DocumentType.png)

<span data-ttu-id="8d9bb-135">För att vara tillgänglig i sökfältet **Övriga** måste en DM-dokumenttyp konfigureras på följande sätt på sidan **Dokumenttyper** (**Organisationsadministration \> Dokumenthantering \> Dokumenttyper**):</span><span class="sxs-lookup"><span data-stu-id="8d9bb-135">To be available in the **Others** lookup field, a DM document type must be configured in the following manner on the **Document types** page (**Organization administration \> Document management \> Document types**):</span></span>

- <span data-ttu-id="8d9bb-136">**Klass:** Bifoga fil</span><span class="sxs-lookup"><span data-stu-id="8d9bb-136">**Class:** Attach file</span></span>
- <span data-ttu-id="8d9bb-137">**Grupp:** fil</span><span class="sxs-lookup"><span data-stu-id="8d9bb-137">**Group:** File</span></span>

![Sidan dokumenttyper i Finance and Operations](./media/GER-PerfTrace-DM-DocumentType.png)

> [!NOTE]
> <span data-ttu-id="8d9bb-139">Den valda dokumenttypen måste vara tillgänglig i alla företag i den aktuella Finance and Operations-instansen eftersom DM-bilagor är företagsspecifika.</span><span class="sxs-lookup"><span data-stu-id="8d9bb-139">The selected document type must be available in every company of the current Finance and Operations instance, because DM attachments are company-specific.</span></span>

### <a name="configure-rcs-parameters"></a><span data-ttu-id="8d9bb-140">Konfigurera RCS-parametrar</span><span class="sxs-lookup"><span data-stu-id="8d9bb-140">Configure RCS parameters</span></span>

<span data-ttu-id="8d9bb-141">ER-prestandaspårningar som skapas i Finance and Operations importeras till RCS för analys med hjälp av ERformatdesigner och ER-mappningsdesigner.</span><span class="sxs-lookup"><span data-stu-id="8d9bb-141">ER performance traces that are generated in Finance and Operations will be imported into RCS for analysis by using the ER format designer and the ER mapping designer.</span></span> <span data-ttu-id="8d9bb-142">Eftersom ER-prestandaspårning lagras som bilagor till körningsloggposten som är relaterad till ER-formatet, måste du konfigurera RCS-parametrar i förväg för att ange den DM-dokumenttyp som ska användas för att koppla prestandaspårningar.</span><span class="sxs-lookup"><span data-stu-id="8d9bb-142">Because ER performance traces are stored as attachments of the execution log record that is related to the ER format, you must configure RCS parameters in advance, to specify the DM document type that should be used to attach performance traces.</span></span> <span data-ttu-id="8d9bb-143">elektronisk I instansen av RCS som har etablerats för ditt företag, i arbetsytan **elektronisk rapportering** väljer du **elektronisk rapportering**.</span><span class="sxs-lookup"><span data-stu-id="8d9bb-143">In the instance of RCS that has been provisioned for your company, in the **Electronic reporting** workspace, select **Electronic reporting parameters**.</span></span> <span data-ttu-id="8d9bb-144">Välj sedan sidan **parametrar för elektronisk rapportering** på fliken **bilagor** i fältet **övriga** och sedan den DM-dokumenttyp som du ska använda för prestandaspårning.</span><span class="sxs-lookup"><span data-stu-id="8d9bb-144">Then, on the **Electronic reporting parameters** page, on the **Attachments** tab, in the **Others** field, select the DM document type to use for performance traces.</span></span>

![Sida för parametrar för elektronisk rapportering i RCS](./media/GER-PerfTrace-RCS-Parameters-DocumentType.png)

<span data-ttu-id="8d9bb-146">För att vara tillgänglig i sökfältet **Övriga** måste en DM-dokumenttyp konfigureras på följande sätt på sidan **Dokumenttyper** (**Organisationsadministration \> Dokumenthantering \> Dokumenttyper**):</span><span class="sxs-lookup"><span data-stu-id="8d9bb-146">To be available in the **Others** lookup field, a DM document type must be configured in the following manner on the **Document types** page (**Organization administration \> Document management \> Document types**):</span></span>

- <span data-ttu-id="8d9bb-147">**Klass:** Bifoga fil</span><span class="sxs-lookup"><span data-stu-id="8d9bb-147">**Class:** Attach file</span></span>
- <span data-ttu-id="8d9bb-148">**Grupp:** fil</span><span class="sxs-lookup"><span data-stu-id="8d9bb-148">**Group:** File</span></span>

## <a name="design-an-er-solution"></a><span data-ttu-id="8d9bb-149">Designa en ER-lösning</span><span class="sxs-lookup"><span data-stu-id="8d9bb-149">Design an ER solution</span></span>

<span data-ttu-id="8d9bb-150">Anta att du har börjat designa en ny ER-lösning för att skapa en ny rapport som visar leverantörstransaktioner.</span><span class="sxs-lookup"><span data-stu-id="8d9bb-150">Assume that you've started to design a new ER solution to generate a new report that presents vendor transactions.</span></span> <span data-ttu-id="8d9bb-151">För närvarande kan du hitta transaktionerna för en vald leverantör på sidan **leverantörstransaktioner** (gå till **leverantörsreskontra\> leverantörer \> alla leverantörer**, välj en leverantörer och sedan i åtgärdspanelen på fliken **leverantörer** i gruppen **transaktioner** väljer du **transaktioner**).</span><span class="sxs-lookup"><span data-stu-id="8d9bb-151">Currently, you can find the transactions for a selected vendor on the **Vendor transactions** page (go to **Account payable \> Vendors \> All vendors**, select a vendor, and then, on the Action Pane, on the **Vendor** tab, in the **Transactions** group, select **Transactions**).</span></span> <span data-ttu-id="8d9bb-152">Du vill dock ha alla leverantörstransaktioner samtidigt i ett elektroniskt dokument i XML-format.</span><span class="sxs-lookup"><span data-stu-id="8d9bb-152">However, you want to have all vendor transaction at the same time in one electronic document in XML format.</span></span> <span data-ttu-id="8d9bb-153">Den här lösningen består av flera ER-konfigurationer som innehåller den nödvändiga datamodellen, metadata, modellmappning och formatkomponenter.</span><span class="sxs-lookup"><span data-stu-id="8d9bb-153">This solution will consist of several ER configurations that contain the required data model, metadata, model mapping, and format components.</span></span>

1. <span data-ttu-id="8d9bb-154">Logga in på den instans av RCS som har etablerats för ditt företag.</span><span class="sxs-lookup"><span data-stu-id="8d9bb-154">Sign in to the instance of RCS that has been provisioned for your company.</span></span>
2. <span data-ttu-id="8d9bb-155">I den här självstudien ska du skapa och ändra konfigurationer för exempelföretaget **Litware, Inc**.</span><span class="sxs-lookup"><span data-stu-id="8d9bb-155">In this tutorial, you will create and modify configurations for the **Litware, Inc.** sample company.</span></span> <span data-ttu-id="8d9bb-156">Kontrollera därför att denna konfigurationsleverantör har lagts till i RCS och valts som aktiv.</span><span class="sxs-lookup"><span data-stu-id="8d9bb-156">Therefore, make sure that this configuration provider has been added to RCS and selected as active.</span></span> <span data-ttu-id="8d9bb-157">Instruktioner finns i proceduren [skapa konfigurationsleverantörer och markera dem som aktiva](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/analytics/tasks/er-configuration-provider-mark-it-active-2016-11).</span><span class="sxs-lookup"><span data-stu-id="8d9bb-157">For instructions, see the [Create configuration providers and mark them as active](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/analytics/tasks/er-configuration-provider-mark-it-active-2016-11) procedure.</span></span>
3. <span data-ttu-id="8d9bb-158">På arbetsytan **Elektronisk rapportering** väljer du panelen **Rapporteringskonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="8d9bb-158">In the **Electronic reporting** workspace, select the **Reporting configurations** tile.</span></span>
4. <span data-ttu-id="8d9bb-159">På sidan **konfigurationer** importerar du de ER-konfigurationer som du hämtade som en förutsättning i RCS i följande ordning: datamodell, metadata, modellmappning, format.</span><span class="sxs-lookup"><span data-stu-id="8d9bb-159">On the **Configurations** page, import the ER configurations that you downloaded as a prerequisite into RCS, in the following order: data model, metadata, model mapping, format.</span></span> <span data-ttu-id="8d9bb-160">Följ dessa steg för varje konfiguration:</span><span class="sxs-lookup"><span data-stu-id="8d9bb-160">For each configuration, follow these steps:</span></span>

    1. <span data-ttu-id="8d9bb-161">På Åtgärdsfönster väljer du **växla \> läs in från XML-fil**.</span><span class="sxs-lookup"><span data-stu-id="8d9bb-161">On the Action Pane, select **Exchange \> Load from XML file**.</span></span>
    2. <span data-ttu-id="8d9bb-162">Välj **bläddra** om du vill välja en fil för den nödvändiga ER-konfigurationen i XML-format.</span><span class="sxs-lookup"><span data-stu-id="8d9bb-162">Select **Browse** to select the appropriate file for the required ER configuration in XML format.</span></span>
    3. <span data-ttu-id="8d9bb-163">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="8d9bb-163">Select **OK**.</span></span>

    ![Sidan Konfigurationer i RCS](./media/GER-PerfTrace-RCS-ImportedConfigurations.png)

## <a name="run-the-er-solution-to-trace-execution"></a><span data-ttu-id="8d9bb-165">Kör ER-lösning för att spåra körning</span><span class="sxs-lookup"><span data-stu-id="8d9bb-165">Run the ER solution to trace execution</span></span>

<span data-ttu-id="8d9bb-166">Anta att du har skapat den första versionen av ER-lösningen.</span><span class="sxs-lookup"><span data-stu-id="8d9bb-166">Assume that you've finished designing the first version of the ER solution.</span></span> <span data-ttu-id="8d9bb-167">Du vill nu testa den i Finance and Operations-instansen och analysera körningsprestanda.</span><span class="sxs-lookup"><span data-stu-id="8d9bb-167">You now want to test it in your Finance and Operations instance and analyze execution performance.</span></span>

### <a id='import-configuration'></a><span data-ttu-id="8d9bb-168">Importera en ER-konfiguration från RCS till Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="8d9bb-168">Import an ER configuration from RCS into Finance and Operations</span></span>

1. <span data-ttu-id="8d9bb-169">Logga in på din instans av Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="8d9bb-169">Sign in to your Finance and Operations instance.</span></span>
2. <span data-ttu-id="8d9bb-170">För den här självstudien ska du importera konfigurationer från din RCS-instans (där du utformar dina ER-komponenter) till Finance and Operations-instansen (där du testar och slutligen använder dem.)</span><span class="sxs-lookup"><span data-stu-id="8d9bb-170">For this tutorial, you will import configurations from your RCS instance (where you design your ER components) into your Finance and Operations instance (where you test and finally use them).</span></span> <span data-ttu-id="8d9bb-171">Därför måste du se till att alla nödvändiga artefakter har förberetts.</span><span class="sxs-lookup"><span data-stu-id="8d9bb-171">Therefore, you must make sure that all the required artifacts have been prepared.</span></span> <span data-ttu-id="8d9bb-172">För mer information, se proceduren [Importera e-rapporteringskonfigurationer från Regulatory Configuration Services (RCS)](https://docs.microsoft.com/en-us/dynamics365/unified-operations/dev-itpro/analytics/rcs-download-configurations).</span><span class="sxs-lookup"><span data-stu-id="8d9bb-172">For instructions, see the [Import Electronic reporting (ER) configurations from Regulatory Configuration Services (RCS)](https://docs.microsoft.com/en-us/dynamics365/unified-operations/dev-itpro/analytics/rcs-download-configurations) procedure.</span></span>
3. <span data-ttu-id="8d9bb-173">Följ dessa steg för att importera konfigurationerna från RCS till Finance and Operations:</span><span class="sxs-lookup"><span data-stu-id="8d9bb-173">Follow these steps to import the configurations from RCS into Finance and Operations:</span></span>

    1. <span data-ttu-id="8d9bb-174">I arbetsytan **elektronisk rapportering** på panelen för konfigurationsleverantören **Litware, Inc.** väljer du **Databaser**.</span><span class="sxs-lookup"><span data-stu-id="8d9bb-174">In the **Electronic reporting** workspace, on the tile for the **Litware, Inc.** configuration provider, select **Repositories**.</span></span>
    2. <span data-ttu-id="8d9bb-175">På sidan **Konfigurationsdatabaser** väljer du i rutnätet den befintliga databasen för **RCS**-typ och väljer sedan **Öppna**.</span><span class="sxs-lookup"><span data-stu-id="8d9bb-175">On the **Configuration repository** page, select the repository of the **RCS** type, and then select **Open**.</span></span>
    3. <span data-ttu-id="8d9bb-176">På snabbfliken **konfigurationer** väljer du konfigurationen **Prestandaspårningsformat**.</span><span class="sxs-lookup"><span data-stu-id="8d9bb-176">On the **Configurations** FastTab, select the **Performance trace format** configuration.</span></span>
    4. <span data-ttu-id="8d9bb-177">I snabbfliken **Versioner** väljer du version **1.1.** för vald konfiguration och sedan **Importera**.</span><span class="sxs-lookup"><span data-stu-id="8d9bb-177">On the **Versions** FastTab, select version **1.1** of the selected configuration, and then select **Import**.</span></span>

    ![Sidan Konfigurationsdatabaser i Finance and Operations](./media/GER-PerfTrace-GER-ImportedConfigurations.png)

<span data-ttu-id="8d9bb-179">Motsvarande versioner av datamodell- och modellmappningskonfigurationer importeras automatiskt som förutsättningar för den importerade ER-formatkonfigurationen.</span><span class="sxs-lookup"><span data-stu-id="8d9bb-179">The corresponding versions of the data model and model mapping configurations are automatically imported as prerequisites for the imported ER format configuration.</span></span>

### <a name="turn-on-the-er-performance-trace"></a><span data-ttu-id="8d9bb-180">Aktivera ER-prestandaspårning</span><span class="sxs-lookup"><span data-stu-id="8d9bb-180">Turn on the ER performance trace</span></span>

1. <span data-ttu-id="8d9bb-181">I Finance and Operations, gå till **Organisationsadministration \> Elektronisk rapportering \> Konfigurationer**.</span><span class="sxs-lookup"><span data-stu-id="8d9bb-181">In Finance and Operations, go to **Organization administration \> Electronic reporting \> Configurations**.</span></span>
2. <span data-ttu-id="8d9bb-182">På sidan **Konfigurationer** i åtgärdsfönstret, på fliken **Konfigurationer** i gruppen **Avancerad inställningar** markerar du **Använd parametrar**.</span><span class="sxs-lookup"><span data-stu-id="8d9bb-182">On the **Configurations** page, on the Action Pane, on the **Configurations** tab, in the **Advanced settings** group, select **User parameters**.</span></span>
3. <span data-ttu-id="8d9bb-183">I dialogrutan **Användarparametrar** i avsnittet **körningsspårning** gör fäljande steg:</span><span class="sxs-lookup"><span data-stu-id="8d9bb-183">In the **User parameters** dialog box, in the **Execution tracing** section, follow these steps:</span></span>

    1. <span data-ttu-id="8d9bb-184">I fältet **körningsspårningsformat** väljer du **felsökningsspårningsformat** för att börja samla in information om ER-formatkörning.</span><span class="sxs-lookup"><span data-stu-id="8d9bb-184">In the **Execution trace format** field, select **Debug trace format** to start to collect the details of ER format execution.</span></span> <span data-ttu-id="8d9bb-185">När det här värdet väljs samlar prestandaspårningen in information om den tid som har ägnats åt följande åtgärder:</span><span class="sxs-lookup"><span data-stu-id="8d9bb-185">When this value is selected, the performance trace will collect information about the time that is spent on the following actions:</span></span>

        - <span data-ttu-id="8d9bb-186">Kör varje datakälla i modellmappningen som anropas för att hämta data</span><span class="sxs-lookup"><span data-stu-id="8d9bb-186">Running each data source in the model mapping that is called to get data</span></span>
        - <span data-ttu-id="8d9bb-187">Behandla varje formatobjekt för att ange data i de utdata som genereras</span><span class="sxs-lookup"><span data-stu-id="8d9bb-187">Processing each format item to enter data in the output that is generated</span></span>

        <span data-ttu-id="8d9bb-188">Du använder fältet **körningsspårningsformat** om du vill ange formatet för den genererade prestandaspårning som körningsinformationen lagras i för ER-format och mappningselement.</span><span class="sxs-lookup"><span data-stu-id="8d9bb-188">You use the **Execution trace format** field to specify the format of the generated performance trace that the execution details are stored in for ER format and mapping elements.</span></span> <span data-ttu-id="8d9bb-189">Om du väljer **felsökningsspårningsformat** som värde kan du analysera innehållet i spårningen i ER-åtgärdsdesignern och se ER-format eller mappningselement som nämns i spårningen.</span><span class="sxs-lookup"><span data-stu-id="8d9bb-189">By selecting **Debug trace format** as the value, you will be able to analyze the content of the trace in ER Operation designer, and see the ER format or mapping elements that are mentioned in the trace.</span></span>

    2. <span data-ttu-id="8d9bb-190">Ange följande alternativ till **ja** för att samla in specifik information om körningen av komponenterna ER-modellmappning och ER-format:</span><span class="sxs-lookup"><span data-stu-id="8d9bb-190">Set the following options to **Yes** to collect specific details of the execution of the ER model mapping and ER format components:</span></span>

        - <span data-ttu-id="8d9bb-191">**Samla in frestatistik** – när det här alternativet är aktiverat samlar prestandaspårningen in följande information:</span><span class="sxs-lookup"><span data-stu-id="8d9bb-191">**Collect query statistics** – When this option is turned on, the performance trace will collect the following information:</span></span>

            - <span data-ttu-id="8d9bb-192">Antalet databasanrop som har gjorts av datakällor</span><span class="sxs-lookup"><span data-stu-id="8d9bb-192">The number of database calls that were made by data sources</span></span>
            - <span data-ttu-id="8d9bb-193">Antalet dubblettanrop till databasen.</span><span class="sxs-lookup"><span data-stu-id="8d9bb-193">The number of duplicate calls to the database</span></span>
            - <span data-ttu-id="8d9bb-194">Information om SQL-satserna som användes för att göra databasanrop</span><span class="sxs-lookup"><span data-stu-id="8d9bb-194">Details of the SQL statements that were used to make database calls</span></span>

        - <span data-ttu-id="8d9bb-195">**Spåra åtkomst av cachelagring** – när det här alternativet är aktiverat samlar prestandaspårningen in information om vad som gäller för ER-modell mappningens cache-användning.</span><span class="sxs-lookup"><span data-stu-id="8d9bb-195">**Trace access of caching** – When this option is turned on, the performance trace will collect information about the ER model mapping's cache usage.</span></span>
        - <span data-ttu-id="8d9bb-196">**Spåra dataåtkomst** – när det här alternativet är aktiverat samlar prestandaspårningen in information om antalet anrop till databasen för körda datakällor av postlisttypen.</span><span class="sxs-lookup"><span data-stu-id="8d9bb-196">**Trace data access** – When this option is turned on, the performance trace will collect information about the number of calls to the database for executed data sources of the record list type.</span></span>
        - <span data-ttu-id="8d9bb-197">**Spåra listuppräkning** – när det här alternativet är aktiverat samlar prestandaspårningen in information om antalet poster som begärs från datakällor av postlisttypen.</span><span class="sxs-lookup"><span data-stu-id="8d9bb-197">**Trace list enumeration** – When this option is turned on, the performance trace will collect information about the number of records that are requested from data sources of the record list type.</span></span>

    > [!NOTE]
    > <span data-ttu-id="8d9bb-198">Parametrarna i dialogrutan **användarparametrar** är specifika för användaren och det aktuella företaget.</span><span class="sxs-lookup"><span data-stu-id="8d9bb-198">The parameters in the **User parameters** dialog box are specific to the user and the current company.</span></span>

    ![Dialogrutan användarparametrar i Finance and Operations](./media/GER-PerfTrace-GER-UserParameters.png)

### <a id='run-format'></a><span data-ttu-id="8d9bb-200">Kör ER-format</span><span class="sxs-lookup"><span data-stu-id="8d9bb-200">Run the ER format</span></span>

1. <span data-ttu-id="8d9bb-201">I Finance and Operations, välj företaget **DEMF**.</span><span class="sxs-lookup"><span data-stu-id="8d9bb-201">In Finance and Operations, select the **DEMF** company.</span></span>
2. <span data-ttu-id="8d9bb-202">Gå till **Organisationsadministration  \> Elektronisk rapportering \> Konfigurationer**.</span><span class="sxs-lookup"><span data-stu-id="8d9bb-202">Go to **Organization administration \> Electronic reporting \> Configurations**.</span></span>
3. <span data-ttu-id="8d9bb-203">På sidan **konfigurationer** i konfigurationsträdet väljer du artikeln **Prestandaspårningsformat**.</span><span class="sxs-lookup"><span data-stu-id="8d9bb-203">On the **Configurations** page, in the configuration tree, select the **Performance trace format** item.</span></span>
4. <span data-ttu-id="8d9bb-204">Klicka på **Kör** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="8d9bb-204">On the Action Pane, select **Run**.</span></span>

<span data-ttu-id="8d9bb-205">Observera att filen som genereras visar information om 265 transaktioner för sex leverantörer.</span><span class="sxs-lookup"><span data-stu-id="8d9bb-205">Notice that the file that is generated presents information about 265 transactions for six vendors.</span></span>

## <a name="review-the-execution-trace"></a><span data-ttu-id="8d9bb-206">Granska körningsspårningen</span><span class="sxs-lookup"><span data-stu-id="8d9bb-206">Review the execution trace</span></span>

### <a id='export-trace'></a><span data-ttu-id="8d9bb-207">Exportera den genererade spårningen från Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="8d9bb-207">Export the generated trace from Finance and Operations</span></span>

<span data-ttu-id="8d9bb-208">Prestandaspårningen kopplas från källans ER-format och kan serialiseras till en extern ZIP-fil.</span><span class="sxs-lookup"><span data-stu-id="8d9bb-208">Performance traces are decoupled from the source ER format and can be serialized to an external zip file.</span></span>

1. <span data-ttu-id="8d9bb-209">I Finance and Operations, gå till **Organisationsadministration \> Elektronisk rapportering \> Konfiguration av felsökningsloggar**.</span><span class="sxs-lookup"><span data-stu-id="8d9bb-209">In Finance and Operations, go to **Organization administration \> Electronic reporting \> Configuration debug logs**.</span></span>
2. <span data-ttu-id="8d9bb-210">På sidan **elektronisk rapportering kör loggar** i det vänstra fönstret i **konfigurationsnamn** väljer du **prestandaspårningsformat** i för att hitta de loggposter som har genererats vid körning av konfigurationen **Prestandaspårningsformat**.</span><span class="sxs-lookup"><span data-stu-id="8d9bb-210">On the **Electronic reporting run logs** page, in the left pane, in the **Configuration name** field, select **Performance trace format** to find the log records that have been generated by the execution of the **Performance trace format** configuration.</span></span>
3. <span data-ttu-id="8d9bb-211">Välj knappen **Bilagor** (gemsymbolen) längst upp till höger på sidan eller tryck på **Ctrl+Shift+A**.</span><span class="sxs-lookup"><span data-stu-id="8d9bb-211">Select the **Attachments** button (the paper clip symbol) in the upper-right corner of the page, or press **Ctrl+Shift+A**.</span></span>

    ![Knappen Bilagor på sidan elektronisk rapportering körningsloggarna i Finance and Operations](./media/GER-PerfTrace-GER-DebugLog.png)

4. <span data-ttu-id="8d9bb-213">På sidan **bilagor för elektroniska rapportering körningsloggar** i åtgärdsfönstret väljer du **öppna** för att få prestandaspårningen som en zip-fil och spara den lokalt.</span><span class="sxs-lookup"><span data-stu-id="8d9bb-213">On the **Attachments for Electronic reporting run logs** page, on the Action Pane, select **Open** to get the performance trace as a zip file and store it locally.</span></span>

    ![Bilagor för elektronisk rapportering körningsloggarna i Finance and Operations](./media/GER-PerfTrace-GER-DebugLog-AttachedTrace.png)

> [!NOTE]
> <span data-ttu-id="8d9bb-215">Spårningen som genereras har en referens till källans ER-rapport via en unik rapportidentifierare i **GUID**-format.</span><span class="sxs-lookup"><span data-stu-id="8d9bb-215">The trace that is generated has a reference to the source ER report via a unique report identifier in **GUID** format only.</span></span> <span data-ttu-id="8d9bb-216">Versionsnumret för formatet beaktas inte.</span><span class="sxs-lookup"><span data-stu-id="8d9bb-216">The version numbering of the format isn't considered.</span></span>

<span data-ttu-id="8d9bb-217">Observera att associationen mellan resultatspårningen som har genererats för det körda ER-formatet och ER-modellmappningen baseras på den rotbeskrivare som användes och den gemensamma datamodellen.</span><span class="sxs-lookup"><span data-stu-id="8d9bb-217">Notice that the association between the performance trace that has been generated for the executed ER format and the ER model mapping is based on the root descriptor that was used and the common data model.</span></span> <span data-ttu-id="8d9bb-218">Versionsnumret för formatet ochmmdellmappning beaktas inte.</span><span class="sxs-lookup"><span data-stu-id="8d9bb-218">The version numbering of the format and model mapping isn't considered.</span></span> <span data-ttu-id="8d9bb-219">Inställningen av flaggan **Standard för modellmappning** för modellmappningen beaktas inte heller.</span><span class="sxs-lookup"><span data-stu-id="8d9bb-219">The setting of the **Default for model mapping** flag for the model mapping also isn't considered.</span></span>

### <a id='import-trace'></a><span data-ttu-id="8d9bb-220">Importera genererad spårning till RCS.</span><span class="sxs-lookup"><span data-stu-id="8d9bb-220">Import the generated trace into RCS</span></span>

1. <span data-ttu-id="8d9bb-221">I RCS på arbetsytan **Elektronisk rapportering** väljer du panelen **Rapporteringskonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="8d9bb-221">In RCS, in the **Electronic reporting** workspace, select the **Reporting configurations** tile.</span></span>
2. <span data-ttu-id="8d9bb-222">På sidan **konfigurationer** i konfigurationsträdet, expandera artikeln **Prestandaspårningsmodell** och väljer artikeln **Prestandaspårningsformat**.</span><span class="sxs-lookup"><span data-stu-id="8d9bb-222">On the **Configurations** page, in the configuration tree, expand the **Performance trace model** item, and select the **Performance trace format** item.</span></span>
3. <span data-ttu-id="8d9bb-223">Klicka på **Designer** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="8d9bb-223">On the Action Pane, select **Designer**.</span></span>
4. <span data-ttu-id="8d9bb-224">På snabbfliken **Formatdesigner** på åtgärdsfönstret väljer du **Prestandaspårningsformat**.</span><span class="sxs-lookup"><span data-stu-id="8d9bb-224">On the **Format designer** page, on the Action Pane, select **Performance trace**.</span></span>
5. <span data-ttu-id="8d9bb-225">I dialogrutan **Inställning av prestandaspårningsresultat** väljer du **Importera prestandaspårning**.</span><span class="sxs-lookup"><span data-stu-id="8d9bb-225">In the **Performance trace result settings** dialog box, select **Import performance trace**.</span></span>
6. <span data-ttu-id="8d9bb-226">Välj **bläddra** om du vill välja den zip-fil som du exporterade från Finance and Operations tidigare.</span><span class="sxs-lookup"><span data-stu-id="8d9bb-226">Select **Browse** to select the zip file that you exported from Finance and Operations earlier.</span></span>
7. <span data-ttu-id="8d9bb-227">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="8d9bb-227">Select **OK**.</span></span>

    ![Dialogrutan inställningar av prestandaspårningsresultat i RCS](./media/GER-PerfTrace-RCS-ImportedPerfTrace.png)

### <a name="use-the-performance-trace-for-analysis-in-rcs--format-execution"></a><span data-ttu-id="8d9bb-229">Använd prestandaspårning för analys i RCS – formatkörning</span><span class="sxs-lookup"><span data-stu-id="8d9bb-229">Use the performance trace for analysis in RCS – Format execution</span></span>

1. <span data-ttu-id="8d9bb-230">I RCS, på sidan **Formatdesigner** välj **Visa/Dölj** för att expandera innehållet i alla formatobjekt.</span><span class="sxs-lookup"><span data-stu-id="8d9bb-230">In RCS, on the **Format designer** page, select **Expand/collapse** to expand the content of all format items.</span></span>

    <span data-ttu-id="8d9bb-231">Lägg märke till att ytterligare information visas för vissa artiklar i det aktuella formatet:</span><span class="sxs-lookup"><span data-stu-id="8d9bb-231">Notice that additional information is shown for some items of the current format:</span></span>

    - <span data-ttu-id="8d9bb-232">Den faktiska tid som användes för att mata in data i det genererade utmatninget med hjälp av formaobjekt</span><span class="sxs-lookup"><span data-stu-id="8d9bb-232">The actual time that was spent entering data in the generated output by using the format item</span></span>
    - <span data-ttu-id="8d9bb-233">Samma tid uttryckt i procent av den totala tid som användes för att generera hela utdata</span><span class="sxs-lookup"><span data-stu-id="8d9bb-233">The same time expressed as a percentage of the total time that was spent generating the whole output</span></span>

    ![Formatdesignersida i RCS](./media/GER-PerfTrace-RCS-TraceInfoInFormat.png)

2. <span data-ttu-id="8d9bb-235">Stäng sidan **Formatdesigner**.</span><span class="sxs-lookup"><span data-stu-id="8d9bb-235">Close **Format designer** page.</span></span>

### <a id='use-trace'></a><span data-ttu-id="8d9bb-236">Använd prestandaspårning för analys i RCS – modellmappning</span><span class="sxs-lookup"><span data-stu-id="8d9bb-236">Use the performance trace for analysis in RCS – Model mapping</span></span>

1. <span data-ttu-id="8d9bb-237">I RCS på sidan **konfigurationer** i konfigurationsträdet väljer du artikeln **Prestandaspårningsmappning**.</span><span class="sxs-lookup"><span data-stu-id="8d9bb-237">In RCS, on the **Configurations** page, in the configuration tree, select the **Performance trace mapping** item.</span></span>
2. <span data-ttu-id="8d9bb-238">Klicka på **Designer** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="8d9bb-238">On the Action Pane, select **Designer**.</span></span>
3. <span data-ttu-id="8d9bb-239">Välj **Designer**.</span><span class="sxs-lookup"><span data-stu-id="8d9bb-239">Select **Designer**.</span></span>
4. <span data-ttu-id="8d9bb-240">På snabbfliken **Modellmappningsdesigner** på åtgärdsfönstret väljer du **Prestandaspårningsformat**.</span><span class="sxs-lookup"><span data-stu-id="8d9bb-240">On the **Model mapping designer** page, on the Action Pane, select **Performance trace**.</span></span>
5. <span data-ttu-id="8d9bb-241">Välj spårningen som du importerade tidigare.</span><span class="sxs-lookup"><span data-stu-id="8d9bb-241">Select the trace that you imported earlier.</span></span>
6. <span data-ttu-id="8d9bb-242">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="8d9bb-242">Select **OK**.</span></span>

<span data-ttu-id="8d9bb-243">Lägg märke till att ny information blir tillgänglig för vissa datakällobjekt i den aktuella modellmappningen:</span><span class="sxs-lookup"><span data-stu-id="8d9bb-243">Notice that new information becomes available for some data source items of the current model mapping:</span></span>

- <span data-ttu-id="8d9bb-244">Den faktiska tid som användes för att hämta data genom att använda datakällan</span><span class="sxs-lookup"><span data-stu-id="8d9bb-244">The actual time that was spent getting data by using the data source</span></span>
- <span data-ttu-id="8d9bb-245">Samma tid uttryckt i procent av den totala tid som användes för att köra hela modellmappningen</span><span class="sxs-lookup"><span data-stu-id="8d9bb-245">The same time expressed as a percentage of the total time that was spent running the whole model mapping</span></span>

<span data-ttu-id="8d9bb-246">Observera att du informerar dig om att den aktuella modellmappningen duplicerar databas begäranden när datakällan VendTable/\<Relations/VendTrans.VendTable\_AccountNum körs.</span><span class="sxs-lookup"><span data-stu-id="8d9bb-246">Notice that ER informs you that the current model mapping duplicates database requests while the VendTable/\<Relations/VendTrans.VendTable\_AccountNum data source is run.</span></span> <span data-ttu-id="8d9bb-247">Den här dubbletten sker eftersom listan med leverantörstransaktioner anropas två gånger för varje förslagen leverantörspost:</span><span class="sxs-lookup"><span data-stu-id="8d9bb-247">This duplication occurs because the list of vendor transactions is called two times for each iterated vendor record:</span></span>

- <span data-ttu-id="8d9bb-248">Ett anrop görs för att ange information om varje transaktion i datamodellen, baserat på konfigurerade bindningar.</span><span class="sxs-lookup"><span data-stu-id="8d9bb-248">One call is made to enter details of each transaction in the data model, based on configured bindings.</span></span>
- <span data-ttu-id="8d9bb-249">Ett samtal görs för att ange det beräknade antalet transaktioner per leverantör i datamodellen.</span><span class="sxs-lookup"><span data-stu-id="8d9bb-249">One call is made to enter the calculated number of transactions per vendor in the data model.</span></span>

![Meddelande om dubbla databasbegäranden på sidan modellmappningsdesigner i RCS](./media/GER-PerfTrace-RCS-TraceInfoInMapping1.png)

<span data-ttu-id="8d9bb-251">Värdet **\[Q:530\]** anger att VendTrans-registret har anropats 530 gånger för att returnera en post från registret till datakällan VendTable/\<Relations/VendTrans.VendTable\_AccountNum.</span><span class="sxs-lookup"><span data-stu-id="8d9bb-251">The value **\[Q:530\]** indicates that the VendTrans table was called 530 times to return a record from that table to the VendTable/\<Relations/VendTrans.VendTable\_AccountNum data source.</span></span> <span data-ttu-id="8d9bb-252">Värdet **\[530\]** anger att datakällan VendTable/\<Relations/VendTrans.VendTable\_AccountNum har anropats 530 gånger för att returnera en post från den datakällan och ange informationen från den i datamodellen.</span><span class="sxs-lookup"><span data-stu-id="8d9bb-252">The value **\[530\]** indicates that the VendTable/\<Relations/VendTrans.VendTable\_AccountNum data source was called 530 times to return a record from that data source and enter the details from it in the data model.</span></span>

<span data-ttu-id="8d9bb-253">Vi rekommenderar att du använder cache för datakällan VendTable/\<Relations/VendTrans.VendTable\_AccountNum för att minska antalet anrop som görs för att få information om 265-transaktioner och förbättra modellmappningens prestanda.</span><span class="sxs-lookup"><span data-stu-id="8d9bb-253">We recommend that you use caching for the VendTable/\<Relations/VendTrans.VendTable\_AccountNum data source, to reduce the number of calls that are made to get the details for 265 transactions and help improve the performance of the model mapping.</span></span>

<span data-ttu-id="8d9bb-254">Det kan också vara användbart om du vill minska antalet anrop som görs till datakällan LedgerTransTypeList.</span><span class="sxs-lookup"><span data-stu-id="8d9bb-254">It can also be useful to reduce the number of calls that are made to the LedgerTransTypeList data source.</span></span> <span data-ttu-id="8d9bb-255">Denna datakälla används för att koppla varje värde i **LedgerTransType**-uppräkningen till dess etikett.</span><span class="sxs-lookup"><span data-stu-id="8d9bb-255">This data source is used to associate each value of the **LedgerTransType** enumeration with its label.</span></span> <span data-ttu-id="8d9bb-256">Genom att använda den här datakällan kan du hitta en lämplig etikett och ange den i datamodellen för varje leverantörstransaktion.</span><span class="sxs-lookup"><span data-stu-id="8d9bb-256">By using this data source, you can find an appropriate label and enter it in the data model for each vendor transaction.</span></span> <span data-ttu-id="8d9bb-257">Det aktuella antalet anrop till den här datakällan (9 027) är ganska högt för 265 transaktioner.</span><span class="sxs-lookup"><span data-stu-id="8d9bb-257">The current number of calls to this data source (9,027) is quite high for 265 transactions.</span></span>

![Sidan modellmappningsdesigner i RCS, visar 9 027 anrop till datakällan](./media/GER-PerfTrace-RCS-TraceInfoInMapping1a.png)

## <a name="improve-the-model-mapping-based-on-information-from-the-execution-trace"></a><span data-ttu-id="8d9bb-259">Förbättra modellmappningen utifrån information från körningsspårningen</span><span class="sxs-lookup"><span data-stu-id="8d9bb-259">Improve the model mapping based on information from the execution trace</span></span>

### <a name="modify-the-logic-of-the-model-mapping"></a><span data-ttu-id="8d9bb-260">Ändra logiken för modellmappningen</span><span class="sxs-lookup"><span data-stu-id="8d9bb-260">Modify the logic of the model mapping</span></span>

1. <span data-ttu-id="8d9bb-261">Gör så här om du vill använda cache för att förhindra att anrop till databasen dupliceras:</span><span class="sxs-lookup"><span data-stu-id="8d9bb-261">Follow these steps to use caching, to help prevent duplicate calls to the database:</span></span>

    1. <span data-ttu-id="8d9bb-262">I RCS, på sidan **Modellmappingsdesigner** i fönstret **Datakällor** väljer du objektet **VendTable**.</span><span class="sxs-lookup"><span data-stu-id="8d9bb-262">In RCS, on the **Model mapping designer** page, in the **Data sources** pane, select the **VendTable** item.</span></span>
    2. <span data-ttu-id="8d9bb-263">Välj **cache**.</span><span class="sxs-lookup"><span data-stu-id="8d9bb-263">Select **Cache**.</span></span>
    3. <span data-ttu-id="8d9bb-264">Expandera objektet **VendTable**  expandera listan med 1:n-relationer för VendTable-datakälla (**\<Relationer** objekt) och välj objektet **VendTrans.VendTable\_AccountNum**.</span><span class="sxs-lookup"><span data-stu-id="8d9bb-264">Expand the **VendTable** item, expand the list of one-to-many relations for the VendTable data source (the **\<Relations** item), and select the **VendTrans.VendTable\_AccountNum** item.</span></span>
    4. <span data-ttu-id="8d9bb-265">Välj **cache**.</span><span class="sxs-lookup"><span data-stu-id="8d9bb-265">Select **Cache**.</span></span>

    ![Cachelagring för att förhindra dubbla anrop](./media/GER-PerfTrace-RCS-ChangeMapping-Cache.png)

2. <span data-ttu-id="8d9bb-267">Följ dessa steg för att hämta datakällan LedgerTransTypeList till omfattningen för datakällan VendTable:</span><span class="sxs-lookup"><span data-stu-id="8d9bb-267">Follow these steps to bring the LedgerTransTypeList data source into the scope of the VendTable data source:</span></span>

    1. <span data-ttu-id="8d9bb-268">I fönstret **datakälltyper** expanderar du objektet **funktioner** och markerar objektet **beräknade fält**.</span><span class="sxs-lookup"><span data-stu-id="8d9bb-268">In the **Data source types** pane, expand the **Functions** item, and select the **Calculated field** item.</span></span>
    2. <span data-ttu-id="8d9bb-269">Markera objektet **VendTable** i fönstret **datakällor**.</span><span class="sxs-lookup"><span data-stu-id="8d9bb-269">In the **Data sources** pane, select the **VendTable** item.</span></span>
    3. <span data-ttu-id="8d9bb-270">Markera **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="8d9bb-270">Select **Add**.</span></span>
    4. <span data-ttu-id="8d9bb-271">Skriv **\$TransType** i fältet **Namn**.</span><span class="sxs-lookup"><span data-stu-id="8d9bb-271">In the **Name** field, enter **\$TransType**.</span></span>
    5. <span data-ttu-id="8d9bb-272">Välj **Redigera recept**.</span><span class="sxs-lookup"><span data-stu-id="8d9bb-272">Select **Edit formula**.</span></span>
    6. <span data-ttu-id="8d9bb-273">I fältet **Recept** ange **LedgerTransTypeList**.</span><span class="sxs-lookup"><span data-stu-id="8d9bb-273">In the **Formula** field, enter **LedgerTransTypeList**.</span></span>
    7. <span data-ttu-id="8d9bb-274">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="8d9bb-274">Select **Save**.</span></span>
    8. <span data-ttu-id="8d9bb-275">Stäng sidan **receptredigering**.</span><span class="sxs-lookup"><span data-stu-id="8d9bb-275">Close the **Formula editor** page.</span></span>
    9. <span data-ttu-id="8d9bb-276">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="8d9bb-276">Click **OK**.</span></span>

3. <span data-ttu-id="8d9bb-277">Gör följande om du vill göra cachelagring av fältet **\$TransType**:</span><span class="sxs-lookup"><span data-stu-id="8d9bb-277">Follow these steps to do caching of the **\$TransType** field:</span></span>

    1. <span data-ttu-id="8d9bb-278">Välj bjektet **LedgerTransTypeList**.</span><span class="sxs-lookup"><span data-stu-id="8d9bb-278">Select the **LedgerTransTypeList** item.</span></span>
    2. <span data-ttu-id="8d9bb-279">Välj **cache**.</span><span class="sxs-lookup"><span data-stu-id="8d9bb-279">Select **Cache**.</span></span>
    3. <span data-ttu-id="8d9bb-280">Välj objektet **VendTable.\$TransType**.</span><span class="sxs-lookup"><span data-stu-id="8d9bb-280">Select the **VendTable.\$TransType** item.</span></span>
    4. <span data-ttu-id="8d9bb-281">Välj **cache**.</span><span class="sxs-lookup"><span data-stu-id="8d9bb-281">Select **Cache**.</span></span>

    ![Cachelagra inställningar för fältet $TransType](./media/GER-PerfTrace-RCS-ChangeMapping-Cache2.png)

4. <span data-ttu-id="8d9bb-283">Följ dessa steg för att ändra **\$TransTypeRecord** så att det börjar använda cachelagrade fältet **\$TransType**:</span><span class="sxs-lookup"><span data-stu-id="8d9bb-283">Follow these steps to change the **\$TransTypeRecord** field so that it starts to use the cached **\$TransType** field:</span></span>

    1. <span data-ttu-id="8d9bb-284">I fönstret **Datakällor**, expandera objektet **VendTable** expandera objektet **\<Relations** expandera objektet **VendTrans.VendTable\_AccountNum** och välj sedan  **VendTable. VendTrans.VendTable\_AccountNum.\$TransTypeRecord**.</span><span class="sxs-lookup"><span data-stu-id="8d9bb-284">In the **Data sources** pane, expand the **VendTable** item, expand the **\<Relations** item, expand the **VendTrans.VendTable\_AccountNum** item, and select the **VendTable. VendTrans.VendTable\_AccountNum.\$TransTypeRecord** item.</span></span>
    2. <span data-ttu-id="8d9bb-285">Välj **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="8d9bb-285">Select **Edit**.</span></span>
    3. <span data-ttu-id="8d9bb-286">Välj **Redigera recept**.</span><span class="sxs-lookup"><span data-stu-id="8d9bb-286">Select **Edit formula**.</span></span>
    4. <span data-ttu-id="8d9bb-287">I fältet **formel** hittar du följande uttryck:</span><span class="sxs-lookup"><span data-stu-id="8d9bb-287">In the **Formula** field, find the following expression:</span></span>

        <span data-ttu-id="8d9bb-288">FIRSTORNULL (WHERE (LedgerTransTypeList, LedgerTransTypeList.Enum = \@.TransType))</span><span class="sxs-lookup"><span data-stu-id="8d9bb-288">FIRSTORNULL (WHERE (LedgerTransTypeList, LedgerTransTypeList.Enum = \@.TransType))</span></span>

    5. <span data-ttu-id="8d9bb-289">I fältet **formel** anger du följande uttryck:</span><span class="sxs-lookup"><span data-stu-id="8d9bb-289">In the **Formula** field, enter the following expression:</span></span>

        <span data-ttu-id="8d9bb-290">FIRSTORNULL (WHERE (VendTable.'\$TransType', VendTable.'\$TransType'.Enum = \@.TransType)).</span><span class="sxs-lookup"><span data-stu-id="8d9bb-290">FIRSTORNULL (WHERE (VendTable.'\$TransType', VendTable.'\$TransType'.Enum = \@.TransType)).</span></span>

    6. <span data-ttu-id="8d9bb-291">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="8d9bb-291">Select **Save**.</span></span>
    7. <span data-ttu-id="8d9bb-292">Stäng sidan **receptredigering**.</span><span class="sxs-lookup"><span data-stu-id="8d9bb-292">Close the **Formula editor** page.</span></span>
    8. <span data-ttu-id="8d9bb-293">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="8d9bb-293">Select **OK**.</span></span>

5. <span data-ttu-id="8d9bb-294">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="8d9bb-294">Select **Save**.</span></span>
6. <span data-ttu-id="8d9bb-295">Stäng sidan **modellmappningsdesigner**.</span><span class="sxs-lookup"><span data-stu-id="8d9bb-295">Close the **Model mapping designer** page.</span></span>
7. <span data-ttu-id="8d9bb-296">Stäng sidan **modellmappningar**.</span><span class="sxs-lookup"><span data-stu-id="8d9bb-296">Close the **Model mappings** page.</span></span>

### <a name="complete-the-modified-version-of-the-er-model-mapping"></a><span data-ttu-id="8d9bb-297">Slutför den ändrade versionen av ER-modellmappningen</span><span class="sxs-lookup"><span data-stu-id="8d9bb-297">Complete the modified version of the ER model mapping</span></span>

1. <span data-ttu-id="8d9bb-298">I RCS, på sidan **Konfigurationer** på snabbfliken **Versioner** FastTab, välj version **1.2** av konfigurationen **prestandaspårningsmappning**.</span><span class="sxs-lookup"><span data-stu-id="8d9bb-298">In RCS, on the **Configurations** page, on the **Versions** FastTab, select version **1.2** of the **Performance trace mapping** configuration.</span></span>
2. <span data-ttu-id="8d9bb-299">Välj **Ändra status**.</span><span class="sxs-lookup"><span data-stu-id="8d9bb-299">Select **Change status**.</span></span>
3. <span data-ttu-id="8d9bb-300">Välj **Slutför**.</span><span class="sxs-lookup"><span data-stu-id="8d9bb-300">Select **Complete**.</span></span>

### <a name="import-the-modified-er-model-mapping-configuration-from-rcs-into-finance-and-operations"></a><span data-ttu-id="8d9bb-301">Importera den modifierade ER-modellmappningskonfigurationen från RCS till Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="8d9bb-301">Import the modified ER model mapping configuration from RCS into Finance and Operations</span></span>

<span data-ttu-id="8d9bb-302">Upprepa stegen i avsnittet [Importera en ER-konfiguration från RCS till Finance and Operations](#import-configuration) tidigare i det här avsnittet om du vill importera version 1.2 av konfigurationen **Prestandaspårningsmappning** i Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="8d9bb-302">Repeat the steps in the [Import an ER configuration from RCS into Finance and Operations](#import-configuration) section earlier in this topic to import version 1.2 of the **Performance trace mapping** configuration into Finance and Operations.</span></span>

## <a name="run-the-modified-er-solution-to-trace-execution"></a><span data-ttu-id="8d9bb-303">Kör modifierad ER-lösning för att spåra körning</span><span class="sxs-lookup"><span data-stu-id="8d9bb-303">Run the modified ER solution to trace execution</span></span>

### <a name="run-the-er-format"></a><span data-ttu-id="8d9bb-304">Kör ER-format</span><span class="sxs-lookup"><span data-stu-id="8d9bb-304">Run the ER format</span></span>

<span data-ttu-id="8d9bb-305">Upprepa stegen i avsnittet [kör ER-format](#run-format) tidigare i det här avsnittet om du vill generera en ny prestandaspårning.</span><span class="sxs-lookup"><span data-stu-id="8d9bb-305">Repeat the steps in the [Run the ER format](#run-format) section earlier in this topic to generate a new performance trace.</span></span>

## <a name="review-the-execution-trace"></a><span data-ttu-id="8d9bb-306">Granska körningsspårningen</span><span class="sxs-lookup"><span data-stu-id="8d9bb-306">Review the execution trace</span></span>

### <a name="export-the-generated-trace-from-finance-and-operations"></a><span data-ttu-id="8d9bb-307">Exportera den genererade spårningen från Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="8d9bb-307">Export the generated trace from Finance and Operations</span></span>

<span data-ttu-id="8d9bb-308">Upprepa stegen i avsnittet [exportera den genererade spårningen från Finance and Operations](#export-trace) tidigare i det här avsnittet om du vill spara en ny prestandaspårning lokalt.</span><span class="sxs-lookup"><span data-stu-id="8d9bb-308">Repeat the steps in the [Export the generated trace from Finance and Operations](#export-trace) section earlier in this topic to save a new performance trace locally.</span></span>

### <a name="import-the-generated-trace-into-rcs"></a><span data-ttu-id="8d9bb-309">Importera genererad spårning till RCS.</span><span class="sxs-lookup"><span data-stu-id="8d9bb-309">Import the generated trace into RCS</span></span>

<span data-ttu-id="8d9bb-310">tiUpprepa stegen i avsnittet [importera den genererade spårningen till RCS](#import-trace) tidigare i det här avsnittet om du vill importera den nya prestandaspårningen till RCS.</span><span class="sxs-lookup"><span data-stu-id="8d9bb-310">Repeat the steps in the [Import the generated trace into RCS](#import-trace) section earlier in this topic to import the new performance trace into RCS.</span></span>

### <a name="use-the-performance-trace-for-analysis-in-rcs--model-mapping"></a><span data-ttu-id="8d9bb-311">Använd prestandaspårning för analys i RCS – modellmappning</span><span class="sxs-lookup"><span data-stu-id="8d9bb-311">Use the performance trace for analysis in RCS – Model mapping</span></span>

<span data-ttu-id="8d9bb-312">Upprepa stegen i avsnittet [Använd prestandaspårning för analys i RCS – modellmappning](#use-trace) tidigare i det här avsnittet om du vill analysera den senaste prestandaspårningen.</span><span class="sxs-lookup"><span data-stu-id="8d9bb-312">Repeat the steps in the [Use the performance trace for analysis in RCS – Model mapping](#use-trace) section earlier in this topic to analyze the latest performance trace.</span></span>

<span data-ttu-id="8d9bb-313">Observera att justeringarna som du har gjort av modellmappningen har eliminerat dubbla frågor till databasen.</span><span class="sxs-lookup"><span data-stu-id="8d9bb-313">Notice that the adjustments that you made to the model mapping have eliminated duplicate queries to database.</span></span> <span data-ttu-id="8d9bb-314">Antalet anrop till databasregister och datakällor för den här modellmappningen har också minskats.</span><span class="sxs-lookup"><span data-stu-id="8d9bb-314">The number of calls to database tables and data sources for this model mapping has been also reduced.</span></span> <span data-ttu-id="8d9bb-315">Därför har hela ER-lösningens prestanda förbättrats.</span><span class="sxs-lookup"><span data-stu-id="8d9bb-315">Therefore, the performance of the whole ER solution has improved.</span></span>

![Spårningsinformation för datamodellen VendTable på sidan för modellmappningsdesigner i RCS](./media/GER-PerfTrace-RCS-TraceInfoInMapping2.png)

<span data-ttu-id="8d9bb-317">I spårningsinformationen indikerar värdet **\[12\]** för VendTable-datakällan att denna datakälla har anropats 12 gånger.</span><span class="sxs-lookup"><span data-stu-id="8d9bb-317">In the trace information, the value **\[12\]** for the VendTable data source indicates that this data source was called 12 times.</span></span> <span data-ttu-id="8d9bb-318">Värdet **\[Q:6\]** anger att sex anrop översattes till databasanrop till VendTable-registret.</span><span class="sxs-lookup"><span data-stu-id="8d9bb-318">The value **\[Q:6\]** indicates that six calls were translated to database calls to the VendTable table.</span></span> <span data-ttu-id="8d9bb-319">Värdet **\[C:6\]** indikerar att posterna som hämtades från databasen cachelagrades, och sex andra anrop bearbetades med hjälp av cachen.</span><span class="sxs-lookup"><span data-stu-id="8d9bb-319">The value **\[C:6\]** indicates that the records that were fetched from the database were cached, and six other calls were processed by using the cache.</span></span>

<span data-ttu-id="8d9bb-320">Observera att antalet anrop till datakällan LedgerTransTypeList har minskats från 9 027 till 240.</span><span class="sxs-lookup"><span data-stu-id="8d9bb-320">Notice that the number of calls to the LedgerTransTypeList data source has been reduced from 9,027 to 240.</span></span>

![Spårningsinformation för datamodellen LedgerTransTypeList på sidan för modellmappningsdesigner i RCS](./media/GER-PerfTrace-RCS-TraceInfoInMapping2a.png)

## <a name="review-the-execution-trace-in-finance-and-operations"></a><span data-ttu-id="8d9bb-322">Granska körningsspårningen i Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="8d9bb-322">Review the execution trace in Finance and Operations</span></span>

<span data-ttu-id="8d9bb-323">Förutom RCS kan vissa versioner av Finance and Operations erbjuda funktioner för en ER-ramverk designerupplevelse.</span><span class="sxs-lookup"><span data-stu-id="8d9bb-323">In addition to RCS, some versions of Finance and Operations might offer capabilities for an ER framework designer experience.</span></span> <span data-ttu-id="8d9bb-324">Dessa versioner av Finance and Operations har alternativet **aktivera designläge** som kan aktiveras.</span><span class="sxs-lookup"><span data-stu-id="8d9bb-324">These versions of Finance and Operations have an **Enable design mode** option that can be turned on.</span></span> <span data-ttu-id="8d9bb-325">Du hittar det här alternativet på fliken **Allmänt** på sidan **parametrar elektronisk rapportering** som du öppnar från arbetsytan **elektronisk rapportering**.</span><span class="sxs-lookup"><span data-stu-id="8d9bb-325">You can find this option on the **General** tab of the **Electronic reporting parameters** page, which you can open from the **Electronic reporting** workspace.</span></span>

![Aktivera designlägesalternativet på sidan parametrar för elektronisk rapportering i Finance and Operations](./media/GER-PerfTrace-GER-Parameters-DesignMode.png)

<span data-ttu-id="8d9bb-327">Om du använder någon av dessa versioner av Finance and Operations kan du analysera detaljerna för genererade resultat spårningar direkt i Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="8d9bb-327">If you use one of these versions of Finance and Operations, you can analyze the details of generated performance traces directly in Finance and Operations.</span></span> <span data-ttu-id="8d9bb-328">Du behöver inte exportera dem från Finance and Operations och importera dem till RCS.</span><span class="sxs-lookup"><span data-stu-id="8d9bb-328">You don't have to export them from Finance and Operation and import them into RCS.</span></span>

## <a name="review-the-execution-trace-by-using-external-tools"></a><span data-ttu-id="8d9bb-329">Granska körningsspårningen med hjälp av externa verktyg</span><span class="sxs-lookup"><span data-stu-id="8d9bb-329">Review the execution trace by using external tools</span></span>

### <a name="configure-user-parameters"></a><span data-ttu-id="8d9bb-330">Konfigurera användarparametrar</span><span class="sxs-lookup"><span data-stu-id="8d9bb-330">Configure user parameters</span></span>

1. <span data-ttu-id="8d9bb-331">I Finance and Operations, gå till **Organisationsadministration \> Elektronisk rapportering \> Konfigurationer**.</span><span class="sxs-lookup"><span data-stu-id="8d9bb-331">In Finance and Operations, go to **Organization administration \> Electronic reporting \> Configurations**.</span></span>
2. <span data-ttu-id="8d9bb-332">På sidan **Konfigurationer** i åtgärdsfönstret, på fliken **Konfigurationer** i gruppen **Avancerad inställningar** markerar du **Använd parametrar**.</span><span class="sxs-lookup"><span data-stu-id="8d9bb-332">On the **Configurations** page, on the Action Pane, on the **Configurations** tab, in the **Advanced settings** group, select **User parameters**.</span></span>
3. <span data-ttu-id="8d9bb-333">I dialogrutan **Användarparametrar** i avsnittet **Körningsspårning** i fältet **Körnngsspårningsformat**, välj **PerfView XML**.</span><span class="sxs-lookup"><span data-stu-id="8d9bb-333">In the **User parameters** dialog box, in the **Execution tracing** section, in the **Execution trace format** field, select **PerfView XML**.</span></span>

### <a name="run-the-er-format"></a><span data-ttu-id="8d9bb-334">Kör ER-format</span><span class="sxs-lookup"><span data-stu-id="8d9bb-334">Run the ER format</span></span>

<span data-ttu-id="8d9bb-335">Upprepa stegen i avsnittet [kör ER-format](#run-format) tidigare i det här avsnittet om du vill generera en ny prestandaspårning.</span><span class="sxs-lookup"><span data-stu-id="8d9bb-335">Repeat the steps in the [Run the ER format](#run-format) section earlier in this topic to generate a new performance trace.</span></span>

<span data-ttu-id="8d9bb-336">Observera att en zip-fil kan hämtas i webbläsaren.</span><span class="sxs-lookup"><span data-stu-id="8d9bb-336">Notice that the web browser offers a zip file for download.</span></span> <span data-ttu-id="8d9bb-337">Den här filen innehåller prestandaspårningen i PerfView-format.</span><span class="sxs-lookup"><span data-stu-id="8d9bb-337">This file contains the performance trace in PerfView format.</span></span> <span data-ttu-id="8d9bb-338">Du kan sedan använda prestandaanalysverktyget PerfView för att analysera information om ER-formatkörning.</span><span class="sxs-lookup"><span data-stu-id="8d9bb-338">You can then use the PerfView performance analysis tool to analyze the details of ER format execution.</span></span>
