--- 
title: "Konfigurera delning ekonomiska data mellan företag"
description: "I den här proceduren visas hur du konfigurerar, aktiverar, validerar och löser konflikter när data delas mellan företag."
author: aprilolson
manager: AnnBe
ms.date: 06/22/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: margoc
ms.search.scope: Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: 779722bd3acd10a85b089a4d30757b62293ea4e4
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---
# <a name="configure-financial-cross-company-data-sharing"></a><span data-ttu-id="d2463-103">Konfigurera delning ekonomiska data mellan företag</span><span class="sxs-lookup"><span data-stu-id="d2463-103">Configure financial cross-company data sharing</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="d2463-104">I den här proceduren visas hur du konfigurerar, aktiverar, validerar och löser konflikter när data delas mellan företag.</span><span class="sxs-lookup"><span data-stu-id="d2463-104">This procedure shows how to configure, enable, validate, and resolve conflicts when sharing data between companies.</span></span> <span data-ttu-id="d2463-105">Den använder USMF-företaget och finansiella datas delningsmall.</span><span class="sxs-lookup"><span data-stu-id="d2463-105">It uses the USMF company and the Financial data sharing template.</span></span>



<span data-ttu-id="d2463-106">Den här uppgiftsguiden kräver Dynamics AX plattform 7.1 eller senare.</span><span class="sxs-lookup"><span data-stu-id="d2463-106">This task guide requires Dynamics AX platform 7.1 or later.</span></span>

1. <span data-ttu-id="d2463-107">Gå till Systemadministration > Arbetsytor > Datahantering.</span><span class="sxs-lookup"><span data-stu-id="d2463-107">Go to System administration > Workspaces > Data management.</span></span>
2. <span data-ttu-id="d2463-108">Klicka på Importera.</span><span class="sxs-lookup"><span data-stu-id="d2463-108">Click Import.</span></span>
3. <span data-ttu-id="d2463-109">Skriv ett värde i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="d2463-109">In the Name field, type a value.</span></span>
4. <span data-ttu-id="d2463-110">Välj pakettypen i i fältet Källadataformat.</span><span class="sxs-lookup"><span data-stu-id="d2463-110">In the Source data format field, select the Package type.</span></span>
    * <span data-ttu-id="d2463-111">Klicka på Skicka.</span><span class="sxs-lookup"><span data-stu-id="d2463-111">Click Upload.</span></span> <span data-ttu-id="d2463-112">Navigera till platsen för paketfilen för finansiella datas delningsmall och välj den filen.</span><span class="sxs-lookup"><span data-stu-id="d2463-112">Navigate to the location of the Financial data sharing template package file and select that file.</span></span>  
5. <span data-ttu-id="d2463-113">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="d2463-113">Click Save.</span></span>
6. <span data-ttu-id="d2463-114">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="d2463-114">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="d2463-115">Välj datadelningpolicyn som just har skapats.</span><span class="sxs-lookup"><span data-stu-id="d2463-115">Select the data sharing policy that was just created.</span></span>  
7. <span data-ttu-id="d2463-116">Klicka på Importera.</span><span class="sxs-lookup"><span data-stu-id="d2463-116">Click Import.</span></span>
8. <span data-ttu-id="d2463-117">Klicka på Stäng.</span><span class="sxs-lookup"><span data-stu-id="d2463-117">Click Close.</span></span>
9. <span data-ttu-id="d2463-118">Uppdatera sidan.</span><span class="sxs-lookup"><span data-stu-id="d2463-118">Refresh the page.</span></span>
10. <span data-ttu-id="d2463-119">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="d2463-119">Close the page.</span></span>
11. <span data-ttu-id="d2463-120">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="d2463-120">Close the page.</span></span>
12. <span data-ttu-id="d2463-121">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="d2463-121">Close the page.</span></span>
13. <span data-ttu-id="d2463-122">Gå till systemadministration > Inställningar > Konfigurera datadelning mellan företag.</span><span class="sxs-lookup"><span data-stu-id="d2463-122">Go to System administration > Setup > Configure cross-company data sharing.</span></span>
14. <span data-ttu-id="d2463-123">Hitta och välj Betalningsdagar i listan.</span><span class="sxs-lookup"><span data-stu-id="d2463-123">In the list, find and select Payment days.</span></span>
15. <span data-ttu-id="d2463-124">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="d2463-124">Click Add.</span></span>
16. <span data-ttu-id="d2463-125">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="d2463-125">In the list, mark the selected row.</span></span>
17. <span data-ttu-id="d2463-126">Ange "USSI" i fältet Företag.</span><span class="sxs-lookup"><span data-stu-id="d2463-126">In the Company field, type 'USSI'.</span></span>
18. <span data-ttu-id="d2463-127">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="d2463-127">Click Add.</span></span>
19. <span data-ttu-id="d2463-128">Ange "USMF" i fältet Företag.</span><span class="sxs-lookup"><span data-stu-id="d2463-128">In the Company field, type 'USMF'.</span></span>
20. <span data-ttu-id="d2463-129">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="d2463-129">Click Save.</span></span>
21. <span data-ttu-id="d2463-130">Klicka på Aktivera.</span><span class="sxs-lookup"><span data-stu-id="d2463-130">Click Enable.</span></span>
22. <span data-ttu-id="d2463-131">Klicka på Ja.</span><span class="sxs-lookup"><span data-stu-id="d2463-131">Click Yes.</span></span>
23. <span data-ttu-id="d2463-132">Klicka på Hitta delningsproblem.</span><span class="sxs-lookup"><span data-stu-id="d2463-132">Click Find sharing issues.</span></span>
24. <span data-ttu-id="d2463-133">Klicka på Ja.</span><span class="sxs-lookup"><span data-stu-id="d2463-133">Click Yes.</span></span>
25. <span data-ttu-id="d2463-134">Klicka på Uppdatera fältvärde.</span><span class="sxs-lookup"><span data-stu-id="d2463-134">Click Update field value.</span></span>
26. <span data-ttu-id="d2463-135">Klicka på Använd värde från Företag 1.</span><span class="sxs-lookup"><span data-stu-id="d2463-135">Click Use value from company 1.</span></span>
27. <span data-ttu-id="d2463-136">Uppdatera sidan.</span><span class="sxs-lookup"><span data-stu-id="d2463-136">Refresh the page.</span></span>
28. <span data-ttu-id="d2463-137">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="d2463-137">Close the page.</span></span>

