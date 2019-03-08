---
title: Skapa serviceorder automatiskt
description: Du kan skapa serviceorder som baseras på ett serviceavtal för den giltiga perioden av serviceavtalet.
author: ShylaThompson
manager: AnnBe
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMAServiceOrderTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: ShylaThompson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0189a9f99ffbb6ed2387211ba9e3b9f3bcdb3b52
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2019
ms.locfileid: "331194"
---
# <a name="automatically-create-service-orders"></a><span data-ttu-id="aa68c-103">Skapa serviceorder automatiskt</span><span class="sxs-lookup"><span data-stu-id="aa68c-103">Automatically create service orders</span></span> 

[!include [banner](../includes/banner.md)]


<span data-ttu-id="aa68c-104">Du kan skapa serviceorder som baseras på ett serviceavtal för den giltiga perioden av serviceavtalet.</span><span class="sxs-lookup"><span data-stu-id="aa68c-104">You can generate service orders that are based on a service agreement for the valid period of the service agreement.</span></span>

<span data-ttu-id="aa68c-105">De serviceorder som du skapar från ett serviceavtal kopplas till serviceavtalet.</span><span class="sxs-lookup"><span data-stu-id="aa68c-105">The service orders that you generate from a service agreement are all attached to the service agreement.</span></span>

<span data-ttu-id="aa68c-106">Serviceorder skapas automatiskt utifrån följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="aa68c-106">Service orders are generated automatically from the following settings:</span></span>

  - <span data-ttu-id="aa68c-107">Det serviceavtalsintervall som har ställts in på serviceavtalsraderna.</span><span class="sxs-lookup"><span data-stu-id="aa68c-107">The service agreement interval that is set up in the service agreement lines.</span></span> <span data-ttu-id="aa68c-108">Serviceavtalsintervallet anger med vilken frekvens serviceorderrader ska skapas.</span><span class="sxs-lookup"><span data-stu-id="aa68c-108">The service agreement interval indicates the frequency that service-order lines are created.</span></span> <span data-ttu-id="aa68c-109">Mer information om serviceintervall finns i [Serviceintervall](service-intervals.md).</span><span class="sxs-lookup"><span data-stu-id="aa68c-109">For more information, see [Service intervals](service-intervals.md).</span></span>

  - <span data-ttu-id="aa68c-110">Den period du anger för att definiera serviceperioden i fälten **Från datum** och **Till datum** i formuläret **Skapa serviceorder**.</span><span class="sxs-lookup"><span data-stu-id="aa68c-110">The period that you specify to define the service period in the **From date** and **To date** fields in the **Create service orders** form.</span></span> <span data-ttu-id="aa68c-111">Mer information finns i [Skapa serviceorder automatiskt](create-service-orders-automatically.md).</span><span class="sxs-lookup"><span data-stu-id="aa68c-111">For more information, see [Create service orders automatically](create-service-orders-automatically.md).</span></span>

  - <span data-ttu-id="aa68c-112">Alternativet **kombinera serviceorder** i serviceavtalshuvudet.</span><span class="sxs-lookup"><span data-stu-id="aa68c-112">The **Combine service orders** option on the service agreement header.</span></span> <span data-ttu-id="aa68c-113">Alternativet anger om de serviceorderrader som skapas från ett serviceavtal ska kombinera serviceorder efter medarbetare, serviceuppgift, serviceobjekt eller serviceavtal.</span><span class="sxs-lookup"><span data-stu-id="aa68c-113">This option defines whether service order lines generated from a service agreement, combines service orders according to employee, service task, service object, or service agreement.</span></span> <span data-ttu-id="aa68c-114">Mer information finns i [kombinera serviceorder](combine-service-orders.md).</span><span class="sxs-lookup"><span data-stu-id="aa68c-114">For more information, see [Combine service orders](combine-service-orders.md).</span></span>

  - <span data-ttu-id="aa68c-115">Alternativet **Tidsfönster** på serviceavtalsraden.</span><span class="sxs-lookup"><span data-stu-id="aa68c-115">The **Time window** option on the service agreement line.</span></span> <span data-ttu-id="aa68c-116">Tidsfönstret anger hur långt en serviceorderrad kan utsträckas i tiden i relation till radens beräknade datum.</span><span class="sxs-lookup"><span data-stu-id="aa68c-116">The time window defines how far a service order line can move with regard to its calculated date.</span></span> <span data-ttu-id="aa68c-117">Mer information finns i [tidsfönster](time-windows.md).</span><span class="sxs-lookup"><span data-stu-id="aa68c-117">For more information, see [Time windows](time-windows.md).</span></span>


