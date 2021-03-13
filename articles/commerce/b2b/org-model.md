---
title: Skapa organisationsmodelleringshierarkier för B2B-organisationer
description: I detta ämne beskrivs hur du skapar organisationsmodellhierarkier för B2B-organisationer (business-to-business).
author: josaw1
manager: AnnBe
ms.date: 01/20/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailOperations
audience: Application User, IT Pro
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: retail
ms.author: josaw
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 450efd595a1cc1b72b2e62afbdd4518bcca59cb0
ms.sourcegitcommit: f9df202aefef761be52c0360b0e22da88773914c
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/21/2021
ms.locfileid: "5035965"
---
# <a name="create-org-modeling-hierarchies-for-b2b-organizations"></a><span data-ttu-id="01aa8-103">Skapa organisationsmodelleringshierarkier för B2B-organisationer</span><span class="sxs-lookup"><span data-stu-id="01aa8-103">Create org modeling hierarchies for B2B organizations</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="01aa8-104">I detta ämne beskrivs hur du skapar organisationsmodellhierarkier för B2B-organisationer (business-to-business) i Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="01aa8-104">This topic describes how to create organizational modeling hierarchies for business-to-business (B2B) organizations in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="01aa8-105">I Commerce-administrationen representeras affärspartner-organisationerna av kund- och kundhierarkientiteter.</span><span class="sxs-lookup"><span data-stu-id="01aa8-105">In Commerce headquarters, business partner organizations are represented by customer and customer hierarchy entities.</span></span> <span data-ttu-id="01aa8-106">Partnerorganisationen och dess användare representeras som kunder, och kundhierarkier används för att koppla dessa kunder till varandra.</span><span class="sxs-lookup"><span data-stu-id="01aa8-106">The business partner organization and its users are represented as customers, and customer hierarchies are used to associate those customers with each other.</span></span>

<span data-ttu-id="01aa8-107">När en affärspartners begäran om att ansluta till en B2B-näthandelssajt godkänns, utförs följande åtgärder:</span><span class="sxs-lookup"><span data-stu-id="01aa8-107">When a business partner request to join a B2B e-commerce site is approved, the following actions are performed:</span></span>

- <span data-ttu-id="01aa8-108">Två nya kundposter skapas i systemet: en kundpost av typen **Organisation** för affärspartnerorganisationen, samt en kundpost av typen **Person** för begäranden (dvs. den affärspartneranvändare som skickade in begäran).</span><span class="sxs-lookup"><span data-stu-id="01aa8-108">Two new customer records are created in the system: a **Type Organization** customer record for the business partner organization and a **Type Person** customer record for the requestor (that is, the business partner user who submitted the request).</span></span>
- <span data-ttu-id="01aa8-109">En ny kundhierarkipost skapas under **Kund \> Kundkundhierarki**.</span><span class="sxs-lookup"><span data-stu-id="01aa8-109">A new customer hierarchy record is created under **Customer \> Customer hierarchy**.</span></span> <span data-ttu-id="01aa8-110">Den här posten har följande rubrikegenskaper:</span><span class="sxs-lookup"><span data-stu-id="01aa8-110">This record has the following header properties:</span></span>

    - <span data-ttu-id="01aa8-111">**Kundhierarki-ID** – Ett unikt ID för kundhierarkin.</span><span class="sxs-lookup"><span data-stu-id="01aa8-111">**Customer hierarchy ID** – A unique ID for the customer hierarchy.</span></span> <span data-ttu-id="01aa8-112">Detta ID använder den nummerserie som definierats i delade Commerce-parametrar i Commerce-administrationen.</span><span class="sxs-lookup"><span data-stu-id="01aa8-112">This ID uses the number sequence that is defined in Commerce shared parameters in Commerce headquarters.</span></span>
    - <span data-ttu-id="01aa8-113">**Namn** – Organisationsnamnet för affärspartnern, enligt vad som angetts i begäran om registrering.</span><span class="sxs-lookup"><span data-stu-id="01aa8-113">**Name** – The organization name of the business partner, as specified in the onboarding request.</span></span>
    - <span data-ttu-id="01aa8-114">**Syfte** – Denna egenskap är inställd på det fördefinierade värdet **B2B-organisation**.</span><span class="sxs-lookup"><span data-stu-id="01aa8-114">**Purpose** – This property is set to the predefined value **B2B organization**.</span></span>
    - <span data-ttu-id="01aa8-115">**Organisation** – Kund-ID för affärspartnern.</span><span class="sxs-lookup"><span data-stu-id="01aa8-115">**Organization** – The customer ID of the business partner.</span></span>

<span data-ttu-id="01aa8-116">Här finns information om kundhierarkiposten:</span><span class="sxs-lookup"><span data-stu-id="01aa8-116">Here are the details of the customer hierarchy record:</span></span>

