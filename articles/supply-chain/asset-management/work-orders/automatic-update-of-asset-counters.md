---
title: Automatisk uppdatering av tillgångsräknare
description: Det här avsnittet beskriver automatisk uppdatering av tillgångsräknare i Tillgångshantering.
author: josaw1
manager: AnnBe
ms.date: 10/15/2019
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
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: d51b9a7684e460d555632c3896e9dd8a4e10d92c
ms.sourcegitcommit: deb87e518a151d8bb084891851a39758938a96e4
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/15/2019
ms.locfileid: "2626188"
---
# <a name="automatic-update-of-asset-counters"></a><span data-ttu-id="227ee-103">Automatisk uppdatering av tillgångsräknare</span><span class="sxs-lookup"><span data-stu-id="227ee-103">Automatic update of asset counters</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="227ee-104">Mer information om manuell registrering av tillgångsräknare finns i [Manuell uppdatering av tillgångsräknare](../work-orders/manual-update-of-asset-counters.md).</span><span class="sxs-lookup"><span data-stu-id="227ee-104">For information about manual registration of asset counters, see [Manual update of asset counters](../work-orders/manual-update-of-asset-counters.md).</span></span> <span data-ttu-id="227ee-105">Mer information om hur du ställer in tillgångsräknare finns i [räknare](../setup-for-objects/counters.md).</span><span class="sxs-lookup"><span data-stu-id="227ee-105">For information on how to set up asset counters, see [Counters](../setup-for-objects/counters.md).</span></span>

<span data-ttu-id="227ee-106">Räknarvärden kan också uppdateras automatiskt från produktionsregistreringar, baserat på produktionstimmar eller produktionskvantitet (det vill säga den kvantitet som produceras).</span><span class="sxs-lookup"><span data-stu-id="227ee-106">Counter values can also be automatically updated from production registrations, based on the production hours or production quantity (that is, the quantity that is produced).</span></span> <span data-ttu-id="227ee-107">Uppdateringen görs på sidan **uppdatera tillgångsräknare**.</span><span class="sxs-lookup"><span data-stu-id="227ee-107">This update is done on the **Update asset counters** page.</span></span> <span data-ttu-id="227ee-108">Du kan uppdatera en eller flera tillgångar genom att konfigurera en parameter, **Från datum**.</span><span class="sxs-lookup"><span data-stu-id="227ee-108">You can update one or several assets by setting one parameter, **From date**.</span></span> <span data-ttu-id="227ee-109">Den här parametern anger startdatum för produktionsregistreringar (produktionstimmar eller produktionskvantiteter).</span><span class="sxs-lookup"><span data-stu-id="227ee-109">This parameter specifies the start date for production registrations (production hours or production quantities).</span></span> <span data-ttu-id="227ee-110">Med andra ord anges det datum då räknarens värden ska uppdateras.</span><span class="sxs-lookup"><span data-stu-id="227ee-110">In other words, it specifies the date that counter values should be updated from.</span></span>

<span data-ttu-id="227ee-111">Alla tillgångar som är relaterade till en resurs *och* har tillgångsräknare, som har ställts in för uppdatering baserad på produktionstimmar eller produktionskvantitet tas med i en automatisk uppdatering.</span><span class="sxs-lookup"><span data-stu-id="227ee-111">All assets that are related to a resource, *and* that have asset counters that are set up to be updated based on the production hours or production quantity, will be included in an automatic update.</span></span> <span data-ttu-id="227ee-112">Nya räknarvärden kommer att skapas.</span><span class="sxs-lookup"><span data-stu-id="227ee-112">New counter values will be created.</span></span>

