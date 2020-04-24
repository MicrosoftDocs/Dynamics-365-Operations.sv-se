---
title: Kostnads- och datumkontroll
description: I det här avsnittet förklaras kostnads- och datumkontrollen i Tillgångshantering.
author: josaw1
manager: tfehr
ms.date: 08/23/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: dc3b4d22f5ce9a7e14b3834c299fa5a86d8d2868
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/02/2020
ms.locfileid: "3205516"
---
# <a name="cost-and-date-control"></a><span data-ttu-id="05c42-103">Kostnads- och datumkontroll</span><span class="sxs-lookup"><span data-stu-id="05c42-103">Cost and date control</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="05c42-104">I Tillgångshantering kan du beräkna kostnader för att få en översikt över de faktiska kostnaderna jämfört med budgetkostnader för tillgångar, funktionsplatser och arbetsorder.</span><span class="sxs-lookup"><span data-stu-id="05c42-104">In Asset Management, you can calculate costs to get an overview of actual costs compared to budget costs on assets, functional locations, and work orders.</span></span> <span data-ttu-id="05c42-105">Faktiska kostnader baseras på bokförda transaktioner.</span><span class="sxs-lookup"><span data-stu-id="05c42-105">Actual costs are based on posted transactions.</span></span> 

<span data-ttu-id="05c42-106">Du kan också göra en datumberäkning om du vill jämföra planerade start- och slutdatum med faktiska start- och slutdatum på arbetsorder.</span><span class="sxs-lookup"><span data-stu-id="05c42-106">You can also make a date calculation if you want to compare scheduled start and end dates to actual start and end dates on work orders.</span></span>

## <a name="cost-control-for-assets-functional-locations-and-work-orders"></a><span data-ttu-id="05c42-107">Kostnadskontroll för tillgångar, funktionsplatser och arbetsorder</span><span class="sxs-lookup"><span data-stu-id="05c42-107">Cost control for assets, functional locations, and work orders</span></span>

<span data-ttu-id="05c42-108">De beräkningar som görs för tillgångar, funktionsplatser och arbetsorder är nästan identiska.</span><span class="sxs-lookup"><span data-stu-id="05c42-108">The calculations made for assets, functional locations, and work orders are almost identical.</span></span> <span data-ttu-id="05c42-109">Den enda skillnaden är att för tillgångar och funktionsplatser kan du även inkludera underresurser och underplatser i beräkningen.</span><span class="sxs-lookup"><span data-stu-id="05c42-109">The only difference is that for assets and functional locations, you can also include sub assets and sub locations in your calculation.</span></span> <span data-ttu-id="05c42-110">Datumet är transaktionsdatumet när registreringen gjordes.</span><span class="sxs-lookup"><span data-stu-id="05c42-110">The date is the transaction date when the registration was recorded.</span></span>

1. <span data-ttu-id="05c42-111">Klicka på **Tillgångshantering** > **Förfrågningar** > **Tillgångar** > **Kostnadskontroll för tillgång** eller **Kostnadskontroll för funktionsplats**, eller **Tillgångshantering** > **Förfrågningar** > **Arbetsorder** > **Kostnadskontroll för arbetsorder**.</span><span class="sxs-lookup"><span data-stu-id="05c42-111">Click **Asset management** > **Inquiries** > **Assets** > **Asset cost control** or **Functional location cost control**, or **Asset management** > **Inquiries** > **Work orders** > **Work order cost control**.</span></span>

2. <span data-ttu-id="05c42-112">I dialogrutan **Kostnadskontroll för tillgång** / **Kostnadskontroll för funktionsplats** / **Kostnadskontroll för arbetsorder** väljer du ett tidsintervall som ska beräknas.</span><span class="sxs-lookup"><span data-stu-id="05c42-112">In the **Asset cost control** / **Functional location cost control** / **Work order cost control** dialog, select a time range to be calculated.</span></span>

3. <span data-ttu-id="05c42-113">Välj vid behov en ekonomisk dimensionsuppsättning som ska inkluderas i beräkningen.</span><span class="sxs-lookup"><span data-stu-id="05c42-113">If required, select a financial dimension set to be included in the calculation.</span></span>

