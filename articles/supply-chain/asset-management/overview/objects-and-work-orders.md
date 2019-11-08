---
title: Tillgångar och arbetsorder
description: Det här avsnittet beskriver tillgångar och arbetsorder i tillgångshantering.
author: josaw1
manager: AnnBe
ms.date: 06/24/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 8b56234eac247185c5cd4d8ab45a65d258013acd
ms.sourcegitcommit: d37fb09101c30858bcb975931b3d8f947d72017b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/10/2019
ms.locfileid: "2571379"
---
# <a name="assets-and-work-orders"></a><span data-ttu-id="34ac8-103">Tillgångar och arbetsorder</span><span class="sxs-lookup"><span data-stu-id="34ac8-103">Assets and work orders</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="34ac8-104">Det här avsnittet beskriver tillgångar och arbetsorder i tillgångshantering.</span><span class="sxs-lookup"><span data-stu-id="34ac8-104">This topic describes assets and work orders in Asset Management.</span></span> <span data-ttu-id="34ac8-105">Tillgångar och arbetsorder är de centrala delarna i funktionshanteraren.</span><span class="sxs-lookup"><span data-stu-id="34ac8-105">Assets and work orders are the central parts of Asset Management.</span></span> <span data-ttu-id="34ac8-106">En *tillgång* är en maskin- eller maskindel som kräver kontinuerlig underhåll och service.</span><span class="sxs-lookup"><span data-stu-id="34ac8-106">An *asset* is a machine or machine part that requires continuous maintenance and service.</span></span> <span data-ttu-id="34ac8-107">Tillgångar kan skapas i en hierarkisk struktur och de kan relateras till funktionsplatser.</span><span class="sxs-lookup"><span data-stu-id="34ac8-107">Assets can be created in a hierarchical structure, and they can be related to functional locations.</span></span> <span data-ttu-id="34ac8-108">Underhållsjobb kan planeras på alla nivåer i tillgångsstrukturen.</span><span class="sxs-lookup"><span data-stu-id="34ac8-108">Maintenance jobs can be planned at all levels in the asset structure.</span></span>

<span data-ttu-id="34ac8-109">Olika data, till exempel produktinformation och tillgångsspecifikation och nödvändiga underhållsplaner ställs in för varje tillgång.</span><span class="sxs-lookup"><span data-stu-id="34ac8-109">Various data, such as product information and asset specification, and required maintenance plans are set up on each asset.</span></span> <span data-ttu-id="34ac8-110">Följande illustration visar en översikt över tillgångsdata och anslutning av tillgångar till jobbtyper.</span><span class="sxs-lookup"><span data-stu-id="34ac8-110">The following illustration shows an overview of asset data and the affiliation of assets to job types.</span></span> <span data-ttu-id="34ac8-111">Röd text används för exempel som visar arv och beroenden.</span><span class="sxs-lookup"><span data-stu-id="34ac8-111">Red text is used for examples that show inheritance and dependencies.</span></span>

![Diagram som visar tillgångsdata relaterade till jobbtyper](media/05-overview-image.png)

<span data-ttu-id="34ac8-113">Varje arbetsorder har en arbetsordertyp, sådant förebyggande underhåll, avhjälpande underhåll eller inspektion.</span><span class="sxs-lookup"><span data-stu-id="34ac8-113">Every work order has a work order type, such preventive maintenance, corrective maintenance, or inspection.</span></span> <span data-ttu-id="34ac8-114">Arbetsordern innehåller ett eller flera arbetsorderjobb.</span><span class="sxs-lookup"><span data-stu-id="34ac8-114">The work order contains one or more work order jobs.</span></span> <span data-ttu-id="34ac8-115">Varje arbetsorderjobb definierar ett jobb som måste utföras på en tillgång och en relaterad jobbtyp.</span><span class="sxs-lookup"><span data-stu-id="34ac8-115">Every work order job defines a job that must be performed on an asset and a related job type.</span></span> <span data-ttu-id="34ac8-116">Exempel på relaterade jobbtyper är 10 000 km, 50 000 km, 1-års översyn och säkerhetsinspektion.</span><span class="sxs-lookup"><span data-stu-id="34ac8-116">Examples of related job types include 10,000 km, 50,000 km, 1-year overhaul, and safety inspection.</span></span> <span data-ttu-id="34ac8-117">En arbetsorder kan relateras till flera tillgångar.</span><span class="sxs-lookup"><span data-stu-id="34ac8-117">One work order can be related to multiple assets.</span></span>

