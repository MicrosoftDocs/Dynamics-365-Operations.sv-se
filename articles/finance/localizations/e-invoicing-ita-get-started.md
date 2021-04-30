---
title: Kom i gång med e-fakturering för Italien
description: Det här avsnittet innehåller information som hjälper dig att komma igång med e-fakturering för Italien.
author: gionoder
ms.date: 09/22/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: 140977a6eac145f35870d3516a4b0d0c794afe4b
ms.sourcegitcommit: 951393b05bf409333cb3c7ad977bcaa804aa801b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/13/2021
ms.locfileid: "5894787"
---
# <a name="get-started-with-electronic-invoicing-for-italy"></a><span data-ttu-id="7b587-103">Kom i gång med e-fakturering för Italien</span><span class="sxs-lookup"><span data-stu-id="7b587-103">Get started with Electronic invoicing for Italy</span></span>

[!include [banner](../includes/banner.md)]


> [!IMPORTANT]
> <span data-ttu-id="7b587-104">E-fakturering för Italien kanske för närvarande inte stöder alla funktioner som är tillgängliga för elektroniska fakturor i Microsoft Dynamics 365 Finance och Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="7b587-104">Electronic invoicing for Italy might not currently support all the functions that are available for electronic invoices in Microsoft Dynamics 365 Finance and Dynamics 365 Supply Chain Management.</span></span> 

<span data-ttu-id="7b587-105">Det här avsnittet innehåller information som hjälper dig att komma igång med e-fakturering för Italien.</span><span class="sxs-lookup"><span data-stu-id="7b587-105">This topic provides information that will help you get started with Electronic invoicing for Italy.</span></span> <span data-ttu-id="7b587-106">Den guidar dig genom de konfigurationssteg som är beroende av RCS (Regulatory Configuration Services) och Finance.</span><span class="sxs-lookup"><span data-stu-id="7b587-106">It guides you through the configuration steps that are country-dependent in Regulatory Configuration Services (RCS) and Finance.</span></span> <span data-ttu-id="7b587-107">Det guidar dig också genom processen att skicka elektroniska fakturor som genereras i det italienska formatet **FatturaPA** via tjänsten och den förklarar hur du granskar resultaten av bearbetningen.</span><span class="sxs-lookup"><span data-stu-id="7b587-107">It also guides you through the process for submitting electronic invoices that are generated in the Italy-specific **FatturaPA** format through the service, and it explains how to review the results of processing.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="7b587-108">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="7b587-108">Prerequisites</span></span>

<span data-ttu-id="7b587-109">Innan du slutför stegen i det här avsnittet måste du slutföra stegen i [komma igång med e-fakturering](e-invoicing-get-started.md).</span><span class="sxs-lookup"><span data-stu-id="7b587-109">Before you complete the steps in this topic, you must complete the steps in [Get started with Electronic invoicing](e-invoicing-get-started.md).</span></span>

## <a name="rcs-setup"></a><span data-ttu-id="7b587-110">Inställning av RCS</span><span class="sxs-lookup"><span data-stu-id="7b587-110">RCS setup</span></span>

<span data-ttu-id="7b587-111">Under RCS-inställningar ska du utföra följande uppgifter:</span><span class="sxs-lookup"><span data-stu-id="7b587-111">During the RCS setup, you will complete these tasks:</span></span>

1. <span data-ttu-id="7b587-112">Importera e-faktureringsfunktionen för export av kunders elektroniska fakturor i format **FatturaPA**.</span><span class="sxs-lookup"><span data-stu-id="7b587-112">Import the e-Invoicing feature for the export of customer electronic invoices in the **FatturaPA** format.</span></span>
2. <span data-ttu-id="7b587-113">Granska de formatkonfigurationer som krävs för att generera, skicka och ta emot svar om elektroniska fakturor.</span><span class="sxs-lookup"><span data-stu-id="7b587-113">Review the format configurations that are required to generate, submit, and receive responses about electronic invoices.</span></span>
3. <span data-ttu-id="7b587-114">Konfigurera de händelser som stöder överföringsscenarier för elektronisk faktura.</span><span class="sxs-lookup"><span data-stu-id="7b587-114">Configure the events that support the electronic invoice submission scenarios.</span></span>
4. <span data-ttu-id="7b587-115">Publicera e-faktureringsfunktionen.</span><span class="sxs-lookup"><span data-stu-id="7b587-115">Publish the e-Invoicing feature.</span></span>

> [!NOTE]
> <span data-ttu-id="7b587-116">"e-faktureringsfunktionen" är det allmänna namnet för resursen som är konfigurerad och publicerad för att använda servern för e-fakturering.</span><span class="sxs-lookup"><span data-stu-id="7b587-116">"The e-Invoicing feature" is the generic name for the resource that is configured and published to consume the Electronic invoicing server.</span></span> <span data-ttu-id="7b587-117">I detta fall, export av kunders elektroniska fakturor är den e-faktureringsfunktion som du ställer in.</span><span class="sxs-lookup"><span data-stu-id="7b587-117">In this case, the export of customer electronic invoices is the e-Invoicing feature that you will set up.</span></span>

