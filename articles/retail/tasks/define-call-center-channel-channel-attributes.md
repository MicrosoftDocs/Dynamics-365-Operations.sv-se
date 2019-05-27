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
ms.openlocfilehash: 7ef094535214ecf4c65f95c36a93455446d7e388
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/15/2019
ms.locfileid: "1556148"
---
# <a name="create-call-center-channels-and-define-channel-attributes"></a><span data-ttu-id="dbbf0-103">Skapa kundtjänstkanaler och definiera kanalattribut</span><span class="sxs-lookup"><span data-stu-id="dbbf0-103">Create call center channels and define channel attributes</span></span>

[!include [task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="dbbf0-104">Den här proceduren beskriver hur du skapar en ny butikskanal och definierar kanalattribut.</span><span class="sxs-lookup"><span data-stu-id="dbbf0-104">This procedure walks through creating a new retail channel and defining channel attributes.</span></span> <span data-ttu-id="dbbf0-105">Det demonstrationsdataföretag som används för att skapa den här uppgiften är USRT.</span><span class="sxs-lookup"><span data-stu-id="dbbf0-105">The demo data company used to create this task is USRT.</span></span> <span data-ttu-id="dbbf0-106">Den här proceduren är avsedd för rollen Butik-IT.</span><span class="sxs-lookup"><span data-stu-id="dbbf0-106">This procedure is intended for the Retail IT role.</span></span>


## <a name="create-new-store"></a><span data-ttu-id="dbbf0-107">Skapa ny butik</span><span class="sxs-lookup"><span data-stu-id="dbbf0-107">Create new store</span></span>
1. <span data-ttu-id="dbbf0-108">Gå till Alla arbetsytor > Kanalgruppering.</span><span class="sxs-lookup"><span data-stu-id="dbbf0-108">Go to All workspaces > Channel deployment.</span></span>
2. <span data-ttu-id="dbbf0-109">Klicka på Ny kanal.</span><span class="sxs-lookup"><span data-stu-id="dbbf0-109">Click New channel.</span></span>
3. <span data-ttu-id="dbbf0-110">Klicka på Butik.</span><span class="sxs-lookup"><span data-stu-id="dbbf0-110">Click Store.</span></span>
4. <span data-ttu-id="dbbf0-111">Skriv ett värde i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="dbbf0-111">In the Name field, type a value.</span></span>
5. <span data-ttu-id="dbbf0-112">Skriv ett värde i fältet Butiksnummer.</span><span class="sxs-lookup"><span data-stu-id="dbbf0-112">In the Store number field, type a value.</span></span>
6. <span data-ttu-id="dbbf0-113">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Lagerställe.</span><span class="sxs-lookup"><span data-stu-id="dbbf0-113">In the Warehouse field, click the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="dbbf0-114">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="dbbf0-114">In the list, find and select the desired record.</span></span>
8. <span data-ttu-id="dbbf0-115">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="dbbf0-115">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="dbbf0-116">Markera ett alternativ i fältet Tidszon för butik.</span><span class="sxs-lookup"><span data-stu-id="dbbf0-116">In the Store time zone field, select an option.</span></span>
10. <span data-ttu-id="dbbf0-117">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Kanalprofil.</span><span class="sxs-lookup"><span data-stu-id="dbbf0-117">In the Channel profile field, click the drop-down button to open the lookup.</span></span>
11. <span data-ttu-id="dbbf0-118">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="dbbf0-118">In the list, click the link in the selected row.</span></span>
12. <span data-ttu-id="dbbf0-119">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Språk.</span><span class="sxs-lookup"><span data-stu-id="dbbf0-119">In the Language field, click the drop-down button to open the lookup.</span></span>
13. <span data-ttu-id="dbbf0-120">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="dbbf0-120">In the list, find and select the desired record.</span></span>
14. <span data-ttu-id="dbbf0-121">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="dbbf0-121">In the list, click the link in the selected row.</span></span>
15. <span data-ttu-id="dbbf0-122">I fältet Momsgrupp, öppna sökningen genom att klicka på den nedrullningsbara knappen.</span><span class="sxs-lookup"><span data-stu-id="dbbf0-122">In the Sales tax group field, click the drop-down button to open the lookup.</span></span>
16. <span data-ttu-id="dbbf0-123">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="dbbf0-123">In the list, find and select the desired record.</span></span>
17. <span data-ttu-id="dbbf0-124">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="dbbf0-124">In the list, click the link in the selected row.</span></span>
18. <span data-ttu-id="dbbf0-125">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Kundens adressbok.</span><span class="sxs-lookup"><span data-stu-id="dbbf0-125">In the Customer address book field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="dbbf0-126">Välj adressboken som ska användas för att koppla kunder till den här butiken.</span><span class="sxs-lookup"><span data-stu-id="dbbf0-126">Select the address book used to link customers to this store.</span></span>  
19. <span data-ttu-id="dbbf0-127">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="dbbf0-127">In the list, find and select the desired record.</span></span>
20. <span data-ttu-id="dbbf0-128">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="dbbf0-128">In the list, click the link in the selected row.</span></span>
21. <span data-ttu-id="dbbf0-129">Klicka på Välj.</span><span class="sxs-lookup"><span data-stu-id="dbbf0-129">Click Select.</span></span>
22. <span data-ttu-id="dbbf0-130">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Medarbetarens adressbok.</span><span class="sxs-lookup"><span data-stu-id="dbbf0-130">In the Employee address book field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="dbbf0-131">Välj adressboken som ska användas för att koppla kassörer till den här kanalen.</span><span class="sxs-lookup"><span data-stu-id="dbbf0-131">Select the address book used to link cashiers to this channel.</span></span>  
23. <span data-ttu-id="dbbf0-132">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="dbbf0-132">In the list, find and select the desired record.</span></span>
24. <span data-ttu-id="dbbf0-133">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="dbbf0-133">In the list, click the link in the selected row.</span></span>
25. <span data-ttu-id="dbbf0-134">Klicka på Välj.</span><span class="sxs-lookup"><span data-stu-id="dbbf0-134">Click Select.</span></span>
26. <span data-ttu-id="dbbf0-135">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Standardkund.</span><span class="sxs-lookup"><span data-stu-id="dbbf0-135">In the Default customer field, click the drop-down button to open the lookup.</span></span>
27. <span data-ttu-id="dbbf0-136">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="dbbf0-136">In the list, click the link in the selected row.</span></span>
28. <span data-ttu-id="dbbf0-137">Utöka eller komprimera avsnittet Skärmlayout.</span><span class="sxs-lookup"><span data-stu-id="dbbf0-137">Expand or collapse the Screen layout section.</span></span>
29. <span data-ttu-id="dbbf0-138">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Skärmlayout-ID.</span><span class="sxs-lookup"><span data-stu-id="dbbf0-138">In the Screen layout ID field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="dbbf0-139">Välj standardlayout för den här butikens kassaskärm.</span><span class="sxs-lookup"><span data-stu-id="dbbf0-139">Select the default POS screen layout for this store.</span></span>  
30. <span data-ttu-id="dbbf0-140">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="dbbf0-140">In the list, find and select the desired record.</span></span>
31. <span data-ttu-id="dbbf0-141">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="dbbf0-141">In the list, click the link in the selected row.</span></span>
32. <span data-ttu-id="dbbf0-142">Klicka på Ställ in i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="dbbf0-142">On the Action Pane, click Set up.</span></span>
33. <span data-ttu-id="dbbf0-143">Klicka på Kanalattribut.</span><span class="sxs-lookup"><span data-stu-id="dbbf0-143">Click Channel attributes.</span></span>
34. <span data-ttu-id="dbbf0-144">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="dbbf0-144">Click New.</span></span>
35. <span data-ttu-id="dbbf0-145">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="dbbf0-145">In the Name field, click the drop-down button to open the lookup.</span></span>
36. <span data-ttu-id="dbbf0-146">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="dbbf0-146">In the list, find and select the desired record.</span></span>
37. <span data-ttu-id="dbbf0-147">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="dbbf0-147">In the list, click the link in the selected row.</span></span>
38. <span data-ttu-id="dbbf0-148">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="dbbf0-148">Click Save.</span></span>
39. <span data-ttu-id="dbbf0-149">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="dbbf0-149">Close the page.</span></span>
40. <span data-ttu-id="dbbf0-150">Klicka på Ställ in i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="dbbf0-150">On the Action Pane, click Set up.</span></span>
41. <span data-ttu-id="dbbf0-151">Klicka på Betalningsmetoder.</span><span class="sxs-lookup"><span data-stu-id="dbbf0-151">Click Payment methods.</span></span>
42. <span data-ttu-id="dbbf0-152">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="dbbf0-152">Click New.</span></span>
43. <span data-ttu-id="dbbf0-153">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Betalningsmetod.</span><span class="sxs-lookup"><span data-stu-id="dbbf0-153">In the Payment method field, click the drop-down button to open the lookup.</span></span>
44. <span data-ttu-id="dbbf0-154">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="dbbf0-154">In the list, click the link in the selected row.</span></span>
45. <span data-ttu-id="dbbf0-155">Utöka eller komprimera avsnittet Bokföring.</span><span class="sxs-lookup"><span data-stu-id="dbbf0-155">Expand or collapse the Posting section.</span></span>
46. <span data-ttu-id="dbbf0-156">Ange önskade värden i fältet Kontonummer.</span><span class="sxs-lookup"><span data-stu-id="dbbf0-156">In the Account number field, specify the desired values.</span></span>
47. <span data-ttu-id="dbbf0-157">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="dbbf0-157">Click Save.</span></span>
48. <span data-ttu-id="dbbf0-158">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="dbbf0-158">Close the page.</span></span>
49. <span data-ttu-id="dbbf0-159">Klicka på Ställ in i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="dbbf0-159">On the Action Pane, click Set up.</span></span>
50. <span data-ttu-id="dbbf0-160">Klicka på Kontantavstämning.</span><span class="sxs-lookup"><span data-stu-id="dbbf0-160">Click Cash declaration.</span></span>
51. <span data-ttu-id="dbbf0-161">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="dbbf0-161">Click New.</span></span>
52. <span data-ttu-id="dbbf0-162">Ange ett tal i fältet Belopp i transaktionsvaluta.</span><span class="sxs-lookup"><span data-stu-id="dbbf0-162">In the Amount in transaction currency field, enter a number.</span></span>
53. <span data-ttu-id="dbbf0-163">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Valuta.</span><span class="sxs-lookup"><span data-stu-id="dbbf0-163">In the Currency field, click the drop-down button to open the lookup.</span></span>
54. <span data-ttu-id="dbbf0-164">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="dbbf0-164">In the list, find and select the desired record.</span></span>
55. <span data-ttu-id="dbbf0-165">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="dbbf0-165">In the list, click the link in the selected row.</span></span>
56. <span data-ttu-id="dbbf0-166">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="dbbf0-166">Click Save.</span></span>
57. <span data-ttu-id="dbbf0-167">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="dbbf0-167">Close the page.</span></span>
58. <span data-ttu-id="dbbf0-168">Klicka på Ställ in i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="dbbf0-168">On the Action Pane, click Set up.</span></span>
59. <span data-ttu-id="dbbf0-169">Klicka på Tilldelning för butikslokaliserargrupp.</span><span class="sxs-lookup"><span data-stu-id="dbbf0-169">Click Store locator group assignment.</span></span>
60. <span data-ttu-id="dbbf0-170">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="dbbf0-170">Click New.</span></span>
61. <span data-ttu-id="dbbf0-171">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="dbbf0-171">In the list, mark the selected row.</span></span>
62. <span data-ttu-id="dbbf0-172">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Lokaliserargrupp.</span><span class="sxs-lookup"><span data-stu-id="dbbf0-172">In the Locator group field, click the drop-down button to open the lookup.</span></span>
63. <span data-ttu-id="dbbf0-173">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="dbbf0-173">In the list, find and select the desired record.</span></span>
64. <span data-ttu-id="dbbf0-174">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="dbbf0-174">In the list, click the link in the selected row.</span></span>
65. <span data-ttu-id="dbbf0-175">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="dbbf0-175">Click Save.</span></span>
66. <span data-ttu-id="dbbf0-176">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="dbbf0-176">Close the page.</span></span>

