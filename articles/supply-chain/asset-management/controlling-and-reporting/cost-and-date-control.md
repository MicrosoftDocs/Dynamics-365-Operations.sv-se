---
title: Kostnads- och datumkontroll
description: I det här avsnittet förklaras kostnads- och datumkontrollen i Tillgångshantering.
author: josaw1
manager: AnnBe
ms.date: 08/23/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 2bcd1584f6a858f7589387fbfe96267b7c16176a
ms.sourcegitcommit: 2292b54e2da96f71b59ec9ccf17cd32d3d1d8b21
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/23/2019
ms.locfileid: "1918405"
---
# <a name="cost-and-date-control"></a><span data-ttu-id="574f6-103">Kostnads- och datumkontroll</span><span class="sxs-lookup"><span data-stu-id="574f6-103">Cost and date control</span></span>

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

<span data-ttu-id="574f6-104">I Tillgångshantering kan du beräkna kostnader för att få en översikt över de faktiska kostnaderna jämfört med budgetkostnader för tillgångar, funktionsplatser och arbetsorder.</span><span class="sxs-lookup"><span data-stu-id="574f6-104">In Asset Management, you can calculate costs to get an overview of actual costs compared to budget costs on assets, functional locations, and work orders.</span></span> <span data-ttu-id="574f6-105">Faktiska kostnader baseras på bokförda transaktioner.</span><span class="sxs-lookup"><span data-stu-id="574f6-105">Actual costs are based on posted transactions.</span></span> <span data-ttu-id="574f6-106">Du kan också göra en datumberäkning om du vill jämföra planerade start- och slutdatum med faktiska start- och slutdatum på arbetsorder.</span><span class="sxs-lookup"><span data-stu-id="574f6-106">You can also make a date calculation if you want to compare scheduled start and end dates to actual start and end dates on work orders.</span></span>

## <a name="cost-control-for-assets-functional-locations-and-work-orders"></a><span data-ttu-id="574f6-107">Kostnadskontroll för tillgångar, funktionsplatser och arbetsorder</span><span class="sxs-lookup"><span data-stu-id="574f6-107">Cost control for assets, functional locations, and work orders</span></span>

<span data-ttu-id="574f6-108">De beräkningar som görs för tillgångar, funktionsplatser och arbetsorder är nästan identiska.</span><span class="sxs-lookup"><span data-stu-id="574f6-108">The calculations made for assets, functional locations, and work orders are almost identical.</span></span> <span data-ttu-id="574f6-109">Enda skillnad är att för tillgångar och funktionsplatser kan du även inkludera underresurser och underplatser i beräkningen.</span><span class="sxs-lookup"><span data-stu-id="574f6-109">Only difference is that for assets and functional locations, you can also include sub assets and sub locations in your calculation.</span></span> <span data-ttu-id="574f6-110">Datumet är transaktionsdatumet när registreringen gjordes.</span><span class="sxs-lookup"><span data-stu-id="574f6-110">The date is the transaction date when the registration was recorded.</span></span>

1. <span data-ttu-id="574f6-111">Klicka på **Tillgångshantering** > **Förfrågningar** > **Tillgångar** > **Kostnadskontroll för tillgång** eller **Kostnadskontroll för funktionsplats**, eller **Tillgångshantering** > **Förfrågningar** > **Arbetsorder** > **Kostnadskontroll för arbetsorder**.</span><span class="sxs-lookup"><span data-stu-id="574f6-111">Click **Asset management** > **Inquiries** > **Assets** > **Asset cost control** or **Functional location cost control**, or **Asset management** > **Inquiries** > **Work orders** > **Work order cost control**.</span></span>

2. <span data-ttu-id="574f6-112">I dialogrutan **Kostnadskontroll för tillgång** / **Kostnadskontroll för funktionsplats** / **Kostnadskontroll för arbetsorder** väljer du en period som ska beräknas.</span><span class="sxs-lookup"><span data-stu-id="574f6-112">In the **Asset cost control** / **Functional location cost control** / **Work order cost control** dialog, select a period to be calculated.</span></span>

3. <span data-ttu-id="574f6-113">Välj vid behov en ekonomisk dimensionsuppsättning som ska inkluderas i beräkningen.</span><span class="sxs-lookup"><span data-stu-id="574f6-113">If required, select a financial dimension set to be included in the calculation.</span></span>

