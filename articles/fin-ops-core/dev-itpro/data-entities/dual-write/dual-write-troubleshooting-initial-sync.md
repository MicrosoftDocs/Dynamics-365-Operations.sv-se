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
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-03-16
ms.openlocfilehash: 4d0ca1fb4b7a4964194516544686b6bb7d26e76c
ms.sourcegitcommit: 0a741b131ed71f6345d4219a47cf5f71fec6744b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "3997336"
---
# <a name="troubleshoot-issues-during-initial-synchronization"></a><span data-ttu-id="6fcb3-103">Felsöka problem under första synkroniseringen</span><span class="sxs-lookup"><span data-stu-id="6fcb3-103">Troubleshoot issues during initial synchronization</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="6fcb3-104">Det här avsnittet innehåller felsökningsinformation för integrering av dubbelriktad skrivning mellan Finance and Operations-appar och Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="6fcb3-104">This topic provides troubleshooting information for dual-write integration between Finance and Operations apps and Common Data Service.</span></span> <span data-ttu-id="6fcb3-105">Det ger särskilt information som kan hjälpa dig att åtgärda problem som kan uppstå under initial synkronisering.</span><span class="sxs-lookup"><span data-stu-id="6fcb3-105">Specifically, it provides information that can help you fix issues that might occur during initial synchronization.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6fcb3-106">Vissa av de problem som det här ämnet behandlar kan kräva antingen systemadministratörsrollen eller Microsoft Azure Active Directory (Azure AD) autentiseringsuppgifter för administratör för klientorganisationen.</span><span class="sxs-lookup"><span data-stu-id="6fcb3-106">Some of the issues that this topic addresses might require either the system admin role or Microsoft Azure Active Directory (Azure AD) tenant admin credentials.</span></span> <span data-ttu-id="6fcb3-107">I avsnittet för varje problem förklaras om en viss roll eller autentiseringsuppgifter krävs.</span><span class="sxs-lookup"><span data-stu-id="6fcb3-107">The section for each issue explains whether a specific role or credentials are required.</span></span>

## <a name="check-for-initial-synchronization-errors-in-a-finance-and-operations-app"></a><span data-ttu-id="6fcb3-108">Sök efter inledande synkroniseringsfel i en Finance and Operations-app</span><span class="sxs-lookup"><span data-stu-id="6fcb3-108">Check for initial synchronization errors in a Finance and Operations app</span></span>

<span data-ttu-id="6fcb3-109">När du har aktiverat mappningsmallen ska status för mappningarna **köras**.</span><span class="sxs-lookup"><span data-stu-id="6fcb3-109">After you enable the mapping templates, the status of the maps should be **Running**.</span></span> <span data-ttu-id="6fcb3-110">Om status **inte körs** har fel uppstått vid den ursprungliga synkroniseringen.</span><span class="sxs-lookup"><span data-stu-id="6fcb3-110">If the status is **Not running** , errors occurred during initial synchronization.</span></span> <span data-ttu-id="6fcb3-111">Om du vill visa felen väljer du fliken **Information om initial synkronisering** på sidan **Dubbelriktad skrivning**.</span><span class="sxs-lookup"><span data-stu-id="6fcb3-111">To view the errors, select the **Initial sync details** tab on the **Dual-write** page.</span></span>

![Fel på fliken information om inledande synkronisering](media/initial_sync_status.png)

## <a name="you-cant-complete-initial-synchronization-400-bad-request"></a><span data-ttu-id="6fcb3-113">Det går inte att slutföra den första synkroniseringen: 400 Felaktig begäran</span><span class="sxs-lookup"><span data-stu-id="6fcb3-113">You can't complete initial synchronization: 400 Bad Request</span></span>

<span data-ttu-id="6fcb3-114">**Den roll som krävs för att åtgärda problemet:** systemadministratör</span><span class="sxs-lookup"><span data-stu-id="6fcb3-114">**Required role to fix the issue:** System admin</span></span>

<span data-ttu-id="6fcb3-115">Följande felmeddelande kan visas när du försöker köra mappningen och den första synkroniseringen:</span><span class="sxs-lookup"><span data-stu-id="6fcb3-115">You might receive the following error message when you try to run the mapping and initial synchronization:</span></span>

<span data-ttu-id="6fcb3-116">*(\[Felaktig begäran\], Fjärrservern returnerade ett fel: (400) felaktig begäran.), AX exporten upptäckte ett fel*</span><span class="sxs-lookup"><span data-stu-id="6fcb3-116">*(\[Bad Request\], The remote server returned an error: (400) Bad Request.), AX export encountered an error*</span></span>

