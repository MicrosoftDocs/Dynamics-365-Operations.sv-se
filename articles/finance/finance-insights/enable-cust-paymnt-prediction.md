---
title: Aktivera prediktioner av kundbetalning (förhandsversion)
description: I det här ämnet beskrivs hur du aktiverar och konfigurerar funktionen för kundbetalningsförutsägelse i Finance-insikter.
author: ShivamPandey-msft
ms.date: 06/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2020-05-29
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: ae957f592ad9a1237817fec5d4172295f9a53020
ms.sourcegitcommit: 655b0e16c7aef6182cd58bc816b901470e1bb2ce
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/10/2021
ms.locfileid: "6222596"
---
# <a name="enable-customer-payment-predictions-preview"></a><span data-ttu-id="4c9e4-103">Aktivera prediktioner av kundbetalning (förhandsversion)</span><span class="sxs-lookup"><span data-stu-id="4c9e4-103">Enable customer payment predictions (preview)</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="4c9e4-104">I det här ämnet beskrivs hur du aktiverar och konfigurerar funktionen för kundbetalningsförutsägelse i Finance-insikter.</span><span class="sxs-lookup"><span data-stu-id="4c9e4-104">This topic explains how to turn on and configure the Customer payment predictions feature in Finance insights.</span></span> <span data-ttu-id="4c9e4-105">Du aktiverar funktionen på arbetsytan **Funktionshantering** och anger konfigurationsinställningar på sidan **Parametrar för ekonomiinsikter**.</span><span class="sxs-lookup"><span data-stu-id="4c9e4-105">You turn on the feature in the **Feature management** workspace and enter configuration settings on the **Financial insights parameters** page.</span></span> <span data-ttu-id="4c9e4-106">Det här avsnittet innehåller också information som kan hjälpa dig att effektivt använda funktionen.</span><span class="sxs-lookup"><span data-stu-id="4c9e4-106">This topic also includes information that can help you effectively use the feature.</span></span>

> [!NOTE]
> <span data-ttu-id="4c9e4-107">Innan du genomför följande steg måste du se till att slutföra de nödvändiga stegen i ämnet [Konfigurera för Finance-insikter](configure-for-fin-insites.md).</span><span class="sxs-lookup"><span data-stu-id="4c9e4-107">Before you complete the following steps, be sure to complete the prerequisite steps in the [Configure for Finance insights](configure-for-fin-insites.md) topic.</span></span>

1. <span data-ttu-id="4c9e4-108">Använd information från miljösidan i Microsoft Dynamics Lifecycle Services (LCS) för att ansluta till den primära instansen av Azure SQL för den miljön.</span><span class="sxs-lookup"><span data-stu-id="4c9e4-108">Use information from the environment page in Microsoft Dynamics Lifecycle Services (LCS) to connect to the primary instance of Azure SQL for that environment.</span></span> <span data-ttu-id="4c9e4-109">Kör följande Transact-SQL-kommando (T-SQL) för att aktivera förhandsversioner för sandbox-miljön.</span><span class="sxs-lookup"><span data-stu-id="4c9e4-109">Run the following Transact-SQL (T-SQL) command to turn on flights for the sandbox environment.</span></span> <span data-ttu-id="4c9e4-110">(Du kanske måste aktivera åtkomst för din IP-adress i LCS innan du kan fjärransluta till Application Object Server \[AOS\].)</span><span class="sxs-lookup"><span data-stu-id="4c9e4-110">(You might have to turn on access for your IP address in LCS before you can connect remotely to Application Object Server \[AOS\].)</span></span>

    `INSERT INTO SYSFLIGHTING (FLIGHTNAME, ENABLED) VALUES ('PayPredEnableFeature', 1)`

    > [!NOTE]
    > <span data-ttu-id="4c9e4-111">Hoppa över det här steget om du använder version 10.0.20 eller senare, eller om du använder en Service Fabric-distribution.</span><span class="sxs-lookup"><span data-stu-id="4c9e4-111">Skip this step if you're using version 10.0.20 or later, or if you're using a Service Fabric deployment.</span></span> <span data-ttu-id="4c9e4-112">Teamet för ekonomiinsikter ska redan ha aktiverat förhandsversionen för dig.</span><span class="sxs-lookup"><span data-stu-id="4c9e4-112">The Finance insights team should already have turned on the flight for you.</span></span> <span data-ttu-id="4c9e4-113">Om funktionen inte visas på arbetsytan **Funktionshantering**, eller om det uppstår problem när du försöker att aktivera den, kontaktar du <fiap@microsoft.com>.</span><span class="sxs-lookup"><span data-stu-id="4c9e4-113">If you don't see the feature in the **Feature management** workspace, or if you experience issues when you try to turn it on, contact <fiap@microsoft.com>.</span></span> 

