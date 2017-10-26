---
title: "Visa och exportera fältbeskrivningar"
description: "Den här artikeln innehåller en beskrivning av hur du visar fältbeskrivningar och hur du använder sidan Fältbeskrivningar vid export av beskrivningar."
author: YuyuScheller
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: FieldDescriptions
audience: Application User, Developer, IT Pro
ms.reviewer: rschloma
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 11534
ms.assetid: e2795f51-a8a7-4c74-bdb9-b1be93bdd358
ms.search.region: Global
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 908f854e5ca50f4298110c08c87fefd9427b5cc9
ms.openlocfilehash: 841c18630a59c3f5a7b51cd005962fa8a7f7163f
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---

# <a name="view-and-export-field-descriptions"></a><span data-ttu-id="7bf9d-103">Visa och exportera fältbeskrivningar</span><span class="sxs-lookup"><span data-stu-id="7bf9d-103">View and export field descriptions</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="7bf9d-104">Den här artikeln innehåller en beskrivning av hur du visar fältbeskrivningar och hur du använder sidan Fältbeskrivningar vid export av beskrivningar.</span><span class="sxs-lookup"><span data-stu-id="7bf9d-104">This article describes how to view field descriptions and how to use the Field descriptions page to export descriptions.</span></span>

<span data-ttu-id="7bf9d-105">Microsoft Dynamics 365 for Finance and Operations har beskrivningar för vissa av de mer komplexa fälten.</span><span class="sxs-lookup"><span data-stu-id="7bf9d-105">Microsoft Dynamics 365 for Finance and Operations has descriptions for some of the more complex fields.</span></span> <span data-ttu-id="7bf9d-106">Dessa beskrivningar visas när du håller muspekaren över ett fält.</span><span class="sxs-lookup"><span data-stu-id="7bf9d-106">These descriptions appear when you hover over a field.</span></span> <span data-ttu-id="7bf9d-107">På sidan **Fältbeskrivningar** kan du visa och exportera fältbeskrivningar.</span><span class="sxs-lookup"><span data-stu-id="7bf9d-107">You can also view and export descriptions on the **Field descriptions** page.</span></span> 

<span data-ttu-id="7bf9d-108">Inte alla sidor har fältbeskrivningar.</span><span class="sxs-lookup"><span data-stu-id="7bf9d-108">Not all pages have field descriptions.</span></span> <span data-ttu-id="7bf9d-109">Vi tillhandahåller enbart beskrivningar av de mer komplexa fälten och inte av dem där användningen av fältet är tydligt.</span><span class="sxs-lookup"><span data-stu-id="7bf9d-109">We want to provide descriptions only for the more complex fields, not where the use of the field is obvious.</span></span> <span data-ttu-id="7bf9d-110">Av den anledningen saknas fältbeskrivningar på vissa sidor. Andra sidor innehåller några få beskrivningar och några av de mer komplexa sidorna, till exempel många av parametersidorna, har många beskrivningar.</span><span class="sxs-lookup"><span data-stu-id="7bf9d-110">Therefore, some pages don't have any field descriptions, some pages have a few descriptions, and some of the more complex pages, such as many of the parameters pages, have many descriptions.</span></span> 

<span data-ttu-id="7bf9d-111">Om du har tillgång till utvecklingsmiljön för Finance and Operationskan kan du lägga till egna fältbeskrivningar och anpassa befintliga beskrivningar.</span><span class="sxs-lookup"><span data-stu-id="7bf9d-111">If you have access to the Finance and Operations development environment, you can add new field descriptions and customize existing descriptions.</span></span> <span data-ttu-id="7bf9d-112">Du kan till exempel lägga till företagsspecifik information i en fältbeskrivning.</span><span class="sxs-lookup"><span data-stu-id="7bf9d-112">For example, you can add company-specific information to a field description.</span></span> <span data-ttu-id="7bf9d-113">Mer information hittar du i [Hjälp för Anpassa fält](../../dev-itpro/user-interface/customize-field-help.md).</span><span class="sxs-lookup"><span data-stu-id="7bf9d-113">For more information, see [Customize field help](../../dev-itpro/user-interface/customize-field-help.md).</span></span>

