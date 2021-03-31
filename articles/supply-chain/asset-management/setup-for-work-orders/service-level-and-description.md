---
title: Servicenivå och beskrivning
description: I det här avsnittet beskrivs servicenivå och beskrivning i Tillgångshantering.
author: josaw1
manager: tfehr
ms.date: 08/13/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetObjectServiceLevel, EntAssetWorkOrderStandardDescription, EntAssetWorkOrderServiceLevel, EntAssetServiceLevelLookup
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2019-08-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 65a3a0b6c2c052c41be469591c1281c1cce2b7d0
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5226795"
---
# <a name="service-level-and-description"></a><span data-ttu-id="d81bd-103">Servicenivå och beskrivning</span><span class="sxs-lookup"><span data-stu-id="d81bd-103">Service level and description</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="d81bd-104">När du skapar en arbetsorder kanske du vill definiera servicenivåerna för den och lägga till en allmän beskrivning i den.</span><span class="sxs-lookup"><span data-stu-id="d81bd-104">When you create a work order, you might want to define the service levels for it and add a general description to it.</span></span> <span data-ttu-id="d81bd-105">Du kan skapa servicenivåer för arbetsorder på sidan **Servicenivåer för arbetsorder** och beskrivningar på sidan **Arbetsorderbeskrivning**.</span><span class="sxs-lookup"><span data-stu-id="d81bd-105">You can create work order service levels on the **Work order service levels** page and descriptions on the **Work order description** page.</span></span>

## <a name="create-a-service-level"></a><span data-ttu-id="d81bd-106">Skapa en servicenivå</span><span class="sxs-lookup"><span data-stu-id="d81bd-106">Create a service level</span></span>

1. <span data-ttu-id="d81bd-107">Välj **Tillgångshantering** \> **Inställningar** \> **Arbetsorder** \> **Servicenivå**.</span><span class="sxs-lookup"><span data-stu-id="d81bd-107">Select **Asset management** \> **Setup** \> **Work orders** \> **Service level**.</span></span>
2. <span data-ttu-id="d81bd-108">Välj **Ny**.</span><span class="sxs-lookup"><span data-stu-id="d81bd-108">Select **New**.</span></span>
3. <span data-ttu-id="d81bd-109">I fältet **Servicenivå** anger du servicenivå (t.ex. en siffra).</span><span class="sxs-lookup"><span data-stu-id="d81bd-109">In the **Service level** field, enter the service level (for example, a number).</span></span>
4. <span data-ttu-id="d81bd-110">Ange sedan ett namn i fältet **Namn**.</span><span class="sxs-lookup"><span data-stu-id="d81bd-110">In the **Name** field, enter a name.</span></span>

    <span data-ttu-id="d81bd-111">På snabbfliken **Arbetsorder** kan du definiera förväntade start-och slutdatum och start- och sluttider.</span><span class="sxs-lookup"><span data-stu-id="d81bd-111">On the **Work orders** FastTab, you can define expected start and end dates and times.</span></span> <span data-ttu-id="d81bd-112">Fälten på den här snabbfliken definierar den period som arbetsorder ska startas och avslutas under.</span><span class="sxs-lookup"><span data-stu-id="d81bd-112">The fields on this FastTab define the period that work orders should be started and ended during.</span></span> <span data-ttu-id="d81bd-113">De används för arbetsorder som skapas manuellt och arbetsorder som skapas baserat på underhållsbegäranden.</span><span class="sxs-lookup"><span data-stu-id="d81bd-113">They are used for work orders that are manually created and work orders that are created based on maintenance requests.</span></span> 

