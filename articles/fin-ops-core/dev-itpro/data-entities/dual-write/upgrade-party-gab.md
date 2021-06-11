---
title: Uppgradera till part- och globala adressboksmodellen.
description: I detta ämne beskrivs hur du uppgraderar data för dubbel skrivning till parten samt till den globala adressboksmodellen..
author: RamaKrishnamoorthy
ms.date: 03/31/2021
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2021-03-31
ms.openlocfilehash: 90ddbe704ab21d62752b581a813601e8986c2103
ms.sourcegitcommit: 180548e3c10459776cf199989d3753e0c1555912
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/28/2021
ms.locfileid: "6112683"
---
# <a name="upgrade-to-the-party-and-global-address-book-model"></a><span data-ttu-id="f40ea-103">Uppgradera till part- och globala adressboksmodellen</span><span class="sxs-lookup"><span data-stu-id="f40ea-103">Upgrade to the party and global address book model</span></span>

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="f40ea-104">[Mallen Microsoft Azure Data Factory](https://aka.ms/dual-write-gab-adf) hjälper dig att uppgradera befintliga registerdata för dubbel skrivning för **Konto**, **Kontakt** och **Leverantör** till parten samt till den globala adressboksmodellen.</span><span class="sxs-lookup"><span data-stu-id="f40ea-104">The [Microsoft Azure Data Factory template](https://aka.ms/dual-write-gab-adf) helps you upgrade existing **Account**, **Contact**, and **Vendor** table data in dual-write to the party and global address book model.</span></span> <span data-ttu-id="f40ea-105">I mallen stäms data från både Finance and Operations-program och program för kundrelationer av.</span><span class="sxs-lookup"><span data-stu-id="f40ea-105">The template reconciles the data from both finance and operations apps and customer engagement applications.</span></span> <span data-ttu-id="f40ea-106">I slutet av processen skapas fälten **Part** och **Kontakt** för **Part**-poster, som sedan associeras med poster för **Konto**, **Kontakt** och **Leverantör** i program för kundengagemang.</span><span class="sxs-lookup"><span data-stu-id="f40ea-106">At the end of the process, **Party** and **Contact** fields for **Party** records will be created and associated with **Account**, **Contact**, and **Vendor** records in customer engagement applications.</span></span> <span data-ttu-id="f40ea-107">En .csv-fil (`FONewParty.csv`) genereras för att skapa nya **Part**-poster inuti Finance and Operations-appen.</span><span class="sxs-lookup"><span data-stu-id="f40ea-107">A .csv file (`FONewParty.csv`) is generated to create new **Party** records inside the finance and operations app.</span></span> <span data-ttu-id="f40ea-108">I detta ämne finns instruktioner om hur du använder Data Factory-mallen och uppgraderar dina data.</span><span class="sxs-lookup"><span data-stu-id="f40ea-108">This topic provides instructions about how to use the Data Factory template and upgrade your data.</span></span>

<span data-ttu-id="f40ea-109">Om du inte har några anpassningar kan du använda mallen som den är.</span><span class="sxs-lookup"><span data-stu-id="f40ea-109">If you don’t have any customizations, you can use the template as is.</span></span> <span data-ttu-id="f40ea-110">Om du har anpassningar för **Konto**, **Kontakt** och **Leverantör** måste du ändra mallen med hjälp av följande instruktioner.</span><span class="sxs-lookup"><span data-stu-id="f40ea-110">If you have customizations for **Account**, **Contact**, and **Vendor** then you must modify the template using the following instructions.</span></span>

> [!NOTE]
> <span data-ttu-id="f40ea-111">Mallen uppgraderar endast **Partsdata**.</span><span class="sxs-lookup"><span data-stu-id="f40ea-111">The template only upgrades the **Party** data.</span></span> <span data-ttu-id="f40ea-112">I en framtida version inkluderas postnummer och elektroniska adresser.</span><span class="sxs-lookup"><span data-stu-id="f40ea-112">In a future release, postal and electronic addresses will be included.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="f40ea-113">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="f40ea-113">Prerequisites</span></span>

<span data-ttu-id="f40ea-114">Följande förutsättningar krävs för att du ska kunna uppgradera till den part och den globala adressboksmodellen:</span><span class="sxs-lookup"><span data-stu-id="f40ea-114">The following prerequisites are required to upgrade to the party and global address book model:</span></span>

+ [<span data-ttu-id="f40ea-115">Azure-abonnemang</span><span class="sxs-lookup"><span data-stu-id="f40ea-115">Azure subscription</span></span>](https://portal.azure.com/)
+ [<span data-ttu-id="f40ea-116">Åtkomst till mallen</span><span class="sxs-lookup"><span data-stu-id="f40ea-116">Access to the template</span></span>](https://aka.ms/dual-write-gab-adf)
+ <span data-ttu-id="f40ea-117">Du måste vara en befintlig kund.</span><span class="sxs-lookup"><span data-stu-id="f40ea-117">You must be an existing dual-write customer.</span></span>

## <a name="prepare-for-the-upgrade"></a><span data-ttu-id="f40ea-118">Förbereda uppgraderinge</span><span class="sxs-lookup"><span data-stu-id="f40ea-118">Prepare for the upgrade</span></span>
<span data-ttu-id="f40ea-119">Följande aktiviteter behövs för att förbereda uppgraderingen:</span><span class="sxs-lookup"><span data-stu-id="f40ea-119">The following activities are needed to prepare for the upgrade:</span></span>

+ <span data-ttu-id="f40ea-120">**Fullt synkroniserat**: Båda miljöerna är helt synkroniserade för **Konto (kund)**, **Kontakt** och **Leverantör**.</span><span class="sxs-lookup"><span data-stu-id="f40ea-120">**Fully synced**: Both environments are in a fully synced state for **Account (Customer)**, **Contact**, and **Vendor**.</span></span>
+ <span data-ttu-id="f40ea-121">**Integreringsnycklar**: Registren **Konto (Kund)**, **Kontakt** och **Leverantör** i program för kundengagemang använder de integreringsnycklar som levererades färdiga.</span><span class="sxs-lookup"><span data-stu-id="f40ea-121">**Integration keys**: **Account (Customer)**, **Contact**, and **Vendor** tables in customer engagement apps are using the integration keys that shipped out-of-the-box.</span></span> <span data-ttu-id="f40ea-122">Om du anpassar integreringsnycklarna måste du anpassa mallen.</span><span class="sxs-lookup"><span data-stu-id="f40ea-122">If you customized the integration keys, you must customize the template.</span></span>
+ <span data-ttu-id="f40ea-123">**Partsnummer**: Alla **Kontro (kund)-**, **Kontakt-** och **Leverantörs** poster som ska uppgraderas har ett **Parts** nummer.</span><span class="sxs-lookup"><span data-stu-id="f40ea-123">**Party number**: All **Account (Customer)**, **Contact**, and **Vendor** records that will be upgraded have a **Party** number.</span></span> <span data-ttu-id="f40ea-124">Poster utan ett **Parts** nummer ignoreras.</span><span class="sxs-lookup"><span data-stu-id="f40ea-124">Records without a **Party** number will be ignored.</span></span> <span data-ttu-id="f40ea-125">Om du vill uppgradera dessa poster lägger du till ett **Parts** nummer i dem innan du startar uppgraderingsprocessen.</span><span class="sxs-lookup"><span data-stu-id="f40ea-125">If you want to upgrade those records, add a **Party** number to them before you start the upgrade process.</span></span>
+ <span data-ttu-id="f40ea-126">**Systemavbrott**: Under uppgraderingen måste du ta både Finance and Operations-miljön och miljön för kundengagemang offline.</span><span class="sxs-lookup"><span data-stu-id="f40ea-126">**System outage**: During the upgrade process, you will have to take both the finance and operations and customer engagement environments offline.</span></span>
+ <span data-ttu-id="f40ea-127">**Ögonblicksbild**: Ta ögonblicksbilder av både Finance and Operations-appen och appen för kundengagemang.</span><span class="sxs-lookup"><span data-stu-id="f40ea-127">**Snapshot**: Take snapshots of both the finance and operations apps and customer engagement apps.</span></span> <span data-ttu-id="f40ea-128">Använd ögonblicksbilderna om du vill återställa föregående status vid behov.</span><span class="sxs-lookup"><span data-stu-id="f40ea-128">Use the snapshots to restore the previous state if you need to.</span></span>

## <a name="deployment"></a><span data-ttu-id="f40ea-129">Distribution</span><span class="sxs-lookup"><span data-stu-id="f40ea-129">Deployment</span></span>

1. <span data-ttu-id="f40ea-130">Hämta mallen från [Implementeringstillgångar för Dynamics-365-FastTrack](https://aka.ms/dual-write-gab-adf)</span><span class="sxs-lookup"><span data-stu-id="f40ea-130">Download the template from [Dynamics-365-FastTrack-Implementation-Assets](https://aka.ms/dual-write-gab-adf).</span></span>

2. <span data-ttu-id="f40ea-131">Logga in på [Microsoft Azure](https://portal.azure.com/).</span><span class="sxs-lookup"><span data-stu-id="f40ea-131">Sign in to [Microsoft Azure](https://portal.azure.com/).</span></span>

3. <span data-ttu-id="f40ea-132">Skapa en [resursgrupp](/azure/azure-resource-manager/management/manage-resource-groups-portal).</span><span class="sxs-lookup"><span data-stu-id="f40ea-132">Create a [resource group](/azure/azure-resource-manager/management/manage-resource-groups-portal).</span></span>

4. <span data-ttu-id="f40ea-133">Skapa ett [lagringskonto](/azure/storage/common/storage-account-create?tabs=azure-portal) i resursgruppen som du skapade.</span><span class="sxs-lookup"><span data-stu-id="f40ea-133">Create a [storage account](/azure/storage/common/storage-account-create?tabs=azure-portal) in the resource group that you created.</span></span>

5. <span data-ttu-id="f40ea-134">Skapa en [datafabrik](/azure/data-factory/quickstart-create-data-factory-portal) i resursgruppen som du skapade ovan.</span><span class="sxs-lookup"><span data-stu-id="f40ea-134">Create a [data factory](/azure/data-factory/quickstart-create-data-factory-portal) in above resource group that you created.</span></span>

6. <span data-ttu-id="f40ea-135">Öppna datafabriken och välj panelen **Skapa och övervaka**.</span><span class="sxs-lookup"><span data-stu-id="f40ea-135">Open the data factory and select the **Author & Monitor** tile.</span></span>

7. <span data-ttu-id="f40ea-136">På fliken **Hantera** väljer du **ARM-mall**.</span><span class="sxs-lookup"><span data-stu-id="f40ea-136">On the **Manage** tab, select **ARM template**.</span></span>

8. <span data-ttu-id="f40ea-137">Välj **Importera ARM-mall** för att importera mallen **Part**.</span><span class="sxs-lookup"><span data-stu-id="f40ea-137">Select the **Import ARM template** to import the **Party** template.</span></span>

9. <span data-ttu-id="f40ea-138">Importera mallen till datafabriken.</span><span class="sxs-lookup"><span data-stu-id="f40ea-138">Import the template into the data factory.</span></span> <span data-ttu-id="f40ea-139">Ange följande värden för **Projektinformation** och **Instansinformation**.</span><span class="sxs-lookup"><span data-stu-id="f40ea-139">Enter the following values for **Project details** and **Instance details**.</span></span>

    <span data-ttu-id="f40ea-140">Fält</span><span class="sxs-lookup"><span data-stu-id="f40ea-140">Field</span></span> | <span data-ttu-id="f40ea-141">Värde</span><span class="sxs-lookup"><span data-stu-id="f40ea-141">Value</span></span>
    ---|---
    <span data-ttu-id="f40ea-142">Abonnemang</span><span class="sxs-lookup"><span data-stu-id="f40ea-142">Subscription</span></span> | <span data-ttu-id="f40ea-143">Azure-abonnemang</span><span class="sxs-lookup"><span data-stu-id="f40ea-143">Azure subscription</span></span>
    <span data-ttu-id="f40ea-144">Resursgrupp</span><span class="sxs-lookup"><span data-stu-id="f40ea-144">Resource group</span></span> | <span data-ttu-id="f40ea-145">Ange samma resurs under vilken lagringskontot skapas.</span><span class="sxs-lookup"><span data-stu-id="f40ea-145">Provide same resource under which storage account is created.</span></span>
    <span data-ttu-id="f40ea-146">Region</span><span class="sxs-lookup"><span data-stu-id="f40ea-146">Region</span></span> | <span data-ttu-id="f40ea-147">Ange region.</span><span class="sxs-lookup"><span data-stu-id="f40ea-147">Specify region.</span></span>
    <span data-ttu-id="f40ea-148">Fabriksnamn</span><span class="sxs-lookup"><span data-stu-id="f40ea-148">Factory Name</span></span> | <span data-ttu-id="f40ea-149">Ange fabriksnamn.</span><span class="sxs-lookup"><span data-stu-id="f40ea-149">Specify factory name.</span></span>
    <span data-ttu-id="f40ea-150">Huvudservicenyckel för kopplad FO-service</span><span class="sxs-lookup"><span data-stu-id="f40ea-150">FO Linked Service_service Principal Key</span></span> | <span data-ttu-id="f40ea-151">Ange nyckeln för ansökan</span><span class="sxs-lookup"><span data-stu-id="f40ea-151">Specify the application's key.</span></span>
    <span data-ttu-id="f40ea-152">Anslutningssträng för Azure Blob Storage</span><span class="sxs-lookup"><span data-stu-id="f40ea-152">Azure Blob Storage_connection String</span></span> | <span data-ttu-id="f40ea-153">Anslutningssträng för Azure Blob-lagring.</span><span class="sxs-lookup"><span data-stu-id="f40ea-153">Azure Blob storage connection string.</span></span>
    <span data-ttu-id="f40ea-154">Kopplat tjänstelösenord för Dynamics Crm</span><span class="sxs-lookup"><span data-stu-id="f40ea-154">Dynamics Crm Linked Service_password</span></span> | <span data-ttu-id="f40ea-155">Lösenordet för det användarkonto du angett som användarnamn.</span><span class="sxs-lookup"><span data-stu-id="f40ea-155">The password for the user account you specified as the username.</span></span>
    <span data-ttu-id="f40ea-156">FO Linked Service_properties_type Properties_url</span><span class="sxs-lookup"><span data-stu-id="f40ea-156">FO Linked Service_properties_type Properties_url</span></span>  | `https://sampledynamics.sandbox-operationsdynamics.com/data`
    <span data-ttu-id="f40ea-157">FO Linked Service_properties_type Properties_tenant</span><span class="sxs-lookup"><span data-stu-id="f40ea-157">FO Linked Service_properties_type Properties_tenant</span></span> | <span data-ttu-id="f40ea-158">Ange information om klientorganisation (domännamn eller ID för klientorganisation) under vilket programmet finns.</span><span class="sxs-lookup"><span data-stu-id="f40ea-158">Specify the tenant information (domain name or tenant ID) under which your application resides.</span></span>
    <span data-ttu-id="f40ea-159">FO Linked Service_properties_type Properties_aad Resource Id</span><span class="sxs-lookup"><span data-stu-id="f40ea-159">FO Linked Service_properties_type Properties_aad Resource Id</span></span> | `https://sampledynamics.sandboxoperationsdynamics.com`
    <span data-ttu-id="f40ea-160">FO Linked Service_properties_type Properties_service Principal Id</span><span class="sxs-lookup"><span data-stu-id="f40ea-160">FO Linked Service_properties_type Properties_service Principal Id</span></span> | <span data-ttu-id="f40ea-161">Ange programmets klient-ID.</span><span class="sxs-lookup"><span data-stu-id="f40ea-161">Specify the application's client ID.</span></span>
    <span data-ttu-id="f40ea-162">Dynamics Crm Linked Service_properties_type Properties_username</span><span class="sxs-lookup"><span data-stu-id="f40ea-162">Dynamics Crm Linked Service_properties_type Properties_username</span></span> | <span data-ttu-id="f40ea-163">Användarnamnet som ska kopplas till Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="f40ea-163">The username to connect to Dynamics 365.</span></span>

    <span data-ttu-id="f40ea-164">Mer information finns i följande ämnen:</span><span class="sxs-lookup"><span data-stu-id="f40ea-164">For additional information, refer to the following topics:</span></span> 
    
    - [<span data-ttu-id="f40ea-165">Manuellt främja en Resource Manager-mall för varje miljö</span><span class="sxs-lookup"><span data-stu-id="f40ea-165">Manually promote a Resource Manager template for each environment</span></span>](/azure/data-factory/continuous-integration-deployment#manually-promote-a-resource-manager-template-for-each-environment)
    - [<span data-ttu-id="f40ea-166">Länkade tjänsteegenskaper</span><span class="sxs-lookup"><span data-stu-id="f40ea-166">Linked service properties</span></span>](/azure/data-factory/connector-dynamics-ax#linked-service-properties)
    - [<span data-ttu-id="f40ea-167">Kopiera data med Azure Data Factory</span><span class="sxs-lookup"><span data-stu-id="f40ea-167">Copy data using Azure Data Factory</span></span>](/azure/data-factory/connector-dynamics-crm-office-365#dynamics-365-and-dynamics-crm-online)

10. <span data-ttu-id="f40ea-168">Efter distributionen kan du validera datauppsättningarna, dataflödet och länkad tjänst för datafabriken.</span><span class="sxs-lookup"><span data-stu-id="f40ea-168">After deployment, validate the datasets, data flow, and linked service of the data factory.</span></span>

   ![Datauppsättningar, dataflöde och länkad tjänst](media/data-factory-validate.png)

11. <span data-ttu-id="f40ea-170">Navigera till **Hantera**.</span><span class="sxs-lookup"><span data-stu-id="f40ea-170">Navigate to **Manage**.</span></span> <span data-ttu-id="f40ea-171">Under **Anslutningar** väljer du **Kopplad tjänst**.</span><span class="sxs-lookup"><span data-stu-id="f40ea-171">Under **Connections**, select **Linked Service**.</span></span> <span data-ttu-id="f40ea-172">Välj **DynamicsCrmLinkedService**.</span><span class="sxs-lookup"><span data-stu-id="f40ea-172">Select **DynamicsCrmLinkedService**.</span></span> <span data-ttu-id="f40ea-173">Ange följande värden i formuläret **Redigera kopplad tjänst (Dynamics CRM)**.</span><span class="sxs-lookup"><span data-stu-id="f40ea-173">In the **Edit linked service (Dynamics CRM)** form, enter the following values.</span></span>

    <span data-ttu-id="f40ea-174">Fält</span><span class="sxs-lookup"><span data-stu-id="f40ea-174">Field</span></span> | <span data-ttu-id="f40ea-175">Värde</span><span class="sxs-lookup"><span data-stu-id="f40ea-175">Value</span></span>
    ---|---
    <span data-ttu-id="f40ea-176">Namn</span><span class="sxs-lookup"><span data-stu-id="f40ea-176">Name</span></span> | <span data-ttu-id="f40ea-177">DynamicsCrmLinkedService</span><span class="sxs-lookup"><span data-stu-id="f40ea-177">DynamicsCrmLinkedService</span></span>
    <span data-ttu-id="f40ea-178">beskrivning</span><span class="sxs-lookup"><span data-stu-id="f40ea-178">Description</span></span> | <span data-ttu-id="f40ea-179">Kopplade tjänster för anslutning med CRM-instans för hämtning av entitetsdata</span><span class="sxs-lookup"><span data-stu-id="f40ea-179">Linked services to connect with CRM instance to fetch entities data</span></span>
    <span data-ttu-id="f40ea-180">Anslut via integreringskörning</span><span class="sxs-lookup"><span data-stu-id="f40ea-180">Connect via integration runtime</span></span> | <span data-ttu-id="f40ea-181">AutoResolvelntegrationRuntime</span><span class="sxs-lookup"><span data-stu-id="f40ea-181">AutoResolvelntegrationRuntime</span></span>
    <span data-ttu-id="f40ea-182">Distributionstyp</span><span class="sxs-lookup"><span data-stu-id="f40ea-182">Deployment type</span></span> | <span data-ttu-id="f40ea-183">Online</span><span class="sxs-lookup"><span data-stu-id="f40ea-183">Online</span></span>
    <span data-ttu-id="f40ea-184">Service-Uri</span><span class="sxs-lookup"><span data-stu-id="f40ea-184">Service Uri</span></span> | `https://<organization-name>.crm[x].dynamics.com`
    <span data-ttu-id="f40ea-185">Autentiseringstyp</span><span class="sxs-lookup"><span data-stu-id="f40ea-185">Authentication type</span></span> | <span data-ttu-id="f40ea-186">Office365</span><span class="sxs-lookup"><span data-stu-id="f40ea-186">Office365</span></span>
    <span data-ttu-id="f40ea-187">Användarnamn</span><span class="sxs-lookup"><span data-stu-id="f40ea-187">User name</span></span> |
    <span data-ttu-id="f40ea-188">Lösenord eller Azure-nyckelvalv</span><span class="sxs-lookup"><span data-stu-id="f40ea-188">Password or Azure Key Vault</span></span> | <span data-ttu-id="f40ea-189">Lösenord</span><span class="sxs-lookup"><span data-stu-id="f40ea-189">Password</span></span>
    <span data-ttu-id="f40ea-190">Lösenord</span><span class="sxs-lookup"><span data-stu-id="f40ea-190">Password</span></span> |

## <a name="run-the-template"></a><span data-ttu-id="f40ea-191">Kör mallen</span><span class="sxs-lookup"><span data-stu-id="f40ea-191">Run the template</span></span>

1. <span data-ttu-id="f40ea-192">Stoppa följande dubbelriktade mappningar för **Konto**, **Kontakt** och **Leverantör** med hjälp av Finance and Operations-programmet.</span><span class="sxs-lookup"><span data-stu-id="f40ea-192">Stop the following **Account**, **Contact**, and **Vendor** dual-write maps using the Finance and Operations app.</span></span>

    + <span data-ttu-id="f40ea-193">Kunder V3 (konton)</span><span class="sxs-lookup"><span data-stu-id="f40ea-193">Customers V3(accounts)</span></span>
    + <span data-ttu-id="f40ea-194">Kunder V3 (kontakter)</span><span class="sxs-lookup"><span data-stu-id="f40ea-194">Customers V3(contacts)</span></span>
    + <span data-ttu-id="f40ea-195">CDS-kontakter V2 (kontakter)</span><span class="sxs-lookup"><span data-stu-id="f40ea-195">CDS Contacts V2(contacts)</span></span>
    + <span data-ttu-id="f40ea-196">CDS-kontakter V2 (kontakter)</span><span class="sxs-lookup"><span data-stu-id="f40ea-196">CDS Contacts V2(contacts)</span></span>
    + <span data-ttu-id="f40ea-197">Leverantör V2 (msdyn_vendor)</span><span class="sxs-lookup"><span data-stu-id="f40ea-197">Vendor V2 (msdyn_vendor)</span></span>

2. <span data-ttu-id="f40ea-198">Kontrollera att kartorna har tagits bort från `msdy_dualwriteruntimeconfig`-registret i Dataverse.</span><span class="sxs-lookup"><span data-stu-id="f40ea-198">Make sure the maps are removed from the `msdy_dualwriteruntimeconfig` table in Dataverse.</span></span>

3. <span data-ttu-id="f40ea-199">Installera [lösningar för dubbel skrivningspart och global adressbok](https://aka.ms/dual-write-gab) från AppSource.</span><span class="sxs-lookup"><span data-stu-id="f40ea-199">Install [Dual-write Party and Global Address Book Solutions](https://aka.ms/dual-write-gab) from AppSource.</span></span>

4. <span data-ttu-id="f40ea-200">Om följande register innehåller data i Finance and Operations-programmet kör du sedan **Initial synkronisering** för dem.</span><span class="sxs-lookup"><span data-stu-id="f40ea-200">In the finance and operations app, if the following tables contain data, then run **Initial Sync** for them.</span></span>

    + <span data-ttu-id="f40ea-201">Tilltal</span><span class="sxs-lookup"><span data-stu-id="f40ea-201">Salutations</span></span>
    + <span data-ttu-id="f40ea-202">Typer av personliga egenskaper</span><span class="sxs-lookup"><span data-stu-id="f40ea-202">Personal character types</span></span>
    + <span data-ttu-id="f40ea-203">Avslutningsfras</span><span class="sxs-lookup"><span data-stu-id="f40ea-203">Complimentary closing</span></span>
    + <span data-ttu-id="f40ea-204">Kontaktpersonens titlar</span><span class="sxs-lookup"><span data-stu-id="f40ea-204">Contact person titles</span></span>
    + <span data-ttu-id="f40ea-205">Roller för beslutsfattare</span><span class="sxs-lookup"><span data-stu-id="f40ea-205">Decision making roles</span></span>
    + <span data-ttu-id="f40ea-206">Lojalitetsnivåer</span><span class="sxs-lookup"><span data-stu-id="f40ea-206">Loyalty levels</span></span>

5. <span data-ttu-id="f40ea-207">Inaktivera följande instickssteg i programmet för kundengagemang.</span><span class="sxs-lookup"><span data-stu-id="f40ea-207">In the customer engagement app, disable the following plug-in steps.</span></span>

    + <span data-ttu-id="f40ea-208">Kontouppdatering</span><span class="sxs-lookup"><span data-stu-id="f40ea-208">Account Update</span></span>
         + <span data-ttu-id="f40ea-209">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromAccountEntity: Kontouppdatering</span><span class="sxs-lookup"><span data-stu-id="f40ea-209">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromAccountEntity: Update of account</span></span>
         + <span data-ttu-id="f40ea-210">Microsoft.Dynamics.FinanceExtended.Plugins.TriggerNotesForCustomerTypeCodes: Kontouppdatering</span><span class="sxs-lookup"><span data-stu-id="f40ea-210">Microsoft.Dynamics.FinanceExtended.Plugins.TriggerNotesForCustomerTypeCodes: Update of account</span></span>
    + <span data-ttu-id="f40ea-211">Kontaktuppdatering</span><span class="sxs-lookup"><span data-stu-id="f40ea-211">Contact Update</span></span>
         + <span data-ttu-id="f40ea-212">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromContactEntity: Kontouppdatering</span><span class="sxs-lookup"><span data-stu-id="f40ea-212">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromContactEntity: Update of contact</span></span>
         + <span data-ttu-id="f40ea-213">Microsoft.Dynamics.FinanceExtended.Plugins.TriggerNotesForSellableContact: Kontouppdatering</span><span class="sxs-lookup"><span data-stu-id="f40ea-213">Microsoft.Dynamics.FinanceExtended.Plugins.TriggerNotesForSellableContact: Update of contact</span></span>
    + <span data-ttu-id="f40ea-214">Uppdatering av msdyn_party</span><span class="sxs-lookup"><span data-stu-id="f40ea-214">msdyn_party Update</span></span>
         + <span data-ttu-id="f40ea-215">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromPartyEntity: Uppdatering av msdyn_party</span><span class="sxs-lookup"><span data-stu-id="f40ea-215">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromPartyEntity: Update of msdyn_party</span></span>
    + <span data-ttu-id="f40ea-216">Uppdatering av msdyn_vendor</span><span class="sxs-lookup"><span data-stu-id="f40ea-216">msdyn_vendor Update</span></span>
         + <span data-ttu-id="f40ea-217">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromVendorEntity: Uppdatering av msdyn_vendor</span><span class="sxs-lookup"><span data-stu-id="f40ea-217">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromVendorEntity: Update of msdyn_vendor</span></span>

6. <span data-ttu-id="f40ea-218">Inaktivera följande arbetsflöden i programmet för kundengagemang:</span><span class="sxs-lookup"><span data-stu-id="f40ea-218">In the customer engagement app, disable the following workflows:</span></span>

    + <span data-ttu-id="f40ea-219">Skapa leverantörer i tabellen Konton</span><span class="sxs-lookup"><span data-stu-id="f40ea-219">Create Vendors in Accounts Table</span></span>
    + <span data-ttu-id="f40ea-220">Skapa leverantörer i tabellen Konton</span><span class="sxs-lookup"><span data-stu-id="f40ea-220">Create Vendors in Accounts Table</span></span>
    + <span data-ttu-id="f40ea-221">Skapa leverantörer av typen "person" i registret Kontakter</span><span class="sxs-lookup"><span data-stu-id="f40ea-221">Create Vendors of type person in Contacts Table</span></span>
    + <span data-ttu-id="f40ea-222">Skapa leverantörer av typen person i tabellen Leverantörer</span><span class="sxs-lookup"><span data-stu-id="f40ea-222">Create Vendors of type Person in Vendors Table</span></span>
    + <span data-ttu-id="f40ea-223">Uppdatera leverantörer i tabellen Konton</span><span class="sxs-lookup"><span data-stu-id="f40ea-223">Update Vendors in Accounts Table</span></span>
    + <span data-ttu-id="f40ea-224">Uppdatera leverantörer i tabellen Leverantörer</span><span class="sxs-lookup"><span data-stu-id="f40ea-224">Update Vendors in Vendors Table</span></span>
    + <span data-ttu-id="f40ea-225">Uppdatera leverantörer av typen person i tabellen Kontakter</span><span class="sxs-lookup"><span data-stu-id="f40ea-225">Update Vendors of type Person in Contacts Table</span></span>
    + <span data-ttu-id="f40ea-226">Uppdatera leverantörer av typen person i tabellen Leverantörer</span><span class="sxs-lookup"><span data-stu-id="f40ea-226">Update Vendors of type Person in Vendors Table</span></span>

7. <span data-ttu-id="f40ea-227">Kör mallen i datafabriken genom att välja **Utlösa nu** på det sätt som visas i bilden nedan.</span><span class="sxs-lookup"><span data-stu-id="f40ea-227">In the data factory, run the template by selecting **Trigger now** as shown in the following image.</span></span> <span data-ttu-id="f40ea-228">Denna process kan ta några timmar att slutföra baserat på datavolymen.</span><span class="sxs-lookup"><span data-stu-id="f40ea-228">This process might take a few hours to complete based on the data volume.</span></span>

    ![Utlösarkörning](media/data-factory-trigger.png)

    > [!NOTE]
    > <span data-ttu-id="f40ea-230">Om du har anpassningar för **Konto**, **Kontakt** och **Leverantör** måste du ändra mallen.</span><span class="sxs-lookup"><span data-stu-id="f40ea-230">If you have customizations for **Account**, **Contact**, and **Vendor**, then you need to modify the template.</span></span>

8. <span data-ttu-id="f40ea-231">Importera de nya **Part**-posterna i Finance and Operations-programmet.</span><span class="sxs-lookup"><span data-stu-id="f40ea-231">Import the new **Party** records in the Finance and Operations app.</span></span>

    + <span data-ttu-id="f40ea-232">Hämta filen `FONewParty.csv` från Azure blob-lagring.</span><span class="sxs-lookup"><span data-stu-id="f40ea-232">Download the `FONewParty.csv` file from Azure blob storage.</span></span> <span data-ttu-id="f40ea-233">Sökvägen är `partybootstrapping/output/FONewParty.csv`.</span><span class="sxs-lookup"><span data-stu-id="f40ea-233">The path is `partybootstrapping/output/FONewParty.csv`.</span></span>
    + <span data-ttu-id="f40ea-234">Konvertera filen `FONewParty.csv` till en Excel-fil och importera Excel-filen till Finance and Operations-programmet.</span><span class="sxs-lookup"><span data-stu-id="f40ea-234">Convert the `FONewParty.csv` file into an Excel file and import the Excel file into the finance and operations app.</span></span> <span data-ttu-id="f40ea-235">Om CSV-importen fungerar kan du importera CSV-filen direkt.</span><span class="sxs-lookup"><span data-stu-id="f40ea-235">If the csv import works for you, you can import the csv file directly.</span></span> <span data-ttu-id="f40ea-236">Importen kan ta ett par timmar att köra, beroende på datavolymen.</span><span class="sxs-lookup"><span data-stu-id="f40ea-236">The import could take a few hours to run, depending on the data volume.</span></span> <span data-ttu-id="f40ea-237">Mer information finns i [Översikt över dataimport- och exportjobb](../data-import-export-job.md).</span><span class="sxs-lookup"><span data-stu-id="f40ea-237">For more information, see [Data import and export jobs overview](../data-import-export-job.md).</span></span>

    ![Importera poster för Datavers-parten](media/data-factory-import-party.png)

9. <span data-ttu-id="f40ea-239">Aktivera följande instickssteg i programmet för kundengagemang:</span><span class="sxs-lookup"><span data-stu-id="f40ea-239">In the customer engagement apps, enable the following plug-in steps:</span></span>

    + <span data-ttu-id="f40ea-240">Kontouppdatering</span><span class="sxs-lookup"><span data-stu-id="f40ea-240">Account Update</span></span>
         + <span data-ttu-id="f40ea-241">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromAccountEntity: Kontouppdatering</span><span class="sxs-lookup"><span data-stu-id="f40ea-241">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromAccountEntity: Update of account</span></span>
         + <span data-ttu-id="f40ea-242">Microsoft.Dynamics.FinanceExtended.Plugins.TriggerNotesForCustomerTypeCodes: Kontouppdatering</span><span class="sxs-lookup"><span data-stu-id="f40ea-242">Microsoft.Dynamics.FinanceExtended.Plugins.TriggerNotesForCustomerTypeCodes: Update of account</span></span>
    + <span data-ttu-id="f40ea-243">Kontaktuppdatering</span><span class="sxs-lookup"><span data-stu-id="f40ea-243">Contact Update</span></span>
         + <span data-ttu-id="f40ea-244">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromContactEntity: Kontouppdatering</span><span class="sxs-lookup"><span data-stu-id="f40ea-244">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromContactEntity: Update of contact</span></span>
         + <span data-ttu-id="f40ea-245">Microsoft.Dynamics.FinanceExtended.Plugins.TriggerNotesForSellableContact: Kontouppdatering</span><span class="sxs-lookup"><span data-stu-id="f40ea-245">Microsoft.Dynamics.FinanceExtended.Plugins.TriggerNotesForSellableContact: Update of contact</span></span>
    + <span data-ttu-id="f40ea-246">Uppdatering av msdyn_party</span><span class="sxs-lookup"><span data-stu-id="f40ea-246">msdyn_party Update</span></span>
         + <span data-ttu-id="f40ea-247">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromPartyEntity: Uppdatering av msdyn_party</span><span class="sxs-lookup"><span data-stu-id="f40ea-247">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromPartyEntity: Update of msdyn_party</span></span>
    + <span data-ttu-id="f40ea-248">Uppdatering av msdyn_vendor</span><span class="sxs-lookup"><span data-stu-id="f40ea-248">msdyn_vendor Update</span></span>
         + <span data-ttu-id="f40ea-249">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromVendorEntity: Uppdatering av msdyn_vendor</span><span class="sxs-lookup"><span data-stu-id="f40ea-249">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromVendorEntity: Update of msdyn_vendor</span></span>

10. <span data-ttu-id="f40ea-250">Aktivera följande arbetsflöden i kundkopplingsprogrammen om du inaktiverat dem i föregående steg:</span><span class="sxs-lookup"><span data-stu-id="f40ea-250">In the customer engagement apps, activate the following workflows if you deactivated them in previous steps:</span></span>

    + <span data-ttu-id="f40ea-251">Skapa leverantörer i tabellen Konton</span><span class="sxs-lookup"><span data-stu-id="f40ea-251">Create Vendors in Accounts Table</span></span>
    + <span data-ttu-id="f40ea-252">Skapa leverantörer i tabellen Konton</span><span class="sxs-lookup"><span data-stu-id="f40ea-252">Create Vendors in Accounts Table</span></span>
    + <span data-ttu-id="f40ea-253">Skapa leverantörer av typen "person" i registret Kontakter</span><span class="sxs-lookup"><span data-stu-id="f40ea-253">Create Vendors of type person in Contacts Table</span></span>
    + <span data-ttu-id="f40ea-254">Skapa leverantörer av typen person i tabellen Leverantörer</span><span class="sxs-lookup"><span data-stu-id="f40ea-254">Create Vendors of type Person in Vendors Table</span></span>
    + <span data-ttu-id="f40ea-255">Uppdatera leverantörer i tabellen Konton</span><span class="sxs-lookup"><span data-stu-id="f40ea-255">Update Vendors in Accounts Table</span></span>
    + <span data-ttu-id="f40ea-256">Uppdatera leverantörer i tabellen Leverantörer</span><span class="sxs-lookup"><span data-stu-id="f40ea-256">Update Vendors in Vendors Table</span></span>
    + <span data-ttu-id="f40ea-257">Uppdatera leverantörer av typen person i tabellen Kontakter</span><span class="sxs-lookup"><span data-stu-id="f40ea-257">Update Vendors of type Person in Contacts Table</span></span>
    + <span data-ttu-id="f40ea-258">Uppdatera leverantörer av typen person i tabellen Leverantörer</span><span class="sxs-lookup"><span data-stu-id="f40ea-258">Update Vendors of type Person in Vendors Table</span></span>

11. <span data-ttu-id="f40ea-259">Kör de **part** relaterade kartorna enligt instruktionerna i [Part och global adressbok](party-gab.md).</span><span class="sxs-lookup"><span data-stu-id="f40ea-259">Run the **Party**-related maps as instructed in [Party and global address book](party-gab.md).</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="f40ea-260">Felsökning</span><span class="sxs-lookup"><span data-stu-id="f40ea-260">Troubleshooting</span></span>

1. <span data-ttu-id="f40ea-261">Om processen misslyckas kör du datafabriken igen, med början från den misslyckade aktiviteten.</span><span class="sxs-lookup"><span data-stu-id="f40ea-261">If the process fails, rerun the data factory starting from the failed activity.</span></span>
2. <span data-ttu-id="f40ea-262">Vissa filer genereras av den datafabrik som du kan använda för datavalidering.</span><span class="sxs-lookup"><span data-stu-id="f40ea-262">Some files are generated by the data factory that you can use for data validation purpose.</span></span>
3. <span data-ttu-id="f40ea-263">Datafabriken körs baserat på CSV-filer som är kommaavgränsade.</span><span class="sxs-lookup"><span data-stu-id="f40ea-263">The data factory runs based on csv files that are comma-delimited.</span></span> <span data-ttu-id="f40ea-264">Om det finns ett fältvärde med ett kommatecken kan detta komma att störa resultaten.</span><span class="sxs-lookup"><span data-stu-id="f40ea-264">If there is a field value that has a comma, it may interfere with the results.</span></span> <span data-ttu-id="f40ea-265">Du måste ta bort kommatecknen.</span><span class="sxs-lookup"><span data-stu-id="f40ea-265">You need to remove the commas.</span></span>
4. <span data-ttu-id="f40ea-266">På fliken **Övervakning** finns information om alla steg och data som bearbetas.</span><span class="sxs-lookup"><span data-stu-id="f40ea-266">The **Monitoring** tab provides information about all steps and data processed.</span></span> <span data-ttu-id="f40ea-267">Välj ett specifikt steg för att felsöka det.</span><span class="sxs-lookup"><span data-stu-id="f40ea-267">Select a specific step to debug it.</span></span>

    ![Fliken Övervakning](media/data-factory-monitor.png)

## <a name="learn-more-about-the-template"></a><span data-ttu-id="f40ea-269">Läs mer om mallen</span><span class="sxs-lookup"><span data-stu-id="f40ea-269">Learn more about the template</span></span>

<span data-ttu-id="f40ea-270">Mer information om mallen finns i [Kommentarer för Azure Data Factory-mallen readme](https://github.com/microsoft/Dynamics-365-FastTrack-Implementation-Assets/blob/master/Dual-write/Upgrade%20data%20to%20dual-write%20Party-GAB%20schema/readme.md).</span><span class="sxs-lookup"><span data-stu-id="f40ea-270">You can find additional information about the template in [Comments for Azure Data Factory template readme](https://github.com/microsoft/Dynamics-365-FastTrack-Implementation-Assets/blob/master/Dual-write/Upgrade%20data%20to%20dual-write%20Party-GAB%20schema/readme.md).</span></span>
