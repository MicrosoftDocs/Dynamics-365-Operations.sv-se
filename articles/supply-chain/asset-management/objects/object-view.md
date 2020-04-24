---
title: Tillgångsvy
description: I detta avsnitt beskrivs tillgångsvy i Tillgångshantering.
author: josaw1
manager: tfehr
ms.date: 06/26/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 14dc2cd95a47931ae4941b87205f2104891af404
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/02/2020
ms.locfileid: "3208235"
---
# <a name="asset-view"></a><span data-ttu-id="0f9fe-103">Tillgångsvy</span><span class="sxs-lookup"><span data-stu-id="0f9fe-103">Asset view</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="0f9fe-104">I detta avsnitt beskrivs tillgångsvy i Tillgångshantering.</span><span class="sxs-lookup"><span data-stu-id="0f9fe-104">This topic describes the asset view in Asset Management.</span></span> <span data-ttu-id="0f9fe-105">Sidan **Tillgångsvy** visar aktiva tillgångar och funktionsplatser i en trädvy.</span><span class="sxs-lookup"><span data-stu-id="0f9fe-105">The **Asset view** page shows active assets and functional locations in a tree view.</span></span> <span data-ttu-id="0f9fe-106">Därför kan du enkelt få en översikt över tillgångsrelationer till funktionsplatser.</span><span class="sxs-lookup"><span data-stu-id="0f9fe-106">Therefore, you can easily get an overview of asset relations to functional locations.</span></span> <span data-ttu-id="0f9fe-107">Dessutom kan du visa detaljerad information om funktionsplatser, tillgångar och relaterade strukturlistor.</span><span class="sxs-lookup"><span data-stu-id="0f9fe-107">Additionally, you can view detailed information about functional locations, assets, and related bills of materials (BOMs).</span></span> <span data-ttu-id="0f9fe-108">Du kan också få en snabb överblick över aktiva underhållsbegäranden och arbetsorder som är relaterade till en tillgång.</span><span class="sxs-lookup"><span data-stu-id="0f9fe-108">You can also get a quick overview of active maintenance requests and work orders that are related to an asset.</span></span>

1. <span data-ttu-id="0f9fe-109">Välj **Tillgångshantering** \> **Allmänt** \> **Tillgångar** \> **Tillgångsvy**</span><span class="sxs-lookup"><span data-stu-id="0f9fe-109">Select **Asset management** \> **Common** \> **Assets** \> **Asset view**.</span></span>
2. <span data-ttu-id="0f9fe-110">Om du vill ändra vyn som visas på sidan väljer du ett nytt värde i fältet **Vy**.</span><span class="sxs-lookup"><span data-stu-id="0f9fe-110">To change the view that is shown on the page, select a new value in the **View** field.</span></span>

    > [!NOTE]
    > <span data-ttu-id="0f9fe-111">Standardvyn som visas när du öppnar sidan **Tillgångsvy** beror på värdet som valts i fältet **Vy** på fliken **tillgångar** på sidan **parametrar för tillgångshantering** (**tillgångshantering** \> **inställning** \> **parametrar för tillgångshantering**).</span><span class="sxs-lookup"><span data-stu-id="0f9fe-111">The default view that is shown when you open the **Asset view** page depends on the value that is selected in the **View** field on the **Assets** tab of the **Asset management parameters** page (**Asset management** \> **Setup** \> **Asset management parameters**).</span></span>

<span data-ttu-id="0f9fe-112">Till höger på sidan visar snabbflikar information om den valda vyn.</span><span class="sxs-lookup"><span data-stu-id="0f9fe-112">On the right side of the page, FastTabs shows details of the selected view.</span></span>

<span data-ttu-id="0f9fe-113">Navigeringssökvägen som visas ovanför trädvyn visar den aktuella markeringen i trädvyn.</span><span class="sxs-lookup"><span data-stu-id="0f9fe-113">The breadcrumb trail that appears above the tree view shows the current selection in the tree view.</span></span> <span data-ttu-id="0f9fe-114">Denna navigeringssökväg använder följande format:</span><span class="sxs-lookup"><span data-stu-id="0f9fe-114">This breadcrumb trail uses the following format:</span></span>

<span data-ttu-id="0f9fe-115">Funktionellt plats-ID/funktionellt plats-ID (om det finns fler än en funktionsplats) \> tillgångs-ID/tillgångs-ID (om det finns mer än en tillgång) - artikelnummer.</span><span class="sxs-lookup"><span data-stu-id="0f9fe-115">Functional location ID / Functional location ID (if there is more than one functional location) \> Asset ID / Asset ID (if there is more than one asset) - Item number.</span></span>

<span data-ttu-id="0f9fe-116">Om du har valt en tillgång i trädvyn kan du välja **aktiva begäranden** eller **aktiva arbetsorder** för att visa de underhållsbegäranden eller arbetsorder som är relaterade till tillgången.</span><span class="sxs-lookup"><span data-stu-id="0f9fe-116">If you've selected an asset in the tree view, you can select **Active requests** or **Active work orders** to view the maintenance requests or work orders that are related to the asset.</span></span> <span data-ttu-id="0f9fe-117">Du kan också välja **öppna** \> **funktionsplats**, **tillgång**eller **tillgångsstruktur** för att öppna den relaterade vyn.</span><span class="sxs-lookup"><span data-stu-id="0f9fe-117">You can also select **Open** \> **Functional location**, **Asset**, or **Asset BOM** to open the related view.</span></span>

<span data-ttu-id="0f9fe-118">Alternativet **funktionsplatser för tillgång** som du kan välja i fältet **Vy** är också tillgängligt i alla tillgångssökning där du kan välja en tillgång.</span><span class="sxs-lookup"><span data-stu-id="0f9fe-118">The **Asset functional locations** option that you can select in the **View** field is also available in any asset lookup where you can select an asset.</span></span> <span data-ttu-id="0f9fe-119">Trädvyn visas på fliken **tillgångsvy**, till exempel där du [skapar en tillgång](../objects/create-an-object.md), skapar en underhållsbegäran eller skapar en arbetsorder.</span><span class="sxs-lookup"><span data-stu-id="0f9fe-119">The tree view is shown on an **Asset view** tab, for example, where you [create an asset](../objects/create-an-object.md), create a maintenance request, or create a work order.</span></span>
