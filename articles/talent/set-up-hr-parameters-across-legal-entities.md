---
title: Ställ in personalparametrar bland juridiska personer
description: Du måste ställa in delade parametrar för poster som delas av flera företag, till exempel befattningsposter. Den här artikeln innehåller information om hur du ställer in personalparametrar för juridiska personer.
author: andreabichsel
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: HcmSharedParameters
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations, Talent
ms.custom: 51891
ms.assetid: c7d8f58c-d78a-4035-abbf-2b0ce16109fe
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Talent July 2017 update
ms.openlocfilehash: a8167545864a1cc2fc22f044f7d16ca590d59b43
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/07/2019
ms.locfileid: "1519152"
---
# <a name="set-up-human-resources-hr-parameters-across-legal-entities"></a><span data-ttu-id="5b786-104">Ställ in personalparametrar bland juridiska personer</span><span class="sxs-lookup"><span data-stu-id="5b786-104">Set up Human resources (HR) parameters across legal entities</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="5b786-105">Du måste ställa in delade parametrar för poster som delas av flera företag, till exempel befattningsposter.</span><span class="sxs-lookup"><span data-stu-id="5b786-105">You must set up shared parameters for records that are shared across companies, such as Position records.</span></span> <span data-ttu-id="5b786-106">Den här artikeln innehåller information om hur du ställer in personalparametrar för juridiska personer.</span><span class="sxs-lookup"><span data-stu-id="5b786-106">This article explains how to set up Human resources parameters across legal entities.</span></span>

<span data-ttu-id="5b786-107">Vissa typer av poster, såsom läge, delas mellan företag.</span><span class="sxs-lookup"><span data-stu-id="5b786-107">Some types of records, such as Position records, are shared across companies.</span></span> <span data-ttu-id="5b786-108">För dessa poster måste du ställa in delad parametrar.</span><span class="sxs-lookup"><span data-stu-id="5b786-108">For these records, you must set up shared parameters.</span></span> <span data-ttu-id="5b786-109">Du kan till exempel använda **mänskliga resurser delade parametrar** för att ställa in mänskliga resurser parametrar över juridiska personer.</span><span class="sxs-lookup"><span data-stu-id="5b786-109">For example, you use the **Human resources shared parameters** page to set up Human resources parameters across legal entities.</span></span> 

<span data-ttu-id="5b786-110">På **mänskliga resurser delade parametrar sidan** , parametrar är indelade i områden, baserade på deras funktionsduglighet.</span><span class="sxs-lookup"><span data-stu-id="5b786-110">On the **Human resources shared parameters** page, parameters are grouped into areas, based on their functionality.</span></span> 

### <a name="previously-released-functionality"></a><span data-ttu-id="5b786-111">Tidigare utgivna funktioner</span><span class="sxs-lookup"><span data-stu-id="5b786-111">Previously released functionality</span></span>
<span data-ttu-id="5b786-112">På **fliken identifiering** , måste du välja id typer som representerar ID-nummer som finns på sidan.</span><span class="sxs-lookup"><span data-stu-id="5b786-112">On the **Identification** tab, you must select the identification types that represent the identification numbers that are listed on the page.</span></span> <span data-ttu-id="5b786-113">Du måste ställa in identifieringtyper innan du kan ange identifieringsinformation för anställd.</span><span class="sxs-lookup"><span data-stu-id="5b786-113">You must set up identification types before you can enter identification information for workers.</span></span> <span data-ttu-id="5b786-114">Information om personnummer, försäkringsnummer, Alien-ID-nummer och personliga ID-kod bibehålls på **identifiering typ** page.</span><span class="sxs-lookup"><span data-stu-id="5b786-114">Information about the Social Security number, national ID number, alien ID number, and personal ID code is maintained on the **Identification type** page.</span></span> <span data-ttu-id="5b786-115">För att definiera en ny typ av identifiering eller granska listan över befintliga typer, klicka på **Mänskliga resurser** &gt; **Länkflik** &gt; **Inställningar** &gt; **Identifieringstyper**.</span><span class="sxs-lookup"><span data-stu-id="5b786-115">To define a new identification type or review the list of existing types, click **Personnel management** &gt; **Links tab** &gt; **Setup** &gt; **Identification types**.</span></span> <span data-ttu-id="5b786-116">Du kan ange en enkel kod och beskrivning.</span><span class="sxs-lookup"><span data-stu-id="5b786-116">You can enter a simple code and description.</span></span> 

