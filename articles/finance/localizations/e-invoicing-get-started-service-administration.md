---
title: Kom i gång med tjänsteadministreringen för tillägget Elektronisk fakturering
description: I det här avsnittet beskrivs hur du kommer igång med tillägget Elektronisk fakturering.
author: gionoder
manager: AnnBe
ms.date: 03/12/2021
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
ms.openlocfilehash: 05b00380cec7511adad2467d3f252799a4aaee5c
ms.sourcegitcommit: 543772ee97efe215cf6f2ec6e092cc1568919f20
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/13/2021
ms.locfileid: "5592536"
---
# <a name="get-started-with-electronic-invoicing-add-on-service-administration"></a><span data-ttu-id="18a64-103">Kom i gång med tjänsteadministreringen för tillägget Elektronisk fakturering</span><span class="sxs-lookup"><span data-stu-id="18a64-103">Get started with Electronic invoicing add-on service administration</span></span>

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

## <a name="prerequisites"></a><span data-ttu-id="18a64-104">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="18a64-104">Prerequisites</span></span>

<span data-ttu-id="18a64-105">Innan du kan slutföra procedurerna i detta ämne måste följande förutsättningar finnas på plats:</span><span class="sxs-lookup"><span data-stu-id="18a64-105">Before you complete the procedures in this topic, the following prerequisites must be in place:</span></span>

- <span data-ttu-id="18a64-106">Du måste ha tillgång till ditt Microsoft Dynamics Lifecycle Services-konto (LCS).</span><span class="sxs-lookup"><span data-stu-id="18a64-106">You must have access to your Microsoft Dynamics Lifecycle Services (LCS) account.</span></span>
- <span data-ttu-id="18a64-107">Du måste ha ett LCS-projekt som innehåller version 10.0.17 eller senare av Microsoft Dynamics 365 Finance och Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="18a64-107">You must have an LCS project that includes version 10.0.17 or later of Microsoft Dynamics 365 Finance and Dynamics 365 Supply Chain Management.</span></span> <span data-ttu-id="18a64-108">Dessa program måste dessutom distribueras i något av följande Azure-områden:</span><span class="sxs-lookup"><span data-stu-id="18a64-108">Additionally, these apps must be deployed in one of the following Azure geographies:</span></span>

    - <span data-ttu-id="18a64-109">Östra USA</span><span class="sxs-lookup"><span data-stu-id="18a64-109">East US</span></span>
    - <span data-ttu-id="18a64-110">Västra USA</span><span class="sxs-lookup"><span data-stu-id="18a64-110">West US</span></span>
    - <span data-ttu-id="18a64-111">Norra EU</span><span class="sxs-lookup"><span data-stu-id="18a64-111">North EU</span></span>
    - <span data-ttu-id="18a64-112">Västra EU</span><span class="sxs-lookup"><span data-stu-id="18a64-112">West EU</span></span>

- <span data-ttu-id="18a64-113">Du måste ha tillgång till ditt Dynamics 365 Regulatory Configuration Services-konto (RCS).</span><span class="sxs-lookup"><span data-stu-id="18a64-113">You must have access to your Dynamics 365 Regulatory Configuration Services (RCS) account.</span></span>
- <span data-ttu-id="18a64-114">Du måste aktivera globaliseringsfunktionen för ditt RCS-konto i funktionshanteringen.</span><span class="sxs-lookup"><span data-stu-id="18a64-114">You must activate the Globalization feature for your RCS account in Feature management.</span></span> <span data-ttu-id="18a64-115">Mer information finns i [Regulatory Configuration Services (RCS) – globaliseringsfunktioner](rcs-globalization-feature.md).</span><span class="sxs-lookup"><span data-stu-id="18a64-115">For more information, see [Regulatory Configuration Services (RCS) - Globalization features](rcs-globalization-feature.md).</span></span>
- <span data-ttu-id="18a64-116">Du måste skapa ett nyckelvalv och ett lagringskonto i Azure.</span><span class="sxs-lookup"><span data-stu-id="18a64-116">You must create a key vault and a storage account in Azure.</span></span> <span data-ttu-id="18a64-117">Mer information finns i [Skapa ett Azure-lagringskonto och ett nyckelvalv](e-invoicing-create-azure-storage-account-key-vault.md).</span><span class="sxs-lookup"><span data-stu-id="18a64-117">For more information, see [Create an Azure storage account and a key vault](e-invoicing-create-azure-storage-account-key-vault.md).</span></span>

