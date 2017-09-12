---
title: "Skapa en ny order för försändelseåteranskaffning"
description: "I den här proceduren visas hur du skapar en lagerpåfyllnadsorder för försändelse, där du kan följa den förväntade leveransen från en leverantör till ditt försändelselager."
author: mkirknel
manager: AnnBe
ms.date: 10/13/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0e7f66cccd76e5326fce75d1a13aff294c16fb9b
ms.openlocfilehash: 6286e8f52b8131a8e4779f1e11d84233b8e0760e
ms.contentlocale: sv-se
ms.lasthandoff: 09/12/2017

---
# <a name="create-a-consignment-replenishment-order"></a><span data-ttu-id="324b7-103">Skapa en ny order för försändelseåteranskaffning</span><span class="sxs-lookup"><span data-stu-id="324b7-103">Create a consignment replenishment order</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="324b7-104">I den här proceduren visas hur du skapar en lagerpåfyllnadsorder för försändelse, där du kan följa den förväntade leveransen från en leverantör till ditt försändelselager.</span><span class="sxs-lookup"><span data-stu-id="324b7-104">This procedure shows how to create a consignment replenishment order where you can track the expected delivery from a vendor into your consignment inventory.</span></span> <span data-ttu-id="324b7-105">Den visar även hur du registrerar en inleverans av produkter, så att försändelselagret är registrerat som lagerbehållning som ägs av leverantören.</span><span class="sxs-lookup"><span data-stu-id="324b7-105">It also shows how to record a receipt of products so that the consignment inventory is registered as on-hand inventory owned by the vendor.</span></span> <span data-ttu-id="324b7-106">Denna procedur görs normalt av ett anskaffningsproffs.</span><span class="sxs-lookup"><span data-stu-id="324b7-106">This procedure would typically be done by a procurement professional.</span></span> <span data-ttu-id="324b7-107">Du kan använda den här guiden i demonstrationsföretaget USMF.</span><span class="sxs-lookup"><span data-stu-id="324b7-107">You can use this guide in demo data company USMF.</span></span> <span data-ttu-id="324b7-108">Denna procedur är avsedd för en funktion som lades till i Dynamics 365 for Operations, version 1611.</span><span class="sxs-lookup"><span data-stu-id="324b7-108">This procedure is for a feature that was added in Dynamics 365 for Operations, version 1611.</span></span>




## <a name="create-a-consignment-replenishment-order"></a><span data-ttu-id="324b7-109">Skapa en ny order för försändelseåteranskaffning</span><span class="sxs-lookup"><span data-stu-id="324b7-109">Create a consignment replenishment order</span></span>
1. <span data-ttu-id="324b7-110">Gå till Anskaffning och källa > Försändelse > Order för försändelseåteranskaffning.</span><span class="sxs-lookup"><span data-stu-id="324b7-110">Go to Procurement and sourcing > Consignment > Consignment replenishment orders.</span></span>
2. <span data-ttu-id="324b7-111">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="324b7-111">Click New.</span></span>
3. <span data-ttu-id="324b7-112">Ange leverantör US-104 i Vendor account.</span><span class="sxs-lookup"><span data-stu-id="324b7-112">In the Vendor account field, select vendor US-104.</span></span>
    * <span data-ttu-id="324b7-113">Du måste välja en leverantör som har registrerats som en ägare i sida för lagerägare.</span><span class="sxs-lookup"><span data-stu-id="324b7-113">You must select a vendor that’s registered as an owner in the Inventory owners page.</span></span>  
4. <span data-ttu-id="324b7-114">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="324b7-114">Click OK.</span></span>
5. <span data-ttu-id="324b7-115">Klicka på Lägg till rad.</span><span class="sxs-lookup"><span data-stu-id="324b7-115">Click Add line.</span></span>
6. <span data-ttu-id="324b7-116">I fältet Item number anger du M9211CI.</span><span class="sxs-lookup"><span data-stu-id="324b7-116">In the Item number field, type M9211CI.</span></span>
    * <span data-ttu-id="324b7-117">Du måste välja en artikel som har ställts in för försändelselager.</span><span class="sxs-lookup"><span data-stu-id="324b7-117">You must select an item that is set up for consignment inventory.</span></span>  
7. <span data-ttu-id="324b7-118">Ange ett tal i fältet Kvantitet.</span><span class="sxs-lookup"><span data-stu-id="324b7-118">In the Quantity field, enter a number.</span></span>
8. <span data-ttu-id="324b7-119">Ange ett datum i fältet Requested delivery date.</span><span class="sxs-lookup"><span data-stu-id="324b7-119">In the Requested delivery date field, enter a date.</span></span>
    * <span data-ttu-id="324b7-120">Begärda och bekräftade datum används av MRP-motorn för varornas förväntade ankomst.</span><span class="sxs-lookup"><span data-stu-id="324b7-120">The requested and confirmed dates are used by the MRP engine for the expected arrival of the goods.</span></span>  
