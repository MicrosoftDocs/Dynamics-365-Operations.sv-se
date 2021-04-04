---
title: Justera ett ER-format för att skapa ett anpassat elektroniskt dokument
description: Det här avsnittet innehåller information om hur du justerar ett "ER"-format (elektronisk rapportering) från Microsoft så att ett anpassat elektroniskt dokument skapas.
author: NickSelin
manager: AnnBe
ms.date: 06/22/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, ERParameters, ERDataModelDesigner, ERModelMappingTable, ERModelMappingDesigner, EROperationDesigner, ERVendorTable
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: 220314
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 3c643c913d9bc9233c891709593dff995284e2e5
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/09/2021
ms.locfileid: "5569007"
---
# <a name="adjust-an-er-format-to-generate-a-custom-electronic-document"></a><span data-ttu-id="7bf58-103">Justera ett ER-format för att skapa ett anpassat elektroniskt dokument</span><span class="sxs-lookup"><span data-stu-id="7bf58-103">Adjust an ER format to generate a custom electronic document</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="7bf58-104">Procedurerna i det här avsnittet förklarar hur en användare i rollen systemadministratör eller elektronisk rapportering kan utföra dessa uppgifter:</span><span class="sxs-lookup"><span data-stu-id="7bf58-104">The procedures in this topic explain how a user in the System Administrator or Electronic Reporting Functional Consultant role can perform these tasks:</span></span>

- <span data-ttu-id="7bf58-105">Konfigurera parametrar för [ramverket för elektronisk rapportering (ER)](general-electronic-reporting.md).</span><span class="sxs-lookup"><span data-stu-id="7bf58-105">Configure parameters for the [Electronic reporting (ER) framework](general-electronic-reporting.md).</span></span>
- <span data-ttu-id="7bf58-106">Importera ER-konfigurationer som tillhandahålls av Microsoft och används för att generera en betalningsfil medan en [leverantörsbetalning](../../../finance/cash-bank-management/tasks/vendor-payment-overview.md) bearbetas.</span><span class="sxs-lookup"><span data-stu-id="7bf58-106">Import ER configurations that are provided by Microsoft and used to generate a payment file while a [vendor payment](../../../finance/cash-bank-management/tasks/vendor-payment-overview.md) is being processed.</span></span>
- <span data-ttu-id="7bf58-107">Skapa en anpassad version av en standardkonfiguration av ER-format som tillhandahålls av Microsoft.</span><span class="sxs-lookup"><span data-stu-id="7bf58-107">Create a custom version of a standard ER format configuration that is provided by Microsoft.</span></span>
- <span data-ttu-id="7bf58-108">Ändra konfigurationen för det anpassade ER-formatet så att den genererar betalningsfiler som uppfyller kraven för en specifik bank.</span><span class="sxs-lookup"><span data-stu-id="7bf58-108">Modify the custom ER format configuration so that it generates payment files that meets the requirements of a specific bank.</span></span>
- <span data-ttu-id="7bf58-109">Anta ändringar som görs i standardkonfigurationen för ER-format i konfigurationen för anpassat ER-format.</span><span class="sxs-lookup"><span data-stu-id="7bf58-109">Adopt changes that are made to the standard ER format configuration in the custom ER format configuration.</span></span>

<span data-ttu-id="7bf58-110">Alla följande procedurer kan göras i **GBSI** företaget.</span><span class="sxs-lookup"><span data-stu-id="7bf58-110">All the following procedures can be done in the **GBSI** company.</span></span> <span data-ttu-id="7bf58-111">Ingen kod behövs.</span><span class="sxs-lookup"><span data-stu-id="7bf58-111">No coding is required.</span></span>

