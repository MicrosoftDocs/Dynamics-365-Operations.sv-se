---
title: Tillgångar på flera nivåer
description: Det här avsnittet beskriver hur du skapar och tar bort tillgångar på flera nivåer.
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
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a69fd8b7d81700a62ae96d679372b1d6c8a70bbf
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5253216"
---
# <a name="multi-level-assets"></a><span data-ttu-id="d7758-103">Tillgångar på flera nivåer</span><span class="sxs-lookup"><span data-stu-id="d7758-103">Multi-level assets</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="d7758-104">Det här avsnittet beskriver hur du skapar och tar bort tillgångar på flera nivåer.</span><span class="sxs-lookup"><span data-stu-id="d7758-104">This topic explains how to create and delete multi-level assets.</span></span> <span data-ttu-id="d7758-105">Du kan skapa tillgångar och relaterade undertillgångar i en hierarkisk trädstruktur.</span><span class="sxs-lookup"><span data-stu-id="d7758-105">You can create assets and related sub-assets in a hierarchical tree structure.</span></span> <span data-ttu-id="d7758-106">På så sätt kan du visa relationer och beroenden mellan tillgångar.</span><span class="sxs-lookup"><span data-stu-id="d7758-106">In this way, you can show relations and dependencies among assets.</span></span> <span data-ttu-id="d7758-107">Underhållsjobb kan relateras till alla nivåer i trädstrukturen.</span><span class="sxs-lookup"><span data-stu-id="d7758-107">Maintenance jobs can be related to all levels of the tree structure.</span></span> <span data-ttu-id="d7758-108">Statistik kan också skapas för en individuell nivå eller som en summa av alla nivåer av undertillgångar.</span><span class="sxs-lookup"><span data-stu-id="d7758-108">Statistics can also be created for an individual level or as a sum of all sub-asset levels.</span></span>

<span data-ttu-id="d7758-109">På listsidan **Alla tillgångar** (**Tillgångshantering** \> **Allmänt** \> **Tillgångar** \> **Alla tillgångar**), anger kolumnen **Tillgångar** alla tillgångar i hierarkisk ordning.</span><span class="sxs-lookup"><span data-stu-id="d7758-109">On the **All Assets** list page (**Asset management** \> **Common** \> **Assets** \> **All assets**), the **Asset** column lists assets in hierarchical order.</span></span> <span data-ttu-id="d7758-110">Kolumnen **överordnade** visar den relaterade överordnade.</span><span class="sxs-lookup"><span data-stu-id="d7758-110">The **Parent** column shows the related parent.</span></span> <span data-ttu-id="d7758-111">Dessutom, om tillgångar och undertillgångar redan har skapats visar avsnittet **Tillgångsträd** i fönstret **Relaterad information** tillgången i trädstrukturen.</span><span class="sxs-lookup"><span data-stu-id="d7758-111">Additionally, if assets and sub-assets have already been created, the **Asset tree** section in the **Related information** pane shows the assets in a tree structure.</span></span>

<span data-ttu-id="d7758-112">Information om hur du skapar en tillgång finns i [Skapa en tillgång](../objects/create-an-object.md).</span><span class="sxs-lookup"><span data-stu-id="d7758-112">For information about how to create an asset, see [Create an asset](../objects/create-an-object.md).</span></span> <span data-ttu-id="d7758-113">Om du vill skapa en undertillgång väljer du den den överordnade tillgången i fältet **överordnad** på snabbfliken **allmänt**.</span><span class="sxs-lookup"><span data-stu-id="d7758-113">To create a sub-asset, select the parent asset in the **Parent** field on the **General** FastTab.</span></span>

## <a name="copy-an-asset-or-asset-structure"></a><span data-ttu-id="d7758-114">Kopiera en tillgång eller tillgångsstruktur</span><span class="sxs-lookup"><span data-stu-id="d7758-114">Copy an asset or asset structure</span></span>

<span data-ttu-id="d7758-115">Om ditt företag har flera liknande tillgångsstrukturer, kan du använda funktionen Kopiera i Tillgångshantering för att snabbt skapa dem.</span><span class="sxs-lookup"><span data-stu-id="d7758-115">If your company has several similar asset structures, you can use the Copy function in Asset Management to quickly create them.</span></span>

