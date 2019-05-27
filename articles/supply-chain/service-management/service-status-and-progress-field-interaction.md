---
title: Samband mellan servicestatus och förloppsfält
description: I formuläret Serviceorder återspeglar fältet Förlopp i serviceorderns huvud statusvärdet för hela serviceordern, och Status anger statusvärdet för enskilda serviceorderrader.
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
ms.openlocfilehash: 2dd7b5160149a38dd62535901c1225bf704f404d
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/15/2019
ms.locfileid: "1570796"
---
# <a name="service-status-and-progress-field-interaction"></a><span data-ttu-id="87baa-103">Samband mellan servicestatus och förloppsfält</span><span class="sxs-lookup"><span data-stu-id="87baa-103">Service status and progress field interaction</span></span> 

[!include [banner](../includes/banner.md)]


<span data-ttu-id="87baa-104">I formuläret **Serviceorder**, fältet **Förlopp** i serviceorderns huvud statusvärdet för hela serviceordern, och **Status** anger statusvärdet för enskilda serviceorderrader.</span><span class="sxs-lookup"><span data-stu-id="87baa-104">In the **Service orders** form, the **Progress** field on the service order header reflects the status of the whole service order, and the **Status** reports the status of individual service order lines.</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="87baa-105">Förlopp</span><span class="sxs-lookup"><span data-stu-id="87baa-105">Progress</span></span></p></th>
<th><p><span data-ttu-id="87baa-106">Status för rad 1</span><span class="sxs-lookup"><span data-stu-id="87baa-106">Line 1 Status</span></span></p></th>
<th><p><span data-ttu-id="87baa-107">Status för rad 2</span><span class="sxs-lookup"><span data-stu-id="87baa-107">Line 2 Status</span></span></p></th>
<th><p><span data-ttu-id="87baa-108">Status för rad 3</span><span class="sxs-lookup"><span data-stu-id="87baa-108">Line 3 Status</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="87baa-109"><strong>Pågår</strong></span><span class="sxs-lookup"><span data-stu-id="87baa-109"><strong>In process</strong></span></span></p></td>
<td><p><span data-ttu-id="87baa-110"><strong>Skapat</strong></span><span class="sxs-lookup"><span data-stu-id="87baa-110"><strong>Created</strong></span></span></p></td>
<td><p><span data-ttu-id="87baa-111"><strong>Skapat</strong></span><span class="sxs-lookup"><span data-stu-id="87baa-111"><strong>Created</strong></span></span></p></td>
<td><p><span data-ttu-id="87baa-112"><strong>Skapat</strong></span><span class="sxs-lookup"><span data-stu-id="87baa-112"><strong>Created</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="87baa-113"><strong>Pågår</strong></span><span class="sxs-lookup"><span data-stu-id="87baa-113"><strong>In process</strong></span></span></p></td>
<td><p><span data-ttu-id="87baa-114"><strong>Annullerad</strong></span><span class="sxs-lookup"><span data-stu-id="87baa-114"><strong>Canceled</strong></span></span></p></td>
<td><p><span data-ttu-id="87baa-115"><strong>Skapat</strong></span><span class="sxs-lookup"><span data-stu-id="87baa-115"><strong>Created</strong></span></span></p></td>
<td><p><span data-ttu-id="87baa-116"><strong>Skapat</strong></span><span class="sxs-lookup"><span data-stu-id="87baa-116"><strong>Created</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="87baa-117"><strong>Pågår</strong></span><span class="sxs-lookup"><span data-stu-id="87baa-117"><strong>In process</strong></span></span></p></td>
<td><p><span data-ttu-id="87baa-118"><strong>Skapat</strong></span><span class="sxs-lookup"><span data-stu-id="87baa-118"><strong>Created</strong></span></span></p></td>
<td><p><span data-ttu-id="87baa-119"><strong>Annullerad</strong></span><span class="sxs-lookup"><span data-stu-id="87baa-119"><strong>Canceled</strong></span></span></p></td>
<td><p><span data-ttu-id="87baa-120"><strong>Bokförd</strong></span><span class="sxs-lookup"><span data-stu-id="87baa-120"><strong>Posted</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="87baa-121"><strong>Annullerad</strong></span><span class="sxs-lookup"><span data-stu-id="87baa-121"><strong>Canceled</strong></span></span></p></td>
<td><p><span data-ttu-id="87baa-122"><strong>Annullerad</strong></span><span class="sxs-lookup"><span data-stu-id="87baa-122"><strong>Canceled</strong></span></span></p></td>
<td><p><span data-ttu-id="87baa-123"><strong>Annullerad</strong></span><span class="sxs-lookup"><span data-stu-id="87baa-123"><strong>Canceled</strong></span></span></p></td>
<td><p><span data-ttu-id="87baa-124"><strong>Annullerad</strong></span><span class="sxs-lookup"><span data-stu-id="87baa-124"><strong>Canceled</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="87baa-125"><strong>Bokförd</strong></span><span class="sxs-lookup"><span data-stu-id="87baa-125"><strong>Posted</strong></span></span></p></td>
<td><p><span data-ttu-id="87baa-126"><strong>Bokförd</strong></span><span class="sxs-lookup"><span data-stu-id="87baa-126"><strong>Posted</strong></span></span></p></td>
<td><p><span data-ttu-id="87baa-127"><strong>Bokförd</strong></span><span class="sxs-lookup"><span data-stu-id="87baa-127"><strong>Posted</strong></span></span></p></td>
<td><p><span data-ttu-id="87baa-128"><strong>Bokförd</strong></span><span class="sxs-lookup"><span data-stu-id="87baa-128"><strong>Posted</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="87baa-129"><strong>Bokförd</strong></span><span class="sxs-lookup"><span data-stu-id="87baa-129"><strong>Posted</strong></span></span></p></td>
<td><p><span data-ttu-id="87baa-130"><strong>Bokförd</strong></span><span class="sxs-lookup"><span data-stu-id="87baa-130"><strong>Posted</strong></span></span></p></td>
<td><p><span data-ttu-id="87baa-131"><strong>Annullerad</strong></span><span class="sxs-lookup"><span data-stu-id="87baa-131"><strong>Canceled</strong></span></span></p></td>
<td><p><span data-ttu-id="87baa-132"><strong>Annullerad</strong></span><span class="sxs-lookup"><span data-stu-id="87baa-132"><strong>Canceled</strong></span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="87baa-133">En serviceorders förlopp är pågående om alla rader har statusvärdet **Skapad**; och det pågår fortfarande om några av raderna har statusvärdet **Avbruten** eller **Bokförd**.</span><span class="sxs-lookup"><span data-stu-id="87baa-133">The progress of a service order is in process if all lines have the status **Created**; it is still in process if some of the lines have a status of **Canceled** or **Posted**.</span></span>

<span data-ttu-id="87baa-134">Om alla rader på en serviceorder markeras som **Bokförd**, är förloppet på statusordern **Bokförd**.</span><span class="sxs-lookup"><span data-stu-id="87baa-134">If all lines in a service order are marked as **Posted**, the progress of the status order is **Posted**.</span></span> <span data-ttu-id="87baa-135">Om några rader är **Bokförd** och vissa är **Avbruten**, är förloppet fortfarande **Bokförd**.</span><span class="sxs-lookup"><span data-stu-id="87baa-135">If some lines are **Posted** and some are **Canceled**, the progress is still **Posted**.</span></span>

  


