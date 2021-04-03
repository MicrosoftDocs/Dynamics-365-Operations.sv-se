---
title: Skapa en ny order för lagerpåfyllnad för försändelse
description: I det här avsnittet visas hur du skapar en lagerpåfyllnadsorder för försändelse, där du kan följa den förväntade leveransen från en leverantör till ditt försändelselager.
author: RichardLuan
manager: tfehr
ms.date: 08/19/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ConsignmentReplenishmentOrder, ConsignmentReplenishmentOrderCreate, InventTrans, ConsignmentDraftReplenishmentOrderJournal, InventOnhandMovement, InventOnhandItem, InventItemIdLookupSimple, ConsignmentProductReceiptJournal, ConsignmentReplenishmentOrderLineQuantity
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: riluan
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 09b6b69d72d0a5f429dbd8cba6faefd4b1a057e4
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5264884"
---
# <a name="create-a-consignment-replenishment-order"></a><span data-ttu-id="0ecbf-103">Skapa en ny order för lagerpåfyllnad för försändelse</span><span class="sxs-lookup"><span data-stu-id="0ecbf-103">Create a consignment replenishment order</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="0ecbf-104">I det här avsnittet visas hur du skapar en lagerpåfyllnadsorder för försändelse, där du kan följa den förväntade leveransen från en leverantör till ditt försändelselager.</span><span class="sxs-lookup"><span data-stu-id="0ecbf-104">This topic explains how to create a consignment replenishment order where you can track the expected delivery from a vendor into your consignment inventory.</span></span> <span data-ttu-id="0ecbf-105">Den visar även hur du registrerar en inleverans av produkter, så att försändelselagret är registrerat som lagerbehållning som ägs av leverantören.</span><span class="sxs-lookup"><span data-stu-id="0ecbf-105">It also shows how to record a receipt of products so that the consignment inventory is registered as on-hand inventory owned by the vendor.</span></span> <span data-ttu-id="0ecbf-106">Denna procedur görs normalt av ett anskaffningsproffs.</span><span class="sxs-lookup"><span data-stu-id="0ecbf-106">This procedure would typically be done by a procurement professional.</span></span> <span data-ttu-id="0ecbf-107">Du kan använda den här guiden i demonstrationsföretaget USMF.</span><span class="sxs-lookup"><span data-stu-id="0ecbf-107">You can use this guide in demo data company USMF.</span></span> <span data-ttu-id="0ecbf-108">Denna procedur är avsedd för en funktion som lades till i Dynamics 365 for Operations, version 1611.</span><span class="sxs-lookup"><span data-stu-id="0ecbf-108">This procedure is for a feature that was added in Dynamics 365 for Operations, version 1611.</span></span>

