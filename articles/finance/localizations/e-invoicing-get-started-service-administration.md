---
title: Kom i gång med tjänstadministration för elektronisk fakturering
description: I det här avsnittet beskrivs hur du kommer igång med Elektronisk fakturering.
author: gionoder
ms.date: 03/29/2021
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
ms.openlocfilehash: ec431cb4a3620459d905f64a80fd820a2113290f
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5840158"
---
# <a name="get-started-with-electronic-invoicing-service-administration"></a><span data-ttu-id="59bc3-103">Kom i gång med tjänstadministration för elektronisk fakturering</span><span class="sxs-lookup"><span data-stu-id="59bc3-103">Get started with Electronic invoicing service administration</span></span>

[!include [banner](../includes/banner.md)]

## <a name="prerequisites"></a><span data-ttu-id="59bc3-104">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="59bc3-104">Prerequisites</span></span>

<span data-ttu-id="59bc3-105">Innan du kan slutföra procedurerna i detta ämne måste följande förutsättningar finnas på plats:</span><span class="sxs-lookup"><span data-stu-id="59bc3-105">Before you complete the procedures in this topic, the following prerequisites must be in place:</span></span>

- <span data-ttu-id="59bc3-106">Du måste ha tillgång till ditt Microsoft Dynamics Lifecycle Services-konto (LCS).</span><span class="sxs-lookup"><span data-stu-id="59bc3-106">You must have access to your Microsoft Dynamics Lifecycle Services (LCS) account.</span></span>
- <span data-ttu-id="59bc3-107">Du måste ha ett LCS-projekt som innehåller version 10.0.17 eller senare av Microsoft Dynamics 365 Finance och Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="59bc3-107">You must have an LCS project that includes version 10.0.17 or later of Microsoft Dynamics 365 Finance and Dynamics 365 Supply Chain Management.</span></span> <span data-ttu-id="59bc3-108">Dessa program måste dessutom distribueras i något av följande Azure-områden:</span><span class="sxs-lookup"><span data-stu-id="59bc3-108">Additionally, these apps must be deployed in one of the following Azure geographies:</span></span>

    - <span data-ttu-id="59bc3-109">Östra USA</span><span class="sxs-lookup"><span data-stu-id="59bc3-109">East US</span></span>
    - <span data-ttu-id="59bc3-110">Västra USA</span><span class="sxs-lookup"><span data-stu-id="59bc3-110">West US</span></span>
    - <span data-ttu-id="59bc3-111">Norra EU</span><span class="sxs-lookup"><span data-stu-id="59bc3-111">North EU</span></span>
    - <span data-ttu-id="59bc3-112">Västra EU</span><span class="sxs-lookup"><span data-stu-id="59bc3-112">West EU</span></span>

- <span data-ttu-id="59bc3-113">Du måste ha tillgång till ditt Dynamics 365 Regulatory Configuration Services-konto (RCS).</span><span class="sxs-lookup"><span data-stu-id="59bc3-113">You must have access to your Dynamics 365 Regulatory Configuration Services (RCS) account.</span></span>
- <span data-ttu-id="59bc3-114">Du måste aktivera globaliseringsfunktionen för ditt RCS-konto i funktionshanteringen.</span><span class="sxs-lookup"><span data-stu-id="59bc3-114">You must activate the Globalization feature for your RCS account in Feature management.</span></span> <span data-ttu-id="59bc3-115">Mer information finns i [Regulatory Configuration Services (RCS) – globaliseringsfunktioner](rcs-globalization-feature.md).</span><span class="sxs-lookup"><span data-stu-id="59bc3-115">For more information, see [Regulatory Configuration Services (RCS) - Globalization features](rcs-globalization-feature.md).</span></span>
- <span data-ttu-id="59bc3-116">Du måste skapa ett nyckelvalv och ett lagringskonto i Azure.</span><span class="sxs-lookup"><span data-stu-id="59bc3-116">You must create a key vault and a storage account in Azure.</span></span> <span data-ttu-id="59bc3-117">Mer information finns i [Skapa ett Azure-lagringskonto och ett nyckelvalv](e-invoicing-create-azure-storage-account-key-vault.md).</span><span class="sxs-lookup"><span data-stu-id="59bc3-117">For more information, see [Create an Azure storage account and a key vault](e-invoicing-create-azure-storage-account-key-vault.md).</span></span>