### <a name="if-youre-using-dynamics-365-for-talent"></a><span data-ttu-id="5b786-117">Om du använder Dynamics 365 for Talent</span><span class="sxs-lookup"><span data-stu-id="5b786-117">If you're using Dynamics 365 for Talent</span></span>
<span data-ttu-id="5b786-118">På **fliken identifiering** , måste du välja id typer som representerar ID-nummer som finns på sidan.</span><span class="sxs-lookup"><span data-stu-id="5b786-118">On the **Identification** tab, you must select the identification types that represent the identification numbers that are listed on the page.</span></span> <span data-ttu-id="5b786-119">Du måste ställa in identifieringtyper innan du kan ange identifieringsinformation för anställd.</span><span class="sxs-lookup"><span data-stu-id="5b786-119">You must set up identification types before you can enter identification information for workers.</span></span> <span data-ttu-id="5b786-120">Information om personnummer, försäkringsnummer, Alien-ID-nummer och personliga ID-kod bibehålls på **identifiering typ** page.</span><span class="sxs-lookup"><span data-stu-id="5b786-120">Information about the Social Security number, national ID number, alien ID number, and personal ID code is maintained on the **Identification type** page.</span></span> <span data-ttu-id="5b786-121">För att definiera en ny typ av identifiering eller granska listan över befintliga typer, klicka på **Mänskliga resurser** &gt; **Inställningar** &gt; **Identifieringstyper**.</span><span class="sxs-lookup"><span data-stu-id="5b786-121">To define a new identification type or review the list of existing types, click **Human resources** &gt; **Setup** &gt; **Identification types**.</span></span> <span data-ttu-id="5b786-122">Du kan ange en enkel kod och beskrivning.</span><span class="sxs-lookup"><span data-stu-id="5b786-122">You can enter a simple code and description.</span></span> 

<span data-ttu-id="5b786-123">På fliken **Nummersekvenser** kan du välja antalet sekvenser som används för följande poster: Anställningsnummer, befattning, användarens begärande-ID, 1-9 dokument, sökande, diskussion, förmåns-ID och personalåtgärd (om detta är aktiverat).</span><span class="sxs-lookup"><span data-stu-id="5b786-123">On the **Number sequences** tab, you can select the number sequences that are used for the following records: Personnel number, Position, User request ID, I-9 document, Applicant, Discussion, Benefit ID, and Personnel action (if this record type is enabled).</span></span> <span data-ttu-id="5b786-124">För att bibehålla nummersekvens referenser och koder, använd **nummersekvens** listsidan.</span><span class="sxs-lookup"><span data-stu-id="5b786-124">To maintain number sequence references and codes, use the **Number sequences** list page.</span></span> <span data-ttu-id="5b786-125">För att hitta denna sida, använd sidan sökfunktionen.</span><span class="sxs-lookup"><span data-stu-id="5b786-125">To find this page, use the page search feature.</span></span> 

<span data-ttu-id="5b786-126">På **fliken positioner** , ange om nya positioner som är tillgängliga för tilldelning som standard:</span><span class="sxs-lookup"><span data-stu-id="5b786-126">On the **Positions** tab, indicate whether new positions are available for assignment by default:</span></span>

-   <span data-ttu-id="5b786-127">**Alltid** – Du kan tilldela arbetstagare till nya positioner när positioner skapas.</span><span class="sxs-lookup"><span data-stu-id="5b786-127">**Always** – You can assign workers to new positions when positions are created.</span></span> <span data-ttu-id="5b786-128">När befattningar skapas kommer datum och tid för **Tillgänglig för tilldelningar** på fliken **Allmänt** på sidan **Position** anges automatiskt till skapandedatum och -tid.</span><span class="sxs-lookup"><span data-stu-id="5b786-128">When positions are created, the **Available for assignment** date and time on the **General** tab of the **Position** page are automatically set to the creation date and time.</span></span>
-   <span data-ttu-id="5b786-129">**Aldrig** – Du kan inte tilldela arbetstagare till nya positioner när positioner skapas.</span><span class="sxs-lookup"><span data-stu-id="5b786-129">**Never** – You can't assign workers to new positions when positions are created.</span></span> <span data-ttu-id="5b786-130">Om du väljer det här alternativet, måste du öppna **läge** sida för varje ny position när den blir tillgänglig, och sedan på **fliken Allmänt** anger du är **tillgängliga för tilldelning** datum att arbetstagaren uppdrag.</span><span class="sxs-lookup"><span data-stu-id="5b786-130">If you select this option, you must open the **Position** page for each new position as it becomes available, and then, on the **General** tab, enter the **Available for assignment** date to enable worker assignment.</span></span>


<a name="additional-resources"></a><span data-ttu-id="5b786-131">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="5b786-131">Additional resources</span></span>
--------

[<span data-ttu-id="5b786-132">Ställa in företagsspecifika HR parametrar</span><span class="sxs-lookup"><span data-stu-id="5b786-132">Set up company specific HR parameters</span></span>](set-up-company-specific-hr-parameters.md)



