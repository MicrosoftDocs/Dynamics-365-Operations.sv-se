---
title: Uppskatta en produktionsorder
description: Du kan köra den här proceduren med demonstrationsdataföretaget USMF eller använda dina egna data.
author: johanhoffmann
manager: AnnBe
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f1e99d7c84171e4affe59fb896a7e93c2a328740
ms.sourcegitcommit: fcb27d6a46cd544feef34f6ec7607bdd46b0c12b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/18/2020
ms.locfileid: "3146777"
---
# <a name="estimate-a-production-order"></a><span data-ttu-id="75929-103">Uppskatta en produktionsorder</span><span class="sxs-lookup"><span data-stu-id="75929-103">Estimate a production order</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="75929-104">Du kan köra den här proceduren med demonstrationsdataföretaget USMF eller använda dina egna data.</span><span class="sxs-lookup"><span data-stu-id="75929-104">You can run this procedure by using the USMF demo data company or your own data set.</span></span> <span data-ttu-id="75929-105">I båda fall måste du ha en öppen produktionsorder som har statusen Skapad.</span><span class="sxs-lookup"><span data-stu-id="75929-105">In both cases, you need to have an open production order that has the Created status.</span></span> <span data-ttu-id="75929-106">Detta är den andra proceduren av sju som förklarar produktionsorderns livscykel.</span><span class="sxs-lookup"><span data-stu-id="75929-106">This is the second procedure out of seven which explains the production order lifecycle.</span></span>


## <a name="estimate-a-production-order"></a><span data-ttu-id="75929-107">Uppskatta en produktionsorder</span><span class="sxs-lookup"><span data-stu-id="75929-107">Estimate a production order</span></span>
1. <span data-ttu-id="75929-108">Gå till Produktionskontroll > Produktionsorder > Alla produktionsorder.</span><span class="sxs-lookup"><span data-stu-id="75929-108">Go to Production control > Production orders > All production orders.</span></span>
2. <span data-ttu-id="75929-109">Markera en order som har statusen Skapad i rutnätet.</span><span class="sxs-lookup"><span data-stu-id="75929-109">Select an order that has the Created status in the grid.</span></span>
3. <span data-ttu-id="75929-110">Klicka på Produktionsorder i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="75929-110">On the Action Pane, click Production order.</span></span>
4. <span data-ttu-id="75929-111">Klicka på Uppskattning.</span><span class="sxs-lookup"><span data-stu-id="75929-111">Click Estimate.</span></span>
    * <span data-ttu-id="75929-112">I det här steget beräknas de uppskattade kostnaderna för en enskild produktionsorder.</span><span class="sxs-lookup"><span data-stu-id="75929-112">In this step, the estimated costs of a single production order is calculated.</span></span>   
5. <span data-ttu-id="75929-113">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="75929-113">Click OK.</span></span>

## <a name="view-the-calculation-details"></a><span data-ttu-id="75929-114">Visa beräkningsuppgifterna</span><span class="sxs-lookup"><span data-stu-id="75929-114">View the calculation details</span></span>
1. <span data-ttu-id="75929-115">Klicka på Hantera kostnader i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="75929-115">On the Action Pane, click Manage costs.</span></span>
2. <span data-ttu-id="75929-116">Klicka på Visa beräkningsuppgifter.</span><span class="sxs-lookup"><span data-stu-id="75929-116">Click View calculation details.</span></span>
    * <span data-ttu-id="75929-117">Den här sidan visar kostnadsuppdelningen.</span><span class="sxs-lookup"><span data-stu-id="75929-117">This page displays the cost breakdown.</span></span> <span data-ttu-id="75929-118">Du kan till exempel visa den totala självkostnaden per enhet för den färdiga produkten på den första raden.</span><span class="sxs-lookup"><span data-stu-id="75929-118">For example, you can view the total cost price per unit for the finished product in the first row.</span></span> <span data-ttu-id="75929-119">De efterföljande raderna innehåller kostnader i enlighet med strukturlistan, produktionsflödet och de indirekta kostnaderna.</span><span class="sxs-lookup"><span data-stu-id="75929-119">The subsequent rows contain costs according to the bill of materials, production route, and indirect costs.</span></span>  