## <a name="import-the-e-invoicing-feature"></a><span data-ttu-id="7b587-118">Importera e-faktureringsfunktion</span><span class="sxs-lookup"><span data-stu-id="7b587-118">Import the e-Invoicing feature</span></span>

1. <span data-ttu-id="7b587-119">Logga in på RCS-kontot.</span><span class="sxs-lookup"><span data-stu-id="7b587-119">Sign in to your RCS account.</span></span>
2. <span data-ttu-id="7b587-120">I arbetsytan **globaliseringsfunktioner** i avsnittet **Funktioner**, välj panelen **e-fakturering**.</span><span class="sxs-lookup"><span data-stu-id="7b587-120">In the **Globalization features** workspace, in the **Features** section, select the **e-Invoicing** tile.</span></span>
3. <span data-ttu-id="7b587-121">På sidan **e-faktureringsfunktioner** väljer du **Importera** för att importera e-faktureringsfunktion från den globala databasen.</span><span class="sxs-lookup"><span data-stu-id="7b587-121">On the **e-Invoicing Features** page, select **Import** to import the e-Invoicing feature from the Global repository.</span></span>

    > [!NOTE]
    > <span data-ttu-id="7b587-122">Om listan över tillgängliga funktioner inte visas väljer du **synkronisera**.</span><span class="sxs-lookup"><span data-stu-id="7b587-122">If you don't see the list of available features, select **Synchronize**.</span></span> 

4. <span data-ttu-id="7b587-123">Välj funktionen **export av e-fakturor (IT)** och välj sedan **Importera**.</span><span class="sxs-lookup"><span data-stu-id="7b587-123">Select the **e-Invoices Export (IT)** feature, and then select **Import**.</span></span>

![Importera funktionen export av e-fakturor (IT)](media/e-Invoicing-services-get-started-ITA-Select-Import-e-Invoicing-feature.png)

<span data-ttu-id="7b587-125">När du importerar funktionen **exportera e-fakturor (IT)** från den globala databasen, importeras även alla inställningar som beskrivs i de följande avsnitten.</span><span class="sxs-lookup"><span data-stu-id="7b587-125">When you import the **e-Invoices Export (IT)** feature from the Global repository, all the settings that are described in the next sections are also imported.</span></span>

## <a name="create-a-new-version-of-the-e-invoices-export-it-feature"></a><span data-ttu-id="7b587-126">Skapa en ny version av funktionen export av e-fakturor (IT)</span><span class="sxs-lookup"><span data-stu-id="7b587-126">Create a new version of the e-Invoices Export (IT) feature</span></span>

1. <span data-ttu-id="7b587-127">På sidan **e-faktureringsfunktioner** på fliken **Versioner** välj Ändra status **Ny**.</span><span class="sxs-lookup"><span data-stu-id="7b587-127">On the **e-Invoicing Features** page, on the **Versions** tab, select **New**.</span></span> 

    ![Lägger till en ny version av e-faktureringsfunktion](media/e-Invoicing-services-get-started-ITA-Select-New-e-Invoicing-feature-version.png)

    <span data-ttu-id="7b587-129">Därefter ska du konfigurera formaten för elektronisk rapportering (ER) som är kopplade till e-faktureringsfunktionen.</span><span class="sxs-lookup"><span data-stu-id="7b587-129">Next, you will configure the Electronic reporting (ER) formats that are associated with the e-Invoicing feature.</span></span>

2. <span data-ttu-id="7b587-130">På fliken **Konfigurationer** välj **Lägg till** för att hantera konfigurationsversionerna.</span><span class="sxs-lookup"><span data-stu-id="7b587-130">On the **Configurations** tab, select **Add** to manage the configuration versions.</span></span>

    ![Hantera konfigurationsversioner av e-faktureringsfunktion](media/e-Invoicing-services-get-started-ITA-Manage-e-Invoicing-feature-configurations.png)

    <span data-ttu-id="7b587-132">I det här steget ska du lägga till och konfigurera ER-formaten för olika filer som används för att exportera italienska e-fakturor.</span><span class="sxs-lookup"><span data-stu-id="7b587-132">In this step, you're adding and configuring the ER formats of different files that are used to export Italian e-invoices.</span></span> <span data-ttu-id="7b587-133">För italienska FatturaPA e-fakturor använder du antingen följande standardkonfigurationer eller de anpassade konfigurationerna som du använder för e-fakturering:</span><span class="sxs-lookup"><span data-stu-id="7b587-133">For Italian FatturaPA e-invoices, use either the following standard configurations or the actual customized configurations that you use for e-invoicing:</span></span>

    - <span data-ttu-id="7b587-134">Försäljningsfaktura (IT)</span><span class="sxs-lookup"><span data-stu-id="7b587-134">Sales invoice (IT)</span></span>
    - <span data-ttu-id="7b587-135">Projektfaktura (IT)</span><span class="sxs-lookup"><span data-stu-id="7b587-135">Project invoice (IT)</span></span>

    <span data-ttu-id="7b587-136">När du skapar en e-faktureringsfunktion som härleds från en annan e-faktureringsfunktion ärvs alla ER-format från den ursprungliga funktionen.</span><span class="sxs-lookup"><span data-stu-id="7b587-136">When you create an e-Invoicing feature that is derived from another e-Invoicing feature, all ER formats are inherited from the original feature.</span></span>

