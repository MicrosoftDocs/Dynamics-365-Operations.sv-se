---
title: Självstudie för att ställa in och installera Regression Suite Automation Tool
description: Det här avsnittet innehåller en vägledning om hur du ställer in och installerar RSAT (Regression Suite Automation Tool).
author: kfend
manager: AnnBe
ms.date: 06/24/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 21761
ms.search.region: Global
ms.author: kfend
ms.search.validFrom: 2019-05-30
ms.dyn365.ops.version: AX 7.0.0, Operations
ms.openlocfilehash: e2287cb0281e920de219cb88d41cd69264911f93
ms.sourcegitcommit: 16bfa0fd08feec1647829630401ce62ce2ffa1a4
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/02/2019
ms.locfileid: "1850881"
---
# <a name="set-up-and-install-regression-suite-automation-tool-tutorial"></a><span data-ttu-id="0f737-103">Självstudie för att ställa in och installera Regression Suite Automation Tool</span><span class="sxs-lookup"><span data-stu-id="0f737-103">Set up and install Regression suite automation tool tutorial</span></span>
<span data-ttu-id="0f737-104">Det här avsnittet är en vägledning som hjälper dig att få installationsprogrammet och komma igång med RSAT och verktygen för att använda RSAT.</span><span class="sxs-lookup"><span data-stu-id="0f737-104">This topic is a tutorial that helps you get setup and get started with RSAT and the tools associated with using RSAT.</span></span> 

[!include [banner](../includes/banner.md)]

> [!NOTE]
> <span data-ttu-id="0f737-105">Använd webbläsarverktygen för att hämta och spara sidan i PDF-format.</span><span class="sxs-lookup"><span data-stu-id="0f737-105">Use your internet browser tools to download and save this page in PDF format.</span></span> 

## <a name="key-concepts"></a><span data-ttu-id="0f737-106">Viktiga begrepp</span><span class="sxs-lookup"><span data-stu-id="0f737-106">Key concepts</span></span>

- <span data-ttu-id="0f737-107">Förstå installationen och nödvändiga inställningar som krävs för de olika programmen som stöder RSAT (Regression Suite Automation Tool).</span><span class="sxs-lookup"><span data-stu-id="0f737-107">Understand the installation and prerequisite setup that are required for the various applications that support Regression suite automation tool (RSAT).</span></span>
- <span data-ttu-id="0f737-108">Förstå hur funktionen uppgiftsinspelare i Microsoft Dynamics 365 for Finance and Operations tillsammans med Microsoft Dynamics med Lifecycle Services (LCS) och Microsoft Azure DevOps, gör det möjligt att skapa, konfigurera, köra, undersöka och rapportera om testfall.</span><span class="sxs-lookup"><span data-stu-id="0f737-108">Understand how the Task recorder feature in Microsoft Dynamics 365 for Finance and Operations, together with Microsoft Dynamics Lifecycle Services (LCS) and Microsoft Azure DevOps, let you create, configure, run, investigate, and report on test cases.</span></span>
- <span data-ttu-id="0f737-109">Ge funktionella användare möjlighet att registrera affärsuppgifter med hjälp av uppgiftsregistrering i Finance and Operations och sedan konvertera inspelningsuppgifterna till en uppsättning automatiserade tester utan att källkoden behöver skrivas.</span><span class="sxs-lookup"><span data-stu-id="0f737-109">Empower functional users to record business tasks by using Task recorder in Finance and Operations, and then convert the task recordings into a suite of automated tests, without having to write source code.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="0f737-110">Innan du börjar</span><span class="sxs-lookup"><span data-stu-id="0f737-110">Before you begin</span></span>

### <a name="prerequisites"></a><span data-ttu-id="0f737-111">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="0f737-111">Prerequisites</span></span>

- <span data-ttu-id="0f737-112">En Finance and Operations-miljö som kör Microsoft Dynamics 365 for Finance and Operations version 10.0 (april 2019) eller senare krävs för den här självstudien.</span><span class="sxs-lookup"><span data-stu-id="0f737-112">A Finance and Operations environment that runs Microsoft Dynamics 365 for Finance and Operations version 10.0 (April 2019) or later is required for this tutorial.</span></span> <span data-ttu-id="0f737-113">För kunder som använder Microsoft Dynamics 365 for Finance and Operations Enterprise Edition 7.3, plattformsuppdatering 20 (PU20) eller senare stöds också.</span><span class="sxs-lookup"><span data-stu-id="0f737-113">For customers who are using Microsoft Dynamics 365 for Finance and Operations, Enterprise edition 7.3, Platform update 20 (PU20) or later is also supported.</span></span>
- <span data-ttu-id="0f737-114">Användaren måste ha administratörsrättigheter till Finance and Operations-miljö.</span><span class="sxs-lookup"><span data-stu-id="0f737-114">The user must have admin rights to the Finance and Operations environment.</span></span>
- <span data-ttu-id="0f737-115">Du måste ha tillgång till kundens LCS-klientorganisation och Azure DevOps (kallades tidigare Microsoft Visual Studio Team Services \[VSTS\]).</span><span class="sxs-lookup"><span data-stu-id="0f737-115">You must have access to the customer tenant LCS and Azure DevOps (previously known as Microsoft Visual Studio Team Services \[VSTS\]).</span></span>
- <span data-ttu-id="0f737-116">Användaren som skapar och hanterar testpaket måste ha en licens för Azure DevOps testplan eller testansvarig.</span><span class="sxs-lookup"><span data-stu-id="0f737-116">The user that is creating and managing tests suites must have an Azure DevOps Test Plans or Test Manager license.</span></span> <span data-ttu-id="0f737-117">Följande licenser kommer också att ge dig åtkomst till testplaner:</span><span class="sxs-lookup"><span data-stu-id="0f737-117">The following licenses will also give you access to Test Plans:</span></span>
    - <span data-ttu-id="0f737-118">Visual Studio Enterprise-licens</span><span class="sxs-lookup"><span data-stu-id="0f737-118">Visual Studio Enterprise license</span></span>
    - <span data-ttu-id="0f737-119">Visual Studio Test Professional-licens</span><span class="sxs-lookup"><span data-stu-id="0f737-119">Visual Studio Test Professional license</span></span>
    - <span data-ttu-id="0f737-120">Prenumerationslicens för MSDN-plattformar</span><span class="sxs-lookup"><span data-stu-id="0f737-120">MSDN Platforms subscriber license</span></span>
- <span data-ttu-id="0f737-121">RSAT måste ha åtkomst till testmiljön via en webbläsare.</span><span class="sxs-lookup"><span data-stu-id="0f737-121">RSAT must have access to the test environment via a web browser.</span></span>
- <span data-ttu-id="0f737-122">För att kunna generera och redigera testparametrar måste du ha Microsoft Excel installerat.</span><span class="sxs-lookup"><span data-stu-id="0f737-122">To generate and edit test parameters, you must have Microsoft Excel installed.</span></span>

## <a name="configure-azure-devops"></a><span data-ttu-id="0f737-123">Konfigurera Azure DevOps</span><span class="sxs-lookup"><span data-stu-id="0f737-123">Configure Azure DevOps</span></span>

### <a name="user-eligibility"></a><span data-ttu-id="0f737-124">Användarberättigande</span><span class="sxs-lookup"><span data-stu-id="0f737-124">User eligibility</span></span>

