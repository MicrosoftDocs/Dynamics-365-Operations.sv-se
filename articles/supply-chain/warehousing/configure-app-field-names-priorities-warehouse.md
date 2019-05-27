---
title: Konfigurera programfältnamn i lagerstyrningsprogrammet
description: Det här avsnittet beskriver hur du definierar och konfigurerar fältnamnen i lagerställets program samt prioriteringar i Finance and Operations.
author: MarkusFogelberg
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSMobileAppField, WHSMobileAppFieldPriority
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 269434
ms.assetid: 6cf3d7da-29bb-4d3d-aaf5-544ca9cc2980
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: mafoge
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 0162014189ed6bffb17e6718a67eecfd55c334a5
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/15/2019
ms.locfileid: "1548939"
---
# <a name="configure-app-field-names-in-warehousing-app"></a><span data-ttu-id="3890a-103">Konfigurera programfältnamn i lagerstyrningsprogrammet</span><span class="sxs-lookup"><span data-stu-id="3890a-103">Configure app field names in Warehousing app</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="3890a-104">Det här avsnittet beskriver hur du definierar och konfigurerar fältnamnen i lagerställets program samt prioriteringar i Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="3890a-104">This topic describes how to define and configure warehouse app field names and priorities in Finance and Operations.</span></span> 

<span data-ttu-id="3890a-105">**Obs!** Denna artikel gäller funktioner i lagerstyrningshanteringen.</span><span class="sxs-lookup"><span data-stu-id="3890a-105">**Note:** This topic applies to features in Warehouse management.</span></span> <span data-ttu-id="3890a-106">Den gäller inte funktioner i lagerhanteringshanteringen.</span><span class="sxs-lookup"><span data-stu-id="3890a-106">It doesn’t apply to features in Inventory management.</span></span> <span data-ttu-id="3890a-107">Finance and Operations - Lagerstyrning är ett program som du kan använda för att utföra uppgifter på lagerstället.</span><span class="sxs-lookup"><span data-stu-id="3890a-107">Finance and Operations - Warehousing is an application that you can use to perform warehouse tasks.</span></span> <span data-ttu-id="3890a-108">Du kan definiera och konfigurera de fältnamn som används i programmet, samt konfigurera prioriteringen bland de fältnamn som ska tilldelas.</span><span class="sxs-lookup"><span data-stu-id="3890a-108">You can define and configure the field names that are used in the app, as well as configure the priority to which the field names should be assigned.</span></span> <span data-ttu-id="3890a-109">Det här avsnittet förklarar hur du definierar och konfigurerar fältnamn och prioriteringar i lagerställets program, samt hur dessa används i Finance and Operations - Lagerstyrning.</span><span class="sxs-lookup"><span data-stu-id="3890a-109">This topic explains how to define and configure these warehouse app field names and priorities, and how they are used in Finance and Operations - Warehousing.</span></span> <span data-ttu-id="3890a-110">Detaljerad information om hur du konfigurerar anslutningen till Finance and Operations - Lagerstyrning, finns i kursen [Installera och konfigurera Finance and Operations - Lagerstyrning](install-configure-warehousing-app.md).</span><span class="sxs-lookup"><span data-stu-id="3890a-110">For detailed information about how to configure the connection to Finance and Operations  - Warehousing, refer to the tutorial [Install and configure Finance and Operations - Warehousing](install-configure-warehousing-app.md).</span></span>

## <a name="configure-warehouse-app-field-names"></a><span data-ttu-id="3890a-111">Konfigurera fältnamn i lagerställets program</span><span class="sxs-lookup"><span data-stu-id="3890a-111">Configure warehouse app field names</span></span>