3. <span data-ttu-id="7b587-137">Välj en specifik konfiguration för ER-formatfil.</span><span class="sxs-lookup"><span data-stu-id="7b587-137">Select a specific ER format file configuration.</span></span>
4. <span data-ttu-id="7b587-138">Välj **Redigera** eller **Visa** för att öppna sidan **Formatdesigner**.</span><span class="sxs-lookup"><span data-stu-id="7b587-138">Select **Edit** or **View** to open the **Format designer** page.</span></span>

    ![Öppna sidan Formatdesigner](media/e-Invoicing-services-get-started-ITA-Configuration-ER-format-designer.png)

5. <span data-ttu-id="7b587-140">Använd sidan **Formatdesigner** för att redigera och visa filkonfigurationerna i ER-format.</span><span class="sxs-lookup"><span data-stu-id="7b587-140">Use the **Format designer** page to edit and view the ER format file configurations.</span></span>

    ![Formatdesignersida](media/e-Invoicing-services-get-started-ITA-ER-format-designer.png)

## <a name="manage-the-e-invoicing-feature-setups"></a><span data-ttu-id="7b587-142">Hantera inställningen för e-faktureringsfunktionen</span><span class="sxs-lookup"><span data-stu-id="7b587-142">Manage the e-Invoicing feature setups</span></span>

- <span data-ttu-id="7b587-143">på sidan **e-faktureringsfunktioner** på fliken **Inställningar** välj **Lägg till**, **Ta bort** eller **Redigera** för att hantera inställningsfunktionen för e-fakturering.</span><span class="sxs-lookup"><span data-stu-id="7b587-143">On the **e-Invoicing Features** page, on the **Setups** tab, select **Add**, **Delete**, or **Edit** to manage the e-Invoicing feature setups.</span></span>

![Hantera inställningen för e-faktureringsfunktionen](media/e-Invoicing-services-get-started-ITA-Manage-e-Invoicing-feature-setup.png)

<span data-ttu-id="7b587-145">I det här steget konfigurerar du de händelser som gäller för elektroniska fakturor, inklusive generering av XML-utdatafilerna i **FatturaPA**-format och digital signering (om det behövs).</span><span class="sxs-lookup"><span data-stu-id="7b587-145">In this step, you configure the events that are applicable to electronic invoices, including generation of the XML output files in **FatturaPA** format and digital signing (if required).</span></span>

### <a name="configure-the-sales-invoice-feature-setup"></a><span data-ttu-id="7b587-146">Konfigurera inställningen av funktionen Sales-faktura</span><span class="sxs-lookup"><span data-stu-id="7b587-146">Configure the Sales invoice feature setup</span></span>

1. <span data-ttu-id="7b587-147">På sidan **e-faktureringsfunktioner** på fliken **Inställningar** i kolumnen **Funktionsinställningar** välj **Försäljningsfaktura**.</span><span class="sxs-lookup"><span data-stu-id="7b587-147">On the **e-Invoicing Features** page, on the **Setups** tab, in the **Feature setup** column, select **Sales invoice**.</span></span>
2. <span data-ttu-id="7b587-148">Välj **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="7b587-148">Select **Edit**.</span></span>
3. <span data-ttu-id="7b587-149">På sidan **Inställning av funktionsversion** välj fliken **Åtgärder** för att hantera listan med åtgärder.</span><span class="sxs-lookup"><span data-stu-id="7b587-149">On the **Feature version setup** page, select the **Actions** tab to manage the list of actions.</span></span> <span data-ttu-id="7b587-150">Åtgärder definierar en lista med operationer som måste köras i en sekventiell ordning för att händelsen ska kunna utföras.</span><span class="sxs-lookup"><span data-stu-id="7b587-150">Actions define a list of operations that must be run in sequential order to accomplish full execution of the event.</span></span>

    ![Fliken åtgärder](media/e-Invoicing-services-get-started-ITA-Select-Actions.png)

    | <span data-ttu-id="7b587-152">Åtgärds-ID</span><span class="sxs-lookup"><span data-stu-id="7b587-152">Action ID</span></span> | <span data-ttu-id="7b587-153">Namn på åtgärd</span><span class="sxs-lookup"><span data-stu-id="7b587-153">Action name</span></span>        | <span data-ttu-id="7b587-154">Åtgärdsbeskrivning</span><span class="sxs-lookup"><span data-stu-id="7b587-154">Action description</span></span>                                     |
    |-----------|--------------------|--------------------------------------------------------|
    | <span data-ttu-id="7b587-155">1</span><span class="sxs-lookup"><span data-stu-id="7b587-155">1</span></span>         | <span data-ttu-id="7b587-156">Transformera dokument</span><span class="sxs-lookup"><span data-stu-id="7b587-156">Transform document</span></span> | <span data-ttu-id="7b587-157">Skapa e-fakturans XML-fil i formatet **FatturaPA**.</span><span class="sxs-lookup"><span data-stu-id="7b587-157">Create the e-invoice XML file in **FatturaPA** format.</span></span> |
    | <span data-ttu-id="7b587-158">2</span><span class="sxs-lookup"><span data-stu-id="7b587-158">2</span></span>         | <span data-ttu-id="7b587-159">Signera dokument</span><span class="sxs-lookup"><span data-stu-id="7b587-159">Sign document</span></span>      | <span data-ttu-id="7b587-160">Använd en digital signatur i XML-filen.</span><span class="sxs-lookup"><span data-stu-id="7b587-160">Apply a digital signature to the XML file.</span></span>             |

