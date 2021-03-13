---
title: Kom i gång med tjänsteadministreringen för tillägget Elektronisk fakturering
description: I det här avsnittet beskrivs hur du kommer igång med tillägget Elektronisk fakturering.
author: gionoder
manager: AnnBe
ms.date: 01/28/2021
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
ms.openlocfilehash: 111ec65aa826795125d4a9ce835f72e1a0f41b7b
ms.sourcegitcommit: e88c96d1cb817a22db81856cadb563c095ab2671
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/02/2021
ms.locfileid: "5104438"
---
# <a name="get-started-with-electronic-invoicing-add-on-service-administration"></a><span data-ttu-id="e5ca0-103">Kom i gång med tjänsteadministreringen för tillägget Elektronisk fakturering</span><span class="sxs-lookup"><span data-stu-id="e5ca0-103">Get started with Electronic invoicing add-on service administration</span></span>

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

## <a name="prerequisites"></a><span data-ttu-id="e5ca0-104">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="e5ca0-104">Prerequisites</span></span>

<span data-ttu-id="e5ca0-105">Innan du kan slutföra procedurerna i detta ämne måste följande förutsättningar finnas på plats:</span><span class="sxs-lookup"><span data-stu-id="e5ca0-105">Before you complete the procedures in this topic, the following prerequisites must be in place:</span></span>

- <span data-ttu-id="e5ca0-106">Du måste ha tillgång till ditt Microsoft Dynamics Lifecycle Services-konto (LCS).</span><span class="sxs-lookup"><span data-stu-id="e5ca0-106">You must have access to your Microsoft Dynamics Lifecycle Services (LCS) account.</span></span>
- <span data-ttu-id="e5ca0-107">Du måste ha ett LCS-projekt som innehåller version 10.0.13 eller senare av Microsoft Dynamics 365 Finance och Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="e5ca0-107">You must have an LCS project that includes version 10.0.13 or later of Microsoft Dynamics 365 Finance and Dynamics 365 Supply Chain Management.</span></span> <span data-ttu-id="e5ca0-108">Dessa program måste dessutom distribueras i något av följande Azure-områden:</span><span class="sxs-lookup"><span data-stu-id="e5ca0-108">Additionally, these apps must be deployed in one of the following Azure geographies:</span></span>

    - <span data-ttu-id="e5ca0-109">Östra USA</span><span class="sxs-lookup"><span data-stu-id="e5ca0-109">East US</span></span>
    - <span data-ttu-id="e5ca0-110">Västra USA</span><span class="sxs-lookup"><span data-stu-id="e5ca0-110">West US</span></span>
    - <span data-ttu-id="e5ca0-111">Norra EU</span><span class="sxs-lookup"><span data-stu-id="e5ca0-111">North EU</span></span>
    - <span data-ttu-id="e5ca0-112">Västra EU</span><span class="sxs-lookup"><span data-stu-id="e5ca0-112">West EU</span></span>

- <span data-ttu-id="e5ca0-113">Du måste ha tillgång till ditt Dynamics 365 Regulatory Configuration Services-konto (RCS).</span><span class="sxs-lookup"><span data-stu-id="e5ca0-113">You must have access to your Dynamics 365 Regulatory Configuration Services (RCS) account.</span></span>
- <span data-ttu-id="e5ca0-114">Du måste aktivera globaliseringsfunktionen för ditt RCS-konto i funktionshanteringen.</span><span class="sxs-lookup"><span data-stu-id="e5ca0-114">You must activate the Globalization feature for your RCS account in Feature management.</span></span> <span data-ttu-id="e5ca0-115">Mer information finns i [Regulatory Configuration Services (RCS) – globaliseringsfunktioner](rcs-globalization-feature.md).</span><span class="sxs-lookup"><span data-stu-id="e5ca0-115">For more information, see [Regulatory Configuration Services (RCS) - Globalization features](rcs-globalization-feature.md).</span></span>
- <span data-ttu-id="e5ca0-116">Du måste skapa ett nyckelvalv och ett lagringskonto i Azure.</span><span class="sxs-lookup"><span data-stu-id="e5ca0-116">You must create a key vault and a storage account in Azure.</span></span> <span data-ttu-id="e5ca0-117">Mer information finns i [Skapa ett Azure-lagringskonto och ett nyckelvalv](e-invoicing-create-azure-storage-account-key-vault.md).</span><span class="sxs-lookup"><span data-stu-id="e5ca0-117">For more information, see [Create an Azure storage account and a key vault](e-invoicing-create-azure-storage-account-key-vault.md).</span></span>

