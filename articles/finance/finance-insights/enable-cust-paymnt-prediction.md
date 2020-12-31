---
title: Aktivera prediktioner av kundbetalning (förhandsversion)
description: I det här ämnet beskrivs hur du aktiverar och konfigurerar funktionen för kundbetalningsförutsägelse i Ekonomiinsikter.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 05/27/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2020-05-29
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: e10aa9342ec9f089ef8ecec5e1221a31c580fc87
ms.sourcegitcommit: deb711c92251ed48cdf20ea514d03461c26a2262
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/25/2020
ms.locfileid: "4645003"
---
# <a name="enable-customer-payment-predictions-preview"></a><span data-ttu-id="4565c-103">Aktivera prediktioner av kundbetalning (förhandsversion)</span><span class="sxs-lookup"><span data-stu-id="4565c-103">Enable customer payment predictions (preview)</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="4565c-104">I det här ämnet beskrivs hur du aktiverar och konfigurerar funktionen för kundbetalningsförutsägelse i Ekonomiinsikter.</span><span class="sxs-lookup"><span data-stu-id="4565c-104">This topic explains how to turn on and configure the Customer payment predictions feature in Finance insights.</span></span> <span data-ttu-id="4565c-105">Du aktiverar funktionen på arbetsytan **Funktionshantering** och anger konfigurationsinställningar på sidan **Parametrar för ekonomiinsikter**.</span><span class="sxs-lookup"><span data-stu-id="4565c-105">You turn on the feature in the **Feature management** workspace and enter configuration settings on the **Financial insights parameters** page.</span></span> <span data-ttu-id="4565c-106">Det här avsnittet innehåller också information som kan hjälpa dig att effektivt använda funktionen.</span><span class="sxs-lookup"><span data-stu-id="4565c-106">This topic also includes information that can help you effectively use the feature.</span></span>

> [!NOTE]
> <span data-ttu-id="4565c-107">Innan du genomför följande steg måste du se till att slutföra de nödvändiga stegen i ämnet [Konfigurera för Ekonomiinsikter](configure-for-fin-insites.md).</span><span class="sxs-lookup"><span data-stu-id="4565c-107">Before you complete the following steps, be sure to complete the prerequisite steps in the [Configure for Finance insights](configure-for-fin-insites.md) topic.</span></span>

1. <span data-ttu-id="4565c-108">Använd information från miljösidan i Microsoft Dynamics Lifecycle Services (LCS) för att ansluta till den primära instansen av Azure SQL för den miljön.</span><span class="sxs-lookup"><span data-stu-id="4565c-108">Use information from the environment page in Microsoft Dynamics Lifecycle Services (LCS) to connect to the primary instance of Azure SQL for that environment.</span></span> <span data-ttu-id="4565c-109">Kör följande Transact-SQL-kommando (T-SQL) för att aktivera förhandsversioner för sandbox-miljön.</span><span class="sxs-lookup"><span data-stu-id="4565c-109">Run the following Transact-SQL (T-SQL) command to turn on flights for the sandbox environment.</span></span> <span data-ttu-id="4565c-110">(Du kanske måste aktivera åtkomst för din IP-adress i LCS innan du kan fjärransluta till Application Object Server \[AOS\].)</span><span class="sxs-lookup"><span data-stu-id="4565c-110">(You might have to turn on access for your IP address in LCS before you can connect remotely to Application Object Server \[AOS\].)</span></span>

    `INSERT INTO SYSFLIGHTING (FLIGHTNAME, ENABLED, PARTITION) VALUES ('PayPredEnableFeature', 1, 5637144576)`

    > [!NOTE]
    > <span data-ttu-id="4565c-111">Om din distribution av Microsoft Dynamics 365 Finance är en Service Fabric-distribution kan du hoppa över det här steget.</span><span class="sxs-lookup"><span data-stu-id="4565c-111">If your deployment of Microsoft Dynamics 365 Finance is a Service Fabric deployment, you can skip this step.</span></span> <span data-ttu-id="4565c-112">Teamet för ekonomiinsikter ska redan ha aktiverat förhandsversionen för dig.</span><span class="sxs-lookup"><span data-stu-id="4565c-112">The Finance insights team should already have turned on the flight for you.</span></span> <span data-ttu-id="4565c-113">Om funktionen inte visas på arbetsytan **Funktionshantering**, eller om det uppstår problem när du försöker att aktivera den, kontaktar du <fiap@microsoft.com>.</span><span class="sxs-lookup"><span data-stu-id="4565c-113">If you don't see the feature in the **Feature management** workspace, or if experience issues when you try to turn it on, contact <fiap@microsoft.com>.</span></span>

