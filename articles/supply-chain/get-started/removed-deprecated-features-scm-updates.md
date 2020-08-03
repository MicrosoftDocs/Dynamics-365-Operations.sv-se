---
title: Borttagna och utfasade funktioner i Dynamics 365 Supply Chain Management
description: I det här avsnittet beskrivs funktioner som har tagits bort, eller har planerats för borttagning i Dynamics 365 Supply Chain Management.
author: kamaybac
manager: tfehr
ms.date: 04/30/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2020-03-03
ms.dyn365.ops.version: Platform update 33
ms.openlocfilehash: 07f37488747766dcca96884e204339b425bbd201
ms.sourcegitcommit: f64fce03ec52f844b05a9e8cac286cb201385002
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/16/2020
ms.locfileid: "3597126"
---
# <a name="removed-or-deprecated-features-in-dynamics-365-supply-chain-management"></a><span data-ttu-id="8bfd1-103">Borttagna och utfasade funktioner i Dynamics 365 Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="8bfd1-103">Removed or deprecated features in Dynamics 365 Supply Chain Management</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="8bfd1-104">Det här ämnet kommer att uppdateras när nya borttagna eller inaktuella funktioner dokumenteras för Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="8bfd1-104">This topic will be updated as new removed or deprecated features are documented for Dynamics 365 Supply Chain Management.</span></span>

- <span data-ttu-id="8bfd1-105">En *borttagen* funktion är inte längre tillgänglig i produkten.</span><span class="sxs-lookup"><span data-stu-id="8bfd1-105">A *removed* feature is no longer available in the product.</span></span>
- <span data-ttu-id="8bfd1-106">En *borttagen* funktion är inte i aktiv utveckling och kan tas bort i en kommande uppdatering.</span><span class="sxs-lookup"><span data-stu-id="8bfd1-106">A *deprecated* feature is not in active development and may be removed in a future update.</span></span>

<span data-ttu-id="8bfd1-107">Den här listan är avsedd att hjälpa dig att ta hänsyn till dessa borttagna och inaktuella funktioner för din planerings skull.</span><span class="sxs-lookup"><span data-stu-id="8bfd1-107">This list is intended to help you consider these removals and deprecations for your own planning.</span></span>

