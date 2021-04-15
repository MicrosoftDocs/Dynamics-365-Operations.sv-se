---
title: Faktura för underhåll av kundägda tillgångar
description: I det här avsnittet beskrivs hur du skapar, bearbetar och fakturerar underhåll som utförs på tillgångar som dina kunder äger.
author: johanhoffmann
ms.date: 01/28/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ProjProjectContractsListPage, ProjInvoiceTable, ProjProjectsListPage, ProjTable, EntAssetWorkOrderType, EntAssetWorkOrderProjectSetup, EntAssetObjectTable, EntAssetWorkOrderTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2021-01-28
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 5532f1ce14239002022f487f227286efe10abf12
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5813807"
---
# <a name="bill-for-maintenance-on-customer-owned-assets"></a><span data-ttu-id="9a796-103">Faktura för underhåll av kundägda tillgångar</span><span class="sxs-lookup"><span data-stu-id="9a796-103">Bill for maintenance on customer-owned assets</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="9a796-104">Med hjälp av funktionen *Fakturering av arbetsorder* låter dig skapa, bearbeta och fakturera underhållsarbete som utförs på tillgångar som dina kunder äger.</span><span class="sxs-lookup"><span data-stu-id="9a796-104">The *Work order billing* feature lets you create, process, and bill maintenance work that is done on assets that your customers own.</span></span> <span data-ttu-id="9a796-105">Denna funktion låter dig utföra följande uppgifter:</span><span class="sxs-lookup"><span data-stu-id="9a796-105">This feature lets you perform the following tasks:</span></span>

- <span data-ttu-id="9a796-106">Koppla kunder till tillgångarna de äger.</span><span class="sxs-lookup"><span data-stu-id="9a796-106">Connect customers to the assets that they own.</span></span>
- <span data-ttu-id="9a796-107">Välj en kund och visa de tillgångar som kunden äger när du skapar en arbetsorder.</span><span class="sxs-lookup"><span data-stu-id="9a796-107">Select a customer and view the assets that customer owns when you create a work order.</span></span>
- <span data-ttu-id="9a796-108">Ställ in ett överordnat projekt för varje kund.</span><span class="sxs-lookup"><span data-stu-id="9a796-108">Set up a parent project for each customer.</span></span>
- <span data-ttu-id="9a796-109">Registrera timmar, artiklar, utgifter och avgifter mot arbetsordern, och skapa sedan ett fakturaförslag för kunden senare.</span><span class="sxs-lookup"><span data-stu-id="9a796-109">Register hours, items, expenses, and fees against the work order, and then create an invoice proposal for the customer later.</span></span>

<span data-ttu-id="9a796-110">Funktionen innehåller dessutom följande funktioner:</span><span class="sxs-lookup"><span data-stu-id="9a796-110">In addition, the feature provides the following functionality:</span></span>

- <span data-ttu-id="9a796-111">Projektkontraktet från en kunds överordnade projekt kopieras automatiskt till det relevanta arbetsorderprojektet.</span><span class="sxs-lookup"><span data-stu-id="9a796-111">The project contract from a customer's parent project is automatically copied to the relevant work order project.</span></span>
- <span data-ttu-id="9a796-112">Nu kan tillgångshanteringen använda projekttransaktionstyp *avgift* på både arbetsorderprognoser och arbetsorderjournaler.</span><span class="sxs-lookup"><span data-stu-id="9a796-112">Asset management can now use the *fee* project transaction type on both work order forecasts and work order journals.</span></span>

## <a name="turn-on-the-customer-billing-feature"></a><span data-ttu-id="9a796-113">Aktivera funktionen för kundbetalning</span><span class="sxs-lookup"><span data-stu-id="9a796-113">Turn on the customer billing feature</span></span>

