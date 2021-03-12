---
title: Kom igång med tillägget elektronisk fakturering för Brasilien
description: Det här avsnittet innehåller information som hjälper dig att komma igång med tillägget elektronisk fakturering för Brasilien i Microsoft Dynamics 365 Finance och Dynamics 365 Supply Chain Management.
author: gionoder
manager: AnnBe
ms.date: 09/04/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
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
ms.openlocfilehash: 0320bd1d9e93cc30ed75f28e387ac2ec8dbfc226
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "4962845"
---
# <a name="get-started-with-the-electronic-invoicing-add-on-for-brazil"></a><span data-ttu-id="36383-103">Kom igång med tillägget elektronisk fakturering för Brasilien</span><span class="sxs-lookup"><span data-stu-id="36383-103">Get started with the Electronic invoicing add-on for Brazil</span></span> 

[!include [banner](../includes/banner.md)]


> [!IMPORTANT]
> <span data-ttu-id="36383-104">Det elektroniska faktureringstillägget för Brasilien stöder för närvarande inte alla funktioner som är tillgängliga i integrationen av skattedokument som är inbyggd i Microsoft Dynamics 365 Finance och Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="36383-104">The Electronic invoicing add-on for Brazil doesn't currently support all the functions that are available in the fiscal document integration that is built into Microsoft Dynamics 365 Finance and Dynamics 365 Supply Chain Management.</span></span>

<span data-ttu-id="36383-105">Det här avsnittet innehåller information som hjälper dig att komma igång med tillägget elektronisk fakturering för Brasilien.</span><span class="sxs-lookup"><span data-stu-id="36383-105">This topic provides information that will help you get started with the Electronic invoicing add-on for Brazil.</span></span> <span data-ttu-id="36383-106">Den guidar dig genom de konfigurationssteg som är beroende av RCS (Regulatory Configuration Services) och i Finance och Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="36383-106">It guides you through the configuration steps that are country-dependent in Regulatory Configuration Services (RCS) and in Finance and Supply Chain Management.</span></span> <span data-ttu-id="36383-107">Det vägleder dig genom processen att skicka ett NF-e skattedokument (elektroniskt skattedokument modell 55) via tjänsten och förklarar hur du granskar bearbetningsresultaten och status för skattedokumenten.</span><span class="sxs-lookup"><span data-stu-id="36383-107">It also guides you through the process of submitting an NF-e fiscal document (Electronic fiscal document model 55) through the service, and it explains how review the processing results and the status of the fiscal documents.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="36383-108">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="36383-108">Prerequisites</span></span>

<span data-ttu-id="36383-109">Innan du slutför stegen i det här avsnittet måste du slutföra stegen i [komma igång med tillägget elektronisk fakturering](e-invoicing-get-started.md).</span><span class="sxs-lookup"><span data-stu-id="36383-109">Before you complete the steps in this topic, you must complete the steps in [Get started with the Electronic invoicing add-on](e-invoicing-get-started.md).</span></span>

## <a name="rcs-setup"></a><span data-ttu-id="36383-110">Inställning av RCS</span><span class="sxs-lookup"><span data-stu-id="36383-110">RCS setup</span></span>

<span data-ttu-id="36383-111">Under RCS-inställningar ska du utföra följande uppgifter:</span><span class="sxs-lookup"><span data-stu-id="36383-111">During the RCS setup, you will complete these tasks:</span></span>

1. <span data-ttu-id="36383-112">Importera e-faktureringsfunktionen för NF-e skattedokument.</span><span class="sxs-lookup"><span data-stu-id="36383-112">Import the e-Invoicing feature for NF-e fiscal documents.</span></span>
2. <span data-ttu-id="36383-113">Granska filformaten som krävs för att skicka NF-e skattedokument för auktorisering.</span><span class="sxs-lookup"><span data-stu-id="36383-113">Review the file formats that are required to submit NF-e fiscal documents for authorization.</span></span>
3. <span data-ttu-id="36383-114">Granska filformaten som krävs för att begära annullering av en godkänd NF-e.</span><span class="sxs-lookup"><span data-stu-id="36383-114">Review the file formats that are required to request the cancellation of an approved NF-e.</span></span>
4. <span data-ttu-id="36383-115">Konfigurera händelsen som krävs för att skicka NF-e skattedokument för auktorisering.</span><span class="sxs-lookup"><span data-stu-id="36383-115">Configure the event that is required to submit NF-e fiscal documents for authorization.</span></span>
5. <span data-ttu-id="36383-116">Konfigurera händelsen som krävs för att begära annullering av en godkänd NF-e.</span><span class="sxs-lookup"><span data-stu-id="36383-116">Configure the event that is required to request the cancellation of an approved NF-e.</span></span>
6. <span data-ttu-id="36383-117">Tilldela e-faktureringsfunktionen till en miljö för tillägget Elektronisk fakturering.</span><span class="sxs-lookup"><span data-stu-id="36383-117">Assign the e-Invoicing feature to an Electronic invoicing add-on environment.</span></span>
7. <span data-ttu-id="36383-118">Publicera e-faktureringsfunktionen.</span><span class="sxs-lookup"><span data-stu-id="36383-118">Publish the e-Invoicing feature.</span></span>

> [!NOTE]
> <span data-ttu-id="36383-119">"e-faktureringsfunktionen" är det allmänna namnet för resursen som är konfigurerad och publicerad för att använda tilläggsservern för elektronisk fakturering.</span><span class="sxs-lookup"><span data-stu-id="36383-119">"The e-Invoicing feature" is the generic name for the resource that is configured and published to consume the Electronic invoicing add-on server.</span></span> <span data-ttu-id="36383-120">Inställningen av funktionen e-fakturering kombinerar bland annat användningen av konfigurationsformat för elektronisk rapportering (ER) för att skapa konfigurerbara export- och importfiler och användningen av åtgärder och åtgärdsflöden för att möjliggöra skapandet av konfigurerbara regler för att skicka förfrågningar , importera svar och analysera svarsinnehållet.</span><span class="sxs-lookup"><span data-stu-id="36383-120">The setup of the e-Invoicing feature combines, among other things, the use of Electronic reporting (ER) configuration formats to create configurable export and import files, and the use of actions and actions flows to enable the creation of configurable rules to send requests, import responses, and parse the response contents.</span></span>

## <a name="import-the-e-invoicing-feature"></a><span data-ttu-id="36383-121">Importera e-faktureringsfunktion</span><span class="sxs-lookup"><span data-stu-id="36383-121">Import the e-Invoicing feature</span></span>

1. <span data-ttu-id="36383-122">Logga in på RCS-kontot</span><span class="sxs-lookup"><span data-stu-id="36383-122">Sign in to your RCS account</span></span>
2. <span data-ttu-id="36383-123">I arbetsytan **globaliseringsfunktioner** i avsnittet **Funktioner**, välj panelen **e-fakturering**.</span><span class="sxs-lookup"><span data-stu-id="36383-123">In the **Globalization features** workspace, in the **Features** section, select the **e-Invoicing** tile.</span></span>
3. <span data-ttu-id="36383-124">På sidan **e-faktureringsfunktioner** väljer du **Importera** för att importera e-faktureringsfunktion för NF-e-skattedokument från den globala databasen.</span><span class="sxs-lookup"><span data-stu-id="36383-124">On the **e-Invoicing Features** page, select **Import** to import a NF-e fiscal document e-Invoicing feature from the Global repository.</span></span>

    ![Importera-knapp](media/e-Invoicing-services-get-started-BRA-Select-Import-e-Invoicing-feature.png)