<span data-ttu-id="6fcb3-117">Här följer ett exempel på det fullständiga felmeddelandet.</span><span class="sxs-lookup"><span data-stu-id="6fcb3-117">Here is an example of the full error message.</span></span>

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

<span data-ttu-id="6fcb3-118">Om detta fel inträffar konsekvent och du inte kan slutföra den ursprungliga synkroniseringen följer du stegen nedan för att åtgärda problemet.</span><span class="sxs-lookup"><span data-stu-id="6fcb3-118">If this error occurs consistently, and you can't complete the initial synchronization, follow these steps to fix the issue.</span></span>

1. <span data-ttu-id="6fcb3-119">Logga in på den virtuella datorn (VM) för Finance and Operations-appen.</span><span class="sxs-lookup"><span data-stu-id="6fcb3-119">Sign in to the virtual machine (VM) for the Finance and Operations app.</span></span>
2. <span data-ttu-id="6fcb3-120">Öppna Microsoft Management Console.</span><span class="sxs-lookup"><span data-stu-id="6fcb3-120">Open Microsoft Management Console.</span></span>
3. <span data-ttu-id="6fcb3-121">I fönstret **tjänster** ser du till att tjänsten ramverk för dataimport och export av Microsoft Dynamics 365 körs.</span><span class="sxs-lookup"><span data-stu-id="6fcb3-121">In the **Services** pane, make sure that the Microsoft Dynamics 365 Data import export framework service is running.</span></span> <span data-ttu-id="6fcb3-122">Starta om den om den har stoppats eftersom den första synkroniseringen kräver det.</span><span class="sxs-lookup"><span data-stu-id="6fcb3-122">Restart it if it has been stopped, because the initial synchronization requires it.</span></span>

## <a name="initial-synchronization-error-403-forbidden"></a><span data-ttu-id="6fcb3-123">Fel vid första synkronisering: 403 förbud</span><span class="sxs-lookup"><span data-stu-id="6fcb3-123">Initial synchronization error: 403 Forbidden</span></span>

<span data-ttu-id="6fcb3-124">Följande felmeddelande kan visas under första synkroniseringen:</span><span class="sxs-lookup"><span data-stu-id="6fcb3-124">You might receive the following error message during initial synchronization:</span></span>

<span data-ttu-id="6fcb3-125">*(\[Förbjudet\], Fjärrservern returnerade ett fel: (403) Förbjudet.), AX-exporten upptäckte ett fel*</span><span class="sxs-lookup"><span data-stu-id="6fcb3-125">*(\[Forbidden\], The remote server returned an error: (403) Forbidden.), AX export encountered an error*</span></span>

<span data-ttu-id="6fcb3-126">Gör så här om du vill åtgärda problemet.</span><span class="sxs-lookup"><span data-stu-id="6fcb3-126">To fix the issue, follow these steps.</span></span>

1. <span data-ttu-id="6fcb3-127">Logga in på Finance and Operations-appen.</span><span class="sxs-lookup"><span data-stu-id="6fcb3-127">Sign in to the Finance and Operations app.</span></span>
2. <span data-ttu-id="6fcb3-128">På sidan **Azure Active Directory-appar** ta bort klienten **DtAppID** och lägg sedan till den igen.</span><span class="sxs-lookup"><span data-stu-id="6fcb3-128">On the **Azure Active Directory applications** page, delete the **DtAppID** client, and then add it again.</span></span>

![DtAppID-klient i listan över Azure AD-program](media/aad_applications.png)

## <a name="self-reference-or-circular-reference-failures-during-initial-synchronization"></a><span data-ttu-id="6fcb3-130">Självreferens- eller cirkulära referensfel vid inledande synkronisering</span><span class="sxs-lookup"><span data-stu-id="6fcb3-130">Self-reference or circular reference failures during initial synchronization</span></span>

<span data-ttu-id="6fcb3-131">Ett felmeddelande om någon av dina mappningar har självreferenser eller cirkulära referenser.</span><span class="sxs-lookup"><span data-stu-id="6fcb3-131">You might receive an error messages if any of your mappings have self-references or circular references.</span></span> <span data-ttu-id="6fcb3-132">Felen hör till dessa kategorier:</span><span class="sxs-lookup"><span data-stu-id="6fcb3-132">The errors fall into these categories:</span></span>