## <a name="install-the-add-on-for-microservices-in-lifecycle-services"></a><span data-ttu-id="e5ca0-118">Installera tillägget för mikrotjänster i Lifecycle Services</span><span class="sxs-lookup"><span data-stu-id="e5ca0-118">Install the add-on for microservices in Lifecycle Services</span></span>

1. <span data-ttu-id="e5ca0-119">Logga in på LCS-kontot.</span><span class="sxs-lookup"><span data-stu-id="e5ca0-119">Sign in to your LCS account.</span></span>
2. <span data-ttu-id="e5ca0-120">Välj panelen **Hantera förhandsgranskning**.</span><span class="sxs-lookup"><span data-stu-id="e5ca0-120">Select the **Preview feature management** tile.</span></span>
3. <span data-ttu-id="e5ca0-121">I avsnittet **Funktioner i allmänt tillgänglig förhandsversion** väljer du **Tjänst för e-fakturering**.</span><span class="sxs-lookup"><span data-stu-id="e5ca0-121">In the **Public Preview Features** section, select **e-Invoicing service**.</span></span>
4. <span data-ttu-id="e5ca0-122">Se till att alternativet **Förhandsgranskning aktiverad** är inställt på **Ja**.</span><span class="sxs-lookup"><span data-stu-id="e5ca0-122">Make sure that the **Preview feature enabled** option is set to **Yes**.</span></span>

## <a name="set-up-the-parameters-for-rcs-integration-with-the-electronic-invoicing-add-on"></a><span data-ttu-id="e5ca0-123">Ställ in parametrarna för RCS-integrationen med tillägget Elektronisk fakturering</span><span class="sxs-lookup"><span data-stu-id="e5ca0-123">Set up the parameters for RCS integration with the Electronic invoicing add-on</span></span>

1. <span data-ttu-id="e5ca0-124">Logga in på RCS-kontot.</span><span class="sxs-lookup"><span data-stu-id="e5ca0-124">Sign in to your RCS account.</span></span>
2. <span data-ttu-id="e5ca0-125">I arbetsytan **elektronisk rapportering** i avsnittet **Relaterade länkar** väljer du **parametrar för elektronisk rapportering**.</span><span class="sxs-lookup"><span data-stu-id="e5ca0-125">In the **Electronic reporting** workspace, in the **Related links** section, select **Electronic reporting parameters**.</span></span>
3. <span data-ttu-id="e5ca0-126">På fliken **Tjänst för e-fakturering**, under fliken **URI för tjänstens slutpunkt** anger du ungefärlig tjänsteslutpunkt för ditt Azure-område enligt följande tabell.</span><span class="sxs-lookup"><span data-stu-id="e5ca0-126">On the **e-Invoicing service** tab, in the **Service endpoint URI** field, enter the appropriate service endpoint for your Azure geography, as shown in the following table.</span></span>

    | <span data-ttu-id="e5ca0-127">Azure-område för datacenter</span><span class="sxs-lookup"><span data-stu-id="e5ca0-127">Datacenter Azure geography</span></span> | <span data-ttu-id="e5ca0-128">URI för tjänstslutpunkt</span><span class="sxs-lookup"><span data-stu-id="e5ca0-128">Service endpoint URI</span></span>                                                       |
    |----------------------------|----------------------------------------------------------------------------|
    | <span data-ttu-id="e5ca0-129">Östra USA</span><span class="sxs-lookup"><span data-stu-id="e5ca0-129">East US</span></span>                    | `https://electronicinvoicing.eus-il301.gateway.prod.island.powerapps.com/` |
    | <span data-ttu-id="e5ca0-130">Västra USA</span><span class="sxs-lookup"><span data-stu-id="e5ca0-130">West US</span></span>                    | `https://electronicinvoicing.wus-il301.gateway.prod.island.powerapps.com/` |
    | <span data-ttu-id="e5ca0-131">Norra EU</span><span class="sxs-lookup"><span data-stu-id="e5ca0-131">North EU</span></span>                   | `https://electronicinvoicing.neu-il301.gateway.prod.island.powerapps.com/` |
    | <span data-ttu-id="e5ca0-132">Västra EU</span><span class="sxs-lookup"><span data-stu-id="e5ca0-132">West EU</span></span>                    | `https://electronicinvoicing.weu-il301.gateway.prod.island.powerapps.com/` |

