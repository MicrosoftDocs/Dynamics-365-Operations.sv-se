---
title: "Förhindra rabatter för butiksprodukter"
description: "Det finns olika skäl varför återförsäljare kan vilja förhindra att vissa produkter rabatteras från ett erbjudande eller vid försäljningen i kassan."
author: jblucher
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
ms.search.form: RetailPeriodicDiscount
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 85183
ms.assetid: e8c5a24f-7edd-4fd6-af80-5e0ac9f03127
ms.search.region: Global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 70139c124486e3e6a01c1c08e71f140dcf1864c0
ms.openlocfilehash: e0d3a16da6a673f9ce6a025a7d4bde9ffb1a9e9b
ms.contentlocale: sv-se
ms.lasthandoff: 10/24/2017

---

# <a name="prevent-discounts-for-retail-products"></a>Förhindra rabatter för butiksprodukter

[!include[banner](includes/banner.md)]

Det finns olika skäl varför återförsäljare kan vilja förhindra att vissa produkter rabatteras från ett erbjudande eller vid försäljningen i kassan.

Följande alternativ, som du hittar på fliken **Butik** för frisläppta produkter, tillåter att produkten konfigureras för att förhindra alla eller manuella rabatter. Inställningarna kan också anges på kategorinivå från butikskategorihierarki.

**Förhindra alla rabatter**: Markera det här alternativet om du vill förhindra att alla typer av rabatter används för den här produkten. Detta inkluderar erbjudanden som till exempel mixa och matcha, kvantitets- och tröskelvärdesrabatter samt manuella rad- och transaktionsrabatter som används vid försäljning av en kassaanvändare.

**Förhindra manuella rabatter**: Markera det här alternativet för att bara förhindra manuella rad- och transaktionsrabatter som används vid försäljning av en kassaanvändare. Produkter med det här alternativet är fortfarande berättigade till erbjudanden, såsom rabatter för mixa och matcha och kvantitets- och tröskelvärdesrabatter.

**Observera**: De här inställningarna begränsar inte hur prisåsidosättningsåtgärden eftersom de anger grundpriset och behandlas inte som en rabatt.  

[![förhindra rabattfält](./media/prevent discounts.png)](./media/prevent discounts.png)