## <a name="see-field-descriptions-in-the-user-interface"></a><span data-ttu-id="7bf9d-114">Se fältbeskrivningarna i användargränssnittet.</span><span class="sxs-lookup"><span data-stu-id="7bf9d-114">See field descriptions in the user interface</span></span>
<span data-ttu-id="7bf9d-115">Du kan visa fältbeskrivningar genom att hovra över ett fält.</span><span class="sxs-lookup"><span data-stu-id="7bf9d-115">You can view field descriptions by hovering over a field.</span></span> <span data-ttu-id="7bf9d-116">Om det inte finns någon beskrivning ser du fältnamnet när du för muspekaren över fältet.</span><span class="sxs-lookup"><span data-stu-id="7bf9d-116">If no description is available, you see the field name when you hover over the field.</span></span> <span data-ttu-id="7bf9d-117">(Obs! I Dynamics AX 7.0 (February 2016) kan fältbeskrivningarna endast visas på sidan **Fältbeskrivningar**.) Följande illustration visar den fältbeskrivning som visas när du för muspekaren över fältet **Lås artiklar under inventeringen**.</span><span class="sxs-lookup"><span data-stu-id="7bf9d-117">(Note: In Dynamics AX 7.0 (February 2016), field descriptions can be viewed only on the **Field descriptions** page.) The following illustration shows the field description that appears when you hover over the **Lock items during count** field.</span></span> 

<span data-ttu-id="7bf9d-118">[![Exempel på en fältbeskrivning](./media/field-description.png)](./media/field-description.png)</span><span class="sxs-lookup"><span data-stu-id="7bf9d-118">[![Example of a field description](./media/field-description.png)](./media/field-description.png)</span></span>

## <a name="use-the-field-descriptions-page-to-view-and-export-field-help"></a><span data-ttu-id="7bf9d-119">Använd sidan Fältbeskrivningar för att visa och exportera hjälp för fält.</span><span class="sxs-lookup"><span data-stu-id="7bf9d-119">Use the Field descriptions page to view and export field help</span></span>
<span data-ttu-id="7bf9d-120">På sidan **Fältbeskrivningar** kan du visa och exportera fältbeskrivningar.</span><span class="sxs-lookup"><span data-stu-id="7bf9d-120">The **Field descriptions** page lets you view and export field descriptions.</span></span> <span data-ttu-id="7bf9d-121">Du kan se de beskrivningar som är tillgängliga en sida i taget.</span><span class="sxs-lookup"><span data-stu-id="7bf9d-121">You can see the descriptions that are available for one page at a time.</span></span>

### <a name="view-the-descriptions-for-a-page"></a><span data-ttu-id="7bf9d-122">Visa beskrivningarna för en sida</span><span class="sxs-lookup"><span data-stu-id="7bf9d-122">View the descriptions for a page</span></span>

<span data-ttu-id="7bf9d-123">Visa beskrivningarna för en sida genom att följa det här steget:</span><span class="sxs-lookup"><span data-stu-id="7bf9d-123">To view the descriptions for a page, follow this step.</span></span>

-   <span data-ttu-id="7bf9d-124">Ange sidan namn i fältet **Välj en sida**.</span><span class="sxs-lookup"><span data-stu-id="7bf9d-124">In the **Select a page** field, type the name of the page.</span></span> <span data-ttu-id="7bf9d-125">Du kan också klicka på pilen om du vill öppna en lista över alla sidor och sedan bläddra i eller filtrera listan.</span><span class="sxs-lookup"><span data-stu-id="7bf9d-125">Alternatively, click the arrow to open a list of all the pages, and then browse or filter the list.</span></span>

<span data-ttu-id="7bf9d-126">Du kan antingen använda sidans namn som visas i användargränssnittet (UI) (till exempel **Kunder**) eller kodnamnet (AOT-namn) som visas när du högerklickar på en sida (till exempel **CustTable**).</span><span class="sxs-lookup"><span data-stu-id="7bf9d-126">You can use either the name of the page that is shown in the user interface (UI) (for example, **Customers**) or the code name (AOT name) that's available when you right-click a page (for example, **CustTable**).</span></span> 

