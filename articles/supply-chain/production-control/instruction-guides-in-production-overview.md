---
title: Tillhandahålla guider för mixad verklighet för arbetare i produktion
description: I det här avsnittet beskrivs hur du integrerar modulen för produktionshantering i Microsoft Dynamics 365 Supply Chain Management med Dynamics 365 Guides.
author: cabeln
ms.date: 11/13/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WorkGuidesManufacturing
audience: Application User
ms.reviewer: kamaybac
ms.custom: 61943
ms.assetid: a3847f07-fca4-4140-a26f-d83c6ac68dde
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: cabeln
ms.search.validFrom: 2020-08-01
ms.dyn365.ops.version: AX 10.0.15
ms.openlocfilehash: 59fe3996013737198d4fbc86d64f8ef9dbe035e4
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5829364"
---
# <a name="provide-mixed-reality-guides-for-workers-in-production"></a><span data-ttu-id="9d871-103">Tillhandahålla guider för mixad verklighet för arbetare i produktion</span><span class="sxs-lookup"><span data-stu-id="9d871-103">Provide mixed-reality Guides for workers in production</span></span>

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="9d871-104">Arbetare i produktionsprocesser kommer att ha nytta av relevanta instruktioner som ges vid rätt tid inom ramen för deras arbete.</span><span class="sxs-lookup"><span data-stu-id="9d871-104">Workers in production processes will benefit from relevant instructions that are provided at the right time in the context of their work.</span></span> <span data-ttu-id="9d871-105">*Instruktionerna* gäller i flera arbetsdomäner, t.ex. sammansättning, service, åtgärder, certifiering och säkerhet.</span><span class="sxs-lookup"><span data-stu-id="9d871-105">*Instructions* apply in several domains of work, including: assembly, service, operations, certification, and safety.</span></span> <span data-ttu-id="9d871-106">I alla dessa grundläggande affärsfunktioner kan de pågående utbildningsinstruktionerna hjälpa medarbetarna att utföra mer och arbeta bättre.</span><span class="sxs-lookup"><span data-stu-id="9d871-106">Across all of these core business functions, ongoing training instructions can help empower workers to achieve more and work better.</span></span>

## <a name="introduction"></a><span data-ttu-id="9d871-107">Introduktion</span><span class="sxs-lookup"><span data-stu-id="9d871-107">Introduction</span></span>

