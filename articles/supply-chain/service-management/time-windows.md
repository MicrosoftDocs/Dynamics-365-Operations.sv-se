---
title: Tidsfönster
description: Du kan använda tidsfönster för att optimera planeringen av serviceorderraderna.
author: ShylaThompson
manager: tfehr
ms.date: 02/20/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMATimeAgreement
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d79e3d3756b8dc402d6f293437209b2e108be38e
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "4437828"
---
# <a name="time-windows"></a><span data-ttu-id="2e3d4-103">Tidsfönster</span><span class="sxs-lookup"><span data-stu-id="2e3d4-103">Time windows</span></span>  

[!include [banner](../includes/banner.md)]

<span data-ttu-id="2e3d4-104">Du kan använda tidsfönster för att optimera planeringen av serviceorderraderna.</span><span class="sxs-lookup"><span data-stu-id="2e3d4-104">You can use time windows to optimize the scheduling of service order lines.</span></span> <span data-ttu-id="2e3d4-105">Du kan ställa in systemet så att serviceorder skapas automatiskt.</span><span class="sxs-lookup"><span data-stu-id="2e3d4-105">You can set up the system so that it automatically creates service orders.</span></span> <span data-ttu-id="2e3d4-106">Du kan ansluta så många serviceorderrader som möjligt till så få serviceorder som möjligt utifrån de kriterier som anges av ett tidsfönster.</span><span class="sxs-lookup"><span data-stu-id="2e3d4-106">Based on the criteria specified by a time window, you can connect as many service order lines as possible to as few service orders as possible.</span></span>

<span data-ttu-id="2e3d4-107">Tidsfönstret specificerar hur långt en serviceorderrad kan flyttas från dess beräkningsdatum.</span><span class="sxs-lookup"><span data-stu-id="2e3d4-107">Time windows specify how far a service order line can move from its calculated date.</span></span> <span data-ttu-id="2e3d4-108">Det beräknade datumet är det datum när serviceorderraden har schemalagts.</span><span class="sxs-lookup"><span data-stu-id="2e3d4-108">The calculated date is the date when the service order line was scheduled to occur.</span></span> <span data-ttu-id="2e3d4-109">Datumet baseras på dess intervallinställning och den serviceperiod som du har definierat på sidan för **skapa serviceorder**.</span><span class="sxs-lookup"><span data-stu-id="2e3d4-109">The date is based on its interval setting and the service period that you defined in the **Create service orders** page.</span></span> <span data-ttu-id="2e3d4-110">Du definierar ett tidsfönster med hjälp av värdena i tabellen som följer.</span><span class="sxs-lookup"><span data-stu-id="2e3d4-110">You define a time window by using the values in the following table.</span></span>

| <span data-ttu-id="2e3d4-111">Metod</span><span class="sxs-lookup"><span data-stu-id="2e3d4-111">Method</span></span> | <span data-ttu-id="2e3d4-112">beskrivning</span><span class="sxs-lookup"><span data-stu-id="2e3d4-112">Description</span></span>                                                                                                                                                                                                                                                                                           |
|--------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="2e3d4-113">Vecka</span><span class="sxs-lookup"><span data-stu-id="2e3d4-113">Week</span></span>   | <span data-ttu-id="2e3d4-114">Det datum då serviceorderraden kan flyttas till en annan öppen dag i samma vecka som det ursprungliga beräkningsdatumet.</span><span class="sxs-lookup"><span data-stu-id="2e3d4-114">The date that the service order line can be moved to any open day in the same week as the initial calculated date.</span></span>                                                                                                                                                                                    |
| <span data-ttu-id="2e3d4-115">Månad</span><span class="sxs-lookup"><span data-stu-id="2e3d4-115">Month</span></span>  | <span data-ttu-id="2e3d4-116">Det datum då serviceorderraden kan flyttas till en annan öppen dag i samma månad som det ursprungliga beräkningsdatumet.</span><span class="sxs-lookup"><span data-stu-id="2e3d4-116">The date that the service order line can be moved to any open day in the same month as the initial calculated date.</span></span> <span data-ttu-id="2e3d4-117">Som exempel är 15 february 2017 beräkningsdatumet för en serviceorderrad.</span><span class="sxs-lookup"><span data-stu-id="2e3d4-117">For example, the calculated date for a service order line is February 15, 2017.</span></span> <span data-ttu-id="2e3d4-118">Serviceorderraden kan schemaläggas för en veckodag mellan den 1 februari och den 28 februari 2017.</span><span class="sxs-lookup"><span data-stu-id="2e3d4-118">The service order line can be scheduled for any weekday between February 1 and February 28, 2017.</span></span> |
| <span data-ttu-id="2e3d4-119">Manuell</span><span class="sxs-lookup"><span data-stu-id="2e3d4-119">Manual</span></span> | <span data-ttu-id="2e3d4-120">Du definierar det maximala antalet dagar före och efter det ursprungliga beräkningsdatumet som serviceorderraden kan flyttas till.</span><span class="sxs-lookup"><span data-stu-id="2e3d4-120">You define the maximum number of days before or after the initial calculated date that the service order line can be moved.</span></span>                                                                                                                                                                           |

<span data-ttu-id="2e3d4-121">Om inget tidsfönster har angetts för en serviceavtalsrad måste serviceorderraden som hämtas från serviceavtalet köras exakt på det datum då det ursprungligen planerades.</span><span class="sxs-lookup"><span data-stu-id="2e3d4-121">If you do not specify a time window for a service agreement line, the service order line that is derived from the service agreement must be on the exact date for which it was originally scheduled.</span></span>

## <a name="related-topics"></a><span data-ttu-id="2e3d4-122">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="2e3d4-122">Related topics</span></span>

[<span data-ttu-id="2e3d4-123">Skapa tidsfönster</span><span class="sxs-lookup"><span data-stu-id="2e3d4-123">Create time windows</span></span>](create-time-windows.md)