4. <span data-ttu-id="574f6-114">Välj "Ja" på växlingsknappen **Hoppa över noll** om du inte vill visa resultat som innehåller kostnaden noll.</span><span class="sxs-lookup"><span data-stu-id="574f6-114">Select "Yes" on the **Skip zero** toggle button if you don't want to show results with a cost of zero.</span></span>

5. <span data-ttu-id="574f6-115">Du kan använda fältet **Nivå** för att indikera hur detaljerad kostnadskontrollraderna ska vara gällande funktionsplatser.</span><span class="sxs-lookup"><span data-stu-id="574f6-115">You can use the **Level** field to indicate how detailed you want the cost control lines to be regarding functional locations.</span></span> <span data-ttu-id="574f6-116">Om du till exempel infogar siffran "1" i fältet och har en funktionsplatshierarki med flera nivåer, visas alla kostnadskontrollrader för en funktionsplats på den översta nivån, och därmed kan också de timmar som finns på en rad läggas till från funktionsplatser på en lägre nivå.</span><span class="sxs-lookup"><span data-stu-id="574f6-116">For example, if you insert the number "1" in the field, and you have a multi-level functional location hierarchy, all cost control lines for a functional location will be shown on the top level, and therefore the hours on a line may be added up from functional locations located at a lower level.</span></span> <span data-ttu-id="574f6-117">Om du infogar siffran "0" i fältet **Nivå** visas ett detaljerat resultat med alla kostnadskontrollrader på alla den funktionsplatsnivå som de är relaterade till.</span><span class="sxs-lookup"><span data-stu-id="574f6-117">If you insert the number "0" in the **Level** field, you will see a detailed result showing all cost control lines on all the functional location level to which they are related.</span></span>

6. <span data-ttu-id="574f6-118">Välj "Ja" på växlingsknappen **Visa öppen utfäst kostnad** om du vill inkludera den kolumnen i beräkningen.</span><span class="sxs-lookup"><span data-stu-id="574f6-118">Select "Yes" on the **Show open committed cost** toggle button if you want to include that column in the calculation.</span></span>

7. <span data-ttu-id="574f6-119">Välj "Ja" på växlingsknappen **Inkludera undertillgångar** om du vill visa kostnader som är relaterade till undertillgångar som separata rader.</span><span class="sxs-lookup"><span data-stu-id="574f6-119">Select "Yes" on the **Include sub assets** toggle button to show costs related to sub assets as separate lines.</span></span>

8. <span data-ttu-id="574f6-120">Om du vill begränsa sökningen kan du välja specifika tillgångar/funktionsplatser/arbetsorder på snabbfliken **Poster som ska ingå**.</span><span class="sxs-lookup"><span data-stu-id="574f6-120">If you want to limit the search, you can select specific assets / functional locations / work orders on the **Records to include** FastTab.</span></span>

9. <span data-ttu-id="574f6-121">Klicka på **OK** för att starta beräkningen.</span><span class="sxs-lookup"><span data-stu-id="574f6-121">Click **OK** to start the calculation.</span></span>

<span data-ttu-id="574f6-122">I bilden nedan visas ett exempel på dialogrutan **Kostnadskontroll för tillgång**.</span><span class="sxs-lookup"><span data-stu-id="574f6-122">The figure below shows an example of the **Asset cost control** dialog.</span></span>

![Figur 1](media/01-controlling-and-reporting.png)

10. <span data-ttu-id="574f6-124">I åtgärdsfönstergrupperna **Gruppera efter...** på sidan **Kostnadskontroll för tillgång** klickar du på relevanta knappar om du vill visa den obligatoriska detaljnivån för beräkningen.</span><span class="sxs-lookup"><span data-stu-id="574f6-124">In the **Group by...** action pane groups on the **Asset cost control** page, click the relevant buttons to show the required detail level of the calculation.</span></span> <span data-ttu-id="574f6-125">De valda knapparna i åtgärdsfönstret markeras.</span><span class="sxs-lookup"><span data-stu-id="574f6-125">The selected action pane buttons are highlighted.</span></span> <span data-ttu-id="574f6-126">Klicka på en knapp för att aktivera och inaktivera den.</span><span class="sxs-lookup"><span data-stu-id="574f6-126">Click on a button to activate or deactivate it.</span></span>

