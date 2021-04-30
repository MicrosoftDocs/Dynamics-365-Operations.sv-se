---
title: Kopiera en instans
description: Du kan använda Microsoft Dynamics Lifecycle Services (LCS) för att kopiera en Microsoft Dynamics 365 Human Resources-databas till en miljö i begränsat läge.
author: andreabichsel
ms.date: 07/22/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SystemAdministrationWorkspaceForm
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 44df05083cd3c91e5dcbdb3062665c2145d92a7e
ms.sourcegitcommit: 951393b05bf409333cb3c7ad977bcaa804aa801b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/13/2021
ms.locfileid: "5889822"
---
# <a name="copy-an-instance"></a><span data-ttu-id="d4c2e-103">Kopiera en instans</span><span class="sxs-lookup"><span data-stu-id="d4c2e-103">Copy an instance</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="d4c2e-104">Du kan använda Microsoft Dynamics Lifecycle Services (LCS) för att kopiera en Microsoft Dynamics 365 Human Resources-databas till en miljö i begränsat läge.</span><span class="sxs-lookup"><span data-stu-id="d4c2e-104">You can use Microsoft Dynamics Lifecycle Services (LCS) to copy a Microsoft Dynamics 365 Human Resources database to a sandbox environment.</span></span> <span data-ttu-id="d4c2e-105">Om du har en annan miljö med begränsat läge kan du även kopiera databasen från den miljön till en miljö med begränsat läge.</span><span class="sxs-lookup"><span data-stu-id="d4c2e-105">If you have another sandbox environment, you can also copy the database from that environment to a targeted sandbox environment.</span></span>

<span data-ttu-id="d4c2e-106">Om du vill kopiera en instans bör du tänka på följande:</span><span class="sxs-lookup"><span data-stu-id="d4c2e-106">To copy an instance, keep the following tips in mind:</span></span>

- <span data-ttu-id="d4c2e-107">Den personalinstans som du vill skriva över måste vara en miljö i begränsat läge.</span><span class="sxs-lookup"><span data-stu-id="d4c2e-107">The Human Resources instance you want to overwrite must be a sandbox environment.</span></span>

- <span data-ttu-id="d4c2e-108">De miljöer som du kopierar från och till måste finnas i samma region.</span><span class="sxs-lookup"><span data-stu-id="d4c2e-108">The environments you're copying from and to must be in the same region.</span></span> <span data-ttu-id="d4c2e-109">Du kan inte kopiera mellan regioner.</span><span class="sxs-lookup"><span data-stu-id="d4c2e-109">You can't copy across regions.</span></span>

- <span data-ttu-id="d4c2e-110">Du måste vara administratör i målmiljön för att du ska kunna logga in på den efter att du har kopierat instansen.</span><span class="sxs-lookup"><span data-stu-id="d4c2e-110">You must be an Administrator in the target environment so you can sign into it after copying the instance.</span></span>

- <span data-ttu-id="d4c2e-111">När du kopierar databasen för Personal kopierar du inte de element (appar eller data) som finns i en Microsoft Power Apps-miljö.</span><span class="sxs-lookup"><span data-stu-id="d4c2e-111">When you copy the Human Resources database, you don't copy the elements (apps or data) that are contained in a Microsoft Power Apps environment.</span></span> <span data-ttu-id="d4c2e-112">Information om hur du kopierar element i en Power Apps-miljö finns i [kopiera en miljö](/power-platform/admin/copy-environment).</span><span class="sxs-lookup"><span data-stu-id="d4c2e-112">For information about how to copy elements in a Power Apps environment, see [Copy an environment](/power-platform/admin/copy-environment).</span></span> <span data-ttu-id="d4c2e-113">Den Power Apps-miljö som du vill skriva över måste vara en miljö i begränsat läge.</span><span class="sxs-lookup"><span data-stu-id="d4c2e-113">The Power Apps environment you want to overwrite must be a sandbox environment.</span></span> <span data-ttu-id="d4c2e-114">Du måste vara global innehavaradministratör om du vill ändra en Power Apps-produktionsmiljö till en miljö i begränsat läge.</span><span class="sxs-lookup"><span data-stu-id="d4c2e-114">You must be a global tenant admin to change a Power Apps production environment to a sandbox environment.</span></span> <span data-ttu-id="d4c2e-115">Mer information om hur du ändrar Power Apps-miljö finns i [Växla en instans](/dynamics365/admin/switch-instance).</span><span class="sxs-lookup"><span data-stu-id="d4c2e-115">For more information about changing a Power Apps environment, see [Switch an instance](/dynamics365/admin/switch-instance).</span></span>

