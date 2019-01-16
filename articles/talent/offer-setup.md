---
title: "Ställa in erbjudandehantering"
description: "I det här avsnittet beskrivs hur du ställer in erbjudanden i Talent."
author: josaw
manager: AnnBe
ms.date: 12/07/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Talent
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2018-10-18
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: be66d9f95551066bb8bc25445c652d4fa59066d4
ms.openlocfilehash: bb90f0a3c87c64a74ca63610105abfeb8223900a
ms.contentlocale: sv-se
ms.lasthandoff: 12/07/2018

---
# <a name="set-up-offer-management"></a><span data-ttu-id="e0d18-103">Ställa in erbjudandehantering</span><span class="sxs-lookup"><span data-stu-id="e0d18-103">Set up offer management</span></span> 

[!include [banner](includes/banner.md)]

<span data-ttu-id="e0d18-104">När en kandidat flyttas till erbjudandefasen i Dynamics 365 for Talent: Attract, måste du se till att erbjudandena snabbt kan skapas för kandidater, godkännas efter behov och skickas ut till kandidaten.</span><span class="sxs-lookup"><span data-stu-id="e0d18-104">When a candidate is moved to the offer stage in Dynamics 365 for Talent: Attract, you need to ensure that the offers can be quickly created for the candidate, approved as necessary, and sent out to the candidate.</span></span> <span data-ttu-id="e0d18-105">Eftersom de flesta erbjudanden är standard måste de skapas från återanvändningsbara mallar.</span><span class="sxs-lookup"><span data-stu-id="e0d18-105">Because most offers are standard, they can be created from reusable templates.</span></span> <span data-ttu-id="e0d18-106">I Attract samlas alla erbjudanden i ett erbjudandepaket som består av ett eller flera erbjudandedokument.</span><span class="sxs-lookup"><span data-stu-id="e0d18-106">In Attract, all offers are rolled into an offer package, which is a collection of one or more offer documents.</span></span> 

<span data-ttu-id="e0d18-107">Det här avsnittet beskriver de steg som en Attract-administratör skulle följa för att konfigurera olika erbjudandepaketmallar som en del av erbjudandehanteringen i Attract.</span><span class="sxs-lookup"><span data-stu-id="e0d18-107">This topic lists all the steps that an Attract administrator would follow to set up different offer package templates as part of the offer management capability in Attract.</span></span> <span data-ttu-id="e0d18-108">Användare som inte har administratörsroll har inte åtkomst till dessa funktioner.</span><span class="sxs-lookup"><span data-stu-id="e0d18-108">Users with non-administrator roles will not have access to these capabilities.</span></span>

>[!NOTE]
> <span data-ttu-id="e0d18-109">Erbjudandehanteringsfunktioner är tillgängliga som en del av tillägget för omfattande anställning.</span><span class="sxs-lookup"><span data-stu-id="e0d18-109">Offer management capabilities are available as part of the Comprehensive Hiring Add-On.</span></span>

## <a name="offer-data"></a><span data-ttu-id="e0d18-110">Erbjudandedata</span><span class="sxs-lookup"><span data-stu-id="e0d18-110">Offer data</span></span> 

<span data-ttu-id="e0d18-111">Erbjudandedata utgör den minsta enheten inne i erbjudandepaketmallen.</span><span class="sxs-lookup"><span data-stu-id="e0d18-111">Offer data is the smallest unit inside the offer package template.</span></span> <span data-ttu-id="e0d18-112">Ett typiskt erbjudande består av standardtext och en uppsättning värden.</span><span class="sxs-lookup"><span data-stu-id="e0d18-112">A typical offer consists of standard text and a set of values.</span></span> <span data-ttu-id="e0d18-113">Uppsättningar med värden är de enda enheter som kan ändras mellan erbjudanden.</span><span class="sxs-lookup"><span data-stu-id="e0d18-113">The sets of values are the only pieces that could change between offers.</span></span> <span data-ttu-id="e0d18-114">När du skapar erbjudandet är den viktigaste aspekten att den person som skapat erbjudandet kan fokusera på listan med platshållare för erbjudandedata som finns i erbjudandepaketmallen.</span><span class="sxs-lookup"><span data-stu-id="e0d18-114">During the offer creation, the most important aspect that the offer creator can focus on is the list of offer data placeholders present in an offer package template.</span></span> <span data-ttu-id="e0d18-115">Gör följande om du vill ställa in erbjudandedata.</span><span class="sxs-lookup"><span data-stu-id="e0d18-115">To set up offer data, do the following.</span></span>

1.  <span data-ttu-id="e0d18-116">Gå till **Erbjudandehantering**.</span><span class="sxs-lookup"><span data-stu-id="e0d18-116">Go to **Offer management**.</span></span>

