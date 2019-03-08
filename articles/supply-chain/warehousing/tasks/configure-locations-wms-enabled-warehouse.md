---
title: Konfigurera platser i ett WMS-aktiverat lagerställe
description: Den här guiden visar hur du konfigurerar platsinställningar för ett nytt WMS-aktiverat lagerställe (ett lagerställe som använder avancerade lagerstyrningsprocesser).
author: perlynne
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventLocation, WHSLocationFormat, WHSLocationType, WHSLocationProfile, WHSParameters, WHSZoneGroup, WHSZone, WHSLocationBuild, WHSLocation, WHSPackSizeCategory, WHSLocationLimit, WHSInventFixedLocation, WMSLocationIdLookup
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 2be3c7cb33225041872e8b747ba28063f897dae9
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2019
ms.locfileid: "337335"
---
# <a name="configure-locations-in-a-wms-enabled-warehouse"></a><span data-ttu-id="0bab3-103">Konfigurera platser i ett WMS-aktiverat lagerställe</span><span class="sxs-lookup"><span data-stu-id="0bab3-103">Configure locations in a WMS-enabled warehouse</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="0bab3-104">Den här guiden visar hur du konfigurerar platsinställningar för ett nytt WMS-aktiverat lagerställe (ett lagerställe som använder avancerade lagerstyrningsprocesser).</span><span class="sxs-lookup"><span data-stu-id="0bab3-104">This guide shows you how to configure the location setup for a new WMS-enabled warehouse (a warehouse that uses advanced warehouse management processes).</span></span> <span data-ttu-id="0bab3-105">Processen normalt utförs av en lagerchef.</span><span class="sxs-lookup"><span data-stu-id="0bab3-105">The process is typically done by a warehouse manager.</span></span> <span data-ttu-id="0bab3-106">Du kan köra den här guiden för demonstrationsföretaget USMF eller på dina egna data.</span><span class="sxs-lookup"><span data-stu-id="0bab3-106">You can run this guide in demo data company USMF or on your own data.</span></span> <span data-ttu-id="0bab3-107">En förutsättning är att du har konfigurerat minst en webbplats.</span><span class="sxs-lookup"><span data-stu-id="0bab3-107">A precondition is that you have at least one site configured.</span></span>


## <a name="create-a-new-warehouse"></a><span data-ttu-id="0bab3-108">Skapa ett nytt lagerställe</span><span class="sxs-lookup"><span data-stu-id="0bab3-108">Create a new warehouse</span></span>
1. <span data-ttu-id="0bab3-109">Gå till Lagerställen.</span><span class="sxs-lookup"><span data-stu-id="0bab3-109">Go to Warehouses.</span></span>
2. <span data-ttu-id="0bab3-110">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="0bab3-110">Click New.</span></span>
3. <span data-ttu-id="0bab3-111">Ange ett värde i fältet Lagerställe.</span><span class="sxs-lookup"><span data-stu-id="0bab3-111">In the Warehouse field, type a value.</span></span>
4. <span data-ttu-id="0bab3-112">Skriv ett värde i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="0bab3-112">In the Name field, type a value.</span></span>
5. <span data-ttu-id="0bab3-113">Ange ett värde i fältet Plats.</span><span class="sxs-lookup"><span data-stu-id="0bab3-113">In the Site field, type a value.</span></span>
6. <span data-ttu-id="0bab3-114">Visa eller dölj avsnittet Lagerställe.</span><span class="sxs-lookup"><span data-stu-id="0bab3-114">Expand or collapse the Warehouse section.</span></span>
7. <span data-ttu-id="0bab3-115">Välj alternativet Ja för Använd lagerstyrningsprocesser.</span><span class="sxs-lookup"><span data-stu-id="0bab3-115">Set the Use warehouse management processes option to Yes.</span></span>
    * <span data-ttu-id="0bab3-116">Den här inställningen gör det även möjligt att köra avancerade lagerprocesser med hjälp av lagerarbete och mobila enheter.</span><span class="sxs-lookup"><span data-stu-id="0bab3-116">This setting allows you to  run advanced warehousing processes using warehouse work and mobile devices.</span></span>  
8. <span data-ttu-id="0bab3-117">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="0bab3-117">Close the page.</span></span>