## <a name="install-the-add-in-for-microservices-in-lifecycle-services"></a><span data-ttu-id="59bc3-118">Installera tillägget för mikrotjänster i Lifecycle Services</span><span class="sxs-lookup"><span data-stu-id="59bc3-118">Install the add-in for microservices in Lifecycle Services</span></span>

1. <span data-ttu-id="59bc3-119">Logga in på LCS-kontot.</span><span class="sxs-lookup"><span data-stu-id="59bc3-119">Sign in to your LCS account.</span></span>
2. <span data-ttu-id="59bc3-120">Välj panelen **Hantera förhandsgranskning**.</span><span class="sxs-lookup"><span data-stu-id="59bc3-120">Select the **Preview feature management** tile.</span></span>
3. <span data-ttu-id="59bc3-121">I avsnittet **Funktioner i allmänt tillgänglig förhandsversion** väljer du **Tjänst för e-fakturering**.</span><span class="sxs-lookup"><span data-stu-id="59bc3-121">In the **Public Preview Features** section, select **e-Invoicing service**.</span></span>
4. <span data-ttu-id="59bc3-122">Se till att alternativet **Förhandsgranskning aktiverad** är inställt på **Ja**.</span><span class="sxs-lookup"><span data-stu-id="59bc3-122">Make sure that the **Preview feature enabled** option is set to **Yes**.</span></span>
5. <span data-ttu-id="59bc3-123">Välj ditt LCS-distributionsprojekt på LCS-instrumentpanelen.</span><span class="sxs-lookup"><span data-stu-id="59bc3-123">On your LCS dashboard, select your LCS deployment project.</span></span> <span data-ttu-id="59bc3-124">LCS-projektet måste köras.</span><span class="sxs-lookup"><span data-stu-id="59bc3-124">The LCS project must be running.</span></span>
7. <span data-ttu-id="59bc3-125">På fliken **Miljötillägg** välj **Installera ett nytt tillägg**.</span><span class="sxs-lookup"><span data-stu-id="59bc3-125">On the **Environment add-ins** tab, select **Install a new add-in**.</span></span>
8. <span data-ttu-id="59bc3-126">Välj **e-faktureringstjänster**.</span><span class="sxs-lookup"><span data-stu-id="59bc3-126">Select **e-invoicing Services**.</span></span>
9. <span data-ttu-id="59bc3-127">I fältet **AAD-program-ID**, ange **091c98b0-a1c9-4b02-b62c-7753395ccabe**.</span><span class="sxs-lookup"><span data-stu-id="59bc3-127">In the **AAD application ID** field, enter **091c98b0-a1c9-4b02-b62c-7753395ccabe**.</span></span> <span data-ttu-id="59bc3-128">Detta är ett fast värde.</span><span class="sxs-lookup"><span data-stu-id="59bc3-128">This is a fixed value.</span></span>
10. <span data-ttu-id="59bc3-129">I fältet **AAD innehavar-ID** anger du innehavar-ID för ditt Azure abonnemangskonto.</span><span class="sxs-lookup"><span data-stu-id="59bc3-129">In the **AAD tenant ID** field, enter the tenant ID of your Azure subscription account.</span></span>
11. <span data-ttu-id="59bc3-130">Granska villkoren och markera sedan kryssrutan.</span><span class="sxs-lookup"><span data-stu-id="59bc3-130">Review the terms and conditions, and then select the check box.</span></span>
12. <span data-ttu-id="59bc3-131">Välj **Installera**.</span><span class="sxs-lookup"><span data-stu-id="59bc3-131">Select **Install**.</span></span>


## <a name="set-up-the-parameters-for-rcs-integration-with-electronic-invoicing"></a><span data-ttu-id="59bc3-132">Ställ in parametrarna för RCS-integrationen med Elektronisk fakturering</span><span class="sxs-lookup"><span data-stu-id="59bc3-132">Set up the parameters for RCS integration with Electronic invoicing</span></span>

