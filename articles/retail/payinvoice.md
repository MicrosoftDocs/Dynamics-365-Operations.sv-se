---
title: "Ordna scenarier för fakturabetalning"
description: "Detta ämne beskriver hur man konfigurerar Dynamics 365 for Retail så att det stöder olika scenarier som gäller fakturabetalningar."
author: josaw1
manager: AnnBe
ms.date: 11/14/2018
ms.topic: index-page
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 
ms.assetid: ed0f77f7-3609-4330-bebd-ca3134575216
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2018-11-15
ms.dyn365.ops.version: 
ms.translationtype: HT
ms.sourcegitcommit: 3331b984693c58c6ee8c49b98ed7d3a8df5b79ff
ms.openlocfilehash: 53c4b9a9c9dac1add7021d909b2c8900d11e5c0c
ms.contentlocale: sv-se
ms.lasthandoff: 12/04/2018

---
# <a name="set-up-pay-invoice-scenarios"></a><span data-ttu-id="d1f09-103">Ordna scenarier för fakturabetalning</span><span class="sxs-lookup"><span data-stu-id="d1f09-103">Set up pay invoice scenarios</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="d1f09-104">Funktionen Betala fakturan i Dynamics 365 for Retail har utökats och stöder nu detta:</span><span class="sxs-lookup"><span data-stu-id="d1f09-104">The Pay invoice functionality in Dynamics 365 for Retail has been expanded to support:</span></span>
- <span data-ttu-id="d1f09-105">Betalning av flera försäljningsorderfakturor i samma kassatransaktion.</span><span class="sxs-lookup"><span data-stu-id="d1f09-105">Payoff of multiple sales order invoices in a single POS transaction.</span></span>
- <span data-ttu-id="d1f09-106">De typer av kundfakturor som går att betala är fritextfakturor, projektbaserade fakturor och kreditfakturor.</span><span class="sxs-lookup"><span data-stu-id="d1f09-106">Payment of various customer invoice types including free text invoices, project-based invoices, and credit notes.</span></span>

<span data-ttu-id="d1f09-107">Om du vill aktivera dessa scenarier måste funktionsprofilen för butiker konfigureras enligt beskrivningen nedan.</span><span class="sxs-lookup"><span data-stu-id="d1f09-107">To enable these scenarios, the functionality profile for stores must be configured as outlined in below.</span></span>  

1. <span data-ttu-id="d1f09-108">Öppna **Retail > Kanalinställningar > Kassainställning > Kassaprofiler > Funktionsprofiler** och välj en profil som är kopplad till butikerna du vill göra ändringar för.</span><span class="sxs-lookup"><span data-stu-id="d1f09-108">Go to **Retail > Channel setup > POS setup > POS profiles > Functionality profiles** and select a profile that's linked to the stores that you want to make the changes for.</span></span>

1. <span data-ttu-id="d1f09-109">Konfigurera de följande parametrarna på fliken **Funktioner** efter behov.</span><span class="sxs-lookup"><span data-stu-id="d1f09-109">On the **Functions** tab, configure the following parameters as needed.</span></span>

    - <span data-ttu-id="d1f09-110">**Försäljningsorderfaktura** – Välj **Ja** så att användarna kan betala en eller flera försäljningsorderbaserade fakturor i samma kassatransaktion.</span><span class="sxs-lookup"><span data-stu-id="d1f09-110">**Sales order invoice** - Select **Yes** to allow users to pay one or more sales order-based invoices in a single POS transaction.</span></span>

    - <span data-ttu-id="d1f09-111">**Fritextfaktura** – Välj **Ja** så att användarna kan betala en eller flera fritextbaserade fakturor i samma kassatransaktion.</span><span class="sxs-lookup"><span data-stu-id="d1f09-111">**Free text invoice** - Select **Yes** to allow users to pay one or more free text-based invoices in a single POS transaction.</span></span>

    - <span data-ttu-id="d1f09-112">**Projektfaktura** – Välj **Ja** så att användarna kan betala en eller flera projektbaserade fakturor i samma kassatransaktion.</span><span class="sxs-lookup"><span data-stu-id="d1f09-112">**Project invoice** - Select **Yes** to allow users to pay one or more project-based invoices in a single POS transaction.</span></span>

    - <span data-ttu-id="d1f09-113">**Försäljningsorder - Kreditfaktura** – Välj **Ja** så att användarna kan kvitta flera försäljningsorderbaserade kreditfakturor mot öppna fakturor eller bearbeta en återbetalning till kunden för en öppen kreditfaktura.</span><span class="sxs-lookup"><span data-stu-id="d1f09-113">**Sales order credit note** - Select **Yes** to allow users to settle multiple sales order-based credit notes against open invoices or process a refund to the customer for an open credit note.</span></span>

> [!NOTE]
> <span data-ttu-id="d1f09-114">Betalning eller kvittning av partiella belopp stöds inte ännu.</span><span class="sxs-lookup"><span data-stu-id="d1f09-114">Payment or settlement of partial amounts is not yet supported.</span></span>