> [!NOTE]
> <P><span data-ttu-id="aa68c-118">Om den dag som har angetts för en serviceorder inte är öppen i den kalender som du har valt i formuläret <STRONG>Servicehanteringsparametrar</STRONG> visas ett meddelande om att det finns en kalenderkonflikt.</span><span class="sxs-lookup"><span data-stu-id="aa68c-118">If the day that is specified for a service order is not open in the calendar that you have selected in the <STRONG>Service management parameters</STRONG> form, a message will indicate that there is a calendar conflict.</span></span> <span data-ttu-id="aa68c-119">Du kan ignorera meddelandet och serviceordern skapas även om dagen är stängd i kalendern.</span><span class="sxs-lookup"><span data-stu-id="aa68c-119">You can safely ignore the message; the service order will be created, even though the day is closed on the calendar.</span></span></P>

## <a name="example-1"></a><span data-ttu-id="aa68c-120">Exempel 1</span><span class="sxs-lookup"><span data-stu-id="aa68c-120">Example 1</span></span>

<span data-ttu-id="aa68c-121">Serviceavtalet varar från 1 januari 2012 till 31 december 2012.</span><span class="sxs-lookup"><span data-stu-id="aa68c-121">The service agreement lasts from January 1, 2012 until December 31, 2012.</span></span> <span data-ttu-id="aa68c-122">Om den serviceperiod som du anger i formuläret **skapa serviceorder** är från 1 november 2012 fram till den 1 februari 2013 skapas serviceorder från 1 november 2012 till 31 december 2012.</span><span class="sxs-lookup"><span data-stu-id="aa68c-122">If the service period that you specify in the **Create service orders** form is from November 1, 2012 until February 1, 2013, service orders are created from November 1, 2012 until December 31, 2012.</span></span>

## <a name="example-2"></a><span data-ttu-id="aa68c-123">Exempel 2</span><span class="sxs-lookup"><span data-stu-id="aa68c-123">Example 2</span></span>

<span data-ttu-id="aa68c-124">Serviceavtalet varar från 1 januari 2012 till 31 december 2012.</span><span class="sxs-lookup"><span data-stu-id="aa68c-124">The service agreement lasts from January 1, 2012 until December 31, 2012.</span></span> <span data-ttu-id="aa68c-125">Det finns två serviceavtalsrader kopplade till serviceavtalet.</span><span class="sxs-lookup"><span data-stu-id="aa68c-125">Two service agreement lines are attached to the service agreement.</span></span> <span data-ttu-id="aa68c-126">Första serviceavtalsraden har 2 januari 2012 som startdatum och 1 mars 2012 som slutdatum.</span><span class="sxs-lookup"><span data-stu-id="aa68c-126">The first service agreement line has a starting date on January 2, 2012 and an ending date on March 1, 2012.</span></span> <span data-ttu-id="aa68c-127">Den andra serviceavtalsraden har 1 april 2012 som startdatum och 31 december 2012 som slutdatum.</span><span class="sxs-lookup"><span data-stu-id="aa68c-127">The second service agreement line has a starting date on April 1, 2012 and an ending date on December 31, 2012.</span></span> <span data-ttu-id="aa68c-128">Du kan ange en period i formuläret **skapa serviceorder** från 1 oktober 2012 till 31 December 2012.</span><span class="sxs-lookup"><span data-stu-id="aa68c-128">You specify a period in the **Create service orders** form that is from October 1, 2012 until December 31, 2012.</span></span> <span data-ttu-id="aa68c-129">Detta innebär att serviceorder bara skapas för den andra serviceavtalsraden, eftersom start- och slutdatumen för den första raden ligger före den period som du har angett för serviceordern.</span><span class="sxs-lookup"><span data-stu-id="aa68c-129">Therefore, service orders are generated only for the second agreement line, because the starting date and ending date of the first agreement line are before the period that you specified for the service order.</span></span>

  


