---
title: Konfigurera fält för mobilappen för distributionslagerhantering
description: Det här avsnittet beskriver hur du definierar och konfigurerar namn och prioriteringar av fälten som visas i mobilappen Hantering av distributionslager.
author: MarkusFogelberg
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSMobileAppField, WHSMobileAppFieldPriority
audience: Application User
ms.reviewer: kamaybac
ms.custom: 269434
ms.assetid: 6cf3d7da-29bb-4d3d-aaf5-544ca9cc2980
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: mafoge
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: bc224d3fd6cf5b111f61066202090f10ba4a7e8a
ms.sourcegitcommit: ff09736563d3cd2bc74c7664edd1767b218401cb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/04/2021
ms.locfileid: "6189260"
---
# <a name="configure-fields-for-the-warehouse-management-mobile-app"></a><span data-ttu-id="4b32f-103">Konfigurera fält för mobilappen för distributionslagerhantering</span><span class="sxs-lookup"><span data-stu-id="4b32f-103">Configure fields for the Warehouse Management mobile app</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="4b32f-104">Det här avsnittet beskriver hur du definierar och konfigurerar namn och prioriteringar av fälten som visas i mobilappen Hantering av distributionslager.</span><span class="sxs-lookup"><span data-stu-id="4b32f-104">This topic describes how to define and configure names and priorities of fields shown in the Warehouse Management mobile app.</span></span>

> [!NOTE]
> <span data-ttu-id="4b32f-105">Denna artikel gäller funktioner i lagerstyrningshanteringen.</span><span class="sxs-lookup"><span data-stu-id="4b32f-105">This topic applies to features in Warehouse management.</span></span> <span data-ttu-id="4b32f-106">Den gäller inte funktioner i lagerhanteringshanteringen.</span><span class="sxs-lookup"><span data-stu-id="4b32f-106">It doesn’t apply to features in Inventory management.</span></span> <span data-ttu-id="4b32f-107">Mobilappen Hantering av distributionslager är ett program som du kan använda för att utföra uppgifter på lagerstället.</span><span class="sxs-lookup"><span data-stu-id="4b32f-107">The Warehouse Management mobile app is an application that you can use to perform warehouse tasks.</span></span> <span data-ttu-id="4b32f-108">Du kan definiera och konfigurera de fältnamn som används i programmet, samt konfigurera prioriteringen bland de fältnamn som ska tilldelas.</span><span class="sxs-lookup"><span data-stu-id="4b32f-108">You can define and configure the field names that are used in the app, as well as configure the priority to which the field names should be assigned.</span></span> <span data-ttu-id="4b32f-109">Det här avsnittet förklarar hur du definierar och konfigurerar fältnamn och prioriteringar i mobilappen Hantering av distributionslager, samt hur dessa används.</span><span class="sxs-lookup"><span data-stu-id="4b32f-109">This topic explains how to define and configure these Warehouse Management mobile app field names and priorities, and how they are used.</span></span>

## <a name="configure-warehouse-app-field-names"></a><span data-ttu-id="4b32f-110">Konfigurera fältnamn i lagerställets program</span><span class="sxs-lookup"><span data-stu-id="4b32f-110">Configure warehouse app field names</span></span>