9. <span data-ttu-id="324b7-121">I fältet Bekräftat leveransdatum, ange ett datum.</span><span class="sxs-lookup"><span data-stu-id="324b7-121">In the Confirmed delivery date field, enter a date.</span></span>
10. <span data-ttu-id="324b7-122">Expandera avsnittet Radinformation.</span><span class="sxs-lookup"><span data-stu-id="324b7-122">Expand the Line details section.</span></span>
11. <span data-ttu-id="324b7-123">Klicka på fliken Lagerdimensioner.</span><span class="sxs-lookup"><span data-stu-id="324b7-123">Click the Inventory dimensions tab.</span></span>
12. <span data-ttu-id="324b7-124">Uppdatera sidan om du vill visa ägaren i fältet Inventory dimensions owner.</span><span class="sxs-lookup"><span data-stu-id="324b7-124">To show the owner in the Inventory dimensions owner field, refresh the page.</span></span>
    * <span data-ttu-id="324b7-125">Leverantören US-104 anges nu som ägare.</span><span class="sxs-lookup"><span data-stu-id="324b7-125">Vendor US-104 is now listed as the owner.</span></span>  

## <a name="check-the-inventory-transaction-status"></a><span data-ttu-id="324b7-126">Kontrollera statusen för lagertransaktion</span><span class="sxs-lookup"><span data-stu-id="324b7-126">Check the inventory transaction status</span></span>
1. <span data-ttu-id="324b7-127">Klicka på Lager.</span><span class="sxs-lookup"><span data-stu-id="324b7-127">Click Inventory.</span></span>
2. <span data-ttu-id="324b7-128">Klicka på Transaktioner.</span><span class="sxs-lookup"><span data-stu-id="324b7-128">Click Transactions.</span></span>
3. <span data-ttu-id="324b7-129">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="324b7-129">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="324b7-130">Observera att fältet Receipt anges som Ordered.</span><span class="sxs-lookup"><span data-stu-id="324b7-130">Notice that the Receipt field is set to Ordered.</span></span>  
4. <span data-ttu-id="324b7-131">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="324b7-131">Close the page.</span></span>

## <a name="receive-items"></a><span data-ttu-id="324b7-132">Ta emot artiklar</span><span class="sxs-lookup"><span data-stu-id="324b7-132">Receive items</span></span>
1. <span data-ttu-id="324b7-133">Klicka på Produktinleverans.</span><span class="sxs-lookup"><span data-stu-id="324b7-133">Click Product receipt.</span></span>
2. <span data-ttu-id="324b7-134">Ange ett värde i fältet External product receipt.</span><span class="sxs-lookup"><span data-stu-id="324b7-134">In the External product receipt field, type a value.</span></span>
3. <span data-ttu-id="324b7-135">Ange ett värde som är lägre än det som visas i fältet Quantity.</span><span class="sxs-lookup"><span data-stu-id="324b7-135">In the Quantity field, enter a number that’s lower than the number that’s shown there.</span></span>
4. <span data-ttu-id="324b7-136">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="324b7-136">Click OK.</span></span>

## <a name="check-the-on-hand-inventory"></a><span data-ttu-id="324b7-137">Kontrollera behållningslagret</span><span class="sxs-lookup"><span data-stu-id="324b7-137">Check the on-hand inventory</span></span>
1. <span data-ttu-id="324b7-138">Klicka på Lager.</span><span class="sxs-lookup"><span data-stu-id="324b7-138">Click Inventory.</span></span>
2. <span data-ttu-id="324b7-139">Klicka på On-hand.</span><span class="sxs-lookup"><span data-stu-id="324b7-139">Click On-hand.</span></span>
3. <span data-ttu-id="324b7-140">Klicka på Overview.</span><span class="sxs-lookup"><span data-stu-id="324b7-140">Click Overview.</span></span>
    * <span data-ttu-id="324b7-141">Artiklarna som har inlevererats som ett försändelselager ägt av leverantören finns tillgängliga i lager.</span><span class="sxs-lookup"><span data-stu-id="324b7-141">The items that have been received as consignment inventory owned by the vendor are available on-hand.</span></span> <span data-ttu-id="324b7-142">Återstående kvantitet i lagerpåfyllnadsordern för försändelse anges i fältet Ordered in total.</span><span class="sxs-lookup"><span data-stu-id="324b7-142">The remaining quantity on the consignment replenishment order is shown in the Ordered in total field.</span></span>  
4. <span data-ttu-id="324b7-143">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="324b7-143">Close the page.</span></span>
5. <span data-ttu-id="324b7-144">Klicka på Stäng.</span><span class="sxs-lookup"><span data-stu-id="324b7-144">Click Close.</span></span>

