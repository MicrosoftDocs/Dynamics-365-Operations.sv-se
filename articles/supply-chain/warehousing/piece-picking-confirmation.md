---
title: Enhetsplockningsbekräftelse
description: Med enhetsplockning kan du bekräfta varje lagerenhet via plocknings- eller inventeringsarbete på en mobil enhet.
author: Mirzaab
ms.date: 05/26/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSRFAutoConfirm, WHSRFMenuItem
audience: Application User
ms.reviewer: kamaybac
ms.custom: 269384
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 3f9da533998341de60d210e196baae64d285d372
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5818858"
---
# <a name="piece-picking-confirmation"></a><span data-ttu-id="5abee-103">Enhetsplockningsbekräftelse</span><span class="sxs-lookup"><span data-stu-id="5abee-103">Piece picking confirmation</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="5abee-104">Med enhetsplockning kan du bekräfta varje lagerenhet via plocknings- eller inventeringsarbete på en mobil enhet.</span><span class="sxs-lookup"><span data-stu-id="5abee-104">Piece picking allows you to confirm each piece of inventory through picking or counting work on a mobile device.</span></span> <span data-ttu-id="5abee-105">För plockning, kan du bekräfta mängden arbete ska hanteras upp till den kvantitet som anges på det arbete som ska plockas.</span><span class="sxs-lookup"><span data-stu-id="5abee-105">For picks, you can confirm the quantity of work to be processed up to the quantity that is specified on work to be picked.</span></span> <span data-ttu-id="5abee-106">För inventeringsarbete kan du skanna lagret du inventerar och spåra det totala antalet.</span><span class="sxs-lookup"><span data-stu-id="5abee-106">For counting work, you can scan the inventory you are counting and track the total amount.</span></span>

<span data-ttu-id="5abee-107">Bekräftelse av produkten väljs automatiskt när du aktiverar enhetsplockning.</span><span class="sxs-lookup"><span data-stu-id="5abee-107">When you enable piece picking, product confirmation is automatically selected.</span></span> <span data-ttu-id="5abee-108">För arbetstypen kan du ange maximalt antal enheter.</span><span class="sxs-lookup"><span data-stu-id="5abee-108">For work-type picks, you can set a maximum number of pieces.</span></span> <span data-ttu-id="5abee-109">På så sätt kan du ange maximalt antal enheter som måste bekräftas under arbetsprocessen.</span><span class="sxs-lookup"><span data-stu-id="5abee-109">This allows you to set a maximum to the number of pieces that must be confirmed during the work process.</span></span> <span data-ttu-id="5abee-110">Den maximala kvantiteten är baserad på den aktuella arbetsenheten som bearbetas.</span><span class="sxs-lookup"><span data-stu-id="5abee-110">The maximum quantity is based on the current work unit that is being processed.</span></span> <span data-ttu-id="5abee-111">Arbetstypen Inventering tillåter inte ett maximum.</span><span class="sxs-lookup"><span data-stu-id="5abee-111">The counting work type does not allow a maximum.</span></span>

<span data-ttu-id="5abee-112">Du kan också använda kvantitet och måttenhet (UOM) som är associerad med en skannad streckkod.</span><span class="sxs-lookup"><span data-stu-id="5abee-112">You can also use the quantity and unit of measure (UOM) that is associated with a scanned bar code.</span></span> <span data-ttu-id="5abee-113">Den här metoden fungerar för inleverans på inkommande flöden inklusive inleverans av blandad registreringsskylt, artikel för inköpsorder, artikel för överföringsorder och lastartikel.</span><span class="sxs-lookup"><span data-stu-id="5abee-113">This will work for receiving on inbound flows including mixed license plate receiving, purchase order item, transfer order item, and load item.</span></span> <span data-ttu-id="5abee-114">Den fungerar även för enhetsplockning där skanning av streckkoden lägger till kvantiteten till det totala antalet bekräftade enheter som konverteras mellan måttenheten på streckkoden och arbetsenheten.</span><span class="sxs-lookup"><span data-stu-id="5abee-114">It also works for piece picking where scanning the bar code will add the quantity to the total number of confirmed pieces converting between the UOM on the bar code and the work unit.</span></span> <span data-ttu-id="5abee-115">Vid bekräftelse på att kvantiteten är godkänd för inventering i sekvensgruppen i samband med inventering av måttenheten på streckkoden läggs kvantiteten till i det totala antalet.</span><span class="sxs-lookup"><span data-stu-id="5abee-115">When counting the UOM on the bar code, if it is confirmed that the quantity is allowed for counting on the sequence group, the quantity will be added to the total count.</span></span>