- <span data-ttu-id="d4c2e-116">Om du kopierar en instans till sandbox-miljön och vill integrera sandbox-miljön med Dataverse, måste du återställa anpassade fält till Dataverse-register.</span><span class="sxs-lookup"><span data-stu-id="d4c2e-116">If you copy an instance into your sandbox environment and want to integrate your sandbox environment with Dataverse, you must reapply custom fields to Dataverse tables.</span></span> <span data-ttu-id="d4c2e-117">Se [tillämpa anpassade fält på Dataverse](hr-admin-setup-copy-instance.md?apply-custom-fields-to-common-data-service).</span><span class="sxs-lookup"><span data-stu-id="d4c2e-117">See [Apply custom fields to Dataverse](hr-admin-setup-copy-instance.md?apply-custom-fields-to-common-data-service).</span></span>

## <a name="effects-of-copying-a-human-resources-database"></a><span data-ttu-id="d4c2e-118">Effekter av att kopiera personaldatabasen</span><span class="sxs-lookup"><span data-stu-id="d4c2e-118">Effects of copying a Human Resources database</span></span>

<span data-ttu-id="d4c2e-119">Följande händelser inträffar när du kopierar en personaldatabas:</span><span class="sxs-lookup"><span data-stu-id="d4c2e-119">The following events occur when you copy a Human Resources database:</span></span>

- <span data-ttu-id="d4c2e-120">När du kopierar processen raderas den befintliga databasen i målmiljön.</span><span class="sxs-lookup"><span data-stu-id="d4c2e-120">The copy process erases the existing database in the target environment.</span></span> <span data-ttu-id="d4c2e-121">När kopieringsprocessen är klar kan du inte återställa den befintliga databasen.</span><span class="sxs-lookup"><span data-stu-id="d4c2e-121">After the copy process is completed, you can't recover the existing database.</span></span>

- <span data-ttu-id="d4c2e-122">Målmiljön kommer inte att vara tillgänglig förrän kopieringsprocessen har slutförts.</span><span class="sxs-lookup"><span data-stu-id="d4c2e-122">The target environment will be unavailable until the copy process is completed.</span></span>

- <span data-ttu-id="d4c2e-123">Dokument i Microsoft Azure Blob-lagring kopieras inte från en miljö till en annan.</span><span class="sxs-lookup"><span data-stu-id="d4c2e-123">Documents in Microsoft Azure Blob storage aren't copied from one environment to another.</span></span> <span data-ttu-id="d4c2e-124">Därför kopieras inte de kopplade dokumenten och mallarna och de blir kvar i källmiljön.</span><span class="sxs-lookup"><span data-stu-id="d4c2e-124">As a result, any documents and templates that are attached won't be copied and will remain in the source environment.</span></span>

- <span data-ttu-id="d4c2e-125">Alla användare förutom administratören och andra interna användarkonton kommer inte att vara tillgängliga.​</span><span class="sxs-lookup"><span data-stu-id="d4c2e-125">All users except the Admin user and other internal service user accounts will be unavailable.</span></span> <span data-ttu-id="d4c2e-126">Administratörsanvändaren kan ta bort eller dölja data innan andra användare tillåts tillbaka till systemet.</span><span class="sxs-lookup"><span data-stu-id="d4c2e-126">The Admin user can delete or obfuscate data before other users are allowed back into the system.</span></span>

- <span data-ttu-id="d4c2e-127">Administratörsanvändaren måste göra obligatoriska konfigurationsändringar, t.ex. återansluta integreringsslutpunkter för specifika tjänster eller URL:er.</span><span class="sxs-lookup"><span data-stu-id="d4c2e-127">The Admin user must make required configuration changes, such as reconnecting integration endpoints to specific services or URLs.</span></span>