4. <span data-ttu-id="e5ca0-133">Kontrollera att fältet **Program-ID** är inställt på **0cdb527f-a8d1-4bf8-9436-b352c68682b2**.</span><span class="sxs-lookup"><span data-stu-id="e5ca0-133">Verify that the **Application Id** field is set to **0cdb527f-a8d1-4bf8-9436-b352c68682b2**.</span></span> <span data-ttu-id="e5ca0-134">Det här värdet är ett fast värde.</span><span class="sxs-lookup"><span data-stu-id="e5ca0-134">This value is a fixed value.</span></span>
5. <span data-ttu-id="e5ca0-135">I fältet **ID för LCS-miljö** anger du ID för ditt LCS-abonnemangskonto.</span><span class="sxs-lookup"><span data-stu-id="e5ca0-135">In the **LCS Environment Id** field, enter the ID of your LCS subscription account.</span></span>
6. <span data-ttu-id="e5ca0-136">Markera **Spara** och stäng sedan sidan.</span><span class="sxs-lookup"><span data-stu-id="e5ca0-136">Select **Save**, and then close the page.</span></span>

## <a name="create-key-vault-secret"></a><span data-ttu-id="e5ca0-137">Skapa nyckelvalvshemlighet</span><span class="sxs-lookup"><span data-stu-id="e5ca0-137">Create Key Vault secret</span></span>

1. <span data-ttu-id="e5ca0-138">Logga in på RCS-kontot.</span><span class="sxs-lookup"><span data-stu-id="e5ca0-138">Sign in to your RCS account.</span></span>
2. <span data-ttu-id="e5ca0-139">I arbetsytan **Globaliseringsfunktioner** i avsnittet **Miljö** väljer du panelen **e-fakturering**.</span><span class="sxs-lookup"><span data-stu-id="e5ca0-139">In the **Globalization feature** workspace, in the **Environment** section, select the **e-Invoicing** tile.</span></span>
3. <span data-ttu-id="e5ca0-140">På sidan **Miljökonfigurationer** väljer du i åtgärdsfönstret **Tjänstemiljö** och sedan **Parametrar för nyckelval**.</span><span class="sxs-lookup"><span data-stu-id="e5ca0-140">On the **Environment setups** page, on the action Pane, select **Service environment**, and then select **Key Vault parameters**.</span></span>
4. <span data-ttu-id="e5ca0-141">Välj **Ny** för att skapa en nyckelvalvshemlighet.</span><span class="sxs-lookup"><span data-stu-id="e5ca0-141">Select **New** to create a key vault secret.</span></span>
5. <span data-ttu-id="e5ca0-142">I fältet **Namn** anger du namnet för nyckelvalvshemligheten.</span><span class="sxs-lookup"><span data-stu-id="e5ca0-142">In the **Name** field, enter the name of the key vault secret.</span></span> <span data-ttu-id="e5ca0-143">Ange en beskrivning i fältet **beskrivning**.</span><span class="sxs-lookup"><span data-stu-id="e5ca0-143">In the **Description** field, enter a description.</span></span>
6. <span data-ttu-id="e5ca0-144">I fältet **URI för nyckelvalv** klistrar du in hemligheten från Azure Key Vault.</span><span class="sxs-lookup"><span data-stu-id="e5ca0-144">In the **Key Vault URI** field, paste the secret from Azure Key Vault.</span></span>
7. <span data-ttu-id="e5ca0-145">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="e5ca0-145">Select **Save**.</span></span>

