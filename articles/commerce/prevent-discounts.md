---
title: Alternativ för att förhindra rabatter för butiksprodukter
description: Det finns olika skäl varför återförsäljare kan vilja förhindra att vissa produkter rabatteras från ett erbjudande eller vid försäljningen i POS.
author: jblucher
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RetailPeriodicDiscount
audience: Application User
ms.reviewer: josaw
ms.custom: 85183
ms.assetid: e8c5a24f-7edd-4fd6-af80-5e0ac9f03127
ms.search.region: Global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: ddf3834057c89f5a091f09412183ca79540225fc
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5802897"
---
# <a name="options-for-preventing-discounts-for-retail-products"></a><span data-ttu-id="b4c64-103">Alternativ för att förhindra rabatter för butiksprodukter</span><span class="sxs-lookup"><span data-stu-id="b4c64-103">Options for preventing discounts for retail products</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="b4c64-104">Det finns olika skäl varför återförsäljare kan vilja förhindra att vissa produkter rabatteras från ett erbjudande eller vid försäljningen i POS.</span><span class="sxs-lookup"><span data-stu-id="b4c64-104">There are various reasons why retailers may want to prevent some products from being discounted, either from a promotion or during the sale at the POS.</span></span>

<span data-ttu-id="b4c64-105">Följande alternativ, som du hittar på fliken **Commerce** för frisläppta produkter, tillåter att produkten konfigureras för att förhindra alla eller manuella rabatter.</span><span class="sxs-lookup"><span data-stu-id="b4c64-105">The following options, which can be found on the **Commerce** tab of released products, will allow the product to be configured to prevent all or manual discounts.</span></span> <span data-ttu-id="b4c64-106">Inställningarna kan också anges på kategorinivå från kategorihierarki.</span><span class="sxs-lookup"><span data-stu-id="b4c64-106">The settings can also be specified at the category level from the category hierarchy.</span></span>

- <span data-ttu-id="b4c64-107">**Förhindra alla rabatter** – Markera det här alternativet om du vill förhindra att alla typer av rabatter används för den här produkten.</span><span class="sxs-lookup"><span data-stu-id="b4c64-107">**Prevent all discounts** – Select this option to prevent all types of discounts from being applied to this product.</span></span> <span data-ttu-id="b4c64-108">Detta inkluderar erbjudanden som till exempel mixa och matcha, kvantitets- och tröskelvärdesrabatter samt manuella rad- och transaktionsrabatter som används vid försäljning av en kassaanvändare.</span><span class="sxs-lookup"><span data-stu-id="b4c64-108">This includes promotions such as mix and match, quantity and threshold discounts, as well as manual line and transaction discounts that are applied during a sale by a POS user.</span></span>
- <span data-ttu-id="b4c64-109">**Förhindra manuella rabatter** – Markera det här alternativet för att bara förhindra manuella rad- och transaktionsrabatter som används vid försäljning av en kassaanvändare.</span><span class="sxs-lookup"><span data-stu-id="b4c64-109">**Prevent manual discounts** – Select this option to only prevent the manual line or transaction discounts that are applied during a sale by a POS user.</span></span> <span data-ttu-id="b4c64-110">Produkter med det här alternativet är fortfarande berättigade till erbjudanden, såsom rabatter för mixa och matcha och kvantitets- och tröskelvärdesrabatter.</span><span class="sxs-lookup"><span data-stu-id="b4c64-110">Products with this option selected are still eligible for promotions, such as mix and match and quantity and threshold discounts.</span></span>

> [!NOTE]
> <span data-ttu-id="b4c64-111">De här inställningarna begränsar inte hur prisåsidosättningsåtgärden eftersom de anger grundpriset och behandlas inte som en rabatt.</span><span class="sxs-lookup"><span data-stu-id="b4c64-111">These settings do not restrict the price override operation, because that sets the base price and is not treated as a discount.</span></span>

<span data-ttu-id="b4c64-112">[![Förhindra rabattfält](./media/prevent-discounts.png)](./media/prevent-discounts.png)</span><span class="sxs-lookup"><span data-stu-id="b4c64-112">[![Prevent discounts field](./media/prevent-discounts.png)](./media/prevent-discounts.png)</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]