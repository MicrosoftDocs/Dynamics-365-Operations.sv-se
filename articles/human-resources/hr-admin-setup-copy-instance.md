---
title: Kopiera en instans
description: Du kan använda Microsoft Dynamics Lifecycle Services (LCS) för att kopiera en Microsoft Dynamics 365 Human Resources-databas till en miljö i begränsat läge.
author: andreabichsel
manager: AnnBe
ms.date: 07/22/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
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
ms.openlocfilehash: 40ca0a4d9733fc2a163daa4ea1c27a3bfae6d3bf
ms.sourcegitcommit: e89bb3e5420a6ece84f4e80c11e360b4a042f59d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/17/2020
ms.locfileid: "4527847"
---
# <a name="copy-an-instance"></a><span data-ttu-id="4926f-103">Kopiera en instans</span><span class="sxs-lookup"><span data-stu-id="4926f-103">Copy an instance</span></span>

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="4926f-104">Du kan använda Microsoft Dynamics Lifecycle Services (LCS) för att kopiera en Microsoft Dynamics 365 Human Resources-databas till en miljö i begränsat läge.</span><span class="sxs-lookup"><span data-stu-id="4926f-104">You can use Microsoft Dynamics Lifecycle Services (LCS) to copy a Microsoft Dynamics 365 Human Resources database to a sandbox environment.</span></span> <span data-ttu-id="4926f-105">Om du har en annan miljö med begränsat läge kan du även kopiera databasen från den miljön till en miljö med begränsat läge.</span><span class="sxs-lookup"><span data-stu-id="4926f-105">If you have another sandbox environment, you can also copy the database from that environment to a targeted sandbox environment.</span></span>

<span data-ttu-id="4926f-106">Om du vill kopiera en instans bör du tänka på följande:</span><span class="sxs-lookup"><span data-stu-id="4926f-106">To copy an instance, keep the following tips in mind:</span></span>

- <span data-ttu-id="4926f-107">Den personalinstans som du vill skriva över måste vara en miljö i begränsat läge.</span><span class="sxs-lookup"><span data-stu-id="4926f-107">The Human Resources instance you want to overwrite must be a sandbox environment.</span></span>

- <span data-ttu-id="4926f-108">De miljöer som du kopierar från och till måste finnas i samma region.</span><span class="sxs-lookup"><span data-stu-id="4926f-108">The environments you're copying from and to must be in the same region.</span></span> <span data-ttu-id="4926f-109">Du kan inte kopiera mellan regioner.</span><span class="sxs-lookup"><span data-stu-id="4926f-109">You can't copy across regions.</span></span>

- <span data-ttu-id="4926f-110">Du måste vara administratör i målmiljön för att du ska kunna logga in på den efter att du har kopierat instansen.</span><span class="sxs-lookup"><span data-stu-id="4926f-110">You must be an Administrator in the target environment so you can sign into it after copying the instance.</span></span>

- <span data-ttu-id="4926f-111">När du kopierar databasen för Personal kopierar du inte de element (appar eller data) som finns i en Microsoft Power Apps-miljö.</span><span class="sxs-lookup"><span data-stu-id="4926f-111">When you copy the Human Resources database, you don't copy the elements (apps or data) that are contained in a Microsoft Power Apps environment.</span></span> <span data-ttu-id="4926f-112">Information om hur du kopierar element i en Power Apps-miljö finns i [kopiera en miljö](https://docs.microsoft.com/power-platform/admin/copy-environment).</span><span class="sxs-lookup"><span data-stu-id="4926f-112">For information about how to copy elements in a Power Apps environment, see [Copy an environment](https://docs.microsoft.com/power-platform/admin/copy-environment).</span></span> <span data-ttu-id="4926f-113">Den Power Apps-miljö som du vill skriva över måste vara en miljö i begränsat läge.</span><span class="sxs-lookup"><span data-stu-id="4926f-113">The Power Apps environment you want to overwrite must be a sandbox environment.</span></span> <span data-ttu-id="4926f-114">Du måste vara global innehavaradministratör om du vill ändra en Power Apps-produktionsmiljö till en miljö i begränsat läge.</span><span class="sxs-lookup"><span data-stu-id="4926f-114">You must be a global tenant admin to change a Power Apps production environment to a sandbox environment.</span></span> <span data-ttu-id="4926f-115">Mer information om hur du ändrar Power Apps-miljö finns i [Växla en instans](https://docs.microsoft.com/dynamics365/admin/switch-instance).</span><span class="sxs-lookup"><span data-stu-id="4926f-115">For more information about changing a Power Apps environment, see [Switch an instance](https://docs.microsoft.com/dynamics365/admin/switch-instance).</span></span>

