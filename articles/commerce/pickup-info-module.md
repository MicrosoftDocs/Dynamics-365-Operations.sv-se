---
title: Informationsmodul för upphämtning
description: Det här avsnittet handlar om informationsmodulen för upphämtning och beskriver hur du lägger till den på kassasidorna i Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 11/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2020-09021
ms.dyn365.ops.version: Release 10.0.15
ms.openlocfilehash: 222e8ad79b30e5197f7140958309d442b284f286
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5263190"
---
# <a name="pickup-information-module"></a><span data-ttu-id="a6d70-103">Modul för upphämtningsinformation</span><span class="sxs-lookup"><span data-stu-id="a6d70-103">Pickup information module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="a6d70-104">Det här avsnittet handlar om informationsmodulen för upphämtning och beskriver hur du lägger till den på kassasidorna i Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="a6d70-104">This topic covers the pickup information module and describes how to add it to checkout pages in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="a6d70-105">Du kan använda modulen för upphämtningsinformation i en kassamodul för att visa information om orderupphämtning.</span><span class="sxs-lookup"><span data-stu-id="a6d70-105">The pickup information module can be used in a checkout module to show order pickup information.</span></span> <span data-ttu-id="a6d70-106">Kunder kan visa tillgängliga datum och tidpunkter för upphämtning och sedan välja en lämplig tid att hämta sin order.</span><span class="sxs-lookup"><span data-stu-id="a6d70-106">Customers can view available pickup dates and time slots, and then select a suitable time to pick up their order.</span></span> <span data-ttu-id="a6d70-107">En kund kan till exempel välja att hämta en order kl. 15.00 den 21 mars från butiken i San Francisco.</span><span class="sxs-lookup"><span data-stu-id="a6d70-107">For example, a customer can choose to pick up an order at 3 PM on March 21 from the San Francisco store.</span></span>

<span data-ttu-id="a6d70-108">Upphämtningstider för relevanta butiker måste konfigureras i Commerce-administrationen.</span><span class="sxs-lookup"><span data-stu-id="a6d70-108">Pickup time slots for the appropriate stores must be configured in Commerce headquarters.</span></span> <span data-ttu-id="a6d70-109">Mer information finns i [Skapa och uppdatera tidpunkter för kundupphämtning](dev-itpro/pickup-timeslots.md).</span><span class="sxs-lookup"><span data-stu-id="a6d70-109">For more information, see [Create and update time slots for customer pickup](dev-itpro/pickup-timeslots.md).</span></span>

<span data-ttu-id="a6d70-110">Om en modul för upphämtningsinformation skapas på en kassasida men inga tidpunkter har definierats för den butik som valts för upphämtning, visar modulen information men användaren kan inte välja några tidpunkter.</span><span class="sxs-lookup"><span data-stu-id="a6d70-110">If a pickup information module is created on a checkout page, but no time slots are defined for the store that is selected for pickup, the module will show information, but the user won't be able to select any time slots.</span></span> <span data-ttu-id="a6d70-111">Tidpunkter är valfria och krävs inte för att lägga en beställning.</span><span class="sxs-lookup"><span data-stu-id="a6d70-111">Time slots are optional and aren't required to place an order.</span></span>

<span data-ttu-id="a6d70-112">Om flera artiklar har valts för upphämtning över flera butiker, kommer modulen för upphämtningsinformation att låta användaren välja en tidpunkt för respektive butik, förutsatt att det finns tillgängliga tidpunkter för densamma.</span><span class="sxs-lookup"><span data-stu-id="a6d70-112">If multiple items are selected for pickup across multiple stores, the pickup information module will let the user select a time slot for each store, provided that time slots are available for it.</span></span>

> [!NOTE]
> <span data-ttu-id="a6d70-113">Stöd för tidpunkter och informationsmodulen för kassaupphämtning finns att tillgå i Dynamics 365 Commerce version 10.0.15 och senare.</span><span class="sxs-lookup"><span data-stu-id="a6d70-113">Support for time slots and the checkout pickup information module is available in Dynamics 365 Commerce version 10.0.15 and later.</span></span>