<span data-ttu-id="227ee-113">För räknare som baseras på produktionskvantiteten inkluderar antalet både den godkända kvantiteten och den felkvantitet som är registrerad.</span><span class="sxs-lookup"><span data-stu-id="227ee-113">For counters that are based on the production quantity, the count includes both the good quantity and the error quantity that are registered.</span></span> <span data-ttu-id="227ee-114">Om enheten som används för registrering av produktionskvantitet skiljer sig från den som används på räknaren, konverteras kvantiteten så att den motsvarar räknarenheten.</span><span class="sxs-lookup"><span data-stu-id="227ee-114">If the unit that is used for production quantity registration differs from the unit that is used for the counter, the quantity is converted so that it corresponds to the counter unit.</span></span>

<span data-ttu-id="227ee-115">Som nämnts ovan kan automatiska räknare uppdateras från produktionsregistreringar.</span><span class="sxs-lookup"><span data-stu-id="227ee-115">As mentioned above, automatic counters can be updated from production registrations.</span></span> <span data-ttu-id="227ee-116">Därför måste den tillgång som du vill uppdatera räknare automatiskt för vara relaterad till en resurs (dator).</span><span class="sxs-lookup"><span data-stu-id="227ee-116">Therefore, the asset for which you want to automatically update counters must be related to a resource (machine).</span></span> <span data-ttu-id="227ee-117">När producerade kvantiteter eller produktionstimmar har registrerats för resursen kan du uppdatera de relaterade räknarna för tillgångar.</span><span class="sxs-lookup"><span data-stu-id="227ee-117">When produced quantities or production hours have been registered on the resource, you can update the related asset counters.</span></span>

1. <span data-ttu-id="227ee-118">Klicka på **Tillgångshantering** > **Periodisk** > **Tillgångar** > **Uppdatera tillgångsräknare**.</span><span class="sxs-lookup"><span data-stu-id="227ee-118">Select **Asset management** > **Periodic** > **Assets** > **Update asset counters**.</span></span>

2. <span data-ttu-id="227ee-119">Välj startdatum för den automatiska uppdateringen i fältet **Från datum**.</span><span class="sxs-lookup"><span data-stu-id="227ee-119">In the **From date** field, select the start date of the automatic update.</span></span>

>[!NOTE]
><span data-ttu-id="227ee-120">Datumet i det här fältet är "pågående arbete"-datumet från **Flödestransaktioner** (**Produktionskontroll** > **Förfrågningar och rapporter** > **Produktion** > **Flödestransaktioner** >  fältet **Fysiskt datum**).</span><span class="sxs-lookup"><span data-stu-id="227ee-120">The date in this field is the "work in progress" date from **Route transactions** (**Production control** > **Inquiries and reports** > **Production** > **Route transactions** > **Physical date** field).</span></span>

3. <span data-ttu-id="227ee-121">På snabbfliken **Poster som ska ingå** kan du välja specifika tillgångar, tillgångstyper eller resurser för den automatiska uppdateringen.</span><span class="sxs-lookup"><span data-stu-id="227ee-121">On the **Records to include** FastTab, you can select specific assets, asset types, or resources for the automatic update.</span></span> <span data-ttu-id="227ee-122">Välj **filter**och gör relevanta val.</span><span class="sxs-lookup"><span data-stu-id="227ee-122">Select **Filter**, and make the relevant selections.</span></span>

4. <span data-ttu-id="227ee-123">På snabbfliken **Kör i bakgrunden** kan du ställa in den automatiska uppdateringen som ett batchjobb, efter behov.</span><span class="sxs-lookup"><span data-stu-id="227ee-123">On the **Run in the background** FastTab, you can set up the automatic update as a batch job, as you require.</span></span>

<span data-ttu-id="227ee-124">Bilden nedan visar ett exempel på dialogrutan **Uppdatera tillgångsräknare**.</span><span class="sxs-lookup"><span data-stu-id="227ee-124">The illustration below shows an example of the **Update asset counters** dialog.</span></span>

![Figur 1](media/12-work-orders.png)

5. <span data-ttu-id="227ee-126">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="227ee-126">Select **OK**.</span></span> 

