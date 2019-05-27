---
title: Ange sökanden och ansökningsdata manuellt
description: I den här proceduren visas hur du manuellt hanterar information om sökanden och hans/hennes ansökning.
author: andreabichsel
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: HcmApplicant, LogisticsContactInfoGrid, HRMApplication,  DirPartyTable
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ea61e3c1d76ade6e0d694b4b521e4be76fc8799d
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/07/2019
ms.locfileid: "1507751"
---
# <a name="enter-applicant-and-application-data-manually"></a><span data-ttu-id="cd93b-103">Ange sökanden och ansökningsdata manuellt</span><span class="sxs-lookup"><span data-stu-id="cd93b-103">Enter applicant and application data manually</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="cd93b-104">I den här proceduren visas hur du manuellt hanterar information om sökanden och hans/hennes ansökning.</span><span class="sxs-lookup"><span data-stu-id="cd93b-104">This procedure shows how to manually maintain information about applicants and their application.</span></span>   <span data-ttu-id="cd93b-105">Du kan ange och hantera personuppgifter, intervjudata och tider, referenser, kompetenser och logiförfrågningar för sökande.</span><span class="sxs-lookup"><span data-stu-id="cd93b-105">You can enter and maintain personal information, interview dates and times, references, competencies, and accommodation requests for applicants.</span></span> <span data-ttu-id="cd93b-106">Du kan även uppdatera statusen för sökandens platsansökningar och skapa brev eller e-postmeddelande för att kommunicera med sökanden.</span><span class="sxs-lookup"><span data-stu-id="cd93b-106">You can also update the status of applicants’ applications for employment and create letters or email messages to communicate with applicants.</span></span> <span data-ttu-id="cd93b-107">När du skapar en sökandepost, skapas en personpost för den sökanden i den globala adressboken.</span><span class="sxs-lookup"><span data-stu-id="cd93b-107">When you create an applicant record, a person record for that applicant is created in the global address book.</span></span>       <span data-ttu-id="cd93b-108">Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF.</span><span class="sxs-lookup"><span data-stu-id="cd93b-108">The demo data company used to create this procedure is USMF.</span></span>


## <a name="create-a-new-applicant-record"></a><span data-ttu-id="cd93b-109">Skapa en ny sökandepost</span><span class="sxs-lookup"><span data-stu-id="cd93b-109">Create a new applicant record</span></span>
1. <span data-ttu-id="cd93b-110">Gå till Personal > Rekrytering > Sökanden > Sökanden.</span><span class="sxs-lookup"><span data-stu-id="cd93b-110">Go to Human resources > Recruitment > Applicants > Applicants.</span></span>
2. <span data-ttu-id="cd93b-111">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="cd93b-111">Click New.</span></span>
3. <span data-ttu-id="cd93b-112">I fältet Förnamn, skriv ett värde.</span><span class="sxs-lookup"><span data-stu-id="cd93b-112">In the First name field, type a value.</span></span>
4. <span data-ttu-id="cd93b-113">I fältet Efternamn, skriv ett värde.</span><span class="sxs-lookup"><span data-stu-id="cd93b-113">In the Last name field, type a value.</span></span>
    * <span data-ttu-id="cd93b-114">Du kan ange ytterligare information om sökande, om det finns tillgängligt.</span><span class="sxs-lookup"><span data-stu-id="cd93b-114">You can enter additional applicant information if it's available.</span></span> <span data-ttu-id="cd93b-115">Du kan till exempel inkludera information om sökandens högsta examen, aktuell jobbtitel eller föregående arbetsgivare.</span><span class="sxs-lookup"><span data-stu-id="cd93b-115">For example, information can include the applicant's highest degree, current job title, or previous employer.</span></span>  
5. <span data-ttu-id="cd93b-116">Växla expansionen av avsnittet Kontaktinformation.</span><span class="sxs-lookup"><span data-stu-id="cd93b-116">Toggle the expansion of the Contact information section.</span></span>
6. <span data-ttu-id="cd93b-117">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="cd93b-117">Click Add.</span></span>
7. <span data-ttu-id="cd93b-118">Skriv "E-post för kommunikation" i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="cd93b-118">In the Description field, type 'Communications email'.</span></span>
8. <span data-ttu-id="cd93b-119">Välj ett alternativ i fältet Typ.</span><span class="sxs-lookup"><span data-stu-id="cd93b-119">In the Type field, select an option.</span></span>
9. <span data-ttu-id="cd93b-120">Skriv ett värde i fältet Kontaktens nummer/adress.</span><span class="sxs-lookup"><span data-stu-id="cd93b-120">In the Contact number/address field, type a value.</span></span>
    * <span data-ttu-id="cd93b-121">Den här e-postadressen används för att skapa e-postkommunikation med den sökande.</span><span class="sxs-lookup"><span data-stu-id="cd93b-121">This email address will be used to generate email communication with the applicant.</span></span>  
