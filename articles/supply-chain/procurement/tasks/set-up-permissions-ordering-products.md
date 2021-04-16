---
title: Ställ in behörigheter för att beställa produkter för någon annans räkning
description: I det här avsnittet visas hur du beviljar arbetare behörighet att förbereda inköpsrekvisitioner på uppdrag av andra arbetare.
author: kamaybac
ms.date: 08/20/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: PurchReqAuthorization, HcmWorkerLookUp
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: dabourq
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d0408085d401a34a409bfe46bc6845a9c81a2eea
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5811904"
---
# <a name="set-up-permissions-for-ordering-products-on-behalf-of-someone-else"></a><span data-ttu-id="3150e-103">Ställ in behörigheter för att beställa produkter för någon annans räkning</span><span class="sxs-lookup"><span data-stu-id="3150e-103">Set up permissions for ordering products on behalf of someone else</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="3150e-104">I det här avsnittet visas hur du beviljar arbetare behörighet att förbereda inköpsrekvisitioner på uppdrag av andra arbetare.</span><span class="sxs-lookup"><span data-stu-id="3150e-104">This topic explains how to grant workers permission to prepare purchase requisitions on behalf of other workers.</span></span> <span data-ttu-id="3150e-105">Med andra ord kan en "förberedare" av inköpsrekvisitionen skapa en rekvisition för en annan ”begärare”.</span><span class="sxs-lookup"><span data-stu-id="3150e-105">In other words, a purchase requisition "preparer" can create a requisition for another "requester."</span></span> <span data-ttu-id="3150e-106">Denna procedur visar också hur du beviljar en anställd behörighet till orderartiklar och tjänster i olika juridiska personer eller driftenheter.</span><span class="sxs-lookup"><span data-stu-id="3150e-106">The procedure also shows how to grant a worker permission to order items and services in different legal entities or operating units.</span></span> <span data-ttu-id="3150e-107">Dessa inställningsuppgifter utförs normalt av en inköpschef.</span><span class="sxs-lookup"><span data-stu-id="3150e-107">Typically, these tasks are performed by a purchasing manager.</span></span> <span data-ttu-id="3150e-108">Du kan använda den här proceduren antingen i data för demonstrationsföretaget USMF eller på dina egna data.</span><span class="sxs-lookup"><span data-stu-id="3150e-108">You can use this procedure either on data for the USMF demo company or on your own data.</span></span>


## <a name="grant-permission-to-enter-purchase-requisitions-on-behalf-of-another-worker"></a><span data-ttu-id="3150e-109">Bevilja behörighet att ange inköpsrekvisitioner på uppdrag av en annan anställd</span><span class="sxs-lookup"><span data-stu-id="3150e-109">Grant permission to enter purchase requisitions on behalf of another worker</span></span>
1. <span data-ttu-id="3150e-110">I navigeringsfönstret går du till **Moduler > Anskaffning och källa > Inställningar > Policyer > Behörighet för inköpsrekvisition**.</span><span class="sxs-lookup"><span data-stu-id="3150e-110">In the navigation pane, go to **Modules > Procurement and sourcing > Setup > Policies > Purchase requisition permissions**.</span></span> <span data-ttu-id="3150e-111">Kontrollera att fältet **Aktuell vy** är inställt på **Per förberedare**.</span><span class="sxs-lookup"><span data-stu-id="3150e-111">Make sure that the **Current view** field is set to **By preparer**.</span></span> <span data-ttu-id="3150e-112">Listan i vänstra fönstret visar personer som kan beviljas behörighet att förbereda rekvisitioner på uppdrag av andra personer.</span><span class="sxs-lookup"><span data-stu-id="3150e-112">The list in the left pane shows the people who can be granted permission to prepare requisitions on behalf of other people.</span></span>  
2. <span data-ttu-id="3150e-113">Välj den person som ska beviljas behörighet (förberedaren).</span><span class="sxs-lookup"><span data-stu-id="3150e-113">Select the person to grant permission to (the preparer).</span></span>
3. <span data-ttu-id="3150e-114">Markera **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="3150e-114">Select **Add**.</span></span>
4. <span data-ttu-id="3150e-115">Hitta och välj den person om du vill lägga till som en beställare.</span><span class="sxs-lookup"><span data-stu-id="3150e-115">Find and select the person to add as a requester.</span></span>
    - <span data-ttu-id="3150e-116">Beställaren är den person som förberedaren kan skapa rekvisitioner för.</span><span class="sxs-lookup"><span data-stu-id="3150e-116">The requester is the person that the preparer can create requisitions on behalf of.</span></span>  
    - <span data-ttu-id="3150e-117">I fältet **Auktorisering** väljer du **Specifik** och förberedaren ska kunna skapa inköpsrekvisitioner på uppdrag av den valda arbetaren.</span><span class="sxs-lookup"><span data-stu-id="3150e-117">In the **Authorization** field, select **Specific** if the preparer should be able to create purchase requisitions on behalf of the selected worker.</span></span> <span data-ttu-id="3150e-118">Välj **Rapportering** om förberedaren även ska kunna skapa inköpsrekvisitioner på uppdrag av alla arbetare som rapporterar till den arbetaren.</span><span class="sxs-lookup"><span data-stu-id="3150e-118">Select **Reporting** if the preparer should also be able to create purchase requisitions on behalf of all workers who report to that worker.</span></span>  