<span data-ttu-id="4b32f-111">När du använder Lagerstyrning på din mobila enhet kan du konfigurera hur metadata ska visas på enheten på sidan **Fältnamn i lagerställeprogram**.</span><span class="sxs-lookup"><span data-stu-id="4b32f-111">When you use Warehousing on your mobile device, you can configure how metadata should be displayed on your device on the **Warehouse app field names** page.</span></span> <span data-ttu-id="4b32f-112">Välj **Skapa standardinställning** i ett nytt företag för att skapa alla fältnamn som ska användas i lagerställets arbetsflöden för mobila enheter, och tilldela dem sedan ett föredraget inmatningsläge och en föredragen inmatningstyp.</span><span class="sxs-lookup"><span data-stu-id="4b32f-112">In a new company, select **Create default setup** to generate all field names that will be used in the warehouse mobile device workflows, and then assign a preferred input mode and input type to them.</span></span> <span data-ttu-id="4b32f-113">När du har genererat alla fältnamn väljer du in följande inmatningsalternativ.</span><span class="sxs-lookup"><span data-stu-id="4b32f-113">After you have generated all field names, you can select the following input options.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4b32f-114">Alternativ</span><span class="sxs-lookup"><span data-stu-id="4b32f-114">Option</span></span></th>
<th><span data-ttu-id="4b32f-115">beskrivning</span><span class="sxs-lookup"><span data-stu-id="4b32f-115">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="4b32f-116">Prioriterat indataläge</span><span class="sxs-lookup"><span data-stu-id="4b32f-116">Preferred input mode</span></span></td>
<td><span data-ttu-id="4b32f-117">Det här alternativet anger om ett skanningsfält eller ett fält för manuell inmatning bör visas för det valda fältnamnet.</span><span class="sxs-lookup"><span data-stu-id="4b32f-117">This option defines whether a scanning field or a manual entry input field should be shown for the selected field name.</span></span> <span data-ttu-id="4b32f-118">Detta är användbart för att skilja fälten åt, beroende på om du använder streckkoder för fältet.</span><span class="sxs-lookup"><span data-stu-id="4b32f-118">This is useful to distinguish fields depending on if barcodes are used for the field.</span></span> <span data-ttu-id="4b32f-119"><strong>Obs!</strong> För fältnamn med önskat inmatningsläge angivet som <strong>Skanning</strong> kan du ange information manuellt om streckkoden är skadad eller oläsbar.</span><span class="sxs-lookup"><span data-stu-id="4b32f-119"><strong>Note:</strong> For field names with preferred input mode set to <strong>Scanning</strong>, you can enter information manually if the barcode is unreadable or damaged.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="4b32f-120">Inmatningstyp</span><span class="sxs-lookup"><span data-stu-id="4b32f-120">Input type</span></span></td>
<td><span data-ttu-id="4b32f-121">Det här alternativet definierar vilken inmatningstyp som ska användas för det valda fältnamnet.</span><span class="sxs-lookup"><span data-stu-id="4b32f-121">This option defines what input type should be used for the selected field name.</span></span> <span data-ttu-id="4b32f-122">Det finns fyra alternativ:</span><span class="sxs-lookup"><span data-stu-id="4b32f-122">Four options are available:</span></span>
<ul>
<li><span data-ttu-id="4b32f-123"><strong>Urval</strong> - Innehåller en lista över tillgängliga alternativ.</span><span class="sxs-lookup"><span data-stu-id="4b32f-123"><strong>Selection</strong> - Contains a list of options to choose from.</span></span> <span data-ttu-id="4b32f-124">Fältnamn med det här alternativet kan inte redigeras.</span><span class="sxs-lookup"><span data-stu-id="4b32f-124">Field names with this option are not editable.</span></span></li>
<li><span data-ttu-id="4b32f-125"><strong>Datum</strong> - Fältnamn angivna som datum visar ett datumformat tillsammans med etiketten.</span><span class="sxs-lookup"><span data-stu-id="4b32f-125"><strong>Date</strong> - Field names specified as date will show a date format with the label.</span></span> <span data-ttu-id="4b32f-126">Detta hjälper lagerarbetare att se i vilket format datumet ska anges.</span><span class="sxs-lookup"><span data-stu-id="4b32f-126">This helps warehouse workers see in which format to enter the date.</span></span> <span data-ttu-id="4b32f-127">Fältnamn med det här alternativet kan inte redigeras.</span><span class="sxs-lookup"><span data-stu-id="4b32f-127">Field names with this option are not editable.</span></span></li>
<li><span data-ttu-id="4b32f-128"><strong>Alfa</strong> - Om detta alternativ väljs kommer enhetens tangentbord att användas när du anger information manuellt i appen.</span><span class="sxs-lookup"><span data-stu-id="4b32f-128"><strong>Alpha</strong> - If selected, the device keyboard will be used when entering information manually in the app.</span></span> <span data-ttu-id="4b32f-129">Tangentbordsupplevelsen kan ändras beroende på vilken enhet som används.</span><span class="sxs-lookup"><span data-stu-id="4b32f-129">The keyboard experience can be changed depending on which device is used.</span></span></li>
<li><span data-ttu-id="4b32f-130"><strong>Numerisk</strong> - Välj detta alternativ för fältnamn som endast använder numerisk inmatning om du vill visa ett numeriskt tangentbord tillsammans med inmatningsfältet stället för enhetens tangentbord.</span><span class="sxs-lookup"><span data-stu-id="4b32f-130"><strong>Numeric</strong> - For field names that use numeric input only, you can select this option to display a custom numeric keypad with the input field instead of the device keyboard.</span></span></li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="configure-warehouse-app-field-priority"></a><span data-ttu-id="4b32f-131">Konfigurera prioriteringsordningen för lagerställets programfält</span><span class="sxs-lookup"><span data-stu-id="4b32f-131">Configure warehouse app field priority</span></span>

