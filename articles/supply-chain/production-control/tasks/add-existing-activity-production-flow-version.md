--- 
title: "Lägg till en befintlig aktivitet i en produktionsflödesversion"
description: "När du skapar nya versioner av produktionsflöden kan du välja att lägga till aktiviteter som skapats för de äldre versionerna, till den nya versionen."
author: cvocph
manager: AnnBe
ms.date: 8/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: LeanProductionFlow, PlanActivity, PlanActivityAddExisting, PlanActivityAddExistingLookup
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: conradv
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 32d71167fdad65cb1dec37671999a497759ca484
ms.openlocfilehash: cb185c1ec55346af7cfe0b950f0915072242e961
ms.contentlocale: sv-se
ms.lasthandoff: 09/11/2018

---
# <a name="add-an-existing-activity-to-a-production-flow-version"></a><span data-ttu-id="923f3-103">Lägg till en befintlig aktivitet i en produktionsflödesversion</span><span class="sxs-lookup"><span data-stu-id="923f3-103">Add an existing activity to a production flow version</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="923f3-104">När du skapar nya versioner av produktionsflöden kan du välja att lägga till aktiviteter som skapats för de äldre versionerna, till den nya versionen.</span><span class="sxs-lookup"><span data-stu-id="923f3-104">When creating new versions of production flows, you can choose to add activities created for the older versions, to the new version.</span></span> <span data-ttu-id="923f3-105">I den här proceduren visas hur en ny version skapas för ett befintligt produktionsflöde, utan aktiviteterna kopieras.</span><span class="sxs-lookup"><span data-stu-id="923f3-105">This procedure shows how a new version is created for an existing production flow, without copying the activities.</span></span> <span data-ttu-id="923f3-106">I nästa steg läggs en befintlig aktivitet till i den nya versionen.</span><span class="sxs-lookup"><span data-stu-id="923f3-106">In the next step, an existing activity is added to the new version.</span></span> 

<span data-ttu-id="923f3-107">Denna uppgift kräver produktionsflöde med version och aktiviteter som redan har skapats.</span><span class="sxs-lookup"><span data-stu-id="923f3-107">This task requires production flow with version and activities already created.</span></span>


## <a name="create-a-new-production-flow-version"></a><span data-ttu-id="923f3-108">Skapa en ny produktionsflödesversion</span><span class="sxs-lookup"><span data-stu-id="923f3-108">Create a new production flow version</span></span>
1. <span data-ttu-id="923f3-109">Gå till Produktionskontroll > Inställningar > Lean-produktionsflöde > Produktionsflöden.</span><span class="sxs-lookup"><span data-stu-id="923f3-109">Go to Production control > Setup > Lean production flow > Production flows.</span></span>
2. <span data-ttu-id="923f3-110">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="923f3-110">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="923f3-111">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="923f3-111">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="923f3-112">Klicka på Redigera.</span><span class="sxs-lookup"><span data-stu-id="923f3-112">Click Edit.</span></span>
5. <span data-ttu-id="923f3-113">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="923f3-113">In the list, mark the selected row.</span></span>
6. <span data-ttu-id="923f3-114">I fältet Utgångsdatum anger du datum och tid.</span><span class="sxs-lookup"><span data-stu-id="923f3-114">In the Expiration date field, enter a date and time.</span></span>
    * <span data-ttu-id="923f3-115">Observera att du, innan du skapar en ny produktionsflödesversion, måste kontrollera utgångsdatum och tid för den aktiva versionen.</span><span class="sxs-lookup"><span data-stu-id="923f3-115">Note that before you create a new production flow version, make sure to check the expiration date and time of the active version.</span></span> <span data-ttu-id="923f3-116">Den nya versionen skapas med ett effektivt startdatum som kopplas till den valda versionens utgångsdatum.</span><span class="sxs-lookup"><span data-stu-id="923f3-116">The new version will be created with an effective start date, which connects to the expiry date of the selected version.</span></span>  
7. <span data-ttu-id="923f3-117">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="923f3-117">Click Add.</span></span>
8. <span data-ttu-id="923f3-118">Välj No i fältet Copy from version.</span><span class="sxs-lookup"><span data-stu-id="923f3-118">Select No in the Copy from version field.</span></span>
    * <span data-ttu-id="923f3-119">Välj No för att börja med en tom version om de flesta aktiviteter i den kopierade versionen ska ersättas av nya aktiviteter.</span><span class="sxs-lookup"><span data-stu-id="923f3-119">Select No to start with an empty version if most of the activities of the copied version will be replaced by new activities.</span></span> <span data-ttu-id="923f3-120">Lägg till oförändrade aktiviteter i funktionen Add existing function manuellt i aktivitetsformuläret.</span><span class="sxs-lookup"><span data-stu-id="923f3-120">Add the unchanged activities to the Add existing function in the activity form manually.</span></span>  
9. <span data-ttu-id="923f3-121">Välj No i fältet Duplicate kanban rules.</span><span class="sxs-lookup"><span data-stu-id="923f3-121">Select No in the Duplicate kanban rules field.</span></span>
    * <span data-ttu-id="923f3-122">När aktiviteterna inte kopieras till den nya versionen går det inte att kopiera kanban-reglerna när den nya versionen skapas.</span><span class="sxs-lookup"><span data-stu-id="923f3-122">When the activities are not copied to the new version, it is not possible to copy the kanban rules at the time of creation of the new version.</span></span>   <span data-ttu-id="923f3-123">Istället ska du använda funktionen för skapande av kanbanutbyte senare i regelformuläret för kanban, detta för att ersätta kanban-reglerna i den gamla produktionsflödesversionen med kanbanregler, detta med hjälp av aktiviteter i den nya versionen.</span><span class="sxs-lookup"><span data-stu-id="923f3-123">Instead you will use the create replacement kanban function later in the kanban rule form, to replace kanban rules of the old production flow version with kanban rules using the activities of the new version.</span></span>  
10. <span data-ttu-id="923f3-124">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="923f3-124">Click OK.</span></span>
11. <span data-ttu-id="923f3-125">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="923f3-125">In the list, find and select the desired record.</span></span>

## <a name="add-an-existing-activity"></a><span data-ttu-id="923f3-126">Lägg till en befintlig aktivitet</span><span class="sxs-lookup"><span data-stu-id="923f3-126">Add an existing activity</span></span>
1. <span data-ttu-id="923f3-127">Klicka på Aktiviteter.</span><span class="sxs-lookup"><span data-stu-id="923f3-127">Click Activities.</span></span>
2. <span data-ttu-id="923f3-128">Klicka på Add existing för att öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="923f3-128">Click Add existing to open the drop dialog.</span></span>
    * <span data-ttu-id="923f3-129">Välj en befintlig aktivitet som ska läggas till i den nya produktionsflödesversionen.</span><span class="sxs-lookup"><span data-stu-id="923f3-129">Find and select an existing activity to be added to the new production flow version.</span></span>  <span data-ttu-id="923f3-130">Observera att listan visas alla aktiviteter som har skapats för detta produktionsflöde för alla tidigare versioner av flödet.</span><span class="sxs-lookup"><span data-stu-id="923f3-130">Note that the list shows all activities that have been created for this production flow for all previous versions of the flow.</span></span>  
3. <span data-ttu-id="923f3-131">Ange eller välj ett värde i fältet Activity.</span><span class="sxs-lookup"><span data-stu-id="923f3-131">In the Activity field, enter or select a value.</span></span>
4. <span data-ttu-id="923f3-132">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="923f3-132">Click OK.</span></span>


