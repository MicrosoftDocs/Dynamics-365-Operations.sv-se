---
title: Skapa förbrukningsrapporter
description: I det här avsnittet beskrivs hur du skapar förbrukningsrapporter i Tillgångshantering.
author: josaw1
manager: tfehr
ms.date: 08/21/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 5e32924c71fd221caee4a7f413908120014ec8c5
ms.sourcegitcommit: deac22ba5377a912d93fe408c5ae875706378c2d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/16/2021
ms.locfileid: "5022543"
---
# <a name="create-consumption-reports"></a><span data-ttu-id="e8c1d-103">Skapa förbrukningsrapporter</span><span class="sxs-lookup"><span data-stu-id="e8c1d-103">Create consumption reports</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="e8c1d-104">När du har skapat och bokfört förbrukningsregistreringar för arbetsorder i Tillgångshantering finns det två rapporter som kan visa information om förbrukningen.</span><span class="sxs-lookup"><span data-stu-id="e8c1d-104">When you've created and posted consumption registrations on work orders in Asset Management, two reports are available to display consumption details.</span></span>


## <a name="asset-consumption-report"></a><span data-ttu-id="e8c1d-105">Rapport om tillgångsförbrukning</span><span class="sxs-lookup"><span data-stu-id="e8c1d-105">Asset consumption report</span></span>

<span data-ttu-id="e8c1d-106">När du har bokfört förbrukning på arbetsorder kan du skriva ut en rapport över tillgångsförbrukning.</span><span class="sxs-lookup"><span data-stu-id="e8c1d-106">When you have posted consumption on work orders, you can print an asset consumption report.</span></span> <span data-ttu-id="e8c1d-107">I rapporten visas timmar, timkostnader, artikel kostnader och utgifter som har bokförts på tillgångar.</span><span class="sxs-lookup"><span data-stu-id="e8c1d-107">The report displays hours, hour costs, item costs, and expenses posted on assets.</span></span>

1. <span data-ttu-id="e8c1d-108">Klicka på **Tillgångshantering** > **Rapporter** > **Tillgångar** > **Tillgångsförbrukning**.</span><span class="sxs-lookup"><span data-stu-id="e8c1d-108">Click **Asset management** > **Reports** > **Assets** > **Asset consumption**.</span></span>

2. <span data-ttu-id="e8c1d-109">I dialogrutan **Tillgångsförbrukning** väljer du de parametrar och den detaljnivå som du vill visa genom att välja **Ja** på de relevanta växlingsknapparna och infoga en funktionsplatsnivå i avsnittet **Visa**.</span><span class="sxs-lookup"><span data-stu-id="e8c1d-109">In the **Asset consumption** dialog, select the parameters and detail level you want to see by selecting **Yes** on the relevant toggle buttons, and inserting a functional location level in the **Show** section.</span></span>
    - <span data-ttu-id="e8c1d-110">Du kan använda fältet **Nivåer** för att indikera hur detaljerad tillgångsraderna ska vara gällande funktionsplatser.</span><span class="sxs-lookup"><span data-stu-id="e8c1d-110">You can use the **Levels** field to indicate how detailed you want the asset lines to be regarding functional locations.</span></span> 
    
        <span data-ttu-id="e8c1d-111">Om du till exempel infogar siffran "1" i fältet och har en funktionsplatsstruktur med flera nivåer, visas alla tillgångar för en funktionsplats på den översta nivån, och därmed kan också de timmar som finns på en rad läggas till från funktionsplatser på en lägre nivå.</span><span class="sxs-lookup"><span data-stu-id="e8c1d-111">For example, if you enter the number "1" in the field, and you have a multi-level functional location structure, all assets for a functional location will be shown on the top level, and therefore a line may be added up from functional locations located at a lower level.</span></span> 
        
        <span data-ttu-id="e8c1d-112">Om du infogar siffran "0" i fältet **Nivåer** visas ett detaljerat resultat med alla tillgångar på alla de funktionsplatsnivåer som de är relaterade till.</span><span class="sxs-lookup"><span data-stu-id="e8c1d-112">If you enter the number "0" in the **Levels** field, you will see a detailed result showing all assets on all the functional location levels to which they are related.</span></span> 
        
    - <span data-ttu-id="e8c1d-113">Välj **Ja** på växlingsknappen **Summa på alla undertillgångar** om du vill se summorna för varje undertillgång i rapporten.</span><span class="sxs-lookup"><span data-stu-id="e8c1d-113">Select **Yes** on the **Sum on all sub assets** toggle button to see sums for each sub asset in the report.</span></span>

3. <span data-ttu-id="e8c1d-114">Välj ett datumintervall i avsnittet **Datum**.</span><span class="sxs-lookup"><span data-stu-id="e8c1d-114">Select a date interval in the **Dates** section.</span></span>

