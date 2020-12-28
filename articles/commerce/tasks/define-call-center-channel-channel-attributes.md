---
title: Skapa kundtjänstkanaler och definiera kanalattribut
description: Den här proceduren beskriver hur du skapar en ny kanal och definierar kanalattribut.
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
ms.openlocfilehash: a2f99029195a8b783f0d12990d4e8bab0bb348d7
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "4415878"
---
# <a name="create-call-center-channels-and-define-channel-attributes"></a><span data-ttu-id="fa143-103">Skapa kundtjänstkanaler och definiera kanalattribut</span><span class="sxs-lookup"><span data-stu-id="fa143-103">Create call center channels and define channel attributes</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="fa143-104">Den här proceduren beskriver hur du skapar en ny handelskanal och definierar kanalattribut.</span><span class="sxs-lookup"><span data-stu-id="fa143-104">This procedure walks through creating a new commerce channel and defining channel attributes.</span></span> <span data-ttu-id="fa143-105">Det demonstrationsdataföretag som används för att skapa den här uppgiften är USRT.</span><span class="sxs-lookup"><span data-stu-id="fa143-105">The demo data company used to create this task is USRT.</span></span> <span data-ttu-id="fa143-106">Den här proceduren är avsedd för rollen Handels-IT.</span><span class="sxs-lookup"><span data-stu-id="fa143-106">This procedure is intended for the Commerce IT role.</span></span>