1. <span data-ttu-id="59bc3-133">Logga in på RCS-kontot.</span><span class="sxs-lookup"><span data-stu-id="59bc3-133">Sign in to your RCS account.</span></span>
2. <span data-ttu-id="59bc3-134">I arbetsytan **elektronisk rapportering** i avsnittet **Relaterade länkar** väljer du **parametrar för elektronisk rapportering**.</span><span class="sxs-lookup"><span data-stu-id="59bc3-134">In the **Electronic reporting** workspace, in the **Related links** section, select **Electronic reporting parameters**.</span></span>
3. <span data-ttu-id="59bc3-135">På fliken **Tjänst för e-fakturering**, under fliken **URI för tjänstens slutpunkt** anger du ungefärlig tjänsteslutpunkt för ditt Azure-område enligt följande tabell.</span><span class="sxs-lookup"><span data-stu-id="59bc3-135">On the **e-Invoicing service** tab, in the **Service endpoint URI** field, enter the appropriate service endpoint for your Azure geography, as shown in the following table.</span></span>

    | <span data-ttu-id="59bc3-136">Azure-område för datacenter</span><span class="sxs-lookup"><span data-stu-id="59bc3-136">Datacenter Azure geography</span></span> | <span data-ttu-id="59bc3-137">URI för tjänstslutpunkt</span><span class="sxs-lookup"><span data-stu-id="59bc3-137">Service endpoint URI</span></span>                                                       |
    |----------------------------|----------------------------------------------------------------------------|
    | <span data-ttu-id="59bc3-138">Östra USA</span><span class="sxs-lookup"><span data-stu-id="59bc3-138">East US</span></span>                    | `https://electronicinvoicing.eus-il301.gateway.prod.island.powerapps.com/` |
    | <span data-ttu-id="59bc3-139">Västra USA</span><span class="sxs-lookup"><span data-stu-id="59bc3-139">West US</span></span>                    | `https://electronicinvoicing.wus-il301.gateway.prod.island.powerapps.com/` |
    | <span data-ttu-id="59bc3-140">Norra EU</span><span class="sxs-lookup"><span data-stu-id="59bc3-140">North EU</span></span>                   | `https://electronicinvoicing.neu-il301.gateway.prod.island.powerapps.com/` |
    | <span data-ttu-id="59bc3-141">Västra EU</span><span class="sxs-lookup"><span data-stu-id="59bc3-141">West EU</span></span>                    | `https://electronicinvoicing.weu-il301.gateway.prod.island.powerapps.com/` |

4. <span data-ttu-id="59bc3-142">Kontrollera att fältet **Program-ID** är inställt på **0cdb527f-a8d1-4bf8-9436-b352c68682b2**.</span><span class="sxs-lookup"><span data-stu-id="59bc3-142">Verify that the **Application Id** field is set to **0cdb527f-a8d1-4bf8-9436-b352c68682b2**.</span></span> <span data-ttu-id="59bc3-143">Det här värdet är ett fast värde.</span><span class="sxs-lookup"><span data-stu-id="59bc3-143">This value is a fixed value.</span></span>
5. <span data-ttu-id="59bc3-144">I fältet **ID för LCS-miljö** anger du ID för ditt LCS-miljö.</span><span class="sxs-lookup"><span data-stu-id="59bc3-144">In the **LCS Environment Id** field, enter the ID of your LCS environment.</span></span>
6. <span data-ttu-id="59bc3-145">Markera **Spara** och stäng sedan sidan.</span><span class="sxs-lookup"><span data-stu-id="59bc3-145">Select **Save**, and then close the page.</span></span>

## <a name="create-key-vault-references"></a><span data-ttu-id="59bc3-146">Skapa en nyckelvalvsreferens</span><span class="sxs-lookup"><span data-stu-id="59bc3-146">Create Key Vault references</span></span>

