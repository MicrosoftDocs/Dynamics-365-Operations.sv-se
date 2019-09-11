---
title: Servicenivå och beskrivning
description: I det här avsnittet beskrivs servicenivå och beskrivning i Tillgångshantering.
author: josaw1
manager: AnnBe
ms.date: 08/13/2019
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
ms.search.validFrom: 2019-08-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 5e645c25208f55b1032bc7f7c181c72db7a2f265
ms.sourcegitcommit: 802dbf0a744d70f9e546632d419415b0993331ab
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/13/2019
ms.locfileid: "1874657"
---
# <a name="service-level-and-description"></a><span data-ttu-id="cde6a-103">Servicenivå och beskrivning</span><span class="sxs-lookup"><span data-stu-id="cde6a-103">Service level and description</span></span>

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

<span data-ttu-id="cde6a-104">När du skapar en arbetsorder kanske du vill definiera servicenivåerna för den och lägga till en allmän beskrivning i den.</span><span class="sxs-lookup"><span data-stu-id="cde6a-104">When you create a work order, you might want to define the service levels for it and add a general description to it.</span></span> <span data-ttu-id="cde6a-105">Du kan skapa servicenivåer för arbetsorder på sidan **Servicenivåer för arbetsorder** och beskrivningar på sidan **Arbetsorderbeskrivning**.</span><span class="sxs-lookup"><span data-stu-id="cde6a-105">You can create work order service levels on the **Work order service levels** page and descriptions on the **Work order description** page.</span></span>

## <a name="create-a-service-level"></a><span data-ttu-id="cde6a-106">Skapa en servicenivå</span><span class="sxs-lookup"><span data-stu-id="cde6a-106">Create a service level</span></span>

1. <span data-ttu-id="cde6a-107">Välj **Tillgångshantering** \> **Inställningar** \> **Arbetsorder** \> **Servicenivå**.</span><span class="sxs-lookup"><span data-stu-id="cde6a-107">Select **Asset management** \> **Setup** \> **Work orders** \> **Service level**.</span></span>
2. <span data-ttu-id="cde6a-108">Välj **Ny**.</span><span class="sxs-lookup"><span data-stu-id="cde6a-108">Select **New**.</span></span>
3. <span data-ttu-id="cde6a-109">I fältet **Servicenivå** anger du servicenivå (t.ex. en siffra).</span><span class="sxs-lookup"><span data-stu-id="cde6a-109">In the **Service level** field, enter the service level (for example, a number).</span></span>
4. <span data-ttu-id="cde6a-110">Ange sedan ett namn i fältet **Namn**.</span><span class="sxs-lookup"><span data-stu-id="cde6a-110">In the **Name** field, enter a name.</span></span>

    <span data-ttu-id="cde6a-111">På snabbfliken **Arbetsorder** kan du definiera förväntade start-och slutdatum och start- och sluttider.</span><span class="sxs-lookup"><span data-stu-id="cde6a-111">On the **Work orders** FastTab, you can define expected start and end dates and times.</span></span> <span data-ttu-id="cde6a-112">Fälten på den här snabbfliken definierar den period som arbetsorder ska startas och avslutas under.</span><span class="sxs-lookup"><span data-stu-id="cde6a-112">The fields on this FastTab define the period that work orders should be started and ended during.</span></span> <span data-ttu-id="cde6a-113">De används för arbetsorder som skapas manuellt och arbetsorder som skapas baserat på underhållsbegäranden.</span><span class="sxs-lookup"><span data-stu-id="cde6a-113">They are used for work orders that are manually created and work orders that are created based on maintenance requests.</span></span> 

