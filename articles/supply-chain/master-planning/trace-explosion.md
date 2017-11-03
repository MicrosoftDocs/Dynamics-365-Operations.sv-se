---
title: "Använd spårning för nedbrytning"
description: "Det här avsnittet beskriver hur du kan använda spårning för att undersöka orsakerna till resultatet av en ordernedbrytning."
author: roxanadiaconu
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ReqTransExplosion
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 19231
ms.assetid: 9bc9bfbe-a7a9-437b-a947-826229b0585a
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: f3891688542ac6d4f9afce026808c65992a592d4
ms.contentlocale: sv-se
ms.lasthandoff: 11/03/2017

---

# <a name="use-tracing-for-explosion"></a><span data-ttu-id="fe146-103">Använd spårning för nedbrytning</span><span class="sxs-lookup"><span data-stu-id="fe146-103">Use tracing for explosion</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="fe146-104">Det här avsnittet beskriver hur du kan använda spårning för att undersöka orsakerna till resultatet av en ordernedbrytning.</span><span class="sxs-lookup"><span data-stu-id="fe146-104">This article explains how you can use tracing to explore the causes behind the outcome of an order explosion.</span></span>

<span data-ttu-id="fe146-105">Genom att aktivera spårning kan du visa information om vilka faktorer som bidrog till resultatet för nedbrytningen av en viss order.</span><span class="sxs-lookup"><span data-stu-id="fe146-105">By enabling tracing, you can view information about the factors that contributed to the outcome of the explosion of a particular order.</span></span> <span data-ttu-id="fe146-106">I följande exempel visas hur du kan använda spårningsinformationen:</span><span class="sxs-lookup"><span data-stu-id="fe146-106">The following examples show how you can use the tracing information:</span></span>

-   <span data-ttu-id="fe146-107">Visa relationer mellan åtgärderna för planerade order för att optimera leveranskedjan och lagerreservationerna.</span><span class="sxs-lookup"><span data-stu-id="fe146-107">View relations between the actions on planned orders to optimize the supply chain and inventory reservations.</span></span>
-   <span data-ttu-id="fe146-108">Visa relationer för order som redan har godkänts.</span><span class="sxs-lookup"><span data-stu-id="fe146-108">View relations to orders that are already approved.</span></span> <span data-ttu-id="fe146-109">Du kan fokusera på att automatiskt koppla härledda behov och sedan prioritera order mer exakt.</span><span class="sxs-lookup"><span data-stu-id="fe146-109">You can focus on automatically firming derived requirements and then prioritize orders more accurately.</span></span>
-   <span data-ttu-id="fe146-110">Simulera planläggningsresultat för att bestämma om planläggningsparametrarna är optimala.</span><span class="sxs-lookup"><span data-stu-id="fe146-110">Simulate planning results to determine whether the planning parameters are optimal.</span></span>
-   <span data-ttu-id="fe146-111">Identifiera hur information, till exempel produktionsdatum, kvantiteter och prioritet för en order bestämts.</span><span class="sxs-lookup"><span data-stu-id="fe146-111">Identify how information such as production dates, quantities, and priorities for an order were determined.</span></span>

<span data-ttu-id="fe146-112">Du kan visa information om leveransplaner och åtgärder för en vald order.</span><span class="sxs-lookup"><span data-stu-id="fe146-112">You can view details about futures and actions for a selected order.</span></span> <span data-ttu-id="fe146-113">På sidan **Nedbrytning** finns spårningsinformation på fliken **Förklaring** i det övre fönstret.</span><span class="sxs-lookup"><span data-stu-id="fe146-113">On the **Explosion** page, tracing information is available on the **Explanation** tab in the upper pane.</span></span> <span data-ttu-id="fe146-114">Spårning uppstår när du bryter ned en order.</span><span class="sxs-lookup"><span data-stu-id="fe146-114">Tracing occurs when you explode an order.</span></span> <span data-ttu-id="fe146-115">Om du vill börja spåra för ordern klickar du på **Uppdatera** och markerar kryssrutan **Aktivera spårning**.</span><span class="sxs-lookup"><span data-stu-id="fe146-115">To start tracing for the order, click **Update**, and then select the **Enable trace** check box.</span></span> <span data-ttu-id="fe146-116">Du kan använda fältet **Sök text** för att söka i loggen efter specifik information.</span><span class="sxs-lookup"><span data-stu-id="fe146-116">You can use the **Find text** field to search the log for specific information.</span></span> <span data-ttu-id="fe146-117">Sökresultatet markeras i trädet.</span><span class="sxs-lookup"><span data-stu-id="fe146-117">Search results are highlighted in the tree.</span></span>

<a name="see-also"></a><span data-ttu-id="fe146-118">Se även</span><span class="sxs-lookup"><span data-stu-id="fe146-118">See also</span></span>
--------

[<span data-ttu-id="fe146-119">Huvudplaner</span><span class="sxs-lookup"><span data-stu-id="fe146-119">Master plans</span></span>](master-plans.md)




