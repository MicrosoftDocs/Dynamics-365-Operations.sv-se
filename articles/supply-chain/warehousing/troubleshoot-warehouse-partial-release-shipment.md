---
title: Felsöka delvis frisläppning och delleverans
description: Det här avsnittet beskriver hur du åtgärdar vanliga problem som du kan stöta på när du arbetar med delvis frisläppning och delleveranser i Microsoft Dynamics 365 Supply Chain Management.
author: perlynne
manager: tfehr
ms.date: 10/19/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-10-19
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: e89a430f90374733b23fadaf53f5bab598d67d62
ms.sourcegitcommit: deb711c92251ed48cdf20ea514d03461c26a2262
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/25/2020
ms.locfileid: "4645958"
---
# <a name="troubleshoot-partial-releases-and-partial-shipments"></a><span data-ttu-id="7944a-103">Felsöka delvis frisläppning och delleverans</span><span class="sxs-lookup"><span data-stu-id="7944a-103">Troubleshoot partial releases and partial shipments</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="7944a-104">Det här avsnittet beskriver hur du åtgärdar vanliga problem som du kan stöta på när du arbetar med delvis frisläppning och delleveranser i Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="7944a-104">This topic describes how to fix common issues that you might encounter while you work with partial releases and partial shipments in Microsoft Dynamics 365 Supply Chain Management.</span></span>

## <a name="the-release-status-of-a-sales-order-remains-partially-released-even-after-the-sales-order-is-invoiced"></a><span data-ttu-id="7944a-105">Frisläppningsstatusen för en försäljningsorder förblir delvis frisläppt även när försäljningsordern har fakturerats.</span><span class="sxs-lookup"><span data-stu-id="7944a-105">The release status of a sales order remains Partially released even after the sales order is invoiced.</span></span>

### <a name="issue-description"></a><span data-ttu-id="7944a-106">Problembeskrivning</span><span class="sxs-lookup"><span data-stu-id="7944a-106">Issue description</span></span>

<span data-ttu-id="7944a-107">En försäljningsorder är en leveransorder, men en eller flera artiklar på den har ett annat leverans sätt.</span><span class="sxs-lookup"><span data-stu-id="7944a-107">A sales order is a delivery order, but one or more items on it have a different mode of delivery.</span></span> <span data-ttu-id="7944a-108">När ordern har fakturerats har den fortfarande frisläppningsstatus som *delvis släppts*.</span><span class="sxs-lookup"><span data-stu-id="7944a-108">After the order is invoiced, it still has a release status of *Partially released*.</span></span>

<span data-ttu-id="7944a-109">En försäljningsorder har till exempel två artiklar: en för leverans och en för upphämtning.</span><span class="sxs-lookup"><span data-stu-id="7944a-109">For example, a sales order has two items: one for delivery and one for pickup.</span></span> <span data-ttu-id="7944a-110">Både leveransen och upphämtningen har utförts.</span><span class="sxs-lookup"><span data-stu-id="7944a-110">Both the delivery and the pickup have been done.</span></span> <span data-ttu-id="7944a-111">Därför har båda raderna fakturerats.</span><span class="sxs-lookup"><span data-stu-id="7944a-111">Therefore, both lines have been invoiced.</span></span> <span data-ttu-id="7944a-112">Frisläppnings status visas fortfarande som *delvis utsläppt*, vilket är missvisande.</span><span class="sxs-lookup"><span data-stu-id="7944a-112">However, the release status is still shown as *Partially released*, which is misleading.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="7944a-113">Problemlösning</span><span class="sxs-lookup"><span data-stu-id="7944a-113">Issue resolution</span></span>

<span data-ttu-id="7944a-114">Frisläppningsstatus gäller bara för orderrader där artiklarna är aktiverade för lagerstyrning.</span><span class="sxs-lookup"><span data-stu-id="7944a-114">The release status applies only to order lines where the items are enabled for warehouse management.</span></span> <span data-ttu-id="7944a-115">Därför fortsätter frisläppningsstatusen att vara *delvis släppts* i det här scenariot.</span><span class="sxs-lookup"><span data-stu-id="7944a-115">Therefore, the release status remains *Partially released* in this scenario.</span></span> <span data-ttu-id="7944a-116">Microsoft har utvärderat det här problemet och har fastställt att det är en funktionsbegränsning.</span><span class="sxs-lookup"><span data-stu-id="7944a-116">Microsoft has evaluated this issue and has determined that it's a feature limitation.</span></span> <span data-ttu-id="7944a-117">Ett tillägg kan läggas till som en del av följesedeln och faktureringsprocessen för att uppdatera frisläppningsstatus.</span><span class="sxs-lookup"><span data-stu-id="7944a-117">An extension could be added as part of the packing slip and invoicing process to update the release status.</span></span>
