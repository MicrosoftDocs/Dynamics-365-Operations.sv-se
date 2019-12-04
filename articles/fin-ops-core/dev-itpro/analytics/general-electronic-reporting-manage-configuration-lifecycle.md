---
title: Hantera livscykeln för konfiguration av elektronisk rapportering (ER)
description: Den här avsnittet beskriver hur du hanterar livscykeln för elektronisk rapportering (ER) konfigurationer för Microsoft Dynamics 365 Finance-lösningen.
author: NickSelin
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERMappedFormatDesigner, ERModelMappingDesigner, ERModelMappingTable, ERSolutionImport, ERSolutionTable, ERVendorTable, ERWorkspace
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 58801
ms.assetid: 35ad19ea-185d-4fce-b9cb-f94584b14f75
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ecaeb80f3cda2ee24533ed263df63cc10c5ffc65
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/06/2019
ms.locfileid: "2771106"
---
# <a name="manage-the-electronic-reporting-er-configuration-lifecycle"></a><span data-ttu-id="537ef-103">Hantera livscykeln för konfiguration av elektronisk rapportering (ER)</span><span class="sxs-lookup"><span data-stu-id="537ef-103">Manage the Electronic reporting (ER) configuration lifecycle</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="537ef-104">Den här avsnittet beskriver hur du hanterar livscykeln för elektronisk rapportering (ER) konfigurationer för Microsoft Dynamics 365 Finance.</span><span class="sxs-lookup"><span data-stu-id="537ef-104">This topic describes how to manage the lifecycle of Electronic reporting (ER) configurations for Microsoft Dynamics 365 Finance.</span></span>

## <a name="overview"></a><span data-ttu-id="537ef-105">Översikt</span><span class="sxs-lookup"><span data-stu-id="537ef-105">Overview</span></span>

<span data-ttu-id="537ef-106">Elektronisk rapportering (ER) är en motor som stöder lagstadgade behov och landsspecifika elektroniska dokument.</span><span class="sxs-lookup"><span data-stu-id="537ef-106">Electronic reporting (ER) is an engine that supports statutory required and country-specific electronic documents.</span></span> <span data-ttu-id="537ef-107">I allmänhet förutsätter ER en förmåga att utföra följande uppgifter för ett enstaka elektroniskt dokument.</span><span class="sxs-lookup"><span data-stu-id="537ef-107">In general, ER assumes an ability to perform the following tasks for a single electronic document.</span></span> <span data-ttu-id="537ef-108">Mer information finns i [översikt för (ER) elektronisk rapportering](general-electronic-reporting.md).</span><span class="sxs-lookup"><span data-stu-id="537ef-108">For more details, see [Electronic reporting (ER) overview](general-electronic-reporting.md).</span></span>

- <span data-ttu-id="537ef-109">Designa en mall för ett elektroniskt dokument:</span><span class="sxs-lookup"><span data-stu-id="537ef-109">Design a template for an electronic document:</span></span>

    - <span data-ttu-id="537ef-110">Identifiera nödvändiga datakällor som kan presenteras i detta dokument:</span><span class="sxs-lookup"><span data-stu-id="537ef-110">Identify the required sources of data that can be presented in the document:</span></span>

        - <span data-ttu-id="537ef-111">Underliggande data, till exempel dataregister, dataentiteter och klasser.</span><span class="sxs-lookup"><span data-stu-id="537ef-111">Underlying data, such as data tables, data entities, and classes.</span></span>
        - <span data-ttu-id="537ef-112">Processens särskilda egenskaper, till exempel utförandedatum och tid och tidszon.</span><span class="sxs-lookup"><span data-stu-id="537ef-112">Process-specific properties, such as execution date and time, and time zone.</span></span>
        - <span data-ttu-id="537ef-113">Användarindataparametrar som anges av slutanvändaren vid körtid.</span><span class="sxs-lookup"><span data-stu-id="537ef-113">User input parameters, specified by the end user at run time.</span></span>

    - <span data-ttu-id="537ef-114">Definiera nödvändiga dokument, liksom deras topologi för att specificera ett slutligt dokumentformat.</span><span class="sxs-lookup"><span data-stu-id="537ef-114">Define the required document elements and their topology to specify a final document format.</span></span>
    - <span data-ttu-id="537ef-115">Konfigurera önskat flöde av data från utvalda datakällor för att definiera dokumentets element (via datakällbindningar till dokumentets formatkomponenter) och ange processkontrollogik.</span><span class="sxs-lookup"><span data-stu-id="537ef-115">Configure the desired flow of data from selected data sources to defined document elements (via data source bindings to document format components), and specify process control logic.</span></span>