4. <span data-ttu-id="7b587-161">Välj fliken **tillämplighetsregler** om du vill visa och underhålla tillämplighetsreglerna.</span><span class="sxs-lookup"><span data-stu-id="7b587-161">Select the **Applicability rules** tab to view and maintain the applicability rules.</span></span> <span data-ttu-id="7b587-162">Tillämplighetsregler definierar i vilket sammanhang åtgärden ska köras.</span><span class="sxs-lookup"><span data-stu-id="7b587-162">Applicability rules define the context where the action will be run.</span></span>

    ![Fliken tillämplighetsregler](media/e-Invoicing-services-get-started-ITA-Select-Applicability-rules.png)

5. <span data-ttu-id="7b587-164">Välj fliken **Variabler** om du vill visa och underhålla variablerna.</span><span class="sxs-lookup"><span data-stu-id="7b587-164">Select the **Variables** tab to view and maintain the variables.</span></span>

    ![Fliken Variabler](media/e-Invoicing-services-get-started-ITA-Select-Variables.png)

6. <span data-ttu-id="7b587-166">Definiera de offentliga variabler som krävs för att köra åtgärderna.</span><span class="sxs-lookup"><span data-stu-id="7b587-166">Define the public variables that are required to run the actions.</span></span>

### <a name="configure-the-project-invoice-feature-setup"></a><span data-ttu-id="7b587-167">Konfigurera inställningen av funktionen projektfaktura</span><span class="sxs-lookup"><span data-stu-id="7b587-167">Configure the Project invoice feature setup</span></span> 

<span data-ttu-id="7b587-168">Stegen och inställningarna som krävs för att konfigurera funktionsinställning **Projektfaktura** är mycket liknande steget och inställningar för funktionsinställningen **Försäljningsfaktura**.</span><span class="sxs-lookup"><span data-stu-id="7b587-168">The steps and settings that are required to configure the **Project invoice** feature setup are very similar to the steps and settings for the **Sales invoice** feature setup.</span></span> <span data-ttu-id="7b587-169">När du arbetar med projektfakturor följer du procedurerna för försäljningsfakturor.</span><span class="sxs-lookup"><span data-stu-id="7b587-169">When you work with project invoices, see the procedures for sales invoices.</span></span>

## <a name="assign-the-e-invoicing-feature-to-the-environment"></a><span data-ttu-id="7b587-170">Tilldela e-faktureringsfunktionen till miljön</span><span class="sxs-lookup"><span data-stu-id="7b587-170">Assign the e-Invoicing feature to the environment</span></span>

1. <span data-ttu-id="7b587-171">På sidan **e-faktureringsfunktioner** på fliken **Miljöer** välj Ändra status **Aktivera**.</span><span class="sxs-lookup"><span data-stu-id="7b587-171">On the **e-Invoicing Features** page, on the **Environments** tab, select **Enable**.</span></span>
2. <span data-ttu-id="7b587-172">I fältet **miljö** välj miljön.</span><span class="sxs-lookup"><span data-stu-id="7b587-172">In the **Environment** field, select the environment.</span></span>
3. <span data-ttu-id="7b587-173">I fältet **gäller från** väljer du det datum då miljön ska börja gälla.</span><span class="sxs-lookup"><span data-stu-id="7b587-173">In the **Effective from** field, select the date when the environment should become effective.</span></span>
4. <span data-ttu-id="7b587-174">Välj **Aktivera**.</span><span class="sxs-lookup"><span data-stu-id="7b587-174">Select **Enable**.</span></span> 

