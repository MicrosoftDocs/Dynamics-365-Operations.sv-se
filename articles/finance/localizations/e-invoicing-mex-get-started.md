---
title: Kom i gång med e-fakturering för Mexiko
description: Det här avsnittet innehåller information som hjälper dig att komma igång med e-fakturering för Mexiko.
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
ms.openlocfilehash: c1112ba8394afb3aa9c9b4f68249524498bd8b32
ms.sourcegitcommit: 951393b05bf409333cb3c7ad977bcaa804aa801b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/13/2021
ms.locfileid: "5894893"
---
# <a name="get-started-with-electronic-invoicing-for-mexico"></a><span data-ttu-id="0d592-103">Kom i gång med e-fakturering för Mexiko</span><span class="sxs-lookup"><span data-stu-id="0d592-103">Get started with Electronic invoicing for Mexico</span></span>

[!include [banner](../includes/banner.md)]

> [!IMPORTANT]
> <span data-ttu-id="0d592-104">E-fakturering för Mexiko stöder för närvarande inte alla funktioner som är tillgängliga i dokumentet Comprobante Fiscal Digital por Internet (CFDI) i den relaterade integrationen som är inbyggd i Microsoft Dynamics 365 Finance eller Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="0d592-104">Electronic invoicing for Mexico might not currently support all the functions that are available in the Comprobante Fiscal Digital por Internet (CFDI) document, and in the related integration that is built into Microsoft Dynamics 365 Finance or Dynamics 365 Supply Chain Management.</span></span>

<span data-ttu-id="0d592-105">Det här avsnittet innehåller information som hjälper dig att komma igång med e-fakturering för Mexiko.</span><span class="sxs-lookup"><span data-stu-id="0d592-105">This topic provides information that will help you get started with Electronic invoicing for Mexico.</span></span> <span data-ttu-id="0d592-106">Den guidar dig genom de konfigurationssteg som är beroende av RCS (Regulatory Configuration Services) och Finance.</span><span class="sxs-lookup"><span data-stu-id="0d592-106">It guides you through the configuration steps that are country-dependent in Regulatory Configuration Services (RCS) and Finance.</span></span> <span data-ttu-id="0d592-107">Det vägleder dig genom de steg som du måste följa i ekonomin när du vill skicka CFDI-fakturor via tjänsten, och den innehåller även information om hur du granskar bearbetningsresultaten och status för CFDI-fakturor.</span><span class="sxs-lookup"><span data-stu-id="0d592-107">It also guides you through the steps that you must follow in Finance to submit CFDI invoices through the service, and it explains how to review the processing results and the status of CFDI invoices.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="0d592-108">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="0d592-108">Prerequisites</span></span>

<span data-ttu-id="0d592-109">Innan du slutför stegen i det här avsnittet måste du slutföra stegen i [komma igång med e-fakturering](e-invoicing-get-started.md).</span><span class="sxs-lookup"><span data-stu-id="0d592-109">Before you complete the steps in this topic, you must complete the steps in [Get started with Electronic invoicing](e-invoicing-get-started.md).</span></span>

## <a name="rcs-setup"></a><span data-ttu-id="0d592-110">Inställning av RCS</span><span class="sxs-lookup"><span data-stu-id="0d592-110">RCS setup</span></span>

<span data-ttu-id="0d592-111">Under RCS-inställningar ska du utföra följande uppgifter:</span><span class="sxs-lookup"><span data-stu-id="0d592-111">During the RCS setup, you will complete these tasks:</span></span>

1. <span data-ttu-id="0d592-112">Importera e-faktureringsfunktionen för att bearbeta CFDI-fakturor.</span><span class="sxs-lookup"><span data-stu-id="0d592-112">Import the e-Invoicing feature for processing CFDI invoices.</span></span>
2. <span data-ttu-id="0d592-113">Granska de formatkonfigurationer som krävs för att generera, skicka och ta emot svar om CFDI-fakturor och för att skicka och ta emot svar om annullering.</span><span class="sxs-lookup"><span data-stu-id="0d592-113">Review the format configurations that are required to generate, submit, and receive responses about CFDI invoices, and to submit and receive responses about cancellation.</span></span>
3. <span data-ttu-id="0d592-114">Konfigurera de händelser som stöder CFDI för fakturaöverföringar.</span><span class="sxs-lookup"><span data-stu-id="0d592-114">Configure the events that support the CFDI invoice submission scenarios.</span></span>
4. <span data-ttu-id="0d592-115">Publicera e-faktureringsfunktionen för CFDI-fakturor.</span><span class="sxs-lookup"><span data-stu-id="0d592-115">Publish the e-Invoicing feature for CFDI invoices.</span></span>

> [!NOTE]
> <span data-ttu-id="0d592-116">"e-faktureringsfunktionen" är det allmänna namnet för resursen som är konfigurerad och publicerad för att använda servern för e-fakturering.</span><span class="sxs-lookup"><span data-stu-id="0d592-116">"The e-Invoicing feature" is the generic name for the resource that is configured and published to consume the Electronic invoicing server.</span></span> <span data-ttu-id="0d592-117">I det här fallet är CFDI-fakturor (MX) den e-faktureringsfunktion du vill ställa in.</span><span class="sxs-lookup"><span data-stu-id="0d592-117">In this case, CFDI invoices (MX) are the e-Invoicing feature that you will set up.</span></span>

## <a name="import-the-e-invoicing-feature"></a><span data-ttu-id="0d592-118">Importera e-faktureringsfunktion</span><span class="sxs-lookup"><span data-stu-id="0d592-118">Import the e-Invoicing feature</span></span>

1. <span data-ttu-id="0d592-119">Logga in på RCS-kontot.</span><span class="sxs-lookup"><span data-stu-id="0d592-119">Sign in to your RCS account.</span></span>
2. <span data-ttu-id="0d592-120">I arbetsytan **globaliseringsfunktioner** i avsnittet **Funktioner**, välj panelen **e-fakturering**.</span><span class="sxs-lookup"><span data-stu-id="0d592-120">In the **Globalization features** workspace, in the **Features** section, select the **e-Invoicing** tile.</span></span>
3. <span data-ttu-id="0d592-121">På sidan **e-faktureringsfunktioner** väljer du **Importera** för att importera **CFDI-fakturor (MX)** från den globala databasen.</span><span class="sxs-lookup"><span data-stu-id="0d592-121">On the **e-Invoicing Features** page, select **Import** to import the **CFDI invoices (MX)** feature from the Global repository.</span></span>

    > [!NOTE]
    > <span data-ttu-id="0d592-122">Om funktionen inte visas i listan väljer du **synkronisera** och upprepar sedan steg 3.</span><span class="sxs-lookup"><span data-stu-id="0d592-122">If you don't see the feature in the list, select **Synchronize**, and then repeat step 3.</span></span>

![Importera CFDI-fakturor (MX)](media/e-Invoicing-services-get-started-MEX-Select-Import-CFDI-feature.png)

<span data-ttu-id="0d592-124">När du importerar **CFD-fakturor (MX)** från den globala databasen, importeras också alla funktionsinställningar, inklusive konfigurationer och åtgärder.</span><span class="sxs-lookup"><span data-stu-id="0d592-124">When you import the **CFDI invoices (MX)** feature from the Global repository, all the feature settings, including configurations and actions, are also imported.</span></span>

