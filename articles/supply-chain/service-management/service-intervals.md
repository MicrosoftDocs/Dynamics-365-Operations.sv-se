---
title: Serviceintervall
description: Serviceintervallet anger frekvensen med vilken serviceorderrader skapas för serviceavtalsrader när du skapar serviceorder.
author: ShylaThompson
manager: tfehr
ms.date: 02/20/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMAAgreementTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1027a6a1ddb1057ba039382d394522d6f9538a90
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/10/2020
ms.locfileid: "3979146"
---
# <a name="service-intervals"></a><span data-ttu-id="b16bf-103">Serviceintervall</span><span class="sxs-lookup"><span data-stu-id="b16bf-103">Service intervals</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b16bf-104">Serviceavtalsintervallet anger den frekvens med vilken serviceorderrader skapas för serviceavtalsrader när du skapar serviceorder automatiskt.</span><span class="sxs-lookup"><span data-stu-id="b16bf-104">The service agreement interval indicates the frequency with which service order lines are created for service agreement lines when you create service orders automatically.</span></span>

<span data-ttu-id="b16bf-105">När du skapar serviceorder automatiskt, skapas serviceorderrader i enlighet med det intervall du har angett för serviceavtalsraden från avtalsradens startdatum.</span><span class="sxs-lookup"><span data-stu-id="b16bf-105">When you create service orders automatically, service order lines are created according to the interval that you have specified for the service agreement line from the start date of the agreement line.</span></span>

<span data-ttu-id="b16bf-106">Om fältet för **intervall** på en serviceavtalsrad på sidan **serviceavtal** är blank, förekommer raden en gång och den används inte för att skapa serviceorder vid flera tillfällen.</span><span class="sxs-lookup"><span data-stu-id="b16bf-106">If the **Interval** field of a service agreement line in the **Service agreements** page is blank, the line is a one-time event, and it is not used to create service orders repeatedly.</span></span>

## <a name="example"></a><span data-ttu-id="b16bf-107">Exempel</span><span class="sxs-lookup"><span data-stu-id="b16bf-107">Example</span></span>

<span data-ttu-id="b16bf-108">Det här exemplet illustrerar hur ett serviceintervall påverkar serviceavtalsrader och serviceorderrader på en serviceorder.</span><span class="sxs-lookup"><span data-stu-id="b16bf-108">This example illustrates how a service interval will affect service agreement lines and service order lines on a service order.</span></span>

### <a name="create-a-service-agreement"></a><span data-ttu-id="b16bf-109">Skapa ett serviceavtal</span><span class="sxs-lookup"><span data-stu-id="b16bf-109">Create a service agreement</span></span>

<span data-ttu-id="b16bf-110">Först skapar du ett serviceavtal och anger **med serviceavtal** för alternativet **kombinera serviceorder**.</span><span class="sxs-lookup"><span data-stu-id="b16bf-110">First, you create a service agreement and set the **Combine service orders** option to **By service agreement**.</span></span>

1. <span data-ttu-id="b16bf-111">Klicka på **Serviceavtal**</span><span class="sxs-lookup"><span data-stu-id="b16bf-111">Click **Service agreements**</span></span>
2. <span data-ttu-id="b16bf-112">För att skapa ett nytt serviceavtal använd **åtgärdsfönstret**på fliken **serviceavtal** och klicka på **serviceavtal** i gruppen för **nytt**.</span><span class="sxs-lookup"><span data-stu-id="b16bf-112">On the **Action Pane**, on the **Service agreement** tab, in the **New** group, click **Service agreement** to create a new service agreement.</span></span>
3. <span data-ttu-id="b16bf-113">Ange en beskrivning, välj ett projekt i fältet **projekt-ID** och ange ett datum i fältet **startdatum**.</span><span class="sxs-lookup"><span data-stu-id="b16bf-113">Enter a description, select a project in the **Project ID** field, and enter a date in the **Start date** field.</span></span>
4. <span data-ttu-id="b16bf-114">I fältet **kombinera serviceorder** väljer du **med serviceavtal**.</span><span class="sxs-lookup"><span data-stu-id="b16bf-114">In the **Combine service orders** field, select **By service agreement**.</span></span>