<span data-ttu-id="9d871-108">Du kan ange instruktioner på olika sätt.</span><span class="sxs-lookup"><span data-stu-id="9d871-108">You can provide instructions in different ways.</span></span> <span data-ttu-id="9d871-109">Ett effektivt system som levereras utanför kartongen använder [Dynamics 365 Guides](https://dynamics.microsoft.com/mixed-reality/guides/).</span><span class="sxs-lookup"><span data-stu-id="9d871-109">One efficient system that ships out of the box uses [Dynamics 365 Guides](https://dynamics.microsoft.com/mixed-reality/guides/).</span></span>

<span data-ttu-id="9d871-110">Dynamics 365 Guides kan hjälpa dina anställda med praktisk utbildning.</span><span class="sxs-lookup"><span data-stu-id="9d871-110">Dynamics 365 Guides can help empower your employees with hands-on learning.</span></span> <span data-ttu-id="9d871-111">Du kan definiera standardiserade processer med steg-för-steg-instruktioner som vägleder dina medarbetare till de verktyg och delar de behöver och visa anställda hur de kan använda verktygen i verkliga arbetssituationer.</span><span class="sxs-lookup"><span data-stu-id="9d871-111">You can define standardized processes with step-by-step instructions that guide your employees to the tools and parts they need and show employees how to use these tools in real work situations.</span></span>

<span data-ttu-id="9d871-112">Du kan koppla layoutstöd till olika aspekter av produktionsstyrningen inklusive:</span><span class="sxs-lookup"><span data-stu-id="9d871-112">You can attach guides to various aspects of production control including:</span></span>

- [<span data-ttu-id="9d871-113">Resurser</span><span class="sxs-lookup"><span data-stu-id="9d871-113">Resources</span></span>](#resources)
- [<span data-ttu-id="9d871-114">Resursgrupper</span><span class="sxs-lookup"><span data-stu-id="9d871-114">Resource groups</span></span>](#resource-groups)
- [<span data-ttu-id="9d871-115">Frisläppta produkter</span><span class="sxs-lookup"><span data-stu-id="9d871-115">Released products</span></span>](#released-products)
- [<span data-ttu-id="9d871-116">Formler</span><span class="sxs-lookup"><span data-stu-id="9d871-116">Formulas</span></span>](#formulas)
- [<span data-ttu-id="9d871-117">Formelversioner</span><span class="sxs-lookup"><span data-stu-id="9d871-117">Formula versions</span></span>](#formula-versions)
- [<span data-ttu-id="9d871-118">Strukturlista</span><span class="sxs-lookup"><span data-stu-id="9d871-118">Bills of material (BOMs)</span></span>](#bom)
- [<span data-ttu-id="9d871-119">Strukturlisteversioner</span><span class="sxs-lookup"><span data-stu-id="9d871-119">BOM versions</span></span>](#bom-versions)
- [<span data-ttu-id="9d871-120">Rutter</span><span class="sxs-lookup"><span data-stu-id="9d871-120">Routes</span></span>](#routes)
- [<span data-ttu-id="9d871-121">Flödesversioner</span><span class="sxs-lookup"><span data-stu-id="9d871-121">Route versions</span></span>](#route-versions)
- [<span data-ttu-id="9d871-122">Flödesoperationsrelation</span><span class="sxs-lookup"><span data-stu-id="9d871-122">Route operation relations</span></span>](#route-operation-relations)

> [!NOTE]
> <span data-ttu-id="9d871-123">Du kan också koppla guider med tillgångshantering.</span><span class="sxs-lookup"><span data-stu-id="9d871-123">You can also attach Guides with Asset Management.</span></span> <span data-ttu-id="9d871-124">För mer information om det alternativet, se [Integrera Dynamics 365 Supply Chain Management (tillgångshantering) med Dynamics 365 Guides](../asset-management/asset-management-guides-integration.md).</span><span class="sxs-lookup"><span data-stu-id="9d871-124">For more information about that option, see [Integrate Dynamics 365 Supply Chain Management (Asset Management) with Dynamics 365 Guides](../asset-management/asset-management-guides-integration.md).</span></span>

<span data-ttu-id="9d871-125">När en medarbetare i första ledet väljer ett jobb på verkstadsgolvet med hjälp av Supply Chain Management kan medarbetaren se [relevanta handböcker](#logic) på jobbkortet.</span><span class="sxs-lookup"><span data-stu-id="9d871-125">When a first-line worker chooses a job on the shop floor through Supply Chain Management, the worker can see [the relevant guides](#logic) on the job card.</span></span> <span data-ttu-id="9d871-126">När arbetaren väljer en viss guide visas en QR-kod för denna guide på skärmen.</span><span class="sxs-lookup"><span data-stu-id="9d871-126">When the worker chooses a specific guide, a QR code for that guide is shown on the screen.</span></span> <span data-ttu-id="9d871-127">Arbetaren använder sedan sin HoloLens för att skanna QR-koden, som startar guider och visar de instruktioner som krävs.</span><span class="sxs-lookup"><span data-stu-id="9d871-127">The worker then uses their HoloLens to scan the QR code, which launches Guides and shows the required instructions.</span></span>

<span data-ttu-id="9d871-128">Följande underavsnitt beskriver några utvalda scenarier där företag över branscher kan se störst värde när man använder guider för att presentera tillverkningsinstruktioner.</span><span class="sxs-lookup"><span data-stu-id="9d871-128">The following subsections describe a few selected scenarios where companies across industries can see the biggest value when using Guides to present instructions for manufacturing.</span></span>

### <a name="assembly"></a><span data-ttu-id="9d871-129">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="9d871-129">Assembly</span></span>

<span data-ttu-id="9d871-130">![Använda guider i monteringsuppgifter](media/instruction-guides-hero-assembly.png "Använda guider i serviceuppgifter")</span><span class="sxs-lookup"><span data-stu-id="9d871-130">![Use Guides in assembly tasks](media/instruction-guides-hero-assembly.png "Use Guides in service tasks")</span></span>

<span data-ttu-id="9d871-131">Instruktioner i monteringsoperationer visar arbetare vilka verktyg och delar de behöver och hur de ska användas i realtidssituationer.</span><span class="sxs-lookup"><span data-stu-id="9d871-131">Instructions in assembly operations show workers the tools and parts they need and how to use them in real work situations.</span></span>

<span data-ttu-id="9d871-132">Produktionschefer kan t.ex. skapa och tilldela guider för [produktionsflöden](routes-operations.md), [operationsrelationer](routes-operations.md#operation-relations) eller [strukturlistor](bill-of-material-bom.md).</span><span class="sxs-lookup"><span data-stu-id="9d871-132">Production managers can create and assign Guides, for example, for [production routes](routes-operations.md), [operation relations](routes-operations.md#operation-relations), or [bills of material](bill-of-material-bom.md).</span></span> <span data-ttu-id="9d871-133">Medarbetarna kommer att hitta de relevanta instruktionerna om respektive operationserfarenhet på verkstadsgolvet.</span><span class="sxs-lookup"><span data-stu-id="9d871-133">Workers will find the relevant instructions on the respective operation experience on the shop floor.</span></span>

### <a name="service"></a><span data-ttu-id="9d871-134">Service</span><span class="sxs-lookup"><span data-stu-id="9d871-134">Service</span></span>

<span data-ttu-id="9d871-135">![Använda guider i serviceuppgifter](media/instruction-guides-hero-service.png "Använda guider i serviceuppgifter")</span><span class="sxs-lookup"><span data-stu-id="9d871-135">![Use Guides in service tasks](media/instruction-guides-hero-service.png "Use Guides in service tasks")</span></span>

<span data-ttu-id="9d871-136">Utrusta tekniker med guidade instruktioner på arbetsplatsen, vilket eliminerar behovet av att schemalägga ytterligare besök.</span><span class="sxs-lookup"><span data-stu-id="9d871-136">Equip technicians with guided instructions at the job site, eliminating the need to schedule additional visits.</span></span>

<span data-ttu-id="9d871-137">Serviceansvariga kan till exempel tilldela guider till specifika [produkter](../../commerce/product.md) som går igenom rutinerna för kvalitetsbedömning.</span><span class="sxs-lookup"><span data-stu-id="9d871-137">Service managers can assign Guides, for example, to specific [products](../../commerce/product.md) that walk through routines of quality assessment.</span></span>

### <a name="quality"></a><span data-ttu-id="9d871-138">Kvalitet</span><span class="sxs-lookup"><span data-stu-id="9d871-138">Quality</span></span>

<span data-ttu-id="9d871-139">![Använda guider i kvalitetssäkringsuppgifter](media/instruction-guides-hero-quality.png "Använda guider i kvalitetssäkringsuppgifter")</span><span class="sxs-lookup"><span data-stu-id="9d871-139">![Use Guides in quality assurance tasks](media/instruction-guides-hero-quality.png "Use Guides in quality assurance tasks")</span></span>

<span data-ttu-id="9d871-140">Lansering av nya processer och bättre överensstämmelse genom att göra medarbetarnas kunskaper i ett repeterbart verktyg.</span><span class="sxs-lookup"><span data-stu-id="9d871-140">Rollout new processes and ensure increased consistency by turning employee knowledge into a repeatable tool.</span></span>

<span data-ttu-id="9d871-141">Kvalitetssäkringsansvariga kan tilldela guider till [produkter](../../commerce/product.md) som går igenom rutinerna för kvalitetsbedömning.</span><span class="sxs-lookup"><span data-stu-id="9d871-141">Quality assurance managers can assign guides, for example, to [products](../../commerce/product.md) that walk through routines of quality assessment.</span></span>

### <a name="certifications"></a><span data-ttu-id="9d871-142">Intyg</span><span class="sxs-lookup"><span data-stu-id="9d871-142">Certifications</span></span>

<span data-ttu-id="9d871-143">![Använda guider för uppgifter som rör certifiering](media/instruction-guides-hero-certification.png "Använda guider för uppgifter som rör certifiering")</span><span class="sxs-lookup"><span data-stu-id="9d871-143">![Use Guides for certification related tasks](media/instruction-guides-hero-certification.png "Use Guides for certification related tasks")</span></span>

<span data-ttu-id="9d871-144">Se till att alla medarbetare uppfyller höga standarder genom att snabbt identifiera vem som behöver hjälp och var.</span><span class="sxs-lookup"><span data-stu-id="9d871-144">Ensure every employee meets high standards by quickly identifying who needs help and where.</span></span>

### <a name="safety"></a><span data-ttu-id="9d871-145">Säkerhet</span><span class="sxs-lookup"><span data-stu-id="9d871-145">Safety</span></span>

<span data-ttu-id="9d871-146">![Använda guider i instruktioner om arbetssäkerhet](media/instruction-guides-hero-safety.png "Använda guider i instruktioner om arbetssäkerhet")</span><span class="sxs-lookup"><span data-stu-id="9d871-146">![Use Guides in work safety instructions](media/instruction-guides-hero-safety.png "Use Guides in work safety instructions")</span></span>

<span data-ttu-id="9d871-147">Ge instruktioner för hur du ska gå igenom de farliga procedurerna i stort innan du försöker göra det i den fysiska miljön.</span><span class="sxs-lookup"><span data-stu-id="9d871-147">Provide instructions that walk through dangerous procedures virtually before attempting in the physical environment.</span></span> <span data-ttu-id="9d871-148">Med en blandad verklighet kan medarbetarna uppleva farliga procedurer i princip.</span><span class="sxs-lookup"><span data-stu-id="9d871-148">With a mixed reality approach, workers can experience dangerous procedures virtually.</span></span>

<span data-ttu-id="9d871-149">Produktionschefer kan tillhandahålla dedikerade hanteringsinstruktioner för hantering av farliga material och ömtåliga genom att tilldela instruktioner till [produktartiklar](../../commerce/product.md), [flöden](routes-operations.md) och [operationer](routes-operations.md#operation-relations).</span><span class="sxs-lookup"><span data-stu-id="9d871-149">Production managers can provide dedicated handling instructions for hazardous material handling or delicate handling procedures by assigning instructions to [product items](../../commerce/product.md), [routes](routes-operations.md), and [operations](routes-operations.md#operation-relations).</span></span>

## <a name="get-started-with-instructions-and-guides"></a><span data-ttu-id="9d871-150">Komma igång med instruktioner och guider</span><span class="sxs-lookup"><span data-stu-id="9d871-150">Get started with instructions and Guides</span></span>

<span data-ttu-id="9d871-151">Om du vill aktivera instruktioner i produktionsprocesser tillhandahåller Supply Chain Management en medföljande integration i Dynamics 365 Guides.</span><span class="sxs-lookup"><span data-stu-id="9d871-151">To enable instructions in production processes, Supply Chain Management provides an out-of-the-box integration with Dynamics 365 Guides.</span></span> <span data-ttu-id="9d871-152">En licensierad och installerad appinstans av Guides krävs för att skapa, underhålla och tilldela instruktioner till produktion och arbete i mixad verklighet.</span><span class="sxs-lookup"><span data-stu-id="9d871-152">A licensed and installed application instance of Guides is required to build, maintain, and assign mixed reality instructions to production assets and work.</span></span>

### <a name="prerequisites"></a><span data-ttu-id="9d871-153">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="9d871-153">Prerequisites</span></span>

<span data-ttu-id="9d871-154">För att du ska kunna använda den här funktionen måste systemet innehålla följande:</span><span class="sxs-lookup"><span data-stu-id="9d871-154">To use this feature, your system must include the following:</span></span>

- <span data-ttu-id="9d871-155">Dynamics 365 Supply Chain Management version 10.0.15 eller senare</span><span class="sxs-lookup"><span data-stu-id="9d871-155">Dynamics 365 Supply Chain Management version 10.0.15 or later</span></span>
- <span data-ttu-id="9d871-156">[Dubbelriktad skrivning](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/enable-dual-write) för Supply Chain Management-appar.</span><span class="sxs-lookup"><span data-stu-id="9d871-156">[Dual-write](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/enable-dual-write) for Supply Chain Management apps.</span></span>
- <span data-ttu-id="9d871-157">[Dynamics 365 Guides](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup#step-2-create-a-common-data-service-environment-and-install-the-dynamics-365-guides-solution) version 400.0.1.48 eller senare</span><span class="sxs-lookup"><span data-stu-id="9d871-157">[Dynamics 365 Guides](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup#step-2-create-a-common-data-service-environment-and-install-the-dynamics-365-guides-solution) version 400.0.1.48 or later</span></span>

### <a name="turn-on-the-feature"></a><span data-ttu-id="9d871-158">Aktivera en funktion</span><span class="sxs-lookup"><span data-stu-id="9d871-158">Turn on the feature</span></span>

<span data-ttu-id="9d871-159">Om du vill göra funktionen tillgänglig i systemet måste du aktivera dess konfigurationsnycklar.</span><span class="sxs-lookup"><span data-stu-id="9d871-159">To make the feature available on your system, you must enable its configuration keys.</span></span> <span data-ttu-id="9d871-160">Du behöver bara göra detta en gång.</span><span class="sxs-lookup"><span data-stu-id="9d871-160">You only need to do this once.</span></span> <span data-ttu-id="9d871-161">För att göra detta måste en administratör göra följande:</span><span class="sxs-lookup"><span data-stu-id="9d871-161">To do this, an administrator must do the following:</span></span>

1. <span data-ttu-id="9d871-162">Sätt ditt system i underhållsläge enligt beskrivningen i [underhållsläge](../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md).</span><span class="sxs-lookup"><span data-stu-id="9d871-162">Place your system into maintenance mode as described in [Maintenance mode](../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md).</span></span>
1. <span data-ttu-id="9d871-163">Öppna **Systemadministration \> Inställningar \> Licenskonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="9d871-163">Go to **System administration \> Setup \> License configuration**.</span></span>
1. <span data-ttu-id="9d871-164">Expandera avsnittet **Mixad verklighet** och markera kryssrutan **Guide för mixad verklighet**.</span><span class="sxs-lookup"><span data-stu-id="9d871-164">Expand the **Mixed reality** section and then select the **Mixed reality guide** check box.</span></span>
1. <span data-ttu-id="9d871-165">Expandera avsnittet **Produktionshantering** och markera kryssrutan **Produktionsinstruktioner**.</span><span class="sxs-lookup"><span data-stu-id="9d871-165">Expand the **Production management** section and then select the **Production instructions** check box.</span></span>
1. <span data-ttu-id="9d871-166">Inaktivera underhållsläge enligt beskrivningen i [underhållsläge](../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md).</span><span class="sxs-lookup"><span data-stu-id="9d871-166">Turn off maintenance mode as described in [Maintenance mode](../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md).</span></span>
  
## <a name="configure-how-guides-appear-on-the-shop-floor"></a><span data-ttu-id="9d871-167">Konfigurera hur guider visas på verkstadsgolvet</span><span class="sxs-lookup"><span data-stu-id="9d871-167">Configure how Guides appear on the shop floor</span></span>

<span data-ttu-id="9d871-168">Om du vill konfigurera hur guider visas verkstadsgolvet går du till konfiguration **Mixad verklighet \> Dynamics 365 Guides \> Konfigurera integration av guider**.</span><span class="sxs-lookup"><span data-stu-id="9d871-168">To configure how Guides appear on the shop floor, go to **Mixed Reality \> Dynamics 365 Guides \> Configure Guides integration**.</span></span>

<span data-ttu-id="9d871-169">![Konfigurera integrering av guide för tillverkning](media/instruction-guides-configure-integration.png "Konfigurera integrering av guide för tillverkning")</span><span class="sxs-lookup"><span data-stu-id="9d871-169">![Configure Guide integration for manufacturing](media/instruction-guides-configure-integration.png "Configure Guide integration for manufacturing")</span></span>

<span data-ttu-id="9d871-170">Ange följande fält.</span><span class="sxs-lookup"><span data-stu-id="9d871-170">Set the following fields:</span></span>

- <span data-ttu-id="9d871-171">**Microsoft Dataverse URL** - Ange den URL till Microsoft Dataverse-miljön där du skapar Guides.</span><span class="sxs-lookup"><span data-stu-id="9d871-171">**Microsoft Dataverse URL** - Specify the URL for the Microsoft Dataverse environment where you create your Guides.</span></span> <span data-ttu-id="9d871-172">Formatet är "contoso.crm4.dynamics.com", där den första delen av webbadressen vanligtvis namnges efter din organisation (t.ex. "contoso."), den andra delen är specifik för din miljös dataområde (t.ex. "CRM4.") och den sista delen är domänen (t.ex. "dynamics.com").</span><span class="sxs-lookup"><span data-stu-id="9d871-172">The format is "contoso.crm4.dynamics.com", where the first part of the URL is typically named after your organization (such as "contoso."), the second part is specific to the data region of your environment (such as "crm4."), and the last part is the domain (such as "dynamics.com").</span></span> <span data-ttu-id="9d871-173">Ett sätt att hitta rätt URL är att gå till [home.dynamics.com](https://home.dynamics.com/) och sedan öppna appen Guides.</span><span class="sxs-lookup"><span data-stu-id="9d871-173">One way to find the right URL is to go to [home.dynamics.com](https://home.dynamics.com/) and then open your Guides app.</span></span> <span data-ttu-id="9d871-174">När Guides öppnas visas URL:en i adressfältet i webbläsaren (endast bas-URL:en, som bör likna föregående exempel).</span><span class="sxs-lookup"><span data-stu-id="9d871-174">When Guides opens, you will see the URL in the address bar of your browser (only take the base URL, which should resemble the previous example).</span></span> <span data-ttu-id="9d871-175">Det här värdet används för att skapa adresser för guider och de kommer att kodas till QR-koderna."</span><span class="sxs-lookup"><span data-stu-id="9d871-175">This value is used to compose addresses for your guides and will be encoded into the QR codes."</span></span>
- <span data-ttu-id="9d871-176">**Storlek på QR** - Ange storleken på den återgivna QR-koden.</span><span class="sxs-lookup"><span data-stu-id="9d871-176">**QR code size** - Set the size of the rendered QR code.</span></span> <span data-ttu-id="9d871-177">Vi rekommenderar att du väljer en storlek som kommer att fylla större delen av skärmen, men inte mer.</span><span class="sxs-lookup"><span data-stu-id="9d871-177">We recommend choosing a size that will fill most of your display screen, but not more.</span></span> <span data-ttu-id="9d871-178">Normalt *15* är ett bra värde.</span><span class="sxs-lookup"><span data-stu-id="9d871-178">Typically, *15* is a good value.</span></span>
- <span data-ttu-id="9d871-179">**Korrigeringsnivå för QR-kod** - Ange granularitet för QR-koden.</span><span class="sxs-lookup"><span data-stu-id="9d871-179">**QR code error correction level** - Set the granularity of the QR code.</span></span> <span data-ttu-id="9d871-180">Högre granularitet kan öka kodens tillförlitlighet, men **QR-kodens storlek** måste vara stor nog för att ge den detaljnivå som krävs för den valda korrigeringsnivån.</span><span class="sxs-lookup"><span data-stu-id="9d871-180">Higher granularity can help increase the code's reliability, but your **QR code size** must be large enough to support the level of detail required by your selected correction level.</span></span>

> [!TIP]
> - <span data-ttu-id="9d871-181">Värden för QR-koder som är för stora för din bildskärm tar lite längre tid att återge och sedan skalas de ned så att de passar din bildskärm.</span><span class="sxs-lookup"><span data-stu-id="9d871-181">QR codes sizes that are too large for your display will take a bit longer to render and then be scaled down to fit your display.</span></span> <span data-ttu-id="9d871-182">De ger ingen förmån.</span><span class="sxs-lookup"><span data-stu-id="9d871-182">These do not provide a benefit.</span></span>
> - <span data-ttu-id="9d871-183">De QR-kodstorlekar som är för små kan minska möjligheten HoloLens att läsa koden korrekt i vissa miljöer.</span><span class="sxs-lookup"><span data-stu-id="9d871-183">QR code sizes that are too small may decrease the ability of HoloLens to read the code properly in some environments.</span></span>
> - <span data-ttu-id="9d871-184">Vi rekommenderar att du testar inställningarna för varje enhet som ska visa QR-koder för HoloLens-användarna.</span><span class="sxs-lookup"><span data-stu-id="9d871-184">We recommend that you test the settings for each device that will display QR codes for HoloLens users.</span></span> <span data-ttu-id="9d871-185">Välj inställningar som ger tillräcklig läsbarhet i din arbetsmiljö.</span><span class="sxs-lookup"><span data-stu-id="9d871-185">Choose settings that provide sufficient readability in your shop floor environment.</span></span>  

## <a name="get-an-overview-of-all-guide-assignments"></a><span data-ttu-id="9d871-186">Få en översikt över alla tilldelningar i guidetilldelningar</span><span class="sxs-lookup"><span data-stu-id="9d871-186">Get an overview of all Guide assignments</span></span>

<span data-ttu-id="9d871-187">Använd sidan **Alla guider** för att visa en lista över alla tillgängliga guider i din organisation och alla tilldelningar till produktionsprocesserna och resurserna.</span><span class="sxs-lookup"><span data-stu-id="9d871-187">Use the **All Guides** page to see the list of all available Guides in your organization and all assignments to your production processes and resources.</span></span> <span data-ttu-id="9d871-188">Om du vill öppna den går du till **Mixad verklighet \> Guider \> Alla guider**.</span><span class="sxs-lookup"><span data-stu-id="9d871-188">To open it, go to **Mixed reality \> Guides \> All Guides**.</span></span> <span data-ttu-id="9d871-189">Listan högst upp visar alla tillgängliga guider och du kan använda fältet här för att filtrera listan.</span><span class="sxs-lookup"><span data-stu-id="9d871-189">The list at the top shows all the available Guides and you can use the field here to filter the list.</span></span> <span data-ttu-id="9d871-190">Listan längst ned visar alla guider tilldelningar och innehåller ett verktygsfält för hantering av dem.</span><span class="sxs-lookup"><span data-stu-id="9d871-190">The list at the bottom shows all Guide assignments and provides a toolbar for managing them.</span></span>

<span data-ttu-id="9d871-191">![Hantera guider](media/instruction-guides-allguides.png "Hantera guider")</span><span class="sxs-lookup"><span data-stu-id="9d871-191">![Manage Guides](media/instruction-guides-allguides.png "Manage Guides")</span></span>

<span data-ttu-id="9d871-192">I följande avsnitt beskrivs de typer av objekt som du kan tilldela guider till.</span><span class="sxs-lookup"><span data-stu-id="9d871-192">The following sections describe the types of objects that you can assign Guides to.</span></span> <span data-ttu-id="9d871-193">Varje tilldelad guide innehåller instruktioner som automatiskt kopplas till respektive produktionsjobb och blir tillgängliga i verktygsgolvet.</span><span class="sxs-lookup"><span data-stu-id="9d871-193">Each assigned guide provides instructions that are automatically attached to the respective production jobs and will be available on the shop floor.</span></span>

## <a name="associate-a-guide-to-a-resource"></a><a name="resources"></a><span data-ttu-id="9d871-194">Associera en guider till en resurs</span><span class="sxs-lookup"><span data-stu-id="9d871-194">Associate a Guide to a resource</span></span>

<span data-ttu-id="9d871-195">Lägg till en guide till en [resurs](operations-resources.md) för att erbjuda guiden i samband med relevanta produktionsjobb.</span><span class="sxs-lookup"><span data-stu-id="9d871-195">Add a Guide to a [resource](operations-resources.md) to offer the Guide in the context of relevant production jobs.</span></span>

### <a name="typical-scenario-using-resources"></a><span data-ttu-id="9d871-196">Vanligt scenario med resurser</span><span class="sxs-lookup"><span data-stu-id="9d871-196">Typical scenario using resources</span></span>

<span data-ttu-id="9d871-197">Du kan till exempel lägga till en guide med generella maskin säkerhets- eller hanteringsinstruktioner på en resurs av typen maskin.</span><span class="sxs-lookup"><span data-stu-id="9d871-197">For example, you could attach a Guide with general machine security or handling instructions to a resource of type machine.</span></span> <span data-ttu-id="9d871-198">Sedan kommer guiden att vara tillgänglig på alla jobb som utförs på datorn.</span><span class="sxs-lookup"><span data-stu-id="9d871-198">Then, the Guide will be available on every job that is performed on the machine.</span></span>

### <a name="add-a-guide-to-a-resource"></a><span data-ttu-id="9d871-199">Lägg till en guider till en resurs</span><span class="sxs-lookup"><span data-stu-id="9d871-199">Add a Guide to a resource</span></span>

<span data-ttu-id="9d871-200">Lägg till en guider till en resurs:</span><span class="sxs-lookup"><span data-stu-id="9d871-200">To add a Guide to a resource:</span></span>

1. <span data-ttu-id="9d871-201">Gå till **Produktionsstyrning \> Inställningar \> Resurser \> Resurser**.</span><span class="sxs-lookup"><span data-stu-id="9d871-201">Go to **Production control \> Setup \> Resources \> Resources**.</span></span>
1. <span data-ttu-id="9d871-202">Välj den resurs som du vill tilldela en guide till i listrutan.</span><span class="sxs-lookup"><span data-stu-id="9d871-202">From the list pane, select the resource you want to assign a Guide to.</span></span>
1. <span data-ttu-id="9d871-203">Expandera snabbfliken **Associerade guider**.</span><span class="sxs-lookup"><span data-stu-id="9d871-203">Expand the **Associated Guides** FastTab.</span></span>
1. <span data-ttu-id="9d871-204">Välj **Lägg till** från verktygsfältet **Associerade guider**.</span><span class="sxs-lookup"><span data-stu-id="9d871-204">Select **Add** from the **Associated Guides** toolbar.</span></span> <span data-ttu-id="9d871-205">En ny rad läggs till i rutnätet.</span><span class="sxs-lookup"><span data-stu-id="9d871-205">A new line is added to the grid.</span></span>
1. <span data-ttu-id="9d871-206">För den nya raden använder du listrutan i kolumnen **namn** för att välja den guider du vill tilldela.</span><span class="sxs-lookup"><span data-stu-id="9d871-206">For the new line, use the drop-down list in the **Name** column to choose the Guide you want to assign.</span></span> <span data-ttu-id="9d871-207">Om du har ett stort antal guider kan du filtrera listan för att hitta den som du söker efter.</span><span class="sxs-lookup"><span data-stu-id="9d871-207">If you have a large number of Guides, then you can filter the list to find the one you are looking for.</span></span>
    <span data-ttu-id="9d871-208">![Hantera guider](media/instruction-guides-allguides.png "Hantera guider")</span><span class="sxs-lookup"><span data-stu-id="9d871-208">![Manage Guides](media/instruction-guides-allguides.png "Manage Guides")</span></span>

## <a name="associate-a-guide-to-a-resource-group"></a><a name="resource-groups"></a><span data-ttu-id="9d871-209">Associera en guider till en resursgrupp</span><span class="sxs-lookup"><span data-stu-id="9d871-209">Associate a Guide to a resource group</span></span>

<span data-ttu-id="9d871-210">Du kan lägga till en guide i [resursgrupper](tasks/define-discrete-manufacturing-resource-group.md) om du använder dem för att hantera grupper av maskiner, produktionsrader eller arbetsceller.</span><span class="sxs-lookup"><span data-stu-id="9d871-210">You can add a guide to [resource groups](tasks/define-discrete-manufacturing-resource-group.md) if you use them to manage groups of machines, production lines, or work cells.</span></span>

### <a name="typical-scenarios-using-resource-groups"></a><span data-ttu-id="9d871-211">Vanligt scenario med resursgrupper</span><span class="sxs-lookup"><span data-stu-id="9d871-211">Typical scenarios using resource groups</span></span>

<span data-ttu-id="9d871-212">**Exempel 1:** du har definierat en resursgrupp för flera maskiner av samma modell.</span><span class="sxs-lookup"><span data-stu-id="9d871-212">**Example 1:** You have defined a resource group for several machines of the same model.</span></span> <span data-ttu-id="9d871-213">I stället för att tilldela relevant guide för hanteringsinstruktioner för maskinmodellen till varje relevant resurs, kan du i stället tilldela guiden till den resursgrupp som återspeglar den maskinmodellen.</span><span class="sxs-lookup"><span data-stu-id="9d871-213">Instead of assigning the relevant handling instruction guide for the machine model to every relevant resource, you could instead assign the Guide to the resource group that reflects that machine model.</span></span>

<span data-ttu-id="9d871-214">**Exempel 2:** du har definierat en resursgrupp för en arbetsgrupp som innehåller olika maskiner och du har en guide som innehåller allmänna instruktioner för hur du ska underhålla arbetsgruppen.</span><span class="sxs-lookup"><span data-stu-id="9d871-214">**Example 2:** You have defined a resource group for a work cell that contains different machines and you have a Guide that provides general instructions for how to maintain the work cell.</span></span> <span data-ttu-id="9d871-215">Guiden gäller alla produktionsaktiviteter i den här arbetsgruppen.</span><span class="sxs-lookup"><span data-stu-id="9d871-215">The Guide applies to any production activity in this work cell.</span></span>

### <a name="add-a-guide-to-a-resource-group"></a><span data-ttu-id="9d871-216">Lägg till en guide till en resursgrupp</span><span class="sxs-lookup"><span data-stu-id="9d871-216">Add a Guide to a resource group</span></span>

<span data-ttu-id="9d871-217">För att lägga till en guide till en resursgrupp:</span><span class="sxs-lookup"><span data-stu-id="9d871-217">To add a Guide to a resource group:</span></span>

1. <span data-ttu-id="9d871-218">Gå till **Produktionsstyrning \> Inställningar \> Resurser \> Resursgrupper**.</span><span class="sxs-lookup"><span data-stu-id="9d871-218">Go to **Production control \> Setup \> Resources \> Resource groups**.</span></span>
1. <span data-ttu-id="9d871-219">Välj den resursgrupp som du vill tilldela en guide till i listrutan.</span><span class="sxs-lookup"><span data-stu-id="9d871-219">From the list pane, select the resource group you want to assign a Guide to.</span></span>
1. <span data-ttu-id="9d871-220">Expandera snabbfliken **Associerade guider**.</span><span class="sxs-lookup"><span data-stu-id="9d871-220">Expand the **Associated Guides** FastTab.</span></span>
1. <span data-ttu-id="9d871-221">Välj **Lägg till** från verktygsfältet **Associerade guider**.</span><span class="sxs-lookup"><span data-stu-id="9d871-221">Select **Add** from the **Associated Guides** toolbar.</span></span> <span data-ttu-id="9d871-222">En ny rad läggs till i rutnätet.</span><span class="sxs-lookup"><span data-stu-id="9d871-222">A new line is added to the grid.</span></span>
1. <span data-ttu-id="9d871-223">För den nya raden använder du listrutan i kolumnen **namn** för att välja den guider du vill tilldela.</span><span class="sxs-lookup"><span data-stu-id="9d871-223">For the new line, use the drop-down list in the **Name** column to choose the Guide you want to assign.</span></span> <span data-ttu-id="9d871-224">Om du har ett stort antal guider kan du filtrera listan för att hitta den som du söker efter.</span><span class="sxs-lookup"><span data-stu-id="9d871-224">If you have a large number of Guides, then you can filter the list to find the one you are looking for.</span></span>
    <span data-ttu-id="9d871-225">![Lägg till en guide till en resursgrupp](media/instruction-guides-resourcegroup.png "Lägg till en guide till en resursgrupp")</span><span class="sxs-lookup"><span data-stu-id="9d871-225">![Adding a Guide to a resource group](media/instruction-guides-resourcegroup.png "Adding a Guide to a resource group")</span></span>

## <a name="associate-a-guide-to-a-released-product"></a><a name="released-products"></a><span data-ttu-id="9d871-226">Associera en guide till en frisläppt produkt</span><span class="sxs-lookup"><span data-stu-id="9d871-226">Associate a Guide to a released product</span></span>

<span data-ttu-id="9d871-227">Du kan lägga till en guide för alla [frisläppta produkter](../pim/tasks/create-released-product-single-company.md).</span><span class="sxs-lookup"><span data-stu-id="9d871-227">You can add a guide to any [released product](../pim/tasks/create-released-product-single-company.md).</span></span>

### <a name="typical-scenario-using-released-products"></a><span data-ttu-id="9d871-228">Vanligt scenario när frisläppta produkter används</span><span class="sxs-lookup"><span data-stu-id="9d871-228">Typical scenario using released products</span></span>

<span data-ttu-id="9d871-229">Med hjälp av guider på produktnivå kan hjälpa verkstadsarbetarna med instruktioner som rör drift eller hantering av en specifik frisläppt produkt eller artikel.</span><span class="sxs-lookup"><span data-stu-id="9d871-229">Product-level Guides help shop floor workers with instructions relevant to operating or handling a specific released product or item.</span></span>

### <a name="add-a-guide-to-a-released-product"></a><span data-ttu-id="9d871-230">Lägg till en guide till en frisläppt produkt</span><span class="sxs-lookup"><span data-stu-id="9d871-230">Add a Guide to a released product</span></span>

<span data-ttu-id="9d871-231">Lägg till en guide till en frisläppt produkt:</span><span class="sxs-lookup"><span data-stu-id="9d871-231">To add a Guide to a released product:</span></span>

1. <span data-ttu-id="9d871-232">Gå till **Produktionsinformationshantering \> Produkter \> Frisläppta produkter**.</span><span class="sxs-lookup"><span data-stu-id="9d871-232">Go to **Production information management \> Products \> Released products**.</span></span>
1. <span data-ttu-id="9d871-233">Öppna den produkt som du vill tilldela en guide till.</span><span class="sxs-lookup"><span data-stu-id="9d871-233">Open the product you want to assign a Guide to.</span></span>
1. <span data-ttu-id="9d871-234">I åtgärdsfönstret, öppna fliken **Tekniker** och från gruppen **Vy** välj **Associerade guider**.</span><span class="sxs-lookup"><span data-stu-id="9d871-234">On the Action Pane, open the **Engineer** tab and from the **View** group, select **Associated Guides**.</span></span>
1. <span data-ttu-id="9d871-235">Sidan **Associerade guider** öppnas för den valda produkten.</span><span class="sxs-lookup"><span data-stu-id="9d871-235">The **Associated Guides** page opens for your selected product.</span></span>
1. <span data-ttu-id="9d871-236">Välj **Lägg till** i åtgärdsfönstret för att lägga till en ny rad i rutnätet.</span><span class="sxs-lookup"><span data-stu-id="9d871-236">Select **Add** on the Action Pane to add a new line to the grid.</span></span> 
1. <span data-ttu-id="9d871-237">För den nya raden använder du listrutan i kolumnen **namn** för att välja den guider du vill tilldela.</span><span class="sxs-lookup"><span data-stu-id="9d871-237">For the new line, use the drop-down list in the **Name** column to choose the Guide you want to assign.</span></span>
    <span data-ttu-id="9d871-238">![Lägg till en guide till en frisläppt produkt](media/instruction-guides-ReleasedProduct-AddGuides.png "Lägg till en guide till en frisläppt produkt")</span><span class="sxs-lookup"><span data-stu-id="9d871-238">![Adding a Guide to a released product](media/instruction-guides-ReleasedProduct-AddGuides.png "Adding a Guide to a released product")</span></span>

## <a name="associate-a-guide-to-a-formula"></a><a name="formulas"></a><span data-ttu-id="9d871-239">Associera en guide till en formel</span><span class="sxs-lookup"><span data-stu-id="9d871-239">Associate a Guide to a formula</span></span>

<span data-ttu-id="9d871-240">Du kan lägga till en guide för alla [formel](bill-of-material-bom.md#formulas-co-products-and-by-products).</span><span class="sxs-lookup"><span data-stu-id="9d871-240">You can add a guide to any [formula](bill-of-material-bom.md#formulas-co-products-and-by-products).</span></span>

### <a name="typical-scenario-using-formulas"></a><span data-ttu-id="9d871-241">Vanligt scenario med formler</span><span class="sxs-lookup"><span data-stu-id="9d871-241">Typical scenario using formulas</span></span>
  
<span data-ttu-id="9d871-242">På formelnivå finns guider som ger verkstadsarbetare guidade hanteringsinstruktioner i samband med en formel eller ett recept.</span><span class="sxs-lookup"><span data-stu-id="9d871-242">Formula-level Guides provide shop floor workers with guided handling instructions in the context of a formula or recipe.</span></span> <span data-ttu-id="9d871-243">Guider kan också tilldelas till en version av en formel.</span><span class="sxs-lookup"><span data-stu-id="9d871-243">Guides can also be assigned to versions of a formula.</span></span>

> [!NOTE]
> <span data-ttu-id="9d871-244">Du kan tilldela vägledningar som är relevanta för produktionsprocesser baserade på en formel till ett flöde, flödesversion eller flödesoperationsrelationer.</span><span class="sxs-lookup"><span data-stu-id="9d871-244">You can assign guidance relevant for production processes based on a formula to a route, route version, or route operation relations.</span></span>  

> <span data-ttu-id="9d871-245">Guider kan för närvarande inte kopplas till enskilda formelrader.</span><span class="sxs-lookup"><span data-stu-id="9d871-245">Guides can't currently be attached to individual formula lines.</span></span>

### <a name="add-a-guide-to-a-formula"></a><span data-ttu-id="9d871-246">Lägg till en guide till en formel</span><span class="sxs-lookup"><span data-stu-id="9d871-246">Add a Guide to a formula</span></span>

<span data-ttu-id="9d871-247">Lägg till en guide till en formel:</span><span class="sxs-lookup"><span data-stu-id="9d871-247">To add a Guide to a formula:</span></span>

1. <span data-ttu-id="9d871-248">Gå till **Produktinformationshantering \> Strukturlistor och formler \> Formler**.</span><span class="sxs-lookup"><span data-stu-id="9d871-248">Go to **Production information management \> Bills of materials and formulas \> Formulas**.</span></span>
1. <span data-ttu-id="9d871-249">Öppna den formel som du vill tilldela en guide till.</span><span class="sxs-lookup"><span data-stu-id="9d871-249">Open the formula you want to assign a Guide to.</span></span>
1. <span data-ttu-id="9d871-250">Öppna fliken **Rubrik** ovanför den övre snabbfliken.</span><span class="sxs-lookup"><span data-stu-id="9d871-250">Open the **Header** tab above the top FastTab.</span></span>
1. <span data-ttu-id="9d871-251">Expandera snabbfliken **Associerade guider**.</span><span class="sxs-lookup"><span data-stu-id="9d871-251">Expand the **Associated Guides** FastTab.</span></span>
1. <span data-ttu-id="9d871-252">Välj **Lägg till** från verktygsfältet **Associerade guider**.</span><span class="sxs-lookup"><span data-stu-id="9d871-252">Select **Add** from the **Associated Guides** toolbar.</span></span> <span data-ttu-id="9d871-253">En ny rad läggs till i rutnätet.</span><span class="sxs-lookup"><span data-stu-id="9d871-253">A new line is added to the grid.</span></span>
1. <span data-ttu-id="9d871-254">För den nya raden använder du listrutan i kolumnen **namn** för att välja den guider du vill tilldela.</span><span class="sxs-lookup"><span data-stu-id="9d871-254">For the new line, use the drop-down list in the **Name** column to choose the Guide you want to assign.</span></span>
    <span data-ttu-id="9d871-255">![Lägg till en guide till en formel](media/instruction-guides-Formula.png "Lägg till en guide till en formel")</span><span class="sxs-lookup"><span data-stu-id="9d871-255">![Adding a Guide to a formula](media/instruction-guides-Formula.png "Adding a Guide to a formula")</span></span>

## <a name="associate-a-guide-to-a-formula-version"></a><a name="formula-versions"></a><span data-ttu-id="9d871-256">Associera en guide till en formelversion</span><span class="sxs-lookup"><span data-stu-id="9d871-256">Associate a Guide to a formula version</span></span>

<span data-ttu-id="9d871-257">Du kan lägga till en guide för alla [formelversion](bill-of-material-bom.md#bom-and-formula-versions).</span><span class="sxs-lookup"><span data-stu-id="9d871-257">You can add a guide to any [formula version](bill-of-material-bom.md#bom-and-formula-versions).</span></span>

### <a name="typical-scenario-using-formula-versions"></a><span data-ttu-id="9d871-258">Vanligt scenario med formelversioner</span><span class="sxs-lookup"><span data-stu-id="9d871-258">Typical scenario using formula versions</span></span>

<span data-ttu-id="9d871-259">Guider som är kopplade till en enskild version av en formel ger arbetstagare instruktioner som går igenom produktionen av formelreceptet.</span><span class="sxs-lookup"><span data-stu-id="9d871-259">Guides attached to an individual version of a formula provide shop floor workers with instructions that walk through the production of that version of the formula recipe.</span></span>

> [!TIP]
> <span data-ttu-id="9d871-260">Du kan tilldela vägledningar som är relevanta för produktionsprocesser baserade på en formelversion till ett flöde, flödesversion eller flödesoperationsrelationer.</span><span class="sxs-lookup"><span data-stu-id="9d871-260">You can assign guidance relevant for production processes based on this formula version to a route, route version, or route operation relations.</span></span>  

> [!NOTE]
> <span data-ttu-id="9d871-261">Guider kan för närvarande inte kopplas till enskilda formelrader.</span><span class="sxs-lookup"><span data-stu-id="9d871-261">Guides can't currently be attached to individual formula lines.</span></span>

### <a name="add-a-guide-to-a-formula-version"></a><span data-ttu-id="9d871-262">Lägg till en guide till en formelversion</span><span class="sxs-lookup"><span data-stu-id="9d871-262">Add a Guide to a formula version</span></span>

<span data-ttu-id="9d871-263">Lägg till en guide till en formelversion:</span><span class="sxs-lookup"><span data-stu-id="9d871-263">To add a Guide to a formula version:</span></span>

1. <span data-ttu-id="9d871-264">Gå till **Produktinformationshantering \> Strukturlistor och formler \> Formler**.</span><span class="sxs-lookup"><span data-stu-id="9d871-264">Go to **Production information management \> Bills of materials and formulas \> Formulas**.</span></span>
1. <span data-ttu-id="9d871-265">Öppna formeln som innehåller en version som du vill tilldela en guide till.</span><span class="sxs-lookup"><span data-stu-id="9d871-265">Open the formula that includes a version that you want to assign a Guide to.</span></span>
1. <span data-ttu-id="9d871-266">Öppna fliken **Rubrik** ovanför den övre snabbfliken.</span><span class="sxs-lookup"><span data-stu-id="9d871-266">Open the **Header** tab above the top FastTab.</span></span>
1. <span data-ttu-id="9d871-267">På snabbfliken **Formelversioner** välj den version som du vill tilldela en guide till.</span><span class="sxs-lookup"><span data-stu-id="9d871-267">On the **Formula versions** FastTab, select the version you want to assign a Guide to.</span></span>
1. <span data-ttu-id="9d871-268">I verktygsfältet **Formelversioner** väljer du **Koppla guider**.</span><span class="sxs-lookup"><span data-stu-id="9d871-268">On the **Formula versions** toolbar, select **Associated Guides**.</span></span>
    <span data-ttu-id="9d871-269">![Öppna de guider som associeras med en vald formelversion](media/instruction-guides-FormulaVersion.png "Öppna de guider som associeras med en vald formelversion")</span><span class="sxs-lookup"><span data-stu-id="9d871-269">![Open the Guides associated with a selected formula version](media/instruction-guides-FormulaVersion.png "Open the Guides associated with a selected formula version")</span></span>
1. <span data-ttu-id="9d871-270">Sidan **Associerade guider** öppnas för den valda formelversionen.</span><span class="sxs-lookup"><span data-stu-id="9d871-270">The **Associated Guides** page opens for your formula version.</span></span>
1. <span data-ttu-id="9d871-271">Välj **Lägg till** i åtgärdsfönstret för att lägga till en ny rad i rutnätet.</span><span class="sxs-lookup"><span data-stu-id="9d871-271">Select **Add** on the Action Pane to add a new line to the grid.</span></span> 
1. <span data-ttu-id="9d871-272">För den nya raden använder du listrutan i kolumnen **namn** för att välja den guider du vill tilldela.</span><span class="sxs-lookup"><span data-stu-id="9d871-272">For the new line, use the drop-down list in the **Name** column to choose the Guide you want to assign.</span></span>
    <span data-ttu-id="9d871-273">![Lägg till en guide till en formelversion](media/instruction-guides-FormulaVersionAddGuide.png "Lägg till en guide till en formelversion")</span><span class="sxs-lookup"><span data-stu-id="9d871-273">![Adding a Guide to a formula version](media/instruction-guides-FormulaVersionAddGuide.png "Adding a Guide to a formula version")</span></span>

## <a name="associate-a-guide-to-a-bill-of-materials"></a><a name="bom"></a><span data-ttu-id="9d871-274">Associera en guide till en strukturlista</span><span class="sxs-lookup"><span data-stu-id="9d871-274">Associate a Guide to a bill of materials</span></span>

<span data-ttu-id="9d871-275">Du kan lägga till en guide för en valfri [strukturlista](bill-of-material-bom.md).</span><span class="sxs-lookup"><span data-stu-id="9d871-275">You can add a guide to any [bill of materials](bill-of-material-bom.md) (BOM).</span></span>

### <a name="typical-scenario-using-bills-of-materials"></a><span data-ttu-id="9d871-276">Vanligt scenario vid användning av strukturlistor</span><span class="sxs-lookup"><span data-stu-id="9d871-276">Typical scenario using bills of materials</span></span>

<span data-ttu-id="9d871-277">Guider som är kopplade till en strukturlista ger arbetstagare instruktioner som förklarar hur material förbereds och hanteras från en strukturlista.</span><span class="sxs-lookup"><span data-stu-id="9d871-277">Guides attached to a BOM provide shop floor workers with instructions that explain how to prepare and handle material from a BOM.</span></span> <span data-ttu-id="9d871-278">Guider kan också tilldelas till en version av en strukturlista.</span><span class="sxs-lookup"><span data-stu-id="9d871-278">Guides can also be assigned to versions of a BOM.</span></span>

> [!NOTE]
> <span data-ttu-id="9d871-279">Guider kan för närvarande inte kopplas till enskilda strukturlisterader.</span><span class="sxs-lookup"><span data-stu-id="9d871-279">Guides can't currently be attached to individual BOM lines.</span></span>

### <a name="add-a-guide-to-a-bill-of-materials"></a><span data-ttu-id="9d871-280">Lägg till en guide till en strukturlista</span><span class="sxs-lookup"><span data-stu-id="9d871-280">Add a Guide to a bill of materials</span></span>

<span data-ttu-id="9d871-281">Lägg till en guide till en strukturlista:</span><span class="sxs-lookup"><span data-stu-id="9d871-281">To add a Guide to a bill of material:</span></span>

1. <span data-ttu-id="9d871-282">Gå till **Produktinformationshantering \> Strukturlistor och formler \> Strukturlistor**.</span><span class="sxs-lookup"><span data-stu-id="9d871-282">Go to **Production information management \> Bills of materials and formulas \> Bills of materials**.</span></span>
1. <span data-ttu-id="9d871-283">Öppna den strukturlista som du vill tilldela en guide till.</span><span class="sxs-lookup"><span data-stu-id="9d871-283">Open the bill of materials that you want to assign a Guide to.</span></span>
1. <span data-ttu-id="9d871-284">Öppna fliken **Rubrik** ovanför den övre snabbfliken.</span><span class="sxs-lookup"><span data-stu-id="9d871-284">Open the **Header** tab above the top FastTab.</span></span>
1. <span data-ttu-id="9d871-285">Expandera snabbfliken **Associerade guider**.</span><span class="sxs-lookup"><span data-stu-id="9d871-285">Expand the **Associated Guides** FastTab.</span></span>
1. <span data-ttu-id="9d871-286">Välj **Lägg till** från verktygsfältet **Associerade guider**.</span><span class="sxs-lookup"><span data-stu-id="9d871-286">Select **Add** from the **Associated Guides** toolbar.</span></span> <span data-ttu-id="9d871-287">En ny rad läggs till i rutnätet.</span><span class="sxs-lookup"><span data-stu-id="9d871-287">A new line is added to the grid.</span></span>
1. <span data-ttu-id="9d871-288">För den nya raden använder du listrutan i kolumnen **namn** för att välja den guider du vill tilldela.</span><span class="sxs-lookup"><span data-stu-id="9d871-288">For the new line, use the drop-down list in the **Name** column to choose the Guide you want to assign.</span></span>
    <span data-ttu-id="9d871-289">![Lägg till en guide till en strukturlista](media/instruction-guides-BOM.png "Lägg till en guide till en strukturlista")</span><span class="sxs-lookup"><span data-stu-id="9d871-289">![Adding a Guide to a BOM](media/instruction-guides-BOM.png "Adding a Guide to a BOM")</span></span>

## <a name="associate-a-guide-to-a-bill-of-materials-version"></a><a name="bom-versions"></a><span data-ttu-id="9d871-290">Associera en guide till en strukturlisteversion</span><span class="sxs-lookup"><span data-stu-id="9d871-290">Associate a Guide to a bill of materials version</span></span>

<span data-ttu-id="9d871-291">Du kan lägga till en guide för en valfri [strukturlisteversion](bill-of-material-bom.md#bom-and-formula-versions).</span><span class="sxs-lookup"><span data-stu-id="9d871-291">You can add a guide to any [bill of materials version](bill-of-material-bom.md#bom-and-formula-versions).</span></span>

### <a name="typical-scenario-using-bill-of-materials-versions"></a><span data-ttu-id="9d871-292">Vanligt scenario vid användning av strukturlisteversioner</span><span class="sxs-lookup"><span data-stu-id="9d871-292">Typical scenario using bill of materials versions</span></span>

<span data-ttu-id="9d871-293">Guider som är kopplade till en enskild strukturlisteversion ger arbetstagare instruktioner som förklarar hur material förbereds och hanteras för en version av en strukturlista som skiljer sig från den allmänna strukturlistan eller andra versioner av den.</span><span class="sxs-lookup"><span data-stu-id="9d871-293">Guides attached to an individual BOM version provide shop floor workers with instructions that explain how to prepare and handle material for a version of a BOM that is different from the generic BOM or other versions of it.</span></span>

> [!NOTE]
> <span data-ttu-id="9d871-294">Guider kan för närvarande inte kopplas till enskilda strukturlisterader.</span><span class="sxs-lookup"><span data-stu-id="9d871-294">Guides can't currently be attached to individual BOM lines.</span></span>

### <a name="add-a-guide-to-a-bill-of-materials-version"></a><span data-ttu-id="9d871-295">Lägg till en guide till en strukturlisteversion</span><span class="sxs-lookup"><span data-stu-id="9d871-295">Add a Guide to a bill of materials version</span></span>

<span data-ttu-id="9d871-296">Lägg till en guide till en strukturlisteversion:</span><span class="sxs-lookup"><span data-stu-id="9d871-296">To add a Guide to a bill of materials version:</span></span>

1. <span data-ttu-id="9d871-297">Gå till **Produktinformationshantering \> Strukturlistor och formler \> Strukturlistor**.</span><span class="sxs-lookup"><span data-stu-id="9d871-297">Go to **Production information management \> Bills of materials and formulas \> Bills of materials**.</span></span>
1. <span data-ttu-id="9d871-298">Öppna strukturlistan som innehåller en version som du vill tilldela en guide till.</span><span class="sxs-lookup"><span data-stu-id="9d871-298">Open the BOM that includes a version that you want to assign a Guide to.</span></span>
1. <span data-ttu-id="9d871-299">Öppna fliken **Rubrik** ovanför den övre snabbfliken.</span><span class="sxs-lookup"><span data-stu-id="9d871-299">Open the **Header** tab above the top FastTab.</span></span>
1. <span data-ttu-id="9d871-300">På snabbfliken **Strukturlisteversioner** välj den version som du vill tilldela en guide till.</span><span class="sxs-lookup"><span data-stu-id="9d871-300">On the **BOM versions** FastTab, select the version you want to assign a Guide to.</span></span>
1. <span data-ttu-id="9d871-301">I verktygsfältet **Strukturlisteversioner** väljer du **Koppla guider**.</span><span class="sxs-lookup"><span data-stu-id="9d871-301">On the **BOM versions** toolbar, select **Associated Guides**.</span></span>
    <span data-ttu-id="9d871-302">![Öppna de guider som associeras med en vald strukturlisteversion](media/instruction-guides-BOMVersion.png "Öppna de guider som associeras med en vald strukturlisteversion")</span><span class="sxs-lookup"><span data-stu-id="9d871-302">![Open the Guides associated with a selected BOM version](media/instruction-guides-BOMVersion.png "Open the Guides associated with a selected BOM version")</span></span>
1. <span data-ttu-id="9d871-303">Sidan **Associerade guider** öppnas för den valda strukturlisteversionen.</span><span class="sxs-lookup"><span data-stu-id="9d871-303">The **Associated Guides** page opens for your BOM version.</span></span>
1. <span data-ttu-id="9d871-304">Välj **Lägg till** i åtgärdsfönstret för att lägga till en ny rad i rutnätet.</span><span class="sxs-lookup"><span data-stu-id="9d871-304">Select **Add** on the Action Pane to add a new line to the grid.</span></span>
1. <span data-ttu-id="9d871-305">För den nya raden använder du listrutan i kolumnen **namn** för att välja den guider du vill tilldela.</span><span class="sxs-lookup"><span data-stu-id="9d871-305">For the new line, use the drop-down list in the **Name** column to choose the Guide you want to assign.</span></span>
    <span data-ttu-id="9d871-306">![Lägg till en guide till en strukturlisteversion](media/instruction-guides-BOMVersionAddGuide.png "Lägg till en guide till en strukturlisteversion")</span><span class="sxs-lookup"><span data-stu-id="9d871-306">![Adding a Guide to a BOM version](media/instruction-guides-BOMVersionAddGuide.png "Adding a Guide to a BOM version")</span></span>

## <a name="associate-a-guide-to-a-route"></a><a name="routes"></a><span data-ttu-id="9d871-307">Associera en guide till ett flöde</span><span class="sxs-lookup"><span data-stu-id="9d871-307">Associate a Guide to a route</span></span>

<span data-ttu-id="9d871-308">Du kan lägga till en guide för alla [flöden](routes-operations.md).</span><span class="sxs-lookup"><span data-stu-id="9d871-308">You can add a guide to any [route](routes-operations.md).</span></span>

### <a name="typical-scenario-using-routes"></a><span data-ttu-id="9d871-309">Vanligt scenario med flöden</span><span class="sxs-lookup"><span data-stu-id="9d871-309">Typical scenario using routes</span></span>

<span data-ttu-id="9d871-310">Flöden används vanligtvis för att ange hur en viss frisläppt produkt ska skapas på grundval av en strukturlista eller strukturlisteversion och med en uppsättning resurser eller resursgrupper.</span><span class="sxs-lookup"><span data-stu-id="9d871-310">Routes are typically used to specify how a certain released product shall be produced based on a BOM or BOM version and with a set of resources or resource groups.</span></span>

<span data-ttu-id="9d871-311">Tilldela en guide till ett flöde om du vill skapa steg för steg-instruktioner för respektive produktionsprocess.</span><span class="sxs-lookup"><span data-stu-id="9d871-311">Assign a Guide to a route to provide step-by-step instructions for the respective production process.</span></span>

### <a name="add-a-guide-to-a-route"></a><span data-ttu-id="9d871-312">Lägg till en guide till ett flöde</span><span class="sxs-lookup"><span data-stu-id="9d871-312">Add a Guide to a route</span></span>

<span data-ttu-id="9d871-313">Lägg till en guide till ett flöde:</span><span class="sxs-lookup"><span data-stu-id="9d871-313">To add a Guide to a route:</span></span>

1. <span data-ttu-id="9d871-314">Gå till **produktionskontroll \> alla flöden**.</span><span class="sxs-lookup"><span data-stu-id="9d871-314">Go to **Production control \> All routes**.</span></span>
1. <span data-ttu-id="9d871-315">Öppna det flöde som du vill tilldela en guide till.</span><span class="sxs-lookup"><span data-stu-id="9d871-315">Open the route that you want to assign a Guide to.</span></span>
1. <span data-ttu-id="9d871-316">Expandera snabbfliken **Associerade guider**.</span><span class="sxs-lookup"><span data-stu-id="9d871-316">Expand the **Associated Guides** FastTab.</span></span>
1. <span data-ttu-id="9d871-317">Välj **Lägg till** från verktygsfältet **Associerade guider**.</span><span class="sxs-lookup"><span data-stu-id="9d871-317">Select **Add** from the **Associated Guides** toolbar.</span></span> <span data-ttu-id="9d871-318">En ny rad läggs till i rutnätet.</span><span class="sxs-lookup"><span data-stu-id="9d871-318">A new line is added to the grid.</span></span>
1. <span data-ttu-id="9d871-319">För den nya raden använder du listrutan i kolumnen **namn** för att välja den guider du vill tilldela.</span><span class="sxs-lookup"><span data-stu-id="9d871-319">For the new line, use the drop-down list in the **Name** column to choose the Guide you want to assign.</span></span>
    <span data-ttu-id="9d871-320">![Lägg till en guide till ett flöde](media/instruction-guides-Route.png "Lägg till en guide till ett flöde")</span><span class="sxs-lookup"><span data-stu-id="9d871-320">![Adding a Guide to a route](media/instruction-guides-Route.png "Adding a Guide to a route")</span></span>

## <a name="associate-a-guide-to-a-route-version"></a><a name="route-versions"></a><span data-ttu-id="9d871-321">Associera en guide till en flödesversion</span><span class="sxs-lookup"><span data-stu-id="9d871-321">Associate a Guide to a route version</span></span>

<span data-ttu-id="9d871-322">Du kan lägga till en guide för alla [flödesversion](routes-operations.md#route-versions).</span><span class="sxs-lookup"><span data-stu-id="9d871-322">You can add a guide to any [route version](routes-operations.md#route-versions).</span></span>

### <a name="typical-scenario-using-route-versions"></a><span data-ttu-id="9d871-323">Vanligt scenario med flödesversioner</span><span class="sxs-lookup"><span data-stu-id="9d871-323">Typical scenario using route versions</span></span>

<span data-ttu-id="9d871-324">Flödesversioner används vanligtvis för att ange varianter av produktionsprocesser baserade på ett befintligt flöde.</span><span class="sxs-lookup"><span data-stu-id="9d871-324">Routes versions are typically used to specify variants of production processes based on an existing route.</span></span> <span data-ttu-id="9d871-325">Du kan tilldela olika guider till varje flödesversion.</span><span class="sxs-lookup"><span data-stu-id="9d871-325">You can assign different Guides to each route version.</span></span>

### <a name="add-a-guide-to-a-route-version"></a><span data-ttu-id="9d871-326">Lägg till en guide till en flödesversion</span><span class="sxs-lookup"><span data-stu-id="9d871-326">Add a Guide to a route version</span></span>

<span data-ttu-id="9d871-327">Lägg till en guide till en flödesversion:</span><span class="sxs-lookup"><span data-stu-id="9d871-327">To add a Guide to a route version:</span></span>

1. <span data-ttu-id="9d871-328">Gå till **produktionskontroll \> alla flöden**.</span><span class="sxs-lookup"><span data-stu-id="9d871-328">Go to **Production control \> All routes**.</span></span>
1. <span data-ttu-id="9d871-329">Öppna det flöde som du vill tilldela en guide till.</span><span class="sxs-lookup"><span data-stu-id="9d871-329">Open the route that you want to assign a Guide to.</span></span>
1. <span data-ttu-id="9d871-330">På snabbfliken **Versioner** välj den version som du vill tilldela en guide till.</span><span class="sxs-lookup"><span data-stu-id="9d871-330">On the **Versions** FastTab, select the version you want to assign a Guide to.</span></span>
1. <span data-ttu-id="9d871-331">I verktygsfältet **Versioner** väljer du **Koppla guider**.</span><span class="sxs-lookup"><span data-stu-id="9d871-331">On the **Versions** toolbar, select **Associated Guides**.</span></span>
    <span data-ttu-id="9d871-332">![Öppna de guider som associeras med en vald flödesversion](media/instruction-guides-RouteVersion.png "Öppna de guider som associeras med en vald flödesversion")</span><span class="sxs-lookup"><span data-stu-id="9d871-332">![Open the Guides associated with a selected route version](media/instruction-guides-RouteVersion.png "Open the Guides associated with a selected route version")</span></span>
1. <span data-ttu-id="9d871-333">Sidan **Associerade guider** öppnas för den valda strukturlisteversionen.</span><span class="sxs-lookup"><span data-stu-id="9d871-333">The **Associated Guides** page opens for your BOM version.</span></span>
1. <span data-ttu-id="9d871-334">Välj **Lägg till** i åtgärdsfönstret för att lägga till en ny rad i rutnätet.</span><span class="sxs-lookup"><span data-stu-id="9d871-334">Select **Add** on the Action Pane to add a new line to the grid.</span></span>
1. <span data-ttu-id="9d871-335">För den nya raden använder du listrutan i kolumnen **namn** för att välja den guider du vill tilldela.</span><span class="sxs-lookup"><span data-stu-id="9d871-335">For the new line, use the drop-down list in the **Name** column to choose the Guide you want to assign.</span></span>
    <span data-ttu-id="9d871-336">![Lägg till en guide till en flödesversion](media/instruction-guides-RouteVersionAddGuide.png "Lägg till en guide till en flödesversion")</span><span class="sxs-lookup"><span data-stu-id="9d871-336">![Adding a Guide to a route version](media/instruction-guides-RouteVersionAddGuide.png "Adding a Guide to a route version")</span></span>

## <a name="associate-a-guide-to-a-route-operation-relation"></a><a name="route-operation-relations"></a><span data-ttu-id="9d871-337">Associera en guide till en flödesoperationsrelation</span><span class="sxs-lookup"><span data-stu-id="9d871-337">Associate a Guide to a route operation relation</span></span>

<span data-ttu-id="9d871-338">Du kan lägga till en guide för alla [flödesoperationsrelationer](routes-operations.md#operation-relations).</span><span class="sxs-lookup"><span data-stu-id="9d871-338">You can add a guide to any [route operation relation](routes-operations.md#operation-relations).</span></span>

### <a name="typical-scenario-using-route-operation-relations"></a><span data-ttu-id="9d871-339">Vanligt scenario med flödesoperationsrelationer</span><span class="sxs-lookup"><span data-stu-id="9d871-339">Typical scenario using route operation relations</span></span>

<span data-ttu-id="9d871-340">Operationsrelationer är det mest specifika sättet att lägga till vägledning för en produktprocess och dess relaterade operationer.</span><span class="sxs-lookup"><span data-stu-id="9d871-340">Operation relations are the most specific way to add guidance to a product process and its related operations.</span></span> <span data-ttu-id="9d871-341">Du kan ange vägledning för varje operation i ett flöde och ange olika vägledning för vilken typ av relationskontext som anges för ett flöde, t.ex. för specifika artiklar, konfigurationer med mera.</span><span class="sxs-lookup"><span data-stu-id="9d871-341">You can specify guidance for each operation in a route and specify different guidance for any type of relation context specified for a route, such as for specific items, configurations, and more.</span></span> <span data-ttu-id="9d871-342">Du kan också ange för vilka faser i operationen som vägledningen gäller (t.ex. inställningar, köhantering, process eller transport).</span><span class="sxs-lookup"><span data-stu-id="9d871-342">You can also specify to which stages in the operation the guidance applies (such as setup, queueing, process, or transport).</span></span>

> [!NOTE]
> <span data-ttu-id="9d871-343">Om du anger guider för flera operationsrelationer för ett flöde, bland dessa guider, visas bara guiden från den mest specifika relationen i arbetsstyrningen för det genererade jobbet.</span><span class="sxs-lookup"><span data-stu-id="9d871-343">If you specify guides for several operation relations of a route, among those guides, only the guide from the most specific relation will be show on the shop floor for the generated job.</span></span>

### <a name="add-a-guide-to-a-route-operation-relation"></a><span data-ttu-id="9d871-344">Lägg till en guide till en flödesoperationsrelation</span><span class="sxs-lookup"><span data-stu-id="9d871-344">Add a Guide to a route operation relation</span></span>

<span data-ttu-id="9d871-345">Lägg till en guide till en flödesoperationsrelation:</span><span class="sxs-lookup"><span data-stu-id="9d871-345">To add a Guide to a route operation relation:</span></span>

1. <span data-ttu-id="9d871-346">Gå till **produktionskontroll \> alla flöden**.</span><span class="sxs-lookup"><span data-stu-id="9d871-346">Go to **Production control \> All routes**.</span></span>
1. <span data-ttu-id="9d871-347">Öppna det flöde som du vill tilldela en guide till.</span><span class="sxs-lookup"><span data-stu-id="9d871-347">Open the route that you want to assign a Guide to.</span></span>
1. <span data-ttu-id="9d871-348">I åtgärdsfönstret, öppna fliken **Flöde** och från gruppen **Underhåll** välj **Flödesdetaljer**.</span><span class="sxs-lookup"><span data-stu-id="9d871-348">On the Action Pane, open the **Route** tab and from the **Maintain** group, select **Route details**.</span></span>
1. <span data-ttu-id="9d871-349">Sidan **Flödesinformation** öppnas för det valda flödet.</span><span class="sxs-lookup"><span data-stu-id="9d871-349">The **Route details** page opens for your selected rout.</span></span>
1. <span data-ttu-id="9d871-350">Välj den operation som du vill ge vägledning för i det övre rutnätet.</span><span class="sxs-lookup"><span data-stu-id="9d871-350">In the top grid, select the operation you want to provide guidance for.</span></span>
1. <span data-ttu-id="9d871-351">I det nedre rutnätet väljer du en specifik relation (eller det generiska **Alla** relation).</span><span class="sxs-lookup"><span data-stu-id="9d871-351">In the bottom grid, select a specific relation (or the generic **All** relation).</span></span>
    <span data-ttu-id="9d871-352">![Välj en operation och sedan en relation](media/instruction-guides-RouteOperationRelation.png "Välj en operation och sedan en relation")</span><span class="sxs-lookup"><span data-stu-id="9d871-352">![Select an operation and then a relation](media/instruction-guides-RouteOperationRelation.png "Select an operation and then a relation")</span></span>
1. <span data-ttu-id="9d871-353">Ovanför den nedre rutnätet öppnar du fliken **Kopplade guider**. ![Fliken Kopplade guider](media/instruction-guides-RouteOperationRelation-AddGuide.png "Fliken kopplade guider")</span><span class="sxs-lookup"><span data-stu-id="9d871-353">Above the bottom gird, open the **Associated Guides** tab.  ![The Associated Guides tab](media/instruction-guides-RouteOperationRelation-AddGuide.png "The Associated Guides tab")</span></span>
1. <span data-ttu-id="9d871-354">Välj **Lägg till** från verktygsfältet högst upp i det nedre rutnätet för att lägga till en ny rad till rutnätet.</span><span class="sxs-lookup"><span data-stu-id="9d871-354">Select **Add** from the toolbar at the top of the bottom grid to add a new line to the grid.</span></span>
1. <span data-ttu-id="9d871-355">För den nya raden använder du listrutan i kolumnen **namn** för att välja den guider du vill tilldela.</span><span class="sxs-lookup"><span data-stu-id="9d871-355">For the new row, use the drop-down list in the **Name** column to choose the Guide you want to assign.</span></span> <span data-ttu-id="9d871-356">Markera kryssrutan för varje kontext där den valda guiden ska vara tillgänglig i resten av raden.</span><span class="sxs-lookup"><span data-stu-id="9d871-356">In the rest of the row, select the check box for each context where the selected Guide should be available.</span></span>

> [!NOTE]
> <span data-ttu-id="9d871-357">Du kan lägga till en eller flera guider för varje steg i varje operation.</span><span class="sxs-lookup"><span data-stu-id="9d871-357">You can add one or more guides for each stage of each operation.</span></span>

## <a name="select-guides-from-the-shop-floor-execution-interface"></a><span data-ttu-id="9d871-358">Välj guider från gränssnittet för arbetsstyrningskörning</span><span class="sxs-lookup"><span data-stu-id="9d871-358">Select guides from the shop floor execution interface</span></span>

<span data-ttu-id="9d871-359">När en arbetare öppnar en jobblista i gränssnittet för arbetsstyrningskörningen, hittar Supply Chain Management relevanta guider för de jobb som visas.</span><span class="sxs-lookup"><span data-stu-id="9d871-359">When a worker opens a job list on the shop floor execution interface, Supply Chain Management finds the relevant guides for the jobs shown.</span></span> <span data-ttu-id="9d871-360">Använd knappen **Guider** om du vill visa relevanta guider.</span><span class="sxs-lookup"><span data-stu-id="9d871-360">Use the **Guides** button to view the relevant guides.</span></span>

<span data-ttu-id="9d871-361">![Knappen guider från gränssnittet för arbetsstyrningskörning](media/instruction-guides-Shopfloor1.png "Knappen guider från gränssnittet för arbetsstyrningskörning")</span><span class="sxs-lookup"><span data-stu-id="9d871-361">![Guides button in the shop floor execution interface](media/instruction-guides-Shopfloor1.png "Guides button in the shop floor execution interface")</span></span>

<span data-ttu-id="9d871-362">Sätt sedan på en HoloLens och gå till respektive guide efter att titta på QR-koden och aktivera respektive guide.</span><span class="sxs-lookup"><span data-stu-id="9d871-362">Then put on a HoloLens and access the respective guide by glancing at the QR code and activating the respective Guide.</span></span>

<span data-ttu-id="9d871-363">![QR-kod för åtkomst till guider med HoloLens](media/instruction-guides-Shopfloor2.png "QR-kod för åtkomst till guider med HoloLens")</span><span class="sxs-lookup"><span data-stu-id="9d871-363">![QR code to access guides using a HoloLens](media/instruction-guides-Shopfloor2.png "QR code to access guides using a HoloLens")</span></span>

## <a name="resolving-the-logic-for-selecting-guides"></a><a name="logic"></a><span data-ttu-id="9d871-364">Lösa logiken för att markera guider</span><span class="sxs-lookup"><span data-stu-id="9d871-364">Resolving the logic for selecting Guides</span></span>

<span data-ttu-id="9d871-365">Du kan lägga till guider till följande produktionsdata:</span><span class="sxs-lookup"><span data-stu-id="9d871-365">You can add Guides to the following production data:</span></span>

- [<span data-ttu-id="9d871-366">Resurser</span><span class="sxs-lookup"><span data-stu-id="9d871-366">Resources</span></span>](#resources)
- [<span data-ttu-id="9d871-367">Resursgrupper</span><span class="sxs-lookup"><span data-stu-id="9d871-367">Resource groups</span></span>](#resource-groups)
- [<span data-ttu-id="9d871-368">Frisläppta produkter</span><span class="sxs-lookup"><span data-stu-id="9d871-368">Released products</span></span>](#released-products)
- [<span data-ttu-id="9d871-369">Formler</span><span class="sxs-lookup"><span data-stu-id="9d871-369">Formulas</span></span>](#formulas)
- [<span data-ttu-id="9d871-370">Formelversioner</span><span class="sxs-lookup"><span data-stu-id="9d871-370">Formula versions</span></span>](#formula-versions)
- [<span data-ttu-id="9d871-371">Strukturlista</span><span class="sxs-lookup"><span data-stu-id="9d871-371">Bills of material (BOMs)</span></span>](#bom)
- [<span data-ttu-id="9d871-372">Strukturlisteversioner</span><span class="sxs-lookup"><span data-stu-id="9d871-372">BOM versions</span></span>](#bom-versions)
- [<span data-ttu-id="9d871-373">Rutter</span><span class="sxs-lookup"><span data-stu-id="9d871-373">Routes</span></span>](#routes)
- [<span data-ttu-id="9d871-374">Flödesversioner</span><span class="sxs-lookup"><span data-stu-id="9d871-374">Route versions</span></span>](#route-versions)
- [<span data-ttu-id="9d871-375">Flödesoperationsrelation</span><span class="sxs-lookup"><span data-stu-id="9d871-375">Route operation relations</span></span>](#route-operation-relations)

<span data-ttu-id="9d871-376">När Supply Chain Management genererar jobben för produktionsgolvet, samlar det in relevanta guider från dessa källor.</span><span class="sxs-lookup"><span data-stu-id="9d871-376">When Supply Chain Management generates the jobs for the production floor, it will collect the relevant Guides from those sources.</span></span> <span data-ttu-id="9d871-377">Notera följande viktiga regler.</span><span class="sxs-lookup"><span data-stu-id="9d871-377">Take note of the following important rules.</span></span>

- <span data-ttu-id="9d871-378">Om du kopplar en strukturlisteversion eller en formelversion till ett flöde tillverkningsorder, visas alla guider som är kopplade till den aktuella versionen och även de stödlinjer som är kopplade till den överordnade strukturlistan eller formeln för den versionen, visas i jobbet.</span><span class="sxs-lookup"><span data-stu-id="9d871-378">If you attach a BOM version or formula version to a route or production order, then any Guides attached to this version, and also the Guides attached to the parent BOM or formula of that version, will be shown on the job.</span></span>
- <span data-ttu-id="9d871-379">Om du kopplar ett flöde till en tillverkningsorder, visas alla guider som är kopplade till den aktuella versionen och även de stödlinjer som är kopplade till det överordnade flödet för den versionen, visas i jobbet.</span><span class="sxs-lookup"><span data-stu-id="9d871-379">If you attach a route version to a production order, then any Guides attached to this version, and also the Guides attached to the parent route of that version, will be shown on the job.</span></span>
- <span data-ttu-id="9d871-380">Om du definierar flera flödesoperationsrelationer som omfattar *alla* relationer och tilldelar guider till dem, visas bara guiderna från den mest specifika relationen för jobbet.</span><span class="sxs-lookup"><span data-stu-id="9d871-380">If you define several route operation relations that include the *All* relation and assign Guides to those, only the Guides from the most specific relation will be shown for the job.</span></span>  

<span data-ttu-id="9d871-381">![Diagram för att lösa relevanta guider](media/instruction-guides-Resolve.png "Diagram för att lösa relevanta guider")</span><span class="sxs-lookup"><span data-stu-id="9d871-381">![Diagram on resolving the relevant Guides](media/instruction-guides-Resolve.png "Diagram on resolving the relevant Guides")</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]