4. <span data-ttu-id="05c42-114">Välj "Ja" på växlingsknappen **Hoppa över noll** om du inte vill visa resultat som innehåller kostnaden noll.</span><span class="sxs-lookup"><span data-stu-id="05c42-114">Select "Yes" on the **Skip zero** toggle button if you don't want to show results with a cost of zero.</span></span>

5. <span data-ttu-id="05c42-115">Du kan använda fältet **Nivå** för att indikera hur detaljerad kostnadskontrollraderna ska vara gällande funktionsplatser.</span><span class="sxs-lookup"><span data-stu-id="05c42-115">You can use the **Level** field to indicate how detailed you want the cost control lines to be regarding functional locations.</span></span> 

    <span data-ttu-id="05c42-116">Om du till exempel infogar siffran "1" i fältet och har en funktionsplatshierarki med flera nivåer, visas alla kostnadskontrollrader för en funktionsplats på den översta nivån, och därmed kan också de timmar som finns på en rad läggas till från funktionsplatser på en lägre nivå.</span><span class="sxs-lookup"><span data-stu-id="05c42-116">For example, if you insert the number "1" in the field, and you have a multi-level functional location hierarchy, all cost control lines for a functional location will be shown on the top level, and therefore the hours on a line may be added up from functional locations located at a lower level.</span></span> 
    
    <span data-ttu-id="05c42-117">Om du infogar siffran "0" i fältet **Nivå** visas ett detaljerat resultat med alla kostnadskontrollrader på alla den funktionsplatsnivå som de är relaterade till.</span><span class="sxs-lookup"><span data-stu-id="05c42-117">If you insert the number "0" in the **Level** field, you will see a detailed result showing all cost control lines on all the functional location level to which they are related.</span></span>

6. <span data-ttu-id="05c42-118">Välj "Ja" på växlingsknappen **Visa öppen utfäst kostnad** om du vill inkludera den kolumnen i beräkningen.</span><span class="sxs-lookup"><span data-stu-id="05c42-118">Select "Yes" on the **Show open committed cost** toggle button if you want to include that column in the calculation.</span></span>

7. <span data-ttu-id="05c42-119">Välj "Ja" på växlingsknappen **Inkludera undertillgångar** om du vill visa kostnader som är relaterade till undertillgångar som separata rader.</span><span class="sxs-lookup"><span data-stu-id="05c42-119">Select "Yes" on the **Include sub assets** toggle button to show costs related to sub assets as separate lines.</span></span>

8. <span data-ttu-id="05c42-120">Om du vill begränsa sökningen kan du välja specifika tillgångar/funktionsplatser/arbetsorder på snabbfliken **Poster som ska ingå**.</span><span class="sxs-lookup"><span data-stu-id="05c42-120">If you want to limit the search, you can select specific assets / functional locations / work orders on the **Records to include** FastTab.</span></span>

9. <span data-ttu-id="05c42-121">Klicka på **OK** för att starta beräkningen.</span><span class="sxs-lookup"><span data-stu-id="05c42-121">Click **OK** to start the calculation.</span></span>

    <span data-ttu-id="05c42-122">I bilden nedan visas ett exempel på dialogrutan **Kostnadskontroll för tillgång**.</span><span class="sxs-lookup"><span data-stu-id="05c42-122">The figure below shows an example of the **Asset cost control** dialog.</span></span>

    ![Dialogrutan kostnadskontroll för tillgång](media/01-controlling-and-reporting.png)

10. <span data-ttu-id="05c42-124">På sidan **Kostnadskontroll för tillgång**, välj knapparna **Gruppera efter** för att visa den obligatoriska detaljnivån för beräkningen.</span><span class="sxs-lookup"><span data-stu-id="05c42-124">On the **Asset cost control** page, click the **Group by** buttons to show the required detail level of the calculation.</span></span> <span data-ttu-id="05c42-125">De valda knapparna **Gruppera efter** markeras.</span><span class="sxs-lookup"><span data-stu-id="05c42-125">The selected **Group by** buttons are highlighted.</span></span> <span data-ttu-id="05c42-126">Klicka på en knapp för att aktivera och inaktivera den.</span><span class="sxs-lookup"><span data-stu-id="05c42-126">Click on a button to activate or deactivate it.</span></span>

## <a name="example"></a><span data-ttu-id="05c42-127">Exempel</span><span class="sxs-lookup"><span data-stu-id="05c42-127">Example</span></span>