## <a name="define-a-location-format"></a><span data-ttu-id="0bab3-118">Definiera ett platsformat</span><span class="sxs-lookup"><span data-stu-id="0bab3-118">Define a location format</span></span>
1. <span data-ttu-id="0bab3-119">Gå till Platsformat.</span><span class="sxs-lookup"><span data-stu-id="0bab3-119">Go to Location formats.</span></span>
    * <span data-ttu-id="0bab3-120">Platsformat är ett namnhanteringssystem som används för att skapa unika och konsekventa unika namn för de olika platsbingepositioner som används inom ett lagerställe.</span><span class="sxs-lookup"><span data-stu-id="0bab3-120">Location formats are a naming-system used to create unique and consistent names for the different location bin positions used within a warehouse.</span></span> <span data-ttu-id="0bab3-121">Det kan vara praktiskt att använda avgränsare som en del av platsformatet om du vill göra det enklare att identifiera komponenter på platsen, till exempel gångnumret.</span><span class="sxs-lookup"><span data-stu-id="0bab3-121">It can be useful to use separators as part of the location format to make it easier to identify components of the location such as the aisle number.</span></span> <span data-ttu-id="0bab3-122">I det här exemplet ska vi skapa ett namn med fyra komponenter.</span><span class="sxs-lookup"><span data-stu-id="0bab3-122">In this example, we’ll create a name with four components.</span></span> <span data-ttu-id="0bab3-123">Till exempel kan du använda gång, ställning, hylla och binge.</span><span class="sxs-lookup"><span data-stu-id="0bab3-123">For example, these could be aisle, rack, shelf, and bin.</span></span>  
2. <span data-ttu-id="0bab3-124">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="0bab3-124">Click New.</span></span>
3. <span data-ttu-id="0bab3-125">I fältet Platsformat, skriv ett värde.</span><span class="sxs-lookup"><span data-stu-id="0bab3-125">In the Location format field, type a value.</span></span>
4. <span data-ttu-id="0bab3-126">Skriv ett värde i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="0bab3-126">In the Name field, type a value.</span></span>
5. <span data-ttu-id="0bab3-127">I fältet Segmentbeskrivning, skriv ett värde.</span><span class="sxs-lookup"><span data-stu-id="0bab3-127">In the Segment description field, type a value.</span></span>
    * <span data-ttu-id="0bab3-128">Den beskriver vad den första komponenten i ett platsnamn representerar.</span><span class="sxs-lookup"><span data-stu-id="0bab3-128">This describes what the first component of the location name represents.</span></span> <span data-ttu-id="0bab3-129">Till exempel kan det vara Gång.</span><span class="sxs-lookup"><span data-stu-id="0bab3-129">For example, it could be Aisle.</span></span>  
6. <span data-ttu-id="0bab3-130">I fältet Längd, ange ett tal.</span><span class="sxs-lookup"><span data-stu-id="0bab3-130">In the Length field, enter a number.</span></span>
    * <span data-ttu-id="0bab3-131">Detta avgör hur många tecken den här delen av platsnamnet måste ha.</span><span class="sxs-lookup"><span data-stu-id="0bab3-131">This determines how many characters this part of the location name must have.</span></span> <span data-ttu-id="0bab3-132">Observera att summan av alla komponenter i namnet, inklusive avgränsarna, inte får överstiga 10 tecken.</span><span class="sxs-lookup"><span data-stu-id="0bab3-132">Note that the total of all components in the name, including the separators, cannot exceed 10 characters.</span></span>  
7. <span data-ttu-id="0bab3-133">I fältet Avgränsare, ange ett värde.</span><span class="sxs-lookup"><span data-stu-id="0bab3-133">In the Separator field, type a value.</span></span>
    * <span data-ttu-id="0bab3-134">Detta avgör vilket tecken eller vilken symbol som används mellan den första och andra komponenten i namnet.</span><span class="sxs-lookup"><span data-stu-id="0bab3-134">This determines which character or symbol is used between the first and second component of the name.</span></span>  