## <a name="install-the-add-on-for-microservices-in-lifecycle-services"></a><span data-ttu-id="18a64-118">Installera tillägget för mikrotjänster i Lifecycle Services</span><span class="sxs-lookup"><span data-stu-id="18a64-118">Install the add-on for microservices in Lifecycle Services</span></span>

1. <span data-ttu-id="18a64-119">Logga in på LCS-kontot.</span><span class="sxs-lookup"><span data-stu-id="18a64-119">Sign in to your LCS account.</span></span>
2. <span data-ttu-id="18a64-120">Välj panelen **Hantera förhandsgranskning**.</span><span class="sxs-lookup"><span data-stu-id="18a64-120">Select the **Preview feature management** tile.</span></span>
3. <span data-ttu-id="18a64-121">I avsnittet **Funktioner i allmänt tillgänglig förhandsversion** väljer du **Tjänst för e-fakturering**.</span><span class="sxs-lookup"><span data-stu-id="18a64-121">In the **Public Preview Features** section, select **e-Invoicing service**.</span></span>
4. <span data-ttu-id="18a64-122">Se till att alternativet **Förhandsgranskning aktiverad** är inställt på **Ja**.</span><span class="sxs-lookup"><span data-stu-id="18a64-122">Make sure that the **Preview feature enabled** option is set to **Yes**.</span></span>
5. <span data-ttu-id="18a64-123">Välj ditt LCS-distributionsprojekt på LCS-instrumentpanelen.</span><span class="sxs-lookup"><span data-stu-id="18a64-123">On your LCS dashboard, select your LCS deployment project.</span></span> <span data-ttu-id="18a64-124">LCS-projektet måste köras.</span><span class="sxs-lookup"><span data-stu-id="18a64-124">The LCS project must be running.</span></span>
7. <span data-ttu-id="18a64-125">På fliken **Miljötillägg** välj **Installera ett nytt tillägg**.</span><span class="sxs-lookup"><span data-stu-id="18a64-125">On the **Environment add-ins** tab, select **Install a new add-in**.</span></span>
8. <span data-ttu-id="18a64-126">Välj **e-faktureringstjänster** och i fältet **AAD-program-ID** ange **091c98b0-a1c9-4b02-b62c-7753395ccabe**.</span><span class="sxs-lookup"><span data-stu-id="18a64-126">Select **e-invoicing Services** and in the **AAD application ID** field, enter **091c98b0-a1c9-4b02-b62c-7753395ccabe**.</span></span> <span data-ttu-id="18a64-127">Detta är ett fast värde.</span><span class="sxs-lookup"><span data-stu-id="18a64-127">This is a fixed value.</span></span>
10. <span data-ttu-id="18a64-128">I fältet **AAD innehavar-ID** anger du innehavar-ID för ditt Azure abonnemangskonto.</span><span class="sxs-lookup"><span data-stu-id="18a64-128">In the **AAD tenant ID** field, enter the tenant ID of your Azure subscription account.</span></span>
11. <span data-ttu-id="18a64-129">Granska villkoren och markera sedan kryssrutan.</span><span class="sxs-lookup"><span data-stu-id="18a64-129">Review the terms and conditions, and then select the check box.</span></span>
12. <span data-ttu-id="18a64-130">Välj **Installera**.</span><span class="sxs-lookup"><span data-stu-id="18a64-130">Select **Install**.</span></span>


