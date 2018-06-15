---
title: "Samband mellan servicestatus och förloppsfält"
description: "I formuläret Serviceorder återspeglar fältet Förlopp i serviceorderns huvud statusvärdet för hela serviceordern, och Status anger statusvärdet för enskilda serviceorderrader."
author: YuyuScheller
manager: AnnBe
ms.date: 05/01/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SMAServiceOrderTable
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: YuyuScheller
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 51ef39266e8de00488954918568d00a297a9b50a
ms.contentlocale: sv-se
ms.lasthandoff: 05/08/2018

---


# <a name="service-status-and-progress-field-interaction"></a><span data-ttu-id="e577e-103">Samband mellan servicestatus och förloppsfält</span><span class="sxs-lookup"><span data-stu-id="e577e-103">Service status and progress field interaction</span></span> 

[!include [banner](../includes/banner.md)]


<span data-ttu-id="e577e-104">I formuläret **Serviceorder**, fältet **Förlopp** i serviceorderns huvud statusvärdet för hela serviceordern, och **Status** anger statusvärdet för enskilda serviceorderrader.</span><span class="sxs-lookup"><span data-stu-id="e577e-104">In the **Service orders** form, the **Progress** field on the service order header reflects the status of the whole service order, and the **Status** reports the status of individual service order lines.</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="e577e-105">Förlopp</span><span class="sxs-lookup"><span data-stu-id="e577e-105">Progress</span></span></p></th>
<th><p><span data-ttu-id="e577e-106">Status för rad 1</span><span class="sxs-lookup"><span data-stu-id="e577e-106">Line 1 Status</span></span></p></th>
<th><p><span data-ttu-id="e577e-107">Status för rad 2</span><span class="sxs-lookup"><span data-stu-id="e577e-107">Line 2 Status</span></span></p></th>
<th><p><span data-ttu-id="e577e-108">Status för rad 3</span><span class="sxs-lookup"><span data-stu-id="e577e-108">Line 3 Status</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e577e-109"><strong>Pågår</strong></span><span class="sxs-lookup"><span data-stu-id="e577e-109"><strong>In process</strong></span></span></p></td>
<td><p><span data-ttu-id="e577e-110"><strong>Skapat</strong></span><span class="sxs-lookup"><span data-stu-id="e577e-110"><strong>Created</strong></span></span></p></td>
<td><p><span data-ttu-id="e577e-111"><strong>Skapat</strong></span><span class="sxs-lookup"><span data-stu-id="e577e-111"><strong>Created</strong></span></span></p></td>
<td><p><span data-ttu-id="e577e-112"><strong>Skapat</strong></span><span class="sxs-lookup"><span data-stu-id="e577e-112"><strong>Created</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e577e-113"><strong>Pågår</strong></span><span class="sxs-lookup"><span data-stu-id="e577e-113"><strong>In process</strong></span></span></p></td>
<td><p><span data-ttu-id="e577e-114"><strong>Annullerad</strong></span><span class="sxs-lookup"><span data-stu-id="e577e-114"><strong>Canceled</strong></span></span></p></td>
<td><p><span data-ttu-id="e577e-115"><strong>Skapat</strong></span><span class="sxs-lookup"><span data-stu-id="e577e-115"><strong>Created</strong></span></span></p></td>
<td><p><span data-ttu-id="e577e-116"><strong>Skapat</strong></span><span class="sxs-lookup"><span data-stu-id="e577e-116"><strong>Created</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e577e-117"><strong>Pågår</strong></span><span class="sxs-lookup"><span data-stu-id="e577e-117"><strong>In process</strong></span></span></p></td>
<td><p><span data-ttu-id="e577e-118"><strong>Skapat</strong></span><span class="sxs-lookup"><span data-stu-id="e577e-118"><strong>Created</strong></span></span></p></td>
<td><p><span data-ttu-id="e577e-119"><strong>Annullerad</strong></span><span class="sxs-lookup"><span data-stu-id="e577e-119"><strong>Canceled</strong></span></span></p></td>
<td><p><span data-ttu-id="e577e-120"><strong>Bokförd</strong></span><span class="sxs-lookup"><span data-stu-id="e577e-120"><strong>Posted</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e577e-121"><strong>Annullerad</strong></span><span class="sxs-lookup"><span data-stu-id="e577e-121"><strong>Canceled</strong></span></span></p></td>
<td><p><span data-ttu-id="e577e-122"><strong>Annullerad</strong></span><span class="sxs-lookup"><span data-stu-id="e577e-122"><strong>Canceled</strong></span></span></p></td>
<td><p><span data-ttu-id="e577e-123"><strong>Annullerad</strong></span><span class="sxs-lookup"><span data-stu-id="e577e-123"><strong>Canceled</strong></span></span></p></td>
<td><p><span data-ttu-id="e577e-124"><strong>Annullerad</strong></span><span class="sxs-lookup"><span data-stu-id="e577e-124"><strong>Canceled</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e577e-125"><strong>Bokförd</strong></span><span class="sxs-lookup"><span data-stu-id="e577e-125"><strong>Posted</strong></span></span></p></td>
<td><p><span data-ttu-id="e577e-126"><strong>Bokförd</strong></span><span class="sxs-lookup"><span data-stu-id="e577e-126"><strong>Posted</strong></span></span></p></td>
<td><p><span data-ttu-id="e577e-127"><strong>Bokförd</strong></span><span class="sxs-lookup"><span data-stu-id="e577e-127"><strong>Posted</strong></span></span></p></td>
<td><p><span data-ttu-id="e577e-128"><strong>Bokförd</strong></span><span class="sxs-lookup"><span data-stu-id="e577e-128"><strong>Posted</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e577e-129"><strong>Bokförd</strong></span><span class="sxs-lookup"><span data-stu-id="e577e-129"><strong>Posted</strong></span></span></p></td>
<td><p><span data-ttu-id="e577e-130"><strong>Bokförd</strong></span><span class="sxs-lookup"><span data-stu-id="e577e-130"><strong>Posted</strong></span></span></p></td>
<td><p><span data-ttu-id="e577e-131"><strong>Annullerad</strong></span><span class="sxs-lookup"><span data-stu-id="e577e-131"><strong>Canceled</strong></span></span></p></td>
<td><p><span data-ttu-id="e577e-132"><strong>Annullerad</strong></span><span class="sxs-lookup"><span data-stu-id="e577e-132"><strong>Canceled</strong></span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="e577e-133">En serviceorders förlopp är pågående om alla rader har statusvärdet **Skapad**; och det pågår fortfarande om några av raderna har statusvärdet **Avbruten** eller **Bokförd**.</span><span class="sxs-lookup"><span data-stu-id="e577e-133">The progress of a service order is in process if all lines have the status **Created**; it is still in process if some of the lines have a status of **Canceled** or **Posted**.</span></span>

<span data-ttu-id="e577e-134">Om alla rader på en serviceorder markeras som **Bokförd**, är förloppet på statusordern **Bokförd**.</span><span class="sxs-lookup"><span data-stu-id="e577e-134">If all lines in a service order are marked as **Posted**, the progress of the status order is **Posted**.</span></span> <span data-ttu-id="e577e-135">Om några rader är **Bokförd** och vissa är **Avbruten**, är förloppet fortfarande **Bokförd**.</span><span class="sxs-lookup"><span data-stu-id="e577e-135">If some lines are **Posted** and some are **Canceled**, the progress is still **Posted**.</span></span>

  