<span data-ttu-id="574f6-127">I bilden nedan visas ett exempel på beräkningsresultat i **Kostnadskontroll för tillgång**.</span><span class="sxs-lookup"><span data-stu-id="574f6-127">The figure below shows an example of calculation results in **Asset cost control**.</span></span>

![Figur 2](media/02-controlling-and-reporting.png)

<span data-ttu-id="574f6-129">Ett annat sätt att göra en kostnadsberäkning är att använda flera tillgångar i **Alla tillgångar** eller **Aktiva tillgångar**.</span><span class="sxs-lookup"><span data-stu-id="574f6-129">Another way of making a cost calculation is to multi-select assets in **All assets** or **Active assets**.</span></span> <span data-ttu-id="574f6-130">Klicka sedan på knappen **Kostnadskontroll** på fliken **Allmänt**. I dialogrutan **Kostnadskontroll för tillgång** infogas de valda tillgångarna automatiskt i fältet **Tillgång** på snabbfliken **Poster som ska ingå**.</span><span class="sxs-lookup"><span data-stu-id="574f6-130">Then, you click the **Cost control** button on the **General** tab. In the **Asset cost control** dialog, the selected assets are automatically inserted in the **Asset** field on the **Records to include** FastTab.</span></span> <span data-ttu-id="574f6-131">Klicka på **OK** och en kostnadsberäkning för valda tillgångar visas.</span><span class="sxs-lookup"><span data-stu-id="574f6-131">Click **OK**, and a cost calculation for the selected assets is shown.</span></span> <span data-ttu-id="574f6-132">Samma procedur kan utföras för funktionsplatser i **Alla funktionsplatser** eller **Aktiva funktionsplatser**, och för arbetsorder i **Alla arbetsorder** eller **Aktiva arbetsorder**.</span><span class="sxs-lookup"><span data-stu-id="574f6-132">The same procedure can be done for functional locations in **All functional locations** or **Active functional locations**, and for work orders in **All work orders** or **Active work orders**.</span></span>

>[!NOTE]
><span data-ttu-id="574f6-133">I fältet **Ursprunglig budget** visas budgetkostnader från arbetsorderprognosen.</span><span class="sxs-lookup"><span data-stu-id="574f6-133">The **Original budget** field shows budget costs from the work order forecast.</span></span> <span data-ttu-id="574f6-134">Fältet **Utfästa kostnader** visar det totala beloppet för utgifter som en juridisk person har lovat att betala.</span><span class="sxs-lookup"><span data-stu-id="574f6-134">The **Committed cost** field shows the total amount of expenses that a legal entity has committed itself to pay.</span></span> <span data-ttu-id="574f6-135">I fältet **Öppen utfäst kostnad** visas utfästelser som ska betalas för artiklar, timmar och tjänster som du har beställt eller tagit emot men ännu inte betalt för.</span><span class="sxs-lookup"><span data-stu-id="574f6-135">The **Open committed cost** field shows commitments to pay for items, hours, and services you have ordered or received but not yet paid for.</span></span> <span data-ttu-id="574f6-136">När alla förbrukningsregistreringar har bokförts inkluderas de relaterade kostnaderna i fältet **Faktisk kostnad**.</span><span class="sxs-lookup"><span data-stu-id="574f6-136">When all consumption registrations have been posted, the related costs are included in the **Actual cost** field.</span></span>

## <a name="work-order-date-control"></a><span data-ttu-id="574f6-137">Datumkontroll för arbetsorder</span><span class="sxs-lookup"><span data-stu-id="574f6-137">Work order date control</span></span>

<span data-ttu-id="574f6-138">Använd den här sidan om du vill få en översikt över förväntade start- och slutdatum i förhållande till faktiska start- och slutdatum på arbetsorder.</span><span class="sxs-lookup"><span data-stu-id="574f6-138">Use this page to get an overview of expected start and end dates compared to actual start and end dates on work orders.</span></span>

1. <span data-ttu-id="574f6-139">Klicka på **Tillgångshantering** > **Förfrågningar** > **Arbetsorder** > **Datumkontroll för arbetsorder**.</span><span class="sxs-lookup"><span data-stu-id="574f6-139">Click **Asset management** > **Inquiries** > **Work orders** > **Work order date control**.</span></span>

