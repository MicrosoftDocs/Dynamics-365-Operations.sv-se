---
title: Du kan inte bekräfta en försändelse på grund av att arbetet inte är slutförd eller saknas
description: Du kan inte bekräfta en försändelse på grund av att arbetet inte är slutförd eller saknas
author: perlynne
ms.date: 04/21/2021
ms.topic: troubleshooting
ms.search.form: WHSLoadTable_WHSShipConfirm,WHSLoadPlanningListPage_WHSShipConfirm,WHSLoadPlanningWorkbench_WHSShipConfirm,WHSTransportLoad_WHSShipConfirm,WHSShipPlanningListPage_WHSShipConfirm,WHSShipmentDetails_WHSShipConfirm,WHSWorkTable_WHSShipConfirm,WHSWorkTableListPage_WHSShipConfirm,Dialog_WHSOutboundShipConfirmController_WHSOutboundShipConfirm, WHSContainerCloseDiag_WHSShipConfirm
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: lbc
ms.search.validFrom: 2021-04-21
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: beef0909d41e69f3e7bcc1021527be35b7e6fd44
ms.sourcegitcommit: c2c6d687a89bc1534c029109315c23e92865b63b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/31/2021
ms.locfileid: "6123853"
---
# <a name="you-cant-confirm-a-shipment-because-of-incomplete-or-missing-work"></a><span data-ttu-id="c1b75-103">Du kan inte bekräfta en försändelse på grund av att arbetet inte är slutförd eller saknas</span><span class="sxs-lookup"><span data-stu-id="c1b75-103">You can't confirm a shipment because of incomplete or missing work</span></span>

<span data-ttu-id="c1b75-104">Felkod: WAX515</span><span class="sxs-lookup"><span data-stu-id="c1b75-104">Error code: WAX515</span></span>

## <a name="symptoms"></a><span data-ttu-id="c1b75-105">Symtom</span><span class="sxs-lookup"><span data-stu-id="c1b75-105">Symptoms</span></span>

<span data-ttu-id="c1b75-106">När du försöker bekräfta en leverans visas följande felmeddelande i systemet:</span><span class="sxs-lookup"><span data-stu-id="c1b75-106">When you try to confirm a shipment, the system shows the following error message:</span></span>

> <span data-ttu-id="c1b75-107">Det gick inte att bekräfta leveransen av lasten %1 eftersom alla arbetsuppgifter för lasten måste slutföras.</span><span class="sxs-lookup"><span data-stu-id="c1b75-107">The shipment for load %1 could not be confirmed because all work for the load must be complete.</span></span>

<span data-ttu-id="c1b75-108">Du kan därför inte bekräfta leveransen för beläggningen.</span><span class="sxs-lookup"><span data-stu-id="c1b75-108">Therefore, you can't confirm the shipment for the load.</span></span>

## <a name="cause"></a><span data-ttu-id="c1b75-109">Orsak</span><span class="sxs-lookup"><span data-stu-id="c1b75-109">Cause</span></span>

<span data-ttu-id="c1b75-110">Beläggningen eller leveransen befinner sig för närvarande i ett skick där leveransbekräftelsen misslyckas.</span><span class="sxs-lookup"><span data-stu-id="c1b75-110">The load or shipment is currently in a state where shipment confirmation fails.</span></span> <span data-ttu-id="c1b75-111">Innan du kan bekräfta leveransen måste det minst finnas arbete för beläggningen, och allt detta arbete måste ha statusen *Stängd* eller *Annullerad*.</span><span class="sxs-lookup"><span data-stu-id="c1b75-111">Before you can confirm the shipment, at least some work must exist for the load, and all that work must have a status of *Closed* or *Canceled*.</span></span>

## <a name="resolution"></a><span data-ttu-id="c1b75-112">Upplösning</span><span class="sxs-lookup"><span data-stu-id="c1b75-112">Resolution</span></span>

<span data-ttu-id="c1b75-113">Kontrollera relaterade försäljnings- eller överföringsorder för beläggningen eller försändelsen, och se till att allt relaterat arbete har slutförts eller annullerats.</span><span class="sxs-lookup"><span data-stu-id="c1b75-113">Check the related sales orders or transfer orders for the load or shipment, and make sure that all the related work has been completed or canceled.</span></span>

<span data-ttu-id="c1b75-114">Du kan arbeta med försändelser och beläggningar på flera sidor.</span><span class="sxs-lookup"><span data-stu-id="c1b75-114">You can work with shipments and loads on several pages.</span></span> <span data-ttu-id="c1b75-115">Följande delavsnitt ger några exempel.</span><span class="sxs-lookup"><span data-stu-id="c1b75-115">The following subsections provide a few examples.</span></span>

### <a name="all-loads-page"></a><span data-ttu-id="c1b75-116">Sida för samtliga beläggningar</span><span class="sxs-lookup"><span data-stu-id="c1b75-116">All loads page</span></span>