### <a name="create-a-new-version-of-the-cfdi-invoices-mx-feature"></a><span data-ttu-id="0d592-125">Skapa en ny version av funktionen CFDI-fakturor (MX)</span><span class="sxs-lookup"><span data-stu-id="0d592-125">Create a new version of the CFDI invoices (MX) feature</span></span>

<span data-ttu-id="0d592-126">Du kan skapa en ny version om t.ex. URL:er måste uppdateras.</span><span class="sxs-lookup"><span data-stu-id="0d592-126">You can create a new version if, for example, URLs must be updated.</span></span> <span data-ttu-id="0d592-127">Mer information finns i [E-fakturering CFDI](tasks/mx-00010-e-invoicing-cfdi.md).</span><span class="sxs-lookup"><span data-stu-id="0d592-127">For more information, see [E-invoicing CFDI](tasks/mx-00010-e-invoicing-cfdi.md).</span></span>

- <span data-ttu-id="0d592-128">På sidan **e-faktureringsfunktioner** på fliken **Versioner** välj Ändra status **Ny**.</span><span class="sxs-lookup"><span data-stu-id="0d592-128">On the **e-Invoicing Features** page, on the **Versions** tab, select **New**.</span></span>

![Lägger till en ny version av e-faktureringsfunktion](media/e-Invoicing-services-get-started-MEX-Select-New-e-Invoicing-feature.png)

### <a name="update-the-configuration-version"></a><span data-ttu-id="0d592-130">Uppdatera konfigurationsversionen</span><span class="sxs-lookup"><span data-stu-id="0d592-130">Update the configuration version</span></span>

1. <span data-ttu-id="0d592-131">På sidan **e-faktureringsfunktioner** på fliken **Konfigurationer** välj **Lägg till** eller **Ta bort** för att hantera konfigurationsversioner (konfigurationer för ER-filformat).</span><span class="sxs-lookup"><span data-stu-id="0d592-131">On the **e-Invoicing Features** page, on the **Configurations** tab, select **Add** or **Delete** to manage the configuration versions (ER file format configurations).</span></span>

    ![Hantera konfiguration av e-faktureringsfunktioner](media/e-Invoicing-services-get-started-MEX-Manage-e-Invoicing-feature-Configurations.png)

    <span data-ttu-id="0d592-133">När du skapar en ny version ärvs alla konfigurationer från den senast publicerade versionen.</span><span class="sxs-lookup"><span data-stu-id="0d592-133">When you create a new version, all configurations are inherited from the last published version.</span></span> <span data-ttu-id="0d592-134">För att bearbeta CFDI-fakturor krävs följande konfigurationer:</span><span class="sxs-lookup"><span data-stu-id="0d592-134">To process CFDI invoices, the following configurations are required:</span></span>

    - <span data-ttu-id="0d592-135">CFDI-faktura (BusinessDocumentService)</span><span class="sxs-lookup"><span data-stu-id="0d592-135">CFDI invoice (BusinessDocumentService)</span></span>
    - <span data-ttu-id="0d592-136">CFDI import av svarsmeddelande</span><span class="sxs-lookup"><span data-stu-id="0d592-136">CFDI response message import</span></span>
    - <span data-ttu-id="0d592-137">CFDI import av fellogg</span><span class="sxs-lookup"><span data-stu-id="0d592-137">CFDI error log import</span></span>
    - <span data-ttu-id="0d592-138">CFDI annulleringsbegäran (MX) (BusinessDocumentService)</span><span class="sxs-lookup"><span data-stu-id="0d592-138">CFDI cancelation request (MX) (BusinessDocumentService)</span></span>
    - <span data-ttu-id="0d592-139">CFDI-faktura (BusinessDocumentService)</span><span class="sxs-lookup"><span data-stu-id="0d592-139">CFDI invoice (BusinessDocumentService)</span></span>

2. <span data-ttu-id="0d592-140">Välj en konfigurationsversion i listan och välj sedan **Redigera** eller **Visa** för att öppna sidan **Formatdesigner**, där du kan redigera eller visa konfigurationen.</span><span class="sxs-lookup"><span data-stu-id="0d592-140">In the list, select a configuration version, and then select **Edit** or **View** to open the **Format designer** page, where you can edit or view the configuration.</span></span>

    ![Öppna sidan Formatdesigner](media/e-Invoicing-services-get-started-MEX-Configuration-ER-format-designer.png)

3. <span data-ttu-id="0d592-142">Använd sidan **Formatdesigner** för att redigera och visa filkonfigurationerna i ER-format.</span><span class="sxs-lookup"><span data-stu-id="0d592-142">Use the **Format designer** page to edit and view the ER format file configurations.</span></span> <span data-ttu-id="0d592-143">Mer information finns i [Skapa konfigurationer för elektroniska dokument](../../fin-ops-core/dev-itpro/analytics/electronic-reporting-configuration.md).</span><span class="sxs-lookup"><span data-stu-id="0d592-143">For more information, see [Create electronic document configurations](../../fin-ops-core/dev-itpro/analytics/electronic-reporting-configuration.md).</span></span>

    ![Formatdesignersida](media/e-Invoicing-services-get-started-MEX-ER-format-designer.png)

## <a name="manage-the-e-invoicing-feature-setups"></a><span data-ttu-id="0d592-145">Hantera inställningen för e-faktureringsfunktionen</span><span class="sxs-lookup"><span data-stu-id="0d592-145">Manage the e-Invoicing feature setups</span></span>

- <span data-ttu-id="0d592-146">på sidan **e-faktureringsfunktioner** på fliken **Inställningar** välj **Lägg till**, **Ta bort** eller **Redigera** för att hantera inställningsfunktionen för e-fakturering.</span><span class="sxs-lookup"><span data-stu-id="0d592-146">On the **e-Invoicing Features** page, on the **Setups** tab, select **Add**, **Delete**, or **Edit** to manage the e-Invoicing feature setups.</span></span>

![Hantera inställningen för e-faktureringsfunktionen](media/e-Invoicing-services-get-started-MEX-Manage-e-Invoicing-feature-Setup.png)

<span data-ttu-id="0d592-148">Om du vill skicka CFDI-fakturor för auktorisering (generera XML-filen, skicka XML-filen och svaret) måste du konfigurera funktionen för **försäljningsfaktura**.</span><span class="sxs-lookup"><span data-stu-id="0d592-148">To submit CFDI invoices for authorization (generate the XML file, submit the XML file, and process the response), the **Sales invoice** feature setup is required.</span></span>

<span data-ttu-id="0d592-149">Om du vill skicka annullering av CFDI-faktura krävs funktionsinställningarna **Annullering** och **Annullera**.</span><span class="sxs-lookup"><span data-stu-id="0d592-149">To submit CFDI invoice cancellation, the **Cancellation** and **Cancel** feature setups are required.</span></span>

### <a name="configure-the-sales-invoice-feature-setup"></a><span data-ttu-id="0d592-150">Konfigurera inställningen av funktionen Sales-faktura</span><span class="sxs-lookup"><span data-stu-id="0d592-150">Configure the Sales invoice feature setup</span></span>