## <a name="create-new-store"></a><span data-ttu-id="fa143-107">Skapa ny butik</span><span class="sxs-lookup"><span data-stu-id="fa143-107">Create new store</span></span>
1. <span data-ttu-id="fa143-108">Gå till Alla arbetsytor > Kanalgruppering.</span><span class="sxs-lookup"><span data-stu-id="fa143-108">Go to All workspaces > Channel deployment.</span></span>
2. <span data-ttu-id="fa143-109">Klicka på Ny kanal.</span><span class="sxs-lookup"><span data-stu-id="fa143-109">Click New channel.</span></span>
3. <span data-ttu-id="fa143-110">Klicka på Butik.</span><span class="sxs-lookup"><span data-stu-id="fa143-110">Click Store.</span></span>
4. <span data-ttu-id="fa143-111">Skriv ett värde i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="fa143-111">In the Name field, type a value.</span></span>
5. <span data-ttu-id="fa143-112">Skriv ett värde i fältet Butiksnummer.</span><span class="sxs-lookup"><span data-stu-id="fa143-112">In the Store number field, type a value.</span></span>
6. <span data-ttu-id="fa143-113">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Lagerställe.</span><span class="sxs-lookup"><span data-stu-id="fa143-113">In the Warehouse field, click the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="fa143-114">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="fa143-114">In the list, find and select the desired record.</span></span>
8. <span data-ttu-id="fa143-115">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="fa143-115">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="fa143-116">Markera ett alternativ i fältet Tidszon för butik.</span><span class="sxs-lookup"><span data-stu-id="fa143-116">In the Store time zone field, select an option.</span></span>
10. <span data-ttu-id="fa143-117">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Kanalprofil.</span><span class="sxs-lookup"><span data-stu-id="fa143-117">In the Channel profile field, click the drop-down button to open the lookup.</span></span>
11. <span data-ttu-id="fa143-118">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="fa143-118">In the list, click the link in the selected row.</span></span>
12. <span data-ttu-id="fa143-119">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Språk.</span><span class="sxs-lookup"><span data-stu-id="fa143-119">In the Language field, click the drop-down button to open the lookup.</span></span>
13. <span data-ttu-id="fa143-120">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="fa143-120">In the list, find and select the desired record.</span></span>
14. <span data-ttu-id="fa143-121">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="fa143-121">In the list, click the link in the selected row.</span></span>
15. <span data-ttu-id="fa143-122">I fältet Momsgrupp, öppna sökningen genom att klicka på den nedrullningsbara knappen.</span><span class="sxs-lookup"><span data-stu-id="fa143-122">In the Sales tax group field, click the drop-down button to open the lookup.</span></span>
16. <span data-ttu-id="fa143-123">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="fa143-123">In the list, find and select the desired record.</span></span>
17. <span data-ttu-id="fa143-124">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="fa143-124">In the list, click the link in the selected row.</span></span>
18. <span data-ttu-id="fa143-125">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Kundens adressbok.</span><span class="sxs-lookup"><span data-stu-id="fa143-125">In the Customer address book field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="fa143-126">Välj adressboken som ska användas för att koppla kunder till den här butiken.</span><span class="sxs-lookup"><span data-stu-id="fa143-126">Select the address book used to link customers to this store.</span></span>  
19. <span data-ttu-id="fa143-127">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="fa143-127">In the list, find and select the desired record.</span></span>
20. <span data-ttu-id="fa143-128">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="fa143-128">In the list, click the link in the selected row.</span></span>
21. <span data-ttu-id="fa143-129">Klicka på Välj.</span><span class="sxs-lookup"><span data-stu-id="fa143-129">Click Select.</span></span>
22. <span data-ttu-id="fa143-130">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Medarbetarens adressbok.</span><span class="sxs-lookup"><span data-stu-id="fa143-130">In the Employee address book field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="fa143-131">Välj adressboken som ska användas för att koppla kassörer till den här kanalen.</span><span class="sxs-lookup"><span data-stu-id="fa143-131">Select the address book used to link cashiers to this channel.</span></span>  
23. <span data-ttu-id="fa143-132">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="fa143-132">In the list, find and select the desired record.</span></span>
24. <span data-ttu-id="fa143-133">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="fa143-133">In the list, click the link in the selected row.</span></span>
25. <span data-ttu-id="fa143-134">Klicka på Välj.</span><span class="sxs-lookup"><span data-stu-id="fa143-134">Click Select.</span></span>
26. <span data-ttu-id="fa143-135">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Standardkund.</span><span class="sxs-lookup"><span data-stu-id="fa143-135">In the Default customer field, click the drop-down button to open the lookup.</span></span>
27. <span data-ttu-id="fa143-136">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="fa143-136">In the list, click the link in the selected row.</span></span>
28. <span data-ttu-id="fa143-137">Utöka eller komprimera avsnittet Skärmlayout.</span><span class="sxs-lookup"><span data-stu-id="fa143-137">Expand or collapse the Screen layout section.</span></span>
29. <span data-ttu-id="fa143-138">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Skärmlayout-ID.</span><span class="sxs-lookup"><span data-stu-id="fa143-138">In the Screen layout ID field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="fa143-139">Välj standardlayout för den här butikens kassaskärm.</span><span class="sxs-lookup"><span data-stu-id="fa143-139">Select the default POS screen layout for this store.</span></span>  
30. <span data-ttu-id="fa143-140">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="fa143-140">In the list, find and select the desired record.</span></span>
31. <span data-ttu-id="fa143-141">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="fa143-141">In the list, click the link in the selected row.</span></span>
32. <span data-ttu-id="fa143-142">Klicka på Ställ in i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="fa143-142">On the Action Pane, click Set up.</span></span>
33. <span data-ttu-id="fa143-143">Klicka på Kanalattribut.</span><span class="sxs-lookup"><span data-stu-id="fa143-143">Click Channel attributes.</span></span>
34. <span data-ttu-id="fa143-144">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="fa143-144">Click New.</span></span>
35. <span data-ttu-id="fa143-145">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="fa143-145">In the Name field, click the drop-down button to open the lookup.</span></span>
36. <span data-ttu-id="fa143-146">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="fa143-146">In the list, find and select the desired record.</span></span>
37. <span data-ttu-id="fa143-147">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="fa143-147">In the list, click the link in the selected row.</span></span>
38. <span data-ttu-id="fa143-148">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="fa143-148">Click Save.</span></span>
39. <span data-ttu-id="fa143-149">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="fa143-149">Close the page.</span></span>
40. <span data-ttu-id="fa143-150">Klicka på Ställ in i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="fa143-150">On the Action Pane, click Set up.</span></span>
41. <span data-ttu-id="fa143-151">Klicka på Betalningsmetoder.</span><span class="sxs-lookup"><span data-stu-id="fa143-151">Click Payment methods.</span></span>
42. <span data-ttu-id="fa143-152">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="fa143-152">Click New.</span></span>
43. <span data-ttu-id="fa143-153">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Betalningsmetod.</span><span class="sxs-lookup"><span data-stu-id="fa143-153">In the Payment method field, click the drop-down button to open the lookup.</span></span>
44. <span data-ttu-id="fa143-154">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="fa143-154">In the list, click the link in the selected row.</span></span>
45. <span data-ttu-id="fa143-155">Utöka eller komprimera avsnittet Bokföring.</span><span class="sxs-lookup"><span data-stu-id="fa143-155">Expand or collapse the Posting section.</span></span>
46. <span data-ttu-id="fa143-156">Ange önskade värden i fältet Kontonummer.</span><span class="sxs-lookup"><span data-stu-id="fa143-156">In the Account number field, specify the desired values.</span></span>
47. <span data-ttu-id="fa143-157">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="fa143-157">Click Save.</span></span>
48. <span data-ttu-id="fa143-158">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="fa143-158">Close the page.</span></span>
49. <span data-ttu-id="fa143-159">Klicka på Ställ in i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="fa143-159">On the Action Pane, click Set up.</span></span>
50. <span data-ttu-id="fa143-160">Klicka på Kontantavstämning.</span><span class="sxs-lookup"><span data-stu-id="fa143-160">Click Cash declaration.</span></span>
51. <span data-ttu-id="fa143-161">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="fa143-161">Click New.</span></span>
52. <span data-ttu-id="fa143-162">Ange ett tal i fältet Belopp i transaktionsvaluta.</span><span class="sxs-lookup"><span data-stu-id="fa143-162">In the Amount in transaction currency field, enter a number.</span></span>
53. <span data-ttu-id="fa143-163">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Valuta.</span><span class="sxs-lookup"><span data-stu-id="fa143-163">In the Currency field, click the drop-down button to open the lookup.</span></span>
54. <span data-ttu-id="fa143-164">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="fa143-164">In the list, find and select the desired record.</span></span>
55. <span data-ttu-id="fa143-165">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="fa143-165">In the list, click the link in the selected row.</span></span>
56. <span data-ttu-id="fa143-166">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="fa143-166">Click Save.</span></span>
57. <span data-ttu-id="fa143-167">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="fa143-167">Close the page.</span></span>
58. <span data-ttu-id="fa143-168">Klicka på Ställ in i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="fa143-168">On the Action Pane, click Set up.</span></span>
59. <span data-ttu-id="fa143-169">Klicka på Tilldelning för butikslokaliserargrupp.</span><span class="sxs-lookup"><span data-stu-id="fa143-169">Click Store locator group assignment.</span></span>
60. <span data-ttu-id="fa143-170">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="fa143-170">Click New.</span></span>
61. <span data-ttu-id="fa143-171">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="fa143-171">In the list, mark the selected row.</span></span>
62. <span data-ttu-id="fa143-172">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Lokaliserargrupp.</span><span class="sxs-lookup"><span data-stu-id="fa143-172">In the Locator group field, click the drop-down button to open the lookup.</span></span>
63. <span data-ttu-id="fa143-173">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="fa143-173">In the list, find and select the desired record.</span></span>
64. <span data-ttu-id="fa143-174">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="fa143-174">In the list, click the link in the selected row.</span></span>
65. <span data-ttu-id="fa143-175">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="fa143-175">Click Save.</span></span>
66. <span data-ttu-id="fa143-176">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="fa143-176">Close the page.</span></span>