- <span data-ttu-id="4926f-116">Om du kopierar en instans till sandbox-miljön och vill integrera sandbox-miljön med Common Data Service måste du återställa anpassade fält till Common Data Service-entiteter.</span><span class="sxs-lookup"><span data-stu-id="4926f-116">If you copy an instance into your sandbox environment and want to integrate your sandbox environment with Common Data Service, you must reapply custom fields to Common Data Service entities.</span></span> <span data-ttu-id="4926f-117">Se [tillämpa anpassade fält på Common Data Service](hr-admin-setup-copy-instance.md?apply-custom-fields-to-common-data-service).</span><span class="sxs-lookup"><span data-stu-id="4926f-117">See [Apply custom fields to Common Data Service](hr-admin-setup-copy-instance.md?apply-custom-fields-to-common-data-service).</span></span>

## <a name="effects-of-copying-a-human-resources-database"></a><span data-ttu-id="4926f-118">Effekter av att kopiera personaldatabasen</span><span class="sxs-lookup"><span data-stu-id="4926f-118">Effects of copying a Human Resources database</span></span>

<span data-ttu-id="4926f-119">Följande händelser inträffar när du kopierar en personaldatabas:</span><span class="sxs-lookup"><span data-stu-id="4926f-119">The following events occur when you copy a Human Resources database:</span></span>

- <span data-ttu-id="4926f-120">När du kopierar processen raderas den befintliga databasen i målmiljön.</span><span class="sxs-lookup"><span data-stu-id="4926f-120">The copy process erases the existing database in the target environment.</span></span> <span data-ttu-id="4926f-121">När kopieringsprocessen är klar kan du inte återställa den befintliga databasen.</span><span class="sxs-lookup"><span data-stu-id="4926f-121">After the copy process is completed, you can't recover the existing database.</span></span>

- <span data-ttu-id="4926f-122">Målmiljön kommer inte att vara tillgänglig förrän kopieringsprocessen har slutförts.</span><span class="sxs-lookup"><span data-stu-id="4926f-122">The target environment will be unavailable until the copy process is completed.</span></span>

- <span data-ttu-id="4926f-123">Dokument i Microsoft Azure Blob-lagring kopieras inte från en miljö till en annan.</span><span class="sxs-lookup"><span data-stu-id="4926f-123">Documents in Microsoft Azure Blob storage aren't copied from one environment to another.</span></span> <span data-ttu-id="4926f-124">Därför kopieras inte de kopplade dokumenten och mallarna och de blir kvar i källmiljön.</span><span class="sxs-lookup"><span data-stu-id="4926f-124">As a result, any documents and templates that are attached won't be copied and will remain in the source environment.</span></span>

- <span data-ttu-id="4926f-125">Alla användare förutom administratören och andra interna användarkonton kommer inte att vara tillgängliga.​</span><span class="sxs-lookup"><span data-stu-id="4926f-125">All users except the Admin user and other internal service user accounts will be unavailable.</span></span> <span data-ttu-id="4926f-126">Administratörsanvändaren kan ta bort eller dölja data innan andra användare tillåts tillbaka till systemet.</span><span class="sxs-lookup"><span data-stu-id="4926f-126">The Admin user can delete or obfuscate data before other users are allowed back into the system.</span></span>

