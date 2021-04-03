---
title: Visa och exportera fältbeskrivningar
description: Den här artikeln innehåller en beskrivning av hur du visar fältbeskrivningar och hur du använder sidan Fältbeskrivningar vid export av beskrivningar.
author: rschloma
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: FieldDescriptions
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.custom: 11534
ms.assetid: e2795f51-a8a7-4c74-bdb9-b1be93bdd358
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 265b540ba36b7526a8d6cb64f29157b6126e4dae
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/09/2021
ms.locfileid: "5566208"
---
# <a name="view-and-export-field-descriptions"></a><span data-ttu-id="9ad14-103">Visa och exportera fältbeskrivningar</span><span class="sxs-lookup"><span data-stu-id="9ad14-103">View and export field descriptions</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="9ad14-104">Den här artikeln innehåller en beskrivning av hur du visar fältbeskrivningar och hur du använder sidan Fältbeskrivningar vid export av beskrivningar.</span><span class="sxs-lookup"><span data-stu-id="9ad14-104">This article describes how to view field descriptions and how to use the Field descriptions page to export descriptions.</span></span>

<span data-ttu-id="9ad14-105">Vissa av de mer komplexa fälten har fältbeskrivningar.</span><span class="sxs-lookup"><span data-stu-id="9ad14-105">Some of the more complex fields have field descriptions.</span></span> <span data-ttu-id="9ad14-106">Dessa beskrivningar visas när du håller muspekaren över ett fält.</span><span class="sxs-lookup"><span data-stu-id="9ad14-106">These descriptions appear when you hover over a field.</span></span> <span data-ttu-id="9ad14-107">På sidan **Fältbeskrivningar** kan du visa och exportera fältbeskrivningar.</span><span class="sxs-lookup"><span data-stu-id="9ad14-107">You can also view and export descriptions on the **Field descriptions** page.</span></span>

<span data-ttu-id="9ad14-108">Inte alla sidor har fältbeskrivningar.</span><span class="sxs-lookup"><span data-stu-id="9ad14-108">Not all pages have field descriptions.</span></span> <span data-ttu-id="9ad14-109">Vi tillhandahåller enbart beskrivningar av de mer komplexa fälten och inte av dem där användningen av fältet är tydligt.</span><span class="sxs-lookup"><span data-stu-id="9ad14-109">We want to provide descriptions only for the more complex fields, not where the use of the field is obvious.</span></span> <span data-ttu-id="9ad14-110">Av den anledningen saknas fältbeskrivningar på vissa sidor. Andra sidor innehåller några få beskrivningar och några av de mer komplexa sidorna, till exempel många av parametersidorna, har många beskrivningar.</span><span class="sxs-lookup"><span data-stu-id="9ad14-110">Therefore, some pages don't have any field descriptions, some pages have a few descriptions, and some of the more complex pages, such as many of the parameters pages, have many descriptions.</span></span>

<span data-ttu-id="9ad14-111">Om du har tillgång till utvecklingsmiljön kan du lägga till egna fältbeskrivningar och anpassa befintliga beskrivningar.</span><span class="sxs-lookup"><span data-stu-id="9ad14-111">If you have access to the development environment, you can add new field descriptions and customize existing descriptions.</span></span> <span data-ttu-id="9ad14-112">Du kan till exempel lägga till företagsspecifik information i en fältbeskrivning.</span><span class="sxs-lookup"><span data-stu-id="9ad14-112">For example, you can add company-specific information to a field description.</span></span> <span data-ttu-id="9ad14-113">Mer information hittar du i [Beskrivning av Anpassa fält](../../dev-itpro/user-interface/customize-field-help.md).</span><span class="sxs-lookup"><span data-stu-id="9ad14-113">For more information, see [Customize field descriptions](../../dev-itpro/user-interface/customize-field-help.md).</span></span>