## <a name="create-storage-account-secret"></a><span data-ttu-id="e5ca0-146">Skapa hemlighet för lagringskonto</span><span class="sxs-lookup"><span data-stu-id="e5ca0-146">Create Storage account secret</span></span>

1. <span data-ttu-id="e5ca0-147">På sidan **Parametrar för nyckelvalv**, i avsnittet **Certifikat**, väljer du **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="e5ca0-147">On **Key vault parameters** page, in the **Certificates** section, select **Add**.</span></span>
2. <span data-ttu-id="e5ca0-148">I fältet **Namn** anger du namnet för lagringskontots hemlighet.</span><span class="sxs-lookup"><span data-stu-id="e5ca0-148">In the **Name** field, enter the same of the storage account secret.</span></span> <span data-ttu-id="e5ca0-149">Ange en beskrivning i fältet **beskrivning**.</span><span class="sxs-lookup"><span data-stu-id="e5ca0-149">In the **Description** field, enter a description.</span></span>
3. <span data-ttu-id="e5ca0-150">I fältet **Typ** väljer du **Certifikat**.</span><span class="sxs-lookup"><span data-stu-id="e5ca0-150">In the **Type** field, select **Certificate**.</span></span>
4. <span data-ttu-id="e5ca0-151">Markera **Spara** och stäng sedan sidan.</span><span class="sxs-lookup"><span data-stu-id="e5ca0-151">Select **Save**, and then close the page.</span></span>

## <a name="create-an-electronic-invoicing-add-on-environment"></a><span data-ttu-id="e5ca0-152">Skapa en miljö för Elektronisk fakturering</span><span class="sxs-lookup"><span data-stu-id="e5ca0-152">Create an Electronic invoicing add-on environment</span></span>

1. <span data-ttu-id="e5ca0-153">Logga in på RCS-kontot.</span><span class="sxs-lookup"><span data-stu-id="e5ca0-153">Sign in to your RCS account.</span></span>
2. <span data-ttu-id="e5ca0-154">I arbetsytan **Globaliseringsfunktioner** i avsnittet **Miljö** väljer du panelen **e-fakturering**.</span><span class="sxs-lookup"><span data-stu-id="e5ca0-154">In the **Globalization feature** workspace, in the **Environment** section, select the **e-Invoicing** tile.</span></span>

## <a name="create-a-service-environment"></a><span data-ttu-id="e5ca0-155">Skapa en tjänstemiljö</span><span class="sxs-lookup"><span data-stu-id="e5ca0-155">Create a service environment</span></span>