## <a name="copy-the-human-resources-database"></a><span data-ttu-id="d4c2e-128">Kopiera databasen för personal</span><span class="sxs-lookup"><span data-stu-id="d4c2e-128">Copy the Human Resources database</span></span>

<span data-ttu-id="d4c2e-129">Om du vill slutföra den här uppgiften kopierar du först en instans och loggar sedan in på Microsoft Power Platform administrationscenter för att kopiera Power Apps-miljön.</span><span class="sxs-lookup"><span data-stu-id="d4c2e-129">To complete this task, you first copy an instance, and then sign in to the Microsoft Power Platform Admin Center to copy your Power Apps environment.</span></span>

> [!WARNING]
> <span data-ttu-id="d4c2e-130">När du kopierar en instans raderas databasen i målinstansen.</span><span class="sxs-lookup"><span data-stu-id="d4c2e-130">When you copy an instance, the database is erased in the target instance.</span></span> <span data-ttu-id="d4c2e-131">Målinstansen är inte tillgänglig under denna process.</span><span class="sxs-lookup"><span data-stu-id="d4c2e-131">The target instance is unavailable during this process.</span></span>

1. <span data-ttu-id="d4c2e-132">Logga in på LCS och välj det LCS-projekt som innehåller den instans som du vill kopiera.</span><span class="sxs-lookup"><span data-stu-id="d4c2e-132">Sign in to LCS, and select the LCS project that contains the instance that you want to copy.</span></span>

2. <span data-ttu-id="d4c2e-133">I LCS-projektet väljer du fliken **-hantering for Personal**.</span><span class="sxs-lookup"><span data-stu-id="d4c2e-133">In your LCS project, select the **Human Resources App Management** tile.</span></span>

3. <span data-ttu-id="d4c2e-134">Markera den instans du vill kopiera och välj sedan **kopiera**.</span><span class="sxs-lookup"><span data-stu-id="d4c2e-134">Select the instance to copy, and then select **Copy**.</span></span>

4. <span data-ttu-id="d4c2e-135">I åtgärdsfönstret **Kopiera en instans** välj instansen som ska skrivas över och välj sedan **Kopiera**.</span><span class="sxs-lookup"><span data-stu-id="d4c2e-135">In the **Copy an instance** task pane, select the instance to overwrite, and then select **Copy**.</span></span> <span data-ttu-id="d4c2e-136">Vänta tills värdet på fältet **Kopieringsstatus** uppdateras till **Slutförd**.</span><span class="sxs-lookup"><span data-stu-id="d4c2e-136">Wait for the value of the **Copy status** field to be updated to **Completed**.</span></span>

   ![[<span data-ttu-id="d4c2e-137">Välj instans som ska skrivas över</span><span class="sxs-lookup"><span data-stu-id="d4c2e-137">Select instance to overwrite</span></span>](./media/copy-instance-select-target-instance.png)](./media/copy-instance-select-target-instance.png)

5. <span data-ttu-id="d4c2e-138">Välj **Power Platform** och logga in på administrationscenter för Microsoft Power Platform.</span><span class="sxs-lookup"><span data-stu-id="d4c2e-138">Select **Power Platform**, and sign in to the Microsoft Power Platform Admin Center.</span></span>

   ![[<span data-ttu-id="d4c2e-139">Välj Power Platform</span><span class="sxs-lookup"><span data-stu-id="d4c2e-139">Select Power Platform</span></span>](./media/copy-instance-select-power-platform.png)](./media/copy-instance-select-power-platform.png)

6. <span data-ttu-id="d4c2e-140">Markera den Power Apps-miljö du vill kopiera och välj sedan **kopiera**.</span><span class="sxs-lookup"><span data-stu-id="d4c2e-140">Select the Power Apps environment to copy, and then select **Copy**.</span></span>