1. <span data-ttu-id="0d592-151">På sidan **e-faktureringsfunktioner** på fliken **Inställningar** i kolumnen **Funktionsinställningar** välj **Försäljningsfaktura**.</span><span class="sxs-lookup"><span data-stu-id="0d592-151">On the **e-Invoicing Features** page, on the **Setups** tab, in the **Feature setup** column, select **Sales invoice**.</span></span>
2. <span data-ttu-id="0d592-152">Välj **Redigera** om du vill konfigurera åtgärder, tillämpningsreglerna och variabler.</span><span class="sxs-lookup"><span data-stu-id="0d592-152">Select **Edit** to configure the actions, applicability rules, and variables.</span></span>

    ![Redigera inställningen för e-faktureringsfunktionen](media/e-Invoicing-services-get-started-MEX-Edit-e-Invoicing-feature-setup.png)

3. <span data-ttu-id="0d592-154">På sidan **Inställning av funktionsversion** välj fliken **Åtgärder** för att hantera listan med åtgärder.</span><span class="sxs-lookup"><span data-stu-id="0d592-154">On the **Feature version setup** page, select the **Actions** tab to manage the list of actions.</span></span> <span data-ttu-id="0d592-155">Åtgärder definierar en lista med operationer som måste köras i en sekventiell ordning för att händelsen ska kunna utföras.</span><span class="sxs-lookup"><span data-stu-id="0d592-155">Actions define a list of operations that must be run in sequential order to accomplish full execution of the event.</span></span>

    ![Fliken åtgärder](media/e-Invoicing-services-get-started-MEX-Select-Actions.png)

    | <span data-ttu-id="0d592-157">Åtgärds-ID</span><span class="sxs-lookup"><span data-stu-id="0d592-157">Action ID</span></span> | <span data-ttu-id="0d592-158">Åtgärd</span><span class="sxs-lookup"><span data-stu-id="0d592-158">Action</span></span>                   | <span data-ttu-id="0d592-159">Namn på åtgärd</span><span class="sxs-lookup"><span data-stu-id="0d592-159">Action name</span></span>                                  | <span data-ttu-id="0d592-160">Åtgärdsbeskrivning</span><span class="sxs-lookup"><span data-stu-id="0d592-160">Action description</span></span>                                          |
    |-----------|--------------------------|----------------------------------------------|-------------------------------------------------------------|
    | <span data-ttu-id="0d592-161">1</span><span class="sxs-lookup"><span data-stu-id="0d592-161">1</span></span>         | <span data-ttu-id="0d592-162">Transformera dokument</span><span class="sxs-lookup"><span data-stu-id="0d592-162">Transform document</span></span>       | <span data-ttu-id="0d592-163">Generera CFDI E-faktura utan digital signering</span><span class="sxs-lookup"><span data-stu-id="0d592-163">Generate CFDI E-Invoice without digital sign</span></span> | <span data-ttu-id="0d592-164">Generera CFDI e-faktura.</span><span class="sxs-lookup"><span data-stu-id="0d592-164">Generate the CFDI e-invoice.</span></span>                                |
    | <span data-ttu-id="0d592-165">2</span><span class="sxs-lookup"><span data-stu-id="0d592-165">2</span></span>         | <span data-ttu-id="0d592-166">Signera dokument</span><span class="sxs-lookup"><span data-stu-id="0d592-166">Sign document</span></span>            | <span data-ttu-id="0d592-167">Digitalt tecken</span><span class="sxs-lookup"><span data-stu-id="0d592-167">Digital sign</span></span>                                 | <span data-ttu-id="0d592-168">Signera e-postfakturan digitalt för överföring.</span><span class="sxs-lookup"><span data-stu-id="0d592-168">Digitally sign the e-invoice for submission.</span></span>                |
    | <span data-ttu-id="0d592-169">3</span><span class="sxs-lookup"><span data-stu-id="0d592-169">3</span></span>         | <span data-ttu-id="0d592-170">Anropa mexikanska PAC-tjänsten</span><span class="sxs-lookup"><span data-stu-id="0d592-170">Call Mexican PAC service</span></span> | <span data-ttu-id="0d592-171">Skicka CFDI e-faktura</span><span class="sxs-lookup"><span data-stu-id="0d592-171">Submit CFDI E-Invoice</span></span>                        | <span data-ttu-id="0d592-172">WCF-klienten (Windows Communication Foundation) skickar CFDI e-faktura.</span><span class="sxs-lookup"><span data-stu-id="0d592-172">The Windows Communication Foundation (WCF) client submits the CFDI e-invoice.</span></span> |
    | <span data-ttu-id="0d592-173">4</span><span class="sxs-lookup"><span data-stu-id="0d592-173">4</span></span>         | <span data-ttu-id="0d592-174">Behandla svar</span><span class="sxs-lookup"><span data-stu-id="0d592-174">Process response</span></span>         | <span data-ttu-id="0d592-175">Analysera webbtjänstsvar</span><span class="sxs-lookup"><span data-stu-id="0d592-175">Analyze web service response</span></span>                 | <span data-ttu-id="0d592-176">Analysera webbtjänstens svar och returnera felloggen.</span><span class="sxs-lookup"><span data-stu-id="0d592-176">Analyze the web service response, and return the error log.</span></span> |

### <a name="set-up-the-url-for-mexican-pac-web-services"></a><span data-ttu-id="0d592-177">Ställ in URL:en för mexikanska PAC-webbtjänster</span><span class="sxs-lookup"><span data-stu-id="0d592-177">Set up the URL for Mexican PAC web services</span></span> 

1. <span data-ttu-id="0d592-178">På fliken **Inställning av funktionsversion** på fliken **Åtgärder** på snabbfliken **Åtgärder** välj **Anropa mexikanska PAC-tjänsten**.</span><span class="sxs-lookup"><span data-stu-id="0d592-178">On the **Feature version setup** page, on the **Actions** tab, on the **Actions** FastTab, select **Call Mexican PAC service**.</span></span>
2. <span data-ttu-id="0d592-179">På snabbfliken **Parametrar** i fältet **URL-adress** anger du webbadressen till webbtjänsten för CFDI fakturasändning.</span><span class="sxs-lookup"><span data-stu-id="0d592-179">On the **Parameters** FastTab, in the **URL address** field, enter the URL of the web service for CFDI invoice submission.</span></span>

> [!NOTE]
> <span data-ttu-id="0d592-180">Använd samma steg för att uppdatera URL:en för åtgärden **Anropa mexikanska PAC-tjänsten** för funktionsinställningarna **Annullera** och **Annulleringsbegäran**.</span><span class="sxs-lookup"><span data-stu-id="0d592-180">Use the same steps to update the URL for **Call Mexican PAC service** action for the **Cancel** and **Cancelation request** feature setups.</span></span>

## <a name="assign-the-draft-version-to-an-e-invoicing-environment"></a><span data-ttu-id="0d592-181">Tilldela utkastversionen till en e-faktureringsmiljö</span><span class="sxs-lookup"><span data-stu-id="0d592-181">Assign the Draft version to an e-Invoicing environment</span></span>