## <a name="set-up-the-parameters-for-rcs-integration-with-the-electronic-invoicing-add-on"></a><span data-ttu-id="18a64-131">Ställ in parametrarna för RCS-integrationen med tillägget Elektronisk fakturering</span><span class="sxs-lookup"><span data-stu-id="18a64-131">Set up the parameters for RCS integration with the Electronic invoicing add-on</span></span>

1. <span data-ttu-id="18a64-132">Logga in på RCS-kontot.</span><span class="sxs-lookup"><span data-stu-id="18a64-132">Sign in to your RCS account.</span></span>
2. <span data-ttu-id="18a64-133">I arbetsytan **elektronisk rapportering** i avsnittet **Relaterade länkar** väljer du **parametrar för elektronisk rapportering**.</span><span class="sxs-lookup"><span data-stu-id="18a64-133">In the **Electronic reporting** workspace, in the **Related links** section, select **Electronic reporting parameters**.</span></span>
3. <span data-ttu-id="18a64-134">På fliken **Tjänst för e-fakturering**, under fliken **URI för tjänstens slutpunkt** anger du ungefärlig tjänsteslutpunkt för ditt Azure-område enligt följande tabell.</span><span class="sxs-lookup"><span data-stu-id="18a64-134">On the **e-Invoicing service** tab, in the **Service endpoint URI** field, enter the appropriate service endpoint for your Azure geography, as shown in the following table.</span></span>

    | <span data-ttu-id="18a64-135">Azure-område för datacenter</span><span class="sxs-lookup"><span data-stu-id="18a64-135">Datacenter Azure geography</span></span> | <span data-ttu-id="18a64-136">URI för tjänstslutpunkt</span><span class="sxs-lookup"><span data-stu-id="18a64-136">Service endpoint URI</span></span>                                                       |
    |----------------------------|----------------------------------------------------------------------------|
    | <span data-ttu-id="18a64-137">Östra USA</span><span class="sxs-lookup"><span data-stu-id="18a64-137">East US</span></span>                    | `https://electronicinvoicing.eus-il301.gateway.prod.island.powerapps.com/` |
    | <span data-ttu-id="18a64-138">Västra USA</span><span class="sxs-lookup"><span data-stu-id="18a64-138">West US</span></span>                    | `https://electronicinvoicing.wus-il301.gateway.prod.island.powerapps.com/` |
    | <span data-ttu-id="18a64-139">Norra EU</span><span class="sxs-lookup"><span data-stu-id="18a64-139">North EU</span></span>                   | `https://electronicinvoicing.neu-il301.gateway.prod.island.powerapps.com/` |
    | <span data-ttu-id="18a64-140">Västra EU</span><span class="sxs-lookup"><span data-stu-id="18a64-140">West EU</span></span>                    | `https://electronicinvoicing.weu-il301.gateway.prod.island.powerapps.com/` |

4. <span data-ttu-id="18a64-141">Kontrollera att fältet **Program-ID** är inställt på **0cdb527f-a8d1-4bf8-9436-b352c68682b2**.</span><span class="sxs-lookup"><span data-stu-id="18a64-141">Verify that the **Application Id** field is set to **0cdb527f-a8d1-4bf8-9436-b352c68682b2**.</span></span> <span data-ttu-id="18a64-142">Det här värdet är ett fast värde.</span><span class="sxs-lookup"><span data-stu-id="18a64-142">This value is a fixed value.</span></span>
5. <span data-ttu-id="18a64-143">I fältet **ID för LCS-miljö** anger du ID för ditt LCS-abonnemangskonto.</span><span class="sxs-lookup"><span data-stu-id="18a64-143">In the **LCS Environment Id** field, enter the ID of your LCS subscription account.</span></span>
6. <span data-ttu-id="18a64-144">Markera **Spara** och stäng sedan sidan.</span><span class="sxs-lookup"><span data-stu-id="18a64-144">Select **Save**, and then close the page.</span></span>

