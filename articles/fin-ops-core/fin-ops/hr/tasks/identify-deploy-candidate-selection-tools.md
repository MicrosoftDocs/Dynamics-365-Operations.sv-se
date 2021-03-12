---
title: Identifiera och distribuera kandidaturvalsverktyg
description: Om du vill hitta en kvalificerad pool av kandidater kan det vara svårt att fylla vakanser, särskilt för en befattning kräver en unik kompetenskombination.
author: andreabichsel
manager: AnnBe
ms.date: 11/20/2020
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: HcmSkillMapping, HcmJobLookup, HcmSkillMappingLine, HcmPersonCertificate, CCHTMLPrintPreview
audience: Application User
ms.reviewer: anbichse
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 8015d4e32da2ba80230aa0ad48576948f2fd1678
ms.sourcegitcommit: b112925c389a460a98c3401cc2c67df7091b066f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/19/2020
ms.locfileid: "4797760"
---
# <a name="identify-and-deploy-candidate-selection-tools"></a><span data-ttu-id="a74c2-103">Identifiera och distribuera kandidaturvalsverktyg</span><span class="sxs-lookup"><span data-stu-id="a74c2-103">Identify and deploy candidate selection tools</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="a74c2-104">Om du vill hitta en kvalificerad pool av kandidater kan det vara svårt att fylla vakanser, särskilt för en befattning kräver en unik kompetenskombination.</span><span class="sxs-lookup"><span data-stu-id="a74c2-104">Finding a qualified pool of candidates to fill vacancies can be difficult, especially when a position requires a unique set of skills.</span></span>  <span data-ttu-id="a74c2-105">Det kan dock hända att kandidater med de färdigheter som du behöver redan arbetar i din organisation.</span><span class="sxs-lookup"><span data-stu-id="a74c2-105">However, candidates with the skills you need might already be employed in your organization.</span></span> <span data-ttu-id="a74c2-106">Du kan söka efter en viss kompetensuppsättning bland befintliga medarbetare eller nya sökande.</span><span class="sxs-lookup"><span data-stu-id="a74c2-106">You can search for a specific skill set among existing employees, or new applicants.</span></span> <span data-ttu-id="a74c2-107">Det gör att en rekryterare snabbt kan samla in och gå igenom sökande som har ansökt till en vakans, nu eller tidigare, eller hitta potentiella sökande från sin befintliga pool av medarbetare.</span><span class="sxs-lookup"><span data-stu-id="a74c2-107">This allows a recruiter to quickly gather and screen applicants who have applied for open position now or in the past, or to find potential candidates from their existing pool of employees.</span></span> <span data-ttu-id="a74c2-108">Använd den här uppgiftsregistreringen om du vill veta hur kompetensmappningsfunktionen kan hjälpa dig att hitta rätt person för en vakans.</span><span class="sxs-lookup"><span data-stu-id="a74c2-108">Use this task recording to learn how the skill mapping functionality can help you find the right person for an open position.</span></span> <span data-ttu-id="a74c2-109">Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF.</span><span class="sxs-lookup"><span data-stu-id="a74c2-109">The demo data company used to create this procedure is USMF.</span></span>

1. <span data-ttu-id="a74c2-110">Gå till Personal > Kompetenser > Kompetensanalys > Kompetensmappningsprofiler.</span><span class="sxs-lookup"><span data-stu-id="a74c2-110">Go to Human resources > Competencies > Skill analysis > Skill mapping profiles.</span></span>
2. <span data-ttu-id="a74c2-111">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="a74c2-111">Click New.</span></span>
3. <span data-ttu-id="a74c2-112">Ange ett namn för din kompetensmappning i kompetensmappningsfältet.</span><span class="sxs-lookup"><span data-stu-id="a74c2-112">In the Skill mapping field, enter a name for your skill mapping.</span></span>  <span data-ttu-id="a74c2-113">Exempel: Redovisare.</span><span class="sxs-lookup"><span data-stu-id="a74c2-113">Example: Accountant.</span></span>
4. <span data-ttu-id="a74c2-114">Ange en beskrivning av kompetensmappningen i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="a74c2-114">In the Description field, enter a description of the skill mapping..</span></span>
5. <span data-ttu-id="a74c2-115">Ange ett datum i fältet Datum.</span><span class="sxs-lookup"><span data-stu-id="a74c2-115">In the Date field, enter a date.</span></span>
6. <span data-ttu-id="a74c2-116">Klicka på Hämta profil.</span><span class="sxs-lookup"><span data-stu-id="a74c2-116">Click Retrieve profile.</span></span>
    * <span data-ttu-id="a74c2-117">Använd Hämta profil om du vill hämta data om certifikat, färdighet och utbildning från ett val av person, jobb eller kurs som grund för sökningen.</span><span class="sxs-lookup"><span data-stu-id="a74c2-117">Use Retrieve profile to pull in the Certificate, Skill, and Education data from a selected Person, Job or Course as the basis for your search.</span></span>   <span data-ttu-id="a74c2-118">Du kan sedan lägga till eller ta bort villkor, ange om villkoren är valfria och rangordna betydelsen av villkoret.</span><span class="sxs-lookup"><span data-stu-id="a74c2-118">You can then add or remove criteria, state if the criteria is optional and rank the importance of the criteria.</span></span>  
