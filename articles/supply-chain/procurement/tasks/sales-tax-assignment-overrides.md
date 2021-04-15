---
title: Momstilldelning och åsidosättningar
description: I den här proceduren visas hur du tilldelar momsgrupper till handelskanaler.
author: kamaybac
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: RetailStoreTable, RetailTaxOverrideCode, RetailTaxOverrideGroup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: dabourq
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 28d393dcf727eec7211f6092ea67de2b85359f1a
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5811952"
---
# <a name="sales-tax-assignment-and-overrides"></a><span data-ttu-id="101d8-103">Momstilldelning och åsidosättningar</span><span class="sxs-lookup"><span data-stu-id="101d8-103">Sales tax assignment and overrides</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="101d8-104">I den här proceduren visas hur du tilldelar momsgrupper till handelskanaler.</span><span class="sxs-lookup"><span data-stu-id="101d8-104">This procedure demonstrates how to assign sales tax groups to commerce channels.</span></span> <span data-ttu-id="101d8-105">Den går också igenom processen att skapa en ny momsåsidosättning och tilldela den till en befintlig momsåsidosättningsgrupp.</span><span class="sxs-lookup"><span data-stu-id="101d8-105">It also walks through the process of creating a new sales tax override and assigning it to an existing sales tax override group.</span></span> <span data-ttu-id="101d8-106">I proceduren används demonstrationsföretaget USRT.</span><span class="sxs-lookup"><span data-stu-id="101d8-106">This procedure uses the USRT company in demo data.</span></span>

1. <span data-ttu-id="101d8-107">Gå till Butik och handel > Kanaler > Butiker >Alla butiker.</span><span class="sxs-lookup"><span data-stu-id="101d8-107">Go to Retail and Commerce > Channels > Stores > All stores.</span></span>
2. <span data-ttu-id="101d8-108">Klicka på länken kanal-ID för "Houston" i listan.</span><span class="sxs-lookup"><span data-stu-id="101d8-108">In the list, click the Channel ID link for "Houston."</span></span>
3. <span data-ttu-id="101d8-109">Klicka på Redigera.</span><span class="sxs-lookup"><span data-stu-id="101d8-109">Click Edit.</span></span>
    * <span data-ttu-id="101d8-110">Fältet "Momsgrupp" innehåller listan med momsgrupper för det aktuella företaget.</span><span class="sxs-lookup"><span data-stu-id="101d8-110">The "Sales tax group" field contains the list of sales tax groups for the current company.</span></span> <span data-ttu-id="101d8-111">Den aktuella tilldelade gruppen är en allmän ”Texas”-momsgrupp.</span><span class="sxs-lookup"><span data-stu-id="101d8-111">The currently assigned group is a generic "Texas" sales tax group.</span></span> <span data-ttu-id="101d8-112">Det finns även momsgrupper för ”Washington” och ”Washington King County”.</span><span class="sxs-lookup"><span data-stu-id="101d8-112">There are also sales tax groups for "Washington" and "Washington, King County."</span></span> <span data-ttu-id="101d8-113">Momsgrupper kan inkludera tillämpliga skatter för flera kommuner.</span><span class="sxs-lookup"><span data-stu-id="101d8-113">Sales tax groups can include applicable taxes for multiple municipalities.</span></span>  
    * <span data-ttu-id="101d8-114">I fältet moms ”Åsidosätt moms" kan momsåsidosättgrupper mappas till kanalen.</span><span class="sxs-lookup"><span data-stu-id="101d8-114">The "Sales tax override" field is where sales tax override groups can be mapped to the channel.</span></span> <span data-ttu-id="101d8-115">Momsåsidosättgrupper kan användas till att gruppera momsåsidosättningsgrupper som arbetar för flera butiker.</span><span class="sxs-lookup"><span data-stu-id="101d8-115">Sales tax override groups can be used to group together sales tax overrides that work for multiple stores.</span></span> <span data-ttu-id="101d8-116">Snarare än att manuellt tilldela en momsåsidosättning i taget kan gruppen skapas och tilldelas direkt till kanalerna om du vill spara tid.</span><span class="sxs-lookup"><span data-stu-id="101d8-116">Rather than manually assigning sales tax overrides one by one, the group can be created and assigned directly to the channels to save time.</span></span>  
