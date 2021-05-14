---
title: Felsöka problem under första synkroniseringen
description: Det här avsnittet innehåller felsökningsinformation som kan hjälpa dig att åtgärda problem som kan uppstå under initial synkronisering.
author: RamaKrishnamoorthy
ms.date: 03/16/2020
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: 709a3c332bb6d086910b257fee9cdec8d2bc81a2
ms.sourcegitcommit: a202bf67c3c2c054e2a47cb7b3145cb7c0ee635e
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/25/2021
ms.locfileid: "5941065"
---
# <a name="troubleshoot-issues-during-initial-synchronization"></a><span data-ttu-id="e25bb-103">Felsöka problem under första synkroniseringen</span><span class="sxs-lookup"><span data-stu-id="e25bb-103">Troubleshoot issues during initial synchronization</span></span>

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="e25bb-104">Det här avsnittet innehåller felsökningsinformation för integrering av dubbelriktad skrivning mellan Finance and Operations-appar och Dataverse.</span><span class="sxs-lookup"><span data-stu-id="e25bb-104">This topic provides troubleshooting information for dual-write integration between Finance and Operations apps and Dataverse.</span></span> <span data-ttu-id="e25bb-105">Det ger särskilt information som kan hjälpa dig att åtgärda problem som kan uppstå under initial synkronisering.</span><span class="sxs-lookup"><span data-stu-id="e25bb-105">Specifically, it provides information that can help you fix issues that might occur during initial synchronization.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e25bb-106">Vissa av de problem som det här ämnet behandlar kan kräva antingen systemadministratörsrollen eller Microsoft Azure Active Directory (Azure AD) autentiseringsuppgifter för administratör för klientorganisationen.</span><span class="sxs-lookup"><span data-stu-id="e25bb-106">Some of the issues that this topic addresses might require either the system admin role or Microsoft Azure Active Directory (Azure AD) tenant admin credentials.</span></span> <span data-ttu-id="e25bb-107">I avsnittet för varje problem förklaras om en viss roll eller autentiseringsuppgifter krävs.</span><span class="sxs-lookup"><span data-stu-id="e25bb-107">The section for each issue explains whether a specific role or credentials are required.</span></span>

## <a name="check-for-initial-synchronization-errors-in-a-finance-and-operations-app"></a><span data-ttu-id="e25bb-108">Sök efter inledande synkroniseringsfel i en Finance and Operations-app</span><span class="sxs-lookup"><span data-stu-id="e25bb-108">Check for initial synchronization errors in a Finance and Operations app</span></span>

<span data-ttu-id="e25bb-109">När du har aktiverat mappningsmallen ska status för mappningarna **köras**.</span><span class="sxs-lookup"><span data-stu-id="e25bb-109">After you enable the mapping templates, the status of the maps should be **Running**.</span></span> <span data-ttu-id="e25bb-110">Om status **inte körs** har fel uppstått vid den ursprungliga synkroniseringen.</span><span class="sxs-lookup"><span data-stu-id="e25bb-110">If the status is **Not running**, errors occurred during initial synchronization.</span></span> <span data-ttu-id="e25bb-111">Om du vill visa felen väljer du fliken **Information om initial synkronisering** på sidan **Dubbelriktad skrivning**.</span><span class="sxs-lookup"><span data-stu-id="e25bb-111">To view the errors, select the **Initial sync details** tab on the **Dual-write** page.</span></span>

![Fel på fliken information om inledande synkronisering](media/initial_sync_status.png)

## <a name="you-cant-complete-initial-synchronization-400-bad-request"></a><span data-ttu-id="e25bb-113">Det går inte att slutföra den första synkroniseringen: 400 Felaktig begäran</span><span class="sxs-lookup"><span data-stu-id="e25bb-113">You can't complete initial synchronization: 400 Bad Request</span></span>

<span data-ttu-id="e25bb-114">**Den roll som krävs för att åtgärda problemet:** systemadministratör</span><span class="sxs-lookup"><span data-stu-id="e25bb-114">**Required role to fix the issue:** System admin</span></span>

<span data-ttu-id="e25bb-115">Följande felmeddelande kan visas när du försöker köra mappningen och den första synkroniseringen:</span><span class="sxs-lookup"><span data-stu-id="e25bb-115">You might receive the following error message when you try to run the mapping and initial synchronization:</span></span>

<span data-ttu-id="e25bb-116">*(\[Felaktig begäran\], Fjärrservern returnerade ett fel: (400) felaktig begäran.), AX exporten upptäckte ett fel*</span><span class="sxs-lookup"><span data-stu-id="e25bb-116">*(\[Bad Request\], The remote server returned an error: (400) Bad Request.), AX export encountered an error*</span></span>

