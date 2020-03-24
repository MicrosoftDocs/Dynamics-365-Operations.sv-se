---
title: Kopiera en instans
description: Du kan använda Microsoft Dynamics Lifecycle Services (LCS) för att kopiera en Microsoft Dynamics 365 Human Resources-databas till en miljö i begränsat läge.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: bb363369994d99f358be0c23cdaf1dbc80b644e5
ms.sourcegitcommit: f38302b9430f2ab3efe91d0a7beff946bc610e8f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/28/2020
ms.locfileid: "3092302"
---
# <a name="copy-an-instance"></a><span data-ttu-id="18074-103">Kopiera en instans</span><span class="sxs-lookup"><span data-stu-id="18074-103">Copy an instance</span></span>

<span data-ttu-id="18074-104">Du kan använda Microsoft Dynamics Lifecycle Services (LCS) för att kopiera en Microsoft Dynamics 365 Human Resources-databas till en miljö i begränsat läge.</span><span class="sxs-lookup"><span data-stu-id="18074-104">You can use Microsoft Dynamics Lifecycle Services (LCS) to copy a Microsoft Dynamics 365 Human Resources database to a sandbox environment.</span></span> <span data-ttu-id="18074-105">Om du har en annan miljö med begränsat läge kan du även kopiera databasen från den miljön till en miljö med begränsat läge.</span><span class="sxs-lookup"><span data-stu-id="18074-105">If you have another sandbox environment, you can also copy the database from that environment to a targeted sandbox environment.</span></span>

<span data-ttu-id="18074-106">Om du vill kopiera en instans måste du säkerställa följande:</span><span class="sxs-lookup"><span data-stu-id="18074-106">To copy an instance, you need to ensure the following:</span></span>

- <span data-ttu-id="18074-107">Den personalinstans som du vill skriva över måste vara en miljö i begränsat läge.</span><span class="sxs-lookup"><span data-stu-id="18074-107">The Human Resources instance you want to overwrite must be a sandbox environment.</span></span>

- <span data-ttu-id="18074-108">De miljöer som du kopierar från och till måste finnas i samma region.</span><span class="sxs-lookup"><span data-stu-id="18074-108">The environments you are copying from and to must be in the same region.</span></span> <span data-ttu-id="18074-109">Du kan inte kopiera mellan regioner.</span><span class="sxs-lookup"><span data-stu-id="18074-109">You can't copy across regions.</span></span>

- <span data-ttu-id="18074-110">Du måste vara administratör i målmiljön för att du ska kunna logga in på den efter att du har kopierat instansen.</span><span class="sxs-lookup"><span data-stu-id="18074-110">You must be an Administrator in the target environment so you can sign into it after copying the instance.</span></span>

- <span data-ttu-id="18074-111">När du kopierar databasen för Personal kopierar du inte de element (appar eller data) som finns i en Microsoft PowerApps-miljö.</span><span class="sxs-lookup"><span data-stu-id="18074-111">When you copy the Human Resources database, you don't copy the elements (apps or data) that are contained in a Microsoft PowerApps environment.</span></span> <span data-ttu-id="18074-112">Information om hur du kopierar element i en PowerApps-miljö finns i [kopiera en miljö](https://docs.microsoft.com/power-platform/admin/copy-environment).</span><span class="sxs-lookup"><span data-stu-id="18074-112">For information about how to copy elements in a PowerApps environment, see [Copy an environment](https://docs.microsoft.com/power-platform/admin/copy-environment).</span></span> <span data-ttu-id="18074-113">Den PowerApps-miljö som du vill skriva över måste vara en miljö i begränsat läge.</span><span class="sxs-lookup"><span data-stu-id="18074-113">The PowerApps environment you want to overwrite must be a sandbox environment.</span></span> <span data-ttu-id="18074-114">Du måste vara global innehavaradministratör om du vill ändra en PowerApps-produktionsmiljö till en miljö i begränsat läge.</span><span class="sxs-lookup"><span data-stu-id="18074-114">You must be a global tenant admin to change a PowerApps production environment to a sandbox environment.</span></span> <span data-ttu-id="18074-115">Mer information om hur du ändrar PowerApps-miljö finns i [Växla en instans](https://docs.microsoft.com/dynamics365/admin/switch-instance).</span><span class="sxs-lookup"><span data-stu-id="18074-115">For more information about changing a PowerApps environment, see [Switch an instance](https://docs.microsoft.com/dynamics365/admin/switch-instance).</span></span>

## <a name="effects-of-copying-a-human-resources-database"></a><span data-ttu-id="18074-116">Effekter av att kopiera personaldatabasen</span><span class="sxs-lookup"><span data-stu-id="18074-116">Effects of copying a Human Resources database</span></span>