2. <span data-ttu-id="4c9e4-114">Aktivera funktionen för kundbetalningsinsikter:</span><span class="sxs-lookup"><span data-stu-id="4c9e4-114">Turn on the Customer payment insights feature:</span></span>

    1. <span data-ttu-id="4c9e4-115">Gå till **Systemadministration \> Arbetsytor \> Funktionshantering**.</span><span class="sxs-lookup"><span data-stu-id="4c9e4-115">Go to **System administration \> Workspaces \> Feature management**.</span></span>
    2. <span data-ttu-id="4c9e4-116">Hitta funktionen med namnet **Kundbetalningsinsikter (förhandsversion)**.</span><span class="sxs-lookup"><span data-stu-id="4c9e4-116">Find the feature that is named **Customer payment insights (preview)**.</span></span>
    3. <span data-ttu-id="4c9e4-117">Välj **Aktivera nu**.</span><span class="sxs-lookup"><span data-stu-id="4c9e4-117">Select **Enable now**.</span></span>

    <span data-ttu-id="4c9e4-118">Funktionen för kundbetalningsinsikter är nu aktiverad och kan konfigureras.</span><span class="sxs-lookup"><span data-stu-id="4c9e4-118">The Customer payment insights feature is now turned on and ready to be configured.</span></span>