7. <span data-ttu-id="d4c2e-141">När kopieringsprocessen har slutförts loggar du in på målinstansen och aktiverar Dataverse-integreringen.</span><span class="sxs-lookup"><span data-stu-id="d4c2e-141">When the copy process is completed, sign in to the target instance, and enable Dataverse integration.</span></span> <span data-ttu-id="d4c2e-142">Mer information och anvisningar finns i [Konfigurera Dataverse-integration](./hr-admin-integration-common-data-service.md).</span><span class="sxs-lookup"><span data-stu-id="d4c2e-142">For more information and instructions, see [Configure Dataverse integration](./hr-admin-integration-common-data-service.md).</span></span>

## <a name="data-elements-and-statuses"></a><span data-ttu-id="d4c2e-143">Dataelement och status</span><span class="sxs-lookup"><span data-stu-id="d4c2e-143">Data elements and statuses</span></span>

<span data-ttu-id="d4c2e-144">Följande dataelement kopieras inte när du kopierar en personalinstans:</span><span class="sxs-lookup"><span data-stu-id="d4c2e-144">The following data elements aren't copied when you copy a Human Resources instance:</span></span>

- <span data-ttu-id="d4c2e-145">E-postadresser i **LogisticsElectronicAddress**-registret</span><span class="sxs-lookup"><span data-stu-id="d4c2e-145">Email addresses in the **LogisticsElectronicAddress** table</span></span>

- <span data-ttu-id="d4c2e-146">Historiken för batchjobb i tabellerna **BatchJobHistory**, **BatchHistory** och **BatchConstraintHistory**</span><span class="sxs-lookup"><span data-stu-id="d4c2e-146">The batch job history in the **BatchJobHistory**, **BatchHistory**, and **BatchConstraintHistory** tables</span></span>

- <span data-ttu-id="d4c2e-147">SMTP-lösenordet (Simple Mail Transfer Protocol) i **SysEmailSMTPPassword**-registret</span><span class="sxs-lookup"><span data-stu-id="d4c2e-147">The Simple Mail Transfer Protocol (SMTP) password in the **SysEmailSMTPPassword** table</span></span>

- <span data-ttu-id="d4c2e-148">SMTP-relayservern i **SysEmailParameters**-registret</span><span class="sxs-lookup"><span data-stu-id="d4c2e-148">The SMTP Relay server in the **SysEmailParameters** table</span></span>

- <span data-ttu-id="d4c2e-149">Utskriftshanteringsinställningar i registren **PrintMgmtSettings** och **PrintMgmtDocInstance**</span><span class="sxs-lookup"><span data-stu-id="d4c2e-149">Print Management settings in the **PrintMgmtSettings** and **PrintMgmtDocInstance** tables</span></span>

- <span data-ttu-id="d4c2e-150">Miljöspecifika poster i registren **SysServerConfig**, **SysServerSessions**, **SysCorpNetPrinters**, **SysClientSessions**, **BatchServerConfig** och **BatchServerGroup**</span><span class="sxs-lookup"><span data-stu-id="d4c2e-150">Environment-specific records in the **SysServerConfig**, **SysServerSessions**, **SysCorpNetPrinters**, **SysClientSessions**, **BatchServerConfig**, and **BatchServerGroup** tables</span></span>

- <span data-ttu-id="d4c2e-151">Dokumentbilagor i DocuValue-registret.</span><span class="sxs-lookup"><span data-stu-id="d4c2e-151">Document attachments in the DocuValue table.</span></span> <span data-ttu-id="d4c2e-152">Dessa bifogade filer innehåller alla Microsoft Office-mallar som har skrivits över i källmiljön</span><span class="sxs-lookup"><span data-stu-id="d4c2e-152">These attachments include any Microsoft Office templates that were overwritten in the source environment</span></span>

- <span data-ttu-id="d4c2e-153">Anslutningssträngen i registret **PersonnelIntegrationConfiguration**</span><span class="sxs-lookup"><span data-stu-id="d4c2e-153">The connection string in the **PersonnelIntegrationConfiguration** table</span></span>

