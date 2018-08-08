---
title: "Enhetsplockningsbekräftelse"
description: "Det här avsnittet beskriver hur du ställer in och använder bekräftelse av komponentplockning från en mobil enhet."
author: Mirzaab
manager: AnnBe
ms.date: 05/26/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: WHSRFAutoConfirm, WHSRFMenuItem
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 269384
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 1d98cbff30620256c9d13e7b4a90314db150e33e
ms.openlocfilehash: 9b85414dd1385dc3d8c97632eaaeb252759590ff
ms.contentlocale: sv-se
ms.lasthandoff: 08/07/2018

---

# <a name="piece-picking-confirmation"></a><span data-ttu-id="ece94-103">Enhetsplockningsbekräftelse</span><span class="sxs-lookup"><span data-stu-id="ece94-103">Piece picking confirmation</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="ece94-104">Med enhetsplockning kan du bekräfta varje lagerenhet via plocknings- eller inventeringsarbete på en mobil enhet.</span><span class="sxs-lookup"><span data-stu-id="ece94-104">Piece picking allows you to confirm each piece of inventory through picking or counting work on a mobile device.</span></span> <span data-ttu-id="ece94-105">För plockning, kan du bekräfta mängden arbete ska hanteras upp till den kvantitet som anges på det arbete som ska plockas.</span><span class="sxs-lookup"><span data-stu-id="ece94-105">For picks, you can confirm the quantity of work to be processed up to the quantity that is specified on work to be picked.</span></span> <span data-ttu-id="ece94-106">För inventeringsarbete kan du skanna lagret du inventerar och spåra det totala antalet.</span><span class="sxs-lookup"><span data-stu-id="ece94-106">For counting work, you can scan the inventory that you are counting and track the total amount.</span></span>

<span data-ttu-id="ece94-107">Bekräftelse av produkten väljs automatiskt när du aktiverar enhetsplockning.</span><span class="sxs-lookup"><span data-stu-id="ece94-107">When you enable piece picking, product confirmation is automatically selected.</span></span> <span data-ttu-id="ece94-108">För arbetstypen Plockning aktiveras maximalt antal enheter.</span><span class="sxs-lookup"><span data-stu-id="ece94-108">For work-type picks, a maximum number of pieces is enabled.</span></span> <span data-ttu-id="ece94-109">På så sätt kan du ange maximalt antal enheter som måste bekräftas under arbetsprocessen.</span><span class="sxs-lookup"><span data-stu-id="ece94-109">This allows you to set a maximum to the number of pieces that must be confirmed during the work process.</span></span> <span data-ttu-id="ece94-110">Den maximala kvantiteten är baserad på den aktuella arbetsenheten som bearbetas.</span><span class="sxs-lookup"><span data-stu-id="ece94-110">The maximum quantity is based on the current work unit that is being processed.</span></span> <span data-ttu-id="ece94-111">Arbetstypen Inventering tillåter inte ett maximum.</span><span class="sxs-lookup"><span data-stu-id="ece94-111">The counting work type does not allow a maximum.</span></span>

<span data-ttu-id="ece94-112">Du kan också använda kvantitet och måttenhet (UOM) som är associerad med en skannad streckkod.</span><span class="sxs-lookup"><span data-stu-id="ece94-112">You can also use the quantity and unit of measure (UOM) that is associated with a scanned bar code.</span></span> <span data-ttu-id="ece94-113">Den här metoden fungerar för inleverans på inkommande flöden inklusive inleverans av blandad registreringsskylt, artikel för inköpsorder, artikel för överföringsorder och lastartikel.</span><span class="sxs-lookup"><span data-stu-id="ece94-113">This will work for receiving on inbound flows including mixed license plate receiving, purchase order item, transfer order item, and load item.</span></span> <span data-ttu-id="ece94-114">Den fungerar även för enhetsplockning där skanning av streckkoden lägger till kvantiteten till det totala antalet bekräftade enheter som konverteras mellan måttenheten på streckkoden och arbetsenheten.</span><span class="sxs-lookup"><span data-stu-id="ece94-114">It also works for piece picking where scanning the bar code will add the quantity to the total number of confirmed pieces converting between the UOM on the bar code and the work unit.</span></span> <span data-ttu-id="ece94-115">Vid bekräftelse på att kvantiteten är godkänd för inventering i sekvensgruppen i samband med inventering av måttenheten på streckkoden läggs kvantiteten till i det totala antalet.</span><span class="sxs-lookup"><span data-stu-id="ece94-115">If, when counting the UOM on the bar code, it is confirmed that the quantity is allowed for counting on the sequence group, the quantity will be added to the total count.</span></span>

