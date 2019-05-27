---
title: Momstilldelning och åsidosättningar
description: I den här proceduren visas hur du tilldelar momsgrupper till butikskanaler.
author: mkirknel
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: RetailStoreTable, RetailTaxOverrideCode, RetailTaxOverrideGroup
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a1907b0d0266eaa405ac2b92b40d6a2d310cf07b
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/15/2019
ms.locfileid: "1569947"
---
# <a name="sales-tax-assignment-and-overrides"></a><span data-ttu-id="0cc68-103">Momstilldelning och åsidosättningar</span><span class="sxs-lookup"><span data-stu-id="0cc68-103">Sales tax assignment and overrides</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="0cc68-104">I den här proceduren visas hur du tilldelar momsgrupper till butikskanaler.</span><span class="sxs-lookup"><span data-stu-id="0cc68-104">This procedure demonstrates how to assign sales tax groups to retail channels.</span></span> <span data-ttu-id="0cc68-105">Den går också igenom processen att skapa en ny momsåsidosättning och tilldela den till en befintlig momsåsidosättningsgrupp.</span><span class="sxs-lookup"><span data-stu-id="0cc68-105">It also walks through the process of creating a new sales tax override and assigning it to an existing sales tax override group.</span></span> <span data-ttu-id="0cc68-106">Den här uppgiften</span><span class="sxs-lookup"><span data-stu-id="0cc68-106">This procedure</span></span>

<span data-ttu-id="0cc68-107">använder sig av demonstrationsföretaget USRT.</span><span class="sxs-lookup"><span data-stu-id="0cc68-107">uses the USRT company in demo data.</span></span>

1. <span data-ttu-id="0cc68-108">Gå till butik och handel > Kanaler > butiker > Alla butiker.</span><span class="sxs-lookup"><span data-stu-id="0cc68-108">Go to Retail and commerce > Channels > Retail stores > All retail stores.</span></span>
2. <span data-ttu-id="0cc68-109">Klicka på länken Butikskanal-ID för "Houston" i listan.</span><span class="sxs-lookup"><span data-stu-id="0cc68-109">In the list, click the Retail Channel ID link for "Houston."</span></span>
3. <span data-ttu-id="0cc68-110">Klicka på Redigera.</span><span class="sxs-lookup"><span data-stu-id="0cc68-110">Click Edit.</span></span>
    * <span data-ttu-id="0cc68-111">Fältet "Momsgrupp" innehåller listan med momsgrupper för det aktuella företaget.</span><span class="sxs-lookup"><span data-stu-id="0cc68-111">The "Sales tax group" field contains the list of sales tax groups for the current company.</span></span> <span data-ttu-id="0cc68-112">Den aktuella tilldelade gruppen är en allmän ”Texas”-momsgrupp.</span><span class="sxs-lookup"><span data-stu-id="0cc68-112">The currently assigned group is a generic "Texas" sales tax group.</span></span> <span data-ttu-id="0cc68-113">Det finns även momsgrupper för ”Washington” och ”Washington King County”.</span><span class="sxs-lookup"><span data-stu-id="0cc68-113">There are also sales tax groups for "Washington" and "Washington, King County."</span></span> <span data-ttu-id="0cc68-114">Momsgrupper kan inkludera tillämpliga skatter för flera kommuner.</span><span class="sxs-lookup"><span data-stu-id="0cc68-114">Sales tax groups can include applicable taxes for multiple municipalities.</span></span>  
    * <span data-ttu-id="0cc68-115">I fältet moms ”Åsidosätt moms" kan momsåsidosättgrupper mappas till kanalen.</span><span class="sxs-lookup"><span data-stu-id="0cc68-115">The "Sales tax override" field is where sales tax override groups can be mapped to the channel.</span></span> <span data-ttu-id="0cc68-116">Momsåsidosättgrupper kan användas till att gruppera momsåsidosättningsgrupper som arbetar för flera butiker.</span><span class="sxs-lookup"><span data-stu-id="0cc68-116">Sales tax override groups can be used to group together sales tax overrides that work for multiple stores.</span></span> <span data-ttu-id="0cc68-117">Snarare än att manuellt tilldela en momsåsidosättning i taget kan gruppen skapas och tilldelas direkt till kanalerna om du vill spara tid.</span><span class="sxs-lookup"><span data-stu-id="0cc68-117">Rather than manually assigning sales tax overrides one by one, the group can be created and assigned directly to the channels to save time.</span></span>  
