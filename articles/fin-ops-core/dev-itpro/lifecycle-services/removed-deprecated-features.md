---
title: Borttagna eller föråldrade funktioner i Lifecycle Services (LCS)
description: I det här avsnittet beskrivs funktioner som har tagits bort, eller har planerats för borttagning från Microsoft Dynamics Lifecycle Services (LCS).
author: AngelMarshall
manager: AnnBe
ms.date: 02/05/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.scope: Operations
ms.search.region: Global
ms.author: tsmarsha
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 96ecd040ef8661765c0a3861d8e07fee3c241161
ms.sourcegitcommit: fb7d0efd97754f1ae0b5aa765d0eeb3f57b8078f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/05/2020
ms.locfileid: "3027990"
---
# <a name="removed-or-deprecated-features-in-lifecycle-services-lcs"></a><span data-ttu-id="6248e-103">Borttagna eller föråldrade funktioner i Lifecycle Services (LCS)</span><span class="sxs-lookup"><span data-stu-id="6248e-103">Removed or deprecated features in Lifecycle Services (LCS)</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="6248e-104">I det här avsnittet beskrivs funktioner som har tagits bort eller är utfasad för Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="6248e-104">This topic describes features that have been removed or deprecated for Microsoft Dynamics Lifecycle Services (LCS).</span></span>

- <span data-ttu-id="6248e-105">En *borttagen* funktion är inte längre tillgänglig i tjänsten.</span><span class="sxs-lookup"><span data-stu-id="6248e-105">A *removed* feature is no longer available in the service.</span></span>
- <span data-ttu-id="6248e-106">En *borttagen* funktion är inte i aktiv utveckling och kan tas bort i en kommande uppdatering.</span><span class="sxs-lookup"><span data-stu-id="6248e-106">A *deprecated* feature isn't in active development and might be removed in a future update.</span></span>

<span data-ttu-id="6248e-107">Den här listan tillhandahålls så att du kan ta hänsyn till dessa borttagna och inaktuella funktioner för din planerings skull.</span><span class="sxs-lookup"><span data-stu-id="6248e-107">This list is provided so that you can consider these removals and deprecations as you do your own planning.</span></span>

## <a name="october-2019-announcements"></a><span data-ttu-id="6248e-108">Oktober 2019 meddelanden</span><span class="sxs-lookup"><span data-stu-id="6248e-108">October 2019 announcements</span></span>

### <a name="flowchart-diagrams-in-business-process-modeler"></a><span data-ttu-id="6248e-109">Flödesscheman i affärsprocessmodelleraren</span><span class="sxs-lookup"><span data-stu-id="6248e-109">Flowchart diagrams in Business process modeler</span></span>

<table>
<tbody>
<tr>
<td><span data-ttu-id="6248e-110"><strong>Orsak till inaktuell/borttagning</strong></span><span class="sxs-lookup"><span data-stu-id="6248e-110"><strong>Reason for deprecation/removal</strong></span></span></td>
<td><span data-ttu-id="6248e-111">Vi använder inte komponenten flödesschema i Affärsprocessmodelleraren (BPM), eftersom äldre designen orsakade låg användning.</span><span class="sxs-lookup"><span data-stu-id="6248e-111">We are deprecating the flowchart diagrams component in Business process modeler (BPM), because the legacy design caused low usage.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="6248e-112"><strong>Ersatt av en annan funktion?</strong></span><span class="sxs-lookup"><span data-stu-id="6248e-112"><strong>Replaced by another feature?</strong></span></span></td>
<td><span data-ttu-id="6248e-113">Nej</span><span class="sxs-lookup"><span data-stu-id="6248e-113">No</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="6248e-114"><strong>Områden som påverkas</strong></span><span class="sxs-lookup"><span data-stu-id="6248e-114"><strong>Areas affected</strong></span></span></td>
<td><span data-ttu-id="6248e-115">Affärsprocessmodelleraren</span><span class="sxs-lookup"><span data-stu-id="6248e-115">Business process modeler</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="6248e-116"><strong>Status</strong></span><span class="sxs-lookup"><span data-stu-id="6248e-116"><strong>Status</strong></span></span></td>
<td><span data-ttu-id="6248e-117">Inaktuell: komponenten flödesschema i BPM förväntas tas bort år 2020.</span><span class="sxs-lookup"><span data-stu-id="6248e-117">Deprecated: The flowchart diagrams component in BPM is expected to be removed in 2020.</span></span> <span data-ttu-id="6248e-118">Följande funktion kommer att tas bort:</span><span class="sxs-lookup"><span data-stu-id="6248e-118">The following functionality will be removed:</span></span>
<ul>
<li><span data-ttu-id="6248e-119">Befintliga flödesscheman kommer inte att vara tillgängliga för visning eller redigering.</span><span class="sxs-lookup"><span data-stu-id="6248e-119">Existing flowcharts will be unavailable for viewing or editing.</span></span> <span data-ttu-id="6248e-120">De formegenskaper som associeras med flödesschemats aktiviteter kommer inte heller att vara tillgängliga, eftersom hela <strong>flödesschemat</strong> kommer att tas bort.</span><span class="sxs-lookup"><span data-stu-id="6248e-120">The shape properties that are associated with flowchart activities will also be unavailable, because the whole <strong>Flowchart</strong> tab will be removed.</span></span> <span data-ttu-id="6248e-121">Dessa flödesscheman innehåller både standardflödesscheman som genereras automatiskt och anpassade flödesscheman som ändras baserat på dessa standard flödesscheman.</span><span class="sxs-lookup"><span data-stu-id="6248e-121">These flowcharts include both the default flowcharts that are automatically generated and customized flowcharts that are modified based on those default flowcharts.</span></span></li>
<li><span data-ttu-id="6248e-122">Den inaktuella funktionen Bristanalys kommer inte att vara tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="6248e-122">The legacy fit/gap analysis feature will be unavailable.</span></span> <span data-ttu-id="6248e-123">Därför skapas ingen lista över luckor automatiskt eller tillgänglig för export.</span><span class="sxs-lookup"><span data-stu-id="6248e-123">Therefore, no gap list will be automatically created or available for export.</span></span>
<p><span data-ttu-id="6248e-124"><strong>Obs!</strong> Den här funktionen hade tidigare ersatts av Microsoft Azure DevOps-integreringar.</span><span class="sxs-lookup"><span data-stu-id="6248e-124"><strong>Note:</strong> This feature had previously been deprecated and replaced by Microsoft Azure DevOps integrations.</span></span></p>
</li>
<li><span data-ttu-id="6248e-125">Versionshistoriken för flödesschemat kommer inte att vara tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="6248e-125">The version history of the flowchart will be unavailable.</span></span></li>
</ul>
</td>
</tr>
</tbody>
</table>