![Aktivera en e-faktureringsmiljö](media/e-Invoicing-services-get-started-ITA-Enable-e-Invoicing-environment.png)

## <a name="publish-the-e-invoicing-feature"></a><span data-ttu-id="7b587-176">Publicera e-faktureringsfunktion</span><span class="sxs-lookup"><span data-stu-id="7b587-176">Publish the e-invoicing feature</span></span>

<span data-ttu-id="7b587-177">Du kan publicera e-faktureringsfunktionen genom att ändra versionsstatus till **slutförd** eller **publicerad**.</span><span class="sxs-lookup"><span data-stu-id="7b587-177">You can publish the e-Invoicing feature by changing the version status to **Completed** or **Published**.</span></span>

### <a name="change-the-version-status-to-completed"></a><span data-ttu-id="7b587-178">Ändra versionsstatus till slutförd</span><span class="sxs-lookup"><span data-stu-id="7b587-178">Change the version status to Completed</span></span>

1. <span data-ttu-id="7b587-179">På sidan **e-faktureringsfunktion** på fliken **Versioner**, välj den version av e-faktureringsfunktionen som har status **Utkast**.</span><span class="sxs-lookup"><span data-stu-id="7b587-179">On the **e-Invoicing Features** page, on the **Versions** tab, select the version of the e-Invoicing feature that has a status of **Draft**.</span></span>
2. <span data-ttu-id="7b587-180">Välj **Ändra status \> Slutför**.</span><span class="sxs-lookup"><span data-stu-id="7b587-180">Select **Change status \> Complete**.</span></span> 

### <a name="change-the-version-status-to-published"></a><span data-ttu-id="7b587-181">Ändra versionsstatus till publicerad</span><span class="sxs-lookup"><span data-stu-id="7b587-181">Change the version status to Published</span></span> 

1. <span data-ttu-id="7b587-182">På sidan **e-faktureringsfunktion** på fliken **Versioner**, välj den version av e-faktureringsfunktionen som har status **Slutförd**.</span><span class="sxs-lookup"><span data-stu-id="7b587-182">On the **e-Invoicing Features** page, on the **Versions** tab, select the version of the e-Invoicing feature that has a status of **Completed**.</span></span>
2. <span data-ttu-id="7b587-183">Välj **Ändra status \> Publicera**.</span><span class="sxs-lookup"><span data-stu-id="7b587-183">Select **Change status \> Publish**.</span></span>

![Ändra status för e-faktureringsfunktionen](media/e-Invoicing-services-get-started-ITA-Change-status-of-e-Invoicing-feature.png)

## <a name="set-up-electronic-invoicing-integration-in-finance"></a><span data-ttu-id="7b587-185">Ställ in integrering av e-fakturering i Finance</span><span class="sxs-lookup"><span data-stu-id="7b587-185">Set up Electronic invoicing integration in Finance</span></span>

<span data-ttu-id="7b587-186">Under inställningar av Finance ska du utföra följande uppgifter:</span><span class="sxs-lookup"><span data-stu-id="7b587-186">During the setup of Finance, you will complete these tasks:</span></span>

1. <span data-ttu-id="7b587-187">Importera ER-datamodell, ER-datamodellmappning och kontextkonfigurationer för FatturaPA e-fakturor.</span><span class="sxs-lookup"><span data-stu-id="7b587-187">Import the ER data model, the ER data model mapping, and the context configurations for FatturaPA e-invoices.</span></span>
2. <span data-ttu-id="7b587-188">Konfigurera det certifikat som krävs för digital signering av italienska e-fakturor.</span><span class="sxs-lookup"><span data-stu-id="7b587-188">Configure the certificate that is required to digitally sign Italian e-invoices.</span></span>

### <a name="import-the-er-data-model-data-model-mapping-and-formats"></a><span data-ttu-id="7b587-189">Importera ER-datamodellen, datamodellmappningen och formaten</span><span class="sxs-lookup"><span data-stu-id="7b587-189">Import the ER data model, data model mapping, and formats</span></span>

1. <span data-ttu-id="7b587-190">I arbetsytan **elektronisk rapportering** kontrollera att konfigurationsleverantören **Tjänst för affärsdokument** anges till **Aktiv**.</span><span class="sxs-lookup"><span data-stu-id="7b587-190">In the **Electronic reporting** workspace, verify that the **Business Document Service** configuration provider is set to **Active**.</span></span>
2. <span data-ttu-id="7b587-191">Välj **Databaser**.</span><span class="sxs-lookup"><span data-stu-id="7b587-191">Select **Repositories**.</span></span>
3. <span data-ttu-id="7b587-192">Välj **Global resurs \> Öppna**.</span><span class="sxs-lookup"><span data-stu-id="7b587-192">Select **Global resource \> Open**.</span></span>
4. <span data-ttu-id="7b587-193">Importera **Fakturamodell**, **Mappning av fakturamodell** och **Kontextmodell för kundfaktura**.</span><span class="sxs-lookup"><span data-stu-id="7b587-193">Import **Invoice model**, **Invoice model mapping**, and **Customer invoice context model**.</span></span>