3. <span data-ttu-id="4c9e4-119">Konfigurera funktionen för kundbetalningsinsikter:</span><span class="sxs-lookup"><span data-stu-id="4c9e4-119">Configure the Customer payment insights feature:</span></span>

    1. <span data-ttu-id="4c9e4-120">Gå till **Kredit och inkasso \> Konfigurera \> Finance-insikter \> Parametrar för ekonomiinsikter**.</span><span class="sxs-lookup"><span data-stu-id="4c9e4-120">Go to **Credit and collections \> Setup \> Finance insights \> Finance insights parameters**.</span></span>

        <span data-ttu-id="4c9e4-121">[![Sidan med parametrar för ekonomiinsikter innan funktionen har konfigurerats](./media/finance-insights-parameters.png)](./media/finance-insights-parameters.png)</span><span class="sxs-lookup"><span data-stu-id="4c9e4-121">[![Financial insights parameters page before the feature is configured](./media/finance-insights-parameters.png)](./media/finance-insights-parameters.png)</span></span>

    2. <span data-ttu-id="4c9e4-122">På sidan **Parametrar för ekonomiinsikter**, på fliken **Kundbetalningsinsikter**, väljer du länken **Visa de datafält som används i förutsägelsemodellen** för att öppna sidan **Datafält för förutsägelsemodell**.</span><span class="sxs-lookup"><span data-stu-id="4c9e4-122">On the **Financial insights parameters** page, on the **Customer payment insights** tab, select the **View the data fields used in the prediction model** link to open the **Data fields for prediction model** page.</span></span> <span data-ttu-id="4c9e4-123">Där kan du visa standardlistan över fält som används för att skapa en AI-förutsägelsemodell för kundbetalningsförutsägelser.</span><span class="sxs-lookup"><span data-stu-id="4c9e4-123">There, you can view the default list of fields that are used to create the artificial intelligence (AI) prediction model for customer payment predictions.</span></span>

        <span data-ttu-id="4c9e4-124">Om du vill använda standardlistan med fält för att skapa förutsägelsemodellen stänger du sidan **Datafält för förutsägelsemodell** och väljer sedan **Ja** för alternativet **Aktivera funktion** på sidan **Parametrar för ekonomiinsikter**.</span><span class="sxs-lookup"><span data-stu-id="4c9e4-124">To use the default list of fields to create the prediction model, close the **Data fields for prediction model** page, and then, on the **Financial insights parameters** page, set the **Enable feature** option to **Yes**.</span></span>

    3. <span data-ttu-id="4c9e4-125">Ange transaktionsperioden "mycket sent" för att definiera vad den förutsägelsebucketen **Mycket sent** innebär för din verksamhet.</span><span class="sxs-lookup"><span data-stu-id="4c9e4-125">Specify the "very late" transaction period to define what the **Very late** prediction bucket means for your business.</span></span>

        <span data-ttu-id="4c9e4-126">För varje öppen faktura förutsäger systemet sannolikheten för betalning i tre buckets: **i tid**, **sent** och **mycket sent**.</span><span class="sxs-lookup"><span data-stu-id="4c9e4-126">For each open invoice, the system predicts the probability of payment in three buckets: **On time**, **Late**, and **Very late**.</span></span>

        - <span data-ttu-id="4c9e4-127">**I tid** – Denna bucket inkluderar betalningar som förutsägs betalas på eller före transaktionens förfallodatum.</span><span class="sxs-lookup"><span data-stu-id="4c9e4-127">**On time** – This bucket includes payments that are predicted to be paid on or before the transaction due date.</span></span>
        - <span data-ttu-id="4c9e4-128">**Sent** – Denna bucket inkluderar betalningar som förutsägs betalas efter transaktionens förfallodatum men innan transaktionsperioden "mycket sent" har startats.</span><span class="sxs-lookup"><span data-stu-id="4c9e4-128">**Late** – This bucket includes payments that are predicted to be paid after the transaction due date but before the start of the "very late" transaction period.</span></span>
        - <span data-ttu-id="4c9e4-129">**Mycket sent** – Denna bucket inkluderar betalningar som förutsägs betalas efter att transaktionsperioden "mycket sent" har startats.</span><span class="sxs-lookup"><span data-stu-id="4c9e4-129">**Very late** – This bucket includes payments that are predicted to be paid after the start of the "very late" transaction period.</span></span>

        > [!NOTE]
        > <span data-ttu-id="4c9e4-130">Om du ändrar transaktionsperioden "mycket sent" och väljer **Ändra tröskel för Sent** efter att AI-förutsägelsemodellen för kundbetalningar har skapats tas den befintliga förutsägelsemodellen bort och en ny modell skapas.</span><span class="sxs-lookup"><span data-stu-id="4c9e4-130">If you change the "very late" transaction period and select **Change late threshold** after the AI prediction model for customer payments has been created, the existing prediction model is deleted, and a new model is created.</span></span> <span data-ttu-id="4c9e4-131">Den nya förutsägelsemodellen flyttar transaktionerna till perioden "mycket sent", baserat på de inställningar som angavs för att definiera den.</span><span class="sxs-lookup"><span data-stu-id="4c9e4-131">The new prediction model will move transactions into the "very late" period, based on the settings that were entered to define it.</span></span>

    4. <span data-ttu-id="4c9e4-132">När du har definierat transaktionsperioden "mycket sent" väljer **Skapa förutsägelsemodell** för att skapa förutsägelsemodellen.</span><span class="sxs-lookup"><span data-stu-id="4c9e4-132">After you've finished defining the "very late" transaction period, select **Create prediction model** to create the prediction model.</span></span> <span data-ttu-id="4c9e4-133">I avsnittet **Förutsägelsemodell** på sidan **Parametrar för ekonomiinsikter** visas status för förutsägelsemodellen.</span><span class="sxs-lookup"><span data-stu-id="4c9e4-133">The **Prediction model** section on the **Financial insights parameters** page shows the status of the prediction model.</span></span>

        > [!NOTE]
        > <span data-ttu-id="4c9e4-134">Du kan när som helst medan förusägelsemodellen skapas välja **Återställ modellskapande** för att starta om processen.</span><span class="sxs-lookup"><span data-stu-id="4c9e4-134">At any time while the prediction model is being created, you can select **Reset model creation** to restart the process.</span></span>

    <span data-ttu-id="4c9e4-135">Funktionen har nu konfigurerats och är redo att användas.</span><span class="sxs-lookup"><span data-stu-id="4c9e4-135">The feature has now been configured and is ready to be used.</span></span>