<span data-ttu-id="05c42-128">I skärmbilden nedan visas ett exempel på beräkningsresultat i **Kostnadskontroll för tillgång**.</span><span class="sxs-lookup"><span data-stu-id="05c42-128">The screenshot below shows an example of calculation results in **Asset cost control**.</span></span>

- <span data-ttu-id="05c42-129">I fältet **Ursprunglig budget** visas budgetkostnader från arbetsorderprognosen.</span><span class="sxs-lookup"><span data-stu-id="05c42-129">The **Original budget** field shows budget costs from the work order forecast.</span></span> 
- <span data-ttu-id="05c42-130">Fältet **Utfästa kostnader** visar det totala beloppet för utgifter som en juridisk person har lovat att betala.</span><span class="sxs-lookup"><span data-stu-id="05c42-130">The **Committed cost** field shows the total amount of expenses that a legal entity has committed itself to pay.</span></span> 
- <span data-ttu-id="05c42-131">I fältet **Öppen utfäst kostnad** visas utfästelser som ska betalas för artiklar, timmar och tjänster som du har beställt eller tagit emot men ännu inte betalt för.</span><span class="sxs-lookup"><span data-stu-id="05c42-131">The **Open committed cost** field shows commitments to pay for items, hours, and services you have ordered or received but not yet paid for.</span></span> 
- <span data-ttu-id="05c42-132">**Faktisk kostnad** fältet visar relaterade kostnader efter att alla förbrukningsregistreringar har bokförts.</span><span class="sxs-lookup"><span data-stu-id="05c42-132">The **Actual cost** field shows related costs after all consumption registrations have been posted.</span></span>

![Exempel på beräkningsresultat i Kostnadskontroll för tillgång](media/02-controlling-and-reporting.png)

<span data-ttu-id="05c42-134">Ett annat sätt att göra en kostnadsberäkning är att använda flera tillgångar i **Alla tillgångar** eller **Aktiva tillgångar**.</span><span class="sxs-lookup"><span data-stu-id="05c42-134">Another way of making a cost calculation is to multi-select assets in **All assets** or **Active assets**.</span></span> <span data-ttu-id="05c42-135">Klicka sedan på knappen **Kostnadskontroll** på fliken **Allmänt**. I dialogrutan **Kostnadskontroll för tillgång** infogas de valda tillgångarna automatiskt i fältet **Tillgång** på snabbfliken **Poster som ska ingå**.</span><span class="sxs-lookup"><span data-stu-id="05c42-135">Then, you click the **Cost control** button on the **General** tab. In the **Asset cost control** dialog, the selected assets are automatically inserted in the **Asset** field on the **Records to include** FastTab.</span></span> <span data-ttu-id="05c42-136">Klicka på **OK** och en kostnadsberäkning för valda tillgångar visas.</span><span class="sxs-lookup"><span data-stu-id="05c42-136">Click **OK**, and a cost calculation for the selected assets is shown.</span></span> <span data-ttu-id="05c42-137">Samma procedur kan utföras för funktionsplatser i **Alla funktionsplatser** eller **Aktiva funktionsplatser**, och för arbetsorder i **Alla arbetsorder** eller **Aktiva arbetsorder**.</span><span class="sxs-lookup"><span data-stu-id="05c42-137">The same procedure can be done for functional locations in **All functional locations** or **Active functional locations**, and for work orders in **All work orders** or **Active work orders**.</span></span>


## <a name="work-order-date-control"></a><span data-ttu-id="05c42-138">Datumkontroll för arbetsorder</span><span class="sxs-lookup"><span data-stu-id="05c42-138">Work order date control</span></span>

<span data-ttu-id="05c42-139">Använd den här sidan om du vill få en översikt över förväntade start- och slutdatum i förhållande till faktiska start- och slutdatum på arbetsorder.</span><span class="sxs-lookup"><span data-stu-id="05c42-139">Use this page to get an overview of expected start and end dates compared to actual start and end dates on work orders.</span></span>

1. <span data-ttu-id="05c42-140">Klicka på **Tillgångshantering** > **Förfrågningar** > **Arbetsorder** > **Datumkontroll för arbetsorder**.</span><span class="sxs-lookup"><span data-stu-id="05c42-140">Click **Asset management** > **Inquiries** > **Work orders** > **Work order date control**.</span></span>