<span data-ttu-id="b16bf-115">Nu har du skapat följande serviceavtal:</span><span class="sxs-lookup"><span data-stu-id="b16bf-115">You have now created the following service agreement:</span></span>

| <span data-ttu-id="b16bf-116">Project</span><span class="sxs-lookup"><span data-stu-id="b16bf-116">Project</span></span>      | <span data-ttu-id="b16bf-117">Startdatum</span><span class="sxs-lookup"><span data-stu-id="b16bf-117">Start date</span></span>                                                                         |
|--------------|------------------------------------------------------------------------------------|
| <span data-ttu-id="b16bf-118">Ditt projekt</span><span class="sxs-lookup"><span data-stu-id="b16bf-118">Your project</span></span> | <span data-ttu-id="b16bf-119">Det angivna datumet för projektet.</span><span class="sxs-lookup"><span data-stu-id="b16bf-119">The date you specified for the project.</span></span> <span data-ttu-id="b16bf-120">I det här exemplet används dagens datum.</span><span class="sxs-lookup"><span data-stu-id="b16bf-120">In this example, the current date is used.</span></span> |

### <a name="create-a-service-agreement-line"></a><span data-ttu-id="b16bf-121">Skapa en serviceavtalsrad</span><span class="sxs-lookup"><span data-stu-id="b16bf-121">Create a service agreement line</span></span>

<span data-ttu-id="b16bf-122">Nu ska du skapa en serviceavtalsrad med transaktionstypen **timme**.</span><span class="sxs-lookup"><span data-stu-id="b16bf-122">Next, you create a service agreement line that has the transaction type **Hour**.</span></span>

<span data-ttu-id="b16bf-123">För att slutföra den här delen av exemplet måste du skapa ett serviceintervall på 10 dagar på sidan för **serviceintervall**.</span><span class="sxs-lookup"><span data-stu-id="b16bf-123">To complete this part of the example, you must create a service interval of 10 days in the **Service intervals** page.</span></span> 

1. <span data-ttu-id="b16bf-124">Markera det serviceavtal du just skapat.</span><span class="sxs-lookup"><span data-stu-id="b16bf-124">Select the service agreement that you just created.</span></span> 
2. <span data-ttu-id="b16bf-125">I snabbfliken för **rader** klickar du på knappen som **lägger till** för att skapa en ny rad i det nedre fönstret på sidan för **serviceavtal**.</span><span class="sxs-lookup"><span data-stu-id="b16bf-125">On the **Lines** FastTab, click the **Add** button to create a new line in the lower pane of the **Service agreements** page.</span></span>
3. <span data-ttu-id="b16bf-126">Välj **timme** i fältet för **transaktionstyp**.</span><span class="sxs-lookup"><span data-stu-id="b16bf-126">In the **Transaction type** field, select **Hour**.</span></span>
4. <span data-ttu-id="b16bf-127">I fältet för **medarbetare** välj den medarbetare som ska leverera tjänsten.</span><span class="sxs-lookup"><span data-stu-id="b16bf-127">In the **Worker** field, select the worker who will deliver the service.</span></span>
5. <span data-ttu-id="b16bf-128">I fältet för **serviceintervall** väljer du 10-dagarsintervall.</span><span class="sxs-lookup"><span data-stu-id="b16bf-128">In the **Service interval** field, select the 10 days interval.</span></span>

<span data-ttu-id="b16bf-129">Nu har du skapat en serviceavtalsrad med följande information:</span><span class="sxs-lookup"><span data-stu-id="b16bf-129">You have now created a service agreement line with the following information:</span></span>

| <span data-ttu-id="b16bf-130">transaktionstyp</span><span class="sxs-lookup"><span data-stu-id="b16bf-130">Transaction type</span></span> | <span data-ttu-id="b16bf-131">Startdatum</span><span class="sxs-lookup"><span data-stu-id="b16bf-131">Start date</span></span>                               | <span data-ttu-id="b16bf-132">Serviceintervall</span><span class="sxs-lookup"><span data-stu-id="b16bf-132">Service interval</span></span> |
|------------------|------------------------------------------|------------------|
| <span data-ttu-id="b16bf-133">Timme</span><span class="sxs-lookup"><span data-stu-id="b16bf-133">Hour</span></span>             | <span data-ttu-id="b16bf-134">Aktuellt datum.</span><span class="sxs-lookup"><span data-stu-id="b16bf-134">The current date.</span></span>                        | <span data-ttu-id="b16bf-135">Var 10:e dag</span><span class="sxs-lookup"><span data-stu-id="b16bf-135">Every 10 days</span></span>    |
| <span data-ttu-id="b16bf-136">Arbetare</span><span class="sxs-lookup"><span data-stu-id="b16bf-136">Worker</span></span>           | <span data-ttu-id="b16bf-137">Den medarbetare som ska utföra servicen.</span><span class="sxs-lookup"><span data-stu-id="b16bf-137">The worker who will perform the service.</span></span> |                  |