1. <span data-ttu-id="e5ca0-156">På sidan **Miljökonfigurationer** väljer du **Tjänstemiljö** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="e5ca0-156">On the **Environment setups** page, on the action Pane, select **Service environment**.</span></span>
2. <span data-ttu-id="e5ca0-157">Välj **Ny** för att skapa en ny tjänstemiljö.</span><span class="sxs-lookup"><span data-stu-id="e5ca0-157">Select **New** to create a new service environment.</span></span>
3. <span data-ttu-id="e5ca0-158">I fältet **Namn** anger du namnet på miljön för e-fakturering.</span><span class="sxs-lookup"><span data-stu-id="e5ca0-158">In the **Name** field, enter the name of the e-Invoicing environment.</span></span> <span data-ttu-id="e5ca0-159">Ange en beskrivning i fältet **beskrivning**.</span><span class="sxs-lookup"><span data-stu-id="e5ca0-159">In the **Description** field, enter a description.</span></span>
4. <span data-ttu-id="e5ca0-160">I fältet **Lagringshemlighet för SAS-token** väljer du namnet på det certifikat som måste användas för att ge åtkomst till lagringskontot.</span><span class="sxs-lookup"><span data-stu-id="e5ca0-160">In the **Storage SAS token secret** field, select the name of the certificate that must be used to authenticate access to the storage account.</span></span>
5. <span data-ttu-id="e5ca0-161">I avsnittet **Användare** väljer du **Lägg till** om du vill lägga till en användare som är behörig att skicka in elektroniska fakturor via miljön samt även ansluta till lagringskontot.</span><span class="sxs-lookup"><span data-stu-id="e5ca0-161">In the **Users** section, select **Add** to add a user who is allowed to submit electronic invoices through the environment and also connect to the storage account.</span></span>
6. <span data-ttu-id="e5ca0-162">I fältet **Användar-ID** anger du användarens alias.</span><span class="sxs-lookup"><span data-stu-id="e5ca0-162">In the **User ID** field, enter the alias of the user.</span></span> <span data-ttu-id="e5ca0-163">I fältet **E-postadress** anger du användarens e-postadress.</span><span class="sxs-lookup"><span data-stu-id="e5ca0-163">In the **Email** field, enter the user's email address.</span></span>
7. <span data-ttu-id="e5ca0-164">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="e5ca0-164">Select **Save**.</span></span>
8. <span data-ttu-id="e5ca0-165">Om dina lands-/regionspecifika fakturor kräver en certifikatkedja för att kunna tillämpa digitala signaturer, väljer du **Parametrar för nyckelvalv** och sedan **Certifikatkedja** i åtgärdsfönstret och följer sedan dessa steg:</span><span class="sxs-lookup"><span data-stu-id="e5ca0-165">If your country/region-specific invoices require a chain of certificates to apply digital signatures, on the Action pane, select **Key Vault parameters**, then select **Chain of certificates**, and follow these steps:</span></span>

    1. <span data-ttu-id="e5ca0-166">Välj **Ny** för att skapa en certifikatkedja.</span><span class="sxs-lookup"><span data-stu-id="e5ca0-166">Select **New** to create a chain of certificates.</span></span>
    2. <span data-ttu-id="e5ca0-167">I fältet **Namn** anger du namnet på certifikatkedjan.</span><span class="sxs-lookup"><span data-stu-id="e5ca0-167">In the **Name** field, enter the name of the chain of certificate.</span></span> <span data-ttu-id="e5ca0-168">Ange en beskrivning i fältet **beskrivning**.</span><span class="sxs-lookup"><span data-stu-id="e5ca0-168">In the **Description** field, enter a description.</span></span>
    3. <span data-ttu-id="e5ca0-169">I avsnittet **Certifikat** väljer du **Lägg till** för att lägga till ett certifikat i kedjan.</span><span class="sxs-lookup"><span data-stu-id="e5ca0-169">In the **Certificates** section, select **Add** to add a certificate to the chain.</span></span>
    4. <span data-ttu-id="e5ca0-170">Använd knappen **Upp** eller **Ner** för att byta certifikatets position i kedjan.</span><span class="sxs-lookup"><span data-stu-id="e5ca0-170">Use the **Up** or **Down** button to change the position of the certificate in the chain.</span></span>
    5. <span data-ttu-id="e5ca0-171">Markera **Spara** och stäng sedan sidan.</span><span class="sxs-lookup"><span data-stu-id="e5ca0-171">Select **Save**, and then close the page.</span></span>
    6. <span data-ttu-id="e5ca0-172">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="e5ca0-172">Close the page.</span></span>
9. <span data-ttu-id="e5ca0-173">I åtgärdsfönstret på sidan **Tjänstemiljö** väljer du **Publicera** om du vill publicera miljön i molnet.</span><span class="sxs-lookup"><span data-stu-id="e5ca0-173">On **Service environment** page, on the Action Pane, select **Publish** to publish the environment to the cloud.</span></span> <span data-ttu-id="e5ca0-174">Värdet i fältet **Status** ändras till **Publicerad**.</span><span class="sxs-lookup"><span data-stu-id="e5ca0-174">The value of the **Status** field is changed to **Published**.</span></span>

## <a name="create-a-connected-application"></a><span data-ttu-id="e5ca0-175">Skapa ett anslutet program.</span><span class="sxs-lookup"><span data-stu-id="e5ca0-175">Create a connected application</span></span>

