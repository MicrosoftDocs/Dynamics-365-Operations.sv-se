---
title: Felsöka problem under första synkroniseringen
description: Det här avsnittet innehåller felsökningsinformation som kan hjälpa dig att åtgärda problem som kan uppstå under initial synkronisering.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 03/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-03-16
ms.openlocfilehash: 10065039fce441d7f96f700ff826d959e96f2479
ms.sourcegitcommit: cecd97fd74ff7b31f1a677e8fdf3e233aa28ef5a
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/28/2020
ms.locfileid: "3410091"
---
# <a name="troubleshoot-issues-during-initial-synchronization"></a><span data-ttu-id="da600-103">Felsöka problem under första synkroniseringen</span><span class="sxs-lookup"><span data-stu-id="da600-103">Troubleshoot issues during initial synchronization</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="da600-104">Det här avsnittet innehåller felsökningsinformation för integrering av dubbelriktad skrivning mellan Finance and Operations-appar och Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="da600-104">This topic provides troubleshooting information for dual-write integration between Finance and Operations apps and Common Data Service.</span></span> <span data-ttu-id="da600-105">Det ger särskilt information som kan hjälpa dig att åtgärda problem som kan uppstå under initial synkronisering.</span><span class="sxs-lookup"><span data-stu-id="da600-105">Specifically, it provides information that can help you fix issues that might occur during initial synchronization.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="da600-106">Vissa av de problem som det här ämnet behandlar kan kräva antingen systemadministratörsrollen eller Microsoft Azure Active Directory (Azure AD) autentiseringsuppgifter för administratör för klientorganisationen.</span><span class="sxs-lookup"><span data-stu-id="da600-106">Some of the issues that this topic addresses might require either the system admin role or Microsoft Azure Active Directory (Azure AD) tenant admin credentials.</span></span> <span data-ttu-id="da600-107">I avsnittet för varje problem förklaras om en viss roll eller autentiseringsuppgifter krävs.</span><span class="sxs-lookup"><span data-stu-id="da600-107">The section for each issue explains whether a specific role or credentials are required.</span></span>

## <a name="check-for-initial-synchronization-errors-in-a-finance-and-operations-app"></a><span data-ttu-id="da600-108">Sök efter inledande synkroniseringsfel i en Finance and Operations-app</span><span class="sxs-lookup"><span data-stu-id="da600-108">Check for initial synchronization errors in a Finance and Operations app</span></span>

<span data-ttu-id="da600-109">När du har aktiverat mappningsmallen ska status för mappningarna **köras**.</span><span class="sxs-lookup"><span data-stu-id="da600-109">After you enable the mapping templates, the status of the maps should be **Running**.</span></span> <span data-ttu-id="da600-110">Om status **inte körs** har fel uppstått vid den ursprungliga synkroniseringen.</span><span class="sxs-lookup"><span data-stu-id="da600-110">If the status is **Not running**, errors occurred during initial synchronization.</span></span> <span data-ttu-id="da600-111">Om du vill visa felen väljer du fliken **Information om initial synkronisering** på sidan **Dubbelriktad skrivning**.</span><span class="sxs-lookup"><span data-stu-id="da600-111">To view the errors, select the **Initial sync details** tab on the **Dual-write** page.</span></span>

![Fliken Information om initial synkronisering](media/initial_sync_status.png)

## <a name="you-cant-complete-initial-synchronization-400-bad-request"></a><span data-ttu-id="da600-113">Det går inte att slutföra den första synkroniseringen: 400 Felaktig begäran</span><span class="sxs-lookup"><span data-stu-id="da600-113">You can't complete initial synchronization: 400 Bad Request</span></span>

<span data-ttu-id="da600-114">**Den roll som krävs för att åtgärda problemet:** systemadministratör</span><span class="sxs-lookup"><span data-stu-id="da600-114">**Required role to fix the issue:** System admin</span></span>

<span data-ttu-id="da600-115">Följande felmeddelande kan visas när du försöker köra mappningen och den första synkroniseringen:</span><span class="sxs-lookup"><span data-stu-id="da600-115">You might receive the following error message when you try to run the mapping and initial synchronization:</span></span>

<span data-ttu-id="da600-116">*Fjärrservern returnerade ett fel: (400) felaktig begäran.) AX, exporten upptäckte ett fel*</span><span class="sxs-lookup"><span data-stu-id="da600-116">*The remote server returned an error: (400) Bad Request.), AX export encountered an error*</span></span>