- <span data-ttu-id="537ef-116">Gör en mall tillgänglig så att den kan användas i andra instanser:</span><span class="sxs-lookup"><span data-stu-id="537ef-116">Make a template available so that it can be used in other instances:</span></span>

    - <span data-ttu-id="537ef-117">Omforma en dokumentmall som har skapats till en ER-konfiguration och exportera konfigurationen från den aktuella appinstansen som ett XML-paket som antingen kan lagras lokalt eller i LCS.</span><span class="sxs-lookup"><span data-stu-id="537ef-117">Transform a document template that was created into an ER configuration, and export the configuration from the current application instance as an XML package that can be stored either locally or in LCS.</span></span>
    - <span data-ttu-id="537ef-118">Omforma en ER-konfiguration till en dokumentmall för appar.</span><span class="sxs-lookup"><span data-stu-id="537ef-118">Transform an ER configuration into an application document template.</span></span>
    - <span data-ttu-id="537ef-119">Importera ett XML-paket som lagras lokalt antingen eller i LCS till den aktuella instansen.</span><span class="sxs-lookup"><span data-stu-id="537ef-119">Import an XML package that is stored either locally or in LCS into the current instance.</span></span>

- <span data-ttu-id="537ef-120">Anpassa en mall för ett elektroniskt dokument:</span><span class="sxs-lookup"><span data-stu-id="537ef-120">Customize the template of an electronic document:</span></span>

    - <span data-ttu-id="537ef-121">Hämta en mall från LCS till nuvarande instansen som en ER-konfiguration.</span><span class="sxs-lookup"><span data-stu-id="537ef-121">Bring a template from LCS into the current instance as an ER configuration.</span></span>
    - <span data-ttu-id="537ef-122">Utforma en anpassad version av en ER-konfiguration och behåll en hänvisning till basversionen.</span><span class="sxs-lookup"><span data-stu-id="537ef-122">Design a custom version of an ER configuration, and keep a reference to the base version.</span></span>

- <span data-ttu-id="537ef-123">Integrera en mall med en viss arbetsprocess så att den är tillgänglig i appen:</span><span class="sxs-lookup"><span data-stu-id="537ef-123">Integrate a template with a particular business process, so that it's available in the application:</span></span>

    - <span data-ttu-id="537ef-124">Konfigurera inställningar så att appen börjar använda en ER-konfiguration, detta genom att referera till konfigurationen i en processrelaterad parameter.</span><span class="sxs-lookup"><span data-stu-id="537ef-124">Configure settings so that the application starts to use an ER configuration, by referring to that configuration in a process-related parameter.</span></span> <span data-ttu-id="537ef-125">Till exempel, referera till ER-konfigurationen i en viss leverantörsreskontrabetalningsmetod för att skapa ett meddelande för elektronisk betalning för bearbetning av fakturor.</span><span class="sxs-lookup"><span data-stu-id="537ef-125">For example, refer to the ER configuration in a specific Accounts payable payment method to generate an electronic payment message for processing invoices.</span></span>

- <span data-ttu-id="537ef-126">Använd en mall i en viss affärsprocess.:</span><span class="sxs-lookup"><span data-stu-id="537ef-126">Use a template in a specific business process:</span></span>

    - <span data-ttu-id="537ef-127">Köra en ER-konfiguration i en specifik affärsprocess.</span><span class="sxs-lookup"><span data-stu-id="537ef-127">Run an ER configuration in a specific business process.</span></span> <span data-ttu-id="537ef-128">Till exempel, referera till ER-konfigurationen i en viss leverantörsreskontrabetalningsmetod när en betalningsmetod som hänvisar till en av ER-konfiguration är vald.</span><span class="sxs-lookup"><span data-stu-id="537ef-128">For example, to generate an electronic payment message for processing invoices when a payment method that references the ER configuration is selected.</span></span>

