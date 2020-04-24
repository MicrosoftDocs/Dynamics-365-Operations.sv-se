---
title: Använd spårning för nedbrytning
description: Det här avsnittet beskriver hur du kan använda spårning för att undersöka orsakerna till resultatet av en ordernedbrytning.
author: roxanadiaconu
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqTransExplosion
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 19231
ms.assetid: 9bc9bfbe-a7a9-437b-a947-826229b0585a
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 046d4f5270869542d33023b9b9c927e89f5ad40b
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/02/2020
ms.locfileid: "3209523"
---
# <a name="use-tracing-for-explosion"></a><span data-ttu-id="7ac8b-103">Använd spårning för nedbrytning</span><span class="sxs-lookup"><span data-stu-id="7ac8b-103">Use tracing for explosion</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="7ac8b-104">Det här avsnittet beskriver hur du kan använda spårning för att undersöka orsakerna till resultatet av en ordernedbrytning.</span><span class="sxs-lookup"><span data-stu-id="7ac8b-104">This article explains how you can use tracing to explore the causes behind the outcome of an order explosion.</span></span>

<span data-ttu-id="7ac8b-105">Genom att aktivera spårning kan du visa information om vilka faktorer som bidrog till resultatet för nedbrytningen av en viss order.</span><span class="sxs-lookup"><span data-stu-id="7ac8b-105">By enabling tracing, you can view information about the factors that contributed to the outcome of the explosion of a particular order.</span></span> <span data-ttu-id="7ac8b-106">I följande exempel visas hur du kan använda spårningsinformationen:</span><span class="sxs-lookup"><span data-stu-id="7ac8b-106">The following examples show how you can use the tracing information:</span></span>

-   <span data-ttu-id="7ac8b-107">Visa relationer mellan åtgärderna för planerade order för att optimera leveranskedjan och lagerreservationerna.</span><span class="sxs-lookup"><span data-stu-id="7ac8b-107">View relations between the actions on planned orders to optimize the supply chain and inventory reservations.</span></span>
-   <span data-ttu-id="7ac8b-108">Visa relationer för order som redan har godkänts.</span><span class="sxs-lookup"><span data-stu-id="7ac8b-108">View relations to orders that are already approved.</span></span> <span data-ttu-id="7ac8b-109">Du kan fokusera på att automatiskt koppla härledda behov och sedan prioritera order mer exakt.</span><span class="sxs-lookup"><span data-stu-id="7ac8b-109">You can focus on automatically firming derived requirements and then prioritize orders more accurately.</span></span>
-   <span data-ttu-id="7ac8b-110">Simulera planläggningsresultat för att bestämma om planläggningsparametrarna är optimala.</span><span class="sxs-lookup"><span data-stu-id="7ac8b-110">Simulate planning results to determine whether the planning parameters are optimal.</span></span>
-   <span data-ttu-id="7ac8b-111">Identifiera hur information, till exempel produktionsdatum, kvantiteter och prioritet för en order bestämts.</span><span class="sxs-lookup"><span data-stu-id="7ac8b-111">Identify how information such as production dates, quantities, and priorities for an order were determined.</span></span>

<span data-ttu-id="7ac8b-112">Du kan visa information om leveransplaner och åtgärder för en vald order.</span><span class="sxs-lookup"><span data-stu-id="7ac8b-112">You can view details about futures and actions for a selected order.</span></span> <span data-ttu-id="7ac8b-113">På sidan **Nedbrytning** finns spårningsinformation på fliken **Förklaring** i det övre fönstret.</span><span class="sxs-lookup"><span data-stu-id="7ac8b-113">On the **Explosion** page, tracing information is available on the **Explanation** tab in the upper pane.</span></span> <span data-ttu-id="7ac8b-114">Spårning uppstår när du bryter ned en order.</span><span class="sxs-lookup"><span data-stu-id="7ac8b-114">Tracing occurs when you explode an order.</span></span> <span data-ttu-id="7ac8b-115">Om du vill börja spåra för ordern klickar du på **Uppdatera** och markerar kryssrutan **Aktivera spårning**.</span><span class="sxs-lookup"><span data-stu-id="7ac8b-115">To start tracing for the order, click **Update**, and then select the **Enable trace** check box.</span></span> <span data-ttu-id="7ac8b-116">Du kan använda fältet **Sök text** för att söka i loggen efter specifik information.</span><span class="sxs-lookup"><span data-stu-id="7ac8b-116">You can use the **Find text** field to search the log for specific information.</span></span> <span data-ttu-id="7ac8b-117">Sökresultatet markeras i trädet.</span><span class="sxs-lookup"><span data-stu-id="7ac8b-117">Search results are highlighted in the tree.</span></span>

<a name="additional-resources"></a><span data-ttu-id="7ac8b-118">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="7ac8b-118">Additional resources</span></span>
--------

[<span data-ttu-id="7ac8b-119">Huvudplaner – översikt</span><span class="sxs-lookup"><span data-stu-id="7ac8b-119">Master plans overview</span></span>](master-plans.md)