4. <span data-ttu-id="101d8-117">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="101d8-117">Click Save.</span></span>
5. <span data-ttu-id="101d8-118">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="101d8-118">Close the page.</span></span>
6. <span data-ttu-id="101d8-119">Gå till Butik och handel > Kanalinställning > Moms > Momsåsidosättning.</span><span class="sxs-lookup"><span data-stu-id="101d8-119">Go to Retail and Commerce > Channel setup > Sales taxes > Sales tax overrides.</span></span>
7. <span data-ttu-id="101d8-120">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="101d8-120">Click New.</span></span>
8. <span data-ttu-id="101d8-121">Ange ett namn för den nya åsidosättningen i fältet Momsåsidosättning.</span><span class="sxs-lookup"><span data-stu-id="101d8-121">In the Sales tax override field, provide a name for your new override.</span></span>
9. <span data-ttu-id="101d8-122">I fältet Beskrivning anger du en kort beskrivning av åsidosättningen.</span><span class="sxs-lookup"><span data-stu-id="101d8-122">In the Description field, provide a description of the override.</span></span>
10. <span data-ttu-id="101d8-123">Ange status till "Aktivera".</span><span class="sxs-lookup"><span data-stu-id="101d8-123">Set the status to "Enable."</span></span>
11. <span data-ttu-id="101d8-124">Visa eller dölj avsnittet Åsidosättning.</span><span class="sxs-lookup"><span data-stu-id="101d8-124">Expand or collapse the Override section.</span></span>
12. <span data-ttu-id="101d8-125">Välj ett alternativ i fältet Typ.</span><span class="sxs-lookup"><span data-stu-id="101d8-125">In the Type field, select an option.</span></span>
    * <span data-ttu-id="101d8-126">Artikelmomsgrupper kan användas för att åsidosätta moms för specifika artiklar som tillhör gruppen.</span><span class="sxs-lookup"><span data-stu-id="101d8-126">Item sales tax groups can be used to override taxes for specific items that belong to the group.</span></span> <span data-ttu-id="101d8-127">Till exempel beskattas livsmedel vanligtvis annorlunda än fysiska varor och har troligen sin egen momsgrupp.</span><span class="sxs-lookup"><span data-stu-id="101d8-127">For example, food items are typically taxed differently from hard goods, and would likely have their own sales tax group.</span></span> <span data-ttu-id="101d8-128">Momsgrupper är grupper av moms som gäller för en viss kanal.</span><span class="sxs-lookup"><span data-stu-id="101d8-128">Sales tax groups are groups of taxes that are applicable to a particular channel.</span></span> <span data-ttu-id="101d8-129">Om en kanal till exempel säljer både till butik och mellan företag kan olika artikelmomsgrupper användas.</span><span class="sxs-lookup"><span data-stu-id="101d8-129">For example, if a channel sells both retail and business-to-business, different items sales tax groups may be used.</span></span> <span data-ttu-id="101d8-130">All tillämplig moms mappas till momsgruppen.</span><span class="sxs-lookup"><span data-stu-id="101d8-130">All the applicable taxes would be mapped to the sales tax group.</span></span>  
    * <span data-ttu-id="101d8-131">Nu kan du välja ”Från”- och ”Till”-moms eller ”Från momsgrupp" och "Till momsgrupp" för att skapa din momsåsidosättning.</span><span class="sxs-lookup"><span data-stu-id="101d8-131">Now you can select the "From" and "To" taxes or "From tax group" and "To tax group" to create your sales tax override.</span></span> <span data-ttu-id="101d8-132">Fältet "Från" anger den moms eller momsgrupp som ska åsidosättas.</span><span class="sxs-lookup"><span data-stu-id="101d8-132">The "From" field indicates the tax or tax group to be overridden.</span></span> <span data-ttu-id="101d8-133">Åsidosätta efter Artikelmomsgrupp ger olika alternativ än att åsidosätta efter momsgrupp.</span><span class="sxs-lookup"><span data-stu-id="101d8-133">Overriding by Item sales tax group provides different options than overriding by sales tax group.</span></span> <span data-ttu-id="101d8-134">Momsåsidosättning kan ställas in för att åsidosätta moms på hela transaktioner eller på särskilda rader i transaktionen.</span><span class="sxs-lookup"><span data-stu-id="101d8-134">Sales tax overrides can be set up to override taxes on entire transactions or on particular lines in the transaction.</span></span>  
13. <span data-ttu-id="101d8-135">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="101d8-135">Click Save.</span></span>
14. <span data-ttu-id="101d8-136">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="101d8-136">Close the page.</span></span>
15. <span data-ttu-id="101d8-137">Gå till Butik och handel > Kanalinställning > Moms > Momsåsidosättningsgrupper.</span><span class="sxs-lookup"><span data-stu-id="101d8-137">Go to Retail and Commerce > Channel setup > Sales taxes > Sales tax override groups.</span></span>
    * <span data-ttu-id="101d8-138">I detta steg tilldelar du den nyligen skapade momsåsidosättningen till den momsåsidosättgrupp som tilldelats Houston-kanalen.</span><span class="sxs-lookup"><span data-stu-id="101d8-138">In this step you will assigned the newly created sales tax override to the sales tax override group assigned to the Houston channel.</span></span>  
16. <span data-ttu-id="101d8-139">Klicka på Redigera.</span><span class="sxs-lookup"><span data-stu-id="101d8-139">Click Edit.</span></span>
17. <span data-ttu-id="101d8-140">Utöka eller komprimera avsnittet Inställningar.</span><span class="sxs-lookup"><span data-stu-id="101d8-140">Expand or collapse the Setup section.</span></span>
18. <span data-ttu-id="101d8-141">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="101d8-141">Click Add.</span></span>
19. <span data-ttu-id="101d8-142">I fältet Momsåsidosättning, öppna sökningen genom att klicka på den nedrullningsbara knappen.</span><span class="sxs-lookup"><span data-stu-id="101d8-142">In the Sales tax override field, click the drop-down button to open the lookup.</span></span>
20. <span data-ttu-id="101d8-143">Välj den tidigare skapade momsåsidosättningen i listan.</span><span class="sxs-lookup"><span data-stu-id="101d8-143">Select the previously created sales tax override from the list.</span></span>
21. <span data-ttu-id="101d8-144">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="101d8-144">In the list, click the link in the selected row.</span></span>
22. <span data-ttu-id="101d8-145">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="101d8-145">Click Save.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]