<span data-ttu-id="7bf9d-127">Information om olika sätt att filtrera listan över sidor hittar du i avsnittet "Söka efter en sida" senare i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="7bf9d-127">For information about the various ways to filter the list of pages, see the "Searching for a page" section later in this article.</span></span> 

<span data-ttu-id="7bf9d-128">Om du ställer in alternativet **Inkludera fält utan en beskrivning** till **Ja** kommer alla fält på sidan att visas, oavsett om de har en fältbeskrivning eller inte.</span><span class="sxs-lookup"><span data-stu-id="7bf9d-128">If you set the **Include fields without a description** option to **Yes**, all the fields on the page are shown, even if they don't have a field description.</span></span>

### <a name="export-the-descriptions-for-a-page"></a><span data-ttu-id="7bf9d-129">Exportera beskrivningarna för en sida</span><span class="sxs-lookup"><span data-stu-id="7bf9d-129">Export the descriptions for a page</span></span>

<span data-ttu-id="7bf9d-130">Om du vill exportera beskrivningarna för en sida ska du följa de här stegen:</span><span class="sxs-lookup"><span data-stu-id="7bf9d-130">To export the descriptions for a page, follow these steps.</span></span>

1.  <span data-ttu-id="7bf9d-131">Välj en sida i fältet **Välj en sida**.</span><span class="sxs-lookup"><span data-stu-id="7bf9d-131">In the **Select a page** field, select a page.</span></span>
2.  <span data-ttu-id="7bf9d-132">Klicka på knappen **Öppna i Microsoft Office** i det övre högra hörnet och klicka sedan på **FieldDescriptionTmp**.</span><span class="sxs-lookup"><span data-stu-id="7bf9d-132">Click the **Open in Microsoft Office** button in the upper-right corner, and then click **FieldDescriptionTmp**.</span></span>

### <a name="searching-for-a-page"></a><span data-ttu-id="7bf9d-133">Söka efter en sida</span><span class="sxs-lookup"><span data-stu-id="7bf9d-133">Searching for a page</span></span>

<span data-ttu-id="7bf9d-134">Det finns flera sätt att söka efter en sida i fältet **Välj en sida**.</span><span class="sxs-lookup"><span data-stu-id="7bf9d-134">There are several ways to search for a page in the **Select a page** field.</span></span> <span data-ttu-id="7bf9d-135">I många fall måste du klicka på pilen i fältet **Välj en sida** om du vill öppna listrutan och sedan välja från en filtrerad lista över sidor.</span><span class="sxs-lookup"><span data-stu-id="7bf9d-135">In many cases, you must click the arrow in the **Select a page** field to open the drop-down list, and then select from a filtered list of pages.</span></span>