- [<span data-ttu-id="7bf58-112">Konfigurera ER-ramverket</span><span class="sxs-lookup"><span data-stu-id="7bf58-112">Configure the ER framework</span></span>](#ConfigureFramework)

    - [<span data-ttu-id="7bf58-113">Konfigurera ER-parametrar</span><span class="sxs-lookup"><span data-stu-id="7bf58-113">Configure ER parameters</span></span>](#ConfigureParameters)
    - [<span data-ttu-id="7bf58-114">Aktivera en ER-konfigurationsleverantör</span><span class="sxs-lookup"><span data-stu-id="7bf58-114">Activate an ER configuration provider</span></span>](#ActivateProvider)

        - [<span data-ttu-id="7bf58-115">Granska listan med ER-konfigurationsleverantörer</span><span class="sxs-lookup"><span data-stu-id="7bf58-115">Review the list of ER configuration providers</span></span>](#ReviewProvidersList)
        - [<span data-ttu-id="7bf58-116">Lägg till en ny ER-konfigurationsleverantör</span><span class="sxs-lookup"><span data-stu-id="7bf58-116">Add a new ER configuration provider</span></span>](#ActivateProvider)
        - [<span data-ttu-id="7bf58-117">Aktivera en ER-konfigurationsleverantör</span><span class="sxs-lookup"><span data-stu-id="7bf58-117">Activate an ER configuration provider</span></span>](#ActivateAddedProvider)

- [<span data-ttu-id="7bf58-118">Importera standardkonfiguration av ER-format</span><span class="sxs-lookup"><span data-stu-id="7bf58-118">Import the standard ER format configurations</span></span>](#ImportERSolution1)

    - [<span data-ttu-id="7bf58-119">Importera ER-standardkonfiguration</span><span class="sxs-lookup"><span data-stu-id="7bf58-119">Import the standard ER configurations</span></span>](#ImportERFormat1)
    - [<span data-ttu-id="7bf58-120">Granska importerade ER-konfigurationer</span><span class="sxs-lookup"><span data-stu-id="7bf58-120">Review the imported ER configurations</span></span>](#ReviewImportedERSolution)

- [<span data-ttu-id="7bf58-121">Förbered en leverantörsbetalning för bearbetning</span><span class="sxs-lookup"><span data-stu-id="7bf58-121">Prepare a vendor payment for processing</span></span>](#PrepareVendorPayment)

    - [<span data-ttu-id="7bf58-122">Lägga till bankinformation för ett leverantörskonto</span><span class="sxs-lookup"><span data-stu-id="7bf58-122">Add bank information for a vendor account</span></span>](#AddBankAccount)
    - [<span data-ttu-id="7bf58-123">Ange en leverantörsbetalning</span><span class="sxs-lookup"><span data-stu-id="7bf58-123">Enter a vendor payment</span></span>](#EnterVendorPayment)

- [<span data-ttu-id="7bf58-124">Bearbeta en leverantörsbetalning med hjälp av ER-standardformat</span><span class="sxs-lookup"><span data-stu-id="7bf58-124">Process a vendor payment by using the standard ER format</span></span>](#ProcessVendorPayment1)

    - [<span data-ttu-id="7bf58-125">Ange den elektroniska betalningsmetoden</span><span class="sxs-lookup"><span data-stu-id="7bf58-125">Set up the electronic payment method</span></span>](#ConfigureMethodOfPayment1)
    - [<span data-ttu-id="7bf58-126">Bearbeta en leverantörsbetalning</span><span class="sxs-lookup"><span data-stu-id="7bf58-126">Process a vendor payment</span></span>](#ProcessPayment1)

- [<span data-ttu-id="7bf58-127">Anpassa ER-standardformatet</span><span class="sxs-lookup"><span data-stu-id="7bf58-127">Customize the standard ER format</span></span>](#CustomizeProvidedFormat)

    - [<span data-ttu-id="7bf58-128">Skapa ett anpassat format</span><span class="sxs-lookup"><span data-stu-id="7bf58-128">Create a custom format</span></span>](#DeriveProvidedFormat)
    - [<span data-ttu-id="7bf58-129">Redigera ett anpassat format</span><span class="sxs-lookup"><span data-stu-id="7bf58-129">Edit a custom format</span></span>](#ConfigureDerivedFormat)
    - [<span data-ttu-id="7bf58-130">Markera ett anpassat format som körbart</span><span class="sxs-lookup"><span data-stu-id="7bf58-130">Mark a custom format as runnable</span></span>](#MarkFormatRunnable)

- [<span data-ttu-id="7bf58-131">Bearbeta en leverantörsbetalning med hjälp av anpassat ER-format</span><span class="sxs-lookup"><span data-stu-id="7bf58-131">Process a vendor payment by using the custom ER format</span></span>](#ProcessVendorPayment2)

    - [<span data-ttu-id="7bf58-132">Ange den elektroniska betalningsmetoden</span><span class="sxs-lookup"><span data-stu-id="7bf58-132">Set up the electronic payment method</span></span>](#ConfigureMethodOfPayment2)
    - [<span data-ttu-id="7bf58-133">Bearbeta en leverantörsbetalning</span><span class="sxs-lookup"><span data-stu-id="7bf58-133">Process a vendor payment</span></span>](#ProcessPayment2)

- [<span data-ttu-id="7bf58-134">Importera nya versioner av standardkonfiguration av ER-format</span><span class="sxs-lookup"><span data-stu-id="7bf58-134">Import new versions of the standard ER format configurations</span></span>](#ImportERSolution2)

    - [<span data-ttu-id="7bf58-135">Importera nya versioner av ER-standardkonfigurationer</span><span class="sxs-lookup"><span data-stu-id="7bf58-135">Import new versions of the standard ER configurations</span></span>](#ImportERFormat2)
    - [<span data-ttu-id="7bf58-136">Granska importerade ER-formatkonfigurationer</span><span class="sxs-lookup"><span data-stu-id="7bf58-136">Review the imported ER format configurations</span></span>](#ReviewImportedERFormat)

- [<span data-ttu-id="7bf58-137">Tillämpa ändringarna i den nya versionen av ett importerat format i ett anpassat format</span><span class="sxs-lookup"><span data-stu-id="7bf58-137">Adopt the changes in the new version of an imported format in a custom format</span></span>](#AdoptNewBaseVersion)

    - [<span data-ttu-id="7bf58-138">Slutför den nuvarande utkastversionen av ett anpassat format</span><span class="sxs-lookup"><span data-stu-id="7bf58-138">Complete the current draft version of a custom format</span></span>](#CompleteDerivedFormat)
    - [<span data-ttu-id="7bf58-139">Basera ett anpassat format på en ny basversion</span><span class="sxs-lookup"><span data-stu-id="7bf58-139">Rebase a custom format to a new base version</span></span>](#RebaseDerivedFormat)
    - [<span data-ttu-id="7bf58-140">Bearbeta en leverantörsbetalning med hjälp av ombaserat ER-format</span><span class="sxs-lookup"><span data-stu-id="7bf58-140">Process a vendor payment by using a rebased ER format</span></span>](#ProcessPayment3)

- [<span data-ttu-id="7bf58-141">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="7bf58-141">Additional resources</span></span>](#References)

## <a name="configure-the-er-framework"></a><a id="ConfigureFramework"></a><span data-ttu-id="7bf58-142">Konfigurera ER-ramverket</span><span class="sxs-lookup"><span data-stu-id="7bf58-142">Configure the ER framework</span></span>

<span data-ttu-id="7bf58-143">Som användare i rollen funktionell konsult för elektronisk rapportering måste du konfigurera den minsta uppsättningen ER-parametrar innan du kan börja använda ER-ramverket för att designa en anpassad version av ett vanligt ER-format.</span><span class="sxs-lookup"><span data-stu-id="7bf58-143">As a user in the Electronic Reporting Functional Consultant role, you must configure the minimal set of ER parameters before you can start to use the ER framework to design a custom version of a standard ER format.</span></span>

### <a name="configure-er-parameters"></a><a id="ConfigureParameters"></a><span data-ttu-id="7bf58-144">Konfigurera ER-parametrar</span><span class="sxs-lookup"><span data-stu-id="7bf58-144">Configure ER parameters</span></span>

1. <span data-ttu-id="7bf58-145">Gå till **Organisationsadministration** \> **Arbetsytor** \> **Elektronisk rapportering**.</span><span class="sxs-lookup"><span data-stu-id="7bf58-145">Go to **Organization administration** \> **Workspaces** \> **Electronic reporting**.</span></span>
2. <span data-ttu-id="7bf58-146">På sidan **lokaliseringskonfiguration** i avsnittet **Relaterade länkar** väljer du **parametrar för elektronisk rapportering**.</span><span class="sxs-lookup"><span data-stu-id="7bf58-146">On the **Localization configurations** page, in the **Related links** section, select **Electronic reporting parameters**.</span></span>
3. <span data-ttu-id="7bf58-147">På sidan **parametrar för elektronisk rapportering** på fliken **allmänna** anger du alternativet till **aktivera designläge** till **Ja**.</span><span class="sxs-lookup"><span data-stu-id="7bf58-147">On the **Electronic reporting parameters** page, on the **General** tab, set the **Enable design mode** option to **Yes**.</span></span>
4. <span data-ttu-id="7bf58-148">Ange följande parametrar på fliken **Bilagor**:</span><span class="sxs-lookup"><span data-stu-id="7bf58-148">On the **Attachments** tab, set the following parameters:</span></span>

    - <span data-ttu-id="7bf58-149">I fältet **Konfigurationer** välj typen **Fil** för **USMF**-företaget.</span><span class="sxs-lookup"><span data-stu-id="7bf58-149">In the **Configurations** field, select the **File** type for the **USMF** company.</span></span>
    - <span data-ttu-id="7bf58-150">I fältet **Jobbarkiv**, **Tillfälliga**, **Baslinje** och **Andra** och välj typen **Fil**.</span><span class="sxs-lookup"><span data-stu-id="7bf58-150">In the **Job archive**, **Temporary**, **Baseline**, and **Others** fields, select the **File** type.</span></span>

<span data-ttu-id="7bf58-151">Mer information om ER-parametrar finns i [Konfigurera om ER-ramverket](electronic-reporting-er-configure-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="7bf58-151">For more information about ER parameters, see [Configure the ER framework](electronic-reporting-er-configure-parameters.md).</span></span>

### <a name="activate-an-er-configuration-provider"></a><a id="ActivateProvider"></a><span data-ttu-id="7bf58-152">Aktivera en ER-konfigurationsleverantör</span><span class="sxs-lookup"><span data-stu-id="7bf58-152">Activate an ER configuration provider</span></span>

<span data-ttu-id="7bf58-153">Varje ER-konfiguration som läggs till markeras som ägd av en ER-konfigurationsleverantör.</span><span class="sxs-lookup"><span data-stu-id="7bf58-153">Every ER configuration that is added is marked as owned by an ER configuration provider.</span></span> <span data-ttu-id="7bf58-154">Den ER-konfigurationsleverantör för ER som aktiveras i arbetsytan **Elektronisk rapportering** används för det här syftet.</span><span class="sxs-lookup"><span data-stu-id="7bf58-154">The ER configuration provider that is activated in the **Electronic reporting** workspace is used for this purpose.</span></span> <span data-ttu-id="7bf58-155">Därför måste du aktivera en ER-konfigurationsleverantör i arbetsytan **Elektronisk rapportering** innan du börjar lägga till eller redigera ER-konfigurationer.</span><span class="sxs-lookup"><span data-stu-id="7bf58-155">Therefore, you must activate an ER configuration provider in the **Electronic reporting** workspace before you start to add or edit ER configurations.</span></span>

> [!NOTE]
> <span data-ttu-id="7bf58-156">Endast ägaren till en ER-konfiguration kan redigera den.</span><span class="sxs-lookup"><span data-stu-id="7bf58-156">Only the owner of an ER configuration can edit it.</span></span> <span data-ttu-id="7bf58-157">Därför måste en lämplig ER-konfigurationsleverantör aktiveras innan en ER-konfiguration kan redigeras arbetsytan **Elektronisk rapportering**.</span><span class="sxs-lookup"><span data-stu-id="7bf58-157">Therefore, before an ER configuration can be edited, the appropriate ER configuration provider must be activated in the **Electronic reporting** workspace.</span></span>

#### <a name="review-the-list-of-er-configuration-providers"></a><a id="ReviewProvidersList"></a><span data-ttu-id="7bf58-158">Granska listan med ER-konfigurationsleverantörer</span><span class="sxs-lookup"><span data-stu-id="7bf58-158">Review the list of ER configuration providers</span></span>

1. <span data-ttu-id="7bf58-159">Gå till **Organisationsadministration** \> **Arbetsytor** \> **Elektronisk rapportering**.</span><span class="sxs-lookup"><span data-stu-id="7bf58-159">Go to **Organization administration** \> **Workspaces** \> **Electronic reporting**.</span></span>
2. <span data-ttu-id="7bf58-160">På sidan **lokaliseringskonfiguration** i avsnittet **Relaterade länkar** väljer du **Konfigurationsleverantörer**.</span><span class="sxs-lookup"><span data-stu-id="7bf58-160">On the **Localization configurations** page, in the **Related links** section, select **Configuration providers**.</span></span>
3. <span data-ttu-id="7bf58-161">På sidan **Tabellen konfigurationsleverantörer** har varje leverantörspost ett unikt namn och en URL.</span><span class="sxs-lookup"><span data-stu-id="7bf58-161">On the **Configuration provider table** page, each provider record has a unique name and URL.</span></span> <span data-ttu-id="7bf58-162">Granska innehållet på den här sidan.</span><span class="sxs-lookup"><span data-stu-id="7bf58-162">Review the contents of this page.</span></span> <span data-ttu-id="7bf58-163">Om det redan finns en post för **Litware, Inc.** (`https://www.litware.com`) hoppar du över nästa procedur [Lägg till en ny ER-konfigurationsleverantör](#ActivateProvider).</span><span class="sxs-lookup"><span data-stu-id="7bf58-163">If a record for **Litware, Inc.** (`https://www.litware.com`) already exists, skip the next procedure, [Add a new ER configuration provider](#ActivateProvider).</span></span>

#### <a name="add-a-new-er-configuration-provider"></a><a id="ActivateProvider"></a><span data-ttu-id="7bf58-164">Lägg till en ny ER-konfigurationsleverantör</span><span class="sxs-lookup"><span data-stu-id="7bf58-164">Add a new ER configuration provider</span></span>

1. <span data-ttu-id="7bf58-165">Gå till **Organisationsadministration** \> **Arbetsytor** \> **Elektronisk rapportering**.</span><span class="sxs-lookup"><span data-stu-id="7bf58-165">Go to **Organization administration** \> **Workspaces** \> **Electronic reporting**.</span></span>
2. <span data-ttu-id="7bf58-166">På sidan **lokaliseringskonfiguration** i avsnittet **Relaterade länkar** väljer du **Konfigurationsleverantörer**.</span><span class="sxs-lookup"><span data-stu-id="7bf58-166">On the **Localization configurations** page, in the **Related links** section, select **Configuration providers**.</span></span>
3. <span data-ttu-id="7bf58-167">Välj **Konfigurationsleverantörer** på sidan **Leveranssätt**.</span><span class="sxs-lookup"><span data-stu-id="7bf58-167">On the **Configuration providers** page, select **New**.</span></span>
4. <span data-ttu-id="7bf58-168">I fältet **Namn** anger du **Litware, Inc.**.</span><span class="sxs-lookup"><span data-stu-id="7bf58-168">In the **Name** field, enter **Litware, Inc.**</span></span>
5. <span data-ttu-id="7bf58-169">I fältet **Internetadress** anger du `https://www.litware.com`.</span><span class="sxs-lookup"><span data-stu-id="7bf58-169">In the **Internet address** field, enter `https://www.litware.com`.</span></span>
6. <span data-ttu-id="7bf58-170">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="7bf58-170">Select **Save**.</span></span>

#### <a name="activate-an-er-configuration-provider"></a><a id="ActivateAddedProvider"></a><span data-ttu-id="7bf58-171">Aktivera en ER-konfigurationsleverantörer</span><span class="sxs-lookup"><span data-stu-id="7bf58-171">Activate an ER configuration provider</span></span>

1. <span data-ttu-id="7bf58-172">Gå till **Organisationsadministration** \> **Arbetsytor** \> **Elektronisk rapportering**.</span><span class="sxs-lookup"><span data-stu-id="7bf58-172">Go to **Organization administration** \> **Workspaces** \> **Electronic reporting**.</span></span>
2. <span data-ttu-id="7bf58-173">På sidan **lokaliseringskonfiguration** i avsnittet **konfigurationsleverantörer** välj panelen **Litware, Inc.** och välj sedan **Ange aktiv**.</span><span class="sxs-lookup"><span data-stu-id="7bf58-173">On the **Localization configurations** page, in the **Configuration providers** section, select the **Litware, Inc.** tile, and then select **Set active**.</span></span>

<span data-ttu-id="7bf58-174">Mer information om ER-konfigurationsleverantörer finns i [Skapa konfigurationsleverantörer och markera dem som aktiva](tasks/er-configuration-provider-mark-it-active-2016-11.md).</span><span class="sxs-lookup"><span data-stu-id="7bf58-174">For more information about ER configuration providers, see [Create configuration providers and mark them as active](tasks/er-configuration-provider-mark-it-active-2016-11.md).</span></span>

## <a name="import-the-standard-er-format-configurations"></a><a id="ImportERSolution1"></a><span data-ttu-id="7bf58-175">Importera standardkonfiguration av ER-format</span><span class="sxs-lookup"><span data-stu-id="7bf58-175">Import the standard ER format configurations</span></span>

### <a name="import-the-standard-er-configurations"></a><a id="ImportERFormat1"></a><span data-ttu-id="7bf58-176">Importera ER-standardkonfiguration</span><span class="sxs-lookup"><span data-stu-id="7bf58-176">Import the standard ER configurations</span></span>

<span data-ttu-id="7bf58-177">Om du vill lägga till standard-ER-konfigurationer i din aktuella instans av Microsoft Dynamics 365 Finance, måste du importera dem från ER [databasen](general-electronic-reporting.md#Repository) som har konfigurerats för den instansen.</span><span class="sxs-lookup"><span data-stu-id="7bf58-177">To add the standard ER configurations to your current instance of Microsoft Dynamics 365 Finance, you must import them from the ER [repository](general-electronic-reporting.md#Repository) that was configured for that instance.</span></span>

1. <span data-ttu-id="7bf58-178">Gå till **Organisationsadministration** \> **Arbetsytor** \> **Elektronisk rapportering**.</span><span class="sxs-lookup"><span data-stu-id="7bf58-178">Go to **Organization administration** \> **Workspaces** \> **Electronic reporting**.</span></span>
2. <span data-ttu-id="7bf58-179">På sidan **lokaliseringskonfiguration** i avsnittet **konfigurationsleverantörer** välj panelen **Microsoft** och markera sedan **databaser** om du vill visa listan över databaser för Microsoft-leverantören.</span><span class="sxs-lookup"><span data-stu-id="7bf58-179">On the **Localization configurations** page, in the **Configuration providers** section, select the **Microsoft** tile, and then select **Repositories** to view the list of repositories for the Microsoft provider.</span></span>
3. <span data-ttu-id="7bf58-180">På sidan **Konfigurationsdatabaser** väljer du i rutnätet den befintliga databasen för **Global**-typ och väljer sedan **Öppna**.</span><span class="sxs-lookup"><span data-stu-id="7bf58-180">On the **Configuration repositories** page, select the repository of the **Global** type, and then select **Open**.</span></span> <span data-ttu-id="7bf58-181">Om du uppmanas att bevilja behörighet att ansluta till Regulatory Configuration Service följer du instruktionerna för auktorisering.</span><span class="sxs-lookup"><span data-stu-id="7bf58-181">If you're prompted for authorization to connect to Regulatory Configuration Service, follow the authorization instructions.</span></span>
4. <span data-ttu-id="7bf58-182">På sidan **Konfigurationsdatabas** i konfigurationsträdet i vänster fönster, välj den **BACS (UK)**-formatkonfiguration.</span><span class="sxs-lookup"><span data-stu-id="7bf58-182">On the **Configuration repository** page, in the configuration tree in the left pane, select the **BACS (UK)** format configuration.</span></span>
5. <span data-ttu-id="7bf58-183">På snabbfliken **Versioner** välj version **1.1** av den valda ER-formatkonfigurationen.</span><span class="sxs-lookup"><span data-stu-id="7bf58-183">On the **Versions** FastTab, select version **1.1** of the selected ER format configuration.</span></span>
6. <span data-ttu-id="7bf58-184">Välj **Importera** för att hämta den valda versionen från den globala databasen till den aktuella Finance-instansen.</span><span class="sxs-lookup"><span data-stu-id="7bf58-184">Select **Import** to download the selected version from the Global repository to the current Finance instance.</span></span>

![Sidan Konfigurationsdatabas](./media/er-quick-start2-import-solution1.png)

> [!TIP]
> <span data-ttu-id="7bf58-186">Om du har problem med att komma åt den [Global databasen](er-download-configurations-global-repo.md), kan du [hämta konfigurationer](download-electronic-reporting-configuration-lcs.md) från Microsoft Dynamics Lifecycle Services (LCS) istället.</span><span class="sxs-lookup"><span data-stu-id="7bf58-186">If you have trouble accessing the [Global repository](er-download-configurations-global-repo.md), you can [download configurations](download-electronic-reporting-configuration-lcs.md) from Microsoft Dynamics Lifecycle Services (LCS) instead.</span></span>

### <a name="review-the-imported-er-configurations"></a><a id="ReviewImportedERSolution"></a><span data-ttu-id="7bf58-187">Granska importerade ER-konfigurationer</span><span class="sxs-lookup"><span data-stu-id="7bf58-187">Review the imported ER configurations</span></span>

1. <span data-ttu-id="7bf58-188">Gå till **Organisationsadministration** \> **Arbetsytor** \> **Elektronisk rapportering**.</span><span class="sxs-lookup"><span data-stu-id="7bf58-188">Go to **Organization administration** \> **Workspaces** \> **Electronic reporting**.</span></span>
2. <span data-ttu-id="7bf58-189">På sidan **Lokaliseringskonfiguration** i avsnittet **Konfigurationer** väljer du panelen **Rapporteringskonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="7bf58-189">On the **Localization configurations** page, in the **Configurations** section, select the **Reporting configurations** tile.</span></span>
3. <span data-ttu-id="7bf58-190">På sidan **konfigurationer** i konfigurationsträdet i vänster fönster expanderar du **Betalningsmodell**.</span><span class="sxs-lookup"><span data-stu-id="7bf58-190">On the **Configurations** page, in the configuration tree in the left pane, expand **Payment model**.</span></span>
4. <span data-ttu-id="7bf58-191">Observera att förutom det valda **BACS (UK)** ER-format, har andra krävda ER-konfigurationer har importerats.</span><span class="sxs-lookup"><span data-stu-id="7bf58-191">Notice that, in addition to the selected **BACS (UK)** ER format, other required ER configurations were imported.</span></span> <span data-ttu-id="7bf58-192">Se till att följande ER-konfigurationer är tillgängliga i konfigurationsträdet:</span><span class="sxs-lookup"><span data-stu-id="7bf58-192">Make sure that the following ER configurations are available in the configuration tree:</span></span>

    - <span data-ttu-id="7bf58-193">**Betalningsmodell** – Den här konfigurationen innehåller den [datamodell](general-electronic-reporting.md#data-model-and-model-mapping-components) ER-komponent för datamodellen som representerar data strukturen i betalningsaffärsdomänen.</span><span class="sxs-lookup"><span data-stu-id="7bf58-193">**Payment model** – This configuration contains the [data model](general-electronic-reporting.md#data-model-and-model-mapping-components) ER component that represents the data structure of the payment business domain.</span></span>
    - <span data-ttu-id="7bf58-194">**Mappning av betalningsmodell 1611** – Den här konfigurationen innehåller [modellmappningen](general-electronic-reporting.md#data-model-and-model-mapping-components) ER-komponent som beskriver hur datamodellen fylls i med appdata under körning.</span><span class="sxs-lookup"><span data-stu-id="7bf58-194">**Payment model mapping 1611** – This configuration contains the [model mapping](general-electronic-reporting.md#data-model-and-model-mapping-components) ER component that describes how the data model is filled in with application data at runtime.</span></span>
    - <span data-ttu-id="7bf58-195">**BACS (UK)** – Den här konfigurationen innehåller [format](general-electronic-reporting.md#FormatComponentOutbound) och formatmappning för ER-komponenter.</span><span class="sxs-lookup"><span data-stu-id="7bf58-195">**BACS (UK)** – This configuration contains the [format](general-electronic-reporting.md#FormatComponentOutbound) and format mapping ER components.</span></span> <span data-ttu-id="7bf58-196">Formatkomponenten anger rapportlayouten.</span><span class="sxs-lookup"><span data-stu-id="7bf58-196">The format component specifies the report layout.</span></span> <span data-ttu-id="7bf58-197">Komponenten för formatmappning innehåller modelldatakällan och anger hur rapportlayouten fylls i med hjälp av den här datakällan vid körning.</span><span class="sxs-lookup"><span data-stu-id="7bf58-197">The format mapping component contains the model data source and specifies how the report layout is filled in by using this data source at runtime.</span></span>

![Sidan Konfigurationer](./media/er-quick-start2-imported-solution1.png)

## <a name="prepare-a-vendor-payment-for-processing"></a><a id="PrepareVendorPayment"></a><span data-ttu-id="7bf58-199">Förbered en leverantörsbetalning för bearbetning</span><span class="sxs-lookup"><span data-stu-id="7bf58-199">Prepare a vendor payment for processing</span></span>

### <a name="add-bank-information-for-a-vendor-account"></a><a id="AddBankAccount"></a><span data-ttu-id="7bf58-200">Lägga till bankinformation för ett leverantörskonto</span><span class="sxs-lookup"><span data-stu-id="7bf58-200">Add bank information for a vendor account</span></span>

<span data-ttu-id="7bf58-201">Du måste lägga till bankinformation för ett leverantörskonto som kommer att refereras till senare i en registrerad betalning.</span><span class="sxs-lookup"><span data-stu-id="7bf58-201">You must add bank information for a vendor account that will be referred to later in a registered payment.</span></span>

1. <span data-ttu-id="7bf58-202">Gå till **Leverantörsreskontra** \> **Leverantörer** \> **Alla leverantörer**.</span><span class="sxs-lookup"><span data-stu-id="7bf58-202">Go to **Accounts payable** \> **Vendors** \> **All vendors**.</span></span>
2. <span data-ttu-id="7bf58-203">På sidan **Alla leverantörer**, välj **GB_SI_000001** leverantörskonto och sedan på åtgärdsfönstret, på fliken **Leverantör** i gruppen **Inställningar** väljer du **Bankkonton**.</span><span class="sxs-lookup"><span data-stu-id="7bf58-203">On the **All vendors** page, select the **GB_SI_000001** vendor account, and then, on the Action Pane, on the **Vendor** tab, in the **Set up** group, select **Bank accounts**.</span></span>
3. <span data-ttu-id="7bf58-204">På sidan **Leverantörsbankkonton**, välj **Ny** och ange sedan följande information:</span><span class="sxs-lookup"><span data-stu-id="7bf58-204">On the **Vendor bank accounts** page, select **New**, and then enter the following information:</span></span>

    1. <span data-ttu-id="7bf58-205">I fältet **Bankkonto** väljer du **GBP OPER**.</span><span class="sxs-lookup"><span data-stu-id="7bf58-205">In the **Bank account** field, enter **GBP OPER**.</span></span>
    2. <span data-ttu-id="7bf58-206">I fältet **Bankgrupper** väljer du **BankGBP**.</span><span class="sxs-lookup"><span data-stu-id="7bf58-206">In the **Bank groups** field, select **BankGBP**.</span></span>
    3. <span data-ttu-id="7bf58-207">I fältet **Bankkontonummer** väljer du **202015**.</span><span class="sxs-lookup"><span data-stu-id="7bf58-207">In the **Bank account number** field, enter **202015**.</span></span>
    4. <span data-ttu-id="7bf58-208">I fältet **SWIFT-kod** ange <a id="DefineSWIFTCode"></a>**CHASDEFXXXX**.</span><span class="sxs-lookup"><span data-stu-id="7bf58-208">In the **SWIFT code** field, enter <a id="DefineSWIFTCode"></a>**CHASDEFXXXX**.</span></span>
    5. <span data-ttu-id="7bf58-209">I fältet **IBAN** anger du **GB33BUKB20201555555555**.</span><span class="sxs-lookup"><span data-stu-id="7bf58-209">In the **IBAN** field, enter **GB33BUKB20201555555555**.</span></span>
    6. <span data-ttu-id="7bf58-210">I fältet **Clearingnummer** behåll värdet <a id="DefineRoutingNumber"></a>**123456**.</span><span class="sxs-lookup"><span data-stu-id="7bf58-210">In the **Routing number** field, keep the default value, <a id="DefineRoutingNumber"></a>**123456**.</span></span>

    ![Sidan Leverantörsbankkonton](./media/er-quick-start2-bank-account.png)

4. <span data-ttu-id="7bf58-212">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="7bf58-212">Select **Save**.</span></span>
5. <span data-ttu-id="7bf58-213">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="7bf58-213">Close the page.</span></span>
6. <span data-ttu-id="7bf58-214">På sidan **Alla leverantörer** öppnar du **GB_SI_000001** leverantörskonto.</span><span class="sxs-lookup"><span data-stu-id="7bf58-214">On the **All vendors** page, open the **GB_SI_000001** vendor account.</span></span>
7. <span data-ttu-id="7bf58-215">På sidan leverantörsinformation väljer du **Redigera** för att göra sidan redigerbar om det behövs.</span><span class="sxs-lookup"><span data-stu-id="7bf58-215">On the vendor details page, select **Edit** to make the page editable, if required.</span></span>
8. <span data-ttu-id="7bf58-216">På snabbfliken **Betalning** i fältet **Bankkonto** väljer du **GBP OPER**.</span><span class="sxs-lookup"><span data-stu-id="7bf58-216">On the **Payment** FastTab, in the **Bank account** field, select **GBP OPER**.</span></span>

    ![Sidan Leverantörsinformation](./media/er-quick-start2-bank-account-reference.png)

9. <span data-ttu-id="7bf58-218">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="7bf58-218">Select **Save**.</span></span>
10. <span data-ttu-id="7bf58-219">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="7bf58-219">Close the page.</span></span>

### <a name="enter-a-vendor-payment"></a><a id="EnterVendorPayment"></a><span data-ttu-id="7bf58-220">Ange en leverantörsbetalning</span><span class="sxs-lookup"><span data-stu-id="7bf58-220">Enter a vendor payment</span></span>

<span data-ttu-id="7bf58-221">Du måste ange en ny leverantörsbetalning genom att använda [betalningsförslag](https://docs.microsoft.com/dynamics365/finance/accounts-payable/create-vendor-payments-payment-proposal).</span><span class="sxs-lookup"><span data-stu-id="7bf58-221">You must enter a new vendor payment by using a [payment proposal](https://docs.microsoft.com/dynamics365/finance/accounts-payable/create-vendor-payments-payment-proposal).</span></span>

1. <span data-ttu-id="7bf58-222">Gå till **Leverantörsreskontra** \> **Betalningar** \> **Leverantörsbetalningsjournal**.</span><span class="sxs-lookup"><span data-stu-id="7bf58-222">Go to **Accounts payable** \> **Payments** \> **Vendor payment journal**.</span></span>
2. <span data-ttu-id="7bf58-223">Välj **Leverantörsbetalningsjournal** på sidan **Leveranssätt**.</span><span class="sxs-lookup"><span data-stu-id="7bf58-223">On the **Vendor payment journal** page, select **New**.</span></span>
3. <span data-ttu-id="7bf58-224">Välj **VendPay** i fältet **Namn**.</span><span class="sxs-lookup"><span data-stu-id="7bf58-224">In the **Name** field, select **VendPay**.</span></span>
4. <span data-ttu-id="7bf58-225">Markera **rader**</span><span class="sxs-lookup"><span data-stu-id="7bf58-225">Select **Lines**.</span></span>
5. <span data-ttu-id="7bf58-226">Välj **Betalningsförslag** \> **Skapa betalningsförslag**.</span><span class="sxs-lookup"><span data-stu-id="7bf58-226">Select **Payment proposal** \> **Create payment proposal**.</span></span>
6. <span data-ttu-id="7bf58-227">I dialogrutan **leverantörsbetalningsförslag** konfigurera villkor för att filtrera poster för endast leverantörskonto **GB_SI_000001** och välj sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="7bf58-227">In the **Vendor payment proposal** dialog box, configure conditions to filter for records for the **GB_SI_000001** vendor account only, and then select **OK**.</span></span>
7. <span data-ttu-id="7bf58-228">Markera raden för fakturan **00000007_Inv** och välj sedan **Skapa betalning**.</span><span class="sxs-lookup"><span data-stu-id="7bf58-228">Select the line for the **00000007_Inv** invoice, and then select **Create payment**.</span></span>

    ![Dialogrutan leverantörsbetalningsförslag](./media/er-quick-start2-payment-proposal.png)

8. <span data-ttu-id="7bf58-230">Kontrollera att betalningen som anges har konfigurerats för användning av betalningsmetoden **elektronisk**.</span><span class="sxs-lookup"><span data-stu-id="7bf58-230">Verify that the payment that is entered is configured to use the **Electronic** method of payment.</span></span>

    ![Sidan Leverantörsbetalningar](./media/er-quick-start2-payment-line.png)

## <a name="process-a-vendor-payment-by-using-the-standard-er-format"></a><a id="ProcessVendorPayment1"></a><span data-ttu-id="7bf58-232">Bearbeta en leverantörsbetalning med hjälp av ER-standardformat</span><span class="sxs-lookup"><span data-stu-id="7bf58-232">Process a vendor payment by using the standard ER format</span></span>

### <a name="set-up-the-electronic-payment-method"></a><a id="ConfigureMethodOfPayment1"></a><span data-ttu-id="7bf58-233">Ange den elektroniska betalningsmetoden</span><span class="sxs-lookup"><span data-stu-id="7bf58-233">Set up the electronic payment method</span></span>

<span data-ttu-id="7bf58-234">Du måste konfigurera den elektroniska betalningsmetoden så att den använder den importerade ER-formatkonfigurationen.</span><span class="sxs-lookup"><span data-stu-id="7bf58-234">You must configure the electronic method of payment so that it uses the imported ER format configuration.</span></span>

1. <span data-ttu-id="7bf58-235">Gå till **Leverantörsreskontra** \> **Betalningsinställning** \> **Betalningsmetoder**.</span><span class="sxs-lookup"><span data-stu-id="7bf58-235">Go to **Accounts payable** \> **Payment setup** \> **Methods of payment**.</span></span>
2. <span data-ttu-id="7bf58-236">På sidan **Betalningsmetoder - leverantörer** välj metoden **Elektronisk** i det vänstra fönstret.</span><span class="sxs-lookup"><span data-stu-id="7bf58-236">On the **Methods of payment - vendors** page, select the **Electronic** method of payment in the left pane.</span></span>
3. <span data-ttu-id="7bf58-237">Välj **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="7bf58-237">Select **Edit**.</span></span>
4. <span data-ttu-id="7bf58-238">På snabbfliken **filformat** ställer du in alternativet **Allmänt elektroniskt exportformat** till **Ja**.</span><span class="sxs-lookup"><span data-stu-id="7bf58-238">On the **File formats** FastTab, set the **General electronic Export format** option to **Yes**.</span></span>
5. <span data-ttu-id="7bf58-239">I fältet **Exportformatkonfiguration** väljer du formatkonfigurationen **BACS (UK)**.</span><span class="sxs-lookup"><span data-stu-id="7bf58-239">In the **Export format configuration** field, select the **BACS (UK)** format configuration.</span></span>

    ![Sidan Betalningsmetoder - leverantörer](./media/er-quick-start2-method-of-payment1.png)

6. <span data-ttu-id="7bf58-241">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="7bf58-241">Select **Save**.</span></span>

### <a name="process-a-vendor-payment"></a><a id="ProcessPayment1"></a><span data-ttu-id="7bf58-242">Bearbeta en leverantörsbetalning</span><span class="sxs-lookup"><span data-stu-id="7bf58-242">Process a vendor payment</span></span>

1. <span data-ttu-id="7bf58-243">Gå till **Leverantörsreskontra** \> **Betalningar** \> **Leverantörsbetalningsjournal**.</span><span class="sxs-lookup"><span data-stu-id="7bf58-243">Go to **Accounts payable** \> **Payments** \> **Vendor payment journal**.</span></span>
2. <span data-ttu-id="7bf58-244">På sidan **Leverantörsbetalningsjournal** väljer du den betalningsjournal som du lade till tidigare och väljer sedan **Rader**.</span><span class="sxs-lookup"><span data-stu-id="7bf58-244">On the **Vendor payment journal** page, select the payment journal that you added earlier, and then select **Lines**.</span></span>
3. <span data-ttu-id="7bf58-245">På sidan **Leverantörsbetalningar** välj **Generera betalningar**.</span><span class="sxs-lookup"><span data-stu-id="7bf58-245">On the **Vendor payments** page, select **Generate payments**.</span></span>
4. <span data-ttu-id="7bf58-246">Ange följande information i dialogrutan **Generera betalningar**:</span><span class="sxs-lookup"><span data-stu-id="7bf58-246">In the **Generate payments** dialog box, enter the following information:</span></span>

    - <span data-ttu-id="7bf58-247">I fältet **Betalningsmetod** väljer du **Elektronisk**.</span><span class="sxs-lookup"><span data-stu-id="7bf58-247">In the **Method of payment** field, select **Electronic**.</span></span>
    - <span data-ttu-id="7bf58-248">I fältet **Bankkonto** väljer du **GBSI OPER**.</span><span class="sxs-lookup"><span data-stu-id="7bf58-248">In the **Bank account** field, select **GBSI OPER**.</span></span>

5. <span data-ttu-id="7bf58-249">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="7bf58-249">Select **OK**.</span></span>
6. <span data-ttu-id="7bf58-250">I dialogrutan **Elektroniska rapportparametrar** anger du alternativet **Skriv ut kontrollrapport** till **Ja** och väljer sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="7bf58-250">In the **Electronic report parameters** dialog box, set the **Print control report** option to **Yes**, and then select **OK**.</span></span>

    ![Sidan Dialog för elektroniska rapportparametrar](./media/er-quick-start2-payment-dialog1.png)

    > [!NOTE]
    > <span data-ttu-id="7bf58-252">Förutom betalningsfilen kan du nu generera kontrollrapporten.</span><span class="sxs-lookup"><span data-stu-id="7bf58-252">In addition to the payment file, you can now generate the control report.</span></span>

7. <span data-ttu-id="7bf58-253">Hämta zip-filen och extrahera följande filer från den:</span><span class="sxs-lookup"><span data-stu-id="7bf58-253">Download the zip file, and then extract the following files from it:</span></span>

    - <span data-ttu-id="7bf58-254">Kontrollrapporten i Excel-format</span><span class="sxs-lookup"><span data-stu-id="7bf58-254">The control report in Excel format</span></span>
    - <span data-ttu-id="7bf58-255">Betalningsfil i TXT-format</span><span class="sxs-lookup"><span data-stu-id="7bf58-255">The payment file in TXT format</span></span>

        <span data-ttu-id="7bf58-256">Observera att i enlighet med [struktur](#PositionRoutingNumber) i den genererade filen börjar med det organisationsnummer som [definierats](#DefineRoutingNumber) för det konfigurerade bankkontot.</span><span class="sxs-lookup"><span data-stu-id="7bf58-256">Notice that, in accordance with the [structure](#PositionRoutingNumber) of the provided ER format, the payment line in the generated file starts with the routing number that was [defined](#DefineRoutingNumber) for the configured bank account.</span></span>

        ![Betalningsfil i TXT-format](./media/er-quick-start2-payment-file1.png)

## <a name="customize-the-standard-er-format"></a><a id="CustomizeProvidedFormat"></a><span data-ttu-id="7bf58-258">Anpassa ER-standardformatet</span><span class="sxs-lookup"><span data-stu-id="7bf58-258">Customize the standard ER format</span></span>

<span data-ttu-id="7bf58-259">För exemplet som visas i det här avsnittet vill du använda ER-konfigurationerna som tillhandahålls av Microsoft för att generera leverantörsbetalningsfiler i BACS-format, men du måste lägga till en anpassning för att stödja kraven för en specifik bank.</span><span class="sxs-lookup"><span data-stu-id="7bf58-259">For the example that is shown in this section, you want to use the ER configurations that are provided by Microsoft to generate vendor payment files in BACS format, but you must add a customization to support the requirements of a specific bank.</span></span> <span data-ttu-id="7bf58-260">Du vill också kunna uppgradera det anpassade formatet när nya versioner av ER-konfigurationer blir tillgängliga.</span><span class="sxs-lookup"><span data-stu-id="7bf58-260">You also want to be able to upgrade your custom format when new versions of ER configurations become available.</span></span> <span data-ttu-id="7bf58-261">Du vill dock kunna uppgradera till den lägsta kostnaden.</span><span class="sxs-lookup"><span data-stu-id="7bf58-261">However, you want to be able to do the upgrade at the lowest cost.</span></span>

<span data-ttu-id="7bf58-262">I det här fallet, som representant för Litware, Inc. måste du skapa (härledd) en ny ER-formatering genom att använda den **BACS (UK)** Microsoft-konfigurationen som bas.</span><span class="sxs-lookup"><span data-stu-id="7bf58-262">In this case, as the representative of Litware, Inc., you must create (derive) a new ER format configuration by using the **BACS (UK)** Microsoft-provided configuration as a base.</span></span>

### <a name="create-a-custom-format"></a><a id="DeriveProvidedFormat"></a><span data-ttu-id="7bf58-263">Skapa ett anpassat format</span><span class="sxs-lookup"><span data-stu-id="7bf58-263">Create a custom format</span></span>

1. <span data-ttu-id="7bf58-264">Gå till **Organisationsadministration** \> **Elektronisk rapportering** \> **Konfigurationer**.</span><span class="sxs-lookup"><span data-stu-id="7bf58-264">Go to **Organization administration** \> **Electronic reporting** \> **Configurations**.</span></span>
2. <span data-ttu-id="7bf58-265">På sidan **konfigurationer** i konfigurationsträdet i vänster fönster expanderar du **Betalningsmodell** och väljer sedan **BACS (UK)**.</span><span class="sxs-lookup"><span data-stu-id="7bf58-265">On the **Configurations** page, in the configuration tree in the left pane, expand **Payment model**, and then select **BACS (UK)**.</span></span> <span data-ttu-id="7bf58-266">Litware, Inc. kommer att använda version 1.1 av den här ER-formatkonfigurationen som bas för den anpassade versionen.</span><span class="sxs-lookup"><span data-stu-id="7bf58-266">Litware, Inc. will use version 1.1 of this ER format configuration as the base for the custom version.</span></span>
3. <span data-ttu-id="7bf58-267">Välj **Skapa konfiguration** om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="7bf58-267">Select **Create configuration** to open the drop-down dialog box.</span></span> <span data-ttu-id="7bf58-268">Du kan använda denna dialogruta för att skapa en ny konfiguration för ett anpassat betalningsformat.</span><span class="sxs-lookup"><span data-stu-id="7bf58-268">You can use this dialog box to create a new configuration for a custom payment format.</span></span>
4. <span data-ttu-id="7bf58-269">I fältgruppen **Ny** väljer du alternativet **Härled från namn: BACS (UK), Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="7bf58-269">In the **New** field group, select the **Derive from Name: BACS (UK), Microsoft** option.</span></span>
5. <span data-ttu-id="7bf58-270">I fältet **Namn** anger du **BACS (kund från Storbritannien)**.</span><span class="sxs-lookup"><span data-stu-id="7bf58-270">In the **Name** field, enter **BACS (UK custom)**.</span></span>

    ![Den nedrullningsbara dialogrutan skapa konfiguration](./media/er-quick-start2-add-derived-format.png)

6. <span data-ttu-id="7bf58-272">Välj **Skapa konfiguration**.</span><span class="sxs-lookup"><span data-stu-id="7bf58-272">Select **Create configuration**.</span></span>

<span data-ttu-id="7bf58-273">Version 1.1.1 av **BACS (kund från Storbritannien)** ER-formatkonfiguration har skapats.</span><span class="sxs-lookup"><span data-stu-id="7bf58-273">Version 1.1.1 of the **BACS (UK custom)** ER format configuration is created.</span></span> <span data-ttu-id="7bf58-274">Den här versionen har [status](general-electronic-reporting.md#component-versioning) av **utkast** och kan redigeras.</span><span class="sxs-lookup"><span data-stu-id="7bf58-274">This version has a [status](general-electronic-reporting.md#component-versioning) of **Draft** and can be edited.</span></span> <span data-ttu-id="7bf58-275">Det aktuella innehållet i det anpassade ER-formatet matchar innehållet i det format som tillhandahålls av Microsoft.</span><span class="sxs-lookup"><span data-stu-id="7bf58-275">The current content of your custom ER format matches the content of the format that is provided by Microsoft.</span></span>

![Sidan Konfigurationer](./media/er-quick-start2-derived-format-configuration1.png)

### <a name="edit-a-custom-format"></a><a id="ConfigureDerivedFormat"></a><span data-ttu-id="7bf58-277">Redigera ett anpassat format</span><span class="sxs-lookup"><span data-stu-id="7bf58-277">Edit a custom format</span></span>

<span data-ttu-id="7bf58-278">Du måste konfigurera det anpassade formatet så att det uppfyller de bankspecifika kraven.</span><span class="sxs-lookup"><span data-stu-id="7bf58-278">You must configure your custom format so that it meets bank-specific requirements.</span></span> <span data-ttu-id="7bf58-279">En bank kan t.ex. kräva att betalningsfiler som genereras inkluderar samhället i den globala SWIFT-koden (Financial Telecommunication Interbank) för en bank som tilldelas agentrollen i den bearbetade leverantörsbetalningen.</span><span class="sxs-lookup"><span data-stu-id="7bf58-279">For example, a bank might require that payment files that are generated include the Society for Worldwide Interbank Financial Telecommunication (SWIFT) code of a bank that is assigned the agent role in the processed vendor payment.</span></span> <span data-ttu-id="7bf58-280">SWIFT-koder är internationella bankkoder som identifierar specifika banker över hela världen.</span><span class="sxs-lookup"><span data-stu-id="7bf58-280">SWIFT codes are international bank codes that identify specific banks worldwide.</span></span> <span data-ttu-id="7bf58-281">De är också kända som BIC (Bank Identifier Codes).</span><span class="sxs-lookup"><span data-stu-id="7bf58-281">They are also known as Bank Identifier Codes (BICs).</span></span> <span data-ttu-id="7bf58-282">SWIFT-koden måste vara 11 tecken lång och den måste anges i början av varje betalningsrad i en genererad betalningsfil.</span><span class="sxs-lookup"><span data-stu-id="7bf58-282">The SWIFT code must be 11 characters long, and it must be entered at the beginning of every payment line in a generated payment file.</span></span>

1. <span data-ttu-id="7bf58-283">Gå till **Organisationsadministration** \> **Elektronisk rapportering** \> **Konfigurationer**.</span><span class="sxs-lookup"><span data-stu-id="7bf58-283">Go to **Organization administration** \> **Electronic reporting** \> **Configurations**.</span></span>
2. <span data-ttu-id="7bf58-284">På sidan **konfigurationer** i konfigurationsträdet i vänster fönster expanderar du **Betalningsmodell** och väljer sedan **BACS (kund från Storbritannien)**.</span><span class="sxs-lookup"><span data-stu-id="7bf58-284">On the **Configurations** page, in the configuration tree in the left pane, expand **Payment model**, and then select **BACS (UK custom)**.</span></span>
3. <span data-ttu-id="7bf58-285">På snabbfliken **Versioner** välj version **1.1.1** av den valda konfigurationen.</span><span class="sxs-lookup"><span data-stu-id="7bf58-285">On the **Versions** FastTab, select version **1.1.1** of the selected configuration.</span></span>
4. <span data-ttu-id="7bf58-286">Välj **Designer**.</span><span class="sxs-lookup"><span data-stu-id="7bf58-286">Select **Designer**.</span></span>
5. <span data-ttu-id="7bf58-287">På sidan **Formatdesigner** väljer du **Visa information** om du vill visa mer information om formatelementen.</span><span class="sxs-lookup"><span data-stu-id="7bf58-287">On the **Format designer** page, select **Show details** to view more information about the format elements.</span></span>
6. <span data-ttu-id="7bf58-288">Expandera och granska följande element:</span><span class="sxs-lookup"><span data-stu-id="7bf58-288">Expand and review the following elements:</span></span>

    - <span data-ttu-id="7bf58-289">Elementet **BACSReportsFolder** av typen **Mapp**.</span><span class="sxs-lookup"><span data-stu-id="7bf58-289">The **BACSReportsFolder** element of the **Folder** type.</span></span> <span data-ttu-id="7bf58-290">Det här elementet används för att generera utdata i ZIP-format.</span><span class="sxs-lookup"><span data-stu-id="7bf58-290">This element is used to generate output in ZIP format.</span></span>
    - <span data-ttu-id="7bf58-291">Elementet **fil** av typen **Fil**.</span><span class="sxs-lookup"><span data-stu-id="7bf58-291">The **file** element of the **File** type.</span></span> <span data-ttu-id="7bf58-292">Det här elementet används för att generera en betalningsfil i TXT-format.</span><span class="sxs-lookup"><span data-stu-id="7bf58-292">This element is used to generate a payment file in TXT format.</span></span>
    - <span data-ttu-id="7bf58-293">Elementet **transaktioner** av typen **Sekvens**.</span><span class="sxs-lookup"><span data-stu-id="7bf58-293">The **transactions** element of the **Sequence** type.</span></span> <span data-ttu-id="7bf58-294">Det här elementet används för att generera en enda betalningsrad i en betalningsfil.</span><span class="sxs-lookup"><span data-stu-id="7bf58-294">This element is used to generate a single payment line in a payment file.</span></span>
    - <span data-ttu-id="7bf58-295">Elementet **transaktion** av typen **Sekvens**.</span><span class="sxs-lookup"><span data-stu-id="7bf58-295">The **transaction** element of the **Sequence** type.</span></span> <span data-ttu-id="7bf58-296">Det här elementet används för att generera individuella fält av en enda betalningsrad.</span><span class="sxs-lookup"><span data-stu-id="7bf58-296">This element is used to generate individual fields of a single payment line.</span></span>

7. <span data-ttu-id="7bf58-297">Välj elementet **transaktion**.</span><span class="sxs-lookup"><span data-stu-id="7bf58-297">Select the **transaction** element.</span></span>

    ![Transaktionselement i ER-åtgärdsdesigner](./media/er-quick-start2-derived-format0.png)

    > [!NOTE]
    > <span data-ttu-id="7bf58-299">Den angivna rapporten konfigureras så att <a id="PositionRoutingNumber"></a>varje betalningsrad inleds med bankens organisationsnummer.</span><span class="sxs-lookup"><span data-stu-id="7bf58-299">The provided report is configured so that <a id="PositionRoutingNumber"></a>every payment line starts with the bank routing number.</span></span> <span data-ttu-id="7bf58-300">Formatelementet **vendBankRouteNum** används för detta syfte.</span><span class="sxs-lookup"><span data-stu-id="7bf58-300">The **vendBankRouteNum** format element is used for this purpose.</span></span> 

8. <span data-ttu-id="7bf58-301">Välj **Lägg till** och välj sedan typen **Text\\Sträng** för det formatelement som du vill lägga till:</span><span class="sxs-lookup"><span data-stu-id="7bf58-301">Select **Add**, and then select the **Text\\String** type of the format element that you're adding:</span></span>

    1. <span data-ttu-id="7bf58-302">I fältet **Namn** anger du **vendBankSWIFT**.</span><span class="sxs-lookup"><span data-stu-id="7bf58-302">In the **Name** field, enter **vendBankSWIFT**.</span></span>
    2. <span data-ttu-id="7bf58-303">I fältet **Minsta längd** anger du **11**.</span><span class="sxs-lookup"><span data-stu-id="7bf58-303">In the **Minimum length** field, enter **11**.</span></span>
    3. <span data-ttu-id="7bf58-304">I fältet **Maximal längd** anger du **11**.</span><span class="sxs-lookup"><span data-stu-id="7bf58-304">In the **Maximum length** field, enter **11**.</span></span>
    4. <span data-ttu-id="7bf58-305">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="7bf58-305">Select **OK**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="7bf58-306">Elementet **VendBankSWIFT** används för att ange SWIFT-koden för en leverantörsbank i genererade filer.</span><span class="sxs-lookup"><span data-stu-id="7bf58-306">The **vendBankSWIFT** element will be used to enter the SWIFT code of a vendor bank in generated files.</span></span>

9. <span data-ttu-id="7bf58-307">I formatstrukturträdet, välj **vendBankSWIFT**.</span><span class="sxs-lookup"><span data-stu-id="7bf58-307">In the format structure tree, select **vendBankSWIFT**.</span></span>
10. <span data-ttu-id="7bf58-308">Välj **Flytta upp** om du vill flytta det valda format elementet en nivå uppåt.</span><span class="sxs-lookup"><span data-stu-id="7bf58-308">Select **Move up** to move the selected format element up one level.</span></span> <span data-ttu-id="7bf58-309">Upprepa det här steget tills elementet **vendBankSWIFT** är det <a id="PositionSWIFTCode"></a>första elementet under det överordnade elementet **transaktion**.</span><span class="sxs-lookup"><span data-stu-id="7bf58-309">Repeat this step until the **vendBankSWIFT** element is the <a id="PositionSWIFTCode"></a>first element under the parent **transaction** element.</span></span>

    ![VendBankSWIFT som första del under transaktionen i ER-åtgärdsdesigner](./media/er-quick-start2-derived-format1.png)

11. <span data-ttu-id="7bf58-311">När **vendBankSWIFT** fortfarande är markerat i formatstrukturträdet väljer du fliken **mappning** och expanderar sedan **modell** datakällan.</span><span class="sxs-lookup"><span data-stu-id="7bf58-311">While the **vendBankSWIFT** is still selected in the format structure tree, select the **Mapping** tab, and then expand the **model** data source.</span></span>
12. <span data-ttu-id="7bf58-312">Expandera **model.Payment** \> **model.Payment.CreditorAgent** och välj fält **model.Payment.CreditorAgent.BICFI** för datakälla.</span><span class="sxs-lookup"><span data-stu-id="7bf58-312">Expand **model.Payment** \> **model.Payment.CreditorAgent**, and select the **model.Payment.CreditorAgent.BICFI** data source field.</span></span> <span data-ttu-id="7bf58-313">Det här fältet i datakällan visar SWIFT-koden för en leverantörs bank som har tilldelats agentrollen i den bearbetade leverantörsbetalningen.</span><span class="sxs-lookup"><span data-stu-id="7bf58-313">This data source field exposes the SWIFT code of a vendor bank that is assigned the agent role in the processed vendor payment.</span></span>
13. <span data-ttu-id="7bf58-314">Välj **bind**.</span><span class="sxs-lookup"><span data-stu-id="7bf58-314">Select **Bind**.</span></span> <span data-ttu-id="7bf58-315">Formatelementet **vendBankSWIFT** är nu bundet med fältet **model.Payment.CreditorAgent.BICFI** för datakälla så att SWIFT-koder anges i den genererade betalningsfilen.</span><span class="sxs-lookup"><span data-stu-id="7bf58-315">The **vendBankSWIFT** format element is now bound with the **model.Payment.CreditorAgent.BICFI** data source field, so that SWIFT codes will be entered in generated payment files.</span></span>

    ![vendBankSWIFT formatelement som är kopplat till model.Payment.CreditorAgent.BICFI fältet datakälla i ER-åtgärdsdesigner](./media/er-quick-start2-derived-format2.png)

14. <span data-ttu-id="7bf58-317">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="7bf58-317">Select **Save**.</span></span>
15. <span data-ttu-id="7bf58-318">Stäng designersidan.</span><span class="sxs-lookup"><span data-stu-id="7bf58-318">Close the designer page.</span></span>

### <a name="mark-a-custom-format-as-runnable"></a><a id="MarkFormatRunnable"></a><span data-ttu-id="7bf58-319">Markera ett anpassat format som körbart</span><span class="sxs-lookup"><span data-stu-id="7bf58-319">Mark a custom format as runnable</span></span>

<span data-ttu-id="7bf58-320">Nu när den första versionen av det anpassade formatet har skapats och har statusen **utkast** kan du köra den i testsyfte.</span><span class="sxs-lookup"><span data-stu-id="7bf58-320">Now that the first version of your custom format has been created and has a status of **Draft**, you can run it for testing purposes.</span></span> <span data-ttu-id="7bf58-321">Om du vill köra rapporten måste du bearbeta en leverantörsbetalning genom att använda betalningsmetoden som refererar till det anpassade ER-formatet.</span><span class="sxs-lookup"><span data-stu-id="7bf58-321">To run the report, you must process a vendor payment by using the payment method that refers to your custom ER format.</span></span> <span data-ttu-id="7bf58-322">Som standard, när du anropar ett ER-format från appen kan endast versioner som har status **slutförd** eller **delad** [beaktas](general-electronic-reporting.md#component-versioning).</span><span class="sxs-lookup"><span data-stu-id="7bf58-322">By default, when you call an ER format from the application, only versions that have a status of **Completed** or **Shared** are [considered](general-electronic-reporting.md#component-versioning).</span></span> <span data-ttu-id="7bf58-323">Det här beteendet gör det enklare att använda ER-format som inte innehåller färdiga designer.</span><span class="sxs-lookup"><span data-stu-id="7bf58-323">This behavior helps prevent ER formats that have unfinished designs from being used.</span></span> <span data-ttu-id="7bf58-324">För att testet ska kunna köras kan du dock tvinga appen att använda den version av ditt ER-format som har statusen **utkast**.</span><span class="sxs-lookup"><span data-stu-id="7bf58-324">However, for your test runs, you can force the application to use the version of your ER format that has a status of **Draft**.</span></span> <span data-ttu-id="7bf58-325">På det här sättet kan du justera den aktuella formatversionen om du behöver göra ändringar.</span><span class="sxs-lookup"><span data-stu-id="7bf58-325">In this way, you can adjust the current format version if any modifications are required.</span></span> <span data-ttu-id="7bf58-326">Mer information finns i [Tillämplighet](electronic-reporting-destinations.md#applicability).</span><span class="sxs-lookup"><span data-stu-id="7bf58-326">For more information, see [Applicability](electronic-reporting-destinations.md#applicability).</span></span>

<span data-ttu-id="7bf58-327">Om du vill använda utkastversionen av ett ER-format måste du markera ER-format på tydligt sätt.</span><span class="sxs-lookup"><span data-stu-id="7bf58-327">To use the draft version of an ER format, you must explicitly mark the ER format.</span></span>

1. <span data-ttu-id="7bf58-328">Gå till **Organisationsadministration** \> **Elektronisk rapportering** \> **Konfigurationer**.</span><span class="sxs-lookup"><span data-stu-id="7bf58-328">Go to **Organization administration** \> **Electronic reporting** \> **Configurations**.</span></span>
2. <span data-ttu-id="7bf58-329">På sidan **Konfigurationer** i åtgärdsfönstret, på fliken **Konfigurationer** i gruppen **Avancerad inställningar** markerar du **Använd parametrar**.</span><span class="sxs-lookup"><span data-stu-id="7bf58-329">On the **Configurations** page, on the Action Pane, on the **Configurations** tab, in the **Advanced settings** group, select **User parameters**.</span></span>
3. <span data-ttu-id="7bf58-330">I dialogrutan **Användarparametrar** ange alternativet **Kör inställningar** till **Ja** och väljer sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="7bf58-330">In the **User parameters** dialog box, set the **Run settings** option to **Yes**, and then select **OK**.</span></span>
4. <span data-ttu-id="7bf58-331">Välj **redigera** för att göra den aktuella sidan klar för redigering.</span><span class="sxs-lookup"><span data-stu-id="7bf58-331">Select **Edit** to make the current page editable, as required.</span></span>
5. <span data-ttu-id="7bf58-332">I konfigurationsträdet i det vänstra fönstret, välj **BACS (kund från Storbritannien)**.</span><span class="sxs-lookup"><span data-stu-id="7bf58-332">In the configuration tree in the left pane, select **BACS (UK custom)**.</span></span>
6. <span data-ttu-id="7bf58-333">Ge alternativet **Kör utkast** värdet **Ja**.</span><span class="sxs-lookup"><span data-stu-id="7bf58-333">Set the **Run Draft** option to **Yes**.</span></span>

    ![Alternativet Kör utkast på sidan konfigurationer](./media/er-quick-start2-derived-format-configuration2.png)

## <a name="process-a-vendor-payment-by-using-the-custom-er-format"></a><a id="ProcessVendorPayment2"></a><span data-ttu-id="7bf58-335">Bearbeta en leverantörsbetalning med hjälp av anpassat ER-format</span><span class="sxs-lookup"><span data-stu-id="7bf58-335">Process a vendor payment by using the custom ER format</span></span>

### <a name="set-up-the-electronic-payment-method"></a><a id="ConfigureMethodOfPayment2"></a><span data-ttu-id="7bf58-336">Ange den elektroniska betalningsmetoden</span><span class="sxs-lookup"><span data-stu-id="7bf58-336">Set up the electronic payment method</span></span>

<span data-ttu-id="7bf58-337">Du måste konfigurera den elektroniska betalningsmetoden så att ditt eget ER-format används för att bearbeta leverantörsbetalningar.</span><span class="sxs-lookup"><span data-stu-id="7bf58-337">You must configure the electronic method of payment so that your custom ER format is used to process vendor payments.</span></span>

1. <span data-ttu-id="7bf58-338">Gå till **Leverantörsreskontra** \> **Betalningsinställning** \> **Betalningsmetoder**.</span><span class="sxs-lookup"><span data-stu-id="7bf58-338">Go to **Accounts payable** \> **Payment setup** \> **Methods of payment**.</span></span>
2. <span data-ttu-id="7bf58-339">På sidan **Betalningsmetoder - leverantörer** välj metoden **Elektronisk** i det vänstra fönstret.</span><span class="sxs-lookup"><span data-stu-id="7bf58-339">On the **Methods of payment - vendors** page, select the **Electronic** method of payment in the left pane.</span></span>
3. <span data-ttu-id="7bf58-340">Välj **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="7bf58-340">Select **Edit**.</span></span>
4. <span data-ttu-id="7bf58-341">På snabbfliken **filformat** ställer du in alternativet **Allmänt elektroniskt exportformat** till **Ja**.</span><span class="sxs-lookup"><span data-stu-id="7bf58-341">On the **File format** FastTab, set the **General electronic export format** option to **Yes**.</span></span>
5. <span data-ttu-id="7bf58-342">I fältet **Exportformatkonfiguration** väljer du formatkonfigurationen **BACS (kund från Storbritannien)**.</span><span class="sxs-lookup"><span data-stu-id="7bf58-342">In the **Export format configuration** field, select the **BACS (UK custom)** format configuration.</span></span>

    ![Sidan Betalningsmetoder - leverantörer](./media/er-quick-start2-method-of-payment2.png)

6. <span data-ttu-id="7bf58-344">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="7bf58-344">Select **Save**.</span></span>

### <a name="process-a-vendor-payment"></a><a id="ProcessPayment2"></a><span data-ttu-id="7bf58-345">Bearbeta en leverantörsbetalning</span><span class="sxs-lookup"><span data-stu-id="7bf58-345">Process a vendor payment</span></span>

1. <span data-ttu-id="7bf58-346">Gå till **Leverantörsreskontra** \> **Betalningar** \> **Leverantörsbetalningsjournal**.</span><span class="sxs-lookup"><span data-stu-id="7bf58-346">Go to **Accounts payable** \> **Payments** \> **Vendor payment journal**.</span></span>
2. <span data-ttu-id="7bf58-347">På sidan **Leverantörsbetalningsjournal** väljer du den betalningsjournal som du skapade tidigare.</span><span class="sxs-lookup"><span data-stu-id="7bf58-347">On the **Vendor payment journal** page, select the payment journal that you created earlier.</span></span>
3. <span data-ttu-id="7bf58-348">Markera **rader**</span><span class="sxs-lookup"><span data-stu-id="7bf58-348">Select **Lines**.</span></span>
4. <span data-ttu-id="7bf58-349">På sidan **leverantörsbetalningar** ovanför rutnätet väljer du **betalningsstatus** \> **ingen**.</span><span class="sxs-lookup"><span data-stu-id="7bf58-349">On the **Vendor payments** page, above the grid, select **Payment status** \> **None**.</span></span>
5. <span data-ttu-id="7bf58-350">Välj **Generera betalning**.</span><span class="sxs-lookup"><span data-stu-id="7bf58-350">Select **Generate payment**.</span></span>
6. <span data-ttu-id="7bf58-351">Ange följande information i dialogrutan **Generera betalningar**:</span><span class="sxs-lookup"><span data-stu-id="7bf58-351">In the **Generate payments** dialog box, enter the following information:</span></span>

    - <span data-ttu-id="7bf58-352">I fältet **Betalningsmetod** väljer du **Elektronisk**.</span><span class="sxs-lookup"><span data-stu-id="7bf58-352">In the **Method of payment** field, select **Electronic**.</span></span>
    - <span data-ttu-id="7bf58-353">I fältet **Bankkonto** väljer du **GBSI OPER**.</span><span class="sxs-lookup"><span data-stu-id="7bf58-353">In the **Bank account** field, select **GBSI OPER**.</span></span>

7. <span data-ttu-id="7bf58-354">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="7bf58-354">Select **OK**.</span></span>
8. <span data-ttu-id="7bf58-355">I dialogrutan **Elektroniska rapportparametrar** anger du alternativet **Skriv ut kontrollrapport** till **Ja** och väljer sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="7bf58-355">In the **Electronic report parameters** dialog box, set the **Print control report** option to **Yes**, and then select **OK**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="7bf58-356">Förutom betalningsfilen kan du endast generera kontrollrapporten.</span><span class="sxs-lookup"><span data-stu-id="7bf58-356">In addition to the payment file, you can generate only the control report.</span></span>

9. <span data-ttu-id="7bf58-357">Hämta zip-filen och extrahera följande filer från den:</span><span class="sxs-lookup"><span data-stu-id="7bf58-357">Download the zip file, and then extract the following files from it:</span></span>

    - <span data-ttu-id="7bf58-358">Kontrollrapporten i Excel-format</span><span class="sxs-lookup"><span data-stu-id="7bf58-358">The control report in Excel format</span></span>
    - <span data-ttu-id="7bf58-359">Betalningsfil i TXT-format</span><span class="sxs-lookup"><span data-stu-id="7bf58-359">The payment file in TXT format</span></span>

        <span data-ttu-id="7bf58-360">Lägg märke till att betalningsraden i den genererade filen, i enlighet med strukturen i ditt anpassade ER-format, nu [startar](#PositionSWIFTCode) med SWIFT-kod som var [angav](#DefineSWIFTCode) för bankkontot för leverantören vars betalning har behandlats.</span><span class="sxs-lookup"><span data-stu-id="7bf58-360">Notice that, in accordance with the structure of your custom ER format, the payment line in the generated file now [starts](#PositionSWIFTCode) with the SWIFT code that was [entered](#DefineSWIFTCode) for the bank account of the vendor whose payment has been processed.</span></span>

        ![Betalningsfil i TXT-format](./media/er-quick-start2-payment-file2.png)

## <a name="import-new-versions-of-the-standard-er-format-configurations"></a><a id="ImportERSolution2"></a><span data-ttu-id="7bf58-362">Importera nya versioner av standardkonfiguration av ER-format</span><span class="sxs-lookup"><span data-stu-id="7bf58-362">Import new versions of the standard ER format configurations</span></span>

<span data-ttu-id="7bf58-363">För exemplet som visas i det här avsnittet får du ett meddelande om Knowledge Base-artikeln [KB 3763330](https://fix.lcs.dynamics.com/Issue/Details?kb=3182046).</span><span class="sxs-lookup"><span data-stu-id="7bf58-363">For the example that is shown in this section, you receive a notification about Knowledge Base article [KB3763330](https://fix.lcs.dynamics.com/Issue/Details?kb=3182046).</span></span> <span data-ttu-id="7bf58-364">I det här meddelandet får du information om den nya versionen av **BACS (UK)** ER-format som har publicerats av Microsoft.</span><span class="sxs-lookup"><span data-stu-id="7bf58-364">This notification informs you about the new version of the **BACS (UK)** ER format that has been published by Microsoft.</span></span> <span data-ttu-id="7bf58-365">Förutom kontrollrapporten kan användarna skapa betalningsavirapporten och rapporten för notering av deltagande när en leverantörsbetalning bearbetas.</span><span class="sxs-lookup"><span data-stu-id="7bf58-365">In addition to the control report, this new version lets users generate the payment advice report and the attending note report while a vendor payment is being processed.</span></span> <span data-ttu-id="7bf58-366">Du vill börja använda den funktionen.</span><span class="sxs-lookup"><span data-stu-id="7bf58-366">You want to start to use that functionality.</span></span>

### <a name="import-new-versions-of-the-standard-er-configurations"></a><a id="ImportERFormat2"></a><span data-ttu-id="7bf58-367">Importera nya versioner av ER-standardkonfigurationer</span><span class="sxs-lookup"><span data-stu-id="7bf58-367">Import new versions of the standard ER configurations</span></span>

<span data-ttu-id="7bf58-368">Om du vill lägga till nya versioner av ER-konfigurationer i din aktuella Finance-instans måste du importera dem från ER [databasen](general-electronic-reporting.md#Repository) som du har konfigurerat.</span><span class="sxs-lookup"><span data-stu-id="7bf58-368">To add new versions of the ER configurations to the current Finance instance, you must import them from the ER [repository](general-electronic-reporting.md#Repository) that you've configured.</span></span>

1. <span data-ttu-id="7bf58-369">Gå till **Organisationsadministration** \> **Arbetsytor** \> **Elektronisk rapportering**.</span><span class="sxs-lookup"><span data-stu-id="7bf58-369">Go to **Organization administration** \> **Workspaces** \> **Electronic reporting**.</span></span>
2. <span data-ttu-id="7bf58-370">På sidan **lokaliseringskonfiguration** i avsnittet **konfigurationsleverantörer** välj panelen **Microsoft** och markera sedan **databaser** om du vill visa listan över databaser för Microsoft-leverantören.</span><span class="sxs-lookup"><span data-stu-id="7bf58-370">On the **Localization configurations** page, in the **Configuration providers** section, select the **Microsoft** tile, and then select **Repositories** to view the list of repositories for the Microsoft provider.</span></span>
3. <span data-ttu-id="7bf58-371">På sidan **Konfigurationsdatabaser** väljer du i rutnätet den befintliga databasen för **Global**-typ och väljer sedan **Öppna**.</span><span class="sxs-lookup"><span data-stu-id="7bf58-371">On the **Configuration repositories** page, select the repository of the **Global** type, and then select **Open**.</span></span> <span data-ttu-id="7bf58-372">Om du uppmanas att bevilja behörighet att ansluta till Regulatory Configuration Service följer du instruktionerna för auktorisering.</span><span class="sxs-lookup"><span data-stu-id="7bf58-372">If you're prompted for authorization to connect to Regulatory Configuration Service, follow the authorization instructions.</span></span>
4. <span data-ttu-id="7bf58-373">På sidan **Konfigurationsdatabas** i konfigurationsträdet i vänster fönster, välj den **BACS (UK)**-formatkonfiguration.</span><span class="sxs-lookup"><span data-stu-id="7bf58-373">On the **Configuration repository** page, in the configuration tree in the left pane, select the **BACS (UK)** format configuration.</span></span>
5. <span data-ttu-id="7bf58-374">På snabbfliken **Versioner** välj version **3.3** av den valda ER-formatkonfigurationen.</span><span class="sxs-lookup"><span data-stu-id="7bf58-374">On the **Versions** FastTab, select version **3.3** of the selected ER format configuration.</span></span>
6. <span data-ttu-id="7bf58-375">Välj **Importera** för att hämta den valda versionen från den globala databasen till den aktuella Finance-instansen.</span><span class="sxs-lookup"><span data-stu-id="7bf58-375">Select **Import** to download the selected version from the Global repository to the current Finance instance.</span></span>

![Sidan Konfigurationsdatabas](./media/er-quick-start2-import-solution2.png)

> [!TIP]
> <span data-ttu-id="7bf58-377">Om du har problem med att komma åt den [Global databasen](er-download-configurations-global-repo.md), kan du [hämta konfigurationer](download-electronic-reporting-configuration-lcs.md) från LCS istället.</span><span class="sxs-lookup"><span data-stu-id="7bf58-377">If you have trouble accessing the [Global repository](er-download-configurations-global-repo.md), you can [download configurations](download-electronic-reporting-configuration-lcs.md) from LCS instead.</span></span>

### <a name="review-the-imported-er-format-configurations"></a><a id="ReviewImportedERFormat"></a><span data-ttu-id="7bf58-378">Granska importerade ER-formatkonfigurationer</span><span class="sxs-lookup"><span data-stu-id="7bf58-378">Review the imported ER format configurations</span></span>

1. <span data-ttu-id="7bf58-379">Gå till **Organisationsadministration** \> **Arbetsytor** \> **Elektronisk rapportering**.</span><span class="sxs-lookup"><span data-stu-id="7bf58-379">Go to **Organization administration** \> **Workspaces** \> **Electronic reporting**.</span></span>
2. <span data-ttu-id="7bf58-380">På sidan **Lokaliseringskonfiguration** i avsnittet **Konfigurationer** väljer du panelen **Rapporteringskonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="7bf58-380">On the **Localization configurations** page, in the **Configurations** section, select the **Reporting configurations** tile.</span></span>
3. <span data-ttu-id="7bf58-381">På sidan **konfigurationer** i konfigurationsträdet i vänster fönster expanderar du **Betalningsmodell** och väljer sedan **BACS (UK)**.</span><span class="sxs-lookup"><span data-stu-id="7bf58-381">On the **Configurations** page, in the configuration tree in the left pane, expand **Payment model**, and then select **BACS (UK)**.</span></span>
4. <span data-ttu-id="7bf58-382">På snabbfliken **Versioner**, välj version **3.3**.</span><span class="sxs-lookup"><span data-stu-id="7bf58-382">On the **Versions** FastTab, select version **3.3**.</span></span>
5. <span data-ttu-id="7bf58-383">Välj **Designer**.</span><span class="sxs-lookup"><span data-stu-id="7bf58-383">Select **Designer**.</span></span>
6. <span data-ttu-id="7bf58-384">På sidan **Formatdesigner** expandera **BACSReportsFolder** formatelement.</span><span class="sxs-lookup"><span data-stu-id="7bf58-384">On the **Format designer** page, expand the **BACSReportsFolder** format element.</span></span>
7.  <span data-ttu-id="7bf58-385">Observera att version 3.3 innehåller det **PaymentAdviceReport** formatelement som används för att generera en betalningsavirapport när en leverantörsbetalning bearbetas.</span><span class="sxs-lookup"><span data-stu-id="7bf58-385">Notice that version 3.3 contains the **PaymentAdviceReport** format element that is used to generate a payment advice report when a vendor payment is processed.</span></span>

    ![PaymentAdviceReport-formatelement i ER-åtgärdsdesigner](./media/er-quick-start2-imported-solution2.png)

8. <span data-ttu-id="7bf58-387">Stäng designersidan.</span><span class="sxs-lookup"><span data-stu-id="7bf58-387">Close the designer page.</span></span>

## <a name="adopt-the-changes-in-the-new-version-of-an-imported-format-in-a-custom-format"></a><a id="AdoptNewBaseVersion"></a><span data-ttu-id="7bf58-388">Tillämpa ändringarna i den nya versionen av ett importerat format i ett anpassat format</span><span class="sxs-lookup"><span data-stu-id="7bf58-388">Adopt the changes in the new version of an imported format in a custom format</span></span>

### <a name="complete-the-current-draft-version-of-a-custom-format"></a><a id="CompleteDerivedFormat"></a><span data-ttu-id="7bf58-389">Slutför den nuvarande utkastversionen av ett anpassat format</span><span class="sxs-lookup"><span data-stu-id="7bf58-389">Complete the current draft version of a custom format</span></span>

<span data-ttu-id="7bf58-390">Om du vill behålla det anpassade formatets aktuella status ska du fylla i utkast version 1.1.1 genom att ändra dess status från **utkast** till **slutförd**.</span><span class="sxs-lookup"><span data-stu-id="7bf58-390">If you want to keep the current state of your custom format, complete the draft version 1.1.1 by changing its status from **Draft** to **Completed**.</span></span>

1. <span data-ttu-id="7bf58-391">Gå till **Organisationsadministration** \> **Arbetsytor** \> **Elektronisk rapportering**.</span><span class="sxs-lookup"><span data-stu-id="7bf58-391">Go to **Organization administration** \> **Workspaces** \> **Electronic reporting**.</span></span>
2. <span data-ttu-id="7bf58-392">På sidan **Lokaliseringskonfiguration** i avsnittet **Konfigurationer** väljer du panelen **Rapporteringskonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="7bf58-392">On the **Localization configurations** page, in the **Configurations** section, select the **Reporting configurations** tile.</span></span>
3. <span data-ttu-id="7bf58-393">På sidan **konfigurationer** i konfigurationsträdet i vänster fönster expanderar du **Betalningsmodell**, expandera **BACS (UK)** och väljer sedan **BACS (kund från Storbritannien)**.</span><span class="sxs-lookup"><span data-stu-id="7bf58-393">On the **Configurations** page, in the configuration tree in the left pane, expand **Payment model**, expand **BACS (UK)**, and then select **BACS (UK custom)**.</span></span>
4. <span data-ttu-id="7bf58-394">På snabbfliken **Versioner** välj **Ändra status** \> **Slutförd** och välj sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="7bf58-394">On the **Versions** FastTab, select **Change status** \> **Complete**, and then select **OK**.</span></span>

<span data-ttu-id="7bf58-395">Status för version 1.1.1 ändras från **utkast** till **slutfört** och versionen blir skrivskyddad.</span><span class="sxs-lookup"><span data-stu-id="7bf58-395">The status of version 1.1.1 is changed from **Draft** to **Completed**, and the version becomes read-only.</span></span> <span data-ttu-id="7bf58-396">En ny redigerbar version, 1.1.2, har lagts till och har statusen **utkast**.</span><span class="sxs-lookup"><span data-stu-id="7bf58-396">A new editable version, 1.1.2, has been added and has a status of **Draft**.</span></span> <span data-ttu-id="7bf58-397">Du kan använda den här versionen för att göra ytterligare ändringar i det anpassade ER-formatet.</span><span class="sxs-lookup"><span data-stu-id="7bf58-397">You can use this version to make further changes in your custom ER format.</span></span>

### <a name="rebase-a-custom-format-to-a-new-base-version"></a><a id="RebaseDerivedFormat"></a><span data-ttu-id="7bf58-398">Basera ett anpassat format på en ny basversion</span><span class="sxs-lookup"><span data-stu-id="7bf58-398">Rebase a custom format to a new base version</span></span>

<span data-ttu-id="7bf58-399">Om du vill börja använda den nya funktionen i version 3.3 av **BACS (UK)** formatet i anpassningen måste du ändra baskonfigurationsversionen för den anpassade konfigurationen **BACS (kund från Storbritannien)**.</span><span class="sxs-lookup"><span data-stu-id="7bf58-399">To start to use the new functionality of version 3.3 of the **BACS (UK)** format in your customization, you must change the base configuration version for the custom configuration, **BACS (UK custom)**.</span></span> <span data-ttu-id="7bf58-400">Den här processen kallas för [ombasering](general-electronic-reporting.md#upgrading-a-format-selecting-a-new-version-of-base-format-rebase).</span><span class="sxs-lookup"><span data-stu-id="7bf58-400">This process is known as [rebasing](general-electronic-reporting.md#upgrading-a-format-selecting-a-new-version-of-base-format-rebase).</span></span> <span data-ttu-id="7bf58-401">I stället för version 1.1 oav **BACS (UK)**, använd version 3.3.</span><span class="sxs-lookup"><span data-stu-id="7bf58-401">Instead of version 1.1 of **BACS (UK)**, use version 3.3.</span></span>

1. <span data-ttu-id="7bf58-402">Gå till **Organisationsadministration** \> **Elektronisk rapportering** \> **Konfigurationer**.</span><span class="sxs-lookup"><span data-stu-id="7bf58-402">Go to **Organization administration** \> **Electronic reporting** \> **Configurations**.</span></span>
2. <span data-ttu-id="7bf58-403">På sidan **konfigurationer** i konfigurationsträdet i vänster fönster expanderar du **Betalningsmodell** och väljer sedan **BACS (kund från Storbritannien)**.</span><span class="sxs-lookup"><span data-stu-id="7bf58-403">On the **Configurations** page, in the configuration tree in the left pane, expand **Payment model**, and then select **BACS (UK custom)**.</span></span>
3. <span data-ttu-id="7bf58-404">På snabbfliken **Versioner** välj version **1.1.2** och välj sedan **Basera om**.</span><span class="sxs-lookup"><span data-stu-id="7bf58-404">On the **Versions** FastTab, select version **1.1.2**, and then select **Rebase**.</span></span>
4. <span data-ttu-id="7bf58-405">I dialogrutan **Basera om** i fältet **Målversion** välj version **3.3** av baskonfiguration att använda den som den nya basen och använda den för att uppdatera konfigurationen.</span><span class="sxs-lookup"><span data-stu-id="7bf58-405">In the **Rebase** dialog box, in the **Target version** field, select version **3.3** of the base configuration to apply it as the new base and use it to update the configuration.</span></span>

    ![Dialogrutan Basera om](./media/er-quick-start2-rebase1.png)

5. <span data-ttu-id="7bf58-407">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="7bf58-407">Select **OK**.</span></span>
6. <span data-ttu-id="7bf58-408">Observera att numret på utkastversionen har ändrats från **1.1.2** till **3.3.2** för att avspegla ändringen i basversionen.</span><span class="sxs-lookup"><span data-stu-id="7bf58-408">Notice that the number of the draft version has been changed from **1.1.2** to **3.3.2** to reflect the change in the base version.</span></span>

    <span data-ttu-id="7bf58-409">När den anpassade versionen och en ny basversion slås samman kan vissa konflikter upptäckas på grund av formatändringar som inte kan slås samman automatiskt.</span><span class="sxs-lookup"><span data-stu-id="7bf58-409">When the custom version and a new base version are merged, some conflicts might be discovered because of format changes that can't be merged automatically.</span></span>

    ![Ombaserad konfiguration med konflikter på sidan konfigurationer](./media/er-quick-start2-rebase2.png)

    <span data-ttu-id="7bf58-411">Om konflikter upptäcks måste de lösas manuellt i formatdesignern.</span><span class="sxs-lookup"><span data-stu-id="7bf58-411">If conflicts are discovered, they must be manually resolved in the format designer.</span></span>

7. <span data-ttu-id="7bf58-412">På snabbfliken **Versioner**, välj version **3.3.2**.</span><span class="sxs-lookup"><span data-stu-id="7bf58-412">On the **Versions** FastTab, select version **3.3.2**.</span></span>
8. <span data-ttu-id="7bf58-413">Välj **Designer**.</span><span class="sxs-lookup"><span data-stu-id="7bf58-413">Select **Designer**.</span></span>
9. <span data-ttu-id="7bf58-414">På sidan **Formatdesigner** på snabbfliken **Detaljer** välj posten ombasera konflikt och välj sedan **tillämpa basvärde**.</span><span class="sxs-lookup"><span data-stu-id="7bf58-414">On the **Format designer** page, on the **Details** FastTab, select a rebase conflict record, and then select **Apply base value**.</span></span>

    ![Posten ombasera konflikt i ER-åtgärdsdesigner](./media/er-quick-start2-rebase3.png)

10. <span data-ttu-id="7bf58-416">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="7bf58-416">Select **Save**.</span></span>

    <span data-ttu-id="7bf58-417">Posten ombasera konflikt ska inte längre visas på snabbfliken **information**.</span><span class="sxs-lookup"><span data-stu-id="7bf58-417">The rebase conflict record should no longer appear on the **Details** FastTab.</span></span>

    ![Konflikt lösas i ER-åtgärdsdesigner](./media/er-quick-start2-rebase4.png)

    > [!NOTE]
    > <span data-ttu-id="7bf58-419">Du har löst konflikten genom att bekräfta att version 3 av basmodellen måste användas i detta ER-format.</span><span class="sxs-lookup"><span data-stu-id="7bf58-419">You resolved the conflict by confirming that version 3 of the base model must be used in this ER format.</span></span>

11. <span data-ttu-id="7bf58-420">Expandera **BACSReportsFolder** \> **fil** \> **transaktioner** \> **transaktion**.</span><span class="sxs-lookup"><span data-stu-id="7bf58-420">Expand **BACSReportsFolder** \> **file** \> **transactions** \> **transaction**.</span></span>
12. <span data-ttu-id="7bf58-421">På fliken **Mappning** observera att version 3.3.2 av ditt anpassade ER-format innehåller både din anpassning (formatelementet **vendBankSWIFT** och dess bindning) och de nya funktionerna i version 3.3 av grundläggande ER-format som tillhandahölls av Microsoft (**PaymentAdviceReport** formatelement tillsammans med det är kapslade element och konfigurerade bindningar).</span><span class="sxs-lookup"><span data-stu-id="7bf58-421">On the **Mapping** tab, notice that version 3.3.2 of your custom ER format contains both your customization (the **vendBankSWIFT** format element and its binding) and the new functionality of version 3.3 of the base ER format that was provided by Microsoft (the **PaymentAdviceReport** format element together with its nested elements and configured bindings).</span></span> <span data-ttu-id="7bf58-422">Med bara några musklick kan du tillämpa ändringarna i en ny grundläggande version genom att koppla dem till dina anpassningar.</span><span class="sxs-lookup"><span data-stu-id="7bf58-422">In just a few mouse clicks, you adopted the modifications of a new base version by merging them with your customization.</span></span>

    ![Kopplat format i ER-åtgärdsdesigner](./media/er-quick-start2-rebase5.png)

13. <span data-ttu-id="7bf58-424">Stäng designersidan.</span><span class="sxs-lookup"><span data-stu-id="7bf58-424">Close the designer page.</span></span>

> [!NOTE]
> <span data-ttu-id="7bf58-425">Instruktionen för ombasering går att ångra.</span><span class="sxs-lookup"><span data-stu-id="7bf58-425">The rebase action is reversible.</span></span> <span data-ttu-id="7bf58-426">Om du vill avbryta den här ombaseringen väljer du version **1.1.1** av formatet **BACS (kund från Storbritannien)** på snabbfliken **Versioner** och välj sedan **Hämta denna version**.</span><span class="sxs-lookup"><span data-stu-id="7bf58-426">To cancel this rebase, select version **1.1.1** of the **BACS (UK custom)** format on the **Versions** FastTab, and then select **Get this version**.</span></span> <span data-ttu-id="7bf58-427">Version 3.3.2 kommer då att numreras om till och med innehållet i version 1.1.1 kommer innehållet i utkast version 1.1.2 att matchas.</span><span class="sxs-lookup"><span data-stu-id="7bf58-427">Version 3.3.2 will then be renumbered 1.1.2, and the content of draft version 1.1.2 will match the content of version 1.1.1.</span></span>

### <a name="process-a-vendor-payment-by-using-a-rebased-er-format"></a><a id="ProcessPayment3"></a><span data-ttu-id="7bf58-428">Bearbeta en leverantörsbetalning med hjälp av ombaserat ER-format</span><span class="sxs-lookup"><span data-stu-id="7bf58-428">Process a vendor payment by using a rebased ER format</span></span>

1. <span data-ttu-id="7bf58-429">Gå till **Leverantörsreskontra** \> **Betalningar** \> **Leverantörsbetalningsjournal**.</span><span class="sxs-lookup"><span data-stu-id="7bf58-429">Go to **Accounts payable** \> **Payments** \> **Vendor payment journal**.</span></span>
2. <span data-ttu-id="7bf58-430">På sidan **Leverantörsbetalningsjournal** väljer du den betalningsjournal som du skapade tidigare.</span><span class="sxs-lookup"><span data-stu-id="7bf58-430">On the **Vendor payment journal** page, select the payment journal that you created earlier.</span></span>
3. <span data-ttu-id="7bf58-431">Markera **rader**</span><span class="sxs-lookup"><span data-stu-id="7bf58-431">Select **Lines**.</span></span>
4. <span data-ttu-id="7bf58-432">På sidan **leverantörsbetalningar** ovanför rutnätet väljer du **betalningsstatus** \> **ingen**.</span><span class="sxs-lookup"><span data-stu-id="7bf58-432">On the **Vendor payments** page, above the grid, select **Payment status** \> **None**.</span></span>
5. <span data-ttu-id="7bf58-433">Välj **Generera betalning**.</span><span class="sxs-lookup"><span data-stu-id="7bf58-433">Select **Generate payment**.</span></span>
6. <span data-ttu-id="7bf58-434">Ange följande information i dialogrutan **Generera betalningar**:</span><span class="sxs-lookup"><span data-stu-id="7bf58-434">In the **Generate payments** dialog box, enter the following information:</span></span>

    - <span data-ttu-id="7bf58-435">I fältet **Betalningsmetod** väljer du **Elektronisk**.</span><span class="sxs-lookup"><span data-stu-id="7bf58-435">In the **Method of payment** field, select **Electronic**.</span></span>
    - <span data-ttu-id="7bf58-436">I fältet **Bankkonto** väljer du **GBSI OPER**.</span><span class="sxs-lookup"><span data-stu-id="7bf58-436">In the **Bank account** field, select **GBSI OPER**.</span></span>

7. <span data-ttu-id="7bf58-437">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="7bf58-437">Select **OK**.</span></span>
8. <span data-ttu-id="7bf58-438">I dialogrutan **Elektroniska rapportparametrar** ange följande information:</span><span class="sxs-lookup"><span data-stu-id="7bf58-438">In the **Electronic report parameters** dialog box, enter the following information:</span></span>

    - <span data-ttu-id="7bf58-439">Ange alternativet **Skriv ut kontrollrapport** till **Ja**.</span><span class="sxs-lookup"><span data-stu-id="7bf58-439">Set the **Print control report** option to **Yes**.</span></span>
    - <span data-ttu-id="7bf58-440">Ange alternativet **Skriv ut betalningsavi** till **Ja**.</span><span class="sxs-lookup"><span data-stu-id="7bf58-440">Set the **Print payment advice** option to **Yes**.</span></span>

    ![Dialogrutan Elektroniska rapportparametrar](./media/er-quick-start2-payment-dialog2.png)

    > [!NOTE]
    > <span data-ttu-id="7bf58-442">Förutom betalningsfilen kan du nu generera både kontrollrapporten och betalningsavirapporten.</span><span class="sxs-lookup"><span data-stu-id="7bf58-442">In addition to the payment file, you can now generate both the control report and the payment advice report.</span></span>

9. <span data-ttu-id="7bf58-443">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="7bf58-443">Select **OK**.</span></span>
10. <span data-ttu-id="7bf58-444">Hämta zip-filen och extrahera följande filer från den:</span><span class="sxs-lookup"><span data-stu-id="7bf58-444">Download the zip file, and then extract the following files from it:</span></span>

    - <span data-ttu-id="7bf58-445">Kontrollrapporten i Excel-format</span><span class="sxs-lookup"><span data-stu-id="7bf58-445">The control report in Excel format</span></span>
    - <span data-ttu-id="7bf58-446">Betalningsavirapporten i Excel-format</span><span class="sxs-lookup"><span data-stu-id="7bf58-446">The payment advice report in Excel format</span></span>

        ![Betalningsavirapporten i Excel-format](./media/er-quick-start2-payment-advice-report.png)

    - <span data-ttu-id="7bf58-448">Betalningsfil i TXT-format</span><span class="sxs-lookup"><span data-stu-id="7bf58-448">The payment file in TXT format</span></span>

        <span data-ttu-id="7bf58-449">Lägg märke till att betalningsraden i den genererade filen börjar med SWIFT-koden som anges för bankkontot för en leverantör vars betalning har behandlats.</span><span class="sxs-lookup"><span data-stu-id="7bf58-449">Notice that the payment line in the generated file starts  with the SWIFT code that was entered for the bank account of a vendor whose payment has been processed.</span></span>

        ![Betalningsfil i TXT-format](./media/er-quick-start2-payment-file3.png)

## <a name="additional-resources"></a><a id="References"></a><span data-ttu-id="7bf58-451">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="7bf58-451">Additional resources</span></span>

- [<span data-ttu-id="7bf58-452">Översikt över elektronisk rapportering</span><span class="sxs-lookup"><span data-stu-id="7bf58-452">Electronic Reporting overview</span></span>](general-electronic-reporting.md)
- [<span data-ttu-id="7bf58-453">Ladda ned ER-konfigurationer från Lifecycle Services</span><span class="sxs-lookup"><span data-stu-id="7bf58-453">Download ER configurations from Lifecycle Services</span></span>](download-electronic-reporting-configuration-lcs.md)
- [<span data-ttu-id="7bf58-454">Hämta ER-konfigurationer från den globala databasen med konfigurationstjänster</span><span class="sxs-lookup"><span data-stu-id="7bf58-454">Download ER configurations from Global repository of Configuration service</span></span>](er-download-configurations-global-repo.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]