1. <span data-ttu-id="d7758-116">Välj **Tillgångshantering** \> **Allmänt** \> **Tillgångar** \> **Alla tillgångar**</span><span class="sxs-lookup"><span data-stu-id="d7758-116">Select **Asset management** \> **Common** \> **Assets** \> **All assets**.</span></span>
2. <span data-ttu-id="d7758-117">På listsidan **Alla tillgångar** väljer du den tillgång som ska kopieras.</span><span class="sxs-lookup"><span data-stu-id="d7758-117">On the **All assets** list page, select the asset to copy.</span></span> <span data-ttu-id="d7758-118">Om du till exempel vill kopiera hela tillgångsstrukturen, inklusive undertillgångar, väljer du en överordnad tillgång.</span><span class="sxs-lookup"><span data-stu-id="d7758-118">For example, if you want to copy the whole asset structure, including sub-assets, select a parent asset.</span></span>
3. <span data-ttu-id="d7758-119">Välj **Kopiera tillgång**.</span><span class="sxs-lookup"><span data-stu-id="d7758-119">Select **Copy asset**.</span></span> <span data-ttu-id="d7758-120">I avsnittet **Kopiera från** är fältet **Tillgång** inställt på den tillgång som du valde på listsidan.</span><span class="sxs-lookup"><span data-stu-id="d7758-120">In the **Copy from** section, the **Asset** field is set to the asset that you selected on the list page.</span></span>
4. <span data-ttu-id="d7758-121">I avsnittet **Kopiera till** i fältet **Tillgång** anger du namnet på den nya tillgången.</span><span class="sxs-lookup"><span data-stu-id="d7758-121">In the **Copy to** section, in the **Asset** field, enter the name of the new asset.</span></span>
5. <span data-ttu-id="d7758-122">Om den tillgång som du skapar ska vara en del av en befintlig tillgångsstruktur, i avsnittet **Överordnad tillgång** i fältet **Tillgång** väljer du ett överordnat ID.</span><span class="sxs-lookup"><span data-stu-id="d7758-122">If the asset that you're creating should be part of an existing asset structure, in the **Parent asset** section, in the **Asset** field, select a parent ID.</span></span>
6. <span data-ttu-id="d7758-123">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="d7758-123">Select **OK**.</span></span> <span data-ttu-id="d7758-124">Den nya tillgångsstrukturen visas på listsidan **Alla tillgångar**.</span><span class="sxs-lookup"><span data-stu-id="d7758-124">The new asset structure is shown on the **All assets** list page.</span></span> <span data-ttu-id="d7758-125">Alla tillgångsattribut, underhållsplaner och underhållsomgångar som är relaterade till den tillgång som du kopierade överförs till den nya tillgången eller tillgångsstrukturen.</span><span class="sxs-lookup"><span data-stu-id="d7758-125">All asset attributes, maintenance plans, and maintenance rounds that are related to the asset that you copied are transferred to the new asset or asset structure.</span></span>

<span data-ttu-id="d7758-126">När du kopierar en tillgångsstruktur har undertillgångarna i den nya strukturen samma namn som undertillgångarna du kopierade.</span><span class="sxs-lookup"><span data-stu-id="d7758-126">When you copy an asset structure, the sub-assets in the new structure have the same name as the sub-assets that you copied.</span></span> <span data-ttu-id="d7758-127">När kopieringen är klar kan du enkelt ändra namn och andra inställningar för en tillgång.</span><span class="sxs-lookup"><span data-stu-id="d7758-127">After the copy procedure is completed, you can easily change the name and other settings for an asset.</span></span> <span data-ttu-id="d7758-128">Välj tillgången på listsidan **Alla tillgångar** och välj sedan knappen **redigera**.</span><span class="sxs-lookup"><span data-stu-id="d7758-128">Select the asset on the **All assets** list page, and then select the **Edit** button.</span></span>

> [!NOTE]
> <span data-ttu-id="d7758-129">När du kopierar en tillgång eller tillgångsstruktur återställs livscykeltillståndet för de nya tillgångarna till det tillstånd som du definierade som det ursprungliga livscykeltillståndet för tillgångarna.</span><span class="sxs-lookup"><span data-stu-id="d7758-129">When you copy an asset or asset structure, the lifecycle state of the new assets is reset to whatever state you defined as the initial lifecycle state for assets.</span></span> <span data-ttu-id="d7758-130">Funktionsplatsen återställs till standardfunktionsplatsen.</span><span class="sxs-lookup"><span data-stu-id="d7758-130">The functional location is reset to the default functional location.</span></span>

## <a name="delete-an-asset-or-asset-structure"></a><span data-ttu-id="d7758-131">Ta bort en tillgång eller tillgångsstruktur</span><span class="sxs-lookup"><span data-stu-id="d7758-131">Delete an asset or asset structure</span></span>

<span data-ttu-id="d7758-132">Om en tillgång har relaterade undertillgångar kan du endast ta bort den om inga underhållsbegäran, arbetsorderjobb, felregistreringar eller villkorsbedömningar registreras på någon av tillgångarna.</span><span class="sxs-lookup"><span data-stu-id="d7758-132">If an asset has related sub-assets, you can delete it only if no maintenance requests, work order jobs, fault registrations, or condition assessments are registered on any of the assets.</span></span>

1. <span data-ttu-id="d7758-133">På listsidan **Alla tillgångar** väljer du den tillgång som ska tas bort.</span><span class="sxs-lookup"><span data-stu-id="d7758-133">On the **All assets** list page, select the asset to delete.</span></span>
2. <span data-ttu-id="d7758-134">Välj **Ta bort**.</span><span class="sxs-lookup"><span data-stu-id="d7758-134">Select **Delete**.</span></span>

> [!NOTE]
> <span data-ttu-id="d7758-135">Om du inte kan ta bort en tillgång med hjälp av den här proceduren är ett annat sätt att hantera borttagningen att ställa in ett tillgångs livscykeltillstånd för detta ändamål.</span><span class="sxs-lookup"><span data-stu-id="d7758-135">If you can't delete an asset by using this procedure, another way to handle deletion is to set up an asset lifecycle state for this purpose.</span></span> <span data-ttu-id="d7758-136">Du kan till exempel ställa in ett **Kasserat** eller **Borttaget** livscykeltillstånd på sidan **Tillgångens livscykeltillstånd**.</span><span class="sxs-lookup"><span data-stu-id="d7758-136">For example, you can set up a **Scrapped** or **Deleted** lifecycle state on the **Asset lifecycle states** page.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]