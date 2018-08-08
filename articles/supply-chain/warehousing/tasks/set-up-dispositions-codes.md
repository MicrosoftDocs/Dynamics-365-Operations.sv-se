--- 
title: "Ställ in dispositionskoder"
description: "I den här proceduren läggs fokus på inställningen av en dispositionskod som kan användas på en mobil enhet för inleveransprocessen för returorder."
author: ShylaThompson
manager: AnnBe
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 1d98cbff30620256c9d13e7b4a90314db150e33e
ms.openlocfilehash: 85402e05d55367da5fe89b242ad8eafc727b441e
ms.contentlocale: sv-se
ms.lasthandoff: 08/07/2018

---
# <a name="set-up-dispositions-codes"></a><span data-ttu-id="91d36-103">Ställ in dispositionskoder</span><span class="sxs-lookup"><span data-stu-id="91d36-103">Set up dispositions codes</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="91d36-104">I den här proceduren läggs fokus på inställningen av en dispositionskod som kan användas på en mobil enhet för inleveransprocessen för returorder.</span><span class="sxs-lookup"><span data-stu-id="91d36-104">This procedure focuses on the setup of a disposition code that can be used on a mobile device for the return order receiving process.</span></span> <span data-ttu-id="91d36-105">Dispositionskoder är en grupp regler som kan användas när artiklar tas emot.</span><span class="sxs-lookup"><span data-stu-id="91d36-105">Disposition codes are a collection of rules that can be used when items are received.</span></span> <span data-ttu-id="91d36-106">När till exempel en arbetare använder en mobil enhet för att ta emot artiklar som är skadade, måste användaren skanna en dispositionskod för skadade artiklar.</span><span class="sxs-lookup"><span data-stu-id="91d36-106">For example, when a work user uses a mobile device to receive items that were damaged, the user must scan a disposition code for damaged items.</span></span> <span data-ttu-id="91d36-107">Lagerstatusen för de mottagna varorna, arbetsmallen och platsdirektivet kan fastställas från den skannade dispositionskoden.</span><span class="sxs-lookup"><span data-stu-id="91d36-107">The inventory status of the goods received, the work template, and the location directive can be determined from the scanned disposition code.</span></span> <span data-ttu-id="91d36-108">För inleveransprocessen för inköpsorder och produktionsorderrapporten som slutförd process är användningen av en dispositionskod valfritt.</span><span class="sxs-lookup"><span data-stu-id="91d36-108">For the purchase order receiving process and the production order report as finished process, the use of a disposition code is optional.</span></span> <span data-ttu-id="91d36-109">För inleveransprocessen för försäljningsorder där artiklarna registreras med hjälp av en mobil enhet, är användning av dispositionskoden obligatorisk.</span><span class="sxs-lookup"><span data-stu-id="91d36-109">For the sales order return receiving process, if the items are registered using a mobile device, the use of disposition code is mandatory.</span></span>  <span data-ttu-id="91d36-110">Guiden har skapats med demodataföretaget USMF.</span><span class="sxs-lookup"><span data-stu-id="91d36-110">This guide was created using the demo data company USMF.</span></span> <span data-ttu-id="91d36-111">Den här proceduren är avsedd för lagerchefen.</span><span class="sxs-lookup"><span data-stu-id="91d36-111">This procedure is intended for the warehouse manager.</span></span> 

1. <span data-ttu-id="91d36-112">Gå till Lagerstyrning > Inställningar > Mobil enhet > Dispositionskoder.</span><span class="sxs-lookup"><span data-stu-id="91d36-112">Go to Warehouse management > Setup > Mobile device > Disposition codes.</span></span>
2. <span data-ttu-id="91d36-113">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="91d36-113">Click New.</span></span>
    * <span data-ttu-id="91d36-114">Skapa en ny dispositionskod som ska användas för kundreturer.</span><span class="sxs-lookup"><span data-stu-id="91d36-114">Create a new disposition code to use for customer returns.</span></span>  
3. <span data-ttu-id="91d36-115">Skriv ett värde i fältet Dispositionskod.</span><span class="sxs-lookup"><span data-stu-id="91d36-115">In the Disposition code field, type a value.</span></span>
4. <span data-ttu-id="91d36-116">Välj en lagerstatus där det finns lagerspärr i fältet Lagerstatus.</span><span class="sxs-lookup"><span data-stu-id="91d36-116">In the Inventory status field, select an inventory status where there is inventory blocking.</span></span>
    * <span data-ttu-id="91d36-117">Välj "Spärr" om du använder USMF.</span><span class="sxs-lookup"><span data-stu-id="91d36-117">If you're using USMF, select 'Blocking'.</span></span> <span data-ttu-id="91d36-118">Du kan lägga till en lagerstatus till dispositionskoden för att åsidosätta standardstatusen på orderraderna.</span><span class="sxs-lookup"><span data-stu-id="91d36-118">You can add an inventory status to the disposition code to override the default status that’s on the order lines.</span></span>  
5. <span data-ttu-id="91d36-119">Skriv ett värde i fältet Arbetsmall.</span><span class="sxs-lookup"><span data-stu-id="91d36-119">In the Work template field, type a value.</span></span>
    * <span data-ttu-id="91d36-120">Valfritt: Välj en arbetsmallkod som associeras med en returorder.</span><span class="sxs-lookup"><span data-stu-id="91d36-120">Optional: Select a work template code that is associated with a return order.</span></span> <span data-ttu-id="91d36-121">Om inget värde anges, anges arbetsmallen med hjälp av de konfigurerade standardreglerna i systemet.</span><span class="sxs-lookup"><span data-stu-id="91d36-121">If no value is provided, the work template will be resolved using the standard rules configured in your system.</span></span> <span data-ttu-id="91d36-122">Om du väljer en arbetsmall begränsas de processer som dispositionskoden kan användas med.</span><span class="sxs-lookup"><span data-stu-id="91d36-122">Selecting a work template will limit the processes this disposition code can be used with.</span></span> <span data-ttu-id="91d36-123">Om en dispositionskod till exempel har en arbetsmall med en arbetsorder av typen inköpsorder, kan den inte användas för att registrera artiklar som returneras av kunder.</span><span class="sxs-lookup"><span data-stu-id="91d36-123">For example, if a disposition code has a work template with a work order of type purchase order, it can’t be used to register items that are returned by customers.</span></span>  
6. <span data-ttu-id="91d36-124">Skriv ett värde i fältet Returdispositionskod.</span><span class="sxs-lookup"><span data-stu-id="91d36-124">In the Return disposition code field, type a value.</span></span>
    * <span data-ttu-id="91d36-125">Returdispositionskoden bestämmer resten av returorderprocessen för de registrerade artiklarna.</span><span class="sxs-lookup"><span data-stu-id="91d36-125">The return disposition code determines the remainder of the return order process for the items registered.</span></span> <span data-ttu-id="91d36-126">I det här exemplet ska kunden få en kreditfaktura.</span><span class="sxs-lookup"><span data-stu-id="91d36-126">In this example, the customer should receive a credit note.</span></span> <span data-ttu-id="91d36-127">Lägg till en returdispositionskod som innehåller en åtgärdskredit.</span><span class="sxs-lookup"><span data-stu-id="91d36-127">Add a returns disposition code that contains an action Credit.</span></span>  