<span data-ttu-id="9a796-114">Innan du kan använda den här funktionen den aktiveras i ditt system.</span><span class="sxs-lookup"><span data-stu-id="9a796-114">Before you can use this feature, it must be turned on in your system.</span></span> <span data-ttu-id="9a796-115">Administratörer kan använda inställningarna [funktionshantering](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) för att kontrollera funktionens status och aktivera den.</span><span class="sxs-lookup"><span data-stu-id="9a796-115">Admins can use the [feature management](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) settings to check the status of the feature and turn it on.</span></span> <span data-ttu-id="9a796-116">I arbetsytan **utgiftshantering** anges den här funktionen på följande sätt:</span><span class="sxs-lookup"><span data-stu-id="9a796-116">In the **Feature management** workspace, the feature is listed in the following way:</span></span>

- <span data-ttu-id="9a796-117">**Modul:** *Projekthantering och redovisning*</span><span class="sxs-lookup"><span data-stu-id="9a796-117">**Module:** *Project management and accounting*</span></span>
- <span data-ttu-id="9a796-118">**Funktionsnamn:** *Fakturering av arbetsorder*</span><span class="sxs-lookup"><span data-stu-id="9a796-118">**Feature name:** *Work order billing*</span></span>

## <a name="example-scenario"></a><span data-ttu-id="9a796-119">Exempelscenario</span><span class="sxs-lookup"><span data-stu-id="9a796-119">Example scenario</span></span>

<span data-ttu-id="9a796-120">Om du vill veta hur funktionen fungerar arbetar du med följande exempelscenario.</span><span class="sxs-lookup"><span data-stu-id="9a796-120">To learn how this feature works, work through the following example scenario.</span></span>

<span data-ttu-id="9a796-121">Om du vill arbeta genom detta scenario med hjälp av de exempelposter och värden som anges här måste du använda ett system där standard [demodata](../../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) har installerats.</span><span class="sxs-lookup"><span data-stu-id="9a796-121">To work through this scenario by using the sample records and values that are specified here, you must be on a system where the standard [demo data](../../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) is installed.</span></span> <span data-ttu-id="9a796-122">Du måste välja den **USMF** juridiska personen innan du börjar.</span><span class="sxs-lookup"><span data-stu-id="9a796-122">You must select the **USMF** legal entity before you begin.</span></span>

<span data-ttu-id="9a796-123">Du kan också använda detta scenario som vägledning för funktionen när du arbetar med ett produktionssystem.</span><span class="sxs-lookup"><span data-stu-id="9a796-123">You can also use this scenario as guidance for using the feature when you work on a production system.</span></span> <span data-ttu-id="9a796-124">I så fall måste du emellertid ersätta dina egna värden och du kanske saknar vissa typer av obligatoriska poster som används i standard demodata.</span><span class="sxs-lookup"><span data-stu-id="9a796-124">However, in that case, you must substitute your own values, and you might be missing some types of required records that the standard demo data provides.</span></span>

### <a name="step-1-create-a-new-project-contract-for-the-customer"></a><span data-ttu-id="9a796-125">Steg 1: Skapa ett nytt projektkontrakt för kunden</span><span class="sxs-lookup"><span data-stu-id="9a796-125">Step 1: Create a new project contract for the customer</span></span>

1. <span data-ttu-id="9a796-126">Gå till **Projekthantering och redovisning \> Projekt \> Projektkontrakt**.</span><span class="sxs-lookup"><span data-stu-id="9a796-126">Go to **Project management and accounting \> Projects \> Project contracts**.</span></span>
1. <span data-ttu-id="9a796-127">Klicka på **Ny** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="9a796-127">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="9a796-128">I dialogrutan **nytt projektkontrakt** anger du följande värden:</span><span class="sxs-lookup"><span data-stu-id="9a796-128">In the **New project contract** dialog box, set the following values:</span></span>

    - <span data-ttu-id="9a796-129">**Namn:** *Pelican Wholesales*</span><span class="sxs-lookup"><span data-stu-id="9a796-129">**Name:** *Pelican Wholesales*</span></span>
    - <span data-ttu-id="9a796-130">**Finansieringstyp:** *Kund*</span><span class="sxs-lookup"><span data-stu-id="9a796-130">**Funding type:** *Customer*</span></span>
    - <span data-ttu-id="9a796-131">**Finansieringskälla:** *US-013* (*Pelican Wholesales*)</span><span class="sxs-lookup"><span data-stu-id="9a796-131">**Funding source:** *US-013* (*Pelican Wholesales*)</span></span>