## <a name="see-field-descriptions-in-the-user-interface"></a><span data-ttu-id="9ad14-114">Se fältbeskrivningarna i användargränssnittet.</span><span class="sxs-lookup"><span data-stu-id="9ad14-114">See field descriptions in the user interface</span></span>

<span data-ttu-id="9ad14-115">Du kan visa fältbeskrivningar genom att hovra över ett fält.</span><span class="sxs-lookup"><span data-stu-id="9ad14-115">You can view field descriptions by hovering over a field.</span></span> <span data-ttu-id="9ad14-116">Om det inte finns någon beskrivning ser du fältnamnet när du för muspekaren över fältet.</span><span class="sxs-lookup"><span data-stu-id="9ad14-116">If no description is available, you see the field name when you hover over the field.</span></span>

> [!NOTE]
> <span data-ttu-id="9ad14-117">Fältbeskrivningar AX 7.0 (februari 2016) kan endast visas på sidan **Fältbeskrivningar**.</span><span class="sxs-lookup"><span data-stu-id="9ad14-117">In Dynamics AX 7.0 (February 2016), field descriptions can be viewed only on the **Field descriptions** page.</span></span>

<span data-ttu-id="9ad14-118">I följande illustration visas fältbeskrivningen som visas när du för muspekaren över fältet **Lås artiklar under inventeringen**.</span><span class="sxs-lookup"><span data-stu-id="9ad14-118">The following illustration shows the field description that appears when you hover over the **Lock items during count** field.</span></span>

<span data-ttu-id="9ad14-119">[![Exempel på en fältbeskrivning](./media/field-description.png)](./media/field-description.png)</span><span class="sxs-lookup"><span data-stu-id="9ad14-119">[![Example of a field description](./media/field-description.png)](./media/field-description.png)</span></span>

## <a name="use-the-field-descriptions-page-to-view-and-export-field-help"></a><span data-ttu-id="9ad14-120">Använd sidan Fältbeskrivningar för att visa och exportera hjälp för fält.</span><span class="sxs-lookup"><span data-stu-id="9ad14-120">Use the Field descriptions page to view and export field help</span></span>

<span data-ttu-id="9ad14-121">På sidan **Fältbeskrivningar** kan du visa och exportera fältbeskrivningar.</span><span class="sxs-lookup"><span data-stu-id="9ad14-121">The **Field descriptions** page lets you view and export field descriptions.</span></span> <span data-ttu-id="9ad14-122">Du kan se de beskrivningar som är tillgängliga en sida i taget.</span><span class="sxs-lookup"><span data-stu-id="9ad14-122">You can see the descriptions that are available for one page at a time.</span></span>

### <a name="view-the-descriptions-for-a-page"></a><span data-ttu-id="9ad14-123">Visa beskrivningarna för en sida</span><span class="sxs-lookup"><span data-stu-id="9ad14-123">View the descriptions for a page</span></span>

<span data-ttu-id="9ad14-124">Visa beskrivningarna för en sida genom att följa det här steget:</span><span class="sxs-lookup"><span data-stu-id="9ad14-124">To view the descriptions for a page, follow this step.</span></span>

- <span data-ttu-id="9ad14-125">Ange sidan namn i fältet **Välj en sida**.</span><span class="sxs-lookup"><span data-stu-id="9ad14-125">In the **Select a page** field, type the name of the page.</span></span> <span data-ttu-id="9ad14-126">Du kan också klicka på pilen om du vill öppna en lista över alla sidor och sedan bläddra i eller filtrera listan.</span><span class="sxs-lookup"><span data-stu-id="9ad14-126">Alternatively, click the arrow to open a list of all the pages, and then browse or filter the list.</span></span>

<span data-ttu-id="9ad14-127">Du kan antingen använda sidans namn som visas i användargränssnittet (UI) (till exempel **Kunder**) eller kodnamnet (AOT-namn) som visas när du högerklickar på en sida (till exempel **CustTable**).</span><span class="sxs-lookup"><span data-stu-id="9ad14-127">You can use either the name of the page that is shown in the user interface (UI) (for example, **Customers**) or the code name (AOT name) that's available when you right-click a page (for example, **CustTable**).</span></span>

