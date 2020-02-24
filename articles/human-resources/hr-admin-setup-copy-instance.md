---
title: Kopiera en instans
description: ''
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
ms.openlocfilehash: 0bbe325edb65cad0c1912e0a6ade559e5675dc58
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/03/2020
ms.locfileid: "3010552"
---
# <a name="copy-an-instance"></a><span data-ttu-id="c6263-102">Kopiera en instans</span><span class="sxs-lookup"><span data-stu-id="c6263-102">Copy an instance</span></span>

<span data-ttu-id="c6263-103">Du kan använda Microsoft Dynamics Lifecycle Services (LCS) för att kopiera en Microsoft Dynamics 365 Human Resources-databas till en miljö i begränsat läge.</span><span class="sxs-lookup"><span data-stu-id="c6263-103">You can use Microsoft Dynamics Lifecycle Services (LCS) to copy a Microsoft Dynamics 365 Human Resources database to a sandbox environment.</span></span> <span data-ttu-id="c6263-104">Om du har en annan miljö med begränsat läge kan du även kopiera databasen från den miljön till en miljö med begränsat läge.</span><span class="sxs-lookup"><span data-stu-id="c6263-104">If you have another sandbox environment, you can also copy the database from that environment to a targeted sandbox environment.</span></span>

<span data-ttu-id="c6263-105">Om du vill kopiera en instans måste du säkerställa följande:</span><span class="sxs-lookup"><span data-stu-id="c6263-105">To copy an instance, you need to ensure the following:</span></span>

- <span data-ttu-id="c6263-106">Den personalinstans som du vill skriva över måste vara en miljö i begränsat läge.</span><span class="sxs-lookup"><span data-stu-id="c6263-106">The Human Resources instance you want to overwrite must be a sandbox environment.</span></span>

- <span data-ttu-id="c6263-107">De miljöer som du kopierar från och till måste finnas i samma region.</span><span class="sxs-lookup"><span data-stu-id="c6263-107">The environments you are copying from and to must be in the same region.</span></span> <span data-ttu-id="c6263-108">Du kan inte kopiera mellan regioner.</span><span class="sxs-lookup"><span data-stu-id="c6263-108">You can't copy across regions.</span></span>

- <span data-ttu-id="c6263-109">Du måste vara administratör i målmiljön för att du ska kunna logga in på den efter att du har kopierat instansen.</span><span class="sxs-lookup"><span data-stu-id="c6263-109">You must be an Administrator in the target environment so you can sign into it after copying the instance.</span></span>

- <span data-ttu-id="c6263-110">När du kopierar databasen för Personal kopierar du inte de element (appar eller data) som finns i en Microsoft PowerApps-miljö.</span><span class="sxs-lookup"><span data-stu-id="c6263-110">When you copy the Human Resources database, you don't copy the elements (apps or data) that are contained in a Microsoft PowerApps environment.</span></span> <span data-ttu-id="c6263-111">Information om hur du kopierar element i en PowerApps-miljö finns i [kopiera en miljö](https://docs.microsoft.com/power-platform/admin/copy-environment).</span><span class="sxs-lookup"><span data-stu-id="c6263-111">For information about how to copy elements in a PowerApps environment, see [Copy an environment](https://docs.microsoft.com/power-platform/admin/copy-environment).</span></span> <span data-ttu-id="c6263-112">Den PowerApps-miljö som du vill skriva över måste vara en miljö i begränsat läge.</span><span class="sxs-lookup"><span data-stu-id="c6263-112">The PowerApps environment you want to overwrite must be a sandbox environment.</span></span> <span data-ttu-id="c6263-113">Du måste vara global innehavaradministratör om du vill ändra en PowerApps-produktionsmiljö till en miljö i begränsat läge.</span><span class="sxs-lookup"><span data-stu-id="c6263-113">You must be a global tenant admin to change a PowerApps production environment to a sandbox environment.</span></span> <span data-ttu-id="c6263-114">Mer information om hur du ändrar PowerApps-miljö finns i [Växla en instans](https://docs.microsoft.com/dynamics365/admin/switch-instance).</span><span class="sxs-lookup"><span data-stu-id="c6263-114">For more information about changing a PowerApps environment, see [Switch an instance](https://docs.microsoft.com/dynamics365/admin/switch-instance).</span></span>

## <a name="effects-of-copying-a-human-resources-database"></a><span data-ttu-id="c6263-115">Effekter av att kopiera personaldatabasen</span><span class="sxs-lookup"><span data-stu-id="c6263-115">Effects of copying a Human Resources database</span></span>