## <a name="where-it-applies"></a><span data-ttu-id="5abee-116">Tillämpning</span><span class="sxs-lookup"><span data-stu-id="5abee-116">Where it applies</span></span>

<span data-ttu-id="5abee-117">Enhetsplockning fungerar för allt inventeringsarbete och för den ursprungliga plockningen för alla typer av arbete.</span><span class="sxs-lookup"><span data-stu-id="5abee-117">Piece picking works for all counting work and for the initial pick for any type of work.</span></span> <span data-ttu-id="5abee-118">Enhetsplockning gäller inte om artikeln styrs av serienummer eller om det är en tillverknings- eller kanban-plockning från en registreringsskyltsplats (LP) och artikeln är inställd till mellanlagring.</span><span class="sxs-lookup"><span data-stu-id="5abee-118">Piece picking does not apply if the item is controlled by serial numbers or if it is a production or kanban pick from a license plate (LP) location and the item is set to staging.</span></span>

## <a name="set-up-piece-picking"></a><span data-ttu-id="5abee-119">Ställa in enhetsplockning</span><span class="sxs-lookup"><span data-stu-id="5abee-119">Set up piece picking</span></span>

1.  <span data-ttu-id="5abee-120">I den mobila enhetens menyalternativ öppnar du inställningsformuläret för arbetsbekräftelse: Lagerstyrning > **Lagerstyrning** > **Inställningar** > **Mobil enhet** > **Mobila enhetens menyalternativ**.</span><span class="sxs-lookup"><span data-stu-id="5abee-120">On a mobile device menu item, open the setup form for work confirmation: Warehouse management > **Warehouse management** > **Setup** > **Mobile device** > **Mobile device menu items**.</span></span> 
2. <span data-ttu-id="5abee-121">Från den mobila enhetens menyalternativ öppnar du Inställning av arbetsbekräftelse.</span><span class="sxs-lookup"><span data-stu-id="5abee-121">From the mobile device menu item, open Work confirmation setup.</span></span>

<span data-ttu-id="5abee-122">Följande alternativ blir tillgängliga när arbetstypen är Plockning eller Inventering.</span><span class="sxs-lookup"><span data-stu-id="5abee-122">The following options become available for selection when the work type is pick or counting.</span></span>


|           <span data-ttu-id="5abee-123">Alternativ</span><span class="sxs-lookup"><span data-stu-id="5abee-123">Option</span></span>           |                                                                            <span data-ttu-id="5abee-124">beskrivning</span><span class="sxs-lookup"><span data-stu-id="5abee-124">Description</span></span>                                                                            |
|----------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="5abee-125">Enhetsplockningsbekräftelse</span><span class="sxs-lookup"><span data-stu-id="5abee-125">Piece picking confirmation</span></span> | <span data-ttu-id="5abee-126">Tillgängliga för arbetstyperna Plockning och Inventering.</span><span class="sxs-lookup"><span data-stu-id="5abee-126">Available for pick and counting work types.</span></span> <span data-ttu-id="5abee-127">Bekräftelse av produkten väljs automatiskt.</span><span class="sxs-lookup"><span data-stu-id="5abee-127">Product confirmation is automatically selected.</span></span> <span data-ttu-id="5abee-128">Låter dig bekräfta varje lagerenhet från den mobila enheten.</span><span class="sxs-lookup"><span data-stu-id="5abee-128">Allows you to confirm each piece of inventory from the mobile device.</span></span> |
|  <span data-ttu-id="5abee-129">Maximalt antal enheter</span><span class="sxs-lookup"><span data-stu-id="5abee-129">Maximum number of pieces</span></span>  |                   <span data-ttu-id="5abee-130">Tillgänglig för plockningsarbete om enhetsplockningsbekräftelse är aktiverad.</span><span class="sxs-lookup"><span data-stu-id="5abee-130">Available for pick work if piece picking confirmation is enabled.</span></span> <span data-ttu-id="5abee-131">Sätter en gräns för hur många enheter du måste bekräfta.</span><span class="sxs-lookup"><span data-stu-id="5abee-131">Sets a limit to the number of pieces that you must confirm.</span></span>                   |



[!INCLUDE[footer-include](../../includes/footer-banner.md)]