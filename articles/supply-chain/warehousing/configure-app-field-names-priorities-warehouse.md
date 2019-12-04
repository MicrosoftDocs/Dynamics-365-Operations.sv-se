---
title: Konfigurera programfältnamn i lagerstyrningsprogrammet
description: Det här avsnittet beskriver hur du definierar och konfigurerar fältnamnen i lagerställets program samt prioriteringar i Dynamics 365 Supply Chain Management.
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
ms.openlocfilehash: 11f6c96cc07c63d2c0c6a94385916b3396a77ed5
ms.sourcegitcommit: 57bc7e17682e2edb5e1766496b7a22f4621819dd
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/18/2019
ms.locfileid: "2814983"
---
# <a name="configure-app-field-names-in-warehousing-app"></a><span data-ttu-id="65851-103">Konfigurera programfältnamn i lagerstyrningsprogrammet</span><span class="sxs-lookup"><span data-stu-id="65851-103">Configure app field names in Warehousing app</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="65851-104">Det här avsnittet beskriver hur du definierar och konfigurerar fältnamnen i lagerställets program samt prioriteringar i Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="65851-104">This topic describes how to define and configure warehouse app field names and priorities in Dynamics 365 Supply Chain Management.</span></span> 

> [!NOTE]
> <span data-ttu-id="65851-105">Denna artikel gäller funktioner i lagerstyrningshanteringen.</span><span class="sxs-lookup"><span data-stu-id="65851-105">This topic applies to features in Warehouse management.</span></span> <span data-ttu-id="65851-106">Den gäller inte funktioner i lagerhanteringshanteringen.</span><span class="sxs-lookup"><span data-stu-id="65851-106">It doesn’t apply to features in Inventory management.</span></span> <span data-ttu-id="65851-107">Lagerstyrning är ett program som du kan använda för att utföra uppgifter på lagerstället.</span><span class="sxs-lookup"><span data-stu-id="65851-107">Warehousing is an application that you can use to perform warehouse tasks.</span></span> <span data-ttu-id="65851-108">Du kan definiera och konfigurera de fältnamn som används i programmet, samt konfigurera prioriteringen bland de fältnamn som ska tilldelas.</span><span class="sxs-lookup"><span data-stu-id="65851-108">You can define and configure the field names that are used in the app, as well as configure the priority to which the field names should be assigned.</span></span> <span data-ttu-id="65851-109">Det här avsnittet förklarar hur du definierar och konfigurerar fältnamn och prioriteringar i lagerställets program, samt hur dessa används i Lagerstyrning.</span><span class="sxs-lookup"><span data-stu-id="65851-109">This topic explains how to define and configure these warehouse app field names and priorities, and how they are used in Warehousing.</span></span> <span data-ttu-id="65851-110">Detaljerad information om hur du konfigurerar anslutningen till Lagerstyrning, finns i kursen [Installera och konfigurera lagerstyrningsappen - översikt](install-configure-warehousing-app.md).</span><span class="sxs-lookup"><span data-stu-id="65851-110">For detailed information about how to configure the connection to FWarehousing, refer to the tutorial [Install and configure the Warehousing app overview](install-configure-warehousing-app.md).</span></span>

## <a name="configure-warehouse-app-field-names"></a><span data-ttu-id="65851-111">Konfigurera fältnamn i lagerställets program</span><span class="sxs-lookup"><span data-stu-id="65851-111">Configure warehouse app field names</span></span>

