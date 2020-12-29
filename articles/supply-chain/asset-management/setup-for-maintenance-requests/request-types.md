---
title: Underhåll begärandetyper
description: I det här avsnittet beskrivs hur du ställer in en typ av underhållsbegäran i tillgångshantering.
author: josaw1
manager: tfehr
ms.date: 07/26/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-07-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d353f084e0d3e056f1b5ff5af6437ba211def8ec
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "4437780"
---
# <a name="maintenance-request-types"></a><span data-ttu-id="9c2a4-103">Underhåll begärandetyper</span><span class="sxs-lookup"><span data-stu-id="9c2a4-103">Maintenance request types</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="9c2a4-104">Typer av underhållsbegäran används för att kategorisera underhållsbegäranden.</span><span class="sxs-lookup"><span data-stu-id="9c2a4-104">Maintenance request types are used to categorize maintenance requests.</span></span> <span data-ttu-id="9c2a4-105">Du kan till exempel ha underhållsbegärandetyper som är relaterade till förebyggande underhåll och korrigerande underhåll.</span><span class="sxs-lookup"><span data-stu-id="9c2a4-105">For example, you might have maintenance request types that are related to preventive maintenance and corrective maintenance.</span></span> <span data-ttu-id="9c2a4-106">Eller du kanske har en särskild typ av underhållsbegäran som används för att hantera reparation av tillgångar (depotreparation).</span><span class="sxs-lookup"><span data-stu-id="9c2a4-106">Or you might have a special maintenance request type that is used to manage repair of assets (depot repair).</span></span>

<span data-ttu-id="9c2a4-107">En typ av underhållbegäran definierar anslutningen med en livscykeltillståndgrupp för underhållsbegäran (underhållslivscykelmodell).</span><span class="sxs-lookup"><span data-stu-id="9c2a4-107">A maintenance request type defines the affiliation with a maintenance request lifecycle state group (maintenance lifecycle model).</span></span> <span data-ttu-id="9c2a4-108">Livscykelmodeller för underhållsbegäran definierar de livscykeltillstånd som kan ställas in för en underhållsbegäran.</span><span class="sxs-lookup"><span data-stu-id="9c2a4-108">Maintenance request lifecycle models define the lifecycle states that can be set for a maintenance request.</span></span> <span data-ttu-id="9c2a4-109">(Exempel på livscykeltillstånd för underhållsbegäran inkluderar **skapad**, **aktiv** och **avslutad**.)</span><span class="sxs-lookup"><span data-stu-id="9c2a4-109">(Examples of maintenance request lifecycle states include **Created**, **Active**, and **Ended**.)</span></span>

1. <span data-ttu-id="9c2a4-110">Välj **tillgångshantering** \> **inställningar** \> **underhållbegäran** \> **underhållbegärantyper**.</span><span class="sxs-lookup"><span data-stu-id="9c2a4-110">Select **Asset management** \> **Setup** \> **Maintenance requests** \> **Maintenance request types**.</span></span>
2. <span data-ttu-id="9c2a4-111">Välj **ny** för att skapa en typ av underhållsbegäran.</span><span class="sxs-lookup"><span data-stu-id="9c2a4-111">Select **New** to create a maintenance request type.</span></span>
3. <span data-ttu-id="9c2a4-112">I fältet **underhållbegärantyp** anger du ett ID för underhållbegärantypen.</span><span class="sxs-lookup"><span data-stu-id="9c2a4-112">In the **Maintenance request type** field, enter an ID for the maintenance request type.</span></span>
4. <span data-ttu-id="9c2a4-113">Ange sedan ett namn i fältet **Namn**.</span><span class="sxs-lookup"><span data-stu-id="9c2a4-113">In the **Name** field, enter a name.</span></span>
5. <span data-ttu-id="9c2a4-114">På snabbfliken **allmänt** i fältet **livscykelmodell för underhållsbegäran** väljer du en livscykelmodell för underhållsbegäran.</span><span class="sxs-lookup"><span data-stu-id="9c2a4-114">On the **General** FastTab, in the **Maintenance request lifecycle model** field, select a maintenance request lifecycle model.</span></span>
6. <span data-ttu-id="9c2a4-115">I fältet **arbetsordertyp** väljer du en arbetsorder.</span><span class="sxs-lookup"><span data-stu-id="9c2a4-115">In the **Work order type** field, select a work order type.</span></span> <span data-ttu-id="9c2a4-116">När en underhållsbegäran konverteras till en arbetsorder får arbetsordern automatiskt den arbetsordertyp som är relaterad till typen av underhållsbegäran.</span><span class="sxs-lookup"><span data-stu-id="9c2a4-116">When a maintenance request is converted to a work order, the work order automatically gets the work order type that is related to the maintenance request type.</span></span>

<span data-ttu-id="9c2a4-117">Följande illustration visar ett exempel på sidan **underhållsbegärandetyper**.</span><span class="sxs-lookup"><span data-stu-id="9c2a4-117">The following illustration shows an example of the **Maintenance request types** page.</span></span>

![Sidan Typer av underhållsbegäran](media/07-setup-for-requests.png)