1. <span data-ttu-id="e5ca0-176">På sidan **Miljökonfigurationer** väljer du **Anslutna program** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="e5ca0-176">On the **Environment setups** page, on the action Pane, select **Connected applications**.</span></span>
2. <span data-ttu-id="e5ca0-177">Skapa ett anslutet program genom att välja **Ny**.</span><span class="sxs-lookup"><span data-stu-id="e5ca0-177">Select **New** to create a connected application.</span></span>
3. <span data-ttu-id="e5ca0-178">I fältet **Namn** anger du namnet på det program du vill ansluta.</span><span class="sxs-lookup"><span data-stu-id="e5ca0-178">In the **Name** field, enter the name of the application to connect.</span></span>
4. <span data-ttu-id="e5ca0-179">I fältet **Program** anger du URL:en för den Finance- och Supply Chain Management-miljö du vill ansluta.</span><span class="sxs-lookup"><span data-stu-id="e5ca0-179">In the **Application** field, enter the URL of the Finance and Supply Chain Management environment to connect.</span></span>
4. <span data-ttu-id="e5ca0-180">I fältet **Klientorganisation** anger du klientorganisationen för Finance and Supply Chain Management-miljön.</span><span class="sxs-lookup"><span data-stu-id="e5ca0-180">In the **Tenant** field, enter the tenant of the Finance and Supply Chain Management environment.</span></span>
5. <span data-ttu-id="e5ca0-181">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="e5ca0-181">Select **Save**.</span></span>
6. <span data-ttu-id="e5ca0-182">I åtgärdsfönstret väljer du **Kontrollera anslutning** om du vill testa anslutningen till miljön.</span><span class="sxs-lookup"><span data-stu-id="e5ca0-182">On the Action Pane, select **Check connection** to test the connection with the environment.</span></span> <span data-ttu-id="e5ca0-183">Stäng sedan sidan.</span><span class="sxs-lookup"><span data-stu-id="e5ca0-183">Then close the page.</span></span>

## <a name="link-connected-applications-to-environments"></a><span data-ttu-id="e5ca0-184">Koppla anslutna program till miljöer</span><span class="sxs-lookup"><span data-stu-id="e5ca0-184">Link connected applications to environments</span></span>

1. <span data-ttu-id="e5ca0-185">På sidan **Miljökonfigurationer** väljer du **Ny** om du vill tilldela ett anslutet program till en miljö.</span><span class="sxs-lookup"><span data-stu-id="e5ca0-185">On the **Environment setups** page, select **New** to assign a connected application to an environment.</span></span>
2. <span data-ttu-id="e5ca0-186">I fältet **Anslutet program** väljer du ett anslutet program.</span><span class="sxs-lookup"><span data-stu-id="e5ca0-186">In the **Connected application** field, select a connected application.</span></span>
3. <span data-ttu-id="e5ca0-187">I fältet **Tjänstemiljö** väljer du en tjänstemiljö.</span><span class="sxs-lookup"><span data-stu-id="e5ca0-187">In the **Service environment** field, select a service environment.</span></span>
4. <span data-ttu-id="e5ca0-188">Markera **Spara** och stäng sedan sidan.</span><span class="sxs-lookup"><span data-stu-id="e5ca0-188">Select **Save**, and then close the page.</span></span>

## <a name="set-up-the-electronic-invoicing-add-on-integration-in-finance-and-supply-chain-management"></a><span data-ttu-id="e5ca0-189">Ställa in integrering av tillägget Elektronisk fakturering i Finance och Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="e5ca0-189">Set up the Electronic invoicing add-on integration in Finance and Supply Chain Management</span></span>

### <a name="turn-on-the-electronic-invoicing-add-on-integration-feature"></a><span data-ttu-id="e5ca0-190">Aktivera integrationsfunktionen för tillägget Elektronisk fakturering</span><span class="sxs-lookup"><span data-stu-id="e5ca0-190">Turn on the Electronic invoicing add-on integration feature</span></span>

