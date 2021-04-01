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
ms.search.region: Global
ms.author: mumani
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d5e4ef84abcfd0948c46c5312078f2a940840144
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5256959"
---
# <a name="create-call-center-channels-and-define-channel-attributes"></a><span data-ttu-id="477f6-103">Skapa kundtjänstkanaler och definiera kanalattribut</span><span class="sxs-lookup"><span data-stu-id="477f6-103">Create call center channels and define channel attributes</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="477f6-104">Den här proceduren beskriver hur du skapar en ny handelskanal och definierar kanalattribut.</span><span class="sxs-lookup"><span data-stu-id="477f6-104">This procedure walks through creating a new commerce channel and defining channel attributes.</span></span> <span data-ttu-id="477f6-105">Det demonstrationsdataföretag som används för att skapa den här uppgiften är USRT.</span><span class="sxs-lookup"><span data-stu-id="477f6-105">The demo data company used to create this task is USRT.</span></span> <span data-ttu-id="477f6-106">Den här proceduren är avsedd för rollen Commerces-IT.</span><span class="sxs-lookup"><span data-stu-id="477f6-106">This procedure is intended for the Commerce IT role.</span></span>


## <a name="create-new-store"></a><span data-ttu-id="477f6-107">Skapa ny butik</span><span class="sxs-lookup"><span data-stu-id="477f6-107">Create new store</span></span>
1. <span data-ttu-id="477f6-108">Gå till Alla arbetsytor > Kanalgruppering.</span><span class="sxs-lookup"><span data-stu-id="477f6-108">Go to All workspaces > Channel deployment.</span></span>
2. <span data-ttu-id="477f6-109">Klicka på Ny kanal.</span><span class="sxs-lookup"><span data-stu-id="477f6-109">Click New channel.</span></span>
3. <span data-ttu-id="477f6-110">Klicka på Butik.</span><span class="sxs-lookup"><span data-stu-id="477f6-110">Click Store.</span></span>
4. <span data-ttu-id="477f6-111">Skriv ett värde i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="477f6-111">In the Name field, type a value.</span></span>
5. <span data-ttu-id="477f6-112">Skriv ett värde i fältet Butiksnummer.</span><span class="sxs-lookup"><span data-stu-id="477f6-112">In the Store number field, type a value.</span></span>
6. <span data-ttu-id="477f6-113">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Lagerställe.</span><span class="sxs-lookup"><span data-stu-id="477f6-113">In the Warehouse field, click the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="477f6-114">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="477f6-114">In the list, find and select the desired record.</span></span>
8. <span data-ttu-id="477f6-115">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="477f6-115">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="477f6-116">Markera ett alternativ i fältet Tidszon för butik.</span><span class="sxs-lookup"><span data-stu-id="477f6-116">In the Store time zone field, select an option.</span></span>
10. <span data-ttu-id="477f6-117">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Kanalprofil.</span><span class="sxs-lookup"><span data-stu-id="477f6-117">In the Channel profile field, click the drop-down button to open the lookup.</span></span>
11. <span data-ttu-id="477f6-118">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="477f6-118">In the list, click the link in the selected row.</span></span>
12. <span data-ttu-id="477f6-119">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Språk.</span><span class="sxs-lookup"><span data-stu-id="477f6-119">In the Language field, click the drop-down button to open the lookup.</span></span>
13. <span data-ttu-id="477f6-120">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="477f6-120">In the list, find and select the desired record.</span></span>
14. <span data-ttu-id="477f6-121">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="477f6-121">In the list, click the link in the selected row.</span></span>
15. <span data-ttu-id="477f6-122">I fältet Momsgrupp, öppna sökningen genom att klicka på den nedrullningsbara knappen.</span><span class="sxs-lookup"><span data-stu-id="477f6-122">In the Sales tax group field, click the drop-down button to open the lookup.</span></span>
16. <span data-ttu-id="477f6-123">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="477f6-123">In the list, find and select the desired record.</span></span>
17. <span data-ttu-id="477f6-124">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="477f6-124">In the list, click the link in the selected row.</span></span>
18. <span data-ttu-id="477f6-125">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Kundens adressbok.</span><span class="sxs-lookup"><span data-stu-id="477f6-125">In the Customer address book field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="477f6-126">Välj adressboken som ska användas för att koppla kunder till den här butiken.</span><span class="sxs-lookup"><span data-stu-id="477f6-126">Select the address book used to link customers to this store.</span></span>  
19. <span data-ttu-id="477f6-127">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="477f6-127">In the list, find and select the desired record.</span></span>
20. <span data-ttu-id="477f6-128">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="477f6-128">In the list, click the link in the selected row.</span></span>
21. <span data-ttu-id="477f6-129">Klicka på Välj.</span><span class="sxs-lookup"><span data-stu-id="477f6-129">Click Select.</span></span>
22. <span data-ttu-id="477f6-130">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Medarbetarens adressbok.</span><span class="sxs-lookup"><span data-stu-id="477f6-130">In the Employee address book field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="477f6-131">Välj adressboken som ska användas för att koppla kassörer till den här kanalen.</span><span class="sxs-lookup"><span data-stu-id="477f6-131">Select the address book used to link cashiers to this channel.</span></span>  
23. <span data-ttu-id="477f6-132">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="477f6-132">In the list, find and select the desired record.</span></span>
24. <span data-ttu-id="477f6-133">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="477f6-133">In the list, click the link in the selected row.</span></span>
25. <span data-ttu-id="477f6-134">Klicka på Välj.</span><span class="sxs-lookup"><span data-stu-id="477f6-134">Click Select.</span></span>
26. <span data-ttu-id="477f6-135">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Standardkund.</span><span class="sxs-lookup"><span data-stu-id="477f6-135">In the Default customer field, click the drop-down button to open the lookup.</span></span>
27. <span data-ttu-id="477f6-136">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="477f6-136">In the list, click the link in the selected row.</span></span>
28. <span data-ttu-id="477f6-137">Utöka eller komprimera avsnittet Skärmlayout.</span><span class="sxs-lookup"><span data-stu-id="477f6-137">Expand or collapse the Screen layout section.</span></span>
29. <span data-ttu-id="477f6-138">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Skärmlayout-ID.</span><span class="sxs-lookup"><span data-stu-id="477f6-138">In the Screen layout ID field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="477f6-139">Välj standardlayout för den här butikens kassaskärm.</span><span class="sxs-lookup"><span data-stu-id="477f6-139">Select the default POS screen layout for this store.</span></span>  
30. <span data-ttu-id="477f6-140">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="477f6-140">In the list, find and select the desired record.</span></span>
31. <span data-ttu-id="477f6-141">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="477f6-141">In the list, click the link in the selected row.</span></span>
32. <span data-ttu-id="477f6-142">Klicka på Ställ in i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="477f6-142">On the Action Pane, click Set up.</span></span>
33. <span data-ttu-id="477f6-143">Klicka på Kanalattribut.</span><span class="sxs-lookup"><span data-stu-id="477f6-143">Click Channel attributes.</span></span>
34. <span data-ttu-id="477f6-144">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="477f6-144">Click New.</span></span>
35. <span data-ttu-id="477f6-145">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="477f6-145">In the Name field, click the drop-down button to open the lookup.</span></span>
36. <span data-ttu-id="477f6-146">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="477f6-146">In the list, find and select the desired record.</span></span>
37. <span data-ttu-id="477f6-147">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="477f6-147">In the list, click the link in the selected row.</span></span>
38. <span data-ttu-id="477f6-148">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="477f6-148">Click Save.</span></span>
39. <span data-ttu-id="477f6-149">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="477f6-149">Close the page.</span></span>
40. <span data-ttu-id="477f6-150">Klicka på Ställ in i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="477f6-150">On the Action Pane, click Set up.</span></span>
41. <span data-ttu-id="477f6-151">Klicka på Betalsätt.</span><span class="sxs-lookup"><span data-stu-id="477f6-151">Click Payment methods.</span></span>
42. <span data-ttu-id="477f6-152">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="477f6-152">Click New.</span></span>
43. <span data-ttu-id="477f6-153">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Betalningsmetod.</span><span class="sxs-lookup"><span data-stu-id="477f6-153">In the Payment method field, click the drop-down button to open the lookup.</span></span>
44. <span data-ttu-id="477f6-154">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="477f6-154">In the list, click the link in the selected row.</span></span>
45. <span data-ttu-id="477f6-155">Utöka eller komprimera avsnittet Bokföring.</span><span class="sxs-lookup"><span data-stu-id="477f6-155">Expand or collapse the Posting section.</span></span>
46. <span data-ttu-id="477f6-156">Ange önskade värden i fältet Kontonummer.</span><span class="sxs-lookup"><span data-stu-id="477f6-156">In the Account number field, specify the desired values.</span></span>
47. <span data-ttu-id="477f6-157">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="477f6-157">Click Save.</span></span>
48. <span data-ttu-id="477f6-158">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="477f6-158">Close the page.</span></span>
49. <span data-ttu-id="477f6-159">Klicka på Ställ in i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="477f6-159">On the Action Pane, click Set up.</span></span>
50. <span data-ttu-id="477f6-160">Klicka på Kontantavstämning.</span><span class="sxs-lookup"><span data-stu-id="477f6-160">Click Cash declaration.</span></span>
51. <span data-ttu-id="477f6-161">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="477f6-161">Click New.</span></span>
52. <span data-ttu-id="477f6-162">Ange ett tal i fältet Belopp i transaktionsvaluta.</span><span class="sxs-lookup"><span data-stu-id="477f6-162">In the Amount in transaction currency field, enter a number.</span></span>
53. <span data-ttu-id="477f6-163">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Valuta.</span><span class="sxs-lookup"><span data-stu-id="477f6-163">In the Currency field, click the drop-down button to open the lookup.</span></span>
54. <span data-ttu-id="477f6-164">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="477f6-164">In the list, find and select the desired record.</span></span>
55. <span data-ttu-id="477f6-165">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="477f6-165">In the list, click the link in the selected row.</span></span>
56. <span data-ttu-id="477f6-166">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="477f6-166">Click Save.</span></span>
57. <span data-ttu-id="477f6-167">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="477f6-167">Close the page.</span></span>
58. <span data-ttu-id="477f6-168">Klicka på Ställ in i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="477f6-168">On the Action Pane, click Set up.</span></span>
59. <span data-ttu-id="477f6-169">Klicka på Tilldelning för butikslokaliserargrupp.</span><span class="sxs-lookup"><span data-stu-id="477f6-169">Click Store locator group assignment.</span></span>
60. <span data-ttu-id="477f6-170">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="477f6-170">Click New.</span></span>
61. <span data-ttu-id="477f6-171">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="477f6-171">In the list, mark the selected row.</span></span>
62. <span data-ttu-id="477f6-172">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Lokaliserargrupp.</span><span class="sxs-lookup"><span data-stu-id="477f6-172">In the Locator group field, click the drop-down button to open the lookup.</span></span>
63. <span data-ttu-id="477f6-173">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="477f6-173">In the list, find and select the desired record.</span></span>
64. <span data-ttu-id="477f6-174">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="477f6-174">In the list, click the link in the selected row.</span></span>
65. <span data-ttu-id="477f6-175">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="477f6-175">Click Save.</span></span>
66. <span data-ttu-id="477f6-176">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="477f6-176">Close the page.</span></span>



[!INCLUDE[footer-include](../../includes/footer-banner.md)]