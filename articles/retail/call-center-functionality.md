---
title: Säljfunktion för kundtjänst
description: Det här avsnittet innehåller en översikt över funktionen för callcenterförsäljning i Dynamics 365 Retail.
author: josaw1
manager: AnnBe
ms.date: 04/03/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailMCRChannelDetailPage, MCROrderParameters
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 16361
ms.assetid: c8ed2ba4-8d06-4d99-9728-2a83e6d95ca9
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 2e44770af4a30f539e56d38b21c897cacd2707e7
ms.sourcegitcommit: 57bc7e17682e2edb5e1766496b7a22f4621819dd
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/18/2019
ms.locfileid: "2812349"
---
# <a name="call-center-sales-functionality"></a><span data-ttu-id="364b3-103">Försäljningsfunktioner för kundtjänst</span><span class="sxs-lookup"><span data-stu-id="364b3-103">Call center sales functionality</span></span>

[!include [banner](includes/banner.md)]


<span data-ttu-id="364b3-104">I Dynamics 365 Retail, är kundtjänst en typ av butikskanal som kan definieras i programmet.</span><span class="sxs-lookup"><span data-stu-id="364b3-104">In Dynamics 365 Retail, a call center is a type of Retail channel that can be defined in the application.</span></span> <span data-ttu-id="364b3-105">Definiera en viss kanal för dina kundtjänstenheter låter systemet koppla specifika datastandarder och orderhantering är som standard försäljningsorder som har skapats av en användare av kundtjänst.</span><span class="sxs-lookup"><span data-stu-id="364b3-105">Defining a specific channel for your call center entities allows the system to tie specific data defaults and order processing defaults to sales orders created by a user of the call center channel.</span></span>

<span data-ttu-id="364b3-106">Kundtjänst omfattar avancerat butikspris och erbjudanden, kataloger, presentkort, bonusprogram och kuponger.</span><span class="sxs-lookup"><span data-stu-id="364b3-106">Call center features include advanced retail price and promotions, catalogs, gift cards, loyalty programs, and coupons.</span></span> <span data-ttu-id="364b3-107">Kundtjänstorder utnyttjas också av kassaprogrammet för att ge stöd för scenarier för orderuppfyllelse mellan kanaler.</span><span class="sxs-lookup"><span data-stu-id="364b3-107">Call center orders are also leveraged by the point of sale (POS) application to support cross-channel order fulfillment scenarios.</span></span>

<span data-ttu-id="364b3-108">Det är viktigt att komma ihåg att medan modulen för kundtjänst kan användas inom andra branscher utanför Retail, har den aktuella versionen av kundtjänstprogrammet för Retail inte optimerats för användning i B2B-orderbehandlingsscenarier och scenarier där order har ett stort antal försäljningsrader.</span><span class="sxs-lookup"><span data-stu-id="364b3-108">It's important to note that while the call center module can be utilized by other industries outside of Retail, the current release of the Retail call center application hasn't been optimized for use in business-to-business (B2B) order processing scenarios, or scenarios where orders have a large amount of sales lines.</span></span> <span data-ttu-id="364b3-109">Vi rekommenderar att användare som vill använda kundtjänstfunktioner för orderhantering utanför normal transaktionsbearbetning direkt till konsument, ta tillräcklig tid för att testa och verifiera att kundtjänstfunktionerna uppfyller funktionella och prestandabehov.</span><span class="sxs-lookup"><span data-stu-id="364b3-109">It's recommended that users who want to utilize the call center features for order processing outside of typical direct-to-consumer transaction processing, take adequate time to test and validate that enabling call center functionality will meet functional and performance needs.</span></span>

<span data-ttu-id="364b3-110">Förutom att stödja skapande av order ger kundtjänstmodulen även ett användarvänligt kundtjänstprogram som gör det enklare för användare att hitta kundkonton och granska alla relaterade kundorderdata och attribut.</span><span class="sxs-lookup"><span data-stu-id="364b3-110">In addition to supporting order creation, the call center module also provides a user-friendly customer service application that makes it easier for users to locate customer accounts and review all of the related customer order data and attributes.</span></span> <span data-ttu-id="364b3-111">Skärmen för kundtjänst har utformats så att användare snabbt får tillgång till orderrelaterade data för att besvara vanliga orderrelaterade frågor som tagits emot från kunder.</span><span class="sxs-lookup"><span data-stu-id="364b3-111">The customer service screen is designed to enable a user to quickly access order related data that will allow them to answer the most common order-related questions received from customers.</span></span>

