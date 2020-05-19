---
title: Allmän felsökning
description: Det här avsnittet innehåller allmän felsökningsinformation för integrering av dubbelriktad skrivning mellan Finance and Operations-appar och Common Data Service.
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
ms.openlocfilehash: 8cc7c11233c745719af72222eba02fb71d7a8944
ms.sourcegitcommit: 4edc658448612afbf1c1663c166d12e08e4c4165
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/06/2020
ms.locfileid: "3340940"
---
# <a name="general-troubleshooting"></a><span data-ttu-id="e2d4b-103">Allmän felsökning</span><span class="sxs-lookup"><span data-stu-id="e2d4b-103">General troubleshooting</span></span>

[!include [banner](../../includes/banner.md)]



<span data-ttu-id="e2d4b-104">Det här avsnittet innehåller allmän felsökningsinformation för integrering av dubbelriktad skrivning mellan Finance and Operations-appar och Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="e2d4b-104">This topic provides general troubleshooting information for dual-write integration between Finance and Operations apps and Common Data Service.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e2d4b-105">Vissa av de problem som det här ämnet behandlar kan kräva antingen systemadministratörsrollen eller Microsoft Azure Active Directory (Azure AD) autentiseringsuppgifter för administratör för klientorganisationen.</span><span class="sxs-lookup"><span data-stu-id="e2d4b-105">Some of the issues that this topic addresses might require either the system admin role or Microsoft Azure Active Directory (Azure AD) tenant admin credentials.</span></span> <span data-ttu-id="e2d4b-106">I avsnittet för varje problem förklaras om en viss roll eller autentiseringsuppgifter krävs.</span><span class="sxs-lookup"><span data-stu-id="e2d4b-106">The section for each issue explains whether a specific role or credentials are required.</span></span>

## <a name="when-you-try-to-install-the-dual-write-package-by-using-the-package-deployer-tool-no-available-solutions-are-shown"></a><span data-ttu-id="e2d4b-107">När du försöker installera paketet för dubbelriktad skrivning visas med hjälp av verktyget package deployer inga tillgängliga lösningar</span><span class="sxs-lookup"><span data-stu-id="e2d4b-107">When you try to install the dual-write package by using the package deployer tool, no available solutions are shown</span></span>

