---
title: Du får ett felmeddelande när du kör den inbyggda huvudplaneringsmotorn
description: När du kör den inaktuella inbyggda huvudplaneringsmotorn får du ett felmeddelande.
author: ankubik
ms.date: 06/10/2021
ms.topic: troubleshooting
ms.search.form: Dialog_ReqCalcScheduleItemTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: ankubik
ms.search.validFrom: 2021-06-10
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 9c950292a4f43319d21a7deafdfb341b7bef15d8
ms.sourcegitcommit: 18ca2df785e9656fdd4e8c0734eca2b2624fda10
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/22/2021
ms.locfileid: "6294183"
---
# <a name="you-receive-an-error-when-running-the-built-in-master-planning-engine"></a><span data-ttu-id="56392-103">Du får ett felmeddelande när du kör den inbyggda huvudplaneringsmotorn</span><span class="sxs-lookup"><span data-stu-id="56392-103">You receive an error when running the built-in master planning engine</span></span>

<span data-ttu-id="56392-104">Felkod: ReqCalcScheduleItemTablePlanningOptimizationFitError</span><span class="sxs-lookup"><span data-stu-id="56392-104">Error code: ReqCalcScheduleItemTablePlanningOptimizationFitError</span></span>

## <a name="symptoms"></a><span data-ttu-id="56392-105">Symtom</span><span class="sxs-lookup"><span data-stu-id="56392-105">Symptoms</span></span>

<span data-ttu-id="56392-106">När du kör huvudplanering med den inbyggda huvudplaneringsmotorn får du följande felmeddelande:</span><span class="sxs-lookup"><span data-stu-id="56392-106">When you run master planning by using the deprecated built-in master planning engine, you receive the following error message:</span></span>

> <span data-ttu-id="56392-107">Det här felmeddelandet visas eftersom den inbyggda huvudplaneringsmotorn användes för scenarier som stöds vid planeringsoptimering.</span><span class="sxs-lookup"><span data-stu-id="56392-107">You receive this error message because the built-in master planning engine was used for scenarios supported by Planning Optimization.</span></span> <span data-ttu-id="56392-108">Du bör migrera till planeringsoptimering nu eftersom den aktuella inbyggda huvudplaneringen är föråldrad.</span><span class="sxs-lookup"><span data-stu-id="56392-108">You should migrate to Planning Optimization now, as the current built-in master planning will be deprecated.</span></span> <span data-ttu-id="56392-109">Observera att huvudplaneringskörningen slutfördes utan fel.</span><span class="sxs-lookup"><span data-stu-id="56392-109">Note that this master planning run did complete successfully.</span></span> <span data-ttu-id="56392-110">Om migreringen har starka beroenden på väntande funktioner kan det krävas ett undantag till fortsatt användning av den inbyggda huvudplaneringsmotorn.</span><span class="sxs-lookup"><span data-stu-id="56392-110">In case your migration has strong dependencies on pending features, an exception to continued usage of the built-in master planning engine can be requested.</span></span> <span data-ttu-id="56392-111">Fyll i följande enkät för att komma igång och om relevant undantag från migreringen till planeringsoptimering.</span><span class="sxs-lookup"><span data-stu-id="56392-111">Please complete the following questionnaire to get started and, if relevant, request an exception from migration to Planning Optimization.</span></span> [<span data-ttu-id="56392-112">Planera optimeringsmigrering och undantagsenkät</span><span class="sxs-lookup"><span data-stu-id="56392-112">Planning Optimization migration and exception questionnaire</span></span>](https://go.microsoft.com/fwlink/?linkid=2144962)

## <a name="cause"></a><span data-ttu-id="56392-113">Orsak</span><span class="sxs-lookup"><span data-stu-id="56392-113">Cause</span></span>

<span data-ttu-id="56392-114">Om du kör planering och inte använder produktionskontrollfunktioner bör du migrera till Planeringsoptimering.</span><span class="sxs-lookup"><span data-stu-id="56392-114">If you run planning and don't use production control features, you should consider migrating to Planning Optimization.</span></span> <span data-ttu-id="56392-115">Den inbyggda huvudplaneringsmotorn avaktiveras.</span><span class="sxs-lookup"><span data-stu-id="56392-115">The built-in master planning engine is being deprecated.</span></span> <span data-ttu-id="56392-116">Om du vill fortsätta att använda det utan att få felmeddelandet måste du därför ansöka om ett undantag från Microsoft.</span><span class="sxs-lookup"><span data-stu-id="56392-116">Therefore, if you want to continue to use it without receiving the error message, you must apply for an exception from Microsoft.</span></span>

## <a name="resolution"></a><span data-ttu-id="56392-117">Lösning</span><span class="sxs-lookup"><span data-stu-id="56392-117">Resolution</span></span>

<span data-ttu-id="56392-118">Mer information om hur du migrerar till Planeringsoptimering eller hur du ansöker om ett undantag så att du kan fortsätta att använda den inbyggda planeringsmotorn som avaktiveras finns i [Migrering till planeringsoptimering för huvudplanering](/dynamics365/supply-chain/master-planning/new-master-planning-engine).</span><span class="sxs-lookup"><span data-stu-id="56392-118">For more information about how to migrate to Planning Optimization, or how to apply for an exception so that you can continue to use the deprecated built-in planning engine instead, see [Migration to Planning Optimization for master planning](/dynamics365/supply-chain/master-planning/new-master-planning-engine).</span></span>