1.  <span data-ttu-id="e0d18-117">Expandera avsnittet **Bibliotek** under det vänstra navigeringsfönstret och gå sedan till **erbjudandedata**.</span><span class="sxs-lookup"><span data-stu-id="e0d18-117">Expand the **Library** section in the left navigation pane, then go to **Offer data**.</span></span>

    >[!NOTE]
    > <span data-ttu-id="e0d18-118">På sidan **erbjudandedata** finns avsnitten **kandidatdetaljer** och **jobbdetaljer**.</span><span class="sxs-lookup"><span data-stu-id="e0d18-118">On the **Offer data** page are the **Candidate details** and **Job details** sections.</span></span> <span data-ttu-id="e0d18-119">Attract ger några platshållare för erbjudandedata från början.</span><span class="sxs-lookup"><span data-stu-id="e0d18-119">Attract provides a few offer data placeholders out-of-the-box.</span></span>
    
    > <span data-ttu-id="e0d18-120">Det finns avsnitt på sidan för att ordna olika platshållare för erbjudandedata i logiska grupper.</span><span class="sxs-lookup"><span data-stu-id="e0d18-120">There are sections on the page to organize different offer data placeholders together in logical groups.</span></span> <span data-ttu-id="e0d18-121">Dessa avsnitt kan hjälpa dig med underhåll av erbjudandedata och ifyllning av data under processen för skapande av erbjudandet.</span><span class="sxs-lookup"><span data-stu-id="e0d18-121">These sections can help with maintenance of offer data and population of data during the offer creation process.</span></span>

1.  <span data-ttu-id="e0d18-122">För att skapa ett nytt erbjudandedataavsnitt, klicka på **Lägg till ett avsnitt** och ange ett unikt namn för avsnittet.</span><span class="sxs-lookup"><span data-stu-id="e0d18-122">To create a new offer data section, click **Add a section** and enter a unique name for the section.</span></span>

1.  <span data-ttu-id="e0d18-123">Lägg till platshållare för erbjudandedata till ett visst avsnitt genom att klicka på **Lägg till erbjudandedata** och ange ett unikt namn för platshållaren.</span><span class="sxs-lookup"><span data-stu-id="e0d18-123">To add offer data placeholders to any section, click **Add offer data** and enter a unique name for the placeholder.</span></span>

1.  <span data-ttu-id="e0d18-124">Hovra över avsnittsnamnet om du vill redigera namnet på ett avsnitt och uppdatera namnet.</span><span class="sxs-lookup"><span data-stu-id="e0d18-124">To edit the name of any section, hover over the section name and update the name.</span></span>

1.  <span data-ttu-id="e0d18-125">Om du vill redigera namnet på befintliga platshållare för erbjudandedata, se till att platshållaren inte är en del av en mall.</span><span class="sxs-lookup"><span data-stu-id="e0d18-125">To edit the name of any existing offer data placeholder, first make sure that the placeholder is not already part of any template.</span></span> <span data-ttu-id="e0d18-126">För sedan muspekaren över namnet på platshållaren för erbjudandedata och uppdatera namnet om det behövs.</span><span class="sxs-lookup"><span data-stu-id="e0d18-126">Then, hover over the name of the offer data placeholder and update the name as needed.</span></span>

1. <span data-ttu-id="e0d18-127">Om du vill radera namnet på befintliga platshållare för erbjudandedata, se till att platshållaren inte är en del av en annan mall.</span><span class="sxs-lookup"><span data-stu-id="e0d18-127">To delete an existing offer data placeholder, first make sure that the placeholder is not part of any other template.</span></span> <span data-ttu-id="e0d18-128">För sedan muspekaren över platshållaren och när ikonen för papperskorgen visas klickar du på papperskorgen för att ta bort platshållaren för erbjudandedata.</span><span class="sxs-lookup"><span data-stu-id="e0d18-128">Then, hover over the placeholder and when the trash can icon appears, click the trash can to delete the offer data placeholder.</span></span>
    >[!NOTE]
    > <span data-ttu-id="e0d18-129">Du kan se hur många mallar som en platshållare för erbjudandedata tillhör genom nummerindikatorn bredvid varje erbjudandedata.</span><span class="sxs-lookup"><span data-stu-id="e0d18-129">You can see how many templates an offer data placeholder is part of by the number indicator next to each offer data.</span></span> 

