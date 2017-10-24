---
title: Call center-funktioner
description: "Det här avsnittet innehåller en översikt över funktionen för callcenterförsäljning i Microsoft Dynamics 365 for Retail."
author: josaw1
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations, Retail
ms.custom: 16361
ms.assetid: c8ed2ba4-8d06-4d99-9728-2a83e6d95ca9
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 00d24e9933d087f150ec5270da94ad911423824d
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---

# <a name="call-center-functionality"></a><span data-ttu-id="29614-103">Kundtjänstfunktioner</span><span class="sxs-lookup"><span data-stu-id="29614-103">Call center functionality</span></span>

[!include[banner](includes/banner.md)]


<span data-ttu-id="29614-104">Det här avsnittet innehåller en översikt över funktionen för callcenterförsäljning i Microsoft Dynamics 365 for Retail.</span><span class="sxs-lookup"><span data-stu-id="29614-104">This article provides an overview of the call center sales functionality in Microsoft Dynamics 365 for Retail.</span></span>

<span data-ttu-id="29614-105">Dynamics 365 for Retail stöder också kundtjänst som en typ av butikskanal.</span><span class="sxs-lookup"><span data-stu-id="29614-105">Dynamics 365 for Retail supports call centers as a type of retail channel.</span></span> <span data-ttu-id="29614-106">I kundtjänsten tar anställda emot beställningar från kunder per telefon och skapar försäljningsorder.</span><span class="sxs-lookup"><span data-stu-id="29614-106">In a call center, workers take orders from customers over the phone and create sales orders.</span></span> <span data-ttu-id="29614-107">Kundtjänst innehåller funktioner som gör det enklare att ta emot telefonbeställningar och hantera kundtjänst genom hela orderbehandlingsprocessen.</span><span class="sxs-lookup"><span data-stu-id="29614-107">Call center functionality includes features that are designed to make it easier to take phone orders and handle customer service throughout the order fulfillment process.</span></span> <span data-ttu-id="29614-108">Callcentermedarbetare kan registrera betalningsinformation direkt till försäljningsordern och visa en detaljerad sammanfattning över avgifter och betalningar innan de skickar ordern.</span><span class="sxs-lookup"><span data-stu-id="29614-108">For example, call center workers can enter payment information directly into the sales order, and can view a detailed summary of charges and payments before they submit the order.</span></span> <span data-ttu-id="29614-109">Arbetstagarna har också alternativ för att styra prissättningen, och kan nå olika data om kunder, produkter och priser från **försäljning** .</span><span class="sxs-lookup"><span data-stu-id="29614-109">Workers also have options for controlling pricing, and can access various data about customers, products, and prices from the **Sales order** page.</span></span> <span data-ttu-id="29614-110">Dessutom callcenter har förbättrade funktioner för spårning av kundens historia och beställningsstatus.</span><span class="sxs-lookup"><span data-stu-id="29614-110">Additionally, call centers have enhanced functionality for tracking customer history and order status.</span></span> <span data-ttu-id="29614-111">Varje kundtjänst kan ha sina egna användare, betalningsmetoder, prisgrupper, ekonomiska dimensioner och leveranssätt.</span><span class="sxs-lookup"><span data-stu-id="29614-111">Each call center can have its own users, payment methods, price groups, financial dimensions, and modes of delivery.</span></span> <span data-ttu-id="29614-112">Du kan konfigurera dessa alternativ, när du skapar kundtjänst.</span><span class="sxs-lookup"><span data-stu-id="29614-112">You can configure these options when you create the call center.</span></span> <span data-ttu-id="29614-113">Du kan dessutom använda **Call center-** sidan för att aktivera eller inaktivera följande grupper av funktioner som är unika för call center:</span><span class="sxs-lookup"><span data-stu-id="29614-113">Additionally, you can use the **Call center** page to enable or disable the following groups of features that are unique to call centers:</span></span>