- [<span data-ttu-id="6fcb3-133">Fel i ett fel i leverantörerna V2 och entitetsmappningen</span><span class="sxs-lookup"><span data-stu-id="6fcb3-133">Errors in the Vendors V2–to–msdyn_vendors entity mapping</span></span>](#error-vendor-map)
- [<span data-ttu-id="6fcb3-134">Fel i enhetsmappning för kunder V3 till konton</span><span class="sxs-lookup"><span data-stu-id="6fcb3-134">Errors in the Customers V3–to–Accounts entity mapping</span></span>](#error-customer-map)

## <a name="resolve-errors-in-the-vendors-v2tomsdyn_vendors-entity-mapping"></a><a id="error-vendor-map"></a><span data-ttu-id="6fcb3-135">Lös fel i leverantörerna V2 och entitetsmappningen</span><span class="sxs-lookup"><span data-stu-id="6fcb3-135">Resolve errors in the Vendors V2–to–msdyn_vendors entity mapping</span></span>

<span data-ttu-id="6fcb3-136">Du kan stöta på initiala synkroniseringsfel för mappning **Leverantörer V2** till **msdyn\_vendors** om entiteterna har befintliga poster med värden i fälten **PrimaryContactPersonId** och **InvoiceVendorAccountNumber**.</span><span class="sxs-lookup"><span data-stu-id="6fcb3-136">You might encounter initial synchronization errors for the mapping of **Vendors V2** to **msdyn\_vendors** if the entities have existing records where there are values in the **PrimaryContactPersonId** and **InvoiceVendorAccountNumber** fields.</span></span> <span data-ttu-id="6fcb3-137">Dessa fel beror på att **InvoiceVendorAccountNumber** är ett självrefererande fält och att **PrimaryContactPersonId** är en cirkelreferens i leverantörsmappningen.</span><span class="sxs-lookup"><span data-stu-id="6fcb3-137">These errors occur because **InvoiceVendorAccountNumber** is a self-referencing field, and **PrimaryContactPersonId** is a circular reference in the vendor mapping.</span></span>

<span data-ttu-id="6fcb3-138">Felmeddelandena som visas kommer att ha följande format.</span><span class="sxs-lookup"><span data-stu-id="6fcb3-138">The error messages that you receive will have the following form.</span></span>

<span data-ttu-id="6fcb3-139">*Det gick inte att matcha GUID för fältet: \<field\>. Det gick inte att hitta sökningen: \<value\>. Prova denna URL för att se om referensdata existerar: `https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/<entity>?$select=<field>&$filter=<field> eq <value>`*</span><span class="sxs-lookup"><span data-stu-id="6fcb3-139">*Couldn't resolve the guid for the field: \<field\>. The lookup was not found: \<value\>. Try this URL(s) to check if the reference data exists: `https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/<entity>?$select=<field>&$filter=<field> eq <value>`*</span></span>

<span data-ttu-id="6fcb3-140">Nedan följer några exempel:</span><span class="sxs-lookup"><span data-stu-id="6fcb3-140">Here are some examples:</span></span>

- <span data-ttu-id="6fcb3-141">*Det gick inte att matcha GUID för fältet: msdyn\_vendorprimarycontactperson.msdyn\_contactpersonid. Det gick inte att hitta sökningen: 000056. Prova denna URL för att se om referensdata existerar: `https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/contacts?$select=msdyn_contactpersonid.contactid&$filter=msdyn_contactpersonid eq '000056'`*</span><span class="sxs-lookup"><span data-stu-id="6fcb3-141">*Couldn't resolve the guid for the field: msdyn\_vendorprimarycontactperson.msdyn\_contactpersonid. The lookup was not found: 000056. Try this URL(s) to check if the reference data exists: `https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/contacts?$select=msdyn_contactpersonid.contactid&$filter=msdyn_contactpersonid eq '000056'`*</span></span>
- <span data-ttu-id="6fcb3-142">*Det gick inte att matcha GUID för fältet: msdyn\_invoicevendoraccountnumber.msdyn\_vendoraccountnumber. Det gick inte att hitta sökningen: V24-1. Prova denna URL för att se om referensdata existerar: `https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/msdn_vendors?$select=msdyn_vendoraccountnumber,msdyn_vendorid&$filter=msdyn_vendoraccountnumber eq 'V24-1'`*</span><span class="sxs-lookup"><span data-stu-id="6fcb3-142">*Couldn't resolve the guid for the field: msdyn\_invoicevendoraccountnumber.msdyn\_vendoraccountnumber. The lookup was not found: V24-1. Try this URL(s) to check if the reference data exists: `https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/msdn_vendors?$select=msdyn_vendoraccountnumber,msdyn_vendorid&$filter=msdyn_vendoraccountnumber eq 'V24-1'`*</span></span>

<span data-ttu-id="6fcb3-143">Om några poster i leverantörsenheten har värden i fälten **PrimaryContactPersonId** och **InvoiceVendorAccountNumber** följ dessa steg slutföra den inledande synkroniseringen.</span><span class="sxs-lookup"><span data-stu-id="6fcb3-143">If any records in the vendor entity have values in the **PrimaryContactPersonId** and **InvoiceVendorAccountNumber** fields, follow these steps to complete the initial synchronization.</span></span>

1. <span data-ttu-id="6fcb3-144">I Finance and Operations-appen tar du bort fälten **PrimaryContactPersonId** och **InvoiceVendorAccountNumber** från mappningen och s för att spara ändringarna.</span><span class="sxs-lookup"><span data-stu-id="6fcb3-144">In the Finance and Operations app, delete the **PrimaryContactPersonId** and **InvoiceVendorAccountNumber** fields from the mapping, and then save the mapping.</span></span>

    1. <span data-ttu-id="6fcb3-145">På sidan för mappning med dubbelriktad skrivning för **leverantörer V2 (msdyn\_vendors)** på fliken **Entitetsmappningar** i vänster filter väljer du **Finance and Operations apps.Vendors V2**.</span><span class="sxs-lookup"><span data-stu-id="6fcb3-145">On the dual-write mapping page for **Vendors V2 (msdyn\_vendors)** , on the **Entity mappings** tab, in the left filter, select **Finance and Operations apps.Vendors V2**.</span></span> <span data-ttu-id="6fcb3-146">I höger filter, välj **Sales.Vendor**.</span><span class="sxs-lookup"><span data-stu-id="6fcb3-146">In the right filter, select **Sales.Vendor**.</span></span>
    2. <span data-ttu-id="6fcb3-147">Sök efter **primarycontactperson** för att hitta källfältet **PrimaryContactPersonId**.</span><span class="sxs-lookup"><span data-stu-id="6fcb3-147">Search for **primarycontactperson** to find the **PrimaryContactPersonId** source field.</span></span>
    3. <span data-ttu-id="6fcb3-148">Välj **åtgärder** och välj sedan **ta bort**.</span><span class="sxs-lookup"><span data-stu-id="6fcb3-148">Select **Actions** , and then select **Delete**.</span></span>

        ![Ta bort fältet PrimaryContactPersonId](media/vend_selfref3.png)

    4. <span data-ttu-id="6fcb3-150">Upprepa dessa steg om du vill ta bort fältet **InvoiceVendorAccountNumber**.</span><span class="sxs-lookup"><span data-stu-id="6fcb3-150">Repeat these steps to delete the **InvoiceVendorAccountNumber** field.</span></span>

        ![Ta bort fältet InvoiceVendorAccountNumber](media/vend-selfref4.png)

    5. <span data-ttu-id="6fcb3-152">Spara dina ändringar i mappningen.</span><span class="sxs-lookup"><span data-stu-id="6fcb3-152">Save your changes to the mapping.</span></span>

2. <span data-ttu-id="6fcb3-153">Inaktivera ändringsspårningen för entiteten **leverantörer V2**.</span><span class="sxs-lookup"><span data-stu-id="6fcb3-153">Turn off change tracking for the **Vendors V2** entity.</span></span>

    1. <span data-ttu-id="6fcb3-154">I arbetsytan **Datahanteringen** välj panelen **Dataentiteter**.</span><span class="sxs-lookup"><span data-stu-id="6fcb3-154">In the **Data management** workspace, select the **Data entities** tile.</span></span>
    2. <span data-ttu-id="6fcb3-155">Välj entiteten **Leverantörer V2**.</span><span class="sxs-lookup"><span data-stu-id="6fcb3-155">Select the **Vendors V2** entity.</span></span>
    3. <span data-ttu-id="6fcb3-156">I åtgärdsfönstret, välj **Alternativ** och välj sedan **Ändra spårning**.</span><span class="sxs-lookup"><span data-stu-id="6fcb3-156">On the Action Pane, select **Options** , and then select **Change tracking**.</span></span>

        ![Välja alternativet Ändringsspårning](media/selfref_options.png)

    4. <span data-ttu-id="6fcb3-158">Klicka på **inaktivera ändringsspårning**.</span><span class="sxs-lookup"><span data-stu-id="6fcb3-158">Select **Disable Change Tracking**.</span></span>

        ![Klicka på inaktivera ändringsspårning](media/selfref_tracking.png)

3. <span data-ttu-id="6fcb3-160">Kör den första synkroniseringen igen för mappningen **leverantörer V2 (msdyn\_vendors)**.</span><span class="sxs-lookup"><span data-stu-id="6fcb3-160">Run initial synchronization for the **Vendors V2 (msdyn\_vendors)** mapping.</span></span> <span data-ttu-id="6fcb3-161">Den ursprungliga synkroniseringen bör köras utan fel.</span><span class="sxs-lookup"><span data-stu-id="6fcb3-161">The initial synchronization should run successfully, without any errors.</span></span>
4. <span data-ttu-id="6fcb3-162">Kör den första synkroniseringen för mappningen **CDS-kontakter V2 (kontakter)**.</span><span class="sxs-lookup"><span data-stu-id="6fcb3-162">Run initial synchronization for the **CDS Contacts V2 (contacts)** mapping.</span></span> <span data-ttu-id="6fcb3-163">Du måste synkronisera den här mappningen om du vill synkronisera primära kontaktfält på leverantörsenheten, eftersom initial synkronisering också måste göras för kontaktposterna.</span><span class="sxs-lookup"><span data-stu-id="6fcb3-163">You must sync this mapping if you want to sync the primary contact field on the vendors entity, because initial synchronization must also be done for the contact records.</span></span>
5. <span data-ttu-id="6fcb3-164">Lägg till fälten **PrimaryContactPersonId** och **InvoiceVendorAccountNumber** tillbaka till mappningen **leverantörer V2 (msdyn\_vendors)** och spara mappningen.</span><span class="sxs-lookup"><span data-stu-id="6fcb3-164">Add the **PrimaryContactPersonId** and **InvoiceVendorAccountNumber** fields back to the **Vendors V2 (msdyn\_vendors)** mapping, and then save the mapping.</span></span>
6. <span data-ttu-id="6fcb3-165">Kör den första synkroniseringen igen för mappningen **leverantörer V2 (msdyn\_vendors)**.</span><span class="sxs-lookup"><span data-stu-id="6fcb3-165">Run initial synchronization again for the **Vendors V2 (msdyn\_vendors)** mapping.</span></span> <span data-ttu-id="6fcb3-166">Alla poster kommer att synkroniseras eftersom spårning av ändringar har inaktiverats.</span><span class="sxs-lookup"><span data-stu-id="6fcb3-166">Because change tracking is turned off, all the records will be synced.</span></span>
7. <span data-ttu-id="6fcb3-167">Aktivera tillbaka ändringsspårningen för entiteten **leverantörer V2**.</span><span class="sxs-lookup"><span data-stu-id="6fcb3-167">Turn change tracking back on for the **Vendors V2** entity.</span></span>

## <a name="resolve-errors-in-the-customers-v3toaccounts-entity-mapping"></a><a id="error-customer-map"></a><span data-ttu-id="6fcb3-168">Lös fel i enhetsmappning för kunder V3 till konton</span><span class="sxs-lookup"><span data-stu-id="6fcb3-168">Resolve errors in the Customers V3–to–Accounts entity mapping</span></span>

<span data-ttu-id="6fcb3-169">Du kan stöta på initiala synkroniseringsfel för mappning av **kunder V3** till **konton** om entiteterna har befintliga poster med värden i fälten **ContactPersonID** och **InvoiceAccount**.</span><span class="sxs-lookup"><span data-stu-id="6fcb3-169">You might encounter initial synchronization errors for the mapping of **Customers V3** to **Accounts** if the entities have existing records where there are values in the **ContactPersonID** and **InvoiceAccount** fields.</span></span> <span data-ttu-id="6fcb3-170">Dessa fel beror på att **InvoiceAccount** är ett självrefererande fält och att **ContactPersonID** är en cirkelreferens i leverantörsmappningen.</span><span class="sxs-lookup"><span data-stu-id="6fcb3-170">These errors occur because **InvoiceAccount** is a self-referencing field, and **ContactPersonID** is a circular reference in the vendor mapping.</span></span>

<span data-ttu-id="6fcb3-171">Felmeddelandena som visas kommer att ha följande format.</span><span class="sxs-lookup"><span data-stu-id="6fcb3-171">The error messages that you receive will have the following form.</span></span>

<span data-ttu-id="6fcb3-172">*Det gick inte att matcha GUID för fältet: \<field\>. Det gick inte att hitta sökningen: \<value\>. Prova denna URL för att se om referensdata existerar: `https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/<entity>?$select=<field>&$filter=<field> eq <value>`*</span><span class="sxs-lookup"><span data-stu-id="6fcb3-172">*Couldn't resolve the guid for the field: \<field\>. The lookup was not found: \<value\>. Try this URL(s) to check if the reference data exists: `https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/<entity>?$select=<field>&$filter=<field> eq <value>`*</span></span>

<span data-ttu-id="6fcb3-173">Nedan följer några exempel:</span><span class="sxs-lookup"><span data-stu-id="6fcb3-173">Here are some examples:</span></span>

- <span data-ttu-id="6fcb3-174">*Det gick inte att matcha GUID för fältet: primarycontactid.msdyn\_contactpersonid. Det gick inte att hitta sökningen: 000056. Prova denna URL för att se om referensdata existerar: `https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/contacts?$select=msdyn_contactpersonid.contactid&$filter=msdyn_contactpersonid eq '000056'`*</span><span class="sxs-lookup"><span data-stu-id="6fcb3-174">*Couldn't resolve the guid for the field: primarycontactid.msdyn\_contactpersonid. The lookup was not found: 000056. Try this URL(s) to check if the reference data exists: `https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/contacts?$select=msdyn_contactpersonid.contactid&$filter=msdyn_contactpersonid eq '000056'`*</span></span>
- <span data-ttu-id="6fcb3-175">*Det gick inte att matcha GUID för fältet: msdyn\_billingaccount.accountnumber. Det gick inte att hitta sökningen: 1206-1. Prova denna URL för att se om referensdata existerar: `https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/accounts?$select=accountnumber.account&$filter=accountnumber eq '1206-1'`*</span><span class="sxs-lookup"><span data-stu-id="6fcb3-175">*Couldn't resolve the guid for the field: msdyn\_billingaccount.accountnumber. The lookup was not found: 1206-1. Try this URL(s) to check if the reference data exists: `https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/accounts?$select=accountnumber.account&$filter=accountnumber eq '1206-1'`*</span></span>

<span data-ttu-id="6fcb3-176">Om några poster i kundenheten har värden i fälten **ContactPersonID** och **InvoiceAccount** följ dessa steg slutföra den inledande synkroniseringen.</span><span class="sxs-lookup"><span data-stu-id="6fcb3-176">If any records in the customer entity have values in the **ContactPersonID** and **InvoiceAccount** fields, follow these steps to complete the initial synchronization.</span></span> <span data-ttu-id="6fcb3-177">Du kan använda den här metoden för alla enheter utanför lådan, t.ex. **konton** och **kontakter**.</span><span class="sxs-lookup"><span data-stu-id="6fcb3-177">You can use this approach for any out-of-box entities, such **Accounts** and **Contacts**.</span></span>

1. <span data-ttu-id="6fcb3-178">I Finance and Operations-appen, ta bort fälten **ContactPersonID** och **InvoiceAccount** från **Kunder V3 (konton)** -mappningen och spara mappningen.</span><span class="sxs-lookup"><span data-stu-id="6fcb3-178">In the Finance and Operations app, delete the **ContactPersonID** and **InvoiceAccount** fields from the **Customers V3 (accounts)** mapping, and then save the mapping.</span></span>

    1. <span data-ttu-id="6fcb3-179">Navigera till mappning med dubbelriktad skrivning för **Kunder V3 (konton)** och välj fliken **enhetsmappningar**. I vänster filter, välj **Finance and Operations app.Customers V3**.</span><span class="sxs-lookup"><span data-stu-id="6fcb3-179">On the dual-write mapping page for **Customers V3 (accounts)** , on the **Entity mappings** tab, in the left filter, select **Finance and Operations app.Customers V3**.</span></span> <span data-ttu-id="6fcb3-180">I höger filter, välj **Common Data Service.Account**.</span><span class="sxs-lookup"><span data-stu-id="6fcb3-180">In the right filter, select **Common Data Service.Account**.</span></span>
    2. <span data-ttu-id="6fcb3-181">Sök efter **contactperson** för att hitta källfältet **ContactPersonID**.</span><span class="sxs-lookup"><span data-stu-id="6fcb3-181">Search for **contactperson** to find the **ContactPersonID** source field.</span></span>
    3. <span data-ttu-id="6fcb3-182">Välj **åtgärder** och välj sedan **ta bort**.</span><span class="sxs-lookup"><span data-stu-id="6fcb3-182">Select **Actions** , and then select **Delete**.</span></span>

        ![Ta bort fältet ContactPersonID](media/cust_selfref3.png)

    4. <span data-ttu-id="6fcb3-184">Upprepa dessa steg om du vill ta bort fältet **InvoiceAccount**.</span><span class="sxs-lookup"><span data-stu-id="6fcb3-184">Repeat these steps to delete the **InvoiceAccount** field.</span></span>

        ![Ta bort fältet InvoiceAccount](media/cust_selfref4.png)

    5. <span data-ttu-id="6fcb3-186">Spara dina ändringar i mappningen.</span><span class="sxs-lookup"><span data-stu-id="6fcb3-186">Save your changes to the mapping.</span></span>

2. <span data-ttu-id="6fcb3-187">Inaktivera ändringsspårningen för entiteten **Kunder V3**.</span><span class="sxs-lookup"><span data-stu-id="6fcb3-187">Turn off change tracking for the **Customers V3** entity.</span></span>

    1. <span data-ttu-id="6fcb3-188">I arbetsytan **Datahanteringen** välj panelen **Dataentiteter**.</span><span class="sxs-lookup"><span data-stu-id="6fcb3-188">In the **Data management** workspace, select the **Data entities** tile.</span></span>
    2. <span data-ttu-id="6fcb3-189">Välj entiteten **kunder V3**.</span><span class="sxs-lookup"><span data-stu-id="6fcb3-189">Select the **Customers V3** entity.</span></span>
    3. <span data-ttu-id="6fcb3-190">I åtgärdsfönstret, välj **Alternativ** och välj sedan **Ändra spårning**.</span><span class="sxs-lookup"><span data-stu-id="6fcb3-190">On the Action Pane, select **Options** , and then select **Change tracking**.</span></span>

        ![Välja alternativet Ändringsspårning](media/selfref_options.png)

    4. <span data-ttu-id="6fcb3-192">Klicka på **inaktivera ändringsspårning**.</span><span class="sxs-lookup"><span data-stu-id="6fcb3-192">Select **Disable Change Tracking**.</span></span>

        ![Klicka på inaktivera ändringsspårning](media/selfref_tracking.png)

3. <span data-ttu-id="6fcb3-194">Kör den första synkroniseringen igen för mappningen **Kunder V3 (konton)**.</span><span class="sxs-lookup"><span data-stu-id="6fcb3-194">Run initial synchronization for the **Customers V3 (Accounts)** mapping.</span></span> <span data-ttu-id="6fcb3-195">Den ursprungliga synkroniseringen bör köras utan fel.</span><span class="sxs-lookup"><span data-stu-id="6fcb3-195">The initial synchronization should run successfully, without any errors.</span></span>
4. <span data-ttu-id="6fcb3-196">Kör den första synkroniseringen för mappningen **CDS-kontakter V2 (kontakter)**.</span><span class="sxs-lookup"><span data-stu-id="6fcb3-196">Run initial synchronization for the **CDS Contacts V2 (contacts)** mapping.</span></span>

    > [!NOTE]
    > <span data-ttu-id="6fcb3-197">Det finns två mappningar med samma namn.</span><span class="sxs-lookup"><span data-stu-id="6fcb3-197">There are two maps that have the same name.</span></span> <span data-ttu-id="6fcb3-198">Se till att kartan som har följande beskrivning flik **Detaljer** : **Mall för dubbelriktad skrivning för synkronisering mellan FO.CDS Vendor Contacts V2 to CDS.Contacts. Kräver nytt paket \[Dynamics365SupplyChainExtended\].**</span><span class="sxs-lookup"><span data-stu-id="6fcb3-198">Be sure to select the map that has the following description on the **Details** tab: **Dual-write template for sync between FO.CDS Vendor Contacts V2 to CDS.Contacts. Requires new package \[Dynamics365SupplyChainExtended\].**</span></span>

5. <span data-ttu-id="6fcb3-199">Lägg till fälten **InvoiceAccount** och **ContactPersonId** tillbaka till mappningen **Kunder V3 (konton)** och spara mappningen.</span><span class="sxs-lookup"><span data-stu-id="6fcb3-199">Add the **InvoiceAccount** and **ContactPersonId** fields back to the **Customers V3 (Accounts)** mapping, and then save the mapping.</span></span> <span data-ttu-id="6fcb3-200">Nu är både fältet **InvoiceAccount** och fältet **ContactPersonId** del i ett direkt synkroniseringsläge.</span><span class="sxs-lookup"><span data-stu-id="6fcb3-200">Both the **InvoiceAccount** field and the **ContactPersonId** field are now part of live synchronization mode again.</span></span> <span data-ttu-id="6fcb3-201">I nästa steg slutför du den inledande synkroniseringen för dessa fält.</span><span class="sxs-lookup"><span data-stu-id="6fcb3-201">In the next step, you will do the initial synchronization for these fields.</span></span>
6. <span data-ttu-id="6fcb3-202">Kör den första synkroniseringen igen för mappningen **Kunder V3 (konton)**.</span><span class="sxs-lookup"><span data-stu-id="6fcb3-202">Run initial synchronization again for the **Customers V3 (Accounts)** mapping.</span></span> <span data-ttu-id="6fcb3-203">Eftersom ändringsspårning är inaktiverat kommer data för **InvoiceAccount** och **ContactPersonId** att synkroniseras från Finance and Operations-appen till Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="6fcb3-203">Because change tracking is turned off, the data for **InvoiceAccount** and **ContactPersonId** will be synced from the Finance and Operations app to Common Data Service.</span></span>
7. <span data-ttu-id="6fcb3-204">Om du vill synkronisera data för **InvoiceAccount** och **ContactPersonId** från Common Data Service till Finance and Operations-appen måste du använda ett dataintegreringsprojekt.</span><span class="sxs-lookup"><span data-stu-id="6fcb3-204">To sync the data for **InvoiceAccount** and **ContactPersonId** from Common Data Service to the Finance and Operations app, you must use a data integration project.</span></span>

    1. <span data-ttu-id="6fcb3-205">I Power Apps skapar du ett dataintegreringsprojekt mellan **Sales.Account** och **Finance and Operations-appar. Kunder V3** -enheter.</span><span class="sxs-lookup"><span data-stu-id="6fcb3-205">In Power Apps, create a data integration project between the **Sales.Account** and **Finance and Operations apps.Customers V3** entities.</span></span> <span data-ttu-id="6fcb3-206">Datariktningen måste vara från Common Data Service till Finance and Operations-appen.</span><span class="sxs-lookup"><span data-stu-id="6fcb3-206">The data direction must be from Common Data Service to the Finance and Operations app.</span></span> <span data-ttu-id="6fcb3-207">Eftersom **InvoiceAccount** är ett nytt attribut i dubbelriktad skrivning kanske du vill hoppa över den inledande synkroniseringen för det.</span><span class="sxs-lookup"><span data-stu-id="6fcb3-207">Because **InvoiceAccount** is a new attribute in dual-write, you might want to skip initial synchronization for it.</span></span> <span data-ttu-id="6fcb3-208">Mer information finns i [integrera data i Common Data Service](https://docs.microsoft.com/power-platform/admin/data-integrator).</span><span class="sxs-lookup"><span data-stu-id="6fcb3-208">For more information, see [Integrate data into Common Data Service](https://docs.microsoft.com/power-platform/admin/data-integrator).</span></span>

        <span data-ttu-id="6fcb3-209">Följande bild visar ett projekt som uppdaterar **CustomerAccount** och **ContactPersonId**.</span><span class="sxs-lookup"><span data-stu-id="6fcb3-209">The following illustration shows a project that updates **CustomerAccount** and **ContactPersonId**.</span></span>

        ![Dataintegrationsprojekt för att uppdatera CustomerAccount och ContactPersonId](media/cust_selfref6.png)

    2. <span data-ttu-id="6fcb3-211">Lägg till företagskriterierna i filtret på Common Data Service sidan, eftersom endast de poster som matchar filter villkoren kommer att uppdateras i  Finance and Operations-appen.</span><span class="sxs-lookup"><span data-stu-id="6fcb3-211">Add the company criteria in the filter on the Common Data Service side, so that only records that match the filter criteria will be updated in the Finance and Operations app.</span></span> <span data-ttu-id="6fcb3-212">Klicka på filterknappen om du vill lägga till ett filter.</span><span class="sxs-lookup"><span data-stu-id="6fcb3-212">To add a filter, select the filter button.</span></span> <span data-ttu-id="6fcb3-213">Sedan i dialogrutan **Redigera fråga** kan du lägga till en filterfråga som **\_msdyn\_company\_value eq '\<guid\>'**.</span><span class="sxs-lookup"><span data-stu-id="6fcb3-213">Then, in the **Edit query** dialog box, you can add a filter query such as **\_msdyn\_company\_value eq '\<guid\>'**.</span></span> 

        > <span data-ttu-id="6fcb3-214">[OBS] Om det inte finns någon filterknapp skapar du ett supportärende som ber dataintegrationsgruppen att aktivera filterkapaciteten för din klientorganisation.</span><span class="sxs-lookup"><span data-stu-id="6fcb3-214">[NOTE] If the filter button isn't present, create a support ticket to ask the data integration team to enable the filter capability on your tenant.</span></span>

        <span data-ttu-id="6fcb3-215">Om du inte anger någon filterfråga för **\_msdyn\_company\_value** , synkroniseras alla poster.</span><span class="sxs-lookup"><span data-stu-id="6fcb3-215">If you don't enter a filter query for **\_msdyn\_company\_value** , all the records will be synced.</span></span>

        ![Lägga till en filterfråga](media/cust_selfref7.png)

    <span data-ttu-id="6fcb3-217">Den inledande synkroniseringen av posterna har nu slutförts.</span><span class="sxs-lookup"><span data-stu-id="6fcb3-217">The initial synchronization of the records is now completed.</span></span>

8. <span data-ttu-id="6fcb3-218">I Finance and Operations-appen, aktivera tillbaka ändringsspårning på entiteten **Kunder V3**.</span><span class="sxs-lookup"><span data-stu-id="6fcb3-218">In the Finance and Operations app, turn change tracking back on for the **Customers V3** entity.</span></span>