- <span data-ttu-id="4926f-127">Administratörsanvändaren måste göra obligatoriska konfigurationsändringar, t.ex. återansluta integreringsslutpunkter för specifika tjänster eller URL:er.</span><span class="sxs-lookup"><span data-stu-id="4926f-127">The Admin user must make required configuration changes, such as reconnecting integration endpoints to specific services or URLs.</span></span>

## <a name="copy-the-human-resources-database"></a><span data-ttu-id="4926f-128">Kopiera databasen för personal</span><span class="sxs-lookup"><span data-stu-id="4926f-128">Copy the Human Resources database</span></span>

<span data-ttu-id="4926f-129">Om du vill slutföra den här uppgiften kopierar du först en instans och loggar sedan in på Microsoft Power Platform administrationscenter för att kopiera Power Apps-miljön.</span><span class="sxs-lookup"><span data-stu-id="4926f-129">To complete this task, you first copy an instance, and then sign in to the Microsoft Power Platform Admin Center to copy your Power Apps environment.</span></span>

> [!WARNING]
> <span data-ttu-id="4926f-130">När du kopierar en instans raderas databasen i målinstansen.</span><span class="sxs-lookup"><span data-stu-id="4926f-130">When you copy an instance, the database is erased in the target instance.</span></span> <span data-ttu-id="4926f-131">Målinstansen är inte tillgänglig under denna process.</span><span class="sxs-lookup"><span data-stu-id="4926f-131">The target instance is unavailable during this process.</span></span>

1. <span data-ttu-id="4926f-132">Logga in på LCS och välj det LCS-projekt som innehåller den instans som du vill kopiera.</span><span class="sxs-lookup"><span data-stu-id="4926f-132">Sign in to LCS, and select the LCS project that contains the instance that you want to copy.</span></span>

2. <span data-ttu-id="4926f-133">I LCS-projektet väljer du fliken **-hantering for Personal**.</span><span class="sxs-lookup"><span data-stu-id="4926f-133">In your LCS project, select the **Human Resources App Management** tile.</span></span>

3. <span data-ttu-id="4926f-134">Markera den instans du vill kopiera och välj sedan **kopiera**.</span><span class="sxs-lookup"><span data-stu-id="4926f-134">Select the instance to copy, and then select **Copy**.</span></span>

4. <span data-ttu-id="4926f-135">I åtgärdsfönstret **Kopiera en instans** välj instansen som ska skrivas över och välj sedan **Kopiera**.</span><span class="sxs-lookup"><span data-stu-id="4926f-135">In the **Copy an instance** task pane, select the instance to overwrite, and then select **Copy**.</span></span> <span data-ttu-id="4926f-136">Vänta tills värdet på fältet **Kopieringsstatus** uppdateras till **Slutförd**.</span><span class="sxs-lookup"><span data-stu-id="4926f-136">Wait for the value of the **Copy status** field to be updated to **Completed**.</span></span>

   ![[<span data-ttu-id="4926f-137">Välj instans som ska skrivas över</span><span class="sxs-lookup"><span data-stu-id="4926f-137">Select instance to overwrite</span></span>](./media/copy-instance-select-target-instance.png)](./media/copy-instance-select-target-instance.png)

5. <span data-ttu-id="4926f-138">Välj **Power Platform** och logga in på administrationscenter för Microsoft Power Platform.</span><span class="sxs-lookup"><span data-stu-id="4926f-138">Select **Power Platform**, and sign in to the Microsoft Power Platform Admin Center.</span></span>

   ![[<span data-ttu-id="4926f-139">Välj Power Platform</span><span class="sxs-lookup"><span data-stu-id="4926f-139">Select Power Platform</span></span>](./media/copy-instance-select-power-platform.png)](./media/copy-instance-select-power-platform.png)

6. <span data-ttu-id="4926f-140">Markera den Power Apps-miljö du vill kopiera och välj sedan **kopiera**.</span><span class="sxs-lookup"><span data-stu-id="4926f-140">Select the Power Apps environment to copy, and then select **Copy**.</span></span>