1. <span data-ttu-id="9a796-132">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="9a796-132">Select **OK**.</span></span>

### <a name="step-2-create-a-new-parent-project-for-the-customer"></a><span data-ttu-id="9a796-133">Steg 2: Skapa ett nytt överordnat projekt för kunden</span><span class="sxs-lookup"><span data-stu-id="9a796-133">Step 2: Create a new parent project for the customer</span></span>

<span data-ttu-id="9a796-134">Det överordnade projekt som du skapar här används när arbetsorder för kunden skapas.</span><span class="sxs-lookup"><span data-stu-id="9a796-134">The parent project that you create here will be used when work orders for the customer are created.</span></span>

1. <span data-ttu-id="9a796-135">Gå till **Projekthantering och redovisning \> Projekt \> Alla projekt**.</span><span class="sxs-lookup"><span data-stu-id="9a796-135">Go to **Project management and accounting \> Projects \> All projects**.</span></span>
1. <span data-ttu-id="9a796-136">Klicka på **Ny** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="9a796-136">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="9a796-137">I dialogrutan **Nytt projekt** anger du följande värden:</span><span class="sxs-lookup"><span data-stu-id="9a796-137">In the **New project** dialog box, set the following values:</span></span>

    - <span data-ttu-id="9a796-138">**Projekttyp:** *Tid och material*</span><span class="sxs-lookup"><span data-stu-id="9a796-138">**Project type:** *Time and material*</span></span>
    - <span data-ttu-id="9a796-139">**Projektnamn:** *Pelican Wholesales arbetsorder*</span><span class="sxs-lookup"><span data-stu-id="9a796-139">**Project name:** *Pelican Wholesales work orders*</span></span>
    - <span data-ttu-id="9a796-140">**Projektgrupp:** *TM*</span><span class="sxs-lookup"><span data-stu-id="9a796-140">**Project group:** *TM*</span></span>
    - <span data-ttu-id="9a796-141">**Projektkontrakts-ID:** *Pelican Wholesales* (det kontrakt som du skapade tidigare)</span><span class="sxs-lookup"><span data-stu-id="9a796-141">**Project contract ID:** *Pelican Wholesales* (the contract that you created earlier)</span></span>
    - <span data-ttu-id="9a796-142">**Startdatum:** Välj dagens datum.</span><span class="sxs-lookup"><span data-stu-id="9a796-142">**Start date:** Select today's date.</span></span>

1. <span data-ttu-id="9a796-143">Markera **Skapa projekt**.</span><span class="sxs-lookup"><span data-stu-id="9a796-143">Select **Create project**.</span></span>
1. <span data-ttu-id="9a796-144">Det nya projektet öppnas.</span><span class="sxs-lookup"><span data-stu-id="9a796-144">The new project is opened.</span></span> <span data-ttu-id="9a796-145">Gör en notering om värdet **Projekt-ID**.</span><span class="sxs-lookup"><span data-stu-id="9a796-145">Make a note of the **Project ID** value.</span></span> <span data-ttu-id="9a796-146">Du måste skriva in den senare.</span><span class="sxs-lookup"><span data-stu-id="9a796-146">You will have to enter it later.</span></span>

### <a name="step-3-create-a-new-work-order-type-in-asset-management"></a><span data-ttu-id="9a796-147">Steg 3: Skapa en ny arbetsordertyp i Tillgångshantering</span><span class="sxs-lookup"><span data-stu-id="9a796-147">Step 3: Create a new work order type in Asset management</span></span>