8. <span data-ttu-id="0bab3-135">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="0bab3-135">Click New.</span></span>
9. <span data-ttu-id="0bab3-136">I fältet Segmentbeskrivning, skriv ett värde.</span><span class="sxs-lookup"><span data-stu-id="0bab3-136">In the Segment description field, type a value.</span></span>
10. <span data-ttu-id="0bab3-137">I fältet Längd, ange ett tal.</span><span class="sxs-lookup"><span data-stu-id="0bab3-137">In the Length field, enter a number.</span></span>
11. <span data-ttu-id="0bab3-138">I fältet Avgränsare, ange ett värde.</span><span class="sxs-lookup"><span data-stu-id="0bab3-138">In the Separator field, type a value.</span></span>
12. <span data-ttu-id="0bab3-139">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="0bab3-139">Click New.</span></span>
13. <span data-ttu-id="0bab3-140">I fältet Segmentbeskrivning, skriv ett värde.</span><span class="sxs-lookup"><span data-stu-id="0bab3-140">In the Segment description field, type a value.</span></span>
14. <span data-ttu-id="0bab3-141">I fältet Längd, ange ett tal.</span><span class="sxs-lookup"><span data-stu-id="0bab3-141">In the Length field, enter a number.</span></span>
15. <span data-ttu-id="0bab3-142">I fältet Avgränsare, ange ett värde.</span><span class="sxs-lookup"><span data-stu-id="0bab3-142">In the Separator field, type a value.</span></span>
16. <span data-ttu-id="0bab3-143">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="0bab3-143">Click New.</span></span>
17. <span data-ttu-id="0bab3-144">I fältet Segmentbeskrivning, skriv ett värde.</span><span class="sxs-lookup"><span data-stu-id="0bab3-144">In the Segment description field, type a value.</span></span>
18. <span data-ttu-id="0bab3-145">I fältet Längd, ange ett tal.</span><span class="sxs-lookup"><span data-stu-id="0bab3-145">In the Length field, enter a number.</span></span>
19. <span data-ttu-id="0bab3-146">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="0bab3-146">Click Save.</span></span>
20. <span data-ttu-id="0bab3-147">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="0bab3-147">Close the page.</span></span>

## <a name="define-location-types"></a><span data-ttu-id="0bab3-148">Definiera platstyper</span><span class="sxs-lookup"><span data-stu-id="0bab3-148">Define location types</span></span>
1. <span data-ttu-id="0bab3-149">Gå till Platstyper.</span><span class="sxs-lookup"><span data-stu-id="0bab3-149">Go to Location types.</span></span>
    * <span data-ttu-id="0bab3-150">Platstyper kan användas som filtreringsalternativ för att styra de olika lagerstyrningsprocesserna.</span><span class="sxs-lookup"><span data-stu-id="0bab3-150">Location types can be used as filtering options to control the different warehouse management processes.</span></span> <span data-ttu-id="0bab3-151">Som minst måste du skapa platstyper för mellanlagring och slutlig leverans för att definiera den utgående lagerhanteringsprocessen.</span><span class="sxs-lookup"><span data-stu-id="0bab3-151">As a minimum, you need to create staging and final shipping location types in order to define the outbound warehouse management process.</span></span>  
2. <span data-ttu-id="0bab3-152">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="0bab3-152">Click New.</span></span>
3. <span data-ttu-id="0bab3-153">Skriv ett värde i fältet Platstyp.</span><span class="sxs-lookup"><span data-stu-id="0bab3-153">In the Location type field, type a value.</span></span>
4. <span data-ttu-id="0bab3-154">Ange ett värde i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="0bab3-154">In the Description field, type a value.</span></span>
5. <span data-ttu-id="0bab3-155">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="0bab3-155">Close the page.</span></span>

## <a name="define-location-profile"></a><span data-ttu-id="0bab3-156">Definiera platsprofil</span><span class="sxs-lookup"><span data-stu-id="0bab3-156">Define location profile</span></span>
1. <span data-ttu-id="0bab3-157">Gå till Platsprofiler.</span><span class="sxs-lookup"><span data-stu-id="0bab3-157">Go to Location profiles.</span></span>
    * <span data-ttu-id="0bab3-158">Definitionen av platsprofiler är mycket viktig.</span><span class="sxs-lookup"><span data-stu-id="0bab3-158">The definition of location profiles is very important.</span></span> <span data-ttu-id="0bab3-159">Grupperad platskapacitet kan kontrolleras här, men även policyer som är relaterade till vilket lager som lagras, och hur det lagras.</span><span class="sxs-lookup"><span data-stu-id="0bab3-159">Grouped locations capacity can be controlled here, as well as the policies related to what inventory gets stored, and how it is stored.</span></span> <span data-ttu-id="0bab3-160">Platsprofiler kan användas som filtreringsalternativ för att styra de olika lagerstyrningsprocesserna.</span><span class="sxs-lookup"><span data-stu-id="0bab3-160">Location profiles can be used as filtering options to control the different warehouse management processes.</span></span> <span data-ttu-id="0bab3-161">Som minimum måste du skapa en användarplatsprofil för att kunna aktivera lagerstyrningsprocesserna.</span><span class="sxs-lookup"><span data-stu-id="0bab3-161">As a minimum, you must create a user location profile in order to enable the warehouse management processes.</span></span>  