## <a name="create-key-vault-secret"></a><span data-ttu-id="18a64-145">Skapa nyckelvalvshemlighet</span><span class="sxs-lookup"><span data-stu-id="18a64-145">Create Key Vault secret</span></span>

1. <span data-ttu-id="18a64-146">Logga in på RCS-kontot.</span><span class="sxs-lookup"><span data-stu-id="18a64-146">Sign in to your RCS account.</span></span>
2. <span data-ttu-id="18a64-147">I arbetsytan **globaliseringsfunktion** i avsnittet **Miljöer**, välj panelen **Tillägg för elektroniska fakturor**.</span><span class="sxs-lookup"><span data-stu-id="18a64-147">In the **Globalization feature** workspace, in the **Environment** section, select the **Electronic invoicing add-on** tile.</span></span>
3. <span data-ttu-id="18a64-148">På sidan **Miljökonfigurationer** väljer du i åtgärdsfönstret **Tjänstemiljö** och sedan **Parametrar för nyckelval**.</span><span class="sxs-lookup"><span data-stu-id="18a64-148">On the **Environment setups** page, on the action Pane, select **Service environment**, and then select **Key Vault parameters**.</span></span>
4. <span data-ttu-id="18a64-149">Välj **Ny** för att skapa en nyckelvalvshemlighet.</span><span class="sxs-lookup"><span data-stu-id="18a64-149">Select **New** to create a key vault secret.</span></span>
5. <span data-ttu-id="18a64-150">I fältet **Namn** anger du namnet för nyckelvalvshemligheten.</span><span class="sxs-lookup"><span data-stu-id="18a64-150">In the **Name** field, enter the name of the key vault secret.</span></span> <span data-ttu-id="18a64-151">Ange en beskrivning i fältet **beskrivning**.</span><span class="sxs-lookup"><span data-stu-id="18a64-151">In the **Description** field, enter a description.</span></span>
6. <span data-ttu-id="18a64-152">I fältet **URI för nyckelvalv** klistrar du in hemligheten från Azure Key Vault.</span><span class="sxs-lookup"><span data-stu-id="18a64-152">In the **Key Vault URI** field, paste the secret from Azure Key Vault.</span></span>
7. <span data-ttu-id="18a64-153">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="18a64-153">Select **Save**.</span></span>

## <a name="create-storage-account-secret"></a><span data-ttu-id="18a64-154">Skapa hemlighet för lagringskonto</span><span class="sxs-lookup"><span data-stu-id="18a64-154">Create Storage account secret</span></span>

1. <span data-ttu-id="18a64-155">Gå till **Systemadministration** > **Inställningar** > **Key Vault-parametrar** och välj en Key Vault-hemlighet.</span><span class="sxs-lookup"><span data-stu-id="18a64-155">Go to **System administration** > **Setup** > **Key Vault parameters**, and select a Key vault secret.</span></span>
2. <span data-ttu-id="18a64-156">I avsnittet **Certifikat** välj **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="18a64-156">In the **Certificates** section, select **Add**.</span></span>
3. <span data-ttu-id="18a64-157">I fältet **Namn**, ange namnet på lagringskontohemligheten och i fältet **Beskrivning**, ange en beskrivning.</span><span class="sxs-lookup"><span data-stu-id="18a64-157">In the **Name** field, enter the name of the storage account secret and in the **Description** field, enter a description.</span></span>
4. <span data-ttu-id="18a64-158">I fältet **Typ** väljer du **Certifikat**.</span><span class="sxs-lookup"><span data-stu-id="18a64-158">In the **Type** field, select **Certificate**.</span></span>
5. <span data-ttu-id="18a64-159">Markera **Spara** och stäng sedan sidan.</span><span class="sxs-lookup"><span data-stu-id="18a64-159">Select **Save**, and then close the page.</span></span>

