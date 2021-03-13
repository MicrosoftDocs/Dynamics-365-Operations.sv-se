---
title: Skapa en kanban-regel för uttag
description: I den här proceduren visas de inställningar som behövs om du vill skapa en kanban-regel för uttag för överföring av material i en resurssnål miljö.
author: ChristianRytt
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KanbanRules, LeanProductionFlowActivityLookup, InventItemIdLookupSimple, UnitOfMeasureLookup, KanbanCreate
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 1694472e20c28a0b0f94c1ced8544b7258c22b40
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "5007101"
---
# <a name="create-a-withdrawal-kanban-rule"></a><span data-ttu-id="eea09-103">Skapa en kanban-regel för uttag</span><span class="sxs-lookup"><span data-stu-id="eea09-103">Create a withdrawal kanban rule</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="eea09-104">I den här proceduren visas de inställningar som behövs om du vill skapa en kanban-regel för uttag för överföring av material i en resurssnål miljö.</span><span class="sxs-lookup"><span data-stu-id="eea09-104">This procedure shows the setup that is needed to create a withdrawal kanban rule for transferring material in a lean environment.</span></span> <span data-ttu-id="eea09-105">Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF.</span><span class="sxs-lookup"><span data-stu-id="eea09-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="eea09-106">Den här proceduren är avsedd för processingenjören eller värdeströmansvarig när de förbereder lagerpåfyllnaden av ett nytt eller ändrat material.</span><span class="sxs-lookup"><span data-stu-id="eea09-106">This procedure is intended for the Process Engineer or the Value Stream Manager, as they prepare replenishment of new or modified material.</span></span>


## <a name="create-new-kanban-rule"></a><span data-ttu-id="eea09-107">Skapa en ny kanban-regel</span><span class="sxs-lookup"><span data-stu-id="eea09-107">Create new kanban rule</span></span>
1. <span data-ttu-id="eea09-108">Gå till Kanban-regler.</span><span class="sxs-lookup"><span data-stu-id="eea09-108">Go to Kanban rules.</span></span>
2. <span data-ttu-id="eea09-109">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="eea09-109">Click New.</span></span>
3. <span data-ttu-id="eea09-110">Välj "Uttag" i fältet Typ.</span><span class="sxs-lookup"><span data-stu-id="eea09-110">In the Type field, select 'Withdrawal'.</span></span>
    * <span data-ttu-id="eea09-111">Uttagstypen används för kanban-regler för att överföra material och gods.</span><span class="sxs-lookup"><span data-stu-id="eea09-111">The Withdrawal type is used for kanban rules to transfer material or goods.</span></span>  
4. <span data-ttu-id="eea09-112">Ange eller välj ett värde i fältet Första planaktivitet.</span><span class="sxs-lookup"><span data-stu-id="eea09-112">In the First plan activity field, enter or select a value.</span></span>
    * <span data-ttu-id="eea09-113">Välj ReplenishSpeakerComponents.</span><span class="sxs-lookup"><span data-stu-id="eea09-113">Select ReplenishSpeakerComponents.</span></span>   <span data-ttu-id="eea09-114">Denna aktivitet ställs in för att flytta komponenter från lagerställe 11, plats 11 till lagerställe 12 och plats 12.</span><span class="sxs-lookup"><span data-stu-id="eea09-114">This activity is set up to move components from warehouse 11, location 11 to warehouse 12, and location 12.</span></span>  
5. <span data-ttu-id="eea09-115">Ange eller välj ett värde i fältet Produkt.</span><span class="sxs-lookup"><span data-stu-id="eea09-115">In the Product field, enter or select a value.</span></span>
    * <span data-ttu-id="eea09-116">Välj M0007.</span><span class="sxs-lookup"><span data-stu-id="eea09-116">Select M0007.</span></span>  
6. <span data-ttu-id="eea09-117">Ange ett värde i fältet Produktionstid.</span><span class="sxs-lookup"><span data-stu-id="eea09-117">In the Lead time field, enter a number.</span></span>
    * <span data-ttu-id="eea09-118">Exempelvis 60.</span><span class="sxs-lookup"><span data-stu-id="eea09-118">For example, 60.</span></span>  
7. <span data-ttu-id="eea09-119">Ange eller välj ett värde i fältet Måttenhet.</span><span class="sxs-lookup"><span data-stu-id="eea09-119">In the Unit of measure field, enter or select a value.</span></span>
    * <span data-ttu-id="eea09-120">T.ex. minuter.</span><span class="sxs-lookup"><span data-stu-id="eea09-120">For example, Minutes.</span></span>  

