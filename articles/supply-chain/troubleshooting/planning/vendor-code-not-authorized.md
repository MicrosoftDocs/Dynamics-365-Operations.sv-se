---
title: Leverantörskod som inte är auktoriserad för en viss produkt och ett visst datum
description: När du försöker fastställa en planerad beställning eller lägga till en rad i en inköpsorder får du ett felmeddelande som anger att leverantörskoden inte är auktoriserad för en produkt och ett datum.
author: ankubik
ms.date: 06/10/2021
ms.topic: troubleshooting
ms.search.form: ReqTransPO_ReqTransPoMarkFirm
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: ankubik
ms.search.validFrom: 2021-06-10
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: e6b1189e4fedfdb029f4b4503f0635133df9d87e
ms.sourcegitcommit: 18ca2df785e9656fdd4e8c0734eca2b2624fda10
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/22/2021
ms.locfileid: "6294185"
---
# <a name="vendor-code-isnt-authorized-for-a-specific-product-and-date"></a><span data-ttu-id="f0087-103">Leverantörskod som inte är auktoriserad för en viss produkt och ett visst datum</span><span class="sxs-lookup"><span data-stu-id="f0087-103">Vendor code isn't authorized for a specific product and date</span></span>

<span data-ttu-id="f0087-104">Felkod: SYP4881415</span><span class="sxs-lookup"><span data-stu-id="f0087-104">Error code: SYP4881415</span></span>

## <a name="symptoms"></a><span data-ttu-id="f0087-105">Symtom</span><span class="sxs-lookup"><span data-stu-id="f0087-105">Symptoms</span></span>

<span data-ttu-id="f0087-106">När du försöker bekräfta en planerad order eller lägger till en rad på en inköpsorder visas följande felmeddelande:</span><span class="sxs-lookup"><span data-stu-id="f0087-106">When you try to firm a planned order or add a line to a purchase order, you receive the following error message:</span></span>

> <span data-ttu-id="f0087-107">Leverantörskoden %1 är inte auktoriserad för %2 på %3.</span><span class="sxs-lookup"><span data-stu-id="f0087-107">Vendor code %1 is not authorized for %2 on %3.</span></span>

## <a name="cause"></a><span data-ttu-id="f0087-108">Orsak</span><span class="sxs-lookup"><span data-stu-id="f0087-108">Cause</span></span>

<span data-ttu-id="f0087-109">Felet inträffar eftersom fältet **Godkänd metod för leverantörskontroll** anges till *Endast varning* eller *Inte tillåten* för den angivna produkten och säljaren är för närvarande inte auktoriserad att leverera den produkten.</span><span class="sxs-lookup"><span data-stu-id="f0087-109">The error occurs because the **Approved vendor check method** field is set to *Warning only* or *Not allowed* for the specified product, and the vendor isn't currently authorized to supply that product.</span></span>

## <a name="resolution"></a><span data-ttu-id="f0087-110">Lösning</span><span class="sxs-lookup"><span data-stu-id="f0087-110">Resolution</span></span>

<span data-ttu-id="f0087-111">Du löser det här problemet genom att antingen inaktivera leverantörskontrollen för den relevanta produkten eller godkänna leverantören.</span><span class="sxs-lookup"><span data-stu-id="f0087-111">To fix this issue, either disable the vendor check for the relevant product or approve the vendor.</span></span>

<span data-ttu-id="f0087-112">Om du vill inaktivera leverantörskontrollen för en produkt följer du dessa steg.</span><span class="sxs-lookup"><span data-stu-id="f0087-112">To disable the vendor check for a product, follow these steps.</span></span>

1. <span data-ttu-id="f0087-113">Gå till **Produktinformationshantering \> Produkter \> Frisläppta produkter**.</span><span class="sxs-lookup"><span data-stu-id="f0087-113">Go to **Product information management \> Products \> Released products**.</span></span>
1. <span data-ttu-id="f0087-114">Öppna relevanta produkt.</span><span class="sxs-lookup"><span data-stu-id="f0087-114">Open the relevant product.</span></span>
1. <span data-ttu-id="f0087-115">På snabbfliken **Inköp** ange fältet **Kontrollmetod för godkänd leverantör** till ett annat värde än *Endast varning* eller *Ej tillåtet*.</span><span class="sxs-lookup"><span data-stu-id="f0087-115">On the **Purchase** FastTab, set the **Approved vendor check method** field to a value other than *Warning only* or *Not allowed*.</span></span>

<span data-ttu-id="f0087-116">Om du vill godkänna en leverantör för en produkt följer du dessa steg.</span><span class="sxs-lookup"><span data-stu-id="f0087-116">To approve a vendor for a product, follow these steps.</span></span>

1. <span data-ttu-id="f0087-117">Gå till **Produktinformationshantering \> Produkter \> Frisläppta produkter**.</span><span class="sxs-lookup"><span data-stu-id="f0087-117">Go to **Product information management \> Products \> Released products**.</span></span>
1. <span data-ttu-id="f0087-118">Öppna relevanta artikeln.</span><span class="sxs-lookup"><span data-stu-id="f0087-118">Open the relevant item.</span></span>
1. <span data-ttu-id="f0087-119">I åtgärdsfönstret, på fliken **Inköp**, i gruppen **Godkänd leverantör**, klickar du på **Inställningar**.</span><span class="sxs-lookup"><span data-stu-id="f0087-119">On the Action Pane, on the **Purchase** tab, in the **Approved vendor** group, select **Setup**.</span></span>
1. <span data-ttu-id="f0087-120">På listsidan **Godkänd leverantör** lägger du till en rad i rutnätet och ställer in följande värden för den:</span><span class="sxs-lookup"><span data-stu-id="f0087-120">On the **Approved vendor** list page, add a row to the grid, and set the following values for it:</span></span>

    - <span data-ttu-id="f0087-121">**Leverantör** - Välj den leverantör som ska godkännas för den aktuella produkten.</span><span class="sxs-lookup"><span data-stu-id="f0087-121">**Vendor** – Select the vendor to approve for the current product.</span></span>
    - <span data-ttu-id="f0087-122">**Giltighetsdatum** – Välj det första datumet som leverantören godkänns för.</span><span class="sxs-lookup"><span data-stu-id="f0087-122">**Effective date** – Select the first date that the vendor is approved for.</span></span>
    - <span data-ttu-id="f0087-123">**Utgångsdatum** – Välj det sista datumet som leverantören godkänns för.</span><span class="sxs-lookup"><span data-stu-id="f0087-123">**Expiration date** – Select the last date that the vendor is approved for.</span></span>

<span data-ttu-id="f0087-124">Mer information finns i [Godkänn leverantörer för specifika produkter](/dynamics365/supply-chain/procurement/tasks/approve-vendors-specific-products.md).</span><span class="sxs-lookup"><span data-stu-id="f0087-124">For more information, see [Approve vendors for specific products](/dynamics365/supply-chain/procurement/tasks/approve-vendors-specific-products.md).</span></span>