## <a name="create-a-consignment-replenishment-order"></a><span data-ttu-id="0ecbf-109">Skapa en ny order för lagerpåfyllnad för försändelse</span><span class="sxs-lookup"><span data-stu-id="0ecbf-109">Create a consignment replenishment order</span></span>
1. <span data-ttu-id="0ecbf-110">I navigeringsfönstret, gå till **Moduler > Anskaffning och källa > Försändelse > Order för försändelseåteranskaffning**.</span><span class="sxs-lookup"><span data-stu-id="0ecbf-110">In the navigation pane, go to **Modules > Procurement and sourcing > Consignment > Consignment replenishment orders**.</span></span>
2. <span data-ttu-id="0ecbf-111">Välj **Ny**.</span><span class="sxs-lookup"><span data-stu-id="0ecbf-111">Select **New**.</span></span>
3. <span data-ttu-id="0ecbf-112">I fältet **Leverantörskonto** väljer du leverantör **US-104** (du måste välja en leverantör som är registrerad som en ägare på sidan **lagerägare**).</span><span class="sxs-lookup"><span data-stu-id="0ecbf-112">In the **Vendor account** field, select vendor **US-104** (you must select a vendor that's registered as an owner in the **inventory owners** page).</span></span> 
4. <span data-ttu-id="0ecbf-113">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="0ecbf-113">Select **OK**.</span></span>
5. <span data-ttu-id="0ecbf-114">Välj **Markera rad**.</span><span class="sxs-lookup"><span data-stu-id="0ecbf-114">Select **Add line**.</span></span>
6. <span data-ttu-id="0ecbf-115">I fältet **Artikelnummer** anger du `M9211CI` (du måste välja en artikel som har ställts in för försändelselager).</span><span class="sxs-lookup"><span data-stu-id="0ecbf-115">In the **Item number** field, type `M9211CI` (you must select an item that is set up for consignment inventory).</span></span>
7. <span data-ttu-id="0ecbf-116">Ange ett nummer i fältet **Kvantitet**.</span><span class="sxs-lookup"><span data-stu-id="0ecbf-116">In the **Quantity** field, enter a number.</span></span>
8. <span data-ttu-id="0ecbf-117">Ange ett datum i fältet **Begärt leveransdatum**.</span><span class="sxs-lookup"><span data-stu-id="0ecbf-117">In the **Requested delivery date** field, enter a date.</span></span> <span data-ttu-id="0ecbf-118">Begärda och bekräftade datum används av MRP-motorn för varornas förväntade ankomst.</span><span class="sxs-lookup"><span data-stu-id="0ecbf-118">The requested and confirmed dates are used by the MRP engine for the expected arrival of the goods.</span></span>  
9. <span data-ttu-id="0ecbf-119">Ange ett datum i fältet **Bekräftat leveransdatum.**</span><span class="sxs-lookup"><span data-stu-id="0ecbf-119">In the **Confirmed delivery date** field, enter a date.</span></span>
10. <span data-ttu-id="0ecbf-120">Visa avsnittet **Raddetaljer**.</span><span class="sxs-lookup"><span data-stu-id="0ecbf-120">Expand the **Line details** section.</span></span>
11. <span data-ttu-id="0ecbf-121">Välj fliken **Lagerdimensioner**.</span><span class="sxs-lookup"><span data-stu-id="0ecbf-121">Select the **Inventory dimensions** tab.</span></span>
12. <span data-ttu-id="0ecbf-122">Uppdatera sidan om du vill visa ägaren i fältet **Ägare till lagerdimensioner**.</span><span class="sxs-lookup"><span data-stu-id="0ecbf-122">To show the owner in the **Inventory dimensions owner** field, refresh the page.</span></span> <span data-ttu-id="0ecbf-123">Leverantören US-104 anges nu som ägare.</span><span class="sxs-lookup"><span data-stu-id="0ecbf-123">Vendor US-104 is now listed as the owner.</span></span>  

## <a name="check-the-inventory-transaction-status"></a><span data-ttu-id="0ecbf-124">Kontrollera statusen för lagertransaktion</span><span class="sxs-lookup"><span data-stu-id="0ecbf-124">Check the inventory transaction status</span></span>
1. <span data-ttu-id="0ecbf-125">Välj **Lager**.</span><span class="sxs-lookup"><span data-stu-id="0ecbf-125">Select **Inventory**.</span></span>
2. <span data-ttu-id="0ecbf-126">Markera **transaktioner**</span><span class="sxs-lookup"><span data-stu-id="0ecbf-126">Select **Transactions**.</span></span>
3. <span data-ttu-id="0ecbf-127">På den önskade raden, observera att fältet **Inleverans** anges som **Beställt**.</span><span class="sxs-lookup"><span data-stu-id="0ecbf-127">In the desired row, notice that the **Receipt** field is set to **Ordered**.</span></span>  
4. <span data-ttu-id="0ecbf-128">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="0ecbf-128">Close the page.</span></span>

## <a name="receive-items"></a><span data-ttu-id="0ecbf-129">Ta emot artiklar</span><span class="sxs-lookup"><span data-stu-id="0ecbf-129">Receive items</span></span>
1. <span data-ttu-id="0ecbf-130">Välj **produktinleverans**</span><span class="sxs-lookup"><span data-stu-id="0ecbf-130">Select **Product receipt**.</span></span>
2. <span data-ttu-id="0ecbf-131">Ange ett värde i fältet **Extern produktinleverans**.</span><span class="sxs-lookup"><span data-stu-id="0ecbf-131">In the **External product receipt** field, type a value.</span></span>
3. <span data-ttu-id="0ecbf-132">Ange ett värde som är lägre än det som visas i fältet **Kvantitet**.</span><span class="sxs-lookup"><span data-stu-id="0ecbf-132">In the **Quantity** field, enter a number that's lower than the number that's shown there.</span></span> 
4. <span data-ttu-id="0ecbf-133">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="0ecbf-133">Select **OK**.</span></span>

## <a name="check-the-on-hand-inventory"></a><span data-ttu-id="0ecbf-134">Kontrollera behållningslagret</span><span class="sxs-lookup"><span data-stu-id="0ecbf-134">Check the on-hand inventory</span></span>
1. <span data-ttu-id="0ecbf-135">Välj **Lager**.</span><span class="sxs-lookup"><span data-stu-id="0ecbf-135">Select **Inventory**.</span></span>
2. <span data-ttu-id="0ecbf-136">Välj **Behållning**.</span><span class="sxs-lookup"><span data-stu-id="0ecbf-136">Select **On-hand**.</span></span>
3. <span data-ttu-id="0ecbf-137">Välj **Översikt**.</span><span class="sxs-lookup"><span data-stu-id="0ecbf-137">Select **Overview**.</span></span> <span data-ttu-id="0ecbf-138">Artiklarna som har inlevererats som ett försändelselager ägt av leverantören finns tillgängliga i lager.</span><span class="sxs-lookup"><span data-stu-id="0ecbf-138">The items that have been received as consignment inventory owned by the vendor are available on-hand.</span></span> <span data-ttu-id="0ecbf-139">Återstående kvantitet i lagerpåfyllnadsordern för försändelse anges i fältet **Totalt beställt**.</span><span class="sxs-lookup"><span data-stu-id="0ecbf-139">The remaining quantity on the consignment replenishment order is shown in the **Ordered in total** field.</span></span>  
4. <span data-ttu-id="0ecbf-140">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="0ecbf-140">Close the page.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]