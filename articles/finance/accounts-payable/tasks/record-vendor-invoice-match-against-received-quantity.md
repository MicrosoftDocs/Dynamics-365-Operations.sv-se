---
title: Registrera leverantörsfakturan och matcha mot mottagen kvantitet
description: När du får en faktura från en leverantör för varor eller tjänster på en inköpsorder kanske affärsprocesserna kräver att varorna eller tjänsterna inlevereras innan fakturan godkänns för betalning.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchTable, PurchCreateOrder, PurchEditLines, VendEditInvoice, VendEditInvoiceDefaultQuantityForLinesDropDialog,  VendJournalMatch_PackingSlip, VendInvoiceMatchingDetails
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 66f3b3444b9ff6a93d83c97f1d962c3bdb0699c9
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5227122"
---
# <a name="record-vendor-invoice-and-match-against-received-quantity"></a><span data-ttu-id="9ecd2-103">Registrera leverantörsfakturan och matcha mot mottagen kvantitet</span><span class="sxs-lookup"><span data-stu-id="9ecd2-103">Record vendor invoice and match against received quantity</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="9ecd2-104">När du får en faktura från en leverantör för varor eller tjänster på en inköpsorder kanske affärsprocesserna kräver att varorna eller tjänsterna inlevereras innan fakturan godkänns för betalning.</span><span class="sxs-lookup"><span data-stu-id="9ecd2-104">When you receive an invoice from a vendor for goods or services on a purchase order, the business processes might require that the goods or services be received before the invoice can be approved for payment.</span></span> <span data-ttu-id="9ecd2-105">Innan du börjar kontrollerar du att konfigurationsnyckeln för fakturamatchning har valts.</span><span class="sxs-lookup"><span data-stu-id="9ecd2-105">Before you begin, make sure that the Invoice matching configuration key is selected.</span></span> 

<span data-ttu-id="9ecd2-106">På sidan med leverantörsreskontraparametrarna kontrollerar du att alternativet Aktivera fakturamatchningsvalidering har valts, fältet Bokför faktura med avvikelser har ställts in som Begär godkännande och fältet Radmatchningspolicy har ställts in som Trevägsmatchning.</span><span class="sxs-lookup"><span data-stu-id="9ecd2-106">In the Accounts payable parameters page, ensure that the Enable invoice matching validation option is selected, the Post invoice with discrepancies field is set to Require approval, and the Line matching policy field is set to Three-way matching.</span></span>

<span data-ttu-id="9ecd2-107">I den här proceduren används demonstrationsföretaget USMF.</span><span class="sxs-lookup"><span data-stu-id="9ecd2-107">This procedure uses the USMF demo company.</span></span> <span data-ttu-id="9ecd2-108">Leverantörsreskontrachefsrollen eller redovisningschefsrollen ska utföra stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="9ecd2-108">The accounts payable manager or accounting manager role would perform these steps.</span></span>


## <a name="create-a-purchase-order"></a><span data-ttu-id="9ecd2-109">Skapa en inköpsorder</span><span class="sxs-lookup"><span data-stu-id="9ecd2-109">Create a purchase order</span></span>
1. <span data-ttu-id="9ecd2-110">Gå till Alla inköpsorder.</span><span class="sxs-lookup"><span data-stu-id="9ecd2-110">Go to All purchase orders.</span></span>
2. <span data-ttu-id="9ecd2-111">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="9ecd2-111">Click New.</span></span>
3. <span data-ttu-id="9ecd2-112">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Leverantörskonto.</span><span class="sxs-lookup"><span data-stu-id="9ecd2-112">In the Vendor account field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="9ecd2-113">Ange ett värde i fältet Leverantörskonto.</span><span class="sxs-lookup"><span data-stu-id="9ecd2-113">In the Vendor account field, type a value.</span></span>
5. <span data-ttu-id="9ecd2-114">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="9ecd2-114">Click OK.</span></span>
6. <span data-ttu-id="9ecd2-115">Klicka på Lägg till rad.</span><span class="sxs-lookup"><span data-stu-id="9ecd2-115">Click Add line.</span></span>
7. <span data-ttu-id="9ecd2-116">Skriv ett värde i fältet Artikelnummer.</span><span class="sxs-lookup"><span data-stu-id="9ecd2-116">In the Item number field, type a value.</span></span>
8. <span data-ttu-id="9ecd2-117">Klicka på Inköp i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="9ecd2-117">On the Action Pane, click Purchase.</span></span>
9. <span data-ttu-id="9ecd2-118">Klicka på Bekräfta.</span><span class="sxs-lookup"><span data-stu-id="9ecd2-118">Click Confirm.</span></span>