1. <span data-ttu-id="9a796-148">Gå till **Tillgångshantering \> Inställningar \> Arbetsorder \> Arbetsordertyper**.</span><span class="sxs-lookup"><span data-stu-id="9a796-148">Go to **Asset management \> Setup \> Work order \> Work order types**.</span></span>
1. <span data-ttu-id="9a796-149">Klicka på **Ny** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="9a796-149">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="9a796-150">En ny post läggs till i listan.</span><span class="sxs-lookup"><span data-stu-id="9a796-150">A new record is added to the list.</span></span> <span data-ttu-id="9a796-151">Ange följande värden för den:</span><span class="sxs-lookup"><span data-stu-id="9a796-151">Set the following values for it:</span></span>

    - <span data-ttu-id="9a796-152">**Typ av arbetsorder:** *Tjänst*</span><span class="sxs-lookup"><span data-stu-id="9a796-152">**Work order type:** *Service*</span></span>
    - <span data-ttu-id="9a796-153">**Namn:** *Arbetsorder för tjänst*</span><span class="sxs-lookup"><span data-stu-id="9a796-153">**Name:** *Service work orders*</span></span>
    - <span data-ttu-id="9a796-154">**Livscykeltillstånd för arbetsorder:** *Standard*</span><span class="sxs-lookup"><span data-stu-id="9a796-154">**Work order lifecycle state:** *Standard*</span></span>

### <a name="step-4-link-the-customer-account-to-the-parent-project"></a><span data-ttu-id="9a796-155">Steg 4: Koppla kundkontot till det överordnade projektet</span><span class="sxs-lookup"><span data-stu-id="9a796-155">Step 4: Link the customer account to the parent project</span></span>

<span data-ttu-id="9a796-156">Du måste nu koppla kundkontot till det överordnade projektet i projektinställningarna i Tillgångshantering.</span><span class="sxs-lookup"><span data-stu-id="9a796-156">You must now link the customer account to the parent project in the project setup in Asset management.</span></span>

1. <span data-ttu-id="9a796-157">Gå till **Tillgångshantering \> Inställningar \> Arbetsorder \> Projektinställningar**.</span><span class="sxs-lookup"><span data-stu-id="9a796-157">Go to **Asset management \> Setup \> Work orders \> Project setup**.</span></span>
1. <span data-ttu-id="9a796-158">På fliken **Överordnat projekt**, välj **Lägg till** om du vill lägga till en rad.</span><span class="sxs-lookup"><span data-stu-id="9a796-158">On the **Parent project** tab, select **Add** to add a line.</span></span>
1. <span data-ttu-id="9a796-159">Ställ in följande värden på denna nya rad:</span><span class="sxs-lookup"><span data-stu-id="9a796-159">On the new line, set the following values:</span></span>

    - <span data-ttu-id="9a796-160">**Kundkonto:** *US-013* (*Pelican Wholesales*)</span><span class="sxs-lookup"><span data-stu-id="9a796-160">**Customer account:** *US-013* (*Pelican Wholesales*)</span></span>
    - <span data-ttu-id="9a796-161">**Projekt-ID:** Ange projekt-ID som du antecknade tidigare.</span><span class="sxs-lookup"><span data-stu-id="9a796-161">**Project ID:** Enter the project ID that you made a note of earlier.</span></span>

### <a name="step-5-link-the-project-group-and-type-to-the-work-order-project"></a><span data-ttu-id="9a796-162">Steg 5: Koppla projektgruppen och typen till arbetsorderprojektet</span><span class="sxs-lookup"><span data-stu-id="9a796-162">Step 5: Link the project group and type to the work order project</span></span>

<span data-ttu-id="9a796-163">Du bör fortfarande vara på sidan **Projektinställning** (**Tillgångshantering \> Inställningar \> Arbetsorder \> Projektinställning**).</span><span class="sxs-lookup"><span data-stu-id="9a796-163">You should still be on the **Project setup** page (**Asset management \> Setup \> Work orders \> Project setup**).</span></span>