<span data-ttu-id="3890a-112">När du använder Finance and Operations – Lagerstyrning på din mobila enhet kan du konfigurera hur metadata ska visas på enheten på sidan **Fältnamn i lagerställeprogram**.</span><span class="sxs-lookup"><span data-stu-id="3890a-112">When you use Finance and Operations - Warehousing on your mobile device, you can configure how metadata should be displayed on your device on the **Warehouse app field names** page.</span></span> <span data-ttu-id="3890a-113">Välj **Skapa standardinställning** i ett nytt företag i Finance and Operations för att skapa alla fältnamn som ska användas i lagerställets arbetsflöden för mobila enheter, och tilldela dem sedan ett föredraget inmatningsläge och en föredragen inmatningstyp.</span><span class="sxs-lookup"><span data-stu-id="3890a-113">In a new company in Finance and Operations, select **Create default setup** to generate all field names that will be used in the warehouse mobile device workflows, and then assign a preferred input mode and input type to them.</span></span> <span data-ttu-id="3890a-114">När du har genererat alla fältnamn väljer du in följande inmatningsalternativ.</span><span class="sxs-lookup"><span data-stu-id="3890a-114">After you have generated all field names, you can select the following input options.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3890a-115">Alternativ</span><span class="sxs-lookup"><span data-stu-id="3890a-115">Option</span></span></th>
<th><span data-ttu-id="3890a-116">beskrivning</span><span class="sxs-lookup"><span data-stu-id="3890a-116">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="3890a-117">Prioriterat indataläge</span><span class="sxs-lookup"><span data-stu-id="3890a-117">Preferred input mode</span></span></td>
<td><span data-ttu-id="3890a-118">Det här alternativet anger om ett skanningsfält eller ett fält för manuell inmatning bör visas för det valda fältnamnet.</span><span class="sxs-lookup"><span data-stu-id="3890a-118">This option defines whether a scanning field or a manual entry input field should be shown for the selected field name.</span></span> <span data-ttu-id="3890a-119">Detta är användbart för att skilja fälten åt, beroende på om du använder streckkoder för fältet.</span><span class="sxs-lookup"><span data-stu-id="3890a-119">This is useful to distinguish fields depending on if barcodes are used for the field.</span></span> <span data-ttu-id="3890a-120"><strong>Obs!</strong> För fältnamn med önskat inmatningsläge angivet som <strong>Skanning</strong> kan du ange information manuellt om streckkoden är skadad eller oläsbar.</span><span class="sxs-lookup"><span data-stu-id="3890a-120"><strong>Note:</strong> For field names with preferred input mode set to <strong>Scanning</strong>, you can enter information manually if the barcode is unreadable or damaged.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="3890a-121">Inmatningstyp</span><span class="sxs-lookup"><span data-stu-id="3890a-121">Input type</span></span></td>
<td><span data-ttu-id="3890a-122">Det här alternativet definierar vilken inmatningstyp som ska användas för det valda fältnamnet.</span><span class="sxs-lookup"><span data-stu-id="3890a-122">This option defines what input type should be used for the selected field name.</span></span> <span data-ttu-id="3890a-123">Det finns fyra alternativ:</span><span class="sxs-lookup"><span data-stu-id="3890a-123">Four options are available:</span></span>
<ul>
<li><span data-ttu-id="3890a-124"><strong>Urval</strong> - Innehåller en lista över tillgängliga alternativ.</span><span class="sxs-lookup"><span data-stu-id="3890a-124"><strong>Selection</strong> - Contains a list of options to choose from.</span></span> <span data-ttu-id="3890a-125">Fältnamn med det här alternativet kan inte redigeras.</span><span class="sxs-lookup"><span data-stu-id="3890a-125">Field names with this option are not editable.</span></span></li>
<li><span data-ttu-id="3890a-126"><strong>Datum</strong> - Fältnamn angivna som datum visar ett datumformat tillsammans med etiketten.</span><span class="sxs-lookup"><span data-stu-id="3890a-126"><strong>Date</strong> - Field names specified as date will show a date format with the label.</span></span> <span data-ttu-id="3890a-127">Detta hjälper lagerarbetare att se i vilket format datumet ska anges.</span><span class="sxs-lookup"><span data-stu-id="3890a-127">This helps warehouse workers see in which format to enter the date.</span></span> <span data-ttu-id="3890a-128">Fältnamn med det här alternativet kan inte redigeras.</span><span class="sxs-lookup"><span data-stu-id="3890a-128">Field names with this option are not editable.</span></span></li>
<li><span data-ttu-id="3890a-129"><strong>Alfa</strong> - Om detta alternativ väljs kommer enhetens tangentbord att användas när du anger information manuellt i appen.</span><span class="sxs-lookup"><span data-stu-id="3890a-129"><strong>Alpha</strong> - If selected, the device keyboard will be used when entering information manually in the app.</span></span> <span data-ttu-id="3890a-130">Tangentbordsupplevelsen kan ändras beroende på vilken enhet som används.</span><span class="sxs-lookup"><span data-stu-id="3890a-130">The keyboard experience can be changed depending on which device is used.</span></span></li>
<li><span data-ttu-id="3890a-131"><strong>Numerisk</strong> - Välj detta alternativ för fältnamn som endast använder numerisk inmatning om du vill visa ett numeriskt tangentbord tillsammans med inmatningsfältet stället för enhetens tangentbord.</span><span class="sxs-lookup"><span data-stu-id="3890a-131"><strong>Numeric</strong> - For field names that use numeric input only, you can select this option to display a custom numeric keypad with the input field instead of the device keyboard.</span></span></li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="configure-warehouse-app-field-priority"></a><span data-ttu-id="3890a-132">Konfigurera prioriteringsordningen för lagerställets programfält</span><span class="sxs-lookup"><span data-stu-id="3890a-132">Configure warehouse app field priority</span></span>