<span data-ttu-id="4b32f-132">På sidan **Fältprioritet för lagerställeprogram** kan du ange fältnamn i olika prioriteringsgrupper.</span><span class="sxs-lookup"><span data-stu-id="4b32f-132">On the **Warehouse app field priority** page, you can put field names into different priority groups.</span></span> <span data-ttu-id="4b32f-133">Detta gör det möjligt att bestämma vilken information som ska visas på huvuduppgiftssidan när lagerarbetare utför åtgärder med programmet.</span><span class="sxs-lookup"><span data-stu-id="4b32f-133">This makes it possible to decide what information should be displayed on the main task page when warehouse workers perform tasks using the app.</span></span> <span data-ttu-id="4b32f-134">Om du klickar på **Skapa standardinställning** skapas en standarduppsättning prioriterade grupper.</span><span class="sxs-lookup"><span data-stu-id="4b32f-134">If you click **Create default setup**, a default set of priority groups will be generated.</span></span> <span data-ttu-id="4b32f-135">Det går att skapa så många prioriteringsgrupper som krävs, men endast tre prioriteringsgrupper visas på uppgiftssidan.</span><span class="sxs-lookup"><span data-stu-id="4b32f-135">It is possible to create as many priority groups as needed, but only three priority groups will be shown on the task page.</span></span> <span data-ttu-id="4b32f-136">När systemet skickar metadata till programmet, kommer det att tilldela varje fält en relativ prioritet beroende på dess prioriteringsgrupp, och programmet kommer att visa de första tre prioriteringsgrupperna i metadatan på uppgiftssidan.</span><span class="sxs-lookup"><span data-stu-id="4b32f-136">When the system sends metadata to the app, it will assign each field a relative priority depending on its priority group, and the app will display the first three priority groups contained in the metadata on the task page.</span></span> <span data-ttu-id="4b32f-137">Överflödig metadata visas på en ytterligare informationssida.</span><span class="sxs-lookup"><span data-stu-id="4b32f-137">The rest of the overflowing metadata will be displayed on a secondary details page.</span></span> <span data-ttu-id="4b32f-138">Tabellen nedan visar ett exempel på fem prioriteringsgrupper.</span><span class="sxs-lookup"><span data-stu-id="4b32f-138">The following table shows an example of five priority groups.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4b32f-139">Prioriteringsgrupp</span><span class="sxs-lookup"><span data-stu-id="4b32f-139">Priority group</span></span></th>
<th><span data-ttu-id="4b32f-140">Tilldelade fält</span><span class="sxs-lookup"><span data-stu-id="4b32f-140">Assigned fields</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td> <span data-ttu-id="4b32f-141">Prioritet 10</span><span class="sxs-lookup"><span data-stu-id="4b32f-141">Priority 10</span></span></td>
<td><ul>
<li><span data-ttu-id="4b32f-142">Artikel</span><span class="sxs-lookup"><span data-stu-id="4b32f-142">Item</span></span></li>
<li><span data-ttu-id="4b32f-143">Kvantitet</span><span class="sxs-lookup"><span data-stu-id="4b32f-143">Quantity</span></span></li>
<li><span data-ttu-id="4b32f-144">Enhet</span><span class="sxs-lookup"><span data-stu-id="4b32f-144">Unit of measure</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td> <span data-ttu-id="4b32f-145">Prioritet 20</span><span class="sxs-lookup"><span data-stu-id="4b32f-145">Priority 20</span></span></td>
<td><ul>
<li><span data-ttu-id="4b32f-146">Klusterposition</span><span class="sxs-lookup"><span data-stu-id="4b32f-146">Cluster position</span></span></li>
<li><span data-ttu-id="4b32f-147">Kluster</span><span class="sxs-lookup"><span data-stu-id="4b32f-147">Cluster</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td> <span data-ttu-id="4b32f-148">Prioritet 30</span><span class="sxs-lookup"><span data-stu-id="4b32f-148">Priority 30</span></span></td>
<td><ul>
<li><span data-ttu-id="4b32f-149">Artikelbeskrivning</span><span class="sxs-lookup"><span data-stu-id="4b32f-149">Item description</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td> <span data-ttu-id="4b32f-150">Prioritet 40</span><span class="sxs-lookup"><span data-stu-id="4b32f-150">Priority 40</span></span></td>
<td><ul>
<li><span data-ttu-id="4b32f-151">Inställningar</span><span class="sxs-lookup"><span data-stu-id="4b32f-151">Configuration</span></span></li>
<li><span data-ttu-id="4b32f-152">Färg</span><span class="sxs-lookup"><span data-stu-id="4b32f-152">Color</span></span></li>
<li><span data-ttu-id="4b32f-153">Storlek</span><span class="sxs-lookup"><span data-stu-id="4b32f-153">Size</span></span></li>
<li><span data-ttu-id="4b32f-154">Stil</span><span class="sxs-lookup"><span data-stu-id="4b32f-154">Style</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td> <span data-ttu-id="4b32f-155">Prioritet 50</span><span class="sxs-lookup"><span data-stu-id="4b32f-155">Priority 50</span></span></td>
<td><ul>
<li><span data-ttu-id="4b32f-156">Plats</span><span class="sxs-lookup"><span data-stu-id="4b32f-156">Location</span></span></li>
<li><span data-ttu-id="4b32f-157">ID-nummer</span><span class="sxs-lookup"><span data-stu-id="4b32f-157">License plate</span></span></li>
</ul></td>
</tr>
</tbody>
</table>