2. <span data-ttu-id="4565c-114">Aktivera funktionen för kundbetalningsinsikter:</span><span class="sxs-lookup"><span data-stu-id="4565c-114">Turn on the Customer payment insights feature:</span></span>

    1. <span data-ttu-id="4565c-115">Gå till **Systemadministration \> Arbetsytor \> Funktionshantering**.</span><span class="sxs-lookup"><span data-stu-id="4565c-115">Go to **System administration \> Workspaces \> Feature management**.</span></span>
    2. <span data-ttu-id="4565c-116">Hitta funktionen med namnet **Kundbetalningsinsikter (förhandsversion)**.</span><span class="sxs-lookup"><span data-stu-id="4565c-116">Find the feature that is named **Customer payment insights (preview)**.</span></span>
    3. <span data-ttu-id="4565c-117">Välj **Aktivera nu**.</span><span class="sxs-lookup"><span data-stu-id="4565c-117">Select **Enable now**.</span></span>

    <span data-ttu-id="4565c-118">Funktionen för kundbetalningsinsikter är nu aktiverad och kan konfigureras.</span><span class="sxs-lookup"><span data-stu-id="4565c-118">The Customer payment insights feature is now turned on and ready to be configured.</span></span>

3. <span data-ttu-id="4565c-119">Konfigurera funktionen för kundbetalningsinsikter:</span><span class="sxs-lookup"><span data-stu-id="4565c-119">Configure the Customer payment insights feature:</span></span>

    1. <span data-ttu-id="4565c-120">Gå till **Kredit och inkasso \> Konfigurera \> Ekonomiinsikter \> Parametrar för ekonomiinsikter**.</span><span class="sxs-lookup"><span data-stu-id="4565c-120">Go to **Credit and collections \> Setup \> Finance insights \> Finance insights parameters**.</span></span>

        <span data-ttu-id="4565c-121">[![Sidan med parametrar för ekonomiinsikter innan funktionen har konfigurerats](./media/finance-insights-parameters.png)](./media/finance-insights-parameters.png)</span><span class="sxs-lookup"><span data-stu-id="4565c-121">[![Financial insights parameters page before the feature is configured](./media/finance-insights-parameters.png)](./media/finance-insights-parameters.png)</span></span>

    2. <span data-ttu-id="4565c-122">På sidan **Parametrar för ekonomiinsikter**, på fliken **Kundbetalningsinsikter**, väljer du länken **Visa de datafält som används i förutsägelsemodellen** för att öppna sidan **Datafält för förutsägelsemodell**.</span><span class="sxs-lookup"><span data-stu-id="4565c-122">On the **Financial insights parameters** page, on the **Customer payment insights** tab, select the **View the data fields used in the prediction model** link to open the **Data fields for prediction model** page.</span></span> <span data-ttu-id="4565c-123">Där kan du visa standardlistan över fält som används för att skapa en AI-förutsägelsemodell för kundbetalningsförutsägelser.</span><span class="sxs-lookup"><span data-stu-id="4565c-123">There, you can view the default list of fields that are used to create the artificial intelligence (AI) prediction model for customer payment predictions.</span></span>

        <span data-ttu-id="4565c-124">Om du vill använda standardlistan med fält för att skapa förutsägelsemodellen stänger du sidan **Datafält för förutsägelsemodell** och väljer sedan **Ja** för alternativet **Aktivera funktion** på sidan **Parametrar för ekonomiinsikter**.</span><span class="sxs-lookup"><span data-stu-id="4565c-124">To use the default list of fields to create the prediction model, close the **Data fields for prediction model** page, and then, on the **Financial insights parameters** page, set the **Enable feature** option to **Yes**.</span></span>

    3. <span data-ttu-id="4565c-125">Ange transaktionsperioden "mycket sent" för att definiera vad den förutsägelsebucketen **Mycket sent** innebär för din verksamhet.</span><span class="sxs-lookup"><span data-stu-id="4565c-125">Specify the "very late" transaction period to define what the **Very late** prediction bucket means for your business.</span></span>

        <span data-ttu-id="4565c-126">För varje öppen faktura förutsäger systemet sannolikheten för betalning i tre buckets: **i tid**, **sent** och **mycket sent**.</span><span class="sxs-lookup"><span data-stu-id="4565c-126">For each open invoice, the system predicts the probability of payment in three buckets: **On time**, **Late**, and **Very late**.</span></span>

        - <span data-ttu-id="4565c-127">**I tid** – Denna bucket inkluderar betalningar som förutsägs betalas på eller före transaktionens förfallodatum.</span><span class="sxs-lookup"><span data-stu-id="4565c-127">**On time** – This bucket includes payments that are predicted to be paid on or before the transaction due date.</span></span>
        - <span data-ttu-id="4565c-128">**Sent** – Denna bucket inkluderar betalningar som förutsägs betalas efter transaktionens förfallodatum men innan transaktionsperioden "mycket sent" har startats.</span><span class="sxs-lookup"><span data-stu-id="4565c-128">**Late** – This bucket includes payments that are predicted to be paid after the transaction due date but before the start of the "very late" transaction period.</span></span>
        - <span data-ttu-id="4565c-129">**Mycket sent** – Denna bucket inkluderar betalningar som förutsägs betalas efter att transaktionsperioden "mycket sent" har startats.</span><span class="sxs-lookup"><span data-stu-id="4565c-129">**Very late** – This bucket includes payments that are predicted to be paid after the start of the "very late" transaction period.</span></span>

        > [!NOTE]
        > <span data-ttu-id="4565c-130">Om du ändrar transaktionsperioden "mycket sent" och väljer **Ändra tröskel för Sent** efter att AI-förutsägelsemodellen för kundbetalningar har skapats tas den befintliga förutsägelsemodellen bort och en ny modell skapas.</span><span class="sxs-lookup"><span data-stu-id="4565c-130">If you change the "very late" transaction period and select **Change late threshold** after the AI prediction model for customer payments has been created, the existing prediction model is deleted, and a new model is created.</span></span> <span data-ttu-id="4565c-131">Den nya förutsägelsemodellen flyttar transaktionerna till perioden "mycket sent", baserat på de inställningar som angavs för att definiera den.</span><span class="sxs-lookup"><span data-stu-id="4565c-131">The new prediction model will move transactions into the "very late" period, based on the settings that were entered to define it.</span></span>

    4. <span data-ttu-id="4565c-132">När du har definierat transaktionsperioden "mycket sent" väljer **Skapa förutsägelsemodell** för att skapa förutsägelsemodellen.</span><span class="sxs-lookup"><span data-stu-id="4565c-132">After you've finished defining the "very late" transaction period, select **Create prediction model** to create the prediction model.</span></span> <span data-ttu-id="4565c-133">I avsnittet **Förutsägelsemodell** på sidan **Parametrar för ekonomiinsikter** visas status för förutsägelsemodellen.</span><span class="sxs-lookup"><span data-stu-id="4565c-133">The **Prediction model** section on the **Financial insights parameters** page shows the status of the prediction model.</span></span>

        > [!NOTE]
        > <span data-ttu-id="4565c-134">Du kan när som helst medan förusägelsemodellen skapas välja **Återställ modellskapande** för att starta om processen.</span><span class="sxs-lookup"><span data-stu-id="4565c-134">At any time while the prediction model is being created, you can select **Reset model creation** to restart the process.</span></span>

    <span data-ttu-id="4565c-135">Funktionen har nu konfigurerats och är redo att användas.</span><span class="sxs-lookup"><span data-stu-id="4565c-135">The feature has now been configured and is ready to be used.</span></span>