1. <span data-ttu-id="e0d18-130">Ta bort ett avsnitt genom att hovra över namnet.</span><span class="sxs-lookup"><span data-stu-id="e0d18-130">To delete any section, hover over the name.</span></span> <span data-ttu-id="e0d18-131">Om ingen av platshållarna för erbjudandedata inuti avsnittet visas i en mall klickar du på ikonen för papperskorgen om du vill ta bort den.</span><span class="sxs-lookup"><span data-stu-id="e0d18-131">If none of the offer data placeholders inside the section appear in any template, you can click the trash can icon to delete it.</span></span> 
    >[!NOTE]
    > <span data-ttu-id="e0d18-132">Om du tar bort avsnittet, tas även alla platshållarna för erbjudandedata bort inne i avsnittet.</span><span class="sxs-lookup"><span data-stu-id="e0d18-132">Deleting the section will also delete all the offer data placeholders inside that section.</span></span>

<span data-ttu-id="e0d18-133">När platshållarna för erbjudandedata har skapats kan du använda dem över alla dokumentmallar.</span><span class="sxs-lookup"><span data-stu-id="e0d18-133">After the offer data placeholders have been set up, you can use them across any document template.</span></span> <span data-ttu-id="e0d18-134">Platshållare för erbjudandedata är inte begränsade till en specifik mall – samma uppsättning kan användas på alla mallar.</span><span class="sxs-lookup"><span data-stu-id="e0d18-134">Offer data placeholders are not restricted to a specific template -- the same set can be used across all templates.</span></span>

## <a name="offer-data-rules"></a><span data-ttu-id="e0d18-135">Regler för erbjudandedata</span><span class="sxs-lookup"><span data-stu-id="e0d18-135">Offer data rules</span></span>

<span data-ttu-id="e0d18-136">De flesta företag har regler för hur erbjudande måste skapas.</span><span class="sxs-lookup"><span data-stu-id="e0d18-136">Most organization have rules for how offers must be created.</span></span> <span data-ttu-id="e0d18-137">En organisation kan exempelvis kräva att erbjudandet för maximal årslön för en viss kombination av plats och tjänsteåldernivå måste vara inom ett visst intervall eller att det inte finns några specifika värden för erbjudandenivån för den nya anställningen.</span><span class="sxs-lookup"><span data-stu-id="e0d18-137">For example, an organization may want to require that the maximum annual salary offer for a specific location and seniority level combination has to be within a certain range, or that there are only a few specific values possible for the offer level for the new hire.</span></span> <span data-ttu-id="e0d18-138">Attract ger stöder för närvarande alla dessa dataregler genom att använda en CSV-fil.</span><span class="sxs-lookup"><span data-stu-id="e0d18-138">Attract currently supports all such data rules using a CSV file.</span></span>

<span data-ttu-id="e0d18-139">Gör följande om du vill förbereda CSV-filen med dataregler.</span><span class="sxs-lookup"><span data-stu-id="e0d18-139">To prepare the data rules CSV file, do the following.</span></span>

1.  <span data-ttu-id="e0d18-140">Bestäm platshållaren för erbjudandedata för regeluppsättningen.</span><span class="sxs-lookup"><span data-stu-id="e0d18-140">Determine the offer data placeholder for the rule set.</span></span> <span data-ttu-id="e0d18-141">Till exempel **årslön**.</span><span class="sxs-lookup"><span data-stu-id="e0d18-141">For example, **Annual Salary**.</span></span>

1.  <span data-ttu-id="e0d18-142">Identifiera det beroende platshållarvärdet för erbjudandedata.</span><span class="sxs-lookup"><span data-stu-id="e0d18-142">Identify the dependent offer data placeholder values.</span></span> <span data-ttu-id="e0d18-143">Till exempel **Plats för jobbet** och **Nivå**.</span><span class="sxs-lookup"><span data-stu-id="e0d18-143">For example, **Job Location** and **Level**.</span></span>

1.  <span data-ttu-id="e0d18-144">Ange kolumner 1 och 2 som **Plats för jobbet** och **Nivå**.</span><span class="sxs-lookup"><span data-stu-id="e0d18-144">Specify columns 1 and 2 as **Job Location** and **Level**.</span></span>

1.  <span data-ttu-id="e0d18-145">Gör kolumnerna 3 och 4 till **Årslön** om du vill överföra ett intervallvärde.</span><span class="sxs-lookup"><span data-stu-id="e0d18-145">To upload a range value, make columns 3 and 4 **Annual Salary**.</span></span> <span data-ttu-id="e0d18-146">Gör endast kolumn 3 **Årslön** om du vill överföra ett specifikt värde istället för ett intervall.</span><span class="sxs-lookup"><span data-stu-id="e0d18-146">To upload a specific value instead of a range, only make column 3 **Annual Salary**.</span></span>

1.  <span data-ttu-id="e0d18-147">Fyll i Microsoft Excel-filen utifrån dina obligatoriska roller.</span><span class="sxs-lookup"><span data-stu-id="e0d18-147">Populate the Microsoft Excel file based on your required roles.</span></span>