1. <span data-ttu-id="c1b75-117">Gå till **Lagerstyrning \> Laster \> Alla laster**.</span><span class="sxs-lookup"><span data-stu-id="c1b75-117">Go to **Warehouse management \> Loads \> All loads**.</span></span>
1. <span data-ttu-id="c1b75-118">Välj den beläggning som leveransen inte kan bekräftas för.</span><span class="sxs-lookup"><span data-stu-id="c1b75-118">Select the load that the shipment can't be confirmed for.</span></span>
1. <span data-ttu-id="c1b75-119">I åtgärdsfönstret, på fliken **Geläggningar**, i gruppen **Relaterad information**, väljer du **Arbete**.</span><span class="sxs-lookup"><span data-stu-id="c1b75-119">On the Action Pane, on the **Loads** tab, in the **Related information** group, select **Work**.</span></span>
1. <span data-ttu-id="c1b75-120">Inspektera statusen för respektive arbets-ID.</span><span class="sxs-lookup"><span data-stu-id="c1b75-120">Inspect the status of each work ID.</span></span> <span data-ttu-id="c1b75-121">Följ upp varje arbets-ID som inte har statusen *Stängd* eller *Annullerad*.</span><span class="sxs-lookup"><span data-stu-id="c1b75-121">Follow up on each work ID that doesn't have a status of *Closed* or *Canceled*.</span></span>
1. <span data-ttu-id="c1b75-122">Om varje arbets-ID har statusen *Stängd* eller *Annullerad* ska du försöka igen för att bekräfta försändelsen.</span><span class="sxs-lookup"><span data-stu-id="c1b75-122">When every work ID has a status of *Closed* or *Canceled*, try again to confirm the shipment.</span></span>

### <a name="all-shipments-page"></a><span data-ttu-id="c1b75-123">Sida för alla leveranser</span><span class="sxs-lookup"><span data-stu-id="c1b75-123">All shipments page</span></span>

1. <span data-ttu-id="c1b75-124">Gå till **Lagerstyrning \> Leveranser \> Alla leveranser**.</span><span class="sxs-lookup"><span data-stu-id="c1b75-124">Go to **Warehouse management \> Shipments\> All shipments**.</span></span>
1. <span data-ttu-id="c1b75-125">Välj den försändelse som inte kan bekräftas.</span><span class="sxs-lookup"><span data-stu-id="c1b75-125">Select the shipment that can't be confirmed.</span></span>
1. <span data-ttu-id="c1b75-126">I åtgärdsfönstret, på fliken **Försändelser**, i gruppen **Arbete**, väljer du **Arbetsdetaljer**.</span><span class="sxs-lookup"><span data-stu-id="c1b75-126">On the Action Pane, on the **Shipments** tab, in the **Work** group, select **Work details**.</span></span>
1. <span data-ttu-id="c1b75-127">Inspektera statusen för respektive arbets-ID.</span><span class="sxs-lookup"><span data-stu-id="c1b75-127">Inspect the status of each work ID.</span></span> <span data-ttu-id="c1b75-128">Följ upp varje arbets-ID som inte har statusen *Stängd* eller *Annullerad*.</span><span class="sxs-lookup"><span data-stu-id="c1b75-128">Follow up on each work ID that doesn't have a status of *Closed* or *Canceled*.</span></span>
1. <span data-ttu-id="c1b75-129">Om varje arbets-ID har statusen *Stängd* eller *Annullerad* ska du försöka igen för att bekräfta försändelsen.</span><span class="sxs-lookup"><span data-stu-id="c1b75-129">When every work ID has a status of *Closed* or *Canceled*, try again to confirm the shipment.</span></span>

### <a name="all-work-page"></a><span data-ttu-id="c1b75-130">Sia för alla arbeten</span><span class="sxs-lookup"><span data-stu-id="c1b75-130">All work page</span></span>

1. <span data-ttu-id="c1b75-131">Gå till **Lagerstyrning \> Arbete\> Allt arbete**.</span><span class="sxs-lookup"><span data-stu-id="c1b75-131">Go to **Warehouse management \> Work\> All work**.</span></span>
1. <span data-ttu-id="c1b75-132">Välj arbetet för det ordernummer som försändelsen inte kan bekräftas för.</span><span class="sxs-lookup"><span data-stu-id="c1b75-132">Select the work for the order number that the shipment can't be confirmed for.</span></span>
1. <span data-ttu-id="c1b75-133">I åtgärdsfönstret: På fliken **Försändelse**, i gruppen **Försändelse**, väljer du **Bekräfta försändelse**.</span><span class="sxs-lookup"><span data-stu-id="c1b75-133">On the Action Pane, on the **Shipment** tab, in the **Shipment** group, select **Confirm shipment**.</span></span>
1. <span data-ttu-id="c1b75-134">Inspektera statusen för respektive arbets-ID.</span><span class="sxs-lookup"><span data-stu-id="c1b75-134">Inspect the status of each work ID.</span></span> <span data-ttu-id="c1b75-135">Följ upp varje arbets-ID som inte har statusen *Stängd* eller *Annullerad*.</span><span class="sxs-lookup"><span data-stu-id="c1b75-135">Follow up on each work ID that doesn't have a status of *Closed* or *Canceled*.</span></span>
1. <span data-ttu-id="c1b75-136">Om varje arbets-ID har statusen *Stängd* eller *Annullerad* ska du försöka igen för att bekräfta försändelsen.</span><span class="sxs-lookup"><span data-stu-id="c1b75-136">When every work ID has a status of *Closed* or *Canceled*, try again to confirm the shipment.</span></span>