<span data-ttu-id="da600-117">Här följer ett exempel på det fullständiga felmeddelandet.</span><span class="sxs-lookup"><span data-stu-id="da600-117">Here is an example of the full error message.</span></span>

```console
Dual write Initial Sync completed with status: Error. Following are the details:
Executed leg: From AX Financial dimensions to CRM msdyn_dimensionattributes
with exported records count: 0, ImportRecordsErrorCount: 0,
ImportRecordsInsertedCount: 0 and ImportRecordsUpdatedCount: 0
ErrorsDetails:
Dual write Initial sync failed
Message: ([Bad Request], The remote server returned an error: (400) Bad Request.), AX export encountered an error
Stacktrace: at
Microsoft.Dynamics.Integrator.QueryGenerator.AxClient.\<ExportAxPackage\>d__16.MoveNext()
in X:\\bt\\1024532\\repo\\src\\Core\\QueryGenerator\\AxClient.cs:line 265
\--- End of stack trace from previous location where exception was thrown ---
at System.Runtime.ExceptionServices.ExceptionDispatchInfo.Throw()
at System.Runtime.CompilerServices.TaskAwaiter.HandleNonSuccessAndDebuggerNotification(Task task)
at Microsoft.D365.ServicePlatform.Context.ServiceContext.Activity.\<ExecuteAsync\>d__11\`2.MoveNext()
\--- End of stack trace from previous location where exception was thrown ---
```

<span data-ttu-id="da600-118">Om detta fel inträffar konsekvent och du inte kan slutföra den ursprungliga synkroniseringen följer du stegen nedan för att åtgärda problemet.</span><span class="sxs-lookup"><span data-stu-id="da600-118">If this error occurs consistently, and you can't complete the initial synchronization, follow these steps to fix the issue.</span></span>

1. <span data-ttu-id="da600-119">Logga in på den virtuella datorn (VM) för Finance and Operations-appen.</span><span class="sxs-lookup"><span data-stu-id="da600-119">Sign in to the virtual machine (VM) for the Finance and Operations app.</span></span>
2. <span data-ttu-id="da600-120">Öppna Microsoft Management Console.</span><span class="sxs-lookup"><span data-stu-id="da600-120">Open Microsoft Management Console.</span></span>
3. <span data-ttu-id="da600-121">I fönstret **tjänster** ser du till att tjänsten ramverk för dataimport och export av Microsoft Dynamics 365 körs.</span><span class="sxs-lookup"><span data-stu-id="da600-121">In the **Services** pane, make sure that the Microsoft Dynamics 365 Data import export framework service is running.</span></span> <span data-ttu-id="da600-122">Starta om den om den har stoppats eftersom den första synkroniseringen kräver det.</span><span class="sxs-lookup"><span data-stu-id="da600-122">Restart it if it has been stopped, because the initial synchronization requires it.</span></span>

## <a name="initial-synchronization-error-403-forbidden"></a><span data-ttu-id="da600-123">Fel vid första synkronisering: 403 förbud</span><span class="sxs-lookup"><span data-stu-id="da600-123">Initial synchronization error: 403 Forbidden</span></span>

<span data-ttu-id="da600-124">Följande felmeddelande kan visas under första synkroniseringen:</span><span class="sxs-lookup"><span data-stu-id="da600-124">You might receive the following error message during initial synchronization:</span></span>

<span data-ttu-id="da600-125">*(\[Förbjudet\], Fjärrservern returnerade ett fel: (403) Förbjudet.), AX-exporten upptäckte ett fel*</span><span class="sxs-lookup"><span data-stu-id="da600-125">*(\[Forbidden\], The remote server returned an error: (403) Forbidden.), AX export encountered an error*</span></span>

<span data-ttu-id="da600-126">Gör så här om du vill åtgärda problemet.</span><span class="sxs-lookup"><span data-stu-id="da600-126">To fix the issue, follow these steps.</span></span>

1. <span data-ttu-id="da600-127">Logga in på Finance and Operations-appen.</span><span class="sxs-lookup"><span data-stu-id="da600-127">Sign in to the Finance and Operations app.</span></span>
2. <span data-ttu-id="da600-128">På sidan **Azure Active Directory-appar** ta bort klienten **DtAppID** och lägg sedan till den igen.</span><span class="sxs-lookup"><span data-stu-id="da600-128">On the **Azure Active Directory applications** page, delete the **DtAppID** client, and then add it again.</span></span>

![Lista över Azure AD-appar](media/aad_applications.png)

