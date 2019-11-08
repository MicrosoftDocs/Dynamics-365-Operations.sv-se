---
title: Arbetstidskontroll
description: I det här avsnittet förklaras arbetstidskontroll i Tillgångshantering.
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
ms.openlocfilehash: 1a59b4bbf1a4612cea1ba3bd536ba4b018fc621f
ms.sourcegitcommit: fb66731f05207094149a6bc7b8549a4dabbb071a
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/22/2019
ms.locfileid: "2652343"
---
# <a name="work-hour-control"></a><span data-ttu-id="8a70e-103">Arbetstidskontroll</span><span class="sxs-lookup"><span data-stu-id="8a70e-103">Work hour control</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="8a70e-104">I Tillgångshantering kan du beräkna timmar för att få en översikt över de faktiska timmarna jämfört med budgeterade timmar för tillgångar, funktionsplatser och arbetsorder.</span><span class="sxs-lookup"><span data-stu-id="8a70e-104">In Asset Management, you can calculate hours to get an overview of actual hours compared to budget hours on assets, functional locations, or work orders.</span></span> <span data-ttu-id="8a70e-105">Faktiska timmar baseras på bokförda transaktioner.</span><span class="sxs-lookup"><span data-stu-id="8a70e-105">Actual hours are based on posted transactions.</span></span>

## <a name="work-hour-control-for-assets-functional-locations-and-work-orders"></a><span data-ttu-id="8a70e-106">Arbetstidskontroll för tillgångar, funktionsplatser och arbetsorder</span><span class="sxs-lookup"><span data-stu-id="8a70e-106">Work hour control for assets, functional locations, and work orders</span></span>

<span data-ttu-id="8a70e-107">De beräkningar som görs för tillgångar, funktionsplatser och arbetsorder är nästan identiska.</span><span class="sxs-lookup"><span data-stu-id="8a70e-107">The calculations made for assets, functional locations, and work orders are almost identical.</span></span> <span data-ttu-id="8a70e-108">Enda skillnad är att för tillgångar och funktionsplatser kan du även inkludera underresurser och underplatser i beräkningen.</span><span class="sxs-lookup"><span data-stu-id="8a70e-108">Only difference is that for assets and functional locations, you can also include sub assets and sub locations in your calculation.</span></span> <span data-ttu-id="8a70e-109">Datumet är transaktionsdatumet när registreringen gjordes.</span><span class="sxs-lookup"><span data-stu-id="8a70e-109">The date is the transaction date when the registration was recorded.</span></span>

1. <span data-ttu-id="8a70e-110">Klicka på **Tillgångshantering** > **Förfrågningar** > **Tillgångar** > **Timkontroll för tillgång** eller **Timkontroll för funktionsplats**, eller **Tillgångshantering** > **Förfrågningar** > **Arbetsorder** > **Timkontroll för arbetsorder**.</span><span class="sxs-lookup"><span data-stu-id="8a70e-110">Click **Asset management** > **Inquiries** > **Assets** > **Asset hour control** or **Functional location hour control**, or **Asset management** > **Inquiries** > **Work orders** > **Work order hour control**.</span></span>

2. <span data-ttu-id="8a70e-111">I dialogrutan **Timkontroll för tillgång**.</span><span class="sxs-lookup"><span data-stu-id="8a70e-111">In the **Asset hour control** dialog, .</span></span>

3. <span data-ttu-id="8a70e-112">I dialogrutan **Timkontroll för tillgång** / **Timkontroll för funktionsplats** / **Timkontroll för arbetsorder** väljer du en period som ska beräknas i fälten **Från datum** och **Till datum**.</span><span class="sxs-lookup"><span data-stu-id="8a70e-112">In the **Asset hour control** / **Functional location hour control** / **Work order hour control** dialog, select a period to be calculated in the **From date** and **To date** fields.</span></span>

4. <span data-ttu-id="8a70e-113">Välj vid behov en **ekonomisk dimensionsuppsättning** som ska inkluderas i beräkningen.</span><span class="sxs-lookup"><span data-stu-id="8a70e-113">If required, select a **Financial dimension set** to be included in the calculation.</span></span>

5. <span data-ttu-id="8a70e-114">Välj "Ja" på växlingsknappen **Hoppa över noll** om du inte vill visa resultat som innehåller noll timmar.</span><span class="sxs-lookup"><span data-stu-id="8a70e-114">Select "Yes" on the **Skip zero** toggle button if you don't want to show results containing zero hours.</span></span>

6. <span data-ttu-id="8a70e-115">Du kan använda fältet **Nivå** för att indikera hur detaljerad timkontrollraderna ska vara gällande funktionsplatser.</span><span class="sxs-lookup"><span data-stu-id="8a70e-115">You can use the **Level** field to indicate how detailed you want the hour control lines to be regarding functional locations.</span></span> 

    <span data-ttu-id="8a70e-116">Om du till exempel infogar siffran "1" i fältet och har en funktionsplatshierarki med flera nivåer, visas alla timkontrollrader för en funktionsplats på den översta nivån, och därmed kan också de timmar som finns på en rad läggas till från funktionsplatser på en lägre nivå.</span><span class="sxs-lookup"><span data-stu-id="8a70e-116">For example, if you insert the number "1" in the field, and you have a multi-level functional location hierarchy, all hour control lines for a functional location will be shown on the top level, and therefore the hours on a line may be added up from functional locations located at a lower level.</span></span> 
    
    <span data-ttu-id="8a70e-117">Om du infogar siffran "0" i fältet **Nivå** visas ett detaljerat resultat med alla timkontrollrader på alla de funktionsplatsnivåer som de är relaterade till.</span><span class="sxs-lookup"><span data-stu-id="8a70e-117">If you insert the number "0" in the **Level** field, you will see a detailed result showing all hour control lines on all the functional location levels to which they are related.</span></span>