1. <span data-ttu-id="59bc3-147">Logga in på RCS-kontot.</span><span class="sxs-lookup"><span data-stu-id="59bc3-147">Sign in to your RCS account.</span></span>
2. <span data-ttu-id="59bc3-148">I arbetsytan **globaliseringsfunktion** i avsnittet **Miljöer**, välj panelen **Elektroniska fakturor**.</span><span class="sxs-lookup"><span data-stu-id="59bc3-148">In the **Globalization feature** workspace, in the **Environment** section, select the **Electronic invoicing** tile.</span></span>
3. <span data-ttu-id="59bc3-149">På sidan **Miljökonfigurationer** väljer du i åtgärdsfönstret **Tjänstemiljö** och sedan **Parametrar för nyckelval**.</span><span class="sxs-lookup"><span data-stu-id="59bc3-149">On the **Environment setups** page, on the action Pane, select **Service environment**, and then select **Key Vault parameters**.</span></span>
4. <span data-ttu-id="59bc3-150">Välj **Ny** för att skapa en nyckelvalvsreferens.</span><span class="sxs-lookup"><span data-stu-id="59bc3-150">Select **New** to create a key vault reference.</span></span>
5. <span data-ttu-id="59bc3-151">I fältet **Namn** anger du namnet för nyckelvalvsreferens.</span><span class="sxs-lookup"><span data-stu-id="59bc3-151">In the **Name** field, enter the name of the key vault reference.</span></span> <span data-ttu-id="59bc3-152">Ange en beskrivning i fältet **beskrivning**.</span><span class="sxs-lookup"><span data-stu-id="59bc3-152">In the **Description** field, enter a description.</span></span>
6. <span data-ttu-id="59bc3-153">I fältet **URI för nyckelvalv** klistrar du in nyckelvalvshemlighet från Azure Key Vault.</span><span class="sxs-lookup"><span data-stu-id="59bc3-153">In the **Key Vault URI** field, paste the key vault secret from Azure Key Vault.</span></span> <span data-ttu-id="59bc3-154">Mer information finns i [Skapa ett Azure-lagringskonto och ett nyckelvalv](e-invoicing-create-azure-storage-account-key-vault.md).</span><span class="sxs-lookup"><span data-stu-id="59bc3-154">For more information, see [Create an Azure storage account and a key vault](e-invoicing-create-azure-storage-account-key-vault.md).</span></span>
7. <span data-ttu-id="59bc3-155">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="59bc3-155">Select **Save**.</span></span>

## <a name="create-storage-account-secret"></a><span data-ttu-id="59bc3-156">Skapa hemlighet för lagringskonto</span><span class="sxs-lookup"><span data-stu-id="59bc3-156">Create Storage account secret</span></span>

1. <span data-ttu-id="59bc3-157">På sidan **Miljökonfigurationer** väljer du i åtgärdsfönstret **Tjänstemiljö** > **Parametrar för nyckelval**.</span><span class="sxs-lookup"><span data-stu-id="59bc3-157">On the **Environment setups** page, on the Action Pane, select **Service environment** > **Key Vault parameters**.</span></span>
2. <span data-ttu-id="59bc3-158">Välj en **Nyckelvalvsreferens** och i avsnittet **Certifikat**, välj **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="59bc3-158">Select a **Key Vault reference** and in the **Certificates** section, select **Add**.</span></span>
3. <span data-ttu-id="59bc3-159">I fältet **Namn** anger du namnet för lagringskontots hemlighet.</span><span class="sxs-lookup"><span data-stu-id="59bc3-159">In the **Name** field, enter the name of the storage account secret.</span></span> <span data-ttu-id="59bc3-160">Mer information finns i [Skapa ett Azure-lagringskonto och ett nyckelvalv](e-invoicing-create-azure-storage-account-key-vault.md).</span><span class="sxs-lookup"><span data-stu-id="59bc3-160">For more information, see [Create an Azure storage account and a key vault](e-invoicing-create-azure-storage-account-key-vault.md).</span></span>
4. <span data-ttu-id="59bc3-161">Ange en beskrivning i fältet **beskrivning**.</span><span class="sxs-lookup"><span data-stu-id="59bc3-161">In the **Description** field, enter a description.</span></span>
5. <span data-ttu-id="59bc3-162">Välj **Typ** i fältet **Hemlighet**.</span><span class="sxs-lookup"><span data-stu-id="59bc3-162">In the **Type** field, select **Secret**.</span></span>
6. <span data-ttu-id="59bc3-163">Markera **Spara** och stäng sedan sidan.</span><span class="sxs-lookup"><span data-stu-id="59bc3-163">Select **Save**, and then close the page.</span></span>

## <a name="create-a-digital-certificate-secret"></a><span data-ttu-id="59bc3-164">Skapa en hemlighet för digitalt certifikat</span><span class="sxs-lookup"><span data-stu-id="59bc3-164">Create a digital certificate secret</span></span>

