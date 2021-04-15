---
title: Frisläpp produktionsorder
description: En frisläppt produktionsorder är en order som har auktoriserats för tillverkning. Termen frisläppt används för att beskriva ett tillstånd i produktionsorderlivscykeln, där produktionsordern är tillgänglig för körning i produktionsarbete och för lagerställeprocesser.
author: johanhoffmann
ms.date: 03/02/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ProdParmRelease
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2414
ms.assetid: 50c2257b-2924-44f5-b7c1-11f498092053
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 118b0d6300647135b22e42cc84a79f07e48d7ef4
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5811712"
---
# <a name="release-production-orders"></a><span data-ttu-id="3d0f3-104">Frisläpp produktionsorder</span><span class="sxs-lookup"><span data-stu-id="3d0f3-104">Release production orders</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="3d0f3-105">En frisläppt produktionsorder är en order som har auktoriserats för tillverkning.</span><span class="sxs-lookup"><span data-stu-id="3d0f3-105">A released production order is an order that has been authorized for production.</span></span> <span data-ttu-id="3d0f3-106">Termen frisläppt används för att beskriva ett tillstånd i produktionsorderlivscykeln, där produktionsordern är tillgänglig för körning i produktionsarbete och för lagerställeprocesser.</span><span class="sxs-lookup"><span data-stu-id="3d0f3-106">The term Released is used to describe a state in the production order life cycle, where the production order is available for execution on the production shop floor and for warehouse processes.</span></span>

## <a name="characteristics-of-the-released-state"></a><span data-ttu-id="3d0f3-107">Egenskaper för det frisläppta tillståndet</span><span class="sxs-lookup"><span data-stu-id="3d0f3-107">Characteristics of the Released state</span></span>

<span data-ttu-id="3d0f3-108">**Frisläppt** tillstånd är ett tillstånd i produktionsorderns livscykel.</span><span class="sxs-lookup"><span data-stu-id="3d0f3-108">The **Released** state is one state in the production order life cycle.</span></span> <span data-ttu-id="3d0f3-109">Produktionsorder som är i **Frisläppt** tillstånd är tillgängliga för körning på produktionsarbete och lagerställeprocesser.</span><span class="sxs-lookup"><span data-stu-id="3d0f3-109">Production orders that are in the **Released** state are available for execution on the production shop floor and for warehouse processes.</span></span> <span data-ttu-id="3d0f3-110">**Frisläppt** tillstånd har följande egenskaper:</span><span class="sxs-lookup"><span data-stu-id="3d0f3-110">The **Released** state has the following characteristics:</span></span>

- <span data-ttu-id="3d0f3-111">En produktionsorder kan ändras till **Frisläppt** tillstånd antingen från produktionsordern eller genom att använda en batchprocess.</span><span class="sxs-lookup"><span data-stu-id="3d0f3-111">A production order can be changed to the **Released** state either from the production order or by using a batch process.</span></span> <span data-ttu-id="3d0f3-112">Produktionsordern kan också uppdateras automatiskt från planerade produktionsorder som bekräftas med hjälp av fältet **Bekräfta tidsgräns** på sidan **Huvudplan**.</span><span class="sxs-lookup"><span data-stu-id="3d0f3-112">The production order can also be updated automatically from planned production orders that are firmed by using the **Firming time fence** field on the **Master plan** page.</span></span>
- <span data-ttu-id="3d0f3-113">**Frisläppt** tillstånd är signalen för fabriksoperatörerna att börja köra produktionsjobben i fabriken.</span><span class="sxs-lookup"><span data-stu-id="3d0f3-113">The **Released** state is the signal for the shop floor operators (operators) to start executing the production jobs on the shop floor.</span></span>
- <span data-ttu-id="3d0f3-114">Produktionsdokument som t.ex. flödeskort, flödesjobb och jobbkort innehåller information om produktionsjobb och kan utfärdas.</span><span class="sxs-lookup"><span data-stu-id="3d0f3-114">Production papers, such as route cards, route jobs, and jobs cards provide information about production jobs and can be issued.</span></span>
- <span data-ttu-id="3d0f3-115">För material som reserverats fysiskt genereras lagerställearbete för att plocka material för produktionsordern.</span><span class="sxs-lookup"><span data-stu-id="3d0f3-115">For materials that are physically reserved, warehouse work is generated to pick materials for the production order.</span></span>

## <a name="releasing-jobs-to-the-shop-floor"></a><span data-ttu-id="3d0f3-116">Frisläppning av jobb för fabriken</span><span class="sxs-lookup"><span data-stu-id="3d0f3-116">Releasing jobs to the shop floor</span></span>