<span data-ttu-id="b16bf-138">Inget tidsfönster har angetts för denna rad.</span><span class="sxs-lookup"><span data-stu-id="b16bf-138">There is no time window specified for the line.</span></span> 

### <a name="create-planned-service-orders"></a><span data-ttu-id="b16bf-139">Skapa planerade serviceorder</span><span class="sxs-lookup"><span data-stu-id="b16bf-139">Create planned service orders</span></span>

<span data-ttu-id="b16bf-140">Nu kan du skapa planerade serviceorder och serviceorderrader för kommande månad.</span><span class="sxs-lookup"><span data-stu-id="b16bf-140">You can now create planned service orders and service order lines for the coming month.</span></span>

1. <span data-ttu-id="b16bf-141">På sidan för **serviceavtal** klickar du på **planerade serviceorder** på fliken **leverera** i **åtgärdsfönstret**.</span><span class="sxs-lookup"><span data-stu-id="b16bf-141">In the **Service agreements** page, on the **Action Pane**, on the **Deliver** tab, click **Planned service orders**.</span></span>
2. <span data-ttu-id="b16bf-142">På sidan för att **skapa serviceorder** anger du det aktuella datumet i fältet **från datum** och ett datum som infaller en månad från det aktuella datumet i fältet **till datum**.</span><span class="sxs-lookup"><span data-stu-id="b16bf-142">In the **Create service orders** page, enter the current date in the **From date** field and a date that is one month from the current date in the **To date** field.</span></span>
3. <span data-ttu-id="b16bf-143">Ställ skjutreglaget för **timme** på **Ja**.</span><span class="sxs-lookup"><span data-stu-id="b16bf-143">Set the **Hour** slider to **Yes**.</span></span> 
4. <span data-ttu-id="b16bf-144">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="b16bf-144">Click **OK**.</span></span>

<span data-ttu-id="b16bf-145">Eftersom det inte finns någon gruppering på serviceordern (definierad av alternativet **med serviceavtal** i fältet **kombinera serviceorder**), skapas en serviceorderrad per serviceorder.</span><span class="sxs-lookup"><span data-stu-id="b16bf-145">Because there is no grouping on the service order (defined by the **By service agreement** option in the **Combine service orders** field), one service order line is created per service order.</span></span>

### <a name="service-orders-created"></a><span data-ttu-id="b16bf-146">Skapade serviceorder</span><span class="sxs-lookup"><span data-stu-id="b16bf-146">Service orders created</span></span>

<span data-ttu-id="b16bf-147">Tre serviceorderrader har skapats inom den tidsram som du angav i dialogrutan för att **skapa serviceorder**.</span><span class="sxs-lookup"><span data-stu-id="b16bf-147">Three service order lines have been created within the time frame that you specified in the **Create service orders** dialog box.</span></span> <span data-ttu-id="b16bf-148">Du kan se serviceorderraderna på sidan för **serviceavtal** (**åtgärdsfönstret**\>**leverera**-fliken \>**visa** -knappen).</span><span class="sxs-lookup"><span data-stu-id="b16bf-148">You can view the service order lines in the **Service agreements** page (**Action Pane** \> **Deliver** tab \>**View** button).</span></span>

## <a name="related-topics"></a><span data-ttu-id="b16bf-149">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="b16bf-149">Related topics</span></span>

[<span data-ttu-id="b16bf-150">Ställ in serviceintervall</span><span class="sxs-lookup"><span data-stu-id="b16bf-150">Set up service intervals</span></span>](set-up-service-intervals.md)  