1. <span data-ttu-id="0d592-182">På sidan **e-faktureringsfunktioner** på fliken **Miljöer** välj Ändra status **Aktivera**.</span><span class="sxs-lookup"><span data-stu-id="0d592-182">On the **e-Invoicing Features** page, on the **Environments** tab, select **Enable**.</span></span>
2. <span data-ttu-id="0d592-183">I fältet **miljö** välj miljön.</span><span class="sxs-lookup"><span data-stu-id="0d592-183">In the **Environment** field, select the environment.</span></span>
3. <span data-ttu-id="0d592-184">I fältet **gäller från** väljer du det datum då miljön ska börja gälla.</span><span class="sxs-lookup"><span data-stu-id="0d592-184">In the **Effective from** field, select the date when the environment should become effective.</span></span>
3. <span data-ttu-id="0d592-185">Välj **Aktivera**.</span><span class="sxs-lookup"><span data-stu-id="0d592-185">Select **Enable**.</span></span>

![Aktivera en e-faktureringsmiljö](media/e-Invoicing-services-get-started-MEX-Enable-e-Invoicing-Environment.png)

## <a name="change-the-version-status-to-completed"></a><span data-ttu-id="0d592-187">Ändra versionsstatus till slutförd</span><span class="sxs-lookup"><span data-stu-id="0d592-187">Change the version status to Completed</span></span>

1. <span data-ttu-id="0d592-188">På sidan **e-faktureringsfunktion** på fliken **Versioner**, välj den version av e-faktureringsfunktionen som har status **Utkast**.</span><span class="sxs-lookup"><span data-stu-id="0d592-188">On the **e-Invoicing Features** page, on the **Versions** tab, select the version of the e-Invoicing feature that has a status of **Draft**.</span></span>
2. <span data-ttu-id="0d592-189">Välj **Ändra status \> Slutför**.</span><span class="sxs-lookup"><span data-stu-id="0d592-189">Select **Change status \> Complete**.</span></span>

## <a name="change-the-version-status-to-published"></a><span data-ttu-id="0d592-190">Ändra versionsstatus till publicerad</span><span class="sxs-lookup"><span data-stu-id="0d592-190">Change the version status to Published</span></span>

- <span data-ttu-id="0d592-191">På sidan **e-faktureringsfunktioner** på fliken **Versioner** välj **Ändra status \> Publicera**.</span><span class="sxs-lookup"><span data-stu-id="0d592-191">On the **e-Invoicing Features** page, on the **Versions** tab, select **Change status \> Publish**.</span></span>

## <a name="publish-the-e-invoicing-feature"></a><span data-ttu-id="0d592-192">Publicera e-faktureringsfunktionen</span><span class="sxs-lookup"><span data-stu-id="0d592-192">Publish the e-Invoicing feature</span></span>

1. <span data-ttu-id="0d592-193">På sidan **e-faktureringsfunktioner** väljer du fliken **Versioner** för att hantera status för funktionen **CFDI-fakturor (MX)**.</span><span class="sxs-lookup"><span data-stu-id="0d592-193">On the **e-Invoicing Features** page, select the **Versions** tab to manage the status of the **CFDI invoices (MX)** feature.</span></span>
2. <span data-ttu-id="0d592-194">Välj **ändra status** om du vill ändra funktionens status.</span><span class="sxs-lookup"><span data-stu-id="0d592-194">Select **Change status** to change the status of the feature.</span></span>

![Ändra status för e-faktureringsfunktionen](media/e-Invoicing-services-get-started-MEX-Change-status-of-e-Invoicing-feature.png)

## <a name="set-up-electronic-invoicing--integration-in-finance"></a><span data-ttu-id="0d592-196">Ställ in integrering av e-fakturering i Finance</span><span class="sxs-lookup"><span data-stu-id="0d592-196">Set up Electronic invoicing  integration in Finance</span></span>

<span data-ttu-id="0d592-197">Du ställer in elektroniska fakturering i Finance genom att utföra följande uppgifter:</span><span class="sxs-lookup"><span data-stu-id="0d592-197">To set up Electronic invoicing in Finance, you will complete these tasks:</span></span>

1. <span data-ttu-id="0d592-198">Importera ER-datamodell, ER-datamodellmappning och de format som krävs för CFDI-fakturor.</span><span class="sxs-lookup"><span data-stu-id="0d592-198">Import the ER data model, the ER data model mapping, and the formats that are required for CFDI invoices.</span></span>
2. <span data-ttu-id="0d592-199">Konfigurera svarstyper för uppdatering av CFDI-fakturor.</span><span class="sxs-lookup"><span data-stu-id="0d592-199">Configure response types for updating the CFDI invoices.</span></span> <span data-ttu-id="0d592-200">Dessa svarstyper används för svaret från den auktoriserade certifieringsserverns leverantör (PAC).</span><span class="sxs-lookup"><span data-stu-id="0d592-200">These response types are used for the response from the authorized certification provider (PAC) server.</span></span>

### <a name="import-the-er-data-model-er-data-model-mapping-and-context-configurations-for-cfdi-invoices"></a><span data-ttu-id="0d592-201">Importera ER-datamodell, ER-datamodellmappning och kontextkonfigurationer för CFDI-fakturor</span><span class="sxs-lookup"><span data-stu-id="0d592-201">Import the ER data model, ER data model mapping, and context configurations for CFDI invoices</span></span>

1. <span data-ttu-id="0d592-202">Logga in på Finance.</span><span class="sxs-lookup"><span data-stu-id="0d592-202">Sign in to Finance.</span></span>
2. <span data-ttu-id="0d592-203">I arbetsytan **elektronisk rapportering** i avsnittet **konfigurationsprovider** väljer du rubriken **Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="0d592-203">In the **Electronic reporting** workspace, in the **Configuration providers** section, select the **Microsoft** title.</span></span> <span data-ttu-id="0d592-204">Kontrollera att konfigurationsprovidern är **aktiverad**.</span><span class="sxs-lookup"><span data-stu-id="0d592-204">Make sure that this configuration provider is set to **Active**.</span></span> <span data-ttu-id="0d592-205">För information om hur du ställer in en leverantör på **Aktiv**, se [Skapa konfigurationsleverantörer och markera dem som aktiva](../../fin-ops-core/dev-itpro/analytics/tasks/er-configuration-provider-mark-it-active-2016-11.md).</span><span class="sxs-lookup"><span data-stu-id="0d592-205">For information about how to set a provider to **Active**, see [Create configuration providers and mark them as active](../../fin-ops-core/dev-itpro/analytics/tasks/er-configuration-provider-mark-it-active-2016-11.md).</span></span>
3. <span data-ttu-id="0d592-206">Välj **Databaser**.</span><span class="sxs-lookup"><span data-stu-id="0d592-206">Select **Repositories**.</span></span>
4. <span data-ttu-id="0d592-207">Välj **Global resurs \> Öppna**.</span><span class="sxs-lookup"><span data-stu-id="0d592-207">Select **Global resource \> Open**.</span></span>
5. <span data-ttu-id="0d592-208">Importera **Fakturamodell**, **Mappning av fakturamodell**, **CFDI-fakturaformat (MX)**, **CFDI-format för begäran om annullering av faktura (MX)** och **CFDI-format för annullering av faktura (MX)**.</span><span class="sxs-lookup"><span data-stu-id="0d592-208">Import **Invoice model**, **Invoice model mapping**, **CFDI invoice format (MX)**, **CFDI invoice cancelation request format (MX)**, and **CFDI invoice cancel format (MX)**.</span></span>