4. <span data-ttu-id="36383-126">Välj funktionen för NF-e-skattedokumen och välj sedan **Importera**.</span><span class="sxs-lookup"><span data-stu-id="36383-126">Select the NF-e fiscal document feature, and then select **Import**.</span></span>

    ![Importera NF-e-funktionen](media/e-Invoicing-services-get-started-BRA-Select-Import-NF-e-feature.png)

### <a name="create-a-new-version-of-the-nf-e-fiscal-document-feature"></a><span data-ttu-id="36383-128">Skapa en ny version av funktionen NF-e-skattedokument</span><span class="sxs-lookup"><span data-stu-id="36383-128">Create a new version of the NF-e fiscal document feature</span></span>

- <span data-ttu-id="36383-129">På sidan **e-faktureringsfunktioner** på fliken **Versioner** välj Ändra status **Ny**.</span><span class="sxs-lookup"><span data-stu-id="36383-129">On the **e-Invoicing Features** page, on the **Versions** tab, select **New**.</span></span>

![Lägger till en ny version av e-faktureringsfunktion](media/e-Invoicing-services-get-started-BRA-Select-New-e-Invoicing-feature-version.png)

### <a name="update-the-configuration-version"></a><span data-ttu-id="36383-131">Uppdatera konfigurationsversionen</span><span class="sxs-lookup"><span data-stu-id="36383-131">Update the configuration version</span></span>

1. <span data-ttu-id="36383-132">På sidan **e-faktureringsfunktioner** på fliken **Konfigurationer** välj **Lägg till** eller **Ta bort** för att hantera konfigurationsversioner (konfigurationer för ER-filformat).</span><span class="sxs-lookup"><span data-stu-id="36383-132">On the **e-Invoicing Features** page, on the **Configurations** tab, select **Add** or **Delete** to manage the configuration versions (ER file format configurations).</span></span>

    ![Hantera konfiguration av e-faktureringsfunktioner](media/e-Invoicing-services-get-started-BRA-Manage-e-Invoicing-feature-configurations.png)

    - <span data-ttu-id="36383-134">När du skapar en ny version av funktionen NF-e-skattedokument ärvs alla konfigurationsversioner (ER-filformat) från den senaste versionen.</span><span class="sxs-lookup"><span data-stu-id="36383-134">When you create a new version of the NF-e fiscal document feature, all configuration version (ER file formats) are inherited from the latest version.</span></span>
    - <span data-ttu-id="36383-135">Följande konfigurationsversioner krävs för att skicka NF-e-skattedokument för auktorisering:</span><span class="sxs-lookup"><span data-stu-id="36383-135">To submit the NF-e fiscal document for authorization, the following configuration versions are required:</span></span>

        - <span data-ttu-id="36383-136">NFe skicka exportformat</span><span class="sxs-lookup"><span data-stu-id="36383-136">NFe submit export format</span></span>
        - <span data-ttu-id="36383-137">NFe import av svarsmeddelande</span><span class="sxs-lookup"><span data-stu-id="36383-137">NFe response message import</span></span>
        - <span data-ttu-id="36383-138">NFe import av fellogg</span><span class="sxs-lookup"><span data-stu-id="36383-138">NFe error log import</span></span>

    - <span data-ttu-id="36383-139">Följande konfigurationsversion krävs för att skicka NF-e-annulleringen:</span><span class="sxs-lookup"><span data-stu-id="36383-139">To submit the NF-e cancellation, the following configuration version is required:</span></span>

        - <span data-ttu-id="36383-140">NFe annullera exportformat</span><span class="sxs-lookup"><span data-stu-id="36383-140">NFe cancel export format</span></span>

2. <span data-ttu-id="36383-141">Välj en konfigurationsversion i listan och välj sedan **Redigera** eller **Visa** för att öppna sidan **Formatdesigner**, där du kan redigera eller visa konfigurationen.</span><span class="sxs-lookup"><span data-stu-id="36383-141">In the list, select a configuration version, and then select **Edit** or **View** to open the **Format designer** page, where you can edit or view the configuration.</span></span>

    ![Öppna sidan Formatdesigner](media/e-Invoicing-services-get-started-BRA-Configuration-ER-fomat-designer.png)

3. <span data-ttu-id="36383-143">Använd sidan **Formatdesigner** för att redigera eller visa filkonfigurationerna i ER-format.</span><span class="sxs-lookup"><span data-stu-id="36383-143">Use the **Format designer** page to edit or view the ER format file configurations.</span></span> <span data-ttu-id="36383-144">Mer information finns i [Skapa konfigurationer för elektroniska dokument](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/analytics/electronic-reporting-configuration).</span><span class="sxs-lookup"><span data-stu-id="36383-144">For more information, see [Create electronic document configurations](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/analytics/electronic-reporting-configuration).</span></span>

    ![Formatdesignersida](media/e-Invoicing-services-get-started-BRA-ER-Format-designer.png)

### <a name="manage-the-e-invoicing-feature-setups"></a><span data-ttu-id="36383-146">Hantera inställningen för e-faktureringsfunktionen</span><span class="sxs-lookup"><span data-stu-id="36383-146">Manage the e-Invoicing feature setups</span></span>

- <span data-ttu-id="36383-147">På sidan **e-faktureringsfunktioner** på fliken **Inställningar** välj **Lägg till** eller **Ta bort** för att hantera inställningsfunktionen för e-fakturering (t.ex. NF-e-händelser).</span><span class="sxs-lookup"><span data-stu-id="36383-147">On the **e-Invoicing Features** page, on the **Setups** tab, select **Add** or **Delete** to manage the e-Invoicing feature setups (that is, NF-e events).</span></span>

![Hantera inställningen för e-faktureringsfunktionen](media/e-Invoicing-services-get-started-BRA-Manage-e-Invoicing-feature-setup.png)

<span data-ttu-id="36383-149">När du skapar en ny version av funktionen för NF-e-skattedokument som härleds från en annan e-faktureringsfunktion, ärvs alla funktionsinställningar (NF-e-händelser) från den senaste versionen.</span><span class="sxs-lookup"><span data-stu-id="36383-149">When you create a new version of the NF-e fiscal document feature that is derived from another e-Invoicing feature, all feature setups (NF-e events) are inherited from the latest version.</span></span>

<span data-ttu-id="36383-150">För att skicka NF-e skattedokument för auktorisering krävs funktionsinställningen **Skicka**.</span><span class="sxs-lookup"><span data-stu-id="36383-150">To submit NF-e fiscal documents for authorization, the **Submit** feature setup is required.</span></span>

<span data-ttu-id="36383-151">Om du vill skicka in en NF-e-annullering måste du ställa in en funktion för att **avbryta**.</span><span class="sxs-lookup"><span data-stu-id="36383-151">To submit NF-e cancellation, the **Cancellation** feature setup is required.</span></span>

#### <a name="configure-the-submit-feature-setup"></a><span data-ttu-id="36383-152">Konfigurera inställningar för överföringsfunktionen</span><span class="sxs-lookup"><span data-stu-id="36383-152">Configure the Submit feature setup</span></span>

1. <span data-ttu-id="36383-153">På sidan **e-faktureringsfunktioner** på fliken **Inställningar** i kolumnen **Funktionsinställningar** välj **Skicka**.</span><span class="sxs-lookup"><span data-stu-id="36383-153">On the **e-Invoicing Features** page, on the **Setups** tab, in the **Feature setup** column, select **Submit**.</span></span>
2. <span data-ttu-id="36383-154">Välj **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="36383-154">Select **Edit**.</span></span>

    ![Redigera inställningar för e-faktureringsfunktioner](media/e-Invoicing-services-get-started-BRA-Edit-e-Invoicing-feature-setup.png)

