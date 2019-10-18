---
title: Granska fakturor och nyckeldata i LR-system
description: När du får en faktura från en leverantör för varor eller tjänster på en inköpsorder kanske affärsprocesserna kräver att varorna eller tjänsterna inlevereras innan fakturan godkänns för betalning.
author: saraschi2
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchTable, PurchCreateOrder, PurchEditLines, VendEditInvoice, VendEditInvoiceDefaultQuantityForLinesDropDialog,  VendJournalMatch_PackingSlip, VendInvoiceMatchingDetails
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: c6e8967fe4db67ff98fc7093792bdb82b73a33d9
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/27/2019
ms.locfileid: "2179912"
---
# <a name="audit-invoices-and-key-data-in-ap-system"></a><span data-ttu-id="bdf6c-103">Granska fakturor och nyckeldata i LR-system</span><span class="sxs-lookup"><span data-stu-id="bdf6c-103">Audit invoices and key data in AP system</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="bdf6c-104">När du får en faktura från en leverantör för varor eller tjänster på en inköpsorder kanske affärsprocesserna kräver att varorna eller tjänsterna inlevereras innan fakturan godkänns för betalning.</span><span class="sxs-lookup"><span data-stu-id="bdf6c-104">When you receive an invoice from a vendor for goods or services on a purchase order, the business processes might require that the goods or services be received before the invoice can be approved for payment.</span></span> <span data-ttu-id="bdf6c-105">Innan du börjar kontrollerar du att konfigurationsnyckeln för fakturamatchning har valts.</span><span class="sxs-lookup"><span data-stu-id="bdf6c-105">Before you begin, make sure that the Invoice matching configuration key is selected.</span></span> 

<span data-ttu-id="bdf6c-106">På sidan med leverantörsreskontraparametrarna kontrollerar du att alternativet Aktivera fakturamatchningsvalidering har valts, fältet Bokför faktura med avvikelser har ställts in som Begär godkännande och fältet Radmatchningspolicy har ställts in som Trevägsmatchning.</span><span class="sxs-lookup"><span data-stu-id="bdf6c-106">In the Accounts payable parameters page, ensure that the Enable invoice matching validation option is selected, the Post invoice with discrepancies field is set to Require approval, and the Line matching policy field is set to Three-way matching.</span></span>

<span data-ttu-id="bdf6c-107">I den här proceduren används demonstrationsföretaget USMF.</span><span class="sxs-lookup"><span data-stu-id="bdf6c-107">This procedure uses the USMF demo company.</span></span> <span data-ttu-id="bdf6c-108">Leverantörsreskontrachefsrollen eller redovisningschefsrollen ska utföra stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="bdf6c-108">The accounts payable manager or accounting manager role would perform these steps.</span></span>


## <a name="create-a-purchase-order"></a><span data-ttu-id="bdf6c-109">Skapa en inköpsorder</span><span class="sxs-lookup"><span data-stu-id="bdf6c-109">Create a purchase order</span></span>
1. <span data-ttu-id="bdf6c-110">Gå till **Alla inköpsorder**.</span><span class="sxs-lookup"><span data-stu-id="bdf6c-110">Go to **All purchase orders**.</span></span>
2. <span data-ttu-id="bdf6c-111">Klicka på **Ny**.</span><span class="sxs-lookup"><span data-stu-id="bdf6c-111">Click **New**.</span></span>
3. <span data-ttu-id="bdf6c-112">I fältet **Leverantörskonto**, skriv ett värde.</span><span class="sxs-lookup"><span data-stu-id="bdf6c-112">In the **Vendor account** field, type a value.</span></span>
4. <span data-ttu-id="bdf6c-113">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="bdf6c-113">Click **OK**.</span></span>
5. <span data-ttu-id="bdf6c-114">Klicka på **Lägg till rad**.</span><span class="sxs-lookup"><span data-stu-id="bdf6c-114">Click **Add line**.</span></span>
6. <span data-ttu-id="bdf6c-115">I fältet **Artikelnummer**, skriv ett värde.</span><span class="sxs-lookup"><span data-stu-id="bdf6c-115">In the **Item number** field, type a value.</span></span>
7. <span data-ttu-id="bdf6c-116">I åtgärdsrutan, klicka på **Köp**.</span><span class="sxs-lookup"><span data-stu-id="bdf6c-116">On the Action Pane, click **Purchase**.</span></span>
8. <span data-ttu-id="bdf6c-117">Klicka på **Bekräfta**.</span><span class="sxs-lookup"><span data-stu-id="bdf6c-117">Click **Confirm**.</span></span>