<span data-ttu-id="364b3-112">Den här sidan innehåller länkar till relevanta handlingar som är relaterade till installation, konfiguration och funktionell användning av kundtjänstfunktionerna i Retail.</span><span class="sxs-lookup"><span data-stu-id="364b3-112">This page provides links to relevant documentation related to the setup, configuration, and functional use of the call center features in Retail.</span></span>


## <a name="configure-the-call-center"></a><span data-ttu-id="364b3-113">Konfigurera kundtjänst.</span><span class="sxs-lookup"><span data-stu-id="364b3-113">Configure the call center</span></span>

[<span data-ttu-id="364b3-114">Ställa in kundtjänstkanaler</span><span class="sxs-lookup"><span data-stu-id="364b3-114">Set up call center channels</span></span>](set-up-order-processing-options.md)

## <a name="configure-order-processing"></a><span data-ttu-id="364b3-115">Konfigurera orderbearbetning</span><span class="sxs-lookup"><span data-stu-id="364b3-115">Configure order processing</span></span>

[<span data-ttu-id="364b3-116">Ställa in och arbeta med bedrägerivarningar för kundtjänst</span><span class="sxs-lookup"><span data-stu-id="364b3-116">Set up and work with call center fraud alerts</span></span>](set-up-fraud-alerts.md)

[<span data-ttu-id="364b3-117">Konfigurera och arbeta med orderspärrar för kundtjänst</span><span class="sxs-lookup"><span data-stu-id="364b3-117">Configure and work with call center order holds</span></span>](work-with-order-holds.md)

## <a name="configure-payment-processing"></a><span data-ttu-id="364b3-118">Konfigurera betalningsbearbetning</span><span class="sxs-lookup"><span data-stu-id="364b3-118">Configure payment processing</span></span>

[<span data-ttu-id="364b3-119">Betalningsmetoder i kundcenter</span><span class="sxs-lookup"><span data-stu-id="364b3-119">Payment methods in call centers</span></span>](work-with-payments.md)

## <a name="configure-delivery-modes"></a><span data-ttu-id="364b3-120">Konfigurera leveranslägen</span><span class="sxs-lookup"><span data-stu-id="364b3-120">Configure delivery modes</span></span>

[<span data-ttu-id="364b3-121">Konfigurera leveranslägen och avgifter för kundtjänst</span><span class="sxs-lookup"><span data-stu-id="364b3-121">Configure call center delivery modes and charges</span></span>](configure-call-center-delivery.md)

## <a name="configure-direct-marketing"></a><span data-ttu-id="364b3-122">Konfigurera direkt marknadsföring</span><span class="sxs-lookup"><span data-stu-id="364b3-122">Configure direct marketing</span></span>

[<span data-ttu-id="364b3-123">Kundtjänstkataloger</span><span class="sxs-lookup"><span data-stu-id="364b3-123">Call center catalogs</span></span>](call-center-catalogs.md)

[<span data-ttu-id="364b3-124">Ställa in Recency-, frekvens- och penninganalys (RFM)</span><span class="sxs-lookup"><span data-stu-id="364b3-124">Set up Recency, Frequency, and Monetary (RFM) analysis</span></span>](set-up-rfm-analysis.md)

## <a name="configure-continuity-programs"></a><span data-ttu-id="364b3-125">Konfigurera kontinuitetsprogram</span><span class="sxs-lookup"><span data-stu-id="364b3-125">Configure continuity programs</span></span>

[<span data-ttu-id="364b3-126">Ställa in kontinuitetsprogram för kundtjänster</span><span class="sxs-lookup"><span data-stu-id="364b3-126">Set up continuity programs for call centers</span></span>](set-up-continuity-program.md)