2. <span data-ttu-id="0bab3-162">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="0bab3-162">Click New.</span></span>
3. <span data-ttu-id="0bab3-163">Skriv ett värde i fältet Platsprofil-ID.</span><span class="sxs-lookup"><span data-stu-id="0bab3-163">In the Location profile ID field, type a value.</span></span>
4. <span data-ttu-id="0bab3-164">Skriv ett värde i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="0bab3-164">In the Name field, type a value.</span></span>
5. <span data-ttu-id="0bab3-165">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Platsformat.</span><span class="sxs-lookup"><span data-stu-id="0bab3-165">In the Location format field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="0bab3-166">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="0bab3-166">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="0bab3-167">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="0bab3-167">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="0bab3-168">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Platstyp.</span><span class="sxs-lookup"><span data-stu-id="0bab3-168">In the Location type field, click the drop-down button to open the lookup.</span></span>
9. <span data-ttu-id="0bab3-169">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="0bab3-169">In the list, find and select the desired record.</span></span>
10. <span data-ttu-id="0bab3-170">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="0bab3-170">In the list, click the link in the selected row.</span></span>
11. <span data-ttu-id="0bab3-171">Markera eller avmarkera kryssrutan Allow mixed inventory statuses.</span><span class="sxs-lookup"><span data-stu-id="0bab3-171">Select or clear the Allow mixed  inventory statuses check box.</span></span>
    * <span data-ttu-id="0bab3-172">Aktivera det här alternativet om du vill tillåta blandade lagerstatusar på de platser som ska grupperas efter den här platsprofilen.</span><span class="sxs-lookup"><span data-stu-id="0bab3-172">Enable this option if you want to allow mixed inventory status values in the locations that are going to be grouped by this location profile.</span></span>  
12. <span data-ttu-id="0bab3-173">Markera eller avmarkera kryssrutan Åsidosättningsregler för batchdagar.</span><span class="sxs-lookup"><span data-stu-id="0bab3-173">Select or clear the Override rules for batch days check box.</span></span>
    * <span data-ttu-id="0bab3-174">Aktivera det här alternativet för att åsidosätta regeln för hur många dagar lagerbatchutgångsdatumen kan skilja sig åt, för att tillåta blandning av lagerbatchar som inte uppfyller den här regeln.</span><span class="sxs-lookup"><span data-stu-id="0bab3-174">Enable this option to override the rule for how many days the inventory batch expiration dates can differ, to allow mixing of inventory batches that don’t obeying this rule.</span></span>  
13. <span data-ttu-id="0bab3-175">Markera eller avmarkera kryssrutan Tillåt rullande inventering.</span><span class="sxs-lookup"><span data-stu-id="0bab3-175">Select or clear the Allow cycle counting check box.</span></span>
    * <span data-ttu-id="0bab3-176">Aktivera det här alternativet om du vill tillåta bearbetning av rullande inventering på alla de platser som ska grupperas efter den här platsprofilen.</span><span class="sxs-lookup"><span data-stu-id="0bab3-176">Enable this option to allow cycle counting processing in all the locations that are going to be grouped by this location profile.</span></span>  
14. <span data-ttu-id="0bab3-177">Visa eller dölj avsnittet Dimensioner.</span><span class="sxs-lookup"><span data-stu-id="0bab3-177">Expand or collapse the Dimensions section.</span></span>
    * <span data-ttu-id="0bab3-178">Fliken Dimensioner gör det möjligt att definiera parametrar och metoder för att aktivera exakta beräkningar av kapacitetsbeläggningen på varje plats.</span><span class="sxs-lookup"><span data-stu-id="0bab3-178">The Dimensions tab allows you to define parameters and methods to enable precise calculations of the load capacity within each of the locations.</span></span>  
15. <span data-ttu-id="0bab3-179">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="0bab3-179">Close the page.</span></span>

