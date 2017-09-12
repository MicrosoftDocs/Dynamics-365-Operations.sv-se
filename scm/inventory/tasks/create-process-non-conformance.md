---
title: "Skapa och bearbeta en överensstämmelse"
description: "Använd den här proceduren för att utföra avvikelsehantering baserat på en befintlig kvalitetsorder."
author: perlynne
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0e7f66cccd76e5326fce75d1a13aff294c16fb9b
ms.openlocfilehash: e5187c44aac881273900b2fc0ca91045a65cd838
ms.contentlocale: sv-se
ms.lasthandoff: 09/12/2017

---
# <a name="create-and-process-a-conformance"></a><span data-ttu-id="7aa51-103">Skapa och bearbeta en överensstämmelse</span><span class="sxs-lookup"><span data-stu-id="7aa51-103">Create and process a conformance</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="7aa51-104">Använd den här proceduren för att utföra avvikelsehantering baserat på en befintlig kvalitetsorder.</span><span class="sxs-lookup"><span data-stu-id="7aa51-104">Use this procedure to perform nonconformance management, based on an existing quality order.</span></span> <span data-ttu-id="7aa51-105">Du kan köra denna registrering i USMF-demonstrationsföretaget och kan använda det föreslagna värdet.</span><span class="sxs-lookup"><span data-stu-id="7aa51-105">You can run this recording in the USMF demo company and can use the suggested values.</span></span> <span data-ttu-id="7aa51-106">Vanligtvis utförs den här proceduren av en kontorist.</span><span class="sxs-lookup"><span data-stu-id="7aa51-106">Typically, this procedure is performed by a quality clerk.</span></span>  <span data-ttu-id="7aa51-107">Kör uppgiftsregistreringen "kontrollera kvaliteten på varor" först.</span><span class="sxs-lookup"><span data-stu-id="7aa51-107">As a prerequisite, run the “Inspect the quality of goods” task recording.</span></span> <span data-ttu-id="7aa51-108">För att bearbeta godkännandet av en avvikelse måste användaren som utför uppgiftsregistreringen ha ett "namn"-värde tilldelat på användarsidan.</span><span class="sxs-lookup"><span data-stu-id="7aa51-108">To process the approval of a nonconformance, the user who runs the task recording must have a “Name” value assigned on the Users page.</span></span> <span data-ttu-id="7aa51-109">För att använda dokumentanteckningar måste användaren även ha Dokumenthantering aktiverat i användaralternativen.</span><span class="sxs-lookup"><span data-stu-id="7aa51-109">To use the document notes, the user must also have Document handling activated in the user options.</span></span>


## <a name="select-a-quality-order"></a><span data-ttu-id="7aa51-110">Välj en kvalitetsorder.</span><span class="sxs-lookup"><span data-stu-id="7aa51-110">Select a quality order</span></span>
1. <span data-ttu-id="7aa51-111">Gå till Kvalitetsorder.</span><span class="sxs-lookup"><span data-stu-id="7aa51-111">Go to Quality orders.</span></span>
2. <span data-ttu-id="7aa51-112">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="7aa51-112">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="7aa51-113">Välj kvalitetsordern som skapades från uppgiftsregistreringen "kontrollera kvaliteten på varor".</span><span class="sxs-lookup"><span data-stu-id="7aa51-113">Select the quality order that was created from the "Inspect the quality of goods" task recording.</span></span>  

## <a name="create-a-nonconformance"></a><span data-ttu-id="7aa51-114">Skapa en avvikelse</span><span class="sxs-lookup"><span data-stu-id="7aa51-114">Create a nonconformance</span></span>
1. <span data-ttu-id="7aa51-115">Klicka på Förfrågningar.</span><span class="sxs-lookup"><span data-stu-id="7aa51-115">Click Inquiries.</span></span>
2. <span data-ttu-id="7aa51-116">Klicka på Avvikelser.</span><span class="sxs-lookup"><span data-stu-id="7aa51-116">Click Non conformances.</span></span>
3. <span data-ttu-id="7aa51-117">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="7aa51-117">Click New.</span></span>
4. <span data-ttu-id="7aa51-118">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Problemtyp.</span><span class="sxs-lookup"><span data-stu-id="7aa51-118">In the Problem type field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="7aa51-119">Välj problemet som hittades vid inspektionen.</span><span class="sxs-lookup"><span data-stu-id="7aa51-119">Select the problem that was found during the inspection process.</span></span>  
5. <span data-ttu-id="7aa51-120">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Problemtyp.</span><span class="sxs-lookup"><span data-stu-id="7aa51-120">In the Problem type field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="7aa51-121">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="7aa51-121">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="7aa51-122">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="7aa51-122">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="7aa51-123">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="7aa51-123">Click OK.</span></span>

