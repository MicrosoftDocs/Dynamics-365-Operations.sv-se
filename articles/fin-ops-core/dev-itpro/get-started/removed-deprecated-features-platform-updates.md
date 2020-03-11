---
title: Borttagna eller avskrivna plattformsfunktioner
description: I det här avsnittet beskrivs funktioner som har tagits bort, eller har planerats för borttagning i plattformsuppdatering av Finance and Operations-appar.
author: sericks007
manager: AnnBe
ms.date: 02/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.scope: Operations
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2020-02-29
ms.dyn365.ops.version: Platform update 33
ms.openlocfilehash: 66e1420c7053c0df9f42b15c55aba1a8c869f02a
ms.sourcegitcommit: 2cc3b89efdd90f8d80883b7a271d7885282ba3e8
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/26/2020
ms.locfileid: "3087893"
---
# <a name="removed-or-deprecated-platform-features"></a><span data-ttu-id="eb7da-103">Borttagna eller avskrivna plattformsfunktioner</span><span class="sxs-lookup"><span data-stu-id="eb7da-103">Removed or deprecated platform features</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="eb7da-104">I det här avsnittet beskrivs funktioner som har tagits bort, eller har planerats för borttagning i plattformsuppdatering av Finance and Operations-appar.</span><span class="sxs-lookup"><span data-stu-id="eb7da-104">This topic describes features that have been removed, or that are planned for removal in platform updates of Finance and Operations apps.</span></span>

- <span data-ttu-id="eb7da-105">En *borttagen* funktion är inte längre tillgänglig i produkten.</span><span class="sxs-lookup"><span data-stu-id="eb7da-105">A *removed* feature is no longer available in the product.</span></span>
- <span data-ttu-id="eb7da-106">En *borttagen* funktion är inte i aktiv utveckling och kan tas bort i en kommande uppdatering.</span><span class="sxs-lookup"><span data-stu-id="eb7da-106">A *deprecated* feature is not in active development and may be removed in a future update.</span></span>

<span data-ttu-id="eb7da-107">Den här listan är avsedd att hjälpa dig att ta hänsyn till dessa borttagna och inaktuella funktioner för din planerings skull.</span><span class="sxs-lookup"><span data-stu-id="eb7da-107">This list is intended to help you consider these removals and deprecations for your own planning.</span></span> 