-   <span data-ttu-id="7bf9d-136">Skriv in en del av namnet och öppna sedan listrutan för att välja från en filtrerad lista över sidor.</span><span class="sxs-lookup"><span data-stu-id="7bf9d-136">Type part of the name, and then open the drop-down list to select from a filtered list of pages.</span></span>
-   <span data-ttu-id="7bf9d-137">Öppna listrutan och klicka antingen på rubriken **Sök namn** högst upp i listan eller på rubriken **Sök AOT-namn**.</span><span class="sxs-lookup"><span data-stu-id="7bf9d-137">Open the drop-down list, and then click either the **Page name** heading at the top of the list or the **Page AOT name** heading.</span></span> <span data-ttu-id="7bf9d-138">Efter detta öppnas en dialogruta där du kan använda avancerada filtreringsalternativ såsom **Sidnamn som börjar med**.</span><span class="sxs-lookup"><span data-stu-id="7bf9d-138">A dialog box appears, where you can use advanced filtering options, such as **Page name begins with**.</span></span>
-   <span data-ttu-id="7bf9d-139">Skriv in hela namnet på sidan.</span><span class="sxs-lookup"><span data-stu-id="7bf9d-139">Type the full name of the page.</span></span> <span data-ttu-id="7bf9d-140">När du använder det här alternativet är det bäst att öppna listrutan och se vad mer som finns i listan, även om fältbeskrivningar visas.</span><span class="sxs-lookup"><span data-stu-id="7bf9d-140">When you use this option, it's best to open the drop-down list and see what else is in the list, even if field descriptions are shown.</span></span>
    -   <span data-ttu-id="7bf9d-141">Om det finns en enskild exakt matchning på namnet visas fältbeskrivningarna för den sidan.</span><span class="sxs-lookup"><span data-stu-id="7bf9d-141">If there is a single exact match to the name, the field descriptions for that page are shown.</span></span>
    -   <span data-ttu-id="7bf9d-142">Om det finns fler än en exakt matchning visas inga beskrivningar.</span><span class="sxs-lookup"><span data-stu-id="7bf9d-142">If there is more than one exact match, no descriptions are shown.</span></span> <span data-ttu-id="7bf9d-143">Du måste öppna listrutan och välja sida.</span><span class="sxs-lookup"><span data-stu-id="7bf9d-143">You must open the drop-down list and select the page that you want.</span></span>
    -   <span data-ttu-id="7bf9d-144">Om namnet du angav är en del av namnet på en annan sida ser du beskrivningarna av sidan.</span><span class="sxs-lookup"><span data-stu-id="7bf9d-144">If the name that you typed is part of the name of another page, you see the descriptions for your page.</span></span> <span data-ttu-id="7bf9d-145">Om du öppnar listrutan kan du se ytterligare sidor som innehåller det aktuella namnet.</span><span class="sxs-lookup"><span data-stu-id="7bf9d-145">However, if you open the drop-down list, you see additional pages that contain that name.</span></span>

<span data-ttu-id="7bf9d-146">Inga beskrivningar visas om du exempelvis skriver **Inventering** i fältet ****Välj en sida****.</span><span class="sxs-lookup"><span data-stu-id="7bf9d-146">For example, no descriptions are shown when you type **Counting** in the ****Select a page**** field.</span></span> <span data-ttu-id="7bf9d-147">Om du öppnar listrutan och ser du att det finns två sidor med namnet **Inventering** och flera sidor som innehåller ordet "Inventering".</span><span class="sxs-lookup"><span data-stu-id="7bf9d-147">You open the drop-down list, and see that there are two pages that have the name **Counting** and several pages that contain the word "Counting" in the name.</span></span> <span data-ttu-id="7bf9d-148">Om du väljer sidan med AOT-namnet **InventJournalCount** visas fältbeskrivningarna för den sidan.</span><span class="sxs-lookup"><span data-stu-id="7bf9d-148">If you select the page that has the AOT name **InventJournalCount**, the field descriptions are shown for that page.</span></span> <span data-ttu-id="7bf9d-149">Om du öppnar listrutan igen ser du att listan nu innehåller alla sidor som har "InventJournalCount" som en del i AOT-sidans namn.</span><span class="sxs-lookup"><span data-stu-id="7bf9d-149">However, if you open the drop-down list again, you will see that the list now contains all pages that have "InventJournalCount" as part of their AOT name.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="7bf9d-150">Felsökning</span><span class="sxs-lookup"><span data-stu-id="7bf9d-150">Troubleshooting</span></span>
<span data-ttu-id="7bf9d-151">Det här avsnittet innehåller information som hjälper dig att felsöka problem som kan uppstå när du använder fältbeskrivningar.</span><span class="sxs-lookup"><span data-stu-id="7bf9d-151">This section provides information to help you troubleshoot issues that you might encounter when you use field descriptions.</span></span>

### <a name="i-cant-find-a-field-description"></a><span data-ttu-id="7bf9d-152">Jag kan inte hitta en fältbeskrivning</span><span class="sxs-lookup"><span data-stu-id="7bf9d-152">I can't find a field description</span></span>