<span data-ttu-id="65851-112">När du använder Lagerstyrning på din mobila enhet kan du konfigurera hur metadata ska visas på enheten på sidan **Fältnamn i lagerställeprogram**.</span><span class="sxs-lookup"><span data-stu-id="65851-112">When you use Warehousing on your mobile device, you can configure how metadata should be displayed on your device on the **Warehouse app field names** page.</span></span> <span data-ttu-id="65851-113">Välj **Skapa standardinställning** i ett nytt företag för att skapa alla fältnamn som ska användas i lagerställets arbetsflöden för mobila enheter, och tilldela dem sedan ett föredraget inmatningsläge och en föredragen inmatningstyp.</span><span class="sxs-lookup"><span data-stu-id="65851-113">In a new company, select **Create default setup** to generate all field names that will be used in the warehouse mobile device workflows, and then assign a preferred input mode and input type to them.</span></span> <span data-ttu-id="65851-114">När du har genererat alla fältnamn väljer du in följande inmatningsalternativ.</span><span class="sxs-lookup"><span data-stu-id="65851-114">After you have generated all field names, you can select the following input options.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="65851-115">Alternativ</span><span class="sxs-lookup"><span data-stu-id="65851-115">Option</span></span></th>
<th><span data-ttu-id="65851-116">beskrivning</span><span class="sxs-lookup"><span data-stu-id="65851-116">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="65851-117">Prioriterat indataläge</span><span class="sxs-lookup"><span data-stu-id="65851-117">Preferred input mode</span></span></td>
<td><span data-ttu-id="65851-118">Det här alternativet anger om ett skanningsfält eller ett fält för manuell inmatning bör visas för det valda fältnamnet.</span><span class="sxs-lookup"><span data-stu-id="65851-118">This option defines whether a scanning field or a manual entry input field should be shown for the selected field name.</span></span> <span data-ttu-id="65851-119">Detta är användbart för att skilja fälten åt, beroende på om du använder streckkoder för fältet.</span><span class="sxs-lookup"><span data-stu-id="65851-119">This is useful to distinguish fields depending on if barcodes are used for the field.</span></span> <span data-ttu-id="65851-120"><strong>Obs!</strong> För fältnamn med önskat inmatningsläge angivet som <strong>Skanning</strong> kan du ange information manuellt om streckkoden är skadad eller oläsbar.</span><span class="sxs-lookup"><span data-stu-id="65851-120"><strong>Note:</strong> For field names with preferred input mode set to <strong>Scanning</strong>, you can enter information manually if the barcode is unreadable or damaged.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="65851-121">Inmatningstyp</span><span class="sxs-lookup"><span data-stu-id="65851-121">Input type</span></span></td>
<td><span data-ttu-id="65851-122">Det här alternativet definierar vilken inmatningstyp som ska användas för det valda fältnamnet.</span><span class="sxs-lookup"><span data-stu-id="65851-122">This option defines what input type should be used for the selected field name.</span></span> <span data-ttu-id="65851-123">Det finns fyra alternativ:</span><span class="sxs-lookup"><span data-stu-id="65851-123">Four options are available:</span></span>
<ul>
<li><span data-ttu-id="65851-124"><strong>Urval</strong> - Innehåller en lista över tillgängliga alternativ.</span><span class="sxs-lookup"><span data-stu-id="65851-124"><strong>Selection</strong> - Contains a list of options to choose from.</span></span> <span data-ttu-id="65851-125">Fältnamn med det här alternativet kan inte redigeras.</span><span class="sxs-lookup"><span data-stu-id="65851-125">Field names with this option are not editable.</span></span></li>
<li><span data-ttu-id="65851-126"><strong>Datum</strong> - Fältnamn angivna som datum visar ett datumformat tillsammans med etiketten.</span><span class="sxs-lookup"><span data-stu-id="65851-126"><strong>Date</strong> - Field names specified as date will show a date format with the label.</span></span> <span data-ttu-id="65851-127">Detta hjälper lagerarbetare att se i vilket format datumet ska anges.</span><span class="sxs-lookup"><span data-stu-id="65851-127">This helps warehouse workers see in which format to enter the date.</span></span> <span data-ttu-id="65851-128">Fältnamn med det här alternativet kan inte redigeras.</span><span class="sxs-lookup"><span data-stu-id="65851-128">Field names with this option are not editable.</span></span></li>
<li><span data-ttu-id="65851-129"><strong>Alfa</strong> - Om detta alternativ väljs kommer enhetens tangentbord att användas när du anger information manuellt i appen.</span><span class="sxs-lookup"><span data-stu-id="65851-129"><strong>Alpha</strong> - If selected, the device keyboard will be used when entering information manually in the app.</span></span> <span data-ttu-id="65851-130">Tangentbordsupplevelsen kan ändras beroende på vilken enhet som används.</span><span class="sxs-lookup"><span data-stu-id="65851-130">The keyboard experience can be changed depending on which device is used.</span></span></li>
<li><span data-ttu-id="65851-131"><strong>Numerisk</strong> - Välj detta alternativ för fältnamn som endast använder numerisk inmatning om du vill visa ett numeriskt tangentbord tillsammans med inmatningsfältet stället för enhetens tangentbord.</span><span class="sxs-lookup"><span data-stu-id="65851-131"><strong>Numeric</strong> - For field names that use numeric input only, you can select this option to display a custom numeric keypad with the input field instead of the device keyboard.</span></span></li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="configure-warehouse-app-field-priority"></a><span data-ttu-id="65851-132">Konfigurera prioriteringsordningen för lagerställets programfält</span><span class="sxs-lookup"><span data-stu-id="65851-132">Configure warehouse app field priority</span></span>