3. <span data-ttu-id="36383-156">På sidan **Inställning av funktionsversion** välj fliken **Åtgärder** för att hantera listan med åtgärder.</span><span class="sxs-lookup"><span data-stu-id="36383-156">On the **Feature version setup** page, select the **Actions** tab to manage the list of actions.</span></span>

    ![Fliken åtgärder](media/e-Invoicing-services-get-started-BRA-Select-Actions.png)

4. <span data-ttu-id="36383-158">Granska åtgärderna som krävs för att skicka NF-e för auktorisering.</span><span class="sxs-lookup"><span data-stu-id="36383-158">Review the actions that are required to submit an NF-e for authorization.</span></span>

    | <span data-ttu-id="36383-159">Åtgärds-ID</span><span class="sxs-lookup"><span data-stu-id="36383-159">Action ID</span></span> | <span data-ttu-id="36383-160">Namn på åtgärd</span><span class="sxs-lookup"><span data-stu-id="36383-160">Action name</span></span>                  | <span data-ttu-id="36383-161">Åtgärdsbeskrivning</span><span class="sxs-lookup"><span data-stu-id="36383-161">Action description</span></span>                                                |
    |-----------|------------------------------|-------------------------------------------------------------------|
    | <span data-ttu-id="36383-162">1</span><span class="sxs-lookup"><span data-stu-id="36383-162">1</span></span>         | <span data-ttu-id="36383-163">Transformera dokument</span><span class="sxs-lookup"><span data-stu-id="36383-163">Transform document</span></span>           | <span data-ttu-id="36383-164">Skapa den NF-e XML-fil som ska skickas.</span><span class="sxs-lookup"><span data-stu-id="36383-164">Create the NF-e XML file for submission.</span></span>                          |
    | <span data-ttu-id="36383-165">2</span><span class="sxs-lookup"><span data-stu-id="36383-165">2</span></span>         | <span data-ttu-id="36383-166">Signera dokument</span><span class="sxs-lookup"><span data-stu-id="36383-166">Sign document</span></span>                | <span data-ttu-id="36383-167">Använd ett digitalt certifikat i XML-filen.</span><span class="sxs-lookup"><span data-stu-id="36383-167">Apply the digital certificate to the XML file.</span></span>                    |
    | <span data-ttu-id="36383-168">3</span><span class="sxs-lookup"><span data-stu-id="36383-168">3</span></span>         | <span data-ttu-id="36383-169">Ring brasilianska SEFAZ-tjänsten</span><span class="sxs-lookup"><span data-stu-id="36383-169">Call Brazilian SEFAZ service</span></span> | <span data-ttu-id="36383-170">Skicka den signerade XML-filen till webbtjänsterna för auktorisering.</span><span class="sxs-lookup"><span data-stu-id="36383-170">Submit the signed XML file to the web services for authorization.</span></span> |
    | <span data-ttu-id="36383-171">4</span><span class="sxs-lookup"><span data-stu-id="36383-171">4</span></span>         | <span data-ttu-id="36383-172">Behandla svar</span><span class="sxs-lookup"><span data-stu-id="36383-172">Process response</span></span>             | <span data-ttu-id="36383-173">Hämta webbtjänstsvaret.</span><span class="sxs-lookup"><span data-stu-id="36383-173">Get the web service response.</span></span>                                     |
    | <span data-ttu-id="36383-174">5</span><span class="sxs-lookup"><span data-stu-id="36383-174">5</span></span>         | <span data-ttu-id="36383-175">Transformera dokument</span><span class="sxs-lookup"><span data-stu-id="36383-175">Transform document</span></span>           | <span data-ttu-id="36383-176">Tolka innehållet i den fil som tas emot som ett svar.</span><span class="sxs-lookup"><span data-stu-id="36383-176">Parse the content of the file that is received as a response.</span></span>     |
    | <span data-ttu-id="36383-177">6</span><span class="sxs-lookup"><span data-stu-id="36383-177">6</span></span>         | <span data-ttu-id="36383-178">Transformera dokument</span><span class="sxs-lookup"><span data-stu-id="36383-178">Transform document</span></span>           | <span data-ttu-id="36383-179">Skapa XML-filen för att fråga om status för överföringen.</span><span class="sxs-lookup"><span data-stu-id="36383-179">Create the XML file to inquire about status of the submission.</span></span>    |
    | <span data-ttu-id="36383-180">7</span><span class="sxs-lookup"><span data-stu-id="36383-180">7</span></span>         | <span data-ttu-id="36383-181">Ring brasilianska SEFAZ-tjänsten</span><span class="sxs-lookup"><span data-stu-id="36383-181">Call Brazilian SEFAZ service</span></span> | <span data-ttu-id="36383-182">Skicka XML-filen som begär status för överföringen.</span><span class="sxs-lookup"><span data-stu-id="36383-182">Submit the XML file that requests the submission status.</span></span>          |
    | <span data-ttu-id="36383-183">8</span><span class="sxs-lookup"><span data-stu-id="36383-183">8</span></span>         | <span data-ttu-id="36383-184">Behandla svar</span><span class="sxs-lookup"><span data-stu-id="36383-184">Process response</span></span>             | <span data-ttu-id="36383-185">Hämta webbtjänstsvaret.</span><span class="sxs-lookup"><span data-stu-id="36383-185">Get the web service response.</span></span>                                     |

#### <a name="set-up-the-url-for-sefaz-web-services"></a><span data-ttu-id="36383-186">Ställ in URL:en för SEFAZ-webbtjänster</span><span class="sxs-lookup"><span data-stu-id="36383-186">Set up the URL for SEFAZ web services</span></span> 

1. <span data-ttu-id="36383-187">På fliken **Inställning av funktionsversion** på fliken **Åtgärder** på snabbfliken **Åtgärder** välj **Anropa brasilianska SEFAZ-tjänsten** (åtgärds-ID **3**).</span><span class="sxs-lookup"><span data-stu-id="36383-187">On the **Feature version setup** page, on the **Actions** tab, on the **Actions** FastTab, select **Call Brazilian SEFAZ service** (action ID **3**).</span></span>
2. <span data-ttu-id="36383-188">På snabbfliken **Parametrar** i fältet **Parametrar för URL-adress** anger du webbadressen till SEFAZ-webbtjänsten för NF-e-sändning.</span><span class="sxs-lookup"><span data-stu-id="36383-188">On the **Parameters** FastTab, in the **URL address parameter** field, enter the URL of the SEFAZ web service for NF-e submission.</span></span>
3. <span data-ttu-id="36383-189">På snabbfliken **åtgärder** väljer du **anropa brasilianska SEFAZ-tjänsten** (åtgärds-ID **7**).</span><span class="sxs-lookup"><span data-stu-id="36383-189">On the **Actions** FastTab, select **Call Brazilian SEFAZ service** (action ID **7**).</span></span>
4. <span data-ttu-id="36383-190">På snabbfliken **Parametrar** i fältet **Parametrar för URL-adress** anger du webbadressen till SEFAZ-webbtjänsten för NF-e-sändning.</span><span class="sxs-lookup"><span data-stu-id="36383-190">On the **Parameters** FastTab, in the **URL address parameter** field, enter the URL of the SEFAZ web service for NF-e submission.</span></span>

#### <a name="configure-the-cancellation-feature-setup"></a><span data-ttu-id="36383-191">Konfigurera inställningar för annulleringsfunktionen</span><span class="sxs-lookup"><span data-stu-id="36383-191">Configure the Cancellation feature setup</span></span>

