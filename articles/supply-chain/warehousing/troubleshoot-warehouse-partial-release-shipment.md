---
title: Felsöka delvis frisläppning och delleverans
description: Det här avsnittet beskriver hur du åtgärdar vanliga problem som du kan stöta på när du arbetar med delvis frisläppning och delleveranser i Microsoft Dynamics 365 Supply Chain Management.
author: perlynne
ms.date: 10/19/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-10-19
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 5534099f81a97a1dcf4908784fd71dd03cf94eaf
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5828164"
---
# <a name="troubleshoot-partial-releases-and-partial-shipments"></a><span data-ttu-id="19f83-103">Felsöka delvis frisläppning och delleverans</span><span class="sxs-lookup"><span data-stu-id="19f83-103">Troubleshoot partial releases and partial shipments</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="19f83-104">Det här avsnittet beskriver hur du åtgärdar vanliga problem som du kan stöta på när du arbetar med delvis frisläppning och delleveranser i Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="19f83-104">This topic describes how to fix common issues that you might encounter while you work with partial releases and partial shipments in Microsoft Dynamics 365 Supply Chain Management.</span></span>

## <a name="the-release-status-of-a-sales-order-remains-partially-released-even-after-the-sales-order-is-invoiced"></a><span data-ttu-id="19f83-105">Frisläppningsstatusen för en försäljningsorder förblir delvis frisläppt även när försäljningsordern har fakturerats.</span><span class="sxs-lookup"><span data-stu-id="19f83-105">The release status of a sales order remains Partially released even after the sales order is invoiced.</span></span>

### <a name="issue-description"></a><span data-ttu-id="19f83-106">Problembeskrivning</span><span class="sxs-lookup"><span data-stu-id="19f83-106">Issue description</span></span>

<span data-ttu-id="19f83-107">En försäljningsorder är en leveransorder, men en eller flera artiklar på den har ett annat leverans sätt.</span><span class="sxs-lookup"><span data-stu-id="19f83-107">A sales order is a delivery order, but one or more items on it have a different mode of delivery.</span></span> <span data-ttu-id="19f83-108">När ordern har fakturerats har den fortfarande frisläppningsstatus som *delvis släppts*.</span><span class="sxs-lookup"><span data-stu-id="19f83-108">After the order is invoiced, it still has a release status of *Partially released*.</span></span>

<span data-ttu-id="19f83-109">En försäljningsorder har till exempel två artiklar: en för leverans och en för upphämtning.</span><span class="sxs-lookup"><span data-stu-id="19f83-109">For example, a sales order has two items: one for delivery and one for pickup.</span></span> <span data-ttu-id="19f83-110">Både leveransen och upphämtningen har utförts.</span><span class="sxs-lookup"><span data-stu-id="19f83-110">Both the delivery and the pickup have been done.</span></span> <span data-ttu-id="19f83-111">Därför har båda raderna fakturerats.</span><span class="sxs-lookup"><span data-stu-id="19f83-111">Therefore, both lines have been invoiced.</span></span> <span data-ttu-id="19f83-112">Frisläppnings status visas fortfarande som *delvis utsläppt*, vilket är missvisande.</span><span class="sxs-lookup"><span data-stu-id="19f83-112">However, the release status is still shown as *Partially released*, which is misleading.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="19f83-113">Problemlösning</span><span class="sxs-lookup"><span data-stu-id="19f83-113">Issue resolution</span></span>

<span data-ttu-id="19f83-114">Frisläppningsstatus gäller bara för orderrader där artiklarna är aktiverade för lagerstyrning.</span><span class="sxs-lookup"><span data-stu-id="19f83-114">The release status applies only to order lines where the items are enabled for warehouse management.</span></span> <span data-ttu-id="19f83-115">Därför fortsätter frisläppningsstatusen att vara *delvis släppts* i det här scenariot.</span><span class="sxs-lookup"><span data-stu-id="19f83-115">Therefore, the release status remains *Partially released* in this scenario.</span></span> <span data-ttu-id="19f83-116">Microsoft har utvärderat det här problemet och har fastställt att det är en funktionsbegränsning.</span><span class="sxs-lookup"><span data-stu-id="19f83-116">Microsoft has evaluated this issue and has determined that it's a feature limitation.</span></span> <span data-ttu-id="19f83-117">Ett tillägg kan läggas till som en del av följesedeln och faktureringsprocessen för att uppdatera frisläppningsstatus.</span><span class="sxs-lookup"><span data-stu-id="19f83-117">An extension could be added as part of the packing slip and invoicing process to update the release status.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]