2. <span data-ttu-id="05c42-141">Klicka på **Beräkna**.</span><span class="sxs-lookup"><span data-stu-id="05c42-141">Click **Calculate**.</span></span>

3. <span data-ttu-id="05c42-142">Välj en funktionsplats i fältet **Funktionsplats**.</span><span class="sxs-lookup"><span data-stu-id="05c42-142">Select a functional location in the **Functional location** field.</span></span>

4. <span data-ttu-id="05c42-143">Infoga den intervall för vilken du vill utföra beräkningen i fälten **Från datum** och **Till datum**.</span><span class="sxs-lookup"><span data-stu-id="05c42-143">Insert the range for which you want to make the calculation in the **From date** and **To date** fields.</span></span> <span data-ttu-id="05c42-144">Alla arbetsorder med förväntad startdatum inom intervallet inkluderas.</span><span class="sxs-lookup"><span data-stu-id="05c42-144">All work orders with expected start date within the range will be included.</span></span>

5. <span data-ttu-id="05c42-145">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="05c42-145">Click **OK**.</span></span>

6. <span data-ttu-id="05c42-146">Klicka på knapparna **Gruppera efter...** för att visa den obligatoriska detaljnivån för beräkningen.</span><span class="sxs-lookup"><span data-stu-id="05c42-146">Click the **Group by** buttons to show the required detail level of the calculation.</span></span> <span data-ttu-id="05c42-147">De valda knapparna **Gruppera efter** markeras.</span><span class="sxs-lookup"><span data-stu-id="05c42-147">The selected **Group by** buttons are highlighted.</span></span> <span data-ttu-id="05c42-148">Klicka på en knapp för att aktivera och inaktivera den.</span><span class="sxs-lookup"><span data-stu-id="05c42-148">Click on a button to activate or deactivate it.</span></span>

## <a name="example"></a><span data-ttu-id="05c42-149">Exempel</span><span class="sxs-lookup"><span data-stu-id="05c42-149">Example</span></span>

<span data-ttu-id="05c42-150">I bildskärmen nedan visas ett exempel på beräkningsresultat i **Datumkontroll för arbetsorder**.</span><span class="sxs-lookup"><span data-stu-id="05c42-150">The screenshot below shows an example of calculation results in **Work order date control**.</span></span>

- <span data-ttu-id="05c42-151">Fältet **Genomsnittlig startfördröjning** visar skillnaden i dagar mellan det schemalagda startdatumet för en arbetsorder jämfört med faktiskt startdatum.</span><span class="sxs-lookup"><span data-stu-id="05c42-151">The **Avg. start delay** field shows the difference in days between scheduled start date for a work order compared to actual start date.</span></span> <span data-ttu-id="05c42-152">Om till exempel det verkliga startdatumet infaller två dagar före det schemalagda startdatumet visas "-2" i det här fältet.</span><span class="sxs-lookup"><span data-stu-id="05c42-152">If, for example, the actual start date was two days before the scheduled start date, "-2" will be displayed in this field.</span></span>  
- <span data-ttu-id="05c42-153">Fältet **Genomsnittlig slutfördröjning** visar skillnaden i dagar mellan det schemalagda slutdatumet för en arbetsorder jämfört med faktiskt slutdatum.</span><span class="sxs-lookup"><span data-stu-id="05c42-153">The **Avg. end delay** field shows the difference in days between scheduled end date for a work order compared to actual end date.</span></span> <span data-ttu-id="05c42-154">Om till exempel det faktiska slutdatumet infaller tre dagar efter det schemalagda slutdatumet visas "3" i det här fältet.</span><span class="sxs-lookup"><span data-stu-id="05c42-154">If, for example, the actual end date was three days after the scheduled end date, "3" will be displayed in this field.</span></span>  
- <span data-ttu-id="05c42-155">I fälten **Förekomster** visas antalet gånger avvikelser uppträder i relation till schemalagt och faktiskt startdatum, samt schemalagt och faktiskt slutdatum på arbetsordern.</span><span class="sxs-lookup"><span data-stu-id="05c42-155">The **Occurrences** fields show the number of times deviations occur in relation to scheduled and actual start date, and scheduled and actual end date on the work order.</span></span>

![Exempel på beräkningsresultat i Datumkontroll för arbetsorder](media/03-controlling-and-reporting.png)


