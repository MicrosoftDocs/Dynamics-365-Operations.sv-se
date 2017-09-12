--- 
title: " Skapa och associera en maskinvarustation"
description: "Den här proceduren visar hur du skapar en ny maskinvarustation."
author: jashanno
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: jashanno
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 2705008908699bda9479eb54a4827c71f402b603
ms.contentlocale: sv-se
ms.lasthandoff: 08/29/2017

---
# <a name="create-and-associate-a-hardware-station"></a><span data-ttu-id="737d6-103"> Skapa och associera en maskinvarustation</span><span class="sxs-lookup"><span data-stu-id="737d6-103">Create and associate a hardware station</span></span>

[!include[task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="737d6-104">Den här proceduren visar hur du skapar en ny maskinvarustation.</span><span class="sxs-lookup"><span data-stu-id="737d6-104">This procedure walks through how to create a new hardware station.</span></span> <span data-ttu-id="737d6-105">En ny maskinvaruprofil skapas och läggs till för alla nya maskinvarustationer till en fördefinierad butik (kanal).</span><span class="sxs-lookup"><span data-stu-id="737d6-105">A new hardware profile will be created and used to add new hardware stations to a pre-defined store (channel).</span></span> <span data-ttu-id="737d6-106">I proceduren används demonstrationsföretaget USRT.</span><span class="sxs-lookup"><span data-stu-id="737d6-106">This procedure uses the USRT company in demo data.</span></span>

1. <span data-ttu-id="737d6-107">Gå till grundläggande om handel > kanaler >..</span><span class="sxs-lookup"><span data-stu-id="737d6-107">Go to Commerce essentials > Channels > ..</span></span> <span data-ttu-id="737d6-108">> </span><span class="sxs-lookup"><span data-stu-id="737d6-108">> ..</span></span> <span data-ttu-id="737d6-109">> </span><span class="sxs-lookup"><span data-stu-id="737d6-109">> ..</span></span> <span data-ttu-id="737d6-110">> Maskinvarustationens profiler.</span><span class="sxs-lookup"><span data-stu-id="737d6-110">> Hardware station profiles.</span></span>
2. <span data-ttu-id="737d6-111">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="737d6-111">Click New.</span></span>
3. <span data-ttu-id="737d6-112">Skriv TestHWProfile i fältet ID för maskinvarustation.</span><span class="sxs-lookup"><span data-stu-id="737d6-112">In the Hardware station ID field, type 'TestHWProfile'.</span></span>
4. <span data-ttu-id="737d6-113">Skriv ett värde i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="737d6-113">In the Name field, type a value.</span></span>
5. <span data-ttu-id="737d6-114">Ange ett nummer i fältet Portnummer.</span><span class="sxs-lookup"><span data-stu-id="737d6-114">In the Port number field, enter a number.</span></span>
6. <span data-ttu-id="737d6-115">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Maskinvaruprofil.</span><span class="sxs-lookup"><span data-stu-id="737d6-115">In the Hardware profile field, click the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="737d6-116">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="737d6-116">In the list, find and select the desired record.</span></span>
8. <span data-ttu-id="737d6-117">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="737d6-117">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="737d6-118">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Paketnamn.</span><span class="sxs-lookup"><span data-stu-id="737d6-118">In the Package name field, click the drop-down button to open the lookup.</span></span>
10. <span data-ttu-id="737d6-119">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="737d6-119">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="737d6-120">Detta är standardpaketet som kommer med en ny miljö.</span><span class="sxs-lookup"><span data-stu-id="737d6-120">This is the standard package that comes with a new environment.</span></span> <span data-ttu-id="737d6-121">Versionsnumret kan variera.</span><span class="sxs-lookup"><span data-stu-id="737d6-121">The version number may vary.</span></span>  
11. <span data-ttu-id="737d6-122">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="737d6-122">Click Save.</span></span>
12. <span data-ttu-id="737d6-123">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="737d6-123">Close the page.</span></span>
13. <span data-ttu-id="737d6-124">Gå till Butik och handel > Kanaler > Alla butiker.</span><span class="sxs-lookup"><span data-stu-id="737d6-124">Go to Retail and commerce > Channels > All retail stores.</span></span>
14. <span data-ttu-id="737d6-125">Välj rad 17 i listan.</span><span class="sxs-lookup"><span data-stu-id="737d6-125">In the list, select row 17.</span></span>
    * <span data-ttu-id="737d6-126">Om du använder demodataföretaget USRT är det Houston-butiken.</span><span class="sxs-lookup"><span data-stu-id="737d6-126">If you are using the USRT demo data company, this is the Houston store.</span></span>  
15. <span data-ttu-id="737d6-127">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="737d6-127">In the list, click the link in the selected row.</span></span>
16. <span data-ttu-id="737d6-128">Växla utökningen av avsnittet Maskinvarustationer.</span><span class="sxs-lookup"><span data-stu-id="737d6-128">Toggle the expansion of the Hardware stations section.</span></span>
17. <span data-ttu-id="737d6-129">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="737d6-129">Click Add.</span></span>
18. <span data-ttu-id="737d6-130">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="737d6-130">In the list, mark the selected row.</span></span>
19. <span data-ttu-id="737d6-131">I fältet Profil-ID öppnar du sökningen genom att klicka på den nedrullningsbara knappen.</span><span class="sxs-lookup"><span data-stu-id="737d6-131">In the Profile ID field, click the drop-down button to open the lookup.</span></span>
20. <span data-ttu-id="737d6-132">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="737d6-132">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="737d6-133">Detta måste vara den nya maskinvarustationsprofilen som har skapats i föregående steg.</span><span class="sxs-lookup"><span data-stu-id="737d6-133">This must be the new hardware station profile that was created in the previous steps.</span></span>  
21. <span data-ttu-id="737d6-134">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="737d6-134">In the list, click the link in the selected row.</span></span>
22. <span data-ttu-id="737d6-135">I fältet Värdnamn, skriv ett värde.</span><span class="sxs-lookup"><span data-stu-id="737d6-135">In the Host name field, type a value.</span></span>
23. <span data-ttu-id="737d6-136">Skriv ett värde i fältet EFT-terminal-ID.</span><span class="sxs-lookup"><span data-stu-id="737d6-136">In the EFT terminal ID field, type a value.</span></span>
24. <span data-ttu-id="737d6-137">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="737d6-137">Click Save.</span></span>


