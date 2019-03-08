---
title: Produktionsåterrapportering
description: Den här artikeln innehåller information om produktionsåterrapportering, som ger arbetarna återrapportering om produktionsjobb. Artikeln innehåller information om de olika sätten att uppdatera produktionsåterrapportering.
author: johanhoffmann
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: JmgRegistration, ProdJournalTransJob, ProdJournalTransRoute, ProdParmReportFinished
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 19351
ms.assetid: bcc9e242-b4b8-4144-b14d-c3c106fb40ec
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5b0a49cf05a7eee838dcf9fb699d273d0f7518a1
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2019
ms.locfileid: "340923"
---
# <a name="production-feedback"></a><span data-ttu-id="d7c5c-104">Produktionsåterrapportering</span><span class="sxs-lookup"><span data-stu-id="d7c5c-104">Production feedback</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="d7c5c-105">Den här artikeln innehåller information om produktionsåterrapportering, som ger arbetarna återrapportering om produktionsjobb.</span><span class="sxs-lookup"><span data-stu-id="d7c5c-105">This article provides information about production feedback, which gives workers feedback about production jobs.</span></span> <span data-ttu-id="d7c5c-106">Artikeln innehåller information om de olika sätten att uppdatera produktionsåterrapportering.</span><span class="sxs-lookup"><span data-stu-id="d7c5c-106">The article includes information about the various ways that production feedback can be updated.</span></span>

<span data-ttu-id="d7c5c-107">Produktionåterkoppling ger arbetarna återrapportering om produktionsjobb.</span><span class="sxs-lookup"><span data-stu-id="d7c5c-107">Production feedback gives workers feedback about production jobs.</span></span> <span data-ttu-id="d7c5c-108">Den registrerar materialförbrukning och produktionsorder, operationskvantiteter och status och fel som orsakar att ett jobb eller en operation misslyckas.</span><span class="sxs-lookup"><span data-stu-id="d7c5c-108">It records time and material consumption on production orders, operation quantities and status, and errors that cause a job or operation to fail.</span></span> <span data-ttu-id="d7c5c-109">Produktionåterkoppling kan uppdateras i journaler som är relaterade till produktionsorder.</span><span class="sxs-lookup"><span data-stu-id="d7c5c-109">Production feedback can be updated in journals that are related to production orders.</span></span> <span data-ttu-id="d7c5c-110">Journalerna **Produktionsjobbkort** och **Produktionsflödekort** används för att rapportera tid och kvantiteter per jobb eller operation.</span><span class="sxs-lookup"><span data-stu-id="d7c5c-110">The **Production job card** and **Production route card** journals are used to report time and quantities per job or operation.</span></span> <span data-ttu-id="d7c5c-111">För att rapportera om det sista jobbet eller operationen kan kvantiteter i den färdiga produkten rapporteras som slutförda.</span><span class="sxs-lookup"><span data-stu-id="d7c5c-111">For reporting about the last job or operation, quantities on the finished product can be reported as finished.</span></span> <span data-ttu-id="d7c5c-112">Produktionåterkoppling kan också uppdateras på sidorna **Jobbkortterminal** och **Jobbkortenhet**.</span><span class="sxs-lookup"><span data-stu-id="d7c5c-112">Production feedback can also be updated on the **Job card terminal** and **Job card device** pages.</span></span> <span data-ttu-id="d7c5c-113">Dessa sidor låter produktionsåterrapportering uppdateras på tillverkningsstället, och ingår i funktionen tillverkningskörning i modulen **Produktionskontroll**.</span><span class="sxs-lookup"><span data-stu-id="d7c5c-113">These pages enable production feedback to be updated on the shop floor and are part of the manufacturing execution functionality in the **Production control** module.</span></span> <span data-ttu-id="d7c5c-114">Sidan**Jobbkortterminal** har ett konfigurerbart användargränssnitt som visar en lista med de frisläppta jobben i en prioriterad order för ett valt arbetsområde.</span><span class="sxs-lookup"><span data-stu-id="d7c5c-114">The **Job card terminal** page has a configurable user interface that shows a list of the released jobs in a prioritized order for a selected work area.</span></span> <span data-ttu-id="d7c5c-115">Den erbjuder även avancerade alternativ som till exempel buntning av jobb och teamarbete.</span><span class="sxs-lookup"><span data-stu-id="d7c5c-115">It also offers advanced options such as job bundling and team work.</span></span> <span data-ttu-id="d7c5c-116">Sidan **Jobbkortenhet** har ett pekvänligt användargränssnitt.</span><span class="sxs-lookup"><span data-stu-id="d7c5c-116">The **Job card device** page has a touch-optimized user interface.</span></span> <span data-ttu-id="d7c5c-117">Produktionåterkoppling på båda sidorna uppdateras från produktionsjournalerna.</span><span class="sxs-lookup"><span data-stu-id="d7c5c-117">Production feedback on both pages is updated from the production journals.</span></span>



