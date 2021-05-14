---
title: Skapa och underhålla en lagerspärr
description: I detta ämne beskrivs hur du kan använda en lagerspärr i syfte att förhindra att fysiskt lager reserveras av andra utgående källdokument.
author: perlynne
ms.date: 03/23/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: InventBlocking, InventItemIdLookupSimple, InventLocationIdLookup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e9aa38ca52da577fff258bb330922ad7f4044330
ms.sourcegitcommit: 8362f3bd32ce8b9a5af93c8e57daef732a93b19e
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/28/2021
ms.locfileid: "5956168"
---
# <a name="create-and-maintain-an-inventory-blocking"></a><span data-ttu-id="b167c-103">Skapa och underhålla en lagerspärr</span><span class="sxs-lookup"><span data-stu-id="b167c-103">Create and maintain an inventory blocking</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="b167c-104">I detta ämne beskrivs hur du kan använda en lagerspärr i syfte att förhindra att fysiskt lager reserveras av andra utgående källdokument.</span><span class="sxs-lookup"><span data-stu-id="b167c-104">This topic describes how to use an inventory blocking to prevent physical on-hand inventory from being reserved by other outbound source documents.</span></span> <span data-ttu-id="b167c-105">Innan du inleder förfarandena i detta ämne måste du ha en artikel för vilken fysiskt lager finns att tillgå.</span><span class="sxs-lookup"><span data-stu-id="b167c-105">Before you start the procedures in this topic, you must have an item that physical on-hand inventory is available for.</span></span>

## <a name="block-inventory"></a><span data-ttu-id="b167c-106">Spärra lager</span><span class="sxs-lookup"><span data-stu-id="b167c-106">Block inventory</span></span>

<span data-ttu-id="b167c-107">Följ de här stegen om du vill skapa en lagerspärrpost så att lagret spärras.</span><span class="sxs-lookup"><span data-stu-id="b167c-107">To create an inventory blocking record so that inventory is blocked, follow these steps.</span></span>

1. <span data-ttu-id="b167c-108">Gå till **Lagerhantering \> Periodiska uppgifter \> Lagerspärr**.</span><span class="sxs-lookup"><span data-stu-id="b167c-108">Go to **Inventory management \> Periodic tasks \> Inventory blocking**.</span></span>
1. <span data-ttu-id="b167c-109">Klicka på **Ny** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="b167c-109">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="b167c-110">I rubriken för den nya spärrposten anger du fältet **Artikelnummer** som den artikel som du vill spärra och anger en beskrivning.</span><span class="sxs-lookup"><span data-stu-id="b167c-110">On the header of the new blocking record, set the **Item number** field to the item that you want to block, and enter a description.</span></span>
1. <span data-ttu-id="b167c-111">På snabbfliken **Allmänt**, i fältet **Kvantitet**, anger du antalet artiklar som ska spärras.</span><span class="sxs-lookup"><span data-stu-id="b167c-111">On the **General** FastTab, in the **Quantity** field, enter the number of items to block.</span></span>
1. <span data-ttu-id="b167c-112">På snabbfliken **Lagerdimensioner** anger du den plats och det lagerställe där artiklarna som du vill spärra finns för närvarande.</span><span class="sxs-lookup"><span data-stu-id="b167c-112">On the **Inventory dimensions** FastTab, specify the site and warehouse where the items that you want to block are currently located.</span></span>
1. <span data-ttu-id="b167c-113">Klicka på **Spara** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="b167c-113">On the Action Pane, select **Save**.</span></span>

## <a name="update-the-conditions-of-the-inventory-blocking"></a><span data-ttu-id="b167c-114">Uppdatera villkoren för lagerspärrren</span><span class="sxs-lookup"><span data-stu-id="b167c-114">Update the conditions of the inventory blocking</span></span>

<span data-ttu-id="b167c-115">Följ de här stegen om du vill uppdatera en lagerspärrpost.</span><span class="sxs-lookup"><span data-stu-id="b167c-115">To update an inventory blocking record, follow these steps.</span></span>

1. <span data-ttu-id="b167c-116">Gå till **Lagerhantering \> Periodiska uppgifter \> Lagerspärr**.</span><span class="sxs-lookup"><span data-stu-id="b167c-116">Go to **Inventory management \> Periodic tasks \> Inventory blocking**.</span></span>
1. <span data-ttu-id="b167c-117">I listfönstret väljer du relevant spärrpost.</span><span class="sxs-lookup"><span data-stu-id="b167c-117">In the list pane, select the relevant blocking record.</span></span>
1. <span data-ttu-id="b167c-118">Redigera posten efter behov.</span><span class="sxs-lookup"><span data-stu-id="b167c-118">Edit the record as required.</span></span> <span data-ttu-id="b167c-119">Exempelvis kanske du ändrar värdet för fältet **Förväntat datum** i syfte att indikera när det spärrade lagret förväntas bli tillgängligt för reservation.</span><span class="sxs-lookup"><span data-stu-id="b167c-119">For example, you might change the value of the **Expected date** field to indicate when the blocked inventory is expected to become available for reservation.</span></span> <span data-ttu-id="b167c-120">Om alternativet **Förväntade inleveranser** har valts visas datumet på den förväntade transaktionen.</span><span class="sxs-lookup"><span data-stu-id="b167c-120">If the **Expected receipts** option is selected, the date will appear on the expected transaction.</span></span> <span data-ttu-id="b167c-121">(Alternativet **Förväntade inleveranser** väljs som standard när du manuellt skapar en spärrpost.)</span><span class="sxs-lookup"><span data-stu-id="b167c-121">(The **Expected receipts** option is selected by default when you manually create a blocking record.)</span></span>
1. <span data-ttu-id="b167c-122">Klicka på **Spara** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="b167c-122">On the Action Pane, select **Save**.</span></span>

## <a name="unblock-inventory"></a><span data-ttu-id="b167c-123">Lås upp lager</span><span class="sxs-lookup"><span data-stu-id="b167c-123">Unblock inventory</span></span>

<span data-ttu-id="b167c-124">Följ de här stegen om du vill ta bort en lagerspärrpost så att lagret låses upp.</span><span class="sxs-lookup"><span data-stu-id="b167c-124">To remove an inventory blocking record so that inventory is unblocked, follow these steps.</span></span>

1. <span data-ttu-id="b167c-125">Gå till **Lagerhantering \> Periodiska uppgifter \> Lagerspärr**.</span><span class="sxs-lookup"><span data-stu-id="b167c-125">Go to **Inventory management \> Periodic tasks \> Inventory blocking**.</span></span>
1. <span data-ttu-id="b167c-126">I listfönstret väljer du relevant spärrpost.</span><span class="sxs-lookup"><span data-stu-id="b167c-126">In the list pane, select the relevant blocking record.</span></span>
1. <span data-ttu-id="b167c-127">Välj sedan **Ta bort** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="b167c-127">On the Action Pane, select **Delete**.</span></span>
1. <span data-ttu-id="b167c-128">Du uppmanas att bekräfta funktionen.</span><span class="sxs-lookup"><span data-stu-id="b167c-128">You're prompted to confirm the operation.</span></span> <span data-ttu-id="b167c-129">Klicka på **Ja** när du vill fortsätta.</span><span class="sxs-lookup"><span data-stu-id="b167c-129">Select **Yes** to continue.</span></span>
1. <span data-ttu-id="b167c-130">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="b167c-130">Close the page.</span></span>

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