1.  <span data-ttu-id="e0d18-148">Kontrollera att varje rad är en unik kombination av de värden som sammanfogas.</span><span class="sxs-lookup"><span data-stu-id="e0d18-148">Ensure that each row is a unique combination of all the values put together.</span></span>

1.  <span data-ttu-id="e0d18-149">Spara filen som ett CSV-format.</span><span class="sxs-lookup"><span data-stu-id="e0d18-149">Save the file as a CSV format.</span></span>

<span data-ttu-id="e0d18-150">Gör följande om du vill överföra filen med regler för erbjudandedata.</span><span class="sxs-lookup"><span data-stu-id="e0d18-150">To upload the offer data rules file, do the following.</span></span>

1.  <span data-ttu-id="e0d18-151">Gå till **Erbjudandehantering**.</span><span class="sxs-lookup"><span data-stu-id="e0d18-151">Go to **Offer management**.</span></span>

1.  <span data-ttu-id="e0d18-152">Expandera avsnittet **Bibliotek** under det vänstra navigeringspanelen och gå sedan till **Regler för erbjudandedata**.</span><span class="sxs-lookup"><span data-stu-id="e0d18-152">Expand the **Library** section in the left navigation panel, then go to **Offer data rules**.</span></span>

1.  <span data-ttu-id="e0d18-153">Klicka på **Ny datauppsättning** för att visa dialogrutan **överför**.</span><span class="sxs-lookup"><span data-stu-id="e0d18-153">Click **New data set** to display the **Upload** dialog box.</span></span>

1.  <span data-ttu-id="e0d18-154">Ange ett unikt namn för regeluppsättningen och överför sedan den sparade CSV-filen.</span><span class="sxs-lookup"><span data-stu-id="e0d18-154">Specify a unique name for the rule set and then upload the saved CSV file.</span></span>

1.  <span data-ttu-id="e0d18-155">Klicka på **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="e0d18-155">Click **Add**.</span></span>
    <span data-ttu-id="e0d18-156">Regeluppsättningen ska bearbetas i bakgrunden och du får ett meddelande i appen och via e-post så snart den är slutförd.</span><span class="sxs-lookup"><span data-stu-id="e0d18-156">The rule set will be processed in the background and you will be notified in-app and via email once it completes.</span></span>

    <span data-ttu-id="e0d18-157">Du meddelas om fel uppstår under bearbetningen av överföringen.</span><span class="sxs-lookup"><span data-stu-id="e0d18-157">You will be notified if there are errors while processing the upload.</span></span> <span data-ttu-id="e0d18-158">Du kan sedan hämta felloggen, korrigera filen och överföra den igen.</span><span class="sxs-lookup"><span data-stu-id="e0d18-158">You can then download the error log, fix the file, and upload it again.</span></span>

1.  <span data-ttu-id="e0d18-159">Använd ellips-knappen (**...**) om du vill hämta regeluppsättningen och uppdatera uppsättningen med värden.</span><span class="sxs-lookup"><span data-stu-id="e0d18-159">Use the ellipses button (**…**) option if you want to download the rule set and update the set of values.</span></span> <span data-ttu-id="e0d18-160">När du har uppdaterat, kan du överföra filen igen.</span><span class="sxs-lookup"><span data-stu-id="e0d18-160">After updating, you can upload the file again.</span></span>

1.  <span data-ttu-id="e0d18-161">Du kan ta bort en befintlig överföring av regeluppsättning om platshållaren som definieras inte används i en annan dokumentmall.</span><span class="sxs-lookup"><span data-stu-id="e0d18-161">You can delete an existing rule set upload if the placeholder being defined is not being used in another document template.</span></span>

>[!NOTE]
> - <span data-ttu-id="e0d18-162">Varje platshållare kan bara ha en unik uppsättning kolumner som den är beroende av.</span><span class="sxs-lookup"><span data-stu-id="e0d18-162">Each placeholder can only have one unique set of columns that it is dependent on.</span></span> <span data-ttu-id="e0d18-163">Om till exempel **årslön** är beroende av **plats för jobbet** och **nivå** kan du inte överföra en annan regeluppsättning där **årslön** är beroende av en annan uppsättning kolumner.</span><span class="sxs-lookup"><span data-stu-id="e0d18-163">For example, if **Annual Salary** is dependent on **Job Location** and **Level**, you can't upload another rule set where **Annual Salary** is dependent on a different set of columns.</span></span>

> - <span data-ttu-id="e0d18-164">Du kan hämta exempel på regeluppsättningar för erbjudandedata på fliken **Exempel** på sidan **Regler för erbjudandedata**.</span><span class="sxs-lookup"><span data-stu-id="e0d18-164">You can download sample offer data rule sets on the **Samples** tab on the **Offer data rules** page.</span></span>