1. <span data-ttu-id="9a796-164">På fliken **Projektgrupp**, välj **Lägg till** om du vill lägga till en rad.</span><span class="sxs-lookup"><span data-stu-id="9a796-164">On the **Project group** tab, select **Add** to add a line.</span></span>
1. <span data-ttu-id="9a796-165">Ställ in följande värden på denna nya rad:</span><span class="sxs-lookup"><span data-stu-id="9a796-165">On the new line, set the following values:</span></span>

    - <span data-ttu-id="9a796-166">**Arbetsordertyp:** *Tjänst* (arbetsordertypen som du skapade tidigare)</span><span class="sxs-lookup"><span data-stu-id="9a796-166">**Work order type:** *Service* (the work order type that you created earlier)</span></span>
    - <span data-ttu-id="9a796-167">**Projektgrupp:** *TM*</span><span class="sxs-lookup"><span data-stu-id="9a796-167">**Project group:** *TM*</span></span>

> [!NOTE]
> <span data-ttu-id="9a796-168">Projektkontraktet i arbetsorderprojektet ärvs alltid från det överordnade projektet.</span><span class="sxs-lookup"><span data-stu-id="9a796-168">The project contract on the work order project is always inherited from the parent project.</span></span>

### <a name="step-6-link-an-asset-to-the-customer-id"></a><span data-ttu-id="9a796-169">Steg 6: Koppla en tillgång till kund-ID:t</span><span class="sxs-lookup"><span data-stu-id="9a796-169">Step 6: Link an asset to the customer ID</span></span>

1. <span data-ttu-id="9a796-170">Gå till **Tillgångshantering \> Tillgångar \> Aktiva tillgångar**.</span><span class="sxs-lookup"><span data-stu-id="9a796-170">Go to **Asset management \> Assets \> Active assets**.</span></span>
1. <span data-ttu-id="9a796-171">I fältet **Filter** anger du *VE-102* och väljer att filtrera efter **Tillgång**.</span><span class="sxs-lookup"><span data-stu-id="9a796-171">In the **Filter** field, enter *VE-102*, and select to filter by **Asset**.</span></span>
1. <span data-ttu-id="9a796-172">Markera den tillgång som du vill öppna dess inställningar för.</span><span class="sxs-lookup"><span data-stu-id="9a796-172">Select the asset to open its settings.</span></span>
1. <span data-ttu-id="9a796-173">På snabbfliken **Kund** ställer du in fältet **Kundkonto** på *US-013* (*Pelican Wholesales*).</span><span class="sxs-lookup"><span data-stu-id="9a796-173">On the **Customer** FastTab, set the **Customer account** field to *US-013* (*Pelican Wholesales*).</span></span>

    <span data-ttu-id="9a796-174">Fältet **Namn** uppdateras automatiskt till *Pelican Wholesales*.</span><span class="sxs-lookup"><span data-stu-id="9a796-174">The **Name** field is automatically updated to *Pelican Wholesales*.</span></span>

### <a name="step-7-create-a-new-work-order-on-the-asset"></a><span data-ttu-id="9a796-175">Steg 7: Skapa en ny arbetsordertyp i tillgången</span><span class="sxs-lookup"><span data-stu-id="9a796-175">Step 7: Create a new work order on the asset</span></span>