<span data-ttu-id="e25bb-117">Här följer ett exempel på det fullständiga felmeddelandet.</span><span class="sxs-lookup"><span data-stu-id="e25bb-117">Here is an example of the full error message.</span></span>

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

<span data-ttu-id="e25bb-118">Om detta fel inträffar konsekvent och du inte kan slutföra den ursprungliga synkroniseringen följer du stegen nedan för att åtgärda problemet.</span><span class="sxs-lookup"><span data-stu-id="e25bb-118">If this error occurs consistently, and you can't complete the initial synchronization, follow these steps to fix the issue.</span></span>

1. <span data-ttu-id="e25bb-119">Logga in på den virtuella datorn (VM) för Finance and Operations-appen.</span><span class="sxs-lookup"><span data-stu-id="e25bb-119">Sign in to the virtual machine (VM) for the Finance and Operations app.</span></span>
2. <span data-ttu-id="e25bb-120">Öppna Microsoft Management Console.</span><span class="sxs-lookup"><span data-stu-id="e25bb-120">Open Microsoft Management Console.</span></span>
3. <span data-ttu-id="e25bb-121">I fönstret **tjänster** ser du till att tjänsten ramverk för dataimport och export av Microsoft Dynamics 365 körs.</span><span class="sxs-lookup"><span data-stu-id="e25bb-121">In the **Services** pane, make sure that the Microsoft Dynamics 365 Data import export framework service is running.</span></span> <span data-ttu-id="e25bb-122">Starta om den om den har stoppats eftersom den första synkroniseringen kräver det.</span><span class="sxs-lookup"><span data-stu-id="e25bb-122">Restart it if it has been stopped, because the initial synchronization requires it.</span></span>

## <a name="initial-synchronization-error-403-forbidden"></a><span data-ttu-id="e25bb-123">Fel vid första synkronisering: 403 förbud</span><span class="sxs-lookup"><span data-stu-id="e25bb-123">Initial synchronization error: 403 Forbidden</span></span>

<span data-ttu-id="e25bb-124">Följande felmeddelande kan visas under första synkroniseringen:</span><span class="sxs-lookup"><span data-stu-id="e25bb-124">You might receive the following error message during initial synchronization:</span></span>

<span data-ttu-id="e25bb-125">*(\[Förbjudet\], Fjärrservern returnerade ett fel: (403) Förbjudet.), AX-exporten upptäckte ett fel*</span><span class="sxs-lookup"><span data-stu-id="e25bb-125">*(\[Forbidden\], The remote server returned an error: (403) Forbidden.), AX export encountered an error*</span></span>

<span data-ttu-id="e25bb-126">Gör så här om du vill åtgärda problemet.</span><span class="sxs-lookup"><span data-stu-id="e25bb-126">To fix the issue, follow these steps.</span></span>

1. <span data-ttu-id="e25bb-127">Logga in på Finance and Operations-appen.</span><span class="sxs-lookup"><span data-stu-id="e25bb-127">Sign in to the Finance and Operations app.</span></span>
2. <span data-ttu-id="e25bb-128">På sidan **Azure Active Directory-appar** ta bort klienten **DtAppID** och lägg sedan till den igen.</span><span class="sxs-lookup"><span data-stu-id="e25bb-128">On the **Azure Active Directory applications** page, delete the **DtAppID** client, and then add it again.</span></span>

![DtAppID-klient i listan över Azure AD-program](media/aad_applications.png)

## <a name="self-reference-or-circular-reference-failures-during-initial-synchronization"></a><span data-ttu-id="e25bb-130">Självreferens- eller cirkulära referensfel vid inledande synkronisering</span><span class="sxs-lookup"><span data-stu-id="e25bb-130">Self-reference or circular reference failures during initial synchronization</span></span>

<span data-ttu-id="e25bb-131">Ett felmeddelande om någon av dina mappningar har självreferenser eller cirkulära referenser.</span><span class="sxs-lookup"><span data-stu-id="e25bb-131">You might receive an error messages if any of your mappings have self-references or circular references.</span></span> <span data-ttu-id="e25bb-132">Felen hör till dessa kategorier:</span><span class="sxs-lookup"><span data-stu-id="e25bb-132">The errors fall into these categories:</span></span>