#### <a name="turn-on-the-feature-for-exporting-customer-electronic-invoices-for-italy"></a><span data-ttu-id="7b587-194">Aktivera funktionen för att exportera kunders elektroniska fakturor för Italien</span><span class="sxs-lookup"><span data-stu-id="7b587-194">Turn on the feature for exporting customer electronic invoices for Italy</span></span>

1. <span data-ttu-id="7b587-195">Gå till **organisationsadministration \> inställning \> parametrar för elektroniska dokument**.</span><span class="sxs-lookup"><span data-stu-id="7b587-195">Go to **Organization administration \> Setup \> Electronic document parameters**.</span></span>
2. <span data-ttu-id="7b587-196">På fliken **Funktioner** markerar du kryssrutan **Aktivera** i raden för funktionsreferens **IT00036**.</span><span class="sxs-lookup"><span data-stu-id="7b587-196">On the **Features** tab, select the **Enabled** check box in the row for feature reference **IT00036**.</span></span>

![Aktivera funktionen FatturaPA](media/e-Invoicing-services-get-started-ITA-Enable-FatturaPA-feature.png)

#### <a name="configure-electronic-documents"></a><span data-ttu-id="7b587-198">Konfigurera elektroniska dokument</span><span class="sxs-lookup"><span data-stu-id="7b587-198">Configure electronic documents</span></span>

1. <span data-ttu-id="7b587-199">Gå till **organisationsadministration \> inställning \> parametrar för elektroniska dokument**.</span><span class="sxs-lookup"><span data-stu-id="7b587-199">Go to **Organization administration \> Setup \> Electronic document parameters**.</span></span>
2. <span data-ttu-id="7b587-200">På fliken **Elektroniskt dokument** välj **Lägg till** och ange de register som krävs för att generera italienska e-fakturor:</span><span class="sxs-lookup"><span data-stu-id="7b587-200">On the **Electronic document** tab, select **Add**, and enter the tables that are required to generate Italian e-invoices:</span></span>

    - <span data-ttu-id="7b587-201">**Registernamn:** Kundfakturajournal</span><span class="sxs-lookup"><span data-stu-id="7b587-201">**Table name:** Customer invoice journal</span></span>
    - <span data-ttu-id="7b587-202">**Registernamn:** projektfaktura</span><span class="sxs-lookup"><span data-stu-id="7b587-202">**Table name:** Project invoice</span></span>

3. <span data-ttu-id="7b587-203">Definiera ett relaterat dokumentsammanhang för varje register.</span><span class="sxs-lookup"><span data-stu-id="7b587-203">For each table, define a related document context:</span></span>

    - <span data-ttu-id="7b587-204">För **Kundfakturajournaler** anger du **Kundfakturakontext**.</span><span class="sxs-lookup"><span data-stu-id="7b587-204">For **Customer invoice journal**, select **Customer invoice context**.</span></span>
    - <span data-ttu-id="7b587-205">För **Projektfaktura**, ange **Projektfaktura kontext**.</span><span class="sxs-lookup"><span data-stu-id="7b587-205">For **Project invoice**, select **Project invoice context**.</span></span>

![Ställ in svarstyper](media/e-Invoicing-services-get-started-ITA-Set-up-response-types.png)

## <a name="electronic-invoice-processing"></a><span data-ttu-id="7b587-207">Elektronisk fakturabearbetning</span><span class="sxs-lookup"><span data-stu-id="7b587-207">Electronic invoice processing</span></span>

<span data-ttu-id="7b587-208">Under bearbetningen i Finance ska du utföra följande uppgifter:</span><span class="sxs-lookup"><span data-stu-id="7b587-208">During processing in Finance, you will complete these tasks:</span></span>

1. <span data-ttu-id="7b587-209">Skapa italienska e-fakturor via E-fakturering</span><span class="sxs-lookup"><span data-stu-id="7b587-209">Generate Italian e-invoices through Electronic invoicing</span></span>
2. <span data-ttu-id="7b587-210">Visa körningsloggarna och granska resultaten av bearbetningen</span><span class="sxs-lookup"><span data-stu-id="7b587-210">View the execution logs and review the results of processing</span></span>

### <a name="generate-electronic-invoices"></a><span data-ttu-id="7b587-211">Generera elektroniska fakturor</span><span class="sxs-lookup"><span data-stu-id="7b587-211">Generate electronic invoices</span></span>