<span data-ttu-id="18074-117">Följande händelser inträffar när du kopierar en personaldatabas:</span><span class="sxs-lookup"><span data-stu-id="18074-117">The following events occur when you copy a Human Resources database:</span></span>

- <span data-ttu-id="18074-118">När du kopierar processen raderas den befintliga databasen i målmiljön.</span><span class="sxs-lookup"><span data-stu-id="18074-118">The copy process erases the existing database in the target environment.</span></span> <span data-ttu-id="18074-119">När kopieringsprocessen är klar kan du inte återställa den befintliga databasen.</span><span class="sxs-lookup"><span data-stu-id="18074-119">After the copy process is completed, you can't recover the existing database.</span></span>

- <span data-ttu-id="18074-120">Målmiljön kommer inte att vara tillgänglig förrän kopieringsprocessen har slutförts.</span><span class="sxs-lookup"><span data-stu-id="18074-120">The target environment will be unavailable until the copy process is completed.</span></span>

- <span data-ttu-id="18074-121">Dokument i Microsoft Azure Blob-lagring kopieras inte från en miljö till en annan.</span><span class="sxs-lookup"><span data-stu-id="18074-121">Documents in Microsoft Azure Blob storage aren't copied from one environment to another.</span></span> <span data-ttu-id="18074-122">Därför kopieras inte de kopplade dokumenten och mallarna och de blir kvar i källmiljön.</span><span class="sxs-lookup"><span data-stu-id="18074-122">Therefore, any documents and templates that are attached won't be copied and will remain in the source environment.</span></span>

- <span data-ttu-id="18074-123">Alla användare förutom administratören och andra interna användarkonton kommer inte att vara tillgängliga.​</span><span class="sxs-lookup"><span data-stu-id="18074-123">All users except the Admin user and other internal service user accounts will be unavailable.</span></span> <span data-ttu-id="18074-124">Därför kan administratörsanvändaren ta bort eller dölja data innan andra användare tillåts tillbaka till systemet.</span><span class="sxs-lookup"><span data-stu-id="18074-124">Therefore, the Admin user can delete or obfuscate data before other users are allowed back into the system.</span></span>

- <span data-ttu-id="18074-125">Administratörsanvändaren måste göra obligatoriska konfigurationsändringar, t.ex. återansluta integreringsslutpunkter för specifika tjänster eller URL:er.</span><span class="sxs-lookup"><span data-stu-id="18074-125">The Admin user must make required configuration changes, such as reconnecting integration endpoints to specific services or URLs.</span></span>

## <a name="copy-the-human-resources-database"></a><span data-ttu-id="18074-126">Kopiera databasen för personal</span><span class="sxs-lookup"><span data-stu-id="18074-126">Copy the Human Resources database</span></span>

<span data-ttu-id="18074-127">Om du vill slutföra den här uppgiften kopierar du först en instans och loggar sedan in på Microsoft Power Platform administrationscenter för att kopiera PowerApps-miljön.</span><span class="sxs-lookup"><span data-stu-id="18074-127">To complete this task, you first copy an instance, and then sign in to the Microsoft Power Platform Admin Center to copy your PowerApps environment.</span></span>

> [!WARNING]
> <span data-ttu-id="18074-128">När du kopierar en instans raderas databasen i målinstansen.</span><span class="sxs-lookup"><span data-stu-id="18074-128">When you copy an instance, the database is erased in the target instance.</span></span> <span data-ttu-id="18074-129">Målinstansen är inte tillgänglig under denna process.</span><span class="sxs-lookup"><span data-stu-id="18074-129">The target instance is unavailable during this process.</span></span>

1. <span data-ttu-id="18074-130">Logga in på LCS och välj det LCS-projekt som innehåller den instans som du vill kopiera.</span><span class="sxs-lookup"><span data-stu-id="18074-130">Sign in to LCS, and select the LCS project that contains the instance that you want to copy.</span></span>

2. <span data-ttu-id="18074-131">I LCS-projektet väljer du fliken **-hantering for Personal**.</span><span class="sxs-lookup"><span data-stu-id="18074-131">In your LCS project, select the **Human Resources App Management** tile.</span></span>

3. <span data-ttu-id="18074-132">Markera den instans du vill kopiera och välj sedan **kopiera**.</span><span class="sxs-lookup"><span data-stu-id="18074-132">Select the instance to copy, and then select **Copy**.</span></span>

