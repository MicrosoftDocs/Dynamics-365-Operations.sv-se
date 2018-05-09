--- 
title: "Ställ in behörigheter att beställa produkter för någon annans räkning"
description: "I den här proceduren visas hur du beviljar arbetare behörighet att förbereda inköpsrekvisitioner på uppdrag av andra arbetare."
author: mkirknel
manager: AnnBe
ms.date: 08/23/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 30d91d2ffab74250b3a8a46d7b7c5441a94d8dfd
ms.contentlocale: sv-se
ms.lasthandoff: 05/08/2018

---
# <a name="set-up-permissions-for-ordering-products-on-behalf-of-someone-else"></a><span data-ttu-id="17e85-103">Ställ in behörigheter att beställa produkter för någon annans räkning</span><span class="sxs-lookup"><span data-stu-id="17e85-103">Set up permissions for ordering products on behalf of someone else</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="17e85-104">I den här proceduren visas hur du beviljar arbetare behörighet att förbereda inköpsrekvisitioner på uppdrag av andra arbetare.</span><span class="sxs-lookup"><span data-stu-id="17e85-104">This procedure shows how to grant workers permission to prepare purchase requisitions on behalf of other workers.</span></span> <span data-ttu-id="17e85-105">Med andra ord kan en "förberedare" av inköpsrekvisitionen skapa en rekvisition för en annan ”begärare”.</span><span class="sxs-lookup"><span data-stu-id="17e85-105">In other words, a purchase requisition “preparer” can create a requisition for another “requester.”</span></span> <span data-ttu-id="17e85-106">Denna procedur visar också hur du beviljar en anställd behörighet till orderartiklar och tjänster i olika juridiska personer eller driftenheter.</span><span class="sxs-lookup"><span data-stu-id="17e85-106">The procedure also shows how to grant a worker permission to order items and services in different legal entities or operating units.</span></span> <span data-ttu-id="17e85-107">Dessa inställningsuppgifter utförs normalt av en inköpschef.</span><span class="sxs-lookup"><span data-stu-id="17e85-107">Typically, these tasks are performed by a purchasing manager.</span></span> <span data-ttu-id="17e85-108">Du kan använda den här proceduren antingen i data för demonstrationsföretaget USMF eller på dina egna data.</span><span class="sxs-lookup"><span data-stu-id="17e85-108">You can use this procedure either on data for the USMF demo company or on your own data.</span></span>


## <a name="grant-permission-to-enter-purchase-requisitions-on-behalf-of-another-worker"></a><span data-ttu-id="17e85-109">Bevilja behörighet att ange inköpsrekvisitioner på uppdrag av en annan anställd</span><span class="sxs-lookup"><span data-stu-id="17e85-109">Grant permission to enter purchase requisitions on behalf of another worker</span></span>
1. <span data-ttu-id="17e85-110">Gå till Anskaffning och källa > Inställningar > Policyer > Behörighet för inköpsrekvisition.</span><span class="sxs-lookup"><span data-stu-id="17e85-110">Go to Procurement and sourcing > Setup > Policies > Purchase requisition permissions.</span></span>
    * <span data-ttu-id="17e85-111">Kontrollera att fältet Aktuell vy är inställd på Per förberedare.</span><span class="sxs-lookup"><span data-stu-id="17e85-111">Make sure that the Current view field is set to By preparer.</span></span>  <span data-ttu-id="17e85-112">Listan i vänstra fönstret visar personer som kan beviljas behörighet att förbereda rekvisitioner på uppdrag av andra personer.</span><span class="sxs-lookup"><span data-stu-id="17e85-112">The list in the left pane shows the people who can be granted permission to prepare requisitions on behalf of other people.</span></span>  