<span data-ttu-id="7b587-212">När du har aktiverat funktionen **konfigurerbara integrering för e-fakturering** och aktiverat funktionen **IT00036** kommer den gamla Finance-processen för att generera italienska e-fakturor inte längre kunna användas.</span><span class="sxs-lookup"><span data-stu-id="7b587-212">After you turn on the **Configurable Electronic invoicing integration** feature and activate the **IT00036** feature, the old Finance process for generating Italian e-invoices can no longer be used.</span></span> <span data-ttu-id="7b587-213">Den ersätts med en ny process som kallas **skicka elektroniska dokument**.</span><span class="sxs-lookup"><span data-stu-id="7b587-213">It's replaced by a new process that is named **Submit electronic documents**.</span></span>

<span data-ttu-id="7b587-214">Du kan skicka dokumenten manuellt, baserat på efterfrågan på e-fakturadokument.</span><span class="sxs-lookup"><span data-stu-id="7b587-214">You can submit the documents manually, based on your demand for e-invoice documents.</span></span>

> [!NOTE]
> <span data-ttu-id="7b587-215">Innan du fortsätter kontrollerar du att inställningarna som krävs för italienska e-fakturorna är slutförda.</span><span class="sxs-lookup"><span data-stu-id="7b587-215">Before you continue, verify that the setup that is required for Italian e-invoices was completed.</span></span> <span data-ttu-id="7b587-216">Mer information finns i [Elektroniska kundfakturor](./emea-ita-e-invoices.md).</span><span class="sxs-lookup"><span data-stu-id="7b587-216">For more information, see [Customer electronic invoices](./emea-ita-e-invoices.md).</span></span> <span data-ttu-id="7b587-217">Tänk på att vissa av de inställningssteg som beskrivs i det ämnet kanske inte är tillgängliga på grund av aktivering av E-fakturering.</span><span class="sxs-lookup"><span data-stu-id="7b587-217">Be aware that some of the setup steps that are described in that topic might be unavailable because of Electronic invoicing activation.</span></span>

1. <span data-ttu-id="7b587-218">Gå till **organisationsadministration \> periodisk \> elektroniska dokument \> skicka elektroniska dokument**.</span><span class="sxs-lookup"><span data-stu-id="7b587-218">Go to **Organization administration \> Periodic \> Electronic documents \> Submit electronic documents**.</span></span>
2. <span data-ttu-id="7b587-219">Ställ alltid in alternativet **Skicka dokument igen** till **Nej** för första inlämningen av ett dokument.</span><span class="sxs-lookup"><span data-stu-id="7b587-219">For the first submission of any document, set the **Resubmit documents** option to **No**.</span></span> <span data-ttu-id="7b587-220">Om du måste skicka ett dokument på nytt via tjänsten ställer du in det här alternativet på **Ja**.</span><span class="sxs-lookup"><span data-stu-id="7b587-220">If you must resubmit a document through the service, set this option to **Yes**.</span></span>
3. <span data-ttu-id="7b587-221">På snabbfliken **Poster att inkludera** välj **Filter** för att öppna dialogrutan **fråga** där du kan skapa en frågeställning för att välja dokument för överföring.</span><span class="sxs-lookup"><span data-stu-id="7b587-221">On the **Records to include** FastTab, select **Filter** to open the **Inquiry** dialog box, where you can build a query to select documents for submission.</span></span>

![Skicka in dialogrutan elektroniska dokument](media/e-Invoicing-services-get-started-ITA-Submission-form.png)

#### <a name="filter-query"></a><span data-ttu-id="7b587-223">Filterfråga</span><span class="sxs-lookup"><span data-stu-id="7b587-223">Filter query</span></span>

1. <span data-ttu-id="7b587-224">Dialogrutan **Förfrågning**, konfigurera filtreringsvillkoren för både försäljningsfakturor och projektfakturor, eller låt villkoren vara tomma för att inkludera alla icke inlämnade fakturor.</span><span class="sxs-lookup"><span data-stu-id="7b587-224">In the **Inquiry** dialog box, configure the filtering conditions for both sales invoices and project invoices, or leave the conditions blank to include all unsubmitted invoices.</span></span>

    ![Ställa in kriterier för överföringsfilter](media/e-Invoicing-services-get-started-ITA-Set-up-Submission-filter-criteria.png)

2. <span data-ttu-id="7b587-226">Välj **OK** för att stänga dialogrutan **Förfrågning**.</span><span class="sxs-lookup"><span data-stu-id="7b587-226">Select **OK** to close the **Inquiry** dialog box.</span></span>
3. <span data-ttu-id="7b587-227">Välj **OK** för att skicka de valda dokumenten.</span><span class="sxs-lookup"><span data-stu-id="7b587-227">Select **OK** submit the selected documents.</span></span>