<span data-ttu-id="4565c-136">När funktionen har aktiverats och konfigurerats, och om förutsägelsemodellen har skapats och fungerar, visar avsnittet **Förutsägelsemodell** på sidan **Parametrar för ekonomiinsikter** hur noggrann modellen är, vilket visas i bilden nedan.</span><span class="sxs-lookup"><span data-stu-id="4565c-136">After the feature has been turned on and configured, and the prediction model has been created and is working, the **Prediction model** section of the **Financial insights parameters** page shows the accuracy of the model, as shown in the following illustration.</span></span>

<span data-ttu-id="4565c-137">[![Noggrannhet för förutsägelsemodellen på sidan Parametrar för ekonomiinsikter](./media/finance-insights-parameters-accuracy.png)](./media/finance-insights-parameters-accuracy.png)</span><span class="sxs-lookup"><span data-stu-id="4565c-137">[![Accuracy of the prediction model on the Financial insights parameters page](./media/finance-insights-parameters-accuracy.png)](./media/finance-insights-parameters-accuracy.png)</span></span>

## <a name="release-details"></a><span data-ttu-id="4565c-138">Frisläppningsinformation</span><span class="sxs-lookup"><span data-stu-id="4565c-138">Release details</span></span>

<span data-ttu-id="4565c-139">Den allmänt tillgängliga förhandsversionen av Ekonomiinsikter finns tillgänglig för utvärderingsdistribution i USA, Europa och Storbritannien.</span><span class="sxs-lookup"><span data-stu-id="4565c-139">Finance insights public preview is available for trial deployments in the United States of America, Europe, and the United Kingdom.</span></span> <span data-ttu-id="4565c-140">Microsoft lägger stegvis till support för fler regioner.</span><span class="sxs-lookup"><span data-stu-id="4565c-140">Microsoft is incrementally adding support for more regions.</span></span>