## <a name="create-a-digital-certificate-secret"></a><span data-ttu-id="18a64-160">Skapa en hemlighet för digitalt certifikat</span><span class="sxs-lookup"><span data-stu-id="18a64-160">Create a digital certificate secret</span></span>

1. <span data-ttu-id="18a64-161">Gå till **Systemadministration** > **Inställningar** > **Key Vault-parametrar** och välj en Key Vault-hemlighet.</span><span class="sxs-lookup"><span data-stu-id="18a64-161">Go to **System administration** > **Setup** > **Key Vault parameters**, and select a Key vault secret.</span></span>
2. <span data-ttu-id="18a64-162">I avsnittet **Certifikat** välj **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="18a64-162">In the **Certificates** section, select **Add**.</span></span>
3. <span data-ttu-id="18a64-163">I fältet **Namn**, ange namnet på hemlighet för digitalt certifikat och i fältet **Beskrivning**, ange en beskrivning.</span><span class="sxs-lookup"><span data-stu-id="18a64-163">In the **Name** field, enter the name of the digital certificate secret and in the **Description** field, enter a description.</span></span>
4. <span data-ttu-id="18a64-164">I fältet **Typ** väljer du **Certifikat**.</span><span class="sxs-lookup"><span data-stu-id="18a64-164">In the **Type** field, select **Certificate**.</span></span>
5. <span data-ttu-id="18a64-165">Markera **Spara** och stäng sedan sidan.</span><span class="sxs-lookup"><span data-stu-id="18a64-165">Select **Save**, and then close the page.</span></span>

## <a name="create-an-electronic-invoicing-add-on-environment"></a><span data-ttu-id="18a64-166">Skapa en miljö för Elektronisk fakturering</span><span class="sxs-lookup"><span data-stu-id="18a64-166">Create an Electronic invoicing add-on environment</span></span>

1. <span data-ttu-id="18a64-167">Logga in på RCS-kontot.</span><span class="sxs-lookup"><span data-stu-id="18a64-167">Sign in to your RCS account.</span></span>
2. <span data-ttu-id="18a64-168">I arbetsytan **globaliseringsfunktion** i avsnittet **Miljöer**, välj panelen **Tillägg för elektroniska fakturor**.</span><span class="sxs-lookup"><span data-stu-id="18a64-168">In the **Globalization feature** workspace, in the **Environment** section, select the **Electronic invoicing add-on** tile.</span></span>

## <a name="create-a-service-environment"></a><span data-ttu-id="18a64-169">Skapa en tjänstemiljö</span><span class="sxs-lookup"><span data-stu-id="18a64-169">Create a service environment</span></span>