## <a name="where-it-applies"></a><span data-ttu-id="ece94-116">Tillämpning</span><span class="sxs-lookup"><span data-stu-id="ece94-116">Where it applies</span></span>

<span data-ttu-id="ece94-117">Enhetsplockning fungerar för allt inventeringsarbete och för den ursprungliga plockningen för alla typer av arbete.</span><span class="sxs-lookup"><span data-stu-id="ece94-117">Piece picking works for all counting work and for the initial pick for any type of work.</span></span> <span data-ttu-id="ece94-118">Enhetsplockning gäller inte om artikeln styrs av serienummer eller om det är en tillverknings- eller kanban-plockning från en registreringsskyltsplats (LP) och artikeln är inställd till mellanlagring.</span><span class="sxs-lookup"><span data-stu-id="ece94-118">Piece picking does not apply if the item is controlled by serial numbers or if it is a production or kanban pick from a license plate (LP) location and the item is set to staging.</span></span>

## <a name="set-up-piece-picking"></a><span data-ttu-id="ece94-119">Ställa in enhetsplockning</span><span class="sxs-lookup"><span data-stu-id="ece94-119">Set up piece picking</span></span>

1.  <span data-ttu-id="ece94-120">I den mobila enhetens menyalternativ öppnar du inställningsformuläret för arbetsbekräftelse: Lagerstyrning > **Lagerstyrning** > **Inställningar** > **Mobil enhet** > **Mobila enhetens menyalternativ**.</span><span class="sxs-lookup"><span data-stu-id="ece94-120">On a mobile device menu item, open the setup form for work confirmation: Warehouse management > **Warehouse management** > **Setup** > **Mobile device** > **Mobile device menu items**.</span></span> 
2. <span data-ttu-id="ece94-121">Från den mobila enhetens menyalternativ öppnar du Inställning av arbetsbekräftelse.</span><span class="sxs-lookup"><span data-stu-id="ece94-121">From the mobile device menu item, open Work confirmation setup.</span></span>

<span data-ttu-id="ece94-122">Följande alternativ blir tillgängliga när arbetstypen är Plockning eller Inventering.</span><span class="sxs-lookup"><span data-stu-id="ece94-122">The following options become available for selection when the work type is pick or counting.</span></span>


|           <span data-ttu-id="ece94-123">Alternativ</span><span class="sxs-lookup"><span data-stu-id="ece94-123">Option</span></span>           |                                                                            <span data-ttu-id="ece94-124">beskrivning</span><span class="sxs-lookup"><span data-stu-id="ece94-124">Description</span></span>                                                                            |
|----------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="ece94-125">Enhetsplockningsbekräftelse</span><span class="sxs-lookup"><span data-stu-id="ece94-125">Piece picking confirmation</span></span> | <span data-ttu-id="ece94-126">Tillgängliga för arbetstyperna Plockning och Inventering.</span><span class="sxs-lookup"><span data-stu-id="ece94-126">Available for pick and counting work types.</span></span> <span data-ttu-id="ece94-127">Bekräftelse av produkten väljs automatiskt.</span><span class="sxs-lookup"><span data-stu-id="ece94-127">Product confirmation is automatically selected.</span></span> <span data-ttu-id="ece94-128">Låter dig bekräfta varje lagerenhet från den mobila enheten.</span><span class="sxs-lookup"><span data-stu-id="ece94-128">Allows you to confirm each piece of inventory from the mobile device.</span></span> |
|  <span data-ttu-id="ece94-129">Maximalt antal enheter</span><span class="sxs-lookup"><span data-stu-id="ece94-129">Maximum number of pieces</span></span>  |                   <span data-ttu-id="ece94-130">Tillgänglig för plockningsarbete om enhetsplockningsbekräftelse är aktiverad.</span><span class="sxs-lookup"><span data-stu-id="ece94-130">Available for pick work if piece picking confirmation is enabled.</span></span> <span data-ttu-id="ece94-131">Sätter en gräns för hur många enheter du måste bekräfta.</span><span class="sxs-lookup"><span data-stu-id="ece94-131">Sets a limit to the number of pieces that you must confirm.</span></span>                   |