1. <span data-ttu-id="59bc3-165">På sidan **Miljökonfigurationer** väljer du i åtgärdsfönstret **Tjänstemiljö** och sedan **Parametrar för nyckelval**.</span><span class="sxs-lookup"><span data-stu-id="59bc3-165">On the **Environment setups** page, on the action Pane, select **Service environment** and then select **Key Vault parameters**.</span></span>
2. <span data-ttu-id="59bc3-166">Välj en **Nyckelvalvsreferens** och i avsnittet **Certifikat**, välj **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="59bc3-166">Select a **Key Vault reference** and then in the **Certificates** section, select **Add**.</span></span>
3. <span data-ttu-id="59bc3-167">I fältet **Namn** anger du namnet för hemlighet för digitalt certifikat.</span><span class="sxs-lookup"><span data-stu-id="59bc3-167">In the **Name** field, enter the name of the digital certificate secret.</span></span> <span data-ttu-id="59bc3-168">Mer information finns i [Skapa ett Azure-lagringskonto och ett nyckelvalv](e-invoicing-create-azure-storage-account-key-vault.md).</span><span class="sxs-lookup"><span data-stu-id="59bc3-168">For more information, see [Create an Azure storage account and a key vault](e-invoicing-create-azure-storage-account-key-vault.md).</span></span>
4. <span data-ttu-id="59bc3-169">Ange en beskrivning i fältet **beskrivning**.</span><span class="sxs-lookup"><span data-stu-id="59bc3-169">In the **Description** field, enter a description.</span></span>
5. <span data-ttu-id="59bc3-170">I fältet **Typ** väljer du **Certifikat**.</span><span class="sxs-lookup"><span data-stu-id="59bc3-170">In the **Type** field, select **Certificate**.</span></span>
6. <span data-ttu-id="59bc3-171">Markera **Spara** och stäng sedan sidan.</span><span class="sxs-lookup"><span data-stu-id="59bc3-171">Select **Save**, and then close the page.</span></span>

## <a name="create-a-service-environment"></a><span data-ttu-id="59bc3-172">Skapa en tjänstemiljö</span><span class="sxs-lookup"><span data-stu-id="59bc3-172">Create a service environment</span></span>

1. <span data-ttu-id="59bc3-173">Logga in på RCS-kontot.</span><span class="sxs-lookup"><span data-stu-id="59bc3-173">Sign in to your RCS account.</span></span>
2. <span data-ttu-id="59bc3-174">I arbetsytan **globaliseringsfunktion** i avsnittet **Miljöer**, välj panelen **Elektroniska fakturor**.</span><span class="sxs-lookup"><span data-stu-id="59bc3-174">In the **Globalization feature** workspace, in the **Environment** section, select the **Electronic invoicing** tile.</span></span>
3. <span data-ttu-id="59bc3-175">På sidan **Miljökonfigurationer** väljer du **Tjänstemiljö** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="59bc3-175">On the **Environment setups** page, on the Action Pane, select **Service environment**.</span></span>
4. <span data-ttu-id="59bc3-176">Välj **Ny** för att skapa en ny tjänstemiljö.</span><span class="sxs-lookup"><span data-stu-id="59bc3-176">Select **New** to create a new service environment.</span></span>
5. <span data-ttu-id="59bc3-177">I fältet **Namn** anger du namnet på miljön för e-fakturering.</span><span class="sxs-lookup"><span data-stu-id="59bc3-177">In the **Name** field, enter the name of the e-Invoicing environment.</span></span> <span data-ttu-id="59bc3-178">Ange en beskrivning i fältet **beskrivning**.</span><span class="sxs-lookup"><span data-stu-id="59bc3-178">In the **Description** field, enter a description.</span></span>
6. <span data-ttu-id="59bc3-179">I fältet **Lagringshemlighet för SAS-token** väljer du namnet på lagringskontots hemlighet som måste användas för att ge åtkomst till lagringskontot.</span><span class="sxs-lookup"><span data-stu-id="59bc3-179">In the **Storage SAS token secret** field, select the name of the storage account secret that must be used to authenticate access to the storage account.</span></span>
7. <span data-ttu-id="59bc3-180">I avsnittet **Användare** väljer du **Lägg till** om du vill lägga till en användare som är behörig att skicka in elektroniska fakturor via miljön samt även ansluta till lagringskontot.</span><span class="sxs-lookup"><span data-stu-id="59bc3-180">In the **Users** section, select **Add** to add a user who is allowed to submit electronic invoices through the environment and also connect to the storage account.</span></span>
8. <span data-ttu-id="59bc3-181">I fältet **Användar-ID** anger du användarens alias.</span><span class="sxs-lookup"><span data-stu-id="59bc3-181">In the **User ID** field, enter the alias of the user.</span></span> <span data-ttu-id="59bc3-182">I fältet **E-postadress** anger du användarens e-postadress.</span><span class="sxs-lookup"><span data-stu-id="59bc3-182">In the **Email** field, enter the user's email address.</span></span>
9. <span data-ttu-id="59bc3-183">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="59bc3-183">Select **Save**.</span></span>
10. <span data-ttu-id="59bc3-184">Om dina lands-/regionspecifika fakturor kräver en certifikatkedja för att kunna tillämpa digitala signaturer, väljer du **Parametrar för nyckelvalv** och sedan **Certifikatkedja** i åtgärdsfönstret och följer sedan dessa steg:</span><span class="sxs-lookup"><span data-stu-id="59bc3-184">If your country/region-specific invoices require a chain of certificates to apply digital signatures, on the Action pane, select **Key Vault parameters**, then select **Chain of certificates**, and follow these steps:</span></span>
    1. <span data-ttu-id="59bc3-185">Välj **Ny** för att skapa en certifikatkedja.</span><span class="sxs-lookup"><span data-stu-id="59bc3-185">Select **New** to create a chain of certificates.</span></span>
    2. <span data-ttu-id="59bc3-186">I fältet **Namn** anger du namnet på certifikatkedjan.</span><span class="sxs-lookup"><span data-stu-id="59bc3-186">In the **Name** field, enter the name of the chain of certificate.</span></span> <span data-ttu-id="59bc3-187">Ange en beskrivning i fältet **beskrivning**.</span><span class="sxs-lookup"><span data-stu-id="59bc3-187">In the **Description** field, enter a description.</span></span>
    3. <span data-ttu-id="59bc3-188">I avsnittet **Certifikat** väljer du **Lägg till** för att lägga till ett certifikat i kedjan.</span><span class="sxs-lookup"><span data-stu-id="59bc3-188">In the **Certificates** section, select **Add** to add a certificate to the chain.</span></span>
    4. <span data-ttu-id="59bc3-189">Använd knappen **Upp** eller **Ner** för att byta certifikatets position i kedjan.</span><span class="sxs-lookup"><span data-stu-id="59bc3-189">Use the **Up** or **Down** button to change the position of the certificate in the chain.</span></span>
    5. <span data-ttu-id="59bc3-190">Markera **Spara** och stäng sedan sidan.</span><span class="sxs-lookup"><span data-stu-id="59bc3-190">Select **Save**, and then close the page.</span></span>
    6. <span data-ttu-id="59bc3-191">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="59bc3-191">Close the page.</span></span>
