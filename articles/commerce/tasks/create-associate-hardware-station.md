---
title: " Skapa och associera en maskinvarustation"
description: Den här proceduren visar hur du skapar en ny maskinvarustation.
author: jashanno
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: RetailHardwareStation, RetailStoreTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: jashanno
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 305308b0e4ba99aae4bf6f8f94041db570a25893
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "4415888"
---
# <a name="create-and-associate-a-hardware-station"></a><span data-ttu-id="27827-103"> Skapa och associera en maskinvarustation</span><span class="sxs-lookup"><span data-stu-id="27827-103">Create and associate a hardware station</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="27827-104">Den här proceduren visar hur du skapar en ny maskinvarustation.</span><span class="sxs-lookup"><span data-stu-id="27827-104">This procedure walks through how to create a new hardware station.</span></span> <span data-ttu-id="27827-105">En ny maskinvaruprofil skapas och läggs till för alla nya maskinvarustationer till en fördefinierad butik (kanal).</span><span class="sxs-lookup"><span data-stu-id="27827-105">A new hardware profile will be created and used to add new hardware stations to a pre-defined store (channel).</span></span> <span data-ttu-id="27827-106">I proceduren används demonstrationsföretaget USRT.</span><span class="sxs-lookup"><span data-stu-id="27827-106">This procedure uses the USRT company in demo data.</span></span>

1. <span data-ttu-id="27827-107">Gå till grundläggande om handel > kanaler >..</span><span class="sxs-lookup"><span data-stu-id="27827-107">Go to Commerce essentials > Channels > ..</span></span> <span data-ttu-id="27827-108">> </span><span class="sxs-lookup"><span data-stu-id="27827-108">> ..</span></span> <span data-ttu-id="27827-109">> </span><span class="sxs-lookup"><span data-stu-id="27827-109">> ..</span></span> <span data-ttu-id="27827-110">> Maskinvarustationens profiler.</span><span class="sxs-lookup"><span data-stu-id="27827-110">> Hardware station profiles.</span></span>
2. <span data-ttu-id="27827-111">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="27827-111">Click New.</span></span>
3. <span data-ttu-id="27827-112">Skriv TestHWProfile i fältet ID för maskinvarustation.</span><span class="sxs-lookup"><span data-stu-id="27827-112">In the Hardware station ID field, type 'TestHWProfile'.</span></span>
4. <span data-ttu-id="27827-113">Skriv ett värde i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="27827-113">In the Name field, type a value.</span></span>
5. <span data-ttu-id="27827-114">Ange ett nummer i fältet Portnummer.</span><span class="sxs-lookup"><span data-stu-id="27827-114">In the Port number field, enter a number.</span></span>
6. <span data-ttu-id="27827-115">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Maskinvaruprofil.</span><span class="sxs-lookup"><span data-stu-id="27827-115">In the Hardware profile field, click the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="27827-116">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="27827-116">In the list, find and select the desired record.</span></span>
8. <span data-ttu-id="27827-117">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="27827-117">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="27827-118">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Paketnamn.</span><span class="sxs-lookup"><span data-stu-id="27827-118">In the Package name field, click the drop-down button to open the lookup.</span></span>
10. <span data-ttu-id="27827-119">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="27827-119">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="27827-120">Detta är standardpaketet som kommer med en ny miljö.</span><span class="sxs-lookup"><span data-stu-id="27827-120">This is the standard package that comes with a new environment.</span></span> <span data-ttu-id="27827-121">Versionsnumret kan variera.</span><span class="sxs-lookup"><span data-stu-id="27827-121">The version number may vary.</span></span>  
11. <span data-ttu-id="27827-122">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="27827-122">Click Save.</span></span>
12. <span data-ttu-id="27827-123">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="27827-123">Close the page.</span></span>
13. <span data-ttu-id="27827-124">Gå till Butik och handel > Kanaler > Alla butiker.</span><span class="sxs-lookup"><span data-stu-id="27827-124">Go to Retail and Commerce > Channels > All stores.</span></span>
14. <span data-ttu-id="27827-125">Välj rad 17 i listan.</span><span class="sxs-lookup"><span data-stu-id="27827-125">In the list, select row 17.</span></span>
    * <span data-ttu-id="27827-126">Om du använder demodataföretaget USRT är det Houston-butiken.</span><span class="sxs-lookup"><span data-stu-id="27827-126">If you are using the USRT demo data company, this is the Houston store.</span></span>  
15. <span data-ttu-id="27827-127">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="27827-127">In the list, click the link in the selected row.</span></span>
16. <span data-ttu-id="27827-128">Växla utökningen av avsnittet Maskinvarustationer.</span><span class="sxs-lookup"><span data-stu-id="27827-128">Toggle the expansion of the Hardware stations section.</span></span>
17. <span data-ttu-id="27827-129">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="27827-129">Click Add.</span></span>
18. <span data-ttu-id="27827-130">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="27827-130">In the list, mark the selected row.</span></span>
19. <span data-ttu-id="27827-131">I fältet Profil-ID öppnar du sökningen genom att klicka på den nedrullningsbara knappen.</span><span class="sxs-lookup"><span data-stu-id="27827-131">In the Profile ID field, click the drop-down button to open the lookup.</span></span>
20. <span data-ttu-id="27827-132">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="27827-132">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="27827-133">Detta måste vara den nya maskinvarustationsprofilen som har skapats i föregående steg.</span><span class="sxs-lookup"><span data-stu-id="27827-133">This must be the new hardware station profile that was created in the previous steps.</span></span>  
21. <span data-ttu-id="27827-134">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="27827-134">In the list, click the link in the selected row.</span></span>
22. <span data-ttu-id="27827-135">I fältet Värdnamn, skriv ett värde.</span><span class="sxs-lookup"><span data-stu-id="27827-135">In the Host name field, type a value.</span></span>
23. <span data-ttu-id="27827-136">Skriv ett värde i fältet EFT-terminal-ID.</span><span class="sxs-lookup"><span data-stu-id="27827-136">In the EFT terminal ID field, type a value.</span></span>
24. <span data-ttu-id="27827-137">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="27827-137">Click Save.</span></span>

