---
title: Använda prissättningsmotorn för Dynamics 365 Commerce med Dynamics 365 Sales
description: I det här avsnittet beskrivs hur du använder prissättningsmotorn i Microsoft Dynamics 365 Commerce för att skapa offerter i Dynamics 365 Sales.
author: ShalabhjainMSFT
ms.date: 11/19/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: shajain
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-11-03
ms.openlocfilehash: 364cc5adf0358ffa952750149ad31d62cbd35e87
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5751444"
---
# <a name="use-the-dynamics-365-commerce-pricing-engine-with-dynamics-365-sales"></a><span data-ttu-id="34d7d-103">Använda prissättningsmotorn för Dynamics 365 Commerce med Dynamics 365 Sales</span><span class="sxs-lookup"><span data-stu-id="34d7d-103">Use the Dynamics 365 Commerce pricing engine with Dynamics 365 Sales</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="34d7d-104">I det här avsnittet beskrivs hur du använder prissättningsmotorn i Microsoft Dynamics 365 Commerce för att skapa offerter i Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="34d7d-104">This topic describes how to use the Microsoft Dynamics 365 Commerce pricing engine to create sales quotations in Dynamics 365 Sales.</span></span>

<span data-ttu-id="34d7d-105">Prissättningsmotorn i Dynamics 365 Commerce har stöd för de flesta B2C (Business-to-Consumer) prisvarianter, till exempel pris på butiksnivå, partnerbaserade och förmånbaserade priser, mixa och-matcha-rabatter, mängdrabatter och tröskelrabatter.</span><span class="sxs-lookup"><span data-stu-id="34d7d-105">The Dynamics 365 Commerce pricing engine supports most business-to-consumer (B2C) pricing scenarios, such as store-level pricing, affiliation-based and loyalty-based pricing, mix-and-match discounts, quantity discounts, and threshold discounts.</span></span> <span data-ttu-id="34d7d-106">Prissättningsmotorn använder komplexa regler för att fastställa det bästa priset för en given offert eller order.</span><span class="sxs-lookup"><span data-stu-id="34d7d-106">The pricing engine uses complex rules to determine the best price for a given quotation or order.</span></span>

<span data-ttu-id="34d7d-107">När du använder [dubbelriktad skrivning](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-overview) har du tre alternativ för dina prissättningsbehov.</span><span class="sxs-lookup"><span data-stu-id="34d7d-107">When you use [dual-write](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-overview), you have three options for your pricing needs.</span></span> <span data-ttu-id="34d7d-108">Du kan använda den statiska prissättningen från prislistan i Dynamics 365 Sales, prissättningsmotorn i Dynamics 365 Supply Chain Management eller prissättningsmotorn i Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="34d7d-108">You can use the static pricing that comes from the price list in Dynamics 365 Sales, the pricing engine in Dynamics 365 Supply Chain Management, or the pricing engine in Dynamics 365 Commerce.</span></span> <span data-ttu-id="34d7d-109">Av de här alternativen är prissättningsmotorn i Commerce bäst lämpad för B2C-scenarier.</span><span class="sxs-lookup"><span data-stu-id="34d7d-109">Among these options, the Commerce pricing engine is best suited to B2C scenarios.</span></span>

## <a name="use-the-commerce-pricing-engine-in-sales"></a><span data-ttu-id="34d7d-110">Använda prissättningsmotorn i Commerce i Sales</span><span class="sxs-lookup"><span data-stu-id="34d7d-110">Use the Commerce pricing engine in Sales</span></span>

> [!NOTE]
> <span data-ttu-id="34d7d-111">För närvarande kan prissättningsmotorn i Commerce bara användas för att skapa offerter i Sales.</span><span class="sxs-lookup"><span data-stu-id="34d7d-111">Currently, the Commerce pricing engine can be used only for quotation creation in the Sales.</span></span> <span data-ttu-id="34d7d-112">Integration av försäljningsorder med prissättningsmotorn i Commerce är inte tillgänglig ännu.</span><span class="sxs-lookup"><span data-stu-id="34d7d-112">Sales order integration with the Commerce pricing engine isn't yet available.</span></span>

<span data-ttu-id="34d7d-113">När användarna initierar en offert i Sales kopieras offertinformationen till Commerce med ramverket för dubbelriktad skrivning.</span><span class="sxs-lookup"><span data-stu-id="34d7d-113">When users initiate a quotation in Sales, the dual-write framework copies the quotation details to Commerce.</span></span> <span data-ttu-id="34d7d-114">Alla ändringar av befintliga offertrader eller eventuella nyligen tillagda offertrader i Sales kopieras till Commerce.</span><span class="sxs-lookup"><span data-stu-id="34d7d-114">Any changes to existing quotation lines or any newly added quotation lines in Sales are copied to Commerce.</span></span> <span data-ttu-id="34d7d-115">När användarna vill använda prissättningsmotorn i Commerce för att prissätta offerten kan de välja **Prisoffert** för att uppdatera offertens priser, baserat på prissättningsmotorn i Commerce.</span><span class="sxs-lookup"><span data-stu-id="34d7d-115">When users want to use the Commerce pricing engine to price the quotation, they can select **Price quote** to update the prices of the quotation, based on the Commerce pricing engine.</span></span> <span data-ttu-id="34d7d-116">Priserna uppdateras sedan automatiskt i både Sales och Commerce.</span><span class="sxs-lookup"><span data-stu-id="34d7d-116">Prices are then automatically updated in both Sales and Commerce.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="34d7d-117">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="34d7d-117">Prerequisites</span></span>

- <span data-ttu-id="34d7d-118">Innan du kan använda prissättningsmotorn i Commerce i Sales måste du följa stegen i [Potentiell kund till kontanter vid dubbelriktad skrivning](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-prospect-to-cash/).</span><span class="sxs-lookup"><span data-stu-id="34d7d-118">Before you can use the Commerce pricing engine in Sales, you must follow the steps in [Prospect-to-cash in dual-write](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-prospect-to-cash/).</span></span>
- <span data-ttu-id="34d7d-119">Du måste stänga av utvärdering av handelsavtal för manuell registrering genom att utföra följande steg:</span><span class="sxs-lookup"><span data-stu-id="34d7d-119">You must turn off trade agreement evaluation for manual entry by following these steps:</span></span>

    1. <span data-ttu-id="34d7d-120">I Commerce-miljön går du till **Kundreskontra \> Inställningar \> Parametrar för kundreskontra**.</span><span class="sxs-lookup"><span data-stu-id="34d7d-120">In your Commerce environment, go to **Accounts receivable \> Setup \> Accounts receivable parameters**.</span></span>
    1. <span data-ttu-id="34d7d-121">på fliken **Priser** på FastTab **Utvärdering av handelsavtal** avmarkerar du kryssrutan **Manuell registrering**.</span><span class="sxs-lookup"><span data-stu-id="34d7d-121">On the **Prices** tab, on the **Trade agreement evaluation** FastTab, clear the **Manual entry** check box.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="34d7d-122">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="34d7d-122">Additional resources</span></span>

[<span data-ttu-id="34d7d-123">Potentiell kund till kontanter vid dubbel skrivning</span><span class="sxs-lookup"><span data-stu-id="34d7d-123">Prospect-to-cash in dual-write</span></span>](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-prospect-to-cash/)


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]