<span data-ttu-id="d4c2e-154">Vissa av elementen kopieras inte eftersom de är miljöspecifika.</span><span class="sxs-lookup"><span data-stu-id="d4c2e-154">Some of these elements aren't copied because they're environment-specific.</span></span> <span data-ttu-id="d4c2e-155">Exempel innehåller posterna **BatchServerConfig** och **SysCorpNetPrinters**.</span><span class="sxs-lookup"><span data-stu-id="d4c2e-155">Examples include **BatchServerConfig** and **SysCorpNetPrinters** records.</span></span> <span data-ttu-id="d4c2e-156">Andra element kopieras inte på grund av supportärendens volym.</span><span class="sxs-lookup"><span data-stu-id="d4c2e-156">Other elements aren't copied because of the volume of support tickets.</span></span> <span data-ttu-id="d4c2e-157">Exempel:</span><span class="sxs-lookup"><span data-stu-id="d4c2e-157">For example:</span></span>

- <span data-ttu-id="d4c2e-158">Dubbla e-postmeddelanden kan skickas eftersom SMTP fortfarande är aktiverat i den begränsade miljön för användar godkännande.</span><span class="sxs-lookup"><span data-stu-id="d4c2e-158">Duplicate emails might be sent because SMTP is still enabled in the user acceptance testing (sandbox) environment.</span></span>

- <span data-ttu-id="d4c2e-159">Ogiltiga integrationsmeddelanden kan skickas eftersom batch-jobb fortfarande är aktiverade.</span><span class="sxs-lookup"><span data-stu-id="d4c2e-159">Invalid integration messages might be sent because batch jobs are still enabled.</span></span>

- <span data-ttu-id="d4c2e-160">Användare kan aktiveras innan administratörer kan utföra rensningsåtgärder efter uppdatering.</span><span class="sxs-lookup"><span data-stu-id="d4c2e-160">Users might be enabled before admins can perform post-refresh cleanup actions.</span></span>

<span data-ttu-id="d4c2e-161">Dessutom ändras följande statusvärden när du kopierar en instans:</span><span class="sxs-lookup"><span data-stu-id="d4c2e-161">Also, the following statuses change when you copy an instance:</span></span>

- <span data-ttu-id="d4c2e-162">Alla användare utom administratören har **inaktiverats**.</span><span class="sxs-lookup"><span data-stu-id="d4c2e-162">All users except Admin are set to **Disabled**.</span></span>

- <span data-ttu-id="d4c2e-163">Alla batchjobb, förutom vissa systemjobb, ställs in på **undanhålla**.</span><span class="sxs-lookup"><span data-stu-id="d4c2e-163">All batch jobs, except for some system jobs, are set to **Withhold**.</span></span>

## <a name="environment-admin"></a><span data-ttu-id="d4c2e-164">Miljöadministration</span><span class="sxs-lookup"><span data-stu-id="d4c2e-164">Environment admin</span></span>

<span data-ttu-id="d4c2e-165">Alla användare i målmiljön i begränsat läge, inklusive administratörer, ersätts av användarna i källmiljön.</span><span class="sxs-lookup"><span data-stu-id="d4c2e-165">All users in the target sandbox environment, including Administrators, are replaced by the users of the source environment.</span></span> <span data-ttu-id="d4c2e-166">Kontrollera att du är administratör i källmiljön innan du kopierar en instans.</span><span class="sxs-lookup"><span data-stu-id="d4c2e-166">Before you copy an instance, be sure that you're an Administrator in the source environment.</span></span> <span data-ttu-id="d4c2e-167">Om du inte är det kan du inte logga in till målmiljön efter att kopieringen har slutförts.</span><span class="sxs-lookup"><span data-stu-id="d4c2e-167">If you aren't, you can't sign in to the target sandbox environment after the copy has completed.</span></span>

<span data-ttu-id="d4c2e-168">Alla användare som inte är administratörer i målmiljön i begränsat läge är inaktiverade för att förhindra oönskade inloggningar i miljön i begränsat läge.</span><span class="sxs-lookup"><span data-stu-id="d4c2e-168">All non-Administrator users in the target sandbox environment are disabled to prevent unwanted sign-ins in the sandbox environment.</span></span> <span data-ttu-id="d4c2e-169">Administratörer kan återaktivera användare om det behövs.</span><span class="sxs-lookup"><span data-stu-id="d4c2e-169">Administrators can reenable users if needed.</span></span>