## <a name="enable-warehouse-management-parameters"></a><span data-ttu-id="0bab3-180">Aktivera parametrar för lagerstyrning</span><span class="sxs-lookup"><span data-stu-id="0bab3-180">Enable warehouse management parameters</span></span>
1. <span data-ttu-id="0bab3-181">Gå till Parametrar för lagerstyrning.</span><span class="sxs-lookup"><span data-stu-id="0bab3-181">Go to Warehouse management parameters.</span></span>
    * <span data-ttu-id="0bab3-182">För att kunna bearbeta lagerarbete måste du ange parametrar för användarens platsprofil för typen av mellanlagringsplats och den slutliga leveransplatsen. Så snart som den utgående processen avslutas vid typen för den slutliga leveransplatsen som du definierar, de relaterade utgående transaktionerna uppdateras till Plockad.</span><span class="sxs-lookup"><span data-stu-id="0bab3-182">To be able to process warehouse work, you need to set parameters for the user location profile the staging location type, and the final shipping location type  As soon as the outbound process ends at the final shipping location type that you define, the related outbound transactions will be updated to ‘Picked’.</span></span>  
2. <span data-ttu-id="0bab3-183">Visa eller dölj avsnittet Platsprofiler.</span><span class="sxs-lookup"><span data-stu-id="0bab3-183">Expand or collapse the Location profiles section.</span></span>
3. <span data-ttu-id="0bab3-184">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Användarplats.</span><span class="sxs-lookup"><span data-stu-id="0bab3-184">In the User location field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="0bab3-185">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="0bab3-185">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="0bab3-186">Visa eller dölj avsnittet Platstyper.</span><span class="sxs-lookup"><span data-stu-id="0bab3-186">Expand or collapse the Location types section.</span></span>
6. <span data-ttu-id="0bab3-187">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Typ av mellanlagringsplats.</span><span class="sxs-lookup"><span data-stu-id="0bab3-187">In the Staging location type field, click the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="0bab3-188">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="0bab3-188">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="0bab3-189">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Typ av slutlig leveransplats.</span><span class="sxs-lookup"><span data-stu-id="0bab3-189">In the Final shipping location type field, click the drop-down button to open the lookup.</span></span>
9. <span data-ttu-id="0bab3-190">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="0bab3-190">In the list, click the link in the selected row.</span></span>
10. <span data-ttu-id="0bab3-191">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="0bab3-191">Close the page.</span></span>

## <a name="define-warehouse-zone-groups"></a><span data-ttu-id="0bab3-192">Definiera grupper för lagerställezoner</span><span class="sxs-lookup"><span data-stu-id="0bab3-192">Define warehouse zone groups</span></span>
1. <span data-ttu-id="0bab3-193">Gå till Grupper - lagerställezoner.</span><span class="sxs-lookup"><span data-stu-id="0bab3-193">Go to Warehouse zone groups.</span></span>
    * <span data-ttu-id="0bab3-194">Lagerställezoner kan användas som filtreringsalternativ för att styra de olika lagerstyrningsprocesserna.</span><span class="sxs-lookup"><span data-stu-id="0bab3-194">Warehouse zones can be used as filters for options to control the different warehouse management processes.</span></span> <span data-ttu-id="0bab3-195">Du måste skapa en zongrupp innan du kan definiera en zon.</span><span class="sxs-lookup"><span data-stu-id="0bab3-195">You need to create a zone group before you can define a zone.</span></span>  
2. <span data-ttu-id="0bab3-196">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="0bab3-196">Click New.</span></span>
3. <span data-ttu-id="0bab3-197">Skriv ett värde i fältet Zongrupps-ID.</span><span class="sxs-lookup"><span data-stu-id="0bab3-197">In the Zone group ID field, type a value.</span></span>
4. <span data-ttu-id="0bab3-198">Skriv ett värde i fältet Zongruppnamn.</span><span class="sxs-lookup"><span data-stu-id="0bab3-198">In the Zone group name field, type a value.</span></span>
5. <span data-ttu-id="0bab3-199">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="0bab3-199">Close the page.</span></span>

## <a name="define-warehouse-zones"></a><span data-ttu-id="0bab3-200">Definiera lagerställezoner</span><span class="sxs-lookup"><span data-stu-id="0bab3-200">Define Warehouse zones</span></span>
1. <span data-ttu-id="0bab3-201">Gå till Zoner.</span><span class="sxs-lookup"><span data-stu-id="0bab3-201">Go to Zones.</span></span>
2. <span data-ttu-id="0bab3-202">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="0bab3-202">Click New.</span></span>
3. <span data-ttu-id="0bab3-203">Skriv ett värde i fältet Zon-ID.</span><span class="sxs-lookup"><span data-stu-id="0bab3-203">In the Zone ID field, type a value.</span></span>
4. <span data-ttu-id="0bab3-204">Skriv ett värde i fältet Zonnamn.</span><span class="sxs-lookup"><span data-stu-id="0bab3-204">In the Zone name field, type a value.</span></span>
5. <span data-ttu-id="0bab3-205">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Zongrupps-ID.</span><span class="sxs-lookup"><span data-stu-id="0bab3-205">In the Zone group ID field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="0bab3-206">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="0bab3-206">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="0bab3-207">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="0bab3-207">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="0bab3-208">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="0bab3-208">Close the page.</span></span>