> - <span data-ttu-id="e0d18-165">När en person som skapat erbjudandet åsidosätter de värden som rekommenderas av regler för erbjudandedata markeras erbjudandet som icke-standardiserat och arbetsflödet för godkännande av erbjudandet kommer att vara bestämt.</span><span class="sxs-lookup"><span data-stu-id="e0d18-165">When an offer creator overrides the values that are recommended by the offer data rules, the offer is flagged as non-standard and offer approval workflow will be mandated.</span></span>

## <a name="document-templates"></a><span data-ttu-id="e0d18-166">Dokumentmallar</span><span class="sxs-lookup"><span data-stu-id="e0d18-166">Document templates</span></span>

<span data-ttu-id="e0d18-167">En erbjudandedokumentmall kan hjälpa administratörer att skapa erbjudandebrev.</span><span class="sxs-lookup"><span data-stu-id="e0d18-167">An offer document template can help administrators create offer letters.</span></span> <span data-ttu-id="e0d18-168">Erbjudandedokumentmallen är en kombination av text som ska ingå i erbjudandet samt definierade platshållare för erbjudandedata.</span><span class="sxs-lookup"><span data-stu-id="e0d18-168">The offer document template is a combination of the text that will be part of the offer as well as the defined offer data placeholders.</span></span> 

<span data-ttu-id="e0d18-169">Gör följande om du vill skapa en erbjudandedokumentmall.</span><span class="sxs-lookup"><span data-stu-id="e0d18-169">To create an offer document template, do the following.</span></span>

1.  <span data-ttu-id="e0d18-170">Gå till **Erbjudandehantering**.</span><span class="sxs-lookup"><span data-stu-id="e0d18-170">Go to **Offer management**.</span></span>

1.  <span data-ttu-id="e0d18-171">Expandera avsnittet **Bibliotek** under det vänstra navigeringsfönstret och gå till **Mallar**.</span><span class="sxs-lookup"><span data-stu-id="e0d18-171">Expand the **Library** section in the left navigation pane and go to **Templates**.</span></span>

    <span data-ttu-id="e0d18-172">Sidan **mallar** visar en lista över dokumentmallar som redan har definierats.</span><span class="sxs-lookup"><span data-stu-id="e0d18-172">The **Templates** page will display a list of document templates that have already been defined.</span></span>

1.  <span data-ttu-id="e0d18-173">Klicka på **Ny mall** om du vill skapa en ny dokumentmall.</span><span class="sxs-lookup"><span data-stu-id="e0d18-173">To create a new document template, click **New Template**.</span></span>

1.  <span data-ttu-id="e0d18-174">Ange ett unikt namn för mallen och klicka på **Skapa**.</span><span class="sxs-lookup"><span data-stu-id="e0d18-174">Enter a unique name for the template and click **Create**.</span></span>

1.  <span data-ttu-id="e0d18-175">Använd RTF-redigeraren för att sätta in och redigera innehållet i erbjudandedokumentet.</span><span class="sxs-lookup"><span data-stu-id="e0d18-175">Use the rich text editor to insert or edit the offer document content.</span></span> <span data-ttu-id="e0d18-176">Du kan infoga tabeller, bilder och hyperlänkar med hjälp av alternativen längst upp i textredigeraren.</span><span class="sxs-lookup"><span data-stu-id="e0d18-176">You can insert tables, images, and hyperlinks using the options available at the top of the text editor.</span></span>