<span data-ttu-id="e2d4b-108">Vissa versioner av verktyget package deployer är inte kompatibla med lösningspaketet för dubbelriktad skrivning.</span><span class="sxs-lookup"><span data-stu-id="e2d4b-108">Some versions of the package deployer tool are incompatible with the dual-write solution package.</span></span> <span data-ttu-id="e2d4b-109">Om du vill installera paketet måste du först använda [version 9.1.0.20](https://www.nuget.org/packages/Microsoft.CrmSdk.XrmTooling.PackageDeployment.Wpf/9.1.0.20) eller senare av verktyget package deployer.</span><span class="sxs-lookup"><span data-stu-id="e2d4b-109">To successfully install the package, be sure to use [version 9.1.0.20](https://www.nuget.org/packages/Microsoft.CrmSdk.XrmTooling.PackageDeployment.Wpf/9.1.0.20) or later of the package deployer tool.</span></span>

<span data-ttu-id="e2d4b-110">När du har installerat verktyget package deployer installerar du lösningspaketet genom att följa stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="e2d4b-110">After you install the package deployer tool, install the solution package by following these steps.</span></span>

1. <span data-ttu-id="e2d4b-111">Hämta den senaste lösningspaketfilen från Yammer. com.</span><span class="sxs-lookup"><span data-stu-id="e2d4b-111">Download the latest solution package file from Yammer.com.</span></span> <span data-ttu-id="e2d4b-112">När paketets zip-fil har hämtats högerklickar du på den och väljer **egenskaper**.</span><span class="sxs-lookup"><span data-stu-id="e2d4b-112">After the package zip file is downloaded, right-click it, and select **Properties**.</span></span> <span data-ttu-id="e2d4b-113">Markera kryssrutan **Avblockera** och välj sedan **Använd**.</span><span class="sxs-lookup"><span data-stu-id="e2d4b-113">Select the **Unblock** check box, and then select **Apply**.</span></span> <span data-ttu-id="e2d4b-114">Om du inte ser kryssrutan **Avblockera** är zip-filen redan avblockerad och du kan hoppa över det här steget.</span><span class="sxs-lookup"><span data-stu-id="e2d4b-114">If you don't see the **Unblock** check box, the zip file is already unblocked, and you can skip this step.</span></span>

    ![Dialogrutan egenskaper](media/unblock_option.png)

2. <span data-ttu-id="e2d4b-116">Extrahera paketets zip-fil och kopiera alla filer i mappen **Dynamics365FinanceAndOperationsCommon.PackageDeployer.2.0.43**.</span><span class="sxs-lookup"><span data-stu-id="e2d4b-116">Extract the package zip file, and copy all the files in the **Dynamics365FinanceAndOperationsCommon.PackageDeployer.2.0.438** folder.</span></span>

    ![Innehåll i mappen Dynamics365FinanceAndOperationsCommon.PackageDeployer.2.0.438](media/extract_package.png)

3. <span data-ttu-id="e2d4b-118">Klistra in alla kopierade filer i mappen **Verktyg** i verktyget package deployer.</span><span class="sxs-lookup"><span data-stu-id="e2d4b-118">Paste all the copied files into the **Tools** folder of the package deployer tool.</span></span> 
4. <span data-ttu-id="e2d4b-119">Kör **PackageDeployer. exe** för att välja Common Data Service-miljön och installera lösningarna.</span><span class="sxs-lookup"><span data-stu-id="e2d4b-119">Run **PackageDeployer.exe** to select the Common Data Service environment and install the solutions.</span></span>

    ![Innehåll i mappen verktyg](media/paste_copied_files.png)

## <a name="enable-and-view-the-plug-in-trace-log-in-common-data-service-to-view-error-details"></a><span data-ttu-id="e2d4b-121">Aktivera och visa spårningslogg för plugin-program i Common Data Service för att visa felinformation</span><span class="sxs-lookup"><span data-stu-id="e2d4b-121">Enable and view the plug-in trace log in Common Data Service to view error details</span></span>

<span data-ttu-id="e2d4b-122">**Nödvändig roll för att aktivera spårningsloggen och visa fel:** systemadministratör</span><span class="sxs-lookup"><span data-stu-id="e2d4b-122">**Required role to turn on the trace log and view errors:** System admin</span></span>

<span data-ttu-id="e2d4b-123">Så här aktiverar du spårningslogg.</span><span class="sxs-lookup"><span data-stu-id="e2d4b-123">To turn on the trace log, follow these steps.</span></span>

1. <span data-ttu-id="e2d4b-124">Logga in på den modelldrivna appen i Dynamics 365, öppna sidan **Inställningar** och under **System**, välj **Administration**.</span><span class="sxs-lookup"><span data-stu-id="e2d4b-124">Sign in to the model-driven app in Dynamics 365, open the **Settings** page, and then, under **System**, select **Administration**.</span></span>
2. <span data-ttu-id="e2d4b-125">På sidan **Administration** väljer du **Systeminställningar**.</span><span class="sxs-lookup"><span data-stu-id="e2d4b-125">On the **Administration** page, select **System Settings**.</span></span>
3. <span data-ttu-id="e2d4b-126">På fliken **Anpassning** i fältet **Plugin-program and aktivitetsspåring för anpassat arbetsflöde**, välj **Alla** för att aktivera spårningsloggen för plugin-program.</span><span class="sxs-lookup"><span data-stu-id="e2d4b-126">On the **Customization** tab, in the **Plug-in and custom workflow activity tracing** field, select **All** to enable the plug-in trace log.</span></span> <span data-ttu-id="e2d4b-127">Om du bara vill logga spårningsloggar när undantag inträffar kan du istället välja **undantag**.</span><span class="sxs-lookup"><span data-stu-id="e2d4b-127">If you want to log trace logs only when exceptions occur, you can select **Exception** instead.</span></span>


<span data-ttu-id="e2d4b-128">Så här visar du spårningslogg.</span><span class="sxs-lookup"><span data-stu-id="e2d4b-128">To view the trace log, follow these steps.</span></span>

1. <span data-ttu-id="e2d4b-129">Logga in på den modelldrivna appen i Dynamics 365, öppna sidan **Inställningar** och under **Anpassning**, välj **Spårningslogg för plugin-program**.</span><span class="sxs-lookup"><span data-stu-id="e2d4b-129">Sign in to the model-driven app in Dynamics 365, open the **Settings** page, and then, under **Customization**, select **Plug-in Trace Log**.</span></span>
2. <span data-ttu-id="e2d4b-130">Sök efter spårningsloggarna där fältet **Typnamn** anges till **Microsoft.Dynamics.Integrator.DualWriteRuntime.Plugins.PreCommmitPlugin**.</span><span class="sxs-lookup"><span data-stu-id="e2d4b-130">Find the trace logs where the **Type Name** field is set to **Microsoft.Dynamics.Integrator.DualWriteRuntime.Plugins.PreCommmitPlugin**.</span></span>
3. <span data-ttu-id="e2d4b-131">Dubbelklicka på ett objekt om du vill visa hela loggen och på snabbfliken **Körning**, granska texten **Meddelandeblock**.</span><span class="sxs-lookup"><span data-stu-id="e2d4b-131">Double-click an item to view the full log, and then, on the **Execution** FastTab, review the **Message Block** text.</span></span>

## <a name="enable-debug-mode-to-troubleshoot-live-synchronization-issues-in-finance-and-operations-apps"></a><span data-ttu-id="e2d4b-132">Aktivera felsökningsläget för att felsöka problem med direkt synkronisering i Finance and Operations-appar</span><span class="sxs-lookup"><span data-stu-id="e2d4b-132">Enable debug mode to troubleshoot live synchronization issues in Finance and Operations apps</span></span>

<span data-ttu-id="e2d4b-133">**Den roll som krävs för att visa felet:** systemadministratören Fel i dubbelriktad skrivning som har sitt ursprung i Common Data Service kan visas i Finance and Operations-appen.</span><span class="sxs-lookup"><span data-stu-id="e2d4b-133">**Required role to view the errors:** System admin Dual-write errors that originate in Common Data Service can appear in the Finance and Operations app.</span></span> <span data-ttu-id="e2d4b-134">I vissa fall är den fullständiga texten i felmeddelandet inte tillgänglig eftersom meddelandet är för långt eller innehåller personligt identifierande information (PII).</span><span class="sxs-lookup"><span data-stu-id="e2d4b-134">In some cases, the full text of the error message isn't available because the message is too long or contains personally identifying information (PII).</span></span> <span data-ttu-id="e2d4b-135">Du kan aktivera detaljerad loggning för fel genom att följa stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="e2d4b-135">You can turn on verbose logging for errors by following these steps.</span></span>

1. <span data-ttu-id="e2d4b-136">Alla projektkonfigurationer i Finance and Operations-appar har en **IsDebugMode**-egenskap i entiteten **DualWriteProjectConfiguration**.</span><span class="sxs-lookup"><span data-stu-id="e2d4b-136">All project configurations in Finance and Operations apps have an **IsDebugMode** property in the **DualWriteProjectConfiguration** entity.</span></span> <span data-ttu-id="e2d4b-137">Öppna entiteten **DualWriteProjectConfiguration** genom att använda Excel-tillägget.</span><span class="sxs-lookup"><span data-stu-id="e2d4b-137">Open the **DualWriteProjectConfiguration** entity by using the Excel add-in.</span></span>

    > [!TIP]
    > <span data-ttu-id="e2d4b-138">Ett enkelt sätt att öppna entiteten är att aktivera **design**-läget i Excel-tillägget och sedan lägga till **DualWriteProjectConfigurationEntity** i kalkylbladet.</span><span class="sxs-lookup"><span data-stu-id="e2d4b-138">An easy way to open the entity is to turn on **Design** mode in the Excel add-in and then add **DualWriteProjectConfigurationEntity** to the worksheet.</span></span> <span data-ttu-id="e2d4b-139">För mer information, se [Öppna entitetsdata i Excel och uppdatera den med hjälp av Excel-tillägget](../../office-integration/use-excel-add-in.md).</span><span class="sxs-lookup"><span data-stu-id="e2d4b-139">For more information, see [Open entity data in Excel and update it by using the Excel add-in](../../office-integration/use-excel-add-in.md).</span></span>

2. <span data-ttu-id="e2d4b-140">Ställ in egenskapen **IsDebugMode** på **ja** för projektet.</span><span class="sxs-lookup"><span data-stu-id="e2d4b-140">Set the **IsDebugMode** property to **Yes** for the project.</span></span>
3. <span data-ttu-id="e2d4b-141">Kör scenariot som genererar fel.</span><span class="sxs-lookup"><span data-stu-id="e2d4b-141">Run the scenario that is generating errors.</span></span>
4. <span data-ttu-id="e2d4b-142">De detaljerade loggarna finns i registret DualWriteErrorLog.</span><span class="sxs-lookup"><span data-stu-id="e2d4b-142">The verbose logs are available in the DualWriteErrorLog table.</span></span> <span data-ttu-id="e2d4b-143">Om du vill söka efter data i en registerläsare använder du följande URL (ersätt **XXX** efter behov):</span><span class="sxs-lookup"><span data-stu-id="e2d4b-143">To look up data in the table browser, use the following URL (replace **XXX** as appropriate):</span></span>

    `https://XXXaos.cloudax.dynamics.com/?mi=SysTableBrowser&tableName=>DualWriteErrorLog`

## <a name="check-synchronization-errors-on-the-virtual-machine-for-the-finance-and-operations-app"></a><span data-ttu-id="e2d4b-144">Kontrollera synkroniseringsfel på den virtuella datorn för Finance and Operations-appen</span><span class="sxs-lookup"><span data-stu-id="e2d4b-144">Check synchronization errors on the virtual machine for the Finance and Operations app</span></span>

<span data-ttu-id="e2d4b-145">**Den roll som krävs för att visa felen:** systemadministratör</span><span class="sxs-lookup"><span data-stu-id="e2d4b-145">**Required role to view the errors:** System administrator</span></span>

1. <span data-ttu-id="e2d4b-146">Logga in på Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="e2d4b-146">Sign in to Microsoft Dynamics Lifecycle Services (LCS).</span></span>
2. <span data-ttu-id="e2d4b-147">Öppna LCS-projektet som du valde att utföra testning av dubbelriktad skrivning för.</span><span class="sxs-lookup"><span data-stu-id="e2d4b-147">Open the LCS project that you chose to do the dual-write testing for.</span></span>
3. <span data-ttu-id="e2d4b-148">Välj panelen **Molnstyrda miljöer**.</span><span class="sxs-lookup"><span data-stu-id="e2d4b-148">Select the **Cloud-hosted environments** tile.</span></span>
4. <span data-ttu-id="e2d4b-149">Logga in på den virtuella datorn (VM) för Finance and Operations-appen med hjälp av fjärrskrivbord.</span><span class="sxs-lookup"><span data-stu-id="e2d4b-149">Use Remote Desktop to sign in to the virtual machine (VM) for the Finance and Operations app.</span></span> <span data-ttu-id="e2d4b-150">Använd det lokala kontot som visas i LCS.</span><span class="sxs-lookup"><span data-stu-id="e2d4b-150">Use the local account that is shown in LCS.</span></span>
5. <span data-ttu-id="e2d4b-151">Öppna händelsevisningsprogrammet.</span><span class="sxs-lookup"><span data-stu-id="e2d4b-151">Open Event viewer.</span></span>
6. <span data-ttu-id="e2d4b-152">Välj **Program- och tjänstloggar \> Microsoft \> Dynamics \> AX-DualWriteSync \> Drift**.</span><span class="sxs-lookup"><span data-stu-id="e2d4b-152">Select **Applications and Services Logs \> Microsoft \> Dynamics \> AX-DualWriteSync \> Operational**.</span></span>
7. <span data-ttu-id="e2d4b-153">Granska listan över de senaste felen.</span><span class="sxs-lookup"><span data-stu-id="e2d4b-153">Review the list of recent errors.</span></span>

## <a name="unlink-and-link-another-common-data-service-environment-from-a-finance-and-operations-app"></a><span data-ttu-id="e2d4b-154">Ta bort länken och länka en annan Common Data Service-miljö från en Finance and Operations-app</span><span class="sxs-lookup"><span data-stu-id="e2d4b-154">Unlink and link another Common Data Service environment from a Finance and Operations app</span></span>

<span data-ttu-id="e2d4b-155">**Nödvändiga autentiseringsuppgifter för ta bort länken till miljö**: systemadministratör för antingen Finance and Operations-appen eller Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="e2d4b-155">**Required role to unlink the environment:** System administrator for either Finance and Operations app or Common Data Service.</span></span>

1. <span data-ttu-id="e2d4b-156">Logga in på Finance and Operations-appen.</span><span class="sxs-lookup"><span data-stu-id="e2d4b-156">Sign in to the Finance and Operations app.</span></span>
2. <span data-ttu-id="e2d4b-157">Gå till **Arbetsytor \> Datahantering** och välj panelen **Dubbelriktad skrivning**.</span><span class="sxs-lookup"><span data-stu-id="e2d4b-157">Go to **Workspaces \> Data management**, and select the **Dual Write** tile.</span></span>
3. <span data-ttu-id="e2d4b-158">Markera alla mappningar och sedan **stoppa**.</span><span class="sxs-lookup"><span data-stu-id="e2d4b-158">Select all running mappings, and then select **Stop**.</span></span>
4. <span data-ttu-id="e2d4b-159">Välj **Ta bort länk till miljö**.</span><span class="sxs-lookup"><span data-stu-id="e2d4b-159">Select **Unlink environment**.</span></span>
5. <span data-ttu-id="e2d4b-160">Välj **Ja** för att bekräfta åtgärden.</span><span class="sxs-lookup"><span data-stu-id="e2d4b-160">Select **Yes** to confirm the operation.</span></span>

<span data-ttu-id="e2d4b-161">Nu kan du länka en ny miljö.</span><span class="sxs-lookup"><span data-stu-id="e2d4b-161">You can now link a new environment.</span></span>

## <a name="unable-to-view-the-sales-order-line-information-form"></a><span data-ttu-id="e2d4b-162">Det går inte att visa formuläret information om försäljningsorderrad</span><span class="sxs-lookup"><span data-stu-id="e2d4b-162">Unable to view the sales order line Information form</span></span> 

<span data-ttu-id="e2d4b-163">När du skapar en försäljningsorder i Dynamics 365 Sales kan du om du klickar på **+ Lägg till produkter** omdirigeras till formuläret för orderrad Dynamics 365 projektåtgärder.</span><span class="sxs-lookup"><span data-stu-id="e2d4b-163">When you create a sales order in Dynamics 365 Sales, clicking on **+ Add products** might redirect you to the Dynamics 365 Project Operations order line form.</span></span> <span data-ttu-id="e2d4b-164">Från det formuläret finns det inget sätt att visa formuläret för försäljningsorderrad **Information**.</span><span class="sxs-lookup"><span data-stu-id="e2d4b-164">There is no way from that form to view the sales order line **Information** form.</span></span> <span data-ttu-id="e2d4b-165">Alternativet för **information** visas inte i listrutan under **Ny orderrad**.</span><span class="sxs-lookup"><span data-stu-id="e2d4b-165">The option for **Information** does not appear in the dropdown below **New Order Line**.</span></span> <span data-ttu-id="e2d4b-166">Detta inträffar eftersom projektåtgärder har installerats i din miljö.</span><span class="sxs-lookup"><span data-stu-id="e2d4b-166">This happens because Project Operations has been installed in your environment.</span></span>

<span data-ttu-id="e2d4b-167">Så här aktiverar du alternativet för formuläret **informations** igen:</span><span class="sxs-lookup"><span data-stu-id="e2d4b-167">To re-enable the **Information** form option, follow these steps:</span></span>
1. <span data-ttu-id="e2d4b-168">Navigera till entiteten **orderrad**.</span><span class="sxs-lookup"><span data-stu-id="e2d4b-168">Navigate to the **Order Line** entity.</span></span>
2. <span data-ttu-id="e2d4b-169">Hitta formuläret **Information** under formulärnoden.</span><span class="sxs-lookup"><span data-stu-id="e2d4b-169">Find the **Information** form under the forms node.</span></span> 
3. <span data-ttu-id="e2d4b-170">Markera formuläret **Information** och klicka på **aktivera säkerhetsroller**.</span><span class="sxs-lookup"><span data-stu-id="e2d4b-170">Select the **Information** form and click **Enable security roles**.</span></span> 
4. <span data-ttu-id="e2d4b-171">Ändra säkerhetsinställningarna till **Visa för alla**.</span><span class="sxs-lookup"><span data-stu-id="e2d4b-171">Change the security setting to **Display to everyone**.</span></span>