## <a name="create-locations-using-the-location-setup-wizard"></a><span data-ttu-id="0bab3-209">Skapa platser med hjälp av guiden för platsinställning</span><span class="sxs-lookup"><span data-stu-id="0bab3-209">Create locations using the Location setup wizard</span></span>
1. <span data-ttu-id="0bab3-210">Gå till Guide för platsinställning.</span><span class="sxs-lookup"><span data-stu-id="0bab3-210">Go to Location setup wizard.</span></span>
2. <span data-ttu-id="0bab3-211">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Lagerställe.</span><span class="sxs-lookup"><span data-stu-id="0bab3-211">In the Warehouse field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="0bab3-212">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="0bab3-212">In the list, find and select the desired record.</span></span>
4. <span data-ttu-id="0bab3-213">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="0bab3-213">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="0bab3-214">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Zon-ID.</span><span class="sxs-lookup"><span data-stu-id="0bab3-214">In the Zone ID field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="0bab3-215">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="0bab3-215">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="0bab3-216">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="0bab3-216">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="0bab3-217">I fältet Platsprofil-ID öppnar du sökningen genom att klicka på den nedrullningsbara knappen.</span><span class="sxs-lookup"><span data-stu-id="0bab3-217">In the Location profile ID field, click the drop-down button to open the lookup.</span></span>
9. <span data-ttu-id="0bab3-218">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="0bab3-218">In the list, find and select the desired record.</span></span>
10. <span data-ttu-id="0bab3-219">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="0bab3-219">In the list, click the link in the selected row.</span></span>
11. <span data-ttu-id="0bab3-220">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="0bab3-220">In the list, mark the selected row.</span></span>
12. <span data-ttu-id="0bab3-221">Ange ett nummer i fältet Från nummer.</span><span class="sxs-lookup"><span data-stu-id="0bab3-221">In the From number field, enter a number.</span></span>
    * <span data-ttu-id="0bab3-222">Fälten Från nummer och Till nummer definierar hur många platser som ska skapas.</span><span class="sxs-lookup"><span data-stu-id="0bab3-222">The From number and To number fields define how many locations will be created.</span></span> <span data-ttu-id="0bab3-223">Om du till exempel ställer in Från nummer till 1 och Till nummer till 3 för alla fyra raderna i platsformatet skapas 81 platser (3 × 3 × 3 × 3).</span><span class="sxs-lookup"><span data-stu-id="0bab3-223">For example, if you set From number to 1 and To number to 3 for all four lines in the location format, 81 locations will be created (3x3x3x3).</span></span>  
13. <span data-ttu-id="0bab3-224">Ange ett nummer i fältet Till nummer.</span><span class="sxs-lookup"><span data-stu-id="0bab3-224">In the To number field, enter a number.</span></span>
14. <span data-ttu-id="0bab3-225">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="0bab3-225">In the list, find and select the desired record.</span></span>
15. <span data-ttu-id="0bab3-226">Ange ett nummer i fältet Från nummer.</span><span class="sxs-lookup"><span data-stu-id="0bab3-226">In the From number field, enter a number.</span></span>
16. <span data-ttu-id="0bab3-227">Ange ett nummer i fältet Till nummer.</span><span class="sxs-lookup"><span data-stu-id="0bab3-227">In the To number field, enter a number.</span></span>
17. <span data-ttu-id="0bab3-228">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="0bab3-228">In the list, find and select the desired record.</span></span>
18. <span data-ttu-id="0bab3-229">Ange ett nummer i fältet Från nummer.</span><span class="sxs-lookup"><span data-stu-id="0bab3-229">In the From number field, enter a number.</span></span>
19. <span data-ttu-id="0bab3-230">Ange ett nummer i fältet Till nummer.</span><span class="sxs-lookup"><span data-stu-id="0bab3-230">In the To number field, enter a number.</span></span>
20. <span data-ttu-id="0bab3-231">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="0bab3-231">In the list, find and select the desired record.</span></span>
21. <span data-ttu-id="0bab3-232">Ange ett nummer i fältet Från nummer.</span><span class="sxs-lookup"><span data-stu-id="0bab3-232">In the From number field, enter a number.</span></span>
22. <span data-ttu-id="0bab3-233">Ange ett nummer i fältet Till nummer.</span><span class="sxs-lookup"><span data-stu-id="0bab3-233">In the To number field, enter a number.</span></span>
23. <span data-ttu-id="0bab3-234">Klicka på Skapa.</span><span class="sxs-lookup"><span data-stu-id="0bab3-234">Click Create.</span></span>