<span data-ttu-id="9ad14-128">Information om olika sätt att filtrera listan över sidor hittar du i avsnittet "Söka efter en sida" senare i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="9ad14-128">For information about the various ways to filter the list of pages, see the "Searching for a page" section later in this article.</span></span>

<span data-ttu-id="9ad14-129">Om du ställer in alternativet **Inkludera fält utan en beskrivning** till **Ja** kommer alla fält på sidan att visas, oavsett om de har en fältbeskrivning eller inte.</span><span class="sxs-lookup"><span data-stu-id="9ad14-129">If you set the **Include fields without a description** option to **Yes**, all the fields on the page are shown, even if they don't have a field description.</span></span>

### <a name="export-the-descriptions-for-a-page"></a><span data-ttu-id="9ad14-130">Exportera beskrivningarna för en sida</span><span class="sxs-lookup"><span data-stu-id="9ad14-130">Export the descriptions for a page</span></span>

<span data-ttu-id="9ad14-131">Om du vill exportera beskrivningarna för en sida ska du följa de här stegen:</span><span class="sxs-lookup"><span data-stu-id="9ad14-131">To export the descriptions for a page, follow these steps.</span></span>

1. <span data-ttu-id="9ad14-132">Välj en sida i fältet **Välj en sida**.</span><span class="sxs-lookup"><span data-stu-id="9ad14-132">In the **Select a page** field, select a page.</span></span>
2. <span data-ttu-id="9ad14-133">Klicka på **Öppna i Microsoft Office** i det övre högra hörnet och klicka sedan på **FieldDescriptionTmp**.</span><span class="sxs-lookup"><span data-stu-id="9ad14-133">Click the **Open in Microsoft Office** button in the upper-right corner, and then click **FieldDescriptionTmp**.</span></span>

### <a name="searching-for-a-page"></a><span data-ttu-id="9ad14-134">Söka efter en sida</span><span class="sxs-lookup"><span data-stu-id="9ad14-134">Searching for a page</span></span>

<span data-ttu-id="9ad14-135">Det finns flera sätt att söka efter en sida i fältet **Välj en sida**.</span><span class="sxs-lookup"><span data-stu-id="9ad14-135">There are several ways to search for a page in the **Select a page** field.</span></span> <span data-ttu-id="9ad14-136">I många fall måste du klicka på pilen i fältet **Välj en sida** om du vill öppna listrutan och sedan välja från en filtrerad lista över sidor.</span><span class="sxs-lookup"><span data-stu-id="9ad14-136">In many cases, you must click the arrow in the **Select a page** field to open the drop-down list, and then select from a filtered list of pages.</span></span>