1. <span data-ttu-id="e5ca0-191">Logga in på din instans för Finance eller Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="e5ca0-191">Sign in to your Finance or Supply Chain Management instance.</span></span>
2. <span data-ttu-id="e5ca0-192">I arbetsytan **Funktionshantering** söker du efter den nya funktionen **Integrering av tillägg för elektronisk fakturering**.</span><span class="sxs-lookup"><span data-stu-id="e5ca0-192">In the **Feature management** workspace, search for the **Electronic invoicing add-on integration** feature.</span></span> <span data-ttu-id="e5ca0-193">Om den här funktionen inte visas på sidan väljer du **Sök efter uppdateringar**.</span><span class="sxs-lookup"><span data-stu-id="e5ca0-193">If this feature doesn't appear on the page, select **Check for updates**.</span></span>
3. <span data-ttu-id="e5ca0-194">Välj funktionen och välj sedan **aktivera nu**.</span><span class="sxs-lookup"><span data-stu-id="e5ca0-194">Select the feature, and then select **Enable now**.</span></span>

### <a name="set-up-the-service-endpoint-url"></a><span data-ttu-id="e5ca0-195">Ställ in URL för tjänstslutpunkt</span><span class="sxs-lookup"><span data-stu-id="e5ca0-195">Set up the service endpoint URL</span></span>

1. <span data-ttu-id="e5ca0-196">Gå till **organisationsadministration \> inställning \> parametrar för elektroniska dokument**.</span><span class="sxs-lookup"><span data-stu-id="e5ca0-196">Go to **Organization administration \> Setup \> Electronic document parameters**.</span></span>
2. <span data-ttu-id="e5ca0-197">På fliken **Överföringstjänst**, i fältet **URL för tjänsteslutpunkt** anger du relevant tjänsteslutpunkt för ditt Azure-område enligt följande tabell.</span><span class="sxs-lookup"><span data-stu-id="e5ca0-197">On the **Submission service** tab, in the **Service endpoint URL** field, enter the appropriate service endpoint for your Azure geography, as shown in the following table.</span></span>

    | <span data-ttu-id="e5ca0-198">Azure-område för datacenter</span><span class="sxs-lookup"><span data-stu-id="e5ca0-198">Datacenter Azure geography</span></span> | <span data-ttu-id="e5ca0-199">URL för tjänstslutpunkt</span><span class="sxs-lookup"><span data-stu-id="e5ca0-199">Service endpoint URL</span></span>                                                       |
    |----------------------------|----------------------------------------------------------------------------|
    | <span data-ttu-id="e5ca0-200">Östra USA</span><span class="sxs-lookup"><span data-stu-id="e5ca0-200">East US</span></span>                    | `https://electronicinvoicing.eus-il301.gateway.prod.island.powerapps.com/` |
    | <span data-ttu-id="e5ca0-201">Västra USA</span><span class="sxs-lookup"><span data-stu-id="e5ca0-201">West US</span></span>                    | `https://electronicinvoicing.wus-il301.gateway.prod.island.powerapps.com/` |
    | <span data-ttu-id="e5ca0-202">Norra EU</span><span class="sxs-lookup"><span data-stu-id="e5ca0-202">North EU</span></span>                   | `https://electronicinvoicing.neu-il301.gateway.prod.island.powerapps.com/` |
    | <span data-ttu-id="e5ca0-203">Västra EU</span><span class="sxs-lookup"><span data-stu-id="e5ca0-203">West EU</span></span>                    | `https://electronicinvoicing.weu-il301.gateway.prod.island.powerapps.com/` |

3. <span data-ttu-id="e5ca0-204">I fältet **Miljö** anger du namnet på miljön för tillägget Elektronisk fakturering.</span><span class="sxs-lookup"><span data-stu-id="e5ca0-204">In the **Environment** field, enter the name of the Electronic invoicing add-on environment.</span></span>
4. <span data-ttu-id="e5ca0-205">Markera **Spara** och stäng sedan sidan.</span><span class="sxs-lookup"><span data-stu-id="e5ca0-205">Select **Save**, and then close the page.</span></span>
