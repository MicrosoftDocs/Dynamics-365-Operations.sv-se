---
title: Artikelbehov för serviceorder
description: Om du behöver reservera specifika artiklar för en serviceorder kan du skapa lagerartikelkrav för den.
author: ShylaThompson
manager: tfehr
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProjSalesItemReq
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 8866d8a4d6ad879f2c43b470af98457cb7c75721
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/10/2020
ms.locfileid: "3985750"
---
# <a name="service-order-item-requirements"></a><span data-ttu-id="47e3e-103">Artikelbehov för serviceorder</span><span class="sxs-lookup"><span data-stu-id="47e3e-103">Service order item requirements</span></span>   

[!include [banner](../includes/banner.md)]


<span data-ttu-id="47e3e-104">Du kan du skapa en serviceorder för att följa och hantera tjänster som du tillhandahåller dina kunder.</span><span class="sxs-lookup"><span data-stu-id="47e3e-104">You can create a service order to track and manage services that you provide to your customers.</span></span> <span data-ttu-id="47e3e-105">Om du behöver reservera specifika artiklar för en serviceorder kan du skapa lagerartikelkrav för den.</span><span class="sxs-lookup"><span data-stu-id="47e3e-105">If you need to reserve specific items for a service order, you can create inventory item requirements for it.</span></span> <span data-ttu-id="47e3e-106">Ett artikelbehov kan förbrukas omedelbart från lagret eller så kan det initiera en produktionsorder för artikeln.</span><span class="sxs-lookup"><span data-stu-id="47e3e-106">An item requirement can be immediately consumed from inventory, or it can initiate a production order for the item.</span></span>

<span data-ttu-id="47e3e-107">Genom att använda ett artikelbehov i stället för en artikeltransaktion kan du planera för inleverans precis innan artikeln verkligen används, skapa en inköpsorder, ta med artikeln i handelsavtalsramverket och ta med artikelbehovet i produktionsplaneringen.</span><span class="sxs-lookup"><span data-stu-id="47e3e-107">By using an item requirement instead of an item transaction, you can plan for delivery just before the item is actually used, create a purchase order, include the item in the trade-agreement framework, and include the item requirement in production planning.</span></span>

<span data-ttu-id="47e3e-108">Artikelbehov för serviceorder bearbetas via ett projekt.</span><span class="sxs-lookup"><span data-stu-id="47e3e-108">Item requirements for service orders are processed through a project.</span></span> <span data-ttu-id="47e3e-109">För att kunna skapa ett artikelbehov på en serviceorder måste serviceordern ha kopplats till ett projekt.</span><span class="sxs-lookup"><span data-stu-id="47e3e-109">To create an item requirement on a service order, the service order must be attached to a project.</span></span>

<span data-ttu-id="47e3e-110">Så snart ett artikelbehov har skapats för en serviceorder kan det visas från **Projekt** på den enskilda serviceordern eller via formuläret **Försäljningsorder**.</span><span class="sxs-lookup"><span data-stu-id="47e3e-110">As soon as an item requirement is created for a service order, it can be viewed from **Project** in the individual service order or through the **Sales order** form.</span></span>

## <a name="view-an-item-requirement-from-a-service-order"></a><span data-ttu-id="47e3e-111">Visa ett artikelbehov från en serviceorder</span><span class="sxs-lookup"><span data-stu-id="47e3e-111">View an item requirement from a service order</span></span>

1.  <span data-ttu-id="47e3e-112">Klicka på noden **Servicehantering** \> **Vanligt** \> **Serviceorder** \> **Serviceorder**.</span><span class="sxs-lookup"><span data-stu-id="47e3e-112">Click **Service management** \> **Common** \> **Service orders** \> **Service orders**.</span></span>

2.  <span data-ttu-id="47e3e-113">Klicka på **Varuutförsel**, och klicka sedan på **artikelbehov** öppna formuläret **artikelbehov**.</span><span class="sxs-lookup"><span data-stu-id="47e3e-113">Click **Dispatch**, and then click **Item requirement** to open the **Item requirements** form.</span></span>

3.  <span data-ttu-id="47e3e-114">Klicka på fliken **Projekt** och markera fältet **Serviceorder** om du vill visa serviceorder för artikelbehovet.</span><span class="sxs-lookup"><span data-stu-id="47e3e-114">Click the **Project** tab, and check the **Service order** field to see the service orders of the item requirement.</span></span>