11. <span data-ttu-id="59bc3-192">I åtgärdsfönstret på sidan **Tjänstemiljö** väljer du **Publicera** om du vill publicera miljön i molnet.</span><span class="sxs-lookup"><span data-stu-id="59bc3-192">On **Service environment** page, on the Action Pane, select **Publish** to publish the environment to the cloud.</span></span> <span data-ttu-id="59bc3-193">Värdet i fältet **Status** ändras till **Publicerad**.</span><span class="sxs-lookup"><span data-stu-id="59bc3-193">The value of the **Status** field is changed to **Published**.</span></span>

## <a name="create-a-connected-application"></a><span data-ttu-id="59bc3-194">Skapa ett anslutet program.</span><span class="sxs-lookup"><span data-stu-id="59bc3-194">Create a connected application</span></span>

1. <span data-ttu-id="59bc3-195">På sidan **Miljökonfigurationer** väljer du **Anslutna program** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="59bc3-195">On the **Environment setups** page, on the action Pane, select **Connected applications**.</span></span>
2. <span data-ttu-id="59bc3-196">Skapa ett anslutet program genom att välja **Ny**.</span><span class="sxs-lookup"><span data-stu-id="59bc3-196">Select **New** to create a connected application.</span></span>
3. <span data-ttu-id="59bc3-197">I fältet **Namn** anger du namnet på det program du vill ansluta.</span><span class="sxs-lookup"><span data-stu-id="59bc3-197">In the **Name** field, enter the name of the application to connect.</span></span>
4. <span data-ttu-id="59bc3-198">I fältet **Program** anger du URL:en för den Finance- och Supply Chain Management-miljö du vill ansluta.</span><span class="sxs-lookup"><span data-stu-id="59bc3-198">In the **Application** field, enter the URL of the Finance and Supply Chain Management environment to connect.</span></span>
4. <span data-ttu-id="59bc3-199">I fältet **Klientorganisation** anger du klientorganisationen för Finance and Supply Chain Management-miljön.</span><span class="sxs-lookup"><span data-stu-id="59bc3-199">In the **Tenant** field, enter the tenant of the Finance and Supply Chain Management environment.</span></span>
5. <span data-ttu-id="59bc3-200">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="59bc3-200">Select **Save**.</span></span>
6. <span data-ttu-id="59bc3-201">I åtgärdsfönstret väljer du **Kontrollera anslutning** om du vill testa anslutningen till miljön.</span><span class="sxs-lookup"><span data-stu-id="59bc3-201">On the Action Pane, select **Check connection** to test the connection with the environment.</span></span> <span data-ttu-id="59bc3-202">Stäng sedan sidan.</span><span class="sxs-lookup"><span data-stu-id="59bc3-202">Then close the page.</span></span>