<span data-ttu-id="4b32f-158">När en lagerarbetare exempelvis utför en aktivitet på en mobil enhet och metadatan som ska visas i programmet består av följande fält:</span><span class="sxs-lookup"><span data-stu-id="4b32f-158">For example, when a warehouse worker is performing a task on a mobile device, if the metadata that will be displayed in the app consists of the following fields:</span></span>

-   <span data-ttu-id="4b32f-159">Artikel</span><span class="sxs-lookup"><span data-stu-id="4b32f-159">Item</span></span>
-   <span data-ttu-id="4b32f-160">Kvantitet</span><span class="sxs-lookup"><span data-stu-id="4b32f-160">Quantity</span></span>
-   <span data-ttu-id="4b32f-161">Enhet</span><span class="sxs-lookup"><span data-stu-id="4b32f-161">Unit of measure</span></span>
-   <span data-ttu-id="4b32f-162">Artikelbeskrivning</span><span class="sxs-lookup"><span data-stu-id="4b32f-162">Item description</span></span>
-   <span data-ttu-id="4b32f-163">Storlek och plats</span><span class="sxs-lookup"><span data-stu-id="4b32f-163">Size and Location</span></span>

<span data-ttu-id="4b32f-164">Baserat på fältprioriteringen i lagerställets program som anges i tabellen ovan, kommer följande 3 rader med information att visas på uppgiftssidan:</span><span class="sxs-lookup"><span data-stu-id="4b32f-164">Based on the warehouse app field priority set up in the table above, the following 3 rows of information will be displayed on the task page:</span></span>

-   <span data-ttu-id="4b32f-165">Rad 1: Artikel, Kvantitet, Måttenhet</span><span class="sxs-lookup"><span data-stu-id="4b32f-165">Row 1: Item, Quantity, Unit of measure</span></span>
-   <span data-ttu-id="4b32f-166">Rad 2: Artikelbeskrivning</span><span class="sxs-lookup"><span data-stu-id="4b32f-166">Row 2: Item description</span></span>
-   <span data-ttu-id="4b32f-167">Rad 3: Storlek</span><span class="sxs-lookup"><span data-stu-id="4b32f-167">Row 3: Size</span></span>

<span data-ttu-id="4b32f-168">Återstående metadata, till exempel plats, visas inte på uppgiftssidan men däremot på en informationssida.</span><span class="sxs-lookup"><span data-stu-id="4b32f-168">The remaining metadata, for example, Location, will not be displayed on the task page, but will be displayed on a details page.</span></span> <span data-ttu-id="4b32f-169">Om du vill veta mer och visa exempel på användargränssnittet, se blogginlägget [Vi presenterar Finance and Operations - Lagerstyrning](https://blogs.msdn.microsoft.com/dynamicsaxscm/2017/01/20/announcing-dynamics-365-for-operations-warehousing/).</span><span class="sxs-lookup"><span data-stu-id="4b32f-169">To learn more and see examples of the user interface, refer to the blog post [Announcing Finance and Operations - Warehousing](https://blogs.msdn.microsoft.com/dynamicsaxscm/2017/01/20/announcing-dynamics-365-for-operations-warehousing/).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="4b32f-170">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="4b32f-170">Additional resources</span></span>

[<span data-ttu-id="4b32f-171">Installera och ansluta mobilappen för distributionslagerhantering</span><span class="sxs-lookup"><span data-stu-id="4b32f-171">Install and connect the Warehouse Management mobile app</span></span>](../warehousing/install-configure-warehouse-management-app.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]