4. <span data-ttu-id="e8c1d-115">På snabbfliken **Destination** väljer du om du vill visa rapporten på skärmen, skriva ut den eller spara den som en fil eller ett e-postmeddelande.</span><span class="sxs-lookup"><span data-stu-id="e8c1d-115">On the **Destination** FastTab, select if you want to display the report on screen, print it, or save it as a file or email.</span></span>

5. <span data-ttu-id="e8c1d-116">Vid behov kan du välja specifika tillgångar som ska visas i rapporten.</span><span class="sxs-lookup"><span data-stu-id="e8c1d-116">If required, you can select specific assets to be displayed in the report.</span></span> <span data-ttu-id="e8c1d-117">På snabbfliken **Poster som ska ingå** klickar du på **Filter** och lägger till de tillgångar som du vill inkludera i rapporten.</span><span class="sxs-lookup"><span data-stu-id="e8c1d-117">On the **Records to include** FastTab, click **Filter**, and add the assets you want to include in the report.</span></span>

6. <span data-ttu-id="e8c1d-118">Klicka på **OK** för att generera rapporten.</span><span class="sxs-lookup"><span data-stu-id="e8c1d-118">Click **OK** to generate the report.</span></span>


## <a name="work-order-consumption-report"></a><span data-ttu-id="e8c1d-119">Förbrukningsrapport för arbetsorder</span><span class="sxs-lookup"><span data-stu-id="e8c1d-119">Work order consumption report</span></span>

<span data-ttu-id="e8c1d-120">När du har bokfört förbrukning på arbetsorder kan du skriva ut en rapport över arbetsorderförbrukning.</span><span class="sxs-lookup"><span data-stu-id="e8c1d-120">When you have posted consumption on work orders, you can print a work order consumption report.</span></span> <span data-ttu-id="e8c1d-121">I rapporten visas timmar, timkostnader, artikel kostnader och utgifter som har bokförts på arbetsorder.</span><span class="sxs-lookup"><span data-stu-id="e8c1d-121">The report displays hours, hour costs, item costs, and expenses posted on work orders.</span></span>

1. <span data-ttu-id="e8c1d-122">Klicka på **Tillgångshantering** > **Rapporter** > **Arbetsorder** > **Arbetsorderförbrukning**.</span><span class="sxs-lookup"><span data-stu-id="e8c1d-122">Click **Asset management** > **Reports** > **Work orders** > **Work order consumption**.</span></span>

2. <span data-ttu-id="e8c1d-123">I dialogrutan **Arbetsorderförbrukning** väljer du de parametrar som du vill inkludera i rapporten genom att välja **Ja** på de relevanta växlingsknapparna i avsnittet **Visa**.</span><span class="sxs-lookup"><span data-stu-id="e8c1d-123">In the **Work order consumption** dialog, select the parameters you want to include in the report by selecting **Yes** on the relevant toggle buttons in the **Show** section.</span></span>

3. <span data-ttu-id="e8c1d-124">Välj ett datumintervall i avsnittet **Datum**.</span><span class="sxs-lookup"><span data-stu-id="e8c1d-124">Select a date interval in the **Dates** section.</span></span>

4. <span data-ttu-id="e8c1d-125">På snabbfliken **Destination** väljer du om du vill visa rapporten på skärmen, skriva ut den eller spara den som en fil eller ett e-postmeddelande.</span><span class="sxs-lookup"><span data-stu-id="e8c1d-125">On the **Destination** FastTab, select if you want to display the report on screen, print it, or save it as a file or email.</span></span>

5. <span data-ttu-id="e8c1d-126">Vid behov kan du välja specifika arbetsorder som ska visas i rapporten.</span><span class="sxs-lookup"><span data-stu-id="e8c1d-126">If required, you can select specific work orders to be displayed in the report.</span></span> <span data-ttu-id="e8c1d-127">På snabbfliken **Poster som ska ingå** klickar du på **Filter** och lägger till de arbetsorder som du vill inkludera i rapporten.</span><span class="sxs-lookup"><span data-stu-id="e8c1d-127">On the **Records to include** FastTab, click **Filter**, and add the work orders you want to include in the report.</span></span>

6. <span data-ttu-id="e8c1d-128">Klicka på **OK** för att generera rapporten.</span><span class="sxs-lookup"><span data-stu-id="e8c1d-128">Click **OK** to generate the report.</span></span>


>[!NOTE]
><span data-ttu-id="e8c1d-129">Du kan också skapa en [arbetsorderrapport](../work-orders/work-order-report.md)som innehåller mer information om arbetsorder.</span><span class="sxs-lookup"><span data-stu-id="e8c1d-129">You can also generate a [work order report](../work-orders/work-order-report.md), which contains more work order details.</span></span>