5. <span data-ttu-id="cde6a-114">I fältet **Startdag** anger du ett antal dagar för att definiera den period som arbetsordern ska starta under.</span><span class="sxs-lookup"><span data-stu-id="cde6a-114">In the **Start day** field, enter a number of days to define the period that the work order should start during.</span></span> <span data-ttu-id="cde6a-115">Antalet dagar beräknas från arbetsorderns skapandedatum.</span><span class="sxs-lookup"><span data-stu-id="cde6a-115">The number of days is calculated from the creation date of the work order.</span></span> <span data-ttu-id="cde6a-116">Om till exempel arbetsordern ska starta när den skapas anger du **0**.</span><span class="sxs-lookup"><span data-stu-id="cde6a-116">For example, if the work order should start when it's created, enter **0**.</span></span> <span data-ttu-id="cde6a-117">Om arbetsordern ska starta inom en vecka efter att den skapats anger du **7**.</span><span class="sxs-lookup"><span data-stu-id="cde6a-117">If the work order should start within one week after it's created, enter **7**.</span></span>
6. <span data-ttu-id="cde6a-118">Om du vill ange en starttid för arbetsordern, utöver startdatumet, ställer du in alternativet **Ange starttid** till **Ja**.</span><span class="sxs-lookup"><span data-stu-id="cde6a-118">To set a start time for the work order, in addition to a start date, set the **Set start time** option to **Yes**.</span></span> <span data-ttu-id="cde6a-119">Ange starttiden i fältet **Starttid**.</span><span class="sxs-lookup"><span data-stu-id="cde6a-119">Then enter the start time in the **Start time** field.</span></span> <span data-ttu-id="cde6a-120">Om du ställer in alternativet till **Nej**, används den aktuella tiden på dagen.</span><span class="sxs-lookup"><span data-stu-id="cde6a-120">If you set the option to **No**, the current time of day is used.</span></span>
7. <span data-ttu-id="cde6a-121">I fältet **Slutdag** anger du ett antal dagar för att definiera den period som arbetsordern ska sluta under.</span><span class="sxs-lookup"><span data-stu-id="cde6a-121">In the **End day** field, enter a number of days to define the period that the work order should end during.</span></span> <span data-ttu-id="cde6a-122">Antalet dagar beräknas från arbetsorderns startdatum.</span><span class="sxs-lookup"><span data-stu-id="cde6a-122">The number of days is calculated from the start date of the work order.</span></span> <span data-ttu-id="cde6a-123">Om arbetsordern t.ex. ska sluta inom en vecka efter startdatum anger **7**.</span><span class="sxs-lookup"><span data-stu-id="cde6a-123">For example, if the work order should end within one week of its start date, enter **7**.</span></span>
8. <span data-ttu-id="cde6a-124">Om du vill ange en sluttid för arbetsordern, utöver slutdatumet, ställer du in alternativet **Ange sluttid** till **Ja**.</span><span class="sxs-lookup"><span data-stu-id="cde6a-124">To set an end time for the work order, in addition to an end date, set the **Set end time** option to **Yes**.</span></span> <span data-ttu-id="cde6a-125">Ange sluttiden i fältet **Sluttid**.</span><span class="sxs-lookup"><span data-stu-id="cde6a-125">Then enter the end time in the **End time** field.</span></span> <span data-ttu-id="cde6a-126">Om du ställer in alternativet till **Nej**, används den aktuella tiden på dagen.</span><span class="sxs-lookup"><span data-stu-id="cde6a-126">If you set the option to **No**, the current time of day is used.</span></span>
9. <span data-ttu-id="cde6a-127">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="cde6a-127">Select **Save**.</span></span>

![Figur 1](media/19-setup-for-work-orders.png)

## <a name="create-a-description"></a><span data-ttu-id="cde6a-129">Skapa en beskrivning</span><span class="sxs-lookup"><span data-stu-id="cde6a-129">Create a description</span></span>

1. <span data-ttu-id="cde6a-130">Välj **Tillgångshantering** \> **Inställningar** \> **Arbetsorder** \> **Beskrivningar**.</span><span class="sxs-lookup"><span data-stu-id="cde6a-130">Select **Asset management** \> **Setup** \> **Work orders** \> **Descriptions**.</span></span>
2. <span data-ttu-id="cde6a-131">Välj **Ny**.</span><span class="sxs-lookup"><span data-stu-id="cde6a-131">Select **New**.</span></span>
3. <span data-ttu-id="cde6a-132">Ange en beskrivning i fältet **Beskrivning**.</span><span class="sxs-lookup"><span data-stu-id="cde6a-132">In the **Description** field, enter the description.</span></span>
4. <span data-ttu-id="cde6a-133">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="cde6a-133">Select **Save**.</span></span>
