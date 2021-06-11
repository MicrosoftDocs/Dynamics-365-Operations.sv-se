---
title: Mappa kompetenser
description: Du kan skapa en färdighetsmappningssökning för att hitta en kvalificerad person i Dynamics 365 Human Resources.
author: andreabichsel
manager: tfehr
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HcmSkill, HcmSkillGapProfile, HcmSkillMapping, HcmSkillType, HcmEmployeeDevelopmentWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 3361
ms.assetid: c2ce94c0-933d-4edb-822c-7f0e7b49e4ee
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Human Resources
ms.openlocfilehash: 03b7860fbde89097141cfe48f2c240dc127aa9c3
ms.sourcegitcommit: 48528233e0f02dbd47e96e030254ef65f2bb899e
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/20/2021
ms.locfileid: "6076615"
---
# <a name="map-skills"></a><span data-ttu-id="5fae9-103">Mappa kompetenser</span><span class="sxs-lookup"><span data-stu-id="5fae9-103">Map skills</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="5fae9-104">Du kan skapa en färdighetsmappningssökning för att hitta en kvalificerad person i Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="5fae9-104">You can create a skill-mapping search to find a qualified person in Dynamics 365 Human Resources.</span></span> <span data-ttu-id="5fae9-105">Färdighetsmappning söker efter returresultat efter de kriterier du anger genom att leta igenom följande information:</span><span class="sxs-lookup"><span data-stu-id="5fae9-105">Skill-mapping searches return results for criteria you enter by looking through the following information:</span></span>

- <span data-ttu-id="5fae9-106">Kompetenser</span><span class="sxs-lookup"><span data-stu-id="5fae9-106">Skills</span></span>
- <span data-ttu-id="5fae9-107">Utbildning</span><span class="sxs-lookup"><span data-stu-id="5fae9-107">Education</span></span>
- <span data-ttu-id="5fae9-108">Intyg</span><span class="sxs-lookup"><span data-stu-id="5fae9-108">Certificates</span></span>
- <span data-ttu-id="5fae9-109">Befattningar</span><span class="sxs-lookup"><span data-stu-id="5fae9-109">Positions</span></span>
- <span data-ttu-id="5fae9-110">Projekterfarenhet</span><span class="sxs-lookup"><span data-stu-id="5fae9-110">Project experience</span></span>

<span data-ttu-id="5fae9-111">Du kan till exempel hitta personer i organisationen som har fått sin CPA.</span><span class="sxs-lookup"><span data-stu-id="5fae9-111">For example, you can find people in your organization who have earned their CPA.</span></span>

<span data-ttu-id="5fae9-112">Färdighetsmappningsprofiler låter dig hitta nuvarande anställda eller kandidater med kvalifikationer som direkt motsvarar verksamhetens behov.</span><span class="sxs-lookup"><span data-stu-id="5fae9-112">Skill-mapping profiles allow you to find current employees or candidates with qualifications that directly correspond to business needs.</span></span>

> [!NOTE]
> <span data-ttu-id="5fae9-113">Endast anställda, sökande och kontaktpersoner som valts för inkludering i sökningar efter kompetensmappning kan visas i resultatlistan från en kompetensmappning eller inkluderas i kompetensprofil.</span><span class="sxs-lookup"><span data-stu-id="5fae9-113">Only workers, applicants, and contact persons who are selected to be included in skill-mapping searches will display in a skill-mapping results list, or be included in a skill profile.</span></span> <span data-ttu-id="5fae9-114">Om du vill ta med en person i färdighetsmappningsökningar markerar du i alternativet **Inkludera i färdighetsmappning** **Ja** på följande sidor:</span><span class="sxs-lookup"><span data-stu-id="5fae9-114">To include a person in skill mapping searches, set the **Include in skill mapping** selection to **Yes** in the following pages:</span></span><br>
> - <span data-ttu-id="5fae9-115">Arbetare</span><span class="sxs-lookup"><span data-stu-id="5fae9-115">Worker</span></span><br>
> - <span data-ttu-id="5fae9-116">Medarbetare</span><span class="sxs-lookup"><span data-stu-id="5fae9-116">Employee</span></span><br>
> - <span data-ttu-id="5fae9-117">Sökande</span><span class="sxs-lookup"><span data-stu-id="5fae9-117">Applicant</span></span><br>
> - <span data-ttu-id="5fae9-118">Kontakter</span><span class="sxs-lookup"><span data-stu-id="5fae9-118">Contacts</span></span><br>

<span data-ttu-id="5fae9-119">Om du vill skapa en färdighetsmappning går du till **Utveckling för medarbetare > Länkar > Färdighetsmappning**.</span><span class="sxs-lookup"><span data-stu-id="5fae9-119">To create a skill mapping, go to **Employee development > Links > Skill mapping**.</span></span> <span data-ttu-id="5fae9-120">Om du vill skapa en profil för färdighetsmappning går du till **Utveckling för medarbetare > Länkar > Profil för färdighetsmappning**.</span><span class="sxs-lookup"><span data-stu-id="5fae9-120">To create a skill-mapping profile, go to **Employee development > Links > Skill mapping profiles**.</span></span>

## <a name="skill-gap-analysis-and-skill-profile-analysis"></a><span data-ttu-id="5fae9-121">Analys av färdighetsluckor och analys av kompetensprofil</span><span class="sxs-lookup"><span data-stu-id="5fae9-121">Skill gap analysis and skill profile analysis</span></span>

<span data-ttu-id="5fae9-122">Du kan skapa en färdighetsprofilanalys om du vill visa en lista med personens kompetenser.</span><span class="sxs-lookup"><span data-stu-id="5fae9-122">You can create a skill profile analysis to view a list of a person's competencies.</span></span> <span data-ttu-id="5fae9-123">Du kan skapa en analys för luckor i kompetens om du vill jämföra en persons kompetenser med de kompetenser som krävs för ett jobb.</span><span class="sxs-lookup"><span data-stu-id="5fae9-123">You can create a skill gap analysis to compare a person’s skills and the skills required for a job.</span></span>

<span data-ttu-id="5fae9-124">Om du vill skapa en analys av luckor går du till **Medarbetarutveckling > Länkar > Jobb för analys av färdighetsluckor - person**.</span><span class="sxs-lookup"><span data-stu-id="5fae9-124">To create a gap analysis, go to **Employee development > Links > Skill gap analysis job - person**.</span></span> <span data-ttu-id="5fae9-125">Om du vill skapa en analys av kompetensprofil går du till **Utveckling för medarbetare > Länkar > Analys av kompetensprofil**.</span><span class="sxs-lookup"><span data-stu-id="5fae9-125">To create a skill profile analysis, go to **Employee development > Links > Skill profile analysis**.</span></span>

## <a name="see-also"></a><span data-ttu-id="5fae9-126">Se även</span><span class="sxs-lookup"><span data-stu-id="5fae9-126">See also</span></span>

[<span data-ttu-id="5fae9-127">Konfigurera färdigheter</span><span class="sxs-lookup"><span data-stu-id="5fae9-127">Configure skills</span></span>](hr-develop-skills.md)<br>
[<span data-ttu-id="5fae9-128">Ange färdigheter</span><span class="sxs-lookup"><span data-stu-id="5fae9-128">Enter skills</span></span>](hr-develop-enter-skills.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]