<span data-ttu-id="3d0f3-117">När en produktionsorder har frisläppts visas produktionsjobb som hör till ordern och är redo att registreras.</span><span class="sxs-lookup"><span data-stu-id="3d0f3-117">After a production order is released, production jobs that are related to the order are visible and ready for registration.</span></span> <span data-ttu-id="3d0f3-118">Operatörerna kan göra jobbregistreringar, t ex Start, Stopp och Slutförande, på antingen sidan **Jobbkortterminal** eller sidan **Jobbkortenhet**.</span><span class="sxs-lookup"><span data-stu-id="3d0f3-118">The operators can make job registrations, such as Start, Stop, and Completion, on either the **Job card terminal** page or the **Job card device** page.</span></span> <span data-ttu-id="3d0f3-119">Registrerad tid och kvantitet överförs automatiskt från registreringssidorna till produktionsjournaler för att hålla reda på förbrukad tid och kvantitet.</span><span class="sxs-lookup"><span data-stu-id="3d0f3-119">The registered time and quantity are automatically transferred from the registration pages to production journals to keep track of the consumed time and quantity.</span></span>

## <a name="route-cards"></a><span data-ttu-id="3d0f3-120">Flödeskort</span><span class="sxs-lookup"><span data-stu-id="3d0f3-120">Route cards</span></span>

<span data-ttu-id="3d0f3-121">Ett flödeskort omfattar en översikt över informationen som kommer från flödet och operationsinställningarna samt från operations- och finplaneringsmetoderna.</span><span class="sxs-lookup"><span data-stu-id="3d0f3-121">A route card provides an overview of information that comes from route and operation setups, and from operation and job scheduling methods.</span></span>

## <a name="route-jobs"></a><span data-ttu-id="3d0f3-122">Flödesjobb</span><span class="sxs-lookup"><span data-stu-id="3d0f3-122">Route jobs</span></span>

<span data-ttu-id="3d0f3-123">Ett flödesjobb anger alla jobb i en operation i detalj och omfattar inställnings-, process-, kö- och transporttider.</span><span class="sxs-lookup"><span data-stu-id="3d0f3-123">A route job lists each job of an operation in detail, and includes setup, process, queue, and transportation times.</span></span> <span data-ttu-id="3d0f3-124">En operation som att måla kan till exempel kräva olika jobb som inställningstid, körtid för målningsprocessen och kötid för torkning.</span><span class="sxs-lookup"><span data-stu-id="3d0f3-124">For example, an operation such as painting might require individual jobs, such as setup time, run time for the painting process, and queue time for drying.</span></span>

## <a name="job-cards"></a><span data-ttu-id="3d0f3-125">Jobbkort</span><span class="sxs-lookup"><span data-stu-id="3d0f3-125">Job cards</span></span>

<span data-ttu-id="3d0f3-126">Ett jobbkort anger de enskilda jobbnumren för en viss operation.</span><span class="sxs-lookup"><span data-stu-id="3d0f3-126">A job card lists the individual job numbers of a particular operation.</span></span> <span data-ttu-id="3d0f3-127">Ett jobb visas på varje sida.</span><span class="sxs-lookup"><span data-stu-id="3d0f3-127">One job appears on each page.</span></span> <span data-ttu-id="3d0f3-128">De jobb som finns på ett jobbkort, och deras uppskattade tider, kommer från flödet och operationens inställningsinformation.</span><span class="sxs-lookup"><span data-stu-id="3d0f3-128">The jobs that are included on a job card, and their estimated times, come from the route and operation setup information.</span></span> <span data-ttu-id="3d0f3-129">Från ett jobbkort kan du öppna sidan **Produktionsjournalrader**, **jobbkort**.</span><span class="sxs-lookup"><span data-stu-id="3d0f3-129">From a job card, you can open the **Production journal lines**, **job card** page.</span></span> <span data-ttu-id="3d0f3-130">De som driver operationsresurser kan återrapportera om produktionsprocessen.</span><span class="sxs-lookup"><span data-stu-id="3d0f3-130">People who run operations resources can provide feedback about the production process.</span></span> <span data-ttu-id="3d0f3-131">Det finns fält där du kan ange förbrukningsstatistik och information som felkvantitet.</span><span class="sxs-lookup"><span data-stu-id="3d0f3-131">There are fields where you can enter consumption statistics and information such as the error quantity.</span></span>

## <a name="warehouse-work-for-raw-material-picking"></a><span data-ttu-id="3d0f3-132">Lagerställearbete för plockning av råmaterial.</span><span class="sxs-lookup"><span data-stu-id="3d0f3-132">Warehouse work for raw material picking</span></span>

