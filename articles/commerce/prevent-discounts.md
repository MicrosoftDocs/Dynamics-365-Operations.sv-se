---
title: Alternativ för att förhindra rabatter för butiksprodukter
description: Det finns olika skäl varför återförsäljare kan vilja förhindra att vissa produkter rabatteras från ett erbjudande eller vid försäljningen i POS.
author: jblucher
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
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
ms.openlocfilehash: f5037067917290f21f681d2446a0e1ab0e31228c
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5231210"
---
# <a name="options-for-preventing-discounts-for-retail-products"></a>Alternativ för att förhindra rabatter för butiksprodukter

[!include [banner](includes/banner.md)]

Det finns olika skäl varför återförsäljare kan vilja förhindra att vissa produkter rabatteras från ett erbjudande eller vid försäljningen i POS.

Följande alternativ, som du hittar på fliken **Commerce** för frisläppta produkter, tillåter att produkten konfigureras för att förhindra alla eller manuella rabatter. Inställningarna kan också anges på kategorinivå från kategorihierarki.

- **Förhindra alla rabatter** – Markera det här alternativet om du vill förhindra att alla typer av rabatter används för den här produkten. Detta inkluderar erbjudanden som till exempel mixa och matcha, kvantitets- och tröskelvärdesrabatter samt manuella rad- och transaktionsrabatter som används vid försäljning av en kassaanvändare.
- **Förhindra manuella rabatter** – Markera det här alternativet för att bara förhindra manuella rad- och transaktionsrabatter som används vid försäljning av en kassaanvändare. Produkter med det här alternativet är fortfarande berättigade till erbjudanden, såsom rabatter för mixa och matcha och kvantitets- och tröskelvärdesrabatter.

> [!NOTE]
> De här inställningarna begränsar inte hur prisåsidosättningsåtgärden eftersom de anger grundpriset och behandlas inte som en rabatt.

[![Förhindra rabattfält](./media/prevent-discounts.png)](./media/prevent-discounts.png)


[!INCLUDE[footer-include](../includes/footer-banner.md)]