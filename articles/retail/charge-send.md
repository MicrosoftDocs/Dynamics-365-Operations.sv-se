---
title: Skicka order från en annan butik genom att använda sändningsfunktionen Tillägg
description: Det här avsnittet beskriver sändningsfunktionen Tillägg.
author: ashishmsft
manager: AnnBe
ms.date: 10/10/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2017-10-10
ms.dyn365.ops.version: Retail July 2017 update
ms.openlocfilehash: e5351086c56d13ef98937aec066be00cdf88fd37
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/15/2019
ms.locfileid: "1553654"
---
# <a name="ship-orders-from-another-store-by-using-the-charge-send-feature"></a><span data-ttu-id="27193-103">Skicka order från en annan butik genom att använda sändningsfunktionen Tillägg</span><span class="sxs-lookup"><span data-stu-id="27193-103">Ship orders from another store by using the Charge send feature</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="27193-104">Med sändningsfunktionen Tillägg i Dynamics 365 for Retail kan kundorder placeras i en butik och levereras från en annan butik.</span><span class="sxs-lookup"><span data-stu-id="27193-104">With the Charge send feature in Dynamics 365 for Retail, customer orders can be placed in one store and shipped from another store.</span></span>

<span data-ttu-id="27193-105">Kundorder i butik klientstöd med flera utförandealternativ.</span><span class="sxs-lookup"><span data-stu-id="27193-105">Customer orders in the point of sale (POS) client support multiple fulfillment options.</span></span> <span data-ttu-id="27193-106">Exempel på utförandealternativ är:</span><span class="sxs-lookup"><span data-stu-id="27193-106">Some examples of fulfillment options include:</span></span>

- <span data-ttu-id="27193-107">Hämta från samma butik ett annat datum.</span><span class="sxs-lookup"><span data-stu-id="27193-107">Pick up from the same store on a different date.</span></span>
- <span data-ttu-id="27193-108">Hämta från en annan butik samma datum eller ett annat datum.</span><span class="sxs-lookup"><span data-stu-id="27193-108">Pick up from a different store on the same date or a different date.</span></span>
- <span data-ttu-id="27193-109">Leverera från det standardsändningslagerställe som tilldelats butiken och leverera ett visst datum.</span><span class="sxs-lookup"><span data-stu-id="27193-109">Ship from the default shipping warehouse that is assigned to the store, and deliver on a specific date.</span></span>

<span data-ttu-id="27193-110">Sändningsfunktionen Tillägg använder följande butiksåtgärder: leverera alla produkter och leverera valda produkter.</span><span class="sxs-lookup"><span data-stu-id="27193-110">The Charge send feature uses the following POS operations: Ship all products and Ship selected products.</span></span> <span data-ttu-id="27193-111">Detta gör att butiksansvarig kan välja ”levereras från”-platsen som ordern eller orderraden kan uppfyllas från.</span><span class="sxs-lookup"><span data-stu-id="27193-111">This allows the store clerk to select the "ship from" location that the order or order line can be fulfilled from.</span></span> <span data-ttu-id="27193-112">Som standard är "leverans från"-platsen är det sändningslagerställe som associeras med butiken.</span><span class="sxs-lookup"><span data-stu-id="27193-112">By default, the "ship from" location is the shipping warehouse that is associated with the store.</span></span> <span data-ttu-id="27193-113">Emellertidkan butiksansvarig ändra denna plats och välja en butik som definieras i den butikslokaliserargrupp som tilldelats butiken.</span><span class="sxs-lookup"><span data-stu-id="27193-113">However, the store clerk can change this location and select any store that is defined in the store locator group that is assigned to the store.</span></span>

<span data-ttu-id="27193-114">Möjligheten att välja adresser ”leverans till” ändras inte.</span><span class="sxs-lookup"><span data-stu-id="27193-114">The ability to select "ship to" addresses remains unchanged.</span></span>

<span data-ttu-id="27193-115">Leveransmetoder som kan användas för att uppfylla orderraden baseras på konfigurationen av giltiga leveranssätt för produkter och adresser.</span><span class="sxs-lookup"><span data-stu-id="27193-115">The shipping methods that can be used to fulfill the order line are based on the configuration of valid modes of delivery for products and addresses.</span></span> <span data-ttu-id="27193-116">Eftersom reglerna om giltiga leveranssätt hanteras i Retail-administration (huvudkontor), butiksklienten ringer upp i realtid för att hämta giltiga leveranssätt för en transportrad.</span><span class="sxs-lookup"><span data-stu-id="27193-116">Because the rules about valid of modes of delivery are maintained only in the Retail headquarters (HQ), the POS client makes a real-time call to fetch the valid modes of delivery for a ship line.</span></span>