<span data-ttu-id="65851-133">På sidan **Fältprioritet för lagerställeprogram** kan du ange fältnamn i olika prioriteringsgrupper.</span><span class="sxs-lookup"><span data-stu-id="65851-133">On the **Warehouse app field priority** page, you can put field names into different priority groups.</span></span> <span data-ttu-id="65851-134">Detta gör det möjligt att bestämma vilken information som ska visas på huvuduppgiftssidan när lagerarbetare utför åtgärder med programmet.</span><span class="sxs-lookup"><span data-stu-id="65851-134">This makes it possible to decide what information should be displayed on the main task page when warehouse workers perform tasks using the app.</span></span> <span data-ttu-id="65851-135">Om du klickar på **Skapa standardinställning** skapas en standarduppsättning prioriterade grupper.</span><span class="sxs-lookup"><span data-stu-id="65851-135">If you click **Create default setup**, a default set of priority groups will be generated.</span></span> <span data-ttu-id="65851-136">Det går att skapa så många prioriteringsgrupper som krävs, men endast tre prioriteringsgrupper visas på uppgiftssidan.</span><span class="sxs-lookup"><span data-stu-id="65851-136">It is possible to create as many priority groups as needed, but only three priority groups will be shown on the task page.</span></span> <span data-ttu-id="65851-137">När systemet skickar metadata till programmet, kommer det att tilldela varje fält en relativ prioritet beroende på dess prioriteringsgrupp, och programmet kommer att visa de första tre prioriteringsgrupperna i metadatan på uppgiftssidan.</span><span class="sxs-lookup"><span data-stu-id="65851-137">When the system sends metadata to the app, it will assign each field a relative priority depending on its priority group, and the app will display the first three priority groups contained in the metadata on the task page.</span></span> <span data-ttu-id="65851-138">Överflödig metadata visas på en ytterligare informationssida.</span><span class="sxs-lookup"><span data-stu-id="65851-138">The rest of the overflowing metadata will be displayed on a secondary details page.</span></span> <span data-ttu-id="65851-139">Tabellen nedan visar ett exempel på fem prioriteringsgrupper.</span><span class="sxs-lookup"><span data-stu-id="65851-139">The following table shows an example of five priority groups.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="65851-140">Prioriteringsgrupp</span><span class="sxs-lookup"><span data-stu-id="65851-140">Priority group</span></span></th>
<th><span data-ttu-id="65851-141">Tilldelade fält</span><span class="sxs-lookup"><span data-stu-id="65851-141">Assigned fields</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td> <span data-ttu-id="65851-142">Prioritet 10</span><span class="sxs-lookup"><span data-stu-id="65851-142">Priority 10</span></span></td>
<td><ul>
<li><span data-ttu-id="65851-143">Artikel</span><span class="sxs-lookup"><span data-stu-id="65851-143">Item</span></span></li>
<li><span data-ttu-id="65851-144">Kvantitet</span><span class="sxs-lookup"><span data-stu-id="65851-144">Quantity</span></span></li>
<li><span data-ttu-id="65851-145">Enhet</span><span class="sxs-lookup"><span data-stu-id="65851-145">Unit of measure</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td> <span data-ttu-id="65851-146">Prioritet 20</span><span class="sxs-lookup"><span data-stu-id="65851-146">Priority 20</span></span></td>
<td><ul>
<li><span data-ttu-id="65851-147">Klusterposition</span><span class="sxs-lookup"><span data-stu-id="65851-147">Cluster position</span></span></li>
<li><span data-ttu-id="65851-148">Kluster</span><span class="sxs-lookup"><span data-stu-id="65851-148">Cluster</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td> <span data-ttu-id="65851-149">Prioritet 30</span><span class="sxs-lookup"><span data-stu-id="65851-149">Priority 30</span></span></td>
<td><ul>
<li><span data-ttu-id="65851-150">Artikelbeskrivning</span><span class="sxs-lookup"><span data-stu-id="65851-150">Item description</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td> <span data-ttu-id="65851-151">Prioritet 40</span><span class="sxs-lookup"><span data-stu-id="65851-151">Priority 40</span></span></td>
<td><ul>
<li><span data-ttu-id="65851-152">Inställningar</span><span class="sxs-lookup"><span data-stu-id="65851-152">Configuration</span></span></li>
<li><span data-ttu-id="65851-153">Färg</span><span class="sxs-lookup"><span data-stu-id="65851-153">Color</span></span></li>
<li><span data-ttu-id="65851-154">Storlek</span><span class="sxs-lookup"><span data-stu-id="65851-154">Size</span></span></li>
<li><span data-ttu-id="65851-155">Stil</span><span class="sxs-lookup"><span data-stu-id="65851-155">Style</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td> <span data-ttu-id="65851-156">Prioritet 50</span><span class="sxs-lookup"><span data-stu-id="65851-156">Priority 50</span></span></td>
<td><ul>
<li><span data-ttu-id="65851-157">Plats</span><span class="sxs-lookup"><span data-stu-id="65851-157">Location</span></span></li>
<li><span data-ttu-id="65851-158">ID-nummer</span><span class="sxs-lookup"><span data-stu-id="65851-158">License plate</span></span></li>
</ul></td>
</tr>
</tbody>
</table>