<span data-ttu-id="0f737-125">Se till att användaren har skapats i Azure DevOps och har en prenumerationsnivå som ger åtkomst till Azure testplaner.</span><span class="sxs-lookup"><span data-stu-id="0f737-125">Make sure that the user is created in Azure DevOps and has a subscription level that provides access to Azure Test Plans.</span></span> <span data-ttu-id="0f737-126">En Azure DevOps Test Plans-licens krävs endast om användaren ska skapa och hantera testfall (dvs. inte alla RSAT-användare behöver denna licens).</span><span class="sxs-lookup"><span data-stu-id="0f737-126">An Azure DevOps Test Plans license is required only if the user will create and manage test cases (that is, not all RSAT users require this license).</span></span> <span data-ttu-id="0f737-127">Mer information om licens kraven finns i [licenskrav](https://docs.microsoft.com/azure/devops/test/manual-test-permissions#license-requirements).</span><span class="sxs-lookup"><span data-stu-id="0f737-127">For information about the license requirements, see [License requirements](https://docs.microsoft.com/azure/devops/test/manual-test-permissions#license-requirements).</span></span>

### <a name="create-a-new-azure-devops-project"></a><span data-ttu-id="0f737-128">Skapa ett nytt Azure DevOps-projekt</span><span class="sxs-lookup"><span data-stu-id="0f737-128">Create a new Azure DevOps project</span></span>
<span data-ttu-id="0f737-129">I RSAT använder Azure DevOps för testfall och testpaket hantering, rapportering och undersöka testkörningsresultat.</span><span class="sxs-lookup"><span data-stu-id="0f737-129">RSAT uses Azure Devops for test case and test suite management, reporting, and investigating test run results.</span></span> 

> [!NOTE]
> <span data-ttu-id="0f737-130">Du kan använda ett befintligt Azure DevOps-projekt.</span><span class="sxs-lookup"><span data-stu-id="0f737-130">You can use an existing Azure DevOps project.</span></span> <span data-ttu-id="0f737-131">Om ditt befintliga Azure DevOps-projekt har konfigurerats så att det har en anpassad mall visas dock felmeddelandet "Fel vid VSTS-synkronisering" när du synkroniserar testfall från BPM (Affärsprocessmodelleraren) till Azure DevOps (se avsnittet [Testa synkroniseringen från BPM till Azure DevOps](#test-the-synchronization-from-bpm-to-azure-devops)).</span><span class="sxs-lookup"><span data-stu-id="0f737-131">However, if your existing Azure DevOps project is set up so that it has a custom template, you will receive a "VSTS Sync Failure" error when you sync test cases from Business process modeler (BPM) to Azure DevOps (see the [Test the synchronization from BPM to Azure DevOps](#test-the-synchronization-from-bpm-to-azure-devops) section).</span></span> <span data-ttu-id="0f737-132">Om följande metodtips har följts för den anpassade mallen kommer du att kunna synkronisera test fallen med Azure DevOps.</span><span class="sxs-lookup"><span data-stu-id="0f737-132">If the following best practices have been followed for the custom template, you will be able to sync the test cases to Azure DevOps.</span></span> <span data-ttu-id="0f737-133">(De här metodtipsen finns i felmeddelandet.)</span><span class="sxs-lookup"><span data-stu-id="0f737-133">(These best practices are listed in the error message.)</span></span>

- <span data-ttu-id="0f737-134">Ta inte bort några arbetsuppgiftstyper eller färdigkonfigurerade fält</span><span class="sxs-lookup"><span data-stu-id="0f737-134">Do not delete any work item types or out-of-the-box fields.</span></span>
- <span data-ttu-id="0f737-135">Ta inte bort något tillstånd för en arbetsuppgiftstyp</span><span class="sxs-lookup"><span data-stu-id="0f737-135">Do not delete any state of a work item type.</span></span>
- <span data-ttu-id="0f737-136">Lägg inte till några obligatoriska fält i en arbetsuppgiftstyp</span><span class="sxs-lookup"><span data-stu-id="0f737-136">Do not add any required fields to a work item type.</span></span>

![Felmeddelande med en lista över metodtips](./media/setup_rsa_tool_02.png)

<span data-ttu-id="0f737-138">I den här självstudien rekommenderar vi annars att du skapar ett nytt Azure DevOps-projekt.</span><span class="sxs-lookup"><span data-stu-id="0f737-138">Otherwise, for this tutorial, we recommend that you create a new Azure DevOps project.</span></span> <span data-ttu-id="0f737-139">Mer information finns i [frågor vid synkronisering till BPM med hjälp av en anpassad Azure DevOps (VSTS) processmall](https://blogs.msdn.microsoft.com/lcs/2018/11/28/issues-when-syncing-to-bpm-using-a-custom-azure-devops-vsts-process-template/).</span><span class="sxs-lookup"><span data-stu-id="0f737-139">For more information, see [Issues when syncing to BPM using a custom Azure DevOps (VSTS) process template](https://blogs.msdn.microsoft.com/lcs/2018/11/28/issues-when-syncing-to-bpm-using-a-custom-azure-devops-vsts-process-template/).</span></span>

1. <span data-ttu-id="0f737-140">Öppna Azure DevOps-URL (`https://dev.azure.com/<Azure DevOps Name>`).</span><span class="sxs-lookup"><span data-stu-id="0f737-140">Open the Azure DevOps URL (`https://dev.azure.com/<Azure DevOps Name>`).</span></span>
2. <span data-ttu-id="0f737-141">Klicka på knappen **Skapa projekt** längst upp till höger på Azure DevOps-sidan.</span><span class="sxs-lookup"><span data-stu-id="0f737-141">Select **Create project** in the upper-right corner of the Azure DevOps page.</span></span>

    ![Knappen Skapa projekt](./media/setup_rsa_tool_03.png)

3. <span data-ttu-id="0f737-143">Fyll i följande fält och välj sedan **skapa**:</span><span class="sxs-lookup"><span data-stu-id="0f737-143">Fill in the following fields, and then select **Create**:</span></span>

    - <span data-ttu-id="0f737-144">**Projektnamn**</span><span class="sxs-lookup"><span data-stu-id="0f737-144">**Project name**</span></span>
    - <span data-ttu-id="0f737-145">**Versionskontroll**  – Välj **Versionskontroll för Team Foundation**.</span><span class="sxs-lookup"><span data-stu-id="0f737-145">**Version control** – Select **Team Foundation Version Control**.</span></span> <span data-ttu-id="0f737-146">Observera att standardalternativet **Git** inte stöds.</span><span class="sxs-lookup"><span data-stu-id="0f737-146">Note that the default option, **Git**, isn't supported.</span></span>
    - <span data-ttu-id="0f737-147">**Arbetsuppgiftprocess**</span><span class="sxs-lookup"><span data-stu-id="0f737-147">**Work item process**</span></span>

    ![Dialogrutan skapa nytt projekt](./media/setup_rsa_tool_04.png)

### <a name="create-a-personal-access-token"></a><span data-ttu-id="0f737-149">Skapa ett token för personlig åtkomst</span><span class="sxs-lookup"><span data-stu-id="0f737-149">Create a personal access token</span></span>

<span data-ttu-id="0f737-150">I den här självstudien ska du använda LCS affärsprocessmodelleraren (BPM) för att skapa ett testfallsbibliotek och synkronisera dina testfall med Azure DevOps.</span><span class="sxs-lookup"><span data-stu-id="0f737-150">In this tutorial, you will use the LCS Business Process Modeler (BPM) to create a test case library and synchronize your test cases with Azure DevOps.</span></span> <span data-ttu-id="0f737-151">Du måste ha en personlig åtkomsttoken för att kunna synkronisera BPM med Azure DevOps.</span><span class="sxs-lookup"><span data-stu-id="0f737-151">You will need a personal access token to sync BPM with Azure DevOps.</span></span>

1. <span data-ttu-id="0f737-152">Välj en profilikon i det övre högra hörnet på sidan för Azure DevOps-projektet och välj sedan **säkerhet**.</span><span class="sxs-lookup"><span data-stu-id="0f737-152">Select the profile icon in the upper-right corner of the page for your Azure DevOps project, and then select **Security**.</span></span>

    ![Säkerhetskommando](./media/setup_rsa_tool_05.png)

2. <span data-ttu-id="0f737-154">Markera **personliga åtkomsttoken**i det vänstra fönstret under **säkerhet**.</span><span class="sxs-lookup"><span data-stu-id="0f737-154">In the left pane, under **Security**, select **Personal access tokens**.</span></span> <span data-ttu-id="0f737-155">Välj sedan **ny token**.</span><span class="sxs-lookup"><span data-stu-id="0f737-155">Then select **New Token**.</span></span>

    ![Knappen Ny token på fliken för personliga åtkomsttoken i användarinställningar](./media/setup_rsa_tool_06.png)

3. <span data-ttu-id="0f737-157">Fyll i följande fält och välj sedan **skapa**:</span><span class="sxs-lookup"><span data-stu-id="0f737-157">Fill in the following fields, and then select **Create**:</span></span>

    - <span data-ttu-id="0f737-158">**Namn**</span><span class="sxs-lookup"><span data-stu-id="0f737-158">**Name**</span></span>
    - <span data-ttu-id="0f737-159">**Förfallodatum (UTC**) – Välj **anpassad definierad och använd sedan datumväljaren för att välja det sista tillgängliga datumet**.</span><span class="sxs-lookup"><span data-stu-id="0f737-159">**Expiration (UTC)** – Select **Custom defined**, and then use the date picker to select the last available date.</span></span>
    - <span data-ttu-id="0f737-160">**Oområde** – Markera alternativet **fullständig åtkomst**.</span><span class="sxs-lookup"><span data-stu-id="0f737-160">**Scopes** – Select the **Full access** option.</span></span>

    ![Dialogrutan skapa en ny personlig åtkomsttoken](./media/setup_rsa_tool_07.png)

    > [!NOTE]
    > <span data-ttu-id="0f737-162">Anteckna vilken personlig åtkomsttoken som skapas.</span><span class="sxs-lookup"><span data-stu-id="0f737-162">Make a note of the personal access token that is created.</span></span> <span data-ttu-id="0f737-163">Du kommer att behöva det senare när du ställer in konfigurationen för RSAT.</span><span class="sxs-lookup"><span data-stu-id="0f737-163">You will need it later when you set up the RSAT configuration.</span></span>

    ![Token för personlig åtkomst](./media/setup_rsa_tool_08.png)

## <a name="configure-the-lcs-project"></a><span data-ttu-id="0f737-165">Konfigurera LCS-projekt</span><span class="sxs-lookup"><span data-stu-id="0f737-165">Configure the LCS project</span></span>

<span data-ttu-id="0f737-166">Du behöver ett LCS-projekt (Lifecycle Services) för ditt huvudtestbibliotek.</span><span class="sxs-lookup"><span data-stu-id="0f737-166">You need a Lifecycle Services (LCS) project for your master test library.</span></span> <span data-ttu-id="0f737-167">LCS affärsprocessmodelleraren (BPM) används som huvudbibliotek för testfallen.</span><span class="sxs-lookup"><span data-stu-id="0f737-167">The LCS Business Process Modeler (BPM) is used as the master library for your test cases.</span></span> <span data-ttu-id="0f737-168">BPM används för att hantera och distribuera testbibliotek över LCS-projekt.</span><span class="sxs-lookup"><span data-stu-id="0f737-168">BPM is used to manage and distribute test libraries across LCS projects.</span></span> <span data-ttu-id="0f737-169">En Microsoft-partner eller en oberoende programleverantör (ISV) för att skapa testbibliotek frigörs till exempel testfall i form av BPM-bibliotek.</span><span class="sxs-lookup"><span data-stu-id="0f737-169">For example, a Microsoft partner or independent software vendor (ISV) building test libraries will release test cases in the form of BPM libraries.</span></span> <span data-ttu-id="0f737-170">I BPM är testfall organiserade efter affärsprocess.</span><span class="sxs-lookup"><span data-stu-id="0f737-170">In BPM, test cases are organized by business process.</span></span> <span data-ttu-id="0f737-171">BPM definierar inte körningsordningen eller frekvensen för testpass.</span><span class="sxs-lookup"><span data-stu-id="0f737-171">BPM doesn't define the execution order or frequency of your test pass.</span></span> <span data-ttu-id="0f737-172">Dessa detaljer hanteras i Azure DevOps vilket beskrivs mer utförligt i detta ämne.</span><span class="sxs-lookup"><span data-stu-id="0f737-172">These details are managed in Azure DevOps, as described later in this topic.</span></span>  

<span data-ttu-id="0f737-173">För det LCS-projektet kan du använda ett befintligt implementerings- eller partnerprojekt för kund.</span><span class="sxs-lookup"><span data-stu-id="0f737-173">For your LCS project, you can use an existing customer implementation or partner project.</span></span>

### <a name="update-the-lcs-language"></a><span data-ttu-id="0f737-174">Uppdatera LCS-språk</span><span class="sxs-lookup"><span data-stu-id="0f737-174">Update the LCS language</span></span>

> [!NOTE]
> <span data-ttu-id="0f737-175">För användargränssnittet (UI) för att visa affärsprocesser korrekt måste LCS föredraget språk vara **engelska (USA)**.</span><span class="sxs-lookup"><span data-stu-id="0f737-175">For the user interface (UI) to correctly show business processes, the LCS preferred language must be set to **English (United States)**.</span></span>

1. <span data-ttu-id="0f737-176">Gå till själva LCS-implementeringsprojektet.</span><span class="sxs-lookup"><span data-stu-id="0f737-176">Go to the LCS implementation project.</span></span>
2. <span data-ttu-id="0f737-177">Välj knappen **inställningar** (växelsymbol) i det övre högra hörnet och välj sedan **Språkinställning**.</span><span class="sxs-lookup"><span data-stu-id="0f737-177">Select the **Settings** button (the gear symbol) in the upper-right corner, and then select **Language preference**.</span></span>

    ![Kommandon på menyn Inställningar](./media/setup_rsa_tool_09.png)

3. <span data-ttu-id="0f737-179">I fältet **Föredraget språk**, välj **engelska (USA)** och välj sedan **Spara**.</span><span class="sxs-lookup"><span data-stu-id="0f737-179">In the **Preferred language** field, select **English (United States)**, and then select **Save**.</span></span>

    ![Fliken språkinställningar i användarinställningar](./media/setup_rsa_tool_10.png)

### <a name="configure-lcs-to-connect-to-the-azure-devops-project"></a><span data-ttu-id="0f737-181">Konfigurera LCS för att ansluta till Azure DevOps-projektet</span><span class="sxs-lookup"><span data-stu-id="0f737-181">Configure LCS to connect to the Azure DevOps project</span></span>

<span data-ttu-id="0f737-182">Om du skapade ett nytt Azure DevOps-projekt tidigare konfigurerar du LCS-projektet så att du kan ansluta till det.</span><span class="sxs-lookup"><span data-stu-id="0f737-182">If you created a new Azure DevOps project earlier, configure the LCS project to connect to it.</span></span> <span data-ttu-id="0f737-183">Om LCS-projektet redan är anslutet till ditt Azure DevOps-projekt kan du fortsätta till nästa avsnitt.</span><span class="sxs-lookup"><span data-stu-id="0f737-183">Otherwise, if your LCS project is already connected to your Azure DevOps project, you can continue to the next section.</span></span>

1. <span data-ttu-id="0f737-184">Gå till själva LCS-implementeringsprojektet.</span><span class="sxs-lookup"><span data-stu-id="0f737-184">Go to the LCS implementation project.</span></span>
2. <span data-ttu-id="0f737-185">Välj knappen **meny** och välj sedan **projektinställningar**.</span><span class="sxs-lookup"><span data-stu-id="0f737-185">Select the **Menu** button, and then select **Project settings**.</span></span>

    ![Projektinställningskommando](./media/setup_rsa_tool_11.png)

3. <span data-ttu-id="0f737-187">Markera **Visual Studio Team Services** i det vänstra fönstret och välj sedan **konfigurera Visual Studio Team Services**.</span><span class="sxs-lookup"><span data-stu-id="0f737-187">In the left pane, select **Visual Studio Team Services**, and then select **Setup Visual Studio Team Services**.</span></span>

    ![Fliken Visual Studio Team Services i projektinställningar](./media/setup_rsa_tool_12.png)

4. <span data-ttu-id="0f737-189">Ange **Azure DevOps webbplatsens URL** i fältet Azure DevOps webbplats-URL.</span><span class="sxs-lookup"><span data-stu-id="0f737-189">In the **Azure DevOps site URL** field, enter the URL of the Azure DevOps site.</span></span> <span data-ttu-id="0f737-190">I fältet **personlig åtkomsttoken** anger du den personliga åtkomsttoken som skapades tidigare.</span><span class="sxs-lookup"><span data-stu-id="0f737-190">In the **Personal access token** field, enter the personal access token that was created earlier.</span></span>

    > [!NOTE]
    > <span data-ttu-id="0f737-191">Ãven om VSTS nu kallas Azure DevOps kan du använda den gamla URL för att ansluta LCS till Azure DevOps-projektet.</span><span class="sxs-lookup"><span data-stu-id="0f737-191">Although VSTS is now known as Azure DevOps, to connect LCS to your Azure DevOps project, use the old URL.</span></span> <span data-ttu-id="0f737-192">Till exempel den Azure DevOps-URL som används i den här självstudien är `https://dev.azure.com/D365FOFastTrack/`.</span><span class="sxs-lookup"><span data-stu-id="0f737-192">For example, the Azure DevOps URL that is used in this tutorial is `https://dev.azure.com/D365FOFastTrack/`.</span></span> <span data-ttu-id="0f737-193">I följande illustration är det dock angivet som `https://D365FOFastTrack.visualstudio.com/`.</span><span class="sxs-lookup"><span data-stu-id="0f737-193">However, in the following illustration, it's entered as `https://D365FOFastTrack.visualstudio.com/`.</span></span>

    ![Steg 1 i Konfigurera Visual Studio Team Services](./media/setup_rsa_tool_13.png)

5. <span data-ttu-id="0f737-195">Välj **Fortsätt**.</span><span class="sxs-lookup"><span data-stu-id="0f737-195">Select **Continue**.</span></span>
6. <span data-ttu-id="0f737-196">I fältet **Visual Studio Team Services-projekt** väljer du det VSTS-projekt på den valda webbplatsen för att koppla med LCS-projekt.</span><span class="sxs-lookup"><span data-stu-id="0f737-196">In the **Visual Studio Team Services project** field, select the VSTS project on the selected site to link with the LCS project.</span></span> <span data-ttu-id="0f737-197">Som standard anges fältet **processmall** till **Agile**.</span><span class="sxs-lookup"><span data-stu-id="0f737-197">The **Process template** field is set to **Agile** by default.</span></span> <span data-ttu-id="0f737-198">Om du vill ha en anpassad mall ska du läsa metodtipsen i avsnittet [Skapa ett nytt Azure DevOps-projekt](#create-a-new-azure-devops-project).</span><span class="sxs-lookup"><span data-stu-id="0f737-198">For a custom template, review the best practice guidance in the [Create a new Azure DevOps project](#create-a-new-azure-devops-project) section.</span></span> <span data-ttu-id="0f737-199">Välj sedan **Fortsätt**.</span><span class="sxs-lookup"><span data-stu-id="0f737-199">Then select **Continue**.</span></span>

    ![Steg 2 i Konfigurera Visual Studio Team Services](./media/setup_rsa_tool_14.png)

7. <span data-ttu-id="0f737-201">Granska inställningarna och välj sedan **Spara**.</span><span class="sxs-lookup"><span data-stu-id="0f737-201">Review your settings, and then select **Save**.</span></span>

    ![Steg 3 i Konfigurera Visual Studio Team Services](./media/setup_rsa_tool_15.png)

8. <span data-ttu-id="0f737-203">Välj **Auktorisera** för att auktorisera LCS för åtkomst till den konfigurerade Azure DevOps-platsen för din räkning och aktivera funktioner som är integrerade med VSTS.</span><span class="sxs-lookup"><span data-stu-id="0f737-203">Select **Authorize** to authorize LCS to access the configured Azure DevOps site on your behalf and to turn on features that integrate with VSTS.</span></span>

    ![Knappen auktorisera](./media/setup_rsa_tool_16.png)

9. <span data-ttu-id="0f737-205">En meddelanderutan visas som anger: Du omdirigeras till en extern webbplats för en att ge LCS behörighet att ansluta till Visual Studio Team Services för din räkning.</span><span class="sxs-lookup"><span data-stu-id="0f737-205">A message box appears that states, "You are about to be redirected to an eternal site to authorize LCS to connect to Visual Studio Team Services on your behalf.</span></span> <span data-ttu-id="0f737-206">Villl du fortsätta?</span><span class="sxs-lookup"><span data-stu-id="0f737-206">Proceed?"</span></span> <span data-ttu-id="0f737-207">Välj **Ja**.</span><span class="sxs-lookup"><span data-stu-id="0f737-207">Select **Yes**.</span></span>

    ![Meddelanderuta](./media/setup_rsa_tool_17.png)

10. <span data-ttu-id="0f737-209">Välj **Godkänn**.</span><span class="sxs-lookup"><span data-stu-id="0f737-209">Select **Accept**.</span></span>

    ![Auktorisera åtkomst](./media/setup_rsa_tool_18.png)

11. <span data-ttu-id="0f737-211">Om du är auktoriserad som användare ska du gå tillbaka till sidan LCS-projektinställningar.</span><span class="sxs-lookup"><span data-stu-id="0f737-211">If you're authorized as a user, the UI should you return to the LCS project settings page.</span></span>

    ![Behöriga användare](./media/setup_rsa_tool_19.png)

### <a name="create-a-new-bpm-library"></a><span data-ttu-id="0f737-213">Skapa ett nytt BPM-bibliotek</span><span class="sxs-lookup"><span data-stu-id="0f737-213">Create a new BPM library</span></span>

1. <span data-ttu-id="0f737-214">Gå till själva LCS-implementeringsprojektet.</span><span class="sxs-lookup"><span data-stu-id="0f737-214">Go to the LCS implementation project.</span></span>
2. <span data-ttu-id="0f737-215">Välj knappen **meny** och välj sedan **affärsprocessmodelleraren**.</span><span class="sxs-lookup"><span data-stu-id="0f737-215">Select the **Menu** button, and then select **Business process modeler**.</span></span>

    ![Kommandot Affärsprocessmodelleraren](./media/setup_rsa_tool_20.png)

3. <span data-ttu-id="0f737-217">Välj ett **Nytt bibliotek**.</span><span class="sxs-lookup"><span data-stu-id="0f737-217">Select **New library**.</span></span>

    ![Knappen Nytt bibliotek](./media/setup_rsa_tool_21.png)

4. <span data-ttu-id="0f737-219">I fältet **biblioteksnamn** anger du ett namn och väljer sedan **skapa**.</span><span class="sxs-lookup"><span data-stu-id="0f737-219">In the **Library name** field, enter a name, and then select **Create**.</span></span> <span data-ttu-id="0f737-220">I den här självstudien namnger du BPM-biblioteket **RSAT**.</span><span class="sxs-lookup"><span data-stu-id="0f737-220">For this tutorial, name the BPM library **RSAT**.</span></span>

    ![Dialogrutan skapa nytt bibliotek](./media/setup_rsa_tool_22.png)

5. <span data-ttu-id="0f737-222">Öppna det nya BMP-biblioteket för **BPM**.</span><span class="sxs-lookup"><span data-stu-id="0f737-222">Open the new **RSAT** BPM library.</span></span>
6. <span data-ttu-id="0f737-223">Välj affärsprocessen **Sample Core Business Process** och välj **redigeringsläge** till höger.</span><span class="sxs-lookup"><span data-stu-id="0f737-223">Select the **Sample Core Business Process** process, and then, on the right, select **Edit mode**.</span></span>

    ![Knappen Redigeringsläge](./media/setup_rsa_tool_23.png)

7. <span data-ttu-id="0f737-225">Ändra värdet för både fältet **Namn** och fältet **Beskrivning** för att **skapa en produkt**.</span><span class="sxs-lookup"><span data-stu-id="0f737-225">Change the value of both the **Name** field and the **Description** field to **Create a product**.</span></span> <span data-ttu-id="0f737-226">Välj sedan **Spara**.</span><span class="sxs-lookup"><span data-stu-id="0f737-226">Then select **Save**.</span></span>

    ![Fälten namn och beskrivning](./media/setup_rsa_tool_24.png)

## <a name="finance-and-operations-environment"></a><span data-ttu-id="0f737-228">Finance and Operations-miljön</span><span class="sxs-lookup"><span data-stu-id="0f737-228">Finance and Operations environment</span></span>

### <a name="version-requirement"></a><span data-ttu-id="0f737-229">Versionskrav</span><span class="sxs-lookup"><span data-stu-id="0f737-229">Version requirement</span></span>

<span data-ttu-id="0f737-230">Ett test- eller begränsat läge-miljö som kör version 10 krävs för ett Finance and Operations-test.</span><span class="sxs-lookup"><span data-stu-id="0f737-230">A Finance and Operations test or sandbox environment that runs version 10 is required.</span></span> <span data-ttu-id="0f737-231">För kunder som använder version 7.3, plattformsuppdatering 20 eller senare stöds också.</span><span class="sxs-lookup"><span data-stu-id="0f737-231">For customers that are using version 7.3, Platform update 20 or later is also supported.</span></span>

> [!NOTE]
> <span data-ttu-id="0f737-232">RSAT måste ha åtkomst till Finance and Operations-testmiljön via en webbläsare.</span><span class="sxs-lookup"><span data-stu-id="0f737-232">RSAT must have access to your Finance and Operations test environment via a web browser.</span></span>

### <a name="user-criteria"></a><span data-ttu-id="0f737-233">Användarkriterier</span><span class="sxs-lookup"><span data-stu-id="0f737-233">User criteria</span></span>

<span data-ttu-id="0f737-234">Användaren måste ha administratörsbehörighet till den här miljön.</span><span class="sxs-lookup"><span data-stu-id="0f737-234">The user must have admin rights to this environment.</span></span>

### <a name="set-up-help-settings-to-connect-with-lcs"></a><span data-ttu-id="0f737-235">Konfigurera hjälpinställningar för anslutning med LCS</span><span class="sxs-lookup"><span data-stu-id="0f737-235">Set up Help settings to connect with LCS</span></span>

<span data-ttu-id="0f737-236">Det här steget krävs för att ansluta med LCS så att uppgiftsregistreringar kan sparas i lämpligt BPM-bibliotek i LCS via Finance and Operations-klienten.</span><span class="sxs-lookup"><span data-stu-id="0f737-236">This step is required in order to connect with LCS so that task recordings can be saved to the appropriate BPM library in LCS through the Finance and Operations client.</span></span>

1. <span data-ttu-id="0f737-237">Öppna Finance and Operations-klienten</span><span class="sxs-lookup"><span data-stu-id="0f737-237">Open the Finance and Operations client.</span></span>
2. <span data-ttu-id="0f737-238">Navigera till **Systemadministration \> Inställningar \> Systemparametrar**.</span><span class="sxs-lookup"><span data-stu-id="0f737-238">Go to **System Administration \> Setup \> System parameters**.</span></span>
3. <span data-ttu-id="0f737-239">På fliken **Hjälp** i fältet **Hjälpkonfiguration för Lifecycle Services**, välj relevant LCS-projekt (**RSAT** för denna självstudie).</span><span class="sxs-lookup"><span data-stu-id="0f737-239">On the **Help** tab, in the **Lifecycle Services help configuration** field, select the relevant LCS project (**RSAT** for this tutorial).</span></span>

    ![Lifecycle Services hjälper konfigurationsfält på fliken Hjälp](./media/setup_rsa_tool_25.png)

    <span data-ttu-id="0f737-241">BPM-bibliotek fylls i under lämpligt LCS-projekt.</span><span class="sxs-lookup"><span data-stu-id="0f737-241">BPM libraries are filled in under the appropriate LCS project.</span></span>

4. <span data-ttu-id="0f737-242">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="0f737-242">Select **Save**.</span></span>
5. <span data-ttu-id="0f737-243">Du kanske måste uppdatera webbläsaren för att kunna se det uppdaterade hjälpinnehållet.</span><span class="sxs-lookup"><span data-stu-id="0f737-243">You might have to refresh the browser to see the updated Help content.</span></span>

    ![Meddelande om uppdatering av webbläsaren](./media/setup_rsa_tool_26.png)

## <a name="task-recordings"></a><span data-ttu-id="0f737-245">Uppgiftsinspelningar</span><span class="sxs-lookup"><span data-stu-id="0f737-245">Task recordings</span></span>

> [!NOTE]
> <span data-ttu-id="0f737-246">Kontrollera att alla uppgiftsinspelningar startar på huvudinstrumentpanelen i Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="0f737-246">Make sure that all your task recordings start on the main dashboard of Finance and Operations.</span></span> <span data-ttu-id="0f737-247">Hålla enskilda inspelningar korta och fokusera på en affärsuppgift, t.ex. skapa en försäljningsorder.</span><span class="sxs-lookup"><span data-stu-id="0f737-247">Keep individual recordings short, and focus on one business task, such as creating a sales order.</span></span>

### <a name="create-a-task-recording-and-save-it-to-the-bpm-library"></a><span data-ttu-id="0f737-248">Skapa en uppgiftsinspelning och spara den i BPM-biblioteket</span><span class="sxs-lookup"><span data-stu-id="0f737-248">Create a task recording and save it to the BPM library</span></span>

<span data-ttu-id="0f737-249">Skapa en motsvarande uppgiftsinspelning som du kan koppla till den enkla affärsprocess som skapades i det nya BPM-biblioteket.</span><span class="sxs-lookup"><span data-stu-id="0f737-249">Create a corresponding task recording that you can attach to the simple business process that was created in the new BPM library.</span></span>

1. <span data-ttu-id="0f737-250">Öppna Finance and Operations-klienten</span><span class="sxs-lookup"><span data-stu-id="0f737-250">Open the Finance and Operations client.</span></span>
2. <span data-ttu-id="0f737-251">Välj knappen **inställningar** (växelsymbolen) och sedan **Uppgiftsinspelare**.</span><span class="sxs-lookup"><span data-stu-id="0f737-251">On the main dashboard, select the **Settings** button (the gear symbol), and then select **Task recorder**.</span></span>

    ![Kommandon på menyn Inställningar](./media/setup_rsa_tool_27.png)

3. <span data-ttu-id="0f737-253">Välj **Skapa registrering**.</span><span class="sxs-lookup"><span data-stu-id="0f737-253">Select **Create recording**.</span></span>

    ![Knappen Skapa registrering](./media/setup_rsa_tool_28.png)

4. <span data-ttu-id="0f737-255">Fyll i fälten **inspelningsnamn** och **inspelningsbeskrivning** och välj sedan **starta**.</span><span class="sxs-lookup"><span data-stu-id="0f737-255">Fill in the **Recording name** and **Recording description** fields, and then select **Start**.</span></span>

    ![Fälten Inspelningens namn och Inspelningens beskrivning.](./media/setup_rsa_tool_29.png)

5. <span data-ttu-id="0f737-257">Registrera stegen för att skapa en produkt.</span><span class="sxs-lookup"><span data-stu-id="0f737-257">Record the steps for creating a product.</span></span> <span data-ttu-id="0f737-258">När du är klar väljer du **stoppa** om du vill stoppa inspelningen.</span><span class="sxs-lookup"><span data-stu-id="0f737-258">When you've finished, select **Stop** to stop recording.</span></span>

    ![Steg för att skapa en produkt](./media/setup_rsa_tool_30.png)

6. <span data-ttu-id="0f737-260">Välj **Spara till Lifecycle Services**.</span><span class="sxs-lookup"><span data-stu-id="0f737-260">Select **Save to Lifecycle Services**.</span></span>

    ![Alternativ för spara](./media/setup_rsa_tool_31.png)

    <span data-ttu-id="0f737-262">Biblioteksinformationen läses in från LCS.</span><span class="sxs-lookup"><span data-stu-id="0f737-262">Library information is loaded from LCS.</span></span>

    ![Förloppsindikator](./media/setup_rsa_tool_32.png)

7. <span data-ttu-id="0f737-264">Välj BPM-bibliotek som ska associeras med uppgiftsinspelningen.</span><span class="sxs-lookup"><span data-stu-id="0f737-264">Select the BPM library to associate the task recording with.</span></span> <span data-ttu-id="0f737-265">För den här självstudien väljer du **RSAT** BPM-biblioteket, som skapades tidigare och affärsprocessen **Skapa en produkt** under det.</span><span class="sxs-lookup"><span data-stu-id="0f737-265">For this tutorial, select the **RSAT** BPM library that was created earlier and the **Create a product** business process under it.</span></span> <span data-ttu-id="0f737-266">Välj sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="0f737-266">Then select **OK**.</span></span>

    ![Associera en uppgiftsinspelning med ett BPM-bibliotek och en affärsprocess](./media/setup_rsa_tool_33.png)

    <span data-ttu-id="0f737-268">Meddelandet Spara till Lifecycle Services slutfördes visas.</span><span class="sxs-lookup"><span data-stu-id="0f737-268">A "Saving to Lifecycle Services was successful" message appears.</span></span>

    ![Meddelande om lyckad sparning till LCS](./media/setup_rsa_tool_34.png)

8. <span data-ttu-id="0f737-270">Gör så här om du vill spara uppgiftsinspelningen lokalt och sedan överföra den till BPM via LCS:</span><span class="sxs-lookup"><span data-stu-id="0f737-270">If you want to save the task recording locally and then upload it to BPM through LCS, follow these steps:</span></span>

    1. <span data-ttu-id="0f737-271">När inspelningen har slutförts väljer su **Spara på den här datorn**.</span><span class="sxs-lookup"><span data-stu-id="0f737-271">After the recording is completed, select **Save to this PC**.</span></span>

        ![Alternativ för spara](./media/setup_rsa_tool_35.png)

    2. <span data-ttu-id="0f737-273">I webbläsarens meddelandefält väljer du **Spara** eller **Spara som** om du vill spara filen på den lokala datorn.</span><span class="sxs-lookup"><span data-stu-id="0f737-273">In the browser's Notification bar, select **Save** or **Save As** to save the file on your local computer.</span></span>

        ![Meddelandefält](./media/setup_rsa_tool_36.png)

    3. <span data-ttu-id="0f737-275">Gå till **RSAT** BPM-biblioteket och välj den affärsprocess som du vill spara uppgiftsinspelningen mot.</span><span class="sxs-lookup"><span data-stu-id="0f737-275">Go to the **RSAT** BPM library, and select the business process to save the task recording against.</span></span>
    4. <span data-ttu-id="0f737-276">På fliken **översikt** väljer du **överför**.</span><span class="sxs-lookup"><span data-stu-id="0f737-276">On the **Overview** tab, select **Upload**.</span></span>

        ![Knappen Överför](./media/setup_rsa_tool_37.png)

    5. <span data-ttu-id="0f737-278">Välj **bläddra**och markera den .axtr-fil som du sparade tidigare.</span><span class="sxs-lookup"><span data-stu-id="0f737-278">Select **Browse**, and select the .axtr file that you saved earlier.</span></span> <span data-ttu-id="0f737-279">Välj sedan **överför**.</span><span class="sxs-lookup"><span data-stu-id="0f737-279">Then select **Upload**.</span></span>

        ![Välja vilken .axtr-fil som ska överföras](./media/setup_rsa_tool_38.png)

### <a name="test-the-synchronization-from-bpm-to-azure-devops"></a><span data-ttu-id="0f737-281">Testa synkroniseringen från BPM till Azure DevOps</span><span class="sxs-lookup"><span data-stu-id="0f737-281">Test the synchronization from BPM to Azure DevOps</span></span>

<span data-ttu-id="0f737-282">Nu när en uppgiftsinspelning är kopplad till affärsprocessen måste du validera att affärsprocessen och den tillhör ande uppgiftsinspelningen kan synkroniseras till Azure DevOps som en funktion och ett testfall med hjälp av VSTS-synkroniseringsfunktionen i LCS.</span><span class="sxs-lookup"><span data-stu-id="0f737-282">Now that a task recording is attached to the business process, you must validate that the business process and the associated task recording can be synced to Azure DevOps as a feature and a test case (respectively) by using the VSTS sync feature in LCS.</span></span>

> [!NOTE]
> <span data-ttu-id="0f737-283">Motsvarande arbetsuppgiftstyp som skapades i Azure DevOpsvarierar beroende på vilken procesmall du valde när du konfigurerade LCS-projektet med Azure DevOps, som beskrivs i avsnittet [skapa ett nytt Azure DevOps-projekt](#create-a-new-azure-devops-project).</span><span class="sxs-lookup"><span data-stu-id="0f737-283">The corresponding work item type that is created in Azure DevOps will vary, depending on the process template that you selected when you configured the LCS project with Azure DevOps, as described in the [Create a new Azure DevOps project](#create-a-new-azure-devops-project) section.</span></span>

1. <span data-ttu-id="0f737-284">Gå till BPM-biblioteket och öppna det **RSAT**-bibliotek som du skapade tidigare.</span><span class="sxs-lookup"><span data-stu-id="0f737-284">Go to the BPM library, and open the **RSAT** library that you created earlier.</span></span>
2. <span data-ttu-id="0f737-285">Markera ellips-knappen (**...**) och välj **VSTS-synkronsiering**.</span><span class="sxs-lookup"><span data-stu-id="0f737-285">Select the ellipsis button (**...**), and select **VSTS sync**.</span></span>

    ![Kommandot VSTS-synkronsiering på ellips-menyn](./media/setup_rsa_tool_39.png)

    <span data-ttu-id="0f737-287">När VSTS-synkroniseringen är slutförd visas fliken **krav** på vänster sida och innehåller motsvarande Azure DevOps-arbetsuppgift.</span><span class="sxs-lookup"><span data-stu-id="0f737-287">After VSTS sync is completed, a **Requirements** tab appears on the left side and includes the corresponding Azure DevOps work item.</span></span>

    > [!NOTE]
    > <span data-ttu-id="0f737-288">Arbetsuppgiften som skapas i Azure DevOps kommer att ha BPM-biblioteksnamnet som rubrikprefix.</span><span class="sxs-lookup"><span data-stu-id="0f737-288">The work item that is created in Azure DevOps will have the BPM library name as the title prefix.</span></span>

    ![Fliken Krav](./media/setup_rsa_tool_40.png)

3. <span data-ttu-id="0f737-290">Uppdatera sidan.</span><span class="sxs-lookup"><span data-stu-id="0f737-290">Refresh the page.</span></span>
4. <span data-ttu-id="0f737-291">Markera ellips-knappen (**...**). Du kommer att se ett ytterligare alternativ **Synkronisera testfall**.</span><span class="sxs-lookup"><span data-stu-id="0f737-291">Select the ellipsis button (**...**). You will see an additional option, **Sync test cases**.</span></span> <span data-ttu-id="0f737-292">Välj det här alternativet .</span><span class="sxs-lookup"><span data-stu-id="0f737-292">Select this option.</span></span>

    ![Kommandot synkronisera testfall på ellips-menyn](./media/setup_rsa_tool_41.png)

    > [!NOTE]
    > <span data-ttu-id="0f737-294">Om alternativet **synkronisera testfall** inte är tillgängligt när du har uppdaterat sidan går du till huvudsidan för BPM och väljer **synkronisera testfall** för hela biblioteket.</span><span class="sxs-lookup"><span data-stu-id="0f737-294">If the **Sync test cases** option isn't available after you refresh the page, go to main page for BPM, and select **Sync test cases** for the whole library itself.</span></span> <span data-ttu-id="0f737-295">På så sätt framtvingar du effektivt en synkronisering av hela biblioteket.</span><span class="sxs-lookup"><span data-stu-id="0f737-295">In this way, you effectively force a synchronization for the whole library.</span></span>
    > 
    > ![Välja synkronisering av testfall för hela biblioteket](./media/setup_rsa_tool_42.png)

    <span data-ttu-id="0f737-297">När synkroniseringen av testfall hargjorts skapas ett nytt testfall på fliken **krav**.</span><span class="sxs-lookup"><span data-stu-id="0f737-297">After Sync test cases is completed, a new test case is created on the **Requirements** tab.</span></span>

    ![Nytt testfall på fliken Krav](./media/setup_rsa_tool_43.png)

5. <span data-ttu-id="0f737-299">Gå till Azure DevOps-projektet och välj **Tavlor \> Arbetsuppgifter**.</span><span class="sxs-lookup"><span data-stu-id="0f737-299">Go to your Azure DevOps project, and select **Boards \> Work Items**.</span></span>

    ![Kommandot arbetsuppgifter under tavlor](./media/setup_rsa_tool_44.png)

6. <span data-ttu-id="0f737-301">Validera att arbetsuppgiften och testfallet som du skapade genom BPM-synkronisering finns.</span><span class="sxs-lookup"><span data-stu-id="0f737-301">Validate that the work item and test case that you created through BPM synchronization exist.</span></span>

    ![Arbetsuppgift och testfall](./media/setup_rsa_tool_45.png)

## <a name="install-and-configure-rsat"></a><span data-ttu-id="0f737-303">Installera och konfigurera RSAT</span><span class="sxs-lookup"><span data-stu-id="0f737-303">Install and Configure RSAT</span></span>

<span data-ttu-id="0f737-304">RSAT kan installeras på alla datorer som kör Windows 10 och som kan ansluta till Finance and Operations-miljö via en webbläsare (Internet Explorer eller Google Chrome).</span><span class="sxs-lookup"><span data-stu-id="0f737-304">RSAT can be installed on any computer that runs Windows 10 and that can connect to the Finance and Operations environment via a web browser (Internet Explorer or Google Chrome).</span></span>

> [!NOTE]
> <span data-ttu-id="0f737-305">Innan du installerar en ny version av verktyget rekommenderar vi att du avinstallerar den tidigare versionen.</span><span class="sxs-lookup"><span data-stu-id="0f737-305">Before you install a new version of the tool, we recommend that you uninstall the previous version.</span></span>

### <a name="install-an-authentication-certificate"></a><span data-ttu-id="0f737-306">Installera ett autentiseringscertifikat</span><span class="sxs-lookup"><span data-stu-id="0f737-306">Install an authentication certificate</span></span>

<span data-ttu-id="0f737-307">Om du vill aktivera autentisering måste du generera och installera ett certifikat på samma dator som RSAT körs på.</span><span class="sxs-lookup"><span data-stu-id="0f737-307">To enable authentication, you must generate and install a certificate on the same computer that RSAT is running on.</span></span>

#### <a name="generate-a-certificate"></a><span data-ttu-id="0f737-308">Generera ett certifikat</span><span class="sxs-lookup"><span data-stu-id="0f737-308">Generate a certificate</span></span>

1. <span data-ttu-id="0f737-309">Om du vill generera en certifikatfil öppnar du Microsoft Windows PowerShell-fönster som administratör och kör följande kommando.</span><span class="sxs-lookup"><span data-stu-id="0f737-309">To generate a certificate file, open a Microsoft Windows PowerShell window as an admin, and run the following command.</span></span>

    ```
    $certificate = New-SelfSignedCertificate -dnsname 127.0.0.1 -CertStoreLocation cert:\LocalMachine\My -FriendlyName "D365 Automated testing certificate" -Provider "Microsoft Strong Cryptographic Provider"
    ```

2. <span data-ttu-id="0f737-310">Öppna certifikathanterare genom att ange **certlm.msc** i dialogrutan **Kör** och bekräfta attcertifikatet **D365-automatiserad testning** har skapats under **personliga \> certifikat**.</span><span class="sxs-lookup"><span data-stu-id="0f737-310">Open certificate manager by entering **certlm.msc** in the **Run** dialog box, and confirm that the **D365 Automated testing certificate** certificate is created under **Personal \> Certificates**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="0f737-311">Glöm inte att ange **certlm.msc**, inte **certmgr.msc**, eftersom certifikaten lagras på den lokala datorn.</span><span class="sxs-lookup"><span data-stu-id="0f737-311">Be sure to enter **certlm.msc**, not **certmgr.msc**, because the certificates are stored on the local computer.</span></span>

    ![D365 för automatisk testning av certifikat](./media/setup_rsa_tool_46.png)

3. <span data-ttu-id="0f737-313">Högerklicka i certifikatet och välj sedan **Kopiera**.</span><span class="sxs-lookup"><span data-stu-id="0f737-313">Right-click the certificate, and then select **Copy**.</span></span>
4. <span data-ttu-id="0f737-314">Gå till **certifikat till betrodda rotcertifikatutfärdare \> certifikat**.</span><span class="sxs-lookup"><span data-stu-id="0f737-314">Go to **Trusted Root Certification Authorities \> Certificates**.</span></span>

    ![Mappen Certifikat under mappen Betrodda rotcertifikatutfärdare](./media/setup_rsa_tool_47.png)

5. <span data-ttu-id="0f737-316">På menyn **Åtgärd**, välj **Klistra in** om du vill kopiera certifikatet till platsen **certifikat till betrodda rotcertifikatutfärdare**.</span><span class="sxs-lookup"><span data-stu-id="0f737-316">On the **Action** menu, select **Paste** to copy the certificate to the **Trusted Root Certification Authorities** location.</span></span>

    ![Kommandot Klistra in på Åtgärd-menyn](./media/setup_rsa_tool_48.png)

6. <span data-ttu-id="0f737-318">Om du vill hämta tumavtrycket för det installerade certifikatet, men utan blanksteg eller specialtecken, öppnar du ett Windows PowerShell-fönster som administratör och kör följande kommandon.</span><span class="sxs-lookup"><span data-stu-id="0f737-318">To get the thumbprint of the installed certificate, but without spaces or special characters, open a Windows PowerShell window as an admin, and run the following commands.</span></span>

    ```
    cd Cert:\LocalMachine\My

    Get-ChildItem | Where-Object { $_.Subject -like "CN=127.0.0.1" }
    ```

    > [!NOTE]
    > <span data-ttu-id="0f737-319">Spara tumavtrycket eftersom du kommer att behöva det senare när du uppdaterar .wif-filerna för programobjektserver (AOS) och ställ in RSAT-konfigurationen.</span><span class="sxs-lookup"><span data-stu-id="0f737-319">Save the thumbprint, because you will need it later when you update the .wif files for Application Object Server (AOS) and set up the RSAT configuration.</span></span>

#### <a name="configure-the-aos-computer-to-trust-the-connection"></a><span data-ttu-id="0f737-320">Konfigurera AOS-datorn så att den betror anslutningen</span><span class="sxs-lookup"><span data-stu-id="0f737-320">Configure the AOS computer to trust the connection</span></span>

> [!NOTE]
> <span data-ttu-id="0f737-321">Om Finance and Operations-miljön är en Nivå 2+-miljö, måste tumavtrycket för certifikatet uppdateras i filen wif.config för **alla** AOS-datorer för miljön.</span><span class="sxs-lookup"><span data-stu-id="0f737-321">If the Finance and Operations environment is a Tier 2+ environment, the certificate thumbprint must be updated in the wif.config file for **all** AOS computers for the environment.</span></span>

1. <span data-ttu-id="0f737-322">Upprätta en RDP-anslutning (Remote Desktop Protocol) till AOS-datorn.</span><span class="sxs-lookup"><span data-stu-id="0f737-322">Establish a Remote Desktop Protocol (RDP) connection to the AOS computer.</span></span> <span data-ttu-id="0f737-323">Inloggningsinformation finns på miljöns informationssida i LCS.</span><span class="sxs-lookup"><span data-stu-id="0f737-323">Sign-in details are available on the environment details page in LCS.</span></span>
2. <span data-ttu-id="0f737-324">Öppna Microsoft Internet Information Services (IIS) och sök efter **AOSService** i listan över webbplatser.</span><span class="sxs-lookup"><span data-stu-id="0f737-324">Open Microsoft Internet Information Services (IIS), and find **AOSService** in the list of sites.</span></span>

    ![AOSService i listan över webbplatser](./media/setup_rsa_tool_49.png)

3. <span data-ttu-id="0f737-326">Högerklicka på **utforska** om du vill öppna mappen **\<enhet\>: \\AosService\\WebRoot**.</span><span class="sxs-lookup"><span data-stu-id="0f737-326">Right-click **Explore** to open the **\<Drive\>: \\AosService\\WebRoot** folder.</span></span> <span data-ttu-id="0f737-327">Leta upp filen **wif.config**.</span><span class="sxs-lookup"><span data-stu-id="0f737-327">Find the **wif.config** file.</span></span>

    ![Filen wif.config i mappen WebRoot](./media/setup_rsa_tool_50.png)

4. <span data-ttu-id="0f737-329">Uppdatera filen **wif.config** genom att lägga till en ny auktoritetspost för ditt certifikat och auktoritetsnamn, som i följande exempel.</span><span class="sxs-lookup"><span data-stu-id="0f737-329">Update the **wif.config** file by adding a new authority entry for your certificate and authority name, as shown in the following example.</span></span>

    ```
    <issuerNameRegistry type="Microsoft.Dynamics.AX.Security.SharedUtility.AxIssuerNameRegistry,Microsoft.Dynamics.AX.Security.SharedUtility">
        <authority name="CN=127.0.0.1">
            <keys>
                <add thumbprint="xxxxxxxxxxxxxxxxxxxx" />
                <add thumbprint="xxxxxxxxxxxxxxxxxxxx" />
            </keys>
            <validIssuers>
                <add name="CN=127.0.0.1" />
            </validIssuers>
        </authority>
    ```

    > [!NOTE]
    > <span data-ttu-id="0f737-330">Om flera användare använder samma Finance and Operations-program, måste varje användare generera separata tumavtryck och alla dessa tumavtryck måste läggas till i avsnittet **\<nycklar\>**.</span><span class="sxs-lookup"><span data-stu-id="0f737-330">If multiple users are using the same Finance and Operations application, each user must generate separate thumbprints, and each of those thumbprints must be added in the **\<keys\>** section.</span></span>

5. <span data-ttu-id="0f737-331">Om det finns fler än en AOS-dator upprepar du steg 3 till och med 4 för varje ytterligare dator.</span><span class="sxs-lookup"><span data-stu-id="0f737-331">If there is more than one AOS computer, repeat steps 3 through 4 for each additional computer.</span></span>

    > [!NOTE]
    > <span data-ttu-id="0f737-332">Till skillnad från äldre miljöer med nivå 2 distribueras nya miljöer med nivå 2 med två AOS-instanser.</span><span class="sxs-lookup"><span data-stu-id="0f737-332">Unlike older Tier 2 environments, new Tier 2 environments are deployed with two AOS instances.</span></span>

6. <span data-ttu-id="0f737-333">Kör **iisreset** på alla AOS-datorer.</span><span class="sxs-lookup"><span data-stu-id="0f737-333">Run **iisreset** on all the AOS computers.</span></span>

    > [!NOTE]
    > <span data-ttu-id="0f737-334">Om du inte har administratörsbehörighet för att köra **iisreset** på en dator på nivå 1 väljer du Underhåll > Starta om tjänster på sidan Miljödetaljer i LCS.</span><span class="sxs-lookup"><span data-stu-id="0f737-334">If you don't have admin rights to run **iisreset** on a Tier 1 computer, on the Environment details page in LCS, select Maintain > Restart services.</span></span>

#### <a name="tier-2-environment"></a><span data-ttu-id="0f737-335">Nivå 2+-miljö</span><span class="sxs-lookup"><span data-stu-id="0f737-335">Tier 2+ environment</span></span>

<span data-ttu-id="0f737-336">Om en nivå 2+ (sandbox med standardacceptanstest eller högre) Finance and Operations-miljö används, kontrollerar eller anger du följande registerinställning på datorn där RSAT har installerats.</span><span class="sxs-lookup"><span data-stu-id="0f737-336">If a Tier 2+ (Standard Acceptance Test sandbox or higher) Finance and Operations environment is used, verify or set the following registry setting on the computer where RSAT is installed.</span></span> <span data-ttu-id="0f737-337">Det här steget är obligatoriskt eftersom det hjälper dig att undvika anslutningsfel för autentisering eller RSAT.</span><span class="sxs-lookup"><span data-stu-id="0f737-337">This step is required because it helps you avoid authentication or RSAT connection errors.</span></span>

```
if ((Test-Path HKLM:\SOFTWARE\Wow6432Node\Microsoft\.NETFramework\v4.0.30319))
{
    Set-ItemProperty HKLM:\SOFTWARE\Wow6432Node\Microsoft\.NETFramework\v4.0.30319 -Name SchUseStrongCrypto -Value 1 -Type dword -Force -Confirm:$false
}
```

### <a name="install-rsat"></a><span data-ttu-id="0f737-338">Installera RSAT</span><span class="sxs-lookup"><span data-stu-id="0f737-338">Install RSAT</span></span>

1. <span data-ttu-id="0f737-339">Gå till <https://www.microsoft.com/download/details.aspx?id=57357> och välj **Hämta**.</span><span class="sxs-lookup"><span data-stu-id="0f737-339">Go to <https://www.microsoft.com/download/details.aspx?id=57357>, and select **Download**.</span></span>
2. <span data-ttu-id="0f737-340">Markera alla filer och välj **nästa**.</span><span class="sxs-lookup"><span data-stu-id="0f737-340">Select all the files, and then select **Next**.</span></span>

    ![Markera alla filer](./media/setup_rsa_tool_51.png)

3. <span data-ttu-id="0f737-342">Dubbelklicka på .msi-paketet för att köra installationsprogrammet.</span><span class="sxs-lookup"><span data-stu-id="0f737-342">Double-click the .msi package to run the installer.</span></span> <span data-ttu-id="0f737-343">Sedan när installationen är slutförd väljer du **Slutför**.</span><span class="sxs-lookup"><span data-stu-id="0f737-343">Then, when the installation is completed, select **Finish**.</span></span>

    ![Installationsfil för RSAT](./media/setup_rsa_tool_52.png)

### <a name="install-selenium-and-browser-drivers"></a><span data-ttu-id="0f737-345">Installera drivrutiner för Selenium och webbläsare</span><span class="sxs-lookup"><span data-stu-id="0f737-345">Install Selenium and browser drivers</span></span>

<span data-ttu-id="0f737-346">I tidigare versioner av RSAT var du tvungen att installera drivrutiner för Selenium och webbläsare.</span><span class="sxs-lookup"><span data-stu-id="0f737-346">In older versions of RSAT, you had to install Selenium and browser drivers.</span></span> <span data-ttu-id="0f737-347">Du behöver inte längre installera dessa drivrutiner eftersom de installeras automatiskt.</span><span class="sxs-lookup"><span data-stu-id="0f737-347">You no longer have to install these drivers because they are automatically installed.</span></span>

1. <span data-ttu-id="0f737-348">Första gången du öppnar RSAT uppmanas du att automatiskt hämta och installera Selenium.</span><span class="sxs-lookup"><span data-stu-id="0f737-348">The first time that you open RSAT, you're prompted to automatically download and install Selenium.</span></span> <span data-ttu-id="0f737-349">Mer information finns i avsnittet [ Konfigurera RSAT](#configure-rsat).</span><span class="sxs-lookup"><span data-stu-id="0f737-349">For more information, see the [Configure RSAT](#configure-rsat) section.</span></span>
2. <span data-ttu-id="0f737-350">Innan du kan köra ett testfall uppmanas du att automatiskt hämta och installera drivrutinen för webbläsaren som motsvarar standardwebbläsaren som väljs i konfigurationen för RSAT.</span><span class="sxs-lookup"><span data-stu-id="0f737-350">Before you can run a test case, you're prompted to automatically download and install the browser driver that corresponds to the default browser that is selected in the RSAT configuration.</span></span> <span data-ttu-id="0f737-351">Mer information finns i avsnittet [Läsa in och köra testfall](#load-and-run-test-cases).</span><span class="sxs-lookup"><span data-stu-id="0f737-351">For more information, see the [Load and run test cases](#load-and-run-test-cases) section.</span></span>

## <a name="get-started-with-rsat"></a><span data-ttu-id="0f737-352">Kom igång med RSAT</span><span class="sxs-lookup"><span data-stu-id="0f737-352">Get started with RSAT</span></span>

### <a name="create-a-test-plan-and-test-suites"></a><span data-ttu-id="0f737-353">Skapa en testplan och testpaket</span><span class="sxs-lookup"><span data-stu-id="0f737-353">Create a test plan and test suites</span></span>

1. <span data-ttu-id="0f737-354">Gå till Azure DevOps-projektet och välj **testplaner**.</span><span class="sxs-lookup"><span data-stu-id="0f737-354">Go to the Azure DevOps project, and select **Test Plans**.</span></span>

    ![Testplaner, kommando](./media/setup_rsa_tool_53.png)

2. <span data-ttu-id="0f737-356">Välj **ny testplan**.</span><span class="sxs-lookup"><span data-stu-id="0f737-356">Select **New Test Plan**.</span></span>

    ![Knappen Ny testplan](./media/setup_rsa_tool_54.png)

3. <span data-ttu-id="0f737-358">Fyll i fältet **Namn** och välj sedan **Skapa**.</span><span class="sxs-lookup"><span data-stu-id="0f737-358">Fill in the **Name** field, and then select **Create**.</span></span> <span data-ttu-id="0f737-359">I den här självstudien namnger du **RSAT-testplan**.</span><span class="sxs-lookup"><span data-stu-id="0f737-359">For this tutorial, name the test plan **RSAT Test Plan**.</span></span>

    ![Dialogrutan ny testplan](./media/setup_rsa_tool_55.png)

4. <span data-ttu-id="0f737-361">Välj plustecknet (**+**) och välj sedan **statiskt paket** för att skapa en statiskt paket under den nya testplanen.</span><span class="sxs-lookup"><span data-stu-id="0f737-361">Select the plus sign (**+**), and then select **Static suite** to create a static suite under the new test plan.</span></span> <span data-ttu-id="0f737-362">Ange ett namn på det nya testpaketet **T01 – Tillverka mot lager**.</span><span class="sxs-lookup"><span data-stu-id="0f737-362">Name the new test suite **T01 – Make to Stock**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="0f737-363">Du kan också skapa ett frågebaserat paket om du vill att de nya testfallen från BPM ska hämtas automatiskt till testpaketet för RSAT.</span><span class="sxs-lookup"><span data-stu-id="0f737-363">You can also create a query-based suite, if you want the new test cases from BPM to be automatically pulled into the RSAT test suite.</span></span>

    ![Skapa en statiskt paket](./media/setup_rsa_tool_56.png)

### <a name="attach-test-cases-to-test-suites"></a><span data-ttu-id="0f737-365">Bifoga testfall till testpaket</span><span class="sxs-lookup"><span data-stu-id="0f737-365">Attach test cases to test suites</span></span>

1. <span data-ttu-id="0f737-366">Välj **Lägg till befintlig** på höger sida om du vill lägga till befintliga testfall i testprogrammet.</span><span class="sxs-lookup"><span data-stu-id="0f737-366">Select **Add existing** on the right side to add existing test cases to the test suite.</span></span>

    ![Knappen Lägg till befintlig](./media/setup_rsa_tool_57.png)

2. <span data-ttu-id="0f737-368">På sidan **Lägg till testfall till paket** väljer du **Kör fråga** och väljer sedan det testfall som ska läggas till i testpaketet.</span><span class="sxs-lookup"><span data-stu-id="0f737-368">On the **Add test cases to suite** page, select **Run query**, and then select the test case to add to the test suite.</span></span> <span data-ttu-id="0f737-369">För den här självstudien väljer du testfallet **Skapa enny produkt**.</span><span class="sxs-lookup"><span data-stu-id="0f737-369">For this tutorial, select the **Create a new product** test case.</span></span> <span data-ttu-id="0f737-370">Välj sedan **Lägg till testfall** i det nedre högra hörnet på sidan (den här knappen visas inte på följande bild).</span><span class="sxs-lookup"><span data-stu-id="0f737-370">Then select **Add test cases** in the lower-right corner of the page (this button isn't shown in the following illustration).</span></span>

    ![Knappen Kör fråga](./media/setup_rsa_tool_58.png)

    <span data-ttu-id="0f737-372">Testfall som läggs till i testfallet **T01 - Tillverka mot lager**.</span><span class="sxs-lookup"><span data-stu-id="0f737-372">The test case is added to the **T01-Make to Stock** test suite.</span></span>

    ![Testfall tillagt i testpaketet](./media/setup_rsa_tool_59.png)

### <a name="configure-rsat"></a><span data-ttu-id="0f737-374">Konfigurera RSAT</span><span class="sxs-lookup"><span data-stu-id="0f737-374">Configure RSAT</span></span>

1. <span data-ttu-id="0f737-375">Öppna RSAT</span><span class="sxs-lookup"><span data-stu-id="0f737-375">Open RSAT.</span></span>

    ![RSAT-ikon](./media/setup_rsa_tool_60.png)

2. <span data-ttu-id="0f737-377">Du får ett varningsmeddelande om att "Regression Suite Automation Tool kräver Selenium, vill du att det automatiskt ska hämtas och installeras nu?"</span><span class="sxs-lookup"><span data-stu-id="0f737-377">You receive a warning message that states, "The Regression Suite Automation Tool requires Selenium, do you want to automatically download and install it now?"</span></span> <span data-ttu-id="0f737-378">Välj **Ja**.</span><span class="sxs-lookup"><span data-stu-id="0f737-378">Select **Yes**.</span></span>

    ![Varningsmeddelande](./media/setup_rsa_tool_61.png)

3. <span data-ttu-id="0f737-380">Välj knappen **inställningar** (kugghjulssymbolen) i det övre högra hörnet och fyll sedan i följande fält i dialogrutan som visas:</span><span class="sxs-lookup"><span data-stu-id="0f737-380">Select the **Settings** button (the gear symbol) in the upper-right corner, and then, in the dialog box that appears, fill in the following fields:</span></span>

    - <span data-ttu-id="0f737-381">**Azure DevOps Url** – Anger URL för ditt Azure DevOps-projekt, t.ex. `https://yourAzureDevOpsUrlHere.visualStudio.com`.</span><span class="sxs-lookup"><span data-stu-id="0f737-381">**Azure DevOps Url** – Enter the URL of your Azure DevOps project, such as `https://yourAzureDevOpsUrlHere.visualStudio.com`.</span></span>
    - <span data-ttu-id="0f737-382">**Åtkomsttoken** – ange den åtkomsttoken som gör att verktyget kan ansluta till Azure DevOps.</span><span class="sxs-lookup"><span data-stu-id="0f737-382">**Access Token** – Enter the access token that lets the tool connect to Azure DevOps.</span></span> <span data-ttu-id="0f737-383">Använd den personliga åtkomsttoken som du skapade tidigare i den här självstudien.</span><span class="sxs-lookup"><span data-stu-id="0f737-383">Use the personal access token that you created earlier in this tutorial.</span></span> <span data-ttu-id="0f737-384">Mer information finns i autentisera [åtkomst med privata åtkomsttoken](https://www.visualstudio.com/docs/setup-admin/team-services/use-personal-access-tokens-to-authenticate).</span><span class="sxs-lookup"><span data-stu-id="0f737-384">For more information, see [Authenticate access with personal access tokens](https://www.visualstudio.com/docs/setup-admin/team-services/use-personal-access-tokens-to-authenticate).</span></span>
    - <span data-ttu-id="0f737-385">**Projektnamn** – Välj namnet på Azure DevOps-projektet.</span><span class="sxs-lookup"><span data-stu-id="0f737-385">**Project Name** – Select the name of your Azure DevOps project.</span></span>
    - <span data-ttu-id="0f737-386">**Testplan** – Välj Azure DevOps testplanen som innehåller testfallen.</span><span class="sxs-lookup"><span data-stu-id="0f737-386">**Test Plan** – Select the Azure DevOps test plan that contains your test cases.</span></span> <span data-ttu-id="0f737-387">Mer information finns i [skapa testplaner och testpaket](https://www.visualstudio.com/docs/test/manual-exploratory-testing/getting-started/create-a-test-plan).</span><span class="sxs-lookup"><span data-stu-id="0f737-387">For more information, see [Create test plans and test suites](https://www.visualstudio.com/docs/test/manual-exploratory-testing/getting-started/create-a-test-plan).</span></span> <span data-ttu-id="0f737-388">När du har valt en testplan väljer du **testa anslutning** för att testa anslutningen till Azure DevOps.</span><span class="sxs-lookup"><span data-stu-id="0f737-388">After you select a test plan, select **Test Connection** to test your connection to Azure DevOps.</span></span>
    - <span data-ttu-id="0f737-389">**Värdnamn** – ange värdnamnet på Finance and Operations-testmiljön, t. ex. **\<myaos\>.cloudax.dynamics.com**.</span><span class="sxs-lookup"><span data-stu-id="0f737-389">**Hostname** – Enter the host name of the Finance and Operations test environment, such as **\<myaos\>.cloudax.dynamics.com**.</span></span> <span data-ttu-id="0f737-390">Ta inte med prefixet **https://** eller **http://**.</span><span class="sxs-lookup"><span data-stu-id="0f737-390">Don't include the **https://** or **http://** prefix.</span></span>
    - <span data-ttu-id="0f737-391">**SOAP-värdnamn** – ange SOAP-värdnamnet för Finance and Operations-testmiljön.</span><span class="sxs-lookup"><span data-stu-id="0f737-391">**SOAP Hostname** – Enter the SOAP host name of the Finance and Operations test environment.</span></span> <span data-ttu-id="0f737-392">Vanligt vis är SOAP-värdnamnet detsamma som värdnamnet, men det har ett **soap**-suffix.</span><span class="sxs-lookup"><span data-stu-id="0f737-392">Typically, the SOAP host name is the same as the host name, but it has a **soap** suffix.</span></span> <span data-ttu-id="0f737-393">Här följer ett exempel: **\<myaos\>soap.cloudax.dynamics.com**.</span><span class="sxs-lookup"><span data-stu-id="0f737-393">Here is an example: **\<myaos\>soap.cloudax.dynamics.com**.</span></span> <span data-ttu-id="0f737-394">Ta inte med prefixet **https://** eller **http://**.</span><span class="sxs-lookup"><span data-stu-id="0f737-394">Don't include the **https://** or **http://** prefix.</span></span>

        > [!NOTE]
        > <span data-ttu-id="0f737-395">Om du vill hitta värdnamnet och namnet på SOAP-värddatorn, öppna IIS-hanterare, högerklicka på **Webbplatser \> AOSService** och välj sedan **redigera bindningar**.</span><span class="sxs-lookup"><span data-stu-id="0f737-395">To find the host name and SOAP host name, open IIS Manager, right-click **Sites \> AOSService**, and then select **Edit bindings**.</span></span> <span data-ttu-id="0f737-396">Värdena i kolumnen **värdnamn** ger värdnamnet och namnet på SOAP-värddatorn (SOAP-värdnamnet har suffixet **soap** i URL).</span><span class="sxs-lookup"><span data-stu-id="0f737-396">The values in the **Host Name** column give you the host name and SOAP host name (the SOAP host name has the suffix **soap** in the URL).</span></span>

        ![Värdnamnet och SOAP-värdnamnet i kolumnen värdnamn](./media/setup_rsa_tool_63.png)

    - <span data-ttu-id="0f737-398">**Användarnamn för administratören** – Ange e-postadressen för en administratörsanvändare i testmiljön Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="0f737-398">**Admin user name** – Enter the email address of an admin user in the Finance and Operations test environment.</span></span>
    - <span data-ttu-id="0f737-399">**Tumavtryck** – Ange certifikatets tumavtryck, enligt beskrivningen ovan i den här självstudien.</span><span class="sxs-lookup"><span data-stu-id="0f737-399">**Thumbprint** – Enter the thumbprint of the authentication certificate, as described earlier in this tutorial.</span></span>
    - <span data-ttu-id="0f737-400">**Arbetskatalog** – ange mappens plats där du vill lagra testautomatiseringsfiler, t.ex. Excel-testdatafiler.</span><span class="sxs-lookup"><span data-stu-id="0f737-400">**Working directory** – Specify the folder location for storing test automation files, such as Excel test data files.</span></span> <span data-ttu-id="0f737-401">Skriv t.ex. eller välj **C:\\Temp\\RegressionTool**.</span><span class="sxs-lookup"><span data-stu-id="0f737-401">For example, enter or select **C:\\Temp\\RegressionTool**.</span></span>

        > [!NOTE]
        > <span data-ttu-id="0f737-402">Om namnet på mappen innehåller blanksteg misslyckas körningen eftersom mappen inte kan hittas.</span><span class="sxs-lookup"><span data-stu-id="0f737-402">If the name of the folder has spaces, execution will fail because the folder can't be found.</span></span> <span data-ttu-id="0f737-403">Det här problemet är ett känt problem och bör korrigeras i den senaste versionen av verktyget.</span><span class="sxs-lookup"><span data-stu-id="0f737-403">This issue is a known issue and should be fixed in the latest version of the tool.</span></span>

    - <span data-ttu-id="0f737-404">**Standardwebbläsare** – Välj antingen **Internet Explorer** eller **Google Chrome**.</span><span class="sxs-lookup"><span data-stu-id="0f737-404">**Default browser** – Select either **Internet Explorer** or **Google Chrome**.</span></span> <span data-ttu-id="0f737-405">Kontrollera att rätt drivrutiner för webbläsarfilen har installerats.</span><span class="sxs-lookup"><span data-stu-id="0f737-405">Make sure that the appropriate browser drivers have been installed.</span></span>
    - <span data-ttu-id="0f737-406">**Tidsgräns för testkörning** – ange tidsgränsen i minuter för testkörningarna.</span><span class="sxs-lookup"><span data-stu-id="0f737-406">**Test run timeout** – Specify the time-out period, in minutes, for test runs.</span></span> <span data-ttu-id="0f737-407">När tidsgränsen går ut stängs alla aktiva fönster och väntande testfall misslyckas.</span><span class="sxs-lookup"><span data-stu-id="0f737-407">When the time-out period elapses, all active windows are closed, and pending test cases fail.</span></span>
    - <span data-ttu-id="0f737-408">**Teståtgärdens tidsgräns** – det här fältet styr tidsgränsen, i minuter, för Finance and Operation-miljöns serverbegäran.</span><span class="sxs-lookup"><span data-stu-id="0f737-408">**Test action timeout** – This field controls the time-out period, in minutes, for Finance and Operation environment server requests.</span></span> <span data-ttu-id="0f737-409">Normalt bör standardvärdet (2 minuter) vara tillräckligt.</span><span class="sxs-lookup"><span data-stu-id="0f737-409">Usually, the default value (2 minutes) should be enough.</span></span> <span data-ttu-id="0f737-410">För långsammare miljöer kan det dock vara bra att öka värdet om fel som rör tidsgränden uppstår.</span><span class="sxs-lookup"><span data-stu-id="0f737-410">However, for slower environments, you might want to increase the value if errors that are related to time-outs occur.</span></span>
    - <span data-ttu-id="0f737-411">**Företagsnamn** – ange vilket företagsnamn som ska användas som standardföretag för Finance and Operations när Excel-parameterfiler skapas.</span><span class="sxs-lookup"><span data-stu-id="0f737-411">**Company name** – Enter the company name to use as your default Finance and Operations company when Excel parameter files are created.</span></span> <span data-ttu-id="0f737-412">Du kan ändra företaget senare genom att redigera Excel-parameterfilen.</span><span class="sxs-lookup"><span data-stu-id="0f737-412">You can change the company later by editing the Excel parameter file.</span></span>

    ![Dialogrutan Inställningar](./media/setup_rsa_tool_62.png)

4. <span data-ttu-id="0f737-414">Välj **tillämpa** om du vill tillämpa och spara inställningarna.</span><span class="sxs-lookup"><span data-stu-id="0f737-414">Select **Apply** to apply and save your settings.</span></span>

    <span data-ttu-id="0f737-415">Om du vill spara de aktuella inställningarna i en konfigurationsfil på din dator väljer du **Spara som**.</span><span class="sxs-lookup"><span data-stu-id="0f737-415">To save your current settings to a configuration file on your computer, select **Save as**.</span></span> <span data-ttu-id="0f737-416">Om du vill återställa dina inställningarna från en konfigurationsfil på din dator väljer du **Öppna**.</span><span class="sxs-lookup"><span data-stu-id="0f737-416">To restore your settings from a configuration file on your computer, select **Open**.</span></span>

5. <span data-ttu-id="0f737-417">Välj **Stäng** för att stänga dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="0f737-417">Select **Close** to close the dialog box.</span></span>

### <a name="load-and-run-test-cases"></a><span data-ttu-id="0f737-418">Läs in och kör testfall</span><span class="sxs-lookup"><span data-stu-id="0f737-418">Load and run test cases</span></span>

1. <span data-ttu-id="0f737-419">Välj **Läs in** föratt läsa in testplanen **RSAT-testplan** från Azure DevOps-projektet.</span><span class="sxs-lookup"><span data-stu-id="0f737-419">Select **Load** to load the **RSAT Test Plan** test plan from the Azure DevOps project.</span></span>

    ![Knappen Läs in](./media/setup_rsa_tool_64.png)

2. <span data-ttu-id="0f737-421">Välj **skapa en ny produkt** testfall från testpaketet och välj sedan **ny \> generera testkörning och parameterfil**.</span><span class="sxs-lookup"><span data-stu-id="0f737-421">Select the **Create a new product** test case from the test suite, and then select **New \> Generate Test Execution and Parameter files**.</span></span>

    ![Generera kommandon Testkörning och Parameterfiler på menyn Ny](./media/setup_rsa_tool_65.png)

    <span data-ttu-id="0f737-423">Excel-parameterfilen skapas i den lokala mapp som du har angett i RSAT-konfigurationen (t.ex. **C:\\Temp\\RegressionTool**).</span><span class="sxs-lookup"><span data-stu-id="0f737-423">The Excel parameter file is created in the local folder that you specified in the RSAT configuration (for example, **C:\\Temp\\RegressionTool**).</span></span>

    ![Excel-parameterfilen skapas](./media/setup_rsa_tool_66.png)

3. <span data-ttu-id="0f737-425">Om du vill spara parametervärdena väljer du **överför**.</span><span class="sxs-lookup"><span data-stu-id="0f737-425">If you want to save the parameter files, select **Upload**.</span></span> <span data-ttu-id="0f737-426">Testautomatiseringsfiler för alla valda testfall överförs till Azure DevOps för framtida användning.</span><span class="sxs-lookup"><span data-stu-id="0f737-426">Test automation files of all selected test cases are uploaded to Azure DevOps for future use.</span></span> <span data-ttu-id="0f737-427">(Dessa filer inkluderar även Excel-testparameterfiler.)</span><span class="sxs-lookup"><span data-stu-id="0f737-427">(These files include Excel test parameter files.)</span></span>

    <span data-ttu-id="0f737-428">På så sätt kan du välja **Läs in** för att läsa in parametervärdena (och automatiseringsfiler) från testfall direkt från Azure DevOps.</span><span class="sxs-lookup"><span data-stu-id="0f737-428">In this way, you can select **Load** to load the parameter files (and automation files) from the test case directly from Azure DevOps.</span></span> <span data-ttu-id="0f737-429">Du behöver inte generera om parameterfilerna.</span><span class="sxs-lookup"><span data-stu-id="0f737-429">You don't have to regenerate the parameter files.</span></span> <span data-ttu-id="0f737-430">Den här metoden kommer att bli viktig senare när du vill behålla ändringarna i parameterfilen och inte vill att de ska skrivas över.</span><span class="sxs-lookup"><span data-stu-id="0f737-430">This approach will become important later, when you want to keep the modifications in the parameter file and don't want them to be overwritten.</span></span>

4. <span data-ttu-id="0f737-431">Om du vill kontrollera att automatiseringsfiler och parameterfilerna sparas i Azure DevOps, gå till Azure DevOps-projektet och välj **Tavlor \> Arbetsuppgifter** och välj sedan testfallet **Skapa en ny produkt**.</span><span class="sxs-lookup"><span data-stu-id="0f737-431">To verify that the automation files and parameter files are saved to Azure DevOps, go to the Azure DevOps project, select **Boards \> Work Items**, and select the **Create a new product** test case.</span></span> <span data-ttu-id="0f737-432">På fliken **bifogade filer** ska du se fyra filer:</span><span class="sxs-lookup"><span data-stu-id="0f737-432">On the **Attachments** tab, you should see four files:</span></span>

    - <span data-ttu-id="0f737-433">**.cs** – C\# automatiseringsfil</span><span class="sxs-lookup"><span data-stu-id="0f737-433">**.cs** – C\# automation file</span></span>
    - <span data-ttu-id="0f737-434">**.dll** – kompilerad automatiseringsfil som en sammansättning</span><span class="sxs-lookup"><span data-stu-id="0f737-434">**.dll** – Compiled automation file as an assembly</span></span>
    - <span data-ttu-id="0f737-435">**.xlsx** – Excel-parameterfil</span><span class="sxs-lookup"><span data-stu-id="0f737-435">**.xlsx** – Excel parameter file</span></span>
    - <span data-ttu-id="0f737-436">**.xml** – Inspelningsfil</span><span class="sxs-lookup"><span data-stu-id="0f737-436">**.xml** – Recording file</span></span>

    ![Filer på fliken Bifogade filer](./media/setup_rsa_tool_67.png)

5. <span data-ttu-id="0f737-438">Välj det testfall som ska köras och välj sedan **kör**.</span><span class="sxs-lookup"><span data-stu-id="0f737-438">Select the test case to run, and then select **Run**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="0f737-439">Innan du kör testfall, om du använder Internet Explorer som webbläsare kontrollerar du att din skrivbordsupplösning är inställd på **100 %** på **Inställningar för Windows-display \> Skala och layout**.</span><span class="sxs-lookup"><span data-stu-id="0f737-439">Before you run test cases, if you're using Internet Explorer as the browser, make sure that your desktop resolution is set to **100%** at **Windows Display settings \> Scale and layout**.</span></span> <span data-ttu-id="0f737-440">Om du inte kan ändra den här inställningen på en virtuell dator (VM) ändrar du den på klienten (den bärbara datorn) som du försöker komma åt den virtuella datorn från.</span><span class="sxs-lookup"><span data-stu-id="0f737-440">If you can't change this setting on a virtual machine (VM), change it on the client (laptop) that you're trying to access the VM from.</span></span> <span data-ttu-id="0f737-441">Inställningarna för upplösning kommer sedan att ärvas av inställningarna för den virtuella datorns bildskärm.</span><span class="sxs-lookup"><span data-stu-id="0f737-441">The resolution settings will then be inherited by the VM display settings.</span></span>

    ![Skärmupplösningen är inställd på 100 %](./media/setup_rsa_tool_68.png)

6. <span data-ttu-id="0f737-443">Om drivrutinerna för webbläsaren inte är installerade i systemet visas ett varningsmeddelande om "Den här åtgärden kräver drivrutin för \<webbläsare\>.</span><span class="sxs-lookup"><span data-stu-id="0f737-443">If the browser drivers aren't installed in the system, you receive a warning message that states, "This operation requires the \<browser name\> driver.</span></span> <span data-ttu-id="0f737-444">Vill du att den automatiskt ska hämtas och installeras nu?"</span><span class="sxs-lookup"><span data-stu-id="0f737-444">Do you want to automatically downloads and install it now?"</span></span> <span data-ttu-id="0f737-445">Välj **Ja**.</span><span class="sxs-lookup"><span data-stu-id="0f737-445">Select **Yes**.</span></span>

    ![Varningsmeddelande för Internet Explorer](./media/setup_rsa_tool_69.png)

    ![Varningsmeddelande för Chrome](./media/setup_rsa_tool_70.png)

    > [!NOTE]
    > <span data-ttu-id="0f737-448">Om du använder Chrome som webbläsare och får ett felmeddelande om att sessionen inte skapades eftersom den inte är korrekt, hämtar du den senaste Chrome-drivrutinen från <http://chromedriver.chromium.org/downloads> till mappen **C:\\Programfiler (x86)\\Regression Suite Automation Tool\\Vanliga\\Externa\\Selenium**.</span><span class="sxs-lookup"><span data-stu-id="0f737-448">If you're using Chrome as the browser and receive an error message that states that the session wasn't created because the Chrome version isn't correct, download the latest Chrome driver from <http://chromedriver.chromium.org/downloads> to the **C:\\Program Files (x86)\\Regression Suite Automation Tool\\Common\\External\\Selenium** folder.</span></span>

    ![Felmeddelande för Chrome](./media/setup_rsa_tool_71.png)

    <span data-ttu-id="0f737-450">Testfall körs och fältet **resultat** uppdateras.</span><span class="sxs-lookup"><span data-stu-id="0f737-450">The test case is run, and the **Result** field is updated.</span></span>

    ![Förloppsindikator](./media/setup_rsa_tool_72.png)

    <span data-ttu-id="0f737-452">Om du har följt den här vägledningen som den är skriven kommer testfallet **Skapa en ny produkt** att misslyckas eftersom uppgiftsinspelningen för att skapa en produkt har sparade produktnamnet som ett hårdkodat värde.</span><span class="sxs-lookup"><span data-stu-id="0f737-452">If you've followed this tutorial as it's written, the **Create a new product** test case will fail, because the task recording for creating a product saved the product name as a hard-coded value.</span></span> <span data-ttu-id="0f737-453">Om du kör samma testfall igen bör du få ett felmeddelande, eftersom produkten redan finns.</span><span class="sxs-lookup"><span data-stu-id="0f737-453">If you rerun the same test case, you should receive an error message, because the product already exists.</span></span>

    ![Fältet Resultat angavs till misslyckat](./media/setup_rsa_tool_72.png)

### <a name="view-the-test-results"></a><span data-ttu-id="0f737-455">Visa testresultaten</span><span class="sxs-lookup"><span data-stu-id="0f737-455">View the test results</span></span>

1. <span data-ttu-id="0f737-456">Dubbelklicka på det misslyckade testfallet.</span><span class="sxs-lookup"><span data-stu-id="0f737-456">Double-click the failed test case.</span></span>

    <span data-ttu-id="0f737-457">Du får ett felmeddelande.</span><span class="sxs-lookup"><span data-stu-id="0f737-457">You receive an error message.</span></span>

    ![Felmeddelande](./media/setup_rsa_tool_73.png)

2. <span data-ttu-id="0f737-459">Välj **Detaljer** om du vill visa hela felmeddelandet.</span><span class="sxs-lookup"><span data-stu-id="0f737-459">Select **Details** to view the whole error message.</span></span>

    ![Hela felmeddelande](./media/setup_rsa_tool_74.png)

3. <span data-ttu-id="0f737-461">Om du vill visa en detaljerad version av felmeddelandet i Azure DevOps väljer **Öppna i Azure DevOps**.</span><span class="sxs-lookup"><span data-stu-id="0f737-461">To view a detailed version of the error message in Azure DevOps, select **Open in Azure DevOps**.</span></span> <span data-ttu-id="0f737-462">I Azure DevOps kan du visa status för testfallet och det detaljerade felmeddelandet.</span><span class="sxs-lookup"><span data-stu-id="0f737-462">In Azure DevOps, you can view the status of the test case and the detailed error message.</span></span>

    ![Detaljerat felmeddelande i Azure DevOps](./media/setup_rsa_tool_75.png)

4. <span data-ttu-id="0f737-464">Om du vill visa testresultaten direkt i Azure DevOps-projektet går du till **testplaner \> testplaner \> körs**.</span><span class="sxs-lookup"><span data-stu-id="0f737-464">To view the test results directly in the Azure DevOps project, go to **Test Plans \> Test Plans \> Runs**.</span></span> <span data-ttu-id="0f737-465">Dubbelklicka på testkörningen som du vill ha mer information om.</span><span class="sxs-lookup"><span data-stu-id="0f737-465">Double-click the test run that you want to see more details for.</span></span>

    ![Lista över testkörningar i Azure DevOps](./media/setup_rsa_tool_76.png)

5. <span data-ttu-id="0f737-467">Fliken **Kör sammanfattning** anger att testfallet misslyckades, men det inte ger det faktiska felmeddelandet.</span><span class="sxs-lookup"><span data-stu-id="0f737-467">The **Run summary** tab indicates that the test case failed, but it doesn't provide the actual error message.</span></span> <span data-ttu-id="0f737-468">Om du vill visa det detaljerade felmeddelandet väljer du fliken **testresultat**.</span><span class="sxs-lookup"><span data-stu-id="0f737-468">To view the detailed error message, select the **Test results** tab.</span></span>

    ![Kör fliken Sammanfattning](./media/setup_rsa_tool_77.png)

    <span data-ttu-id="0f737-470">På fliken **Testresultat** finns information om testfall tillsammans med resultatet och felmeddelandet.</span><span class="sxs-lookup"><span data-stu-id="0f737-470">The **Test results** tab provides the test case information, together with the outcome and the error message.</span></span>

    ![Fliken Testresultat](./media/setup_rsa_tool_78.png)

6. <span data-ttu-id="0f737-472">Dubbelklicka på den relevanta posten så visas ett detaljerat felmeddelande.</span><span class="sxs-lookup"><span data-stu-id="0f737-472">Double-click the relevant record to view the detailed error message.</span></span>

    ![Detaljerat felmeddelande](./media/setup_rsa_tool_79.png)

    > [!NOTE]
    > <span data-ttu-id="0f737-474">Alla felmeddelanden finns också lokalt i **C:\\Användare\\\$YourUserName\\AppData\\Roaming\\regressionTool\\errormsg-.txt**.</span><span class="sxs-lookup"><span data-stu-id="0f737-474">All error messages are also available locally in **C:\\Users\\\$YourUserName\\AppData\\Roaming\\regressionTool\\errormsg-.txt**.</span></span>

7. <span data-ttu-id="0f737-475">Du kan också exportera testresultaten från testplannivån genom att välja **exportera**.</span><span class="sxs-lookup"><span data-stu-id="0f737-475">You can also export the test run results from the test plan level by selecting **Export**.</span></span>

    ![Exportera en testplan](./media/setup_rsa_tool_80.png)

### <a name="modify-the-excel-parameter-file"></a><span data-ttu-id="0f737-477">Modifiera Excel-parameterfil</span><span class="sxs-lookup"><span data-stu-id="0f737-477">Modify the Excel parameter file</span></span>

1. <span data-ttu-id="0f737-478">Öppna RSAT</span><span class="sxs-lookup"><span data-stu-id="0f737-478">Open RSAT.</span></span>
2. <span data-ttu-id="0f737-479">Markera testfallen och välj sedan **redigera** för att öppna Excel-parameterfil.</span><span class="sxs-lookup"><span data-stu-id="0f737-479">Select the test case, and then select **Edit** to open the Excel parameter file.</span></span>

    <span data-ttu-id="0f737-480">På arket **EcoResProductCreate**, observera att värdetpå fältet **produktnummer** är hårdkodat.</span><span class="sxs-lookup"><span data-stu-id="0f737-480">On the **EcoResProductCreate** sheet, notice that the value of the **Product number** field is hard-coded.</span></span> <span data-ttu-id="0f737-481">Du måste uppdatera det här fältet till ett nytt produktnummer innan du kör testfallet igen.</span><span class="sxs-lookup"><span data-stu-id="0f737-481">You must update this field to a new product number before you run the test case again.</span></span>

3. <span data-ttu-id="0f737-482">Om du vill skapa ett unikt produktnummer för varje körning utan att behöva öppna Excel-parameterfilen på nytt och uppdatera produktnumret manuellt varje gång, använder du följande Excel-formel.</span><span class="sxs-lookup"><span data-stu-id="0f737-482">To generate a unique product number for each run without having to reopen the Excel parameter file and manually update the product number every time, use the following Excel formula.</span></span>

    ```
    ="RSAT_"&TEXT(NOW(),"yyymmddhhmm")
    ```

    > [!NOTE]
    > <span data-ttu-id="0f737-483">Förutom fliken **allmänt** innehåller Excel-parameterfilen en dataflik för varje Finance and Operations-formulärsida som testfallet besöker.</span><span class="sxs-lookup"><span data-stu-id="0f737-483">In addition to the **General** tab, the Excel parameter file contains a data tab for every Finance and Operations form page the test case visits.</span></span>

    ![Fältet Produktnummer](./media/setup_rsa_tool_81.png)

4. <span data-ttu-id="0f737-485">Markera **Spara** och stäng sedan Excel-arbetsboken.</span><span class="sxs-lookup"><span data-stu-id="0f737-485">Select **Save**, and then close the Excel workbook.</span></span>
5. <span data-ttu-id="0f737-486">Välj **överför** om du vill spara Excel-parameterfilen på Azure DevOps.</span><span class="sxs-lookup"><span data-stu-id="0f737-486">Select **Upload** to save the Excel parameter file to Azure DevOps.</span></span>

    ![Meddelandet Uppladdning klar](./media/setup_rsa_tool_82.png)

    > [!NOTE]
    > <span data-ttu-id="0f737-488">Om du vill köra testfall i en specifik användarkontext anger du användarens e-post-ID **testanvändare** på fliken **Allmänt** i Excel-parameterfilen.</span><span class="sxs-lookup"><span data-stu-id="0f737-488">To run test cases in a specific user context, enter the user's email ID in the **Test User** field on the **General** tab of the Excel parameter file.</span></span> <span data-ttu-id="0f737-489">I den senaste versionen av RSAT har layouten för fälten i Excel-parameterfilen uppdaterats, men konceptet förblir oförändrat.</span><span class="sxs-lookup"><span data-stu-id="0f737-489">In the latest version of RSAT, the layout of the fields in the Excel parameter file has been updated, but the concept remains the same.</span></span>
    >
    > ![Fältet Testanvändare](./media/setup_rsa_tool_83.png)

### <a name="validate-the-results"></a><span data-ttu-id="0f737-491">Validera resultaten</span><span class="sxs-lookup"><span data-stu-id="0f737-491">Validate the results</span></span>

- <span data-ttu-id="0f737-492">Välj **kör** för att köra testfallet igen och kontrollera att testfallet har godkänts.</span><span class="sxs-lookup"><span data-stu-id="0f737-492">Select **Run** to rerun the test case, and verify that the test case has passed.</span></span> <span data-ttu-id="0f737-493">Du kan visa testresultaten enligt beskrivningen i avsnittet [Visa testresultat](#view-the-test-results).</span><span class="sxs-lookup"><span data-stu-id="0f737-493">You can view the test results as described in the [View the test results](#view-the-test-results) section.</span></span>

    ![Fältet Resultat angavs till Godkänt](./media/setup_rsa_tool_84.png)

### <a name="chaining-of-test-cases"></a><span data-ttu-id="0f737-495">Kedja av testfall</span><span class="sxs-lookup"><span data-stu-id="0f737-495">Chaining of test cases</span></span>

<span data-ttu-id="0f737-496">En nyckelegenskap i RSAT är en kedja av testfall (det vill säga förmågan hos ett test för att överföra värden till andra tester).</span><span class="sxs-lookup"><span data-stu-id="0f737-496">One key feature of RSAT is the chaining of test cases (that is, the capability of a test to pass values to other tests).</span></span> <span data-ttu-id="0f737-497">Testfall körs enligt deras definierade ordning i Azure DevOps-testplan.</span><span class="sxs-lookup"><span data-stu-id="0f737-497">Test cases are run according to their defined order in the Azure DevOps test plan.</span></span> <span data-ttu-id="0f737-498">(Den här ordningen kan också uppdateras i själva testverktyget.) Om du vill överföra variabler från ett testfall till ett annat, är det därför mycket viktigt att testen finns i rätt ordning.</span><span class="sxs-lookup"><span data-stu-id="0f737-498">(This order can also be updated in the test tool itself.) Therefore, if you want to pass variables from one test case to another, it's very important that the tests be in the correct order.</span></span>

<span data-ttu-id="0f737-499">I det här avsnittet skapar du en sparad variabel i det första testfallet, skapar ett andra testfall och skickar den sparade variabeln från det första testfallet till det andra testfallet.</span><span class="sxs-lookup"><span data-stu-id="0f737-499">In this section, you will create a saved variable in the first test case, create a second test case, and pass the saved variable from the first test case to the second test case.</span></span> <span data-ttu-id="0f737-500">Sedan kör du testfallen som ett kedjetestfall i RSAT.</span><span class="sxs-lookup"><span data-stu-id="0f737-500">You will then run the test cases as a chained test case in RSAT.</span></span>

#### <a name="modify-an-existing-task-recording-to-create-a-saved-variable"></a><span data-ttu-id="0f737-501">Ändra en befintlig uppgiftsinspelning för att skapa en sparad variabel</span><span class="sxs-lookup"><span data-stu-id="0f737-501">Modify an existing task recording to create a saved variable</span></span>

1. <span data-ttu-id="0f737-502">Öppna Finance and Operations-klienten</span><span class="sxs-lookup"><span data-stu-id="0f737-502">Open the Finance and Operations client.</span></span>
2. <span data-ttu-id="0f737-503">Välj knappen **inställningar** (växelsymbolen) och sedan **Uppgiftsinspelare**.</span><span class="sxs-lookup"><span data-stu-id="0f737-503">Select the **Settings** button (the gear symbol), and then select **Task recorder**.</span></span>
3. <span data-ttu-id="0f737-504">Välj **redigera inspelning**.</span><span class="sxs-lookup"><span data-stu-id="0f737-504">Select **Edit Recording**.</span></span>

    ![Knappen Redigera inspelning](./media/setup_rsa_tool_85.png)

4. <span data-ttu-id="0f737-506">Välj **Öppna från Lifecycle Services**.</span><span class="sxs-lookup"><span data-stu-id="0f737-506">Select **Open from Lifecycle Services**.</span></span>

    ![Knappen Öppna från Lifecycle Services](./media/setup_rsa_tool_86.png)

5. <span data-ttu-id="0f737-508">Välj **Lifecycle Services-bibliotek**</span><span class="sxs-lookup"><span data-stu-id="0f737-508">Select **Select the Lifecycle Services library**.</span></span>

    ![Knappen Välj Lifecycle Services-bibliotek](./media/setup_rsa_tool_87.png)

    <span data-ttu-id="0f737-510">BPM-bibliotek läses in från LCS.</span><span class="sxs-lookup"><span data-stu-id="0f737-510">BPM libraries are loaded from LCS.</span></span>

    ![Förloppsindikator](./media/setup_rsa_tool_88.png)

6. <span data-ttu-id="0f737-512">När du har läst in BPM-biblioteken från LCS väljer du **RSAT** BPM-biblioteket och affärsprocessen **Skapa enny produkt** som uppgiftsinspelningen var associerad med.</span><span class="sxs-lookup"><span data-stu-id="0f737-512">After the BPM libraries are loaded from LCS, select the **RSAT** BPM library and the **Create a new product** business process that the task recording was associated with.</span></span> <span data-ttu-id="0f737-513">Välj sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="0f737-513">Then select **OK**.</span></span>

    ![Välj ett BPM-bibliotek och en affärsprocess](./media/setup_rsa_tool_89.png)

7. <span data-ttu-id="0f737-515">Namnet på lämplig uppgiftsinspelning anges i fältet **inspelningsnamn**.</span><span class="sxs-lookup"><span data-stu-id="0f737-515">The name of the appropriate task recording is entered in the **Recording name** field.</span></span> <span data-ttu-id="0f737-516">Välj **start**.</span><span class="sxs-lookup"><span data-stu-id="0f737-516">Select **Start**.</span></span>

    ![Namn på uppgiftsinspelningen i fältet Inspelningsnamn](./media/setup_rsa_tool_90.png)

8. <span data-ttu-id="0f737-518">Gå till **produktinformationshantering \> produkter** och välj **Ny** om du vill öppna sidan med den ursprungliga uppgiftsinspelningen, **Skapa en produkt** spelades in.</span><span class="sxs-lookup"><span data-stu-id="0f737-518">Go to **Product information management \> Products**, and select **New** to open the page where the original task recording, **Create a product**, was recorded.</span></span>
9. <span data-ttu-id="0f737-519">Välj **infoga steg**.</span><span class="sxs-lookup"><span data-stu-id="0f737-519">Select **Insert step**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="0f737-520">Det nya steget infogas **efter** steget som du valde i fönstret.</span><span class="sxs-lookup"><span data-stu-id="0f737-520">The new step is inserted **after** the step that you selected in the pane.</span></span>

    ![Knappen Infoga steg](./media/setup_rsa_tool_91.png)

10. <span data-ttu-id="0f737-522">Högerklicka i fältet **produktnummer** och välj sedan **uppgiftsinspelning \> Kopia**.</span><span class="sxs-lookup"><span data-stu-id="0f737-522">Right-click the **Product number** field, and then select **Task recorder \> Copy**.</span></span>

    ![Kopiera kommando](./media/setup_rsa_tool_92.png)

11. <span data-ttu-id="0f737-524">Ett nytt steg läggs till i fönstret.</span><span class="sxs-lookup"><span data-stu-id="0f737-524">A new step is added in the pane.</span></span> <span data-ttu-id="0f737-525">Anteckna värdet i fältet **produktnummer** eftersom det senare kommer att bli nödvändigt.</span><span class="sxs-lookup"><span data-stu-id="0f737-525">Make a note of the value in the **Product number** field, because you will need it later.</span></span>

    ![Nya steg har lagts till](./media/setup_rsa_tool_93.png)

12. <span data-ttu-id="0f737-527">Välj **Redigeringen är slutförd**.</span><span class="sxs-lookup"><span data-stu-id="0f737-527">Select **Done editing**.</span></span>
13. <span data-ttu-id="0f737-528">Välj **Spara till Lifecycle Services**och koppla den nya uppgiftsinspelningen till samma BPM-bibliotek och affärsprocess som den ursprungliga uppgiftsinspelningen var kopplad till.</span><span class="sxs-lookup"><span data-stu-id="0f737-528">Select **Save to Lifecycle Services**, and associate the new task recording with the same BPM library and business process that the original task recording was associated with.</span></span> <span data-ttu-id="0f737-529">Mer information finns i avsnittet [skapa en uppgiftsinspelning och spara den i BPM-biblioteket](#create-a-task-recording-and-save-it-to-the-bpm-library).</span><span class="sxs-lookup"><span data-stu-id="0f737-529">For more information, see the [Create a task recording and save it to the BPM library](#create-a-task-recording-and-save-it-to-the-bpm-library) section.</span></span>
14. <span data-ttu-id="0f737-530">Gå till BPM-biblioteket och välj **Synkronisera testärenden** om du vill skriva över den uppgiftsinspelning som är kopplad till testfallet i Azure DevOps, enligt beskrivningen i avsnittet [testa synkronisering från BPM till Azure DevOps](#test-the-synchronization-from-bpm-to-azure-devops).</span><span class="sxs-lookup"><span data-stu-id="0f737-530">Go to the BPM library, and select **Sync testcases** to overwrite the task recording that is attached to the test case in Azure DevOps, as described in the [Test the synchronization from BPM to Azure DevOps](#test-the-synchronization-from-bpm-to-azure-devops) section.</span></span>
15. <span data-ttu-id="0f737-531">Öppna RSAT och välj **Läs in** om du vill läsa in alla testfall i testpaketet på nytt.</span><span class="sxs-lookup"><span data-stu-id="0f737-531">Open RSAT, and select **Load** to reload all the test cases in the test suite.</span></span> <span data-ttu-id="0f737-532">Du måste generera om automatiserings- och parameterfiler genom att välja testfall och sedan välja **Ny \> Generera testkörnings- och parameterfiler**, enligt beskrivningen i avsnittet [Läs in och kör testfall](#load-and-run-test-cases).</span><span class="sxs-lookup"><span data-stu-id="0f737-532">You must regenerate the automation and parameter files for the appropriate test case by selecting the test case and then selecting **New \> Generate Test Execution and Parameter files**, as described in the [Load and run test cases](#load-and-run-test-cases) section.</span></span>

    > [!NOTE]
    > <span data-ttu-id="0f737-533">Om Excel-parametern har lämnats öppen kommer omgenereringen att misslyckas.</span><span class="sxs-lookup"><span data-stu-id="0f737-533">If the Excel parameter file was left open, regeneration will fail.</span></span> <span data-ttu-id="0f737-534">Kontrollera därför att Excel-parametern för testfall är stängd innan du genererar den nya parameterfilen för Excel.</span><span class="sxs-lookup"><span data-stu-id="0f737-534">Therefore, make sure that the Excel parameter file for the test case is closed before you generate the new Excel parameter file.</span></span>

16. <span data-ttu-id="0f737-535">Välj **redigera** om du vill öppna den nya Excel-parametern.</span><span class="sxs-lookup"><span data-stu-id="0f737-535">Select **Edit** to open the new Excel parameter file.</span></span> <span data-ttu-id="0f737-536">Du kommer att se en ny post för **Sparad variabel** på rad 9.</span><span class="sxs-lookup"><span data-stu-id="0f737-536">You will see a new **Saved variable** entry on line 9.</span></span> <span data-ttu-id="0f737-537">Den här variabeln, **{{EcoResProductCreate\_Identification\_ProductNumber\_Copy}}** sparas i uppgiftsinspelningens XML-fil och kan användas i efterföljande tester.</span><span class="sxs-lookup"><span data-stu-id="0f737-537">This variable, **{{EcoResProductCreate\_Identification\_ProductNumber\_Copy}}**, is saved in the task recording's XML file and can be used in subsequent tests.</span></span>

    ![Sparad variabelpost](./media/setup_rsa_tool_94.png)

#### <a name="create-a-new-test-case"></a><span data-ttu-id="0f737-539">Skapa ett nytt testfall</span><span class="sxs-lookup"><span data-stu-id="0f737-539">Create a new test case</span></span>

1. <span data-ttu-id="0f737-540">Gå till **RSAT** BPM-biblioteket.</span><span class="sxs-lookup"><span data-stu-id="0f737-540">Go to the **RSAT** BPM library.</span></span>
2. <span data-ttu-id="0f737-541">Välj processen **Sample Support Business Process** och välj **redigeringsläge** till höger.</span><span class="sxs-lookup"><span data-stu-id="0f737-541">Select the **Sample Support Business Process** process, and then, on the right, select **Edit mode**.</span></span>
3. <span data-ttu-id="0f737-542">Ändra värdet för både fältet **Namn** och fältet **Beskrivning** för att **Frisläpp en produkt**.</span><span class="sxs-lookup"><span data-stu-id="0f737-542">Change the value of both the **Name** field and the **Description** field to **Release a product**.</span></span> <span data-ttu-id="0f737-543">Välj sedan **Spara**.</span><span class="sxs-lookup"><span data-stu-id="0f737-543">Then select **Save**.</span></span>

    ![Namn och beskrivning har ändrats till Frisläpp en produkt](./media/setup_rsa_tool_95.png)

#### <a name="create-a-new-task-recording-that-has-a-validate-function"></a><span data-ttu-id="0f737-545">Skapa en ny uppgiftsinspelning som har en valideringsfunktion</span><span class="sxs-lookup"><span data-stu-id="0f737-545">Create a new task recording that has a Validate function</span></span>

- <span data-ttu-id="0f737-546">Skapa en uppgiftsinspelning om du vill frisläppa den produkt som skapades tidigare till den USRT juridiska personen.</span><span class="sxs-lookup"><span data-stu-id="0f737-546">Create a task recording to release the product that was created earlier to the USRT legal entity.</span></span> <span data-ttu-id="0f737-547">Mer information finns i avsnittet [skapa en uppgiftsinspelning och spara den i BPM-biblioteket](#create-a-task-recording-and-save-it-to-the-bpm-library).</span><span class="sxs-lookup"><span data-stu-id="0f737-547">For more information, see the [Create a task recording and save it to the BPM library](#create-a-task-recording-and-save-it-to-the-bpm-library) section.</span></span>

    > [!NOTE]
    > <span data-ttu-id="0f737-548">För sammankopplade testfall rekommenderar vi alltid att du söker efter eller filtrerar posten som du behöver genom att *manuellt skriva värdet i fältet*.</span><span class="sxs-lookup"><span data-stu-id="0f737-548">For chained test cases, we always recommend that you find or filter for the record that you require by *manually typing the value of the field*.</span></span> <span data-ttu-id="0f737-549">På så sätt kan du i verktyget bestämma vilken post som åtgärden måste vidtas mot i det efterföljande testfallet.</span><span class="sxs-lookup"><span data-stu-id="0f737-549">In that way, the tool can determine the record that the action must be taken against in the subsequent test case.</span></span>

    ![Ny uppgiftsinspelning som har en valideringsfunktion](./media/setup_rsa_tool_96.png)

    <span data-ttu-id="0f737-551">Som den föregående visar,efter att produkten hittas genom att använda snabbfiltret, men efter att du har valt **Frisläpp produkter**, måste du validera värdet av fältet **Produktnummer** för att se till att produkt-ID:t är det produkt-ID som skapades tidigare.</span><span class="sxs-lookup"><span data-stu-id="0f737-551">As the preceding illustration shows, after the product is found by using the Quick Filter, but before you select **Release products**, you validate the value of the **Product number** field to make sure that the product ID is the product ID that was created earlier.</span></span> <span data-ttu-id="0f737-552">Om du vill validera värdet högerklickar du på fältet **produktnummer** och väljer sedan **uppgiftsinspelning \> validera \> aktuellt värde**.</span><span class="sxs-lookup"><span data-stu-id="0f737-552">To validate the value, right-click the **Product number** field, and then select **Task recorder \> Validate \> Current Value**.</span></span>

    ![Valider det aktuella värdet](./media/setup_rsa_tool_97.png)

#### <a name="save-the-task-recording-to-bpm"></a><span data-ttu-id="0f737-554">Spara uppgiftsinspelning till BPM</span><span class="sxs-lookup"><span data-stu-id="0f737-554">Save the task recording to BPM</span></span>

1. <span data-ttu-id="0f737-555">När uppgiftsinspelningen har slutförts väljer du **Spara till Lifecycle Services**.</span><span class="sxs-lookup"><span data-stu-id="0f737-555">After the task recording is completed, select **Save to Lifecycle Services**.</span></span>

    ![Alternativ för spara](./media/setup_rsa_tool_98.png)

2. <span data-ttu-id="0f737-557">Biblioteksinformationen läses in från LCS.</span><span class="sxs-lookup"><span data-stu-id="0f737-557">Library information is loaded from LCS.</span></span>

    ![Förloppsindikator](./media/setup_rsa_tool_99.png)

3. <span data-ttu-id="0f737-559">Välj BPM-bibliotek som ska associeras med uppgiftsinspelningen.</span><span class="sxs-lookup"><span data-stu-id="0f737-559">Select the BPM library to associate the task recording with.</span></span> <span data-ttu-id="0f737-560">För den här självstudien väljer du **RSAT** BPM-biblioteket, som skapades tidigare och affärsprocessen **Frisläpp en produkt** under det.</span><span class="sxs-lookup"><span data-stu-id="0f737-560">For this tutorial, select the **RSAT** BPM library that was created earlier and the **Release a product** business process under it.</span></span> <span data-ttu-id="0f737-561">Välj sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="0f737-561">Then select **OK**.</span></span>

#### <a name="sync-bpm-to-azure-devops"></a><span data-ttu-id="0f737-562">Synkronisera BPM till Azure DevOps</span><span class="sxs-lookup"><span data-stu-id="0f737-562">Sync BPM to Azure DevOps</span></span>

1. <span data-ttu-id="0f737-563">Gå till BPM-biblioteket och öppna biblioteket för **RSAT**.</span><span class="sxs-lookup"><span data-stu-id="0f737-563">Go to the BPM library, and open the **RSAT** library.</span></span>
2. <span data-ttu-id="0f737-564">Välj **VSTS-synkronisering** och **synkronisera testfall**.</span><span class="sxs-lookup"><span data-stu-id="0f737-564">Select **VSTS sync** and then **Sync test cases**.</span></span> <span data-ttu-id="0f737-565">Mer information finns i avsnittet [testa synkroniseringen från BPM till Azure DevOps](#test-the-synchronization-from-bpm-to-azure-devops).</span><span class="sxs-lookup"><span data-stu-id="0f737-565">For more information, see the [Test the synchronization from BPM to Azure DevOps](#test-the-synchronization-from-bpm-to-azure-devops) section.</span></span>

    <span data-ttu-id="0f737-566">När synkroniseringen är slutförd visas den nya arbetsuppgiften och motsvarande testfall för affärsprocessen **frisläppa en produkt** som visas i Azure DevOps på **Tavlor \> Arbetsartiklar**.</span><span class="sxs-lookup"><span data-stu-id="0f737-566">After the synchronization is completed, the new work item and the corresponding test case for the **Release a product** business process appear in Azure DevOps at **Boards \> Work Items**.</span></span>

#### <a name="add-the-new-test-case-to-the-existing-test-suite"></a><span data-ttu-id="0f737-567">Lägg till det nya testfallet i det befintliga testpaketet</span><span class="sxs-lookup"><span data-stu-id="0f737-567">Add the new test case to the existing test suite</span></span>

1. <span data-ttu-id="0f737-568">Gå till **testplaner \> testplaner**och markera planen **RSAT-testplan**.</span><span class="sxs-lookup"><span data-stu-id="0f737-568">Go to **Test plans \> Test plans**, and select the **RSAT Test Plan** plan.</span></span>
2. <span data-ttu-id="0f737-569">Välj **Lägg till befintlig**.</span><span class="sxs-lookup"><span data-stu-id="0f737-569">Select **Add existing**.</span></span>
3. <span data-ttu-id="0f737-570">På sidan **Lägg till testfall i paket** väljer du **Kör fråga**.</span><span class="sxs-lookup"><span data-stu-id="0f737-570">On the **Add test cases to suite** page, select **Run query**.</span></span>
4. <span data-ttu-id="0f737-571">Välj det nya testfallet som har skapats för **Frisläppa en produkt** och välj sedan **Lägg testfall** i det nedre högra hörnet på sidan (den här knappen visas inte i bilden nedan).</span><span class="sxs-lookup"><span data-stu-id="0f737-571">Select the new test case that was created for **Release a product**, and then select **Add test cases** in the lower-right corner of the page (this button isn't shown in the following illustration).</span></span>

    ![Lägg till testfall på sidan Paket](./media/setup_rsa_tool_100.png)

    <span data-ttu-id="0f737-573">Testpaketet har nu två testfall.</span><span class="sxs-lookup"><span data-stu-id="0f737-573">The test suite now has two test cases.</span></span>

    ![Två testfall i testpaketet.](./media/setup_rsa_tool_101.png)

#### <a name="load-test-cases-into-rsat"></a><span data-ttu-id="0f737-575">Läs in testfall i RSAT</span><span class="sxs-lookup"><span data-stu-id="0f737-575">Load test cases into RSAT</span></span>

1. <span data-ttu-id="0f737-576">Öppna RSAT och välj **Läs in**.</span><span class="sxs-lookup"><span data-stu-id="0f737-576">Open RSAT, and select **Load**.</span></span>
2. <span data-ttu-id="0f737-577">Testfallen läses in och du får en varning om att "den här åtgärden skriver över Excel-testdatafilerna, lokala ändringar går förlorade.</span><span class="sxs-lookup"><span data-stu-id="0f737-577">The test cases are loaded, and you receive a warning that states, "This action will overwrite Excel test data files, local changes will be lost.</span></span> <span data-ttu-id="0f737-578">Vill du fortsätta?"</span><span class="sxs-lookup"><span data-stu-id="0f737-578">Do you want to proceed?"</span></span> <span data-ttu-id="0f737-579">Välj **ja** om du vill uppdatera Excel-parametervärdena i det lokala systemet, men inte de Excel-parametervärden som överförts till Azure DevOps.</span><span class="sxs-lookup"><span data-stu-id="0f737-579">Select **Yes** to update the Excel parameter files in the local system but not the Excel parameter files that were uploaded to Azure DevOps.</span></span>

    ![Varningsmeddelande](./media/setup_rsa_tool_102.png)

    <span data-ttu-id="0f737-581">Båda testfallen läses in, tillsammans med Excel-parametern för det första testfallet.</span><span class="sxs-lookup"><span data-stu-id="0f737-581">Both the test cases are loaded, together with the Excel parameter file for the first test case.</span></span> <span data-ttu-id="0f737-582">Eftersom du valde **överför** i den senaste körningen hämtas parametervärdena från Azure DevOps.</span><span class="sxs-lookup"><span data-stu-id="0f737-582">Because you selected **Upload** in the last run, the parameter files are pulled from Azure DevOps.</span></span>

    ![Testfall har lästs in](./media/setup_rsa_tool_103.png)

3. <span data-ttu-id="0f737-584">Markera bara det andra testfallet och välj sedan **ny \> generera testkörning och parameterstyrda filer**.</span><span class="sxs-lookup"><span data-stu-id="0f737-584">Select only the second test case, and then select **New \> Generate test execution and parameter files**.</span></span>

#### <a name="edit-the-excel-parameter-file"></a><span data-ttu-id="0f737-585">Redigera Excel-parameterfilen.</span><span class="sxs-lookup"><span data-stu-id="0f737-585">Edit the Excel parameter file</span></span>

1. <span data-ttu-id="0f737-586">Markera endast det andra testfallet och välj sedan **redigera** för att öppna motsvarande Excel-parameterfil.</span><span class="sxs-lookup"><span data-stu-id="0f737-586">Select only the second test case, and then select **Edit** to open the corresponding Excel parameter file.</span></span>
2. <span data-ttu-id="0f737-587">Kopiera **{{EcoResProductCreate\_Identification\_ProductNumber\_Copy}}** sparad variabel (se avsnittet [Ändra en befintlig uppgiftsinspelning för att skapa en sparad variabel](#modify-an-existing-task-recording-to-create-a-saved-variable)) från det första testfallet till alla fält där produktnumret används.</span><span class="sxs-lookup"><span data-stu-id="0f737-587">Copy the **{{EcoResProductCreate\_Identification\_ProductNumber\_Copy}}** saved variable (see the [Modify an existing task recording to create a saved variable](#modify-an-existing-task-recording-to-create-a-saved-variable) section) from the first test case into all the fields where the product number is used.</span></span> <span data-ttu-id="0f737-588">I det här fallet kopierar du variabeln till fälten **produktnummer** och **validera produktnummer** på arket **EcoResProductListPage**.</span><span class="sxs-lookup"><span data-stu-id="0f737-588">In this case, you copy the variable into the **Product number** and **Validate Product number** fields on the **EcoResProductListPage** sheet.</span></span>

    ![Fält för produktnummer och validera produktnummer](./media/setup_rsa_tool_104.png)

    > [!NOTE]
    > <span data-ttu-id="0f737-590">Variabler kan bara skickas mellan tester under samma testkörning.</span><span class="sxs-lookup"><span data-stu-id="0f737-590">Variables can be passed between tests only during the same test run.</span></span> <span data-ttu-id="0f737-591">Namnen på variablerna måste matcha exakt.</span><span class="sxs-lookup"><span data-stu-id="0f737-591">The names of the variables must match exactly.</span></span>

3. <span data-ttu-id="0f737-592">Markera **Spara** och stäng sedan Excel-arbetsboken.</span><span class="sxs-lookup"><span data-stu-id="0f737-592">Select **Save**, and then close the Excel workbook.</span></span>
4. <span data-ttu-id="0f737-593">Välj **överför** om du vill spara ändringarna som du gjorde i Excel-parameterfilen.</span><span class="sxs-lookup"><span data-stu-id="0f737-593">Select **Upload** to save the changes that you made to the Excel parameter file.</span></span>

#### <a name="run-the-chained-test-cases"></a><span data-ttu-id="0f737-594">Kör kedjetestfallen</span><span class="sxs-lookup"><span data-stu-id="0f737-594">Run the chained test cases</span></span>

1. <span data-ttu-id="0f737-595">Välj båda testfallen och välj sedan **kör**.</span><span class="sxs-lookup"><span data-stu-id="0f737-595">Select both the test cases, and then select **Run**.</span></span>
2. <span data-ttu-id="0f737-596">Kontrollera att båda testfallen har godkänts.</span><span class="sxs-lookup"><span data-stu-id="0f737-596">Verify that both test cases have passed.</span></span>

    ![Resultatfältet har godkänts för båda testfallen](./media/setup_rsa_tool_105.png)