### <a name="turn-on-the-feature-for-processing-cfdi-invoices"></a><span data-ttu-id="0d592-209">Aktivera funktionen för att bearbeta CFDI-fakturor</span><span class="sxs-lookup"><span data-stu-id="0d592-209">Turn on the feature for processing CFDI invoices</span></span>

1. <span data-ttu-id="0d592-210">Gå till **organisationsadministration \> inställning \> parametrar för elektroniska dokument**.</span><span class="sxs-lookup"><span data-stu-id="0d592-210">Go to **Organization administration \> Setup \> Electronic document parameters**.</span></span>
2. <span data-ttu-id="0d592-211">På fliken **funktioner** markerar du kryssrutan **Aktivera** i raderna för funktionsreferenser till **MX-00010** och **MX-00016**.</span><span class="sxs-lookup"><span data-stu-id="0d592-211">On the **Features** tab, select the **Enable** check box in the rows for feature references **MX-00010** and **MX-00016**.</span></span>

![Aktivera funktioner för att bearbeta CFDI-fakturor](media/e-Invoicing-services-get-started-MEX-Enable-CFDI-feature.png)

### <a name="import-er-configurations-and-set-up-the-response-types-for-updating-cfdi-invoices"></a><span data-ttu-id="0d592-213">Importera ER-konfigurationer och ställ in svarstyperna för uppdatering av CFDI-fakturor</span><span class="sxs-lookup"><span data-stu-id="0d592-213">Import ER configurations and set up the response types for updating CFDI invoices</span></span>

#### <a name="import-er-configurations"></a><span data-ttu-id="0d592-214">Importera ER-konfigurationer</span><span class="sxs-lookup"><span data-stu-id="0d592-214">Import ER configurations</span></span>

1. <span data-ttu-id="0d592-215">I arbetsytan **elektronisk rapportering** i avsnittet **konfigurationsprovider** väljer du rubriken **Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="0d592-215">In the **Electronic reporting** workspace, in the **Configuration providers** section, select the **Microsoft** title.</span></span>
3. <span data-ttu-id="0d592-216">Välj **Databaser**.</span><span class="sxs-lookup"><span data-stu-id="0d592-216">Select **Repositories**.</span></span>
4. <span data-ttu-id="0d592-217">Välj **Global resurs \> Öppna**.</span><span class="sxs-lookup"><span data-stu-id="0d592-217">Select **Global resource \> Open**.</span></span>
5. <span data-ttu-id="0d592-218">Importera **Svarsmeddelandemodell**, **CFDI import av fellogg (MX)** och **CFDI import av svarsmeddelande (MX)**.</span><span class="sxs-lookup"><span data-stu-id="0d592-218">Import **Response message model**, **CFDI error log import (MX)**, and **CFDI response message import (MX)**.</span></span>

#### <a name="set-up-the-response-types"></a><span data-ttu-id="0d592-219">Ställ in svarstyper</span><span class="sxs-lookup"><span data-stu-id="0d592-219">Set up the response types</span></span>

1. <span data-ttu-id="0d592-220">Gå till **organisationsadministration \> inställning \> parametrar för elektroniska dokument**.</span><span class="sxs-lookup"><span data-stu-id="0d592-220">Go to **Organization administration \> Setup \> Electronic document parameters**.</span></span>
2. <span data-ttu-id="0d592-221">På fliken **Elektroniska dokument** väljer du **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="0d592-221">On the **Electronic document** tab, select **Add**.</span></span>
3. <span data-ttu-id="0d592-222">Ange kundfakturajournalen och välj sedan projektfakturan i fältet **Registernamn**.</span><span class="sxs-lookup"><span data-stu-id="0d592-222">Enter the customer invoice journal, and then, in the **Table name** field, select the project invoice.</span></span>
4. <span data-ttu-id="0d592-223">Definiera ett relaterat dokumentsammanhang för varje register.</span><span class="sxs-lookup"><span data-stu-id="0d592-223">For each table, define a related document context:</span></span>

    - <span data-ttu-id="0d592-224">För **Kundfakturajournaler** anger du **Kundfakturakontext**.</span><span class="sxs-lookup"><span data-stu-id="0d592-224">For **Customer invoice journal**, enter **Customer invoice context**.</span></span>
    - <span data-ttu-id="0d592-225">För **Projektfaktura**, ange **Projektfaktura kontext**.</span><span class="sxs-lookup"><span data-stu-id="0d592-225">For **Project invoice**, enter **Project invoice context**.</span></span>

4. <span data-ttu-id="0d592-226">Välj **svarstyper** för att konfigurera de svarstyper som kan returneras från e-fakturering och inkluderas i en kundfakturajournal eller på en projektfaktura.</span><span class="sxs-lookup"><span data-stu-id="0d592-226">Select **Response types** to configure the response types that can be returned from Electronic invoicing and included in a customer invoice journal or project invoice.</span></span>
5. <span data-ttu-id="0d592-227">Markera **Ny** och sedan, i fältet **Svarstyp**, markerar du **Svar**.</span><span class="sxs-lookup"><span data-stu-id="0d592-227">Select **New**, and then, in the **Response type** field, select **Response**.</span></span>
6. <span data-ttu-id="0d592-228">I fältet **Överföringsstatus** välj **Väntande**.</span><span class="sxs-lookup"><span data-stu-id="0d592-228">In the **Submission status** field, select **Pending**.</span></span>
7. <span data-ttu-id="0d592-229">I fältet **Modellmappning** välj **Importformat för svarsmeddelande – Modellmappning från svarsmeddelande**.</span><span class="sxs-lookup"><span data-stu-id="0d592-229">In the **Model mapping** field, select **Response message import format – Model mapping from response message**.</span></span>
8. <span data-ttu-id="0d592-230">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="0d592-230">Select **Save**.</span></span>
9. <span data-ttu-id="0d592-231">Markera **Ny** och sedan, i fältet **Svarstyp**, markerar du **ResponseData**.</span><span class="sxs-lookup"><span data-stu-id="0d592-231">Select **New**, and then, in the **Response type** field, select **ResponseData**.</span></span>
10. <span data-ttu-id="0d592-232">I fältet **Överföringsstatus** välj **Väntande**.</span><span class="sxs-lookup"><span data-stu-id="0d592-232">In the **Submission status** field, select **Pending**.</span></span>
11. <span data-ttu-id="0d592-233">I fältet **modellmappning** väljer du **CFDI importformat för svarsdata (information) – import av svarsdata**.</span><span class="sxs-lookup"><span data-stu-id="0d592-233">In the **Model mapping** field, select **CFDI response data import format (details) – Response data import**.</span></span>
12. <span data-ttu-id="0d592-234">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="0d592-234">Select **Save**.</span></span>