<span data-ttu-id="4565c-141">Funktionerna för allmänt tillgänglig förhandsversion kan och ska bara aktiveras i nivå-2-sandbox-miljöer.</span><span class="sxs-lookup"><span data-stu-id="4565c-141">Public preview features can and should be turned on only in Tier-2 sandbox environments.</span></span> <span data-ttu-id="4565c-142">Konfiguration och AI-modeller som skapas i en sandbox-miljö kan inte migreras till en produktionsmiljö.</span><span class="sxs-lookup"><span data-stu-id="4565c-142">Setup and AI models that are created in a sandbox environment can't be migrated to a production environment.</span></span> <span data-ttu-id="4565c-143">Mer information finns i [Tilläggsavtal för Microsoft Dynamics 365 förhandsversioner](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/public-preview-terms).</span><span class="sxs-lookup"><span data-stu-id="4565c-143">For more information, see [Supplemental Terms of Use for Microsoft Dynamics 365 Previews](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/public-preview-terms).</span></span>

## <a name="privacy-notice"></a><span data-ttu-id="4565c-144">Sekretesspolicy</span><span class="sxs-lookup"><span data-stu-id="4565c-144">Privacy notice</span></span>

<span data-ttu-id="4565c-145">Förhandsversioner (1) kan använda färre sekretess- och säkerhetsfunktioner än Dynamics 365 Finance and Operations, (2) de ingår inte i serviceavtalet (SLA) för den här tjänsten, (3) bör inte användas för behandling av personuppgifter eller andra uppgifter som omfattas av lagar och andra efterlevnadskrav, samt (4) har begränsad support.</span><span class="sxs-lookup"><span data-stu-id="4565c-145">Previews (1) might use less privacy and fewer security measures than the Dynamics 365 Finance and Operations service, (2) aren't included in the service level agreement (SLA) for this service, (3) should not be used to process personal data or other data that is subject to legal or regulatory compliance requirements, and (4) have limited support.</span></span>
