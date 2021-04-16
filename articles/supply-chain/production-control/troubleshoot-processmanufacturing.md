---
title: Felsöka processtillverkning
description: I det här avsnittet beskrivs hur du åtgärdar problem som kan uppstå när du arbetar med processtillverkning.
author: SmithaNataraj
ms.date: 11/04/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: smnatara
ms.search.validFrom: 2020-11-04
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 938820b6cd2bb470b440fea7b70124efc0faf7f8
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5825000"
---
# <a name="troubleshoot-process-manufacturing"></a><span data-ttu-id="75604-103">Felsöka processtillverkning</span><span class="sxs-lookup"><span data-stu-id="75604-103">Troubleshoot process manufacturing</span></span>

<span data-ttu-id="75604-104">I det här avsnittet beskrivs hur du åtgärdar problem som kan uppstå när du arbetar med processtillverkning.</span><span class="sxs-lookup"><span data-stu-id="75604-104">This topic describes how to fix issues that you might encounter while you work with process manufacturing.</span></span>

## <a name="when-i-use-the-job-card-device-to-report-a-partial-quantity-on-the-last-job-in-a-production-order-all-the-previous-jobs-on-that-order-that-have-a-status-of-in-progress-are-automatically-ended"></a><span data-ttu-id="75604-105">När jag använder jobbkortsenheten för att rapportera en delkvantitet för det sista jobbet i en tillverkningsorder, avslutas automatiskt alla tidigare jobb på den ordern som har statusen pågår.</span><span class="sxs-lookup"><span data-stu-id="75604-105">When I use the job card device to report a partial quantity on the last job in a production order, all the previous jobs on that order that have a status of In progress are automatically ended.</span></span>

<span data-ttu-id="75604-106">Detta beteende är av design.</span><span class="sxs-lookup"><span data-stu-id="75604-106">This behavior is by design.</span></span> <span data-ttu-id="75604-107">På sidan **Standarder för produktionsorde** på fliken **Rapportera som färdigt** finns ett alternativ som heter **Slutmarkera flöde**.</span><span class="sxs-lookup"><span data-stu-id="75604-107">On the **Production order defaults** page, on the **Report as finished** tab, there is an option that is named **End-mark route**.</span></span> <span data-ttu-id="75604-108">Om det här avsnittet är inställt på *Ja*, bokförs en flödeskortjournal när en arbetare använder jobbkortsenhet eller jobbkortsterminal för att rapportera den senaste operationen.</span><span class="sxs-lookup"><span data-stu-id="75604-108">If this topic is set to *Yes*, a route card journal is posted when a worker uses the job card device or job card terminal to report the last operation.</span></span> <span data-ttu-id="75604-109">Den här journalen markerar alla operationer som slutförda och avslutar alla produktionsjobb.</span><span class="sxs-lookup"><span data-stu-id="75604-109">This journal marks all the operations as completed and ends all the production jobs.</span></span> <span data-ttu-id="75604-110">När alternativet **Slutmarkera flöde** anges till *Ja* tar systemet inte hänsyn till jobbstatus som den anställde valde när de rapporterade den senaste operationen.</span><span class="sxs-lookup"><span data-stu-id="75604-110">When the **End-mark route** option is set to *Yes*, the system doesn't consider the job status that the worker selected when they reported the last operation.</span></span> <span data-ttu-id="75604-111">Systemet betraktar inte heller om arbetaren rapporterar en fullständig eller partiell kvantitet.</span><span class="sxs-lookup"><span data-stu-id="75604-111">The system also doesn't consider whether the worker is reporting a full or partial quantity.</span></span>

## <a name="when-i-attempt-a-stock-closing-i-receive-the-following-warning-message-no-execution-of-backflush-costing-calculation-with-a-date-1-matching-period-end-has-been-registered"></a><span data-ttu-id="75604-112">När jag försöker stänga aktier får jag följande varningsmeddelande: "Inget utförande av kostnadskalkylering med automatisk lageravräkning med datum %1 matchningsperiodens slut har registrerats".</span><span class="sxs-lookup"><span data-stu-id="75604-112">When I attempt a stock closing, I receive the following warning message: "No execution of Backflush costing calculation with a date %1 matching period end has been registered."</span></span>

<span data-ttu-id="75604-113">I versioner före release 10.0.13 får du följande felaktiga varningsmeddelande under lagerstängning om du inte använder det lean produktionskostnadsflödet:</span><span class="sxs-lookup"><span data-stu-id="75604-113">In releases before release 10.0.13, if you aren't using the lean production costing flow, you receive the following erroneous warning message during inventory closing:</span></span>

> <span data-ttu-id="75604-114">Du utför en lagerstängning med ett datum %1.</span><span class="sxs-lookup"><span data-stu-id="75604-114">You are about to execute an Inventory close with a date %1.</span></span> <span data-ttu-id="75604-115">Ingen kostnadskalkylering med automatisk lageravräkning med datum %1 matchningsperiodens slut har registrerats.</span><span class="sxs-lookup"><span data-stu-id="75604-115">No execution of Backflush costing calculation with a date %1 matching period end has been registered.</span></span> <span data-ttu-id="75604-116">Kom ihåg att utföra en kostnadskalkylering med automatisk lageravräkning med datum %1 matchningsperiodens slut.</span><span class="sxs-lookup"><span data-stu-id="75604-116">Please remember to execute a Backflush costing calculation with a date of %1 matching period end.</span></span> <span data-ttu-id="75604-117">Värderingen av lager, sålda varor och avvikelser kan inte vara korrekt i delredovisning eller redovisning förrän denna har utförts.</span><span class="sxs-lookup"><span data-stu-id="75604-117">The valuation of inventories, cost of goods sold and variances might not be correct in Subledger or General ledger until this has been executed.</span></span>

<span data-ttu-id="75604-118">Det här problemet har korrigerats i version 10.0.13 och senare.</span><span class="sxs-lookup"><span data-stu-id="75604-118">This issue has been fixed in release 10.0.13 and later.</span></span> <span data-ttu-id="75604-119">Mer information finns i [KB 4582468](https://fix.lcs.dynamics.com/Issue/Details?kb=4582468&bugId=468844&dbType=3&qc=fcd64080446a27382cfde3e4c3bdcfb714279185932259cd11ceb0d500617296).</span><span class="sxs-lookup"><span data-stu-id="75604-119">For more information, see [KB 4582468](https://fix.lcs.dynamics.com/Issue/Details?kb=4582468&bugId=468844&dbType=3&qc=fcd64080446a27382cfde3e4c3bdcfb714279185932259cd11ceb0d500617296).</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]