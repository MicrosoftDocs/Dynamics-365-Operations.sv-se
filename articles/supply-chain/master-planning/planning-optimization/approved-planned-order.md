---
title: Godkänn planerade order
description: Det här ämnet beskriver godkännande av planerade order som stöds i planeringsoptimering.
author: ChristianRytt
manager: tfehr
ms.date: 08/21/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2020-08-21
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: b7975088be898ccecceb1f7be009cecff107f6e6
ms.sourcegitcommit: cd339f48066b1d0fc740b513cb72ea19015acd16
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/02/2020
ms.locfileid: "3759698"
---
# <a name="approve-planned-orders"></a><span data-ttu-id="18126-103">Godkänn planerade order</span><span class="sxs-lookup"><span data-stu-id="18126-103">Approve planned orders</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="18126-104">Det här avsnittet innehåller information om hur du uppdaterar status för planerade order i planeringsoptimering.</span><span class="sxs-lookup"><span data-stu-id="18126-104">This topic provides information about how to update the status of planned orders in Planning Optimization.</span></span>

<span data-ttu-id="18126-105">Observera att godkännande av planerade order är ett valfritt steg, på vägen för att skapa en bekräftad order från en planerad order.</span><span class="sxs-lookup"><span data-stu-id="18126-105">Note that approval of planned orders is an optional step, on the way to create a firmed order from a planned order.</span></span> <span data-ttu-id="18126-106">Du rekommenderas att godkänna ändrade planerade order, annars ignoreras dessa ändringar och skrivs över vid nästa planeringskörning.</span><span class="sxs-lookup"><span data-stu-id="18126-106">It is recommended to approve modified planned orders, otherwise the edits will be ignored and overwritten by the next planning run.</span></span>

![Planerat orderflöde](media/approved-planned-orders-1.png)

<span data-ttu-id="18126-108">Fältet **Status** hjälper dig att spåra dina framsteg med följande värden:</span><span class="sxs-lookup"><span data-stu-id="18126-108">The **Status** field helps you tack your progress using the following values:</span></span>

- <span data-ttu-id="18126-109">**Obearbetad:** När huvudplaneringen genererar planerade order, har planerade order statusen *Obearbetad*.</span><span class="sxs-lookup"><span data-stu-id="18126-109">**Unprocessed:** When master planning generates planned orders, the planned orders have a status of *Unprocessed*.</span></span> <span data-ttu-id="18126-110">Planerade order med denna status raderas vid nästa planeringskörning.</span><span class="sxs-lookup"><span data-stu-id="18126-110">Planned orders with this status will be deleted during the next planning run.</span></span>
- <span data-ttu-id="18126-111">**Slutfört:** om du väljer att inte bekräfta en planerad order kan du ändra statusen till *slutförd* för att indikera att du har slutfört utvärderingen av den planerade ordern.</span><span class="sxs-lookup"><span data-stu-id="18126-111">**Completed:** If you decide not to firm a planned order, you can change the status to *Completed* to indicate that you completed evaluating this planned order.</span></span> <span data-ttu-id="18126-112">Observera att statusen *obearbetade* och *slutförd* behandlas på samma sätt i systemet.</span><span class="sxs-lookup"><span data-stu-id="18126-112">Note that a status of *Unprocessed* and *Completed* are treated the same by the system.</span></span>
- <span data-ttu-id="18126-113">**Godkänd:** om du vill fortsätta redigera eller planera att bekräfta en planerad order ändrar du statusvärdet till *godkänd* .</span><span class="sxs-lookup"><span data-stu-id="18126-113">**Approved:** If you want to keep edits or are planning to firm a planned order, change the status to *Approved*.</span></span> <span data-ttu-id="18126-114">Planerade order med status *godkänd* anses vara fasta och förväntad leverans av huvudplaneringen, så att de inte ändras eller tas bort under en senare huvudplaneringskörning.</span><span class="sxs-lookup"><span data-stu-id="18126-114">Planned orders with *Approved* status are considered as fixed and expected supply by master planning, so they are not modified or deleted during later master planning runs.</span></span> <span data-ttu-id="18126-115">För att uppnå detta kopierar planeringslogiken de *godkända* planerade orderna från den gamla planversionen till den nya planversionen under huvudplaneringen.</span><span class="sxs-lookup"><span data-stu-id="18126-115">To achieve this, the planning logic copies the *Approved* planned orders from the old plan version to the new plan version during master planning.</span></span> <span data-ttu-id="18126-116">Observera att *godkända* planerade order endast behandlas som leverans inom den specifika huvudplanen.</span><span class="sxs-lookup"><span data-stu-id="18126-116">Note that *Approved* planned orders are only considered supply within the specific master plan.</span></span>

<span data-ttu-id="18126-117">Du kan hantera planerade order från arbetsytan **Huvudplanering**, listan **Planerad order** eller listorna **Planerade produktionsorder**, **Planerade inköpsorder** och **Planerad överföring**.</span><span class="sxs-lookup"><span data-stu-id="18126-117">You can manage planned orders from the  **Master planning**  workspace, the  **Planned order**  list, or the  **Planned production orders**,  **Planned purchase orders**, and  **Planned transfer**  lists.</span></span>
