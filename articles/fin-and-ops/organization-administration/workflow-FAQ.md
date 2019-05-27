---
title: Vanliga frågor om arbetsflöde
description: Detta avsnitt besvarar några vanliga frågor om arbetsflödessystemet i Microsoft Dynamics 365 for Finance and Operations.
author: ChrisGarty
manager: AnnBe
ms.date: 05/07/2019
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
ms.openlocfilehash: f6240b1b5136937aa47f455547fed6f0c7c08e2c
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/07/2019
ms.locfileid: "1509301"
---
# <a name="workflow-system"></a><span data-ttu-id="9b54f-103">Arbetsflödessystem</span><span class="sxs-lookup"><span data-stu-id="9b54f-103">Workflow system</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="9b54f-104">Detta avsnitt besvarar några vanliga frågor om arbetsflödessystemet i Microsoft Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="9b54f-104">This topic answers frequently asked questions about the workflow system in Microsoft Dynamics 365 for Finance and Operations.</span></span>

## <a name="notifications"></a><span data-ttu-id="9b54f-105">Meddelanden</span><span class="sxs-lookup"><span data-stu-id="9b54f-105">Notifications</span></span>

### <a name="why-are-multiple-notifications-received-when-a-work-item-is-rejected"></a><span data-ttu-id="9b54f-106">Varför tas flera meddelanden emot när en arbetsuppgift avvisas?</span><span class="sxs-lookup"><span data-stu-id="9b54f-106">Why are multiple notifications received when a work item is rejected?</span></span>
<span data-ttu-id="9b54f-107">När en arbetsuppgift har avvisats kommer detta arbetsobjekt slutföras som avvisat.</span><span class="sxs-lookup"><span data-stu-id="9b54f-107">When a work item is rejected, that work item is completed as rejected.</span></span> <span data-ttu-id="9b54f-108">En annan arbetsuppgift skapas och tilldelas till upphovsmannen.</span><span class="sxs-lookup"><span data-stu-id="9b54f-108">Another work item is created and assigned to the originator.</span></span> <span data-ttu-id="9b54f-109">Detta innebär att det finns ett meddelande till upphovsmannen för den avvisade arbetsuppgiften och ett separat meddelande till användaren som är tilldelad till den nya ”ändringsbegärda” arbetsuppgiften.</span><span class="sxs-lookup"><span data-stu-id="9b54f-109">This means that there is a notification to the originator for the rejected work item, and a separate notification to the user assigned to the new "change requested" work item.</span></span> 

<span data-ttu-id="9b54f-110">Varje meddelande är för en olika arbetsuppgift, men likheten kan vara förvirrande.</span><span class="sxs-lookup"><span data-stu-id="9b54f-110">Each notification is for a different work item, but the similarity can cause confusion.</span></span> <span data-ttu-id="9b54f-111">Vi undersöker sätt att förbättra detta i framtida versioner.</span><span class="sxs-lookup"><span data-stu-id="9b54f-111">We are looking at ways to improve this in a future release.</span></span>

### <a name="why-are-my-workflow-exports-failing"></a><span data-ttu-id="9b54f-112">Varför fungerar inte min arbetsflödesexport?</span><span class="sxs-lookup"><span data-stu-id="9b54f-112">Why are my workflow exports failing?</span></span>
<span data-ttu-id="9b54f-113">Det finns en begränsning i funktionen för att exportera arbetsflöden som förhindrar att arbetsflödesnamn innehåller fler än 48 tecken.</span><span class="sxs-lookup"><span data-stu-id="9b54f-113">There is currently a limitation in the workflow export feature that prevents workflow names from exceeding 48 characters.</span></span> <span data-ttu-id="9b54f-114">Om du använder ett namn som är längre än 48 tecken kan felmeddelandet "servern kunde inte autentisera begäran" visas och/eller förhindra att en fil exporteras utan filtyp.</span><span class="sxs-lookup"><span data-stu-id="9b54f-114">Using a name that is longer than 48 characters can result in a "Server failed to authenticate the request" error and/or prevent a file to be exported  without a file type.</span></span> <span data-ttu-id="9b54f-115">Följande blogginlägg innehåller mer information om [Felsökning av arbetsflödesexport](https://community.dynamics.com/ax/b/elandaxdynamicsaxupgradesanddevelopment/archive/2019/04/10/workflow-export-troubleshooting).</span><span class="sxs-lookup"><span data-stu-id="9b54f-115">The following blog post provides more details [Workflow Export Troubleshooting](https://community.dynamics.com/ax/b/elandaxdynamicsaxupgradesanddevelopment/archive/2019/04/10/workflow-export-troubleshooting).</span></span>