<span data-ttu-id="65851-159">När en lagerarbetare exempelvis utför en aktivitet på en mobil enhet och metadatan som ska visas i programmet består av följande fält:</span><span class="sxs-lookup"><span data-stu-id="65851-159">For example, when a warehouse worker is performing a task on a mobile device, if the metadata that will be displayed in the app consists of the following fields:</span></span>

-   <span data-ttu-id="65851-160">Artikel</span><span class="sxs-lookup"><span data-stu-id="65851-160">Item</span></span>
-   <span data-ttu-id="65851-161">Kvantitet</span><span class="sxs-lookup"><span data-stu-id="65851-161">Quantity</span></span>
-   <span data-ttu-id="65851-162">Enhet</span><span class="sxs-lookup"><span data-stu-id="65851-162">Unit of measure</span></span>
-   <span data-ttu-id="65851-163">Artikelbeskrivning</span><span class="sxs-lookup"><span data-stu-id="65851-163">Item description</span></span>
-   <span data-ttu-id="65851-164">Storlek och plats</span><span class="sxs-lookup"><span data-stu-id="65851-164">Size and Location</span></span>

<span data-ttu-id="65851-165">Baserat på fältprioriteringen i lagerställets program som anges i tabellen ovan, kommer följande 3 rader med information att visas på uppgiftssidan:</span><span class="sxs-lookup"><span data-stu-id="65851-165">Based on the warehouse app field priority set up in the table above, the following 3 rows of information will be displayed on the task page:</span></span>

-   <span data-ttu-id="65851-166">Rad 1: Artikel, Kvantitet, Måttenhet</span><span class="sxs-lookup"><span data-stu-id="65851-166">Row 1: Item, Quantity, Unit of measure</span></span>
-   <span data-ttu-id="65851-167">Rad 2: Artikelbeskrivning</span><span class="sxs-lookup"><span data-stu-id="65851-167">Row 2: Item description</span></span>
-   <span data-ttu-id="65851-168">Rad 3: Storlek</span><span class="sxs-lookup"><span data-stu-id="65851-168">Row 3: Size</span></span>

<span data-ttu-id="65851-169">Återstående metadata, till exempel plats, visas inte på uppgiftssidan men däremot på en informationssida.</span><span class="sxs-lookup"><span data-stu-id="65851-169">The remaining metadata, for example, Location, will not be displayed on the task page, but will be displayed on a details page.</span></span> <span data-ttu-id="65851-170">Om du vill veta mer och visa exempel på användargränssnittet, se blogginlägget [Vi presenterar Finance and Operations - Lagerstyrning](https://blogs.msdn.microsoft.com/dynamicsaxscm/2017/01/20/announcing-dynamics-365-for-operations-warehousing/).</span><span class="sxs-lookup"><span data-stu-id="65851-170">To learn more and see examples of the user interface, refer to the blog post [Announcing Finance and Operations - Warehousing](https://blogs.msdn.microsoft.com/dynamicsaxscm/2017/01/20/announcing-dynamics-365-for-operations-warehousing/).</span></span>

<a name="additional-resources"></a><span data-ttu-id="65851-171">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="65851-171">Additional resources</span></span>
--------

[<span data-ttu-id="65851-172">Installera och konfigurera lagerstyrningsappen - översikt</span><span class="sxs-lookup"><span data-stu-id="65851-172">Install and configure the Warehousing app overview</span></span>](install-configure-warehousing-app.md)
