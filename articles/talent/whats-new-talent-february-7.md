---
title: Nyheter och ändringar i Dynamics 365 for Talent (7 februari 2019)
description: Det här ämnet beskriver nya eller ändrade funktioner i Microsoft Dynamics 365 for Talent.
author: Darinkramer
manager: AnnBe
ms.date: 02/07/2019
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
ms.search.validFrom: 2019-02-07
ms.dyn365.ops.version: Talent
ms.openlocfilehash: b89fc15130755a80b56f26cf7c61674a26f43e36
ms.sourcegitcommit: 608e68b603afef9eb98d8fb25e90109c2473ef87
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2019
ms.locfileid: "858938"
---
# <a name="whats-new-or-changed-in-dynamics-365-for-talent-february-7-2019"></a><span data-ttu-id="c63d9-103">Nyheter och ändringar i Dynamics 365 for Talent (7 februari 2019)</span><span class="sxs-lookup"><span data-stu-id="c63d9-103">What's new or changed in Dynamics 365 for Talent (February 7, 2019)</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="c63d9-104">Det här ämnet beskriver nya eller ändrade funktioner i Talent.</span><span class="sxs-lookup"><span data-stu-id="c63d9-104">This topic describes features that are either new or changed in Talent.</span></span>

## <a name="changes-in-attract"></a><span data-ttu-id="c63d9-105">Ändringar i Attract</span><span class="sxs-lookup"><span data-stu-id="c63d9-105">Changes in Attract</span></span>

### <a name="interview-scheduling-enhancements"></a><span data-ttu-id="c63d9-106">Förbättring av tidsplanering av intervjuer</span><span class="sxs-lookup"><span data-stu-id="c63d9-106">Interview scheduling enhancements</span></span>
<span data-ttu-id="c63d9-107">Förbättringar har gjorts i tidsplanering för slutpunkt till slutpunkt-intervju.</span><span class="sxs-lookup"><span data-stu-id="c63d9-107">Improvements have been made to the end-to-end interview scheduling experience.</span></span> <span data-ttu-id="c63d9-108">Du kan nu se kalendertillgängligheten för en intern kandidat och använda interna kandidaters kalender för schemarekommendationer.</span><span class="sxs-lookup"><span data-stu-id="c63d9-108">You can now see the calendar availability of an internal candidate and use the internal candidate’s calendar for schedule recommendations.</span></span> <span data-ttu-id="c63d9-109">Mer information finns i [Intervjuplanering och feedback](interview-scheduling-feedback.md).</span><span class="sxs-lookup"><span data-stu-id="c63d9-109">For more information, see [Interview scheduling and feedback](interview-scheduling-feedback.md).</span></span>

### <a name="job-posting-to-linkedin--company-mismatch-issue-fixed"></a><span data-ttu-id="c63d9-110">Jobbpublicering på LinkedIn – företagets matchningsfel har korrigerats</span><span class="sxs-lookup"><span data-stu-id="c63d9-110">Job posting to LinkedIn – company mismatch issue fixed</span></span>
<span data-ttu-id="c63d9-111">Ett problem har åtgärdats där jobb som publicerades på LinkedIn från Attract visades under fel företagsnamn.</span><span class="sxs-lookup"><span data-stu-id="c63d9-111">An issue has been fixed where jobs posted to LinkedIn from Attract were appearing under the wrong company name.</span></span> <span data-ttu-id="c63d9-112">Mer information finns i [skapa, godkänna och publicera projekt i Attract](creating-jobs-attract.md).</span><span class="sxs-lookup"><span data-stu-id="c63d9-112">For more information, see [Create, approve, and post jobs in Attract](creating-jobs-attract.md).</span></span>

### <a name="career-site-url-displayed-in-admin-settings"></a><span data-ttu-id="c63d9-113">Karriärwebbplatsens URL visas i administrationsinställningar</span><span class="sxs-lookup"><span data-stu-id="c63d9-113">Career site URL displayed in Admin settings</span></span>
<span data-ttu-id="c63d9-114">Karriärwebbplatsens startside-URL visas i **administrationsinställningar** under **Hantera karriärwebbplats**.</span><span class="sxs-lookup"><span data-stu-id="c63d9-114">The career site home page URL is now displayed in **Admin Settings** under **Career Site management**.</span></span>

## <a name="changes-in-core-hr"></a><span data-ttu-id="c63d9-115">Ändringar i Core HR</span><span class="sxs-lookup"><span data-stu-id="c63d9-115">Changes in Core HR</span></span>

<span data-ttu-id="c63d9-116">**Skapa 8.1.2134**</span><span class="sxs-lookup"><span data-stu-id="c63d9-116">**Build 8.1.2134**</span></span>