## <a name="create-locations-manually"></a><span data-ttu-id="0bab3-235">Skapa platser manuellt</span><span class="sxs-lookup"><span data-stu-id="0bab3-235">Create locations manually</span></span>
1. <span data-ttu-id="0bab3-236">Gå till Platser.</span><span class="sxs-lookup"><span data-stu-id="0bab3-236">Go to Locations.</span></span>
    * <span data-ttu-id="0bab3-237">Du kan enkelt skapa platser manuellt inom ett lagerställe.</span><span class="sxs-lookup"><span data-stu-id="0bab3-237">Manually creation of locations within a warehouse can easily be done.</span></span> <span data-ttu-id="0bab3-238">Platsnamnet och platsprofil-ID:t är obligatoriska värden.</span><span class="sxs-lookup"><span data-stu-id="0bab3-238">The location name and the Location profile ID are mandatory values.</span></span>  
2. <span data-ttu-id="0bab3-239">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="0bab3-239">Click New.</span></span>
3. <span data-ttu-id="0bab3-240">Ange ett värde i fältet Lagerställe.</span><span class="sxs-lookup"><span data-stu-id="0bab3-240">In the Warehouse field, type a value.</span></span>
4. <span data-ttu-id="0bab3-241">Skriv ett värde i fältet Plats.</span><span class="sxs-lookup"><span data-stu-id="0bab3-241">In the Location field, type a value.</span></span>
    * <span data-ttu-id="0bab3-242">Observera att du skapar en ny plats här, så du behöver skriva en nytt unikt namn snarare än välja ett befintligt.</span><span class="sxs-lookup"><span data-stu-id="0bab3-242">Note that you're creating a new location here, so you need to type a new unique name, rather than selecting an existing one.</span></span>  
5. <span data-ttu-id="0bab3-243">Skriv ett värde i fältet Platsprofil-ID.</span><span class="sxs-lookup"><span data-stu-id="0bab3-243">In the Location profile ID field, type a value.</span></span>
6. <span data-ttu-id="0bab3-244">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="0bab3-244">Close the page.</span></span>

## <a name="define-pack-size-categories"></a><span data-ttu-id="0bab3-245">Definiera kategorier för förpackningsstorlekar</span><span class="sxs-lookup"><span data-stu-id="0bab3-245">Define Pack size categories</span></span>
1. <span data-ttu-id="0bab3-246">Gå till Kategorier för packningsstorlek.</span><span class="sxs-lookup"><span data-stu-id="0bab3-246">Go to Pack size categories.</span></span>
    * <span data-ttu-id="0bab3-247">Kategorier av förpackningsstorlekar kan användas för att gruppera artiklar som har liknande fysiska förpackningsstorlekar.</span><span class="sxs-lookup"><span data-stu-id="0bab3-247">Pack size categories can be used to group items that have similar physical packing sizes.</span></span> <span data-ttu-id="0bab3-248">I det här exemplet används kategorin för förpackningsstorlek för att styra kapaciteten på plockningsplatserna inom en viss zon på lagerstället.</span><span class="sxs-lookup"><span data-stu-id="0bab3-248">In this example the pack size category will be used to control the capacity at the picking locations within a specific zone of the warehouse.</span></span> <span data-ttu-id="0bab3-249">Observera att packstorlekskategori-ID:t måste tilldelas den frisläppta produktenheten för att kunna användas som en del av bearbetningen av lagringsbegränsningar.</span><span class="sxs-lookup"><span data-stu-id="0bab3-249">Please note that the pack size category ID must be assigned to the released product entity in order to be used as part of the stocking limits processing.</span></span>  