<span data-ttu-id="a6d70-114">I bilden nedan visas ett exempel på hur val av tidpunkter via informationsmodulen för upphämtning på en kassasida.</span><span class="sxs-lookup"><span data-stu-id="a6d70-114">The following illustration shows an example of time slot selection through the pickup information module on a checkout page.</span></span>

![Exempel på en modul för upphämtningsinformation på en kassasida](./dev-itpro/media/Curbside_timeslot_eCommerce.PNG)

## <a name="module-properties"></a><span data-ttu-id="a6d70-116">Modulegenskaper</span><span class="sxs-lookup"><span data-stu-id="a6d70-116">Module properties</span></span>

- <span data-ttu-id="a6d70-117">**Rubrik** – Ange en rubrik för modulen.</span><span class="sxs-lookup"><span data-stu-id="a6d70-117">**Heading** – Enter a heading for the module.</span></span>

## <a name="show-time-slot-information-after-an-order-is-placed"></a><span data-ttu-id="a6d70-118">Visa information om tidpunkt efter det att en order har lagts</span><span class="sxs-lookup"><span data-stu-id="a6d70-118">Show time slot information after an order is placed</span></span>

<span data-ttu-id="a6d70-119">När en order har lagts kan information om den valda tidpunkten visas i [modulen för orderbekräftelse](order-confirmation-module.md) och i [modulen för orderinformation](account-management.md#order-details-page).</span><span class="sxs-lookup"><span data-stu-id="a6d70-119">After an order is placed, information about the selected time slot can be viewed in the [order confirmation module](order-confirmation-module.md) and the [order details module](account-management.md#order-details-page).</span></span> <span data-ttu-id="a6d70-120">Båda dessa moduler har egenskapen **Visa tidpunktsinformation**.</span><span class="sxs-lookup"><span data-stu-id="a6d70-120">Both these modules have a **Show timeslot information** property.</span></span> <span data-ttu-id="a6d70-121">Innan de kan visa den valda tidpunkten i samband med orderprocessen måste den här egenskapen ha värdet **True**.</span><span class="sxs-lookup"><span data-stu-id="a6d70-121">Before they can show the selected time slot during the order process, this property must be set to **True**.</span></span>

## <a name="add-a-checkout-pickup-information-module-to-a-page"></a><span data-ttu-id="a6d70-122">Lägg till en informationsmodul för kassaupphämtning på en sida</span><span class="sxs-lookup"><span data-stu-id="a6d70-122">Add a checkout pickup information module to a page</span></span>

<span data-ttu-id="a6d70-123">Instruktioner om hur du lägger till en informationsmodul om upphämtning på en kassasida och anger erforderliga egenskaper finns i [Kassamodulen](add-checkout-module.md).</span><span class="sxs-lookup"><span data-stu-id="a6d70-123">For instructions about how to add a pickup information module to a checkout page and set the required properties, see [Checkout module](add-checkout-module.md).</span></span>

<span data-ttu-id="a6d70-124">I bilden nedan visas ett exempel på en kassasida för näthandel som innehåller tidpunkter för artiklar på upphämtningsrader.</span><span class="sxs-lookup"><span data-stu-id="a6d70-124">The following illustration shows an example of an e-Commerce checkout page that includes time slots for pickup line items.</span></span>

![Exempel på en kassasida för näthandel som innehåller tidpunkter för artiklar på upphämtningsrader](./dev-itpro/media/Curbside_timeslot_eCommerce_checkoutsummary.PNG)

## <a name="additional-resources"></a><span data-ttu-id="a6d70-126">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="a6d70-126">Additional resources</span></span>

[<span data-ttu-id="a6d70-127">Skapa och uppdatera tidpunkter för kundavhämtning</span><span class="sxs-lookup"><span data-stu-id="a6d70-127">Create and update time slots for customer pickup</span></span>](dev-itpro/pickup-timeslots.md)

[<span data-ttu-id="a6d70-128">Kassamodul</span><span class="sxs-lookup"><span data-stu-id="a6d70-128">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="a6d70-129">Modul för orderbekräftelse</span><span class="sxs-lookup"><span data-stu-id="a6d70-129">Order confirmation module</span></span>](order-confirmation-module.md)

[<span data-ttu-id="a6d70-130">Orderinformationsmodul</span><span class="sxs-lookup"><span data-stu-id="a6d70-130">Order details module</span></span>](account-management.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]