10. <span data-ttu-id="cd93b-122">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="cd93b-122">Click Add.</span></span>
11. <span data-ttu-id="cd93b-123">Ange ett värde i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="cd93b-123">In the Description field, type a value.</span></span>
12. <span data-ttu-id="cd93b-124">Skriv ett värde i fältet Kontaktens nummer/adress.</span><span class="sxs-lookup"><span data-stu-id="cd93b-124">In the Contact number/address field, type a value.</span></span>
    * <span data-ttu-id="cd93b-125">Personliga uppgifter om den sökande.</span><span class="sxs-lookup"><span data-stu-id="cd93b-125">Applicant personal information.</span></span>  
    * <span data-ttu-id="cd93b-126">Du kan ange ytterligare personliga uppgifter för den sökande, om det behövs.</span><span class="sxs-lookup"><span data-stu-id="cd93b-126">You can enter additional personal information for the applicant, if needed.</span></span> <span data-ttu-id="cd93b-127">Detta kan till exempel inkludera födelsedatum, etniskt ursprung eller civilstånd.</span><span class="sxs-lookup"><span data-stu-id="cd93b-127">For example, this can include birth date, ethnic origin, gender, or marital status.</span></span>  
13. <span data-ttu-id="cd93b-128">Klicka på Kompetenser i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="cd93b-128">On the Action Pane, click Competencies.</span></span>
    * <span data-ttu-id="cd93b-129">Du kan ange sökandens kompetensprofil, inklusive hans/hennes kompetenser, yrkeserfarenhet, utbildning, tester eller intyg.</span><span class="sxs-lookup"><span data-stu-id="cd93b-129">You can enter the applicant's competency profile, including their skills, professional experiences, education, tests, or certificates.</span></span>  
    * <span data-ttu-id="cd93b-130">Den här informationen kan användas för att mappa sökandens kompetenser till de kompetenser som är associerade med de jobb som har definierats i företagets data.</span><span class="sxs-lookup"><span data-stu-id="cd93b-130">This information can be used to map the applicant's skills to the skills associated with the jobs defined in your company's data.</span></span>   

## <a name="create-an-application-for-the-applicant"></a><span data-ttu-id="cd93b-131">Skapa en ansökning för den sökande</span><span class="sxs-lookup"><span data-stu-id="cd93b-131">Create an application for the applicant</span></span>
1. <span data-ttu-id="cd93b-132">Klicka på Ansökningar.</span><span class="sxs-lookup"><span data-stu-id="cd93b-132">Click Applications.</span></span>
2. <span data-ttu-id="cd93b-133">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="cd93b-133">Click New.</span></span>
3. <span data-ttu-id="cd93b-134">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Rekryteringsprojekt.</span><span class="sxs-lookup"><span data-stu-id="cd93b-134">In the Recruitment project field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="cd93b-135">Genom att välja ett rekryteringsprojekt kommer den sökande att associeras med det specifika jobberbjudande som inkluderas i det rekryteringsprojektet.</span><span class="sxs-lookup"><span data-stu-id="cd93b-135">By selecting a recruitment project, the applicant will be associated with a specific opening included in that recruitment project.</span></span>  
4. <span data-ttu-id="cd93b-136">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="cd93b-136">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="cd93b-137">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="cd93b-137">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="cd93b-138">Som standard baseras jobbet och avdelningen på det valda rekryteringsprojektet.</span><span class="sxs-lookup"><span data-stu-id="cd93b-138">By default, the job and department are based on the selected recruitment project.</span></span>  
6. <span data-ttu-id="cd93b-139">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="cd93b-139">Click Save.</span></span>
    * <span data-ttu-id="cd93b-140">När du har sparat ansökningen kan du koppla dokument till den, inklusive sökandens erfarenhet, belöningar och följebrevet.</span><span class="sxs-lookup"><span data-stu-id="cd93b-140">After saving the application, you can attach documents to it, including the applicant's experience, awards, and cover letter.</span></span>  