<span data-ttu-id="c6263-116">Följande händelser inträffar när du kopierar en personaldatabas:</span><span class="sxs-lookup"><span data-stu-id="c6263-116">The following events occur when you copy a Human Resources database:</span></span>

- <span data-ttu-id="c6263-117">När du kopierar processen raderas den befintliga databasen i målmiljön.</span><span class="sxs-lookup"><span data-stu-id="c6263-117">The copy process erases the existing database in the target environment.</span></span> <span data-ttu-id="c6263-118">När kopieringsprocessen är klar kan du inte återställa den befintliga databasen.</span><span class="sxs-lookup"><span data-stu-id="c6263-118">After the copy process is completed, you can't recover the existing database.</span></span>

- <span data-ttu-id="c6263-119">Målmiljön kommer inte att vara tillgänglig förrän kopieringsprocessen har slutförts.</span><span class="sxs-lookup"><span data-stu-id="c6263-119">The target environment will be unavailable until the copy process is completed.</span></span>

- <span data-ttu-id="c6263-120">Dokument i Microsoft Azure Blob-lagring kopieras inte från en miljö till en annan.</span><span class="sxs-lookup"><span data-stu-id="c6263-120">Documents in Microsoft Azure Blob storage aren't copied from one environment to another.</span></span> <span data-ttu-id="c6263-121">Därför kopieras inte de kopplade dokumenten och mallarna och de blir kvar i källmiljön.</span><span class="sxs-lookup"><span data-stu-id="c6263-121">Therefore, any documents and templates that are attached won't be copied and will remain in the source environment.</span></span>

- <span data-ttu-id="c6263-122">Alla användare förutom administratören och andra interna användarkonton kommer inte att vara tillgängliga.​</span><span class="sxs-lookup"><span data-stu-id="c6263-122">All users except the Admin user and other internal service user accounts will be unavailable.</span></span> <span data-ttu-id="c6263-123">Därför kan administratörsanvändaren ta bort eller dölja data innan andra användare tillåts tillbaka till systemet.</span><span class="sxs-lookup"><span data-stu-id="c6263-123">Therefore, the Admin user can delete or obfuscate data before other users are allowed back into the system.</span></span>

- <span data-ttu-id="c6263-124">Administratörsanvändaren måste göra obligatoriska konfigurationsändringar, t.ex. återansluta integreringsslutpunkter för specifika tjänster eller URL:er.</span><span class="sxs-lookup"><span data-stu-id="c6263-124">The Admin user must make required configuration changes, such as reconnecting integration endpoints to specific services or URLs.</span></span>

## <a name="copy-the-human-resources-database"></a><span data-ttu-id="c6263-125">Kopiera databasen för personal</span><span class="sxs-lookup"><span data-stu-id="c6263-125">Copy the Human Resources database</span></span>

<span data-ttu-id="c6263-126">Om du vill slutföra den här uppgiften kopierar du först en instans och loggar sedan in på Microsoft Power Platform administrationscenter för att kopiera PowerApps-miljön.</span><span class="sxs-lookup"><span data-stu-id="c6263-126">To complete this task, you first copy an instance, and then sign in to the Microsoft Power Platform Admin Center to copy your PowerApps environment.</span></span>

> [!WARNING]
> <span data-ttu-id="c6263-127">När du kopierar en instans raderas databasen i målinstansen.</span><span class="sxs-lookup"><span data-stu-id="c6263-127">When you copy an instance, the database is erased in the target instance.</span></span> <span data-ttu-id="c6263-128">Målinstansen är inte tillgänglig under denna process.</span><span class="sxs-lookup"><span data-stu-id="c6263-128">The target instance is unavailable during this process.</span></span>

1. <span data-ttu-id="c6263-129">Logga in på LCS och välj det LCS-projekt som innehåller den instans som du vill kopiera.</span><span class="sxs-lookup"><span data-stu-id="c6263-129">Sign in to LCS, and select the LCS project that contains the instance that you want to copy.</span></span>

2. <span data-ttu-id="c6263-130">I LCS-projektet väljer du fliken **-hantering for Personal**.</span><span class="sxs-lookup"><span data-stu-id="c6263-130">In your LCS project, select the **Human Resources App Management** tile.</span></span>

3. <span data-ttu-id="c6263-131">Markera den instans du vill kopiera och välj sedan **kopiera**.</span><span class="sxs-lookup"><span data-stu-id="c6263-131">Select the instance to copy, and then select **Copy**.</span></span>