1.  <span data-ttu-id="e0d18-177">Du kan infoga platshållare för erbjudandedata i malldokumenten för erbjudandet genom att:</span><span class="sxs-lookup"><span data-stu-id="e0d18-177">You can insert offer data placeholders in the offer template document by:</span></span>

    - <span data-ttu-id="e0d18-178">Dra och släpp från den högra rutan.</span><span class="sxs-lookup"><span data-stu-id="e0d18-178">Dragging and dropping from the right pane.</span></span>

    - <span data-ttu-id="e0d18-179">Hashtag platshållaren för erbjudandedata direkt till en position.</span><span class="sxs-lookup"><span data-stu-id="e0d18-179">Hashtag the offer data placeholder directly into position.</span></span> <span data-ttu-id="e0d18-180">Skriva **\#** och sedan börja skriva in namnet på platshållaren för erbjudandedata.</span><span class="sxs-lookup"><span data-stu-id="e0d18-180">Type **\#** and then start typing the name of the offer data placeholder.</span></span> <span data-ttu-id="e0d18-181">Alternativen visas i den nedrullningsbara listan.</span><span class="sxs-lookup"><span data-stu-id="e0d18-181">Options will appear in the drop-down list.</span></span> <span data-ttu-id="e0d18-182">Klicka eller tryck på **ange** för att infoga platshållaren för erbjudandedata.</span><span class="sxs-lookup"><span data-stu-id="e0d18-182">Click or press **Enter** to insert the offer data placeholder.</span></span>

    >[!NOTE]
    > - <span data-ttu-id="e0d18-183">Hovra över platshållaren för erbjudandedata om du vill associera en platshållare till dokumentmallen för erbjudandet utan att visa dess värde för kandidaten och klicka på **fäst**-ikonen.</span><span class="sxs-lookup"><span data-stu-id="e0d18-183">To associate a placeholder to the offer document template without exposing its value to the candidate, hover over the offer data placeholder and click the **Pin** icon.</span></span> <span data-ttu-id="e0d18-184">Detta för platshållaren till avsnittet **Fästa erbjudandedata** av dokumentmallen för erbjudandet.</span><span class="sxs-lookup"><span data-stu-id="e0d18-184">This will push the placeholder to the **Pinned offer data** section of the offer document template.</span></span> <span data-ttu-id="e0d18-185">Ta bort genom att följa samma steg men klicka på **ta bort** i listan över platshållare för erbjudandedata.</span><span class="sxs-lookup"><span data-stu-id="e0d18-185">To unpin, follow the same steps but click **Unpin** in the list of offer data placeholders.</span></span>

    > - <span data-ttu-id="e0d18-186">Om du vill visa listan över aktiva platshållare för erbjudandedata, växla till fliken **aktiva** i det högra fönstret.</span><span class="sxs-lookup"><span data-stu-id="e0d18-186">To view the list of active offer data placeholders, switch to the **Active** tab in the right pane.</span></span>

    > - <span data-ttu-id="e0d18-187">Om du infogar en platshållare som drivs av en regeluppsättning för erbjudandedata visas beroendet för den platshållaren för erbjudandedata på andra värden.</span><span class="sxs-lookup"><span data-stu-id="e0d18-187">If you insert a placeholder that is driven by an offer data rule set, you can see the dependency of that offer data placeholder on other values.</span></span>

    > - <span data-ttu-id="e0d18-188">Alternativt kan du **Importera** innehåll från en .docx-fil på den lokala datorn och redigera efter behov.</span><span class="sxs-lookup"><span data-stu-id="e0d18-188">Alternatively, you can **Import** the content from a .docx file on your local machine and edit as required.</span></span> <span data-ttu-id="e0d18-189">På så sätt måste du inte skriva in allt innehåll i redigeraren.</span><span class="sxs-lookup"><span data-stu-id="e0d18-189">That way, you don’t have to type in all the content in the editor.</span></span>

1. <span data-ttu-id="e0d18-190">Om du vill förhandsgranska erbjudandedokumentet, använd alternativet **förhandsgranskning** överst på sidan.</span><span class="sxs-lookup"><span data-stu-id="e0d18-190">To preview the offer document, use the **Preview** option at the top of the page.</span></span>

1. <span data-ttu-id="e0d18-191">För att kontrollera om en person som skapat erbjudandet kan redigera erbjudandedokumentets innehåll, använd alternativet **hantera behörighet** överst på sidan.</span><span class="sxs-lookup"><span data-stu-id="e0d18-191">To control whether an offer creator can edit the offer document content, use the **Manage permission** option at the top of the page.</span></span> <span data-ttu-id="e0d18-192">Om du vill att personen som skapade erbjudandet endast ska infoga platshållarvärden och inte redigera text, anger du behörighetsvärdet till **Nej**.</span><span class="sxs-lookup"><span data-stu-id="e0d18-192">If you want the offer creator to only insert placeholder values and not edit text, set the permission value to **No**.</span></span>

1. <span data-ttu-id="e0d18-193">Spara framstegen genom att klicka på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="e0d18-193">Click **Save** to save your progress.</span></span> <span data-ttu-id="e0d18-194">Mallen sparas i utkastform.</span><span class="sxs-lookup"><span data-stu-id="e0d18-194">The template will be saved in a draft state.</span></span>

1. <span data-ttu-id="e0d18-195">För att avsluta och markera dokumentet som publicerat klickar du på **Slutför**.</span><span class="sxs-lookup"><span data-stu-id="e0d18-195">To finalize and mark the document as published, click **Finish**.</span></span>

1. <span data-ttu-id="e0d18-196">Du kan se vilka dokumentmallar som för närvarande är aktiva, i utkastläget, och som har arkiverats och inte längre används av upplevelsen för biblioteket för dokumentmallar.</span><span class="sxs-lookup"><span data-stu-id="e0d18-196">You can see which document templates are currently active, in draft mode, and have been archived and are no longer in use on the document templates library landing experience.</span></span>