4. <span data-ttu-id="18074-133">I åtgärdsfönstret **Kopiera en instans** välj instansen som ska skrivas över och välj sedan **Kopiera**.</span><span class="sxs-lookup"><span data-stu-id="18074-133">In the **Copy an instance** task pane, select the instance to overwrite, and then select **Copy**.</span></span> <span data-ttu-id="18074-134">Vänta tills värdet på fältet **Kopieringsstatus** uppdateras till **Slutförd**.</span><span class="sxs-lookup"><span data-stu-id="18074-134">Wait for the value of the **Copy status** field to be updated to **Completed**.</span></span>

   ![[<span data-ttu-id="18074-135">Markera instansen som ska skrivas över</span><span class="sxs-lookup"><span data-stu-id="18074-135">Select instance to overwrite</span></span>](./media/copy-instance-select-target-instance.png)](./media/copy-instance-select-target-instance.png)

5. <span data-ttu-id="18074-136">Välj **Power Platform** och logga in på administrationscenter för Microsoft Power Platform.</span><span class="sxs-lookup"><span data-stu-id="18074-136">Select **Power Platform**, and sign in to the Microsoft Power Platform Admin Center.</span></span>

   ![[<span data-ttu-id="18074-137">Välj Power Platform</span><span class="sxs-lookup"><span data-stu-id="18074-137">Select Power Platform</span></span>](./media/copy-instance-select-power-platform.png)](./media/copy-instance-select-power-platform.png)

6. <span data-ttu-id="18074-138">Markera den PowerApps-miljö du vill kopiera och välj sedan **kopiera**.</span><span class="sxs-lookup"><span data-stu-id="18074-138">Select the PowerApps environment to copy, and then select **Copy**.</span></span>

