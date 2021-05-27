---
title: Systemadministratörer kan inte rensa order som finns eftersom de inte är behöriga
description: Systemadministratörer kan inte rensa order som finns eftersom de inte är behöriga.
author: SmithaNataraj
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: SalesTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: acabd6409d9b2860535335bc648bcc34304e0cb0
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026932"
---
# <a name="system-administrators-cant-clear-order-holds-because-they-arent-authorized"></a><span data-ttu-id="16722-103">Systemadministratörer kan inte rensa order som finns eftersom de inte är behöriga</span><span class="sxs-lookup"><span data-stu-id="16722-103">System administrators can't clear order holds because they aren't authorized</span></span>

<span data-ttu-id="16722-104">KB-nummer: 4614642</span><span class="sxs-lookup"><span data-stu-id="16722-104">KB number: 4614642</span></span>

## <a name="symptoms"></a><span data-ttu-id="16722-105">Symtom</span><span class="sxs-lookup"><span data-stu-id="16722-105">Symptoms</span></span>

<span data-ttu-id="16722-106">Systemadministratörer kan inte rensa försäljningsorder såvida de inte har den specifika roll som är tilldelad i orderkoden.</span><span class="sxs-lookup"><span data-stu-id="16722-106">System administrators can't clear sales order holds unless they have the specific role that is assigned in the order hold code.</span></span>

## <a name="resolution"></a><span data-ttu-id="16722-107">Upplösning</span><span class="sxs-lookup"><span data-stu-id="16722-107">Resolution</span></span>

<span data-ttu-id="16722-108">Åtkomsten till vissa åtgärder, till exempel att rensa försäljningsorder, styrs av inställningarna i en affärspolicy.</span><span class="sxs-lookup"><span data-stu-id="16722-108">Access to some operations, such as clearing sales order holds, is driven by the setup of a business policy.</span></span> <span data-ttu-id="16722-109">Systemadministratörer har normalt inte rätt att utföra åtgärder av den här typen.</span><span class="sxs-lookup"><span data-stu-id="16722-109">System administrators aren't typically allowed to perform operations of this type.</span></span> 

<span data-ttu-id="16722-110">Oftast styrs åtkomsten till en viss uppgift av affärspolicyn och endast vissa personer i organisationen godkänns för att utföra den uppgiften.</span><span class="sxs-lookup"><span data-stu-id="16722-110">More often, access to perform a specific task is governed by business policies, and only specific persons in an organization are approved to perform that task.</span></span> <span data-ttu-id="16722-111">Godkännanden kan till exempel vara resultat av arbetsflödesgodkännanden och specifika uppgifter som är resultatet av en arbetsflödeskonfiguration.</span><span class="sxs-lookup"><span data-stu-id="16722-111">Examples include approvals that are the result of workflow approvals and specific tasks that are the result of a workflow configuration.</span></span>

<span data-ttu-id="16722-112">Även om inget arbetsflöde associeras med order är principen liknande.</span><span class="sxs-lookup"><span data-stu-id="16722-112">Although no workflow is associated with order holds, the principle is similar.</span></span> <span data-ttu-id="16722-113">En relevant roll anger den specifika gruppen av personer i en organisation som har rätt att rensa order.</span><span class="sxs-lookup"><span data-stu-id="16722-113">A relevant role designates the specific group of people in an organization who have the right to clear order holds.</span></span> <span data-ttu-id="16722-114">Den här behörigheten bör inte nödvändigtvis beviljas till alla administratörer, eftersom den metoden bryter mot den definierade affärspolicyn.</span><span class="sxs-lookup"><span data-stu-id="16722-114">This right should not necessarily be granted to all administrators, because that approach violates the defined business policy.</span></span>