## <a name="link-connected-applications-to-environments"></a><span data-ttu-id="59bc3-203">Koppla anslutna program till miljöer</span><span class="sxs-lookup"><span data-stu-id="59bc3-203">Link connected applications to environments</span></span>

1. <span data-ttu-id="59bc3-204">På sidan **Miljökonfigurationer** väljer du **Ny** om du vill tilldela ett anslutet program till en miljö.</span><span class="sxs-lookup"><span data-stu-id="59bc3-204">On the **Environment setups** page, select **New** to assign a connected application to an environment.</span></span>
2. <span data-ttu-id="59bc3-205">I fältet **Anslutet program** väljer du ett anslutet program.</span><span class="sxs-lookup"><span data-stu-id="59bc3-205">In the **Connected application** field, select a connected application.</span></span>
3. <span data-ttu-id="59bc3-206">I fältet **Tjänstemiljö** väljer du en tjänstemiljö.</span><span class="sxs-lookup"><span data-stu-id="59bc3-206">In the **Service environment** field, select a service environment.</span></span>
4. <span data-ttu-id="59bc3-207">Markera **Spara** och stäng sedan sidan.</span><span class="sxs-lookup"><span data-stu-id="59bc3-207">Select **Save**, and then close the page.</span></span>

## <a name="set-up-electronic-invoicing-integration-in-finance-and-supply-chain-management"></a><span data-ttu-id="59bc3-208">Ställa in integrering av elektronisk fakturering i Finance och Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="59bc3-208">Set up Electronic invoicing integration in Finance and Supply Chain Management</span></span>

### <a name="turn-on-the-electronic-invoicing-integration-feature"></a><span data-ttu-id="59bc3-209">Aktivera integrationsfunktionen för Elektronisk fakturering</span><span class="sxs-lookup"><span data-stu-id="59bc3-209">Turn on the Electronic invoicing integration feature</span></span>

1. <span data-ttu-id="59bc3-210">Logga in på din instans för Finance eller Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="59bc3-210">Sign in to your Finance or Supply Chain Management instance.</span></span>
2. <span data-ttu-id="59bc3-211">I arbetsytan **Funktionshantering** söker du efter den nya funktionen **Integrering av för elektronisk fakturering**.</span><span class="sxs-lookup"><span data-stu-id="59bc3-211">In the **Feature management** workspace, search for the **Electronic invoicing integration** feature.</span></span> <span data-ttu-id="59bc3-212">Om den här funktionen inte visas på sidan väljer du **Sök efter uppdateringar**.</span><span class="sxs-lookup"><span data-stu-id="59bc3-212">If this feature doesn't appear on the page, select **Check for updates**.</span></span>
3. <span data-ttu-id="59bc3-213">Välj funktionen och välj sedan **aktivera nu**.</span><span class="sxs-lookup"><span data-stu-id="59bc3-213">Select the feature, and then select **Enable now**.</span></span>

### <a name="set-up-the-service-endpoint-url"></a><span data-ttu-id="59bc3-214">Ställ in URL för tjänstslutpunkt</span><span class="sxs-lookup"><span data-stu-id="59bc3-214">Set up the service endpoint URL</span></span>

