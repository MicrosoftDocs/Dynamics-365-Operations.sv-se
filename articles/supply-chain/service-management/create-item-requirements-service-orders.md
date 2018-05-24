---
title: "Skapa artikelbehov för serviceorder"
description: "Om du behöver reservera specifika artiklar för en serviceorder kan du skapa lagerartikelkrav för den."
author: YuyuScheller
manager: AnnBe
ms.date: 05/01/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SMAServiceOrderTable
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: YuyuScheller
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: e76b0c636470a89ba2091363efe2f34eb3d58f88
ms.contentlocale: sv-se
ms.lasthandoff: 05/08/2018

---

# <a name="create-item-requirements-for-service-orders"></a><span data-ttu-id="f94d9-103">Skapa artikelbehov för serviceorder</span><span class="sxs-lookup"><span data-stu-id="f94d9-103">Create item requirements for service orders</span></span> 

[!include [banner](../includes/banner.md)]


<span data-ttu-id="f94d9-104">Du kan du skapa en serviceorder för att följa och hantera tjänster som du tillhandahåller dina kunder.</span><span class="sxs-lookup"><span data-stu-id="f94d9-104">You can create a service order to track and manage services that you provide to your customers.</span></span> <span data-ttu-id="f94d9-105">Om du behöver reservera specifika artiklar för en serviceorder kan du skapa lagerartikelkrav för den.</span><span class="sxs-lookup"><span data-stu-id="f94d9-105">If you need to reserve specific items for a service order, you can create inventory item requirements for it.</span></span> <span data-ttu-id="f94d9-106">Ett artikelbehov kan förbrukas omedelbart från lagret eller så kan det initiera en produktionsorder för artikeln.</span><span class="sxs-lookup"><span data-stu-id="f94d9-106">An item requirement can be immediately consumed from inventory, or it can initiate a production order for the item.</span></span>

<span data-ttu-id="f94d9-107">Genom att använda ett artikelbehov i stället för en artikeltransaktion kan du planera för inleverans precis innan artikeln verkligen används, skapa en inköpsorder, ta med artikeln i handelsavtalsramverket och ta med artikelbehovet i produktionsplaneringen.</span><span class="sxs-lookup"><span data-stu-id="f94d9-107">By using an item requirement instead of an item transaction, you can plan for delivery just before the item is actually used, create a purchase order, include the item in the trade-agreement framework, and include the item requirement in production planning.</span></span>

<span data-ttu-id="f94d9-108">Artikelbehov för serviceorder bearbetas via ett projekt.</span><span class="sxs-lookup"><span data-stu-id="f94d9-108">Item requirements for service orders are processed through a project.</span></span> <span data-ttu-id="f94d9-109">För att kunna skapa ett artikelbehov på en serviceorder måste serviceordern ha tilldelats till ett projekt.</span><span class="sxs-lookup"><span data-stu-id="f94d9-109">To create an item requirement on a service order, the service order must be assigned to a project.</span></span> <span data-ttu-id="f94d9-110">När du har skapat ett artikelbehov för en serviceorder kan du visa artikelbehovet i formuläret **Projekt** för det valda projektet.</span><span class="sxs-lookup"><span data-stu-id="f94d9-110">After you create an item requirement for a service order, you can view the item requirement in the **Projects** form for the selected project.</span></span>

## <a name="create-an-item-requirement-for-a-service-order"></a><span data-ttu-id="f94d9-111">Skapa ett artikelbehov för en serviceorder</span><span class="sxs-lookup"><span data-stu-id="f94d9-111">Create an item requirement for a service order</span></span>

1.  <span data-ttu-id="f94d9-112">Klicka på noden **Servicehantering** \> **Vanligt** \> **Serviceorder** \> **Serviceorder**.</span><span class="sxs-lookup"><span data-stu-id="f94d9-112">Click **Service management** \> **Common** \> **Service orders** \> **Service orders**.</span></span>

2.  <span data-ttu-id="f94d9-113">Välj den serviceorder som du vill skapa ett artikelbehov för.</span><span class="sxs-lookup"><span data-stu-id="f94d9-113">Select the service order that you want to create an item requirement for.</span></span>

