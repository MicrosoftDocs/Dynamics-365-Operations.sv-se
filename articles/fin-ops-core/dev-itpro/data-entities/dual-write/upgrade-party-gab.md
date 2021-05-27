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
ms.openlocfilehash: 95472a00d34ba939ac89b4e2484f34d50bee3088
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/11/2021
ms.locfileid: "6018322"
---
# <a name="upgrade-to-the-party-and-global-address-book-model"></a><span data-ttu-id="69431-103">Uppgradera till part- och globala adressboksmodellen.</span><span class="sxs-lookup"><span data-stu-id="69431-103">Upgrade to the party and global address book model</span></span>

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="69431-104">Mallen [Azure Data Factory](https://aka.ms/dual-write-gab-adf) hjälper dig att uppgradera befintliga registerdata för dubbel skrivning för **Konto**, **Kontakt** och **Leverantör** till parten samt till den globala adressboksmodellen.</span><span class="sxs-lookup"><span data-stu-id="69431-104">The [Azure Data Factory template](https://aka.ms/dual-write-gab-adf) helps you upgrade existing **Account**, **Contact**, and **Vendor** table data in dual-write to the party and global address book model.</span></span> <span data-ttu-id="69431-105">I mallen stäms data från både Finance and Operations-program och program för kundrelationer av.</span><span class="sxs-lookup"><span data-stu-id="69431-105">The template reconciles the data from both Finance and Operations apps and customer engagement applications.</span></span> <span data-ttu-id="69431-106">I slutet av processen skapas fälten **Part** och **Kontakt** för **Part**-poster, som sedan associeras med poster för **Konto**, **Kontakt** och **Leverantör** i program för kundengagemang.</span><span class="sxs-lookup"><span data-stu-id="69431-106">At the end of the process, **Party** and **Contact** fields for **Party** records will be created and associated with **Account**, **Contact**, and **Vendor** records in customer engagement applications.</span></span> <span data-ttu-id="69431-107">En .csv-fil ( `FONewParty.csv`) genereras för att skapa nya **Part**-poster inuti Finance and Operations-programmet.</span><span class="sxs-lookup"><span data-stu-id="69431-107">A .csv file (`FONewParty.csv`) is generated to create new **Party** records inside the Finance and Operations app.</span></span> <span data-ttu-id="69431-108">I detta ämne finns instruktioner om hur du använder Data Factory-mallen och uppgraderar dina data.</span><span class="sxs-lookup"><span data-stu-id="69431-108">This topic provides the instructions to use the Data Factory template and upgrade your data.</span></span>

<span data-ttu-id="69431-109">Om du inte har några anpassningar kan du använda mallen som den är.</span><span class="sxs-lookup"><span data-stu-id="69431-109">If you don’t have any customizations, you can use the template as-is.</span></span> <span data-ttu-id="69431-110">Om du har anpassningar för **Konto**, **Kontakt** och **Leverantör** måste du ändra mallen med hjälp av följande instruktioner.</span><span class="sxs-lookup"><span data-stu-id="69431-110">If you have customizations for **Account**, **Contact**, and **Vendor** then you must modify the template using the following instructions.</span></span>

> [!Note]
> <span data-ttu-id="69431-111">Mallen underlättar uppgraderingen av endast **Partsdata**.</span><span class="sxs-lookup"><span data-stu-id="69431-111">The template helps to upgrade only the **Party** data.</span></span> <span data-ttu-id="69431-112">I en framtida version inkluderas postnummer och elektroniska adresser.</span><span class="sxs-lookup"><span data-stu-id="69431-112">In a future release, postal and electronic addresses will be included.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="69431-113">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="69431-113">Prerequisites</span></span>

<span data-ttu-id="69431-114">Följande förutsättningar krävs:</span><span class="sxs-lookup"><span data-stu-id="69431-114">These prerequisites are required:</span></span>

+ [<span data-ttu-id="69431-115">Azure-abonnemang</span><span class="sxs-lookup"><span data-stu-id="69431-115">Azure subscription</span></span>](https://portal.azure.com/)
+ [<span data-ttu-id="69431-116">Åtkomst till mallen</span><span class="sxs-lookup"><span data-stu-id="69431-116">Access to the template</span></span>](https://aka.ms/dual-write-gab-adf)
+ <span data-ttu-id="69431-117">Du är en befintlig kund.</span><span class="sxs-lookup"><span data-stu-id="69431-117">You are an existing dual-write customer.</span></span>

## <a name="prepare-for-the-upgrade"></a><span data-ttu-id="69431-118">Förbereda uppgraderinge</span><span class="sxs-lookup"><span data-stu-id="69431-118">Prepare for the upgrade</span></span>

+ <span data-ttu-id="69431-119">**Fullt synkroniserat**: Båda miljöerna är helt synkroniserade för **Konto (kund)**, **Kontakt** och **Leverantör**.</span><span class="sxs-lookup"><span data-stu-id="69431-119">**Fully synched**: Both environments are fully synched state for **Account (Customer)**, **Contact**, and **Vendor**.</span></span>
+ <span data-ttu-id="69431-120">**Integreringsnycklar**: Registren **Konto (Kund)**, **Kontakt** och **Leverantör** i program för kundengagemang använder de integreringsnycklar som levererades färdiga.</span><span class="sxs-lookup"><span data-stu-id="69431-120">**Integration keys**: **Account (Customer)**, **Contact**, and **Vendor** tables in customer engagement apps are using the integration keys that shipped out-of-the-box.</span></span> <span data-ttu-id="69431-121">Om du anpassar integreringsnycklarna måste du anpassa mallen.</span><span class="sxs-lookup"><span data-stu-id="69431-121">If you customized the integration keys, you must customize the template.</span></span>
+ <span data-ttu-id="69431-122">**Partsnummer**: Alla **Kontro (kund)-**, **Kontakt-** och **Leverantörs** poster som ska uppgraderas har ett **Parts** nummer.</span><span class="sxs-lookup"><span data-stu-id="69431-122">**Party number**: All **Account (Customer)**, **Contact**, and **Vendor** records that will be upgraded have a **Party** number.</span></span> <span data-ttu-id="69431-123">Poster utan ett **Parts** nummer ignoreras.</span><span class="sxs-lookup"><span data-stu-id="69431-123">Records without a **Party** number will be ignored.</span></span> <span data-ttu-id="69431-124">Om du vill uppgradera dessa poster lägger du till ett **Parts** nummer i dem innan du startar uppgraderingsprocessen.</span><span class="sxs-lookup"><span data-stu-id="69431-124">If you want to upgrade those records, add a **Party** number to them before you start the upgrade process.</span></span>
+ <span data-ttu-id="69431-125">**Systemavbrott**: Under uppgraderingen måste du ta både Finance and Operations-miljön och miljön för kundengagemang offline.</span><span class="sxs-lookup"><span data-stu-id="69431-125">**System outage**: During the upgrade process, you will have to take both the Finance and Operations and customer engagement environments offline.</span></span>
+ <span data-ttu-id="69431-126">**Ögonblicksbild**: Ta ögonblicksbilder av både Finance and Operations-appen och appen för kundengagemang.</span><span class="sxs-lookup"><span data-stu-id="69431-126">**Snapshot**: Take snapshots of both the Finance and Operations and customer engagement apps.</span></span> <span data-ttu-id="69431-127">Använd ögonblicksbilderna om du vill återställa föregående status vid behov.</span><span class="sxs-lookup"><span data-stu-id="69431-127">Use the snapshots to restore the previous state if you need to.</span></span>

## <a name="deployment"></a><span data-ttu-id="69431-128">Distribution</span><span class="sxs-lookup"><span data-stu-id="69431-128">Deployment</span></span>

1. <span data-ttu-id="69431-129">Hämta mallen från [Implementeringstillgångar för Dynamics-365-FastTrack](https://aka.ms/dual-write-gab-adf)</span><span class="sxs-lookup"><span data-stu-id="69431-129">Download the template from [Dynamics-365-FastTrack-Implementation-Assets](https://aka.ms/dual-write-gab-adf).</span></span>

2. <span data-ttu-id="69431-130">Logga in på [Microsoft Azure](https://portal.azure.com/).</span><span class="sxs-lookup"><span data-stu-id="69431-130">Sign in to [Microsoft Azure](https://portal.azure.com/).</span></span>

3. <span data-ttu-id="69431-131">Skapa en [resursgrupp](/azure/azure-resource-manager/management/manage-resource-groups-portal).</span><span class="sxs-lookup"><span data-stu-id="69431-131">Create a [resource group](/azure/azure-resource-manager/management/manage-resource-groups-portal).</span></span>

4. <span data-ttu-id="69431-132">Skapa ett [lagringskonto](/azure/storage/common/storage-account-create?tabs=azure-portal) i resursgruppen som du skapade.</span><span class="sxs-lookup"><span data-stu-id="69431-132">Create a [storage account](/azure/storage/common/storage-account-create?tabs=azure-portal) in the resource group that you created.</span></span>

5. <span data-ttu-id="69431-133">Skapa en [datafabrik](/azure/data-factory/quickstart-create-data-factory-portal) i resursgruppen som du skapade ovan.</span><span class="sxs-lookup"><span data-stu-id="69431-133">Create a [data factory](/azure/data-factory/quickstart-create-data-factory-portal) in above resource group that you created.</span></span>

6. <span data-ttu-id="69431-134">Öppna datafabriken och välj panelen **Skapa och övervaka**.</span><span class="sxs-lookup"><span data-stu-id="69431-134">Open the data factory and select the **Author & Monitor** tile.</span></span>

7. <span data-ttu-id="69431-135">På fliken **Hantera** väljer du **ARM-mall**.</span><span class="sxs-lookup"><span data-stu-id="69431-135">On the **Manage** tab, select **ARM template**.</span></span>

8. <span data-ttu-id="69431-136">Välj **Importera ARM-mall** för att importera mallen **Part**.</span><span class="sxs-lookup"><span data-stu-id="69431-136">Select the **Import ARM template** to import the **Party** template.</span></span>

9. <span data-ttu-id="69431-137">Importera mallen till datafabriken.</span><span class="sxs-lookup"><span data-stu-id="69431-137">Import the template into the data factory.</span></span> <span data-ttu-id="69431-138">Ange följande värden för **Projektinformation** och **Instansinformation**.</span><span class="sxs-lookup"><span data-stu-id="69431-138">Enter the following values for **Project details** and **Instance details**.</span></span>

    <span data-ttu-id="69431-139">Fält</span><span class="sxs-lookup"><span data-stu-id="69431-139">Field</span></span> | <span data-ttu-id="69431-140">Värde</span><span class="sxs-lookup"><span data-stu-id="69431-140">Value</span></span>
    ---|---
    <span data-ttu-id="69431-141">Abonnemang</span><span class="sxs-lookup"><span data-stu-id="69431-141">Subscription</span></span> | <span data-ttu-id="69431-142">Azure-abonnemang</span><span class="sxs-lookup"><span data-stu-id="69431-142">Azure subscription</span></span>
    <span data-ttu-id="69431-143">Resursgrupp</span><span class="sxs-lookup"><span data-stu-id="69431-143">Resource group</span></span> | <span data-ttu-id="69431-144">Ange samma resurs under vilken lagringskontot skapas.</span><span class="sxs-lookup"><span data-stu-id="69431-144">Provide same resource under which storage account is created.</span></span>
    <span data-ttu-id="69431-145">Region</span><span class="sxs-lookup"><span data-stu-id="69431-145">Region</span></span> | <span data-ttu-id="69431-146">Ange region.</span><span class="sxs-lookup"><span data-stu-id="69431-146">Specify region.</span></span>
    <span data-ttu-id="69431-147">Fabriksnamn</span><span class="sxs-lookup"><span data-stu-id="69431-147">Factory Name</span></span> | <span data-ttu-id="69431-148">Ange fabriksnamn.</span><span class="sxs-lookup"><span data-stu-id="69431-148">Specify factory name.</span></span>
    <span data-ttu-id="69431-149">Huvudservicenyckel för kopplad FO-service</span><span class="sxs-lookup"><span data-stu-id="69431-149">FO Linked Service_service Principal Key</span></span> | <span data-ttu-id="69431-150">Ange nyckeln för ansökan</span><span class="sxs-lookup"><span data-stu-id="69431-150">Specify the application's key.</span></span>
    <span data-ttu-id="69431-151">Anslutningssträng för Azure Blob Storage</span><span class="sxs-lookup"><span data-stu-id="69431-151">Azure Blob Storage_connection String</span></span> | <span data-ttu-id="69431-152">Anslutningssträng för Azure Blob-lagring.</span><span class="sxs-lookup"><span data-stu-id="69431-152">Azure Blob storage connection string.</span></span>
    <span data-ttu-id="69431-153">Kopplat tjänstelösenord för Dynamics Crm</span><span class="sxs-lookup"><span data-stu-id="69431-153">Dynamics Crm Linked Service_password</span></span> | <span data-ttu-id="69431-154">Lösenordet för det användarkonto du angett som användarnamn.</span><span class="sxs-lookup"><span data-stu-id="69431-154">The password for the user account you specified as the username.</span></span>
    <span data-ttu-id="69431-155">FO Linked Service_properties_type Properties_url</span><span class="sxs-lookup"><span data-stu-id="69431-155">FO Linked Service_properties_type Properties_url</span></span>  | `https://sampledynamics.sandbox-operationsdynamics.com/data`
    <span data-ttu-id="69431-156">FO Linked Service_properties_type Properties_tenant</span><span class="sxs-lookup"><span data-stu-id="69431-156">FO Linked Service_properties_type Properties_tenant</span></span> | <span data-ttu-id="69431-157">Ange information om klientorganisation (domännamn eller ID för klientorganisation) under vilket programmet finns.</span><span class="sxs-lookup"><span data-stu-id="69431-157">Specify the tenant information (domain name or tenant ID) under which your application resides.</span></span>
    <span data-ttu-id="69431-158">FO Linked Service_properties_type Properties_aad Resource Id</span><span class="sxs-lookup"><span data-stu-id="69431-158">FO Linked Service_properties_type Properties_aad Resource Id</span></span> | `https://sampledynamics.sandboxoperationsdynamics.com`
    <span data-ttu-id="69431-159">FO Linked Service_properties_type Properties_service Principal Id</span><span class="sxs-lookup"><span data-stu-id="69431-159">FO Linked Service_properties_type Properties_service Principal Id</span></span> | <span data-ttu-id="69431-160">Ange programmets klient-ID.</span><span class="sxs-lookup"><span data-stu-id="69431-160">Specify the application's client ID.</span></span>
    <span data-ttu-id="69431-161">Dynamics Crm Linked Service_properties_type Properties_username</span><span class="sxs-lookup"><span data-stu-id="69431-161">Dynamics Crm Linked Service_properties_type Properties_username</span></span> | <span data-ttu-id="69431-162">Användarnamnet som ska kopplas till Dynamics.</span><span class="sxs-lookup"><span data-stu-id="69431-162">The username to connect to Dynamics.</span></span>

    <span data-ttu-id="69431-163">Mer information finns i [Flytta upp en Resource Manager-mall för respektive miljö manuellt](/azure/data-factory/continuous-integration-deployment#manually-promote-a-resource-manager-template-for-each-environment), [Kopplade tjänsteegenskaper](/azure/data-factory/connector-dynamics-ax#linked-service-properties) samt [Kopiera data med hjälp av Azure Data Factory](/azure/data-factory/connector-dynamics-crm-office-365#dynamics-365-and-dynamics-crm-online)</span><span class="sxs-lookup"><span data-stu-id="69431-163">For more information, see [Manually promote a Resource Manager template for each environment](/azure/data-factory/continuous-integration-deployment#manually-promote-a-resource-manager-template-for-each-environment), [Linked service properties](/azure/data-factory/connector-dynamics-ax#linked-service-properties), and [Copy data using Azure Data Factory](/azure/data-factory/connector-dynamics-crm-office-365#dynamics-365-and-dynamics-crm-online)</span></span>

10. <span data-ttu-id="69431-164">Efter distributionen kan du validera datauppsättningarna, dataflödet och länkad tjänst för datafabriken.</span><span class="sxs-lookup"><span data-stu-id="69431-164">After deployment, validate the datasets, data flow, and linked service of the data factory.</span></span>

   ![Datauppsättningar, dataflöde och länkad tjänst](media/data-factory-validate.png)

11. <span data-ttu-id="69431-166">Navigera till **Hantera**.</span><span class="sxs-lookup"><span data-stu-id="69431-166">Navigate to **Manage**.</span></span> <span data-ttu-id="69431-167">Under **Anslutningar** väljer du **Kopplad tjänst**.</span><span class="sxs-lookup"><span data-stu-id="69431-167">Under **Connections**, select **Linked Service**.</span></span> <span data-ttu-id="69431-168">Välj **DynamicsCrmLinkedService**.</span><span class="sxs-lookup"><span data-stu-id="69431-168">Select **DynamicsCrmLinkedService**.</span></span> <span data-ttu-id="69431-169">Ange följande värden i formuläret **Redigera kopplad tjänst (Dynamics CRM)**:</span><span class="sxs-lookup"><span data-stu-id="69431-169">In the **Edit linked service (Dynamics CRM)** form, enter the following values:</span></span>

    <span data-ttu-id="69431-170">Fält</span><span class="sxs-lookup"><span data-stu-id="69431-170">Field</span></span> | <span data-ttu-id="69431-171">Värde</span><span class="sxs-lookup"><span data-stu-id="69431-171">Value</span></span>
    ---|---
    <span data-ttu-id="69431-172">Namn</span><span class="sxs-lookup"><span data-stu-id="69431-172">Name</span></span> | <span data-ttu-id="69431-173">DynamicsCrmLinkedService</span><span class="sxs-lookup"><span data-stu-id="69431-173">DynamicsCrmLinkedService</span></span>
    <span data-ttu-id="69431-174">beskrivning</span><span class="sxs-lookup"><span data-stu-id="69431-174">Description</span></span> | <span data-ttu-id="69431-175">Kopplade tjänster för anslutning med CRM-instans för hämtning av entitetsdata</span><span class="sxs-lookup"><span data-stu-id="69431-175">Linked services to connect with CRM instance to fetch entities data</span></span>
    <span data-ttu-id="69431-176">Anslut via integreringskörning</span><span class="sxs-lookup"><span data-stu-id="69431-176">Connect via integration runtime</span></span> | <span data-ttu-id="69431-177">AutoResolvelntegrationRuntime</span><span class="sxs-lookup"><span data-stu-id="69431-177">AutoResolvelntegrationRuntime</span></span>
    <span data-ttu-id="69431-178">Distributionstyp</span><span class="sxs-lookup"><span data-stu-id="69431-178">Deployment type</span></span> | <span data-ttu-id="69431-179">Online</span><span class="sxs-lookup"><span data-stu-id="69431-179">Online</span></span>
    <span data-ttu-id="69431-180">Service-Uri</span><span class="sxs-lookup"><span data-stu-id="69431-180">Service Uri</span></span> | `https://<organization-name>.crm[x].dynamics.com`
    <span data-ttu-id="69431-181">Autentiseringstyp</span><span class="sxs-lookup"><span data-stu-id="69431-181">Authentication type</span></span> | <span data-ttu-id="69431-182">Office365</span><span class="sxs-lookup"><span data-stu-id="69431-182">Office365</span></span>
    <span data-ttu-id="69431-183">Användarnamn</span><span class="sxs-lookup"><span data-stu-id="69431-183">User name</span></span> |
    <span data-ttu-id="69431-184">Lösenord eller Azure-nyckelvalv</span><span class="sxs-lookup"><span data-stu-id="69431-184">Password or Azure Key Vault</span></span> | <span data-ttu-id="69431-185">Lösenord</span><span class="sxs-lookup"><span data-stu-id="69431-185">Password</span></span>
    <span data-ttu-id="69431-186">Lösenord</span><span class="sxs-lookup"><span data-stu-id="69431-186">Password</span></span> |

## <a name="run-the-template"></a><span data-ttu-id="69431-187">Kör mallen</span><span class="sxs-lookup"><span data-stu-id="69431-187">Run the template</span></span>

1. <span data-ttu-id="69431-188">Stoppa följande dubbelskrivning för **Konto**, **Kontakt** och **Leverantör** med hjälp av Finance and Operations-programmet.</span><span class="sxs-lookup"><span data-stu-id="69431-188">Stop the following **Account**, **Contact**, and **Vendor** dual-write using the Finance and Operations app.</span></span>

    + <span data-ttu-id="69431-189">Kunder V3 (konton)</span><span class="sxs-lookup"><span data-stu-id="69431-189">Customers V3(accounts)</span></span>
    + <span data-ttu-id="69431-190">Kunder V3 (kontakter)</span><span class="sxs-lookup"><span data-stu-id="69431-190">Customers V3(contacts)</span></span>
    + <span data-ttu-id="69431-191">CDS-kontakter V2 (kontakter)</span><span class="sxs-lookup"><span data-stu-id="69431-191">CDS Contacts V2(contacts)</span></span>
    + <span data-ttu-id="69431-192">CDS-kontakter V2 (kontakter)</span><span class="sxs-lookup"><span data-stu-id="69431-192">CDS Contacts V2(contacts)</span></span>
    + <span data-ttu-id="69431-193">Leverantör V2 (msdyn_vendor)</span><span class="sxs-lookup"><span data-stu-id="69431-193">Vendor V2 (msdyn_vendor)</span></span>

2. <span data-ttu-id="69431-194">Kontrollera att kartorna har tagits bort från `msdy_dualwriteruntimeconfig`-registret i Dataverse.</span><span class="sxs-lookup"><span data-stu-id="69431-194">Make sure the maps are removed from the `msdy_dualwriteruntimeconfig` table in Dataverse.</span></span>

3. <span data-ttu-id="69431-195">Installera [lösningar för dubbel skrivningspart och global adressbok](https://aka.ms/dual-write-gab) från AppSource.</span><span class="sxs-lookup"><span data-stu-id="69431-195">Install [Dual-write Party and Global Address Book Solutions](https://aka.ms/dual-write-gab) from AppSource.</span></span>

4. <span data-ttu-id="69431-196">Om följande register innehåller data i Finance and Operations-programmet kör du sedan **Initial synkronisering** för dem.</span><span class="sxs-lookup"><span data-stu-id="69431-196">In the Finance and Operations app, if the following tables contain data, then run **Initial Sync** for them.</span></span>

    + <span data-ttu-id="69431-197">Tilltal</span><span class="sxs-lookup"><span data-stu-id="69431-197">Salutations</span></span>
    + <span data-ttu-id="69431-198">Typer av personliga egenskaper</span><span class="sxs-lookup"><span data-stu-id="69431-198">Personal character types</span></span>
    + <span data-ttu-id="69431-199">Avslutningsfras</span><span class="sxs-lookup"><span data-stu-id="69431-199">Complimentary closing</span></span>
    + <span data-ttu-id="69431-200">Kontaktpersonens titlar</span><span class="sxs-lookup"><span data-stu-id="69431-200">Contact person titles</span></span>
    + <span data-ttu-id="69431-201">Roller för beslutsfattare</span><span class="sxs-lookup"><span data-stu-id="69431-201">Decision making roles</span></span>
    + <span data-ttu-id="69431-202">Lojalitetsnivåer</span><span class="sxs-lookup"><span data-stu-id="69431-202">Loyalty levels</span></span>

5. <span data-ttu-id="69431-203">Inaktivera följande instickssteg i programmet för kundengagemang.</span><span class="sxs-lookup"><span data-stu-id="69431-203">In the customer engagement app, disable the following plugin steps.</span></span>

    + <span data-ttu-id="69431-204">Kontouppdatering</span><span class="sxs-lookup"><span data-stu-id="69431-204">Account Update</span></span>
         + <span data-ttu-id="69431-205">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromAccountEntity: Kontouppdatering</span><span class="sxs-lookup"><span data-stu-id="69431-205">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromAccountEntity: Update of account</span></span>
         + <span data-ttu-id="69431-206">Microsoft.Dynamics.FinanceExtended.Plugins.TriggerNotesForCustomerTypeCodes: Kontouppdatering</span><span class="sxs-lookup"><span data-stu-id="69431-206">Microsoft.Dynamics.FinanceExtended.Plugins.TriggerNotesForCustomerTypeCodes: Update of account</span></span>
    + <span data-ttu-id="69431-207">Kontaktuppdatering</span><span class="sxs-lookup"><span data-stu-id="69431-207">Contact Update</span></span>
         + <span data-ttu-id="69431-208">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromContactEntity: Kontouppdatering</span><span class="sxs-lookup"><span data-stu-id="69431-208">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromContactEntity: Update of contact</span></span>
         + <span data-ttu-id="69431-209">Microsoft.Dynamics.FinanceExtended.Plugins.TriggerNotesForSellableContact: Kontouppdatering</span><span class="sxs-lookup"><span data-stu-id="69431-209">Microsoft.Dynamics.FinanceExtended.Plugins.TriggerNotesForSellableContact: Update of contact</span></span>
    + <span data-ttu-id="69431-210">Uppdatering av msdyn_party</span><span class="sxs-lookup"><span data-stu-id="69431-210">msdyn_party Update</span></span>
         + <span data-ttu-id="69431-211">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromPartyEntity: Uppdatering av msdyn_party</span><span class="sxs-lookup"><span data-stu-id="69431-211">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromPartyEntity: Update of msdyn_party</span></span>
    + <span data-ttu-id="69431-212">Uppdatering av msdyn_vendor</span><span class="sxs-lookup"><span data-stu-id="69431-212">msdyn_vendor Update</span></span>
         + <span data-ttu-id="69431-213">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromVendorEntity: Uppdatering av msdyn_vendor</span><span class="sxs-lookup"><span data-stu-id="69431-213">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromVendorEntity: Update of msdyn_vendor</span></span>

6. <span data-ttu-id="69431-214">Inaktivera följande arbetsflöden i programmet för kundengagemang:</span><span class="sxs-lookup"><span data-stu-id="69431-214">In the customer engagement app, disable the following workflows:</span></span>

    + <span data-ttu-id="69431-215">Skapa leverantörer i tabellen Konton</span><span class="sxs-lookup"><span data-stu-id="69431-215">Create Vendors in Accounts Table</span></span>
    + <span data-ttu-id="69431-216">Skapa leverantörer i tabellen Konton</span><span class="sxs-lookup"><span data-stu-id="69431-216">Create Vendors in Accounts Table</span></span>
    + <span data-ttu-id="69431-217">Skapa leverantörer av typen "person" i registret Kontakter</span><span class="sxs-lookup"><span data-stu-id="69431-217">Create Vendors of type person in Contacts Table</span></span>
    + <span data-ttu-id="69431-218">Skapa leverantörer av typen person i tabellen Leverantörer</span><span class="sxs-lookup"><span data-stu-id="69431-218">Create Vendors of type Person in Vendors Table</span></span>
    + <span data-ttu-id="69431-219">Uppdatera leverantörer i tabellen Konton</span><span class="sxs-lookup"><span data-stu-id="69431-219">Update Vendors in Accounts Table</span></span>
    + <span data-ttu-id="69431-220">Uppdatera leverantörer i tabellen Leverantörer</span><span class="sxs-lookup"><span data-stu-id="69431-220">Update Vendors in Vendors Table</span></span>
    + <span data-ttu-id="69431-221">Uppdatera leverantörer av typen person i tabellen Kontakter</span><span class="sxs-lookup"><span data-stu-id="69431-221">Update Vendors of type Person in Contacts Table</span></span>
    + <span data-ttu-id="69431-222">Uppdatera leverantörer av typen person i tabellen Leverantörer</span><span class="sxs-lookup"><span data-stu-id="69431-222">Update Vendors of type Person in Vendors Table</span></span>

7. <span data-ttu-id="69431-223">Kör mallen i datafabriken genom att välja **Utlösa nu** på det sätt som visas i bilden nedan.</span><span class="sxs-lookup"><span data-stu-id="69431-223">In the data factory, run the template by selecting **Trigger now** as shown in the following image.</span></span> <span data-ttu-id="69431-224">Denna process kan ta några timmar att slutföra baserat på datavolymen.</span><span class="sxs-lookup"><span data-stu-id="69431-224">This process might take a few hours to complete based on the data volume.</span></span>

    ![Utlösarkörning](media/data-factory-trigger.png)

    > [!NOTE]
    > <span data-ttu-id="69431-226">Om du har anpassningar för **Konto**, **Kontakt** och **Leverantör** måste du ändra mallen.</span><span class="sxs-lookup"><span data-stu-id="69431-226">If you have customizations for **Account**, **Contact**, and **Vendor** then you must modify the template.</span></span>

8. <span data-ttu-id="69431-227">Importera de nya **Part**-posterna i Finance and Operations-programmet.</span><span class="sxs-lookup"><span data-stu-id="69431-227">Import the new **Party** records in the Finance and Operations app.</span></span>

    + <span data-ttu-id="69431-228">Hämta filen `FONewParty.csv` från Azure blob-lagring.</span><span class="sxs-lookup"><span data-stu-id="69431-228">Download the `FONewParty.csv` file from Azure blob storage.</span></span> <span data-ttu-id="69431-229">Sökvägen är `partybootstrapping/output/FONewParty.csv`.</span><span class="sxs-lookup"><span data-stu-id="69431-229">The path is `partybootstrapping/output/FONewParty.csv`.</span></span>
    + <span data-ttu-id="69431-230">Konvertera filen `FONewParty.csv` till en Excel-fil och importera Excel-filen till Finance and Operations-programmet.</span><span class="sxs-lookup"><span data-stu-id="69431-230">Convert the `FONewParty.csv` file into an Excel file and import the Excel file into the Finance and Operations app.</span></span>  <span data-ttu-id="69431-231">Om CSV-importen fungerar kan du importera CSV-filen direkt.</span><span class="sxs-lookup"><span data-stu-id="69431-231">If the csv import works for you, you can import csv file directly.</span></span> <span data-ttu-id="69431-232">Importen kan ta ett par timmar att köra, beroende på datavolymen.</span><span class="sxs-lookup"><span data-stu-id="69431-232">The import could take a few hours to run, depending on the data volume.</span></span> <span data-ttu-id="69431-233">Mer information finns i [Översikt över dataimport- och exportjobb](../data-import-export-job.md).</span><span class="sxs-lookup"><span data-stu-id="69431-233">For more information, see [Data import and export jobs overview](../data-import-export-job.md).</span></span>

    ![Importera poster för Datavers-parten](media/data-factory-import-party.png)

9. <span data-ttu-id="69431-235">Aktivera följande instickssteg i programmet för kundengagemang:</span><span class="sxs-lookup"><span data-stu-id="69431-235">In the customer engagement apps, enable the following plugin steps:</span></span>

    + <span data-ttu-id="69431-236">Kontouppdatering</span><span class="sxs-lookup"><span data-stu-id="69431-236">Account Update</span></span>
         + <span data-ttu-id="69431-237">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromAccountEntity: Kontouppdatering</span><span class="sxs-lookup"><span data-stu-id="69431-237">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromAccountEntity: Update of account</span></span>
         + <span data-ttu-id="69431-238">Microsoft.Dynamics.FinanceExtended.Plugins.TriggerNotesForCustomerTypeCodes: Kontouppdatering</span><span class="sxs-lookup"><span data-stu-id="69431-238">Microsoft.Dynamics.FinanceExtended.Plugins.TriggerNotesForCustomerTypeCodes: Update of account</span></span>
    + <span data-ttu-id="69431-239">Kontaktuppdatering</span><span class="sxs-lookup"><span data-stu-id="69431-239">Contact Update</span></span>
         + <span data-ttu-id="69431-240">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromContactEntity: Kontouppdatering</span><span class="sxs-lookup"><span data-stu-id="69431-240">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromContactEntity: Update of contact</span></span>
         + <span data-ttu-id="69431-241">Microsoft.Dynamics.FinanceExtended.Plugins.TriggerNotesForSellableContact: Kontouppdatering</span><span class="sxs-lookup"><span data-stu-id="69431-241">Microsoft.Dynamics.FinanceExtended.Plugins.TriggerNotesForSellableContact: Update of contact</span></span>
    + <span data-ttu-id="69431-242">Uppdatering av msdyn_party</span><span class="sxs-lookup"><span data-stu-id="69431-242">msdyn_party Update</span></span>
         + <span data-ttu-id="69431-243">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromPartyEntity: Uppdatering av msdyn_party</span><span class="sxs-lookup"><span data-stu-id="69431-243">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromPartyEntity: Update of msdyn_party</span></span>
    + <span data-ttu-id="69431-244">Uppdatering av msdyn_vendor</span><span class="sxs-lookup"><span data-stu-id="69431-244">msdyn_vendor Update</span></span>
         + <span data-ttu-id="69431-245">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromVendorEntity: Uppdatering av msdyn_vendor</span><span class="sxs-lookup"><span data-stu-id="69431-245">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromVendorEntity: Update of msdyn_vendor</span></span>

10. <span data-ttu-id="69431-246">Aktivera följande arbetsflöden i kundkopplingsprogrammen om du inaktiverat dem i föregående steg:</span><span class="sxs-lookup"><span data-stu-id="69431-246">In the customer engagement apps, activate the following workflows if you deactivated them in previous steps:</span></span>

    + <span data-ttu-id="69431-247">Skapa leverantörer i tabellen Konton</span><span class="sxs-lookup"><span data-stu-id="69431-247">Create Vendors in Accounts Table</span></span>
    + <span data-ttu-id="69431-248">Skapa leverantörer i tabellen Konton</span><span class="sxs-lookup"><span data-stu-id="69431-248">Create Vendors in Accounts Table</span></span>
    + <span data-ttu-id="69431-249">Skapa leverantörer av typen "person" i registret Kontakter</span><span class="sxs-lookup"><span data-stu-id="69431-249">Create Vendors of type person in Contacts Table</span></span>
    + <span data-ttu-id="69431-250">Skapa leverantörer av typen person i tabellen Leverantörer</span><span class="sxs-lookup"><span data-stu-id="69431-250">Create Vendors of type Person in Vendors Table</span></span>
    + <span data-ttu-id="69431-251">Uppdatera leverantörer i tabellen Konton</span><span class="sxs-lookup"><span data-stu-id="69431-251">Update Vendors in Accounts Table</span></span>
    + <span data-ttu-id="69431-252">Uppdatera leverantörer i tabellen Leverantörer</span><span class="sxs-lookup"><span data-stu-id="69431-252">Update Vendors in Vendors Table</span></span>
    + <span data-ttu-id="69431-253">Uppdatera leverantörer av typen person i tabellen Kontakter</span><span class="sxs-lookup"><span data-stu-id="69431-253">Update Vendors of type Person in Contacts Table</span></span>
    + <span data-ttu-id="69431-254">Uppdatera leverantörer av typen person i tabellen Leverantörer</span><span class="sxs-lookup"><span data-stu-id="69431-254">Update Vendors of type Person in Vendors Table</span></span>

11. <span data-ttu-id="69431-255">Kör de **part** relaterade kartorna enligt instruktionerna i [Part och global adressbok](party-gab.md).</span><span class="sxs-lookup"><span data-stu-id="69431-255">Run the **Party**-related maps as instructed in [Party and global address book](party-gab.md).</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="69431-256">Felsökning</span><span class="sxs-lookup"><span data-stu-id="69431-256">Troubleshooting</span></span>

1. <span data-ttu-id="69431-257">Om processen misslyckas kör du datafabriken igen, med början från den misslyckade aktiviteten.</span><span class="sxs-lookup"><span data-stu-id="69431-257">In the process fails, rerun the data factory starting from the failed activity.</span></span>
2. <span data-ttu-id="69431-258">Vissa filer genereras av den datafabrik som du kan använda för datavalidering.</span><span class="sxs-lookup"><span data-stu-id="69431-258">Some files are generated by the data factory that you can use for data validation purpose.</span></span>
3. <span data-ttu-id="69431-259">Datafabriken körs baserat på CSV-filer som är kommaavgränsade.</span><span class="sxs-lookup"><span data-stu-id="69431-259">The data factory runs based on csv files that are comma-delimited.</span></span> <span data-ttu-id="69431-260">Om det finns ett fältvärde med ett kommatecken kan detta komma att störa resultaten.</span><span class="sxs-lookup"><span data-stu-id="69431-260">If there is a field value that has a comma, it may interfere with the results.</span></span> <span data-ttu-id="69431-261">Du måste ta bort kommatecknen.</span><span class="sxs-lookup"><span data-stu-id="69431-261">You need to remove the commas.</span></span>
4. <span data-ttu-id="69431-262">På fliken **Övervakning** finns information om alla steg och data som bearbetas.</span><span class="sxs-lookup"><span data-stu-id="69431-262">The **Monitoring** tab provides information about all steps and data processed.</span></span> <span data-ttu-id="69431-263">Välj ett specifikt steg för att felsöka det.</span><span class="sxs-lookup"><span data-stu-id="69431-263">Select a specific step to debug it.</span></span>

    ![Fliken Övervakning](media/data-factory-monitor.png)

## <a name="learn-more-about-the-template"></a><span data-ttu-id="69431-265">Läs mer om mallen</span><span class="sxs-lookup"><span data-stu-id="69431-265">Learn more about the template</span></span>

<span data-ttu-id="69431-266">Det finns kommentarer för mallen i filen [readme.md](https://github.com/microsoft/Dynamics-365-FastTrack-Implementation-Assets/blob/master/Dual-write/Upgrade%20data%20to%20dual-write%20Party-GAB%20schema/readme.md).</span><span class="sxs-lookup"><span data-stu-id="69431-266">You can find comments for the template the [readme.md](https://github.com/microsoft/Dynamics-365-FastTrack-Implementation-Assets/blob/master/Dual-write/Upgrade%20data%20to%20dual-write%20Party-GAB%20schema/readme.md) file.</span></span>