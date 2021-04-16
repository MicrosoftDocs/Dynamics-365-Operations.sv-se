---
title: Skapa och bearbeta en överensstämmelse
description: Det här avsnittet förklarar hur du utför avvikelsehantering baserat på en befintlig kvalitetsorder.
author: perlynne
ms.date: 08/07/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c4f7e61adf37e74bdb082270b689cf0375ccc7f7
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5833963"
---
# <a name="create-and-process-a-conformance"></a><span data-ttu-id="13a3f-103">Skapa och bearbeta en överensstämmelse</span><span class="sxs-lookup"><span data-stu-id="13a3f-103">Create and process a conformance</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="13a3f-104">Det här avsnittet förklarar hur du utför avvikelsehantering baserat på en befintlig kvalitetsorder.</span><span class="sxs-lookup"><span data-stu-id="13a3f-104">This topic explains how to perform nonconformance management, based on an existing quality order.</span></span> <span data-ttu-id="13a3f-105">Du kan köra denna registrering i USMF-demonstrationsföretaget och kan använda det föreslagna värdet.</span><span class="sxs-lookup"><span data-stu-id="13a3f-105">You can run this recording in the USMF demo company and can use the suggested values.</span></span> <span data-ttu-id="13a3f-106">Vanligtvis utförs den här proceduren av en kontorist.</span><span class="sxs-lookup"><span data-stu-id="13a3f-106">Typically, this procedure is performed by a quality clerk.</span></span>  <span data-ttu-id="13a3f-107">Slutför först instruktionerna i [Kontrollera kvaliteten på varor](https://github.com/MicrosoftDocs/Dynamics-365-Operations/blob/master/articles/supply-chain/inventory/tasks/inspect-quality-goods.md).</span><span class="sxs-lookup"><span data-stu-id="13a3f-107">As a prerequisite, complete the instructions in [Inspect the quality of goods](https://github.com/MicrosoftDocs/Dynamics-365-Operations/blob/master/articles/supply-chain/inventory/tasks/inspect-quality-goods.md).</span></span> <span data-ttu-id="13a3f-108">För att bearbeta godkännandet av en avvikelse måste användaren som utför uppgiftsregistreringen ha ett "namn"-värde tilldelat på användarsidan.</span><span class="sxs-lookup"><span data-stu-id="13a3f-108">To process the approval of a nonconformance, the user who runs the task recording must have a "Name" value assigned on the Users page.</span></span> <span data-ttu-id="13a3f-109">För att använda dokumentanteckningar måste användaren även ha Dokumenthantering aktiverat i användaralternativen.</span><span class="sxs-lookup"><span data-stu-id="13a3f-109">To use the document notes, the user must also have Document handling activated in the user options.</span></span>


