---
title: Spåra körningen av ER-format för att felsöka prestandaproblem
description: Det här avsnittet innehåller information om hur du använder funktionen för prestandaspårning i elektronisk rapportering (ER) för att felsöka prestandaproblem.
author: NickSelin
ms.date: 06/22/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: 220314
ms.assetid: 2685df16-5ec8-4fd7-9495-c0f653e82567
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: ''
ms.dyn365.ops.version: 10.0.1
ms.openlocfilehash: 7fbec962fea374afdbabaad48a42dad380708678
ms.sourcegitcommit: dbffde1944b9d037124415c28053036c9ef1ecb7
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/23/2021
ms.locfileid: "6295583"
---
# <a name="trace-the-execution-of-er-formats-to-troubleshoot-performance-issues"></a><span data-ttu-id="18bc8-103">Spåra körning av ER-format för att felsöka prestanda problem</span><span class="sxs-lookup"><span data-stu-id="18bc8-103">Trace the execution of ER formats to troubleshoot performance issues</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="18bc8-104">Som en del i processen att utforma konfiguration av elektronisk rapportering (ER) för att generera elektroniska dokument, definierar du den metod som används för att hämta data från programmet och anger den i genererad utdata.</span><span class="sxs-lookup"><span data-stu-id="18bc8-104">As part of the process of designing Electronic reporting (ER) configurations to generate electronic documents, you define the method that is used to get data out of the application and enter it in the output that is generated.</span></span> <span data-ttu-id="18bc8-105">Funktionen för ER-prestationsspårning hjälper till att avsevärt minska både tid och kostnad när det gäller att samla in information om ER-formatkörning och använda den för att felsöka prestandaproblem.</span><span class="sxs-lookup"><span data-stu-id="18bc8-105">The ER performance trace feature helps significantly reduce the time and cost that are involved in collecting the details of ER format execution and using them to troubleshoot performance issues.</span></span> <span data-ttu-id="18bc8-106">I den här självstudien finns riktlinjer för hur du utför prestandaspårning för körda ER-format och hur du använder informationen från dessa spårningar för att förbättra prestanda.</span><span class="sxs-lookup"><span data-stu-id="18bc8-106">This tutorial provides guidelines about how to take performance traces for executed ER formats, and how to use the information from these traces to help improve performance.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="18bc8-107">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="18bc8-107">Prerequisites</span></span>

<span data-ttu-id="18bc8-108">För att slutföra exemplet i den här självstudien måste du ha följande åtkomst:</span><span class="sxs-lookup"><span data-stu-id="18bc8-108">To complete the examples in this tutorial, you must have the following access:</span></span>

- <span data-ttu-id="18bc8-109">Gå till någon av följande roller:</span><span class="sxs-lookup"><span data-stu-id="18bc8-109">Access to one of the following roles:</span></span>

    - <span data-ttu-id="18bc8-110">Utvecklare för elektronisk rapportering</span><span class="sxs-lookup"><span data-stu-id="18bc8-110">Electronic reporting developer</span></span>
    - <span data-ttu-id="18bc8-111">Konsult för funktionen för elektronisk rapportering</span><span class="sxs-lookup"><span data-stu-id="18bc8-111">Electronic reporting functional consultant</span></span>
    - <span data-ttu-id="18bc8-112">Systemadministratör</span><span class="sxs-lookup"><span data-stu-id="18bc8-112">System administrator</span></span>

- <span data-ttu-id="18bc8-113">Åtkomst till den instans av Regulatory Configuration Services (RCS) som har etablerats för samma innehavare som programmet för en av följande roller:</span><span class="sxs-lookup"><span data-stu-id="18bc8-113">Access to the instance of Regulatory Configuration Services (RCS) that has been provisioned for the same tenant as the application, for one of the following roles:</span></span>

    - <span data-ttu-id="18bc8-114">Utvecklare för elektronisk rapportering</span><span class="sxs-lookup"><span data-stu-id="18bc8-114">Electronic reporting developer</span></span>
    - <span data-ttu-id="18bc8-115">Konsult för funktionen för elektronisk rapportering</span><span class="sxs-lookup"><span data-stu-id="18bc8-115">Electronic reporting functional consultant</span></span>
    - <span data-ttu-id="18bc8-116">Systemadministratör</span><span class="sxs-lookup"><span data-stu-id="18bc8-116">System administrator</span></span>

<span data-ttu-id="18bc8-117">Du måste också hämta följande filer och lagra dem lokalt.</span><span class="sxs-lookup"><span data-stu-id="18bc8-117">You must also download and locally store the following files.</span></span>