## <a name="post-a-product-receipt"></a><span data-ttu-id="9ecd2-119">Bokför en produktinleverans</span><span class="sxs-lookup"><span data-stu-id="9ecd2-119">Post a product receipt</span></span>
1. <span data-ttu-id="9ecd2-120">Klicka på Ta emot i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="9ecd2-120">On the Action Pane, click Receive.</span></span>
2. <span data-ttu-id="9ecd2-121">Klicka på Produktinleverans.</span><span class="sxs-lookup"><span data-stu-id="9ecd2-121">Click Product receipt.</span></span>
3. <span data-ttu-id="9ecd2-122">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="9ecd2-122">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="9ecd2-123">Skriv ett värde i fältet Produktinleverans.</span><span class="sxs-lookup"><span data-stu-id="9ecd2-123">In the Product receipt field, type a value.</span></span>
5. <span data-ttu-id="9ecd2-124">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="9ecd2-124">Click OK.</span></span>

## <a name="record-and-match-a-vendor-invoice-to-a-product-receipt"></a><span data-ttu-id="9ecd2-125">Registrera och matcha en leverantörsfaktura mot en produktinleverans</span><span class="sxs-lookup"><span data-stu-id="9ecd2-125">Record and match a vendor invoice to a product receipt</span></span>
1. <span data-ttu-id="9ecd2-126">Klicka på Faktura i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="9ecd2-126">On the Action Pane, click Invoice.</span></span>
2. <span data-ttu-id="9ecd2-127">Klicka på Faktura.</span><span class="sxs-lookup"><span data-stu-id="9ecd2-127">Click Invoice.</span></span>
3. <span data-ttu-id="9ecd2-128">Ange ett värde i fältet Antal.</span><span class="sxs-lookup"><span data-stu-id="9ecd2-128">In the Number field, type a value.</span></span>
4. <span data-ttu-id="9ecd2-129">Klicka på Standard från: Beställd kvantitet för att öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="9ecd2-129">Click Default from: Ordered quantity to open the drop dialog.</span></span>
5. <span data-ttu-id="9ecd2-130">I fältet Standardkvantitet för rader, välj ett alternativ.</span><span class="sxs-lookup"><span data-stu-id="9ecd2-130">In the Default quantity for lines field, select an option.</span></span>
6. <span data-ttu-id="9ecd2-131">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="9ecd2-131">Click OK.</span></span>
7. <span data-ttu-id="9ecd2-132">Klicka på Ja.</span><span class="sxs-lookup"><span data-stu-id="9ecd2-132">Click Yes.</span></span>
8. <span data-ttu-id="9ecd2-133">Klicka på Matcha produktinleveranser.</span><span class="sxs-lookup"><span data-stu-id="9ecd2-133">Click Match product receipts.</span></span>
9. <span data-ttu-id="9ecd2-134">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="9ecd2-134">Click OK.</span></span>
10. <span data-ttu-id="9ecd2-135">Klicka på Granska i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="9ecd2-135">On the Action Pane, click Review.</span></span>
11. <span data-ttu-id="9ecd2-136">Klicka på Matcha detaljer.</span><span class="sxs-lookup"><span data-stu-id="9ecd2-136">Click Matching details.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]