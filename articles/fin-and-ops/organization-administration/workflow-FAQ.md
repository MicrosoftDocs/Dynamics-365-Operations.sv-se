---
title: Vanliga frågor om arbetsflöde
description: Detta avsnitt besvarar några vanliga frågor om arbetsflödessystemet i Microsoft Dynamics 365 for Finance and Operations.
author: ChrisGarty
manager: AnnBe
ms.date: 02/28/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: cgarty
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f058a450eb18e688efbc5306a42b4efef6aa91e7
ms.sourcegitcommit: 9a723737565ac78c884e40f7129d0f5aad747524
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/01/2019
ms.locfileid: "773233"
---
# <a name="workflow-system"></a><span data-ttu-id="e70f3-103">Arbetsflödessystem</span><span class="sxs-lookup"><span data-stu-id="e70f3-103">Workflow system</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="e70f3-104">Detta avsnitt besvarar några vanliga frågor om arbetsflödessystemet i Microsoft Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="e70f3-104">This topic answers frequently asked questions about the workflow system in Microsoft Dynamics 365 for Finance and Operations.</span></span>

## <a name="notifications"></a><span data-ttu-id="e70f3-105">Meddelanden</span><span class="sxs-lookup"><span data-stu-id="e70f3-105">Notifications</span></span>

### <a name="why-are-multiple-notifications-received-when-a-work-item-is-rejected"></a><span data-ttu-id="e70f3-106">Varför tas flera meddelanden emot när en arbetsuppgift avvisas?</span><span class="sxs-lookup"><span data-stu-id="e70f3-106">Why are multiple notifications received when a work item is rejected?</span></span>
<span data-ttu-id="e70f3-107">När en arbetsuppgift har avvisats kommer detta arbetsobjekt slutföras som avvisat.</span><span class="sxs-lookup"><span data-stu-id="e70f3-107">When a work item is rejected, that work item is completed as rejected.</span></span> <span data-ttu-id="e70f3-108">En annan arbetsuppgift skapas och tilldelas till upphovsmannen.</span><span class="sxs-lookup"><span data-stu-id="e70f3-108">Another work item is created and assigned to the originator.</span></span> <span data-ttu-id="e70f3-109">Detta innebär att det finns ett meddelande till upphovsmannen för den avvisade arbetsuppgiften och ett separat meddelande till användaren som är tilldelad till den nya ”ändringsbegärda” arbetsuppgiften.</span><span class="sxs-lookup"><span data-stu-id="e70f3-109">This means that there is a notification to the originator for the rejected work item, and a separate notification to the user assigned to the new "change requested" work item.</span></span> 

<span data-ttu-id="e70f3-110">Varje meddelande är för en olika arbetsuppgift, men likheten kan vara förvirrande.</span><span class="sxs-lookup"><span data-stu-id="e70f3-110">Each notification is for a different work item, but the similarity can cause confusion.</span></span> <span data-ttu-id="e70f3-111">Vi undersöker sätt att förbättra detta i framtida versioner.</span><span class="sxs-lookup"><span data-stu-id="e70f3-111">We are looking at ways to improve this in a future release.</span></span>