4. <span data-ttu-id="0cc68-118">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="0cc68-118">Click Save.</span></span>
5. <span data-ttu-id="0cc68-119">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="0cc68-119">Close the page.</span></span>
6. <span data-ttu-id="0cc68-120">Gå till Butik och handel > Kanalinställning > Moms > Momsåsidosättning.</span><span class="sxs-lookup"><span data-stu-id="0cc68-120">Go to Retail and commerce > Channel setup > Sales taxes > Sales tax overrides.</span></span>
7. <span data-ttu-id="0cc68-121">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="0cc68-121">Click New.</span></span>
8. <span data-ttu-id="0cc68-122">Ange ett namn för den nya åsidosättningen i fältet Momsåsidosättning.</span><span class="sxs-lookup"><span data-stu-id="0cc68-122">In the Sales tax override field, provide a name for your new override.</span></span>
9. <span data-ttu-id="0cc68-123">I fältet Beskrivning anger du en kort beskrivning av åsidosättningen.</span><span class="sxs-lookup"><span data-stu-id="0cc68-123">In the Description field, provide a description of the override.</span></span>
10. <span data-ttu-id="0cc68-124">Ange status till "Aktivera".</span><span class="sxs-lookup"><span data-stu-id="0cc68-124">Set the status to "Enable."</span></span>
11. <span data-ttu-id="0cc68-125">Visa eller dölj avsnittet Åsidosättning.</span><span class="sxs-lookup"><span data-stu-id="0cc68-125">Expand or collapse the Override section.</span></span>
12. <span data-ttu-id="0cc68-126">Välj ett alternativ i fältet Typ.</span><span class="sxs-lookup"><span data-stu-id="0cc68-126">In the Type field, select an option.</span></span>
    * <span data-ttu-id="0cc68-127">Artikelmomsgrupper kan användas för att åsidosätta moms för specifika artiklar som tillhör gruppen.</span><span class="sxs-lookup"><span data-stu-id="0cc68-127">Item sales tax groups can be used to override taxes for specific items that belong to the group.</span></span> <span data-ttu-id="0cc68-128">Till exempel beskattas livsmedel vanligtvis annorlunda än fysiska varor och har troligen sin egen momsgrupp.</span><span class="sxs-lookup"><span data-stu-id="0cc68-128">For example, food items are typically taxed differently from hard goods, and would likely have their own sales tax group.</span></span>     <span data-ttu-id="0cc68-129">Momsgrupper är grupper av moms som gäller för en viss kanal.</span><span class="sxs-lookup"><span data-stu-id="0cc68-129">Sales tax groups are groups of taxes that are applicable to a particular channel.</span></span> <span data-ttu-id="0cc68-130">Om en kanal till exempel säljer både till butik och mellan företag kan olika artikelmomsgrupper användas.</span><span class="sxs-lookup"><span data-stu-id="0cc68-130">For example, if a channel sells both retail and business-to-business, different items sales tax groups may be used.</span></span> <span data-ttu-id="0cc68-131">All tillämplig moms mappas till momsgruppen.</span><span class="sxs-lookup"><span data-stu-id="0cc68-131">All the applicable taxes would be mapped to the sales tax group.</span></span>  
    * <span data-ttu-id="0cc68-132">Nu kan du välja ”Från”- och ”Till”-moms eller ”Från momsgrupp" och "Till momsgrupp" för att skapa din momsåsidosättning.</span><span class="sxs-lookup"><span data-stu-id="0cc68-132">Now you can select the "From" and "To" taxes or "From tax group" and "To tax group" to create your sales tax override.</span></span>    <span data-ttu-id="0cc68-133">Fältet "Från" anger den moms eller momsgrupp som ska åsidosättas.</span><span class="sxs-lookup"><span data-stu-id="0cc68-133">The "From" field indicates the tax or tax group to be overridden.</span></span> <span data-ttu-id="0cc68-134">Åsidosätta efter Artikelmomsgrupp ger olika alternativ än att åsidosätta efter momsgrupp.</span><span class="sxs-lookup"><span data-stu-id="0cc68-134">Overriding by Item sales tax group provides different options than overriding by sales tax group.</span></span>    <span data-ttu-id="0cc68-135">Momsåsidosättning kan ställas in för att åsidosätta moms på hela transaktioner eller på särskilda rader i transaktionen.</span><span class="sxs-lookup"><span data-stu-id="0cc68-135">Sales tax overrides can be set up to override taxes on entire transactions or on particular lines in the transaction.</span></span>  
13. <span data-ttu-id="0cc68-136">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="0cc68-136">Click Save.</span></span>
14. <span data-ttu-id="0cc68-137">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="0cc68-137">Close the page.</span></span>
15. <span data-ttu-id="0cc68-138">Gå till Butik och handel > Kanalinställning > Moms > Momsåsidosättningsgrupper.</span><span class="sxs-lookup"><span data-stu-id="0cc68-138">Go to Retail and commerce > Channel setup > Sales taxes > Sales tax override groups.</span></span>
    * <span data-ttu-id="0cc68-139">I detta steg tilldelar du den nyligen skapade momsåsidosättningen till den momsåsidosättgrupp som tilldelats Houston-kanalen.</span><span class="sxs-lookup"><span data-stu-id="0cc68-139">In this step you will assigned the newly created sales tax override to the sales tax override group assigned to the Houston channel.</span></span>  
16. <span data-ttu-id="0cc68-140">Klicka på Redigera.</span><span class="sxs-lookup"><span data-stu-id="0cc68-140">Click Edit.</span></span>
17. <span data-ttu-id="0cc68-141">Utöka eller komprimera avsnittet Inställningar.</span><span class="sxs-lookup"><span data-stu-id="0cc68-141">Expand or collapse the Setup section.</span></span>
18. <span data-ttu-id="0cc68-142">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="0cc68-142">Click Add.</span></span>
19. <span data-ttu-id="0cc68-143">I fältet Momsåsidosättning, öppna sökningen genom att klicka på den nedrullningsbara knappen.</span><span class="sxs-lookup"><span data-stu-id="0cc68-143">In the Sales tax override field, click the drop-down button to open the lookup.</span></span>
20. <span data-ttu-id="0cc68-144">Välj den tidigare skapade momsåsidosättningen i listan.</span><span class="sxs-lookup"><span data-stu-id="0cc68-144">Select the previously created sales tax override from the list.</span></span>
21. <span data-ttu-id="0cc68-145">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="0cc68-145">In the list, click the link in the selected row.</span></span>
22. <span data-ttu-id="0cc68-146">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="0cc68-146">Click Save.</span></span>

