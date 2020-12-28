---
title: Nyheter och ändringar i Dynamics 365 Talent (5 november 2019)
description: Det här ämnet beskriver nya eller ändrade funktioner i Microsoft Dynamics 365 Talent.
author: Darinkramer
manager: AnnBe
ms.date: 11/05/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2019-11-05
ms.dyn365.ops.version: Talent
ms.openlocfilehash: c4068cf81782d2f9559179b91da31e049c006059
ms.sourcegitcommit: e89bb3e5420a6ece84f4e80c11e360b4a042f59d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/17/2020
ms.locfileid: "4527130"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-november-5-2019"></a><span data-ttu-id="f76eb-103">Nyheter och ändringar i Dynamics 365 Talent (5 november 2019)</span><span class="sxs-lookup"><span data-stu-id="f76eb-103">What's new or changed in Dynamics 365 Talent (November 5, 2019)</span></span>

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="f76eb-104">Det här ämnet beskriver nya eller ändrade funktioner i Dynamics 365 Talent.</span><span class="sxs-lookup"><span data-stu-id="f76eb-104">This topic describes features that are either new or changed in Dynamics 365 Talent.</span></span>

## <a name="changes-in-attract"></a><span data-ttu-id="f76eb-105">Ändringar i Attract</span><span class="sxs-lookup"><span data-stu-id="f76eb-105">Changes in Attract</span></span>

<span data-ttu-id="f76eb-106">Den här versionen inkluderar felkorrigeringar för Dynamics 365 Talent: Attract.</span><span class="sxs-lookup"><span data-stu-id="f76eb-106">This release includes minor bug fixes for Dynamics 365 Talent: Attract.</span></span>

## <a name="changes-in-onboard"></a><span data-ttu-id="f76eb-107">Ändringar i Onboard</span><span class="sxs-lookup"><span data-stu-id="f76eb-107">Changes in Onboard</span></span>

<span data-ttu-id="f76eb-108">Den här versionen inkluderar felkorrigeringar för Dynamics 365 Talent: Onboard.</span><span class="sxs-lookup"><span data-stu-id="f76eb-108">This release includes minor bug fixes for Dynamics 365 Talent: Onboard.</span></span>

## <a name="changes-in-core-hr"></a><span data-ttu-id="f76eb-109">Ändringar i Core HR</span><span class="sxs-lookup"><span data-stu-id="f76eb-109">Changes in Core HR</span></span>

<span data-ttu-id="f76eb-110">Ändringar som beskrivs i detta avsnitt gäller versionsnummer 8.1.2598.</span><span class="sxs-lookup"><span data-stu-id="f76eb-110">Changes described in this section apply to build number 8.1.2598.</span></span> <span data-ttu-id="f76eb-111">Siffror inom parenteser i vissa rubriker refererar till supportnummer i Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="f76eb-111">The numbers in parentheses in some headings refer to support numbers in Microsoft Dynamics Lifecycle Services (LCS).</span></span>

### <a name="copy-a-core-hr-instance"></a><span data-ttu-id="f76eb-112">Kopiera en Core HR-instans</span><span class="sxs-lookup"><span data-stu-id="f76eb-112">Copy a Core HR instance</span></span>

<span data-ttu-id="f76eb-113">Under den här veckans utgåva kan du använda Microsoft Dynamics Lifecycle Services (LCS) för att kopiera Microsoft Dynamics 365 Talent: Core HR-databas till ett begränsat läge.</span><span class="sxs-lookup"><span data-stu-id="f76eb-113">In this week's release, you can use Microsoft Dynamics Lifecycle Services (LCS) to copy a Microsoft Dynamics 365 Talent: Core HR database to a sandbox environment.</span></span> <span data-ttu-id="f76eb-114">Om du har en annan miljö med begränsat läge kan du även kopiera databasen från den miljön till en miljö med begränsat läge.</span><span class="sxs-lookup"><span data-stu-id="f76eb-114">If you have another sandbox environment, you can also copy the database from that environment to a targeted sandbox environment.</span></span> <span data-ttu-id="f76eb-115">Mer information finns i:</span><span class="sxs-lookup"><span data-stu-id="f76eb-115">For more information, see:</span></span>