4. <span data-ttu-id="c6263-132">I åtgärdsfönstret **Kopiera en instans** välj instansen som ska skrivas över och välj sedan **Kopiera**.</span><span class="sxs-lookup"><span data-stu-id="c6263-132">In the **Copy an instance** task pane, select the instance to overwrite, and then select **Copy**.</span></span> <span data-ttu-id="c6263-133">Vänta tills värdet på fältet **Kopieringsstatus** uppdateras till **Slutförd**.</span><span class="sxs-lookup"><span data-stu-id="c6263-133">Wait for the value of the **Copy status** field to be updated to **Completed**.</span></span>

   ![[<span data-ttu-id="c6263-134">Välj instans som ska skrivas över</span><span class="sxs-lookup"><span data-stu-id="c6263-134">Select instance to overwrite</span></span>](./media/copy-instance-select-target-instance.png)](./media/copy-instance-select-target-instance.png)

5. <span data-ttu-id="c6263-135">Välj **Power Platform** och logga in på administrationscenter för Microsoft Power Platform.</span><span class="sxs-lookup"><span data-stu-id="c6263-135">Select **Power Platform**, and sign in to the Microsoft Power Platform Admin Center.</span></span>

   ![[<span data-ttu-id="c6263-136">Välj Power Platform</span><span class="sxs-lookup"><span data-stu-id="c6263-136">Select Power Platform</span></span>](./media/copy-instance-select-power-platform.png)](./media/copy-instance-select-power-platform.png)

6. <span data-ttu-id="c6263-137">Markera den PowerApps-miljö du vill kopiera och välj sedan **kopiera**.</span><span class="sxs-lookup"><span data-stu-id="c6263-137">Select the PowerApps environment to copy, and then select **Copy**.</span></span>