7. <span data-ttu-id="18074-139">När kopieringsprocessen har slutförts loggar du in på målinstansen och aktiverar Common Data Service-integreringen.</span><span class="sxs-lookup"><span data-stu-id="18074-139">When the copy process is completed, sign in to the target instance, and enable Common Data Service integration.</span></span> <span data-ttu-id="18074-140">Mer information och anvisningar finns i [Konfigurera Common Data Service-integration](https://docs.microsoft.com/dynamics365/talent/hr-common-data-service-integration).</span><span class="sxs-lookup"><span data-stu-id="18074-140">For more information and instructions, see [Configure Common Data Service integration](https://docs.microsoft.com/dynamics365/talent/hr-common-data-service-integration).</span></span>

## <a name="data-elements-and-statuses"></a><span data-ttu-id="18074-141">Dataelement och status</span><span class="sxs-lookup"><span data-stu-id="18074-141">Data elements and statuses</span></span>

<span data-ttu-id="18074-142">Följande dataelement kopieras inte när du kopierar en personalinstans:</span><span class="sxs-lookup"><span data-stu-id="18074-142">The following data elements aren't copied when you copy a Human Resources instance:</span></span>

- <span data-ttu-id="18074-143">E-postadresser i **LogisticsElectronicAddress**-registret</span><span class="sxs-lookup"><span data-stu-id="18074-143">Email addresses in the **LogisticsElectronicAddress** table</span></span>

- <span data-ttu-id="18074-144">Historiken för batchjobb i tabellerna **BatchJobHistory**, **BatchHistory**och **BatchConstraintHistory**</span><span class="sxs-lookup"><span data-stu-id="18074-144">The batch job history in the **BatchJobHistory**, **BatchHistory**, and **BatchConstraintHistory** tables</span></span>

- <span data-ttu-id="18074-145">SMTP-lösenordet (Simple Mail Transfer Protocol) i **SysEmailSMTPPassword**-registret</span><span class="sxs-lookup"><span data-stu-id="18074-145">The Simple Mail Transfer Protocol (SMTP) password in the **SysEmailSMTPPassword** table</span></span>

- <span data-ttu-id="18074-146">SMTP-relayservern i **SysEmailParameters**-registret</span><span class="sxs-lookup"><span data-stu-id="18074-146">The SMTP Relay server in the **SysEmailParameters** table</span></span>

- <span data-ttu-id="18074-147">Utskriftshanteringsinställningar i registren **PrintMgmtSettings** och **PrintMgmtDocInstance**</span><span class="sxs-lookup"><span data-stu-id="18074-147">Print Management settings in the **PrintMgmtSettings** and **PrintMgmtDocInstance** tables</span></span>

- <span data-ttu-id="18074-148">Miljöspecifika poster i registren **SysServerConfig**, **SysServerSessions**, **SysCorpNetPrinters**, **SysClientSessions**, **BatchServerConfig** och **BatchServerGroup**</span><span class="sxs-lookup"><span data-stu-id="18074-148">Environment-specific records in the **SysServerConfig**, **SysServerSessions**, **SysCorpNetPrinters**, **SysClientSessions**, **BatchServerConfig**, and **BatchServerGroup** tables</span></span>

- <span data-ttu-id="18074-149">Dokumentbilagor i DocuValue-registret.</span><span class="sxs-lookup"><span data-stu-id="18074-149">Document attachments in the DocuValue table.</span></span> <span data-ttu-id="18074-150">Dessa bifogade filer innehåller alla Microsoft Office-mallar som har skrivits över i källmiljön</span><span class="sxs-lookup"><span data-stu-id="18074-150">These attachments include any Microsoft Office templates that were overwritten in the source environment</span></span>

- <span data-ttu-id="18074-151">Anslutningssträngen i registret **PersonnelIntegrationConfiguration**</span><span class="sxs-lookup"><span data-stu-id="18074-151">The connection string in the **PersonnelIntegrationConfiguration** table</span></span>

<span data-ttu-id="18074-152">Vissa av elementen kopieras inte eftersom de är miljöspecifika.</span><span class="sxs-lookup"><span data-stu-id="18074-152">Some of these elements aren't copied because they are environment-specific.</span></span> <span data-ttu-id="18074-153">Exempel innehåller posterna **BatchServerConfig** och **SysCorpNetPrinters**.</span><span class="sxs-lookup"><span data-stu-id="18074-153">Examples include **BatchServerConfig** and **SysCorpNetPrinters** records.</span></span> <span data-ttu-id="18074-154">Andra element kopieras inte på grund av supportärendens volym.</span><span class="sxs-lookup"><span data-stu-id="18074-154">Other elements aren't copied because of the volume of support tickets.</span></span> <span data-ttu-id="18074-155">Dubbletter av e-postmeddelanden kan t.ex. skickas eftersom SMTP fortfarande är aktiverat i miljön i begränsat läge för användargodkännande kan ogiltiga integrationsmeddelanden skickas eftersom batch-jobb fortfarande är aktiverade och användarna kan aktiveras innan administratörer kan utföra rensningsåtgärder efter uppdatering.</span><span class="sxs-lookup"><span data-stu-id="18074-155">For example, duplicate emails might be sent because SMTP is still enabled in the user acceptance testing (sandbox) environment, invalid integration messages might be sent because batch jobs are still enabled, and users might be enabled before admins can perform post-refresh cleanup actions.</span></span>

<span data-ttu-id="18074-156">Dessutom ändras följande statusvärden när du kopierar en instans:</span><span class="sxs-lookup"><span data-stu-id="18074-156">In addition, the following statuses change when you copy an instance:</span></span>

- <span data-ttu-id="18074-157">Alla användare utom administratören har **inaktiverats**.</span><span class="sxs-lookup"><span data-stu-id="18074-157">All users except Admin are set to **Disabled**.</span></span>

- <span data-ttu-id="18074-158">Alla batchjobb, förutom vissa systemjobb, ställs in på **undanhålla**.</span><span class="sxs-lookup"><span data-stu-id="18074-158">All batch jobs, except for some system jobs, are set to **Withhold**.</span></span>

## <a name="environment-admin"></a><span data-ttu-id="18074-159">Miljöadministration</span><span class="sxs-lookup"><span data-stu-id="18074-159">Environment admin</span></span>

<span data-ttu-id="18074-160">Alla användare i målmiljön i begränsat läge, inklusive administratörer, ersätts av användarna i källmiljön.</span><span class="sxs-lookup"><span data-stu-id="18074-160">All users in the target sandbox environment, including Administrators, are replaced by the users of the source environment.</span></span> <span data-ttu-id="18074-161">Kontrollera att du är administratör i målmiljön innan du kopierar en instans.</span><span class="sxs-lookup"><span data-stu-id="18074-161">Before you copy an instance, be sure that you're an Administrator in the target environment.</span></span> <span data-ttu-id="18074-162">Om du inte är det kan du inte logga in till målmiljön efter att kopieringen har slutförts.</span><span class="sxs-lookup"><span data-stu-id="18074-162">If you aren't, you won't be able to sign in to the target sandbox environment after the copy has completed.</span></span>

<span data-ttu-id="18074-163">Alla användare som inte är administratörer i målmiljön i begränsat läge är inaktiverade för att förhindra oönskade inloggningar i miljön i begränsat läge.</span><span class="sxs-lookup"><span data-stu-id="18074-163">All non-Administrator users in the target sandbox environment are disabled to prevent unwanted sign-ins in the sandbox environment.</span></span> <span data-ttu-id="18074-164">Administratörer kan återaktivera användare om det behövs.</span><span class="sxs-lookup"><span data-stu-id="18074-164">Administrators can reenable users if needed.</span></span>