<span data-ttu-id="3d0f3-133">Produkter för råvaraplockning genereras under leverans.</span><span class="sxs-lookup"><span data-stu-id="3d0f3-133">Work for raw material picking is generated during release.</span></span> <span data-ttu-id="3d0f3-134">Arbete genereras endast för mängden av material som fysiskt reserverats för tillverkningsordern innan ordern frisläpptes.</span><span class="sxs-lookup"><span data-stu-id="3d0f3-134">Work is generated only for the quantity of materials that was physically reserved for the production order before the order was released.</span></span> <span data-ttu-id="3d0f3-135">Följande inställningar krävs för att generera lagerarbete för plockning av råmaterial:</span><span class="sxs-lookup"><span data-stu-id="3d0f3-135">The following setup is required to generate warehouse work for raw material picking:</span></span>

- <span data-ttu-id="3d0f3-136">Ett platsdirektiv för plockning för råmaterial som bestämmer vilket lagerställen som materialet ska plockas i</span><span class="sxs-lookup"><span data-stu-id="3d0f3-136">A location directive for raw materials picking that determines which warehouse location to pick the materials in</span></span>
- <span data-ttu-id="3d0f3-137">En vågmall för råmaterial, där policyer för utförande av lagerställearbete konfigureras</span><span class="sxs-lookup"><span data-stu-id="3d0f3-137">A wave template for raw materials, where policies for the execution of warehouse work are configured</span></span>
- <span data-ttu-id="3d0f3-138">En produktionsinleverans som bestämmer var materialet ska placeras</span><span class="sxs-lookup"><span data-stu-id="3d0f3-138">A production input location that determines where materials are put</span></span>

<span data-ttu-id="3d0f3-139">När du använder licenskontrollerade platser kan du välja om den beställda kvantiteten eller hela den tillgängliga kvantiteten för artikeln ska plockas medan du bearbetar råmaterialplockningen.</span><span class="sxs-lookup"><span data-stu-id="3d0f3-139">When using license plate controlled locations, you can choose whether the ordered quantity or the full quantity available for the item should be picked while processing the raw material picking work.</span></span> <span data-ttu-id="3d0f3-140">Så här ställer du in alternativet:</span><span class="sxs-lookup"><span data-stu-id="3d0f3-140">To set this option:</span></span>

1. <span data-ttu-id="3d0f3-141">Gå till **Produktinformationshantering \> Produkter \> Frisläppta produkter** och öppna relevant objekt.</span><span class="sxs-lookup"><span data-stu-id="3d0f3-141">Go to **Product information management \> Products \> Released products** and open the relevant item.</span></span>
1. <span data-ttu-id="3d0f3-142">Expandera snabbfliken **Lagerställe**.</span><span class="sxs-lookup"><span data-stu-id="3d0f3-142">Expand the **Warehouse** FastTab.</span></span>
1. <span data-ttu-id="3d0f3-143">Välj ett av följande alternativ för fältet **Materialplockning i ID-nummerplatser**:</span><span class="sxs-lookup"><span data-stu-id="3d0f3-143">Select one of the following options for the  **Material picking in license plate locations** field:</span></span>
    - <span data-ttu-id="3d0f3-144">*Orderplockning*: bara den beställda kvantiteten ska plockas.</span><span class="sxs-lookup"><span data-stu-id="3d0f3-144">*Order picking*: Only the ordered quantity should be picked.</span></span>
    - <span data-ttu-id="3d0f3-145">*Mellanlagring*: När det är möjligt bör hela mängden som finns på ID-numret plockas.</span><span class="sxs-lookup"><span data-stu-id="3d0f3-145">*Staging*: Whenever possible, the full quantity available at the license plate should be picked.</span></span> <span data-ttu-id="3d0f3-146">För att en arbetare ska kunna plocka hela kvantiteten av ID-nummer får licensinnehavaren inte innehålla blandade artiklar och får inte ha blandade dimensioner.</span><span class="sxs-lookup"><span data-stu-id="3d0f3-146">For a worker to be able to pick the full license plate quantity, the license plate must not contain mixed items and must not have mixed dimensions.</span></span> <span data-ttu-id="3d0f3-147">Om ID-numret innehåller blandade dimensioner eller artiklar, fortsätter plockningen på samma sätt som om den angetts för *Orderplockning*.</span><span class="sxs-lookup"><span data-stu-id="3d0f3-147">If the license plate contains mixed dimensions or items, the pick will proceed as if it were set to *Order picking*.</span></span>

[!INCLUDE[footer-include](../../includes/footer-banner.md)]