5. <span data-ttu-id="d81bd-114">I fältet **Startdag** anger du ett antal dagar för att definiera den period som arbetsordern ska starta under.</span><span class="sxs-lookup"><span data-stu-id="d81bd-114">In the **Start day** field, enter a number of days to define the period that the work order should start during.</span></span> <span data-ttu-id="d81bd-115">Antalet dagar beräknas från arbetsorderns skapandedatum.</span><span class="sxs-lookup"><span data-stu-id="d81bd-115">The number of days is calculated from the creation date of the work order.</span></span> <span data-ttu-id="d81bd-116">Om till exempel arbetsordern ska starta när den skapas anger du **0**.</span><span class="sxs-lookup"><span data-stu-id="d81bd-116">For example, if the work order should start when it's created, enter **0**.</span></span> <span data-ttu-id="d81bd-117">Om arbetsordern ska starta inom en vecka efter att den skapats anger du **7**.</span><span class="sxs-lookup"><span data-stu-id="d81bd-117">If the work order should start within one week after it's created, enter **7**.</span></span>
6. <span data-ttu-id="d81bd-118">Om du vill ange en starttid för arbetsordern, utöver startdatumet, ställer du in alternativet **Ange starttid** till **Ja**.</span><span class="sxs-lookup"><span data-stu-id="d81bd-118">To set a start time for the work order, in addition to a start date, set the **Set start time** option to **Yes**.</span></span> <span data-ttu-id="d81bd-119">Ange starttiden i fältet **Starttid**.</span><span class="sxs-lookup"><span data-stu-id="d81bd-119">Then enter the start time in the **Start time** field.</span></span> <span data-ttu-id="d81bd-120">Om du ställer in alternativet till **Nej**, används den aktuella tiden på dagen.</span><span class="sxs-lookup"><span data-stu-id="d81bd-120">If you set the option to **No**, the current time of day is used.</span></span>
7. <span data-ttu-id="d81bd-121">I fältet **Slutdag** anger du ett antal dagar för att definiera den period som arbetsordern ska sluta under.</span><span class="sxs-lookup"><span data-stu-id="d81bd-121">In the **End day** field, enter a number of days to define the period that the work order should end during.</span></span> <span data-ttu-id="d81bd-122">Antalet dagar beräknas från arbetsorderns startdatum.</span><span class="sxs-lookup"><span data-stu-id="d81bd-122">The number of days is calculated from the start date of the work order.</span></span> <span data-ttu-id="d81bd-123">Om arbetsordern t.ex. ska sluta inom en vecka efter startdatum anger **7**.</span><span class="sxs-lookup"><span data-stu-id="d81bd-123">For example, if the work order should end within one week of its start date, enter **7**.</span></span>
8. <span data-ttu-id="d81bd-124">Om du vill ange en sluttid för arbetsordern, utöver slutdatumet, ställer du in alternativet **Ange sluttid** till **Ja**.</span><span class="sxs-lookup"><span data-stu-id="d81bd-124">To set an end time for the work order, in addition to an end date, set the **Set end time** option to **Yes**.</span></span> <span data-ttu-id="d81bd-125">Ange sluttiden i fältet **Sluttid**.</span><span class="sxs-lookup"><span data-stu-id="d81bd-125">Then enter the end time in the **End time** field.</span></span> <span data-ttu-id="d81bd-126">Om du ställer in alternativet till **Nej**, används den aktuella tiden på dagen.</span><span class="sxs-lookup"><span data-stu-id="d81bd-126">If you set the option to **No**, the current time of day is used.</span></span>
9. <span data-ttu-id="d81bd-127">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="d81bd-127">Select **Save**.</span></span>

![Sidan Servicenivå för arbetsorder](media/19-setup-for-work-orders.png)

## <a name="create-a-description"></a><span data-ttu-id="d81bd-129">Skapa en beskrivning</span><span class="sxs-lookup"><span data-stu-id="d81bd-129">Create a description</span></span>

1. <span data-ttu-id="d81bd-130">Välj **Tillgångshantering** \> **Inställningar** \> **Arbetsorder** \> **Beskrivningar**.</span><span class="sxs-lookup"><span data-stu-id="d81bd-130">Select **Asset management** \> **Setup** \> **Work orders** \> **Descriptions**.</span></span>
2. <span data-ttu-id="d81bd-131">Välj **Ny**.</span><span class="sxs-lookup"><span data-stu-id="d81bd-131">Select **New**.</span></span>
3. <span data-ttu-id="d81bd-132">Ange en beskrivning i fältet **Beskrivning**.</span><span class="sxs-lookup"><span data-stu-id="d81bd-132">In the **Description** field, enter the description.</span></span>
4. <span data-ttu-id="d81bd-133">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="d81bd-133">Select **Save**.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]