5. <span data-ttu-id="3150e-119">Ange ett datum i fältet **Giltighet.**</span><span class="sxs-lookup"><span data-stu-id="3150e-119">In the **Effective** field, enter a date.</span></span>
6. <span data-ttu-id="3150e-120">I fältet **Utgång** anger du ett datum.</span><span class="sxs-lookup"><span data-stu-id="3150e-120">In the **Expiration** field, enter a date.</span></span>

## <a name="view-preparers-who-have-permission-to-create-purchase-requisitions-for-a-selected-worker"></a><span data-ttu-id="3150e-121">Visa förberedare som har behörighet att skapa inköpsrekvisitioner för en vald arbetare</span><span class="sxs-lookup"><span data-stu-id="3150e-121">View preparers who have permission to create purchase requisitions for a selected worker</span></span>
1. <span data-ttu-id="3150e-122">Välj **Per beställare** i fältet **Aktuell vy**.</span><span class="sxs-lookup"><span data-stu-id="3150e-122">In the **Current view** field, select **By requester**.</span></span> <span data-ttu-id="3150e-123">Denna vy visar en lista med förberedare som har behörighet att skapa inköpsrekvisitioner för en vald anställd.</span><span class="sxs-lookup"><span data-stu-id="3150e-123">This view shows a list of preparers who have been granted permission to create purchase requisitions on behalf of a selected worker.</span></span>  
2. <span data-ttu-id="3150e-124">Använd snabbfiltret för att hitta den arbetare som du just lade till som beställaren.</span><span class="sxs-lookup"><span data-stu-id="3150e-124">Use the Quick Filter to find the worker that you just added as the requester.</span></span>
3. <span data-ttu-id="3150e-125">Välj beställare.</span><span class="sxs-lookup"><span data-stu-id="3150e-125">Select the requester.</span></span> <span data-ttu-id="3150e-126">Förberedarelistan visar personer som har behörighet att beställa artiklar på uppdrag av beställaren som är vald i vänstra fönstret.</span><span class="sxs-lookup"><span data-stu-id="3150e-126">The Preparer list shows the people who have permission to order items on behalf of the requester who is selected in the left pane.</span></span>  <span data-ttu-id="3150e-127">Du kan lägga till ytterligare förberedare här.</span><span class="sxs-lookup"><span data-stu-id="3150e-127">You can add additional preparers here.</span></span> <span data-ttu-id="3150e-128">Denna vy låter dig också bevilja beställarebehörighet att skapa rekvisitioner i juridiska personer och driftenheter som inte är den personens primära juridiska person eller driftenhet.</span><span class="sxs-lookup"><span data-stu-id="3150e-128">This view also lets you grant the requester permission to create requisitions in legal entities and operating units that aren't that person's primary legal entity or operating unit.</span></span>  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]