>[!NOTE]
> <span data-ttu-id="e0d18-197">Du kan ta bort alla erbjudandedokumentmallar som inte är en del av en befintlig erbjudandepaketmall.</span><span class="sxs-lookup"><span data-stu-id="e0d18-197">You can delete any offer document template that is not part of an existing offer package template.</span></span>


## <a name="offer-package-templates"></a><span data-ttu-id="e0d18-198">Erbjudandepaketmallar</span><span class="sxs-lookup"><span data-stu-id="e0d18-198">Offer package templates</span></span>

<span data-ttu-id="e0d18-199">Erbjudandet är erbjudandet artefakterna som delas med sökande och består av en kombination av en eller flera erbjudandet dokumentmallar.</span><span class="sxs-lookup"><span data-stu-id="e0d18-199">Offer packages are the offer artifacts that are shared with the candidate and consist of a combination of one or more offer document templates.</span></span> <span data-ttu-id="e0d18-200">Gör följande om du vill skapa ett erbjudandepaket.</span><span class="sxs-lookup"><span data-stu-id="e0d18-200">To create an offer package, do the following.</span></span>

1.  <span data-ttu-id="e0d18-201">Gå till **Erbjudandehantering**.</span><span class="sxs-lookup"><span data-stu-id="e0d18-201">Go to **Offer management**.</span></span>

1.  <span data-ttu-id="e0d18-202">Gå till **paket** från det vänstra navigeringsfönstret.</span><span class="sxs-lookup"><span data-stu-id="e0d18-202">Go to **Packages** from the left navigation pane.</span></span>

    <span data-ttu-id="e0d18-203">En lista visas över aktiva paketmallar som är tillgängliga för skapare av erbjudanden som ska användas.</span><span class="sxs-lookup"><span data-stu-id="e0d18-203">A list of active package templates that are available for offer creators to use is displayed.</span></span>

1.  <span data-ttu-id="e0d18-204">För att skapa ett nytt erbjudandepaket klickar du på **Nytt paket**.</span><span class="sxs-lookup"><span data-stu-id="e0d18-204">To create a new offer package, click **New Package**.</span></span>

1.  <span data-ttu-id="e0d18-205">Ange ett unikt namn och klicka på **Skapa**.</span><span class="sxs-lookup"><span data-stu-id="e0d18-205">Enter a unique name and click **Create**.</span></span>

1.  <span data-ttu-id="e0d18-206">Klicka på **Lägg till mall**.</span><span class="sxs-lookup"><span data-stu-id="e0d18-206">Click **Add template**.</span></span>

    >[!NOTE]
    > - <span data-ttu-id="e0d18-207">Du kan välja att skapa en ny mall eller välja från en befintlig.</span><span class="sxs-lookup"><span data-stu-id="e0d18-207">You can choose to create a new template or choose from an existing one.</span></span>

    > - <span data-ttu-id="e0d18-208">Om du vill lägga till en befintlig mall måste du kontrollera att erbjudandedokumentmallen har sparats, slutförts och markerats som aktiv.</span><span class="sxs-lookup"><span data-stu-id="e0d18-208">If you choose to add an existing template, you need to make sure that the   offer document template was saved, finalized, and marked as   active.</span></span>
    
    > - <span data-ttu-id="e0d18-209">Du kan välja så många dokumentmallar som du vill.</span><span class="sxs-lookup"><span data-stu-id="e0d18-209">You can choose as many document templates as you want.</span></span> 
    
1.  <span data-ttu-id="e0d18-210">Klicka på **Klar** för att gå tillbaka till **pakethantering**.</span><span class="sxs-lookup"><span data-stu-id="e0d18-210">Click **Done** to return to **Package management**.</span></span>

    <span data-ttu-id="e0d18-211">Du kan konfigurera dokumentens ordningsföljd och även markera om specifika erbjudandedokument krävs vid skapandet av erbjudandet.</span><span class="sxs-lookup"><span data-stu-id="e0d18-211">You can configure the sequence of the documents and also mark whether the specific offer document is required during offer creation.</span></span> <span data-ttu-id="e0d18-212">Den som skapar erbjudandet har ett alternativ för att ta bort dokument markerade som **Krävs inte**.</span><span class="sxs-lookup"><span data-stu-id="e0d18-212">The offer creator will have an option to delete the documents marked as **Not required**.</span></span>