- <span data-ttu-id="9ad14-137">Skriv in en del av namnet och öppna sedan listrutan för att välja från en filtrerad lista över sidor.</span><span class="sxs-lookup"><span data-stu-id="9ad14-137">Type part of the name, and then open the drop-down list to select from a filtered list of pages.</span></span>
- <span data-ttu-id="9ad14-138">Öppna listrutan och klicka antingen på rubriken **Sök namn** högst upp i listan eller på rubriken **Sök AOT-namn**.</span><span class="sxs-lookup"><span data-stu-id="9ad14-138">Open the drop-down list, and then click either the **Page name** heading at the top of the list or the **Page AOT name** heading.</span></span> <span data-ttu-id="9ad14-139">Efter detta öppnas en dialogruta där du kan använda avancerada filtreringsalternativ såsom **Sidnamn som börjar med**.</span><span class="sxs-lookup"><span data-stu-id="9ad14-139">A dialog box appears, where you can use advanced filtering options, such as **Page name begins with**.</span></span>
- <span data-ttu-id="9ad14-140">Skriv in hela namnet på sidan.</span><span class="sxs-lookup"><span data-stu-id="9ad14-140">Type the full name of the page.</span></span> <span data-ttu-id="9ad14-141">När du använder det här alternativet är det bäst att öppna listrutan och se vad mer som finns i listan, även om fältbeskrivningar visas.</span><span class="sxs-lookup"><span data-stu-id="9ad14-141">When you use this option, it's best to open the drop-down list and see what else is in the list, even if field descriptions are shown.</span></span>

    - <span data-ttu-id="9ad14-142">Om det finns en enskild exakt matchning på namnet visas fältbeskrivningarna för den sidan.</span><span class="sxs-lookup"><span data-stu-id="9ad14-142">If there is a single exact match to the name, the field descriptions for that page are shown.</span></span>
    - <span data-ttu-id="9ad14-143">Om det finns fler än en exakt matchning visas inga beskrivningar.</span><span class="sxs-lookup"><span data-stu-id="9ad14-143">If there is more than one exact match, no descriptions are shown.</span></span> <span data-ttu-id="9ad14-144">Du måste öppna listrutan och välja sida.</span><span class="sxs-lookup"><span data-stu-id="9ad14-144">You must open the drop-down list and select the page that you want.</span></span>
    - <span data-ttu-id="9ad14-145">Om namnet du angav är en del av namnet på en annan sida ser du beskrivningarna av sidan.</span><span class="sxs-lookup"><span data-stu-id="9ad14-145">If the name that you typed is part of the name of another page, you see the descriptions for your page.</span></span> <span data-ttu-id="9ad14-146">Om du öppnar listrutan kan du se ytterligare sidor som innehåller det aktuella namnet.</span><span class="sxs-lookup"><span data-stu-id="9ad14-146">However, if you open the drop-down list, you see additional pages that contain that name.</span></span>

<span data-ttu-id="9ad14-147">Inga beskrivningar visas om du exempelvis skriver **Inventering** i fältet **Välj en sida**.</span><span class="sxs-lookup"><span data-stu-id="9ad14-147">For example, no descriptions are shown when you type **Counting** in the **Select a page** field.</span></span> <span data-ttu-id="9ad14-148">Om du öppnar listrutan och ser du att det finns två sidor med namnet **Inventering** och flera sidor som innehåller ordet "Inventering".</span><span class="sxs-lookup"><span data-stu-id="9ad14-148">You open the drop-down list, and see that there are two pages that have the name **Counting** and several pages that contain the word "Counting" in the name.</span></span> <span data-ttu-id="9ad14-149">Om du väljer sidan med AOT-namnet **InventJournalCount** visas fältbeskrivningarna för den sidan.</span><span class="sxs-lookup"><span data-stu-id="9ad14-149">If you select the page that has the AOT name **InventJournalCount**, the field descriptions are shown for that page.</span></span> <span data-ttu-id="9ad14-150">Om du öppnar listrutan igen ser du att listan nu innehåller alla sidor som har "InventJournalCount" som en del i AOT-sidans namn.</span><span class="sxs-lookup"><span data-stu-id="9ad14-150">However, if you open the drop-down list again, you will see that the list now contains all pages that have "InventJournalCount" as part of their AOT name.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="9ad14-151">Felsökning</span><span class="sxs-lookup"><span data-stu-id="9ad14-151">Troubleshooting</span></span>

<span data-ttu-id="9ad14-152">Det här avsnittet innehåller information som hjälper dig att felsöka problem som kan uppstå när du använder fältbeskrivningar.</span><span class="sxs-lookup"><span data-stu-id="9ad14-152">This section provides information to help you troubleshoot issues that you might encounter when you use field descriptions.</span></span>

### <a name="i-cant-find-a-field-description"></a><span data-ttu-id="9ad14-153">Jag kan inte hitta en fältbeskrivning</span><span class="sxs-lookup"><span data-stu-id="9ad14-153">I can't find a field description</span></span>