## <a name="process-electronic-invoices-in-finance"></a><span data-ttu-id="0d592-235">Bearbeta elektroniska fakturor i Finance</span><span class="sxs-lookup"><span data-stu-id="0d592-235">Process electronic invoices in Finance</span></span> 

<span data-ttu-id="0d592-236">Under bearbetningen av CFDI-fakturor i Finance genom E-fakturering kan du utföra följande uppgifter:</span><span class="sxs-lookup"><span data-stu-id="0d592-236">During the processing of CFDI invoices in Finance through Electronic invoicing, you can perform the following tasks:</span></span>

- <span data-ttu-id="0d592-237">Skicka CFDI-fakturor.</span><span class="sxs-lookup"><span data-stu-id="0d592-237">Submit CFDI invoices.</span></span>
- <span data-ttu-id="0d592-238">Visa körningsloggar för överföring.</span><span class="sxs-lookup"><span data-stu-id="0d592-238">View the submission execution logs.</span></span>
- <span data-ttu-id="0d592-239">Skicka annulleringen av en CFDI-faktura.</span><span class="sxs-lookup"><span data-stu-id="0d592-239">Submit the cancellation of a CFDI invoice.</span></span>

### <a name="submit-cfdi-invoices"></a><span data-ttu-id="0d592-240">Skicka CFDI-fakturor</span><span class="sxs-lookup"><span data-stu-id="0d592-240">Submit CFDI invoices</span></span>

<span data-ttu-id="0d592-241">När du har aktiverat funktionen **Konfigurerbar integrering för e-fakturering** kan processen **Exportera/importera e-faktura** (**Kundreskontra \> Fakturor \> E-fakturor**) för att skicka CFDI-fakturor inte längre användas.</span><span class="sxs-lookup"><span data-stu-id="0d592-241">After you turn on the **Configurable Electronic invoicing integration** feature, the **Export/Import electronic invoice** process (**Accounts receivable \> Invoices \> E-invoices**) for submitting CFDI invoices can no longer be used.</span></span> <span data-ttu-id="0d592-242">Den ersätts med en ny process som kallas **skicka elektroniska dokument**.</span><span class="sxs-lookup"><span data-stu-id="0d592-242">It's replaced by a new process that is named **Submit electronic documents**.</span></span>

> [!NOTE]
> <span data-ttu-id="0d592-243">Innan du använder processen för att **skicka elektroniska dokument** bör du kontrollera att inställningen som krävs för mexikanska e-fakturor har slutförts.</span><span class="sxs-lookup"><span data-stu-id="0d592-243">Before you use the new **Submit electronic documents** process, verify that the setup that is required for Mexican e-invoices was completed.</span></span> <span data-ttu-id="0d592-244">För mer information, se [CFDI layout version 3.3](./latam-mex-cfdi-3-3.md).</span><span class="sxs-lookup"><span data-stu-id="0d592-244">For more information, see [CFDI layout version 3.3](./latam-mex-cfdi-3-3.md).</span></span>

1. <span data-ttu-id="0d592-245">Gå till **organisationsadministration \> periodisk \> elektroniska dokument \> skicka elektroniska dokument**.</span><span class="sxs-lookup"><span data-stu-id="0d592-245">Go to **Organization administration \> Periodic \> Electronic documents \> Submit electronic documents**.</span></span>
2. <span data-ttu-id="0d592-246">Ställ alltid in alternativet **Skicka dokument igen** till **Nej** för första inlämningen av ett dokument.</span><span class="sxs-lookup"><span data-stu-id="0d592-246">For the first submission of any document, always set the **Resubmit documents** option to **No**.</span></span> <span data-ttu-id="0d592-247">Om du måste skicka ett dokument på nytt via tjänsten ställer du in det här alternativet på **Ja**.</span><span class="sxs-lookup"><span data-stu-id="0d592-247">If you must resubmit a document through the service, set this option to **Yes**.</span></span>
3. <span data-ttu-id="0d592-248">På snabbfliken **Poster att inkludera** välj **Filter** för att öppna dialogrutan **fråga** där du kan skapa en frågeställning för att välja dokument för överföring.</span><span class="sxs-lookup"><span data-stu-id="0d592-248">On the **Records to include** FastTab, select **Filter** to open the **Inquiry** dialog box, where you can build a query to select documents for submission.</span></span>

![Skicka ett CFDI-dokument](media/e-Invoicing-services-get-started-MEX-Submit-CFDI-document.png)

> [!NOTE]
> <span data-ttu-id="0d592-250">Under ditt första försök att skicka ett dokument via tjänsten uppmanas du att bekräfta anslutningen med E-fakturering.</span><span class="sxs-lookup"><span data-stu-id="0d592-250">During your first attempt to submit a document through the service, you will be prompted to confirm the connection with Electronic invoicing.</span></span> <span data-ttu-id="0d592-251">Välj **Klicka här för att ansluta till tjänsten inlämning av elektroniska dokument**.</span><span class="sxs-lookup"><span data-stu-id="0d592-251">Select **Click here to connect to Electronic Document Submission Service**.</span></span>

### <a name="view-submission-logs"></a><span data-ttu-id="0d592-252">Visa överföringsloggar</span><span class="sxs-lookup"><span data-stu-id="0d592-252">View submission logs</span></span>

<span data-ttu-id="0d592-253">Du kan visa överföringsloggar för alla skickade dokument eller för bara ett skickat dokument.</span><span class="sxs-lookup"><span data-stu-id="0d592-253">You can view the submission logs for all submitted documents or for just one submitted document.</span></span>

#### <a name="view-all-submission-logs"></a><span data-ttu-id="0d592-254">Visa alla överföringsloggar</span><span class="sxs-lookup"><span data-stu-id="0d592-254">View all submission logs</span></span>

<span data-ttu-id="0d592-255">När du har aktiverat funktionen **konfigurerbar integrering för e-fakturering** finns en ny sida där du kan följa upp processen för att skicka dokument.</span><span class="sxs-lookup"><span data-stu-id="0d592-255">After you turn on the **Configurable Electronic invoicing integration** feature, a new page is available that lets you follow up on the document submission process.</span></span> <span data-ttu-id="0d592-256">Du kan använda den här sidan om du vill visa överföringsloggar för alla skickade dokument.</span><span class="sxs-lookup"><span data-stu-id="0d592-256">You can use this page to view the submission logs for all submitted documents.</span></span>

1. <span data-ttu-id="0d592-257">Gå till **organisationsadministration \> periodisk \> elektroniska dokument \> logg för inlämning av elektroniska dokument**.</span><span class="sxs-lookup"><span data-stu-id="0d592-257">Go to **Organization administration \> Periodic \> Electronic documents \> Electronic document submission log**.</span></span>
2. <span data-ttu-id="0d592-258">I fältet **Dokumenttyp** väljer du **Kundfakturajournal** för att filtrera fram nödvändiga elektroniska dokument.</span><span class="sxs-lookup"><span data-stu-id="0d592-258">In the **Document type** field, select **Customer invoice journal** to filter for the required electronic documents.</span></span>

    ![Välja en dokumenttyp för att visa överföringsloggarna](media/e-Invoicing-services-get-started-MEX-Select-document-type-for-viewing-submission-log.png)