## <a name="delete-service-orders-with-item-requirements"></a><span data-ttu-id="47e3e-115">Ta bort serviceorder med artikelbehov</span><span class="sxs-lookup"><span data-stu-id="47e3e-115">Delete service orders with item requirements</span></span>

<span data-ttu-id="47e3e-116">Om ett artikelbehov har skapats på en serviceorder kan du inte ta bort serviceordern.</span><span class="sxs-lookup"><span data-stu-id="47e3e-116">If an item requirement is created on a service order, you cannot delete the service order.</span></span> <span data-ttu-id="47e3e-117">Du måste ta bort artikelbehovet innan du kan ta bort serviceordern.</span><span class="sxs-lookup"><span data-stu-id="47e3e-117">You must delete the item requirement before you can delete the service order.</span></span>

1.  <span data-ttu-id="47e3e-118">Klicka på noden **Servicehantering** \> **Vanligt** \> **Serviceorder** \> **Serviceorder**.</span><span class="sxs-lookup"><span data-stu-id="47e3e-118">Click **Service management** \> **Common** \> **Service orders** \> **Service orders**.</span></span>

2.  <span data-ttu-id="47e3e-119">Klicka på **Varuutförsel**, och klicka sedan på **artikelbehov** öppna formuläret **artikelbehov**.</span><span class="sxs-lookup"><span data-stu-id="47e3e-119">Click **Dispatch**, and then click **Item requirement** to open the **Item requirements** form.</span></span> <span data-ttu-id="47e3e-120">Detta formulär visar en lista med alla artikelbehov som har skapats på serviceordern.</span><span class="sxs-lookup"><span data-stu-id="47e3e-120">This form lists the item requirements that are created on the service order.</span></span>

3.  <span data-ttu-id="47e3e-121">Välj det artikelbehov som ska tas bort och klicka sedan på **Ta bort**.</span><span class="sxs-lookup"><span data-stu-id="47e3e-121">Select the item requirement to delete, and then click **Delete**.</span></span>

<span data-ttu-id="47e3e-122">–eller–</span><span class="sxs-lookup"><span data-stu-id="47e3e-122">–or–</span></span>

1.  <span data-ttu-id="47e3e-123">Klicka på **Projekthantering och redovisning** \> **Vanligt** \> **Projekt** \> **Alla projekt**.</span><span class="sxs-lookup"><span data-stu-id="47e3e-123">Click **Project management and accounting** \> **Common** \> **Projects** \> **All projects**.</span></span>

2.  <span data-ttu-id="47e3e-124">Öppna projektet som har serviceordern där ett artikelbehov har skapats.</span><span class="sxs-lookup"><span data-stu-id="47e3e-124">Open the project that has the service order in which an item requirement is created.</span></span>

3.  <span data-ttu-id="47e3e-125">I formuläret **projekt** i det högra fönstret klickar du på **artikelbehov**.</span><span class="sxs-lookup"><span data-stu-id="47e3e-125">In the **Projects** form, in the right pane, click **Item requirements**.</span></span> <span data-ttu-id="47e3e-126">Formuläret **Artikelbehov** öppnas och visar en lista med artikelbehov som associeras med det valda projektet.</span><span class="sxs-lookup"><span data-stu-id="47e3e-126">The **Item requirements** form lists the item requirements that are associated with the selected project.</span></span>

4.  <span data-ttu-id="47e3e-127">Välj det artikelbehov som ska tas bort och klicka sedan på **Ta bort**.</span><span class="sxs-lookup"><span data-stu-id="47e3e-127">Select the item requirement to delete, and then click **Delete**.</span></span>

## <a name="see-also"></a><span data-ttu-id="47e3e-128">Se även</span><span class="sxs-lookup"><span data-stu-id="47e3e-128">See also</span></span>

<span data-ttu-id="47e3e-129">[Artikelbehov (formulär)](https://technet.microsoft.com/library/aa552021\(v=ax.60\))</span><span class="sxs-lookup"><span data-stu-id="47e3e-129">[Item requirements (form)](https://technet.microsoft.com/library/aa552021\(v=ax.60\))</span></span>