## <a name="set-quantities-for-kanban"></a><span data-ttu-id="eea09-121">Ange kvantiteter för kanban</span><span class="sxs-lookup"><span data-stu-id="eea09-121">Set quantities for kanban</span></span>
1. <span data-ttu-id="eea09-122">Ange standardkvantiteten till "5".</span><span class="sxs-lookup"><span data-stu-id="eea09-122">Set Default quantity to '5'.</span></span>
    * <span data-ttu-id="eea09-123">Detta är kvantiteten som ska överföras för varje kanban.</span><span class="sxs-lookup"><span data-stu-id="eea09-123">This is the quantity that will be transferred for each kanban.</span></span>  
2. <span data-ttu-id="eea09-124">Ange "2" i fältet Fast kanban-kvantitet.</span><span class="sxs-lookup"><span data-stu-id="eea09-124">In the Fixed kanban quantity field, enter '2'.</span></span>
    * <span data-ttu-id="eea09-125">Detta är antalet kanban som ska vara aktiva.</span><span class="sxs-lookup"><span data-stu-id="eea09-125">This is the amount of kanbans that should be active.</span></span> <span data-ttu-id="eea09-126">I det här fallet överför 2 kanbans 5 var.</span><span class="sxs-lookup"><span data-stu-id="eea09-126">In this case, 2 kanbans transferring 5 each.</span></span>  
3. <span data-ttu-id="eea09-127">Ange "1" i fältet Notifieringsgränsminimum.</span><span class="sxs-lookup"><span data-stu-id="eea09-127">In the Alert boundary minimum field, enter '1'.</span></span>
    * <span data-ttu-id="eea09-128">Används för att hålla reda på den minsta mängd fullständiga kanbans som ska finnas på destinationen.</span><span class="sxs-lookup"><span data-stu-id="eea09-128">Used to keep track of the minimum amount of full kanbans that should be at the destination.</span></span> <span data-ttu-id="eea09-129">Detta används till exempel i översikten över kanban-kvantitet.</span><span class="sxs-lookup"><span data-stu-id="eea09-129">For example, this is used on the kanban quantity overview.</span></span>  
4. <span data-ttu-id="eea09-130">Ange "2" i fältet Notifieringsgränsmaximum.</span><span class="sxs-lookup"><span data-stu-id="eea09-130">In the Alert boundary maximum field, enter '2'.</span></span>
    * <span data-ttu-id="eea09-131">Används för att hålla reda på den största mängd fullständiga kanbans som ska finnas på destinationen.</span><span class="sxs-lookup"><span data-stu-id="eea09-131">Used to keep track of the maximum amount of full kanbans that should be at the destination.</span></span> <span data-ttu-id="eea09-132">Detta används till exempel i översikten över kanban-kvantitet.</span><span class="sxs-lookup"><span data-stu-id="eea09-132">For example, this is used on the kanban quantity overview.</span></span>  

## <a name="create-kanbans"></a><span data-ttu-id="eea09-133">Skapa kanban</span><span class="sxs-lookup"><span data-stu-id="eea09-133">Create kanbans</span></span>
1. <span data-ttu-id="eea09-134">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="eea09-134">Click Save.</span></span>
    * <span data-ttu-id="eea09-135">Kanban-regeln måste sparas innan kanbans kan skapas.</span><span class="sxs-lookup"><span data-stu-id="eea09-135">The kanban rule needs to be saved before kanbans can be created.</span></span>  
2. <span data-ttu-id="eea09-136">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="eea09-136">Click Add.</span></span>
    * <span data-ttu-id="eea09-137">Observera att det inte finns några aktiva kanbans. Därför är det föreslagna antalet nya kanbans 2. Detta är lika med ”den fasta kanban-kvantiteten”.</span><span class="sxs-lookup"><span data-stu-id="eea09-137">Note that there are no active kanbans because the suggested 'Number of new kanbans' is 2, which is equal to the 'Fixed kanban quantity'.</span></span>  
3. <span data-ttu-id="eea09-138">Klicka på Skapa.</span><span class="sxs-lookup"><span data-stu-id="eea09-138">Click Create.</span></span>
    * <span data-ttu-id="eea09-139">Detta skapar 2 kanbans.</span><span class="sxs-lookup"><span data-stu-id="eea09-139">This will create two kanbans.</span></span>  
    * <span data-ttu-id="eea09-140">Observera att 2 kanbans, för 5 vardera, skapades för den här kanban-regeln för uttag.</span><span class="sxs-lookup"><span data-stu-id="eea09-140">Note that 2 kanbans, for 5 each, was created for this withdrawal kanban rule.</span></span>  <span data-ttu-id="eea09-141">Detta är det sista steget i den här proceduren.</span><span class="sxs-lookup"><span data-stu-id="eea09-141">This is the last step in this procedure.</span></span>  