## <a name="concepts"></a><span data-ttu-id="537ef-129">Begrepp</span><span class="sxs-lookup"><span data-stu-id="537ef-129">Concepts</span></span>
<span data-ttu-id="537ef-130">Följande roller och relaterade aktiviteter är associerade med ER-konfigurationslivscykeln.</span><span class="sxs-lookup"><span data-stu-id="537ef-130">The following roles and related activities are associated with the ER configuration lifecycle.</span></span>

| <span data-ttu-id="537ef-131">Roll</span><span class="sxs-lookup"><span data-stu-id="537ef-131">Role</span></span>                                       | <span data-ttu-id="537ef-132">Aktiviteter</span><span class="sxs-lookup"><span data-stu-id="537ef-132">Activities</span></span>                                                      | <span data-ttu-id="537ef-133">beskrivning</span><span class="sxs-lookup"><span data-stu-id="537ef-133">Description</span></span> |
|--------------------------------------------|-----------------------------------------------------------------|-------------|
| <span data-ttu-id="537ef-134">Konsult för funktionen för elektronisk rapportering</span><span class="sxs-lookup"><span data-stu-id="537ef-134">Electronic reporting functional consultant</span></span> | <span data-ttu-id="537ef-135">Skapa och hantera ER-komponenter (modeller och format).</span><span class="sxs-lookup"><span data-stu-id="537ef-135">Create and manage ER components (models and formats).</span></span>           | <span data-ttu-id="537ef-136">En affärsrörelsemänniska som designar modeller för ER-domänspecifika data, utformar önskade mallar för elektroniska dokument och binder dem.</span><span class="sxs-lookup"><span data-stu-id="537ef-136">A business person who designs ER domain–specific data models, designs the required templates for electronic documents, and binds them accordingly.</span></span> |
| <span data-ttu-id="537ef-137">Utvecklare för elektronisk rapportering</span><span class="sxs-lookup"><span data-stu-id="537ef-137">Electronic reporting developer</span></span>             | <span data-ttu-id="537ef-138">Skapa och hantera mappningar för datamodellen.</span><span class="sxs-lookup"><span data-stu-id="537ef-138">Create and manage data model mappings.</span></span>                          | <span data-ttu-id="537ef-139">En specialist som väljer de önskade Finance datakällorna och binder dem till ER-domänspecifika datamodeller.</span><span class="sxs-lookup"><span data-stu-id="537ef-139">A specialist who selects the required Finance data sources and binds them to ER domain–specific data models.</span></span> |
| <span data-ttu-id="537ef-140">Redovisningsansvarig</span><span class="sxs-lookup"><span data-stu-id="537ef-140">Accounting supervisor</span></span>                      | <span data-ttu-id="537ef-141">Konfigurera processrelaterade inställningar som refererar till ER-artefakter.</span><span class="sxs-lookup"><span data-stu-id="537ef-141">Configure process-related settings that reference ER artifacts.</span></span> | <span data-ttu-id="537ef-142">Till exempel, en **redovisningsansvarig**-roll som tillåter inställningarna för en ER-konfiguration att användas i en viss leverantörsreskontrabetalningsmetod för att skapa ett meddelande för elektronisk betalning för bearbetning av fakturor</span><span class="sxs-lookup"><span data-stu-id="537ef-142">For example, an **Accounting supervisor** role that allows the settings of an ER configuration to be used in a particular Accounts payable payment method to generate an electronic payment message for processing invoices.</span></span> |
| <span data-ttu-id="537ef-143">Ansvarig för leverantörsreskontrabetalningar</span><span class="sxs-lookup"><span data-stu-id="537ef-143">Accounts payable payments clerk</span></span>            | <span data-ttu-id="537ef-144">Använda ER-artefakter i en viss affärsprocess.</span><span class="sxs-lookup"><span data-stu-id="537ef-144">Use ER artifacts in a specific business process.</span></span>                | <span data-ttu-id="537ef-145">Till exempel, **Ansvarig för leverantörsreskontrabetalningar**-rollen som gör att meddelanden för elektroniska betalningar skapas för att bearbeta fakturor som baseras på ER-formatet som konfigureras för en viss betalningsmetod.</span><span class="sxs-lookup"><span data-stu-id="537ef-145">For example, an **Accounts payable payments clerk** role that allows electronic payment messages to be generated for processing invoices, based on the ER format that is configured for a specific payment method.</span></span> |