## <a name="self-reference-or-circular-reference-failures-during-initial-synchronization"></a><span data-ttu-id="da600-130">Självreferens- eller cirkulära referensfel vid inledande synkronisering</span><span class="sxs-lookup"><span data-stu-id="da600-130">Self-reference or circular-reference failures during initial synchronization</span></span>

<span data-ttu-id="da600-131">Ett felmeddelande om någon av dina mappningar har självreferenser eller cirkulära referenser.</span><span class="sxs-lookup"><span data-stu-id="da600-131">You might receive an error messages if any of your mappings have self-references or circular references.</span></span> <span data-ttu-id="da600-132">Felen hör till dessa kategorier:</span><span class="sxs-lookup"><span data-stu-id="da600-132">The errors fall into these categories:</span></span>

- [<span data-ttu-id="da600-133">Leverantörer V2 till entitetsmappningen msdyn_vendors</span><span class="sxs-lookup"><span data-stu-id="da600-133">Vendors V2 to msdyn_vendors entity mapping</span></span>](#error-vendor-map)
- [<span data-ttu-id="da600-134">Kund V3 till entitetsmappningen Konto</span><span class="sxs-lookup"><span data-stu-id="da600-134">Customers V3 to Accounts entity mapping</span></span>](#error-customer-map)

## <a name="resolve-an-error-in-vendors-v2-to-msdyn_vendors-entity-mapping"></a><a id="error-vendor-map"></a><span data-ttu-id="da600-135">Lös ett fel i leverantörerna V2 och entitetsmappningen msdyn_vendors</span><span class="sxs-lookup"><span data-stu-id="da600-135">Resolve an error in Vendors V2 to msdyn_vendors entity mapping</span></span>

<span data-ttu-id="da600-136">Du kan stöta på följande initiala synkroniseringsfel på **Leverantörer V2** till **msdyn_vendors** mappning om entiteterna har befintliga poster med värden i fälten **PrimaryContactPersonId** och **InvoiceVendorAccountNumber**.</span><span class="sxs-lookup"><span data-stu-id="da600-136">You might run into the following initial sync errors on the **Vendors V2** to **msdyn_vendors** mapping if the entities have existing records with values in the **PrimaryContactPersonId** and **InvoiceVendorAccountNumber** fields.</span></span> <span data-ttu-id="da600-137">Detta beror på att **InvoiceVendorAccountNumber** är ett självrefererande fält och att **PrimaryContactPersonId** är en cirkelreferens i leverantörsmappningen.</span><span class="sxs-lookup"><span data-stu-id="da600-137">This because **InvoiceVendorAccountNumber** is a self-referencing field, and **PrimaryContactPersonId** is a circular reference in the vendor mapping.</span></span>

<span data-ttu-id="da600-138">*Det gick inte att matcha GUID för fältet: <field>. Det gick inte att hitta sökningen: <value>. Prova denna URL för att se om referensdata existerar: https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/<entity>?$select=<field>&$filter=<field> eq <value>*</span><span class="sxs-lookup"><span data-stu-id="da600-138">*Couldn't resolve the guid for the field: <field>. The lookup was not found: <value>. Try this URL(s) to check if the reference data exists: https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/<entity>?$select=<field>&$filter=<field> eq <value>*</span></span>

<span data-ttu-id="da600-139">Här följer några exempel:</span><span class="sxs-lookup"><span data-stu-id="da600-139">Here are a couple of examples:</span></span>

- <span data-ttu-id="da600-140">*Det gick inte att matcha GUID för fältet: msdyn_vendorprimarycontactperson.msdyn_contactpersonid. Det gick inte att hitta sökningen: 000056. Prova denna URL för att se om referensdata existerar: https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/contacts?$select=msdyn_contactpersonid.contactid&$filter=msdyn_contactpersonid eq '000056'*</span><span class="sxs-lookup"><span data-stu-id="da600-140">*Couldn't resolve the guid for the field: msdyn_vendorprimarycontactperson.msdyn_contactpersonid. The lookup was not found: 000056. Try this URL(s) to check if the reference data exists: https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/contacts?$select=msdyn_contactpersonid.contactid&$filter=msdyn_contactpersonid eq '000056'*</span></span>
- <span data-ttu-id="da600-141">*Det gick inte att matcha GUID för fältet: msdyn_invoicevendoraccountnumber.msdyn_vendoraccountnumber. Det gick inte att hitta sökningen: V24-1. Prova denna URL för att se om referensdata existerar: https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/msdn_vendors?$select=msdyn_vendoraccountnumber,msdyn_vendorid&$filter=msdyn_vendoraccountnumber eq 'V24-1'*</span><span class="sxs-lookup"><span data-stu-id="da600-141">*Couldn't resolve the guid for the field: msdyn_invoicevendoraccountnumber.msdyn_vendoraccountnumber. The lookup was not found: V24-1. Try this URL(s) to check if the reference data exists: https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/msdn_vendors?$select=msdyn_vendoraccountnumber,msdyn_vendorid&$filter=msdyn_vendoraccountnumber eq 'V24-1'*</span></span>

<span data-ttu-id="da600-142">Om du har poster med värden i dessa fält i leverantörsenheten följer du stegen i avsnittet nedan för att slutföra den inledande synkroniseringen.</span><span class="sxs-lookup"><span data-stu-id="da600-142">If you have records with values in these fields in the vendor entity follow the steps in the below section to complete initial sync successfully.</span></span>

1. <span data-ttu-id="da600-143">I Finance and Operations-appen tar du bort fälten **PrimaryContactPersonId** och **InvoiceVendorAccountNumber** från mappningen och sparar ändringarna.</span><span class="sxs-lookup"><span data-stu-id="da600-143">In the Finance and Operations app, delete the **PrimaryContactPersonId** and **InvoiceVendorAccountNumber** fields from the mapping and save the changes.</span></span>

    1. <span data-ttu-id="da600-144">Navigera till mappning med dubbelriktad skrivning för **leverantörer V2 (msdyn_vendors)** och välj fliken **enhetsmappningar**. I vänster filter väljer du **Finance and Operations apps.Vendors V2**.</span><span class="sxs-lookup"><span data-stu-id="da600-144">Navigate to the dual-write mapping page for **Vendors V2 (msdyn_vendors)**, and select the **Entity mappings** tab. In the left filter, select **Finance and Operations apps.Vendors V2**.</span></span> <span data-ttu-id="da600-145">I höger filter, välj **Sales.Vendor**.</span><span class="sxs-lookup"><span data-stu-id="da600-145">In the right filter, select **Sales.Vendor**.</span></span>

    2. <span data-ttu-id="da600-146">Sök efter **primarycontactperson** för att hitta källfältet **PrimaryContactPersonId**.</span><span class="sxs-lookup"><span data-stu-id="da600-146">Search for **primarycontactperson** to find the source field **PrimaryContactPersonId**.</span></span>
    
    3. <span data-ttu-id="da600-147">Klicka på knappen **Åtgärder** och välj **Ta bort**.</span><span class="sxs-lookup"><span data-stu-id="da600-147">Click the **Actions** button, and select **Delete**.</span></span>
    
        ![egen eller cirkelreferens 3](media/vend_selfref3.png)
    
    4. <span data-ttu-id="da600-149">Upprepa detta om du vill ta bort fältet **InvoiceVendorAccountNumber**.</span><span class="sxs-lookup"><span data-stu-id="da600-149">Repeat to delete the **InvoiceVendorAccountNumber** field.</span></span>
    
        ![egen eller cirkelreferens 4](media/vend-selfref4.png)
    
    5. <span data-ttu-id="da600-151">Spara mappningsändringarna.</span><span class="sxs-lookup"><span data-stu-id="da600-151">Save the mapping changes.</span></span>

2. <span data-ttu-id="da600-152">Inaktivera ändringsspårningen för entiteten **leverantörer V2**.</span><span class="sxs-lookup"><span data-stu-id="da600-152">Disable the change tracking for the **Vendors V2** entity.</span></span>

    1. <span data-ttu-id="da600-153">Navigera till **Datahantering \> Dataentiteter**.</span><span class="sxs-lookup"><span data-stu-id="da600-153">Navigate to **Data management \> Data Entities**.</span></span>
    
    2. <span data-ttu-id="da600-154">Välj entiteten **Leverantörer V2**.</span><span class="sxs-lookup"><span data-stu-id="da600-154">Select the **Vendors V2** entity.</span></span>
    
    3. <span data-ttu-id="da600-155">Klicka på **alternativ** i menyraden och sedan på **ändra spårning**.</span><span class="sxs-lookup"><span data-stu-id="da600-155">Click **Options** from the menu bar, and then **Change tracking**.</span></span>
    
        ![egen eller cirkelreferens 5](media/selfref_options.png)
    
    4. <span data-ttu-id="da600-157">Klicka på **inaktivera ändringsspårning**.</span><span class="sxs-lookup"><span data-stu-id="da600-157">Click **Disable Change Tracking**.</span></span>
    
        ![egen eller cirkelreferens 6](media/selfref_tracking.png)

3. <span data-ttu-id="da600-159">Kör mappningen av den första synkroniseringen av **leverantörer v2 (msdyn_vendors)**.</span><span class="sxs-lookup"><span data-stu-id="da600-159">Run the initial sync of **Vendors V2 (msdyn_vendors)** mapping.</span></span> <span data-ttu-id="da600-160">Den ursprungliga synkroniseringen bör köras utan fel.</span><span class="sxs-lookup"><span data-stu-id="da600-160">The initial sync should run successfully without any errors.</span></span>

4. <span data-ttu-id="da600-161">Kör den första synkroniseringen för mappningen **CDS-kontakter V2 (kontakter)**.</span><span class="sxs-lookup"><span data-stu-id="da600-161">Run the initial sync for the **CDS Contacts V2 (contacts)** mapping.</span></span> <span data-ttu-id="da600-162">Du måste synkronisera den här mappningen om du vill synkronisera fältet primär kontakt på leverantörsenheten eftersom kontaktposterna också måste synkroniseras.</span><span class="sxs-lookup"><span data-stu-id="da600-162">You must sync this mapping if you want to sync primary contact field on vendors entity as the contacts records also need to be initial synced.</span></span>

5. <span data-ttu-id="da600-163">Lägg till fälten **PrimaryContactPersonId** och **InvoiceVendorAccountNumber** tillbaka till mappningen **leverantörer V2 (msdyn_vendors)** och spara mappningen.</span><span class="sxs-lookup"><span data-stu-id="da600-163">Add the fields **PrimaryContactPersonId** and **InvoiceVendorAccountNumber** back to the **Vendors V2 (msdyn_vendors)** mapping and save the mapping.</span></span>

6. <span data-ttu-id="da600-164">Kör den första synkroniseringen igen för mappningen **leverantörer v2 (msdyn_vendors)**.</span><span class="sxs-lookup"><span data-stu-id="da600-164">Run the initial sync again for the **Vendors V2 (msdyn_vendors)** mapping.</span></span> <span data-ttu-id="da600-165">Alla poster kommer att synkroniseras eftersom spårning av ändringar har inaktiverats.</span><span class="sxs-lookup"><span data-stu-id="da600-165">All the records will be synced, because change tracking is disabled.</span></span>

7. <span data-ttu-id="da600-166">Aktivera ändringsspårningen för entiteten **leverantörer V2**.</span><span class="sxs-lookup"><span data-stu-id="da600-166">Enable change tracking for the **Vendors V2** entity.</span></span>

## <a name="resolve-an-error-in-customers-v3-to-accounts-entity-mapping"></a><a id="error-customer-map"></a><span data-ttu-id="da600-167">Lös ett fel i enhetsmappning för kunder V3 till konton</span><span class="sxs-lookup"><span data-stu-id="da600-167">Resolve an error in Customers V3 to Accounts entity mapping</span></span>

<span data-ttu-id="da600-168">Du kan stöta på följande initiala synkroniseringsfel på mappningen **Kunder V3** till **Konton** om entiteterna har befintliga poster med värden i fälten **ContactPersonID** och **InvoiceAccount**.</span><span class="sxs-lookup"><span data-stu-id="da600-168">You might run into the following initial sync errors on the **Customers V3** to **Accounts** mapping if the entities have existing records with values in the **ContactPersonID** and **InvoiceAccount** fields.</span></span> <span data-ttu-id="da600-169">Detta beror på att **InvoiceAccount** är ett självrefererande fält och att **ContactPersonID** är en cirkelreferens i leverantörsmappningen.</span><span class="sxs-lookup"><span data-stu-id="da600-169">This because **InvoiceAccount** is a self-referencing field, and **ContactPersonID** is a circular reference in the vendor mapping.</span></span>

<span data-ttu-id="da600-170">*Det gick inte att matcha GUID för fältet: <field>. Det gick inte att hitta sökningen: <value>. Prova denna URL för att se om referensdata existerar: https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/<entity>?$select=<field>&$filter=<field> eq <value>*</span><span class="sxs-lookup"><span data-stu-id="da600-170">*Couldn't resolve the guid for the field: <field>. The lookup was not found: <value>. Try this URL(s) to check if the reference data exists: https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/<entity>?$select=<field>&$filter=<field> eq <value>*</span></span>

- <span data-ttu-id="da600-171">*Det gick inte att matcha GUID för fältet: primarycontactid.msdyn_contactpersonid. Det gick inte att hitta sökningen: 000056. Prova denna URL för att se om referensdata existerar: https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/contacts?$select=msdyn_contactpersonid.contactid&$filter=msdyn_contactpersonid eq '000056'*</span><span class="sxs-lookup"><span data-stu-id="da600-171">*Couldn't resolve the guid for the field: primarycontactid.msdyn_contactpersonid. The lookup was not found: 000056. Try this URL(s) to check if the reference data exists: https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/contacts?$select=msdyn_contactpersonid.contactid&$filter=msdyn_contactpersonid eq '000056'*</span></span>
- <span data-ttu-id="da600-172">*Det gick inte att matcha GUID för fältet: msdyn_billingaccount.accountnumber. Det gick inte att hitta sökningen: 1206-1. Prova denna URL för att se om referensdata existerar: https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/accounts?$select=accountnumber.account&$filter=accountnumber eq '1206-1'*</span><span class="sxs-lookup"><span data-stu-id="da600-172">*Couldn't resolve the guid for the field: msdyn_billingaccount.accountnumber. The lookup was not found: 1206-1. Try this URL(s) to check if the reference data exists: https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/accounts?$select=accountnumber.account&$filter=accountnumber eq '1206-1'*</span></span>

<span data-ttu-id="da600-173">Om du har poster med värden i dessa fält i kundenheten följer du stegen i avsnittet nedan för att slutföra den inledande synkroniseringen.</span><span class="sxs-lookup"><span data-stu-id="da600-173">If you have records with values in these fields in the customer entity follow the steps in the below section to complete initial sync successfully.</span></span> <span data-ttu-id="da600-174">Du kan använda den här metoden för alla enheter utanför lådan, t.ex. konton och kontakter.</span><span class="sxs-lookup"><span data-stu-id="da600-174">You can use this approach for any out-of-the-box entities such Accounts and Contacts.</span></span>

1. <span data-ttu-id="da600-175">I Finance and Operations-appen, ta bort fälten **ContactPersonID** och **InvoiceAccount** från **Kunder V3 (konton)**-mappningen och spara mappningen.</span><span class="sxs-lookup"><span data-stu-id="da600-175">In the Finance and Operations app, delete the fields **ContactPersonID** and **InvoiceAccount** from the **Customers V3 (accounts)** mapping and save the mapping.</span></span>

    1. <span data-ttu-id="da600-176">Navigera till mappning med dubbelriktad skrivning för **Kunder V3 (konton)** och välj fliken **enhetsmappningar**. I vänster filter, välj **Finance and Operations app.Customers V3**.</span><span class="sxs-lookup"><span data-stu-id="da600-176">Navigate to the dual-write mapping page for **Customers V3 (accounts)**, select the **Entity mappings** tab. In the left filter, select **Finance and Operations app.Customers V3**.</span></span> <span data-ttu-id="da600-177">I höger filter, välj **Common Data Service.Account**.</span><span class="sxs-lookup"><span data-stu-id="da600-177">In the right filter, select **Common Data Service.Account**.</span></span>

    2. <span data-ttu-id="da600-178">Sök efter **contactperson** för att hitta källfältet **ContactPersonID**.</span><span class="sxs-lookup"><span data-stu-id="da600-178">Search for **contactperson** to find the source field **ContactPersonID**.</span></span>
    
    3. <span data-ttu-id="da600-179">Klicka på knappen **Åtgärder** och välj **Ta bort**.</span><span class="sxs-lookup"><span data-stu-id="da600-179">Click the **Actions** button, and select **Delete**.</span></span>
    
        ![egen eller cirkelreferens 3](media/cust_selfref3.png)
    
    4. <span data-ttu-id="da600-181">Upprepa detta om du vill ta bort fältet **InvoiceAccount**.</span><span class="sxs-lookup"><span data-stu-id="da600-181">Repeat to delete the **InvoiceAccount** field.</span></span>
    
        ![egen eller cirkelreferens](media/cust_selfref4.png)
    
    5. <span data-ttu-id="da600-183">Spara mappningsändringarna.</span><span class="sxs-lookup"><span data-stu-id="da600-183">Save the mapping changes.</span></span>

2. <span data-ttu-id="da600-184">Inaktivera ändringsspårningen för entiteten **kunder V3**.</span><span class="sxs-lookup"><span data-stu-id="da600-184">Disable the change tracking for the **Customers V3** entity.</span></span>

    1. <span data-ttu-id="da600-185">Navigera till **Datahantering \> Dataentiteter**.</span><span class="sxs-lookup"><span data-stu-id="da600-185">Navigate to **Data management \> Data Entities**.</span></span>
    
    2. <span data-ttu-id="da600-186">Välj entiteten **kunder V3**.</span><span class="sxs-lookup"><span data-stu-id="da600-186">Select the **Customers V3** entity.</span></span>
    
    3. <span data-ttu-id="da600-187">Klicka på **alternativ** i menyraden och sedan på **ändra spårning**.</span><span class="sxs-lookup"><span data-stu-id="da600-187">Click **Options** from the menu bar, and then **Change tracking**.</span></span>
    
        ![egen eller cirkelreferens 5](media/selfref_options.png)
    
    4. <span data-ttu-id="da600-189">Klicka på **inaktivera ändringsspårning**.</span><span class="sxs-lookup"><span data-stu-id="da600-189">Click **Disable Change Tracking**.</span></span>
    
        ![egen eller cirkelreferens 6](media/selfref_tracking.png)

3. <span data-ttu-id="da600-191">Kör den första synkroniseringen för mappningen **Kunder V3 (konton)**.</span><span class="sxs-lookup"><span data-stu-id="da600-191">Run the initial sync for the **Customers V3 (Accounts)** mapping.</span></span> <span data-ttu-id="da600-192">Den ursprungliga synkroniseringen bör köras utan fel.</span><span class="sxs-lookup"><span data-stu-id="da600-192">The initial sync should run successfully without any errors.</span></span>

4. <span data-ttu-id="da600-193">Kör den första synkroniseringen för mappningen **CDS-kontakter V2 (kontakter)**.</span><span class="sxs-lookup"><span data-stu-id="da600-193">Run the initial sync for the **CDS Contacts V2 (contacts)** mapping.</span></span> <span data-ttu-id="da600-194">Det finns 2 mappningar med samma namn.</span><span class="sxs-lookup"><span data-stu-id="da600-194">There are 2 maps with the same name.</span></span> <span data-ttu-id="da600-195">Välj den som innehåller **Mall för dubbelriktad skrivning för synkronisering mellan FO.CDS Vendor Contacts V2 to CDS.Contacts. Kräver nytt paket \[Dynamics365SupplyChainExtended\].**</span><span class="sxs-lookup"><span data-stu-id="da600-195">Select the one with the description **Dual-write template for sync between FO.CDS Vendor Contacts V2 to CDS.Contacts. Requires new package \[Dynamics365SupplyChainExtended\].**</span></span> <span data-ttu-id="da600-196">på fliken **Detaljer** på kartan.</span><span class="sxs-lookup"><span data-stu-id="da600-196">on the **Details** tab of the map.</span></span>

5. <span data-ttu-id="da600-197">Lägg till fälten **InvoiceAccount** och **ContactPersonId** tillbaka till mappningen **Kunder V3 (konton)** och spara mappningen.</span><span class="sxs-lookup"><span data-stu-id="da600-197">Add the fields **InvoiceAccount** and **ContactPersonId** back to the **Customers V3 (Accounts)** mapping and save the mapping.</span></span> <span data-ttu-id="da600-198">Nu är både fältet **InvoiceAccount** och fältet **ContactPersonId** del i ett direkt synkroniseringsläge.</span><span class="sxs-lookup"><span data-stu-id="da600-198">Now, both the **InvoiceAccount** field and the **ContactPersonId** field are again part of live sync mode.</span></span> <span data-ttu-id="da600-199">I nästa steg slutför du den inledande synkroniseringen för dessa fält.</span><span class="sxs-lookup"><span data-stu-id="da600-199">In the next step, you complete the initial sync for these fields.</span></span>

6. <span data-ttu-id="da600-200">Kör den första synkroniseringen igen för mappningen **Kunder V3 (konton)**.</span><span class="sxs-lookup"><span data-stu-id="da600-200">Run the initial sync again for the **Customers V3 (Accounts)** mapping.</span></span> <span data-ttu-id="da600-201">Eftersom ändringsspårning är inaktiverat synkroniserar körningen av synkronisering data för **InvoiceAccount** och **ContactPersonId** från Finance and Operations-appen till Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="da600-201">Because change tracking is disabled, running the sync will sync the data for **InvoiceAccount** and **ContactPersonId** from the Finance and Operations app to Common Data Service.</span></span>

7. <span data-ttu-id="da600-202">Om du vill synkronisera data för **InvoiceAccount** och **ContactPersonId** från Common Data Service till Finance and Operations, använder du ett dataintegreringsprojekt.</span><span class="sxs-lookup"><span data-stu-id="da600-202">To sync the data for **InvoiceAccount** and **ContactPersonId** from Common Data Service to the Finance and Operations, you use a data integration project.</span></span>

    1. <span data-ttu-id="da600-203">I Power Apps skapar du ett dataintegreringsprojekt mellan **Sales.Account** och **Finance and Operations-appar. Kunder V3**-enheter.</span><span class="sxs-lookup"><span data-stu-id="da600-203">In Power Apps, create a data integration project between the **Sales.Account** and **Finance and Operations apps.Customers V3** entities.</span></span> <span data-ttu-id="da600-204">Datariktningen måste vara från Common Data Service till Finance and Operations-appen.</span><span class="sxs-lookup"><span data-stu-id="da600-204">The data direction must be from Common Data Service to the Finance and Operations app.</span></span>  <span data-ttu-id="da600-205">Eftersom **InvoiceAccount** är ett nytt attribut i dubbelriktad skrivning kanske du vill hoppa över den inledande synkroniseringen för det här attributet.</span><span class="sxs-lookup"><span data-stu-id="da600-205">Because **InvoiceAccount** is a new attribute in dual-write, you may want to skip initial sync for this attribute.</span></span> <span data-ttu-id="da600-206">Mer information finns i [integrera data i Common Data Service](https://docs.microsoft.com/power-platform/admin/data-integrator).</span><span class="sxs-lookup"><span data-stu-id="da600-206">For more information, see [Integrate data into Common Data Service](https://docs.microsoft.com/power-platform/admin/data-integrator).</span></span>

        <span data-ttu-id="da600-207">Följande bild visar ett projekt som uppdaterar **CustomerAccount** och **ContactPersonId**.</span><span class="sxs-lookup"><span data-stu-id="da600-207">The following image shows a project that updates **CustomerAccount** and **ContactPersonId**.</span></span>

        ![egen eller cirkelreferens](media/cust_selfref6.png)

    2. <span data-ttu-id="da600-209">Lägg till företagskriterierna i filtret på Common Data Service sidan, eftersom endast de poster som matchar filter villkoren kommer att uppdateras i  Finance and Operations-appen.</span><span class="sxs-lookup"><span data-stu-id="da600-209">Add the company criteria in the filter on Common Data Service side, because only the records that match filter criteria will be updated in the Finance and Operations app.</span></span> <span data-ttu-id="da600-210">Klicka på filter ikonen om du vill lägga till ett filter.</span><span class="sxs-lookup"><span data-stu-id="da600-210">To add a filter, click the filter icon.</span></span> <span data-ttu-id="da600-211">I dialogrutan **Redigera fråga** kan du lägga till en filterfråga som **_msdyn_company_value eq '\<guid\>'**.</span><span class="sxs-lookup"><span data-stu-id="da600-211">In the **Edit query** dialog, you can add a filter query like **_msdyn_company_value eq '\<guid\>'**.</span></span> <span data-ttu-id="da600-212">Om det inte finns någon filterikon skapar du ett supportärende som ber dataintegrationsgruppen att aktivera filterkapaciteten för din klientorganisation.</span><span class="sxs-lookup"><span data-stu-id="da600-212">If the filter icon is not present, create a support ticket to ask the data integration team to enable the filter capability on your tenant.</span></span> <span data-ttu-id="da600-213">Om du inte anger någon filterfråga för **_msdyn_company_value** synkroniseras alla poster.</span><span class="sxs-lookup"><span data-stu-id="da600-213">If you do not enter a filter query for **_msdyn_company_value**, then all the records are synced.</span></span>

        ![egen eller cirkelreferens](media/cust_selfref7.png)

        <span data-ttu-id="da600-215">Detta slutför den inledande synkroniseringen av posterna.</span><span class="sxs-lookup"><span data-stu-id="da600-215">This completes the initial sync of the records.</span></span>

8. <span data-ttu-id="da600-216">Aktivera ändringsspårningen för entiteten **kunder V3** i Finance and Operations-appen.</span><span class="sxs-lookup"><span data-stu-id="da600-216">Enable change tracking for the **Customers V3** entity in the Finance and Operations app.</span></span>