1. <span data-ttu-id="36383-192">På sidan **e-faktureringsfunktioner** på fliken **Inställningar** i kolumnen **Funktionsinställningar** välj **Annullera**.</span><span class="sxs-lookup"><span data-stu-id="36383-192">On the **e-Invoicing Features** page, on the **Setups** tab, in the **Feature setup** column, select **Cancellation**.</span></span>
2. <span data-ttu-id="36383-193">Välj **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="36383-193">Select **Edit**.</span></span>
3. <span data-ttu-id="36383-194">På sidan **Inställning av funktionsversion** välj fliken **Åtgärder** för att hantera listan med åtgärder.</span><span class="sxs-lookup"><span data-stu-id="36383-194">On the **Feature version setup** page, select the **Actions** tab to manage the list of actions.</span></span>
4. <span data-ttu-id="36383-195">Granska åtgärderna som krävs för att begära annullering av en godkänd NF-e.</span><span class="sxs-lookup"><span data-stu-id="36383-195">Review the actions that are required to request the cancellation of an approved NF-e.</span></span>

    | <span data-ttu-id="36383-196">Åtgärds-ID</span><span class="sxs-lookup"><span data-stu-id="36383-196">Action ID</span></span> | <span data-ttu-id="36383-197">Namn på åtgärd</span><span class="sxs-lookup"><span data-stu-id="36383-197">Action name</span></span>                  | <span data-ttu-id="36383-198">Åtgärdsbeskrivning</span><span class="sxs-lookup"><span data-stu-id="36383-198">Action description</span></span>                                               |
    |-----------|------------------------------|------------------------------------------------------------------|
    | <span data-ttu-id="36383-199">1</span><span class="sxs-lookup"><span data-stu-id="36383-199">1</span></span>         | <span data-ttu-id="36383-200">Transformera dokument</span><span class="sxs-lookup"><span data-stu-id="36383-200">Transform document</span></span>           | <span data-ttu-id="36383-201">Skapa den NF-e XML-fil för annullering som ska skickas.</span><span class="sxs-lookup"><span data-stu-id="36383-201">Create the NF-e cancellation XML file for submission.</span></span>            |
    | <span data-ttu-id="36383-202">2</span><span class="sxs-lookup"><span data-stu-id="36383-202">2</span></span>         | <span data-ttu-id="36383-203">Signera dokument</span><span class="sxs-lookup"><span data-stu-id="36383-203">Sign document</span></span>                | <span data-ttu-id="36383-204">Använd ett digitalt certifikat i XML-filen.</span><span class="sxs-lookup"><span data-stu-id="36383-204">Apply the digital certificate to the XML file.</span></span>                   |
    | <span data-ttu-id="36383-205">3</span><span class="sxs-lookup"><span data-stu-id="36383-205">3</span></span>         | <span data-ttu-id="36383-206">Ring brasilianska SEFAZ-tjänsten</span><span class="sxs-lookup"><span data-stu-id="36383-206">Call Brazilian SEFAZ service</span></span> | <span data-ttu-id="36383-207">Skicka den signerade XML-filen till webbtjänsterna för annullering.</span><span class="sxs-lookup"><span data-stu-id="36383-207">Submit the signed XML file to the web services for cancellation.</span></span> |
    | <span data-ttu-id="36383-208">4</span><span class="sxs-lookup"><span data-stu-id="36383-208">4</span></span>         | <span data-ttu-id="36383-209">Behandla svar</span><span class="sxs-lookup"><span data-stu-id="36383-209">Process response</span></span>             | <span data-ttu-id="36383-210">Hämta webbtjänstsvaret.</span><span class="sxs-lookup"><span data-stu-id="36383-210">Get the web service response.</span></span>                                    |

#### <a name="set-up-the-url-for-sefaz-web-services"></a><span data-ttu-id="36383-211">Ställ in URL:en för SEFAZ-webbtjänster</span><span class="sxs-lookup"><span data-stu-id="36383-211">Set up the URL for SEFAZ web services</span></span>

1. <span data-ttu-id="36383-212">På fliken **Inställning av funktionsversion** på fliken **Åtgärder** på snabbfliken **Åtgärder** välj **Anropa brasilianska SEFAZ-tjänsten** (åtgärds-ID **3**).</span><span class="sxs-lookup"><span data-stu-id="36383-212">On the **Feature version setup** page, on the **Actions** tab, on the **Actions** FastTab, select **Call Brazilian SEFAZ service** (action ID **3**).</span></span>
2. <span data-ttu-id="36383-213">På snabbfliken **Parametrar** i fältet **Parametrar för URL-adress** anger du webbadressen till SEFAZ-webbtjänsten för annullering av godkänd NF-e.</span><span class="sxs-lookup"><span data-stu-id="36383-213">On the **Parameters** FastTab, in the **URL address parameter** field, enter the URL of the SEFAZ web service for cancellation of an approved NF-e.</span></span>

### <a name="make-an-e-invoicing-environment-available-and-assign-a-draft-version"></a><span data-ttu-id="36383-214">Göra en e-faktureringsmiljö tillgänglig och tilldela en utkastversion</span><span class="sxs-lookup"><span data-stu-id="36383-214">Make an e-Invoicing environment available and assign a Draft version</span></span>

1. <span data-ttu-id="36383-215">På sidan **e-faktureringsfunktioner** på fliken **Miljöer** välj Ändra status **Aktivera**.</span><span class="sxs-lookup"><span data-stu-id="36383-215">On the **e-Invoicing Features** page, on the **Environments** tab, select **Enable**.</span></span>
2. <span data-ttu-id="36383-216">I fältet **miljö** välj miljön.</span><span class="sxs-lookup"><span data-stu-id="36383-216">In the **Environment** field, select the environment.</span></span>
3. <span data-ttu-id="36383-217">I fältet **gäller från** väljer du det datum då miljön ska börja gälla.</span><span class="sxs-lookup"><span data-stu-id="36383-217">In the **Effective from** field, select the date when the environment should become effective.</span></span>
4. <span data-ttu-id="36383-218">Välj **Aktivera**.</span><span class="sxs-lookup"><span data-stu-id="36383-218">Select **Enable**.</span></span>

![Aktivera en e-faktureringsmiljö](media/e-Invoicing-services-get-started-BRA-Enable-e-Invoicing-environment.png)

### <a name="change-the-status-to-completed"></a><span data-ttu-id="36383-220">Ändra status till slutförd</span><span class="sxs-lookup"><span data-stu-id="36383-220">Change the status to Completed</span></span>

1. <span data-ttu-id="36383-221">På sidan **e-faktureringsfunktion** på fliken **Versioner**, välj den version av e-faktureringsfunktionen som har status **Utkast**.</span><span class="sxs-lookup"><span data-stu-id="36383-221">On the **e-Invoicing Features** page, on the **Versions** tab, select the version of the e-Invoicing feature that has a status of **Draft**.</span></span>
2. <span data-ttu-id="36383-222">Välj **Ändra status \> Slutför**.</span><span class="sxs-lookup"><span data-stu-id="36383-222">Select **Change status \> Complete**.</span></span>

### <a name="change-the-status-to-publish"></a><span data-ttu-id="36383-223">Ändra status till publicera</span><span class="sxs-lookup"><span data-stu-id="36383-223">Change the status to Publish</span></span>