7. <span data-ttu-id="c6263-138">När kopieringsprocessen har slutförts loggar du in på målinstansen och aktiverar Common Data Service-integreringen.</span><span class="sxs-lookup"><span data-stu-id="c6263-138">When the copy process is completed, sign in to the target instance, and enable Common Data Service integration.</span></span> <span data-ttu-id="c6263-139">Mer information och anvisningar finns i [Konfigurera Common Data Service-integration](https://docs.microsoft.com/dynamics365/talent/hr-common-data-service-integration).</span><span class="sxs-lookup"><span data-stu-id="c6263-139">For more information and instructions, see [Configure Common Data Service integration](https://docs.microsoft.com/dynamics365/talent/hr-common-data-service-integration).</span></span>

## <a name="data-elements-and-statuses"></a><span data-ttu-id="c6263-140">Dataelement och status</span><span class="sxs-lookup"><span data-stu-id="c6263-140">Data elements and statuses</span></span>

<span data-ttu-id="c6263-141">Följande dataelement kopieras inte när du kopierar en personalinstans:</span><span class="sxs-lookup"><span data-stu-id="c6263-141">The following data elements aren't copied when you copy a Human Resources instance:</span></span>

- <span data-ttu-id="c6263-142">E-postadresser i **LogisticsElectronicAddress**-registret</span><span class="sxs-lookup"><span data-stu-id="c6263-142">Email addresses in the **LogisticsElectronicAddress** table</span></span>

- <span data-ttu-id="c6263-143">Historiken för batchjobb i tabellerna **BatchJobHistory**, **BatchHistory**och **BatchConstraintHistory**</span><span class="sxs-lookup"><span data-stu-id="c6263-143">The batch job history in the **BatchJobHistory**, **BatchHistory**, and **BatchConstraintHistory** tables</span></span>

- <span data-ttu-id="c6263-144">SMTP-lösenordet (Simple Mail Transfer Protocol) i **SysEmailSMTPPassword**-registret</span><span class="sxs-lookup"><span data-stu-id="c6263-144">The Simple Mail Transfer Protocol (SMTP) password in the **SysEmailSMTPPassword** table</span></span>

- <span data-ttu-id="c6263-145">SMTP-relayservern i **SysEmailParameters**-registret</span><span class="sxs-lookup"><span data-stu-id="c6263-145">The SMTP Relay server in the **SysEmailParameters** table</span></span>

- <span data-ttu-id="c6263-146">Utskriftshanteringsinställningar i registren **PrintMgmtSettings** och **PrintMgmtDocInstance**</span><span class="sxs-lookup"><span data-stu-id="c6263-146">Print Management settings in the **PrintMgmtSettings** and **PrintMgmtDocInstance** tables</span></span>

- <span data-ttu-id="c6263-147">Miljöspecifika poster i registren **SysServerConfig**, **SysServerSessions**, **SysCorpNetPrinters**, **SysClientSessions**, **BatchServerConfig** och **BatchServerGroup**</span><span class="sxs-lookup"><span data-stu-id="c6263-147">Environment-specific records in the **SysServerConfig**, **SysServerSessions**, **SysCorpNetPrinters**, **SysClientSessions**, **BatchServerConfig**, and **BatchServerGroup** tables</span></span>

- <span data-ttu-id="c6263-148">Dokumentbilagor i DocuValue-registret.</span><span class="sxs-lookup"><span data-stu-id="c6263-148">Document attachments in the DocuValue table.</span></span> <span data-ttu-id="c6263-149">Dessa bifogade filer innehåller alla Microsoft Office-mallar som har skrivits över i källmiljön</span><span class="sxs-lookup"><span data-stu-id="c6263-149">These attachments include any Microsoft Office templates that were overwritten in the source environment</span></span>

- <span data-ttu-id="c6263-150">Anslutningssträngen i registret **PersonnelIntegrationConfiguration**</span><span class="sxs-lookup"><span data-stu-id="c6263-150">The connection string in the **PersonnelIntegrationConfiguration** table</span></span>

<span data-ttu-id="c6263-151">Vissa av elementen kopieras inte eftersom de är miljöspecifika.</span><span class="sxs-lookup"><span data-stu-id="c6263-151">Some of these elements aren't copied because they are environment-specific.</span></span> <span data-ttu-id="c6263-152">Exempel innehåller posterna **BatchServerConfig** och **SysCorpNetPrinters**.</span><span class="sxs-lookup"><span data-stu-id="c6263-152">Examples include **BatchServerConfig** and **SysCorpNetPrinters** records.</span></span> <span data-ttu-id="c6263-153">Andra element kopieras inte på grund av supportärendens volym.</span><span class="sxs-lookup"><span data-stu-id="c6263-153">Other elements aren't copied because of the volume of support tickets.</span></span> <span data-ttu-id="c6263-154">Dubbletter av e-postmeddelanden kan t.ex. skickas eftersom SMTP fortfarande är aktiverat i miljön i begränsat läge för användargodkännande kan ogiltiga integrationsmeddelanden skickas eftersom batch-jobb fortfarande är aktiverade och användarna kan aktiveras innan administratörer kan utföra rensningsåtgärder efter uppdatering.</span><span class="sxs-lookup"><span data-stu-id="c6263-154">For example, duplicate emails might be sent because SMTP is still enabled in the user acceptance testing (sandbox) environment, invalid integration messages might be sent because batch jobs are still enabled, and users might be enabled before admins can perform post-refresh cleanup actions.</span></span>

<span data-ttu-id="c6263-155">Dessutom ändras följande statusvärden när du kopierar en instans:</span><span class="sxs-lookup"><span data-stu-id="c6263-155">In addition, the following statuses change when you copy an instance:</span></span>

- <span data-ttu-id="c6263-156">Alla användare utom administratören har **inaktiverats**.</span><span class="sxs-lookup"><span data-stu-id="c6263-156">All users except Admin are set to **Disabled**.</span></span>

- <span data-ttu-id="c6263-157">Alla batchjobb, förutom vissa systemjobb, ställs in på **undanhålla**.</span><span class="sxs-lookup"><span data-stu-id="c6263-157">All batch jobs, except for some system jobs, are set to **Withhold**.</span></span>

## <a name="environment-admin"></a><span data-ttu-id="c6263-158">Miljöadministration</span><span class="sxs-lookup"><span data-stu-id="c6263-158">Environment admin</span></span>

<span data-ttu-id="c6263-159">Alla användare i målmiljön i begränsat läge, inklusive administratörer, ersätts av användarna i källmiljön.</span><span class="sxs-lookup"><span data-stu-id="c6263-159">All users in the target sandbox environment, including Administrators, are replaced by the users of the source environment.</span></span> <span data-ttu-id="c6263-160">Kontrollera att du är administratör i målmiljön innan du kopierar en instans.</span><span class="sxs-lookup"><span data-stu-id="c6263-160">Before you copy an instance, be sure that you're an Administrator in the target environment.</span></span> <span data-ttu-id="c6263-161">Om du inte är det kan du inte logga in till målmiljön efter att kopieringen har slutförts.</span><span class="sxs-lookup"><span data-stu-id="c6263-161">If you aren't, you won't be able to sign in to the target sandbox environment after the copy has completed.</span></span>

<span data-ttu-id="c6263-162">Alla användare som inte är administratörer i målmiljön i begränsat läge är inaktiverade för att förhindra oönskade inloggningar i miljön i begränsat läge.</span><span class="sxs-lookup"><span data-stu-id="c6263-162">All non-Administrator users in the target sandbox environment are disabled to prevent unwanted sign-ins in the sandbox environment.</span></span> <span data-ttu-id="c6263-163">Administratörer kan återaktivera användare om det behövs.</span><span class="sxs-lookup"><span data-stu-id="c6263-163">Administrators can reenable users if needed.</span></span>