- <span data-ttu-id="f76eb-116">[Bredare miljöhantering](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-talent/broader-environment-management) i Dynamics 365:2019 utgivningsvåg 2-plan</span><span class="sxs-lookup"><span data-stu-id="f76eb-116">[Broader environment management](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-talent/broader-environment-management) in the Dynamics 365: 2019 release wave 2 plan</span></span>

- <span data-ttu-id="f76eb-117">[Kopiera en Core HR-instans](hr-copy-instance.md) i Talent-dokumentationen</span><span class="sxs-lookup"><span data-stu-id="f76eb-117">[Copy a Core HR instance](hr-copy-instance.md) in Talent documentation</span></span>

### <a name="common-data-service-integration-batch-jobs-arent-created-when-common-data-service-integration-is-enabled-388030"></a><span data-ttu-id="f76eb-118">Batchjobb för Common Data Service-integration skapas inte när Common Data Service integrationen är aktiverad (388030)</span><span class="sxs-lookup"><span data-stu-id="f76eb-118">Common Data Service integration batch jobs aren't created when Common Data Service integration is enabled (388030)</span></span>

<span data-ttu-id="f76eb-119">Denna ändring kommer att skapa batchjobb för Common Data Service-integration när den är aktiverad.</span><span class="sxs-lookup"><span data-stu-id="f76eb-119">This change will create batch jobs for Common Data Service integration when it's enabled.</span></span>

### <a name="the-hcmpersonimageentity-doesnt-resize-the-person-image-when-uploaded-369469"></a><span data-ttu-id="f76eb-120">HcmPersonImageEntity ändrar inte storlek på personbilden när den överförs (369469)</span><span class="sxs-lookup"><span data-stu-id="f76eb-120">The HcmPersonImageEntity doesn't resize the person image when uploaded (369469)</span></span>

<span data-ttu-id="f76eb-121">Denna veckas version ändrar hur bilderna storleks ändras för bättre prestanda när de importeras via datahantering.</span><span class="sxs-lookup"><span data-stu-id="f76eb-121">This week's release changes how images are resized for better performance when imported through data management.</span></span>

### <a name="a-positions-available-for-assignment-date-can-be-earlier-than-the-activation-date-340103"></a><span data-ttu-id="f76eb-122">En befattning som är tillgänglig för tilldelningsdatum kan infalla tidigare än aktiveringsdatumet (340103)</span><span class="sxs-lookup"><span data-stu-id="f76eb-122">A position's Available for assignment date can be earlier than the Activation date (340103)</span></span>

<span data-ttu-id="f76eb-123">Med den här ändringen visas en varning om du väljer **Tillgänglig för tilldelningsdatum** som är tidigare än befattningens **aktiveringsdatum**.</span><span class="sxs-lookup"><span data-stu-id="f76eb-123">With this change, a warning will appear if you select an **Available for assignment date** that's earlier than the position's **Activation date**.</span></span>

### <a name="cant-create-a-compensation-change-request-in-employee-self-service-for-step-based-plans-376872"></a><span data-ttu-id="f76eb-124">Det går inte att skapa en begäran om kompensationsändring i medarbetarsjälvbetjäning för stegbaserade planer (376872)</span><span class="sxs-lookup"><span data-stu-id="f76eb-124">Can't create a compensation change request in employee self-service for step-based plans (376872)</span></span>

<span data-ttu-id="f76eb-125">I den här versionen åtgärdas ett problem när kompensationsändringar begärs via medarbetarsjälvbetjäning för stegbaserade planer.</span><span class="sxs-lookup"><span data-stu-id="f76eb-125">This release corrects an issue when requesting compensation changes through employee self-service for step-based plans.</span></span> 