-   <span data-ttu-id="29614-114">**Orderns färdigdatum** – Denna grupp omfattar funktioner som är relaterade till betalningar och beställningen slutförs på **försäljningen** .</span><span class="sxs-lookup"><span data-stu-id="29614-114">**Order completion** – This group includes features that are related to payments and order completion on the **Sales order** page.</span></span>
-   <span data-ttu-id="29614-115">**Riktad försäljning** – Denna grupp omfattar funktioner som är relaterade till källkoder, manuskript, och katalog.</span><span class="sxs-lookup"><span data-stu-id="29614-115">**Directed selling** – This group includes features that are related to source codes, scripts, and catalog requests.</span></span>

<span data-ttu-id="29614-116">När du aktiverar funktionerna i call center-inställningarna, de finns på **Försäljningsorder** till användare som är associerade med call center.</span><span class="sxs-lookup"><span data-stu-id="29614-116">After you enable these features in the call center settings, they are available on the **Sales order** page to users who are associated with the call center.</span></span> <span data-ttu-id="29614-117">De flesta av dessa funktioner kräver ytterligare inställningar innan de kan användas.</span><span class="sxs-lookup"><span data-stu-id="29614-117">Most of these features require additional setup before they can be used.</span></span> <span data-ttu-id="29614-118">Innan användare kan skapa call center-order måste du lägga till användarna till call center som call center-användare.</span><span class="sxs-lookup"><span data-stu-id="29614-118">Before users can create call center orders, you must add those users to the call center as call center users.</span></span> <span data-ttu-id="29614-119">Det här steget gör att call center kanal-specifika konfigurationer och funktionalitet.</span><span class="sxs-lookup"><span data-stu-id="29614-119">This step enables the call center channel-specific configuration and functionality.</span></span> <span data-ttu-id="29614-120">Här är några exempel på funktioner som blir tillgängliga:</span><span class="sxs-lookup"><span data-stu-id="29614-120">Here are some examples of the functionality that becomes available:</span></span>

-   <span data-ttu-id="29614-121">Guidad försäljning tillhandahåller konfigurationsalternativ för telefonförsäljning manuskript och bilder för att hjälpa och vägleda försäljning clerks medan de tar order.</span><span class="sxs-lookup"><span data-stu-id="29614-121">Guided selling provides configuration options for telesales scripts and product images to help and guide sales clerks while they take orders.</span></span>
-   <span data-ttu-id="29614-122">Beställningar kan inte slutföras förrän försäljningen i butiken har fångat minst ett betalningssätt.</span><span class="sxs-lookup"><span data-stu-id="29614-122">Orders can't be completed until sales clerks have captured at least one payment method.</span></span>
-   <span data-ttu-id="29614-123">Merförsäljning och korsförsäljning av reglerna kan konfigureras att försäljningen i butiken för att främja särskilda produkter till kunden.</span><span class="sxs-lookup"><span data-stu-id="29614-123">Upsell and cross-sell rules can be configured to prompt sales clerks to promote specific products to the customer.</span></span>
-   <span data-ttu-id="29614-124">Försäljningen i butiken kan fånga källkoden för den katalog som en kund beställer från.</span><span class="sxs-lookup"><span data-stu-id="29614-124">Sales clerks can capture the source code for the catalog that a customer is ordering from.</span></span>
-   <span data-ttu-id="29614-125">Försäljningen i butiken kan lägga till detaljhandlarens kuponger till ordern.</span><span class="sxs-lookup"><span data-stu-id="29614-125">Sales clerks can add a retailer's coupons to the order.</span></span>
-   <span data-ttu-id="29614-126">Försäljningen i butiken kan sälja förbindelse program.</span><span class="sxs-lookup"><span data-stu-id="29614-126">Sales clerks can sell continuity programs.</span></span>
-   <span data-ttu-id="29614-127">Beställningar kan parkeras automatiskt eller manuellt, för att indikera att ytterligare utredning krävs innan den kan bearbetas.</span><span class="sxs-lookup"><span data-stu-id="29614-127">Orders can be put on hold manually or automatically, to indicate that additional investigation is required before the order can be processed.</span></span>





