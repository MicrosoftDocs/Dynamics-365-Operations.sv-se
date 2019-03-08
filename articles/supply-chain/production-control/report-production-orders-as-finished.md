---
title: Rapportera produktionsorder som färdiga
description: Rapportera som färdig är en produktionsfas. I detta skede rapporteras färdiga produkter och flyttas från produktionsordern till lagret.
author: johanhoffmann
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProdJournalTransJob, ProdJournalTransProd, ProdJournalTransRoute, ProdParmReportFinished, ProdRouteOprOverview
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 27061
ms.assetid: 1c2dfc54-a293-49f2-9b96-5a912ac5762c
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 61c12ee3a831abcb46af18645eba55fe100c99c9
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2019
ms.locfileid: "315830"
---
# <a name="report-production-orders-as-finished"></a><span data-ttu-id="e7e6a-104">Rapportera produktionsorder som färdiga</span><span class="sxs-lookup"><span data-stu-id="e7e6a-104">Report production orders as finished</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="e7e6a-105">Rapportera som färdig är en produktionsfas.</span><span class="sxs-lookup"><span data-stu-id="e7e6a-105">Report as finished is a production stage.</span></span> <span data-ttu-id="e7e6a-106">I detta skede rapporteras färdiga produkter och flyttas från produktionsordern till lagret.</span><span class="sxs-lookup"><span data-stu-id="e7e6a-106">At this stage, a finished product is reported and moved from the production order to the inventory.</span></span>

<span data-ttu-id="e7e6a-107">När kvantiteten på de slutförda varorna rapporteras som färdig på en produktionsorder, uppdateras den som lagerbehållning.</span><span class="sxs-lookup"><span data-stu-id="e7e6a-107">When a quantity of the finished goods is reported as finished on a production order it is updated as on-hand in the inventory.</span></span> <span data-ttu-id="e7e6a-108">Delvisa kvantiteter av den ursprungligen planerade orderkvantiteten kan rapporteras som färdiga.</span><span class="sxs-lookup"><span data-stu-id="e7e6a-108">Partial quantities of the originally planned order quantity can be reported as finished.</span></span> <span data-ttu-id="e7e6a-109">Det går också att rapportera felkvantiteter med ett associerat fel när du rapporterar kvantiteter som färdiga.</span><span class="sxs-lookup"><span data-stu-id="e7e6a-109">It is also possible to report error quantities with an associated error reason when reporting quantities as finished.</span></span> <span data-ttu-id="e7e6a-110">När produktionsordern når fasen Rapporterad som färdig innebär det att ingen mer kvantitet på tillverkningsordern ska rapporteras.</span><span class="sxs-lookup"><span data-stu-id="e7e6a-110">When the production order reach the stage Reported as finished it indicates that no more quantity is going to be reported at the production  order.</span></span>
<span data-ttu-id="e7e6a-111">Följande egenskaper associeras också med processen **Rapportera som färdig**:</span><span class="sxs-lookup"><span data-stu-id="e7e6a-111">The following characteristics are also associated with the **Report as finished** process:</span></span>
-   <span data-ttu-id="e7e6a-112">Det går att ställa in förbrukning av råmaterial och tid som är proportionerlig till den rapporterade kvantiteten (bakåtavräkning)</span><span class="sxs-lookup"><span data-stu-id="e7e6a-112">It is possible to set up consumption of raw material and time that are proportional to the reported quantity (back-flushing)</span></span>
-   <span data-ttu-id="e7e6a-113">Inlagrat arbete kan skapas för artiklar som aktiveras för lagerställeprocesser.</span><span class="sxs-lookup"><span data-stu-id="e7e6a-113">Put-away work can be generated for items that are enabled for warehouse processes.</span></span>
-   <span data-ttu-id="e7e6a-114">Det planerade eller standardkostnadsvärdet för de färdiga varorna kan ställas in att rapporteras på huvudbokskonton.</span><span class="sxs-lookup"><span data-stu-id="e7e6a-114">The planned or standard cost value of the finished goods can be set up to be reported to ledger accounts.</span></span>
-   <span data-ttu-id="e7e6a-115">En kvalitetsorder kan skapas för den rapporterade kvantiteten baserat på inställningarna för en kvalitetsassociation.</span><span class="sxs-lookup"><span data-stu-id="e7e6a-115">A quality order can be created for the reported quantity based on the setup of a quality association.</span></span>

<span data-ttu-id="e7e6a-116">Kvantiteten rapporteras till utleveransplatsen.</span><span class="sxs-lookup"><span data-stu-id="e7e6a-116">The quantity is reported to the output location.</span></span> <span data-ttu-id="e7e6a-117">Lagerställearbete genereras sedan för att flytta kvantiteten från utleveransplatsen till dess slutmål som definieras av platsdirektivet för platsarbete.</span><span class="sxs-lookup"><span data-stu-id="e7e6a-117">Warehouse work is then generated to move the quantity from the output location to its final destination defined by the location directive for the put-away work.</span></span>

-   <span data-ttu-id="e7e6a-118">En kvalitetsorder kan skapas när en produktionsorder rapporteras som färdig om en kvalitetsassociation har ställts in.</span><span class="sxs-lookup"><span data-stu-id="e7e6a-118">A quality order can be created when a production order is reported as finished if a quality association has been set up.</span></span>

## <a name="set-a-production-order-to-reporting-as-finished"></a><span data-ttu-id="e7e6a-119">Ställ in en produktionsorder till Rapportering som färdig</span><span class="sxs-lookup"><span data-stu-id="e7e6a-119">Set a production order to Reporting as finished</span></span>
<span data-ttu-id="e7e6a-120">Du kan ställa in en produktionsorder som **Rapportera som färdig** genom uppdateringsfunktionen för produktionsorder eller via journalen **Rapportera som färdig**.</span><span class="sxs-lookup"><span data-stu-id="e7e6a-120">You can set a production order to **Report as finished** through the standard production order update function, or through the route and job card journals, or through the journal **Report as finished**.</span></span> <span data-ttu-id="e7e6a-121">Du kan även uppdatera fasen till **Rapportera som färdig** via sidorna för jobbkortterminal och jobbkortenhet när du rapporterar på det sista jobbet för produktionsordern.</span><span class="sxs-lookup"><span data-stu-id="e7e6a-121">You can also update the stage to **Report as finished** through the job card terminal and job card device pages, when you report on the last job of the production order.</span></span> <span data-ttu-id="e7e6a-122">Slutligen kan du aktivera alternativet **Rapportera som färdig** som en process för lösningen för den handhållna lagerställeenheten.</span><span class="sxs-lookup"><span data-stu-id="e7e6a-122">Finally, you can enable the **Report as finished** option as a process for the handheld warehouse device solution.</span></span>  