2. <span data-ttu-id="574f6-140">Klicka på **Beräkna**.</span><span class="sxs-lookup"><span data-stu-id="574f6-140">Click **Calculate**.</span></span>

3. <span data-ttu-id="574f6-141">Välj en funktionsplats i fältet **Funktionsplats**.</span><span class="sxs-lookup"><span data-stu-id="574f6-141">Select a functional location in the **Functional location** field.</span></span>

4. <span data-ttu-id="574f6-142">Infoga den period för vilken du vill utföra beräkningen i fälten **Från datum** och **Till datum**.</span><span class="sxs-lookup"><span data-stu-id="574f6-142">Insert the period for which you want to make the calculation in the **From date** and **To date** fields.</span></span> <span data-ttu-id="574f6-143">Alla arbetsorder med förväntad start inom perioden inkluderas.</span><span class="sxs-lookup"><span data-stu-id="574f6-143">All work orders with expected start within the period will be included.</span></span>

5. <span data-ttu-id="574f6-144">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="574f6-144">Click **OK**.</span></span>

6. <span data-ttu-id="574f6-145">I **Gruppera efter...**-åtgärdsfönstergrupper klickar du på de relevanta knapparna för att visa den obligatoriska detaljnivån för beräkningen.</span><span class="sxs-lookup"><span data-stu-id="574f6-145">In the **Group by...** action pane groups, click the relevant buttons to show the required detail level of the calculation.</span></span> <span data-ttu-id="574f6-146">De valda knapparna i åtgärdsfönstret markeras.</span><span class="sxs-lookup"><span data-stu-id="574f6-146">The selected action pane buttons are highlighted.</span></span> <span data-ttu-id="574f6-147">Klicka på en knapp för att aktivera och inaktivera den.</span><span class="sxs-lookup"><span data-stu-id="574f6-147">Click on a button to activate or deactivate it.</span></span>

<span data-ttu-id="574f6-148">I bilden nedan visas ett exempel på beräkningsresultat i **Datumkontroll för arbetsorder**.</span><span class="sxs-lookup"><span data-stu-id="574f6-148">The figure below shows an example of calculation results in **Work order date control**.</span></span>

![Figur 3](media/03-controlling-and-reporting.png)

- <span data-ttu-id="574f6-150">Fältet **Genomsnittlig startfördröjning** visar skillnaden i dagar mellan det schemalagda startdatumet för en arbetsorder jämfört med faktiskt startdatum.</span><span class="sxs-lookup"><span data-stu-id="574f6-150">The **Avg. start delay** field shows the difference in days between scheduled start date for a work order compared to actual start date.</span></span> <span data-ttu-id="574f6-151">Om till exempel det verkliga startdatumet infaller två dagar före det schemalagda startdatumet visas "-2" i det här fältet.</span><span class="sxs-lookup"><span data-stu-id="574f6-151">If, for example, the actual start date was two days before the scheduled start date, "-2" will be displayed in this field.</span></span>  
- <span data-ttu-id="574f6-152">Fältet **Genomsnittlig slutfördröjning** visar skillnaden i dagar mellan det schemalagda slutdatumet för en arbetsorder jämfört med faktiskt slutdatum.</span><span class="sxs-lookup"><span data-stu-id="574f6-152">The **Avg. end delay** field shows the difference in days between scheduled end date for a work order compared to actual end date.</span></span> <span data-ttu-id="574f6-153">Om till exempel det faktiska slutdatumet infaller tre dagar efter det schemalagda slutdatumet visas "3" i det här fältet.</span><span class="sxs-lookup"><span data-stu-id="574f6-153">If, for example, the actual end date was three days after the scheduled end date, "3" will be displayed in this field.</span></span>  
- <span data-ttu-id="574f6-154">I fälten **Förekomster** visas antalet gånger avvikelser uppträder i relation till schemalagt och faktiskt startdatum, samt schemalagt och faktiskt slutdatum på arbetsordern.</span><span class="sxs-lookup"><span data-stu-id="574f6-154">The **Occurrences** fields show the number of times deviations occur in relation to scheduled and actual start date, and scheduled and actual end date on the work order.</span></span>