1. <span data-ttu-id="e0d18-213">För att spara erbjudandepaketmallen så att den kan användas av alla skapare av erbjudanden, klicka på **spara och publicera**.</span><span class="sxs-lookup"><span data-stu-id="e0d18-213">To save the offer package template so that it's usable by all offer creators, click **Save and publish**.</span></span>

   <span data-ttu-id="e0d18-214">För att visa utkast av erbjudandepaketmallar, gå till fliken **utkast**. Om en ändring görs i erbjudandetpaketmallen måste den sparas och publiceras igen.</span><span class="sxs-lookup"><span data-stu-id="e0d18-214">To view draft offer package templates, go to the **Drafts** tab. If a change is made to the offer package template, it must be  saved and republished.</span></span>

## <a name="configure-an-offer-process"></a><span data-ttu-id="e0d18-215">Konfigurera en erbjudandeprocess</span><span class="sxs-lookup"><span data-stu-id="e0d18-215">Configure an offer process</span></span>

<span data-ttu-id="e0d18-216">Det finns flera olika delar av erbjudandets skapandeprocess som kan konfigureras av en Attract-administratör.</span><span class="sxs-lookup"><span data-stu-id="e0d18-216">There are several parts of the offer creation process that can be configured by an Attract administrator.</span></span>

- <span data-ttu-id="e0d18-217">**Erbjudandegodkännanden** - Välj om erbjudandegodkännande krävs innan erbjudandet kan skickas till kandidaten.</span><span class="sxs-lookup"><span data-stu-id="e0d18-217">**Offer approvals** - Choose whether offer approvals are required before the offer can be sent to the candidate.</span></span> <span data-ttu-id="e0d18-218">Som administratör kan du också bestämma om erbjudandegodkännanden sker i ordningsföljd eller parallellt med godkännandearbetsflödet.</span><span class="sxs-lookup"><span data-stu-id="e0d18-218">As an administrator, you can also decide whether all offer approvals will happen in a sequential manner or parallel approval workflow.</span></span> <span data-ttu-id="e0d18-219">Du kan också bestämma om erbjudandets godkännare måste lägga till en kommentar tillsammans med deras erbjudandegodkännande.</span><span class="sxs-lookup"><span data-stu-id="e0d18-219">You can also mandate whether offer approvers must add a comment along with their offer approval.</span></span> <span data-ttu-id="e0d18-220">Erbjudandegodkännanden är obligatoriska för alla erbjudanden som inte är standard.</span><span class="sxs-lookup"><span data-stu-id="e0d18-220">Offer approvals are mandatory for all non-standard offers.</span></span>

- <span data-ttu-id="e0d18-221">**Kandidatens erfarenhet av erbjudandet** - som administratör kan du ange om alla erbjudanden har ett förfallodatum och i så fall vad standardförskjutningen för förfallodatum ska vara.</span><span class="sxs-lookup"><span data-stu-id="e0d18-221">**Candidate’s offer experience** - As administrator, you can choose to set whether all offers have an expiration date, and if so, what the default offset for the expiration date should be.</span></span> <span data-ttu-id="e0d18-222">Du kan också ange om kandidater kan avvisa ett erbjudande.</span><span class="sxs-lookup"><span data-stu-id="e0d18-222">You can also configure whether candidates can decline an offer.</span></span>

- <span data-ttu-id="e0d18-223">**e-signaturer** - Som administratör kan du också välja metoden kandidater kan använda för att skriva under erbjudanden.</span><span class="sxs-lookup"><span data-stu-id="e0d18-223">**e-Signatures** - As an administrator, you can also choose the method that candidates can use to sign offers.</span></span>
    - <span data-ttu-id="e0d18-224">Adobe Sign - Alla erbjudandepaket skickas och signerats via Adobe Sign.</span><span class="sxs-lookup"><span data-stu-id="e0d18-224">Adobe Sign - All offer packages will be sent and signed via Adobe Sign.</span></span> <span data-ttu-id="e0d18-225">Varje erbjudandeskapare publicerar erbjudandet måste ha Adobe Sign-licensen ansluten till Attract.</span><span class="sxs-lookup"><span data-stu-id="e0d18-225">Each offer creator publishing the offer needs to have their Adobe Sign license connected to Attract.</span></span> 

    - <span data-ttu-id="e0d18-226">ESign - Detta är standardalternativet, tillhandahålles direkt vid leverans, där användaren kan registrera ett erbjudande genom att ange deras namn och initialer.</span><span class="sxs-lookup"><span data-stu-id="e0d18-226">ESign - This is the default option, provided out of the box, where the user can sign an offer by typing their name and initials.</span></span>

<span data-ttu-id="e0d18-227">Mer information om processen att skapa erbjudanden finns i [skapa, godkänna och signera erbjudanden](./creating-offers.md).</span><span class="sxs-lookup"><span data-stu-id="e0d18-227">To learn more about the offer creation process, see [Creating, approving, and signing offers](./creating-offers.md).</span></span>