1. <span data-ttu-id="18a64-170">På sidan **Miljökonfigurationer** väljer du **Tjänstemiljö** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="18a64-170">On the **Environment setups** page, on the Action Pane, select **Service environment**.</span></span>
2. <span data-ttu-id="18a64-171">Välj **Ny** för att skapa en ny tjänstemiljö.</span><span class="sxs-lookup"><span data-stu-id="18a64-171">Select **New** to create a new service environment.</span></span>
3. <span data-ttu-id="18a64-172">I fältet **Namn** anger du namnet på miljön för e-fakturering.</span><span class="sxs-lookup"><span data-stu-id="18a64-172">In the **Name** field, enter the name of the e-Invoicing environment.</span></span> <span data-ttu-id="18a64-173">Ange en beskrivning i fältet **beskrivning**.</span><span class="sxs-lookup"><span data-stu-id="18a64-173">In the **Description** field, enter a description.</span></span>
4. <span data-ttu-id="18a64-174">I fältet **Lagringshemlighet för SAS-token** väljer du namnet på lagringskontots hemlighet som måste användas för att ge åtkomst till lagringskontot.</span><span class="sxs-lookup"><span data-stu-id="18a64-174">In the **Storage SAS token secret** field, select the name of the storage account secret that must be used to authenticate access to the storage account.</span></span>
5. <span data-ttu-id="18a64-175">I avsnittet **Användare** väljer du **Lägg till** om du vill lägga till en användare som är behörig att skicka in elektroniska fakturor via miljön samt även ansluta till lagringskontot.</span><span class="sxs-lookup"><span data-stu-id="18a64-175">In the **Users** section, select **Add** to add a user who is allowed to submit electronic invoices through the environment and also connect to the storage account.</span></span>
6. <span data-ttu-id="18a64-176">I fältet **Användar-ID** anger du användarens alias.</span><span class="sxs-lookup"><span data-stu-id="18a64-176">In the **User ID** field, enter the alias of the user.</span></span> <span data-ttu-id="18a64-177">I fältet **E-postadress** anger du användarens e-postadress.</span><span class="sxs-lookup"><span data-stu-id="18a64-177">In the **Email** field, enter the user's email address.</span></span>
7. <span data-ttu-id="18a64-178">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="18a64-178">Select **Save**.</span></span>
8. <span data-ttu-id="18a64-179">Om dina lands-/regionspecifika fakturor kräver en certifikatkedja för att kunna tillämpa digitala signaturer, väljer du **Parametrar för nyckelvalv** och sedan **Certifikatkedja** i åtgärdsfönstret och följer sedan dessa steg:</span><span class="sxs-lookup"><span data-stu-id="18a64-179">If your country/region-specific invoices require a chain of certificates to apply digital signatures, on the Action pane, select **Key Vault parameters**, then select **Chain of certificates**, and follow these steps:</span></span>

    1. <span data-ttu-id="18a64-180">Välj **Ny** för att skapa en certifikatkedja.</span><span class="sxs-lookup"><span data-stu-id="18a64-180">Select **New** to create a chain of certificates.</span></span>
    2. <span data-ttu-id="18a64-181">I fältet **Namn** anger du namnet på certifikatkedjan.</span><span class="sxs-lookup"><span data-stu-id="18a64-181">In the **Name** field, enter the name of the chain of certificate.</span></span> <span data-ttu-id="18a64-182">Ange en beskrivning i fältet **beskrivning**.</span><span class="sxs-lookup"><span data-stu-id="18a64-182">In the **Description** field, enter a description.</span></span>
    3. <span data-ttu-id="18a64-183">I avsnittet **Certifikat** väljer du **Lägg till** för att lägga till ett certifikat i kedjan.</span><span class="sxs-lookup"><span data-stu-id="18a64-183">In the **Certificates** section, select **Add** to add a certificate to the chain.</span></span>
    4. <span data-ttu-id="18a64-184">Använd knappen **Upp** eller **Ner** för att byta certifikatets position i kedjan.</span><span class="sxs-lookup"><span data-stu-id="18a64-184">Use the **Up** or **Down** button to change the position of the certificate in the chain.</span></span>
    5. <span data-ttu-id="18a64-185">Markera **Spara** och stäng sedan sidan.</span><span class="sxs-lookup"><span data-stu-id="18a64-185">Select **Save**, and then close the page.</span></span>
    6. <span data-ttu-id="18a64-186">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="18a64-186">Close the page.</span></span>
9. <span data-ttu-id="18a64-187">I åtgärdsfönstret på sidan **Tjänstemiljö** väljer du **Publicera** om du vill publicera miljön i molnet.</span><span class="sxs-lookup"><span data-stu-id="18a64-187">On **Service environment** page, on the Action Pane, select **Publish** to publish the environment to the cloud.</span></span> <span data-ttu-id="18a64-188">Värdet i fältet **Status** ändras till **Publicerad**.</span><span class="sxs-lookup"><span data-stu-id="18a64-188">The value of the **Status** field is changed to **Published**.</span></span>

## <a name="create-a-connected-application"></a><span data-ttu-id="18a64-189">Skapa ett anslutet program.</span><span class="sxs-lookup"><span data-stu-id="18a64-189">Create a connected application</span></span>