### <a name="reason-code-doesnt-sync-to-common-data-service-if-the-description-is-longer-than-30-characters-core-hr-allows-60-352682"></a><span data-ttu-id="f76eb-126">Orsakskoden synkroniseras inte till Common Data Service om beskrivningen är längre än 30 tecken, så att Core HR tillåter 60 (352682)</span><span class="sxs-lookup"><span data-stu-id="f76eb-126">Reason code doesn't sync to Common Data Service if the description is longer than 30 characters, Core HR allows 60 (352682)</span></span>

<span data-ttu-id="f76eb-127">Med den här ändringen kommer orsakskoder med fler än 30 tecken att uppdateras i Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="f76eb-127">with this change, reason codes with more than 30 characters will be updated in Common Data Service.</span></span> <span data-ttu-id="f76eb-128">Ändringar som görs i Common Data Service kommer också att återspeglas i Talent.</span><span class="sxs-lookup"><span data-stu-id="f76eb-128">Changes made in Common Data Service will also be reflected back in Talent.</span></span>

### <a name="address-integration-from-talent-to-finance-and-operations-351961"></a><span data-ttu-id="f76eb-129">Adressintegrering från Talent till Finance and Operations (351961)</span><span class="sxs-lookup"><span data-stu-id="f76eb-129">Address integration from Talent to Finance and Operations (351961)</span></span>

<span data-ttu-id="f76eb-130">Genom den här versionen åtgärdas problemet att adresser som uppdateras i Talent inte uppdateras i Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="f76eb-130">This release fixes an issue where addresses updated in Talent weren't updating in Finance and Operations.</span></span> <span data-ttu-id="f76eb-131">Ändringar i adressblock kommer nu att uppdateras.</span><span class="sxs-lookup"><span data-stu-id="f76eb-131">Changes to address blocks will now update.</span></span>

## <a name="coming-soon"></a><span data-ttu-id="f76eb-132">Kommer snart</span><span class="sxs-lookup"><span data-stu-id="f76eb-132">Coming soon</span></span>

### <a name="print-performance-reviews"></a><span data-ttu-id="f76eb-133">Skriv ut resultatöversyner</span><span class="sxs-lookup"><span data-stu-id="f76eb-133">Print performance reviews</span></span>

<span data-ttu-id="f76eb-134">Se [Skriv ut resultatöversyner](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-talent/print-performance-reviews) i Dynamics 365: 2019 släpp påfyllnad 2 plan.</span><span class="sxs-lookup"><span data-stu-id="f76eb-134">See [Print performance reviews](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-talent/print-performance-reviews) in the Dynamics 365: 2019 release wave 2 plan.</span></span>

### <a name="feature-management-workspace"></a><span data-ttu-id="f76eb-135">Arbetsytan Funktionshantering</span><span class="sxs-lookup"><span data-stu-id="f76eb-135">Feature management workspace</span></span>

<span data-ttu-id="f76eb-136">Funktioner läggs till och uppdateras i alla versioner.</span><span class="sxs-lookup"><span data-stu-id="f76eb-136">Features are added and updated in every release.</span></span> <span data-ttu-id="f76eb-137">Funktionshanteringen är en arbetsyta där du kan visa en lista med funktioner som har levererats i varje utgåva.</span><span class="sxs-lookup"><span data-stu-id="f76eb-137">The feature management experience provides a workspace where you can view a list of features that have been delivered in each release.</span></span> <span data-ttu-id="f76eb-138">Nya funktionen är avstängda som standard.</span><span class="sxs-lookup"><span data-stu-id="f76eb-138">By default, new features are turned off.</span></span> <span data-ttu-id="f76eb-139">Du kan använda arbetsytan för att aktivera dem och visa dokumentationen för dem.</span><span class="sxs-lookup"><span data-stu-id="f76eb-139">You can use the workspace to turn them on and view the documentation for them.</span></span>

<span data-ttu-id="f76eb-140">Mer information om de ändringar som kommer från funktionshantering finns i [översikt över funktionshantering](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview).</span><span class="sxs-lookup"><span data-stu-id="f76eb-140">To learn more about the changes coming with feature management, see [Feature management overview](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview).</span></span>