### <a name="multiple-compensation-levels-supported-on-jobs"></a><span data-ttu-id="c63d9-117">Flera kompensationsnivåer som stöds för jobb</span><span class="sxs-lookup"><span data-stu-id="c63d9-117">Multiple compensation levels supported on jobs</span></span>
<span data-ttu-id="c63d9-118">Ändringen tillåter att mer än en kompensationsnivå definieras för ett projekt, vilket tillåter medarbetarens fasta kompensationsintervall som kan variera mellan planer när du använder samma jobb.</span><span class="sxs-lookup"><span data-stu-id="c63d9-118">This change allows for more than one compensation level to be defined on a job, enabling employee fixed compensation ranges which may differ between plans when using the same job.</span></span> 

<span data-ttu-id="c63d9-119">Exempel:</span><span class="sxs-lookup"><span data-stu-id="c63d9-119">For example:</span></span>    
<span data-ttu-id="c63d9-120">*Jobb* - Kontohanterare *Associerade kompensationsnivåer:* B1 och B2 - varje nivå har ett definierat värdeintervall.</span><span class="sxs-lookup"><span data-stu-id="c63d9-120">*Job* - Account Manager *Associated compensation levels:* B1 and B2 - Each level has a defined range of values.</span></span> <span data-ttu-id="c63d9-121">B1 = Min 50 000, Mellan 60 000, Max 75 000 and B2 = Min 65 000, Mellan 74 000, Max 85 000.</span><span class="sxs-lookup"><span data-stu-id="c63d9-121">B1 = Min 50,000, Mid 60,000, Max 75,000 and B2 = Min 65,000, Mid 74,000, Max 85,000.</span></span> <span data-ttu-id="c63d9-122">När du skapar en fast kompensation för medarbetare utifrån definierade berättiganderegler pekar varje fast plan nu på samma jobb och på olika nivåer för jobbet.</span><span class="sxs-lookup"><span data-stu-id="c63d9-122">When creating fixed compensation for employees, based on the eligibility rules defined, each fixed plan can now point to the same job and to different levels on the job.</span></span> <span data-ttu-id="c63d9-123">Detta tillåter att planer definieras i olika regioner/företag och pekar på samma jobb men olika intervall utan att duplicera jobb för att redovisa dessa skillnader.</span><span class="sxs-lookup"><span data-stu-id="c63d9-123">This allows for plans to be defined in different regions/companies and point to the same job but different ranges without duplicating jobs to account for these differences.</span></span>

### <a name="compensation-level-field-has-been-added-to-the-employee-fixed-compensation-entity"></a><span data-ttu-id="c63d9-124">Fält för kompensationsnivåer har lagts till i entiteten medarbetarens fasta kompensation</span><span class="sxs-lookup"><span data-stu-id="c63d9-124">Compensation level field has been added to the Employee fixed compensation entity</span></span> 
<span data-ttu-id="c63d9-125">Med den här uppdateringen har entiteten medarbetarens fasta kompensation uppdaterats med fältet **kompensationsnivå**.</span><span class="sxs-lookup"><span data-stu-id="c63d9-125">With this update, the employee fixed compensation entity has been updated to include the **Compensation level** field.</span></span> <span data-ttu-id="c63d9-126">Detta gör det enklare att uppdatera medarbetarens fasta kompensationsplaner.</span><span class="sxs-lookup"><span data-stu-id="c63d9-126">This addition makes it easier to update employee fixed compensation plans.</span></span> 

### <a name="update-job-family-when-updating-and-creating-new-positions"></a><span data-ttu-id="c63d9-127">Uppdatera jobbfamilj vid uppdatering och skapande av nya befattningar</span><span class="sxs-lookup"><span data-stu-id="c63d9-127">Update Job family when updating and creating new positions</span></span>
<span data-ttu-id="c63d9-128">När du byter jobb på en befattning kommer nu **jobbfamilj** användas som standard baserat på det jobb som valts.</span><span class="sxs-lookup"><span data-stu-id="c63d9-128">When changing the job on a position, **Job family** will now default based on the job selected.</span></span>

### <a name="performance-improvements-when-rendering-workspaces"></a><span data-ttu-id="c63d9-129">Prestandaförbättringar vid återgivning av arbetsytor</span><span class="sxs-lookup"><span data-stu-id="c63d9-129">Performance improvements when rendering workspaces</span></span>
<span data-ttu-id="c63d9-130">Analysflikar på arbetsytor läses nu bara vid åtkomst till sidorna.</span><span class="sxs-lookup"><span data-stu-id="c63d9-130">Analytics tabs on workspaces will now load only when accessing those pages.</span></span> <span data-ttu-id="c63d9-131">En indikator visas under den första återgivningen av sidan i det övre vänstra hörnet på sidan.</span><span class="sxs-lookup"><span data-stu-id="c63d9-131">An indicator will display during the initial rendering of the page in the upper-left corner of the page.</span></span>