1. <span data-ttu-id="18a64-190">På sidan **Miljökonfigurationer** väljer du **Anslutna program** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="18a64-190">On the **Environment setups** page, on the action Pane, select **Connected applications**.</span></span>
2. <span data-ttu-id="18a64-191">Skapa ett anslutet program genom att välja **Ny**.</span><span class="sxs-lookup"><span data-stu-id="18a64-191">Select **New** to create a connected application.</span></span>
3. <span data-ttu-id="18a64-192">I fältet **Namn** anger du namnet på det program du vill ansluta.</span><span class="sxs-lookup"><span data-stu-id="18a64-192">In the **Name** field, enter the name of the application to connect.</span></span>
4. <span data-ttu-id="18a64-193">I fältet **Program** anger du URL:en för den Finance- och Supply Chain Management-miljö du vill ansluta.</span><span class="sxs-lookup"><span data-stu-id="18a64-193">In the **Application** field, enter the URL of the Finance and Supply Chain Management environment to connect.</span></span>
4. <span data-ttu-id="18a64-194">I fältet **Klientorganisation** anger du klientorganisationen för Finance and Supply Chain Management-miljön.</span><span class="sxs-lookup"><span data-stu-id="18a64-194">In the **Tenant** field, enter the tenant of the Finance and Supply Chain Management environment.</span></span>
5. <span data-ttu-id="18a64-195">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="18a64-195">Select **Save**.</span></span>
6. <span data-ttu-id="18a64-196">I åtgärdsfönstret väljer du **Kontrollera anslutning** om du vill testa anslutningen till miljön.</span><span class="sxs-lookup"><span data-stu-id="18a64-196">On the Action Pane, select **Check connection** to test the connection with the environment.</span></span> <span data-ttu-id="18a64-197">Stäng sedan sidan.</span><span class="sxs-lookup"><span data-stu-id="18a64-197">Then close the page.</span></span>

## <a name="link-connected-applications-to-environments"></a><span data-ttu-id="18a64-198">Koppla anslutna program till miljöer</span><span class="sxs-lookup"><span data-stu-id="18a64-198">Link connected applications to environments</span></span>

1. <span data-ttu-id="18a64-199">På sidan **Miljökonfigurationer** väljer du **Ny** om du vill tilldela ett anslutet program till en miljö.</span><span class="sxs-lookup"><span data-stu-id="18a64-199">On the **Environment setups** page, select **New** to assign a connected application to an environment.</span></span>
2. <span data-ttu-id="18a64-200">I fältet **Anslutet program** väljer du ett anslutet program.</span><span class="sxs-lookup"><span data-stu-id="18a64-200">In the **Connected application** field, select a connected application.</span></span>
3. <span data-ttu-id="18a64-201">I fältet **Tjänstemiljö** väljer du en tjänstemiljö.</span><span class="sxs-lookup"><span data-stu-id="18a64-201">In the **Service environment** field, select a service environment.</span></span>
4. <span data-ttu-id="18a64-202">Markera **Spara** och stäng sedan sidan.</span><span class="sxs-lookup"><span data-stu-id="18a64-202">Select **Save**, and then close the page.</span></span>

## <a name="set-up-the-electronic-invoicing-add-on-integration-in-finance-and-supply-chain-management"></a><span data-ttu-id="18a64-203">Ställa in integrering av tillägget Elektronisk fakturering i Finance och Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="18a64-203">Set up the Electronic invoicing add-on integration in Finance and Supply Chain Management</span></span>

### <a name="turn-on-the-electronic-invoicing-add-on-integration-feature"></a><span data-ttu-id="18a64-204">Aktivera integrationsfunktionen för tillägget Elektronisk fakturering</span><span class="sxs-lookup"><span data-stu-id="18a64-204">Turn on the Electronic invoicing add-on integration feature</span></span>