<span data-ttu-id="227ee-127">När uppdateringen av tillgångsräknaren har genomförts kan du visa de räknarregistreringar som är relaterade till tillgången på sidan **Tillgångsräknare**.</span><span class="sxs-lookup"><span data-stu-id="227ee-127">After the automatic asset counter update is done, you can view the counter registrations that are related to the asset on the **Asset counters** page.</span></span> <span data-ttu-id="227ee-128">Välj **Tillgångshantering** > **Allmänt** > **Tillgångar** > **Alla tillgångar**, välj tillgången och sedan i åtgärdsfönstret på fliken **Tillgång** i gruppen **Förebyggande** väljer du **Räknare**.</span><span class="sxs-lookup"><span data-stu-id="227ee-128">Select **Asset management** > **Common** > **Assets** > **All assets**, select the asset, and then, on the Action Pane, on the **Asset** tab, in the **Preventive** group, select **Counters**.</span></span>

<span data-ttu-id="227ee-129">På sidan **Sammanlagt värde för tillgång** kan du få en översikt över den senaste registreringen som gjorts för alla räknartyper för alla tillgångar.</span><span class="sxs-lookup"><span data-stu-id="227ee-129">On the **Asset aggregated value** page, you can get an overview of the latest registration that have been made on all counter types on all assets.</span></span> <span data-ttu-id="227ee-130">Klicka på **Tillgångshantering** > **Förfrågningar** > **Tillgångar** > **Sammanlagt värde för tillgång**.</span><span class="sxs-lookup"><span data-stu-id="227ee-130">Select **Asset management** > **Inquiries** > **Assets** > **Asset aggregated value**.</span></span> <span data-ttu-id="227ee-131">Den här sidan liknar sidan **Tillgångsräknare**, men du kan inte lägga till eller redigera registreringar.</span><span class="sxs-lookup"><span data-stu-id="227ee-131">This page resembles the **Asset counters** page, but you can't add or edit registrations.</span></span> <span data-ttu-id="227ee-132">Den är endast för översikt.</span><span class="sxs-lookup"><span data-stu-id="227ee-132">It's for overview only.</span></span>

<span data-ttu-id="227ee-133">Bilden nedan visar ett exempel på sidan **Sammanlagt värde för tillgång**.</span><span class="sxs-lookup"><span data-stu-id="227ee-133">The illustration below shows an example of the **Asset aggregated value** page.</span></span>

![Figur 2](media/13-work-orders.png)

<span data-ttu-id="227ee-135">Observera följande:</span><span class="sxs-lookup"><span data-stu-id="227ee-135">Note the following points:</span></span>

- <span data-ttu-id="227ee-136">Du kan fortfarande skapa manuella räknarvärderegistreringar för räknartyper som uppdateras automatiskt.</span><span class="sxs-lookup"><span data-stu-id="227ee-136">You can still create manual counter value registrations for counter types that are automatically updated.</span></span> <span data-ttu-id="227ee-137">Mer information finns i  [Manuell uppdatering av tillgångsräknare](../work-orders/manual-update-of-asset-counters.md).</span><span class="sxs-lookup"><span data-stu-id="227ee-137">For more information, see [Manual update of asset counters](../work-orders/manual-update-of-asset-counters.md).</span></span>

- <span data-ttu-id="227ee-138">Du kan ställa in räknare som är relaterade till en annan räknare.</span><span class="sxs-lookup"><span data-stu-id="227ee-138">You can set up counters that are related to another counter.</span></span> <span data-ttu-id="227ee-139">I detta fall uppdateras relaterade räknare automatiskt samtidigt när en räknare uppdateras.</span><span class="sxs-lookup"><span data-stu-id="227ee-139">In this case, when a counter is updated, related counters are automatically updated at the same time.</span></span> <span data-ttu-id="227ee-140">Mer information om hur du ställer in relaterade räknare finns i [räknare](../setup-for-objects/counters.md).</span><span class="sxs-lookup"><span data-stu-id="227ee-140">For more information about how to set up related counters, see [Counters](../setup-for-objects/counters.md).</span></span>