2. <span data-ttu-id="0bab3-250">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="0bab3-250">Click New.</span></span>
3. <span data-ttu-id="0bab3-251">Skriv ett värde i fältet Kategori-ID för packningsstorlek.</span><span class="sxs-lookup"><span data-stu-id="0bab3-251">In the Pack size category ID field, type a value.</span></span>
4. <span data-ttu-id="0bab3-252">Skriv ett värde i fältet Kategorinamn för packningsstorlek.</span><span class="sxs-lookup"><span data-stu-id="0bab3-252">In the Pack size category name field, type a value.</span></span>
5. <span data-ttu-id="0bab3-253">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="0bab3-253">Close the page.</span></span>

## <a name="define-location-stocking-limits"></a><span data-ttu-id="0bab3-254">Definiera lagerbegränsningar för lagerställen</span><span class="sxs-lookup"><span data-stu-id="0bab3-254">Define location stocking limits</span></span>
1. <span data-ttu-id="0bab3-255">Gå till Lagringsbegränsningsplats.</span><span class="sxs-lookup"><span data-stu-id="0bab3-255">Go to Location stocking limits.</span></span>
    * <span data-ttu-id="0bab3-256">Lagringsbegränsningsplatser hjälper till att kontrollera att arbetet inte skapas för att begära att lagret ska infogas på en plats som inte har den fysiska lagringsmöjligheten.</span><span class="sxs-lookup"><span data-stu-id="0bab3-256">Location stocking limits help to make sure that work isn't created to request that inventory to be put in a location that doesn't have the physical capacity to carry the inventory.</span></span>  
2. <span data-ttu-id="0bab3-257">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="0bab3-257">Click New.</span></span>
3. <span data-ttu-id="0bab3-258">Ange ett värde i fältet Lagerställe.</span><span class="sxs-lookup"><span data-stu-id="0bab3-258">In the Warehouse field, type a value.</span></span>
4. <span data-ttu-id="0bab3-259">Skriv ett värde i fältet Platsprofil-ID.</span><span class="sxs-lookup"><span data-stu-id="0bab3-259">In the Location profile ID field, type a value.</span></span>
5. <span data-ttu-id="0bab3-260">Skriv ett värde i fältet Kategori-ID för packningsstorlek.</span><span class="sxs-lookup"><span data-stu-id="0bab3-260">In the Pack size category ID field, type a value.</span></span>
6. <span data-ttu-id="0bab3-261">Ange ett tal i fältet Kvantitet.</span><span class="sxs-lookup"><span data-stu-id="0bab3-261">In the Quantity field, enter a number.</span></span>
7. <span data-ttu-id="0bab3-262">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="0bab3-262">Click Save.</span></span>
8. <span data-ttu-id="0bab3-263">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="0bab3-263">Close the page.</span></span>

## <a name="define-fixed-picking-locations"></a><span data-ttu-id="0bab3-264">Definiera fasta plockplatser</span><span class="sxs-lookup"><span data-stu-id="0bab3-264">Define fixed picking locations</span></span>
1. <span data-ttu-id="0bab3-265">Gå till Fasta lagerplatser.</span><span class="sxs-lookup"><span data-stu-id="0bab3-265">Go to Fixed locations.</span></span>
    * <span data-ttu-id="0bab3-266">Du kan definiera platserna som ska användas per produkt eller per produktvariant.</span><span class="sxs-lookup"><span data-stu-id="0bab3-266">You can define the locations to be used per product or per product variant.</span></span> <span data-ttu-id="0bab3-267">Det är möjligt att skapa flera fasta lagerplatser för samma produkt inom samma lagerställe.</span><span class="sxs-lookup"><span data-stu-id="0bab3-267">It is possible to create multiple fixed locations for the same product within the same warehouse.</span></span>  
2. <span data-ttu-id="0bab3-268">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="0bab3-268">Click New.</span></span>
3. <span data-ttu-id="0bab3-269">Skriv ett värde i fältet Artikelnummer.</span><span class="sxs-lookup"><span data-stu-id="0bab3-269">In the Item number field, type a value.</span></span>
4. <span data-ttu-id="0bab3-270">Ange ett värde i fältet Lagerställe.</span><span class="sxs-lookup"><span data-stu-id="0bab3-270">In the Warehouse field, type a value.</span></span>
5. <span data-ttu-id="0bab3-271">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Plats.</span><span class="sxs-lookup"><span data-stu-id="0bab3-271">In the Location field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="0bab3-272">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="0bab3-272">In the list, click the link in the selected row.</span></span>
7. <span data-ttu-id="0bab3-273">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="0bab3-273">Close the page.</span></span>