7. <span data-ttu-id="4926f-141">När kopieringsprocessen har slutförts loggar du in på målinstansen och aktiverar Common Data Service-integreringen.</span><span class="sxs-lookup"><span data-stu-id="4926f-141">When the copy process is completed, sign in to the target instance, and enable Common Data Service integration.</span></span> <span data-ttu-id="4926f-142">Mer information och anvisningar finns i [Konfigurera Common Data Service-integration](https://docs.microsoft.com/dynamics365/talent/hr-common-data-service-integration).</span><span class="sxs-lookup"><span data-stu-id="4926f-142">For more information and instructions, see [Configure Common Data Service integration](https://docs.microsoft.com/dynamics365/talent/hr-common-data-service-integration).</span></span>

## <a name="data-elements-and-statuses"></a><span data-ttu-id="4926f-143">Dataelement och status</span><span class="sxs-lookup"><span data-stu-id="4926f-143">Data elements and statuses</span></span>

<span data-ttu-id="4926f-144">Följande dataelement kopieras inte när du kopierar en personalinstans:</span><span class="sxs-lookup"><span data-stu-id="4926f-144">The following data elements aren't copied when you copy a Human Resources instance:</span></span>

- <span data-ttu-id="4926f-145">E-postadresser i **LogisticsElectronicAddress**-registret</span><span class="sxs-lookup"><span data-stu-id="4926f-145">Email addresses in the **LogisticsElectronicAddress** table</span></span>

- <span data-ttu-id="4926f-146">Historiken för batchjobb i tabellerna **BatchJobHistory**, **BatchHistory** och **BatchConstraintHistory**</span><span class="sxs-lookup"><span data-stu-id="4926f-146">The batch job history in the **BatchJobHistory**, **BatchHistory**, and **BatchConstraintHistory** tables</span></span>

- <span data-ttu-id="4926f-147">SMTP-lösenordet (Simple Mail Transfer Protocol) i **SysEmailSMTPPassword**-registret</span><span class="sxs-lookup"><span data-stu-id="4926f-147">The Simple Mail Transfer Protocol (SMTP) password in the **SysEmailSMTPPassword** table</span></span>

- <span data-ttu-id="4926f-148">SMTP-relayservern i **SysEmailParameters**-registret</span><span class="sxs-lookup"><span data-stu-id="4926f-148">The SMTP Relay server in the **SysEmailParameters** table</span></span>

- <span data-ttu-id="4926f-149">Utskriftshanteringsinställningar i registren **PrintMgmtSettings** och **PrintMgmtDocInstance**</span><span class="sxs-lookup"><span data-stu-id="4926f-149">Print Management settings in the **PrintMgmtSettings** and **PrintMgmtDocInstance** tables</span></span>

- <span data-ttu-id="4926f-150">Miljöspecifika poster i registren **SysServerConfig**, **SysServerSessions**, **SysCorpNetPrinters**, **SysClientSessions**, **BatchServerConfig** och **BatchServerGroup**</span><span class="sxs-lookup"><span data-stu-id="4926f-150">Environment-specific records in the **SysServerConfig**, **SysServerSessions**, **SysCorpNetPrinters**, **SysClientSessions**, **BatchServerConfig**, and **BatchServerGroup** tables</span></span>

- <span data-ttu-id="4926f-151">Dokumentbilagor i DocuValue-registret.</span><span class="sxs-lookup"><span data-stu-id="4926f-151">Document attachments in the DocuValue table.</span></span> <span data-ttu-id="4926f-152">Dessa bifogade filer innehåller alla Microsoft Office-mallar som har skrivits över i källmiljön</span><span class="sxs-lookup"><span data-stu-id="4926f-152">These attachments include any Microsoft Office templates that were overwritten in the source environment</span></span>

- <span data-ttu-id="4926f-153">Anslutningssträngen i registret **PersonnelIntegrationConfiguration**</span><span class="sxs-lookup"><span data-stu-id="4926f-153">The connection string in the **PersonnelIntegrationConfiguration** table</span></span>

<span data-ttu-id="4926f-154">Vissa av elementen kopieras inte eftersom de är miljöspecifika.</span><span class="sxs-lookup"><span data-stu-id="4926f-154">Some of these elements aren't copied because they're environment-specific.</span></span> <span data-ttu-id="4926f-155">Exempel innehåller posterna **BatchServerConfig** och **SysCorpNetPrinters**.</span><span class="sxs-lookup"><span data-stu-id="4926f-155">Examples include **BatchServerConfig** and **SysCorpNetPrinters** records.</span></span> <span data-ttu-id="4926f-156">Andra element kopieras inte på grund av supportärendens volym.</span><span class="sxs-lookup"><span data-stu-id="4926f-156">Other elements aren't copied because of the volume of support tickets.</span></span> <span data-ttu-id="4926f-157">Exempel:</span><span class="sxs-lookup"><span data-stu-id="4926f-157">For example:</span></span>

- <span data-ttu-id="4926f-158">Dubbla e-postmeddelanden kan skickas eftersom SMTP fortfarande är aktiverat i den begränsade miljön för användar godkännande.</span><span class="sxs-lookup"><span data-stu-id="4926f-158">Duplicate emails might be sent because SMTP is still enabled in the user acceptance testing (sandbox) environment.</span></span>

- <span data-ttu-id="4926f-159">Ogiltiga integrationsmeddelanden kan skickas eftersom batch-jobb fortfarande är aktiverade.</span><span class="sxs-lookup"><span data-stu-id="4926f-159">Invalid integration messages might be sent because batch jobs are still enabled.</span></span>

- <span data-ttu-id="4926f-160">Användare kan aktiveras innan administratörer kan utföra rensningsåtgärder efter uppdatering.</span><span class="sxs-lookup"><span data-stu-id="4926f-160">Users might be enabled before admins can perform post-refresh cleanup actions.</span></span>

<span data-ttu-id="4926f-161">Dessutom ändras följande statusvärden när du kopierar en instans:</span><span class="sxs-lookup"><span data-stu-id="4926f-161">Also, the following statuses change when you copy an instance:</span></span>

- <span data-ttu-id="4926f-162">Alla användare utom administratören har **inaktiverats**.</span><span class="sxs-lookup"><span data-stu-id="4926f-162">All users except Admin are set to **Disabled**.</span></span>

- <span data-ttu-id="4926f-163">Alla batchjobb, förutom vissa systemjobb, ställs in på **undanhålla**.</span><span class="sxs-lookup"><span data-stu-id="4926f-163">All batch jobs, except for some system jobs, are set to **Withhold**.</span></span>

## <a name="environment-admin"></a><span data-ttu-id="4926f-164">Miljöadministration</span><span class="sxs-lookup"><span data-stu-id="4926f-164">Environment admin</span></span>

<span data-ttu-id="4926f-165">Alla användare i målmiljön i begränsat läge, inklusive administratörer, ersätts av användarna i källmiljön.</span><span class="sxs-lookup"><span data-stu-id="4926f-165">All users in the target sandbox environment, including Administrators, are replaced by the users of the source environment.</span></span> <span data-ttu-id="4926f-166">Kontrollera att du är administratör i källmiljön innan du kopierar en instans.</span><span class="sxs-lookup"><span data-stu-id="4926f-166">Before you copy an instance, be sure that you're an Administrator in the source environment.</span></span> <span data-ttu-id="4926f-167">Om du inte är det kan du inte logga in till målmiljön efter att kopieringen har slutförts.</span><span class="sxs-lookup"><span data-stu-id="4926f-167">If you aren't, you can't sign in to the target sandbox environment after the copy has completed.</span></span>

<span data-ttu-id="4926f-168">Alla användare som inte är administratörer i målmiljön i begränsat läge är inaktiverade för att förhindra oönskade inloggningar i miljön i begränsat läge.</span><span class="sxs-lookup"><span data-stu-id="4926f-168">All non-Administrator users in the target sandbox environment are disabled to prevent unwanted sign-ins in the sandbox environment.</span></span> <span data-ttu-id="4926f-169">Administratörer kan återaktivera användare om det behövs.</span><span class="sxs-lookup"><span data-stu-id="4926f-169">Administrators can reenable users if needed.</span></span>

## <a name="apply-custom-fields-to-common-data-service"></a><span data-ttu-id="4926f-170">Tillämpa anpassade fält på Common Data Service</span><span class="sxs-lookup"><span data-stu-id="4926f-170">Apply custom fields to Common Data Service</span></span>

<span data-ttu-id="4926f-171">Om du kopierar en instans till sandbox-miljön och vill integrera sandbox-miljön med Common Data Service måste du återställa anpassade fält till Common Data Service-entiteter.</span><span class="sxs-lookup"><span data-stu-id="4926f-171">If you copy an instance into your sandbox environment and want to integrate your sandbox environment with Common Data Service, you must reapply custom fields to Common Data Service entities.</span></span>

<span data-ttu-id="4926f-172">Utför följande steg för varje anpassat fält som visas på Common Data Service-entiteter:</span><span class="sxs-lookup"><span data-stu-id="4926f-172">For each custom field that's exposed on Common Data Service entities, do the following steps:</span></span>

1. <span data-ttu-id="4926f-173">Gå till det anpassade fältet och välj **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="4926f-173">Go to the custom field and select **Edit**.</span></span>

2. <span data-ttu-id="4926f-174">Avmarkera fältet **aktiverad** för varje cdm_\*-entitet som det anpassade fältet är aktiverat på.</span><span class="sxs-lookup"><span data-stu-id="4926f-174">Unselect the **Enabled** field for each cdm_\* entity that the custom field is enabled on.</span></span>

3. <span data-ttu-id="4926f-175">Välj **Verkställ ändringar**.</span><span class="sxs-lookup"><span data-stu-id="4926f-175">Select **Apply Changes**.</span></span>

4. <span data-ttu-id="4926f-176">Välj **Redigera** igen.</span><span class="sxs-lookup"><span data-stu-id="4926f-176">Select **Edit** again.</span></span>

5. <span data-ttu-id="4926f-177">Markera fältet **aktiverad** för varje cdm_\*-entitet som det anpassade fältet är aktiverat på.</span><span class="sxs-lookup"><span data-stu-id="4926f-177">Select the **Enabled** field for each cdm_\* entity that the custom field is enabled on.</span></span>

6. <span data-ttu-id="4926f-178">Välj **Verkställ ändringar**.</span><span class="sxs-lookup"><span data-stu-id="4926f-178">Select **Apply Changes** again.</span></span>

<span data-ttu-id="4926f-179">Avmarkerar, tillämpar ändringar, markerar om och återanvänder ändringar gör att schemat uppdateras i Common Data Service för att inkludera de anpassade fälten.</span><span class="sxs-lookup"><span data-stu-id="4926f-179">The process of unselecting, applying changes, reselecting, and reapplying changes prompts the schema to update in Common Data Service to include the custom fields.</span></span>

<span data-ttu-id="4926f-180">Mer information om anpassade fält finns i [Skapa och arbeta med anpassade fält](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/user-defined-fields).</span><span class="sxs-lookup"><span data-stu-id="4926f-180">For more information about custom fields, see [Create and work with custom fields](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/user-defined-fields).</span></span>

## <a name="see-also"></a><span data-ttu-id="4926f-181">Se även</span><span class="sxs-lookup"><span data-stu-id="4926f-181">See also</span></span>

[<span data-ttu-id="4926f-182">Reservera Human Resources</span><span class="sxs-lookup"><span data-stu-id="4926f-182">Provision Human Resources</span></span>](hr-admin-setup-provision.md)</br>
[<span data-ttu-id="4926f-183">Ta bort en instans</span><span class="sxs-lookup"><span data-stu-id="4926f-183">Remove an instance</span></span>](hr-admin-setup-remove-instance.md)</br>
[<span data-ttu-id="4926f-184">Uppdatera process</span><span class="sxs-lookup"><span data-stu-id="4926f-184">Update process</span></span>](hr-admin-setup-update-process.md)