1. <span data-ttu-id="36383-224">På sidan **e-faktureringsfunktion** på fliken **Versioner**, välj den version av e-faktureringsfunktionen som har status **Slutförd**.</span><span class="sxs-lookup"><span data-stu-id="36383-224">On the **e-Invoicing Features** page, on the **Versions** tab, select the version of the e-Invoicing feature that has a status of **Completed**.</span></span>
2. <span data-ttu-id="36383-225">Välj **Ändra status \> Publicera**.</span><span class="sxs-lookup"><span data-stu-id="36383-225">Select **Change status \> Publish**.</span></span>

![Publicera e-faktureringsfunktion](media/e-Invoicing-services-get-started-BRA-Publish-e-Invoicing-feature.png)

## <a name="set-up-electronic-invoicing-add-on-integration-in-finance-or-supply-chain-management"></a><span data-ttu-id="36383-227">Ställa in integrering av tillägget elektronisk fakturering i Finance eller Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="36383-227">Set up Electronic invoicing add-on integration in Finance or Supply Chain Management</span></span>

<span data-ttu-id="36383-228">Under inställningen ska du utföra följande uppgifter:</span><span class="sxs-lookup"><span data-stu-id="36383-228">During setup, you will complete these tasks:</span></span>

1. <span data-ttu-id="36383-229">Sätt på den federala NF-e-funktionen för Brasilien.</span><span class="sxs-lookup"><span data-stu-id="36383-229">Turn on the NF-e Federal feature for Brazil.</span></span>
2. <span data-ttu-id="36383-230">Importera den specifika ER-datamodell, ER-datamodellmappning och de format som krävs för NF-e skattedokument.</span><span class="sxs-lookup"><span data-stu-id="36383-230">Import the specific ER data model, the data model mapping, and the formats that are required for NF-e fiscal documents.</span></span>
3. <span data-ttu-id="36383-231">Importera ER-konfiguration och ställ in de svarstyper som krävs för att uppdatera status för skattedokumenten efter överföringsprocessen returneras.</span><span class="sxs-lookup"><span data-stu-id="36383-231">Import the ER configuration, and set up the response types that are required to update the status of the fiscal document after the submission process is returned.</span></span>

### <a name="turn-on-the-nf-e-federal-feature-for-brazil"></a><span data-ttu-id="36383-232">Sätt på den federala NF-e-funktionen för Brasilien</span><span class="sxs-lookup"><span data-stu-id="36383-232">Turn on the NF-e Federal feature for Brazil</span></span>

1. <span data-ttu-id="36383-233">Gå till **organisationsadministration \> inställning \> parametrar för elektroniska dokument**.</span><span class="sxs-lookup"><span data-stu-id="36383-233">Go to **Organization administration \> Setup \> Electronic document parameters**.</span></span>
2. <span data-ttu-id="36383-234">På fliken **Funktioner** markerar du kryssrutan **Aktivera** i raden för funktionsreferens **BR00053**.</span><span class="sxs-lookup"><span data-stu-id="36383-234">On the **Features** tab, select the **Enable** check box in the row for feature reference **BR00053**.</span></span>

### <a name="import-the-er-data-model-mapping-required-for-nf-e-fiscal-documents"></a><span data-ttu-id="36383-235">Importera mappningen för ER-datamodell som krävs för NF-e-skattedokument</span><span class="sxs-lookup"><span data-stu-id="36383-235">Import the ER data model mapping required for NF-e fiscal documents</span></span>

1. <span data-ttu-id="36383-236">Logga in på Finance.</span><span class="sxs-lookup"><span data-stu-id="36383-236">Sign in to Finance.</span></span>
2. <span data-ttu-id="36383-237">I arbetsytan **elektronisk rapportering** i avsnittet **konfigurationsprovider** väljer du panelen **Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="36383-237">In the **Electronic reporting** workspace, in the **Configuration providers** section, select the **Microsoft** tile.</span></span> <span data-ttu-id="36383-238">Kontrollera att konfigurationsprovidern är **aktiverad**.</span><span class="sxs-lookup"><span data-stu-id="36383-238">Make sure that this configuration provider is set to **Active**.</span></span> <span data-ttu-id="36383-239">För information om hur du ställer in en leverantör på **Aktiv**, se [Skapa konfigurationsleverantörer och markera dem som aktiva](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/analytics/tasks/er-configuration-provider-mark-it-active-2016-11).</span><span class="sxs-lookup"><span data-stu-id="36383-239">For information about how to set a provider to **Active**, see [Create configuration providers and mark them as active](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/analytics/tasks/er-configuration-provider-mark-it-active-2016-11).</span></span>
3. <span data-ttu-id="36383-240">Välj **Databaser**.</span><span class="sxs-lookup"><span data-stu-id="36383-240">Select **Repositories**.</span></span>
4. <span data-ttu-id="36383-241">Välj **Global resurs \> Öppna**.</span><span class="sxs-lookup"><span data-stu-id="36383-241">Select **Global resource \> Open**.</span></span>
5. <span data-ttu-id="36383-242">Importera konfigurationer **Mappning av skattedokument**.</span><span class="sxs-lookup"><span data-stu-id="36383-242">Import **Fiscal documents mapping** configurations.</span></span>

### <a name="import-er-configurations-and-set-up-the-response-types-for-fiscal-documents"></a><span data-ttu-id="36383-243">Importera ER-konfigurationer och ställ in svarstyperna för skattedokument</span><span class="sxs-lookup"><span data-stu-id="36383-243">Import ER configurations and set up the response types for fiscal documents</span></span>

1. <span data-ttu-id="36383-244">I arbetsytan **elektronisk rapportering** i avsnittet **konfigurationsprovider** väljer du panelen **Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="36383-244">In the **Electronic reporting** workspace, in the **Configuration providers** section, select the **Microsoft** tile.</span></span>
2. <span data-ttu-id="36383-245">Välj **Databaser**.</span><span class="sxs-lookup"><span data-stu-id="36383-245">Select **Repositories**.</span></span>
3. <span data-ttu-id="36383-246">Välj **Global resurs \> Öppna**.</span><span class="sxs-lookup"><span data-stu-id="36383-246">Select **Global resource \> Open**.</span></span>
4. <span data-ttu-id="36383-247">Importera **import av NF-e fellogg (BR)**, **importformat för NF-e svarsdata (BR)** och **import av NF-e svarsmeddelande (BR)**.</span><span class="sxs-lookup"><span data-stu-id="36383-247">Import **NF-e error log import (BR)**, **NF-e response data import format (BR)**, and **NF-e response message import (BR)**.</span></span>
5. <span data-ttu-id="36383-248">Gå till **organisationsadministration \> inställning \> parametrar för elektroniska dokument**.</span><span class="sxs-lookup"><span data-stu-id="36383-248">Go to **Organization administration \> Setup \> Electronic document parameters**.</span></span>
6. <span data-ttu-id="36383-249">På fliken **Elektroniska dokument** väljer du **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="36383-249">On the **Electronic document** tab, select **Add**.</span></span>
6. <span data-ttu-id="36383-250">I fältet **Registernamn** ange **skattedokumentets rubrik**.</span><span class="sxs-lookup"><span data-stu-id="36383-250">In the **Table name** field, enter **Fiscal document header**.</span></span>
7. <span data-ttu-id="36383-251">I fältet **Dokumentkontext** väljer du **Kundfaktura kontextmodell – skattedokument kontext**.</span><span class="sxs-lookup"><span data-stu-id="36383-251">In the **Document context** field, select **Customer invoice context model – Fiscal document context**.</span></span>
8. <span data-ttu-id="36383-252">Välj **svarstyper**.</span><span class="sxs-lookup"><span data-stu-id="36383-252">Select **Response types**.</span></span>
9. <span data-ttu-id="36383-253">Markera **Ny** och sedan, i fältet **Svarstyp**, markerar du **Svar**.</span><span class="sxs-lookup"><span data-stu-id="36383-253">Select **New**, and then, in the **Response type** field, select **Response**.</span></span>
10. <span data-ttu-id="36383-254">I fältet **Överföringsstatus** välj **Väntande**.</span><span class="sxs-lookup"><span data-stu-id="36383-254">In the **Submission status** field, select **Pending**.</span></span>
11. <span data-ttu-id="36383-255">I fältet **Modellmappning** välj **Importformat för svarsmeddelande – Modellmappning från svarsmeddelande**.</span><span class="sxs-lookup"><span data-stu-id="36383-255">In the **Model mapping** field, select **Response message import format – Model mapping from response message**.</span></span>
12. <span data-ttu-id="36383-256">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="36383-256">Select **Save**.</span></span>
13. <span data-ttu-id="36383-257">Markera **Ny** och sedan, i fältet **Svarstyp**, markerar du **ResponseData**.</span><span class="sxs-lookup"><span data-stu-id="36383-257">Select **New**, and then, in the **Response type** field, enter **ResponseData**.</span></span>
14. <span data-ttu-id="36383-258">I fältet **Överföringsstatus** välj **Väntande**.</span><span class="sxs-lookup"><span data-stu-id="36383-258">In the **Submission status** field, select **Pending**.</span></span>
15. <span data-ttu-id="36383-259">I fältet **modellmappning** väljer du **NFe importformat för svarsdata – import av svarsdata**.</span><span class="sxs-lookup"><span data-stu-id="36383-259">In the **Model mapping** field, select **NFe response data import format – Response data import**.</span></span>
16. <span data-ttu-id="36383-260">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="36383-260">Select **Save**.</span></span>

