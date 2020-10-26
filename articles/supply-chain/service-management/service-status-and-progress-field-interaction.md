---
title: Samband mellan servicestatus och förloppsfält
description: I formuläret Serviceorder återspeglar fältet Förlopp i serviceorderns huvud statusvärdet för hela serviceordern, och Status anger statusvärdet för enskilda serviceorderrader.
author: ShylaThompson
manager: tfehr
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMAServiceOrderTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a94f2df6a4ddb71a29ff951dfe38618ac7762783
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/10/2020
ms.locfileid: "3975498"
---
# <a name="service-status-and-progress-field-interaction"></a><span data-ttu-id="c5c58-103">Samband mellan servicestatus och förloppsfält</span><span class="sxs-lookup"><span data-stu-id="c5c58-103">Service status and progress field interaction</span></span> 

[!include [banner](../includes/banner.md)]


<span data-ttu-id="c5c58-104">I formuläret **Serviceorder**, fältet **Förlopp** i serviceorderns huvud statusvärdet för hela serviceordern, och **Status** anger statusvärdet för enskilda serviceorderrader.</span><span class="sxs-lookup"><span data-stu-id="c5c58-104">In the **Service orders** form, the **Progress** field on the service order header reflects the status of the whole service order, and the **Status** reports the status of individual service order lines.</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="c5c58-105">Förlopp</span><span class="sxs-lookup"><span data-stu-id="c5c58-105">Progress</span></span></p></th>
<th><p><span data-ttu-id="c5c58-106">Status för rad 1</span><span class="sxs-lookup"><span data-stu-id="c5c58-106">Line 1 Status</span></span></p></th>
<th><p><span data-ttu-id="c5c58-107">Status för rad 2</span><span class="sxs-lookup"><span data-stu-id="c5c58-107">Line 2 Status</span></span></p></th>
<th><p><span data-ttu-id="c5c58-108">Status för rad 3</span><span class="sxs-lookup"><span data-stu-id="c5c58-108">Line 3 Status</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c5c58-109"><strong>Pågår</strong></span><span class="sxs-lookup"><span data-stu-id="c5c58-109"><strong>In process</strong></span></span></p></td>
<td><p><span data-ttu-id="c5c58-110"><strong>Skapat</strong></span><span class="sxs-lookup"><span data-stu-id="c5c58-110"><strong>Created</strong></span></span></p></td>
<td><p><span data-ttu-id="c5c58-111"><strong>Skapat</strong></span><span class="sxs-lookup"><span data-stu-id="c5c58-111"><strong>Created</strong></span></span></p></td>
<td><p><span data-ttu-id="c5c58-112"><strong>Skapat</strong></span><span class="sxs-lookup"><span data-stu-id="c5c58-112"><strong>Created</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c5c58-113"><strong>Pågår</strong></span><span class="sxs-lookup"><span data-stu-id="c5c58-113"><strong>In process</strong></span></span></p></td>
<td><p><span data-ttu-id="c5c58-114"><strong>Annullerad</strong></span><span class="sxs-lookup"><span data-stu-id="c5c58-114"><strong>Canceled</strong></span></span></p></td>
<td><p><span data-ttu-id="c5c58-115"><strong>Skapat</strong></span><span class="sxs-lookup"><span data-stu-id="c5c58-115"><strong>Created</strong></span></span></p></td>
<td><p><span data-ttu-id="c5c58-116"><strong>Skapat</strong></span><span class="sxs-lookup"><span data-stu-id="c5c58-116"><strong>Created</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c5c58-117"><strong>Pågår</strong></span><span class="sxs-lookup"><span data-stu-id="c5c58-117"><strong>In process</strong></span></span></p></td>
<td><p><span data-ttu-id="c5c58-118"><strong>Skapat</strong></span><span class="sxs-lookup"><span data-stu-id="c5c58-118"><strong>Created</strong></span></span></p></td>
<td><p><span data-ttu-id="c5c58-119"><strong>Annullerad</strong></span><span class="sxs-lookup"><span data-stu-id="c5c58-119"><strong>Canceled</strong></span></span></p></td>
<td><p><span data-ttu-id="c5c58-120"><strong>Bokförd</strong></span><span class="sxs-lookup"><span data-stu-id="c5c58-120"><strong>Posted</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c5c58-121"><strong>Annullerad</strong></span><span class="sxs-lookup"><span data-stu-id="c5c58-121"><strong>Canceled</strong></span></span></p></td>
<td><p><span data-ttu-id="c5c58-122"><strong>Annullerad</strong></span><span class="sxs-lookup"><span data-stu-id="c5c58-122"><strong>Canceled</strong></span></span></p></td>
<td><p><span data-ttu-id="c5c58-123"><strong>Annullerad</strong></span><span class="sxs-lookup"><span data-stu-id="c5c58-123"><strong>Canceled</strong></span></span></p></td>
<td><p><span data-ttu-id="c5c58-124"><strong>Annullerad</strong></span><span class="sxs-lookup"><span data-stu-id="c5c58-124"><strong>Canceled</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c5c58-125"><strong>Bokförd</strong></span><span class="sxs-lookup"><span data-stu-id="c5c58-125"><strong>Posted</strong></span></span></p></td>
<td><p><span data-ttu-id="c5c58-126"><strong>Bokförd</strong></span><span class="sxs-lookup"><span data-stu-id="c5c58-126"><strong>Posted</strong></span></span></p></td>
<td><p><span data-ttu-id="c5c58-127"><strong>Bokförd</strong></span><span class="sxs-lookup"><span data-stu-id="c5c58-127"><strong>Posted</strong></span></span></p></td>
<td><p><span data-ttu-id="c5c58-128"><strong>Bokförd</strong></span><span class="sxs-lookup"><span data-stu-id="c5c58-128"><strong>Posted</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c5c58-129"><strong>Bokförd</strong></span><span class="sxs-lookup"><span data-stu-id="c5c58-129"><strong>Posted</strong></span></span></p></td>
<td><p><span data-ttu-id="c5c58-130"><strong>Bokförd</strong></span><span class="sxs-lookup"><span data-stu-id="c5c58-130"><strong>Posted</strong></span></span></p></td>
<td><p><span data-ttu-id="c5c58-131"><strong>Annullerad</strong></span><span class="sxs-lookup"><span data-stu-id="c5c58-131"><strong>Canceled</strong></span></span></p></td>
<td><p><span data-ttu-id="c5c58-132"><strong>Annullerad</strong></span><span class="sxs-lookup"><span data-stu-id="c5c58-132"><strong>Canceled</strong></span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="c5c58-133">En serviceorders förlopp är pågående om alla rader har statusvärdet **Skapad**; och det pågår fortfarande om några av raderna har statusvärdet **Avbruten** eller **Bokförd**.</span><span class="sxs-lookup"><span data-stu-id="c5c58-133">The progress of a service order is in process if all lines have the status **Created**; it is still in process if some of the lines have a status of **Canceled** or **Posted**.</span></span>

<span data-ttu-id="c5c58-134">Om alla rader på en serviceorder markeras som **Bokförd**, är förloppet på statusordern **Bokförd**.</span><span class="sxs-lookup"><span data-stu-id="c5c58-134">If all lines in a service order are marked as **Posted**, the progress of the status order is **Posted**.</span></span> <span data-ttu-id="c5c58-135">Om några rader är **Bokförd** och vissa är **Avbruten**, är förloppet fortfarande **Bokförd**.</span><span class="sxs-lookup"><span data-stu-id="c5c58-135">If some lines are **Posted** and some are **Canceled**, the progress is still **Posted**.</span></span>

  


