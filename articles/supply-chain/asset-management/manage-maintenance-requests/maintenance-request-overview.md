---
title: Underhållsbegäranden
description: Det här avsnittet innehåller en översikt över hantering av underhållsbegäran i tillgångshantering.
author: josaw1
manager: tfehr
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetRequestTable, EntAssetRequestWorkspace, EntAssetRequestActivePart, EntAssetRequestWorkOrderActive, EntAssetRequestType, EntAssetRequestTableCreateWO, EntAssetRequestTableLookup, EntAssetRequestTableActivePart, EntAssetMobileRequestDetails
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 7038269c66092367a0faf147766cb45eb5364e1b
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "4437728"
---
# <a name="maintenance-requests"></a><span data-ttu-id="a2d40-103">Underhållsbegäranden</span><span class="sxs-lookup"><span data-stu-id="a2d40-103">Maintenance requests</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="a2d40-104">Underhållsbegäran är anteckningar eller deklarationer som skapas för att meddela en chef eller planerare att en tillgång kan kräva ett underhålls- eller reparationsjobb, men utan att skapa en arbetsorder.</span><span class="sxs-lookup"><span data-stu-id="a2d40-104">Maintenance requests are notes or declarations that are created to notify a manager or planner that an asset might require a maintenance or repair job, but without creating a work order.</span></span> <span data-ttu-id="a2d40-105">Om innehållet i en underhållsbegäran anses vara giltigt, kan en arbetsorder skapas baserat på underhållsbegäran.</span><span class="sxs-lookup"><span data-stu-id="a2d40-105">If the contents of a maintenance request are considered valid, a work order can then be created based on the maintenance request.</span></span>

<span data-ttu-id="a2d40-106">Underhållsbegäran kan skapas för alla tillgångar i tillgångshantering.</span><span class="sxs-lookup"><span data-stu-id="a2d40-106">Maintenance requests can be created for any asset in Asset Management.</span></span> <span data-ttu-id="a2d40-107">Olika typer av underhållsbegäran kan skapas, beroende på hur ditt företag använder underhållsbegäran.</span><span class="sxs-lookup"><span data-stu-id="a2d40-107">Various types of maintenance requests can be created, depending on how your company uses maintenance requests.</span></span> <span data-ttu-id="a2d40-108">Nedan följer några exempel:</span><span class="sxs-lookup"><span data-stu-id="a2d40-108">Here are some examples:</span></span>

- <span data-ttu-id="a2d40-109">Underhållsbegäranden</span><span class="sxs-lookup"><span data-stu-id="a2d40-109">Maintenance requests</span></span>
- <span data-ttu-id="a2d40-110">Anteckningar</span><span class="sxs-lookup"><span data-stu-id="a2d40-110">Notes</span></span>
- <span data-ttu-id="a2d40-111">Korrigeringar eller förbättringar</span><span class="sxs-lookup"><span data-stu-id="a2d40-111">Corrections or enhancements</span></span>
- <span data-ttu-id="a2d40-112">Investeringar</span><span class="sxs-lookup"><span data-stu-id="a2d40-112">Investments</span></span>
- <span data-ttu-id="a2d40-113">Depåreparation (den här typen används när du tar emot tillgångar från en annan plats så att du kan utföra ett underhålls- eller reparationsjobb och sedan returnera tillgången när jobbet har slutförts.)</span><span class="sxs-lookup"><span data-stu-id="a2d40-113">Depot repair (This type is used when you receive assets from another location so that you can do a maintenance or repair job, and you then return the asset after the job is completed.)</span></span>

## <a name="view-maintenance-requests"></a><span data-ttu-id="a2d40-114">Visa underhållsbegäranden</span><span class="sxs-lookup"><span data-stu-id="a2d40-114">View maintenance requests</span></span>