3.  <span data-ttu-id="f94d9-114">På **Åtgärdsfönster**, på fliken **Varuutförsel**, klicka på **Artikelbehov**.</span><span class="sxs-lookup"><span data-stu-id="f94d9-114">On the **Action Pane**, on the **Dispatch** tab, click **Item requirement**.</span></span>

4.  <span data-ttu-id="f94d9-115">I formuläret **Artikelbehov** ange information för krävd artikel.</span><span class="sxs-lookup"><span data-stu-id="f94d9-115">In the **Item requirements** form, enter information for the required item.</span></span> <span data-ttu-id="f94d9-116">Mer information om ett specifikt fält finns i [Artikelbehov (formulär)](https://technet.microsoft.com/en-us/library/aa552021\(v=ax.60\)).</span><span class="sxs-lookup"><span data-stu-id="f94d9-116">For more information about the specific fields, see [Item requirements (form)](https://technet.microsoft.com/en-us/library/aa552021\(v=ax.60\)).</span></span>

## <a name="create-an-item-requirement-for-a-service-agreement"></a><span data-ttu-id="f94d9-117">Skapa ett artikelbehov för ett serviceavtal</span><span class="sxs-lookup"><span data-stu-id="f94d9-117">Create an item requirement for a service agreement</span></span>

1.  <span data-ttu-id="f94d9-118">Klicka på **servicehantering** \> **allmänt** \> **serviceavtal** \> **serviceavtal**.</span><span class="sxs-lookup"><span data-stu-id="f94d9-118">Click **Service management** \> **Common** \> **Service agreements** \> **Service agreements**.</span></span>

2.  <span data-ttu-id="f94d9-119">Öppna serviceavtalet som du vill skapa ett artikelbehov för.</span><span class="sxs-lookup"><span data-stu-id="f94d9-119">Open the service agreement for which you want to create an item requirement.</span></span>

3.  <span data-ttu-id="f94d9-120">På snabbfliken **Rader**, klicka på **Lägg till** för att skapa en ny rad.</span><span class="sxs-lookup"><span data-stu-id="f94d9-120">On the **Lines** FastTab, click **Add** to create a new line.</span></span>

4.  <span data-ttu-id="f94d9-121">I fältet **Transaktionstyp**, välj **Artikel**.</span><span class="sxs-lookup"><span data-stu-id="f94d9-121">In the **Transaction type** field, select **Item**.</span></span>

5.  <span data-ttu-id="f94d9-122">I fältet **Artikelinställningar** välj **artikelbehov**.</span><span class="sxs-lookup"><span data-stu-id="f94d9-122">In the **Item setup** field, select **Item requirement**.</span></span>

6.  <span data-ttu-id="f94d9-123">I fältet **Artikelnummer**, välj den artikel som krävs för serviceavtalet i fältet.</span><span class="sxs-lookup"><span data-stu-id="f94d9-123">In the **Item number** field, select the item that is required for the service agreement.</span></span>

7.  <span data-ttu-id="f94d9-124">På snabbfliken **raduppgifter** på fliken **produktdimensioner** i fältet **Plats** väljer du lagerplats för artikeln.</span><span class="sxs-lookup"><span data-stu-id="f94d9-124">On the **Line details** FastTab, on the **Product dimensions** tab, in the **Site** field, select the inventory site for the item.</span></span>

8.  <span data-ttu-id="f94d9-125">Om du vill skapa en serviceorder från avtalsraden, på snabbfliken **Rader** klickar du på **Skapa serviceorder**, och anger sedan relevant information i formuläret **Skapa serviceorder**.</span><span class="sxs-lookup"><span data-stu-id="f94d9-125">To create a service order from the agreement line, on the **Lines** FastTab, click **Create service orders**, and then enter the relevant information in the **Create service orders** form.</span></span> 


## <a name="see-also"></a><span data-ttu-id="f94d9-126">Se även</span><span class="sxs-lookup"><span data-stu-id="f94d9-126">See also</span></span>

<span data-ttu-id="f94d9-127">[Skapa serviceorder automatiskt](create-service-orders-automatically.md)</span><span class="sxs-lookup"><span data-stu-id="f94d9-127">[Create service orders automatically](create-service-orders-automatically.md).</span></span>

  