<span data-ttu-id="34ac8-118">Följande illustration visar en översikt över nyckeldata i en arbetsorder.</span><span class="sxs-lookup"><span data-stu-id="34ac8-118">The following illustration shows an overview of the key data in a work order.</span></span>

![Diagram som visar nyckeldata i en arbetsorder](media/06-overview-image.png)

<span data-ttu-id="34ac8-120">En arbetsorder kan relateras till en annan arbetsorder och jobbtyper kan innehålla efterföljande jobb som skapar en arbetsorder.</span><span class="sxs-lookup"><span data-stu-id="34ac8-120">A work order can be related to another work order, and job types can contain succeeding jobs that create a work order.</span></span> <span data-ttu-id="34ac8-121">I allmänhet finns det inga beroenden mellan arbetsorder.</span><span class="sxs-lookup"><span data-stu-id="34ac8-121">In general, there are no dependencies between work orders.</span></span> <span data-ttu-id="34ac8-122">Därför kan de ändra sitt livscykeltillstånd för arbetsorder och kan schemaläggas oberoende av varandra.</span><span class="sxs-lookup"><span data-stu-id="34ac8-122">Therefore, they can change their work order lifecycle state and can be scheduled independently of each other.</span></span>

<span data-ttu-id="34ac8-123">Arbetsorder kan skapas på olika sätt som är relaterade till korrigerande, förebyggande eller reaktivt underhåll.</span><span class="sxs-lookup"><span data-stu-id="34ac8-123">Work orders can be created in various ways that are related to corrective, preventive, or reactive maintenance.</span></span> <span data-ttu-id="34ac8-124">Du kan också skapa arbetsorder manuellt.</span><span class="sxs-lookup"><span data-stu-id="34ac8-124">You can also create work orders manually.</span></span> <span data-ttu-id="34ac8-125">Följande illustration visar en översikt över processen för automatisk eller manuell generering av arbetsorder.</span><span class="sxs-lookup"><span data-stu-id="34ac8-125">The following illustration shows an overview of the process for automatic or manual creation of work orders.</span></span>

![Diagram som visar automatisk eller manuell generering av arbetsorder](media/07-overview-image.png)

<span data-ttu-id="34ac8-127">Flera steg måste slutföras när du vill schemalägga och köra ett underhållsjobb på en arbetsorder.</span><span class="sxs-lookup"><span data-stu-id="34ac8-127">Several steps must be completed when you want to schedule and run a maintenance job on a work order.</span></span> <span data-ttu-id="34ac8-128">Följande illustration visar en översikt över bearbetning för en arbetsorder.</span><span class="sxs-lookup"><span data-stu-id="34ac8-128">The following illustration shows an overview of the processing for a work order.</span></span>

![Diagram som visar översikt över bearbetning av en arbetsorder](media/08-overview-image.png)

> [!NOTE]
> <span data-ttu-id="34ac8-130">I allmänhet när du arbetar i Dynamics 365 Supply Chain Management och modulen **tillgångshantering** väljer du **Ny** för att skapa en ny post, väljer **redigera** för att uppdatera en befintlig post och väljer **Spara** för att spara nya eller redigerade data.</span><span class="sxs-lookup"><span data-stu-id="34ac8-130">In general, when you work in Dynamics 365 Supply Chain Management and the **Asset Management** module, you select **New** to create a new record, you select **Edit** to update an existing record, and you select **Save** to save new or edited data.</span></span>