7. <span data-ttu-id="a74c2-119">Klicka på Jobb.</span><span class="sxs-lookup"><span data-stu-id="a74c2-119">Click Job.</span></span>
8. <span data-ttu-id="a74c2-120">Ange eller välj ett värde i fältet Jobb.</span><span class="sxs-lookup"><span data-stu-id="a74c2-120">In the Job field, enter or select a value.</span></span>
9. <span data-ttu-id="a74c2-121">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="a74c2-121">Click OK.</span></span>
10. <span data-ttu-id="a74c2-122">Expandera FastTab för intervallet och lägg till ytterligare information, till exempel avdelning.</span><span class="sxs-lookup"><span data-stu-id="a74c2-122">Expand the Range FastTab, and add any additional information, such as department.</span></span>
11. <span data-ttu-id="a74c2-123">Expandera FastTab för certifikat för att visa eller redigera certifikat.</span><span class="sxs-lookup"><span data-stu-id="a74c2-123">Expand the Certificates FastTab to view or edit the certificates.</span></span>
12. <span data-ttu-id="a74c2-124">Expandera FastTab för Kompetenser om du vill visa eller redigera kompetenser.</span><span class="sxs-lookup"><span data-stu-id="a74c2-124">Expand the Skills FastTab to view or edit the skills.</span></span>
13. <span data-ttu-id="a74c2-125">Expandera FastTab Utbildning om du vill visa eller redigera utbildningskriterier.</span><span class="sxs-lookup"><span data-stu-id="a74c2-125">Expand the Education FastTab to view or edit the education criteria.</span></span>
14. <span data-ttu-id="a74c2-126">Klicka på Kör.</span><span class="sxs-lookup"><span data-stu-id="a74c2-126">Click Execute.</span></span>
15. <span data-ttu-id="a74c2-127">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="a74c2-127">Click OK.</span></span>
16. <span data-ttu-id="a74c2-128">Klicka på Resultat.</span><span class="sxs-lookup"><span data-stu-id="a74c2-128">Click Result.</span></span>
17. <span data-ttu-id="a74c2-129">Klicka på Resultat.</span><span class="sxs-lookup"><span data-stu-id="a74c2-129">Click Result.</span></span>
18. <span data-ttu-id="a74c2-130">Klicka på Fortsätt.</span><span class="sxs-lookup"><span data-stu-id="a74c2-130">Click Resume.</span></span>
19. <span data-ttu-id="a74c2-131">Klicka på Certifikat.</span><span class="sxs-lookup"><span data-stu-id="a74c2-131">Click Certificates.</span></span>
    * <span data-ttu-id="a74c2-132">Du kan detaljgranska varje person och visa information om deras utbildning, färdigheter och yrkeserfarenhet osv.</span><span class="sxs-lookup"><span data-stu-id="a74c2-132">You can drill further into each person listed and see details regarding their education, skills, and professional experience.</span></span>  
20. <span data-ttu-id="a74c2-133">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="a74c2-133">Close the page.</span></span>
21. <span data-ttu-id="a74c2-134">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="a74c2-134">Close the page.</span></span>
22. <span data-ttu-id="a74c2-135">Välj resultatet igen.</span><span class="sxs-lookup"><span data-stu-id="a74c2-135">Select result again.</span></span>
23. <span data-ttu-id="a74c2-136">Klicka på Rapport.</span><span class="sxs-lookup"><span data-stu-id="a74c2-136">Click Report.</span></span>
    * <span data-ttu-id="a74c2-137">Rapporten anger de bästa matchningarna högst upp i rapporten.</span><span class="sxs-lookup"><span data-stu-id="a74c2-137">The report will list the best matches at the top of the report.</span></span>  <span data-ttu-id="a74c2-138">Du kan se att en lucka är listad.</span><span class="sxs-lookup"><span data-stu-id="a74c2-138">You can see that a gap element is listed.</span></span>  <span data-ttu-id="a74c2-139">Detta är skillnaden mellan nivån som anges i kompetensmappningen och nivån på färdigheten som tilldelas till en person.</span><span class="sxs-lookup"><span data-stu-id="a74c2-139">This is the difference between the level that was listed on the skill mapping, and the level of the skill that is assigned to the person.</span></span>  
24. <span data-ttu-id="a74c2-140">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="a74c2-140">Close the page.</span></span>
25. <span data-ttu-id="a74c2-141">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="a74c2-141">Click Save.</span></span>