<span data-ttu-id="3890a-133">På sidan **Fältprioritet för lagerställeprogram** kan du ange fältnamn i olika prioriteringsgrupper.</span><span class="sxs-lookup"><span data-stu-id="3890a-133">On the **Warehouse app field priority** page, you can put field names into different priority groups.</span></span> <span data-ttu-id="3890a-134">Detta gör det möjligt att bestämma vilken information som ska visas på huvuduppgiftssidan när lagerarbetare utför åtgärder med programmet.</span><span class="sxs-lookup"><span data-stu-id="3890a-134">This makes it possible to decide what information should be displayed on the main task page when warehouse workers perform tasks using the app.</span></span> <span data-ttu-id="3890a-135">Om du klickar på **Skapa standardinställning** skapas en standarduppsättning prioriterade grupper.</span><span class="sxs-lookup"><span data-stu-id="3890a-135">If you click **Create default setup**, a default set of priority groups will be generated.</span></span> <span data-ttu-id="3890a-136">Det går att skapa så många prioriteringsgrupper som krävs, men endast tre prioriteringsgrupper visas på uppgiftssidan.</span><span class="sxs-lookup"><span data-stu-id="3890a-136">It is possible to create as many priority groups as needed, but only three priority groups will be shown on the task page.</span></span> <span data-ttu-id="3890a-137">När Finance and Operations skickar metadata till programmet, kommer det att tilldela varje fält en relativ prioritet beroende på dess prioriteringsgrupp, och programmet kommer att visa de första tre prioriteringsgrupperna i metadatan på uppgiftssidan.</span><span class="sxs-lookup"><span data-stu-id="3890a-137">When Finance and Operations sends metadata to the app, it will assign each field a relative priority depending on its priority group, and the app will display the first three priority groups contained in the metadata on the task page.</span></span> <span data-ttu-id="3890a-138">Överflödig metadata visas på en ytterligare informationssida.</span><span class="sxs-lookup"><span data-stu-id="3890a-138">The rest of the overflowing metadata will be displayed on a secondary details page.</span></span> <span data-ttu-id="3890a-139">Tabellen nedan visar ett exempel på fem prioriteringsgrupper.</span><span class="sxs-lookup"><span data-stu-id="3890a-139">The following table shows an example of five priority groups.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3890a-140">Prioriteringsgrupp</span><span class="sxs-lookup"><span data-stu-id="3890a-140">Priority group</span></span></th>
<th><span data-ttu-id="3890a-141">Tilldelade fält</span><span class="sxs-lookup"><span data-stu-id="3890a-141">Assigned fields</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td> <span data-ttu-id="3890a-142">Prioritet 10</span><span class="sxs-lookup"><span data-stu-id="3890a-142">Priority 10</span></span></td>
<td><ul>
<li><span data-ttu-id="3890a-143">Artikel</span><span class="sxs-lookup"><span data-stu-id="3890a-143">Item</span></span></li>
<li><span data-ttu-id="3890a-144">Kvantitet</span><span class="sxs-lookup"><span data-stu-id="3890a-144">Quantity</span></span></li>
<li><span data-ttu-id="3890a-145">Enhet</span><span class="sxs-lookup"><span data-stu-id="3890a-145">Unit of measure</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td> <span data-ttu-id="3890a-146">Prioritet 20</span><span class="sxs-lookup"><span data-stu-id="3890a-146">Priority 20</span></span></td>
<td><ul>
<li><span data-ttu-id="3890a-147">Klusterposition</span><span class="sxs-lookup"><span data-stu-id="3890a-147">Cluster position</span></span></li>
<li><span data-ttu-id="3890a-148">Kluster</span><span class="sxs-lookup"><span data-stu-id="3890a-148">Cluster</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td> <span data-ttu-id="3890a-149">Prioritet 30</span><span class="sxs-lookup"><span data-stu-id="3890a-149">Priority 30</span></span></td>
<td><ul>
<li><span data-ttu-id="3890a-150">Artikelbeskrivning</span><span class="sxs-lookup"><span data-stu-id="3890a-150">Item description</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td> <span data-ttu-id="3890a-151">Prioritet 40</span><span class="sxs-lookup"><span data-stu-id="3890a-151">Priority 40</span></span></td>
<td><ul>
<li><span data-ttu-id="3890a-152">Inställningar</span><span class="sxs-lookup"><span data-stu-id="3890a-152">Configuration</span></span></li>
<li><span data-ttu-id="3890a-153">Färg</span><span class="sxs-lookup"><span data-stu-id="3890a-153">Color</span></span></li>
<li><span data-ttu-id="3890a-154">Storlek</span><span class="sxs-lookup"><span data-stu-id="3890a-154">Size</span></span></li>
<li><span data-ttu-id="3890a-155">Stil</span><span class="sxs-lookup"><span data-stu-id="3890a-155">Style</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td> <span data-ttu-id="3890a-156">Prioritet 50</span><span class="sxs-lookup"><span data-stu-id="3890a-156">Priority 50</span></span></td>
<td><ul>
<li><span data-ttu-id="3890a-157">Plats</span><span class="sxs-lookup"><span data-stu-id="3890a-157">Location</span></span></li>
<li><span data-ttu-id="3890a-158">ID-nummer</span><span class="sxs-lookup"><span data-stu-id="3890a-158">License plate</span></span></li>
</ul></td>
</tr>
</tbody>
</table>