3. <span data-ttu-id="0d592-260">I åtgärdsfönstret, välj **Förfrågningar \> Överföringsinformation** om du vill visa information om körningsloggar för överföring.</span><span class="sxs-lookup"><span data-stu-id="0d592-260">On the Action Pane, select **Inquiries \> Submission details** to view the details of the submission execution logs.</span></span>

    ![Visa information om överföringsloggen](media/e-Invoicing-services-get-started-MEX-View-submission-log-details.png)

<span data-ttu-id="0d592-262">Informationen i överföringsloggarna delas upp på tre snabbflikar:</span><span class="sxs-lookup"><span data-stu-id="0d592-262">The information in the submission logs is divided among three FastTabs:</span></span>

- <span data-ttu-id="0d592-263">**Bearbeta åtgärder** – på den här snabbfliken visas körningsloggen för de åtgärder som är konfigurerade i funktionsversionen som ställdes in i RCS.</span><span class="sxs-lookup"><span data-stu-id="0d592-263">**Processing actions** – This FastTab shows the execution log for the actions that are configured in the feature version that was set up in RCS.</span></span> <span data-ttu-id="0d592-264">Kolumnen **Status** visar om åtgärden har utförts utan fel.</span><span class="sxs-lookup"><span data-stu-id="0d592-264">The **Status** column shows whether the action was successfully run.</span></span>
- <span data-ttu-id="0d592-265">**Åtgärdsfiler** – på den här snabbfliken visas de mellanliggande filer som genererades under körningen av åtgärderna.</span><span class="sxs-lookup"><span data-stu-id="0d592-265">**Action files** – This FastTab shows the intermediate files that were generated during execution of the actions.</span></span> <span data-ttu-id="0d592-266">Du kan välja **vy** om du vill hämta och visa filen.</span><span class="sxs-lookup"><span data-stu-id="0d592-266">You can select **View** to download and view the file.</span></span>
- <span data-ttu-id="0d592-267">**Bearbeta åtgärdslogg** – på den här snabbfliken visas resultaten av kommunikationen mellan E-fakturering och målwebbtjänsten.</span><span class="sxs-lookup"><span data-stu-id="0d592-267">**Processing action log** – This FastTab shows the results of the communication between Electronic invoicing and the target web service.</span></span> <span data-ttu-id="0d592-268">Det visar också vad som har returnerats av bearbetningen från webbtjänst.</span><span class="sxs-lookup"><span data-stu-id="0d592-268">It also shows what was returned by the processing from the web service.</span></span> <span data-ttu-id="0d592-269">I kolumnen **Felkod** visas den returkod som har returnerats av webbtjänsten för auktorisering.</span><span class="sxs-lookup"><span data-stu-id="0d592-269">The **Error code** column shows the return code that was returned by the authorization web service.</span></span>

<span data-ttu-id="0d592-270">När den skickade CFDI-fakturan godkänns uppdateras dess status till **godkänd**.</span><span class="sxs-lookup"><span data-stu-id="0d592-270">When the submitted CFDI invoice is authorized, its status is updated to **Approved**.</span></span>

#### <a name="view-submission-logs-from-cfdi-invoices"></a><span data-ttu-id="0d592-271">Visa överföringsloggar från CFDI-fakturor</span><span class="sxs-lookup"><span data-stu-id="0d592-271">View submission logs from CFDI invoices</span></span>

<span data-ttu-id="0d592-272">När du har aktiverat funktionen **konfigurerbar integrering för e-fakturering** kan du även visa överföringsloggarna från CFDI-fakturor.</span><span class="sxs-lookup"><span data-stu-id="0d592-272">After you turn on the **ConfigurableElectronic invoicing integration** feature, you can also view the submission logs from CFDI invoices.</span></span>

1. <span data-ttu-id="0d592-273">Gå till **Kundreskontra \> Förfrågningar och rapporter \> CFDI (e-fakturor)**.</span><span class="sxs-lookup"><span data-stu-id="0d592-273">Go to **Accounts receivable \> Inquiries and reports \> CFDI (electronic invoices)**.</span></span>
2. <span data-ttu-id="0d592-274">Välj en CFDI-faktura som har skickats efter att funktionen **konfigurerbar integrering för e-fakturering** aktiverades.</span><span class="sxs-lookup"><span data-stu-id="0d592-274">Select a CFDI invoice that was submitted after the **Configurable Electronic invoicing integration** feature was turned on.</span></span>
3. <span data-ttu-id="0d592-275">I åtgärdsfönstret på fliken **Historik** välj **Elektronisk dokumentlogg**.</span><span class="sxs-lookup"><span data-stu-id="0d592-275">On the Action Pane, on the **History** tab, select **Electronic document log**.</span></span>

![Visa överföringsloggar från CFDI-fakturor](media/e-Invoicing-services-get-started-MEX-View-submission-log-from-CFDI-invoice.png)

> [!NOTE]
> <span data-ttu-id="0d592-277">För CFDI-fakturor som har skickats innan den funktionen **konfigurerbar integrering för e-fakturering** aktiverades är knappen **Historik** tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="0d592-277">For CFDI invoices that were submitted before the **Configurable Electronic invoicing integration** feature was turned on, the **History** button is available.</span></span> <span data-ttu-id="0d592-278">Knappen **Historik** är inte tillgänglig för CFDI-fakturor som har skickats innan den funktionen **konfigurerbar integrering för e-fakturering** aktiverades.</span><span class="sxs-lookup"><span data-stu-id="0d592-278">The **History** button isn't available for CFDI invoices that were submitted after the **Configurable Electronic invoicing integration** feature was turned on.</span></span>

### <a name="submit-cancellation-of-cfdi-invoices"></a><span data-ttu-id="0d592-279">Skicka annulleringen av en CFDI-fakturor</span><span class="sxs-lookup"><span data-stu-id="0d592-279">Submit cancellation of CFDI invoices</span></span>

<span data-ttu-id="0d592-280">När du har aktiverat funktionen **konfigurerbar integrering för e-fakturering** kan den gamla processen för att avbryta CFDI-fakturor inte längre användas.</span><span class="sxs-lookup"><span data-stu-id="0d592-280">After you turn on the **Configurable Electronic invoicing integration** feature, the old process for canceling CFDI invoices can no longer be used.</span></span> <span data-ttu-id="0d592-281">Det ersätts med en ny annulleringsprocess som är inbäddad på sidan **Logg för inlämning av elektroniska dokument**.</span><span class="sxs-lookup"><span data-stu-id="0d592-281">It's replaced by a new cancellation process that is embedded on the **Electronic document submission log** page.</span></span>

