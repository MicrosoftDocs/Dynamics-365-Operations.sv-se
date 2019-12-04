---
title: Spåra kandidatkällor i Attract
description: Det här avsnittet innehåller information om att spåra källan för kandidatprofiler och ansökningar.
author: hachandr
manager: AnnBe
ms.date: 03/18/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent, Core
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2018-10-15
ms.dyn365.ops.version: Talent October 2018 update
ms.openlocfilehash: 8860f508eebc377042c4e101eeb08a14a737ba0c
ms.sourcegitcommit: 9cc6a011bfdd1b0fe505760b6bf429eb6c65862a
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/25/2019
ms.locfileid: "2832681"
---
# <a name="track-candidate-sources-in-attract"></a><span data-ttu-id="7b73e-103">Spåra kandidatkällor i Attract</span><span class="sxs-lookup"><span data-stu-id="7b73e-103">Track candidate sources in Attract</span></span>

[!include [banner](includes/banner.md)]

> [!NOTE] 
> <span data-ttu-id="7b73e-104">Funktionen som beskrivs i det här avsnittet är en del av förhandsversionen.</span><span class="sxs-lookup"><span data-stu-id="7b73e-104">Functionality noted in this topic is available as part of a preview review release.</span></span> <span data-ttu-id="7b73e-105">Funktionen och dess innehåll kan ändras.</span><span class="sxs-lookup"><span data-stu-id="7b73e-105">The content and the functionality are subject to change.</span></span> <span data-ttu-id="7b73e-106">Om du vill använda den här funktionen ber du en administratör att aktivera den med hjälp av **administrationsinställningar** i Attract.</span><span class="sxs-lookup"><span data-stu-id="7b73e-106">To use this feature, ask an administrator to enable it using the **Admin settings** in Attract.</span></span> <span data-ttu-id="7b73e-107">En framtida version kommer att tillhandahålla källspårningsrapporter.</span><span class="sxs-lookup"><span data-stu-id="7b73e-107">A future release will provide source tracking reports.</span></span> <span data-ttu-id="7b73e-108">Mer information finns i [Få åtkomst till förhandsfunktioner i Talent](https://docs.microsoft.com/dynamics365/unified-operations/talent/access-preview-feature).</span><span class="sxs-lookup"><span data-stu-id="7b73e-108">For more information, see [Access preview features in Talent](https://docs.microsoft.com/dynamics365/unified-operations/talent/access-preview-feature).</span></span>

<span data-ttu-id="7b73e-109">När det gäller kandidater för ett jobb, spårar Attract automatiskt källan till sina ansökningar och ger dig värdefull information som hjälper dig att följa upp dina rekryteringsmål.</span><span class="sxs-lookup"><span data-stu-id="7b73e-109">When candidates apply for a job, Attract automatically tracks the source of their applications, providing you with valuable information to help you target your recruiting efforts.</span></span> <span data-ttu-id="7b73e-110">Rekryterare och anställande chefer kan också välja en ansökningskälla medan de manuellt lägger till en kandidat till ett jobb eller en talangpool.</span><span class="sxs-lookup"><span data-stu-id="7b73e-110">Recruiters and hiring managers can also select an application source while manually adding a candidate to a job or talent pool.</span></span>

<span data-ttu-id="7b73e-111">Du kan visa ansökningskällan i ansökningsaktivitetsinformationen under fliken **aktivitet** samt i ansökningshistoriken under **profil** i talangpooler.</span><span class="sxs-lookup"><span data-stu-id="7b73e-111">You can view the application source in the application activity details under the **Activity** tab, as well as in the application history available under **Profile** in talent pools.</span></span> <span data-ttu-id="7b73e-112">Du hittar en kandidats profilkälla i kandidatens information under fliken **profil** i både ansökningar och i talangpooler.</span><span class="sxs-lookup"><span data-stu-id="7b73e-112">You can find a candidate's profile source in the candidate details under the **Profile** tab in both applications and talent pools.</span></span>

> [!NOTE] 
> <span data-ttu-id="7b73e-113">Du hittar processmallar i [tillägget för omfattande anställning](https://docs.microsoft.com/dynamics365/unified-operations/talent/attract-comprehensive-hiring).</span><span class="sxs-lookup"><span data-stu-id="7b73e-113">You can find process templates in the [Comprehensive hiring add-on](https://docs.microsoft.com/dynamics365/unified-operations/talent/attract-comprehensive-hiring).</span></span>

## <a name="pre-configured-sources"></a><span data-ttu-id="7b73e-114">Förkonfigurerade källor</span><span class="sxs-lookup"><span data-stu-id="7b73e-114">Pre-configured sources</span></span>

<span data-ttu-id="7b73e-115">Standardkällistan innehåller gemensamma ansökningskällor.</span><span class="sxs-lookup"><span data-stu-id="7b73e-115">The default source list contains common application sources.</span></span> <span data-ttu-id="7b73e-116">Vissa källtyper såsom **jobbtavla** och **sociala nätverk** har ytterligare källinformation.</span><span class="sxs-lookup"><span data-stu-id="7b73e-116">Some source types, like **Job board** and **Social Network**, have additional source details.</span></span> <span data-ttu-id="7b73e-117">Till exempel **sociala nätverk** inkluderar Facebook och Twitter.</span><span class="sxs-lookup"><span data-stu-id="7b73e-117">For example, **Social Network** includes Facebook and Twitter.</span></span> <span data-ttu-id="7b73e-118">Källtypen **Hänvisning** låter dig ange en intern medarbetare som hänvisaren.</span><span class="sxs-lookup"><span data-stu-id="7b73e-118">The **Referral** source type allows you to specify an internal employee as the referrer.</span></span> <span data-ttu-id="7b73e-119">Standardkällistan innehåller följande förkonfigurerade källor:</span><span class="sxs-lookup"><span data-stu-id="7b73e-119">The default source list includes the following pre-configured sources:</span></span>

-   <span data-ttu-id="7b73e-120">Attract karriärwebbplats</span><span class="sxs-lookup"><span data-stu-id="7b73e-120">Attract career site</span></span>

-   <span data-ttu-id="7b73e-121">Myndighet</span><span class="sxs-lookup"><span data-stu-id="7b73e-121">Agency</span></span>

-   <span data-ttu-id="7b73e-122">Karriärmässa</span><span class="sxs-lookup"><span data-stu-id="7b73e-122">Career Fair</span></span>

-   <span data-ttu-id="7b73e-123">Företagets marknadsföring</span><span class="sxs-lookup"><span data-stu-id="7b73e-123">Company Marketing</span></span>

-   <span data-ttu-id="7b73e-124">Konferenser och mässor</span><span class="sxs-lookup"><span data-stu-id="7b73e-124">Conferences & Trade shows</span></span>

-   <span data-ttu-id="7b73e-125">Professionell association</span><span class="sxs-lookup"><span data-stu-id="7b73e-125">Professional Association</span></span>

-   <span data-ttu-id="7b73e-126">Jobbtavla</span><span class="sxs-lookup"><span data-stu-id="7b73e-126">Job board</span></span>

    -   <span data-ttu-id="7b73e-127">Indeed</span><span class="sxs-lookup"><span data-stu-id="7b73e-127">Indeed</span></span>

    -   <span data-ttu-id="7b73e-128">Seek</span><span class="sxs-lookup"><span data-stu-id="7b73e-128">Seek</span></span>

    -   <span data-ttu-id="7b73e-129">CareerBuilder</span><span class="sxs-lookup"><span data-stu-id="7b73e-129">CareerBuilder</span></span>

    -   <span data-ttu-id="7b73e-130">Google Jobs</span><span class="sxs-lookup"><span data-stu-id="7b73e-130">Google Jobs</span></span>

    -   <span data-ttu-id="7b73e-131">Xing</span><span class="sxs-lookup"><span data-stu-id="7b73e-131">Xing</span></span>

    -   <span data-ttu-id="7b73e-132">Glassdoor</span><span class="sxs-lookup"><span data-stu-id="7b73e-132">Glassdoor</span></span>

    -   <span data-ttu-id="7b73e-133">Monster Jobs</span><span class="sxs-lookup"><span data-stu-id="7b73e-133">Monster Jobs</span></span>

-   <span data-ttu-id="7b73e-134">Tidningar och publikationer</span><span class="sxs-lookup"><span data-stu-id="7b73e-134">Magazines & Publications</span></span>

-   <span data-ttu-id="7b73e-135">Sociala nätverk</span><span class="sxs-lookup"><span data-stu-id="7b73e-135">Social Network</span></span>

    -   <span data-ttu-id="7b73e-136">Facebook</span><span class="sxs-lookup"><span data-stu-id="7b73e-136">Facebook</span></span>

    -   <span data-ttu-id="7b73e-137">Twitter</span><span class="sxs-lookup"><span data-stu-id="7b73e-137">Twitter</span></span>

-   <span data-ttu-id="7b73e-138">Universitetsrekrytering</span><span class="sxs-lookup"><span data-stu-id="7b73e-138">University Recruiting</span></span>

-   <span data-ttu-id="7b73e-139">LinkedIn</span><span class="sxs-lookup"><span data-stu-id="7b73e-139">LinkedIn</span></span>

-   <span data-ttu-id="7b73e-140">Klassificerade</span><span class="sxs-lookup"><span data-stu-id="7b73e-140">Classifieds</span></span>

-   <span data-ttu-id="7b73e-141">Hänvisning</span><span class="sxs-lookup"><span data-stu-id="7b73e-141">Referral</span></span>

-   <span data-ttu-id="7b73e-142">Tillagd av rekryterare</span><span class="sxs-lookup"><span data-stu-id="7b73e-142">Added by Recruiter</span></span>

-   <span data-ttu-id="7b73e-143">Annat</span><span class="sxs-lookup"><span data-stu-id="7b73e-143">Other</span></span>

## <a name="customize-the-source-list"></a><span data-ttu-id="7b73e-144">Anpassa källistan</span><span class="sxs-lookup"><span data-stu-id="7b73e-144">Customize the source list</span></span> 

<span data-ttu-id="7b73e-145">Du kan utöka källistan till att inkludera ytterligare ansökningskällor.</span><span class="sxs-lookup"><span data-stu-id="7b73e-145">You can extend the source list to include additional application sources.</span></span> <span data-ttu-id="7b73e-146">Om du vill anpassa listan följer du instruktionerna i [utöka alternativuppsättningar i Attract](https://docs.microsoft.com/dynamics365/unified-operations/talent/extensibility-attract#extending-option-sets-in-attract).</span><span class="sxs-lookup"><span data-stu-id="7b73e-146">To customize this list, follow the instructions in [Extending Option Sets in Attract](https://docs.microsoft.com/dynamics365/unified-operations/talent/extensibility-attract#extending-option-sets-in-attract).</span></span> <span data-ttu-id="7b73e-147">Redigera entiteten **TalentSource** till att inkludera ytterligare källor.</span><span class="sxs-lookup"><span data-stu-id="7b73e-147">Edit the **TalentSource** entity to include additional sources.</span></span> 

<span data-ttu-id="7b73e-148">För att undvika att negativ påverkan av användargränssnittet ska du inte redigera eller ta bort enum-värdet **TalentCategory** (inte namn) för följande:</span><span class="sxs-lookup"><span data-stu-id="7b73e-148">To avoid negatively impacting the user interface (UI), don't edit or delete the **TalentCategory** enum values (not names) for the following:</span></span>

- <span data-ttu-id="7b73e-149">**Hänvisning**</span><span class="sxs-lookup"><span data-stu-id="7b73e-149">**Referral**</span></span>
- <span data-ttu-id="7b73e-150">**LinkedIn**</span><span class="sxs-lookup"><span data-stu-id="7b73e-150">**LinkedIn**</span></span>
- <span data-ttu-id="7b73e-151">**Annat**</span><span class="sxs-lookup"><span data-stu-id="7b73e-151">**Other**</span></span>

<span data-ttu-id="7b73e-152">Däremot kan du utöka enum **TalentSource** för att lägga till andra typer av källor.</span><span class="sxs-lookup"><span data-stu-id="7b73e-152">Instead, you can extend the **TalentSource** enum to add other types of sources.</span></span>