7. <span data-ttu-id="8a70e-118">Välj "Ja" på växlingsknappen **Inkludera undertillgångar** om du vill visa kostnader som är relaterade till undertillgångar som separata rader.</span><span class="sxs-lookup"><span data-stu-id="8a70e-118">Select "Yes" on the **Include sub assets** toggle button to show costs related to sub assets as separate lines.</span></span>

8. <span data-ttu-id="8a70e-119">Om du vill begränsa sökningen kan du välja specifika tillgångar/funktionsplatser/arbetsorder på snabbfliken **Poster som ska ingå**.</span><span class="sxs-lookup"><span data-stu-id="8a70e-119">If you want to limit the search, you can select specific assets / functional locations / work orders on the **Records to include** FastTab.</span></span>

9. <span data-ttu-id="8a70e-120">Klicka på **OK** för att starta beräkningen.</span><span class="sxs-lookup"><span data-stu-id="8a70e-120">Click **OK** to start the calculation.</span></span>

10. <span data-ttu-id="8a70e-121">På sidan **Timkontroll för tillgång**, välj knapparna **Gruppera efter** för att visa den obligatoriska detaljnivån för beräkningen.</span><span class="sxs-lookup"><span data-stu-id="8a70e-121">On the **Asset hour control** page, click the **Group by** buttons to show the required detail level of the calculation.</span></span> <span data-ttu-id="8a70e-122">De valda knapparna **Gruppera efter** markeras.</span><span class="sxs-lookup"><span data-stu-id="8a70e-122">The selected **Group by** buttons are highlighted.</span></span> <span data-ttu-id="8a70e-123">Klicka på en knapp för att aktivera och inaktivera den.</span><span class="sxs-lookup"><span data-stu-id="8a70e-123">Click on a button to activate or deactivate it.</span></span>

## <a name="example"></a><span data-ttu-id="8a70e-124">Exempel</span><span class="sxs-lookup"><span data-stu-id="8a70e-124">Example</span></span>

<span data-ttu-id="8a70e-125">I skärmbilden nedan visas ett exempel på ett beräkningsresultat i **Timkontroll för tillgång**.</span><span class="sxs-lookup"><span data-stu-id="8a70e-125">The screenshot below shows an example of an **Asset hour control** calculation.</span></span>

- <span data-ttu-id="8a70e-126">I fältet **Ursprunglig budget** visas budgettimmar från arbetsorderprognosen.</span><span class="sxs-lookup"><span data-stu-id="8a70e-126">The **Original budget** field shows budget hours from the work order forecast.</span></span> 
- <span data-ttu-id="8a70e-127">I fältet **Faktiska timmar** visas bokförda timmar på arbetsorder.</span><span class="sxs-lookup"><span data-stu-id="8a70e-127">The **Actual hours** field shows posted hours on work orders.</span></span> 
- <span data-ttu-id="8a70e-128">I fältet **Utfäst tid** visas det totala antalet timmar som ditt företag är förpliktigat att utföra i relation till arbetsorder.</span><span class="sxs-lookup"><span data-stu-id="8a70e-128">The **Committed hours** field shows total amount of hours that your company is committed to in relation to work orders.</span></span>

![Exempel på beräkning av timkontroll för tillgång](media/04-controlling-and-reporting.png)

<span data-ttu-id="8a70e-130">Ett annat sätt att göra en timberäkning är att använda flera tillgångar i **Alla tillgångar** eller **Aktiva tillgångar**.</span><span class="sxs-lookup"><span data-stu-id="8a70e-130">Another way of making an hour calculation is to multi-select assets in **All assets** or **Active assets**.</span></span> <span data-ttu-id="8a70e-131">Klicka sedan på knappen **Timkontroll** på snabbfliken **Allmänt**.</span><span class="sxs-lookup"><span data-stu-id="8a70e-131">Then you click the **Hour control** button on the **General** FastTab.</span></span> <span data-ttu-id="8a70e-132">De valda tillgångarna infogas automatiskt i fältet **Tillgång** på snabbfliken **Poster som ska ingå**.</span><span class="sxs-lookup"><span data-stu-id="8a70e-132">The selected assets are automatically inserted in the **Asset** field on the **Records to include** FastTab.</span></span> <span data-ttu-id="8a70e-133">Klicka på **OK** i dialogrutan **Timkontroll för tillgång** och beräkningen för de valda tillgångarna visas.</span><span class="sxs-lookup"><span data-stu-id="8a70e-133">Click **OK** in the **Asset hour control** dialog, and the calculation for the selected assets is shown.</span></span> <span data-ttu-id="8a70e-134">Samma procedur kan utföras för funktionsplatser i **Alla funktionsplatser** eller **Aktiva funktionsplatser**, och för arbetsorder i **Alla arbetsorder** eller **Aktiva arbetsorder**.</span><span class="sxs-lookup"><span data-stu-id="8a70e-134">The same procedure can be done for functional locations in **All functional locations** or **Active functional locations**, and for work orders in **All work orders** or **Active work orders**.</span></span>