- [<span data-ttu-id="e25bb-133">Fel i tabellmappning för Leverantörer V2 till msdyn_vendors</span><span class="sxs-lookup"><span data-stu-id="e25bb-133">Errors in the Vendors V2–to–msdyn_vendors table mapping</span></span>](#error-vendor-map)
- [<span data-ttu-id="e25bb-134">Fel i tabellmappning för kunder V3 till konton</span><span class="sxs-lookup"><span data-stu-id="e25bb-134">Errors in the Customers V3–to–Accounts table mapping</span></span>](#error-customer-map)

## <a name="resolve-errors-in-the-vendors-v2tomsdyn_vendors-table-mapping"></a><a id="error-vendor-map"></a><span data-ttu-id="e25bb-135">Lös fel i tabellmappning för Leverantörer V2 till msdyn_vendors</span><span class="sxs-lookup"><span data-stu-id="e25bb-135">Resolve errors in the Vendors V2–to–msdyn_vendors table mapping</span></span>

<span data-ttu-id="e25bb-136">Du kan stöta på initiala synkroniseringsfel för mappning **Leverantörer V2** till **msdyn\_vendors** om tabellerna har befintliga rader med värden i kolumnerna **PrimaryContactPersonId** och **InvoiceVendorAccountNumber**.</span><span class="sxs-lookup"><span data-stu-id="e25bb-136">You might encounter initial synchronization errors for the mapping of **Vendors V2** to **msdyn\_vendors** if the tables have existing rows where there are values in the **PrimaryContactPersonId** and **InvoiceVendorAccountNumber** columns.</span></span> <span data-ttu-id="e25bb-137">Dessa fel beror på att **InvoiceVendorAccountNumber** är ett självrefererande kolumn och att **PrimaryContactPersonId** är en cirkelreferens i leverantörsmappningen.</span><span class="sxs-lookup"><span data-stu-id="e25bb-137">These errors occur because **InvoiceVendorAccountNumber** is a self-referencing column, and **PrimaryContactPersonId** is a circular reference in the vendor mapping.</span></span>

<span data-ttu-id="e25bb-138">Felmeddelandena som visas kommer att ha följande format.</span><span class="sxs-lookup"><span data-stu-id="e25bb-138">The error messages that you receive will have the following form.</span></span>

<span data-ttu-id="e25bb-139">*Det gick inte att matcha GUID för fältet: \<field\>. Det gick inte att hitta sökningen: \<value\>. Prova denna URL för att se om referensdata existerar: `https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/<entity>?$select=<field>&$filter=<field> eq <value>`*</span><span class="sxs-lookup"><span data-stu-id="e25bb-139">*Couldn't resolve the guid for the field: \<field\>. The lookup was not found: \<value\>. Try this URL(s) to check if the reference data exists: `https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/<entity>?$select=<field>&$filter=<field> eq <value>`*</span></span>

<span data-ttu-id="e25bb-140">Nedan följer några exempel:</span><span class="sxs-lookup"><span data-stu-id="e25bb-140">Here are some examples:</span></span>

- <span data-ttu-id="e25bb-141">*Det gick inte att matcha GUID för fältet: msdyn\_vendorprimarycontactperson.msdyn\_contactpersonid. Det gick inte att hitta sökningen: 000056. Prova denna URL för att se om referensdata existerar: `https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/contacts?$select=msdyn_contactpersonid.contactid&$filter=msdyn_contactpersonid eq '000056'`*</span><span class="sxs-lookup"><span data-stu-id="e25bb-141">*Couldn't resolve the guid for the field: msdyn\_vendorprimarycontactperson.msdyn\_contactpersonid. The lookup was not found: 000056. Try this URL(s) to check if the reference data exists: `https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/contacts?$select=msdyn_contactpersonid.contactid&$filter=msdyn_contactpersonid eq '000056'`*</span></span>
- <span data-ttu-id="e25bb-142">*Det gick inte att matcha GUID för fältet: msdyn\_invoicevendoraccountnumber.msdyn\_vendoraccountnumber. Det gick inte att hitta sökningen: V24-1. Prova denna URL för att se om referensdata existerar: `https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/msdn_vendors?$select=msdyn_vendoraccountnumber,msdyn_vendorid&$filter=msdyn_vendoraccountnumber eq 'V24-1'`*</span><span class="sxs-lookup"><span data-stu-id="e25bb-142">*Couldn't resolve the guid for the field: msdyn\_invoicevendoraccountnumber.msdyn\_vendoraccountnumber. The lookup was not found: V24-1. Try this URL(s) to check if the reference data exists: `https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/msdn_vendors?$select=msdyn_vendoraccountnumber,msdyn_vendorid&$filter=msdyn_vendoraccountnumber eq 'V24-1'`*</span></span>

<span data-ttu-id="e25bb-143">Om några rader i leverantörstabellen har värden i kolumnen **PrimaryContactPersonId** och **InvoiceVendorAccountNumber** ska du följa dessa steg slutföra den inledande synkroniseringen.</span><span class="sxs-lookup"><span data-stu-id="e25bb-143">If any rows in the vendor table have values in the **PrimaryContactPersonId** and **InvoiceVendorAccountNumber** columns, follow these steps to complete the initial synchronization.</span></span>

1. <span data-ttu-id="e25bb-144">I Finance and Operations-appen tar du bort kolumnen **PrimaryContactPersonId** och **InvoiceVendorAccountNumber** från mappningen och s för att spara ändringarna.</span><span class="sxs-lookup"><span data-stu-id="e25bb-144">In the Finance and Operations app, delete the **PrimaryContactPersonId** and **InvoiceVendorAccountNumber** columns from the mapping, and then save the mapping.</span></span>

    1. <span data-ttu-id="e25bb-145">På sidan för mappning med dubbelriktad skrivning för **Leverantörer V2 (msdyn\_vendors)** på fliken **Tabellmappningar** väljer du **Finance and Operations apps.Vendors V2**.</span><span class="sxs-lookup"><span data-stu-id="e25bb-145">On the dual-write mapping page for **Vendors V2 (msdyn\_vendors)**, on the **Table mappings** tab, in the left filter, select **Finance and Operations apps.Vendors V2**.</span></span> <span data-ttu-id="e25bb-146">I höger filter, välj **Sales.Vendor**.</span><span class="sxs-lookup"><span data-stu-id="e25bb-146">In the right filter, select **Sales.Vendor**.</span></span>
    2. <span data-ttu-id="e25bb-147">Sök efter **primarycontactperson** för att hitta källkolumen **PrimaryContactPersonId**.</span><span class="sxs-lookup"><span data-stu-id="e25bb-147">Search for **primarycontactperson** to find the **PrimaryContactPersonId** source column.</span></span>
    3. <span data-ttu-id="e25bb-148">Välj **åtgärder** och välj sedan **ta bort**.</span><span class="sxs-lookup"><span data-stu-id="e25bb-148">Select **Actions**, and then select **Delete**.</span></span>

        ![Ta bort kolumnen PrimaryContactPersonId](media/vend_selfref3.png)

    4. <span data-ttu-id="e25bb-150">Upprepa dessa steg om du vill ta bort kolumnen **InvoiceVendorAccountNumber**.</span><span class="sxs-lookup"><span data-stu-id="e25bb-150">Repeat these steps to delete the **InvoiceVendorAccountNumber** column.</span></span>

        ![Ta bort kolumnen InvoiceVendorAccountNumber](media/vend-selfref4.png)

    5. <span data-ttu-id="e25bb-152">Spara dina ändringar i mappningen.</span><span class="sxs-lookup"><span data-stu-id="e25bb-152">Save your changes to the mapping.</span></span>

2. <span data-ttu-id="e25bb-153">Inaktivera ändringsspårningen för tabellen **leverantörer V2**.</span><span class="sxs-lookup"><span data-stu-id="e25bb-153">Turn off change tracking for the **Vendors V2** table.</span></span>

    1. <span data-ttu-id="e25bb-154">I arbetsytan **Datahantering** väljer du panelen **Datatabeller**.</span><span class="sxs-lookup"><span data-stu-id="e25bb-154">In the **Data management** workspace, select the **Data tables** tile.</span></span>
    2. <span data-ttu-id="e25bb-155">Välj tabellen **Leverantörer V2**.</span><span class="sxs-lookup"><span data-stu-id="e25bb-155">Select the **Vendors V2** table.</span></span>
    3. <span data-ttu-id="e25bb-156">I åtgärdsfönstret, välj **Alternativ** och välj sedan **Ändra spårning**.</span><span class="sxs-lookup"><span data-stu-id="e25bb-156">On the Action Pane, select **Options**, and then select **Change tracking**.</span></span>

        ![Välja alternativet Ändringsspårning](media/selfref_options.png)

    4. <span data-ttu-id="e25bb-158">Klicka på **inaktivera ändringsspårning**.</span><span class="sxs-lookup"><span data-stu-id="e25bb-158">Select **Disable Change Tracking**.</span></span>

        ![Klicka på inaktivera ändringsspårning](media/selfref_tracking.png)

3. <span data-ttu-id="e25bb-160">Kör den första synkroniseringen igen för mappningen **leverantörer V2 (msdyn\_vendors)**.</span><span class="sxs-lookup"><span data-stu-id="e25bb-160">Run initial synchronization for the **Vendors V2 (msdyn\_vendors)** mapping.</span></span> <span data-ttu-id="e25bb-161">Den ursprungliga synkroniseringen bör köras utan fel.</span><span class="sxs-lookup"><span data-stu-id="e25bb-161">The initial synchronization should run successfully, without any errors.</span></span>
4. <span data-ttu-id="e25bb-162">Kör den första synkroniseringen för mappningen **CDS-kontakter V2 (kontakter)**.</span><span class="sxs-lookup"><span data-stu-id="e25bb-162">Run initial synchronization for the **CDS Contacts V2 (contacts)** mapping.</span></span> <span data-ttu-id="e25bb-163">Du måste synkronisera den här mappningen om du vill synkronisera primära kontaktkolumnen på leverantörstabellen, eftersom initial synkronisering också måste göras för kontaktraderna.</span><span class="sxs-lookup"><span data-stu-id="e25bb-163">You must sync this mapping if you want to sync the primary contact column on the vendors table, because initial synchronization must also be done for the contact rows.</span></span>
5. <span data-ttu-id="e25bb-164">Lägg till kolumnen **PrimaryContactPersonId** och **InvoiceVendorAccountNumber** tillbaka till mappningen **leverantörer V2 (msdyn\_vendors)** och spara mappningen.</span><span class="sxs-lookup"><span data-stu-id="e25bb-164">Add the **PrimaryContactPersonId** and **InvoiceVendorAccountNumber** columns back to the **Vendors V2 (msdyn\_vendors)** mapping, and then save the mapping.</span></span>
6. <span data-ttu-id="e25bb-165">Kör den första synkroniseringen igen för mappningen **leverantörer V2 (msdyn\_vendors)**.</span><span class="sxs-lookup"><span data-stu-id="e25bb-165">Run initial synchronization again for the **Vendors V2 (msdyn\_vendors)** mapping.</span></span> <span data-ttu-id="e25bb-166">Alla rader kommer att synkroniseras eftersom spårning av ändringar har inaktiverats.</span><span class="sxs-lookup"><span data-stu-id="e25bb-166">Because change tracking is turned off, all the rows will be synced.</span></span>
7. <span data-ttu-id="e25bb-167">Aktivera tillbaka ändringsspårningen för tabellen **leverantörer V2**.</span><span class="sxs-lookup"><span data-stu-id="e25bb-167">Turn change tracking back on for the **Vendors V2** table.</span></span>

## <a name="resolve-errors-in-the-customers-v3toaccounts-table-mapping"></a><a id="error-customer-map"></a><span data-ttu-id="e25bb-168">Lös fel i tabellmappning för Kunder V3 till konton</span><span class="sxs-lookup"><span data-stu-id="e25bb-168">Resolve errors in the Customers V3–to–Accounts table mapping</span></span>

<span data-ttu-id="e25bb-169">Du kan stöta på initiala synkroniseringsfel för mappning av **Kunder V3** till **Konton** om kolumner har befintliga rader med värden i fälten **ContactPersonID** och **InvoiceAccount**.</span><span class="sxs-lookup"><span data-stu-id="e25bb-169">You might encounter initial synchronization errors for the mapping of **Customers V3** to **Accounts** if the tables have existing rows where there are values in the **ContactPersonID** and **InvoiceAccount** columns.</span></span> <span data-ttu-id="e25bb-170">Dessa fel beror på att **InvoiceAccount** är ett självrefererande kolumnen och att **ContactPersonID** är en cirkelreferens i leverantörsmappningen.</span><span class="sxs-lookup"><span data-stu-id="e25bb-170">These errors occur because **InvoiceAccount** is a self-referencing column, and **ContactPersonID** is a circular reference in the vendor mapping.</span></span>

<span data-ttu-id="e25bb-171">Felmeddelandena som visas kommer att ha följande format.</span><span class="sxs-lookup"><span data-stu-id="e25bb-171">The error messages that you receive will have the following form.</span></span>

<span data-ttu-id="e25bb-172">*Det gick inte att matcha GUID för fältet: \<field\>. Det gick inte att hitta sökningen: \<value\>. Prova denna URL för att se om referensdata existerar: `https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/<entity>?$select=<field>&$filter=<field> eq <value>`*</span><span class="sxs-lookup"><span data-stu-id="e25bb-172">*Couldn't resolve the guid for the field: \<field\>. The lookup was not found: \<value\>. Try this URL(s) to check if the reference data exists: `https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/<entity>?$select=<field>&$filter=<field> eq <value>`*</span></span>

<span data-ttu-id="e25bb-173">Nedan följer några exempel:</span><span class="sxs-lookup"><span data-stu-id="e25bb-173">Here are some examples:</span></span>

- <span data-ttu-id="e25bb-174">*Det gick inte att matcha GUID för fältet: primarycontactid.msdyn\_contactpersonid. Det gick inte att hitta sökningen: 000056. Prova denna URL för att se om referensdata existerar: `https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/contacts?$select=msdyn_contactpersonid.contactid&$filter=msdyn_contactpersonid eq '000056'`*</span><span class="sxs-lookup"><span data-stu-id="e25bb-174">*Couldn't resolve the guid for the field: primarycontactid.msdyn\_contactpersonid. The lookup was not found: 000056. Try this URL(s) to check if the reference data exists: `https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/contacts?$select=msdyn_contactpersonid.contactid&$filter=msdyn_contactpersonid eq '000056'`*</span></span>
- <span data-ttu-id="e25bb-175">*Det gick inte att matcha GUID för fältet: msdyn\_billingaccount.accountnumber. Det gick inte att hitta sökningen: 1206-1. Prova denna URL för att se om referensdata existerar: `https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/accounts?$select=accountnumber.account&$filter=accountnumber eq '1206-1'`*</span><span class="sxs-lookup"><span data-stu-id="e25bb-175">*Couldn't resolve the guid for the field: msdyn\_billingaccount.accountnumber. The lookup was not found: 1206-1. Try this URL(s) to check if the reference data exists: `https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/accounts?$select=accountnumber.account&$filter=accountnumber eq '1206-1'`*</span></span>

<span data-ttu-id="e25bb-176">Om några rader i kundtabellen har värden i kolumner **ContactPersonID** och **InvoiceAccount** ska du följa dessa steg för att slutföra den inledande synkroniseringen.</span><span class="sxs-lookup"><span data-stu-id="e25bb-176">If any rows in the customer table have values in the **ContactPersonID** and **InvoiceAccount** columns, follow these steps to complete the initial synchronization.</span></span> <span data-ttu-id="e25bb-177">Du kan använda den här metoden för alla tabeller utanför lådan, t.ex. **Konton** och **Kontakter**.</span><span class="sxs-lookup"><span data-stu-id="e25bb-177">You can use this approach for any out-of-box tables, such **Accounts** and **Contacts**.</span></span>

1. <span data-ttu-id="e25bb-178">I Finance and Operations-appen, ta bort kolumner **ContactPersonID** och **InvoiceAccount** från **Kunder V3 (konton)**-mappningen och spara mappningen.</span><span class="sxs-lookup"><span data-stu-id="e25bb-178">In the Finance and Operations app, delete the **ContactPersonID** and **InvoiceAccount** columns from the **Customers V3 (accounts)** mapping, and then save the mapping.</span></span>

    1. <span data-ttu-id="e25bb-179">Navigera till sidan för mappning med dubbelriktad skrivning för **Kunder V3 (konton)** och välj fliken **Tabellmappningar** i vänster filter och välj **Finance and Operations app.Customers V3**.</span><span class="sxs-lookup"><span data-stu-id="e25bb-179">On the dual-write mapping page for **Customers V3 (accounts)**, on the **Table mappings** tab, in the left filter, select **Finance and Operations app.Customers V3**.</span></span> <span data-ttu-id="e25bb-180">I höger filter, välj **Dataverse.Account**.</span><span class="sxs-lookup"><span data-stu-id="e25bb-180">In the right filter, select **Dataverse.Account**.</span></span>
    2. <span data-ttu-id="e25bb-181">Sök efter **contactperson** för att hitta källkolumnen **ContactPersonID**.</span><span class="sxs-lookup"><span data-stu-id="e25bb-181">Search for **contactperson** to find the **ContactPersonID** source column.</span></span>
    3. <span data-ttu-id="e25bb-182">Välj **åtgärder** och välj sedan **ta bort**.</span><span class="sxs-lookup"><span data-stu-id="e25bb-182">Select **Actions**, and then select **Delete**.</span></span>

        ![Ta bort kolumnen ContactPersonID](media/cust_selfref3.png)

    4. <span data-ttu-id="e25bb-184">Upprepa dessa steg om du vill ta bort kolumnen **InvoiceAccount**.</span><span class="sxs-lookup"><span data-stu-id="e25bb-184">Repeat these steps to delete the **InvoiceAccount** column.</span></span>

        ![Ta bort kolumnen InvoiceAccount](media/cust_selfref4.png)

    5. <span data-ttu-id="e25bb-186">Spara dina ändringar i mappningen.</span><span class="sxs-lookup"><span data-stu-id="e25bb-186">Save your changes to the mapping.</span></span>

2. <span data-ttu-id="e25bb-187">Inaktivera ändringsspårningen för tabellen **Kunder V3**.</span><span class="sxs-lookup"><span data-stu-id="e25bb-187">Turn off change tracking for the **Customers V3** table.</span></span>

    1. <span data-ttu-id="e25bb-188">I arbetsytan **Datahantering** väljer du panelen **Datatabeller**.</span><span class="sxs-lookup"><span data-stu-id="e25bb-188">In the **Data management** workspace, select the **Data tables** tile.</span></span>
    2. <span data-ttu-id="e25bb-189">Välj tabellen **kunder V3**.</span><span class="sxs-lookup"><span data-stu-id="e25bb-189">Select the **Customers V3** table.</span></span>
    3. <span data-ttu-id="e25bb-190">I åtgärdsfönstret, välj **Alternativ** och välj sedan **Ändra spårning**.</span><span class="sxs-lookup"><span data-stu-id="e25bb-190">On the Action Pane, select **Options**, and then select **Change tracking**.</span></span>

        ![Välja alternativet Ändringsspårning](media/selfref_options.png)

    4. <span data-ttu-id="e25bb-192">Klicka på **inaktivera ändringsspårning**.</span><span class="sxs-lookup"><span data-stu-id="e25bb-192">Select **Disable Change Tracking**.</span></span>

        ![Klicka på inaktivera ändringsspårning](media/selfref_tracking.png)

3. <span data-ttu-id="e25bb-194">Kör den första synkroniseringen igen för mappningen **Kunder V3 (konton)**.</span><span class="sxs-lookup"><span data-stu-id="e25bb-194">Run initial synchronization for the **Customers V3 (Accounts)** mapping.</span></span> <span data-ttu-id="e25bb-195">Den ursprungliga synkroniseringen bör köras utan fel.</span><span class="sxs-lookup"><span data-stu-id="e25bb-195">The initial synchronization should run successfully, without any errors.</span></span>
4. <span data-ttu-id="e25bb-196">Kör den första synkroniseringen för mappningen **CDS-kontakter V2 (kontakter)**.</span><span class="sxs-lookup"><span data-stu-id="e25bb-196">Run initial synchronization for the **CDS Contacts V2 (contacts)** mapping.</span></span>

    > [!NOTE]
    > <span data-ttu-id="e25bb-197">Det finns två mappningar med samma namn.</span><span class="sxs-lookup"><span data-stu-id="e25bb-197">There are two maps that have the same name.</span></span> <span data-ttu-id="e25bb-198">Se till att kartan som har följande beskrivning flik **Detaljer**: **Mall för dubbelriktad skrivning för synkronisering mellan FO.CDS Vendor Contacts V2 to CDS.Contacts. Kräver nytt paket \[Dynamics365SupplyChainExtended\].**</span><span class="sxs-lookup"><span data-stu-id="e25bb-198">Be sure to select the map that has the following description on the **Details** tab: **Dual-write template for sync between FO.CDS Vendor Contacts V2 to CDS.Contacts. Requires new package \[Dynamics365SupplyChainExtended\].**</span></span>

5. <span data-ttu-id="e25bb-199">Lägg till kolumner **InvoiceAccount** och **ContactPersonId** tillbaka till mappningen **Kunder V3 (konton)** och spara mappningen.</span><span class="sxs-lookup"><span data-stu-id="e25bb-199">Add the **InvoiceAccount** and **ContactPersonId** columns back to the **Customers V3 (Accounts)** mapping, and then save the mapping.</span></span> <span data-ttu-id="e25bb-200">Nu är både kolumnen **InvoiceAccount** och kolumnen **ContactPersonId** del i ett direkt synkroniseringsläge.</span><span class="sxs-lookup"><span data-stu-id="e25bb-200">Both the **InvoiceAccount** column and the **ContactPersonId** column are now part of live synchronization mode again.</span></span> <span data-ttu-id="e25bb-201">I nästa steg slutför du den inledande synkroniseringen för dessa kolumner.</span><span class="sxs-lookup"><span data-stu-id="e25bb-201">In the next step, you will do the initial synchronization for these columns.</span></span>
6. <span data-ttu-id="e25bb-202">Kör den första synkroniseringen igen för mappningen **Kunder V3 (konton)**.</span><span class="sxs-lookup"><span data-stu-id="e25bb-202">Run initial synchronization again for the **Customers V3 (Accounts)** mapping.</span></span> <span data-ttu-id="e25bb-203">Eftersom ändringsspårning är inaktiverat kommer data för **InvoiceAccount** och **ContactPersonId** att synkroniseras från Finance and Operations-appen till Dataverse.</span><span class="sxs-lookup"><span data-stu-id="e25bb-203">Because change tracking is turned off, the data for **InvoiceAccount** and **ContactPersonId** will be synced from the Finance and Operations app to Dataverse.</span></span>
7. <span data-ttu-id="e25bb-204">Om du vill synkronisera data för **InvoiceAccount** och **ContactPersonId** från Dataverse till Finance and Operations-appen måste du använda ett dataintegreringsprojekt.</span><span class="sxs-lookup"><span data-stu-id="e25bb-204">To sync the data for **InvoiceAccount** and **ContactPersonId** from Dataverse to the Finance and Operations app, you must use a data integration project.</span></span>

    1. <span data-ttu-id="e25bb-205">I Power Apps skapar du ett dataintegreringsprojekt mellan **Sales.Account** och **Finance and Operations-appar. Kunder V3**-tabeller.</span><span class="sxs-lookup"><span data-stu-id="e25bb-205">In Power Apps, create a data integration project between the **Sales.Account** and **Finance and Operations apps.Customers V3** tables.</span></span> <span data-ttu-id="e25bb-206">Datariktningen måste vara från Dataverse till Finance and Operations-appen.</span><span class="sxs-lookup"><span data-stu-id="e25bb-206">The data direction must be from Dataverse to the Finance and Operations app.</span></span> <span data-ttu-id="e25bb-207">Eftersom **InvoiceAccount** är ett nytt attribut i dubbelriktad skrivning kanske du vill hoppa över den inledande synkroniseringen för det.</span><span class="sxs-lookup"><span data-stu-id="e25bb-207">Because **InvoiceAccount** is a new attribute in dual-write, you might want to skip initial synchronization for it.</span></span> <span data-ttu-id="e25bb-208">Mer information finns i [integrera data i Dataverse](/power-platform/admin/data-integrator).</span><span class="sxs-lookup"><span data-stu-id="e25bb-208">For more information, see [Integrate data into Dataverse](/power-platform/admin/data-integrator).</span></span>

        <span data-ttu-id="e25bb-209">Följande bild visar ett projekt som uppdaterar **CustomerAccount** och **ContactPersonId**.</span><span class="sxs-lookup"><span data-stu-id="e25bb-209">The following illustration shows a project that updates **CustomerAccount** and **ContactPersonId**.</span></span>

        ![Dataintegrationsprojekt för att uppdatera CustomerAccount och ContactPersonId](media/cust_selfref6.png)

    2. <span data-ttu-id="e25bb-211">Lägg till företagskriterierna i filtret på Dataverse-sidan, eftersom endast de poster som matchar filtervillkoren kommer att uppdateras i Finance and Operations-appen.</span><span class="sxs-lookup"><span data-stu-id="e25bb-211">Add the company criteria in the filter on the Dataverse side, so that only rows that match the filter criteria will be updated in the Finance and Operations app.</span></span> <span data-ttu-id="e25bb-212">Klicka på filterknappen om du vill lägga till ett filter.</span><span class="sxs-lookup"><span data-stu-id="e25bb-212">To add a filter, select the filter button.</span></span> <span data-ttu-id="e25bb-213">Sedan i dialogrutan **Redigera fråga** kan du lägga till en filterfråga som **\_msdyn\_company\_value eq '\<guid\>'**.</span><span class="sxs-lookup"><span data-stu-id="e25bb-213">Then, in the **Edit query** dialog box, you can add a filter query such as **\_msdyn\_company\_value eq '\<guid\>'**.</span></span> 

        > <span data-ttu-id="e25bb-214">[OBS] Om det inte finns någon filterknapp skapar du ett supportärende som ber dataintegrationsgruppen att aktivera filterkapaciteten för din klientorganisation.</span><span class="sxs-lookup"><span data-stu-id="e25bb-214">[NOTE] If the filter button isn't present, create a support ticket to ask the data integration team to enable the filter capability on your tenant.</span></span>

        <span data-ttu-id="e25bb-215">Om du inte anger någon filterfråga för **\_msdyn\_company\_value**, synkroniseras alla rader.</span><span class="sxs-lookup"><span data-stu-id="e25bb-215">If you don't enter a filter query for **\_msdyn\_company\_value**, all the rows will be synced.</span></span>

        ![Lägga till en filterfråga](media/cust_selfref7.png)

    <span data-ttu-id="e25bb-217">Den inledande synkroniseringen av raderna har nu slutförts.</span><span class="sxs-lookup"><span data-stu-id="e25bb-217">The initial synchronization of the rows is now completed.</span></span>

8. <span data-ttu-id="e25bb-218">I Finance and Operations-appen, aktivera tillbaka ändringsspårning på tabellen **Kunder V3**.</span><span class="sxs-lookup"><span data-stu-id="e25bb-218">In the Finance and Operations app, turn change tracking back on for the **Customers V3** table.</span></span>


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]