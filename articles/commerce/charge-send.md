---
title: Skicka order från en annan butik genom att använda sändningsfunktionen Tillägg
description: Det här avsnittet beskriver sändningsfunktionen Tillägg.
author: ashishmsft
ms.date: 10/10/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2017-10-10
ms.dyn365.ops.version: Retail July 2017 update
ms.openlocfilehash: b9e0c4f55fd823bf7471edfe6ce1d424b0179d21
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5800481"
---
# <a name="ship-orders-from-another-store-by-using-the-charge-send-feature"></a><span data-ttu-id="0dc8b-103">Skicka order från en annan butik genom att använda sändningsfunktionen Tillägg</span><span class="sxs-lookup"><span data-stu-id="0dc8b-103">Ship orders from another store by using the Charge send feature</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="0dc8b-104">Med sändningsfunktionen Tillägg i Commerce kan kundorder placeras i en butik och levereras från en annan butik.</span><span class="sxs-lookup"><span data-stu-id="0dc8b-104">With the Charge send feature in Commerce, customer orders can be placed in one store and shipped from another store.</span></span>

<span data-ttu-id="0dc8b-105">Kundorder i butik klientstöd med flera utförandealternativ.</span><span class="sxs-lookup"><span data-stu-id="0dc8b-105">Customer orders in the point of sale (POS) client support multiple fulfillment options.</span></span> <span data-ttu-id="0dc8b-106">Exempel på utförandealternativ är:</span><span class="sxs-lookup"><span data-stu-id="0dc8b-106">Some examples of fulfillment options include:</span></span>

- <span data-ttu-id="0dc8b-107">Hämta från samma butik ett annat datum.</span><span class="sxs-lookup"><span data-stu-id="0dc8b-107">Pick up from the same store on a different date.</span></span>
- <span data-ttu-id="0dc8b-108">Hämta från en annan butik samma datum eller ett annat datum.</span><span class="sxs-lookup"><span data-stu-id="0dc8b-108">Pick up from a different store on the same date or a different date.</span></span>
- <span data-ttu-id="0dc8b-109">Leverera från det standardsändningslagerställe som tilldelats butiken och leverera ett visst datum.</span><span class="sxs-lookup"><span data-stu-id="0dc8b-109">Ship from the default shipping warehouse that is assigned to the store, and deliver on a specific date.</span></span>

<span data-ttu-id="0dc8b-110">Sändningsfunktionen Tillägg använder följande butiksåtgärder: leverera alla produkter och leverera valda produkter.</span><span class="sxs-lookup"><span data-stu-id="0dc8b-110">The Charge send feature uses the following POS operations: Ship all products and Ship selected products.</span></span> <span data-ttu-id="0dc8b-111">Detta gör att butiksansvarig kan välja ”levereras från”-platsen som ordern eller orderraden kan uppfyllas från.</span><span class="sxs-lookup"><span data-stu-id="0dc8b-111">This allows the store clerk to select the "ship from" location that the order or order line can be fulfilled from.</span></span> <span data-ttu-id="0dc8b-112">Som standard är "leverans från"-platsen är det sändningslagerställe som associeras med butiken.</span><span class="sxs-lookup"><span data-stu-id="0dc8b-112">By default, the "ship from" location is the shipping warehouse that is associated with the store.</span></span> <span data-ttu-id="0dc8b-113">Emellertidkan butiksansvarig ändra denna plats och välja en butik som definieras i den butikslokaliserargrupp som tilldelats butiken.</span><span class="sxs-lookup"><span data-stu-id="0dc8b-113">However, the store clerk can change this location and select any store that is defined in the store locator group that is assigned to the store.</span></span>

<span data-ttu-id="0dc8b-114">Möjligheten att välja adresser ”leverans till” ändras inte.</span><span class="sxs-lookup"><span data-stu-id="0dc8b-114">The ability to select "ship to" addresses remains unchanged.</span></span>

<span data-ttu-id="0dc8b-115">Leveransmetoder som kan användas för att uppfylla orderraden baseras på konfigurationen av giltiga leveranssätt för produkter och adresser.</span><span class="sxs-lookup"><span data-stu-id="0dc8b-115">The shipping methods that can be used to fulfill the order line are based on the configuration of valid modes of delivery for products and addresses.</span></span> <span data-ttu-id="0dc8b-116">Eftersom reglerna om giltiga leveranssätt hanteras i administration (huvudkontor), butiksklienten ringer upp i realtid för att hämta giltiga leveranssätt för en transportrad.</span><span class="sxs-lookup"><span data-stu-id="0dc8b-116">Because the rules about valid of modes of delivery are maintained only in the Headquarters (HQ), the POS client makes a real-time call to fetch the valid modes of delivery for a ship line.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]