## <a name="select-a-quality-order"></a><span data-ttu-id="13a3f-110">Välj en kvalitetsorder.</span><span class="sxs-lookup"><span data-stu-id="13a3f-110">Select a quality order</span></span>
1. <span data-ttu-id="13a3f-111">I navigeringsfönstret gå till **Moduler > Lagerhantering > Periodiska uppgifter > Kvalitetshantering > Kvalitetsorder**.</span><span class="sxs-lookup"><span data-stu-id="13a3f-111">In the navigation pane, go to **Modules > Inventory management > Periodic tasks > Quality management > Quality orders**.</span></span>
2. <span data-ttu-id="13a3f-112">I listan, välj kvalitetsordern som skapades i [Kontroller kvaliteten på varor](https://github.com/MicrosoftDocs/Dynamics-365-Operations/blob/master/articles/supply-chain/inventory/tasks/inspect-quality-goods.md).</span><span class="sxs-lookup"><span data-stu-id="13a3f-112">In the list, select the quality order that was created in [Inspect the quality of goods](https://github.com/MicrosoftDocs/Dynamics-365-Operations/blob/master/articles/supply-chain/inventory/tasks/inspect-quality-goods.md).</span></span>  

## <a name="create-a-nonconformance"></a><span data-ttu-id="13a3f-113">Skapa en avvikelse</span><span class="sxs-lookup"><span data-stu-id="13a3f-113">Create a nonconformance</span></span>
1. <span data-ttu-id="13a3f-114">Välj **Förfrågningar** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="13a3f-114">On the Action Pane, select **Inquiries**.</span></span>
2. <span data-ttu-id="13a3f-115">Välj **Avvikelser**.</span><span class="sxs-lookup"><span data-stu-id="13a3f-115">Select **Non conformances**.</span></span>
3. <span data-ttu-id="13a3f-116">Välj **Ny**.</span><span class="sxs-lookup"><span data-stu-id="13a3f-116">Select **New**.</span></span>
4. <span data-ttu-id="13a3f-117">Välj det problem som hittades under inspektionsprocessen på den nedrullningsbara menyn i fältet **Problemtyp**.</span><span class="sxs-lookup"><span data-stu-id="13a3f-117">In the drop-down menu of the **Problem type** field, select the problem that was found during the inspection process.</span></span>  
5. <span data-ttu-id="13a3f-118">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="13a3f-118">Select **OK**.</span></span>

## <a name="approvereject-a-nonconformance"></a><span data-ttu-id="13a3f-119">Godkänn/avvisa en avvikelse</span><span class="sxs-lookup"><span data-stu-id="13a3f-119">Approve/reject a nonconformance</span></span>
1. <span data-ttu-id="13a3f-120">Välj **Funktioner**.</span><span class="sxs-lookup"><span data-stu-id="13a3f-120">Select **Functions**.</span></span>
2. <span data-ttu-id="13a3f-121">Välj **Godkänn avvikelsen**.</span><span class="sxs-lookup"><span data-stu-id="13a3f-121">Select **Approve non conformance**.</span></span> <span data-ttu-id="13a3f-122">I detta exempel godkänner du avvikelsen.</span><span class="sxs-lookup"><span data-stu-id="13a3f-122">For this example, approve the nonconformance.</span></span> <span data-ttu-id="13a3f-123">Godkända avvikelser kan associeras med tillhörande åtgärder om du vill registrera arbete som utförs som en del av avvikelsehanteringen och, som i det här avsnittet, bearbetningen av korrigeringshanteringen.</span><span class="sxs-lookup"><span data-stu-id="13a3f-123">Approved nonconformances can be associated with related operations to record work that is done as part of the nonconformance handling and, as in this topic, the processing of correction handling.</span></span>  
3. <span data-ttu-id="13a3f-124">Välj **Ja**.</span><span class="sxs-lookup"><span data-stu-id="13a3f-124">Select **Yes**.</span></span>

## <a name="create-a-correction-action"></a><span data-ttu-id="13a3f-125">Skapa en korrigeringsåtgärd</span><span class="sxs-lookup"><span data-stu-id="13a3f-125">Create a correction action</span></span>
1. <span data-ttu-id="13a3f-126">Välj **Korrigeringar**.</span><span class="sxs-lookup"><span data-stu-id="13a3f-126">Select **Corrections**.</span></span>
2. <span data-ttu-id="13a3f-127">Välj **Ny**.</span><span class="sxs-lookup"><span data-stu-id="13a3f-127">Select **New**.</span></span>
3. <span data-ttu-id="13a3f-128">I fältet **Personalnummer** för den nya raden väljer du den önskade posten från den nedrullningsbara menyn.</span><span class="sxs-lookup"><span data-stu-id="13a3f-128">In the **Personnel number** field of the new row, select the desired record from the drop down menu.</span></span>
4. <span data-ttu-id="13a3f-129">Klicka på **Välj**.</span><span class="sxs-lookup"><span data-stu-id="13a3f-129">Click **Select**.</span></span>
5. <span data-ttu-id="13a3f-130">Välj **Bifoga**.</span><span class="sxs-lookup"><span data-stu-id="13a3f-130">Select **Attach**.</span></span> <span data-ttu-id="13a3f-131">Skapa en notering om korrigeringen.</span><span class="sxs-lookup"><span data-stu-id="13a3f-131">Create a note about the correction.</span></span> <span data-ttu-id="13a3f-132">För det här exemplet är åtgärden att kontakta leverantören för att diskutera avvikelsen.</span><span class="sxs-lookup"><span data-stu-id="13a3f-132">For this example, the action is to contact the vendor to discuss the nonconformance case.</span></span>  
6. <span data-ttu-id="13a3f-133">Välj **Ny**.</span><span class="sxs-lookup"><span data-stu-id="13a3f-133">Select **New**.</span></span>
7. <span data-ttu-id="13a3f-134">Välj **Notering**.</span><span class="sxs-lookup"><span data-stu-id="13a3f-134">Select **Note**.</span></span> <span data-ttu-id="13a3f-135">Beroende på rapportinställningarna, olika dokumenttyper kan skrivas ut på rapporter som är relaterade till avvikelsehanteringen.</span><span class="sxs-lookup"><span data-stu-id="13a3f-135">Depending on the report setup, different document types can be printed on the reports that are related to nonconformance management.</span></span>  
8. <span data-ttu-id="13a3f-136">I fältet **Beskrivning** anger du ett värde.</span><span class="sxs-lookup"><span data-stu-id="13a3f-136">In the **Description** field, type a value.</span></span>
9. <span data-ttu-id="13a3f-137">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="13a3f-137">Close the page.</span></span>

## <a name="maintain-a-correction"></a><span data-ttu-id="13a3f-138">Underhåll en korrigering</span><span class="sxs-lookup"><span data-stu-id="13a3f-138">Maintain a correction</span></span>
1. <span data-ttu-id="13a3f-139">Välj **Markera som slutförd**.</span><span class="sxs-lookup"><span data-stu-id="13a3f-139">Select **Mark complete**.</span></span>
2. <span data-ttu-id="13a3f-140">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="13a3f-140">Select **OK**.</span></span>
3. <span data-ttu-id="13a3f-141">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="13a3f-141">Close the page.</span></span>

## <a name="close-a-nonconformance"></a><span data-ttu-id="13a3f-142">Stäng en avvikelse</span><span class="sxs-lookup"><span data-stu-id="13a3f-142">Close a nonconformance</span></span>
1. <span data-ttu-id="13a3f-143">Välj **Funktioner**.</span><span class="sxs-lookup"><span data-stu-id="13a3f-143">Select **Functions**.</span></span>
2. <span data-ttu-id="13a3f-144">Välj **Stäng avvikelsen**.</span><span class="sxs-lookup"><span data-stu-id="13a3f-144">Select **Close non conformance**.</span></span>
3. <span data-ttu-id="13a3f-145">Välj **Ja**.</span><span class="sxs-lookup"><span data-stu-id="13a3f-145">Select **Yes**.</span></span>
4. <span data-ttu-id="13a3f-146">Stäng sidorna.</span><span class="sxs-lookup"><span data-stu-id="13a3f-146">Close the pages.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]