2. <span data-ttu-id="17e85-113">Välj den person som ska beviljas behörighet (förberedaren).</span><span class="sxs-lookup"><span data-stu-id="17e85-113">Select the person to grant permission to (the preparer).</span></span>
3. <span data-ttu-id="17e85-114">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="17e85-114">Click Add.</span></span>
4. <span data-ttu-id="17e85-115">Hitta och välj den person om du vill lägga till som en beställare.</span><span class="sxs-lookup"><span data-stu-id="17e85-115">Find and select the person to add as a requester.</span></span>
    * <span data-ttu-id="17e85-116">Beställaren är den person som förberedaren kan skapa rekvisitioner för.</span><span class="sxs-lookup"><span data-stu-id="17e85-116">The requester is the person that the preparer can create requisitions on behalf of.</span></span>  
    * <span data-ttu-id="17e85-117">I fältet Auktorisering väljer du Specifik och förberedaren ska kunna skapa inköpsrekvisitioner på uppdrag av den valda arbetaren.</span><span class="sxs-lookup"><span data-stu-id="17e85-117">In the Authorization field, select Specific if the preparer should be able to create purchase requisitions on behalf of the selected worker.</span></span> <span data-ttu-id="17e85-118">Välj Rapporteringen om förberedaren även ska kunna skapa inköpsrekvisitioner på uppdrag av alla arbetare som rapporterar till den arbetaren.</span><span class="sxs-lookup"><span data-stu-id="17e85-118">Select Reporting if the preparer should also be able to create purchase requisitions on behalf of all workers who report to that worker.</span></span>  
5. <span data-ttu-id="17e85-119">Ange ett datum i fältet Giltighet.</span><span class="sxs-lookup"><span data-stu-id="17e85-119">In the Effective field, enter a date.</span></span>
6. <span data-ttu-id="17e85-120">I fältet Utgång anger du datum.</span><span class="sxs-lookup"><span data-stu-id="17e85-120">In the Expiration field, enter a date.</span></span>

## <a name="view-preparers-who-have-permission-to-create-purchase-requisitions-for-a-selected-worker"></a><span data-ttu-id="17e85-121">Visa förberedare som har behörighet att skapa inköpsrekvisitioner för en vald arbetare</span><span class="sxs-lookup"><span data-stu-id="17e85-121">View preparers who have permission to create purchase requisitions for a selected worker</span></span>
1. <span data-ttu-id="17e85-122">Välj ”Per beställare” i fältet Aktuell vy.</span><span class="sxs-lookup"><span data-stu-id="17e85-122">In the Current view field, select 'By requester'.</span></span>
    * <span data-ttu-id="17e85-123">Denna vy visar en lista med förberedare som har behörighet att skapa inköpsrekvisitioner för en vald anställd.</span><span class="sxs-lookup"><span data-stu-id="17e85-123">This view shows a list of preparers who have been granted permission to create purchase requisitions on behalf of a selected worker.</span></span>  
2. <span data-ttu-id="17e85-124">Använd snabbfiltret för att hitta den arbetare som du just lade till som beställaren.</span><span class="sxs-lookup"><span data-stu-id="17e85-124">Use the Quick Filter to find the worker that you just added as the requester.</span></span>
3. <span data-ttu-id="17e85-125">Välj beställare.</span><span class="sxs-lookup"><span data-stu-id="17e85-125">Select the requester.</span></span>
    * <span data-ttu-id="17e85-126">Förberedarelistan visar personer som har behörighet att beställa artiklar på uppdrag av beställaren som är vald i vänstra fönstret.</span><span class="sxs-lookup"><span data-stu-id="17e85-126">The Preparer list shows the people who have permission to order items on behalf of the requester who is selected in the left pane.</span></span>   <span data-ttu-id="17e85-127">Du kan lägga till ytterligare förberedare här.</span><span class="sxs-lookup"><span data-stu-id="17e85-127">You can add additional preparers here.</span></span>   <span data-ttu-id="17e85-128">Denna vy låter dig också bevilja beställarebehörighet att skapa rekvisitioner i juridiska personer och driftenheter som inte är den personens primära juridiska person eller driftenhet.</span><span class="sxs-lookup"><span data-stu-id="17e85-128">This view also lets you grant the requester permission to create requisitions in legal entities and operating units that aren't that person's primary legal entity or operating unit.</span></span>  


