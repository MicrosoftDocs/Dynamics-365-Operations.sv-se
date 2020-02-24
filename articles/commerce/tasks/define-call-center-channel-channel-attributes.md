---
title: Skapa kundtjänstkanaler och definiera kanalattribut
description: Den här proceduren beskriver hur du skapar en ny butikskanal och definierar kanalattribut.
author: mugunthanm
manager: AnnBe
ms.date: 05/22/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations, Retail
ms.search.region: Global
ms.author: mumani
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f4b6db1bfdaf17cd857a0a08515f1e0413994bd6
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/01/2020
ms.locfileid: "3024061"
---
# <a name="create-call-center-channels-and-define-channel-attributes"></a><span data-ttu-id="9fe12-103">Skapa kundtjänstkanaler och definiera kanalattribut</span><span class="sxs-lookup"><span data-stu-id="9fe12-103">Create call center channels and define channel attributes</span></span>

[!include [task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="9fe12-104">Den här proceduren beskriver hur du skapar en ny handelskanal och definierar kanalattribut.</span><span class="sxs-lookup"><span data-stu-id="9fe12-104">This procedure walks through creating a new commerce channel and defining channel attributes.</span></span> <span data-ttu-id="9fe12-105">Det demonstrationsdataföretag som används för att skapa den här uppgiften är USRT.</span><span class="sxs-lookup"><span data-stu-id="9fe12-105">The demo data company used to create this task is USRT.</span></span> <span data-ttu-id="9fe12-106">Den här proceduren är avsedd för rollen Handels-IT.</span><span class="sxs-lookup"><span data-stu-id="9fe12-106">This procedure is intended for the Commerce IT role.</span></span>


## <a name="create-new-store"></a><span data-ttu-id="9fe12-107">Skapa ny butik</span><span class="sxs-lookup"><span data-stu-id="9fe12-107">Create new store</span></span>
1. <span data-ttu-id="9fe12-108">Gå till Alla arbetsytor > Kanalgruppering.</span><span class="sxs-lookup"><span data-stu-id="9fe12-108">Go to All workspaces > Channel deployment.</span></span>
2. <span data-ttu-id="9fe12-109">Klicka på Ny kanal.</span><span class="sxs-lookup"><span data-stu-id="9fe12-109">Click New channel.</span></span>
3. <span data-ttu-id="9fe12-110">Klicka på Butik.</span><span class="sxs-lookup"><span data-stu-id="9fe12-110">Click Store.</span></span>
4. <span data-ttu-id="9fe12-111">Skriv ett värde i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="9fe12-111">In the Name field, type a value.</span></span>
5. <span data-ttu-id="9fe12-112">Skriv ett värde i fältet Butiksnummer.</span><span class="sxs-lookup"><span data-stu-id="9fe12-112">In the Store number field, type a value.</span></span>
6. <span data-ttu-id="9fe12-113">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Lagerställe.</span><span class="sxs-lookup"><span data-stu-id="9fe12-113">In the Warehouse field, click the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="9fe12-114">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="9fe12-114">In the list, find and select the desired record.</span></span>
8. <span data-ttu-id="9fe12-115">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="9fe12-115">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="9fe12-116">Markera ett alternativ i fältet Tidszon för butik.</span><span class="sxs-lookup"><span data-stu-id="9fe12-116">In the Store time zone field, select an option.</span></span>
10. <span data-ttu-id="9fe12-117">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Kanalprofil.</span><span class="sxs-lookup"><span data-stu-id="9fe12-117">In the Channel profile field, click the drop-down button to open the lookup.</span></span>
11. <span data-ttu-id="9fe12-118">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="9fe12-118">In the list, click the link in the selected row.</span></span>
12. <span data-ttu-id="9fe12-119">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Språk.</span><span class="sxs-lookup"><span data-stu-id="9fe12-119">In the Language field, click the drop-down button to open the lookup.</span></span>
13. <span data-ttu-id="9fe12-120">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="9fe12-120">In the list, find and select the desired record.</span></span>
14. <span data-ttu-id="9fe12-121">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="9fe12-121">In the list, click the link in the selected row.</span></span>
15. <span data-ttu-id="9fe12-122">I fältet Momsgrupp, öppna sökningen genom att klicka på den nedrullningsbara knappen.</span><span class="sxs-lookup"><span data-stu-id="9fe12-122">In the Sales tax group field, click the drop-down button to open the lookup.</span></span>
16. <span data-ttu-id="9fe12-123">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="9fe12-123">In the list, find and select the desired record.</span></span>
17. <span data-ttu-id="9fe12-124">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="9fe12-124">In the list, click the link in the selected row.</span></span>
18. <span data-ttu-id="9fe12-125">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Kundens adressbok.</span><span class="sxs-lookup"><span data-stu-id="9fe12-125">In the Customer address book field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="9fe12-126">Välj adressboken som ska användas för att koppla kunder till den här butiken.</span><span class="sxs-lookup"><span data-stu-id="9fe12-126">Select the address book used to link customers to this store.</span></span>  
19. <span data-ttu-id="9fe12-127">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="9fe12-127">In the list, find and select the desired record.</span></span>
20. <span data-ttu-id="9fe12-128">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="9fe12-128">In the list, click the link in the selected row.</span></span>
21. <span data-ttu-id="9fe12-129">Klicka på Välj.</span><span class="sxs-lookup"><span data-stu-id="9fe12-129">Click Select.</span></span>
22. <span data-ttu-id="9fe12-130">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Medarbetarens adressbok.</span><span class="sxs-lookup"><span data-stu-id="9fe12-130">In the Employee address book field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="9fe12-131">Välj adressboken som ska användas för att koppla kassörer till den här kanalen.</span><span class="sxs-lookup"><span data-stu-id="9fe12-131">Select the address book used to link cashiers to this channel.</span></span>  
23. <span data-ttu-id="9fe12-132">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="9fe12-132">In the list, find and select the desired record.</span></span>
24. <span data-ttu-id="9fe12-133">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="9fe12-133">In the list, click the link in the selected row.</span></span>
25. <span data-ttu-id="9fe12-134">Klicka på Välj.</span><span class="sxs-lookup"><span data-stu-id="9fe12-134">Click Select.</span></span>
26. <span data-ttu-id="9fe12-135">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Standardkund.</span><span class="sxs-lookup"><span data-stu-id="9fe12-135">In the Default customer field, click the drop-down button to open the lookup.</span></span>
27. <span data-ttu-id="9fe12-136">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="9fe12-136">In the list, click the link in the selected row.</span></span>
28. <span data-ttu-id="9fe12-137">Utöka eller komprimera avsnittet Skärmlayout.</span><span class="sxs-lookup"><span data-stu-id="9fe12-137">Expand or collapse the Screen layout section.</span></span>
29. <span data-ttu-id="9fe12-138">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Skärmlayout-ID.</span><span class="sxs-lookup"><span data-stu-id="9fe12-138">In the Screen layout ID field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="9fe12-139">Välj standardlayout för den här butikens kassaskärm.</span><span class="sxs-lookup"><span data-stu-id="9fe12-139">Select the default POS screen layout for this store.</span></span>  
30. <span data-ttu-id="9fe12-140">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="9fe12-140">In the list, find and select the desired record.</span></span>
31. <span data-ttu-id="9fe12-141">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="9fe12-141">In the list, click the link in the selected row.</span></span>
32. <span data-ttu-id="9fe12-142">Klicka på Ställ in i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="9fe12-142">On the Action Pane, click Set up.</span></span>
33. <span data-ttu-id="9fe12-143">Klicka på Kanalattribut.</span><span class="sxs-lookup"><span data-stu-id="9fe12-143">Click Channel attributes.</span></span>
34. <span data-ttu-id="9fe12-144">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="9fe12-144">Click New.</span></span>
35. <span data-ttu-id="9fe12-145">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="9fe12-145">In the Name field, click the drop-down button to open the lookup.</span></span>
36. <span data-ttu-id="9fe12-146">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="9fe12-146">In the list, find and select the desired record.</span></span>
37. <span data-ttu-id="9fe12-147">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="9fe12-147">In the list, click the link in the selected row.</span></span>
38. <span data-ttu-id="9fe12-148">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="9fe12-148">Click Save.</span></span>
39. <span data-ttu-id="9fe12-149">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="9fe12-149">Close the page.</span></span>
40. <span data-ttu-id="9fe12-150">Klicka på Ställ in i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="9fe12-150">On the Action Pane, click Set up.</span></span>
41. <span data-ttu-id="9fe12-151">Klicka på Betalningsmetoder.</span><span class="sxs-lookup"><span data-stu-id="9fe12-151">Click Payment methods.</span></span>
42. <span data-ttu-id="9fe12-152">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="9fe12-152">Click New.</span></span>
43. <span data-ttu-id="9fe12-153">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Betalningsmetod.</span><span class="sxs-lookup"><span data-stu-id="9fe12-153">In the Payment method field, click the drop-down button to open the lookup.</span></span>
44. <span data-ttu-id="9fe12-154">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="9fe12-154">In the list, click the link in the selected row.</span></span>
45. <span data-ttu-id="9fe12-155">Utöka eller komprimera avsnittet Bokföring.</span><span class="sxs-lookup"><span data-stu-id="9fe12-155">Expand or collapse the Posting section.</span></span>
46. <span data-ttu-id="9fe12-156">Ange önskade värden i fältet Kontonummer.</span><span class="sxs-lookup"><span data-stu-id="9fe12-156">In the Account number field, specify the desired values.</span></span>
47. <span data-ttu-id="9fe12-157">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="9fe12-157">Click Save.</span></span>
48. <span data-ttu-id="9fe12-158">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="9fe12-158">Close the page.</span></span>
49. <span data-ttu-id="9fe12-159">Klicka på Ställ in i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="9fe12-159">On the Action Pane, click Set up.</span></span>
50. <span data-ttu-id="9fe12-160">Klicka på Kontantavstämning.</span><span class="sxs-lookup"><span data-stu-id="9fe12-160">Click Cash declaration.</span></span>
51. <span data-ttu-id="9fe12-161">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="9fe12-161">Click New.</span></span>
52. <span data-ttu-id="9fe12-162">Ange ett tal i fältet Belopp i transaktionsvaluta.</span><span class="sxs-lookup"><span data-stu-id="9fe12-162">In the Amount in transaction currency field, enter a number.</span></span>
53. <span data-ttu-id="9fe12-163">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Valuta.</span><span class="sxs-lookup"><span data-stu-id="9fe12-163">In the Currency field, click the drop-down button to open the lookup.</span></span>
54. <span data-ttu-id="9fe12-164">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="9fe12-164">In the list, find and select the desired record.</span></span>
55. <span data-ttu-id="9fe12-165">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="9fe12-165">In the list, click the link in the selected row.</span></span>
56. <span data-ttu-id="9fe12-166">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="9fe12-166">Click Save.</span></span>
57. <span data-ttu-id="9fe12-167">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="9fe12-167">Close the page.</span></span>
58. <span data-ttu-id="9fe12-168">Klicka på Ställ in i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="9fe12-168">On the Action Pane, click Set up.</span></span>
59. <span data-ttu-id="9fe12-169">Klicka på Tilldelning för butikslokaliserargrupp.</span><span class="sxs-lookup"><span data-stu-id="9fe12-169">Click Store locator group assignment.</span></span>
60. <span data-ttu-id="9fe12-170">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="9fe12-170">Click New.</span></span>
61. <span data-ttu-id="9fe12-171">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="9fe12-171">In the list, mark the selected row.</span></span>
62. <span data-ttu-id="9fe12-172">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Lokaliserargrupp.</span><span class="sxs-lookup"><span data-stu-id="9fe12-172">In the Locator group field, click the drop-down button to open the lookup.</span></span>
63. <span data-ttu-id="9fe12-173">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="9fe12-173">In the list, find and select the desired record.</span></span>
64. <span data-ttu-id="9fe12-174">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="9fe12-174">In the list, click the link in the selected row.</span></span>
65. <span data-ttu-id="9fe12-175">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="9fe12-175">Click Save.</span></span>
66. <span data-ttu-id="9fe12-176">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="9fe12-176">Close the page.</span></span>