<span data-ttu-id="a2d40-115">Om du vill visa underhållsbegäran, välj **tillgångshantering** \> **allmänt** \> **underhållsbegäran** \> **alla underhållsbegäran**, **aktiva underhållsbegäran** eller **mina underhållsbegäran för funktionsplats**.</span><span class="sxs-lookup"><span data-stu-id="a2d40-115">To view maintenance requests, select **Asset management** \> **Common** \> **Maintenance requests** \> **All maintenance requests**, **Active maintenance requests**, or **My functional location maintenance requests**.</span></span> <span data-ttu-id="a2d40-116">Varje listsida visar en del av den information som är relaterad till en underhållsbegäran.</span><span class="sxs-lookup"><span data-stu-id="a2d40-116">Each list page shows some of the information that is related to a maintenance request.</span></span>

![Visa underhållsbegäranden](media/01-manage-maintenance-requests.png)

> [!NOTE]
> <span data-ttu-id="a2d40-118">Använd listsidan **mina underhållsbegäran för funktionsplats** för att visa en lista över underhållsbegäran som innehåller antingen funktionsplatser som du är relaterad till som en anställd eller tillgångar som är installerade på funktionsplatser som du relaterade till som arbetstagare.</span><span class="sxs-lookup"><span data-stu-id="a2d40-118">Use the **My functional location maintenance requests** list page to view a list of maintenance requests that contain either functional locations that you're related to as a worker or assets that are installed on functional locations that you're related to as a worker.</span></span> <span data-ttu-id="a2d40-119">(Information om hur du ställer in funktionsplatser på underhållsarbetare finns i [Underhållsarbetare och arbetargrupper](../setup-for-objects/workers-and-worker-groups.md).)</span><span class="sxs-lookup"><span data-stu-id="a2d40-119">(For information about how to set up functional locations on maintenance workers, see [Maintenance workers and worker groups](../setup-for-objects/workers-and-worker-groups.md).)</span></span>
> 
> <span data-ttu-id="a2d40-120">Även om kundkontoinformation är tillgänglig i tillgångsservicehantering (externt underhåll), är den inte tillgänglig i tillgångshantering (internt underhåll).</span><span class="sxs-lookup"><span data-stu-id="a2d40-120">Although customer account information is available in Asset Service Management (external maintenance), it isn't available in Asset Management (internal maintenance).</span></span>

<span data-ttu-id="a2d40-121">Om du vill öppna detaljvyn för en post väljer du listsidan **Alla underhållsbegäran** i rutnätsvyn och väljer en länk i kolumnen **Underhållsbegäran**.</span><span class="sxs-lookup"><span data-stu-id="a2d40-121">To open the details view of a record, on the **All maintenance requests** list page, in the grid view, select a link in the **Maintenance request** column.</span></span>

![Visa information om begäran av katalogunderhåll](media/02-manage-maintenance-requests.png)

<span data-ttu-id="a2d40-123">Knapparna i åtgärdsfönstret är ordnade på flikar.</span><span class="sxs-lookup"><span data-stu-id="a2d40-123">The buttons on the Action Pane are organized on tabs.</span></span> <span data-ttu-id="a2d40-124">I följande tabell beskrivs kortfattat knappar som är relaterade till tillgångshantering.</span><span class="sxs-lookup"><span data-stu-id="a2d40-124">The following table briefly describes the buttons that are related to Asset Management.</span></span>