> [!NOTE]
> <span data-ttu-id="eb7da-108">Detaljerad information om objekt i Finance and Operations-appar hittas i [Tekniska referensrapporter](https://mbs.microsoft.com/customersource/northamerica/AX/downloads/reports/axtechrefrep).</span><span class="sxs-lookup"><span data-stu-id="eb7da-108">Detailed information about objects in Finance and Operations apps can be found in the [Technical reference reports](https://mbs.microsoft.com/customersource/northamerica/AX/downloads/reports/axtechrefrep).</span></span> <span data-ttu-id="eb7da-109">Du kan jämföra olika versioner av rapporterna för mer information om objekt som har ändrats eller tagits bort i varje version av Finance and Operations-appar.</span><span class="sxs-lookup"><span data-stu-id="eb7da-109">You can compare the different versions of these reports to learn about objects that have changed or been removed in each version of Finance and Operations apps.</span></span>

## <a name="platform-update-32"></a><span data-ttu-id="eb7da-110">Plattform update 32</span><span class="sxs-lookup"><span data-stu-id="eb7da-110">Platform update 32</span></span>

### <a name="workflow-request-change-dialog-box-no-longer-includes-user-selection-drop-down-list"></a><span data-ttu-id="eb7da-111">Dialogrutan ändra arbetsflödesförfrågan innehåller inte längre listrutan för användarval</span><span class="sxs-lookup"><span data-stu-id="eb7da-111">Workflow request change dialog box no longer includes user selection drop-down list</span></span>
|   |  |
|------------|--------------------|
| <span data-ttu-id="eb7da-112">**Orsak till inaktuell/borttagning**</span><span class="sxs-lookup"><span data-stu-id="eb7da-112">**Reason for deprecation/removal**</span></span> | <span data-ttu-id="eb7da-113">Detta är ett säkerhetsproblem eftersom begäran om ändring kan skickas till en oavsiktlig användare.</span><span class="sxs-lookup"><span data-stu-id="eb7da-113">This was a security issue because the request for change could be sent to an unintended user.</span></span> <span data-ttu-id="eb7da-114">Detta var också ett användbarhetsproblem eftersom det tvingade användaren att avgöra vem som har skapat arbetsflödet och manuellt välja dem manuellt.</span><span class="sxs-lookup"><span data-stu-id="eb7da-114">This was also a usability issue because it forced the user to determine who the workflow originator was and manually select them.</span></span>  |
| <span data-ttu-id="eb7da-115">**Ersatt av en annan funktion?**</span><span class="sxs-lookup"><span data-stu-id="eb7da-115">**Replaced by another feature?**</span></span>   | <span data-ttu-id="eb7da-116">Nej</span><span class="sxs-lookup"><span data-stu-id="eb7da-116">No</span></span> |
| <span data-ttu-id="eb7da-117">**Produktområden som påverkas**</span><span class="sxs-lookup"><span data-stu-id="eb7da-117">**Product areas affected**</span></span>         | <span data-ttu-id="eb7da-118">Arbetsflöde</span><span class="sxs-lookup"><span data-stu-id="eb7da-118">Workflow</span></span> |
| <span data-ttu-id="eb7da-119">**Distribueringsalternativ**</span><span class="sxs-lookup"><span data-stu-id="eb7da-119">**Deployment option**</span></span>              | <span data-ttu-id="eb7da-120">Allt</span><span class="sxs-lookup"><span data-stu-id="eb7da-120">All</span></span> |
| <span data-ttu-id="eb7da-121">**Status**</span><span class="sxs-lookup"><span data-stu-id="eb7da-121">**Status**</span></span>                         | <span data-ttu-id="eb7da-122">Listrutan för användarval har tagits bort från dialogrutan ändring av begäran i plattformsuppdatering 32.</span><span class="sxs-lookup"><span data-stu-id="eb7da-122">The user selection drop-down list was removed from the request change dialog box in Platform update 32.</span></span> <span data-ttu-id="eb7da-123">Begäranden om ändring av begäran kommer att skickas automatiskt till upphovspersonen som avsett.</span><span class="sxs-lookup"><span data-stu-id="eb7da-123">Request change requests will be automatically sent to the originator as intended.</span></span> <span data-ttu-id="eb7da-124">Mer information om den här funktionen finns i [åtgärder i godkännandeprocesser för arbetsflöde](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/organization-administration/workflow-actions?toc=%2Fdynamics365%2Fcommerce%2Ftoc.json#request-change).</span><span class="sxs-lookup"><span data-stu-id="eb7da-124">For more information about this functionality, see [Actions in workflow approval processes](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/organization-administration/workflow-actions?toc=%2Fdynamics365%2Fcommerce%2Ftoc.json#request-change).</span></span> |

## <a name="previous-announcements-about-removed-or-deprecated-features"></a><span data-ttu-id="eb7da-125">Tidigare meddelanden om borttagna eller inaktuella funktioner</span><span class="sxs-lookup"><span data-stu-id="eb7da-125">Previous announcements about removed or deprecated features</span></span>
<span data-ttu-id="eb7da-126">Om du vill veta mer om funktioner som har tagits bort eller ersatts i tidigare versioner, se [borttagna eller inaktuella funktioner i tidigare versioner](../migration-upgrade/deprecated-features.md).</span><span class="sxs-lookup"><span data-stu-id="eb7da-126">To learn more about features that have been removed or deprecated in previous releases, see [Removed or deprecated features in previous releases](../migration-upgrade/deprecated-features.md).</span></span>