<span data-ttu-id="7bf9d-153">Vi håller på att lägga till beskrivningar av de mer komplexa fälten.</span><span class="sxs-lookup"><span data-stu-id="7bf9d-153">We’re in the process of adding descriptions for the more complex fields.</span></span> <span data-ttu-id="7bf9d-154">Om du behöver hjälp med ett visst fält kan du kontakta oss genom att lägga till en kommentar i det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="7bf9d-154">If you require help for a particular field, let us know by adding a comment for this topic.</span></span>

### <a name="the-field-description-isnt-helpful"></a><span data-ttu-id="7bf9d-155">Fältbeskrivningen är inte till någon hjälp</span><span class="sxs-lookup"><span data-stu-id="7bf9d-155">The field description isn't helpful</span></span>

<span data-ttu-id="7bf9d-156">Kontakta oss genom att lägga till en kommentar i det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="7bf9d-156">Let us know by adding a comment for this topic.</span></span> <span data-ttu-id="7bf9d-157">Beskriv gärna vilken ytterligare information du behöver.</span><span class="sxs-lookup"><span data-stu-id="7bf9d-157">If you can, describe the additional information that you require.</span></span>

### <a name="i-cant-find-a-field-on-the-field-descriptions-page"></a><span data-ttu-id="7bf9d-158">Jag kan inte hitta ett fält på sidan Fältbeskrivningar.</span><span class="sxs-lookup"><span data-stu-id="7bf9d-158">I can't find a field on the Field descriptions page</span></span>

<span data-ttu-id="7bf9d-159">Ställ in alternativet **Inkludera fält utan en beskrivning** på **Ja** om du vill visa alla fälten på en sida.</span><span class="sxs-lookup"><span data-stu-id="7bf9d-159">To show all the fields on a page, set the **Include fields without a description** option to **Yes**.</span></span> <span data-ttu-id="7bf9d-160">Klicka på fältet **Välj en sida** för att kontrollera att du har markerat rätt sida.</span><span class="sxs-lookup"><span data-stu-id="7bf9d-160">Click the **Select a page** field to verify that you've selected the correct page.</span></span> <span data-ttu-id="7bf9d-161">Om namnet du angav är en del av ett annat fältnamn kanske du har markerat en sida med ett längre namn.</span><span class="sxs-lookup"><span data-stu-id="7bf9d-161">If the name that you typed is part of another field name, you might have selected the page that has the longer name.</span></span>

### <a name="i-cant-find-a-page-on-the-field-descriptions-page"></a><span data-ttu-id="7bf9d-162">Jag kan inte hitta en sida på sidan Fältbeskrivningar.</span><span class="sxs-lookup"><span data-stu-id="7bf9d-162">I can't find a page on the Field descriptions page</span></span>

<span data-ttu-id="7bf9d-163">Information om olika sätt att hitta sidor hittar du i avsnittet "Söka efter sidor" tidigare i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="7bf9d-163">For information about the various way to find pages, see the "Searching for pages" section earlier in this article.</span></span> <span data-ttu-id="7bf9d-164">Om du har skrivit in sidans exakta namn kan det hända att fältbeskrivningarna inte visas om det finns fler än en sida med samma namn.</span><span class="sxs-lookup"><span data-stu-id="7bf9d-164">If you've typed the exact name of the page, the field descriptions might not be shown if more than one page has the same name.</span></span> <span data-ttu-id="7bf9d-165">Klicka på pilen i fältet **Välj en sida** om du vill öppna en filtrerad lista över de sidor som är tillgängliga.</span><span class="sxs-lookup"><span data-stu-id="7bf9d-165">Click the arrow in the **Select a page** field to open a filtered list of the pages that are available.</span></span>

<a name="see-also"></a><span data-ttu-id="7bf9d-166">Se även</span><span class="sxs-lookup"><span data-stu-id="7bf9d-166">See also</span></span>
--------

[<span data-ttu-id="7bf9d-167">Hjälp för Anpassa fält</span><span class="sxs-lookup"><span data-stu-id="7bf9d-167">Customize field help</span></span>](../../dev-itpro/user-interface/customize-field-help.md)