> [!NOTE]
> <span data-ttu-id="8bfd1-108">Detaljerad information om objekt i Finance and Operations-appar hittas i [Tekniska referensrapporter](https://mbs.microsoft.com/customersource/northamerica/AX/downloads/reports/axtechrefrep).</span><span class="sxs-lookup"><span data-stu-id="8bfd1-108">Detailed information about objects in Finance and Operations apps can be found in the [Technical reference reports](https://mbs.microsoft.com/customersource/northamerica/AX/downloads/reports/axtechrefrep).</span></span> <span data-ttu-id="8bfd1-109">Du kan jämföra olika versioner av rapporterna för mer information om objekt som har ändrats eller tagits bort i varje version av Finance and Operations-appar.</span><span class="sxs-lookup"><span data-stu-id="8bfd1-109">You can compare the different versions of these reports to learn about objects that have changed or been removed in each version of Finance and Operations apps.</span></span>

## <a name="features-removed-or-deprecated-in-the-supply-chain-management-10011-release"></a><span data-ttu-id="8bfd1-110">Borttagna eller föråldrade funktioner i Supply Chain Management version 10.0.11</span><span class="sxs-lookup"><span data-stu-id="8bfd1-110">Features removed or deprecated in the Supply Chain Management 10.0.11 release</span></span>

### <a name="use-of-built-in-supply-chain-management-master-planning-engine-for-distribution-scenarios"></a><span data-ttu-id="8bfd1-111">Användning av den inbyggda huvudplaneringsmotorn för Supply Chain Management för distributionsscenarier</span><span class="sxs-lookup"><span data-stu-id="8bfd1-111">Use of built-in Supply Chain Management master planning engine for distribution scenarios</span></span>

|   |  |
|------------|--------------------|
| <span data-ttu-id="8bfd1-112">**Orsak till inaktuell/borttagning**</span><span class="sxs-lookup"><span data-stu-id="8bfd1-112">**Reason for deprecation/removal**</span></span> | <span data-ttu-id="8bfd1-113">För att förbättra prestanda och minimera inläsning av SQL-databas under huvudplaneringskörning, ersätts den inbyggda huvudplaneringsmotorn för Supply Chain Management med planeringsoptimering.</span><span class="sxs-lookup"><span data-stu-id="8bfd1-113">To enhance performance and minimize the SQL database load during master planning runs, the built-in Supply Chain Management master planning engine is being replaced by Planning Optimization.</span></span> <span data-ttu-id="8bfd1-114">Planeringsoptimering möjliggör snabba planeringskörningar som kan utföras även under kontorstid.</span><span class="sxs-lookup"><span data-stu-id="8bfd1-114">Planning Optimization allows for fast planning runs that can be performed even during office hours.</span></span> <span data-ttu-id="8bfd1-115">Då kan planeraren omedelbart reagera vid ändringar i efterfrågan eller planeringsparametrar.</span><span class="sxs-lookup"><span data-stu-id="8bfd1-115">This enables planners to react immediately to changes in demand or planning parameters.</span></span> |
| <span data-ttu-id="8bfd1-116">**Ersatt av en annan funktion?**</span><span class="sxs-lookup"><span data-stu-id="8bfd1-116">**Replaced by another feature?**</span></span>   | <span data-ttu-id="8bfd1-117">Ja, planeringsoptimering kommer att ersätta befintliga inbyggda huvudplaneringsmotorn för Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="8bfd1-117">Yes, Planning Optimization will replace the existing built-in Supply Chain Management master planning engine.</span></span> |
| <span data-ttu-id="8bfd1-118">**Produktområden som påverkas**</span><span class="sxs-lookup"><span data-stu-id="8bfd1-118">**Product areas affected**</span></span>         | <span data-ttu-id="8bfd1-119">Supply Chain Management – Huvudplanering</span><span class="sxs-lookup"><span data-stu-id="8bfd1-119">Supply Chain Management - Master planning</span></span> |
| <span data-ttu-id="8bfd1-120">**Distribueringsalternativ**</span><span class="sxs-lookup"><span data-stu-id="8bfd1-120">**Deployment option**</span></span>              | <span data-ttu-id="8bfd1-121">Endast i molnet.</span><span class="sxs-lookup"><span data-stu-id="8bfd1-121">Cloud only.</span></span> <span data-ttu-id="8bfd1-122">Planeringsoptimering stöds inte för lokala distributioner.</span><span class="sxs-lookup"><span data-stu-id="8bfd1-122">Planning Optimization is not supported with on-premises deployments.</span></span> |
| <span data-ttu-id="8bfd1-123">**Status**</span><span class="sxs-lookup"><span data-stu-id="8bfd1-123">**Status**</span></span>                         | <span data-ttu-id="8bfd1-124">Inaktuell.</span><span class="sxs-lookup"><span data-stu-id="8bfd1-124">Deprecated.</span></span> <span data-ttu-id="8bfd1-125">April 2021 kommer distributionsscenarier inte längre att stödjas med inbyggda Dynamics 365 Supply Chain Management huvudplaneringsmotor.</span><span class="sxs-lookup"><span data-stu-id="8bfd1-125">On April 2021, distribution scenarios will no longer be supported with the built-in Dynamics 365 Supply Chain Management master planning engine.</span></span> <span data-ttu-id="8bfd1-126">För distributionsscenarier måste kunder använda planeringsoptimering för huvudplanering.</span><span class="sxs-lookup"><span data-stu-id="8bfd1-126">For distribution scenarios, customers must use Planning Optimization for master planning calculations.</span></span> <span data-ttu-id="8bfd1-127">Mer information finns i [dokumentationen för planeringsoptimering](https://go.microsoft.com/fwlink/?linkid=2105830).</span><span class="sxs-lookup"><span data-stu-id="8bfd1-127">For more information, see [Planning Optimization documentation](https://go.microsoft.com/fwlink/?linkid=2105830).</span></span> <span data-ttu-id="8bfd1-128">Kunder med lokala distributioner av Dynamics 365 Supply Chain Management kan fortsätta att använda Supply Chain Managements huvudplaneringsmotor för distributionsscenarier efter april 2021.</span><span class="sxs-lookup"><span data-stu-id="8bfd1-128">Customers with on-premises deployments of Dynamics 365 Supply Chain Management may continue to use the Supply Chain Management master planning engine for distribution scenarios after April 2021.</span></span> <span data-ttu-id="8bfd1-129">Det sker dock inga fler förbättringar av funktionen.</span><span class="sxs-lookup"><span data-stu-id="8bfd1-129">However, no more feature enhancements will be provided.</span></span> |

## <a name="previous-announcements-about-removed-or-deprecated-features"></a><span data-ttu-id="8bfd1-130">Tidigare meddelanden om borttagna eller inaktuella funktioner</span><span class="sxs-lookup"><span data-stu-id="8bfd1-130">Previous announcements about removed or deprecated features</span></span>

<span data-ttu-id="8bfd1-131">Om du vill veta mer om funktioner som har tagits bort eller ersatts i tidigare versioner, se [borttagna eller inaktuella funktioner i tidigare versioner](../../fin-ops-core/dev-itpro/migration-upgrade/deprecated-features.md).</span><span class="sxs-lookup"><span data-stu-id="8bfd1-131">To learn more about features that have been removed or deprecated in previous releases, see [Removed or deprecated features in previous releases](../../fin-ops-core/dev-itpro/migration-upgrade/deprecated-features.md).</span></span>