## <a name="apply-custom-fields-to-dataverse"></a><span data-ttu-id="d4c2e-170">Tillämpa anpassade fält på Dataverse</span><span class="sxs-lookup"><span data-stu-id="d4c2e-170">Apply custom fields to Dataverse</span></span>

<span data-ttu-id="d4c2e-171">Om du kopierar en instans till sandbox-miljön och vill integrera sandbox-miljön med Dataverse, måste du återställa anpassade fält till Dataverse-register.</span><span class="sxs-lookup"><span data-stu-id="d4c2e-171">If you copy an instance into your sandbox environment and want to integrate your sandbox environment with Dataverse, you must reapply custom fields to Dataverse tables.</span></span>

<span data-ttu-id="d4c2e-172">Utför följande steg för varje anpassat fält som visas i Dataverse-register:</span><span class="sxs-lookup"><span data-stu-id="d4c2e-172">For each custom field that's exposed on Dataverse tables, do the following steps:</span></span>

1. <span data-ttu-id="d4c2e-173">Gå till det anpassade fältet och välj **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="d4c2e-173">Go to the custom field and select **Edit**.</span></span>

2. <span data-ttu-id="d4c2e-174">Avmarkera fältet **aktiverad** för varje cdm_\*-entitet som det anpassade fältet är aktiverat på.</span><span class="sxs-lookup"><span data-stu-id="d4c2e-174">Unselect the **Enabled** field for each cdm_\* entity that the custom field is enabled on.</span></span>

3. <span data-ttu-id="d4c2e-175">Välj **Verkställ ändringar**.</span><span class="sxs-lookup"><span data-stu-id="d4c2e-175">Select **Apply Changes**.</span></span>

4. <span data-ttu-id="d4c2e-176">Välj **Redigera** igen.</span><span class="sxs-lookup"><span data-stu-id="d4c2e-176">Select **Edit** again.</span></span>

5. <span data-ttu-id="d4c2e-177">Markera fältet **aktiverad** för varje cdm_\*-entitet som det anpassade fältet är aktiverat på.</span><span class="sxs-lookup"><span data-stu-id="d4c2e-177">Select the **Enabled** field for each cdm_\* entity that the custom field is enabled on.</span></span>

6. <span data-ttu-id="d4c2e-178">Välj **Verkställ ändringar**.</span><span class="sxs-lookup"><span data-stu-id="d4c2e-178">Select **Apply Changes** again.</span></span>

<span data-ttu-id="d4c2e-179">Avmarkerar, tillämpar ändringar, markerar om och återanvänder ändringar gör att schemat uppdateras i Dataverse för att inkludera de anpassade fälten.</span><span class="sxs-lookup"><span data-stu-id="d4c2e-179">The process of unselecting, applying changes, reselecting, and reapplying changes prompts the schema to update in Dataverse to include the custom fields.</span></span>

<span data-ttu-id="d4c2e-180">Mer information om anpassade fält finns i [Skapa och arbeta med anpassade fält](../fin-ops-core/fin-ops/get-started/user-defined-fields.md).</span><span class="sxs-lookup"><span data-stu-id="d4c2e-180">For more information about custom fields, see [Create and work with custom fields](../fin-ops-core/fin-ops/get-started/user-defined-fields.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="d4c2e-181">Se även</span><span class="sxs-lookup"><span data-stu-id="d4c2e-181">See also</span></span>

[<span data-ttu-id="d4c2e-182">Reservera Personal</span><span class="sxs-lookup"><span data-stu-id="d4c2e-182">Provision Human Resources</span></span>](hr-admin-setup-provision.md)</br>
[<span data-ttu-id="d4c2e-183">Ta bort en instans</span><span class="sxs-lookup"><span data-stu-id="d4c2e-183">Remove an instance</span></span>](hr-admin-setup-remove-instance.md)</br>
[<span data-ttu-id="d4c2e-184">Uppdatera process</span><span class="sxs-lookup"><span data-stu-id="d4c2e-184">Update process</span></span>](hr-admin-setup-update-process.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]