<span data-ttu-id="4c9e4-136">När funktionen har aktiverats och konfigurerats, och om förutsägelsemodellen har skapats och fungerar, visar avsnittet **Förutsägelsemodell** på sidan **Parametrar för ekonomiinsikter** hur noggrann modellen är, vilket visas i bilden nedan.</span><span class="sxs-lookup"><span data-stu-id="4c9e4-136">After the feature has been turned on and configured, and the prediction model has been created and is working, the **Prediction model** section of the **Financial insights parameters** page shows the accuracy of the model, as shown in the following illustration.</span></span>

<span data-ttu-id="4c9e4-137">[![Noggrannhet för förutsägelsemodellen på sidan Parametrar för ekonomiinsikter](./media/finance-insights-parameters-accuracy.png)](./media/finance-insights-parameters-accuracy.png)</span><span class="sxs-lookup"><span data-stu-id="4c9e4-137">[![Accuracy of the prediction model on the Financial insights parameters page](./media/finance-insights-parameters-accuracy.png)](./media/finance-insights-parameters-accuracy.png)</span></span>

## <a name="release-details"></a><span data-ttu-id="4c9e4-138">Frisläppningsinformation</span><span class="sxs-lookup"><span data-stu-id="4c9e4-138">Release details</span></span>

<span data-ttu-id="4c9e4-139">Den allmänt tillgängliga förhandsversionen av Finance-insikter finns tillgänglig för bedömningsdistribution i USA, Europa och Storbritannien.</span><span class="sxs-lookup"><span data-stu-id="4c9e4-139">Finance insights public preview is available for trial deployments in the United States of America, Europe, and the United Kingdom.</span></span> <span data-ttu-id="4c9e4-140">Microsoft lägger stegvis till support för fler regioner.</span><span class="sxs-lookup"><span data-stu-id="4c9e4-140">Microsoft is incrementally adding support for more regions.</span></span>

<span data-ttu-id="4c9e4-141">Funktionerna för allmänt tillgänglig förhandsversion kan och ska bara aktiveras i nivå-2-sandbox-miljöer.</span><span class="sxs-lookup"><span data-stu-id="4c9e4-141">Public preview features can and should be turned on only in Tier-2 sandbox environments.</span></span> <span data-ttu-id="4c9e4-142">Konfiguration och AI-modeller som skapas i en sandbox-miljö kan inte migreras till en produktionsmiljö.</span><span class="sxs-lookup"><span data-stu-id="4c9e4-142">Setup and AI models that are created in a sandbox environment can't be migrated to a production environment.</span></span> <span data-ttu-id="4c9e4-143">Mer information finns i [Tilläggsavtal för Microsoft Dynamics 365 förhandsversioner](../../fin-ops-core/fin-ops/get-started/public-preview-terms.md).</span><span class="sxs-lookup"><span data-stu-id="4c9e4-143">For more information, see [Supplemental Terms of Use for Microsoft Dynamics 365 Previews](../../fin-ops-core/fin-ops/get-started/public-preview-terms.md).</span></span>

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
