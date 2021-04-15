---
title: Artiklar utan lager kan checkas ut
description: Det här avsnittet innehåller felsökningsvägledning som kan hjälpa till när kunder kan lägga till artiklar utanför lagret i vagnen och gå vidare till utcheckning.
author: Reza-Assadi
ms.date: 03/11/2021
ms.topic: Troubleshooting
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: rassadi
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: af44def901d3aa7d4b24ab6abfac60d066a8d1a3
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5801757"
---
# <a name="items-without-inventory-can-be-checked-out"></a><span data-ttu-id="7b1b7-103">Artiklar utan lager kan checkas ut</span><span class="sxs-lookup"><span data-stu-id="7b1b7-103">Items without inventory can be checked out</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="7b1b7-104">Det här avsnittet innehåller felsökningsvägledning som kan hjälpa till när kunder kan lägga till artiklar utanför lagret i vagnen och gå vidare till utcheckning.</span><span class="sxs-lookup"><span data-stu-id="7b1b7-104">This topic provides troubleshooting guidance that can help when customers can add out-of-stock items to their cart and proceed to checkout.</span></span>

## <a name="description"></a><span data-ttu-id="7b1b7-105">beskrivning</span><span class="sxs-lookup"><span data-stu-id="7b1b7-105">Description</span></span>

<span data-ttu-id="7b1b7-106">Användarna kan lägga till en artikel i vagnen trots att det inte finns någon lagerbehållning i butiken och sedan gå vidare till utcheckningssidan.</span><span class="sxs-lookup"><span data-stu-id="7b1b7-106">Users can add an item to their cart, even though there is no on-hand inventory in the store, and then proceed to the checkout page.</span></span>

## <a name="resolution"></a><span data-ttu-id="7b1b7-107">Upplösning</span><span class="sxs-lookup"><span data-stu-id="7b1b7-107">Resolution</span></span>

### <a name="enable-the-show-out-of-stock-errors-property-in-commerce-site-builder"></a><span data-ttu-id="7b1b7-108">Aktivera egenskapen Visa fel av typen Slut i lager i Commerce-webbplatsbyggaren</span><span class="sxs-lookup"><span data-stu-id="7b1b7-108">Enable the Show Out Of Stock Errors property in Commerce site builder</span></span>

<span data-ttu-id="7b1b7-109">Aktivera egenskapen **Visa fel av typen Slut i lager** i Commerce-webbplatsbyggaren med dessa steg.</span><span class="sxs-lookup"><span data-stu-id="7b1b7-109">To enable the **Show Out Of Stock Errors** property in Commerce site builder, follow these steps.</span></span>

1. <span data-ttu-id="7b1b7-110">Välj den webbplats som du arbetar på.</span><span class="sxs-lookup"><span data-stu-id="7b1b7-110">Select the site that you're working on.</span></span>
1. <span data-ttu-id="7b1b7-111">I navigeringsfönstret till vänster, välj **sidor**.</span><span class="sxs-lookup"><span data-stu-id="7b1b7-111">In the left navigation, select **Pages**.</span></span>
1. <span data-ttu-id="7b1b7-112">Välj **CartPage** för att öppna den.</span><span class="sxs-lookup"><span data-stu-id="7b1b7-112">Select **CartPage** to open it.</span></span>
1. <span data-ttu-id="7b1b7-113">Markera kortplatsen **Vagn 1** välj **Redigera** och markera sedan kryssrutan **Visa fel av typen Slut i lager**.</span><span class="sxs-lookup"><span data-stu-id="7b1b7-113">Select the **Cart 1** slot, select **Edit**, and then, in the properties pane, select the **Show Out Of Stock Errors** check box.</span></span>
1. <span data-ttu-id="7b1b7-114">Spara och publicera sidan.</span><span class="sxs-lookup"><span data-stu-id="7b1b7-114">Save and publish the page.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="7b1b7-115">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="7b1b7-115">Additional resources</span></span>

[<span data-ttu-id="7b1b7-116">Använd lagerinställningar</span><span class="sxs-lookup"><span data-stu-id="7b1b7-116">Apply inventory settings</span></span>](../inventory-settings.md)

[<span data-ttu-id="7b1b7-117">Beräkna lagertillgänglighet för butikskanaler</span><span class="sxs-lookup"><span data-stu-id="7b1b7-117">Calculate inventory availability for retail channels</span></span>](../calculated-inventory-retail-channels.md)

[<span data-ttu-id="7b1b7-118">Konfigurera lagerkvantiteter och lagernivåer</span><span class="sxs-lookup"><span data-stu-id="7b1b7-118">Configure inventory buffers and inventory levels</span></span>](../inventory-buffers-levels.md)