1. <span data-ttu-id="9a796-176">Gå till **Tillgångshantering \> Arbetsorder \> Aktiva arbetsorder**.</span><span class="sxs-lookup"><span data-stu-id="9a796-176">Go to **Asset management \> Work orders \> Active work orders**.</span></span>
1. <span data-ttu-id="9a796-177">Klicka på **Ny** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="9a796-177">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="9a796-178">I dialogrutan **Skapa arbetsorder** ställ in följande värden:</span><span class="sxs-lookup"><span data-stu-id="9a796-178">In the **Create work order** dialog box, set the following values:</span></span>

    - <span data-ttu-id="9a796-179">**Typ av arbetsorder:** *Tjänst*</span><span class="sxs-lookup"><span data-stu-id="9a796-179">**Work order type:** *Service*</span></span>
    - <span data-ttu-id="9a796-180">**Beskrivning:** *Reparera lastbil*</span><span class="sxs-lookup"><span data-stu-id="9a796-180">**Description:** *Repair Truck*</span></span>
    - <span data-ttu-id="9a796-181">**Kundkonto:** *US-013* (*Pelican Wholesales*)</span><span class="sxs-lookup"><span data-stu-id="9a796-181">**Customer account:** *US-013* (*Pelican Wholesales*)</span></span>
    - <span data-ttu-id="9a796-182">**Tillgång:** *VE-102*</span><span class="sxs-lookup"><span data-stu-id="9a796-182">**Asset:** *VE-102*</span></span>

        > [!NOTE]
        > <span data-ttu-id="9a796-183">I söken visas bara tillgångar som är länkade till det valda kundkontot.</span><span class="sxs-lookup"><span data-stu-id="9a796-183">The lookup shows only assets that are linked to the selected customer account.</span></span>

    - <span data-ttu-id="9a796-184">**Typ av underhållsjobb:** *Reparera*</span><span class="sxs-lookup"><span data-stu-id="9a796-184">**Maintenance job type:** *Repair*</span></span>
    - <span data-ttu-id="9a796-185">**Handel:** *Mekanisk*</span><span class="sxs-lookup"><span data-stu-id="9a796-185">**Trade:** *Mechanic*</span></span>
    - <span data-ttu-id="9a796-186">**Tjänstenivå:** *4*</span><span class="sxs-lookup"><span data-stu-id="9a796-186">**Service level:** *4*</span></span>

1. <span data-ttu-id="9a796-187">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="9a796-187">Select **OK**.</span></span>

### <a name="step-8-review-the-work-order-and-start-to-work-on-it"></a><span data-ttu-id="9a796-188">Steg 8: Granska arbetsordern och börja arbeta med den</span><span class="sxs-lookup"><span data-stu-id="9a796-188">Step 8: Review the work order and start to work on it</span></span>

<span data-ttu-id="9a796-189">I det här avsnittet arbetar du med arbetsordern som du skapade i det föregående avsnittet.</span><span class="sxs-lookup"><span data-stu-id="9a796-189">In this section, you will work on the work order that you created in the previous section.</span></span>

1. <span data-ttu-id="9a796-190">Följ dessa steg för att kontrollera att det överordnade projektet är *Pelican Wholesales arbetsorder*:</span><span class="sxs-lookup"><span data-stu-id="9a796-190">Follow these steps to verify that the parent project is the *Pelican wholesales Work order* project:</span></span>

    1. <span data-ttu-id="9a796-191">I avsnittet **Underhållsjobb för arbetsorder**, välj en rad.</span><span class="sxs-lookup"><span data-stu-id="9a796-191">In the **Work order maintenance jobs** section, select a line.</span></span>
    1. <span data-ttu-id="9a796-192">På snabbfliken **raddetaljer** kontrollera värdet **Projekt-ID-ID**.</span><span class="sxs-lookup"><span data-stu-id="9a796-192">On the **Line details** FastTab, inspect the **Project ID** value.</span></span> <span data-ttu-id="9a796-193">Det bör vara ett bindestrecksnummer i formuläret *\<Parent-Project-ID\>-\<Project-ID\>*.</span><span class="sxs-lookup"><span data-stu-id="9a796-193">It should be a hyphenated number in the form *\<Parent-Project-ID\>-\<Project-ID\>*.</span></span> <span data-ttu-id="9a796-194">Det här värdet är en länk.</span><span class="sxs-lookup"><span data-stu-id="9a796-194">This value is a link.</span></span>
    1. <span data-ttu-id="9a796-195">Markera projekt-ID-länken om du vill öppna en sida där du kan visa namn på det överordnade projektet och projektnamn.</span><span class="sxs-lookup"><span data-stu-id="9a796-195">Select the project ID link to open a page where you can view the parent project and project names.</span></span>