> <span data-ttu-id="7b587-228">![OBS] Under ditt första försök att skicka ett dokument via tjänsten uppmanas du att bekräfta anslutningen med E-fakturering.</span><span class="sxs-lookup"><span data-stu-id="7b587-228">![NOTE] During your first attempt to submit a document through the service, you will be prompted to confirm the connection with Electronic invoicing.</span></span> <span data-ttu-id="7b587-229">Välj **Klicka här för att ansluta till tjänsten inlämning av elektroniska dokument**.</span><span class="sxs-lookup"><span data-stu-id="7b587-229">Select **Click here to connect to Electronic Document Submission Service**.</span></span>

#### <a name="view-submission-logs"></a><span data-ttu-id="7b587-230">Visa överföringsloggar</span><span class="sxs-lookup"><span data-stu-id="7b587-230">View submission logs</span></span>

<span data-ttu-id="7b587-231">Du kan visa överföringsloggar för alla skickade dokument.</span><span class="sxs-lookup"><span data-stu-id="7b587-231">You can view the submission logs for all submitted documents.</span></span>

1. <span data-ttu-id="7b587-232">Gå till **organisationsadministration \> periodisk \> elektroniska dokument \> logg för inlämning av elektroniska dokument**.</span><span class="sxs-lookup"><span data-stu-id="7b587-232">Go to **Organization administration \> Periodic \> Electronic documents \> Electronic document submission log**.</span></span>
2. <span data-ttu-id="7b587-233">I fältet **Dokumenttyp** väljer du **Kundfakturajournal** eller **Projektfaktura** för att filtrera fram nödvändiga elektroniska dokument.</span><span class="sxs-lookup"><span data-stu-id="7b587-233">In the **Document type** field, select **Customer invoice journal** or **Project invoice** to filter for the required electronic documents.</span></span>

    ![Välja en dokumenttyp för att visa överföringsloggarna](media/e-Invoicing-services-get-started-ITA-Select-Document-type-for-viewing-submission-log.png)

    <span data-ttu-id="7b587-235">Värdet som visas i kolumnen **överföringsstatus** representerar den status för överföringsprocessen.</span><span class="sxs-lookup"><span data-stu-id="7b587-235">The value that is shown in the **Submission status** column represents the status of the submission process.</span></span> <span data-ttu-id="7b587-236">Det anger om processen kördes som konfigurerad och om ytterligare åtgärder krävs.</span><span class="sxs-lookup"><span data-stu-id="7b587-236">It indicates whether the process ran as configured and whether additional action is required.</span></span>

3. <span data-ttu-id="7b587-237">I åtgärdsfönstret, välj **Förfrågningar \> Överföringsinformation** om du vill visa information om körningsloggar för överföring.</span><span class="sxs-lookup"><span data-stu-id="7b587-237">On the Action Pane, select **Inquiries \> Submission details** to view the details of the submission execution logs.</span></span>

    ![Visa information om överföringsloggen](media/e-Invoicing-services-get-started-ITA-View-Submission-log-details.png)

4. <span data-ttu-id="7b587-239">På snabbfliken **Bearbeta åtgärder** kan du visa körningsloggen för de åtgärder som är konfigurerade i funktionsversionen som ställdes in i RCS.</span><span class="sxs-lookup"><span data-stu-id="7b587-239">On the **Processing actions** FastTab, you can view the execution log for the actions that are configured in the feature version that was set up in RCS.</span></span> <span data-ttu-id="7b587-240">Kolumnen **Status** visar om åtgärden har utförts utan fel.</span><span class="sxs-lookup"><span data-stu-id="7b587-240">The **Status** column shows whether the action was successfully run.</span></span>
5. <span data-ttu-id="7b587-241">På snabbfliken **Åtgärdsfiler** kan du visa de mellanliggande filer som genererades under körningen av åtgärderna.</span><span class="sxs-lookup"><span data-stu-id="7b587-241">On the **Action files** FastTab, you can view the intermediate files that were generated during execution of the actions.</span></span> <span data-ttu-id="7b587-242">Du kan välja **vy** för att hämta utdata-XML-filen i format **FatturaPA** och visa dess innehåll.</span><span class="sxs-lookup"><span data-stu-id="7b587-242">You can select **View** to download the output XML file in **FatturaPA** format and view its content.</span></span>

## <a name="related-topics"></a><span data-ttu-id="7b587-243">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="7b587-243">Related topics</span></span>

- [<span data-ttu-id="7b587-244">E-fakturering – översikt</span><span class="sxs-lookup"><span data-stu-id="7b587-244">Electronic invoicing overview</span></span>](e-invoicing-service-overview.md)
- [<span data-ttu-id="7b587-245">Kom i gång med e-fakturering</span><span class="sxs-lookup"><span data-stu-id="7b587-245">Get started with Electronic invoicing</span></span>](e-invoicing-get-started.md)
- [<span data-ttu-id="7b587-246">Ställ in e-fakturering</span><span class="sxs-lookup"><span data-stu-id="7b587-246">Set up Electronic invoicing</span></span>](e-invoicing-setup.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]