- <span data-ttu-id="01aa8-117">Kundposten för begäranden associerats med kundhierarkin.</span><span class="sxs-lookup"><span data-stu-id="01aa8-117">The customer record of the requestor is associated with the customer hierarchy.</span></span>
- <span data-ttu-id="01aa8-118">Administratörsrollen associeras med begäranden.</span><span class="sxs-lookup"><span data-stu-id="01aa8-118">The administrator role is associated with the requestor.</span></span>

<span data-ttu-id="01aa8-119">När administratören lägger till fler användare till partnerorganisationen på en B2B-webbplats skapas en ny kundpost för respektive användare i Commerce-administrationen.</span><span class="sxs-lookup"><span data-stu-id="01aa8-119">When the administrator adds more users are to the business partner organization on a B2B site, a new customer record for each user is created in Commerce headquarters.</span></span> <span data-ttu-id="01aa8-120">Denna kundpost läggs också till i den relevanta kundhierarkiposten för affärspartnern och har rollen "användare".</span><span class="sxs-lookup"><span data-stu-id="01aa8-120">This customer record is also added to the relevant customer hierarchy record for the business partner and has the role of a "user."</span></span>

> [!NOTE]
> <span data-ttu-id="01aa8-121">I de flesta fall ska motsvarande egenskapsvärden för alla kundposter i en hierarki matcha.</span><span class="sxs-lookup"><span data-stu-id="01aa8-121">In most cases, the corresponding property values of all customer records in a hierarchy should match.</span></span> <span data-ttu-id="01aa8-122">Eftersom alla affärspartnersanvändare exempelvis ska få liknande priser för produkter, ska deras prisgrupp och associerade konfigurationer matcha.</span><span class="sxs-lookup"><span data-stu-id="01aa8-122">For example, because all business partner users should get similar prices for products, their price group and associated configurations should match.</span></span> <span data-ttu-id="01aa8-123">Systemet framtvingar dock inte denna överensstämmelse.</span><span class="sxs-lookup"><span data-stu-id="01aa8-123">However, the system doesn't enforce this consistency.</span></span> <span data-ttu-id="01aa8-124">Därför ansvarar relevanta Commerce-administrationsanvändare för att egenskapsvärden och konfigurationer ska matcha för alla kunder i en given hierarki.</span><span class="sxs-lookup"><span data-stu-id="01aa8-124">Therefore, the relevant Commerce headquarters users are responsible for ensuring that the property values and configurations match for all customers in a given hierarchy.</span></span>

<span data-ttu-id="01aa8-125">Användare av Commerce-administrationen kan även söka efter egenskapsvärden för alla kundposter i hierarkin i en vy sida vid sida.</span><span class="sxs-lookup"><span data-stu-id="01aa8-125">Commerce headquarters users can look at the property values for all customer records in the hierarchy in a side-by-side view.</span></span> <span data-ttu-id="01aa8-126">Välj relevanta egenskaper för kundposten genom att välja fliknamnen i listrutan.</span><span class="sxs-lookup"><span data-stu-id="01aa8-126">Select the relevant customer record properties by selecting the tab names on the drop-down menu.</span></span> <span data-ttu-id="01aa8-127">Användarna kan visa och redigera egenskapsvärdena direkt från den här vyn.</span><span class="sxs-lookup"><span data-stu-id="01aa8-127">Users can directly view and edit the property values from this view.</span></span> <span data-ttu-id="01aa8-128">Om du vill tillämpa alla värden från administratörskundposten på alla användarkundposter kan du också välja **Åsidosätt** i kundhierarkidetaljerna.</span><span class="sxs-lookup"><span data-stu-id="01aa8-128">Alternatively, if you want to apply all the values from the administrator customer record to all the user customer records, select **Override** in the customer hierarchy details.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="01aa8-129">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="01aa8-129">Additional resources</span></span>

[<span data-ttu-id="01aa8-130">Konfigurera en B2B-näthandelssajt</span><span class="sxs-lookup"><span data-stu-id="01aa8-130">Set up a B2B e-commerce site</span></span>](set-up-b2b-site.md)

[<span data-ttu-id="01aa8-131">Hantera affärspartneranvändare på B2B-näthandelssajter</span><span class="sxs-lookup"><span data-stu-id="01aa8-131">Manage business partner users on B2B e-commerce sites</span></span>](manage-b2b-users.md)

[<span data-ttu-id="01aa8-132">Konfigurera betalsätt för kundkonto för B2B-näthandelssajter</span><span class="sxs-lookup"><span data-stu-id="01aa8-132">Configure the customer account payment method for B2B e-commerce sites</span></span>](payment-method.md)

[<span data-ttu-id="01aa8-133">Ange produktkvantitetsgränser för B2B-näthandelssajter</span><span class="sxs-lookup"><span data-stu-id="01aa8-133">Set product quantity limits for B2B e-commerce sites</span></span>](quantity-limits.md)