## <a name="er-configuration-development-lifecycle"></a><span data-ttu-id="537ef-146">Livscykel för ER-konfigurationsutveckling</span><span class="sxs-lookup"><span data-stu-id="537ef-146">ER configuration development lifecycle</span></span>
<span data-ttu-id="537ef-147">För följande ER-relaterade orsaker rekommenderas att du designar ER-konfigurationer i utvecklingsmiljön som en separat instans av Finance and Operations:</span><span class="sxs-lookup"><span data-stu-id="537ef-147">For the following ER-related reasons, we recommend that you design ER configurations in the development environment, as a separate instance of Finance and Operations:</span></span>

- <span data-ttu-id="537ef-148">Användare i antingen rollen **elektronisk rapportering utvecklare** eller **elektronisk rapportering funktionella konsult** kan redigera konfigurationer och köra dem för teständamål.</span><span class="sxs-lookup"><span data-stu-id="537ef-148">Users in either the **Electronic reporting developer** role or the **Electronic reporting functional consultant** role can edit configurations and run them for testing purposes.</span></span> <span data-ttu-id="537ef-149">Det här scenariot kan orsaka anrop av metoder för klasser och tabeller som kan vara skadliga för affärsdata och instansens prestanda.</span><span class="sxs-lookup"><span data-stu-id="537ef-149">This scenario can cause calls of methods of classes and tables that might harm business data and the performance of the instance.</span></span>
- <span data-ttu-id="537ef-150">Anrop av metoder för klasser och tabeller som ER-datakällor eller ER-konfigurationer är inte begränsade av startpunkter och loggat företagsinnehåll.</span><span class="sxs-lookup"><span data-stu-id="537ef-150">Calls of methods of classes and tables as ER data sources of ER configurations aren't restricted by entry points and logged company content.</span></span> <span data-ttu-id="537ef-151">Därför känslig affärsinformation kan nås av användarna i antingen **elektronisk rapportering utvecklare** eller **elektronisk rapportering funktionella konsult**.</span><span class="sxs-lookup"><span data-stu-id="537ef-151">Therefore, users in either the **Electronic reporting developer** role or the **Electronic reporting functional consultant** role can access business-sensitive data.</span></span>

<span data-ttu-id="537ef-152">ER-konfigurationer som utformas i utvecklingsmiljön kan överföras till testmiljön för utvärdering av konfigurationen (rätt process integration, korrekta resultat, prestanda) och kvalitetssäkring, till exempel korrektheten i rollen som drivs av åtkomsträttigheter och uppdelning av uppgifter.</span><span class="sxs-lookup"><span data-stu-id="537ef-152">ER configurations that are designed in the development environment can be uploaded to the test environment for the configuration evaluation (proper process integration, correctness of results, and performance) and quality assurance, such as correctness of role-driven access rights and segregation of duties.</span></span> <span data-ttu-id="537ef-153">Funktionerna som aktiverar ER-konfigurationsutbyte kan användas i detta syfte.</span><span class="sxs-lookup"><span data-stu-id="537ef-153">The features that enable ER configuration interchange can be used for this purpose.</span></span> <span data-ttu-id="537ef-154">Slutligen kan beprövade ER-konfigurationer överföras antingen till LCS där de kan delas med abonnenter eller till produktionsmiljön för intern användning, som visas i följande bild.</span><span class="sxs-lookup"><span data-stu-id="537ef-154">Finally, proven ER configurations can be uploaded either to LCS, where they can be shared with service subscribers, or to the production environment for internal use, such as shown in the following illustration.</span></span>

![Livscykel för ER-konfiguration](./media/ger-configuration-lifecycle.png)

## <a name="additional-resources"></a><span data-ttu-id="537ef-156">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="537ef-156">Additional resources</span></span>

[<span data-ttu-id="537ef-157">Översikt över elektronisk rapportering (ER)</span><span class="sxs-lookup"><span data-stu-id="537ef-157">Electronic reporting (ER) overview</span></span>](general-electronic-reporting.md)