1. <span data-ttu-id="18a64-205">Logga in på din instans för Finance eller Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="18a64-205">Sign in to your Finance or Supply Chain Management instance.</span></span>
2. <span data-ttu-id="18a64-206">I arbetsytan **Funktionshantering** söker du efter den nya funktionen **Integrering av tillägg för elektronisk fakturering**.</span><span class="sxs-lookup"><span data-stu-id="18a64-206">In the **Feature management** workspace, search for the **Electronic invoicing add-on integration** feature.</span></span> <span data-ttu-id="18a64-207">Om den här funktionen inte visas på sidan väljer du **Sök efter uppdateringar**.</span><span class="sxs-lookup"><span data-stu-id="18a64-207">If this feature doesn't appear on the page, select **Check for updates**.</span></span>
3. <span data-ttu-id="18a64-208">Välj funktionen och välj sedan **aktivera nu**.</span><span class="sxs-lookup"><span data-stu-id="18a64-208">Select the feature, and then select **Enable now**.</span></span>

### <a name="set-up-the-service-endpoint-url"></a><span data-ttu-id="18a64-209">Ställ in URL för tjänstslutpunkt</span><span class="sxs-lookup"><span data-stu-id="18a64-209">Set up the service endpoint URL</span></span>

1. <span data-ttu-id="18a64-210">Gå till **organisationsadministration \> inställning \> parametrar för elektroniska dokument**.</span><span class="sxs-lookup"><span data-stu-id="18a64-210">Go to **Organization administration \> Setup \> Electronic document parameters**.</span></span>
2. <span data-ttu-id="18a64-211">På fliken **Överföringstjänst**, i fältet **URL för tjänsteslutpunkt** anger du relevant tjänsteslutpunkt för ditt Azure-område enligt följande tabell.</span><span class="sxs-lookup"><span data-stu-id="18a64-211">On the **Submission service** tab, in the **Service endpoint URL** field, enter the appropriate service endpoint for your Azure geography, as shown in the following table.</span></span>

    | <span data-ttu-id="18a64-212">Azure-område för datacenter</span><span class="sxs-lookup"><span data-stu-id="18a64-212">Datacenter Azure geography</span></span> | <span data-ttu-id="18a64-213">URL för tjänstslutpunkt</span><span class="sxs-lookup"><span data-stu-id="18a64-213">Service endpoint URL</span></span>                                                       |
    |----------------------------|----------------------------------------------------------------------------|
    | <span data-ttu-id="18a64-214">Östra USA</span><span class="sxs-lookup"><span data-stu-id="18a64-214">East US</span></span>                    | `https://electronicinvoicing.eus-il301.gateway.prod.island.powerapps.com/` |
    | <span data-ttu-id="18a64-215">Västra USA</span><span class="sxs-lookup"><span data-stu-id="18a64-215">West US</span></span>                    | `https://electronicinvoicing.wus-il301.gateway.prod.island.powerapps.com/` |
    | <span data-ttu-id="18a64-216">Norra EU</span><span class="sxs-lookup"><span data-stu-id="18a64-216">North EU</span></span>                   | `https://electronicinvoicing.neu-il301.gateway.prod.island.powerapps.com/` |
    | <span data-ttu-id="18a64-217">Västra EU</span><span class="sxs-lookup"><span data-stu-id="18a64-217">West EU</span></span>                    | `https://electronicinvoicing.weu-il301.gateway.prod.island.powerapps.com/` |

3. <span data-ttu-id="18a64-218">I fältet **Miljö** anger du namnet på miljön för tillägget Elektronisk fakturering.</span><span class="sxs-lookup"><span data-stu-id="18a64-218">In the **Environment** field, enter the name of the Electronic invoicing add-on environment.</span></span>
4. <span data-ttu-id="18a64-219">Markera **Spara** och stäng sedan sidan.</span><span class="sxs-lookup"><span data-stu-id="18a64-219">Select **Save**, and then close the page.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