## <a name="electronic-invoice-processing"></a><span data-ttu-id="36383-261">Elektronisk fakturabearbetning</span><span class="sxs-lookup"><span data-stu-id="36383-261">Electronic invoice processing</span></span>

<span data-ttu-id="36383-262">Under bearbetningen i Finance ska du utföra följande uppgifter:</span><span class="sxs-lookup"><span data-stu-id="36383-262">During processing in Finance, you will complete these tasks:</span></span>

1. <span data-ttu-id="36383-263">Skicka ett skattedokument via tillägget Elektronisk fakturering.</span><span class="sxs-lookup"><span data-stu-id="36383-263">Submit a fiscal document through the Electronic invoicing add-on.</span></span>
2. <span data-ttu-id="36383-264">Visa körningsloggarna för överföring och granska resultaten av bearbetningen.</span><span class="sxs-lookup"><span data-stu-id="36383-264">View the submission execution logs and review the results of processing.</span></span>
3. <span data-ttu-id="36383-265">Skicka annullering av ett skattedokument via tillägget Elektronisk fakturering.</span><span class="sxs-lookup"><span data-stu-id="36383-265">Submit the cancellation of a fiscal document through the Electronic invoicing add-on.</span></span>

### <a name="submit-nf-e-fiscal-documents-for-sefaz-authorization"></a><span data-ttu-id="36383-266">Skicka NF-e-dokument för SEFAZ-auktorisering</span><span class="sxs-lookup"><span data-stu-id="36383-266">Submit NF-e fiscal documents for SEFAZ authorization</span></span> 

<span data-ttu-id="36383-267">När du har aktiverat funktionen **Konfigurerbara integreringstillägg för elektronisk fakturering** kan den gamla processen för NF-e skattedokument för auktorisering (**Exportera/importera NF-e-process**) kan inte längre användas.</span><span class="sxs-lookup"><span data-stu-id="36383-267">After you turn on the **Configurable Electronic invoicing add-on integration** feature, the old process for submitting NF-e fiscal documents for authorization (**Export/Import NF-e process**) can no longer be used.</span></span> <span data-ttu-id="36383-268">Den ersätts med en ny process som kallas **skicka elektroniska dokument**.</span><span class="sxs-lookup"><span data-stu-id="36383-268">It's replaced by a new process that is named **Submit electronic documents**.</span></span>

> [!NOTE]
> <span data-ttu-id="36383-269">Innan du fortsätter måste du kontrollera att du har ett eller flera kundskattedokument modell 55 som har utfärdats av kundens skattemyndighet.</span><span class="sxs-lookup"><span data-stu-id="36383-269">Before you continue, make sure that you have one or more customer fiscal documents model 55 that were issued by the customer's fiscal establishment.</span></span> <span data-ttu-id="36383-270">Riktningen för dessa skattedokument måste ställas in på **utgående** och status måste **skapad**.</span><span class="sxs-lookup"><span data-stu-id="36383-270">The direction for these fiscal documents must be set to **Outgoing**, and the status must be **Created**.</span></span> <span data-ttu-id="36383-271">Mer information finns i avsnittet om att [utfärda kundskattedokument (Brasilien)](https://docs.microsoft.com/dynamics365/finance/localizations/tasks/br-00038-issuing-customer-fiscal-document).</span><span class="sxs-lookup"><span data-stu-id="36383-271">For more information, see [Issue customer fiscal document (Brazil)](https://docs.microsoft.com/dynamics365/finance/localizations/tasks/br-00038-issuing-customer-fiscal-document).</span></span>

1. <span data-ttu-id="36383-272">Gå till **organisationsadministration \> periodisk \> elektroniska dokument \> skicka elektroniska dokument**.</span><span class="sxs-lookup"><span data-stu-id="36383-272">Go to **Organization administration \> Periodic \> Electronic documents \> Submit electronic documents**.</span></span>
2. <span data-ttu-id="36383-273">Ställ alltid in alternativet **Skicka dokument igen** till **Nej** för första inlämningen av ett dokument.</span><span class="sxs-lookup"><span data-stu-id="36383-273">For the first submission of any document, always set the **Resubmit documents** option to **No**.</span></span> <span data-ttu-id="36383-274">Om du måste skicka ett dokument på nytt via tjänsten ställer du in det här alternativet på **Ja**.</span><span class="sxs-lookup"><span data-stu-id="36383-274">If you must resubmit a document through the service, set this option to **Yes**.</span></span>
3. <span data-ttu-id="36383-275">På snabbfliken **Poster att inkludera** välj **Filter** för att öppna dialogrutan **fråga** där du kan skapa en fråga för att välja dokument för överföring.</span><span class="sxs-lookup"><span data-stu-id="36383-275">On the **Records to include** FastTab, select **Filter** to open the **Inquiry** dialog box, where you can build a query to select documents for submission.</span></span>
4. <span data-ttu-id="36383-276">På fliken **Intervall** klickar du på **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="36383-276">On the **Range** tab, select **Add**.</span></span>
5. <span data-ttu-id="36383-277">I fältet **Register** ange **skattedokumentets rubrik**.</span><span class="sxs-lookup"><span data-stu-id="36383-277">In the **Table** field, select **Fiscal document header**.</span></span>
6. <span data-ttu-id="36383-278">I fältet **härlett register** ange **skattedokumentets rubrik**.</span><span class="sxs-lookup"><span data-stu-id="36383-278">In the **Derived table** field, select **Fiscal document header**.</span></span>
6. <span data-ttu-id="36383-279">I fältet **Fält**, välj **Nummer**.</span><span class="sxs-lookup"><span data-stu-id="36383-279">In the **Field** field, select **Number**.</span></span>
7. <span data-ttu-id="36383-280">I fältet **Kriterier** anger du numret på det skattedokument som ska skickas.</span><span class="sxs-lookup"><span data-stu-id="36383-280">In the **Criteria** field, enter the number of the fiscal document that should be submitted.</span></span>
8. <span data-ttu-id="36383-281">Välj **OK** för att stänga dialogrutan **Förfrågning**.</span><span class="sxs-lookup"><span data-stu-id="36383-281">Select **OK** to close the **Inquiry** dialog box.</span></span>
8. <span data-ttu-id="36383-282">Välj **OK** för att skicka de valda dokumenten.</span><span class="sxs-lookup"><span data-stu-id="36383-282">Select **OK** to submit the selected documents.</span></span>