1. <span data-ttu-id="9a796-196">I åtgärdsfönstret, på fliken **Arbetsorder**, i gruppen **livscykeltillstånd**, väljer du **Uppdatera arbetsorderns tillstånd**.</span><span class="sxs-lookup"><span data-stu-id="9a796-196">On the Action Pane, on the **Work order** tab, in the **Lifecycle state** group, select **Update work order state**.</span></span>
1. <span data-ttu-id="9a796-197">I dialogrutan **Uppdatera arbetsorderns tillstånd** i kolumnen **Välj** markera kryssrutan för raden där fältet **livscykeltillstånd** anges till *Pågår*.</span><span class="sxs-lookup"><span data-stu-id="9a796-197">In the **Update work order state** dialog box, in the **Select** column, select the check box for the row where the **Lifecycle state** field is set to *In progress*.</span></span>
1. <span data-ttu-id="9a796-198">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="9a796-198">Select **OK**.</span></span>
1. <span data-ttu-id="9a796-199">I dialogrutan **livscykeltillstånd: pågår**, välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="9a796-199">In the **Lifecycle state: InProgress** dialog box, select **OK**.</span></span>

### <a name="step-9-post-the-hours-that-were-spent-on-the-work-order-and-create-a-new-invoice-proposal"></a><span data-ttu-id="9a796-200">Steg 9: Bokför de timmar som har ägnats åt arbetsordern och skapa ett nytt fakturaförslag</span><span class="sxs-lookup"><span data-stu-id="9a796-200">Step 9: Post the hours that were spent on the work order and create a new invoice proposal</span></span>

<span data-ttu-id="9a796-201">I det här avsnittet fortsätter du arbeta med arbetsordern som du arbetade med i det föregående avsnittet.</span><span class="sxs-lookup"><span data-stu-id="9a796-201">In this section, you will continue to work on the work order that you worked on in the previous section.</span></span>

1. <span data-ttu-id="9a796-202">I åtgärdsfönstret på fliken **Arbetsorder** i gruppen **Projekt** väljer du **Journaler**.</span><span class="sxs-lookup"><span data-stu-id="9a796-202">On the Action Pane, on the **Work order** tab, in the **Project** group, select **Journals**.</span></span>

    <span data-ttu-id="9a796-203">Sidan **Arbetsorderjournaler** visas.</span><span class="sxs-lookup"><span data-stu-id="9a796-203">The **Work order journals** page appears.</span></span> <span data-ttu-id="9a796-204">Här kan du registrera den tid som du har ägnat åt arbetsordern.</span><span class="sxs-lookup"><span data-stu-id="9a796-204">Here, you can register the time that you spent on the work order.</span></span>

1. <span data-ttu-id="9a796-205">På snabbfliken **Timmar** klickar du på **Lägg till rad**.</span><span class="sxs-lookup"><span data-stu-id="9a796-205">On the **Hours** FastTab, select **Add line**.</span></span>
1. <span data-ttu-id="9a796-206">På den nya raden ställer du in fältet **Timmar** till *4*.</span><span class="sxs-lookup"><span data-stu-id="9a796-206">On the new, line, set the **Hours** field to *4*.</span></span>
1. <span data-ttu-id="9a796-207">Klicka på **Bokför journaler** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="9a796-207">On the Action Pane, select **Post journals**.</span></span>
1. <span data-ttu-id="9a796-208">Stäng sidan **Arbetsorderjournaler** när du vill återgå till arbetsordern.</span><span class="sxs-lookup"><span data-stu-id="9a796-208">Close the **Work order journals** page to return to the work order.</span></span>
1. <span data-ttu-id="9a796-209">Välj **Fakturering** på fliken **Nytt fakturaförslag** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="9a796-209">On the Action Pane, on the **Invoicing** tab, select **New invoice proposal**.</span></span>
1. <span data-ttu-id="9a796-210">I dialogrutan **Skapa fakturaförslag** i avsnittet **Projekttransaktioner**, markera kryssrutan **Välj** för varje rad som du vill fakturera.</span><span class="sxs-lookup"><span data-stu-id="9a796-210">In the **Create invoice proposal** dialog box, in the **Project transactions** section, select the **Select** check box for every line  that you want to invoice.</span></span>
1. <span data-ttu-id="9a796-211">Välj **OK** för att stänga dialogrutan och visa det nya fakturaförslaget.</span><span class="sxs-lookup"><span data-stu-id="9a796-211">Select **OK** to close the dialog box and view the new invoice proposal.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]