| <span data-ttu-id="a2d40-125">Namn på knapp</span><span class="sxs-lookup"><span data-stu-id="a2d40-125">Button name</span></span>                      | <span data-ttu-id="a2d40-126">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="a2d40-126">Description</span></span> |
|----------------------------------|-------------|
| <span data-ttu-id="a2d40-127">Redigera</span><span class="sxs-lookup"><span data-stu-id="a2d40-127">Edit</span></span>                             | <span data-ttu-id="a2d40-128">Redigera den valda underhållsbegäran.</span><span class="sxs-lookup"><span data-stu-id="a2d40-128">Edit the selected maintenance request.</span></span> |
| <span data-ttu-id="a2d40-129">Nytt</span><span class="sxs-lookup"><span data-stu-id="a2d40-129">New</span></span>                              | <span data-ttu-id="a2d40-130">Skapa en ny underhållsbegäran.</span><span class="sxs-lookup"><span data-stu-id="a2d40-130">Create a new maintenance request.</span></span> |
| <span data-ttu-id="a2d40-131">Radera</span><span class="sxs-lookup"><span data-stu-id="a2d40-131">Delete</span></span>                           | <span data-ttu-id="a2d40-132">Radera vald underhållsbegäran.</span><span class="sxs-lookup"><span data-stu-id="a2d40-132">Delete the selected maintenance request.</span></span> |
| <span data-ttu-id="a2d40-133">Arbetsorderpool</span><span class="sxs-lookup"><span data-stu-id="a2d40-133">Work order pool</span></span>                  | <span data-ttu-id="a2d40-134">Anslut den valda underhållsbegäran till en arbetsorderpool.</span><span class="sxs-lookup"><span data-stu-id="a2d40-134">Connect the selected maintenance request to a work order pool.</span></span> |
| <span data-ttu-id="a2d40-135">Arbetsorder</span><span class="sxs-lookup"><span data-stu-id="a2d40-135">Work order</span></span>                       | <span data-ttu-id="a2d40-136">Skapa enarbetsorder baserad på den valda underhållsbegäran.</span><span class="sxs-lookup"><span data-stu-id="a2d40-136">Create a work order, based on the selected maintenance request.</span></span> |
| <span data-ttu-id="a2d40-137">Tillgångsfel</span><span class="sxs-lookup"><span data-stu-id="a2d40-137">Asset fault</span></span>                      | <span data-ttu-id="a2d40-138">Klicka **Tillgångsfel**, där du kan skapa en felregistrering på den valda underhållsbegäran.</span><span class="sxs-lookup"><span data-stu-id="a2d40-138">Click **Asset faults**, where you can create a fault registration on the selected maintenance request.</span></span> |
| <span data-ttu-id="a2d40-139">Arbetsorder</span><span class="sxs-lookup"><span data-stu-id="a2d40-139">Work orders</span></span>                      | <span data-ttu-id="a2d40-140">Visa en lista över alla arbetsorder som är kopplade till den valda underhållsbegäran.</span><span class="sxs-lookup"><span data-stu-id="a2d40-140">Show a list of all work orders that are connected to the selected maintenance request.</span></span> |
| <span data-ttu-id="a2d40-141">Uppdatera tillstånd för underhållsbegäran</span><span class="sxs-lookup"><span data-stu-id="a2d40-141">Update maintenance request state</span></span> | <span data-ttu-id="a2d40-142">Uppdatera tillstånd för underhållsbegäran</span><span class="sxs-lookup"><span data-stu-id="a2d40-142">Update the maintenance request state.</span></span> |
| <span data-ttu-id="a2d40-143">Logg för livscykeltillstånd</span><span class="sxs-lookup"><span data-stu-id="a2d40-143">Lifecycle state log</span></span>              | <span data-ttu-id="a2d40-144">Visa en logg som visar livscykeltillstånden för den valda underhållsbegäran.</span><span class="sxs-lookup"><span data-stu-id="a2d40-144">View a log that shows the lifecycle states of the selected maintenance request.</span></span> |
| <span data-ttu-id="a2d40-145">Information om underhållsbegäran</span><span class="sxs-lookup"><span data-stu-id="a2d40-145">Maintenance request details</span></span>      | <span data-ttu-id="a2d40-146">Skriv ut en rapport som visar information om den valda underhållsbegäran.</span><span class="sxs-lookup"><span data-stu-id="a2d40-146">Print a report that shows details of the selected maintenance request.</span></span> |
| <span data-ttu-id="a2d40-147">Skicka utlåningstillgång</span><span class="sxs-lookup"><span data-stu-id="a2d40-147">Send loan asset</span></span>                  | <span data-ttu-id="a2d40-148">Välj en utlåningstillgång som ska vara en temporär ersättning för tillgången som valts i den valda underhållsbegäran.</span><span class="sxs-lookup"><span data-stu-id="a2d40-148">Select a loan asset that should be a temporary replacement for the asset that is selected on the selected maintenance request.</span></span> |
| <span data-ttu-id="a2d40-149">Lämna tillbaka utlåningstillgång</span><span class="sxs-lookup"><span data-stu-id="a2d40-149">Return loan asset</span></span>                | <span data-ttu-id="a2d40-150">Registrera utlåningstillgången som returnerad.</span><span class="sxs-lookup"><span data-stu-id="a2d40-150">Register the loan asset as returned.</span></span> |