## <a name="post-a-product-receipt"></a><span data-ttu-id="bdf6c-118">Bokför en produktinleverans</span><span class="sxs-lookup"><span data-stu-id="bdf6c-118">Post a product receipt</span></span>
1. <span data-ttu-id="bdf6c-119">I åtgärdsrutan, klicka på **Ta emot**.</span><span class="sxs-lookup"><span data-stu-id="bdf6c-119">On the Action Pane, click **Receive**.</span></span>
2. <span data-ttu-id="bdf6c-120">Klicka på **Produktinleverans**.</span><span class="sxs-lookup"><span data-stu-id="bdf6c-120">Click **Product receipt**.</span></span>
3. <span data-ttu-id="bdf6c-121">I fältet **Produktinleverans**, skriv ett värde.</span><span class="sxs-lookup"><span data-stu-id="bdf6c-121">In the **Product receipt** field, type a value.</span></span>
4. <span data-ttu-id="bdf6c-122">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="bdf6c-122">Click **OK**.</span></span>

## <a name="record-and-match-a-vendor-invoice-to-a-product-receipt"></a><span data-ttu-id="bdf6c-123">Registrera och matcha en leverantörsfaktura mot en produktinleverans</span><span class="sxs-lookup"><span data-stu-id="bdf6c-123">Record and match a vendor invoice to a product receipt</span></span>
1. <span data-ttu-id="bdf6c-124">I åtgärdsrutan, klicka på **Faktura > Faktura**.</span><span class="sxs-lookup"><span data-stu-id="bdf6c-124">On the Action Pane, click **Invoice > Invoice**.</span></span>
2. <span data-ttu-id="bdf6c-125">I fältet **Antal**, skriv ett värde.</span><span class="sxs-lookup"><span data-stu-id="bdf6c-125">In the **Number** field, type a value.</span></span>
3. <span data-ttu-id="bdf6c-126">Klicka på **Standard från: Beställd kvantitet** för att öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="bdf6c-126">Click **Default from: Ordered quantity** to open the drop dialog.</span></span>
4. <span data-ttu-id="bdf6c-127">I fältet **Standardkvantitet för rader**, välj ett alternativ.</span><span class="sxs-lookup"><span data-stu-id="bdf6c-127">In the **Default quantity for lines** field, select an option.</span></span>
5. <span data-ttu-id="bdf6c-128">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="bdf6c-128">Click **OK**.</span></span>
6. <span data-ttu-id="bdf6c-129">Klicka på **Ja**.</span><span class="sxs-lookup"><span data-stu-id="bdf6c-129">Click **Yes**.</span></span>
7. <span data-ttu-id="bdf6c-130">Klicka på **Matcha produktinleveranser**.</span><span class="sxs-lookup"><span data-stu-id="bdf6c-130">Click **Match product receipts**.</span></span>
8. <span data-ttu-id="bdf6c-131">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="bdf6c-131">Click **OK**.</span></span>
9. <span data-ttu-id="bdf6c-132">Klicka på **Granska** i åtgärdsrutan.</span><span class="sxs-lookup"><span data-stu-id="bdf6c-132">On the Action Pane, click **Review**.</span></span>
10. <span data-ttu-id="bdf6c-133">Klicka på **Matcha detaljer**.</span><span class="sxs-lookup"><span data-stu-id="bdf6c-133">Click **Matching details**.</span></span>