> [!NOTE]
> <span data-ttu-id="36383-283">Under ditt första försök att skicka ett dokument via tjänsten uppmanas du att bekräfta anslutningen med tillägget Elektronisk fakturering.</span><span class="sxs-lookup"><span data-stu-id="36383-283">During your first attempt to submit a document through the service, you will be prompted to confirm the connection with the Electronic invoicing add-on.</span></span> <span data-ttu-id="36383-284">Välj **Klicka här för att ansluta till tjänsten inlämning av elektroniska dokument**.</span><span class="sxs-lookup"><span data-stu-id="36383-284">Select **Click here to connect to Electronic Document Submission Service**.</span></span>

### <a name="view-all-submission-logs"></a><span data-ttu-id="36383-285">Visa alla överföringsloggar</span><span class="sxs-lookup"><span data-stu-id="36383-285">View all submission logs</span></span>

<span data-ttu-id="36383-286">När du har aktiverat funktionen **konfigurerbara integreringstillägg för elektronisk fakturering** finns en ny sida där du kan följa upp processen för att skicka dokument.</span><span class="sxs-lookup"><span data-stu-id="36383-286">After you turn on the **Configurable Electronic invoicing add-on integration** feature, a new page is available that lets you follow up on the document submission process.</span></span> <span data-ttu-id="36383-287">Du kan använda den här sidan om du vill visa överföringsloggar för alla skickade dokument.</span><span class="sxs-lookup"><span data-stu-id="36383-287">You can use this page to view the submission logs for all submitted documents.</span></span>

1. <span data-ttu-id="36383-288">Gå till **organisationsadministration \> periodisk \> elektroniska dokument \> logg för inlämning av elektroniska dokument**.</span><span class="sxs-lookup"><span data-stu-id="36383-288">Go to **Organization administration \> Periodic \> Electronic documents \> Electronic document submission log**.</span></span>
2. <span data-ttu-id="36383-289">I fältet **Dokumenttyp** väljer du **Skattedokumentets rubrik** att endast filtrera skattedokument.</span><span class="sxs-lookup"><span data-stu-id="36383-289">In the **Document type** field, select **Fiscal document header** to filter for fiscal documents only.</span></span>
3. <span data-ttu-id="36383-290">I åtgärdsfönstret, välj **Förfrågningar \> Överföringsinformation** om du vill visa information om körningsloggar för överföring.</span><span class="sxs-lookup"><span data-stu-id="36383-290">On the Action Pane, select **Inquiries \> Submission details** to view the details of the submission execution logs.</span></span>

![Visa information om överföringsloggen](media/e-Invoicing-services-get-started-BRA-View-Submission-log-details.png)

> [!NOTE] 
> <span data-ttu-id="36383-292">För NF-e skattedokument visar kolumnen **Felkod** den returkod som har returnerats av SEFAZ-webbtjänsten.</span><span class="sxs-lookup"><span data-stu-id="36383-292">For NF-e fiscal documents, the **Error code** column shows the return code that was returned by SEFAZ web services.</span></span>

### <a name="view-submission-logs-through-the-fiscal-document-page"></a><span data-ttu-id="36383-293">Visa överföringsloggar via sidan för skattedokument</span><span class="sxs-lookup"><span data-stu-id="36383-293">View submission logs through the fiscal document page</span></span>

<span data-ttu-id="36383-294">När du har aktiverat funktionen **konfigurerbara integreringstillägg för elektronisk fakturering** kan du även visa överföringsloggarna via sidan för skattedokument.</span><span class="sxs-lookup"><span data-stu-id="36383-294">After you turn on the **Configurable Electronic invoicing add-on integration** feature, you can also view the submission logs through the fiscal document page.</span></span>

1. <span data-ttu-id="36383-295">Gå till **Redovisning \> Förfrågningar och rapporter \> Skattedokument \> Alla skattedokument**.</span><span class="sxs-lookup"><span data-stu-id="36383-295">Go to **General ledger \> Inquiries and reports \> Fiscal documents \> All fiscal documents**.</span></span>
2. <span data-ttu-id="36383-296">Välj ett skattedokument som tidigare skickades via tillägget elektronisk fakturering.</span><span class="sxs-lookup"><span data-stu-id="36383-296">Select a fiscal document that was previously submitted through the Electronic invoicing add-on.</span></span>
3. <span data-ttu-id="36383-297">I åtgärdsfönstret på fliken **NF-e federal** välj **Elektronisk dokumentlogg**.</span><span class="sxs-lookup"><span data-stu-id="36383-297">On the Action Pane, on the **NF-e federal** tab, select **Electronic document log**.</span></span>

![Visa överföringsloggar från sidan för skattedokument](media/e-Invoicing-services-get-started-BRA-View-Submission-log-from-Fiscal-document-viewer.png)

### <a name="submit-approved-nf-e-fiscal-documents-for-sefaz-cancellation"></a><span data-ttu-id="36383-299">Skicka godkända NF-e-dokument för SEFAZ-annullering</span><span class="sxs-lookup"><span data-stu-id="36383-299">Submit approved NF-e fiscal documents for SEFAZ cancellation</span></span>

<span data-ttu-id="36383-300">När du har aktiverat funktionen **konfigurerbara integreringstillägg för elektronisk fakturering** kan den gamla processen för att avbryta NF-e-skattedokument inte längre användas.</span><span class="sxs-lookup"><span data-stu-id="36383-300">After you turn on the **Configurable Electronic invoicing add-on integration** feature, the old process for canceling NF-e fiscal documents can no longer be used.</span></span> <span data-ttu-id="36383-301">Det ersätts med en ny annulleringsprocess som är inbäddad på sidan **Logg för inlämning av elektroniska dokument**.</span><span class="sxs-lookup"><span data-stu-id="36383-301">It's replaced by a new cancellation process that is embedded on the **Electronic document submission log** page.</span></span>

> [!NOTE]
> <span data-ttu-id="36383-302">Kontrollera att du har kört annulleringen av kundens skattedokument för ett godkänt NF-e-dokument.</span><span class="sxs-lookup"><span data-stu-id="36383-302">Make sure that you've run the cancellation of the customer fiscal document for an approved NF-e fiscal document.</span></span> <span data-ttu-id="36383-303">Mer information finns i avsnittet om att [Annullera kundskattedokument (Brasilien)](https://docs.microsoft.com/dynamics365/finance/localizations/latam-bra-cancel-customer-fiscal-documents).</span><span class="sxs-lookup"><span data-stu-id="36383-303">For more information see, [Cancel customer fiscal document (Brazil)](https://docs.microsoft.com/dynamics365/finance/localizations/latam-bra-cancel-customer-fiscal-documents).</span></span>