| <span data-ttu-id="18bc8-118">Fil</span><span class="sxs-lookup"><span data-stu-id="18bc8-118">File</span></span>                                  | <span data-ttu-id="18bc8-119">Innehåll</span><span class="sxs-lookup"><span data-stu-id="18bc8-119">Content</span></span>                               |
|---------------------------------------|---------------------------------------|
| <span data-ttu-id="18bc8-120">Prestandaspårningsmodell.version. 1</span><span class="sxs-lookup"><span data-stu-id="18bc8-120">Performance trace model.version.1</span></span>     | [<span data-ttu-id="18bc8-121">Konfiguration av exempel på ER-datamodell.</span><span class="sxs-lookup"><span data-stu-id="18bc8-121">Sample ER data model configuration</span></span>](https://download.microsoft.com/download/0/a/a/0aa84e48-8040-4c46-b542-e3bf15c9b2ad/Performancetracemodelversion.1.xml)    |
| <span data-ttu-id="18bc8-122">Prestandaspårningsmetadata.version.1</span><span class="sxs-lookup"><span data-stu-id="18bc8-122">Performance trace metadata.version.1</span></span>  | [<span data-ttu-id="18bc8-123">Konfiguration av exempel på ER-metadata.</span><span class="sxs-lookup"><span data-stu-id="18bc8-123">Sample ER metadata configuration</span></span>](https://download.microsoft.com/download/a/9/3/a937e8c4-1f8a-43e4-83ee-7d599cf7d983/Performancetracemetadataversion.1.xml)      |
| <span data-ttu-id="18bc8-124">Prestandaspårningsmappning.version.1.1</span><span class="sxs-lookup"><span data-stu-id="18bc8-124">Performance trace mapping.version.1.1</span></span> | [<span data-ttu-id="18bc8-125">Konfiguration av exempel på ER-modellmappning</span><span class="sxs-lookup"><span data-stu-id="18bc8-125">Sample ER model mapping configuration</span></span>](https://download.microsoft.com/download/7/7/3/77379bdc-7b22-4cfc-9b64-a9147599f931/Performancetracemappingversion1.1.xml) |
| <span data-ttu-id="18bc8-126">Prestandaspårningsformat.version.1.1</span><span class="sxs-lookup"><span data-stu-id="18bc8-126">Performance trace format.version.1.1</span></span>  | [<span data-ttu-id="18bc8-127">Konfiguration av exempel på ER-format.</span><span class="sxs-lookup"><span data-stu-id="18bc8-127">Sample ER format configuration</span></span>](https://download.microsoft.com/download/8/6/8/868ba581-5a06-459e-b173-fb00f038b37f/Performancetraceformatversion1.1.xml)       |

### <a name="configure-er-parameters"></a><span data-ttu-id="18bc8-128">Konfigurera ER-parametrar</span><span class="sxs-lookup"><span data-stu-id="18bc8-128">Configure ER parameters</span></span>

<span data-ttu-id="18bc8-129">Varje ER-prestandaspårning som skapas i programmet lagras som en bilaga till körningsloggposten.</span><span class="sxs-lookup"><span data-stu-id="18bc8-129">Each ER performance trace that is generated in the application is stored as an attachment of the execution log record.</span></span> <span data-ttu-id="18bc8-130">Dokumenthanteringsramverket (DM) används för att hantera dessa bilagor.</span><span class="sxs-lookup"><span data-stu-id="18bc8-130">The Document management (DM) framework is used to manage these attachments.</span></span> <span data-ttu-id="18bc8-131">Du måste konfigurera återställningsparametrar i förväg för att kunna ange vilken typ av DM-dokument som ska användas för att koppla prestandaspårningar.</span><span class="sxs-lookup"><span data-stu-id="18bc8-131">You must configure ER parameters in advance, to specify the DM document type that should be used to attach performance traces.</span></span> <span data-ttu-id="18bc8-132">På arbetsytan **Elektronisk rprogramortering** väljer du **Elektroniska rprogramorteringsparametrar**.</span><span class="sxs-lookup"><span data-stu-id="18bc8-132">In the **Electronic reporting** workspace, select **Electronic reporting parameters**.</span></span> <span data-ttu-id="18bc8-133">Välj sedan sidan **parametrar för elektronisk rapportering** på fliken **bilagor** i fältet **övriga** och sedan den DM-dokumenttyp som du ska använda för prestandaspårning.</span><span class="sxs-lookup"><span data-stu-id="18bc8-133">Then, on the **Electronic reporting parameters** page, on the **Attachments** tab, in the **Others** field, select the DM document type to use for performance traces.</span></span>

![Sida för parametrar för elektronisk rapportering](./media/GER-PerfTrace-GER-Parameters-DocumentType.png)

<span data-ttu-id="18bc8-135">För att vara tillgänglig i sökfältet **Övriga** måste en DM-dokumenttyp konfigureras på följande sätt på sidan **Dokumenttyper** (**Organisationsadministration \> Dokumenthantering \> Dokumenttyper**):</span><span class="sxs-lookup"><span data-stu-id="18bc8-135">To be available in the **Others** lookup field, a DM document type must be configured in the following manner on the **Document types** page (**Organization administration \> Document management \> Document types**):</span></span>

- <span data-ttu-id="18bc8-136">**Klass:** Bifoga fil</span><span class="sxs-lookup"><span data-stu-id="18bc8-136">**Class:** Attach file</span></span>
- <span data-ttu-id="18bc8-137">**Grupp:** fil</span><span class="sxs-lookup"><span data-stu-id="18bc8-137">**Group:** File</span></span>

![Sida för dokumenttyper](./media/GER-PerfTrace-DM-DocumentType.png)

> [!NOTE]
> <span data-ttu-id="18bc8-139">Den valda dokumenttypen måste vara tillgänglig i alla företag i den aktuella instansen eftersom DM-bilagor är företagsspecifika.</span><span class="sxs-lookup"><span data-stu-id="18bc8-139">The selected document type must be available in every company of the current instance, because DM attachments are company-specific.</span></span>

### <a name="configure-rcs-parameters"></a><span data-ttu-id="18bc8-140">Konfigurera RCS-parametrar</span><span class="sxs-lookup"><span data-stu-id="18bc8-140">Configure RCS parameters</span></span>

<span data-ttu-id="18bc8-141">ER-prestandaspårningar som skapas importeras till RCS för analys med hjälp av ER-formatdesigner och ER-mappningsdesigner.</span><span class="sxs-lookup"><span data-stu-id="18bc8-141">ER performance traces that are generated will be imported into RCS for analysis by using the ER format designer and the ER mapping designer.</span></span> <span data-ttu-id="18bc8-142">Eftersom ER-prestandaspårning lagras som bilagor till körningsloggposten som är relaterad till ER-formatet, måste du konfigurera RCS-parametrar i förväg för att ange den DM-dokumenttyp som ska användas för att koppla prestandaspårningar.</span><span class="sxs-lookup"><span data-stu-id="18bc8-142">Because ER performance traces are stored as attachments of the execution log record that is related to the ER format, you must configure RCS parameters in advance, to specify the DM document type that should be used to attach performance traces.</span></span> <span data-ttu-id="18bc8-143">elektronisk I instansen av RCS som har etablerats för ditt företag, i arbetsytan **elektronisk rapportering** väljer du **elektronisk rapportering**.</span><span class="sxs-lookup"><span data-stu-id="18bc8-143">In the instance of RCS that has been provisioned for your company, in the **Electronic reporting** workspace, select **Electronic reporting parameters**.</span></span> <span data-ttu-id="18bc8-144">Välj sedan sidan **parametrar för elektronisk rapportering** på fliken **bilagor** i fältet **övriga** och sedan den DM-dokumenttyp som du ska använda för prestandaspårning.</span><span class="sxs-lookup"><span data-stu-id="18bc8-144">Then, on the **Electronic reporting parameters** page, on the **Attachments** tab, in the **Others** field, select the DM document type to use for performance traces.</span></span>

![Sida för parametrar för elektronisk rapportering i RCS](./media/GER-PerfTrace-RCS-Parameters-DocumentType.png)

<span data-ttu-id="18bc8-146">För att vara tillgänglig i sökfältet **Övriga** måste en DM-dokumenttyp konfigureras på följande sätt på sidan **Dokumenttyper** (**Organisationsadministration \> Dokumenthantering \> Dokumenttyper**):</span><span class="sxs-lookup"><span data-stu-id="18bc8-146">To be available in the **Others** lookup field, a DM document type must be configured in the following manner on the **Document types** page (**Organization administration \> Document management \> Document types**):</span></span>

- <span data-ttu-id="18bc8-147">**Klass:** Bifoga fil</span><span class="sxs-lookup"><span data-stu-id="18bc8-147">**Class:** Attach file</span></span>
- <span data-ttu-id="18bc8-148">**Grupp:** fil</span><span class="sxs-lookup"><span data-stu-id="18bc8-148">**Group:** File</span></span>

## <a name="design-an-er-solution"></a><span data-ttu-id="18bc8-149">Designa en ER-lösning</span><span class="sxs-lookup"><span data-stu-id="18bc8-149">Design an ER solution</span></span>

<span data-ttu-id="18bc8-150">Anta att du har börjat designa en ny ER-lösning för att skapa en ny rapport som visar leverantörstransaktioner.</span><span class="sxs-lookup"><span data-stu-id="18bc8-150">Assume that you've started to design a new ER solution to generate a new report that presents vendor transactions.</span></span> <span data-ttu-id="18bc8-151">För närvarande kan du hitta transaktionerna för en vald leverantör på sidan **leverantörstransaktioner** (gå till **leverantörsreskontra\> leverantörer \> alla leverantörer**, välj en leverantörer och sedan i åtgärdspanelen på fliken **leverantörer** i gruppen **transaktioner** väljer du **transaktioner**).</span><span class="sxs-lookup"><span data-stu-id="18bc8-151">Currently, you can find the transactions for a selected vendor on the **Vendor transactions** page (go to **Account payable \> Vendors \> All vendors**, select a vendor, and then, on the Action Pane, on the **Vendor** tab, in the **Transactions** group, select **Transactions**).</span></span> <span data-ttu-id="18bc8-152">Du vill dock ha alla leverantörstransaktioner samtidigt i ett elektroniskt dokument i XML-format.</span><span class="sxs-lookup"><span data-stu-id="18bc8-152">However, you want to have all vendor transaction at the same time in one electronic document in XML format.</span></span> <span data-ttu-id="18bc8-153">Den här lösningen består av flera ER-konfigurationer som innehåller den nödvändiga datamodellen, metadata, modellmappning och formatkomponenter.</span><span class="sxs-lookup"><span data-stu-id="18bc8-153">This solution will consist of several ER configurations that contain the required data model, metadata, model mapping, and format components.</span></span>

1. <span data-ttu-id="18bc8-154">Logga in på den instans av RCS som har etablerats för ditt företag.</span><span class="sxs-lookup"><span data-stu-id="18bc8-154">Sign in to the instance of RCS that has been provisioned for your company.</span></span>
2. <span data-ttu-id="18bc8-155">I den här självstudien ska du skapa och ändra konfigurationer för exempelföretaget **Litware, Inc**.</span><span class="sxs-lookup"><span data-stu-id="18bc8-155">In this tutorial, you will create and modify configurations for the **Litware, Inc.** sample company.</span></span> <span data-ttu-id="18bc8-156">Kontrollera därför att denna konfigurationsleverantör har lagts till i RCS och valts som aktiv.</span><span class="sxs-lookup"><span data-stu-id="18bc8-156">Therefore, make sure that this configuration provider has been added to RCS and selected as active.</span></span> <span data-ttu-id="18bc8-157">Instruktioner finns i proceduren [skapa konfigurationsleverantörer och markera dem som aktiva](tasks/er-configuration-provider-mark-it-active-2016-11.md).</span><span class="sxs-lookup"><span data-stu-id="18bc8-157">For instructions, see the [Create configuration providers and mark them as active](tasks/er-configuration-provider-mark-it-active-2016-11.md) procedure.</span></span>
3. <span data-ttu-id="18bc8-158">På arbetsytan **Elektronisk rapportering** väljer du panelen **Rapporteringskonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="18bc8-158">In the **Electronic reporting** workspace, select the **Reporting configurations** tile.</span></span>
4. <span data-ttu-id="18bc8-159">På sidan **konfigurationer** importerar du de ER-konfigurationer som du hämtade som en förutsättning i RCS i följande ordning: datamodell, metadata, modellmappning, format.</span><span class="sxs-lookup"><span data-stu-id="18bc8-159">On the **Configurations** page, import the ER configurations that you downloaded as a prerequisite into RCS, in the following order: data model, metadata, model mapping, format.</span></span> <span data-ttu-id="18bc8-160">Följ dessa steg för varje konfiguration:</span><span class="sxs-lookup"><span data-stu-id="18bc8-160">For each configuration, follow these steps:</span></span>

    1. <span data-ttu-id="18bc8-161">På Åtgärdsfönster väljer du **växla \> läs in från XML-fil**.</span><span class="sxs-lookup"><span data-stu-id="18bc8-161">On the Action Pane, select **Exchange \> Load from XML file**.</span></span>
    2. <span data-ttu-id="18bc8-162">Välj **bläddra** om du vill välja en fil för den nödvändiga ER-konfigurationen i XML-format.</span><span class="sxs-lookup"><span data-stu-id="18bc8-162">Select **Browse** to select the appropriate file for the required ER configuration in XML format.</span></span>
    3. <span data-ttu-id="18bc8-163">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="18bc8-163">Select **OK**.</span></span>

    ![Sidan Konfigurationer i RCS](./media/GER-PerfTrace-RCS-ImportedConfigurations.png)

## <a name="run-the-er-solution-to-trace-execution"></a><span data-ttu-id="18bc8-165">Kör ER-lösning för att spåra körning</span><span class="sxs-lookup"><span data-stu-id="18bc8-165">Run the ER solution to trace execution</span></span>

<span data-ttu-id="18bc8-166">Anta att du har skapat den första versionen av ER-lösningen.</span><span class="sxs-lookup"><span data-stu-id="18bc8-166">Assume that you've finished designing the first version of the ER solution.</span></span> <span data-ttu-id="18bc8-167">Du vill nu testa instansen och analysera körningsprestanda.</span><span class="sxs-lookup"><span data-stu-id="18bc8-167">You now want to test it in your instance and analyze execution performance.</span></span>

### <a name="import-an-er-configuration-from-rcs-into-finance-and-operations"></a><a id='import-configuration'></a><span data-ttu-id="18bc8-168">Importera ER-konfigurationer från RCS till Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="18bc8-168">Import an ER configuration from RCS into Finance and Operations</span></span>

1. <span data-ttu-id="18bc8-169">Logga in på programinstansen.</span><span class="sxs-lookup"><span data-stu-id="18bc8-169">Sign in to your application instance.</span></span>
2. <span data-ttu-id="18bc8-170">För den här självstudien ska du importera konfigurationer från din RCS-instans (där du utformar dina ER-komponenter) instansen (där du testar och slutligen använder dem.)</span><span class="sxs-lookup"><span data-stu-id="18bc8-170">For this tutorial, you will import configurations from your RCS instance (where you design your ER components) into your instance (where you test and finally use them).</span></span> <span data-ttu-id="18bc8-171">Därför måste du se till att alla nödvändiga artefakter har förberetts.</span><span class="sxs-lookup"><span data-stu-id="18bc8-171">Therefore, you must make sure that all the required artifacts have been prepared.</span></span> <span data-ttu-id="18bc8-172">För mer information, se proceduren [Importera e-rapporteringskonfigurationer från Regulatory Configuration Services (RCS)](rcs-download-configurations.md).</span><span class="sxs-lookup"><span data-stu-id="18bc8-172">For instructions, see the [Import Electronic reporting (ER) configurations from Regulatory Configuration Services (RCS)](rcs-download-configurations.md) procedure.</span></span>
3. <span data-ttu-id="18bc8-173">Följ dessa steg för att importera konfigurationerna från RCS till programmet:</span><span class="sxs-lookup"><span data-stu-id="18bc8-173">Follow these steps to import the configurations from RCS into the application:</span></span>

    1. <span data-ttu-id="18bc8-174">I arbetsytan **elektronisk rapportering** på panelen för konfigurationsleverantören **Litware, Inc.** väljer du **Databaser**.</span><span class="sxs-lookup"><span data-stu-id="18bc8-174">In the **Electronic reporting** workspace, on the tile for the **Litware, Inc.** configuration provider, select **Repositories**.</span></span>
    2. <span data-ttu-id="18bc8-175">På sidan **Konfigurationsdatabaser** väljer du i rutnätet den befintliga databasen för **RCS**-typ och väljer sedan **Öppna**.</span><span class="sxs-lookup"><span data-stu-id="18bc8-175">On the **Configuration repository** page, select the repository of the **RCS** type, and then select **Open**.</span></span>
    3. <span data-ttu-id="18bc8-176">På snabbfliken **konfigurationer** väljer du konfigurationen **Prestandaspårningsformat**.</span><span class="sxs-lookup"><span data-stu-id="18bc8-176">On the **Configurations** FastTab, select the **Performance trace format** configuration.</span></span>
    4. <span data-ttu-id="18bc8-177">I snabbfliken **Versioner** väljer du version **1.1.** för vald konfiguration och sedan **Importera**.</span><span class="sxs-lookup"><span data-stu-id="18bc8-177">On the **Versions** FastTab, select version **1.1** of the selected configuration, and then select **Import**.</span></span>

    ![Sidan Konfigurationsdatabas](./media/GER-PerfTrace-GER-ImportedConfigurations.png)

<span data-ttu-id="18bc8-179">Motsvarande versioner av datamodell- och modellmappningskonfigurationer importeras automatiskt som förutsättningar för den importerade ER-formatkonfigurationen.</span><span class="sxs-lookup"><span data-stu-id="18bc8-179">The corresponding versions of the data model and model mapping configurations are automatically imported as prerequisites for the imported ER format configuration.</span></span>

### <a name="turn-on-the-er-performance-trace"></a><span data-ttu-id="18bc8-180">Aktivera ER-prestandaspårning</span><span class="sxs-lookup"><span data-stu-id="18bc8-180">Turn on the ER performance trace</span></span>

1. <span data-ttu-id="18bc8-181">Gå till **Organisationsadministration  \> Elektronisk rapportering \> Konfigurationer**.</span><span class="sxs-lookup"><span data-stu-id="18bc8-181">Go to **Organization administration \> Electronic reporting \> Configurations**.</span></span>
2. <span data-ttu-id="18bc8-182">På sidan **Konfigurationer** i åtgärdsfönstret, på fliken **Konfigurationer** i gruppen **Avancerad inställningar** markerar du **Använd parametrar**.</span><span class="sxs-lookup"><span data-stu-id="18bc8-182">On the **Configurations** page, on the Action Pane, on the **Configurations** tab, in the **Advanced settings** group, select **User parameters**.</span></span>
3. <span data-ttu-id="18bc8-183">I dialogrutan **Användarparametrar** i avsnittet **körningsspårning** gör fäljande steg:</span><span class="sxs-lookup"><span data-stu-id="18bc8-183">In the **User parameters** dialog box, in the **Execution tracing** section, follow these steps:</span></span>

    1. <span data-ttu-id="18bc8-184">Du använder fältet **körningsspårningsformat** om du vill ange formatet för den genererade prestandaspårning som körningsinformationen lagras i för ER-format och mappningselement.</span><span class="sxs-lookup"><span data-stu-id="18bc8-184">In the **Execution trace format** field, specify the format of the generated performance trace that the execution details should be stored in for ER format and mapping elements:</span></span>

        - <span data-ttu-id="18bc8-185">**Felsökningsspårningsformat** – Välj det här värdet om du planerar att interaktivt köra ett ER-format som har en kort körningstid.</span><span class="sxs-lookup"><span data-stu-id="18bc8-185">**Debug trace format** – Select this value if you plan to interactively run an ER format that has a short execution time.</span></span> <span data-ttu-id="18bc8-186">En samling detaljer om körningen av ER-formatet startas sedan.</span><span class="sxs-lookup"><span data-stu-id="18bc8-186">The collection of details about ER format execution is then started.</span></span> <span data-ttu-id="18bc8-187">När det här värdet väljs samlar prestandaspårningen in information om den tid som har ägnats åt följande åtgärder:</span><span class="sxs-lookup"><span data-stu-id="18bc8-187">When this value is selected, the performance trace collects information about the time that is spent on the following actions:</span></span>

            - <span data-ttu-id="18bc8-188">Kör varje datakälla i modellmappningen som anropas för att hämta data</span><span class="sxs-lookup"><span data-stu-id="18bc8-188">Running each data source in the model mapping that is called to get data</span></span>
            - <span data-ttu-id="18bc8-189">Behandla varje formatobjekt för att ange data i de utdata som genereras</span><span class="sxs-lookup"><span data-stu-id="18bc8-189">Processing each format item to enter data in the output that is generated</span></span>

            <span data-ttu-id="18bc8-190">Om du väljer värdet **Felsökningsspårningsformat** kan du analysera innehållet i spårningen i ER-åtgärdsdesigner.</span><span class="sxs-lookup"><span data-stu-id="18bc8-190">If you select the **Debug trace format** value, you can analyze the content of the trace in the ER Operation designer.</span></span> <span data-ttu-id="18bc8-191">Där kan du visa ER-formatet eller mappningselementen som nämns i spårningen.</span><span class="sxs-lookup"><span data-stu-id="18bc8-191">There, you can view the ER format or mapping elements that are mentioned in the trace.</span></span>

        - <span data-ttu-id="18bc8-192">**Sammansatt spårningsformat** – Välj det här värdet om du planerar att köra ett ER-format som har en lång körningstid i batchläge.</span><span class="sxs-lookup"><span data-stu-id="18bc8-192">**Aggregated trace format** – Select this value if you plan to run an ER format that has a long execution time in batch mode.</span></span> <span data-ttu-id="18bc8-193">En samling sammanlagda detaljer om körningen av ER-formatet startas sedan.</span><span class="sxs-lookup"><span data-stu-id="18bc8-193">The collection of the aggregated details about ER format execution is then started.</span></span> <span data-ttu-id="18bc8-194">När det här värdet väljs samlar prestandaspårningen in information om den tid som har ägnats åt följande åtgärder:</span><span class="sxs-lookup"><span data-stu-id="18bc8-194">When this value is selected, the performance trace collects information about the time that is spent on the following actions:</span></span>

            - <span data-ttu-id="18bc8-195">Kör varje datakälla i modellmappningen som anropas för att hämta data</span><span class="sxs-lookup"><span data-stu-id="18bc8-195">Running each data source in the model mapping that is called to get data</span></span>
            - <span data-ttu-id="18bc8-196">Kör varje datakälla i formatmappningen som anropas för att hämta data</span><span class="sxs-lookup"><span data-stu-id="18bc8-196">Running each data source in the format mapping that is called to get data</span></span>
            - <span data-ttu-id="18bc8-197">Behandla varje formatobjekt för att ange data i de utdata som genereras</span><span class="sxs-lookup"><span data-stu-id="18bc8-197">Processing each format item to enter data in the output that is generated</span></span>

            <span data-ttu-id="18bc8-198">Värdet **Sammansatt spårningsformat** finns tillgängligt i Microsoft Dynamics 365 Finance version 10.0.20 och senare.</span><span class="sxs-lookup"><span data-stu-id="18bc8-198">The **Aggregated trace format** value is available in Microsoft Dynamics 365 Finance version 10.0.20 and later.</span></span>

            <span data-ttu-id="18bc8-199">I ER-formatdesignern för ER modellmappningsdesignern kan du visa den totala körningstiden för en enskild komponent.</span><span class="sxs-lookup"><span data-stu-id="18bc8-199">In the ER format designer and ER model mapping designer, you can view the total execution time for a single component.</span></span> <span data-ttu-id="18bc8-200">Spårningen innehåller även information om körningen, t.ex. antalet körningar samt den minsta och maximala tiden för en enda körning.</span><span class="sxs-lookup"><span data-stu-id="18bc8-200">Additionally, the trace contains details about the execution, such as the number of executions, and the minimum and maximum time of a single execution.</span></span>

            > [!NOTE]
            > <span data-ttu-id="18bc8-201">Spårningen samlas in utifrån den spårade komponentsökvägen.</span><span class="sxs-lookup"><span data-stu-id="18bc8-201">This trace is collected based on the traced components path.</span></span> <span data-ttu-id="18bc8-202">Statistiken kan därför bli felaktig när en enskild överordnad komponent innehåller flera icke-underordnade komponenter, eller när flera underordnade komponenter har samma namn.</span><span class="sxs-lookup"><span data-stu-id="18bc8-202">Therefore, the statistics might be incorrect when a single parent component contains several unnamed child components, or when several child components have the same name.</span></span>

    2. <span data-ttu-id="18bc8-203">Ange följande alternativ till **ja** för att samla in specifik information om körningen av komponenterna ER-modellmappning och ER-format:</span><span class="sxs-lookup"><span data-stu-id="18bc8-203">Set the following options to **Yes** to collect specific details of the execution of the ER model mapping and ER format components:</span></span>

        - <span data-ttu-id="18bc8-204">**Samla in frestatistik** – när det här alternativet är aktiverat samlar prestandaspårningen in följande information:</span><span class="sxs-lookup"><span data-stu-id="18bc8-204">**Collect query statistics** – When this option is turned on, the performance trace will collect the following information:</span></span>

            - <span data-ttu-id="18bc8-205">Antalet databasanrop som har gjorts av datakällor</span><span class="sxs-lookup"><span data-stu-id="18bc8-205">The number of database calls that were made by data sources</span></span>
            - <span data-ttu-id="18bc8-206">Antalet dubblettanrop till databasen.</span><span class="sxs-lookup"><span data-stu-id="18bc8-206">The number of duplicate calls to the database</span></span>
            - <span data-ttu-id="18bc8-207">Information om SQL-satserna som användes för att göra databasanrop</span><span class="sxs-lookup"><span data-stu-id="18bc8-207">Details of the SQL statements that were used to make database calls</span></span>

        - <span data-ttu-id="18bc8-208">**Spåra åtkomst av cachelagring** – när det här alternativet är aktiverat samlar prestandaspårningen in information om vad som gäller för ER-modell mappningens cache-användning.</span><span class="sxs-lookup"><span data-stu-id="18bc8-208">**Trace access of caching** – When this option is turned on, the performance trace will collect information about the ER model mapping's cache usage.</span></span>
        - <span data-ttu-id="18bc8-209">**Spåra dataåtkomst** – när det här alternativet är aktiverat samlar prestandaspårningen in information om antalet anrop till databasen för körda datakällor av postlisttypen.</span><span class="sxs-lookup"><span data-stu-id="18bc8-209">**Trace data access** – When this option is turned on, the performance trace will collect information about the number of calls to the database for executed data sources of the record list type.</span></span>
        - <span data-ttu-id="18bc8-210">**Spåra listuppräkning** – när det här alternativet är aktiverat samlar prestandaspårningen in information om antalet poster som begärs från datakällor av postlisttypen.</span><span class="sxs-lookup"><span data-stu-id="18bc8-210">**Trace list enumeration** – When this option is turned on, the performance trace will collect information about the number of records that are requested from data sources of the record list type.</span></span>

    > [!NOTE]
    > <span data-ttu-id="18bc8-211">Parametrarna i dialogrutan **användarparametrar** är specifika för användaren och det aktuella företaget.</span><span class="sxs-lookup"><span data-stu-id="18bc8-211">The parameters in the **User parameters** dialog box are specific to the user and the current company.</span></span>

    ![Dialogruta Användarparametrar](./media/GER-PerfTrace-GER-UserParameters.png)

### <a name="run-the-er-format"></a><a id='run-format'></a><span data-ttu-id="18bc8-213">Kör ER-format</span><span class="sxs-lookup"><span data-stu-id="18bc8-213">Run the ER format</span></span>

1. <span data-ttu-id="18bc8-214">Välj företaget **DEMF**.</span><span class="sxs-lookup"><span data-stu-id="18bc8-214">Select the **DEMF** company.</span></span>
2. <span data-ttu-id="18bc8-215">Gå till **Organisationsadministration  \> Elektronisk rapportering \> Konfigurationer**.</span><span class="sxs-lookup"><span data-stu-id="18bc8-215">Go to **Organization administration \> Electronic reporting \> Configurations**.</span></span>
3. <span data-ttu-id="18bc8-216">På sidan **konfigurationer** i konfigurationsträdet väljer du artikeln **Prestandaspårningsformat**.</span><span class="sxs-lookup"><span data-stu-id="18bc8-216">On the **Configurations** page, in the configuration tree, select the **Performance trace format** item.</span></span>
4. <span data-ttu-id="18bc8-217">Klicka på **Kör** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="18bc8-217">On the Action Pane, select **Run**.</span></span>

<span data-ttu-id="18bc8-218">Observera att filen som genereras visar information om 265 transaktioner för sex leverantörer.</span><span class="sxs-lookup"><span data-stu-id="18bc8-218">Notice that the file that is generated presents information about 265 transactions for six vendors.</span></span>

## <a name="review-the-execution-trace"></a><span data-ttu-id="18bc8-219">Granska körningsspårningen</span><span class="sxs-lookup"><span data-stu-id="18bc8-219">Review the execution trace</span></span>

### <a name="export-the-generated-trace-from-the-application"></a><a id='export-trace'></a><span data-ttu-id="18bc8-220">Exportera den genererade spårningen från programmet</span><span class="sxs-lookup"><span data-stu-id="18bc8-220">Export the generated trace from the application</span></span>

<span data-ttu-id="18bc8-221">Prestandaspårningen kopplas från källans ER-format och kan serialiseras till en extern ZIP-fil.</span><span class="sxs-lookup"><span data-stu-id="18bc8-221">Performance traces are decoupled from the source ER format and can be serialized to an external zip file.</span></span>

1. <span data-ttu-id="18bc8-222">Gå till **Organisationsadministration \> Elektronisk rapportering \> Konfiguration av felsökningsloggar**.</span><span class="sxs-lookup"><span data-stu-id="18bc8-222">Go to **Organization administration \> Electronic reporting \> Configuration debug logs**.</span></span>
2. <span data-ttu-id="18bc8-223">På sidan **elektronisk rapportering kör loggar** i det vänstra fönstret i **konfigurationsnamn** väljer du **prestandaspårningsformat** i för att hitta de loggposter som har genererats vid körning av konfigurationen **Prestandaspårningsformat**.</span><span class="sxs-lookup"><span data-stu-id="18bc8-223">On the **Electronic reporting run logs** page, in the left pane, in the **Configuration name** field, select **Performance trace format** to find the log records that have been generated by the execution of the **Performance trace format** configuration.</span></span>
3. <span data-ttu-id="18bc8-224">Välj knappen **Bilagor** (gemsymbolen) längst upp till höger på sidan eller tryck på **Ctrl+Shift+A**.</span><span class="sxs-lookup"><span data-stu-id="18bc8-224">Select the **Attachments** button (the paper clip symbol) in the upper-right corner of the page, or press **Ctrl+Shift+A**.</span></span>

    ![Knappen Bilagor på sidan elektronisk rapportering körningsloggarna](./media/GER-PerfTrace-GER-DebugLog.png)

4. <span data-ttu-id="18bc8-226">På sidan **bilagor för elektroniska rapportering körningsloggar** i åtgärdsfönstret väljer du **öppna** för att få prestandaspårningen som en zip-fil och spara den lokalt.</span><span class="sxs-lookup"><span data-stu-id="18bc8-226">On the **Attachments for Electronic reporting run logs** page, on the Action Pane, select **Open** to get the performance trace as a zip file and store it locally.</span></span>

    ![Bilagor för elektroniska rapportkörningsloggar](./media/GER-PerfTrace-GER-DebugLog-AttachedTrace.png)

> [!NOTE]
> <span data-ttu-id="18bc8-228">Spårningen som genereras har en referens till källans ER-rapport via en unik rapportidentifierare i **GUID**-format.</span><span class="sxs-lookup"><span data-stu-id="18bc8-228">The trace that is generated has a reference to the source ER report via a unique report identifier in **GUID** format only.</span></span> <span data-ttu-id="18bc8-229">Versionsnumret för formatet beaktas inte.</span><span class="sxs-lookup"><span data-stu-id="18bc8-229">The version numbering of the format isn't considered.</span></span>

<span data-ttu-id="18bc8-230">Observera att associationen mellan resultatspårningen som har genererats för det körda ER-formatet och ER-modellmappningen baseras på den rotbeskrivare som användes och den gemensamma datamodellen.</span><span class="sxs-lookup"><span data-stu-id="18bc8-230">Notice that the association between the performance trace that has been generated for the executed ER format and the ER model mapping is based on the root descriptor that was used and the common data model.</span></span> <span data-ttu-id="18bc8-231">Versionsnumret för formatet ochmmdellmappning beaktas inte.</span><span class="sxs-lookup"><span data-stu-id="18bc8-231">The version numbering of the format and model mapping isn't considered.</span></span> <span data-ttu-id="18bc8-232">Inställningen av flaggan **Standard för modellmappning** för modellmappningen beaktas inte heller.</span><span class="sxs-lookup"><span data-stu-id="18bc8-232">The setting of the **Default for model mapping** flag for the model mapping also isn't considered.</span></span>

### <a name="import-the-generated-trace-into-rcs"></a><a id='import-trace'></a><span data-ttu-id="18bc8-233">Importera genererad spårning till RCS.</span><span class="sxs-lookup"><span data-stu-id="18bc8-233">Import the generated trace into RCS</span></span>

1. <span data-ttu-id="18bc8-234">I RCS på arbetsytan **Elektronisk rapportering** väljer du panelen **Rapporteringskonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="18bc8-234">In RCS, in the **Electronic reporting** workspace, select the **Reporting configurations** tile.</span></span>
2. <span data-ttu-id="18bc8-235">På sidan **konfigurationer** i konfigurationsträdet, expandera artikeln **Prestandaspårningsmodell** och väljer artikeln **Prestandaspårningsformat**.</span><span class="sxs-lookup"><span data-stu-id="18bc8-235">On the **Configurations** page, in the configuration tree, expand the **Performance trace model** item, and select the **Performance trace format** item.</span></span>
3. <span data-ttu-id="18bc8-236">Klicka på **Designer** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="18bc8-236">On the Action Pane, select **Designer**.</span></span>
4. <span data-ttu-id="18bc8-237">På snabbfliken **Formatdesigner** på åtgärdsfönstret väljer du **Prestandaspårningsformat**.</span><span class="sxs-lookup"><span data-stu-id="18bc8-237">On the **Format designer** page, on the Action Pane, select **Performance trace**.</span></span>
5. <span data-ttu-id="18bc8-238">I dialogrutan **Inställning av prestandaspårningsresultat** väljer du **Importera prestandaspårning**.</span><span class="sxs-lookup"><span data-stu-id="18bc8-238">In the **Performance trace result settings** dialog box, select **Import performance trace**.</span></span>
6. <span data-ttu-id="18bc8-239">Välj **bläddra** för att markera den zip-fil som du exporterade tidigare.</span><span class="sxs-lookup"><span data-stu-id="18bc8-239">Select **Browse** to select the zip file that you exported earlier.</span></span>
7. <span data-ttu-id="18bc8-240">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="18bc8-240">Select **OK**.</span></span>

    ![Dialogrutan inställningar av prestandaspårningsresultat i RCS](./media/GER-PerfTrace-RCS-ImportedPerfTrace.png)

### <a name="use-the-performance-trace-for-analysis-in-rcs--format-execution"></a><span data-ttu-id="18bc8-242">Använd prestandaspårning för analys i RCS – formatkörning</span><span class="sxs-lookup"><span data-stu-id="18bc8-242">Use the performance trace for analysis in RCS – Format execution</span></span>

1. <span data-ttu-id="18bc8-243">I RCS, på sidan **Formatdesigner** välj **Visa/Dölj** för att expandera innehållet i alla formatobjekt.</span><span class="sxs-lookup"><span data-stu-id="18bc8-243">In RCS, on the **Format designer** page, select **Expand/collapse** to expand the content of all format items.</span></span>

    <span data-ttu-id="18bc8-244">Lägg märke till att ytterligare information visas för vissa artiklar i det aktuella formatet:</span><span class="sxs-lookup"><span data-stu-id="18bc8-244">Notice that additional information is shown for some items of the current format:</span></span>

    - <span data-ttu-id="18bc8-245">Den faktiska tid som användes för att mata in data i det genererade utmatninget med hjälp av formaobjekt</span><span class="sxs-lookup"><span data-stu-id="18bc8-245">The actual time that was spent entering data in the generated output by using the format item</span></span>
    - <span data-ttu-id="18bc8-246">Samma tid uttryckt i procent av den totala tid som användes för att generera hela utdata</span><span class="sxs-lookup"><span data-stu-id="18bc8-246">The same time expressed as a percentage of the total time that was spent generating the whole output</span></span>

    ![Formatdesignersida i RCS](./media/GER-PerfTrace-RCS-TraceInfoInFormat.png)

2. <span data-ttu-id="18bc8-248">Stäng sidan **Formatdesigner**.</span><span class="sxs-lookup"><span data-stu-id="18bc8-248">Close **Format designer** page.</span></span>

### <a name="use-the-performance-trace-for-analysis-in-rcs--model-mapping"></a><a id='use-trace'></a><span data-ttu-id="18bc8-249">Använd prestandaspårning för analys i RCS – modellmappning</span><span class="sxs-lookup"><span data-stu-id="18bc8-249">Use the performance trace for analysis in RCS – Model mapping</span></span>

1. <span data-ttu-id="18bc8-250">I RCS på sidan **konfigurationer** i konfigurationsträdet väljer du artikeln **Prestandaspårningsmappning**.</span><span class="sxs-lookup"><span data-stu-id="18bc8-250">In RCS, on the **Configurations** page, in the configuration tree, select the **Performance trace mapping** item.</span></span>
2. <span data-ttu-id="18bc8-251">Klicka på **Designer** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="18bc8-251">On the Action Pane, select **Designer**.</span></span>
3. <span data-ttu-id="18bc8-252">Välj **Designer**.</span><span class="sxs-lookup"><span data-stu-id="18bc8-252">Select **Designer**.</span></span>
4. <span data-ttu-id="18bc8-253">På snabbfliken **Modellmappningsdesigner** på åtgärdsfönstret väljer du **Prestandaspårningsformat**.</span><span class="sxs-lookup"><span data-stu-id="18bc8-253">On the **Model mapping designer** page, on the Action Pane, select **Performance trace**.</span></span>
5. <span data-ttu-id="18bc8-254">Välj spårningen som du importerade tidigare.</span><span class="sxs-lookup"><span data-stu-id="18bc8-254">Select the trace that you imported earlier.</span></span>
6. <span data-ttu-id="18bc8-255">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="18bc8-255">Select **OK**.</span></span>

<span data-ttu-id="18bc8-256">Lägg märke till att ny information blir tillgänglig för vissa datakällobjekt i den aktuella modellmappningen:</span><span class="sxs-lookup"><span data-stu-id="18bc8-256">Notice that new information becomes available for some data source items of the current model mapping:</span></span>

- <span data-ttu-id="18bc8-257">Den faktiska tid som användes för att hämta data genom att använda datakällan</span><span class="sxs-lookup"><span data-stu-id="18bc8-257">The actual time that was spent getting data by using the data source</span></span>
- <span data-ttu-id="18bc8-258">Samma tid uttryckt i procent av den totala tid som användes för att köra hela modellmappningen</span><span class="sxs-lookup"><span data-stu-id="18bc8-258">The same time expressed as a percentage of the total time that was spent running the whole model mapping</span></span>

<span data-ttu-id="18bc8-259">Observera att du informerar dig om att den aktuella modellmappningen duplicerar databas begäranden när datakällan VendTable/\<Relations/VendTrans.VendTable\_AccountNum körs.</span><span class="sxs-lookup"><span data-stu-id="18bc8-259">Notice that ER informs you that the current model mapping duplicates database requests while the VendTable/\<Relations/VendTrans.VendTable\_AccountNum data source is run.</span></span> <span data-ttu-id="18bc8-260">Den här dubbletten sker eftersom listan med leverantörstransaktioner anropas två gånger för varje förslagen leverantörspost:</span><span class="sxs-lookup"><span data-stu-id="18bc8-260">This duplication occurs because the list of vendor transactions is called two times for each iterated vendor record:</span></span>

- <span data-ttu-id="18bc8-261">Ett anrop görs för att ange information om varje transaktion i datamodellen, baserat på konfigurerade bindningar.</span><span class="sxs-lookup"><span data-stu-id="18bc8-261">One call is made to enter details of each transaction in the data model, based on configured bindings.</span></span>
- <span data-ttu-id="18bc8-262">Ett samtal görs för att ange det beräknade antalet transaktioner per leverantör i datamodellen.</span><span class="sxs-lookup"><span data-stu-id="18bc8-262">One call is made to enter the calculated number of transactions per vendor in the data model.</span></span>

![Meddelande om dubbla databasbegäranden på sidan modellmappningsdesigner i RCS](./media/GER-PerfTrace-RCS-TraceInfoInMapping1.png)

<span data-ttu-id="18bc8-264">Värdet **\[Q:530\]** anger att VendTrans-registret har anropats 530 gånger för att returnera en post från registret till datakällan VendTable/\<Relations/VendTrans.VendTable\_AccountNum.</span><span class="sxs-lookup"><span data-stu-id="18bc8-264">The value **\[Q:530\]** indicates that the VendTrans table was called 530 times to return a record from that table to the VendTable/\<Relations/VendTrans.VendTable\_AccountNum data source.</span></span> <span data-ttu-id="18bc8-265">Värdet **\[530\]** anger att datakällan VendTable/\<Relations/VendTrans.VendTable\_AccountNum har anropats 530 gånger för att returnera en post från den datakällan och ange informationen från den i datamodellen.</span><span class="sxs-lookup"><span data-stu-id="18bc8-265">The value **\[530\]** indicates that the VendTable/\<Relations/VendTrans.VendTable\_AccountNum data source was called 530 times to return a record from that data source and enter the details from it in the data model.</span></span>

<span data-ttu-id="18bc8-266">Vi rekommenderar att du använder cache för datakällan VendTable/\<Relations/VendTrans.VendTable\_AccountNum för att minska antalet anrop som görs för att få information om 265-transaktioner och förbättra modellmappningens prestanda.</span><span class="sxs-lookup"><span data-stu-id="18bc8-266">We recommend that you use caching for the VendTable/\<Relations/VendTrans.VendTable\_AccountNum data source, to reduce the number of calls that are made to get the details for 265 transactions and help improve the performance of the model mapping.</span></span>

<span data-ttu-id="18bc8-267">Det kan också vara användbart om du vill minska antalet anrop som görs till datakällan LedgerTransTypeList.</span><span class="sxs-lookup"><span data-stu-id="18bc8-267">It can also be useful to reduce the number of calls that are made to the LedgerTransTypeList data source.</span></span> <span data-ttu-id="18bc8-268">Denna datakälla används för att koppla varje värde i **LedgerTransType**-uppräkningen till dess etikett.</span><span class="sxs-lookup"><span data-stu-id="18bc8-268">This data source is used to associate each value of the **LedgerTransType** enumeration with its label.</span></span> <span data-ttu-id="18bc8-269">Genom att använda den här datakällan kan du hitta en lämplig etikett och ange den i datamodellen för varje leverantörstransaktion.</span><span class="sxs-lookup"><span data-stu-id="18bc8-269">By using this data source, you can find an appropriate label and enter it in the data model for each vendor transaction.</span></span> <span data-ttu-id="18bc8-270">Det aktuella antalet anrop till den här datakällan (9 027) är ganska högt för 265 transaktioner.</span><span class="sxs-lookup"><span data-stu-id="18bc8-270">The current number of calls to this data source (9,027) is quite high for 265 transactions.</span></span>

![Sidan modellmappningsdesigner i RCS, visar 9 027 anrop till datakällan](./media/GER-PerfTrace-RCS-TraceInfoInMapping1a.png)

## <a name="improve-the-model-mapping-based-on-information-from-the-execution-trace"></a><span data-ttu-id="18bc8-272">Förbättra modellmappningen utifrån information från körningsspårningen</span><span class="sxs-lookup"><span data-stu-id="18bc8-272">Improve the model mapping based on information from the execution trace</span></span>

### <a name="modify-the-logic-of-the-model-mapping"></a><span data-ttu-id="18bc8-273">Ändra logiken för modellmappningen</span><span class="sxs-lookup"><span data-stu-id="18bc8-273">Modify the logic of the model mapping</span></span>

1. <span data-ttu-id="18bc8-274">Gör så här om du vill använda cache för att förhindra att anrop till databasen dupliceras:</span><span class="sxs-lookup"><span data-stu-id="18bc8-274">Follow these steps to use caching, to help prevent duplicate calls to the database:</span></span>

    1. <span data-ttu-id="18bc8-275">I RCS, på sidan **Modellmappingsdesigner** i fönstret **Datakällor** väljer du objektet **VendTable**.</span><span class="sxs-lookup"><span data-stu-id="18bc8-275">In RCS, on the **Model mapping designer** page, in the **Data sources** pane, select the **VendTable** item.</span></span>
    2. <span data-ttu-id="18bc8-276">Välj **cache**.</span><span class="sxs-lookup"><span data-stu-id="18bc8-276">Select **Cache**.</span></span>
    3. <span data-ttu-id="18bc8-277">Expandera objektet **VendTable**  expandera listan med 1:n-relationer för VendTable-datakälla (**\<Relationer** objekt) och välj objektet **VendTrans.VendTable\_AccountNum**.</span><span class="sxs-lookup"><span data-stu-id="18bc8-277">Expand the **VendTable** item, expand the list of one-to-many relations for the VendTable data source (the **\<Relations** item), and select the **VendTrans.VendTable\_AccountNum** item.</span></span>
    4. <span data-ttu-id="18bc8-278">Välj **cache**.</span><span class="sxs-lookup"><span data-stu-id="18bc8-278">Select **Cache**.</span></span>

    ![Cachelagring för att förhindra dubbla anrop](./media/GER-PerfTrace-RCS-ChangeMapping-Cache.png)

2. <span data-ttu-id="18bc8-280">Följ dessa steg för att hämta datakällan LedgerTransTypeList till omfattningen för datakällan VendTable:</span><span class="sxs-lookup"><span data-stu-id="18bc8-280">Follow these steps to bring the LedgerTransTypeList data source into the scope of the VendTable data source:</span></span>

    1. <span data-ttu-id="18bc8-281">I fönstret **datakälltyper** expanderar du objektet **funktioner** och markerar objektet **beräknade fält**.</span><span class="sxs-lookup"><span data-stu-id="18bc8-281">In the **Data source types** pane, expand the **Functions** item, and select the **Calculated field** item.</span></span>
    2. <span data-ttu-id="18bc8-282">Markera objektet **VendTable** i fönstret **datakällor**.</span><span class="sxs-lookup"><span data-stu-id="18bc8-282">In the **Data sources** pane, select the **VendTable** item.</span></span>
    3. <span data-ttu-id="18bc8-283">Markera **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="18bc8-283">Select **Add**.</span></span>
    4. <span data-ttu-id="18bc8-284">Skriv **\$TransType** i fältet **Namn**.</span><span class="sxs-lookup"><span data-stu-id="18bc8-284">In the **Name** field, enter **\$TransType**.</span></span>
    5. <span data-ttu-id="18bc8-285">Välj **Redigera recept**.</span><span class="sxs-lookup"><span data-stu-id="18bc8-285">Select **Edit formula**.</span></span>
    6. <span data-ttu-id="18bc8-286">I fältet **Recept** ange **LedgerTransTypeList**.</span><span class="sxs-lookup"><span data-stu-id="18bc8-286">In the **Formula** field, enter **LedgerTransTypeList**.</span></span>
    7. <span data-ttu-id="18bc8-287">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="18bc8-287">Select **Save**.</span></span>
    8. <span data-ttu-id="18bc8-288">Stäng sidan **receptredigering**.</span><span class="sxs-lookup"><span data-stu-id="18bc8-288">Close the **Formula editor** page.</span></span>
    9. <span data-ttu-id="18bc8-289">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="18bc8-289">Click **OK**.</span></span>

3. <span data-ttu-id="18bc8-290">Gör följande om du vill göra cachelagring av fältet **\$TransType**:</span><span class="sxs-lookup"><span data-stu-id="18bc8-290">Follow these steps to do caching of the **\$TransType** field:</span></span>

    1. <span data-ttu-id="18bc8-291">Välj bjektet **LedgerTransTypeList**.</span><span class="sxs-lookup"><span data-stu-id="18bc8-291">Select the **LedgerTransTypeList** item.</span></span>
    2. <span data-ttu-id="18bc8-292">Välj **cache**.</span><span class="sxs-lookup"><span data-stu-id="18bc8-292">Select **Cache**.</span></span>
    3. <span data-ttu-id="18bc8-293">Välj objektet **VendTable.\$TransType**.</span><span class="sxs-lookup"><span data-stu-id="18bc8-293">Select the **VendTable.\$TransType** item.</span></span>
    4. <span data-ttu-id="18bc8-294">Välj **cache**.</span><span class="sxs-lookup"><span data-stu-id="18bc8-294">Select **Cache**.</span></span>

    ![Cachelagra inställningar för fältet $TransType](./media/GER-PerfTrace-RCS-ChangeMapping-Cache2.png)

4. <span data-ttu-id="18bc8-296">Följ dessa steg för att ändra **\$TransTypeRecord** så att det börjar använda cachelagrade fältet **\$TransType**:</span><span class="sxs-lookup"><span data-stu-id="18bc8-296">Follow these steps to change the **\$TransTypeRecord** field so that it starts to use the cached **\$TransType** field:</span></span>

    1. <span data-ttu-id="18bc8-297">I fönstret **Datakällor**, expandera objektet **VendTable** expandera objektet **\<Relations** expandera objektet **VendTrans.VendTable\_AccountNum** och välj sedan  **VendTable. VendTrans.VendTable\_AccountNum.\$TransTypeRecord**.</span><span class="sxs-lookup"><span data-stu-id="18bc8-297">In the **Data sources** pane, expand the **VendTable** item, expand the **\<Relations** item, expand the **VendTrans.VendTable\_AccountNum** item, and select the **VendTable. VendTrans.VendTable\_AccountNum.\$TransTypeRecord** item.</span></span>
    2. <span data-ttu-id="18bc8-298">Välj **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="18bc8-298">Select **Edit**.</span></span>
    3. <span data-ttu-id="18bc8-299">Välj **Redigera recept**.</span><span class="sxs-lookup"><span data-stu-id="18bc8-299">Select **Edit formula**.</span></span>
    4. <span data-ttu-id="18bc8-300">I fältet **formel** hittar du följande uttryck:</span><span class="sxs-lookup"><span data-stu-id="18bc8-300">In the **Formula** field, find the following expression:</span></span>

        <span data-ttu-id="18bc8-301">FIRSTORNULL (WHERE (LedgerTransTypeList, LedgerTransTypeList.Enum = \@.TransType))</span><span class="sxs-lookup"><span data-stu-id="18bc8-301">FIRSTORNULL (WHERE (LedgerTransTypeList, LedgerTransTypeList.Enum = \@.TransType))</span></span>

    5. <span data-ttu-id="18bc8-302">I fältet **formel** anger du följande uttryck:</span><span class="sxs-lookup"><span data-stu-id="18bc8-302">In the **Formula** field, enter the following expression:</span></span>

        <span data-ttu-id="18bc8-303">FIRSTORNULL (WHERE (VendTable.'\$TransType', VendTable.'\$TransType'.Enum = \@.TransType)).</span><span class="sxs-lookup"><span data-stu-id="18bc8-303">FIRSTORNULL (WHERE (VendTable.'\$TransType', VendTable.'\$TransType'.Enum = \@.TransType)).</span></span>

    6. <span data-ttu-id="18bc8-304">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="18bc8-304">Select **Save**.</span></span>
    7. <span data-ttu-id="18bc8-305">Stäng sidan **receptredigering**.</span><span class="sxs-lookup"><span data-stu-id="18bc8-305">Close the **Formula editor** page.</span></span>
    8. <span data-ttu-id="18bc8-306">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="18bc8-306">Select **OK**.</span></span>

5. <span data-ttu-id="18bc8-307">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="18bc8-307">Select **Save**.</span></span>
6. <span data-ttu-id="18bc8-308">Stäng sidan **modellmappningsdesigner**.</span><span class="sxs-lookup"><span data-stu-id="18bc8-308">Close the **Model mapping designer** page.</span></span>
7. <span data-ttu-id="18bc8-309">Stäng sidan **modellmappningar**.</span><span class="sxs-lookup"><span data-stu-id="18bc8-309">Close the **Model mappings** page.</span></span>

### <a name="complete-the-modified-version-of-the-er-model-mapping"></a><span data-ttu-id="18bc8-310">Slutför den ändrade versionen av ER-modellmappningen</span><span class="sxs-lookup"><span data-stu-id="18bc8-310">Complete the modified version of the ER model mapping</span></span>

1. <span data-ttu-id="18bc8-311">I RCS, på sidan **Konfigurationer** på snabbfliken **Versioner** FastTab, välj version **1.2** av konfigurationen **prestandaspårningsmappning**.</span><span class="sxs-lookup"><span data-stu-id="18bc8-311">In RCS, on the **Configurations** page, on the **Versions** FastTab, select version **1.2** of the **Performance trace mapping** configuration.</span></span>
2. <span data-ttu-id="18bc8-312">Välj **Ändra status**.</span><span class="sxs-lookup"><span data-stu-id="18bc8-312">Select **Change status**.</span></span>
3. <span data-ttu-id="18bc8-313">Välj **Slutför**.</span><span class="sxs-lookup"><span data-stu-id="18bc8-313">Select **Complete**.</span></span>

### <a name="import-the-modified-er-model-mapping-configuration-from-rcs-into-the-application"></a><span data-ttu-id="18bc8-314">Importera den modifierade ER-modellmappningskonfigurationen från RCS till programmet</span><span class="sxs-lookup"><span data-stu-id="18bc8-314">Import the modified ER model mapping configuration from RCS into the application</span></span>

<span data-ttu-id="18bc8-315">Upprepa stegen i avsnittet [Importera en ER-konfiguration från RCS till Finance and Operations](#import-configuration) tidigare i det här avsnittet om du vill importera version 1.2 av konfigurationen **Prestandaspårningsmappning**.</span><span class="sxs-lookup"><span data-stu-id="18bc8-315">Repeat the steps in the [Import an ER configuration from RCS into Finance and Operations](#import-configuration) section earlier in this topic to import version 1.2 of the **Performance trace mapping** configuration.</span></span>

## <a name="run-the-modified-er-solution-to-trace-execution"></a><span data-ttu-id="18bc8-316">Kör modifierad ER-lösning för att spåra körning</span><span class="sxs-lookup"><span data-stu-id="18bc8-316">Run the modified ER solution to trace execution</span></span>

### <a name="run-the-er-format"></a><span data-ttu-id="18bc8-317">Kör ER-format</span><span class="sxs-lookup"><span data-stu-id="18bc8-317">Run the ER format</span></span>

<span data-ttu-id="18bc8-318">Upprepa stegen i avsnittet [kör ER-format](#run-format) tidigare i det här avsnittet om du vill generera en ny prestandaspårning.</span><span class="sxs-lookup"><span data-stu-id="18bc8-318">Repeat the steps in the [Run the ER format](#run-format) section earlier in this topic to generate a new performance trace.</span></span>

## <a name="work-with-the-execution-trace"></a><span data-ttu-id="18bc8-319">Arbeta med körningsspårningen</span><span class="sxs-lookup"><span data-stu-id="18bc8-319">Work with the execution trace</span></span>

### <a name="export-the-generated-trace-from-the-application"></a><span data-ttu-id="18bc8-320">Exportera den genererade spårningen från programmet</span><span class="sxs-lookup"><span data-stu-id="18bc8-320">Export the generated trace from the application</span></span>

<span data-ttu-id="18bc8-321">Upprepa stegen i avsnittet [exportera den genererade spårningen från programmet](#export-trace) tidigare i det här avsnittet om du vill spara en ny prestandaspårning lokalt.</span><span class="sxs-lookup"><span data-stu-id="18bc8-321">Repeat the steps in the [Export the generated trace from the application](#export-trace) section earlier in this topic to save a new performance trace locally.</span></span>

### <a name="import-the-generated-trace-into-rcs"></a><span data-ttu-id="18bc8-322">Importera genererad spårning till RCS.</span><span class="sxs-lookup"><span data-stu-id="18bc8-322">Import the generated trace into RCS</span></span>

<span data-ttu-id="18bc8-323">tiUpprepa stegen i avsnittet [importera den genererade spårningen till RCS](#import-trace) tidigare i det här avsnittet om du vill importera den nya prestandaspårningen till RCS.</span><span class="sxs-lookup"><span data-stu-id="18bc8-323">Repeat the steps in the [Import the generated trace into RCS](#import-trace) section earlier in this topic to import the new performance trace into RCS.</span></span>

### <a name="use-the-performance-trace-for-analysis-in-rcs--model-mapping"></a><span data-ttu-id="18bc8-324">Använd prestandaspårning för analys i RCS – modellmappning</span><span class="sxs-lookup"><span data-stu-id="18bc8-324">Use the performance trace for analysis in RCS – Model mapping</span></span>

<span data-ttu-id="18bc8-325">Upprepa stegen i avsnittet [Använd prestandaspårning för analys i RCS – modellmappning](#use-trace) tidigare i det här avsnittet om du vill analysera den senaste prestandaspårningen.</span><span class="sxs-lookup"><span data-stu-id="18bc8-325">Repeat the steps in the [Use the performance trace for analysis in RCS – Model mapping](#use-trace) section earlier in this topic to analyze the latest performance trace.</span></span>

<span data-ttu-id="18bc8-326">Observera att justeringarna som du har gjort av modellmappningen har eliminerat dubbla frågor till databasen.</span><span class="sxs-lookup"><span data-stu-id="18bc8-326">Notice that the adjustments that you made to the model mapping have eliminated duplicate queries to database.</span></span> <span data-ttu-id="18bc8-327">Antalet anrop till databasregister och datakällor för den här modellmappningen har också minskats.</span><span class="sxs-lookup"><span data-stu-id="18bc8-327">The number of calls to database tables and data sources for this model mapping has been also reduced.</span></span> <span data-ttu-id="18bc8-328">Därför har hela ER-lösningens prestanda förbättrats.</span><span class="sxs-lookup"><span data-stu-id="18bc8-328">Therefore, the performance of the whole ER solution has improved.</span></span>

![Spårningsinformation för datamodellen VendTable på sidan för modellmappningsdesigner i RCS](./media/GER-PerfTrace-RCS-TraceInfoInMapping2.png)

<span data-ttu-id="18bc8-330">I spårningsinformationen indikerar värdet **\[12\]** för VendTable-datakällan att denna datakälla har anropats 12 gånger.</span><span class="sxs-lookup"><span data-stu-id="18bc8-330">In the trace information, the value **\[12\]** for the VendTable data source indicates that this data source was called 12 times.</span></span> <span data-ttu-id="18bc8-331">Värdet **\[Q:6\]** anger att sex anrop översattes till databasanrop till VendTable-registret.</span><span class="sxs-lookup"><span data-stu-id="18bc8-331">The value **\[Q:6\]** indicates that six calls were translated to database calls to the VendTable table.</span></span> <span data-ttu-id="18bc8-332">Värdet **\[C:6\]** indikerar att posterna som hämtades från databasen cachelagrades, och sex andra anrop bearbetades med hjälp av cachen.</span><span class="sxs-lookup"><span data-stu-id="18bc8-332">The value **\[C:6\]** indicates that the records that were fetched from the database were cached, and six other calls were processed by using the cache.</span></span>

<span data-ttu-id="18bc8-333">Observera att antalet anrop till datakällan LedgerTransTypeList har minskats från 9 027 till 240.</span><span class="sxs-lookup"><span data-stu-id="18bc8-333">Notice that the number of calls to the LedgerTransTypeList data source has been reduced from 9,027 to 240.</span></span>

![Spårningsinformation för datamodellen LedgerTransTypeList på sidan för modellmappningsdesigner i RCS](./media/GER-PerfTrace-RCS-TraceInfoInMapping2a.png)

## <a name="review-the-execution-trace-in-the-application"></a><span data-ttu-id="18bc8-335">Granska körningsspårningen i programmet</span><span class="sxs-lookup"><span data-stu-id="18bc8-335">Review the execution trace in the application</span></span>

<span data-ttu-id="18bc8-336">Förutom RCS kan vissa versioner erbjuda funktioner för en ER-ramverk designerupplevelse.</span><span class="sxs-lookup"><span data-stu-id="18bc8-336">In addition to RCS, some versions might offer capabilities for an ER framework designer experience.</span></span> <span data-ttu-id="18bc8-337">Dessa versioner har alternativet **aktivera designläge** som kan aktiveras.</span><span class="sxs-lookup"><span data-stu-id="18bc8-337">These versions have an **Enable design mode** option that can be turned on.</span></span> <span data-ttu-id="18bc8-338">Du hittar det här alternativet på fliken **Allmänt** på sidan **parametrar elektronisk rapportering** som du öppnar från arbetsytan **elektronisk rapportering**.</span><span class="sxs-lookup"><span data-stu-id="18bc8-338">You can find this option on the **General** tab of the **Electronic reporting parameters** page, which you can open from the **Electronic reporting** workspace.</span></span>

![Aktivera alternativet designläge på sidan parametrar för elektronisk rapportering](./media/GER-PerfTrace-GER-Parameters-DesignMode.png)

<span data-ttu-id="18bc8-340">Om du använder någon av dessa versioner kan du analysera detaljerna för genererade resultat spårningar direkt i programmet.</span><span class="sxs-lookup"><span data-stu-id="18bc8-340">If you use one of these versions, you can analyze the details of generated performance traces directly in the application.</span></span> <span data-ttu-id="18bc8-341">Du behöver inte exportera dem från programmet och importera dem till RCS.</span><span class="sxs-lookup"><span data-stu-id="18bc8-341">You don't have to export them from the application and import them into RCS.</span></span>

## <a name="review-the-execution-trace-by-using-external-tools"></a><span data-ttu-id="18bc8-342">Granska körningsspårningen med hjälp av externa verktyg</span><span class="sxs-lookup"><span data-stu-id="18bc8-342">Review the execution trace by using external tools</span></span>

### <a name="configure-user-parameters"></a><span data-ttu-id="18bc8-343">Konfigurera användarparametrar</span><span class="sxs-lookup"><span data-stu-id="18bc8-343">Configure user parameters</span></span>

1. <span data-ttu-id="18bc8-344">Gå till **Organisationsadministration  \> Elektronisk rapportering \> Konfigurationer**.</span><span class="sxs-lookup"><span data-stu-id="18bc8-344">Go to **Organization administration \> Electronic reporting \> Configurations**.</span></span>
2. <span data-ttu-id="18bc8-345">På sidan **Konfigurationer** i åtgärdsfönstret, på fliken **Konfigurationer** i gruppen **Avancerad inställningar** markerar du **Använd parametrar**.</span><span class="sxs-lookup"><span data-stu-id="18bc8-345">On the **Configurations** page, on the Action Pane, on the **Configurations** tab, in the **Advanced settings** group, select **User parameters**.</span></span>
3. <span data-ttu-id="18bc8-346">I dialogrutan **Användarparametrar** i avsnittet **Körningsspårning** i fältet **Körnngsspårningsformat**, välj **PerfView XML**.</span><span class="sxs-lookup"><span data-stu-id="18bc8-346">In the **User parameters** dialog box, in the **Execution tracing** section, in the **Execution trace format** field, select **PerfView XML**.</span></span>

### <a name="run-the-er-format"></a><span data-ttu-id="18bc8-347">Kör ER-format</span><span class="sxs-lookup"><span data-stu-id="18bc8-347">Run the ER format</span></span>

<span data-ttu-id="18bc8-348">Upprepa stegen i avsnittet [kör ER-format](#run-format) tidigare i det här avsnittet om du vill generera en ny prestandaspårning.</span><span class="sxs-lookup"><span data-stu-id="18bc8-348">Repeat the steps in the [Run the ER format](#run-format) section earlier in this topic to generate a new performance trace.</span></span>

<span data-ttu-id="18bc8-349">Observera att en zip-fil kan hämtas i webbläsaren.</span><span class="sxs-lookup"><span data-stu-id="18bc8-349">Notice that the web browser offers a zip file for download.</span></span> <span data-ttu-id="18bc8-350">Den här filen innehåller prestandaspårningen i PerfView-format.</span><span class="sxs-lookup"><span data-stu-id="18bc8-350">This file contains the performance trace in PerfView format.</span></span> <span data-ttu-id="18bc8-351">Du kan sedan använda prestandaanalysverktyget PerfView för att analysera information om ER-formatkörning.</span><span class="sxs-lookup"><span data-stu-id="18bc8-351">You can then use the PerfView performance analysis tool to analyze the details of ER format execution.</span></span>

![Information om prestandaspårning i PerfView-format](./media/GER-PerfTrace2-PerfViewTrace1.PNG)

## <a name="use-external-tools-to-review-an-execution-trace-that-includes-database-queries"></a><span data-ttu-id="18bc8-353">Använd externa verktyg för att granska en körningsspårning som omfattar databasfrågor</span><span class="sxs-lookup"><span data-stu-id="18bc8-353">Use external tools to review an execution trace that includes database queries</span></span>

<span data-ttu-id="18bc8-354">På grund av de förbättringar som har gjorts i ER-ramverk innehåller den prestandaspårning som genereras i PerfView-format fler detaljer om ER-formatkörning.</span><span class="sxs-lookup"><span data-stu-id="18bc8-354">Because of improvements that have been made to the ER framework, the performance trace that is generated in PerfView format now offers more details about ER format execution.</span></span> <span data-ttu-id="18bc8-355">I Microsoft Dynamics 365 for Finance and Operations version 10.0.4 (juli 2019) kan den här spårningen även innehålla information om utförda SQL-frågor till programdatabasen.</span><span class="sxs-lookup"><span data-stu-id="18bc8-355">In Microsoft Dynamics 365 for Finance and Operations version 10.0.4 (July 2019), this trace can also include details of executed SQL queries to the application database.</span></span>

### <a name="configure-user-parameters"></a><span data-ttu-id="18bc8-356">Konfigurera användarparametrar</span><span class="sxs-lookup"><span data-stu-id="18bc8-356">Configure user parameters</span></span>

1. <span data-ttu-id="18bc8-357">Gå till **Organisationsadministration** \> **Elektronisk rapportering** \> **Konfigurationer**.</span><span class="sxs-lookup"><span data-stu-id="18bc8-357">Go to **Organization administration** \> **Electronic reporting** \> **Configurations**.</span></span>
2. <span data-ttu-id="18bc8-358">På sidan **Konfigurationer** i åtgärdsfönstret, på fliken **Konfigurationer** i gruppen **Avancerad inställningar** markerar du **Använd parametrar**.</span><span class="sxs-lookup"><span data-stu-id="18bc8-358">On the **Configurations** page, on the Action Pane, on the **Configurations** tab, in the **Advanced settings** group, select **User parameters**.</span></span>
3. <span data-ttu-id="18bc8-359">I dialogrutan **Användarparametrar** i avsnittet **körningsspårning** ange följande parametrar:</span><span class="sxs-lookup"><span data-stu-id="18bc8-359">In the **User parameters** dialog box, in the **Execution tracing** section, set the following parameters:</span></span>

    - <span data-ttu-id="18bc8-360">I fältet **körningsspårningsformat**, välj **PerfView XML**.</span><span class="sxs-lookup"><span data-stu-id="18bc8-360">In the **Execution trace format** field, select **PerfView XML**.</span></span>
    - <span data-ttu-id="18bc8-361">Ställ in alternativet **Samla in frågestatistik** till **Ja**.</span><span class="sxs-lookup"><span data-stu-id="18bc8-361">Set the **Collect query statistics** option to **Yes**.</span></span>
    - <span data-ttu-id="18bc8-362">Ställ in alternativet **Spårningsfråga** till **Ja**.</span><span class="sxs-lookup"><span data-stu-id="18bc8-362">Set the **Trace query** option to **Yes**.</span></span>

    ![Avsnitt för körningsspårning, dialogrutan användarparametrar](./media/GER-PerfTrace2-GER-UserParameters.PNG)

### <a name="run-the-er-format"></a><span data-ttu-id="18bc8-364">Kör ER-format</span><span class="sxs-lookup"><span data-stu-id="18bc8-364">Run the ER format</span></span>

<span data-ttu-id="18bc8-365">Upprepa stegen i avsnittet [kör ER-format](#run-format) tidigare i det här avsnittet om du vill generera en ny prestandaspårning.</span><span class="sxs-lookup"><span data-stu-id="18bc8-365">Repeat the steps in the [Run the ER format](#run-format) section earlier in this topic to generate a new performance trace.</span></span>

<span data-ttu-id="18bc8-366">Observera att en zip-fil kan hämtas i webbläsaren.</span><span class="sxs-lookup"><span data-stu-id="18bc8-366">Notice that the web browser offers a zip file for download.</span></span> <span data-ttu-id="18bc8-367">Den här filen innehåller prestandaspårningen i PerfView-format.</span><span class="sxs-lookup"><span data-stu-id="18bc8-367">This file contains the performance trace in PerfView format.</span></span> <span data-ttu-id="18bc8-368">Du kan sedan använda prestandaanalysverktyget PerfView för att analysera information om ER-formatkörning.</span><span class="sxs-lookup"><span data-stu-id="18bc8-368">You can then use the PerfView performance analysis tool to analyze the details of ER format execution.</span></span> <span data-ttu-id="18bc8-369">I den här spårningen finns nu information om åtkomst till SQL-databasen under körningen av ER-formatet.</span><span class="sxs-lookup"><span data-stu-id="18bc8-369">This trace now includes the details of SQL database access during the execution of the ER format.</span></span>

![Spårningsinformation för det körda återställningsformatet i PerfView](./media/GER-PerfTrace2-PerfViewTrace2.PNG)

## <a name="additional-resources"></a><span data-ttu-id="18bc8-371">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="18bc8-371">Additional resources</span></span>

- [<span data-ttu-id="18bc8-372">Översikt över elektronisk rapportering</span><span class="sxs-lookup"><span data-stu-id="18bc8-372">Electronic Reporting overview</span></span>](general-electronic-reporting.md)
- [<span data-ttu-id="18bc8-373">Förbättra prestanda för ER-lösningar genom att lägga till parametriserade datakällor för BERÄKNADE FÄLT</span><span class="sxs-lookup"><span data-stu-id="18bc8-373">Improve performance of ER solutions by adding parameterized CALCULATED FIELD data sources</span></span>](er-calculated-field-ds-performance.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