## <a name="approvereject-a-nonconformance"></a><span data-ttu-id="7aa51-124">Godkänn/avvisa en avvikelse</span><span class="sxs-lookup"><span data-stu-id="7aa51-124">Approve/reject a nonconformance</span></span>
1. <span data-ttu-id="7aa51-125">Klicka på Funktioner.</span><span class="sxs-lookup"><span data-stu-id="7aa51-125">Click Functions.</span></span>
2. <span data-ttu-id="7aa51-126">Klicka på Godkänn avvikelse.</span><span class="sxs-lookup"><span data-stu-id="7aa51-126">Click Approve non conformance.</span></span>
    * <span data-ttu-id="7aa51-127">I detta exempel godkänner du avvikelsen.</span><span class="sxs-lookup"><span data-stu-id="7aa51-127">For this example, approve the nonconformance.</span></span> <span data-ttu-id="7aa51-128">Godkända avvikelser kan associeras med tillhörande åtgärder om du vill registrera arbete som utförs som en del av avvikelsehanteringen och, som i den här uppgiften, bearbetningen av korrigeringshanteringen.</span><span class="sxs-lookup"><span data-stu-id="7aa51-128">Approved nonconformances can be associated with related operations to record work that is done as part of the nonconformance handling and, as in this task recording, the processing of correction handling.</span></span>  
3. <span data-ttu-id="7aa51-129">Klicka på Ja.</span><span class="sxs-lookup"><span data-stu-id="7aa51-129">Click Yes.</span></span>

## <a name="create-a-correction-action"></a><span data-ttu-id="7aa51-130">Skapa en korrigeringsåtgärd</span><span class="sxs-lookup"><span data-stu-id="7aa51-130">Create a correction action</span></span>
1. <span data-ttu-id="7aa51-131">Klicka på Korrigeringar.</span><span class="sxs-lookup"><span data-stu-id="7aa51-131">Click Corrections.</span></span>
2. <span data-ttu-id="7aa51-132">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="7aa51-132">Click New.</span></span>
3. <span data-ttu-id="7aa51-133">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="7aa51-133">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="7aa51-134">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Personalnummer.</span><span class="sxs-lookup"><span data-stu-id="7aa51-134">In the Personnel number field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="7aa51-135">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="7aa51-135">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="7aa51-136">Klicka på Välj.</span><span class="sxs-lookup"><span data-stu-id="7aa51-136">Click Select.</span></span>
7. <span data-ttu-id="7aa51-137">Klicka på Koppla.</span><span class="sxs-lookup"><span data-stu-id="7aa51-137">Click Attach.</span></span>
    * <span data-ttu-id="7aa51-138">Skapa en notering om korrigeringen.</span><span class="sxs-lookup"><span data-stu-id="7aa51-138">Create a note about the correction.</span></span> <span data-ttu-id="7aa51-139">För det här exemplet är åtgärden att kontakta leverantören för att diskutera avvikelsen.</span><span class="sxs-lookup"><span data-stu-id="7aa51-139">For this example, the action is to contact the vendor to discuss the nonconformance case.</span></span>  
8. <span data-ttu-id="7aa51-140">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="7aa51-140">Click New.</span></span>
9. <span data-ttu-id="7aa51-141">Klicka på Anmärkning.</span><span class="sxs-lookup"><span data-stu-id="7aa51-141">Click Note.</span></span>
    * <span data-ttu-id="7aa51-142">Observera att, beroende på rapportinställningarna, olika dokumenttyper kan skrivas ut på rapporter som är relaterade till avvikelsehanteringen.</span><span class="sxs-lookup"><span data-stu-id="7aa51-142">Note that, depending on the report setup, different document types can be printed on the reports that are related to nonconformance management.</span></span>  
10. <span data-ttu-id="7aa51-143">Ange ett värde i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="7aa51-143">In the Description field, type a value.</span></span>
11. <span data-ttu-id="7aa51-144">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="7aa51-144">Close the page.</span></span>

## <a name="maintain-a-correction"></a><span data-ttu-id="7aa51-145">Underhåll en korrigering</span><span class="sxs-lookup"><span data-stu-id="7aa51-145">Maintain a correction</span></span>
1. <span data-ttu-id="7aa51-146">Klicka på Markera som slutförd.</span><span class="sxs-lookup"><span data-stu-id="7aa51-146">Click Mark complete.</span></span>
2. <span data-ttu-id="7aa51-147">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="7aa51-147">Click OK.</span></span>
3. <span data-ttu-id="7aa51-148">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="7aa51-148">Close the page.</span></span>

## <a name="close-a-nonconformance"></a><span data-ttu-id="7aa51-149">Stäng en avvikelse</span><span class="sxs-lookup"><span data-stu-id="7aa51-149">Close a nonconformance</span></span>
1. <span data-ttu-id="7aa51-150">Klicka på Funktioner.</span><span class="sxs-lookup"><span data-stu-id="7aa51-150">Click Functions.</span></span>
2. <span data-ttu-id="7aa51-151">Klicka på Stäng avvikelsen.</span><span class="sxs-lookup"><span data-stu-id="7aa51-151">Click Close non conformance.</span></span>
3. <span data-ttu-id="7aa51-152">Klicka på Ja.</span><span class="sxs-lookup"><span data-stu-id="7aa51-152">Click Yes.</span></span>
4. <span data-ttu-id="7aa51-153">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="7aa51-153">Close the page.</span></span>
5. <span data-ttu-id="7aa51-154">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="7aa51-154">Close the page.</span></span>