<span data-ttu-id="9ad14-154">Vi håller på att lägga till beskrivningar av de mer komplexa fälten.</span><span class="sxs-lookup"><span data-stu-id="9ad14-154">We're in the process of adding descriptions for the more complex fields.</span></span> <span data-ttu-id="9ad14-155">Om du behöver hjälp med ett visst fält kan du kontakta oss genom att lägga till en kommentar i det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="9ad14-155">If you require help for a particular field, let us know by adding a comment for this topic.</span></span>

### <a name="the-field-description-isnt-helpful"></a><span data-ttu-id="9ad14-156">Fältbeskrivningen är inte till någon hjälp</span><span class="sxs-lookup"><span data-stu-id="9ad14-156">The field description isn't helpful</span></span>

<span data-ttu-id="9ad14-157">Kontakta oss genom att lägga till en kommentar i det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="9ad14-157">Let us know by adding a comment for this topic.</span></span> <span data-ttu-id="9ad14-158">Beskriv gärna vilken ytterligare information du behöver.</span><span class="sxs-lookup"><span data-stu-id="9ad14-158">If you can, describe the additional information that you require.</span></span>

### <a name="i-cant-find-a-field-on-the-field-descriptions-page"></a><span data-ttu-id="9ad14-159">Jag kan inte hitta ett fält på sidan Fältbeskrivningar.</span><span class="sxs-lookup"><span data-stu-id="9ad14-159">I can't find a field on the Field descriptions page</span></span>

<span data-ttu-id="9ad14-160">Ställ in alternativet **Inkludera fält utan en beskrivning** på **Ja** om du vill visa alla fälten på en sida.</span><span class="sxs-lookup"><span data-stu-id="9ad14-160">To show all the fields on a page, set the **Include fields without a description** option to **Yes**.</span></span> <span data-ttu-id="9ad14-161">Klicka på fältet **Välj en sida** för att kontrollera att du har markerat rätt sida.</span><span class="sxs-lookup"><span data-stu-id="9ad14-161">Click the **Select a page** field to verify that you've selected the correct page.</span></span> <span data-ttu-id="9ad14-162">Om namnet du angav är en del av ett annat fältnamn kanske du har markerat en sida med ett längre namn.</span><span class="sxs-lookup"><span data-stu-id="9ad14-162">If the name that you typed is part of another field name, you might have selected the page that has the longer name.</span></span>

### <a name="i-cant-find-a-page-on-the-field-descriptions-page"></a><span data-ttu-id="9ad14-163">Jag kan inte hitta en sida på sidan Fältbeskrivningar.</span><span class="sxs-lookup"><span data-stu-id="9ad14-163">I can't find a page on the Field descriptions page</span></span>

<span data-ttu-id="9ad14-164">Information om olika sätt att hitta sidor hittar du i avsnittet "Söka efter sidor" tidigare i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="9ad14-164">For information about the various way to find pages, see the "Searching for pages" section earlier in this article.</span></span> <span data-ttu-id="9ad14-165">Om du har skrivit in sidans exakta namn kan det hända att fältbeskrivningarna inte visas om det finns fler än en sida med samma namn.</span><span class="sxs-lookup"><span data-stu-id="9ad14-165">If you've typed the exact name of the page, the field descriptions might not be shown if more than one page has the same name.</span></span> <span data-ttu-id="9ad14-166">Klicka på pilen i fältet **Välj en sida** om du vill öppna en filtrerad lista över de sidor som är tillgängliga.</span><span class="sxs-lookup"><span data-stu-id="9ad14-166">Click the arrow in the **Select a page** field to open a filtered list of the pages that are available.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="9ad14-167">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="9ad14-167">Additional resources</span></span>

[<span data-ttu-id="9ad14-168">Anpassa fältbeskrivningar</span><span class="sxs-lookup"><span data-stu-id="9ad14-168">Customize field descriptions</span></span>](../../dev-itpro/user-interface/customize-field-help.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]