1. <span data-ttu-id="36383-304">Gå till **organisationsadministration \> periodisk \> elektroniska dokument \> logg för inlämning av elektroniska dokument**.</span><span class="sxs-lookup"><span data-stu-id="36383-304">Go to **Organization administration \> Periodic \> Electronic documents \> Electronic document submission log**.</span></span>
2. <span data-ttu-id="36383-305">Välj skattedokument och välj sedan **Funktioner \> Skicka relaterade överföringar**.</span><span class="sxs-lookup"><span data-stu-id="36383-305">Select the fiscal document, and then select **Functions \> Send related submissions**.</span></span>
3. <span data-ttu-id="36383-306">Ange en beskrivning av den relaterade sändningen och klicka sedan på **OK**.</span><span class="sxs-lookup"><span data-stu-id="36383-306">Enter a description for the related submission, and then select **OK**.</span></span>

### <a name="view-cancellation-submission-logs"></a><span data-ttu-id="36383-307">Visa överföringsloggar för annullering</span><span class="sxs-lookup"><span data-stu-id="36383-307">View cancellation submission logs</span></span>

1. <span data-ttu-id="36383-308">Gå till **organisationsadministration \> periodisk \> elektroniska dokument \> logg för inlämning av elektroniska dokument**.</span><span class="sxs-lookup"><span data-stu-id="36383-308">Go to **Organization administration \> Periodic \> Electronic documents \> Electronic document submission log**.</span></span>
2. <span data-ttu-id="36383-309">I fältet **Dokumenttyp** väljer du **Skattedokumentets rubrik** att endast filtrera skattedokument.</span><span class="sxs-lookup"><span data-stu-id="36383-309">In the **Document type** field, select **Fiscal document header** to filter for fiscal documents only.</span></span>
3. <span data-ttu-id="36383-310">Välj skattedokument och välj sedan åtgärdsfönstret **Förfrågningar \> Relaterade överföringar**.</span><span class="sxs-lookup"><span data-stu-id="36383-310">Select the fiscal document, and then, on the Action Pane, select **Inquiries \> Related submission**.</span></span>

    <span data-ttu-id="36383-311">Tillhörande skickade inleveranser är relaterade till en huvudöverföring som först gjordes.</span><span class="sxs-lookup"><span data-stu-id="36383-311">Related submissions are submissions that are related to a main submission that was made first.</span></span> <span data-ttu-id="36383-312">Den överföring som tillåter en specifik NF-e är till exempel huvudöverföring.</span><span class="sxs-lookup"><span data-stu-id="36383-312">For example, the submission that authorizes a specific NF-e is the main submission.</span></span> <span data-ttu-id="36383-313">Överföringen som begär annullering av samma NF-e i SEFAZ är en relaterad överföring.</span><span class="sxs-lookup"><span data-stu-id="36383-313">The submission that requests the cancellation of the same NF-e in SEFAZ is a related submission.</span></span> <span data-ttu-id="36383-314">Den finns bara eftersom den begär att jobbet ska annulleras som skedde genom en annan överföring.</span><span class="sxs-lookup"><span data-stu-id="36383-314">It exists only because it's requesting the cancellation of the job that was done through another submission.</span></span>

    <span data-ttu-id="36383-315">Sidan **relaterade överföringar** visas alla relaterade inskickade och deras inlämningsstatus för ett visst skattedokument.</span><span class="sxs-lookup"><span data-stu-id="36383-315">The **Related submissions** page shows all related submissions, and their submission status, for a given fiscal document.</span></span> <span data-ttu-id="36383-316">På följande bild representerar den första raden inskickad som begärt godkännande av skattedokumentet.</span><span class="sxs-lookup"><span data-stu-id="36383-316">In the following illustration, the first line represents the submission that requested approval of the fiscal document.</span></span> <span data-ttu-id="36383-317">Den andra raden representerar det inskickade som annullerade skattedokumentet.</span><span class="sxs-lookup"><span data-stu-id="36383-317">The second line represents the submission that canceled that fiscal document.</span></span>

    ![Visa överföringsloggar för annullering](media/e-Invoicing-services-get-started-BRA-View-Cancellation-Submission-log.png)

4. <span data-ttu-id="36383-319">I åtgärdsfönstret, välj **Förfrågningar \> Överföringsinformation** om du vill visa information om körningsloggar för överföring.</span><span class="sxs-lookup"><span data-stu-id="36383-319">On the Action Pane, select **Inquiries \> Submission details** to view the details of the submission execution logs.</span></span>

    ![Visa information om överföringsloggar för annullering](media/e-Invoicing-services-get-started-BRA-View-Cancellation-Submission-log-details.png)

## <a name="privacy-notice"></a><span data-ttu-id="36383-321">Sekretesspolicy</span><span class="sxs-lookup"><span data-stu-id="36383-321">Privacy notice</span></span>
<span data-ttu-id="36383-322">Om du aktiverar funktionen BR-00053 (NF-e Federal) kan det krävas att begränsade data skickas, vilket inkluderar organisationens momsregistrerings-ID.</span><span class="sxs-lookup"><span data-stu-id="36383-322">Enabling the BR-00053 (NF-e Federal) feature may require sending limited data, which includes the organization tax registration ID.</span></span> <span data-ttu-id="36383-323">Detta kommer att översändas till tredje parts byråer som har tillstånd av skattemyndigheten för att skicka elektroniska fakturor till denna skattemyndighet i det fördefinierade format som krävs för integrering med den offentliga sektorns webbtjänster.</span><span class="sxs-lookup"><span data-stu-id="36383-323">This will be transmitted to third-party agencies authorized by the tax authority for purposes of sending electronic invoices to this tax authority in the predefined format required for integration with the government’s web service.</span></span> <span data-ttu-id="36383-324">En administratör kan aktivera och inaktivera funktionen BR-00053 (NF-e Federal) genom att navigera till **Organisationsadministration \> Inställningar \> Parametrar för elektroniskt dokument**.</span><span class="sxs-lookup"><span data-stu-id="36383-324">An administrator can enable and disable the BR-00053 (NF-e Federal) feature by navigating to **Organization administration \> Setup \> Electronic document parameters**.</span></span> <span data-ttu-id="36383-325">Välj fliken **Funktioner**, markera den rad som innehåller funktionen BR-00053 och välj sedan lämpligt alternativ.</span><span class="sxs-lookup"><span data-stu-id="36383-325">Select the **Features** tab, select the row containing the BR-00053 feature, and then make the appropriate selection.</span></span> <span data-ttu-id="36383-326">Data som importeras från dessa externa system till denna Dynamics 365 onlinetjänst omfattas av vår [sekretesspolicy](https://go.microsoft.com/fwlink/?LinkId=512132).</span><span class="sxs-lookup"><span data-stu-id="36383-326">Data imported from these external systems into this Dynamics 365 online service are subject to our [privacy statement](https://go.microsoft.com/fwlink/?LinkId=512132).</span></span> <span data-ttu-id="36383-327">Mer information finns i sektionerna om sekretessmeddelanden i landsspecifik funktionsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="36383-327">Please consult the Privacy notice sections in country-specific feature documentation for more information.</span></span>


## <a name="additional-resources"></a><span data-ttu-id="36383-328">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="36383-328">Additional resources</span></span>

- [<span data-ttu-id="36383-329">Tillägg för elektronisk fakturering: översikt</span><span class="sxs-lookup"><span data-stu-id="36383-329">Electronic invoicing add-on overview</span></span>](e-invoicing-service-overview.md)
- [<span data-ttu-id="36383-330">Kom igång med tillägget elektronisk fakturering</span><span class="sxs-lookup"><span data-stu-id="36383-330">Get started with the Electronic invoicing add-on</span></span>](e-invoicing-get-started.md)
- [<span data-ttu-id="36383-331">Ställ in tillägg för elektroniska fakturor</span><span class="sxs-lookup"><span data-stu-id="36383-331">Set up the Electronic invoicing add-on</span></span>](e-invoicing-setup.md)
