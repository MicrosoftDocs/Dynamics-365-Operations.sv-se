---
title: Uppskatta en produktionsorder
description: "Du kan köra den här proceduren med demonstrationsdataföretaget USMF eller använda dina egna data."
author: johanhoffmann
manager: AnnBe
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: dadf0e87eac8522f61bb094c146e37f46a21fc09
ms.openlocfilehash: 862281adac67757e1ce0e9ddd1e96483363abb9a
ms.contentlocale: sv-se
ms.lasthandoff: 02/06/2018

---
# <a name="estimate-a-production-order"></a><span data-ttu-id="a07c6-103">Uppskatta en produktionsorder</span><span class="sxs-lookup"><span data-stu-id="a07c6-103">Estimate a production order</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="a07c6-104">Du kan köra den här proceduren med demonstrationsdataföretaget USMF eller använda dina egna data.</span><span class="sxs-lookup"><span data-stu-id="a07c6-104">You can run this procedure by using the USMF demo data company or your own data set.</span></span> <span data-ttu-id="a07c6-105">I båda fall måste du ha en öppen produktionsorder som har statusen Skapad.</span><span class="sxs-lookup"><span data-stu-id="a07c6-105">In both cases, you need to have an open production order that has the Created status.</span></span> <span data-ttu-id="a07c6-106">Detta är den andra proceduren av sju som förklarar produktionsorderns livscykel.</span><span class="sxs-lookup"><span data-stu-id="a07c6-106">This is the second procedure out of seven which explains the production order lifecycle.</span></span>


## <a name="estimate-a-production-order"></a><span data-ttu-id="a07c6-107">Uppskatta en produktionsorder</span><span class="sxs-lookup"><span data-stu-id="a07c6-107">Estimate a production order</span></span>
1. <span data-ttu-id="a07c6-108">Gå till Produktionskontroll > Produktionsorder > Alla produktionsorder.</span><span class="sxs-lookup"><span data-stu-id="a07c6-108">Go to Production control > Production orders > All production orders.</span></span>
2. <span data-ttu-id="a07c6-109">Markera en order som har statusen Skapad i rutnätet.</span><span class="sxs-lookup"><span data-stu-id="a07c6-109">Select an order that has the Created status in the grid.</span></span>
3. <span data-ttu-id="a07c6-110">Klicka på Produktionsorder i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="a07c6-110">On the Action Pane, click Production order.</span></span>
4. <span data-ttu-id="a07c6-111">Klicka på Uppskattning.</span><span class="sxs-lookup"><span data-stu-id="a07c6-111">Click Estimate.</span></span>
    * <span data-ttu-id="a07c6-112">I det här steget beräknas de uppskattade kostnaderna för en enskild produktionsorder.</span><span class="sxs-lookup"><span data-stu-id="a07c6-112">In this step, the estimated costs of a single production order is calculated.</span></span>   
5. <span data-ttu-id="a07c6-113">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="a07c6-113">Click OK.</span></span>

## <a name="view-the-calculation-details"></a><span data-ttu-id="a07c6-114">Visa beräkningsuppgifterna</span><span class="sxs-lookup"><span data-stu-id="a07c6-114">View the calculation details</span></span>
1. <span data-ttu-id="a07c6-115">Klicka på Hantera kostnader i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="a07c6-115">On the Action Pane, click Manage costs.</span></span>
2. <span data-ttu-id="a07c6-116">Klicka på Visa beräkningsuppgifter.</span><span class="sxs-lookup"><span data-stu-id="a07c6-116">Click View calculation details.</span></span>
    * <span data-ttu-id="a07c6-117">Den här sidan visar kostnadsuppdelningen.</span><span class="sxs-lookup"><span data-stu-id="a07c6-117">This page displays the cost breakdown.</span></span> <span data-ttu-id="a07c6-118">Du kan till exempel visa den totala självkostnaden per enhet för den färdiga produkten på den första raden.</span><span class="sxs-lookup"><span data-stu-id="a07c6-118">For example, you can view the total cost price per unit for the finished product in the first row.</span></span> <span data-ttu-id="a07c6-119">De efterföljande raderna innehåller kostnader i enlighet med strukturlistan, produktionsflödet och de indirekta kostnaderna.</span><span class="sxs-lookup"><span data-stu-id="a07c6-119">The subsequent rows contain costs according to the bill of materials, production route, and indirect costs.</span></span>  