1. <span data-ttu-id="0d592-282">Gå till **Kundreskontra \> Förfrågningar och rapporter \> CFDI (e-fakturor)**.</span><span class="sxs-lookup"><span data-stu-id="0d592-282">Go to **Accounts receivable \> Inquiries and reports \> CFDI (electronic invoices)**.</span></span>
2. <span data-ttu-id="0d592-283">Om CFDI-faktura har statusen **Godkänd** väljer du **Funktioner \> Avbryt CFDI**.</span><span class="sxs-lookup"><span data-stu-id="0d592-283">If the CFDI invoice has a status of **Approved**, select **Functions \> Cancel CFDI**.</span></span>
3. <span data-ttu-id="0d592-284">Gå till **organisationsadministration \> periodisk \> elektroniska dokument \> logg för inlämning av elektroniska dokument**.</span><span class="sxs-lookup"><span data-stu-id="0d592-284">Go to **Organization administration \> Periodic \> Electronic documents \> Electronic document submission log**.</span></span>
4. <span data-ttu-id="0d592-285">Välj den CFDI-fakturan och välj sedan **Funktioner \> Skicka relaterade överföringar**.</span><span class="sxs-lookup"><span data-stu-id="0d592-285">Select the CFDI invoice, and then select **Functions \> Send related submissions**.</span></span>
5. <span data-ttu-id="0d592-286">Ange en beskrivning av den relaterade sändningen och klicka sedan på **OK**.</span><span class="sxs-lookup"><span data-stu-id="0d592-286">Enter a description for the related submission, and then select **OK**.</span></span>

#### <a name="view-cancellation-submission-logs"></a><span data-ttu-id="0d592-287">Visa överföringsloggar för annullering</span><span class="sxs-lookup"><span data-stu-id="0d592-287">View cancellation submission logs</span></span>

1. <span data-ttu-id="0d592-288">Gå till **organisationsadministration \> periodisk \> elektroniska dokument \> logg för inlämning av elektroniska dokument**.</span><span class="sxs-lookup"><span data-stu-id="0d592-288">Go to **Organization administration \> Periodic \> Electronic documents \> Electronic document submission log**.</span></span>
2. <span data-ttu-id="0d592-289">I fältet **Dokumenttyp** väljer du **Kundfakturajournal** för att endast filtrera efter journaldokument för kundfaktura.</span><span class="sxs-lookup"><span data-stu-id="0d592-289">In the **Document type** field, select **Customer invoice journal** to filter for customer invoice journal documents only.</span></span>
3. <span data-ttu-id="0d592-290">Välj CFDI-fakturan och välj sedan åtgärdsfönstret **Förfrågningar \> Relaterade överföringar**.</span><span class="sxs-lookup"><span data-stu-id="0d592-290">Select the CFDI invoice, and then, on the Action Pane, select **Inquiries \> Related submission**.</span></span>

    <span data-ttu-id="0d592-291">Sidan **relaterade överföringar** visas alla relaterade inskickade och deras inlämningsstatus för en viss CFDI-faktura.</span><span class="sxs-lookup"><span data-stu-id="0d592-291">The **Related submissions** page shows all related submissions, and their submission status, for a given CFDI invoice.</span></span> <span data-ttu-id="0d592-292">På följande bild representerar den första raden inskickad som begärt godkännande av CFDI-fakturan.</span><span class="sxs-lookup"><span data-stu-id="0d592-292">In the following illustration, the first line represents the submission that requested approval of the CFDI invoice.</span></span> <span data-ttu-id="0d592-293">Den andra raden representerar det inskickade som annullerade den CFDI-fakturan.</span><span class="sxs-lookup"><span data-stu-id="0d592-293">The second line represents the submission that canceled that CFDI invoice.</span></span>

    ![Visa överföringsloggar för annullering](media/e-Invoicing-services-get-started-MEX-View-cancellation-submission-log.png)

4. <span data-ttu-id="0d592-295">I åtgärdsfönstret, välj **Förfrågningar \> Överföringsinformation** om du vill visa information om körningsloggar för överföring.</span><span class="sxs-lookup"><span data-stu-id="0d592-295">On the Action Pane, select **Inquiries \> Submission details** to view the details of the submission execution logs.</span></span>

    ![Visa information om överföringsloggar för annullering](media/e-Invoicing-services-get-started-MEX-View-cancellation-submission-log-details.png)

## <a name="privacy-notice"></a><span data-ttu-id="0d592-297">Sekretesspolicy</span><span class="sxs-lookup"><span data-stu-id="0d592-297">Privacy notice</span></span>
<span data-ttu-id="0d592-298">Om du aktiverar funktionen **CFDI mexikansk elektronisk faktura (MX)** kan det krävas att begränsade data skickas, vilket inkluderar organisationens skatteregistrerings-ID.</span><span class="sxs-lookup"><span data-stu-id="0d592-298">Enabling the **CFDI Mexican electronic invoice (MX)** feature may require sending limited data, which includes the organization tax registration ID.</span></span> <span data-ttu-id="0d592-299">Detta kommer att översändas till tredje parts byråer som har tillstånd av skattemyndigheten för att skicka elektroniska fakturor till denna skattemyndighet i det fördefinierade format som krävs för integrering med den offentliga sektorns webbtjänster.</span><span class="sxs-lookup"><span data-stu-id="0d592-299">This will be transmitted to third-party agencies authorized by the tax authority for purposes of sending electronic invoices to this tax authority in the predefined format required for integration with the government’s web service.</span></span> <span data-ttu-id="0d592-300">En administratör kan aktivera och inaktivera funktionen **CFDI mexikansk elektronisk faktura (MX)** genom att navigera till **Organisationsadministration \> Inställningar \> Parametrar för elektroniskt dokument**.</span><span class="sxs-lookup"><span data-stu-id="0d592-300">An administrator can enable and disable the **CFDI Mexican electronic invoice (MX)** feature by navigating to **Organization administration \> Setup \> Electronic document parameters**.</span></span> <span data-ttu-id="0d592-301">Välj fliken **Funktioner**, markera de rader som innehåller funktionerna **CFDI mexikansk elektronisk faktura (MX)** och välj sedan lämpligt alternativ.</span><span class="sxs-lookup"><span data-stu-id="0d592-301">Select the **Features** tab, select the rows containing the **CFDI Mexican electronic invoice (MX)** feature, and then make the appropriate selection.</span></span> <span data-ttu-id="0d592-302">Data som importeras från dessa externa system till denna Dynamics 365 onlinetjänst omfattas av vår [sekretesspolicy](https://go.microsoft.com/fwlink/?LinkId=512132).</span><span class="sxs-lookup"><span data-stu-id="0d592-302">Data imported from these external systems into this Dynamics 365 online service are subject to our [privacy statement](https://go.microsoft.com/fwlink/?LinkId=512132).</span></span> <span data-ttu-id="0d592-303">Mer information finns i sektionerna om sekretessmeddelanden i landsspecifik funktionsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="0d592-303">Consult the Privacy notice sections in country-specific feature documentation for more information.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="0d592-304">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="0d592-304">Additional resources</span></span>

- [<span data-ttu-id="0d592-305">E-fakturering – översikt</span><span class="sxs-lookup"><span data-stu-id="0d592-305">Electronic invoicing overview</span></span>](e-invoicing-service-overview.md)
- [<span data-ttu-id="0d592-306">Kom i gång med e-fakturering</span><span class="sxs-lookup"><span data-stu-id="0d592-306">Get started with Electronic invoicing</span></span>](e-invoicing-get-started.md)
- [<span data-ttu-id="0d592-307">Ställ in e-fakturering</span><span class="sxs-lookup"><span data-stu-id="0d592-307">Set up Electronic invoicing</span></span>](e-invoicing-setup.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]