1. <span data-ttu-id="59bc3-215">Gå till **organisationsadministration \> inställning \> parametrar för elektroniska dokument**.</span><span class="sxs-lookup"><span data-stu-id="59bc3-215">Go to **Organization administration \> Setup \> Electronic document parameters**.</span></span>
2. <span data-ttu-id="59bc3-216">På fliken **Överföringstjänst**, i fältet **URL för tjänsteslutpunkt** anger du relevant tjänsteslutpunkt för ditt Azure-område enligt följande tabell.</span><span class="sxs-lookup"><span data-stu-id="59bc3-216">On the **Submission service** tab, in the **Service endpoint URL** field, enter the appropriate service endpoint for your Azure geography, as shown in the following table.</span></span>

    | <span data-ttu-id="59bc3-217">Azure-område för datacenter</span><span class="sxs-lookup"><span data-stu-id="59bc3-217">Datacenter Azure geography</span></span> | <span data-ttu-id="59bc3-218">URL för tjänstslutpunkt</span><span class="sxs-lookup"><span data-stu-id="59bc3-218">Service endpoint URL</span></span>                                                       |
    |----------------------------|----------------------------------------------------------------------------|
    | <span data-ttu-id="59bc3-219">Östra USA</span><span class="sxs-lookup"><span data-stu-id="59bc3-219">East US</span></span>                    | `https://electronicinvoicing.eus-il301.gateway.prod.island.powerapps.com/` |
    | <span data-ttu-id="59bc3-220">Västra USA</span><span class="sxs-lookup"><span data-stu-id="59bc3-220">West US</span></span>                    | `https://electronicinvoicing.wus-il301.gateway.prod.island.powerapps.com/` |
    | <span data-ttu-id="59bc3-221">Norra EU</span><span class="sxs-lookup"><span data-stu-id="59bc3-221">North EU</span></span>                   | `https://electronicinvoicing.neu-il301.gateway.prod.island.powerapps.com/` |
    | <span data-ttu-id="59bc3-222">Västra EU</span><span class="sxs-lookup"><span data-stu-id="59bc3-222">West EU</span></span>                    | `https://electronicinvoicing.weu-il301.gateway.prod.island.powerapps.com/` |

3. <span data-ttu-id="59bc3-223">I fältet **Miljö** anger du namnet på miljön för tjänstemiljö publicerad i Elektronisk fakturering.</span><span class="sxs-lookup"><span data-stu-id="59bc3-223">In the **Environment** field, enter the name of the service environment published in Electronic invoicing.</span></span>
4. <span data-ttu-id="59bc3-224">Markera **Spara** och stäng sedan sidan.</span><span class="sxs-lookup"><span data-stu-id="59bc3-224">Select **Save**, and then close the page.</span></span>

### <a name="enable-flighting-keys"></a><span data-ttu-id="59bc3-225">Aktivera flygnycklar</span><span class="sxs-lookup"><span data-stu-id="59bc3-225">Enable Flighting keys</span></span>

<span data-ttu-id="59bc3-226">Aktivera flygnycklar för Microsoft Dynamics 365 Finance eller Microsoft Dynamics 365 Supply Chain Management-versioner 10.0.17 eller tidigare.</span><span class="sxs-lookup"><span data-stu-id="59bc3-226">Enable Flight keys for  Microsoft Dynamics 365 Finance or  Microsoft Dynamics 365 Supply Chain Management versions 10.0.17 or earlier.</span></span> 
1. <span data-ttu-id="59bc3-227">Kör följande SQL-kommando:</span><span class="sxs-lookup"><span data-stu-id="59bc3-227">Execute the following SQL command:</span></span>

    <span data-ttu-id="59bc3-228">INFOGA I SYSFLIGHTING (FLIGHTNAME, ENABLED) VÄRDEN ('BusinessDocumentSubmissionServiceEnabled', 1)</span><span class="sxs-lookup"><span data-stu-id="59bc3-228">INSERT INTO SYSFLIGHTING (FLIGHTNAME, ENABLED) VALUES ('BusinessDocumentSubmissionServiceEnabled', 1)</span></span>
    
    <span data-ttu-id="59bc3-229">INFOGA I SYSFLIGHTING (FLIGHTNAME, ENABLED) VÄRDEN ('ElectronicInvoicingServiceIntegrationFeature', 1)</span><span class="sxs-lookup"><span data-stu-id="59bc3-229">INSERT INTO SYSFLIGHTING (FLIGHTNAME, ENABLED) VALUES ('ElectronicInvoicingServiceIntegrationFeature', 1)</span></span>

2. <span data-ttu-id="59bc3-230">Utför ett IISreset-kommando för alla AOS:er.</span><span class="sxs-lookup"><span data-stu-id="59bc3-230">Perform an IISreset command for all AOS's.</span></span>

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