<span data-ttu-id="3890a-159">När en lagerarbetare exempelvis utför en aktivitet på en mobil enhet och metadatan som ska visas i programmet består av följande fält:</span><span class="sxs-lookup"><span data-stu-id="3890a-159">For example, when a warehouse worker is performing a task on a mobile device, if the metadata that will be displayed in the app consists of the following fields:</span></span>

-   <span data-ttu-id="3890a-160">Artikel</span><span class="sxs-lookup"><span data-stu-id="3890a-160">Item</span></span>
-   <span data-ttu-id="3890a-161">Kvantitet</span><span class="sxs-lookup"><span data-stu-id="3890a-161">Quantity</span></span>
-   <span data-ttu-id="3890a-162">Enhet</span><span class="sxs-lookup"><span data-stu-id="3890a-162">Unit of measure</span></span>
-   <span data-ttu-id="3890a-163">Artikelbeskrivning</span><span class="sxs-lookup"><span data-stu-id="3890a-163">Item description</span></span>
-   <span data-ttu-id="3890a-164">Storlek och plats</span><span class="sxs-lookup"><span data-stu-id="3890a-164">Size and Location</span></span>

<span data-ttu-id="3890a-165">Baserat på fältprioriteringen i lagerställets program som anges i tabellen ovan, kommer följande 3 rader med information att visas på uppgiftssidan:</span><span class="sxs-lookup"><span data-stu-id="3890a-165">Based on the warehouse app field priority set up in the table above, the following 3 rows of information will be displayed on the task page:</span></span>

-   <span data-ttu-id="3890a-166">Rad 1: Artikel, Kvantitet, Måttenhet</span><span class="sxs-lookup"><span data-stu-id="3890a-166">Row 1: Item, Quantity, Unit of measure</span></span>
-   <span data-ttu-id="3890a-167">Rad 2: Artikelbeskrivning</span><span class="sxs-lookup"><span data-stu-id="3890a-167">Row 2: Item description</span></span>
-   <span data-ttu-id="3890a-168">Rad 3: Storlek</span><span class="sxs-lookup"><span data-stu-id="3890a-168">Row 3: Size</span></span>

<span data-ttu-id="3890a-169">Återstående metadata, till exempel plats, visas inte på uppgiftssidan men däremot på en informationssida.</span><span class="sxs-lookup"><span data-stu-id="3890a-169">The remaining metadata, for example, Location, will not be displayed on the task page, but will be displayed on a details page.</span></span> <span data-ttu-id="3890a-170">Om du vill veta mer och visa exempel på användargränssnittet, se blogginlägget [Vi presenterar Finance and Operations - Lagerstyrning](https://blogs.msdn.microsoft.com/dynamicsaxscm/2017/01/20/announcing-dynamics-365-for-operations-warehousing/).</span><span class="sxs-lookup"><span data-stu-id="3890a-170">To learn more and see examples of the user interface, refer to the blog post [Announcing Finance and Operations - Warehousing](https://blogs.msdn.microsoft.com/dynamicsaxscm/2017/01/20/announcing-dynamics-365-for-operations-warehousing/).</span></span>

<a name="additional-resources"></a><span data-ttu-id="3890a-171">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="3890a-171">Additional resources</span></span>
--------

[<span data-ttu-id="3890a-172">Installera och konfigurera Microsoft Dynamics 365 for Finance and Operations – Lagerhållning</span><span class="sxs-lookup"><span data-stu-id="3890a-172">Install and configure Microsoft Dynamics 365 for Finance and Operations – Warehousing</span></span>](install-configure-warehousing-app.md)



